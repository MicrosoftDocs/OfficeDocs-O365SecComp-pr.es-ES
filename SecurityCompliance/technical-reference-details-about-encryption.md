---
title: Información de referencia técnica sobre el cifrado en Office 365
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 03/29/2019
audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MET150
- MOE150
ms.assetid: 862cbe93-4268-4ef9-ba79-277545ecf221
description: Vea los detalles técnicos sobre encyption en Office 365.
ms.openlocfilehash: 0ae26aa6a534f0de0923f869acb94d7ee8529f31
ms.sourcegitcommit: 73dcdafb15b462223d1a670c781db260eb73c2f5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/01/2019
ms.locfileid: "36048242"
---
# <a name="technical-reference-details-about-encryption-in-office-365"></a>Información de referencia técnica sobre el cifrado en Office 365

Consulte este artículo para obtener información sobre certificados, tecnologías y conjuntos de cifrado TLS usados para el [cifrado en Office 365](encryption.md). En este artículo también se proporcionan detalles sobre las despreciaciones planeadas.
  
- Si está buscando información general, vea cifrado [en Office 365](encryption.md).
- Si está buscando información de configuración, consulte [configurar el cifrado en Office 365 Enterprise](set-up-encryption.md).
- Para obtener información acerca de los conjuntos de cifrado compatibles con versiones específicas de Windows, consulte [conjuntos de cifrado en TLS/SSL (Schannel SSP)](https://docs.microsoft.com/windows/desktop/SecAuthN/cipher-suites-in-schannel).
    
## <a name="microsoft-office-365-certificate-ownership-and-management"></a>Propiedad y administración de certificados de Microsoft Office 365

No es necesario comprar ni mantener certificados para Office 365 porque Microsoft usa sus propios certificados.
  
## <a name="current-encryption-standards-and-planned-deprecations"></a>Estándares de cifrado actuales y despreciaciones planeadas

Para seguir proporcionando el mejor cifrado de su clase para Office 365, Microsoft revisa regularmente los estándares de cifrado compatibles. A veces, es necesario dejar de usar los estándares anteriores, ya que se han quedado obsoletos y, por lo tanto, son menos seguros. En este tema se describen los conjuntos de cifrado admitidos actualmente y otros estándares, así como detalles sobre las despreciaciones planeadas. 

## <a name="fips-compliance-for-office-365"></a>Cumplimiento de FIPS para Office 365
Todos los conjuntos de programas de cifrado compatibles con Office 365 usan algoritmos aceptables en FIPS 140-2. Office 365 hereda las validaciones FIPS de Windows (a través de Schannel). Para obtener información sobre Schannel, consulte [conjuntos de cifrado en TLS/SSL (Schannel SSP)](https://docs.microsoft.com/windows/desktop/SecAuthN/cipher-suites-in-schannel).
  
## <a name="versions-of-tls-supported-by-office-365"></a>Versiones de TLS admitidas por Office 365

TLS (Seguridad de la capa de transporte) y SSL (antecesor de TLS) son protocolos criptográficos que protegen la comunicación por red con certificados de seguridad que cifran una conexión entre equipos. Office 365 es compatible con las siguientes versiones de TLS:
  
- TLS versión 1.2 (TLS 1.2)
    
- TLS versión 1.1 (TLS 1.1)
    
- TLS versión 1.0 (TLS 1.0)
    
 La compatibilidad con TLS 1,0 y TLS 1,1 estará en desuso el 31 de octubre de 2018. Vea [desuso de la compatibilidad con TLS 1,0 y 1,1 y qué significa para](technical-reference-details-about-encryption.md#TLS11and12deprecation) obtener más información. 
  
## <a name="deprecating-support-for-tls-10-and-11-and-what-this-means-for-you"></a>Desuso de la compatibilidad con TLS 1,0 y 1,1, y lo que esto significa para usted
<a name="TLS11and12deprecation"> </a>

Desde el 31 de octubre de 2018, Office 365 ya no admite TLS 1,0 y 1,1. Esto significa que Microsoft no corregirá los nuevos problemas que se encuentren en los clientes, dispositivos o servicios que se conectan a Office 365 mediante TLS 1,0 y 1,1.

Nota Esto no significa que Office 365 bloqueará las conexiones TLS 1,0 y 1,1. 

TLS 1,0 y TLS 1,1 quedarán obsoletos oficialmente en las fechas siguientes:
- 1 de junio de 2020 para clientes en los entornos de todo el mundo y GCC.
- 15 de enero de 2020 para los clientes en los entornos soberanos altos y DoD de GCC. 

Debe asegurarse de que todas las combinaciones cliente-servidor y explorador-servidor usen TLS 1,2 (o una versión posterior) para mantener la conexión con los servicios de Office 365. Puede que tenga que actualizar ciertas combinaciones cliente-servidor y explorador-servidor. Para obtener más información acerca de cómo esto afecta, vea [preparación del uso obligatorio de TLS 1,2 en Office 365](https://support.microsoft.com/en-us/help/4057306/preparing-for-tls-1-2-in-office-365).
  
## <a name="deprecating-support-for-3des"></a>Desuso de la compatibilidad con 3DES
<a name="TLS11and12deprecation"> </a>

Desde el 31 de octubre de 2018, Office 365 ya no admite el uso de conjuntos de cifrado 3DES para comunicarse con Office 365. Más concretamente, Office 365 ya no es compatible con el conjunto de cifrado TLS_RSA_WITH_3DES_EDE_CBC_SHA. Desde el 28 de febrero de 2019, este conjunto de cifrado se deshabilita en Office 365. Los clientes y los servidores que se comunican con O365 después de esta fecha deben admitir al menos uno de los cifrados más seguros que se enumeran en este tema (vea conjuntos de cifrado de [TLS compatibles con Office 365](technical-reference-details-about-encryption.md#TLSCipherSuites)).
  
## <a name="deprecating-sha-1-certificate-support-in-office-365"></a>Desuso de la compatibilidad con certificados SHA-1 en Office 365
<a name="TLS11and12deprecation"> </a>

A partir del 2016 de junio de Office 365 ya no acepta un certificado SHA-1 para las conexiones salientes o entrantes. Si actualmente usa un certificado con SHA-1 en la cadena de certificados, tendrá que actualizar la cadena para usar SHA-2 (algoritmo de hash seguro 2) o un algoritmo hash más seguro.
  
## <a name="tls-cipher-suites-supported-by-office-365"></a>Conjuntos de cifrado de TLS compatibles con Office 365
<a name="TLSCipherSuites"> </a>

Un conjunto de cifrado es una colección de algoritmos de cifrado que TLS emplea para establecer conexiones seguras. Los conjuntos de cifrado compatibles con Office 365 se enumeran en la siguiente tabla, en orden de rigor con el conjunto de cifrado más seguro que aparece en primer lugar. Cuando Office 365 recibe una solicitud de conexión, primero intenta conectarse con el conjunto de cifrado de nivel superior y, si no lo consigue, prueba con el segundo conjunto de cifrado de la lista, y así sucesivamente. Cuando Office 365 envía una solicitud de conexión a otro servidor o a un cliente, el servidor o el cliente receptor elige el conjunto de cifrado o si se va a usar TLS.

> [!IMPORTANT]
> Tenga en cuenta que las versiones de TLS están en desuso y que *no deben usarse* versiones obsoletas cuando hay versiones más recientes disponibles. En otras palabras, en cualquier lugar en el que se muestre que se admiten TLS 1,0, 1,1 y 1,2, elija la versión *más reciente* (TLS 1,2).
  
|**Protocolos**|**Nombre del conjunto de cifrado**|**Algoritmo/fuerza de intercambio de claves**|**Compatibilidad con confidencialidad directa perfecta**|**Algoritmo de autenticación/seguridad**|**Cifrado o seguridad**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|TLS 1.2  <br/> |TLS_ECDHE_RSA_WITH_AES_256_GCM_SHA384  <br/> |ECDH/192  <br/> |Sí  <br/> |RSA/112  <br/> |AES/256  <br/> |
|TLS 1.2  <br/> |TLS_ECDHE_RSA_WITH_AES_128_GCM_SHA256  <br/> |ECDH/128  <br/> |Sí  <br/> |RSA/112  <br/> |AES/128  <br/> |
|TLS 1.2  <br/> |TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA384_P384  <br/> |ECDH/192  <br/> |Sí  <br/> |RSA/112  <br/> |AES/256  <br/> |
|TLS 1.2  <br/> |TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA256_P256  <br/> |ECDH/128  <br/> |Sí  <br/> |RSA/112  <br/> |AES/128  <br/> |
|TLS 1.0, 1.1, 1.2  <br/> |TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA_P384  <br/> |ECDH/192  <br/> |Sí  <br/> |RSA/112  <br/> |AES/256  <br/> |
|TLS 1.0, 1.1, 1.2  <br/> |TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA_P256  <br/> |ECDH/128  <br/> |Sí  <br/> |RSA/112  <br/> |AES/128  <br/> |
|TLS 1.2  <br/> |TLS_RSA_WITH_AES_256_CBC_SHA256  <br/> |RSA/112  <br/> |No  <br/> |RSA/112  <br/> |AES/256  <br/> |
|TLS 1.2  <br/> |TLS_RSA_WITH_AES_128_CBC_SHA256  <br/> |RSA/112  <br/> |No  <br/> |RSA/112  <br/> |AES/128  <br/> |
|TLS 1.0, 1.1, 1.2  <br/> |TLS_RSA_WITH_AES_256_CBC_SHA  <br/> |RSA/112  <br/> |No  <br/> |RSA/112  <br/> |AES/256  <br/> |
|TLS 1.0, 1.1, 1.2  <br/> |TLS_RSA_WITH_AES_128_CBC_SHA  <br/> |RSA/112  <br/> |No  <br/> |RSA/112  <br/> |AES/128  <br/> |
   
## <a name="related-topics"></a>Temas relacionados
[Conjuntos de cifrado TLS en Windows 10 v1607](https://docs.microsoft.com/windows/desktop/SecAuthN/tls-cipher-suites-in-windows-10-v1607)

[Cifrado en Office 365](encryption.md)
  
[Configurar el cifrado en Office 365 Enterprise](set-up-encryption.md)
  
[Implementación de Schannel TLS 1,0 en la actualización de estado de seguridad de Windows: 24 de noviembre de 2015](https://support.microsoft.com/kb/3117336)
  
[Mejoras de cifrado de TLS/SSL (centro de TI de Windows)](https://technet.microsoft.com/en-us/library/cc766285%28v=ws.10%29.aspx)
  

