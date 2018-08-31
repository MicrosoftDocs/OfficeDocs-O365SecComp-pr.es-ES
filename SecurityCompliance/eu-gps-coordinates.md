---
title: Coordenadas de GPS de la UE
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/14/2018
ms.audience: Admin
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
ms.assetid: fdf2aebc-d5a4-4138-b10f-4a81dd70415a
description: Prevención de pérdida de datos (DLP) en la seguridad de Office 365 &amp; centro de cumplimiento incluye muchos tipos de información confidencial que están listos para su uso en las directivas de DLP. En este tema se describe el tipo de información confidencial coordenadas de GPS de la UE.
ms.openlocfilehash: 89fb8420e479b9f793fc2be9aa3a9a9fd5741691
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22536114"
---
# <a name="eu-gps-coordinates"></a><span data-ttu-id="95662-104">Coordenadas de GPS de la UE</span><span class="sxs-lookup"><span data-stu-id="95662-104">EU GPS Coordinates</span></span>

<span data-ttu-id="95662-p102">Prevención de pérdida de datos (DLP) en la seguridad de Office 365 &amp; centro de cumplimiento incluye muchos tipos de información confidencial que están listos para su uso en las directivas de DLP. En este tema se describe el tipo de información confidencial coordenadas de GPS de la UE.</span><span class="sxs-lookup"><span data-stu-id="95662-p102">Data loss prevention (DLP) in the Office 365 Security &amp; Compliance Center includes many sensitive information types that are ready for you to use in your DLP policies. This topic describes the EU GPS Coordinates sensitive information type.</span></span>
  
## <a name="austria"></a><span data-ttu-id="95662-107">Austria</span><span class="sxs-lookup"><span data-stu-id="95662-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="95662-108">Formato</span><span class="sxs-lookup"><span data-stu-id="95662-108">Format</span></span>

<span data-ttu-id="95662-109">Coordina para ciudades en Austria se encuentran en el intervalo: latitud de 46.526 a 48.816 y longitud de 9,6 a 16.945.</span><span class="sxs-lookup"><span data-stu-id="95662-109">Coordinates for cities in Austria are in range: Latitude from 46.526 to 48.816 and longitude from 9.6 to 16.945.</span></span>
  
### <a name="pattern"></a><span data-ttu-id="95662-110">Patrón</span><span class="sxs-lookup"><span data-stu-id="95662-110">Pattern</span></span>

<span data-ttu-id="95662-111">Para cada coordenada, la combinación de hasta 6 dígitos y un separador decimal.</span><span class="sxs-lookup"><span data-stu-id="95662-111">For each coordinate, combination of up to 6 digits and a decimal point.</span></span>
  
- <span data-ttu-id="95662-112">Hasta 6 dígitos</span><span class="sxs-lookup"><span data-stu-id="95662-112">Up to 6 digits</span></span>
    
- <span data-ttu-id="95662-113">Un punto decimal después de la primera o segunda dígitos.</span><span class="sxs-lookup"><span data-stu-id="95662-113">A decimal point after first or second digit.</span></span>
    
### <a name="checksum"></a><span data-ttu-id="95662-114">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="95662-114">Checksum</span></span>

<span data-ttu-id="95662-115">No aplicable</span><span class="sxs-lookup"><span data-stu-id="95662-115">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="95662-116">Definición</span><span class="sxs-lookup"><span data-stu-id="95662-116">Definition</span></span>

<span data-ttu-id="95662-117">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="95662-117">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="95662-118">La expresión regular `Regex_austria_eu_gps_data_1` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="95662-118">The regular expression  `Regex_austria_eu_gps_data_1` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="95662-119">Una palabra clave de `Keywords_austria_eu_gps_data` se encuentra.</span><span class="sxs-lookup"><span data-stu-id="95662-119">A keyword from  `Keywords_austria_eu_gps_data` is found.</span></span> 
    
<span data-ttu-id="95662-120">Una directiva DLP está segura al 65% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="95662-120">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="95662-121">La expresión regular `Regex_austria_eu_gps_data_1` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="95662-121">The regular expression  `Regex_austria_eu_gps_data_1` finds content that matches the pattern.</span></span> 
    
<span data-ttu-id="95662-122">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="95662-122">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="95662-123">La expresión regular `Regex_austria_eu_gps_data_2` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="95662-123">The regular expression  `Regex_austria_eu_gps_data_2` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="95662-124">Una palabra clave de `Keywords_austria_eu_gps_data` se encuentra.</span><span class="sxs-lookup"><span data-stu-id="95662-124">A keyword from  `Keywords_austria_eu_gps_data` is found.</span></span> 
    
<span data-ttu-id="95662-125">Una directiva DLP está segura al 65% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="95662-125">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="95662-126">La expresión regular `Regex_austria_eu_gps_data_2` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="95662-126">The regular expression  `Regex_austria_eu_gps_data_2` finds content that matches the pattern.</span></span> 
    
```
 
<Entity id="42ac9f40-0912-4ae3-b5e6-08967192dec0" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_gps_data_1" />
          <Match idRef="Keywords_austria_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_austria_eu_gps_data_1" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_gps_data_2" />
          <Match idRef="Keywords_austria_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_austria_eu_gps_data_2" />
        </Pattern>

```

### <a name="keywords"></a><span data-ttu-id="95662-127">Keywords</span><span class="sxs-lookup"><span data-stu-id="95662-127">Keywords</span></span>

#### <a name="keywordsaustriaeugpsdata"></a><span data-ttu-id="95662-128">Keywords_austria_eu_gps_data</span><span class="sxs-lookup"><span data-stu-id="95662-128">Keywords_austria_eu_gps_data</span></span>

<span data-ttu-id="95662-129">Rastreador de GPS</span><span class="sxs-lookup"><span data-stu-id="95662-129">gps tracker</span></span>
  
<span data-ttu-id="95662-130">coordenadas de GPS</span><span class="sxs-lookup"><span data-stu-id="95662-130">gps coordinates</span></span>
  
<span data-ttu-id="95662-131">ubicación</span><span class="sxs-lookup"><span data-stu-id="95662-131">location</span></span>
  
<span data-ttu-id="95662-132">asignar</span><span class="sxs-lookup"><span data-stu-id="95662-132">map</span></span>
  
<span data-ttu-id="95662-133">latitud</span><span class="sxs-lookup"><span data-stu-id="95662-133">latitude</span></span>
  
<span data-ttu-id="95662-134">latitud</span><span class="sxs-lookup"><span data-stu-id="95662-134">longitude</span></span>
  
<span data-ttu-id="95662-135">Rastreador de GPS</span><span class="sxs-lookup"><span data-stu-id="95662-135">GPS-Tracker</span></span>
  
<span data-ttu-id="95662-136">GPS Koordinaten</span><span class="sxs-lookup"><span data-stu-id="95662-136">GPS-Koordinaten</span></span>
  
<span data-ttu-id="95662-137">Standort Karte</span><span class="sxs-lookup"><span data-stu-id="95662-137">Standort Karte</span></span>
  
<span data-ttu-id="95662-138">Breitengrad</span><span class="sxs-lookup"><span data-stu-id="95662-138">Breitengrad</span></span>
  
<span data-ttu-id="95662-139">Längengrad</span><span class="sxs-lookup"><span data-stu-id="95662-139">Längengrad</span></span>
  
## <a name="belgium"></a><span data-ttu-id="95662-140">Bélgica</span><span class="sxs-lookup"><span data-stu-id="95662-140">Belgium</span></span>

### <a name="pattern"></a><span data-ttu-id="95662-141">Patrón</span><span class="sxs-lookup"><span data-stu-id="95662-141">Pattern</span></span>

-  <span data-ttu-id="95662-142">dígitos</span><span class="sxs-lookup"><span data-stu-id="95662-142">digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="95662-143">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="95662-143">Checksum</span></span>

<span data-ttu-id="95662-144">No aplicable</span><span class="sxs-lookup"><span data-stu-id="95662-144">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="95662-145">Definición</span><span class="sxs-lookup"><span data-stu-id="95662-145">Definition</span></span>

<span data-ttu-id="95662-146">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="95662-146">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="95662-147">La expresión regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="95662-147">The regular expression finds content that matches the pattern.</span></span>
    
- <span data-ttu-id="95662-148">Se ha encontrado una palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="95662-148">A keyword from is found.</span></span>
    
```
 
<Entity id="42ac9f40-0912-4ae3-b5e6-08967192dec0" patternsProximity="300" recommendedConfidence="75>">
<Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_gps_data_1" />
          <Match idRef="Keywords_belgium_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_belgium_eu_gps_data_1" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_gps_data_2" />
          <Match idRef="Keywords_belgium_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_belgium_eu_gps_data_2" />
        </Pattern>
</Entity>
```

## <a name="bulgaria"></a><span data-ttu-id="95662-149">Bulgaria</span><span class="sxs-lookup"><span data-stu-id="95662-149">Bulgaria</span></span>

### <a name="pattern"></a><span data-ttu-id="95662-150">Patrón</span><span class="sxs-lookup"><span data-stu-id="95662-150">Pattern</span></span>

-  <span data-ttu-id="95662-151">dígitos</span><span class="sxs-lookup"><span data-stu-id="95662-151">digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="95662-152">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="95662-152">Checksum</span></span>

<span data-ttu-id="95662-153">No aplicable</span><span class="sxs-lookup"><span data-stu-id="95662-153">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="95662-154">Definición</span><span class="sxs-lookup"><span data-stu-id="95662-154">Definition</span></span>

<span data-ttu-id="95662-155">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="95662-155">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="95662-156">La expresión regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="95662-156">The regular expression finds content that matches the pattern.</span></span>
    
- <span data-ttu-id="95662-157">Se ha encontrado una palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="95662-157">A keyword from is found.</span></span>
    
```
<Entity id="42ac9f40-0912-4ae3-b5e6-08967192dec0" patternsProximity="300" recommendedConfidence="75>
</Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_belgium_eu_gps_data_2" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_gps_data_1" />
          <Match idRef="Keywords_bulgaria_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_bulgaria_eu_gps_data_1" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_gps_data_2" />
          <Match idRef="Keywords_bulgaria_eu_gps_data" />
        </Pattern>
</Entity>
```

## <a name="croatia"></a><span data-ttu-id="95662-158">Croacia</span><span class="sxs-lookup"><span data-stu-id="95662-158">Croatia</span></span>

### <a name="pattern"></a><span data-ttu-id="95662-159">Patrón</span><span class="sxs-lookup"><span data-stu-id="95662-159">Pattern</span></span>

-  <span data-ttu-id="95662-160">dígitos</span><span class="sxs-lookup"><span data-stu-id="95662-160">digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="95662-161">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="95662-161">Checksum</span></span>

<span data-ttu-id="95662-162">No aplicable</span><span class="sxs-lookup"><span data-stu-id="95662-162">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="95662-163">Definición</span><span class="sxs-lookup"><span data-stu-id="95662-163">Definition</span></span>

<span data-ttu-id="95662-164">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="95662-164">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="95662-165">La expresión regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="95662-165">The regular expression finds content that matches the pattern.</span></span>
    
- <span data-ttu-id="95662-166">Se ha encontrado una palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="95662-166">A keyword from is found.</span></span>
    
```
<Entity id="42ac9f40-0912-4ae3-b5e6-08967192dec0" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_gps_data_1" />
          <Match idRef="Keywords_croatia_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_croatia_eu_gps_data_1" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_gps_data_2" />
          <Match idRef="Keywords_croatia_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_croatia_eu_gps_data_2" />
        </Pattern>
</Entity>
```

## <a name="cyprus"></a><span data-ttu-id="95662-167">Chipre</span><span class="sxs-lookup"><span data-stu-id="95662-167">Cyprus</span></span>

### <a name="pattern"></a><span data-ttu-id="95662-168">Patrón</span><span class="sxs-lookup"><span data-stu-id="95662-168">Pattern</span></span>

-  <span data-ttu-id="95662-169">dígitos</span><span class="sxs-lookup"><span data-stu-id="95662-169">digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="95662-170">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="95662-170">Checksum</span></span>

<span data-ttu-id="95662-171">No aplicable</span><span class="sxs-lookup"><span data-stu-id="95662-171">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="95662-172">Definición</span><span class="sxs-lookup"><span data-stu-id="95662-172">Definition</span></span>

<span data-ttu-id="95662-173">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="95662-173">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="95662-174">La expresión regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="95662-174">The regular expression finds content that matches the pattern.</span></span>
    
- <span data-ttu-id="95662-175">Se ha encontrado una palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="95662-175">A keyword from is found.</span></span>
    
```
 
<Entity id="42ac9f40-0912-4ae3-b5e6-08967192dec0" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_gps_data_1" />
          <Match idRef="Keywords_cyprus_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_cyprus_eu_gps_data_1" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_gps_data_2" />
          <Match idRef="Keywords_cyprus_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_cyprus_eu_gps_data_2" />
        </Pattern>
</Entity>
```

## <a name="czech-republic"></a><span data-ttu-id="95662-176">República Checa</span><span class="sxs-lookup"><span data-stu-id="95662-176">Czech Republic</span></span>

### <a name="pattern"></a><span data-ttu-id="95662-177">Patrón</span><span class="sxs-lookup"><span data-stu-id="95662-177">Pattern</span></span>

-  <span data-ttu-id="95662-178">dígitos</span><span class="sxs-lookup"><span data-stu-id="95662-178">digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="95662-179">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="95662-179">Checksum</span></span>

<span data-ttu-id="95662-180">No aplicable</span><span class="sxs-lookup"><span data-stu-id="95662-180">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="95662-181">Definición</span><span class="sxs-lookup"><span data-stu-id="95662-181">Definition</span></span>

<span data-ttu-id="95662-182">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="95662-182">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
<span data-ttu-id="95662-183">Una directiva de DLP es % seguro de que ha detectado este tipo de información confidencial if, dentro de una proximidad de caracteres:</span><span class="sxs-lookup"><span data-stu-id="95662-183">A DLP policy is % confident that it's detected this type of sensitive information if, within a proximity of characters:</span></span>
  
- <span data-ttu-id="95662-184">La expresión regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="95662-184">The regular expression finds content that matches the pattern.</span></span>
    
- <span data-ttu-id="95662-185">Se ha encontrado una palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="95662-185">A keyword from is found.</span></span>
    
```
 
<Entity id="42ac9f40-0912-4ae3-b5e6-08967192dec0" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_gps_data_1" />
          <Match idRef="Keywords_czech_republic_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_czech_republic_eu_gps_data_1" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_gps_data_2" />
          <Match idRef="Keywords_czech_republic_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_czech_republic_eu_gps_data_2" />
        </Pattern>
</Entity>
```

## <a name="denmark"></a><span data-ttu-id="95662-186">Dinamarca</span><span class="sxs-lookup"><span data-stu-id="95662-186">Denmark</span></span>

### <a name="pattern"></a><span data-ttu-id="95662-187">Patrón</span><span class="sxs-lookup"><span data-stu-id="95662-187">Pattern</span></span>

-  <span data-ttu-id="95662-188">dígitos</span><span class="sxs-lookup"><span data-stu-id="95662-188">digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="95662-189">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="95662-189">Checksum</span></span>

<span data-ttu-id="95662-190">No aplicable</span><span class="sxs-lookup"><span data-stu-id="95662-190">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="95662-191">Definición</span><span class="sxs-lookup"><span data-stu-id="95662-191">Definition</span></span>

<span data-ttu-id="95662-192">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="95662-192">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="95662-193">La expresión regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="95662-193">The regular expression finds content that matches the pattern.</span></span>
    
- <span data-ttu-id="95662-194">Se ha encontrado una palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="95662-194">A keyword from is found.</span></span>
    
```
 
<Entity id="42ac9f40-0912-4ae3-b5e6-08967192dec0" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_gps_data_1" />
          <Match idRef="Keywords_denmark_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_denmark_eu_gps_data_1" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_gps_data_2" />
          <Match idRef="Keywords_denmark_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_denmark_eu_gps_data_2" />
        </Pattern>
</Entity>
```

## <a name="estonia"></a><span data-ttu-id="95662-195">Estonia</span><span class="sxs-lookup"><span data-stu-id="95662-195">Estonia</span></span>

### <a name="pattern"></a><span data-ttu-id="95662-196">Patrón</span><span class="sxs-lookup"><span data-stu-id="95662-196">Pattern</span></span>

-  <span data-ttu-id="95662-197">dígitos</span><span class="sxs-lookup"><span data-stu-id="95662-197">digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="95662-198">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="95662-198">Checksum</span></span>

<span data-ttu-id="95662-199">No aplicable</span><span class="sxs-lookup"><span data-stu-id="95662-199">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="95662-200">Definición</span><span class="sxs-lookup"><span data-stu-id="95662-200">Definition</span></span>

<span data-ttu-id="95662-201">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="95662-201">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="95662-202">La expresión regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="95662-202">The regular expression finds content that matches the pattern.</span></span>
    
- <span data-ttu-id="95662-203">Se ha encontrado una palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="95662-203">A keyword from is found.</span></span>
    
```
 
<Entity id="42ac9f40-0912-4ae3-b5e6-08967192dec0" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_gps_data_1" />
          <Match idRef="Keywords_estonia_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_estonia_eu_gps_data_1" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_gps_data_2" />
          <Match idRef="Keywords_estonia_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_estonia_eu_gps_data_2" />
        </Pattern>
</Entity>
```

## <a name="finland"></a><span data-ttu-id="95662-204">Finlandia</span><span class="sxs-lookup"><span data-stu-id="95662-204">Finland</span></span>

### <a name="pattern"></a><span data-ttu-id="95662-205">Patrón</span><span class="sxs-lookup"><span data-stu-id="95662-205">Pattern</span></span>

-  <span data-ttu-id="95662-206">dígitos</span><span class="sxs-lookup"><span data-stu-id="95662-206">digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="95662-207">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="95662-207">Checksum</span></span>

<span data-ttu-id="95662-208">No aplicable</span><span class="sxs-lookup"><span data-stu-id="95662-208">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="95662-209">Definición</span><span class="sxs-lookup"><span data-stu-id="95662-209">Definition</span></span>

<span data-ttu-id="95662-210">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="95662-210">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="95662-211">La expresión regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="95662-211">The regular expression finds content that matches the pattern.</span></span>
    
- <span data-ttu-id="95662-212">Se ha encontrado una palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="95662-212">A keyword from is found.</span></span>
    
```
 
<Entity id="42ac9f40-0912-4ae3-b5e6-08967192dec0" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_finland_eu_gps_data_1" />
          <Match idRef="Keywords_finland_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_finland_eu_gps_data_1" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_finland_eu_gps_data_2" />
          <Match idRef="Keywords_finland_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_finland_eu_gps_data_2" />
        </Pattern>
</Entity>
```

## <a name="france"></a><span data-ttu-id="95662-213">Francia</span><span class="sxs-lookup"><span data-stu-id="95662-213">France</span></span>

### <a name="pattern"></a><span data-ttu-id="95662-214">Patrón</span><span class="sxs-lookup"><span data-stu-id="95662-214">Pattern</span></span>

-  <span data-ttu-id="95662-215">dígitos</span><span class="sxs-lookup"><span data-stu-id="95662-215">digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="95662-216">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="95662-216">Checksum</span></span>

<span data-ttu-id="95662-217">No aplicable</span><span class="sxs-lookup"><span data-stu-id="95662-217">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="95662-218">Definición</span><span class="sxs-lookup"><span data-stu-id="95662-218">Definition</span></span>

<span data-ttu-id="95662-219">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="95662-219">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="95662-220">La expresión regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="95662-220">The regular expression finds content that matches the pattern.</span></span>
    
- <span data-ttu-id="95662-221">Se ha encontrado una palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="95662-221">A keyword from is found.</span></span>
    
```
 
<Entity id="42ac9f40-0912-4ae3-b5e6-08967192dec0" patternsProximity="300" recommendedConfidence="75">
 <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_france_eu_gps_data_1" />
          <Match idRef="Keywords_france_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_france_eu_gps_data_1" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_france_eu_gps_data_2" />
          <Match idRef="Keywords_france_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_france_eu_gps_data_2" />
        </Pattern>
</Entity>
```

## <a name="germany"></a><span data-ttu-id="95662-222">Alemania</span><span class="sxs-lookup"><span data-stu-id="95662-222">Germany</span></span>

### <a name="pattern"></a><span data-ttu-id="95662-223">Patrón</span><span class="sxs-lookup"><span data-stu-id="95662-223">Pattern</span></span>

-  <span data-ttu-id="95662-224">dígitos</span><span class="sxs-lookup"><span data-stu-id="95662-224">digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="95662-225">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="95662-225">Checksum</span></span>

<span data-ttu-id="95662-226">No aplicable</span><span class="sxs-lookup"><span data-stu-id="95662-226">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="95662-227">Definición</span><span class="sxs-lookup"><span data-stu-id="95662-227">Definition</span></span>

<span data-ttu-id="95662-228">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="95662-228">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="95662-229">La expresión regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="95662-229">The regular expression finds content that matches the pattern.</span></span>
    
- <span data-ttu-id="95662-230">Se ha encontrado una palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="95662-230">A keyword from is found.</span></span>
    
```
 
<Entity id="42ac9f40-0912-4ae3-b5e6-08967192dec0" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_germany_eu_gps_data_1" />
          <Match idRef="Keywords_germany_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_germany_eu_gps_data_1" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_germany_eu_gps_data_2" />
          <Match idRef="Keywords_germany_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_germany_eu_gps_data_2" />
        </Pattern>
</Entity>
```

## <a name="greece"></a><span data-ttu-id="95662-231">Grecia</span><span class="sxs-lookup"><span data-stu-id="95662-231">Greece</span></span>

### <a name="pattern"></a><span data-ttu-id="95662-232">Patrón</span><span class="sxs-lookup"><span data-stu-id="95662-232">Pattern</span></span>

-  <span data-ttu-id="95662-233">dígitos</span><span class="sxs-lookup"><span data-stu-id="95662-233">digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="95662-234">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="95662-234">Checksum</span></span>

<span data-ttu-id="95662-235">No aplicable</span><span class="sxs-lookup"><span data-stu-id="95662-235">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="95662-236">Definición</span><span class="sxs-lookup"><span data-stu-id="95662-236">Definition</span></span>

<span data-ttu-id="95662-237">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="95662-237">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="95662-238">La expresión regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="95662-238">The regular expression finds content that matches the pattern.</span></span>
    
- <span data-ttu-id="95662-239">Se ha encontrado una palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="95662-239">A keyword from is found.</span></span>
    
```
 
<Entity id="42ac9f40-0912-4ae3-b5e6-08967192dec0" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_gps_data_1" />
          <Match idRef="Keywords_greece_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_greece_eu_gps_data_1" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_gps_data_2" />
          <Match idRef="Keywords_greece_eu_gps_data" />
        </Pattern>
</Entity>
```

## <a name="hungary"></a><span data-ttu-id="95662-240">Hungría</span><span class="sxs-lookup"><span data-stu-id="95662-240">Hungary</span></span>

### <a name="pattern"></a><span data-ttu-id="95662-241">Patrón</span><span class="sxs-lookup"><span data-stu-id="95662-241">Pattern</span></span>

-  <span data-ttu-id="95662-242">dígitos</span><span class="sxs-lookup"><span data-stu-id="95662-242">digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="95662-243">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="95662-243">Checksum</span></span>

<span data-ttu-id="95662-244">No aplicable</span><span class="sxs-lookup"><span data-stu-id="95662-244">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="95662-245">Definición</span><span class="sxs-lookup"><span data-stu-id="95662-245">Definition</span></span>

<span data-ttu-id="95662-246">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="95662-246">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="95662-247">La expresión regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="95662-247">The regular expression finds content that matches the pattern.</span></span>
    
- <span data-ttu-id="95662-248">Se ha encontrado una palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="95662-248">A keyword from is found.</span></span>
    
```
 
<Entity id="42ac9f40-0912-4ae3-b5e6-08967192dec0" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_gps_data_1" />
          <Match idRef="Keywords_hungary_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_hungary_eu_gps_data_1" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_gps_data_2" />
          <Match idRef="Keywords_hungary_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_hungary_eu_gps_data_2" />
        </Pattern>
</Entity>
```

## <a name="ireland"></a><span data-ttu-id="95662-249">Irlanda</span><span class="sxs-lookup"><span data-stu-id="95662-249">Ireland</span></span>

### <a name="pattern"></a><span data-ttu-id="95662-250">Patrón</span><span class="sxs-lookup"><span data-stu-id="95662-250">Pattern</span></span>

-  <span data-ttu-id="95662-251">dígitos</span><span class="sxs-lookup"><span data-stu-id="95662-251">digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="95662-252">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="95662-252">Checksum</span></span>

<span data-ttu-id="95662-253">No aplicable</span><span class="sxs-lookup"><span data-stu-id="95662-253">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="95662-254">Definición</span><span class="sxs-lookup"><span data-stu-id="95662-254">Definition</span></span>

<span data-ttu-id="95662-255">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="95662-255">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="95662-256">La expresión regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="95662-256">The regular expression finds content that matches the pattern.</span></span>
    
- <span data-ttu-id="95662-257">Se ha encontrado una palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="95662-257">A keyword from is found.</span></span>
    
```
 
<Entity id="42ac9f40-0912-4ae3-b5e6-08967192dec0" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_gps_data_1" />
          <Match idRef="Keywords_ireland_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_ireland_eu_gps_data_1" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_gps_data_2" />
          <Match idRef="Keywords_ireland_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_ireland_eu_gps_data_2" />
        </Pattern>
</Entity>
```

## <a name="italy"></a><span data-ttu-id="95662-258">Italia</span><span class="sxs-lookup"><span data-stu-id="95662-258">Italy</span></span>

### <a name="pattern"></a><span data-ttu-id="95662-259">Patrón</span><span class="sxs-lookup"><span data-stu-id="95662-259">Pattern</span></span>

-  <span data-ttu-id="95662-260">dígitos</span><span class="sxs-lookup"><span data-stu-id="95662-260">digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="95662-261">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="95662-261">Checksum</span></span>

<span data-ttu-id="95662-262">No aplicable</span><span class="sxs-lookup"><span data-stu-id="95662-262">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="95662-263">Definición</span><span class="sxs-lookup"><span data-stu-id="95662-263">Definition</span></span>

<span data-ttu-id="95662-264">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="95662-264">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="95662-265">La expresión regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="95662-265">The regular expression finds content that matches the pattern.</span></span>
    
- <span data-ttu-id="95662-266">Se ha encontrado una palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="95662-266">A keyword from is found.</span></span>
    
```
 <Entity id="42ac9f40-0912-4ae3-b5e6-08967192dec0" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_italy_eu_gps_data_1" />
          <Match idRef="Keywords_italy_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_italy_eu_gps_data_1" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_italy_eu_gps_data_2" />
          <Match idRef="Keywords_italy_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_italy_eu_gps_data_2" />
        </Pattern>
</Entity>
```

## <a name="latvia"></a><span data-ttu-id="95662-267">Letonia</span><span class="sxs-lookup"><span data-stu-id="95662-267">Latvia</span></span>

### <a name="pattern"></a><span data-ttu-id="95662-268">Patrón</span><span class="sxs-lookup"><span data-stu-id="95662-268">Pattern</span></span>

-  <span data-ttu-id="95662-269">dígitos</span><span class="sxs-lookup"><span data-stu-id="95662-269">digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="95662-270">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="95662-270">Checksum</span></span>

<span data-ttu-id="95662-271">No aplicable</span><span class="sxs-lookup"><span data-stu-id="95662-271">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="95662-272">Definición</span><span class="sxs-lookup"><span data-stu-id="95662-272">Definition</span></span>

<span data-ttu-id="95662-273">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="95662-273">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="95662-274">La expresión regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="95662-274">The regular expression finds content that matches the pattern.</span></span>
    
- <span data-ttu-id="95662-275">Se ha encontrado una palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="95662-275">A keyword from is found.</span></span>
    
```
 <Entity id="42ac9f40-0912-4ae3-b5e6-08967192dec0" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_gps_data_1" />
          <Match idRef="Keywords_latvia_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_latvia_eu_gps_data_1" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_gps_data_2" />
          <Match idRef="Keywords_latvia_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_latvia_eu_gps_data_2" />
        </Pattern>
</Entity>
```

## <a name="lithuania"></a><span data-ttu-id="95662-276">Lituania</span><span class="sxs-lookup"><span data-stu-id="95662-276">Lithuania</span></span>

### <a name="pattern"></a><span data-ttu-id="95662-277">Patrón</span><span class="sxs-lookup"><span data-stu-id="95662-277">Pattern</span></span>

-  <span data-ttu-id="95662-278">dígitos</span><span class="sxs-lookup"><span data-stu-id="95662-278">digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="95662-279">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="95662-279">Checksum</span></span>

<span data-ttu-id="95662-280">No aplicable</span><span class="sxs-lookup"><span data-stu-id="95662-280">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="95662-281">Definición</span><span class="sxs-lookup"><span data-stu-id="95662-281">Definition</span></span>

<span data-ttu-id="95662-282">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="95662-282">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="95662-283">La expresión regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="95662-283">The regular expression finds content that matches the pattern.</span></span>
    
- <span data-ttu-id="95662-284">Se ha encontrado una palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="95662-284">A keyword from is found.</span></span>
    
```
 <Entity id="42ac9f40-0912-4ae3-b5e6-08967192dec0" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_gps_data_1" />
          <Match idRef="Keywords_lithuania_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_lithuania_eu_gps_data_1" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_gps_data_2" />
          <Match idRef="Keywords_lithuania_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_lithuania_eu_gps_data_2" />
        </Pattern>
</Entity>
```

## <a name="luxemburg"></a><span data-ttu-id="95662-285">Luxemburgo</span><span class="sxs-lookup"><span data-stu-id="95662-285">Luxemburg</span></span>

### <a name="pattern"></a><span data-ttu-id="95662-286">Patrón</span><span class="sxs-lookup"><span data-stu-id="95662-286">Pattern</span></span>

-  <span data-ttu-id="95662-287">dígitos</span><span class="sxs-lookup"><span data-stu-id="95662-287">digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="95662-288">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="95662-288">Checksum</span></span>

<span data-ttu-id="95662-289">No aplicable</span><span class="sxs-lookup"><span data-stu-id="95662-289">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="95662-290">Definición</span><span class="sxs-lookup"><span data-stu-id="95662-290">Definition</span></span>

<span data-ttu-id="95662-291">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="95662-291">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="95662-292">La expresión regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="95662-292">The regular expression finds content that matches the pattern.</span></span>
    
- <span data-ttu-id="95662-293">Se ha encontrado una palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="95662-293">A keyword from is found.</span></span>
    
```
 <Entity id="42ac9f40-0912-4ae3-b5e6-08967192dec0" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_luxemburg_eu_gps_data_1" />
          <Match idRef="Keywords_luxemburg_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_luxemburg_eu_gps_data_1" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_luxemburg_eu_gps_data_2" />
          <Match idRef="Keywords_luxemburg_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_luxemburg_eu_gps_data_2" />
        </Pattern>
</Entity>
```

## <a name="malta"></a><span data-ttu-id="95662-294">Malta</span><span class="sxs-lookup"><span data-stu-id="95662-294">Malta</span></span>

### <a name="pattern"></a><span data-ttu-id="95662-295">Patrón</span><span class="sxs-lookup"><span data-stu-id="95662-295">Pattern</span></span>

-  <span data-ttu-id="95662-296">dígitos</span><span class="sxs-lookup"><span data-stu-id="95662-296">digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="95662-297">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="95662-297">Checksum</span></span>

<span data-ttu-id="95662-298">No aplicable</span><span class="sxs-lookup"><span data-stu-id="95662-298">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="95662-299">Definición</span><span class="sxs-lookup"><span data-stu-id="95662-299">Definition</span></span>

<span data-ttu-id="95662-300">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="95662-300">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="95662-301">La expresión regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="95662-301">The regular expression finds content that matches the pattern.</span></span>
    
- <span data-ttu-id="95662-302">Se ha encontrado una palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="95662-302">A keyword from is found.</span></span>
    
```
<Entity id="42ac9f40-0912-4ae3-b5e6-08967192dec0" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_gps_data_1" />
          <Match idRef="Keywords_malta_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_malta_eu_gps_data_1" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_gps_data_2" />
          <Match idRef="Keywords_malta_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_malta_eu_gps_data_2" />
        </Pattern>
</Entity>
```

## <a name="netherlands"></a><span data-ttu-id="95662-303">Países Bajos</span><span class="sxs-lookup"><span data-stu-id="95662-303">Netherlands</span></span>

### <a name="pattern"></a><span data-ttu-id="95662-304">Patrón</span><span class="sxs-lookup"><span data-stu-id="95662-304">Pattern</span></span>

-  <span data-ttu-id="95662-305">dígitos</span><span class="sxs-lookup"><span data-stu-id="95662-305">digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="95662-306">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="95662-306">Checksum</span></span>

<span data-ttu-id="95662-307">No aplicable</span><span class="sxs-lookup"><span data-stu-id="95662-307">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="95662-308">Definición</span><span class="sxs-lookup"><span data-stu-id="95662-308">Definition</span></span>

<span data-ttu-id="95662-309">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="95662-309">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="95662-310">La expresión regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="95662-310">The regular expression finds content that matches the pattern.</span></span>
    
- <span data-ttu-id="95662-311">Se ha encontrado una palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="95662-311">A keyword from is found.</span></span>
    
```
 <Entity id="42ac9f40-0912-4ae3-b5e6-08967192dec0" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_gps_data_1" />
          <Match idRef="Keywords_netherlands_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_netherlands_eu_gps_data_1" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_gps_data_2" />
          <Match idRef="Keywords_netherlands_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_netherlands_eu_gps_data_2" />
        </Pattern>
</Entity>
```

## <a name="poland"></a><span data-ttu-id="95662-312">Polonia</span><span class="sxs-lookup"><span data-stu-id="95662-312">Poland</span></span>

### <a name="pattern"></a><span data-ttu-id="95662-313">Patrón</span><span class="sxs-lookup"><span data-stu-id="95662-313">Pattern</span></span>

-  <span data-ttu-id="95662-314">dígitos</span><span class="sxs-lookup"><span data-stu-id="95662-314">digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="95662-315">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="95662-315">Checksum</span></span>

<span data-ttu-id="95662-316">No aplicable</span><span class="sxs-lookup"><span data-stu-id="95662-316">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="95662-317">Definición</span><span class="sxs-lookup"><span data-stu-id="95662-317">Definition</span></span>

<span data-ttu-id="95662-318">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="95662-318">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="95662-319">La expresión regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="95662-319">The regular expression finds content that matches the pattern.</span></span>
    
- <span data-ttu-id="95662-320">Se ha encontrado una palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="95662-320">A keyword from is found.</span></span>
    
```
 <Entity id="42ac9f40-0912-4ae3-b5e6-08967192dec0" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_poland_eu_gps_data_1" />
          <Match idRef="Keywords_poland_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_poland_eu_gps_data_1" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_poland_eu_gps_data_2" />
          <Match idRef="Keywords_poland_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_poland_eu_gps_data_2" />
        </Pattern>
</Entity>
```

## <a name="portugal"></a><span data-ttu-id="95662-321">Portugal</span><span class="sxs-lookup"><span data-stu-id="95662-321">Portugal</span></span>

### <a name="pattern"></a><span data-ttu-id="95662-322">Patrón</span><span class="sxs-lookup"><span data-stu-id="95662-322">Pattern</span></span>

-  <span data-ttu-id="95662-323">dígitos</span><span class="sxs-lookup"><span data-stu-id="95662-323">digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="95662-324">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="95662-324">Checksum</span></span>

<span data-ttu-id="95662-325">No aplicable</span><span class="sxs-lookup"><span data-stu-id="95662-325">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="95662-326">Definición</span><span class="sxs-lookup"><span data-stu-id="95662-326">Definition</span></span>

<span data-ttu-id="95662-327">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="95662-327">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="95662-328">La expresión regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="95662-328">The regular expression finds content that matches the pattern.</span></span>
    
- <span data-ttu-id="95662-329">Se ha encontrado una palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="95662-329">A keyword from is found.</span></span>
    
```
 <Entity id="42ac9f40-0912-4ae3-b5e6-08967192dec0" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_gps_data_1" />
          <Match idRef="Keywords_portugal_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_portugal_eu_gps_data_1" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_gps_data_2" />
          <Match idRef="Keywords_portugal_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_portugal_eu_gps_data_2" />
        </Pattern>
</Entity>
```

## <a name="romania"></a><span data-ttu-id="95662-330">Rumania</span><span class="sxs-lookup"><span data-stu-id="95662-330">Romania</span></span>

### <a name="pattern"></a><span data-ttu-id="95662-331">Patrón</span><span class="sxs-lookup"><span data-stu-id="95662-331">Pattern</span></span>

-  <span data-ttu-id="95662-332">dígitos</span><span class="sxs-lookup"><span data-stu-id="95662-332">digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="95662-333">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="95662-333">Checksum</span></span>

<span data-ttu-id="95662-334">No aplicable</span><span class="sxs-lookup"><span data-stu-id="95662-334">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="95662-335">Definición</span><span class="sxs-lookup"><span data-stu-id="95662-335">Definition</span></span>

<span data-ttu-id="95662-336">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="95662-336">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="95662-337">La expresión regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="95662-337">The regular expression finds content that matches the pattern.</span></span>
    
- <span data-ttu-id="95662-338">Se ha encontrado una palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="95662-338">A keyword from is found.</span></span>
    
```
 <Entity id="42ac9f40-0912-4ae3-b5e6-08967192dec0" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_gps_data_1" />
          <Match idRef="Keywords_romania_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_romania_eu_gps_data_1" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_gps_data_2" />
          <Match idRef="Keywords_romania_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_romania_eu_gps_data_2" />
        </Pattern>
</Entity>
```

## <a name="slovakia"></a><span data-ttu-id="95662-339">Eslovaquia</span><span class="sxs-lookup"><span data-stu-id="95662-339">Slovakia</span></span>

### <a name="pattern"></a><span data-ttu-id="95662-340">Patrón</span><span class="sxs-lookup"><span data-stu-id="95662-340">Pattern</span></span>

-  <span data-ttu-id="95662-341">dígitos</span><span class="sxs-lookup"><span data-stu-id="95662-341">digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="95662-342">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="95662-342">Checksum</span></span>

<span data-ttu-id="95662-343">No aplicable</span><span class="sxs-lookup"><span data-stu-id="95662-343">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="95662-344">Definición</span><span class="sxs-lookup"><span data-stu-id="95662-344">Definition</span></span>

<span data-ttu-id="95662-345">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="95662-345">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="95662-346">La expresión regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="95662-346">The regular expression finds content that matches the pattern.</span></span>
    
- <span data-ttu-id="95662-347">Se ha encontrado una palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="95662-347">A keyword from is found.</span></span>
    
```
 <Entity id="42ac9f40-0912-4ae3-b5e6-08967192dec0" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_gps_data_1" />
          <Match idRef="Keywords_slovakia_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_slovakia_eu_gps_data_1" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_gps_data_2" />
          <Match idRef="Keywords_slovakia_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_slovakia_eu_gps_data_2" />
        </Pattern>
</Entity>
```

## <a name="slovenia"></a><span data-ttu-id="95662-348">Eslovenia</span><span class="sxs-lookup"><span data-stu-id="95662-348">Slovenia</span></span>

### <a name="pattern"></a><span data-ttu-id="95662-349">Patrón</span><span class="sxs-lookup"><span data-stu-id="95662-349">Pattern</span></span>

-  <span data-ttu-id="95662-350">dígitos</span><span class="sxs-lookup"><span data-stu-id="95662-350">digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="95662-351">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="95662-351">Checksum</span></span>

<span data-ttu-id="95662-352">No aplicable</span><span class="sxs-lookup"><span data-stu-id="95662-352">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="95662-353">Definición</span><span class="sxs-lookup"><span data-stu-id="95662-353">Definition</span></span>

<span data-ttu-id="95662-354">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="95662-354">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="95662-355">La expresión regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="95662-355">The regular expression finds content that matches the pattern.</span></span>
    
- <span data-ttu-id="95662-356">Se ha encontrado una palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="95662-356">A keyword from is found.</span></span>
    
```
 <Entity id="42ac9f40-0912-4ae3-b5e6-08967192dec0" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_gps_data_1" />
          <Match idRef="Keywords_slovenia_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_slovenia_eu_gps_data_1" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_gps_data_2" />
          <Match idRef="Keywords_slovenia_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_slovenia_eu_gps_data_2" />
        </Pattern>
</Entity>
```

## <a name="spain"></a><span data-ttu-id="95662-357">España</span><span class="sxs-lookup"><span data-stu-id="95662-357">Spain</span></span>

### <a name="pattern"></a><span data-ttu-id="95662-358">Patrón</span><span class="sxs-lookup"><span data-stu-id="95662-358">Pattern</span></span>

-  <span data-ttu-id="95662-359">dígitos</span><span class="sxs-lookup"><span data-stu-id="95662-359">digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="95662-360">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="95662-360">Checksum</span></span>

<span data-ttu-id="95662-361">No aplicable</span><span class="sxs-lookup"><span data-stu-id="95662-361">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="95662-362">Definición</span><span class="sxs-lookup"><span data-stu-id="95662-362">Definition</span></span>

<span data-ttu-id="95662-363">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="95662-363">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="95662-364">La expresión regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="95662-364">The regular expression finds content that matches the pattern.</span></span>
    
- <span data-ttu-id="95662-365">Se ha encontrado una palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="95662-365">A keyword from is found.</span></span>
    
```
 <Entity id="42ac9f40-0912-4ae3-b5e6-08967192dec0" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_spain_eu_gps_data_1" />
          <Match idRef="Keywords_spain_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_spain_eu_gps_data_1" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_spain_eu_gps_data_2" />
          <Match idRef="Keywords_spain_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_spain_eu_gps_data_2" />
        </Pattern>
</Entity>
```

## <a name="sweden"></a><span data-ttu-id="95662-366">Suecia</span><span class="sxs-lookup"><span data-stu-id="95662-366">Sweden</span></span>

### <a name="pattern"></a><span data-ttu-id="95662-367">Patrón</span><span class="sxs-lookup"><span data-stu-id="95662-367">Pattern</span></span>

-  <span data-ttu-id="95662-368">dígitos</span><span class="sxs-lookup"><span data-stu-id="95662-368">digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="95662-369">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="95662-369">Checksum</span></span>

<span data-ttu-id="95662-370">No aplicable</span><span class="sxs-lookup"><span data-stu-id="95662-370">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="95662-371">Definición</span><span class="sxs-lookup"><span data-stu-id="95662-371">Definition</span></span>

<span data-ttu-id="95662-372">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="95662-372">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="95662-373">La expresión regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="95662-373">The regular expression finds content that matches the pattern.</span></span>
    
- <span data-ttu-id="95662-374">Se ha encontrado una palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="95662-374">A keyword from is found.</span></span>
    
```
 <Entity id="42ac9f40-0912-4ae3-b5e6-08967192dec0" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_sweden_eu_gps_data_1" />
          <Match idRef="Keywords_sweden_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_sweden_eu_gps_data_1" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_sweden_eu_gps_data_2" />
          <Match idRef="Keywords_sweden_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_sweden_eu_gps_data_2" />
        </Pattern>
</Entity>
```

## <a name="uk"></a><span data-ttu-id="95662-375">REINO UNIDO</span><span class="sxs-lookup"><span data-stu-id="95662-375">UK</span></span>

### <a name="pattern"></a><span data-ttu-id="95662-376">Patrón</span><span class="sxs-lookup"><span data-stu-id="95662-376">Pattern</span></span>

-  <span data-ttu-id="95662-377">dígitos</span><span class="sxs-lookup"><span data-stu-id="95662-377">digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="95662-378">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="95662-378">Checksum</span></span>

<span data-ttu-id="95662-379">No aplicable</span><span class="sxs-lookup"><span data-stu-id="95662-379">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="95662-380">Definición</span><span class="sxs-lookup"><span data-stu-id="95662-380">Definition</span></span>

<span data-ttu-id="95662-381">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="95662-381">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="95662-382">La expresión regular busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="95662-382">The regular expression finds content that matches the pattern.</span></span>
    
- <span data-ttu-id="95662-383">Se ha encontrado una palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="95662-383">A keyword from is found.</span></span>
    
```
 <Entity id="42ac9f40-0912-4ae3-b5e6-08967192dec0" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_uk_eu_gps_data_1" />
          <Match idRef="Keywords_uk_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_uk_eu_gps_data_1" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_uk_eu_gps_data_2" />
          <Match idRef="Keywords_uk_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_uk_eu_gps_data_2" />
        </Pattern>
</Entity>
```

## <a name="see-also"></a><span data-ttu-id="95662-384">Vea también</span><span class="sxs-lookup"><span data-stu-id="95662-384">See also</span></span>

[<span data-ttu-id="95662-385">Qué buscan los tipos de información confidencial</span><span class="sxs-lookup"><span data-stu-id="95662-385">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

