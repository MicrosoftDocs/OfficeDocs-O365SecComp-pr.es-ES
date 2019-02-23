---
title: Qué buscan las funciones de DLP
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 6/18/2016
ms.audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 94349ed4-5351-4ee2-bbda-70813c9ed693
description: Los tipos de información confidencial buscan un patrón específico y corroborarlo asegurándose de que el formato es correcto, aplicando sumas de comprobación y buscando palabras clave relevantes u otra información. Parte de esta funcionalidad se realiza mediante funciones internas. En este tema se explica qué buscan estas funciones para ayudarle a comprender cómo funcionan los tipos de información confidencial predefinidos.
ms.openlocfilehash: 55c740e892e92902b368b2dcf7b0999cbc60f3ed
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/23/2019
ms.locfileid: "30219360"
---
# <a name="what-the-dlp-functions-look-for"></a><span data-ttu-id="c6ca0-105">Qué buscan las funciones de DLP</span><span class="sxs-lookup"><span data-stu-id="c6ca0-105">What the DLP functions look for</span></span>

<span data-ttu-id="c6ca0-p102">La Prevención de pérdida de datos (DLP) incluye tipos de información confidencial, como el número de tarjeta de crédito y el número de tarjeta de débito de la UE, que están listos para su uso en las directivas de DLP. Estos tipos de información confidencial buscan un patrón específico y lo comprueban asegurándose de que el formato es el adecuado, forzando las sumas de comprobación y buscando palabras clave pertinentes u otra información. Parte de esta funcionalidad la realizan funciones internas. Por ejemplo, el tipo de información confidencial de la tarjeta de crédito usa una función para buscar fechas con formato como la fecha de vencimiento, que ayuda a comprobar que un número es un número de tarjeta de crédito.</span><span class="sxs-lookup"><span data-stu-id="c6ca0-p102">Data loss prevention (DLP) includes sensitive information types, such as Credit Card Number and EU Debit Card Number, which are ready for you to use in your DLP policies. These sensitive information types look for a specific pattern and corroborate it by ensuring proper formatting, enforcing checksums, and looking for relevant keywords or other information. Some of this functionality is performed by internal functions. For example, the Credit Card Number sensitive information type uses a function to look for dates formatted like an expiration date, to help corroborate that a number is a credit card number.</span></span>
  
<span data-ttu-id="c6ca0-p103">En este tema se explica lo que estas funciones buscan, para que comprenda mejor cómo funcionan los tipos de información confidencial predefinidos. Para más información, consulte [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="c6ca0-p103">This topic explains what these functions look for, to help you understand how the predefined sensitive information types work. For more information, see [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="funcusdate"></a><span data-ttu-id="c6ca0-112">Func_us_date</span><span class="sxs-lookup"><span data-stu-id="c6ca0-112">Func_us_date</span></span>

<span data-ttu-id="c6ca0-p104">Esta función busca una fecha con el formato que se usa habitualmente en Estados Unidos. Esto incluye los formatos "month/Day/Year", "month-Day-Year" y "month Day Year". Los nombres o abreviaturas de meses no distinguen mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="c6ca0-p104">This function looks for a date in the format commonly used in the U.S. This includes the formats "month/day/year", "month-day-year", and "month day year ". The names or abbreviations of months are not case sensitive.</span></span> 
  
<span data-ttu-id="c6ca0-115">Ejemplos:</span><span class="sxs-lookup"><span data-stu-id="c6ca0-115">Examples:</span></span>
  
- <span data-ttu-id="c6ca0-116">2 de diciembre de 2016</span><span class="sxs-lookup"><span data-stu-id="c6ca0-116">December 2, 2016</span></span>
    
- <span data-ttu-id="c6ca0-117">2 de diciembre de 2016</span><span class="sxs-lookup"><span data-stu-id="c6ca0-117">Dec 2, 2016</span></span>
    
- <span data-ttu-id="c6ca0-118">Dec 02 2016</span><span class="sxs-lookup"><span data-stu-id="c6ca0-118">dec 02 2016</span></span>
    
- <span data-ttu-id="c6ca0-119">12/2/2016</span><span class="sxs-lookup"><span data-stu-id="c6ca0-119">12/2/2016</span></span>
    
- <span data-ttu-id="c6ca0-120">12/02/16</span><span class="sxs-lookup"><span data-stu-id="c6ca0-120">12/02/16</span></span>
    
- <span data-ttu-id="c6ca0-121">Dec-2-2016</span><span class="sxs-lookup"><span data-stu-id="c6ca0-121">Dec-2-2016</span></span>
    
- <span data-ttu-id="c6ca0-122">12-2-16</span><span class="sxs-lookup"><span data-stu-id="c6ca0-122">12-2-16</span></span>
    
<span data-ttu-id="c6ca0-123">Nombres de mes aceptados:</span><span class="sxs-lookup"><span data-stu-id="c6ca0-123">Accepted month names:</span></span>
  
- <span data-ttu-id="c6ca0-124">Inglés</span><span class="sxs-lookup"><span data-stu-id="c6ca0-124">English</span></span>
    
  - <span data-ttu-id="c6ca0-125">Enero, febrero, marzo, abril, mayo, junio, julio, agosto, septiembre, octubre, noviembre, diciembre</span><span class="sxs-lookup"><span data-stu-id="c6ca0-125">January, February, march, April, may, June, July, August, September, October, November, December</span></span>
    
  - <span data-ttu-id="c6ca0-126">Ene. Feb., abril. Mayo, junio julio agosto. Sept. Oct.-Nov.</span><span class="sxs-lookup"><span data-stu-id="c6ca0-126">Jan. Feb. Mar. Apr. May June July Aug. Sept. Oct. Nov. Dec.</span></span>
    
## <a name="funceudate"></a><span data-ttu-id="c6ca0-127">Func_eu_date</span><span class="sxs-lookup"><span data-stu-id="c6ca0-127">Func_eu_date</span></span>

<span data-ttu-id="c6ca0-p105">Esta función busca una fecha en el formato que suele usarse en la UE (y en la mayoría de lugares fuera de los Estados Unidos). Esto incluye los formatos de "día/mes/año", "día-mes-año" y "día mes año". Los nombres o las abreviaturas de los meses no distinguen mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="c6ca0-p105">This function looks for a date in the format commonly used in the E.U. (and most places outside the U.S.). This includes the formats "day/month/year", "day-month-year", and "day month year". The names or abbreviations of months are not case sensitive.</span></span>
  
<span data-ttu-id="c6ca0-132">Ejemplos:</span><span class="sxs-lookup"><span data-stu-id="c6ca0-132">Examples:</span></span>
  
- <span data-ttu-id="c6ca0-133">2 Dec 2016</span><span class="sxs-lookup"><span data-stu-id="c6ca0-133">2 Dec 2016</span></span>
    
- <span data-ttu-id="c6ca0-134">02 Dec 2016</span><span class="sxs-lookup"><span data-stu-id="c6ca0-134">02 dec 2016</span></span>
    
- <span data-ttu-id="c6ca0-135">2 16 de diciembre</span><span class="sxs-lookup"><span data-stu-id="c6ca0-135">2 Dec 16</span></span>
    
- <span data-ttu-id="c6ca0-136">2/12/2016</span><span class="sxs-lookup"><span data-stu-id="c6ca0-136">2/12/2016</span></span>
    
- <span data-ttu-id="c6ca0-137">02/12/16</span><span class="sxs-lookup"><span data-stu-id="c6ca0-137">02/12/16</span></span>
    
- <span data-ttu-id="c6ca0-138">2-Dic-2016</span><span class="sxs-lookup"><span data-stu-id="c6ca0-138">2-Dec-2016</span></span>
    
- <span data-ttu-id="c6ca0-139">2-12-16</span><span class="sxs-lookup"><span data-stu-id="c6ca0-139">2-12-16</span></span>
    
<span data-ttu-id="c6ca0-140">Nombres de mes aceptados:</span><span class="sxs-lookup"><span data-stu-id="c6ca0-140">Accepted month names:</span></span>
  
- <span data-ttu-id="c6ca0-141">Inglés</span><span class="sxs-lookup"><span data-stu-id="c6ca0-141">English</span></span>
    
  - <span data-ttu-id="c6ca0-142">Enero, febrero, marzo, abril, mayo, junio, julio, agosto, septiembre, octubre, noviembre, diciembre</span><span class="sxs-lookup"><span data-stu-id="c6ca0-142">January, February, march, April, may, June, July, August, September, October, November, December</span></span>
    
  - <span data-ttu-id="c6ca0-143">Ene. Feb., abril. Mayo, junio julio agosto. Sept. Oct.-Nov.</span><span class="sxs-lookup"><span data-stu-id="c6ca0-143">Jan. Feb. Mar. Apr. May June July Aug. Sept. Oct. Nov. Dec.</span></span>
    
- <span data-ttu-id="c6ca0-144">Neerlandés</span><span class="sxs-lookup"><span data-stu-id="c6ca0-144">Dutch</span></span>
    
  - <span data-ttu-id="c6ca0-145">januari, februari, maart, April, mei, juni, juli, augustus, September, ocktober, October, November, December</span><span class="sxs-lookup"><span data-stu-id="c6ca0-145">januari, februari, maart, April, mei, juni, juli, augustus, September, ocktober, October, November, December</span></span>
    
  - <span data-ttu-id="c6ca0-146">Jan Feb maart Apr Mei Jun-Jul-Sep-Sept Oct OKT Nov Dec</span><span class="sxs-lookup"><span data-stu-id="c6ca0-146">jan feb maart apr mei jun jul aug sep sept oct okt nov dec</span></span>
    
- <span data-ttu-id="c6ca0-147">Francés</span><span class="sxs-lookup"><span data-stu-id="c6ca0-147">French</span></span>
    
  - <span data-ttu-id="c6ca0-148">Janvier, février, Mars, Avril, Mai, juin Juillet, Août, Septembre, octobre, Novembre, décembre</span><span class="sxs-lookup"><span data-stu-id="c6ca0-148">janvier, février, mars, avril, mai, juin juillet, août, septembre, octobre, novembre, décembre</span></span>
    
  - <span data-ttu-id="c6ca0-p106">janv. févr. Mars Avril Mai juin juil. Août Sept. Oct. Nov. déc.</span><span class="sxs-lookup"><span data-stu-id="c6ca0-p106">janv. févr. mars avril mai juin juil. août sept. oct. nov. déc.</span></span>
    
- <span data-ttu-id="c6ca0-156">Alemán</span><span class="sxs-lookup"><span data-stu-id="c6ca0-156">German</span></span>
    
  - <span data-ttu-id="c6ca0-157">Januar, Februar, März, April, Mai, Juni Juli, agosto, septiembre, Oktober, noviembre, Dezember</span><span class="sxs-lookup"><span data-stu-id="c6ca0-157">jänuar, februar, märz, April, mai, juni juli, August, September, oktober, November, dezember</span></span>
    
  - <span data-ttu-id="c6ca0-p107">Ene./Jän. Feb. März Apr. Mai Juni Juli agosto de la OKT. Nov dez.</span><span class="sxs-lookup"><span data-stu-id="c6ca0-p107">Jan./Jän. Feb. März Apr. Mai Juni Juli Aug. Sept. Okt. Nov. Dez.</span></span>
    
- <span data-ttu-id="c6ca0-161">Italiano</span><span class="sxs-lookup"><span data-stu-id="c6ca0-161">Italian</span></span>
    
  - <span data-ttu-id="c6ca0-162">Gennaio, Febbraio, marzo, Aprile, Maggio, Giugno, Luglio, agosto, Settembre, Ottobre, Novembre, dicembre</span><span class="sxs-lookup"><span data-stu-id="c6ca0-162">gennaio, febbraio, marzo, aprile, maggio, giugno, luglio, agosto, settembre, ottobre, novembre, dicembre</span></span>
    
  - <span data-ttu-id="c6ca0-p108">Genn. febbr. graduación. TA. Magg. Giugno Luglio AG. SETT. Ott. noviembre. Dic.</span><span class="sxs-lookup"><span data-stu-id="c6ca0-p108">genn. febbr. mar. apr. magg. giugno luglio ag. sett. ott. nov. dic.</span></span>
    
- <span data-ttu-id="c6ca0-173">Portugués</span><span class="sxs-lookup"><span data-stu-id="c6ca0-173">Portuguese</span></span>
    
  - <span data-ttu-id="c6ca0-174">janeiro, fevereiro, março, marco, abril, maio, junho, julho, agosto, setembro, outubro, novembro, dezembro</span><span class="sxs-lookup"><span data-stu-id="c6ca0-174">janeiro, fevereiro, março, marco, abril, maio, junho, julho, agosto, setembro, outubro, novembro, dezembro</span></span>
    
  - <span data-ttu-id="c6ca0-175">Jan FEV mar abr Mai Jun-Nov hace dez</span><span class="sxs-lookup"><span data-stu-id="c6ca0-175">jan fev mar abr mai jun jul ago set out nov dez</span></span>
    
- <span data-ttu-id="c6ca0-176">Español</span><span class="sxs-lookup"><span data-stu-id="c6ca0-176">Spanish</span></span>
    
  - <span data-ttu-id="c6ca0-177">enero, febrero, marzo, abril, mayo, junio, julio, agosto, septiembre, octubre, noviembre, diciembre</span><span class="sxs-lookup"><span data-stu-id="c6ca0-177">enero, febrero, marzo, abril, mayo, junio, julio, agosto, septiembre, octubre, noviembre, diciembre</span></span>
    
  - <span data-ttu-id="c6ca0-p109">Enero Feb. marzo Abr. Mayo Jun. Jul. Agosto Sept./set. Oct. Nov. Dic.</span><span class="sxs-lookup"><span data-stu-id="c6ca0-p109">enero feb. marzo abr. mayo jun. jul. agosto sept./set. oct. nov. dic.</span></span>
    
## <a name="funceudate1-deprecated"></a><span data-ttu-id="c6ca0-186">Func_eu_date1 (en desuso)</span><span class="sxs-lookup"><span data-stu-id="c6ca0-186">Func_eu_date1 (deprecated)</span></span>

> [!NOTE]
> <span data-ttu-id="c6ca0-187">Esta función está en desuso porque solo admite nombres de mes en Portugués, que ahora están incluidos en `Func_eu_date` la función anterior.</span><span class="sxs-lookup"><span data-stu-id="c6ca0-187">This function is deprecated because it supports only Portuguese month names, which are now included in the  `Func_eu_date` function above.</span></span> 
  
<span data-ttu-id="c6ca0-p110">Esta función busca una fecha con el formato que se usa habitualmente en Portugués. El formato de esta función es el mismo que `Func_eu_date`en el idioma usado.</span><span class="sxs-lookup"><span data-stu-id="c6ca0-p110">This function looks for a date in the format commonly used in Portuguese. The format for this function is the same as  `Func_eu_date`, differing only in the language used.</span></span>
  
<span data-ttu-id="c6ca0-190">Ejemplos:</span><span class="sxs-lookup"><span data-stu-id="c6ca0-190">Examples:</span></span>
  
- <span data-ttu-id="c6ca0-191">2 dez 2016</span><span class="sxs-lookup"><span data-stu-id="c6ca0-191">2 Dez 2016</span></span>
    
- <span data-ttu-id="c6ca0-192">02 dez 2016</span><span class="sxs-lookup"><span data-stu-id="c6ca0-192">02 dez 2016</span></span>
    
- <span data-ttu-id="c6ca0-193">2 dez 16</span><span class="sxs-lookup"><span data-stu-id="c6ca0-193">2 Dez 16</span></span>
    
- <span data-ttu-id="c6ca0-194">2/12/2016</span><span class="sxs-lookup"><span data-stu-id="c6ca0-194">2/12/2016</span></span>
    
- <span data-ttu-id="c6ca0-195">02/12/16</span><span class="sxs-lookup"><span data-stu-id="c6ca0-195">02/12/16</span></span>
    
- <span data-ttu-id="c6ca0-196">2-dez-2016</span><span class="sxs-lookup"><span data-stu-id="c6ca0-196">2-Dez-2016</span></span>
    
- <span data-ttu-id="c6ca0-197">2-12-16</span><span class="sxs-lookup"><span data-stu-id="c6ca0-197">2-12-16</span></span>
    
<span data-ttu-id="c6ca0-198">Nombres de mes aceptados:</span><span class="sxs-lookup"><span data-stu-id="c6ca0-198">Accepted month names:</span></span>
  
- <span data-ttu-id="c6ca0-199">Portugués</span><span class="sxs-lookup"><span data-stu-id="c6ca0-199">Portuguese</span></span>
    
  - <span data-ttu-id="c6ca0-200">janeiro, fevereiro, março, marco, abril, maio, junho, julho, agosto, setembro, outubro, novembro, dezembro</span><span class="sxs-lookup"><span data-stu-id="c6ca0-200">janeiro, fevereiro, março, marco, abril, maio, junho, julho, agosto, setembro, outubro, novembro, dezembro</span></span>
    
  - <span data-ttu-id="c6ca0-201">Jan FEV mar abr Mai Jun-Nov hace dez</span><span class="sxs-lookup"><span data-stu-id="c6ca0-201">jan fev mar abr mai jun jul ago set out nov dez</span></span>
    
## <a name="funceudate2-deprecated"></a><span data-ttu-id="c6ca0-202">Func_eu_date2 (en desuso)</span><span class="sxs-lookup"><span data-stu-id="c6ca0-202">Func_eu_date2 (deprecated)</span></span>

> [!NOTE]
> <span data-ttu-id="c6ca0-203">Esta función está en desuso porque solo admite nombres de mes en holandés, que ahora están incluidos en `Func_eu_date` la función anterior.</span><span class="sxs-lookup"><span data-stu-id="c6ca0-203">This function is deprecated because it supports only Dutch month names, which are now included in the  `Func_eu_date` function above.</span></span> 
  
<span data-ttu-id="c6ca0-p111">Esta función busca una fecha con el formato que se usa normalmente en holandés. El formato de esta función es el mismo que `Func_eu_date`en el idioma usado.</span><span class="sxs-lookup"><span data-stu-id="c6ca0-p111">This function looks for a date in the format commonly used in Dutch. The format for this function is the same as  `Func_eu_date`, differing only in the language used.</span></span>
  
<span data-ttu-id="c6ca0-206">Ejemplos:</span><span class="sxs-lookup"><span data-stu-id="c6ca0-206">Examples:</span></span>
  
- <span data-ttu-id="c6ca0-207">2 Mei 2016</span><span class="sxs-lookup"><span data-stu-id="c6ca0-207">2 Mei 2016</span></span>
    
- <span data-ttu-id="c6ca0-208">02 Mei 2016</span><span class="sxs-lookup"><span data-stu-id="c6ca0-208">02 mei 2016</span></span>
    
- <span data-ttu-id="c6ca0-209">2 Mei 16</span><span class="sxs-lookup"><span data-stu-id="c6ca0-209">2 Mei 16</span></span>
    
- <span data-ttu-id="c6ca0-210">2/12/2016</span><span class="sxs-lookup"><span data-stu-id="c6ca0-210">2/12/2016</span></span>
    
- <span data-ttu-id="c6ca0-211">02/12/16</span><span class="sxs-lookup"><span data-stu-id="c6ca0-211">02/12/16</span></span>
    
- <span data-ttu-id="c6ca0-212">2-Mei-2016</span><span class="sxs-lookup"><span data-stu-id="c6ca0-212">2-Mei-2016</span></span>
    
- <span data-ttu-id="c6ca0-213">2-12-16</span><span class="sxs-lookup"><span data-stu-id="c6ca0-213">2-12-16</span></span>
    
<span data-ttu-id="c6ca0-214">Nombres de mes aceptados:</span><span class="sxs-lookup"><span data-stu-id="c6ca0-214">Accepted month names:</span></span>
  
- <span data-ttu-id="c6ca0-215">Holandés</span><span class="sxs-lookup"><span data-stu-id="c6ca0-215">Dutch</span></span>
    
  - <span data-ttu-id="c6ca0-216">januari, februari, maart, April, mei, juni, juli, augustus, September, ocktober, October, November, December</span><span class="sxs-lookup"><span data-stu-id="c6ca0-216">januari, februari, maart, April, mei, juni, juli, augustus, September, ocktober, October, November, December</span></span>
    
  - <span data-ttu-id="c6ca0-217">Jan Feb maart Apr Mei Jun-Jul-Sep-Sept Oct OKT Nov Dec</span><span class="sxs-lookup"><span data-stu-id="c6ca0-217">jan feb maart apr mei jun jul aug sep sept oct okt nov dec</span></span>
    
## <a name="funcexpirationdate"></a><span data-ttu-id="c6ca0-218">Func_expiration_date</span><span class="sxs-lookup"><span data-stu-id="c6ca0-218">Func_expiration_date</span></span>

<span data-ttu-id="c6ca0-p112">Esta función busca una fecha en los formatos usados normalmente por tarjetas de crédito y débito, que excluyen los días en favor de los meses. Esta función coincidirá con las fechas en el formato "mes/año", "mes-año", "[nombre del mes]" y "[abreviatura del mes] año". Los nombres o abreviaturas de meses no distinguen mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="c6ca0-p112">This function looks for a date in the formats commonly used by credit and debit cards, which exclude days in favor of months. This function will match dates in format of "month/year", "month-year", "[month name] year", and "[month abbreviation] year". The names or abbreviations of months are not case sensitive.</span></span>
  
<span data-ttu-id="c6ca0-222">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="c6ca0-222">Examples:</span></span>
  
- <span data-ttu-id="c6ca0-223">MM/AA: por ejemplo, 01/11 o 1/11</span><span class="sxs-lookup"><span data-stu-id="c6ca0-223">MM/YY -- for example, 01/11 or 1/11</span></span>
    
- <span data-ttu-id="c6ca0-224">MM/AAAA: por ejemplo, 01/2011 o 1/2011</span><span class="sxs-lookup"><span data-stu-id="c6ca0-224">MM/YYYY -- for example, 01/2011 or 1/2011</span></span>
    
- <span data-ttu-id="c6ca0-225">MM-AA: por ejemplo 01-11 o 1-11</span><span class="sxs-lookup"><span data-stu-id="c6ca0-225">MM-YY -- for example, 01-22 or 1-11</span></span>
    
- <span data-ttu-id="c6ca0-226">MM-AAAA: por ejemplo 01-2000 o 1-2000</span><span class="sxs-lookup"><span data-stu-id="c6ca0-226">MM-YYYY -- for example, 01-2000 or 1-2000</span></span>
    
<span data-ttu-id="c6ca0-227">Los formatos siguientes admiten AA o AAAA:</span><span class="sxs-lookup"><span data-stu-id="c6ca0-227">The following formats support YY or YYYY:</span></span>
  
- <span data-ttu-id="c6ca0-228">Mes-AAAA: por ejemplo, ene-2010, enero-2010, ene-10 o enero-10</span><span class="sxs-lookup"><span data-stu-id="c6ca0-228">Month-YYYY -- for example, .Jan-2010 or january-2010 or Jan-10 or january-10</span></span>
    
- <span data-ttu-id="c6ca0-229">Mes AAAA: por ejemplo, "enero 2010", "ene. 2010", "enero 10" o "ene. 10"</span><span class="sxs-lookup"><span data-stu-id="c6ca0-229">Month YYYY -- for example, 'january 2010' or 'Jan 2010' or 'january 10' or 'Jan 10'</span></span>
    
- <span data-ttu-id="c6ca0-230">MesAAAA: por ejemplo, "enero2010", "ene2010", "enero10" o "ene10"</span><span class="sxs-lookup"><span data-stu-id="c6ca0-230">MonthYYYY -- for example, 'january2010' or 'Jan2010' or 'january10' or 'Jan10'</span></span>
    
- <span data-ttu-id="c6ca0-231">Mes/AAAA: por ejemplo, "enero/2010" o "ene/2010" o "enero/10" o "ene/10"</span><span class="sxs-lookup"><span data-stu-id="c6ca0-231">Month/YYYY -- for example, 'january/2010' or 'Jan/2010' or 'january/10' or 'Jan/10'</span></span>
    
<span data-ttu-id="c6ca0-232">Nombres de mes aceptados:</span><span class="sxs-lookup"><span data-stu-id="c6ca0-232">Accepted month names:</span></span>
  
- <span data-ttu-id="c6ca0-233">Inglés</span><span class="sxs-lookup"><span data-stu-id="c6ca0-233">English</span></span>
    
  - <span data-ttu-id="c6ca0-234">Enero, febrero, marzo, abril, mayo, junio, julio, agosto, septiembre, octubre, noviembre, diciembre</span><span class="sxs-lookup"><span data-stu-id="c6ca0-234">January, February, march, April, may, June, July, August, September, October, November, December</span></span>
    
  - <span data-ttu-id="c6ca0-235">Jan Feb Marzo Apr mayo junio julio agosto Sept Oct Nov Dic</span><span class="sxs-lookup"><span data-stu-id="c6ca0-235">Jan Feb Mar Apr May June July Aug Sept Oct Nov Dec</span></span>
    
## <a name="funcusaddress"></a><span data-ttu-id="c6ca0-236">Func_us_address</span><span class="sxs-lookup"><span data-stu-id="c6ca0-236">Func_us_address</span></span>

<span data-ttu-id="c6ca0-p113">Esta función busca un nombre de estado de los Estados Unidos o una abreviatura postal seguidos de un código postal válido, tal como se usan en las direcciones postales. El código postal debe ser uno de los códigos postales correctos asociados al nombre del estado de los Estados Unidos o su abreviatura. El nombre de estado de los Estados Unidos y el código postal no pueden estar separados por signos de puntuación o letras.</span><span class="sxs-lookup"><span data-stu-id="c6ca0-p113">This function looks for a U.S. state name or postal abbreviation followed by a valid zip code, just as they are used in postal addresses. The zip code must be one of the correct zip codes associated with the U.S. state name or abbreviation. The U.S. state name and zip code cannot be separated by punctuation or letters.</span></span>
  
<span data-ttu-id="c6ca0-240">Ejemplos:</span><span class="sxs-lookup"><span data-stu-id="c6ca0-240">Examples:</span></span>
  
- <span data-ttu-id="c6ca0-241">Washington 98052</span><span class="sxs-lookup"><span data-stu-id="c6ca0-241">Washington 98052</span></span>
    
- <span data-ttu-id="c6ca0-242">Washington 98052-9998</span><span class="sxs-lookup"><span data-stu-id="c6ca0-242">Washington 98052-9998</span></span>
    
- <span data-ttu-id="c6ca0-243">WA 98052</span><span class="sxs-lookup"><span data-stu-id="c6ca0-243">WA 98052</span></span>
    
- <span data-ttu-id="c6ca0-244">WA 98052-9998</span><span class="sxs-lookup"><span data-stu-id="c6ca0-244">WA 98052-9998</span></span>
    

