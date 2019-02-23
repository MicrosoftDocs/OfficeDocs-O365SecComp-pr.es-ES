---
title: Número de permiso de conducción de la UE
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/17/2018
ms.audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: c3923cd3-ec84-435f-bf41-cadc37996a4b
description: En este tema se muestra qué busca una directiva de prevención de pérdida de datos (DLP) cuando detecta el tipo de información confidencial del número de licencia de conductor de la UE. Este tipo de información confidencial define distintos patrones, palabras clave y otras pruebas para cada país.
ms.openlocfilehash: 86be7b52aed7581fd62ab595ac2c4b63ab33aab3
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/23/2019
ms.locfileid: "30217750"
---
# <a name="eu-drivers-license-number"></a><span data-ttu-id="c358f-104">Número de permiso de conducción de la UE</span><span class="sxs-lookup"><span data-stu-id="c358f-104">EU Driver's License Number</span></span>

<span data-ttu-id="c358f-p102">En este tema se muestra qué busca una directiva de prevención de pérdida de datos (DLP) cuando detecta el tipo de información confidencial del número de licencia de conductor de la UE. Este tipo de información confidencial define distintos patrones, palabras clave y otras pruebas para cada país.</span><span class="sxs-lookup"><span data-stu-id="c358f-p102">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Driver's License Number sensitive information type. This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="c358f-107">Austria</span><span class="sxs-lookup"><span data-stu-id="c358f-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="c358f-108">Formato</span><span class="sxs-lookup"><span data-stu-id="c358f-108">Format</span></span>

<span data-ttu-id="c358f-109">Ocho dígitos sin espacios y delimitadores</span><span class="sxs-lookup"><span data-stu-id="c358f-109">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="c358f-110">Patrón</span><span class="sxs-lookup"><span data-stu-id="c358f-110">Pattern</span></span>

<span data-ttu-id="c358f-111">Ocho dígitos</span><span class="sxs-lookup"><span data-stu-id="c358f-111">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="c358f-112">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="c358f-112">Checksum</span></span>

<span data-ttu-id="c358f-113">No</span><span class="sxs-lookup"><span data-stu-id="c358f-113">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="c358f-114">Definición</span><span class="sxs-lookup"><span data-stu-id="c358f-114">Definition</span></span>

<span data-ttu-id="c358f-115">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="c358f-115">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c358f-116">La expresión `Regex_austria_eu_driver's_license_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="c358f-116">The regular expression  `Regex_austria_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c358f-117">Se encuentra una `Keywords_austria_eu_driver's_license_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="c358f-117">A keyword from  `Keywords_austria_eu_driver's_license_number` is found.</span></span> 
    
```
<!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_driver's_license_number" />
          <Match idRef="Keywords_austria_eu_driver's_license_number" />
        </Pattern>
    </Entity>

```

### <a name="keywords"></a><span data-ttu-id="c358f-118">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="c358f-118">Keywords</span></span>

<span data-ttu-id="c358f-119">| |</span><span class="sxs-lookup"><span data-stu-id="c358f-119"></span></span>
|<span data-ttu-id="c358f-120">**Keywords_austria_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="c358f-120">**Keywords_austria_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="c358f-121">dl#</span><span class="sxs-lookup"><span data-stu-id="c358f-121">dl#</span></span>  <br/> <span data-ttu-id="c358f-122">permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="c358f-122">driver license</span></span>  <br/> <span data-ttu-id="c358f-123">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="c358f-123">driver license number</span></span>  <br/> <span data-ttu-id="c358f-124">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="c358f-124">driver licence</span></span>  <br/> <span data-ttu-id="c358f-125">Lic de drivers.</span><span class="sxs-lookup"><span data-stu-id="c358f-125">drivers lic.</span></span>  <br/> <span data-ttu-id="c358f-126">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="c358f-126">drivers license</span></span>  <br/> <span data-ttu-id="c358f-127">permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="c358f-127">driver's licence</span></span>  <br/> <span data-ttu-id="c358f-128">permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="c358f-128">driver's license</span></span>  <br/> <span data-ttu-id="c358f-129">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="c358f-129">driver's license number</span></span>  <br/> <span data-ttu-id="c358f-130">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="c358f-130">driver's licence number</span></span>  <br/>  <span data-ttu-id="c358f-131">número de licencia de conducir</span><span class="sxs-lookup"><span data-stu-id="c358f-131">driving license number</span></span>  <br/> <span data-ttu-id="c358f-132">dlno #</span><span class="sxs-lookup"><span data-stu-id="c358f-132">dlno#</span></span>  <br/> <span data-ttu-id="c358f-133">fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="c358f-133">fuhrerschein</span></span>  <br/> <span data-ttu-id="c358f-134">fuhrerschein Republik Osterreich</span><span class="sxs-lookup"><span data-stu-id="c358f-134">fuhrerschein republik osterreich</span></span>  <br/> |
   
## <a name="belgium"></a><span data-ttu-id="c358f-135">Bélgica</span><span class="sxs-lookup"><span data-stu-id="c358f-135">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="c358f-136">Formato</span><span class="sxs-lookup"><span data-stu-id="c358f-136">Format</span></span>

<span data-ttu-id="c358f-137">10 dígitos sin espacios y delimitadores</span><span class="sxs-lookup"><span data-stu-id="c358f-137">10 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="c358f-138">Patrón</span><span class="sxs-lookup"><span data-stu-id="c358f-138">Pattern</span></span>

<span data-ttu-id="c358f-139">10 dígitos</span><span class="sxs-lookup"><span data-stu-id="c358f-139">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="c358f-140">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="c358f-140">Checksum</span></span>

<span data-ttu-id="c358f-141">No</span><span class="sxs-lookup"><span data-stu-id="c358f-141">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="c358f-142">Definición</span><span class="sxs-lookup"><span data-stu-id="c358f-142">Definition</span></span>

<span data-ttu-id="c358f-143">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="c358f-143">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c358f-144">La expresión `Regex_belgium_eu_driver's_license_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="c358f-144">The regular expression  `Regex_belgium_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c358f-145">Se encuentra una `Keywords_belgium_eu_driver's_license_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="c358f-145">A keyword from  `Keywords_belgium_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_driver's_license_number" />
          <Match idRef="Keywords_belgium_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="c358f-146">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="c358f-146">Keywords</span></span>

<span data-ttu-id="c358f-147">| |</span><span class="sxs-lookup"><span data-stu-id="c358f-147"></span></span>
|<span data-ttu-id="c358f-148">**Keywords__belgium_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="c358f-148">**Keywords__belgium_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="c358f-149">dl#</span><span class="sxs-lookup"><span data-stu-id="c358f-149">dl#</span></span>  <br/> <span data-ttu-id="c358f-150">permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="c358f-150">driver license</span></span>  <br/> <span data-ttu-id="c358f-151">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="c358f-151">driver license number</span></span>  <br/> <span data-ttu-id="c358f-152">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="c358f-152">driver licence</span></span>  <br/> <span data-ttu-id="c358f-153">Lic de drivers.</span><span class="sxs-lookup"><span data-stu-id="c358f-153">drivers lic.</span></span>  <br/> <span data-ttu-id="c358f-154">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="c358f-154">drivers license</span></span>  <br/> <span data-ttu-id="c358f-155">drivers licence</span><span class="sxs-lookup"><span data-stu-id="c358f-155">drivers licence</span></span>  <br/> <span data-ttu-id="c358f-156">permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="c358f-156">driver's license</span></span>  <br/> <span data-ttu-id="c358f-157">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="c358f-157">driver's license number</span></span>  <br/> <span data-ttu-id="c358f-158">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="c358f-158">driver's licence number</span></span>  <br/> <span data-ttu-id="c358f-159">dlno #</span><span class="sxs-lookup"><span data-stu-id="c358f-159">dlno#</span></span>  <br/> <span data-ttu-id="c358f-160">rijbewijs</span><span class="sxs-lookup"><span data-stu-id="c358f-160">rijbewijs</span></span>  <br/> <span data-ttu-id="c358f-161">rijbewijsnummer</span><span class="sxs-lookup"><span data-stu-id="c358f-161">rijbewijsnummer</span></span>  <br/> <span data-ttu-id="c358f-162">führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="c358f-162">führerscheinnummer</span></span>  <br/> <span data-ttu-id="c358f-163">fuhrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="c358f-163">fuhrerscheinnummer</span></span>  <br/> <span data-ttu-id="c358f-164">fuehrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="c358f-164">fuehrerscheinnummer</span></span>  <br/> <span data-ttu-id="c358f-165">Führerschein-NR</span><span class="sxs-lookup"><span data-stu-id="c358f-165">führerschein- nr</span></span>  <br/> <span data-ttu-id="c358f-166">fuehrerschein-NR</span><span class="sxs-lookup"><span data-stu-id="c358f-166">fuehrerschein- Nr</span></span>  <br/> <span data-ttu-id="c358f-167">fuehrerschein-NR</span><span class="sxs-lookup"><span data-stu-id="c358f-167">fuehrerschein- nr</span></span>  <br/> |
   
## <a name="bulgaria"></a><span data-ttu-id="c358f-168">Bulgaria</span><span class="sxs-lookup"><span data-stu-id="c358f-168">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="c358f-169">Formato</span><span class="sxs-lookup"><span data-stu-id="c358f-169">Format</span></span>

<span data-ttu-id="c358f-170">Nueve dígitos sin espacios y delimitadores</span><span class="sxs-lookup"><span data-stu-id="c358f-170">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="c358f-171">Patrón</span><span class="sxs-lookup"><span data-stu-id="c358f-171">Pattern</span></span>

<span data-ttu-id="c358f-172">Nueve dígitos</span><span class="sxs-lookup"><span data-stu-id="c358f-172">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="c358f-173">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="c358f-173">Checksum</span></span>

<span data-ttu-id="c358f-174">No</span><span class="sxs-lookup"><span data-stu-id="c358f-174">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="c358f-175">Definición</span><span class="sxs-lookup"><span data-stu-id="c358f-175">Definition</span></span>

<span data-ttu-id="c358f-176">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="c358f-176">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c358f-177">La expresión `Regex_bulgaria_eu_driver's_license_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="c358f-177">The regular expression  `Regex_bulgaria_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c358f-178">Se encuentra una `Keywords_bulgaria_eu_driver's_license_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="c358f-178">A keyword from  `Keywords_bulgaria_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
             <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_driver's_license_number" />
          <Match idRef="Keywords_bulgaria_eu_driver's_license_number" />
        </Pattern> 
</Entity>    

```

### <a name="keywords"></a><span data-ttu-id="c358f-179">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="c358f-179">Keywords</span></span>

<span data-ttu-id="c358f-180">| |</span><span class="sxs-lookup"><span data-stu-id="c358f-180"></span></span>
|<span data-ttu-id="c358f-181">**Keywords_bulgaria_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="c358f-181">**Keywords_bulgaria_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="c358f-182">dl#</span><span class="sxs-lookup"><span data-stu-id="c358f-182">dl#</span></span>  <br/> <span data-ttu-id="c358f-183">permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="c358f-183">driver license</span></span>  <br/> <span data-ttu-id="c358f-184">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="c358f-184">driver license number</span></span>  <br/> <span data-ttu-id="c358f-185">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="c358f-185">driver licence</span></span>  <br/> <span data-ttu-id="c358f-186">Lic de drivers.</span><span class="sxs-lookup"><span data-stu-id="c358f-186">drivers lic.</span></span>  <br/> <span data-ttu-id="c358f-187">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="c358f-187">drivers license</span></span>  <br/> <span data-ttu-id="c358f-188">drivers licence</span><span class="sxs-lookup"><span data-stu-id="c358f-188">drivers licence</span></span>  <br/> <span data-ttu-id="c358f-189">permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="c358f-189">driver's license</span></span>  <br/> <span data-ttu-id="c358f-190">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="c358f-190">driver's license number</span></span>  <br/> <span data-ttu-id="c358f-191">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="c358f-191">driver's licence number</span></span>  <br/> <span data-ttu-id="c358f-192">número de licencia de conducir</span><span class="sxs-lookup"><span data-stu-id="c358f-192">driving license number</span></span>  <br/> <span data-ttu-id="c358f-193">dlno #</span><span class="sxs-lookup"><span data-stu-id="c358f-193">dlno#</span></span>  <br/> <span data-ttu-id="c358f-194">свидетелство за управление на мпс</span><span class="sxs-lookup"><span data-stu-id="c358f-194">свидетелство за управление на мпс</span></span>  <br/> <span data-ttu-id="c358f-195">свидетелство за управление на моторно превозно средство</span><span class="sxs-lookup"><span data-stu-id="c358f-195">свидетелство за управление на моторно превозно средство</span></span>  <br/> <span data-ttu-id="c358f-196">сумпс</span><span class="sxs-lookup"><span data-stu-id="c358f-196">сумпс</span></span>  <br/> <span data-ttu-id="c358f-197">шофьорска книжка</span><span class="sxs-lookup"><span data-stu-id="c358f-197">шофьорска книжка</span></span>  <br/> |
   
## <a name="croatia"></a><span data-ttu-id="c358f-198">Croacia</span><span class="sxs-lookup"><span data-stu-id="c358f-198">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="c358f-199">Formato</span><span class="sxs-lookup"><span data-stu-id="c358f-199">Format</span></span>

<span data-ttu-id="c358f-200">Ocho dígitos sin espacios y delimitadores</span><span class="sxs-lookup"><span data-stu-id="c358f-200">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="c358f-201">Patrón</span><span class="sxs-lookup"><span data-stu-id="c358f-201">Pattern</span></span>

<span data-ttu-id="c358f-202">Ocho dígitos</span><span class="sxs-lookup"><span data-stu-id="c358f-202">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="c358f-203">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="c358f-203">Checksum</span></span>

<span data-ttu-id="c358f-204">No</span><span class="sxs-lookup"><span data-stu-id="c358f-204">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="c358f-205">Definición</span><span class="sxs-lookup"><span data-stu-id="c358f-205">Definition</span></span>

<span data-ttu-id="c358f-206">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="c358f-206">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c358f-207">La expresión `Regex_croatia_eu_driver's_license_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="c358f-207">The regular expression  `Regex_croatia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c358f-208">Se encuentra una `Keywords_croatia_eu_driver's_license_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="c358f-208">A keyword from  `Keywords_croatia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_driver's_license_number" />
          <Match idRef="Keywords_croatia_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="c358f-209">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="c358f-209">Keywords</span></span>

<span data-ttu-id="c358f-210">| |</span><span class="sxs-lookup"><span data-stu-id="c358f-210"></span></span>
|<span data-ttu-id="c358f-211">**Keywords_croatia_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="c358f-211">**Keywords_croatia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="c358f-212">dl#</span><span class="sxs-lookup"><span data-stu-id="c358f-212">dl#</span></span>  <br/> <span data-ttu-id="c358f-213">permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="c358f-213">driver license</span></span>  <br/> <span data-ttu-id="c358f-214">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="c358f-214">driver license number</span></span>  <br/> <span data-ttu-id="c358f-215">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="c358f-215">driver licence</span></span>  <br/> <span data-ttu-id="c358f-216">Lic de drivers.</span><span class="sxs-lookup"><span data-stu-id="c358f-216">drivers lic.</span></span>  <br/> <span data-ttu-id="c358f-217">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="c358f-217">drivers license</span></span>  <br/> <span data-ttu-id="c358f-218">drivers licence</span><span class="sxs-lookup"><span data-stu-id="c358f-218">drivers licence</span></span>  <br/> <span data-ttu-id="c358f-219">permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="c358f-219">driver's license</span></span>  <br/> <span data-ttu-id="c358f-220">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="c358f-220">driver's license number</span></span>  <br/> <span data-ttu-id="c358f-221">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="c358f-221">driver's licence number</span></span>  <br/> <span data-ttu-id="c358f-222">número de licencia de conducir</span><span class="sxs-lookup"><span data-stu-id="c358f-222">driving license number</span></span>  <br/> <span data-ttu-id="c358f-223">dlno #</span><span class="sxs-lookup"><span data-stu-id="c358f-223">dlno#</span></span>  <br/> <span data-ttu-id="c358f-224">vozačka Dozvola</span><span class="sxs-lookup"><span data-stu-id="c358f-224">vozačka dozvola</span></span>  <br/> |
   
## <a name="cyprus"></a><span data-ttu-id="c358f-225">Chipre</span><span class="sxs-lookup"><span data-stu-id="c358f-225">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="c358f-226">Formato</span><span class="sxs-lookup"><span data-stu-id="c358f-226">Format</span></span>

<span data-ttu-id="c358f-227">12 dígitos sin espacios y delimitadores</span><span class="sxs-lookup"><span data-stu-id="c358f-227">12 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="c358f-228">Patrón</span><span class="sxs-lookup"><span data-stu-id="c358f-228">Pattern</span></span>

<span data-ttu-id="c358f-229">12 dígitos</span><span class="sxs-lookup"><span data-stu-id="c358f-229">12 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="c358f-230">Checksum</span><span class="sxs-lookup"><span data-stu-id="c358f-230">Checksum</span></span>

<span data-ttu-id="c358f-231">No</span><span class="sxs-lookup"><span data-stu-id="c358f-231">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="c358f-232">Definición</span><span class="sxs-lookup"><span data-stu-id="c358f-232">Definition</span></span>

<span data-ttu-id="c358f-233">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="c358f-233">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c358f-234">La expresión `Regex_cyprus_eu_driver's_license_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="c358f-234">The regular expression  `Regex_cyprus_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c358f-235">Se encuentra una `Keywords_cyprus_eu_driver's_license_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="c358f-235">A keyword from  `Keywords_cyprus_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_driver's_license_number" />
          <Match idRef="Keywords_cyprus_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="c358f-236">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="c358f-236">Keywords</span></span>

<span data-ttu-id="c358f-237">| |</span><span class="sxs-lookup"><span data-stu-id="c358f-237"></span></span>
|<span data-ttu-id="c358f-238">**Keywords_cyprus_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="c358f-238">**Keywords_cyprus_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="c358f-239">dl#</span><span class="sxs-lookup"><span data-stu-id="c358f-239">dl#</span></span>  <br/> <span data-ttu-id="c358f-240">permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="c358f-240">driver license</span></span>  <br/> <span data-ttu-id="c358f-241">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="c358f-241">driver license number</span></span>  <br/> <span data-ttu-id="c358f-242">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="c358f-242">driver licence</span></span>  <br/> <span data-ttu-id="c358f-243">Lic de drivers.</span><span class="sxs-lookup"><span data-stu-id="c358f-243">drivers lic.</span></span>  <br/> <span data-ttu-id="c358f-244">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="c358f-244">drivers license</span></span>  <br/> <span data-ttu-id="c358f-245">drivers licence</span><span class="sxs-lookup"><span data-stu-id="c358f-245">drivers licence</span></span>  <br/> <span data-ttu-id="c358f-246">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="c358f-246">driver's license number</span></span>  <br/> <span data-ttu-id="c358f-247">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="c358f-247">driver's licence number</span></span>  <br/> <span data-ttu-id="c358f-248">número de licencia de conducir</span><span class="sxs-lookup"><span data-stu-id="c358f-248">driving license number</span></span>  <br/> <span data-ttu-id="c358f-249">dlno #</span><span class="sxs-lookup"><span data-stu-id="c358f-249">dlno#</span></span>  <br/> <span data-ttu-id="c358f-250">άδεια οδήγησης</span><span class="sxs-lookup"><span data-stu-id="c358f-250">άδεια οδήγησης</span></span>  <br/> |
   
## <a name="czech-republic"></a><span data-ttu-id="c358f-251">Chequia</span><span class="sxs-lookup"><span data-stu-id="c358f-251">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="c358f-252">Formato</span><span class="sxs-lookup"><span data-stu-id="c358f-252">Format</span></span>

<span data-ttu-id="c358f-253">Dos letras seguidas de seis dígitos</span><span class="sxs-lookup"><span data-stu-id="c358f-253">Two letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="c358f-254">Patrón</span><span class="sxs-lookup"><span data-stu-id="c358f-254">Pattern</span></span>

<span data-ttu-id="c358f-255">Ocho letras y dígitos:</span><span class="sxs-lookup"><span data-stu-id="c358f-255">Eight letters and digits:</span></span>
  
- <span data-ttu-id="c358f-256">Dos letras (sin distinción entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="c358f-256">Two letters (not case-sensitive)</span></span>
    
- <span data-ttu-id="c358f-257">Un espacio (opcional) </span><span class="sxs-lookup"><span data-stu-id="c358f-257">A space (optional)</span></span>
    
- <span data-ttu-id="c358f-258">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="c358f-258">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="c358f-259">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="c358f-259">Checksum</span></span>

<span data-ttu-id="c358f-260">No</span><span class="sxs-lookup"><span data-stu-id="c358f-260">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="c358f-261">Definición</span><span class="sxs-lookup"><span data-stu-id="c358f-261">Definition</span></span>

<span data-ttu-id="c358f-262">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="c358f-262">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c358f-263">La expresión `Regex_czech_republic_eu_driver's_license_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="c358f-263">The regular expression  `Regex_czech_republic_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c358f-264">Se encuentra una `Keywords_czech_republic_eu_driver's_license_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="c358f-264">A keyword from  `Keywords_czech_republic_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_driver's_license_number" />
          <Match idRef="Keywords_czech_republic_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="c358f-265">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="c358f-265">Keywords</span></span>

<span data-ttu-id="c358f-266">| |</span><span class="sxs-lookup"><span data-stu-id="c358f-266"></span></span>
|<span data-ttu-id="c358f-267">**Keywords_czech_republic_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="c358f-267">**Keywords_czech_republic_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="c358f-268">dl#</span><span class="sxs-lookup"><span data-stu-id="c358f-268">dl#</span></span>  <br/> <span data-ttu-id="c358f-269">permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="c358f-269">driver license</span></span>  <br/> <span data-ttu-id="c358f-270">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="c358f-270">driver license number</span></span>  <br/> <span data-ttu-id="c358f-271">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="c358f-271">driver licence</span></span>  <br/> <span data-ttu-id="c358f-272">Lic de drivers.</span><span class="sxs-lookup"><span data-stu-id="c358f-272">drivers lic.</span></span>  <br/> <span data-ttu-id="c358f-273">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="c358f-273">drivers license</span></span>  <br/> <span data-ttu-id="c358f-274">drivers licence</span><span class="sxs-lookup"><span data-stu-id="c358f-274">drivers licence</span></span>  <br/> <span data-ttu-id="c358f-275">permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="c358f-275">driver's license</span></span>  <br/> <span data-ttu-id="c358f-276">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="c358f-276">driver's license number</span></span>  <br/> <span data-ttu-id="c358f-277">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="c358f-277">driver's license number</span></span>  <br/> <span data-ttu-id="c358f-278">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="c358f-278">driver's licence number</span></span>  <br/> <span data-ttu-id="c358f-279">número de licencia de conducir</span><span class="sxs-lookup"><span data-stu-id="c358f-279">driving license number</span></span>  <br/> <span data-ttu-id="c358f-280">dlno #</span><span class="sxs-lookup"><span data-stu-id="c358f-280">dlno#</span></span>  <br/> <span data-ttu-id="c358f-281">řidičský prúkaz</span><span class="sxs-lookup"><span data-stu-id="c358f-281">řidičský prúkaz</span></span>  <br/> |
   
## <a name="denmark"></a><span data-ttu-id="c358f-282">Dinamarca</span><span class="sxs-lookup"><span data-stu-id="c358f-282">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="c358f-283">Formato</span><span class="sxs-lookup"><span data-stu-id="c358f-283">Format</span></span>

<span data-ttu-id="c358f-284">Ocho dígitos sin espacios y delimitadores</span><span class="sxs-lookup"><span data-stu-id="c358f-284">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="c358f-285">Patrón</span><span class="sxs-lookup"><span data-stu-id="c358f-285">Pattern</span></span>

<span data-ttu-id="c358f-286">Ocho dígitos</span><span class="sxs-lookup"><span data-stu-id="c358f-286">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="c358f-287">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="c358f-287">Checksum</span></span>

<span data-ttu-id="c358f-288">Sí</span><span class="sxs-lookup"><span data-stu-id="c358f-288">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="c358f-289">Definición</span><span class="sxs-lookup"><span data-stu-id="c358f-289">Definition</span></span>

<span data-ttu-id="c358f-290">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="c358f-290">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c358f-291">La expresión `Regex_denmark_eu_driver's_license_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="c358f-291">The regular expression  `Regex_denmark_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c358f-292">Se encuentra una `Keywords_denmark_eu_driver's_license_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="c358f-292">A keyword from  `Keywords_denmark_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_driver's_license_number" />
          <Match idRef="Keywords_denmark_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="c358f-293">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="c358f-293">Keywords</span></span>

<span data-ttu-id="c358f-294">| |</span><span class="sxs-lookup"><span data-stu-id="c358f-294"></span></span>
|<span data-ttu-id="c358f-295">**Keywords_denmark_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="c358f-295">**Keywords_denmark_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="c358f-296">dl#</span><span class="sxs-lookup"><span data-stu-id="c358f-296">dl#</span></span>  <br/> <span data-ttu-id="c358f-297">permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="c358f-297">driver license</span></span>  <br/> <span data-ttu-id="c358f-298">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="c358f-298">driver license number</span></span>  <br/> <span data-ttu-id="c358f-299">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="c358f-299">driver licence</span></span>  <br/> <span data-ttu-id="c358f-300">Lic de drivers.</span><span class="sxs-lookup"><span data-stu-id="c358f-300">drivers lic.</span></span>  <br/> <span data-ttu-id="c358f-301">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="c358f-301">drivers license</span></span>  <br/> <span data-ttu-id="c358f-302">drivers licence</span><span class="sxs-lookup"><span data-stu-id="c358f-302">drivers licence</span></span>  <br/> <span data-ttu-id="c358f-303">permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="c358f-303">driver's license</span></span>  <br/> <span data-ttu-id="c358f-304">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="c358f-304">driver's license number</span></span>  <br/> <span data-ttu-id="c358f-305">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="c358f-305">driver's licence number</span></span>  <br/> <span data-ttu-id="c358f-306">número de licencia de conducir</span><span class="sxs-lookup"><span data-stu-id="c358f-306">driving license number</span></span>  <br/> <span data-ttu-id="c358f-307">dlno #</span><span class="sxs-lookup"><span data-stu-id="c358f-307">dlno#</span></span>  <br/> <span data-ttu-id="c358f-308">kørekort</span><span class="sxs-lookup"><span data-stu-id="c358f-308">kørekort</span></span>  <br/> <span data-ttu-id="c358f-309">kørekortnummer</span><span class="sxs-lookup"><span data-stu-id="c358f-309">kørekortnummer</span></span>  <br/> |
   
## <a name="estonia"></a><span data-ttu-id="c358f-310">Estonia</span><span class="sxs-lookup"><span data-stu-id="c358f-310">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="c358f-311">Formato</span><span class="sxs-lookup"><span data-stu-id="c358f-311">Format</span></span>

<span data-ttu-id="c358f-312">Dos letras seguidas de seis dígitos</span><span class="sxs-lookup"><span data-stu-id="c358f-312">Two letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="c358f-313">Patrón</span><span class="sxs-lookup"><span data-stu-id="c358f-313">Pattern</span></span>

<span data-ttu-id="c358f-314">Dos letras y seis dígitos:</span><span class="sxs-lookup"><span data-stu-id="c358f-314">Two letters and six digits:</span></span>
  
-  <span data-ttu-id="c358f-315">Las letras "ET" (sin distinción entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="c358f-315">The letters "ET" (not case-sensitive)</span></span> 
    
- <span data-ttu-id="c358f-316">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="c358f-316">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="c358f-317">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="c358f-317">Checksum</span></span>

<span data-ttu-id="c358f-318">No</span><span class="sxs-lookup"><span data-stu-id="c358f-318">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="c358f-319">Definición</span><span class="sxs-lookup"><span data-stu-id="c358f-319">Definition</span></span>

<span data-ttu-id="c358f-320">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="c358f-320">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c358f-321">La expresión `Regex_estonia_eu_driver's_license_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="c358f-321">The regular expression  `Regex_estonia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c358f-322">Se encuentra una `Keywords_estonia_eu_driver's_license_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="c358f-322">A keyword from  `Keywords_estonia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_driver's_license_number" />
          <Match idRef="Keywords_estonia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="c358f-323">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="c358f-323">Keywords</span></span>

<span data-ttu-id="c358f-324">| |</span><span class="sxs-lookup"><span data-stu-id="c358f-324"></span></span>
|<span data-ttu-id="c358f-325">**Keywords_estonia_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="c358f-325">**Keywords_estonia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="c358f-326">dl#</span><span class="sxs-lookup"><span data-stu-id="c358f-326">dl#</span></span>  <br/> <span data-ttu-id="c358f-327">permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="c358f-327">driver license</span></span>  <br/> <span data-ttu-id="c358f-328">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="c358f-328">driver license number</span></span>  <br/> <span data-ttu-id="c358f-329">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="c358f-329">driver license number</span></span>  <br/> <span data-ttu-id="c358f-330">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="c358f-330">driver licence</span></span>  <br/> <span data-ttu-id="c358f-331">Lic de drivers.</span><span class="sxs-lookup"><span data-stu-id="c358f-331">drivers lic.</span></span>  <br/> <span data-ttu-id="c358f-332">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="c358f-332">drivers license</span></span>  <br/> <span data-ttu-id="c358f-333">drivers licence</span><span class="sxs-lookup"><span data-stu-id="c358f-333">drivers licence</span></span>  <br/> <span data-ttu-id="c358f-334">permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="c358f-334">driver's license</span></span>  <br/> <span data-ttu-id="c358f-335">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="c358f-335">driver's license number</span></span>  <br/> <span data-ttu-id="c358f-336">número de licencia de conducir</span><span class="sxs-lookup"><span data-stu-id="c358f-336">driving license number</span></span>  <br/> <span data-ttu-id="c358f-337">dlno #</span><span class="sxs-lookup"><span data-stu-id="c358f-337">dlno#</span></span>  <br/> <span data-ttu-id="c358f-338">
permis de conduire</span><span class="sxs-lookup"><span data-stu-id="c358f-338">permis de conduire</span></span>  <br/> |
   
## <a name="finland"></a><span data-ttu-id="c358f-339">Finlandia</span><span class="sxs-lookup"><span data-stu-id="c358f-339">Finland</span></span>

### <a name="format"></a><span data-ttu-id="c358f-340">Formato</span><span class="sxs-lookup"><span data-stu-id="c358f-340">Format</span></span>

<span data-ttu-id="c358f-341">10 dígitos que contienen un guión</span><span class="sxs-lookup"><span data-stu-id="c358f-341">10 digits containing a hyphen</span></span>
  
### <a name="pattern"></a><span data-ttu-id="c358f-342">Patrón</span><span class="sxs-lookup"><span data-stu-id="c358f-342">Pattern</span></span>

<span data-ttu-id="c358f-343">10 dígitos que contienen un guión:</span><span class="sxs-lookup"><span data-stu-id="c358f-343">10 digits containing a hyphen:</span></span>
  
-  <span data-ttu-id="c358f-344">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="c358f-344">Six digits</span></span> 
    
- <span data-ttu-id="c358f-345">Un guion</span><span class="sxs-lookup"><span data-stu-id="c358f-345">A hyphen</span></span>
    
-  <span data-ttu-id="c358f-346">Cuatro dígitos</span><span class="sxs-lookup"><span data-stu-id="c358f-346">Four digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="c358f-347">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="c358f-347">Checksum</span></span>

<span data-ttu-id="c358f-348">No</span><span class="sxs-lookup"><span data-stu-id="c358f-348">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="c358f-349">Definición</span><span class="sxs-lookup"><span data-stu-id="c358f-349">Definition</span></span>

<span data-ttu-id="c358f-350">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="c358f-350">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c358f-351">La expresión `Regex_finland_eu_driver's_license_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="c358f-351">The regular expression  `Regex_finland_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c358f-352">Se encuentra una `Keywords_finland_eu_driver's_license_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="c358f-352">A keyword from  `Keywords_finland_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_finland_eu_driver's_license_number" />
          <Match idRef="Keywords_finland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="c358f-353">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="c358f-353">Keywords</span></span>

<span data-ttu-id="c358f-354">| |</span><span class="sxs-lookup"><span data-stu-id="c358f-354"></span></span>
|<span data-ttu-id="c358f-355">**Keywords_finland_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="c358f-355">**Keywords_finland_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="c358f-356">dl#</span><span class="sxs-lookup"><span data-stu-id="c358f-356">dl#</span></span>  <br/> <span data-ttu-id="c358f-357">permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="c358f-357">driver license</span></span>  <br/> <span data-ttu-id="c358f-358">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="c358f-358">driver license number</span></span>  <br/> <span data-ttu-id="c358f-359">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="c358f-359">driver licence</span></span>  <br/> <span data-ttu-id="c358f-360">Lic de drivers.</span><span class="sxs-lookup"><span data-stu-id="c358f-360">drivers lic.</span></span>  <br/> <span data-ttu-id="c358f-361">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="c358f-361">drivers license</span></span>  <br/> <span data-ttu-id="c358f-362">drivers licence</span><span class="sxs-lookup"><span data-stu-id="c358f-362">drivers licence</span></span>  <br/> <span data-ttu-id="c358f-363">permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="c358f-363">driver's license</span></span>  <br/> <span data-ttu-id="c358f-364">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="c358f-364">driver's license number</span></span>  <br/> <span data-ttu-id="c358f-365">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="c358f-365">driver's licence number</span></span>  <br/> <span data-ttu-id="c358f-366">número de licencia de conducir</span><span class="sxs-lookup"><span data-stu-id="c358f-366">driving license number</span></span>  <br/> <span data-ttu-id="c358f-367">dlno #</span><span class="sxs-lookup"><span data-stu-id="c358f-367">dlno#</span></span>  <br/> <span data-ttu-id="c358f-368">ajokortti</span><span class="sxs-lookup"><span data-stu-id="c358f-368">ajokortti</span></span>  <br/> |
   
## <a name="france"></a><span data-ttu-id="c358f-369">Francia</span><span class="sxs-lookup"><span data-stu-id="c358f-369">France</span></span>

<span data-ttu-id="c358f-370">Para obtener más información, consulte la sección "número de permiso de conducción de Francia" en [Qué buscan los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="c358f-370">For details, see the section "France Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="germany"></a><span data-ttu-id="c358f-371">Alemania</span><span class="sxs-lookup"><span data-stu-id="c358f-371">Germany</span></span>

<span data-ttu-id="c358f-372">Para obtener más información, consulte la sección "número de permiso de conducción de alemán" en [el que se buscan los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="c358f-372">For details, see the section "German Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="greece"></a><span data-ttu-id="c358f-373">Grecia</span><span class="sxs-lookup"><span data-stu-id="c358f-373">Greece</span></span>

### <a name="format"></a><span data-ttu-id="c358f-374">Formato</span><span class="sxs-lookup"><span data-stu-id="c358f-374">Format</span></span>

<span data-ttu-id="c358f-375">Nueve dígitos sin espacios y delimitadores</span><span class="sxs-lookup"><span data-stu-id="c358f-375">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="c358f-376">Patrón</span><span class="sxs-lookup"><span data-stu-id="c358f-376">Pattern</span></span>

 <span data-ttu-id="c358f-377">Nueve dígitos</span><span class="sxs-lookup"><span data-stu-id="c358f-377">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="c358f-378">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="c358f-378">Checksum</span></span>

<span data-ttu-id="c358f-379">No</span><span class="sxs-lookup"><span data-stu-id="c358f-379">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="c358f-380">Definición</span><span class="sxs-lookup"><span data-stu-id="c358f-380">Definition</span></span>

<span data-ttu-id="c358f-381">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="c358f-381">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c358f-382">La expresión `Regex_greece_eu_driver's_license_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="c358f-382">The regular expression  `Regex_greece_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c358f-383">Se encuentra una `Keywords_greece_eu_driver's_license_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="c358f-383">A keyword from  `Keywords_greece_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_driver's_license_number" />
          <Match idRef="Keywords_greece_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="c358f-384">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="c358f-384">Keywords</span></span>

<span data-ttu-id="c358f-385">| |</span><span class="sxs-lookup"><span data-stu-id="c358f-385"></span></span>
|<span data-ttu-id="c358f-386">**Keywords_greece_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="c358f-386">**Keywords_greece_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="c358f-387">Biblioteca</span><span class="sxs-lookup"><span data-stu-id="c358f-387">dlL#</span></span>  <br/> <span data-ttu-id="c358f-388">permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="c358f-388">driver license</span></span>  <br/> <span data-ttu-id="c358f-389">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="c358f-389">driver license number</span></span>  <br/> <span data-ttu-id="c358f-390">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="c358f-390">driver licence</span></span>  <br/> <span data-ttu-id="c358f-391">Lic de drivers.</span><span class="sxs-lookup"><span data-stu-id="c358f-391">drivers lic.</span></span>  <br/> <span data-ttu-id="c358f-392">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="c358f-392">drivers license</span></span>  <br/> <span data-ttu-id="c358f-393">drivers licence</span><span class="sxs-lookup"><span data-stu-id="c358f-393">drivers licence</span></span>  <br/> <span data-ttu-id="c358f-394">permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="c358f-394">driver's license</span></span>  <br/> <span data-ttu-id="c358f-395">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="c358f-395">driver's license number</span></span>  <br/> <span data-ttu-id="c358f-396">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="c358f-396">driver's licence number</span></span>  <br/> <span data-ttu-id="c358f-397">número de licencia de conducir</span><span class="sxs-lookup"><span data-stu-id="c358f-397">driving license number</span></span>  <br/> <span data-ttu-id="c358f-398">dlno #</span><span class="sxs-lookup"><span data-stu-id="c358f-398">dlno#</span></span>  <br/> <span data-ttu-id="c358f-399">δεια οδήγησης</span><span class="sxs-lookup"><span data-stu-id="c358f-399">δεια οδήγησης</span></span>  <br/> <span data-ttu-id="c358f-400">Adeia odigisis</span><span class="sxs-lookup"><span data-stu-id="c358f-400">Adeia odigisis</span></span>  <br/> |
   
## <a name="hungary"></a><span data-ttu-id="c358f-401">Hungría</span><span class="sxs-lookup"><span data-stu-id="c358f-401">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="c358f-402">Formato</span><span class="sxs-lookup"><span data-stu-id="c358f-402">Format</span></span>

<span data-ttu-id="c358f-403">Dos letras seguidas de seis dígitos</span><span class="sxs-lookup"><span data-stu-id="c358f-403">Two letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="c358f-404">Patrón</span><span class="sxs-lookup"><span data-stu-id="c358f-404">Pattern</span></span>

<span data-ttu-id="c358f-405">Dos letras y seis dígitos:</span><span class="sxs-lookup"><span data-stu-id="c358f-405">Two letters and six digits:</span></span>
  
-  <span data-ttu-id="c358f-406">Dos letras (sin distinción entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="c358f-406">Two letters (not case-sensitive)</span></span> 
    
- <span data-ttu-id="c358f-407">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="c358f-407">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="c358f-408">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="c358f-408">Checksum</span></span>

<span data-ttu-id="c358f-409">No</span><span class="sxs-lookup"><span data-stu-id="c358f-409">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="c358f-410">Definición</span><span class="sxs-lookup"><span data-stu-id="c358f-410">Definition</span></span>

<span data-ttu-id="c358f-411">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="c358f-411">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c358f-412">La expresión `Regex_hungary_eu_driver's_license_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="c358f-412">The regular expression  `Regex_hungary_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c358f-413">Se encuentra una `Keywords_hungary_eu_driver's_license_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="c358f-413">A keyword from  `Keywords_hungary_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_driver's_license_number" />
          <Match idRef="Keywords_hungary_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="c358f-414">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="c358f-414">Keywords</span></span>

<span data-ttu-id="c358f-415">| |</span><span class="sxs-lookup"><span data-stu-id="c358f-415"></span></span>
|<span data-ttu-id="c358f-416">**Keywords_hungary_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="c358f-416">**Keywords_hungary_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="c358f-417">dl#</span><span class="sxs-lookup"><span data-stu-id="c358f-417">dl#</span></span>  <br/> <span data-ttu-id="c358f-418">permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="c358f-418">driver license</span></span>  <br/> <span data-ttu-id="c358f-419">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="c358f-419">driver license number</span></span>  <br/> <span data-ttu-id="c358f-420">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="c358f-420">driver licence</span></span>  <br/> <span data-ttu-id="c358f-421">Lic de drivers.</span><span class="sxs-lookup"><span data-stu-id="c358f-421">drivers lic.</span></span>  <br/> <span data-ttu-id="c358f-422">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="c358f-422">drivers license</span></span>  <br/> <span data-ttu-id="c358f-423">drivers licence</span><span class="sxs-lookup"><span data-stu-id="c358f-423">drivers licence</span></span>  <br/> <span data-ttu-id="c358f-424">permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="c358f-424">driver's license</span></span>  <br/> <span data-ttu-id="c358f-425">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="c358f-425">driver's license number</span></span>  <br/> <span data-ttu-id="c358f-426">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="c358f-426">driver's licence number</span></span>  <br/> <span data-ttu-id="c358f-427">número de licencia de conducir</span><span class="sxs-lookup"><span data-stu-id="c358f-427">driving license number</span></span>  <br/> <span data-ttu-id="c358f-428">dlno #</span><span class="sxs-lookup"><span data-stu-id="c358f-428">dlno#</span></span>  <br/> <span data-ttu-id="c358f-429">vezetoi engedely</span><span class="sxs-lookup"><span data-stu-id="c358f-429">vezetoi engedely</span></span>  <br/> |
   
## <a name="ireland"></a><span data-ttu-id="c358f-430">Irlanda</span><span class="sxs-lookup"><span data-stu-id="c358f-430">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="c358f-431">Formato</span><span class="sxs-lookup"><span data-stu-id="c358f-431">Format</span></span>

<span data-ttu-id="c358f-432">Seis dígitos seguidos de cuatro letras</span><span class="sxs-lookup"><span data-stu-id="c358f-432">Six digits followed by four letters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="c358f-433">Patrón</span><span class="sxs-lookup"><span data-stu-id="c358f-433">Pattern</span></span>

<span data-ttu-id="c358f-434">Seis dígitos y cuatro letras:</span><span class="sxs-lookup"><span data-stu-id="c358f-434">Six digits and four letters:</span></span>
  
- <span data-ttu-id="c358f-435">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="c358f-435">Six digits</span></span>
    
- <span data-ttu-id="c358f-436">Cuatro letras (sin distinción entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="c358f-436">Four letters (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="c358f-437">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="c358f-437">Checksum</span></span>

<span data-ttu-id="c358f-438">No</span><span class="sxs-lookup"><span data-stu-id="c358f-438">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="c358f-439">Definición</span><span class="sxs-lookup"><span data-stu-id="c358f-439">Definition</span></span>

<span data-ttu-id="c358f-440">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="c358f-440">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c358f-441">La expresión `Regex_ireland_eu_driver's_license_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="c358f-441">The regular expression  `Regex_ireland_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c358f-442">Se encuentra una `Keywords_ireland_eu_driver's_license_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="c358f-442">A keyword from  `Keywords_ireland_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_driver's_license_number" />
          <Match idRef="Keywords_ireland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="c358f-443">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="c358f-443">Keywords</span></span>

<span data-ttu-id="c358f-444">| |</span><span class="sxs-lookup"><span data-stu-id="c358f-444"></span></span>
|<span data-ttu-id="c358f-445">**Keywords_ireland_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="c358f-445">**Keywords_ireland_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="c358f-446">dl#</span><span class="sxs-lookup"><span data-stu-id="c358f-446">dl#</span></span>  <br/> <span data-ttu-id="c358f-447">permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="c358f-447">driver license</span></span>  <br/> <span data-ttu-id="c358f-448">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="c358f-448">driver license number</span></span>  <br/> <span data-ttu-id="c358f-449">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="c358f-449">driver licence</span></span>  <br/> <span data-ttu-id="c358f-450">Lic de drivers.</span><span class="sxs-lookup"><span data-stu-id="c358f-450">drivers lic.</span></span>  <br/> <span data-ttu-id="c358f-451">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="c358f-451">drivers license</span></span>  <br/> <span data-ttu-id="c358f-452">drivers licence</span><span class="sxs-lookup"><span data-stu-id="c358f-452">drivers licence</span></span>  <br/> <span data-ttu-id="c358f-453">permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="c358f-453">driver's license</span></span>  <br/> <span data-ttu-id="c358f-454">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="c358f-454">driver's license number</span></span>  <br/> <span data-ttu-id="c358f-455">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="c358f-455">driver's licence number</span></span>  <br/> <span data-ttu-id="c358f-456">número de licencia de conducir</span><span class="sxs-lookup"><span data-stu-id="c358f-456">driving license number</span></span>  <br/> <span data-ttu-id="c358f-457">dlno #</span><span class="sxs-lookup"><span data-stu-id="c358f-457">dlno#</span></span>  <br/> <span data-ttu-id="c358f-458">ceadúnas tiomána</span><span class="sxs-lookup"><span data-stu-id="c358f-458">ceadúnas tiomána</span></span>  <br/> |
   
## <a name="italy"></a><span data-ttu-id="c358f-459">Italia</span><span class="sxs-lookup"><span data-stu-id="c358f-459">Italy</span></span>

<span data-ttu-id="c358f-460">Para obtener más información, consulte la sección "número de licencia de conducción de Italia" en el [que se buscan los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="c358f-460">For details, see the section "Italy Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="latvia"></a><span data-ttu-id="c358f-461">Letonia</span><span class="sxs-lookup"><span data-stu-id="c358f-461">Latvia</span></span>

### <a name="format"></a><span data-ttu-id="c358f-462">Formato</span><span class="sxs-lookup"><span data-stu-id="c358f-462">Format</span></span>

<span data-ttu-id="c358f-463">Tres letras seguidas de seis dígitos</span><span class="sxs-lookup"><span data-stu-id="c358f-463">Three letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="c358f-464">Patrón</span><span class="sxs-lookup"><span data-stu-id="c358f-464">Pattern</span></span>

<span data-ttu-id="c358f-465">Tres letras y seis dígitos:</span><span class="sxs-lookup"><span data-stu-id="c358f-465">Three letters and six digits:</span></span>
  
-  <span data-ttu-id="c358f-466">Tres letras (sin distinción entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="c358f-466">Three letters (not case-sensitive)</span></span> 
    
- <span data-ttu-id="c358f-467">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="c358f-467">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="c358f-468">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="c358f-468">Checksum</span></span>

<span data-ttu-id="c358f-469">No</span><span class="sxs-lookup"><span data-stu-id="c358f-469">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="c358f-470">Definición</span><span class="sxs-lookup"><span data-stu-id="c358f-470">Definition</span></span>

<span data-ttu-id="c358f-471">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="c358f-471">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c358f-472">La expresión `Regex_latvia_eu_driver's_license_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="c358f-472">The regular expression  `Regex_latvia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c358f-473">Se encuentra una `Keywords_latvia_eu_driver's_license_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="c358f-473">A keyword from  `Keywords_latvia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_driver's_license_number" />
          <Match idRef="Keywords_latvia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="c358f-474">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="c358f-474">Keywords</span></span>

<span data-ttu-id="c358f-475">| |</span><span class="sxs-lookup"><span data-stu-id="c358f-475"></span></span>
|<span data-ttu-id="c358f-476">**Keywords_latvia_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="c358f-476">**Keywords_latvia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="c358f-477">dl#</span><span class="sxs-lookup"><span data-stu-id="c358f-477">dl#</span></span>  <br/> <span data-ttu-id="c358f-478">permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="c358f-478">driver license</span></span>  <br/> <span data-ttu-id="c358f-479">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="c358f-479">driver license number</span></span>  <br/> <span data-ttu-id="c358f-480">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="c358f-480">driver licence</span></span>  <br/> <span data-ttu-id="c358f-481">Lic de drivers.</span><span class="sxs-lookup"><span data-stu-id="c358f-481">drivers lic.</span></span>  <br/> <span data-ttu-id="c358f-482">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="c358f-482">drivers license</span></span>  <br/> <span data-ttu-id="c358f-483">drivers licence</span><span class="sxs-lookup"><span data-stu-id="c358f-483">drivers licence</span></span>  <br/> <span data-ttu-id="c358f-484">permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="c358f-484">driver's license</span></span>  <br/> <span data-ttu-id="c358f-485">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="c358f-485">driver's license number</span></span>  <br/> <span data-ttu-id="c358f-486">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="c358f-486">driver's licence number</span></span>  <br/> <span data-ttu-id="c358f-487">número de licencia de conducir</span><span class="sxs-lookup"><span data-stu-id="c358f-487">driving license number</span></span>  <br/> <span data-ttu-id="c358f-488">dlno #</span><span class="sxs-lookup"><span data-stu-id="c358f-488">dlno#</span></span>  <br/> <span data-ttu-id="c358f-489">autovadītāja apliecība</span><span class="sxs-lookup"><span data-stu-id="c358f-489">autovadītāja apliecība</span></span>  <br/> |
   
## <a name="lithuania"></a><span data-ttu-id="c358f-490">Lituania</span><span class="sxs-lookup"><span data-stu-id="c358f-490">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="c358f-491">Formato</span><span class="sxs-lookup"><span data-stu-id="c358f-491">Format</span></span>

<span data-ttu-id="c358f-492">Ocho dígitos sin espacios y delimitadores</span><span class="sxs-lookup"><span data-stu-id="c358f-492">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="c358f-493">Patrón</span><span class="sxs-lookup"><span data-stu-id="c358f-493">Pattern</span></span>

 <span data-ttu-id="c358f-494">Ocho dígitos</span><span class="sxs-lookup"><span data-stu-id="c358f-494">Eight digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="c358f-495">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="c358f-495">Checksum</span></span>

<span data-ttu-id="c358f-496">No</span><span class="sxs-lookup"><span data-stu-id="c358f-496">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="c358f-497">Definición</span><span class="sxs-lookup"><span data-stu-id="c358f-497">Definition</span></span>

<span data-ttu-id="c358f-498">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="c358f-498">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c358f-499">La expresión `Regex_lithuania_eu_driver's_license_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="c358f-499">The regular expression  `Regex_lithuania_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c358f-500">Se encuentra una `Keywords_lithuania_eu_driver's_license_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="c358f-500">A keyword from  `Keywords_lithuania_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_driver's_license_number" />
          <Match idRef="Keywords_lithuania_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="c358f-501">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="c358f-501">Keywords</span></span>

<span data-ttu-id="c358f-502">| |</span><span class="sxs-lookup"><span data-stu-id="c358f-502"></span></span>
|<span data-ttu-id="c358f-503">**Keywords_lithuania_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="c358f-503">**Keywords_lithuania_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="c358f-504">dl#</span><span class="sxs-lookup"><span data-stu-id="c358f-504">dl#</span></span>  <br/> <span data-ttu-id="c358f-505">permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="c358f-505">driver license</span></span>  <br/> <span data-ttu-id="c358f-506">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="c358f-506">driver license number</span></span>  <br/> <span data-ttu-id="c358f-507">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="c358f-507">driver licence</span></span>  <br/> <span data-ttu-id="c358f-508">Lic de drivers.</span><span class="sxs-lookup"><span data-stu-id="c358f-508">drivers lic.</span></span>  <br/> <span data-ttu-id="c358f-509">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="c358f-509">drivers license</span></span>  <br/> <span data-ttu-id="c358f-510">drivers licence</span><span class="sxs-lookup"><span data-stu-id="c358f-510">drivers licence</span></span>  <br/> <span data-ttu-id="c358f-511">permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="c358f-511">driver's license</span></span>  <br/> <span data-ttu-id="c358f-512">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="c358f-512">driver's license number</span></span>  <br/> <span data-ttu-id="c358f-513">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="c358f-513">driver's licence number</span></span>  <br/> <span data-ttu-id="c358f-514">número de licencia de conducir</span><span class="sxs-lookup"><span data-stu-id="c358f-514">driving license number</span></span>  <br/> <span data-ttu-id="c358f-515">dlno #</span><span class="sxs-lookup"><span data-stu-id="c358f-515">dlno#</span></span>  <br/> <span data-ttu-id="c358f-516">vairuotojo pažymėjimas</span><span class="sxs-lookup"><span data-stu-id="c358f-516">vairuotojo pažymėjimas</span></span>  <br/> |
   
## <a name="luxemburg"></a><span data-ttu-id="c358f-517">Luxemburgo</span><span class="sxs-lookup"><span data-stu-id="c358f-517">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="c358f-518">Formato</span><span class="sxs-lookup"><span data-stu-id="c358f-518">Format</span></span>

<span data-ttu-id="c358f-519">Seis dígitos sin espacios y delimitadores</span><span class="sxs-lookup"><span data-stu-id="c358f-519">Six digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="c358f-520">Patrón</span><span class="sxs-lookup"><span data-stu-id="c358f-520">Pattern</span></span>

 <span data-ttu-id="c358f-521">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="c358f-521">Six digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="c358f-522">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="c358f-522">Checksum</span></span>

<span data-ttu-id="c358f-523">No</span><span class="sxs-lookup"><span data-stu-id="c358f-523">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="c358f-524">Definición</span><span class="sxs-lookup"><span data-stu-id="c358f-524">Definition</span></span>

<span data-ttu-id="c358f-525">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="c358f-525">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c358f-526">La expresión `Regex_luxemburg_eu_driver's_license_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="c358f-526">The regular expression  `Regex_luxemburg_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c358f-527">Se encuentra una `Keywords_luxemburg_eu_driver's_license_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="c358f-527">A keyword from  `Keywords_luxemburg_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_luxemburg_eu_driver's_license_number" />
          <Match idRef="Keywords_luxemburg_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="c358f-528">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="c358f-528">Keywords</span></span>

<span data-ttu-id="c358f-529">| |</span><span class="sxs-lookup"><span data-stu-id="c358f-529"></span></span>
|<span data-ttu-id="c358f-530">**Keywords_luxemburg_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="c358f-530">**Keywords_luxemburg_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="c358f-531">dl#</span><span class="sxs-lookup"><span data-stu-id="c358f-531">dl#</span></span>  <br/> <span data-ttu-id="c358f-532">permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="c358f-532">driver license</span></span>  <br/> <span data-ttu-id="c358f-533">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="c358f-533">driver license number</span></span>  <br/> <span data-ttu-id="c358f-534">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="c358f-534">driver licence</span></span>  <br/> <span data-ttu-id="c358f-535">Lic de drivers.</span><span class="sxs-lookup"><span data-stu-id="c358f-535">drivers lic.</span></span>  <br/> <span data-ttu-id="c358f-536">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="c358f-536">drivers license</span></span>  <br/> <span data-ttu-id="c358f-537">drivers licence</span><span class="sxs-lookup"><span data-stu-id="c358f-537">drivers licence</span></span>  <br/> <span data-ttu-id="c358f-538">permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="c358f-538">driver's license</span></span>  <br/> <span data-ttu-id="c358f-539">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="c358f-539">driver's license number</span></span>  <br/> <span data-ttu-id="c358f-540">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="c358f-540">driver's licence number</span></span>  <br/> <span data-ttu-id="c358f-541">número de licencia de conducir</span><span class="sxs-lookup"><span data-stu-id="c358f-541">driving license number</span></span>  <br/> <span data-ttu-id="c358f-542">dlno #</span><span class="sxs-lookup"><span data-stu-id="c358f-542">dlno#</span></span>  <br/> <span data-ttu-id="c358f-543">fahrerlaubnis</span><span class="sxs-lookup"><span data-stu-id="c358f-543">fahrerlaubnis</span></span>  <br/> |
   
## <a name="malta"></a><span data-ttu-id="c358f-544">Malta</span><span class="sxs-lookup"><span data-stu-id="c358f-544">Malta</span></span>

### <a name="format"></a><span data-ttu-id="c358f-545">Formato</span><span class="sxs-lookup"><span data-stu-id="c358f-545">Format</span></span>

<span data-ttu-id="c358f-546">Combinación de dos caracteres y seis dígitos en el patrón especificado</span><span class="sxs-lookup"><span data-stu-id="c358f-546">Combination of two characters and six digits in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="c358f-547">Patrón</span><span class="sxs-lookup"><span data-stu-id="c358f-547">Pattern</span></span>

<span data-ttu-id="c358f-548">Combinación de dos caracteres y seis dígitos:</span><span class="sxs-lookup"><span data-stu-id="c358f-548">Combination of two characters and six digits:</span></span>
  
- <span data-ttu-id="c358f-549">Dos caracteres (dígitos o letras, no distinguen entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="c358f-549">Two characters (digits or letters, not case-sensitive)</span></span>
    
- <span data-ttu-id="c358f-550">Un espacio (opcional) </span><span class="sxs-lookup"><span data-stu-id="c358f-550">A space (optional)</span></span>
    
- <span data-ttu-id="c358f-551">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="c358f-551">Three digits</span></span>
    
- <span data-ttu-id="c358f-552">Un espacio (opcional) </span><span class="sxs-lookup"><span data-stu-id="c358f-552">A space (optional)</span></span>
    
- <span data-ttu-id="c358f-553">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="c358f-553">Three digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="c358f-554">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="c358f-554">Checksum</span></span>

<span data-ttu-id="c358f-555">No</span><span class="sxs-lookup"><span data-stu-id="c358f-555">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="c358f-556">Definición</span><span class="sxs-lookup"><span data-stu-id="c358f-556">Definition</span></span>

<span data-ttu-id="c358f-557">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="c358f-557">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c358f-558">La expresión `Regex_malta_eu_driver's_license_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="c358f-558">The regular expression  `Regex_malta_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c358f-559">Se encuentra una `Keywords_malta_eu_driver's_license_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="c358f-559">A keyword from  `Keywords_malta_eu_driver's_license_number` is found.</span></span> 
    
```
<!-- EU Driver's License Number -->
 <Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_driver's_license_number" />
          <Match idRef="Keywords_malta_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="c358f-560">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="c358f-560">Keywords</span></span>

<span data-ttu-id="c358f-561">| |</span><span class="sxs-lookup"><span data-stu-id="c358f-561"></span></span>
|<span data-ttu-id="c358f-562">**Keywords_malta_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="c358f-562">**Keywords_malta_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="c358f-563">dl#</span><span class="sxs-lookup"><span data-stu-id="c358f-563">dl#</span></span>  <br/> <span data-ttu-id="c358f-564">permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="c358f-564">driver license</span></span>  <br/> <span data-ttu-id="c358f-565">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="c358f-565">driver license number</span></span>  <br/> <span data-ttu-id="c358f-566">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="c358f-566">driver licence</span></span>  <br/> <span data-ttu-id="c358f-567">Lic de drivers.</span><span class="sxs-lookup"><span data-stu-id="c358f-567">drivers lic.</span></span>  <br/> <span data-ttu-id="c358f-568">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="c358f-568">drivers license</span></span>  <br/> <span data-ttu-id="c358f-569">drivers licence</span><span class="sxs-lookup"><span data-stu-id="c358f-569">drivers licence</span></span>  <br/> <span data-ttu-id="c358f-570">permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="c358f-570">driver's license</span></span>  <br/> <span data-ttu-id="c358f-571">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="c358f-571">driver's license number</span></span>  <br/> <span data-ttu-id="c358f-572">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="c358f-572">driver's licence number</span></span>  <br/> <span data-ttu-id="c358f-573">número de licencia de conducir</span><span class="sxs-lookup"><span data-stu-id="c358f-573">driving license number</span></span>  <br/> <span data-ttu-id="c358f-574">dlno #</span><span class="sxs-lookup"><span data-stu-id="c358f-574">dlno#</span></span>  <br/> <span data-ttu-id="c358f-575">liċenzja sewqan</span><span class="sxs-lookup"><span data-stu-id="c358f-575">liċenzja tas-sewqan</span></span>  <br/> |
   
## <a name="netherlands"></a><span data-ttu-id="c358f-576">Países Bajos</span><span class="sxs-lookup"><span data-stu-id="c358f-576">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="c358f-577">Formato</span><span class="sxs-lookup"><span data-stu-id="c358f-577">Format</span></span>

<span data-ttu-id="c358f-578">10 dígitos sin espacios y delimitadores</span><span class="sxs-lookup"><span data-stu-id="c358f-578">10 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="c358f-579">Patrón</span><span class="sxs-lookup"><span data-stu-id="c358f-579">Pattern</span></span>

<span data-ttu-id="c358f-580">10 dígitos</span><span class="sxs-lookup"><span data-stu-id="c358f-580">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="c358f-581">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="c358f-581">Checksum</span></span>

<span data-ttu-id="c358f-582">No</span><span class="sxs-lookup"><span data-stu-id="c358f-582">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="c358f-583">Definición</span><span class="sxs-lookup"><span data-stu-id="c358f-583">Definition</span></span>

<span data-ttu-id="c358f-584">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="c358f-584">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c358f-585">La expresión `Regex_netherlands_eu_driver's_license_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="c358f-585">The regular expression  `Regex_netherlands_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c358f-586">Se encuentra una `Keywords_netherlands_eu_driver's_license_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="c358f-586">A keyword from  `Keywords_netherlands_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_driver's_license_number" />
          <Match idRef="Keywords_netherlands_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="c358f-587">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="c358f-587">Keywords</span></span>

<span data-ttu-id="c358f-588">| |</span><span class="sxs-lookup"><span data-stu-id="c358f-588"></span></span>
|<span data-ttu-id="c358f-589">**Keywords_netherlands_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="c358f-589">**Keywords_netherlands_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="c358f-590">dl#</span><span class="sxs-lookup"><span data-stu-id="c358f-590">dl#</span></span>  <br/> <span data-ttu-id="c358f-591">permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="c358f-591">driver license</span></span>  <br/> <span data-ttu-id="c358f-592">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="c358f-592">driver license number</span></span>  <br/> <span data-ttu-id="c358f-593">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="c358f-593">driver licence</span></span>  <br/> <span data-ttu-id="c358f-594">Lic de drivers.</span><span class="sxs-lookup"><span data-stu-id="c358f-594">drivers lic.</span></span>  <br/> <span data-ttu-id="c358f-595">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="c358f-595">drivers license</span></span>  <br/> <span data-ttu-id="c358f-596">drivers licence</span><span class="sxs-lookup"><span data-stu-id="c358f-596">drivers licence</span></span>  <br/> <span data-ttu-id="c358f-597">permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="c358f-597">driver's license</span></span>  <br/> <span data-ttu-id="c358f-598">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="c358f-598">driver's license number</span></span>  <br/> <span data-ttu-id="c358f-599">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="c358f-599">driver's licence number</span></span>  <br/> <span data-ttu-id="c358f-600">número de licencia de conducir</span><span class="sxs-lookup"><span data-stu-id="c358f-600">driving license number</span></span>  <br/> <span data-ttu-id="c358f-601">dlno #</span><span class="sxs-lookup"><span data-stu-id="c358f-601">dlno#</span></span>  <br/> <span data-ttu-id="c358f-602">
permis de conduire</span><span class="sxs-lookup"><span data-stu-id="c358f-602">permis de conduire</span></span>  <br/> <span data-ttu-id="c358f-603">rijbewijs</span><span class="sxs-lookup"><span data-stu-id="c358f-603">rijbewijs</span></span>  <br/> <span data-ttu-id="c358f-604">rijbewijsnummer</span><span class="sxs-lookup"><span data-stu-id="c358f-604">rijbewijsnummer</span></span>  <br/> |
   
## <a name="poland"></a><span data-ttu-id="c358f-605">Polonia</span><span class="sxs-lookup"><span data-stu-id="c358f-605">Poland</span></span>

### <a name="format"></a><span data-ttu-id="c358f-606">Formato</span><span class="sxs-lookup"><span data-stu-id="c358f-606">Format</span></span>

<span data-ttu-id="c358f-607">14 dígitos que contienen 2 barras diagonales</span><span class="sxs-lookup"><span data-stu-id="c358f-607">14 digits containing 2 forward slashes</span></span>
  
### <a name="pattern"></a><span data-ttu-id="c358f-608">Patrón</span><span class="sxs-lookup"><span data-stu-id="c358f-608">Pattern</span></span>

<span data-ttu-id="c358f-609">14 dígitos y 2 barras diagonales:</span><span class="sxs-lookup"><span data-stu-id="c358f-609">14 digits and 2 forward slashes:</span></span>
  
-  <span data-ttu-id="c358f-610">Cinco dígitos</span><span class="sxs-lookup"><span data-stu-id="c358f-610">Five digits</span></span> 
    
- <span data-ttu-id="c358f-611">Una barra diagonal </span><span class="sxs-lookup"><span data-stu-id="c358f-611">A forward slash</span></span>
    
- <span data-ttu-id="c358f-612">Dos dígitos</span><span class="sxs-lookup"><span data-stu-id="c358f-612">Two digits</span></span>
    
- <span data-ttu-id="c358f-613">Una barra diagonal </span><span class="sxs-lookup"><span data-stu-id="c358f-613">A forward slash</span></span>
    
- <span data-ttu-id="c358f-614">Siete dígitos</span><span class="sxs-lookup"><span data-stu-id="c358f-614">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="c358f-615">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="c358f-615">Checksum</span></span>

<span data-ttu-id="c358f-616">No</span><span class="sxs-lookup"><span data-stu-id="c358f-616">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="c358f-617">Definición</span><span class="sxs-lookup"><span data-stu-id="c358f-617">Definition</span></span>

<span data-ttu-id="c358f-618">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="c358f-618">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c358f-619">La expresión `Regex_poland_eu_driver's_license_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="c358f-619">The regular expression  `Regex_poland_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c358f-620">Se encuentra una `Keywords_poland_eu_driver's_license_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="c358f-620">A keyword from  `Keywords_poland_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_poland_eu_driver's_license_number" />
          <Match idRef="Keywords_poland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="c358f-621">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="c358f-621">Keywords</span></span>

<span data-ttu-id="c358f-622">| |</span><span class="sxs-lookup"><span data-stu-id="c358f-622"></span></span>
|<span data-ttu-id="c358f-623">**Keywords_poland_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="c358f-623">**Keywords_poland_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="c358f-624">dl#</span><span class="sxs-lookup"><span data-stu-id="c358f-624">dl#</span></span>  <br/> <span data-ttu-id="c358f-625">permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="c358f-625">driver license</span></span>  <br/> <span data-ttu-id="c358f-626">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="c358f-626">driver license number</span></span>  <br/> <span data-ttu-id="c358f-627">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="c358f-627">driver licence</span></span>  <br/> <span data-ttu-id="c358f-628">Lic de drivers.</span><span class="sxs-lookup"><span data-stu-id="c358f-628">drivers lic.</span></span>  <br/> <span data-ttu-id="c358f-629">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="c358f-629">drivers license</span></span>  <br/> <span data-ttu-id="c358f-630">drivers licence</span><span class="sxs-lookup"><span data-stu-id="c358f-630">drivers licence</span></span>  <br/> <span data-ttu-id="c358f-631">permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="c358f-631">driver's license</span></span>  <br/> <span data-ttu-id="c358f-632">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="c358f-632">driver's license number</span></span>  <br/> <span data-ttu-id="c358f-633">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="c358f-633">driver's licence number</span></span>  <br/> <span data-ttu-id="c358f-634">número de licencia de conducir</span><span class="sxs-lookup"><span data-stu-id="c358f-634">driving license number</span></span>  <br/> <span data-ttu-id="c358f-635">dlno #</span><span class="sxs-lookup"><span data-stu-id="c358f-635">dlno#</span></span>  <br/> <span data-ttu-id="c358f-636">Prawo jazdy</span><span class="sxs-lookup"><span data-stu-id="c358f-636">prawo jazdy</span></span>  <br/> |
   
## <a name="portugal"></a><span data-ttu-id="c358f-637">Portugal</span><span class="sxs-lookup"><span data-stu-id="c358f-637">Portugal</span></span>

### <a name="format"></a><span data-ttu-id="c358f-638">Formato</span><span class="sxs-lookup"><span data-stu-id="c358f-638">Format</span></span>

<span data-ttu-id="c358f-639">Dos letras seguidas de siete números en el patrón especificado</span><span class="sxs-lookup"><span data-stu-id="c358f-639">Two letters followed by a seven numbers in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="c358f-640">Patrón</span><span class="sxs-lookup"><span data-stu-id="c358f-640">Pattern</span></span>

<span data-ttu-id="c358f-641">Dos letras seguidas de siete números con caracteres especiales:</span><span class="sxs-lookup"><span data-stu-id="c358f-641">Two letters followed by seven numbers with special characters:</span></span>
  
-  <span data-ttu-id="c358f-642">Dos letras (sin distinción entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="c358f-642">Two letters (not case-sensitive)</span></span> 
    
- <span data-ttu-id="c358f-643">Un guión </span><span class="sxs-lookup"><span data-stu-id="c358f-643">A hyphen</span></span>
    
- <span data-ttu-id="c358f-644">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="c358f-644">Six digits</span></span>
    
- <span data-ttu-id="c358f-645">Un espacio</span><span class="sxs-lookup"><span data-stu-id="c358f-645">A space</span></span>
    
- <span data-ttu-id="c358f-646">Un dígito</span><span class="sxs-lookup"><span data-stu-id="c358f-646">One digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="c358f-647">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="c358f-647">Checksum</span></span>

<span data-ttu-id="c358f-648">No</span><span class="sxs-lookup"><span data-stu-id="c358f-648">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="c358f-649">Definición</span><span class="sxs-lookup"><span data-stu-id="c358f-649">Definition</span></span>

<span data-ttu-id="c358f-650">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="c358f-650">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c358f-651">La expresión `Regex_portugal_eu_driver's_license_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="c358f-651">The regular expression  `Regex_portugal_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c358f-652">Se encuentra una `Keywords_portugal_eu_driver's_license_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="c358f-652">A keyword from  `Keywords_portugal_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_driver's_license_number" />
          <Match idRef="Keywords_portugal_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="c358f-653">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="c358f-653">Keywords</span></span>

<span data-ttu-id="c358f-654">| |</span><span class="sxs-lookup"><span data-stu-id="c358f-654"></span></span>
|<span data-ttu-id="c358f-655">**Keywords_portugal_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="c358f-655">**Keywords_portugal_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="c358f-656">dl#</span><span class="sxs-lookup"><span data-stu-id="c358f-656">dl#</span></span>  <br/> <span data-ttu-id="c358f-657">permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="c358f-657">driver license</span></span>  <br/> <span data-ttu-id="c358f-658">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="c358f-658">driver license number</span></span>  <br/> <span data-ttu-id="c358f-659">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="c358f-659">driver licence</span></span>  <br/> <span data-ttu-id="c358f-660">Lic de drivers.</span><span class="sxs-lookup"><span data-stu-id="c358f-660">drivers lic.</span></span>  <br/> <span data-ttu-id="c358f-661">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="c358f-661">drivers license</span></span>  <br/> <span data-ttu-id="c358f-662">drivers licence</span><span class="sxs-lookup"><span data-stu-id="c358f-662">drivers licence</span></span>  <br/> <span data-ttu-id="c358f-663">permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="c358f-663">driver's license</span></span>  <br/> <span data-ttu-id="c358f-664">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="c358f-664">driver's license number</span></span>  <br/> <span data-ttu-id="c358f-665">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="c358f-665">driver's licence number</span></span>  <br/> <span data-ttu-id="c358f-666">número de licencia de conducir</span><span class="sxs-lookup"><span data-stu-id="c358f-666">driving license number</span></span>  <br/> <span data-ttu-id="c358f-667">dlno #</span><span class="sxs-lookup"><span data-stu-id="c358f-667">dlno#</span></span>  <br/> <span data-ttu-id="c358f-668">Carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="c358f-668">carteira de motorista</span></span>  <br/> |
   
## <a name="romania"></a><span data-ttu-id="c358f-669">Rumania</span><span class="sxs-lookup"><span data-stu-id="c358f-669">Romania</span></span>

### <a name="format"></a><span data-ttu-id="c358f-670">Formato</span><span class="sxs-lookup"><span data-stu-id="c358f-670">Format</span></span>

<span data-ttu-id="c358f-671">Un carácter seguido de ocho dígitos</span><span class="sxs-lookup"><span data-stu-id="c358f-671">One character followed by eight digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="c358f-672">Patrón</span><span class="sxs-lookup"><span data-stu-id="c358f-672">Pattern</span></span>

<span data-ttu-id="c358f-673">Un carácter seguido de ocho dígitos:</span><span class="sxs-lookup"><span data-stu-id="c358f-673">One character followed by eight digits:</span></span>
  
-  <span data-ttu-id="c358f-674">Una letra (no distingue entre mayúsculas y minúsculas) o un dígito</span><span class="sxs-lookup"><span data-stu-id="c358f-674">One letter (not case-sensitive) or digit</span></span> 
    
- <span data-ttu-id="c358f-675">Ocho dígitos</span><span class="sxs-lookup"><span data-stu-id="c358f-675">Eight digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="c358f-676">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="c358f-676">Checksum</span></span>

<span data-ttu-id="c358f-677">No</span><span class="sxs-lookup"><span data-stu-id="c358f-677">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="c358f-678">Definición</span><span class="sxs-lookup"><span data-stu-id="c358f-678">Definition</span></span>

<span data-ttu-id="c358f-679">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="c358f-679">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c358f-680">La expresión `Regex_romania_eu_driver's_license_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="c358f-680">The regular expression  `Regex_romania_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c358f-681">Se encuentra una `Keywords_romania_eu_driver's_license_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="c358f-681">A keyword from  `Keywords_romania_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_driver's_license_number" />
          <Match idRef="Keywords_romania_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="c358f-682">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="c358f-682">Keywords</span></span>

<span data-ttu-id="c358f-683">| |</span><span class="sxs-lookup"><span data-stu-id="c358f-683"></span></span>
|<span data-ttu-id="c358f-684">**Keywords_romania_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="c358f-684">**Keywords_romania_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="c358f-685">dl#</span><span class="sxs-lookup"><span data-stu-id="c358f-685">dl#</span></span>  <br/> <span data-ttu-id="c358f-686">permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="c358f-686">driver license</span></span>  <br/> <span data-ttu-id="c358f-687">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="c358f-687">driver license number</span></span>  <br/> <span data-ttu-id="c358f-688">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="c358f-688">driver licence</span></span>  <br/> <span data-ttu-id="c358f-689">Lic de drivers.</span><span class="sxs-lookup"><span data-stu-id="c358f-689">drivers lic.</span></span>  <br/> <span data-ttu-id="c358f-690">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="c358f-690">drivers license</span></span>  <br/> <span data-ttu-id="c358f-691">drivers licence</span><span class="sxs-lookup"><span data-stu-id="c358f-691">drivers licence</span></span>  <br/> <span data-ttu-id="c358f-692">permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="c358f-692">driver's license</span></span>  <br/> <span data-ttu-id="c358f-693">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="c358f-693">driver's license number</span></span>  <br/> <span data-ttu-id="c358f-694">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="c358f-694">driver's licence number</span></span>  <br/> <span data-ttu-id="c358f-695">número de licencia de conducir</span><span class="sxs-lookup"><span data-stu-id="c358f-695">driving license number</span></span>  <br/> <span data-ttu-id="c358f-696">dlno #</span><span class="sxs-lookup"><span data-stu-id="c358f-696">dlno#</span></span>  <br/> <span data-ttu-id="c358f-697">Perm de conducere</span><span class="sxs-lookup"><span data-stu-id="c358f-697">permis de conducere</span></span>  <br/> |
   
## <a name="slovakia"></a><span data-ttu-id="c358f-698">Eslovaquia</span><span class="sxs-lookup"><span data-stu-id="c358f-698">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="c358f-699">Formato</span><span class="sxs-lookup"><span data-stu-id="c358f-699">Format</span></span>

<span data-ttu-id="c358f-700">Un carácter seguido de siete dígitos</span><span class="sxs-lookup"><span data-stu-id="c358f-700">One character followed by seven digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="c358f-701">Patrón</span><span class="sxs-lookup"><span data-stu-id="c358f-701">Pattern</span></span>

<span data-ttu-id="c358f-702">Un carácter seguido de siete dígitos</span><span class="sxs-lookup"><span data-stu-id="c358f-702">One character followed by seven digits</span></span>
  
- <span data-ttu-id="c358f-703">Una letra (no distingue entre mayúsculas y minúsculas) o un dígito</span><span class="sxs-lookup"><span data-stu-id="c358f-703">One letter (not case-sensitive) or digit</span></span>
    
-  <span data-ttu-id="c358f-704">Siete dígitos</span><span class="sxs-lookup"><span data-stu-id="c358f-704">Seven digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="c358f-705">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="c358f-705">Checksum</span></span>

<span data-ttu-id="c358f-706">No</span><span class="sxs-lookup"><span data-stu-id="c358f-706">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="c358f-707">Definición</span><span class="sxs-lookup"><span data-stu-id="c358f-707">Definition</span></span>

<span data-ttu-id="c358f-708">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="c358f-708">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c358f-709">La expresión `Regex_slovakia_eu_driver's_license_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="c358f-709">The regular expression  `Regex_slovakia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c358f-710">Se encuentra una `Keywords_slovakia_eu_driver's_license_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="c358f-710">A keyword from  `Keywords_slovakia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovaknia_eu_driver's_license_number" />
          <Match idRef="Keywords_slovakia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="c358f-711">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="c358f-711">Keywords</span></span>

<span data-ttu-id="c358f-712">| |</span><span class="sxs-lookup"><span data-stu-id="c358f-712"></span></span>
|<span data-ttu-id="c358f-713">**Keywords_slovakia_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="c358f-713">**Keywords_slovakia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="c358f-714">dl#</span><span class="sxs-lookup"><span data-stu-id="c358f-714">dl#</span></span>  <br/> <span data-ttu-id="c358f-715">permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="c358f-715">driver license</span></span>  <br/> <span data-ttu-id="c358f-716">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="c358f-716">driver license number</span></span>  <br/> <span data-ttu-id="c358f-717">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="c358f-717">driver licence</span></span>  <br/> <span data-ttu-id="c358f-718">Lic de drivers.</span><span class="sxs-lookup"><span data-stu-id="c358f-718">drivers lic.</span></span>  <br/> <span data-ttu-id="c358f-719">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="c358f-719">drivers license</span></span>  <br/> <span data-ttu-id="c358f-720">drivers licence</span><span class="sxs-lookup"><span data-stu-id="c358f-720">drivers licence</span></span>  <br/> <span data-ttu-id="c358f-721">permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="c358f-721">driver's license</span></span>  <br/> <span data-ttu-id="c358f-722">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="c358f-722">driver's license number</span></span>  <br/> <span data-ttu-id="c358f-723">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="c358f-723">driver's licence number</span></span>  <br/> <span data-ttu-id="c358f-724">número de licencia de conducir</span><span class="sxs-lookup"><span data-stu-id="c358f-724">driving license number</span></span>  <br/> <span data-ttu-id="c358f-725">dlno #</span><span class="sxs-lookup"><span data-stu-id="c358f-725">dlno#</span></span>  <br/> <span data-ttu-id="c358f-726">vodičský preukaz</span><span class="sxs-lookup"><span data-stu-id="c358f-726">vodičský preukaz</span></span>  <br/> |
   
## <a name="slovenia"></a><span data-ttu-id="c358f-727">Eslovenia</span><span class="sxs-lookup"><span data-stu-id="c358f-727">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="c358f-728">Formato</span><span class="sxs-lookup"><span data-stu-id="c358f-728">Format</span></span>

<span data-ttu-id="c358f-729">Nueve dígitos sin espacios y delimitadores</span><span class="sxs-lookup"><span data-stu-id="c358f-729">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="c358f-730">Patrón</span><span class="sxs-lookup"><span data-stu-id="c358f-730">Pattern</span></span>

<span data-ttu-id="c358f-731">Nueve dígitos</span><span class="sxs-lookup"><span data-stu-id="c358f-731">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="c358f-732">Checksum</span><span class="sxs-lookup"><span data-stu-id="c358f-732">Checksum</span></span>

<span data-ttu-id="c358f-733">No</span><span class="sxs-lookup"><span data-stu-id="c358f-733">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="c358f-734">Definición</span><span class="sxs-lookup"><span data-stu-id="c358f-734">Definition</span></span>

<span data-ttu-id="c358f-735">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="c358f-735">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c358f-736">La expresión `Regex_slovenia_eu_driver's_license_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="c358f-736">The regular expression  `Regex_slovenia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c358f-737">Se encuentra una `Keywords_slovenia_eu_driver's_license_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="c358f-737">A keyword from  `Keywords_slovenia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_driver's_license_number" />
          <Match idRef="Keywords_slovenia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="c358f-738">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="c358f-738">Keywords</span></span>

<span data-ttu-id="c358f-739">| |</span><span class="sxs-lookup"><span data-stu-id="c358f-739"></span></span>
|<span data-ttu-id="c358f-740">**Keywords_slovenia_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="c358f-740">**Keywords_slovenia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="c358f-741">dl#</span><span class="sxs-lookup"><span data-stu-id="c358f-741">dl#</span></span>  <br/> <span data-ttu-id="c358f-742">permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="c358f-742">driver license</span></span>  <br/> <span data-ttu-id="c358f-743">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="c358f-743">driver license number</span></span>  <br/> <span data-ttu-id="c358f-744">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="c358f-744">driver licence</span></span>  <br/> <span data-ttu-id="c358f-745">Lic de drivers.</span><span class="sxs-lookup"><span data-stu-id="c358f-745">drivers lic.</span></span>  <br/> <span data-ttu-id="c358f-746">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="c358f-746">drivers license</span></span>  <br/> <span data-ttu-id="c358f-747">drivers licence</span><span class="sxs-lookup"><span data-stu-id="c358f-747">drivers licence</span></span>  <br/> <span data-ttu-id="c358f-748">permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="c358f-748">driver's license</span></span>  <br/> <span data-ttu-id="c358f-749">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="c358f-749">driver's license number</span></span>  <br/> <span data-ttu-id="c358f-750">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="c358f-750">driver's licence number</span></span>  <br/> <span data-ttu-id="c358f-751">número de licencia de conducir</span><span class="sxs-lookup"><span data-stu-id="c358f-751">driving license number</span></span>  <br/> <span data-ttu-id="c358f-752">dlno #</span><span class="sxs-lookup"><span data-stu-id="c358f-752">dlno#</span></span>  <br/> <span data-ttu-id="c358f-753">vozniško dovoljenje</span><span class="sxs-lookup"><span data-stu-id="c358f-753">vozniško dovoljenje</span></span>  <br/> |
   
## <a name="spain"></a><span data-ttu-id="c358f-754">España</span><span class="sxs-lookup"><span data-stu-id="c358f-754">Spain</span></span>

### <a name="format"></a><span data-ttu-id="c358f-755">Formato</span><span class="sxs-lookup"><span data-stu-id="c358f-755">Format</span></span>

<span data-ttu-id="c358f-756">Ocho dígitos seguidos de un carácter</span><span class="sxs-lookup"><span data-stu-id="c358f-756">Eight digits followed by one character</span></span>
  
### <a name="pattern"></a><span data-ttu-id="c358f-757">Patrón</span><span class="sxs-lookup"><span data-stu-id="c358f-757">Pattern</span></span>

<span data-ttu-id="c358f-758">Ocho dígitos seguidos de un carácter:</span><span class="sxs-lookup"><span data-stu-id="c358f-758">Eight digits followed by one character:</span></span>
  
-  <span data-ttu-id="c358f-759">Ocho dígitos</span><span class="sxs-lookup"><span data-stu-id="c358f-759">Eight digits</span></span> 
    
- <span data-ttu-id="c358f-760">Un dígito o letra (no distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="c358f-760">One digit or letter (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="c358f-761">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="c358f-761">Checksum</span></span>

<span data-ttu-id="c358f-762">Sí</span><span class="sxs-lookup"><span data-stu-id="c358f-762">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="c358f-763">Definición</span><span class="sxs-lookup"><span data-stu-id="c358f-763">Definition</span></span>

<span data-ttu-id="c358f-764">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="c358f-764">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c358f-765">La función `Func_spain_eu_driver's_license_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="c358f-765">The function  `Func_spain_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c358f-766">Se encuentra una `Keywords_spain_eu_driver's_license_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="c358f-766">A keyword from  `Keywords_spain_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spain_eu_driver's_license_number" />
          <Match idRef="Keywords_spain_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="c358f-767">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="c358f-767">Keywords</span></span>

<span data-ttu-id="c358f-768">| |</span><span class="sxs-lookup"><span data-stu-id="c358f-768"></span></span>
|<span data-ttu-id="c358f-769">**Keywords_spain_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="c358f-769">**Keywords_spain_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="c358f-770">dlno #</span><span class="sxs-lookup"><span data-stu-id="c358f-770">dlno#</span></span>  <br/> <span data-ttu-id="c358f-771">dl#</span><span class="sxs-lookup"><span data-stu-id="c358f-771">dl#</span></span>  <br/> <span data-ttu-id="c358f-772">Lic de drivers.</span><span class="sxs-lookup"><span data-stu-id="c358f-772">drivers lic.</span></span>  <br/> <span data-ttu-id="c358f-773">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="c358f-773">driver licence</span></span>  <br/> <span data-ttu-id="c358f-774">permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="c358f-774">driver license</span></span>  <br/> <span data-ttu-id="c358f-775">drivers licence</span><span class="sxs-lookup"><span data-stu-id="c358f-775">drivers licence</span></span>  <br/> <span data-ttu-id="c358f-776">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="c358f-776">drivers license</span></span>  <br/> <span data-ttu-id="c358f-777">permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="c358f-777">driver's licence</span></span>  <br/> <span data-ttu-id="c358f-778">permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="c358f-778">driver's license</span></span>  <br/> <span data-ttu-id="c358f-779">driving licence
</span><span class="sxs-lookup"><span data-stu-id="c358f-779">driving licence</span></span>  <br/> <span data-ttu-id="c358f-780">licencia de conducir</span><span class="sxs-lookup"><span data-stu-id="c358f-780">driving license</span></span>  <br/> <span data-ttu-id="c358f-781">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="c358f-781">driver licence number</span></span>  <br/> <span data-ttu-id="c358f-782">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="c358f-782">driver license number</span></span>  <br/> <span data-ttu-id="c358f-783">número de licencia de drivers</span><span class="sxs-lookup"><span data-stu-id="c358f-783">drivers licence number</span></span>  <br/> <span data-ttu-id="c358f-784">número de licencia de drivers</span><span class="sxs-lookup"><span data-stu-id="c358f-784">drivers license number</span></span>  <br/> <span data-ttu-id="c358f-785">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="c358f-785">driver's licence number</span></span>  <br/> <span data-ttu-id="c358f-786">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="c358f-786">driver's license number</span></span>  <br/> <span data-ttu-id="c358f-787">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="c358f-787">driving licence number</span></span>  <br/> <span data-ttu-id="c358f-788">número de licencia de conducir</span><span class="sxs-lookup"><span data-stu-id="c358f-788">driving license number</span></span>  <br/> <span data-ttu-id="c358f-789">permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="c358f-789">driving permit</span></span>  <br/> <span data-ttu-id="c358f-790">número de permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="c358f-790">driving permit number</span></span>  <br/> <span data-ttu-id="c358f-791">permisos de conducción</span><span class="sxs-lookup"><span data-stu-id="c358f-791">permiso de conducción</span></span>  <br/> <span data-ttu-id="c358f-792">permisos conducción</span><span class="sxs-lookup"><span data-stu-id="c358f-792">permiso conducción</span></span>  <br/> <span data-ttu-id="c358f-793">número de licencia conducir</span><span class="sxs-lookup"><span data-stu-id="c358f-793">número licencia conducir</span></span>  <br/> <span data-ttu-id="c358f-794">número de cuaderno de conducir</span><span class="sxs-lookup"><span data-stu-id="c358f-794">número de carnet de conducir</span></span>  <br/> <span data-ttu-id="c358f-795">número conducir de cuaderno</span><span class="sxs-lookup"><span data-stu-id="c358f-795">número carnet conducir</span></span>  <br/> <span data-ttu-id="c358f-796">licenciar conducir</span><span class="sxs-lookup"><span data-stu-id="c358f-796">licencia conducir</span></span>  <br/> <span data-ttu-id="c358f-797">número de permisos de conducir</span><span class="sxs-lookup"><span data-stu-id="c358f-797">número de permiso de conducir</span></span>  <br/> <span data-ttu-id="c358f-798">número de permisos conducir</span><span class="sxs-lookup"><span data-stu-id="c358f-798">número de permiso conducir</span></span>  <br/> <span data-ttu-id="c358f-799">número permisos conducir</span><span class="sxs-lookup"><span data-stu-id="c358f-799">número permiso conducir</span></span>  <br/> <span data-ttu-id="c358f-800">permisos conducir</span><span class="sxs-lookup"><span data-stu-id="c358f-800">permiso conducir</span></span>  <br/> <span data-ttu-id="c358f-801">licencia de manejo</span><span class="sxs-lookup"><span data-stu-id="c358f-801">licencia de manejo</span></span>  <br/> <span data-ttu-id="c358f-802">el cuaderno de conducir</span><span class="sxs-lookup"><span data-stu-id="c358f-802">el carnet de conducir</span></span>  <br/> <span data-ttu-id="c358f-803">conducir del cuaderno</span><span class="sxs-lookup"><span data-stu-id="c358f-803">carnet conducir</span></span>  <br/> |
   
## <a name="sweden"></a><span data-ttu-id="c358f-804">Suecia</span><span class="sxs-lookup"><span data-stu-id="c358f-804">Sweden</span></span>

### <a name="format"></a><span data-ttu-id="c358f-805">Formato</span><span class="sxs-lookup"><span data-stu-id="c358f-805">Format</span></span>

<span data-ttu-id="c358f-806">Diez dígitos que contienen un guión</span><span class="sxs-lookup"><span data-stu-id="c358f-806">Ten digits containing a hyphen</span></span>
  
### <a name="pattern"></a><span data-ttu-id="c358f-807">Patrón</span><span class="sxs-lookup"><span data-stu-id="c358f-807">Pattern</span></span>

<span data-ttu-id="c358f-808">Diez dígitos que contienen un guión:</span><span class="sxs-lookup"><span data-stu-id="c358f-808">Ten digits containing a hyphen:</span></span>
  
-  <span data-ttu-id="c358f-809">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="c358f-809">Six digits</span></span> 
    
- <span data-ttu-id="c358f-810">Un guion</span><span class="sxs-lookup"><span data-stu-id="c358f-810">A hyphen</span></span>
    
- <span data-ttu-id="c358f-811">Cuatro dígitos</span><span class="sxs-lookup"><span data-stu-id="c358f-811">Four digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="c358f-812">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="c358f-812">Checksum</span></span>

<span data-ttu-id="c358f-813">No</span><span class="sxs-lookup"><span data-stu-id="c358f-813">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="c358f-814">Definición</span><span class="sxs-lookup"><span data-stu-id="c358f-814">Definition</span></span>

<span data-ttu-id="c358f-815">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="c358f-815">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c358f-816">La expresión `Regex_sweden_eu_driver's_license_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="c358f-816">The regular expression  `Regex_sweden_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c358f-817">Se encuentra una `Keywords_sweden_eu_driver's_license_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="c358f-817">A keyword from  `Keywords_sweden_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_sweden_eu_driver's_license_number" />
          <Match idRef="Keywords_sweden_eu_driver's_license_number" />
        </Pattern>
</Entity> 
```

### <a name="keywords"></a><span data-ttu-id="c358f-818">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="c358f-818">Keywords</span></span>

<span data-ttu-id="c358f-819">| |</span><span class="sxs-lookup"><span data-stu-id="c358f-819"></span></span>
|<span data-ttu-id="c358f-820">**Keywords_sweden_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="c358f-820">**Keywords_sweden_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="c358f-821">dl#</span><span class="sxs-lookup"><span data-stu-id="c358f-821">dl#</span></span>  <br/> <span data-ttu-id="c358f-822">permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="c358f-822">driver license</span></span>  <br/> <span data-ttu-id="c358f-823">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="c358f-823">driver license number</span></span>  <br/> <span data-ttu-id="c358f-824">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="c358f-824">driver licence</span></span>  <br/> <span data-ttu-id="c358f-825">Lic de drivers.</span><span class="sxs-lookup"><span data-stu-id="c358f-825">drivers lic.</span></span>  <br/> <span data-ttu-id="c358f-826">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="c358f-826">drivers license</span></span>  <br/> <span data-ttu-id="c358f-827">drivers licence</span><span class="sxs-lookup"><span data-stu-id="c358f-827">drivers licence</span></span>  <br/> <span data-ttu-id="c358f-828">permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="c358f-828">driver's license</span></span>  <br/> <span data-ttu-id="c358f-829">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="c358f-829">driver's license number</span></span>  <br/> <span data-ttu-id="c358f-830">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="c358f-830">driver's licence number</span></span>  <br/> <span data-ttu-id="c358f-831">número de licencia de conducir</span><span class="sxs-lookup"><span data-stu-id="c358f-831">driving license number</span></span>  <br/> <span data-ttu-id="c358f-832">dlno #</span><span class="sxs-lookup"><span data-stu-id="c358f-832">dlno#</span></span>  <br/> <span data-ttu-id="c358f-833">körkort</span><span class="sxs-lookup"><span data-stu-id="c358f-833">körkort</span></span>  <br/> |
   
## <a name="uk"></a><span data-ttu-id="c358f-834">LIBRA</span><span class="sxs-lookup"><span data-stu-id="c358f-834">UK</span></span>

<span data-ttu-id="c358f-p103">Para obtener más información, consulte la sección "número de licencia de conductor del Reino Unido" en [Qué buscan los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="c358f-p103">For details, see the section "U.K. Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="c358f-837">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c358f-837">See also</span></span>

[<span data-ttu-id="c358f-838">Qué buscan los tipos de información confidencial</span><span class="sxs-lookup"><span data-stu-id="c358f-838">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

