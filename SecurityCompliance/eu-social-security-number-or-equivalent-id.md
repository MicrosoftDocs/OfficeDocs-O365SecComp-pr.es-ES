---
title: Número de la seguridad social de la UE o identificador equivalente
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/17/2018
ms.audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
description: En este tema se muestra qué busca una directiva de prevención de pérdida de datos (DLP) cuando detecta el número de la seguridad social de la UE o el tipo de información confidencial del identificador equivalente. Este tipo de información confidencial define distintos patrones, palabras clave y otras pruebas para cada país.
ms.openlocfilehash: c0c808eafa52209c79f3b4e8a2113f587fd8a771
ms.sourcegitcommit: ed822a776d3419853453583e882f3c61ca26d4b2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "30410805"
---
# <a name="eu-social-security-number-or-equivalent-id"></a><span data-ttu-id="9eb47-104">Número de la seguridad social de la UE o identificador equivalente</span><span class="sxs-lookup"><span data-stu-id="9eb47-104">EU Social Security Number or Equivalent ID</span></span>

<span data-ttu-id="9eb47-105">En este tema se muestra qué busca una directiva de prevención de pérdida de datos (DLP) cuando detecta el tipo de información confidencial del número de la seguridad social (SSN) o del identificador equivalente de la UE.</span><span class="sxs-lookup"><span data-stu-id="9eb47-105">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Social Security Number (SSN) or Equivalent ID sensitive information type.</span></span> <span data-ttu-id="9eb47-106">Este tipo de información confidencial define distintos patrones, palabras clave y otras pruebas para cada país.</span><span class="sxs-lookup"><span data-stu-id="9eb47-106">This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="9eb47-107">Austria</span><span class="sxs-lookup"><span data-stu-id="9eb47-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="9eb47-108">Dé</span><span class="sxs-lookup"><span data-stu-id="9eb47-108">Format</span></span>

<span data-ttu-id="9eb47-109">10 dígitos en el formato especificado</span><span class="sxs-lookup"><span data-stu-id="9eb47-109">10 digits in the specified format</span></span>
  
### <a name="pattern"></a><span data-ttu-id="9eb47-110">Patrón</span><span class="sxs-lookup"><span data-stu-id="9eb47-110">Pattern</span></span>

<span data-ttu-id="9eb47-111">10 dígitos:</span><span class="sxs-lookup"><span data-stu-id="9eb47-111">10 digits:</span></span>
  
-  <span data-ttu-id="9eb47-112">Tres dígitos que corresponden a un número de serie</span><span class="sxs-lookup"><span data-stu-id="9eb47-112">Three digits that correspond to a serial number</span></span> 
    
- <span data-ttu-id="9eb47-113">Un dígito de control</span><span class="sxs-lookup"><span data-stu-id="9eb47-113">One check digit</span></span>
    
- <span data-ttu-id="9eb47-114">Seis dígitos que corresponden a la fecha de nacimiento (DDMMAA)</span><span class="sxs-lookup"><span data-stu-id="9eb47-114">Six digits that correspond to the birth date (DDMMYY)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="9eb47-115">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="9eb47-115">Checksum</span></span>

<span data-ttu-id="9eb47-116">Sí</span><span class="sxs-lookup"><span data-stu-id="9eb47-116">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="9eb47-117">Definición</span><span class="sxs-lookup"><span data-stu-id="9eb47-117">Definition</span></span>

<span data-ttu-id="9eb47-118">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="9eb47-118">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9eb47-119">La función `Func_austria_eu_ssn_or_equivalent` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="9eb47-119">The function  `Func_austria_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="9eb47-120">Se encuentra una `Keywords_austria_eu_ssn_or_equivalent` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="9eb47-120">A keyword from  `Keywords_austria_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="9eb47-121">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="9eb47-121">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9eb47-122">La función `Func_austria_eu_ssn_or_equivalent` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="9eb47-122">The function  `Func_austria_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="9eb47-123">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="9eb47-123">Keywords</span></span>

#### <a name="keywordsaustriaeussnorequivalent"></a><span data-ttu-id="9eb47-124">Keywords_austria_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="9eb47-124">Keywords_austria_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="9eb47-125">n.º de seguridad social</span><span class="sxs-lookup"><span data-stu-id="9eb47-125">social security no</span></span>
  
<span data-ttu-id="9eb47-126">social security number</span><span class="sxs-lookup"><span data-stu-id="9eb47-126">social security number</span></span>
  
<span data-ttu-id="9eb47-127">social security code</span><span class="sxs-lookup"><span data-stu-id="9eb47-127">social security code</span></span>
  
<span data-ttu-id="9eb47-128">número de seguro</span><span class="sxs-lookup"><span data-stu-id="9eb47-128">insurance number</span></span>
  
<span data-ttu-id="9eb47-129">SSN austriaco</span><span class="sxs-lookup"><span data-stu-id="9eb47-129">austrian ssn</span></span>
  
<span data-ttu-id="9eb47-130">SSN</span><span class="sxs-lookup"><span data-stu-id="9eb47-130">ssn#</span></span>
  
<span data-ttu-id="9eb47-131">SSN</span><span class="sxs-lookup"><span data-stu-id="9eb47-131">ssn</span></span>
  
<span data-ttu-id="9eb47-132">código de seguro</span><span class="sxs-lookup"><span data-stu-id="9eb47-132">insurance code</span></span>
  
<span data-ttu-id="9eb47-133">número de código de seguro</span><span class="sxs-lookup"><span data-stu-id="9eb47-133">insurance code#</span></span>
  
<span data-ttu-id="9eb47-134">socialsecurityno #</span><span class="sxs-lookup"><span data-stu-id="9eb47-134">socialsecurityno#</span></span>
  
<span data-ttu-id="9eb47-135">sozialversicherungsnummer</span><span class="sxs-lookup"><span data-stu-id="9eb47-135">sozialversicherungsnummer</span></span>
  
<span data-ttu-id="9eb47-136">Soziale Sicherheit kein</span><span class="sxs-lookup"><span data-stu-id="9eb47-136">soziale sicherheit kein</span></span>
  
<span data-ttu-id="9eb47-137">versicherungsnummer</span><span class="sxs-lookup"><span data-stu-id="9eb47-137">versicherungsnummer</span></span>
  
## <a name="belgium"></a><span data-ttu-id="9eb47-138">Bélgica</span><span class="sxs-lookup"><span data-stu-id="9eb47-138">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="9eb47-139">Dé</span><span class="sxs-lookup"><span data-stu-id="9eb47-139">Format</span></span>

<span data-ttu-id="9eb47-140">11 dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="9eb47-140">11 digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="9eb47-141">Patrón</span><span class="sxs-lookup"><span data-stu-id="9eb47-141">Pattern</span></span>

<span data-ttu-id="9eb47-142">11 dígitos</span><span class="sxs-lookup"><span data-stu-id="9eb47-142">11 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="9eb47-143">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="9eb47-143">Checksum</span></span>

<span data-ttu-id="9eb47-144">Sí</span><span class="sxs-lookup"><span data-stu-id="9eb47-144">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="9eb47-145">Definición</span><span class="sxs-lookup"><span data-stu-id="9eb47-145">Definition</span></span>

<span data-ttu-id="9eb47-146">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="9eb47-146">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9eb47-147">La función `Func_belgium_eu_ssn_or_equivalent` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="9eb47-147">The function  `Func_belgium_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="9eb47-148">Se encuentra una `Keywords_belgium_eu_ssn_or_equivalent` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="9eb47-148">A keyword from  `Keywords_belgium_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="9eb47-149">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="9eb47-149">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9eb47-150">La función `Func_belgium_eu_ssn_or_equivalent` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="9eb47-150">The function  `Func_belgium_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="9eb47-151">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="9eb47-151">Keywords</span></span>

#### <a name="keywordsbelgiumeussnorequivalent"></a><span data-ttu-id="9eb47-152">Keywords_belgium_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="9eb47-152">Keywords_belgium_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="9eb47-153">número nacional belga</span><span class="sxs-lookup"><span data-stu-id="9eb47-153">belgian national number</span></span>
  
<span data-ttu-id="9eb47-154">número nacional</span><span class="sxs-lookup"><span data-stu-id="9eb47-154">national number</span></span>
  
<span data-ttu-id="9eb47-155">social security number</span><span class="sxs-lookup"><span data-stu-id="9eb47-155">social security number</span></span>
  
<span data-ttu-id="9eb47-156">nationalnumber #</span><span class="sxs-lookup"><span data-stu-id="9eb47-156">nationalnumber#</span></span>
  
<span data-ttu-id="9eb47-157">SSN</span><span class="sxs-lookup"><span data-stu-id="9eb47-157">ssn#</span></span>
  
<span data-ttu-id="9eb47-158">SSN</span><span class="sxs-lookup"><span data-stu-id="9eb47-158">ssn</span></span>
  
<span data-ttu-id="9eb47-159">nationalnumber</span><span class="sxs-lookup"><span data-stu-id="9eb47-159">nationalnumber</span></span>
  
<span data-ttu-id="9eb47-160">BNN #</span><span class="sxs-lookup"><span data-stu-id="9eb47-160">bnn#</span></span>
  
<span data-ttu-id="9eb47-161">BNN</span><span class="sxs-lookup"><span data-stu-id="9eb47-161">bnn</span></span>
  
<span data-ttu-id="9eb47-162">número de identificación personal</span><span class="sxs-lookup"><span data-stu-id="9eb47-162">personal id number</span></span>
  
<span data-ttu-id="9eb47-163">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="9eb47-163">personalidnumber#</span></span>
  
<span data-ttu-id="9eb47-164">numéro nacional</span><span class="sxs-lookup"><span data-stu-id="9eb47-164">numéro national</span></span>
  
<span data-ttu-id="9eb47-165">numéro de sécurité</span><span class="sxs-lookup"><span data-stu-id="9eb47-165">numéro de sécurité</span></span>
  
<span data-ttu-id="9eb47-166">numéro d'assuré</span><span class="sxs-lookup"><span data-stu-id="9eb47-166">numéro d'assuré</span></span>
  
<span data-ttu-id="9eb47-167">Nacional del identificador</span><span class="sxs-lookup"><span data-stu-id="9eb47-167">identifiant national</span></span>
  
<span data-ttu-id="9eb47-168">identifiantnational #</span><span class="sxs-lookup"><span data-stu-id="9eb47-168">identifiantnational#</span></span>
  
<span data-ttu-id="9eb47-169">numéronational #</span><span class="sxs-lookup"><span data-stu-id="9eb47-169">numéronational#</span></span>
  
## <a name="croatia"></a><span data-ttu-id="9eb47-170">Croacia</span><span class="sxs-lookup"><span data-stu-id="9eb47-170">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="9eb47-171">Dé</span><span class="sxs-lookup"><span data-stu-id="9eb47-171">Format</span></span>

<span data-ttu-id="9eb47-172">11 dígitos sin espacios y delimitadores</span><span class="sxs-lookup"><span data-stu-id="9eb47-172">11 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="9eb47-173">Patrón</span><span class="sxs-lookup"><span data-stu-id="9eb47-173">Pattern</span></span>

 <span data-ttu-id="9eb47-174">11 dígitos:</span><span class="sxs-lookup"><span data-stu-id="9eb47-174">11 digits:</span></span> 
  
-  <span data-ttu-id="9eb47-175">Diez dígitos</span><span class="sxs-lookup"><span data-stu-id="9eb47-175">Ten digits</span></span> 
    
- <span data-ttu-id="9eb47-176">Un dígito de control</span><span class="sxs-lookup"><span data-stu-id="9eb47-176">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="9eb47-177">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="9eb47-177">Checksum</span></span>

<span data-ttu-id="9eb47-178">Sí</span><span class="sxs-lookup"><span data-stu-id="9eb47-178">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="9eb47-179">Definición</span><span class="sxs-lookup"><span data-stu-id="9eb47-179">Definition</span></span>

<span data-ttu-id="9eb47-180">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="9eb47-180">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9eb47-181">La función `Func_croatia_eu_ssn_or_equivalent` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="9eb47-181">The function  `Func_croatia_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="9eb47-182">Se encuentra una `Keywords_croatia_eu_ssn_or_equivalent` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="9eb47-182">A keyword from  `Keywords_croatia_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="9eb47-183">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="9eb47-183">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9eb47-184">La función `Func_croatia_eu_ssn_or_equivalent` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="9eb47-184">The function  `Func_croatia_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="9eb47-185">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="9eb47-185">Keywords</span></span>

#### <a name="keywordscroatiaeussnorequivalent"></a><span data-ttu-id="9eb47-186">Keywords_croatia_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="9eb47-186">Keywords_croatia_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="9eb47-187">número de identificación personal</span><span class="sxs-lookup"><span data-stu-id="9eb47-187">personal identification number</span></span>
  
<span data-ttu-id="9eb47-188">número de ciudadano principal</span><span class="sxs-lookup"><span data-stu-id="9eb47-188">master citizen number</span></span>
  
<span data-ttu-id="9eb47-189">national identification number</span><span class="sxs-lookup"><span data-stu-id="9eb47-189">national identification number</span></span>
  
<span data-ttu-id="9eb47-190">social security number</span><span class="sxs-lookup"><span data-stu-id="9eb47-190">social security number</span></span>
  
<span data-ttu-id="9eb47-191">nationalnumber #</span><span class="sxs-lookup"><span data-stu-id="9eb47-191">nationalnumber#</span></span>
  
<span data-ttu-id="9eb47-192">SSN</span><span class="sxs-lookup"><span data-stu-id="9eb47-192">ssn#</span></span>
  
<span data-ttu-id="9eb47-193">SSN</span><span class="sxs-lookup"><span data-stu-id="9eb47-193">ssn</span></span>
  
<span data-ttu-id="9eb47-194">nationalnumber</span><span class="sxs-lookup"><span data-stu-id="9eb47-194">nationalnumber</span></span>
  
<span data-ttu-id="9eb47-195">BNN #</span><span class="sxs-lookup"><span data-stu-id="9eb47-195">bnn#</span></span>
  
<span data-ttu-id="9eb47-196">BNN</span><span class="sxs-lookup"><span data-stu-id="9eb47-196">bnn</span></span>
  
<span data-ttu-id="9eb47-197">número de identificación personal</span><span class="sxs-lookup"><span data-stu-id="9eb47-197">personal id number</span></span>
  
<span data-ttu-id="9eb47-198">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="9eb47-198">personalidnumber#</span></span>
  
<span data-ttu-id="9eb47-199">OIB</span><span class="sxs-lookup"><span data-stu-id="9eb47-199">oib</span></span>
  
<span data-ttu-id="9eb47-200">osobni identifikacijski broj</span><span class="sxs-lookup"><span data-stu-id="9eb47-200">osobni identifikacijski broj</span></span>
  
## <a name="czech-republic"></a><span data-ttu-id="9eb47-201">Chequia</span><span class="sxs-lookup"><span data-stu-id="9eb47-201">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="9eb47-202">Dé</span><span class="sxs-lookup"><span data-stu-id="9eb47-202">Format</span></span>

<span data-ttu-id="9eb47-203">Diez dígitos y una barra diagonal inversa en el patrón especificado</span><span class="sxs-lookup"><span data-stu-id="9eb47-203">Ten digits and a backslash in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="9eb47-204">Patrón</span><span class="sxs-lookup"><span data-stu-id="9eb47-204">Pattern</span></span>

<span data-ttu-id="9eb47-205">Diez dígitos y una barra diagonal inversa:</span><span class="sxs-lookup"><span data-stu-id="9eb47-205">Ten digits and a backslash:</span></span>
  
- <span data-ttu-id="9eb47-206">Seis dígitos que corresponden a la fecha de nacimiento (AAMMDD):</span><span class="sxs-lookup"><span data-stu-id="9eb47-206">Six digits that correspond to the birth date (YYMMDD):</span></span> 
    
- <span data-ttu-id="9eb47-207">Una barra diagonal inversa</span><span class="sxs-lookup"><span data-stu-id="9eb47-207">A backslash</span></span>
    
- <span data-ttu-id="9eb47-208">Tres dígitos que corresponden a un número de serie que separa a los empleados nacidos en la misma fecha.</span><span class="sxs-lookup"><span data-stu-id="9eb47-208">Three digits that correspond to a serial number that separates persons born on the same date</span></span>
    
- <span data-ttu-id="9eb47-209">Un dígito de control</span><span class="sxs-lookup"><span data-stu-id="9eb47-209">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="9eb47-210">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="9eb47-210">Checksum</span></span>

<span data-ttu-id="9eb47-211">Sí</span><span class="sxs-lookup"><span data-stu-id="9eb47-211">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="9eb47-212">Definición</span><span class="sxs-lookup"><span data-stu-id="9eb47-212">Definition</span></span>

<span data-ttu-id="9eb47-213">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="9eb47-213">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9eb47-214">La función `Func_czech_republic_eu_ssn_or_equivalent` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="9eb47-214">The function  `Func_czech_republic_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="9eb47-215">Se encuentra una `Keywords_czech_republic_eu_ssn_or_equivalent` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="9eb47-215">A keyword from  `Keywords_czech_republic_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="9eb47-216">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="9eb47-216">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9eb47-217">La función `Func_czech_republic_eu_ssn_or_equivalent` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="9eb47-217">The function  `Func_czech_republic_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="9eb47-218">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="9eb47-218">Keywords</span></span>

#### <a name="keywordsczechrepubliceussnorequivalent"></a><span data-ttu-id="9eb47-219">Keywords_czech_republic_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="9eb47-219">Keywords_czech_republic_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="9eb47-220">número de nacimiento</span><span class="sxs-lookup"><span data-stu-id="9eb47-220">birth number</span></span>
  
<span data-ttu-id="9eb47-221">national identification number</span><span class="sxs-lookup"><span data-stu-id="9eb47-221">national identification number</span></span>
  
<span data-ttu-id="9eb47-222">número de identificación personal</span><span class="sxs-lookup"><span data-stu-id="9eb47-222">personal identification number</span></span>
  
<span data-ttu-id="9eb47-223">social security number</span><span class="sxs-lookup"><span data-stu-id="9eb47-223">social security number</span></span>
  
<span data-ttu-id="9eb47-224">nationalnumber #</span><span class="sxs-lookup"><span data-stu-id="9eb47-224">nationalnumber#</span></span>
  
<span data-ttu-id="9eb47-225">SSN</span><span class="sxs-lookup"><span data-stu-id="9eb47-225">ssn#</span></span>
  
<span data-ttu-id="9eb47-226">SSN</span><span class="sxs-lookup"><span data-stu-id="9eb47-226">ssn</span></span>
  
<span data-ttu-id="9eb47-227">número nacional</span><span class="sxs-lookup"><span data-stu-id="9eb47-227">national number</span></span>
  
<span data-ttu-id="9eb47-228">número de identificación personal</span><span class="sxs-lookup"><span data-stu-id="9eb47-228">personal id number</span></span>
  
<span data-ttu-id="9eb47-229">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="9eb47-229">personalidnumber#</span></span>
  
<span data-ttu-id="9eb47-230">rč</span><span class="sxs-lookup"><span data-stu-id="9eb47-230">rč</span></span>
  
<span data-ttu-id="9eb47-231">rodné číslo</span><span class="sxs-lookup"><span data-stu-id="9eb47-231">rodné číslo</span></span>
  
<span data-ttu-id="9eb47-232">rodne cislo</span><span class="sxs-lookup"><span data-stu-id="9eb47-232">rodne cislo</span></span>
  
## <a name="denmark"></a><span data-ttu-id="9eb47-233">Dinamarca</span><span class="sxs-lookup"><span data-stu-id="9eb47-233">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="9eb47-234">Dé</span><span class="sxs-lookup"><span data-stu-id="9eb47-234">Format</span></span>

<span data-ttu-id="9eb47-235">Diez dígitos y un guión en el patrón especificado</span><span class="sxs-lookup"><span data-stu-id="9eb47-235">Ten digits and a hyphen in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="9eb47-236">Patrón</span><span class="sxs-lookup"><span data-stu-id="9eb47-236">Pattern</span></span>

<span data-ttu-id="9eb47-237">Diez dígitos y un guión:</span><span class="sxs-lookup"><span data-stu-id="9eb47-237">Ten digits and a hyphen:</span></span>
  
- <span data-ttu-id="9eb47-238">Seis dígitos que corresponden a la fecha de nacimiento (DDMMAA)</span><span class="sxs-lookup"><span data-stu-id="9eb47-238">Six digits that correspond to the birth date (DDMMYY)</span></span> 
    
- <span data-ttu-id="9eb47-239">Un guión </span><span class="sxs-lookup"><span data-stu-id="9eb47-239">A hyphen</span></span>
    
- <span data-ttu-id="9eb47-240">Cuatro dígitos que corresponden a un número de secuencia</span><span class="sxs-lookup"><span data-stu-id="9eb47-240">Four digits that correspond to a sequence number</span></span>
    
### <a name="checksum"></a><span data-ttu-id="9eb47-241">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="9eb47-241">Checksum</span></span>

<span data-ttu-id="9eb47-242">Sí</span><span class="sxs-lookup"><span data-stu-id="9eb47-242">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="9eb47-243">Definición</span><span class="sxs-lookup"><span data-stu-id="9eb47-243">Definition</span></span>

<span data-ttu-id="9eb47-244">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="9eb47-244">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9eb47-245">La función `Func_denmark_eu_ssn_or_equivalent` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="9eb47-245">The function  `Func_denmark_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="9eb47-246">Se encuentra una `Keywords_denmark_eu_ssn_or_equivalent` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="9eb47-246">A keyword from  `Keywords_denmark_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="9eb47-247">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="9eb47-247">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9eb47-248">La función `Func_denmark_eu_ssn_or_equivalent` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="9eb47-248">The function  `Func_denmark_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="9eb47-249">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="9eb47-249">Keywords</span></span>

#### <a name="keywordsdenmarkeussnorequivalent"></a><span data-ttu-id="9eb47-250">Keywords_denmark_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="9eb47-250">Keywords_denmark_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="9eb47-251">número de identificación personal</span><span class="sxs-lookup"><span data-stu-id="9eb47-251">personal identification number</span></span>
  
<span data-ttu-id="9eb47-252">national identification number</span><span class="sxs-lookup"><span data-stu-id="9eb47-252">national identification number</span></span>
  
<span data-ttu-id="9eb47-253">social security number</span><span class="sxs-lookup"><span data-stu-id="9eb47-253">social security number</span></span>
  
<span data-ttu-id="9eb47-254">nationalnumber #</span><span class="sxs-lookup"><span data-stu-id="9eb47-254">nationalnumber#</span></span>
  
<span data-ttu-id="9eb47-255">SSN</span><span class="sxs-lookup"><span data-stu-id="9eb47-255">ssn#</span></span>
  
<span data-ttu-id="9eb47-256">SSN</span><span class="sxs-lookup"><span data-stu-id="9eb47-256">ssn</span></span>
  
<span data-ttu-id="9eb47-257">número nacional</span><span class="sxs-lookup"><span data-stu-id="9eb47-257">national number</span></span>
  
<span data-ttu-id="9eb47-258">número de identificación personal</span><span class="sxs-lookup"><span data-stu-id="9eb47-258">personal id number</span></span>
  
<span data-ttu-id="9eb47-259">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="9eb47-259">personalidnumber#</span></span>
  
<span data-ttu-id="9eb47-260">CPR-Nummer</span><span class="sxs-lookup"><span data-stu-id="9eb47-260">cpr-nummer</span></span>
  
<span data-ttu-id="9eb47-261">personnummer</span><span class="sxs-lookup"><span data-stu-id="9eb47-261">personnummer</span></span>
  
## <a name="finland"></a><span data-ttu-id="9eb47-262">Finlandia</span><span class="sxs-lookup"><span data-stu-id="9eb47-262">Finland</span></span>

### <a name="format"></a><span data-ttu-id="9eb47-263">Dé</span><span class="sxs-lookup"><span data-stu-id="9eb47-263">Format</span></span>

<span data-ttu-id="9eb47-264">Una combinación de 11 caracteres en el formato especificado</span><span class="sxs-lookup"><span data-stu-id="9eb47-264">An 11-character combination in the specified format</span></span>
  
### <a name="pattern"></a><span data-ttu-id="9eb47-265">Patrón</span><span class="sxs-lookup"><span data-stu-id="9eb47-265">Pattern</span></span>

<span data-ttu-id="9eb47-266">Una combinación de 11 caracteres en el formato especificado:</span><span class="sxs-lookup"><span data-stu-id="9eb47-266">An 11-character combination in the specified format:</span></span>
  
-  <span data-ttu-id="9eb47-267">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="9eb47-267">Six digits</span></span> 
    
- <span data-ttu-id="9eb47-268">Una instancia de una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="9eb47-268">One instance of one of the following:</span></span>
    
  - <span data-ttu-id="9eb47-269">Símbolo más</span><span class="sxs-lookup"><span data-stu-id="9eb47-269">Plus symbol</span></span>
    
  - <span data-ttu-id="9eb47-270">Símbolo menos</span><span class="sxs-lookup"><span data-stu-id="9eb47-270">Minus symbol</span></span>
    
  - <span data-ttu-id="9eb47-271">La letra "A" (sin distinción entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="9eb47-271">The letter "A" (not case-sensitive)</span></span>
    
- <span data-ttu-id="9eb47-272">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="9eb47-272">Three digits</span></span>
    
- <span data-ttu-id="9eb47-273">Una letra o un dígito</span><span class="sxs-lookup"><span data-stu-id="9eb47-273">One letter or one digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="9eb47-274">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="9eb47-274">Checksum</span></span>

<span data-ttu-id="9eb47-275">Sí</span><span class="sxs-lookup"><span data-stu-id="9eb47-275">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="9eb47-276">Definición</span><span class="sxs-lookup"><span data-stu-id="9eb47-276">Definition</span></span>

<span data-ttu-id="9eb47-277">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="9eb47-277">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9eb47-278">La función `Func_finland_eu_ssn_or_equivalent` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="9eb47-278">The function  `Func_finland_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="9eb47-279">Se encuentra una `Keywords_finland_eu_ssn_or_equivalent` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="9eb47-279">A keyword from  `Keywords_finland_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="9eb47-280">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="9eb47-280">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9eb47-281">La función `Func_finland_eu_ssn_or_equivalent` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="9eb47-281">The function  `Func_finland_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="9eb47-282">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="9eb47-282">Keywords</span></span>

#### <a name="keywordsfinlandeussnorequivalent"></a><span data-ttu-id="9eb47-283">Keywords_finland_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="9eb47-283">Keywords_finland_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="9eb47-284">identification number</span><span class="sxs-lookup"><span data-stu-id="9eb47-284">identification number</span></span>
  
<span data-ttu-id="9eb47-285">identificador personal</span><span class="sxs-lookup"><span data-stu-id="9eb47-285">personal id</span></span>
  
<span data-ttu-id="9eb47-286">número de identidad</span><span class="sxs-lookup"><span data-stu-id="9eb47-286">identity number</span></span>
  
<span data-ttu-id="9eb47-287">número de identificación nacional finlandesa</span><span class="sxs-lookup"><span data-stu-id="9eb47-287">finnish national id number</span></span>
  
<span data-ttu-id="9eb47-288">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="9eb47-288">personalidnumber#</span></span>
  
<span data-ttu-id="9eb47-289">national identification number</span><span class="sxs-lookup"><span data-stu-id="9eb47-289">national identification number</span></span>
  
<span data-ttu-id="9eb47-290">número de identificador</span><span class="sxs-lookup"><span data-stu-id="9eb47-290">id number</span></span>
  
<span data-ttu-id="9eb47-291">n.º de identificación nacional</span><span class="sxs-lookup"><span data-stu-id="9eb47-291">national id no.</span></span>
  
<span data-ttu-id="9eb47-292">número de identificación nacional</span><span class="sxs-lookup"><span data-stu-id="9eb47-292">national id number</span></span>
  
<span data-ttu-id="9eb47-293">identificador no</span><span class="sxs-lookup"><span data-stu-id="9eb47-293">id no</span></span>
  
<span data-ttu-id="9eb47-294">tunnistenumero</span><span class="sxs-lookup"><span data-stu-id="9eb47-294">tunnistenumero</span></span>
  
<span data-ttu-id="9eb47-295">henkilötunnus</span><span class="sxs-lookup"><span data-stu-id="9eb47-295">henkilötunnus</span></span>
  
<span data-ttu-id="9eb47-296">yksilöllinen henkilökohtainen tunnistenumero</span><span class="sxs-lookup"><span data-stu-id="9eb47-296">yksilöllinen henkilökohtainen tunnistenumero</span></span>
  
<span data-ttu-id="9eb47-297">Ainutlaatuinen henkilökohtainen Tunnus</span><span class="sxs-lookup"><span data-stu-id="9eb47-297">ainutlaatuinen henkilökohtainen tunnus</span></span>
  
<span data-ttu-id="9eb47-298">identiteetti numero</span><span class="sxs-lookup"><span data-stu-id="9eb47-298">identiteetti numero</span></span>
  
<span data-ttu-id="9eb47-299">Suomen Kansallinen henkilötunnus</span><span class="sxs-lookup"><span data-stu-id="9eb47-299">suomen kansallinen henkilötunnus</span></span>
  
<span data-ttu-id="9eb47-300">henkilötunnusnumero #</span><span class="sxs-lookup"><span data-stu-id="9eb47-300">henkilötunnusnumero#</span></span>
  
<span data-ttu-id="9eb47-301">kansallisen tunnistenumero</span><span class="sxs-lookup"><span data-stu-id="9eb47-301">kansallisen tunnistenumero</span></span>
  
<span data-ttu-id="9eb47-302">tunnusnumero</span><span class="sxs-lookup"><span data-stu-id="9eb47-302">tunnusnumero</span></span>
  
<span data-ttu-id="9eb47-303">Kansallinen Tunnus numero</span><span class="sxs-lookup"><span data-stu-id="9eb47-303">kansallinen tunnus numero</span></span>
  
<span data-ttu-id="9eb47-304">hetu</span><span class="sxs-lookup"><span data-stu-id="9eb47-304">hetu</span></span>
  
## <a name="france"></a><span data-ttu-id="9eb47-305">Francia</span><span class="sxs-lookup"><span data-stu-id="9eb47-305">France</span></span>

<span data-ttu-id="9eb47-306">Para obtener más información, consulte la sección "número de la seguridad social de Francia (INSEE)" en [Qué buscan los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="9eb47-306">For details, see the section "France Social Security Number (INSEE)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="germany"></a><span data-ttu-id="9eb47-307">Alemania</span><span class="sxs-lookup"><span data-stu-id="9eb47-307">Germany</span></span>

<span data-ttu-id="9eb47-308">Para obtener más información, consulte la sección "número de tarjeta de identidades Alemania" en [Qué buscan los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="9eb47-308">For details, see the section "Germany Identity Card Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="greece"></a><span data-ttu-id="9eb47-309">Grecia</span><span class="sxs-lookup"><span data-stu-id="9eb47-309">Greece</span></span>

<span data-ttu-id="9eb47-310">Para obtener más información, consulte la sección "tarjeta de identificación nacional de Grecia" en [Qué buscan los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="9eb47-310">For details, see the section "Greece National ID Card" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="hungary"></a><span data-ttu-id="9eb47-311">Hungría</span><span class="sxs-lookup"><span data-stu-id="9eb47-311">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="9eb47-312">Dé</span><span class="sxs-lookup"><span data-stu-id="9eb47-312">Format</span></span>

<span data-ttu-id="9eb47-313">Nueve dígitos sin espacios y delimitadores</span><span class="sxs-lookup"><span data-stu-id="9eb47-313">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="9eb47-314">Patrón</span><span class="sxs-lookup"><span data-stu-id="9eb47-314">Pattern</span></span>

<span data-ttu-id="9eb47-315">Nueve dígitos</span><span class="sxs-lookup"><span data-stu-id="9eb47-315">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="9eb47-316">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="9eb47-316">Checksum</span></span>

<span data-ttu-id="9eb47-317">Sí</span><span class="sxs-lookup"><span data-stu-id="9eb47-317">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="9eb47-318">Definición</span><span class="sxs-lookup"><span data-stu-id="9eb47-318">Definition</span></span>

<span data-ttu-id="9eb47-319">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="9eb47-319">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9eb47-320">La función `Func_hungary_eu_ssn_or_equivalent` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="9eb47-320">The function  `Func_hungary_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="9eb47-321">Se encuentra una `Keywords_hungary_eu_ssn_or_equivalent` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="9eb47-321">A keyword from  `Keywords_hungary_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="9eb47-322">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="9eb47-322">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9eb47-323">La función `Func_hungary_eu_ssn_or_equivalent` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="9eb47-323">The function  `Func_hungary_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="9eb47-324">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="9eb47-324">Keywords</span></span>

#### <a name="keywordshungaryeussnorequivalent"></a><span data-ttu-id="9eb47-325">Keywords_hungary_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="9eb47-325">Keywords_hungary_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="9eb47-326">número de la seguridad social húngara</span><span class="sxs-lookup"><span data-stu-id="9eb47-326">hungarian social security number</span></span>
  
<span data-ttu-id="9eb47-327">social security number</span><span class="sxs-lookup"><span data-stu-id="9eb47-327">social security number</span></span>
  
<span data-ttu-id="9eb47-328">NúmeroSeguridadSocial</span><span class="sxs-lookup"><span data-stu-id="9eb47-328">socialsecuritynumber#</span></span>
  
<span data-ttu-id="9eb47-329">hssn #</span><span class="sxs-lookup"><span data-stu-id="9eb47-329">hssn#</span></span>
  
<span data-ttu-id="9eb47-330">socialsecuritynno</span><span class="sxs-lookup"><span data-stu-id="9eb47-330">socialsecuritynno</span></span>
  
<span data-ttu-id="9eb47-331">hssn</span><span class="sxs-lookup"><span data-stu-id="9eb47-331">hssn</span></span>
  
<span data-ttu-id="9eb47-332">Taj</span><span class="sxs-lookup"><span data-stu-id="9eb47-332">taj</span></span>
  
<span data-ttu-id="9eb47-333">Taj #</span><span class="sxs-lookup"><span data-stu-id="9eb47-333">taj#</span></span>
  
<span data-ttu-id="9eb47-334">SSN</span><span class="sxs-lookup"><span data-stu-id="9eb47-334">ssn</span></span>
  
<span data-ttu-id="9eb47-335">SSN</span><span class="sxs-lookup"><span data-stu-id="9eb47-335">ssn#</span></span>
  
<span data-ttu-id="9eb47-336">n.º de seguridad social</span><span class="sxs-lookup"><span data-stu-id="9eb47-336">social security no</span></span>
  
<span data-ttu-id="9eb47-337">áfa</span><span class="sxs-lookup"><span data-stu-id="9eb47-337">áfa</span></span>
  
<span data-ttu-id="9eb47-338">közösségi adószám</span><span class="sxs-lookup"><span data-stu-id="9eb47-338">közösségi adószám</span></span>
  
<span data-ttu-id="9eb47-339">Általános forgalmi adó szám</span><span class="sxs-lookup"><span data-stu-id="9eb47-339">általános forgalmi adó szám</span></span>
  
<span data-ttu-id="9eb47-340">hozzáadottérték adó</span><span class="sxs-lookup"><span data-stu-id="9eb47-340">hozzáadottérték adó</span></span>
  
<span data-ttu-id="9eb47-341">áfa szám</span><span class="sxs-lookup"><span data-stu-id="9eb47-341">áfa szám</span></span>
  
<span data-ttu-id="9eb47-342">Magyar áfa szám</span><span class="sxs-lookup"><span data-stu-id="9eb47-342">magyar áfa szám</span></span>
  
## <a name="portugal"></a><span data-ttu-id="9eb47-343">Portugal</span><span class="sxs-lookup"><span data-stu-id="9eb47-343">Portugal</span></span>

<span data-ttu-id="9eb47-344">Para obtener más información, consulte la sección "número de tarjeta de ciudadano de Portugal" en [Qué buscan los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="9eb47-344">For details, see the section "Portugal Citizen Card Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="spain"></a><span data-ttu-id="9eb47-345">España</span><span class="sxs-lookup"><span data-stu-id="9eb47-345">Spain</span></span>

<span data-ttu-id="9eb47-346">Para obtener más información, consulte la sección "número de la seguridad social de España (SSN)" en [Qué buscan los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="9eb47-346">For details, see the section "Spain Social Security Number (SSN)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="sweden"></a><span data-ttu-id="9eb47-347">Suecia</span><span class="sxs-lookup"><span data-stu-id="9eb47-347">Sweden</span></span>

### <a name="format"></a><span data-ttu-id="9eb47-348">Dé</span><span class="sxs-lookup"><span data-stu-id="9eb47-348">Format</span></span>

<span data-ttu-id="9eb47-349">12 dígitos sin espacios y delimitadores</span><span class="sxs-lookup"><span data-stu-id="9eb47-349">12 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="9eb47-350">Patrón</span><span class="sxs-lookup"><span data-stu-id="9eb47-350">Pattern</span></span>

<span data-ttu-id="9eb47-351">12 dígitos:</span><span class="sxs-lookup"><span data-stu-id="9eb47-351">12 digits:</span></span>
  
-  <span data-ttu-id="9eb47-352">Ocho dígitos que corresponden a la fecha de nacimiento (AAAAMMDD)</span><span class="sxs-lookup"><span data-stu-id="9eb47-352">Eight digits that correspond to the birth date (YYYYMMDD)</span></span> 
    
- <span data-ttu-id="9eb47-353">Tres dígitos que corresponden a un número de serie en el que:</span><span class="sxs-lookup"><span data-stu-id="9eb47-353">Three digits that correspond to a serial number where:</span></span> 
    
  - <span data-ttu-id="9eb47-354">El último dígito del número de serie indica el sexo por la asignación de un número impar para macho y un número par para hembras</span><span class="sxs-lookup"><span data-stu-id="9eb47-354">The last digit in the serial number indicates gender by the assignment of an odd number for male and an even number for female</span></span>
    
  - <span data-ttu-id="9eb47-355">Hasta 1990, la asignación de número de serie que se corresponde con el condado en el que nació el portador del número o (si nació antes de 1947) donde estuvo viviendo, de acuerdo con los registros fiscales, el 1 de enero de 1947, con un código especial (por lo general, 9 como el séptimo dígito) para Immigrants</span><span class="sxs-lookup"><span data-stu-id="9eb47-355">Up to 1990, the assignment of serial number corresponded to the county where the bearer of the number was born or (if born before 1947) where he/she had been living, according to tax records, on January 1, 1947, with a special code (usually 9 as the 7th digit) for immigrants</span></span> 
    
- <span data-ttu-id="9eb47-356">Un dígito de control</span><span class="sxs-lookup"><span data-stu-id="9eb47-356">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="9eb47-357">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="9eb47-357">Checksum</span></span>

<span data-ttu-id="9eb47-358">Sí</span><span class="sxs-lookup"><span data-stu-id="9eb47-358">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="9eb47-359">Definición</span><span class="sxs-lookup"><span data-stu-id="9eb47-359">Definition</span></span>

<span data-ttu-id="9eb47-360">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="9eb47-360">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9eb47-361">La función `Func_sweden_eu_ssn_or_equivalent` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="9eb47-361">The function  `Func_sweden_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="9eb47-362">Se encuentra una `Keywords_sweden_eu_ssn_or_equivalent` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="9eb47-362">A keyword from  `Keywords_sweden_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="9eb47-363">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="9eb47-363">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9eb47-364">La función `Func_sweden_eu_ssn_or_equivalent` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="9eb47-364">The function  `Func_sweden_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="9eb47-365">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="9eb47-365">Keywords</span></span>

#### <a name="keywordsswedeneussnorequivalent"></a><span data-ttu-id="9eb47-366">Keywords_sweden_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="9eb47-366">Keywords_sweden_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="9eb47-367">número de identificación personal</span><span class="sxs-lookup"><span data-stu-id="9eb47-367">personal id number</span></span>
  
<span data-ttu-id="9eb47-368">identification number</span><span class="sxs-lookup"><span data-stu-id="9eb47-368">identification number</span></span>
  
<span data-ttu-id="9eb47-369">número de identificación personal</span><span class="sxs-lookup"><span data-stu-id="9eb47-369">personal id no</span></span>
  
<span data-ttu-id="9eb47-370">n.º de identidad</span><span class="sxs-lookup"><span data-stu-id="9eb47-370">identity no</span></span>
  
<span data-ttu-id="9eb47-371">n.º de identificación</span><span class="sxs-lookup"><span data-stu-id="9eb47-371">identification no</span></span>
  
<span data-ttu-id="9eb47-372">n.º de identificación personal</span><span class="sxs-lookup"><span data-stu-id="9eb47-372">personal identification no</span></span>
  
<span data-ttu-id="9eb47-373">identificador personnummer</span><span class="sxs-lookup"><span data-stu-id="9eb47-373">personnummer id</span></span>
  
<span data-ttu-id="9eb47-374">personligt ID-Nummer</span><span class="sxs-lookup"><span data-stu-id="9eb47-374">personligt id-nummer</span></span>
  
<span data-ttu-id="9eb47-375">unikt ID-Nummer</span><span class="sxs-lookup"><span data-stu-id="9eb47-375">unikt id-nummer</span></span>
  
<span data-ttu-id="9eb47-376">personnummer</span><span class="sxs-lookup"><span data-stu-id="9eb47-376">personnummer</span></span>
  
<span data-ttu-id="9eb47-377">identifikationsnumret</span><span class="sxs-lookup"><span data-stu-id="9eb47-377">identifikationsnumret</span></span>
  
<span data-ttu-id="9eb47-378">personnummer #</span><span class="sxs-lookup"><span data-stu-id="9eb47-378">personnummer#</span></span>
  
<span data-ttu-id="9eb47-379">identifikationsnumret #</span><span class="sxs-lookup"><span data-stu-id="9eb47-379">identifikationsnumret#</span></span>
  
## <a name="see-also"></a><span data-ttu-id="9eb47-380">Vea también</span><span class="sxs-lookup"><span data-stu-id="9eb47-380">See also</span></span>

[<span data-ttu-id="9eb47-381">Qué buscan los tipos de información confidencial</span><span class="sxs-lookup"><span data-stu-id="9eb47-381">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

