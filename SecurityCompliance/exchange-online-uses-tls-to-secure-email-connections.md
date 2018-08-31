---
title: Empleo de TLS por parte de Exchange Online para proteger las conexiones de correo electrónico en Office 365
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 8/2/2018
ms.audience: ITPro
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MET150
- MOE150
ms.assetid: 4cde0cda-3430-4dc0-b489-f2c0736c929f
description: Obtenga información sobre cómo Office 365 y Exchange Online usan seguridad de capa de transporte (TLS) y desviar secreto (FS) para proteger las comunicaciones de correo electrónico. También Obtenga información sobre el certificado emitido por Microsoft para Exchange Online.
ms.openlocfilehash: 079a6f574838f5710dbbbcb53726799abfae1d3a
ms.sourcegitcommit: ddfa0ac1f8ef95a78dcc1468241ef29363d56b5b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/30/2018
ms.locfileid: "23520149"
---
# <a name="how-exchange-online-uses-tls-to-secure-email-connections-in-office-365"></a>Empleo de TLS por parte de Exchange Online para proteger las conexiones de correo electrónico en Office 365

Obtenga información sobre cómo Office 365 y Exchange Online usan seguridad de capa de transporte (TLS) y desviar secreto (FS) para proteger las comunicaciones de correo electrónico. También proporciona información sobre el certificado emitido por Microsoft para Exchange Online.
  
## <a name="tls-basics-for-office-365-and-exchange-online"></a>Conceptos básicos de TLS para Office 365 y Exchange Online

Seguridad de capa de transporte (TLS) y SSL que se incluían antes TLS, son los protocolos criptográficos que protección la comunicación a través de una red mediante el uso de certificados de seguridad para cifrar una conexión entre los equipos. TLS reemplaza la capa de Sockets seguros (SSL) y a menudo se conoce como SSL 3.1. Para Exchange Online, usamos TLS para cifrar las conexiones entre nuestros servidores de Exchange y las conexiones entre nuestros servidores de Exchange y otros servidores como los servidores de Exchange locales o los servidores de correo de los destinatarios. Una vez que la conexión está cifrada, todos los datos enviados a través de esa conexión se envía a través del canal cifrado. Sin embargo, si reenviar un mensaje que se envió a través de una conexión de cifrado TLS, ese mensaje necesariamente no se cifra. Esto es debido a que, en términos sencillos, TLS no cifrar el mensaje, únicamente la conexión.
  
Si quiere cifrar el mensaje, necesita usar una tecnología de cifrado que cifre el contenido del mensaje (por ejemplo, Cifrado de mensajes de Office). Vea [Email encryption in Office 365](email-encryption.md) y [Office 365 Message Encryption (OME)](ome.md) para más información sobre las opciones de cifrado de mensajes de Office 365. 
  
Se recomienda usar TLS en situaciones donde desea establecer un canal seguro de correspondencia entre Office 365 y de la organización local o de otra organización, como un socio. Exchange Online siempre intenta usar TLS para proteger su correo electrónico en primer lugar, pero siempre no puede hacer esto si la otra parte no ofrece seguridad TLS. Siga leyendo para averiguar cómo puede proteger todo el correo a los servidores locales o socios importantes mediante el uso de *conectores*. 
  
## <a name="how-exchange-online-uses-tls-between-exchange-online-customers"></a>Empleo de TLS por parte de Exchange Online entre clientes de Exchange Online

Los servidores de Exchange Online siempre cifran las conexiones con otros servidores de Exchange Online de nuestros centros de datos con TLS 1.2. Cuando envía un correo a un destinatario que está dentro de la organización de Office 365, ese correo electrónico se envía automáticamente a través de una conexión cifrada con TLS. Además, todo el correo electrónico que envía a otros clientes de Office 365 se envía a través de conexiones cifradas con TLS y protegidas con confidencialidad directa.
  
## <a name="how-office-365-uses-tls-between-office-365-and-external-trusted-partners"></a>Cómo Office 365 usa TLS entre Office 365 y socios externos de confianza

De forma predeterminada, Exchange Online siempre utiliza TLS oportunista. Esto significa que Exchange Online siempre intenta cifrar las conexiones con la versión más segura de TLS en primer lugar, a continuación, funciona hacia abajo la lista de cifrado TLS hasta que encuentra uno en el que pueden aceptar la ambas partes. A menos que haya configurado en Exchange Online para asegurarse de que los mensajes a los destinatarios que sólo se envían a través de conexiones seguras, a continuación, de forma predeterminada el mensaje se enviará sin cifrar si la organización de destino no admite el cifrado TLS. TLS oportunista es suficiente para la mayoría de las empresas. Sin embargo, para la empresa que tienen requisitos de cumplimiento de normas como médico, banca u organizaciones gubernamentales, puede configurar Exchange Online para requerir o forzar TLS. Para obtener instrucciones, vea [Configurar el flujo de correo mediante conectores en Office 365](https://technet.microsoft.com/library/ms.exch.eac.connectorselection%28v=exchg.150%29.aspx).
  
Si decide configurar TLS entre la organización y una organización de socio de confianza, Exchange Online puede usar TLS forzada para crear confianza canales de comunicación. TLS forzada requiere su organización socio para autenticar a Exchange Online con un certificado de seguridad para poder enviar correo a usted. Su socio será necesario administrar sus propios certificados con el fin de hacer esto. En Exchange Online, usamos conectores para proteger los mensajes que envían del acceso no autorizado antes de que llegan al proveedor de correo electrónico del destinatario. Para obtener información sobre el uso de conectores para configurar el flujo de correo, vea [Configurar el flujo de correo mediante conectores en Office 365](https://technet.microsoft.com/library/ms.exch.eac.connectorselection%28v=exchg.150%29.aspx).
  
## <a name="tls-and-hybrid-exchange-server-deployments"></a>TLS e implementaciones híbridas de Exchange Server

Si va a administrar una implementación híbrida de Exchange, sus necesidades de servidor de Exchange local para autenticar a Office 365 con un certificado de seguridad con el fin de enviar correo a los destinatarios cuyos buzones de correo se encuentran sólo en Office 365. Como resultado, debe administrar sus propios certificados de seguridad para los servidores de Exchange local. También de forma segura debe almacenar y mantener estos certificados de servidor. Para obtener más información sobre la administración de certificados en las implementaciones híbridas, vea [requisitos de certificado para implementaciones híbridas](https://technet.microsoft.com/library/hh563848%28v=exchg.150%29.aspx).
  
## <a name="how-to-set-up-forced-tls-for-exchange-online-in-office-365"></a>Configurar TLS forzado para Exchange Online en Office 365

Para los clientes de Exchange Online, en orden para TLS forzada para que funcione para proteger todos los de su correo electrónico enviado y recibido, es necesario configurar más de un conector que se requiere TLS. Necesitará un conector para el correo electrónico enviado a los buzones de usuario y el otro conector para correo electrónico enviado desde los buzones de usuario. Crear estos conectores en el centro de administración de Exchange en Office 365. Para obtener instrucciones, vea [Configurar el flujo de correo mediante conectores en Office 365](https://technet.microsoft.com/library/ms.exch.eac.connectorselection%28v=exchg.150%29.aspx).
  
## <a name="tls-certificate-information-for-exchange-online"></a>Información de certificado TLS para Exchange Online

La información del certificado utilizada por Exchange Online se describe en la siguiente tabla. Si su socio empresarial consiste en configurar TLS forzada en su servidor de correo electrónico, debe proporcionar esta información a ellos. Tenga en cuenta que por motivos de seguridad, nuestros certificados cambiar de vez en cuando. Nos hemos implantado una actualización a nuestro certificado dentro de nuestros centros de datos. El nuevo certificado es válido a partir del 3 de septiembre de 2018.
  
 **Información del certificado actual válido a partir del 3 de septiembre de 2018**
  
|**Atributo**|**Valor**|
|:-----|:-----|
|Emisor raíz de la autoridad de certificado  <br/> |Raíz de GlobalSign – R1 <br/> |
|Nombre del certificado  <br/> |Mail.Protection.Outlook.com  <br/> |
|Organización  <br/> |Microsoft Corporation  <br/> |
|Unidad de organización  <br/> |  <br/> |
|Nivel de la clave de certificado  <br/> |2048  <br/> |
   
 **Información del certificado en desuso válido hasta 3 de septiembre de 2018**
  
Para ayudar a garantizar una transición sin problemas, seguiremos proporcionar la información del certificado anterior para su referencia durante algún tiempo, sin embargo, debe usar la información del certificado actual en el futuro.
  
****

|**Atributo**|**Valor**|
|:-----|:-----|
|Emisor raíz de la autoridad de certificado  <br/> |Baltimore CyberTrust Root  <br/> |
|Nombre del certificado  <br/> |Mail.Protection.Outlook.com  <br/> |
|Organización  <br/> |Microsoft Corporation  <br/> |
|Unidad de organización  <br/> |Microsoft Corporation  <br/> |
|Nivel de la clave de certificado  <br/> |2048  <br/> |
   
## <a name="prepare-for-the-new-exchange-online-certificate"></a>Preparación para el nuevo certificado de Exchange Online

El nuevo certificado está emitido por una entidad de diferentes certificado (CA) desde el anterior certificado utilizado por Exchange Online. Como resultado, es posible que necesite realizar algunas acciones para poder usar el nuevo certificado.

El nuevo certificado requiere que se conectan a los extremos de la nueva entidad de certificación como parte de validar el certificado. Se puede producir si no lo hace en el flujo de correo que se vea afectado negativamente. Si proteger los servidores de correo con los servidores de seguridad que sólo permiten que los servidores de correo conectarse con determinados destinos que debe comprobar si el servidor es capaz de validar el certificado nuevo. Para confirmar que el servidor puede usar el nuevo certificado, siga estos pasos:

1. Conectarse al servidor de Exchange local mediante Windows PowerShell y, a continuación, ejecute el siguiente comando:  
  `certutil -URL http://crl.globalsign.com/gsorganizationvalsha2g3.crl`
2. En la ventana que aparece, elija **recuperar**.
3. Una vez completada la utilidad su comprobación devuelve un estado. Si el estado muestra **Aceptar**, a continuación, el servidor de correo puede validar correctamente el nuevo certificado. En caso contrario, es necesario determinar qué es lo que provoca que las conexiones se lleve a cabo. Lo más probable, debe actualizar la configuración de un servidor de seguridad. La lista completa de los extremos que debe tener acceso incluyen:
    - OCSP.GlobalSign.com
     - CRL.GlobalSign.com
     - Secure.GlobalSign.com   

Normalmente, recibirá actualizaciones a los certificados raíz automáticamente a través de Windows Update. Sin embargo que algunas implementaciones tengan seguridad adicionales en su lugar que impide que se produzca automáticamente estas actualizaciones. En estas implementaciones bloqueado donde Windows Update no se puede actualizar automáticamente los certificados raíz, debe asegurarse de que se instala el certificado de entidad de certificación de raíz correcta, siga estos pasos:
1.  Conectarse al servidor de Exchange local mediante Windows PowerShell y, a continuación, ejecute el siguiente comando:  
  `certmgr.msc`
2. Bajo **Confianza raíz o certificados de entidades emisoras**, confirme que aparece el nuevo certificado.

## <a name="get-more-information-about-tls-and-office-365"></a>Obtenga más información sobre TLS y Office 365

Para obtener una lista de conjuntos de cifrado compatibles, vea [los detalles de referencia técnica acerca del cifrado en Office 365](technical-reference-details-about-encryption.md).
  
[Configurar conectores para flujo de correo seguro con una organización asociada](https://technet.microsoft.com/library/dn751021%28v=exchg.150%29.aspx)
  
[Conectores con seguridad mejorada de correo electrónico](https://technet.microsoft.com/library/261d92e4-7371-4555-b781-2062b5bb5278.aspx)
  
[Cifrado en Office 365](encryption.md)
  

