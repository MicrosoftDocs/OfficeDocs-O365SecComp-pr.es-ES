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
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32255558"
---
# <a name="eu-social-security-number-or-equivalent-id"></a><span data-ttu-id="d4ee0-104">Número de la seguridad social de la UE o identificador equivalente</span><span class="sxs-lookup"><span data-stu-id="d4ee0-104">EU Social Security Number or Equivalent ID</span></span>

<span data-ttu-id="d4ee0-105">En este tema se muestra qué busca una directiva de prevención de pérdida de datos (DLP) cuando detecta el tipo de información confidencial del número de la seguridad social (SSN) o del identificador equivalente de la UE.</span><span class="sxs-lookup"><span data-stu-id="d4ee0-105">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Social Security Number (SSN) or Equivalent ID sensitive information type.</span></span> <span data-ttu-id="d4ee0-106">Este tipo de información confidencial define distintos patrones, palabras clave y otras pruebas para cada país.</span><span class="sxs-lookup"><span data-stu-id="d4ee0-106">This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="d4ee0-107">Austria</span><span class="sxs-lookup"><span data-stu-id="d4ee0-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="d4ee0-108">Formato</span><span class="sxs-lookup"><span data-stu-id="d4ee0-108">Format</span></span>

<span data-ttu-id="d4ee0-109">10 dígitos en el formato especificado</span><span class="sxs-lookup"><span data-stu-id="d4ee0-109">10 digits in the specified format</span></span>
  
### <a name="pattern"></a><span data-ttu-id="d4ee0-110">Patrón</span><span class="sxs-lookup"><span data-stu-id="d4ee0-110">Pattern</span></span>

<span data-ttu-id="d4ee0-111">10 dígitos:</span><span class="sxs-lookup"><span data-stu-id="d4ee0-111">10 digits:</span></span>
  
-  <span data-ttu-id="d4ee0-112">Tres dígitos que corresponden a un número de serie</span><span class="sxs-lookup"><span data-stu-id="d4ee0-112">Three digits that correspond to a serial number</span></span> 
    
- <span data-ttu-id="d4ee0-113">Un dígito de control</span><span class="sxs-lookup"><span data-stu-id="d4ee0-113">One check digit</span></span>
    
- <span data-ttu-id="d4ee0-114">Seis dígitos que corresponden a la fecha de nacimiento (DDMMAA)</span><span class="sxs-lookup"><span data-stu-id="d4ee0-114">Six digits that correspond to the birth date (DDMMYY)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="d4ee0-115">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="d4ee0-115">Checksum</span></span>

<span data-ttu-id="d4ee0-116">Sí</span><span class="sxs-lookup"><span data-stu-id="d4ee0-116">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="d4ee0-117">Definición</span><span class="sxs-lookup"><span data-stu-id="d4ee0-117">Definition</span></span>

<span data-ttu-id="d4ee0-118">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="d4ee0-118">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d4ee0-119">La función `Func_austria_eu_ssn_or_equivalent` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="d4ee0-119">The function  `Func_austria_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="d4ee0-120">Se encuentra una `Keywords_austria_eu_ssn_or_equivalent` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="d4ee0-120">A keyword from  `Keywords_austria_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="d4ee0-121">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="d4ee0-121">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d4ee0-122">La función `Func_austria_eu_ssn_or_equivalent` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="d4ee0-122">The function  `Func_austria_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="d4ee0-123">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="d4ee0-123">Keywords</span></span>

#### <a name="keywordsaustriaeussnorequivalent"></a><span data-ttu-id="d4ee0-124">Keywords_austria_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="d4ee0-124">Keywords_austria_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="d4ee0-125">n.º de seguridad social</span><span class="sxs-lookup"><span data-stu-id="d4ee0-125">social security no</span></span>
  
<span data-ttu-id="d4ee0-126">social security number</span><span class="sxs-lookup"><span data-stu-id="d4ee0-126">social security number</span></span>
  
<span data-ttu-id="d4ee0-127">social security code</span><span class="sxs-lookup"><span data-stu-id="d4ee0-127">social security code</span></span>
  
<span data-ttu-id="d4ee0-128">número de seguro</span><span class="sxs-lookup"><span data-stu-id="d4ee0-128">insurance number</span></span>
  
<span data-ttu-id="d4ee0-129">SSN austriaco</span><span class="sxs-lookup"><span data-stu-id="d4ee0-129">austrian ssn</span></span>
  
<span data-ttu-id="d4ee0-130">SSN</span><span class="sxs-lookup"><span data-stu-id="d4ee0-130">ssn#</span></span>
  
<span data-ttu-id="d4ee0-131">SSN</span><span class="sxs-lookup"><span data-stu-id="d4ee0-131">ssn</span></span>
  
<span data-ttu-id="d4ee0-132">código de seguro</span><span class="sxs-lookup"><span data-stu-id="d4ee0-132">insurance code</span></span>
  
<span data-ttu-id="d4ee0-133">número de código de seguro</span><span class="sxs-lookup"><span data-stu-id="d4ee0-133">insurance code#</span></span>
  
<span data-ttu-id="d4ee0-134">socialsecurityno #</span><span class="sxs-lookup"><span data-stu-id="d4ee0-134">socialsecurityno#</span></span>
  
<span data-ttu-id="d4ee0-135">sozialversicherungsnummer</span><span class="sxs-lookup"><span data-stu-id="d4ee0-135">sozialversicherungsnummer</span></span>
  
<span data-ttu-id="d4ee0-136">Soziale Sicherheit kein</span><span class="sxs-lookup"><span data-stu-id="d4ee0-136">soziale sicherheit kein</span></span>
  
<span data-ttu-id="d4ee0-137">versicherungsnummer</span><span class="sxs-lookup"><span data-stu-id="d4ee0-137">versicherungsnummer</span></span>
  
## <a name="belgium"></a><span data-ttu-id="d4ee0-138">Bélgica</span><span class="sxs-lookup"><span data-stu-id="d4ee0-138">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="d4ee0-139">Formato</span><span class="sxs-lookup"><span data-stu-id="d4ee0-139">Format</span></span>

<span data-ttu-id="d4ee0-140">11 dígitos sin espacios ni delimitadores</span><span class="sxs-lookup"><span data-stu-id="d4ee0-140">11 digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="d4ee0-141">Patrón</span><span class="sxs-lookup"><span data-stu-id="d4ee0-141">Pattern</span></span>

<span data-ttu-id="d4ee0-142">11 dígitos</span><span class="sxs-lookup"><span data-stu-id="d4ee0-142">11 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="d4ee0-143">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="d4ee0-143">Checksum</span></span>

<span data-ttu-id="d4ee0-144">Sí</span><span class="sxs-lookup"><span data-stu-id="d4ee0-144">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="d4ee0-145">Definición</span><span class="sxs-lookup"><span data-stu-id="d4ee0-145">Definition</span></span>

<span data-ttu-id="d4ee0-146">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="d4ee0-146">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d4ee0-147">La función `Func_belgium_eu_ssn_or_equivalent` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="d4ee0-147">The function  `Func_belgium_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="d4ee0-148">Se encuentra una `Keywords_belgium_eu_ssn_or_equivalent` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="d4ee0-148">A keyword from  `Keywords_belgium_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="d4ee0-149">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="d4ee0-149">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d4ee0-150">La función `Func_belgium_eu_ssn_or_equivalent` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="d4ee0-150">The function  `Func_belgium_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="d4ee0-151">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="d4ee0-151">Keywords</span></span>

#### <a name="keywordsbelgiumeussnorequivalent"></a><span data-ttu-id="d4ee0-152">Keywords_belgium_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="d4ee0-152">Keywords_belgium_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="d4ee0-153">número nacional belga</span><span class="sxs-lookup"><span data-stu-id="d4ee0-153">belgian national number</span></span>
  
<span data-ttu-id="d4ee0-154">número nacional</span><span class="sxs-lookup"><span data-stu-id="d4ee0-154">national number</span></span>
  
<span data-ttu-id="d4ee0-155">social security number</span><span class="sxs-lookup"><span data-stu-id="d4ee0-155">social security number</span></span>
  
<span data-ttu-id="d4ee0-156">nationalnumber #</span><span class="sxs-lookup"><span data-stu-id="d4ee0-156">nationalnumber#</span></span>
  
<span data-ttu-id="d4ee0-157">SSN</span><span class="sxs-lookup"><span data-stu-id="d4ee0-157">ssn#</span></span>
  
<span data-ttu-id="d4ee0-158">SSN</span><span class="sxs-lookup"><span data-stu-id="d4ee0-158">ssn</span></span>
  
<span data-ttu-id="d4ee0-159">nationalnumber</span><span class="sxs-lookup"><span data-stu-id="d4ee0-159">nationalnumber</span></span>
  
<span data-ttu-id="d4ee0-160">BNN #</span><span class="sxs-lookup"><span data-stu-id="d4ee0-160">bnn#</span></span>
  
<span data-ttu-id="d4ee0-161">BNN</span><span class="sxs-lookup"><span data-stu-id="d4ee0-161">bnn</span></span>
  
<span data-ttu-id="d4ee0-162">número de identificación personal</span><span class="sxs-lookup"><span data-stu-id="d4ee0-162">personal id number</span></span>
  
<span data-ttu-id="d4ee0-163">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="d4ee0-163">personalidnumber#</span></span>
  
<span data-ttu-id="d4ee0-164">numéro nacional</span><span class="sxs-lookup"><span data-stu-id="d4ee0-164">numéro national</span></span>
  
<span data-ttu-id="d4ee0-165">numéro de sécurité</span><span class="sxs-lookup"><span data-stu-id="d4ee0-165">numéro de sécurité</span></span>
  
<span data-ttu-id="d4ee0-166">numéro d'assuré</span><span class="sxs-lookup"><span data-stu-id="d4ee0-166">numéro d'assuré</span></span>
  
<span data-ttu-id="d4ee0-167">Nacional del identificador</span><span class="sxs-lookup"><span data-stu-id="d4ee0-167">identifiant national</span></span>
  
<span data-ttu-id="d4ee0-168">identifiantnational #</span><span class="sxs-lookup"><span data-stu-id="d4ee0-168">identifiantnational#</span></span>
  
<span data-ttu-id="d4ee0-169">numéronational #</span><span class="sxs-lookup"><span data-stu-id="d4ee0-169">numéronational#</span></span>
  
## <a name="croatia"></a><span data-ttu-id="d4ee0-170">Croacia</span><span class="sxs-lookup"><span data-stu-id="d4ee0-170">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="d4ee0-171">Formato</span><span class="sxs-lookup"><span data-stu-id="d4ee0-171">Format</span></span>

<span data-ttu-id="d4ee0-172">11 dígitos sin espacios y delimitadores</span><span class="sxs-lookup"><span data-stu-id="d4ee0-172">11 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="d4ee0-173">Patrón</span><span class="sxs-lookup"><span data-stu-id="d4ee0-173">Pattern</span></span>

 <span data-ttu-id="d4ee0-174">11 dígitos:</span><span class="sxs-lookup"><span data-stu-id="d4ee0-174">11 digits:</span></span> 
  
-  <span data-ttu-id="d4ee0-175">Diez dígitos</span><span class="sxs-lookup"><span data-stu-id="d4ee0-175">Ten digits</span></span> 
    
- <span data-ttu-id="d4ee0-176">Un dígito de control</span><span class="sxs-lookup"><span data-stu-id="d4ee0-176">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="d4ee0-177">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="d4ee0-177">Checksum</span></span>

<span data-ttu-id="d4ee0-178">Sí</span><span class="sxs-lookup"><span data-stu-id="d4ee0-178">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="d4ee0-179">Definición</span><span class="sxs-lookup"><span data-stu-id="d4ee0-179">Definition</span></span>

<span data-ttu-id="d4ee0-180">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="d4ee0-180">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d4ee0-181">La función `Func_croatia_eu_ssn_or_equivalent` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="d4ee0-181">The function  `Func_croatia_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="d4ee0-182">Se encuentra una `Keywords_croatia_eu_ssn_or_equivalent` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="d4ee0-182">A keyword from  `Keywords_croatia_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="d4ee0-183">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="d4ee0-183">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d4ee0-184">La función `Func_croatia_eu_ssn_or_equivalent` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="d4ee0-184">The function  `Func_croatia_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="d4ee0-185">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="d4ee0-185">Keywords</span></span>

#### <a name="keywordscroatiaeussnorequivalent"></a><span data-ttu-id="d4ee0-186">Keywords_croatia_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="d4ee0-186">Keywords_croatia_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="d4ee0-187">número de identificación personal</span><span class="sxs-lookup"><span data-stu-id="d4ee0-187">personal identification number</span></span>
  
<span data-ttu-id="d4ee0-188">número de ciudadano principal</span><span class="sxs-lookup"><span data-stu-id="d4ee0-188">master citizen number</span></span>
  
<span data-ttu-id="d4ee0-189">national identification number</span><span class="sxs-lookup"><span data-stu-id="d4ee0-189">national identification number</span></span>
  
<span data-ttu-id="d4ee0-190">social security number</span><span class="sxs-lookup"><span data-stu-id="d4ee0-190">social security number</span></span>
  
<span data-ttu-id="d4ee0-191">nationalnumber #</span><span class="sxs-lookup"><span data-stu-id="d4ee0-191">nationalnumber#</span></span>
  
<span data-ttu-id="d4ee0-192">SSN</span><span class="sxs-lookup"><span data-stu-id="d4ee0-192">ssn#</span></span>
  
<span data-ttu-id="d4ee0-193">SSN</span><span class="sxs-lookup"><span data-stu-id="d4ee0-193">ssn</span></span>
  
<span data-ttu-id="d4ee0-194">nationalnumber</span><span class="sxs-lookup"><span data-stu-id="d4ee0-194">nationalnumber</span></span>
  
<span data-ttu-id="d4ee0-195">BNN #</span><span class="sxs-lookup"><span data-stu-id="d4ee0-195">bnn#</span></span>
  
<span data-ttu-id="d4ee0-196">BNN</span><span class="sxs-lookup"><span data-stu-id="d4ee0-196">bnn</span></span>
  
<span data-ttu-id="d4ee0-197">número de identificación personal</span><span class="sxs-lookup"><span data-stu-id="d4ee0-197">personal id number</span></span>
  
<span data-ttu-id="d4ee0-198">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="d4ee0-198">personalidnumber#</span></span>
  
<span data-ttu-id="d4ee0-199">OIB</span><span class="sxs-lookup"><span data-stu-id="d4ee0-199">oib</span></span>
  
<span data-ttu-id="d4ee0-200">osobni identifikacijski broj</span><span class="sxs-lookup"><span data-stu-id="d4ee0-200">osobni identifikacijski broj</span></span>
  
## <a name="czech-republic"></a><span data-ttu-id="d4ee0-201">Chequia</span><span class="sxs-lookup"><span data-stu-id="d4ee0-201">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="d4ee0-202">Formato</span><span class="sxs-lookup"><span data-stu-id="d4ee0-202">Format</span></span>

<span data-ttu-id="d4ee0-203">Diez dígitos y una barra diagonal inversa en el patrón especificado</span><span class="sxs-lookup"><span data-stu-id="d4ee0-203">Ten digits and a backslash in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="d4ee0-204">Patrón</span><span class="sxs-lookup"><span data-stu-id="d4ee0-204">Pattern</span></span>

<span data-ttu-id="d4ee0-205">Diez dígitos y una barra diagonal inversa:</span><span class="sxs-lookup"><span data-stu-id="d4ee0-205">Ten digits and a backslash:</span></span>
  
- <span data-ttu-id="d4ee0-206">Seis dígitos que corresponden a la fecha de nacimiento (AAMMDD):</span><span class="sxs-lookup"><span data-stu-id="d4ee0-206">Six digits that correspond to the birth date (YYMMDD):</span></span> 
    
- <span data-ttu-id="d4ee0-207">Una barra diagonal inversa</span><span class="sxs-lookup"><span data-stu-id="d4ee0-207">A backslash</span></span>
    
- <span data-ttu-id="d4ee0-208">Tres dígitos que corresponden a un número de serie que separa a los empleados nacidos en la misma fecha.</span><span class="sxs-lookup"><span data-stu-id="d4ee0-208">Three digits that correspond to a serial number that separates persons born on the same date</span></span>
    
- <span data-ttu-id="d4ee0-209">Un dígito de control</span><span class="sxs-lookup"><span data-stu-id="d4ee0-209">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="d4ee0-210">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="d4ee0-210">Checksum</span></span>

<span data-ttu-id="d4ee0-211">Sí</span><span class="sxs-lookup"><span data-stu-id="d4ee0-211">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="d4ee0-212">Definición</span><span class="sxs-lookup"><span data-stu-id="d4ee0-212">Definition</span></span>

<span data-ttu-id="d4ee0-213">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="d4ee0-213">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d4ee0-214">La función `Func_czech_republic_eu_ssn_or_equivalent` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="d4ee0-214">The function  `Func_czech_republic_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="d4ee0-215">Se encuentra una `Keywords_czech_republic_eu_ssn_or_equivalent` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="d4ee0-215">A keyword from  `Keywords_czech_republic_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="d4ee0-216">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="d4ee0-216">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d4ee0-217">La función `Func_czech_republic_eu_ssn_or_equivalent` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="d4ee0-217">The function  `Func_czech_republic_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="d4ee0-218">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="d4ee0-218">Keywords</span></span>

#### <a name="keywordsczechrepubliceussnorequivalent"></a><span data-ttu-id="d4ee0-219">Keywords_czech_republic_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="d4ee0-219">Keywords_czech_republic_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="d4ee0-220">número de nacimiento</span><span class="sxs-lookup"><span data-stu-id="d4ee0-220">birth number</span></span>
  
<span data-ttu-id="d4ee0-221">national identification number</span><span class="sxs-lookup"><span data-stu-id="d4ee0-221">national identification number</span></span>
  
<span data-ttu-id="d4ee0-222">número de identificación personal</span><span class="sxs-lookup"><span data-stu-id="d4ee0-222">personal identification number</span></span>
  
<span data-ttu-id="d4ee0-223">social security number</span><span class="sxs-lookup"><span data-stu-id="d4ee0-223">social security number</span></span>
  
<span data-ttu-id="d4ee0-224">nationalnumber #</span><span class="sxs-lookup"><span data-stu-id="d4ee0-224">nationalnumber#</span></span>
  
<span data-ttu-id="d4ee0-225">SSN</span><span class="sxs-lookup"><span data-stu-id="d4ee0-225">ssn#</span></span>
  
<span data-ttu-id="d4ee0-226">SSN</span><span class="sxs-lookup"><span data-stu-id="d4ee0-226">ssn</span></span>
  
<span data-ttu-id="d4ee0-227">número nacional</span><span class="sxs-lookup"><span data-stu-id="d4ee0-227">national number</span></span>
  
<span data-ttu-id="d4ee0-228">número de identificación personal</span><span class="sxs-lookup"><span data-stu-id="d4ee0-228">personal id number</span></span>
  
<span data-ttu-id="d4ee0-229">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="d4ee0-229">personalidnumber#</span></span>
  
<span data-ttu-id="d4ee0-230">rč</span><span class="sxs-lookup"><span data-stu-id="d4ee0-230">rč</span></span>
  
<span data-ttu-id="d4ee0-231">rodné číslo</span><span class="sxs-lookup"><span data-stu-id="d4ee0-231">rodné číslo</span></span>
  
<span data-ttu-id="d4ee0-232">rodne cislo</span><span class="sxs-lookup"><span data-stu-id="d4ee0-232">rodne cislo</span></span>
  
## <a name="denmark"></a><span data-ttu-id="d4ee0-233">Dinamarca</span><span class="sxs-lookup"><span data-stu-id="d4ee0-233">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="d4ee0-234">Formato</span><span class="sxs-lookup"><span data-stu-id="d4ee0-234">Format</span></span>

<span data-ttu-id="d4ee0-235">Diez dígitos y un guión en el patrón especificado</span><span class="sxs-lookup"><span data-stu-id="d4ee0-235">Ten digits and a hyphen in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="d4ee0-236">Patrón</span><span class="sxs-lookup"><span data-stu-id="d4ee0-236">Pattern</span></span>

<span data-ttu-id="d4ee0-237">Diez dígitos y un guión:</span><span class="sxs-lookup"><span data-stu-id="d4ee0-237">Ten digits and a hyphen:</span></span>
  
- <span data-ttu-id="d4ee0-238">Seis dígitos que corresponden a la fecha de nacimiento (DDMMAA)</span><span class="sxs-lookup"><span data-stu-id="d4ee0-238">Six digits that correspond to the birth date (DDMMYY)</span></span> 
    
- <span data-ttu-id="d4ee0-239">Un guión </span><span class="sxs-lookup"><span data-stu-id="d4ee0-239">A hyphen</span></span>
    
- <span data-ttu-id="d4ee0-240">Cuatro dígitos que corresponden a un número de secuencia</span><span class="sxs-lookup"><span data-stu-id="d4ee0-240">Four digits that correspond to a sequence number</span></span>
    
### <a name="checksum"></a><span data-ttu-id="d4ee0-241">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="d4ee0-241">Checksum</span></span>

<span data-ttu-id="d4ee0-242">Sí</span><span class="sxs-lookup"><span data-stu-id="d4ee0-242">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="d4ee0-243">Definición</span><span class="sxs-lookup"><span data-stu-id="d4ee0-243">Definition</span></span>

<span data-ttu-id="d4ee0-244">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="d4ee0-244">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d4ee0-245">La función `Func_denmark_eu_ssn_or_equivalent` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="d4ee0-245">The function  `Func_denmark_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="d4ee0-246">Se encuentra una `Keywords_denmark_eu_ssn_or_equivalent` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="d4ee0-246">A keyword from  `Keywords_denmark_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="d4ee0-247">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="d4ee0-247">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d4ee0-248">La función `Func_denmark_eu_ssn_or_equivalent` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="d4ee0-248">The function  `Func_denmark_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="d4ee0-249">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="d4ee0-249">Keywords</span></span>

#### <a name="keywordsdenmarkeussnorequivalent"></a><span data-ttu-id="d4ee0-250">Keywords_denmark_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="d4ee0-250">Keywords_denmark_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="d4ee0-251">número de identificación personal</span><span class="sxs-lookup"><span data-stu-id="d4ee0-251">personal identification number</span></span>
  
<span data-ttu-id="d4ee0-252">national identification number</span><span class="sxs-lookup"><span data-stu-id="d4ee0-252">national identification number</span></span>
  
<span data-ttu-id="d4ee0-253">social security number</span><span class="sxs-lookup"><span data-stu-id="d4ee0-253">social security number</span></span>
  
<span data-ttu-id="d4ee0-254">nationalnumber #</span><span class="sxs-lookup"><span data-stu-id="d4ee0-254">nationalnumber#</span></span>
  
<span data-ttu-id="d4ee0-255">SSN</span><span class="sxs-lookup"><span data-stu-id="d4ee0-255">ssn#</span></span>
  
<span data-ttu-id="d4ee0-256">SSN</span><span class="sxs-lookup"><span data-stu-id="d4ee0-256">ssn</span></span>
  
<span data-ttu-id="d4ee0-257">número nacional</span><span class="sxs-lookup"><span data-stu-id="d4ee0-257">national number</span></span>
  
<span data-ttu-id="d4ee0-258">número de identificación personal</span><span class="sxs-lookup"><span data-stu-id="d4ee0-258">personal id number</span></span>
  
<span data-ttu-id="d4ee0-259">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="d4ee0-259">personalidnumber#</span></span>
  
<span data-ttu-id="d4ee0-260">CPR-Nummer</span><span class="sxs-lookup"><span data-stu-id="d4ee0-260">cpr-nummer</span></span>
  
<span data-ttu-id="d4ee0-261">personnummer</span><span class="sxs-lookup"><span data-stu-id="d4ee0-261">personnummer</span></span>
  
## <a name="finland"></a><span data-ttu-id="d4ee0-262">Finlandia</span><span class="sxs-lookup"><span data-stu-id="d4ee0-262">Finland</span></span>

### <a name="format"></a><span data-ttu-id="d4ee0-263">Formato</span><span class="sxs-lookup"><span data-stu-id="d4ee0-263">Format</span></span>

<span data-ttu-id="d4ee0-264">Una combinación de 11 caracteres en el formato especificado</span><span class="sxs-lookup"><span data-stu-id="d4ee0-264">An 11-character combination in the specified format</span></span>
  
### <a name="pattern"></a><span data-ttu-id="d4ee0-265">Patrón</span><span class="sxs-lookup"><span data-stu-id="d4ee0-265">Pattern</span></span>

<span data-ttu-id="d4ee0-266">Una combinación de 11 caracteres en el formato especificado:</span><span class="sxs-lookup"><span data-stu-id="d4ee0-266">An 11-character combination in the specified format:</span></span>
  
-  <span data-ttu-id="d4ee0-267">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="d4ee0-267">Six digits</span></span> 
    
- <span data-ttu-id="d4ee0-268">Una instancia de una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="d4ee0-268">One instance of one of the following:</span></span>
    
  - <span data-ttu-id="d4ee0-269">Símbolo más</span><span class="sxs-lookup"><span data-stu-id="d4ee0-269">Plus symbol</span></span>
    
  - <span data-ttu-id="d4ee0-270">Símbolo menos</span><span class="sxs-lookup"><span data-stu-id="d4ee0-270">Minus symbol</span></span>
    
  - <span data-ttu-id="d4ee0-271">La letra "A" (sin distinción entre mayúsculas y minúsculas)</span><span class="sxs-lookup"><span data-stu-id="d4ee0-271">The letter "A" (not case-sensitive)</span></span>
    
- <span data-ttu-id="d4ee0-272">Tres dígitos</span><span class="sxs-lookup"><span data-stu-id="d4ee0-272">Three digits</span></span>
    
- <span data-ttu-id="d4ee0-273">Una letra o un dígito</span><span class="sxs-lookup"><span data-stu-id="d4ee0-273">One letter or one digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="d4ee0-274">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="d4ee0-274">Checksum</span></span>

<span data-ttu-id="d4ee0-275">Sí</span><span class="sxs-lookup"><span data-stu-id="d4ee0-275">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="d4ee0-276">Definición</span><span class="sxs-lookup"><span data-stu-id="d4ee0-276">Definition</span></span>

<span data-ttu-id="d4ee0-277">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="d4ee0-277">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d4ee0-278">La función `Func_finland_eu_ssn_or_equivalent` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="d4ee0-278">The function  `Func_finland_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="d4ee0-279">Se encuentra una `Keywords_finland_eu_ssn_or_equivalent` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="d4ee0-279">A keyword from  `Keywords_finland_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="d4ee0-280">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="d4ee0-280">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d4ee0-281">La función `Func_finland_eu_ssn_or_equivalent` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="d4ee0-281">The function  `Func_finland_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="d4ee0-282">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="d4ee0-282">Keywords</span></span>

#### <a name="keywordsfinlandeussnorequivalent"></a><span data-ttu-id="d4ee0-283">Keywords_finland_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="d4ee0-283">Keywords_finland_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="d4ee0-284">identification number</span><span class="sxs-lookup"><span data-stu-id="d4ee0-284">identification number</span></span>
  
<span data-ttu-id="d4ee0-285">identificador personal</span><span class="sxs-lookup"><span data-stu-id="d4ee0-285">personal id</span></span>
  
<span data-ttu-id="d4ee0-286">número de identidad</span><span class="sxs-lookup"><span data-stu-id="d4ee0-286">identity number</span></span>
  
<span data-ttu-id="d4ee0-287">número de identificación nacional finlandesa</span><span class="sxs-lookup"><span data-stu-id="d4ee0-287">finnish national id number</span></span>
  
<span data-ttu-id="d4ee0-288">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="d4ee0-288">personalidnumber#</span></span>
  
<span data-ttu-id="d4ee0-289">national identification number</span><span class="sxs-lookup"><span data-stu-id="d4ee0-289">national identification number</span></span>
  
<span data-ttu-id="d4ee0-290">número de identificador</span><span class="sxs-lookup"><span data-stu-id="d4ee0-290">id number</span></span>
  
<span data-ttu-id="d4ee0-291">n.º de identificación nacional</span><span class="sxs-lookup"><span data-stu-id="d4ee0-291">national id no.</span></span>
  
<span data-ttu-id="d4ee0-292">número de identificación nacional</span><span class="sxs-lookup"><span data-stu-id="d4ee0-292">national id number</span></span>
  
<span data-ttu-id="d4ee0-293">identificador no</span><span class="sxs-lookup"><span data-stu-id="d4ee0-293">id no</span></span>
  
<span data-ttu-id="d4ee0-294">tunnistenumero</span><span class="sxs-lookup"><span data-stu-id="d4ee0-294">tunnistenumero</span></span>
  
<span data-ttu-id="d4ee0-295">henkilötunnus</span><span class="sxs-lookup"><span data-stu-id="d4ee0-295">henkilötunnus</span></span>
  
<span data-ttu-id="d4ee0-296">yksilöllinen henkilökohtainen tunnistenumero</span><span class="sxs-lookup"><span data-stu-id="d4ee0-296">yksilöllinen henkilökohtainen tunnistenumero</span></span>
  
<span data-ttu-id="d4ee0-297">Ainutlaatuinen henkilökohtainen Tunnus</span><span class="sxs-lookup"><span data-stu-id="d4ee0-297">ainutlaatuinen henkilökohtainen tunnus</span></span>
  
<span data-ttu-id="d4ee0-298">identiteetti numero</span><span class="sxs-lookup"><span data-stu-id="d4ee0-298">identiteetti numero</span></span>
  
<span data-ttu-id="d4ee0-299">Suomen Kansallinen henkilötunnus</span><span class="sxs-lookup"><span data-stu-id="d4ee0-299">suomen kansallinen henkilötunnus</span></span>
  
<span data-ttu-id="d4ee0-300">henkilötunnusnumero #</span><span class="sxs-lookup"><span data-stu-id="d4ee0-300">henkilötunnusnumero#</span></span>
  
<span data-ttu-id="d4ee0-301">kansallisen tunnistenumero</span><span class="sxs-lookup"><span data-stu-id="d4ee0-301">kansallisen tunnistenumero</span></span>
  
<span data-ttu-id="d4ee0-302">tunnusnumero</span><span class="sxs-lookup"><span data-stu-id="d4ee0-302">tunnusnumero</span></span>
  
<span data-ttu-id="d4ee0-303">Kansallinen Tunnus numero</span><span class="sxs-lookup"><span data-stu-id="d4ee0-303">kansallinen tunnus numero</span></span>
  
<span data-ttu-id="d4ee0-304">hetu</span><span class="sxs-lookup"><span data-stu-id="d4ee0-304">hetu</span></span>
  
## <a name="france"></a><span data-ttu-id="d4ee0-305">Francia</span><span class="sxs-lookup"><span data-stu-id="d4ee0-305">France</span></span>

<span data-ttu-id="d4ee0-306">Para obtener más información, consulte la sección "número de la seguridad social de Francia (INSEE)" en [Qué buscan los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="d4ee0-306">For details, see the section "France Social Security Number (INSEE)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="germany"></a><span data-ttu-id="d4ee0-307">Alemania</span><span class="sxs-lookup"><span data-stu-id="d4ee0-307">Germany</span></span>

<span data-ttu-id="d4ee0-308">Para obtener más información, consulte la sección "número de tarjeta de identidades Alemania" en [Qué buscan los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="d4ee0-308">For details, see the section "Germany Identity Card Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="greece"></a><span data-ttu-id="d4ee0-309">Grecia</span><span class="sxs-lookup"><span data-stu-id="d4ee0-309">Greece</span></span>

<span data-ttu-id="d4ee0-310">Para obtener más información, consulte la sección "tarjeta de identificación nacional de Grecia" en [Qué buscan los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="d4ee0-310">For details, see the section "Greece National ID Card" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="hungary"></a><span data-ttu-id="d4ee0-311">Hungría</span><span class="sxs-lookup"><span data-stu-id="d4ee0-311">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="d4ee0-312">Formato</span><span class="sxs-lookup"><span data-stu-id="d4ee0-312">Format</span></span>

<span data-ttu-id="d4ee0-313">Nueve dígitos sin espacios y delimitadores</span><span class="sxs-lookup"><span data-stu-id="d4ee0-313">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="d4ee0-314">Patrón</span><span class="sxs-lookup"><span data-stu-id="d4ee0-314">Pattern</span></span>

<span data-ttu-id="d4ee0-315">Nueve dígitos</span><span class="sxs-lookup"><span data-stu-id="d4ee0-315">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="d4ee0-316">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="d4ee0-316">Checksum</span></span>

<span data-ttu-id="d4ee0-317">Sí</span><span class="sxs-lookup"><span data-stu-id="d4ee0-317">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="d4ee0-318">Definición</span><span class="sxs-lookup"><span data-stu-id="d4ee0-318">Definition</span></span>

<span data-ttu-id="d4ee0-319">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="d4ee0-319">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d4ee0-320">La función `Func_hungary_eu_ssn_or_equivalent` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="d4ee0-320">The function  `Func_hungary_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="d4ee0-321">Se encuentra una `Keywords_hungary_eu_ssn_or_equivalent` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="d4ee0-321">A keyword from  `Keywords_hungary_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="d4ee0-322">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="d4ee0-322">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d4ee0-323">La función `Func_hungary_eu_ssn_or_equivalent` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="d4ee0-323">The function  `Func_hungary_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="d4ee0-324">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="d4ee0-324">Keywords</span></span>

#### <a name="keywordshungaryeussnorequivalent"></a><span data-ttu-id="d4ee0-325">Keywords_hungary_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="d4ee0-325">Keywords_hungary_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="d4ee0-326">número de la seguridad social húngara</span><span class="sxs-lookup"><span data-stu-id="d4ee0-326">hungarian social security number</span></span>
  
<span data-ttu-id="d4ee0-327">social security number</span><span class="sxs-lookup"><span data-stu-id="d4ee0-327">social security number</span></span>
  
<span data-ttu-id="d4ee0-328">NúmeroSeguridadSocial</span><span class="sxs-lookup"><span data-stu-id="d4ee0-328">socialsecuritynumber#</span></span>
  
<span data-ttu-id="d4ee0-329">hssn #</span><span class="sxs-lookup"><span data-stu-id="d4ee0-329">hssn#</span></span>
  
<span data-ttu-id="d4ee0-330">socialsecuritynno</span><span class="sxs-lookup"><span data-stu-id="d4ee0-330">socialsecuritynno</span></span>
  
<span data-ttu-id="d4ee0-331">hssn</span><span class="sxs-lookup"><span data-stu-id="d4ee0-331">hssn</span></span>
  
<span data-ttu-id="d4ee0-332">Taj</span><span class="sxs-lookup"><span data-stu-id="d4ee0-332">taj</span></span>
  
<span data-ttu-id="d4ee0-333">Taj #</span><span class="sxs-lookup"><span data-stu-id="d4ee0-333">taj#</span></span>
  
<span data-ttu-id="d4ee0-334">SSN</span><span class="sxs-lookup"><span data-stu-id="d4ee0-334">ssn</span></span>
  
<span data-ttu-id="d4ee0-335">SSN</span><span class="sxs-lookup"><span data-stu-id="d4ee0-335">ssn#</span></span>
  
<span data-ttu-id="d4ee0-336">n.º de seguridad social</span><span class="sxs-lookup"><span data-stu-id="d4ee0-336">social security no</span></span>
  
<span data-ttu-id="d4ee0-337">áfa</span><span class="sxs-lookup"><span data-stu-id="d4ee0-337">áfa</span></span>
  
<span data-ttu-id="d4ee0-338">közösségi adószám</span><span class="sxs-lookup"><span data-stu-id="d4ee0-338">közösségi adószám</span></span>
  
<span data-ttu-id="d4ee0-339">Általános forgalmi adó szám</span><span class="sxs-lookup"><span data-stu-id="d4ee0-339">általános forgalmi adó szám</span></span>
  
<span data-ttu-id="d4ee0-340">hozzáadottérték adó</span><span class="sxs-lookup"><span data-stu-id="d4ee0-340">hozzáadottérték adó</span></span>
  
<span data-ttu-id="d4ee0-341">áfa szám</span><span class="sxs-lookup"><span data-stu-id="d4ee0-341">áfa szám</span></span>
  
<span data-ttu-id="d4ee0-342">Magyar áfa szám</span><span class="sxs-lookup"><span data-stu-id="d4ee0-342">magyar áfa szám</span></span>
  
## <a name="portugal"></a><span data-ttu-id="d4ee0-343">Portugal</span><span class="sxs-lookup"><span data-stu-id="d4ee0-343">Portugal</span></span>

<span data-ttu-id="d4ee0-344">Para obtener más información, consulte la sección "número de tarjeta de ciudadano de Portugal" en [Qué buscan los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="d4ee0-344">For details, see the section "Portugal Citizen Card Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="spain"></a><span data-ttu-id="d4ee0-345">España</span><span class="sxs-lookup"><span data-stu-id="d4ee0-345">Spain</span></span>

<span data-ttu-id="d4ee0-346">Para obtener más información, consulte la sección "número de la seguridad social de España (SSN)" en [Qué buscan los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="d4ee0-346">For details, see the section "Spain Social Security Number (SSN)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="sweden"></a><span data-ttu-id="d4ee0-347">Suecia</span><span class="sxs-lookup"><span data-stu-id="d4ee0-347">Sweden</span></span>

### <a name="format"></a><span data-ttu-id="d4ee0-348">Formato</span><span class="sxs-lookup"><span data-stu-id="d4ee0-348">Format</span></span>

<span data-ttu-id="d4ee0-349">12 dígitos sin espacios y delimitadores</span><span class="sxs-lookup"><span data-stu-id="d4ee0-349">12 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="d4ee0-350">Patrón</span><span class="sxs-lookup"><span data-stu-id="d4ee0-350">Pattern</span></span>

<span data-ttu-id="d4ee0-351">12 dígitos:</span><span class="sxs-lookup"><span data-stu-id="d4ee0-351">12 digits:</span></span>
  
-  <span data-ttu-id="d4ee0-352">Ocho dígitos que corresponden a la fecha de nacimiento (AAAAMMDD)</span><span class="sxs-lookup"><span data-stu-id="d4ee0-352">Eight digits that correspond to the birth date (YYYYMMDD)</span></span> 
    
- <span data-ttu-id="d4ee0-353">Tres dígitos que corresponden a un número de serie en el que:</span><span class="sxs-lookup"><span data-stu-id="d4ee0-353">Three digits that correspond to a serial number where:</span></span> 
    
  - <span data-ttu-id="d4ee0-354">El último dígito del número de serie indica el sexo por la asignación de un número impar para macho y un número par para hembras</span><span class="sxs-lookup"><span data-stu-id="d4ee0-354">The last digit in the serial number indicates gender by the assignment of an odd number for male and an even number for female</span></span>
    
  - <span data-ttu-id="d4ee0-355">Hasta 1990, la asignación de número de serie que se corresponde con el condado en el que nació el portador del número o (si nació antes de 1947) donde estuvo viviendo, de acuerdo con los registros fiscales, el 1 de enero de 1947, con un código especial (por lo general, 9 como el séptimo dígito) para Immigrants</span><span class="sxs-lookup"><span data-stu-id="d4ee0-355">Up to 1990, the assignment of serial number corresponded to the county where the bearer of the number was born or (if born before 1947) where he/she had been living, according to tax records, on January 1, 1947, with a special code (usually 9 as the 7th digit) for immigrants</span></span> 
    
- <span data-ttu-id="d4ee0-356">Un dígito de control</span><span class="sxs-lookup"><span data-stu-id="d4ee0-356">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="d4ee0-357">Suma de comprobación</span><span class="sxs-lookup"><span data-stu-id="d4ee0-357">Checksum</span></span>

<span data-ttu-id="d4ee0-358">Sí</span><span class="sxs-lookup"><span data-stu-id="d4ee0-358">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="d4ee0-359">Definición</span><span class="sxs-lookup"><span data-stu-id="d4ee0-359">Definition</span></span>

<span data-ttu-id="d4ee0-360">Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="d4ee0-360">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d4ee0-361">La función `Func_sweden_eu_ssn_or_equivalent` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="d4ee0-361">The function  `Func_sweden_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="d4ee0-362">Se encuentra una `Keywords_sweden_eu_ssn_or_equivalent` palabra clave de.</span><span class="sxs-lookup"><span data-stu-id="d4ee0-362">A keyword from  `Keywords_sweden_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="d4ee0-363">Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="d4ee0-363">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d4ee0-364">La función `Func_sweden_eu_ssn_or_equivalent` busca contenido que coincide con el patrón.</span><span class="sxs-lookup"><span data-stu-id="d4ee0-364">The function  `Func_sweden_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="d4ee0-365">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="d4ee0-365">Keywords</span></span>

#### <a name="keywordsswedeneussnorequivalent"></a><span data-ttu-id="d4ee0-366">Keywords_sweden_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="d4ee0-366">Keywords_sweden_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="d4ee0-367">número de identificación personal</span><span class="sxs-lookup"><span data-stu-id="d4ee0-367">personal id number</span></span>
  
<span data-ttu-id="d4ee0-368">identification number</span><span class="sxs-lookup"><span data-stu-id="d4ee0-368">identification number</span></span>
  
<span data-ttu-id="d4ee0-369">número de identificación personal</span><span class="sxs-lookup"><span data-stu-id="d4ee0-369">personal id no</span></span>
  
<span data-ttu-id="d4ee0-370">n.º de identidad</span><span class="sxs-lookup"><span data-stu-id="d4ee0-370">identity no</span></span>
  
<span data-ttu-id="d4ee0-371">n.º de identificación</span><span class="sxs-lookup"><span data-stu-id="d4ee0-371">identification no</span></span>
  
<span data-ttu-id="d4ee0-372">n.º de identificación personal</span><span class="sxs-lookup"><span data-stu-id="d4ee0-372">personal identification no</span></span>
  
<span data-ttu-id="d4ee0-373">identificador personnummer</span><span class="sxs-lookup"><span data-stu-id="d4ee0-373">personnummer id</span></span>
  
<span data-ttu-id="d4ee0-374">personligt ID-Nummer</span><span class="sxs-lookup"><span data-stu-id="d4ee0-374">personligt id-nummer</span></span>
  
<span data-ttu-id="d4ee0-375">unikt ID-Nummer</span><span class="sxs-lookup"><span data-stu-id="d4ee0-375">unikt id-nummer</span></span>
  
<span data-ttu-id="d4ee0-376">personnummer</span><span class="sxs-lookup"><span data-stu-id="d4ee0-376">personnummer</span></span>
  
<span data-ttu-id="d4ee0-377">identifikationsnumret</span><span class="sxs-lookup"><span data-stu-id="d4ee0-377">identifikationsnumret</span></span>
  
<span data-ttu-id="d4ee0-378">personnummer #</span><span class="sxs-lookup"><span data-stu-id="d4ee0-378">personnummer#</span></span>
  
<span data-ttu-id="d4ee0-379">identifikationsnumret #</span><span class="sxs-lookup"><span data-stu-id="d4ee0-379">identifikationsnumret#</span></span>
  
## <a name="see-also"></a><span data-ttu-id="d4ee0-380">Vea también</span><span class="sxs-lookup"><span data-stu-id="d4ee0-380">See also</span></span>

[<span data-ttu-id="d4ee0-381">Qué buscan los tipos de información confidencial</span><span class="sxs-lookup"><span data-stu-id="d4ee0-381">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

