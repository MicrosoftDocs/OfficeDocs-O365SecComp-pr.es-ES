---
title: Configurar notificaciones de correo no deseado para el usuario final en Exchange Online
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: bfc91c73-a955-40e1-a95f-ad466624339a
ms.collection:
- M365-security-compliance
description: Puede configurar notificaciones de correo no deseado para el usuario final para la directiva predeterminada de filtro de correo no deseado de toda la compañía o para directivas personalizadas de filtro de correo no deseado que se aplican a dominios.
ms.openlocfilehash: e3e5ce044879318dab55f5d08ec2ee0e3379dfb2
ms.sourcegitcommit: 48fa456981b5c52ab8aeace173c8366b9f36723b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2019
ms.locfileid: "30341371"
---
# <a name="configure-end-user-spam-notifications-in-exchange-online"></a><span data-ttu-id="eeda8-103">Configurar notificaciones de correo no deseado para el usuario final en Exchange Online</span><span class="sxs-lookup"><span data-stu-id="eeda8-103">Configure end-user spam notifications in Exchange Online</span></span>

> [!IMPORTANT]
> <span data-ttu-id="eeda8-p101">Este tema es para los clientes de Exchange online que protegen los buzones hospedados en la nube. Exchange Online Protection (EOP) los clientes independientes que protegen buzones locales deben leer el siguiente tema: [configurar notificaciones de correo no deseado para el usuario final en EOP](configure-end-user-spam-notifications-in-eop.md).</span><span class="sxs-lookup"><span data-stu-id="eeda8-p101">This topic is for Exchange Online customers who are protecting cloud-hosted mailboxes. Exchange Online Protection (EOP) standalone customers who are protecting on-premises mailboxes should read the following topic instead: [Configure end-user spam notifications in EOP](configure-end-user-spam-notifications-in-eop.md).</span></span> 
  
<span data-ttu-id="eeda8-p102">Puede configurar notificaciones de correo no deseado para el usuario final para la directiva predeterminada de filtro de correo no deseado de toda la compañía o para directivas personalizadas de filtro de correo no deseado que se aplican a dominios. La habilitación de mensajes de notificación de correo no deseado para el usuario final permite a los usuarios finales administrar automáticamente sus propios mensajes de correo no deseado en cuarentena. Las notificaciones de correo no deseado para el usuario final no se pueden usar con las directivas que se aplican a usuarios o grupos, o a una directiva con excepciones.</span><span class="sxs-lookup"><span data-stu-id="eeda8-p102">You can configure end-user spam notifications for the default company-wide spam filter policy or for custom spam filter policies that are applied to domains. Enabling end-user spam notification messages lets your end users self-manage their own spam-quarantined messages. End-user spam notifications cannot be used with policies applied to users or groups, or to a policy with exceptions.</span></span>
  
<span data-ttu-id="eeda8-p103">Las notificaciones de correo no deseado para el usuario final contienen una lista de los mensajes de correo no deseado puestos en cuarentena que recibió el usuario final durante el período de tiempo que usted configure (puede especificar cualquier valor entre 1 y 15 días). También puede configurar el idioma en el que está escrito el mensaje de notificación.</span><span class="sxs-lookup"><span data-stu-id="eeda8-p103">End-user spam notifications contain a list of all spam-quarantined messages that the end user has received during a time period that you configure (you can specify a value between 1 and 15 days). You can also configure the language in which the notification message is written.</span></span>
  
<span data-ttu-id="eeda8-111">Después de recibir un mensaje de notificación, los usuarios finales pueden elegir entre las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="eeda8-111">After receiving a notification message, end users can choose from the following options:</span></span>

<span data-ttu-id="eeda8-112">**Obtenga una vista previa** del mensaje si desea obtener una vista previa del contenido o encabezado antes de llevar a cabo la acción.</span><span class="sxs-lookup"><span data-stu-id="eeda8-112">**Preview** the message if you would like to preview the content or header prior to taking action.</span></span>

<span data-ttu-id="eeda8-113">**Descargue** el mensaje si desea revisar el mensaje y los datos adjuntos (si los hay) en el dispositivo antes de realizar la acción.</span><span class="sxs-lookup"><span data-stu-id="eeda8-113">**Download** the message if you would like to review the message and attachments (if any) on your device prior to taking action.</span></span>

<span data-ttu-id="eeda8-114">**Release** si el mensaje no es correo no deseado y desea que Office 365 envíe el mensaje al buzón de correo.</span><span class="sxs-lookup"><span data-stu-id="eeda8-114">**Release** if the message isn’t spam and you want Office 365 to send the message to your mailbox.</span></span>

<span data-ttu-id="eeda8-p104">**Versión _AMP_ Permitir remitente** si el mensaje no es correo no deseado y desea que Office 365 agregue el remitente a la lista de remitentes seguros y destinatarios para futuros correos electrónicos. Tenga en cuenta que el administrador puede tener otras configuraciones de permitir o bloquear de toda la organización que invaliden la lista de remitentes seguros.</span><span class="sxs-lookup"><span data-stu-id="eeda8-p104">**Release & Allow Sender** if the message isn’t spam and you want Office 365 to add the sender to your safe senders and recipients list for future emails. Keep in mind that your admin may have other organization wide allow/block configurations that override your safe sender list.</span></span>

<span data-ttu-id="eeda8-117">**Publique el informe de &**, si el mensaje no es correo no deseado y desea enviar el mensaje al buzón e identificarlo en Microsoft para su análisis.</span><span class="sxs-lookup"><span data-stu-id="eeda8-117">**Release & Report**, if the message isn’t spam and you want to send the message to your mailbox and report it to Microsoft for analysis.</span></span>

<span data-ttu-id="eeda8-118">**Bloquear** si desea que Office 365 agregue el remitente a la lista de remitentes bloqueados.</span><span class="sxs-lookup"><span data-stu-id="eeda8-118">**Block** if you want Office 365 to add the sender to your blocked senders list.</span></span>
  
## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="eeda8-119">¿Qué necesita saber antes de comenzar?</span><span class="sxs-lookup"><span data-stu-id="eeda8-119">What do you need to know before you begin?</span></span>

<span data-ttu-id="eeda8-120">Tiempo estimado para finalizar: 2 minutos</span><span class="sxs-lookup"><span data-stu-id="eeda8-120">Estimated time to complete: 2 minutes</span></span>
  
<span data-ttu-id="eeda8-p105">Debe tener permisos asignados para poder llevar a cabo este procedimiento o procedimientos. Para ver qué permisos necesita, consulte el entrada "contra el correo electrónico no deseado" en el tema [permisos de características de Exchange Online](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx) .</span><span class="sxs-lookup"><span data-stu-id="eeda8-p105">You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Anti-spam" entry in the [Feature Permissions in Exchange Online](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx) topic.</span></span> 
  
<span data-ttu-id="eeda8-123">Para obtener información acerca de los métodos abreviados de teclado aplicables a los procedimientos de este tema, consulte **Keyboard shortcuts in Exchange 2013**.</span><span class="sxs-lookup"><span data-stu-id="eeda8-123">For information about keyboard shortcuts that may apply to the procedures in this topic, see **Keyboard shortcuts in the Exchange admin center**.</span></span>
  
## <a name="use-the-eac-to-configure-end-user-spam-notifications"></a><span data-ttu-id="eeda8-124">Usar el EAC para configurar las notificaciones de correo no deseado para el usuario final</span><span class="sxs-lookup"><span data-stu-id="eeda8-124">Use the EAC to configure end-user spam notifications</span></span>

1. <span data-ttu-id="eeda8-125">En el Centro de administración de Exchange (EAC), vaya a **Protección** \> **Filtro de correo no deseado**.</span><span class="sxs-lookup"><span data-stu-id="eeda8-125">In the Exchange admin center (EAC), navigate to **Protection** \> **Spam filter**.</span></span>
    
2. <span data-ttu-id="eeda8-126">Seleccione la Directiva de filtro de correo no deseado para la que desea habilitar las notificaciones de correo no deseado para el usuario final (están deshabilitadas de forma predeterminada).</span><span class="sxs-lookup"><span data-stu-id="eeda8-126">Select the spam filter policy for which you want to enable end-user spam notifications (they are disabled by default).</span></span>
    
3. <span data-ttu-id="eeda8-127">En el panel derecho, donde aparece la información de resumen sobre la directiva, haga clic en el vínculo **Configurar notificaciones de correo no deseado para el usuario final**.</span><span class="sxs-lookup"><span data-stu-id="eeda8-127">In the right pane, where the summary information about your policy appears, click the **Configure End-user spam notifications** link.</span></span> 
    
4. <span data-ttu-id="eeda8-128">En el cuadro de diálogo siguiente, puede configurar las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="eeda8-128">In the subsequent dialog box, you can configure the following options:</span></span>
    
1. <span data-ttu-id="eeda8-p106">**Habilitar las notificaciones de correo no deseado para el usuario final** Active esta casilla para habilitar las notificaciones de correo no deseado para el usuario final en esta directiva. (Y viceversa: si la directiva está habilitada, puede desactivar la casilla para deshabilitar las notificaciones de correo no deseado para el usuario final en esta directiva).</span><span class="sxs-lookup"><span data-stu-id="eeda8-p106">**Enable end-user spam notifications** Select this check box in order to enable end-user spam notifications for this policy. (Conversely, if this policy is enabled, you can clear this check box in order to disable end-user spam notifications for this policy.)</span></span> 
    
2. <span data-ttu-id="eeda8-p107">**Enviar notificaciones de correo no deseado para el usuario final cada (días)** Especifique la frecuencia con la que quiere que se envíen las notificaciones de correo no deseado para el usuario final. El valor predeterminado es 3 días. Puede especificar cualquier valor entre 1 y 15 días. Si especifica 7 días, por ejemplo, la notificación incluirá una lista de todos los mensajes destinados a ese usuario en los 7 últimos días que se enviaron, en lugar de al usuario, a la cuarentena de correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="eeda8-p107">**Send end-user spam notifications every (days)** Specify how often to send end-user spam notifications. The default is 3 days. You can specify between 1 and 15 days. If you specify 7 days, for example, the notification will include a list of all messages intended for that user within the past 7 days that were sent to the spam quarantine instead.</span></span> 
    
3. <span data-ttu-id="eeda8-135">**Idioma de notificación** En la lista desplegable, seleccione el idioma en el que se escribirán las notificaciones de correo no deseado para el usuario final en esta directiva.</span><span class="sxs-lookup"><span data-stu-id="eeda8-135">**Notification language** Using the drop-down list, select the language in which to write end-user spam notifications for this policy.</span></span> 
    
5. <span data-ttu-id="eeda8-p108">Haga clic en **Guardar**. En el panel derecho aparecerá un resumen de la configuración de la Directiva de filtro de correo no deseado, incluida la configuración de notificaciones de correo no deseado para el usuario final.</span><span class="sxs-lookup"><span data-stu-id="eeda8-p108">Click **save**. A summary of your spam filter policy settings, including your end-user spam notification settings, appears in the right pane.</span></span>
    
> [!NOTE]
>  <span data-ttu-id="eeda8-p109">Las notificaciones de correo no deseado para el usuario final solo serán compatibles con las directivas de filtro de correo no deseado que estén habilitadas. >: las notificaciones de correo no deseado para el usuario final solo se envían una vez al día. No se puede garantizar el tiempo de entrega de la notificación para un cliente específico y no se puede configurar.</span><span class="sxs-lookup"><span data-stu-id="eeda8-p109">End-user spam notifications will only be functional for spam filter policies that are enabled. >  End-user spam notifications are only sent once per day. The delivery time of the notification cannot be guaranteed for any specific customer and is not configurable.</span></span> 
  
 <span data-ttu-id="eeda8-p110">**Sugerencia:** Si desea probar las notificaciones de correo no deseado para el usuario final enviándolas a un conjunto limitado de usuarios antes de implementarlos por completo, cree una directiva personalizada de filtro de correo no deseado que permita notificaciones de correo no deseado para el usuario final para los dominios en los que residen los usuarios. A continuación, en el EAC, en **reglas \> de flujo de correo**, cree una regla de flujo de correo (también denominada regla de transporte) para bloquear mensajes de Quarantine@messaging.microsoft.com (la dirección de correo electrónico que envía notificaciones) con excepciones para los usuarios que desee. para recibir las notificaciones. La siguiente imagen es un ejemplo de creación de una excepción para dos usuarios (SARAD y AlexD) del dominio Contoso.com:</span><span class="sxs-lookup"><span data-stu-id="eeda8-p110">**Tip:** If you want to test end-user spam notifications by sending them to a limited set of users before fully implementing them, create a custom spam filter policy that enables end-user spam notifications for the domains in which the users reside. Then, in the EAC, under **Mail flow \> rules**, create a mail flow rule (also known as a transport rule) to block messages from quarantine@messaging.microsoft.com (the email address that sends notifications) with exceptions for the users who you want to receive the notifications. The following image is an example of creating an exception for two users (SaraD and AlexD) from domain Contoso.com:</span></span> 
  
![Regla de transporte para probar las notificaciones de correo no deseado de usuario final](media/EOP-ESN-testspecificusers.jpg)
  
## <a name="for-more-information"></a><span data-ttu-id="eeda8-145">Más información</span><span class="sxs-lookup"><span data-stu-id="eeda8-145">For more information</span></span>

[<span data-ttu-id="eeda8-146">Configurar las directivas de filtro de correo no deseado</span><span class="sxs-lookup"><span data-stu-id="eeda8-146">Configure your spam filter policies</span></span>](configure-your-spam-filter-policies.md)
  
