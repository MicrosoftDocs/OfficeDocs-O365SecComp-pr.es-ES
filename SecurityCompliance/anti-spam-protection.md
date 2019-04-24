---
title: Protección contra spam para el correo electrónico de Office 365
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 6/29/2018
ms.audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 6a601501-a6a8-4559-b2e7-56b59c96a586
ms.collection:
- M365-security-compliance
description: Obtenga información sobre la configuración y los filtros contra correo no deseado que le ayudarán a evitar el correo no deseado en Exchange Online y Office 365. ¿Obtengo mucho correo no deseado en Office 365? Puede personalizar los filtros de correo no deseado y la configuración de la Directiva contra correo no deseado.
ms.openlocfilehash: 253ef10ac98b10377252a7a43fa306dd5a0ea90a
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32242518"
---
# <a name="office-365-email-anti-spam-protection"></a>Protección contra spam para el correo electrónico de Office 365

¿Le preocupan recibir demasiado correo no deseado en Office 365? Hemos creado varios filtros de correo no deseado en el servicio de Office 365 o Exchange Online Protection (EOP), por lo que el correo electrónico está protegido desde el momento en que recibe el primer mensaje. Para ayudar a evitar el correo no deseado en Office 365, es posible que quiera cambiar una configuración de protección para tratar con un problema específico de su organización (por ejemplo, que reciba un gran número de mensajes de correo no deseado de un remitente en particular, por ejemplo) o que simplemente ajuste la configuración para que esté adaptado para satisfacer mejor las necesidades de su organización. Para ello, puede cambiar la configuración contra correo no deseado en el centro de seguridad &amp; y cumplimiento de Office 365.
  
Este artículo está destinado a los administradores de Office 365. Si no es administrador, pero es un usuario de Office 365 y desea saber cómo tratar con el correo no deseado que recibe, este no es el artículo que está buscando. En su lugar, si usa Outlook para PC o Outlook para Mac, empiece con [información general del filtro de correo electrónico no deseado](https://support.office.com/article/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089). Si usa Outlook en la web, empiece con [información sobre correo electrónico no deseado y](https://support.office.com/article/86c1d76f-4d5a-4967-9647-35665dc17c31)suplantación de identidad.
  
## <a name="these-options-help-you-prevent-spam-in-office-365"></a>Estas opciones ayudan a evitar el correo no deseado en Office 365

 **Filtrado de conexiones**: al usar el filtrado de la conexión, Office 365 comprueba la reputación del remitente antes de permitir que pase un mensaje. Puede crear una lista de permitidos o una lista de remitentes seguros para asegurarse de que recibe todos los mensajes que se le envíen desde una dirección IP específica o un intervalo de direcciones IP. También puede crear una lista de direcciones IP desde las que se van a bloquear los mensajes, denominados lista de bloqueados. Para obtener más información, vea [Configure the Connection Filter Policy](https://technet.microsoft.com/library/jj200718%28v=exchg.150%29.aspx). Si le preocupa el correo no deseado en Office 365, use el filtrado de conexiones para ayudar a evitar el correo no deseado.
  
Para los clientes que tienen Office 365 Enterprise E5 o han adquirido licencias de protección contra amenazas avanzada (ATP), la inteligencia de identidad utiliza el filtrado de conexiones para crear listas de permitidos y bloqueados de remitentes que suplantan el dominio. Para obtener más información, vea más información [sobre la inteligencia de](https://go.microsoft.com/fwlink/?LinkID=735009)suplantación de identidad.
  
 **Filtrado de correo no deseado**: Office 365 comprueba si hay características de mensajes coherentes con el correo no deseado mediante el filtrado de correo no deseado. Puede cambiar las acciones que se deben realizar en los mensajes identificados como correo no deseado y elegir si desea filtrar los mensajes escritos en idiomas específicos o enviados desde países o regiones específicos. También puede activar las opciones avanzadas de filtrado de correo no deseado si desea seguir un enfoque agresivo del filtrado de correo no deseado. Además, puede configurar notificaciones de correo no deseado para el usuario final para informar a los usuarios de que los mensajes dirigidos a ellos se han enviado a la cuarentena en su lugar. (El envío de mensajes a la cuarentena es una de las acciones configurables). A partir de estas notificaciones, los usuarios finales pueden liberar falsos positivos y notificarlos a Microsoft para su análisis. Para obtener más información, vea [Configurar las directivas de filtro de correo no deseado](https://go.microsoft.com/fwlink/p/?LinkId=617147). Para ayudar a evitar el correo no deseado en Office 365, use el filtrado de correo no deseado, si le preocupa que haya demasiado correo no deseado en Office 365, use el filtrado de conexiones para ayudar a evitar el correo no deseado.
  
> [!NOTE]
> Para clientes independientes de EOP: de manera predeterminada, los filtros de correo no deseado de EOP envían mensajes detectados como correo no deseado a la carpeta de correo no deseado de cada destinatario. Sin embargo, para asegurarse de que la acción **mover el mensaje a la carpeta correo no deseado** funcionará con los buzones locales, debe configurar dos reglas de flujo de correo de Exchange (también conocidas como reglas de transporte) en los servidores locales para detectar los encabezados de correo no deseado agregados por EOP. Para más información, consulte [Asegurarse de que el correo no deseado se enruta a la carpeta de correo no deseado de cada usuario](https://technet.microsoft.com/library/jj837173%28v=exchg.150%29.aspx). 
  
## <a name="extra-information-if-you-receive-too-much-spam-in-office-365"></a>Información adicional si recibe demasiado correo no deseado en Office 365

En el siguiente vídeo se proporciona información general sobre cómo configurar el filtrado de correo no deseado en EOP.
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/608be94c-d763-4c47-af94-99e7cb277713?autoplay=false]
  
Para obtener más información, consulte el tema [Configure Spam Filter Policies](https://go.microsoft.com/fwlink/p/?LinkId=617147) .
  
## <a name="check-your-outgoing-messages-to-prevent-spam-in-office-365"></a>Comprobar los mensajes salientes para evitar el correo no deseado en Office 365

 **Filtrado de salida**: Office 365 también se asegura de que los usuarios no envíen correo no deseado. Por ejemplo, es posible que el equipo de un usuario se infecte con malware que provoque el envío de mensajes de correo no deseado, por lo que creamos protección frente a esto con el nombre de *filtrado de salida*. No puede desactivar el filtrado de salida, pero puede configurar las opciones descritas en [configurar la Directiva de correo no deseado saliente](https://technet.microsoft.com/library/jj200737%28v=exchg.150%29.aspx). Si le preocupa demasiado correo no deseado en Office 365, use el filtrado de salida para ayudar a evitar el correo no deseado en Exchange Online.
  
## <a name="beyond-the-basics-more-ways-to-prevent-spam-in-office-365"></a>Más allá de los conceptos básicos: más formas de evitar el correo no deseado en Office 365

 **Reglas de flujo de correo**: Si quiere ir más allá del filtrado de correo no deseado integrado y crear reglas personalizadas basadas en las directivas empresariales, _[las reglas de flujo de correo](https://technet.microsoft.com/library/jj919238%28v=exchg.150%29.aspx)_ (también denominadas reglas de _transporte_) son otro filtro que le ayuda a evitar el correo no deseado en Office 365. Por ejemplo, puede usar reglas de flujo de correo para establecer el valor de nivel de confianza contra correo no deseado (SCL) para los mensajes que coinciden con condiciones específicas, como se describe en [usar reglas de flujo de correo para establecer el nivel de confianza contra correo no deseado (SCL) en los mensajes](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md).
  
 **Autenticación de correo electrónico**: las técnicas que usan el sistema de nombres de dominio (DNS) para agregar información comprobable a los mensajes de correo electrónico acerca del remitente de un mensaje de correo electrónico se denominan autenticación de correo electrónico. Los administradores más avanzados de Office 365 pueden usar estos métodos de autenticación de correo electrónico:
  
- **Marco de directivas de remitente (SPF)**: SPF valida el origen de los mensajes de correo electrónico mediante la comprobación de la dirección IP del remitente frente al propietario presunta del dominio remitente. Para ver una introducción rápida a SPF y configurarlo rápidamente, consulte [Set up SPF in Office 365 to help prevent spoofing](https://technet.microsoft.com/library/dn789058%28v=exchg.150%29.aspx). Para comprender en detalle cómo Office 365 usa SPF, o para la solución de problemas o las implementaciones no estándar (por ejemplo, implementaciones híbridas), comience con [How Office 365 uses Sender Policy Framework (SPF) to prevent spoofing](https://technet.microsoft.com/library/mt712724%28v=exchg.150%29.aspx).

- **DomainKeys Identified Mail (DKIM)**: DKIM le permite adjuntar una firma digital a los mensajes de correo electrónico en el encabezado del mensaje de los correos electrónicos que envía. Los sistemas de correo electrónico que reciben correo electrónico de su dominio usan esta firma digital para determinar si el correo electrónico entrante que reciben es legítimo. Para obtener información sobre DKIM y Office 365, vea [usar DKIM para validar el correo electrónico saliente enviado desde su dominio en Office 365](https://technet.microsoft.com/library/mt695945%28v=exchg.150%29.aspx).

- **Autenticación de mensajes basada en dominio, informes y cumplimiento (dMarc)**: dMarc ayuda a los sistemas de correo a determinar qué hacer con los mensajes que no superen las comprobaCIONES de SPF o DKIM y proporciona otro nivel de confianza para los asociados de correo electrónico. Para obtener información sobre cómo configurar DMARC, vea [usar dMarc para validar el correo electrónico en Office 365](https://technet.microsoft.com/library/mt734386%28v=exchg.150%29.aspx).

Si está preocupado por el correo no deseado, la suplantación de identidad (phishing) y la suplantación de identidad en Office 365, use SPF, DKIM y DMARC conjuntamente para evitar el correo no deseado y la suplantación de identidad.
  
 **Configuración administrada por el usuario final**: Si está buscando información sobre cómo los usuarios finales pueden administrar su propia configuración de correo no deseado, consulte [información general sobre el filtro de correo no deseado](https://go.microsoft.com/fwlink/?LinkId=270065) (para usuarios de Microsoft Outlook) o [información sobre el correo no deseado y el phishing](https://go.microsoft.com/fwlink/?LinkId=270068) (para Usuarios de Outlook en la web). Si está usando EOP para proteger los buzones locales, asegúrese de usar la sincronización de directorios para asegurarse de que esta configuración se sincronice con el servicio. Para más información sobre cómo configurar la sincronización de directorios, vea "Usar la sincronización de directorios para administrar usuarios de correo" en [Administrar usuarios de correo en EOP](https://technet.microsoft.com/library/dn636911%28v=exchg.150%29.aspx).
  
## <a name="for-more-information"></a>Más información

[Blog: ¿por qué recibe correo no deseado y suplantación de identidad en Office 365?](https://go.microsoft.com/fwlink/?LinkId=528179 )
  
[Preguntas más frecuentes sobre protección contra correo electrónico no deseado](https://technet.microsoft.com/library/jj937231%28v=exchg.150%29.aspx)
  
[Impedir falsos positivos de correo electrónico marcado como correo no deseado con una lista segura u otras técnicas](prevent-email-from-being-marked-as-spam-0.md)
  
[Cómo configurar el filtrado de correo no deseado de Office 365 para ayudar a bloquear los mensajes de correo no deseado](reduce-spam-email.md)
  
[¿Cuál es la diferencia entre correo electrónico no deseado y correo electrónico masivo?](https://technet.microsoft.com/library/dn720441%28v=exchg.150%29.aspx)
  
[Encabezados de mensajes de correo no deseado](https://technet.microsoft.com/library/dn205071%28v=exchg.150%29.aspx)
  
[Mensajes de reenvío masivo y EOP](https://technet.microsoft.com/library/dn499795%28v=exchg.150%29.aspx)

## <a name="more-resources"></a>Más recursos

[Obtén ayuda en los foros de la comunidad de Office 365](https://go.microsoft.com/fwlink/p/?LinkId=518605)
  
[Administradores: iniciar sesión y crear una solicitud de servicio](https://go.microsoft.com/fwlink/p/?LinkId=519124)
  
[Administradores: llamar al soporte técnico](https://go.microsoft.com/fwlink/p/?LinkID=518322)
