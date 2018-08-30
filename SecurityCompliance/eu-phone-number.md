---
title: Número de teléfono de la UE
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/17/2018
ms.audience: Admin
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
ms.assetid: 1c90ca41-1681-46bf-8ad6-6bf4cec5c426
description: Prevención de pérdida de datos (DLP) en la seguridad de Office 365 &amp; centro de cumplimiento incluye muchos tipos de información confidencial que están listos para su uso en las directivas de DLP. En este tema se describe el tipo de información confidencial de número de teléfono de la UE.
ms.openlocfilehash: 9dd878e3385312982f9f3a4927205e3ebb27aabb
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22536269"
---
# <a name="eu-phone-number"></a><span data-ttu-id="93d04-104">Número de teléfono de la UE</span><span class="sxs-lookup"><span data-stu-id="93d04-104">EU Phone Number</span></span>

<span data-ttu-id="93d04-p102">Prevención de pérdida de datos (DLP) en la seguridad de Office 365 &amp; centro de cumplimiento incluye muchos tipos de información confidencial que están listos para su uso en las directivas de DLP. En este tema se describe el tipo de información confidencial de número de teléfono de la UE.</span><span class="sxs-lookup"><span data-stu-id="93d04-p102">Data loss prevention (DLP) in the Office 365 Security &amp; Compliance Center includes many sensitive information types that are ready for you to use in your DLP policies. This topic describes the EU Phone Number sensitive information type.</span></span> 
  
## <a name="austria"></a><span data-ttu-id="93d04-107">Austria</span><span class="sxs-lookup"><span data-stu-id="93d04-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="93d04-108">Formato</span><span class="sxs-lookup"><span data-stu-id="93d04-108">Format</span></span>

<span data-ttu-id="93d04-109">No hay longitud estándar</span><span class="sxs-lookup"><span data-stu-id="93d04-109">No standard length</span></span>
  
### <a name="pattern"></a><span data-ttu-id="93d04-110">Patrón</span><span class="sxs-lookup"><span data-stu-id="93d04-110">Pattern</span></span>

- <span data-ttu-id="93d04-111">Dígitos</span><span class="sxs-lookup"><span data-stu-id="93d04-111">Digits</span></span> 
    
- <span data-ttu-id="93d04-112">Sólo los números de teléfono móvil comenzarán con el dígito "6"</span><span class="sxs-lookup"><span data-stu-id="93d04-112">Only mobile phone numbers begin with the digit "6"</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="93d04-113">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="93d04-113">Checksum</span></span>

<span data-ttu-id="93d04-114">No aplicable</span><span class="sxs-lookup"><span data-stu-id="93d04-114">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="93d04-115">Definición</span><span class="sxs-lookup"><span data-stu-id="93d04-115">Definition</span></span>

<span data-ttu-id="93d04-116">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="93d04-116">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="93d04-117">La expresión regular `Regex_austria_eu_telephone_number_1` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="93d04-117">The regular expression  `Regex_austria_eu_telephone_number_1` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="93d04-118">Una palabra clave de `Keywords_austria_eu_telephone_number` se encuentra.</span><span class="sxs-lookup"><span data-stu-id="93d04-118">A keyword from  `Keywords_austria_eu_telephone_number` is found.</span></span> 
    
<span data-ttu-id="93d04-119">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="93d04-119">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="93d04-120">La expresión regular `Regex_austria_eu_telephone_number_2` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="93d04-120">The regular expression  `Regex_austria_eu_telephone_number_2` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="93d04-121">Una palabra clave de `Keywords_austria_eu_telephone_number` se encuentra.</span><span class="sxs-lookup"><span data-stu-id="93d04-121">A keyword from  `Keywords_austria_eu_telephone_number` is found.</span></span> 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_telephone_number_1" />
          <Match idRef="Keywords_austria_eu_telephone_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_telephone_number_2" />
          <Match idRef="Keywords_austria_eu_telephone_number" />
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_austria_eu_formatted_telephone_number_1" />
          </Pattern>
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_austria_eu_formatted_telephone_number_2" />
          </Pattern>
</Entity>
```

## <a name="belgium"></a><span data-ttu-id="93d04-122">Bélgica</span><span class="sxs-lookup"><span data-stu-id="93d04-122">Belgium</span></span>

### <a name="definition"></a><span data-ttu-id="93d04-123">Definición</span><span class="sxs-lookup"><span data-stu-id="93d04-123">Definition</span></span>

<span data-ttu-id="93d04-124">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="93d04-124">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="93d04-125">La expresión regular `Regex_belgium_eu_telephone_number_1` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="93d04-125">The regular expression  `Regex_belgium_eu_telephone_number_1` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="93d04-126">Una palabra clave de `Keywords_belgium_eu_telephone_number` se encuentra.</span><span class="sxs-lookup"><span data-stu-id="93d04-126">A keyword from  `Keywords_belgium_eu_telephone_number` is found.</span></span> 
    
<span data-ttu-id="93d04-127">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="93d04-127">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="93d04-128">La expresión regular `Regex_belgium_eu_telephone_number_2` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="93d04-128">The regular expression  `Regex_belgium_eu_telephone_number_2` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="93d04-129">Una palabra clave de `Keywords_belgium_eu_telephone_number` se encuentra.</span><span class="sxs-lookup"><span data-stu-id="93d04-129">A keyword from  `Keywords_belgium_eu_telephone_number` is found.</span></span> 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_telephone_number_1" />
          <Match idRef="Keywords_belgium_eu_telephone_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_telephone_number_2" />
          <Match idRef="Keywords_belgium_eu_telephone_number" />
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_belgium_eu_formatted_telephone_number_1" />
          </Pattern>
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_belgium_eu_formatted_telephone_number_2" />
          </Pattern></Entity>
```

## <a name="bulgaria"></a><span data-ttu-id="93d04-130">Bulgaria</span><span class="sxs-lookup"><span data-stu-id="93d04-130">Bulgaria</span></span>

### <a name="pattern"></a><span data-ttu-id="93d04-131">Patrón</span><span class="sxs-lookup"><span data-stu-id="93d04-131">Pattern</span></span>

- <span data-ttu-id="93d04-132">Dígitos</span><span class="sxs-lookup"><span data-stu-id="93d04-132">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="93d04-133">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="93d04-133">Checksum</span></span>

<span data-ttu-id="93d04-134">No aplicable</span><span class="sxs-lookup"><span data-stu-id="93d04-134">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="93d04-135">Definición</span><span class="sxs-lookup"><span data-stu-id="93d04-135">Definition</span></span>

<span data-ttu-id="93d04-136">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="93d04-136">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="93d04-137">La expresión regular `Regex_bulgaria_eu_telephone_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="93d04-137">The regular expression  `Regex_bulgaria_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="93d04-138">Una palabra clave de `Keywords_bulgaria_eu_telephone_number` se encuentra.</span><span class="sxs-lookup"><span data-stu-id="93d04-138">A keyword from  `Keywords_bulgaria_eu_telephone_number` is found.</span></span> 
    
<span data-ttu-id="93d04-139">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="93d04-139">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="93d04-140">La expresión regular `Regex_bulgaria_eu_telephone_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="93d04-140">The regular expression  `Regex_bulgaria_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_telephone_number" />
          <Match idRef="Keywords_bulgaria_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_bulgaria_eu_formatted_telephone_number" />
          </Pattern>
          
</Entity>
```

## <a name="croatia"></a><span data-ttu-id="93d04-141">Croacia</span><span class="sxs-lookup"><span data-stu-id="93d04-141">Croatia</span></span>

### <a name="pattern"></a><span data-ttu-id="93d04-142">Patrón</span><span class="sxs-lookup"><span data-stu-id="93d04-142">Pattern</span></span>

- <span data-ttu-id="93d04-143">Dígitos</span><span class="sxs-lookup"><span data-stu-id="93d04-143">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="93d04-144">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="93d04-144">Checksum</span></span>

<span data-ttu-id="93d04-145">No aplicable</span><span class="sxs-lookup"><span data-stu-id="93d04-145">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="93d04-146">Definición</span><span class="sxs-lookup"><span data-stu-id="93d04-146">Definition</span></span>

<span data-ttu-id="93d04-147">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="93d04-147">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="93d04-148">La expresión regular `Regex_croatia_eu_telephone_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="93d04-148">The regular expression  `Regex_croatia_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="93d04-149">Una palabra clave de `Keywords_croatia_eu_telephone_number` se encuentra.</span><span class="sxs-lookup"><span data-stu-id="93d04-149">A keyword from  `Keywords_croatia_eu_telephone_number` is found.</span></span> 
    
<span data-ttu-id="93d04-150">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="93d04-150">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="93d04-151">La expresión regular `Regex_croatia_eu_telephone_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="93d04-151">The regular expression  `Regex_croatia_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_telephone_number" />
          <Match idRef="Keywords_croatia_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_croatia_eu_formatted_telephone_number" />
          </Pattern>
         </Entity>
```

## <a name="cyprus"></a><span data-ttu-id="93d04-152">Chipre</span><span class="sxs-lookup"><span data-stu-id="93d04-152">Cyprus</span></span>

### <a name="pattern"></a><span data-ttu-id="93d04-153">Patrón</span><span class="sxs-lookup"><span data-stu-id="93d04-153">Pattern</span></span>

- <span data-ttu-id="93d04-154">Dígitos</span><span class="sxs-lookup"><span data-stu-id="93d04-154">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="93d04-155">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="93d04-155">Checksum</span></span>

<span data-ttu-id="93d04-156">No aplicable</span><span class="sxs-lookup"><span data-stu-id="93d04-156">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="93d04-157">Definición</span><span class="sxs-lookup"><span data-stu-id="93d04-157">Definition</span></span>

<span data-ttu-id="93d04-158">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="93d04-158">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="93d04-159">La expresión regular `Regex_cyprus_eu_telephone_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="93d04-159">The regular expression  `Regex_cyprus_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="93d04-160">Una palabra clave de `Keywords_cyprus_eu_telephone_number` se encuentra.</span><span class="sxs-lookup"><span data-stu-id="93d04-160">A keyword from  `Keywords_cyprus_eu_telephone_number` is found.</span></span> 
    
<span data-ttu-id="93d04-161">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="93d04-161">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="93d04-162">La expresión regular `Regex_cyprus_eu_telephone_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="93d04-162">The regular expression  `Regex_cyprus_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_telephone_number" />
          <Match idRef="Keywords_cyprus_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_cyprus_eu_formatted_telephone_number" />
            </Pattern>
</Entity>
```

## <a name="czech-republic"></a><span data-ttu-id="93d04-163">República Checa</span><span class="sxs-lookup"><span data-stu-id="93d04-163">Czech Republic</span></span>

### <a name="pattern"></a><span data-ttu-id="93d04-164">Patrón</span><span class="sxs-lookup"><span data-stu-id="93d04-164">Pattern</span></span>

- <span data-ttu-id="93d04-165">Dígitos</span><span class="sxs-lookup"><span data-stu-id="93d04-165">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="93d04-166">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="93d04-166">Checksum</span></span>

<span data-ttu-id="93d04-167">No aplicable</span><span class="sxs-lookup"><span data-stu-id="93d04-167">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="93d04-168">Definición</span><span class="sxs-lookup"><span data-stu-id="93d04-168">Definition</span></span>

<span data-ttu-id="93d04-169">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="93d04-169">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="93d04-170">La expresión regular `Regex_czech_republic_eu_telephone_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="93d04-170">The regular expression  `Regex_czech_republic_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="93d04-171">Una palabra clave de `Keywords_czech_republic_eu_telephone_number` se encuentra.</span><span class="sxs-lookup"><span data-stu-id="93d04-171">A keyword from  `Keywords_czech_republic_eu_telephone_number` is found.</span></span> 
    
<span data-ttu-id="93d04-172">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="93d04-172">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="93d04-173">La expresión regular `Regex_czech_republic_eu_telephone_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="93d04-173">The regular expression  `Regex_czech_republic_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_telephone_number" />
          <Match idRef="Keywords_czech_republic_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_czech_republic_eu_formatted_telephone_number" />
          </Pattern>
        </Entity>
```

## <a name="denmark"></a><span data-ttu-id="93d04-174">Dinamarca</span><span class="sxs-lookup"><span data-stu-id="93d04-174">Denmark</span></span>

### <a name="pattern"></a><span data-ttu-id="93d04-175">Patrón</span><span class="sxs-lookup"><span data-stu-id="93d04-175">Pattern</span></span>

- <span data-ttu-id="93d04-176">Dígitos</span><span class="sxs-lookup"><span data-stu-id="93d04-176">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="93d04-177">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="93d04-177">Checksum</span></span>

<span data-ttu-id="93d04-178">No aplicable</span><span class="sxs-lookup"><span data-stu-id="93d04-178">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="93d04-179">Definición</span><span class="sxs-lookup"><span data-stu-id="93d04-179">Definition</span></span>

<span data-ttu-id="93d04-180">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="93d04-180">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="93d04-181">La expresión regular `Regex_denmark_eu_telephone_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="93d04-181">The regular expression  `Regex_denmark_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="93d04-182">Una palabra clave de `Keywords_denmark_eu_telephone_number` se encuentra.</span><span class="sxs-lookup"><span data-stu-id="93d04-182">A keyword from  `Keywords_denmark_eu_telephone_number` is found.</span></span> 
    
<span data-ttu-id="93d04-183">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="93d04-183">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="93d04-184">La expresión regular `Regex_denmark_eu_telephone_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="93d04-184">The regular expression  `Regex_denmark_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_telephone_number" />
          <Match idRef="Keywords_denmark_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_denmark_eu_formatted_telephone_number" />
          </Pattern>
          </Entity>
```

## <a name="estonia"></a><span data-ttu-id="93d04-185">Estonia</span><span class="sxs-lookup"><span data-stu-id="93d04-185">Estonia</span></span>

### <a name="pattern"></a><span data-ttu-id="93d04-186">Patrón</span><span class="sxs-lookup"><span data-stu-id="93d04-186">Pattern</span></span>

- <span data-ttu-id="93d04-187">Dígitos</span><span class="sxs-lookup"><span data-stu-id="93d04-187">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="93d04-188">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="93d04-188">Checksum</span></span>

<span data-ttu-id="93d04-189">No aplicable</span><span class="sxs-lookup"><span data-stu-id="93d04-189">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="93d04-190">Definición</span><span class="sxs-lookup"><span data-stu-id="93d04-190">Definition</span></span>

<span data-ttu-id="93d04-191">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="93d04-191">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="93d04-192">La expresión regular `Regex_estonia_eu_telephone_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="93d04-192">The regular expression  `Regex_estonia_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="93d04-193">Una palabra clave de `Keywords_estonia_eu_telephone_number` se encuentra.</span><span class="sxs-lookup"><span data-stu-id="93d04-193">A keyword from  `Keywords_estonia_eu_telephone_number` is found.</span></span> 
    
<span data-ttu-id="93d04-194">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="93d04-194">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="93d04-195">La expresión regular `Regex_estonia_eu_telephone_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="93d04-195">The regular expression  `Regex_estonia_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_telephone_number" />
          <Match idRef="Keywords_estonia_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_estonia_eu_formatted_telephone_number" />
          </Pattern>
       </Entity>
```

## <a name="finland"></a><span data-ttu-id="93d04-196">Finlandia</span><span class="sxs-lookup"><span data-stu-id="93d04-196">Finland</span></span>

### <a name="pattern"></a><span data-ttu-id="93d04-197">Patrón</span><span class="sxs-lookup"><span data-stu-id="93d04-197">Pattern</span></span>

- <span data-ttu-id="93d04-198">Dígitos</span><span class="sxs-lookup"><span data-stu-id="93d04-198">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="93d04-199">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="93d04-199">Checksum</span></span>

<span data-ttu-id="93d04-200">No aplicable</span><span class="sxs-lookup"><span data-stu-id="93d04-200">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="93d04-201">Definición</span><span class="sxs-lookup"><span data-stu-id="93d04-201">Definition</span></span>

<span data-ttu-id="93d04-202">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="93d04-202">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="93d04-203">La expresión regular `Regex_finland_eu_telephone_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="93d04-203">The regular expression  `Regex_finland_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="93d04-204">Una palabra clave de `Keywords_finland_eu_telephone_number` se encuentra.</span><span class="sxs-lookup"><span data-stu-id="93d04-204">A keyword from  `Keywords_finland_eu_telephone_number` is found.</span></span> 
    
<span data-ttu-id="93d04-205">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="93d04-205">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="93d04-206">La expresión regular `Regex_finland_eu_telephone_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="93d04-206">The regular expression  `Regex_finland_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_finland_eu_telephone_number" />
          <Match idRef="Keywords_finland_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_finland_eu_formatted_telephone_number" />
             </Pattern>
</Entity>
```

## <a name="france"></a><span data-ttu-id="93d04-207">Francia</span><span class="sxs-lookup"><span data-stu-id="93d04-207">France</span></span>

### <a name="pattern"></a><span data-ttu-id="93d04-208">Patrón</span><span class="sxs-lookup"><span data-stu-id="93d04-208">Pattern</span></span>

- <span data-ttu-id="93d04-209">Dígitos</span><span class="sxs-lookup"><span data-stu-id="93d04-209">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="93d04-210">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="93d04-210">Checksum</span></span>

<span data-ttu-id="93d04-211">No aplicable</span><span class="sxs-lookup"><span data-stu-id="93d04-211">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="93d04-212">Definición</span><span class="sxs-lookup"><span data-stu-id="93d04-212">Definition</span></span>

<span data-ttu-id="93d04-213">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="93d04-213">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="93d04-214">La expresión regular `Regex_france_eu_telephone_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="93d04-214">The regular expression  `Regex_france_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="93d04-215">Una palabra clave de `Keywords_france_eu_telephone_number` se encuentra.</span><span class="sxs-lookup"><span data-stu-id="93d04-215">A keyword from  `Keywords_france_eu_telephone_number` is found.</span></span> 
    
<span data-ttu-id="93d04-216">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="93d04-216">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="93d04-217">La expresión regular `Regex_france_eu_telephone_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="93d04-217">The regular expression  `Regex_france_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_france_eu_telephone_number" />
          <Match idRef="Keywords_france_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_france_eu_formatted_telephone_number" />
          </Pattern>
          </Entity>
```

## <a name="germany"></a><span data-ttu-id="93d04-218">Alemania</span><span class="sxs-lookup"><span data-stu-id="93d04-218">Germany</span></span>

### <a name="pattern"></a><span data-ttu-id="93d04-219">Patrón</span><span class="sxs-lookup"><span data-stu-id="93d04-219">Pattern</span></span>

- <span data-ttu-id="93d04-220">Dígitos</span><span class="sxs-lookup"><span data-stu-id="93d04-220">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="93d04-221">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="93d04-221">Checksum</span></span>

<span data-ttu-id="93d04-222">No aplicable</span><span class="sxs-lookup"><span data-stu-id="93d04-222">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="93d04-223">Definición</span><span class="sxs-lookup"><span data-stu-id="93d04-223">Definition</span></span>

<span data-ttu-id="93d04-224">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="93d04-224">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="93d04-225">La expresión regular `Regex_germany_eu_telephone_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="93d04-225">The regular expression  `Regex_germany_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="93d04-226">Una palabra clave de `Keywords_germany_eu_telephone_number` se encuentra.</span><span class="sxs-lookup"><span data-stu-id="93d04-226">A keyword from  `Keywords_germany_eu_telephone_number` is found.</span></span> 
    
<span data-ttu-id="93d04-227">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="93d04-227">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="93d04-228">La expresión regular `Regex_germany_eu_telephone_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="93d04-228">The regular expression  `Regex_germany_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_germany_eu_telephone_number" />
          <Match idRef="Keywords_germany_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_germany_eu_formatted_telephone_number" />
          </Pattern>
        </Entity>
```

## <a name="greece"></a><span data-ttu-id="93d04-229">Grecia</span><span class="sxs-lookup"><span data-stu-id="93d04-229">Greece</span></span>

### <a name="pattern"></a><span data-ttu-id="93d04-230">Patrón</span><span class="sxs-lookup"><span data-stu-id="93d04-230">Pattern</span></span>

- <span data-ttu-id="93d04-231">Dígitos</span><span class="sxs-lookup"><span data-stu-id="93d04-231">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="93d04-232">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="93d04-232">Checksum</span></span>

<span data-ttu-id="93d04-233">No aplicable</span><span class="sxs-lookup"><span data-stu-id="93d04-233">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="93d04-234">Definición</span><span class="sxs-lookup"><span data-stu-id="93d04-234">Definition</span></span>

<span data-ttu-id="93d04-235">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="93d04-235">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="93d04-236">La expresión regular `Regex_greece_eu_telephone_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="93d04-236">The regular expression  `Regex_greece_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="93d04-237">Una palabra clave de `Keywords_greece_eu_telephone_number` se encuentra.</span><span class="sxs-lookup"><span data-stu-id="93d04-237">A keyword from  `Keywords_greece_eu_telephone_number` is found.</span></span> 
    
<span data-ttu-id="93d04-238">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="93d04-238">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="93d04-239">La expresión regular `Regex_greece_eu_telephone_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="93d04-239">The regular expression  `Regex_greece_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_telephone_number" />
          <Match idRef="Keywords_greece_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_greece_eu_formatted_telephone_number" />
          </Pattern>
        </Entity>
```

## <a name="hungary"></a><span data-ttu-id="93d04-240">Hungría</span><span class="sxs-lookup"><span data-stu-id="93d04-240">Hungary</span></span>

### <a name="pattern"></a><span data-ttu-id="93d04-241">Patrón</span><span class="sxs-lookup"><span data-stu-id="93d04-241">Pattern</span></span>

- <span data-ttu-id="93d04-242">Dígitos</span><span class="sxs-lookup"><span data-stu-id="93d04-242">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="93d04-243">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="93d04-243">Checksum</span></span>

<span data-ttu-id="93d04-244">No aplicable</span><span class="sxs-lookup"><span data-stu-id="93d04-244">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="93d04-245">Definición</span><span class="sxs-lookup"><span data-stu-id="93d04-245">Definition</span></span>

<span data-ttu-id="93d04-246">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="93d04-246">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="93d04-247">La expresión regular `Regex_hungary_eu_telephone_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="93d04-247">The regular expression  `Regex_hungary_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="93d04-248">Una palabra clave de `Keywords_hungary_eu_telephone_number` se encuentra.</span><span class="sxs-lookup"><span data-stu-id="93d04-248">A keyword from  `Keywords_hungary_eu_telephone_number` is found.</span></span> 
    
<span data-ttu-id="93d04-249">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="93d04-249">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="93d04-250">La expresión regular `Regex_hungary_eu_telephone_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="93d04-250">The regular expression  `Regex_hungary_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_telephone_number" />
          <Match idRef="Keywords_hungary_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_hungary_eu_formatted_telephone_number" />
          </Pattern>
       </Entity>
```

## <a name="ireland"></a><span data-ttu-id="93d04-251">Irlanda</span><span class="sxs-lookup"><span data-stu-id="93d04-251">Ireland</span></span>

### <a name="pattern"></a><span data-ttu-id="93d04-252">Patrón</span><span class="sxs-lookup"><span data-stu-id="93d04-252">Pattern</span></span>

- <span data-ttu-id="93d04-253">Dígitos</span><span class="sxs-lookup"><span data-stu-id="93d04-253">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="93d04-254">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="93d04-254">Checksum</span></span>

<span data-ttu-id="93d04-255">No aplicable</span><span class="sxs-lookup"><span data-stu-id="93d04-255">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="93d04-256">Definición</span><span class="sxs-lookup"><span data-stu-id="93d04-256">Definition</span></span>

<span data-ttu-id="93d04-257">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="93d04-257">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="93d04-258">La expresión regular `Regex_ireland_eu_telephone_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="93d04-258">The regular expression  `Regex_ireland_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="93d04-259">Una palabra clave de `Keywords_ireland_eu_telephone_number` se encuentra.</span><span class="sxs-lookup"><span data-stu-id="93d04-259">A keyword from  `Keywords_ireland_eu_telephone_number` is found.</span></span> 
    
<span data-ttu-id="93d04-260">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="93d04-260">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="93d04-261">La expresión regular `Regex_ireland_eu_telephone_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="93d04-261">The regular expression  `Regex_ireland_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_telephone_number" />
          <Match idRef="Keywords_ireland_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_ireland_eu_formatted_telephone_number" />
          </Pattern>
          </Entity>
```

## <a name="italy"></a><span data-ttu-id="93d04-262">Italia</span><span class="sxs-lookup"><span data-stu-id="93d04-262">Italy</span></span>

### <a name="pattern"></a><span data-ttu-id="93d04-263">Patrón</span><span class="sxs-lookup"><span data-stu-id="93d04-263">Pattern</span></span>

- <span data-ttu-id="93d04-264">Dígitos</span><span class="sxs-lookup"><span data-stu-id="93d04-264">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="93d04-265">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="93d04-265">Checksum</span></span>

<span data-ttu-id="93d04-266">No aplicable</span><span class="sxs-lookup"><span data-stu-id="93d04-266">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="93d04-267">Definición</span><span class="sxs-lookup"><span data-stu-id="93d04-267">Definition</span></span>

<span data-ttu-id="93d04-268">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="93d04-268">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="93d04-269">La expresión regular `Regex_italy_eu_telephone_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="93d04-269">The regular expression  `Regex_italy_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="93d04-270">Una palabra clave de `Keywords_italy_eu_telephone_number` se encuentra.</span><span class="sxs-lookup"><span data-stu-id="93d04-270">A keyword from  `Keywords_italy_eu_telephone_number` is found.</span></span> 
    
<span data-ttu-id="93d04-271">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="93d04-271">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="93d04-272">La expresión regular `Regex_italy_eu_telephone_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="93d04-272">The regular expression  `Regex_italy_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_italy_eu_telephone_number" />
          <Match idRef="Keywords_italy_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_italy_eu_formatted_telephone_number" />
          </Pattern>
         </Entity>
```

## <a name="latvia"></a><span data-ttu-id="93d04-273">Letonia</span><span class="sxs-lookup"><span data-stu-id="93d04-273">Latvia</span></span>

### <a name="pattern"></a><span data-ttu-id="93d04-274">Patrón</span><span class="sxs-lookup"><span data-stu-id="93d04-274">Pattern</span></span>

- <span data-ttu-id="93d04-275">Dígitos</span><span class="sxs-lookup"><span data-stu-id="93d04-275">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="93d04-276">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="93d04-276">Checksum</span></span>

<span data-ttu-id="93d04-277">No aplicable</span><span class="sxs-lookup"><span data-stu-id="93d04-277">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="93d04-278">Definición</span><span class="sxs-lookup"><span data-stu-id="93d04-278">Definition</span></span>

<span data-ttu-id="93d04-279">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="93d04-279">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="93d04-280">La expresión regular `Regex_latvia_eu_telephone_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="93d04-280">The regular expression  `Regex_latvia_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="93d04-281">Una palabra clave de `Keywords_latvia_eu_telephone_number` se encuentra.</span><span class="sxs-lookup"><span data-stu-id="93d04-281">A keyword from  `Keywords_latvia_eu_telephone_number` is found.</span></span> 
    
<span data-ttu-id="93d04-282">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="93d04-282">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="93d04-283">La expresión regular `Regex_latvia_eu_telephone_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="93d04-283">The regular expression  `Regex_latvia_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_telephone_number" />
          <Match idRef="Keywords_latvia_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_latvia_eu_formatted_telephone_number" />
          </Pattern>
          </Entity>
```

## <a name="lithuania"></a><span data-ttu-id="93d04-284">Lituania</span><span class="sxs-lookup"><span data-stu-id="93d04-284">Lithuania</span></span>

### <a name="pattern"></a><span data-ttu-id="93d04-285">Patrón</span><span class="sxs-lookup"><span data-stu-id="93d04-285">Pattern</span></span>

- <span data-ttu-id="93d04-286">Dígitos</span><span class="sxs-lookup"><span data-stu-id="93d04-286">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="93d04-287">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="93d04-287">Checksum</span></span>

<span data-ttu-id="93d04-288">No aplicable</span><span class="sxs-lookup"><span data-stu-id="93d04-288">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="93d04-289">Definición</span><span class="sxs-lookup"><span data-stu-id="93d04-289">Definition</span></span>

<span data-ttu-id="93d04-290">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="93d04-290">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="93d04-291">La expresión regular `Regex_lithuania_eu_telephone_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="93d04-291">The regular expression  `Regex_lithuania_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="93d04-292">Una palabra clave de `Keywords_lithuania_eu_telephone_number` se encuentra.</span><span class="sxs-lookup"><span data-stu-id="93d04-292">A keyword from  `Keywords_lithuania_eu_telephone_number` is found.</span></span> 
    
<span data-ttu-id="93d04-293">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="93d04-293">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="93d04-294">La expresión regular `Regex_lithuania_eu_telephone_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="93d04-294">The regular expression  `Regex_lithuania_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_telephone_number" />
          <Match idRef="Keywords_lithuania_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_lithuania_eu_formatted_telephone_number" />
          </Pattern>
          </Entity>
```

## <a name="luxemburg"></a><span data-ttu-id="93d04-295">Luxemburgo</span><span class="sxs-lookup"><span data-stu-id="93d04-295">Luxemburg</span></span>

### <a name="pattern"></a><span data-ttu-id="93d04-296">Patrón</span><span class="sxs-lookup"><span data-stu-id="93d04-296">Pattern</span></span>

- <span data-ttu-id="93d04-297">Dígitos</span><span class="sxs-lookup"><span data-stu-id="93d04-297">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="93d04-298">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="93d04-298">Checksum</span></span>

<span data-ttu-id="93d04-299">No aplicable</span><span class="sxs-lookup"><span data-stu-id="93d04-299">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="93d04-300">Definición</span><span class="sxs-lookup"><span data-stu-id="93d04-300">Definition</span></span>

<span data-ttu-id="93d04-301">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="93d04-301">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="93d04-302">La expresión regular `Regex_luxemburg_eu_telephone_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="93d04-302">The regular expression  `Regex_luxemburg_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="93d04-303">Una palabra clave de `Keywords_luxemburg_eu_telephone_number` se encuentra.</span><span class="sxs-lookup"><span data-stu-id="93d04-303">A keyword from  `Keywords_luxemburg_eu_telephone_number` is found.</span></span> 
    
<span data-ttu-id="93d04-304">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="93d04-304">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="93d04-305">La expresión regular `Regex_luxemburg_eu_telephone_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="93d04-305">The regular expression  `Regex_luxemburg_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_luxemburg_eu_telephone_number" />
          <Match idRef="Keywords_luxemburg_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_luxemburg_eu_formatted_telephone_number" />
                  </Pattern>
</Entity>
```

## <a name="malta"></a><span data-ttu-id="93d04-306">Malta</span><span class="sxs-lookup"><span data-stu-id="93d04-306">Malta</span></span>

### <a name="pattern"></a><span data-ttu-id="93d04-307">Patrón</span><span class="sxs-lookup"><span data-stu-id="93d04-307">Pattern</span></span>

- <span data-ttu-id="93d04-308">Dígitos</span><span class="sxs-lookup"><span data-stu-id="93d04-308">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="93d04-309">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="93d04-309">Checksum</span></span>

<span data-ttu-id="93d04-310">No aplicable</span><span class="sxs-lookup"><span data-stu-id="93d04-310">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="93d04-311">Definición</span><span class="sxs-lookup"><span data-stu-id="93d04-311">Definition</span></span>

<span data-ttu-id="93d04-312">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="93d04-312">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="93d04-313">La expresión regular `Regex_malta_eu_telephone_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="93d04-313">The regular expression  `Regex_malta_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="93d04-314">Una palabra clave de `Keywords_malta_eu_telephone_number` se encuentra.</span><span class="sxs-lookup"><span data-stu-id="93d04-314">A keyword from  `Keywords_malta_eu_telephone_number` is found.</span></span> 
    
<span data-ttu-id="93d04-315">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="93d04-315">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="93d04-316">La expresión regular `Regex_malta_eu_telephone_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="93d04-316">The regular expression  `Regex_malta_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_telephone_number" />
          <Match idRef="Keywords_malta_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_malta_eu_formatted_telephone_number" />
            </Pattern>
</Entity>
```

## <a name="netherlands"></a><span data-ttu-id="93d04-317">Países Bajos</span><span class="sxs-lookup"><span data-stu-id="93d04-317">Netherlands</span></span>

### <a name="pattern"></a><span data-ttu-id="93d04-318">Patrón</span><span class="sxs-lookup"><span data-stu-id="93d04-318">Pattern</span></span>

- <span data-ttu-id="93d04-319">Dígitos</span><span class="sxs-lookup"><span data-stu-id="93d04-319">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="93d04-320">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="93d04-320">Checksum</span></span>

<span data-ttu-id="93d04-321">No aplicable</span><span class="sxs-lookup"><span data-stu-id="93d04-321">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="93d04-322">Definición</span><span class="sxs-lookup"><span data-stu-id="93d04-322">Definition</span></span>

<span data-ttu-id="93d04-323">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="93d04-323">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="93d04-324">La expresión regular `Regex_netherlands_eu_telephone_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="93d04-324">The regular expression  `Regex_netherlands_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="93d04-325">Una palabra clave de `Keywords_netherlands_eu_telephone_number` se encuentra.</span><span class="sxs-lookup"><span data-stu-id="93d04-325">A keyword from  `Keywords_netherlands_eu_telephone_number` is found.</span></span> 
    
<span data-ttu-id="93d04-326">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="93d04-326">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="93d04-327">La expresión regular `Regex_netherlands_eu_telephone_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="93d04-327">The regular expression  `Regex_netherlands_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_telephone_number" />
          <Match idRef="Keywords_netherlands_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_netherlands_eu_formatted_telephone_number" />
            </Pattern>
</Entity>
```

## <a name="poland"></a><span data-ttu-id="93d04-328">Polonia</span><span class="sxs-lookup"><span data-stu-id="93d04-328">Poland</span></span>

### <a name="pattern"></a><span data-ttu-id="93d04-329">Patrón</span><span class="sxs-lookup"><span data-stu-id="93d04-329">Pattern</span></span>

- <span data-ttu-id="93d04-330">Dígitos</span><span class="sxs-lookup"><span data-stu-id="93d04-330">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="93d04-331">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="93d04-331">Checksum</span></span>

<span data-ttu-id="93d04-332">No aplicable</span><span class="sxs-lookup"><span data-stu-id="93d04-332">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="93d04-333">Definición</span><span class="sxs-lookup"><span data-stu-id="93d04-333">Definition</span></span>

<span data-ttu-id="93d04-334">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="93d04-334">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="93d04-335">La expresión regular `Regex_poland_eu_telephone_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="93d04-335">The regular expression  `Regex_poland_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="93d04-336">Una palabra clave de `Keywords_poland_eu_telephone_number` se encuentra.</span><span class="sxs-lookup"><span data-stu-id="93d04-336">A keyword from  `Keywords_poland_eu_telephone_number` is found.</span></span> 
    
<span data-ttu-id="93d04-337">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="93d04-337">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="93d04-338">La expresión regular `Regex_poland_eu_telephone_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="93d04-338">The regular expression  `Regex_poland_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_poland_eu_telephone_number" />
          <Match idRef="Keywords_poland_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_poland_eu_formatted_telephone_number" />
             </Pattern>
</Entity>
```

## <a name="portugal"></a><span data-ttu-id="93d04-339">Portugal</span><span class="sxs-lookup"><span data-stu-id="93d04-339">Portugal</span></span>

### <a name="pattern"></a><span data-ttu-id="93d04-340">Patrón</span><span class="sxs-lookup"><span data-stu-id="93d04-340">Pattern</span></span>

- <span data-ttu-id="93d04-341">Dígitos</span><span class="sxs-lookup"><span data-stu-id="93d04-341">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="93d04-342">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="93d04-342">Checksum</span></span>

<span data-ttu-id="93d04-343">No aplicable</span><span class="sxs-lookup"><span data-stu-id="93d04-343">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="93d04-344">Definición</span><span class="sxs-lookup"><span data-stu-id="93d04-344">Definition</span></span>

<span data-ttu-id="93d04-345">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="93d04-345">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="93d04-346">La expresión regular `Regex_portugal_eu_telephone_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="93d04-346">The regular expression  `Regex_portugal_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="93d04-347">Una palabra clave de `Keywords_portugal_eu_telephone_number` se encuentra.</span><span class="sxs-lookup"><span data-stu-id="93d04-347">A keyword from  `Keywords_portugal_eu_telephone_number` is found.</span></span> 
    
<span data-ttu-id="93d04-348">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="93d04-348">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="93d04-349">La expresión regular `Regex_portugal_eu_telephone_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="93d04-349">The regular expression  `Regex_portugal_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_telephone_number" />
          <Match idRef="Keywords_portugal_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_portugal_eu_formatted_telephone_number" />
          </Pattern>
        </Entity>
```

## <a name="romania"></a><span data-ttu-id="93d04-350">Rumania</span><span class="sxs-lookup"><span data-stu-id="93d04-350">Romania</span></span>

### <a name="pattern"></a><span data-ttu-id="93d04-351">Patrón</span><span class="sxs-lookup"><span data-stu-id="93d04-351">Pattern</span></span>

- <span data-ttu-id="93d04-352">Dígitos</span><span class="sxs-lookup"><span data-stu-id="93d04-352">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="93d04-353">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="93d04-353">Checksum</span></span>

<span data-ttu-id="93d04-354">No aplicable</span><span class="sxs-lookup"><span data-stu-id="93d04-354">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="93d04-355">Definición</span><span class="sxs-lookup"><span data-stu-id="93d04-355">Definition</span></span>

<span data-ttu-id="93d04-356">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="93d04-356">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="93d04-357">La expresión regular `Regex_romania_eu_telephone_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="93d04-357">The regular expression  `Regex_romania_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="93d04-358">Una palabra clave de `Keywords_romania_eu_telephone_number` se encuentra.</span><span class="sxs-lookup"><span data-stu-id="93d04-358">A keyword from  `Keywords_romania_eu_telephone_number` is found.</span></span> 
    
<span data-ttu-id="93d04-359">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="93d04-359">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="93d04-360">La expresión regular `Regex_romania_eu_telephone_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="93d04-360">The regular expression  `Regex_romania_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_telephone_number" />
          <Match idRef="Keywords_romania_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_romania_eu_formatted_telephone_number" />
            </Pattern>
</Entity>
```

## <a name="slovakia"></a><span data-ttu-id="93d04-361">Eslovaquia</span><span class="sxs-lookup"><span data-stu-id="93d04-361">Slovakia</span></span>

### <a name="pattern"></a><span data-ttu-id="93d04-362">Patrón</span><span class="sxs-lookup"><span data-stu-id="93d04-362">Pattern</span></span>

- <span data-ttu-id="93d04-363">Dígitos</span><span class="sxs-lookup"><span data-stu-id="93d04-363">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="93d04-364">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="93d04-364">Checksum</span></span>

<span data-ttu-id="93d04-365">No aplicable</span><span class="sxs-lookup"><span data-stu-id="93d04-365">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="93d04-366">Definición</span><span class="sxs-lookup"><span data-stu-id="93d04-366">Definition</span></span>

<span data-ttu-id="93d04-367">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="93d04-367">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="93d04-368">La expresión regular `Regex_slovakia_eu_telephone_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="93d04-368">The regular expression  `Regex_slovakia_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="93d04-369">Una palabra clave de `Keywords_slovakia_eu_telephone_number` se encuentra.</span><span class="sxs-lookup"><span data-stu-id="93d04-369">A keyword from  `Keywords_slovakia_eu_telephone_number` is found.</span></span> 
    
<span data-ttu-id="93d04-370">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="93d04-370">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="93d04-371">La expresión regular `Regex_slovakia_eu_telephone_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="93d04-371">The regular expression  `Regex_slovakia_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_telephone_number" />
          <Match idRef="Keywords_slovakia_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_slovakia_eu_formatted_telephone_number" />
            </Pattern>
</Entity>
```

## <a name="slovenia"></a><span data-ttu-id="93d04-372">Eslovenia</span><span class="sxs-lookup"><span data-stu-id="93d04-372">Slovenia</span></span>

### <a name="pattern"></a><span data-ttu-id="93d04-373">Patrón</span><span class="sxs-lookup"><span data-stu-id="93d04-373">Pattern</span></span>

- <span data-ttu-id="93d04-374">Dígitos</span><span class="sxs-lookup"><span data-stu-id="93d04-374">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="93d04-375">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="93d04-375">Checksum</span></span>

<span data-ttu-id="93d04-376">No aplicable</span><span class="sxs-lookup"><span data-stu-id="93d04-376">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="93d04-377">Definición</span><span class="sxs-lookup"><span data-stu-id="93d04-377">Definition</span></span>

<span data-ttu-id="93d04-378">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="93d04-378">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="93d04-379">La expresión regular `Regex_slovenia_eu_telephone_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="93d04-379">The regular expression  `Regex_slovenia_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="93d04-380">Una palabra clave de `Keywords_slovenia_eu_telephone_number` se encuentra.</span><span class="sxs-lookup"><span data-stu-id="93d04-380">A keyword from  `Keywords_slovenia_eu_telephone_number` is found.</span></span> 
    
<span data-ttu-id="93d04-381">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="93d04-381">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="93d04-382">La expresión regular `Regex_slovenia_eu_telephone_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="93d04-382">The regular expression  `Regex_slovenia_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_telephone_number" />
          <Match idRef="Keywords_slovenia_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_slovenia_eu_formatted_telephone_number" />
          </Pattern>
          </Entity>
```

## <a name="spain"></a><span data-ttu-id="93d04-383">España</span><span class="sxs-lookup"><span data-stu-id="93d04-383">Spain</span></span>

### <a name="pattern"></a><span data-ttu-id="93d04-384">Patrón</span><span class="sxs-lookup"><span data-stu-id="93d04-384">Pattern</span></span>

- <span data-ttu-id="93d04-385">Dígitos</span><span class="sxs-lookup"><span data-stu-id="93d04-385">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="93d04-386">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="93d04-386">Checksum</span></span>

<span data-ttu-id="93d04-387">No aplicable</span><span class="sxs-lookup"><span data-stu-id="93d04-387">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="93d04-388">Definición</span><span class="sxs-lookup"><span data-stu-id="93d04-388">Definition</span></span>

<span data-ttu-id="93d04-389">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="93d04-389">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="93d04-390">La expresión regular `Regex_spain_eu_telephone_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="93d04-390">The regular expression  `Regex_spain_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="93d04-391">Una palabra clave de `Keywords_spain_eu_telephone_number` se encuentra.</span><span class="sxs-lookup"><span data-stu-id="93d04-391">A keyword from  `Keywords_spain_eu_telephone_number` is found.</span></span> 
    
<span data-ttu-id="93d04-392">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="93d04-392">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="93d04-393">La expresión regular `Regex_spain_eu_telephone_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="93d04-393">The regular expression  `Regex_spain_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_spain_eu_telephone_number" />
          <Match idRef="Keywords_spain_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_spain_eu_formatted_telephone_number" />
          </Pattern>
          </Entity>
```

## <a name="sweden"></a><span data-ttu-id="93d04-394">Suecia</span><span class="sxs-lookup"><span data-stu-id="93d04-394">Sweden</span></span>

### <a name="pattern"></a><span data-ttu-id="93d04-395">Patrón</span><span class="sxs-lookup"><span data-stu-id="93d04-395">Pattern</span></span>

- <span data-ttu-id="93d04-396">Dígitos</span><span class="sxs-lookup"><span data-stu-id="93d04-396">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="93d04-397">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="93d04-397">Checksum</span></span>

<span data-ttu-id="93d04-398">No aplicable</span><span class="sxs-lookup"><span data-stu-id="93d04-398">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="93d04-399">Definición</span><span class="sxs-lookup"><span data-stu-id="93d04-399">Definition</span></span>

<span data-ttu-id="93d04-400">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="93d04-400">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="93d04-401">La expresión regular `Regex_sweden_eu_telephone_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="93d04-401">The regular expression  `Regex_sweden_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="93d04-402">Una palabra clave de `Keywords_sweden_eu_telephone_number` se encuentra.</span><span class="sxs-lookup"><span data-stu-id="93d04-402">A keyword from  `Keywords_sweden_eu_telephone_number` is found.</span></span> 
    
<span data-ttu-id="93d04-403">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="93d04-403">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="93d04-404">La expresión regular `Regex_sweden_eu_telephone_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="93d04-404">The regular expression  `Regex_sweden_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_sweden_eu_telephone_number" />
          <Match idRef="Keywords_sweden_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_sweden_eu_formatted_telephone_number" />
          </Pattern>
          </Entity>
```

## <a name="uk"></a><span data-ttu-id="93d04-405">REINO UNIDO</span><span class="sxs-lookup"><span data-stu-id="93d04-405">UK</span></span>

### <a name="pattern"></a><span data-ttu-id="93d04-406">Patrón</span><span class="sxs-lookup"><span data-stu-id="93d04-406">Pattern</span></span>

- <span data-ttu-id="93d04-407">Dígitos</span><span class="sxs-lookup"><span data-stu-id="93d04-407">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="93d04-408">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="93d04-408">Checksum</span></span>

<span data-ttu-id="93d04-409">No aplicable</span><span class="sxs-lookup"><span data-stu-id="93d04-409">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="93d04-410">Definición</span><span class="sxs-lookup"><span data-stu-id="93d04-410">Definition</span></span>

<span data-ttu-id="93d04-411">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="93d04-411">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="93d04-412">La expresión regular `Regex_uk_eu_telephone_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="93d04-412">The regular expression  `Regex_uk_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="93d04-413">Una palabra clave de `Keywords_uk_eu_telephone_number` se encuentra.</span><span class="sxs-lookup"><span data-stu-id="93d04-413">A keyword from  `Keywords_uk_eu_telephone_number` is found.</span></span> 
    
<span data-ttu-id="93d04-414">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="93d04-414">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="93d04-415">La expresión regular `Regex_uk_eu_telephone_number` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="93d04-415">The regular expression  `Regex_uk_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_uk_eu_telephone_number" />
          <Match idRef="Keywords_uk_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_uk_eu_formatted_telephone_number" />
            </Pattern>
</Entity>
```

## <a name="see-also"></a><span data-ttu-id="93d04-416">Vea también</span><span class="sxs-lookup"><span data-stu-id="93d04-416">See also</span></span>

[<span data-ttu-id="93d04-417">Qué buscan los tipos de información confidencial</span><span class="sxs-lookup"><span data-stu-id="93d04-417">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

