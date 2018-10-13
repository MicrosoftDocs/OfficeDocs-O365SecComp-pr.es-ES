---
title: Cadenas de certificados de Office 365
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 6/26/2018
ms.audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
ms.assetid: 0c03e6b3-e73f-4316-9e2b-bf4091ae96bb
description: Office 365 aprovecha un número de proveedores de certificado diferentes. A continuación describe la lista completa de certificados de raíz de Office 365 conocidos que pueden encontrar los clientes al obtener acceso a Office 365. Para obtener información acerca de los certificados debe instalar en su propia infraestructura, vea Plan for certificados SSL de terceros para Office 365. La siguiente información del certificado se aplica a todas las instancias de la nube en todo el mundo y nacionales de Office 365.
ms.openlocfilehash: 1dcc2dc38bb8e3239a3be3983791b0c60917dc5e
ms.sourcegitcommit: 13f40ff7c1799152bf45af2d8110f4f3235b770a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/12/2018
ms.locfileid: "25549773"
---
# <a name="office-365-certificate-chains"></a><span data-ttu-id="a8dfa-106">Cadenas de certificados de Office 365</span><span class="sxs-lookup"><span data-stu-id="a8dfa-106">Office 365 Certificate Chains</span></span>

<span data-ttu-id="a8dfa-p102">Office 365 aprovecha un número de proveedores de certificado diferentes. A continuación describe la lista completa de certificados de raíz de Office 365 conocidos que pueden encontrar los clientes al obtener acceso a Office 365. Para obtener información sobre los certificados que necesita instalar en su propia infraestructura, consulte [Plan para los certificados SSL de terceros para Office 365](https://support.office.com/article/b48cdf63-07e0-4cda-8c12-4871590f59ce). La siguiente información del certificado se aplica a todas las instancias de la nube en todo el mundo y nacionales de Office 365.</span><span class="sxs-lookup"><span data-stu-id="a8dfa-p102">Office 365 leverages a number of different certificate providers. The following describes the complete list of known Office 365 root certificates that customers may encounter when accessing Office 365. For information on the certificates you may need to install in your own infrastructure, see [Plan for third-party SSL certificates for Office 365](https://support.office.com/article/b48cdf63-07e0-4cda-8c12-4871590f59ce). The following certificate information applies to all worldwide and national cloud instances of Office 365.</span></span>
  

|<span data-ttu-id="a8dfa-111">**Tipo de certificado**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-111">**Certificate type**</span></span>|<span data-ttu-id="a8dfa-112">**Descarga de P7b**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-112">**P7b download**</span></span>|<span data-ttu-id="a8dfa-113">**Extremos CRL**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-113">**CRL Endpoints**</span></span>|<span data-ttu-id="a8dfa-114">**Extremos OCSP**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-114">**OCSP Endpoints**</span></span>|<span data-ttu-id="a8dfa-115">**Extremos AIA**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-115">**AIA Endpoints**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|[<span data-ttu-id="a8dfa-116">Certificados raíz de confianza públicamente</span><span class="sxs-lookup"><span data-stu-id="a8dfa-116">Publicly Trusted Root Certificates</span></span>](https://support.office.com/article/0c03e6b3-e73f-4316-9e2b-bf4091ae96bb#rootcerts) <br/> |[<span data-ttu-id="a8dfa-117">Agrupación de certificado raíz de Office 365 (P7B)</span><span class="sxs-lookup"><span data-stu-id="a8dfa-117">Office 365 Root Certificate Bundle (P7B)</span></span>](http://download.microsoft.com/download/A/5/A/A5AE01F3-D19B-4A11-9407-801263CEF72C/O365_Root_Certs_20170321.p7b) <br/> |<span data-ttu-id="a8dfa-118">CRL.GlobalSign.NET</span><span class="sxs-lookup"><span data-stu-id="a8dfa-118">crl.globalsign.net</span></span>  <br/> <span data-ttu-id="a8dfa-119">www.d-Trust.NET</span><span class="sxs-lookup"><span data-stu-id="a8dfa-119">www.d-trust.net</span></span>  <br/> |<span data-ttu-id="a8dfa-120">N/D</span><span class="sxs-lookup"><span data-stu-id="a8dfa-120">N/A</span></span>  <br/> |<span data-ttu-id="a8dfa-121">N/D</span><span class="sxs-lookup"><span data-stu-id="a8dfa-121">N/A</span></span>  <br/> |
|[<span data-ttu-id="a8dfa-122">Los certificados intermedios de confianza públicamente</span><span class="sxs-lookup"><span data-stu-id="a8dfa-122">Publicly Trusted Intermediate Certificates</span></span>](https://support.office.com/article/0c03e6b3-e73f-4316-9e2b-bf4091ae96bb#IntermediateCerts) <br/> |[<span data-ttu-id="a8dfa-123">Agrupación de certificados intermedios de Office 365 (P7B)</span><span class="sxs-lookup"><span data-stu-id="a8dfa-123">Office 365 Intermediate Certificate Bundle (P7B)</span></span>](http://download.microsoft.com/download/4/D/5/4D5339A4-0A4A-46AB-AE52-B179DEDA4BEC/O365_Intermediate_Certs_20170321.p7b)  <br/> |<span data-ttu-id="a8dfa-124">cdp1.Public trust.com</span><span class="sxs-lookup"><span data-stu-id="a8dfa-124">cdp1.public-trust.com</span></span>  <br/> <span data-ttu-id="a8dfa-125">CRL.cnnic.CN</span><span class="sxs-lookup"><span data-stu-id="a8dfa-125">crl.cnnic.cn</span></span>  <br/> <span data-ttu-id="a8dfa-126">CRL.Entrust.NET</span><span class="sxs-lookup"><span data-stu-id="a8dfa-126">crl.entrust.net</span></span>  <br/> <span data-ttu-id="a8dfa-127">CRL.GlobalSign.com</span><span class="sxs-lookup"><span data-stu-id="a8dfa-127">crl.globalsign.com</span></span>  <br/> <span data-ttu-id="a8dfa-128">CRL.GlobalSign.NET</span><span class="sxs-lookup"><span data-stu-id="a8dfa-128">crl.globalsign.net</span></span>  <br/> <span data-ttu-id="a8dfa-129">CRL.identrust.com</span><span class="sxs-lookup"><span data-stu-id="a8dfa-129">crl.identrust.com</span></span>  <br/> <span data-ttu-id="a8dfa-130">CRL.Thawte.com</span><span class="sxs-lookup"><span data-stu-id="a8dfa-130">crl.thawte.com</span></span>  <br/> <span data-ttu-id="a8dfa-131">crl3.digicert.com</span><span class="sxs-lookup"><span data-stu-id="a8dfa-131">crl3.digicert.com</span></span>  <br/> <span data-ttu-id="a8dfa-132">crl4.digicert.com</span><span class="sxs-lookup"><span data-stu-id="a8dfa-132">crl4.digicert.com</span></span>  <br/> <span data-ttu-id="a8dfa-133">s1.symcb.com</span><span class="sxs-lookup"><span data-stu-id="a8dfa-133">s1.symcb.com</span></span>  <br/> <span data-ttu-id="a8dfa-134">www.d-Trust.NET</span><span class="sxs-lookup"><span data-stu-id="a8dfa-134">www.d-trust.net</span></span>  <br/> |<span data-ttu-id="a8dfa-135">isrg.trustid.OCSP.identrust.com</span><span class="sxs-lookup"><span data-stu-id="a8dfa-135">isrg.trustid.ocsp.identrust.com</span></span>  <br/> <span data-ttu-id="a8dfa-136">OCSP.digicert.com</span><span class="sxs-lookup"><span data-stu-id="a8dfa-136">ocsp.digicert.com</span></span>  <br/> <span data-ttu-id="a8dfa-137">OCSP.Entrust.NET</span><span class="sxs-lookup"><span data-stu-id="a8dfa-137">ocsp.entrust.net</span></span>  <br/> <span data-ttu-id="a8dfa-138">OCSP.GlobalSign.com</span><span class="sxs-lookup"><span data-stu-id="a8dfa-138">ocsp.globalsign.com</span></span>  <br/> <span data-ttu-id="a8dfa-139">OCSP.OmniRoot.com</span><span class="sxs-lookup"><span data-stu-id="a8dfa-139">ocsp.omniroot.com</span></span>  <br/> <span data-ttu-id="a8dfa-140">OCSP.startssl.com</span><span class="sxs-lookup"><span data-stu-id="a8dfa-140">ocsp.startssl.com</span></span>  <br/> <span data-ttu-id="a8dfa-141">OCSP.Thawte.com</span><span class="sxs-lookup"><span data-stu-id="a8dfa-141">ocsp.thawte.com</span></span>  <br/> <span data-ttu-id="a8dfa-142">ocsp2.GlobalSign.com</span><span class="sxs-lookup"><span data-stu-id="a8dfa-142">ocsp2.globalsign.com</span></span>  <br/> <span data-ttu-id="a8dfa-143">ocspcnnicroot.cnnic.CN</span><span class="sxs-lookup"><span data-stu-id="a8dfa-143">ocspcnnicroot.cnnic.cn</span></span>  <br/> <span data-ttu-id="a8dfa-144">raíz-c3-ca2-2009.ocsp.d-trust.net</span><span class="sxs-lookup"><span data-stu-id="a8dfa-144">root-c3-ca2-2009.ocsp.d-trust.net</span></span>  <br/> <span data-ttu-id="a8dfa-145">root-C3-cA2-EV-2009.OCSP.d-Trust.NET</span><span class="sxs-lookup"><span data-stu-id="a8dfa-145">root-c3-ca2-ev-2009.ocsp.d-trust.net</span></span>  <br/> <span data-ttu-id="a8dfa-146">s2.symcb.com</span><span class="sxs-lookup"><span data-stu-id="a8dfa-146">s2.symcb.com</span></span>  <br/> |<span data-ttu-id="a8dfa-147">AIA.startssl.com</span><span class="sxs-lookup"><span data-stu-id="a8dfa-147">aia.startssl.com</span></span>  <br/> <span data-ttu-id="a8dfa-148">Apps.identrust.com</span><span class="sxs-lookup"><span data-stu-id="a8dfa-148">apps.identrust.com</span></span>  <br/> <span data-ttu-id="a8dfa-149">CACert.OmniRoot.com</span><span class="sxs-lookup"><span data-stu-id="a8dfa-149">cacert.omniroot.com</span></span>  <br/> <span data-ttu-id="a8dfa-150">www.cnnic.CN</span><span class="sxs-lookup"><span data-stu-id="a8dfa-150">www.cnnic.cn</span></span>  <br/> |
   
<span data-ttu-id="a8dfa-151">Expanda la raíz y las secciones intermedias para ver detalles adicionales acerca de los proveedores de certificado.</span><span class="sxs-lookup"><span data-stu-id="a8dfa-151">Expand the root and intermediate sections below to see additional details about the certificate providers.</span></span>
  
## <a name="office-365-root-certificate-details"></a><span data-ttu-id="a8dfa-152">Detalles del certificado de raíz de Office 365</span><span class="sxs-lookup"><span data-stu-id="a8dfa-152">Office 365 Root Certificate Details</span></span>
<span data-ttu-id="a8dfa-153"><a name="RootCerts"> </a></span><span class="sxs-lookup"><span data-stu-id="a8dfa-153"></span></span>

 <span data-ttu-id="a8dfa-154">**Baltimore CyberTrust Root**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-154">**Baltimore CyberTrust Root**</span></span>
  
<span data-ttu-id="a8dfa-155">|:-----|</span><span class="sxs-lookup"><span data-stu-id="a8dfa-155">|:-----|</span></span>
|<span data-ttu-id="a8dfa-156">**Asunto**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-156">**Subject**</span></span>|
|:-----|
|<span data-ttu-id="a8dfa-157">**Número de serie**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-157">**Serial Number**</span></span>|
|<span data-ttu-id="a8dfa-158">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-158"></span></span>|
|<span data-ttu-id="a8dfa-159">**Longitud de clave pública**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-159">**Public Key Length**</span></span>|
|<span data-ttu-id="a8dfa-160">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-160"></span></span>|
|<span data-ttu-id="a8dfa-161">**Algoritmo de firma**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-161">**Signature Algorithm**</span></span>|
|<span data-ttu-id="a8dfa-162">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-162"></span></span>|
|<span data-ttu-id="a8dfa-163">**Validez no antes**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-163">**Validity Not Before**</span></span>|
|<span data-ttu-id="a8dfa-164">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-164"></span></span>|
|<span data-ttu-id="a8dfa-165">**Validez no después**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-165">**Validity Not After**</span></span>|
|<span data-ttu-id="a8dfa-166">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-166"></span></span>|
|<span data-ttu-id="a8dfa-167">**Identificador de clave de asunto**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-167">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="a8dfa-168">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-168"></span></span>|
|<span data-ttu-id="a8dfa-169">**Huella digital (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-169">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="a8dfa-170">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-170"></span></span>|
|<span data-ttu-id="a8dfa-171">**Huella digital (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-171">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="a8dfa-172">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-172"></span></span>|
|<span data-ttu-id="a8dfa-173">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-173">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="a8dfa-174">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-174"></span></span>|
   
 <span data-ttu-id="a8dfa-175">**RAÍZ DE CNNIC**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-175">**CNNIC ROOT**</span></span>
  
||
|:-----|
|<span data-ttu-id="a8dfa-176">**Asunto**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-176">**Subject**</span></span>|
|<span data-ttu-id="a8dfa-177">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-177"></span></span>|
|<span data-ttu-id="a8dfa-178">**Número de serie**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-178">**Serial Number**</span></span>|
|<span data-ttu-id="a8dfa-179">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-179"></span></span>|
|<span data-ttu-id="a8dfa-180">**Longitud de clave pública**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-180">**Public Key Length**</span></span>|
|<span data-ttu-id="a8dfa-181">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-181"></span></span>|
|<span data-ttu-id="a8dfa-182">**Algoritmo de firma**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-182">**Signature Algorithm**</span></span>|
|<span data-ttu-id="a8dfa-183">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-183"></span></span>|
|<span data-ttu-id="a8dfa-184">**Validez no antes**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-184">**Validity Not Before**</span></span>|
|<span data-ttu-id="a8dfa-185">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-185"></span></span>|
|<span data-ttu-id="a8dfa-186">**Validez no después**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-186">**Validity Not After**</span></span>|
|<span data-ttu-id="a8dfa-187">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-187"></span></span>|
|<span data-ttu-id="a8dfa-188">**Identificador de clave de asunto**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-188">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="a8dfa-189">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-189"></span></span>|
|<span data-ttu-id="a8dfa-190">**Identificador de clave de entidad de certificación**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-190">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="a8dfa-191">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-191"></span></span>|
|<span data-ttu-id="a8dfa-192">**Huella digital (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-192">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="a8dfa-193">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-193"></span></span>|
|<span data-ttu-id="a8dfa-194">**Huella digital (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-194">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="a8dfa-195">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-195"></span></span>|
|<span data-ttu-id="a8dfa-196">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-196">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="a8dfa-197">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-197"></span></span>|
   
 <span data-ttu-id="a8dfa-198">**DigiCert de entidad de certificación raíz Global**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-198">**DigiCert Global Root CA**</span></span>
  
||
|:-----|
|<span data-ttu-id="a8dfa-199">**Asunto**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-199">**Subject**</span></span>|
|<span data-ttu-id="a8dfa-200">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-200"></span></span>|
|<span data-ttu-id="a8dfa-201">**Número de serie**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-201">**Serial Number**</span></span>|
|<span data-ttu-id="a8dfa-202">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-202"></span></span>|
|<span data-ttu-id="a8dfa-203">**Longitud de clave pública**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-203">**Public Key Length**</span></span>|
|<span data-ttu-id="a8dfa-204">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-204"></span></span>|
|<span data-ttu-id="a8dfa-205">**Algoritmo de firma**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-205">**Signature Algorithm**</span></span>|
|<span data-ttu-id="a8dfa-206">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-206"></span></span>|
|<span data-ttu-id="a8dfa-207">**Validez no antes**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-207">**Validity Not Before**</span></span>|
|<span data-ttu-id="a8dfa-208">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-208"></span></span>|
|<span data-ttu-id="a8dfa-209">**Validez no después**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-209">**Validity Not After**</span></span>|
|<span data-ttu-id="a8dfa-210">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-210"></span></span>|
|<span data-ttu-id="a8dfa-211">**Identificador de clave de asunto**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-211">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="a8dfa-212">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-212"></span></span>|
|<span data-ttu-id="a8dfa-213">**Identificador de clave de entidad de certificación**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-213">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="a8dfa-214">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-214"></span></span>|
|<span data-ttu-id="a8dfa-215">**Huella digital (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-215">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="a8dfa-216">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-216"></span></span>|
|<span data-ttu-id="a8dfa-217">**Huella digital (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-217">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="a8dfa-218">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-218"></span></span>|
|<span data-ttu-id="a8dfa-219">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-219">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="a8dfa-220">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-220"></span></span>|
   
 <span data-ttu-id="a8dfa-221">**Entidad de certificación raíz de DigiCert High Assurance EV**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-221">**DigiCert High Assurance EV Root CA**</span></span>
  
||
|:-----|
|<span data-ttu-id="a8dfa-222">**Asunto**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-222">**Subject**</span></span>|
|<span data-ttu-id="a8dfa-223">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-223"></span></span>|
|<span data-ttu-id="a8dfa-224">**Número de serie**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-224">**Serial Number**</span></span>|
|<span data-ttu-id="a8dfa-225">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-225"></span></span>|
|<span data-ttu-id="a8dfa-226">**Longitud de clave pública**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-226">**Public Key Length**</span></span>|
|<span data-ttu-id="a8dfa-227">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-227"></span></span>|
|<span data-ttu-id="a8dfa-228">**Algoritmo de firma**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-228">**Signature Algorithm**</span></span>|
|<span data-ttu-id="a8dfa-229">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-229"></span></span>|
|<span data-ttu-id="a8dfa-230">**Validez no antes**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-230">**Validity Not Before**</span></span>|
|<span data-ttu-id="a8dfa-231">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-231"></span></span>|
|<span data-ttu-id="a8dfa-232">**Validez no después**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-232">**Validity Not After**</span></span>|
|<span data-ttu-id="a8dfa-233">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-233"></span></span>|
|<span data-ttu-id="a8dfa-234">**Identificador de clave de asunto**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-234">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="a8dfa-235">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-235"></span></span>|
|<span data-ttu-id="a8dfa-236">**Identificador de clave de entidad de certificación**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-236">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="a8dfa-237">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-237"></span></span>|
|<span data-ttu-id="a8dfa-238">**Huella digital (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-238">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="a8dfa-239">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-239"></span></span>|
|<span data-ttu-id="a8dfa-240">**Huella digital (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-240">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="a8dfa-241">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-241"></span></span>|
|<span data-ttu-id="a8dfa-242">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-242">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="a8dfa-243">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-243"></span></span>|
   
 <span data-ttu-id="a8dfa-244">**Entidad de certificación de raíz de confianza de D clase 3 2 de 2009**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-244">**D-TRUST Root Class 3 CA 2 2009**</span></span>
  
||
|:-----|
|<span data-ttu-id="a8dfa-245">**Asunto**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-245">**Subject**</span></span>|
|<span data-ttu-id="a8dfa-246">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-246"></span></span>|
|<span data-ttu-id="a8dfa-247">**Número de serie**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-247">**Serial Number**</span></span>|
|<span data-ttu-id="a8dfa-248">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-248"></span></span>|
|<span data-ttu-id="a8dfa-249">**Longitud de clave pública**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-249">**Public Key Length**</span></span>|
|<span data-ttu-id="a8dfa-250">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-250"></span></span>|
|<span data-ttu-id="a8dfa-251">**Algoritmo de firma**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-251">**Signature Algorithm**</span></span>|
|<span data-ttu-id="a8dfa-252">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-252"></span></span>|
|<span data-ttu-id="a8dfa-253">**Validez no antes**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-253">**Validity Not Before**</span></span>|
|<span data-ttu-id="a8dfa-254">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-254"></span></span>|
|<span data-ttu-id="a8dfa-255">**Validez no después**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-255">**Validity Not After**</span></span>|
|<span data-ttu-id="a8dfa-256">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-256"></span></span>|
|<span data-ttu-id="a8dfa-257">**Identificador de clave de asunto**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-257">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="a8dfa-258">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-258"></span></span>|
|<span data-ttu-id="a8dfa-259">**Huella digital (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-259">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="a8dfa-260">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-260"></span></span>|
|<span data-ttu-id="a8dfa-261">**Huella digital (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-261">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="a8dfa-262">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-262"></span></span>|
|<span data-ttu-id="a8dfa-263">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-263">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="a8dfa-264">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-264"></span></span>|
|<span data-ttu-id="a8dfa-265">**Direcciones URL CRL**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-265">**CRL URLs**</span></span>|
|<span data-ttu-id="a8dfa-266">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-266"></span></span>|
   
 <span data-ttu-id="a8dfa-267">**Entidad de certificación raíz de confianza de D clase 3 2 EV de 2009**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-267">**D-TRUST Root Class 3 CA 2 EV 2009**</span></span>
  
||
|:-----|
|<span data-ttu-id="a8dfa-268">**Asunto**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-268">**Subject**</span></span>|
|<span data-ttu-id="a8dfa-269">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-269"></span></span>|
|<span data-ttu-id="a8dfa-270">**Número de serie**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-270">**Serial Number**</span></span>|
|<span data-ttu-id="a8dfa-271">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-271"></span></span>|
|<span data-ttu-id="a8dfa-272">**Longitud de clave pública**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-272">**Public Key Length**</span></span>|
|<span data-ttu-id="a8dfa-273">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-273"></span></span>|
|<span data-ttu-id="a8dfa-274">**Algoritmo de firma**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-274">**Signature Algorithm**</span></span>|
|<span data-ttu-id="a8dfa-275">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-275"></span></span>|
|<span data-ttu-id="a8dfa-276">**Validez no antes**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-276">**Validity Not Before**</span></span>|
|<span data-ttu-id="a8dfa-277">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-277"></span></span>|
|<span data-ttu-id="a8dfa-278">**Validez no después**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-278">**Validity Not After**</span></span>|
|<span data-ttu-id="a8dfa-279">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-279"></span></span>|
|<span data-ttu-id="a8dfa-280">**Identificador de clave de asunto**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-280">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="a8dfa-281">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-281"></span></span>|
|<span data-ttu-id="a8dfa-282">**Huella digital (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-282">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="a8dfa-283">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-283"></span></span>|
|<span data-ttu-id="a8dfa-284">**Huella digital (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-284">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="a8dfa-285">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-285"></span></span>|
|<span data-ttu-id="a8dfa-286">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-286">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="a8dfa-287">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-287"></span></span>|
|<span data-ttu-id="a8dfa-288">**Direcciones URL CRL**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-288">**CRL URLs**</span></span>|
|<span data-ttu-id="a8dfa-289">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-289"></span></span>|
   
 <span data-ttu-id="a8dfa-290">**X3 de la entidad de certificación de raíz de horario de verano**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-290">**DST Root CA X3**</span></span>
  
||
|:-----|
|<span data-ttu-id="a8dfa-291">**Asunto**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-291">**Subject**</span></span>|
|<span data-ttu-id="a8dfa-292">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-292"></span></span>|
|<span data-ttu-id="a8dfa-293">**Número de serie**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-293">**Serial Number**</span></span>|
|<span data-ttu-id="a8dfa-294">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-294"></span></span>|
|<span data-ttu-id="a8dfa-295">**Longitud de clave pública**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-295">**Public Key Length**</span></span>|
|<span data-ttu-id="a8dfa-296">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-296"></span></span>|
|<span data-ttu-id="a8dfa-297">**Algoritmo de firma**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-297">**Signature Algorithm**</span></span>|
|<span data-ttu-id="a8dfa-298">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-298"></span></span>|
|<span data-ttu-id="a8dfa-299">**Validez no antes**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-299">**Validity Not Before**</span></span>|
|<span data-ttu-id="a8dfa-300">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-300"></span></span>|
|<span data-ttu-id="a8dfa-301">**Validez no después**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-301">**Validity Not After**</span></span>|
|<span data-ttu-id="a8dfa-302">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-302"></span></span>|
|<span data-ttu-id="a8dfa-303">**Identificador de clave de asunto**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-303">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="a8dfa-304">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-304"></span></span>|
|<span data-ttu-id="a8dfa-305">**Huella digital (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-305">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="a8dfa-306">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-306"></span></span>|
|<span data-ttu-id="a8dfa-307">**Huella digital (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-307">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="a8dfa-308">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-308"></span></span>|
|<span data-ttu-id="a8dfa-309">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-309">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="a8dfa-310">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-310"></span></span>|
   
 <span data-ttu-id="a8dfa-311">**Entrust entidad de certificación raíz - G2**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-311">**Entrust Root Certification Authority - G2**</span></span>
  
||
|:-----|
|<span data-ttu-id="a8dfa-312">**Asunto**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-312">**Subject**</span></span>|
|<span data-ttu-id="a8dfa-313">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-313"></span></span>|
|<span data-ttu-id="a8dfa-314">**Número de serie**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-314">**Serial Number**</span></span>|
|<span data-ttu-id="a8dfa-315">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-315"></span></span>|
|<span data-ttu-id="a8dfa-316">**Longitud de clave pública**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-316">**Public Key Length**</span></span>|
|<span data-ttu-id="a8dfa-317">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-317"></span></span>|
|<span data-ttu-id="a8dfa-318">**Algoritmo de firma**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-318">**Signature Algorithm**</span></span>|
|<span data-ttu-id="a8dfa-319">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-319"></span></span>|
|<span data-ttu-id="a8dfa-320">**Validez no antes**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-320">**Validity Not Before**</span></span>|
|<span data-ttu-id="a8dfa-321">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-321"></span></span>|
|<span data-ttu-id="a8dfa-322">**Validez no después**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-322">**Validity Not After**</span></span>|
|<span data-ttu-id="a8dfa-323">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-323"></span></span>|
|<span data-ttu-id="a8dfa-324">**Identificador de clave de asunto**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-324">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="a8dfa-325">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-325"></span></span>|
|<span data-ttu-id="a8dfa-326">**Huella digital (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-326">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="a8dfa-327">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-327"></span></span>|
|<span data-ttu-id="a8dfa-328">**Huella digital (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-328">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="a8dfa-329">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-329"></span></span>|
|<span data-ttu-id="a8dfa-330">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-330">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="a8dfa-331">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-331"></span></span>|
   
 <span data-ttu-id="a8dfa-332">**Entrust.net Certification Authority (2048)**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-332">**Entrust.net Certification Authority (2048)**</span></span>
  
||
|:-----|
|<span data-ttu-id="a8dfa-333">**Asunto**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-333">**Subject**</span></span>|
|<span data-ttu-id="a8dfa-334">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-334"></span></span>|
|<span data-ttu-id="a8dfa-335">**Número de serie**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-335">**Serial Number**</span></span>|
|<span data-ttu-id="a8dfa-336">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-336"></span></span>|
|<span data-ttu-id="a8dfa-337">**Longitud de clave pública**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-337">**Public Key Length**</span></span>|
|<span data-ttu-id="a8dfa-338">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-338"></span></span>|
|<span data-ttu-id="a8dfa-339">**Algoritmo de firma**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-339">**Signature Algorithm**</span></span>|
|<span data-ttu-id="a8dfa-340">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-340"></span></span>|
|<span data-ttu-id="a8dfa-341">**Validez no antes**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-341">**Validity Not Before**</span></span>|
|<span data-ttu-id="a8dfa-342">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-342"></span></span>|
|<span data-ttu-id="a8dfa-343">**Validez no después**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-343">**Validity Not After**</span></span>|
|<span data-ttu-id="a8dfa-344">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-344"></span></span>|
|<span data-ttu-id="a8dfa-345">**Identificador de clave de asunto**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-345">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="a8dfa-346">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-346"></span></span>|
|<span data-ttu-id="a8dfa-347">**Huella digital (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-347">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="a8dfa-348">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-348"></span></span>|
|<span data-ttu-id="a8dfa-349">**Huella digital (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-349">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="a8dfa-350">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-350"></span></span>|
|<span data-ttu-id="a8dfa-351">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-351">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="a8dfa-352">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-352"></span></span>|
   
 <span data-ttu-id="a8dfa-353">**GlobalSign**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-353">**GlobalSign**</span></span>
  
||
|:-----|
|<span data-ttu-id="a8dfa-354">**Asunto**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-354">**Subject**</span></span>|
|<span data-ttu-id="a8dfa-355">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-355"></span></span>|
|<span data-ttu-id="a8dfa-356">**Número de serie**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-356">**Serial Number**</span></span>|
|<span data-ttu-id="a8dfa-357">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-357"></span></span>|
|<span data-ttu-id="a8dfa-358">**Longitud de clave pública**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-358">**Public Key Length**</span></span>|
|<span data-ttu-id="a8dfa-359">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-359"></span></span>|
|<span data-ttu-id="a8dfa-360">**Algoritmo de firma**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-360">**Signature Algorithm**</span></span>|
|<span data-ttu-id="a8dfa-361">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-361"></span></span>|
|<span data-ttu-id="a8dfa-362">**Validez no antes**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-362">**Validity Not Before**</span></span>|
|<span data-ttu-id="a8dfa-363">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-363"></span></span>|
|<span data-ttu-id="a8dfa-364">**Validez no después**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-364">**Validity Not After**</span></span>|
|<span data-ttu-id="a8dfa-365">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-365"></span></span>|
|<span data-ttu-id="a8dfa-366">**Identificador de clave de asunto**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-366">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="a8dfa-367">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-367"></span></span>|
|<span data-ttu-id="a8dfa-368">**Identificador de clave de entidad de certificación**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-368">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="a8dfa-369">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-369"></span></span>|
|<span data-ttu-id="a8dfa-370">**Huella digital (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-370">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="a8dfa-371">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-371"></span></span>|
|<span data-ttu-id="a8dfa-372">**Huella digital (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-372">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="a8dfa-373">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-373"></span></span>|
|<span data-ttu-id="a8dfa-374">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-374">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="a8dfa-375">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-375"></span></span>|
|<span data-ttu-id="a8dfa-376">**Direcciones URL CRL**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-376">**CRL URLs**</span></span>|
|<span data-ttu-id="a8dfa-377">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-377"></span></span>|
   
 <span data-ttu-id="a8dfa-378">**GlobalSign Root CA**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-378">**GlobalSign Root CA**</span></span>
  
||
|:-----|
|<span data-ttu-id="a8dfa-379">**Asunto**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-379">**Subject**</span></span>|
|<span data-ttu-id="a8dfa-380">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-380"></span></span>|
|<span data-ttu-id="a8dfa-381">**Número de serie**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-381">**Serial Number**</span></span>|
|<span data-ttu-id="a8dfa-382">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-382"></span></span>|
|<span data-ttu-id="a8dfa-383">**Longitud de clave pública**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-383">**Public Key Length**</span></span>|
|<span data-ttu-id="a8dfa-384">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-384"></span></span>|
|<span data-ttu-id="a8dfa-385">**Algoritmo de firma**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-385">**Signature Algorithm**</span></span>|
|<span data-ttu-id="a8dfa-386">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-386"></span></span>|
|<span data-ttu-id="a8dfa-387">**Validez no antes**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-387">**Validity Not Before**</span></span>|
|<span data-ttu-id="a8dfa-388">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-388"></span></span>|
|<span data-ttu-id="a8dfa-389">**Validez no después**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-389">**Validity Not After**</span></span>|
|<span data-ttu-id="a8dfa-390">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-390"></span></span>|
|<span data-ttu-id="a8dfa-391">**Identificador de clave de asunto**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-391">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="a8dfa-392">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-392"></span></span>|
|<span data-ttu-id="a8dfa-393">**Huella digital (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-393">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="a8dfa-394">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-394"></span></span>|
|<span data-ttu-id="a8dfa-395">**Huella digital (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-395">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="a8dfa-396">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-396"></span></span>|
|<span data-ttu-id="a8dfa-397">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-397">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="a8dfa-398">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-398"></span></span>|
   
 <span data-ttu-id="a8dfa-399">**Thawte entidad emisora de certificados raíz principal - G3**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-399">**thawte Primary Root CA - G3**</span></span>
  
||
|:-----|
|<span data-ttu-id="a8dfa-400">**Asunto**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-400">**Subject**</span></span>|
|<span data-ttu-id="a8dfa-401">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-401"></span></span>|
|<span data-ttu-id="a8dfa-402">**Número de serie**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-402">**Serial Number**</span></span>|
|<span data-ttu-id="a8dfa-403">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-403"></span></span>|
|<span data-ttu-id="a8dfa-404">**Longitud de clave pública**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-404">**Public Key Length**</span></span>|
|<span data-ttu-id="a8dfa-405">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-405"></span></span>|
|<span data-ttu-id="a8dfa-406">**Algoritmo de firma**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-406">**Signature Algorithm**</span></span>|
|<span data-ttu-id="a8dfa-407">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-407"></span></span>|
|<span data-ttu-id="a8dfa-408">**Validez no antes**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-408">**Validity Not Before**</span></span>|
|<span data-ttu-id="a8dfa-409">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-409"></span></span>|
|<span data-ttu-id="a8dfa-410">**Validez no después**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-410">**Validity Not After**</span></span>|
|<span data-ttu-id="a8dfa-411">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-411"></span></span>|
|<span data-ttu-id="a8dfa-412">**Identificador de clave de asunto**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-412">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="a8dfa-413">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-413"></span></span>|
|<span data-ttu-id="a8dfa-414">**Huella digital (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-414">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="a8dfa-415">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-415"></span></span>|
|<span data-ttu-id="a8dfa-416">**Huella digital (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-416">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="a8dfa-417">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-417"></span></span>|
|<span data-ttu-id="a8dfa-418">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-418">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="a8dfa-419">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-419"></span></span>|
   
 <span data-ttu-id="a8dfa-420">**Entidad de certificación principal pública de clase 3 de VeriSign - G5**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-420">**VeriSign Class 3 Public Primary Certification Authority - G5**</span></span>
  
||
|:-----|
|<span data-ttu-id="a8dfa-421">**Asunto**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-421">**Subject**</span></span>|
|<span data-ttu-id="a8dfa-422">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-422"></span></span>|
|<span data-ttu-id="a8dfa-423">**Número de serie**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-423">**Serial Number**</span></span>|
|<span data-ttu-id="a8dfa-424">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-424"></span></span>|
|<span data-ttu-id="a8dfa-425">**Longitud de clave pública**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-425">**Public Key Length**</span></span>|
|<span data-ttu-id="a8dfa-426">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-426"></span></span>|
|<span data-ttu-id="a8dfa-427">**Algoritmo de firma**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-427">**Signature Algorithm**</span></span>|
|<span data-ttu-id="a8dfa-428">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-428"></span></span>|
|<span data-ttu-id="a8dfa-429">**Validez no antes**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-429">**Validity Not Before**</span></span>|
|<span data-ttu-id="a8dfa-430">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-430"></span></span>|
|<span data-ttu-id="a8dfa-431">**Validez no después**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-431">**Validity Not After**</span></span>|
|<span data-ttu-id="a8dfa-432">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-432"></span></span>|
|<span data-ttu-id="a8dfa-433">**Identificador de clave de asunto**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-433">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="a8dfa-434">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-434"></span></span>|
|<span data-ttu-id="a8dfa-435">**Huella digital (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-435">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="a8dfa-436">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-436"></span></span>|
|<span data-ttu-id="a8dfa-437">**Huella digital (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-437">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="a8dfa-438">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-438"></span></span>|
|<span data-ttu-id="a8dfa-439">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-439">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="a8dfa-440">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-440"></span></span>|
   
## <a name="office-365-intermediate-certificate-details"></a><span data-ttu-id="a8dfa-441">Detalles del certificado intermedio de Office 365</span><span class="sxs-lookup"><span data-stu-id="a8dfa-441">Office 365 Intermediate Certificate Details</span></span>
<span data-ttu-id="a8dfa-442"><a name="IntermediateCerts"> </a></span><span class="sxs-lookup"><span data-stu-id="a8dfa-442"></span></span>

 <span data-ttu-id="a8dfa-443">**CNNIC SHA256 SSL**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-443">**CNNIC SHA256 SSL**</span></span>
  
||
|:-----|
|<span data-ttu-id="a8dfa-444">**Asunto**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-444">**Subject**</span></span>|
|<span data-ttu-id="a8dfa-445">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-445"></span></span>|
|<span data-ttu-id="a8dfa-446">**Emisor**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-446">**Issuer**</span></span>|
|<span data-ttu-id="a8dfa-447">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-447"></span></span>|
|<span data-ttu-id="a8dfa-448">**Número de serie**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-448">**Serial Number**</span></span>|
|<span data-ttu-id="a8dfa-449">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-449"></span></span>|
|<span data-ttu-id="a8dfa-450">**Longitud de clave pública**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-450">**Public Key Length**</span></span>|
|<span data-ttu-id="a8dfa-451">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-451"></span></span>|
|<span data-ttu-id="a8dfa-452">**Algoritmo de firma**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-452">**Signature Algorithm**</span></span>|
|<span data-ttu-id="a8dfa-453">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-453"></span></span>|
|<span data-ttu-id="a8dfa-454">**Validez no antes**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-454">**Validity Not Before**</span></span>|
|<span data-ttu-id="a8dfa-455">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-455"></span></span>|
|<span data-ttu-id="a8dfa-456">**Validez no después**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-456">**Validity Not After**</span></span>|
|<span data-ttu-id="a8dfa-457">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-457"></span></span>|
|<span data-ttu-id="a8dfa-458">**Identificador de clave de asunto**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-458">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="a8dfa-459">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-459"></span></span>|
|<span data-ttu-id="a8dfa-460">**Identificador de clave de entidad de certificación**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-460">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="a8dfa-461">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-461"></span></span>|
|<span data-ttu-id="a8dfa-462">**Huella digital (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-462">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="a8dfa-463">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-463"></span></span>|
|<span data-ttu-id="a8dfa-464">**Huella digital (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-464">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="a8dfa-465">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-465"></span></span>|
|<span data-ttu-id="a8dfa-466">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-466">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="a8dfa-467">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-467"></span></span>|
|<span data-ttu-id="a8dfa-468">**Direcciones URL AIA**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-468">**AIA URLs**</span></span>|
|<span data-ttu-id="a8dfa-469">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-469"></span></span>|
|<span data-ttu-id="a8dfa-470">**Direcciones URL CRL**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-470">**CRL URLs**</span></span>|
|<span data-ttu-id="a8dfa-471">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-471"></span></span>|
|<span data-ttu-id="a8dfa-472">**Direcciones URL OCSP**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-472">**OCSP URLs**</span></span>|
|<span data-ttu-id="a8dfa-473">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-473"></span></span>|
   
 <span data-ttu-id="a8dfa-474">**Entidad de certificación de confianza de D SSL clase 3 1 de 2009**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-474">**D-TRUST SSL Class 3 CA 1 2009**</span></span>
  
||
|:-----|
|<span data-ttu-id="a8dfa-475">**Asunto**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-475">**Subject**</span></span>|
|<span data-ttu-id="a8dfa-476">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-476"></span></span>|
|<span data-ttu-id="a8dfa-477">**Emisor**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-477">**Issuer**</span></span>|
|<span data-ttu-id="a8dfa-478">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-478"></span></span>|
|<span data-ttu-id="a8dfa-479">**Nombre alternativo del sujeto**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-479">**Subject Alternative Name**</span></span>|
|<span data-ttu-id="a8dfa-480">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-480"></span></span>|
|<span data-ttu-id="a8dfa-481">**Número de serie**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-481">**Serial Number**</span></span>|
|<span data-ttu-id="a8dfa-482">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-482"></span></span>|
|<span data-ttu-id="a8dfa-483">**Longitud de clave pública**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-483">**Public Key Length**</span></span>|
|<span data-ttu-id="a8dfa-484">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-484"></span></span>|
|<span data-ttu-id="a8dfa-485">**Algoritmo de firma**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-485">**Signature Algorithm**</span></span>|
|<span data-ttu-id="a8dfa-486">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-486"></span></span>|
|<span data-ttu-id="a8dfa-487">**Validez no antes**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-487">**Validity Not Before**</span></span>|
|<span data-ttu-id="a8dfa-488">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-488"></span></span>|
|<span data-ttu-id="a8dfa-489">**Validez no después**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-489">**Validity Not After**</span></span>|
|<span data-ttu-id="a8dfa-490">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-490"></span></span>|
|<span data-ttu-id="a8dfa-491">**Identificador de clave de asunto**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-491">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="a8dfa-492">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-492"></span></span>|
|<span data-ttu-id="a8dfa-493">**Identificador de clave de entidad de certificación**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-493">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="a8dfa-494">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-494"></span></span>|
|<span data-ttu-id="a8dfa-495">**Huella digital (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-495">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="a8dfa-496">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-496"></span></span>|
|<span data-ttu-id="a8dfa-497">**Huella digital (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-497">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="a8dfa-498">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-498"></span></span>|
|<span data-ttu-id="a8dfa-499">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-499">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="a8dfa-500">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-500"></span></span>|
|<span data-ttu-id="a8dfa-501">**Direcciones URL CRL**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-501">**CRL URLs**</span></span>|
|<span data-ttu-id="a8dfa-502">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-502"></span></span>|
|<span data-ttu-id="a8dfa-503">**Direcciones URL OCSP**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-503">**OCSP URLs**</span></span>|
|<span data-ttu-id="a8dfa-504">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-504"></span></span>|
   
 <span data-ttu-id="a8dfa-505">**Entidad de certificación de confianza de D SSL clase 3 1 EV 2009**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-505">**D-TRUST SSL Class 3 CA 1 EV 2009**</span></span>
  
||
|:-----|
|<span data-ttu-id="a8dfa-506">**Asunto**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-506">**Subject**</span></span>|
|<span data-ttu-id="a8dfa-507">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-507"></span></span>|
|<span data-ttu-id="a8dfa-508">**Emisor**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-508">**Issuer**</span></span>|
|<span data-ttu-id="a8dfa-509">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-509"></span></span>|
|<span data-ttu-id="a8dfa-510">**Nombre alternativo del sujeto**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-510">**Subject Alternative Name**</span></span>|
|<span data-ttu-id="a8dfa-511">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-511"></span></span>|
|<span data-ttu-id="a8dfa-512">**Número de serie**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-512">**Serial Number**</span></span>|
|<span data-ttu-id="a8dfa-513">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-513"></span></span>|
|<span data-ttu-id="a8dfa-514">**Longitud de clave pública**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-514">**Public Key Length**</span></span>|
|<span data-ttu-id="a8dfa-515">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-515"></span></span>|
|<span data-ttu-id="a8dfa-516">**Algoritmo de firma**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-516">**Signature Algorithm**</span></span>|
|<span data-ttu-id="a8dfa-517">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-517"></span></span>|
|<span data-ttu-id="a8dfa-518">**Validez no antes**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-518">**Validity Not Before**</span></span>|
|<span data-ttu-id="a8dfa-519">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-519"></span></span>|
|<span data-ttu-id="a8dfa-520">**Validez no después**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-520">**Validity Not After**</span></span>|
|<span data-ttu-id="a8dfa-521">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-521"></span></span>|
|<span data-ttu-id="a8dfa-522">**Identificador de clave de asunto**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-522">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="a8dfa-523">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-523"></span></span>|
|<span data-ttu-id="a8dfa-524">**Identificador de clave de entidad de certificación**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-524">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="a8dfa-525">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-525"></span></span>|
|<span data-ttu-id="a8dfa-526">**Huella digital (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-526">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="a8dfa-527">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-527"></span></span>|
|<span data-ttu-id="a8dfa-528">**Huella digital (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-528">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="a8dfa-529">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-529"></span></span>|
|<span data-ttu-id="a8dfa-530">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-530">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="a8dfa-531">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-531"></span></span>|
|<span data-ttu-id="a8dfa-532">**Direcciones URL CRL**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-532">**CRL URLs**</span></span>|
|<span data-ttu-id="a8dfa-533">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-533"></span></span>|
|<span data-ttu-id="a8dfa-534">**Direcciones URL OCSP**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-534">**OCSP URLs**</span></span>|
|<span data-ttu-id="a8dfa-535">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-535"></span></span>|
   
 <span data-ttu-id="a8dfa-536">**1 de la entidad emisora de certificados de servicios de nube de DigiCert**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-536">**DigiCert Cloud Services CA-1**</span></span>
  
||
|:-----|
|<span data-ttu-id="a8dfa-537">**Asunto**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-537">**Subject**</span></span>|
|<span data-ttu-id="a8dfa-538">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-538"></span></span>|
|<span data-ttu-id="a8dfa-539">**Emisor**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-539">**Issuer**</span></span>|
|<span data-ttu-id="a8dfa-540">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-540"></span></span>|
|<span data-ttu-id="a8dfa-541">**Número de serie**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-541">**Serial Number**</span></span>|
|<span data-ttu-id="a8dfa-542">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-542"></span></span>|
|<span data-ttu-id="a8dfa-543">**Longitud de clave pública**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-543">**Public Key Length**</span></span>|
|<span data-ttu-id="a8dfa-544">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-544"></span></span>|
|<span data-ttu-id="a8dfa-545">**Algoritmo de firma**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-545">**Signature Algorithm**</span></span>|
|<span data-ttu-id="a8dfa-546">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-546"></span></span>|
|<span data-ttu-id="a8dfa-547">**Validez no antes**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-547">**Validity Not Before**</span></span>|
|<span data-ttu-id="a8dfa-548">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-548"></span></span>|
|<span data-ttu-id="a8dfa-549">**Validez no después**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-549">**Validity Not After**</span></span>|
|<span data-ttu-id="a8dfa-550">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-550"></span></span>|
|<span data-ttu-id="a8dfa-551">**Identificador de clave de asunto**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-551">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="a8dfa-552">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-552"></span></span>|
|<span data-ttu-id="a8dfa-553">**Identificador de clave de entidad de certificación**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-553">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="a8dfa-554">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-554"></span></span>|
|<span data-ttu-id="a8dfa-555">**Huella digital (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-555">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="a8dfa-556">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-556"></span></span>|
|<span data-ttu-id="a8dfa-557">**Huella digital (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-557">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="a8dfa-558">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-558"></span></span>|
|<span data-ttu-id="a8dfa-559">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-559">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="a8dfa-560">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-560"></span></span>|
|<span data-ttu-id="a8dfa-561">**Direcciones URL CRL**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-561">**CRL URLs**</span></span>|
|<span data-ttu-id="a8dfa-562">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-562"></span></span>|
|<span data-ttu-id="a8dfa-563">**Direcciones URL OCSP**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-563">**OCSP URLs**</span></span>|
|<span data-ttu-id="a8dfa-564">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-564"></span></span>|
   
 <span data-ttu-id="a8dfa-565">**Servidor de seguridad alta DigiCert SHA2 entidad emisora de certificados**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-565">**DigiCert SHA2 High Assurance Server CA**</span></span>
  
||
|:-----|
|<span data-ttu-id="a8dfa-566">**Asunto**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-566">**Subject**</span></span>|
|<span data-ttu-id="a8dfa-567">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-567"></span></span>|
|<span data-ttu-id="a8dfa-568">**Emisor**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-568">**Issuer**</span></span>|
|<span data-ttu-id="a8dfa-569">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-569"></span></span>|
|<span data-ttu-id="a8dfa-570">**Número de serie**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-570">**Serial Number**</span></span>|
|<span data-ttu-id="a8dfa-571">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-571"></span></span>|
|<span data-ttu-id="a8dfa-572">**Longitud de clave pública**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-572">**Public Key Length**</span></span>|
|<span data-ttu-id="a8dfa-573">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-573"></span></span>|
|<span data-ttu-id="a8dfa-574">**Algoritmo de firma**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-574">**Signature Algorithm**</span></span>|
|<span data-ttu-id="a8dfa-575">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-575"></span></span>|
|<span data-ttu-id="a8dfa-576">**Validez no antes**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-576">**Validity Not Before**</span></span>|
|<span data-ttu-id="a8dfa-577">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-577"></span></span>|
|<span data-ttu-id="a8dfa-578">**Validez no después**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-578">**Validity Not After**</span></span>|
|<span data-ttu-id="a8dfa-579">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-579"></span></span>|
|<span data-ttu-id="a8dfa-580">**Identificador de clave de asunto**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-580">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="a8dfa-581">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-581"></span></span>|
|<span data-ttu-id="a8dfa-582">**Identificador de clave de entidad de certificación**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-582">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="a8dfa-583">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-583"></span></span>|
|<span data-ttu-id="a8dfa-584">**Huella digital (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-584">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="a8dfa-585">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-585"></span></span>|
|<span data-ttu-id="a8dfa-586">**Huella digital (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-586">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="a8dfa-587">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-587"></span></span>|
|<span data-ttu-id="a8dfa-588">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-588">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="a8dfa-589">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-589"></span></span>|
|<span data-ttu-id="a8dfa-590">**Direcciones URL CRL**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-590">**CRL URLs**</span></span>|
|<span data-ttu-id="a8dfa-591">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-591"></span></span>|
|<span data-ttu-id="a8dfa-592">**Direcciones URL OCSP**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-592">**OCSP URLs**</span></span>|
|<span data-ttu-id="a8dfa-593">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-593"></span></span>|
   
 <span data-ttu-id="a8dfa-594">**Servidor seguro DigiCert SHA2 entidad emisora de certificados**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-594">**DigiCert SHA2 Secure Server CA**</span></span>
  
||
|:-----|
|<span data-ttu-id="a8dfa-595">**Asunto**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-595">**Subject**</span></span>|
|<span data-ttu-id="a8dfa-596">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-596"></span></span>|
|<span data-ttu-id="a8dfa-597">**Emisor**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-597">**Issuer**</span></span>|
|<span data-ttu-id="a8dfa-598">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-598"></span></span>|
|<span data-ttu-id="a8dfa-599">**Número de serie**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-599">**Serial Number**</span></span>|
|<span data-ttu-id="a8dfa-600">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-600"></span></span>|
|<span data-ttu-id="a8dfa-601">**Longitud de clave pública**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-601">**Public Key Length**</span></span>|
|<span data-ttu-id="a8dfa-602">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-602"></span></span>|
|<span data-ttu-id="a8dfa-603">**Algoritmo de firma**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-603">**Signature Algorithm**</span></span>|
|<span data-ttu-id="a8dfa-604">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-604"></span></span>|
|<span data-ttu-id="a8dfa-605">**Validez no antes**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-605">**Validity Not Before**</span></span>|
|<span data-ttu-id="a8dfa-606">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-606"></span></span>|
|<span data-ttu-id="a8dfa-607">**Validez no después**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-607">**Validity Not After**</span></span>|
|<span data-ttu-id="a8dfa-608">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-608"></span></span>|
|<span data-ttu-id="a8dfa-609">**Identificador de clave de asunto**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-609">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="a8dfa-610">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-610"></span></span>|
|<span data-ttu-id="a8dfa-611">**Identificador de clave de entidad de certificación**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-611">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="a8dfa-612">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-612"></span></span>|
|<span data-ttu-id="a8dfa-613">**Huella digital (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-613">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="a8dfa-614">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-614"></span></span>|
|<span data-ttu-id="a8dfa-615">**Huella digital (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-615">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="a8dfa-616">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-616"></span></span>|
|<span data-ttu-id="a8dfa-617">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-617">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="a8dfa-618">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-618"></span></span>|
|<span data-ttu-id="a8dfa-619">**Direcciones URL CRL**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-619">**CRL URLs**</span></span>|
|<span data-ttu-id="a8dfa-620">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-620"></span></span>|
|<span data-ttu-id="a8dfa-621">**Direcciones URL OCSP**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-621">**OCSP URLs**</span></span>|
|<span data-ttu-id="a8dfa-622">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-622"></span></span>|
   
 <span data-ttu-id="a8dfa-623">**Entrust entidad de certificación - L1C**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-623">**Entrust Certification Authority - L1C**</span></span>
  
||
|:-----|
|<span data-ttu-id="a8dfa-624">**Asunto**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-624">**Subject**</span></span>|
|<span data-ttu-id="a8dfa-625">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-625"></span></span>|
|<span data-ttu-id="a8dfa-626">**Emisor**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-626">**Issuer**</span></span>|
|<span data-ttu-id="a8dfa-627">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-627"></span></span>|
|<span data-ttu-id="a8dfa-628">**Número de serie**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-628">**Serial Number**</span></span>|
|<span data-ttu-id="a8dfa-629">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-629"></span></span>|
|<span data-ttu-id="a8dfa-630">**Longitud de clave pública**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-630">**Public Key Length**</span></span>|
|<span data-ttu-id="a8dfa-631">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-631"></span></span>|
|<span data-ttu-id="a8dfa-632">**Algoritmo de firma**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-632">**Signature Algorithm**</span></span>|
|<span data-ttu-id="a8dfa-633">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-633"></span></span>|
|<span data-ttu-id="a8dfa-634">**Validez no antes**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-634">**Validity Not Before**</span></span>|
|<span data-ttu-id="a8dfa-635">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-635"></span></span>|
|<span data-ttu-id="a8dfa-636">**Validez no después**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-636">**Validity Not After**</span></span>|
|<span data-ttu-id="a8dfa-637">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-637"></span></span>|
|<span data-ttu-id="a8dfa-638">**Identificador de clave de asunto**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-638">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="a8dfa-639">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-639"></span></span>|
|<span data-ttu-id="a8dfa-640">**Identificador de clave de entidad de certificación**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-640">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="a8dfa-641">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-641"></span></span>|
|<span data-ttu-id="a8dfa-642">**Huella digital (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-642">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="a8dfa-643">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-643"></span></span>|
|<span data-ttu-id="a8dfa-644">**Huella digital (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-644">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="a8dfa-645">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-645"></span></span>|
|<span data-ttu-id="a8dfa-646">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-646">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="a8dfa-647">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-647"></span></span>|
|<span data-ttu-id="a8dfa-648">**Direcciones URL CRL**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-648">**CRL URLs**</span></span>|
|<span data-ttu-id="a8dfa-649">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-649"></span></span>|
|<span data-ttu-id="a8dfa-650">**Direcciones URL OCSP**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-650">**OCSP URLs**</span></span>|
|<span data-ttu-id="a8dfa-651">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-651"></span></span>|
   
 <span data-ttu-id="a8dfa-652">**Entrust entidad de certificación - L1K**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-652">**Entrust Certification Authority - L1K**</span></span>
  
||
|:-----|
|<span data-ttu-id="a8dfa-653">**Asunto**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-653">**Subject**</span></span>|
|<span data-ttu-id="a8dfa-654">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-654"></span></span>|
|<span data-ttu-id="a8dfa-655">**Emisor**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-655">**Issuer**</span></span>|
|<span data-ttu-id="a8dfa-656">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-656"></span></span>|
|<span data-ttu-id="a8dfa-657">**Número de serie**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-657">**Serial Number**</span></span>|
|<span data-ttu-id="a8dfa-658">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-658"></span></span>|
|<span data-ttu-id="a8dfa-659">**Longitud de clave pública**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-659">**Public Key Length**</span></span>|
|<span data-ttu-id="a8dfa-660">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-660"></span></span>|
|<span data-ttu-id="a8dfa-661">**Algoritmo de firma**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-661">**Signature Algorithm**</span></span>|
|<span data-ttu-id="a8dfa-662">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-662"></span></span>|
|<span data-ttu-id="a8dfa-663">**Validez no antes**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-663">**Validity Not Before**</span></span>|
|<span data-ttu-id="a8dfa-664">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-664"></span></span>|
|<span data-ttu-id="a8dfa-665">**Validez no después**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-665">**Validity Not After**</span></span>|
|<span data-ttu-id="a8dfa-666">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-666"></span></span>|
|<span data-ttu-id="a8dfa-667">**Identificador de clave de asunto**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-667">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="a8dfa-668">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-668"></span></span>|
|<span data-ttu-id="a8dfa-669">**Identificador de clave de entidad de certificación**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-669">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="a8dfa-670">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-670"></span></span>|
|<span data-ttu-id="a8dfa-671">**Huella digital (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-671">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="a8dfa-672">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-672"></span></span>|
|<span data-ttu-id="a8dfa-673">**Huella digital (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-673">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="a8dfa-674">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-674"></span></span>|
|<span data-ttu-id="a8dfa-675">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-675">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="a8dfa-676">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-676"></span></span>|
|<span data-ttu-id="a8dfa-677">**Direcciones URL CRL**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-677">**CRL URLs**</span></span>|
|<span data-ttu-id="a8dfa-678">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-678"></span></span>|
|<span data-ttu-id="a8dfa-679">**Direcciones URL OCSP**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-679">**OCSP URLs**</span></span>|
|<span data-ttu-id="a8dfa-680">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-680"></span></span>|
   
 <span data-ttu-id="a8dfa-681">**GlobalSign**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-681">**GlobalSign**</span></span>
  
||
|:-----|
|<span data-ttu-id="a8dfa-682">**Asunto**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-682">**Subject**</span></span>|
|<span data-ttu-id="a8dfa-683">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-683"></span></span>|
|<span data-ttu-id="a8dfa-684">**Emisor**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-684">**Issuer**</span></span>|
|<span data-ttu-id="a8dfa-685">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-685"></span></span>|
|<span data-ttu-id="a8dfa-686">**Número de serie**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-686">**Serial Number**</span></span>|
|<span data-ttu-id="a8dfa-687">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-687"></span></span>|
|<span data-ttu-id="a8dfa-688">**Longitud de clave pública**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-688">**Public Key Length**</span></span>|
|<span data-ttu-id="a8dfa-689">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-689"></span></span>|
|<span data-ttu-id="a8dfa-690">**Algoritmo de firma**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-690">**Signature Algorithm**</span></span>|
|<span data-ttu-id="a8dfa-691">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-691"></span></span>|
|<span data-ttu-id="a8dfa-692">**Validez no antes**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-692">**Validity Not Before**</span></span>|
|<span data-ttu-id="a8dfa-693">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-693"></span></span>|
|<span data-ttu-id="a8dfa-694">**Validez no después**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-694">**Validity Not After**</span></span>|
|<span data-ttu-id="a8dfa-695">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-695"></span></span>|
|<span data-ttu-id="a8dfa-696">**Identificador de clave de asunto**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-696">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="a8dfa-697">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-697"></span></span>|
|<span data-ttu-id="a8dfa-698">**Identificador de clave de entidad de certificación**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-698">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="a8dfa-699">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-699"></span></span>|
|<span data-ttu-id="a8dfa-700">**Huella digital (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-700">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="a8dfa-701">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-701"></span></span>|
|<span data-ttu-id="a8dfa-702">**Huella digital (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-702">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="a8dfa-703">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-703"></span></span>|
|<span data-ttu-id="a8dfa-704">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-704">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="a8dfa-705">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-705"></span></span>|
|<span data-ttu-id="a8dfa-706">**Direcciones URL CRL**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-706">**CRL URLs**</span></span>|
|<span data-ttu-id="a8dfa-707">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-707"></span></span>|
|<span data-ttu-id="a8dfa-708">**Direcciones URL OCSP**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-708">**OCSP URLs**</span></span>|
|<span data-ttu-id="a8dfa-709">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-709"></span></span>|
   
 <span data-ttu-id="a8dfa-710">**GlobalSign extendida Validation CA - SHA256 - G2**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-710">**GlobalSign Extended Validation CA - SHA256 - G2**</span></span>
  
||
|:-----|
|<span data-ttu-id="a8dfa-711">**Asunto**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-711">**Subject**</span></span>|
|<span data-ttu-id="a8dfa-712">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-712"></span></span>|
|<span data-ttu-id="a8dfa-713">**Emisor**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-713">**Issuer**</span></span>|
|<span data-ttu-id="a8dfa-714">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-714"></span></span>|
|<span data-ttu-id="a8dfa-715">**Número de serie**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-715">**Serial Number**</span></span>|
|<span data-ttu-id="a8dfa-716">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-716"></span></span>|
|<span data-ttu-id="a8dfa-717">**Longitud de clave pública**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-717">**Public Key Length**</span></span>|
|<span data-ttu-id="a8dfa-718">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-718"></span></span>|
|<span data-ttu-id="a8dfa-719">**Algoritmo de firma**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-719">**Signature Algorithm**</span></span>|
|<span data-ttu-id="a8dfa-720">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-720"></span></span>|
|<span data-ttu-id="a8dfa-721">**Validez no antes**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-721">**Validity Not Before**</span></span>|
|<span data-ttu-id="a8dfa-722">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-722"></span></span>|
|<span data-ttu-id="a8dfa-723">**Validez no después**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-723">**Validity Not After**</span></span>|
|<span data-ttu-id="a8dfa-724">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-724"></span></span>|
|<span data-ttu-id="a8dfa-725">**Identificador de clave de asunto**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-725">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="a8dfa-726">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-726"></span></span>|
|<span data-ttu-id="a8dfa-727">**Identificador de clave de entidad de certificación**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-727">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="a8dfa-728">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-728"></span></span>|
|<span data-ttu-id="a8dfa-729">**Huella digital (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-729">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="a8dfa-730">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-730"></span></span>|
|<span data-ttu-id="a8dfa-731">**Huella digital (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-731">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="a8dfa-732">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-732"></span></span>|
|<span data-ttu-id="a8dfa-733">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-733">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="a8dfa-734">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-734"></span></span>|
|<span data-ttu-id="a8dfa-735">**Direcciones URL CRL**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-735">**CRL URLs**</span></span>|
|<span data-ttu-id="a8dfa-736">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-736"></span></span>|
|<span data-ttu-id="a8dfa-737">**Direcciones URL OCSP**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-737">**OCSP URLs**</span></span>|
|<span data-ttu-id="a8dfa-738">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-738"></span></span>|
   
 <span data-ttu-id="a8dfa-739">**GlobalSign extendida Validation CA - SHA256 - G3**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-739">**GlobalSign Extended Validation CA - SHA256 - G3**</span></span>
  
||
|:-----|
|<span data-ttu-id="a8dfa-740">**Asunto**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-740">**Subject**</span></span>|
|<span data-ttu-id="a8dfa-741">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-741"></span></span>|
|<span data-ttu-id="a8dfa-742">**Emisor**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-742">**Issuer**</span></span>|
|<span data-ttu-id="a8dfa-743">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-743"></span></span>|
|<span data-ttu-id="a8dfa-744">**Número de serie**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-744">**Serial Number**</span></span>|
|<span data-ttu-id="a8dfa-745">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-745"></span></span>|
|<span data-ttu-id="a8dfa-746">**Longitud de clave pública**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-746">**Public Key Length**</span></span>|
|<span data-ttu-id="a8dfa-747">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-747"></span></span>|
|<span data-ttu-id="a8dfa-748">**Algoritmo de firma**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-748">**Signature Algorithm**</span></span>|
|<span data-ttu-id="a8dfa-749">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-749"></span></span>|
|<span data-ttu-id="a8dfa-750">**Validez no antes**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-750">**Validity Not Before**</span></span>|
|<span data-ttu-id="a8dfa-751">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-751"></span></span>|
|<span data-ttu-id="a8dfa-752">**Validez no después**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-752">**Validity Not After**</span></span>|
|<span data-ttu-id="a8dfa-753">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-753"></span></span>|
|<span data-ttu-id="a8dfa-754">**Identificador de clave de asunto**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-754">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="a8dfa-755">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-755"></span></span>|
|<span data-ttu-id="a8dfa-756">**Identificador de clave de entidad de certificación**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-756">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="a8dfa-757">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-757"></span></span>|
|<span data-ttu-id="a8dfa-758">**Huella digital (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-758">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="a8dfa-759">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-759"></span></span>|
|<span data-ttu-id="a8dfa-760">**Huella digital (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-760">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="a8dfa-761">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-761"></span></span>|
|<span data-ttu-id="a8dfa-762">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-762">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="a8dfa-763">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-763"></span></span>|
|<span data-ttu-id="a8dfa-764">**Direcciones URL CRL**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-764">**CRL URLs**</span></span>|
|<span data-ttu-id="a8dfa-765">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-765"></span></span>|
|<span data-ttu-id="a8dfa-766">**Direcciones URL OCSP**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-766">**OCSP URLs**</span></span>|
|<span data-ttu-id="a8dfa-767">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-767"></span></span>|
   
 <span data-ttu-id="a8dfa-768">**GlobalSign organización validación CA - SHA256 - G2**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-768">**GlobalSign Organization Validation CA - SHA256 - G2**</span></span>
  
||
|:-----|
|<span data-ttu-id="a8dfa-769">**Asunto**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-769">**Subject**</span></span>|
|<span data-ttu-id="a8dfa-770">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-770"></span></span>|
|<span data-ttu-id="a8dfa-771">**Emisor**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-771">**Issuer**</span></span>|
|<span data-ttu-id="a8dfa-772">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-772"></span></span>|
|<span data-ttu-id="a8dfa-773">**Número de serie**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-773">**Serial Number**</span></span>|
|<span data-ttu-id="a8dfa-774">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-774"></span></span>|
|<span data-ttu-id="a8dfa-775">**Longitud de clave pública**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-775">**Public Key Length**</span></span>|
|<span data-ttu-id="a8dfa-776">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-776"></span></span>|
|<span data-ttu-id="a8dfa-777">**Algoritmo de firma**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-777">**Signature Algorithm**</span></span>|
|<span data-ttu-id="a8dfa-778">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-778"></span></span>|
|<span data-ttu-id="a8dfa-779">**Validez no antes**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-779">**Validity Not Before**</span></span>|
|<span data-ttu-id="a8dfa-780">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-780"></span></span>|
|<span data-ttu-id="a8dfa-781">**Validez no después**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-781">**Validity Not After**</span></span>|
|<span data-ttu-id="a8dfa-782">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-782"></span></span>|
|<span data-ttu-id="a8dfa-783">**Identificador de clave de asunto**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-783">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="a8dfa-784">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-784"></span></span>|
|<span data-ttu-id="a8dfa-785">**Identificador de clave de entidad de certificación**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-785">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="a8dfa-786">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-786"></span></span>|
|<span data-ttu-id="a8dfa-787">**Huella digital (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-787">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="a8dfa-788">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-788"></span></span>|
|<span data-ttu-id="a8dfa-789">**Huella digital (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-789">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="a8dfa-790">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-790"></span></span>|
|<span data-ttu-id="a8dfa-791">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-791">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="a8dfa-792">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-792"></span></span>|
|<span data-ttu-id="a8dfa-793">**Direcciones URL CRL**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-793">**CRL URLs**</span></span>|
|<span data-ttu-id="a8dfa-794">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-794"></span></span>|
|<span data-ttu-id="a8dfa-795">**Direcciones URL OCSP**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-795">**OCSP URLs**</span></span>|
|<span data-ttu-id="a8dfa-796">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-796"></span></span>|
   
 <span data-ttu-id="a8dfa-797">**GlobalSign organización validación CA - SHA256 - G2**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-797">**GlobalSign Organization Validation CA - SHA256 - G2**</span></span>
  
||
|:-----|
|<span data-ttu-id="a8dfa-798">**Asunto**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-798">**Subject**</span></span>|
|<span data-ttu-id="a8dfa-799">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-799"></span></span>|
|<span data-ttu-id="a8dfa-800">**Emisor**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-800">**Issuer**</span></span>|
|<span data-ttu-id="a8dfa-801">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-801"></span></span>|
|<span data-ttu-id="a8dfa-802">**Número de serie**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-802">**Serial Number**</span></span>|
|<span data-ttu-id="a8dfa-803">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-803"></span></span>|
|<span data-ttu-id="a8dfa-804">**Longitud de clave pública**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-804">**Public Key Length**</span></span>|
|<span data-ttu-id="a8dfa-805">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-805"></span></span>|
|<span data-ttu-id="a8dfa-806">**Algoritmo de firma**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-806">**Signature Algorithm**</span></span>|
|<span data-ttu-id="a8dfa-807">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-807"></span></span>|
|<span data-ttu-id="a8dfa-808">**Validez no antes**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-808">**Validity Not Before**</span></span>|
|<span data-ttu-id="a8dfa-809">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-809"></span></span>|
|<span data-ttu-id="a8dfa-810">**Validez no después**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-810">**Validity Not After**</span></span>|
|<span data-ttu-id="a8dfa-811">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-811"></span></span>|
|<span data-ttu-id="a8dfa-812">**Identificador de clave de asunto**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-812">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="a8dfa-813">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-813"></span></span>|
|<span data-ttu-id="a8dfa-814">**Identificador de clave de entidad de certificación**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-814">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="a8dfa-815">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-815"></span></span>|
|<span data-ttu-id="a8dfa-816">**Huella digital (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-816">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="a8dfa-817">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-817"></span></span>|
|<span data-ttu-id="a8dfa-818">**Huella digital (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-818">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="a8dfa-819">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-819"></span></span>|
|<span data-ttu-id="a8dfa-820">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-820">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="a8dfa-821">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-821"></span></span>|
|<span data-ttu-id="a8dfa-822">**Direcciones URL CRL**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-822">**CRL URLs**</span></span>|
|<span data-ttu-id="a8dfa-823">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-823"></span></span>|
|<span data-ttu-id="a8dfa-824">**Direcciones URL OCSP**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-824">**OCSP URLs**</span></span>|
|<span data-ttu-id="a8dfa-825">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-825"></span></span>|
   
 <span data-ttu-id="a8dfa-826">**Vamos a cifrar autoridad X3**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-826">**Let's Encrypt Authority X3**</span></span>
  
||
|:-----|
|<span data-ttu-id="a8dfa-827">**Asunto**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-827">**Subject**</span></span>|
|<span data-ttu-id="a8dfa-828">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-828"></span></span>|
|<span data-ttu-id="a8dfa-829">**Emisor**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-829">**Issuer**</span></span>|
|<span data-ttu-id="a8dfa-830">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-830"></span></span>|
|<span data-ttu-id="a8dfa-831">**Número de serie**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-831">**Serial Number**</span></span>|
|<span data-ttu-id="a8dfa-832">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-832"></span></span>|
|<span data-ttu-id="a8dfa-833">**Longitud de clave pública**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-833">**Public Key Length**</span></span>|
|<span data-ttu-id="a8dfa-834">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-834"></span></span>|
|<span data-ttu-id="a8dfa-835">**Algoritmo de firma**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-835">**Signature Algorithm**</span></span>|
|<span data-ttu-id="a8dfa-836">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-836"></span></span>|
|<span data-ttu-id="a8dfa-837">**Validez no antes**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-837">**Validity Not Before**</span></span>|
|<span data-ttu-id="a8dfa-838">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-838"></span></span>|
|<span data-ttu-id="a8dfa-839">**Validez no después**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-839">**Validity Not After**</span></span>|
|<span data-ttu-id="a8dfa-840">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-840"></span></span>|
|<span data-ttu-id="a8dfa-841">**Identificador de clave de asunto**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-841">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="a8dfa-842">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-842"></span></span>|
|<span data-ttu-id="a8dfa-843">**Identificador de clave de entidad de certificación**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-843">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="a8dfa-844">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-844"></span></span>|
|<span data-ttu-id="a8dfa-845">**Huella digital (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-845">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="a8dfa-846">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-846"></span></span>|
|<span data-ttu-id="a8dfa-847">**Huella digital (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-847">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="a8dfa-848">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-848"></span></span>|
|<span data-ttu-id="a8dfa-849">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-849">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="a8dfa-850">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-850"></span></span>|
|<span data-ttu-id="a8dfa-851">**Direcciones URL AIA**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-851">**AIA URLs**</span></span>|
|<span data-ttu-id="a8dfa-852">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-852"></span></span>|
|<span data-ttu-id="a8dfa-853">**Direcciones URL CRL**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-853">**CRL URLs**</span></span>|
|<span data-ttu-id="a8dfa-854">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-854"></span></span>|
|<span data-ttu-id="a8dfa-855">**Direcciones URL OCSP**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-855">**OCSP URLs**</span></span>|
|<span data-ttu-id="a8dfa-856">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-856"></span></span>|
   
 <span data-ttu-id="a8dfa-857">**Microsoft IT SSL SHA2**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-857">**Microsoft IT SSL SHA2**</span></span>
  
||
|:-----|
|<span data-ttu-id="a8dfa-858">**Asunto**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-858">**Subject**</span></span>|
|<span data-ttu-id="a8dfa-859">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-859"></span></span>|
|<span data-ttu-id="a8dfa-860">**Emisor**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-860">**Issuer**</span></span>|
|<span data-ttu-id="a8dfa-861">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-861"></span></span>|
|<span data-ttu-id="a8dfa-862">**Número de serie**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-862">**Serial Number**</span></span>|
|<span data-ttu-id="a8dfa-863">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-863"></span></span>|
|<span data-ttu-id="a8dfa-864">**Longitud de clave pública**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-864">**Public Key Length**</span></span>|
|<span data-ttu-id="a8dfa-865">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-865"></span></span>|
|<span data-ttu-id="a8dfa-866">**Algoritmo de firma**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-866">**Signature Algorithm**</span></span>|
|<span data-ttu-id="a8dfa-867">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-867"></span></span>|
|<span data-ttu-id="a8dfa-868">**Validez no antes**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-868">**Validity Not Before**</span></span>|
|<span data-ttu-id="a8dfa-869">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-869"></span></span>|
|<span data-ttu-id="a8dfa-870">**Validez no después**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-870">**Validity Not After**</span></span>|
|<span data-ttu-id="a8dfa-871">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-871"></span></span>|
|<span data-ttu-id="a8dfa-872">**Identificador de clave de asunto**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-872">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="a8dfa-873">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-873"></span></span>|
|<span data-ttu-id="a8dfa-874">**Identificador de clave de entidad de certificación**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-874">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="a8dfa-875">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-875"></span></span>|
|<span data-ttu-id="a8dfa-876">**Huella digital (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-876">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="a8dfa-877">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-877"></span></span>|
|<span data-ttu-id="a8dfa-878">**Huella digital (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-878">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="a8dfa-879">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-879"></span></span>|
|<span data-ttu-id="a8dfa-880">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-880">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="a8dfa-881">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-881"></span></span>|
|<span data-ttu-id="a8dfa-882">**Direcciones URL CRL**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-882">**CRL URLs**</span></span>|
|<span data-ttu-id="a8dfa-883">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-883"></span></span>|
   
 <span data-ttu-id="a8dfa-884">**Microsoft IT SSL SHA2**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-884">**Microsoft IT SSL SHA2**</span></span>
  
||
|:-----|
|<span data-ttu-id="a8dfa-885">**Asunto**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-885">**Subject**</span></span>|
|<span data-ttu-id="a8dfa-886">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-886"></span></span>|
|<span data-ttu-id="a8dfa-887">**Emisor**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-887">**Issuer**</span></span>|
|<span data-ttu-id="a8dfa-888">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-888"></span></span>|
|<span data-ttu-id="a8dfa-889">**Número de serie**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-889">**Serial Number**</span></span>|
|<span data-ttu-id="a8dfa-890">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-890"></span></span>|
|<span data-ttu-id="a8dfa-891">**Longitud de clave pública**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-891">**Public Key Length**</span></span>|
|<span data-ttu-id="a8dfa-892">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-892"></span></span>|
|<span data-ttu-id="a8dfa-893">**Algoritmo de firma**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-893">**Signature Algorithm**</span></span>|
|<span data-ttu-id="a8dfa-894">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-894"></span></span>|
|<span data-ttu-id="a8dfa-895">**Validez no antes**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-895">**Validity Not Before**</span></span>|
|<span data-ttu-id="a8dfa-896">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-896"></span></span>|
|<span data-ttu-id="a8dfa-897">**Validez no después**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-897">**Validity Not After**</span></span>|
|<span data-ttu-id="a8dfa-898">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-898"></span></span>|
|<span data-ttu-id="a8dfa-899">**Identificador de clave de asunto**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-899">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="a8dfa-900">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-900"></span></span>|
|<span data-ttu-id="a8dfa-901">**Identificador de clave de entidad de certificación**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-901">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="a8dfa-902">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-902"></span></span>|
|<span data-ttu-id="a8dfa-903">**Huella digital (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-903">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="a8dfa-904">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-904"></span></span>|
|<span data-ttu-id="a8dfa-905">**Huella digital (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-905">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="a8dfa-906">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-906"></span></span>|
|<span data-ttu-id="a8dfa-907">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-907">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="a8dfa-908">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-908"></span></span>|
|<span data-ttu-id="a8dfa-909">**Direcciones URL CRL**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-909">**CRL URLs**</span></span>|
|<span data-ttu-id="a8dfa-910">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-910"></span></span>|
|<span data-ttu-id="a8dfa-911">**Direcciones URL OCSP**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-911">**OCSP URLs**</span></span>|
|<span data-ttu-id="a8dfa-912">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-912"></span></span>|
   
 <span data-ttu-id="a8dfa-913">**Entidad de certificación de Microsoft IT TLS 1**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-913">**Microsoft IT TLS CA 1**</span></span>
  
||
|:-----|
|<span data-ttu-id="a8dfa-914">**Asunto**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-914">**Subject**</span></span>|
|<span data-ttu-id="a8dfa-915">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-915"></span></span>|
|<span data-ttu-id="a8dfa-916">**Emisor**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-916">**Issuer**</span></span>|
|<span data-ttu-id="a8dfa-917">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-917"></span></span>|
|<span data-ttu-id="a8dfa-918">**Número de serie**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-918">**Serial Number**</span></span>|
|<span data-ttu-id="a8dfa-919">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-919"></span></span>|
|<span data-ttu-id="a8dfa-920">**Longitud de clave pública**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-920">**Public Key Length**</span></span>|
|<span data-ttu-id="a8dfa-921">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-921"></span></span>|
|<span data-ttu-id="a8dfa-922">**Algoritmo de firma**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-922">**Signature Algorithm**</span></span>|
|<span data-ttu-id="a8dfa-923">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-923"></span></span>|
|<span data-ttu-id="a8dfa-924">**Validez no antes**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-924">**Validity Not Before**</span></span>|
|<span data-ttu-id="a8dfa-925">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-925"></span></span>|
|<span data-ttu-id="a8dfa-926">**Validez no después**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-926">**Validity Not After**</span></span>|
|<span data-ttu-id="a8dfa-927">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-927"></span></span>|
|<span data-ttu-id="a8dfa-928">**Identificador de clave de asunto**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-928">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="a8dfa-929">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-929"></span></span>|
|<span data-ttu-id="a8dfa-930">**Identificador de clave de entidad de certificación**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-930">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="a8dfa-931">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-931"></span></span>|
|<span data-ttu-id="a8dfa-932">**Huella digital (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-932">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="a8dfa-933">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-933"></span></span>|
|<span data-ttu-id="a8dfa-934">**Huella digital (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-934">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="a8dfa-935">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-935"></span></span>|
|<span data-ttu-id="a8dfa-936">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-936">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="a8dfa-937">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-937"></span></span>|
|<span data-ttu-id="a8dfa-938">**Direcciones URL CRL**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-938">**CRL URLs**</span></span>|
|<span data-ttu-id="a8dfa-939">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-939"></span></span>|
|<span data-ttu-id="a8dfa-940">**Direcciones URL OCSP**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-940">**OCSP URLs**</span></span>|
|<span data-ttu-id="a8dfa-941">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-941"></span></span>|
   
 <span data-ttu-id="a8dfa-942">**Entidad de certificación de Microsoft IT TLS 2**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-942">**Microsoft IT TLS CA 2**</span></span>
  
||
|:-----|
|<span data-ttu-id="a8dfa-943">**Asunto**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-943">**Subject**</span></span>|
|<span data-ttu-id="a8dfa-944">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-944"></span></span>|
|<span data-ttu-id="a8dfa-945">**Emisor**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-945">**Issuer**</span></span>|
|<span data-ttu-id="a8dfa-946">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-946"></span></span>|
|<span data-ttu-id="a8dfa-947">**Número de serie**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-947">**Serial Number**</span></span>|
|<span data-ttu-id="a8dfa-948">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-948"></span></span>|
|<span data-ttu-id="a8dfa-949">**Longitud de clave pública**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-949">**Public Key Length**</span></span>|
|<span data-ttu-id="a8dfa-950">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-950"></span></span>|
|<span data-ttu-id="a8dfa-951">**Algoritmo de firma**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-951">**Signature Algorithm**</span></span>|
|<span data-ttu-id="a8dfa-952">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-952"></span></span>|
|<span data-ttu-id="a8dfa-953">**Validez no antes**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-953">**Validity Not Before**</span></span>|
|<span data-ttu-id="a8dfa-954">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-954"></span></span>|
|<span data-ttu-id="a8dfa-955">**Validez no después**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-955">**Validity Not After**</span></span>|
|<span data-ttu-id="a8dfa-956">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-956"></span></span>|
|<span data-ttu-id="a8dfa-957">**Identificador de clave de asunto**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-957">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="a8dfa-958">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-958"></span></span>|
|<span data-ttu-id="a8dfa-959">**Identificador de clave de entidad de certificación**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-959">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="a8dfa-960">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-960"></span></span>|
|<span data-ttu-id="a8dfa-961">**Huella digital (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-961">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="a8dfa-962">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-962"></span></span>|
|<span data-ttu-id="a8dfa-963">**Huella digital (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-963">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="a8dfa-964">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-964"></span></span>|
|<span data-ttu-id="a8dfa-965">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-965">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="a8dfa-966">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-966"></span></span>|
|<span data-ttu-id="a8dfa-967">**Direcciones URL CRL**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-967">**CRL URLs**</span></span>|
|<span data-ttu-id="a8dfa-968">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-968"></span></span>|
|<span data-ttu-id="a8dfa-969">**Direcciones URL OCSP**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-969">**OCSP URLs**</span></span>|
|<span data-ttu-id="a8dfa-970">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-970"></span></span>|
   
 <span data-ttu-id="a8dfa-971">**Entidad de certificación de Microsoft IT TLS 4**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-971">**Microsoft IT TLS CA 4**</span></span>
  
||
|:-----|
|<span data-ttu-id="a8dfa-972">**Asunto**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-972">**Subject**</span></span>|
|<span data-ttu-id="a8dfa-973">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-973"></span></span>|
|<span data-ttu-id="a8dfa-974">**Emisor**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-974">**Issuer**</span></span>|
|<span data-ttu-id="a8dfa-975">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-975"></span></span>|
|<span data-ttu-id="a8dfa-976">**Número de serie**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-976">**Serial Number**</span></span>|
|<span data-ttu-id="a8dfa-977">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-977"></span></span>|
|<span data-ttu-id="a8dfa-978">**Longitud de clave pública**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-978">**Public Key Length**</span></span>|
|<span data-ttu-id="a8dfa-979">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-979"></span></span>|
|<span data-ttu-id="a8dfa-980">**Algoritmo de firma**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-980">**Signature Algorithm**</span></span>|
|<span data-ttu-id="a8dfa-981">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-981"></span></span>|
|<span data-ttu-id="a8dfa-982">**Validez no antes**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-982">**Validity Not Before**</span></span>|
|<span data-ttu-id="a8dfa-983">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-983"></span></span>|
|<span data-ttu-id="a8dfa-984">**Validez no después**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-984">**Validity Not After**</span></span>|
|<span data-ttu-id="a8dfa-985">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-985"></span></span>|
|<span data-ttu-id="a8dfa-986">**Identificador de clave de asunto**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-986">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="a8dfa-987">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-987"></span></span>|
|<span data-ttu-id="a8dfa-988">**Identificador de clave de entidad de certificación**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-988">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="a8dfa-989">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-989"></span></span>|
|<span data-ttu-id="a8dfa-990">**Huella digital (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-990">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="a8dfa-991">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-991"></span></span>|
|<span data-ttu-id="a8dfa-992">**Huella digital (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-992">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="a8dfa-993">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-993"></span></span>|
|<span data-ttu-id="a8dfa-994">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-994">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="a8dfa-995">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-995"></span></span>|
|<span data-ttu-id="a8dfa-996">**Direcciones URL CRL**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-996">**CRL URLs**</span></span>|
|<span data-ttu-id="a8dfa-997">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-997"></span></span>|
|<span data-ttu-id="a8dfa-998">**Direcciones URL OCSP**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-998">**OCSP URLs**</span></span>|
|<span data-ttu-id="a8dfa-999">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-999"></span></span>|
   
 <span data-ttu-id="a8dfa-1000">**Entidad de certificación de Microsoft IT TLS 5**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-1000">**Microsoft IT TLS CA 5**</span></span>
  
||
|:-----|
|<span data-ttu-id="a8dfa-1001">**Asunto**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-1001">**Subject**</span></span>|
|<span data-ttu-id="a8dfa-1002">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-1002"></span></span>|
|<span data-ttu-id="a8dfa-1003">**Emisor**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-1003">**Issuer**</span></span>|
|<span data-ttu-id="a8dfa-1004">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-1004"></span></span>|
|<span data-ttu-id="a8dfa-1005">**Número de serie**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-1005">**Serial Number**</span></span>|
|<span data-ttu-id="a8dfa-1006">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-1006"></span></span>|
|<span data-ttu-id="a8dfa-1007">**Longitud de clave pública**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-1007">**Public Key Length**</span></span>|
|<span data-ttu-id="a8dfa-1008">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-1008"></span></span>|
|<span data-ttu-id="a8dfa-1009">**Algoritmo de firma**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-1009">**Signature Algorithm**</span></span>|
|<span data-ttu-id="a8dfa-1010">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-1010"></span></span>|
|<span data-ttu-id="a8dfa-1011">**Validez no antes**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-1011">**Validity Not Before**</span></span>|
|<span data-ttu-id="a8dfa-1012">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-1012"></span></span>|
|<span data-ttu-id="a8dfa-1013">**Validez no después**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-1013">**Validity Not After**</span></span>|
|<span data-ttu-id="a8dfa-1014">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-1014"></span></span>|
|<span data-ttu-id="a8dfa-1015">**Identificador de clave de asunto**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-1015">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="a8dfa-1016">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-1016"></span></span>|
|<span data-ttu-id="a8dfa-1017">**Identificador de clave de entidad de certificación**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-1017">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="a8dfa-1018">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-1018"></span></span>|
|<span data-ttu-id="a8dfa-1019">**Huella digital (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-1019">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="a8dfa-1020">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-1020"></span></span>|
|<span data-ttu-id="a8dfa-1021">**Huella digital (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-1021">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="a8dfa-1022">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-1022"></span></span>|
|<span data-ttu-id="a8dfa-1023">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-1023">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="a8dfa-1024">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-1024"></span></span>|
|<span data-ttu-id="a8dfa-1025">**Direcciones URL CRL**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-1025">**CRL URLs**</span></span>|
|<span data-ttu-id="a8dfa-1026">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-1026"></span></span>|
|<span data-ttu-id="a8dfa-1027">**Direcciones URL OCSP**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-1027">**OCSP URLs**</span></span>|
|<span data-ttu-id="a8dfa-1028">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-1028"></span></span>|
   
 <span data-ttu-id="a8dfa-1029">**Entidad de certificación de Symantec clase de 3 EV SSL - G3**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-1029">**Symantec Class 3 EV SSL CA - G3**</span></span>
  
||
|:-----|
|<span data-ttu-id="a8dfa-1030">**Asunto**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-1030">**Subject**</span></span>|
|<span data-ttu-id="a8dfa-1031">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-1031"></span></span>|
|<span data-ttu-id="a8dfa-1032">**Emisor**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-1032">**Issuer**</span></span>|
|<span data-ttu-id="a8dfa-1033">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-1033"></span></span>|
|<span data-ttu-id="a8dfa-1034">**Nombre alternativo del sujeto**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-1034">**Subject Alternative Name**</span></span>|
|<span data-ttu-id="a8dfa-1035">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-1035"></span></span>|
|<span data-ttu-id="a8dfa-1036">**Número de serie**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-1036">**Serial Number**</span></span>|
|<span data-ttu-id="a8dfa-1037">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-1037"></span></span>|
|<span data-ttu-id="a8dfa-1038">**Longitud de clave pública**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-1038">**Public Key Length**</span></span>|
|<span data-ttu-id="a8dfa-1039">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-1039"></span></span>|
|<span data-ttu-id="a8dfa-1040">**Algoritmo de firma**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-1040">**Signature Algorithm**</span></span>|
|<span data-ttu-id="a8dfa-1041">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-1041"></span></span>|
|<span data-ttu-id="a8dfa-1042">**Validez no antes**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-1042">**Validity Not Before**</span></span>|
|<span data-ttu-id="a8dfa-1043">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-1043"></span></span>|
|<span data-ttu-id="a8dfa-1044">**Validez no después**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-1044">**Validity Not After**</span></span>|
|<span data-ttu-id="a8dfa-1045">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-1045"></span></span>|
|<span data-ttu-id="a8dfa-1046">**Identificador de clave de asunto**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-1046">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="a8dfa-1047">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-1047"></span></span>|
|<span data-ttu-id="a8dfa-1048">**Identificador de clave de entidad de certificación**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-1048">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="a8dfa-1049">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-1049"></span></span>|
|<span data-ttu-id="a8dfa-1050">**Huella digital (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-1050">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="a8dfa-1051">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-1051"></span></span>|
|<span data-ttu-id="a8dfa-1052">**Huella digital (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-1052">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="a8dfa-1053">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-1053"></span></span>|
|<span data-ttu-id="a8dfa-1054">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-1054">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="a8dfa-1055">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-1055"></span></span>|
|<span data-ttu-id="a8dfa-1056">**Direcciones URL CRL**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-1056">**CRL URLs**</span></span>|
|<span data-ttu-id="a8dfa-1057">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-1057"></span></span>|
|<span data-ttu-id="a8dfa-1058">**Direcciones URL OCSP**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-1058">**OCSP URLs**</span></span>|
|<span data-ttu-id="a8dfa-1059">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-1059"></span></span>|
   
 <span data-ttu-id="a8dfa-1060">**Clase Symantec 3 servidores seguros CA - G4**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-1060">**Symantec Class 3 Secure Server CA - G4**</span></span>
  
||
|:-----|
|<span data-ttu-id="a8dfa-1061">**Asunto**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-1061">**Subject**</span></span>|
|<span data-ttu-id="a8dfa-1062">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-1062"></span></span>|
|<span data-ttu-id="a8dfa-1063">**Emisor**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-1063">**Issuer**</span></span>|
|<span data-ttu-id="a8dfa-1064">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-1064"></span></span>|
|<span data-ttu-id="a8dfa-1065">**Nombre alternativo del sujeto**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-1065">**Subject Alternative Name**</span></span>|
|<span data-ttu-id="a8dfa-1066">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-1066"></span></span>|
|<span data-ttu-id="a8dfa-1067">**Número de serie**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-1067">**Serial Number**</span></span>|
|<span data-ttu-id="a8dfa-1068">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-1068"></span></span>|
|<span data-ttu-id="a8dfa-1069">**Longitud de clave pública**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-1069">**Public Key Length**</span></span>|
|<span data-ttu-id="a8dfa-1070">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-1070"></span></span>|
|<span data-ttu-id="a8dfa-1071">**Algoritmo de firma**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-1071">**Signature Algorithm**</span></span>|
|<span data-ttu-id="a8dfa-1072">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-1072"></span></span>|
|<span data-ttu-id="a8dfa-1073">**Validez no antes**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-1073">**Validity Not Before**</span></span>|
|<span data-ttu-id="a8dfa-1074">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-1074"></span></span>|
|<span data-ttu-id="a8dfa-1075">**Validez no después**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-1075">**Validity Not After**</span></span>|
|<span data-ttu-id="a8dfa-1076">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-1076"></span></span>|
|<span data-ttu-id="a8dfa-1077">**Identificador de clave de asunto**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-1077">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="a8dfa-1078">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-1078"></span></span>|
|<span data-ttu-id="a8dfa-1079">**Identificador de clave de entidad de certificación**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-1079">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="a8dfa-1080">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-1080"></span></span>|
|<span data-ttu-id="a8dfa-1081">**Huella digital (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-1081">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="a8dfa-1082">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-1082"></span></span>|
|<span data-ttu-id="a8dfa-1083">**Huella digital (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-1083">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="a8dfa-1084">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-1084"></span></span>|
|<span data-ttu-id="a8dfa-1085">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-1085">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="a8dfa-1086">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-1086"></span></span>|
|<span data-ttu-id="a8dfa-1087">**Direcciones URL CRL**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-1087">**CRL URLs**</span></span>|
|<span data-ttu-id="a8dfa-1088">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-1088"></span></span>|
|<span data-ttu-id="a8dfa-1089">**Direcciones URL OCSP**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-1089">**OCSP URLs**</span></span>|
|<span data-ttu-id="a8dfa-1090">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-1090"></span></span>|
   
 <span data-ttu-id="a8dfa-1091">**Thawte SHA256 SSL entidad emisora de certificados**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-1091">**thawte SHA256 SSL CA**</span></span>
  
||
|:-----|
|<span data-ttu-id="a8dfa-1092">**Asunto**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-1092">**Subject**</span></span>|
|<span data-ttu-id="a8dfa-1093">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-1093"></span></span>|
|<span data-ttu-id="a8dfa-1094">**Emisor**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-1094">**Issuer**</span></span>|
|<span data-ttu-id="a8dfa-1095">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-1095"></span></span>|
|<span data-ttu-id="a8dfa-1096">**Nombre alternativo del sujeto**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-1096">**Subject Alternative Name**</span></span>|
|<span data-ttu-id="a8dfa-1097">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-1097"></span></span>|
|<span data-ttu-id="a8dfa-1098">**Número de serie**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-1098">**Serial Number**</span></span>|
|<span data-ttu-id="a8dfa-1099">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-1099"></span></span>|
|<span data-ttu-id="a8dfa-1100">**Longitud de clave pública**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-1100">**Public Key Length**</span></span>|
|<span data-ttu-id="a8dfa-1101">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-1101"></span></span>|
|<span data-ttu-id="a8dfa-1102">**Algoritmo de firma**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-1102">**Signature Algorithm**</span></span>|
|<span data-ttu-id="a8dfa-1103">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-1103"></span></span>|
|<span data-ttu-id="a8dfa-1104">**Validez no antes**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-1104">**Validity Not Before**</span></span>|
|<span data-ttu-id="a8dfa-1105">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-1105"></span></span>|
|<span data-ttu-id="a8dfa-1106">**Validez no después**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-1106">**Validity Not After**</span></span>|
|<span data-ttu-id="a8dfa-1107">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-1107"></span></span>|
|<span data-ttu-id="a8dfa-1108">**Identificador de clave de asunto**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-1108">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="a8dfa-1109">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-1109"></span></span>|
|<span data-ttu-id="a8dfa-1110">**Identificador de clave de entidad de certificación**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-1110">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="a8dfa-1111">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-1111"></span></span>|
|<span data-ttu-id="a8dfa-1112">**Huella digital (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-1112">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="a8dfa-1113">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-1113"></span></span>|
|<span data-ttu-id="a8dfa-1114">**Huella digital (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-1114">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="a8dfa-1115">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-1115"></span></span>|
|<span data-ttu-id="a8dfa-1116">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-1116">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="a8dfa-1117">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-1117"></span></span>|
|<span data-ttu-id="a8dfa-1118">**Direcciones URL CRL**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-1118">**CRL URLs**</span></span>|
|<span data-ttu-id="a8dfa-1119">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-1119"></span></span>|
|<span data-ttu-id="a8dfa-1120">**Direcciones URL OCSP**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-1120">**OCSP URLs**</span></span>|
|<span data-ttu-id="a8dfa-1121">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-1121"></span></span>|
   
 <span data-ttu-id="a8dfa-1122">**Entidad emisora de certificados SureServer de Verizon Akamai G14-SHA2**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-1122">**Verizon Akamai SureServer CA G14-SHA2**</span></span>
  
||
|:-----|
|<span data-ttu-id="a8dfa-1123">**Asunto**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-1123">**Subject**</span></span>|
|<span data-ttu-id="a8dfa-1124">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-1124"></span></span>|
|<span data-ttu-id="a8dfa-1125">**Emisor**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-1125">**Issuer**</span></span>|
|<span data-ttu-id="a8dfa-1126">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-1126"></span></span>|
|<span data-ttu-id="a8dfa-1127">**Número de serie**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-1127">**Serial Number**</span></span>|
|<span data-ttu-id="a8dfa-1128">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-1128"></span></span>|
|<span data-ttu-id="a8dfa-1129">**Longitud de clave pública**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-1129">**Public Key Length**</span></span>|
|<span data-ttu-id="a8dfa-1130">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-1130"></span></span>|
|<span data-ttu-id="a8dfa-1131">**Algoritmo de firma**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-1131">**Signature Algorithm**</span></span>|
|<span data-ttu-id="a8dfa-1132">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-1132"></span></span>|
|<span data-ttu-id="a8dfa-1133">**Validez no antes**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-1133">**Validity Not Before**</span></span>|
|<span data-ttu-id="a8dfa-1134">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-1134"></span></span>|
|<span data-ttu-id="a8dfa-1135">**Validez no después**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-1135">**Validity Not After**</span></span>|
|<span data-ttu-id="a8dfa-1136">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-1136"></span></span>|
|<span data-ttu-id="a8dfa-1137">**Identificador de clave de asunto**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-1137">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="a8dfa-1138">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-1138"></span></span>|
|<span data-ttu-id="a8dfa-1139">**Identificador de clave de entidad de certificación**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-1139">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="a8dfa-1140">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-1140"></span></span>|
|<span data-ttu-id="a8dfa-1141">**Huella digital (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-1141">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="a8dfa-1142">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-1142"></span></span>|
|<span data-ttu-id="a8dfa-1143">**Huella digital (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-1143">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="a8dfa-1144">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-1144"></span></span>|
|<span data-ttu-id="a8dfa-1145">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-1145">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="a8dfa-1146">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-1146"></span></span>|
|<span data-ttu-id="a8dfa-1147">**Direcciones URL AIA**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-1147">**AIA URLs**</span></span>|
|<span data-ttu-id="a8dfa-1148">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-1148"></span></span>|
|<span data-ttu-id="a8dfa-1149">**Direcciones URL CRL**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-1149">**CRL URLs**</span></span>|
|<span data-ttu-id="a8dfa-1150">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-1150"></span></span>|
|<span data-ttu-id="a8dfa-1151">**Direcciones URL OCSP**</span><span class="sxs-lookup"><span data-stu-id="a8dfa-1151">**OCSP URLs**</span></span>|
|<span data-ttu-id="a8dfa-1152">:-----</span><span class="sxs-lookup"><span data-stu-id="a8dfa-1152"></span></span>|
   
## <a name="additional-certificate-paths"></a><span data-ttu-id="a8dfa-1153">Rutas de acceso del certificado adicional</span><span class="sxs-lookup"><span data-stu-id="a8dfa-1153">Additional certificate paths</span></span>
<span data-ttu-id="a8dfa-1154"><a name="IntermediateCerts"> </a></span><span class="sxs-lookup"><span data-stu-id="a8dfa-1154"></span></span>

<span data-ttu-id="a8dfa-1155">El siguiente incluir certificados heredados que no se incluyen por encima y se combinarán con la lista de arriba a través del tiempo.</span><span class="sxs-lookup"><span data-stu-id="a8dfa-1155">The following include legacy certificates that aren't included above and will be merged with the list above over time.</span></span>
  
```
evsecure-aia.verisign.com
sa.symcb.com
sd.symcb.com
*.omniroot.com
*.verisign.com
*.symcb.com
*.symcd.com
*.verisign.net
*.geotrust.com
*.entrust.net
*.public-trust.com
EVIntl-ocsp.verisign.com
EVSecure-ocsp.verisign.com
isrg.trustid.ocsp.identrust.com
ocsp.digicert.com
ocsp.entrust.net
ocsp.globalsign.com/ExtendedSSLSHA256CACross
ocsp.globalsign.com/rootr1
ocsp.globalsign.com/rootr2
ocsp2.globalsign.com/rootr3
ocsp.int-x3.letsencrypt.org/
ocsp.msocsp.com
ocsp.omniroot.com/baltimoreroot
ocsp2.globalsign.com/gsextendvalsha2g3r3
ocsp2.globalsign.com/gsorganizationvalsha2g2
ocsp2.globalsign.com/gsorganizationvalsha2g3
ocsp2.globalsign.com/rootr3
ocspx.digicert.com
s2.symcb.com
sr.symcd.com
su.symcd.com
vassg142.ocsp.omniroot.com
cdp1.public-trust.com/CRL/Omniroot2025.crl
crl.entrust.net/2048ca.crl
crl.entrust.net/g2ca.crl
crl.entrust.net/level1k.crl
crl.entrust.net/rootca1.crl
crl.globalsign.com/gs/gsextendvalsha2g3r3.crl
crl.globalsign.com/gs/gsorganizationvalsha2g2.crl
crl.globalsign.com/gsorganizationvalsha2g3.crl
crl.globalsign.com/root.crl
crl.globalsign.net/root-r2.crl
crl.globalsign.com/root-r3.crl
crl.globalsign.net/root.crl
crl.identrust.com/DSTROOTCAX3CRL.crl
crl.microsoft.com/pki/mscorp/crl/msitwww1.crl
crl.microsoft.com/pki/mscorp/crl/msitwww2.crl
crl3.digicert.com/DigiCertCloudServicesCA-1-g1.crl
crl3.digicert.com/DigiCertGlobalRootCA.crl
crl3.digicert.com/sha2-ev-server-g1.crl
crl3.digicert.com/sha2-ha-server-g5.crl
crl3.digicert.com/ssca-sha2-g5.crl
crl4.digicert.com/DigiCertCloudServicesCA-1-g1.crl
crl4.digicert.com/DigiCertGlobalRootCA.crl
crl4.digicert.com/DigiCertHighAssuranceEVRootCA.crl
crl4.digicert.com/sha2-ev-server-g1.crl
crl4.digicert.com/sha2-ha-server-g5.crl
crl4.digicert.com/ssca-sha2-g5.crl
EVIntl-crl.verisign.com/EVIntl2006.crl
EVSecure-crl.verisign.com/pca3-g5.crl
mscrl.microsoft.com/pki/mscorp/crl/msitwww1.crl
mscrl.microsoft.com/pki/mscorp/crl/msitwww2.crl
s1.symcb.com/pca3-g5.crl
sr.symcb.com/sr.crl
su.symcb.com/su.crl
vassg142.crl.omniroot.com/vassg142.crl
aia.entrust.net/l1k-chain256.cer
apps.identrust.com/roots/dstrootcax3.p7c
https://cacert.a.omniroot.com/vassg142.crt
https://cacert.a.omniroot.com/vassg142.der
https://cacert.omniroot.com/baltimoreroot.crt
https://cacert.omniroot.com/baltimoreroot.der
cacerts.digicert.com/DigiCertCloudServicesCA-1.crt
cacerts.digicert.com/DigiCertSHA2ExtendedValidationServerCA.crt
cacerts.digicert.com/DigiCertSHA2HighAssuranceServerCA.crt
cacerts.digicert.com/DigiCertSHA2SecureServerCA.crt
cert.int-x3.letsencrypt.org/
EVIntl-aia.verisign.com/EVIntl2006.cer
secure.globalsign.com/cacert/gsextendvalsha2g2r2.crt
secure.globalsign.com/cacert/gsextendvalsha2g3r3.crt
secure.globalsign.com/cacert/gsorganizationvalsha2g2r1.crt
secure.globalsign.com/cacert/gsorganizationvalsha2g3.crt
sr.symcb.com/sr.crt
su.symcb.com/su.crt
https://www.digicert.com/CACerts/DigiCertGlobalRootCA.crt
https://www.digicert.com/CACerts/DigiCertHighAssuranceEVRootCA.crt
www.microsoft.com/pki/mscorp/msitwww1.crt
www.microsoft.com/pki/mscorp/msitwww2.crt

```


