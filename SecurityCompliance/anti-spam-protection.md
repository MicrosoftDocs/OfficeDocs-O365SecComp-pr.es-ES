---
title: Protección contra correo no deseado de Office 365 correo electrónico
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 6/29/2018
ms.audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 6a601501-a6a8-4559-b2e7-56b59c96a586
description: Obtenga información acerca de la configuración contra correo no deseado y los filtros que le ayudarán a que evitar correo no deseado en Exchange Online y Office 365. ¿Introducción demasiado spam en Office 365? Puede personalizar los filtros de spam y la configuración de la directiva contra correo no deseado.
ms.openlocfilehash: 0a23ddd0610599bbd6478781c61e5e32b06726bc
ms.sourcegitcommit: 7e2a0185cadea7f3a6afc5ddc445eac2e1ce22eb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/11/2019
ms.locfileid: "29652275"
---
# <a name="office-365-email-anti-spam-protection"></a>Protección contra correo no deseado de Office 365

¿Le preocupa la gran cantidad de spam en Office 365? Hemos incorporado varios filtros de spam en el servicio Office 365 o Exchange Online Protection (EOP), por lo que su correo electrónico está protegido desde el momento en que recibe su primer mensaje. Con el fin de ayudar a evitar el correo no deseado en Office 365, es posible que desee cambiar una configuración de protección para abordar los problemas con un problema específico en su organización: diga que está recibiendo una gran cantidad de correo no deseado de un remitente determinado, por ejemplo, o para simplemente no pasa nada, ajustar la configuración de modo que estén diseñadas para satisfacer mejor las necesidades de su organización. Para ello, puede cambiar la configuración de correo no deseada en la seguridad de Office 365 &amp; centro de cumplimiento.
  
Este artículo está pensado para administradores de Office 365. Si usted no es administrador, pero es un usuario de Office 365 y desea información sobre cómo abordar los problemas con spam que recibirá, esto no es el artículo que está buscando. En su lugar, si usa Outlook para PC o Outlook para Mac, empiece con [información general sobre el filtro de correo electrónico no deseado](https://support.office.com/article/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089). Si usa Outlook en la web, empiece con [temas sobre correo no deseado y suplantación de identidad](https://support.office.com/article/86c1d76f-4d5a-4967-9647-35665dc17c31).
  
## <a name="these-options-help-you-prevent-spam-in-office-365"></a>Estas opciones le ayudarán a evitar que el correo no deseado en Office 365

 **Filtrado de la conexión.** Cuando se utiliza el filtrado de la conexión, Office 365 comprueba la reputación del remitente antes de permitir que un mensaje obtener a través de. Puede crear una lista de remitentes seguros, para asegurarse de que recibirá cada mensaje enviado desde una dirección IP específica o un intervalo de direcciones IP o lista Permitir. También puede crear una lista de direcciones IP desde la que se va a bloquear mensajes, denominados una lista de bloqueo. Para obtener más información, vea [Configurar la directiva de filtro de conexión](https://technet.microsoft.com/library/jj200718%28v=exchg.150%29.aspx). Si le preocupa el correo no deseado en Office 365, use el filtrado de conexiones para ayudar a evitar correo no deseado.
  
Para los clientes que tienen Office 365 Enterprise E5 o han adquirido licencias de protección avanzada de amenaza (ATP), filtrado de conexiones se usa inteligencia simulado para crear listas de remitentes que son de su dominio suplantación permitir o bloquear. Para obtener más información, vea [más información acerca de la inteligencia de suplantación](https://go.microsoft.com/fwlink/?LinkID=735009).
  
 **Filtrado de Spam.** Office 365 comprueba si hay características coherentes con spam de los mensajes mediante el uso de filtrado de spam. Puede cambiar qué acciones para realizar en los mensajes identificados como correo no deseado y elija si desea filtrar mensajes escritos en idiomas concretos, o enviados desde ciertos países o regiones. También puede activar avanzadas correo no deseado filtrado opciones si desea seguir un enfoque agresivo para el filtrado de correo no deseado. Además, puede configurar las notificaciones de spam para el usuario final para informar a los usuarios cuando los mensajes destinados a ellos se han enviado a la cuarentena en su lugar. (Envío de mensajes a la cuarentena es una de las acciones configurables.) Desde estas notificaciones, los usuarios finales pueden liberar falsos positivos y notificar a Microsoft para su análisis. Para obtener más información, vea [configurar sus directivas de filtro de correo no deseado](https://go.microsoft.com/fwlink/p/?LinkId=617147). Con el fin de ayudar a evitar que el correo no deseado en Office 365, use spam filtrado, si le preocupa la gran cantidad de spam en Office 365, use el filtrado de conexiones para ayudar a evitar correo no deseado.
  
> [!NOTE]
> Para los clientes de EOP independiente: de forma predeterminada, los filtros de spam de elevación de privilegios envían los mensajes detectados como correo no deseado a la carpeta de correo no deseado de cada de los destinatarios. Sin embargo, con el fin de asegurarse de que la acción de **mover el mensaje a la carpeta correo no deseado** funcionarán con buzones locales, debe configurar dos reglas de transporte de Exchange en los servidores locales para detectar los encabezados de spam agregados por elevación de privilegios. Para obtener información detallada, vea [Asegúrese de que el correo no deseado se enrute a la carpeta de correo no deseado de cada usuario](https://technet.microsoft.com/library/jj837173%28v=exchg.150%29.aspx). 
  
## <a name="extra-information-if-you-receive-too-much-spam-in-office-365"></a>Información adicional si recibe demasiado spam en Office 365

En el siguiente vídeo se proporciona información general de la configuración de filtrado de elevación de privilegios de spam.
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/608be94c-d763-4c47-af94-99e7cb277713?autoplay=false]
  
Para obtener más información, vea el tema [Configure las directivas de filtro de correo no deseado](https://go.microsoft.com/fwlink/p/?LinkId=617147) .
  
## <a name="check-your-outgoing-messages-to-prevent-spam-in-office-365"></a>Comprobar los mensajes salientes para impedir el correo no deseado en Office 365

 **El filtrado de salida.** Office 365 también comprueba para asegurarse de que los usuarios no envíen correo no deseado. Por ejemplo, el equipo de un usuario puede obtener infectado con malware que hace que enviar los mensajes de spam, por lo que creamos protección frente a la que llama *el filtrado de salida* . No se puede desactivar el filtrado de salida, pero se puede establecer la configuración que se describe en [Configurar la directiva de correo no deseado saliente](https://technet.microsoft.com/library/jj200737%28v=exchg.150%29.aspx). Si le preocupa la gran cantidad de spam en Office 365, use el filtrado de salida para ayudar a evitar el correo no deseado en Exchange Online.
  
## <a name="beyond-the-basics-more-ways-to-prevent-spam-in-office-365"></a>Más allá de los conceptos básicos: más formas para evitar que el correo no deseado en Office 365

 **Las reglas de flujo de correo.** Si desea ir más allá de filtrado de correo no deseado integrado y crear reglas personalizadas que se basan en directivas de su empresa, *[reglas de flujo de correo](https://technet.microsoft.com/library/jj919238%28v=exchg.150%29.aspx)*, también denominadas *las reglas de transporte*, son otro filtro que le ayudan a evitar correo no deseado en Office 365. Por ejemplo, puede usar las reglas de flujo de correo para establecer el valor deseado (SCL) nivel de confianza para los mensajes que coinciden con las condiciones específicas, como se describe en [utilizar reglas de flujo de correo para establecer el nivel de confianza de correo no deseado (SCL) en los mensajes](https://technet.microsoft.com/library/dn798345%28v=exchg.150%29.aspx).
  
 **Autenticación de correo electrónico.** Las técnicas que use el sistema de nombres de dominio (DNS) para agregar estipulan a mensajes de correo electrónico acerca del remitente de un mensaje de correo electrónico se denominan autenticación de correo electrónico. Más avanzado pueden hacer que los administradores de Office 365 el uso de estos métodos de autenticación de correo electrónico:
  
- **Marco de directivas de remitente (SPF).** SPF valida el origen de los mensajes de correo electrónico mediante la comprobación de la dirección IP del remitente contra la presunta propietario del dominio envío. Para obtener una introducción rápida a SPF y para obtenerlo configurado rápidamente, vea [Set up SPF en Office 365 para ayudar a evitar la suplantación de identidad](https://technet.microsoft.com/library/dn789058%28v=exchg.150%29.aspx). Para obtener una descripción más detallada de cómo Office 365 usa SPF, o para las implementaciones de solución de problemas o no estándar, como las implementaciones híbridas, empiece con [cómo Office 365 usa el marco de directivas de remitentes (SPF) para evitar la suplantación de identidad](https://technet.microsoft.com/library/mt712724%28v=exchg.150%29.aspx).

- **Por claves de dominio identifican correo (DKIM).** DKIM le permite adjuntar una firma digital a los mensajes de correo electrónico en el encabezado del mensaje de los correos electrónicos enviados. Sistemas de correo electrónico que reciben correo electrónico de su dominio use esta firma digital para determinar si el correo electrónico entrante que reciben es legítimo. Para obtener información acerca de DKIM y Office 365, vea [Uso de DKIM para validar el correo electrónico saliente enviado desde su dominio en Office 365](https://technet.microsoft.com/library/mt695945%28v=exchg.150%29.aspx).

- **Autenticación de mensajes basado en dominio, informes y conformidad (DMARC).** Ayuda de DMARC a recibir sistemas de correo de determinar qué hacer con los mensajes que no cumplen las comprobaciones SPF o DKIM y proporcionan otro nivel de confianza para los socios de correo electrónico. Para obtener información acerca de cómo configurar DMARC, vea [Usar DMARC para validar el correo electrónico en Office 365](https://technet.microsoft.com/library/mt734386%28v=exchg.150%29.aspx).

Si le preocupa de correo no deseado, suplantación de identidad y suplantación de identidad en Office 365, use SPF, DKIM y DMARC conjuntamente para ayudar a impedir el correo no deseado y suplantación de identidad no deseados.
  
 **Para el usuario final la configuración administrado.** Si está buscando información acerca de cómo los usuarios finales pueden administrar su propia configuración de correo no deseado, consulte [información general del filtro de correo electrónico no deseado](https://go.microsoft.com/fwlink/?LinkId=270065) (para los usuarios de Microsoft Outlook) o [Aprenda acerca de correo electrónico no deseado y suplantación de identidad](https://go.microsoft.com/fwlink/?LinkId=270068) (para Outlook en los usuarios de web). Si usa EOP para proteger los buzones locales, asegúrese de usar la sincronización de directorios para asegurarse de que estas opciones se sincronizan con el servicio. Para obtener más información acerca de cómo configurar la sincronización de Active directory, vea "Usar la sincronización de Active directory para administrar usuarios de correo" en [Administrar usuarios de correo en EOP](https://technet.microsoft.com/library/dn636911%28v=exchg.150%29.aspx).
  
## <a name="for-more-information"></a>Más información

[Blog: ¿Por qué correo no deseado y suplantación de identidad obtener a través de Office 365?](https://go.microsoft.com/fwlink/?LinkId=528179 )
  
[Preguntas más frecuentes sobre protección contra correo electrónico no deseado](https://technet.microsoft.com/library/jj937231%28v=exchg.150%29.aspx)
  
[Impedir falsos positivos de correo electrónico marcado como correo no deseado con una lista segura u otras técnicas](prevent-email-from-being-marked-as-spam-0.md)
  
[Cómo configurar el filtrado para ayudar a bloquear los mensajes no deseado de spam de Office 365](block-email-spam-to-prevent-false-negatives.md)
  
[¿Cuál es la diferencia entre correo electrónico no deseado y correo electrónico masivo?](https://technet.microsoft.com/library/dn720441%28v=exchg.150%29.aspx)
  
[Encabezados de mensajes de correo no deseado](https://technet.microsoft.com/library/dn205071%28v=exchg.150%29.aspx)
  
[Contra mensajes y elevación de privilegios](https://technet.microsoft.com/library/dn499795%28v=exchg.150%29.aspx)

## <a name="more-resources"></a>Más recursos

[Obtén ayuda en los foros de la comunidad de Office 365](https://go.microsoft.com/fwlink/p/?LinkId=518605)
  
[Administradores: iniciar sesión y crear una solicitud de servicio](https://go.microsoft.com/fwlink/p/?LinkId=519124)
  
[Administradores: llamar al soporte técnico](https://go.microsoft.com/fwlink/p/?LinkID=518322)
