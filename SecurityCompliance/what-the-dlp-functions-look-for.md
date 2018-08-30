---
title: Qué buscan las funciones de DLP
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 6/18/2016
ms.audience: Admin
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 94349ed4-5351-4ee2-bbda-70813c9ed693
description: Los tipos de información confidencial busca un patrón específico y comprobar al garantizar adecuada formato, aplicar las sumas de comprobación y busca las palabras clave relevantes u otra información. Parte de esta funcionalidad se realiza por funciones internas. En este tema se explica lo que estas funciones buscan, que le ayudarán a comprender cómo funcionan los tipos de información confidencial predefinidos.
ms.openlocfilehash: 510f98e2b4e1d2480550f11026cf445be6ffc931
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "23013764"
---
# <a name="what-the-dlp-functions-look-for"></a><span data-ttu-id="a8e31-105">Qué buscan las funciones de DLP</span><span class="sxs-lookup"><span data-stu-id="a8e31-105">What the DLP functions look for</span></span>

<span data-ttu-id="a8e31-p102">La Prevención de pérdida de datos (DLP) incluye tipos de información confidencial, como el número de tarjeta de crédito y el número de tarjeta de débito de la UE, que están listos para su uso en las directivas de DLP. Estos tipos de información confidencial buscan un patrón específico y lo comprueban asegurándose de que el formato es el adecuado, forzando las sumas de comprobación y buscando palabras clave pertinentes u otra información. Parte de esta funcionalidad la realizan funciones internas. Por ejemplo, el tipo de información confidencial de la tarjeta de crédito usa una función para buscar fechas con formato como la fecha de vencimiento, que ayuda a comprobar que un número es un número de tarjeta de crédito.</span><span class="sxs-lookup"><span data-stu-id="a8e31-p102">Data loss prevention (DLP) includes sensitive information types, such as Credit Card Number and EU Debit Card Number, which are ready for you to use in your DLP policies. These sensitive information types look for a specific pattern and corroborate it by ensuring proper formatting, enforcing checksums, and looking for relevant keywords or other information. Some of this functionality is performed by internal functions. For example, the Credit Card Number sensitive information type uses a function to look for dates formatted like an expiration date, to help corroborate that a number is a credit card number.</span></span>
  
<span data-ttu-id="a8e31-p103">En este tema se explica lo que estas funciones buscan, para que comprenda mejor cómo funcionan los tipos de información confidencial predefinidos. Para más información, consulte [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="a8e31-p103">This topic explains what these functions look for, to help you understand how the predefined sensitive information types work. For more information, see [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="funcusdate"></a><span data-ttu-id="a8e31-112">Func_us_date</span><span class="sxs-lookup"><span data-stu-id="a8e31-112">Func_us_date</span></span>

<span data-ttu-id="a8e31-p104">Esta función busca una fecha en el formato utilizado con frecuencia en los Estados Unidos Esto incluye los formatos "día/mes/año", "día-mes-año" y "mes del año de día". Los nombres o abreviaturas de meses no distinguen mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="a8e31-p104">This function looks for a date in the format commonly used in the U.S. This includes the formats "month/day/year", "month-day-year", and "month day year ". The names or abbreviations of months are not case sensitive.</span></span> 
  
<span data-ttu-id="a8e31-115">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="a8e31-115">Examples:</span></span>
  
- <span data-ttu-id="a8e31-116">2 de diciembre de 2016</span><span class="sxs-lookup"><span data-stu-id="a8e31-116">December 2, 2016</span></span>
    
- <span data-ttu-id="a8e31-117">2 de diciembre de 2016</span><span class="sxs-lookup"><span data-stu-id="a8e31-117">Dec 2, 2016</span></span>
    
- <span data-ttu-id="a8e31-118">Dic 02 2016</span><span class="sxs-lookup"><span data-stu-id="a8e31-118">dec 02 2016</span></span>
    
- <span data-ttu-id="a8e31-119">2/12/2016</span><span class="sxs-lookup"><span data-stu-id="a8e31-119">12/2/2016</span></span>
    
- <span data-ttu-id="a8e31-120">02/12/16</span><span class="sxs-lookup"><span data-stu-id="a8e31-120">12/02/16</span></span>
    
- <span data-ttu-id="a8e31-121">Dic-2-2016</span><span class="sxs-lookup"><span data-stu-id="a8e31-121">Dec-2-2016</span></span>
    
- <span data-ttu-id="a8e31-122">12-2-16</span><span class="sxs-lookup"><span data-stu-id="a8e31-122">12-2-16</span></span>
    
<span data-ttu-id="a8e31-123">Nombres de mes aceptados:</span><span class="sxs-lookup"><span data-stu-id="a8e31-123">Accepted month names:</span></span>
  
- <span data-ttu-id="a8e31-124">Inglés</span><span class="sxs-lookup"><span data-stu-id="a8e31-124">English</span></span>
    
  - <span data-ttu-id="a8e31-125">Enero, febrero, marzo, abril, mayo, junio, julio, agosto, septiembre, octubre, noviembre, diciembre</span><span class="sxs-lookup"><span data-stu-id="a8e31-125">January, February, march, April, may, June, July, August, September, October, November, December</span></span>
    
  - <span data-ttu-id="a8e31-126">Enero febrero marzo abril mayo junio julio agosto septiembre octubre noviembre Dic.</span><span class="sxs-lookup"><span data-stu-id="a8e31-126">Jan. Feb. Mar. Apr. May June July Aug. Sept. Oct. Nov. Dec.</span></span>
    
## <a name="funceudate"></a><span data-ttu-id="a8e31-127">Func_eu_date</span><span class="sxs-lookup"><span data-stu-id="a8e31-127">Func_eu_date</span></span>

<span data-ttu-id="a8e31-p105">Esta función busca una fecha en el formato que suele usarse en la UE (y en la mayoría de lugares fuera de los Estados Unidos). Esto incluye los formatos de "día/mes/año", "día-mes-año" y "día mes año". Los nombres o las abreviaturas de los meses no distinguen mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="a8e31-p105">This function looks for a date in the format commonly used in the E.U. (and most places outside the U.S.). This includes the formats "day/month/year", "day-month-year", and "day month year". The names or abbreviations of months are not case sensitive.</span></span>
  
<span data-ttu-id="a8e31-132">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="a8e31-132">Examples:</span></span>
  
- <span data-ttu-id="a8e31-133">2 de diciembre de 2016</span><span class="sxs-lookup"><span data-stu-id="a8e31-133">2 Dec 2016</span></span>
    
- <span data-ttu-id="a8e31-134">Dic 02 2016</span><span class="sxs-lookup"><span data-stu-id="a8e31-134">02 dec 2016</span></span>
    
- <span data-ttu-id="a8e31-135">16 de diciembre de 2</span><span class="sxs-lookup"><span data-stu-id="a8e31-135">2 Dec 16</span></span>
    
- <span data-ttu-id="a8e31-136">12/2/2016</span><span class="sxs-lookup"><span data-stu-id="a8e31-136">2/12/2016</span></span>
    
- <span data-ttu-id="a8e31-137">16/12/02</span><span class="sxs-lookup"><span data-stu-id="a8e31-137">02/12/16</span></span>
    
- <span data-ttu-id="a8e31-138">2-Dic-2016</span><span class="sxs-lookup"><span data-stu-id="a8e31-138">2-Dec-2016</span></span>
    
- <span data-ttu-id="a8e31-139">2-12-16</span><span class="sxs-lookup"><span data-stu-id="a8e31-139">2-12-16</span></span>
    
<span data-ttu-id="a8e31-140">Nombres de mes aceptados:</span><span class="sxs-lookup"><span data-stu-id="a8e31-140">Accepted month names:</span></span>
  
- <span data-ttu-id="a8e31-141">Inglés</span><span class="sxs-lookup"><span data-stu-id="a8e31-141">English</span></span>
    
  - <span data-ttu-id="a8e31-142">Enero, febrero, marzo, abril, mayo, junio, julio, agosto, septiembre, octubre, noviembre, diciembre</span><span class="sxs-lookup"><span data-stu-id="a8e31-142">January, February, march, April, may, June, July, August, September, October, November, December</span></span>
    
  - <span data-ttu-id="a8e31-143">Enero febrero marzo abril mayo junio julio agosto septiembre octubre noviembre Dic.</span><span class="sxs-lookup"><span data-stu-id="a8e31-143">Jan. Feb. Mar. Apr. May June July Aug. Sept. Oct. Nov. Dec.</span></span>
    
- <span data-ttu-id="a8e31-144">Neerlandés</span><span class="sxs-lookup"><span data-stu-id="a8e31-144">Dutch</span></span>
    
  - <span data-ttu-id="a8e31-145">januari, februari, maart, April, mei, juni, juli, augustus, September, ocktober, October, November, December</span><span class="sxs-lookup"><span data-stu-id="a8e31-145">januari, februari, maart, April, mei, juni, juli, augustus, September, ocktober, October, November, December</span></span>
    
  - <span data-ttu-id="a8e31-146">Ene febrero maart Abr mei jun julio agosto sep septiembre oct okt noviembre Dic</span><span class="sxs-lookup"><span data-stu-id="a8e31-146">jan feb maart apr mei jun jul aug sep sept oct okt nov dec</span></span>
    
- <span data-ttu-id="a8e31-147">Francés</span><span class="sxs-lookup"><span data-stu-id="a8e31-147">French</span></span>
    
  - <span data-ttu-id="a8e31-148">enero, febrero, mars, avril, mayo, julio de junio, août, septiembre, octubre, noviembre, diciembre de</span><span class="sxs-lookup"><span data-stu-id="a8e31-148">janvier, février, mars, avril, mai, juin juillet, août, septembre, octobre, novembre, décembre</span></span>
    
  - <span data-ttu-id="a8e31-p106">janv. févr. mar avril mayo junio juil. septiembre août. octubre noviembre. déc.</span><span class="sxs-lookup"><span data-stu-id="a8e31-p106">janv. févr. mars avril mai juin juil. août sept. oct. nov. déc.</span></span>
    
- <span data-ttu-id="a8e31-156">Alemán</span><span class="sxs-lookup"><span data-stu-id="a8e31-156">German</span></span>
    
  - <span data-ttu-id="a8e31-157">jänuar, februar, märz, abril, mayo, juni juli, agosto, septiembre, octubre, noviembre, dezember</span><span class="sxs-lookup"><span data-stu-id="a8e31-157">jänuar, februar, märz, April, mai, juni juli, August, September, oktober, November, dezember</span></span>
    
  - <span data-ttu-id="a8e31-p107">Ene. / Jän. Febrero März abril mayo Juni Juli agosto septiembre Okt. Dez de noviembre.</span><span class="sxs-lookup"><span data-stu-id="a8e31-p107">Jan./Jän. Feb. März Apr. Mai Juni Juli Aug. Sept. Okt. Nov. Dez.</span></span>
    
- <span data-ttu-id="a8e31-161">Italiano</span><span class="sxs-lookup"><span data-stu-id="a8e31-161">Italian</span></span>
    
  - <span data-ttu-id="a8e31-162">gennaio, febbraio, marzo, aprile, maggio, giugno, luglio, agosto, settembre, ottobre, noviembre, dicembre</span><span class="sxs-lookup"><span data-stu-id="a8e31-162">gennaio, febbraio, marzo, aprile, maggio, giugno, luglio, agosto, settembre, ottobre, novembre, dicembre</span></span>
    
  - <span data-ttu-id="a8e31-p108">Genn. febbr. mar. Abr. magg. giugno luglio ag. configuración. ott. noviembre. Dic.</span><span class="sxs-lookup"><span data-stu-id="a8e31-p108">genn. febbr. mar. apr. magg. giugno luglio ag. sett. ott. nov. dic.</span></span>
    
- <span data-ttu-id="a8e31-173">Portugués</span><span class="sxs-lookup"><span data-stu-id="a8e31-173">Portuguese</span></span>
    
  - <span data-ttu-id="a8e31-174">janeiro, fevereiro, março, marco, abril, maio, junho, julho, agosto, setembro, outubro, novembro, dezembro</span><span class="sxs-lookup"><span data-stu-id="a8e31-174">janeiro, fevereiro, março, marco, abril, maio, junho, julho, agosto, setembro, outubro, novembro, dezembro</span></span>
    
  - <span data-ttu-id="a8e31-175">Jan fev mar abr mai jun julio hace establecidos dez noviembre</span><span class="sxs-lookup"><span data-stu-id="a8e31-175">jan fev mar abr mai jun jul ago set out nov dez</span></span>
    
- <span data-ttu-id="a8e31-176">Español</span><span class="sxs-lookup"><span data-stu-id="a8e31-176">Spanish</span></span>
    
  - <span data-ttu-id="a8e31-177">enero, febrero, marzo, abril, mayo, junio, julio, agosto, septiembre, octubre, noviembre, diciembre</span><span class="sxs-lookup"><span data-stu-id="a8e31-177">enero, febrero, marzo, abril, mayo, junio, julio, agosto, septiembre, octubre, noviembre, diciembre</span></span>
    
  - <span data-ttu-id="a8e31-p109">enero febrero. marzo abr. mayo Jun julio. agosto septiembre o establecer. octubre noviembre. Dic.</span><span class="sxs-lookup"><span data-stu-id="a8e31-p109">enero feb. marzo abr. mayo jun. jul. agosto sept./set. oct. nov. dic.</span></span>
    
## <a name="funceudate1-deprecated"></a><span data-ttu-id="a8e31-186">Func_eu_date1 (en desuso)</span><span class="sxs-lookup"><span data-stu-id="a8e31-186">Func_eu_date1 (deprecated)</span></span>

> [!NOTE]
> <span data-ttu-id="a8e31-187">Esta función está desusada porque admite únicamente nombres de mes portugués, que ahora se incluyen en el `Func_eu_date` función anterior.</span><span class="sxs-lookup"><span data-stu-id="a8e31-187">This function is deprecated because it supports only Portuguese month names, which are now included in the  `Func_eu_date` function above.</span></span> 
  
<span data-ttu-id="a8e31-p110">Esta función busca una fecha en el formato de uso frecuente en portugués. El formato de esta función es el mismo que `Func_eu_date`y diferentes sólo en el idioma usado.</span><span class="sxs-lookup"><span data-stu-id="a8e31-p110">This function looks for a date in the format commonly used in Portuguese. The format for this function is the same as  `Func_eu_date`, differing only in the language used.</span></span>
  
<span data-ttu-id="a8e31-190">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="a8e31-190">Examples:</span></span>
  
- <span data-ttu-id="a8e31-191">2 Dez 2016</span><span class="sxs-lookup"><span data-stu-id="a8e31-191">2 Dez 2016</span></span>
    
- <span data-ttu-id="a8e31-192">02 dez 2016</span><span class="sxs-lookup"><span data-stu-id="a8e31-192">02 dez 2016</span></span>
    
- <span data-ttu-id="a8e31-193">2 Dez 16</span><span class="sxs-lookup"><span data-stu-id="a8e31-193">2 Dez 16</span></span>
    
- <span data-ttu-id="a8e31-194">12/2/2016</span><span class="sxs-lookup"><span data-stu-id="a8e31-194">2/12/2016</span></span>
    
- <span data-ttu-id="a8e31-195">16/12/02</span><span class="sxs-lookup"><span data-stu-id="a8e31-195">02/12/16</span></span>
    
- <span data-ttu-id="a8e31-196">2-Dez-2016</span><span class="sxs-lookup"><span data-stu-id="a8e31-196">2-Dez-2016</span></span>
    
- <span data-ttu-id="a8e31-197">2-12-16</span><span class="sxs-lookup"><span data-stu-id="a8e31-197">2-12-16</span></span>
    
<span data-ttu-id="a8e31-198">Nombres de mes aceptados:</span><span class="sxs-lookup"><span data-stu-id="a8e31-198">Accepted month names:</span></span>
  
- <span data-ttu-id="a8e31-199">Portugués</span><span class="sxs-lookup"><span data-stu-id="a8e31-199">Portuguese</span></span>
    
  - <span data-ttu-id="a8e31-200">janeiro, fevereiro, março, marco, abril, maio, junho, julho, agosto, setembro, outubro, novembro, dezembro</span><span class="sxs-lookup"><span data-stu-id="a8e31-200">janeiro, fevereiro, março, marco, abril, maio, junho, julho, agosto, setembro, outubro, novembro, dezembro</span></span>
    
  - <span data-ttu-id="a8e31-201">Jan fev mar abr mai jun julio hace establecidos dez noviembre</span><span class="sxs-lookup"><span data-stu-id="a8e31-201">jan fev mar abr mai jun jul ago set out nov dez</span></span>
    
## <a name="funceudate2-deprecated"></a><span data-ttu-id="a8e31-202">Func_eu_date2 (en desuso)</span><span class="sxs-lookup"><span data-stu-id="a8e31-202">Func_eu_date2 (deprecated)</span></span>

> [!NOTE]
> <span data-ttu-id="a8e31-203">Esta función está desusada porque admite únicamente nombres de mes neerlandés, que ahora se incluyen en el `Func_eu_date` función anterior.</span><span class="sxs-lookup"><span data-stu-id="a8e31-203">This function is deprecated because it supports only Dutch month names, which are now included in the  `Func_eu_date` function above.</span></span> 
  
<span data-ttu-id="a8e31-p111">Esta función busca una fecha en el formato de uso frecuente en neerlandés. El formato de esta función es el mismo que `Func_eu_date`y diferentes sólo en el idioma usado.</span><span class="sxs-lookup"><span data-stu-id="a8e31-p111">This function looks for a date in the format commonly used in Dutch. The format for this function is the same as  `Func_eu_date`, differing only in the language used.</span></span>
  
<span data-ttu-id="a8e31-206">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="a8e31-206">Examples:</span></span>
  
- <span data-ttu-id="a8e31-207">2 Mei 2016</span><span class="sxs-lookup"><span data-stu-id="a8e31-207">2 Mei 2016</span></span>
    
- <span data-ttu-id="a8e31-208">mei 02 2016</span><span class="sxs-lookup"><span data-stu-id="a8e31-208">02 mei 2016</span></span>
    
- <span data-ttu-id="a8e31-209">Mei 2 16</span><span class="sxs-lookup"><span data-stu-id="a8e31-209">2 Mei 16</span></span>
    
- <span data-ttu-id="a8e31-210">12/2/2016</span><span class="sxs-lookup"><span data-stu-id="a8e31-210">2/12/2016</span></span>
    
- <span data-ttu-id="a8e31-211">16/12/02</span><span class="sxs-lookup"><span data-stu-id="a8e31-211">02/12/16</span></span>
    
- <span data-ttu-id="a8e31-212">2-Mei-2016</span><span class="sxs-lookup"><span data-stu-id="a8e31-212">2-Mei-2016</span></span>
    
- <span data-ttu-id="a8e31-213">2-12-16</span><span class="sxs-lookup"><span data-stu-id="a8e31-213">2-12-16</span></span>
    
<span data-ttu-id="a8e31-214">Nombres de mes aceptados:</span><span class="sxs-lookup"><span data-stu-id="a8e31-214">Accepted month names:</span></span>
  
- <span data-ttu-id="a8e31-215">Holandés</span><span class="sxs-lookup"><span data-stu-id="a8e31-215">Dutch</span></span>
    
  - <span data-ttu-id="a8e31-216">januari, februari, maart, April, mei, juni, juli, augustus, September, ocktober, October, November, December</span><span class="sxs-lookup"><span data-stu-id="a8e31-216">januari, februari, maart, April, mei, juni, juli, augustus, September, ocktober, October, November, December</span></span>
    
  - <span data-ttu-id="a8e31-217">Ene febrero maart Abr mei jun julio agosto sep septiembre oct okt noviembre Dic</span><span class="sxs-lookup"><span data-stu-id="a8e31-217">jan feb maart apr mei jun jul aug sep sept oct okt nov dec</span></span>
    
## <a name="funcexpirationdate"></a><span data-ttu-id="a8e31-218">Func_expiration_date</span><span class="sxs-lookup"><span data-stu-id="a8e31-218">Func_expiration_date</span></span>

<span data-ttu-id="a8e31-p112">Esta función busca una fecha en los formatos utilizadas frecuentemente por tarjetas de debe y haber, que excluyen días en favor de meses. Esta función coincidirá con las fechas en formato de "mes/año", "día-mes-año", "[nombre del mes] año" y "[abreviatura del mes]". Los nombres o abreviaturas de meses no distinguen mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="a8e31-p112">This function looks for a date in the formats commonly used by credit and debit cards, which exclude days in favor of months. This function will match dates in format of "month/year", "month-year", "[month name] year", and "[month abbreviation] year". The names or abbreviations of months are not case sensitive.</span></span>
  
<span data-ttu-id="a8e31-222">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="a8e31-222">Examples:</span></span>
  
- <span data-ttu-id="a8e31-223">MM/AA: por ejemplo, 01/11 o 1/11</span><span class="sxs-lookup"><span data-stu-id="a8e31-223">MM/YY -- for example, 01/11 or 1/11</span></span>
    
- <span data-ttu-id="a8e31-224">MM/AAAA: por ejemplo, 01/2011 o 1/2011</span><span class="sxs-lookup"><span data-stu-id="a8e31-224">MM/YYYY -- for example, 01/2011 or 1/2011</span></span>
    
- <span data-ttu-id="a8e31-225">MM-AA: por ejemplo 01-11 o 1-11</span><span class="sxs-lookup"><span data-stu-id="a8e31-225">MM-YY -- for example, 01-22 or 1-11</span></span>
    
- <span data-ttu-id="a8e31-226">MM-AAAA: por ejemplo 01-2000 o 1-2000</span><span class="sxs-lookup"><span data-stu-id="a8e31-226">MM-YYYY -- for example, 01-2000 or 1-2000</span></span>
    
<span data-ttu-id="a8e31-227">Los formatos siguientes admiten AA o AAAA:</span><span class="sxs-lookup"><span data-stu-id="a8e31-227">The following formats support YY or YYYY:</span></span>
  
- <span data-ttu-id="a8e31-228">Mes-AAAA: por ejemplo, ene-2010, enero-2010, ene-10 o enero-10</span><span class="sxs-lookup"><span data-stu-id="a8e31-228">Month-YYYY -- for example, .Jan-2010 or january-2010 or Jan-10 or january-10</span></span>
    
- <span data-ttu-id="a8e31-229">Mes AAAA: por ejemplo, "enero 2010", "ene. 2010", "enero 10" o "ene. 10"</span><span class="sxs-lookup"><span data-stu-id="a8e31-229">Month YYYY -- for example, 'january 2010' or 'Jan 2010' or 'january 10' or 'Jan 10'</span></span>
    
- <span data-ttu-id="a8e31-230">MesAAAA: por ejemplo, "enero2010", "ene2010", "enero10" o "ene10"</span><span class="sxs-lookup"><span data-stu-id="a8e31-230">MonthYYYY -- for example, 'january2010' or 'Jan2010' or 'january10' or 'Jan10'</span></span>
    
- <span data-ttu-id="a8e31-231">Mes/aaaa--por ejemplo, ' enero/2010' o ' Ene/2010' o ' enero/10' o ' Ene/10'</span><span class="sxs-lookup"><span data-stu-id="a8e31-231">Month/YYYY -- for example, 'january/2010' or 'Jan/2010' or 'january/10' or 'Jan/10'</span></span>
    
<span data-ttu-id="a8e31-232">Nombres de mes aceptados:</span><span class="sxs-lookup"><span data-stu-id="a8e31-232">Accepted month names:</span></span>
  
- <span data-ttu-id="a8e31-233">Inglés</span><span class="sxs-lookup"><span data-stu-id="a8e31-233">English</span></span>
    
  - <span data-ttu-id="a8e31-234">Enero, febrero, marzo, abril, mayo, junio, julio, agosto, septiembre, octubre, noviembre, diciembre</span><span class="sxs-lookup"><span data-stu-id="a8e31-234">January, February, march, April, may, June, July, August, September, October, November, December</span></span>
    
  - <span data-ttu-id="a8e31-235">Febrero de Ene Abr de Mar, es posible que junio julio agosto septiembre octubre noviembre Dic</span><span class="sxs-lookup"><span data-stu-id="a8e31-235">Jan Feb Mar Apr May June July Aug Sept Oct Nov Dec</span></span>
    
## <a name="funcusaddress"></a><span data-ttu-id="a8e31-236">Func_us_address</span><span class="sxs-lookup"><span data-stu-id="a8e31-236">Func_us_address</span></span>

<span data-ttu-id="a8e31-p113">Esta función busca un nombre de estado de los Estados Unidos o una abreviatura postal seguidos de un código postal válido, tal como se usan en las direcciones postales. El código postal debe ser uno de los códigos postales correctos asociados al nombre del estado de los Estados Unidos o su abreviatura. El nombre de estado de los Estados Unidos y el código postal no pueden estar separados por signos de puntuación o letras.</span><span class="sxs-lookup"><span data-stu-id="a8e31-p113">This function looks for a U.S. state name or postal abbreviation followed by a valid zip code, just as they are used in postal addresses. The zip code must be one of the correct zip codes associated with the U.S. state name or abbreviation. The U.S. state name and zip code cannot be separated by punctuation or letters.</span></span>
  
<span data-ttu-id="a8e31-240">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="a8e31-240">Examples:</span></span>
  
- <span data-ttu-id="a8e31-241">Washington 98052</span><span class="sxs-lookup"><span data-stu-id="a8e31-241">Washington 98052</span></span>
    
- <span data-ttu-id="a8e31-242">Washington 98052-9998</span><span class="sxs-lookup"><span data-stu-id="a8e31-242">Washington 98052-9998</span></span>
    
- <span data-ttu-id="a8e31-243">WA 98052</span><span class="sxs-lookup"><span data-stu-id="a8e31-243">WA 98052</span></span>
    
- <span data-ttu-id="a8e31-244">WA 98052-9998</span><span class="sxs-lookup"><span data-stu-id="a8e31-244">WA 98052-9998</span></span>
    

