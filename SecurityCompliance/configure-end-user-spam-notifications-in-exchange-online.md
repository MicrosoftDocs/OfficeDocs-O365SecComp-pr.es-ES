---
title: Configurar notificaciones de correo no deseado para el usuario final en Exchange Online
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: bfc91c73-a955-40e1-a95f-ad466624339a
description: Puede configurar notificaciones de spam para el usuario final para la directiva de filtro de spam de toda la compañía predeterminada o para las directivas de filtro de correo no deseado personalizadas que se aplican a dominios.
ms.openlocfilehash: 4a4c7c6b139fe0f8b0a1f6b69c1b95e321293af5
ms.sourcegitcommit: 22bca85c3c6d946083d3784f72e886c068d49f4a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/06/2018
ms.locfileid: "22027537"
---
# <a name="configure-end-user-spam-notifications-in-exchange-online"></a><span data-ttu-id="b7130-103">Configurar notificaciones de correo no deseado para el usuario final en Exchange Online</span><span class="sxs-lookup"><span data-stu-id="b7130-103">Configure end-user spam notifications in Exchange Online</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b7130-p101">En este tema es para los clientes de Exchange Online que va a proteger los buzones de correo hospedada en la nube. Los clientes de independiente de Exchange Online Protection (EOP) que va a proteger los buzones locales deben leer el tema siguiente en su lugar: [Configurar notificaciones de spam para el usuario final en EOP](configure-end-user-spam-notifications-in-eop.md).</span><span class="sxs-lookup"><span data-stu-id="b7130-p101">This topic is for Exchange Online customers who are protecting cloud-hosted mailboxes. Exchange Online Protection (EOP) standalone customers who are protecting on-premises mailboxes should read the following topic instead: [Configure end-user spam notifications in EOP](configure-end-user-spam-notifications-in-eop.md).</span></span> 
  
<span data-ttu-id="b7130-p102">Puede configurar notificaciones de spam para el usuario final para la directiva de filtro de spam de toda la compañía predeterminada o para las directivas de filtro de correo no deseado personalizadas que se aplican a dominios. Habilitación de los mensajes de notificación de spam para el usuario final permite a los usuarios finales Self-administrar sus propios mensajes en cuarentena de correo no deseado. Notificaciones de spam para el usuario final no pueden usarse con las directivas que se aplica a los usuarios o grupos, o a una directiva con excepciones.</span><span class="sxs-lookup"><span data-stu-id="b7130-p102">You can configure end-user spam notifications for the default company-wide spam filter policy or for custom spam filter policies that are applied to domains. Enabling end-user spam notification messages lets your end users self-manage their own spam-quarantined messages. End-user spam notifications cannot be used with policies applied to users or groups, or to a policy with exceptions.</span></span>
  
<span data-ttu-id="b7130-p103">Las notificaciones de correo no deseado para el usuario final contienen una lista de los mensajes de correo no deseado puestos en cuarentena que recibió el usuario final durante el período de tiempo que usted configure (puede especificar cualquier valor entre 1 y 15 días). También puede configurar el idioma en el que está escrito el mensaje de notificación.</span><span class="sxs-lookup"><span data-stu-id="b7130-p103">End-user spam notifications contain a list of all spam-quarantined messages that the end user has received during a time period that you configure (you can specify a value between 1 and 15 days). You can also configure the language in which the notification message is written.</span></span>
  
<span data-ttu-id="b7130-111">Tras recibir un mensaje de notificación, los usuarios finales pueden hacer clic en el correo electrónico no deseado para moverlo a su Bandeja de entrada o informar de que el correo es deseado, en cuyo caso se enviará al equipo de análisis de correo no deseado de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b7130-111">After receiving a notification message, end users can click to move the spam email to their inbox, or report the spam email as Not Junk, in which case it will be sent to the Microsoft Spam Analysis Team.</span></span> 
  
## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="b7130-112">¿Qué necesita saber antes de comenzar?</span><span class="sxs-lookup"><span data-stu-id="b7130-112">What do you need to know before you begin?</span></span>

<span data-ttu-id="b7130-113">Tiempo estimado para finalizar: 2 minutos</span><span class="sxs-lookup"><span data-stu-id="b7130-113">Estimated time to complete: 2 minutes</span></span>
  
<span data-ttu-id="b7130-p104">Debe tener asignados los permisos puede llevar a cabo estos procedimientos. Para ver qué permisos necesita, vea la entrada "Contra correo no deseado" en el tema [Feature Permissions in Exchange Online](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx) .</span><span class="sxs-lookup"><span data-stu-id="b7130-p104">You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Anti-spam" entry in the [Feature Permissions in Exchange Online](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx) topic.</span></span> 
  
<span data-ttu-id="b7130-116">Para obtener información acerca de los métodos abreviados de teclado aplicables a los procedimientos de este tema, consulte **Keyboard shortcuts in Exchange 2013**.</span><span class="sxs-lookup"><span data-stu-id="b7130-116">For information about keyboard shortcuts that may apply to the procedures in this topic, see **Keyboard shortcuts in the Exchange admin center**.</span></span>
  
## <a name="use-the-eac-to-configure-end-user-spam-notifications"></a><span data-ttu-id="b7130-117">Usar el EAC para configurar las notificaciones de correo no deseado para el usuario final</span><span class="sxs-lookup"><span data-stu-id="b7130-117">Use the EAC to configure end-user spam notifications</span></span>

1. <span data-ttu-id="b7130-118">En el Centro de administración de Exchange (EAC), vaya a **Protección** \> **Filtro de correo no deseado**.</span><span class="sxs-lookup"><span data-stu-id="b7130-118">In the Exchange admin center (EAC), navigate to **Protection** \> **Spam filter**.</span></span>
    
2. <span data-ttu-id="b7130-119">Seleccione la directiva de filtro de spam para el que desea habilitar las notificaciones de spam para el usuario final (están deshabilitadas de forma predeterminada).</span><span class="sxs-lookup"><span data-stu-id="b7130-119">Select the spam filter policy for which you want to enable end-user spam notifications (they are disabled by default).</span></span>
    
3. <span data-ttu-id="b7130-120">En el panel derecho, donde aparece la información de resumen sobre la directiva, haga clic en el vínculo **Configurar notificaciones de correo no deseado para el usuario final**.</span><span class="sxs-lookup"><span data-stu-id="b7130-120">In the right pane, where the summary information about your policy appears, click the **Configure End-user spam notifications** link.</span></span> 
    
4. <span data-ttu-id="b7130-121">En el cuadro de diálogo siguiente, puede configurar las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="b7130-121">In the subsequent dialog box, you can configure the following options:</span></span>
    
1. <span data-ttu-id="b7130-p105">**Habilitar las notificaciones de correo no deseado para el usuario final** Active esta casilla para habilitar las notificaciones de correo no deseado para el usuario final en esta directiva. (Y viceversa: si la directiva está habilitada, puede desactivar la casilla para deshabilitar las notificaciones de correo no deseado para el usuario final en esta directiva).</span><span class="sxs-lookup"><span data-stu-id="b7130-p105">**Enable end-user spam notifications** Select this check box in order to enable end-user spam notifications for this policy. (Conversely, if this policy is enabled, you can clear this check box in order to disable end-user spam notifications for this policy.)</span></span> 
    
2. <span data-ttu-id="b7130-p106">**Enviar notificaciones de correo no deseado para el usuario final cada (días)** Especifique la frecuencia con la que quiere que se envíen las notificaciones de correo no deseado para el usuario final. El valor predeterminado es 3 días. Puede especificar cualquier valor entre 1 y 15 días. Si especifica 7 días, por ejemplo, la notificación incluirá una lista de todos los mensajes destinados a ese usuario en los 7 últimos días que se enviaron, en lugar de al usuario, a la cuarentena de correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="b7130-p106">**Send end-user spam notifications every (days)** Specify how often to send end-user spam notifications. The default is 3 days. You can specify between 1 and 15 days. If you specify 7 days, for example, the notification will include a list of all messages intended for that user within the past 7 days that were sent to the spam quarantine instead.</span></span> 
    
3. <span data-ttu-id="b7130-128">**Idioma de notificación** En la lista desplegable, seleccione el idioma en el que se escribirán las notificaciones de correo no deseado para el usuario final en esta directiva.</span><span class="sxs-lookup"><span data-stu-id="b7130-128">**Notification language** Using the drop-down list, select the language in which to write end-user spam notifications for this policy.</span></span> 
    
5. <span data-ttu-id="b7130-p107">Haga clic en **Guardar**. Se mostrará un resumen de su configuración de directiva de filtro de correo no deseado, incluida la configuración de notificación de correo no deseado del usuario final, en el panel derecho.</span><span class="sxs-lookup"><span data-stu-id="b7130-p107">Click **save**. A summary of your spam filter policy settings, including your end-user spam notification settings, appears in the right pane.</span></span>
    
> [!NOTE]
>  <span data-ttu-id="b7130-p108">Notificaciones de spam para el usuario final sólo será funcionales para directivas de filtro de correo no deseado que están habilitadas. > Sólo se envían las notificaciones de spam para el usuario final una vez al día. La hora de la notificación de entrega no se puede garantizar para cualquier cliente específico y no se puede configurar.</span><span class="sxs-lookup"><span data-stu-id="b7130-p108">End-user spam notifications will only be functional for spam filter policies that are enabled. >  End-user spam notifications are only sent once per day. The delivery time of the notification cannot be guaranteed for any specific customer and is not configurable.</span></span> 
  
 <span data-ttu-id="b7130-p109">**Sugerencia:** Si desea probar las notificaciones de spam para el usuario final mediante el envío a un conjunto limitado de usuarios antes de implementarlos totalmente, crear una directiva de filtro de correo no deseado personalizadas que habilita las notificaciones de spam para el usuario final para los dominios en la que residen los usuarios. A continuación, en el CEF, bajo **flujo de correo \> reglas**, crear una regla de transporte para bloquear los mensajes de quarantine@messaging.microsoft.com (la dirección de correo electrónico que envía notificaciones) con excepciones para los usuarios que desea recibir las notificaciones. La imagen siguiente es un ejemplo de creación de una excepción para dos usuarios (SaraD y AlexD) desde el dominio Contoso.com:</span><span class="sxs-lookup"><span data-stu-id="b7130-p109">**Tip:** If you want to test end-user spam notifications by sending them to a limited set of users before fully implementing them, create a custom spam filter policy that enables end-user spam notifications for the domains in which the users reside. Then, in the EAC, under **Mail flow \> rules**, create a transport rule to block messages from quarantine@messaging.microsoft.com (the email address that sends notifications) with exceptions for the users who you want to receive the notifications. The following image is an example of creating an exception for two users (SaraD and AlexD) from domain Contoso.com:</span></span> 
  
![Regla de transporte para probar las notificaciones de correo no deseado de usuario final](media/EOP-ESN-testspecificusers.jpg)
  
## <a name="for-more-information"></a><span data-ttu-id="b7130-138">Más información</span><span class="sxs-lookup"><span data-stu-id="b7130-138">For more information</span></span>

[<span data-ttu-id="b7130-139">Configurar las directivas de filtro de correo no deseado</span><span class="sxs-lookup"><span data-stu-id="b7130-139">Configure your spam filter policies</span></span>](configure-your-spam-filter-policies.md)
  
