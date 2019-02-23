---
title: S/MIME para la firma y el cifrado de mensajes en Exchange Online
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
description: S/MIME le permite cifrar los mensajes de correo electrónico y firmarlos digitalmente. Cuando se usa S/MIME con un mensaje de correo electrónico, ayuda a las personas que reciben el mensaje a tener la certeza de que lo que ven en la bandeja de entrada es el mensaje exacto que comenzó con el remitente.
ms.openlocfilehash: 41a84d5332092748f9a8cc8fe4936c39e5fd2012
ms.sourcegitcommit: 06d6e63225f912d0f3c6bb836c61eb11c1dbe97a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/22/2019
ms.locfileid: "30206513"
---
# <a name="smime-for-message-signing-and-encryption"></a>S/MIME para la firma y el cifrado de mensajes

S/MIME (extensiones seguras multipropósito al correo de Internet) es un método ampliamente aceptado, o más bien, un protocolo más preciso, para enviar mensajes cifrados y firmados digitalmente. S/MIME le permite cifrar los mensajes de correo electrónico y firmarlos digitalmente. Cuando se usa S/MIME con un mensaje de correo electrónico, ayuda a las personas que reciben el mensaje a tener la certeza de que lo que ven en la bandeja de entrada es el mensaje exacto que comenzó con el remitente. También ayudará a las personas que reciben mensajes a fin de asegurarse de que el mensaje proviene del remitente específico y no de alguien que pretende ser el remitente. Para ello, S/MIME proporciona servicios de seguridad criptográfica, como autenticación, integridad de mensajes y sin rechazo de origen (con firmas digitales). También ayuda a mejorar la privacidad y la seguridad de los datos (mediante cifrado) para la mensajería electrónica. Para obtener un fondo más completo sobre el historial y la arquitectura de S/MIME en el contexto del correo electrónico, consulte [understandIng S/MIME](https://go.microsoft.com/fwlink/?LinkID=393948). 
  
Como administrador, puede habilitar la seguridad basada en S/MIME para su organización si tiene buzones de Exchange 2013 SP1 o Exchange Online, parte de Office 365. Use las instrucciones de los temas que se vinculan aquí junto con el shell de administración de Exchange para configurar S/MIME. Para usar S/MIME en versiones compatibles de Outlook o ActiveSync, con Exchange 2013 SP1 o Exchange Online, los usuarios de la organización deben tener certificados emitidos para la firma y el cifrado y datos publicados en su implementación local de Active Directory. Servicio de dominio (AD DS). AD DS debe estar ubicado en equipos en una ubicación física que usted controle y no en una instalación remota o un servicio basado en la nube en cualquier lugar de Internet. Para obtener más información acerca de AD DS, consulte [servicios de dominio de Active Directory](https://go.microsoft.com/fwlink/?LinkID=394064).
  
## <a name="supported-scenarios-and-technical-considerations"></a>Consideraciones técnicas y escenarios admitidos
<a name="sectionSection0"> </a>

Puede configurar S/MIME para trabajar con cualquiera de los siguientes extremos: 
  
- Outlook 2010 o posterior
    
- Outlook en la web (anteriormente conocida como Outlook Web App)
    
- Exchange ActiveSync (EAS)
    
Los pasos que debe seguir para configurar S/MIME con cada uno de estos extremos es ligeramente diferente según cuál elija. Por lo general, deberá realizar lo siguiente:
  
- Instale una entidad de certificación basada en Windows y configure una infraestructura de clave pública para emitir certificados S/MIME. También se admiten los certificados emitidos por proveedores de certificados de terceros. Para obtener más información, vea [Introducción a los servicios de certificados de Active](https://technet.microsoft.com/library/hh831740.aspx)Directory.
    
- Publicar el certificado de usuario en una cuenta local de AD DS en los atributos UserSMIMECertificate y UserCertificate.
    
- Para las organizaciones de Exchange Online, sincronice los certificados de usuario de AD DS a Azure Active Directory mediante una versión adecuada de dirSync. Estos certificados se sincronizarán desde Azure Active Directory a directorio de Exchange Online y se usarán al cifrar un mensaje a un destinatario.
    
- Configurar una colección de certificados virtuales para validar S/MIME. Esta información se usa en Outlook en la web (anteriormente conocido como Outlook en la web) cuando se valida la firma de un correo electrónico y se garantiza que se firmó mediante un certificado de confianza.
    
- Configurar el extremo de Outlook o EAS para usar S/MIME. 
    
## <a name="setup-smime-with-outlook-on-the-web"></a>Configuración de S/MIME con Outlook en la web
<a name="sectionSection1"> </a>

La configuración de S/MIME para Exchange Online con Outlook en la web implica los siguientes pasos clave:
  
1. [Configure S/MIME settings for Outlook on the web](configure-s-mime-settings-for-outlook-web-app.md)
    
2. [Configurar una colección de certificados virtuales para validar S/MIME](set-up-virtual-certificate-collection-to-validate-s-mime.md)
    
3. [Sincronizar certificados de usuario con Office 365 para S/MIME](sync-user-certificates-to-office-365-for-s-mime.md) Este paso solo se aplica a Exchange Online. 
    
## <a name="related-message-encryption-technologies"></a>Tecnologías de cifrado de mensajes relacionadas
<a name="sectionSection2"> </a>

A medida que la seguridad de los mensajes se vuelve más importante, los administradores deben comprender los principios y conceptos de la mensajería segura. Esta comprensión es especialmente importante debido a la creciente variedad de tecnologías relacionadas con la protección, como S/MIME, que se han disponible. Para obtener más información acerca de S/MIME y cómo funciona en el contexto del correo electrónico, consulte [understandIng s/MIME](https://go.microsoft.com/fwlink/?LinkID=393948). Una variedad de tecnologías de cifrado funcionan en conjunto para proporcionar protección a los mensajes en reposo y en tránsito. S/MIME puede funcionar simultáneamente con las siguientes tecnologías, pero no depende de ellas:
  
> **Seguridad de la capa de transporte (TLS)** cifra el túnel o la ruta entre los servidores de correo electrónico para ayudar a evitar exámenes y escuchas no autorizados. 
    
> **Capa de sockets seguros (SSL)** cifra la conexión entre los clientes de correo electrónico y los servidores de Office 365. 
    
> **BitLocker** cifra los datos de un disco duro en un centro de datos para que si alguien obtiene acceso no autorizado, no pueda leerlo. 
    
### <a name="smime-compared-with-office-365-message-encryption"></a>Comparación de S/MIME con Cifrado de mensajes de Office 365

S/MIME requiere una infraestructura de certificados y publicación que a menudo se usa en situaciones de negocio a negocio y de negocio a consumidor. El usuario controla las claves de cifrado en S/MIME y puede elegir si las usa para cada mensaje que envían. Los programas de correo electrónico como Outlook buscan una ubicación de entidad de certificación raíz de confianza para realizar la firma digital y la comprobación de la firma. El cifrado de mensajes de Office 365 es un servicio de cifrado basado en directivas que puede configurar un administrador, y no un usuario individual, para cifrar el correo enviado a cualquier persona dentro o fuera de la organización. Es un servicio en línea que se basa en Azure Rights Management (RMS) y no depende de una infraestructura de clave pública. El cifrado de mensajes de Office 365 también proporciona funciones adicionales, como la capacidad de personalizar el correo con la marca de la organización. Para obtener más información acerca del cifrado de mensajes de Office 365, consulte [office 365 Message Encryption](https://go.microsoft.com/fwlink/?LinkID=392525).
  
## <a name="more-information"></a>Más información
<a name="sectionSection3"> </a>

[Outlook en la Web](http://technet.microsoft.com/library/3814b665-01e8-4881-9a44-163f14789ee4.aspx)
  
[Correo seguro (2000)](https://technet.microsoft.com/en-us/library/cc962043.aspx)
  

