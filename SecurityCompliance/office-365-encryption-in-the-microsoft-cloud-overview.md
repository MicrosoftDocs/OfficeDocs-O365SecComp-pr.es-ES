---
title: Cifrado en Microsoft Cloud
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: 8/21/2018
audience: ITPro
ms.topic: article
ms.service: Office 365 Administration
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: Una descripción general de cifrado en el Microsoft Cloud.
ms.openlocfilehash: b8dee7ca7a791878763b885ada40a1d87f074e8e
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22536614"
---
# <a name="encryption-in-the-microsoft-cloud"></a>Cifrado en Microsoft Cloud

Datos de los clientes dentro de los servicios de nube de empresa de Microsoft está protegidos por una variedad de tecnologías y los procesos, incluidas las diversas formas de cifrado. (Los datos de cliente de office 365 en este documento incluyen contenido de buzones de correo de Exchange Online (cuerpo del correo electrónico, las entradas de calendario y el contenido de los datos adjuntos de correo electrónico y si procede, Skype para contenido empresarial), el contenido del sitio de SharePoint Online y los archivos almacenan en sitios y los archivos cargados en OneDrive para empresa o de Skype para la empresa.) Microsoft utiliza varios métodos de cifrado, protocolos y cifrados a través de sus productos y servicios para ayudar a proporcionar una ruta de acceso seguro para viajar a través de nuestros servicios de nube y para ayudar a proteger la confidencialidad de los datos de cliente que se almacenan dentro de los datos de cliente nuestros servicios de nube. Microsoft utiliza algunos de los protocolos de cifrado más seguro, más seguro disponibles para proporcionar las barreras contra el acceso no autorizado a los datos de cliente. Administración de claves correcta también es un elemento esencial de procedimientos recomendados de cifrado y de Microsoft works para asegurarse de que todas las claves de cifrado administrado por Microsoft están protegidas correctamente.

Independientemente de la configuración del cliente, los datos de cliente almacenados en los servicios de nube de empresa de Microsoft está protegidos mediante uno o varios formularios de cifrado. (Validación de nuestra política de cifrado y su aplicación se comprueba de forma independiente por varios auditores de terceros, y los informes de las auditorías están disponibles en el [Portal de servicio de confianza](https://aka.ms/stp)).

Microsoft proporciona tecnologías del servicio que cifrar datos en reposo y en tránsito de los clientes. Por ejemplo, para datos en reposo de los clientes, Microsoft Azure usa [BitLocker](https://docs.microsoft.com/windows/device-security/bitlocker/bitlocker-overview) y [Cifrado de DM](https://en.wikipedia.org/wiki/Dm-crypt)y Microsoft Office 365 usa el servicio de BitLocker, [Cifrado de servicio de almacenamiento de Azure](https://azure.microsoft.com/documentation/articles/storage-service-encryption/), [El Administrador de claves distribuida](https://support.office.com/article/989ba10c-f73f-4efb-ad1b-af3322e5f376) (DKM) y Office 365 cifrado. Para los datos del cliente en tránsito, Azure, Office 365, soporte técnico de Microsoft comercial, Microsoft Dynamics 365, Microsoft Power BI y Visual Studio Team Services utilizan protocolos de transporte seguro estándar del sector, como protocolo de seguridad de Internet (IPsec) y Capa de transporte seguridad (TLS), entre centros de datos de Microsoft y entre los dispositivos de usuario y los centros de datos de Microsoft.

Además del nivel de línea de base de seguridad de cifrado proporcionado por Microsoft, nuestros servicios de nube también incluyen las opciones de criptografía adicionales que se pueden administrar. Por ejemplo, puede habilitar el cifrado para el tráfico entre sus máquinas virtuales de Azure (máquinas virtuales) y sus usuarios. Con las [Redes virtuales de Azure](https://azure.microsoft.com/services/virtual-network/), puede usar el protocolo IPsec estándar del sector para cifrar el tráfico entre la puerta de enlace VPN corporativo y Azure, así como entre las máquinas virtuales que se encuentra en la red Virtual. Además, además, [nuevas capacidades de Office 365 Message Encryption](set-up-new-message-encryption-capabilities.md) permiten enviar correo cifrado a cualquier persona.

Conformidad con el pública clave infraestructura operativa estándar de seguridad, que es un componente de la [Directiva de seguridad de Microsoft](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=5868ecc8-50b7-4f91-b43f-640e2b99e86e&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ%20and%20White%20Papers), Microsoft aprovecha las capacidades de cifrado incluidas en el sistema operativo de Windows para los certificados y mecanismos de autenticación, que incluye el uso de los módulos criptográficos que cumplen [Estándares Federal de procesamiento de información](http://csrc.nist.gov/publications/PubsFIPS.html) (FIPS del gobierno de Estados Unidos) 140-2 estándar. (Los números de certificado NIST relevantes para Microsoft pueden encontrarse enhttp://csrc.nist.gov/groups/STM/cmvp/documents/140-1/1401vend.htm.)

> [NOTA] Para obtener acceso a la directiva de seguridad de Microsoft como un recurso, debe iniciar sesión con su cuenta de trabajo o escuela. Si no dispone de una suscripción aún, [puede registrarse para una versión de prueba gratuita](https://servicetrust.microsoft.com/Home/TrialSubscriptions).

FIPS 140-2 es un estándar diseñado específicamente para validar los módulos del producto que implementan criptografía en lugar de los productos que usan. Módulos criptográficos que se implementan dentro de un servicio pueden estar certificados como los requisitos para la fuerza de hash, administración de claves y similares de la reunión. Cualquier momento capacidades criptográficas se emplean para proteger la confidencialidad, integridad o disponibilidad de los datos en los servicios de nube de Microsoft, los módulos y utiliza los cifrados cumplan el FIPS 140-2 estándar.

Microsoft certifica los módulos criptográficos subyacentes usados en nuestros servicios de nube con cada nueva versión del sistema operativo Windows:
- Azure y Azure gobierno de Estados Unidos
- Dynamics 365 y gobierno de Estados Unidos Dynamics 365
- Office 365, el gobierno de Estados Unidos de Office 365 y defensa del gobierno de Estados Unidos de Office 365

Cifrado de datos de cliente de Office 365 en reposo es proporcionado por varias tecnologías del servicio, incluidos BitLocker, DKM, cifrado de servicio de almacenamiento de Azure y cifrado de servicio en Exchange Online, Skype para la empresa, OneDrive para la empresa y SharePoint En línea. Cifrado de Office 365 servicio incluye una opción para usar claves de cifrado administrado por el cliente que se almacenan en Azure clave cámara. Este cliente administrado clave opción, denominada [Clave de cliente de Office 365](https://support.office.com/article/f2cd475a-e592-46cf-80a3-1bfb0fa17697), está disponible para Exchange Online, SharePoint Online, Skype para la empresa y OneDrive para la empresa.

Para los datos del cliente en tránsito, todos los servidores de Office 365 negocian sesiones seguras mediante TLS de forma predeterminada con los equipos cliente para proteger los datos de cliente.  Esto se aplica a los protocolos en cualquier dispositivo utilizado por los clientes, como Skype para la empresa, Outlook y Outlook en el web, los clientes móviles y los exploradores web.

(Todos los servidores orientados al cliente negocian para TLS 1.2 de forma predeterminada, pero también se admite la negociación hacia abajo hasta un estándar inferior, si es necesario).

## <a name="related-links"></a>Vínculos relacionados

- [Cifrado en Azure](office-365-azure-encryption.md)
- [BitLocker y Administrador de claves distribuidas (DKM) para el cifrado](office-365-bitlocker-and-distributed-key-manager-for-encryption.md)
- [Cifrado de servicio de Office 365](office-365-service-encryption.md)
- [Cifrado de Office 365 para Skype para la empresa, OneDrive para la empresa, SharePoint Online y Exchange Online](office-365-encryption-for-skype-onedrive-sharepoint-and-exchange.md)
- [Cifrado de datos en tránsito](office-365-encryption-for-data-in-transit.md)
- [Características de cifrado administradas por el cliente](office-365-customer-managed-encryption-features.md)
- [Riesgos y protección de cifrado](office-365-encryption-risks-and-protections.md)
- [Cifrado en Microsoft Dynamics 365](office-365-encryption-in-microsoft-dynamics-365.md)