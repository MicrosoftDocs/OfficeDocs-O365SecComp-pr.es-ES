---
title: Número de licencia del controlador de la UE
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/17/2018
ms.audience: Admin
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
ms.assetid: c3923cd3-ec84-435f-bf41-cadc37996a4b
description: En este tema se muestra lo que busca una directiva de (DLP) de prevención de pérdida de datos cuando detecta el tipo de información confidencial de número de licencia del controlador de la UE. Este tipo de información confidencial define diferentes patrones, palabras clave y otras pruebas para cada país.
ms.openlocfilehash: 065684249f9766d567c63e6b8170d36f56692e45
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22536159"
---
# <a name="eu-drivers-license-number"></a><span data-ttu-id="f5b73-104">Número de licencia del controlador de la UE</span><span class="sxs-lookup"><span data-stu-id="f5b73-104">EU Driver's License Number</span></span>

<span data-ttu-id="f5b73-p102">En este tema se muestra lo que busca una directiva de (DLP) de prevención de pérdida de datos cuando detecta el tipo de información confidencial de número de licencia del controlador de la UE. Este tipo de información confidencial define diferentes patrones, palabras clave y otras pruebas para cada país.</span><span class="sxs-lookup"><span data-stu-id="f5b73-p102">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Driver's License Number sensitive information type. This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="f5b73-107">Austria</span><span class="sxs-lookup"><span data-stu-id="f5b73-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="f5b73-108">Formato</span><span class="sxs-lookup"><span data-stu-id="f5b73-108">Format</span></span>

<span data-ttu-id="f5b73-109">Ocho dígitos sin espacios y los delimitadores</span><span class="sxs-lookup"><span data-stu-id="f5b73-109">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f5b73-110">Patrón</span><span class="sxs-lookup"><span data-stu-id="f5b73-110">Pattern</span></span>

<span data-ttu-id="f5b73-111">Ocho dígitos</span><span class="sxs-lookup"><span data-stu-id="f5b73-111">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="f5b73-112">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="f5b73-112">Checksum</span></span>

<span data-ttu-id="f5b73-113">No</span><span class="sxs-lookup"><span data-stu-id="f5b73-113">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="f5b73-114">Definición</span><span class="sxs-lookup"><span data-stu-id="f5b73-114">Definition</span></span>

<span data-ttu-id="f5b73-115">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="f5b73-115">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f5b73-116">La expresión regular `Regex_austria_eu_driver's_license_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="f5b73-116">The regular expression  `Regex_austria_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f5b73-117">Una palabra clave de `Keywords_austria_eu_driver's_license_number` se encuentra.</span><span class="sxs-lookup"><span data-stu-id="f5b73-117">A keyword from  `Keywords_austria_eu_driver's_license_number` is found.</span></span> 
    
```
<!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_driver's_license_number" />
          <Match idRef="Keywords_austria_eu_driver's_license_number" />
        </Pattern>
    </Entity>

```

### <a name="keywords"></a><span data-ttu-id="f5b73-118">Keywords</span><span class="sxs-lookup"><span data-stu-id="f5b73-118">Keywords</span></span>

<span data-ttu-id="f5b73-119">| |</span><span class="sxs-lookup"><span data-stu-id="f5b73-119"></span></span>
|<span data-ttu-id="f5b73-120">**Keywords_austria_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="f5b73-120">**Keywords_austria_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="f5b73-121">dl#</span><span class="sxs-lookup"><span data-stu-id="f5b73-121">dl#</span></span>  <br/> <span data-ttu-id="f5b73-122">permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="f5b73-122">driver license</span></span>  <br/> <span data-ttu-id="f5b73-123">número de licencia del controlador</span><span class="sxs-lookup"><span data-stu-id="f5b73-123">driver license number</span></span>  <br/> <span data-ttu-id="f5b73-124">licencia de controlador</span><span class="sxs-lookup"><span data-stu-id="f5b73-124">driver licence</span></span>  <br/> <span data-ttu-id="f5b73-125">lic de controladores.</span><span class="sxs-lookup"><span data-stu-id="f5b73-125">drivers lic.</span></span>  <br/> <span data-ttu-id="f5b73-126">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="f5b73-126">drivers license</span></span>  <br/> <span data-ttu-id="f5b73-127">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="f5b73-127">driver's licence</span></span>  <br/> <span data-ttu-id="f5b73-128">permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="f5b73-128">driver's license</span></span>  <br/> <span data-ttu-id="f5b73-129">número de licencia del controlador</span><span class="sxs-lookup"><span data-stu-id="f5b73-129">driver's license number</span></span>  <br/> <span data-ttu-id="f5b73-130">número de la licencia del controlador</span><span class="sxs-lookup"><span data-stu-id="f5b73-130">driver's licence number</span></span>  <br/>  <span data-ttu-id="f5b73-131">número de licencia de fuerzas</span><span class="sxs-lookup"><span data-stu-id="f5b73-131">driving license number</span></span>  <br/> <span data-ttu-id="f5b73-132">dlno #</span><span class="sxs-lookup"><span data-stu-id="f5b73-132">dlno#</span></span>  <br/> <span data-ttu-id="f5b73-133">fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="f5b73-133">fuhrerschein</span></span>  <br/> <span data-ttu-id="f5b73-134">fuhrerschein República osterreich</span><span class="sxs-lookup"><span data-stu-id="f5b73-134">fuhrerschein republik osterreich</span></span>  <br/> |
   
## <a name="belgium"></a><span data-ttu-id="f5b73-135">Bélgica</span><span class="sxs-lookup"><span data-stu-id="f5b73-135">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="f5b73-136">Formato</span><span class="sxs-lookup"><span data-stu-id="f5b73-136">Format</span></span>

<span data-ttu-id="f5b73-137">10 dígitos sin espacios y los delimitadores</span><span class="sxs-lookup"><span data-stu-id="f5b73-137">10 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f5b73-138">Patrón</span><span class="sxs-lookup"><span data-stu-id="f5b73-138">Pattern</span></span>

<span data-ttu-id="f5b73-139">10 dígitos</span><span class="sxs-lookup"><span data-stu-id="f5b73-139">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="f5b73-140">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="f5b73-140">Checksum</span></span>

<span data-ttu-id="f5b73-141">No</span><span class="sxs-lookup"><span data-stu-id="f5b73-141">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="f5b73-142">Definición</span><span class="sxs-lookup"><span data-stu-id="f5b73-142">Definition</span></span>

<span data-ttu-id="f5b73-143">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="f5b73-143">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f5b73-144">La expresión regular `Regex_belgium_eu_driver's_license_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="f5b73-144">The regular expression  `Regex_belgium_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f5b73-145">Una palabra clave de `Keywords_belgium_eu_driver's_license_number` se encuentra.</span><span class="sxs-lookup"><span data-stu-id="f5b73-145">A keyword from  `Keywords_belgium_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_driver's_license_number" />
          <Match idRef="Keywords_belgium_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="f5b73-146">Keywords</span><span class="sxs-lookup"><span data-stu-id="f5b73-146">Keywords</span></span>

<span data-ttu-id="f5b73-147">| |</span><span class="sxs-lookup"><span data-stu-id="f5b73-147"></span></span>
|<span data-ttu-id="f5b73-148">**Keywords__belgium_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="f5b73-148">**Keywords__belgium_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="f5b73-149">dl#</span><span class="sxs-lookup"><span data-stu-id="f5b73-149">dl#</span></span>  <br/> <span data-ttu-id="f5b73-150">permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="f5b73-150">driver license</span></span>  <br/> <span data-ttu-id="f5b73-151">número de licencia del controlador</span><span class="sxs-lookup"><span data-stu-id="f5b73-151">driver license number</span></span>  <br/> <span data-ttu-id="f5b73-152">licencia de controlador</span><span class="sxs-lookup"><span data-stu-id="f5b73-152">driver licence</span></span>  <br/> <span data-ttu-id="f5b73-153">lic de controladores.</span><span class="sxs-lookup"><span data-stu-id="f5b73-153">drivers lic.</span></span>  <br/> <span data-ttu-id="f5b73-154">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="f5b73-154">drivers license</span></span>  <br/> <span data-ttu-id="f5b73-155">drivers licence</span><span class="sxs-lookup"><span data-stu-id="f5b73-155">drivers licence</span></span>  <br/> <span data-ttu-id="f5b73-156">permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="f5b73-156">driver's license</span></span>  <br/> <span data-ttu-id="f5b73-157">número de licencia del controlador</span><span class="sxs-lookup"><span data-stu-id="f5b73-157">driver's license number</span></span>  <br/> <span data-ttu-id="f5b73-158">número de la licencia del controlador</span><span class="sxs-lookup"><span data-stu-id="f5b73-158">driver's licence number</span></span>  <br/> <span data-ttu-id="f5b73-159">dlno #</span><span class="sxs-lookup"><span data-stu-id="f5b73-159">dlno#</span></span>  <br/> <span data-ttu-id="f5b73-160">rijbewijs</span><span class="sxs-lookup"><span data-stu-id="f5b73-160">rijbewijs</span></span>  <br/> <span data-ttu-id="f5b73-161">rijbewijsnummer</span><span class="sxs-lookup"><span data-stu-id="f5b73-161">rijbewijsnummer</span></span>  <br/> <span data-ttu-id="f5b73-162">führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="f5b73-162">führerscheinnummer</span></span>  <br/> <span data-ttu-id="f5b73-163">fuhrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="f5b73-163">fuhrerscheinnummer</span></span>  <br/> <span data-ttu-id="f5b73-164">fuehrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="f5b73-164">fuehrerscheinnummer</span></span>  <br/> <span data-ttu-id="f5b73-165">führerschein n</span><span class="sxs-lookup"><span data-stu-id="f5b73-165">führerschein- nr</span></span>  <br/> <span data-ttu-id="f5b73-166">fuehrerschein n</span><span class="sxs-lookup"><span data-stu-id="f5b73-166">fuehrerschein- Nr</span></span>  <br/> <span data-ttu-id="f5b73-167">fuehrerschein n</span><span class="sxs-lookup"><span data-stu-id="f5b73-167">fuehrerschein- nr</span></span>  <br/> |
   
## <a name="bulgaria"></a><span data-ttu-id="f5b73-168">Bulgaria</span><span class="sxs-lookup"><span data-stu-id="f5b73-168">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="f5b73-169">Formato</span><span class="sxs-lookup"><span data-stu-id="f5b73-169">Format</span></span>

<span data-ttu-id="f5b73-170">Nueve dígitos sin espacios y los delimitadores</span><span class="sxs-lookup"><span data-stu-id="f5b73-170">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f5b73-171">Patrón</span><span class="sxs-lookup"><span data-stu-id="f5b73-171">Pattern</span></span>

<span data-ttu-id="f5b73-172">Nueve dígitos</span><span class="sxs-lookup"><span data-stu-id="f5b73-172">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="f5b73-173">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="f5b73-173">Checksum</span></span>

<span data-ttu-id="f5b73-174">No</span><span class="sxs-lookup"><span data-stu-id="f5b73-174">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="f5b73-175">Definición</span><span class="sxs-lookup"><span data-stu-id="f5b73-175">Definition</span></span>

<span data-ttu-id="f5b73-176">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="f5b73-176">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f5b73-177">La expresión regular `Regex_bulgaria_eu_driver's_license_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="f5b73-177">The regular expression  `Regex_bulgaria_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f5b73-178">Una palabra clave de `Keywords_bulgaria_eu_driver's_license_number` se encuentra.</span><span class="sxs-lookup"><span data-stu-id="f5b73-178">A keyword from  `Keywords_bulgaria_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
             <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_driver's_license_number" />
          <Match idRef="Keywords_bulgaria_eu_driver's_license_number" />
        </Pattern> 
</Entity>    

```

### <a name="keywords"></a><span data-ttu-id="f5b73-179">Keywords</span><span class="sxs-lookup"><span data-stu-id="f5b73-179">Keywords</span></span>

<span data-ttu-id="f5b73-180">| |</span><span class="sxs-lookup"><span data-stu-id="f5b73-180"></span></span>
|<span data-ttu-id="f5b73-181">**Keywords_bulgaria_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="f5b73-181">**Keywords_bulgaria_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="f5b73-182">dl#</span><span class="sxs-lookup"><span data-stu-id="f5b73-182">dl#</span></span>  <br/> <span data-ttu-id="f5b73-183">permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="f5b73-183">driver license</span></span>  <br/> <span data-ttu-id="f5b73-184">número de licencia del controlador</span><span class="sxs-lookup"><span data-stu-id="f5b73-184">driver license number</span></span>  <br/> <span data-ttu-id="f5b73-185">licencia de controlador</span><span class="sxs-lookup"><span data-stu-id="f5b73-185">driver licence</span></span>  <br/> <span data-ttu-id="f5b73-186">lic de controladores.</span><span class="sxs-lookup"><span data-stu-id="f5b73-186">drivers lic.</span></span>  <br/> <span data-ttu-id="f5b73-187">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="f5b73-187">drivers license</span></span>  <br/> <span data-ttu-id="f5b73-188">drivers licence</span><span class="sxs-lookup"><span data-stu-id="f5b73-188">drivers licence</span></span>  <br/> <span data-ttu-id="f5b73-189">permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="f5b73-189">driver's license</span></span>  <br/> <span data-ttu-id="f5b73-190">número de licencia del controlador</span><span class="sxs-lookup"><span data-stu-id="f5b73-190">driver's license number</span></span>  <br/> <span data-ttu-id="f5b73-191">número de la licencia del controlador</span><span class="sxs-lookup"><span data-stu-id="f5b73-191">driver's licence number</span></span>  <br/> <span data-ttu-id="f5b73-192">número de licencia de fuerzas</span><span class="sxs-lookup"><span data-stu-id="f5b73-192">driving license number</span></span>  <br/> <span data-ttu-id="f5b73-193">dlno #</span><span class="sxs-lookup"><span data-stu-id="f5b73-193">dlno#</span></span>  <br/> <span data-ttu-id="f5b73-194">СВИДЕТЕЛСТВО ЗА УПРАВЛЕНИЕ НА МПС</span><span class="sxs-lookup"><span data-stu-id="f5b73-194">свидетелство за управление на мпс</span></span>  <br/> <span data-ttu-id="f5b73-195">СВИДЕТЕЛСТВО ЗА УПРАВЛЕНИЕ НА МОТОРНО ПРЕВОЗНО СРЕДСТВО</span><span class="sxs-lookup"><span data-stu-id="f5b73-195">свидетелство за управление на моторно превозно средство</span></span>  <br/> <span data-ttu-id="f5b73-196">СУМПС</span><span class="sxs-lookup"><span data-stu-id="f5b73-196">сумпс</span></span>  <br/> <span data-ttu-id="f5b73-197">ШОФЬОРСКА КНИЖКА</span><span class="sxs-lookup"><span data-stu-id="f5b73-197">шофьорска книжка</span></span>  <br/> |
   
## <a name="croatia"></a><span data-ttu-id="f5b73-198">Croacia</span><span class="sxs-lookup"><span data-stu-id="f5b73-198">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="f5b73-199">Formato</span><span class="sxs-lookup"><span data-stu-id="f5b73-199">Format</span></span>

<span data-ttu-id="f5b73-200">Ocho dígitos sin espacios y los delimitadores</span><span class="sxs-lookup"><span data-stu-id="f5b73-200">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f5b73-201">Patrón</span><span class="sxs-lookup"><span data-stu-id="f5b73-201">Pattern</span></span>

<span data-ttu-id="f5b73-202">Ocho dígitos</span><span class="sxs-lookup"><span data-stu-id="f5b73-202">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="f5b73-203">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="f5b73-203">Checksum</span></span>

<span data-ttu-id="f5b73-204">No</span><span class="sxs-lookup"><span data-stu-id="f5b73-204">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="f5b73-205">Definición</span><span class="sxs-lookup"><span data-stu-id="f5b73-205">Definition</span></span>

<span data-ttu-id="f5b73-206">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="f5b73-206">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f5b73-207">La expresión regular `Regex_croatia_eu_driver's_license_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="f5b73-207">The regular expression  `Regex_croatia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f5b73-208">Una palabra clave de `Keywords_croatia_eu_driver's_license_number` se encuentra.</span><span class="sxs-lookup"><span data-stu-id="f5b73-208">A keyword from  `Keywords_croatia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_driver's_license_number" />
          <Match idRef="Keywords_croatia_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="f5b73-209">Keywords</span><span class="sxs-lookup"><span data-stu-id="f5b73-209">Keywords</span></span>

<span data-ttu-id="f5b73-210">| |</span><span class="sxs-lookup"><span data-stu-id="f5b73-210"></span></span>
|<span data-ttu-id="f5b73-211">**Keywords_croatia_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="f5b73-211">**Keywords_croatia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="f5b73-212">dl#</span><span class="sxs-lookup"><span data-stu-id="f5b73-212">dl#</span></span>  <br/> <span data-ttu-id="f5b73-213">permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="f5b73-213">driver license</span></span>  <br/> <span data-ttu-id="f5b73-214">número de licencia del controlador</span><span class="sxs-lookup"><span data-stu-id="f5b73-214">driver license number</span></span>  <br/> <span data-ttu-id="f5b73-215">licencia de controlador</span><span class="sxs-lookup"><span data-stu-id="f5b73-215">driver licence</span></span>  <br/> <span data-ttu-id="f5b73-216">lic de controladores.</span><span class="sxs-lookup"><span data-stu-id="f5b73-216">drivers lic.</span></span>  <br/> <span data-ttu-id="f5b73-217">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="f5b73-217">drivers license</span></span>  <br/> <span data-ttu-id="f5b73-218">drivers licence</span><span class="sxs-lookup"><span data-stu-id="f5b73-218">drivers licence</span></span>  <br/> <span data-ttu-id="f5b73-219">permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="f5b73-219">driver's license</span></span>  <br/> <span data-ttu-id="f5b73-220">número de licencia del controlador</span><span class="sxs-lookup"><span data-stu-id="f5b73-220">driver's license number</span></span>  <br/> <span data-ttu-id="f5b73-221">número de la licencia del controlador</span><span class="sxs-lookup"><span data-stu-id="f5b73-221">driver's licence number</span></span>  <br/> <span data-ttu-id="f5b73-222">número de licencia de fuerzas</span><span class="sxs-lookup"><span data-stu-id="f5b73-222">driving license number</span></span>  <br/> <span data-ttu-id="f5b73-223">dlno #</span><span class="sxs-lookup"><span data-stu-id="f5b73-223">dlno#</span></span>  <br/> <span data-ttu-id="f5b73-224">vozačka dozvola</span><span class="sxs-lookup"><span data-stu-id="f5b73-224">vozačka dozvola</span></span>  <br/> |
   
## <a name="cyprus"></a><span data-ttu-id="f5b73-225">Chipre</span><span class="sxs-lookup"><span data-stu-id="f5b73-225">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="f5b73-226">Formato</span><span class="sxs-lookup"><span data-stu-id="f5b73-226">Format</span></span>

<span data-ttu-id="f5b73-227">12 dígitos sin espacios y los delimitadores</span><span class="sxs-lookup"><span data-stu-id="f5b73-227">12 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f5b73-228">Patrón</span><span class="sxs-lookup"><span data-stu-id="f5b73-228">Pattern</span></span>

<span data-ttu-id="f5b73-229">12 dígitos</span><span class="sxs-lookup"><span data-stu-id="f5b73-229">12 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="f5b73-230">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="f5b73-230">Checksum</span></span>

<span data-ttu-id="f5b73-231">No</span><span class="sxs-lookup"><span data-stu-id="f5b73-231">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="f5b73-232">Definición</span><span class="sxs-lookup"><span data-stu-id="f5b73-232">Definition</span></span>

<span data-ttu-id="f5b73-233">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="f5b73-233">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f5b73-234">La expresión regular `Regex_cyprus_eu_driver's_license_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="f5b73-234">The regular expression  `Regex_cyprus_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f5b73-235">Una palabra clave de `Keywords_cyprus_eu_driver's_license_number` se encuentra.</span><span class="sxs-lookup"><span data-stu-id="f5b73-235">A keyword from  `Keywords_cyprus_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_driver's_license_number" />
          <Match idRef="Keywords_cyprus_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="f5b73-236">Keywords</span><span class="sxs-lookup"><span data-stu-id="f5b73-236">Keywords</span></span>

<span data-ttu-id="f5b73-237">| |</span><span class="sxs-lookup"><span data-stu-id="f5b73-237"></span></span>
|<span data-ttu-id="f5b73-238">**Keywords_cyprus_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="f5b73-238">**Keywords_cyprus_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="f5b73-239">dl#</span><span class="sxs-lookup"><span data-stu-id="f5b73-239">dl#</span></span>  <br/> <span data-ttu-id="f5b73-240">permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="f5b73-240">driver license</span></span>  <br/> <span data-ttu-id="f5b73-241">número de licencia del controlador</span><span class="sxs-lookup"><span data-stu-id="f5b73-241">driver license number</span></span>  <br/> <span data-ttu-id="f5b73-242">licencia de controlador</span><span class="sxs-lookup"><span data-stu-id="f5b73-242">driver licence</span></span>  <br/> <span data-ttu-id="f5b73-243">lic de controladores.</span><span class="sxs-lookup"><span data-stu-id="f5b73-243">drivers lic.</span></span>  <br/> <span data-ttu-id="f5b73-244">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="f5b73-244">drivers license</span></span>  <br/> <span data-ttu-id="f5b73-245">drivers licence</span><span class="sxs-lookup"><span data-stu-id="f5b73-245">drivers licence</span></span>  <br/> <span data-ttu-id="f5b73-246">número de licencia del controlador</span><span class="sxs-lookup"><span data-stu-id="f5b73-246">driver's license number</span></span>  <br/> <span data-ttu-id="f5b73-247">número de la licencia del controlador</span><span class="sxs-lookup"><span data-stu-id="f5b73-247">driver's licence number</span></span>  <br/> <span data-ttu-id="f5b73-248">número de licencia de fuerzas</span><span class="sxs-lookup"><span data-stu-id="f5b73-248">driving license number</span></span>  <br/> <span data-ttu-id="f5b73-249">dlno #</span><span class="sxs-lookup"><span data-stu-id="f5b73-249">dlno#</span></span>  <br/> <span data-ttu-id="f5b73-250">ΆΔΕΙΑ ΟΔΉΓΗΣΗΣ</span><span class="sxs-lookup"><span data-stu-id="f5b73-250">άδεια οδήγησης</span></span>  <br/> |
   
## <a name="czech-republic"></a><span data-ttu-id="f5b73-251">República Checa</span><span class="sxs-lookup"><span data-stu-id="f5b73-251">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="f5b73-252">Formato</span><span class="sxs-lookup"><span data-stu-id="f5b73-252">Format</span></span>

<span data-ttu-id="f5b73-253">Dos letras seguidas por seis dígitos</span><span class="sxs-lookup"><span data-stu-id="f5b73-253">Two letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f5b73-254">Patrón</span><span class="sxs-lookup"><span data-stu-id="f5b73-254">Pattern</span></span>

<span data-ttu-id="f5b73-255">Ocho letras y dígitos:</span><span class="sxs-lookup"><span data-stu-id="f5b73-255">Eight letters and digits:</span></span>
  
- <span data-ttu-id="f5b73-256">Dos letras (no distingue mayúsculas de minúsculas)</span><span class="sxs-lookup"><span data-stu-id="f5b73-256">Two letters (not case-sensitive)</span></span>
    
- <span data-ttu-id="f5b73-257">Un espacio (opcional) </span><span class="sxs-lookup"><span data-stu-id="f5b73-257">A space (optional)</span></span>
    
- <span data-ttu-id="f5b73-258">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="f5b73-258">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="f5b73-259">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="f5b73-259">Checksum</span></span>

<span data-ttu-id="f5b73-260">No</span><span class="sxs-lookup"><span data-stu-id="f5b73-260">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="f5b73-261">Definición</span><span class="sxs-lookup"><span data-stu-id="f5b73-261">Definition</span></span>

<span data-ttu-id="f5b73-262">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="f5b73-262">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f5b73-263">La expresión regular `Regex_czech_republic_eu_driver's_license_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="f5b73-263">The regular expression  `Regex_czech_republic_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f5b73-264">Una palabra clave de `Keywords_czech_republic_eu_driver's_license_number` se encuentra.</span><span class="sxs-lookup"><span data-stu-id="f5b73-264">A keyword from  `Keywords_czech_republic_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_driver's_license_number" />
          <Match idRef="Keywords_czech_republic_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="f5b73-265">Keywords</span><span class="sxs-lookup"><span data-stu-id="f5b73-265">Keywords</span></span>

<span data-ttu-id="f5b73-266">| |</span><span class="sxs-lookup"><span data-stu-id="f5b73-266"></span></span>
|<span data-ttu-id="f5b73-267">**Keywords_czech_republic_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="f5b73-267">**Keywords_czech_republic_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="f5b73-268">dl#</span><span class="sxs-lookup"><span data-stu-id="f5b73-268">dl#</span></span>  <br/> <span data-ttu-id="f5b73-269">permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="f5b73-269">driver license</span></span>  <br/> <span data-ttu-id="f5b73-270">número de licencia del controlador</span><span class="sxs-lookup"><span data-stu-id="f5b73-270">driver license number</span></span>  <br/> <span data-ttu-id="f5b73-271">licencia de controlador</span><span class="sxs-lookup"><span data-stu-id="f5b73-271">driver licence</span></span>  <br/> <span data-ttu-id="f5b73-272">lic de controladores.</span><span class="sxs-lookup"><span data-stu-id="f5b73-272">drivers lic.</span></span>  <br/> <span data-ttu-id="f5b73-273">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="f5b73-273">drivers license</span></span>  <br/> <span data-ttu-id="f5b73-274">drivers licence</span><span class="sxs-lookup"><span data-stu-id="f5b73-274">drivers licence</span></span>  <br/> <span data-ttu-id="f5b73-275">permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="f5b73-275">driver's license</span></span>  <br/> <span data-ttu-id="f5b73-276">número de licencia del controlador</span><span class="sxs-lookup"><span data-stu-id="f5b73-276">driver's license number</span></span>  <br/> <span data-ttu-id="f5b73-277">número de licencia del controlador</span><span class="sxs-lookup"><span data-stu-id="f5b73-277">driver's license number</span></span>  <br/> <span data-ttu-id="f5b73-278">número de la licencia del controlador</span><span class="sxs-lookup"><span data-stu-id="f5b73-278">driver's licence number</span></span>  <br/> <span data-ttu-id="f5b73-279">número de licencia de fuerzas</span><span class="sxs-lookup"><span data-stu-id="f5b73-279">driving license number</span></span>  <br/> <span data-ttu-id="f5b73-280">dlno #</span><span class="sxs-lookup"><span data-stu-id="f5b73-280">dlno#</span></span>  <br/> <span data-ttu-id="f5b73-281">Řidičský prúkaz</span><span class="sxs-lookup"><span data-stu-id="f5b73-281">řidičský prúkaz</span></span>  <br/> |
   
## <a name="denmark"></a><span data-ttu-id="f5b73-282">Dinamarca</span><span class="sxs-lookup"><span data-stu-id="f5b73-282">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="f5b73-283">Formato</span><span class="sxs-lookup"><span data-stu-id="f5b73-283">Format</span></span>

<span data-ttu-id="f5b73-284">Ocho dígitos sin espacios y los delimitadores</span><span class="sxs-lookup"><span data-stu-id="f5b73-284">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f5b73-285">Patrón</span><span class="sxs-lookup"><span data-stu-id="f5b73-285">Pattern</span></span>

<span data-ttu-id="f5b73-286">Ocho dígitos</span><span class="sxs-lookup"><span data-stu-id="f5b73-286">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="f5b73-287">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="f5b73-287">Checksum</span></span>

<span data-ttu-id="f5b73-288">Sí</span><span class="sxs-lookup"><span data-stu-id="f5b73-288">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="f5b73-289">Definición</span><span class="sxs-lookup"><span data-stu-id="f5b73-289">Definition</span></span>

<span data-ttu-id="f5b73-290">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="f5b73-290">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f5b73-291">La expresión regular `Regex_denmark_eu_driver's_license_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="f5b73-291">The regular expression  `Regex_denmark_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f5b73-292">Una palabra clave de `Keywords_denmark_eu_driver's_license_number` se encuentra.</span><span class="sxs-lookup"><span data-stu-id="f5b73-292">A keyword from  `Keywords_denmark_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_driver's_license_number" />
          <Match idRef="Keywords_denmark_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="f5b73-293">Keywords</span><span class="sxs-lookup"><span data-stu-id="f5b73-293">Keywords</span></span>

<span data-ttu-id="f5b73-294">| |</span><span class="sxs-lookup"><span data-stu-id="f5b73-294"></span></span>
|<span data-ttu-id="f5b73-295">**Keywords_denmark_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="f5b73-295">**Keywords_denmark_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="f5b73-296">dl#</span><span class="sxs-lookup"><span data-stu-id="f5b73-296">dl#</span></span>  <br/> <span data-ttu-id="f5b73-297">permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="f5b73-297">driver license</span></span>  <br/> <span data-ttu-id="f5b73-298">número de licencia del controlador</span><span class="sxs-lookup"><span data-stu-id="f5b73-298">driver license number</span></span>  <br/> <span data-ttu-id="f5b73-299">licencia de controlador</span><span class="sxs-lookup"><span data-stu-id="f5b73-299">driver licence</span></span>  <br/> <span data-ttu-id="f5b73-300">lic de controladores.</span><span class="sxs-lookup"><span data-stu-id="f5b73-300">drivers lic.</span></span>  <br/> <span data-ttu-id="f5b73-301">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="f5b73-301">drivers license</span></span>  <br/> <span data-ttu-id="f5b73-302">drivers licence</span><span class="sxs-lookup"><span data-stu-id="f5b73-302">drivers licence</span></span>  <br/> <span data-ttu-id="f5b73-303">permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="f5b73-303">driver's license</span></span>  <br/> <span data-ttu-id="f5b73-304">número de licencia del controlador</span><span class="sxs-lookup"><span data-stu-id="f5b73-304">driver's license number</span></span>  <br/> <span data-ttu-id="f5b73-305">número de la licencia del controlador</span><span class="sxs-lookup"><span data-stu-id="f5b73-305">driver's licence number</span></span>  <br/> <span data-ttu-id="f5b73-306">número de licencia de fuerzas</span><span class="sxs-lookup"><span data-stu-id="f5b73-306">driving license number</span></span>  <br/> <span data-ttu-id="f5b73-307">dlno #</span><span class="sxs-lookup"><span data-stu-id="f5b73-307">dlno#</span></span>  <br/> <span data-ttu-id="f5b73-308">kørekort</span><span class="sxs-lookup"><span data-stu-id="f5b73-308">kørekort</span></span>  <br/> <span data-ttu-id="f5b73-309">kørekortnummer</span><span class="sxs-lookup"><span data-stu-id="f5b73-309">kørekortnummer</span></span>  <br/> |
   
## <a name="estonia"></a><span data-ttu-id="f5b73-310">Estonia</span><span class="sxs-lookup"><span data-stu-id="f5b73-310">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="f5b73-311">Formato</span><span class="sxs-lookup"><span data-stu-id="f5b73-311">Format</span></span>

<span data-ttu-id="f5b73-312">Dos letras seguidas por seis dígitos</span><span class="sxs-lookup"><span data-stu-id="f5b73-312">Two letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f5b73-313">Patrón</span><span class="sxs-lookup"><span data-stu-id="f5b73-313">Pattern</span></span>

<span data-ttu-id="f5b73-314">Dos letras y seis dígitos:</span><span class="sxs-lookup"><span data-stu-id="f5b73-314">Two letters and six digits:</span></span>
  
-  <span data-ttu-id="f5b73-315">Las letras "ET" (no distingue mayúsculas de minúsculas)</span><span class="sxs-lookup"><span data-stu-id="f5b73-315">The letters "ET" (not case-sensitive)</span></span> 
    
- <span data-ttu-id="f5b73-316">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="f5b73-316">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="f5b73-317">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="f5b73-317">Checksum</span></span>

<span data-ttu-id="f5b73-318">No</span><span class="sxs-lookup"><span data-stu-id="f5b73-318">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="f5b73-319">Definición</span><span class="sxs-lookup"><span data-stu-id="f5b73-319">Definition</span></span>

<span data-ttu-id="f5b73-320">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="f5b73-320">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f5b73-321">La expresión regular `Regex_estonia_eu_driver's_license_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="f5b73-321">The regular expression  `Regex_estonia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f5b73-322">Una palabra clave de `Keywords_estonia_eu_driver's_license_number` se encuentra.</span><span class="sxs-lookup"><span data-stu-id="f5b73-322">A keyword from  `Keywords_estonia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_driver's_license_number" />
          <Match idRef="Keywords_estonia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="f5b73-323">Keywords</span><span class="sxs-lookup"><span data-stu-id="f5b73-323">Keywords</span></span>

<span data-ttu-id="f5b73-324">| |</span><span class="sxs-lookup"><span data-stu-id="f5b73-324"></span></span>
|<span data-ttu-id="f5b73-325">**Keywords_estonia_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="f5b73-325">**Keywords_estonia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="f5b73-326">dl#</span><span class="sxs-lookup"><span data-stu-id="f5b73-326">dl#</span></span>  <br/> <span data-ttu-id="f5b73-327">permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="f5b73-327">driver license</span></span>  <br/> <span data-ttu-id="f5b73-328">número de licencia del controlador</span><span class="sxs-lookup"><span data-stu-id="f5b73-328">driver license number</span></span>  <br/> <span data-ttu-id="f5b73-329">número de licencia del controlador</span><span class="sxs-lookup"><span data-stu-id="f5b73-329">driver license number</span></span>  <br/> <span data-ttu-id="f5b73-330">licencia de controlador</span><span class="sxs-lookup"><span data-stu-id="f5b73-330">driver licence</span></span>  <br/> <span data-ttu-id="f5b73-331">lic de controladores.</span><span class="sxs-lookup"><span data-stu-id="f5b73-331">drivers lic.</span></span>  <br/> <span data-ttu-id="f5b73-332">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="f5b73-332">drivers license</span></span>  <br/> <span data-ttu-id="f5b73-333">drivers licence</span><span class="sxs-lookup"><span data-stu-id="f5b73-333">drivers licence</span></span>  <br/> <span data-ttu-id="f5b73-334">permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="f5b73-334">driver's license</span></span>  <br/> <span data-ttu-id="f5b73-335">número de licencia del controlador</span><span class="sxs-lookup"><span data-stu-id="f5b73-335">driver's license number</span></span>  <br/> <span data-ttu-id="f5b73-336">número de licencia de fuerzas</span><span class="sxs-lookup"><span data-stu-id="f5b73-336">driving license number</span></span>  <br/> <span data-ttu-id="f5b73-337">dlno #</span><span class="sxs-lookup"><span data-stu-id="f5b73-337">dlno#</span></span>  <br/> <span data-ttu-id="f5b73-338">
permis de conduire</span><span class="sxs-lookup"><span data-stu-id="f5b73-338">permis de conduire</span></span>  <br/> |
   
## <a name="finland"></a><span data-ttu-id="f5b73-339">Finlandia</span><span class="sxs-lookup"><span data-stu-id="f5b73-339">Finland</span></span>

### <a name="format"></a><span data-ttu-id="f5b73-340">Formato</span><span class="sxs-lookup"><span data-stu-id="f5b73-340">Format</span></span>

<span data-ttu-id="f5b73-341">10 dígitos que contienen un guión</span><span class="sxs-lookup"><span data-stu-id="f5b73-341">10 digits containing a hyphen</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f5b73-342">Patrón</span><span class="sxs-lookup"><span data-stu-id="f5b73-342">Pattern</span></span>

<span data-ttu-id="f5b73-343">10 dígitos que contiene un guión:</span><span class="sxs-lookup"><span data-stu-id="f5b73-343">10 digits containing a hyphen:</span></span>
  
-  <span data-ttu-id="f5b73-344">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="f5b73-344">Six digits</span></span> 
    
- <span data-ttu-id="f5b73-345">Un guion</span><span class="sxs-lookup"><span data-stu-id="f5b73-345">A hyphen</span></span>
    
-  <span data-ttu-id="f5b73-346">Cuatro dígitos</span><span class="sxs-lookup"><span data-stu-id="f5b73-346">Four digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="f5b73-347">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="f5b73-347">Checksum</span></span>

<span data-ttu-id="f5b73-348">No</span><span class="sxs-lookup"><span data-stu-id="f5b73-348">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="f5b73-349">Definición</span><span class="sxs-lookup"><span data-stu-id="f5b73-349">Definition</span></span>

<span data-ttu-id="f5b73-350">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="f5b73-350">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f5b73-351">La expresión regular `Regex_finland_eu_driver's_license_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="f5b73-351">The regular expression  `Regex_finland_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f5b73-352">Una palabra clave de `Keywords_finland_eu_driver's_license_number` se encuentra.</span><span class="sxs-lookup"><span data-stu-id="f5b73-352">A keyword from  `Keywords_finland_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_finland_eu_driver's_license_number" />
          <Match idRef="Keywords_finland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="f5b73-353">Keywords</span><span class="sxs-lookup"><span data-stu-id="f5b73-353">Keywords</span></span>

<span data-ttu-id="f5b73-354">| |</span><span class="sxs-lookup"><span data-stu-id="f5b73-354"></span></span>
|<span data-ttu-id="f5b73-355">**Keywords_finland_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="f5b73-355">**Keywords_finland_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="f5b73-356">dl#</span><span class="sxs-lookup"><span data-stu-id="f5b73-356">dl#</span></span>  <br/> <span data-ttu-id="f5b73-357">permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="f5b73-357">driver license</span></span>  <br/> <span data-ttu-id="f5b73-358">número de licencia del controlador</span><span class="sxs-lookup"><span data-stu-id="f5b73-358">driver license number</span></span>  <br/> <span data-ttu-id="f5b73-359">licencia de controlador</span><span class="sxs-lookup"><span data-stu-id="f5b73-359">driver licence</span></span>  <br/> <span data-ttu-id="f5b73-360">lic de controladores.</span><span class="sxs-lookup"><span data-stu-id="f5b73-360">drivers lic.</span></span>  <br/> <span data-ttu-id="f5b73-361">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="f5b73-361">drivers license</span></span>  <br/> <span data-ttu-id="f5b73-362">drivers licence</span><span class="sxs-lookup"><span data-stu-id="f5b73-362">drivers licence</span></span>  <br/> <span data-ttu-id="f5b73-363">permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="f5b73-363">driver's license</span></span>  <br/> <span data-ttu-id="f5b73-364">número de licencia del controlador</span><span class="sxs-lookup"><span data-stu-id="f5b73-364">driver's license number</span></span>  <br/> <span data-ttu-id="f5b73-365">número de la licencia del controlador</span><span class="sxs-lookup"><span data-stu-id="f5b73-365">driver's licence number</span></span>  <br/> <span data-ttu-id="f5b73-366">número de licencia de fuerzas</span><span class="sxs-lookup"><span data-stu-id="f5b73-366">driving license number</span></span>  <br/> <span data-ttu-id="f5b73-367">dlno #</span><span class="sxs-lookup"><span data-stu-id="f5b73-367">dlno#</span></span>  <br/> <span data-ttu-id="f5b73-368">ajokortti</span><span class="sxs-lookup"><span data-stu-id="f5b73-368">ajokortti</span></span>  <br/> |
   
## <a name="france"></a><span data-ttu-id="f5b73-369">Francia</span><span class="sxs-lookup"><span data-stu-id="f5b73-369">France</span></span>

<span data-ttu-id="f5b73-370">Para obtener información detallada, vea la sección "Número de licencia del controlador de Francia" en [Buscar qué los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="f5b73-370">For details, see the section "France Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="germany"></a><span data-ttu-id="f5b73-371">Alemania</span><span class="sxs-lookup"><span data-stu-id="f5b73-371">Germany</span></span>

<span data-ttu-id="f5b73-372">Para obtener información detallada, vea la sección "Número de licencia del controlador alemán" en [Buscar qué los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="f5b73-372">For details, see the section "German Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="greece"></a><span data-ttu-id="f5b73-373">Grecia</span><span class="sxs-lookup"><span data-stu-id="f5b73-373">Greece</span></span>

### <a name="format"></a><span data-ttu-id="f5b73-374">Formato</span><span class="sxs-lookup"><span data-stu-id="f5b73-374">Format</span></span>

<span data-ttu-id="f5b73-375">Nueve dígitos sin espacios y los delimitadores</span><span class="sxs-lookup"><span data-stu-id="f5b73-375">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f5b73-376">Patrón</span><span class="sxs-lookup"><span data-stu-id="f5b73-376">Pattern</span></span>

 <span data-ttu-id="f5b73-377">Nueve dígitos</span><span class="sxs-lookup"><span data-stu-id="f5b73-377">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="f5b73-378">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="f5b73-378">Checksum</span></span>

<span data-ttu-id="f5b73-379">No</span><span class="sxs-lookup"><span data-stu-id="f5b73-379">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="f5b73-380">Definición</span><span class="sxs-lookup"><span data-stu-id="f5b73-380">Definition</span></span>

<span data-ttu-id="f5b73-381">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="f5b73-381">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f5b73-382">La expresión regular `Regex_greece_eu_driver's_license_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="f5b73-382">The regular expression  `Regex_greece_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f5b73-383">Una palabra clave de `Keywords_greece_eu_driver's_license_number` se encuentra.</span><span class="sxs-lookup"><span data-stu-id="f5b73-383">A keyword from  `Keywords_greece_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_driver's_license_number" />
          <Match idRef="Keywords_greece_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="f5b73-384">Keywords</span><span class="sxs-lookup"><span data-stu-id="f5b73-384">Keywords</span></span>

<span data-ttu-id="f5b73-385">| |</span><span class="sxs-lookup"><span data-stu-id="f5b73-385"></span></span>
|<span data-ttu-id="f5b73-386">**Keywords_greece_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="f5b73-386">**Keywords_greece_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="f5b73-387">dlL #</span><span class="sxs-lookup"><span data-stu-id="f5b73-387">dlL#</span></span>  <br/> <span data-ttu-id="f5b73-388">permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="f5b73-388">driver license</span></span>  <br/> <span data-ttu-id="f5b73-389">número de licencia del controlador</span><span class="sxs-lookup"><span data-stu-id="f5b73-389">driver license number</span></span>  <br/> <span data-ttu-id="f5b73-390">licencia de controlador</span><span class="sxs-lookup"><span data-stu-id="f5b73-390">driver licence</span></span>  <br/> <span data-ttu-id="f5b73-391">lic de controladores.</span><span class="sxs-lookup"><span data-stu-id="f5b73-391">drivers lic.</span></span>  <br/> <span data-ttu-id="f5b73-392">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="f5b73-392">drivers license</span></span>  <br/> <span data-ttu-id="f5b73-393">drivers licence</span><span class="sxs-lookup"><span data-stu-id="f5b73-393">drivers licence</span></span>  <br/> <span data-ttu-id="f5b73-394">permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="f5b73-394">driver's license</span></span>  <br/> <span data-ttu-id="f5b73-395">número de licencia del controlador</span><span class="sxs-lookup"><span data-stu-id="f5b73-395">driver's license number</span></span>  <br/> <span data-ttu-id="f5b73-396">número de la licencia del controlador</span><span class="sxs-lookup"><span data-stu-id="f5b73-396">driver's licence number</span></span>  <br/> <span data-ttu-id="f5b73-397">número de licencia de fuerzas</span><span class="sxs-lookup"><span data-stu-id="f5b73-397">driving license number</span></span>  <br/> <span data-ttu-id="f5b73-398">dlno #</span><span class="sxs-lookup"><span data-stu-id="f5b73-398">dlno#</span></span>  <br/> <span data-ttu-id="f5b73-399">ΔΕΙΑ ΟΔΉΓΗΣΗΣ</span><span class="sxs-lookup"><span data-stu-id="f5b73-399">δεια οδήγησης</span></span>  <br/> <span data-ttu-id="f5b73-400">Adeia odigisis</span><span class="sxs-lookup"><span data-stu-id="f5b73-400">Adeia odigisis</span></span>  <br/> |
   
## <a name="hungary"></a><span data-ttu-id="f5b73-401">Hungría</span><span class="sxs-lookup"><span data-stu-id="f5b73-401">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="f5b73-402">Formato</span><span class="sxs-lookup"><span data-stu-id="f5b73-402">Format</span></span>

<span data-ttu-id="f5b73-403">Dos letras seguidas por seis dígitos</span><span class="sxs-lookup"><span data-stu-id="f5b73-403">Two letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f5b73-404">Patrón</span><span class="sxs-lookup"><span data-stu-id="f5b73-404">Pattern</span></span>

<span data-ttu-id="f5b73-405">Dos letras y seis dígitos:</span><span class="sxs-lookup"><span data-stu-id="f5b73-405">Two letters and six digits:</span></span>
  
-  <span data-ttu-id="f5b73-406">Dos letras (no distingue mayúsculas de minúsculas)</span><span class="sxs-lookup"><span data-stu-id="f5b73-406">Two letters (not case-sensitive)</span></span> 
    
- <span data-ttu-id="f5b73-407">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="f5b73-407">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="f5b73-408">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="f5b73-408">Checksum</span></span>

<span data-ttu-id="f5b73-409">No</span><span class="sxs-lookup"><span data-stu-id="f5b73-409">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="f5b73-410">Definición</span><span class="sxs-lookup"><span data-stu-id="f5b73-410">Definition</span></span>

<span data-ttu-id="f5b73-411">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="f5b73-411">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f5b73-412">La expresión regular `Regex_hungary_eu_driver's_license_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="f5b73-412">The regular expression  `Regex_hungary_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f5b73-413">Una palabra clave de `Keywords_hungary_eu_driver's_license_number` se encuentra.</span><span class="sxs-lookup"><span data-stu-id="f5b73-413">A keyword from  `Keywords_hungary_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_driver's_license_number" />
          <Match idRef="Keywords_hungary_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="f5b73-414">Keywords</span><span class="sxs-lookup"><span data-stu-id="f5b73-414">Keywords</span></span>

<span data-ttu-id="f5b73-415">| |</span><span class="sxs-lookup"><span data-stu-id="f5b73-415"></span></span>
|<span data-ttu-id="f5b73-416">**Keywords_hungary_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="f5b73-416">**Keywords_hungary_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="f5b73-417">dl#</span><span class="sxs-lookup"><span data-stu-id="f5b73-417">dl#</span></span>  <br/> <span data-ttu-id="f5b73-418">permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="f5b73-418">driver license</span></span>  <br/> <span data-ttu-id="f5b73-419">número de licencia del controlador</span><span class="sxs-lookup"><span data-stu-id="f5b73-419">driver license number</span></span>  <br/> <span data-ttu-id="f5b73-420">licencia de controlador</span><span class="sxs-lookup"><span data-stu-id="f5b73-420">driver licence</span></span>  <br/> <span data-ttu-id="f5b73-421">lic de controladores.</span><span class="sxs-lookup"><span data-stu-id="f5b73-421">drivers lic.</span></span>  <br/> <span data-ttu-id="f5b73-422">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="f5b73-422">drivers license</span></span>  <br/> <span data-ttu-id="f5b73-423">drivers licence</span><span class="sxs-lookup"><span data-stu-id="f5b73-423">drivers licence</span></span>  <br/> <span data-ttu-id="f5b73-424">permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="f5b73-424">driver's license</span></span>  <br/> <span data-ttu-id="f5b73-425">número de licencia del controlador</span><span class="sxs-lookup"><span data-stu-id="f5b73-425">driver's license number</span></span>  <br/> <span data-ttu-id="f5b73-426">número de la licencia del controlador</span><span class="sxs-lookup"><span data-stu-id="f5b73-426">driver's licence number</span></span>  <br/> <span data-ttu-id="f5b73-427">número de licencia de fuerzas</span><span class="sxs-lookup"><span data-stu-id="f5b73-427">driving license number</span></span>  <br/> <span data-ttu-id="f5b73-428">dlno #</span><span class="sxs-lookup"><span data-stu-id="f5b73-428">dlno#</span></span>  <br/> <span data-ttu-id="f5b73-429">vezetoi engedely</span><span class="sxs-lookup"><span data-stu-id="f5b73-429">vezetoi engedely</span></span>  <br/> |
   
## <a name="ireland"></a><span data-ttu-id="f5b73-430">Irlanda</span><span class="sxs-lookup"><span data-stu-id="f5b73-430">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="f5b73-431">Formato</span><span class="sxs-lookup"><span data-stu-id="f5b73-431">Format</span></span>

<span data-ttu-id="f5b73-432">Seis dígitos seguidos de cuatro letras</span><span class="sxs-lookup"><span data-stu-id="f5b73-432">Six digits followed by four letters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f5b73-433">Patrón</span><span class="sxs-lookup"><span data-stu-id="f5b73-433">Pattern</span></span>

<span data-ttu-id="f5b73-434">Seis dígitos y cuatro letras:</span><span class="sxs-lookup"><span data-stu-id="f5b73-434">Six digits and four letters:</span></span>
  
- <span data-ttu-id="f5b73-435">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="f5b73-435">Six digits</span></span>
    
- <span data-ttu-id="f5b73-436">Cuatro letras (no distingue mayúsculas de minúsculas)</span><span class="sxs-lookup"><span data-stu-id="f5b73-436">Four letters (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="f5b73-437">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="f5b73-437">Checksum</span></span>

<span data-ttu-id="f5b73-438">No</span><span class="sxs-lookup"><span data-stu-id="f5b73-438">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="f5b73-439">Definición</span><span class="sxs-lookup"><span data-stu-id="f5b73-439">Definition</span></span>

<span data-ttu-id="f5b73-440">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="f5b73-440">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f5b73-441">La expresión regular `Regex_ireland_eu_driver's_license_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="f5b73-441">The regular expression  `Regex_ireland_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f5b73-442">Una palabra clave de `Keywords_ireland_eu_driver's_license_number` se encuentra.</span><span class="sxs-lookup"><span data-stu-id="f5b73-442">A keyword from  `Keywords_ireland_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_driver's_license_number" />
          <Match idRef="Keywords_ireland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="f5b73-443">Keywords</span><span class="sxs-lookup"><span data-stu-id="f5b73-443">Keywords</span></span>

<span data-ttu-id="f5b73-444">| |</span><span class="sxs-lookup"><span data-stu-id="f5b73-444"></span></span>
|<span data-ttu-id="f5b73-445">**Keywords_ireland_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="f5b73-445">**Keywords_ireland_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="f5b73-446">dl#</span><span class="sxs-lookup"><span data-stu-id="f5b73-446">dl#</span></span>  <br/> <span data-ttu-id="f5b73-447">permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="f5b73-447">driver license</span></span>  <br/> <span data-ttu-id="f5b73-448">número de licencia del controlador</span><span class="sxs-lookup"><span data-stu-id="f5b73-448">driver license number</span></span>  <br/> <span data-ttu-id="f5b73-449">licencia de controlador</span><span class="sxs-lookup"><span data-stu-id="f5b73-449">driver licence</span></span>  <br/> <span data-ttu-id="f5b73-450">lic de controladores.</span><span class="sxs-lookup"><span data-stu-id="f5b73-450">drivers lic.</span></span>  <br/> <span data-ttu-id="f5b73-451">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="f5b73-451">drivers license</span></span>  <br/> <span data-ttu-id="f5b73-452">drivers licence</span><span class="sxs-lookup"><span data-stu-id="f5b73-452">drivers licence</span></span>  <br/> <span data-ttu-id="f5b73-453">permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="f5b73-453">driver's license</span></span>  <br/> <span data-ttu-id="f5b73-454">número de licencia del controlador</span><span class="sxs-lookup"><span data-stu-id="f5b73-454">driver's license number</span></span>  <br/> <span data-ttu-id="f5b73-455">número de la licencia del controlador</span><span class="sxs-lookup"><span data-stu-id="f5b73-455">driver's licence number</span></span>  <br/> <span data-ttu-id="f5b73-456">número de licencia de fuerzas</span><span class="sxs-lookup"><span data-stu-id="f5b73-456">driving license number</span></span>  <br/> <span data-ttu-id="f5b73-457">dlno #</span><span class="sxs-lookup"><span data-stu-id="f5b73-457">dlno#</span></span>  <br/> <span data-ttu-id="f5b73-458">ceadúnas tiomána</span><span class="sxs-lookup"><span data-stu-id="f5b73-458">ceadúnas tiomána</span></span>  <br/> |
   
## <a name="italy"></a><span data-ttu-id="f5b73-459">Italia</span><span class="sxs-lookup"><span data-stu-id="f5b73-459">Italy</span></span>

<span data-ttu-id="f5b73-460">Para obtener información detallada, vea la sección "Número de licencia del controlador de Italia" en [Buscar qué los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="f5b73-460">For details, see the section "Italy Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="latvia"></a><span data-ttu-id="f5b73-461">Letonia</span><span class="sxs-lookup"><span data-stu-id="f5b73-461">Latvia</span></span>

### <a name="format"></a><span data-ttu-id="f5b73-462">Formato</span><span class="sxs-lookup"><span data-stu-id="f5b73-462">Format</span></span>

<span data-ttu-id="f5b73-463">Tres letras seguidas de seis dígitos</span><span class="sxs-lookup"><span data-stu-id="f5b73-463">Three letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f5b73-464">Patrón</span><span class="sxs-lookup"><span data-stu-id="f5b73-464">Pattern</span></span>

<span data-ttu-id="f5b73-465">Tres letras y seis dígitos:</span><span class="sxs-lookup"><span data-stu-id="f5b73-465">Three letters and six digits:</span></span>
  
-  <span data-ttu-id="f5b73-466">Tres letras (no distingue mayúsculas de minúsculas)</span><span class="sxs-lookup"><span data-stu-id="f5b73-466">Three letters (not case-sensitive)</span></span> 
    
- <span data-ttu-id="f5b73-467">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="f5b73-467">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="f5b73-468">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="f5b73-468">Checksum</span></span>

<span data-ttu-id="f5b73-469">No</span><span class="sxs-lookup"><span data-stu-id="f5b73-469">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="f5b73-470">Definición</span><span class="sxs-lookup"><span data-stu-id="f5b73-470">Definition</span></span>

<span data-ttu-id="f5b73-471">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="f5b73-471">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f5b73-472">La expresión regular `Regex_latvia_eu_driver's_license_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="f5b73-472">The regular expression  `Regex_latvia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f5b73-473">Una palabra clave de `Keywords_latvia_eu_driver's_license_number` se encuentra.</span><span class="sxs-lookup"><span data-stu-id="f5b73-473">A keyword from  `Keywords_latvia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_driver's_license_number" />
          <Match idRef="Keywords_latvia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="f5b73-474">Keywords</span><span class="sxs-lookup"><span data-stu-id="f5b73-474">Keywords</span></span>

<span data-ttu-id="f5b73-475">| |</span><span class="sxs-lookup"><span data-stu-id="f5b73-475"></span></span>
|<span data-ttu-id="f5b73-476">**Keywords_latvia_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="f5b73-476">**Keywords_latvia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="f5b73-477">dl#</span><span class="sxs-lookup"><span data-stu-id="f5b73-477">dl#</span></span>  <br/> <span data-ttu-id="f5b73-478">permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="f5b73-478">driver license</span></span>  <br/> <span data-ttu-id="f5b73-479">número de licencia del controlador</span><span class="sxs-lookup"><span data-stu-id="f5b73-479">driver license number</span></span>  <br/> <span data-ttu-id="f5b73-480">licencia de controlador</span><span class="sxs-lookup"><span data-stu-id="f5b73-480">driver licence</span></span>  <br/> <span data-ttu-id="f5b73-481">lic de controladores.</span><span class="sxs-lookup"><span data-stu-id="f5b73-481">drivers lic.</span></span>  <br/> <span data-ttu-id="f5b73-482">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="f5b73-482">drivers license</span></span>  <br/> <span data-ttu-id="f5b73-483">drivers licence</span><span class="sxs-lookup"><span data-stu-id="f5b73-483">drivers licence</span></span>  <br/> <span data-ttu-id="f5b73-484">permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="f5b73-484">driver's license</span></span>  <br/> <span data-ttu-id="f5b73-485">número de licencia del controlador</span><span class="sxs-lookup"><span data-stu-id="f5b73-485">driver's license number</span></span>  <br/> <span data-ttu-id="f5b73-486">número de la licencia del controlador</span><span class="sxs-lookup"><span data-stu-id="f5b73-486">driver's licence number</span></span>  <br/> <span data-ttu-id="f5b73-487">número de licencia de fuerzas</span><span class="sxs-lookup"><span data-stu-id="f5b73-487">driving license number</span></span>  <br/> <span data-ttu-id="f5b73-488">dlno #</span><span class="sxs-lookup"><span data-stu-id="f5b73-488">dlno#</span></span>  <br/> <span data-ttu-id="f5b73-489">autovadītāja apliecība</span><span class="sxs-lookup"><span data-stu-id="f5b73-489">autovadītāja apliecība</span></span>  <br/> |
   
## <a name="lithuania"></a><span data-ttu-id="f5b73-490">Lituania</span><span class="sxs-lookup"><span data-stu-id="f5b73-490">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="f5b73-491">Formato</span><span class="sxs-lookup"><span data-stu-id="f5b73-491">Format</span></span>

<span data-ttu-id="f5b73-492">Ocho dígitos sin espacios y los delimitadores</span><span class="sxs-lookup"><span data-stu-id="f5b73-492">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f5b73-493">Patrón</span><span class="sxs-lookup"><span data-stu-id="f5b73-493">Pattern</span></span>

 <span data-ttu-id="f5b73-494">Ocho dígitos</span><span class="sxs-lookup"><span data-stu-id="f5b73-494">Eight digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="f5b73-495">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="f5b73-495">Checksum</span></span>

<span data-ttu-id="f5b73-496">No</span><span class="sxs-lookup"><span data-stu-id="f5b73-496">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="f5b73-497">Definición</span><span class="sxs-lookup"><span data-stu-id="f5b73-497">Definition</span></span>

<span data-ttu-id="f5b73-498">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="f5b73-498">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f5b73-499">La expresión regular `Regex_lithuania_eu_driver's_license_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="f5b73-499">The regular expression  `Regex_lithuania_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f5b73-500">Una palabra clave de `Keywords_lithuania_eu_driver's_license_number` se encuentra.</span><span class="sxs-lookup"><span data-stu-id="f5b73-500">A keyword from  `Keywords_lithuania_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_driver's_license_number" />
          <Match idRef="Keywords_lithuania_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="f5b73-501">Keywords</span><span class="sxs-lookup"><span data-stu-id="f5b73-501">Keywords</span></span>

<span data-ttu-id="f5b73-502">| |</span><span class="sxs-lookup"><span data-stu-id="f5b73-502"></span></span>
|<span data-ttu-id="f5b73-503">**Keywords_lithuania_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="f5b73-503">**Keywords_lithuania_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="f5b73-504">dl#</span><span class="sxs-lookup"><span data-stu-id="f5b73-504">dl#</span></span>  <br/> <span data-ttu-id="f5b73-505">permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="f5b73-505">driver license</span></span>  <br/> <span data-ttu-id="f5b73-506">número de licencia del controlador</span><span class="sxs-lookup"><span data-stu-id="f5b73-506">driver license number</span></span>  <br/> <span data-ttu-id="f5b73-507">licencia de controlador</span><span class="sxs-lookup"><span data-stu-id="f5b73-507">driver licence</span></span>  <br/> <span data-ttu-id="f5b73-508">lic de controladores.</span><span class="sxs-lookup"><span data-stu-id="f5b73-508">drivers lic.</span></span>  <br/> <span data-ttu-id="f5b73-509">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="f5b73-509">drivers license</span></span>  <br/> <span data-ttu-id="f5b73-510">drivers licence</span><span class="sxs-lookup"><span data-stu-id="f5b73-510">drivers licence</span></span>  <br/> <span data-ttu-id="f5b73-511">permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="f5b73-511">driver's license</span></span>  <br/> <span data-ttu-id="f5b73-512">número de licencia del controlador</span><span class="sxs-lookup"><span data-stu-id="f5b73-512">driver's license number</span></span>  <br/> <span data-ttu-id="f5b73-513">número de la licencia del controlador</span><span class="sxs-lookup"><span data-stu-id="f5b73-513">driver's licence number</span></span>  <br/> <span data-ttu-id="f5b73-514">número de licencia de fuerzas</span><span class="sxs-lookup"><span data-stu-id="f5b73-514">driving license number</span></span>  <br/> <span data-ttu-id="f5b73-515">dlno #</span><span class="sxs-lookup"><span data-stu-id="f5b73-515">dlno#</span></span>  <br/> <span data-ttu-id="f5b73-516">vairuotojo pažymėjimas</span><span class="sxs-lookup"><span data-stu-id="f5b73-516">vairuotojo pažymėjimas</span></span>  <br/> |
   
## <a name="luxemburg"></a><span data-ttu-id="f5b73-517">Luxemburgo</span><span class="sxs-lookup"><span data-stu-id="f5b73-517">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="f5b73-518">Formato</span><span class="sxs-lookup"><span data-stu-id="f5b73-518">Format</span></span>

<span data-ttu-id="f5b73-519">Seis dígitos sin espacios y los delimitadores</span><span class="sxs-lookup"><span data-stu-id="f5b73-519">Six digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f5b73-520">Patrón</span><span class="sxs-lookup"><span data-stu-id="f5b73-520">Pattern</span></span>

 <span data-ttu-id="f5b73-521">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="f5b73-521">Six digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="f5b73-522">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="f5b73-522">Checksum</span></span>

<span data-ttu-id="f5b73-523">No</span><span class="sxs-lookup"><span data-stu-id="f5b73-523">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="f5b73-524">Definición</span><span class="sxs-lookup"><span data-stu-id="f5b73-524">Definition</span></span>

<span data-ttu-id="f5b73-525">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="f5b73-525">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f5b73-526">La expresión regular `Regex_luxemburg_eu_driver's_license_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="f5b73-526">The regular expression  `Regex_luxemburg_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f5b73-527">Una palabra clave de `Keywords_luxemburg_eu_driver's_license_number` se encuentra.</span><span class="sxs-lookup"><span data-stu-id="f5b73-527">A keyword from  `Keywords_luxemburg_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_luxemburg_eu_driver's_license_number" />
          <Match idRef="Keywords_luxemburg_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="f5b73-528">Keywords</span><span class="sxs-lookup"><span data-stu-id="f5b73-528">Keywords</span></span>

<span data-ttu-id="f5b73-529">| |</span><span class="sxs-lookup"><span data-stu-id="f5b73-529"></span></span>
|<span data-ttu-id="f5b73-530">**Keywords_luxemburg_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="f5b73-530">**Keywords_luxemburg_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="f5b73-531">dl#</span><span class="sxs-lookup"><span data-stu-id="f5b73-531">dl#</span></span>  <br/> <span data-ttu-id="f5b73-532">permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="f5b73-532">driver license</span></span>  <br/> <span data-ttu-id="f5b73-533">número de licencia del controlador</span><span class="sxs-lookup"><span data-stu-id="f5b73-533">driver license number</span></span>  <br/> <span data-ttu-id="f5b73-534">licencia de controlador</span><span class="sxs-lookup"><span data-stu-id="f5b73-534">driver licence</span></span>  <br/> <span data-ttu-id="f5b73-535">lic de controladores.</span><span class="sxs-lookup"><span data-stu-id="f5b73-535">drivers lic.</span></span>  <br/> <span data-ttu-id="f5b73-536">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="f5b73-536">drivers license</span></span>  <br/> <span data-ttu-id="f5b73-537">drivers licence</span><span class="sxs-lookup"><span data-stu-id="f5b73-537">drivers licence</span></span>  <br/> <span data-ttu-id="f5b73-538">permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="f5b73-538">driver's license</span></span>  <br/> <span data-ttu-id="f5b73-539">número de licencia del controlador</span><span class="sxs-lookup"><span data-stu-id="f5b73-539">driver's license number</span></span>  <br/> <span data-ttu-id="f5b73-540">número de la licencia del controlador</span><span class="sxs-lookup"><span data-stu-id="f5b73-540">driver's licence number</span></span>  <br/> <span data-ttu-id="f5b73-541">número de licencia de fuerzas</span><span class="sxs-lookup"><span data-stu-id="f5b73-541">driving license number</span></span>  <br/> <span data-ttu-id="f5b73-542">dlno #</span><span class="sxs-lookup"><span data-stu-id="f5b73-542">dlno#</span></span>  <br/> <span data-ttu-id="f5b73-543">fahrerlaubnis</span><span class="sxs-lookup"><span data-stu-id="f5b73-543">fahrerlaubnis</span></span>  <br/> |
   
## <a name="malta"></a><span data-ttu-id="f5b73-544">Malta</span><span class="sxs-lookup"><span data-stu-id="f5b73-544">Malta</span></span>

### <a name="format"></a><span data-ttu-id="f5b73-545">Formato</span><span class="sxs-lookup"><span data-stu-id="f5b73-545">Format</span></span>

<span data-ttu-id="f5b73-546">Combinación de dos caracteres y seis dígitos en el patrón especificado</span><span class="sxs-lookup"><span data-stu-id="f5b73-546">Combination of two characters and six digits in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f5b73-547">Patrón</span><span class="sxs-lookup"><span data-stu-id="f5b73-547">Pattern</span></span>

<span data-ttu-id="f5b73-548">Combinación de dos caracteres y seis dígitos:</span><span class="sxs-lookup"><span data-stu-id="f5b73-548">Combination of two characters and six digits:</span></span>
  
- <span data-ttu-id="f5b73-549">Dos caracteres (dígitos o letras, no distingue mayúsculas de minúsculas)</span><span class="sxs-lookup"><span data-stu-id="f5b73-549">Two characters (digits or letters, not case-sensitive)</span></span>
    
- <span data-ttu-id="f5b73-550">Un espacio (opcional) </span><span class="sxs-lookup"><span data-stu-id="f5b73-550">A space (optional)</span></span>
    
- <span data-ttu-id="f5b73-551">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="f5b73-551">Three digits</span></span>
    
- <span data-ttu-id="f5b73-552">Un espacio (opcional) </span><span class="sxs-lookup"><span data-stu-id="f5b73-552">A space (optional)</span></span>
    
- <span data-ttu-id="f5b73-553">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="f5b73-553">Three digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="f5b73-554">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="f5b73-554">Checksum</span></span>

<span data-ttu-id="f5b73-555">No</span><span class="sxs-lookup"><span data-stu-id="f5b73-555">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="f5b73-556">Definición</span><span class="sxs-lookup"><span data-stu-id="f5b73-556">Definition</span></span>

<span data-ttu-id="f5b73-557">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="f5b73-557">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f5b73-558">La expresión regular `Regex_malta_eu_driver's_license_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="f5b73-558">The regular expression  `Regex_malta_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f5b73-559">Una palabra clave de `Keywords_malta_eu_driver's_license_number` se encuentra.</span><span class="sxs-lookup"><span data-stu-id="f5b73-559">A keyword from  `Keywords_malta_eu_driver's_license_number` is found.</span></span> 
    
```
<!-- EU Driver's License Number -->
 <Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_driver's_license_number" />
          <Match idRef="Keywords_malta_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="f5b73-560">Keywords</span><span class="sxs-lookup"><span data-stu-id="f5b73-560">Keywords</span></span>

<span data-ttu-id="f5b73-561">| |</span><span class="sxs-lookup"><span data-stu-id="f5b73-561"></span></span>
|<span data-ttu-id="f5b73-562">**Keywords_malta_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="f5b73-562">**Keywords_malta_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="f5b73-563">dl#</span><span class="sxs-lookup"><span data-stu-id="f5b73-563">dl#</span></span>  <br/> <span data-ttu-id="f5b73-564">permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="f5b73-564">driver license</span></span>  <br/> <span data-ttu-id="f5b73-565">número de licencia del controlador</span><span class="sxs-lookup"><span data-stu-id="f5b73-565">driver license number</span></span>  <br/> <span data-ttu-id="f5b73-566">licencia de controlador</span><span class="sxs-lookup"><span data-stu-id="f5b73-566">driver licence</span></span>  <br/> <span data-ttu-id="f5b73-567">lic de controladores.</span><span class="sxs-lookup"><span data-stu-id="f5b73-567">drivers lic.</span></span>  <br/> <span data-ttu-id="f5b73-568">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="f5b73-568">drivers license</span></span>  <br/> <span data-ttu-id="f5b73-569">drivers licence</span><span class="sxs-lookup"><span data-stu-id="f5b73-569">drivers licence</span></span>  <br/> <span data-ttu-id="f5b73-570">permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="f5b73-570">driver's license</span></span>  <br/> <span data-ttu-id="f5b73-571">número de licencia del controlador</span><span class="sxs-lookup"><span data-stu-id="f5b73-571">driver's license number</span></span>  <br/> <span data-ttu-id="f5b73-572">número de la licencia del controlador</span><span class="sxs-lookup"><span data-stu-id="f5b73-572">driver's licence number</span></span>  <br/> <span data-ttu-id="f5b73-573">número de licencia de fuerzas</span><span class="sxs-lookup"><span data-stu-id="f5b73-573">driving license number</span></span>  <br/> <span data-ttu-id="f5b73-574">dlno #</span><span class="sxs-lookup"><span data-stu-id="f5b73-574">dlno#</span></span>  <br/> <span data-ttu-id="f5b73-575">tareas de liċenzja-sewqan</span><span class="sxs-lookup"><span data-stu-id="f5b73-575">liċenzja tas-sewqan</span></span>  <br/> |
   
## <a name="netherlands"></a><span data-ttu-id="f5b73-576">Países Bajos</span><span class="sxs-lookup"><span data-stu-id="f5b73-576">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="f5b73-577">Formato</span><span class="sxs-lookup"><span data-stu-id="f5b73-577">Format</span></span>

<span data-ttu-id="f5b73-578">10 dígitos sin espacios y los delimitadores</span><span class="sxs-lookup"><span data-stu-id="f5b73-578">10 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f5b73-579">Patrón</span><span class="sxs-lookup"><span data-stu-id="f5b73-579">Pattern</span></span>

<span data-ttu-id="f5b73-580">10 dígitos</span><span class="sxs-lookup"><span data-stu-id="f5b73-580">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="f5b73-581">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="f5b73-581">Checksum</span></span>

<span data-ttu-id="f5b73-582">No</span><span class="sxs-lookup"><span data-stu-id="f5b73-582">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="f5b73-583">Definición</span><span class="sxs-lookup"><span data-stu-id="f5b73-583">Definition</span></span>

<span data-ttu-id="f5b73-584">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="f5b73-584">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f5b73-585">La expresión regular `Regex_netherlands_eu_driver's_license_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="f5b73-585">The regular expression  `Regex_netherlands_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f5b73-586">Una palabra clave de `Keywords_netherlands_eu_driver's_license_number` se encuentra.</span><span class="sxs-lookup"><span data-stu-id="f5b73-586">A keyword from  `Keywords_netherlands_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_driver's_license_number" />
          <Match idRef="Keywords_netherlands_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="f5b73-587">Keywords</span><span class="sxs-lookup"><span data-stu-id="f5b73-587">Keywords</span></span>

<span data-ttu-id="f5b73-588">| |</span><span class="sxs-lookup"><span data-stu-id="f5b73-588"></span></span>
|<span data-ttu-id="f5b73-589">**Keywords_netherlands_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="f5b73-589">**Keywords_netherlands_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="f5b73-590">dl#</span><span class="sxs-lookup"><span data-stu-id="f5b73-590">dl#</span></span>  <br/> <span data-ttu-id="f5b73-591">permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="f5b73-591">driver license</span></span>  <br/> <span data-ttu-id="f5b73-592">número de licencia del controlador</span><span class="sxs-lookup"><span data-stu-id="f5b73-592">driver license number</span></span>  <br/> <span data-ttu-id="f5b73-593">licencia de controlador</span><span class="sxs-lookup"><span data-stu-id="f5b73-593">driver licence</span></span>  <br/> <span data-ttu-id="f5b73-594">lic de controladores.</span><span class="sxs-lookup"><span data-stu-id="f5b73-594">drivers lic.</span></span>  <br/> <span data-ttu-id="f5b73-595">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="f5b73-595">drivers license</span></span>  <br/> <span data-ttu-id="f5b73-596">drivers licence</span><span class="sxs-lookup"><span data-stu-id="f5b73-596">drivers licence</span></span>  <br/> <span data-ttu-id="f5b73-597">permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="f5b73-597">driver's license</span></span>  <br/> <span data-ttu-id="f5b73-598">número de licencia del controlador</span><span class="sxs-lookup"><span data-stu-id="f5b73-598">driver's license number</span></span>  <br/> <span data-ttu-id="f5b73-599">número de la licencia del controlador</span><span class="sxs-lookup"><span data-stu-id="f5b73-599">driver's licence number</span></span>  <br/> <span data-ttu-id="f5b73-600">número de licencia de fuerzas</span><span class="sxs-lookup"><span data-stu-id="f5b73-600">driving license number</span></span>  <br/> <span data-ttu-id="f5b73-601">dlno #</span><span class="sxs-lookup"><span data-stu-id="f5b73-601">dlno#</span></span>  <br/> <span data-ttu-id="f5b73-602">
permis de conduire</span><span class="sxs-lookup"><span data-stu-id="f5b73-602">permis de conduire</span></span>  <br/> <span data-ttu-id="f5b73-603">rijbewijs</span><span class="sxs-lookup"><span data-stu-id="f5b73-603">rijbewijs</span></span>  <br/> <span data-ttu-id="f5b73-604">rijbewijsnummer</span><span class="sxs-lookup"><span data-stu-id="f5b73-604">rijbewijsnummer</span></span>  <br/> |
   
## <a name="poland"></a><span data-ttu-id="f5b73-605">Polonia</span><span class="sxs-lookup"><span data-stu-id="f5b73-605">Poland</span></span>

### <a name="format"></a><span data-ttu-id="f5b73-606">Formato</span><span class="sxs-lookup"><span data-stu-id="f5b73-606">Format</span></span>

<span data-ttu-id="f5b73-607">14 dígitos que contiene 2 barras diagonales</span><span class="sxs-lookup"><span data-stu-id="f5b73-607">14 digits containing 2 forward slashes</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f5b73-608">Patrón</span><span class="sxs-lookup"><span data-stu-id="f5b73-608">Pattern</span></span>

<span data-ttu-id="f5b73-609">14 dígitos y barras 2 diagonales:</span><span class="sxs-lookup"><span data-stu-id="f5b73-609">14 digits and 2 forward slashes:</span></span>
  
-  <span data-ttu-id="f5b73-610">Cinco dígitos</span><span class="sxs-lookup"><span data-stu-id="f5b73-610">Five digits</span></span> 
    
- <span data-ttu-id="f5b73-611">Una barra diagonal </span><span class="sxs-lookup"><span data-stu-id="f5b73-611">A forward slash</span></span>
    
- <span data-ttu-id="f5b73-612">Dos dígitos</span><span class="sxs-lookup"><span data-stu-id="f5b73-612">Two digits</span></span>
    
- <span data-ttu-id="f5b73-613">Una barra diagonal </span><span class="sxs-lookup"><span data-stu-id="f5b73-613">A forward slash</span></span>
    
- <span data-ttu-id="f5b73-614">Siete dígitos</span><span class="sxs-lookup"><span data-stu-id="f5b73-614">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="f5b73-615">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="f5b73-615">Checksum</span></span>

<span data-ttu-id="f5b73-616">No</span><span class="sxs-lookup"><span data-stu-id="f5b73-616">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="f5b73-617">Definición</span><span class="sxs-lookup"><span data-stu-id="f5b73-617">Definition</span></span>

<span data-ttu-id="f5b73-618">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="f5b73-618">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f5b73-619">La expresión regular `Regex_poland_eu_driver's_license_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="f5b73-619">The regular expression  `Regex_poland_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f5b73-620">Una palabra clave de `Keywords_poland_eu_driver's_license_number` se encuentra.</span><span class="sxs-lookup"><span data-stu-id="f5b73-620">A keyword from  `Keywords_poland_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_poland_eu_driver's_license_number" />
          <Match idRef="Keywords_poland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="f5b73-621">Keywords</span><span class="sxs-lookup"><span data-stu-id="f5b73-621">Keywords</span></span>

<span data-ttu-id="f5b73-622">| |</span><span class="sxs-lookup"><span data-stu-id="f5b73-622"></span></span>
|<span data-ttu-id="f5b73-623">**Keywords_poland_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="f5b73-623">**Keywords_poland_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="f5b73-624">dl#</span><span class="sxs-lookup"><span data-stu-id="f5b73-624">dl#</span></span>  <br/> <span data-ttu-id="f5b73-625">permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="f5b73-625">driver license</span></span>  <br/> <span data-ttu-id="f5b73-626">número de licencia del controlador</span><span class="sxs-lookup"><span data-stu-id="f5b73-626">driver license number</span></span>  <br/> <span data-ttu-id="f5b73-627">licencia de controlador</span><span class="sxs-lookup"><span data-stu-id="f5b73-627">driver licence</span></span>  <br/> <span data-ttu-id="f5b73-628">lic de controladores.</span><span class="sxs-lookup"><span data-stu-id="f5b73-628">drivers lic.</span></span>  <br/> <span data-ttu-id="f5b73-629">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="f5b73-629">drivers license</span></span>  <br/> <span data-ttu-id="f5b73-630">drivers licence</span><span class="sxs-lookup"><span data-stu-id="f5b73-630">drivers licence</span></span>  <br/> <span data-ttu-id="f5b73-631">permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="f5b73-631">driver's license</span></span>  <br/> <span data-ttu-id="f5b73-632">número de licencia del controlador</span><span class="sxs-lookup"><span data-stu-id="f5b73-632">driver's license number</span></span>  <br/> <span data-ttu-id="f5b73-633">número de la licencia del controlador</span><span class="sxs-lookup"><span data-stu-id="f5b73-633">driver's licence number</span></span>  <br/> <span data-ttu-id="f5b73-634">número de licencia de fuerzas</span><span class="sxs-lookup"><span data-stu-id="f5b73-634">driving license number</span></span>  <br/> <span data-ttu-id="f5b73-635">dlno #</span><span class="sxs-lookup"><span data-stu-id="f5b73-635">dlno#</span></span>  <br/> <span data-ttu-id="f5b73-636">prawo jazdy</span><span class="sxs-lookup"><span data-stu-id="f5b73-636">prawo jazdy</span></span>  <br/> |
   
## <a name="portugal"></a><span data-ttu-id="f5b73-637">Portugal</span><span class="sxs-lookup"><span data-stu-id="f5b73-637">Portugal</span></span>

### <a name="format"></a><span data-ttu-id="f5b73-638">Formato</span><span class="sxs-lookup"><span data-stu-id="f5b73-638">Format</span></span>

<span data-ttu-id="f5b73-639">Dos letras seguidas por un siete números en el patrón especificado</span><span class="sxs-lookup"><span data-stu-id="f5b73-639">Two letters followed by a seven numbers in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f5b73-640">Patrón</span><span class="sxs-lookup"><span data-stu-id="f5b73-640">Pattern</span></span>

<span data-ttu-id="f5b73-641">Dos letras seguidas por siete números con caracteres especiales:</span><span class="sxs-lookup"><span data-stu-id="f5b73-641">Two letters followed by seven numbers with special characters:</span></span>
  
-  <span data-ttu-id="f5b73-642">Dos letras (no distingue mayúsculas de minúsculas)</span><span class="sxs-lookup"><span data-stu-id="f5b73-642">Two letters (not case-sensitive)</span></span> 
    
- <span data-ttu-id="f5b73-643">Un guión </span><span class="sxs-lookup"><span data-stu-id="f5b73-643">A hyphen</span></span>
    
- <span data-ttu-id="f5b73-644">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="f5b73-644">Six digits</span></span>
    
- <span data-ttu-id="f5b73-645">Un espacio</span><span class="sxs-lookup"><span data-stu-id="f5b73-645">A space</span></span>
    
- <span data-ttu-id="f5b73-646">Un dígito</span><span class="sxs-lookup"><span data-stu-id="f5b73-646">One digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="f5b73-647">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="f5b73-647">Checksum</span></span>

<span data-ttu-id="f5b73-648">No</span><span class="sxs-lookup"><span data-stu-id="f5b73-648">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="f5b73-649">Definición</span><span class="sxs-lookup"><span data-stu-id="f5b73-649">Definition</span></span>

<span data-ttu-id="f5b73-650">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="f5b73-650">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f5b73-651">La expresión regular `Regex_portugal_eu_driver's_license_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="f5b73-651">The regular expression  `Regex_portugal_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f5b73-652">Una palabra clave de `Keywords_portugal_eu_driver's_license_number` se encuentra.</span><span class="sxs-lookup"><span data-stu-id="f5b73-652">A keyword from  `Keywords_portugal_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_driver's_license_number" />
          <Match idRef="Keywords_portugal_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="f5b73-653">Keywords</span><span class="sxs-lookup"><span data-stu-id="f5b73-653">Keywords</span></span>

<span data-ttu-id="f5b73-654">| |</span><span class="sxs-lookup"><span data-stu-id="f5b73-654"></span></span>
|<span data-ttu-id="f5b73-655">**Keywords_portugal_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="f5b73-655">**Keywords_portugal_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="f5b73-656">dl#</span><span class="sxs-lookup"><span data-stu-id="f5b73-656">dl#</span></span>  <br/> <span data-ttu-id="f5b73-657">permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="f5b73-657">driver license</span></span>  <br/> <span data-ttu-id="f5b73-658">número de licencia del controlador</span><span class="sxs-lookup"><span data-stu-id="f5b73-658">driver license number</span></span>  <br/> <span data-ttu-id="f5b73-659">licencia de controlador</span><span class="sxs-lookup"><span data-stu-id="f5b73-659">driver licence</span></span>  <br/> <span data-ttu-id="f5b73-660">lic de controladores.</span><span class="sxs-lookup"><span data-stu-id="f5b73-660">drivers lic.</span></span>  <br/> <span data-ttu-id="f5b73-661">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="f5b73-661">drivers license</span></span>  <br/> <span data-ttu-id="f5b73-662">drivers licence</span><span class="sxs-lookup"><span data-stu-id="f5b73-662">drivers licence</span></span>  <br/> <span data-ttu-id="f5b73-663">permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="f5b73-663">driver's license</span></span>  <br/> <span data-ttu-id="f5b73-664">número de licencia del controlador</span><span class="sxs-lookup"><span data-stu-id="f5b73-664">driver's license number</span></span>  <br/> <span data-ttu-id="f5b73-665">número de la licencia del controlador</span><span class="sxs-lookup"><span data-stu-id="f5b73-665">driver's licence number</span></span>  <br/> <span data-ttu-id="f5b73-666">número de licencia de fuerzas</span><span class="sxs-lookup"><span data-stu-id="f5b73-666">driving license number</span></span>  <br/> <span data-ttu-id="f5b73-667">dlno #</span><span class="sxs-lookup"><span data-stu-id="f5b73-667">dlno#</span></span>  <br/> <span data-ttu-id="f5b73-668">carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="f5b73-668">carteira de motorista</span></span>  <br/> |
   
## <a name="romania"></a><span data-ttu-id="f5b73-669">Rumania</span><span class="sxs-lookup"><span data-stu-id="f5b73-669">Romania</span></span>

### <a name="format"></a><span data-ttu-id="f5b73-670">Formato</span><span class="sxs-lookup"><span data-stu-id="f5b73-670">Format</span></span>

<span data-ttu-id="f5b73-671">Un carácter seguido de ocho dígitos</span><span class="sxs-lookup"><span data-stu-id="f5b73-671">One character followed by eight digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f5b73-672">Patrón</span><span class="sxs-lookup"><span data-stu-id="f5b73-672">Pattern</span></span>

<span data-ttu-id="f5b73-673">Un carácter seguido de ocho dígitos:</span><span class="sxs-lookup"><span data-stu-id="f5b73-673">One character followed by eight digits:</span></span>
  
-  <span data-ttu-id="f5b73-674">Una letra (no distingue mayúsculas de minúsculas) o un dígito</span><span class="sxs-lookup"><span data-stu-id="f5b73-674">One letter (not case-sensitive) or digit</span></span> 
    
- <span data-ttu-id="f5b73-675">Ocho dígitos</span><span class="sxs-lookup"><span data-stu-id="f5b73-675">Eight digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="f5b73-676">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="f5b73-676">Checksum</span></span>

<span data-ttu-id="f5b73-677">No</span><span class="sxs-lookup"><span data-stu-id="f5b73-677">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="f5b73-678">Definición</span><span class="sxs-lookup"><span data-stu-id="f5b73-678">Definition</span></span>

<span data-ttu-id="f5b73-679">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="f5b73-679">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f5b73-680">La expresión regular `Regex_romania_eu_driver's_license_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="f5b73-680">The regular expression  `Regex_romania_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f5b73-681">Una palabra clave de `Keywords_romania_eu_driver's_license_number` se encuentra.</span><span class="sxs-lookup"><span data-stu-id="f5b73-681">A keyword from  `Keywords_romania_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_driver's_license_number" />
          <Match idRef="Keywords_romania_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="f5b73-682">Keywords</span><span class="sxs-lookup"><span data-stu-id="f5b73-682">Keywords</span></span>

<span data-ttu-id="f5b73-683">| |</span><span class="sxs-lookup"><span data-stu-id="f5b73-683"></span></span>
|<span data-ttu-id="f5b73-684">**Keywords_romania_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="f5b73-684">**Keywords_romania_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="f5b73-685">dl#</span><span class="sxs-lookup"><span data-stu-id="f5b73-685">dl#</span></span>  <br/> <span data-ttu-id="f5b73-686">permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="f5b73-686">driver license</span></span>  <br/> <span data-ttu-id="f5b73-687">número de licencia del controlador</span><span class="sxs-lookup"><span data-stu-id="f5b73-687">driver license number</span></span>  <br/> <span data-ttu-id="f5b73-688">licencia de controlador</span><span class="sxs-lookup"><span data-stu-id="f5b73-688">driver licence</span></span>  <br/> <span data-ttu-id="f5b73-689">lic de controladores.</span><span class="sxs-lookup"><span data-stu-id="f5b73-689">drivers lic.</span></span>  <br/> <span data-ttu-id="f5b73-690">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="f5b73-690">drivers license</span></span>  <br/> <span data-ttu-id="f5b73-691">drivers licence</span><span class="sxs-lookup"><span data-stu-id="f5b73-691">drivers licence</span></span>  <br/> <span data-ttu-id="f5b73-692">permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="f5b73-692">driver's license</span></span>  <br/> <span data-ttu-id="f5b73-693">número de licencia del controlador</span><span class="sxs-lookup"><span data-stu-id="f5b73-693">driver's license number</span></span>  <br/> <span data-ttu-id="f5b73-694">número de la licencia del controlador</span><span class="sxs-lookup"><span data-stu-id="f5b73-694">driver's licence number</span></span>  <br/> <span data-ttu-id="f5b73-695">número de licencia de fuerzas</span><span class="sxs-lookup"><span data-stu-id="f5b73-695">driving license number</span></span>  <br/> <span data-ttu-id="f5b73-696">dlno #</span><span class="sxs-lookup"><span data-stu-id="f5b73-696">dlno#</span></span>  <br/> <span data-ttu-id="f5b73-697">Permis de conducere</span><span class="sxs-lookup"><span data-stu-id="f5b73-697">permis de conducere</span></span>  <br/> |
   
## <a name="slovakia"></a><span data-ttu-id="f5b73-698">Eslovaquia</span><span class="sxs-lookup"><span data-stu-id="f5b73-698">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="f5b73-699">Formato</span><span class="sxs-lookup"><span data-stu-id="f5b73-699">Format</span></span>

<span data-ttu-id="f5b73-700">Un carácter seguido de siete dígitos</span><span class="sxs-lookup"><span data-stu-id="f5b73-700">One character followed by seven digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f5b73-701">Patrón</span><span class="sxs-lookup"><span data-stu-id="f5b73-701">Pattern</span></span>

<span data-ttu-id="f5b73-702">Un carácter seguido de siete dígitos</span><span class="sxs-lookup"><span data-stu-id="f5b73-702">One character followed by seven digits</span></span>
  
- <span data-ttu-id="f5b73-703">Una letra (no distingue mayúsculas de minúsculas) o un dígito</span><span class="sxs-lookup"><span data-stu-id="f5b73-703">One letter (not case-sensitive) or digit</span></span>
    
-  <span data-ttu-id="f5b73-704">Siete dígitos</span><span class="sxs-lookup"><span data-stu-id="f5b73-704">Seven digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="f5b73-705">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="f5b73-705">Checksum</span></span>

<span data-ttu-id="f5b73-706">No</span><span class="sxs-lookup"><span data-stu-id="f5b73-706">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="f5b73-707">Definición</span><span class="sxs-lookup"><span data-stu-id="f5b73-707">Definition</span></span>

<span data-ttu-id="f5b73-708">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="f5b73-708">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f5b73-709">La expresión regular `Regex_slovakia_eu_driver's_license_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="f5b73-709">The regular expression  `Regex_slovakia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f5b73-710">Una palabra clave de `Keywords_slovakia_eu_driver's_license_number` se encuentra.</span><span class="sxs-lookup"><span data-stu-id="f5b73-710">A keyword from  `Keywords_slovakia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovaknia_eu_driver's_license_number" />
          <Match idRef="Keywords_slovakia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="f5b73-711">Keywords</span><span class="sxs-lookup"><span data-stu-id="f5b73-711">Keywords</span></span>

<span data-ttu-id="f5b73-712">| |</span><span class="sxs-lookup"><span data-stu-id="f5b73-712"></span></span>
|<span data-ttu-id="f5b73-713">**Keywords_slovakia_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="f5b73-713">**Keywords_slovakia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="f5b73-714">dl#</span><span class="sxs-lookup"><span data-stu-id="f5b73-714">dl#</span></span>  <br/> <span data-ttu-id="f5b73-715">permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="f5b73-715">driver license</span></span>  <br/> <span data-ttu-id="f5b73-716">número de licencia del controlador</span><span class="sxs-lookup"><span data-stu-id="f5b73-716">driver license number</span></span>  <br/> <span data-ttu-id="f5b73-717">licencia de controlador</span><span class="sxs-lookup"><span data-stu-id="f5b73-717">driver licence</span></span>  <br/> <span data-ttu-id="f5b73-718">lic de controladores.</span><span class="sxs-lookup"><span data-stu-id="f5b73-718">drivers lic.</span></span>  <br/> <span data-ttu-id="f5b73-719">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="f5b73-719">drivers license</span></span>  <br/> <span data-ttu-id="f5b73-720">drivers licence</span><span class="sxs-lookup"><span data-stu-id="f5b73-720">drivers licence</span></span>  <br/> <span data-ttu-id="f5b73-721">permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="f5b73-721">driver's license</span></span>  <br/> <span data-ttu-id="f5b73-722">número de licencia del controlador</span><span class="sxs-lookup"><span data-stu-id="f5b73-722">driver's license number</span></span>  <br/> <span data-ttu-id="f5b73-723">número de la licencia del controlador</span><span class="sxs-lookup"><span data-stu-id="f5b73-723">driver's licence number</span></span>  <br/> <span data-ttu-id="f5b73-724">número de licencia de fuerzas</span><span class="sxs-lookup"><span data-stu-id="f5b73-724">driving license number</span></span>  <br/> <span data-ttu-id="f5b73-725">dlno #</span><span class="sxs-lookup"><span data-stu-id="f5b73-725">dlno#</span></span>  <br/> <span data-ttu-id="f5b73-726">vodičský preukaz</span><span class="sxs-lookup"><span data-stu-id="f5b73-726">vodičský preukaz</span></span>  <br/> |
   
## <a name="slovenia"></a><span data-ttu-id="f5b73-727">Eslovenia</span><span class="sxs-lookup"><span data-stu-id="f5b73-727">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="f5b73-728">Formato</span><span class="sxs-lookup"><span data-stu-id="f5b73-728">Format</span></span>

<span data-ttu-id="f5b73-729">Nueve dígitos sin espacios y los delimitadores</span><span class="sxs-lookup"><span data-stu-id="f5b73-729">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f5b73-730">Patrón</span><span class="sxs-lookup"><span data-stu-id="f5b73-730">Pattern</span></span>

<span data-ttu-id="f5b73-731">Nueve dígitos</span><span class="sxs-lookup"><span data-stu-id="f5b73-731">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="f5b73-732">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="f5b73-732">Checksum</span></span>

<span data-ttu-id="f5b73-733">No</span><span class="sxs-lookup"><span data-stu-id="f5b73-733">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="f5b73-734">Definición</span><span class="sxs-lookup"><span data-stu-id="f5b73-734">Definition</span></span>

<span data-ttu-id="f5b73-735">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="f5b73-735">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f5b73-736">La expresión regular `Regex_slovenia_eu_driver's_license_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="f5b73-736">The regular expression  `Regex_slovenia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f5b73-737">Una palabra clave de `Keywords_slovenia_eu_driver's_license_number` se encuentra.</span><span class="sxs-lookup"><span data-stu-id="f5b73-737">A keyword from  `Keywords_slovenia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_driver's_license_number" />
          <Match idRef="Keywords_slovenia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="f5b73-738">Keywords</span><span class="sxs-lookup"><span data-stu-id="f5b73-738">Keywords</span></span>

<span data-ttu-id="f5b73-739">| |</span><span class="sxs-lookup"><span data-stu-id="f5b73-739"></span></span>
|<span data-ttu-id="f5b73-740">**Keywords_slovenia_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="f5b73-740">**Keywords_slovenia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="f5b73-741">dl#</span><span class="sxs-lookup"><span data-stu-id="f5b73-741">dl#</span></span>  <br/> <span data-ttu-id="f5b73-742">permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="f5b73-742">driver license</span></span>  <br/> <span data-ttu-id="f5b73-743">número de licencia del controlador</span><span class="sxs-lookup"><span data-stu-id="f5b73-743">driver license number</span></span>  <br/> <span data-ttu-id="f5b73-744">licencia de controlador</span><span class="sxs-lookup"><span data-stu-id="f5b73-744">driver licence</span></span>  <br/> <span data-ttu-id="f5b73-745">lic de controladores.</span><span class="sxs-lookup"><span data-stu-id="f5b73-745">drivers lic.</span></span>  <br/> <span data-ttu-id="f5b73-746">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="f5b73-746">drivers license</span></span>  <br/> <span data-ttu-id="f5b73-747">drivers licence</span><span class="sxs-lookup"><span data-stu-id="f5b73-747">drivers licence</span></span>  <br/> <span data-ttu-id="f5b73-748">permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="f5b73-748">driver's license</span></span>  <br/> <span data-ttu-id="f5b73-749">número de licencia del controlador</span><span class="sxs-lookup"><span data-stu-id="f5b73-749">driver's license number</span></span>  <br/> <span data-ttu-id="f5b73-750">número de la licencia del controlador</span><span class="sxs-lookup"><span data-stu-id="f5b73-750">driver's licence number</span></span>  <br/> <span data-ttu-id="f5b73-751">número de licencia de fuerzas</span><span class="sxs-lookup"><span data-stu-id="f5b73-751">driving license number</span></span>  <br/> <span data-ttu-id="f5b73-752">dlno #</span><span class="sxs-lookup"><span data-stu-id="f5b73-752">dlno#</span></span>  <br/> <span data-ttu-id="f5b73-753">vozniško dovoljenje</span><span class="sxs-lookup"><span data-stu-id="f5b73-753">vozniško dovoljenje</span></span>  <br/> |
   
## <a name="spain"></a><span data-ttu-id="f5b73-754">España</span><span class="sxs-lookup"><span data-stu-id="f5b73-754">Spain</span></span>

### <a name="format"></a><span data-ttu-id="f5b73-755">Formato</span><span class="sxs-lookup"><span data-stu-id="f5b73-755">Format</span></span>

<span data-ttu-id="f5b73-756">Ocho dígitos seguidos de un carácter</span><span class="sxs-lookup"><span data-stu-id="f5b73-756">Eight digits followed by one character</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f5b73-757">Patrón</span><span class="sxs-lookup"><span data-stu-id="f5b73-757">Pattern</span></span>

<span data-ttu-id="f5b73-758">Ocho dígitos seguidos de un carácter:</span><span class="sxs-lookup"><span data-stu-id="f5b73-758">Eight digits followed by one character:</span></span>
  
-  <span data-ttu-id="f5b73-759">Ocho dígitos</span><span class="sxs-lookup"><span data-stu-id="f5b73-759">Eight digits</span></span> 
    
- <span data-ttu-id="f5b73-760">Un dígito o letra (no distingue mayúsculas de minúsculas)</span><span class="sxs-lookup"><span data-stu-id="f5b73-760">One digit or letter (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="f5b73-761">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="f5b73-761">Checksum</span></span>

<span data-ttu-id="f5b73-762">Sí</span><span class="sxs-lookup"><span data-stu-id="f5b73-762">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="f5b73-763">Definición</span><span class="sxs-lookup"><span data-stu-id="f5b73-763">Definition</span></span>

<span data-ttu-id="f5b73-764">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="f5b73-764">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f5b73-765">La función `Func_spain_eu_driver's_license_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="f5b73-765">The function  `Func_spain_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f5b73-766">Una palabra clave de `Keywords_spain_eu_driver's_license_number` se encuentra.</span><span class="sxs-lookup"><span data-stu-id="f5b73-766">A keyword from  `Keywords_spain_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spain_eu_driver's_license_number" />
          <Match idRef="Keywords_spain_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="f5b73-767">Keywords</span><span class="sxs-lookup"><span data-stu-id="f5b73-767">Keywords</span></span>

<span data-ttu-id="f5b73-768">| |</span><span class="sxs-lookup"><span data-stu-id="f5b73-768"></span></span>
|<span data-ttu-id="f5b73-769">**Keywords_spain_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="f5b73-769">**Keywords_spain_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="f5b73-770">dlno #</span><span class="sxs-lookup"><span data-stu-id="f5b73-770">dlno#</span></span>  <br/> <span data-ttu-id="f5b73-771">dl#</span><span class="sxs-lookup"><span data-stu-id="f5b73-771">dl#</span></span>  <br/> <span data-ttu-id="f5b73-772">lic de controladores.</span><span class="sxs-lookup"><span data-stu-id="f5b73-772">drivers lic.</span></span>  <br/> <span data-ttu-id="f5b73-773">licencia de controlador</span><span class="sxs-lookup"><span data-stu-id="f5b73-773">driver licence</span></span>  <br/> <span data-ttu-id="f5b73-774">permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="f5b73-774">driver license</span></span>  <br/> <span data-ttu-id="f5b73-775">drivers licence</span><span class="sxs-lookup"><span data-stu-id="f5b73-775">drivers licence</span></span>  <br/> <span data-ttu-id="f5b73-776">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="f5b73-776">drivers license</span></span>  <br/> <span data-ttu-id="f5b73-777">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="f5b73-777">driver's licence</span></span>  <br/> <span data-ttu-id="f5b73-778">permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="f5b73-778">driver's license</span></span>  <br/> <span data-ttu-id="f5b73-779">driving licence
</span><span class="sxs-lookup"><span data-stu-id="f5b73-779">driving licence</span></span>  <br/> <span data-ttu-id="f5b73-780">licencia fuerzas</span><span class="sxs-lookup"><span data-stu-id="f5b73-780">driving license</span></span>  <br/> <span data-ttu-id="f5b73-781">número de licencia del controlador</span><span class="sxs-lookup"><span data-stu-id="f5b73-781">driver licence number</span></span>  <br/> <span data-ttu-id="f5b73-782">número de licencia del controlador</span><span class="sxs-lookup"><span data-stu-id="f5b73-782">driver license number</span></span>  <br/> <span data-ttu-id="f5b73-783">número de solicitudes de certificado de controladores</span><span class="sxs-lookup"><span data-stu-id="f5b73-783">drivers licence number</span></span>  <br/> <span data-ttu-id="f5b73-784">número de licencia de controladores</span><span class="sxs-lookup"><span data-stu-id="f5b73-784">drivers license number</span></span>  <br/> <span data-ttu-id="f5b73-785">número de la licencia del controlador</span><span class="sxs-lookup"><span data-stu-id="f5b73-785">driver's licence number</span></span>  <br/> <span data-ttu-id="f5b73-786">número de licencia del controlador</span><span class="sxs-lookup"><span data-stu-id="f5b73-786">driver's license number</span></span>  <br/> <span data-ttu-id="f5b73-787">número de permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="f5b73-787">driving licence number</span></span>  <br/> <span data-ttu-id="f5b73-788">número de licencia de fuerzas</span><span class="sxs-lookup"><span data-stu-id="f5b73-788">driving license number</span></span>  <br/> <span data-ttu-id="f5b73-789">que manejan el permiso</span><span class="sxs-lookup"><span data-stu-id="f5b73-789">driving permit</span></span>  <br/> <span data-ttu-id="f5b73-790">número del permiso de fuerzas</span><span class="sxs-lookup"><span data-stu-id="f5b73-790">driving permit number</span></span>  <br/> <span data-ttu-id="f5b73-791">permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="f5b73-791">permiso de conducción</span></span>  <br/> <span data-ttu-id="f5b73-792">conducción de permiso</span><span class="sxs-lookup"><span data-stu-id="f5b73-792">permiso conducción</span></span>  <br/> <span data-ttu-id="f5b73-793">número licencia conducir</span><span class="sxs-lookup"><span data-stu-id="f5b73-793">número licencia conducir</span></span>  <br/> <span data-ttu-id="f5b73-794">número de cuaderno de conducir</span><span class="sxs-lookup"><span data-stu-id="f5b73-794">número de carnet de conducir</span></span>  <br/> <span data-ttu-id="f5b73-795">número cuaderno conducir</span><span class="sxs-lookup"><span data-stu-id="f5b73-795">número carnet conducir</span></span>  <br/> <span data-ttu-id="f5b73-796">licencia conducir</span><span class="sxs-lookup"><span data-stu-id="f5b73-796">licencia conducir</span></span>  <br/> <span data-ttu-id="f5b73-797">número de permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="f5b73-797">número de permiso de conducir</span></span>  <br/> <span data-ttu-id="f5b73-798">número de permiso conducir</span><span class="sxs-lookup"><span data-stu-id="f5b73-798">número de permiso conducir</span></span>  <br/> <span data-ttu-id="f5b73-799">número permiso conducir</span><span class="sxs-lookup"><span data-stu-id="f5b73-799">número permiso conducir</span></span>  <br/> <span data-ttu-id="f5b73-800">permiso conducir</span><span class="sxs-lookup"><span data-stu-id="f5b73-800">permiso conducir</span></span>  <br/> <span data-ttu-id="f5b73-801">licencia de manejo</span><span class="sxs-lookup"><span data-stu-id="f5b73-801">licencia de manejo</span></span>  <br/> <span data-ttu-id="f5b73-802">el cuaderno de conducir</span><span class="sxs-lookup"><span data-stu-id="f5b73-802">el carnet de conducir</span></span>  <br/> <span data-ttu-id="f5b73-803">Cuaderno conducir</span><span class="sxs-lookup"><span data-stu-id="f5b73-803">carnet conducir</span></span>  <br/> |
   
## <a name="sweden"></a><span data-ttu-id="f5b73-804">Suecia</span><span class="sxs-lookup"><span data-stu-id="f5b73-804">Sweden</span></span>

### <a name="format"></a><span data-ttu-id="f5b73-805">Formato</span><span class="sxs-lookup"><span data-stu-id="f5b73-805">Format</span></span>

<span data-ttu-id="f5b73-806">Diez dígitos que contiene un guión</span><span class="sxs-lookup"><span data-stu-id="f5b73-806">Ten digits containing a hyphen</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f5b73-807">Patrón</span><span class="sxs-lookup"><span data-stu-id="f5b73-807">Pattern</span></span>

<span data-ttu-id="f5b73-808">Diez dígitos que contiene un guión:</span><span class="sxs-lookup"><span data-stu-id="f5b73-808">Ten digits containing a hyphen:</span></span>
  
-  <span data-ttu-id="f5b73-809">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="f5b73-809">Six digits</span></span> 
    
- <span data-ttu-id="f5b73-810">Un guion</span><span class="sxs-lookup"><span data-stu-id="f5b73-810">A hyphen</span></span>
    
- <span data-ttu-id="f5b73-811">Cuatro dígitos</span><span class="sxs-lookup"><span data-stu-id="f5b73-811">Four digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="f5b73-812">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="f5b73-812">Checksum</span></span>

<span data-ttu-id="f5b73-813">No</span><span class="sxs-lookup"><span data-stu-id="f5b73-813">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="f5b73-814">Definición</span><span class="sxs-lookup"><span data-stu-id="f5b73-814">Definition</span></span>

<span data-ttu-id="f5b73-815">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="f5b73-815">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f5b73-816">La expresión regular `Regex_sweden_eu_driver's_license_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="f5b73-816">The regular expression  `Regex_sweden_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f5b73-817">Una palabra clave de `Keywords_sweden_eu_driver's_license_number` se encuentra.</span><span class="sxs-lookup"><span data-stu-id="f5b73-817">A keyword from  `Keywords_sweden_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_sweden_eu_driver's_license_number" />
          <Match idRef="Keywords_sweden_eu_driver's_license_number" />
        </Pattern>
</Entity> 
```

### <a name="keywords"></a><span data-ttu-id="f5b73-818">Keywords</span><span class="sxs-lookup"><span data-stu-id="f5b73-818">Keywords</span></span>

<span data-ttu-id="f5b73-819">| |</span><span class="sxs-lookup"><span data-stu-id="f5b73-819"></span></span>
|<span data-ttu-id="f5b73-820">**Keywords_sweden_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="f5b73-820">**Keywords_sweden_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="f5b73-821">dl#</span><span class="sxs-lookup"><span data-stu-id="f5b73-821">dl#</span></span>  <br/> <span data-ttu-id="f5b73-822">permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="f5b73-822">driver license</span></span>  <br/> <span data-ttu-id="f5b73-823">número de licencia del controlador</span><span class="sxs-lookup"><span data-stu-id="f5b73-823">driver license number</span></span>  <br/> <span data-ttu-id="f5b73-824">licencia de controlador</span><span class="sxs-lookup"><span data-stu-id="f5b73-824">driver licence</span></span>  <br/> <span data-ttu-id="f5b73-825">lic de controladores.</span><span class="sxs-lookup"><span data-stu-id="f5b73-825">drivers lic.</span></span>  <br/> <span data-ttu-id="f5b73-826">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="f5b73-826">drivers license</span></span>  <br/> <span data-ttu-id="f5b73-827">drivers licence</span><span class="sxs-lookup"><span data-stu-id="f5b73-827">drivers licence</span></span>  <br/> <span data-ttu-id="f5b73-828">permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="f5b73-828">driver's license</span></span>  <br/> <span data-ttu-id="f5b73-829">número de licencia del controlador</span><span class="sxs-lookup"><span data-stu-id="f5b73-829">driver's license number</span></span>  <br/> <span data-ttu-id="f5b73-830">número de la licencia del controlador</span><span class="sxs-lookup"><span data-stu-id="f5b73-830">driver's licence number</span></span>  <br/> <span data-ttu-id="f5b73-831">número de licencia de fuerzas</span><span class="sxs-lookup"><span data-stu-id="f5b73-831">driving license number</span></span>  <br/> <span data-ttu-id="f5b73-832">dlno #</span><span class="sxs-lookup"><span data-stu-id="f5b73-832">dlno#</span></span>  <br/> <span data-ttu-id="f5b73-833">körkort</span><span class="sxs-lookup"><span data-stu-id="f5b73-833">körkort</span></span>  <br/> |
   
## <a name="uk"></a><span data-ttu-id="f5b73-834">REINO UNIDO</span><span class="sxs-lookup"><span data-stu-id="f5b73-834">UK</span></span>

<span data-ttu-id="f5b73-p103">Para obtener información detallada, vea la sección "Número de licencia del Reino Unido conductor" en [Buscar qué los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="f5b73-p103">For details, see the section "U.K. Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="f5b73-837">Vea también</span><span class="sxs-lookup"><span data-stu-id="f5b73-837">See also</span></span>

[<span data-ttu-id="f5b73-838">Qué buscan los tipos de información confidencial</span><span class="sxs-lookup"><span data-stu-id="f5b73-838">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

