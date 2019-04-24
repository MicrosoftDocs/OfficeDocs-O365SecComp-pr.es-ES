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
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32256828"
---
# <a name="eu-passport-number"></a><span data-ttu-id="5aa15-104">Número de pasaporte de la UE</span><span class="sxs-lookup"><span data-stu-id="5aa15-104">EU Passport Number</span></span>

<span data-ttu-id="5aa15-105">En este tema se muestra qué busca una directiva de prevención de pérdida de datos (DLP) cuando detecta el tipo de información confidencial de número de pasaporte de la UE.</span><span class="sxs-lookup"><span data-stu-id="5aa15-105">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Passport Number sensitive information type.</span></span> <span data-ttu-id="5aa15-106">Este tipo de información confidencial define distintos patrones, palabras clave y otras pruebas para cada país.</span><span class="sxs-lookup"><span data-stu-id="5aa15-106">This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="5aa15-107">Austria</span><span class="sxs-lookup"><span data-stu-id="5aa15-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="5aa15-108">Formato</span><span class="sxs-lookup"><span data-stu-id="5aa15-108">Format</span></span>

<span data-ttu-id="5aa15-109">Una letra seguida de un espacio opcional y siete dígitos</span><span class="sxs-lookup"><span data-stu-id="5aa15-109">One letter followed by an optional space and seven digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="5aa15-110">Patrón</span><span class="sxs-lookup"><span data-stu-id="5aa15-110">Pattern</span></span>

<span data-ttu-id="5aa15-111">Una combinación de una letra, siete dígitos y un espacio:</span><span class="sxs-lookup"><span data-stu-id="5aa15-111">A combination of one letter, seven digits, and one space:</span></span>
  
- <span data-ttu-id="5aa15-112">Una letra (no distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="5aa15-112">One letter (not case sensitive)</span></span>
    
- <span data-ttu-id="5aa15-113">Un espacio (opcional)</span><span class="sxs-lookup"><span data-stu-id="5aa15-113">One space (optional)</span></span>
    
- <span data-ttu-id="5aa15-114">Siete dígitos</span><span class="sxs-lookup"><span data-stu-id="5aa15-114">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="5aa15-115">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="5aa15-115">Checksum</span></span>

<span data-ttu-id="5aa15-116">No aplicable</span><span class="sxs-lookup"><span data-stu-id="5aa15-116">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="5aa15-117">Definición</span><span class="sxs-lookup"><span data-stu-id="5aa15-117">Definition</span></span>

<span data-ttu-id="5aa15-118">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="5aa15-118">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5aa15-119">La expresión `Regex_austria_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="5aa15-119">The regular expression  `Regex_austria_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5aa15-120">Se encuentra una `Keywords_austria_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="5aa15-120">A keyword from  `Keywords_austria_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_passport_number" />
          <Match idRef="Keywords_austria_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="5aa15-121">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="5aa15-121">Keywords</span></span>

<span data-ttu-id="5aa15-122">| |</span><span class="sxs-lookup"><span data-stu-id="5aa15-122"></span></span>
|<span data-ttu-id="5aa15-123">**Keywords_austria_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="5aa15-123">**Keywords_austria_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="5aa15-124">passport number</span><span class="sxs-lookup"><span data-stu-id="5aa15-124">passport number</span></span>  <br/> <span data-ttu-id="5aa15-125">número de pasaporte austriaco</span><span class="sxs-lookup"><span data-stu-id="5aa15-125">austrian passport number</span></span>  <br/> <span data-ttu-id="5aa15-126">n.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="5aa15-126">passport no</span></span>  <br/> <span data-ttu-id="5aa15-127">reisepass</span><span class="sxs-lookup"><span data-stu-id="5aa15-127">reisepass</span></span>  <br/> <span data-ttu-id="5aa15-128">österreichisch reisepass</span><span class="sxs-lookup"><span data-stu-id="5aa15-128">österreichisch reisepass</span></span>  <br/> |
   
## <a name="belgium"></a><span data-ttu-id="5aa15-129">Bélgica</span><span class="sxs-lookup"><span data-stu-id="5aa15-129">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="5aa15-130">Formato</span><span class="sxs-lookup"><span data-stu-id="5aa15-130">Format</span></span>

<span data-ttu-id="5aa15-131">Dos letras seguidas de seis dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="5aa15-131">Two letters followed by six digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="5aa15-132">Patrón</span><span class="sxs-lookup"><span data-stu-id="5aa15-132">Pattern</span></span>

<span data-ttu-id="5aa15-133">Dos letras y seguidas de seis dígitos</span><span class="sxs-lookup"><span data-stu-id="5aa15-133">Two letters and followed by six digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="5aa15-134">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="5aa15-134">Checksum</span></span>

<span data-ttu-id="5aa15-135">No aplicable</span><span class="sxs-lookup"><span data-stu-id="5aa15-135">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="5aa15-136">Definición</span><span class="sxs-lookup"><span data-stu-id="5aa15-136">Definition</span></span>

<span data-ttu-id="5aa15-137">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="5aa15-137">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5aa15-138">La expresión `Regex_belgium_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="5aa15-138">The regular expression  `Regex_belgium_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5aa15-139">Se encuentra una `Keywords_belgium_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="5aa15-139">A keyword from  `Keywords_belgium_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium__eu_passport_number" />
          <Match idRef="Keywords_belgium_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="5aa15-140">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="5aa15-140">Keywords</span></span>

<span data-ttu-id="5aa15-141">| |</span><span class="sxs-lookup"><span data-stu-id="5aa15-141"></span></span>
|<span data-ttu-id="5aa15-142">**Keywords_belgium_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="5aa15-142">**Keywords_belgium_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="5aa15-143">passport number</span><span class="sxs-lookup"><span data-stu-id="5aa15-143">passport number</span></span>  <br/> <span data-ttu-id="5aa15-144">número de pasaporte belga</span><span class="sxs-lookup"><span data-stu-id="5aa15-144">belgian passport number</span></span>  <br/> <span data-ttu-id="5aa15-145">n.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="5aa15-145">passport no</span></span>  <br/> <span data-ttu-id="5aa15-146">paspoort</span><span class="sxs-lookup"><span data-stu-id="5aa15-146">paspoort</span></span>  <br/> <span data-ttu-id="5aa15-147">paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="5aa15-147">paspoortnummer</span></span>  <br/> <span data-ttu-id="5aa15-148">reisepass kein</span><span class="sxs-lookup"><span data-stu-id="5aa15-148">reisepass kein</span></span>  <br/> <span data-ttu-id="5aa15-149">reisepass</span><span class="sxs-lookup"><span data-stu-id="5aa15-149">reisepass</span></span>  <br/> |
   
## <a name="bulgaria"></a><span data-ttu-id="5aa15-150">Bulgaria</span><span class="sxs-lookup"><span data-stu-id="5aa15-150">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="5aa15-151">Formato</span><span class="sxs-lookup"><span data-stu-id="5aa15-151">Format</span></span>

<span data-ttu-id="5aa15-152">Nueve dígitos sin espacios y delimitadores</span><span class="sxs-lookup"><span data-stu-id="5aa15-152">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="5aa15-153">Patrón</span><span class="sxs-lookup"><span data-stu-id="5aa15-153">Pattern</span></span>

 <span data-ttu-id="5aa15-154">Nueve dígitos</span><span class="sxs-lookup"><span data-stu-id="5aa15-154">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="5aa15-155">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="5aa15-155">Checksum</span></span>

<span data-ttu-id="5aa15-156">No</span><span class="sxs-lookup"><span data-stu-id="5aa15-156">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="5aa15-157">Definición</span><span class="sxs-lookup"><span data-stu-id="5aa15-157">Definition</span></span>

<span data-ttu-id="5aa15-158">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="5aa15-158">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5aa15-159">La expresión `Regex_bulgaria_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="5aa15-159">The regular expression  `Regex_bulgaria_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5aa15-160">Se encuentra una `Keywords_bulgaria_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="5aa15-160">A keyword from  `Keywords_bulgaria_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_passport_number" />
          <Match idRef="Keywords_bulgaria_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="5aa15-161">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="5aa15-161">Keywords</span></span>

<span data-ttu-id="5aa15-162">| |</span><span class="sxs-lookup"><span data-stu-id="5aa15-162"></span></span>
|<span data-ttu-id="5aa15-163">**Keywords_bulgaria_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="5aa15-163">**Keywords_bulgaria_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="5aa15-164">passport number</span><span class="sxs-lookup"><span data-stu-id="5aa15-164">passport number</span></span>  <br/> <span data-ttu-id="5aa15-165">número de pasaporte búlgaro</span><span class="sxs-lookup"><span data-stu-id="5aa15-165">bulgarian passport number</span></span>  <br/> <span data-ttu-id="5aa15-166">n.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="5aa15-166">passport no</span></span>  <br/> <span data-ttu-id="5aa15-167">номер на паспорта</span><span class="sxs-lookup"><span data-stu-id="5aa15-167">номер на паспорта</span></span>  <br/> |
   
## <a name="croatia"></a><span data-ttu-id="5aa15-168">Croacia</span><span class="sxs-lookup"><span data-stu-id="5aa15-168">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="5aa15-169">Formato</span><span class="sxs-lookup"><span data-stu-id="5aa15-169">Format</span></span>

<span data-ttu-id="5aa15-170">Nueve dígitos sin espacios y delimitadores</span><span class="sxs-lookup"><span data-stu-id="5aa15-170">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="5aa15-171">Patrón</span><span class="sxs-lookup"><span data-stu-id="5aa15-171">Pattern</span></span>

 <span data-ttu-id="5aa15-172">Nueve dígitos</span><span class="sxs-lookup"><span data-stu-id="5aa15-172">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="5aa15-173">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="5aa15-173">Checksum</span></span>

<span data-ttu-id="5aa15-174">No</span><span class="sxs-lookup"><span data-stu-id="5aa15-174">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="5aa15-175">Definición</span><span class="sxs-lookup"><span data-stu-id="5aa15-175">Definition</span></span>

<span data-ttu-id="5aa15-176">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="5aa15-176">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5aa15-177">La expresión `Regex_croatia_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="5aa15-177">The regular expression  `Regex_croatia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5aa15-178">Se encuentra una `Keywords_croatia_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="5aa15-178">A keyword from  `Keywords_croatia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_passport_number" />
          <Match idRef="Keywords_croatia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="5aa15-179">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="5aa15-179">Keywords</span></span>

<span data-ttu-id="5aa15-180">| |</span><span class="sxs-lookup"><span data-stu-id="5aa15-180"></span></span>
|<span data-ttu-id="5aa15-181">**Keywords_croatia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="5aa15-181">**Keywords_croatia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="5aa15-182">passport number</span><span class="sxs-lookup"><span data-stu-id="5aa15-182">passport number</span></span>  <br/> <span data-ttu-id="5aa15-183">número de pasaporte de croata</span><span class="sxs-lookup"><span data-stu-id="5aa15-183">croatian passport number</span></span>  <br/> <span data-ttu-id="5aa15-184">n.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="5aa15-184">passport no</span></span>  <br/> <span data-ttu-id="5aa15-185">Broj putovnice</span><span class="sxs-lookup"><span data-stu-id="5aa15-185">broj putovnice</span></span>  <br/> |
   
## <a name="cyprus"></a><span data-ttu-id="5aa15-186">Chipre</span><span class="sxs-lookup"><span data-stu-id="5aa15-186">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="5aa15-187">Formato</span><span class="sxs-lookup"><span data-stu-id="5aa15-187">Format</span></span>

<span data-ttu-id="5aa15-188">Una letra seguida de 6-8 dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="5aa15-188">One letter followed by 6-8 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="5aa15-189">Patrón</span><span class="sxs-lookup"><span data-stu-id="5aa15-189">Pattern</span></span>

<span data-ttu-id="5aa15-190">Una letra seguida de seis a ocho dígitos</span><span class="sxs-lookup"><span data-stu-id="5aa15-190">One letter followed by six to eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="5aa15-191">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="5aa15-191">Checksum</span></span>

<span data-ttu-id="5aa15-192">No</span><span class="sxs-lookup"><span data-stu-id="5aa15-192">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="5aa15-193">Definición</span><span class="sxs-lookup"><span data-stu-id="5aa15-193">Definition</span></span>

<span data-ttu-id="5aa15-194">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="5aa15-194">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5aa15-195">La expresión `Regex_cyprus_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="5aa15-195">The regular expression  `Regex_cyprus_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5aa15-196">Se encuentra una `Keywords_cyprus_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="5aa15-196">A keyword from  `Keywords_cyprus_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_passport_number" />
          <Match idRef="Keywords_cyprus_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="5aa15-197">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="5aa15-197">Keywords</span></span>

<span data-ttu-id="5aa15-198">| |</span><span class="sxs-lookup"><span data-stu-id="5aa15-198"></span></span>
|<span data-ttu-id="5aa15-199">**Keywords_cyprus_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="5aa15-199">**Keywords_cyprus_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="5aa15-200">passport number</span><span class="sxs-lookup"><span data-stu-id="5aa15-200">passport number</span></span>  <br/> <span data-ttu-id="5aa15-201">número de pasaporte de Chipre</span><span class="sxs-lookup"><span data-stu-id="5aa15-201">cyprus passport number</span></span>  <br/> <span data-ttu-id="5aa15-202">n.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="5aa15-202">passport no</span></span>  <br/> <span data-ttu-id="5aa15-203">αριθμό διαβατηρίου</span><span class="sxs-lookup"><span data-stu-id="5aa15-203">αριθμό διαβατηρίου</span></span>  <br/> |
   
## <a name="czech-republic"></a><span data-ttu-id="5aa15-204">Chequia</span><span class="sxs-lookup"><span data-stu-id="5aa15-204">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="5aa15-205">Formato</span><span class="sxs-lookup"><span data-stu-id="5aa15-205">Format</span></span>

<span data-ttu-id="5aa15-206">Ocho dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="5aa15-206">Eight digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="5aa15-207">Patrón</span><span class="sxs-lookup"><span data-stu-id="5aa15-207">Pattern</span></span>

<span data-ttu-id="5aa15-208">Ocho dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="5aa15-208">Eight digits without spaces or delimiters</span></span>
  
### <a name="checksum"></a><span data-ttu-id="5aa15-209">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="5aa15-209">Checksum</span></span>

<span data-ttu-id="5aa15-210">No</span><span class="sxs-lookup"><span data-stu-id="5aa15-210">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="5aa15-211">Definición</span><span class="sxs-lookup"><span data-stu-id="5aa15-211">Definition</span></span>

<span data-ttu-id="5aa15-212">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="5aa15-212">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5aa15-213">La expresión `Regex_czech_republic_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="5aa15-213">The regular expression  `Regex_czech_republic_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5aa15-214">Se encuentra una `Keywords_czech_republic_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="5aa15-214">A keyword from  `Keywords_czech_republic_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_passport_number" />
          <Match idRef="Keywords_czech_republic_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="5aa15-215">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="5aa15-215">Keywords</span></span>

<span data-ttu-id="5aa15-216">| |</span><span class="sxs-lookup"><span data-stu-id="5aa15-216"></span></span>
|<span data-ttu-id="5aa15-217">**Keywords_czech_republic_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="5aa15-217">**Keywords_czech_republic_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="5aa15-218">passport number</span><span class="sxs-lookup"><span data-stu-id="5aa15-218">passport number</span></span>  <br/> <span data-ttu-id="5aa15-219">número de pasaporte Checo</span><span class="sxs-lookup"><span data-stu-id="5aa15-219">czech passport number</span></span>  <br/> <span data-ttu-id="5aa15-220">n.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="5aa15-220">passport no</span></span>  <br/> <span data-ttu-id="5aa15-221">Cestovní PAS</span><span class="sxs-lookup"><span data-stu-id="5aa15-221">cestovní pas</span></span>  <br/> <span data-ttu-id="5aa15-222">PAS</span><span class="sxs-lookup"><span data-stu-id="5aa15-222">pas</span></span>  <br/> |
   
## <a name="denmark"></a><span data-ttu-id="5aa15-223">Dinamarca</span><span class="sxs-lookup"><span data-stu-id="5aa15-223">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="5aa15-224">Formato</span><span class="sxs-lookup"><span data-stu-id="5aa15-224">Format</span></span>

<span data-ttu-id="5aa15-225">Nueve dígitos sin espacios y delimitadores</span><span class="sxs-lookup"><span data-stu-id="5aa15-225">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="5aa15-226">Patrón</span><span class="sxs-lookup"><span data-stu-id="5aa15-226">Pattern</span></span>

 <span data-ttu-id="5aa15-227">Nueve dígitos</span><span class="sxs-lookup"><span data-stu-id="5aa15-227">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="5aa15-228">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="5aa15-228">Checksum</span></span>

<span data-ttu-id="5aa15-229">No</span><span class="sxs-lookup"><span data-stu-id="5aa15-229">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="5aa15-230">Definición</span><span class="sxs-lookup"><span data-stu-id="5aa15-230">Definition</span></span>

<span data-ttu-id="5aa15-231">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="5aa15-231">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5aa15-232">La expresión `Regex_denmark_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="5aa15-232">The regular expression  `Regex_denmark_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5aa15-233">Se encuentra una `Keywords_denmark_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="5aa15-233">A keyword from  `Keywords_denmark_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_passport_number" />
          <Match idRef="Keywords_denmark_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="5aa15-234">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="5aa15-234">Keywords</span></span>

<span data-ttu-id="5aa15-235">| |</span><span class="sxs-lookup"><span data-stu-id="5aa15-235"></span></span>
|<span data-ttu-id="5aa15-236">**Keywords_denmark_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="5aa15-236">**Keywords_denmark_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="5aa15-237">passport number</span><span class="sxs-lookup"><span data-stu-id="5aa15-237">passport number</span></span>  <br/> <span data-ttu-id="5aa15-238">número de pasaporte danés</span><span class="sxs-lookup"><span data-stu-id="5aa15-238">danish passport number</span></span>  <br/> <span data-ttu-id="5aa15-239">n.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="5aa15-239">passport no</span></span>  <br/> <span data-ttu-id="5aa15-240">PAS</span><span class="sxs-lookup"><span data-stu-id="5aa15-240">pas</span></span>  <br/> <span data-ttu-id="5aa15-241">pasnummer</span><span class="sxs-lookup"><span data-stu-id="5aa15-241">pasnummer</span></span>  <br/> |
   
## <a name="estonia"></a><span data-ttu-id="5aa15-242">Estonia</span><span class="sxs-lookup"><span data-stu-id="5aa15-242">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="5aa15-243">Formato</span><span class="sxs-lookup"><span data-stu-id="5aa15-243">Format</span></span>

<span data-ttu-id="5aa15-244">Una letra seguida de siete dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="5aa15-244">One letter followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="5aa15-245">Patrón</span><span class="sxs-lookup"><span data-stu-id="5aa15-245">Pattern</span></span>

<span data-ttu-id="5aa15-246">Una letra seguida de siete dígitos</span><span class="sxs-lookup"><span data-stu-id="5aa15-246">One letter followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="5aa15-247">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="5aa15-247">Checksum</span></span>

<span data-ttu-id="5aa15-248">No</span><span class="sxs-lookup"><span data-stu-id="5aa15-248">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="5aa15-249">Definición</span><span class="sxs-lookup"><span data-stu-id="5aa15-249">Definition</span></span>

<span data-ttu-id="5aa15-250">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="5aa15-250">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5aa15-251">La expresión `Regex_estonia_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="5aa15-251">The regular expression  `Regex_estonia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5aa15-252">Se encuentra una `Keywords_estonia_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="5aa15-252">A keyword from  `Keywords_estonia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_passport_number" />
          <Match idRef="Keywords_estonia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="5aa15-253">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="5aa15-253">Keywords</span></span>

<span data-ttu-id="5aa15-254">| |</span><span class="sxs-lookup"><span data-stu-id="5aa15-254"></span></span>
|<span data-ttu-id="5aa15-255">**Keywords_estonia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="5aa15-255">**Keywords_estonia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="5aa15-256">passport number</span><span class="sxs-lookup"><span data-stu-id="5aa15-256">passport number</span></span>  <br/> <span data-ttu-id="5aa15-257">número de pasaporte de estonio</span><span class="sxs-lookup"><span data-stu-id="5aa15-257">estonian passport number</span></span>  <br/> <span data-ttu-id="5aa15-258">n.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="5aa15-258">passport no</span></span>  <br/> <span data-ttu-id="5aa15-259">Eesti kodaniku Pass</span><span class="sxs-lookup"><span data-stu-id="5aa15-259">eesti kodaniku pass</span></span>  <br/> |
   
## <a name="finland"></a><span data-ttu-id="5aa15-260">Finlandia</span><span class="sxs-lookup"><span data-stu-id="5aa15-260">Finland</span></span>

<span data-ttu-id="5aa15-261">Para obtener más información, consulte la sección "número de pasaporte de Finlandia" en [Qué buscan los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="5aa15-261">For details, see the section "Finland Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="france"></a><span data-ttu-id="5aa15-262">Francia</span><span class="sxs-lookup"><span data-stu-id="5aa15-262">France</span></span>

<span data-ttu-id="5aa15-263">Para obtener más información, consulte la sección "número de pasaporte de Francia" en [Qué buscan los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="5aa15-263">For details, see the section "France Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="germany"></a><span data-ttu-id="5aa15-264">Alemania</span><span class="sxs-lookup"><span data-stu-id="5aa15-264">Germany</span></span>

<span data-ttu-id="5aa15-265">Para obtener más información, consulte la sección "número de pasaporte de Alemania" en [Qué buscan los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="5aa15-265">For details, see the section "Germany Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="greece"></a><span data-ttu-id="5aa15-266">Grecia</span><span class="sxs-lookup"><span data-stu-id="5aa15-266">Greece</span></span>

### <a name="format"></a><span data-ttu-id="5aa15-267">Formato</span><span class="sxs-lookup"><span data-stu-id="5aa15-267">Format</span></span>

<span data-ttu-id="5aa15-268">Dos letras seguidas de siete dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="5aa15-268">Two letters followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="5aa15-269">Patrón</span><span class="sxs-lookup"><span data-stu-id="5aa15-269">Pattern</span></span>

<span data-ttu-id="5aa15-270">Dos letras seguidas de siete dígitos</span><span class="sxs-lookup"><span data-stu-id="5aa15-270">Two letters followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="5aa15-271">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="5aa15-271">Checksum</span></span>

<span data-ttu-id="5aa15-272">No</span><span class="sxs-lookup"><span data-stu-id="5aa15-272">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="5aa15-273">Definición</span><span class="sxs-lookup"><span data-stu-id="5aa15-273">Definition</span></span>

<span data-ttu-id="5aa15-274">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="5aa15-274">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5aa15-275">La expresión `Regex_greece_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="5aa15-275">The regular expression  `Regex_greece_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5aa15-276">Se encuentra una `Keywords_greece_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="5aa15-276">A keyword from  `Keywords_greece_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_passport_number" />
          <Match idRef="Keywords_greece_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="5aa15-277">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="5aa15-277">Keywords</span></span>

<span data-ttu-id="5aa15-278">| |</span><span class="sxs-lookup"><span data-stu-id="5aa15-278"></span></span>
|<span data-ttu-id="5aa15-279">**Keywords_greece_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="5aa15-279">**Keywords_greece_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="5aa15-280">passport number</span><span class="sxs-lookup"><span data-stu-id="5aa15-280">passport number</span></span>  <br/> <span data-ttu-id="5aa15-281">número de pasaporte griego</span><span class="sxs-lookup"><span data-stu-id="5aa15-281">greek passport number</span></span>  <br/> <span data-ttu-id="5aa15-282">n.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="5aa15-282">passport no</span></span>  <br/> <span data-ttu-id="5aa15-283">διαβατηριο</span><span class="sxs-lookup"><span data-stu-id="5aa15-283">διαβατηριο</span></span>  <br/> |
   
## <a name="hungary"></a><span data-ttu-id="5aa15-284">Hungría</span><span class="sxs-lookup"><span data-stu-id="5aa15-284">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="5aa15-285">Formato</span><span class="sxs-lookup"><span data-stu-id="5aa15-285">Format</span></span>

<span data-ttu-id="5aa15-286">Dos letras seguidas por seis u siete dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="5aa15-286">Two letters followed by six or seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="5aa15-287">Patrón</span><span class="sxs-lookup"><span data-stu-id="5aa15-287">Pattern</span></span>

<span data-ttu-id="5aa15-288">Dos letras seguidas por seis o siete dígitos</span><span class="sxs-lookup"><span data-stu-id="5aa15-288">Two letters followed by six or seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="5aa15-289">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="5aa15-289">Checksum</span></span>

<span data-ttu-id="5aa15-290">No</span><span class="sxs-lookup"><span data-stu-id="5aa15-290">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="5aa15-291">Definición</span><span class="sxs-lookup"><span data-stu-id="5aa15-291">Definition</span></span>

<span data-ttu-id="5aa15-292">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="5aa15-292">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5aa15-293">La expresión `Regex_hungary_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="5aa15-293">The regular expression  `Regex_hungary_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5aa15-294">Se encuentra una `Keywords_hungary_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="5aa15-294">A keyword from  `Keywords_hungary_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_passport_number" />
          <Match idRef="Keywords_hungary_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="5aa15-295">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="5aa15-295">Keywords</span></span>

<span data-ttu-id="5aa15-296">| |</span><span class="sxs-lookup"><span data-stu-id="5aa15-296"></span></span>
|<span data-ttu-id="5aa15-297">**Keywords_hungary_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="5aa15-297">**Keywords_hungary_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="5aa15-298">passport number</span><span class="sxs-lookup"><span data-stu-id="5aa15-298">passport number</span></span>  <br/> <span data-ttu-id="5aa15-299">número de pasaporte Húngaro</span><span class="sxs-lookup"><span data-stu-id="5aa15-299">hungarian passport number</span></span>  <br/> <span data-ttu-id="5aa15-300">n.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="5aa15-300">passport no</span></span>  <br/> <span data-ttu-id="5aa15-301">útlevél száma</span><span class="sxs-lookup"><span data-stu-id="5aa15-301">útlevél száma</span></span>  <br/> |
   
## <a name="ireland"></a><span data-ttu-id="5aa15-302">Irlanda</span><span class="sxs-lookup"><span data-stu-id="5aa15-302">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="5aa15-303">Formato</span><span class="sxs-lookup"><span data-stu-id="5aa15-303">Format</span></span>

<span data-ttu-id="5aa15-304">Dos letras o dígitos seguidos de siete dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="5aa15-304">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="5aa15-305">Patrón</span><span class="sxs-lookup"><span data-stu-id="5aa15-305">Pattern</span></span>

<span data-ttu-id="5aa15-306">Dos letras o dígitos seguidos de siete dígitos:</span><span class="sxs-lookup"><span data-stu-id="5aa15-306">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="5aa15-307">Dos dígitos o letras (no distinguen entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="5aa15-307">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="5aa15-308">Siete dígitos</span><span class="sxs-lookup"><span data-stu-id="5aa15-308">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="5aa15-309">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="5aa15-309">Checksum</span></span>

<span data-ttu-id="5aa15-310">No</span><span class="sxs-lookup"><span data-stu-id="5aa15-310">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="5aa15-311">Definición</span><span class="sxs-lookup"><span data-stu-id="5aa15-311">Definition</span></span>

<span data-ttu-id="5aa15-312">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="5aa15-312">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5aa15-313">La expresión `Regex_ireland_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="5aa15-313">The regular expression  `Regex_ireland_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5aa15-314">Se encuentra una `Keywords_ireland_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="5aa15-314">A keyword from  `Keywords_ireland_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_passport_number" />
          <Match idRef="Keywords_ireland_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="5aa15-315">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="5aa15-315">Keywords</span></span>

<span data-ttu-id="5aa15-316">| |</span><span class="sxs-lookup"><span data-stu-id="5aa15-316"></span></span>
|<span data-ttu-id="5aa15-317">**Keywords_ireland_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="5aa15-317">**Keywords_ireland_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="5aa15-318">passport number</span><span class="sxs-lookup"><span data-stu-id="5aa15-318">passport number</span></span>  <br/> <span data-ttu-id="5aa15-319">número de pasaporte irlandés</span><span class="sxs-lookup"><span data-stu-id="5aa15-319">irish passport number</span></span>  <br/> <span data-ttu-id="5aa15-320">n.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="5aa15-320">passport no</span></span>  <br/> <span data-ttu-id="5aa15-321">PAS</span><span class="sxs-lookup"><span data-stu-id="5aa15-321">pas</span></span>  <br/> <span data-ttu-id="5aa15-322">usuarios</span><span class="sxs-lookup"><span data-stu-id="5aa15-322">passport</span></span>  <br/> <span data-ttu-id="5aa15-323">passeport</span><span class="sxs-lookup"><span data-stu-id="5aa15-323">passeport</span></span>  <br/> <span data-ttu-id="5aa15-324">passeport numero</span><span class="sxs-lookup"><span data-stu-id="5aa15-324">passeport numero</span></span>  <br/> |
   
## <a name="italy"></a><span data-ttu-id="5aa15-325">Italia</span><span class="sxs-lookup"><span data-stu-id="5aa15-325">Italy</span></span>

### <a name="format"></a><span data-ttu-id="5aa15-326">Formato</span><span class="sxs-lookup"><span data-stu-id="5aa15-326">Format</span></span>

<span data-ttu-id="5aa15-327">Dos letras o dígitos seguidos de siete dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="5aa15-327">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="5aa15-328">Patrón</span><span class="sxs-lookup"><span data-stu-id="5aa15-328">Pattern</span></span>

<span data-ttu-id="5aa15-329">Dos letras o dígitos seguidos de siete dígitos:</span><span class="sxs-lookup"><span data-stu-id="5aa15-329">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="5aa15-330">Dos dígitos o letras (no distinguen entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="5aa15-330">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="5aa15-331">Siete dígitos</span><span class="sxs-lookup"><span data-stu-id="5aa15-331">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="5aa15-332">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="5aa15-332">Checksum</span></span>

<span data-ttu-id="5aa15-333">No aplicable</span><span class="sxs-lookup"><span data-stu-id="5aa15-333">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="5aa15-334">Definición</span><span class="sxs-lookup"><span data-stu-id="5aa15-334">Definition</span></span>

<span data-ttu-id="5aa15-335">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="5aa15-335">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5aa15-336">La expresión `Regex_italy_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="5aa15-336">The regular expression  `Regex_italy_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5aa15-337">Se encuentra una `Keywords_italy_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="5aa15-337">A keyword from  `Keywords_italy_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_italy_eu_passport_number" />
          <Match idRef="Keywords_italy_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="5aa15-338">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="5aa15-338">Keywords</span></span>

<span data-ttu-id="5aa15-339">| |</span><span class="sxs-lookup"><span data-stu-id="5aa15-339"></span></span>
|<span data-ttu-id="5aa15-340">**Keywords_italy_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="5aa15-340">**Keywords_italy_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="5aa15-341">número de pasaporte Italiano</span><span class="sxs-lookup"><span data-stu-id="5aa15-341">italian passport number</span></span>  <br/> <span data-ttu-id="5aa15-342">Repubblica Italiana Passaporto</span><span class="sxs-lookup"><span data-stu-id="5aa15-342">repubblica italiana passaporto</span></span>  <br/> <span data-ttu-id="5aa15-343">Passaporto</span><span class="sxs-lookup"><span data-stu-id="5aa15-343">passaporto</span></span>  <br/> <span data-ttu-id="5aa15-344">Passaporto italiana</span><span class="sxs-lookup"><span data-stu-id="5aa15-344">passaporto italiana</span></span>  <br/> <span data-ttu-id="5aa15-345">passport number</span><span class="sxs-lookup"><span data-stu-id="5aa15-345">passport number</span></span>  <br/> <span data-ttu-id="5aa15-346">italiana Passaporto numero</span><span class="sxs-lookup"><span data-stu-id="5aa15-346">italiana passaporto numero</span></span>  <br/> <span data-ttu-id="5aa15-347">Passaporto numero</span><span class="sxs-lookup"><span data-stu-id="5aa15-347">passaporto numero</span></span>  <br/> <span data-ttu-id="5aa15-348">numéro passeport Italien</span><span class="sxs-lookup"><span data-stu-id="5aa15-348">numéro passeport italien</span></span>  <br/> <span data-ttu-id="5aa15-349">numéro passeport</span><span class="sxs-lookup"><span data-stu-id="5aa15-349">numéro passeport</span></span>  <br/> |
   
## <a name="latvia"></a><span data-ttu-id="5aa15-350">Letonia</span><span class="sxs-lookup"><span data-stu-id="5aa15-350">Latvia</span></span>

### <a name="format"></a><span data-ttu-id="5aa15-351">Formato</span><span class="sxs-lookup"><span data-stu-id="5aa15-351">Format</span></span>

<span data-ttu-id="5aa15-352">Dos letras o dígitos seguidos de siete dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="5aa15-352">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="5aa15-353">Patrón</span><span class="sxs-lookup"><span data-stu-id="5aa15-353">Pattern</span></span>

<span data-ttu-id="5aa15-354">Dos letras o dígitos seguidos de siete dígitos:</span><span class="sxs-lookup"><span data-stu-id="5aa15-354">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="5aa15-355">Dos dígitos o letras (no distinguen entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="5aa15-355">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="5aa15-356">Siete dígitos</span><span class="sxs-lookup"><span data-stu-id="5aa15-356">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="5aa15-357">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="5aa15-357">Checksum</span></span>

<span data-ttu-id="5aa15-358">No</span><span class="sxs-lookup"><span data-stu-id="5aa15-358">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="5aa15-359">Definición</span><span class="sxs-lookup"><span data-stu-id="5aa15-359">Definition</span></span>

<span data-ttu-id="5aa15-360">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="5aa15-360">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5aa15-361">La expresión `Regex_latvia_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="5aa15-361">The regular expression  `Regex_latvia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5aa15-362">Se encuentra una `Keywords_latvia_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="5aa15-362">A keyword from  `Keywords_latvia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_passport_number" />
          <Match idRef="Keywords_latvia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="5aa15-363">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="5aa15-363">Keywords</span></span>

<span data-ttu-id="5aa15-364">| |</span><span class="sxs-lookup"><span data-stu-id="5aa15-364"></span></span>
|<span data-ttu-id="5aa15-365">**Keywords_latvia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="5aa15-365">**Keywords_latvia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="5aa15-366">passport number</span><span class="sxs-lookup"><span data-stu-id="5aa15-366">passport number</span></span>  <br/> <span data-ttu-id="5aa15-367">número de pasaporte de letón</span><span class="sxs-lookup"><span data-stu-id="5aa15-367">latvian passport number</span></span>  <br/> <span data-ttu-id="5aa15-368">n.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="5aa15-368">passport no</span></span>  <br/> <span data-ttu-id="5aa15-369">Pase numurs</span><span class="sxs-lookup"><span data-stu-id="5aa15-369">pase numurs</span></span>  <br/> |
   
## <a name="lithuania"></a><span data-ttu-id="5aa15-370">Lituania</span><span class="sxs-lookup"><span data-stu-id="5aa15-370">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="5aa15-371">Formato</span><span class="sxs-lookup"><span data-stu-id="5aa15-371">Format</span></span>

<span data-ttu-id="5aa15-372">Ocho dígitos o letras sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="5aa15-372">Eight digits or letters with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="5aa15-373">Patrón</span><span class="sxs-lookup"><span data-stu-id="5aa15-373">Pattern</span></span>

<span data-ttu-id="5aa15-374">Ocho dígitos o letras (no distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="5aa15-374">Eight digits or letters (not case sensitive)</span></span>
  
### <a name="checksum"></a><span data-ttu-id="5aa15-375">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="5aa15-375">Checksum</span></span>

<span data-ttu-id="5aa15-376">No aplicable</span><span class="sxs-lookup"><span data-stu-id="5aa15-376">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="5aa15-377">Definición</span><span class="sxs-lookup"><span data-stu-id="5aa15-377">Definition</span></span>

<span data-ttu-id="5aa15-378">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="5aa15-378">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5aa15-379">La expresión `Regex_lithuania_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="5aa15-379">The regular expression  `Regex_lithuania_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5aa15-380">Se encuentra una `Keywords_lithuania_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="5aa15-380">A keyword from  `Keywords_lithuania_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_passport_number" />
          <Match idRef="Keywords_lithuania_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="5aa15-381">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="5aa15-381">Keywords</span></span>

<span data-ttu-id="5aa15-382">| |</span><span class="sxs-lookup"><span data-stu-id="5aa15-382"></span></span>
|<span data-ttu-id="5aa15-383">**Keywords_lithuania_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="5aa15-383">**Keywords_lithuania_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="5aa15-384">passport number</span><span class="sxs-lookup"><span data-stu-id="5aa15-384">passport number</span></span>  <br/> <span data-ttu-id="5aa15-385">número de pasaporte de lithunian</span><span class="sxs-lookup"><span data-stu-id="5aa15-385">lithunian passport number</span></span>  <br/> <span data-ttu-id="5aa15-386">n.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="5aa15-386">passport no</span></span>  <br/> <span data-ttu-id="5aa15-387">numeración paso</span><span class="sxs-lookup"><span data-stu-id="5aa15-387">paso numeris</span></span>  <br/> |
   
## <a name="luxemburg"></a><span data-ttu-id="5aa15-388">Luxemburgo</span><span class="sxs-lookup"><span data-stu-id="5aa15-388">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="5aa15-389">Formato</span><span class="sxs-lookup"><span data-stu-id="5aa15-389">Format</span></span>

<span data-ttu-id="5aa15-390">Ocho dígitos o letras sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="5aa15-390">Eight digits or letters with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="5aa15-391">Patrón</span><span class="sxs-lookup"><span data-stu-id="5aa15-391">Pattern</span></span>

<span data-ttu-id="5aa15-392">Ocho dígitos o letras (no distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="5aa15-392">Eight digits or letters (not case sensitive)</span></span>
  
### <a name="checksum"></a><span data-ttu-id="5aa15-393">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="5aa15-393">Checksum</span></span>

<span data-ttu-id="5aa15-394">No</span><span class="sxs-lookup"><span data-stu-id="5aa15-394">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="5aa15-395">Definición</span><span class="sxs-lookup"><span data-stu-id="5aa15-395">Definition</span></span>

<span data-ttu-id="5aa15-396">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="5aa15-396">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5aa15-397">La expresión `Regex_nation_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="5aa15-397">The regular expression  `Regex_nation_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5aa15-398">Se encuentra una `Keywords_nation_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="5aa15-398">A keyword from  `Keywords_nation_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_nation_eu_passport_number" />
          <Match idRef="Keywords_nation_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="5aa15-399">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="5aa15-399">Keywords</span></span>

<span data-ttu-id="5aa15-400">| |</span><span class="sxs-lookup"><span data-stu-id="5aa15-400"></span></span>
|<span data-ttu-id="5aa15-401">**Keywords_nation_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="5aa15-401">**Keywords_nation_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="5aa15-402">passport number</span><span class="sxs-lookup"><span data-stu-id="5aa15-402">passport number</span></span>  <br/> <span data-ttu-id="5aa15-403">número de pasaporte de letón</span><span class="sxs-lookup"><span data-stu-id="5aa15-403">latvian passport number</span></span>  <br/> <span data-ttu-id="5aa15-404">n.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="5aa15-404">passport no</span></span>  <br/> <span data-ttu-id="5aa15-405">passnummer</span><span class="sxs-lookup"><span data-stu-id="5aa15-405">passnummer</span></span>  <br/> |
   
## <a name="malta"></a><span data-ttu-id="5aa15-406">Malta</span><span class="sxs-lookup"><span data-stu-id="5aa15-406">Malta</span></span>

### <a name="format"></a><span data-ttu-id="5aa15-407">Formato</span><span class="sxs-lookup"><span data-stu-id="5aa15-407">Format</span></span>

<span data-ttu-id="5aa15-408">Siete dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="5aa15-408">Seven digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="5aa15-409">Patrón</span><span class="sxs-lookup"><span data-stu-id="5aa15-409">Pattern</span></span>

 <span data-ttu-id="5aa15-410">Siete dígitos</span><span class="sxs-lookup"><span data-stu-id="5aa15-410">Seven digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="5aa15-411">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="5aa15-411">Checksum</span></span>

<span data-ttu-id="5aa15-412">No</span><span class="sxs-lookup"><span data-stu-id="5aa15-412">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="5aa15-413">Definición</span><span class="sxs-lookup"><span data-stu-id="5aa15-413">Definition</span></span>

<span data-ttu-id="5aa15-414">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="5aa15-414">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5aa15-415">La expresión `Regex_malta_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="5aa15-415">The regular expression  `Regex_malta_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5aa15-416">Se encuentra una `Keywords_malta_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="5aa15-416">A keyword from  `Keywords_malta_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_passport_number" />
          <Match idRef="Keywords_malta_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="5aa15-417">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="5aa15-417">Keywords</span></span>

<span data-ttu-id="5aa15-418">| |</span><span class="sxs-lookup"><span data-stu-id="5aa15-418"></span></span>
|<span data-ttu-id="5aa15-419">**Keywords_malta_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="5aa15-419">**Keywords_malta_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="5aa15-420">passport number</span><span class="sxs-lookup"><span data-stu-id="5aa15-420">passport number</span></span>  <br/> <span data-ttu-id="5aa15-421">número de pasaporte de Maltés</span><span class="sxs-lookup"><span data-stu-id="5aa15-421">maltese passport number</span></span>  <br/> <span data-ttu-id="5aa15-422">n.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="5aa15-422">passport no</span></span>  <br/> <span data-ttu-id="5aa15-423">numru tal-passaport</span><span class="sxs-lookup"><span data-stu-id="5aa15-423">numru tal-passaport</span></span>  <br/> |
   
## <a name="netherlands"></a><span data-ttu-id="5aa15-424">Países Bajos</span><span class="sxs-lookup"><span data-stu-id="5aa15-424">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="5aa15-425">Formato</span><span class="sxs-lookup"><span data-stu-id="5aa15-425">Format</span></span>

<span data-ttu-id="5aa15-426">Nueve letras o dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="5aa15-426">Nine letters or digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="5aa15-427">Patrón</span><span class="sxs-lookup"><span data-stu-id="5aa15-427">Pattern</span></span>

<span data-ttu-id="5aa15-428">Nueve letras o dígitos</span><span class="sxs-lookup"><span data-stu-id="5aa15-428">Nine letters or digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="5aa15-429">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="5aa15-429">Checksum</span></span>

<span data-ttu-id="5aa15-430">No aplicable</span><span class="sxs-lookup"><span data-stu-id="5aa15-430">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="5aa15-431">Definición</span><span class="sxs-lookup"><span data-stu-id="5aa15-431">Definition</span></span>

<span data-ttu-id="5aa15-432">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="5aa15-432">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5aa15-433">La expresión `Regex_netherlands_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="5aa15-433">The regular expression  `Regex_netherlands_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5aa15-434">Se encuentra una `Keywords_netherlands_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="5aa15-434">A keyword from  `Keywords_netherlands_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_passport_number" />
          <Match idRef="Keywords_netherlands_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="5aa15-435">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="5aa15-435">Keywords</span></span>

<span data-ttu-id="5aa15-436">| |</span><span class="sxs-lookup"><span data-stu-id="5aa15-436"></span></span>
|<span data-ttu-id="5aa15-437">**Keywords_netherlands_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="5aa15-437">**Keywords_netherlands_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="5aa15-438">número de pasaporte holandés</span><span class="sxs-lookup"><span data-stu-id="5aa15-438">dutch passport number</span></span>  <br/> <span data-ttu-id="5aa15-439">passport number</span><span class="sxs-lookup"><span data-stu-id="5aa15-439">passport number</span></span>  <br/> <span data-ttu-id="5aa15-440">número de pasaporte de Holanda</span><span class="sxs-lookup"><span data-stu-id="5aa15-440">netherlands passport number</span></span>  <br/> <span data-ttu-id="5aa15-441">Nederlanden paspoort Nummer</span><span class="sxs-lookup"><span data-stu-id="5aa15-441">nederlanden paspoort nummer</span></span>  <br/> <span data-ttu-id="5aa15-442">paspoort</span><span class="sxs-lookup"><span data-stu-id="5aa15-442">paspoort</span></span>  <br/> <span data-ttu-id="5aa15-443">Nederlanden paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="5aa15-443">nederlanden paspoortnummer</span></span>  <br/> <span data-ttu-id="5aa15-444">paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="5aa15-444">paspoortnummer</span></span>  <br/> |
   
## <a name="poland"></a><span data-ttu-id="5aa15-445">Polonia</span><span class="sxs-lookup"><span data-stu-id="5aa15-445">Poland</span></span>

<span data-ttu-id="5aa15-446">Para obtener más información, consulte la sección "número de pasaporte de Polonia" en [Qué buscan los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="5aa15-446">For details, see the section "Poland Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="portugal"></a><span data-ttu-id="5aa15-447">Portugal</span><span class="sxs-lookup"><span data-stu-id="5aa15-447">Portugal</span></span>

### <a name="format"></a><span data-ttu-id="5aa15-448">Formato</span><span class="sxs-lookup"><span data-stu-id="5aa15-448">Format</span></span>

<span data-ttu-id="5aa15-449">Una letra seguida de seis dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="5aa15-449">One letter followed by six digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="5aa15-450">Patrón</span><span class="sxs-lookup"><span data-stu-id="5aa15-450">Pattern</span></span>

<span data-ttu-id="5aa15-451">Una letra seguida de seis dígitos:</span><span class="sxs-lookup"><span data-stu-id="5aa15-451">One letter followed by six digits:</span></span>
  
- <span data-ttu-id="5aa15-452">Una letra (no distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="5aa15-452">One letter (not case sensitive)</span></span>
    
- <span data-ttu-id="5aa15-453">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="5aa15-453">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="5aa15-454">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="5aa15-454">Checksum</span></span>

<span data-ttu-id="5aa15-455">No</span><span class="sxs-lookup"><span data-stu-id="5aa15-455">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="5aa15-456">Definición</span><span class="sxs-lookup"><span data-stu-id="5aa15-456">Definition</span></span>

<span data-ttu-id="5aa15-457">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="5aa15-457">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5aa15-458">La expresión `Regex_portugal_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="5aa15-458">The regular expression  `Regex_portugal_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5aa15-459">Se encuentra una `Keywords_portugal_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="5aa15-459">A keyword from  `Keywords_portugal_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_passport_number" />
          <Match idRef="Keywords_portugal_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="5aa15-460">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="5aa15-460">Keywords</span></span>

<span data-ttu-id="5aa15-461">| |</span><span class="sxs-lookup"><span data-stu-id="5aa15-461"></span></span>
|<span data-ttu-id="5aa15-462">**Keywords_portugal_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="5aa15-462">**Keywords_portugal_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="5aa15-463">passport number</span><span class="sxs-lookup"><span data-stu-id="5aa15-463">passport number</span></span>  <br/> <span data-ttu-id="5aa15-464">número de pasaporte de Portugués</span><span class="sxs-lookup"><span data-stu-id="5aa15-464">portuguese passport number</span></span>  <br/> <span data-ttu-id="5aa15-465">n.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="5aa15-465">passport no</span></span>  <br/> <span data-ttu-id="5aa15-466">número Passaporte</span><span class="sxs-lookup"><span data-stu-id="5aa15-466">número do passaporte</span></span>  <br/> |
   
## <a name="romania"></a><span data-ttu-id="5aa15-467">Rumania</span><span class="sxs-lookup"><span data-stu-id="5aa15-467">Romania</span></span>

### <a name="format"></a><span data-ttu-id="5aa15-468">Formato</span><span class="sxs-lookup"><span data-stu-id="5aa15-468">Format</span></span>

<span data-ttu-id="5aa15-469">Ocho o nueve dígitos sin espacios y delimitadores</span><span class="sxs-lookup"><span data-stu-id="5aa15-469">Eight or nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="5aa15-470">Patrón</span><span class="sxs-lookup"><span data-stu-id="5aa15-470">Pattern</span></span>

<span data-ttu-id="5aa15-471">Ocho o nueve dígitos</span><span class="sxs-lookup"><span data-stu-id="5aa15-471">Eight or nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="5aa15-472">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="5aa15-472">Checksum</span></span>

<span data-ttu-id="5aa15-473">No</span><span class="sxs-lookup"><span data-stu-id="5aa15-473">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="5aa15-474">Definición</span><span class="sxs-lookup"><span data-stu-id="5aa15-474">Definition</span></span>

<span data-ttu-id="5aa15-475">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="5aa15-475">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5aa15-476">La expresión `Regex_romania_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="5aa15-476">The regular expression  `Regex_romania_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5aa15-477">Se encuentra una `Keywords_romania_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="5aa15-477">A keyword from  `Keywords_romania_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_passport_number" />
          <Match idRef="Keywords_romania_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="5aa15-478">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="5aa15-478">Keywords</span></span>

<span data-ttu-id="5aa15-479">| |</span><span class="sxs-lookup"><span data-stu-id="5aa15-479"></span></span>
|<span data-ttu-id="5aa15-480">**Keywords_romania_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="5aa15-480">**Keywords_romania_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="5aa15-481">passport number</span><span class="sxs-lookup"><span data-stu-id="5aa15-481">passport number</span></span>  <br/> <span data-ttu-id="5aa15-482">número de pasaporte de rumano</span><span class="sxs-lookup"><span data-stu-id="5aa15-482">romanian passport number</span></span>  <br/> <span data-ttu-id="5aa15-483">n.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="5aa15-483">passport no</span></span>  <br/> <span data-ttu-id="5aa15-484">numărul pașaportului</span><span class="sxs-lookup"><span data-stu-id="5aa15-484">numărul pașaportului</span></span>  <br/> |
   
## <a name="slovakia"></a><span data-ttu-id="5aa15-485">Eslovaquia</span><span class="sxs-lookup"><span data-stu-id="5aa15-485">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="5aa15-486">Formato</span><span class="sxs-lookup"><span data-stu-id="5aa15-486">Format</span></span>

<span data-ttu-id="5aa15-487">Un dígito o letra seguido de siete dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="5aa15-487">One digit or letter followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="5aa15-488">Patrón</span><span class="sxs-lookup"><span data-stu-id="5aa15-488">Pattern</span></span>

<span data-ttu-id="5aa15-489">Un dígito o letra (no distingue entre mayúsculas y minúsculas) seguido de siete dígitos</span><span class="sxs-lookup"><span data-stu-id="5aa15-489">One digit or letter (not case sensitive) followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="5aa15-490">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="5aa15-490">Checksum</span></span>

<span data-ttu-id="5aa15-491">No</span><span class="sxs-lookup"><span data-stu-id="5aa15-491">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="5aa15-492">Definición</span><span class="sxs-lookup"><span data-stu-id="5aa15-492">Definition</span></span>

<span data-ttu-id="5aa15-493">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="5aa15-493">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5aa15-494">La expresión `Regex_slovakia_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="5aa15-494">The regular expression  `Regex_slovakia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5aa15-495">Se encuentra una `Keywords_slovakia_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="5aa15-495">A keyword from  `Keywords_slovakia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_passport_number" />
          <Match idRef="Keywords_slovakia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="5aa15-496">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="5aa15-496">Keywords</span></span>

<span data-ttu-id="5aa15-497">| |</span><span class="sxs-lookup"><span data-stu-id="5aa15-497"></span></span>
|<span data-ttu-id="5aa15-498">**Keywords_slovakia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="5aa15-498">**Keywords_slovakia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="5aa15-499">passport number</span><span class="sxs-lookup"><span data-stu-id="5aa15-499">passport number</span></span>  <br/> <span data-ttu-id="5aa15-500">número de pasaporte de eslovaco</span><span class="sxs-lookup"><span data-stu-id="5aa15-500">slovakian passport number</span></span>  <br/> <span data-ttu-id="5aa15-501">n.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="5aa15-501">passport no</span></span>  <br/> <span data-ttu-id="5aa15-502">číslo Pasu</span><span class="sxs-lookup"><span data-stu-id="5aa15-502">číslo pasu</span></span>  <br/> |
   
## <a name="slovenia"></a><span data-ttu-id="5aa15-503">Eslovenia</span><span class="sxs-lookup"><span data-stu-id="5aa15-503">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="5aa15-504">Formato</span><span class="sxs-lookup"><span data-stu-id="5aa15-504">Format</span></span>

<span data-ttu-id="5aa15-505">Dos letras seguidas de siete dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="5aa15-505">Two letters followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="5aa15-506">Patrón</span><span class="sxs-lookup"><span data-stu-id="5aa15-506">Pattern</span></span>

<span data-ttu-id="5aa15-507">Dos letras seguidas de siete dígitos:</span><span class="sxs-lookup"><span data-stu-id="5aa15-507">Two letters followed by seven digits:</span></span>
  
- <span data-ttu-id="5aa15-508">La letra "P"</span><span class="sxs-lookup"><span data-stu-id="5aa15-508">The letter "P"</span></span>
    
- <span data-ttu-id="5aa15-509">Una letra mayúscula</span><span class="sxs-lookup"><span data-stu-id="5aa15-509">One uppercase letter</span></span>
    
- <span data-ttu-id="5aa15-510">Siete dígitos</span><span class="sxs-lookup"><span data-stu-id="5aa15-510">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="5aa15-511">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="5aa15-511">Checksum</span></span>

<span data-ttu-id="5aa15-512">No</span><span class="sxs-lookup"><span data-stu-id="5aa15-512">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="5aa15-513">Definición</span><span class="sxs-lookup"><span data-stu-id="5aa15-513">Definition</span></span>

<span data-ttu-id="5aa15-514">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="5aa15-514">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5aa15-515">La expresión `Regex_slovenia_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="5aa15-515">The regular expression  `Regex_slovenia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5aa15-516">Se encuentra una `Keywords_slovenia_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="5aa15-516">A keyword from  `Keywords_slovenia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_passport_number" />
          <Match idRef="Keywords_slovenia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="5aa15-517">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="5aa15-517">Keywords</span></span>

<span data-ttu-id="5aa15-518">| |</span><span class="sxs-lookup"><span data-stu-id="5aa15-518"></span></span>
|<span data-ttu-id="5aa15-519">**Keywords_slovenia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="5aa15-519">**Keywords_slovenia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="5aa15-520">passport number</span><span class="sxs-lookup"><span data-stu-id="5aa15-520">passport number</span></span>  <br/> <span data-ttu-id="5aa15-521">número de pasaporte de esloveno</span><span class="sxs-lookup"><span data-stu-id="5aa15-521">slovenian passport number</span></span>  <br/> <span data-ttu-id="5aa15-522">n.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="5aa15-522">passport no</span></span>  <br/> <span data-ttu-id="5aa15-523">številka potnega lista</span><span class="sxs-lookup"><span data-stu-id="5aa15-523">številka potnega lista</span></span>  <br/> |
   
## <a name="spain"></a><span data-ttu-id="5aa15-524">España</span><span class="sxs-lookup"><span data-stu-id="5aa15-524">Spain</span></span>

### <a name="format"></a><span data-ttu-id="5aa15-525">Formato</span><span class="sxs-lookup"><span data-stu-id="5aa15-525">Format</span></span>

<span data-ttu-id="5aa15-526">Una combinación de letras y números de ocho o nueve caracteres sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="5aa15-526">An eight- or nine-character combination of letters and numbers with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="5aa15-527">Patrón</span><span class="sxs-lookup"><span data-stu-id="5aa15-527">Pattern</span></span>

<span data-ttu-id="5aa15-528">Una combinación de letras y números de ocho o nueve caracteres:</span><span class="sxs-lookup"><span data-stu-id="5aa15-528">An eight- or nine-character combination of letters and numbers:</span></span>
  
-  <span data-ttu-id="5aa15-529">Dos dígitos o letras</span><span class="sxs-lookup"><span data-stu-id="5aa15-529">Two digits or letters</span></span> 
    
- <span data-ttu-id="5aa15-530">Un dígito o letra (opcional)</span><span class="sxs-lookup"><span data-stu-id="5aa15-530">One digit or letter (optional)</span></span>
    
- <span data-ttu-id="5aa15-531">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="5aa15-531">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="5aa15-532">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="5aa15-532">Checksum</span></span>

<span data-ttu-id="5aa15-533">No aplicable</span><span class="sxs-lookup"><span data-stu-id="5aa15-533">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="5aa15-534">Definición</span><span class="sxs-lookup"><span data-stu-id="5aa15-534">Definition</span></span>

<span data-ttu-id="5aa15-535">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="5aa15-535">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5aa15-536">La expresión `Regex_spain_eu_passport_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="5aa15-536">The regular expression  `Regex_spain_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5aa15-537">Se encuentra una `Keywords_spain_eu_passport_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="5aa15-537">A keyword from  `Keywords_spain_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_spain_eu_passport_number" />
          <Match idRef="Keywords_spain_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="5aa15-538">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="5aa15-538">Keywords</span></span>

<span data-ttu-id="5aa15-539">| |</span><span class="sxs-lookup"><span data-stu-id="5aa15-539"></span></span>
|<span data-ttu-id="5aa15-540">**Keywords_spain_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="5aa15-540">**Keywords_spain_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="5aa15-541">usuarios</span><span class="sxs-lookup"><span data-stu-id="5aa15-541">passport</span></span>  <br/> <span data-ttu-id="5aa15-542">pasaporte de España</span><span class="sxs-lookup"><span data-stu-id="5aa15-542">spain passport</span></span>  <br/> <span data-ttu-id="5aa15-543">libro de Passport</span><span class="sxs-lookup"><span data-stu-id="5aa15-543">passport book</span></span>  <br/> <span data-ttu-id="5aa15-544">passport number</span><span class="sxs-lookup"><span data-stu-id="5aa15-544">passport number</span></span>  <br/> <span data-ttu-id="5aa15-545">n.º de pasaporte</span><span class="sxs-lookup"><span data-stu-id="5aa15-545">passport no</span></span>  <br/> <span data-ttu-id="5aa15-546">libreta pasaporte</span><span class="sxs-lookup"><span data-stu-id="5aa15-546">libreta pasaporte</span></span>  <br/> <span data-ttu-id="5aa15-547">número pasaporte</span><span class="sxs-lookup"><span data-stu-id="5aa15-547">número pasaporte</span></span>  <br/> <span data-ttu-id="5aa15-548">España pasaporte</span><span class="sxs-lookup"><span data-stu-id="5aa15-548">españa pasaporte</span></span>  <br/> <span data-ttu-id="5aa15-549">pasaporte</span><span class="sxs-lookup"><span data-stu-id="5aa15-549">pasaporte</span></span>  <br/> |
   
## <a name="sweden"></a><span data-ttu-id="5aa15-550">Suecia</span><span class="sxs-lookup"><span data-stu-id="5aa15-550">Sweden</span></span>

<span data-ttu-id="5aa15-551">Para obtener más información, consulte la sección "número de pasaporte de Suecia" en [Qué buscan los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="5aa15-551">For details, see the section "Sweden Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="uk"></a><span data-ttu-id="5aa15-552">LIBRA</span><span class="sxs-lookup"><span data-stu-id="5aa15-552">UK</span></span>

<span data-ttu-id="5aa15-553">Para obtener más información, consulte la sección "Estados Unidos/Reino Unido</span><span class="sxs-lookup"><span data-stu-id="5aa15-553">For details, see the section "U.S. / U.K.</span></span> <span data-ttu-id="5aa15-554">Número de pasaporte "en [lo que buscan los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="5aa15-554">Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="5aa15-555">Vea también</span><span class="sxs-lookup"><span data-stu-id="5aa15-555">See also</span></span>

[<span data-ttu-id="5aa15-556">Qué buscan los tipos de información confidencial</span><span class="sxs-lookup"><span data-stu-id="5aa15-556">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

