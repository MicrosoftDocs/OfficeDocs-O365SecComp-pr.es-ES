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
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32255778"
---
# <a name="eu-drivers-license-number"></a><span data-ttu-id="5d24e-104">Número de permiso de conducción de la UE</span><span class="sxs-lookup"><span data-stu-id="5d24e-104">EU Driver's License Number</span></span>

<span data-ttu-id="5d24e-105">En este tema se muestra qué busca una directiva de prevención de pérdida de datos (DLP) cuando detecta el tipo de información confidencial del número de licencia de conductor de la UE.</span><span class="sxs-lookup"><span data-stu-id="5d24e-105">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Driver's License Number sensitive information type.</span></span> <span data-ttu-id="5d24e-106">Este tipo de información confidencial define distintos patrones, palabras clave y otras pruebas para cada país.</span><span class="sxs-lookup"><span data-stu-id="5d24e-106">This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="5d24e-107">Austria</span><span class="sxs-lookup"><span data-stu-id="5d24e-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="5d24e-108">Formato</span><span class="sxs-lookup"><span data-stu-id="5d24e-108">Format</span></span>

<span data-ttu-id="5d24e-109">Ocho dígitos sin espacios y delimitadores</span><span class="sxs-lookup"><span data-stu-id="5d24e-109">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="5d24e-110">Patrón</span><span class="sxs-lookup"><span data-stu-id="5d24e-110">Pattern</span></span>

<span data-ttu-id="5d24e-111">Ocho dígitos</span><span class="sxs-lookup"><span data-stu-id="5d24e-111">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="5d24e-112">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="5d24e-112">Checksum</span></span>

<span data-ttu-id="5d24e-113">No</span><span class="sxs-lookup"><span data-stu-id="5d24e-113">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="5d24e-114">Definición</span><span class="sxs-lookup"><span data-stu-id="5d24e-114">Definition</span></span>

<span data-ttu-id="5d24e-115">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="5d24e-115">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5d24e-116">La expresión `Regex_austria_eu_driver's_license_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="5d24e-116">The regular expression  `Regex_austria_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5d24e-117">Se encuentra una `Keywords_austria_eu_driver's_license_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="5d24e-117">A keyword from  `Keywords_austria_eu_driver's_license_number` is found.</span></span> 
    
```
<!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_driver's_license_number" />
          <Match idRef="Keywords_austria_eu_driver's_license_number" />
        </Pattern>
    </Entity>

```

### <a name="keywords"></a><span data-ttu-id="5d24e-118">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="5d24e-118">Keywords</span></span>

<span data-ttu-id="5d24e-119">| |</span><span class="sxs-lookup"><span data-stu-id="5d24e-119"></span></span>
|<span data-ttu-id="5d24e-120">**Keywords_austria_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="5d24e-120">**Keywords_austria_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="5d24e-121">listas</span><span class="sxs-lookup"><span data-stu-id="5d24e-121">dl#</span></span>  <br/> <span data-ttu-id="5d24e-122">driver license</span><span class="sxs-lookup"><span data-stu-id="5d24e-122">driver license</span></span>  <br/> <span data-ttu-id="5d24e-123">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="5d24e-123">driver license number</span></span>  <br/> <span data-ttu-id="5d24e-124">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="5d24e-124">driver licence</span></span>  <br/> <span data-ttu-id="5d24e-125">Lic de drivers.</span><span class="sxs-lookup"><span data-stu-id="5d24e-125">drivers lic.</span></span>  <br/> <span data-ttu-id="5d24e-126">drivers license</span><span class="sxs-lookup"><span data-stu-id="5d24e-126">drivers license</span></span>  <br/> <span data-ttu-id="5d24e-127">driver's licence</span><span class="sxs-lookup"><span data-stu-id="5d24e-127">driver's licence</span></span>  <br/> <span data-ttu-id="5d24e-128">driver's license</span><span class="sxs-lookup"><span data-stu-id="5d24e-128">driver's license</span></span>  <br/> <span data-ttu-id="5d24e-129">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="5d24e-129">driver's license number</span></span>  <br/> <span data-ttu-id="5d24e-130">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="5d24e-130">driver's licence number</span></span>  <br/>  <span data-ttu-id="5d24e-131">número de licencia de conducir</span><span class="sxs-lookup"><span data-stu-id="5d24e-131">driving license number</span></span>  <br/> <span data-ttu-id="5d24e-132">dlno #</span><span class="sxs-lookup"><span data-stu-id="5d24e-132">dlno#</span></span>  <br/> <span data-ttu-id="5d24e-133">fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="5d24e-133">fuhrerschein</span></span>  <br/> <span data-ttu-id="5d24e-134">fuhrerschein Republik Osterreich</span><span class="sxs-lookup"><span data-stu-id="5d24e-134">fuhrerschein republik osterreich</span></span>  <br/> |
   
## <a name="belgium"></a><span data-ttu-id="5d24e-135">Bélgica</span><span class="sxs-lookup"><span data-stu-id="5d24e-135">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="5d24e-136">Formato</span><span class="sxs-lookup"><span data-stu-id="5d24e-136">Format</span></span>

<span data-ttu-id="5d24e-137">10 dígitos sin espacios y delimitadores</span><span class="sxs-lookup"><span data-stu-id="5d24e-137">10 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="5d24e-138">Patrón</span><span class="sxs-lookup"><span data-stu-id="5d24e-138">Pattern</span></span>

<span data-ttu-id="5d24e-139">10 dígitos</span><span class="sxs-lookup"><span data-stu-id="5d24e-139">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="5d24e-140">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="5d24e-140">Checksum</span></span>

<span data-ttu-id="5d24e-141">No</span><span class="sxs-lookup"><span data-stu-id="5d24e-141">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="5d24e-142">Definición</span><span class="sxs-lookup"><span data-stu-id="5d24e-142">Definition</span></span>

<span data-ttu-id="5d24e-143">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="5d24e-143">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5d24e-144">La expresión `Regex_belgium_eu_driver's_license_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="5d24e-144">The regular expression  `Regex_belgium_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5d24e-145">Se encuentra una `Keywords_belgium_eu_driver's_license_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="5d24e-145">A keyword from  `Keywords_belgium_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_driver's_license_number" />
          <Match idRef="Keywords_belgium_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="5d24e-146">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="5d24e-146">Keywords</span></span>

<span data-ttu-id="5d24e-147">| |</span><span class="sxs-lookup"><span data-stu-id="5d24e-147"></span></span>
|<span data-ttu-id="5d24e-148">**Keywords__belgium_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="5d24e-148">**Keywords__belgium_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="5d24e-149">listas</span><span class="sxs-lookup"><span data-stu-id="5d24e-149">dl#</span></span>  <br/> <span data-ttu-id="5d24e-150">driver license</span><span class="sxs-lookup"><span data-stu-id="5d24e-150">driver license</span></span>  <br/> <span data-ttu-id="5d24e-151">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="5d24e-151">driver license number</span></span>  <br/> <span data-ttu-id="5d24e-152">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="5d24e-152">driver licence</span></span>  <br/> <span data-ttu-id="5d24e-153">Lic de drivers.</span><span class="sxs-lookup"><span data-stu-id="5d24e-153">drivers lic.</span></span>  <br/> <span data-ttu-id="5d24e-154">drivers license</span><span class="sxs-lookup"><span data-stu-id="5d24e-154">drivers license</span></span>  <br/> <span data-ttu-id="5d24e-155">drivers licence</span><span class="sxs-lookup"><span data-stu-id="5d24e-155">drivers licence</span></span>  <br/> <span data-ttu-id="5d24e-156">driver's license</span><span class="sxs-lookup"><span data-stu-id="5d24e-156">driver's license</span></span>  <br/> <span data-ttu-id="5d24e-157">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="5d24e-157">driver's license number</span></span>  <br/> <span data-ttu-id="5d24e-158">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="5d24e-158">driver's licence number</span></span>  <br/> <span data-ttu-id="5d24e-159">dlno #</span><span class="sxs-lookup"><span data-stu-id="5d24e-159">dlno#</span></span>  <br/> <span data-ttu-id="5d24e-160">rijbewijs</span><span class="sxs-lookup"><span data-stu-id="5d24e-160">rijbewijs</span></span>  <br/> <span data-ttu-id="5d24e-161">rijbewijsnummer</span><span class="sxs-lookup"><span data-stu-id="5d24e-161">rijbewijsnummer</span></span>  <br/> <span data-ttu-id="5d24e-162">führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="5d24e-162">führerscheinnummer</span></span>  <br/> <span data-ttu-id="5d24e-163">fuhrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="5d24e-163">fuhrerscheinnummer</span></span>  <br/> <span data-ttu-id="5d24e-164">fuehrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="5d24e-164">fuehrerscheinnummer</span></span>  <br/> <span data-ttu-id="5d24e-165">Führerschein-NR</span><span class="sxs-lookup"><span data-stu-id="5d24e-165">führerschein- nr</span></span>  <br/> <span data-ttu-id="5d24e-166">fuehrerschein-NR</span><span class="sxs-lookup"><span data-stu-id="5d24e-166">fuehrerschein- Nr</span></span>  <br/> <span data-ttu-id="5d24e-167">fuehrerschein-NR</span><span class="sxs-lookup"><span data-stu-id="5d24e-167">fuehrerschein- nr</span></span>  <br/> |
   
## <a name="bulgaria"></a><span data-ttu-id="5d24e-168">Bulgaria</span><span class="sxs-lookup"><span data-stu-id="5d24e-168">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="5d24e-169">Formato</span><span class="sxs-lookup"><span data-stu-id="5d24e-169">Format</span></span>

<span data-ttu-id="5d24e-170">Nueve dígitos sin espacios y delimitadores</span><span class="sxs-lookup"><span data-stu-id="5d24e-170">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="5d24e-171">Patrón</span><span class="sxs-lookup"><span data-stu-id="5d24e-171">Pattern</span></span>

<span data-ttu-id="5d24e-172">Nueve dígitos</span><span class="sxs-lookup"><span data-stu-id="5d24e-172">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="5d24e-173">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="5d24e-173">Checksum</span></span>

<span data-ttu-id="5d24e-174">No</span><span class="sxs-lookup"><span data-stu-id="5d24e-174">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="5d24e-175">Definición</span><span class="sxs-lookup"><span data-stu-id="5d24e-175">Definition</span></span>

<span data-ttu-id="5d24e-176">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="5d24e-176">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5d24e-177">La expresión `Regex_bulgaria_eu_driver's_license_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="5d24e-177">The regular expression  `Regex_bulgaria_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5d24e-178">Se encuentra una `Keywords_bulgaria_eu_driver's_license_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="5d24e-178">A keyword from  `Keywords_bulgaria_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
             <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_driver's_license_number" />
          <Match idRef="Keywords_bulgaria_eu_driver's_license_number" />
        </Pattern> 
</Entity>    

```

### <a name="keywords"></a><span data-ttu-id="5d24e-179">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="5d24e-179">Keywords</span></span>

<span data-ttu-id="5d24e-180">| |</span><span class="sxs-lookup"><span data-stu-id="5d24e-180"></span></span>
|<span data-ttu-id="5d24e-181">**Keywords_bulgaria_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="5d24e-181">**Keywords_bulgaria_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="5d24e-182">listas</span><span class="sxs-lookup"><span data-stu-id="5d24e-182">dl#</span></span>  <br/> <span data-ttu-id="5d24e-183">driver license</span><span class="sxs-lookup"><span data-stu-id="5d24e-183">driver license</span></span>  <br/> <span data-ttu-id="5d24e-184">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="5d24e-184">driver license number</span></span>  <br/> <span data-ttu-id="5d24e-185">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="5d24e-185">driver licence</span></span>  <br/> <span data-ttu-id="5d24e-186">Lic de drivers.</span><span class="sxs-lookup"><span data-stu-id="5d24e-186">drivers lic.</span></span>  <br/> <span data-ttu-id="5d24e-187">drivers license</span><span class="sxs-lookup"><span data-stu-id="5d24e-187">drivers license</span></span>  <br/> <span data-ttu-id="5d24e-188">drivers licence</span><span class="sxs-lookup"><span data-stu-id="5d24e-188">drivers licence</span></span>  <br/> <span data-ttu-id="5d24e-189">driver's license</span><span class="sxs-lookup"><span data-stu-id="5d24e-189">driver's license</span></span>  <br/> <span data-ttu-id="5d24e-190">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="5d24e-190">driver's license number</span></span>  <br/> <span data-ttu-id="5d24e-191">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="5d24e-191">driver's licence number</span></span>  <br/> <span data-ttu-id="5d24e-192">número de licencia de conducir</span><span class="sxs-lookup"><span data-stu-id="5d24e-192">driving license number</span></span>  <br/> <span data-ttu-id="5d24e-193">dlno #</span><span class="sxs-lookup"><span data-stu-id="5d24e-193">dlno#</span></span>  <br/> <span data-ttu-id="5d24e-194">свидетелство за управление на мпс</span><span class="sxs-lookup"><span data-stu-id="5d24e-194">свидетелство за управление на мпс</span></span>  <br/> <span data-ttu-id="5d24e-195">свидетелство за управление на моторно превозно средство</span><span class="sxs-lookup"><span data-stu-id="5d24e-195">свидетелство за управление на моторно превозно средство</span></span>  <br/> <span data-ttu-id="5d24e-196">сумпс</span><span class="sxs-lookup"><span data-stu-id="5d24e-196">сумпс</span></span>  <br/> <span data-ttu-id="5d24e-197">шофьорска книжка</span><span class="sxs-lookup"><span data-stu-id="5d24e-197">шофьорска книжка</span></span>  <br/> |
   
## <a name="croatia"></a><span data-ttu-id="5d24e-198">Croacia</span><span class="sxs-lookup"><span data-stu-id="5d24e-198">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="5d24e-199">Formato</span><span class="sxs-lookup"><span data-stu-id="5d24e-199">Format</span></span>

<span data-ttu-id="5d24e-200">Ocho dígitos sin espacios y delimitadores</span><span class="sxs-lookup"><span data-stu-id="5d24e-200">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="5d24e-201">Patrón</span><span class="sxs-lookup"><span data-stu-id="5d24e-201">Pattern</span></span>

<span data-ttu-id="5d24e-202">Ocho dígitos</span><span class="sxs-lookup"><span data-stu-id="5d24e-202">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="5d24e-203">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="5d24e-203">Checksum</span></span>

<span data-ttu-id="5d24e-204">No</span><span class="sxs-lookup"><span data-stu-id="5d24e-204">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="5d24e-205">Definición</span><span class="sxs-lookup"><span data-stu-id="5d24e-205">Definition</span></span>

<span data-ttu-id="5d24e-206">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="5d24e-206">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5d24e-207">La expresión `Regex_croatia_eu_driver's_license_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="5d24e-207">The regular expression  `Regex_croatia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5d24e-208">Se encuentra una `Keywords_croatia_eu_driver's_license_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="5d24e-208">A keyword from  `Keywords_croatia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_driver's_license_number" />
          <Match idRef="Keywords_croatia_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="5d24e-209">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="5d24e-209">Keywords</span></span>

<span data-ttu-id="5d24e-210">| |</span><span class="sxs-lookup"><span data-stu-id="5d24e-210"></span></span>
|<span data-ttu-id="5d24e-211">**Keywords_croatia_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="5d24e-211">**Keywords_croatia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="5d24e-212">listas</span><span class="sxs-lookup"><span data-stu-id="5d24e-212">dl#</span></span>  <br/> <span data-ttu-id="5d24e-213">driver license</span><span class="sxs-lookup"><span data-stu-id="5d24e-213">driver license</span></span>  <br/> <span data-ttu-id="5d24e-214">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="5d24e-214">driver license number</span></span>  <br/> <span data-ttu-id="5d24e-215">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="5d24e-215">driver licence</span></span>  <br/> <span data-ttu-id="5d24e-216">Lic de drivers.</span><span class="sxs-lookup"><span data-stu-id="5d24e-216">drivers lic.</span></span>  <br/> <span data-ttu-id="5d24e-217">drivers license</span><span class="sxs-lookup"><span data-stu-id="5d24e-217">drivers license</span></span>  <br/> <span data-ttu-id="5d24e-218">drivers licence</span><span class="sxs-lookup"><span data-stu-id="5d24e-218">drivers licence</span></span>  <br/> <span data-ttu-id="5d24e-219">driver's license</span><span class="sxs-lookup"><span data-stu-id="5d24e-219">driver's license</span></span>  <br/> <span data-ttu-id="5d24e-220">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="5d24e-220">driver's license number</span></span>  <br/> <span data-ttu-id="5d24e-221">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="5d24e-221">driver's licence number</span></span>  <br/> <span data-ttu-id="5d24e-222">número de licencia de conducir</span><span class="sxs-lookup"><span data-stu-id="5d24e-222">driving license number</span></span>  <br/> <span data-ttu-id="5d24e-223">dlno #</span><span class="sxs-lookup"><span data-stu-id="5d24e-223">dlno#</span></span>  <br/> <span data-ttu-id="5d24e-224">vozačka Dozvola</span><span class="sxs-lookup"><span data-stu-id="5d24e-224">vozačka dozvola</span></span>  <br/> |
   
## <a name="cyprus"></a><span data-ttu-id="5d24e-225">Chipre</span><span class="sxs-lookup"><span data-stu-id="5d24e-225">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="5d24e-226">Formato</span><span class="sxs-lookup"><span data-stu-id="5d24e-226">Format</span></span>

<span data-ttu-id="5d24e-227">12 dígitos sin espacios y delimitadores</span><span class="sxs-lookup"><span data-stu-id="5d24e-227">12 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="5d24e-228">Patrón</span><span class="sxs-lookup"><span data-stu-id="5d24e-228">Pattern</span></span>

<span data-ttu-id="5d24e-229">12 dígitos</span><span class="sxs-lookup"><span data-stu-id="5d24e-229">12 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="5d24e-230">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="5d24e-230">Checksum</span></span>

<span data-ttu-id="5d24e-231">No</span><span class="sxs-lookup"><span data-stu-id="5d24e-231">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="5d24e-232">Definición</span><span class="sxs-lookup"><span data-stu-id="5d24e-232">Definition</span></span>

<span data-ttu-id="5d24e-233">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="5d24e-233">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5d24e-234">La expresión `Regex_cyprus_eu_driver's_license_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="5d24e-234">The regular expression  `Regex_cyprus_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5d24e-235">Se encuentra una `Keywords_cyprus_eu_driver's_license_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="5d24e-235">A keyword from  `Keywords_cyprus_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_driver's_license_number" />
          <Match idRef="Keywords_cyprus_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="5d24e-236">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="5d24e-236">Keywords</span></span>

<span data-ttu-id="5d24e-237">| |</span><span class="sxs-lookup"><span data-stu-id="5d24e-237"></span></span>
|<span data-ttu-id="5d24e-238">**Keywords_cyprus_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="5d24e-238">**Keywords_cyprus_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="5d24e-239">listas</span><span class="sxs-lookup"><span data-stu-id="5d24e-239">dl#</span></span>  <br/> <span data-ttu-id="5d24e-240">driver license</span><span class="sxs-lookup"><span data-stu-id="5d24e-240">driver license</span></span>  <br/> <span data-ttu-id="5d24e-241">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="5d24e-241">driver license number</span></span>  <br/> <span data-ttu-id="5d24e-242">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="5d24e-242">driver licence</span></span>  <br/> <span data-ttu-id="5d24e-243">Lic de drivers.</span><span class="sxs-lookup"><span data-stu-id="5d24e-243">drivers lic.</span></span>  <br/> <span data-ttu-id="5d24e-244">drivers license</span><span class="sxs-lookup"><span data-stu-id="5d24e-244">drivers license</span></span>  <br/> <span data-ttu-id="5d24e-245">drivers licence</span><span class="sxs-lookup"><span data-stu-id="5d24e-245">drivers licence</span></span>  <br/> <span data-ttu-id="5d24e-246">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="5d24e-246">driver's license number</span></span>  <br/> <span data-ttu-id="5d24e-247">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="5d24e-247">driver's licence number</span></span>  <br/> <span data-ttu-id="5d24e-248">número de licencia de conducir</span><span class="sxs-lookup"><span data-stu-id="5d24e-248">driving license number</span></span>  <br/> <span data-ttu-id="5d24e-249">dlno #</span><span class="sxs-lookup"><span data-stu-id="5d24e-249">dlno#</span></span>  <br/> <span data-ttu-id="5d24e-250">άδεια οδήγησης</span><span class="sxs-lookup"><span data-stu-id="5d24e-250">άδεια οδήγησης</span></span>  <br/> |
   
## <a name="czech-republic"></a><span data-ttu-id="5d24e-251">Chequia</span><span class="sxs-lookup"><span data-stu-id="5d24e-251">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="5d24e-252">Formato</span><span class="sxs-lookup"><span data-stu-id="5d24e-252">Format</span></span>

<span data-ttu-id="5d24e-253">Dos letras seguidas de seis dígitos</span><span class="sxs-lookup"><span data-stu-id="5d24e-253">Two letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="5d24e-254">Patrón</span><span class="sxs-lookup"><span data-stu-id="5d24e-254">Pattern</span></span>

<span data-ttu-id="5d24e-255">Ocho letras y dígitos:</span><span class="sxs-lookup"><span data-stu-id="5d24e-255">Eight letters and digits:</span></span>
  
- <span data-ttu-id="5d24e-256">Dos letras (sin distinción entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="5d24e-256">Two letters (not case-sensitive)</span></span>
    
- <span data-ttu-id="5d24e-257">Un espacio (opcional) </span><span class="sxs-lookup"><span data-stu-id="5d24e-257">A space (optional)</span></span>
    
- <span data-ttu-id="5d24e-258">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="5d24e-258">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="5d24e-259">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="5d24e-259">Checksum</span></span>

<span data-ttu-id="5d24e-260">No</span><span class="sxs-lookup"><span data-stu-id="5d24e-260">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="5d24e-261">Definición</span><span class="sxs-lookup"><span data-stu-id="5d24e-261">Definition</span></span>

<span data-ttu-id="5d24e-262">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="5d24e-262">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5d24e-263">La expresión `Regex_czech_republic_eu_driver's_license_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="5d24e-263">The regular expression  `Regex_czech_republic_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5d24e-264">Se encuentra una `Keywords_czech_republic_eu_driver's_license_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="5d24e-264">A keyword from  `Keywords_czech_republic_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_driver's_license_number" />
          <Match idRef="Keywords_czech_republic_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="5d24e-265">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="5d24e-265">Keywords</span></span>

<span data-ttu-id="5d24e-266">| |</span><span class="sxs-lookup"><span data-stu-id="5d24e-266"></span></span>
|<span data-ttu-id="5d24e-267">**Keywords_czech_republic_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="5d24e-267">**Keywords_czech_republic_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="5d24e-268">listas</span><span class="sxs-lookup"><span data-stu-id="5d24e-268">dl#</span></span>  <br/> <span data-ttu-id="5d24e-269">driver license</span><span class="sxs-lookup"><span data-stu-id="5d24e-269">driver license</span></span>  <br/> <span data-ttu-id="5d24e-270">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="5d24e-270">driver license number</span></span>  <br/> <span data-ttu-id="5d24e-271">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="5d24e-271">driver licence</span></span>  <br/> <span data-ttu-id="5d24e-272">Lic de drivers.</span><span class="sxs-lookup"><span data-stu-id="5d24e-272">drivers lic.</span></span>  <br/> <span data-ttu-id="5d24e-273">drivers license</span><span class="sxs-lookup"><span data-stu-id="5d24e-273">drivers license</span></span>  <br/> <span data-ttu-id="5d24e-274">drivers licence</span><span class="sxs-lookup"><span data-stu-id="5d24e-274">drivers licence</span></span>  <br/> <span data-ttu-id="5d24e-275">driver's license</span><span class="sxs-lookup"><span data-stu-id="5d24e-275">driver's license</span></span>  <br/> <span data-ttu-id="5d24e-276">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="5d24e-276">driver's license number</span></span>  <br/> <span data-ttu-id="5d24e-277">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="5d24e-277">driver's license number</span></span>  <br/> <span data-ttu-id="5d24e-278">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="5d24e-278">driver's licence number</span></span>  <br/> <span data-ttu-id="5d24e-279">número de licencia de conducir</span><span class="sxs-lookup"><span data-stu-id="5d24e-279">driving license number</span></span>  <br/> <span data-ttu-id="5d24e-280">dlno #</span><span class="sxs-lookup"><span data-stu-id="5d24e-280">dlno#</span></span>  <br/> <span data-ttu-id="5d24e-281">řidičský prúkaz</span><span class="sxs-lookup"><span data-stu-id="5d24e-281">řidičský prúkaz</span></span>  <br/> |
   
## <a name="denmark"></a><span data-ttu-id="5d24e-282">Dinamarca</span><span class="sxs-lookup"><span data-stu-id="5d24e-282">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="5d24e-283">Formato</span><span class="sxs-lookup"><span data-stu-id="5d24e-283">Format</span></span>

<span data-ttu-id="5d24e-284">Ocho dígitos sin espacios y delimitadores</span><span class="sxs-lookup"><span data-stu-id="5d24e-284">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="5d24e-285">Patrón</span><span class="sxs-lookup"><span data-stu-id="5d24e-285">Pattern</span></span>

<span data-ttu-id="5d24e-286">Ocho dígitos</span><span class="sxs-lookup"><span data-stu-id="5d24e-286">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="5d24e-287">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="5d24e-287">Checksum</span></span>

<span data-ttu-id="5d24e-288">Sí</span><span class="sxs-lookup"><span data-stu-id="5d24e-288">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="5d24e-289">Definición</span><span class="sxs-lookup"><span data-stu-id="5d24e-289">Definition</span></span>

<span data-ttu-id="5d24e-290">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="5d24e-290">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5d24e-291">La expresión `Regex_denmark_eu_driver's_license_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="5d24e-291">The regular expression  `Regex_denmark_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5d24e-292">Se encuentra una `Keywords_denmark_eu_driver's_license_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="5d24e-292">A keyword from  `Keywords_denmark_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_driver's_license_number" />
          <Match idRef="Keywords_denmark_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="5d24e-293">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="5d24e-293">Keywords</span></span>

<span data-ttu-id="5d24e-294">| |</span><span class="sxs-lookup"><span data-stu-id="5d24e-294"></span></span>
|<span data-ttu-id="5d24e-295">**Keywords_denmark_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="5d24e-295">**Keywords_denmark_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="5d24e-296">listas</span><span class="sxs-lookup"><span data-stu-id="5d24e-296">dl#</span></span>  <br/> <span data-ttu-id="5d24e-297">driver license</span><span class="sxs-lookup"><span data-stu-id="5d24e-297">driver license</span></span>  <br/> <span data-ttu-id="5d24e-298">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="5d24e-298">driver license number</span></span>  <br/> <span data-ttu-id="5d24e-299">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="5d24e-299">driver licence</span></span>  <br/> <span data-ttu-id="5d24e-300">Lic de drivers.</span><span class="sxs-lookup"><span data-stu-id="5d24e-300">drivers lic.</span></span>  <br/> <span data-ttu-id="5d24e-301">drivers license</span><span class="sxs-lookup"><span data-stu-id="5d24e-301">drivers license</span></span>  <br/> <span data-ttu-id="5d24e-302">drivers licence</span><span class="sxs-lookup"><span data-stu-id="5d24e-302">drivers licence</span></span>  <br/> <span data-ttu-id="5d24e-303">driver's license</span><span class="sxs-lookup"><span data-stu-id="5d24e-303">driver's license</span></span>  <br/> <span data-ttu-id="5d24e-304">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="5d24e-304">driver's license number</span></span>  <br/> <span data-ttu-id="5d24e-305">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="5d24e-305">driver's licence number</span></span>  <br/> <span data-ttu-id="5d24e-306">número de licencia de conducir</span><span class="sxs-lookup"><span data-stu-id="5d24e-306">driving license number</span></span>  <br/> <span data-ttu-id="5d24e-307">dlno #</span><span class="sxs-lookup"><span data-stu-id="5d24e-307">dlno#</span></span>  <br/> <span data-ttu-id="5d24e-308">kørekort</span><span class="sxs-lookup"><span data-stu-id="5d24e-308">kørekort</span></span>  <br/> <span data-ttu-id="5d24e-309">kørekortnummer</span><span class="sxs-lookup"><span data-stu-id="5d24e-309">kørekortnummer</span></span>  <br/> |
   
## <a name="estonia"></a><span data-ttu-id="5d24e-310">Estonia</span><span class="sxs-lookup"><span data-stu-id="5d24e-310">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="5d24e-311">Formato</span><span class="sxs-lookup"><span data-stu-id="5d24e-311">Format</span></span>

<span data-ttu-id="5d24e-312">Dos letras seguidas de seis dígitos</span><span class="sxs-lookup"><span data-stu-id="5d24e-312">Two letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="5d24e-313">Patrón</span><span class="sxs-lookup"><span data-stu-id="5d24e-313">Pattern</span></span>

<span data-ttu-id="5d24e-314">Dos letras y seis dígitos:</span><span class="sxs-lookup"><span data-stu-id="5d24e-314">Two letters and six digits:</span></span>
  
-  <span data-ttu-id="5d24e-315">Las letras "ET" (sin distinción entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="5d24e-315">The letters "ET" (not case-sensitive)</span></span> 
    
- <span data-ttu-id="5d24e-316">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="5d24e-316">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="5d24e-317">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="5d24e-317">Checksum</span></span>

<span data-ttu-id="5d24e-318">No</span><span class="sxs-lookup"><span data-stu-id="5d24e-318">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="5d24e-319">Definición</span><span class="sxs-lookup"><span data-stu-id="5d24e-319">Definition</span></span>

<span data-ttu-id="5d24e-320">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="5d24e-320">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5d24e-321">La expresión `Regex_estonia_eu_driver's_license_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="5d24e-321">The regular expression  `Regex_estonia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5d24e-322">Se encuentra una `Keywords_estonia_eu_driver's_license_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="5d24e-322">A keyword from  `Keywords_estonia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_driver's_license_number" />
          <Match idRef="Keywords_estonia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="5d24e-323">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="5d24e-323">Keywords</span></span>

<span data-ttu-id="5d24e-324">| |</span><span class="sxs-lookup"><span data-stu-id="5d24e-324"></span></span>
|<span data-ttu-id="5d24e-325">**Keywords_estonia_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="5d24e-325">**Keywords_estonia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="5d24e-326">listas</span><span class="sxs-lookup"><span data-stu-id="5d24e-326">dl#</span></span>  <br/> <span data-ttu-id="5d24e-327">driver license</span><span class="sxs-lookup"><span data-stu-id="5d24e-327">driver license</span></span>  <br/> <span data-ttu-id="5d24e-328">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="5d24e-328">driver license number</span></span>  <br/> <span data-ttu-id="5d24e-329">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="5d24e-329">driver license number</span></span>  <br/> <span data-ttu-id="5d24e-330">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="5d24e-330">driver licence</span></span>  <br/> <span data-ttu-id="5d24e-331">Lic de drivers.</span><span class="sxs-lookup"><span data-stu-id="5d24e-331">drivers lic.</span></span>  <br/> <span data-ttu-id="5d24e-332">drivers license</span><span class="sxs-lookup"><span data-stu-id="5d24e-332">drivers license</span></span>  <br/> <span data-ttu-id="5d24e-333">drivers licence</span><span class="sxs-lookup"><span data-stu-id="5d24e-333">drivers licence</span></span>  <br/> <span data-ttu-id="5d24e-334">driver's license</span><span class="sxs-lookup"><span data-stu-id="5d24e-334">driver's license</span></span>  <br/> <span data-ttu-id="5d24e-335">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="5d24e-335">driver's license number</span></span>  <br/> <span data-ttu-id="5d24e-336">número de licencia de conducir</span><span class="sxs-lookup"><span data-stu-id="5d24e-336">driving license number</span></span>  <br/> <span data-ttu-id="5d24e-337">dlno #</span><span class="sxs-lookup"><span data-stu-id="5d24e-337">dlno#</span></span>  <br/> <span data-ttu-id="5d24e-338">permis de conduire</span><span class="sxs-lookup"><span data-stu-id="5d24e-338">permis de conduire</span></span>  <br/> |
   
## <a name="finland"></a><span data-ttu-id="5d24e-339">Finlandia</span><span class="sxs-lookup"><span data-stu-id="5d24e-339">Finland</span></span>

### <a name="format"></a><span data-ttu-id="5d24e-340">Formato</span><span class="sxs-lookup"><span data-stu-id="5d24e-340">Format</span></span>

<span data-ttu-id="5d24e-341">10 dígitos que contienen un guión</span><span class="sxs-lookup"><span data-stu-id="5d24e-341">10 digits containing a hyphen</span></span>
  
### <a name="pattern"></a><span data-ttu-id="5d24e-342">Patrón</span><span class="sxs-lookup"><span data-stu-id="5d24e-342">Pattern</span></span>

<span data-ttu-id="5d24e-343">10 dígitos que contienen un guión:</span><span class="sxs-lookup"><span data-stu-id="5d24e-343">10 digits containing a hyphen:</span></span>
  
-  <span data-ttu-id="5d24e-344">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="5d24e-344">Six digits</span></span> 
    
- <span data-ttu-id="5d24e-345">Un guión</span><span class="sxs-lookup"><span data-stu-id="5d24e-345">A hyphen</span></span>
    
-  <span data-ttu-id="5d24e-346">Cuatro dígitos</span><span class="sxs-lookup"><span data-stu-id="5d24e-346">Four digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="5d24e-347">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="5d24e-347">Checksum</span></span>

<span data-ttu-id="5d24e-348">No</span><span class="sxs-lookup"><span data-stu-id="5d24e-348">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="5d24e-349">Definición</span><span class="sxs-lookup"><span data-stu-id="5d24e-349">Definition</span></span>

<span data-ttu-id="5d24e-350">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="5d24e-350">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5d24e-351">La expresión `Regex_finland_eu_driver's_license_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="5d24e-351">The regular expression  `Regex_finland_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5d24e-352">Se encuentra una `Keywords_finland_eu_driver's_license_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="5d24e-352">A keyword from  `Keywords_finland_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_finland_eu_driver's_license_number" />
          <Match idRef="Keywords_finland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="5d24e-353">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="5d24e-353">Keywords</span></span>

<span data-ttu-id="5d24e-354">| |</span><span class="sxs-lookup"><span data-stu-id="5d24e-354"></span></span>
|<span data-ttu-id="5d24e-355">**Keywords_finland_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="5d24e-355">**Keywords_finland_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="5d24e-356">listas</span><span class="sxs-lookup"><span data-stu-id="5d24e-356">dl#</span></span>  <br/> <span data-ttu-id="5d24e-357">driver license</span><span class="sxs-lookup"><span data-stu-id="5d24e-357">driver license</span></span>  <br/> <span data-ttu-id="5d24e-358">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="5d24e-358">driver license number</span></span>  <br/> <span data-ttu-id="5d24e-359">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="5d24e-359">driver licence</span></span>  <br/> <span data-ttu-id="5d24e-360">Lic de drivers.</span><span class="sxs-lookup"><span data-stu-id="5d24e-360">drivers lic.</span></span>  <br/> <span data-ttu-id="5d24e-361">drivers license</span><span class="sxs-lookup"><span data-stu-id="5d24e-361">drivers license</span></span>  <br/> <span data-ttu-id="5d24e-362">drivers licence</span><span class="sxs-lookup"><span data-stu-id="5d24e-362">drivers licence</span></span>  <br/> <span data-ttu-id="5d24e-363">driver's license</span><span class="sxs-lookup"><span data-stu-id="5d24e-363">driver's license</span></span>  <br/> <span data-ttu-id="5d24e-364">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="5d24e-364">driver's license number</span></span>  <br/> <span data-ttu-id="5d24e-365">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="5d24e-365">driver's licence number</span></span>  <br/> <span data-ttu-id="5d24e-366">número de licencia de conducir</span><span class="sxs-lookup"><span data-stu-id="5d24e-366">driving license number</span></span>  <br/> <span data-ttu-id="5d24e-367">dlno #</span><span class="sxs-lookup"><span data-stu-id="5d24e-367">dlno#</span></span>  <br/> <span data-ttu-id="5d24e-368">ajokortti</span><span class="sxs-lookup"><span data-stu-id="5d24e-368">ajokortti</span></span>  <br/> |
   
## <a name="france"></a><span data-ttu-id="5d24e-369">Francia</span><span class="sxs-lookup"><span data-stu-id="5d24e-369">France</span></span>

<span data-ttu-id="5d24e-370">Para obtener más información, consulte la sección "número de permiso de conducción de Francia" en [Qué buscan los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="5d24e-370">For details, see the section "France Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="germany"></a><span data-ttu-id="5d24e-371">Alemania</span><span class="sxs-lookup"><span data-stu-id="5d24e-371">Germany</span></span>

<span data-ttu-id="5d24e-372">Para obtener más información, consulte la sección "número de permiso de conducción de alemán" en [el que se buscan los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="5d24e-372">For details, see the section "German Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="greece"></a><span data-ttu-id="5d24e-373">Grecia</span><span class="sxs-lookup"><span data-stu-id="5d24e-373">Greece</span></span>

### <a name="format"></a><span data-ttu-id="5d24e-374">Formato</span><span class="sxs-lookup"><span data-stu-id="5d24e-374">Format</span></span>

<span data-ttu-id="5d24e-375">Nueve dígitos sin espacios y delimitadores</span><span class="sxs-lookup"><span data-stu-id="5d24e-375">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="5d24e-376">Patrón</span><span class="sxs-lookup"><span data-stu-id="5d24e-376">Pattern</span></span>

 <span data-ttu-id="5d24e-377">Nueve dígitos</span><span class="sxs-lookup"><span data-stu-id="5d24e-377">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="5d24e-378">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="5d24e-378">Checksum</span></span>

<span data-ttu-id="5d24e-379">No</span><span class="sxs-lookup"><span data-stu-id="5d24e-379">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="5d24e-380">Definición</span><span class="sxs-lookup"><span data-stu-id="5d24e-380">Definition</span></span>

<span data-ttu-id="5d24e-381">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="5d24e-381">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5d24e-382">La expresión `Regex_greece_eu_driver's_license_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="5d24e-382">The regular expression  `Regex_greece_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5d24e-383">Se encuentra una `Keywords_greece_eu_driver's_license_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="5d24e-383">A keyword from  `Keywords_greece_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_driver's_license_number" />
          <Match idRef="Keywords_greece_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="5d24e-384">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="5d24e-384">Keywords</span></span>

<span data-ttu-id="5d24e-385">| |</span><span class="sxs-lookup"><span data-stu-id="5d24e-385"></span></span>
|<span data-ttu-id="5d24e-386">**Keywords_greece_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="5d24e-386">**Keywords_greece_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="5d24e-387">Biblioteca</span><span class="sxs-lookup"><span data-stu-id="5d24e-387">dlL#</span></span>  <br/> <span data-ttu-id="5d24e-388">driver license</span><span class="sxs-lookup"><span data-stu-id="5d24e-388">driver license</span></span>  <br/> <span data-ttu-id="5d24e-389">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="5d24e-389">driver license number</span></span>  <br/> <span data-ttu-id="5d24e-390">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="5d24e-390">driver licence</span></span>  <br/> <span data-ttu-id="5d24e-391">Lic de drivers.</span><span class="sxs-lookup"><span data-stu-id="5d24e-391">drivers lic.</span></span>  <br/> <span data-ttu-id="5d24e-392">drivers license</span><span class="sxs-lookup"><span data-stu-id="5d24e-392">drivers license</span></span>  <br/> <span data-ttu-id="5d24e-393">drivers licence</span><span class="sxs-lookup"><span data-stu-id="5d24e-393">drivers licence</span></span>  <br/> <span data-ttu-id="5d24e-394">driver's license</span><span class="sxs-lookup"><span data-stu-id="5d24e-394">driver's license</span></span>  <br/> <span data-ttu-id="5d24e-395">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="5d24e-395">driver's license number</span></span>  <br/> <span data-ttu-id="5d24e-396">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="5d24e-396">driver's licence number</span></span>  <br/> <span data-ttu-id="5d24e-397">número de licencia de conducir</span><span class="sxs-lookup"><span data-stu-id="5d24e-397">driving license number</span></span>  <br/> <span data-ttu-id="5d24e-398">dlno #</span><span class="sxs-lookup"><span data-stu-id="5d24e-398">dlno#</span></span>  <br/> <span data-ttu-id="5d24e-399">δεια οδήγησης</span><span class="sxs-lookup"><span data-stu-id="5d24e-399">δεια οδήγησης</span></span>  <br/> <span data-ttu-id="5d24e-400">Adeia odigisis</span><span class="sxs-lookup"><span data-stu-id="5d24e-400">Adeia odigisis</span></span>  <br/> |
   
## <a name="hungary"></a><span data-ttu-id="5d24e-401">Hungría</span><span class="sxs-lookup"><span data-stu-id="5d24e-401">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="5d24e-402">Formato</span><span class="sxs-lookup"><span data-stu-id="5d24e-402">Format</span></span>

<span data-ttu-id="5d24e-403">Dos letras seguidas de seis dígitos</span><span class="sxs-lookup"><span data-stu-id="5d24e-403">Two letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="5d24e-404">Patrón</span><span class="sxs-lookup"><span data-stu-id="5d24e-404">Pattern</span></span>

<span data-ttu-id="5d24e-405">Dos letras y seis dígitos:</span><span class="sxs-lookup"><span data-stu-id="5d24e-405">Two letters and six digits:</span></span>
  
-  <span data-ttu-id="5d24e-406">Dos letras (sin distinción entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="5d24e-406">Two letters (not case-sensitive)</span></span> 
    
- <span data-ttu-id="5d24e-407">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="5d24e-407">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="5d24e-408">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="5d24e-408">Checksum</span></span>

<span data-ttu-id="5d24e-409">No</span><span class="sxs-lookup"><span data-stu-id="5d24e-409">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="5d24e-410">Definición</span><span class="sxs-lookup"><span data-stu-id="5d24e-410">Definition</span></span>

<span data-ttu-id="5d24e-411">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="5d24e-411">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5d24e-412">La expresión `Regex_hungary_eu_driver's_license_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="5d24e-412">The regular expression  `Regex_hungary_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5d24e-413">Se encuentra una `Keywords_hungary_eu_driver's_license_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="5d24e-413">A keyword from  `Keywords_hungary_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_driver's_license_number" />
          <Match idRef="Keywords_hungary_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="5d24e-414">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="5d24e-414">Keywords</span></span>

<span data-ttu-id="5d24e-415">| |</span><span class="sxs-lookup"><span data-stu-id="5d24e-415"></span></span>
|<span data-ttu-id="5d24e-416">**Keywords_hungary_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="5d24e-416">**Keywords_hungary_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="5d24e-417">listas</span><span class="sxs-lookup"><span data-stu-id="5d24e-417">dl#</span></span>  <br/> <span data-ttu-id="5d24e-418">driver license</span><span class="sxs-lookup"><span data-stu-id="5d24e-418">driver license</span></span>  <br/> <span data-ttu-id="5d24e-419">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="5d24e-419">driver license number</span></span>  <br/> <span data-ttu-id="5d24e-420">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="5d24e-420">driver licence</span></span>  <br/> <span data-ttu-id="5d24e-421">Lic de drivers.</span><span class="sxs-lookup"><span data-stu-id="5d24e-421">drivers lic.</span></span>  <br/> <span data-ttu-id="5d24e-422">drivers license</span><span class="sxs-lookup"><span data-stu-id="5d24e-422">drivers license</span></span>  <br/> <span data-ttu-id="5d24e-423">drivers licence</span><span class="sxs-lookup"><span data-stu-id="5d24e-423">drivers licence</span></span>  <br/> <span data-ttu-id="5d24e-424">driver's license</span><span class="sxs-lookup"><span data-stu-id="5d24e-424">driver's license</span></span>  <br/> <span data-ttu-id="5d24e-425">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="5d24e-425">driver's license number</span></span>  <br/> <span data-ttu-id="5d24e-426">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="5d24e-426">driver's licence number</span></span>  <br/> <span data-ttu-id="5d24e-427">número de licencia de conducir</span><span class="sxs-lookup"><span data-stu-id="5d24e-427">driving license number</span></span>  <br/> <span data-ttu-id="5d24e-428">dlno #</span><span class="sxs-lookup"><span data-stu-id="5d24e-428">dlno#</span></span>  <br/> <span data-ttu-id="5d24e-429">vezetoi engedely</span><span class="sxs-lookup"><span data-stu-id="5d24e-429">vezetoi engedely</span></span>  <br/> |
   
## <a name="ireland"></a><span data-ttu-id="5d24e-430">Irlanda</span><span class="sxs-lookup"><span data-stu-id="5d24e-430">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="5d24e-431">Formato</span><span class="sxs-lookup"><span data-stu-id="5d24e-431">Format</span></span>

<span data-ttu-id="5d24e-432">Seis dígitos seguidos de cuatro letras</span><span class="sxs-lookup"><span data-stu-id="5d24e-432">Six digits followed by four letters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="5d24e-433">Patrón</span><span class="sxs-lookup"><span data-stu-id="5d24e-433">Pattern</span></span>

<span data-ttu-id="5d24e-434">Seis dígitos y cuatro letras:</span><span class="sxs-lookup"><span data-stu-id="5d24e-434">Six digits and four letters:</span></span>
  
- <span data-ttu-id="5d24e-435">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="5d24e-435">Six digits</span></span>
    
- <span data-ttu-id="5d24e-436">Cuatro letras (sin distinción entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="5d24e-436">Four letters (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="5d24e-437">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="5d24e-437">Checksum</span></span>

<span data-ttu-id="5d24e-438">No</span><span class="sxs-lookup"><span data-stu-id="5d24e-438">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="5d24e-439">Definición</span><span class="sxs-lookup"><span data-stu-id="5d24e-439">Definition</span></span>

<span data-ttu-id="5d24e-440">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="5d24e-440">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5d24e-441">La expresión `Regex_ireland_eu_driver's_license_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="5d24e-441">The regular expression  `Regex_ireland_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5d24e-442">Se encuentra una `Keywords_ireland_eu_driver's_license_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="5d24e-442">A keyword from  `Keywords_ireland_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_driver's_license_number" />
          <Match idRef="Keywords_ireland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="5d24e-443">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="5d24e-443">Keywords</span></span>

<span data-ttu-id="5d24e-444">| |</span><span class="sxs-lookup"><span data-stu-id="5d24e-444"></span></span>
|<span data-ttu-id="5d24e-445">**Keywords_ireland_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="5d24e-445">**Keywords_ireland_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="5d24e-446">listas</span><span class="sxs-lookup"><span data-stu-id="5d24e-446">dl#</span></span>  <br/> <span data-ttu-id="5d24e-447">driver license</span><span class="sxs-lookup"><span data-stu-id="5d24e-447">driver license</span></span>  <br/> <span data-ttu-id="5d24e-448">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="5d24e-448">driver license number</span></span>  <br/> <span data-ttu-id="5d24e-449">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="5d24e-449">driver licence</span></span>  <br/> <span data-ttu-id="5d24e-450">Lic de drivers.</span><span class="sxs-lookup"><span data-stu-id="5d24e-450">drivers lic.</span></span>  <br/> <span data-ttu-id="5d24e-451">drivers license</span><span class="sxs-lookup"><span data-stu-id="5d24e-451">drivers license</span></span>  <br/> <span data-ttu-id="5d24e-452">drivers licence</span><span class="sxs-lookup"><span data-stu-id="5d24e-452">drivers licence</span></span>  <br/> <span data-ttu-id="5d24e-453">driver's license</span><span class="sxs-lookup"><span data-stu-id="5d24e-453">driver's license</span></span>  <br/> <span data-ttu-id="5d24e-454">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="5d24e-454">driver's license number</span></span>  <br/> <span data-ttu-id="5d24e-455">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="5d24e-455">driver's licence number</span></span>  <br/> <span data-ttu-id="5d24e-456">número de licencia de conducir</span><span class="sxs-lookup"><span data-stu-id="5d24e-456">driving license number</span></span>  <br/> <span data-ttu-id="5d24e-457">dlno #</span><span class="sxs-lookup"><span data-stu-id="5d24e-457">dlno#</span></span>  <br/> <span data-ttu-id="5d24e-458">ceadúnas tiomána</span><span class="sxs-lookup"><span data-stu-id="5d24e-458">ceadúnas tiomána</span></span>  <br/> |
   
## <a name="italy"></a><span data-ttu-id="5d24e-459">Italia</span><span class="sxs-lookup"><span data-stu-id="5d24e-459">Italy</span></span>

<span data-ttu-id="5d24e-460">Para obtener más información, consulte la sección "número de licencia de conducción de Italia" en el [que se buscan los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="5d24e-460">For details, see the section "Italy Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="latvia"></a><span data-ttu-id="5d24e-461">Letonia</span><span class="sxs-lookup"><span data-stu-id="5d24e-461">Latvia</span></span>

### <a name="format"></a><span data-ttu-id="5d24e-462">Formato</span><span class="sxs-lookup"><span data-stu-id="5d24e-462">Format</span></span>

<span data-ttu-id="5d24e-463">Tres letras seguidas de seis dígitos</span><span class="sxs-lookup"><span data-stu-id="5d24e-463">Three letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="5d24e-464">Patrón</span><span class="sxs-lookup"><span data-stu-id="5d24e-464">Pattern</span></span>

<span data-ttu-id="5d24e-465">Tres letras y seis dígitos:</span><span class="sxs-lookup"><span data-stu-id="5d24e-465">Three letters and six digits:</span></span>
  
-  <span data-ttu-id="5d24e-466">Tres letras (sin distinción entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="5d24e-466">Three letters (not case-sensitive)</span></span> 
    
- <span data-ttu-id="5d24e-467">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="5d24e-467">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="5d24e-468">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="5d24e-468">Checksum</span></span>

<span data-ttu-id="5d24e-469">No</span><span class="sxs-lookup"><span data-stu-id="5d24e-469">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="5d24e-470">Definición</span><span class="sxs-lookup"><span data-stu-id="5d24e-470">Definition</span></span>

<span data-ttu-id="5d24e-471">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="5d24e-471">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5d24e-472">La expresión `Regex_latvia_eu_driver's_license_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="5d24e-472">The regular expression  `Regex_latvia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5d24e-473">Se encuentra una `Keywords_latvia_eu_driver's_license_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="5d24e-473">A keyword from  `Keywords_latvia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_driver's_license_number" />
          <Match idRef="Keywords_latvia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="5d24e-474">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="5d24e-474">Keywords</span></span>

<span data-ttu-id="5d24e-475">| |</span><span class="sxs-lookup"><span data-stu-id="5d24e-475"></span></span>
|<span data-ttu-id="5d24e-476">**Keywords_latvia_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="5d24e-476">**Keywords_latvia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="5d24e-477">listas</span><span class="sxs-lookup"><span data-stu-id="5d24e-477">dl#</span></span>  <br/> <span data-ttu-id="5d24e-478">driver license</span><span class="sxs-lookup"><span data-stu-id="5d24e-478">driver license</span></span>  <br/> <span data-ttu-id="5d24e-479">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="5d24e-479">driver license number</span></span>  <br/> <span data-ttu-id="5d24e-480">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="5d24e-480">driver licence</span></span>  <br/> <span data-ttu-id="5d24e-481">Lic de drivers.</span><span class="sxs-lookup"><span data-stu-id="5d24e-481">drivers lic.</span></span>  <br/> <span data-ttu-id="5d24e-482">drivers license</span><span class="sxs-lookup"><span data-stu-id="5d24e-482">drivers license</span></span>  <br/> <span data-ttu-id="5d24e-483">drivers licence</span><span class="sxs-lookup"><span data-stu-id="5d24e-483">drivers licence</span></span>  <br/> <span data-ttu-id="5d24e-484">driver's license</span><span class="sxs-lookup"><span data-stu-id="5d24e-484">driver's license</span></span>  <br/> <span data-ttu-id="5d24e-485">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="5d24e-485">driver's license number</span></span>  <br/> <span data-ttu-id="5d24e-486">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="5d24e-486">driver's licence number</span></span>  <br/> <span data-ttu-id="5d24e-487">número de licencia de conducir</span><span class="sxs-lookup"><span data-stu-id="5d24e-487">driving license number</span></span>  <br/> <span data-ttu-id="5d24e-488">dlno #</span><span class="sxs-lookup"><span data-stu-id="5d24e-488">dlno#</span></span>  <br/> <span data-ttu-id="5d24e-489">autovadītāja apliecība</span><span class="sxs-lookup"><span data-stu-id="5d24e-489">autovadītāja apliecība</span></span>  <br/> |
   
## <a name="lithuania"></a><span data-ttu-id="5d24e-490">Lituania</span><span class="sxs-lookup"><span data-stu-id="5d24e-490">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="5d24e-491">Formato</span><span class="sxs-lookup"><span data-stu-id="5d24e-491">Format</span></span>

<span data-ttu-id="5d24e-492">Ocho dígitos sin espacios y delimitadores</span><span class="sxs-lookup"><span data-stu-id="5d24e-492">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="5d24e-493">Patrón</span><span class="sxs-lookup"><span data-stu-id="5d24e-493">Pattern</span></span>

 <span data-ttu-id="5d24e-494">Ocho dígitos</span><span class="sxs-lookup"><span data-stu-id="5d24e-494">Eight digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="5d24e-495">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="5d24e-495">Checksum</span></span>

<span data-ttu-id="5d24e-496">No</span><span class="sxs-lookup"><span data-stu-id="5d24e-496">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="5d24e-497">Definición</span><span class="sxs-lookup"><span data-stu-id="5d24e-497">Definition</span></span>

<span data-ttu-id="5d24e-498">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="5d24e-498">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5d24e-499">La expresión `Regex_lithuania_eu_driver's_license_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="5d24e-499">The regular expression  `Regex_lithuania_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5d24e-500">Se encuentra una `Keywords_lithuania_eu_driver's_license_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="5d24e-500">A keyword from  `Keywords_lithuania_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_driver's_license_number" />
          <Match idRef="Keywords_lithuania_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="5d24e-501">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="5d24e-501">Keywords</span></span>

<span data-ttu-id="5d24e-502">| |</span><span class="sxs-lookup"><span data-stu-id="5d24e-502"></span></span>
|<span data-ttu-id="5d24e-503">**Keywords_lithuania_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="5d24e-503">**Keywords_lithuania_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="5d24e-504">listas</span><span class="sxs-lookup"><span data-stu-id="5d24e-504">dl#</span></span>  <br/> <span data-ttu-id="5d24e-505">driver license</span><span class="sxs-lookup"><span data-stu-id="5d24e-505">driver license</span></span>  <br/> <span data-ttu-id="5d24e-506">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="5d24e-506">driver license number</span></span>  <br/> <span data-ttu-id="5d24e-507">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="5d24e-507">driver licence</span></span>  <br/> <span data-ttu-id="5d24e-508">Lic de drivers.</span><span class="sxs-lookup"><span data-stu-id="5d24e-508">drivers lic.</span></span>  <br/> <span data-ttu-id="5d24e-509">drivers license</span><span class="sxs-lookup"><span data-stu-id="5d24e-509">drivers license</span></span>  <br/> <span data-ttu-id="5d24e-510">drivers licence</span><span class="sxs-lookup"><span data-stu-id="5d24e-510">drivers licence</span></span>  <br/> <span data-ttu-id="5d24e-511">driver's license</span><span class="sxs-lookup"><span data-stu-id="5d24e-511">driver's license</span></span>  <br/> <span data-ttu-id="5d24e-512">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="5d24e-512">driver's license number</span></span>  <br/> <span data-ttu-id="5d24e-513">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="5d24e-513">driver's licence number</span></span>  <br/> <span data-ttu-id="5d24e-514">número de licencia de conducir</span><span class="sxs-lookup"><span data-stu-id="5d24e-514">driving license number</span></span>  <br/> <span data-ttu-id="5d24e-515">dlno #</span><span class="sxs-lookup"><span data-stu-id="5d24e-515">dlno#</span></span>  <br/> <span data-ttu-id="5d24e-516">vairuotojo pažymėjimas</span><span class="sxs-lookup"><span data-stu-id="5d24e-516">vairuotojo pažymėjimas</span></span>  <br/> |
   
## <a name="luxemburg"></a><span data-ttu-id="5d24e-517">Luxemburgo</span><span class="sxs-lookup"><span data-stu-id="5d24e-517">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="5d24e-518">Formato</span><span class="sxs-lookup"><span data-stu-id="5d24e-518">Format</span></span>

<span data-ttu-id="5d24e-519">Seis dígitos sin espacios y delimitadores</span><span class="sxs-lookup"><span data-stu-id="5d24e-519">Six digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="5d24e-520">Patrón</span><span class="sxs-lookup"><span data-stu-id="5d24e-520">Pattern</span></span>

 <span data-ttu-id="5d24e-521">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="5d24e-521">Six digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="5d24e-522">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="5d24e-522">Checksum</span></span>

<span data-ttu-id="5d24e-523">No</span><span class="sxs-lookup"><span data-stu-id="5d24e-523">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="5d24e-524">Definición</span><span class="sxs-lookup"><span data-stu-id="5d24e-524">Definition</span></span>

<span data-ttu-id="5d24e-525">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="5d24e-525">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5d24e-526">La expresión `Regex_luxemburg_eu_driver's_license_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="5d24e-526">The regular expression  `Regex_luxemburg_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5d24e-527">Se encuentra una `Keywords_luxemburg_eu_driver's_license_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="5d24e-527">A keyword from  `Keywords_luxemburg_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_luxemburg_eu_driver's_license_number" />
          <Match idRef="Keywords_luxemburg_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="5d24e-528">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="5d24e-528">Keywords</span></span>

<span data-ttu-id="5d24e-529">| |</span><span class="sxs-lookup"><span data-stu-id="5d24e-529"></span></span>
|<span data-ttu-id="5d24e-530">**Keywords_luxemburg_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="5d24e-530">**Keywords_luxemburg_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="5d24e-531">listas</span><span class="sxs-lookup"><span data-stu-id="5d24e-531">dl#</span></span>  <br/> <span data-ttu-id="5d24e-532">driver license</span><span class="sxs-lookup"><span data-stu-id="5d24e-532">driver license</span></span>  <br/> <span data-ttu-id="5d24e-533">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="5d24e-533">driver license number</span></span>  <br/> <span data-ttu-id="5d24e-534">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="5d24e-534">driver licence</span></span>  <br/> <span data-ttu-id="5d24e-535">Lic de drivers.</span><span class="sxs-lookup"><span data-stu-id="5d24e-535">drivers lic.</span></span>  <br/> <span data-ttu-id="5d24e-536">drivers license</span><span class="sxs-lookup"><span data-stu-id="5d24e-536">drivers license</span></span>  <br/> <span data-ttu-id="5d24e-537">drivers licence</span><span class="sxs-lookup"><span data-stu-id="5d24e-537">drivers licence</span></span>  <br/> <span data-ttu-id="5d24e-538">driver's license</span><span class="sxs-lookup"><span data-stu-id="5d24e-538">driver's license</span></span>  <br/> <span data-ttu-id="5d24e-539">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="5d24e-539">driver's license number</span></span>  <br/> <span data-ttu-id="5d24e-540">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="5d24e-540">driver's licence number</span></span>  <br/> <span data-ttu-id="5d24e-541">número de licencia de conducir</span><span class="sxs-lookup"><span data-stu-id="5d24e-541">driving license number</span></span>  <br/> <span data-ttu-id="5d24e-542">dlno #</span><span class="sxs-lookup"><span data-stu-id="5d24e-542">dlno#</span></span>  <br/> <span data-ttu-id="5d24e-543">fahrerlaubnis</span><span class="sxs-lookup"><span data-stu-id="5d24e-543">fahrerlaubnis</span></span>  <br/> |
   
## <a name="malta"></a><span data-ttu-id="5d24e-544">Malta</span><span class="sxs-lookup"><span data-stu-id="5d24e-544">Malta</span></span>

### <a name="format"></a><span data-ttu-id="5d24e-545">Formato</span><span class="sxs-lookup"><span data-stu-id="5d24e-545">Format</span></span>

<span data-ttu-id="5d24e-546">Combinación de dos caracteres y seis dígitos en el patrón especificado</span><span class="sxs-lookup"><span data-stu-id="5d24e-546">Combination of two characters and six digits in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="5d24e-547">Patrón</span><span class="sxs-lookup"><span data-stu-id="5d24e-547">Pattern</span></span>

<span data-ttu-id="5d24e-548">Combinación de dos caracteres y seis dígitos:</span><span class="sxs-lookup"><span data-stu-id="5d24e-548">Combination of two characters and six digits:</span></span>
  
- <span data-ttu-id="5d24e-549">Dos caracteres (dígitos o letras, no distinguen entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="5d24e-549">Two characters (digits or letters, not case-sensitive)</span></span>
    
- <span data-ttu-id="5d24e-550">Un espacio (opcional) </span><span class="sxs-lookup"><span data-stu-id="5d24e-550">A space (optional)</span></span>
    
- <span data-ttu-id="5d24e-551">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="5d24e-551">Three digits</span></span>
    
- <span data-ttu-id="5d24e-552">Un espacio (opcional) </span><span class="sxs-lookup"><span data-stu-id="5d24e-552">A space (optional)</span></span>
    
- <span data-ttu-id="5d24e-553">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="5d24e-553">Three digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="5d24e-554">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="5d24e-554">Checksum</span></span>

<span data-ttu-id="5d24e-555">No</span><span class="sxs-lookup"><span data-stu-id="5d24e-555">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="5d24e-556">Definición</span><span class="sxs-lookup"><span data-stu-id="5d24e-556">Definition</span></span>

<span data-ttu-id="5d24e-557">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="5d24e-557">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5d24e-558">La expresión `Regex_malta_eu_driver's_license_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="5d24e-558">The regular expression  `Regex_malta_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5d24e-559">Se encuentra una `Keywords_malta_eu_driver's_license_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="5d24e-559">A keyword from  `Keywords_malta_eu_driver's_license_number` is found.</span></span> 
    
```
<!-- EU Driver's License Number -->
 <Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_driver's_license_number" />
          <Match idRef="Keywords_malta_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="5d24e-560">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="5d24e-560">Keywords</span></span>

<span data-ttu-id="5d24e-561">| |</span><span class="sxs-lookup"><span data-stu-id="5d24e-561"></span></span>
|<span data-ttu-id="5d24e-562">**Keywords_malta_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="5d24e-562">**Keywords_malta_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="5d24e-563">listas</span><span class="sxs-lookup"><span data-stu-id="5d24e-563">dl#</span></span>  <br/> <span data-ttu-id="5d24e-564">driver license</span><span class="sxs-lookup"><span data-stu-id="5d24e-564">driver license</span></span>  <br/> <span data-ttu-id="5d24e-565">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="5d24e-565">driver license number</span></span>  <br/> <span data-ttu-id="5d24e-566">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="5d24e-566">driver licence</span></span>  <br/> <span data-ttu-id="5d24e-567">Lic de drivers.</span><span class="sxs-lookup"><span data-stu-id="5d24e-567">drivers lic.</span></span>  <br/> <span data-ttu-id="5d24e-568">drivers license</span><span class="sxs-lookup"><span data-stu-id="5d24e-568">drivers license</span></span>  <br/> <span data-ttu-id="5d24e-569">drivers licence</span><span class="sxs-lookup"><span data-stu-id="5d24e-569">drivers licence</span></span>  <br/> <span data-ttu-id="5d24e-570">driver's license</span><span class="sxs-lookup"><span data-stu-id="5d24e-570">driver's license</span></span>  <br/> <span data-ttu-id="5d24e-571">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="5d24e-571">driver's license number</span></span>  <br/> <span data-ttu-id="5d24e-572">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="5d24e-572">driver's licence number</span></span>  <br/> <span data-ttu-id="5d24e-573">número de licencia de conducir</span><span class="sxs-lookup"><span data-stu-id="5d24e-573">driving license number</span></span>  <br/> <span data-ttu-id="5d24e-574">dlno #</span><span class="sxs-lookup"><span data-stu-id="5d24e-574">dlno#</span></span>  <br/> <span data-ttu-id="5d24e-575">liċenzja sewqan</span><span class="sxs-lookup"><span data-stu-id="5d24e-575">liċenzja tas-sewqan</span></span>  <br/> |
   
## <a name="netherlands"></a><span data-ttu-id="5d24e-576">Países Bajos</span><span class="sxs-lookup"><span data-stu-id="5d24e-576">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="5d24e-577">Formato</span><span class="sxs-lookup"><span data-stu-id="5d24e-577">Format</span></span>

<span data-ttu-id="5d24e-578">10 dígitos sin espacios y delimitadores</span><span class="sxs-lookup"><span data-stu-id="5d24e-578">10 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="5d24e-579">Patrón</span><span class="sxs-lookup"><span data-stu-id="5d24e-579">Pattern</span></span>

<span data-ttu-id="5d24e-580">10 dígitos</span><span class="sxs-lookup"><span data-stu-id="5d24e-580">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="5d24e-581">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="5d24e-581">Checksum</span></span>

<span data-ttu-id="5d24e-582">No</span><span class="sxs-lookup"><span data-stu-id="5d24e-582">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="5d24e-583">Definición</span><span class="sxs-lookup"><span data-stu-id="5d24e-583">Definition</span></span>

<span data-ttu-id="5d24e-584">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="5d24e-584">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5d24e-585">La expresión `Regex_netherlands_eu_driver's_license_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="5d24e-585">The regular expression  `Regex_netherlands_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5d24e-586">Se encuentra una `Keywords_netherlands_eu_driver's_license_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="5d24e-586">A keyword from  `Keywords_netherlands_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_driver's_license_number" />
          <Match idRef="Keywords_netherlands_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="5d24e-587">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="5d24e-587">Keywords</span></span>

<span data-ttu-id="5d24e-588">| |</span><span class="sxs-lookup"><span data-stu-id="5d24e-588"></span></span>
|<span data-ttu-id="5d24e-589">**Keywords_netherlands_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="5d24e-589">**Keywords_netherlands_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="5d24e-590">listas</span><span class="sxs-lookup"><span data-stu-id="5d24e-590">dl#</span></span>  <br/> <span data-ttu-id="5d24e-591">driver license</span><span class="sxs-lookup"><span data-stu-id="5d24e-591">driver license</span></span>  <br/> <span data-ttu-id="5d24e-592">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="5d24e-592">driver license number</span></span>  <br/> <span data-ttu-id="5d24e-593">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="5d24e-593">driver licence</span></span>  <br/> <span data-ttu-id="5d24e-594">Lic de drivers.</span><span class="sxs-lookup"><span data-stu-id="5d24e-594">drivers lic.</span></span>  <br/> <span data-ttu-id="5d24e-595">drivers license</span><span class="sxs-lookup"><span data-stu-id="5d24e-595">drivers license</span></span>  <br/> <span data-ttu-id="5d24e-596">drivers licence</span><span class="sxs-lookup"><span data-stu-id="5d24e-596">drivers licence</span></span>  <br/> <span data-ttu-id="5d24e-597">driver's license</span><span class="sxs-lookup"><span data-stu-id="5d24e-597">driver's license</span></span>  <br/> <span data-ttu-id="5d24e-598">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="5d24e-598">driver's license number</span></span>  <br/> <span data-ttu-id="5d24e-599">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="5d24e-599">driver's licence number</span></span>  <br/> <span data-ttu-id="5d24e-600">número de licencia de conducir</span><span class="sxs-lookup"><span data-stu-id="5d24e-600">driving license number</span></span>  <br/> <span data-ttu-id="5d24e-601">dlno #</span><span class="sxs-lookup"><span data-stu-id="5d24e-601">dlno#</span></span>  <br/> <span data-ttu-id="5d24e-602">permis de conduire</span><span class="sxs-lookup"><span data-stu-id="5d24e-602">permis de conduire</span></span>  <br/> <span data-ttu-id="5d24e-603">rijbewijs</span><span class="sxs-lookup"><span data-stu-id="5d24e-603">rijbewijs</span></span>  <br/> <span data-ttu-id="5d24e-604">rijbewijsnummer</span><span class="sxs-lookup"><span data-stu-id="5d24e-604">rijbewijsnummer</span></span>  <br/> |
   
## <a name="poland"></a><span data-ttu-id="5d24e-605">Polonia</span><span class="sxs-lookup"><span data-stu-id="5d24e-605">Poland</span></span>

### <a name="format"></a><span data-ttu-id="5d24e-606">Formato</span><span class="sxs-lookup"><span data-stu-id="5d24e-606">Format</span></span>

<span data-ttu-id="5d24e-607">14 dígitos que contienen 2 barras diagonales</span><span class="sxs-lookup"><span data-stu-id="5d24e-607">14 digits containing 2 forward slashes</span></span>
  
### <a name="pattern"></a><span data-ttu-id="5d24e-608">Patrón</span><span class="sxs-lookup"><span data-stu-id="5d24e-608">Pattern</span></span>

<span data-ttu-id="5d24e-609">14 dígitos y 2 barras diagonales:</span><span class="sxs-lookup"><span data-stu-id="5d24e-609">14 digits and 2 forward slashes:</span></span>
  
-  <span data-ttu-id="5d24e-610">Cinco dígitos</span><span class="sxs-lookup"><span data-stu-id="5d24e-610">Five digits</span></span> 
    
- <span data-ttu-id="5d24e-611">Una barra diagonal </span><span class="sxs-lookup"><span data-stu-id="5d24e-611">A forward slash</span></span>
    
- <span data-ttu-id="5d24e-612">Dos dígitos</span><span class="sxs-lookup"><span data-stu-id="5d24e-612">Two digits</span></span>
    
- <span data-ttu-id="5d24e-613">Una barra diagonal </span><span class="sxs-lookup"><span data-stu-id="5d24e-613">A forward slash</span></span>
    
- <span data-ttu-id="5d24e-614">Siete dígitos</span><span class="sxs-lookup"><span data-stu-id="5d24e-614">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="5d24e-615">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="5d24e-615">Checksum</span></span>

<span data-ttu-id="5d24e-616">No</span><span class="sxs-lookup"><span data-stu-id="5d24e-616">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="5d24e-617">Definición</span><span class="sxs-lookup"><span data-stu-id="5d24e-617">Definition</span></span>

<span data-ttu-id="5d24e-618">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="5d24e-618">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5d24e-619">La expresión `Regex_poland_eu_driver's_license_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="5d24e-619">The regular expression  `Regex_poland_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5d24e-620">Se encuentra una `Keywords_poland_eu_driver's_license_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="5d24e-620">A keyword from  `Keywords_poland_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_poland_eu_driver's_license_number" />
          <Match idRef="Keywords_poland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="5d24e-621">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="5d24e-621">Keywords</span></span>

<span data-ttu-id="5d24e-622">| |</span><span class="sxs-lookup"><span data-stu-id="5d24e-622"></span></span>
|<span data-ttu-id="5d24e-623">**Keywords_poland_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="5d24e-623">**Keywords_poland_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="5d24e-624">listas</span><span class="sxs-lookup"><span data-stu-id="5d24e-624">dl#</span></span>  <br/> <span data-ttu-id="5d24e-625">driver license</span><span class="sxs-lookup"><span data-stu-id="5d24e-625">driver license</span></span>  <br/> <span data-ttu-id="5d24e-626">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="5d24e-626">driver license number</span></span>  <br/> <span data-ttu-id="5d24e-627">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="5d24e-627">driver licence</span></span>  <br/> <span data-ttu-id="5d24e-628">Lic de drivers.</span><span class="sxs-lookup"><span data-stu-id="5d24e-628">drivers lic.</span></span>  <br/> <span data-ttu-id="5d24e-629">drivers license</span><span class="sxs-lookup"><span data-stu-id="5d24e-629">drivers license</span></span>  <br/> <span data-ttu-id="5d24e-630">drivers licence</span><span class="sxs-lookup"><span data-stu-id="5d24e-630">drivers licence</span></span>  <br/> <span data-ttu-id="5d24e-631">driver's license</span><span class="sxs-lookup"><span data-stu-id="5d24e-631">driver's license</span></span>  <br/> <span data-ttu-id="5d24e-632">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="5d24e-632">driver's license number</span></span>  <br/> <span data-ttu-id="5d24e-633">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="5d24e-633">driver's licence number</span></span>  <br/> <span data-ttu-id="5d24e-634">número de licencia de conducir</span><span class="sxs-lookup"><span data-stu-id="5d24e-634">driving license number</span></span>  <br/> <span data-ttu-id="5d24e-635">dlno #</span><span class="sxs-lookup"><span data-stu-id="5d24e-635">dlno#</span></span>  <br/> <span data-ttu-id="5d24e-636">Prawo jazdy</span><span class="sxs-lookup"><span data-stu-id="5d24e-636">prawo jazdy</span></span>  <br/> |
   
## <a name="portugal"></a><span data-ttu-id="5d24e-637">Portugal</span><span class="sxs-lookup"><span data-stu-id="5d24e-637">Portugal</span></span>

### <a name="format"></a><span data-ttu-id="5d24e-638">Formato</span><span class="sxs-lookup"><span data-stu-id="5d24e-638">Format</span></span>

<span data-ttu-id="5d24e-639">Dos letras seguidas de siete números en el patrón especificado</span><span class="sxs-lookup"><span data-stu-id="5d24e-639">Two letters followed by a seven numbers in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="5d24e-640">Patrón</span><span class="sxs-lookup"><span data-stu-id="5d24e-640">Pattern</span></span>

<span data-ttu-id="5d24e-641">Dos letras seguidas de siete números con caracteres especiales:</span><span class="sxs-lookup"><span data-stu-id="5d24e-641">Two letters followed by seven numbers with special characters:</span></span>
  
-  <span data-ttu-id="5d24e-642">Dos letras (sin distinción entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="5d24e-642">Two letters (not case-sensitive)</span></span> 
    
- <span data-ttu-id="5d24e-643">Un guión </span><span class="sxs-lookup"><span data-stu-id="5d24e-643">A hyphen</span></span>
    
- <span data-ttu-id="5d24e-644">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="5d24e-644">Six digits</span></span>
    
- <span data-ttu-id="5d24e-645">Un espacio</span><span class="sxs-lookup"><span data-stu-id="5d24e-645">A space</span></span>
    
- <span data-ttu-id="5d24e-646">Un dígito</span><span class="sxs-lookup"><span data-stu-id="5d24e-646">One digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="5d24e-647">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="5d24e-647">Checksum</span></span>

<span data-ttu-id="5d24e-648">No</span><span class="sxs-lookup"><span data-stu-id="5d24e-648">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="5d24e-649">Definición</span><span class="sxs-lookup"><span data-stu-id="5d24e-649">Definition</span></span>

<span data-ttu-id="5d24e-650">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="5d24e-650">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5d24e-651">La expresión `Regex_portugal_eu_driver's_license_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="5d24e-651">The regular expression  `Regex_portugal_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5d24e-652">Se encuentra una `Keywords_portugal_eu_driver's_license_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="5d24e-652">A keyword from  `Keywords_portugal_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_driver's_license_number" />
          <Match idRef="Keywords_portugal_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="5d24e-653">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="5d24e-653">Keywords</span></span>

<span data-ttu-id="5d24e-654">| |</span><span class="sxs-lookup"><span data-stu-id="5d24e-654"></span></span>
|<span data-ttu-id="5d24e-655">**Keywords_portugal_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="5d24e-655">**Keywords_portugal_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="5d24e-656">listas</span><span class="sxs-lookup"><span data-stu-id="5d24e-656">dl#</span></span>  <br/> <span data-ttu-id="5d24e-657">driver license</span><span class="sxs-lookup"><span data-stu-id="5d24e-657">driver license</span></span>  <br/> <span data-ttu-id="5d24e-658">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="5d24e-658">driver license number</span></span>  <br/> <span data-ttu-id="5d24e-659">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="5d24e-659">driver licence</span></span>  <br/> <span data-ttu-id="5d24e-660">Lic de drivers.</span><span class="sxs-lookup"><span data-stu-id="5d24e-660">drivers lic.</span></span>  <br/> <span data-ttu-id="5d24e-661">drivers license</span><span class="sxs-lookup"><span data-stu-id="5d24e-661">drivers license</span></span>  <br/> <span data-ttu-id="5d24e-662">drivers licence</span><span class="sxs-lookup"><span data-stu-id="5d24e-662">drivers licence</span></span>  <br/> <span data-ttu-id="5d24e-663">driver's license</span><span class="sxs-lookup"><span data-stu-id="5d24e-663">driver's license</span></span>  <br/> <span data-ttu-id="5d24e-664">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="5d24e-664">driver's license number</span></span>  <br/> <span data-ttu-id="5d24e-665">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="5d24e-665">driver's licence number</span></span>  <br/> <span data-ttu-id="5d24e-666">número de licencia de conducir</span><span class="sxs-lookup"><span data-stu-id="5d24e-666">driving license number</span></span>  <br/> <span data-ttu-id="5d24e-667">dlno #</span><span class="sxs-lookup"><span data-stu-id="5d24e-667">dlno#</span></span>  <br/> <span data-ttu-id="5d24e-668">Carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="5d24e-668">carteira de motorista</span></span>  <br/> |
   
## <a name="romania"></a><span data-ttu-id="5d24e-669">Rumania</span><span class="sxs-lookup"><span data-stu-id="5d24e-669">Romania</span></span>

### <a name="format"></a><span data-ttu-id="5d24e-670">Formato</span><span class="sxs-lookup"><span data-stu-id="5d24e-670">Format</span></span>

<span data-ttu-id="5d24e-671">Un carácter seguido de ocho dígitos</span><span class="sxs-lookup"><span data-stu-id="5d24e-671">One character followed by eight digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="5d24e-672">Patrón</span><span class="sxs-lookup"><span data-stu-id="5d24e-672">Pattern</span></span>

<span data-ttu-id="5d24e-673">Un carácter seguido de ocho dígitos:</span><span class="sxs-lookup"><span data-stu-id="5d24e-673">One character followed by eight digits:</span></span>
  
-  <span data-ttu-id="5d24e-674">Una letra (no distingue entre mayúsculas y minúsculas) o un dígito</span><span class="sxs-lookup"><span data-stu-id="5d24e-674">One letter (not case-sensitive) or digit</span></span> 
    
- <span data-ttu-id="5d24e-675">Ocho dígitos</span><span class="sxs-lookup"><span data-stu-id="5d24e-675">Eight digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="5d24e-676">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="5d24e-676">Checksum</span></span>

<span data-ttu-id="5d24e-677">No</span><span class="sxs-lookup"><span data-stu-id="5d24e-677">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="5d24e-678">Definición</span><span class="sxs-lookup"><span data-stu-id="5d24e-678">Definition</span></span>

<span data-ttu-id="5d24e-679">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="5d24e-679">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5d24e-680">La expresión `Regex_romania_eu_driver's_license_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="5d24e-680">The regular expression  `Regex_romania_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5d24e-681">Se encuentra una `Keywords_romania_eu_driver's_license_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="5d24e-681">A keyword from  `Keywords_romania_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_driver's_license_number" />
          <Match idRef="Keywords_romania_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="5d24e-682">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="5d24e-682">Keywords</span></span>

<span data-ttu-id="5d24e-683">| |</span><span class="sxs-lookup"><span data-stu-id="5d24e-683"></span></span>
|<span data-ttu-id="5d24e-684">**Keywords_romania_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="5d24e-684">**Keywords_romania_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="5d24e-685">listas</span><span class="sxs-lookup"><span data-stu-id="5d24e-685">dl#</span></span>  <br/> <span data-ttu-id="5d24e-686">driver license</span><span class="sxs-lookup"><span data-stu-id="5d24e-686">driver license</span></span>  <br/> <span data-ttu-id="5d24e-687">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="5d24e-687">driver license number</span></span>  <br/> <span data-ttu-id="5d24e-688">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="5d24e-688">driver licence</span></span>  <br/> <span data-ttu-id="5d24e-689">Lic de drivers.</span><span class="sxs-lookup"><span data-stu-id="5d24e-689">drivers lic.</span></span>  <br/> <span data-ttu-id="5d24e-690">drivers license</span><span class="sxs-lookup"><span data-stu-id="5d24e-690">drivers license</span></span>  <br/> <span data-ttu-id="5d24e-691">drivers licence</span><span class="sxs-lookup"><span data-stu-id="5d24e-691">drivers licence</span></span>  <br/> <span data-ttu-id="5d24e-692">driver's license</span><span class="sxs-lookup"><span data-stu-id="5d24e-692">driver's license</span></span>  <br/> <span data-ttu-id="5d24e-693">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="5d24e-693">driver's license number</span></span>  <br/> <span data-ttu-id="5d24e-694">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="5d24e-694">driver's licence number</span></span>  <br/> <span data-ttu-id="5d24e-695">número de licencia de conducir</span><span class="sxs-lookup"><span data-stu-id="5d24e-695">driving license number</span></span>  <br/> <span data-ttu-id="5d24e-696">dlno #</span><span class="sxs-lookup"><span data-stu-id="5d24e-696">dlno#</span></span>  <br/> <span data-ttu-id="5d24e-697">Perm de conducere</span><span class="sxs-lookup"><span data-stu-id="5d24e-697">permis de conducere</span></span>  <br/> |
   
## <a name="slovakia"></a><span data-ttu-id="5d24e-698">Eslovaquia</span><span class="sxs-lookup"><span data-stu-id="5d24e-698">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="5d24e-699">Formato</span><span class="sxs-lookup"><span data-stu-id="5d24e-699">Format</span></span>

<span data-ttu-id="5d24e-700">Un carácter seguido de siete dígitos</span><span class="sxs-lookup"><span data-stu-id="5d24e-700">One character followed by seven digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="5d24e-701">Patrón</span><span class="sxs-lookup"><span data-stu-id="5d24e-701">Pattern</span></span>

<span data-ttu-id="5d24e-702">Un carácter seguido de siete dígitos</span><span class="sxs-lookup"><span data-stu-id="5d24e-702">One character followed by seven digits</span></span>
  
- <span data-ttu-id="5d24e-703">Una letra (no distingue entre mayúsculas y minúsculas) o un dígito</span><span class="sxs-lookup"><span data-stu-id="5d24e-703">One letter (not case-sensitive) or digit</span></span>
    
-  <span data-ttu-id="5d24e-704">Siete dígitos</span><span class="sxs-lookup"><span data-stu-id="5d24e-704">Seven digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="5d24e-705">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="5d24e-705">Checksum</span></span>

<span data-ttu-id="5d24e-706">No</span><span class="sxs-lookup"><span data-stu-id="5d24e-706">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="5d24e-707">Definición</span><span class="sxs-lookup"><span data-stu-id="5d24e-707">Definition</span></span>

<span data-ttu-id="5d24e-708">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="5d24e-708">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5d24e-709">La expresión `Regex_slovakia_eu_driver's_license_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="5d24e-709">The regular expression  `Regex_slovakia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5d24e-710">Se encuentra una `Keywords_slovakia_eu_driver's_license_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="5d24e-710">A keyword from  `Keywords_slovakia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovaknia_eu_driver's_license_number" />
          <Match idRef="Keywords_slovakia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="5d24e-711">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="5d24e-711">Keywords</span></span>

<span data-ttu-id="5d24e-712">| |</span><span class="sxs-lookup"><span data-stu-id="5d24e-712"></span></span>
|<span data-ttu-id="5d24e-713">**Keywords_slovakia_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="5d24e-713">**Keywords_slovakia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="5d24e-714">listas</span><span class="sxs-lookup"><span data-stu-id="5d24e-714">dl#</span></span>  <br/> <span data-ttu-id="5d24e-715">driver license</span><span class="sxs-lookup"><span data-stu-id="5d24e-715">driver license</span></span>  <br/> <span data-ttu-id="5d24e-716">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="5d24e-716">driver license number</span></span>  <br/> <span data-ttu-id="5d24e-717">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="5d24e-717">driver licence</span></span>  <br/> <span data-ttu-id="5d24e-718">Lic de drivers.</span><span class="sxs-lookup"><span data-stu-id="5d24e-718">drivers lic.</span></span>  <br/> <span data-ttu-id="5d24e-719">drivers license</span><span class="sxs-lookup"><span data-stu-id="5d24e-719">drivers license</span></span>  <br/> <span data-ttu-id="5d24e-720">drivers licence</span><span class="sxs-lookup"><span data-stu-id="5d24e-720">drivers licence</span></span>  <br/> <span data-ttu-id="5d24e-721">driver's license</span><span class="sxs-lookup"><span data-stu-id="5d24e-721">driver's license</span></span>  <br/> <span data-ttu-id="5d24e-722">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="5d24e-722">driver's license number</span></span>  <br/> <span data-ttu-id="5d24e-723">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="5d24e-723">driver's licence number</span></span>  <br/> <span data-ttu-id="5d24e-724">número de licencia de conducir</span><span class="sxs-lookup"><span data-stu-id="5d24e-724">driving license number</span></span>  <br/> <span data-ttu-id="5d24e-725">dlno #</span><span class="sxs-lookup"><span data-stu-id="5d24e-725">dlno#</span></span>  <br/> <span data-ttu-id="5d24e-726">vodičský preukaz</span><span class="sxs-lookup"><span data-stu-id="5d24e-726">vodičský preukaz</span></span>  <br/> |
   
## <a name="slovenia"></a><span data-ttu-id="5d24e-727">Eslovenia</span><span class="sxs-lookup"><span data-stu-id="5d24e-727">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="5d24e-728">Formato</span><span class="sxs-lookup"><span data-stu-id="5d24e-728">Format</span></span>

<span data-ttu-id="5d24e-729">Nueve dígitos sin espacios y delimitadores</span><span class="sxs-lookup"><span data-stu-id="5d24e-729">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="5d24e-730">Patrón</span><span class="sxs-lookup"><span data-stu-id="5d24e-730">Pattern</span></span>

<span data-ttu-id="5d24e-731">Nueve dígitos</span><span class="sxs-lookup"><span data-stu-id="5d24e-731">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="5d24e-732">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="5d24e-732">Checksum</span></span>

<span data-ttu-id="5d24e-733">No</span><span class="sxs-lookup"><span data-stu-id="5d24e-733">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="5d24e-734">Definición</span><span class="sxs-lookup"><span data-stu-id="5d24e-734">Definition</span></span>

<span data-ttu-id="5d24e-735">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="5d24e-735">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5d24e-736">La expresión `Regex_slovenia_eu_driver's_license_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="5d24e-736">The regular expression  `Regex_slovenia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5d24e-737">Se encuentra una `Keywords_slovenia_eu_driver's_license_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="5d24e-737">A keyword from  `Keywords_slovenia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_driver's_license_number" />
          <Match idRef="Keywords_slovenia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="5d24e-738">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="5d24e-738">Keywords</span></span>

<span data-ttu-id="5d24e-739">| |</span><span class="sxs-lookup"><span data-stu-id="5d24e-739"></span></span>
|<span data-ttu-id="5d24e-740">**Keywords_slovenia_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="5d24e-740">**Keywords_slovenia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="5d24e-741">listas</span><span class="sxs-lookup"><span data-stu-id="5d24e-741">dl#</span></span>  <br/> <span data-ttu-id="5d24e-742">driver license</span><span class="sxs-lookup"><span data-stu-id="5d24e-742">driver license</span></span>  <br/> <span data-ttu-id="5d24e-743">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="5d24e-743">driver license number</span></span>  <br/> <span data-ttu-id="5d24e-744">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="5d24e-744">driver licence</span></span>  <br/> <span data-ttu-id="5d24e-745">Lic de drivers.</span><span class="sxs-lookup"><span data-stu-id="5d24e-745">drivers lic.</span></span>  <br/> <span data-ttu-id="5d24e-746">drivers license</span><span class="sxs-lookup"><span data-stu-id="5d24e-746">drivers license</span></span>  <br/> <span data-ttu-id="5d24e-747">drivers licence</span><span class="sxs-lookup"><span data-stu-id="5d24e-747">drivers licence</span></span>  <br/> <span data-ttu-id="5d24e-748">driver's license</span><span class="sxs-lookup"><span data-stu-id="5d24e-748">driver's license</span></span>  <br/> <span data-ttu-id="5d24e-749">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="5d24e-749">driver's license number</span></span>  <br/> <span data-ttu-id="5d24e-750">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="5d24e-750">driver's licence number</span></span>  <br/> <span data-ttu-id="5d24e-751">número de licencia de conducir</span><span class="sxs-lookup"><span data-stu-id="5d24e-751">driving license number</span></span>  <br/> <span data-ttu-id="5d24e-752">dlno #</span><span class="sxs-lookup"><span data-stu-id="5d24e-752">dlno#</span></span>  <br/> <span data-ttu-id="5d24e-753">vozniško dovoljenje</span><span class="sxs-lookup"><span data-stu-id="5d24e-753">vozniško dovoljenje</span></span>  <br/> |
   
## <a name="spain"></a><span data-ttu-id="5d24e-754">España</span><span class="sxs-lookup"><span data-stu-id="5d24e-754">Spain</span></span>

### <a name="format"></a><span data-ttu-id="5d24e-755">Formato</span><span class="sxs-lookup"><span data-stu-id="5d24e-755">Format</span></span>

<span data-ttu-id="5d24e-756">Ocho dígitos seguidos de un carácter</span><span class="sxs-lookup"><span data-stu-id="5d24e-756">Eight digits followed by one character</span></span>
  
### <a name="pattern"></a><span data-ttu-id="5d24e-757">Patrón</span><span class="sxs-lookup"><span data-stu-id="5d24e-757">Pattern</span></span>

<span data-ttu-id="5d24e-758">Ocho dígitos seguidos de un carácter:</span><span class="sxs-lookup"><span data-stu-id="5d24e-758">Eight digits followed by one character:</span></span>
  
-  <span data-ttu-id="5d24e-759">Ocho dígitos</span><span class="sxs-lookup"><span data-stu-id="5d24e-759">Eight digits</span></span> 
    
- <span data-ttu-id="5d24e-760">Un dígito o letra (no distingue entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="5d24e-760">One digit or letter (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="5d24e-761">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="5d24e-761">Checksum</span></span>

<span data-ttu-id="5d24e-762">Sí</span><span class="sxs-lookup"><span data-stu-id="5d24e-762">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="5d24e-763">Definición</span><span class="sxs-lookup"><span data-stu-id="5d24e-763">Definition</span></span>

<span data-ttu-id="5d24e-764">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="5d24e-764">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5d24e-765">La función `Func_spain_eu_driver's_license_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="5d24e-765">The function  `Func_spain_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5d24e-766">Se encuentra una `Keywords_spain_eu_driver's_license_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="5d24e-766">A keyword from  `Keywords_spain_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spain_eu_driver's_license_number" />
          <Match idRef="Keywords_spain_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="5d24e-767">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="5d24e-767">Keywords</span></span>

<span data-ttu-id="5d24e-768">| |</span><span class="sxs-lookup"><span data-stu-id="5d24e-768"></span></span>
|<span data-ttu-id="5d24e-769">**Keywords_spain_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="5d24e-769">**Keywords_spain_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="5d24e-770">dlno #</span><span class="sxs-lookup"><span data-stu-id="5d24e-770">dlno#</span></span>  <br/> <span data-ttu-id="5d24e-771">listas</span><span class="sxs-lookup"><span data-stu-id="5d24e-771">dl#</span></span>  <br/> <span data-ttu-id="5d24e-772">Lic de drivers.</span><span class="sxs-lookup"><span data-stu-id="5d24e-772">drivers lic.</span></span>  <br/> <span data-ttu-id="5d24e-773">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="5d24e-773">driver licence</span></span>  <br/> <span data-ttu-id="5d24e-774">driver license</span><span class="sxs-lookup"><span data-stu-id="5d24e-774">driver license</span></span>  <br/> <span data-ttu-id="5d24e-775">drivers licence</span><span class="sxs-lookup"><span data-stu-id="5d24e-775">drivers licence</span></span>  <br/> <span data-ttu-id="5d24e-776">drivers license</span><span class="sxs-lookup"><span data-stu-id="5d24e-776">drivers license</span></span>  <br/> <span data-ttu-id="5d24e-777">driver's licence</span><span class="sxs-lookup"><span data-stu-id="5d24e-777">driver's licence</span></span>  <br/> <span data-ttu-id="5d24e-778">driver's license</span><span class="sxs-lookup"><span data-stu-id="5d24e-778">driver's license</span></span>  <br/> <span data-ttu-id="5d24e-779">driving licence</span><span class="sxs-lookup"><span data-stu-id="5d24e-779">driving licence</span></span>  <br/> <span data-ttu-id="5d24e-780">driving license</span><span class="sxs-lookup"><span data-stu-id="5d24e-780">driving license</span></span>  <br/> <span data-ttu-id="5d24e-781">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="5d24e-781">driver licence number</span></span>  <br/> <span data-ttu-id="5d24e-782">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="5d24e-782">driver license number</span></span>  <br/> <span data-ttu-id="5d24e-783">número de licencia de drivers</span><span class="sxs-lookup"><span data-stu-id="5d24e-783">drivers licence number</span></span>  <br/> <span data-ttu-id="5d24e-784">número de licencia de drivers</span><span class="sxs-lookup"><span data-stu-id="5d24e-784">drivers license number</span></span>  <br/> <span data-ttu-id="5d24e-785">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="5d24e-785">driver's licence number</span></span>  <br/> <span data-ttu-id="5d24e-786">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="5d24e-786">driver's license number</span></span>  <br/> <span data-ttu-id="5d24e-787">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="5d24e-787">driving licence number</span></span>  <br/> <span data-ttu-id="5d24e-788">número de licencia de conducir</span><span class="sxs-lookup"><span data-stu-id="5d24e-788">driving license number</span></span>  <br/> <span data-ttu-id="5d24e-789">permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="5d24e-789">driving permit</span></span>  <br/> <span data-ttu-id="5d24e-790">número de permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="5d24e-790">driving permit number</span></span>  <br/> <span data-ttu-id="5d24e-791">permisos de conducción</span><span class="sxs-lookup"><span data-stu-id="5d24e-791">permiso de conducción</span></span>  <br/> <span data-ttu-id="5d24e-792">permisos conducción</span><span class="sxs-lookup"><span data-stu-id="5d24e-792">permiso conducción</span></span>  <br/> <span data-ttu-id="5d24e-793">número de licencia conducir</span><span class="sxs-lookup"><span data-stu-id="5d24e-793">número licencia conducir</span></span>  <br/> <span data-ttu-id="5d24e-794">número de cuaderno de conducir</span><span class="sxs-lookup"><span data-stu-id="5d24e-794">número de carnet de conducir</span></span>  <br/> <span data-ttu-id="5d24e-795">número conducir de cuaderno</span><span class="sxs-lookup"><span data-stu-id="5d24e-795">número carnet conducir</span></span>  <br/> <span data-ttu-id="5d24e-796">licenciar conducir</span><span class="sxs-lookup"><span data-stu-id="5d24e-796">licencia conducir</span></span>  <br/> <span data-ttu-id="5d24e-797">número de permisos de conducir</span><span class="sxs-lookup"><span data-stu-id="5d24e-797">número de permiso de conducir</span></span>  <br/> <span data-ttu-id="5d24e-798">número de permisos conducir</span><span class="sxs-lookup"><span data-stu-id="5d24e-798">número de permiso conducir</span></span>  <br/> <span data-ttu-id="5d24e-799">número permisos conducir</span><span class="sxs-lookup"><span data-stu-id="5d24e-799">número permiso conducir</span></span>  <br/> <span data-ttu-id="5d24e-800">permisos conducir</span><span class="sxs-lookup"><span data-stu-id="5d24e-800">permiso conducir</span></span>  <br/> <span data-ttu-id="5d24e-801">licencia de manejo</span><span class="sxs-lookup"><span data-stu-id="5d24e-801">licencia de manejo</span></span>  <br/> <span data-ttu-id="5d24e-802">el cuaderno de conducir</span><span class="sxs-lookup"><span data-stu-id="5d24e-802">el carnet de conducir</span></span>  <br/> <span data-ttu-id="5d24e-803">conducir del cuaderno</span><span class="sxs-lookup"><span data-stu-id="5d24e-803">carnet conducir</span></span>  <br/> |
   
## <a name="sweden"></a><span data-ttu-id="5d24e-804">Suecia</span><span class="sxs-lookup"><span data-stu-id="5d24e-804">Sweden</span></span>

### <a name="format"></a><span data-ttu-id="5d24e-805">Formato</span><span class="sxs-lookup"><span data-stu-id="5d24e-805">Format</span></span>

<span data-ttu-id="5d24e-806">Diez dígitos que contienen un guión</span><span class="sxs-lookup"><span data-stu-id="5d24e-806">Ten digits containing a hyphen</span></span>
  
### <a name="pattern"></a><span data-ttu-id="5d24e-807">Patrón</span><span class="sxs-lookup"><span data-stu-id="5d24e-807">Pattern</span></span>

<span data-ttu-id="5d24e-808">Diez dígitos que contienen un guión:</span><span class="sxs-lookup"><span data-stu-id="5d24e-808">Ten digits containing a hyphen:</span></span>
  
-  <span data-ttu-id="5d24e-809">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="5d24e-809">Six digits</span></span> 
    
- <span data-ttu-id="5d24e-810">Un guión</span><span class="sxs-lookup"><span data-stu-id="5d24e-810">A hyphen</span></span>
    
- <span data-ttu-id="5d24e-811">Cuatro dígitos</span><span class="sxs-lookup"><span data-stu-id="5d24e-811">Four digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="5d24e-812">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="5d24e-812">Checksum</span></span>

<span data-ttu-id="5d24e-813">No</span><span class="sxs-lookup"><span data-stu-id="5d24e-813">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="5d24e-814">Definición</span><span class="sxs-lookup"><span data-stu-id="5d24e-814">Definition</span></span>

<span data-ttu-id="5d24e-815">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="5d24e-815">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5d24e-816">La expresión `Regex_sweden_eu_driver's_license_number` regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="5d24e-816">The regular expression  `Regex_sweden_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5d24e-817">Se encuentra una `Keywords_sweden_eu_driver's_license_number` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="5d24e-817">A keyword from  `Keywords_sweden_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_sweden_eu_driver's_license_number" />
          <Match idRef="Keywords_sweden_eu_driver's_license_number" />
        </Pattern>
</Entity> 
```

### <a name="keywords"></a><span data-ttu-id="5d24e-818">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="5d24e-818">Keywords</span></span>

<span data-ttu-id="5d24e-819">| |</span><span class="sxs-lookup"><span data-stu-id="5d24e-819"></span></span>
|<span data-ttu-id="5d24e-820">**Keywords_sweden_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="5d24e-820">**Keywords_sweden_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="5d24e-821">listas</span><span class="sxs-lookup"><span data-stu-id="5d24e-821">dl#</span></span>  <br/> <span data-ttu-id="5d24e-822">driver license</span><span class="sxs-lookup"><span data-stu-id="5d24e-822">driver license</span></span>  <br/> <span data-ttu-id="5d24e-823">número de licencia de conductor</span><span class="sxs-lookup"><span data-stu-id="5d24e-823">driver license number</span></span>  <br/> <span data-ttu-id="5d24e-824">permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="5d24e-824">driver licence</span></span>  <br/> <span data-ttu-id="5d24e-825">Lic de drivers.</span><span class="sxs-lookup"><span data-stu-id="5d24e-825">drivers lic.</span></span>  <br/> <span data-ttu-id="5d24e-826">drivers license</span><span class="sxs-lookup"><span data-stu-id="5d24e-826">drivers license</span></span>  <br/> <span data-ttu-id="5d24e-827">drivers licence</span><span class="sxs-lookup"><span data-stu-id="5d24e-827">drivers licence</span></span>  <br/> <span data-ttu-id="5d24e-828">driver's license</span><span class="sxs-lookup"><span data-stu-id="5d24e-828">driver's license</span></span>  <br/> <span data-ttu-id="5d24e-829">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="5d24e-829">driver's license number</span></span>  <br/> <span data-ttu-id="5d24e-830">número de permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="5d24e-830">driver's licence number</span></span>  <br/> <span data-ttu-id="5d24e-831">número de licencia de conducir</span><span class="sxs-lookup"><span data-stu-id="5d24e-831">driving license number</span></span>  <br/> <span data-ttu-id="5d24e-832">dlno #</span><span class="sxs-lookup"><span data-stu-id="5d24e-832">dlno#</span></span>  <br/> <span data-ttu-id="5d24e-833">körkort</span><span class="sxs-lookup"><span data-stu-id="5d24e-833">körkort</span></span>  <br/> |
   
## <a name="uk"></a><span data-ttu-id="5d24e-834">LIBRA</span><span class="sxs-lookup"><span data-stu-id="5d24e-834">UK</span></span>

<span data-ttu-id="5d24e-835">Para obtener más información, consulte la sección "Reino Unido.</span><span class="sxs-lookup"><span data-stu-id="5d24e-835">For details, see the section "U.K.</span></span> <span data-ttu-id="5d24e-836">Número de permiso de conducir "en [Qué buscan los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="5d24e-836">Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="5d24e-837">Vea también</span><span class="sxs-lookup"><span data-stu-id="5d24e-837">See also</span></span>

[<span data-ttu-id="5d24e-838">Qué buscan los tipos de información confidencial</span><span class="sxs-lookup"><span data-stu-id="5d24e-838">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

