---
title: Configurar la directiva de correo no deseado saliente
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 11/10/2016
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a44764e9-a5d2-4c67-8888-e7fb871c17c7
description: El filtrado de correo no deseado saliente siempre está habilitado si utiliza el servicio para enviar correo electrónico saliente, lo que protege a las organizaciones que utilizan el servicio y sus destinatarios.
ms.openlocfilehash: b6185cfded28613cb5a512882aefb1a99db158db
ms.sourcegitcommit: e9dca2d6a7838f98bb7eca127fdda2372cda402c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/21/2018
ms.locfileid: "23002430"
---
# <a name="configure-the-outbound-spam-policy"></a><span data-ttu-id="18436-103">Configurar la directiva de correo no deseado saliente</span><span class="sxs-lookup"><span data-stu-id="18436-103">Configure the outbound spam policy</span></span>

<span data-ttu-id="18436-p101">El filtrado de correo no deseado saliente siempre está habilitado si utiliza el servicio para enviar correo electrónico saliente, lo que protege a las organizaciones que utilizan el servicio y sus destinatarios. De manera similar al filtrado entrante, el filtrado de correo no deseado saliente está compuesto por el filtro de conexión y el filtro de contenido; no obstante, no es posible configurar el filtrado saliente. Si se determina que un mensaje saliente es correo no deseado, este se enruta mediante el grupo de entrega de mayor riesgo, que reduce la probabilidad de que el grupo de IP saliente normal se agregue a una lista de bloqueo. Si un cliente continúa enviando correo no deseado saliente mediante el servicio, su envío de mensajes se bloqueará. Si bien no es posible deshabilitar ni modificar el filtrado de correo no deseado saliente, puede configurar varias opciones de correo no deseado en toda la empresa mediante la directiva de correo no deseado saliente predeterminada.</span><span class="sxs-lookup"><span data-stu-id="18436-p101">Outbound spam filtering is always enabled if you use the service for sending outbound email, thereby protecting organizations using the service and their intended recipients. Similar to inbound filtering, outbound spam filtering is comprised of connection filtering and content filtering, however the outbound filter settings are not configurable. If an outbound message is determined to be spam, it is routed through the higher risk delivery pool, which reduces the probability of the normal outbound-IP pool being added to a block list. If a customer continues to send outbound spam through the service, they will be blocked from sending messages. Although outbound spam filtering cannot be disabled or changed, you can configure several company-wide outbound spam settings via the default outbound spam policy.</span></span> 
  
<span data-ttu-id="18436-109">En el siguiente vídeo se muestra cómo se configura la directiva de correo no deseado saliente:</span><span class="sxs-lookup"><span data-stu-id="18436-109">The following video shows how to configure the outbound spam policy:</span></span>
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/1f20d655-0d3d-4141-9cae-e57f5a6cffe8?autoplay=false]
  
## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="18436-110">¿Qué necesita saber antes de comenzar?</span><span class="sxs-lookup"><span data-stu-id="18436-110">What do you need to know before you begin?</span></span>
<span data-ttu-id="18436-111"><a name="sectionSection0"> </a></span><span class="sxs-lookup"><span data-stu-id="18436-111"></span></span>

<span data-ttu-id="18436-112">Tiempo estimado para finalizar: 5 minutos</span><span class="sxs-lookup"><span data-stu-id="18436-112">Estimated time to complete: 5 minutes</span></span>
  
<span data-ttu-id="18436-p102">Debe tener asignados los permisos puede llevar a cabo estos procedimientos. Para ver qué permisos necesita, vea la entrada"contra correo no deseado en el tema [Feature Permissions in Exchange Online](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx) .</span><span class="sxs-lookup"><span data-stu-id="18436-p102">You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Anti-spam entry in the [Feature Permissions in Exchange Online](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx) topic.</span></span> 
  
<span data-ttu-id="18436-115">Para obtener información acerca de los métodos abreviados de teclado aplicables a los procedimientos de este tema, consulte **Métodos abreviados de teclado en el Centro de administración de Exchange**.</span><span class="sxs-lookup"><span data-stu-id="18436-115">For information about keyboard shortcuts that may apply to the procedures in this topic, see **Keyboard shortcuts in the Exchange admin center**.</span></span>
  
<span data-ttu-id="18436-p103">El siguiente procedimiento también se puede realizar mediante PowerShell remoto. Use el cmdlet [Get-HostedOutboundSpamFilterPolicy](http://technet.microsoft.com/library/8f15c83c-c10a-4d9d-b135-35321430bdc2.aspx) para revisar la configuración y el [Conjunto HostedOutboundSpamFilterPolicy](http://technet.microsoft.com/library/665d1b04-d4b5-4a0e-811a-4e37096ccbfd.aspx) para editar la configuración de directiva de correo no deseado saliente. Para obtener información sobre cómo usar Windows PowerShell para conectarse a Exchange Online Protection, vea [Connect to Exchange Online Protection PowerShell](https://go.microsoft.com/fwlink/p/?linkid=627290). Para obtener información sobre cómo usar Windows PowerShell para conectarse a Exchange Online, vea [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span><span class="sxs-lookup"><span data-stu-id="18436-p103">The following procedure can also be performed via remote PowerShell. Use the [Get-HostedOutboundSpamFilterPolicy](http://technet.microsoft.com/library/8f15c83c-c10a-4d9d-b135-35321430bdc2.aspx) cmdlet to review your settings, and the [Set-HostedOutboundSpamFilterPolicy](http://technet.microsoft.com/library/665d1b04-d4b5-4a0e-811a-4e37096ccbfd.aspx) to edit your outbound spam policy settings. To learn how to use Windows PowerShell to connect to Exchange Online Protection, see [Connect to Exchange Online Protection PowerShell](https://go.microsoft.com/fwlink/p/?linkid=627290). To learn how to use Windows PowerShell to connect to Exchange Online, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span></span>
  
## <a name="use-the-eac-to-edit-the-default-outbound-spam-policy"></a><span data-ttu-id="18436-120">Usar el EAC para editar la directiva predeterminada de correo no deseado saliente</span><span class="sxs-lookup"><span data-stu-id="18436-120">Use the EAC to edit the default outbound spam policy</span></span>
<span data-ttu-id="18436-121"><a name="sectionSection1"> </a></span><span class="sxs-lookup"><span data-stu-id="18436-121"></span></span>

<span data-ttu-id="18436-122">Utilice el siguiente procedimiento para editar la directiva predeterminada del correo no deseado saliente:</span><span class="sxs-lookup"><span data-stu-id="18436-122">Use the following procedure to edit the default outbound spam policy:</span></span>
  
### <a name="to-configure-the-default-outbound-spam-policy"></a><span data-ttu-id="18436-123">Para configurar la directiva de correo no deseado saliente predeterminada</span><span class="sxs-lookup"><span data-stu-id="18436-123">To configure the default outbound spam policy</span></span>

1. <span data-ttu-id="18436-124">En el Centro de administración de Exchange (EAC), vaya a **Protección** \> **Correo no deseado** y, luego, haga doble clic en la directiva predeterminada.</span><span class="sxs-lookup"><span data-stu-id="18436-124">In the Exchange admin center (EAC), navigate to **Protection** \> **Outbound spam**, and then double-click the default policy.</span></span>
    
2. <span data-ttu-id="18436-125">Seleccione la opción de menú **Preferencias de correo no deseado de salida**.</span><span class="sxs-lookup"><span data-stu-id="18436-125">Select the **Outbound spam preferences** menu option.</span></span> 
    
3. <span data-ttu-id="18436-126">Seleccione las siguientes casillas relativas a los mensajes salientes y después, especifique una o varias direcciones de correo electrónico asociadas en el cuadro de entrada asociado (pueden ser listas de distribución si se resuelven como destinatarios SMTP válidos):</span><span class="sxs-lookup"><span data-stu-id="18436-126">Select the following check boxes pertaining to outbound messages, and then specify an associated email address or addresses in the accompanying input box (these can be distribution lists if they resolve as valid SMTP destinations):</span></span>
    
1. <span data-ttu-id="18436-p104">**Enviar una copa de todos los mensajes de correo electrónico saliente sospechosos a las siguientes direcciones de correo electrónico**. Estos mensajes son los marcados como correo no deseado por el filtro (independientemente de la clasificación de SCL). El filtro no los rechaza y son enviados al grupo de envío de mayor riesgo. Separar varias direcciones con un punto y coma. Tenga en cuenta que los destinatarios especificados recibirán los mensajes como una dirección con copia oculta (CCC) (los campos De y Para son el remitente y el destinatario originales).</span><span class="sxs-lookup"><span data-stu-id="18436-p104">**Send a copy of all suspicious outbound email messages to the following email address or addresses**. These are messages that are marked as spam by the filter (regardless of the SCL rating). They are not rejected by the filter but are routed through the higher risk delivery pool. Separate multiple addresses with a semicolon. Note that the recipients specified will receive the messages as a Blind carbon copy (Bcc) address (the From and To fields are the original sender and recipient).</span></span>
    
2. <span data-ttu-id="18436-p105">**Envía una notificación a la siguiente dirección de correo electrónico cuando se bloquea un remitente por enviar correo electrónico no deseado**. Separar varias direcciones con un punto y coma.</span><span class="sxs-lookup"><span data-stu-id="18436-p105">**Send a notification to the following email address when a sender is blocked sending outbound spam**. Separate multiple addresses with a semicolon.</span></span>
    
    <span data-ttu-id="18436-p106">Cuando una cantidad significativa de correo no deseado proviene de un usuario en particular, el usuario se deshabilita para que no pueda enviar mensajes de correo electrónico. Al administrador del dominio, que se especifica con esta opción de configuración, se le informa de que se han bloqueado los mensajes salientes de este usuario. Para ver el aspecto que tiene esta notificación, véase [Notificación de muestra cuando se bloquea a un remitente para enviar correo no deseado de salida](sample-notification-when-a-sender-is-blocked-sending-outbound-spam.md). Para obtener información sobre cómo volver a habilitar a un usuario, consulte [Removing a user, domain, or IP address from a block list after sending spam email](http://technet.microsoft.com/library/712cfcc1-31e8-4e51-8561-b64258a8f1e5.aspx).</span><span class="sxs-lookup"><span data-stu-id="18436-p106">When a significant amount of spam is originating from a particular user, the user is disabled from sending email messages. The administrator for the domain, who is specified using this setting, will be informed that outbound messages are blocked for this user. To see what this notification looks like, see [Sample notification when a sender is blocked sending outbound spam](sample-notification-when-a-sender-is-blocked-sending-outbound-spam.md). For information about getting re-enabled, see [Removing a user, domain, or IP address from a block list after sending spam email](http://technet.microsoft.com/library/712cfcc1-31e8-4e51-8561-b64258a8f1e5.aspx).</span></span>
    
4. <span data-ttu-id="18436-p107">Haga clic en **Guardar**. En el panel a la derecha, aparece un resumen de la configuración predeterminada de directiva.</span><span class="sxs-lookup"><span data-stu-id="18436-p107">Click **save**. A summary of your default policy settings appears in the right pane.</span></span>
    
## <a name="for-more-information"></a><span data-ttu-id="18436-140">Más información</span><span class="sxs-lookup"><span data-stu-id="18436-140">For more information</span></span>
<span data-ttu-id="18436-141"><a name="sectionSection2"> </a></span><span class="sxs-lookup"><span data-stu-id="18436-141"></span></span>

[<span data-ttu-id="18436-142">Grupo de entrega de alto riesgo para mensajes salientes</span><span class="sxs-lookup"><span data-stu-id="18436-142">High-risk delivery pool for outbound messages</span></span>](high-risk-delivery-pool-for-outbound-messages.md)
  
[<span data-ttu-id="18436-143">Protección contra correo no deseado preguntas más frecuentes</span><span class="sxs-lookup"><span data-stu-id="18436-143">Anti-spam protection FAQ</span></span>](anti-spam-protection-faq.md)
  

