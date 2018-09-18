---
title: Controlar el correo no deseado saliente en Office 365
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 09/18/2018
ms.audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 6a601501-a6a8-4559-b2e7-56b59c96a586
description: Si la organización envía una gran cantidad de correo masivo que se marca como correo no deseado, que se podría obtener bloqueado de envío de correo electrónico con Office 365. Lea este artículo para obtener más información acerca de por qué esto ocurre y qué puede hacer acerca de él.
ms.openlocfilehash: c5baf12b9b54e46e3863e33172cfb7339227e309
ms.sourcegitcommit: 122646e570bb13e93d4fdc5090bdd25ed65d1997
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/18/2018
ms.locfileid: "23998979"
---
# <a name="controlling-outbound-spam-in-office-365"></a>Controlar el correo no deseado saliente en Office 365

Que se tomen administración de correo no deseado saliente en serio debido a que nuestro es un servicio compartido.  Hay muchos clientes detrás de un grupo compartido de recursos, donde si un cliente envía correo no deseado saliente, que puede afectar negativamente a la reputación de IP saliente del servicio y afecta a la correcta entrega de correo electrónico para otros clientes. Es desleal a un cliente si envía correo basura cliente B y la dirección IP que usa de lista de varias listas de IP parte 3ª bloqueo.

## <a name="what-admins-can-do-to-control-outbound-spam"></a>¿Qué pueden hacer los administradores para controlar el correo no deseado saliente

- **Habilitar las notificaciones cuando una cuenta está enviando spam o apagar**. Los administradores pueden obtener bcc'ed cada vez que un mensaje se marcó como correo no deseado saliente y enviado a través del grupo de alto riesgo. Mediante la supervisión de este buzón de correo, un administrador puede detectar si tienen una cuenta en peligro en su red, o si el filtro de spam por error consiste en marcar su correo electrónico como correo no deseado.  Puede encontrar más información acerca de cómo configurar la directiva de correo no deseado saliente [aquí](configure-the-outbound-spam-policy.md).
 
- **Revisar manualmente quejas spam de 3ª proveedores de correo electrónico**. Muchos servicios de correo electrónico de parte 3ª como Outlook.com, Yahoo y AOL proporcionan un bucle de comentarios donde si cualquier usuario en su servicio de marca un correo electrónico de nuestro servicio como correo no deseado, el mensaje se empaquetan y Enviar atrás para nosotros para su revisión. Para obtener más información sobre la compatibilidad de remitente para Outlook.com, haga clic en [aquí](https://sendersupport.olc.protection.outlook.com/pm/services.aspx).

## <a name="what-eop-does-to-control-outbound-spam"></a>Efecto de elevación de privilegios para controlar el correo no deseado saliente 

1. **Segregación de tráfico saliente en grupos de servidores independientes de IP**. Se examinan todos los mensajes que envían a través del servicio a los clientes como correo no deseado. Si el mensaje es spam, se enruta a través del grupo de entrega de alto riesgo. Este grupo de servidores IP contiene correo no deseado y las notificaciones de estado de no entrega. No se garantiza la entrega al destinatario previsto como otras muchas empresas no aceptará correo electrónico porque la calidad de correo electrónico que emite.</br></br>Dividir el tráfico de este modo se asegura de que el menor calidad de correo electrónico (correo no deseado, contra NDR) no arrastrar hacia abajo la reputación de los grupos de servidores de correo electrónico saliente normal. El grupo de alto riesgo tiene normalmente bajo reputación en muchas receptores alrededor de Internet, aunque esto no es universal. 

2. **Reputación de supervisión de IP**. Office 365 consulta diversos 3ª parte IP las listas de bloqueo y genera alertas si cualquiera de nuestro IP saliente figuran en ellos. Esto nos permite reaccionar rápidamente cuando spam ha provocado nuestra reputación a reducirse considerablemente. Cuando se genera una alerta, tenemos documentación interna remotas cuáles son los pasos a seguir para obtener elimine de la lista. 

3. **Desactivación de cuentas ofensivos cuando envían demasiado correo electrónico marcados como correo no deseado**. Aunque se segregar nuestro correo no deseado y que no sean-correo no deseado en dos grupos de IP salientes independientes, las cuentas de correo electrónico no pueden enviar correo no deseado indefinidamente. Se controlar qué cuentas envían spam y si se excede un límite divulgar, se bloquea la cuenta de envío de spam.</br></br>Un solo mensaje se marca como spam puede ser un misclassification por el motor de spam y también conocido como un falso positivo. Enviarlo a través del grupo de alto riesgo para concederle una posibilidad de que salen; Sin embargo, es indicativo de un problema que se produce un gran número de mensajes en un marco de hora corta, se bloqueará la cuenta de envío de cualquier correo electrónico más. Existen diferentes umbrales que existen para cuentas de correo individuales, así como en agregado para el inquilino todo.

4. **Desactivación de cuentas ofensivos cuando envían demasiado correo electrónico en demasiado corto un marco de tiempo**. Además de los límites por encima de ese aspecto para una proporción de mensajes marcados como correo no deseado, también hay algunos límites que bloquean las cuentas cuando se alcance un límite general, independientemente de si los mensajes se marcan como correo no deseado. La razón de que este límite existe es debido a que una cuenta en peligro podría enviar correo no deseado de día cero que perdidas por el filtro de spam. Debido a que resulta difícil, si no imposible, en ocasiones, indicar la diferencia entre una campaña de correo masivo legítima y una campaña de spam masiva, activan estos límites para limitar los posibles daños.

> [!NOTE]
> Para #3 y 4 #, no se anuncia a los límites exactos.  Esto es para evitar que los remitentes de spam desde el sistema de juegos y para asegurarse de que podemos cambiar los límites cuando es necesario. Los límites son lo suficientemente alto como por ejemplo, que un usuario empresarial promedio nunca llegará a ellos y lo suficientemente baja que contiene la mayoría de los daños que puede hacer un remitente de spam. 

## <a name="recommended-workarounds-for-customers-who-want-to-send-outbound-a-lot-of-email-through-eop"></a>Soluciones recomendadas para los clientes que desean enviar la salida de una gran cantidad de correo electrónico a través de elevación de privilegios

Es difícil mantener un equilibrio entre los clientes que desean enviar un gran volumen de correo electrónico frente a proteger el servicio de cuentas en peligro y emailers de forma masiva con prácticas de adquisición de lista deficiente. Una vez más, el costo de un IP saliente en una lista de bloqueo de parte 3ª de destino es mayor que un cliente de envío de correo electrónico saliente de bloqueo. Tal como se describe en la [Descripción del servicio de Exchange Online](https://technet.microsoft.com/library/exchange-online-limits.aspx#RecipientLimits), uso de elevación de privilegios para enviar correo electrónico masivo no es un uso del servicio y no admitidas sólo se permite en una base de "mejor esfuerzo". Para los clientes que desean enviar correo electrónico masivo, se recomienda lo siguiente:

1. **Enviar el correo electrónico masivo a través de sus propios servidores de correo local**. Esto significa que el cliente tendrá que mantener su propia infraestructura de correo electrónico para este tipo de correo electrónico.

2. **Use un 3 º emailer masiva para enviar la comunicación masiva**. Hay varias emailers de masa parte 3ª cuyo único empresarial es enviar correo electrónico masivo. Puede trabajar con los clientes para asegurarse de que disponen de buenas prácticas de Email y tienen recursos dedicados a aplicarla. 

La mensajería, Mobile, Malware antiintrusión grupo de trabajo (MAAWG) publica su lista de pertenencia [aquí](http://www.maawg.org/about/roster). Varios proveedores de correo electrónico masivo están en la lista y se conocen como los ciudadanos responsables de Internet. 
  
## <a name="for-more-information"></a>Más información

[Notificación de muestra cuando se bloquea a un remitente para enviar correo no deseado de salida](sample-notification-when-a-sender-is-blocked-sending-outbound-spam.md)

[Protección contra correo no deseado de Office 365](anti-spam-protection.md)

[Protección contra suplantación de identidad en Office 365](anti-spoofing-protection.md)

[Niveles de confianza del correo no deseado](spam-confidence-levels.md)
