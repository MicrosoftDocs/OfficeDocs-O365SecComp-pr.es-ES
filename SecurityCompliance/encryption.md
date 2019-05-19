---
title: Cifrado en Office 365
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 1/3/2018
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 0a322724-08ca-43db-b69a-afbfa20484cd
ms.collection:
- M365-security-compliance
- Strat_O365_IP
description: Con Office 365, el contenido está cifrado en reposo y en tránsito, usando el cifrado, los protocolos y las tecnologías más seguros disponibles. Obtenga información general sobre el cifrado en Office 365.
ms.openlocfilehash: 3cd72b3caf26c18ca6836490bc3cd48c2977863b
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/17/2019
ms.locfileid: "34154722"
---
# <a name="encryption-in-office-365"></a>Cifrado en Office 365

El cifrado es una parte importante de las estrategias de protección de información y protección de archivos. Lea este artículo para obtener información general sobre el cifrado usado para todas las versiones de Office 365 y obtener ayuda con las tareas de cifrado, desde la configuración del cifrado de la organización a la protección de documentos de Office con contraseña.
  
- Si está buscando información sobre certificados y tecnologías como TLS, consulte información [de referencia técnica sobre el cifrado en Office 365](technical-reference-details-about-encryption.md).

- Si busca información sobre cómo configurar o configurar el cifrado para su organización, vea [configurar el cifrado en Office 365 Enterprise](set-up-encryption.md).

## <a name="what-is-encryption-and-how-does-it-work-in-office-365"></a>¿Qué es el cifrado y cómo funciona en Office 365?

En un nivel alto, el cifrado es el proceso de codificar los datos (denominados como texto sin formato) en texto cifrado que no pueden usar los usuarios o los equipos a menos que se descifre el texto cifrado. El descifrado requiere una clave de cifrado que solo tengan los usuarios autorizados. El cifrado ayuda a garantizar que solo los destinatarios autorizados puedan descifrar el contenido, como los mensajes de correo electrónico y los archivos.
  
El cifrado por sí mismo no evita que el contenido, como archivos, mensajes de correo electrónico, entradas de calendario, etc., llegue a las manos equivocadas. El cifrado forma parte de una estrategia de protección de la información más amplia para su organización. Mediante el cifrado, puede ayudar a garantizar que solo los usuarios que deberían poder usar datos cifrados puedan.
  
Puede tener varios niveles de cifrado en su ubicación al mismo tiempo. Por ejemplo, puede cifrar los mensajes de correo electrónico y los canales de comunicación a través de los cuales fluye el correo electrónico. Con Office 365, los datos se cifran en reposo y en tránsito, mediante el uso de varios protocolos de cifrado seguros y tecnologías que incluyen seguridad de la capa de transporte/capa de sockets seguros (TLS/SSL), seguridad de protocolo de Internet (IPSec) y cifrado avanzado Estándar (AES).
  
## <a name="encryption-for-data-at-rest-and-data-in-transit"></a>Cifrado de datos en reposo y datos en tránsito

 **Algunos ejemplos de datos en reposo** incluyen los archivos que se han cargado en una biblioteca de SharePoint, los datos de Project online, los documentos que se han cargado en una reunión de Skype empresarial, los mensajes de correo electrónico y los datos adjuntos que se almacenan en las carpetas de su oficina 365 buzón de correo y archivos cargados en OneDrive para la empresa. 
  
 **Algunos ejemplos de datos en tránsito** son los mensajes de correo que están en proceso de entrega o las conversaciones que se están llevando a cabo en una reunión en línea. En Office 365, los datos están en tránsito siempre que el dispositivo de un usuario se comunica con un servidor de Office 365 o cuando un servidor de Office 365 se comunica con otro servidor. 
  
Con Office 365, puede tener varias capas y tipos de cifrado que trabajan juntos para proteger sus datos. En la tabla siguiente se incluyen algunos ejemplos, con vínculos a información adicional.
  
|**Tipos de contenido**|**Tecnologías de cifrado**|**Recursos para obtener más información**|
|:-----|:-----|:-----|
|Archivos en un dispositivo. Esto puede incluir los mensajes de correo electrónico guardados en una carpeta, los documentos de Office guardados en un equipo, una tableta o un teléfono, o los datos guardados en la nube de Microsoft.  <br/> |BitLocker en centros de recursos de Microsoft. BitLocker también se puede usar en equipos cliente, como equipos y tabletas Windows  <br/> Administrador de claves distribuidas (DKM) en centros de recursos de Microsoft  <br/> Clave del cliente de Office 365  <br/> |[Centro de TI de Windows: BitLocker](https://docs.microsoft.com/windows/device-security/bitlocker/bitlocker-overview) <br/> [Centro de confianza de Microsoft: cifrado](https://www.microsoft.com/en-us/TrustCenter/Security/Encryption) <br/> [Serie de controles de seguridad en la nube: cifrado de datos en reposo](https://blogs.microsoft.com/microsoftsecure/2015/09/10/cloud-security-controls-series-encrypting-data-at-rest) <br/> [Cómo Exchange Online protege su información confidencial de correo electrónico](exchange-online-secures-email-secrets.md) <br/> [Controlar los datos en Office 365 con la clave de cliente](controlling-your-data-using-customer-key.md) <br/> |
|Archivos en tránsito entre usuarios. Esto puede incluir documentos de Office o elementos de lista de SharePoint compartidos entre usuarios.  <br/> |TLS para los archivos en tránsito  <br/> |[Cifrado de datos en OneDrive para la Empresa y SharePoint Online](data-encryption-in-odb-and-spo.md) <br/> [Skype empresarial online: seguridad y archivado](https://technet.microsoft.com/library/skype-for-business-online-security-and-archiving.aspx) <br/> |
|Correo electrónico en tránsito entre los destinatarios. Esto incluye el correo electrónico hospedado por Exchange Online.  <br/> |Office 365 cifrado de mensajes con Azure Rights Management, S/MIME y TLS para el correo electrónico en tránsito  <br/> |[Cifrado de mensajes de Office 365 (OME)](ome.md) <br/> [Cifrado de correo electrónico en Office 365](email-encryption.md) <br/> [Cómo Exchange Online usa TLS para proteger las conexiones de correo electrónico en Office 365](exchange-online-uses-tls-to-secure-email-connections.md) <br/> |

## <a name="what-if-i-need-more-control-over-encryption-to-meet-security-and-compliance-requirements"></a>¿Qué sucede si necesito más control sobre el cifrado para cumplir con los requisitos de seguridad y cumplimiento?

Además de las soluciones administradas por Microsoft para el cifrado de volúmenes, el cifrado de archivos y el cifrado de buzones en Office 365, se pueden usar las opciones administradas por el cliente para cumplir con los requisitos de seguridad y cumplimiento más estrictos. Estas soluciones usan Azure Rights Management (Azure RMS) junto con Office 365.
  
Vea los siguientes recursos para obtener más información:
  
- [¿Qué es Azure Rights Management?](https://docs.microsoft.com/information-protection/understand-explore/what-is-azure-rms)

- [Activación de Rights Management en el Centro de administración de Office 365](https://support.office.com/article/5b6d3ac7-b1ac-428e-b03e-50e882f85a6e)

- [Set up Information Rights Management (IRM) in SharePoint admin center](set-up-irm-in-sp-admin-center.md).

## <a name="how-do-i"></a>Cómo...

|**Para realizar esta tarea**|**Ver estos recursos**|
|:-----|:-----|
|Configurar el cifrado para mi organización  <br/> |[Configurar el cifrado en Office 365 Enterprise](set-up-encryption.md) <br/> |
|Ver detalles sobre certificados, tecnologías y conjuntos de cifrado TLS en Office 365  <br/> |[Detalles técnicos sobre el cifrado en Office 365](technical-reference-details-about-encryption.md) <br/> |
|Trabajar con mensajes cifrados en un dispositivo móvil  <br/> |[Ver mensajes cifrados en su dispositivo Android](https://support.office.com/article/83d60f17-2305-407a-a762-7d518401fdeb) <br/> [Ver mensajes cifrados en su iPhone o iPad](https://support.office.com/article/4d631321-0d26-4bcc-a483-d294dd0b1caf) <br/> |
|Cifrado de un documento con protección con contraseña  <br/><br/>  Actualmente, la protección con contraseña no es compatible con Office online. Use versiones de escritorio de Word, Excel y PowerPoint para la protección con contraseña.           |[Agregar o quitar la protección en el documento, libro o presentación](https://support.office.com/article/05084cc3-300d-4c1a-8416-38d3e37d6826) (Elija una sección **protección para agregar** y, a continuación, ver cifrar **con contraseña** )  <br/> |
|Quitar el cifrado de un documento  <br/> |[Agregar o quitar la protección en el documento, libro o presentación](https://support.office.com/article/05084cc3-300d-4c1a-8416-38d3e37d6826) (Elija una sección **quitar protección** y, a continuación, vea **quitar cifrado de contraseña** )  <br/> |

## <a name="related-topics"></a>Temas relacionados

[Planeación de las capacidades de protección de la información y la seguridad de Office 365](https://support.office.com/article/3d4ac4a1-3920-4ff9-918f-011f3ce60408)
  
[Seguridad y cumplimiento en Office 365 para empresas: ayuda para administradores](https://support.office.com/article/7fe448f7-49bd-4d3e-919d-0a6d1cf675bb)