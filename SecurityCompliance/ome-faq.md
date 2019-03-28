---
title: Preguntas más frecuentes sobre el cifrado de mensajes de Office 365
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 02/11/2019
ms.audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 0432dce9-d9b6-4e73-8a13-4a932eb0081e
description: ¿Tiene alguna pregunta sobre cómo funcionan las nuevas capacidades de protección de mensajes en Office 365? Compruebe si hay una respuesta aquí.
ms.openlocfilehash: 2c140ef476b5fe19ef3655b062a3f197d36222e7
ms.sourcegitcommit: 8a65a29aa3bfe5dcad0ff152a7cd795e02877dd9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2019
ms.locfileid: "30936790"
---
# <a name="office-365-message-encryption-faq"></a>Preguntas más frecuentes sobre el cifrado de mensajes de Office 365

¿Tiene alguna pregunta sobre cómo funcionan las nuevas capacidades de protección de mensajes en Office 365? Compruebe si hay una respuesta aquí. Además, eche un vistazo a las [preguntas más frecuentes sobre la protección de datos en Azure Information Protection](https://docs.microsoft.com/information-protection/get-started/faqs-rms) para obtener respuestas a preguntas sobre el servicio de protección de datos, Azure Rights Management, en Azure Information Protection.

||
|:-----|
|Este artículo forma parte de una amplia serie de artículos sobre el cifrado de mensajes de Office 365. Este artículo está destinado a los administradores y ITPros. Si solo está buscando información sobre cómo enviar o recibir un mensaje cifrado, vea la lista de artículos en el cifrado de [mensajes de Office 365 (OME)](ome.md) y busque el artículo que mejor se adapte a sus necesidades. |
||
  
## <a name="what-is-office-365-message-encryption-ome"></a>¿Qué es el cifrado de mensajes de Office 365 (OME)?

OME combina capacidades de cifrado de correo electrónico y administración de derechos. Las capacidades de administración de derechos están basadas en Azure Information Protection.
  
## <a name="who-can-use-ome"></a>¿Quién puede usar OME?

Puede usar las nuevas funciones para OME en las siguientes condiciones:
  
- Si nunca ha configurado OME o IRM para Exchange online en Office 365.
    
- Si ha configurado OME e IRM, puede seguir estos pasos si va a usar el servicio Azure Rights Management desde Azure Information Protection.
    
- Si usa Exchange Online con el servicio de administración de derechos de Active Directory (AD RMS), no puede habilitar estas nuevas funcionalidades inmediatamente. En su lugar, debe [migrar AD RMS a Azure Information Protection en](https://docs.microsoft.com/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms) primer lugar. Una vez finalizada la migración, puede configurar OME correctamente. 
    
    Si opta por seguir usando AD RMS local con Exchange online en lugar de migrar a Azure Information Protection, no podrá usar estas nuevas funciones de.
    
## <a name="what-subscriptions-do-i-need-to-use-the-new-ome-capabilities"></a>¿Qué suscripciones necesito para usar las nuevas capacidades de OME?

Para usar las nuevas capacidades de OME, necesita uno de los siguientes planes:
  
- El cifrado de mensajes de Office 365 se ofrece como parte de Office 365 Enterprise E3 y E5, Microsoft Enterprise E3 y E5, Microsoft 365 Business, Office 365 a1, a3 y A5, y Office 365 Government G3 y G5. Los clientes no necesitan licencias adicionales para recibir las nuevas capacidades de protección de Azure Information Protection. 
    
- También puede Agregar el plan 1 de Azure Information Protection a los siguientes planes para recibir las nuevas capacidades de cifrado de mensajes de Office 365: Plan 1 de Exchange Online, Exchange Online plan 2, Office 365 F1, Office 365 empresa Essentials, Office 365 empresa Premium o Office 365 Enterprise E1.
    
- Cada usuario que se beneficie de Office 365 el cifrado de mensajes debe disponer de una licencia que abarque la característica.
    
- Para obtener la lista completa, consulte descripciones del [servicio de Exchange Online](https://technet.microsoft.com/library/exchange-online-service-description.aspx) para el cifrado de mensajes de Office 365. 
    
## <a name="can-i-use-exchange-online-with-bring-your-own-key-byok-in-azure-information-protection"></a>¿Puedo usar Exchange Online con la opción de traer su propia clave (BYOK) en Azure Information Protection?

Afirma! Microsoft recomienda que complete los pasos para configurar BYOK antes de configurar OME.
  
Para obtener más información sobre BYOK, consulte [Planning and Implementing Your Azure Information Protection tenant Key](https://docs.microsoft.com/information-protection/plan-design/plan-implement-tenant-key).
  
## <a name="do-ome-and-byok-with-azure-information-protection-change-microsofts-approach-to-third-party-data-requests-such-as-subpoenas"></a>¿OME y BYOK con Azure Information Protection cambian el enfoque de Microsoft a las solicitudes de datos de terceros, como las citacións?

No. OME y la opción de proporcionar y controlar las claves de cifrado propias, denominadas BYOK, de Azure Information Protection no se diseñaron para responder a las inFormaciones de cumplimiento de la ley. OME, con BYOK para Azure Information Protection, se diseñó para clientes centrados en el cumplimiento normativo. Microsoft realiza muy en serio solicitudes de terceros para los datos de los clientes. Como proveedor de servicios en la nube, siempre proponemos la privacidad de los datos de clientes. En el caso de que recibamos una citación, siempre intentaremos redirigir a la tercera parte al cliente para obtener la información. (Lea el blog de Brad Martínez: [proteger los datos de clientes de la supervisión gubernamental](https://blogs.microsoft.com/blog/2013/12/04/protecting-customer-data-from-government-snooping/)). Periódicamente publicamos información detallada de la solicitud que recibimos. Para obtener más información acerca de las solicitudes de datos de terceros, vea [responder a las solicitudes de gobierno y cumplimiento de la ley para acceder a datos de clientes](https://www.microsoft.com/en-us/trustcenter/privacy/govt-requests-for-data) en el centro de confianza de Microsoft. Consulte también "revelación de datos de clientes" en los [términos de servicios en línea (OST)](https://www.microsoft.com/en-us/Licensing/product-licensing/products.aspx).
  
## <a name="how-is-this-feature-related-to-legacy-office-365-message-encryption-ome-and-information-rights-management-irm-features"></a>¿Cómo se relaciona esta característica con las características heredadas de Office 365 cifrado de mensajes (OME) y Information Rights Management (IRM)?

Las nuevas funciones para el cifrado de mensajes de Office 365 son una evolución de las soluciones de IRM y de OME heredadas existentes. En la tabla siguiente se proporcionan más detalles.
  
**Comparación de las capacidades heredadas de OME, IRM y las nuevas funciones de OME**

|**Función**|**Versiones anteriores de OME**|**IRM**|**Nuevas funciones de OME**|
|:-----|:-----|:-----|:-----|
|**Enviar correo electrónico cifrado**|Solo a través de reglas de flujo de correo de Exchange|Usuario final iniciado desde Outlook para PC, Outlook para Mac o Outlook en la web; o mediante reglas de flujo de correo de Exchange|Usuario final iniciado desde Outlook para PC, Outlook para Mac o Outlook en la web; o mediante reglas de flujo de correo|
|**Administración de derechos**|-|No reEnviar opciones y plantillas personalizadas|Opción no reEnviar, opción de solo codificación, plantillas predeterminadas y personalizadas|
|**Tipo de destinatario admitido**|Solo destinatarios externos|Solo destinatarios internos|Destinatarios internos y externos|
|**Experiencia con el destinatario**|Los destinatarios externos recibieron un mensaje HTML que se descargaron y abrieron en un explorador o en una aplicación móvil descargada.|Los destinatarios internos solo recibieron correo electrónico cifrado en Outlook para PC, Outlook para Mac y Outlook en la Web.|Los destinatarios internos y externos reciben correo electrónico en Outlook para PC, Outlook para Mac, Outlook en la web, Outlook para Android y Outlook para iOS, o a través de un portal web, independientemente de si están o no en la misma organización de Office 365 o en cualquier Office 365 Organization. El portal OME no requiere descargas independientes.|
|**Proporcionar su propio soporte clave**|No disponible|No disponible| BYOK compatible|

## <a name="how-do-i-enable-the-new-ome-capabilities-for-my-organization"></a>¿Cómo habilito las nuevas funciones de OME para mi organización?

Consulte [configurar nuevas capacidades de cifrado de mensajes de Office 365](set-up-new-message-encryption-capabilities.md).
  
## <a name="will-the-previous-version-of-ome-be-deprecated"></a>¿La versión anterior de OME estará en desuso?

Puede seguir usando la versión anterior de OME; en este momento, no estará en desuso. Sin embargo, recomendamos encarecidamente que las organizaciones usen la solución OME nueva y mejorada. Los clientes que todavía no han implementado OME no pueden configurar una nueva implementación de la versión anterior de OME.
  
## <a name="my-organization-uses-active-directory-rights-management-can-i-use-this-functionality"></a>Mi organización usa la administración de derechos de Active Directory, ¿puedo usar esta funcionalidad?

No. Si usa Exchange Online con el servicio de administración de derechos de Active Directory (AD RMS), no puede habilitar estas nuevas funcionalidades inmediatamente. En su lugar, debe [migrar AD RMS a Azure Information Protection en](https://docs.microsoft.com/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms) primer lugar. 
  
## <a name="my-organization-has-an-exchange-hybrid-deployment-can-i-use-this-feature"></a>Mi organización tiene una implementación híbrida de Exchange. ¿Puedo usar esta característica?

Los usuarios locales pueden enviar correo cifrado con las reglas de flujo de correo de Exchange Online. Para ello, debe redirigir el correo electrónico a través de Exchange Online. Para obtener más información, vea [parte 2: configurar el correo para que fluya desde su servidor de correo electrónico a Office 365](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-to-route-mail#part-2-configure-mail-to-flow-from-your-email-server-to-office-365).
  
## <a name="what-email-client-do-i-need-to-use-in-order-to-create-an-ome-encrypted-message-what-applications-are-supported-for-sending-protected-messages"></a>¿Qué cliente de correo electrónico debo usar para crear un mensaje cifrado OME? ¿Qué aplicaciones se admiten para enviar mensajes protegidos?

Puede crear mensajes protegidos desde Outlook 2016, y Outlook en la web, y Outlook en la Web.
  
## <a name="what-email-clients-are-supported-to-read-and-reply-to-protected-emails"></a>¿Qué clientes de correo electrónico se admiten para leer y responder a los correos electrónicos protegidos?

Puede leer y responder desde Outlook para PC y Mac (2013 y 2016), Outlook en la web y Outlook Mobile (Android e iOS) si es un usuario de Office 365. También puede usar el cliente de correo nativo de iOS si su organización lo permite. Si no es un usuario de Office 365, puede leer y responder a mensajes cifrados en la web a través del explorador Web.
  
## <a name="what-file-types-are-supported-as-attachments-in-protected-emails-do-attachments-inherit-the-protection-policies-associated-with-protected-emails"></a>¿Qué tipos de archivo se admiten como datos adjuntos en correos electrónicos protegidos? ¿Los datos adjuntos heredan las directivas de protección asociadas con los correos electrónicos protegidos?

Puede adjuntar cualquier tipo de archivo a un correo protegido, pero las directivas de protección solo se aplican a los formatos de archivo que se mencionan [aquí](https://docs.microsoft.com/information-protection/rms-client/client-admin-guide-file-types). 
  
Si se admite un formato de archivo, como un archivo de Word, Excel o PowerPoint, el archivo siempre está protegido, incluso después de que el destinatario haya descargado los datos adjuntos. Por ejemplo, si un dato adjunto está protegido por no reEnviar y el destinatario original descarga y reenvía los datos adjuntos a un nuevo destinatario, el nuevo destinatario no podrá abrir el archivo protegido.
  
## <a name="are-pdf-file-attachments-supported"></a>¿Se admiten los datos adjuntos de archivos PDF?

Si adjunta un archivo PDF a un mensaje protegido, el propio mensaje estará protegido, pero no se aplicará ninguna protección adicional al archivo PDF una vez que el destinatario lo haya recibido. Esto significa que el destinatario puede guardar, reEnviar, copiar e imprimir el archivo PDF.
  
## <a name="are-onedrive-for-business-attachments-supported"></a>¿Los datos adjuntos de OneDrive para la empresa son compatibles?

Not yet. Los datos adjuntos de OneDrive para la empresa no son compatibles y los usuarios finales no pueden cifrar un correo que contenga datos adjuntos de OneDrive para la empresa en la nube.
  
## <a name="can-i-automatically-encrypt-messages-by-setting-up-policies"></a>¿Puedo cifrar mensajes automáticamente mediante la configuración de directivas?

Sí. Usar reglas de flujo de correo en Exchange Online para cifrar automáticamente un mensaje en función de ciertas condiciones. Por ejemplo, puede crear directivas basadas en el identificador del destinatario, el dominio del destinatario o el contenido en el cuerpo o el asunto del mensaje. Consulte [definir reglas de flujo de correo para cifrar mensajes de correo electrónico en Office 365.](define-mail-flow-rules-to-encrypt-email.md)
  
## <a name="can-i-automatically-encrypt-messages-by-setting-up-policies-in-data-loss-prevention-dlp-through-the-security-amp-compliance-center"></a>¿Puedo cifrar mensajes automáticamente mediante la configuración de directivas en prevención de pérdida de datos (DLP &amp; ) a través del centro de seguridad y cumplimiento?

Afirma! Puede configurar reglas de flujo de correo en Exchange online o mediante DLP en el centro de &amp; seguridad y cumplimiento.
  
## <a name="can-i-open-encrypted-messages-sent-to-a-shared-mailbox"></a>¿Puedo abrir mensajes cifrados enviados a un buzón compartido?

Los mensajes cifrados actualmente no son compatibles con un buzón compartido.

## <a name="can-i-customize-encrypted-messages-with-my-company-branding"></a>¿Puedo personalizar mensajes cifrados con la personalización de marca de mi empresa?

Afirma! Para obtener información sobre cómo personalizar los mensajes de correo electrónico y el portal OME, consulte Agregar la marca de su organización a los mensajes cifrados. Consulte [Agregar la marca de su organización a los mensajes cifrados.](add-your-organization-brand-to-encrypted-messages.md)
  
## <a name="are-there-any-reporting-capabilities-or-insights-for-encrypted-emails"></a>¿Hay información o capacidades de informes para los correos electrónicos cifrados?

No en este momento, pero lo estará próximamente.
  
## <a name="can-i-use-message-encryption-with-compliance-features-such-as-ediscovery"></a>¿Puedo usar el cifrado de mensajes con características de cumplimiento como la exhibición de documentos electrónicos?

Sí. Todos los mensajes de correo electrónico cifrados son detectables por las características de cumplimiento de Office 365.
  

