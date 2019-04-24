---
title: Configurar la directiva de correo no deseado saliente
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 11/10/2016
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a44764e9-a5d2-4c67-8888-e7fb871c17c7
ms.collection:
- M365-security-compliance
description: El filtrado de correo no deseado saliente siempre está habilitado si utiliza el servicio para enviar correo electrónico saliente, lo que protege a las organizaciones que utilizan el servicio y sus destinatarios.
ms.openlocfilehash: af48962879dd4ee1e5bbbe832f221e88900faa75
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32258417"
---
# <a name="configure-the-outbound-spam-policy"></a>Configurar la directiva de correo no deseado saliente

El filtrado de correo no deseado saliente siempre está habilitado si utiliza el servicio para enviar correo electrónico saliente, lo que protege a las organizaciones que utilizan el servicio y sus destinatarios. De manera similar al filtrado entrante, el filtrado de correo no deseado saliente está compuesto por el filtro de conexión y el filtro de contenido; no obstante, no es posible configurar el filtrado saliente. Si se determina que un mensaje saliente es correo no deseado, este se enruta mediante el grupo de entrega de mayor riesgo, que reduce la probabilidad de que el grupo de IP saliente normal se agregue a una lista de bloqueo. Si un cliente continúa enviando correo no deseado saliente mediante el servicio, su envío de mensajes se bloqueará. Si bien no es posible deshabilitar ni modificar el filtrado de correo no deseado saliente, puede configurar varias opciones de correo no deseado en toda la empresa mediante la directiva de correo no deseado saliente predeterminada. 
  
En el siguiente vídeo se muestra cómo se configura la directiva de correo no deseado saliente:
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/1f20d655-0d3d-4141-9cae-e57f5a6cffe8?autoplay=false]
  
## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de comenzar?
<a name="sectionSection0"> </a>

Tiempo estimado para finalizar: 5 minutos
  
Deberá tener asignados permisos antes de poder llevar a cabo este procedimiento o procedimientos. Para ver qué permisos necesita, consulte el tema "entrada contra correo electrónico no deseado" en el tema [permisos de características de Exchange Online](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx) . 
  
Para obtener información acerca de los métodos abreviados de teclado aplicables a los procedimientos de este tema, consulte **Keyboard shortcuts in Exchange 2013**.
  
El siguiente procedimiento también se puede llevar a cabo mediante PowerShell remoto. Use el cmdlet [Get-HostedOutboundSpamFilterPolicy](http://technet.microsoft.com/library/8f15c83c-c10a-4d9d-b135-35321430bdc2.aspx) para revisar su configuración y [Set-HostedOutboundSpamFilterPolicy](http://technet.microsoft.com/library/665d1b04-d4b5-4a0e-811a-4e37096ccbfd.aspx) para editar su configuración de directiva de correo no deseado saliente. Para obtener información sobre cómo usar Windows PowerShell para conectarse a Exchange Online Protection, vea [conectarse a PowerShell de Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkid=627290). Para obtener información sobre cómo usar Windows PowerShell para conectarse a Exchange Online, vea [Conexión a Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).
  
## <a name="use-the-eac-to-edit-the-default-outbound-spam-policy"></a>Usar el EAC para editar la directiva predeterminada de correo no deseado saliente
<a name="sectionSection1"> </a>

Utilice el siguiente procedimiento para editar la directiva predeterminada del correo no deseado saliente:
  
### <a name="to-configure-the-default-outbound-spam-policy"></a>Para configurar la directiva de correo no deseado saliente predeterminada

1. En el Centro de administración de Exchange (EAC), vaya a **Protección** \> **Correo no deseado** y, luego, haga doble clic en la directiva predeterminada.
    
2. Seleccione la opción de menú **Preferencias de correo no deseado de salida**. 
    
3. Seleccione las siguientes casillas relativas a los mensajes salientes y después, especifique una o varias direcciones de correo electrónico asociadas en el cuadro de entrada asociado (pueden ser listas de distribución si se resuelven como destinatarios SMTP válidos):
    
1. **Enviar una copa de todos los mensajes de correo electrónico saliente sospechosos a las siguientes direcciones de correo electrónico**. Estos mensajes son los marcados como correo no deseado por el filtro (independientemente de la clasificación de SCL). El filtro no los rechaza y son enviados al grupo de envío de mayor riesgo. Separar varias direcciones con un punto y coma. Tenga en cuenta que los destinatarios especificados recibirán los mensajes como una dirección con copia oculta (CCC) (los campos De y Para son el remitente y el destinatario originales).
    
2. **Envía una notificación a la siguiente dirección de correo electrónico cuando se bloquea un remitente por enviar correo electrónico no deseado**. Separar varias direcciones con un punto y coma.
    
    Cuando una cantidad significativa de correo no deseado proviene de un usuario en particular, el usuario se deshabilita para que no pueda enviar mensajes de correo electrónico. Al administrador del dominio, que se especifica con esta opción de configuración, se le informa de que se han bloqueado los mensajes salientes de este usuario. Para ver el aspecto que tiene esta notificación, véase [Notificación de muestra cuando se bloquea a un remitente para enviar correo no deseado de salida](sample-notification-when-a-sender-is-blocked-sending-outbound-spam.md). Para obtener información sobre cómo volver a habilitar a un usuario, consulte [Removing a user, domain, or IP address from a block list after sending spam email](http://technet.microsoft.com/library/712cfcc1-31e8-4e51-8561-b64258a8f1e5.aspx).
    
4. Haga clic en **Guardar**. En el panel a la derecha, aparece un resumen de la configuración predeterminada de directiva.
    
## <a name="for-more-information"></a>Más información
<a name="sectionSection2"> </a>

[Grupo de entrega de alto riesgo para mensajes salientes](high-risk-delivery-pool-for-outbound-messages.md)
  
[Preguntas más frecuentes sobre protección contra correo no deseado](anti-spam-protection-faq.md)
  

