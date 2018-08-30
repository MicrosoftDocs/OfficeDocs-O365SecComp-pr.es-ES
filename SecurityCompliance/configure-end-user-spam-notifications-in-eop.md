---
title: Configurar notificaciones de correo no deseado para el usuario final en EOP
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: e9947db5-1dd1-4493-872d-7362b24c7ba0
description: Las notificaciones de correo no deseado para el usuario final se pueden configurar en la directiva de filtro de contenido de toda la compañía, o bien en las directivas de filtro de contenido personalizadas que se aplican a los dominios.
ms.openlocfilehash: 990fa31cc22b33d235d6e8f106511996a52212a2
ms.sourcegitcommit: e9dca2d6a7838f98bb7eca127fdda2372cda402c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/21/2018
ms.locfileid: "23002929"
---
# <a name="configure-end-user-spam-notifications-in-eop"></a><span data-ttu-id="b0f7c-103">Configurar notificaciones de correo no deseado para el usuario final en EOP</span><span class="sxs-lookup"><span data-stu-id="b0f7c-103">Configure end-user spam notifications in EOP</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="b0f7c-p101">En este tema es para los clientes de independiente de Exchange Online Protection (EOP) que va a proteger los buzones locales. Los clientes de Exchange Online que va a proteger los buzones de correo hospedada en la nube deben leer el tema siguiente en su lugar: [configurar para el usuario final de correo no deseado notificaciones en Exchange Online](configure-end-user-spam-notifications-in-exchange-online.md).</span><span class="sxs-lookup"><span data-stu-id="b0f7c-p101">This topic is for Exchange Online Protection (EOP) standalone customers who are protecting on-premises mailboxes. Exchange Online customers who are protecting cloud-hosted mailboxes should read the following topic instead: [Configure end-user spam notifications in Exchange Online](configure-end-user-spam-notifications-in-exchange-online.md).</span></span> 
  
<span data-ttu-id="b0f7c-p102">Las notificaciones de correo no deseado para el usuario final se pueden configurar en la directiva de filtro de contenido de toda la compañía, o bien en las directivas de filtro de contenido personalizadas que se aplican a los dominios. Cuando se habilitan los mensajes de notificación de correo no deseado para el usuario final, los usuarios finales pueden administrar sus propios mensajes de correo no deseado o en cuarentena. Las notificaciones de correo no deseado para el usuario final se pueden usar con directivas válidas que se aplican a usuarios o grupos, o bien a una directiva con excepciones.</span><span class="sxs-lookup"><span data-stu-id="b0f7c-p102">You can configure end-user spam notifications for the default company-wide content filter policy or for custom content filter policies that are applied to domains. Enabling end-user spam notification messages lets your end users self-manage their own spam-quarantined messages. End-user spam notifications cannot be used with policies applied to users or groups, or to a policy with exceptions.</span></span>
  
<span data-ttu-id="b0f7c-p103">Las notificaciones de correo no deseado para el usuario final contienen una lista de los mensajes de correo no deseado puestos en cuarentena que recibió el usuario final durante el período de tiempo que usted configure (puede especificar cualquier valor entre 1 y 15 días). También puede configurar el idioma en el que está escrito el mensaje de notificación.</span><span class="sxs-lookup"><span data-stu-id="b0f7c-p103">End-user spam notifications contain a list of all spam-quarantined messages that the end user has received during a time period that you configure (you can specify a value between 1 and 15 days). You can also configure the language in which the notification message is written.</span></span>
  
<span data-ttu-id="b0f7c-111">Tras recibir un mensaje de notificación, los usuarios finales pueden hacer clic en el correo electrónico no deseado para moverlo a su Bandeja de entrada o informar de que el correo es deseado, en cuyo caso se enviará al equipo de análisis de correo no deseado de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b0f7c-111">After receiving a notification message, end users can click to move the spam email to their inbox, or report the spam email as Not Junk, in which case it will be sent to the Microsoft Spam Analysis Team.</span></span>
  
## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="b0f7c-112">¿Qué necesita saber antes de empezar?</span><span class="sxs-lookup"><span data-stu-id="b0f7c-112">What do you need to know before you begin?</span></span>
<span data-ttu-id="b0f7c-113"><a name="sectionSection0"> </a></span><span class="sxs-lookup"><span data-stu-id="b0f7c-113"></span></span>

<span data-ttu-id="b0f7c-114">Tiempo estimado para finalizar: 5 minutos</span><span class="sxs-lookup"><span data-stu-id="b0f7c-114">Estimated time to complete: 5 minutes</span></span>
  
<span data-ttu-id="b0f7c-p104">Deberá tener asignados permisos antes de poder llevar a cabo este procedimiento o procedimientos. Para ver qué permisos necesita, consulte el entrada "Contra el correo electrónico no deseado" en el tema [Permisos de características en EOP](eop/feature-permissions-in-eop.md).</span><span class="sxs-lookup"><span data-stu-id="b0f7c-p104">You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Anti-spam" entry in the [Feature permissions in EOP](eop/feature-permissions-in-eop.md) topic.</span></span> 
  
<span data-ttu-id="b0f7c-117">Para obtener información acerca de los métodos abreviados de teclado aplicables a los procedimientos de este tema, consulte **Keyboard shortcuts in Exchange 2013**.</span><span class="sxs-lookup"><span data-stu-id="b0f7c-117">For information about keyboard shortcuts that may apply to the procedures in this topic, see **Keyboard shortcuts in the Exchange admin center**.</span></span>
  
## <a name="use-the-eac-to-configure-end-user-spam-notifications"></a><span data-ttu-id="b0f7c-118">Usar el EAC para configurar las notificaciones de correo no deseado para el usuario final</span><span class="sxs-lookup"><span data-stu-id="b0f7c-118">Use the EAC to configure end-user spam notifications</span></span>

1. <span data-ttu-id="b0f7c-119">En el Centro de administración de Exchange (EAC), vaya a **Protección** \> **Filtro de contenido**.</span><span class="sxs-lookup"><span data-stu-id="b0f7c-119">In the Exchange admin center (EAC), navigate to **Protection** \> **Content filter**.</span></span>
    
2. <span data-ttu-id="b0f7c-120">Seleccione la directiva de filtro de contenido para la que quiera habilitar notificaciones de correo no deseado para el usuario final (están deshabilitadas de forma predeterminada).</span><span class="sxs-lookup"><span data-stu-id="b0f7c-120">Select the content filter policy for which you want to enable end-user spam notifications (they are disabled by default).</span></span>
    
3. <span data-ttu-id="b0f7c-121">En el panel derecho, donde aparece la información de resumen sobre la directiva, haga clic en el vínculo **Configurar notificaciones de correo no deseado para el usuario final**.</span><span class="sxs-lookup"><span data-stu-id="b0f7c-121">In the right pane, where the summary information about your policy appears, click the **Configure End-user spam notifications** link.</span></span> 
    
4. <span data-ttu-id="b0f7c-122">En el cuadro de diálogo siguiente, puede configurar las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="b0f7c-122">In the subsequent dialog box, you can configure the following options:</span></span>
    
1. <span data-ttu-id="b0f7c-p105">**Habilitar las notificaciones de correo no deseado para el usuario final** Active esta casilla para habilitar las notificaciones de correo no deseado para el usuario final en esta directiva. (Y viceversa: si la directiva está habilitada, puede desactivar la casilla para deshabilitar las notificaciones de correo no deseado para el usuario final en esta directiva).</span><span class="sxs-lookup"><span data-stu-id="b0f7c-p105">**Enable end-user spam notifications** Select this check box in order to enable end-user spam notifications for this policy. (Conversely, if this policy is enabled, you can clear this check box in order to disable end-user spam notifications for this policy.)</span></span> 
    
2. <span data-ttu-id="b0f7c-p106">**Enviar notificaciones de correo no deseado para el usuario final cada (días)** Especifique la frecuencia con la que quiere que se envíen las notificaciones de correo no deseado para el usuario final. El valor predeterminado es 3 días. Puede especificar cualquier valor entre 1 y 15 días. Si especifica 7 días, por ejemplo, la notificación incluirá una lista de todos los mensajes destinados a ese usuario en los 7 últimos días que se enviaron, en lugar de al usuario, a la cuarentena de correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="b0f7c-p106">**Send end-user spam notifications every (days)** Specify how often to send end-user spam notifications. The default is 3 days. You can specify between 1 and 15 days. If you specify 7 days, for example, the notification will include a list of all messages intended for that user within the past 7 days that were sent to the spam quarantine instead.</span></span> 
    
3. <span data-ttu-id="b0f7c-129">**Idioma de notificación** En la lista desplegable, seleccione el idioma en el que se escribirán las notificaciones de correo no deseado para el usuario final en esta directiva.</span><span class="sxs-lookup"><span data-stu-id="b0f7c-129">**Notification language** Using the drop-down list, select the language in which to write end-user spam notifications for this policy.</span></span> 
    
5. <span data-ttu-id="b0f7c-p107">Haga clic en **Guardar**. Aparecerá un resumen de la configuración de la directiva de filtro de contenido, incluida la configuración de notificaciones de correo no deseado para el usuario final, en el panel derecho.</span><span class="sxs-lookup"><span data-stu-id="b0f7c-p107">Click **save**. A summary of your content filter policy settings, including your end-user spam notification settings, appears in the right pane.</span></span>
    
> [!NOTE]
>  <span data-ttu-id="b0f7c-p108">Las notificaciones de correo no deseado para el usuario final funcionarán únicamente en las directivas de filtro de contenido en las que estén habilitadas. >  Las notificaciones de correo no deseado para el usuario final solo se envían una vez al día. No se puede garantizar ni se puede configurar el plazo de entrega de la notificación para ningún cliente específico.</span><span class="sxs-lookup"><span data-stu-id="b0f7c-p108">End-user spam notifications will only be functional for content filter policies that are enabled. >  End-user spam notifications are only sent once per day. The delivery time of the notification cannot be guaranteed for any specific customer and is not configurable.</span></span> 
  
 <span data-ttu-id="b0f7c-p109">**Sugerencia:** Si quiere probar las notificaciones de correo no deseado para el usuario final enviándolas a un conjunto limitado de usuarios antes de implementarlas totalmente, cree una directiva de filtro de contenido personalizada que habilite notificaciones de correo no deseado para el usuario final para los dominios en los que residen los usuarios. Luego, en el EAC, en **Flujo de correo \> reglas**, cree una regla de transporte para bloquear mensajes de quarantine@messaging.microsoft.com (la dirección de correo electrónico que envía notificaciones) con excepciones para los usuarios que desea que reciban las notificaciones. La siguiente imagen es un ejemplo de cómo crear una excepción para dos usuarios (SaraD y AlexD) desde el dominio Contoso.com:</span><span class="sxs-lookup"><span data-stu-id="b0f7c-p109">**Tip:** If you want to test end-user spam notifications by sending them to a limited set of users before fully implementing them, create a custom content filter policy that enables end-user spam notifications for the domains in which the users reside. Then, in the EAC, under **Mail flow \> rules**, create a transport rule to block messages from quarantine@messaging.microsoft.com (the email address that sends notifications) with exceptions for the users who you want to receive the notifications. The following image is an example of creating an exception for two users (SaraD and AlexD) from domain Contoso.com:</span></span> 
  
![Regla de transporte para probar las notificaciones de correo no deseado de usuario final](media/EOP-ESN-testspecificusers.jpg)
  
## <a name="for-more-information"></a><span data-ttu-id="b0f7c-139">Más información</span><span class="sxs-lookup"><span data-stu-id="b0f7c-139">For more information</span></span>

[<span data-ttu-id="b0f7c-140">Configurar las directivas de filtro de correo no deseado</span><span class="sxs-lookup"><span data-stu-id="b0f7c-140">Configure your spam filter policies</span></span>](configure-your-spam-filter-policies.md)
  
