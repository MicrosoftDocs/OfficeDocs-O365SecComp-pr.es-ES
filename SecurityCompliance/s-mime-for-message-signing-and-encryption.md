---
title: S/MIME para la firma y el cifrado de mensajes
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/9/2016
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 887c710b-0ec6-4ff0-8065-5f05f74afef3
description: S/MIME le permite cifrar mensajes de correo electrónico y firmen digitalmente. Cuando se utiliza S/MIME con un mensaje de correo electrónico, ayuda a las personas que reciban ese mensaje para estar seguro de que lo aparece en su Bandeja de entrada es el mensaje exacto que inició con el remitente.
ms.openlocfilehash: 26c50fb6e4d1b07b7dba26948ae46e7f36eeaec5
ms.sourcegitcommit: e9dca2d6a7838f98bb7eca127fdda2372cda402c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/21/2018
ms.locfileid: "23002776"
---
# <a name="smime-for-message-signing-and-encryption"></a>S/MIME para la firma y el cifrado de mensajes

S/MIME (Extensiones seguras multipropósito de correo Internet) es un método ampliamente aceptado, o con mayor precisión un protocolo, para el envío de digitalmente mensajes firmados y cifrados. S/MIME le permite cifrar mensajes de correo electrónico y firmen digitalmente. Cuando se utiliza S/MIME con un mensaje de correo electrónico, ayuda a las personas que reciban ese mensaje para estar seguro de que lo aparece en su Bandeja de entrada es el mensaje exacto que inició con el remitente. También ayudará a las personas que reciben los mensajes que se asegure de que el mensaje procede de un remitente específico y no de alguien que pretende ser el remitente. Para ello, S/MIME proporciona para servicios de seguridad criptográfica como la autenticación, integridad de mensajes y rechazo de origen (uso de firmas digitales). También ayuda a mejorar la privacidad y seguridad de datos (mediante cifrado) para la mensajería electrónica. Para un fondo más completado acerca de la historia y la arquitectura de S/MIME en el contexto de correo electrónico, vea [Descripción de S/MIME](https://go.microsoft.com/fwlink/?LinkID=393948). 
  
Como administrador, puede habilitar la seguridad basada en S/MIME para la organización si tiene buzones de correo de Exchange 2013 SP1 o Exchange Online, una parte de Office 365. Use las instrucciones en los temas vinculados aquí junto con el Shell de administración de Exchange para configurar S/MIME. Para usar S/MIME en las versiones compatibles de Outlook o ActiveSync con Exchange 2013 SP1 o Exchange Online, los usuarios de su organización deben tener los certificados emitidos por razones de firma y cifrado y datos publicados en su Active Directory local Servicio de dominio (AD DS). Su AD DS debe estar ubicada en los equipos en una ubicación física que controlar y no en una instalación remota o servicio basados en la nube en algún lugar de internet. Para obtener más información acerca de AD DS, vea [Los servicios de dominio de Active Directory](https://go.microsoft.com/fwlink/?LinkID=394064).
  
## <a name="supported-scenarios-and-technical-considerations"></a>Consideraciones técnicas y escenarios admitidos
<a name="sectionSection0"> </a>

Si su organización usa Exchange 2013 SP1 o Exchange Online, puede configurar S/MIME para trabajar con cualquiera de los siguientes extremos: 
  
- Outlook 2010
    
- Outlook 2013
    
- Outlook Web App
    
- Exchange ActiveSync (EAS)
    
Los pasos que debe seguir para configurar S/MIME con cada uno de estos extremos es ligeramente diferente según cuál elija. Por lo general, deberá realizar lo siguiente:
  
- Instalar una entidad de certificación basado en Windows y configurar una infraestructura de clave pública para emitir certificados S/MIME. También se admiten los certificados emitidos por proveedores de certificado de terceros. Para obtener información detallada, vea [Introducción a servicios de certificado de Active Directory](https://technet.microsoft.com/library/hh831740.aspx).
    
- Publicar el certificado de usuario en una cuenta local de AD DS en los atributos UserSMIMECertificate y UserCertificate.
    
- Para organizaciones de Exchange Online, sincronizar los certificados de usuario de AD DS para Azure Active Directory mediante el uso de una versión adecuada de sincronización de directorios. Estos certificados, a continuación, obtener sincronizará desde Azure Active Directory al directorio de Exchange Online y se va a usar al cifrar un mensaje a un destinatario.
    
- Crear una colección virtual de certificados para validar S/MIME. OWA usa esta información para validar la firma de un correo electrónico y garantizar que se ha firmado con un certificado de confianza.
    
- Configurar el extremo de Outlook o EAS para usar S/MIME. 
    
## <a name="setup-smime-with-outlook-web-app"></a>Configurar S/MIME con Outlook Web App
<a name="sectionSection1"> </a>

Configuración de S/MIME para Exchange 2013 SP1 o Exchange Online con Outlook Web App implica los siguientes pasos clave:
  
1. [Configuración de S/MIME para Outlook Web App](configure-s-mime-settings-for-outlook-web-app.md)
    
2. [Configurar una colección de certificados virtuales para validar S/MIME](set-up-virtual-certificate-collection-to-validate-s-mime.md)
    
3. [Sincronizar certificados de usuario a Office 365 para S/MIME](sync-user-certificates-to-office-365-for-s-mime.md) Este paso sólo se aplica a Exchange Online. 
    
## <a name="related-message-encryption-technologies"></a>Tecnologías de cifrado de mensajes relacionadas
<a name="sectionSection2"> </a>

Como la seguridad de los mensajes se vuelve más importante, los administradores deben entender los principios y conceptos de mensajería segura. Esta descripción es especialmente importante debido a la creciente variedad de tecnologías relacionadas con la protección, como S/MIME, que se han convertido en disponibles. Para saber más acerca de S/MIME y cómo funciona en el contexto de correo electrónico, vea [Descripción de S/MIME](https://go.microsoft.com/fwlink/?LinkID=393948). Una gran variedad de tecnologías de cifrado funcionan conjuntamente para ofrecer protección para los mensajes en rest y en tránsito. S/MIME pueden trabajar simultáneamente con las siguientes tecnologías, pero no es dependiente de ellos:
  
> **Seguridad de la capa de transporte (TLS)** cifra el túnel o la ruta entre los servidores de correo electrónico para ayudar a evitar exámenes y escuchas no autorizados. 
    
> **Capa de sockets seguros (SSL)** cifra la conexión entre los clientes de correo electrónico y los servidores de Office 365. 
    
> **BitLocker** cifra los datos en una unidad de disco duro en un centro de datos de forma que si alguien obtiene acceso no autorizado, no puede leerlo. 
    
### <a name="smime-compared-with-office-365-message-encryption"></a>Comparación de S/MIME con Cifrado de mensajes de Office 365

S/MIME requiere una infraestructura de certificados y la publicación que se utiliza a menudo en situaciones de negocio a negocio y negocio a consumidor. El usuario controla las claves de cifrado en S/MIME y puede elegir si desea usarlos para cada mensaje enviado. Programas de correo electrónico como Outlook busca en una ubicación de autoridad de certificado raíz de confianza para llevar a cabo la firma digital y comprobación de la firma. Office 365 cifrado de mensajes es un servicio basado en la directiva de cifrado que se puede configurar por un administrador y no es un usuario individual, para cifrar el correo enviado a todas las personas dentro o fuera de la organización. Es un servicio en línea que se basa en Azure Rights Management (RMS) y no se basa en una infraestructura de clave pública. Cifrado de mensajes de Office 365 también proporciona funciones adicionales, como la capacidad de personalizar el correo con la marca de la organización. Para obtener más información acerca del cifrado de mensajes de Office 365, vea [Office 365 Message Encryption](https://go.microsoft.com/fwlink/?LinkID=392525).
  
## <a name="more-information"></a>Más información
<a name="sectionSection3"> </a>

[Outlook Web App](http://technet.microsoft.com/library/3814b665-01e8-4881-9a44-163f14789ee4.aspx)
  
[Correo seguro (2000)](https://technet.microsoft.com/en-us/library/cc962043.aspx)
  

