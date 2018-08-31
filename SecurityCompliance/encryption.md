---
title: Cifrado en Office 365
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 1/3/2018
ms.audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MET150
- MOE150
ms.assetid: 0a322724-08ca-43db-b69a-afbfa20484cd
description: Con Office 365, el contenido se cifra en reposo y en tránsito, con el cifrado más seguro, protocolos y las tecnologías disponibles. Obtenga una visión general de cifrado en Office 365.
ms.openlocfilehash: e5c21cf456f9ccca2393b8985dd47e34745902cf
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22536205"
---
# <a name="encryption-in-office-365"></a>Cifrado en Office 365

El cifrado es una parte importante de las estrategias de protección de protección y de información de archivo. Lea este artículo para obtener una visión general de cifrado que se utiliza para todas las versiones de Office 365 y obtener ayuda con tareas de cifrado, de la configuración de cifrado para la organización a los documentos de Office de protección con contraseña.
  
- Si está buscando información sobre certificados y tecnologías como TLS, vea [los detalles de referencia técnica acerca del cifrado en Office 365](technical-reference-details-about-encryption.md).
    
- Si busca información acerca de cómo configurar o configurar el cifrado para su organización, vea [Configurar el cifrado en Office 365 Enterprise](set-up-encryption.md).
    
## <a name="what-is-encryption-and-how-does-it-work-in-office-365"></a>¿Qué es el cifrado, y cómo funciona en Office 365?

En un nivel alto, el cifrado es el proceso de codificación de los datos (denominados como texto sin formato) en texto cifrado que no se puede usar por personas o los equipos a menos que y hasta que el texto cifrado se descifra. Descifrado requiere una clave de cifrado que sólo los usuarios autorizados tienen. Cifrado ayuda a garantizar que sólo los destinatarios autorizados pueden descifrar el contenido, como mensajes de correo electrónico y archivos.
  
Cifrado por sí solo no impide que contenido, como archivos, mensajes de correo electrónico, las entradas de calendario y así sucesivamente, llegue a manos incorrectos. El cifrado es parte de una estrategia de protección de la información más grande para su organización. Mediante el uso de cifrado, puede garantizar que sólo aquellos que debe ser capaz de usar los datos cifrados son capaces de.
  
Puede tener varios niveles de cifrado en su lugar al mismo tiempo. Por ejemplo, puede cifrar mensajes de correo electrónico y también en los canales de comunicación a través del cual fluye el correo electrónico. Con Office 365, se cifran los datos en reposo y en tránsito, con varios protocolos de cifrado seguras y tecnologías que incluyen Transport Layer Security/Secure Sockets Layer (TLS/SSL), seguridad de protocolo de Internet (IPSec) y cifrado avanzados Estándar de (cifrado avanzado AES).
  
## <a name="encryption-for-data-at-rest-and-data-in-transit"></a>Cifrado de datos en reposo y los datos en tránsito

 **Algunos ejemplos de datos en reposo** son archivos que se han cargado en una biblioteca de SharePoint, datos de Project Online, los documentos que se han cargado en un Skype para empresas reunión, mensajes de correo electrónico y datos adjuntos que se almacenan en las carpetas en Office 365 buzón de correo y los archivos cargados en OneDrive para la empresa. 
  
 **Algunos ejemplos de los datos en tránsito** son los mensajes de correo que están en proceso de entrega o las conversaciones que se están produciendo en una reunión en línea. En Office 365, los datos están en tránsito siempre que el dispositivo del usuario se comunica con un servidor de Office 365, o cuando un servidor de Office 365 se comunica con otro servidor. 
  
Con Office 365, puede tener varias capas y tipos de cifrado que trabajan en conjunto para proteger los datos. En la siguiente tabla se incluye algunos ejemplos, con vínculos a información adicional.
  
|**Tipos de contenido**|**Tecnologías de cifrado**|**Recursos para obtener más información**|
|:-----|:-----|:-----|
|Archivos en un dispositivo. Esto puede incluir mensajes de correo electrónico guardados en una carpeta, documentos de Office guardados en un equipo, un Tablet PC o un teléfono o datos que se guardan en la nube de Microsoft.  <br/> |BitLocker en centros de datos de Microsoft. También se puede usar BitLocker en equipos cliente, como los equipos de Windows y tabletas  <br/> Administrador de clave distribuida (DKM) en centros de datos de Microsoft  <br/> Clave de cliente de Office 365  <br/> |[Windows IT Center: BitLocker](https://docs.microsoft.com/windows/device-security/bitlocker/bitlocker-overview) <br/> [Centro de confianza de Microsoft: cifrado](https://www.microsoft.com/en-us/TrustCenter/Security/Encryption) <br/> [Serie de controles de seguridad en la nube: cifrar datos en reposo](https://blogs.microsoft.com/microsoftsecure/2015/09/10/cloud-security-controls-series-encrypting-data-at-rest) <br/> [Cómo Exchange Online protege su información confidencial de correo electrónico](exchange-online-secures-email-secrets.md) <br/> [Controlar los datos en Office 365 con la clave de cliente](controlling-your-data-using-customer-key.md) <br/> |
|Archivos en tránsito entre los usuarios. Esto puede incluir documentos de Office o elementos de lista de SharePoint que comparte entre los usuarios.  <br/> |TLS para los archivos en tránsito  <br/> |[Cifrado de datos en OneDrive para la Empresa y SharePoint Online](data-encryption-in-odb-and-spo.md) <br/> [Skype para la empresa en línea: seguridad y archivado](https://technet.microsoft.com/library/skype-for-business-online-security-and-archiving.aspx) <br/> |
|En tránsito entre los destinatarios de correo electrónico. Esto incluye correo electrónico hospedado por Exchange Online.  <br/> |Cifrado de mensajes de Office 365 con Azure Rights Management, S/MIME y TLS para el correo electrónico en tránsito  <br/> |[Cifrado de mensajes de Office 365 (OME)](ome.md) <br/> [Cifrado de correo electrónico en Office 365](email-encryption.md) <br/> [Empleo de TLS por parte de Exchange Online para proteger las conexiones de correo electrónico en Office 365](exchange-online-uses-tls-to-secure-email-connections.md) <br/> |
   
## <a name="what-if-i-need-more-control-over-encryption-to-meet-security-and-compliance-requirements"></a>¿Qué ocurre si necesito más controlar a través de cifrado para cumplir los requisitos de seguridad y cumplimiento de normas?

Además de las soluciones administradas de Microsoft de cifrado de volumen, el cifrado de archivos y el cifrado de buzón de correo en Office 365, administrado por el cliente opciones pueden usarse para cumplir los requisitos de seguridad y cumplimiento de normas más estrictos. Estas soluciones usan Azure Rights Management (RMS Azure) junto con Office 365.
  
Vea los siguientes recursos para obtener más información:
  
- [¿Qué es Azure Rights Management?](https://docs.microsoft.com/information-protection/understand-explore/what-is-azure-rms)
    
- [Activación de Rights Management en el Centro de administración de Office 365](https://support.office.com/article/5b6d3ac7-b1ac-428e-b03e-50e882f85a6e)
    
- [Establecer seguridad de Information Rights Management (IRM) en el centro de administración de SharePoint](set-up-irm-in-sp-admin-center.md)
    
## <a name="how-do-i"></a>Cómo...

|**Para realizar esta tarea**|**Vea estos recursos**|
|:-----|:-----|
|Configurar el cifrado para mi organización  <br/> |[Configurar el cifrado en Office 365 Enterprise](set-up-encryption.md) <br/> |
|Ver detalles acerca de certificados, las tecnologías y los conjuntos de cifrado TLS en Office 365  <br/> |[Detalles técnicos acerca del cifrado en Office 365](technical-reference-details-about-encryption.md) <br/> |
|Trabajar con los mensajes cifrados en un dispositivo móvil  <br/> |[Ver los mensajes cifrados en su dispositivo Android](https://support.office.com/article/83d60f17-2305-407a-a762-7d518401fdeb) <br/> [Ver los mensajes cifrados en su iPhone o iPad](https://support.office.com/article/4d631321-0d26-4bcc-a483-d294dd0b1caf) <br/> |
|Cifrar un documento mediante la protección con contraseña  <br/></br>  Actualmente, la protección con contraseña no se admite en Office Online. Utilice las versiones de escritorio de Word, Excel y PowerPoint para protección con contraseña.           |[Agregar o quitar la protección en el documento, libro o la presentación](https://support.office.com/article/05084cc3-300d-4c1a-8416-38d3e37d6826) (Elija una sección de **protección de agregar** y, a continuación, vea **cifrar con contraseña** )  <br/> |
|Quitar el cifrado de un documento  <br/> |[Agregar o quitar la protección en el documento, libro o la presentación](https://support.office.com/article/05084cc3-300d-4c1a-8416-38d3e37d6826) (Elija una sección de **quitar la protección** y, a continuación, vea **quitar el cifrado de contraseña** )  <br/> |
   
## <a name="related-topics"></a>Temas relacionados

[Planeación de capacidades de protección de información de seguridad y de Office 365](https://support.office.com/article/3d4ac4a1-3920-4ff9-918f-011f3ce60408)
  
[Seguridad y cumplimiento de normas en Office 365 para profesionales - ayuda de administración](https://support.office.com/article/7fe448f7-49bd-4d3e-919d-0a6d1cf675bb)
  

