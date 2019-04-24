---
title: Cifrado en Microsoft Cloud
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
ms.collection:
- Strat_O365_Enterprise
- M365-security-compliance
- Strat_O365_Enterprise
description: Información general sobre el cifrado en la nube de Microsoft.
ms.openlocfilehash: 36bb50cda5f39461401b14ca3e7ada77a6e2cc0d
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32262782"
---
# <a name="encryption-in-the-microsoft-cloud"></a>Cifrado en Microsoft Cloud

Los datos de cliente de los servicios en la nube de la empresa de Microsoft están protegidos por una variedad de tecnologías y procesos, incluidos varios formularios de cifrado. (Office 365 los datos de clientes de este documento incluyen el contenido del buzón de correo de Exchange Online (cuerpo del correo electrónico, entradas del calendario y el contenido de los datos adjuntos de correo electrónico, y, si procede, el contenido de Skype empresarial), el contenido del sitio de SharePoint Online y los archivos almacenados en sitios y archivos cargados en OneDrive para la empresa o Skype empresarial). Microsoft usa varios métodos, protocolos y cifrados de cifrado en sus productos y servicios para ayudar a proporcionar una ruta de acceso segura para que los datos de los clientes viajen a través de nuestros servicios en la nube y ayudar a proteger la confidencialidad de los datos de clientes que se almacenan en nuestros servicios en la nube. Microsoft usa algunos de los protocolos de cifrado más seguros y seguros disponibles para proporcionar barreras contra el acceso no autorizado a los datos de los clientes. La administración de claves adecuada también es un elemento esencial de los procedimientos recomendados de cifrado y Microsoft trabaja para garantizar que todas las claves de cifrado administradas por Microsoft están protegidas correctamente.

Independientemente de la configuración del cliente, los datos del cliente almacenados en los servicios en la nube de empresa de Microsoft se protegen con uno o más formularios de cifrado. (La validación de la Directiva de cifrado y su cumplimiento es comprobada de forma independiente por varios auditores de terceros y los informes de esas auditorías están disponibles en el [portal de confianza del servicio](https://aka.ms/stp)).

Microsoft proporciona tecnologías del lado del servicio que cifran los datos de los clientes en reposo y en tránsito. Por ejemplo, para los datos de cliente en reposo, Microsoft Azure usa [BitLocker](https://docs.microsoft.com/windows/device-security/bitlocker/bitlocker-overview) y [dm-crypt](https://en.wikipedia.org/wiki/Dm-crypt), y Microsoft Office 365 usa BitLocker, el cifrado de [servicio de almacenamiento de Azure](https://azure.microsoft.com/documentation/articles/storage-service-encryption/), el administrador de [claves distribuidas](https://support.office.com/article/989ba10c-f73f-4efb-ad1b-af3322e5f376) (DKM) y el servicio de Office 365 cifrado. Para los datos de clientes en tránsito, Azure, Office 365, soporte comercial de Microsoft, Microsoft Dynamics 365, Microsoft Power BI y Visual Studio Team Services usan protocolos de transporte seguro estándar del sector, como la seguridad del Protocolo de Internet (IPsec) y Seguridad de la capa de transporte (TLS), entre los centros de recursos de Microsoft y entre los dispositivos de usuario y los centros de seguridad de Microsoft.

Además del nivel de línea base de la seguridad criptográfica que proporciona Microsoft, nuestros servicios en la nube también incluyen opciones de criptografía adicionales que puede administrar. Por ejemplo, puede habilitar el cifrado para el tráfico entre sus máquinas virtuales (VM) de Azure y sus usuarios. Con las [redes virtuales de Azure](https://azure.microsoft.com/services/virtual-network/), puede usar el protocolo IPSec estándar del sector para cifrar el tráfico entre la puerta de enlace VPN corporativa y Azure, así como entre las máquinas virtuales que se encuentran en la red virtual. Además, las [nuevas capacidades de cifrado de mensajes de Office 365](set-up-new-message-encryption-capabilities.md) permiten enviar correo cifrado a cualquier persona.

De acuerdo con la norma de seguridad operativa de la infraestructura de clave pública, que es un componente de la [Directiva de seguridad de Microsoft](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=5868ecc8-50b7-4f91-b43f-640e2b99e86e&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ%20and%20White%20Papers), Microsoft aprovecha las capacidades de cifrado incluidas en el sistema operativo Windows para los certificados y mecanismos de autenticación, que incluye el uso de módulos criptográficos que cumplen los [estándares federales de procesamiento de información](http://csrc.nist.gov/publications/PubsFIPS.html) (FIPS) 140-2 del gobierno de Estados Unidos. (Los números de certificado de NIST pertinentes para Microsoft se pueden encontrar enhttp://csrc.nist.gov/groups/STM/cmvp/documents/140-1/1401vend.htm.)

> Note Para tener acceso a la Directiva de seguridad de Microsoft como un recurso, debe iniciar sesión con su cuenta profesional o educativa. Si aún no tiene una suscripción, [puede registrarse para obtener una prueba gratuita](https://servicetrust.microsoft.com/Home/TrialSubscriptions).

FIPS 140-2 es un estándar diseñado específicamente para validar módulos de producto que implementan la criptografía en lugar de los productos que los usan. Los módulos criptográficos que se implementan dentro de un servicio pueden certificarse para cumplir los requisitos de seguridad de hash, la administración de claves y similares. Todas las capacidades de cifrado de tiempo que se emplean para proteger la confidencialidad, la integridad o la disponibilidad de los datos en los servicios en la nube de Microsoft, los módulos y los cifrados que se usan cumplen el estándar FIPS 140-2.

Microsoft certifica los módulos criptográficos subyacentes que se usan en nuestros servicios en la nube con cada nueva versión del sistema operativo Windows:

- Azure y Azure U.S. Government
- Dynamics 365 y Dynamics 365 U.S. Government
- Office 365, Office 365 el gobierno de Estados Unidos y Office 365 para la defensa del gobierno de Estados Unidos

El cifrado de los datos de cliente de Office 365 en reposo lo proporcionan varias tecnologías de servicio, como BitLocker, DKM, el cifrado de servicio de almacenamiento de Azure y el cifrado de servicios en Exchange Online, Skype empresarial, OneDrive para la empresa y SharePoint Online. Office 365 Service Encryption incluye una opción para usar las claves de cifrado administradas por el cliente que se almacenan en Azure Key Vault. Esta opción de clave administrada por el cliente, llamada [clave de cliente de Office 365](https://support.office.com/article/f2cd475a-e592-46cf-80a3-1bfb0fa17697), está disponible para Exchange Online, SharePoint Online, Skype empresarial y OneDrive para la empresa.

Para los datos de clientes en tránsito, todos los servidores de Office 365 negocian sesiones seguras usando TLS de forma predeterminada con los equipos cliente para proteger los datos de los clientes.  Esto se aplica a los protocolos en cualquier dispositivo usado por los clientes, como Skype empresarial, Outlook y Outlook en la web, clientes móviles y exploradores Web.

(Todos los servidores dirigidos a los clientes negocian a TLS 1,2 de forma predeterminada, pero también admiten la negociación a un estándar inferior, si es necesario).

## <a name="related-links"></a>Vínculos relacionados

- [Cifrado en Azure](office-365-azure-encryption.md)
- [BitLocker y Administrador de claves distribuidas (DKM) para el cifrado](office-365-bitlocker-and-distributed-key-manager-for-encryption.md)
- [Cifrado de servicio de Office 365](office-365-service-encryption.md)
- [Office 365 cifrado para Skype empresarial, OneDrive para la empresa, SharePoint Online y Exchange Online](office-365-encryption-for-skype-onedrive-sharepoint-and-exchange.md)
- [Cifrado de datos en tránsito](office-365-encryption-for-data-in-transit.md)
- [Características de cifrado administradas por el cliente](office-365-customer-managed-encryption-features.md)
- [Riesgos y protección de cifrado](office-365-encryption-risks-and-protections.md)
- [Cifrado en Microsoft Dynamics 365](office-365-encryption-in-microsoft-dynamics-365.md)