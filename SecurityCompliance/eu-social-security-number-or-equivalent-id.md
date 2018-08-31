---
title: Identificador de número de seguridad Social de la UE o equivalente
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/17/2018
ms.audience: Admin
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
ms.assetid: 1fabd341-e594-4bfe-961c-62aa82893f60
description: En este tema se muestra lo que busca una directiva de (DLP) de prevención de pérdida de datos cuando detecte el tipo de información confidencial del número de seguridad Social de la UE o identificador equivalente. Este tipo de información confidencial define diferentes patrones, palabras clave y otras pruebas para cada país.
ms.openlocfilehash: 6f1027dcfb648ed937b8180d74d4bc6348dab650
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22536077"
---
# <a name="eu-social-security-number-or-equivalent-id"></a><span data-ttu-id="54816-104">Identificador de número de seguridad Social de la UE o equivalente</span><span class="sxs-lookup"><span data-stu-id="54816-104">EU Social Security Number or Equivalent ID</span></span>

<span data-ttu-id="54816-p102">En este tema se muestra lo que busca una directiva de (DLP) de prevención de pérdida de datos cuando detecte el tipo de información confidencial de la UE número de seguridad Social (SSN) o identificador equivalente. Este tipo de información confidencial define diferentes patrones, palabras clave y otras pruebas para cada país.</span><span class="sxs-lookup"><span data-stu-id="54816-p102">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Social Security Number (SSN) or Equivalent ID sensitive information type. This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="54816-107">Austria</span><span class="sxs-lookup"><span data-stu-id="54816-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="54816-108">Formato</span><span class="sxs-lookup"><span data-stu-id="54816-108">Format</span></span>

<span data-ttu-id="54816-109">10 dígitos en el formato especificado</span><span class="sxs-lookup"><span data-stu-id="54816-109">10 digits in the specified format</span></span>
  
### <a name="pattern"></a><span data-ttu-id="54816-110">Patrón</span><span class="sxs-lookup"><span data-stu-id="54816-110">Pattern</span></span>

<span data-ttu-id="54816-111">10 dígitos:</span><span class="sxs-lookup"><span data-stu-id="54816-111">10 digits:</span></span>
  
-  <span data-ttu-id="54816-112">Tres dígitos que se corresponden con un número de serie</span><span class="sxs-lookup"><span data-stu-id="54816-112">Three digits that correspond to a serial number</span></span> 
    
- <span data-ttu-id="54816-113">Dígito de un control</span><span class="sxs-lookup"><span data-stu-id="54816-113">One check digit</span></span>
    
- <span data-ttu-id="54816-114">Seis dígitos que se corresponden con la fecha de nacimiento (DDMMAA)</span><span class="sxs-lookup"><span data-stu-id="54816-114">Six digits that correspond to the birth date (DDMMYY)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="54816-115">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="54816-115">Checksum</span></span>

<span data-ttu-id="54816-116">Sí</span><span class="sxs-lookup"><span data-stu-id="54816-116">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="54816-117">Definición</span><span class="sxs-lookup"><span data-stu-id="54816-117">Definition</span></span>

<span data-ttu-id="54816-118">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="54816-118">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="54816-119">La función `Func_austria_eu_ssn_or_equivalent` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="54816-119">The function  `Func_austria_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="54816-120">Una palabra clave de `Keywords_austria_eu_ssn_or_equivalent` se encuentra.</span><span class="sxs-lookup"><span data-stu-id="54816-120">A keyword from  `Keywords_austria_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="54816-121">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="54816-121">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="54816-122">La función `Func_austria_eu_ssn_or_equivalent` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="54816-122">The function  `Func_austria_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_austria_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_austria_eu_ssn_or_equivalent" />
        </Pattern>
<Pattern confidenceLevel="75">
            <IdMatch idRef="Func_austria_eu_ssn_or_equivalent" />
          </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="54816-123">Keywords</span><span class="sxs-lookup"><span data-stu-id="54816-123">Keywords</span></span>

#### <a name="keywordsaustriaeussnorequivalent"></a><span data-ttu-id="54816-124">Keywords_austria_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="54816-124">Keywords_austria_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="54816-125">seguridad social no</span><span class="sxs-lookup"><span data-stu-id="54816-125">social security no</span></span>
  
<span data-ttu-id="54816-126">social security number
</span><span class="sxs-lookup"><span data-stu-id="54816-126">social security number</span></span>
  
<span data-ttu-id="54816-127">
social security code</span><span class="sxs-lookup"><span data-stu-id="54816-127">social security code</span></span>
  
<span data-ttu-id="54816-128">número de seguro</span><span class="sxs-lookup"><span data-stu-id="54816-128">insurance number</span></span>
  
<span data-ttu-id="54816-129">ssn austriaco</span><span class="sxs-lookup"><span data-stu-id="54816-129">austrian ssn</span></span>
  
<span data-ttu-id="54816-130">ssn #</span><span class="sxs-lookup"><span data-stu-id="54816-130">ssn#</span></span>
  
<span data-ttu-id="54816-131">ssn</span><span class="sxs-lookup"><span data-stu-id="54816-131">ssn</span></span>
  
<span data-ttu-id="54816-132">código de seguro</span><span class="sxs-lookup"><span data-stu-id="54816-132">insurance code</span></span>
  
<span data-ttu-id="54816-133">código seguro #</span><span class="sxs-lookup"><span data-stu-id="54816-133">insurance code#</span></span>
  
<span data-ttu-id="54816-134">socialsecurityno #</span><span class="sxs-lookup"><span data-stu-id="54816-134">socialsecurityno#</span></span>
  
<span data-ttu-id="54816-135">sozialversicherungsnummer</span><span class="sxs-lookup"><span data-stu-id="54816-135">sozialversicherungsnummer</span></span>
  
<span data-ttu-id="54816-136">Soziale sicherheit kein</span><span class="sxs-lookup"><span data-stu-id="54816-136">soziale sicherheit kein</span></span>
  
<span data-ttu-id="54816-137">versicherungsnummer</span><span class="sxs-lookup"><span data-stu-id="54816-137">versicherungsnummer</span></span>
  
## <a name="belgium"></a><span data-ttu-id="54816-138">Bélgica</span><span class="sxs-lookup"><span data-stu-id="54816-138">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="54816-139">Formato</span><span class="sxs-lookup"><span data-stu-id="54816-139">Format</span></span>

<span data-ttu-id="54816-140">11 dígitos sin espacios o delimitadores</span><span class="sxs-lookup"><span data-stu-id="54816-140">11 digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="54816-141">Patrón</span><span class="sxs-lookup"><span data-stu-id="54816-141">Pattern</span></span>

<span data-ttu-id="54816-142">11 dígitos</span><span class="sxs-lookup"><span data-stu-id="54816-142">11 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="54816-143">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="54816-143">Checksum</span></span>

<span data-ttu-id="54816-144">Sí</span><span class="sxs-lookup"><span data-stu-id="54816-144">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="54816-145">Definición</span><span class="sxs-lookup"><span data-stu-id="54816-145">Definition</span></span>

<span data-ttu-id="54816-146">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="54816-146">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="54816-147">La función `Func_belgium_eu_ssn_or_equivalent` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="54816-147">The function  `Func_belgium_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="54816-148">Una palabra clave de `Keywords_belgium_eu_ssn_or_equivalent` se encuentra.</span><span class="sxs-lookup"><span data-stu-id="54816-148">A keyword from  `Keywords_belgium_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="54816-149">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="54816-149">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="54816-150">La función `Func_belgium_eu_ssn_or_equivalent` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="54816-150">The function  `Func_belgium_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_belgium_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_belgium_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_belgium_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="54816-151">Keywords</span><span class="sxs-lookup"><span data-stu-id="54816-151">Keywords</span></span>

#### <a name="keywordsbelgiumeussnorequivalent"></a><span data-ttu-id="54816-152">Keywords_belgium_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="54816-152">Keywords_belgium_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="54816-153">número nacional belga</span><span class="sxs-lookup"><span data-stu-id="54816-153">belgian national number</span></span>
  
<span data-ttu-id="54816-154">número nacional</span><span class="sxs-lookup"><span data-stu-id="54816-154">national number</span></span>
  
<span data-ttu-id="54816-155">social security number
</span><span class="sxs-lookup"><span data-stu-id="54816-155">social security number</span></span>
  
<span data-ttu-id="54816-156">nationalnumber #</span><span class="sxs-lookup"><span data-stu-id="54816-156">nationalnumber#</span></span>
  
<span data-ttu-id="54816-157">ssn #</span><span class="sxs-lookup"><span data-stu-id="54816-157">ssn#</span></span>
  
<span data-ttu-id="54816-158">ssn</span><span class="sxs-lookup"><span data-stu-id="54816-158">ssn</span></span>
  
<span data-ttu-id="54816-159">nationalnumber</span><span class="sxs-lookup"><span data-stu-id="54816-159">nationalnumber</span></span>
  
<span data-ttu-id="54816-160">bnn #</span><span class="sxs-lookup"><span data-stu-id="54816-160">bnn#</span></span>
  
<span data-ttu-id="54816-161">bnn</span><span class="sxs-lookup"><span data-stu-id="54816-161">bnn</span></span>
  
<span data-ttu-id="54816-162">número de identificación personal</span><span class="sxs-lookup"><span data-stu-id="54816-162">personal id number</span></span>
  
<span data-ttu-id="54816-163">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="54816-163">personalidnumber#</span></span>
  
<span data-ttu-id="54816-164">numéro nacional</span><span class="sxs-lookup"><span data-stu-id="54816-164">numéro national</span></span>
  
<span data-ttu-id="54816-165">numéro de sécurité
</span><span class="sxs-lookup"><span data-stu-id="54816-165">numéro de sécurité</span></span>
  
<span data-ttu-id="54816-166">d. numéro' proceder</span><span class="sxs-lookup"><span data-stu-id="54816-166">numéro d'assuré</span></span>
  
<span data-ttu-id="54816-167">por parte nacional</span><span class="sxs-lookup"><span data-stu-id="54816-167">identifiant national</span></span>
  
<span data-ttu-id="54816-168">identifiantnational #</span><span class="sxs-lookup"><span data-stu-id="54816-168">identifiantnational#</span></span>
  
<span data-ttu-id="54816-169">numéronational #</span><span class="sxs-lookup"><span data-stu-id="54816-169">numéronational#</span></span>
  
## <a name="croatia"></a><span data-ttu-id="54816-170">Croacia</span><span class="sxs-lookup"><span data-stu-id="54816-170">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="54816-171">Formato</span><span class="sxs-lookup"><span data-stu-id="54816-171">Format</span></span>

<span data-ttu-id="54816-172">11 dígitos sin espacios y los delimitadores</span><span class="sxs-lookup"><span data-stu-id="54816-172">11 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="54816-173">Patrón</span><span class="sxs-lookup"><span data-stu-id="54816-173">Pattern</span></span>

 <span data-ttu-id="54816-174">11 dígitos:</span><span class="sxs-lookup"><span data-stu-id="54816-174">11 digits:</span></span> 
  
-  <span data-ttu-id="54816-175">Diez dígitos</span><span class="sxs-lookup"><span data-stu-id="54816-175">Ten digits</span></span> 
    
- <span data-ttu-id="54816-176">Dígito de un control</span><span class="sxs-lookup"><span data-stu-id="54816-176">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="54816-177">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="54816-177">Checksum</span></span>

<span data-ttu-id="54816-178">Sí</span><span class="sxs-lookup"><span data-stu-id="54816-178">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="54816-179">Definición</span><span class="sxs-lookup"><span data-stu-id="54816-179">Definition</span></span>

<span data-ttu-id="54816-180">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="54816-180">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="54816-181">La función `Func_croatia_eu_ssn_or_equivalent` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="54816-181">The function  `Func_croatia_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="54816-182">Una palabra clave de `Keywords_croatia_eu_ssn_or_equivalent` se encuentra.</span><span class="sxs-lookup"><span data-stu-id="54816-182">A keyword from  `Keywords_croatia_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="54816-183">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="54816-183">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="54816-184">La función `Func_croatia_eu_ssn_or_equivalent` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="54816-184">The function  `Func_croatia_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_croatia_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_croatia_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_croatia_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="54816-185">Keywords</span><span class="sxs-lookup"><span data-stu-id="54816-185">Keywords</span></span>

#### <a name="keywordscroatiaeussnorequivalent"></a><span data-ttu-id="54816-186">Keywords_croatia_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="54816-186">Keywords_croatia_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="54816-187">número de identificación personal</span><span class="sxs-lookup"><span data-stu-id="54816-187">personal identification number</span></span>
  
<span data-ttu-id="54816-188">número de ciudadanos maestra</span><span class="sxs-lookup"><span data-stu-id="54816-188">master citizen number</span></span>
  
<span data-ttu-id="54816-189">número de identificación nacional</span><span class="sxs-lookup"><span data-stu-id="54816-189">national identification number</span></span>
  
<span data-ttu-id="54816-190">social security number
</span><span class="sxs-lookup"><span data-stu-id="54816-190">social security number</span></span>
  
<span data-ttu-id="54816-191">nationalnumber #</span><span class="sxs-lookup"><span data-stu-id="54816-191">nationalnumber#</span></span>
  
<span data-ttu-id="54816-192">ssn #</span><span class="sxs-lookup"><span data-stu-id="54816-192">ssn#</span></span>
  
<span data-ttu-id="54816-193">ssn</span><span class="sxs-lookup"><span data-stu-id="54816-193">ssn</span></span>
  
<span data-ttu-id="54816-194">nationalnumber</span><span class="sxs-lookup"><span data-stu-id="54816-194">nationalnumber</span></span>
  
<span data-ttu-id="54816-195">bnn #</span><span class="sxs-lookup"><span data-stu-id="54816-195">bnn#</span></span>
  
<span data-ttu-id="54816-196">bnn</span><span class="sxs-lookup"><span data-stu-id="54816-196">bnn</span></span>
  
<span data-ttu-id="54816-197">número de identificación personal</span><span class="sxs-lookup"><span data-stu-id="54816-197">personal id number</span></span>
  
<span data-ttu-id="54816-198">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="54816-198">personalidnumber#</span></span>
  
<span data-ttu-id="54816-199">oib</span><span class="sxs-lookup"><span data-stu-id="54816-199">oib</span></span>
  
<span data-ttu-id="54816-200">osobni identifikacijski broj</span><span class="sxs-lookup"><span data-stu-id="54816-200">osobni identifikacijski broj</span></span>
  
## <a name="czech-republic"></a><span data-ttu-id="54816-201">República Checa</span><span class="sxs-lookup"><span data-stu-id="54816-201">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="54816-202">Formato</span><span class="sxs-lookup"><span data-stu-id="54816-202">Format</span></span>

<span data-ttu-id="54816-203">Diez dígitos y una barra diagonal inversa en el patrón especificado</span><span class="sxs-lookup"><span data-stu-id="54816-203">Ten digits and a backslash in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="54816-204">Patrón</span><span class="sxs-lookup"><span data-stu-id="54816-204">Pattern</span></span>

<span data-ttu-id="54816-205">Diez dígitos y una barra diagonal inversa:</span><span class="sxs-lookup"><span data-stu-id="54816-205">Ten digits and a backslash:</span></span>
  
- <span data-ttu-id="54816-206">Seis dígitos que se corresponden con la fecha de nacimiento (AAMMDD):</span><span class="sxs-lookup"><span data-stu-id="54816-206">Six digits that correspond to the birth date (YYMMDD):</span></span> 
    
- <span data-ttu-id="54816-207">Una barra diagonal inversa</span><span class="sxs-lookup"><span data-stu-id="54816-207">A backslash</span></span>
    
- <span data-ttu-id="54816-208">Tres dígitos que se corresponden con un número de serie que separa a las personas nacidas en la misma fecha</span><span class="sxs-lookup"><span data-stu-id="54816-208">Three digits that correspond to a serial number that separates persons born on the same date</span></span>
    
- <span data-ttu-id="54816-209">Dígito de un control</span><span class="sxs-lookup"><span data-stu-id="54816-209">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="54816-210">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="54816-210">Checksum</span></span>

<span data-ttu-id="54816-211">Sí</span><span class="sxs-lookup"><span data-stu-id="54816-211">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="54816-212">Definición</span><span class="sxs-lookup"><span data-stu-id="54816-212">Definition</span></span>

<span data-ttu-id="54816-213">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="54816-213">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="54816-214">La función `Func_czech_republic_eu_ssn_or_equivalent` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="54816-214">The function  `Func_czech_republic_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="54816-215">Una palabra clave de `Keywords_czech_republic_eu_ssn_or_equivalent` se encuentra.</span><span class="sxs-lookup"><span data-stu-id="54816-215">A keyword from  `Keywords_czech_republic_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="54816-216">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="54816-216">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="54816-217">La función `Func_czech_republic_eu_ssn_or_equivalent` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="54816-217">The function  `Func_czech_republic_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_czech_republic_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_czech_republic_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_czech_republic_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="54816-218">Keywords</span><span class="sxs-lookup"><span data-stu-id="54816-218">Keywords</span></span>

#### <a name="keywordsczechrepubliceussnorequivalent"></a><span data-ttu-id="54816-219">Keywords_czech_republic_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="54816-219">Keywords_czech_republic_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="54816-220">número de nacimiento</span><span class="sxs-lookup"><span data-stu-id="54816-220">birth number</span></span>
  
<span data-ttu-id="54816-221">número de identificación nacional</span><span class="sxs-lookup"><span data-stu-id="54816-221">national identification number</span></span>
  
<span data-ttu-id="54816-222">número de identificación personal</span><span class="sxs-lookup"><span data-stu-id="54816-222">personal identification number</span></span>
  
<span data-ttu-id="54816-223">social security number
</span><span class="sxs-lookup"><span data-stu-id="54816-223">social security number</span></span>
  
<span data-ttu-id="54816-224">nationalnumber #</span><span class="sxs-lookup"><span data-stu-id="54816-224">nationalnumber#</span></span>
  
<span data-ttu-id="54816-225">ssn #</span><span class="sxs-lookup"><span data-stu-id="54816-225">ssn#</span></span>
  
<span data-ttu-id="54816-226">ssn</span><span class="sxs-lookup"><span data-stu-id="54816-226">ssn</span></span>
  
<span data-ttu-id="54816-227">número nacional</span><span class="sxs-lookup"><span data-stu-id="54816-227">national number</span></span>
  
<span data-ttu-id="54816-228">número de identificación personal</span><span class="sxs-lookup"><span data-stu-id="54816-228">personal id number</span></span>
  
<span data-ttu-id="54816-229">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="54816-229">personalidnumber#</span></span>
  
<span data-ttu-id="54816-230">rč</span><span class="sxs-lookup"><span data-stu-id="54816-230">rč</span></span>
  
<span data-ttu-id="54816-231">rodné číslo</span><span class="sxs-lookup"><span data-stu-id="54816-231">rodné číslo</span></span>
  
<span data-ttu-id="54816-232">rodne cislo</span><span class="sxs-lookup"><span data-stu-id="54816-232">rodne cislo</span></span>
  
## <a name="denmark"></a><span data-ttu-id="54816-233">Dinamarca</span><span class="sxs-lookup"><span data-stu-id="54816-233">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="54816-234">Formato</span><span class="sxs-lookup"><span data-stu-id="54816-234">Format</span></span>

<span data-ttu-id="54816-235">Diez dígitos y un guión en el patrón especificado</span><span class="sxs-lookup"><span data-stu-id="54816-235">Ten digits and a hyphen in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="54816-236">Patrón</span><span class="sxs-lookup"><span data-stu-id="54816-236">Pattern</span></span>

<span data-ttu-id="54816-237">Diez dígitos y un guión:</span><span class="sxs-lookup"><span data-stu-id="54816-237">Ten digits and a hyphen:</span></span>
  
- <span data-ttu-id="54816-238">Seis dígitos que se corresponden con la fecha de nacimiento (DDMMAA)</span><span class="sxs-lookup"><span data-stu-id="54816-238">Six digits that correspond to the birth date (DDMMYY)</span></span> 
    
- <span data-ttu-id="54816-239">Un guión </span><span class="sxs-lookup"><span data-stu-id="54816-239">A hyphen</span></span>
    
- <span data-ttu-id="54816-240">Cuatro dígitos que se corresponden con un número de secuencia</span><span class="sxs-lookup"><span data-stu-id="54816-240">Four digits that correspond to a sequence number</span></span>
    
### <a name="checksum"></a><span data-ttu-id="54816-241">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="54816-241">Checksum</span></span>

<span data-ttu-id="54816-242">Sí</span><span class="sxs-lookup"><span data-stu-id="54816-242">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="54816-243">Definición</span><span class="sxs-lookup"><span data-stu-id="54816-243">Definition</span></span>

<span data-ttu-id="54816-244">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="54816-244">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="54816-245">La función `Func_denmark_eu_ssn_or_equivalent` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="54816-245">The function  `Func_denmark_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="54816-246">Una palabra clave de `Keywords_denmark_eu_ssn_or_equivalent` se encuentra.</span><span class="sxs-lookup"><span data-stu-id="54816-246">A keyword from  `Keywords_denmark_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="54816-247">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="54816-247">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="54816-248">La función `Func_denmark_eu_ssn_or_equivalent` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="54816-248">The function  `Func_denmark_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_denmark_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_denmark_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_denmark_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="54816-249">Keywords</span><span class="sxs-lookup"><span data-stu-id="54816-249">Keywords</span></span>

#### <a name="keywordsdenmarkeussnorequivalent"></a><span data-ttu-id="54816-250">Keywords_denmark_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="54816-250">Keywords_denmark_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="54816-251">número de identificación personal</span><span class="sxs-lookup"><span data-stu-id="54816-251">personal identification number</span></span>
  
<span data-ttu-id="54816-252">número de identificación nacional</span><span class="sxs-lookup"><span data-stu-id="54816-252">national identification number</span></span>
  
<span data-ttu-id="54816-253">social security number
</span><span class="sxs-lookup"><span data-stu-id="54816-253">social security number</span></span>
  
<span data-ttu-id="54816-254">nationalnumber #</span><span class="sxs-lookup"><span data-stu-id="54816-254">nationalnumber#</span></span>
  
<span data-ttu-id="54816-255">ssn #</span><span class="sxs-lookup"><span data-stu-id="54816-255">ssn#</span></span>
  
<span data-ttu-id="54816-256">ssn</span><span class="sxs-lookup"><span data-stu-id="54816-256">ssn</span></span>
  
<span data-ttu-id="54816-257">número nacional</span><span class="sxs-lookup"><span data-stu-id="54816-257">national number</span></span>
  
<span data-ttu-id="54816-258">número de identificación personal</span><span class="sxs-lookup"><span data-stu-id="54816-258">personal id number</span></span>
  
<span data-ttu-id="54816-259">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="54816-259">personalidnumber#</span></span>
  
<span data-ttu-id="54816-260">rcp nummer</span><span class="sxs-lookup"><span data-stu-id="54816-260">cpr-nummer</span></span>
  
<span data-ttu-id="54816-261">personnummer</span><span class="sxs-lookup"><span data-stu-id="54816-261">personnummer</span></span>
  
## <a name="finland"></a><span data-ttu-id="54816-262">Finlandia</span><span class="sxs-lookup"><span data-stu-id="54816-262">Finland</span></span>

### <a name="format"></a><span data-ttu-id="54816-263">Formato</span><span class="sxs-lookup"><span data-stu-id="54816-263">Format</span></span>

<span data-ttu-id="54816-264">Una combinación de caracteres de 11 en el formato especificado</span><span class="sxs-lookup"><span data-stu-id="54816-264">An 11-character combination in the specified format</span></span>
  
### <a name="pattern"></a><span data-ttu-id="54816-265">Patrón</span><span class="sxs-lookup"><span data-stu-id="54816-265">Pattern</span></span>

<span data-ttu-id="54816-266">Una combinación de caracteres de 11 en el formato especificado:</span><span class="sxs-lookup"><span data-stu-id="54816-266">An 11-character combination in the specified format:</span></span>
  
-  <span data-ttu-id="54816-267">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="54816-267">Six digits</span></span> 
    
- <span data-ttu-id="54816-268">Una instancia de uno de los siguientes:</span><span class="sxs-lookup"><span data-stu-id="54816-268">One instance of one of the following:</span></span>
    
  - <span data-ttu-id="54816-269">Además de símbolo</span><span class="sxs-lookup"><span data-stu-id="54816-269">Plus symbol</span></span>
    
  - <span data-ttu-id="54816-270">Signo menos</span><span class="sxs-lookup"><span data-stu-id="54816-270">Minus symbol</span></span>
    
  - <span data-ttu-id="54816-271">La letra "A" (no distingue mayúsculas de minúsculas)</span><span class="sxs-lookup"><span data-stu-id="54816-271">The letter "A" (not case-sensitive)</span></span>
    
- <span data-ttu-id="54816-272">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="54816-272">Three digits</span></span>
    
- <span data-ttu-id="54816-273">Una letra o un dígito</span><span class="sxs-lookup"><span data-stu-id="54816-273">One letter or one digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="54816-274">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="54816-274">Checksum</span></span>

<span data-ttu-id="54816-275">Sí</span><span class="sxs-lookup"><span data-stu-id="54816-275">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="54816-276">Definición</span><span class="sxs-lookup"><span data-stu-id="54816-276">Definition</span></span>

<span data-ttu-id="54816-277">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="54816-277">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="54816-278">La función `Func_finland_eu_ssn_or_equivalent` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="54816-278">The function  `Func_finland_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="54816-279">Una palabra clave de `Keywords_finland_eu_ssn_or_equivalent` se encuentra.</span><span class="sxs-lookup"><span data-stu-id="54816-279">A keyword from  `Keywords_finland_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="54816-280">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="54816-280">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="54816-281">La función `Func_finland_eu_ssn_or_equivalent` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="54816-281">The function  `Func_finland_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_finland_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_finland_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_finland_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="54816-282">Keywords</span><span class="sxs-lookup"><span data-stu-id="54816-282">Keywords</span></span>

#### <a name="keywordsfinlandeussnorequivalent"></a><span data-ttu-id="54816-283">Keywords_finland_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="54816-283">Keywords_finland_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="54816-284">identification number
</span><span class="sxs-lookup"><span data-stu-id="54816-284">identification number</span></span>
  
<span data-ttu-id="54816-285">identificador personal</span><span class="sxs-lookup"><span data-stu-id="54816-285">personal id</span></span>
  
<span data-ttu-id="54816-286">número de identidad</span><span class="sxs-lookup"><span data-stu-id="54816-286">identity number</span></span>
  
<span data-ttu-id="54816-287">número de identificación nacional finlandés</span><span class="sxs-lookup"><span data-stu-id="54816-287">finnish national id number</span></span>
  
<span data-ttu-id="54816-288">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="54816-288">personalidnumber#</span></span>
  
<span data-ttu-id="54816-289">número de identificación nacional</span><span class="sxs-lookup"><span data-stu-id="54816-289">national identification number</span></span>
  
<span data-ttu-id="54816-290">número de Id.</span><span class="sxs-lookup"><span data-stu-id="54816-290">id number</span></span>
  
<span data-ttu-id="54816-291">identificador de nacional no.</span><span class="sxs-lookup"><span data-stu-id="54816-291">national id no.</span></span>
  
<span data-ttu-id="54816-292">número de identificación nacional</span><span class="sxs-lookup"><span data-stu-id="54816-292">national id number</span></span>
  
<span data-ttu-id="54816-293">identificador de ningún</span><span class="sxs-lookup"><span data-stu-id="54816-293">id no</span></span>
  
<span data-ttu-id="54816-294">tunnistenumero</span><span class="sxs-lookup"><span data-stu-id="54816-294">tunnistenumero</span></span>
  
<span data-ttu-id="54816-295">henkilötunnus</span><span class="sxs-lookup"><span data-stu-id="54816-295">henkilötunnus</span></span>
  
<span data-ttu-id="54816-296">yksilöllinen henkilökohtainen tunnistenumero</span><span class="sxs-lookup"><span data-stu-id="54816-296">yksilöllinen henkilökohtainen tunnistenumero</span></span>
  
<span data-ttu-id="54816-297">ainutlaatuinen henkilökohtainen tunnus</span><span class="sxs-lookup"><span data-stu-id="54816-297">ainutlaatuinen henkilökohtainen tunnus</span></span>
  
<span data-ttu-id="54816-298">numero de identiteetti</span><span class="sxs-lookup"><span data-stu-id="54816-298">identiteetti numero</span></span>
  
<span data-ttu-id="54816-299">Suomen kansallinen henkilötunnus</span><span class="sxs-lookup"><span data-stu-id="54816-299">suomen kansallinen henkilötunnus</span></span>
  
<span data-ttu-id="54816-300">henkilötunnusnumero #</span><span class="sxs-lookup"><span data-stu-id="54816-300">henkilötunnusnumero#</span></span>
  
<span data-ttu-id="54816-301">kansallisen tunnistenumero</span><span class="sxs-lookup"><span data-stu-id="54816-301">kansallisen tunnistenumero</span></span>
  
<span data-ttu-id="54816-302">tunnusnumero</span><span class="sxs-lookup"><span data-stu-id="54816-302">tunnusnumero</span></span>
  
<span data-ttu-id="54816-303">numero de tunnus kansallinen</span><span class="sxs-lookup"><span data-stu-id="54816-303">kansallinen tunnus numero</span></span>
  
<span data-ttu-id="54816-304">hetu</span><span class="sxs-lookup"><span data-stu-id="54816-304">hetu</span></span>
  
## <a name="france"></a><span data-ttu-id="54816-305">Francia</span><span class="sxs-lookup"><span data-stu-id="54816-305">France</span></span>

<span data-ttu-id="54816-306">Para obtener información detallada, vea la sección "Francia número de seguridad Social (INSEE)" en [Buscar qué los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="54816-306">For details, see the section "France Social Security Number (INSEE)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="germany"></a><span data-ttu-id="54816-307">Alemania</span><span class="sxs-lookup"><span data-stu-id="54816-307">Germany</span></span>

<span data-ttu-id="54816-308">Para obtener información detallada, vea la sección "Número de tarjeta de identidad de Alemania" en [Buscar qué los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="54816-308">For details, see the section "Germany Identity Card Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="greece"></a><span data-ttu-id="54816-309">Grecia</span><span class="sxs-lookup"><span data-stu-id="54816-309">Greece</span></span>

<span data-ttu-id="54816-310">Para obtener información detallada, vea la sección "tarjeta de identificación nacional Grecia" en [Buscar qué los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="54816-310">For details, see the section "Greece National ID Card" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="hungary"></a><span data-ttu-id="54816-311">Hungría</span><span class="sxs-lookup"><span data-stu-id="54816-311">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="54816-312">Formato</span><span class="sxs-lookup"><span data-stu-id="54816-312">Format</span></span>

<span data-ttu-id="54816-313">Nueve dígitos sin espacios y los delimitadores</span><span class="sxs-lookup"><span data-stu-id="54816-313">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="54816-314">Patrón</span><span class="sxs-lookup"><span data-stu-id="54816-314">Pattern</span></span>

<span data-ttu-id="54816-315">Nueve dígitos</span><span class="sxs-lookup"><span data-stu-id="54816-315">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="54816-316">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="54816-316">Checksum</span></span>

<span data-ttu-id="54816-317">Sí</span><span class="sxs-lookup"><span data-stu-id="54816-317">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="54816-318">Definición</span><span class="sxs-lookup"><span data-stu-id="54816-318">Definition</span></span>

<span data-ttu-id="54816-319">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="54816-319">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="54816-320">La función `Func_hungary_eu_ssn_or_equivalent` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="54816-320">The function  `Func_hungary_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="54816-321">Una palabra clave de `Keywords_hungary_eu_ssn_or_equivalent` se encuentra.</span><span class="sxs-lookup"><span data-stu-id="54816-321">A keyword from  `Keywords_hungary_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="54816-322">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="54816-322">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="54816-323">La función `Func_hungary_eu_ssn_or_equivalent` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="54816-323">The function  `Func_hungary_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_hungary_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_hungary_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_hungary_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="54816-324">Keywords</span><span class="sxs-lookup"><span data-stu-id="54816-324">Keywords</span></span>

#### <a name="keywordshungaryeussnorequivalent"></a><span data-ttu-id="54816-325">Keywords_hungary_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="54816-325">Keywords_hungary_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="54816-326">número de la seguridad social húngaro</span><span class="sxs-lookup"><span data-stu-id="54816-326">hungarian social security number</span></span>
  
<span data-ttu-id="54816-327">social security number
</span><span class="sxs-lookup"><span data-stu-id="54816-327">social security number</span></span>
  
<span data-ttu-id="54816-328">NúmeroSeguridadSocial #</span><span class="sxs-lookup"><span data-stu-id="54816-328">socialsecuritynumber#</span></span>
  
<span data-ttu-id="54816-329">hssn #</span><span class="sxs-lookup"><span data-stu-id="54816-329">hssn#</span></span>
  
<span data-ttu-id="54816-330">socialsecuritynno</span><span class="sxs-lookup"><span data-stu-id="54816-330">socialsecuritynno</span></span>
  
<span data-ttu-id="54816-331">hssn</span><span class="sxs-lookup"><span data-stu-id="54816-331">hssn</span></span>
  
<span data-ttu-id="54816-332">taj</span><span class="sxs-lookup"><span data-stu-id="54816-332">taj</span></span>
  
<span data-ttu-id="54816-333">taj #</span><span class="sxs-lookup"><span data-stu-id="54816-333">taj#</span></span>
  
<span data-ttu-id="54816-334">ssn</span><span class="sxs-lookup"><span data-stu-id="54816-334">ssn</span></span>
  
<span data-ttu-id="54816-335">ssn #</span><span class="sxs-lookup"><span data-stu-id="54816-335">ssn#</span></span>
  
<span data-ttu-id="54816-336">seguridad social no</span><span class="sxs-lookup"><span data-stu-id="54816-336">social security no</span></span>
  
<span data-ttu-id="54816-337">áfa</span><span class="sxs-lookup"><span data-stu-id="54816-337">áfa</span></span>
  
<span data-ttu-id="54816-338">közösségi adószám</span><span class="sxs-lookup"><span data-stu-id="54816-338">közösségi adószám</span></span>
  
<span data-ttu-id="54816-339">általános forgalmi adó szám</span><span class="sxs-lookup"><span data-stu-id="54816-339">általános forgalmi adó szám</span></span>
  
<span data-ttu-id="54816-340">hozzáadottérték adó</span><span class="sxs-lookup"><span data-stu-id="54816-340">hozzáadottérték adó</span></span>
  
<span data-ttu-id="54816-341">áfa szám</span><span class="sxs-lookup"><span data-stu-id="54816-341">áfa szám</span></span>
  
<span data-ttu-id="54816-342">Magiar áfa szám</span><span class="sxs-lookup"><span data-stu-id="54816-342">magyar áfa szám</span></span>
  
## <a name="portugal"></a><span data-ttu-id="54816-343">Portugal</span><span class="sxs-lookup"><span data-stu-id="54816-343">Portugal</span></span>

<span data-ttu-id="54816-344">Para obtener información detallada, vea la sección "Número de tarjeta de Portugal ciudadanos" en [Buscar qué los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="54816-344">For details, see the section "Portugal Citizen Card Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="spain"></a><span data-ttu-id="54816-345">España</span><span class="sxs-lookup"><span data-stu-id="54816-345">Spain</span></span>

<span data-ttu-id="54816-346">Para obtener información detallada, vea la sección "España número de seguridad Social (SSN)" en [Buscar qué los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="54816-346">For details, see the section "Spain Social Security Number (SSN)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="sweden"></a><span data-ttu-id="54816-347">Suecia</span><span class="sxs-lookup"><span data-stu-id="54816-347">Sweden</span></span>

### <a name="format"></a><span data-ttu-id="54816-348">Formato</span><span class="sxs-lookup"><span data-stu-id="54816-348">Format</span></span>

<span data-ttu-id="54816-349">12 dígitos sin espacios y los delimitadores</span><span class="sxs-lookup"><span data-stu-id="54816-349">12 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="54816-350">Patrón</span><span class="sxs-lookup"><span data-stu-id="54816-350">Pattern</span></span>

<span data-ttu-id="54816-351">12 dígitos:</span><span class="sxs-lookup"><span data-stu-id="54816-351">12 digits:</span></span>
  
-  <span data-ttu-id="54816-352">Ocho dígitos que se corresponden con la fecha de nacimiento (aaaammdd)</span><span class="sxs-lookup"><span data-stu-id="54816-352">Eight digits that correspond to the birth date (YYYYMMDD)</span></span> 
    
- <span data-ttu-id="54816-353">Tres dígitos que se corresponden con un número de serie donde:</span><span class="sxs-lookup"><span data-stu-id="54816-353">Three digits that correspond to a serial number where:</span></span> 
    
  - <span data-ttu-id="54816-354">El último dígito en el número de serie indica género por la asignación de un número impar para hombre y un número par de hembra</span><span class="sxs-lookup"><span data-stu-id="54816-354">The last digit in the serial number indicates gender by the assignment of an odd number for male and an even number for female</span></span>
    
  - <span data-ttu-id="54816-355">Hasta 1990, la asignación del número de serie correspondía a la provincia donde surgió el portador del número o (si nacimiento antes de 1947) donde éste tenía ha viva, según los registros de impuestos, en el 1 de enero de 1947, con un código especial (normalmente 9 como el dígito 7) para inmigrantes</span><span class="sxs-lookup"><span data-stu-id="54816-355">Up to 1990, the assignment of serial number corresponded to the county where the bearer of the number was born or (if born before 1947) where he/she had been living, according to tax records, on January 1, 1947, with a special code (usually 9 as the 7th digit) for immigrants</span></span> 
    
- <span data-ttu-id="54816-356">Dígito de un control</span><span class="sxs-lookup"><span data-stu-id="54816-356">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="54816-357">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="54816-357">Checksum</span></span>

<span data-ttu-id="54816-358">Sí</span><span class="sxs-lookup"><span data-stu-id="54816-358">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="54816-359">Definición</span><span class="sxs-lookup"><span data-stu-id="54816-359">Definition</span></span>

<span data-ttu-id="54816-360">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="54816-360">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="54816-361">La función `Func_sweden_eu_ssn_or_equivalent` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="54816-361">The function  `Func_sweden_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="54816-362">Una palabra clave de `Keywords_sweden_eu_ssn_or_equivalent` se encuentra.</span><span class="sxs-lookup"><span data-stu-id="54816-362">A keyword from  `Keywords_sweden_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="54816-363">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="54816-363">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="54816-364">La función `Func_sweden_eu_ssn_or_equivalent` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="54816-364">The function  `Func_sweden_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_sweden_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_sweden_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_sweden_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="54816-365">Keywords</span><span class="sxs-lookup"><span data-stu-id="54816-365">Keywords</span></span>

#### <a name="keywordsswedeneussnorequivalent"></a><span data-ttu-id="54816-366">Keywords_sweden_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="54816-366">Keywords_sweden_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="54816-367">número de identificación personal</span><span class="sxs-lookup"><span data-stu-id="54816-367">personal id number</span></span>
  
<span data-ttu-id="54816-368">identification number
</span><span class="sxs-lookup"><span data-stu-id="54816-368">identification number</span></span>
  
<span data-ttu-id="54816-369">un identificador personal no</span><span class="sxs-lookup"><span data-stu-id="54816-369">personal id no</span></span>
  
<span data-ttu-id="54816-370">identidad no</span><span class="sxs-lookup"><span data-stu-id="54816-370">identity no</span></span>
  
<span data-ttu-id="54816-371">identificación no</span><span class="sxs-lookup"><span data-stu-id="54816-371">identification no</span></span>
  
<span data-ttu-id="54816-372">identificación personal no</span><span class="sxs-lookup"><span data-stu-id="54816-372">personal identification no</span></span>
  
<span data-ttu-id="54816-373">identificador de personnummer</span><span class="sxs-lookup"><span data-stu-id="54816-373">personnummer id</span></span>
  
<span data-ttu-id="54816-374">identificador de personligt-nummer</span><span class="sxs-lookup"><span data-stu-id="54816-374">personligt id-nummer</span></span>
  
<span data-ttu-id="54816-375">identificador de unikt-nummer</span><span class="sxs-lookup"><span data-stu-id="54816-375">unikt id-nummer</span></span>
  
<span data-ttu-id="54816-376">personnummer</span><span class="sxs-lookup"><span data-stu-id="54816-376">personnummer</span></span>
  
<span data-ttu-id="54816-377">identifikationsnumret</span><span class="sxs-lookup"><span data-stu-id="54816-377">identifikationsnumret</span></span>
  
<span data-ttu-id="54816-378">personnummer #</span><span class="sxs-lookup"><span data-stu-id="54816-378">personnummer#</span></span>
  
<span data-ttu-id="54816-379">identifikationsnumret #</span><span class="sxs-lookup"><span data-stu-id="54816-379">identifikationsnumret#</span></span>
  
## <a name="see-also"></a><span data-ttu-id="54816-380">Vea también</span><span class="sxs-lookup"><span data-stu-id="54816-380">See also</span></span>

[<span data-ttu-id="54816-381">Qué buscan los tipos de información confidencial</span><span class="sxs-lookup"><span data-stu-id="54816-381">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

