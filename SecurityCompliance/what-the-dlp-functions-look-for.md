---
title: Qué buscan las funciones de DLP
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 6/18/2016
ms.audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Los tipos de información confidencial buscan un patrón específico y corroborarlo asegurándose de que el formato es correcto, aplicando sumas de comprobación y buscando palabras clave relevantes u otra información. Parte de esta funcionalidad la realizan funciones internas. En este tema se explica lo que estas funciones buscan, para que comprenda mejor cómo funcionan los tipos de información confidencial predefinidos.
ms.openlocfilehash: d0aeb38001f42d9db2b124466b02746ee106b078
ms.sourcegitcommit: 8657e003ab1ff49113f222d1ee8400eff174cb54
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/16/2019
ms.locfileid: "30638937"
---
# <a name="what-the-dlp-functions-look-for"></a><span data-ttu-id="9919e-105">Qué buscan las funciones de DLP</span><span class="sxs-lookup"><span data-stu-id="9919e-105">What the DLP functions look for</span></span>

<span data-ttu-id="9919e-p102">La Prevención de pérdida de datos (DLP) incluye tipos de información confidencial, como el número de tarjeta de crédito y el número de tarjeta de débito de la UE, que están listos para su uso en las directivas de DLP. Estos tipos de información confidencial buscan un patrón específico y lo comprueban asegurándose de que el formato es el adecuado, forzando las sumas de comprobación y buscando palabras clave pertinentes u otra información. Parte de esta funcionalidad la realizan funciones internas. Por ejemplo, el tipo de información confidencial de la tarjeta de crédito usa una función para buscar fechas con formato como la fecha de vencimiento, que ayuda a comprobar que un número es un número de tarjeta de crédito.</span><span class="sxs-lookup"><span data-stu-id="9919e-p102">Data loss prevention (DLP) includes sensitive information types, such as Credit Card Number and EU Debit Card Number, which are ready for you to use in your DLP policies. These sensitive information types look for a specific pattern and corroborate it by ensuring proper formatting, enforcing checksums, and looking for relevant keywords or other information. Some of this functionality is performed by internal functions. For example, the Credit Card Number sensitive information type uses a function to look for dates formatted like an expiration date, to help corroborate that a number is a credit card number.</span></span>
  
<span data-ttu-id="9919e-110">En este tema se explica lo que estas funciones buscan, para que comprenda mejor cómo funcionan los tipos de información confidencial predefinidos.</span><span class="sxs-lookup"><span data-stu-id="9919e-110">This topic explains what these functions look for, to help you understand how the predefined sensitive information types work.</span></span> <span data-ttu-id="9919e-111">Para más información, consulte [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="9919e-111">For more information, see [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="funcusdate"></a><span data-ttu-id="9919e-112">Func_us_date</span><span class="sxs-lookup"><span data-stu-id="9919e-112">Func_us_date</span></span>

<span data-ttu-id="9919e-113">Esta función busca una fecha con el formato que se usa habitualmente en Estados Unidos. Esto incluye los formatos "month/Day/Year", "month-Day-Year" y "month Day Year".</span><span class="sxs-lookup"><span data-stu-id="9919e-113">This function looks for a date in the format commonly used in the U.S. This includes the formats "month/day/year", "month-day-year", and "month day year ".</span></span> <span data-ttu-id="9919e-114">Los nombres o las abreviaturas de los meses no distinguen mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="9919e-114">The names or abbreviations of months are not case sensitive.</span></span> 
  
<span data-ttu-id="9919e-115">Ejemplos:</span><span class="sxs-lookup"><span data-stu-id="9919e-115">Examples:</span></span>
  
- <span data-ttu-id="9919e-116">2 de diciembre de 2016</span><span class="sxs-lookup"><span data-stu-id="9919e-116">December 2, 2016</span></span>
    
- <span data-ttu-id="9919e-117">2 de diciembre de 2016</span><span class="sxs-lookup"><span data-stu-id="9919e-117">Dec 2, 2016</span></span>
    
- <span data-ttu-id="9919e-118">Dec 02 2016</span><span class="sxs-lookup"><span data-stu-id="9919e-118">dec 02 2016</span></span>
    
- <span data-ttu-id="9919e-119">12/2/2016</span><span class="sxs-lookup"><span data-stu-id="9919e-119">12/2/2016</span></span>
    
- <span data-ttu-id="9919e-120">12/02/16</span><span class="sxs-lookup"><span data-stu-id="9919e-120">12/02/16</span></span>
    
- <span data-ttu-id="9919e-121">Dec-2-2016</span><span class="sxs-lookup"><span data-stu-id="9919e-121">Dec-2-2016</span></span>
    
- <span data-ttu-id="9919e-122">12-2-16</span><span class="sxs-lookup"><span data-stu-id="9919e-122">12-2-16</span></span>
    
<span data-ttu-id="9919e-123">Nombres de mes aceptados:</span><span class="sxs-lookup"><span data-stu-id="9919e-123">Accepted month names:</span></span>
  
- <span data-ttu-id="9919e-124">Inglés</span><span class="sxs-lookup"><span data-stu-id="9919e-124">English</span></span>
    
  - <span data-ttu-id="9919e-125">Enero, febrero, marzo, abril, mayo, junio, julio, agosto, septiembre, octubre, noviembre, diciembre</span><span class="sxs-lookup"><span data-stu-id="9919e-125">January, February, march, April, may, June, July, August, September, October, November, December</span></span>
    
  - <span data-ttu-id="9919e-126">Ene. Feb., abril. Mayo, junio julio agosto. Sept. Oct.-Nov.</span><span class="sxs-lookup"><span data-stu-id="9919e-126">Jan. Feb. Mar. Apr. May June July Aug. Sept. Oct. Nov. Dec.</span></span>
    
## <a name="funceudate"></a><span data-ttu-id="9919e-127">Func_eu_date</span><span class="sxs-lookup"><span data-stu-id="9919e-127">Func_eu_date</span></span>

<span data-ttu-id="9919e-p105">Esta función busca una fecha en el formato que suele usarse en la UE (y en la mayoría de lugares fuera de los Estados Unidos). Esto incluye los formatos de "día/mes/año", "día-mes-año" y "día mes año". Los nombres o las abreviaturas de los meses no distinguen mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="9919e-p105">This function looks for a date in the format commonly used in the E.U. (and most places outside the U.S.). This includes the formats "day/month/year", "day-month-year", and "day month year". The names or abbreviations of months are not case sensitive.</span></span>
  
<span data-ttu-id="9919e-132">Ejemplos:</span><span class="sxs-lookup"><span data-stu-id="9919e-132">Examples:</span></span>
  
- <span data-ttu-id="9919e-133">2 Dec 2016</span><span class="sxs-lookup"><span data-stu-id="9919e-133">2 Dec 2016</span></span>
    
- <span data-ttu-id="9919e-134">02 Dec 2016</span><span class="sxs-lookup"><span data-stu-id="9919e-134">02 dec 2016</span></span>
    
- <span data-ttu-id="9919e-135">2 16 de diciembre</span><span class="sxs-lookup"><span data-stu-id="9919e-135">2 Dec 16</span></span>
    
- <span data-ttu-id="9919e-136">2/12/2016</span><span class="sxs-lookup"><span data-stu-id="9919e-136">2/12/2016</span></span>
    
- <span data-ttu-id="9919e-137">02/12/16</span><span class="sxs-lookup"><span data-stu-id="9919e-137">02/12/16</span></span>
    
- <span data-ttu-id="9919e-138">2-Dic-2016</span><span class="sxs-lookup"><span data-stu-id="9919e-138">2-Dec-2016</span></span>
    
- <span data-ttu-id="9919e-139">2-12-16</span><span class="sxs-lookup"><span data-stu-id="9919e-139">2-12-16</span></span>
    
<span data-ttu-id="9919e-140">Nombres de mes aceptados:</span><span class="sxs-lookup"><span data-stu-id="9919e-140">Accepted month names:</span></span>
  
- <span data-ttu-id="9919e-141">Inglés</span><span class="sxs-lookup"><span data-stu-id="9919e-141">English</span></span>
    
  - <span data-ttu-id="9919e-142">Enero, febrero, marzo, abril, mayo, junio, julio, agosto, septiembre, octubre, noviembre, diciembre</span><span class="sxs-lookup"><span data-stu-id="9919e-142">January, February, march, April, may, June, July, August, September, October, November, December</span></span>
    
  - <span data-ttu-id="9919e-143">Ene. Feb., abril. Mayo, junio julio agosto. Sept. Oct.-Nov.</span><span class="sxs-lookup"><span data-stu-id="9919e-143">Jan. Feb. Mar. Apr. May June July Aug. Sept. Oct. Nov. Dec.</span></span>
    
- <span data-ttu-id="9919e-144">Neerlandés</span><span class="sxs-lookup"><span data-stu-id="9919e-144">Dutch</span></span>
    
  - <span data-ttu-id="9919e-145">januari, februari, maart, April, mei, juni, juli, augustus, September, ocktober, October, November, December</span><span class="sxs-lookup"><span data-stu-id="9919e-145">januari, februari, maart, April, mei, juni, juli, augustus, September, ocktober, October, November, December</span></span>
    
  - <span data-ttu-id="9919e-146">Jan Feb maart Apr Mei Jun-Jul-Sep-Sept Oct OKT Nov Dec</span><span class="sxs-lookup"><span data-stu-id="9919e-146">jan feb maart apr mei jun jul aug sep sept oct okt nov dec</span></span>
    
- <span data-ttu-id="9919e-147">Francés</span><span class="sxs-lookup"><span data-stu-id="9919e-147">French</span></span>
    
  - <span data-ttu-id="9919e-148">Janvier, février, Mars, Avril, Mai, juin Juillet, Août, Septembre, octobre, Novembre, décembre</span><span class="sxs-lookup"><span data-stu-id="9919e-148">janvier, février, mars, avril, mai, juin juillet, août, septembre, octobre, novembre, décembre</span></span>
    
  - <span data-ttu-id="9919e-149">janv.</span><span class="sxs-lookup"><span data-stu-id="9919e-149">janv.</span></span> <span data-ttu-id="9919e-150">févr.</span><span class="sxs-lookup"><span data-stu-id="9919e-150">févr.</span></span> <span data-ttu-id="9919e-151">Mars Avril Mai juin juil.</span><span class="sxs-lookup"><span data-stu-id="9919e-151">mars avril mai juin juil.</span></span> <span data-ttu-id="9919e-152">Août Sept.</span><span class="sxs-lookup"><span data-stu-id="9919e-152">août sept.</span></span> <span data-ttu-id="9919e-153">Oct.</span><span class="sxs-lookup"><span data-stu-id="9919e-153">oct.</span></span> <span data-ttu-id="9919e-154">noviembre.</span><span class="sxs-lookup"><span data-stu-id="9919e-154">nov.</span></span> <span data-ttu-id="9919e-155">déc.</span><span class="sxs-lookup"><span data-stu-id="9919e-155">déc.</span></span>
    
- <span data-ttu-id="9919e-156">Alemán</span><span class="sxs-lookup"><span data-stu-id="9919e-156">German</span></span>
    
  - <span data-ttu-id="9919e-157">Januar, Februar, März, April, Mai, Juni Juli, agosto, septiembre, Oktober, noviembre, Dezember</span><span class="sxs-lookup"><span data-stu-id="9919e-157">jänuar, februar, märz, April, mai, juni juli, August, September, oktober, November, dezember</span></span>
    
  - <span data-ttu-id="9919e-158">Ene./Jän.</span><span class="sxs-lookup"><span data-stu-id="9919e-158">Jan./Jän.</span></span> <span data-ttu-id="9919e-159">Feb. März Apr. Mai Juni Juli agosto de la OKT.</span><span class="sxs-lookup"><span data-stu-id="9919e-159">Feb. März Apr. Mai Juni Juli Aug. Sept. Okt.</span></span> <span data-ttu-id="9919e-160">Nov dez.</span><span class="sxs-lookup"><span data-stu-id="9919e-160">Nov. Dez.</span></span>
    
- <span data-ttu-id="9919e-161">Italiano</span><span class="sxs-lookup"><span data-stu-id="9919e-161">Italian</span></span>
    
  - <span data-ttu-id="9919e-162">Gennaio, Febbraio, marzo, Aprile, Maggio, Giugno, Luglio, agosto, Settembre, Ottobre, Novembre, dicembre</span><span class="sxs-lookup"><span data-stu-id="9919e-162">gennaio, febbraio, marzo, aprile, maggio, giugno, luglio, agosto, settembre, ottobre, novembre, dicembre</span></span>
    
  - <span data-ttu-id="9919e-163">Genn.</span><span class="sxs-lookup"><span data-stu-id="9919e-163">genn.</span></span> <span data-ttu-id="9919e-164">febbr.</span><span class="sxs-lookup"><span data-stu-id="9919e-164">febbr.</span></span> <span data-ttu-id="9919e-165">graduación.</span><span class="sxs-lookup"><span data-stu-id="9919e-165">mar.</span></span> <span data-ttu-id="9919e-166">TA.</span><span class="sxs-lookup"><span data-stu-id="9919e-166">apr.</span></span> <span data-ttu-id="9919e-167">Magg.</span><span class="sxs-lookup"><span data-stu-id="9919e-167">magg.</span></span> <span data-ttu-id="9919e-168">Giugno Luglio AG.</span><span class="sxs-lookup"><span data-stu-id="9919e-168">giugno luglio ag.</span></span> <span data-ttu-id="9919e-169">SETT.</span><span class="sxs-lookup"><span data-stu-id="9919e-169">sett.</span></span> <span data-ttu-id="9919e-170">Ott.</span><span class="sxs-lookup"><span data-stu-id="9919e-170">ott.</span></span> <span data-ttu-id="9919e-171">noviembre.</span><span class="sxs-lookup"><span data-stu-id="9919e-171">nov.</span></span> <span data-ttu-id="9919e-172">Dic.</span><span class="sxs-lookup"><span data-stu-id="9919e-172">dic.</span></span>
    
- <span data-ttu-id="9919e-173">Portugués</span><span class="sxs-lookup"><span data-stu-id="9919e-173">Portuguese</span></span>
    
  - <span data-ttu-id="9919e-174">janeiro, fevereiro, março, marco, abril, maio, junho, julho, agosto, setembro, outubro, novembro, dezembro</span><span class="sxs-lookup"><span data-stu-id="9919e-174">janeiro, fevereiro, março, marco, abril, maio, junho, julho, agosto, setembro, outubro, novembro, dezembro</span></span>
    
  - <span data-ttu-id="9919e-175">Jan FEV mar abr Mai Jun-Nov hace dez</span><span class="sxs-lookup"><span data-stu-id="9919e-175">jan fev mar abr mai jun jul ago set out nov dez</span></span>
    
- <span data-ttu-id="9919e-176">Español</span><span class="sxs-lookup"><span data-stu-id="9919e-176">Spanish</span></span>
    
  - <span data-ttu-id="9919e-177">enero, febrero, marzo, abril, mayo, junio, julio, agosto, septiembre, octubre, noviembre, diciembre</span><span class="sxs-lookup"><span data-stu-id="9919e-177">enero, febrero, marzo, abril, mayo, junio, julio, agosto, septiembre, octubre, noviembre, diciembre</span></span>
    
  - <span data-ttu-id="9919e-178">Enero Feb.</span><span class="sxs-lookup"><span data-stu-id="9919e-178">enero feb.</span></span> <span data-ttu-id="9919e-179">marzo Abr.</span><span class="sxs-lookup"><span data-stu-id="9919e-179">marzo abr.</span></span> <span data-ttu-id="9919e-180">Mayo Jun.</span><span class="sxs-lookup"><span data-stu-id="9919e-180">mayo jun.</span></span> <span data-ttu-id="9919e-181">Julio.</span><span class="sxs-lookup"><span data-stu-id="9919e-181">jul.</span></span> <span data-ttu-id="9919e-182">Agosto Sept./set.</span><span class="sxs-lookup"><span data-stu-id="9919e-182">agosto sept./set.</span></span> <span data-ttu-id="9919e-183">Oct.</span><span class="sxs-lookup"><span data-stu-id="9919e-183">oct.</span></span> <span data-ttu-id="9919e-184">noviembre.</span><span class="sxs-lookup"><span data-stu-id="9919e-184">nov.</span></span> <span data-ttu-id="9919e-185">Dic.</span><span class="sxs-lookup"><span data-stu-id="9919e-185">dic.</span></span>
    
## <a name="funceudate1-deprecated"></a><span data-ttu-id="9919e-186">Func_eu_date1 (en desuso)</span><span class="sxs-lookup"><span data-stu-id="9919e-186">Func_eu_date1 (deprecated)</span></span>

> [!NOTE]
> <span data-ttu-id="9919e-187">Esta función está en desuso porque solo admite nombres de mes en Portugués, que ahora están incluidos en `Func_eu_date` la función anterior.</span><span class="sxs-lookup"><span data-stu-id="9919e-187">This function is deprecated because it supports only Portuguese month names, which are now included in the  `Func_eu_date` function above.</span></span> 
  
<span data-ttu-id="9919e-188">Esta función busca una fecha en el formato que suele usarse en portugués.</span><span class="sxs-lookup"><span data-stu-id="9919e-188">This function looks for a date in the format commonly used in Portuguese.</span></span> <span data-ttu-id="9919e-189">El formato de esta función es el mismo que `Func_eu_date`en el idioma usado.</span><span class="sxs-lookup"><span data-stu-id="9919e-189">The format for this function is the same as  `Func_eu_date`, differing only in the language used.</span></span>
  
<span data-ttu-id="9919e-190">Ejemplos:</span><span class="sxs-lookup"><span data-stu-id="9919e-190">Examples:</span></span>
  
- <span data-ttu-id="9919e-191">2 dez 2016</span><span class="sxs-lookup"><span data-stu-id="9919e-191">2 Dez 2016</span></span>
    
- <span data-ttu-id="9919e-192">02 dez 2016</span><span class="sxs-lookup"><span data-stu-id="9919e-192">02 dez 2016</span></span>
    
- <span data-ttu-id="9919e-193">2 dez 16</span><span class="sxs-lookup"><span data-stu-id="9919e-193">2 Dez 16</span></span>
    
- <span data-ttu-id="9919e-194">2/12/2016</span><span class="sxs-lookup"><span data-stu-id="9919e-194">2/12/2016</span></span>
    
- <span data-ttu-id="9919e-195">02/12/16</span><span class="sxs-lookup"><span data-stu-id="9919e-195">02/12/16</span></span>
    
- <span data-ttu-id="9919e-196">2-dez-2016</span><span class="sxs-lookup"><span data-stu-id="9919e-196">2-Dez-2016</span></span>
    
- <span data-ttu-id="9919e-197">2-12-16</span><span class="sxs-lookup"><span data-stu-id="9919e-197">2-12-16</span></span>
    
<span data-ttu-id="9919e-198">Nombres de mes aceptados:</span><span class="sxs-lookup"><span data-stu-id="9919e-198">Accepted month names:</span></span>
  
- <span data-ttu-id="9919e-199">Portugués</span><span class="sxs-lookup"><span data-stu-id="9919e-199">Portuguese</span></span>
    
  - <span data-ttu-id="9919e-200">janeiro, fevereiro, março, marco, abril, maio, junho, julho, agosto, setembro, outubro, novembro, dezembro</span><span class="sxs-lookup"><span data-stu-id="9919e-200">janeiro, fevereiro, março, marco, abril, maio, junho, julho, agosto, setembro, outubro, novembro, dezembro</span></span>
    
  - <span data-ttu-id="9919e-201">Jan FEV mar abr Mai Jun-Nov hace dez</span><span class="sxs-lookup"><span data-stu-id="9919e-201">jan fev mar abr mai jun jul ago set out nov dez</span></span>
    
## <a name="funceudate2-deprecated"></a><span data-ttu-id="9919e-202">Func_eu_date2 (en desuso)</span><span class="sxs-lookup"><span data-stu-id="9919e-202">Func_eu_date2 (deprecated)</span></span>

> [!NOTE]
> <span data-ttu-id="9919e-203">Esta función está en desuso porque solo admite nombres de mes en holandés, que ahora están incluidos en `Func_eu_date` la función anterior.</span><span class="sxs-lookup"><span data-stu-id="9919e-203">This function is deprecated because it supports only Dutch month names, which are now included in the  `Func_eu_date` function above.</span></span> 
  
<span data-ttu-id="9919e-204">Esta función busca una fecha en el formato que suele usarse en neerlandés.</span><span class="sxs-lookup"><span data-stu-id="9919e-204">This function looks for a date in the format commonly used in Dutch.</span></span> <span data-ttu-id="9919e-205">El formato de esta función es el mismo que `Func_eu_date`en el idioma usado.</span><span class="sxs-lookup"><span data-stu-id="9919e-205">The format for this function is the same as  `Func_eu_date`, differing only in the language used.</span></span>
  
<span data-ttu-id="9919e-206">Ejemplos:</span><span class="sxs-lookup"><span data-stu-id="9919e-206">Examples:</span></span>
  
- <span data-ttu-id="9919e-207">2 Mei 2016</span><span class="sxs-lookup"><span data-stu-id="9919e-207">2 Mei 2016</span></span>
    
- <span data-ttu-id="9919e-208">02 Mei 2016</span><span class="sxs-lookup"><span data-stu-id="9919e-208">02 mei 2016</span></span>
    
- <span data-ttu-id="9919e-209">2 Mei 16</span><span class="sxs-lookup"><span data-stu-id="9919e-209">2 Mei 16</span></span>
    
- <span data-ttu-id="9919e-210">2/12/2016</span><span class="sxs-lookup"><span data-stu-id="9919e-210">2/12/2016</span></span>
    
- <span data-ttu-id="9919e-211">02/12/16</span><span class="sxs-lookup"><span data-stu-id="9919e-211">02/12/16</span></span>
    
- <span data-ttu-id="9919e-212">2-Mei-2016</span><span class="sxs-lookup"><span data-stu-id="9919e-212">2-Mei-2016</span></span>
    
- <span data-ttu-id="9919e-213">2-12-16</span><span class="sxs-lookup"><span data-stu-id="9919e-213">2-12-16</span></span>
    
<span data-ttu-id="9919e-214">Nombres de mes aceptados:</span><span class="sxs-lookup"><span data-stu-id="9919e-214">Accepted month names:</span></span>
  
- <span data-ttu-id="9919e-215">Neerlandés</span><span class="sxs-lookup"><span data-stu-id="9919e-215">Dutch</span></span>
    
  - <span data-ttu-id="9919e-216">januari, februari, maart, April, mei, juni, juli, augustus, September, ocktober, October, November, December</span><span class="sxs-lookup"><span data-stu-id="9919e-216">januari, februari, maart, April, mei, juni, juli, augustus, September, ocktober, October, November, December</span></span>
    
  - <span data-ttu-id="9919e-217">Jan Feb maart Apr Mei Jun-Jul-Sep-Sept Oct OKT Nov Dec</span><span class="sxs-lookup"><span data-stu-id="9919e-217">jan feb maart apr mei jun jul aug sep sept oct okt nov dec</span></span>
    
## <a name="funcexpirationdate"></a><span data-ttu-id="9919e-218">Func_expiration_date</span><span class="sxs-lookup"><span data-stu-id="9919e-218">Func_expiration_date</span></span>

<span data-ttu-id="9919e-219">Esta función busca una fecha en los formatos que suelen usarse en las tarjetas de crédito y débito, que excluyen los días a favor de los meses.</span><span class="sxs-lookup"><span data-stu-id="9919e-219">This function looks for a date in the formats commonly used by credit and debit cards, which exclude days in favor of months.</span></span> <span data-ttu-id="9919e-220">Esta función coincidirá con las fechas en el formato "mes/año", "mes-año", "[nombre del mes]" y "[abreviatura del mes] año".</span><span class="sxs-lookup"><span data-stu-id="9919e-220">This function will match dates in format of "month/year", "month-year", "[month name] year", and "[month abbreviation] year".</span></span> <span data-ttu-id="9919e-221">Los nombres o las abreviaturas de los meses no distinguen mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="9919e-221">The names or abbreviations of months are not case sensitive.</span></span>
  
<span data-ttu-id="9919e-222">Ejemplos:</span><span class="sxs-lookup"><span data-stu-id="9919e-222">Examples:</span></span>
  
- <span data-ttu-id="9919e-223">MM/AA: por ejemplo, 01/11 o 1/11</span><span class="sxs-lookup"><span data-stu-id="9919e-223">MM/YY -- for example, 01/11 or 1/11</span></span>
    
- <span data-ttu-id="9919e-224">MM/AAAA: por ejemplo, 01/2011 o 1/2011</span><span class="sxs-lookup"><span data-stu-id="9919e-224">MM/YYYY -- for example, 01/2011 or 1/2011</span></span>
    
- <span data-ttu-id="9919e-225">MM-AA: por ejemplo 01-11 o 1-11</span><span class="sxs-lookup"><span data-stu-id="9919e-225">MM-YY -- for example, 01-22 or 1-11</span></span>
    
- <span data-ttu-id="9919e-226">MM-AAAA: por ejemplo 01-2000 o 1-2000</span><span class="sxs-lookup"><span data-stu-id="9919e-226">MM-YYYY -- for example, 01-2000 or 1-2000</span></span>
    
<span data-ttu-id="9919e-227">Los formatos siguientes admiten AA o AAAA:</span><span class="sxs-lookup"><span data-stu-id="9919e-227">The following formats support YY or YYYY:</span></span>
  
- <span data-ttu-id="9919e-228">Mes-AAAA: por ejemplo, ene-2010, enero-2010, ene-10 o enero-10</span><span class="sxs-lookup"><span data-stu-id="9919e-228">Month-YYYY -- for example, .Jan-2010 or january-2010 or Jan-10 or january-10</span></span>
    
- <span data-ttu-id="9919e-229">Mes AAAA: por ejemplo, "enero 2010", "ene. 2010", "enero 10" o "ene. 10"</span><span class="sxs-lookup"><span data-stu-id="9919e-229">Month YYYY -- for example, 'january 2010' or 'Jan 2010' or 'january 10' or 'Jan 10'</span></span>
    
- <span data-ttu-id="9919e-230">MesAAAA: por ejemplo, "enero2010", "ene2010", "enero10" o "ene10"</span><span class="sxs-lookup"><span data-stu-id="9919e-230">MonthYYYY -- for example, 'january2010' or 'Jan2010' or 'january10' or 'Jan10'</span></span>
    
- <span data-ttu-id="9919e-231">Mes/AAAA: por ejemplo, "enero/2010" o "ene/2010" o "enero/10" o "ene/10"</span><span class="sxs-lookup"><span data-stu-id="9919e-231">Month/YYYY -- for example, 'january/2010' or 'Jan/2010' or 'january/10' or 'Jan/10'</span></span>
    
<span data-ttu-id="9919e-232">Nombres de mes aceptados:</span><span class="sxs-lookup"><span data-stu-id="9919e-232">Accepted month names:</span></span>
  
- <span data-ttu-id="9919e-233">Inglés</span><span class="sxs-lookup"><span data-stu-id="9919e-233">English</span></span>
    
  - <span data-ttu-id="9919e-234">Enero, febrero, marzo, abril, mayo, junio, julio, agosto, septiembre, octubre, noviembre, diciembre</span><span class="sxs-lookup"><span data-stu-id="9919e-234">January, February, march, April, may, June, July, August, September, October, November, December</span></span>
    
  - <span data-ttu-id="9919e-235">Jan Feb Marzo Apr mayo junio julio agosto Sept Oct Nov Dic</span><span class="sxs-lookup"><span data-stu-id="9919e-235">Jan Feb Mar Apr May June July Aug Sept Oct Nov Dec</span></span>
    
## <a name="funcusaddress"></a><span data-ttu-id="9919e-236">Func_us_address</span><span class="sxs-lookup"><span data-stu-id="9919e-236">Func_us_address</span></span>

<span data-ttu-id="9919e-p113">Esta función busca un nombre de estado de los Estados Unidos o una abreviatura postal seguidos de un código postal válido, tal como se usan en las direcciones postales. El código postal debe ser uno de los códigos postales correctos asociados al nombre del estado de los Estados Unidos o su abreviatura. El nombre de estado de los Estados Unidos y el código postal no pueden estar separados por signos de puntuación o letras.</span><span class="sxs-lookup"><span data-stu-id="9919e-p113">This function looks for a U.S. state name or postal abbreviation followed by a valid zip code, just as they are used in postal addresses. The zip code must be one of the correct zip codes associated with the U.S. state name or abbreviation. The U.S. state name and zip code cannot be separated by punctuation or letters.</span></span>
  
<span data-ttu-id="9919e-240">Ejemplos:</span><span class="sxs-lookup"><span data-stu-id="9919e-240">Examples:</span></span>
  
- <span data-ttu-id="9919e-241">Washington 98052</span><span class="sxs-lookup"><span data-stu-id="9919e-241">Washington 98052</span></span>
    
- <span data-ttu-id="9919e-242">Washington 98052-9998</span><span class="sxs-lookup"><span data-stu-id="9919e-242">Washington 98052-9998</span></span>
    
- <span data-ttu-id="9919e-243">WA 98052</span><span class="sxs-lookup"><span data-stu-id="9919e-243">WA 98052</span></span>
    
- <span data-ttu-id="9919e-244">WA 98052-9998</span><span class="sxs-lookup"><span data-stu-id="9919e-244">WA 98052-9998</span></span>
    

