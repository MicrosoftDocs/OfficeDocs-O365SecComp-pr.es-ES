---
title: S/MIME para la firma y el cifrado de mensajes en Exchange Online
ms.author: chrisda
author: chrisda
manager: serdars
ms.date: ''
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 887c710b-0ec6-4ff0-8065-5f05f74afef3
description: Los administradores pueden aprender a usar S/MIME en Exchange Online.
ms.openlocfilehash: 7c7225efce247928e19946e695c19931f198ae32
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32261388"
---
# <a name="smime-for-message-signing-and-encryption-in-exchange-online"></a>S/MIME para la firma y el cifrado de mensajes en Exchange Online

S/MIME (extensiones seguras multipropósito al correo de Internet) es un método ampliamente aceptado (o más exactamente, un protocolo) para enviar mensajes cifrados y firmados digitalmente. S/MIME permite cifrar mensajes de correo electrónico y firmarlos digitalmente. Cuando se usa S/MIME con un mensaje de correo electrónico, ayuda a las personas que reciben el mensaje a tener la certeza de que lo que ven en la bandeja de entrada es el mensaje exacto que comenzó con el remitente. También ayudará a las personas que reciben mensajes a fin de asegurarse de que el mensaje proviene del remitente específico y no de alguien que pretende ser el remitente. Para ello, S/MIME proporciona servicios de seguridad criptográfica como autenticación, integridad de mensajes y no rechazo de origen (usando firmas digitales). También ayuda a mejorar la privacidad y la seguridad de los datos (mediante cifrado) para la mensajería electrónica. Para obtener más información sobre la historia y la arquitectura de S/MIME en el contexto del correo electrónico, consulte [Descripción de S/MIME](https://go.microsoft.com/fwlink/?LinkID=393948).

Como administrador de Exchange Online, puede habilitar la seguridad basada en S/MIME para los buzones de la organización. Use las instrucciones de los temas que se vinculan aquí junto con Exchange Online PowerShell para configurar S/MIME. Para usar S/MIME en clientes de correo electrónico admitidos, los usuarios de la organización deben tener certificados emitidos con fines de firma y cifrado, así como datos publicados en el servicio de dominio de Active Directory (AD DS) local. AD DS debe estar ubicado en equipos en una ubicación física que usted controle y no en una instalación remota o un servicio basado en la nube en cualquier lugar de Internet. Para obtener más información acerca de AD DS, consulte [Servicios de dominio de Active Directory](https://go.microsoft.com/fwlink/?LinkID=394064).

## <a name="supported-scenarios-and-technical-considerations"></a>Consideraciones técnicas y escenarios admitidos

Puede configurar S/MIME para trabajar con cualquiera de los siguientes extremos:

- Outlook 2010 o posterior

- Outlook en la web (anteriormente conocida como Outlook Web App)

- Exchange ActiveSync (EAS)

Los pasos que debe seguir para configurar S/MIME con cada uno de estos extremos son ligeramente diferentes. Por lo general, deberá realizar los pasos siguientes:

- Instale una entidad emisora de certificados basada en Windows y configure una infraestructura de clave pública para emitir certificados S/MIME. También se admiten los certificados emitidos por proveedores de certificados de terceros. Para obtener más información, consulte [Información general de Servicios de certificados de Active Directory](https://technet.microsoft.com/library/hh831740.aspx).

- Publique el certificado de usuario en una cuenta local de AD DS en los atributos **UserSMIMECertificate** y **UserCertificate** .

- Para las organizaciones de Exchange Online, sincronice los certificados de usuario de AD DS a Azure Active Directory mediante una versión adecuada de dirSync. Estos certificados se sincronizarán desde Azure Active Directory a directorio de Exchange Online y se usarán al cifrar un mensaje a un destinatario.

- Crear una colección virtual de certificados para validar S/MIME. Outlook en la web usa esta información para validar la firma de un correo electrónico y garantizar que se ha firmado con un certificado de confianza.

- Configurar el extremo de Outlook o EAS para usar S/MIME.

## <a name="setup-smime-with-outlook-on-the-web"></a>Configuración de S/MIME con Outlook en la web

La configuración de S/MIME para Exchange Online con Outlook en la web implica los siguientes pasos clave:

1. [Configurar S/MIME para Outlook en la Web](configure-s-mime-settings-for-outlook-web-app.md)

2. [Configurar una colección de certificados virtuales para validar S/MIME](set-up-virtual-certificate-collection-to-validate-s-mime.md)

3. [Sincronizar certificados de usuario con Office 365 para S/MIME](sync-user-certificates-to-office-365-for-s-mime.md)

## <a name="related-message-encryption-technologies"></a>Tecnologías de cifrado de mensajes relacionadas

A medida que la seguridad de los mensajes se vuelve más importante, los administradores deben comprender los principios y conceptos de la mensajería segura. Esta comprensión es especialmente importante debido a la creciente variedad de tecnologías relacionadas con la protección (incluido S/MIME) que están disponibles. Para obtener más información acerca de S/MIME y cómo funciona en el contexto del correo electrónico, consulte [understandIng s/MIME](https://go.microsoft.com/fwlink/?LinkID=393948). Una variedad de tecnologías de cifrado funcionan en conjunto para proporcionar protección a los mensajes en reposo y en tránsito. S/MIME puede funcionar simultáneamente con las siguientes tecnologías, pero no depende de ellas:

- **Seguridad de la capa de transporte (TLS)** cifra el túnel o la ruta entre los servidores de correo electrónico para ayudar a evitar la supervisión y el espionaje.

- La **capa de sockets seguros (SSL)** cifra la conexión entre los clientes de correo electrónico y los servidores de Office 365.

- **BitLocker** cifra los datos de un disco duro en un centro de datos para que si alguien obtiene acceso no autorizado, no pueda leerlo.

### <a name="smime-compared-with-office-365-message-encryption"></a>Comparación de S/MIME con el cifrado de mensajes de 365 de Office

S/MIME requiere una infraestructura de certificados y publicación que suele usarse en situaciones de negocio a negocio y de negocio a consumidor. El usuario controla las claves criptográficas en S/MIME y puede elegir si desea usarlas para cada mensaje que envíe. Los programas de correo electrónico como Outlook buscan una ubicación de entidades de certificación raíz de confianza para llevar a cabo la firma digital y la comprobación de la firma. El cifrado de mensajes de Office 365 es un servicio de cifrado basado en directivas que puede configurar un administrador, y no un usuario individual, para cifrar el correo enviado a cualquier persona dentro o fuera de la organización. Es un servicio en línea que se basa en Azure Rights Management (RMS) y no depende de una infraestructura de clave pública. El cifrado de mensajes de Office 365 también proporciona funciones adicionales, como la capacidad de personalizar el correo con la marca de la organización. Para obtener más información acerca del cifrado de mensajes de Office 365, consulte [office 365 Message Encryption](https://go.microsoft.com/fwlink/?LinkID=392525).

## <a name="more-information"></a>Más información

[Outlook en la Web](http://technet.microsoft.com/library/3814b665-01e8-4881-9a44-163f14789ee4.aspx)

[Correo seguro (2000)](https://technet.microsoft.com/en-us/library/cc962043.aspx)
