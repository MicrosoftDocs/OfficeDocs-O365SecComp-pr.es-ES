---
title: Preguntas más frecuentes sobre el cifrado de mensajes de Office 365
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 10/9/2018
ms.audience: ITPro
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 0432dce9-d9b6-4e73-8a13-4a932eb0081e
description: ¿Tiene una pregunta acerca de cómo funcionan las nuevas capacidades de protección de mensajes en Office 365? Compruebe si hay una respuesta aquí.
ms.openlocfilehash: e35495106b44ccb566f4da743264def8c7d4f96f
ms.sourcegitcommit: 7e2a0185cadea7f3a6afc5ddc445eac2e1ce22eb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/11/2019
ms.locfileid: "29696274"
---
# <a name="office-365-message-encryption-faq"></a>Preguntas más frecuentes sobre el cifrado de mensajes de Office 365

¿Tiene una pregunta acerca de cómo funcionan las nuevas capacidades de protección de mensajes en Office 365? Compruebe si hay una respuesta aquí. Además, eche un vistazo [preguntas frecuentes sobre protección de datos en la protección de la información de Azure](https://docs.microsoft.com/information-protection/get-started/faqs-rms) para obtener respuestas a preguntas sobre el servicio de protección de datos, Azure Rights Management, en la protección de la información de Azure.

||
|:-----|
|En este artículo es parte de una serie de artículos sobre Office 365 Message Encryption más grande. En este artículo está destinada a los administradores y profesionales de TI. Si sólo está buscando información en enviar o recibir un mensaje cifrado, vea la lista de los artículos de [Office 365 Message Encryption (OME)](ome.md) y busque el artículo que mejor se adapte a sus necesidades. |
||
  
## <a name="what-is-office-365-message-encryption-ome"></a>¿Qué es Office 365 Message Encryption (OME)?

OME combina las capacidades de administración de derechos y cifrado de correo electrónico. Capacidades de administración de derechos se con tecnología de protección de la información de Azure.
  
## <a name="who-can-use-ome"></a>¿Quién puede usar OME?

Puede usar las nuevas capacidades para OME en las siguientes condiciones:
  
- Si nunca ha establecido seguridad OME o IRM para Exchange Online en Office 365.
    
- Si ha configurado OME e IRM, puede usar estos pasos si usa el servicio de administración de derechos de Azure de protección de la información de Azure.
    
- Si se usa Exchange Online con el servicio de administración de derechos de Active Directory (AD RMS), no se puede habilitar estas nuevas capacidades de inmediato. En su lugar, debe [migrar AD RMS para protección de la información de Azure](https://docs.microsoft.com/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms) en primer lugar. Cuando haya terminado de la migración, puede configurar correctamente OME. 
    
    Si opta por seguir utilizando local AD RMS con Exchange Online en lugar de migrar a la protección de la información de Azure, no podrá usar estas nuevas capacidades.
    
## <a name="what-subscriptions-do-i-need-to-use-the-new-ome-capabilities"></a>¿Qué suscripciones es necesario usar las nuevas capacidades OME?

Para usar las nuevas capacidades OME, necesita uno de los siguientes planes:
  
- Office 365 cifrado de mensajes se ofrece como parte de Office 365 E3 y E5, Microsoft E3 y E5, Office 365 A1, A3 y A5 y Office 365 G3 y G5. Los clientes no necesitan licencias adicionales para recibir las nuevas capacidades de protección con tecnología de protección de la información de Azure. 
    
- También puede agregar planes de Azure información protección Plan 1 a los siguientes elementos para recibir las nuevas capacidades de Office 365 Message Encryption: Exchange Online Plan 1, Exchange Online Plan 2, Office 365 F1, Office 365 Business Essentials, Premium de negocio de Office 365, o Office 365 Enterprise E1.
    
- Debe tener licencia para debe estar cubierto por la característica de cada usuario al sacar provecho de cifrado de mensajes de Office 365.
    
- Para obtener la lista completa, consulte las [descripciones del servicio de Exchange Online](https://technet.microsoft.com/library/exchange-online-service-description.aspx) para Office 365 Message Encryption. 
    
## <a name="can-i-use-exchange-online-with-bring-your-own-key-byok-in-azure-information-protection"></a>¿Puedo usar Exchange Online con Traer su propia clave (BYOK) en la protección de la información de Azure?

¡Sí! Microsoft recomienda que complete los pasos para configurar BYOK antes de configurar OME.
  
Para obtener más información sobre BYOK, consulte [planeación e implementación de la clave de inquilino de protección de la información de Azure](https://docs.microsoft.com/information-protection/plan-design/plan-implement-tenant-key).
  
## <a name="do-ome-and-byok-with-azure-information-protection-change-microsofts-approach-to-third-party-data-requests-such-as-subpoenas"></a>¿OME y BYOK con protección de la información de Azure cambian el enfoque de Microsoft para las solicitudes de datos de terceros, como su orden?

No. OME y la opción para ofrecer y controlar sus propios claves de cifrado, denominadas BYOK, de protección de la información de Azure no se han diseñado para responder a su orden de aplicación de la legislación. OME, con BYOK para la protección de la información de Azure, se ha diseñado para clientes centrados en el cumplimiento de normas. Microsoft toma muy en serio las solicitudes de terceros para los datos de cliente. Como un proveedor de servicios en la nube, siempre se recomiendan para la privacidad de los datos de cliente. En el caso de que se obtenga una citación, intentaremos siempre redirigir el tercero al cliente para obtener la información. (Lea el blog de Brad Smith: [Protecting los datos de cliente de gobierno fisgonear](https://blogs.microsoft.com/blog/2013/12/04/protecting-customer-data-from-government-snooping/)). Periódicamente se publique información detallada de la solicitud de que recepción. Para obtener más información acerca de las solicitudes de datos de terceros, vea [responder a solicitudes legales para tener acceso a los datos de cliente y de gobierno](https://www.microsoft.com/en-us/trustcenter/privacy/govt-requests-for-data) en Microsoft Trust Center. Consulte también "Divulgación de datos de clientes" en [Términos de servicios en línea (OST)](https://www.microsoft.com/en-us/Licensing/product-licensing/products.aspx).
  
## <a name="how-is-this-feature-related-to-legacy-office-365-message-encryption-ome-and-information-rights-management-irm-features"></a>¿Cómo se relaciona esta característica con características heredadas de Office 365 Message Encryption (OME) y de Information Rights Management (IRM)?

Las nuevas capacidades de Office 365 para cifrado de mensajes son una evolución de la IRM existente y las soluciones antiguas de OME. En la siguiente tabla se proporciona información más detallada.
  
**Comparación de OME heredado, IRM y nuevas capacidades OME**

|**Función**|**Versiones anteriores de OME**|**IRM**|**Nuevas capacidades OME**|
|:-----|:-----|:-----|:-----|
|**Enviar un correo electrónico cifrado**|Sólo a través de reglas de flujo de correo de Exchange|Para el usuario final iniciado desde Outlook para PC, Outlook para Mac o Outlook en la web; o a través de Exchange de reglas de flujo de correo|Para el usuario final iniciado desde Outlook para PC, Outlook para Mac o Outlook en la web; o a través de reglas de flujo de correo|
|**Administración de derechos**|-|Realice la opción no reenviar y las plantillas personalizadas|Realice la opción no reenviar, opción sólo cifrar, de forma predeterminada y las plantillas personalizadas|
|**Tipo de destinatario compatible**|Sólo los destinatarios externos|Sólo los destinatarios internos|Destinatarios internos y externos|
|**Experiencia de destinatario**|Destinatarios externos reciben un mensaje HTML que había descargado y había abierto en un explorador o aplicación móvil.|Los destinatarios internos sólo reciben correo electrónico cifrado en Outlook para PC, Outlook para Mac y Outlook en el web.|Los destinatarios internos y externos reciben correo electrónico en Outlook para PC, Outlook para Mac, Outlook en la web, Outlook para Android y Outlook para iOS, o a través de un portal web, independientemente de si están o no en la misma organización de Office 365 o en cualquier Office 365 organización. El portal de OME no requiere ninguna descarga independiente.|
|**Traer la compatibilidad con su propia clave**|No disponible|No disponible| BYOK compatibles|

## <a name="how-do-i-enable-the-new-ome-capabilities-for-my-organization"></a>¿Cómo se puede habilitar las nuevas capacidades OME para mi organización?

Consulte [Configurar nuevas capacidades de cifrado de mensajes de Office 365](set-up-new-message-encryption-capabilities.md).
  
## <a name="will-the-previous-version-of-ome-be-deprecated"></a>¿La versión anterior de OME desusada?

Aún puede usar la versión anterior de OME, no quedará obsoleto en este momento. Sin embargo, recomendamos encarecidamente las organizaciones usen la solución OME nueva y mejorada. Los clientes que aún no ha implementado OME no se pueden configurar una nueva implementación de la versión anterior de OME.
  
## <a name="my-organization-uses-active-directory-rights-management-can-i-use-this-functionality"></a>Mi organización usa Active Directory Rights Management, ¿puedo usar esta funcionalidad?

No. Si se usa Exchange Online con el servicio de administración de derechos de Active Directory (AD RMS), no se puede habilitar estas nuevas capacidades de inmediato. En su lugar, debe [migrar AD RMS para protección de la información de Azure](https://docs.microsoft.com/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms) en primer lugar. 
  
## <a name="my-organization-has-an-exchange-hybrid-deployment-can-i-use-this-feature"></a>Mi organización tiene una implementación híbrida de Exchange. ¿Puedo usar esta característica?

Los usuarios pueden enviar correo cifrado mediante reglas de flujo de correo de Exchange Online en local. Para ello, debe redirigir el correo electrónico a través de Exchange Online. Para obtener más información, vea [parte 2: configurar el correo de flujo de su servidor de correo electrónico a Office 365](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-to-route-mail#part-2-configure-mail-to-flow-from-your-email-server-to-office-365).
  
## <a name="what-email-client-do-i-need-to-use-in-order-to-create-an-ome-encrypted-message-what-applications-are-supported-for-sending-protected-messages"></a>¿Qué cliente de correo electrónico es necesario usar con el fin de crear un mensaje cifrado OME? ¿Qué aplicaciones son compatibles para el envío de mensajes protección?

Puede crear mensajes protegidos de 2016 de Outlook y Outlook 2013 para PC y Mac y de Outlook en la web.
  
## <a name="what-email-clients-are-supported-to-read-and-reply-to-protected-emails"></a>¿Qué clientes de correo electrónico se admiten para leer y responder a mensajes de correo electrónico protegidos?

Puede leer y responder desde Outlook para PC y Mac (2013 y 2016), Outlook en la web y móviles de Outlook (Android y iOS) si es un usuario de Office 365. También puede usar al cliente de correo nativos iOS si la organización lo permite. Si es un usuario que no sean Office 365, puede leer y responder a los mensajes cifrados en la web a través de su explorador web.
  
## <a name="what-file-types-are-supported-as-attachments-in-protected-emails-do-attachments-inherit-the-protection-policies-associated-with-protected-emails"></a>¿Qué tipos de archivo se admiten como datos adjuntos en mensajes de correo electrónico protegidos? ¿Los datos adjuntos heredará las políticas de protección asociadas con los correos electrónicos protegidos?

Puede adjuntar cualquier tipo de archivo a un correo protegido, sin embargo, las directivas de protección se aplican sólo en el archivo formatos mencionados [aquí](https://docs.microsoft.com/information-protection/rms-client/client-admin-guide-file-types). 
  
Si se admite un formato de archivo, como un archivo de Word, Excel o PowerPoint, el archivo siempre está protegido, incluso después de que los datos adjuntos se ha descargado el destinatario. Por ejemplo, si un archivo adjunto está protegido por no reenviar, y el destinatario original descargas y reenvía los datos adjuntos a un destinatario nuevo, el nuevo destinatario no podrán abrir el archivo protegido.
  
## <a name="are-pdf-file-attachments-supported"></a>¿Se admiten datos adjuntos de archivo PDF?

Si se adjunta un archivo PDF a un mensaje protegido, se protegerá el propio mensaje, pero después de que el destinatario lo ha recibido, no se aplicará al archivo PDF protección adicional. Esto significa el destinatario puede guardar como, reenviar, copiar e imprimir el archivo PDF.
  
## <a name="are-onedrive-for-business-attachments-supported"></a>¿Son OneDrive para los archivos adjuntos del negocio compatibles?

Todavía no. No se admiten OneDrive para los archivos adjuntos del negocio y los usuarios finales no pueden cifrar un correo electrónico que contiene una OneDrive en la nube para los datos adjuntos del negocio.
  
## <a name="can-i-automatically-encrypt-messages-by-setting-up-policies"></a>¿Puedo cifrar automáticamente los mensajes mediante la configuración de directivas?

Sí. Use reglas de flujo de correo en Exchange Online para cifrar automáticamente un mensaje en función de ciertas condiciones. Por ejemplo, puede crear directivas que se basan en el destinatario identificador de dominio de destinatario, o en el contenido en el cuerpo o el asunto del mensaje. Vea [definir reglas de flujo de correo para cifrar mensajes de correo electrónico en Office 365.](define-mail-flow-rules-to-encrypt-email.md)
  
## <a name="can-i-automatically-encrypt-messages-by-setting-up-policies-in-data-loss-prevention-dlp-through-the-security-amp-compliance-center"></a>¿Automáticamente cifrar mensajes mediante la configuración de directivas de prevención de pérdida de datos (DLP) a través de la seguridad &amp; centro de cumplimiento?

¡Sí! Puede configurar reglas de flujo de correo en Exchange Online o mediante el uso de DLP en la seguridad &amp; centro de cumplimiento.
  
## <a name="can-i-open-encrypted-messages-sent-to-a-shared-mailbox"></a>¿Puedo abrir los mensajes cifrados enviados a un buzón compartido?

Los mensajes cifrados actualmente no se admiten para un buzón compartido.

## <a name="can-i-customize-encrypted-messages-with-my-company-branding"></a>¿Puedo personalizar los mensajes cifrados con mi compañía de personalización de marca?

¡Sí! Para obtener información sobre cómo personalizar los mensajes de correo electrónico y el portal de OME, vea Agregar marca de su organización a los mensajes cifrados. Vea [Agregar marca de su organización a los mensajes cifrados.](add-your-organization-brand-to-encrypted-messages.md)
  
## <a name="are-there-any-reporting-capabilities-or-insights-for-encrypted-emails"></a>¿Hay alguna informes capacidades o conocimientos para mensajes de correo electrónico cifrados?

No en este momento pero próximamente.
  
## <a name="can-i-use-message-encryption-with-compliance-features-such-as-ediscovery"></a>¿Puedo usar el cifrado de mensajes con las características de cumplimiento de normas como exhibición de documentos electrónicos?

Sí. Todos los mensajes de correo electrónico cifrado son reconocibles por las características de cumplimiento de normas de Office 365.
  

