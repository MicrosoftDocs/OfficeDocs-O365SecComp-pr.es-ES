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
# <a name="office-365-certificate-chains"></a>Cadenas de certificados de Office 365

Office 365 aprovecha un número de proveedores de certificado diferentes. A continuación describe la lista completa de certificados de raíz de Office 365 conocidos que pueden encontrar los clientes al obtener acceso a Office 365. Para obtener información sobre los certificados que necesita instalar en su propia infraestructura, consulte [Plan para los certificados SSL de terceros para Office 365](https://support.office.com/article/b48cdf63-07e0-4cda-8c12-4871590f59ce). La siguiente información del certificado se aplica a todas las instancias de la nube en todo el mundo y nacionales de Office 365.
  

|**Tipo de certificado**|**Descarga de P7b**|**Extremos CRL**|**Extremos OCSP**|**Extremos AIA**|
|:-----|:-----|:-----|:-----|:-----|
|[Certificados raíz de confianza públicamente](https://support.office.com/article/0c03e6b3-e73f-4316-9e2b-bf4091ae96bb#rootcerts) <br/> |[Agrupación de certificado raíz de Office 365 (P7B)](http://download.microsoft.com/download/A/5/A/A5AE01F3-D19B-4A11-9407-801263CEF72C/O365_Root_Certs_20170321.p7b) <br/> |CRL.GlobalSign.NET  <br/> www.d-Trust.NET  <br/> |N/D  <br/> |N/D  <br/> |
|[Los certificados intermedios de confianza públicamente](https://support.office.com/article/0c03e6b3-e73f-4316-9e2b-bf4091ae96bb#IntermediateCerts) <br/> |[Agrupación de certificados intermedios de Office 365 (P7B)](http://download.microsoft.com/download/4/D/5/4D5339A4-0A4A-46AB-AE52-B179DEDA4BEC/O365_Intermediate_Certs_20170321.p7b)  <br/> |cdp1.Public trust.com  <br/> CRL.cnnic.CN  <br/> CRL.Entrust.NET  <br/> CRL.GlobalSign.com  <br/> CRL.GlobalSign.NET  <br/> CRL.identrust.com  <br/> CRL.Thawte.com  <br/> crl3.digicert.com  <br/> crl4.digicert.com  <br/> s1.symcb.com  <br/> www.d-Trust.NET  <br/> |isrg.trustid.OCSP.identrust.com  <br/> OCSP.digicert.com  <br/> OCSP.Entrust.NET  <br/> OCSP.GlobalSign.com  <br/> OCSP.OmniRoot.com  <br/> OCSP.startssl.com  <br/> OCSP.Thawte.com  <br/> ocsp2.GlobalSign.com  <br/> ocspcnnicroot.cnnic.CN  <br/> raíz-c3-ca2-2009.ocsp.d-trust.net  <br/> root-C3-cA2-EV-2009.OCSP.d-Trust.NET  <br/> s2.symcb.com  <br/> |AIA.startssl.com  <br/> Apps.identrust.com  <br/> CACert.OmniRoot.com  <br/> www.cnnic.CN  <br/> |
   
Expanda la raíz y las secciones intermedias para ver detalles adicionales acerca de los proveedores de certificado.
  
## <a name="office-365-root-certificate-details"></a>Detalles del certificado de raíz de Office 365
<a name="RootCerts"> </a>

 **Baltimore CyberTrust Root**
  
|:-----|
|**Asunto**|
|:-----|
|**Número de serie**|
|:-----|
|**Longitud de clave pública**|
|:-----|
|**Algoritmo de firma**|
|:-----|
|**Validez no antes**|
|:-----|
|**Validez no después**|
|:-----|
|**Identificador de clave de asunto**|
|:-----|
|**Huella digital (SHA-1)**|
|:-----|
|**Huella digital (SHA-256)**|
|:-----|
|**PIN (SHA-256)**|
|:-----|
   
 **RAÍZ DE CNNIC**
  
||
|:-----|
|**Asunto**|
|:-----|
|**Número de serie**|
|:-----|
|**Longitud de clave pública**|
|:-----|
|**Algoritmo de firma**|
|:-----|
|**Validez no antes**|
|:-----|
|**Validez no después**|
|:-----|
|**Identificador de clave de asunto**|
|:-----|
|**Identificador de clave de entidad de certificación**|
|:-----|
|**Huella digital (SHA-1)**|
|:-----|
|**Huella digital (SHA-256)**|
|:-----|
|**PIN (SHA-256)**|
|:-----|
   
 **DigiCert de entidad de certificación raíz Global**
  
||
|:-----|
|**Asunto**|
|:-----|
|**Número de serie**|
|:-----|
|**Longitud de clave pública**|
|:-----|
|**Algoritmo de firma**|
|:-----|
|**Validez no antes**|
|:-----|
|**Validez no después**|
|:-----|
|**Identificador de clave de asunto**|
|:-----|
|**Identificador de clave de entidad de certificación**|
|:-----|
|**Huella digital (SHA-1)**|
|:-----|
|**Huella digital (SHA-256)**|
|:-----|
|**PIN (SHA-256)**|
|:-----|
   
 **Entidad de certificación raíz de DigiCert High Assurance EV**
  
||
|:-----|
|**Asunto**|
|:-----|
|**Número de serie**|
|:-----|
|**Longitud de clave pública**|
|:-----|
|**Algoritmo de firma**|
|:-----|
|**Validez no antes**|
|:-----|
|**Validez no después**|
|:-----|
|**Identificador de clave de asunto**|
|:-----|
|**Identificador de clave de entidad de certificación**|
|:-----|
|**Huella digital (SHA-1)**|
|:-----|
|**Huella digital (SHA-256)**|
|:-----|
|**PIN (SHA-256)**|
|:-----|
   
 **Entidad de certificación de raíz de confianza de D clase 3 2 de 2009**
  
||
|:-----|
|**Asunto**|
|:-----|
|**Número de serie**|
|:-----|
|**Longitud de clave pública**|
|:-----|
|**Algoritmo de firma**|
|:-----|
|**Validez no antes**|
|:-----|
|**Validez no después**|
|:-----|
|**Identificador de clave de asunto**|
|:-----|
|**Huella digital (SHA-1)**|
|:-----|
|**Huella digital (SHA-256)**|
|:-----|
|**PIN (SHA-256)**|
|:-----|
|**Direcciones URL CRL**|
|:-----|
   
 **Entidad de certificación raíz de confianza de D clase 3 2 EV de 2009**
  
||
|:-----|
|**Asunto**|
|:-----|
|**Número de serie**|
|:-----|
|**Longitud de clave pública**|
|:-----|
|**Algoritmo de firma**|
|:-----|
|**Validez no antes**|
|:-----|
|**Validez no después**|
|:-----|
|**Identificador de clave de asunto**|
|:-----|
|**Huella digital (SHA-1)**|
|:-----|
|**Huella digital (SHA-256)**|
|:-----|
|**PIN (SHA-256)**|
|:-----|
|**Direcciones URL CRL**|
|:-----|
   
 **X3 de la entidad de certificación de raíz de horario de verano**
  
||
|:-----|
|**Asunto**|
|:-----|
|**Número de serie**|
|:-----|
|**Longitud de clave pública**|
|:-----|
|**Algoritmo de firma**|
|:-----|
|**Validez no antes**|
|:-----|
|**Validez no después**|
|:-----|
|**Identificador de clave de asunto**|
|:-----|
|**Huella digital (SHA-1)**|
|:-----|
|**Huella digital (SHA-256)**|
|:-----|
|**PIN (SHA-256)**|
|:-----|
   
 **Entrust entidad de certificación raíz - G2**
  
||
|:-----|
|**Asunto**|
|:-----|
|**Número de serie**|
|:-----|
|**Longitud de clave pública**|
|:-----|
|**Algoritmo de firma**|
|:-----|
|**Validez no antes**|
|:-----|
|**Validez no después**|
|:-----|
|**Identificador de clave de asunto**|
|:-----|
|**Huella digital (SHA-1)**|
|:-----|
|**Huella digital (SHA-256)**|
|:-----|
|**PIN (SHA-256)**|
|:-----|
   
 **Entrust.net Certification Authority (2048)**
  
||
|:-----|
|**Asunto**|
|:-----|
|**Número de serie**|
|:-----|
|**Longitud de clave pública**|
|:-----|
|**Algoritmo de firma**|
|:-----|
|**Validez no antes**|
|:-----|
|**Validez no después**|
|:-----|
|**Identificador de clave de asunto**|
|:-----|
|**Huella digital (SHA-1)**|
|:-----|
|**Huella digital (SHA-256)**|
|:-----|
|**PIN (SHA-256)**|
|:-----|
   
 **GlobalSign**
  
||
|:-----|
|**Asunto**|
|:-----|
|**Número de serie**|
|:-----|
|**Longitud de clave pública**|
|:-----|
|**Algoritmo de firma**|
|:-----|
|**Validez no antes**|
|:-----|
|**Validez no después**|
|:-----|
|**Identificador de clave de asunto**|
|:-----|
|**Identificador de clave de entidad de certificación**|
|:-----|
|**Huella digital (SHA-1)**|
|:-----|
|**Huella digital (SHA-256)**|
|:-----|
|**PIN (SHA-256)**|
|:-----|
|**Direcciones URL CRL**|
|:-----|
   
 **GlobalSign Root CA**
  
||
|:-----|
|**Asunto**|
|:-----|
|**Número de serie**|
|:-----|
|**Longitud de clave pública**|
|:-----|
|**Algoritmo de firma**|
|:-----|
|**Validez no antes**|
|:-----|
|**Validez no después**|
|:-----|
|**Identificador de clave de asunto**|
|:-----|
|**Huella digital (SHA-1)**|
|:-----|
|**Huella digital (SHA-256)**|
|:-----|
|**PIN (SHA-256)**|
|:-----|
   
 **Thawte entidad emisora de certificados raíz principal - G3**
  
||
|:-----|
|**Asunto**|
|:-----|
|**Número de serie**|
|:-----|
|**Longitud de clave pública**|
|:-----|
|**Algoritmo de firma**|
|:-----|
|**Validez no antes**|
|:-----|
|**Validez no después**|
|:-----|
|**Identificador de clave de asunto**|
|:-----|
|**Huella digital (SHA-1)**|
|:-----|
|**Huella digital (SHA-256)**|
|:-----|
|**PIN (SHA-256)**|
|:-----|
   
 **Entidad de certificación principal pública de clase 3 de VeriSign - G5**
  
||
|:-----|
|**Asunto**|
|:-----|
|**Número de serie**|
|:-----|
|**Longitud de clave pública**|
|:-----|
|**Algoritmo de firma**|
|:-----|
|**Validez no antes**|
|:-----|
|**Validez no después**|
|:-----|
|**Identificador de clave de asunto**|
|:-----|
|**Huella digital (SHA-1)**|
|:-----|
|**Huella digital (SHA-256)**|
|:-----|
|**PIN (SHA-256)**|
|:-----|
   
## <a name="office-365-intermediate-certificate-details"></a>Detalles del certificado intermedio de Office 365
<a name="IntermediateCerts"> </a>

 **CNNIC SHA256 SSL**
  
||
|:-----|
|**Asunto**|
|:-----|
|**Emisor**|
|:-----|
|**Número de serie**|
|:-----|
|**Longitud de clave pública**|
|:-----|
|**Algoritmo de firma**|
|:-----|
|**Validez no antes**|
|:-----|
|**Validez no después**|
|:-----|
|**Identificador de clave de asunto**|
|:-----|
|**Identificador de clave de entidad de certificación**|
|:-----|
|**Huella digital (SHA-1)**|
|:-----|
|**Huella digital (SHA-256)**|
|:-----|
|**PIN (SHA-256)**|
|:-----|
|**Direcciones URL AIA**|
|:-----|
|**Direcciones URL CRL**|
|:-----|
|**Direcciones URL OCSP**|
|:-----|
   
 **Entidad de certificación de confianza de D SSL clase 3 1 de 2009**
  
||
|:-----|
|**Asunto**|
|:-----|
|**Emisor**|
|:-----|
|**Nombre alternativo del sujeto**|
|:-----|
|**Número de serie**|
|:-----|
|**Longitud de clave pública**|
|:-----|
|**Algoritmo de firma**|
|:-----|
|**Validez no antes**|
|:-----|
|**Validez no después**|
|:-----|
|**Identificador de clave de asunto**|
|:-----|
|**Identificador de clave de entidad de certificación**|
|:-----|
|**Huella digital (SHA-1)**|
|:-----|
|**Huella digital (SHA-256)**|
|:-----|
|**PIN (SHA-256)**|
|:-----|
|**Direcciones URL CRL**|
|:-----|
|**Direcciones URL OCSP**|
|:-----|
   
 **Entidad de certificación de confianza de D SSL clase 3 1 EV 2009**
  
||
|:-----|
|**Asunto**|
|:-----|
|**Emisor**|
|:-----|
|**Nombre alternativo del sujeto**|
|:-----|
|**Número de serie**|
|:-----|
|**Longitud de clave pública**|
|:-----|
|**Algoritmo de firma**|
|:-----|
|**Validez no antes**|
|:-----|
|**Validez no después**|
|:-----|
|**Identificador de clave de asunto**|
|:-----|
|**Identificador de clave de entidad de certificación**|
|:-----|
|**Huella digital (SHA-1)**|
|:-----|
|**Huella digital (SHA-256)**|
|:-----|
|**PIN (SHA-256)**|
|:-----|
|**Direcciones URL CRL**|
|:-----|
|**Direcciones URL OCSP**|
|:-----|
   
 **1 de la entidad emisora de certificados de servicios de nube de DigiCert**
  
||
|:-----|
|**Asunto**|
|:-----|
|**Emisor**|
|:-----|
|**Número de serie**|
|:-----|
|**Longitud de clave pública**|
|:-----|
|**Algoritmo de firma**|
|:-----|
|**Validez no antes**|
|:-----|
|**Validez no después**|
|:-----|
|**Identificador de clave de asunto**|
|:-----|
|**Identificador de clave de entidad de certificación**|
|:-----|
|**Huella digital (SHA-1)**|
|:-----|
|**Huella digital (SHA-256)**|
|:-----|
|**PIN (SHA-256)**|
|:-----|
|**Direcciones URL CRL**|
|:-----|
|**Direcciones URL OCSP**|
|:-----|
   
 **Servidor de seguridad alta DigiCert SHA2 entidad emisora de certificados**
  
||
|:-----|
|**Asunto**|
|:-----|
|**Emisor**|
|:-----|
|**Número de serie**|
|:-----|
|**Longitud de clave pública**|
|:-----|
|**Algoritmo de firma**|
|:-----|
|**Validez no antes**|
|:-----|
|**Validez no después**|
|:-----|
|**Identificador de clave de asunto**|
|:-----|
|**Identificador de clave de entidad de certificación**|
|:-----|
|**Huella digital (SHA-1)**|
|:-----|
|**Huella digital (SHA-256)**|
|:-----|
|**PIN (SHA-256)**|
|:-----|
|**Direcciones URL CRL**|
|:-----|
|**Direcciones URL OCSP**|
|:-----|
   
 **Servidor seguro DigiCert SHA2 entidad emisora de certificados**
  
||
|:-----|
|**Asunto**|
|:-----|
|**Emisor**|
|:-----|
|**Número de serie**|
|:-----|
|**Longitud de clave pública**|
|:-----|
|**Algoritmo de firma**|
|:-----|
|**Validez no antes**|
|:-----|
|**Validez no después**|
|:-----|
|**Identificador de clave de asunto**|
|:-----|
|**Identificador de clave de entidad de certificación**|
|:-----|
|**Huella digital (SHA-1)**|
|:-----|
|**Huella digital (SHA-256)**|
|:-----|
|**PIN (SHA-256)**|
|:-----|
|**Direcciones URL CRL**|
|:-----|
|**Direcciones URL OCSP**|
|:-----|
   
 **Entrust entidad de certificación - L1C**
  
||
|:-----|
|**Asunto**|
|:-----|
|**Emisor**|
|:-----|
|**Número de serie**|
|:-----|
|**Longitud de clave pública**|
|:-----|
|**Algoritmo de firma**|
|:-----|
|**Validez no antes**|
|:-----|
|**Validez no después**|
|:-----|
|**Identificador de clave de asunto**|
|:-----|
|**Identificador de clave de entidad de certificación**|
|:-----|
|**Huella digital (SHA-1)**|
|:-----|
|**Huella digital (SHA-256)**|
|:-----|
|**PIN (SHA-256)**|
|:-----|
|**Direcciones URL CRL**|
|:-----|
|**Direcciones URL OCSP**|
|:-----|
   
 **Entrust entidad de certificación - L1K**
  
||
|:-----|
|**Asunto**|
|:-----|
|**Emisor**|
|:-----|
|**Número de serie**|
|:-----|
|**Longitud de clave pública**|
|:-----|
|**Algoritmo de firma**|
|:-----|
|**Validez no antes**|
|:-----|
|**Validez no después**|
|:-----|
|**Identificador de clave de asunto**|
|:-----|
|**Identificador de clave de entidad de certificación**|
|:-----|
|**Huella digital (SHA-1)**|
|:-----|
|**Huella digital (SHA-256)**|
|:-----|
|**PIN (SHA-256)**|
|:-----|
|**Direcciones URL CRL**|
|:-----|
|**Direcciones URL OCSP**|
|:-----|
   
 **GlobalSign**
  
||
|:-----|
|**Asunto**|
|:-----|
|**Emisor**|
|:-----|
|**Número de serie**|
|:-----|
|**Longitud de clave pública**|
|:-----|
|**Algoritmo de firma**|
|:-----|
|**Validez no antes**|
|:-----|
|**Validez no después**|
|:-----|
|**Identificador de clave de asunto**|
|:-----|
|**Identificador de clave de entidad de certificación**|
|:-----|
|**Huella digital (SHA-1)**|
|:-----|
|**Huella digital (SHA-256)**|
|:-----|
|**PIN (SHA-256)**|
|:-----|
|**Direcciones URL CRL**|
|:-----|
|**Direcciones URL OCSP**|
|:-----|
   
 **GlobalSign extendida Validation CA - SHA256 - G2**
  
||
|:-----|
|**Asunto**|
|:-----|
|**Emisor**|
|:-----|
|**Número de serie**|
|:-----|
|**Longitud de clave pública**|
|:-----|
|**Algoritmo de firma**|
|:-----|
|**Validez no antes**|
|:-----|
|**Validez no después**|
|:-----|
|**Identificador de clave de asunto**|
|:-----|
|**Identificador de clave de entidad de certificación**|
|:-----|
|**Huella digital (SHA-1)**|
|:-----|
|**Huella digital (SHA-256)**|
|:-----|
|**PIN (SHA-256)**|
|:-----|
|**Direcciones URL CRL**|
|:-----|
|**Direcciones URL OCSP**|
|:-----|
   
 **GlobalSign extendida Validation CA - SHA256 - G3**
  
||
|:-----|
|**Asunto**|
|:-----|
|**Emisor**|
|:-----|
|**Número de serie**|
|:-----|
|**Longitud de clave pública**|
|:-----|
|**Algoritmo de firma**|
|:-----|
|**Validez no antes**|
|:-----|
|**Validez no después**|
|:-----|
|**Identificador de clave de asunto**|
|:-----|
|**Identificador de clave de entidad de certificación**|
|:-----|
|**Huella digital (SHA-1)**|
|:-----|
|**Huella digital (SHA-256)**|
|:-----|
|**PIN (SHA-256)**|
|:-----|
|**Direcciones URL CRL**|
|:-----|
|**Direcciones URL OCSP**|
|:-----|
   
 **GlobalSign organización validación CA - SHA256 - G2**
  
||
|:-----|
|**Asunto**|
|:-----|
|**Emisor**|
|:-----|
|**Número de serie**|
|:-----|
|**Longitud de clave pública**|
|:-----|
|**Algoritmo de firma**|
|:-----|
|**Validez no antes**|
|:-----|
|**Validez no después**|
|:-----|
|**Identificador de clave de asunto**|
|:-----|
|**Identificador de clave de entidad de certificación**|
|:-----|
|**Huella digital (SHA-1)**|
|:-----|
|**Huella digital (SHA-256)**|
|:-----|
|**PIN (SHA-256)**|
|:-----|
|**Direcciones URL CRL**|
|:-----|
|**Direcciones URL OCSP**|
|:-----|
   
 **GlobalSign organización validación CA - SHA256 - G2**
  
||
|:-----|
|**Asunto**|
|:-----|
|**Emisor**|
|:-----|
|**Número de serie**|
|:-----|
|**Longitud de clave pública**|
|:-----|
|**Algoritmo de firma**|
|:-----|
|**Validez no antes**|
|:-----|
|**Validez no después**|
|:-----|
|**Identificador de clave de asunto**|
|:-----|
|**Identificador de clave de entidad de certificación**|
|:-----|
|**Huella digital (SHA-1)**|
|:-----|
|**Huella digital (SHA-256)**|
|:-----|
|**PIN (SHA-256)**|
|:-----|
|**Direcciones URL CRL**|
|:-----|
|**Direcciones URL OCSP**|
|:-----|
   
 **Vamos a cifrar autoridad X3**
  
||
|:-----|
|**Asunto**|
|:-----|
|**Emisor**|
|:-----|
|**Número de serie**|
|:-----|
|**Longitud de clave pública**|
|:-----|
|**Algoritmo de firma**|
|:-----|
|**Validez no antes**|
|:-----|
|**Validez no después**|
|:-----|
|**Identificador de clave de asunto**|
|:-----|
|**Identificador de clave de entidad de certificación**|
|:-----|
|**Huella digital (SHA-1)**|
|:-----|
|**Huella digital (SHA-256)**|
|:-----|
|**PIN (SHA-256)**|
|:-----|
|**Direcciones URL AIA**|
|:-----|
|**Direcciones URL CRL**|
|:-----|
|**Direcciones URL OCSP**|
|:-----|
   
 **Microsoft IT SSL SHA2**
  
||
|:-----|
|**Asunto**|
|:-----|
|**Emisor**|
|:-----|
|**Número de serie**|
|:-----|
|**Longitud de clave pública**|
|:-----|
|**Algoritmo de firma**|
|:-----|
|**Validez no antes**|
|:-----|
|**Validez no después**|
|:-----|
|**Identificador de clave de asunto**|
|:-----|
|**Identificador de clave de entidad de certificación**|
|:-----|
|**Huella digital (SHA-1)**|
|:-----|
|**Huella digital (SHA-256)**|
|:-----|
|**PIN (SHA-256)**|
|:-----|
|**Direcciones URL CRL**|
|:-----|
   
 **Microsoft IT SSL SHA2**
  
||
|:-----|
|**Asunto**|
|:-----|
|**Emisor**|
|:-----|
|**Número de serie**|
|:-----|
|**Longitud de clave pública**|
|:-----|
|**Algoritmo de firma**|
|:-----|
|**Validez no antes**|
|:-----|
|**Validez no después**|
|:-----|
|**Identificador de clave de asunto**|
|:-----|
|**Identificador de clave de entidad de certificación**|
|:-----|
|**Huella digital (SHA-1)**|
|:-----|
|**Huella digital (SHA-256)**|
|:-----|
|**PIN (SHA-256)**|
|:-----|
|**Direcciones URL CRL**|
|:-----|
|**Direcciones URL OCSP**|
|:-----|
   
 **Entidad de certificación de Microsoft IT TLS 1**
  
||
|:-----|
|**Asunto**|
|:-----|
|**Emisor**|
|:-----|
|**Número de serie**|
|:-----|
|**Longitud de clave pública**|
|:-----|
|**Algoritmo de firma**|
|:-----|
|**Validez no antes**|
|:-----|
|**Validez no después**|
|:-----|
|**Identificador de clave de asunto**|
|:-----|
|**Identificador de clave de entidad de certificación**|
|:-----|
|**Huella digital (SHA-1)**|
|:-----|
|**Huella digital (SHA-256)**|
|:-----|
|**PIN (SHA-256)**|
|:-----|
|**Direcciones URL CRL**|
|:-----|
|**Direcciones URL OCSP**|
|:-----|
   
 **Entidad de certificación de Microsoft IT TLS 2**
  
||
|:-----|
|**Asunto**|
|:-----|
|**Emisor**|
|:-----|
|**Número de serie**|
|:-----|
|**Longitud de clave pública**|
|:-----|
|**Algoritmo de firma**|
|:-----|
|**Validez no antes**|
|:-----|
|**Validez no después**|
|:-----|
|**Identificador de clave de asunto**|
|:-----|
|**Identificador de clave de entidad de certificación**|
|:-----|
|**Huella digital (SHA-1)**|
|:-----|
|**Huella digital (SHA-256)**|
|:-----|
|**PIN (SHA-256)**|
|:-----|
|**Direcciones URL CRL**|
|:-----|
|**Direcciones URL OCSP**|
|:-----|
   
 **Entidad de certificación de Microsoft IT TLS 4**
  
||
|:-----|
|**Asunto**|
|:-----|
|**Emisor**|
|:-----|
|**Número de serie**|
|:-----|
|**Longitud de clave pública**|
|:-----|
|**Algoritmo de firma**|
|:-----|
|**Validez no antes**|
|:-----|
|**Validez no después**|
|:-----|
|**Identificador de clave de asunto**|
|:-----|
|**Identificador de clave de entidad de certificación**|
|:-----|
|**Huella digital (SHA-1)**|
|:-----|
|**Huella digital (SHA-256)**|
|:-----|
|**PIN (SHA-256)**|
|:-----|
|**Direcciones URL CRL**|
|:-----|
|**Direcciones URL OCSP**|
|:-----|
   
 **Entidad de certificación de Microsoft IT TLS 5**
  
||
|:-----|
|**Asunto**|
|:-----|
|**Emisor**|
|:-----|
|**Número de serie**|
|:-----|
|**Longitud de clave pública**|
|:-----|
|**Algoritmo de firma**|
|:-----|
|**Validez no antes**|
|:-----|
|**Validez no después**|
|:-----|
|**Identificador de clave de asunto**|
|:-----|
|**Identificador de clave de entidad de certificación**|
|:-----|
|**Huella digital (SHA-1)**|
|:-----|
|**Huella digital (SHA-256)**|
|:-----|
|**PIN (SHA-256)**|
|:-----|
|**Direcciones URL CRL**|
|:-----|
|**Direcciones URL OCSP**|
|:-----|
   
 **Entidad de certificación de Symantec clase de 3 EV SSL - G3**
  
||
|:-----|
|**Asunto**|
|:-----|
|**Emisor**|
|:-----|
|**Nombre alternativo del sujeto**|
|:-----|
|**Número de serie**|
|:-----|
|**Longitud de clave pública**|
|:-----|
|**Algoritmo de firma**|
|:-----|
|**Validez no antes**|
|:-----|
|**Validez no después**|
|:-----|
|**Identificador de clave de asunto**|
|:-----|
|**Identificador de clave de entidad de certificación**|
|:-----|
|**Huella digital (SHA-1)**|
|:-----|
|**Huella digital (SHA-256)**|
|:-----|
|**PIN (SHA-256)**|
|:-----|
|**Direcciones URL CRL**|
|:-----|
|**Direcciones URL OCSP**|
|:-----|
   
 **Clase Symantec 3 servidores seguros CA - G4**
  
||
|:-----|
|**Asunto**|
|:-----|
|**Emisor**|
|:-----|
|**Nombre alternativo del sujeto**|
|:-----|
|**Número de serie**|
|:-----|
|**Longitud de clave pública**|
|:-----|
|**Algoritmo de firma**|
|:-----|
|**Validez no antes**|
|:-----|
|**Validez no después**|
|:-----|
|**Identificador de clave de asunto**|
|:-----|
|**Identificador de clave de entidad de certificación**|
|:-----|
|**Huella digital (SHA-1)**|
|:-----|
|**Huella digital (SHA-256)**|
|:-----|
|**PIN (SHA-256)**|
|:-----|
|**Direcciones URL CRL**|
|:-----|
|**Direcciones URL OCSP**|
|:-----|
   
 **Thawte SHA256 SSL entidad emisora de certificados**
  
||
|:-----|
|**Asunto**|
|:-----|
|**Emisor**|
|:-----|
|**Nombre alternativo del sujeto**|
|:-----|
|**Número de serie**|
|:-----|
|**Longitud de clave pública**|
|:-----|
|**Algoritmo de firma**|
|:-----|
|**Validez no antes**|
|:-----|
|**Validez no después**|
|:-----|
|**Identificador de clave de asunto**|
|:-----|
|**Identificador de clave de entidad de certificación**|
|:-----|
|**Huella digital (SHA-1)**|
|:-----|
|**Huella digital (SHA-256)**|
|:-----|
|**PIN (SHA-256)**|
|:-----|
|**Direcciones URL CRL**|
|:-----|
|**Direcciones URL OCSP**|
|:-----|
   
 **Entidad emisora de certificados SureServer de Verizon Akamai G14-SHA2**
  
||
|:-----|
|**Asunto**|
|:-----|
|**Emisor**|
|:-----|
|**Número de serie**|
|:-----|
|**Longitud de clave pública**|
|:-----|
|**Algoritmo de firma**|
|:-----|
|**Validez no antes**|
|:-----|
|**Validez no después**|
|:-----|
|**Identificador de clave de asunto**|
|:-----|
|**Identificador de clave de entidad de certificación**|
|:-----|
|**Huella digital (SHA-1)**|
|:-----|
|**Huella digital (SHA-256)**|
|:-----|
|**PIN (SHA-256)**|
|:-----|
|**Direcciones URL AIA**|
|:-----|
|**Direcciones URL CRL**|
|:-----|
|**Direcciones URL OCSP**|
|:-----|
   
## <a name="additional-certificate-paths"></a>Rutas de acceso del certificado adicional
<a name="IntermediateCerts"> </a>

El siguiente incluir certificados heredados que no se incluyen por encima y se combinarán con la lista de arriba a través del tiempo.
  
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


