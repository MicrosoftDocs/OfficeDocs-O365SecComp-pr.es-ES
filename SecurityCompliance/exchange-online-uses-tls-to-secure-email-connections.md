---
title: Empleo de TLS por parte de Exchange Online para proteger las conexiones de correo electrónico en Office 365
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 8/2/2018
ms.audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 4cde0cda-3430-4dc0-b489-f2c0736c929f
ms.collection:
- M365-security-compliance
- Strat_O365_IP
description: Obtenga información sobre cómo Exchange Online y Office 365 usan la seguridad de la capa de transporte (TLS) y la confidencialidad directa (FS) para proteger las comunicaciones de correo electrónico. Obtenga también información sobre el certificado emitido por Microsoft para Exchange Online.
ms.openlocfilehash: e80f477c807f3a7ad5f751e0987b191024c816d9
ms.sourcegitcommit: 03054baf50c1dd5cd9ca6a9bd5d056f3db98f964
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/01/2019
ms.locfileid: "30354632"
---
# <a name="how-exchange-online-uses-tls-to-secure-email-connections-in-office-365"></a>Empleo de TLS por parte de Exchange Online para proteger las conexiones de correo electrónico en Office 365

Obtenga información sobre cómo Exchange Online y Office 365 usan la seguridad de la capa de transporte (TLS) y la confidencialidad directa (FS) para proteger las comunicaciones de correo electrónico. También proporciona información sobre el certificado emitido por Microsoft para Exchange Online.
  
## <a name="tls-basics-for-office-365-and-exchange-online"></a>Conceptos básicos de TLS para Office 365 y Exchange Online

La seguridad de la capa de transporte (TLS) y SSL que se incluían antes de TLS son protocolos criptográficos que protegen la comunicación a través de una red mediante certificados de seguridad para cifrar una conexión entre equipos. TLS reemplaza a la capa de sockets seguros (SSL) y, a menudo, se conoce como SSL 3,1. Para Exchange Online, usamos TLS para cifrar las conexiones entre nuestros servidores de Exchange y las conexiones entre nuestros servidores de Exchange y otros servidores, como los servidores de Exchange locales o los servidores de correo de los destinatarios. Una vez que se cifra la conexión, todos los datos enviados a través de esa conexión se envían a través del canal cifrado. Sin embargo, si reenvía un mensaje que se envió a través de una conexión cifrada con TLS, dicho mensaje no se cifra necesariamente. Esto se debe a que, en términos sencillos, TLS no cifra el mensaje, solo la conexión.
  
Si quiere cifrar el mensaje, necesita usar una tecnología de cifrado que cifre el contenido del mensaje (por ejemplo, Cifrado de mensajes de Office). Vea [Email encryption in Office 365](email-encryption.md) y [Office 365 Message Encryption (OME)](ome.md) para más información sobre las opciones de cifrado de mensajes de Office 365. 
  
Se recomienda usar TLS en situaciones en las que desee configurar un canal seguro de correspondencia entre Office 365 y su organización local u otra organización, como un asociado. Exchange Online siempre intenta usar TLS primero para proteger el correo electrónico, pero no siempre puede hacerlo si la otra parte no ofrece seguridad TLS. Siga leyendo para averiguar cómo puede proteger todo el correo en los servidores locales o los asociados importantes mediante *conectores*. 
  
## <a name="how-exchange-online-uses-tls-between-exchange-online-customers"></a>Empleo de TLS por parte de Exchange Online entre clientes de Exchange Online

Los servidores de Exchange Online siempre cifran las conexiones con otros servidores de Exchange Online de nuestros centros de datos con TLS 1.2. Cuando envía un correo a un destinatario que está dentro de la organización de Office 365, ese correo electrónico se envía automáticamente a través de una conexión cifrada con TLS. Además, todo el correo electrónico que envía a otros clientes de Office 365 se envía a través de conexiones cifradas con TLS y protegidas con confidencialidad directa.
  
## <a name="how-office-365-uses-tls-between-office-365-and-external-trusted-partners"></a>Cómo usa Office 365 TLS entre Office 365 y los asociados de confianza externos

De forma predeterminada, Exchange Online siempre usa TLS oportunista. Esto significa que Exchange Online siempre intenta cifrar las conexiones con la versión más segura de TLS en primer lugar y, a continuación, baja la lista de cifrados TLS hasta que encuentra uno en el que puedan acordar ambas partes. A menos que haya configurado Exchange Online para asegurarse de que los mensajes a ese destinatario solo se envíen a través de conexiones seguras, de manera predeterminada, el mensaje se enviará sin cifrar si la organización del destinatario no admite el cifrado TLS. La TLS oportunista es suficiente para la mayoría de las empresas. Sin embargo, para los negocios que tienen requisitos de cumplimiento, como organizaciones médicas, bancarias o gubernamentales, puede configurar Exchange Online para que exija o fuerce TLS. Para obtener instrucciones, vea [Configure mail Flow Using Connectors in Office 365](https://technet.microsoft.com/library/ms.exch.eac.connectorselection%28v=exchg.150%29.aspx).
  
Si decide configurar TLS entre su organización y una organización de asociado de confianza, Exchange Online puede usar TLS forzada para crear canales de confianza. La TLS forzada requiere que la organización asociada se autentique en Exchange Online con un certificado de seguridad para poder enviar correo al usuario. Su compañero tendrá que administrar sus propios certificados para poder hacerlo. En Exchange Online, usamos conectores para proteger los mensajes enviados desde accesos no autorizados antes de que lleguen al proveedor de correo electrónico del destinatario. Para obtener información acerca del uso de conectores para configurar el flujo de correo, consulte [Configure mail Flow Using Connectors in Office 365](https://technet.microsoft.com/library/ms.exch.eac.connectorselection%28v=exchg.150%29.aspx).
  
## <a name="tls-and-hybrid-exchange-server-deployments"></a>TLS e implementaciones híbridas de Exchange Server

Si está administrando una implementación híbrida de Exchange, su servidor Exchange local debe autenticarse en Office 365 con un certificado de seguridad para poder enviar correo a los destinatarios cuyos buzones solo se encuentran en Office 365. Como resultado, debe administrar sus propios certificados de seguridad para los servidores de Exchange locales. También debe almacenar y mantener de forma segura estos certificados de servidor. Para obtener más información acerca de la administración de certificados en implementaciones híbridas, consulte [Certificate Requirements for Hybrid Deployments](https://technet.microsoft.com/library/hh563848%28v=exchg.150%29.aspx).
  
## <a name="how-to-set-up-forced-tls-for-exchange-online-in-office-365"></a>Configurar TLS forzado para Exchange Online en Office 365

Para los clientes de Exchange Online, para que TLS forzado funcione para proteger todos los correos electrónicos enviados y recibidos, debe configurar más de un conector que requiera TLS. Necesitará un conector para el correo electrónico enviado a sus buzones de usuario y otro para el correo enviado desde sus buzones de usuario. Cree estos conectores en el centro de administración de Exchange en Office 365. Para obtener instrucciones, vea [Configure mail Flow Using Connectors in Office 365](https://technet.microsoft.com/library/ms.exch.eac.connectorselection%28v=exchg.150%29.aspx).
  
## <a name="tls-certificate-information-for-exchange-online"></a>Información de certificado TLS para Exchange Online

La información del certificado que usa Exchange Online se describe en la tabla siguiente. Si su socio comercial está configurando TLS forzado en su servidor de correo electrónico, tendrá que proporcionar esta información a ellos. Tenga en cuenta que, por motivos de seguridad, nuestros certificados realizan cambios de vez en cuando. Hemos implementado una actualización en nuestro certificado dentro de nuestros centros de información. El nuevo certificado es válido a partir del 3 de septiembre de 2018.
  
 **Información del certificado actual válida desde el 3 de septiembre de 2018**
  
|**Atributo**|**Valor**|
|:-----|:-----|
|Emisor raíz de la autoridad de certificado  <br/> |CA raíz GlobalSign – R1 <br/> |
|Nombre del certificado  <br/> |mail.Protection.Outlook.com  <br/> |
|Organización  <br/> |Microsoft Corporation  <br/> |
|Unidad de organización  <br/> |  <br/> |
|Nivel de la clave de certificado  <br/> |2048  <br/> |
   
 **La información del certificado en desuso es válida hasta el 3 de septiembre de 2018**
  
Para ayudar a garantizar una transición sin problemas, seguiremos proporcionando la información antigua del certificado para la referencia por algún tiempo, pero debe usar la información del certificado actual a partir de ahora.
  
****

|**Atributo**|**Valor**|
|:-----|:-----|
|Emisor raíz de la autoridad de certificado  <br/> |Baltimore CyberTrust Root  <br/> |
|Nombre del certificado  <br/> |mail.Protection.Outlook.com  <br/> |
|Organización  <br/> |Microsoft Corporation  <br/> |
|Unidad de organización  <br/> |Microsoft Corporation  <br/> |
|Nivel de la clave de certificado  <br/> |2048  <br/> |
   
## <a name="prepare-for-the-new-exchange-online-certificate"></a>Preparar el nuevo certificado de Exchange Online

El nuevo certificado está emitido por una entidad de certificación (CA) distinta del certificado anterior usado por Exchange Online. Como resultado, es posible que deba realizar algunas acciones para usar el nuevo certificado.

El nuevo certificado requiere la conexión a los puntos de conexión de la nueva entidad de certificación como parte de la validación del certificado. Si no lo hace, el flujo de correo puede verse afectado desfavorablemente. Si protege los servidores de correo con firewalls que solo permiten que los servidores de correo se conecten con determinados destinos, debe comprobar si el servidor puede validar el nuevo certificado. Para confirmar que el servidor puede usar el nuevo certificado, siga estos pasos:

1. Conéctese a su servidor local de Exchange mediante Windows PowerShell y, a continuación, ejecute el siguiente comando:  
  `certutil -URL http://crl.globalsign.com/gsorganizationvalsha2g3.crl`
2. En la ventana que aparece, elija **recuperar**.
3. Cuando la utilidad completa la comprobación, devuelve un estado. Si el estado muestra **correcto**, su servidor de correo puede validar correctamente el nuevo certificado. Si no es así, debe determinar la causa del error de las conexiones. Lo más probable es que necesite actualizar la configuración de un firewall. La lista completa de los puntos de conexión que deben tener acceso son:
    - OCSP.GlobalSign.com
     - CRL.GlobalSign.com
     - Secure.GlobalSign.com   

Normalmente, las actualizaciones se reciben automáticamente en los certificados raíz a través de Windows Update. Sin embargo, algunas implementaciones tienen seguridad adicional en vigor que impide que se realicen estas actualizaciones automáticamente. En estas implementaciones bloqueadas en las que Windows Update no puede actualizar automáticamente los certificados raíz, debe asegurarse de que el certificado de CA raíz correcto está instalado mediante la realización de estos pasos:
1.  Conéctese a su servidor local de Exchange mediante Windows PowerShell y, a continuación, ejecute el siguiente comando:  
  `certmgr.msc`
2. En **certificados/entidades de certificación raíz de confianza**, confirme que el nuevo certificado aparece en la lista.

## <a name="get-more-information-about-tls-and-office-365"></a>Obtenga más información sobre TLS y Office 365

Para obtener una lista de los conjuntos de programas de cifrado compatibles, vea [información de referencia técnica sobre el cifrado en Office 365](technical-reference-details-about-encryption.md).
  
[Configurar conectores para flujo de correo seguro con una organización asociada](https://technet.microsoft.com/library/dn751021%28v=exchg.150%29.aspx)
  
[Conectores con seguridad mejorada de correo electrónico](https://technet.microsoft.com/library/261d92e4-7371-4555-b781-2062b5bb5278.aspx)
  
[Cifrado en Office 365](encryption.md)
  

