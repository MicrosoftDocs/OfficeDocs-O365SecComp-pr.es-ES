---
title: Cadenas de certificados de Office 365
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 6/26/2018
ms.audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
ROBOTS: NOINDEX, NOFOLLOW
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
ms.assetid: 0c03e6b3-e73f-4316-9e2b-bf4091ae96bb
description: Office 365 aprovecha un número de proveedores de certificado diferentes. A continuación describe la lista completa de certificados de raíz de Office 365 conocidos que pueden encontrar los clientes al obtener acceso a Office 365. Para obtener información acerca de los certificados debe instalar en su propia infraestructura, vea Plan for certificados SSL de terceros para Office 365. La siguiente información del certificado se aplica a todas las instancias de la nube en todo el mundo y nacionales de Office 365.
ms.openlocfilehash: 97e00833e57f8f6b7352650b0efdef51ddba77fa
ms.sourcegitcommit: 659b5f5b38ef7e838cdb44eaa38c18e48d922768
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2018
ms.locfileid: "25575364"
---
# <a name="office-365-certificate-chains"></a><span data-ttu-id="161f7-106">Cadenas de certificados de Office 365</span><span class="sxs-lookup"><span data-stu-id="161f7-106">Office 365 Certificate Chains</span></span>

<span data-ttu-id="161f7-p102">Office 365 aprovecha un número de proveedores de certificado diferentes. A continuación describe la lista completa de certificados de raíz de Office 365 conocidos que pueden encontrar los clientes al obtener acceso a Office 365. Para obtener información sobre los certificados que necesita instalar en su propia infraestructura, consulte [Plan para los certificados SSL de terceros para Office 365](https://support.office.com/article/b48cdf63-07e0-4cda-8c12-4871590f59ce). La siguiente información del certificado se aplica a todas las instancias de la nube en todo el mundo y nacionales de Office 365.</span><span class="sxs-lookup"><span data-stu-id="161f7-p102">Office 365 leverages a number of different certificate providers. The following describes the complete list of known Office 365 root certificates that customers may encounter when accessing Office 365. For information on the certificates you may need to install in your own infrastructure, see [Plan for third-party SSL certificates for Office 365](https://support.office.com/article/b48cdf63-07e0-4cda-8c12-4871590f59ce). The following certificate information applies to all worldwide and national cloud instances of Office 365.</span></span>
  

|<span data-ttu-id="161f7-111">**Tipo de certificado**</span><span class="sxs-lookup"><span data-stu-id="161f7-111">**Certificate type**</span></span>|<span data-ttu-id="161f7-112">**Descarga de P7b**</span><span class="sxs-lookup"><span data-stu-id="161f7-112">**P7b download**</span></span>|<span data-ttu-id="161f7-113">**Extremos CRL**</span><span class="sxs-lookup"><span data-stu-id="161f7-113">**CRL Endpoints**</span></span>|<span data-ttu-id="161f7-114">**Extremos OCSP**</span><span class="sxs-lookup"><span data-stu-id="161f7-114">**OCSP Endpoints**</span></span>|<span data-ttu-id="161f7-115">**Extremos AIA**</span><span class="sxs-lookup"><span data-stu-id="161f7-115">**AIA Endpoints**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|[<span data-ttu-id="161f7-116">Certificados raíz de confianza públicamente</span><span class="sxs-lookup"><span data-stu-id="161f7-116">Publicly Trusted Root Certificates</span></span>](https://support.office.com/article/0c03e6b3-e73f-4316-9e2b-bf4091ae96bb#rootcerts) <br/> |[<span data-ttu-id="161f7-117">Agrupación de certificado raíz de Office 365 (P7B)</span><span class="sxs-lookup"><span data-stu-id="161f7-117">Office 365 Root Certificate Bundle (P7B)</span></span>](http://download.microsoft.com/download/A/5/A/A5AE01F3-D19B-4A11-9407-801263CEF72C/O365_Root_Certs_20170321.p7b) <br/> |<span data-ttu-id="161f7-118">CRL.GlobalSign.NET</span><span class="sxs-lookup"><span data-stu-id="161f7-118">crl.globalsign.net</span></span>  <br/> <span data-ttu-id="161f7-119">www.d-Trust.NET</span><span class="sxs-lookup"><span data-stu-id="161f7-119">www.d-trust.net</span></span>  <br/> |<span data-ttu-id="161f7-120">N/D</span><span class="sxs-lookup"><span data-stu-id="161f7-120">N/A</span></span>  <br/> |<span data-ttu-id="161f7-121">N/D</span><span class="sxs-lookup"><span data-stu-id="161f7-121">N/A</span></span>  <br/> |
|[<span data-ttu-id="161f7-122">Los certificados intermedios de confianza públicamente</span><span class="sxs-lookup"><span data-stu-id="161f7-122">Publicly Trusted Intermediate Certificates</span></span>](https://support.office.com/article/0c03e6b3-e73f-4316-9e2b-bf4091ae96bb#IntermediateCerts) <br/> |[<span data-ttu-id="161f7-123">Agrupación de certificados intermedios de Office 365 (P7B)</span><span class="sxs-lookup"><span data-stu-id="161f7-123">Office 365 Intermediate Certificate Bundle (P7B)</span></span>](http://download.microsoft.com/download/4/D/5/4D5339A4-0A4A-46AB-AE52-B179DEDA4BEC/O365_Intermediate_Certs_20170321.p7b)  <br/> |<span data-ttu-id="161f7-124">cdp1.Public trust.com</span><span class="sxs-lookup"><span data-stu-id="161f7-124">cdp1.public-trust.com</span></span>  <br/> <span data-ttu-id="161f7-125">CRL.cnnic.CN</span><span class="sxs-lookup"><span data-stu-id="161f7-125">crl.cnnic.cn</span></span>  <br/> <span data-ttu-id="161f7-126">CRL.Entrust.NET</span><span class="sxs-lookup"><span data-stu-id="161f7-126">crl.entrust.net</span></span>  <br/> <span data-ttu-id="161f7-127">CRL.GlobalSign.com</span><span class="sxs-lookup"><span data-stu-id="161f7-127">crl.globalsign.com</span></span>  <br/> <span data-ttu-id="161f7-128">CRL.GlobalSign.NET</span><span class="sxs-lookup"><span data-stu-id="161f7-128">crl.globalsign.net</span></span>  <br/> <span data-ttu-id="161f7-129">CRL.identrust.com</span><span class="sxs-lookup"><span data-stu-id="161f7-129">crl.identrust.com</span></span>  <br/> <span data-ttu-id="161f7-130">CRL.Thawte.com</span><span class="sxs-lookup"><span data-stu-id="161f7-130">crl.thawte.com</span></span>  <br/> <span data-ttu-id="161f7-131">crl3.digicert.com</span><span class="sxs-lookup"><span data-stu-id="161f7-131">crl3.digicert.com</span></span>  <br/> <span data-ttu-id="161f7-132">crl4.digicert.com</span><span class="sxs-lookup"><span data-stu-id="161f7-132">crl4.digicert.com</span></span>  <br/> <span data-ttu-id="161f7-133">s1.symcb.com</span><span class="sxs-lookup"><span data-stu-id="161f7-133">s1.symcb.com</span></span>  <br/> <span data-ttu-id="161f7-134">www.d-Trust.NET</span><span class="sxs-lookup"><span data-stu-id="161f7-134">www.d-trust.net</span></span>  <br/> |<span data-ttu-id="161f7-135">isrg.trustid.OCSP.identrust.com</span><span class="sxs-lookup"><span data-stu-id="161f7-135">isrg.trustid.ocsp.identrust.com</span></span>  <br/> <span data-ttu-id="161f7-136">OCSP.digicert.com</span><span class="sxs-lookup"><span data-stu-id="161f7-136">ocsp.digicert.com</span></span>  <br/> <span data-ttu-id="161f7-137">OCSP.Entrust.NET</span><span class="sxs-lookup"><span data-stu-id="161f7-137">ocsp.entrust.net</span></span>  <br/> <span data-ttu-id="161f7-138">OCSP.GlobalSign.com</span><span class="sxs-lookup"><span data-stu-id="161f7-138">ocsp.globalsign.com</span></span>  <br/> <span data-ttu-id="161f7-139">OCSP.OmniRoot.com</span><span class="sxs-lookup"><span data-stu-id="161f7-139">ocsp.omniroot.com</span></span>  <br/> <span data-ttu-id="161f7-140">OCSP.startssl.com</span><span class="sxs-lookup"><span data-stu-id="161f7-140">ocsp.startssl.com</span></span>  <br/> <span data-ttu-id="161f7-141">OCSP.Thawte.com</span><span class="sxs-lookup"><span data-stu-id="161f7-141">ocsp.thawte.com</span></span>  <br/> <span data-ttu-id="161f7-142">ocsp2.GlobalSign.com</span><span class="sxs-lookup"><span data-stu-id="161f7-142">ocsp2.globalsign.com</span></span>  <br/> <span data-ttu-id="161f7-143">ocspcnnicroot.cnnic.CN</span><span class="sxs-lookup"><span data-stu-id="161f7-143">ocspcnnicroot.cnnic.cn</span></span>  <br/> <span data-ttu-id="161f7-144">raíz-c3-ca2-2009.ocsp.d-trust.net</span><span class="sxs-lookup"><span data-stu-id="161f7-144">root-c3-ca2-2009.ocsp.d-trust.net</span></span>  <br/> <span data-ttu-id="161f7-145">root-C3-cA2-EV-2009.OCSP.d-Trust.NET</span><span class="sxs-lookup"><span data-stu-id="161f7-145">root-c3-ca2-ev-2009.ocsp.d-trust.net</span></span>  <br/> <span data-ttu-id="161f7-146">s2.symcb.com</span><span class="sxs-lookup"><span data-stu-id="161f7-146">s2.symcb.com</span></span>  <br/> |<span data-ttu-id="161f7-147">AIA.startssl.com</span><span class="sxs-lookup"><span data-stu-id="161f7-147">aia.startssl.com</span></span>  <br/> <span data-ttu-id="161f7-148">Apps.identrust.com</span><span class="sxs-lookup"><span data-stu-id="161f7-148">apps.identrust.com</span></span>  <br/> <span data-ttu-id="161f7-149">CACert.OmniRoot.com</span><span class="sxs-lookup"><span data-stu-id="161f7-149">cacert.omniroot.com</span></span>  <br/> <span data-ttu-id="161f7-150">www.cnnic.CN</span><span class="sxs-lookup"><span data-stu-id="161f7-150">www.cnnic.cn</span></span>  <br/> |
   
<span data-ttu-id="161f7-151">Expanda la raíz y las secciones intermedias para ver detalles adicionales acerca de los proveedores de certificado.</span><span class="sxs-lookup"><span data-stu-id="161f7-151">Expand the root and intermediate sections below to see additional details about the certificate providers.</span></span>
  
## <a name="office-365-root-certificate-details"></a><span data-ttu-id="161f7-152">Detalles del certificado de raíz de Office 365</span><span class="sxs-lookup"><span data-stu-id="161f7-152">Office 365 Root Certificate Details</span></span>
<span data-ttu-id="161f7-153"><a name="RootCerts"> </a></span><span class="sxs-lookup"><span data-stu-id="161f7-153"></span></span>

 <span data-ttu-id="161f7-154">**Baltimore CyberTrust Root**</span><span class="sxs-lookup"><span data-stu-id="161f7-154">**Baltimore CyberTrust Root**</span></span>
  
<span data-ttu-id="161f7-155">|:-----|</span><span class="sxs-lookup"><span data-stu-id="161f7-155">|:-----|</span></span>
|<span data-ttu-id="161f7-156">**Asunto**</span><span class="sxs-lookup"><span data-stu-id="161f7-156">**Subject**</span></span>|
|:-----|
|<span data-ttu-id="161f7-157">**Número de serie**</span><span class="sxs-lookup"><span data-stu-id="161f7-157">**Serial Number**</span></span>|
|<span data-ttu-id="161f7-158">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-158"></span></span>|
|<span data-ttu-id="161f7-159">**Longitud de clave pública**</span><span class="sxs-lookup"><span data-stu-id="161f7-159">**Public Key Length**</span></span>|
|<span data-ttu-id="161f7-160">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-160"></span></span>|
|<span data-ttu-id="161f7-161">**Algoritmo de firma**</span><span class="sxs-lookup"><span data-stu-id="161f7-161">**Signature Algorithm**</span></span>|
|<span data-ttu-id="161f7-162">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-162"></span></span>|
|<span data-ttu-id="161f7-163">**Validez no antes**</span><span class="sxs-lookup"><span data-stu-id="161f7-163">**Validity Not Before**</span></span>|
|<span data-ttu-id="161f7-164">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-164"></span></span>|
|<span data-ttu-id="161f7-165">**Validez no después**</span><span class="sxs-lookup"><span data-stu-id="161f7-165">**Validity Not After**</span></span>|
|<span data-ttu-id="161f7-166">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-166"></span></span>|
|<span data-ttu-id="161f7-167">**Identificador de clave de asunto**</span><span class="sxs-lookup"><span data-stu-id="161f7-167">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="161f7-168">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-168"></span></span>|
|<span data-ttu-id="161f7-169">**Huella digital (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="161f7-169">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="161f7-170">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-170"></span></span>|
|<span data-ttu-id="161f7-171">**Huella digital (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="161f7-171">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="161f7-172">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-172"></span></span>|
|<span data-ttu-id="161f7-173">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="161f7-173">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="161f7-174">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-174"></span></span>|
   
 <span data-ttu-id="161f7-175">**RAÍZ DE CNNIC**</span><span class="sxs-lookup"><span data-stu-id="161f7-175">**CNNIC ROOT**</span></span>
  
||
|:-----|
|<span data-ttu-id="161f7-176">**Asunto**</span><span class="sxs-lookup"><span data-stu-id="161f7-176">**Subject**</span></span>|
|<span data-ttu-id="161f7-177">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-177"></span></span>|
|<span data-ttu-id="161f7-178">**Número de serie**</span><span class="sxs-lookup"><span data-stu-id="161f7-178">**Serial Number**</span></span>|
|<span data-ttu-id="161f7-179">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-179"></span></span>|
|<span data-ttu-id="161f7-180">**Longitud de clave pública**</span><span class="sxs-lookup"><span data-stu-id="161f7-180">**Public Key Length**</span></span>|
|<span data-ttu-id="161f7-181">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-181"></span></span>|
|<span data-ttu-id="161f7-182">**Algoritmo de firma**</span><span class="sxs-lookup"><span data-stu-id="161f7-182">**Signature Algorithm**</span></span>|
|<span data-ttu-id="161f7-183">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-183"></span></span>|
|<span data-ttu-id="161f7-184">**Validez no antes**</span><span class="sxs-lookup"><span data-stu-id="161f7-184">**Validity Not Before**</span></span>|
|<span data-ttu-id="161f7-185">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-185"></span></span>|
|<span data-ttu-id="161f7-186">**Validez no después**</span><span class="sxs-lookup"><span data-stu-id="161f7-186">**Validity Not After**</span></span>|
|<span data-ttu-id="161f7-187">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-187"></span></span>|
|<span data-ttu-id="161f7-188">**Identificador de clave de asunto**</span><span class="sxs-lookup"><span data-stu-id="161f7-188">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="161f7-189">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-189"></span></span>|
|<span data-ttu-id="161f7-190">**Identificador de clave de entidad de certificación**</span><span class="sxs-lookup"><span data-stu-id="161f7-190">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="161f7-191">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-191"></span></span>|
|<span data-ttu-id="161f7-192">**Huella digital (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="161f7-192">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="161f7-193">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-193"></span></span>|
|<span data-ttu-id="161f7-194">**Huella digital (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="161f7-194">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="161f7-195">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-195"></span></span>|
|<span data-ttu-id="161f7-196">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="161f7-196">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="161f7-197">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-197"></span></span>|
   
 <span data-ttu-id="161f7-198">**DigiCert de entidad de certificación raíz Global**</span><span class="sxs-lookup"><span data-stu-id="161f7-198">**DigiCert Global Root CA**</span></span>
  
||
|:-----|
|<span data-ttu-id="161f7-199">**Asunto**</span><span class="sxs-lookup"><span data-stu-id="161f7-199">**Subject**</span></span>|
|<span data-ttu-id="161f7-200">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-200"></span></span>|
|<span data-ttu-id="161f7-201">**Número de serie**</span><span class="sxs-lookup"><span data-stu-id="161f7-201">**Serial Number**</span></span>|
|<span data-ttu-id="161f7-202">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-202"></span></span>|
|<span data-ttu-id="161f7-203">**Longitud de clave pública**</span><span class="sxs-lookup"><span data-stu-id="161f7-203">**Public Key Length**</span></span>|
|<span data-ttu-id="161f7-204">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-204"></span></span>|
|<span data-ttu-id="161f7-205">**Algoritmo de firma**</span><span class="sxs-lookup"><span data-stu-id="161f7-205">**Signature Algorithm**</span></span>|
|<span data-ttu-id="161f7-206">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-206"></span></span>|
|<span data-ttu-id="161f7-207">**Validez no antes**</span><span class="sxs-lookup"><span data-stu-id="161f7-207">**Validity Not Before**</span></span>|
|<span data-ttu-id="161f7-208">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-208"></span></span>|
|<span data-ttu-id="161f7-209">**Validez no después**</span><span class="sxs-lookup"><span data-stu-id="161f7-209">**Validity Not After**</span></span>|
|<span data-ttu-id="161f7-210">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-210"></span></span>|
|<span data-ttu-id="161f7-211">**Identificador de clave de asunto**</span><span class="sxs-lookup"><span data-stu-id="161f7-211">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="161f7-212">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-212"></span></span>|
|<span data-ttu-id="161f7-213">**Identificador de clave de entidad de certificación**</span><span class="sxs-lookup"><span data-stu-id="161f7-213">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="161f7-214">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-214"></span></span>|
|<span data-ttu-id="161f7-215">**Huella digital (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="161f7-215">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="161f7-216">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-216"></span></span>|
|<span data-ttu-id="161f7-217">**Huella digital (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="161f7-217">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="161f7-218">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-218"></span></span>|
|<span data-ttu-id="161f7-219">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="161f7-219">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="161f7-220">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-220"></span></span>|
   
 <span data-ttu-id="161f7-221">**Entidad de certificación raíz de DigiCert High Assurance EV**</span><span class="sxs-lookup"><span data-stu-id="161f7-221">**DigiCert High Assurance EV Root CA**</span></span>
  
||
|:-----|
|<span data-ttu-id="161f7-222">**Asunto**</span><span class="sxs-lookup"><span data-stu-id="161f7-222">**Subject**</span></span>|
|<span data-ttu-id="161f7-223">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-223"></span></span>|
|<span data-ttu-id="161f7-224">**Número de serie**</span><span class="sxs-lookup"><span data-stu-id="161f7-224">**Serial Number**</span></span>|
|<span data-ttu-id="161f7-225">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-225"></span></span>|
|<span data-ttu-id="161f7-226">**Longitud de clave pública**</span><span class="sxs-lookup"><span data-stu-id="161f7-226">**Public Key Length**</span></span>|
|<span data-ttu-id="161f7-227">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-227"></span></span>|
|<span data-ttu-id="161f7-228">**Algoritmo de firma**</span><span class="sxs-lookup"><span data-stu-id="161f7-228">**Signature Algorithm**</span></span>|
|<span data-ttu-id="161f7-229">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-229"></span></span>|
|<span data-ttu-id="161f7-230">**Validez no antes**</span><span class="sxs-lookup"><span data-stu-id="161f7-230">**Validity Not Before**</span></span>|
|<span data-ttu-id="161f7-231">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-231"></span></span>|
|<span data-ttu-id="161f7-232">**Validez no después**</span><span class="sxs-lookup"><span data-stu-id="161f7-232">**Validity Not After**</span></span>|
|<span data-ttu-id="161f7-233">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-233"></span></span>|
|<span data-ttu-id="161f7-234">**Identificador de clave de asunto**</span><span class="sxs-lookup"><span data-stu-id="161f7-234">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="161f7-235">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-235"></span></span>|
|<span data-ttu-id="161f7-236">**Identificador de clave de entidad de certificación**</span><span class="sxs-lookup"><span data-stu-id="161f7-236">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="161f7-237">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-237"></span></span>|
|<span data-ttu-id="161f7-238">**Huella digital (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="161f7-238">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="161f7-239">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-239"></span></span>|
|<span data-ttu-id="161f7-240">**Huella digital (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="161f7-240">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="161f7-241">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-241"></span></span>|
|<span data-ttu-id="161f7-242">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="161f7-242">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="161f7-243">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-243"></span></span>|
   
 <span data-ttu-id="161f7-244">**Entidad de certificación de raíz de confianza de D clase 3 2 de 2009**</span><span class="sxs-lookup"><span data-stu-id="161f7-244">**D-TRUST Root Class 3 CA 2 2009**</span></span>
  
||
|:-----|
|<span data-ttu-id="161f7-245">**Asunto**</span><span class="sxs-lookup"><span data-stu-id="161f7-245">**Subject**</span></span>|
|<span data-ttu-id="161f7-246">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-246"></span></span>|
|<span data-ttu-id="161f7-247">**Número de serie**</span><span class="sxs-lookup"><span data-stu-id="161f7-247">**Serial Number**</span></span>|
|<span data-ttu-id="161f7-248">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-248"></span></span>|
|<span data-ttu-id="161f7-249">**Longitud de clave pública**</span><span class="sxs-lookup"><span data-stu-id="161f7-249">**Public Key Length**</span></span>|
|<span data-ttu-id="161f7-250">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-250"></span></span>|
|<span data-ttu-id="161f7-251">**Algoritmo de firma**</span><span class="sxs-lookup"><span data-stu-id="161f7-251">**Signature Algorithm**</span></span>|
|<span data-ttu-id="161f7-252">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-252"></span></span>|
|<span data-ttu-id="161f7-253">**Validez no antes**</span><span class="sxs-lookup"><span data-stu-id="161f7-253">**Validity Not Before**</span></span>|
|<span data-ttu-id="161f7-254">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-254"></span></span>|
|<span data-ttu-id="161f7-255">**Validez no después**</span><span class="sxs-lookup"><span data-stu-id="161f7-255">**Validity Not After**</span></span>|
|<span data-ttu-id="161f7-256">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-256"></span></span>|
|<span data-ttu-id="161f7-257">**Identificador de clave de asunto**</span><span class="sxs-lookup"><span data-stu-id="161f7-257">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="161f7-258">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-258"></span></span>|
|<span data-ttu-id="161f7-259">**Huella digital (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="161f7-259">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="161f7-260">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-260"></span></span>|
|<span data-ttu-id="161f7-261">**Huella digital (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="161f7-261">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="161f7-262">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-262"></span></span>|
|<span data-ttu-id="161f7-263">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="161f7-263">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="161f7-264">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-264"></span></span>|
|<span data-ttu-id="161f7-265">**Direcciones URL CRL**</span><span class="sxs-lookup"><span data-stu-id="161f7-265">**CRL URLs**</span></span>|
|<span data-ttu-id="161f7-266">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-266"></span></span>|
   
 <span data-ttu-id="161f7-267">**Entidad de certificación raíz de confianza de D clase 3 2 EV de 2009**</span><span class="sxs-lookup"><span data-stu-id="161f7-267">**D-TRUST Root Class 3 CA 2 EV 2009**</span></span>
  
||
|:-----|
|<span data-ttu-id="161f7-268">**Asunto**</span><span class="sxs-lookup"><span data-stu-id="161f7-268">**Subject**</span></span>|
|<span data-ttu-id="161f7-269">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-269"></span></span>|
|<span data-ttu-id="161f7-270">**Número de serie**</span><span class="sxs-lookup"><span data-stu-id="161f7-270">**Serial Number**</span></span>|
|<span data-ttu-id="161f7-271">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-271"></span></span>|
|<span data-ttu-id="161f7-272">**Longitud de clave pública**</span><span class="sxs-lookup"><span data-stu-id="161f7-272">**Public Key Length**</span></span>|
|<span data-ttu-id="161f7-273">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-273"></span></span>|
|<span data-ttu-id="161f7-274">**Algoritmo de firma**</span><span class="sxs-lookup"><span data-stu-id="161f7-274">**Signature Algorithm**</span></span>|
|<span data-ttu-id="161f7-275">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-275"></span></span>|
|<span data-ttu-id="161f7-276">**Validez no antes**</span><span class="sxs-lookup"><span data-stu-id="161f7-276">**Validity Not Before**</span></span>|
|<span data-ttu-id="161f7-277">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-277"></span></span>|
|<span data-ttu-id="161f7-278">**Validez no después**</span><span class="sxs-lookup"><span data-stu-id="161f7-278">**Validity Not After**</span></span>|
|<span data-ttu-id="161f7-279">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-279"></span></span>|
|<span data-ttu-id="161f7-280">**Identificador de clave de asunto**</span><span class="sxs-lookup"><span data-stu-id="161f7-280">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="161f7-281">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-281"></span></span>|
|<span data-ttu-id="161f7-282">**Huella digital (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="161f7-282">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="161f7-283">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-283"></span></span>|
|<span data-ttu-id="161f7-284">**Huella digital (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="161f7-284">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="161f7-285">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-285"></span></span>|
|<span data-ttu-id="161f7-286">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="161f7-286">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="161f7-287">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-287"></span></span>|
|<span data-ttu-id="161f7-288">**Direcciones URL CRL**</span><span class="sxs-lookup"><span data-stu-id="161f7-288">**CRL URLs**</span></span>|
|<span data-ttu-id="161f7-289">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-289"></span></span>|
   
 <span data-ttu-id="161f7-290">**X3 de la entidad de certificación de raíz de horario de verano**</span><span class="sxs-lookup"><span data-stu-id="161f7-290">**DST Root CA X3**</span></span>
  
||
|:-----|
|<span data-ttu-id="161f7-291">**Asunto**</span><span class="sxs-lookup"><span data-stu-id="161f7-291">**Subject**</span></span>|
|<span data-ttu-id="161f7-292">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-292"></span></span>|
|<span data-ttu-id="161f7-293">**Número de serie**</span><span class="sxs-lookup"><span data-stu-id="161f7-293">**Serial Number**</span></span>|
|<span data-ttu-id="161f7-294">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-294"></span></span>|
|<span data-ttu-id="161f7-295">**Longitud de clave pública**</span><span class="sxs-lookup"><span data-stu-id="161f7-295">**Public Key Length**</span></span>|
|<span data-ttu-id="161f7-296">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-296"></span></span>|
|<span data-ttu-id="161f7-297">**Algoritmo de firma**</span><span class="sxs-lookup"><span data-stu-id="161f7-297">**Signature Algorithm**</span></span>|
|<span data-ttu-id="161f7-298">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-298"></span></span>|
|<span data-ttu-id="161f7-299">**Validez no antes**</span><span class="sxs-lookup"><span data-stu-id="161f7-299">**Validity Not Before**</span></span>|
|<span data-ttu-id="161f7-300">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-300"></span></span>|
|<span data-ttu-id="161f7-301">**Validez no después**</span><span class="sxs-lookup"><span data-stu-id="161f7-301">**Validity Not After**</span></span>|
|<span data-ttu-id="161f7-302">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-302"></span></span>|
|<span data-ttu-id="161f7-303">**Identificador de clave de asunto**</span><span class="sxs-lookup"><span data-stu-id="161f7-303">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="161f7-304">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-304"></span></span>|
|<span data-ttu-id="161f7-305">**Huella digital (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="161f7-305">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="161f7-306">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-306"></span></span>|
|<span data-ttu-id="161f7-307">**Huella digital (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="161f7-307">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="161f7-308">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-308"></span></span>|
|<span data-ttu-id="161f7-309">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="161f7-309">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="161f7-310">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-310"></span></span>|
   
 <span data-ttu-id="161f7-311">**Entrust entidad de certificación raíz - G2**</span><span class="sxs-lookup"><span data-stu-id="161f7-311">**Entrust Root Certification Authority - G2**</span></span>
  
||
|:-----|
|<span data-ttu-id="161f7-312">**Asunto**</span><span class="sxs-lookup"><span data-stu-id="161f7-312">**Subject**</span></span>|
|<span data-ttu-id="161f7-313">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-313"></span></span>|
|<span data-ttu-id="161f7-314">**Número de serie**</span><span class="sxs-lookup"><span data-stu-id="161f7-314">**Serial Number**</span></span>|
|<span data-ttu-id="161f7-315">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-315"></span></span>|
|<span data-ttu-id="161f7-316">**Longitud de clave pública**</span><span class="sxs-lookup"><span data-stu-id="161f7-316">**Public Key Length**</span></span>|
|<span data-ttu-id="161f7-317">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-317"></span></span>|
|<span data-ttu-id="161f7-318">**Algoritmo de firma**</span><span class="sxs-lookup"><span data-stu-id="161f7-318">**Signature Algorithm**</span></span>|
|<span data-ttu-id="161f7-319">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-319"></span></span>|
|<span data-ttu-id="161f7-320">**Validez no antes**</span><span class="sxs-lookup"><span data-stu-id="161f7-320">**Validity Not Before**</span></span>|
|<span data-ttu-id="161f7-321">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-321"></span></span>|
|<span data-ttu-id="161f7-322">**Validez no después**</span><span class="sxs-lookup"><span data-stu-id="161f7-322">**Validity Not After**</span></span>|
|<span data-ttu-id="161f7-323">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-323"></span></span>|
|<span data-ttu-id="161f7-324">**Identificador de clave de asunto**</span><span class="sxs-lookup"><span data-stu-id="161f7-324">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="161f7-325">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-325"></span></span>|
|<span data-ttu-id="161f7-326">**Huella digital (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="161f7-326">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="161f7-327">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-327"></span></span>|
|<span data-ttu-id="161f7-328">**Huella digital (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="161f7-328">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="161f7-329">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-329"></span></span>|
|<span data-ttu-id="161f7-330">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="161f7-330">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="161f7-331">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-331"></span></span>|
   
 <span data-ttu-id="161f7-332">**Entrust.net Certification Authority (2048)**</span><span class="sxs-lookup"><span data-stu-id="161f7-332">**Entrust.net Certification Authority (2048)**</span></span>
  
||
|:-----|
|<span data-ttu-id="161f7-333">**Asunto**</span><span class="sxs-lookup"><span data-stu-id="161f7-333">**Subject**</span></span>|
|<span data-ttu-id="161f7-334">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-334"></span></span>|
|<span data-ttu-id="161f7-335">**Número de serie**</span><span class="sxs-lookup"><span data-stu-id="161f7-335">**Serial Number**</span></span>|
|<span data-ttu-id="161f7-336">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-336"></span></span>|
|<span data-ttu-id="161f7-337">**Longitud de clave pública**</span><span class="sxs-lookup"><span data-stu-id="161f7-337">**Public Key Length**</span></span>|
|<span data-ttu-id="161f7-338">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-338"></span></span>|
|<span data-ttu-id="161f7-339">**Algoritmo de firma**</span><span class="sxs-lookup"><span data-stu-id="161f7-339">**Signature Algorithm**</span></span>|
|<span data-ttu-id="161f7-340">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-340"></span></span>|
|<span data-ttu-id="161f7-341">**Validez no antes**</span><span class="sxs-lookup"><span data-stu-id="161f7-341">**Validity Not Before**</span></span>|
|<span data-ttu-id="161f7-342">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-342"></span></span>|
|<span data-ttu-id="161f7-343">**Validez no después**</span><span class="sxs-lookup"><span data-stu-id="161f7-343">**Validity Not After**</span></span>|
|<span data-ttu-id="161f7-344">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-344"></span></span>|
|<span data-ttu-id="161f7-345">**Identificador de clave de asunto**</span><span class="sxs-lookup"><span data-stu-id="161f7-345">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="161f7-346">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-346"></span></span>|
|<span data-ttu-id="161f7-347">**Huella digital (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="161f7-347">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="161f7-348">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-348"></span></span>|
|<span data-ttu-id="161f7-349">**Huella digital (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="161f7-349">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="161f7-350">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-350"></span></span>|
|<span data-ttu-id="161f7-351">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="161f7-351">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="161f7-352">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-352"></span></span>|
   
 <span data-ttu-id="161f7-353">**GlobalSign**</span><span class="sxs-lookup"><span data-stu-id="161f7-353">**GlobalSign**</span></span>
  
||
|:-----|
|<span data-ttu-id="161f7-354">**Asunto**</span><span class="sxs-lookup"><span data-stu-id="161f7-354">**Subject**</span></span>|
|<span data-ttu-id="161f7-355">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-355"></span></span>|
|<span data-ttu-id="161f7-356">**Número de serie**</span><span class="sxs-lookup"><span data-stu-id="161f7-356">**Serial Number**</span></span>|
|<span data-ttu-id="161f7-357">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-357"></span></span>|
|<span data-ttu-id="161f7-358">**Longitud de clave pública**</span><span class="sxs-lookup"><span data-stu-id="161f7-358">**Public Key Length**</span></span>|
|<span data-ttu-id="161f7-359">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-359"></span></span>|
|<span data-ttu-id="161f7-360">**Algoritmo de firma**</span><span class="sxs-lookup"><span data-stu-id="161f7-360">**Signature Algorithm**</span></span>|
|<span data-ttu-id="161f7-361">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-361"></span></span>|
|<span data-ttu-id="161f7-362">**Validez no antes**</span><span class="sxs-lookup"><span data-stu-id="161f7-362">**Validity Not Before**</span></span>|
|<span data-ttu-id="161f7-363">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-363"></span></span>|
|<span data-ttu-id="161f7-364">**Validez no después**</span><span class="sxs-lookup"><span data-stu-id="161f7-364">**Validity Not After**</span></span>|
|<span data-ttu-id="161f7-365">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-365"></span></span>|
|<span data-ttu-id="161f7-366">**Identificador de clave de asunto**</span><span class="sxs-lookup"><span data-stu-id="161f7-366">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="161f7-367">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-367"></span></span>|
|<span data-ttu-id="161f7-368">**Identificador de clave de entidad de certificación**</span><span class="sxs-lookup"><span data-stu-id="161f7-368">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="161f7-369">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-369"></span></span>|
|<span data-ttu-id="161f7-370">**Huella digital (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="161f7-370">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="161f7-371">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-371"></span></span>|
|<span data-ttu-id="161f7-372">**Huella digital (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="161f7-372">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="161f7-373">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-373"></span></span>|
|<span data-ttu-id="161f7-374">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="161f7-374">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="161f7-375">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-375"></span></span>|
|<span data-ttu-id="161f7-376">**Direcciones URL CRL**</span><span class="sxs-lookup"><span data-stu-id="161f7-376">**CRL URLs**</span></span>|
|<span data-ttu-id="161f7-377">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-377"></span></span>|
   
 <span data-ttu-id="161f7-378">**GlobalSign Root CA**</span><span class="sxs-lookup"><span data-stu-id="161f7-378">**GlobalSign Root CA**</span></span>
  
||
|:-----|
|<span data-ttu-id="161f7-379">**Asunto**</span><span class="sxs-lookup"><span data-stu-id="161f7-379">**Subject**</span></span>|
|<span data-ttu-id="161f7-380">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-380"></span></span>|
|<span data-ttu-id="161f7-381">**Número de serie**</span><span class="sxs-lookup"><span data-stu-id="161f7-381">**Serial Number**</span></span>|
|<span data-ttu-id="161f7-382">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-382"></span></span>|
|<span data-ttu-id="161f7-383">**Longitud de clave pública**</span><span class="sxs-lookup"><span data-stu-id="161f7-383">**Public Key Length**</span></span>|
|<span data-ttu-id="161f7-384">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-384"></span></span>|
|<span data-ttu-id="161f7-385">**Algoritmo de firma**</span><span class="sxs-lookup"><span data-stu-id="161f7-385">**Signature Algorithm**</span></span>|
|<span data-ttu-id="161f7-386">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-386"></span></span>|
|<span data-ttu-id="161f7-387">**Validez no antes**</span><span class="sxs-lookup"><span data-stu-id="161f7-387">**Validity Not Before**</span></span>|
|<span data-ttu-id="161f7-388">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-388"></span></span>|
|<span data-ttu-id="161f7-389">**Validez no después**</span><span class="sxs-lookup"><span data-stu-id="161f7-389">**Validity Not After**</span></span>|
|<span data-ttu-id="161f7-390">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-390"></span></span>|
|<span data-ttu-id="161f7-391">**Identificador de clave de asunto**</span><span class="sxs-lookup"><span data-stu-id="161f7-391">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="161f7-392">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-392"></span></span>|
|<span data-ttu-id="161f7-393">**Huella digital (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="161f7-393">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="161f7-394">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-394"></span></span>|
|<span data-ttu-id="161f7-395">**Huella digital (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="161f7-395">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="161f7-396">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-396"></span></span>|
|<span data-ttu-id="161f7-397">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="161f7-397">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="161f7-398">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-398"></span></span>|
   
 <span data-ttu-id="161f7-399">**Thawte entidad emisora de certificados raíz principal - G3**</span><span class="sxs-lookup"><span data-stu-id="161f7-399">**thawte Primary Root CA - G3**</span></span>
  
||
|:-----|
|<span data-ttu-id="161f7-400">**Asunto**</span><span class="sxs-lookup"><span data-stu-id="161f7-400">**Subject**</span></span>|
|<span data-ttu-id="161f7-401">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-401"></span></span>|
|<span data-ttu-id="161f7-402">**Número de serie**</span><span class="sxs-lookup"><span data-stu-id="161f7-402">**Serial Number**</span></span>|
|<span data-ttu-id="161f7-403">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-403"></span></span>|
|<span data-ttu-id="161f7-404">**Longitud de clave pública**</span><span class="sxs-lookup"><span data-stu-id="161f7-404">**Public Key Length**</span></span>|
|<span data-ttu-id="161f7-405">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-405"></span></span>|
|<span data-ttu-id="161f7-406">**Algoritmo de firma**</span><span class="sxs-lookup"><span data-stu-id="161f7-406">**Signature Algorithm**</span></span>|
|<span data-ttu-id="161f7-407">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-407"></span></span>|
|<span data-ttu-id="161f7-408">**Validez no antes**</span><span class="sxs-lookup"><span data-stu-id="161f7-408">**Validity Not Before**</span></span>|
|<span data-ttu-id="161f7-409">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-409"></span></span>|
|<span data-ttu-id="161f7-410">**Validez no después**</span><span class="sxs-lookup"><span data-stu-id="161f7-410">**Validity Not After**</span></span>|
|<span data-ttu-id="161f7-411">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-411"></span></span>|
|<span data-ttu-id="161f7-412">**Identificador de clave de asunto**</span><span class="sxs-lookup"><span data-stu-id="161f7-412">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="161f7-413">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-413"></span></span>|
|<span data-ttu-id="161f7-414">**Huella digital (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="161f7-414">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="161f7-415">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-415"></span></span>|
|<span data-ttu-id="161f7-416">**Huella digital (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="161f7-416">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="161f7-417">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-417"></span></span>|
|<span data-ttu-id="161f7-418">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="161f7-418">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="161f7-419">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-419"></span></span>|
   
 <span data-ttu-id="161f7-420">**Entidad de certificación principal pública de clase 3 de VeriSign - G5**</span><span class="sxs-lookup"><span data-stu-id="161f7-420">**VeriSign Class 3 Public Primary Certification Authority - G5**</span></span>
  
||
|:-----|
|<span data-ttu-id="161f7-421">**Asunto**</span><span class="sxs-lookup"><span data-stu-id="161f7-421">**Subject**</span></span>|
|<span data-ttu-id="161f7-422">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-422"></span></span>|
|<span data-ttu-id="161f7-423">**Número de serie**</span><span class="sxs-lookup"><span data-stu-id="161f7-423">**Serial Number**</span></span>|
|<span data-ttu-id="161f7-424">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-424"></span></span>|
|<span data-ttu-id="161f7-425">**Longitud de clave pública**</span><span class="sxs-lookup"><span data-stu-id="161f7-425">**Public Key Length**</span></span>|
|<span data-ttu-id="161f7-426">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-426"></span></span>|
|<span data-ttu-id="161f7-427">**Algoritmo de firma**</span><span class="sxs-lookup"><span data-stu-id="161f7-427">**Signature Algorithm**</span></span>|
|<span data-ttu-id="161f7-428">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-428"></span></span>|
|<span data-ttu-id="161f7-429">**Validez no antes**</span><span class="sxs-lookup"><span data-stu-id="161f7-429">**Validity Not Before**</span></span>|
|<span data-ttu-id="161f7-430">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-430"></span></span>|
|<span data-ttu-id="161f7-431">**Validez no después**</span><span class="sxs-lookup"><span data-stu-id="161f7-431">**Validity Not After**</span></span>|
|<span data-ttu-id="161f7-432">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-432"></span></span>|
|<span data-ttu-id="161f7-433">**Identificador de clave de asunto**</span><span class="sxs-lookup"><span data-stu-id="161f7-433">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="161f7-434">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-434"></span></span>|
|<span data-ttu-id="161f7-435">**Huella digital (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="161f7-435">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="161f7-436">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-436"></span></span>|
|<span data-ttu-id="161f7-437">**Huella digital (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="161f7-437">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="161f7-438">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-438"></span></span>|
|<span data-ttu-id="161f7-439">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="161f7-439">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="161f7-440">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-440"></span></span>|
   
## <a name="office-365-intermediate-certificate-details"></a><span data-ttu-id="161f7-441">Detalles del certificado intermedio de Office 365</span><span class="sxs-lookup"><span data-stu-id="161f7-441">Office 365 Intermediate Certificate Details</span></span>
<span data-ttu-id="161f7-442"><a name="IntermediateCerts"> </a></span><span class="sxs-lookup"><span data-stu-id="161f7-442"></span></span>

 <span data-ttu-id="161f7-443">**CNNIC SHA256 SSL**</span><span class="sxs-lookup"><span data-stu-id="161f7-443">**CNNIC SHA256 SSL**</span></span>
  
||
|:-----|
|<span data-ttu-id="161f7-444">**Asunto**</span><span class="sxs-lookup"><span data-stu-id="161f7-444">**Subject**</span></span>|
|<span data-ttu-id="161f7-445">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-445"></span></span>|
|<span data-ttu-id="161f7-446">**Emisor**</span><span class="sxs-lookup"><span data-stu-id="161f7-446">**Issuer**</span></span>|
|<span data-ttu-id="161f7-447">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-447"></span></span>|
|<span data-ttu-id="161f7-448">**Número de serie**</span><span class="sxs-lookup"><span data-stu-id="161f7-448">**Serial Number**</span></span>|
|<span data-ttu-id="161f7-449">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-449"></span></span>|
|<span data-ttu-id="161f7-450">**Longitud de clave pública**</span><span class="sxs-lookup"><span data-stu-id="161f7-450">**Public Key Length**</span></span>|
|<span data-ttu-id="161f7-451">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-451"></span></span>|
|<span data-ttu-id="161f7-452">**Algoritmo de firma**</span><span class="sxs-lookup"><span data-stu-id="161f7-452">**Signature Algorithm**</span></span>|
|<span data-ttu-id="161f7-453">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-453"></span></span>|
|<span data-ttu-id="161f7-454">**Validez no antes**</span><span class="sxs-lookup"><span data-stu-id="161f7-454">**Validity Not Before**</span></span>|
|<span data-ttu-id="161f7-455">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-455"></span></span>|
|<span data-ttu-id="161f7-456">**Validez no después**</span><span class="sxs-lookup"><span data-stu-id="161f7-456">**Validity Not After**</span></span>|
|<span data-ttu-id="161f7-457">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-457"></span></span>|
|<span data-ttu-id="161f7-458">**Identificador de clave de asunto**</span><span class="sxs-lookup"><span data-stu-id="161f7-458">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="161f7-459">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-459"></span></span>|
|<span data-ttu-id="161f7-460">**Identificador de clave de entidad de certificación**</span><span class="sxs-lookup"><span data-stu-id="161f7-460">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="161f7-461">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-461"></span></span>|
|<span data-ttu-id="161f7-462">**Huella digital (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="161f7-462">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="161f7-463">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-463"></span></span>|
|<span data-ttu-id="161f7-464">**Huella digital (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="161f7-464">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="161f7-465">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-465"></span></span>|
|<span data-ttu-id="161f7-466">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="161f7-466">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="161f7-467">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-467"></span></span>|
|<span data-ttu-id="161f7-468">**Direcciones URL AIA**</span><span class="sxs-lookup"><span data-stu-id="161f7-468">**AIA URLs**</span></span>|
|<span data-ttu-id="161f7-469">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-469"></span></span>|
|<span data-ttu-id="161f7-470">**Direcciones URL CRL**</span><span class="sxs-lookup"><span data-stu-id="161f7-470">**CRL URLs**</span></span>|
|<span data-ttu-id="161f7-471">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-471"></span></span>|
|<span data-ttu-id="161f7-472">**Direcciones URL OCSP**</span><span class="sxs-lookup"><span data-stu-id="161f7-472">**OCSP URLs**</span></span>|
|<span data-ttu-id="161f7-473">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-473"></span></span>|
   
 <span data-ttu-id="161f7-474">**Entidad de certificación de confianza de D SSL clase 3 1 de 2009**</span><span class="sxs-lookup"><span data-stu-id="161f7-474">**D-TRUST SSL Class 3 CA 1 2009**</span></span>
  
||
|:-----|
|<span data-ttu-id="161f7-475">**Asunto**</span><span class="sxs-lookup"><span data-stu-id="161f7-475">**Subject**</span></span>|
|<span data-ttu-id="161f7-476">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-476"></span></span>|
|<span data-ttu-id="161f7-477">**Emisor**</span><span class="sxs-lookup"><span data-stu-id="161f7-477">**Issuer**</span></span>|
|<span data-ttu-id="161f7-478">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-478"></span></span>|
|<span data-ttu-id="161f7-479">**Nombre alternativo del sujeto**</span><span class="sxs-lookup"><span data-stu-id="161f7-479">**Subject Alternative Name**</span></span>|
|<span data-ttu-id="161f7-480">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-480"></span></span>|
|<span data-ttu-id="161f7-481">**Número de serie**</span><span class="sxs-lookup"><span data-stu-id="161f7-481">**Serial Number**</span></span>|
|<span data-ttu-id="161f7-482">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-482"></span></span>|
|<span data-ttu-id="161f7-483">**Longitud de clave pública**</span><span class="sxs-lookup"><span data-stu-id="161f7-483">**Public Key Length**</span></span>|
|<span data-ttu-id="161f7-484">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-484"></span></span>|
|<span data-ttu-id="161f7-485">**Algoritmo de firma**</span><span class="sxs-lookup"><span data-stu-id="161f7-485">**Signature Algorithm**</span></span>|
|<span data-ttu-id="161f7-486">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-486"></span></span>|
|<span data-ttu-id="161f7-487">**Validez no antes**</span><span class="sxs-lookup"><span data-stu-id="161f7-487">**Validity Not Before**</span></span>|
|<span data-ttu-id="161f7-488">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-488"></span></span>|
|<span data-ttu-id="161f7-489">**Validez no después**</span><span class="sxs-lookup"><span data-stu-id="161f7-489">**Validity Not After**</span></span>|
|<span data-ttu-id="161f7-490">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-490"></span></span>|
|<span data-ttu-id="161f7-491">**Identificador de clave de asunto**</span><span class="sxs-lookup"><span data-stu-id="161f7-491">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="161f7-492">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-492"></span></span>|
|<span data-ttu-id="161f7-493">**Identificador de clave de entidad de certificación**</span><span class="sxs-lookup"><span data-stu-id="161f7-493">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="161f7-494">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-494"></span></span>|
|<span data-ttu-id="161f7-495">**Huella digital (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="161f7-495">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="161f7-496">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-496"></span></span>|
|<span data-ttu-id="161f7-497">**Huella digital (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="161f7-497">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="161f7-498">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-498"></span></span>|
|<span data-ttu-id="161f7-499">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="161f7-499">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="161f7-500">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-500"></span></span>|
|<span data-ttu-id="161f7-501">**Direcciones URL CRL**</span><span class="sxs-lookup"><span data-stu-id="161f7-501">**CRL URLs**</span></span>|
|<span data-ttu-id="161f7-502">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-502"></span></span>|
|<span data-ttu-id="161f7-503">**Direcciones URL OCSP**</span><span class="sxs-lookup"><span data-stu-id="161f7-503">**OCSP URLs**</span></span>|
|<span data-ttu-id="161f7-504">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-504"></span></span>|
   
 <span data-ttu-id="161f7-505">**Entidad de certificación de confianza de D SSL clase 3 1 EV 2009**</span><span class="sxs-lookup"><span data-stu-id="161f7-505">**D-TRUST SSL Class 3 CA 1 EV 2009**</span></span>
  
||
|:-----|
|<span data-ttu-id="161f7-506">**Asunto**</span><span class="sxs-lookup"><span data-stu-id="161f7-506">**Subject**</span></span>|
|<span data-ttu-id="161f7-507">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-507"></span></span>|
|<span data-ttu-id="161f7-508">**Emisor**</span><span class="sxs-lookup"><span data-stu-id="161f7-508">**Issuer**</span></span>|
|<span data-ttu-id="161f7-509">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-509"></span></span>|
|<span data-ttu-id="161f7-510">**Nombre alternativo del sujeto**</span><span class="sxs-lookup"><span data-stu-id="161f7-510">**Subject Alternative Name**</span></span>|
|<span data-ttu-id="161f7-511">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-511"></span></span>|
|<span data-ttu-id="161f7-512">**Número de serie**</span><span class="sxs-lookup"><span data-stu-id="161f7-512">**Serial Number**</span></span>|
|<span data-ttu-id="161f7-513">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-513"></span></span>|
|<span data-ttu-id="161f7-514">**Longitud de clave pública**</span><span class="sxs-lookup"><span data-stu-id="161f7-514">**Public Key Length**</span></span>|
|<span data-ttu-id="161f7-515">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-515"></span></span>|
|<span data-ttu-id="161f7-516">**Algoritmo de firma**</span><span class="sxs-lookup"><span data-stu-id="161f7-516">**Signature Algorithm**</span></span>|
|<span data-ttu-id="161f7-517">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-517"></span></span>|
|<span data-ttu-id="161f7-518">**Validez no antes**</span><span class="sxs-lookup"><span data-stu-id="161f7-518">**Validity Not Before**</span></span>|
|<span data-ttu-id="161f7-519">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-519"></span></span>|
|<span data-ttu-id="161f7-520">**Validez no después**</span><span class="sxs-lookup"><span data-stu-id="161f7-520">**Validity Not After**</span></span>|
|<span data-ttu-id="161f7-521">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-521"></span></span>|
|<span data-ttu-id="161f7-522">**Identificador de clave de asunto**</span><span class="sxs-lookup"><span data-stu-id="161f7-522">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="161f7-523">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-523"></span></span>|
|<span data-ttu-id="161f7-524">**Identificador de clave de entidad de certificación**</span><span class="sxs-lookup"><span data-stu-id="161f7-524">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="161f7-525">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-525"></span></span>|
|<span data-ttu-id="161f7-526">**Huella digital (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="161f7-526">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="161f7-527">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-527"></span></span>|
|<span data-ttu-id="161f7-528">**Huella digital (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="161f7-528">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="161f7-529">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-529"></span></span>|
|<span data-ttu-id="161f7-530">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="161f7-530">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="161f7-531">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-531"></span></span>|
|<span data-ttu-id="161f7-532">**Direcciones URL CRL**</span><span class="sxs-lookup"><span data-stu-id="161f7-532">**CRL URLs**</span></span>|
|<span data-ttu-id="161f7-533">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-533"></span></span>|
|<span data-ttu-id="161f7-534">**Direcciones URL OCSP**</span><span class="sxs-lookup"><span data-stu-id="161f7-534">**OCSP URLs**</span></span>|
|<span data-ttu-id="161f7-535">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-535"></span></span>|
   
 <span data-ttu-id="161f7-536">**1 de la entidad emisora de certificados de servicios de nube de DigiCert**</span><span class="sxs-lookup"><span data-stu-id="161f7-536">**DigiCert Cloud Services CA-1**</span></span>
  
||
|:-----|
|<span data-ttu-id="161f7-537">**Asunto**</span><span class="sxs-lookup"><span data-stu-id="161f7-537">**Subject**</span></span>|
|<span data-ttu-id="161f7-538">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-538"></span></span>|
|<span data-ttu-id="161f7-539">**Emisor**</span><span class="sxs-lookup"><span data-stu-id="161f7-539">**Issuer**</span></span>|
|<span data-ttu-id="161f7-540">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-540"></span></span>|
|<span data-ttu-id="161f7-541">**Número de serie**</span><span class="sxs-lookup"><span data-stu-id="161f7-541">**Serial Number**</span></span>|
|<span data-ttu-id="161f7-542">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-542"></span></span>|
|<span data-ttu-id="161f7-543">**Longitud de clave pública**</span><span class="sxs-lookup"><span data-stu-id="161f7-543">**Public Key Length**</span></span>|
|<span data-ttu-id="161f7-544">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-544"></span></span>|
|<span data-ttu-id="161f7-545">**Algoritmo de firma**</span><span class="sxs-lookup"><span data-stu-id="161f7-545">**Signature Algorithm**</span></span>|
|<span data-ttu-id="161f7-546">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-546"></span></span>|
|<span data-ttu-id="161f7-547">**Validez no antes**</span><span class="sxs-lookup"><span data-stu-id="161f7-547">**Validity Not Before**</span></span>|
|<span data-ttu-id="161f7-548">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-548"></span></span>|
|<span data-ttu-id="161f7-549">**Validez no después**</span><span class="sxs-lookup"><span data-stu-id="161f7-549">**Validity Not After**</span></span>|
|<span data-ttu-id="161f7-550">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-550"></span></span>|
|<span data-ttu-id="161f7-551">**Identificador de clave de asunto**</span><span class="sxs-lookup"><span data-stu-id="161f7-551">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="161f7-552">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-552"></span></span>|
|<span data-ttu-id="161f7-553">**Identificador de clave de entidad de certificación**</span><span class="sxs-lookup"><span data-stu-id="161f7-553">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="161f7-554">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-554"></span></span>|
|<span data-ttu-id="161f7-555">**Huella digital (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="161f7-555">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="161f7-556">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-556"></span></span>|
|<span data-ttu-id="161f7-557">**Huella digital (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="161f7-557">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="161f7-558">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-558"></span></span>|
|<span data-ttu-id="161f7-559">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="161f7-559">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="161f7-560">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-560"></span></span>|
|<span data-ttu-id="161f7-561">**Direcciones URL CRL**</span><span class="sxs-lookup"><span data-stu-id="161f7-561">**CRL URLs**</span></span>|
|<span data-ttu-id="161f7-562">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-562"></span></span>|
|<span data-ttu-id="161f7-563">**Direcciones URL OCSP**</span><span class="sxs-lookup"><span data-stu-id="161f7-563">**OCSP URLs**</span></span>|
|<span data-ttu-id="161f7-564">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-564"></span></span>|
   
 <span data-ttu-id="161f7-565">**Servidor de seguridad alta DigiCert SHA2 entidad emisora de certificados**</span><span class="sxs-lookup"><span data-stu-id="161f7-565">**DigiCert SHA2 High Assurance Server CA**</span></span>
  
||
|:-----|
|<span data-ttu-id="161f7-566">**Asunto**</span><span class="sxs-lookup"><span data-stu-id="161f7-566">**Subject**</span></span>|
|<span data-ttu-id="161f7-567">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-567"></span></span>|
|<span data-ttu-id="161f7-568">**Emisor**</span><span class="sxs-lookup"><span data-stu-id="161f7-568">**Issuer**</span></span>|
|<span data-ttu-id="161f7-569">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-569"></span></span>|
|<span data-ttu-id="161f7-570">**Número de serie**</span><span class="sxs-lookup"><span data-stu-id="161f7-570">**Serial Number**</span></span>|
|<span data-ttu-id="161f7-571">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-571"></span></span>|
|<span data-ttu-id="161f7-572">**Longitud de clave pública**</span><span class="sxs-lookup"><span data-stu-id="161f7-572">**Public Key Length**</span></span>|
|<span data-ttu-id="161f7-573">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-573"></span></span>|
|<span data-ttu-id="161f7-574">**Algoritmo de firma**</span><span class="sxs-lookup"><span data-stu-id="161f7-574">**Signature Algorithm**</span></span>|
|<span data-ttu-id="161f7-575">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-575"></span></span>|
|<span data-ttu-id="161f7-576">**Validez no antes**</span><span class="sxs-lookup"><span data-stu-id="161f7-576">**Validity Not Before**</span></span>|
|<span data-ttu-id="161f7-577">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-577"></span></span>|
|<span data-ttu-id="161f7-578">**Validez no después**</span><span class="sxs-lookup"><span data-stu-id="161f7-578">**Validity Not After**</span></span>|
|<span data-ttu-id="161f7-579">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-579"></span></span>|
|<span data-ttu-id="161f7-580">**Identificador de clave de asunto**</span><span class="sxs-lookup"><span data-stu-id="161f7-580">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="161f7-581">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-581"></span></span>|
|<span data-ttu-id="161f7-582">**Identificador de clave de entidad de certificación**</span><span class="sxs-lookup"><span data-stu-id="161f7-582">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="161f7-583">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-583"></span></span>|
|<span data-ttu-id="161f7-584">**Huella digital (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="161f7-584">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="161f7-585">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-585"></span></span>|
|<span data-ttu-id="161f7-586">**Huella digital (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="161f7-586">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="161f7-587">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-587"></span></span>|
|<span data-ttu-id="161f7-588">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="161f7-588">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="161f7-589">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-589"></span></span>|
|<span data-ttu-id="161f7-590">**Direcciones URL CRL**</span><span class="sxs-lookup"><span data-stu-id="161f7-590">**CRL URLs**</span></span>|
|<span data-ttu-id="161f7-591">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-591"></span></span>|
|<span data-ttu-id="161f7-592">**Direcciones URL OCSP**</span><span class="sxs-lookup"><span data-stu-id="161f7-592">**OCSP URLs**</span></span>|
|<span data-ttu-id="161f7-593">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-593"></span></span>|
   
 <span data-ttu-id="161f7-594">**Servidor seguro DigiCert SHA2 entidad emisora de certificados**</span><span class="sxs-lookup"><span data-stu-id="161f7-594">**DigiCert SHA2 Secure Server CA**</span></span>
  
||
|:-----|
|<span data-ttu-id="161f7-595">**Asunto**</span><span class="sxs-lookup"><span data-stu-id="161f7-595">**Subject**</span></span>|
|<span data-ttu-id="161f7-596">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-596"></span></span>|
|<span data-ttu-id="161f7-597">**Emisor**</span><span class="sxs-lookup"><span data-stu-id="161f7-597">**Issuer**</span></span>|
|<span data-ttu-id="161f7-598">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-598"></span></span>|
|<span data-ttu-id="161f7-599">**Número de serie**</span><span class="sxs-lookup"><span data-stu-id="161f7-599">**Serial Number**</span></span>|
|<span data-ttu-id="161f7-600">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-600"></span></span>|
|<span data-ttu-id="161f7-601">**Longitud de clave pública**</span><span class="sxs-lookup"><span data-stu-id="161f7-601">**Public Key Length**</span></span>|
|<span data-ttu-id="161f7-602">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-602"></span></span>|
|<span data-ttu-id="161f7-603">**Algoritmo de firma**</span><span class="sxs-lookup"><span data-stu-id="161f7-603">**Signature Algorithm**</span></span>|
|<span data-ttu-id="161f7-604">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-604"></span></span>|
|<span data-ttu-id="161f7-605">**Validez no antes**</span><span class="sxs-lookup"><span data-stu-id="161f7-605">**Validity Not Before**</span></span>|
|<span data-ttu-id="161f7-606">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-606"></span></span>|
|<span data-ttu-id="161f7-607">**Validez no después**</span><span class="sxs-lookup"><span data-stu-id="161f7-607">**Validity Not After**</span></span>|
|<span data-ttu-id="161f7-608">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-608"></span></span>|
|<span data-ttu-id="161f7-609">**Identificador de clave de asunto**</span><span class="sxs-lookup"><span data-stu-id="161f7-609">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="161f7-610">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-610"></span></span>|
|<span data-ttu-id="161f7-611">**Identificador de clave de entidad de certificación**</span><span class="sxs-lookup"><span data-stu-id="161f7-611">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="161f7-612">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-612"></span></span>|
|<span data-ttu-id="161f7-613">**Huella digital (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="161f7-613">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="161f7-614">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-614"></span></span>|
|<span data-ttu-id="161f7-615">**Huella digital (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="161f7-615">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="161f7-616">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-616"></span></span>|
|<span data-ttu-id="161f7-617">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="161f7-617">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="161f7-618">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-618"></span></span>|
|<span data-ttu-id="161f7-619">**Direcciones URL CRL**</span><span class="sxs-lookup"><span data-stu-id="161f7-619">**CRL URLs**</span></span>|
|<span data-ttu-id="161f7-620">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-620"></span></span>|
|<span data-ttu-id="161f7-621">**Direcciones URL OCSP**</span><span class="sxs-lookup"><span data-stu-id="161f7-621">**OCSP URLs**</span></span>|
|<span data-ttu-id="161f7-622">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-622"></span></span>|
   
 <span data-ttu-id="161f7-623">**Entrust entidad de certificación - L1C**</span><span class="sxs-lookup"><span data-stu-id="161f7-623">**Entrust Certification Authority - L1C**</span></span>
  
||
|:-----|
|<span data-ttu-id="161f7-624">**Asunto**</span><span class="sxs-lookup"><span data-stu-id="161f7-624">**Subject**</span></span>|
|<span data-ttu-id="161f7-625">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-625"></span></span>|
|<span data-ttu-id="161f7-626">**Emisor**</span><span class="sxs-lookup"><span data-stu-id="161f7-626">**Issuer**</span></span>|
|<span data-ttu-id="161f7-627">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-627"></span></span>|
|<span data-ttu-id="161f7-628">**Número de serie**</span><span class="sxs-lookup"><span data-stu-id="161f7-628">**Serial Number**</span></span>|
|<span data-ttu-id="161f7-629">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-629"></span></span>|
|<span data-ttu-id="161f7-630">**Longitud de clave pública**</span><span class="sxs-lookup"><span data-stu-id="161f7-630">**Public Key Length**</span></span>|
|<span data-ttu-id="161f7-631">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-631"></span></span>|
|<span data-ttu-id="161f7-632">**Algoritmo de firma**</span><span class="sxs-lookup"><span data-stu-id="161f7-632">**Signature Algorithm**</span></span>|
|<span data-ttu-id="161f7-633">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-633"></span></span>|
|<span data-ttu-id="161f7-634">**Validez no antes**</span><span class="sxs-lookup"><span data-stu-id="161f7-634">**Validity Not Before**</span></span>|
|<span data-ttu-id="161f7-635">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-635"></span></span>|
|<span data-ttu-id="161f7-636">**Validez no después**</span><span class="sxs-lookup"><span data-stu-id="161f7-636">**Validity Not After**</span></span>|
|<span data-ttu-id="161f7-637">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-637"></span></span>|
|<span data-ttu-id="161f7-638">**Identificador de clave de asunto**</span><span class="sxs-lookup"><span data-stu-id="161f7-638">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="161f7-639">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-639"></span></span>|
|<span data-ttu-id="161f7-640">**Identificador de clave de entidad de certificación**</span><span class="sxs-lookup"><span data-stu-id="161f7-640">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="161f7-641">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-641"></span></span>|
|<span data-ttu-id="161f7-642">**Huella digital (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="161f7-642">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="161f7-643">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-643"></span></span>|
|<span data-ttu-id="161f7-644">**Huella digital (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="161f7-644">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="161f7-645">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-645"></span></span>|
|<span data-ttu-id="161f7-646">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="161f7-646">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="161f7-647">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-647"></span></span>|
|<span data-ttu-id="161f7-648">**Direcciones URL CRL**</span><span class="sxs-lookup"><span data-stu-id="161f7-648">**CRL URLs**</span></span>|
|<span data-ttu-id="161f7-649">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-649"></span></span>|
|<span data-ttu-id="161f7-650">**Direcciones URL OCSP**</span><span class="sxs-lookup"><span data-stu-id="161f7-650">**OCSP URLs**</span></span>|
|<span data-ttu-id="161f7-651">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-651"></span></span>|
   
 <span data-ttu-id="161f7-652">**Entrust entidad de certificación - L1K**</span><span class="sxs-lookup"><span data-stu-id="161f7-652">**Entrust Certification Authority - L1K**</span></span>
  
||
|:-----|
|<span data-ttu-id="161f7-653">**Asunto**</span><span class="sxs-lookup"><span data-stu-id="161f7-653">**Subject**</span></span>|
|<span data-ttu-id="161f7-654">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-654"></span></span>|
|<span data-ttu-id="161f7-655">**Emisor**</span><span class="sxs-lookup"><span data-stu-id="161f7-655">**Issuer**</span></span>|
|<span data-ttu-id="161f7-656">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-656"></span></span>|
|<span data-ttu-id="161f7-657">**Número de serie**</span><span class="sxs-lookup"><span data-stu-id="161f7-657">**Serial Number**</span></span>|
|<span data-ttu-id="161f7-658">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-658"></span></span>|
|<span data-ttu-id="161f7-659">**Longitud de clave pública**</span><span class="sxs-lookup"><span data-stu-id="161f7-659">**Public Key Length**</span></span>|
|<span data-ttu-id="161f7-660">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-660"></span></span>|
|<span data-ttu-id="161f7-661">**Algoritmo de firma**</span><span class="sxs-lookup"><span data-stu-id="161f7-661">**Signature Algorithm**</span></span>|
|<span data-ttu-id="161f7-662">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-662"></span></span>|
|<span data-ttu-id="161f7-663">**Validez no antes**</span><span class="sxs-lookup"><span data-stu-id="161f7-663">**Validity Not Before**</span></span>|
|<span data-ttu-id="161f7-664">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-664"></span></span>|
|<span data-ttu-id="161f7-665">**Validez no después**</span><span class="sxs-lookup"><span data-stu-id="161f7-665">**Validity Not After**</span></span>|
|<span data-ttu-id="161f7-666">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-666"></span></span>|
|<span data-ttu-id="161f7-667">**Identificador de clave de asunto**</span><span class="sxs-lookup"><span data-stu-id="161f7-667">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="161f7-668">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-668"></span></span>|
|<span data-ttu-id="161f7-669">**Identificador de clave de entidad de certificación**</span><span class="sxs-lookup"><span data-stu-id="161f7-669">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="161f7-670">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-670"></span></span>|
|<span data-ttu-id="161f7-671">**Huella digital (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="161f7-671">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="161f7-672">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-672"></span></span>|
|<span data-ttu-id="161f7-673">**Huella digital (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="161f7-673">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="161f7-674">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-674"></span></span>|
|<span data-ttu-id="161f7-675">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="161f7-675">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="161f7-676">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-676"></span></span>|
|<span data-ttu-id="161f7-677">**Direcciones URL CRL**</span><span class="sxs-lookup"><span data-stu-id="161f7-677">**CRL URLs**</span></span>|
|<span data-ttu-id="161f7-678">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-678"></span></span>|
|<span data-ttu-id="161f7-679">**Direcciones URL OCSP**</span><span class="sxs-lookup"><span data-stu-id="161f7-679">**OCSP URLs**</span></span>|
|<span data-ttu-id="161f7-680">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-680"></span></span>|
   
 <span data-ttu-id="161f7-681">**GlobalSign**</span><span class="sxs-lookup"><span data-stu-id="161f7-681">**GlobalSign**</span></span>
  
||
|:-----|
|<span data-ttu-id="161f7-682">**Asunto**</span><span class="sxs-lookup"><span data-stu-id="161f7-682">**Subject**</span></span>|
|<span data-ttu-id="161f7-683">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-683"></span></span>|
|<span data-ttu-id="161f7-684">**Emisor**</span><span class="sxs-lookup"><span data-stu-id="161f7-684">**Issuer**</span></span>|
|<span data-ttu-id="161f7-685">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-685"></span></span>|
|<span data-ttu-id="161f7-686">**Número de serie**</span><span class="sxs-lookup"><span data-stu-id="161f7-686">**Serial Number**</span></span>|
|<span data-ttu-id="161f7-687">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-687"></span></span>|
|<span data-ttu-id="161f7-688">**Longitud de clave pública**</span><span class="sxs-lookup"><span data-stu-id="161f7-688">**Public Key Length**</span></span>|
|<span data-ttu-id="161f7-689">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-689"></span></span>|
|<span data-ttu-id="161f7-690">**Algoritmo de firma**</span><span class="sxs-lookup"><span data-stu-id="161f7-690">**Signature Algorithm**</span></span>|
|<span data-ttu-id="161f7-691">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-691"></span></span>|
|<span data-ttu-id="161f7-692">**Validez no antes**</span><span class="sxs-lookup"><span data-stu-id="161f7-692">**Validity Not Before**</span></span>|
|<span data-ttu-id="161f7-693">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-693"></span></span>|
|<span data-ttu-id="161f7-694">**Validez no después**</span><span class="sxs-lookup"><span data-stu-id="161f7-694">**Validity Not After**</span></span>|
|<span data-ttu-id="161f7-695">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-695"></span></span>|
|<span data-ttu-id="161f7-696">**Identificador de clave de asunto**</span><span class="sxs-lookup"><span data-stu-id="161f7-696">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="161f7-697">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-697"></span></span>|
|<span data-ttu-id="161f7-698">**Identificador de clave de entidad de certificación**</span><span class="sxs-lookup"><span data-stu-id="161f7-698">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="161f7-699">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-699"></span></span>|
|<span data-ttu-id="161f7-700">**Huella digital (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="161f7-700">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="161f7-701">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-701"></span></span>|
|<span data-ttu-id="161f7-702">**Huella digital (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="161f7-702">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="161f7-703">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-703"></span></span>|
|<span data-ttu-id="161f7-704">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="161f7-704">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="161f7-705">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-705"></span></span>|
|<span data-ttu-id="161f7-706">**Direcciones URL CRL**</span><span class="sxs-lookup"><span data-stu-id="161f7-706">**CRL URLs**</span></span>|
|<span data-ttu-id="161f7-707">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-707"></span></span>|
|<span data-ttu-id="161f7-708">**Direcciones URL OCSP**</span><span class="sxs-lookup"><span data-stu-id="161f7-708">**OCSP URLs**</span></span>|
|<span data-ttu-id="161f7-709">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-709"></span></span>|
   
 <span data-ttu-id="161f7-710">**GlobalSign extendida Validation CA - SHA256 - G2**</span><span class="sxs-lookup"><span data-stu-id="161f7-710">**GlobalSign Extended Validation CA - SHA256 - G2**</span></span>
  
||
|:-----|
|<span data-ttu-id="161f7-711">**Asunto**</span><span class="sxs-lookup"><span data-stu-id="161f7-711">**Subject**</span></span>|
|<span data-ttu-id="161f7-712">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-712"></span></span>|
|<span data-ttu-id="161f7-713">**Emisor**</span><span class="sxs-lookup"><span data-stu-id="161f7-713">**Issuer**</span></span>|
|<span data-ttu-id="161f7-714">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-714"></span></span>|
|<span data-ttu-id="161f7-715">**Número de serie**</span><span class="sxs-lookup"><span data-stu-id="161f7-715">**Serial Number**</span></span>|
|<span data-ttu-id="161f7-716">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-716"></span></span>|
|<span data-ttu-id="161f7-717">**Longitud de clave pública**</span><span class="sxs-lookup"><span data-stu-id="161f7-717">**Public Key Length**</span></span>|
|<span data-ttu-id="161f7-718">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-718"></span></span>|
|<span data-ttu-id="161f7-719">**Algoritmo de firma**</span><span class="sxs-lookup"><span data-stu-id="161f7-719">**Signature Algorithm**</span></span>|
|<span data-ttu-id="161f7-720">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-720"></span></span>|
|<span data-ttu-id="161f7-721">**Validez no antes**</span><span class="sxs-lookup"><span data-stu-id="161f7-721">**Validity Not Before**</span></span>|
|<span data-ttu-id="161f7-722">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-722"></span></span>|
|<span data-ttu-id="161f7-723">**Validez no después**</span><span class="sxs-lookup"><span data-stu-id="161f7-723">**Validity Not After**</span></span>|
|<span data-ttu-id="161f7-724">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-724"></span></span>|
|<span data-ttu-id="161f7-725">**Identificador de clave de asunto**</span><span class="sxs-lookup"><span data-stu-id="161f7-725">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="161f7-726">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-726"></span></span>|
|<span data-ttu-id="161f7-727">**Identificador de clave de entidad de certificación**</span><span class="sxs-lookup"><span data-stu-id="161f7-727">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="161f7-728">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-728"></span></span>|
|<span data-ttu-id="161f7-729">**Huella digital (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="161f7-729">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="161f7-730">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-730"></span></span>|
|<span data-ttu-id="161f7-731">**Huella digital (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="161f7-731">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="161f7-732">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-732"></span></span>|
|<span data-ttu-id="161f7-733">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="161f7-733">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="161f7-734">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-734"></span></span>|
|<span data-ttu-id="161f7-735">**Direcciones URL CRL**</span><span class="sxs-lookup"><span data-stu-id="161f7-735">**CRL URLs**</span></span>|
|<span data-ttu-id="161f7-736">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-736"></span></span>|
|<span data-ttu-id="161f7-737">**Direcciones URL OCSP**</span><span class="sxs-lookup"><span data-stu-id="161f7-737">**OCSP URLs**</span></span>|
|<span data-ttu-id="161f7-738">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-738"></span></span>|
   
 <span data-ttu-id="161f7-739">**GlobalSign extendida Validation CA - SHA256 - G3**</span><span class="sxs-lookup"><span data-stu-id="161f7-739">**GlobalSign Extended Validation CA - SHA256 - G3**</span></span>
  
||
|:-----|
|<span data-ttu-id="161f7-740">**Asunto**</span><span class="sxs-lookup"><span data-stu-id="161f7-740">**Subject**</span></span>|
|<span data-ttu-id="161f7-741">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-741"></span></span>|
|<span data-ttu-id="161f7-742">**Emisor**</span><span class="sxs-lookup"><span data-stu-id="161f7-742">**Issuer**</span></span>|
|<span data-ttu-id="161f7-743">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-743"></span></span>|
|<span data-ttu-id="161f7-744">**Número de serie**</span><span class="sxs-lookup"><span data-stu-id="161f7-744">**Serial Number**</span></span>|
|<span data-ttu-id="161f7-745">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-745"></span></span>|
|<span data-ttu-id="161f7-746">**Longitud de clave pública**</span><span class="sxs-lookup"><span data-stu-id="161f7-746">**Public Key Length**</span></span>|
|<span data-ttu-id="161f7-747">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-747"></span></span>|
|<span data-ttu-id="161f7-748">**Algoritmo de firma**</span><span class="sxs-lookup"><span data-stu-id="161f7-748">**Signature Algorithm**</span></span>|
|<span data-ttu-id="161f7-749">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-749"></span></span>|
|<span data-ttu-id="161f7-750">**Validez no antes**</span><span class="sxs-lookup"><span data-stu-id="161f7-750">**Validity Not Before**</span></span>|
|<span data-ttu-id="161f7-751">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-751"></span></span>|
|<span data-ttu-id="161f7-752">**Validez no después**</span><span class="sxs-lookup"><span data-stu-id="161f7-752">**Validity Not After**</span></span>|
|<span data-ttu-id="161f7-753">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-753"></span></span>|
|<span data-ttu-id="161f7-754">**Identificador de clave de asunto**</span><span class="sxs-lookup"><span data-stu-id="161f7-754">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="161f7-755">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-755"></span></span>|
|<span data-ttu-id="161f7-756">**Identificador de clave de entidad de certificación**</span><span class="sxs-lookup"><span data-stu-id="161f7-756">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="161f7-757">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-757"></span></span>|
|<span data-ttu-id="161f7-758">**Huella digital (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="161f7-758">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="161f7-759">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-759"></span></span>|
|<span data-ttu-id="161f7-760">**Huella digital (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="161f7-760">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="161f7-761">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-761"></span></span>|
|<span data-ttu-id="161f7-762">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="161f7-762">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="161f7-763">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-763"></span></span>|
|<span data-ttu-id="161f7-764">**Direcciones URL CRL**</span><span class="sxs-lookup"><span data-stu-id="161f7-764">**CRL URLs**</span></span>|
|<span data-ttu-id="161f7-765">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-765"></span></span>|
|<span data-ttu-id="161f7-766">**Direcciones URL OCSP**</span><span class="sxs-lookup"><span data-stu-id="161f7-766">**OCSP URLs**</span></span>|
|<span data-ttu-id="161f7-767">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-767"></span></span>|
   
 <span data-ttu-id="161f7-768">**GlobalSign organización validación CA - SHA256 - G2**</span><span class="sxs-lookup"><span data-stu-id="161f7-768">**GlobalSign Organization Validation CA - SHA256 - G2**</span></span>
  
||
|:-----|
|<span data-ttu-id="161f7-769">**Asunto**</span><span class="sxs-lookup"><span data-stu-id="161f7-769">**Subject**</span></span>|
|<span data-ttu-id="161f7-770">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-770"></span></span>|
|<span data-ttu-id="161f7-771">**Emisor**</span><span class="sxs-lookup"><span data-stu-id="161f7-771">**Issuer**</span></span>|
|<span data-ttu-id="161f7-772">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-772"></span></span>|
|<span data-ttu-id="161f7-773">**Número de serie**</span><span class="sxs-lookup"><span data-stu-id="161f7-773">**Serial Number**</span></span>|
|<span data-ttu-id="161f7-774">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-774"></span></span>|
|<span data-ttu-id="161f7-775">**Longitud de clave pública**</span><span class="sxs-lookup"><span data-stu-id="161f7-775">**Public Key Length**</span></span>|
|<span data-ttu-id="161f7-776">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-776"></span></span>|
|<span data-ttu-id="161f7-777">**Algoritmo de firma**</span><span class="sxs-lookup"><span data-stu-id="161f7-777">**Signature Algorithm**</span></span>|
|<span data-ttu-id="161f7-778">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-778"></span></span>|
|<span data-ttu-id="161f7-779">**Validez no antes**</span><span class="sxs-lookup"><span data-stu-id="161f7-779">**Validity Not Before**</span></span>|
|<span data-ttu-id="161f7-780">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-780"></span></span>|
|<span data-ttu-id="161f7-781">**Validez no después**</span><span class="sxs-lookup"><span data-stu-id="161f7-781">**Validity Not After**</span></span>|
|<span data-ttu-id="161f7-782">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-782"></span></span>|
|<span data-ttu-id="161f7-783">**Identificador de clave de asunto**</span><span class="sxs-lookup"><span data-stu-id="161f7-783">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="161f7-784">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-784"></span></span>|
|<span data-ttu-id="161f7-785">**Identificador de clave de entidad de certificación**</span><span class="sxs-lookup"><span data-stu-id="161f7-785">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="161f7-786">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-786"></span></span>|
|<span data-ttu-id="161f7-787">**Huella digital (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="161f7-787">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="161f7-788">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-788"></span></span>|
|<span data-ttu-id="161f7-789">**Huella digital (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="161f7-789">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="161f7-790">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-790"></span></span>|
|<span data-ttu-id="161f7-791">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="161f7-791">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="161f7-792">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-792"></span></span>|
|<span data-ttu-id="161f7-793">**Direcciones URL CRL**</span><span class="sxs-lookup"><span data-stu-id="161f7-793">**CRL URLs**</span></span>|
|<span data-ttu-id="161f7-794">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-794"></span></span>|
|<span data-ttu-id="161f7-795">**Direcciones URL OCSP**</span><span class="sxs-lookup"><span data-stu-id="161f7-795">**OCSP URLs**</span></span>|
|<span data-ttu-id="161f7-796">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-796"></span></span>|
   
 <span data-ttu-id="161f7-797">**GlobalSign organización validación CA - SHA256 - G2**</span><span class="sxs-lookup"><span data-stu-id="161f7-797">**GlobalSign Organization Validation CA - SHA256 - G2**</span></span>
  
||
|:-----|
|<span data-ttu-id="161f7-798">**Asunto**</span><span class="sxs-lookup"><span data-stu-id="161f7-798">**Subject**</span></span>|
|<span data-ttu-id="161f7-799">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-799"></span></span>|
|<span data-ttu-id="161f7-800">**Emisor**</span><span class="sxs-lookup"><span data-stu-id="161f7-800">**Issuer**</span></span>|
|<span data-ttu-id="161f7-801">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-801"></span></span>|
|<span data-ttu-id="161f7-802">**Número de serie**</span><span class="sxs-lookup"><span data-stu-id="161f7-802">**Serial Number**</span></span>|
|<span data-ttu-id="161f7-803">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-803"></span></span>|
|<span data-ttu-id="161f7-804">**Longitud de clave pública**</span><span class="sxs-lookup"><span data-stu-id="161f7-804">**Public Key Length**</span></span>|
|<span data-ttu-id="161f7-805">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-805"></span></span>|
|<span data-ttu-id="161f7-806">**Algoritmo de firma**</span><span class="sxs-lookup"><span data-stu-id="161f7-806">**Signature Algorithm**</span></span>|
|<span data-ttu-id="161f7-807">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-807"></span></span>|
|<span data-ttu-id="161f7-808">**Validez no antes**</span><span class="sxs-lookup"><span data-stu-id="161f7-808">**Validity Not Before**</span></span>|
|<span data-ttu-id="161f7-809">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-809"></span></span>|
|<span data-ttu-id="161f7-810">**Validez no después**</span><span class="sxs-lookup"><span data-stu-id="161f7-810">**Validity Not After**</span></span>|
|<span data-ttu-id="161f7-811">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-811"></span></span>|
|<span data-ttu-id="161f7-812">**Identificador de clave de asunto**</span><span class="sxs-lookup"><span data-stu-id="161f7-812">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="161f7-813">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-813"></span></span>|
|<span data-ttu-id="161f7-814">**Identificador de clave de entidad de certificación**</span><span class="sxs-lookup"><span data-stu-id="161f7-814">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="161f7-815">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-815"></span></span>|
|<span data-ttu-id="161f7-816">**Huella digital (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="161f7-816">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="161f7-817">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-817"></span></span>|
|<span data-ttu-id="161f7-818">**Huella digital (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="161f7-818">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="161f7-819">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-819"></span></span>|
|<span data-ttu-id="161f7-820">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="161f7-820">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="161f7-821">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-821"></span></span>|
|<span data-ttu-id="161f7-822">**Direcciones URL CRL**</span><span class="sxs-lookup"><span data-stu-id="161f7-822">**CRL URLs**</span></span>|
|<span data-ttu-id="161f7-823">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-823"></span></span>|
|<span data-ttu-id="161f7-824">**Direcciones URL OCSP**</span><span class="sxs-lookup"><span data-stu-id="161f7-824">**OCSP URLs**</span></span>|
|<span data-ttu-id="161f7-825">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-825"></span></span>|
   
 <span data-ttu-id="161f7-826">**Vamos a cifrar autoridad X3**</span><span class="sxs-lookup"><span data-stu-id="161f7-826">**Let's Encrypt Authority X3**</span></span>
  
||
|:-----|
|<span data-ttu-id="161f7-827">**Asunto**</span><span class="sxs-lookup"><span data-stu-id="161f7-827">**Subject**</span></span>|
|<span data-ttu-id="161f7-828">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-828"></span></span>|
|<span data-ttu-id="161f7-829">**Emisor**</span><span class="sxs-lookup"><span data-stu-id="161f7-829">**Issuer**</span></span>|
|<span data-ttu-id="161f7-830">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-830"></span></span>|
|<span data-ttu-id="161f7-831">**Número de serie**</span><span class="sxs-lookup"><span data-stu-id="161f7-831">**Serial Number**</span></span>|
|<span data-ttu-id="161f7-832">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-832"></span></span>|
|<span data-ttu-id="161f7-833">**Longitud de clave pública**</span><span class="sxs-lookup"><span data-stu-id="161f7-833">**Public Key Length**</span></span>|
|<span data-ttu-id="161f7-834">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-834"></span></span>|
|<span data-ttu-id="161f7-835">**Algoritmo de firma**</span><span class="sxs-lookup"><span data-stu-id="161f7-835">**Signature Algorithm**</span></span>|
|<span data-ttu-id="161f7-836">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-836"></span></span>|
|<span data-ttu-id="161f7-837">**Validez no antes**</span><span class="sxs-lookup"><span data-stu-id="161f7-837">**Validity Not Before**</span></span>|
|<span data-ttu-id="161f7-838">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-838"></span></span>|
|<span data-ttu-id="161f7-839">**Validez no después**</span><span class="sxs-lookup"><span data-stu-id="161f7-839">**Validity Not After**</span></span>|
|<span data-ttu-id="161f7-840">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-840"></span></span>|
|<span data-ttu-id="161f7-841">**Identificador de clave de asunto**</span><span class="sxs-lookup"><span data-stu-id="161f7-841">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="161f7-842">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-842"></span></span>|
|<span data-ttu-id="161f7-843">**Identificador de clave de entidad de certificación**</span><span class="sxs-lookup"><span data-stu-id="161f7-843">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="161f7-844">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-844"></span></span>|
|<span data-ttu-id="161f7-845">**Huella digital (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="161f7-845">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="161f7-846">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-846"></span></span>|
|<span data-ttu-id="161f7-847">**Huella digital (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="161f7-847">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="161f7-848">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-848"></span></span>|
|<span data-ttu-id="161f7-849">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="161f7-849">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="161f7-850">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-850"></span></span>|
|<span data-ttu-id="161f7-851">**Direcciones URL AIA**</span><span class="sxs-lookup"><span data-stu-id="161f7-851">**AIA URLs**</span></span>|
|<span data-ttu-id="161f7-852">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-852"></span></span>|
|<span data-ttu-id="161f7-853">**Direcciones URL CRL**</span><span class="sxs-lookup"><span data-stu-id="161f7-853">**CRL URLs**</span></span>|
|<span data-ttu-id="161f7-854">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-854"></span></span>|
|<span data-ttu-id="161f7-855">**Direcciones URL OCSP**</span><span class="sxs-lookup"><span data-stu-id="161f7-855">**OCSP URLs**</span></span>|
|<span data-ttu-id="161f7-856">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-856"></span></span>|
   
 <span data-ttu-id="161f7-857">**Microsoft IT SSL SHA2**</span><span class="sxs-lookup"><span data-stu-id="161f7-857">**Microsoft IT SSL SHA2**</span></span>
  
||
|:-----|
|<span data-ttu-id="161f7-858">**Asunto**</span><span class="sxs-lookup"><span data-stu-id="161f7-858">**Subject**</span></span>|
|<span data-ttu-id="161f7-859">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-859"></span></span>|
|<span data-ttu-id="161f7-860">**Emisor**</span><span class="sxs-lookup"><span data-stu-id="161f7-860">**Issuer**</span></span>|
|<span data-ttu-id="161f7-861">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-861"></span></span>|
|<span data-ttu-id="161f7-862">**Número de serie**</span><span class="sxs-lookup"><span data-stu-id="161f7-862">**Serial Number**</span></span>|
|<span data-ttu-id="161f7-863">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-863"></span></span>|
|<span data-ttu-id="161f7-864">**Longitud de clave pública**</span><span class="sxs-lookup"><span data-stu-id="161f7-864">**Public Key Length**</span></span>|
|<span data-ttu-id="161f7-865">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-865"></span></span>|
|<span data-ttu-id="161f7-866">**Algoritmo de firma**</span><span class="sxs-lookup"><span data-stu-id="161f7-866">**Signature Algorithm**</span></span>|
|<span data-ttu-id="161f7-867">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-867"></span></span>|
|<span data-ttu-id="161f7-868">**Validez no antes**</span><span class="sxs-lookup"><span data-stu-id="161f7-868">**Validity Not Before**</span></span>|
|<span data-ttu-id="161f7-869">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-869"></span></span>|
|<span data-ttu-id="161f7-870">**Validez no después**</span><span class="sxs-lookup"><span data-stu-id="161f7-870">**Validity Not After**</span></span>|
|<span data-ttu-id="161f7-871">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-871"></span></span>|
|<span data-ttu-id="161f7-872">**Identificador de clave de asunto**</span><span class="sxs-lookup"><span data-stu-id="161f7-872">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="161f7-873">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-873"></span></span>|
|<span data-ttu-id="161f7-874">**Identificador de clave de entidad de certificación**</span><span class="sxs-lookup"><span data-stu-id="161f7-874">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="161f7-875">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-875"></span></span>|
|<span data-ttu-id="161f7-876">**Huella digital (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="161f7-876">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="161f7-877">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-877"></span></span>|
|<span data-ttu-id="161f7-878">**Huella digital (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="161f7-878">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="161f7-879">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-879"></span></span>|
|<span data-ttu-id="161f7-880">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="161f7-880">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="161f7-881">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-881"></span></span>|
|<span data-ttu-id="161f7-882">**Direcciones URL CRL**</span><span class="sxs-lookup"><span data-stu-id="161f7-882">**CRL URLs**</span></span>|
|<span data-ttu-id="161f7-883">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-883"></span></span>|
   
 <span data-ttu-id="161f7-884">**Microsoft IT SSL SHA2**</span><span class="sxs-lookup"><span data-stu-id="161f7-884">**Microsoft IT SSL SHA2**</span></span>
  
||
|:-----|
|<span data-ttu-id="161f7-885">**Asunto**</span><span class="sxs-lookup"><span data-stu-id="161f7-885">**Subject**</span></span>|
|<span data-ttu-id="161f7-886">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-886"></span></span>|
|<span data-ttu-id="161f7-887">**Emisor**</span><span class="sxs-lookup"><span data-stu-id="161f7-887">**Issuer**</span></span>|
|<span data-ttu-id="161f7-888">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-888"></span></span>|
|<span data-ttu-id="161f7-889">**Número de serie**</span><span class="sxs-lookup"><span data-stu-id="161f7-889">**Serial Number**</span></span>|
|<span data-ttu-id="161f7-890">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-890"></span></span>|
|<span data-ttu-id="161f7-891">**Longitud de clave pública**</span><span class="sxs-lookup"><span data-stu-id="161f7-891">**Public Key Length**</span></span>|
|<span data-ttu-id="161f7-892">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-892"></span></span>|
|<span data-ttu-id="161f7-893">**Algoritmo de firma**</span><span class="sxs-lookup"><span data-stu-id="161f7-893">**Signature Algorithm**</span></span>|
|<span data-ttu-id="161f7-894">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-894"></span></span>|
|<span data-ttu-id="161f7-895">**Validez no antes**</span><span class="sxs-lookup"><span data-stu-id="161f7-895">**Validity Not Before**</span></span>|
|<span data-ttu-id="161f7-896">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-896"></span></span>|
|<span data-ttu-id="161f7-897">**Validez no después**</span><span class="sxs-lookup"><span data-stu-id="161f7-897">**Validity Not After**</span></span>|
|<span data-ttu-id="161f7-898">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-898"></span></span>|
|<span data-ttu-id="161f7-899">**Identificador de clave de asunto**</span><span class="sxs-lookup"><span data-stu-id="161f7-899">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="161f7-900">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-900"></span></span>|
|<span data-ttu-id="161f7-901">**Identificador de clave de entidad de certificación**</span><span class="sxs-lookup"><span data-stu-id="161f7-901">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="161f7-902">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-902"></span></span>|
|<span data-ttu-id="161f7-903">**Huella digital (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="161f7-903">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="161f7-904">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-904"></span></span>|
|<span data-ttu-id="161f7-905">**Huella digital (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="161f7-905">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="161f7-906">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-906"></span></span>|
|<span data-ttu-id="161f7-907">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="161f7-907">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="161f7-908">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-908"></span></span>|
|<span data-ttu-id="161f7-909">**Direcciones URL CRL**</span><span class="sxs-lookup"><span data-stu-id="161f7-909">**CRL URLs**</span></span>|
|<span data-ttu-id="161f7-910">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-910"></span></span>|
|<span data-ttu-id="161f7-911">**Direcciones URL OCSP**</span><span class="sxs-lookup"><span data-stu-id="161f7-911">**OCSP URLs**</span></span>|
|<span data-ttu-id="161f7-912">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-912"></span></span>|
   
 <span data-ttu-id="161f7-913">**Entidad de certificación de Microsoft IT TLS 1**</span><span class="sxs-lookup"><span data-stu-id="161f7-913">**Microsoft IT TLS CA 1**</span></span>
  
||
|:-----|
|<span data-ttu-id="161f7-914">**Asunto**</span><span class="sxs-lookup"><span data-stu-id="161f7-914">**Subject**</span></span>|
|<span data-ttu-id="161f7-915">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-915"></span></span>|
|<span data-ttu-id="161f7-916">**Emisor**</span><span class="sxs-lookup"><span data-stu-id="161f7-916">**Issuer**</span></span>|
|<span data-ttu-id="161f7-917">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-917"></span></span>|
|<span data-ttu-id="161f7-918">**Número de serie**</span><span class="sxs-lookup"><span data-stu-id="161f7-918">**Serial Number**</span></span>|
|<span data-ttu-id="161f7-919">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-919"></span></span>|
|<span data-ttu-id="161f7-920">**Longitud de clave pública**</span><span class="sxs-lookup"><span data-stu-id="161f7-920">**Public Key Length**</span></span>|
|<span data-ttu-id="161f7-921">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-921"></span></span>|
|<span data-ttu-id="161f7-922">**Algoritmo de firma**</span><span class="sxs-lookup"><span data-stu-id="161f7-922">**Signature Algorithm**</span></span>|
|<span data-ttu-id="161f7-923">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-923"></span></span>|
|<span data-ttu-id="161f7-924">**Validez no antes**</span><span class="sxs-lookup"><span data-stu-id="161f7-924">**Validity Not Before**</span></span>|
|<span data-ttu-id="161f7-925">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-925"></span></span>|
|<span data-ttu-id="161f7-926">**Validez no después**</span><span class="sxs-lookup"><span data-stu-id="161f7-926">**Validity Not After**</span></span>|
|<span data-ttu-id="161f7-927">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-927"></span></span>|
|<span data-ttu-id="161f7-928">**Identificador de clave de asunto**</span><span class="sxs-lookup"><span data-stu-id="161f7-928">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="161f7-929">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-929"></span></span>|
|<span data-ttu-id="161f7-930">**Identificador de clave de entidad de certificación**</span><span class="sxs-lookup"><span data-stu-id="161f7-930">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="161f7-931">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-931"></span></span>|
|<span data-ttu-id="161f7-932">**Huella digital (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="161f7-932">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="161f7-933">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-933"></span></span>|
|<span data-ttu-id="161f7-934">**Huella digital (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="161f7-934">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="161f7-935">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-935"></span></span>|
|<span data-ttu-id="161f7-936">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="161f7-936">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="161f7-937">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-937"></span></span>|
|<span data-ttu-id="161f7-938">**Direcciones URL CRL**</span><span class="sxs-lookup"><span data-stu-id="161f7-938">**CRL URLs**</span></span>|
|<span data-ttu-id="161f7-939">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-939"></span></span>|
|<span data-ttu-id="161f7-940">**Direcciones URL OCSP**</span><span class="sxs-lookup"><span data-stu-id="161f7-940">**OCSP URLs**</span></span>|
|<span data-ttu-id="161f7-941">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-941"></span></span>|
   
 <span data-ttu-id="161f7-942">**Entidad de certificación de Microsoft IT TLS 2**</span><span class="sxs-lookup"><span data-stu-id="161f7-942">**Microsoft IT TLS CA 2**</span></span>
  
||
|:-----|
|<span data-ttu-id="161f7-943">**Asunto**</span><span class="sxs-lookup"><span data-stu-id="161f7-943">**Subject**</span></span>|
|<span data-ttu-id="161f7-944">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-944"></span></span>|
|<span data-ttu-id="161f7-945">**Emisor**</span><span class="sxs-lookup"><span data-stu-id="161f7-945">**Issuer**</span></span>|
|<span data-ttu-id="161f7-946">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-946"></span></span>|
|<span data-ttu-id="161f7-947">**Número de serie**</span><span class="sxs-lookup"><span data-stu-id="161f7-947">**Serial Number**</span></span>|
|<span data-ttu-id="161f7-948">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-948"></span></span>|
|<span data-ttu-id="161f7-949">**Longitud de clave pública**</span><span class="sxs-lookup"><span data-stu-id="161f7-949">**Public Key Length**</span></span>|
|<span data-ttu-id="161f7-950">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-950"></span></span>|
|<span data-ttu-id="161f7-951">**Algoritmo de firma**</span><span class="sxs-lookup"><span data-stu-id="161f7-951">**Signature Algorithm**</span></span>|
|<span data-ttu-id="161f7-952">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-952"></span></span>|
|<span data-ttu-id="161f7-953">**Validez no antes**</span><span class="sxs-lookup"><span data-stu-id="161f7-953">**Validity Not Before**</span></span>|
|<span data-ttu-id="161f7-954">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-954"></span></span>|
|<span data-ttu-id="161f7-955">**Validez no después**</span><span class="sxs-lookup"><span data-stu-id="161f7-955">**Validity Not After**</span></span>|
|<span data-ttu-id="161f7-956">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-956"></span></span>|
|<span data-ttu-id="161f7-957">**Identificador de clave de asunto**</span><span class="sxs-lookup"><span data-stu-id="161f7-957">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="161f7-958">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-958"></span></span>|
|<span data-ttu-id="161f7-959">**Identificador de clave de entidad de certificación**</span><span class="sxs-lookup"><span data-stu-id="161f7-959">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="161f7-960">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-960"></span></span>|
|<span data-ttu-id="161f7-961">**Huella digital (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="161f7-961">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="161f7-962">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-962"></span></span>|
|<span data-ttu-id="161f7-963">**Huella digital (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="161f7-963">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="161f7-964">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-964"></span></span>|
|<span data-ttu-id="161f7-965">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="161f7-965">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="161f7-966">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-966"></span></span>|
|<span data-ttu-id="161f7-967">**Direcciones URL CRL**</span><span class="sxs-lookup"><span data-stu-id="161f7-967">**CRL URLs**</span></span>|
|<span data-ttu-id="161f7-968">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-968"></span></span>|
|<span data-ttu-id="161f7-969">**Direcciones URL OCSP**</span><span class="sxs-lookup"><span data-stu-id="161f7-969">**OCSP URLs**</span></span>|
|<span data-ttu-id="161f7-970">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-970"></span></span>|
   
 <span data-ttu-id="161f7-971">**Entidad de certificación de Microsoft IT TLS 4**</span><span class="sxs-lookup"><span data-stu-id="161f7-971">**Microsoft IT TLS CA 4**</span></span>
  
||
|:-----|
|<span data-ttu-id="161f7-972">**Asunto**</span><span class="sxs-lookup"><span data-stu-id="161f7-972">**Subject**</span></span>|
|<span data-ttu-id="161f7-973">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-973"></span></span>|
|<span data-ttu-id="161f7-974">**Emisor**</span><span class="sxs-lookup"><span data-stu-id="161f7-974">**Issuer**</span></span>|
|<span data-ttu-id="161f7-975">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-975"></span></span>|
|<span data-ttu-id="161f7-976">**Número de serie**</span><span class="sxs-lookup"><span data-stu-id="161f7-976">**Serial Number**</span></span>|
|<span data-ttu-id="161f7-977">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-977"></span></span>|
|<span data-ttu-id="161f7-978">**Longitud de clave pública**</span><span class="sxs-lookup"><span data-stu-id="161f7-978">**Public Key Length**</span></span>|
|<span data-ttu-id="161f7-979">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-979"></span></span>|
|<span data-ttu-id="161f7-980">**Algoritmo de firma**</span><span class="sxs-lookup"><span data-stu-id="161f7-980">**Signature Algorithm**</span></span>|
|<span data-ttu-id="161f7-981">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-981"></span></span>|
|<span data-ttu-id="161f7-982">**Validez no antes**</span><span class="sxs-lookup"><span data-stu-id="161f7-982">**Validity Not Before**</span></span>|
|<span data-ttu-id="161f7-983">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-983"></span></span>|
|<span data-ttu-id="161f7-984">**Validez no después**</span><span class="sxs-lookup"><span data-stu-id="161f7-984">**Validity Not After**</span></span>|
|<span data-ttu-id="161f7-985">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-985"></span></span>|
|<span data-ttu-id="161f7-986">**Identificador de clave de asunto**</span><span class="sxs-lookup"><span data-stu-id="161f7-986">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="161f7-987">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-987"></span></span>|
|<span data-ttu-id="161f7-988">**Identificador de clave de entidad de certificación**</span><span class="sxs-lookup"><span data-stu-id="161f7-988">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="161f7-989">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-989"></span></span>|
|<span data-ttu-id="161f7-990">**Huella digital (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="161f7-990">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="161f7-991">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-991"></span></span>|
|<span data-ttu-id="161f7-992">**Huella digital (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="161f7-992">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="161f7-993">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-993"></span></span>|
|<span data-ttu-id="161f7-994">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="161f7-994">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="161f7-995">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-995"></span></span>|
|<span data-ttu-id="161f7-996">**Direcciones URL CRL**</span><span class="sxs-lookup"><span data-stu-id="161f7-996">**CRL URLs**</span></span>|
|<span data-ttu-id="161f7-997">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-997"></span></span>|
|<span data-ttu-id="161f7-998">**Direcciones URL OCSP**</span><span class="sxs-lookup"><span data-stu-id="161f7-998">**OCSP URLs**</span></span>|
|<span data-ttu-id="161f7-999">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-999"></span></span>|
   
 <span data-ttu-id="161f7-1000">**Entidad de certificación de Microsoft IT TLS 5**</span><span class="sxs-lookup"><span data-stu-id="161f7-1000">**Microsoft IT TLS CA 5**</span></span>
  
||
|:-----|
|<span data-ttu-id="161f7-1001">**Asunto**</span><span class="sxs-lookup"><span data-stu-id="161f7-1001">**Subject**</span></span>|
|<span data-ttu-id="161f7-1002">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-1002"></span></span>|
|<span data-ttu-id="161f7-1003">**Emisor**</span><span class="sxs-lookup"><span data-stu-id="161f7-1003">**Issuer**</span></span>|
|<span data-ttu-id="161f7-1004">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-1004"></span></span>|
|<span data-ttu-id="161f7-1005">**Número de serie**</span><span class="sxs-lookup"><span data-stu-id="161f7-1005">**Serial Number**</span></span>|
|<span data-ttu-id="161f7-1006">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-1006"></span></span>|
|<span data-ttu-id="161f7-1007">**Longitud de clave pública**</span><span class="sxs-lookup"><span data-stu-id="161f7-1007">**Public Key Length**</span></span>|
|<span data-ttu-id="161f7-1008">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-1008"></span></span>|
|<span data-ttu-id="161f7-1009">**Algoritmo de firma**</span><span class="sxs-lookup"><span data-stu-id="161f7-1009">**Signature Algorithm**</span></span>|
|<span data-ttu-id="161f7-1010">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-1010"></span></span>|
|<span data-ttu-id="161f7-1011">**Validez no antes**</span><span class="sxs-lookup"><span data-stu-id="161f7-1011">**Validity Not Before**</span></span>|
|<span data-ttu-id="161f7-1012">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-1012"></span></span>|
|<span data-ttu-id="161f7-1013">**Validez no después**</span><span class="sxs-lookup"><span data-stu-id="161f7-1013">**Validity Not After**</span></span>|
|<span data-ttu-id="161f7-1014">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-1014"></span></span>|
|<span data-ttu-id="161f7-1015">**Identificador de clave de asunto**</span><span class="sxs-lookup"><span data-stu-id="161f7-1015">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="161f7-1016">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-1016"></span></span>|
|<span data-ttu-id="161f7-1017">**Identificador de clave de entidad de certificación**</span><span class="sxs-lookup"><span data-stu-id="161f7-1017">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="161f7-1018">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-1018"></span></span>|
|<span data-ttu-id="161f7-1019">**Huella digital (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="161f7-1019">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="161f7-1020">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-1020"></span></span>|
|<span data-ttu-id="161f7-1021">**Huella digital (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="161f7-1021">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="161f7-1022">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-1022"></span></span>|
|<span data-ttu-id="161f7-1023">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="161f7-1023">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="161f7-1024">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-1024"></span></span>|
|<span data-ttu-id="161f7-1025">**Direcciones URL CRL**</span><span class="sxs-lookup"><span data-stu-id="161f7-1025">**CRL URLs**</span></span>|
|<span data-ttu-id="161f7-1026">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-1026"></span></span>|
|<span data-ttu-id="161f7-1027">**Direcciones URL OCSP**</span><span class="sxs-lookup"><span data-stu-id="161f7-1027">**OCSP URLs**</span></span>|
|<span data-ttu-id="161f7-1028">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-1028"></span></span>|
   
 <span data-ttu-id="161f7-1029">**Entidad de certificación de Symantec clase de 3 EV SSL - G3**</span><span class="sxs-lookup"><span data-stu-id="161f7-1029">**Symantec Class 3 EV SSL CA - G3**</span></span>
  
||
|:-----|
|<span data-ttu-id="161f7-1030">**Asunto**</span><span class="sxs-lookup"><span data-stu-id="161f7-1030">**Subject**</span></span>|
|<span data-ttu-id="161f7-1031">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-1031"></span></span>|
|<span data-ttu-id="161f7-1032">**Emisor**</span><span class="sxs-lookup"><span data-stu-id="161f7-1032">**Issuer**</span></span>|
|<span data-ttu-id="161f7-1033">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-1033"></span></span>|
|<span data-ttu-id="161f7-1034">**Nombre alternativo del sujeto**</span><span class="sxs-lookup"><span data-stu-id="161f7-1034">**Subject Alternative Name**</span></span>|
|<span data-ttu-id="161f7-1035">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-1035"></span></span>|
|<span data-ttu-id="161f7-1036">**Número de serie**</span><span class="sxs-lookup"><span data-stu-id="161f7-1036">**Serial Number**</span></span>|
|<span data-ttu-id="161f7-1037">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-1037"></span></span>|
|<span data-ttu-id="161f7-1038">**Longitud de clave pública**</span><span class="sxs-lookup"><span data-stu-id="161f7-1038">**Public Key Length**</span></span>|
|<span data-ttu-id="161f7-1039">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-1039"></span></span>|
|<span data-ttu-id="161f7-1040">**Algoritmo de firma**</span><span class="sxs-lookup"><span data-stu-id="161f7-1040">**Signature Algorithm**</span></span>|
|<span data-ttu-id="161f7-1041">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-1041"></span></span>|
|<span data-ttu-id="161f7-1042">**Validez no antes**</span><span class="sxs-lookup"><span data-stu-id="161f7-1042">**Validity Not Before**</span></span>|
|<span data-ttu-id="161f7-1043">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-1043"></span></span>|
|<span data-ttu-id="161f7-1044">**Validez no después**</span><span class="sxs-lookup"><span data-stu-id="161f7-1044">**Validity Not After**</span></span>|
|<span data-ttu-id="161f7-1045">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-1045"></span></span>|
|<span data-ttu-id="161f7-1046">**Identificador de clave de asunto**</span><span class="sxs-lookup"><span data-stu-id="161f7-1046">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="161f7-1047">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-1047"></span></span>|
|<span data-ttu-id="161f7-1048">**Identificador de clave de entidad de certificación**</span><span class="sxs-lookup"><span data-stu-id="161f7-1048">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="161f7-1049">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-1049"></span></span>|
|<span data-ttu-id="161f7-1050">**Huella digital (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="161f7-1050">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="161f7-1051">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-1051"></span></span>|
|<span data-ttu-id="161f7-1052">**Huella digital (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="161f7-1052">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="161f7-1053">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-1053"></span></span>|
|<span data-ttu-id="161f7-1054">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="161f7-1054">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="161f7-1055">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-1055"></span></span>|
|<span data-ttu-id="161f7-1056">**Direcciones URL CRL**</span><span class="sxs-lookup"><span data-stu-id="161f7-1056">**CRL URLs**</span></span>|
|<span data-ttu-id="161f7-1057">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-1057"></span></span>|
|<span data-ttu-id="161f7-1058">**Direcciones URL OCSP**</span><span class="sxs-lookup"><span data-stu-id="161f7-1058">**OCSP URLs**</span></span>|
|<span data-ttu-id="161f7-1059">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-1059"></span></span>|
   
 <span data-ttu-id="161f7-1060">**Clase Symantec 3 servidores seguros CA - G4**</span><span class="sxs-lookup"><span data-stu-id="161f7-1060">**Symantec Class 3 Secure Server CA - G4**</span></span>
  
||
|:-----|
|<span data-ttu-id="161f7-1061">**Asunto**</span><span class="sxs-lookup"><span data-stu-id="161f7-1061">**Subject**</span></span>|
|<span data-ttu-id="161f7-1062">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-1062"></span></span>|
|<span data-ttu-id="161f7-1063">**Emisor**</span><span class="sxs-lookup"><span data-stu-id="161f7-1063">**Issuer**</span></span>|
|<span data-ttu-id="161f7-1064">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-1064"></span></span>|
|<span data-ttu-id="161f7-1065">**Nombre alternativo del sujeto**</span><span class="sxs-lookup"><span data-stu-id="161f7-1065">**Subject Alternative Name**</span></span>|
|<span data-ttu-id="161f7-1066">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-1066"></span></span>|
|<span data-ttu-id="161f7-1067">**Número de serie**</span><span class="sxs-lookup"><span data-stu-id="161f7-1067">**Serial Number**</span></span>|
|<span data-ttu-id="161f7-1068">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-1068"></span></span>|
|<span data-ttu-id="161f7-1069">**Longitud de clave pública**</span><span class="sxs-lookup"><span data-stu-id="161f7-1069">**Public Key Length**</span></span>|
|<span data-ttu-id="161f7-1070">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-1070"></span></span>|
|<span data-ttu-id="161f7-1071">**Algoritmo de firma**</span><span class="sxs-lookup"><span data-stu-id="161f7-1071">**Signature Algorithm**</span></span>|
|<span data-ttu-id="161f7-1072">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-1072"></span></span>|
|<span data-ttu-id="161f7-1073">**Validez no antes**</span><span class="sxs-lookup"><span data-stu-id="161f7-1073">**Validity Not Before**</span></span>|
|<span data-ttu-id="161f7-1074">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-1074"></span></span>|
|<span data-ttu-id="161f7-1075">**Validez no después**</span><span class="sxs-lookup"><span data-stu-id="161f7-1075">**Validity Not After**</span></span>|
|<span data-ttu-id="161f7-1076">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-1076"></span></span>|
|<span data-ttu-id="161f7-1077">**Identificador de clave de asunto**</span><span class="sxs-lookup"><span data-stu-id="161f7-1077">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="161f7-1078">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-1078"></span></span>|
|<span data-ttu-id="161f7-1079">**Identificador de clave de entidad de certificación**</span><span class="sxs-lookup"><span data-stu-id="161f7-1079">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="161f7-1080">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-1080"></span></span>|
|<span data-ttu-id="161f7-1081">**Huella digital (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="161f7-1081">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="161f7-1082">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-1082"></span></span>|
|<span data-ttu-id="161f7-1083">**Huella digital (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="161f7-1083">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="161f7-1084">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-1084"></span></span>|
|<span data-ttu-id="161f7-1085">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="161f7-1085">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="161f7-1086">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-1086"></span></span>|
|<span data-ttu-id="161f7-1087">**Direcciones URL CRL**</span><span class="sxs-lookup"><span data-stu-id="161f7-1087">**CRL URLs**</span></span>|
|<span data-ttu-id="161f7-1088">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-1088"></span></span>|
|<span data-ttu-id="161f7-1089">**Direcciones URL OCSP**</span><span class="sxs-lookup"><span data-stu-id="161f7-1089">**OCSP URLs**</span></span>|
|<span data-ttu-id="161f7-1090">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-1090"></span></span>|
   
 <span data-ttu-id="161f7-1091">**Thawte SHA256 SSL entidad emisora de certificados**</span><span class="sxs-lookup"><span data-stu-id="161f7-1091">**thawte SHA256 SSL CA**</span></span>
  
||
|:-----|
|<span data-ttu-id="161f7-1092">**Asunto**</span><span class="sxs-lookup"><span data-stu-id="161f7-1092">**Subject**</span></span>|
|<span data-ttu-id="161f7-1093">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-1093"></span></span>|
|<span data-ttu-id="161f7-1094">**Emisor**</span><span class="sxs-lookup"><span data-stu-id="161f7-1094">**Issuer**</span></span>|
|<span data-ttu-id="161f7-1095">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-1095"></span></span>|
|<span data-ttu-id="161f7-1096">**Nombre alternativo del sujeto**</span><span class="sxs-lookup"><span data-stu-id="161f7-1096">**Subject Alternative Name**</span></span>|
|<span data-ttu-id="161f7-1097">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-1097"></span></span>|
|<span data-ttu-id="161f7-1098">**Número de serie**</span><span class="sxs-lookup"><span data-stu-id="161f7-1098">**Serial Number**</span></span>|
|<span data-ttu-id="161f7-1099">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-1099"></span></span>|
|<span data-ttu-id="161f7-1100">**Longitud de clave pública**</span><span class="sxs-lookup"><span data-stu-id="161f7-1100">**Public Key Length**</span></span>|
|<span data-ttu-id="161f7-1101">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-1101"></span></span>|
|<span data-ttu-id="161f7-1102">**Algoritmo de firma**</span><span class="sxs-lookup"><span data-stu-id="161f7-1102">**Signature Algorithm**</span></span>|
|<span data-ttu-id="161f7-1103">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-1103"></span></span>|
|<span data-ttu-id="161f7-1104">**Validez no antes**</span><span class="sxs-lookup"><span data-stu-id="161f7-1104">**Validity Not Before**</span></span>|
|<span data-ttu-id="161f7-1105">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-1105"></span></span>|
|<span data-ttu-id="161f7-1106">**Validez no después**</span><span class="sxs-lookup"><span data-stu-id="161f7-1106">**Validity Not After**</span></span>|
|<span data-ttu-id="161f7-1107">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-1107"></span></span>|
|<span data-ttu-id="161f7-1108">**Identificador de clave de asunto**</span><span class="sxs-lookup"><span data-stu-id="161f7-1108">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="161f7-1109">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-1109"></span></span>|
|<span data-ttu-id="161f7-1110">**Identificador de clave de entidad de certificación**</span><span class="sxs-lookup"><span data-stu-id="161f7-1110">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="161f7-1111">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-1111"></span></span>|
|<span data-ttu-id="161f7-1112">**Huella digital (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="161f7-1112">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="161f7-1113">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-1113"></span></span>|
|<span data-ttu-id="161f7-1114">**Huella digital (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="161f7-1114">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="161f7-1115">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-1115"></span></span>|
|<span data-ttu-id="161f7-1116">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="161f7-1116">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="161f7-1117">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-1117"></span></span>|
|<span data-ttu-id="161f7-1118">**Direcciones URL CRL**</span><span class="sxs-lookup"><span data-stu-id="161f7-1118">**CRL URLs**</span></span>|
|<span data-ttu-id="161f7-1119">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-1119"></span></span>|
|<span data-ttu-id="161f7-1120">**Direcciones URL OCSP**</span><span class="sxs-lookup"><span data-stu-id="161f7-1120">**OCSP URLs**</span></span>|
|<span data-ttu-id="161f7-1121">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-1121"></span></span>|
   
 <span data-ttu-id="161f7-1122">**Entidad emisora de certificados SureServer de Verizon Akamai G14-SHA2**</span><span class="sxs-lookup"><span data-stu-id="161f7-1122">**Verizon Akamai SureServer CA G14-SHA2**</span></span>
  
||
|:-----|
|<span data-ttu-id="161f7-1123">**Asunto**</span><span class="sxs-lookup"><span data-stu-id="161f7-1123">**Subject**</span></span>|
|<span data-ttu-id="161f7-1124">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-1124"></span></span>|
|<span data-ttu-id="161f7-1125">**Emisor**</span><span class="sxs-lookup"><span data-stu-id="161f7-1125">**Issuer**</span></span>|
|<span data-ttu-id="161f7-1126">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-1126"></span></span>|
|<span data-ttu-id="161f7-1127">**Número de serie**</span><span class="sxs-lookup"><span data-stu-id="161f7-1127">**Serial Number**</span></span>|
|<span data-ttu-id="161f7-1128">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-1128"></span></span>|
|<span data-ttu-id="161f7-1129">**Longitud de clave pública**</span><span class="sxs-lookup"><span data-stu-id="161f7-1129">**Public Key Length**</span></span>|
|<span data-ttu-id="161f7-1130">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-1130"></span></span>|
|<span data-ttu-id="161f7-1131">**Algoritmo de firma**</span><span class="sxs-lookup"><span data-stu-id="161f7-1131">**Signature Algorithm**</span></span>|
|<span data-ttu-id="161f7-1132">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-1132"></span></span>|
|<span data-ttu-id="161f7-1133">**Validez no antes**</span><span class="sxs-lookup"><span data-stu-id="161f7-1133">**Validity Not Before**</span></span>|
|<span data-ttu-id="161f7-1134">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-1134"></span></span>|
|<span data-ttu-id="161f7-1135">**Validez no después**</span><span class="sxs-lookup"><span data-stu-id="161f7-1135">**Validity Not After**</span></span>|
|<span data-ttu-id="161f7-1136">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-1136"></span></span>|
|<span data-ttu-id="161f7-1137">**Identificador de clave de asunto**</span><span class="sxs-lookup"><span data-stu-id="161f7-1137">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="161f7-1138">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-1138"></span></span>|
|<span data-ttu-id="161f7-1139">**Identificador de clave de entidad de certificación**</span><span class="sxs-lookup"><span data-stu-id="161f7-1139">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="161f7-1140">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-1140"></span></span>|
|<span data-ttu-id="161f7-1141">**Huella digital (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="161f7-1141">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="161f7-1142">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-1142"></span></span>|
|<span data-ttu-id="161f7-1143">**Huella digital (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="161f7-1143">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="161f7-1144">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-1144"></span></span>|
|<span data-ttu-id="161f7-1145">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="161f7-1145">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="161f7-1146">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-1146"></span></span>|
|<span data-ttu-id="161f7-1147">**Direcciones URL AIA**</span><span class="sxs-lookup"><span data-stu-id="161f7-1147">**AIA URLs**</span></span>|
|<span data-ttu-id="161f7-1148">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-1148"></span></span>|
|<span data-ttu-id="161f7-1149">**Direcciones URL CRL**</span><span class="sxs-lookup"><span data-stu-id="161f7-1149">**CRL URLs**</span></span>|
|<span data-ttu-id="161f7-1150">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-1150"></span></span>|
|<span data-ttu-id="161f7-1151">**Direcciones URL OCSP**</span><span class="sxs-lookup"><span data-stu-id="161f7-1151">**OCSP URLs**</span></span>|
|<span data-ttu-id="161f7-1152">:-----</span><span class="sxs-lookup"><span data-stu-id="161f7-1152"></span></span>|
   
## <a name="additional-certificate-paths"></a><span data-ttu-id="161f7-1153">Rutas de acceso del certificado adicional</span><span class="sxs-lookup"><span data-stu-id="161f7-1153">Additional certificate paths</span></span>
<span data-ttu-id="161f7-1154"><a name="IntermediateCerts"> </a></span><span class="sxs-lookup"><span data-stu-id="161f7-1154"></span></span>

<span data-ttu-id="161f7-1155">El siguiente incluir certificados heredados que no se incluyen por encima y se combinarán con la lista de arriba a través del tiempo.</span><span class="sxs-lookup"><span data-stu-id="161f7-1155">The following include legacy certificates that aren't included above and will be merged with the list above over time.</span></span>
  
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


