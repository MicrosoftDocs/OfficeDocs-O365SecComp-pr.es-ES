---
title: Correo de solución de problemas enviado a Office 365
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 05/02/2016
audience: ITPro
ms.topic: troubleshooting
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: f4caa4e1-e414-4b21-8822-31c08064c059
ms.collection:
- M365-security-compliance
description: En este artículo se proporciona información para solucionar problemas destinada a los remitentes que están teniendo problemas al intentar enviar correo electrónico a bandejas de entrada de Office 365 y prácticas recomendadas para el envío de correo masivo a clientes de Office 365.
ms.openlocfilehash: 9f4b5e8073c173da6638c30ccc5f123dc3b7a2a6
ms.sourcegitcommit: 32ecff689ae32c59a39b7633ca0f36a304e7516e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/09/2019
ms.locfileid: "35600336"
---
# <a name="troubleshooting-mail-sent-to-office-365"></a>Correo de solución de problemas enviado a Office 365

En este artículo se proporciona información para solucionar problemas destinada a los remitentes que están teniendo problemas al intentar enviar correo electrónico a bandejas de entrada de Office 365 y prácticas recomendadas para el envío de correo masivo a clientes de Office 365.
  
## <a name="troubleshooting-common-problems-with-mail-delivery-to-office-365"></a>Solución de problemas comunes en la entrega de correo a Office 365

Elija uno de estos problemas habituales.
  
- [¿Está administrando la reputación de envío de dominios e IP?](troubleshooting-mail-sent-to-office-365.md#ManageRep)
    
- [¿Está enviando correo electrónico desde direcciones IP nuevas?](troubleshooting-mail-sent-to-office-365.md#NewIPs)
    
- [Confirme que su DNS está configurado correctamente](troubleshooting-mail-sent-to-office-365.md#ConfirmDNSsetup)
    
- [Asegúrese de que usted no se anuncia como una dirección IP no enrutable](troubleshooting-mail-sent-to-office-365.md#NoReverseDNS)
    
- [Ha recibido un informe de no entrega (NDR) al enviar un correo electrónico a un usuario en Office 365](troubleshooting-mail-sent-to-office-365.md#NDRInbound)
    
- [Mi correo electrónico fue a parar a la carpeta de correo electrónico no deseado del destinatario en EOP](troubleshooting-mail-sent-to-office-365.md#JunkMailBox)
    
- [El tráfico de mi dirección IP está limitado por EOP](troubleshooting-mail-sent-to-office-365.md#AllowEOPIPs)
    
### <a name="are-you-managing-your-ip-and-domains-sending-reputation"></a>¿Está administrando la reputación de envío de dominios e IP?
<a name="ManageRep"> </a>

Las tecnologías de filtrado de EOP están diseñadas para ofrecer protecciones contra correo no deseado para Microsoft Office 365, así como otros productos de Microsoft como Exchange Server, Microsoft Office Outlook y Windows Live Mail. También aprovechamos SPF, DKIM y DMARC; tecnologías de autenticación de correo electrónico que ayudan a solucionar el problema de la suplantación de identidad y phishing al comprobar que el dominio que envía el correo electrónico está autorizado a hacerlo. El filtrado de EOP se ve influenciado por una serie de factores relacionados con la IP de envío, dominio, autenticación, precisión de lista, tasas de denuncia, contenido, etc. De estos factores, uno de los que más empeora la reputación del remitente y su capacidad para entregar correo electrónico es su tasa de denuncia de correo electrónico no deseado. 
  
### <a name="are-you-sending-email-from-new-ip-addresses"></a>¿Está enviando correo electrónico desde direcciones IP nuevas?
<a name="NewIPs"> </a>

Las direcciones IP que no se hayan usado previamente para enviar correo electrónico por lo general no tienen ninguna reputación en nuestros sistemas. Como resultado, los correos electrónicos de IP nuevas es más probable que experimenten problemas de entrega. Una vez que la dirección IP tiene una reputación en la que no figura el envío de correo electrónico no deseado, EOP suele permitir un mejor proceso de entrega satisfactoria de correo electrónico.
  
Las IP nuevas que se agregan a dominios que están autenticados en los registros de SPF existentes suelen disfrutar del beneficio añadido de heredar parte de la reputación del remitente del dominio. Si su dominio tiene una buena reputación de envío, las nuevas IP puede que disfruten de un tiempo más rápido de impulso. Normalmente una nueva IP se impulsa completamente en un par de semanas o antes según el volumen, la exactitud de la lista y las tasas de denuncia de correo electrónico no deseado.
  
### <a name="confirm-that-your-dns-is-set-up-correctly"></a>Confirme que su DNS está configurado correctamente
<a name="ConfirmDNSsetup"> </a>

Para obtener instrucciones acerca de cómo crear y mantener registros DNS, incluido el registro MX necesario para enrutar el correo, debe ponerse en contacto con su proveedor de hospedaje de DNS.
  
### <a name="ensure-that-you-do-not-advertise-yourself-as-a-non-routable-ip"></a>Asegúrese de que usted no se anuncia como una dirección IP no enrutable
<a name="NoReverseDNS"> </a>

No podemos aceptar correo electrónico de los remitentes que no logran una búsqueda de DNS inverso. En algunos casos, los remitentes legítimos se anuncian incorrectamente como IP no enrutable de Internet cuando se intenta abrir una conexión a EOP. Las direcciones IP reservadas para una red privada (no enrutable) incluyen:
  
- 192.168.0.0/16 (o 192.168.0.0 - 192.168.255.255)
    
- 10.0.0.0/8 (o 10.0.0.0 - 10.255.255.255)
    
- 172.16.0.0/11 (o 172.16.0.0 - 172.31.255.255)
    
### <a name="you-received-a-non-delivery-report-ndr-when-sending-email-to-a-user-in-office-365"></a>Ha recibido un informe de no entrega (NDR) al enviar un correo electrónico a un usuario en Office 365
<a name="NDRInbound"> </a>

Algunos problemas de entrega se deben a que Microsoft ha bloqueado la dirección IP del remitente o a que la cuenta de usuario se identifica como remitente prohibido debido a una actividad precedente de correo no deseado. Si cree que ha recibido el NDR por error, en primer lugar, siga las instrucciones del mensaje de NDR para resolver el problema. 
  
Para obtener más información acerca del error recibido, vea la lista completa de códigos de error de SMTP en [DSNs and NDRs in On-Premises Exchange 2013 and Office 365](http://technet.microsoft.com/library/8e91de84-76fa-49b2-898c-c5eface76560.aspx).
  
 Por ejemplo, si recibe el NDR siguiente, indica que Microsoft ha bloqueado la dirección IP del remitente. 
  
 `550 5.7.606-649 Access denied, banned sending IP [x.x.x.x]; To request removal from this list please visit https://sender.office.com/ and follow the directions.`
  
Para solicitar ser eliminado de esta lista, puede [Usar el portal de eliminación de la lista para quitarse de la lista de remitentes bloqueados de Office 365](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md).
  
### <a name="my-email-landed-in-the-recipients-junk-folder-in-eop"></a>Mi correo electrónico fue a parar a la carpeta de correo electrónico no deseado del destinatario en EOP
<a name="JunkMailBox"> </a>

Si EOP identificó incorrectamente un mensaje como correo no deseado, puede hablar con el destinatario para enviar este mensaje falso positivo al equipo de análisis de correo no deseado de Microsoft, que lo evaluará y analizará. Según los resultados del análisis, se podrían ajustar las reglas de filtro de contenido de correo no deseado de todo el sistema a fin de permitir que pase el mensaje. Usa el correo electrónico para enviar mensajes a Microsoft que no deberían clasificarse como correo no deseado. Al hacerlo, asegúrese de seguir los pasos descritos en el procedimiento siguiente.
  
### <a name="to-use-email-to-submit-false-positive-messages-to-the-microsoft-spam-analysis-team"></a>Usar el correo electrónico para enviar mensajes de falso positivo al equipo de análisis de correo electrónico no deseado de Microsoft

1. Guarde como seguro el mensaje que quiere enviar.
    
2. Cree un nuevo mensaje en blanco y adjunte el mensaje seguro.
    
    Puede adjuntar varios mensajes de correo seguro si es necesario.
    
3. Copie y pegue la línea de asunto del mensaje original en la línea de asunto del mensaje nuevo.
    
    > [!IMPORTANT]
    > Deje el cuerpo del nuevo mensaje en blanco. 
  
4. Envíe el nuevo mensaje a [not_junk@office365.microsoft.com](mailto:not_junk@office365.microsoft.com).
    
### <a name="traffic-from-my-ip-address-is-throttled-by-eop"></a>El tráfico de mi dirección IP está limitado por EOP
<a name="AllowEOPIPs"> </a>

Si recibe un NDR de EOP que indica que EOP está limitando su dirección IP, por ejemplo:
  
 `host xxxx.outlook.com [x.x.x.x]: 451 4.7.550 Access denied, please try again later`
  
Ha recibido el NDR porque se ha detectado actividad sospechosa procedente de la dirección IP en cuestión y se ha restringido temporalmente mientras se analiza el caso en profundidad. Si después del análisis, la dirección deja de ser sospechosa, la restricción se levantará en breve.
  
### <a name="i-cant-receive-email-from-senders-in-office-365"></a>No puedo recibir correo electrónico de remitentes de Office 365
<a name="AllowEOPIPs"> </a>

 Para recibir mensajes de nuestros usuarios, asegúrese de que la red permite conexiones desde las direcciones IP que EOP usa en nuestros centros de datos. Para obtener más información, consulte [Exchange Online Protection IP addresses](eop/exchange-online-protection-ip-addresses.md). 
  
## <a name="best-practices-for-bulk-emailing-to-office-365-users"></a>Prácticas recomendadas para enviar correo electrónico masivo a usuarios de Office 365
<a name="BulkMailer"> </a>

Si suele llevar a cabo campañas de correo electrónico masivo a usuarios de Office 365 y quiere asegurarse de que los mensajes llegan de manera oportuna y segura, siga las sugerencias de esta sección.
  
### <a name="ensure-that-the-from-name-reflects-who-is-sending-the-message"></a>Asegúrese de que el nombre del campo De: refleja quién envía el mensaje

El Asunto debe ser un breve resumen del contenido del mensaje y el cuerpo del mensaje debe indicar clara y sucintamente de qué trata la oferta, servicio o producto. Por ejemplo:
  
Correcto
  
 ` From: marketing@shoppershandbag.com `
  
 `Subject: Updated catalog for the Christmas season!`
  
Incorrecto
  
 `From: someone@outlook.com`
  
 `Subject: Catalogs`
  
Cuanto más fácil sea que las personas sepan quién es usted y lo que hace, menos problemas tendrá para entregar correctamente sus mensajes a través de la mayoría de los filtros de correo electrónico no deseado.
  
### <a name="always-include-an-unsubscribe-option-in-campaign-emails"></a>Incluir siempre una opción de cancelación de suscripción en mensajes de correo electrónico de campaña

Los correos electrónicos de marketing, especialmente los boletines, siempre deben incluir una manera de cancelar la suscripción de futuros correos. Por ejemplo:
  
 `This email was sent to example@contoso.com by sender@fabrikam.com.`
  
 `Update Profile/Email Address | Instant removal with SafeUnsubscribe™ | Privacy Policy`
  
Algunos remitentes incluyen esta opción requiriendo a los destinatarios enviar un correo electrónico a un alias determinado con "Cancelar suscripción" en el asunto. Es preferible decantarse por el ejemplo de un solo clic anterior. Si decide que los destinatarios tengan que enviar un correo, asegúrese de que cuando hagan clic en el vínculo, todos los campos obligatorios estén cumplimentados previamente.
  
### <a name="use-the-double-opt-in-option-for-marketing-email-or-newsletter-registration"></a>Use la opción de doble verificación para registros de correo electrónico de marketing o boletines

Se aconseja optar por esta práctica recomendada si su empresa requiere o anima a los usuarios a registrar su información de contacto para poder acceder a sus productos o servicios. Algunas empresas siguen la práctica de suscribir automáticamente a sus usuarios a mensajes de correo electrónico de marketing o boletines durante el proceso de registro, pero esto se considera un procedimiento cuestionable de marketing en el mundo del filtrado del correo electrónico.
  
Durante el proceso de registro, si la casilla de verificación "Sí, por favor, envíame el boletín" o "Sí, envíenme ofertas especiales" está seleccionada por defecto, los usuarios que no presten atención pueden suscribirse involuntariamente a correo electrónico de marketing o boletines de noticias que no quieren recibir.
  
 Se recomienda en su lugar la opción de doble verificación, lo que significa que la casilla de verificación no está seleccionada de forma predeterminada para correos electrónicos de marketing o boletines. Además, una vez que se ha enviado el formulario de registro, se envía al usuario un correo electrónico de verificación con una dirección URL que le permite confirmar su decisión de recibir correos electrónicos de marketing. 
  
 Esto ayuda a garantizar que solo aquellos usuarios que quieren recibir correo electrónico de marketing se registraron para mensajes de correo electrónico, lo que libera a la empresa de envío de ser acusada de hacer uso de cualquier práctica de marketing de correo electrónico cuestionable. 
  
### <a name="ensure-that-email-message-content-is-transparent-and-traceable"></a>Asegúrese de que el contenido del mensaje de correo electrónico sea transparente y rastreable.

Igual de importante que la forma en que se envían los mensajes de correo electrónico es su contenido. Al crear contenido de correo electrónico, siga las siguientes prácticas recomendadas para asegurarse de que los servicios de filtrado del correo electrónico no marcarán sus correos electrónicos:
  
- Cuando el mensaje de correo requiera que los destinatarios agreguen al remitente a la libreta de direcciones, debe especificarse claramente que dicha acción no es una garantía de entrega.
    
- Los redireccionamientos que se incluyen en el cuerpo del mensaje deben ser similares y coherentes, y no múltiples ni variados. Un redireccionamiento en este contexto es cualquier cosa que apunta fuera del mensaje, como vínculos y documentos. Si tiene mucha publicidad o vínculos de cancelación de suscripción o de actualización de perfiles, todo debe apuntar al mismo dominio. Por ejemplo:
    
    Correcto
    
     `unsubscribe.bulkmailer.com`
    
     `profile.bulkmailer.com`
    
     `options.bulkmailer.com`
    
    Incorrecto
    
     `unsubscribe.bulkmailer.com`
    
     `profiles.excite.com`
    
     `options.yahoo.com`
    
- Evite contenidos con imágenes o datos adjuntos pesados, o mensajes que estén únicamente compuestos por una imagen.
    
- Su configuración de P3P o de privacidad pública debe especificar claramente la presencia de píxeles de seguimiento (errores o señalizaciones web).
    
### <a name="remove-incorrect-email-aliases-from-your-databases"></a>Quitar alias de correo electrónico incorrectos de sus bases de datos

Los alias de correo electrónico de la base de datos que generan devoluciones son innecesarios y exponen a sus correos electrónicos salientes al riesgo de ser objeto de un mayor escrutinio por parte de los servicios de filtrado del correo electrónico. Asegúrese de que la base de datos de su correo electrónico está actualizada.
  

