---
title: Número de permiso de conducción de la UE
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/17/2018
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
description: En este tema se muestra qué busca una directiva de prevención de pérdida de datos (DLP) cuando detecta el tipo de información confidencial del número de licencia de conductor de la UE. Este tipo de información confidencial define distintos patrones, palabras clave y otras pruebas para cada país.
ms.openlocfilehash: f1a95ecbaf6b6d1ac189290dd6d076cfd91ab30f
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/17/2019
ms.locfileid: "34152982"
---
# <a name="eu-drivers-license-number"></a><span data-ttu-id="0716c-104">Número de permiso de conducción de la UE</span><span class="sxs-lookup"><span data-stu-id="0716c-104">EU Driver's License Number</span></span>

<span data-ttu-id="0716c-105">En este tema se muestra qué busca una directiva de prevención de pérdida de datos (DLP) cuando detecta el tipo de información confidencial del número de licencia de conductor de la UE.</span><span class="sxs-lookup"><span data-stu-id="0716c-105">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Driver's License Number sensitive information type.</span></span> <span data-ttu-id="0716c-106">Este tipo de información confidencial define distintos patrones, palabras clave y otras pruebas para cada país.</span><span class="sxs-lookup"><span data-stu-id="0716c-106">This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="0716c-107">Austria</span><span class="sxs-lookup"><span data-stu-id="0716c-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="0716c-108">Formato</span><span class="sxs-lookup"><span data-stu-id="0716c-108">Format</span></span>

<span data-ttu-id="0716c-109">Ocho dígitos sin espacios y delimitadores</span><span class="sxs-lookup"><span data-stu-id="0716c-109">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="0716c-110">Patrón</span><span class="sxs-lookup"><span data-stu-id="0716c-110">Pattern</span></span>

<span data-ttu-id="0716c-111">Ocho dígitos</span><span class="sxs-lookup"><span data-stu-id="0716c-111">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="0716c-112">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="0716c-112">Checksum</span></span>

<span data-ttu-id="0716c-113">No</span><span class="sxs-lookup"><span data-stu-id="0716c-113">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="0716c-114">Definición</span><span class="sxs-lookup"><span data-stu-id="0716c-114">Definition</span></span>

<span data-ttu-id="0716c-115">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="0716c-115">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="0716c-116">La expresión `Regex_austria_eu_driver's_license_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="0716c-116">The regular expression  `Regex_austria_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="0716c-117">Se encuentra una `Keywords_austria_eu_driver's_license_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="0716c-117">A keyword from  `Keywords_austria_eu_driver's_license_number` is found.</span></span> 
    
```
<!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_driver's_license_number" />
          <Match idRef="Keywords_austria_eu_driver's_license_number" />
        </Pattern>
    </Entity>

```

### <a name="keywords"></a><span data-ttu-id="0716c-118">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="0716c-118">Keywords</span></span>

<span data-ttu-id="0716c-119">| |</span><span class="sxs-lookup"><span data-stu-id="0716c-119"></span></span>
|<span data-ttu-id="0716c-120">**Keywords_austria_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="0716c-120">**Keywords_austria_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="0716c-121">listas</span><span class="sxs-lookup"><span data-stu-id="0716c-121">dl#</span></span>  <br/> <span data-ttu-id="0716c-122">driver license</span><span class="sxs-lookup"><span data-stu-id="0716c-122">driver license</span></span>  <br/> <span data-ttu-id="0716c-123">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="0716c-123">driver license number</span></span>  <br/> <span data-ttu-id="0716c-124">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="0716c-124">driver licence</span></span>  <br/> <span data-ttu-id="0716c-125">Lic de drivers.</span><span class="sxs-lookup"><span data-stu-id="0716c-125">drivers lic.</span></span>  <br/> <span data-ttu-id="0716c-126">drivers license</span><span class="sxs-lookup"><span data-stu-id="0716c-126">drivers license</span></span>  <br/> <span data-ttu-id="0716c-127">driver's licence</span><span class="sxs-lookup"><span data-stu-id="0716c-127">driver's licence</span></span>  <br/> <span data-ttu-id="0716c-128">driver's license</span><span class="sxs-lookup"><span data-stu-id="0716c-128">driver's license</span></span>  <br/> <span data-ttu-id="0716c-129">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="0716c-129">driver's license number</span></span>  <br/> <span data-ttu-id="0716c-130">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="0716c-130">driver's licence number</span></span>  <br/>  <span data-ttu-id="0716c-131">número de licencia de conducir</span><span class="sxs-lookup"><span data-stu-id="0716c-131">driving license number</span></span>  <br/> <span data-ttu-id="0716c-132">dlno#</span><span class="sxs-lookup"><span data-stu-id="0716c-132">dlno#</span></span>  <br/> <span data-ttu-id="0716c-133">fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="0716c-133">fuhrerschein</span></span>  <br/> <span data-ttu-id="0716c-134">fuhrerschein republik osterreich</span><span class="sxs-lookup"><span data-stu-id="0716c-134">fuhrerschein republik osterreich</span></span>  <br/> |
   
## <a name="belgium"></a><span data-ttu-id="0716c-135">Bélgica</span><span class="sxs-lookup"><span data-stu-id="0716c-135">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="0716c-136">Formato</span><span class="sxs-lookup"><span data-stu-id="0716c-136">Format</span></span>

<span data-ttu-id="0716c-137">10 dígitos sin espacios y delimitadores</span><span class="sxs-lookup"><span data-stu-id="0716c-137">10 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="0716c-138">Patrón</span><span class="sxs-lookup"><span data-stu-id="0716c-138">Pattern</span></span>

<span data-ttu-id="0716c-139">10 dígitos</span><span class="sxs-lookup"><span data-stu-id="0716c-139">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="0716c-140">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="0716c-140">Checksum</span></span>

<span data-ttu-id="0716c-141">No</span><span class="sxs-lookup"><span data-stu-id="0716c-141">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="0716c-142">Definición</span><span class="sxs-lookup"><span data-stu-id="0716c-142">Definition</span></span>

<span data-ttu-id="0716c-143">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="0716c-143">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="0716c-144">La expresión `Regex_belgium_eu_driver's_license_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="0716c-144">The regular expression  `Regex_belgium_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="0716c-145">Se encuentra una `Keywords_belgium_eu_driver's_license_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="0716c-145">A keyword from  `Keywords_belgium_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_driver's_license_number" />
          <Match idRef="Keywords_belgium_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="0716c-146">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="0716c-146">Keywords</span></span>

<span data-ttu-id="0716c-147">| |</span><span class="sxs-lookup"><span data-stu-id="0716c-147"></span></span>
|<span data-ttu-id="0716c-148">**Keywords__belgium_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="0716c-148">**Keywords__belgium_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="0716c-149">listas</span><span class="sxs-lookup"><span data-stu-id="0716c-149">dl#</span></span>  <br/> <span data-ttu-id="0716c-150">driver license</span><span class="sxs-lookup"><span data-stu-id="0716c-150">driver license</span></span>  <br/> <span data-ttu-id="0716c-151">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="0716c-151">driver license number</span></span>  <br/> <span data-ttu-id="0716c-152">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="0716c-152">driver licence</span></span>  <br/> <span data-ttu-id="0716c-153">Lic de drivers.</span><span class="sxs-lookup"><span data-stu-id="0716c-153">drivers lic.</span></span>  <br/> <span data-ttu-id="0716c-154">drivers license</span><span class="sxs-lookup"><span data-stu-id="0716c-154">drivers license</span></span>  <br/> <span data-ttu-id="0716c-155">drivers licence</span><span class="sxs-lookup"><span data-stu-id="0716c-155">drivers licence</span></span>  <br/> <span data-ttu-id="0716c-156">driver's license</span><span class="sxs-lookup"><span data-stu-id="0716c-156">driver's license</span></span>  <br/> <span data-ttu-id="0716c-157">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="0716c-157">driver's license number</span></span>  <br/> <span data-ttu-id="0716c-158">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="0716c-158">driver's licence number</span></span>  <br/> <span data-ttu-id="0716c-159">dlno#</span><span class="sxs-lookup"><span data-stu-id="0716c-159">dlno#</span></span>  <br/> <span data-ttu-id="0716c-160">rijbewijs</span><span class="sxs-lookup"><span data-stu-id="0716c-160">rijbewijs</span></span>  <br/> <span data-ttu-id="0716c-161">rijbewijsnummer</span><span class="sxs-lookup"><span data-stu-id="0716c-161">rijbewijsnummer</span></span>  <br/> <span data-ttu-id="0716c-162">führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="0716c-162">führerscheinnummer</span></span>  <br/> <span data-ttu-id="0716c-163">fuhrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="0716c-163">fuhrerscheinnummer</span></span>  <br/> <span data-ttu-id="0716c-164">fuehrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="0716c-164">fuehrerscheinnummer</span></span>  <br/> <span data-ttu-id="0716c-165">Führerschein-NR</span><span class="sxs-lookup"><span data-stu-id="0716c-165">führerschein- nr</span></span>  <br/> <span data-ttu-id="0716c-166">fuehrerschein-NR</span><span class="sxs-lookup"><span data-stu-id="0716c-166">fuehrerschein- Nr</span></span>  <br/> <span data-ttu-id="0716c-167">fuehrerschein-NR</span><span class="sxs-lookup"><span data-stu-id="0716c-167">fuehrerschein- nr</span></span>  <br/> |
   
## <a name="bulgaria"></a><span data-ttu-id="0716c-168">Bulgaria</span><span class="sxs-lookup"><span data-stu-id="0716c-168">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="0716c-169">Formato</span><span class="sxs-lookup"><span data-stu-id="0716c-169">Format</span></span>

<span data-ttu-id="0716c-170">Nueve dígitos sin espacios y delimitadores</span><span class="sxs-lookup"><span data-stu-id="0716c-170">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="0716c-171">Patrón</span><span class="sxs-lookup"><span data-stu-id="0716c-171">Pattern</span></span>

<span data-ttu-id="0716c-172">Nueve dígitos</span><span class="sxs-lookup"><span data-stu-id="0716c-172">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="0716c-173">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="0716c-173">Checksum</span></span>

<span data-ttu-id="0716c-174">No</span><span class="sxs-lookup"><span data-stu-id="0716c-174">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="0716c-175">Definición</span><span class="sxs-lookup"><span data-stu-id="0716c-175">Definition</span></span>

<span data-ttu-id="0716c-176">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="0716c-176">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="0716c-177">La expresión `Regex_bulgaria_eu_driver's_license_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="0716c-177">The regular expression  `Regex_bulgaria_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="0716c-178">Se encuentra una `Keywords_bulgaria_eu_driver's_license_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="0716c-178">A keyword from  `Keywords_bulgaria_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
             <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_driver's_license_number" />
          <Match idRef="Keywords_bulgaria_eu_driver's_license_number" />
        </Pattern> 
</Entity>    

```

### <a name="keywords"></a><span data-ttu-id="0716c-179">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="0716c-179">Keywords</span></span>

<span data-ttu-id="0716c-180">| |</span><span class="sxs-lookup"><span data-stu-id="0716c-180"></span></span>
|<span data-ttu-id="0716c-181">**Keywords_bulgaria_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="0716c-181">**Keywords_bulgaria_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="0716c-182">listas</span><span class="sxs-lookup"><span data-stu-id="0716c-182">dl#</span></span>  <br/> <span data-ttu-id="0716c-183">driver license</span><span class="sxs-lookup"><span data-stu-id="0716c-183">driver license</span></span>  <br/> <span data-ttu-id="0716c-184">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="0716c-184">driver license number</span></span>  <br/> <span data-ttu-id="0716c-185">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="0716c-185">driver licence</span></span>  <br/> <span data-ttu-id="0716c-186">Lic de drivers.</span><span class="sxs-lookup"><span data-stu-id="0716c-186">drivers lic.</span></span>  <br/> <span data-ttu-id="0716c-187">drivers license</span><span class="sxs-lookup"><span data-stu-id="0716c-187">drivers license</span></span>  <br/> <span data-ttu-id="0716c-188">drivers licence</span><span class="sxs-lookup"><span data-stu-id="0716c-188">drivers licence</span></span>  <br/> <span data-ttu-id="0716c-189">driver's license</span><span class="sxs-lookup"><span data-stu-id="0716c-189">driver's license</span></span>  <br/> <span data-ttu-id="0716c-190">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="0716c-190">driver's license number</span></span>  <br/> <span data-ttu-id="0716c-191">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="0716c-191">driver's licence number</span></span>  <br/> <span data-ttu-id="0716c-192">número de licencia de conducir</span><span class="sxs-lookup"><span data-stu-id="0716c-192">driving license number</span></span>  <br/> <span data-ttu-id="0716c-193">dlno#</span><span class="sxs-lookup"><span data-stu-id="0716c-193">dlno#</span></span>  <br/> <span data-ttu-id="0716c-194">свидетелство за управление на мпс</span><span class="sxs-lookup"><span data-stu-id="0716c-194">свидетелство за управление на мпс</span></span>  <br/> <span data-ttu-id="0716c-195">свидетелство за управление на моторно превозно средство</span><span class="sxs-lookup"><span data-stu-id="0716c-195">свидетелство за управление на моторно превозно средство</span></span>  <br/> <span data-ttu-id="0716c-196">сумпс</span><span class="sxs-lookup"><span data-stu-id="0716c-196">сумпс</span></span>  <br/> <span data-ttu-id="0716c-197">шофьорска книжка</span><span class="sxs-lookup"><span data-stu-id="0716c-197">шофьорска книжка</span></span>  <br/> |
   
## <a name="croatia"></a><span data-ttu-id="0716c-198">Croacia</span><span class="sxs-lookup"><span data-stu-id="0716c-198">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="0716c-199">Formato</span><span class="sxs-lookup"><span data-stu-id="0716c-199">Format</span></span>

<span data-ttu-id="0716c-200">Ocho dígitos sin espacios y delimitadores</span><span class="sxs-lookup"><span data-stu-id="0716c-200">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="0716c-201">Patrón</span><span class="sxs-lookup"><span data-stu-id="0716c-201">Pattern</span></span>

<span data-ttu-id="0716c-202">Ocho dígitos</span><span class="sxs-lookup"><span data-stu-id="0716c-202">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="0716c-203">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="0716c-203">Checksum</span></span>

<span data-ttu-id="0716c-204">No</span><span class="sxs-lookup"><span data-stu-id="0716c-204">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="0716c-205">Definición</span><span class="sxs-lookup"><span data-stu-id="0716c-205">Definition</span></span>

<span data-ttu-id="0716c-206">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="0716c-206">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="0716c-207">La expresión `Regex_croatia_eu_driver's_license_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="0716c-207">The regular expression  `Regex_croatia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="0716c-208">Se encuentra una `Keywords_croatia_eu_driver's_license_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="0716c-208">A keyword from  `Keywords_croatia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_driver's_license_number" />
          <Match idRef="Keywords_croatia_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="0716c-209">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="0716c-209">Keywords</span></span>

<span data-ttu-id="0716c-210">| |</span><span class="sxs-lookup"><span data-stu-id="0716c-210"></span></span>
|<span data-ttu-id="0716c-211">**Keywords_croatia_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="0716c-211">**Keywords_croatia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="0716c-212">listas</span><span class="sxs-lookup"><span data-stu-id="0716c-212">dl#</span></span>  <br/> <span data-ttu-id="0716c-213">driver license</span><span class="sxs-lookup"><span data-stu-id="0716c-213">driver license</span></span>  <br/> <span data-ttu-id="0716c-214">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="0716c-214">driver license number</span></span>  <br/> <span data-ttu-id="0716c-215">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="0716c-215">driver licence</span></span>  <br/> <span data-ttu-id="0716c-216">Lic de drivers.</span><span class="sxs-lookup"><span data-stu-id="0716c-216">drivers lic.</span></span>  <br/> <span data-ttu-id="0716c-217">drivers license</span><span class="sxs-lookup"><span data-stu-id="0716c-217">drivers license</span></span>  <br/> <span data-ttu-id="0716c-218">drivers licence</span><span class="sxs-lookup"><span data-stu-id="0716c-218">drivers licence</span></span>  <br/> <span data-ttu-id="0716c-219">driver's license</span><span class="sxs-lookup"><span data-stu-id="0716c-219">driver's license</span></span>  <br/> <span data-ttu-id="0716c-220">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="0716c-220">driver's license number</span></span>  <br/> <span data-ttu-id="0716c-221">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="0716c-221">driver's licence number</span></span>  <br/> <span data-ttu-id="0716c-222">número de licencia de conducir</span><span class="sxs-lookup"><span data-stu-id="0716c-222">driving license number</span></span>  <br/> <span data-ttu-id="0716c-223">dlno#</span><span class="sxs-lookup"><span data-stu-id="0716c-223">dlno#</span></span>  <br/> <span data-ttu-id="0716c-224">vozačka dozvola</span><span class="sxs-lookup"><span data-stu-id="0716c-224">vozačka dozvola</span></span>  <br/> |
   
## <a name="cyprus"></a><span data-ttu-id="0716c-225">Chipre</span><span class="sxs-lookup"><span data-stu-id="0716c-225">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="0716c-226">Formato</span><span class="sxs-lookup"><span data-stu-id="0716c-226">Format</span></span>

<span data-ttu-id="0716c-227">12 dígitos sin espacios y delimitadores</span><span class="sxs-lookup"><span data-stu-id="0716c-227">12 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="0716c-228">Patrón</span><span class="sxs-lookup"><span data-stu-id="0716c-228">Pattern</span></span>

<span data-ttu-id="0716c-229">12 dígitos</span><span class="sxs-lookup"><span data-stu-id="0716c-229">12 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="0716c-230">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="0716c-230">Checksum</span></span>

<span data-ttu-id="0716c-231">No</span><span class="sxs-lookup"><span data-stu-id="0716c-231">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="0716c-232">Definición</span><span class="sxs-lookup"><span data-stu-id="0716c-232">Definition</span></span>

<span data-ttu-id="0716c-233">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="0716c-233">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="0716c-234">La expresión `Regex_cyprus_eu_driver's_license_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="0716c-234">The regular expression  `Regex_cyprus_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="0716c-235">Se encuentra una `Keywords_cyprus_eu_driver's_license_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="0716c-235">A keyword from  `Keywords_cyprus_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_driver's_license_number" />
          <Match idRef="Keywords_cyprus_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="0716c-236">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="0716c-236">Keywords</span></span>

<span data-ttu-id="0716c-237">| |</span><span class="sxs-lookup"><span data-stu-id="0716c-237"></span></span>
|<span data-ttu-id="0716c-238">**Keywords_cyprus_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="0716c-238">**Keywords_cyprus_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="0716c-239">listas</span><span class="sxs-lookup"><span data-stu-id="0716c-239">dl#</span></span>  <br/> <span data-ttu-id="0716c-240">driver license</span><span class="sxs-lookup"><span data-stu-id="0716c-240">driver license</span></span>  <br/> <span data-ttu-id="0716c-241">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="0716c-241">driver license number</span></span>  <br/> <span data-ttu-id="0716c-242">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="0716c-242">driver licence</span></span>  <br/> <span data-ttu-id="0716c-243">Lic de drivers.</span><span class="sxs-lookup"><span data-stu-id="0716c-243">drivers lic.</span></span>  <br/> <span data-ttu-id="0716c-244">drivers license</span><span class="sxs-lookup"><span data-stu-id="0716c-244">drivers license</span></span>  <br/> <span data-ttu-id="0716c-245">drivers licence</span><span class="sxs-lookup"><span data-stu-id="0716c-245">drivers licence</span></span>  <br/> <span data-ttu-id="0716c-246">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="0716c-246">driver's license number</span></span>  <br/> <span data-ttu-id="0716c-247">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="0716c-247">driver's licence number</span></span>  <br/> <span data-ttu-id="0716c-248">número de licencia de conducir</span><span class="sxs-lookup"><span data-stu-id="0716c-248">driving license number</span></span>  <br/> <span data-ttu-id="0716c-249">dlno#</span><span class="sxs-lookup"><span data-stu-id="0716c-249">dlno#</span></span>  <br/> <span data-ttu-id="0716c-250">άδεια οδήγησης</span><span class="sxs-lookup"><span data-stu-id="0716c-250">άδεια οδήγησης</span></span>  <br/> |
   
## <a name="czech-republic"></a><span data-ttu-id="0716c-251">Chequia</span><span class="sxs-lookup"><span data-stu-id="0716c-251">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="0716c-252">Formato</span><span class="sxs-lookup"><span data-stu-id="0716c-252">Format</span></span>

<span data-ttu-id="0716c-253">Dos letras seguidas de seis dígitos</span><span class="sxs-lookup"><span data-stu-id="0716c-253">Two letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="0716c-254">Patrón</span><span class="sxs-lookup"><span data-stu-id="0716c-254">Pattern</span></span>

<span data-ttu-id="0716c-255">Ocho letras y dígitos:</span><span class="sxs-lookup"><span data-stu-id="0716c-255">Eight letters and digits:</span></span>
  
- <span data-ttu-id="0716c-256">Dos letras (sin distinción entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="0716c-256">Two letters (not case-sensitive)</span></span>
    
- <span data-ttu-id="0716c-257">Un espacio (opcional) </span><span class="sxs-lookup"><span data-stu-id="0716c-257">A space (optional)</span></span>
    
- <span data-ttu-id="0716c-258">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="0716c-258">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="0716c-259">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="0716c-259">Checksum</span></span>

<span data-ttu-id="0716c-260">No</span><span class="sxs-lookup"><span data-stu-id="0716c-260">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="0716c-261">Definición</span><span class="sxs-lookup"><span data-stu-id="0716c-261">Definition</span></span>

<span data-ttu-id="0716c-262">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="0716c-262">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="0716c-263">La expresión `Regex_czech_republic_eu_driver's_license_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="0716c-263">The regular expression  `Regex_czech_republic_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="0716c-264">Se encuentra una `Keywords_czech_republic_eu_driver's_license_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="0716c-264">A keyword from  `Keywords_czech_republic_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_driver's_license_number" />
          <Match idRef="Keywords_czech_republic_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="0716c-265">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="0716c-265">Keywords</span></span>

<span data-ttu-id="0716c-266">| |</span><span class="sxs-lookup"><span data-stu-id="0716c-266"></span></span>
|<span data-ttu-id="0716c-267">**Keywords_czech_republic_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="0716c-267">**Keywords_czech_republic_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="0716c-268">listas</span><span class="sxs-lookup"><span data-stu-id="0716c-268">dl#</span></span>  <br/> <span data-ttu-id="0716c-269">driver license</span><span class="sxs-lookup"><span data-stu-id="0716c-269">driver license</span></span>  <br/> <span data-ttu-id="0716c-270">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="0716c-270">driver license number</span></span>  <br/> <span data-ttu-id="0716c-271">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="0716c-271">driver licence</span></span>  <br/> <span data-ttu-id="0716c-272">Lic de drivers.</span><span class="sxs-lookup"><span data-stu-id="0716c-272">drivers lic.</span></span>  <br/> <span data-ttu-id="0716c-273">drivers license</span><span class="sxs-lookup"><span data-stu-id="0716c-273">drivers license</span></span>  <br/> <span data-ttu-id="0716c-274">drivers licence</span><span class="sxs-lookup"><span data-stu-id="0716c-274">drivers licence</span></span>  <br/> <span data-ttu-id="0716c-275">driver's license</span><span class="sxs-lookup"><span data-stu-id="0716c-275">driver's license</span></span>  <br/> <span data-ttu-id="0716c-276">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="0716c-276">driver's license number</span></span>  <br/> <span data-ttu-id="0716c-277">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="0716c-277">driver's license number</span></span>  <br/> <span data-ttu-id="0716c-278">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="0716c-278">driver's licence number</span></span>  <br/> <span data-ttu-id="0716c-279">número de licencia de conducir</span><span class="sxs-lookup"><span data-stu-id="0716c-279">driving license number</span></span>  <br/> <span data-ttu-id="0716c-280">dlno#</span><span class="sxs-lookup"><span data-stu-id="0716c-280">dlno#</span></span>  <br/> <span data-ttu-id="0716c-281">řidičský prúkaz</span><span class="sxs-lookup"><span data-stu-id="0716c-281">řidičský prúkaz</span></span>  <br/> |
   
## <a name="denmark"></a><span data-ttu-id="0716c-282">Dinamarca</span><span class="sxs-lookup"><span data-stu-id="0716c-282">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="0716c-283">Formato</span><span class="sxs-lookup"><span data-stu-id="0716c-283">Format</span></span>

<span data-ttu-id="0716c-284">Ocho dígitos sin espacios y delimitadores</span><span class="sxs-lookup"><span data-stu-id="0716c-284">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="0716c-285">Patrón</span><span class="sxs-lookup"><span data-stu-id="0716c-285">Pattern</span></span>

<span data-ttu-id="0716c-286">Ocho dígitos</span><span class="sxs-lookup"><span data-stu-id="0716c-286">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="0716c-287">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="0716c-287">Checksum</span></span>

<span data-ttu-id="0716c-288">Sí</span><span class="sxs-lookup"><span data-stu-id="0716c-288">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="0716c-289">Definición</span><span class="sxs-lookup"><span data-stu-id="0716c-289">Definition</span></span>

<span data-ttu-id="0716c-290">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="0716c-290">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="0716c-291">La expresión `Regex_denmark_eu_driver's_license_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="0716c-291">The regular expression  `Regex_denmark_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="0716c-292">Se encuentra una `Keywords_denmark_eu_driver's_license_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="0716c-292">A keyword from  `Keywords_denmark_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_driver's_license_number" />
          <Match idRef="Keywords_denmark_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="0716c-293">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="0716c-293">Keywords</span></span>

<span data-ttu-id="0716c-294">| |</span><span class="sxs-lookup"><span data-stu-id="0716c-294"></span></span>
|<span data-ttu-id="0716c-295">**Keywords_denmark_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="0716c-295">**Keywords_denmark_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="0716c-296">listas</span><span class="sxs-lookup"><span data-stu-id="0716c-296">dl#</span></span>  <br/> <span data-ttu-id="0716c-297">driver license</span><span class="sxs-lookup"><span data-stu-id="0716c-297">driver license</span></span>  <br/> <span data-ttu-id="0716c-298">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="0716c-298">driver license number</span></span>  <br/> <span data-ttu-id="0716c-299">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="0716c-299">driver licence</span></span>  <br/> <span data-ttu-id="0716c-300">Lic de drivers.</span><span class="sxs-lookup"><span data-stu-id="0716c-300">drivers lic.</span></span>  <br/> <span data-ttu-id="0716c-301">drivers license</span><span class="sxs-lookup"><span data-stu-id="0716c-301">drivers license</span></span>  <br/> <span data-ttu-id="0716c-302">drivers licence</span><span class="sxs-lookup"><span data-stu-id="0716c-302">drivers licence</span></span>  <br/> <span data-ttu-id="0716c-303">driver's license</span><span class="sxs-lookup"><span data-stu-id="0716c-303">driver's license</span></span>  <br/> <span data-ttu-id="0716c-304">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="0716c-304">driver's license number</span></span>  <br/> <span data-ttu-id="0716c-305">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="0716c-305">driver's licence number</span></span>  <br/> <span data-ttu-id="0716c-306">número de licencia de conducir</span><span class="sxs-lookup"><span data-stu-id="0716c-306">driving license number</span></span>  <br/> <span data-ttu-id="0716c-307">dlno#</span><span class="sxs-lookup"><span data-stu-id="0716c-307">dlno#</span></span>  <br/> <span data-ttu-id="0716c-308">kørekort</span><span class="sxs-lookup"><span data-stu-id="0716c-308">kørekort</span></span>  <br/> <span data-ttu-id="0716c-309">kørekortnummer</span><span class="sxs-lookup"><span data-stu-id="0716c-309">kørekortnummer</span></span>  <br/> |
   
## <a name="estonia"></a><span data-ttu-id="0716c-310">Estonia</span><span class="sxs-lookup"><span data-stu-id="0716c-310">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="0716c-311">Formato</span><span class="sxs-lookup"><span data-stu-id="0716c-311">Format</span></span>

<span data-ttu-id="0716c-312">Dos letras seguidas de seis dígitos</span><span class="sxs-lookup"><span data-stu-id="0716c-312">Two letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="0716c-313">Patrón</span><span class="sxs-lookup"><span data-stu-id="0716c-313">Pattern</span></span>

<span data-ttu-id="0716c-314">Dos letras y seis dígitos:</span><span class="sxs-lookup"><span data-stu-id="0716c-314">Two letters and six digits:</span></span>
  
-  <span data-ttu-id="0716c-315">Las letras "ET" (sin distinción entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="0716c-315">The letters "ET" (not case-sensitive)</span></span> 
    
- <span data-ttu-id="0716c-316">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="0716c-316">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="0716c-317">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="0716c-317">Checksum</span></span>

<span data-ttu-id="0716c-318">No</span><span class="sxs-lookup"><span data-stu-id="0716c-318">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="0716c-319">Definición</span><span class="sxs-lookup"><span data-stu-id="0716c-319">Definition</span></span>

<span data-ttu-id="0716c-320">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="0716c-320">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="0716c-321">La expresión `Regex_estonia_eu_driver's_license_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="0716c-321">The regular expression  `Regex_estonia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="0716c-322">Se encuentra una `Keywords_estonia_eu_driver's_license_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="0716c-322">A keyword from  `Keywords_estonia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_driver's_license_number" />
          <Match idRef="Keywords_estonia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="0716c-323">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="0716c-323">Keywords</span></span>

<span data-ttu-id="0716c-324">| |</span><span class="sxs-lookup"><span data-stu-id="0716c-324"></span></span>
|<span data-ttu-id="0716c-325">**Keywords_estonia_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="0716c-325">**Keywords_estonia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="0716c-326">listas</span><span class="sxs-lookup"><span data-stu-id="0716c-326">dl#</span></span>  <br/> <span data-ttu-id="0716c-327">driver license</span><span class="sxs-lookup"><span data-stu-id="0716c-327">driver license</span></span>  <br/> <span data-ttu-id="0716c-328">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="0716c-328">driver license number</span></span>  <br/> <span data-ttu-id="0716c-329">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="0716c-329">driver license number</span></span>  <br/> <span data-ttu-id="0716c-330">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="0716c-330">driver licence</span></span>  <br/> <span data-ttu-id="0716c-331">Lic de drivers.</span><span class="sxs-lookup"><span data-stu-id="0716c-331">drivers lic.</span></span>  <br/> <span data-ttu-id="0716c-332">drivers license</span><span class="sxs-lookup"><span data-stu-id="0716c-332">drivers license</span></span>  <br/> <span data-ttu-id="0716c-333">drivers licence</span><span class="sxs-lookup"><span data-stu-id="0716c-333">drivers licence</span></span>  <br/> <span data-ttu-id="0716c-334">driver's license</span><span class="sxs-lookup"><span data-stu-id="0716c-334">driver's license</span></span>  <br/> <span data-ttu-id="0716c-335">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="0716c-335">driver's license number</span></span>  <br/> <span data-ttu-id="0716c-336">número de licencia de conducir</span><span class="sxs-lookup"><span data-stu-id="0716c-336">driving license number</span></span>  <br/> <span data-ttu-id="0716c-337">dlno#</span><span class="sxs-lookup"><span data-stu-id="0716c-337">dlno#</span></span>  <br/> <span data-ttu-id="0716c-338">permis de conduire</span><span class="sxs-lookup"><span data-stu-id="0716c-338">permis de conduire</span></span>  <br/> |
   
## <a name="finland"></a><span data-ttu-id="0716c-339">Finlandia</span><span class="sxs-lookup"><span data-stu-id="0716c-339">Finland</span></span>

### <a name="format"></a><span data-ttu-id="0716c-340">Formato</span><span class="sxs-lookup"><span data-stu-id="0716c-340">Format</span></span>

<span data-ttu-id="0716c-341">10 dígitos que contienen un guión</span><span class="sxs-lookup"><span data-stu-id="0716c-341">10 digits containing a hyphen</span></span>
  
### <a name="pattern"></a><span data-ttu-id="0716c-342">Patrón</span><span class="sxs-lookup"><span data-stu-id="0716c-342">Pattern</span></span>

<span data-ttu-id="0716c-343">10 dígitos que contienen un guión:</span><span class="sxs-lookup"><span data-stu-id="0716c-343">10 digits containing a hyphen:</span></span>
  
-  <span data-ttu-id="0716c-344">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="0716c-344">Six digits</span></span> 
    
- <span data-ttu-id="0716c-345">Un guión</span><span class="sxs-lookup"><span data-stu-id="0716c-345">A hyphen</span></span>
    
-  <span data-ttu-id="0716c-346">Cuatro dígitos</span><span class="sxs-lookup"><span data-stu-id="0716c-346">Four digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="0716c-347">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="0716c-347">Checksum</span></span>

<span data-ttu-id="0716c-348">No</span><span class="sxs-lookup"><span data-stu-id="0716c-348">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="0716c-349">Definición</span><span class="sxs-lookup"><span data-stu-id="0716c-349">Definition</span></span>

<span data-ttu-id="0716c-350">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="0716c-350">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="0716c-351">La expresión `Regex_finland_eu_driver's_license_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="0716c-351">The regular expression  `Regex_finland_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="0716c-352">Se encuentra una `Keywords_finland_eu_driver's_license_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="0716c-352">A keyword from  `Keywords_finland_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_finland_eu_driver's_license_number" />
          <Match idRef="Keywords_finland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="0716c-353">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="0716c-353">Keywords</span></span>

<span data-ttu-id="0716c-354">| |</span><span class="sxs-lookup"><span data-stu-id="0716c-354"></span></span>
|<span data-ttu-id="0716c-355">**Keywords_finland_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="0716c-355">**Keywords_finland_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="0716c-356">listas</span><span class="sxs-lookup"><span data-stu-id="0716c-356">dl#</span></span>  <br/> <span data-ttu-id="0716c-357">driver license</span><span class="sxs-lookup"><span data-stu-id="0716c-357">driver license</span></span>  <br/> <span data-ttu-id="0716c-358">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="0716c-358">driver license number</span></span>  <br/> <span data-ttu-id="0716c-359">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="0716c-359">driver licence</span></span>  <br/> <span data-ttu-id="0716c-360">Lic de drivers.</span><span class="sxs-lookup"><span data-stu-id="0716c-360">drivers lic.</span></span>  <br/> <span data-ttu-id="0716c-361">drivers license</span><span class="sxs-lookup"><span data-stu-id="0716c-361">drivers license</span></span>  <br/> <span data-ttu-id="0716c-362">drivers licence</span><span class="sxs-lookup"><span data-stu-id="0716c-362">drivers licence</span></span>  <br/> <span data-ttu-id="0716c-363">driver's license</span><span class="sxs-lookup"><span data-stu-id="0716c-363">driver's license</span></span>  <br/> <span data-ttu-id="0716c-364">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="0716c-364">driver's license number</span></span>  <br/> <span data-ttu-id="0716c-365">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="0716c-365">driver's licence number</span></span>  <br/> <span data-ttu-id="0716c-366">número de licencia de conducir</span><span class="sxs-lookup"><span data-stu-id="0716c-366">driving license number</span></span>  <br/> <span data-ttu-id="0716c-367">dlno#</span><span class="sxs-lookup"><span data-stu-id="0716c-367">dlno#</span></span>  <br/> <span data-ttu-id="0716c-368">ajokortti</span><span class="sxs-lookup"><span data-stu-id="0716c-368">ajokortti</span></span>  <br/> |
   
## <a name="france"></a><span data-ttu-id="0716c-369">Francia</span><span class="sxs-lookup"><span data-stu-id="0716c-369">France</span></span>

<span data-ttu-id="0716c-370">Para obtener más información, consulte la sección "número de permiso de conducción de Francia" en [Qué buscan los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="0716c-370">For details, see the section "France Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="germany"></a><span data-ttu-id="0716c-371">Alemania</span><span class="sxs-lookup"><span data-stu-id="0716c-371">Germany</span></span>

<span data-ttu-id="0716c-372">Para obtener más información, consulte la sección "número de permiso de conducción de alemán" en [el que se buscan los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="0716c-372">For details, see the section "German Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="greece"></a><span data-ttu-id="0716c-373">Grecia</span><span class="sxs-lookup"><span data-stu-id="0716c-373">Greece</span></span>

### <a name="format"></a><span data-ttu-id="0716c-374">Formato</span><span class="sxs-lookup"><span data-stu-id="0716c-374">Format</span></span>

<span data-ttu-id="0716c-375">Nueve dígitos sin espacios y delimitadores</span><span class="sxs-lookup"><span data-stu-id="0716c-375">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="0716c-376">Patrón</span><span class="sxs-lookup"><span data-stu-id="0716c-376">Pattern</span></span>

 <span data-ttu-id="0716c-377">Nueve dígitos</span><span class="sxs-lookup"><span data-stu-id="0716c-377">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="0716c-378">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="0716c-378">Checksum</span></span>

<span data-ttu-id="0716c-379">No</span><span class="sxs-lookup"><span data-stu-id="0716c-379">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="0716c-380">Definición</span><span class="sxs-lookup"><span data-stu-id="0716c-380">Definition</span></span>

<span data-ttu-id="0716c-381">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="0716c-381">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="0716c-382">La expresión `Regex_greece_eu_driver's_license_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="0716c-382">The regular expression  `Regex_greece_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="0716c-383">Se encuentra una `Keywords_greece_eu_driver's_license_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="0716c-383">A keyword from  `Keywords_greece_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_driver's_license_number" />
          <Match idRef="Keywords_greece_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="0716c-384">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="0716c-384">Keywords</span></span>

<span data-ttu-id="0716c-385">| |</span><span class="sxs-lookup"><span data-stu-id="0716c-385"></span></span>
|<span data-ttu-id="0716c-386">**Keywords_greece_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="0716c-386">**Keywords_greece_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="0716c-387">Biblioteca</span><span class="sxs-lookup"><span data-stu-id="0716c-387">dlL#</span></span>  <br/> <span data-ttu-id="0716c-388">driver license</span><span class="sxs-lookup"><span data-stu-id="0716c-388">driver license</span></span>  <br/> <span data-ttu-id="0716c-389">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="0716c-389">driver license number</span></span>  <br/> <span data-ttu-id="0716c-390">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="0716c-390">driver licence</span></span>  <br/> <span data-ttu-id="0716c-391">Lic de drivers.</span><span class="sxs-lookup"><span data-stu-id="0716c-391">drivers lic.</span></span>  <br/> <span data-ttu-id="0716c-392">drivers license</span><span class="sxs-lookup"><span data-stu-id="0716c-392">drivers license</span></span>  <br/> <span data-ttu-id="0716c-393">drivers licence</span><span class="sxs-lookup"><span data-stu-id="0716c-393">drivers licence</span></span>  <br/> <span data-ttu-id="0716c-394">driver's license</span><span class="sxs-lookup"><span data-stu-id="0716c-394">driver's license</span></span>  <br/> <span data-ttu-id="0716c-395">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="0716c-395">driver's license number</span></span>  <br/> <span data-ttu-id="0716c-396">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="0716c-396">driver's licence number</span></span>  <br/> <span data-ttu-id="0716c-397">número de licencia de conducir</span><span class="sxs-lookup"><span data-stu-id="0716c-397">driving license number</span></span>  <br/> <span data-ttu-id="0716c-398">dlno#</span><span class="sxs-lookup"><span data-stu-id="0716c-398">dlno#</span></span>  <br/> <span data-ttu-id="0716c-399">δεια οδήγησης</span><span class="sxs-lookup"><span data-stu-id="0716c-399">δεια οδήγησης</span></span>  <br/> <span data-ttu-id="0716c-400">Adeia odigisis</span><span class="sxs-lookup"><span data-stu-id="0716c-400">Adeia odigisis</span></span>  <br/> |
   
## <a name="hungary"></a><span data-ttu-id="0716c-401">Hungría</span><span class="sxs-lookup"><span data-stu-id="0716c-401">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="0716c-402">Formato</span><span class="sxs-lookup"><span data-stu-id="0716c-402">Format</span></span>

<span data-ttu-id="0716c-403">Dos letras seguidas de seis dígitos</span><span class="sxs-lookup"><span data-stu-id="0716c-403">Two letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="0716c-404">Patrón</span><span class="sxs-lookup"><span data-stu-id="0716c-404">Pattern</span></span>

<span data-ttu-id="0716c-405">Dos letras y seis dígitos:</span><span class="sxs-lookup"><span data-stu-id="0716c-405">Two letters and six digits:</span></span>
  
-  <span data-ttu-id="0716c-406">Dos letras (sin distinción entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="0716c-406">Two letters (not case-sensitive)</span></span> 
    
- <span data-ttu-id="0716c-407">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="0716c-407">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="0716c-408">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="0716c-408">Checksum</span></span>

<span data-ttu-id="0716c-409">No</span><span class="sxs-lookup"><span data-stu-id="0716c-409">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="0716c-410">Definición</span><span class="sxs-lookup"><span data-stu-id="0716c-410">Definition</span></span>

<span data-ttu-id="0716c-411">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="0716c-411">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="0716c-412">La expresión `Regex_hungary_eu_driver's_license_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="0716c-412">The regular expression  `Regex_hungary_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="0716c-413">Se encuentra una `Keywords_hungary_eu_driver's_license_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="0716c-413">A keyword from  `Keywords_hungary_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_driver's_license_number" />
          <Match idRef="Keywords_hungary_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="0716c-414">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="0716c-414">Keywords</span></span>

<span data-ttu-id="0716c-415">| |</span><span class="sxs-lookup"><span data-stu-id="0716c-415"></span></span>
|<span data-ttu-id="0716c-416">**Keywords_hungary_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="0716c-416">**Keywords_hungary_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="0716c-417">listas</span><span class="sxs-lookup"><span data-stu-id="0716c-417">dl#</span></span>  <br/> <span data-ttu-id="0716c-418">driver license</span><span class="sxs-lookup"><span data-stu-id="0716c-418">driver license</span></span>  <br/> <span data-ttu-id="0716c-419">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="0716c-419">driver license number</span></span>  <br/> <span data-ttu-id="0716c-420">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="0716c-420">driver licence</span></span>  <br/> <span data-ttu-id="0716c-421">Lic de drivers.</span><span class="sxs-lookup"><span data-stu-id="0716c-421">drivers lic.</span></span>  <br/> <span data-ttu-id="0716c-422">drivers license</span><span class="sxs-lookup"><span data-stu-id="0716c-422">drivers license</span></span>  <br/> <span data-ttu-id="0716c-423">drivers licence</span><span class="sxs-lookup"><span data-stu-id="0716c-423">drivers licence</span></span>  <br/> <span data-ttu-id="0716c-424">driver's license</span><span class="sxs-lookup"><span data-stu-id="0716c-424">driver's license</span></span>  <br/> <span data-ttu-id="0716c-425">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="0716c-425">driver's license number</span></span>  <br/> <span data-ttu-id="0716c-426">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="0716c-426">driver's licence number</span></span>  <br/> <span data-ttu-id="0716c-427">número de licencia de conducir</span><span class="sxs-lookup"><span data-stu-id="0716c-427">driving license number</span></span>  <br/> <span data-ttu-id="0716c-428">dlno#</span><span class="sxs-lookup"><span data-stu-id="0716c-428">dlno#</span></span>  <br/> <span data-ttu-id="0716c-429">vezetoi engedely</span><span class="sxs-lookup"><span data-stu-id="0716c-429">vezetoi engedely</span></span>  <br/> |
   
## <a name="ireland"></a><span data-ttu-id="0716c-430">Irlanda</span><span class="sxs-lookup"><span data-stu-id="0716c-430">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="0716c-431">Formato</span><span class="sxs-lookup"><span data-stu-id="0716c-431">Format</span></span>

<span data-ttu-id="0716c-432">Seis dígitos seguidos de cuatro letras</span><span class="sxs-lookup"><span data-stu-id="0716c-432">Six digits followed by four letters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="0716c-433">Patrón</span><span class="sxs-lookup"><span data-stu-id="0716c-433">Pattern</span></span>

<span data-ttu-id="0716c-434">Seis dígitos y cuatro letras:</span><span class="sxs-lookup"><span data-stu-id="0716c-434">Six digits and four letters:</span></span>
  
- <span data-ttu-id="0716c-435">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="0716c-435">Six digits</span></span>
    
- <span data-ttu-id="0716c-436">Cuatro letras (sin distinción entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="0716c-436">Four letters (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="0716c-437">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="0716c-437">Checksum</span></span>

<span data-ttu-id="0716c-438">No</span><span class="sxs-lookup"><span data-stu-id="0716c-438">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="0716c-439">Definición</span><span class="sxs-lookup"><span data-stu-id="0716c-439">Definition</span></span>

<span data-ttu-id="0716c-440">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="0716c-440">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="0716c-441">La expresión `Regex_ireland_eu_driver's_license_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="0716c-441">The regular expression  `Regex_ireland_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="0716c-442">Se encuentra una `Keywords_ireland_eu_driver's_license_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="0716c-442">A keyword from  `Keywords_ireland_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_driver's_license_number" />
          <Match idRef="Keywords_ireland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="0716c-443">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="0716c-443">Keywords</span></span>

<span data-ttu-id="0716c-444">| |</span><span class="sxs-lookup"><span data-stu-id="0716c-444"></span></span>
|<span data-ttu-id="0716c-445">**Keywords_ireland_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="0716c-445">**Keywords_ireland_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="0716c-446">listas</span><span class="sxs-lookup"><span data-stu-id="0716c-446">dl#</span></span>  <br/> <span data-ttu-id="0716c-447">driver license</span><span class="sxs-lookup"><span data-stu-id="0716c-447">driver license</span></span>  <br/> <span data-ttu-id="0716c-448">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="0716c-448">driver license number</span></span>  <br/> <span data-ttu-id="0716c-449">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="0716c-449">driver licence</span></span>  <br/> <span data-ttu-id="0716c-450">Lic de drivers.</span><span class="sxs-lookup"><span data-stu-id="0716c-450">drivers lic.</span></span>  <br/> <span data-ttu-id="0716c-451">drivers license</span><span class="sxs-lookup"><span data-stu-id="0716c-451">drivers license</span></span>  <br/> <span data-ttu-id="0716c-452">drivers licence</span><span class="sxs-lookup"><span data-stu-id="0716c-452">drivers licence</span></span>  <br/> <span data-ttu-id="0716c-453">driver's license</span><span class="sxs-lookup"><span data-stu-id="0716c-453">driver's license</span></span>  <br/> <span data-ttu-id="0716c-454">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="0716c-454">driver's license number</span></span>  <br/> <span data-ttu-id="0716c-455">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="0716c-455">driver's licence number</span></span>  <br/> <span data-ttu-id="0716c-456">número de licencia de conducir</span><span class="sxs-lookup"><span data-stu-id="0716c-456">driving license number</span></span>  <br/> <span data-ttu-id="0716c-457">dlno#</span><span class="sxs-lookup"><span data-stu-id="0716c-457">dlno#</span></span>  <br/> <span data-ttu-id="0716c-458">ceadúnas tiomána</span><span class="sxs-lookup"><span data-stu-id="0716c-458">ceadúnas tiomána</span></span>  <br/> |
   
## <a name="italy"></a><span data-ttu-id="0716c-459">Italia</span><span class="sxs-lookup"><span data-stu-id="0716c-459">Italy</span></span>

<span data-ttu-id="0716c-460">Para obtener más información, consulte la sección "número de licencia de conducción de Italia" en el [que se buscan los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="0716c-460">For details, see the section "Italy Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="latvia"></a><span data-ttu-id="0716c-461">Letonia</span><span class="sxs-lookup"><span data-stu-id="0716c-461">Latvia</span></span>

### <a name="format"></a><span data-ttu-id="0716c-462">Formato</span><span class="sxs-lookup"><span data-stu-id="0716c-462">Format</span></span>

<span data-ttu-id="0716c-463">Tres letras seguidas de seis dígitos</span><span class="sxs-lookup"><span data-stu-id="0716c-463">Three letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="0716c-464">Patrón</span><span class="sxs-lookup"><span data-stu-id="0716c-464">Pattern</span></span>

<span data-ttu-id="0716c-465">Tres letras y seis dígitos:</span><span class="sxs-lookup"><span data-stu-id="0716c-465">Three letters and six digits:</span></span>
  
-  <span data-ttu-id="0716c-466">Tres letras (sin distinción entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="0716c-466">Three letters (not case-sensitive)</span></span> 
    
- <span data-ttu-id="0716c-467">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="0716c-467">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="0716c-468">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="0716c-468">Checksum</span></span>

<span data-ttu-id="0716c-469">No</span><span class="sxs-lookup"><span data-stu-id="0716c-469">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="0716c-470">Definición</span><span class="sxs-lookup"><span data-stu-id="0716c-470">Definition</span></span>

<span data-ttu-id="0716c-471">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="0716c-471">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="0716c-472">La expresión `Regex_latvia_eu_driver's_license_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="0716c-472">The regular expression  `Regex_latvia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="0716c-473">Se encuentra una `Keywords_latvia_eu_driver's_license_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="0716c-473">A keyword from  `Keywords_latvia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_driver's_license_number" />
          <Match idRef="Keywords_latvia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="0716c-474">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="0716c-474">Keywords</span></span>

<span data-ttu-id="0716c-475">| |</span><span class="sxs-lookup"><span data-stu-id="0716c-475"></span></span>
|<span data-ttu-id="0716c-476">**Keywords_latvia_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="0716c-476">**Keywords_latvia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="0716c-477">listas</span><span class="sxs-lookup"><span data-stu-id="0716c-477">dl#</span></span>  <br/> <span data-ttu-id="0716c-478">driver license</span><span class="sxs-lookup"><span data-stu-id="0716c-478">driver license</span></span>  <br/> <span data-ttu-id="0716c-479">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="0716c-479">driver license number</span></span>  <br/> <span data-ttu-id="0716c-480">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="0716c-480">driver licence</span></span>  <br/> <span data-ttu-id="0716c-481">Lic de drivers.</span><span class="sxs-lookup"><span data-stu-id="0716c-481">drivers lic.</span></span>  <br/> <span data-ttu-id="0716c-482">drivers license</span><span class="sxs-lookup"><span data-stu-id="0716c-482">drivers license</span></span>  <br/> <span data-ttu-id="0716c-483">drivers licence</span><span class="sxs-lookup"><span data-stu-id="0716c-483">drivers licence</span></span>  <br/> <span data-ttu-id="0716c-484">driver's license</span><span class="sxs-lookup"><span data-stu-id="0716c-484">driver's license</span></span>  <br/> <span data-ttu-id="0716c-485">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="0716c-485">driver's license number</span></span>  <br/> <span data-ttu-id="0716c-486">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="0716c-486">driver's licence number</span></span>  <br/> <span data-ttu-id="0716c-487">número de licencia de conducir</span><span class="sxs-lookup"><span data-stu-id="0716c-487">driving license number</span></span>  <br/> <span data-ttu-id="0716c-488">dlno#</span><span class="sxs-lookup"><span data-stu-id="0716c-488">dlno#</span></span>  <br/> <span data-ttu-id="0716c-489">autovadītāja apliecība</span><span class="sxs-lookup"><span data-stu-id="0716c-489">autovadītāja apliecība</span></span>  <br/> |
   
## <a name="lithuania"></a><span data-ttu-id="0716c-490">Lituania</span><span class="sxs-lookup"><span data-stu-id="0716c-490">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="0716c-491">Formato</span><span class="sxs-lookup"><span data-stu-id="0716c-491">Format</span></span>

<span data-ttu-id="0716c-492">Ocho dígitos sin espacios y delimitadores</span><span class="sxs-lookup"><span data-stu-id="0716c-492">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="0716c-493">Patrón</span><span class="sxs-lookup"><span data-stu-id="0716c-493">Pattern</span></span>

 <span data-ttu-id="0716c-494">Ocho dígitos</span><span class="sxs-lookup"><span data-stu-id="0716c-494">Eight digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="0716c-495">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="0716c-495">Checksum</span></span>

<span data-ttu-id="0716c-496">No</span><span class="sxs-lookup"><span data-stu-id="0716c-496">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="0716c-497">Definición</span><span class="sxs-lookup"><span data-stu-id="0716c-497">Definition</span></span>

<span data-ttu-id="0716c-498">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="0716c-498">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="0716c-499">La expresión `Regex_lithuania_eu_driver's_license_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="0716c-499">The regular expression  `Regex_lithuania_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="0716c-500">Se encuentra una `Keywords_lithuania_eu_driver's_license_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="0716c-500">A keyword from  `Keywords_lithuania_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_driver's_license_number" />
          <Match idRef="Keywords_lithuania_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="0716c-501">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="0716c-501">Keywords</span></span>

<span data-ttu-id="0716c-502">| |</span><span class="sxs-lookup"><span data-stu-id="0716c-502"></span></span>
|<span data-ttu-id="0716c-503">**Keywords_lithuania_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="0716c-503">**Keywords_lithuania_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="0716c-504">listas</span><span class="sxs-lookup"><span data-stu-id="0716c-504">dl#</span></span>  <br/> <span data-ttu-id="0716c-505">driver license</span><span class="sxs-lookup"><span data-stu-id="0716c-505">driver license</span></span>  <br/> <span data-ttu-id="0716c-506">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="0716c-506">driver license number</span></span>  <br/> <span data-ttu-id="0716c-507">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="0716c-507">driver licence</span></span>  <br/> <span data-ttu-id="0716c-508">Lic de drivers.</span><span class="sxs-lookup"><span data-stu-id="0716c-508">drivers lic.</span></span>  <br/> <span data-ttu-id="0716c-509">drivers license</span><span class="sxs-lookup"><span data-stu-id="0716c-509">drivers license</span></span>  <br/> <span data-ttu-id="0716c-510">drivers licence</span><span class="sxs-lookup"><span data-stu-id="0716c-510">drivers licence</span></span>  <br/> <span data-ttu-id="0716c-511">driver's license</span><span class="sxs-lookup"><span data-stu-id="0716c-511">driver's license</span></span>  <br/> <span data-ttu-id="0716c-512">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="0716c-512">driver's license number</span></span>  <br/> <span data-ttu-id="0716c-513">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="0716c-513">driver's licence number</span></span>  <br/> <span data-ttu-id="0716c-514">número de licencia de conducir</span><span class="sxs-lookup"><span data-stu-id="0716c-514">driving license number</span></span>  <br/> <span data-ttu-id="0716c-515">dlno#</span><span class="sxs-lookup"><span data-stu-id="0716c-515">dlno#</span></span>  <br/> <span data-ttu-id="0716c-516">vairuotojo pažymėjimas</span><span class="sxs-lookup"><span data-stu-id="0716c-516">vairuotojo pažymėjimas</span></span>  <br/> |
   
## <a name="luxemburg"></a><span data-ttu-id="0716c-517">Luxemburgo</span><span class="sxs-lookup"><span data-stu-id="0716c-517">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="0716c-518">Formato</span><span class="sxs-lookup"><span data-stu-id="0716c-518">Format</span></span>

<span data-ttu-id="0716c-519">Seis dígitos sin espacios y delimitadores</span><span class="sxs-lookup"><span data-stu-id="0716c-519">Six digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="0716c-520">Patrón</span><span class="sxs-lookup"><span data-stu-id="0716c-520">Pattern</span></span>

 <span data-ttu-id="0716c-521">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="0716c-521">Six digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="0716c-522">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="0716c-522">Checksum</span></span>

<span data-ttu-id="0716c-523">No</span><span class="sxs-lookup"><span data-stu-id="0716c-523">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="0716c-524">Definición</span><span class="sxs-lookup"><span data-stu-id="0716c-524">Definition</span></span>

<span data-ttu-id="0716c-525">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="0716c-525">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="0716c-526">La expresión `Regex_luxemburg_eu_driver's_license_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="0716c-526">The regular expression  `Regex_luxemburg_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="0716c-527">Se encuentra una `Keywords_luxemburg_eu_driver's_license_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="0716c-527">A keyword from  `Keywords_luxemburg_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_luxemburg_eu_driver's_license_number" />
          <Match idRef="Keywords_luxemburg_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="0716c-528">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="0716c-528">Keywords</span></span>

<span data-ttu-id="0716c-529">| |</span><span class="sxs-lookup"><span data-stu-id="0716c-529"></span></span>
|<span data-ttu-id="0716c-530">**Keywords_luxemburg_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="0716c-530">**Keywords_luxemburg_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="0716c-531">listas</span><span class="sxs-lookup"><span data-stu-id="0716c-531">dl#</span></span>  <br/> <span data-ttu-id="0716c-532">driver license</span><span class="sxs-lookup"><span data-stu-id="0716c-532">driver license</span></span>  <br/> <span data-ttu-id="0716c-533">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="0716c-533">driver license number</span></span>  <br/> <span data-ttu-id="0716c-534">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="0716c-534">driver licence</span></span>  <br/> <span data-ttu-id="0716c-535">Lic de drivers.</span><span class="sxs-lookup"><span data-stu-id="0716c-535">drivers lic.</span></span>  <br/> <span data-ttu-id="0716c-536">drivers license</span><span class="sxs-lookup"><span data-stu-id="0716c-536">drivers license</span></span>  <br/> <span data-ttu-id="0716c-537">drivers licence</span><span class="sxs-lookup"><span data-stu-id="0716c-537">drivers licence</span></span>  <br/> <span data-ttu-id="0716c-538">driver's license</span><span class="sxs-lookup"><span data-stu-id="0716c-538">driver's license</span></span>  <br/> <span data-ttu-id="0716c-539">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="0716c-539">driver's license number</span></span>  <br/> <span data-ttu-id="0716c-540">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="0716c-540">driver's licence number</span></span>  <br/> <span data-ttu-id="0716c-541">número de licencia de conducir</span><span class="sxs-lookup"><span data-stu-id="0716c-541">driving license number</span></span>  <br/> <span data-ttu-id="0716c-542">dlno#</span><span class="sxs-lookup"><span data-stu-id="0716c-542">dlno#</span></span>  <br/> <span data-ttu-id="0716c-543">fahrerlaubnis</span><span class="sxs-lookup"><span data-stu-id="0716c-543">fahrerlaubnis</span></span>  <br/> |
   
## <a name="malta"></a><span data-ttu-id="0716c-544">Malta</span><span class="sxs-lookup"><span data-stu-id="0716c-544">Malta</span></span>

### <a name="format"></a><span data-ttu-id="0716c-545">Formato</span><span class="sxs-lookup"><span data-stu-id="0716c-545">Format</span></span>

<span data-ttu-id="0716c-546">Combinación de dos caracteres y seis dígitos en el patrón especificado</span><span class="sxs-lookup"><span data-stu-id="0716c-546">Combination of two characters and six digits in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="0716c-547">Patrón</span><span class="sxs-lookup"><span data-stu-id="0716c-547">Pattern</span></span>

<span data-ttu-id="0716c-548">Combinación de dos caracteres y seis dígitos:</span><span class="sxs-lookup"><span data-stu-id="0716c-548">Combination of two characters and six digits:</span></span>
  
- <span data-ttu-id="0716c-549">Dos caracteres (dígitos o letras, no distinguen entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="0716c-549">Two characters (digits or letters, not case-sensitive)</span></span>
    
- <span data-ttu-id="0716c-550">Un espacio (opcional) </span><span class="sxs-lookup"><span data-stu-id="0716c-550">A space (optional)</span></span>
    
- <span data-ttu-id="0716c-551">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="0716c-551">Three digits</span></span>
    
- <span data-ttu-id="0716c-552">Un espacio (opcional) </span><span class="sxs-lookup"><span data-stu-id="0716c-552">A space (optional)</span></span>
    
- <span data-ttu-id="0716c-553">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="0716c-553">Three digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="0716c-554">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="0716c-554">Checksum</span></span>

<span data-ttu-id="0716c-555">No</span><span class="sxs-lookup"><span data-stu-id="0716c-555">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="0716c-556">Definición</span><span class="sxs-lookup"><span data-stu-id="0716c-556">Definition</span></span>

<span data-ttu-id="0716c-557">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="0716c-557">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="0716c-558">La expresión `Regex_malta_eu_driver's_license_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="0716c-558">The regular expression  `Regex_malta_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="0716c-559">Se encuentra una `Keywords_malta_eu_driver's_license_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="0716c-559">A keyword from  `Keywords_malta_eu_driver's_license_number` is found.</span></span> 
    
```
<!-- EU Driver's License Number -->
 <Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_driver's_license_number" />
          <Match idRef="Keywords_malta_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="0716c-560">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="0716c-560">Keywords</span></span>

<span data-ttu-id="0716c-561">| |</span><span class="sxs-lookup"><span data-stu-id="0716c-561"></span></span>
|<span data-ttu-id="0716c-562">**Keywords_malta_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="0716c-562">**Keywords_malta_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="0716c-563">listas</span><span class="sxs-lookup"><span data-stu-id="0716c-563">dl#</span></span>  <br/> <span data-ttu-id="0716c-564">driver license</span><span class="sxs-lookup"><span data-stu-id="0716c-564">driver license</span></span>  <br/> <span data-ttu-id="0716c-565">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="0716c-565">driver license number</span></span>  <br/> <span data-ttu-id="0716c-566">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="0716c-566">driver licence</span></span>  <br/> <span data-ttu-id="0716c-567">Lic de drivers.</span><span class="sxs-lookup"><span data-stu-id="0716c-567">drivers lic.</span></span>  <br/> <span data-ttu-id="0716c-568">drivers license</span><span class="sxs-lookup"><span data-stu-id="0716c-568">drivers license</span></span>  <br/> <span data-ttu-id="0716c-569">drivers licence</span><span class="sxs-lookup"><span data-stu-id="0716c-569">drivers licence</span></span>  <br/> <span data-ttu-id="0716c-570">driver's license</span><span class="sxs-lookup"><span data-stu-id="0716c-570">driver's license</span></span>  <br/> <span data-ttu-id="0716c-571">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="0716c-571">driver's license number</span></span>  <br/> <span data-ttu-id="0716c-572">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="0716c-572">driver's licence number</span></span>  <br/> <span data-ttu-id="0716c-573">número de licencia de conducir</span><span class="sxs-lookup"><span data-stu-id="0716c-573">driving license number</span></span>  <br/> <span data-ttu-id="0716c-574">dlno#</span><span class="sxs-lookup"><span data-stu-id="0716c-574">dlno#</span></span>  <br/> <span data-ttu-id="0716c-575">liċenzja sewqan</span><span class="sxs-lookup"><span data-stu-id="0716c-575">liċenzja tas-sewqan</span></span>  <br/> |
   
## <a name="netherlands"></a><span data-ttu-id="0716c-576">Países Bajos</span><span class="sxs-lookup"><span data-stu-id="0716c-576">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="0716c-577">Formato</span><span class="sxs-lookup"><span data-stu-id="0716c-577">Format</span></span>

<span data-ttu-id="0716c-578">10 dígitos sin espacios y delimitadores</span><span class="sxs-lookup"><span data-stu-id="0716c-578">10 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="0716c-579">Patrón</span><span class="sxs-lookup"><span data-stu-id="0716c-579">Pattern</span></span>

<span data-ttu-id="0716c-580">10 dígitos</span><span class="sxs-lookup"><span data-stu-id="0716c-580">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="0716c-581">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="0716c-581">Checksum</span></span>

<span data-ttu-id="0716c-582">No</span><span class="sxs-lookup"><span data-stu-id="0716c-582">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="0716c-583">Definición</span><span class="sxs-lookup"><span data-stu-id="0716c-583">Definition</span></span>

<span data-ttu-id="0716c-584">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="0716c-584">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="0716c-585">La expresión `Regex_netherlands_eu_driver's_license_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="0716c-585">The regular expression  `Regex_netherlands_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="0716c-586">Se encuentra una `Keywords_netherlands_eu_driver's_license_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="0716c-586">A keyword from  `Keywords_netherlands_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_driver's_license_number" />
          <Match idRef="Keywords_netherlands_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="0716c-587">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="0716c-587">Keywords</span></span>

<span data-ttu-id="0716c-588">| |</span><span class="sxs-lookup"><span data-stu-id="0716c-588"></span></span>
|<span data-ttu-id="0716c-589">**Keywords_netherlands_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="0716c-589">**Keywords_netherlands_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="0716c-590">listas</span><span class="sxs-lookup"><span data-stu-id="0716c-590">dl#</span></span>  <br/> <span data-ttu-id="0716c-591">driver license</span><span class="sxs-lookup"><span data-stu-id="0716c-591">driver license</span></span>  <br/> <span data-ttu-id="0716c-592">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="0716c-592">driver license number</span></span>  <br/> <span data-ttu-id="0716c-593">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="0716c-593">driver licence</span></span>  <br/> <span data-ttu-id="0716c-594">Lic de drivers.</span><span class="sxs-lookup"><span data-stu-id="0716c-594">drivers lic.</span></span>  <br/> <span data-ttu-id="0716c-595">drivers license</span><span class="sxs-lookup"><span data-stu-id="0716c-595">drivers license</span></span>  <br/> <span data-ttu-id="0716c-596">drivers licence</span><span class="sxs-lookup"><span data-stu-id="0716c-596">drivers licence</span></span>  <br/> <span data-ttu-id="0716c-597">driver's license</span><span class="sxs-lookup"><span data-stu-id="0716c-597">driver's license</span></span>  <br/> <span data-ttu-id="0716c-598">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="0716c-598">driver's license number</span></span>  <br/> <span data-ttu-id="0716c-599">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="0716c-599">driver's licence number</span></span>  <br/> <span data-ttu-id="0716c-600">número de licencia de conducir</span><span class="sxs-lookup"><span data-stu-id="0716c-600">driving license number</span></span>  <br/> <span data-ttu-id="0716c-601">dlno#</span><span class="sxs-lookup"><span data-stu-id="0716c-601">dlno#</span></span>  <br/> <span data-ttu-id="0716c-602">permis de conduire</span><span class="sxs-lookup"><span data-stu-id="0716c-602">permis de conduire</span></span>  <br/> <span data-ttu-id="0716c-603">rijbewijs</span><span class="sxs-lookup"><span data-stu-id="0716c-603">rijbewijs</span></span>  <br/> <span data-ttu-id="0716c-604">rijbewijsnummer</span><span class="sxs-lookup"><span data-stu-id="0716c-604">rijbewijsnummer</span></span>  <br/> |
   
## <a name="poland"></a><span data-ttu-id="0716c-605">Polonia</span><span class="sxs-lookup"><span data-stu-id="0716c-605">Poland</span></span>

### <a name="format"></a><span data-ttu-id="0716c-606">Formato</span><span class="sxs-lookup"><span data-stu-id="0716c-606">Format</span></span>

<span data-ttu-id="0716c-607">14 dígitos que contienen 2 barras diagonales</span><span class="sxs-lookup"><span data-stu-id="0716c-607">14 digits containing 2 forward slashes</span></span>
  
### <a name="pattern"></a><span data-ttu-id="0716c-608">Patrón</span><span class="sxs-lookup"><span data-stu-id="0716c-608">Pattern</span></span>

<span data-ttu-id="0716c-609">14 dígitos y 2 barras diagonales:</span><span class="sxs-lookup"><span data-stu-id="0716c-609">14 digits and 2 forward slashes:</span></span>
  
-  <span data-ttu-id="0716c-610">Cinco dígitos</span><span class="sxs-lookup"><span data-stu-id="0716c-610">Five digits</span></span> 
    
- <span data-ttu-id="0716c-611">Una barra diagonal </span><span class="sxs-lookup"><span data-stu-id="0716c-611">A forward slash</span></span>
    
- <span data-ttu-id="0716c-612">Dos dígitos</span><span class="sxs-lookup"><span data-stu-id="0716c-612">Two digits</span></span>
    
- <span data-ttu-id="0716c-613">Una barra diagonal </span><span class="sxs-lookup"><span data-stu-id="0716c-613">A forward slash</span></span>
    
- <span data-ttu-id="0716c-614">Siete dígitos</span><span class="sxs-lookup"><span data-stu-id="0716c-614">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="0716c-615">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="0716c-615">Checksum</span></span>

<span data-ttu-id="0716c-616">No</span><span class="sxs-lookup"><span data-stu-id="0716c-616">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="0716c-617">Definición</span><span class="sxs-lookup"><span data-stu-id="0716c-617">Definition</span></span>

<span data-ttu-id="0716c-618">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="0716c-618">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="0716c-619">La expresión `Regex_poland_eu_driver's_license_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="0716c-619">The regular expression  `Regex_poland_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="0716c-620">Se encuentra una `Keywords_poland_eu_driver's_license_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="0716c-620">A keyword from  `Keywords_poland_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_poland_eu_driver's_license_number" />
          <Match idRef="Keywords_poland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="0716c-621">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="0716c-621">Keywords</span></span>

<span data-ttu-id="0716c-622">| |</span><span class="sxs-lookup"><span data-stu-id="0716c-622"></span></span>
|<span data-ttu-id="0716c-623">**Keywords_poland_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="0716c-623">**Keywords_poland_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="0716c-624">listas</span><span class="sxs-lookup"><span data-stu-id="0716c-624">dl#</span></span>  <br/> <span data-ttu-id="0716c-625">driver license</span><span class="sxs-lookup"><span data-stu-id="0716c-625">driver license</span></span>  <br/> <span data-ttu-id="0716c-626">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="0716c-626">driver license number</span></span>  <br/> <span data-ttu-id="0716c-627">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="0716c-627">driver licence</span></span>  <br/> <span data-ttu-id="0716c-628">Lic de drivers.</span><span class="sxs-lookup"><span data-stu-id="0716c-628">drivers lic.</span></span>  <br/> <span data-ttu-id="0716c-629">drivers license</span><span class="sxs-lookup"><span data-stu-id="0716c-629">drivers license</span></span>  <br/> <span data-ttu-id="0716c-630">drivers licence</span><span class="sxs-lookup"><span data-stu-id="0716c-630">drivers licence</span></span>  <br/> <span data-ttu-id="0716c-631">driver's license</span><span class="sxs-lookup"><span data-stu-id="0716c-631">driver's license</span></span>  <br/> <span data-ttu-id="0716c-632">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="0716c-632">driver's license number</span></span>  <br/> <span data-ttu-id="0716c-633">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="0716c-633">driver's licence number</span></span>  <br/> <span data-ttu-id="0716c-634">número de licencia de conducir</span><span class="sxs-lookup"><span data-stu-id="0716c-634">driving license number</span></span>  <br/> <span data-ttu-id="0716c-635">dlno#</span><span class="sxs-lookup"><span data-stu-id="0716c-635">dlno#</span></span>  <br/> <span data-ttu-id="0716c-636">prawo jazdy</span><span class="sxs-lookup"><span data-stu-id="0716c-636">prawo jazdy</span></span>  <br/> |
   
## <a name="portugal"></a><span data-ttu-id="0716c-637">Portugal</span><span class="sxs-lookup"><span data-stu-id="0716c-637">Portugal</span></span>

### <a name="format"></a><span data-ttu-id="0716c-638">Formato</span><span class="sxs-lookup"><span data-stu-id="0716c-638">Format</span></span>

<span data-ttu-id="0716c-639">Dos letras seguidas de siete números en el patrón especificado</span><span class="sxs-lookup"><span data-stu-id="0716c-639">Two letters followed by a seven numbers in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="0716c-640">Patrón</span><span class="sxs-lookup"><span data-stu-id="0716c-640">Pattern</span></span>

<span data-ttu-id="0716c-641">Dos letras seguidas de siete números con caracteres especiales:</span><span class="sxs-lookup"><span data-stu-id="0716c-641">Two letters followed by seven numbers with special characters:</span></span>
  
-  <span data-ttu-id="0716c-642">Dos letras (sin distinción entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="0716c-642">Two letters (not case-sensitive)</span></span> 
    
- <span data-ttu-id="0716c-643">Un guión </span><span class="sxs-lookup"><span data-stu-id="0716c-643">A hyphen</span></span>
    
- <span data-ttu-id="0716c-644">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="0716c-644">Six digits</span></span>
    
- <span data-ttu-id="0716c-645">Un espacio</span><span class="sxs-lookup"><span data-stu-id="0716c-645">A space</span></span>
    
- <span data-ttu-id="0716c-646">Un dígito</span><span class="sxs-lookup"><span data-stu-id="0716c-646">One digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="0716c-647">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="0716c-647">Checksum</span></span>

<span data-ttu-id="0716c-648">No</span><span class="sxs-lookup"><span data-stu-id="0716c-648">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="0716c-649">Definición</span><span class="sxs-lookup"><span data-stu-id="0716c-649">Definition</span></span>

<span data-ttu-id="0716c-650">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="0716c-650">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="0716c-651">La expresión `Regex_portugal_eu_driver's_license_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="0716c-651">The regular expression  `Regex_portugal_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="0716c-652">Se encuentra una `Keywords_portugal_eu_driver's_license_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="0716c-652">A keyword from  `Keywords_portugal_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_driver's_license_number" />
          <Match idRef="Keywords_portugal_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="0716c-653">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="0716c-653">Keywords</span></span>

<span data-ttu-id="0716c-654">| |</span><span class="sxs-lookup"><span data-stu-id="0716c-654"></span></span>
|<span data-ttu-id="0716c-655">**Keywords_portugal_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="0716c-655">**Keywords_portugal_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="0716c-656">listas</span><span class="sxs-lookup"><span data-stu-id="0716c-656">dl#</span></span>  <br/> <span data-ttu-id="0716c-657">driver license</span><span class="sxs-lookup"><span data-stu-id="0716c-657">driver license</span></span>  <br/> <span data-ttu-id="0716c-658">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="0716c-658">driver license number</span></span>  <br/> <span data-ttu-id="0716c-659">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="0716c-659">driver licence</span></span>  <br/> <span data-ttu-id="0716c-660">Lic de drivers.</span><span class="sxs-lookup"><span data-stu-id="0716c-660">drivers lic.</span></span>  <br/> <span data-ttu-id="0716c-661">drivers license</span><span class="sxs-lookup"><span data-stu-id="0716c-661">drivers license</span></span>  <br/> <span data-ttu-id="0716c-662">drivers licence</span><span class="sxs-lookup"><span data-stu-id="0716c-662">drivers licence</span></span>  <br/> <span data-ttu-id="0716c-663">driver's license</span><span class="sxs-lookup"><span data-stu-id="0716c-663">driver's license</span></span>  <br/> <span data-ttu-id="0716c-664">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="0716c-664">driver's license number</span></span>  <br/> <span data-ttu-id="0716c-665">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="0716c-665">driver's licence number</span></span>  <br/> <span data-ttu-id="0716c-666">número de licencia de conducir</span><span class="sxs-lookup"><span data-stu-id="0716c-666">driving license number</span></span>  <br/> <span data-ttu-id="0716c-667">dlno#</span><span class="sxs-lookup"><span data-stu-id="0716c-667">dlno#</span></span>  <br/> <span data-ttu-id="0716c-668">Carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="0716c-668">carteira de motorista</span></span>  <br/> |
   
## <a name="romania"></a><span data-ttu-id="0716c-669">Rumania</span><span class="sxs-lookup"><span data-stu-id="0716c-669">Romania</span></span>

### <a name="format"></a><span data-ttu-id="0716c-670">Formato</span><span class="sxs-lookup"><span data-stu-id="0716c-670">Format</span></span>

<span data-ttu-id="0716c-671">Un carácter seguido de ocho dígitos</span><span class="sxs-lookup"><span data-stu-id="0716c-671">One character followed by eight digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="0716c-672">Patrón</span><span class="sxs-lookup"><span data-stu-id="0716c-672">Pattern</span></span>

<span data-ttu-id="0716c-673">Un carácter seguido de ocho dígitos:</span><span class="sxs-lookup"><span data-stu-id="0716c-673">One character followed by eight digits:</span></span>
  
-  <span data-ttu-id="0716c-674">Una letra (no distingue entre mayúsculas y minúsculas) o un dígito</span><span class="sxs-lookup"><span data-stu-id="0716c-674">One letter (not case-sensitive) or digit</span></span> 
    
- <span data-ttu-id="0716c-675">Ocho dígitos</span><span class="sxs-lookup"><span data-stu-id="0716c-675">Eight digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="0716c-676">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="0716c-676">Checksum</span></span>

<span data-ttu-id="0716c-677">No</span><span class="sxs-lookup"><span data-stu-id="0716c-677">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="0716c-678">Definición</span><span class="sxs-lookup"><span data-stu-id="0716c-678">Definition</span></span>

<span data-ttu-id="0716c-679">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="0716c-679">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="0716c-680">La expresión `Regex_romania_eu_driver's_license_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="0716c-680">The regular expression  `Regex_romania_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="0716c-681">Se encuentra una `Keywords_romania_eu_driver's_license_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="0716c-681">A keyword from  `Keywords_romania_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_driver's_license_number" />
          <Match idRef="Keywords_romania_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="0716c-682">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="0716c-682">Keywords</span></span>

<span data-ttu-id="0716c-683">| |</span><span class="sxs-lookup"><span data-stu-id="0716c-683"></span></span>
|<span data-ttu-id="0716c-684">**Keywords_romania_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="0716c-684">**Keywords_romania_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="0716c-685">listas</span><span class="sxs-lookup"><span data-stu-id="0716c-685">dl#</span></span>  <br/> <span data-ttu-id="0716c-686">driver license</span><span class="sxs-lookup"><span data-stu-id="0716c-686">driver license</span></span>  <br/> <span data-ttu-id="0716c-687">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="0716c-687">driver license number</span></span>  <br/> <span data-ttu-id="0716c-688">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="0716c-688">driver licence</span></span>  <br/> <span data-ttu-id="0716c-689">Lic de drivers.</span><span class="sxs-lookup"><span data-stu-id="0716c-689">drivers lic.</span></span>  <br/> <span data-ttu-id="0716c-690">drivers license</span><span class="sxs-lookup"><span data-stu-id="0716c-690">drivers license</span></span>  <br/> <span data-ttu-id="0716c-691">drivers licence</span><span class="sxs-lookup"><span data-stu-id="0716c-691">drivers licence</span></span>  <br/> <span data-ttu-id="0716c-692">driver's license</span><span class="sxs-lookup"><span data-stu-id="0716c-692">driver's license</span></span>  <br/> <span data-ttu-id="0716c-693">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="0716c-693">driver's license number</span></span>  <br/> <span data-ttu-id="0716c-694">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="0716c-694">driver's licence number</span></span>  <br/> <span data-ttu-id="0716c-695">número de licencia de conducir</span><span class="sxs-lookup"><span data-stu-id="0716c-695">driving license number</span></span>  <br/> <span data-ttu-id="0716c-696">dlno#</span><span class="sxs-lookup"><span data-stu-id="0716c-696">dlno#</span></span>  <br/> <span data-ttu-id="0716c-697">Perm de conducere</span><span class="sxs-lookup"><span data-stu-id="0716c-697">permis de conducere</span></span>  <br/> |
   
## <a name="slovakia"></a><span data-ttu-id="0716c-698">Eslovaquia</span><span class="sxs-lookup"><span data-stu-id="0716c-698">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="0716c-699">Formato</span><span class="sxs-lookup"><span data-stu-id="0716c-699">Format</span></span>

<span data-ttu-id="0716c-700">Un carácter seguido de siete dígitos</span><span class="sxs-lookup"><span data-stu-id="0716c-700">One character followed by seven digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="0716c-701">Patrón</span><span class="sxs-lookup"><span data-stu-id="0716c-701">Pattern</span></span>

<span data-ttu-id="0716c-702">Un carácter seguido de siete dígitos</span><span class="sxs-lookup"><span data-stu-id="0716c-702">One character followed by seven digits</span></span>
  
- <span data-ttu-id="0716c-703">Una letra (no distingue entre mayúsculas y minúsculas) o un dígito</span><span class="sxs-lookup"><span data-stu-id="0716c-703">One letter (not case-sensitive) or digit</span></span>
    
-  <span data-ttu-id="0716c-704">Siete dígitos</span><span class="sxs-lookup"><span data-stu-id="0716c-704">Seven digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="0716c-705">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="0716c-705">Checksum</span></span>

<span data-ttu-id="0716c-706">No</span><span class="sxs-lookup"><span data-stu-id="0716c-706">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="0716c-707">Definición</span><span class="sxs-lookup"><span data-stu-id="0716c-707">Definition</span></span>

<span data-ttu-id="0716c-708">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="0716c-708">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="0716c-709">La expresión `Regex_slovakia_eu_driver's_license_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="0716c-709">The regular expression  `Regex_slovakia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="0716c-710">Se encuentra una `Keywords_slovakia_eu_driver's_license_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="0716c-710">A keyword from  `Keywords_slovakia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovaknia_eu_driver's_license_number" />
          <Match idRef="Keywords_slovakia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="0716c-711">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="0716c-711">Keywords</span></span>

<span data-ttu-id="0716c-712">| |</span><span class="sxs-lookup"><span data-stu-id="0716c-712"></span></span>
|<span data-ttu-id="0716c-713">**Keywords_slovakia_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="0716c-713">**Keywords_slovakia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="0716c-714">listas</span><span class="sxs-lookup"><span data-stu-id="0716c-714">dl#</span></span>  <br/> <span data-ttu-id="0716c-715">driver license</span><span class="sxs-lookup"><span data-stu-id="0716c-715">driver license</span></span>  <br/> <span data-ttu-id="0716c-716">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="0716c-716">driver license number</span></span>  <br/> <span data-ttu-id="0716c-717">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="0716c-717">driver licence</span></span>  <br/> <span data-ttu-id="0716c-718">Lic de drivers.</span><span class="sxs-lookup"><span data-stu-id="0716c-718">drivers lic.</span></span>  <br/> <span data-ttu-id="0716c-719">drivers license</span><span class="sxs-lookup"><span data-stu-id="0716c-719">drivers license</span></span>  <br/> <span data-ttu-id="0716c-720">drivers licence</span><span class="sxs-lookup"><span data-stu-id="0716c-720">drivers licence</span></span>  <br/> <span data-ttu-id="0716c-721">driver's license</span><span class="sxs-lookup"><span data-stu-id="0716c-721">driver's license</span></span>  <br/> <span data-ttu-id="0716c-722">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="0716c-722">driver's license number</span></span>  <br/> <span data-ttu-id="0716c-723">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="0716c-723">driver's licence number</span></span>  <br/> <span data-ttu-id="0716c-724">número de licencia de conducir</span><span class="sxs-lookup"><span data-stu-id="0716c-724">driving license number</span></span>  <br/> <span data-ttu-id="0716c-725">dlno#</span><span class="sxs-lookup"><span data-stu-id="0716c-725">dlno#</span></span>  <br/> <span data-ttu-id="0716c-726">vodičský preukaz</span><span class="sxs-lookup"><span data-stu-id="0716c-726">vodičský preukaz</span></span>  <br/> |
   
## <a name="slovenia"></a><span data-ttu-id="0716c-727">Eslovenia</span><span class="sxs-lookup"><span data-stu-id="0716c-727">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="0716c-728">Formato</span><span class="sxs-lookup"><span data-stu-id="0716c-728">Format</span></span>

<span data-ttu-id="0716c-729">Nueve dígitos sin espacios y delimitadores</span><span class="sxs-lookup"><span data-stu-id="0716c-729">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="0716c-730">Patrón</span><span class="sxs-lookup"><span data-stu-id="0716c-730">Pattern</span></span>

<span data-ttu-id="0716c-731">Nueve dígitos</span><span class="sxs-lookup"><span data-stu-id="0716c-731">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="0716c-732">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="0716c-732">Checksum</span></span>

<span data-ttu-id="0716c-733">No</span><span class="sxs-lookup"><span data-stu-id="0716c-733">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="0716c-734">Definición</span><span class="sxs-lookup"><span data-stu-id="0716c-734">Definition</span></span>

<span data-ttu-id="0716c-735">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="0716c-735">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="0716c-736">La expresión `Regex_slovenia_eu_driver's_license_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="0716c-736">The regular expression  `Regex_slovenia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="0716c-737">Se encuentra una `Keywords_slovenia_eu_driver's_license_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="0716c-737">A keyword from  `Keywords_slovenia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_driver's_license_number" />
          <Match idRef="Keywords_slovenia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="0716c-738">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="0716c-738">Keywords</span></span>

<span data-ttu-id="0716c-739">| |</span><span class="sxs-lookup"><span data-stu-id="0716c-739"></span></span>
|<span data-ttu-id="0716c-740">**Keywords_slovenia_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="0716c-740">**Keywords_slovenia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="0716c-741">listas</span><span class="sxs-lookup"><span data-stu-id="0716c-741">dl#</span></span>  <br/> <span data-ttu-id="0716c-742">driver license</span><span class="sxs-lookup"><span data-stu-id="0716c-742">driver license</span></span>  <br/> <span data-ttu-id="0716c-743">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="0716c-743">driver license number</span></span>  <br/> <span data-ttu-id="0716c-744">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="0716c-744">driver licence</span></span>  <br/> <span data-ttu-id="0716c-745">Lic de drivers.</span><span class="sxs-lookup"><span data-stu-id="0716c-745">drivers lic.</span></span>  <br/> <span data-ttu-id="0716c-746">drivers license</span><span class="sxs-lookup"><span data-stu-id="0716c-746">drivers license</span></span>  <br/> <span data-ttu-id="0716c-747">drivers licence</span><span class="sxs-lookup"><span data-stu-id="0716c-747">drivers licence</span></span>  <br/> <span data-ttu-id="0716c-748">driver's license</span><span class="sxs-lookup"><span data-stu-id="0716c-748">driver's license</span></span>  <br/> <span data-ttu-id="0716c-749">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="0716c-749">driver's license number</span></span>  <br/> <span data-ttu-id="0716c-750">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="0716c-750">driver's licence number</span></span>  <br/> <span data-ttu-id="0716c-751">número de licencia de conducir</span><span class="sxs-lookup"><span data-stu-id="0716c-751">driving license number</span></span>  <br/> <span data-ttu-id="0716c-752">dlno#</span><span class="sxs-lookup"><span data-stu-id="0716c-752">dlno#</span></span>  <br/> <span data-ttu-id="0716c-753">vozniško dovoljenje</span><span class="sxs-lookup"><span data-stu-id="0716c-753">vozniško dovoljenje</span></span>  <br/> |
   
## <a name="spain"></a><span data-ttu-id="0716c-754">España</span><span class="sxs-lookup"><span data-stu-id="0716c-754">Spain</span></span>

### <a name="format"></a><span data-ttu-id="0716c-755">Formato</span><span class="sxs-lookup"><span data-stu-id="0716c-755">Format</span></span>

<span data-ttu-id="0716c-756">Ocho dígitos seguidos de un carácter</span><span class="sxs-lookup"><span data-stu-id="0716c-756">Eight digits followed by one character</span></span>
  
### <a name="pattern"></a><span data-ttu-id="0716c-757">Patrón</span><span class="sxs-lookup"><span data-stu-id="0716c-757">Pattern</span></span>

<span data-ttu-id="0716c-758">Ocho dígitos seguidos de un carácter:</span><span class="sxs-lookup"><span data-stu-id="0716c-758">Eight digits followed by one character:</span></span>
  
-  <span data-ttu-id="0716c-759">Ocho dígitos</span><span class="sxs-lookup"><span data-stu-id="0716c-759">Eight digits</span></span> 
    
- <span data-ttu-id="0716c-760">Un dígito o letra (no distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="0716c-760">One digit or letter (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="0716c-761">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="0716c-761">Checksum</span></span>

<span data-ttu-id="0716c-762">Sí</span><span class="sxs-lookup"><span data-stu-id="0716c-762">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="0716c-763">Definición</span><span class="sxs-lookup"><span data-stu-id="0716c-763">Definition</span></span>

<span data-ttu-id="0716c-764">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="0716c-764">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="0716c-765">La función `Func_spain_eu_driver's_license_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="0716c-765">The function  `Func_spain_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="0716c-766">Se encuentra una `Keywords_spain_eu_driver's_license_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="0716c-766">A keyword from  `Keywords_spain_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spain_eu_driver's_license_number" />
          <Match idRef="Keywords_spain_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="0716c-767">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="0716c-767">Keywords</span></span>

<span data-ttu-id="0716c-768">| |</span><span class="sxs-lookup"><span data-stu-id="0716c-768"></span></span>
|<span data-ttu-id="0716c-769">**Keywords_spain_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="0716c-769">**Keywords_spain_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="0716c-770">dlno#</span><span class="sxs-lookup"><span data-stu-id="0716c-770">dlno#</span></span>  <br/> <span data-ttu-id="0716c-771">listas</span><span class="sxs-lookup"><span data-stu-id="0716c-771">dl#</span></span>  <br/> <span data-ttu-id="0716c-772">Lic de drivers.</span><span class="sxs-lookup"><span data-stu-id="0716c-772">drivers lic.</span></span>  <br/> <span data-ttu-id="0716c-773">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="0716c-773">driver licence</span></span>  <br/> <span data-ttu-id="0716c-774">driver license</span><span class="sxs-lookup"><span data-stu-id="0716c-774">driver license</span></span>  <br/> <span data-ttu-id="0716c-775">drivers licence</span><span class="sxs-lookup"><span data-stu-id="0716c-775">drivers licence</span></span>  <br/> <span data-ttu-id="0716c-776">drivers license</span><span class="sxs-lookup"><span data-stu-id="0716c-776">drivers license</span></span>  <br/> <span data-ttu-id="0716c-777">driver's licence</span><span class="sxs-lookup"><span data-stu-id="0716c-777">driver's licence</span></span>  <br/> <span data-ttu-id="0716c-778">driver's license</span><span class="sxs-lookup"><span data-stu-id="0716c-778">driver's license</span></span>  <br/> <span data-ttu-id="0716c-779">driving licence</span><span class="sxs-lookup"><span data-stu-id="0716c-779">driving licence</span></span>  <br/> <span data-ttu-id="0716c-780">driving license</span><span class="sxs-lookup"><span data-stu-id="0716c-780">driving license</span></span>  <br/> <span data-ttu-id="0716c-781">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="0716c-781">driver licence number</span></span>  <br/> <span data-ttu-id="0716c-782">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="0716c-782">driver license number</span></span>  <br/> <span data-ttu-id="0716c-783">número de licencia de drivers</span><span class="sxs-lookup"><span data-stu-id="0716c-783">drivers licence number</span></span>  <br/> <span data-ttu-id="0716c-784">número de licencia de drivers</span><span class="sxs-lookup"><span data-stu-id="0716c-784">drivers license number</span></span>  <br/> <span data-ttu-id="0716c-785">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="0716c-785">driver's licence number</span></span>  <br/> <span data-ttu-id="0716c-786">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="0716c-786">driver's license number</span></span>  <br/> <span data-ttu-id="0716c-787">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="0716c-787">driving licence number</span></span>  <br/> <span data-ttu-id="0716c-788">número de licencia de conducir</span><span class="sxs-lookup"><span data-stu-id="0716c-788">driving license number</span></span>  <br/> <span data-ttu-id="0716c-789">permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="0716c-789">driving permit</span></span>  <br/> <span data-ttu-id="0716c-790">número de permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="0716c-790">driving permit number</span></span>  <br/> <span data-ttu-id="0716c-791">permisos de conducción</span><span class="sxs-lookup"><span data-stu-id="0716c-791">permiso de conducción</span></span>  <br/> <span data-ttu-id="0716c-792">permisos conducción</span><span class="sxs-lookup"><span data-stu-id="0716c-792">permiso conducción</span></span>  <br/> <span data-ttu-id="0716c-793">número de licencia conducir</span><span class="sxs-lookup"><span data-stu-id="0716c-793">número licencia conducir</span></span>  <br/> <span data-ttu-id="0716c-794">número de cuaderno de conducir</span><span class="sxs-lookup"><span data-stu-id="0716c-794">número de carnet de conducir</span></span>  <br/> <span data-ttu-id="0716c-795">número conducir de cuaderno</span><span class="sxs-lookup"><span data-stu-id="0716c-795">número carnet conducir</span></span>  <br/> <span data-ttu-id="0716c-796">licenciar conducir</span><span class="sxs-lookup"><span data-stu-id="0716c-796">licencia conducir</span></span>  <br/> <span data-ttu-id="0716c-797">número de permisos de conducir</span><span class="sxs-lookup"><span data-stu-id="0716c-797">número de permiso de conducir</span></span>  <br/> <span data-ttu-id="0716c-798">número de permisos conducir</span><span class="sxs-lookup"><span data-stu-id="0716c-798">número de permiso conducir</span></span>  <br/> <span data-ttu-id="0716c-799">número permisos conducir</span><span class="sxs-lookup"><span data-stu-id="0716c-799">número permiso conducir</span></span>  <br/> <span data-ttu-id="0716c-800">permisos conducir</span><span class="sxs-lookup"><span data-stu-id="0716c-800">permiso conducir</span></span>  <br/> <span data-ttu-id="0716c-801">licencia de manejo</span><span class="sxs-lookup"><span data-stu-id="0716c-801">licencia de manejo</span></span>  <br/> <span data-ttu-id="0716c-802">el cuaderno de conducir</span><span class="sxs-lookup"><span data-stu-id="0716c-802">el carnet de conducir</span></span>  <br/> <span data-ttu-id="0716c-803">conducir del cuaderno</span><span class="sxs-lookup"><span data-stu-id="0716c-803">carnet conducir</span></span>  <br/> |
   
## <a name="sweden"></a><span data-ttu-id="0716c-804">Suecia</span><span class="sxs-lookup"><span data-stu-id="0716c-804">Sweden</span></span>

### <a name="format"></a><span data-ttu-id="0716c-805">Formato</span><span class="sxs-lookup"><span data-stu-id="0716c-805">Format</span></span>

<span data-ttu-id="0716c-806">Diez dígitos que contienen un guión</span><span class="sxs-lookup"><span data-stu-id="0716c-806">Ten digits containing a hyphen</span></span>
  
### <a name="pattern"></a><span data-ttu-id="0716c-807">Patrón</span><span class="sxs-lookup"><span data-stu-id="0716c-807">Pattern</span></span>

<span data-ttu-id="0716c-808">Diez dígitos que contienen un guión:</span><span class="sxs-lookup"><span data-stu-id="0716c-808">Ten digits containing a hyphen:</span></span>
  
-  <span data-ttu-id="0716c-809">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="0716c-809">Six digits</span></span> 
    
- <span data-ttu-id="0716c-810">Un guión</span><span class="sxs-lookup"><span data-stu-id="0716c-810">A hyphen</span></span>
    
- <span data-ttu-id="0716c-811">Cuatro dígitos</span><span class="sxs-lookup"><span data-stu-id="0716c-811">Four digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="0716c-812">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="0716c-812">Checksum</span></span>

<span data-ttu-id="0716c-813">No</span><span class="sxs-lookup"><span data-stu-id="0716c-813">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="0716c-814">Definición</span><span class="sxs-lookup"><span data-stu-id="0716c-814">Definition</span></span>

<span data-ttu-id="0716c-815">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="0716c-815">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="0716c-816">La expresión `Regex_sweden_eu_driver's_license_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="0716c-816">The regular expression  `Regex_sweden_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="0716c-817">Se encuentra una `Keywords_sweden_eu_driver's_license_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="0716c-817">A keyword from  `Keywords_sweden_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_sweden_eu_driver's_license_number" />
          <Match idRef="Keywords_sweden_eu_driver's_license_number" />
        </Pattern>
</Entity> 
```

### <a name="keywords"></a><span data-ttu-id="0716c-818">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="0716c-818">Keywords</span></span>

<span data-ttu-id="0716c-819">| |</span><span class="sxs-lookup"><span data-stu-id="0716c-819"></span></span>
|<span data-ttu-id="0716c-820">**Keywords_sweden_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="0716c-820">**Keywords_sweden_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="0716c-821">listas</span><span class="sxs-lookup"><span data-stu-id="0716c-821">dl#</span></span>  <br/> <span data-ttu-id="0716c-822">driver license</span><span class="sxs-lookup"><span data-stu-id="0716c-822">driver license</span></span>  <br/> <span data-ttu-id="0716c-823">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="0716c-823">driver license number</span></span>  <br/> <span data-ttu-id="0716c-824">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="0716c-824">driver licence</span></span>  <br/> <span data-ttu-id="0716c-825">Lic de drivers.</span><span class="sxs-lookup"><span data-stu-id="0716c-825">drivers lic.</span></span>  <br/> <span data-ttu-id="0716c-826">drivers license</span><span class="sxs-lookup"><span data-stu-id="0716c-826">drivers license</span></span>  <br/> <span data-ttu-id="0716c-827">drivers licence</span><span class="sxs-lookup"><span data-stu-id="0716c-827">drivers licence</span></span>  <br/> <span data-ttu-id="0716c-828">driver's license</span><span class="sxs-lookup"><span data-stu-id="0716c-828">driver's license</span></span>  <br/> <span data-ttu-id="0716c-829">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="0716c-829">driver's license number</span></span>  <br/> <span data-ttu-id="0716c-830">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="0716c-830">driver's licence number</span></span>  <br/> <span data-ttu-id="0716c-831">número de licencia de conducir</span><span class="sxs-lookup"><span data-stu-id="0716c-831">driving license number</span></span>  <br/> <span data-ttu-id="0716c-832">dlno#</span><span class="sxs-lookup"><span data-stu-id="0716c-832">dlno#</span></span>  <br/> <span data-ttu-id="0716c-833">körkort</span><span class="sxs-lookup"><span data-stu-id="0716c-833">körkort</span></span>  <br/> |
   
## <a name="uk"></a><span data-ttu-id="0716c-834">LIBRA</span><span class="sxs-lookup"><span data-stu-id="0716c-834">UK</span></span>

<span data-ttu-id="0716c-835">Para obtener más información, consulte la sección "Reino Unido.</span><span class="sxs-lookup"><span data-stu-id="0716c-835">For details, see the section "U.K.</span></span> <span data-ttu-id="0716c-836">Número de permiso de conducir "en [Qué buscan los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="0716c-836">Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="0716c-837">Vea también</span><span class="sxs-lookup"><span data-stu-id="0716c-837">See also</span></span>

[<span data-ttu-id="0716c-838">Qué buscan los tipos de información confidencial</span><span class="sxs-lookup"><span data-stu-id="0716c-838">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

