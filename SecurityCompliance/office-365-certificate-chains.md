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
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22536079"
---
# <a name="office-365-certificate-chains"></a><span data-ttu-id="54587-106">Cadenas de certificados de Office 365</span><span class="sxs-lookup"><span data-stu-id="54587-106">Office 365 Certificate Chains</span></span>

<span data-ttu-id="54587-p102">Office 365 aprovecha un número de proveedores de certificado diferentes. A continuación describe la lista completa de certificados de raíz de Office 365 conocidos que pueden encontrar los clientes al obtener acceso a Office 365. Para obtener información sobre los certificados que necesita instalar en su propia infraestructura, consulte [Plan para los certificados SSL de terceros para Office 365](https://support.office.com/article/b48cdf63-07e0-4cda-8c12-4871590f59ce). La siguiente información del certificado se aplica a todas las instancias de la nube en todo el mundo y nacionales de Office 365.</span><span class="sxs-lookup"><span data-stu-id="54587-p102">Office 365 leverages a number of different certificate providers. The following describes the complete list of known Office 365 root certificates that customers may encounter when accessing Office 365. For information on the certificates you may need to install in your own infrastructure, see [Plan for third-party SSL certificates for Office 365](https://support.office.com/article/b48cdf63-07e0-4cda-8c12-4871590f59ce). The following certificate information applies to all worldwide and national cloud instances of Office 365.</span></span>
  

|<span data-ttu-id="54587-111">**Tipo de certificado**</span><span class="sxs-lookup"><span data-stu-id="54587-111">**Certificate type**</span></span>|<span data-ttu-id="54587-112">**Descarga de P7b**</span><span class="sxs-lookup"><span data-stu-id="54587-112">**P7b download**</span></span>|<span data-ttu-id="54587-113">**Extremos CRL**</span><span class="sxs-lookup"><span data-stu-id="54587-113">**CRL Endpoints**</span></span>|<span data-ttu-id="54587-114">**Extremos OCSP**</span><span class="sxs-lookup"><span data-stu-id="54587-114">**OCSP Endpoints**</span></span>|<span data-ttu-id="54587-115">**Extremos AIA**</span><span class="sxs-lookup"><span data-stu-id="54587-115">**AIA Endpoints**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|[<span data-ttu-id="54587-116">Certificados raíz de confianza públicamente</span><span class="sxs-lookup"><span data-stu-id="54587-116">Publicly Trusted Root Certificates</span></span>](https://support.office.com/article/0c03e6b3-e73f-4316-9e2b-bf4091ae96bb#rootcerts) <br/> |[<span data-ttu-id="54587-117">Agrupación de certificado raíz de Office 365 (P7B)</span><span class="sxs-lookup"><span data-stu-id="54587-117">Office 365 Root Certificate Bundle (P7B)</span></span>](http://download.microsoft.com/download/A/5/A/A5AE01F3-D19B-4A11-9407-801263CEF72C/O365_Root_Certs_20170321.p7b) <br/> |<span data-ttu-id="54587-118">CRL.GlobalSign.NET</span><span class="sxs-lookup"><span data-stu-id="54587-118">crl.globalsign.net</span></span>  <br/> <span data-ttu-id="54587-119">www.d-Trust.NET</span><span class="sxs-lookup"><span data-stu-id="54587-119">www.d-trust.net</span></span>  <br/> |<span data-ttu-id="54587-120">N/D</span><span class="sxs-lookup"><span data-stu-id="54587-120">N/A</span></span>  <br/> |<span data-ttu-id="54587-121">N/D</span><span class="sxs-lookup"><span data-stu-id="54587-121">N/A</span></span>  <br/> |
|[<span data-ttu-id="54587-122">Los certificados intermedios de confianza públicamente</span><span class="sxs-lookup"><span data-stu-id="54587-122">Publicly Trusted Intermediate Certificates</span></span>](https://support.office.com/article/0c03e6b3-e73f-4316-9e2b-bf4091ae96bb#IntermediateCerts) <br/> |[<span data-ttu-id="54587-123">Agrupación de certificados intermedios de Office 365 (P7B)</span><span class="sxs-lookup"><span data-stu-id="54587-123">Office 365 Intermediate Certificate Bundle (P7B)</span></span>](http://download.microsoft.com/download/4/D/5/4D5339A4-0A4A-46AB-AE52-B179DEDA4BEC/O365_Intermediate_Certs_20170321.p7b)  <br/> |<span data-ttu-id="54587-124">cdp1.Public trust.com</span><span class="sxs-lookup"><span data-stu-id="54587-124">cdp1.public-trust.com</span></span>  <br/> <span data-ttu-id="54587-125">CRL.cnnic.CN</span><span class="sxs-lookup"><span data-stu-id="54587-125">crl.cnnic.cn</span></span>  <br/> <span data-ttu-id="54587-126">CRL.Entrust.NET</span><span class="sxs-lookup"><span data-stu-id="54587-126">crl.entrust.net</span></span>  <br/> <span data-ttu-id="54587-127">CRL.GlobalSign.com</span><span class="sxs-lookup"><span data-stu-id="54587-127">crl.globalsign.com</span></span>  <br/> <span data-ttu-id="54587-128">CRL.GlobalSign.NET</span><span class="sxs-lookup"><span data-stu-id="54587-128">crl.globalsign.net</span></span>  <br/> <span data-ttu-id="54587-129">CRL.identrust.com</span><span class="sxs-lookup"><span data-stu-id="54587-129">crl.identrust.com</span></span>  <br/> <span data-ttu-id="54587-130">CRL.Thawte.com</span><span class="sxs-lookup"><span data-stu-id="54587-130">crl.thawte.com</span></span>  <br/> <span data-ttu-id="54587-131">crl3.digicert.com</span><span class="sxs-lookup"><span data-stu-id="54587-131">crl3.digicert.com</span></span>  <br/> <span data-ttu-id="54587-132">crl4.digicert.com</span><span class="sxs-lookup"><span data-stu-id="54587-132">crl4.digicert.com</span></span>  <br/> <span data-ttu-id="54587-133">s1.symcb.com</span><span class="sxs-lookup"><span data-stu-id="54587-133">s1.symcb.com</span></span>  <br/> <span data-ttu-id="54587-134">www.d-Trust.NET</span><span class="sxs-lookup"><span data-stu-id="54587-134">www.d-trust.net</span></span>  <br/> |<span data-ttu-id="54587-135">isrg.trustid.OCSP.identrust.com</span><span class="sxs-lookup"><span data-stu-id="54587-135">isrg.trustid.ocsp.identrust.com</span></span>  <br/> <span data-ttu-id="54587-136">OCSP.digicert.com</span><span class="sxs-lookup"><span data-stu-id="54587-136">ocsp.digicert.com</span></span>  <br/> <span data-ttu-id="54587-137">OCSP.Entrust.NET</span><span class="sxs-lookup"><span data-stu-id="54587-137">ocsp.entrust.net</span></span>  <br/> <span data-ttu-id="54587-138">OCSP.GlobalSign.com</span><span class="sxs-lookup"><span data-stu-id="54587-138">ocsp.globalsign.com</span></span>  <br/> <span data-ttu-id="54587-139">OCSP.OmniRoot.com</span><span class="sxs-lookup"><span data-stu-id="54587-139">ocsp.omniroot.com</span></span>  <br/> <span data-ttu-id="54587-140">OCSP.startssl.com</span><span class="sxs-lookup"><span data-stu-id="54587-140">ocsp.startssl.com</span></span>  <br/> <span data-ttu-id="54587-141">OCSP.Thawte.com</span><span class="sxs-lookup"><span data-stu-id="54587-141">ocsp.thawte.com</span></span>  <br/> <span data-ttu-id="54587-142">ocsp2.GlobalSign.com</span><span class="sxs-lookup"><span data-stu-id="54587-142">ocsp2.globalsign.com</span></span>  <br/> <span data-ttu-id="54587-143">ocspcnnicroot.cnnic.CN</span><span class="sxs-lookup"><span data-stu-id="54587-143">ocspcnnicroot.cnnic.cn</span></span>  <br/> <span data-ttu-id="54587-144">raíz-c3-ca2-2009.ocsp.d-trust.net</span><span class="sxs-lookup"><span data-stu-id="54587-144">root-c3-ca2-2009.ocsp.d-trust.net</span></span>  <br/> <span data-ttu-id="54587-145">root-C3-cA2-EV-2009.OCSP.d-Trust.NET</span><span class="sxs-lookup"><span data-stu-id="54587-145">root-c3-ca2-ev-2009.ocsp.d-trust.net</span></span>  <br/> <span data-ttu-id="54587-146">s2.symcb.com</span><span class="sxs-lookup"><span data-stu-id="54587-146">s2.symcb.com</span></span>  <br/> |<span data-ttu-id="54587-147">AIA.startssl.com</span><span class="sxs-lookup"><span data-stu-id="54587-147">aia.startssl.com</span></span>  <br/> <span data-ttu-id="54587-148">Apps.identrust.com</span><span class="sxs-lookup"><span data-stu-id="54587-148">apps.identrust.com</span></span>  <br/> <span data-ttu-id="54587-149">CACert.OmniRoot.com</span><span class="sxs-lookup"><span data-stu-id="54587-149">cacert.omniroot.com</span></span>  <br/> <span data-ttu-id="54587-150">www.cnnic.CN</span><span class="sxs-lookup"><span data-stu-id="54587-150">www.cnnic.cn</span></span>  <br/> |
   
<span data-ttu-id="54587-151">Expanda la raíz y las secciones intermedias para ver detalles adicionales acerca de los proveedores de certificado.</span><span class="sxs-lookup"><span data-stu-id="54587-151">Expand the root and intermediate sections below to see additional details about the certificate providers.</span></span>
  
## <a name="office-365-root-certificate-details"></a><span data-ttu-id="54587-152">Detalles del certificado de raíz de Office 365</span><span class="sxs-lookup"><span data-stu-id="54587-152">Office 365 Root Certificate Details</span></span>
<span data-ttu-id="54587-153"><a name="RootCerts"> </a></span><span class="sxs-lookup"><span data-stu-id="54587-153"></span></span>

 <span data-ttu-id="54587-154">**Baltimore CyberTrust Root**</span><span class="sxs-lookup"><span data-stu-id="54587-154">**Baltimore CyberTrust Root**</span></span>
  
<span data-ttu-id="54587-155">|:-----|</span><span class="sxs-lookup"><span data-stu-id="54587-155">|:-----|</span></span>
|<span data-ttu-id="54587-156">**Asunto**</span><span class="sxs-lookup"><span data-stu-id="54587-156">**Subject**</span></span>|
|:-----|
|<span data-ttu-id="54587-157">**Número de serie**</span><span class="sxs-lookup"><span data-stu-id="54587-157">**Serial Number**</span></span>|
|<span data-ttu-id="54587-158">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-158"></span></span>|
|<span data-ttu-id="54587-159">**Longitud de clave pública**</span><span class="sxs-lookup"><span data-stu-id="54587-159">**Public Key Length**</span></span>|
|<span data-ttu-id="54587-160">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-160"></span></span>|
|<span data-ttu-id="54587-161">**Algoritmo de firma**</span><span class="sxs-lookup"><span data-stu-id="54587-161">**Signature Algorithm**</span></span>|
|<span data-ttu-id="54587-162">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-162"></span></span>|
|<span data-ttu-id="54587-163">**Validez no antes**</span><span class="sxs-lookup"><span data-stu-id="54587-163">**Validity Not Before**</span></span>|
|<span data-ttu-id="54587-164">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-164"></span></span>|
|<span data-ttu-id="54587-165">**Validez no después**</span><span class="sxs-lookup"><span data-stu-id="54587-165">**Validity Not After**</span></span>|
|<span data-ttu-id="54587-166">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-166"></span></span>|
|<span data-ttu-id="54587-167">**Identificador de clave de asunto**</span><span class="sxs-lookup"><span data-stu-id="54587-167">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="54587-168">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-168"></span></span>|
|<span data-ttu-id="54587-169">**Huella digital (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="54587-169">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="54587-170">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-170"></span></span>|
|<span data-ttu-id="54587-171">**Huella digital (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="54587-171">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="54587-172">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-172"></span></span>|
|<span data-ttu-id="54587-173">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="54587-173">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="54587-174">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-174"></span></span>|
   
 <span data-ttu-id="54587-175">**RAÍZ DE CNNIC**</span><span class="sxs-lookup"><span data-stu-id="54587-175">**CNNIC ROOT**</span></span>
  
||
|:-----|
|<span data-ttu-id="54587-176">**Asunto**</span><span class="sxs-lookup"><span data-stu-id="54587-176">**Subject**</span></span>|
|<span data-ttu-id="54587-177">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-177"></span></span>|
|<span data-ttu-id="54587-178">**Número de serie**</span><span class="sxs-lookup"><span data-stu-id="54587-178">**Serial Number**</span></span>|
|<span data-ttu-id="54587-179">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-179"></span></span>|
|<span data-ttu-id="54587-180">**Longitud de clave pública**</span><span class="sxs-lookup"><span data-stu-id="54587-180">**Public Key Length**</span></span>|
|<span data-ttu-id="54587-181">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-181"></span></span>|
|<span data-ttu-id="54587-182">**Algoritmo de firma**</span><span class="sxs-lookup"><span data-stu-id="54587-182">**Signature Algorithm**</span></span>|
|<span data-ttu-id="54587-183">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-183"></span></span>|
|<span data-ttu-id="54587-184">**Validez no antes**</span><span class="sxs-lookup"><span data-stu-id="54587-184">**Validity Not Before**</span></span>|
|<span data-ttu-id="54587-185">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-185"></span></span>|
|<span data-ttu-id="54587-186">**Validez no después**</span><span class="sxs-lookup"><span data-stu-id="54587-186">**Validity Not After**</span></span>|
|<span data-ttu-id="54587-187">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-187"></span></span>|
|<span data-ttu-id="54587-188">**Identificador de clave de asunto**</span><span class="sxs-lookup"><span data-stu-id="54587-188">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="54587-189">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-189"></span></span>|
|<span data-ttu-id="54587-190">**Identificador de clave de entidad de certificación**</span><span class="sxs-lookup"><span data-stu-id="54587-190">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="54587-191">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-191"></span></span>|
|<span data-ttu-id="54587-192">**Huella digital (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="54587-192">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="54587-193">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-193"></span></span>|
|<span data-ttu-id="54587-194">**Huella digital (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="54587-194">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="54587-195">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-195"></span></span>|
|<span data-ttu-id="54587-196">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="54587-196">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="54587-197">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-197"></span></span>|
   
 <span data-ttu-id="54587-198">**DigiCert de entidad de certificación raíz Global**</span><span class="sxs-lookup"><span data-stu-id="54587-198">**DigiCert Global Root CA**</span></span>
  
||
|:-----|
|<span data-ttu-id="54587-199">**Asunto**</span><span class="sxs-lookup"><span data-stu-id="54587-199">**Subject**</span></span>|
|<span data-ttu-id="54587-200">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-200"></span></span>|
|<span data-ttu-id="54587-201">**Número de serie**</span><span class="sxs-lookup"><span data-stu-id="54587-201">**Serial Number**</span></span>|
|<span data-ttu-id="54587-202">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-202"></span></span>|
|<span data-ttu-id="54587-203">**Longitud de clave pública**</span><span class="sxs-lookup"><span data-stu-id="54587-203">**Public Key Length**</span></span>|
|<span data-ttu-id="54587-204">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-204"></span></span>|
|<span data-ttu-id="54587-205">**Algoritmo de firma**</span><span class="sxs-lookup"><span data-stu-id="54587-205">**Signature Algorithm**</span></span>|
|<span data-ttu-id="54587-206">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-206"></span></span>|
|<span data-ttu-id="54587-207">**Validez no antes**</span><span class="sxs-lookup"><span data-stu-id="54587-207">**Validity Not Before**</span></span>|
|<span data-ttu-id="54587-208">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-208"></span></span>|
|<span data-ttu-id="54587-209">**Validez no después**</span><span class="sxs-lookup"><span data-stu-id="54587-209">**Validity Not After**</span></span>|
|<span data-ttu-id="54587-210">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-210"></span></span>|
|<span data-ttu-id="54587-211">**Identificador de clave de asunto**</span><span class="sxs-lookup"><span data-stu-id="54587-211">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="54587-212">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-212"></span></span>|
|<span data-ttu-id="54587-213">**Identificador de clave de entidad de certificación**</span><span class="sxs-lookup"><span data-stu-id="54587-213">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="54587-214">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-214"></span></span>|
|<span data-ttu-id="54587-215">**Huella digital (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="54587-215">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="54587-216">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-216"></span></span>|
|<span data-ttu-id="54587-217">**Huella digital (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="54587-217">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="54587-218">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-218"></span></span>|
|<span data-ttu-id="54587-219">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="54587-219">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="54587-220">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-220"></span></span>|
   
 <span data-ttu-id="54587-221">**Entidad de certificación raíz de DigiCert High Assurance EV**</span><span class="sxs-lookup"><span data-stu-id="54587-221">**DigiCert High Assurance EV Root CA**</span></span>
  
||
|:-----|
|<span data-ttu-id="54587-222">**Asunto**</span><span class="sxs-lookup"><span data-stu-id="54587-222">**Subject**</span></span>|
|<span data-ttu-id="54587-223">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-223"></span></span>|
|<span data-ttu-id="54587-224">**Número de serie**</span><span class="sxs-lookup"><span data-stu-id="54587-224">**Serial Number**</span></span>|
|<span data-ttu-id="54587-225">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-225"></span></span>|
|<span data-ttu-id="54587-226">**Longitud de clave pública**</span><span class="sxs-lookup"><span data-stu-id="54587-226">**Public Key Length**</span></span>|
|<span data-ttu-id="54587-227">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-227"></span></span>|
|<span data-ttu-id="54587-228">**Algoritmo de firma**</span><span class="sxs-lookup"><span data-stu-id="54587-228">**Signature Algorithm**</span></span>|
|<span data-ttu-id="54587-229">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-229"></span></span>|
|<span data-ttu-id="54587-230">**Validez no antes**</span><span class="sxs-lookup"><span data-stu-id="54587-230">**Validity Not Before**</span></span>|
|<span data-ttu-id="54587-231">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-231"></span></span>|
|<span data-ttu-id="54587-232">**Validez no después**</span><span class="sxs-lookup"><span data-stu-id="54587-232">**Validity Not After**</span></span>|
|<span data-ttu-id="54587-233">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-233"></span></span>|
|<span data-ttu-id="54587-234">**Identificador de clave de asunto**</span><span class="sxs-lookup"><span data-stu-id="54587-234">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="54587-235">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-235"></span></span>|
|<span data-ttu-id="54587-236">**Identificador de clave de entidad de certificación**</span><span class="sxs-lookup"><span data-stu-id="54587-236">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="54587-237">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-237"></span></span>|
|<span data-ttu-id="54587-238">**Huella digital (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="54587-238">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="54587-239">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-239"></span></span>|
|<span data-ttu-id="54587-240">**Huella digital (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="54587-240">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="54587-241">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-241"></span></span>|
|<span data-ttu-id="54587-242">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="54587-242">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="54587-243">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-243"></span></span>|
   
 <span data-ttu-id="54587-244">**Entidad de certificación de raíz de confianza de D clase 3 2 de 2009**</span><span class="sxs-lookup"><span data-stu-id="54587-244">**D-TRUST Root Class 3 CA 2 2009**</span></span>
  
||
|:-----|
|<span data-ttu-id="54587-245">**Asunto**</span><span class="sxs-lookup"><span data-stu-id="54587-245">**Subject**</span></span>|
|<span data-ttu-id="54587-246">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-246"></span></span>|
|<span data-ttu-id="54587-247">**Número de serie**</span><span class="sxs-lookup"><span data-stu-id="54587-247">**Serial Number**</span></span>|
|<span data-ttu-id="54587-248">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-248"></span></span>|
|<span data-ttu-id="54587-249">**Longitud de clave pública**</span><span class="sxs-lookup"><span data-stu-id="54587-249">**Public Key Length**</span></span>|
|<span data-ttu-id="54587-250">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-250"></span></span>|
|<span data-ttu-id="54587-251">**Algoritmo de firma**</span><span class="sxs-lookup"><span data-stu-id="54587-251">**Signature Algorithm**</span></span>|
|<span data-ttu-id="54587-252">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-252"></span></span>|
|<span data-ttu-id="54587-253">**Validez no antes**</span><span class="sxs-lookup"><span data-stu-id="54587-253">**Validity Not Before**</span></span>|
|<span data-ttu-id="54587-254">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-254"></span></span>|
|<span data-ttu-id="54587-255">**Validez no después**</span><span class="sxs-lookup"><span data-stu-id="54587-255">**Validity Not After**</span></span>|
|<span data-ttu-id="54587-256">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-256"></span></span>|
|<span data-ttu-id="54587-257">**Identificador de clave de asunto**</span><span class="sxs-lookup"><span data-stu-id="54587-257">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="54587-258">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-258"></span></span>|
|<span data-ttu-id="54587-259">**Huella digital (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="54587-259">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="54587-260">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-260"></span></span>|
|<span data-ttu-id="54587-261">**Huella digital (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="54587-261">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="54587-262">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-262"></span></span>|
|<span data-ttu-id="54587-263">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="54587-263">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="54587-264">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-264"></span></span>|
|<span data-ttu-id="54587-265">**Direcciones URL CRL**</span><span class="sxs-lookup"><span data-stu-id="54587-265">**CRL URLs**</span></span>|
|<span data-ttu-id="54587-266">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-266"></span></span>|
   
 <span data-ttu-id="54587-267">**Entidad de certificación raíz de confianza de D clase 3 2 EV de 2009**</span><span class="sxs-lookup"><span data-stu-id="54587-267">**D-TRUST Root Class 3 CA 2 EV 2009**</span></span>
  
||
|:-----|
|<span data-ttu-id="54587-268">**Asunto**</span><span class="sxs-lookup"><span data-stu-id="54587-268">**Subject**</span></span>|
|<span data-ttu-id="54587-269">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-269"></span></span>|
|<span data-ttu-id="54587-270">**Número de serie**</span><span class="sxs-lookup"><span data-stu-id="54587-270">**Serial Number**</span></span>|
|<span data-ttu-id="54587-271">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-271"></span></span>|
|<span data-ttu-id="54587-272">**Longitud de clave pública**</span><span class="sxs-lookup"><span data-stu-id="54587-272">**Public Key Length**</span></span>|
|<span data-ttu-id="54587-273">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-273"></span></span>|
|<span data-ttu-id="54587-274">**Algoritmo de firma**</span><span class="sxs-lookup"><span data-stu-id="54587-274">**Signature Algorithm**</span></span>|
|<span data-ttu-id="54587-275">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-275"></span></span>|
|<span data-ttu-id="54587-276">**Validez no antes**</span><span class="sxs-lookup"><span data-stu-id="54587-276">**Validity Not Before**</span></span>|
|<span data-ttu-id="54587-277">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-277"></span></span>|
|<span data-ttu-id="54587-278">**Validez no después**</span><span class="sxs-lookup"><span data-stu-id="54587-278">**Validity Not After**</span></span>|
|<span data-ttu-id="54587-279">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-279"></span></span>|
|<span data-ttu-id="54587-280">**Identificador de clave de asunto**</span><span class="sxs-lookup"><span data-stu-id="54587-280">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="54587-281">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-281"></span></span>|
|<span data-ttu-id="54587-282">**Huella digital (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="54587-282">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="54587-283">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-283"></span></span>|
|<span data-ttu-id="54587-284">**Huella digital (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="54587-284">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="54587-285">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-285"></span></span>|
|<span data-ttu-id="54587-286">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="54587-286">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="54587-287">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-287"></span></span>|
|<span data-ttu-id="54587-288">**Direcciones URL CRL**</span><span class="sxs-lookup"><span data-stu-id="54587-288">**CRL URLs**</span></span>|
|<span data-ttu-id="54587-289">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-289"></span></span>|
   
 <span data-ttu-id="54587-290">**X3 de la entidad de certificación de raíz de horario de verano**</span><span class="sxs-lookup"><span data-stu-id="54587-290">**DST Root CA X3**</span></span>
  
||
|:-----|
|<span data-ttu-id="54587-291">**Asunto**</span><span class="sxs-lookup"><span data-stu-id="54587-291">**Subject**</span></span>|
|<span data-ttu-id="54587-292">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-292"></span></span>|
|<span data-ttu-id="54587-293">**Número de serie**</span><span class="sxs-lookup"><span data-stu-id="54587-293">**Serial Number**</span></span>|
|<span data-ttu-id="54587-294">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-294"></span></span>|
|<span data-ttu-id="54587-295">**Longitud de clave pública**</span><span class="sxs-lookup"><span data-stu-id="54587-295">**Public Key Length**</span></span>|
|<span data-ttu-id="54587-296">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-296"></span></span>|
|<span data-ttu-id="54587-297">**Algoritmo de firma**</span><span class="sxs-lookup"><span data-stu-id="54587-297">**Signature Algorithm**</span></span>|
|<span data-ttu-id="54587-298">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-298"></span></span>|
|<span data-ttu-id="54587-299">**Validez no antes**</span><span class="sxs-lookup"><span data-stu-id="54587-299">**Validity Not Before**</span></span>|
|<span data-ttu-id="54587-300">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-300"></span></span>|
|<span data-ttu-id="54587-301">**Validez no después**</span><span class="sxs-lookup"><span data-stu-id="54587-301">**Validity Not After**</span></span>|
|<span data-ttu-id="54587-302">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-302"></span></span>|
|<span data-ttu-id="54587-303">**Identificador de clave de asunto**</span><span class="sxs-lookup"><span data-stu-id="54587-303">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="54587-304">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-304"></span></span>|
|<span data-ttu-id="54587-305">**Huella digital (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="54587-305">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="54587-306">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-306"></span></span>|
|<span data-ttu-id="54587-307">**Huella digital (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="54587-307">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="54587-308">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-308"></span></span>|
|<span data-ttu-id="54587-309">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="54587-309">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="54587-310">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-310"></span></span>|
   
 <span data-ttu-id="54587-311">**Entrust entidad de certificación raíz - G2**</span><span class="sxs-lookup"><span data-stu-id="54587-311">**Entrust Root Certification Authority - G2**</span></span>
  
||
|:-----|
|<span data-ttu-id="54587-312">**Asunto**</span><span class="sxs-lookup"><span data-stu-id="54587-312">**Subject**</span></span>|
|<span data-ttu-id="54587-313">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-313"></span></span>|
|<span data-ttu-id="54587-314">**Número de serie**</span><span class="sxs-lookup"><span data-stu-id="54587-314">**Serial Number**</span></span>|
|<span data-ttu-id="54587-315">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-315"></span></span>|
|<span data-ttu-id="54587-316">**Longitud de clave pública**</span><span class="sxs-lookup"><span data-stu-id="54587-316">**Public Key Length**</span></span>|
|<span data-ttu-id="54587-317">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-317"></span></span>|
|<span data-ttu-id="54587-318">**Algoritmo de firma**</span><span class="sxs-lookup"><span data-stu-id="54587-318">**Signature Algorithm**</span></span>|
|<span data-ttu-id="54587-319">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-319"></span></span>|
|<span data-ttu-id="54587-320">**Validez no antes**</span><span class="sxs-lookup"><span data-stu-id="54587-320">**Validity Not Before**</span></span>|
|<span data-ttu-id="54587-321">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-321"></span></span>|
|<span data-ttu-id="54587-322">**Validez no después**</span><span class="sxs-lookup"><span data-stu-id="54587-322">**Validity Not After**</span></span>|
|<span data-ttu-id="54587-323">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-323"></span></span>|
|<span data-ttu-id="54587-324">**Identificador de clave de asunto**</span><span class="sxs-lookup"><span data-stu-id="54587-324">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="54587-325">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-325"></span></span>|
|<span data-ttu-id="54587-326">**Huella digital (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="54587-326">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="54587-327">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-327"></span></span>|
|<span data-ttu-id="54587-328">**Huella digital (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="54587-328">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="54587-329">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-329"></span></span>|
|<span data-ttu-id="54587-330">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="54587-330">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="54587-331">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-331"></span></span>|
   
 <span data-ttu-id="54587-332">**Entrust.net Certification Authority (2048)**</span><span class="sxs-lookup"><span data-stu-id="54587-332">**Entrust.net Certification Authority (2048)**</span></span>
  
||
|:-----|
|<span data-ttu-id="54587-333">**Asunto**</span><span class="sxs-lookup"><span data-stu-id="54587-333">**Subject**</span></span>|
|<span data-ttu-id="54587-334">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-334"></span></span>|
|<span data-ttu-id="54587-335">**Número de serie**</span><span class="sxs-lookup"><span data-stu-id="54587-335">**Serial Number**</span></span>|
|<span data-ttu-id="54587-336">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-336"></span></span>|
|<span data-ttu-id="54587-337">**Longitud de clave pública**</span><span class="sxs-lookup"><span data-stu-id="54587-337">**Public Key Length**</span></span>|
|<span data-ttu-id="54587-338">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-338"></span></span>|
|<span data-ttu-id="54587-339">**Algoritmo de firma**</span><span class="sxs-lookup"><span data-stu-id="54587-339">**Signature Algorithm**</span></span>|
|<span data-ttu-id="54587-340">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-340"></span></span>|
|<span data-ttu-id="54587-341">**Validez no antes**</span><span class="sxs-lookup"><span data-stu-id="54587-341">**Validity Not Before**</span></span>|
|<span data-ttu-id="54587-342">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-342"></span></span>|
|<span data-ttu-id="54587-343">**Validez no después**</span><span class="sxs-lookup"><span data-stu-id="54587-343">**Validity Not After**</span></span>|
|<span data-ttu-id="54587-344">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-344"></span></span>|
|<span data-ttu-id="54587-345">**Identificador de clave de asunto**</span><span class="sxs-lookup"><span data-stu-id="54587-345">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="54587-346">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-346"></span></span>|
|<span data-ttu-id="54587-347">**Huella digital (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="54587-347">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="54587-348">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-348"></span></span>|
|<span data-ttu-id="54587-349">**Huella digital (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="54587-349">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="54587-350">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-350"></span></span>|
|<span data-ttu-id="54587-351">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="54587-351">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="54587-352">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-352"></span></span>|
   
 <span data-ttu-id="54587-353">**GlobalSign**</span><span class="sxs-lookup"><span data-stu-id="54587-353">**GlobalSign**</span></span>
  
||
|:-----|
|<span data-ttu-id="54587-354">**Asunto**</span><span class="sxs-lookup"><span data-stu-id="54587-354">**Subject**</span></span>|
|<span data-ttu-id="54587-355">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-355"></span></span>|
|<span data-ttu-id="54587-356">**Número de serie**</span><span class="sxs-lookup"><span data-stu-id="54587-356">**Serial Number**</span></span>|
|<span data-ttu-id="54587-357">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-357"></span></span>|
|<span data-ttu-id="54587-358">**Longitud de clave pública**</span><span class="sxs-lookup"><span data-stu-id="54587-358">**Public Key Length**</span></span>|
|<span data-ttu-id="54587-359">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-359"></span></span>|
|<span data-ttu-id="54587-360">**Algoritmo de firma**</span><span class="sxs-lookup"><span data-stu-id="54587-360">**Signature Algorithm**</span></span>|
|<span data-ttu-id="54587-361">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-361"></span></span>|
|<span data-ttu-id="54587-362">**Validez no antes**</span><span class="sxs-lookup"><span data-stu-id="54587-362">**Validity Not Before**</span></span>|
|<span data-ttu-id="54587-363">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-363"></span></span>|
|<span data-ttu-id="54587-364">**Validez no después**</span><span class="sxs-lookup"><span data-stu-id="54587-364">**Validity Not After**</span></span>|
|<span data-ttu-id="54587-365">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-365"></span></span>|
|<span data-ttu-id="54587-366">**Identificador de clave de asunto**</span><span class="sxs-lookup"><span data-stu-id="54587-366">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="54587-367">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-367"></span></span>|
|<span data-ttu-id="54587-368">**Identificador de clave de entidad de certificación**</span><span class="sxs-lookup"><span data-stu-id="54587-368">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="54587-369">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-369"></span></span>|
|<span data-ttu-id="54587-370">**Huella digital (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="54587-370">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="54587-371">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-371"></span></span>|
|<span data-ttu-id="54587-372">**Huella digital (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="54587-372">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="54587-373">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-373"></span></span>|
|<span data-ttu-id="54587-374">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="54587-374">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="54587-375">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-375"></span></span>|
|<span data-ttu-id="54587-376">**Direcciones URL CRL**</span><span class="sxs-lookup"><span data-stu-id="54587-376">**CRL URLs**</span></span>|
|<span data-ttu-id="54587-377">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-377"></span></span>|
   
 <span data-ttu-id="54587-378">**GlobalSign Root CA**</span><span class="sxs-lookup"><span data-stu-id="54587-378">**GlobalSign Root CA**</span></span>
  
||
|:-----|
|<span data-ttu-id="54587-379">**Asunto**</span><span class="sxs-lookup"><span data-stu-id="54587-379">**Subject**</span></span>|
|<span data-ttu-id="54587-380">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-380"></span></span>|
|<span data-ttu-id="54587-381">**Número de serie**</span><span class="sxs-lookup"><span data-stu-id="54587-381">**Serial Number**</span></span>|
|<span data-ttu-id="54587-382">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-382"></span></span>|
|<span data-ttu-id="54587-383">**Longitud de clave pública**</span><span class="sxs-lookup"><span data-stu-id="54587-383">**Public Key Length**</span></span>|
|<span data-ttu-id="54587-384">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-384"></span></span>|
|<span data-ttu-id="54587-385">**Algoritmo de firma**</span><span class="sxs-lookup"><span data-stu-id="54587-385">**Signature Algorithm**</span></span>|
|<span data-ttu-id="54587-386">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-386"></span></span>|
|<span data-ttu-id="54587-387">**Validez no antes**</span><span class="sxs-lookup"><span data-stu-id="54587-387">**Validity Not Before**</span></span>|
|<span data-ttu-id="54587-388">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-388"></span></span>|
|<span data-ttu-id="54587-389">**Validez no después**</span><span class="sxs-lookup"><span data-stu-id="54587-389">**Validity Not After**</span></span>|
|<span data-ttu-id="54587-390">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-390"></span></span>|
|<span data-ttu-id="54587-391">**Identificador de clave de asunto**</span><span class="sxs-lookup"><span data-stu-id="54587-391">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="54587-392">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-392"></span></span>|
|<span data-ttu-id="54587-393">**Huella digital (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="54587-393">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="54587-394">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-394"></span></span>|
|<span data-ttu-id="54587-395">**Huella digital (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="54587-395">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="54587-396">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-396"></span></span>|
|<span data-ttu-id="54587-397">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="54587-397">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="54587-398">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-398"></span></span>|
   
 <span data-ttu-id="54587-399">**Thawte entidad emisora de certificados raíz principal - G3**</span><span class="sxs-lookup"><span data-stu-id="54587-399">**thawte Primary Root CA - G3**</span></span>
  
||
|:-----|
|<span data-ttu-id="54587-400">**Asunto**</span><span class="sxs-lookup"><span data-stu-id="54587-400">**Subject**</span></span>|
|<span data-ttu-id="54587-401">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-401"></span></span>|
|<span data-ttu-id="54587-402">**Número de serie**</span><span class="sxs-lookup"><span data-stu-id="54587-402">**Serial Number**</span></span>|
|<span data-ttu-id="54587-403">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-403"></span></span>|
|<span data-ttu-id="54587-404">**Longitud de clave pública**</span><span class="sxs-lookup"><span data-stu-id="54587-404">**Public Key Length**</span></span>|
|<span data-ttu-id="54587-405">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-405"></span></span>|
|<span data-ttu-id="54587-406">**Algoritmo de firma**</span><span class="sxs-lookup"><span data-stu-id="54587-406">**Signature Algorithm**</span></span>|
|<span data-ttu-id="54587-407">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-407"></span></span>|
|<span data-ttu-id="54587-408">**Validez no antes**</span><span class="sxs-lookup"><span data-stu-id="54587-408">**Validity Not Before**</span></span>|
|<span data-ttu-id="54587-409">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-409"></span></span>|
|<span data-ttu-id="54587-410">**Validez no después**</span><span class="sxs-lookup"><span data-stu-id="54587-410">**Validity Not After**</span></span>|
|<span data-ttu-id="54587-411">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-411"></span></span>|
|<span data-ttu-id="54587-412">**Identificador de clave de asunto**</span><span class="sxs-lookup"><span data-stu-id="54587-412">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="54587-413">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-413"></span></span>|
|<span data-ttu-id="54587-414">**Huella digital (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="54587-414">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="54587-415">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-415"></span></span>|
|<span data-ttu-id="54587-416">**Huella digital (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="54587-416">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="54587-417">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-417"></span></span>|
|<span data-ttu-id="54587-418">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="54587-418">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="54587-419">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-419"></span></span>|
   
 <span data-ttu-id="54587-420">**Entidad de certificación principal pública de clase 3 de VeriSign - G5**</span><span class="sxs-lookup"><span data-stu-id="54587-420">**VeriSign Class 3 Public Primary Certification Authority - G5**</span></span>
  
||
|:-----|
|<span data-ttu-id="54587-421">**Asunto**</span><span class="sxs-lookup"><span data-stu-id="54587-421">**Subject**</span></span>|
|<span data-ttu-id="54587-422">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-422"></span></span>|
|<span data-ttu-id="54587-423">**Número de serie**</span><span class="sxs-lookup"><span data-stu-id="54587-423">**Serial Number**</span></span>|
|<span data-ttu-id="54587-424">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-424"></span></span>|
|<span data-ttu-id="54587-425">**Longitud de clave pública**</span><span class="sxs-lookup"><span data-stu-id="54587-425">**Public Key Length**</span></span>|
|<span data-ttu-id="54587-426">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-426"></span></span>|
|<span data-ttu-id="54587-427">**Algoritmo de firma**</span><span class="sxs-lookup"><span data-stu-id="54587-427">**Signature Algorithm**</span></span>|
|<span data-ttu-id="54587-428">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-428"></span></span>|
|<span data-ttu-id="54587-429">**Validez no antes**</span><span class="sxs-lookup"><span data-stu-id="54587-429">**Validity Not Before**</span></span>|
|<span data-ttu-id="54587-430">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-430"></span></span>|
|<span data-ttu-id="54587-431">**Validez no después**</span><span class="sxs-lookup"><span data-stu-id="54587-431">**Validity Not After**</span></span>|
|<span data-ttu-id="54587-432">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-432"></span></span>|
|<span data-ttu-id="54587-433">**Identificador de clave de asunto**</span><span class="sxs-lookup"><span data-stu-id="54587-433">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="54587-434">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-434"></span></span>|
|<span data-ttu-id="54587-435">**Huella digital (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="54587-435">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="54587-436">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-436"></span></span>|
|<span data-ttu-id="54587-437">**Huella digital (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="54587-437">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="54587-438">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-438"></span></span>|
|<span data-ttu-id="54587-439">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="54587-439">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="54587-440">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-440"></span></span>|
   
## <a name="office-365-intermediate-certificate-details"></a><span data-ttu-id="54587-441">Detalles del certificado intermedio de Office 365</span><span class="sxs-lookup"><span data-stu-id="54587-441">Office 365 Intermediate Certificate Details</span></span>
<span data-ttu-id="54587-442"><a name="IntermediateCerts"> </a></span><span class="sxs-lookup"><span data-stu-id="54587-442"></span></span>

 <span data-ttu-id="54587-443">**CNNIC SHA256 SSL**</span><span class="sxs-lookup"><span data-stu-id="54587-443">**CNNIC SHA256 SSL**</span></span>
  
||
|:-----|
|<span data-ttu-id="54587-444">**Asunto**</span><span class="sxs-lookup"><span data-stu-id="54587-444">**Subject**</span></span>|
|<span data-ttu-id="54587-445">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-445"></span></span>|
|<span data-ttu-id="54587-446">**Emisor**</span><span class="sxs-lookup"><span data-stu-id="54587-446">**Issuer**</span></span>|
|<span data-ttu-id="54587-447">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-447"></span></span>|
|<span data-ttu-id="54587-448">**Número de serie**</span><span class="sxs-lookup"><span data-stu-id="54587-448">**Serial Number**</span></span>|
|<span data-ttu-id="54587-449">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-449"></span></span>|
|<span data-ttu-id="54587-450">**Longitud de clave pública**</span><span class="sxs-lookup"><span data-stu-id="54587-450">**Public Key Length**</span></span>|
|<span data-ttu-id="54587-451">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-451"></span></span>|
|<span data-ttu-id="54587-452">**Algoritmo de firma**</span><span class="sxs-lookup"><span data-stu-id="54587-452">**Signature Algorithm**</span></span>|
|<span data-ttu-id="54587-453">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-453"></span></span>|
|<span data-ttu-id="54587-454">**Validez no antes**</span><span class="sxs-lookup"><span data-stu-id="54587-454">**Validity Not Before**</span></span>|
|<span data-ttu-id="54587-455">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-455"></span></span>|
|<span data-ttu-id="54587-456">**Validez no después**</span><span class="sxs-lookup"><span data-stu-id="54587-456">**Validity Not After**</span></span>|
|<span data-ttu-id="54587-457">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-457"></span></span>|
|<span data-ttu-id="54587-458">**Identificador de clave de asunto**</span><span class="sxs-lookup"><span data-stu-id="54587-458">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="54587-459">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-459"></span></span>|
|<span data-ttu-id="54587-460">**Identificador de clave de entidad de certificación**</span><span class="sxs-lookup"><span data-stu-id="54587-460">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="54587-461">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-461"></span></span>|
|<span data-ttu-id="54587-462">**Huella digital (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="54587-462">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="54587-463">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-463"></span></span>|
|<span data-ttu-id="54587-464">**Huella digital (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="54587-464">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="54587-465">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-465"></span></span>|
|<span data-ttu-id="54587-466">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="54587-466">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="54587-467">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-467"></span></span>|
|<span data-ttu-id="54587-468">**Direcciones URL AIA**</span><span class="sxs-lookup"><span data-stu-id="54587-468">**AIA URLs**</span></span>|
|<span data-ttu-id="54587-469">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-469"></span></span>|
|<span data-ttu-id="54587-470">**Direcciones URL CRL**</span><span class="sxs-lookup"><span data-stu-id="54587-470">**CRL URLs**</span></span>|
|<span data-ttu-id="54587-471">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-471"></span></span>|
|<span data-ttu-id="54587-472">**Direcciones URL OCSP**</span><span class="sxs-lookup"><span data-stu-id="54587-472">**OCSP URLs**</span></span>|
|<span data-ttu-id="54587-473">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-473"></span></span>|
   
 <span data-ttu-id="54587-474">**Entidad de certificación de confianza de D SSL clase 3 1 de 2009**</span><span class="sxs-lookup"><span data-stu-id="54587-474">**D-TRUST SSL Class 3 CA 1 2009**</span></span>
  
||
|:-----|
|<span data-ttu-id="54587-475">**Asunto**</span><span class="sxs-lookup"><span data-stu-id="54587-475">**Subject**</span></span>|
|<span data-ttu-id="54587-476">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-476"></span></span>|
|<span data-ttu-id="54587-477">**Emisor**</span><span class="sxs-lookup"><span data-stu-id="54587-477">**Issuer**</span></span>|
|<span data-ttu-id="54587-478">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-478"></span></span>|
|<span data-ttu-id="54587-479">**Nombre alternativo del sujeto**</span><span class="sxs-lookup"><span data-stu-id="54587-479">**Subject Alternative Name**</span></span>|
|<span data-ttu-id="54587-480">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-480"></span></span>|
|<span data-ttu-id="54587-481">**Número de serie**</span><span class="sxs-lookup"><span data-stu-id="54587-481">**Serial Number**</span></span>|
|<span data-ttu-id="54587-482">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-482"></span></span>|
|<span data-ttu-id="54587-483">**Longitud de clave pública**</span><span class="sxs-lookup"><span data-stu-id="54587-483">**Public Key Length**</span></span>|
|<span data-ttu-id="54587-484">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-484"></span></span>|
|<span data-ttu-id="54587-485">**Algoritmo de firma**</span><span class="sxs-lookup"><span data-stu-id="54587-485">**Signature Algorithm**</span></span>|
|<span data-ttu-id="54587-486">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-486"></span></span>|
|<span data-ttu-id="54587-487">**Validez no antes**</span><span class="sxs-lookup"><span data-stu-id="54587-487">**Validity Not Before**</span></span>|
|<span data-ttu-id="54587-488">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-488"></span></span>|
|<span data-ttu-id="54587-489">**Validez no después**</span><span class="sxs-lookup"><span data-stu-id="54587-489">**Validity Not After**</span></span>|
|<span data-ttu-id="54587-490">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-490"></span></span>|
|<span data-ttu-id="54587-491">**Identificador de clave de asunto**</span><span class="sxs-lookup"><span data-stu-id="54587-491">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="54587-492">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-492"></span></span>|
|<span data-ttu-id="54587-493">**Identificador de clave de entidad de certificación**</span><span class="sxs-lookup"><span data-stu-id="54587-493">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="54587-494">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-494"></span></span>|
|<span data-ttu-id="54587-495">**Huella digital (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="54587-495">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="54587-496">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-496"></span></span>|
|<span data-ttu-id="54587-497">**Huella digital (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="54587-497">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="54587-498">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-498"></span></span>|
|<span data-ttu-id="54587-499">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="54587-499">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="54587-500">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-500"></span></span>|
|<span data-ttu-id="54587-501">**Direcciones URL CRL**</span><span class="sxs-lookup"><span data-stu-id="54587-501">**CRL URLs**</span></span>|
|<span data-ttu-id="54587-502">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-502"></span></span>|
|<span data-ttu-id="54587-503">**Direcciones URL OCSP**</span><span class="sxs-lookup"><span data-stu-id="54587-503">**OCSP URLs**</span></span>|
|<span data-ttu-id="54587-504">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-504"></span></span>|
   
 <span data-ttu-id="54587-505">**Entidad de certificación de confianza de D SSL clase 3 1 EV 2009**</span><span class="sxs-lookup"><span data-stu-id="54587-505">**D-TRUST SSL Class 3 CA 1 EV 2009**</span></span>
  
||
|:-----|
|<span data-ttu-id="54587-506">**Asunto**</span><span class="sxs-lookup"><span data-stu-id="54587-506">**Subject**</span></span>|
|<span data-ttu-id="54587-507">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-507"></span></span>|
|<span data-ttu-id="54587-508">**Emisor**</span><span class="sxs-lookup"><span data-stu-id="54587-508">**Issuer**</span></span>|
|<span data-ttu-id="54587-509">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-509"></span></span>|
|<span data-ttu-id="54587-510">**Nombre alternativo del sujeto**</span><span class="sxs-lookup"><span data-stu-id="54587-510">**Subject Alternative Name**</span></span>|
|<span data-ttu-id="54587-511">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-511"></span></span>|
|<span data-ttu-id="54587-512">**Número de serie**</span><span class="sxs-lookup"><span data-stu-id="54587-512">**Serial Number**</span></span>|
|<span data-ttu-id="54587-513">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-513"></span></span>|
|<span data-ttu-id="54587-514">**Longitud de clave pública**</span><span class="sxs-lookup"><span data-stu-id="54587-514">**Public Key Length**</span></span>|
|<span data-ttu-id="54587-515">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-515"></span></span>|
|<span data-ttu-id="54587-516">**Algoritmo de firma**</span><span class="sxs-lookup"><span data-stu-id="54587-516">**Signature Algorithm**</span></span>|
|<span data-ttu-id="54587-517">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-517"></span></span>|
|<span data-ttu-id="54587-518">**Validez no antes**</span><span class="sxs-lookup"><span data-stu-id="54587-518">**Validity Not Before**</span></span>|
|<span data-ttu-id="54587-519">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-519"></span></span>|
|<span data-ttu-id="54587-520">**Validez no después**</span><span class="sxs-lookup"><span data-stu-id="54587-520">**Validity Not After**</span></span>|
|<span data-ttu-id="54587-521">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-521"></span></span>|
|<span data-ttu-id="54587-522">**Identificador de clave de asunto**</span><span class="sxs-lookup"><span data-stu-id="54587-522">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="54587-523">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-523"></span></span>|
|<span data-ttu-id="54587-524">**Identificador de clave de entidad de certificación**</span><span class="sxs-lookup"><span data-stu-id="54587-524">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="54587-525">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-525"></span></span>|
|<span data-ttu-id="54587-526">**Huella digital (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="54587-526">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="54587-527">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-527"></span></span>|
|<span data-ttu-id="54587-528">**Huella digital (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="54587-528">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="54587-529">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-529"></span></span>|
|<span data-ttu-id="54587-530">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="54587-530">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="54587-531">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-531"></span></span>|
|<span data-ttu-id="54587-532">**Direcciones URL CRL**</span><span class="sxs-lookup"><span data-stu-id="54587-532">**CRL URLs**</span></span>|
|<span data-ttu-id="54587-533">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-533"></span></span>|
|<span data-ttu-id="54587-534">**Direcciones URL OCSP**</span><span class="sxs-lookup"><span data-stu-id="54587-534">**OCSP URLs**</span></span>|
|<span data-ttu-id="54587-535">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-535"></span></span>|
   
 <span data-ttu-id="54587-536">**1 de la entidad emisora de certificados de servicios de nube de DigiCert**</span><span class="sxs-lookup"><span data-stu-id="54587-536">**DigiCert Cloud Services CA-1**</span></span>
  
||
|:-----|
|<span data-ttu-id="54587-537">**Asunto**</span><span class="sxs-lookup"><span data-stu-id="54587-537">**Subject**</span></span>|
|<span data-ttu-id="54587-538">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-538"></span></span>|
|<span data-ttu-id="54587-539">**Emisor**</span><span class="sxs-lookup"><span data-stu-id="54587-539">**Issuer**</span></span>|
|<span data-ttu-id="54587-540">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-540"></span></span>|
|<span data-ttu-id="54587-541">**Número de serie**</span><span class="sxs-lookup"><span data-stu-id="54587-541">**Serial Number**</span></span>|
|<span data-ttu-id="54587-542">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-542"></span></span>|
|<span data-ttu-id="54587-543">**Longitud de clave pública**</span><span class="sxs-lookup"><span data-stu-id="54587-543">**Public Key Length**</span></span>|
|<span data-ttu-id="54587-544">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-544"></span></span>|
|<span data-ttu-id="54587-545">**Algoritmo de firma**</span><span class="sxs-lookup"><span data-stu-id="54587-545">**Signature Algorithm**</span></span>|
|<span data-ttu-id="54587-546">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-546"></span></span>|
|<span data-ttu-id="54587-547">**Validez no antes**</span><span class="sxs-lookup"><span data-stu-id="54587-547">**Validity Not Before**</span></span>|
|<span data-ttu-id="54587-548">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-548"></span></span>|
|<span data-ttu-id="54587-549">**Validez no después**</span><span class="sxs-lookup"><span data-stu-id="54587-549">**Validity Not After**</span></span>|
|<span data-ttu-id="54587-550">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-550"></span></span>|
|<span data-ttu-id="54587-551">**Identificador de clave de asunto**</span><span class="sxs-lookup"><span data-stu-id="54587-551">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="54587-552">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-552"></span></span>|
|<span data-ttu-id="54587-553">**Identificador de clave de entidad de certificación**</span><span class="sxs-lookup"><span data-stu-id="54587-553">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="54587-554">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-554"></span></span>|
|<span data-ttu-id="54587-555">**Huella digital (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="54587-555">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="54587-556">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-556"></span></span>|
|<span data-ttu-id="54587-557">**Huella digital (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="54587-557">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="54587-558">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-558"></span></span>|
|<span data-ttu-id="54587-559">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="54587-559">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="54587-560">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-560"></span></span>|
|<span data-ttu-id="54587-561">**Direcciones URL CRL**</span><span class="sxs-lookup"><span data-stu-id="54587-561">**CRL URLs**</span></span>|
|<span data-ttu-id="54587-562">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-562"></span></span>|
|<span data-ttu-id="54587-563">**Direcciones URL OCSP**</span><span class="sxs-lookup"><span data-stu-id="54587-563">**OCSP URLs**</span></span>|
|<span data-ttu-id="54587-564">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-564"></span></span>|
   
 <span data-ttu-id="54587-565">**Servidor de seguridad alta DigiCert SHA2 entidad emisora de certificados**</span><span class="sxs-lookup"><span data-stu-id="54587-565">**DigiCert SHA2 High Assurance Server CA**</span></span>
  
||
|:-----|
|<span data-ttu-id="54587-566">**Asunto**</span><span class="sxs-lookup"><span data-stu-id="54587-566">**Subject**</span></span>|
|<span data-ttu-id="54587-567">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-567"></span></span>|
|<span data-ttu-id="54587-568">**Emisor**</span><span class="sxs-lookup"><span data-stu-id="54587-568">**Issuer**</span></span>|
|<span data-ttu-id="54587-569">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-569"></span></span>|
|<span data-ttu-id="54587-570">**Número de serie**</span><span class="sxs-lookup"><span data-stu-id="54587-570">**Serial Number**</span></span>|
|<span data-ttu-id="54587-571">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-571"></span></span>|
|<span data-ttu-id="54587-572">**Longitud de clave pública**</span><span class="sxs-lookup"><span data-stu-id="54587-572">**Public Key Length**</span></span>|
|<span data-ttu-id="54587-573">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-573"></span></span>|
|<span data-ttu-id="54587-574">**Algoritmo de firma**</span><span class="sxs-lookup"><span data-stu-id="54587-574">**Signature Algorithm**</span></span>|
|<span data-ttu-id="54587-575">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-575"></span></span>|
|<span data-ttu-id="54587-576">**Validez no antes**</span><span class="sxs-lookup"><span data-stu-id="54587-576">**Validity Not Before**</span></span>|
|<span data-ttu-id="54587-577">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-577"></span></span>|
|<span data-ttu-id="54587-578">**Validez no después**</span><span class="sxs-lookup"><span data-stu-id="54587-578">**Validity Not After**</span></span>|
|<span data-ttu-id="54587-579">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-579"></span></span>|
|<span data-ttu-id="54587-580">**Identificador de clave de asunto**</span><span class="sxs-lookup"><span data-stu-id="54587-580">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="54587-581">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-581"></span></span>|
|<span data-ttu-id="54587-582">**Identificador de clave de entidad de certificación**</span><span class="sxs-lookup"><span data-stu-id="54587-582">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="54587-583">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-583"></span></span>|
|<span data-ttu-id="54587-584">**Huella digital (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="54587-584">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="54587-585">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-585"></span></span>|
|<span data-ttu-id="54587-586">**Huella digital (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="54587-586">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="54587-587">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-587"></span></span>|
|<span data-ttu-id="54587-588">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="54587-588">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="54587-589">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-589"></span></span>|
|<span data-ttu-id="54587-590">**Direcciones URL CRL**</span><span class="sxs-lookup"><span data-stu-id="54587-590">**CRL URLs**</span></span>|
|<span data-ttu-id="54587-591">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-591"></span></span>|
|<span data-ttu-id="54587-592">**Direcciones URL OCSP**</span><span class="sxs-lookup"><span data-stu-id="54587-592">**OCSP URLs**</span></span>|
|<span data-ttu-id="54587-593">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-593"></span></span>|
   
 <span data-ttu-id="54587-594">**Servidor seguro DigiCert SHA2 entidad emisora de certificados**</span><span class="sxs-lookup"><span data-stu-id="54587-594">**DigiCert SHA2 Secure Server CA**</span></span>
  
||
|:-----|
|<span data-ttu-id="54587-595">**Asunto**</span><span class="sxs-lookup"><span data-stu-id="54587-595">**Subject**</span></span>|
|<span data-ttu-id="54587-596">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-596"></span></span>|
|<span data-ttu-id="54587-597">**Emisor**</span><span class="sxs-lookup"><span data-stu-id="54587-597">**Issuer**</span></span>|
|<span data-ttu-id="54587-598">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-598"></span></span>|
|<span data-ttu-id="54587-599">**Número de serie**</span><span class="sxs-lookup"><span data-stu-id="54587-599">**Serial Number**</span></span>|
|<span data-ttu-id="54587-600">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-600"></span></span>|
|<span data-ttu-id="54587-601">**Longitud de clave pública**</span><span class="sxs-lookup"><span data-stu-id="54587-601">**Public Key Length**</span></span>|
|<span data-ttu-id="54587-602">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-602"></span></span>|
|<span data-ttu-id="54587-603">**Algoritmo de firma**</span><span class="sxs-lookup"><span data-stu-id="54587-603">**Signature Algorithm**</span></span>|
|<span data-ttu-id="54587-604">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-604"></span></span>|
|<span data-ttu-id="54587-605">**Validez no antes**</span><span class="sxs-lookup"><span data-stu-id="54587-605">**Validity Not Before**</span></span>|
|<span data-ttu-id="54587-606">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-606"></span></span>|
|<span data-ttu-id="54587-607">**Validez no después**</span><span class="sxs-lookup"><span data-stu-id="54587-607">**Validity Not After**</span></span>|
|<span data-ttu-id="54587-608">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-608"></span></span>|
|<span data-ttu-id="54587-609">**Identificador de clave de asunto**</span><span class="sxs-lookup"><span data-stu-id="54587-609">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="54587-610">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-610"></span></span>|
|<span data-ttu-id="54587-611">**Identificador de clave de entidad de certificación**</span><span class="sxs-lookup"><span data-stu-id="54587-611">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="54587-612">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-612"></span></span>|
|<span data-ttu-id="54587-613">**Huella digital (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="54587-613">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="54587-614">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-614"></span></span>|
|<span data-ttu-id="54587-615">**Huella digital (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="54587-615">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="54587-616">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-616"></span></span>|
|<span data-ttu-id="54587-617">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="54587-617">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="54587-618">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-618"></span></span>|
|<span data-ttu-id="54587-619">**Direcciones URL CRL**</span><span class="sxs-lookup"><span data-stu-id="54587-619">**CRL URLs**</span></span>|
|<span data-ttu-id="54587-620">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-620"></span></span>|
|<span data-ttu-id="54587-621">**Direcciones URL OCSP**</span><span class="sxs-lookup"><span data-stu-id="54587-621">**OCSP URLs**</span></span>|
|<span data-ttu-id="54587-622">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-622"></span></span>|
   
 <span data-ttu-id="54587-623">**Entrust entidad de certificación - L1C**</span><span class="sxs-lookup"><span data-stu-id="54587-623">**Entrust Certification Authority - L1C**</span></span>
  
||
|:-----|
|<span data-ttu-id="54587-624">**Asunto**</span><span class="sxs-lookup"><span data-stu-id="54587-624">**Subject**</span></span>|
|<span data-ttu-id="54587-625">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-625"></span></span>|
|<span data-ttu-id="54587-626">**Emisor**</span><span class="sxs-lookup"><span data-stu-id="54587-626">**Issuer**</span></span>|
|<span data-ttu-id="54587-627">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-627"></span></span>|
|<span data-ttu-id="54587-628">**Número de serie**</span><span class="sxs-lookup"><span data-stu-id="54587-628">**Serial Number**</span></span>|
|<span data-ttu-id="54587-629">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-629"></span></span>|
|<span data-ttu-id="54587-630">**Longitud de clave pública**</span><span class="sxs-lookup"><span data-stu-id="54587-630">**Public Key Length**</span></span>|
|<span data-ttu-id="54587-631">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-631"></span></span>|
|<span data-ttu-id="54587-632">**Algoritmo de firma**</span><span class="sxs-lookup"><span data-stu-id="54587-632">**Signature Algorithm**</span></span>|
|<span data-ttu-id="54587-633">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-633"></span></span>|
|<span data-ttu-id="54587-634">**Validez no antes**</span><span class="sxs-lookup"><span data-stu-id="54587-634">**Validity Not Before**</span></span>|
|<span data-ttu-id="54587-635">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-635"></span></span>|
|<span data-ttu-id="54587-636">**Validez no después**</span><span class="sxs-lookup"><span data-stu-id="54587-636">**Validity Not After**</span></span>|
|<span data-ttu-id="54587-637">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-637"></span></span>|
|<span data-ttu-id="54587-638">**Identificador de clave de asunto**</span><span class="sxs-lookup"><span data-stu-id="54587-638">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="54587-639">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-639"></span></span>|
|<span data-ttu-id="54587-640">**Identificador de clave de entidad de certificación**</span><span class="sxs-lookup"><span data-stu-id="54587-640">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="54587-641">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-641"></span></span>|
|<span data-ttu-id="54587-642">**Huella digital (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="54587-642">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="54587-643">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-643"></span></span>|
|<span data-ttu-id="54587-644">**Huella digital (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="54587-644">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="54587-645">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-645"></span></span>|
|<span data-ttu-id="54587-646">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="54587-646">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="54587-647">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-647"></span></span>|
|<span data-ttu-id="54587-648">**Direcciones URL CRL**</span><span class="sxs-lookup"><span data-stu-id="54587-648">**CRL URLs**</span></span>|
|<span data-ttu-id="54587-649">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-649"></span></span>|
|<span data-ttu-id="54587-650">**Direcciones URL OCSP**</span><span class="sxs-lookup"><span data-stu-id="54587-650">**OCSP URLs**</span></span>|
|<span data-ttu-id="54587-651">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-651"></span></span>|
   
 <span data-ttu-id="54587-652">**Entrust entidad de certificación - L1K**</span><span class="sxs-lookup"><span data-stu-id="54587-652">**Entrust Certification Authority - L1K**</span></span>
  
||
|:-----|
|<span data-ttu-id="54587-653">**Asunto**</span><span class="sxs-lookup"><span data-stu-id="54587-653">**Subject**</span></span>|
|<span data-ttu-id="54587-654">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-654"></span></span>|
|<span data-ttu-id="54587-655">**Emisor**</span><span class="sxs-lookup"><span data-stu-id="54587-655">**Issuer**</span></span>|
|<span data-ttu-id="54587-656">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-656"></span></span>|
|<span data-ttu-id="54587-657">**Número de serie**</span><span class="sxs-lookup"><span data-stu-id="54587-657">**Serial Number**</span></span>|
|<span data-ttu-id="54587-658">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-658"></span></span>|
|<span data-ttu-id="54587-659">**Longitud de clave pública**</span><span class="sxs-lookup"><span data-stu-id="54587-659">**Public Key Length**</span></span>|
|<span data-ttu-id="54587-660">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-660"></span></span>|
|<span data-ttu-id="54587-661">**Algoritmo de firma**</span><span class="sxs-lookup"><span data-stu-id="54587-661">**Signature Algorithm**</span></span>|
|<span data-ttu-id="54587-662">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-662"></span></span>|
|<span data-ttu-id="54587-663">**Validez no antes**</span><span class="sxs-lookup"><span data-stu-id="54587-663">**Validity Not Before**</span></span>|
|<span data-ttu-id="54587-664">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-664"></span></span>|
|<span data-ttu-id="54587-665">**Validez no después**</span><span class="sxs-lookup"><span data-stu-id="54587-665">**Validity Not After**</span></span>|
|<span data-ttu-id="54587-666">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-666"></span></span>|
|<span data-ttu-id="54587-667">**Identificador de clave de asunto**</span><span class="sxs-lookup"><span data-stu-id="54587-667">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="54587-668">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-668"></span></span>|
|<span data-ttu-id="54587-669">**Identificador de clave de entidad de certificación**</span><span class="sxs-lookup"><span data-stu-id="54587-669">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="54587-670">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-670"></span></span>|
|<span data-ttu-id="54587-671">**Huella digital (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="54587-671">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="54587-672">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-672"></span></span>|
|<span data-ttu-id="54587-673">**Huella digital (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="54587-673">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="54587-674">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-674"></span></span>|
|<span data-ttu-id="54587-675">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="54587-675">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="54587-676">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-676"></span></span>|
|<span data-ttu-id="54587-677">**Direcciones URL CRL**</span><span class="sxs-lookup"><span data-stu-id="54587-677">**CRL URLs**</span></span>|
|<span data-ttu-id="54587-678">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-678"></span></span>|
|<span data-ttu-id="54587-679">**Direcciones URL OCSP**</span><span class="sxs-lookup"><span data-stu-id="54587-679">**OCSP URLs**</span></span>|
|<span data-ttu-id="54587-680">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-680"></span></span>|
   
 <span data-ttu-id="54587-681">**GlobalSign**</span><span class="sxs-lookup"><span data-stu-id="54587-681">**GlobalSign**</span></span>
  
||
|:-----|
|<span data-ttu-id="54587-682">**Asunto**</span><span class="sxs-lookup"><span data-stu-id="54587-682">**Subject**</span></span>|
|<span data-ttu-id="54587-683">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-683"></span></span>|
|<span data-ttu-id="54587-684">**Emisor**</span><span class="sxs-lookup"><span data-stu-id="54587-684">**Issuer**</span></span>|
|<span data-ttu-id="54587-685">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-685"></span></span>|
|<span data-ttu-id="54587-686">**Número de serie**</span><span class="sxs-lookup"><span data-stu-id="54587-686">**Serial Number**</span></span>|
|<span data-ttu-id="54587-687">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-687"></span></span>|
|<span data-ttu-id="54587-688">**Longitud de clave pública**</span><span class="sxs-lookup"><span data-stu-id="54587-688">**Public Key Length**</span></span>|
|<span data-ttu-id="54587-689">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-689"></span></span>|
|<span data-ttu-id="54587-690">**Algoritmo de firma**</span><span class="sxs-lookup"><span data-stu-id="54587-690">**Signature Algorithm**</span></span>|
|<span data-ttu-id="54587-691">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-691"></span></span>|
|<span data-ttu-id="54587-692">**Validez no antes**</span><span class="sxs-lookup"><span data-stu-id="54587-692">**Validity Not Before**</span></span>|
|<span data-ttu-id="54587-693">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-693"></span></span>|
|<span data-ttu-id="54587-694">**Validez no después**</span><span class="sxs-lookup"><span data-stu-id="54587-694">**Validity Not After**</span></span>|
|<span data-ttu-id="54587-695">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-695"></span></span>|
|<span data-ttu-id="54587-696">**Identificador de clave de asunto**</span><span class="sxs-lookup"><span data-stu-id="54587-696">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="54587-697">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-697"></span></span>|
|<span data-ttu-id="54587-698">**Identificador de clave de entidad de certificación**</span><span class="sxs-lookup"><span data-stu-id="54587-698">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="54587-699">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-699"></span></span>|
|<span data-ttu-id="54587-700">**Huella digital (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="54587-700">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="54587-701">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-701"></span></span>|
|<span data-ttu-id="54587-702">**Huella digital (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="54587-702">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="54587-703">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-703"></span></span>|
|<span data-ttu-id="54587-704">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="54587-704">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="54587-705">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-705"></span></span>|
|<span data-ttu-id="54587-706">**Direcciones URL CRL**</span><span class="sxs-lookup"><span data-stu-id="54587-706">**CRL URLs**</span></span>|
|<span data-ttu-id="54587-707">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-707"></span></span>|
|<span data-ttu-id="54587-708">**Direcciones URL OCSP**</span><span class="sxs-lookup"><span data-stu-id="54587-708">**OCSP URLs**</span></span>|
|<span data-ttu-id="54587-709">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-709"></span></span>|
   
 <span data-ttu-id="54587-710">**GlobalSign extendida Validation CA - SHA256 - G2**</span><span class="sxs-lookup"><span data-stu-id="54587-710">**GlobalSign Extended Validation CA - SHA256 - G2**</span></span>
  
||
|:-----|
|<span data-ttu-id="54587-711">**Asunto**</span><span class="sxs-lookup"><span data-stu-id="54587-711">**Subject**</span></span>|
|<span data-ttu-id="54587-712">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-712"></span></span>|
|<span data-ttu-id="54587-713">**Emisor**</span><span class="sxs-lookup"><span data-stu-id="54587-713">**Issuer**</span></span>|
|<span data-ttu-id="54587-714">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-714"></span></span>|
|<span data-ttu-id="54587-715">**Número de serie**</span><span class="sxs-lookup"><span data-stu-id="54587-715">**Serial Number**</span></span>|
|<span data-ttu-id="54587-716">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-716"></span></span>|
|<span data-ttu-id="54587-717">**Longitud de clave pública**</span><span class="sxs-lookup"><span data-stu-id="54587-717">**Public Key Length**</span></span>|
|<span data-ttu-id="54587-718">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-718"></span></span>|
|<span data-ttu-id="54587-719">**Algoritmo de firma**</span><span class="sxs-lookup"><span data-stu-id="54587-719">**Signature Algorithm**</span></span>|
|<span data-ttu-id="54587-720">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-720"></span></span>|
|<span data-ttu-id="54587-721">**Validez no antes**</span><span class="sxs-lookup"><span data-stu-id="54587-721">**Validity Not Before**</span></span>|
|<span data-ttu-id="54587-722">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-722"></span></span>|
|<span data-ttu-id="54587-723">**Validez no después**</span><span class="sxs-lookup"><span data-stu-id="54587-723">**Validity Not After**</span></span>|
|<span data-ttu-id="54587-724">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-724"></span></span>|
|<span data-ttu-id="54587-725">**Identificador de clave de asunto**</span><span class="sxs-lookup"><span data-stu-id="54587-725">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="54587-726">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-726"></span></span>|
|<span data-ttu-id="54587-727">**Identificador de clave de entidad de certificación**</span><span class="sxs-lookup"><span data-stu-id="54587-727">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="54587-728">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-728"></span></span>|
|<span data-ttu-id="54587-729">**Huella digital (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="54587-729">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="54587-730">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-730"></span></span>|
|<span data-ttu-id="54587-731">**Huella digital (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="54587-731">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="54587-732">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-732"></span></span>|
|<span data-ttu-id="54587-733">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="54587-733">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="54587-734">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-734"></span></span>|
|<span data-ttu-id="54587-735">**Direcciones URL CRL**</span><span class="sxs-lookup"><span data-stu-id="54587-735">**CRL URLs**</span></span>|
|<span data-ttu-id="54587-736">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-736"></span></span>|
|<span data-ttu-id="54587-737">**Direcciones URL OCSP**</span><span class="sxs-lookup"><span data-stu-id="54587-737">**OCSP URLs**</span></span>|
|<span data-ttu-id="54587-738">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-738"></span></span>|
   
 <span data-ttu-id="54587-739">**GlobalSign extendida Validation CA - SHA256 - G3**</span><span class="sxs-lookup"><span data-stu-id="54587-739">**GlobalSign Extended Validation CA - SHA256 - G3**</span></span>
  
||
|:-----|
|<span data-ttu-id="54587-740">**Asunto**</span><span class="sxs-lookup"><span data-stu-id="54587-740">**Subject**</span></span>|
|<span data-ttu-id="54587-741">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-741"></span></span>|
|<span data-ttu-id="54587-742">**Emisor**</span><span class="sxs-lookup"><span data-stu-id="54587-742">**Issuer**</span></span>|
|<span data-ttu-id="54587-743">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-743"></span></span>|
|<span data-ttu-id="54587-744">**Número de serie**</span><span class="sxs-lookup"><span data-stu-id="54587-744">**Serial Number**</span></span>|
|<span data-ttu-id="54587-745">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-745"></span></span>|
|<span data-ttu-id="54587-746">**Longitud de clave pública**</span><span class="sxs-lookup"><span data-stu-id="54587-746">**Public Key Length**</span></span>|
|<span data-ttu-id="54587-747">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-747"></span></span>|
|<span data-ttu-id="54587-748">**Algoritmo de firma**</span><span class="sxs-lookup"><span data-stu-id="54587-748">**Signature Algorithm**</span></span>|
|<span data-ttu-id="54587-749">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-749"></span></span>|
|<span data-ttu-id="54587-750">**Validez no antes**</span><span class="sxs-lookup"><span data-stu-id="54587-750">**Validity Not Before**</span></span>|
|<span data-ttu-id="54587-751">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-751"></span></span>|
|<span data-ttu-id="54587-752">**Validez no después**</span><span class="sxs-lookup"><span data-stu-id="54587-752">**Validity Not After**</span></span>|
|<span data-ttu-id="54587-753">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-753"></span></span>|
|<span data-ttu-id="54587-754">**Identificador de clave de asunto**</span><span class="sxs-lookup"><span data-stu-id="54587-754">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="54587-755">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-755"></span></span>|
|<span data-ttu-id="54587-756">**Identificador de clave de entidad de certificación**</span><span class="sxs-lookup"><span data-stu-id="54587-756">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="54587-757">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-757"></span></span>|
|<span data-ttu-id="54587-758">**Huella digital (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="54587-758">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="54587-759">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-759"></span></span>|
|<span data-ttu-id="54587-760">**Huella digital (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="54587-760">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="54587-761">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-761"></span></span>|
|<span data-ttu-id="54587-762">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="54587-762">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="54587-763">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-763"></span></span>|
|<span data-ttu-id="54587-764">**Direcciones URL CRL**</span><span class="sxs-lookup"><span data-stu-id="54587-764">**CRL URLs**</span></span>|
|<span data-ttu-id="54587-765">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-765"></span></span>|
|<span data-ttu-id="54587-766">**Direcciones URL OCSP**</span><span class="sxs-lookup"><span data-stu-id="54587-766">**OCSP URLs**</span></span>|
|<span data-ttu-id="54587-767">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-767"></span></span>|
   
 <span data-ttu-id="54587-768">**GlobalSign organización validación CA - SHA256 - G2**</span><span class="sxs-lookup"><span data-stu-id="54587-768">**GlobalSign Organization Validation CA - SHA256 - G2**</span></span>
  
||
|:-----|
|<span data-ttu-id="54587-769">**Asunto**</span><span class="sxs-lookup"><span data-stu-id="54587-769">**Subject**</span></span>|
|<span data-ttu-id="54587-770">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-770"></span></span>|
|<span data-ttu-id="54587-771">**Emisor**</span><span class="sxs-lookup"><span data-stu-id="54587-771">**Issuer**</span></span>|
|<span data-ttu-id="54587-772">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-772"></span></span>|
|<span data-ttu-id="54587-773">**Número de serie**</span><span class="sxs-lookup"><span data-stu-id="54587-773">**Serial Number**</span></span>|
|<span data-ttu-id="54587-774">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-774"></span></span>|
|<span data-ttu-id="54587-775">**Longitud de clave pública**</span><span class="sxs-lookup"><span data-stu-id="54587-775">**Public Key Length**</span></span>|
|<span data-ttu-id="54587-776">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-776"></span></span>|
|<span data-ttu-id="54587-777">**Algoritmo de firma**</span><span class="sxs-lookup"><span data-stu-id="54587-777">**Signature Algorithm**</span></span>|
|<span data-ttu-id="54587-778">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-778"></span></span>|
|<span data-ttu-id="54587-779">**Validez no antes**</span><span class="sxs-lookup"><span data-stu-id="54587-779">**Validity Not Before**</span></span>|
|<span data-ttu-id="54587-780">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-780"></span></span>|
|<span data-ttu-id="54587-781">**Validez no después**</span><span class="sxs-lookup"><span data-stu-id="54587-781">**Validity Not After**</span></span>|
|<span data-ttu-id="54587-782">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-782"></span></span>|
|<span data-ttu-id="54587-783">**Identificador de clave de asunto**</span><span class="sxs-lookup"><span data-stu-id="54587-783">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="54587-784">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-784"></span></span>|
|<span data-ttu-id="54587-785">**Identificador de clave de entidad de certificación**</span><span class="sxs-lookup"><span data-stu-id="54587-785">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="54587-786">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-786"></span></span>|
|<span data-ttu-id="54587-787">**Huella digital (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="54587-787">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="54587-788">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-788"></span></span>|
|<span data-ttu-id="54587-789">**Huella digital (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="54587-789">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="54587-790">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-790"></span></span>|
|<span data-ttu-id="54587-791">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="54587-791">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="54587-792">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-792"></span></span>|
|<span data-ttu-id="54587-793">**Direcciones URL CRL**</span><span class="sxs-lookup"><span data-stu-id="54587-793">**CRL URLs**</span></span>|
|<span data-ttu-id="54587-794">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-794"></span></span>|
|<span data-ttu-id="54587-795">**Direcciones URL OCSP**</span><span class="sxs-lookup"><span data-stu-id="54587-795">**OCSP URLs**</span></span>|
|<span data-ttu-id="54587-796">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-796"></span></span>|
   
 <span data-ttu-id="54587-797">**GlobalSign organización validación CA - SHA256 - G2**</span><span class="sxs-lookup"><span data-stu-id="54587-797">**GlobalSign Organization Validation CA - SHA256 - G2**</span></span>
  
||
|:-----|
|<span data-ttu-id="54587-798">**Asunto**</span><span class="sxs-lookup"><span data-stu-id="54587-798">**Subject**</span></span>|
|<span data-ttu-id="54587-799">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-799"></span></span>|
|<span data-ttu-id="54587-800">**Emisor**</span><span class="sxs-lookup"><span data-stu-id="54587-800">**Issuer**</span></span>|
|<span data-ttu-id="54587-801">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-801"></span></span>|
|<span data-ttu-id="54587-802">**Número de serie**</span><span class="sxs-lookup"><span data-stu-id="54587-802">**Serial Number**</span></span>|
|<span data-ttu-id="54587-803">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-803"></span></span>|
|<span data-ttu-id="54587-804">**Longitud de clave pública**</span><span class="sxs-lookup"><span data-stu-id="54587-804">**Public Key Length**</span></span>|
|<span data-ttu-id="54587-805">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-805"></span></span>|
|<span data-ttu-id="54587-806">**Algoritmo de firma**</span><span class="sxs-lookup"><span data-stu-id="54587-806">**Signature Algorithm**</span></span>|
|<span data-ttu-id="54587-807">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-807"></span></span>|
|<span data-ttu-id="54587-808">**Validez no antes**</span><span class="sxs-lookup"><span data-stu-id="54587-808">**Validity Not Before**</span></span>|
|<span data-ttu-id="54587-809">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-809"></span></span>|
|<span data-ttu-id="54587-810">**Validez no después**</span><span class="sxs-lookup"><span data-stu-id="54587-810">**Validity Not After**</span></span>|
|<span data-ttu-id="54587-811">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-811"></span></span>|
|<span data-ttu-id="54587-812">**Identificador de clave de asunto**</span><span class="sxs-lookup"><span data-stu-id="54587-812">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="54587-813">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-813"></span></span>|
|<span data-ttu-id="54587-814">**Identificador de clave de entidad de certificación**</span><span class="sxs-lookup"><span data-stu-id="54587-814">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="54587-815">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-815"></span></span>|
|<span data-ttu-id="54587-816">**Huella digital (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="54587-816">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="54587-817">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-817"></span></span>|
|<span data-ttu-id="54587-818">**Huella digital (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="54587-818">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="54587-819">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-819"></span></span>|
|<span data-ttu-id="54587-820">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="54587-820">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="54587-821">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-821"></span></span>|
|<span data-ttu-id="54587-822">**Direcciones URL CRL**</span><span class="sxs-lookup"><span data-stu-id="54587-822">**CRL URLs**</span></span>|
|<span data-ttu-id="54587-823">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-823"></span></span>|
|<span data-ttu-id="54587-824">**Direcciones URL OCSP**</span><span class="sxs-lookup"><span data-stu-id="54587-824">**OCSP URLs**</span></span>|
|<span data-ttu-id="54587-825">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-825"></span></span>|
   
 <span data-ttu-id="54587-826">**Vamos a cifrar autoridad X3**</span><span class="sxs-lookup"><span data-stu-id="54587-826">**Let's Encrypt Authority X3**</span></span>
  
||
|:-----|
|<span data-ttu-id="54587-827">**Asunto**</span><span class="sxs-lookup"><span data-stu-id="54587-827">**Subject**</span></span>|
|<span data-ttu-id="54587-828">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-828"></span></span>|
|<span data-ttu-id="54587-829">**Emisor**</span><span class="sxs-lookup"><span data-stu-id="54587-829">**Issuer**</span></span>|
|<span data-ttu-id="54587-830">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-830"></span></span>|
|<span data-ttu-id="54587-831">**Número de serie**</span><span class="sxs-lookup"><span data-stu-id="54587-831">**Serial Number**</span></span>|
|<span data-ttu-id="54587-832">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-832"></span></span>|
|<span data-ttu-id="54587-833">**Longitud de clave pública**</span><span class="sxs-lookup"><span data-stu-id="54587-833">**Public Key Length**</span></span>|
|<span data-ttu-id="54587-834">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-834"></span></span>|
|<span data-ttu-id="54587-835">**Algoritmo de firma**</span><span class="sxs-lookup"><span data-stu-id="54587-835">**Signature Algorithm**</span></span>|
|<span data-ttu-id="54587-836">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-836"></span></span>|
|<span data-ttu-id="54587-837">**Validez no antes**</span><span class="sxs-lookup"><span data-stu-id="54587-837">**Validity Not Before**</span></span>|
|<span data-ttu-id="54587-838">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-838"></span></span>|
|<span data-ttu-id="54587-839">**Validez no después**</span><span class="sxs-lookup"><span data-stu-id="54587-839">**Validity Not After**</span></span>|
|<span data-ttu-id="54587-840">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-840"></span></span>|
|<span data-ttu-id="54587-841">**Identificador de clave de asunto**</span><span class="sxs-lookup"><span data-stu-id="54587-841">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="54587-842">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-842"></span></span>|
|<span data-ttu-id="54587-843">**Identificador de clave de entidad de certificación**</span><span class="sxs-lookup"><span data-stu-id="54587-843">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="54587-844">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-844"></span></span>|
|<span data-ttu-id="54587-845">**Huella digital (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="54587-845">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="54587-846">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-846"></span></span>|
|<span data-ttu-id="54587-847">**Huella digital (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="54587-847">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="54587-848">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-848"></span></span>|
|<span data-ttu-id="54587-849">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="54587-849">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="54587-850">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-850"></span></span>|
|<span data-ttu-id="54587-851">**Direcciones URL AIA**</span><span class="sxs-lookup"><span data-stu-id="54587-851">**AIA URLs**</span></span>|
|<span data-ttu-id="54587-852">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-852"></span></span>|
|<span data-ttu-id="54587-853">**Direcciones URL CRL**</span><span class="sxs-lookup"><span data-stu-id="54587-853">**CRL URLs**</span></span>|
|<span data-ttu-id="54587-854">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-854"></span></span>|
|<span data-ttu-id="54587-855">**Direcciones URL OCSP**</span><span class="sxs-lookup"><span data-stu-id="54587-855">**OCSP URLs**</span></span>|
|<span data-ttu-id="54587-856">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-856"></span></span>|
   
 <span data-ttu-id="54587-857">**Microsoft IT SSL SHA2**</span><span class="sxs-lookup"><span data-stu-id="54587-857">**Microsoft IT SSL SHA2**</span></span>
  
||
|:-----|
|<span data-ttu-id="54587-858">**Asunto**</span><span class="sxs-lookup"><span data-stu-id="54587-858">**Subject**</span></span>|
|<span data-ttu-id="54587-859">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-859"></span></span>|
|<span data-ttu-id="54587-860">**Emisor**</span><span class="sxs-lookup"><span data-stu-id="54587-860">**Issuer**</span></span>|
|<span data-ttu-id="54587-861">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-861"></span></span>|
|<span data-ttu-id="54587-862">**Número de serie**</span><span class="sxs-lookup"><span data-stu-id="54587-862">**Serial Number**</span></span>|
|<span data-ttu-id="54587-863">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-863"></span></span>|
|<span data-ttu-id="54587-864">**Longitud de clave pública**</span><span class="sxs-lookup"><span data-stu-id="54587-864">**Public Key Length**</span></span>|
|<span data-ttu-id="54587-865">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-865"></span></span>|
|<span data-ttu-id="54587-866">**Algoritmo de firma**</span><span class="sxs-lookup"><span data-stu-id="54587-866">**Signature Algorithm**</span></span>|
|<span data-ttu-id="54587-867">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-867"></span></span>|
|<span data-ttu-id="54587-868">**Validez no antes**</span><span class="sxs-lookup"><span data-stu-id="54587-868">**Validity Not Before**</span></span>|
|<span data-ttu-id="54587-869">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-869"></span></span>|
|<span data-ttu-id="54587-870">**Validez no después**</span><span class="sxs-lookup"><span data-stu-id="54587-870">**Validity Not After**</span></span>|
|<span data-ttu-id="54587-871">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-871"></span></span>|
|<span data-ttu-id="54587-872">**Identificador de clave de asunto**</span><span class="sxs-lookup"><span data-stu-id="54587-872">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="54587-873">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-873"></span></span>|
|<span data-ttu-id="54587-874">**Identificador de clave de entidad de certificación**</span><span class="sxs-lookup"><span data-stu-id="54587-874">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="54587-875">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-875"></span></span>|
|<span data-ttu-id="54587-876">**Huella digital (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="54587-876">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="54587-877">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-877"></span></span>|
|<span data-ttu-id="54587-878">**Huella digital (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="54587-878">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="54587-879">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-879"></span></span>|
|<span data-ttu-id="54587-880">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="54587-880">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="54587-881">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-881"></span></span>|
|<span data-ttu-id="54587-882">**Direcciones URL CRL**</span><span class="sxs-lookup"><span data-stu-id="54587-882">**CRL URLs**</span></span>|
|<span data-ttu-id="54587-883">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-883"></span></span>|
   
 <span data-ttu-id="54587-884">**Microsoft IT SSL SHA2**</span><span class="sxs-lookup"><span data-stu-id="54587-884">**Microsoft IT SSL SHA2**</span></span>
  
||
|:-----|
|<span data-ttu-id="54587-885">**Asunto**</span><span class="sxs-lookup"><span data-stu-id="54587-885">**Subject**</span></span>|
|<span data-ttu-id="54587-886">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-886"></span></span>|
|<span data-ttu-id="54587-887">**Emisor**</span><span class="sxs-lookup"><span data-stu-id="54587-887">**Issuer**</span></span>|
|<span data-ttu-id="54587-888">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-888"></span></span>|
|<span data-ttu-id="54587-889">**Número de serie**</span><span class="sxs-lookup"><span data-stu-id="54587-889">**Serial Number**</span></span>|
|<span data-ttu-id="54587-890">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-890"></span></span>|
|<span data-ttu-id="54587-891">**Longitud de clave pública**</span><span class="sxs-lookup"><span data-stu-id="54587-891">**Public Key Length**</span></span>|
|<span data-ttu-id="54587-892">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-892"></span></span>|
|<span data-ttu-id="54587-893">**Algoritmo de firma**</span><span class="sxs-lookup"><span data-stu-id="54587-893">**Signature Algorithm**</span></span>|
|<span data-ttu-id="54587-894">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-894"></span></span>|
|<span data-ttu-id="54587-895">**Validez no antes**</span><span class="sxs-lookup"><span data-stu-id="54587-895">**Validity Not Before**</span></span>|
|<span data-ttu-id="54587-896">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-896"></span></span>|
|<span data-ttu-id="54587-897">**Validez no después**</span><span class="sxs-lookup"><span data-stu-id="54587-897">**Validity Not After**</span></span>|
|<span data-ttu-id="54587-898">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-898"></span></span>|
|<span data-ttu-id="54587-899">**Identificador de clave de asunto**</span><span class="sxs-lookup"><span data-stu-id="54587-899">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="54587-900">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-900"></span></span>|
|<span data-ttu-id="54587-901">**Identificador de clave de entidad de certificación**</span><span class="sxs-lookup"><span data-stu-id="54587-901">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="54587-902">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-902"></span></span>|
|<span data-ttu-id="54587-903">**Huella digital (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="54587-903">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="54587-904">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-904"></span></span>|
|<span data-ttu-id="54587-905">**Huella digital (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="54587-905">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="54587-906">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-906"></span></span>|
|<span data-ttu-id="54587-907">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="54587-907">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="54587-908">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-908"></span></span>|
|<span data-ttu-id="54587-909">**Direcciones URL CRL**</span><span class="sxs-lookup"><span data-stu-id="54587-909">**CRL URLs**</span></span>|
|<span data-ttu-id="54587-910">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-910"></span></span>|
|<span data-ttu-id="54587-911">**Direcciones URL OCSP**</span><span class="sxs-lookup"><span data-stu-id="54587-911">**OCSP URLs**</span></span>|
|<span data-ttu-id="54587-912">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-912"></span></span>|
   
 <span data-ttu-id="54587-913">**Entidad de certificación de Microsoft IT TLS 1**</span><span class="sxs-lookup"><span data-stu-id="54587-913">**Microsoft IT TLS CA 1**</span></span>
  
||
|:-----|
|<span data-ttu-id="54587-914">**Asunto**</span><span class="sxs-lookup"><span data-stu-id="54587-914">**Subject**</span></span>|
|<span data-ttu-id="54587-915">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-915"></span></span>|
|<span data-ttu-id="54587-916">**Emisor**</span><span class="sxs-lookup"><span data-stu-id="54587-916">**Issuer**</span></span>|
|<span data-ttu-id="54587-917">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-917"></span></span>|
|<span data-ttu-id="54587-918">**Número de serie**</span><span class="sxs-lookup"><span data-stu-id="54587-918">**Serial Number**</span></span>|
|<span data-ttu-id="54587-919">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-919"></span></span>|
|<span data-ttu-id="54587-920">**Longitud de clave pública**</span><span class="sxs-lookup"><span data-stu-id="54587-920">**Public Key Length**</span></span>|
|<span data-ttu-id="54587-921">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-921"></span></span>|
|<span data-ttu-id="54587-922">**Algoritmo de firma**</span><span class="sxs-lookup"><span data-stu-id="54587-922">**Signature Algorithm**</span></span>|
|<span data-ttu-id="54587-923">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-923"></span></span>|
|<span data-ttu-id="54587-924">**Validez no antes**</span><span class="sxs-lookup"><span data-stu-id="54587-924">**Validity Not Before**</span></span>|
|<span data-ttu-id="54587-925">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-925"></span></span>|
|<span data-ttu-id="54587-926">**Validez no después**</span><span class="sxs-lookup"><span data-stu-id="54587-926">**Validity Not After**</span></span>|
|<span data-ttu-id="54587-927">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-927"></span></span>|
|<span data-ttu-id="54587-928">**Identificador de clave de asunto**</span><span class="sxs-lookup"><span data-stu-id="54587-928">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="54587-929">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-929"></span></span>|
|<span data-ttu-id="54587-930">**Identificador de clave de entidad de certificación**</span><span class="sxs-lookup"><span data-stu-id="54587-930">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="54587-931">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-931"></span></span>|
|<span data-ttu-id="54587-932">**Huella digital (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="54587-932">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="54587-933">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-933"></span></span>|
|<span data-ttu-id="54587-934">**Huella digital (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="54587-934">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="54587-935">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-935"></span></span>|
|<span data-ttu-id="54587-936">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="54587-936">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="54587-937">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-937"></span></span>|
|<span data-ttu-id="54587-938">**Direcciones URL CRL**</span><span class="sxs-lookup"><span data-stu-id="54587-938">**CRL URLs**</span></span>|
|<span data-ttu-id="54587-939">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-939"></span></span>|
|<span data-ttu-id="54587-940">**Direcciones URL OCSP**</span><span class="sxs-lookup"><span data-stu-id="54587-940">**OCSP URLs**</span></span>|
|<span data-ttu-id="54587-941">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-941"></span></span>|
   
 <span data-ttu-id="54587-942">**Entidad de certificación de Microsoft IT TLS 2**</span><span class="sxs-lookup"><span data-stu-id="54587-942">**Microsoft IT TLS CA 2**</span></span>
  
||
|:-----|
|<span data-ttu-id="54587-943">**Asunto**</span><span class="sxs-lookup"><span data-stu-id="54587-943">**Subject**</span></span>|
|<span data-ttu-id="54587-944">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-944"></span></span>|
|<span data-ttu-id="54587-945">**Emisor**</span><span class="sxs-lookup"><span data-stu-id="54587-945">**Issuer**</span></span>|
|<span data-ttu-id="54587-946">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-946"></span></span>|
|<span data-ttu-id="54587-947">**Número de serie**</span><span class="sxs-lookup"><span data-stu-id="54587-947">**Serial Number**</span></span>|
|<span data-ttu-id="54587-948">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-948"></span></span>|
|<span data-ttu-id="54587-949">**Longitud de clave pública**</span><span class="sxs-lookup"><span data-stu-id="54587-949">**Public Key Length**</span></span>|
|<span data-ttu-id="54587-950">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-950"></span></span>|
|<span data-ttu-id="54587-951">**Algoritmo de firma**</span><span class="sxs-lookup"><span data-stu-id="54587-951">**Signature Algorithm**</span></span>|
|<span data-ttu-id="54587-952">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-952"></span></span>|
|<span data-ttu-id="54587-953">**Validez no antes**</span><span class="sxs-lookup"><span data-stu-id="54587-953">**Validity Not Before**</span></span>|
|<span data-ttu-id="54587-954">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-954"></span></span>|
|<span data-ttu-id="54587-955">**Validez no después**</span><span class="sxs-lookup"><span data-stu-id="54587-955">**Validity Not After**</span></span>|
|<span data-ttu-id="54587-956">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-956"></span></span>|
|<span data-ttu-id="54587-957">**Identificador de clave de asunto**</span><span class="sxs-lookup"><span data-stu-id="54587-957">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="54587-958">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-958"></span></span>|
|<span data-ttu-id="54587-959">**Identificador de clave de entidad de certificación**</span><span class="sxs-lookup"><span data-stu-id="54587-959">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="54587-960">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-960"></span></span>|
|<span data-ttu-id="54587-961">**Huella digital (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="54587-961">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="54587-962">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-962"></span></span>|
|<span data-ttu-id="54587-963">**Huella digital (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="54587-963">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="54587-964">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-964"></span></span>|
|<span data-ttu-id="54587-965">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="54587-965">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="54587-966">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-966"></span></span>|
|<span data-ttu-id="54587-967">**Direcciones URL CRL**</span><span class="sxs-lookup"><span data-stu-id="54587-967">**CRL URLs**</span></span>|
|<span data-ttu-id="54587-968">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-968"></span></span>|
|<span data-ttu-id="54587-969">**Direcciones URL OCSP**</span><span class="sxs-lookup"><span data-stu-id="54587-969">**OCSP URLs**</span></span>|
|<span data-ttu-id="54587-970">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-970"></span></span>|
   
 <span data-ttu-id="54587-971">**Entidad de certificación de Microsoft IT TLS 4**</span><span class="sxs-lookup"><span data-stu-id="54587-971">**Microsoft IT TLS CA 4**</span></span>
  
||
|:-----|
|<span data-ttu-id="54587-972">**Asunto**</span><span class="sxs-lookup"><span data-stu-id="54587-972">**Subject**</span></span>|
|<span data-ttu-id="54587-973">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-973"></span></span>|
|<span data-ttu-id="54587-974">**Emisor**</span><span class="sxs-lookup"><span data-stu-id="54587-974">**Issuer**</span></span>|
|<span data-ttu-id="54587-975">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-975"></span></span>|
|<span data-ttu-id="54587-976">**Número de serie**</span><span class="sxs-lookup"><span data-stu-id="54587-976">**Serial Number**</span></span>|
|<span data-ttu-id="54587-977">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-977"></span></span>|
|<span data-ttu-id="54587-978">**Longitud de clave pública**</span><span class="sxs-lookup"><span data-stu-id="54587-978">**Public Key Length**</span></span>|
|<span data-ttu-id="54587-979">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-979"></span></span>|
|<span data-ttu-id="54587-980">**Algoritmo de firma**</span><span class="sxs-lookup"><span data-stu-id="54587-980">**Signature Algorithm**</span></span>|
|<span data-ttu-id="54587-981">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-981"></span></span>|
|<span data-ttu-id="54587-982">**Validez no antes**</span><span class="sxs-lookup"><span data-stu-id="54587-982">**Validity Not Before**</span></span>|
|<span data-ttu-id="54587-983">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-983"></span></span>|
|<span data-ttu-id="54587-984">**Validez no después**</span><span class="sxs-lookup"><span data-stu-id="54587-984">**Validity Not After**</span></span>|
|<span data-ttu-id="54587-985">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-985"></span></span>|
|<span data-ttu-id="54587-986">**Identificador de clave de asunto**</span><span class="sxs-lookup"><span data-stu-id="54587-986">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="54587-987">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-987"></span></span>|
|<span data-ttu-id="54587-988">**Identificador de clave de entidad de certificación**</span><span class="sxs-lookup"><span data-stu-id="54587-988">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="54587-989">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-989"></span></span>|
|<span data-ttu-id="54587-990">**Huella digital (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="54587-990">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="54587-991">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-991"></span></span>|
|<span data-ttu-id="54587-992">**Huella digital (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="54587-992">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="54587-993">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-993"></span></span>|
|<span data-ttu-id="54587-994">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="54587-994">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="54587-995">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-995"></span></span>|
|<span data-ttu-id="54587-996">**Direcciones URL CRL**</span><span class="sxs-lookup"><span data-stu-id="54587-996">**CRL URLs**</span></span>|
|<span data-ttu-id="54587-997">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-997"></span></span>|
|<span data-ttu-id="54587-998">**Direcciones URL OCSP**</span><span class="sxs-lookup"><span data-stu-id="54587-998">**OCSP URLs**</span></span>|
|<span data-ttu-id="54587-999">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-999"></span></span>|
   
 <span data-ttu-id="54587-1000">**Entidad de certificación de Microsoft IT TLS 5**</span><span class="sxs-lookup"><span data-stu-id="54587-1000">**Microsoft IT TLS CA 5**</span></span>
  
||
|:-----|
|<span data-ttu-id="54587-1001">**Asunto**</span><span class="sxs-lookup"><span data-stu-id="54587-1001">**Subject**</span></span>|
|<span data-ttu-id="54587-1002">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-1002"></span></span>|
|<span data-ttu-id="54587-1003">**Emisor**</span><span class="sxs-lookup"><span data-stu-id="54587-1003">**Issuer**</span></span>|
|<span data-ttu-id="54587-1004">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-1004"></span></span>|
|<span data-ttu-id="54587-1005">**Número de serie**</span><span class="sxs-lookup"><span data-stu-id="54587-1005">**Serial Number**</span></span>|
|<span data-ttu-id="54587-1006">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-1006"></span></span>|
|<span data-ttu-id="54587-1007">**Longitud de clave pública**</span><span class="sxs-lookup"><span data-stu-id="54587-1007">**Public Key Length**</span></span>|
|<span data-ttu-id="54587-1008">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-1008"></span></span>|
|<span data-ttu-id="54587-1009">**Algoritmo de firma**</span><span class="sxs-lookup"><span data-stu-id="54587-1009">**Signature Algorithm**</span></span>|
|<span data-ttu-id="54587-1010">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-1010"></span></span>|
|<span data-ttu-id="54587-1011">**Validez no antes**</span><span class="sxs-lookup"><span data-stu-id="54587-1011">**Validity Not Before**</span></span>|
|<span data-ttu-id="54587-1012">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-1012"></span></span>|
|<span data-ttu-id="54587-1013">**Validez no después**</span><span class="sxs-lookup"><span data-stu-id="54587-1013">**Validity Not After**</span></span>|
|<span data-ttu-id="54587-1014">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-1014"></span></span>|
|<span data-ttu-id="54587-1015">**Identificador de clave de asunto**</span><span class="sxs-lookup"><span data-stu-id="54587-1015">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="54587-1016">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-1016"></span></span>|
|<span data-ttu-id="54587-1017">**Identificador de clave de entidad de certificación**</span><span class="sxs-lookup"><span data-stu-id="54587-1017">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="54587-1018">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-1018"></span></span>|
|<span data-ttu-id="54587-1019">**Huella digital (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="54587-1019">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="54587-1020">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-1020"></span></span>|
|<span data-ttu-id="54587-1021">**Huella digital (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="54587-1021">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="54587-1022">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-1022"></span></span>|
|<span data-ttu-id="54587-1023">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="54587-1023">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="54587-1024">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-1024"></span></span>|
|<span data-ttu-id="54587-1025">**Direcciones URL CRL**</span><span class="sxs-lookup"><span data-stu-id="54587-1025">**CRL URLs**</span></span>|
|<span data-ttu-id="54587-1026">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-1026"></span></span>|
|<span data-ttu-id="54587-1027">**Direcciones URL OCSP**</span><span class="sxs-lookup"><span data-stu-id="54587-1027">**OCSP URLs**</span></span>|
|<span data-ttu-id="54587-1028">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-1028"></span></span>|
   
 <span data-ttu-id="54587-1029">**Entidad de certificación de Symantec clase de 3 EV SSL - G3**</span><span class="sxs-lookup"><span data-stu-id="54587-1029">**Symantec Class 3 EV SSL CA - G3**</span></span>
  
||
|:-----|
|<span data-ttu-id="54587-1030">**Asunto**</span><span class="sxs-lookup"><span data-stu-id="54587-1030">**Subject**</span></span>|
|<span data-ttu-id="54587-1031">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-1031"></span></span>|
|<span data-ttu-id="54587-1032">**Emisor**</span><span class="sxs-lookup"><span data-stu-id="54587-1032">**Issuer**</span></span>|
|<span data-ttu-id="54587-1033">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-1033"></span></span>|
|<span data-ttu-id="54587-1034">**Nombre alternativo del sujeto**</span><span class="sxs-lookup"><span data-stu-id="54587-1034">**Subject Alternative Name**</span></span>|
|<span data-ttu-id="54587-1035">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-1035"></span></span>|
|<span data-ttu-id="54587-1036">**Número de serie**</span><span class="sxs-lookup"><span data-stu-id="54587-1036">**Serial Number**</span></span>|
|<span data-ttu-id="54587-1037">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-1037"></span></span>|
|<span data-ttu-id="54587-1038">**Longitud de clave pública**</span><span class="sxs-lookup"><span data-stu-id="54587-1038">**Public Key Length**</span></span>|
|<span data-ttu-id="54587-1039">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-1039"></span></span>|
|<span data-ttu-id="54587-1040">**Algoritmo de firma**</span><span class="sxs-lookup"><span data-stu-id="54587-1040">**Signature Algorithm**</span></span>|
|<span data-ttu-id="54587-1041">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-1041"></span></span>|
|<span data-ttu-id="54587-1042">**Validez no antes**</span><span class="sxs-lookup"><span data-stu-id="54587-1042">**Validity Not Before**</span></span>|
|<span data-ttu-id="54587-1043">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-1043"></span></span>|
|<span data-ttu-id="54587-1044">**Validez no después**</span><span class="sxs-lookup"><span data-stu-id="54587-1044">**Validity Not After**</span></span>|
|<span data-ttu-id="54587-1045">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-1045"></span></span>|
|<span data-ttu-id="54587-1046">**Identificador de clave de asunto**</span><span class="sxs-lookup"><span data-stu-id="54587-1046">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="54587-1047">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-1047"></span></span>|
|<span data-ttu-id="54587-1048">**Identificador de clave de entidad de certificación**</span><span class="sxs-lookup"><span data-stu-id="54587-1048">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="54587-1049">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-1049"></span></span>|
|<span data-ttu-id="54587-1050">**Huella digital (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="54587-1050">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="54587-1051">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-1051"></span></span>|
|<span data-ttu-id="54587-1052">**Huella digital (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="54587-1052">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="54587-1053">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-1053"></span></span>|
|<span data-ttu-id="54587-1054">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="54587-1054">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="54587-1055">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-1055"></span></span>|
|<span data-ttu-id="54587-1056">**Direcciones URL CRL**</span><span class="sxs-lookup"><span data-stu-id="54587-1056">**CRL URLs**</span></span>|
|<span data-ttu-id="54587-1057">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-1057"></span></span>|
|<span data-ttu-id="54587-1058">**Direcciones URL OCSP**</span><span class="sxs-lookup"><span data-stu-id="54587-1058">**OCSP URLs**</span></span>|
|<span data-ttu-id="54587-1059">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-1059"></span></span>|
   
 <span data-ttu-id="54587-1060">**Clase Symantec 3 servidores seguros CA - G4**</span><span class="sxs-lookup"><span data-stu-id="54587-1060">**Symantec Class 3 Secure Server CA - G4**</span></span>
  
||
|:-----|
|<span data-ttu-id="54587-1061">**Asunto**</span><span class="sxs-lookup"><span data-stu-id="54587-1061">**Subject**</span></span>|
|<span data-ttu-id="54587-1062">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-1062"></span></span>|
|<span data-ttu-id="54587-1063">**Emisor**</span><span class="sxs-lookup"><span data-stu-id="54587-1063">**Issuer**</span></span>|
|<span data-ttu-id="54587-1064">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-1064"></span></span>|
|<span data-ttu-id="54587-1065">**Nombre alternativo del sujeto**</span><span class="sxs-lookup"><span data-stu-id="54587-1065">**Subject Alternative Name**</span></span>|
|<span data-ttu-id="54587-1066">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-1066"></span></span>|
|<span data-ttu-id="54587-1067">**Número de serie**</span><span class="sxs-lookup"><span data-stu-id="54587-1067">**Serial Number**</span></span>|
|<span data-ttu-id="54587-1068">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-1068"></span></span>|
|<span data-ttu-id="54587-1069">**Longitud de clave pública**</span><span class="sxs-lookup"><span data-stu-id="54587-1069">**Public Key Length**</span></span>|
|<span data-ttu-id="54587-1070">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-1070"></span></span>|
|<span data-ttu-id="54587-1071">**Algoritmo de firma**</span><span class="sxs-lookup"><span data-stu-id="54587-1071">**Signature Algorithm**</span></span>|
|<span data-ttu-id="54587-1072">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-1072"></span></span>|
|<span data-ttu-id="54587-1073">**Validez no antes**</span><span class="sxs-lookup"><span data-stu-id="54587-1073">**Validity Not Before**</span></span>|
|<span data-ttu-id="54587-1074">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-1074"></span></span>|
|<span data-ttu-id="54587-1075">**Validez no después**</span><span class="sxs-lookup"><span data-stu-id="54587-1075">**Validity Not After**</span></span>|
|<span data-ttu-id="54587-1076">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-1076"></span></span>|
|<span data-ttu-id="54587-1077">**Identificador de clave de asunto**</span><span class="sxs-lookup"><span data-stu-id="54587-1077">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="54587-1078">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-1078"></span></span>|
|<span data-ttu-id="54587-1079">**Identificador de clave de entidad de certificación**</span><span class="sxs-lookup"><span data-stu-id="54587-1079">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="54587-1080">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-1080"></span></span>|
|<span data-ttu-id="54587-1081">**Huella digital (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="54587-1081">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="54587-1082">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-1082"></span></span>|
|<span data-ttu-id="54587-1083">**Huella digital (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="54587-1083">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="54587-1084">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-1084"></span></span>|
|<span data-ttu-id="54587-1085">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="54587-1085">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="54587-1086">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-1086"></span></span>|
|<span data-ttu-id="54587-1087">**Direcciones URL CRL**</span><span class="sxs-lookup"><span data-stu-id="54587-1087">**CRL URLs**</span></span>|
|<span data-ttu-id="54587-1088">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-1088"></span></span>|
|<span data-ttu-id="54587-1089">**Direcciones URL OCSP**</span><span class="sxs-lookup"><span data-stu-id="54587-1089">**OCSP URLs**</span></span>|
|<span data-ttu-id="54587-1090">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-1090"></span></span>|
   
 <span data-ttu-id="54587-1091">**Thawte SHA256 SSL entidad emisora de certificados**</span><span class="sxs-lookup"><span data-stu-id="54587-1091">**thawte SHA256 SSL CA**</span></span>
  
||
|:-----|
|<span data-ttu-id="54587-1092">**Asunto**</span><span class="sxs-lookup"><span data-stu-id="54587-1092">**Subject**</span></span>|
|<span data-ttu-id="54587-1093">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-1093"></span></span>|
|<span data-ttu-id="54587-1094">**Emisor**</span><span class="sxs-lookup"><span data-stu-id="54587-1094">**Issuer**</span></span>|
|<span data-ttu-id="54587-1095">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-1095"></span></span>|
|<span data-ttu-id="54587-1096">**Nombre alternativo del sujeto**</span><span class="sxs-lookup"><span data-stu-id="54587-1096">**Subject Alternative Name**</span></span>|
|<span data-ttu-id="54587-1097">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-1097"></span></span>|
|<span data-ttu-id="54587-1098">**Número de serie**</span><span class="sxs-lookup"><span data-stu-id="54587-1098">**Serial Number**</span></span>|
|<span data-ttu-id="54587-1099">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-1099"></span></span>|
|<span data-ttu-id="54587-1100">**Longitud de clave pública**</span><span class="sxs-lookup"><span data-stu-id="54587-1100">**Public Key Length**</span></span>|
|<span data-ttu-id="54587-1101">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-1101"></span></span>|
|<span data-ttu-id="54587-1102">**Algoritmo de firma**</span><span class="sxs-lookup"><span data-stu-id="54587-1102">**Signature Algorithm**</span></span>|
|<span data-ttu-id="54587-1103">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-1103"></span></span>|
|<span data-ttu-id="54587-1104">**Validez no antes**</span><span class="sxs-lookup"><span data-stu-id="54587-1104">**Validity Not Before**</span></span>|
|<span data-ttu-id="54587-1105">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-1105"></span></span>|
|<span data-ttu-id="54587-1106">**Validez no después**</span><span class="sxs-lookup"><span data-stu-id="54587-1106">**Validity Not After**</span></span>|
|<span data-ttu-id="54587-1107">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-1107"></span></span>|
|<span data-ttu-id="54587-1108">**Identificador de clave de asunto**</span><span class="sxs-lookup"><span data-stu-id="54587-1108">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="54587-1109">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-1109"></span></span>|
|<span data-ttu-id="54587-1110">**Identificador de clave de entidad de certificación**</span><span class="sxs-lookup"><span data-stu-id="54587-1110">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="54587-1111">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-1111"></span></span>|
|<span data-ttu-id="54587-1112">**Huella digital (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="54587-1112">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="54587-1113">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-1113"></span></span>|
|<span data-ttu-id="54587-1114">**Huella digital (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="54587-1114">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="54587-1115">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-1115"></span></span>|
|<span data-ttu-id="54587-1116">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="54587-1116">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="54587-1117">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-1117"></span></span>|
|<span data-ttu-id="54587-1118">**Direcciones URL CRL**</span><span class="sxs-lookup"><span data-stu-id="54587-1118">**CRL URLs**</span></span>|
|<span data-ttu-id="54587-1119">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-1119"></span></span>|
|<span data-ttu-id="54587-1120">**Direcciones URL OCSP**</span><span class="sxs-lookup"><span data-stu-id="54587-1120">**OCSP URLs**</span></span>|
|<span data-ttu-id="54587-1121">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-1121"></span></span>|
   
 <span data-ttu-id="54587-1122">**Entidad emisora de certificados SureServer de Verizon Akamai G14-SHA2**</span><span class="sxs-lookup"><span data-stu-id="54587-1122">**Verizon Akamai SureServer CA G14-SHA2**</span></span>
  
||
|:-----|
|<span data-ttu-id="54587-1123">**Asunto**</span><span class="sxs-lookup"><span data-stu-id="54587-1123">**Subject**</span></span>|
|<span data-ttu-id="54587-1124">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-1124"></span></span>|
|<span data-ttu-id="54587-1125">**Emisor**</span><span class="sxs-lookup"><span data-stu-id="54587-1125">**Issuer**</span></span>|
|<span data-ttu-id="54587-1126">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-1126"></span></span>|
|<span data-ttu-id="54587-1127">**Número de serie**</span><span class="sxs-lookup"><span data-stu-id="54587-1127">**Serial Number**</span></span>|
|<span data-ttu-id="54587-1128">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-1128"></span></span>|
|<span data-ttu-id="54587-1129">**Longitud de clave pública**</span><span class="sxs-lookup"><span data-stu-id="54587-1129">**Public Key Length**</span></span>|
|<span data-ttu-id="54587-1130">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-1130"></span></span>|
|<span data-ttu-id="54587-1131">**Algoritmo de firma**</span><span class="sxs-lookup"><span data-stu-id="54587-1131">**Signature Algorithm**</span></span>|
|<span data-ttu-id="54587-1132">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-1132"></span></span>|
|<span data-ttu-id="54587-1133">**Validez no antes**</span><span class="sxs-lookup"><span data-stu-id="54587-1133">**Validity Not Before**</span></span>|
|<span data-ttu-id="54587-1134">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-1134"></span></span>|
|<span data-ttu-id="54587-1135">**Validez no después**</span><span class="sxs-lookup"><span data-stu-id="54587-1135">**Validity Not After**</span></span>|
|<span data-ttu-id="54587-1136">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-1136"></span></span>|
|<span data-ttu-id="54587-1137">**Identificador de clave de asunto**</span><span class="sxs-lookup"><span data-stu-id="54587-1137">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="54587-1138">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-1138"></span></span>|
|<span data-ttu-id="54587-1139">**Identificador de clave de entidad de certificación**</span><span class="sxs-lookup"><span data-stu-id="54587-1139">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="54587-1140">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-1140"></span></span>|
|<span data-ttu-id="54587-1141">**Huella digital (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="54587-1141">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="54587-1142">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-1142"></span></span>|
|<span data-ttu-id="54587-1143">**Huella digital (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="54587-1143">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="54587-1144">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-1144"></span></span>|
|<span data-ttu-id="54587-1145">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="54587-1145">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="54587-1146">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-1146"></span></span>|
|<span data-ttu-id="54587-1147">**Direcciones URL AIA**</span><span class="sxs-lookup"><span data-stu-id="54587-1147">**AIA URLs**</span></span>|
|<span data-ttu-id="54587-1148">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-1148"></span></span>|
|<span data-ttu-id="54587-1149">**Direcciones URL CRL**</span><span class="sxs-lookup"><span data-stu-id="54587-1149">**CRL URLs**</span></span>|
|<span data-ttu-id="54587-1150">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-1150"></span></span>|
|<span data-ttu-id="54587-1151">**Direcciones URL OCSP**</span><span class="sxs-lookup"><span data-stu-id="54587-1151">**OCSP URLs**</span></span>|
|<span data-ttu-id="54587-1152">:-----</span><span class="sxs-lookup"><span data-stu-id="54587-1152"></span></span>|
   
## <a name="additional-certificate-paths"></a><span data-ttu-id="54587-1153">Rutas de acceso del certificado adicional</span><span class="sxs-lookup"><span data-stu-id="54587-1153">Additional certificate paths</span></span>
<span data-ttu-id="54587-1154"><a name="IntermediateCerts"> </a></span><span class="sxs-lookup"><span data-stu-id="54587-1154"></span></span>

<span data-ttu-id="54587-1155">El siguiente incluir certificados heredados que no se incluyen por encima y se combinarán con la lista de arriba a través del tiempo.</span><span class="sxs-lookup"><span data-stu-id="54587-1155">The following include legacy certificates that aren't included above and will be merged with the list above over time.</span></span>
  
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


