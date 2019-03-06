---
title: Número de permiso de conducción de la UE
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/17/2018
ms.audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
description: En este tema se muestra qué busca una directiva de prevención de pérdida de datos (DLP) cuando detecta el tipo de información confidencial del número de licencia de conductor de la UE. Este tipo de información confidencial define distintos patrones, palabras clave y otras pruebas para cada país.
ms.openlocfilehash: be9497c325866a670dff8d82b5170f4ca947c4ad
ms.sourcegitcommit: ed822a776d3419853453583e882f3c61ca26d4b2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "30410755"
---
# <a name="eu-drivers-license-number"></a><span data-ttu-id="de163-104">Número de permiso de conducción de la UE</span><span class="sxs-lookup"><span data-stu-id="de163-104">EU Driver's License Number</span></span>

<span data-ttu-id="de163-105">En este tema se muestra qué busca una directiva de prevención de pérdida de datos (DLP) cuando detecta el tipo de información confidencial del número de licencia de conductor de la UE.</span><span class="sxs-lookup"><span data-stu-id="de163-105">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Driver's License Number sensitive information type.</span></span> <span data-ttu-id="de163-106">Este tipo de información confidencial define distintos patrones, palabras clave y otras pruebas para cada país.</span><span class="sxs-lookup"><span data-stu-id="de163-106">This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="de163-107">Austria</span><span class="sxs-lookup"><span data-stu-id="de163-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="de163-108">Dé</span><span class="sxs-lookup"><span data-stu-id="de163-108">Format</span></span>

<span data-ttu-id="de163-109">Ocho dígitos sin espacios y delimitadores</span><span class="sxs-lookup"><span data-stu-id="de163-109">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="de163-110">Patrón</span><span class="sxs-lookup"><span data-stu-id="de163-110">Pattern</span></span>

<span data-ttu-id="de163-111">Ocho dígitos</span><span class="sxs-lookup"><span data-stu-id="de163-111">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="de163-112">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="de163-112">Checksum</span></span>

<span data-ttu-id="de163-113">No</span><span class="sxs-lookup"><span data-stu-id="de163-113">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="de163-114">Definición</span><span class="sxs-lookup"><span data-stu-id="de163-114">Definition</span></span>

<span data-ttu-id="de163-115">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="de163-115">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="de163-116">La expresión `Regex_austria_eu_driver's_license_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="de163-116">The regular expression  `Regex_austria_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="de163-117">Se encuentra una `Keywords_austria_eu_driver's_license_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="de163-117">A keyword from  `Keywords_austria_eu_driver's_license_number` is found.</span></span> 
    
```
<!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_driver's_license_number" />
          <Match idRef="Keywords_austria_eu_driver's_license_number" />
        </Pattern>
    </Entity>

```

### <a name="keywords"></a><span data-ttu-id="de163-118">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="de163-118">Keywords</span></span>

<span data-ttu-id="de163-119">| |</span><span class="sxs-lookup"><span data-stu-id="de163-119"></span></span>
|<span data-ttu-id="de163-120">**Keywords_austria_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="de163-120">**Keywords_austria_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="de163-121">listas</span><span class="sxs-lookup"><span data-stu-id="de163-121">dl#</span></span>  <br/> <span data-ttu-id="de163-122">driver license</span><span class="sxs-lookup"><span data-stu-id="de163-122">driver license</span></span>  <br/> <span data-ttu-id="de163-123">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="de163-123">driver license number</span></span>  <br/> <span data-ttu-id="de163-124">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="de163-124">driver licence</span></span>  <br/> <span data-ttu-id="de163-125">Lic de drivers.</span><span class="sxs-lookup"><span data-stu-id="de163-125">drivers lic.</span></span>  <br/> <span data-ttu-id="de163-126">drivers license</span><span class="sxs-lookup"><span data-stu-id="de163-126">drivers license</span></span>  <br/> <span data-ttu-id="de163-127">driver's licence</span><span class="sxs-lookup"><span data-stu-id="de163-127">driver's licence</span></span>  <br/> <span data-ttu-id="de163-128">driver's license</span><span class="sxs-lookup"><span data-stu-id="de163-128">driver's license</span></span>  <br/> <span data-ttu-id="de163-129">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="de163-129">driver's license number</span></span>  <br/> <span data-ttu-id="de163-130">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="de163-130">driver's licence number</span></span>  <br/>  <span data-ttu-id="de163-131">número de licencia de conducir</span><span class="sxs-lookup"><span data-stu-id="de163-131">driving license number</span></span>  <br/> <span data-ttu-id="de163-132">dlno #</span><span class="sxs-lookup"><span data-stu-id="de163-132">dlno#</span></span>  <br/> <span data-ttu-id="de163-133">fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="de163-133">fuhrerschein</span></span>  <br/> <span data-ttu-id="de163-134">fuhrerschein Republik Osterreich</span><span class="sxs-lookup"><span data-stu-id="de163-134">fuhrerschein republik osterreich</span></span>  <br/> |
   
## <a name="belgium"></a><span data-ttu-id="de163-135">Bélgica</span><span class="sxs-lookup"><span data-stu-id="de163-135">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="de163-136">Dé</span><span class="sxs-lookup"><span data-stu-id="de163-136">Format</span></span>

<span data-ttu-id="de163-137">10 dígitos sin espacios y delimitadores</span><span class="sxs-lookup"><span data-stu-id="de163-137">10 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="de163-138">Patrón</span><span class="sxs-lookup"><span data-stu-id="de163-138">Pattern</span></span>

<span data-ttu-id="de163-139">10 dígitos</span><span class="sxs-lookup"><span data-stu-id="de163-139">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="de163-140">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="de163-140">Checksum</span></span>

<span data-ttu-id="de163-141">No</span><span class="sxs-lookup"><span data-stu-id="de163-141">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="de163-142">Definición</span><span class="sxs-lookup"><span data-stu-id="de163-142">Definition</span></span>

<span data-ttu-id="de163-143">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="de163-143">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="de163-144">La expresión `Regex_belgium_eu_driver's_license_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="de163-144">The regular expression  `Regex_belgium_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="de163-145">Se encuentra una `Keywords_belgium_eu_driver's_license_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="de163-145">A keyword from  `Keywords_belgium_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_driver's_license_number" />
          <Match idRef="Keywords_belgium_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="de163-146">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="de163-146">Keywords</span></span>

<span data-ttu-id="de163-147">| |</span><span class="sxs-lookup"><span data-stu-id="de163-147"></span></span>
|<span data-ttu-id="de163-148">**Keywords__belgium_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="de163-148">**Keywords__belgium_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="de163-149">listas</span><span class="sxs-lookup"><span data-stu-id="de163-149">dl#</span></span>  <br/> <span data-ttu-id="de163-150">driver license</span><span class="sxs-lookup"><span data-stu-id="de163-150">driver license</span></span>  <br/> <span data-ttu-id="de163-151">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="de163-151">driver license number</span></span>  <br/> <span data-ttu-id="de163-152">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="de163-152">driver licence</span></span>  <br/> <span data-ttu-id="de163-153">Lic de drivers.</span><span class="sxs-lookup"><span data-stu-id="de163-153">drivers lic.</span></span>  <br/> <span data-ttu-id="de163-154">drivers license</span><span class="sxs-lookup"><span data-stu-id="de163-154">drivers license</span></span>  <br/> <span data-ttu-id="de163-155">drivers licence</span><span class="sxs-lookup"><span data-stu-id="de163-155">drivers licence</span></span>  <br/> <span data-ttu-id="de163-156">driver's license</span><span class="sxs-lookup"><span data-stu-id="de163-156">driver's license</span></span>  <br/> <span data-ttu-id="de163-157">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="de163-157">driver's license number</span></span>  <br/> <span data-ttu-id="de163-158">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="de163-158">driver's licence number</span></span>  <br/> <span data-ttu-id="de163-159">dlno #</span><span class="sxs-lookup"><span data-stu-id="de163-159">dlno#</span></span>  <br/> <span data-ttu-id="de163-160">rijbewijs</span><span class="sxs-lookup"><span data-stu-id="de163-160">rijbewijs</span></span>  <br/> <span data-ttu-id="de163-161">rijbewijsnummer</span><span class="sxs-lookup"><span data-stu-id="de163-161">rijbewijsnummer</span></span>  <br/> <span data-ttu-id="de163-162">führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="de163-162">führerscheinnummer</span></span>  <br/> <span data-ttu-id="de163-163">fuhrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="de163-163">fuhrerscheinnummer</span></span>  <br/> <span data-ttu-id="de163-164">fuehrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="de163-164">fuehrerscheinnummer</span></span>  <br/> <span data-ttu-id="de163-165">Führerschein-NR</span><span class="sxs-lookup"><span data-stu-id="de163-165">führerschein- nr</span></span>  <br/> <span data-ttu-id="de163-166">fuehrerschein-NR</span><span class="sxs-lookup"><span data-stu-id="de163-166">fuehrerschein- Nr</span></span>  <br/> <span data-ttu-id="de163-167">fuehrerschein-NR</span><span class="sxs-lookup"><span data-stu-id="de163-167">fuehrerschein- nr</span></span>  <br/> |
   
## <a name="bulgaria"></a><span data-ttu-id="de163-168">Bulgaria</span><span class="sxs-lookup"><span data-stu-id="de163-168">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="de163-169">Dé</span><span class="sxs-lookup"><span data-stu-id="de163-169">Format</span></span>

<span data-ttu-id="de163-170">Nueve dígitos sin espacios y delimitadores</span><span class="sxs-lookup"><span data-stu-id="de163-170">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="de163-171">Patrón</span><span class="sxs-lookup"><span data-stu-id="de163-171">Pattern</span></span>

<span data-ttu-id="de163-172">Nueve dígitos</span><span class="sxs-lookup"><span data-stu-id="de163-172">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="de163-173">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="de163-173">Checksum</span></span>

<span data-ttu-id="de163-174">No</span><span class="sxs-lookup"><span data-stu-id="de163-174">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="de163-175">Definición</span><span class="sxs-lookup"><span data-stu-id="de163-175">Definition</span></span>

<span data-ttu-id="de163-176">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="de163-176">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="de163-177">La expresión `Regex_bulgaria_eu_driver's_license_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="de163-177">The regular expression  `Regex_bulgaria_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="de163-178">Se encuentra una `Keywords_bulgaria_eu_driver's_license_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="de163-178">A keyword from  `Keywords_bulgaria_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
             <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_driver's_license_number" />
          <Match idRef="Keywords_bulgaria_eu_driver's_license_number" />
        </Pattern> 
</Entity>    

```

### <a name="keywords"></a><span data-ttu-id="de163-179">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="de163-179">Keywords</span></span>

<span data-ttu-id="de163-180">| |</span><span class="sxs-lookup"><span data-stu-id="de163-180"></span></span>
|<span data-ttu-id="de163-181">**Keywords_bulgaria_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="de163-181">**Keywords_bulgaria_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="de163-182">listas</span><span class="sxs-lookup"><span data-stu-id="de163-182">dl#</span></span>  <br/> <span data-ttu-id="de163-183">driver license</span><span class="sxs-lookup"><span data-stu-id="de163-183">driver license</span></span>  <br/> <span data-ttu-id="de163-184">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="de163-184">driver license number</span></span>  <br/> <span data-ttu-id="de163-185">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="de163-185">driver licence</span></span>  <br/> <span data-ttu-id="de163-186">Lic de drivers.</span><span class="sxs-lookup"><span data-stu-id="de163-186">drivers lic.</span></span>  <br/> <span data-ttu-id="de163-187">drivers license</span><span class="sxs-lookup"><span data-stu-id="de163-187">drivers license</span></span>  <br/> <span data-ttu-id="de163-188">drivers licence</span><span class="sxs-lookup"><span data-stu-id="de163-188">drivers licence</span></span>  <br/> <span data-ttu-id="de163-189">driver's license</span><span class="sxs-lookup"><span data-stu-id="de163-189">driver's license</span></span>  <br/> <span data-ttu-id="de163-190">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="de163-190">driver's license number</span></span>  <br/> <span data-ttu-id="de163-191">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="de163-191">driver's licence number</span></span>  <br/> <span data-ttu-id="de163-192">número de licencia de conducir</span><span class="sxs-lookup"><span data-stu-id="de163-192">driving license number</span></span>  <br/> <span data-ttu-id="de163-193">dlno #</span><span class="sxs-lookup"><span data-stu-id="de163-193">dlno#</span></span>  <br/> <span data-ttu-id="de163-194">свидетелство за управление на мпс</span><span class="sxs-lookup"><span data-stu-id="de163-194">свидетелство за управление на мпс</span></span>  <br/> <span data-ttu-id="de163-195">свидетелство за управление на моторно превозно средство</span><span class="sxs-lookup"><span data-stu-id="de163-195">свидетелство за управление на моторно превозно средство</span></span>  <br/> <span data-ttu-id="de163-196">сумпс</span><span class="sxs-lookup"><span data-stu-id="de163-196">сумпс</span></span>  <br/> <span data-ttu-id="de163-197">шофьорска книжка</span><span class="sxs-lookup"><span data-stu-id="de163-197">шофьорска книжка</span></span>  <br/> |
   
## <a name="croatia"></a><span data-ttu-id="de163-198">Croacia</span><span class="sxs-lookup"><span data-stu-id="de163-198">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="de163-199">Dé</span><span class="sxs-lookup"><span data-stu-id="de163-199">Format</span></span>

<span data-ttu-id="de163-200">Ocho dígitos sin espacios y delimitadores</span><span class="sxs-lookup"><span data-stu-id="de163-200">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="de163-201">Patrón</span><span class="sxs-lookup"><span data-stu-id="de163-201">Pattern</span></span>

<span data-ttu-id="de163-202">Ocho dígitos</span><span class="sxs-lookup"><span data-stu-id="de163-202">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="de163-203">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="de163-203">Checksum</span></span>

<span data-ttu-id="de163-204">No</span><span class="sxs-lookup"><span data-stu-id="de163-204">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="de163-205">Definición</span><span class="sxs-lookup"><span data-stu-id="de163-205">Definition</span></span>

<span data-ttu-id="de163-206">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="de163-206">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="de163-207">La expresión `Regex_croatia_eu_driver's_license_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="de163-207">The regular expression  `Regex_croatia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="de163-208">Se encuentra una `Keywords_croatia_eu_driver's_license_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="de163-208">A keyword from  `Keywords_croatia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_driver's_license_number" />
          <Match idRef="Keywords_croatia_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="de163-209">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="de163-209">Keywords</span></span>

<span data-ttu-id="de163-210">| |</span><span class="sxs-lookup"><span data-stu-id="de163-210"></span></span>
|<span data-ttu-id="de163-211">**Keywords_croatia_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="de163-211">**Keywords_croatia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="de163-212">listas</span><span class="sxs-lookup"><span data-stu-id="de163-212">dl#</span></span>  <br/> <span data-ttu-id="de163-213">driver license</span><span class="sxs-lookup"><span data-stu-id="de163-213">driver license</span></span>  <br/> <span data-ttu-id="de163-214">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="de163-214">driver license number</span></span>  <br/> <span data-ttu-id="de163-215">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="de163-215">driver licence</span></span>  <br/> <span data-ttu-id="de163-216">Lic de drivers.</span><span class="sxs-lookup"><span data-stu-id="de163-216">drivers lic.</span></span>  <br/> <span data-ttu-id="de163-217">drivers license</span><span class="sxs-lookup"><span data-stu-id="de163-217">drivers license</span></span>  <br/> <span data-ttu-id="de163-218">drivers licence</span><span class="sxs-lookup"><span data-stu-id="de163-218">drivers licence</span></span>  <br/> <span data-ttu-id="de163-219">driver's license</span><span class="sxs-lookup"><span data-stu-id="de163-219">driver's license</span></span>  <br/> <span data-ttu-id="de163-220">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="de163-220">driver's license number</span></span>  <br/> <span data-ttu-id="de163-221">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="de163-221">driver's licence number</span></span>  <br/> <span data-ttu-id="de163-222">número de licencia de conducir</span><span class="sxs-lookup"><span data-stu-id="de163-222">driving license number</span></span>  <br/> <span data-ttu-id="de163-223">dlno #</span><span class="sxs-lookup"><span data-stu-id="de163-223">dlno#</span></span>  <br/> <span data-ttu-id="de163-224">vozačka Dozvola</span><span class="sxs-lookup"><span data-stu-id="de163-224">vozačka dozvola</span></span>  <br/> |
   
## <a name="cyprus"></a><span data-ttu-id="de163-225">Chipre</span><span class="sxs-lookup"><span data-stu-id="de163-225">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="de163-226">Dé</span><span class="sxs-lookup"><span data-stu-id="de163-226">Format</span></span>

<span data-ttu-id="de163-227">12 dígitos sin espacios y delimitadores</span><span class="sxs-lookup"><span data-stu-id="de163-227">12 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="de163-228">Patrón</span><span class="sxs-lookup"><span data-stu-id="de163-228">Pattern</span></span>

<span data-ttu-id="de163-229">12 dígitos</span><span class="sxs-lookup"><span data-stu-id="de163-229">12 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="de163-230">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="de163-230">Checksum</span></span>

<span data-ttu-id="de163-231">No</span><span class="sxs-lookup"><span data-stu-id="de163-231">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="de163-232">Definición</span><span class="sxs-lookup"><span data-stu-id="de163-232">Definition</span></span>

<span data-ttu-id="de163-233">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="de163-233">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="de163-234">La expresión `Regex_cyprus_eu_driver's_license_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="de163-234">The regular expression  `Regex_cyprus_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="de163-235">Se encuentra una `Keywords_cyprus_eu_driver's_license_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="de163-235">A keyword from  `Keywords_cyprus_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_driver's_license_number" />
          <Match idRef="Keywords_cyprus_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="de163-236">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="de163-236">Keywords</span></span>

<span data-ttu-id="de163-237">| |</span><span class="sxs-lookup"><span data-stu-id="de163-237"></span></span>
|<span data-ttu-id="de163-238">**Keywords_cyprus_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="de163-238">**Keywords_cyprus_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="de163-239">listas</span><span class="sxs-lookup"><span data-stu-id="de163-239">dl#</span></span>  <br/> <span data-ttu-id="de163-240">driver license</span><span class="sxs-lookup"><span data-stu-id="de163-240">driver license</span></span>  <br/> <span data-ttu-id="de163-241">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="de163-241">driver license number</span></span>  <br/> <span data-ttu-id="de163-242">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="de163-242">driver licence</span></span>  <br/> <span data-ttu-id="de163-243">Lic de drivers.</span><span class="sxs-lookup"><span data-stu-id="de163-243">drivers lic.</span></span>  <br/> <span data-ttu-id="de163-244">drivers license</span><span class="sxs-lookup"><span data-stu-id="de163-244">drivers license</span></span>  <br/> <span data-ttu-id="de163-245">drivers licence</span><span class="sxs-lookup"><span data-stu-id="de163-245">drivers licence</span></span>  <br/> <span data-ttu-id="de163-246">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="de163-246">driver's license number</span></span>  <br/> <span data-ttu-id="de163-247">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="de163-247">driver's licence number</span></span>  <br/> <span data-ttu-id="de163-248">número de licencia de conducir</span><span class="sxs-lookup"><span data-stu-id="de163-248">driving license number</span></span>  <br/> <span data-ttu-id="de163-249">dlno #</span><span class="sxs-lookup"><span data-stu-id="de163-249">dlno#</span></span>  <br/> <span data-ttu-id="de163-250">άδεια οδήγησης</span><span class="sxs-lookup"><span data-stu-id="de163-250">άδεια οδήγησης</span></span>  <br/> |
   
## <a name="czech-republic"></a><span data-ttu-id="de163-251">Chequia</span><span class="sxs-lookup"><span data-stu-id="de163-251">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="de163-252">Dé</span><span class="sxs-lookup"><span data-stu-id="de163-252">Format</span></span>

<span data-ttu-id="de163-253">Dos letras seguidas de seis dígitos</span><span class="sxs-lookup"><span data-stu-id="de163-253">Two letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="de163-254">Patrón</span><span class="sxs-lookup"><span data-stu-id="de163-254">Pattern</span></span>

<span data-ttu-id="de163-255">Ocho letras y dígitos:</span><span class="sxs-lookup"><span data-stu-id="de163-255">Eight letters and digits:</span></span>
  
- <span data-ttu-id="de163-256">Dos letras (sin distinción entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="de163-256">Two letters (not case-sensitive)</span></span>
    
- <span data-ttu-id="de163-257">Un espacio (opcional) </span><span class="sxs-lookup"><span data-stu-id="de163-257">A space (optional)</span></span>
    
- <span data-ttu-id="de163-258">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="de163-258">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="de163-259">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="de163-259">Checksum</span></span>

<span data-ttu-id="de163-260">No</span><span class="sxs-lookup"><span data-stu-id="de163-260">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="de163-261">Definición</span><span class="sxs-lookup"><span data-stu-id="de163-261">Definition</span></span>

<span data-ttu-id="de163-262">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="de163-262">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="de163-263">La expresión `Regex_czech_republic_eu_driver's_license_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="de163-263">The regular expression  `Regex_czech_republic_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="de163-264">Se encuentra una `Keywords_czech_republic_eu_driver's_license_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="de163-264">A keyword from  `Keywords_czech_republic_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_driver's_license_number" />
          <Match idRef="Keywords_czech_republic_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="de163-265">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="de163-265">Keywords</span></span>

<span data-ttu-id="de163-266">| |</span><span class="sxs-lookup"><span data-stu-id="de163-266"></span></span>
|<span data-ttu-id="de163-267">**Keywords_czech_republic_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="de163-267">**Keywords_czech_republic_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="de163-268">listas</span><span class="sxs-lookup"><span data-stu-id="de163-268">dl#</span></span>  <br/> <span data-ttu-id="de163-269">driver license</span><span class="sxs-lookup"><span data-stu-id="de163-269">driver license</span></span>  <br/> <span data-ttu-id="de163-270">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="de163-270">driver license number</span></span>  <br/> <span data-ttu-id="de163-271">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="de163-271">driver licence</span></span>  <br/> <span data-ttu-id="de163-272">Lic de drivers.</span><span class="sxs-lookup"><span data-stu-id="de163-272">drivers lic.</span></span>  <br/> <span data-ttu-id="de163-273">drivers license</span><span class="sxs-lookup"><span data-stu-id="de163-273">drivers license</span></span>  <br/> <span data-ttu-id="de163-274">drivers licence</span><span class="sxs-lookup"><span data-stu-id="de163-274">drivers licence</span></span>  <br/> <span data-ttu-id="de163-275">driver's license</span><span class="sxs-lookup"><span data-stu-id="de163-275">driver's license</span></span>  <br/> <span data-ttu-id="de163-276">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="de163-276">driver's license number</span></span>  <br/> <span data-ttu-id="de163-277">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="de163-277">driver's license number</span></span>  <br/> <span data-ttu-id="de163-278">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="de163-278">driver's licence number</span></span>  <br/> <span data-ttu-id="de163-279">número de licencia de conducir</span><span class="sxs-lookup"><span data-stu-id="de163-279">driving license number</span></span>  <br/> <span data-ttu-id="de163-280">dlno #</span><span class="sxs-lookup"><span data-stu-id="de163-280">dlno#</span></span>  <br/> <span data-ttu-id="de163-281">řidičský prúkaz</span><span class="sxs-lookup"><span data-stu-id="de163-281">řidičský prúkaz</span></span>  <br/> |
   
## <a name="denmark"></a><span data-ttu-id="de163-282">Dinamarca</span><span class="sxs-lookup"><span data-stu-id="de163-282">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="de163-283">Dé</span><span class="sxs-lookup"><span data-stu-id="de163-283">Format</span></span>

<span data-ttu-id="de163-284">Ocho dígitos sin espacios y delimitadores</span><span class="sxs-lookup"><span data-stu-id="de163-284">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="de163-285">Patrón</span><span class="sxs-lookup"><span data-stu-id="de163-285">Pattern</span></span>

<span data-ttu-id="de163-286">Ocho dígitos</span><span class="sxs-lookup"><span data-stu-id="de163-286">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="de163-287">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="de163-287">Checksum</span></span>

<span data-ttu-id="de163-288">Sí</span><span class="sxs-lookup"><span data-stu-id="de163-288">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="de163-289">Definición</span><span class="sxs-lookup"><span data-stu-id="de163-289">Definition</span></span>

<span data-ttu-id="de163-290">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="de163-290">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="de163-291">La expresión `Regex_denmark_eu_driver's_license_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="de163-291">The regular expression  `Regex_denmark_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="de163-292">Se encuentra una `Keywords_denmark_eu_driver's_license_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="de163-292">A keyword from  `Keywords_denmark_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_driver's_license_number" />
          <Match idRef="Keywords_denmark_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="de163-293">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="de163-293">Keywords</span></span>

<span data-ttu-id="de163-294">| |</span><span class="sxs-lookup"><span data-stu-id="de163-294"></span></span>
|<span data-ttu-id="de163-295">**Keywords_denmark_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="de163-295">**Keywords_denmark_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="de163-296">listas</span><span class="sxs-lookup"><span data-stu-id="de163-296">dl#</span></span>  <br/> <span data-ttu-id="de163-297">driver license</span><span class="sxs-lookup"><span data-stu-id="de163-297">driver license</span></span>  <br/> <span data-ttu-id="de163-298">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="de163-298">driver license number</span></span>  <br/> <span data-ttu-id="de163-299">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="de163-299">driver licence</span></span>  <br/> <span data-ttu-id="de163-300">Lic de drivers.</span><span class="sxs-lookup"><span data-stu-id="de163-300">drivers lic.</span></span>  <br/> <span data-ttu-id="de163-301">drivers license</span><span class="sxs-lookup"><span data-stu-id="de163-301">drivers license</span></span>  <br/> <span data-ttu-id="de163-302">drivers licence</span><span class="sxs-lookup"><span data-stu-id="de163-302">drivers licence</span></span>  <br/> <span data-ttu-id="de163-303">driver's license</span><span class="sxs-lookup"><span data-stu-id="de163-303">driver's license</span></span>  <br/> <span data-ttu-id="de163-304">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="de163-304">driver's license number</span></span>  <br/> <span data-ttu-id="de163-305">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="de163-305">driver's licence number</span></span>  <br/> <span data-ttu-id="de163-306">número de licencia de conducir</span><span class="sxs-lookup"><span data-stu-id="de163-306">driving license number</span></span>  <br/> <span data-ttu-id="de163-307">dlno #</span><span class="sxs-lookup"><span data-stu-id="de163-307">dlno#</span></span>  <br/> <span data-ttu-id="de163-308">kørekort</span><span class="sxs-lookup"><span data-stu-id="de163-308">kørekort</span></span>  <br/> <span data-ttu-id="de163-309">kørekortnummer</span><span class="sxs-lookup"><span data-stu-id="de163-309">kørekortnummer</span></span>  <br/> |
   
## <a name="estonia"></a><span data-ttu-id="de163-310">Estonia</span><span class="sxs-lookup"><span data-stu-id="de163-310">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="de163-311">Dé</span><span class="sxs-lookup"><span data-stu-id="de163-311">Format</span></span>

<span data-ttu-id="de163-312">Dos letras seguidas de seis dígitos</span><span class="sxs-lookup"><span data-stu-id="de163-312">Two letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="de163-313">Patrón</span><span class="sxs-lookup"><span data-stu-id="de163-313">Pattern</span></span>

<span data-ttu-id="de163-314">Dos letras y seis dígitos:</span><span class="sxs-lookup"><span data-stu-id="de163-314">Two letters and six digits:</span></span>
  
-  <span data-ttu-id="de163-315">Las letras "ET" (sin distinción entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="de163-315">The letters "ET" (not case-sensitive)</span></span> 
    
- <span data-ttu-id="de163-316">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="de163-316">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="de163-317">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="de163-317">Checksum</span></span>

<span data-ttu-id="de163-318">No</span><span class="sxs-lookup"><span data-stu-id="de163-318">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="de163-319">Definición</span><span class="sxs-lookup"><span data-stu-id="de163-319">Definition</span></span>

<span data-ttu-id="de163-320">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="de163-320">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="de163-321">La expresión `Regex_estonia_eu_driver's_license_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="de163-321">The regular expression  `Regex_estonia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="de163-322">Se encuentra una `Keywords_estonia_eu_driver's_license_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="de163-322">A keyword from  `Keywords_estonia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_driver's_license_number" />
          <Match idRef="Keywords_estonia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="de163-323">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="de163-323">Keywords</span></span>

<span data-ttu-id="de163-324">| |</span><span class="sxs-lookup"><span data-stu-id="de163-324"></span></span>
|<span data-ttu-id="de163-325">**Keywords_estonia_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="de163-325">**Keywords_estonia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="de163-326">listas</span><span class="sxs-lookup"><span data-stu-id="de163-326">dl#</span></span>  <br/> <span data-ttu-id="de163-327">driver license</span><span class="sxs-lookup"><span data-stu-id="de163-327">driver license</span></span>  <br/> <span data-ttu-id="de163-328">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="de163-328">driver license number</span></span>  <br/> <span data-ttu-id="de163-329">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="de163-329">driver license number</span></span>  <br/> <span data-ttu-id="de163-330">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="de163-330">driver licence</span></span>  <br/> <span data-ttu-id="de163-331">Lic de drivers.</span><span class="sxs-lookup"><span data-stu-id="de163-331">drivers lic.</span></span>  <br/> <span data-ttu-id="de163-332">drivers license</span><span class="sxs-lookup"><span data-stu-id="de163-332">drivers license</span></span>  <br/> <span data-ttu-id="de163-333">drivers licence</span><span class="sxs-lookup"><span data-stu-id="de163-333">drivers licence</span></span>  <br/> <span data-ttu-id="de163-334">driver's license</span><span class="sxs-lookup"><span data-stu-id="de163-334">driver's license</span></span>  <br/> <span data-ttu-id="de163-335">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="de163-335">driver's license number</span></span>  <br/> <span data-ttu-id="de163-336">número de licencia de conducir</span><span class="sxs-lookup"><span data-stu-id="de163-336">driving license number</span></span>  <br/> <span data-ttu-id="de163-337">dlno #</span><span class="sxs-lookup"><span data-stu-id="de163-337">dlno#</span></span>  <br/> <span data-ttu-id="de163-338">permis de conduire</span><span class="sxs-lookup"><span data-stu-id="de163-338">permis de conduire</span></span>  <br/> |
   
## <a name="finland"></a><span data-ttu-id="de163-339">Finlandia</span><span class="sxs-lookup"><span data-stu-id="de163-339">Finland</span></span>

### <a name="format"></a><span data-ttu-id="de163-340">Dé</span><span class="sxs-lookup"><span data-stu-id="de163-340">Format</span></span>

<span data-ttu-id="de163-341">10 dígitos que contienen un guión</span><span class="sxs-lookup"><span data-stu-id="de163-341">10 digits containing a hyphen</span></span>
  
### <a name="pattern"></a><span data-ttu-id="de163-342">Patrón</span><span class="sxs-lookup"><span data-stu-id="de163-342">Pattern</span></span>

<span data-ttu-id="de163-343">10 dígitos que contienen un guión:</span><span class="sxs-lookup"><span data-stu-id="de163-343">10 digits containing a hyphen:</span></span>
  
-  <span data-ttu-id="de163-344">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="de163-344">Six digits</span></span> 
    
- <span data-ttu-id="de163-345">Un guión</span><span class="sxs-lookup"><span data-stu-id="de163-345">A hyphen</span></span>
    
-  <span data-ttu-id="de163-346">Cuatro dígitos</span><span class="sxs-lookup"><span data-stu-id="de163-346">Four digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="de163-347">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="de163-347">Checksum</span></span>

<span data-ttu-id="de163-348">No</span><span class="sxs-lookup"><span data-stu-id="de163-348">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="de163-349">Definición</span><span class="sxs-lookup"><span data-stu-id="de163-349">Definition</span></span>

<span data-ttu-id="de163-350">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="de163-350">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="de163-351">La expresión `Regex_finland_eu_driver's_license_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="de163-351">The regular expression  `Regex_finland_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="de163-352">Se encuentra una `Keywords_finland_eu_driver's_license_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="de163-352">A keyword from  `Keywords_finland_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_finland_eu_driver's_license_number" />
          <Match idRef="Keywords_finland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="de163-353">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="de163-353">Keywords</span></span>

<span data-ttu-id="de163-354">| |</span><span class="sxs-lookup"><span data-stu-id="de163-354"></span></span>
|<span data-ttu-id="de163-355">**Keywords_finland_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="de163-355">**Keywords_finland_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="de163-356">listas</span><span class="sxs-lookup"><span data-stu-id="de163-356">dl#</span></span>  <br/> <span data-ttu-id="de163-357">driver license</span><span class="sxs-lookup"><span data-stu-id="de163-357">driver license</span></span>  <br/> <span data-ttu-id="de163-358">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="de163-358">driver license number</span></span>  <br/> <span data-ttu-id="de163-359">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="de163-359">driver licence</span></span>  <br/> <span data-ttu-id="de163-360">Lic de drivers.</span><span class="sxs-lookup"><span data-stu-id="de163-360">drivers lic.</span></span>  <br/> <span data-ttu-id="de163-361">drivers license</span><span class="sxs-lookup"><span data-stu-id="de163-361">drivers license</span></span>  <br/> <span data-ttu-id="de163-362">drivers licence</span><span class="sxs-lookup"><span data-stu-id="de163-362">drivers licence</span></span>  <br/> <span data-ttu-id="de163-363">driver's license</span><span class="sxs-lookup"><span data-stu-id="de163-363">driver's license</span></span>  <br/> <span data-ttu-id="de163-364">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="de163-364">driver's license number</span></span>  <br/> <span data-ttu-id="de163-365">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="de163-365">driver's licence number</span></span>  <br/> <span data-ttu-id="de163-366">número de licencia de conducir</span><span class="sxs-lookup"><span data-stu-id="de163-366">driving license number</span></span>  <br/> <span data-ttu-id="de163-367">dlno #</span><span class="sxs-lookup"><span data-stu-id="de163-367">dlno#</span></span>  <br/> <span data-ttu-id="de163-368">ajokortti</span><span class="sxs-lookup"><span data-stu-id="de163-368">ajokortti</span></span>  <br/> |
   
## <a name="france"></a><span data-ttu-id="de163-369">Francia</span><span class="sxs-lookup"><span data-stu-id="de163-369">France</span></span>

<span data-ttu-id="de163-370">Para obtener más información, consulte la sección "número de permiso de conducción de Francia" en [Qué buscan los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="de163-370">For details, see the section "France Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="germany"></a><span data-ttu-id="de163-371">Alemania</span><span class="sxs-lookup"><span data-stu-id="de163-371">Germany</span></span>

<span data-ttu-id="de163-372">Para obtener más información, consulte la sección "número de permiso de conducción de alemán" en [el que se buscan los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="de163-372">For details, see the section "German Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="greece"></a><span data-ttu-id="de163-373">Grecia</span><span class="sxs-lookup"><span data-stu-id="de163-373">Greece</span></span>

### <a name="format"></a><span data-ttu-id="de163-374">Dé</span><span class="sxs-lookup"><span data-stu-id="de163-374">Format</span></span>

<span data-ttu-id="de163-375">Nueve dígitos sin espacios y delimitadores</span><span class="sxs-lookup"><span data-stu-id="de163-375">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="de163-376">Patrón</span><span class="sxs-lookup"><span data-stu-id="de163-376">Pattern</span></span>

 <span data-ttu-id="de163-377">Nueve dígitos</span><span class="sxs-lookup"><span data-stu-id="de163-377">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="de163-378">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="de163-378">Checksum</span></span>

<span data-ttu-id="de163-379">No</span><span class="sxs-lookup"><span data-stu-id="de163-379">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="de163-380">Definición</span><span class="sxs-lookup"><span data-stu-id="de163-380">Definition</span></span>

<span data-ttu-id="de163-381">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="de163-381">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="de163-382">La expresión `Regex_greece_eu_driver's_license_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="de163-382">The regular expression  `Regex_greece_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="de163-383">Se encuentra una `Keywords_greece_eu_driver's_license_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="de163-383">A keyword from  `Keywords_greece_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_driver's_license_number" />
          <Match idRef="Keywords_greece_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="de163-384">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="de163-384">Keywords</span></span>

<span data-ttu-id="de163-385">| |</span><span class="sxs-lookup"><span data-stu-id="de163-385"></span></span>
|<span data-ttu-id="de163-386">**Keywords_greece_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="de163-386">**Keywords_greece_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="de163-387">Biblioteca</span><span class="sxs-lookup"><span data-stu-id="de163-387">dlL#</span></span>  <br/> <span data-ttu-id="de163-388">driver license</span><span class="sxs-lookup"><span data-stu-id="de163-388">driver license</span></span>  <br/> <span data-ttu-id="de163-389">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="de163-389">driver license number</span></span>  <br/> <span data-ttu-id="de163-390">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="de163-390">driver licence</span></span>  <br/> <span data-ttu-id="de163-391">Lic de drivers.</span><span class="sxs-lookup"><span data-stu-id="de163-391">drivers lic.</span></span>  <br/> <span data-ttu-id="de163-392">drivers license</span><span class="sxs-lookup"><span data-stu-id="de163-392">drivers license</span></span>  <br/> <span data-ttu-id="de163-393">drivers licence</span><span class="sxs-lookup"><span data-stu-id="de163-393">drivers licence</span></span>  <br/> <span data-ttu-id="de163-394">driver's license</span><span class="sxs-lookup"><span data-stu-id="de163-394">driver's license</span></span>  <br/> <span data-ttu-id="de163-395">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="de163-395">driver's license number</span></span>  <br/> <span data-ttu-id="de163-396">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="de163-396">driver's licence number</span></span>  <br/> <span data-ttu-id="de163-397">número de licencia de conducir</span><span class="sxs-lookup"><span data-stu-id="de163-397">driving license number</span></span>  <br/> <span data-ttu-id="de163-398">dlno #</span><span class="sxs-lookup"><span data-stu-id="de163-398">dlno#</span></span>  <br/> <span data-ttu-id="de163-399">δεια οδήγησης</span><span class="sxs-lookup"><span data-stu-id="de163-399">δεια οδήγησης</span></span>  <br/> <span data-ttu-id="de163-400">Adeia odigisis</span><span class="sxs-lookup"><span data-stu-id="de163-400">Adeia odigisis</span></span>  <br/> |
   
## <a name="hungary"></a><span data-ttu-id="de163-401">Hungría</span><span class="sxs-lookup"><span data-stu-id="de163-401">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="de163-402">Dé</span><span class="sxs-lookup"><span data-stu-id="de163-402">Format</span></span>

<span data-ttu-id="de163-403">Dos letras seguidas de seis dígitos</span><span class="sxs-lookup"><span data-stu-id="de163-403">Two letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="de163-404">Patrón</span><span class="sxs-lookup"><span data-stu-id="de163-404">Pattern</span></span>

<span data-ttu-id="de163-405">Dos letras y seis dígitos:</span><span class="sxs-lookup"><span data-stu-id="de163-405">Two letters and six digits:</span></span>
  
-  <span data-ttu-id="de163-406">Dos letras (sin distinción entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="de163-406">Two letters (not case-sensitive)</span></span> 
    
- <span data-ttu-id="de163-407">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="de163-407">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="de163-408">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="de163-408">Checksum</span></span>

<span data-ttu-id="de163-409">No</span><span class="sxs-lookup"><span data-stu-id="de163-409">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="de163-410">Definición</span><span class="sxs-lookup"><span data-stu-id="de163-410">Definition</span></span>

<span data-ttu-id="de163-411">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="de163-411">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="de163-412">La expresión `Regex_hungary_eu_driver's_license_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="de163-412">The regular expression  `Regex_hungary_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="de163-413">Se encuentra una `Keywords_hungary_eu_driver's_license_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="de163-413">A keyword from  `Keywords_hungary_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_driver's_license_number" />
          <Match idRef="Keywords_hungary_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="de163-414">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="de163-414">Keywords</span></span>

<span data-ttu-id="de163-415">| |</span><span class="sxs-lookup"><span data-stu-id="de163-415"></span></span>
|<span data-ttu-id="de163-416">**Keywords_hungary_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="de163-416">**Keywords_hungary_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="de163-417">listas</span><span class="sxs-lookup"><span data-stu-id="de163-417">dl#</span></span>  <br/> <span data-ttu-id="de163-418">driver license</span><span class="sxs-lookup"><span data-stu-id="de163-418">driver license</span></span>  <br/> <span data-ttu-id="de163-419">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="de163-419">driver license number</span></span>  <br/> <span data-ttu-id="de163-420">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="de163-420">driver licence</span></span>  <br/> <span data-ttu-id="de163-421">Lic de drivers.</span><span class="sxs-lookup"><span data-stu-id="de163-421">drivers lic.</span></span>  <br/> <span data-ttu-id="de163-422">drivers license</span><span class="sxs-lookup"><span data-stu-id="de163-422">drivers license</span></span>  <br/> <span data-ttu-id="de163-423">drivers licence</span><span class="sxs-lookup"><span data-stu-id="de163-423">drivers licence</span></span>  <br/> <span data-ttu-id="de163-424">driver's license</span><span class="sxs-lookup"><span data-stu-id="de163-424">driver's license</span></span>  <br/> <span data-ttu-id="de163-425">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="de163-425">driver's license number</span></span>  <br/> <span data-ttu-id="de163-426">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="de163-426">driver's licence number</span></span>  <br/> <span data-ttu-id="de163-427">número de licencia de conducir</span><span class="sxs-lookup"><span data-stu-id="de163-427">driving license number</span></span>  <br/> <span data-ttu-id="de163-428">dlno #</span><span class="sxs-lookup"><span data-stu-id="de163-428">dlno#</span></span>  <br/> <span data-ttu-id="de163-429">vezetoi engedely</span><span class="sxs-lookup"><span data-stu-id="de163-429">vezetoi engedely</span></span>  <br/> |
   
## <a name="ireland"></a><span data-ttu-id="de163-430">Irlanda</span><span class="sxs-lookup"><span data-stu-id="de163-430">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="de163-431">Dé</span><span class="sxs-lookup"><span data-stu-id="de163-431">Format</span></span>

<span data-ttu-id="de163-432">Seis dígitos seguidos de cuatro letras</span><span class="sxs-lookup"><span data-stu-id="de163-432">Six digits followed by four letters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="de163-433">Patrón</span><span class="sxs-lookup"><span data-stu-id="de163-433">Pattern</span></span>

<span data-ttu-id="de163-434">Seis dígitos y cuatro letras:</span><span class="sxs-lookup"><span data-stu-id="de163-434">Six digits and four letters:</span></span>
  
- <span data-ttu-id="de163-435">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="de163-435">Six digits</span></span>
    
- <span data-ttu-id="de163-436">Cuatro letras (sin distinción entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="de163-436">Four letters (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="de163-437">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="de163-437">Checksum</span></span>

<span data-ttu-id="de163-438">No</span><span class="sxs-lookup"><span data-stu-id="de163-438">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="de163-439">Definición</span><span class="sxs-lookup"><span data-stu-id="de163-439">Definition</span></span>

<span data-ttu-id="de163-440">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="de163-440">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="de163-441">La expresión `Regex_ireland_eu_driver's_license_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="de163-441">The regular expression  `Regex_ireland_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="de163-442">Se encuentra una `Keywords_ireland_eu_driver's_license_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="de163-442">A keyword from  `Keywords_ireland_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_driver's_license_number" />
          <Match idRef="Keywords_ireland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="de163-443">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="de163-443">Keywords</span></span>

<span data-ttu-id="de163-444">| |</span><span class="sxs-lookup"><span data-stu-id="de163-444"></span></span>
|<span data-ttu-id="de163-445">**Keywords_ireland_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="de163-445">**Keywords_ireland_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="de163-446">listas</span><span class="sxs-lookup"><span data-stu-id="de163-446">dl#</span></span>  <br/> <span data-ttu-id="de163-447">driver license</span><span class="sxs-lookup"><span data-stu-id="de163-447">driver license</span></span>  <br/> <span data-ttu-id="de163-448">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="de163-448">driver license number</span></span>  <br/> <span data-ttu-id="de163-449">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="de163-449">driver licence</span></span>  <br/> <span data-ttu-id="de163-450">Lic de drivers.</span><span class="sxs-lookup"><span data-stu-id="de163-450">drivers lic.</span></span>  <br/> <span data-ttu-id="de163-451">drivers license</span><span class="sxs-lookup"><span data-stu-id="de163-451">drivers license</span></span>  <br/> <span data-ttu-id="de163-452">drivers licence</span><span class="sxs-lookup"><span data-stu-id="de163-452">drivers licence</span></span>  <br/> <span data-ttu-id="de163-453">driver's license</span><span class="sxs-lookup"><span data-stu-id="de163-453">driver's license</span></span>  <br/> <span data-ttu-id="de163-454">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="de163-454">driver's license number</span></span>  <br/> <span data-ttu-id="de163-455">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="de163-455">driver's licence number</span></span>  <br/> <span data-ttu-id="de163-456">número de licencia de conducir</span><span class="sxs-lookup"><span data-stu-id="de163-456">driving license number</span></span>  <br/> <span data-ttu-id="de163-457">dlno #</span><span class="sxs-lookup"><span data-stu-id="de163-457">dlno#</span></span>  <br/> <span data-ttu-id="de163-458">ceadúnas tiomána</span><span class="sxs-lookup"><span data-stu-id="de163-458">ceadúnas tiomána</span></span>  <br/> |
   
## <a name="italy"></a><span data-ttu-id="de163-459">Italia</span><span class="sxs-lookup"><span data-stu-id="de163-459">Italy</span></span>

<span data-ttu-id="de163-460">Para obtener más información, consulte la sección "número de licencia de conducción de Italia" en el [que se buscan los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="de163-460">For details, see the section "Italy Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="latvia"></a><span data-ttu-id="de163-461">Letonia</span><span class="sxs-lookup"><span data-stu-id="de163-461">Latvia</span></span>

### <a name="format"></a><span data-ttu-id="de163-462">Dé</span><span class="sxs-lookup"><span data-stu-id="de163-462">Format</span></span>

<span data-ttu-id="de163-463">Tres letras seguidas de seis dígitos</span><span class="sxs-lookup"><span data-stu-id="de163-463">Three letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="de163-464">Patrón</span><span class="sxs-lookup"><span data-stu-id="de163-464">Pattern</span></span>

<span data-ttu-id="de163-465">Tres letras y seis dígitos:</span><span class="sxs-lookup"><span data-stu-id="de163-465">Three letters and six digits:</span></span>
  
-  <span data-ttu-id="de163-466">Tres letras (sin distinción entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="de163-466">Three letters (not case-sensitive)</span></span> 
    
- <span data-ttu-id="de163-467">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="de163-467">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="de163-468">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="de163-468">Checksum</span></span>

<span data-ttu-id="de163-469">No</span><span class="sxs-lookup"><span data-stu-id="de163-469">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="de163-470">Definición</span><span class="sxs-lookup"><span data-stu-id="de163-470">Definition</span></span>

<span data-ttu-id="de163-471">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="de163-471">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="de163-472">La expresión `Regex_latvia_eu_driver's_license_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="de163-472">The regular expression  `Regex_latvia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="de163-473">Se encuentra una `Keywords_latvia_eu_driver's_license_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="de163-473">A keyword from  `Keywords_latvia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_driver's_license_number" />
          <Match idRef="Keywords_latvia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="de163-474">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="de163-474">Keywords</span></span>

<span data-ttu-id="de163-475">| |</span><span class="sxs-lookup"><span data-stu-id="de163-475"></span></span>
|<span data-ttu-id="de163-476">**Keywords_latvia_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="de163-476">**Keywords_latvia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="de163-477">listas</span><span class="sxs-lookup"><span data-stu-id="de163-477">dl#</span></span>  <br/> <span data-ttu-id="de163-478">driver license</span><span class="sxs-lookup"><span data-stu-id="de163-478">driver license</span></span>  <br/> <span data-ttu-id="de163-479">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="de163-479">driver license number</span></span>  <br/> <span data-ttu-id="de163-480">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="de163-480">driver licence</span></span>  <br/> <span data-ttu-id="de163-481">Lic de drivers.</span><span class="sxs-lookup"><span data-stu-id="de163-481">drivers lic.</span></span>  <br/> <span data-ttu-id="de163-482">drivers license</span><span class="sxs-lookup"><span data-stu-id="de163-482">drivers license</span></span>  <br/> <span data-ttu-id="de163-483">drivers licence</span><span class="sxs-lookup"><span data-stu-id="de163-483">drivers licence</span></span>  <br/> <span data-ttu-id="de163-484">driver's license</span><span class="sxs-lookup"><span data-stu-id="de163-484">driver's license</span></span>  <br/> <span data-ttu-id="de163-485">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="de163-485">driver's license number</span></span>  <br/> <span data-ttu-id="de163-486">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="de163-486">driver's licence number</span></span>  <br/> <span data-ttu-id="de163-487">número de licencia de conducir</span><span class="sxs-lookup"><span data-stu-id="de163-487">driving license number</span></span>  <br/> <span data-ttu-id="de163-488">dlno #</span><span class="sxs-lookup"><span data-stu-id="de163-488">dlno#</span></span>  <br/> <span data-ttu-id="de163-489">autovadītāja apliecība</span><span class="sxs-lookup"><span data-stu-id="de163-489">autovadītāja apliecība</span></span>  <br/> |
   
## <a name="lithuania"></a><span data-ttu-id="de163-490">Lituania</span><span class="sxs-lookup"><span data-stu-id="de163-490">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="de163-491">Dé</span><span class="sxs-lookup"><span data-stu-id="de163-491">Format</span></span>

<span data-ttu-id="de163-492">Ocho dígitos sin espacios y delimitadores</span><span class="sxs-lookup"><span data-stu-id="de163-492">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="de163-493">Patrón</span><span class="sxs-lookup"><span data-stu-id="de163-493">Pattern</span></span>

 <span data-ttu-id="de163-494">Ocho dígitos</span><span class="sxs-lookup"><span data-stu-id="de163-494">Eight digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="de163-495">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="de163-495">Checksum</span></span>

<span data-ttu-id="de163-496">No</span><span class="sxs-lookup"><span data-stu-id="de163-496">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="de163-497">Definición</span><span class="sxs-lookup"><span data-stu-id="de163-497">Definition</span></span>

<span data-ttu-id="de163-498">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="de163-498">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="de163-499">La expresión `Regex_lithuania_eu_driver's_license_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="de163-499">The regular expression  `Regex_lithuania_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="de163-500">Se encuentra una `Keywords_lithuania_eu_driver's_license_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="de163-500">A keyword from  `Keywords_lithuania_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_driver's_license_number" />
          <Match idRef="Keywords_lithuania_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="de163-501">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="de163-501">Keywords</span></span>

<span data-ttu-id="de163-502">| |</span><span class="sxs-lookup"><span data-stu-id="de163-502"></span></span>
|<span data-ttu-id="de163-503">**Keywords_lithuania_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="de163-503">**Keywords_lithuania_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="de163-504">listas</span><span class="sxs-lookup"><span data-stu-id="de163-504">dl#</span></span>  <br/> <span data-ttu-id="de163-505">driver license</span><span class="sxs-lookup"><span data-stu-id="de163-505">driver license</span></span>  <br/> <span data-ttu-id="de163-506">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="de163-506">driver license number</span></span>  <br/> <span data-ttu-id="de163-507">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="de163-507">driver licence</span></span>  <br/> <span data-ttu-id="de163-508">Lic de drivers.</span><span class="sxs-lookup"><span data-stu-id="de163-508">drivers lic.</span></span>  <br/> <span data-ttu-id="de163-509">drivers license</span><span class="sxs-lookup"><span data-stu-id="de163-509">drivers license</span></span>  <br/> <span data-ttu-id="de163-510">drivers licence</span><span class="sxs-lookup"><span data-stu-id="de163-510">drivers licence</span></span>  <br/> <span data-ttu-id="de163-511">driver's license</span><span class="sxs-lookup"><span data-stu-id="de163-511">driver's license</span></span>  <br/> <span data-ttu-id="de163-512">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="de163-512">driver's license number</span></span>  <br/> <span data-ttu-id="de163-513">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="de163-513">driver's licence number</span></span>  <br/> <span data-ttu-id="de163-514">número de licencia de conducir</span><span class="sxs-lookup"><span data-stu-id="de163-514">driving license number</span></span>  <br/> <span data-ttu-id="de163-515">dlno #</span><span class="sxs-lookup"><span data-stu-id="de163-515">dlno#</span></span>  <br/> <span data-ttu-id="de163-516">vairuotojo pažymėjimas</span><span class="sxs-lookup"><span data-stu-id="de163-516">vairuotojo pažymėjimas</span></span>  <br/> |
   
## <a name="luxemburg"></a><span data-ttu-id="de163-517">Luxemburgo</span><span class="sxs-lookup"><span data-stu-id="de163-517">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="de163-518">Dé</span><span class="sxs-lookup"><span data-stu-id="de163-518">Format</span></span>

<span data-ttu-id="de163-519">Seis dígitos sin espacios y delimitadores</span><span class="sxs-lookup"><span data-stu-id="de163-519">Six digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="de163-520">Patrón</span><span class="sxs-lookup"><span data-stu-id="de163-520">Pattern</span></span>

 <span data-ttu-id="de163-521">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="de163-521">Six digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="de163-522">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="de163-522">Checksum</span></span>

<span data-ttu-id="de163-523">No</span><span class="sxs-lookup"><span data-stu-id="de163-523">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="de163-524">Definición</span><span class="sxs-lookup"><span data-stu-id="de163-524">Definition</span></span>

<span data-ttu-id="de163-525">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="de163-525">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="de163-526">La expresión `Regex_luxemburg_eu_driver's_license_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="de163-526">The regular expression  `Regex_luxemburg_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="de163-527">Se encuentra una `Keywords_luxemburg_eu_driver's_license_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="de163-527">A keyword from  `Keywords_luxemburg_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_luxemburg_eu_driver's_license_number" />
          <Match idRef="Keywords_luxemburg_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="de163-528">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="de163-528">Keywords</span></span>

<span data-ttu-id="de163-529">| |</span><span class="sxs-lookup"><span data-stu-id="de163-529"></span></span>
|<span data-ttu-id="de163-530">**Keywords_luxemburg_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="de163-530">**Keywords_luxemburg_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="de163-531">listas</span><span class="sxs-lookup"><span data-stu-id="de163-531">dl#</span></span>  <br/> <span data-ttu-id="de163-532">driver license</span><span class="sxs-lookup"><span data-stu-id="de163-532">driver license</span></span>  <br/> <span data-ttu-id="de163-533">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="de163-533">driver license number</span></span>  <br/> <span data-ttu-id="de163-534">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="de163-534">driver licence</span></span>  <br/> <span data-ttu-id="de163-535">Lic de drivers.</span><span class="sxs-lookup"><span data-stu-id="de163-535">drivers lic.</span></span>  <br/> <span data-ttu-id="de163-536">drivers license</span><span class="sxs-lookup"><span data-stu-id="de163-536">drivers license</span></span>  <br/> <span data-ttu-id="de163-537">drivers licence</span><span class="sxs-lookup"><span data-stu-id="de163-537">drivers licence</span></span>  <br/> <span data-ttu-id="de163-538">driver's license</span><span class="sxs-lookup"><span data-stu-id="de163-538">driver's license</span></span>  <br/> <span data-ttu-id="de163-539">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="de163-539">driver's license number</span></span>  <br/> <span data-ttu-id="de163-540">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="de163-540">driver's licence number</span></span>  <br/> <span data-ttu-id="de163-541">número de licencia de conducir</span><span class="sxs-lookup"><span data-stu-id="de163-541">driving license number</span></span>  <br/> <span data-ttu-id="de163-542">dlno #</span><span class="sxs-lookup"><span data-stu-id="de163-542">dlno#</span></span>  <br/> <span data-ttu-id="de163-543">fahrerlaubnis</span><span class="sxs-lookup"><span data-stu-id="de163-543">fahrerlaubnis</span></span>  <br/> |
   
## <a name="malta"></a><span data-ttu-id="de163-544">Malta</span><span class="sxs-lookup"><span data-stu-id="de163-544">Malta</span></span>

### <a name="format"></a><span data-ttu-id="de163-545">Dé</span><span class="sxs-lookup"><span data-stu-id="de163-545">Format</span></span>

<span data-ttu-id="de163-546">Combinación de dos caracteres y seis dígitos en el patrón especificado</span><span class="sxs-lookup"><span data-stu-id="de163-546">Combination of two characters and six digits in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="de163-547">Patrón</span><span class="sxs-lookup"><span data-stu-id="de163-547">Pattern</span></span>

<span data-ttu-id="de163-548">Combinación de dos caracteres y seis dígitos:</span><span class="sxs-lookup"><span data-stu-id="de163-548">Combination of two characters and six digits:</span></span>
  
- <span data-ttu-id="de163-549">Dos caracteres (dígitos o letras, no distinguen entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="de163-549">Two characters (digits or letters, not case-sensitive)</span></span>
    
- <span data-ttu-id="de163-550">Un espacio (opcional) </span><span class="sxs-lookup"><span data-stu-id="de163-550">A space (optional)</span></span>
    
- <span data-ttu-id="de163-551">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="de163-551">Three digits</span></span>
    
- <span data-ttu-id="de163-552">Un espacio (opcional) </span><span class="sxs-lookup"><span data-stu-id="de163-552">A space (optional)</span></span>
    
- <span data-ttu-id="de163-553">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="de163-553">Three digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="de163-554">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="de163-554">Checksum</span></span>

<span data-ttu-id="de163-555">No</span><span class="sxs-lookup"><span data-stu-id="de163-555">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="de163-556">Definición</span><span class="sxs-lookup"><span data-stu-id="de163-556">Definition</span></span>

<span data-ttu-id="de163-557">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="de163-557">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="de163-558">La expresión `Regex_malta_eu_driver's_license_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="de163-558">The regular expression  `Regex_malta_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="de163-559">Se encuentra una `Keywords_malta_eu_driver's_license_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="de163-559">A keyword from  `Keywords_malta_eu_driver's_license_number` is found.</span></span> 
    
```
<!-- EU Driver's License Number -->
 <Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_driver's_license_number" />
          <Match idRef="Keywords_malta_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="de163-560">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="de163-560">Keywords</span></span>

<span data-ttu-id="de163-561">| |</span><span class="sxs-lookup"><span data-stu-id="de163-561"></span></span>
|<span data-ttu-id="de163-562">**Keywords_malta_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="de163-562">**Keywords_malta_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="de163-563">listas</span><span class="sxs-lookup"><span data-stu-id="de163-563">dl#</span></span>  <br/> <span data-ttu-id="de163-564">driver license</span><span class="sxs-lookup"><span data-stu-id="de163-564">driver license</span></span>  <br/> <span data-ttu-id="de163-565">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="de163-565">driver license number</span></span>  <br/> <span data-ttu-id="de163-566">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="de163-566">driver licence</span></span>  <br/> <span data-ttu-id="de163-567">Lic de drivers.</span><span class="sxs-lookup"><span data-stu-id="de163-567">drivers lic.</span></span>  <br/> <span data-ttu-id="de163-568">drivers license</span><span class="sxs-lookup"><span data-stu-id="de163-568">drivers license</span></span>  <br/> <span data-ttu-id="de163-569">drivers licence</span><span class="sxs-lookup"><span data-stu-id="de163-569">drivers licence</span></span>  <br/> <span data-ttu-id="de163-570">driver's license</span><span class="sxs-lookup"><span data-stu-id="de163-570">driver's license</span></span>  <br/> <span data-ttu-id="de163-571">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="de163-571">driver's license number</span></span>  <br/> <span data-ttu-id="de163-572">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="de163-572">driver's licence number</span></span>  <br/> <span data-ttu-id="de163-573">número de licencia de conducir</span><span class="sxs-lookup"><span data-stu-id="de163-573">driving license number</span></span>  <br/> <span data-ttu-id="de163-574">dlno #</span><span class="sxs-lookup"><span data-stu-id="de163-574">dlno#</span></span>  <br/> <span data-ttu-id="de163-575">liċenzja sewqan</span><span class="sxs-lookup"><span data-stu-id="de163-575">liċenzja tas-sewqan</span></span>  <br/> |
   
## <a name="netherlands"></a><span data-ttu-id="de163-576">Países Bajos</span><span class="sxs-lookup"><span data-stu-id="de163-576">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="de163-577">Dé</span><span class="sxs-lookup"><span data-stu-id="de163-577">Format</span></span>

<span data-ttu-id="de163-578">10 dígitos sin espacios y delimitadores</span><span class="sxs-lookup"><span data-stu-id="de163-578">10 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="de163-579">Patrón</span><span class="sxs-lookup"><span data-stu-id="de163-579">Pattern</span></span>

<span data-ttu-id="de163-580">10 dígitos</span><span class="sxs-lookup"><span data-stu-id="de163-580">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="de163-581">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="de163-581">Checksum</span></span>

<span data-ttu-id="de163-582">No</span><span class="sxs-lookup"><span data-stu-id="de163-582">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="de163-583">Definición</span><span class="sxs-lookup"><span data-stu-id="de163-583">Definition</span></span>

<span data-ttu-id="de163-584">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="de163-584">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="de163-585">La expresión `Regex_netherlands_eu_driver's_license_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="de163-585">The regular expression  `Regex_netherlands_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="de163-586">Se encuentra una `Keywords_netherlands_eu_driver's_license_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="de163-586">A keyword from  `Keywords_netherlands_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_driver's_license_number" />
          <Match idRef="Keywords_netherlands_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="de163-587">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="de163-587">Keywords</span></span>

<span data-ttu-id="de163-588">| |</span><span class="sxs-lookup"><span data-stu-id="de163-588"></span></span>
|<span data-ttu-id="de163-589">**Keywords_netherlands_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="de163-589">**Keywords_netherlands_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="de163-590">listas</span><span class="sxs-lookup"><span data-stu-id="de163-590">dl#</span></span>  <br/> <span data-ttu-id="de163-591">driver license</span><span class="sxs-lookup"><span data-stu-id="de163-591">driver license</span></span>  <br/> <span data-ttu-id="de163-592">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="de163-592">driver license number</span></span>  <br/> <span data-ttu-id="de163-593">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="de163-593">driver licence</span></span>  <br/> <span data-ttu-id="de163-594">Lic de drivers.</span><span class="sxs-lookup"><span data-stu-id="de163-594">drivers lic.</span></span>  <br/> <span data-ttu-id="de163-595">drivers license</span><span class="sxs-lookup"><span data-stu-id="de163-595">drivers license</span></span>  <br/> <span data-ttu-id="de163-596">drivers licence</span><span class="sxs-lookup"><span data-stu-id="de163-596">drivers licence</span></span>  <br/> <span data-ttu-id="de163-597">driver's license</span><span class="sxs-lookup"><span data-stu-id="de163-597">driver's license</span></span>  <br/> <span data-ttu-id="de163-598">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="de163-598">driver's license number</span></span>  <br/> <span data-ttu-id="de163-599">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="de163-599">driver's licence number</span></span>  <br/> <span data-ttu-id="de163-600">número de licencia de conducir</span><span class="sxs-lookup"><span data-stu-id="de163-600">driving license number</span></span>  <br/> <span data-ttu-id="de163-601">dlno #</span><span class="sxs-lookup"><span data-stu-id="de163-601">dlno#</span></span>  <br/> <span data-ttu-id="de163-602">permis de conduire</span><span class="sxs-lookup"><span data-stu-id="de163-602">permis de conduire</span></span>  <br/> <span data-ttu-id="de163-603">rijbewijs</span><span class="sxs-lookup"><span data-stu-id="de163-603">rijbewijs</span></span>  <br/> <span data-ttu-id="de163-604">rijbewijsnummer</span><span class="sxs-lookup"><span data-stu-id="de163-604">rijbewijsnummer</span></span>  <br/> |
   
## <a name="poland"></a><span data-ttu-id="de163-605">Polonia</span><span class="sxs-lookup"><span data-stu-id="de163-605">Poland</span></span>

### <a name="format"></a><span data-ttu-id="de163-606">Dé</span><span class="sxs-lookup"><span data-stu-id="de163-606">Format</span></span>

<span data-ttu-id="de163-607">14 dígitos que contienen 2 barras diagonales</span><span class="sxs-lookup"><span data-stu-id="de163-607">14 digits containing 2 forward slashes</span></span>
  
### <a name="pattern"></a><span data-ttu-id="de163-608">Patrón</span><span class="sxs-lookup"><span data-stu-id="de163-608">Pattern</span></span>

<span data-ttu-id="de163-609">14 dígitos y 2 barras diagonales:</span><span class="sxs-lookup"><span data-stu-id="de163-609">14 digits and 2 forward slashes:</span></span>
  
-  <span data-ttu-id="de163-610">Cinco dígitos</span><span class="sxs-lookup"><span data-stu-id="de163-610">Five digits</span></span> 
    
- <span data-ttu-id="de163-611">Una barra diagonal </span><span class="sxs-lookup"><span data-stu-id="de163-611">A forward slash</span></span>
    
- <span data-ttu-id="de163-612">Dos dígitos</span><span class="sxs-lookup"><span data-stu-id="de163-612">Two digits</span></span>
    
- <span data-ttu-id="de163-613">Una barra diagonal </span><span class="sxs-lookup"><span data-stu-id="de163-613">A forward slash</span></span>
    
- <span data-ttu-id="de163-614">Siete dígitos</span><span class="sxs-lookup"><span data-stu-id="de163-614">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="de163-615">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="de163-615">Checksum</span></span>

<span data-ttu-id="de163-616">No</span><span class="sxs-lookup"><span data-stu-id="de163-616">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="de163-617">Definición</span><span class="sxs-lookup"><span data-stu-id="de163-617">Definition</span></span>

<span data-ttu-id="de163-618">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="de163-618">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="de163-619">La expresión `Regex_poland_eu_driver's_license_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="de163-619">The regular expression  `Regex_poland_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="de163-620">Se encuentra una `Keywords_poland_eu_driver's_license_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="de163-620">A keyword from  `Keywords_poland_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_poland_eu_driver's_license_number" />
          <Match idRef="Keywords_poland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="de163-621">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="de163-621">Keywords</span></span>

<span data-ttu-id="de163-622">| |</span><span class="sxs-lookup"><span data-stu-id="de163-622"></span></span>
|<span data-ttu-id="de163-623">**Keywords_poland_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="de163-623">**Keywords_poland_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="de163-624">listas</span><span class="sxs-lookup"><span data-stu-id="de163-624">dl#</span></span>  <br/> <span data-ttu-id="de163-625">driver license</span><span class="sxs-lookup"><span data-stu-id="de163-625">driver license</span></span>  <br/> <span data-ttu-id="de163-626">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="de163-626">driver license number</span></span>  <br/> <span data-ttu-id="de163-627">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="de163-627">driver licence</span></span>  <br/> <span data-ttu-id="de163-628">Lic de drivers.</span><span class="sxs-lookup"><span data-stu-id="de163-628">drivers lic.</span></span>  <br/> <span data-ttu-id="de163-629">drivers license</span><span class="sxs-lookup"><span data-stu-id="de163-629">drivers license</span></span>  <br/> <span data-ttu-id="de163-630">drivers licence</span><span class="sxs-lookup"><span data-stu-id="de163-630">drivers licence</span></span>  <br/> <span data-ttu-id="de163-631">driver's license</span><span class="sxs-lookup"><span data-stu-id="de163-631">driver's license</span></span>  <br/> <span data-ttu-id="de163-632">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="de163-632">driver's license number</span></span>  <br/> <span data-ttu-id="de163-633">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="de163-633">driver's licence number</span></span>  <br/> <span data-ttu-id="de163-634">número de licencia de conducir</span><span class="sxs-lookup"><span data-stu-id="de163-634">driving license number</span></span>  <br/> <span data-ttu-id="de163-635">dlno #</span><span class="sxs-lookup"><span data-stu-id="de163-635">dlno#</span></span>  <br/> <span data-ttu-id="de163-636">Prawo jazdy</span><span class="sxs-lookup"><span data-stu-id="de163-636">prawo jazdy</span></span>  <br/> |
   
## <a name="portugal"></a><span data-ttu-id="de163-637">Portugal</span><span class="sxs-lookup"><span data-stu-id="de163-637">Portugal</span></span>

### <a name="format"></a><span data-ttu-id="de163-638">Dé</span><span class="sxs-lookup"><span data-stu-id="de163-638">Format</span></span>

<span data-ttu-id="de163-639">Dos letras seguidas de siete números en el patrón especificado</span><span class="sxs-lookup"><span data-stu-id="de163-639">Two letters followed by a seven numbers in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="de163-640">Patrón</span><span class="sxs-lookup"><span data-stu-id="de163-640">Pattern</span></span>

<span data-ttu-id="de163-641">Dos letras seguidas de siete números con caracteres especiales:</span><span class="sxs-lookup"><span data-stu-id="de163-641">Two letters followed by seven numbers with special characters:</span></span>
  
-  <span data-ttu-id="de163-642">Dos letras (sin distinción entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="de163-642">Two letters (not case-sensitive)</span></span> 
    
- <span data-ttu-id="de163-643">Un guión </span><span class="sxs-lookup"><span data-stu-id="de163-643">A hyphen</span></span>
    
- <span data-ttu-id="de163-644">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="de163-644">Six digits</span></span>
    
- <span data-ttu-id="de163-645">Un espacio</span><span class="sxs-lookup"><span data-stu-id="de163-645">A space</span></span>
    
- <span data-ttu-id="de163-646">Un dígito</span><span class="sxs-lookup"><span data-stu-id="de163-646">One digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="de163-647">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="de163-647">Checksum</span></span>

<span data-ttu-id="de163-648">No</span><span class="sxs-lookup"><span data-stu-id="de163-648">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="de163-649">Definición</span><span class="sxs-lookup"><span data-stu-id="de163-649">Definition</span></span>

<span data-ttu-id="de163-650">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="de163-650">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="de163-651">La expresión `Regex_portugal_eu_driver's_license_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="de163-651">The regular expression  `Regex_portugal_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="de163-652">Se encuentra una `Keywords_portugal_eu_driver's_license_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="de163-652">A keyword from  `Keywords_portugal_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_driver's_license_number" />
          <Match idRef="Keywords_portugal_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="de163-653">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="de163-653">Keywords</span></span>

<span data-ttu-id="de163-654">| |</span><span class="sxs-lookup"><span data-stu-id="de163-654"></span></span>
|<span data-ttu-id="de163-655">**Keywords_portugal_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="de163-655">**Keywords_portugal_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="de163-656">listas</span><span class="sxs-lookup"><span data-stu-id="de163-656">dl#</span></span>  <br/> <span data-ttu-id="de163-657">driver license</span><span class="sxs-lookup"><span data-stu-id="de163-657">driver license</span></span>  <br/> <span data-ttu-id="de163-658">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="de163-658">driver license number</span></span>  <br/> <span data-ttu-id="de163-659">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="de163-659">driver licence</span></span>  <br/> <span data-ttu-id="de163-660">Lic de drivers.</span><span class="sxs-lookup"><span data-stu-id="de163-660">drivers lic.</span></span>  <br/> <span data-ttu-id="de163-661">drivers license</span><span class="sxs-lookup"><span data-stu-id="de163-661">drivers license</span></span>  <br/> <span data-ttu-id="de163-662">drivers licence</span><span class="sxs-lookup"><span data-stu-id="de163-662">drivers licence</span></span>  <br/> <span data-ttu-id="de163-663">driver's license</span><span class="sxs-lookup"><span data-stu-id="de163-663">driver's license</span></span>  <br/> <span data-ttu-id="de163-664">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="de163-664">driver's license number</span></span>  <br/> <span data-ttu-id="de163-665">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="de163-665">driver's licence number</span></span>  <br/> <span data-ttu-id="de163-666">número de licencia de conducir</span><span class="sxs-lookup"><span data-stu-id="de163-666">driving license number</span></span>  <br/> <span data-ttu-id="de163-667">dlno #</span><span class="sxs-lookup"><span data-stu-id="de163-667">dlno#</span></span>  <br/> <span data-ttu-id="de163-668">Carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="de163-668">carteira de motorista</span></span>  <br/> |
   
## <a name="romania"></a><span data-ttu-id="de163-669">Rumania</span><span class="sxs-lookup"><span data-stu-id="de163-669">Romania</span></span>

### <a name="format"></a><span data-ttu-id="de163-670">Dé</span><span class="sxs-lookup"><span data-stu-id="de163-670">Format</span></span>

<span data-ttu-id="de163-671">Un carácter seguido de ocho dígitos</span><span class="sxs-lookup"><span data-stu-id="de163-671">One character followed by eight digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="de163-672">Patrón</span><span class="sxs-lookup"><span data-stu-id="de163-672">Pattern</span></span>

<span data-ttu-id="de163-673">Un carácter seguido de ocho dígitos:</span><span class="sxs-lookup"><span data-stu-id="de163-673">One character followed by eight digits:</span></span>
  
-  <span data-ttu-id="de163-674">Una letra (no distingue entre mayúsculas y minúsculas) o un dígito</span><span class="sxs-lookup"><span data-stu-id="de163-674">One letter (not case-sensitive) or digit</span></span> 
    
- <span data-ttu-id="de163-675">Ocho dígitos</span><span class="sxs-lookup"><span data-stu-id="de163-675">Eight digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="de163-676">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="de163-676">Checksum</span></span>

<span data-ttu-id="de163-677">No</span><span class="sxs-lookup"><span data-stu-id="de163-677">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="de163-678">Definición</span><span class="sxs-lookup"><span data-stu-id="de163-678">Definition</span></span>

<span data-ttu-id="de163-679">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="de163-679">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="de163-680">La expresión `Regex_romania_eu_driver's_license_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="de163-680">The regular expression  `Regex_romania_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="de163-681">Se encuentra una `Keywords_romania_eu_driver's_license_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="de163-681">A keyword from  `Keywords_romania_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_driver's_license_number" />
          <Match idRef="Keywords_romania_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="de163-682">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="de163-682">Keywords</span></span>

<span data-ttu-id="de163-683">| |</span><span class="sxs-lookup"><span data-stu-id="de163-683"></span></span>
|<span data-ttu-id="de163-684">**Keywords_romania_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="de163-684">**Keywords_romania_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="de163-685">listas</span><span class="sxs-lookup"><span data-stu-id="de163-685">dl#</span></span>  <br/> <span data-ttu-id="de163-686">driver license</span><span class="sxs-lookup"><span data-stu-id="de163-686">driver license</span></span>  <br/> <span data-ttu-id="de163-687">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="de163-687">driver license number</span></span>  <br/> <span data-ttu-id="de163-688">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="de163-688">driver licence</span></span>  <br/> <span data-ttu-id="de163-689">Lic de drivers.</span><span class="sxs-lookup"><span data-stu-id="de163-689">drivers lic.</span></span>  <br/> <span data-ttu-id="de163-690">drivers license</span><span class="sxs-lookup"><span data-stu-id="de163-690">drivers license</span></span>  <br/> <span data-ttu-id="de163-691">drivers licence</span><span class="sxs-lookup"><span data-stu-id="de163-691">drivers licence</span></span>  <br/> <span data-ttu-id="de163-692">driver's license</span><span class="sxs-lookup"><span data-stu-id="de163-692">driver's license</span></span>  <br/> <span data-ttu-id="de163-693">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="de163-693">driver's license number</span></span>  <br/> <span data-ttu-id="de163-694">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="de163-694">driver's licence number</span></span>  <br/> <span data-ttu-id="de163-695">número de licencia de conducir</span><span class="sxs-lookup"><span data-stu-id="de163-695">driving license number</span></span>  <br/> <span data-ttu-id="de163-696">dlno #</span><span class="sxs-lookup"><span data-stu-id="de163-696">dlno#</span></span>  <br/> <span data-ttu-id="de163-697">Perm de conducere</span><span class="sxs-lookup"><span data-stu-id="de163-697">permis de conducere</span></span>  <br/> |
   
## <a name="slovakia"></a><span data-ttu-id="de163-698">Eslovaquia</span><span class="sxs-lookup"><span data-stu-id="de163-698">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="de163-699">Dé</span><span class="sxs-lookup"><span data-stu-id="de163-699">Format</span></span>

<span data-ttu-id="de163-700">Un carácter seguido de siete dígitos</span><span class="sxs-lookup"><span data-stu-id="de163-700">One character followed by seven digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="de163-701">Patrón</span><span class="sxs-lookup"><span data-stu-id="de163-701">Pattern</span></span>

<span data-ttu-id="de163-702">Un carácter seguido de siete dígitos</span><span class="sxs-lookup"><span data-stu-id="de163-702">One character followed by seven digits</span></span>
  
- <span data-ttu-id="de163-703">Una letra (no distingue entre mayúsculas y minúsculas) o un dígito</span><span class="sxs-lookup"><span data-stu-id="de163-703">One letter (not case-sensitive) or digit</span></span>
    
-  <span data-ttu-id="de163-704">Siete dígitos</span><span class="sxs-lookup"><span data-stu-id="de163-704">Seven digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="de163-705">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="de163-705">Checksum</span></span>

<span data-ttu-id="de163-706">No</span><span class="sxs-lookup"><span data-stu-id="de163-706">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="de163-707">Definición</span><span class="sxs-lookup"><span data-stu-id="de163-707">Definition</span></span>

<span data-ttu-id="de163-708">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="de163-708">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="de163-709">La expresión `Regex_slovakia_eu_driver's_license_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="de163-709">The regular expression  `Regex_slovakia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="de163-710">Se encuentra una `Keywords_slovakia_eu_driver's_license_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="de163-710">A keyword from  `Keywords_slovakia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovaknia_eu_driver's_license_number" />
          <Match idRef="Keywords_slovakia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="de163-711">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="de163-711">Keywords</span></span>

<span data-ttu-id="de163-712">| |</span><span class="sxs-lookup"><span data-stu-id="de163-712"></span></span>
|<span data-ttu-id="de163-713">**Keywords_slovakia_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="de163-713">**Keywords_slovakia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="de163-714">listas</span><span class="sxs-lookup"><span data-stu-id="de163-714">dl#</span></span>  <br/> <span data-ttu-id="de163-715">driver license</span><span class="sxs-lookup"><span data-stu-id="de163-715">driver license</span></span>  <br/> <span data-ttu-id="de163-716">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="de163-716">driver license number</span></span>  <br/> <span data-ttu-id="de163-717">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="de163-717">driver licence</span></span>  <br/> <span data-ttu-id="de163-718">Lic de drivers.</span><span class="sxs-lookup"><span data-stu-id="de163-718">drivers lic.</span></span>  <br/> <span data-ttu-id="de163-719">drivers license</span><span class="sxs-lookup"><span data-stu-id="de163-719">drivers license</span></span>  <br/> <span data-ttu-id="de163-720">drivers licence</span><span class="sxs-lookup"><span data-stu-id="de163-720">drivers licence</span></span>  <br/> <span data-ttu-id="de163-721">driver's license</span><span class="sxs-lookup"><span data-stu-id="de163-721">driver's license</span></span>  <br/> <span data-ttu-id="de163-722">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="de163-722">driver's license number</span></span>  <br/> <span data-ttu-id="de163-723">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="de163-723">driver's licence number</span></span>  <br/> <span data-ttu-id="de163-724">número de licencia de conducir</span><span class="sxs-lookup"><span data-stu-id="de163-724">driving license number</span></span>  <br/> <span data-ttu-id="de163-725">dlno #</span><span class="sxs-lookup"><span data-stu-id="de163-725">dlno#</span></span>  <br/> <span data-ttu-id="de163-726">vodičský preukaz</span><span class="sxs-lookup"><span data-stu-id="de163-726">vodičský preukaz</span></span>  <br/> |
   
## <a name="slovenia"></a><span data-ttu-id="de163-727">Eslovenia</span><span class="sxs-lookup"><span data-stu-id="de163-727">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="de163-728">Dé</span><span class="sxs-lookup"><span data-stu-id="de163-728">Format</span></span>

<span data-ttu-id="de163-729">Nueve dígitos sin espacios y delimitadores</span><span class="sxs-lookup"><span data-stu-id="de163-729">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="de163-730">Patrón</span><span class="sxs-lookup"><span data-stu-id="de163-730">Pattern</span></span>

<span data-ttu-id="de163-731">Nueve dígitos</span><span class="sxs-lookup"><span data-stu-id="de163-731">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="de163-732">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="de163-732">Checksum</span></span>

<span data-ttu-id="de163-733">No</span><span class="sxs-lookup"><span data-stu-id="de163-733">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="de163-734">Definición</span><span class="sxs-lookup"><span data-stu-id="de163-734">Definition</span></span>

<span data-ttu-id="de163-735">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="de163-735">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="de163-736">La expresión `Regex_slovenia_eu_driver's_license_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="de163-736">The regular expression  `Regex_slovenia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="de163-737">Se encuentra una `Keywords_slovenia_eu_driver's_license_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="de163-737">A keyword from  `Keywords_slovenia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_driver's_license_number" />
          <Match idRef="Keywords_slovenia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="de163-738">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="de163-738">Keywords</span></span>

<span data-ttu-id="de163-739">| |</span><span class="sxs-lookup"><span data-stu-id="de163-739"></span></span>
|<span data-ttu-id="de163-740">**Keywords_slovenia_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="de163-740">**Keywords_slovenia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="de163-741">listas</span><span class="sxs-lookup"><span data-stu-id="de163-741">dl#</span></span>  <br/> <span data-ttu-id="de163-742">driver license</span><span class="sxs-lookup"><span data-stu-id="de163-742">driver license</span></span>  <br/> <span data-ttu-id="de163-743">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="de163-743">driver license number</span></span>  <br/> <span data-ttu-id="de163-744">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="de163-744">driver licence</span></span>  <br/> <span data-ttu-id="de163-745">Lic de drivers.</span><span class="sxs-lookup"><span data-stu-id="de163-745">drivers lic.</span></span>  <br/> <span data-ttu-id="de163-746">drivers license</span><span class="sxs-lookup"><span data-stu-id="de163-746">drivers license</span></span>  <br/> <span data-ttu-id="de163-747">drivers licence</span><span class="sxs-lookup"><span data-stu-id="de163-747">drivers licence</span></span>  <br/> <span data-ttu-id="de163-748">driver's license</span><span class="sxs-lookup"><span data-stu-id="de163-748">driver's license</span></span>  <br/> <span data-ttu-id="de163-749">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="de163-749">driver's license number</span></span>  <br/> <span data-ttu-id="de163-750">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="de163-750">driver's licence number</span></span>  <br/> <span data-ttu-id="de163-751">número de licencia de conducir</span><span class="sxs-lookup"><span data-stu-id="de163-751">driving license number</span></span>  <br/> <span data-ttu-id="de163-752">dlno #</span><span class="sxs-lookup"><span data-stu-id="de163-752">dlno#</span></span>  <br/> <span data-ttu-id="de163-753">vozniško dovoljenje</span><span class="sxs-lookup"><span data-stu-id="de163-753">vozniško dovoljenje</span></span>  <br/> |
   
## <a name="spain"></a><span data-ttu-id="de163-754">España</span><span class="sxs-lookup"><span data-stu-id="de163-754">Spain</span></span>

### <a name="format"></a><span data-ttu-id="de163-755">Dé</span><span class="sxs-lookup"><span data-stu-id="de163-755">Format</span></span>

<span data-ttu-id="de163-756">Ocho dígitos seguidos de un carácter</span><span class="sxs-lookup"><span data-stu-id="de163-756">Eight digits followed by one character</span></span>
  
### <a name="pattern"></a><span data-ttu-id="de163-757">Patrón</span><span class="sxs-lookup"><span data-stu-id="de163-757">Pattern</span></span>

<span data-ttu-id="de163-758">Ocho dígitos seguidos de un carácter:</span><span class="sxs-lookup"><span data-stu-id="de163-758">Eight digits followed by one character:</span></span>
  
-  <span data-ttu-id="de163-759">Ocho dígitos</span><span class="sxs-lookup"><span data-stu-id="de163-759">Eight digits</span></span> 
    
- <span data-ttu-id="de163-760">Un dígito o letra (no distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="de163-760">One digit or letter (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="de163-761">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="de163-761">Checksum</span></span>

<span data-ttu-id="de163-762">Sí</span><span class="sxs-lookup"><span data-stu-id="de163-762">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="de163-763">Definición</span><span class="sxs-lookup"><span data-stu-id="de163-763">Definition</span></span>

<span data-ttu-id="de163-764">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="de163-764">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="de163-765">La función `Func_spain_eu_driver's_license_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="de163-765">The function  `Func_spain_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="de163-766">Se encuentra una `Keywords_spain_eu_driver's_license_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="de163-766">A keyword from  `Keywords_spain_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spain_eu_driver's_license_number" />
          <Match idRef="Keywords_spain_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="de163-767">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="de163-767">Keywords</span></span>

<span data-ttu-id="de163-768">| |</span><span class="sxs-lookup"><span data-stu-id="de163-768"></span></span>
|<span data-ttu-id="de163-769">**Keywords_spain_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="de163-769">**Keywords_spain_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="de163-770">dlno #</span><span class="sxs-lookup"><span data-stu-id="de163-770">dlno#</span></span>  <br/> <span data-ttu-id="de163-771">listas</span><span class="sxs-lookup"><span data-stu-id="de163-771">dl#</span></span>  <br/> <span data-ttu-id="de163-772">Lic de drivers.</span><span class="sxs-lookup"><span data-stu-id="de163-772">drivers lic.</span></span>  <br/> <span data-ttu-id="de163-773">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="de163-773">driver licence</span></span>  <br/> <span data-ttu-id="de163-774">driver license</span><span class="sxs-lookup"><span data-stu-id="de163-774">driver license</span></span>  <br/> <span data-ttu-id="de163-775">drivers licence</span><span class="sxs-lookup"><span data-stu-id="de163-775">drivers licence</span></span>  <br/> <span data-ttu-id="de163-776">drivers license</span><span class="sxs-lookup"><span data-stu-id="de163-776">drivers license</span></span>  <br/> <span data-ttu-id="de163-777">driver's licence</span><span class="sxs-lookup"><span data-stu-id="de163-777">driver's licence</span></span>  <br/> <span data-ttu-id="de163-778">driver's license</span><span class="sxs-lookup"><span data-stu-id="de163-778">driver's license</span></span>  <br/> <span data-ttu-id="de163-779">driving licence</span><span class="sxs-lookup"><span data-stu-id="de163-779">driving licence</span></span>  <br/> <span data-ttu-id="de163-780">driving license</span><span class="sxs-lookup"><span data-stu-id="de163-780">driving license</span></span>  <br/> <span data-ttu-id="de163-781">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="de163-781">driver licence number</span></span>  <br/> <span data-ttu-id="de163-782">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="de163-782">driver license number</span></span>  <br/> <span data-ttu-id="de163-783">número de licencia de drivers</span><span class="sxs-lookup"><span data-stu-id="de163-783">drivers licence number</span></span>  <br/> <span data-ttu-id="de163-784">número de licencia de drivers</span><span class="sxs-lookup"><span data-stu-id="de163-784">drivers license number</span></span>  <br/> <span data-ttu-id="de163-785">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="de163-785">driver's licence number</span></span>  <br/> <span data-ttu-id="de163-786">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="de163-786">driver's license number</span></span>  <br/> <span data-ttu-id="de163-787">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="de163-787">driving licence number</span></span>  <br/> <span data-ttu-id="de163-788">número de licencia de conducir</span><span class="sxs-lookup"><span data-stu-id="de163-788">driving license number</span></span>  <br/> <span data-ttu-id="de163-789">permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="de163-789">driving permit</span></span>  <br/> <span data-ttu-id="de163-790">número de permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="de163-790">driving permit number</span></span>  <br/> <span data-ttu-id="de163-791">permisos de conducción</span><span class="sxs-lookup"><span data-stu-id="de163-791">permiso de conducción</span></span>  <br/> <span data-ttu-id="de163-792">permisos conducción</span><span class="sxs-lookup"><span data-stu-id="de163-792">permiso conducción</span></span>  <br/> <span data-ttu-id="de163-793">número de licencia conducir</span><span class="sxs-lookup"><span data-stu-id="de163-793">número licencia conducir</span></span>  <br/> <span data-ttu-id="de163-794">número de cuaderno de conducir</span><span class="sxs-lookup"><span data-stu-id="de163-794">número de carnet de conducir</span></span>  <br/> <span data-ttu-id="de163-795">número conducir de cuaderno</span><span class="sxs-lookup"><span data-stu-id="de163-795">número carnet conducir</span></span>  <br/> <span data-ttu-id="de163-796">licenciar conducir</span><span class="sxs-lookup"><span data-stu-id="de163-796">licencia conducir</span></span>  <br/> <span data-ttu-id="de163-797">número de permisos de conducir</span><span class="sxs-lookup"><span data-stu-id="de163-797">número de permiso de conducir</span></span>  <br/> <span data-ttu-id="de163-798">número de permisos conducir</span><span class="sxs-lookup"><span data-stu-id="de163-798">número de permiso conducir</span></span>  <br/> <span data-ttu-id="de163-799">número permisos conducir</span><span class="sxs-lookup"><span data-stu-id="de163-799">número permiso conducir</span></span>  <br/> <span data-ttu-id="de163-800">permisos conducir</span><span class="sxs-lookup"><span data-stu-id="de163-800">permiso conducir</span></span>  <br/> <span data-ttu-id="de163-801">licencia de manejo</span><span class="sxs-lookup"><span data-stu-id="de163-801">licencia de manejo</span></span>  <br/> <span data-ttu-id="de163-802">el cuaderno de conducir</span><span class="sxs-lookup"><span data-stu-id="de163-802">el carnet de conducir</span></span>  <br/> <span data-ttu-id="de163-803">conducir del cuaderno</span><span class="sxs-lookup"><span data-stu-id="de163-803">carnet conducir</span></span>  <br/> |
   
## <a name="sweden"></a><span data-ttu-id="de163-804">Suecia</span><span class="sxs-lookup"><span data-stu-id="de163-804">Sweden</span></span>

### <a name="format"></a><span data-ttu-id="de163-805">Dé</span><span class="sxs-lookup"><span data-stu-id="de163-805">Format</span></span>

<span data-ttu-id="de163-806">Diez dígitos que contienen un guión</span><span class="sxs-lookup"><span data-stu-id="de163-806">Ten digits containing a hyphen</span></span>
  
### <a name="pattern"></a><span data-ttu-id="de163-807">Patrón</span><span class="sxs-lookup"><span data-stu-id="de163-807">Pattern</span></span>

<span data-ttu-id="de163-808">Diez dígitos que contienen un guión:</span><span class="sxs-lookup"><span data-stu-id="de163-808">Ten digits containing a hyphen:</span></span>
  
-  <span data-ttu-id="de163-809">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="de163-809">Six digits</span></span> 
    
- <span data-ttu-id="de163-810">Un guión</span><span class="sxs-lookup"><span data-stu-id="de163-810">A hyphen</span></span>
    
- <span data-ttu-id="de163-811">Cuatro dígitos</span><span class="sxs-lookup"><span data-stu-id="de163-811">Four digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="de163-812">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="de163-812">Checksum</span></span>

<span data-ttu-id="de163-813">No</span><span class="sxs-lookup"><span data-stu-id="de163-813">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="de163-814">Definición</span><span class="sxs-lookup"><span data-stu-id="de163-814">Definition</span></span>

<span data-ttu-id="de163-815">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="de163-815">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="de163-816">La expresión `Regex_sweden_eu_driver's_license_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="de163-816">The regular expression  `Regex_sweden_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="de163-817">Se encuentra una `Keywords_sweden_eu_driver's_license_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="de163-817">A keyword from  `Keywords_sweden_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_sweden_eu_driver's_license_number" />
          <Match idRef="Keywords_sweden_eu_driver's_license_number" />
        </Pattern>
</Entity> 
```

### <a name="keywords"></a><span data-ttu-id="de163-818">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="de163-818">Keywords</span></span>

<span data-ttu-id="de163-819">| |</span><span class="sxs-lookup"><span data-stu-id="de163-819"></span></span>
|<span data-ttu-id="de163-820">**Keywords_sweden_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="de163-820">**Keywords_sweden_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="de163-821">listas</span><span class="sxs-lookup"><span data-stu-id="de163-821">dl#</span></span>  <br/> <span data-ttu-id="de163-822">driver license</span><span class="sxs-lookup"><span data-stu-id="de163-822">driver license</span></span>  <br/> <span data-ttu-id="de163-823">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="de163-823">driver license number</span></span>  <br/> <span data-ttu-id="de163-824">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="de163-824">driver licence</span></span>  <br/> <span data-ttu-id="de163-825">Lic de drivers.</span><span class="sxs-lookup"><span data-stu-id="de163-825">drivers lic.</span></span>  <br/> <span data-ttu-id="de163-826">drivers license</span><span class="sxs-lookup"><span data-stu-id="de163-826">drivers license</span></span>  <br/> <span data-ttu-id="de163-827">drivers licence</span><span class="sxs-lookup"><span data-stu-id="de163-827">drivers licence</span></span>  <br/> <span data-ttu-id="de163-828">driver's license</span><span class="sxs-lookup"><span data-stu-id="de163-828">driver's license</span></span>  <br/> <span data-ttu-id="de163-829">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="de163-829">driver's license number</span></span>  <br/> <span data-ttu-id="de163-830">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="de163-830">driver's licence number</span></span>  <br/> <span data-ttu-id="de163-831">número de licencia de conducir</span><span class="sxs-lookup"><span data-stu-id="de163-831">driving license number</span></span>  <br/> <span data-ttu-id="de163-832">dlno #</span><span class="sxs-lookup"><span data-stu-id="de163-832">dlno#</span></span>  <br/> <span data-ttu-id="de163-833">körkort</span><span class="sxs-lookup"><span data-stu-id="de163-833">körkort</span></span>  <br/> |
   
## <a name="uk"></a><span data-ttu-id="de163-834">LIBRA</span><span class="sxs-lookup"><span data-stu-id="de163-834">UK</span></span>

<span data-ttu-id="de163-835">Para obtener más información, consulte la sección "Reino Unido.</span><span class="sxs-lookup"><span data-stu-id="de163-835">For details, see the section "U.K.</span></span> <span data-ttu-id="de163-836">Número de permiso de conducir "en [Qué buscan los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="de163-836">Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="de163-837">Vea también</span><span class="sxs-lookup"><span data-stu-id="de163-837">See also</span></span>

[<span data-ttu-id="de163-838">Qué buscan los tipos de información confidencial</span><span class="sxs-lookup"><span data-stu-id="de163-838">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

