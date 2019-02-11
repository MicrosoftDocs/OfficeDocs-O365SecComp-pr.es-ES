---
title: Cifrado de mensajes de Office 365
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 6/6/2018
ms.audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: f87cb016-7876-4317-ae3c-9169b311ff8a
description: Con el cifrado de mensajes de Office 365, la organización puede enviar y recibir mensajes de correo electrónico cifrado entre las personas dentro y fuera de su organización. Cifrado de mensajes de correo electrónico ayuda a garantiza que sólo los destinatarios puede ver el contenido del mensaje.
ms.openlocfilehash: 57b1d34902bb1522a7974e97f8cd90e9f19b76f5
ms.sourcegitcommit: 7e2a0185cadea7f3a6afc5ddc445eac2e1ce22eb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/11/2019
ms.locfileid: "29696264"
---
# <a name="office-365-message-encryption"></a>Cifrado de mensajes de Office 365

Con el cifrado de mensajes de Office 365, la organización puede enviar y recibir mensajes de correo electrónico cifrado entre las personas dentro y fuera de su organización. Office 365 cifrado de mensajes funciona con Outlook.com, Yahoo!, Gmail y otros servicios de correo electrónico. Cifrado de mensajes de correo electrónico ayuda a garantiza que sólo los destinatarios puede ver el contenido del mensaje.
  
En este artículo es parte de una serie de artículos sobre Office 365 Message Encryption más grande. Use la siguiente tabla para encontrar rápidamente la información que necesita.
  
|||
|:-----|:-----|
|Lea este artículo...  <br/> |Si está...  <br/> |
|[Obtenga información sobre los mensajes protegidos en Office 365](https://support.office.com/article/2baf3ac7-12db-40a4-8af7-1852204b4b67.aspx) <br/> |Un usuario final que desea obtener más información acerca de cómo se cifran los mensajes trabajo y qué opciones están disponibles para usted.  <br/> |
|[¿Cómo se puede abrir un mensaje protegido?](https://support.office.com/article/1157a286-8ecc-4b1e-ac43-2a608fbf3098.aspx) <br/> |Un usuario final que desea leer un mensaje protegido que se envió. En este artículo se incluye información acerca de cómo leer los mensajes en varias versiones de Outlook y de las cuentas de correo electrónico diferentes, incluidos aquellos fuera de Office 365, como gmail y las cuentas de Yahoo!.  <br/> |
|[Enviar, ver y responder a los mensajes cifrados en Outlook](https://support.office.com/article/eaa43495-9bbb-4fca-922a-df90dee51980.aspx) <br/> |Un usuario final que desea enviar, ver o responder a un mensaje cifrado desde Outlook. Incluso si no es un miembro de una organización de Office 365, seguir recibiendo la notificación de los mensajes cifrados enviados a usted en Outlook. Use este artículo para obtener instrucciones sobre cómo ver y responder a los mensajes cifrados enviados desde Office 365.  <br/> |
|[Enviar un mensaje firmado digitalmente o cifrado](https://support.office.com/article/a18ecf7f-a7ac-4edd-b02e-687b05eff547) <br/> |Un usuario final que desea enviar, ver o responder a los mensajes cifrados con Outlook para Mac. En este artículo también se trata el uso de los métodos de cifrado que no sea OME, como S/MIME.  <br/> |
|[Ver los mensajes cifrados en su dispositivo Android](https://support.office.com/article/83d60f17-2305-407a-a762-7d518401fdeb) <br/> |Un usuario final que ha recibido un mensaje cifrado con cifrado de mensajes de Office 365 en su dispositivo Android, puede usar la aplicación de Visor de OME gratuita para ver el mensaje y enviar una respuesta cifrada. En este artículo se explica cómo.  <br/> |
|[Ver los mensajes cifrados en su iPhone o iPad](https://support.office.com/article/4d631321-0d26-4bcc-a483-d294dd0b1caf) <br/> |Un usuario final que ha recibido un mensaje cifrado con cifrado de mensajes de Office 365 en su iPhone o iPad, puede usar la aplicación de Visor de OME gratuita para ver el mensaje y enviar una respuesta cifrada. En este artículo se explica cómo.  <br/> |
|Office 365 Message Encryption (OME) (este artículo)  <br/> |Un administrador de Office 365 o Exchange Online Protection que obtenga información sobre dónde puede encontrar recursos adicionales que desea.  <br/> |
|[Comparar versiones de OME](ome-version-comparison.md)  <br/> |Un administrador de Office 365 o Exchange Online Protection que desea información sobre las diferencias entre Office 365 Message Encryption heredado y las nuevas capacidades OME como el modo en puedan trabajar juntos.  <br/> |
|[Preguntas más frecuentes sobre el cifrado de mensajes de Office 365](ome-faq.md) <br/> |Incluida la concesión de licencias y una comparación entre las nuevas capacidades y OME heredado de preguntas más frecuentes sobre un administrador de Office 365 o Exchange Online Protection que desea respuestas a con frecuencia.  <br/> |
|[Configurar las nuevas capacidades de cifrado de mensajes de Office 365](set-up-new-message-encryption-capabilities.md) <br/> |Un administrador de Office 365 o Exchange Online Protection que desea para aprender a configurar las nuevas capacidades de cifrado de mensajes de Office 365 para la organización de Office 365.  <br/> |
|[Definir reglas de flujo de correo para cifrar mensajes de correo electrónico en Office 365](define-mail-flow-rules-to-encrypt-email.md) <br/> |Un administrador de Office 365 o Exchange Online Protection que ya ha establecido el cifrado de mensajes de Office 365 y está listo para definir las reglas de flujo de correo para cifrar automáticamente los mensajes de correo electrónico enviados desde su organización.  <br/> |
|[Administrar el cifrado de mensajes de Office 365](manage-office-365-message-encryption.md) <br/> |Un administrador de Office 365 o Exchange Online Protection que ya ha configurado el cifrado de mensajes de Office 365 y desea configurar la configuración opcional de OME.  <br/> |
|[Agregar la marca de su organización a los mensajes cifrados](add-your-organization-brand-to-encrypted-messages.md) <br/> |Un administrador de Office 365 o Exchange Online Protection que desea aplicar a su compañía para personalizar la apariencia de los mensajes de correo electrónico de cifrado de mensajes de Office 365 de su organización y el contenido del portal de OME de personalización de marca.  <br/> |
|[Revocación de correo electrónico de cifrado de mensajes de Office 365](revoke-ome-encrypted-mail.md) <br/> |Un administrador de Office 365 o Exchange Online Protection que desea revocar un correo electrónico que se cifró mediante el cifrado de mensajes de Office 365.  <br/> |
|Cifrado de mensajes de Office 365 en la [Directiva de mensajes y la descripción del servicio de cumplimiento de normas](https://technet.microsoft.com/en-us/library/5c43c8eb-f8f7-4b5a-a743-b1dab7dc2fc8#bkmk_O365_MessageEncryption) <br/> |Busca una descripción detallada de la característica de cifrado de mensajes de Office 365, admite la inclusión de SKU, disponibles en Office 365.  <br/> |
|[Información heredada para el cifrado de mensajes de Office 365](legacy-information-for-message-encryption.md) <br/> |Un administrador de Office 365 o Exchange Online Protection que ya ha establecido el cifrado de mensajes de Office 365 y se desea obtener información acerca de cómo ha funcionado OME antes del lanzamiento de las nuevas capacidades. Mientras no se puede configurar una nueva implementación mediante OME sin las nuevas capacidades, Microsoft sigue siendo compatible con las implementaciones existentes.  <br/> |
||

El resto de este artículo se aplica a las nuevas capacidades OME.
  
## <a name="how-office-365-message-encryption-works"></a>Cómo funciona el cifrado de mensajes de Office 365

Cifrado de mensajes de Office 365 es un servicio en línea que se basa en Microsoft Azure Rights Management (RMS Azure) que forma parte de la protección de la información de Azure. Los administradores de Office 365 pueden definir reglas de flujo de correo para determinar las condiciones para el cifrado. Por ejemplo, una regla puede requerir el cifrado de todos los mensajes dirigidos a un destinatario concreto.
  
Cuando alguien le envía un mensaje de correo electrónico en Exchange Online que coincide con una regla de flujo de correo cifrado, el mensaje se cifra antes de enviarlo. Todos los usuarios finales de Office 365 que usan a los clientes de Outlook para leer correo reciben nativo, primera clase experiencias para el correo cifrado y protegido con derechos de lectura, incluso si no está en la misma organización que el remitente. Los clientes de Outlook admitidos incluyen escritorio de Outlook, Mac de Outlook, Outlook mobile en iOS y Android y Outlook Web App.
  
En el portal OME mediante su cuenta de Microsoft o credenciales de Gmail o Yahoo fácilmente pueden autenticar a los destinatarios de los mensajes cifrados que reciben correo cifrado o protegidos por derechos enviado a sus cuentas Outlook.com, Gmail y Yahoo.
  
Los usuarios finales que leer correo cifrado o protegidos por derechos en los clientes que no sean de Outlook use también el portal de OME para ver mensajes cifrados y protegidos por derechos que reciben.
  
Hemos aumentado los límites de tamaño de mensajes y datos adjuntos que se pueden cifrar mediante el cifrado de mensajes de Office 365. Para obtener más información acerca de los límites, vea [límites de Exchange Online.](https://technet.microsoft.com/en-us/library/exchange-online-limits.aspx)
  
## <a name="defining-rules-for-office-365-message-encryption"></a>Definición de reglas para el cifrado de mensajes de Office 365

Una forma de habilitar las nuevas capacidades de Office 365 para cifrado de mensajes está dirigido a administradores de Exchange Online y Exchange Online Protection definir reglas de flujo de correo. Estas reglas determinan en qué correo electrónico de condiciones se deben cifrar los mensajes. Cuando se establece una acción de cifrado para una regla, todos los mensajes que coincidan con las condiciones de regla se cifran antes de que se envían.
  
Reglas de flujo de correo son flexibles, lo que le permite combinar las condiciones para que pueda cumplir los requisitos de seguridad específica en una sola regla. Por ejemplo, puede crear una regla para cifrar todos los mensajes que contienen palabras clave especificadas y dirigidos a destinatarios externos. Las nuevas capacidades de cifrado de mensajes de Office 365 también cifran las respuestas de los destinatarios de correo electrónico cifrado.
  
Para obtener más información acerca de cómo crear reglas de flujo para aprovechar las nuevas capacidades OME de correo, consulte [Definir reglas para el cifrado de mensajes de Office 365](define-mail-flow-rules-to-encrypt-email.md).
  
## <a name="sending-viewing-and-replying-to-encrypted-email-messages"></a>Enviar, ver y responder mensajes de correo electrónico cifrado

Con el cifrado de mensajes de Office 365, los usuarios pueden enviar correo electrónico cifrado de Outlook y Outlook en el web. Además, los administradores pueden configurar reglas de flujo de correo en Office 365 para cifrar automáticamente los correos electrónicos según las condiciones de coincidente o o de otra palabra clave.
  
Los destinatarios de los mensajes cifrados que se encuentren en Office 365 organizaciones podrán leer esos mensajes sin ningún problema en cualquier versión de Outlook, incluidos Outlook para PC, Outlook para Mac, Outlook en la web, Outlook para iOS y Outlook para Android. Los usuarios que reciben mensajes cifrados en otros clientes de correo electrónico pueden ver los mensajes en el portal de OME.
  
Para obtener instrucciones detalladas acerca de cómo enviar y ver los mensajes cifrados, eche un vistazo a estos artículos:
  
- [¿Cómo se puede abrir un mensaje protegido?](https://support.office.com/article/1157a286-8ecc-4b1e-ac43-2a608fbf3098.aspx)

- [Enviar, ver y responder a los mensajes cifrados en Outlook](https://support.office.com/article/eaa43495-9bbb-4fca-922a-df90dee51980.aspx)

## <a name="get-started-with-the-new-ome-capabilities"></a>Introducción a las nuevas capacidades OME

Si está listo para empezar a usar las nuevas capacidades OME dentro de la organización, consulte [Configurar nuevas capacidades de cifrado de mensajes de Office 365](set-up-new-message-encryption-capabilities.md).
