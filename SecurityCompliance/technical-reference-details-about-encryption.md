---
title: Información de referencia técnica sobre el cifrado en Office 365
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 4/12/2018
ms.audience: ITPro
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MET150
- MOE150
ms.assetid: 862cbe93-4268-4ef9-ba79-277545ecf221
description: Ver detalles técnicos acerca de cifrado en Office 365.
ms.openlocfilehash: d86692119f7558d74e2083165b4eb6ab4a07da70
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22536599"
---
# <a name="technical-reference-details-about-encryption-in-office-365"></a>Información de referencia técnica sobre el cifrado en Office 365

Consulte este artículo para obtener más información acerca de los certificados, las tecnologías y TLS conjuntos de cifrado utilizadas para el [cifrado en Office 365](encryption.md). En este artículo también proporciona detalles sobre desuso planeada.
  
- Si está buscando información general, vea [cifrado en Office 365](encryption.md).
    
- Si está buscando información de configuración, vea [Configurar el cifrado en Office 365 Enterprise](set-up-encryption.md).
    
## <a name="microsoft-office-365-certificate-ownership-and-management"></a>Propiedad y administración de certificados de Microsoft Office 365

No es necesario comprar ni mantener certificados para Office 365 porque Microsoft usa sus propios certificados.
  
## <a name="current-encryption-standards-and-planned-deprecations"></a>Los estándares de cifrado actual y el desuso planeado

Para poder continuar proporcionar mejores en su clase cifrado para Office 365, Microsoft revisa con regularidad cifrado compatible con estándares. En ocasiones, es necesario dejar de utilizar los estándares antiguo como estén caducada y, por tanto, es menos segura. Este tema describe los conjuntos de cifrado compatibles actualmente y otros estándares así como detalles sobre desuso planeada.
  
## <a name="versions-of-tls-supported-by-office-365"></a>Versiones de TLS admitidas por Office 365

TLS (Seguridad de la capa de transporte) y SSL (antecesor de TLS) son protocolos criptográficos que protegen la comunicación por red con certificados de seguridad que cifran una conexión entre equipos. Office 365 es compatible con las siguientes versiones de TLS:
  
- TLS versión 1.2 (TLS 1.2)
    
- TLS versión 1.1 (TLS 1.1)
    
- TLS versión 1.0 (TLS 1.0)
    
 Compatibilidad con TLS 1.0 y 1.1 de TLS quedará obsoleto el 31 de octubre de 2018. Para obtener más información, vea [compatibilidad con Deprecating para TLS 1.0, 1.1 y lo que esto significa para usted](technical-reference-details-about-encryption.md#TLS11and12deprecation) . 
  
## <a name="deprecating-support-for-tls-10-and-11-and-what-this-means-for-you"></a>Dejar obsoletos soporte para TLS 1.0 y 1.1 y lo que esto significa para usted
<a name="TLS11and12deprecation"> </a>

Llegan los cambios importantes para opciones de cifrado compatibles de Office 365. A partir del 31 de octubre de 2018, Office 365 ya no se admite el uso de TLS 1.0 o 1.1 para la comunicación de Office 365. Una vez que Office 365 deprecates soporte técnico para estos protocolos, toda la comunicación a y desde los servidores de Office 365 tendrá que utilizar TLS 1.2. Para obtener información acerca de cómo esto afecta, vea [Preparar el uso obligatorio de TLS 1.2 en Office 365](https://support.microsoft.com/en-us/help/4057306/preparing-for-tls-1-2-in-office-365). Los servidores y los clientes que se comuniquen con Office 365 después de esta fecha deben admitir TLS 1.2.
  
## <a name="deprecating-support-for-3des"></a>Compatibilidad con dejar obsoletos 3DES
<a name="TLS11and12deprecation"> </a>

A partir del 31 de octubre de 2018, Office 365 ya no se admite el uso de conjuntos de cifrado 3DES para la comunicación de Office 365. Más concretamente, Office 365 ya no se admite el conjunto de cifrado TLS_RSA_WITH_3DES_EDE_CBC_SHA. Los clientes y servidores comunicar con Office 365 después de esta fecha debe admitir al menos uno de los datos cifrados más seguros que aparecen en este tema (vea [conjuntos de aplicaciones compatibles con Office 365 de cifrado TLS](technical-reference-details-about-encryption.md#TLSCipherSuites)).
  
## <a name="deprecating-sha-1-certificate-support-in-office-365"></a>Desuso de la compatibilidad con certificados SHA-1 en Office 365
<a name="TLS11and12deprecation"> </a>

A partir de junio de 2016, Office 365 ya no se acepta un certificado SHA-1 para las conexiones entrantes o salientes. Si actualmente está utilizando un certificado con SHA-1 en la cadena de certificados, debe actualizar la cadena para usar SHA-2 (2 de algoritmo de Hash seguro) o un algoritmo de hash más seguro.
  
## <a name="deprecating-rc4-support-in-office-365"></a>Desuso de la compatibilidad con RC4 en Office 365
<a name="TLS11and12deprecation"> </a>

En julio de 2015, se interrumpió la compatibilidad con los siguientes conjuntos de cifrado RC4:
  
- TLS_RSA_WITH_RC4_128_SHA
    
- TLS_RSA_WITH_RC4_128_MD5
    
## <a name="deprecating-secure-sockets-layer-ssl-30-support-in-office-365"></a>Dejar obsoletos compatibilidad con la capa de Sockets seguros (SSL) 3.0 en Office 365
<a name="TLS11and12deprecation"> </a>

Iniciar el 1 de diciembre de 2014, Office 365 comenzó deshabilitar compatibilidad para Secure Sockets Layer (SSL) 3.0, el predecesor de TLS. Para obtener más información, vea [seguridad asesoramiento al 3009008](https://technet.microsoft.com/library/security/3009008.aspx). Para obtener instrucciones sobre cómo asegurar los clientes usan TLS 1.0 o superior y para deshabilitar SSL 3.0, consulte [protección SSL 3.0 vulnerabilidad](http://blogs.office.com/2014/10/29/protecting-ssl-3-0-vulnerability/).
  
## <a name="tls-cipher-suites-supported-by-office-365"></a>Conjuntos de aplicaciones de cifrado TLS compatibles con Office 365
<a name="TLSCipherSuites"> </a>

Un conjunto de cifrado es una colección de algoritmos de cifrado que TLS emplea para establecer conexiones seguras. Los conjuntos de cifrado compatibles con Office 365 se enumeran en la siguiente tabla por orden de seguridad, con el conjunto de cifrado más seguro en primer lugar. Cuando Office 365 recibe una solicitud de conexión, primero intenta conectarse con el conjunto de cifrado de nivel superior y, si no lo consigue, prueba con el segundo conjunto de cifrado de la lista y así sucesivamente. Cuando Office 365 envía una solicitud de conexión a otro servidor o a un cliente, el servidor o el cliente receptor elige el conjunto de cifrado o si se va a usar TLS.
  
|**Protocolos**|**Nombre del conjunto de cifrado**|**Algoritmo de intercambio de claves o seguridad**|**Compatibilidad con Confidencialidad directa total**|**Algoritmo de autenticación o seguridad**|**Cifrado o seguridad**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|TLS 1.2  <br/> |TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA384_P384  <br/> |ECDH/192  <br/> |Sí  <br/> |RSA/112  <br/> |AES/256  <br/> |
|TLS 1.2  <br/> |TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA256_P256  <br/> |ECDH/128  <br/> |Sí  <br/> |RSA/112  <br/> |AES/128  <br/> |
|TLS 1.0, 1.1, 1.2  <br/> |TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA_P384  <br/> |ECDH/192  <br/> |Sí  <br/> |RSA/112  <br/> |AES/256  <br/> |
|TLS 1.0, 1.1, 1.2  <br/> |TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA_P256  <br/> |ECDH/128  <br/> |Sí  <br/> |RSA/112  <br/> |AES/128  <br/> |
|TLS 1.2  <br/> |TLS_RSA_WITH_AES_256_CBC_SHA256  <br/> |RSA/112  <br/> |No  <br/> |RSA/112  <br/> |AES/256  <br/> |
|TLS 1.2  <br/> |TLS_RSA_WITH_AES_128_CBC_SHA256  <br/> |RSA/112  <br/> |No  <br/> |RSA/112  <br/> |AES/128  <br/> |
|TLS 1.0, 1.1, 1.2  <br/> |TLS_RSA_WITH_AES_256_CBC_SHA  <br/> |RSA/112  <br/> |No  <br/> |RSA/112  <br/> |AES/256  <br/> |
|TLS 1.0, 1.1, 1.2  <br/> |TLS_RSA_WITH_AES_128_CBC_SHA  <br/> |RSA/112  <br/> |No  <br/> |RSA/112  <br/> |AES/128  <br/> |
|TLS 1.0, 1.1, 1.2  <br/> |TLS_RSA_WITH_3DES_EDE_CBC_SHA  <br/> |RSA/112  <br/> |No  <br/> |RSA/112  <br/> |3DES/192  <br/> |
   
## <a name="related-topics"></a>Temas relacionados
<a name="TLSCipherSuites"> </a>

[Cifrado en Office 365](encryption.md)
  
[Configurar el cifrado en Office 365 Enterprise](set-up-encryption.md)
  
[Implementación de Schannel de TLS 1.0 en actualización de estado de seguridad de Windows: 24 de noviembre de 2015](https://support.microsoft.com/kb/3117336)
  
[Mejoras de cifrado TLS/SSL (Windows IT Center)](https://technet.microsoft.com/en-us/library/cc766285%28v=ws.10%29.aspx)
  

