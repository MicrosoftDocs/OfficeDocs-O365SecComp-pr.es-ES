---
title: Número de teléfono móvil de la UE
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/16/2018
ms.audience: Admin
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
ms.assetid: 555e7675-2ae8-42d1-9b8e-2c8f8cd21337
description: Prevención de pérdida de datos (DLP) en la seguridad de Office 365 &amp; centro de cumplimiento incluye muchos tipos de información confidencial que están listos para su uso en las directivas de DLP. En este tema se describe el tipo de información confidencial de número de teléfono móvil de la UE.
ms.openlocfilehash: d0818759dae8ed86cc9aef6f7fad48cbd2acf24f
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22536101"
---
# <a name="eu-mobile-phone-number"></a><span data-ttu-id="4312e-104">Número de teléfono móvil de la UE</span><span class="sxs-lookup"><span data-stu-id="4312e-104">EU Mobile Phone Number</span></span>

<span data-ttu-id="4312e-p102">Prevención de pérdida de datos (DLP) en la seguridad de Office 365 &amp; centro de cumplimiento incluye muchos tipos de información confidencial que están listos para su uso en las directivas de DLP. En este tema se describe el tipo de información confidencial de número de teléfono móvil de la UE.</span><span class="sxs-lookup"><span data-stu-id="4312e-p102">Data loss prevention (DLP) in the Office 365 Security &amp; Compliance Center includes many sensitive information types that are ready for you to use in your DLP policies. This topic describes the EU Mobile Phone Number sensitive information type.</span></span> 
  
## <a name="austria"></a><span data-ttu-id="4312e-107">Austria</span><span class="sxs-lookup"><span data-stu-id="4312e-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="4312e-108">Formato</span><span class="sxs-lookup"><span data-stu-id="4312e-108">Format</span></span>

<span data-ttu-id="4312e-109">Dígitos sin longitud estándar</span><span class="sxs-lookup"><span data-stu-id="4312e-109">Digits without standard lengths</span></span>
  
### <a name="pattern"></a><span data-ttu-id="4312e-110">Patrón</span><span class="sxs-lookup"><span data-stu-id="4312e-110">Pattern</span></span>

-  <span data-ttu-id="4312e-111">Dígitos</span><span class="sxs-lookup"><span data-stu-id="4312e-111">Digits</span></span> 
    
### <a name="definition"></a><span data-ttu-id="4312e-112">Definición</span><span class="sxs-lookup"><span data-stu-id="4312e-112">Definition</span></span>

<span data-ttu-id="4312e-113">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4312e-113">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="4312e-114">La expresión regular `Regex_austria_eu_mobile_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4312e-114">The regular expression  `Regex_austria_eu_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="4312e-115">La expresión regular `Regex_austria_eu_formatted_mobile_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4312e-115">The regular expression  `Regex_austria_eu_formatted_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="4312e-116">Una palabra clave de `Keywords_austria_eu_mobile_number` se encuentra.</span><span class="sxs-lookup"><span data-stu-id="4312e-116">A keyword from  `Keywords_austria_eu_mobile_number` is found.</span></span> 
    
```
 
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_mobile_number"/>
          <Match idRef="Keywords_austria_eu_mobile_number" />
        </Pattern>
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_austria_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="belgium"></a><span data-ttu-id="4312e-117">Bélgica</span><span class="sxs-lookup"><span data-stu-id="4312e-117">Belgium</span></span>

### <a name="pattern"></a><span data-ttu-id="4312e-118">Patrón</span><span class="sxs-lookup"><span data-stu-id="4312e-118">Pattern</span></span>

-  <span data-ttu-id="4312e-119">Dígitos</span><span class="sxs-lookup"><span data-stu-id="4312e-119">Digits</span></span> 
    
### <a name="definition"></a><span data-ttu-id="4312e-120">Definición</span><span class="sxs-lookup"><span data-stu-id="4312e-120">Definition</span></span>

<span data-ttu-id="4312e-121">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4312e-121">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="4312e-122">La expresión regular `Regex_belgium_eu_mobile_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4312e-122">The regular expression  `Regex_belgium_eu_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="4312e-123">La expresión regular `Regex_belgium_eu_formatted_mobile_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4312e-123">The regular expression  `Regex_belgium_eu_formatted_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="4312e-124">Una palabra clave de `Keywords_belgium_eu_mobile_number` se encuentra.</span><span class="sxs-lookup"><span data-stu-id="4312e-124">A keyword from  `Keywords_belgium_eu_mobile_number` is found.</span></span> 
    
```
 
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_mobile_number"/>
          <Match idRef="Keywords_belgium_eu_mobile_number" />
        </Pattern>
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_belgium_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="bulgaria"></a><span data-ttu-id="4312e-125">Bulgaria</span><span class="sxs-lookup"><span data-stu-id="4312e-125">Bulgaria</span></span>

### <a name="pattern"></a><span data-ttu-id="4312e-126">Patrón</span><span class="sxs-lookup"><span data-stu-id="4312e-126">Pattern</span></span>

-  <span data-ttu-id="4312e-127">Dígitos</span><span class="sxs-lookup"><span data-stu-id="4312e-127">Digits</span></span> 
    
### <a name="definition"></a><span data-ttu-id="4312e-128">Definición</span><span class="sxs-lookup"><span data-stu-id="4312e-128">Definition</span></span>

<span data-ttu-id="4312e-129">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4312e-129">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="4312e-130">La expresión regular `Regex_bulgaria_eu_mobile_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4312e-130">The regular expression  `Regex_bulgaria_eu_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="4312e-131">La expresión regular `Regex_bulgaria_eu_formatted_mobile_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4312e-131">The regular expression  `Regex_bulgaria_eu_formatted_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="4312e-132">Una palabra clave de `Keywords_bulgaria_eu_mobile_number` se encuentra.</span><span class="sxs-lookup"><span data-stu-id="4312e-132">A keyword from  `Keywords_bulgaria_eu_mobile_number` is found.</span></span> 
    
```
 
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_mobile_number"/>
          <Match idRef="Keywords_bulgaria_eu_mobile_number" />
        </Pattern>
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_bulgaria_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="croatia"></a><span data-ttu-id="4312e-133">Croacia</span><span class="sxs-lookup"><span data-stu-id="4312e-133">Croatia</span></span>

### <a name="pattern"></a><span data-ttu-id="4312e-134">Patrón</span><span class="sxs-lookup"><span data-stu-id="4312e-134">Pattern</span></span>

-  <span data-ttu-id="4312e-135">Dígitos</span><span class="sxs-lookup"><span data-stu-id="4312e-135">Digits</span></span> 
    
### <a name="definition"></a><span data-ttu-id="4312e-136">Definición</span><span class="sxs-lookup"><span data-stu-id="4312e-136">Definition</span></span>

<span data-ttu-id="4312e-137">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4312e-137">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="4312e-138">La expresión regular `Regex_croatia_eu_mobile_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4312e-138">The regular expression  `Regex_croatia_eu_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="4312e-139">La expresión regular `Regex_croatia_eu_formatted_mobile_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4312e-139">The regular expression  `Regex_croatia_eu_formatted_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="4312e-140">Una palabra clave de `Keywords_croatia_eu_mobile_number` se encuentra.</span><span class="sxs-lookup"><span data-stu-id="4312e-140">A keyword from  `Keywords_croatia_eu_mobile_number` is found.</span></span> 
    
```
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_mobile_number"/>
          <Match idRef="Keywords_croatia_eu_mobile_number" />
        </Pattern>
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_croatia_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="cyprus"></a><span data-ttu-id="4312e-141">Chipre</span><span class="sxs-lookup"><span data-stu-id="4312e-141">Cyprus</span></span>

### <a name="pattern"></a><span data-ttu-id="4312e-142">Patrón</span><span class="sxs-lookup"><span data-stu-id="4312e-142">Pattern</span></span>

-  <span data-ttu-id="4312e-143">Dígitos</span><span class="sxs-lookup"><span data-stu-id="4312e-143">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="4312e-144">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="4312e-144">Checksum</span></span>

<span data-ttu-id="4312e-145">No aplicable</span><span class="sxs-lookup"><span data-stu-id="4312e-145">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="4312e-146">Definición</span><span class="sxs-lookup"><span data-stu-id="4312e-146">Definition</span></span>

<span data-ttu-id="4312e-147">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4312e-147">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="4312e-148">La expresión regular `Regex_cyprus_eu_mobile_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4312e-148">The regular expression  `Regex_cyprus_eu_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="4312e-149">La expresión regular `Regex_cyprus_eu_formatted_mobile_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4312e-149">The regular expression  `Regex_cyprus_eu_formatted_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="4312e-150">Una palabra clave de `Keywords_cyprus_eu_mobile_number` se encuentra.</span><span class="sxs-lookup"><span data-stu-id="4312e-150">A keyword from  `Keywords_cyprus_eu_mobile_number` is found.</span></span> 
    
```
 
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_mobile_number"/>
          <Match idRef="Keywords_cyprus_eu_mobile_number" />
        </Pattern>
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_cyprus_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="czech-republic"></a><span data-ttu-id="4312e-151">República Checa</span><span class="sxs-lookup"><span data-stu-id="4312e-151">Czech Republic</span></span>

### <a name="pattern"></a><span data-ttu-id="4312e-152">Patrón</span><span class="sxs-lookup"><span data-stu-id="4312e-152">Pattern</span></span>

-  <span data-ttu-id="4312e-153">Dígitos</span><span class="sxs-lookup"><span data-stu-id="4312e-153">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="4312e-154">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="4312e-154">Checksum</span></span>

<span data-ttu-id="4312e-155">No aplicable</span><span class="sxs-lookup"><span data-stu-id="4312e-155">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="4312e-156">Definición</span><span class="sxs-lookup"><span data-stu-id="4312e-156">Definition</span></span>

<span data-ttu-id="4312e-157">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4312e-157">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="4312e-158">La expresión regular `Regex_czech_republic_eu_mobile_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4312e-158">The regular expression  `Regex_czech_republic_eu_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="4312e-159">La expresión regular `Regex_czech_republic_eu_formatted_mobile_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4312e-159">The regular expression  `Regex_czech_republic_eu_formatted_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="4312e-160">Una palabra clave de `Keywords_czech_republic_eu_mobile_number` se encuentra.</span><span class="sxs-lookup"><span data-stu-id="4312e-160">A keyword from  `Keywords_czech_republic_eu_mobile_number` is found.</span></span> 
    
```
 
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_mobile_number"/>
          <Match idRef="Keywords_czech_republic_eu_mobile_number" />
        </Pattern>
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_czech_republic_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="denmark"></a><span data-ttu-id="4312e-161">Dinamarca</span><span class="sxs-lookup"><span data-stu-id="4312e-161">Denmark</span></span>

### <a name="pattern"></a><span data-ttu-id="4312e-162">Patrón</span><span class="sxs-lookup"><span data-stu-id="4312e-162">Pattern</span></span>

-  <span data-ttu-id="4312e-163">Dígitos</span><span class="sxs-lookup"><span data-stu-id="4312e-163">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="4312e-164">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="4312e-164">Checksum</span></span>

<span data-ttu-id="4312e-165">No aplicable</span><span class="sxs-lookup"><span data-stu-id="4312e-165">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="4312e-166">Definición</span><span class="sxs-lookup"><span data-stu-id="4312e-166">Definition</span></span>

<span data-ttu-id="4312e-167">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4312e-167">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="4312e-168">La expresión regular `Regex_denmark_eu_mobile_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4312e-168">The regular expression  `Regex_denmark_eu_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="4312e-169">La expresión regular `Regex_denmark_eu_formatted_mobile_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4312e-169">The regular expression  `Regex_denmark_eu_formatted_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="4312e-170">Una palabra clave de `Keywords_denmark_eu_mobile_number` se encuentra.</span><span class="sxs-lookup"><span data-stu-id="4312e-170">A keyword from  `Keywords_denmark_eu_mobile_number` is found.</span></span> 
    
```
 
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_mobile_number"/>
          <Match idRef="Keywords_denmark_eu_mobile_number" />
        </Pattern>
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_denmark_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="estonia"></a><span data-ttu-id="4312e-171">Estonia</span><span class="sxs-lookup"><span data-stu-id="4312e-171">Estonia</span></span>

### <a name="pattern"></a><span data-ttu-id="4312e-172">Patrón</span><span class="sxs-lookup"><span data-stu-id="4312e-172">Pattern</span></span>

-  <span data-ttu-id="4312e-173">Dígitos</span><span class="sxs-lookup"><span data-stu-id="4312e-173">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="4312e-174">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="4312e-174">Checksum</span></span>

<span data-ttu-id="4312e-175">No aplicable</span><span class="sxs-lookup"><span data-stu-id="4312e-175">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="4312e-176">Definición</span><span class="sxs-lookup"><span data-stu-id="4312e-176">Definition</span></span>

<span data-ttu-id="4312e-177">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4312e-177">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="4312e-178">La expresión regular `Regex_estonia_eu_mobile_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4312e-178">The regular expression  `Regex_estonia_eu_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="4312e-179">La expresión regular `Regex_estonia_eu_formatted_mobile_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4312e-179">The regular expression  `Regex_estonia_eu_formatted_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="4312e-180">Una palabra clave de `Keywords_estonia_eu_mobile_number` se encuentra.</span><span class="sxs-lookup"><span data-stu-id="4312e-180">A keyword from  `Keywords_estonia_eu_mobile_number` is found.</span></span> 
    
```
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_mobile_number"/>
          <Match idRef="Keywords_estonia_eu_mobile_number" />
        </Pattern>
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_estonia_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="finland"></a><span data-ttu-id="4312e-181">Finlandia</span><span class="sxs-lookup"><span data-stu-id="4312e-181">Finland</span></span>

### <a name="pattern"></a><span data-ttu-id="4312e-182">Patrón</span><span class="sxs-lookup"><span data-stu-id="4312e-182">Pattern</span></span>

-  <span data-ttu-id="4312e-183">Dígitos</span><span class="sxs-lookup"><span data-stu-id="4312e-183">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="4312e-184">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="4312e-184">Checksum</span></span>

<span data-ttu-id="4312e-185">No aplicable</span><span class="sxs-lookup"><span data-stu-id="4312e-185">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="4312e-186">Definición</span><span class="sxs-lookup"><span data-stu-id="4312e-186">Definition</span></span>

<span data-ttu-id="4312e-187">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4312e-187">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="4312e-188">La expresión regular `Regex_finland_eu_mobile_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4312e-188">The regular expression  `Regex_finland_eu_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="4312e-189">La expresión regular `Regex_finland_eu_formatted_mobile_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4312e-189">The regular expression  `Regex_finland_eu_formatted_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="4312e-190">Una palabra clave de `Keywords_finland_eu_mobile_number` se encuentra.</span><span class="sxs-lookup"><span data-stu-id="4312e-190">A keyword from  `Keywords_finland_eu_mobile_number` is found.</span></span> 
    
```
 
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_finland_eu_mobile_number"/>
          <Match idRef="Keywords_finland_eu_mobile_number" />
        </Pattern>
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_finland_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="france"></a><span data-ttu-id="4312e-191">Francia</span><span class="sxs-lookup"><span data-stu-id="4312e-191">France</span></span>

### <a name="pattern"></a><span data-ttu-id="4312e-192">Patrón</span><span class="sxs-lookup"><span data-stu-id="4312e-192">Pattern</span></span>

-  <span data-ttu-id="4312e-193">Dígitos</span><span class="sxs-lookup"><span data-stu-id="4312e-193">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="4312e-194">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="4312e-194">Checksum</span></span>

<span data-ttu-id="4312e-195">No aplicable</span><span class="sxs-lookup"><span data-stu-id="4312e-195">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="4312e-196">Definición</span><span class="sxs-lookup"><span data-stu-id="4312e-196">Definition</span></span>

<span data-ttu-id="4312e-197">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4312e-197">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="4312e-198">La expresión regular `Regex_france_eu_mobile_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4312e-198">The regular expression  `Regex_france_eu_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="4312e-199">La expresión regular `Regex_france_eu_formatted_mobile_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4312e-199">The regular expression  `Regex_france_eu_formatted_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="4312e-200">Una palabra clave de `Keywords_france_eu_mobile_number` se encuentra.</span><span class="sxs-lookup"><span data-stu-id="4312e-200">A keyword from  `Keywords_france_eu_mobile_number` is found.</span></span> 
    
```
 
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_france_eu_mobile_number"/>
          <Match idRef="Keywords_france_eu_mobile_number" />
        </Pattern>
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_france_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="germany"></a><span data-ttu-id="4312e-201">Alemania</span><span class="sxs-lookup"><span data-stu-id="4312e-201">Germany</span></span>

### <a name="pattern"></a><span data-ttu-id="4312e-202">Patrón</span><span class="sxs-lookup"><span data-stu-id="4312e-202">Pattern</span></span>

-  <span data-ttu-id="4312e-203">Dígitos</span><span class="sxs-lookup"><span data-stu-id="4312e-203">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="4312e-204">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="4312e-204">Checksum</span></span>

<span data-ttu-id="4312e-205">No aplicable</span><span class="sxs-lookup"><span data-stu-id="4312e-205">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="4312e-206">Definición</span><span class="sxs-lookup"><span data-stu-id="4312e-206">Definition</span></span>

<span data-ttu-id="4312e-207">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4312e-207">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="4312e-208">La expresión regular `Regex_germany_eu_mobile_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4312e-208">The regular expression  `Regex_germany_eu_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="4312e-209">La expresión regular `Regex_germany_eu_formatted_mobile_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4312e-209">The regular expression  `Regex_germany_eu_formatted_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="4312e-210">Una palabra clave de `Keywords_germany_eu_mobile_number` se encuentra.</span><span class="sxs-lookup"><span data-stu-id="4312e-210">A keyword from  `Keywords_germany_eu_mobile_number` is found.</span></span> 
    
```
 
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_germany_eu_mobile_number"/>
          <Match idRef="Keywords_germany_eu_mobile_number" />
        </Pattern>
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_germany_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="greece"></a><span data-ttu-id="4312e-211">Grecia</span><span class="sxs-lookup"><span data-stu-id="4312e-211">Greece</span></span>

### <a name="pattern"></a><span data-ttu-id="4312e-212">Patrón</span><span class="sxs-lookup"><span data-stu-id="4312e-212">Pattern</span></span>

-  <span data-ttu-id="4312e-213">Dígitos</span><span class="sxs-lookup"><span data-stu-id="4312e-213">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="4312e-214">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="4312e-214">Checksum</span></span>

<span data-ttu-id="4312e-215">No aplicable</span><span class="sxs-lookup"><span data-stu-id="4312e-215">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="4312e-216">Definición</span><span class="sxs-lookup"><span data-stu-id="4312e-216">Definition</span></span>

<span data-ttu-id="4312e-217">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4312e-217">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="4312e-218">La expresión regular `Regex_greece_eu_mobile_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4312e-218">The regular expression  `Regex_greece_eu_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="4312e-219">La expresión regular `Regex_greece_eu_formatted_mobile_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4312e-219">The regular expression  `Regex_greece_eu_formatted_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="4312e-220">Una palabra clave de `Keywords_greece_eu_mobile_number` se encuentra.</span><span class="sxs-lookup"><span data-stu-id="4312e-220">A keyword from  `Keywords_greece_eu_mobile_number` is found.</span></span> 
    
```
 
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_mobile_number"/>
          <Match idRef="Keywords_greece_eu_mobile_number" />
        </Pattern>
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_greece_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="hungary"></a><span data-ttu-id="4312e-221">Hungría</span><span class="sxs-lookup"><span data-stu-id="4312e-221">Hungary</span></span>

### <a name="pattern"></a><span data-ttu-id="4312e-222">Patrón</span><span class="sxs-lookup"><span data-stu-id="4312e-222">Pattern</span></span>

-  <span data-ttu-id="4312e-223">Dígitos</span><span class="sxs-lookup"><span data-stu-id="4312e-223">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="4312e-224">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="4312e-224">Checksum</span></span>

<span data-ttu-id="4312e-225">No aplicable</span><span class="sxs-lookup"><span data-stu-id="4312e-225">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="4312e-226">Definición</span><span class="sxs-lookup"><span data-stu-id="4312e-226">Definition</span></span>

<span data-ttu-id="4312e-227">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4312e-227">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="4312e-228">La expresión regular `Regex_hungary_eu_mobile_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4312e-228">The regular expression  `Regex_hungary_eu_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="4312e-229">La expresión regular `Regex_hungary_eu_formatted_mobile_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4312e-229">The regular expression  `Regex_hungary_eu_formatted_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="4312e-230">Una palabra clave de `Keywords_hungary_eu_mobile_number` se encuentra.</span><span class="sxs-lookup"><span data-stu-id="4312e-230">A keyword from  `Keywords_hungary_eu_mobile_number` is found.</span></span> 
    
```
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_mobile_number"/>
          <Match idRef="Keywords_hungary_eu_mobile_number" />
        </Pattern>
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_hungary_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="ireland"></a><span data-ttu-id="4312e-231">Irlanda</span><span class="sxs-lookup"><span data-stu-id="4312e-231">Ireland</span></span>

### <a name="pattern"></a><span data-ttu-id="4312e-232">Patrón</span><span class="sxs-lookup"><span data-stu-id="4312e-232">Pattern</span></span>

-  <span data-ttu-id="4312e-233">Dígitos</span><span class="sxs-lookup"><span data-stu-id="4312e-233">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="4312e-234">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="4312e-234">Checksum</span></span>

<span data-ttu-id="4312e-235">No aplicable</span><span class="sxs-lookup"><span data-stu-id="4312e-235">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="4312e-236">Definición</span><span class="sxs-lookup"><span data-stu-id="4312e-236">Definition</span></span>

<span data-ttu-id="4312e-237">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4312e-237">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="4312e-238">La expresión regular `Regex_ireland_eu_mobile_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4312e-238">The regular expression  `Regex_ireland_eu_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="4312e-239">La expresión regular `Regex_ireland_eu_formatted_mobile_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4312e-239">The regular expression  `Regex_ireland_eu_formatted_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="4312e-240">Una palabra clave de `Keywords_ireland_eu_mobile_number` se encuentra.</span><span class="sxs-lookup"><span data-stu-id="4312e-240">A keyword from  `Keywords_ireland_eu_mobile_number` is found.</span></span> 
    
```
 
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_mobile_number"/>
          <Match idRef="Keywords_ireland_eu_mobile_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_ireland_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="italy"></a><span data-ttu-id="4312e-241">Italia</span><span class="sxs-lookup"><span data-stu-id="4312e-241">Italy</span></span>

### <a name="pattern"></a><span data-ttu-id="4312e-242">Patrón</span><span class="sxs-lookup"><span data-stu-id="4312e-242">Pattern</span></span>

-  <span data-ttu-id="4312e-243">Dígitos</span><span class="sxs-lookup"><span data-stu-id="4312e-243">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="4312e-244">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="4312e-244">Checksum</span></span>

<span data-ttu-id="4312e-245">No aplicable</span><span class="sxs-lookup"><span data-stu-id="4312e-245">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="4312e-246">Definición</span><span class="sxs-lookup"><span data-stu-id="4312e-246">Definition</span></span>

<span data-ttu-id="4312e-247">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4312e-247">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="4312e-248">La expresión regular `Regex_italy_eu_mobile_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4312e-248">The regular expression  `Regex_italy_eu_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="4312e-249">La expresión regular `Regex_italy_eu_formatted_mobile_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4312e-249">The regular expression  `Regex_italy_eu_formatted_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="4312e-250">Una palabra clave de `Keywords_italy_eu_mobile_number` se encuentra.</span><span class="sxs-lookup"><span data-stu-id="4312e-250">A keyword from  `Keywords_italy_eu_mobile_number` is found.</span></span> 
    
```
 
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_italy_eu_mobile_number"/>
          <Match idRef="Keywords_italy_eu_mobile_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_italy_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="latvia"></a><span data-ttu-id="4312e-251">Letonia</span><span class="sxs-lookup"><span data-stu-id="4312e-251">Latvia</span></span>

### <a name="pattern"></a><span data-ttu-id="4312e-252">Patrón</span><span class="sxs-lookup"><span data-stu-id="4312e-252">Pattern</span></span>

-  <span data-ttu-id="4312e-253">Dígitos</span><span class="sxs-lookup"><span data-stu-id="4312e-253">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="4312e-254">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="4312e-254">Checksum</span></span>

<span data-ttu-id="4312e-255">No aplicable</span><span class="sxs-lookup"><span data-stu-id="4312e-255">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="4312e-256">Definición</span><span class="sxs-lookup"><span data-stu-id="4312e-256">Definition</span></span>

<span data-ttu-id="4312e-257">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4312e-257">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="4312e-258">La expresión regular `Regex_latvia_eu_mobile_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4312e-258">The regular expression  `Regex_latvia_eu_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="4312e-259">La expresión regular `Regex_latvia_eu_formatted_mobile_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4312e-259">The regular expression  `Regex_latvia_eu_formatted_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="4312e-260">Una palabra clave de `Keywords_latvia_eu_mobile_number` se encuentra.</span><span class="sxs-lookup"><span data-stu-id="4312e-260">A keyword from  `Keywords_latvia_eu_mobile_number` is found.</span></span> 
    
```
 
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_mobile_number"/>
          <Match idRef="Keywords_latvia_eu_mobile_number" />
        </Pattern>
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_latvia_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="lithuania"></a><span data-ttu-id="4312e-261">Lituania</span><span class="sxs-lookup"><span data-stu-id="4312e-261">Lithuania</span></span>

### <a name="pattern"></a><span data-ttu-id="4312e-262">Patrón</span><span class="sxs-lookup"><span data-stu-id="4312e-262">Pattern</span></span>

-  <span data-ttu-id="4312e-263">Dígitos</span><span class="sxs-lookup"><span data-stu-id="4312e-263">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="4312e-264">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="4312e-264">Checksum</span></span>

<span data-ttu-id="4312e-265">No aplicable</span><span class="sxs-lookup"><span data-stu-id="4312e-265">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="4312e-266">Definición</span><span class="sxs-lookup"><span data-stu-id="4312e-266">Definition</span></span>

<span data-ttu-id="4312e-267">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4312e-267">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="4312e-268">La expresión regular `Regex_lithuania_eu_mobile_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4312e-268">The regular expression  `Regex_lithuania_eu_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="4312e-269">La expresión regular `Regex_lithuania_eu_formatted_mobile_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4312e-269">The regular expression  `Regex_lithuania_eu_formatted_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="4312e-270">Una palabra clave de `Keywords_lithuania_eu_mobile_number` se encuentra.</span><span class="sxs-lookup"><span data-stu-id="4312e-270">A keyword from  `Keywords_lithuania_eu_mobile_number` is found.</span></span> 
    
```
 
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_mobile_number"/>
          <Match idRef="Keywords_lithuania_eu_mobile_number" />
        </Pattern>
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_lithuania_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="luxemburg"></a><span data-ttu-id="4312e-271">Luxemburgo</span><span class="sxs-lookup"><span data-stu-id="4312e-271">Luxemburg</span></span>

### <a name="pattern"></a><span data-ttu-id="4312e-272">Patrón</span><span class="sxs-lookup"><span data-stu-id="4312e-272">Pattern</span></span>

-  <span data-ttu-id="4312e-273">Dígitos</span><span class="sxs-lookup"><span data-stu-id="4312e-273">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="4312e-274">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="4312e-274">Checksum</span></span>

<span data-ttu-id="4312e-275">No aplicable</span><span class="sxs-lookup"><span data-stu-id="4312e-275">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="4312e-276">Definición</span><span class="sxs-lookup"><span data-stu-id="4312e-276">Definition</span></span>

<span data-ttu-id="4312e-277">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4312e-277">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="4312e-278">La expresión regular `Regex_luxumburg_eu_mobile_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4312e-278">The regular expression  `Regex_luxumburg_eu_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="4312e-279">La expresión regular `Regex_luxumburg_eu_formatted_mobile_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4312e-279">The regular expression  `Regex_luxumburg_eu_formatted_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="4312e-280">Una palabra clave de `Keywords_luxumburg_eu_mobile_number` se encuentra.</span><span class="sxs-lookup"><span data-stu-id="4312e-280">A keyword from  `Keywords_luxumburg_eu_mobile_number` is found.</span></span> 
    
```
 
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_luxumburg_eu_mobile_number"/>
          <Match idRef="Keywords_luxumburg_eu_mobile_number" />
        </Pattern>
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_luxumburg_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="malta"></a><span data-ttu-id="4312e-281">Malta</span><span class="sxs-lookup"><span data-stu-id="4312e-281">Malta</span></span>

### <a name="pattern"></a><span data-ttu-id="4312e-282">Patrón</span><span class="sxs-lookup"><span data-stu-id="4312e-282">Pattern</span></span>

-  <span data-ttu-id="4312e-283">Dígitos</span><span class="sxs-lookup"><span data-stu-id="4312e-283">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="4312e-284">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="4312e-284">Checksum</span></span>

<span data-ttu-id="4312e-285">No aplicable</span><span class="sxs-lookup"><span data-stu-id="4312e-285">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="4312e-286">Definición</span><span class="sxs-lookup"><span data-stu-id="4312e-286">Definition</span></span>

<span data-ttu-id="4312e-287">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4312e-287">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="4312e-288">La expresión regular `Regex_malta_eu_mobile_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4312e-288">The regular expression  `Regex_malta_eu_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="4312e-289">La expresión regular `Regex_malta_eu_formatted_mobile_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4312e-289">The regular expression  `Regex_malta_eu_formatted_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="4312e-290">Una palabra clave de `Keywords_malta_eu_mobile_number` se encuentra.</span><span class="sxs-lookup"><span data-stu-id="4312e-290">A keyword from  `Keywords_malta_eu_mobile_number` is found.</span></span> 
    
```
 
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_mobile_number"/>
          <Match idRef="Keywords_malta_eu_mobile_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_malta_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="netherlands"></a><span data-ttu-id="4312e-291">Países Bajos</span><span class="sxs-lookup"><span data-stu-id="4312e-291">Netherlands</span></span>

### <a name="pattern"></a><span data-ttu-id="4312e-292">Patrón</span><span class="sxs-lookup"><span data-stu-id="4312e-292">Pattern</span></span>

-  <span data-ttu-id="4312e-293">Dígitos</span><span class="sxs-lookup"><span data-stu-id="4312e-293">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="4312e-294">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="4312e-294">Checksum</span></span>

<span data-ttu-id="4312e-295">No aplicable</span><span class="sxs-lookup"><span data-stu-id="4312e-295">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="4312e-296">Definición</span><span class="sxs-lookup"><span data-stu-id="4312e-296">Definition</span></span>

<span data-ttu-id="4312e-297">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4312e-297">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="4312e-298">La expresión regular `Regex_netherlands_eu_mobile_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4312e-298">The regular expression  `Regex_netherlands_eu_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="4312e-299">La expresión regular `Regex_netherlands_eu_formatted_mobile_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4312e-299">The regular expression  `Regex_netherlands_eu_formatted_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="4312e-300">Una palabra clave de `Keywords_netherlands_eu_mobile_number` se encuentra.</span><span class="sxs-lookup"><span data-stu-id="4312e-300">A keyword from  `Keywords_netherlands_eu_mobile_number` is found.</span></span> 
    
```
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_mobile_number"/>
          <Match idRef="Keywords_netherlands_eu_mobile_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_netherlands_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="poland"></a><span data-ttu-id="4312e-301">Polonia</span><span class="sxs-lookup"><span data-stu-id="4312e-301">Poland</span></span>

### <a name="pattern"></a><span data-ttu-id="4312e-302">Patrón</span><span class="sxs-lookup"><span data-stu-id="4312e-302">Pattern</span></span>

-  <span data-ttu-id="4312e-303">Dígitos</span><span class="sxs-lookup"><span data-stu-id="4312e-303">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="4312e-304">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="4312e-304">Checksum</span></span>

<span data-ttu-id="4312e-305">No aplicable</span><span class="sxs-lookup"><span data-stu-id="4312e-305">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="4312e-306">Definición</span><span class="sxs-lookup"><span data-stu-id="4312e-306">Definition</span></span>

<span data-ttu-id="4312e-307">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4312e-307">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="4312e-308">La expresión regular `Regex_poland_eu_mobile_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4312e-308">The regular expression  `Regex_poland_eu_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="4312e-309">La expresión regular `Regex_poland_eu_formatted_mobile_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4312e-309">The regular expression  `Regex_poland_eu_formatted_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="4312e-310">Una palabra clave de `Keywords_poland_eu_mobile_number` se encuentra.</span><span class="sxs-lookup"><span data-stu-id="4312e-310">A keyword from  `Keywords_poland_eu_mobile_number` is found.</span></span> 
    
```
 
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_poland_eu_mobile_number"/>
          <Match idRef="Keywords_poland_eu_mobile_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_poland_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="portugal"></a><span data-ttu-id="4312e-311">Portugal</span><span class="sxs-lookup"><span data-stu-id="4312e-311">Portugal</span></span>

### <a name="pattern"></a><span data-ttu-id="4312e-312">Patrón</span><span class="sxs-lookup"><span data-stu-id="4312e-312">Pattern</span></span>

-  <span data-ttu-id="4312e-313">Dígitos</span><span class="sxs-lookup"><span data-stu-id="4312e-313">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="4312e-314">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="4312e-314">Checksum</span></span>

<span data-ttu-id="4312e-315">No aplicable</span><span class="sxs-lookup"><span data-stu-id="4312e-315">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="4312e-316">Definición</span><span class="sxs-lookup"><span data-stu-id="4312e-316">Definition</span></span>

<span data-ttu-id="4312e-317">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4312e-317">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="4312e-318">La expresión regular `Regex_portugal_eu_mobile_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4312e-318">The regular expression  `Regex_portugal_eu_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="4312e-319">La expresión regular `Regex_portugal_eu_formatted_mobile_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4312e-319">The regular expression  `Regex_portugal_eu_formatted_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="4312e-320">Una palabra clave de `Keywords_portugal_eu_mobile_number` se encuentra.</span><span class="sxs-lookup"><span data-stu-id="4312e-320">A keyword from  `Keywords_portugal_eu_mobile_number` is found.</span></span> 
    
```
 
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_mobile_number"/>
          <Match idRef="Keywords_portugal_eu_mobile_number" />
        </Pattern>
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_portugal_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="romania"></a><span data-ttu-id="4312e-321">Rumania</span><span class="sxs-lookup"><span data-stu-id="4312e-321">Romania</span></span>

### <a name="pattern"></a><span data-ttu-id="4312e-322">Patrón</span><span class="sxs-lookup"><span data-stu-id="4312e-322">Pattern</span></span>

-  <span data-ttu-id="4312e-323">Dígitos</span><span class="sxs-lookup"><span data-stu-id="4312e-323">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="4312e-324">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="4312e-324">Checksum</span></span>

<span data-ttu-id="4312e-325">No aplicable</span><span class="sxs-lookup"><span data-stu-id="4312e-325">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="4312e-326">Definición</span><span class="sxs-lookup"><span data-stu-id="4312e-326">Definition</span></span>

<span data-ttu-id="4312e-327">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4312e-327">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="4312e-328">La expresión regular `Regex_romania_eu_mobile_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4312e-328">The regular expression  `Regex_romania_eu_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="4312e-329">La expresión regular `Regex_romania_eu_formatted_mobile_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4312e-329">The regular expression  `Regex_romania_eu_formatted_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="4312e-330">Una palabra clave de `Keywords_romania_eu_mobile_number` se encuentra.</span><span class="sxs-lookup"><span data-stu-id="4312e-330">A keyword from  `Keywords_romania_eu_mobile_number` is found.</span></span> 
    
```
 
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_mobile_number"/>
          <Match idRef="Keywords_romania_eu_mobile_number" />
        </Pattern>
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_romania_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="slovakia"></a><span data-ttu-id="4312e-331">Eslovaquia</span><span class="sxs-lookup"><span data-stu-id="4312e-331">Slovakia</span></span>

### <a name="pattern"></a><span data-ttu-id="4312e-332">Patrón</span><span class="sxs-lookup"><span data-stu-id="4312e-332">Pattern</span></span>

-  <span data-ttu-id="4312e-333">Dígitos</span><span class="sxs-lookup"><span data-stu-id="4312e-333">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="4312e-334">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="4312e-334">Checksum</span></span>

<span data-ttu-id="4312e-335">No aplicable</span><span class="sxs-lookup"><span data-stu-id="4312e-335">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="4312e-336">Definición</span><span class="sxs-lookup"><span data-stu-id="4312e-336">Definition</span></span>

<span data-ttu-id="4312e-337">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4312e-337">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="4312e-338">La expresión regular `Regex_slovakia_eu_mobile_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4312e-338">The regular expression  `Regex_slovakia_eu_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="4312e-339">La expresión regular `Regex_slovakia_eu_formatted_mobile_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4312e-339">The regular expression  `Regex_slovakia_eu_formatted_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="4312e-340">Una palabra clave de `Keywords_slovakia_eu_mobile_number` se encuentra.</span><span class="sxs-lookup"><span data-stu-id="4312e-340">A keyword from  `Keywords_slovakia_eu_mobile_number` is found.</span></span> 
    
```
 
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_mobile_number"/>
          <Match idRef="Keywords_slovakia_eu_mobile_number" />
        </Pattern>
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_slovakia_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="slovenia"></a><span data-ttu-id="4312e-341">Eslovenia</span><span class="sxs-lookup"><span data-stu-id="4312e-341">Slovenia</span></span>

### <a name="pattern"></a><span data-ttu-id="4312e-342">Patrón</span><span class="sxs-lookup"><span data-stu-id="4312e-342">Pattern</span></span>

-  <span data-ttu-id="4312e-343">Dígitos</span><span class="sxs-lookup"><span data-stu-id="4312e-343">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="4312e-344">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="4312e-344">Checksum</span></span>

<span data-ttu-id="4312e-345">No aplicable</span><span class="sxs-lookup"><span data-stu-id="4312e-345">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="4312e-346">Definición</span><span class="sxs-lookup"><span data-stu-id="4312e-346">Definition</span></span>

<span data-ttu-id="4312e-347">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4312e-347">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="4312e-348">La expresión regular `Regex_slovenia_eu_mobile_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4312e-348">The regular expression  `Regex_slovenia_eu_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="4312e-349">La expresión regular `Regex_slovenia_eu_formatted_mobile_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4312e-349">The regular expression  `Regex_slovenia_eu_formatted_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="4312e-350">Una palabra clave de `Keywords_slovenia_eu_mobile_number` se encuentra.</span><span class="sxs-lookup"><span data-stu-id="4312e-350">A keyword from  `Keywords_slovenia_eu_mobile_number` is found.</span></span> 
    
```
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_mobile_number"/>
          <Match idRef="Keywords_slovenia_eu_mobile_number" />
        </Pattern>
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_slovenia_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="spain"></a><span data-ttu-id="4312e-351">España</span><span class="sxs-lookup"><span data-stu-id="4312e-351">Spain</span></span>

### <a name="pattern"></a><span data-ttu-id="4312e-352">Patrón</span><span class="sxs-lookup"><span data-stu-id="4312e-352">Pattern</span></span>

-  <span data-ttu-id="4312e-353">Dígitos</span><span class="sxs-lookup"><span data-stu-id="4312e-353">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="4312e-354">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="4312e-354">Checksum</span></span>

<span data-ttu-id="4312e-355">No aplicable</span><span class="sxs-lookup"><span data-stu-id="4312e-355">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="4312e-356">Definición</span><span class="sxs-lookup"><span data-stu-id="4312e-356">Definition</span></span>

<span data-ttu-id="4312e-357">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4312e-357">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="4312e-358">La expresión regular `Regex_spain_eu_mobile_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4312e-358">The regular expression  `Regex_spain_eu_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="4312e-359">La expresión regular `Regex_spain_eu_formatted_mobile_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4312e-359">The regular expression  `Regex_spain_eu_formatted_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="4312e-360">Una palabra clave de `Keywords_spain_eu_mobile_number` se encuentra.</span><span class="sxs-lookup"><span data-stu-id="4312e-360">A keyword from  `Keywords_spain_eu_mobile_number` is found.</span></span> 
    
```
 
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_spain_eu_mobile_number"/>
          <Match idRef="Keywords_spain_eu_mobile_number" />
        </Pattern>
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_spain_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="sweden"></a><span data-ttu-id="4312e-361">Suecia</span><span class="sxs-lookup"><span data-stu-id="4312e-361">Sweden</span></span>

### <a name="pattern"></a><span data-ttu-id="4312e-362">Patrón</span><span class="sxs-lookup"><span data-stu-id="4312e-362">Pattern</span></span>

-  <span data-ttu-id="4312e-363">Dígitos</span><span class="sxs-lookup"><span data-stu-id="4312e-363">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="4312e-364">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="4312e-364">Checksum</span></span>

<span data-ttu-id="4312e-365">No aplicable</span><span class="sxs-lookup"><span data-stu-id="4312e-365">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="4312e-366">Definición</span><span class="sxs-lookup"><span data-stu-id="4312e-366">Definition</span></span>

<span data-ttu-id="4312e-367">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4312e-367">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="4312e-368">La expresión regular `Regex_sweden_eu_mobile_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4312e-368">The regular expression  `Regex_sweden_eu_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="4312e-369">La expresión regular `Regex_sweden_eu_formatted_mobile_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4312e-369">The regular expression  `Regex_sweden_eu_formatted_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="4312e-370">Una palabra clave de `Keywords_sweden_eu_mobile_number` se encuentra.</span><span class="sxs-lookup"><span data-stu-id="4312e-370">A keyword from  `Keywords_sweden_eu_mobile_number` is found.</span></span> 
    
```
 
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_sweden_eu_mobile_number"/>
          <Match idRef="Keywords_sweden_eu_mobile_number" />
        </Pattern>
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_sweden_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="uk"></a><span data-ttu-id="4312e-371">REINO UNIDO</span><span class="sxs-lookup"><span data-stu-id="4312e-371">UK</span></span>

### <a name="pattern"></a><span data-ttu-id="4312e-372">Patrón</span><span class="sxs-lookup"><span data-stu-id="4312e-372">Pattern</span></span>

-  <span data-ttu-id="4312e-373">Dígitos</span><span class="sxs-lookup"><span data-stu-id="4312e-373">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="4312e-374">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="4312e-374">Checksum</span></span>

<span data-ttu-id="4312e-375">No aplicable</span><span class="sxs-lookup"><span data-stu-id="4312e-375">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="4312e-376">Definición</span><span class="sxs-lookup"><span data-stu-id="4312e-376">Definition</span></span>

<span data-ttu-id="4312e-377">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4312e-377">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="4312e-378">La expresión regular `Regex_uk_eu_mobile_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4312e-378">The regular expression  `Regex_uk_eu_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="4312e-379">La expresión regular `Regex_uk_eu_formatted_mobile_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="4312e-379">The regular expression  `Regex_uk_eu_formatted_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="4312e-380">Una palabra clave de `Keywords_uk_eu_mobile_number` se encuentra.</span><span class="sxs-lookup"><span data-stu-id="4312e-380">A keyword from  `Keywords_uk_eu_mobile_number` is found.</span></span> 
    
```
 
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_uk_eu_mobile_number"/>
          <Match idRef="Keywords_uk_eu_mobile_number" />
        </Pattern>
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_uk_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="see-also"></a><span data-ttu-id="4312e-381">Vea también</span><span class="sxs-lookup"><span data-stu-id="4312e-381">See also</span></span>

[<span data-ttu-id="4312e-382">Qué buscan los tipos de información confidencial</span><span class="sxs-lookup"><span data-stu-id="4312e-382">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

