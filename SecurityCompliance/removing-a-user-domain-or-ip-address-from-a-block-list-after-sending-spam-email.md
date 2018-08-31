---
title: Quitar un usuario, un dominio o una dirección IP de una lista de bloqueados después de enviar correo no deseado
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 6/20/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.exch.eac.ActionCenter
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 712cfcc1-31e8-4e51-8561-b64258a8f1e5
description: Si un usuario envía continuamente mensajes de correo electrónico de Office 365 que se clasifica como correo no deseado, se bloqueará de enviar más mensajes.
ms.openlocfilehash: 87b7083fe1345a15ea582f12a5b0d417bbe6b568
ms.sourcegitcommit: e9dca2d6a7838f98bb7eca127fdda2372cda402c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/21/2018
ms.locfileid: "23002613"
---
# <a name="removing-a-user-domain-or-ip-address-from-a-block-list-after-sending-spam-email"></a><span data-ttu-id="68edb-103">Quitar un usuario, un dominio o una dirección IP de una lista de bloqueados después de enviar correo no deseado</span><span class="sxs-lookup"><span data-stu-id="68edb-103">Removing a user, domain, or IP address from a block list after sending spam email</span></span>

<span data-ttu-id="68edb-104">Si un usuario envía continuamente mensajes de correo electrónico de Office 365 que se clasifica como correo no deseado, se bloqueará de enviar más mensajes.</span><span class="sxs-lookup"><span data-stu-id="68edb-104">If a user continuously sends email messages from Office 365 that is classified as spam, they will be blocked from sending any more messages.</span></span> 
  
<span data-ttu-id="68edb-105">Cuando un remitente está bloqueado de envío de mensajes de correos electrónicos, reciben un informe de no entrega (NDR o no se pudo enviar el mensaje de correo electrónico) que proporciona información específica acerca de los pasos que se tienen que tomar para desbloquear a sí mismos.</span><span class="sxs-lookup"><span data-stu-id="68edb-105">When a sender is blocked from sending emails messages, they receive a Non-Delivery Report (NDR or email failed to send message) that provides specific information about the steps that they have to take to unblock themselves.</span></span>
  
<span data-ttu-id="68edb-p101">No sólo a los usuarios individuales se pueden bloquear por los dominios de servicio, pero determinados sitios Web, y también se pueden bloquear las direcciones IP. En algunos casos, dominios o sitios Web pueden agregarse a una lista de bloqueados sólo porque aparecen en un mensaje de spam. Como la administración de Office 365, puede intentar obtener los usuarios, sitios, dominios y direcciones IP quitadas de listas de bloqueo de otro fabricante. Use los vínculos en la tabla en la parte inferior de este tema para ponerse en contacto con cada tercero y, a continuación, siga las instrucciones. Si alguien de fuera de Office 365 no puede enviar mensajes a su cuenta de Office 365, su cuenta puede haya terminado en la lista de remitentes bloqueados externo. Los usuarios externos a Office 365 pueden intentar se quiten de la lista de remitentes bloqueados a través del [portal de autoservicio de eliminación de la lista](https://technet.microsoft.com/library/mt661881%28v=exchg.150%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="68edb-p101">Not only can individual users be blocked by the service, but specific websites, domains, and IP addresses can also be blocked. In some cases, domains or websites can be added to a block list just because they appear in a spam message. As the Office 365 admin, you can try to get users, websites, domains, and IP addresses removed from third-party block lists. Use the links in the table at the bottom of this topic to contact each third party, and then follow the instructions. If someone outside Office 365 cannot send messages to your Office 365 account, their account may have ended up on the external blocked senders list. Users outside Office 365 can try to remove themselves from the blocked senders list by using the [self-service delisting portal](https://technet.microsoft.com/library/mt661881%28v=exchg.150%29.aspx).</span></span>
  
<span data-ttu-id="68edb-p102">Configuración de correo no deseado saliente puede configurar para que obtener anotification cuando un usuario de Office 365 está bloqueado de envío de correo electrónico que se clasifica como correo no deseado. Una vez resuelto el problema con el buzón del usuario, puede quitar el bloque de ese remitente.</span><span class="sxs-lookup"><span data-stu-id="68edb-p102">You can configure outbound spam settings so that you get anotification when an Office 365 user is blocked from sending email that's classified as spam. After the problem with the user's mailbox is resolved, you can remove the block on that sender.</span></span>
  
## <a name="unblock-a-blocked-office-365-email-account"></a><span data-ttu-id="68edb-114">Desbloquear una cuenta de correo electrónico de Office 365</span><span class="sxs-lookup"><span data-stu-id="68edb-114">Unblock a blocked Office 365 email account</span></span>

<span data-ttu-id="68edb-p103">Complete esta tarea en el centro de administración de Exchange (EAC). Desproteger [Exchange centro de administración en Exchange Online Protection](exchange-admin-center-in-exchange-online-protection-eop.md) para obtener información detallada sobre el CEF.</span><span class="sxs-lookup"><span data-stu-id="68edb-p103">You complete this task in the Exchange admin center (EAC). Check out [Exchange admin center in Exchange Online Protection](exchange-admin-center-in-exchange-online-protection-eop.md) for details about the EAC.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="68edb-117">No verá el centro de actividades a no ser que se encuentre en el EAC de Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="68edb-117">You won't see the action center unless you're in the EAC for Exchange Online.</span></span> 
  
1. <span data-ttu-id="68edb-118">En el EAC, vaya a **protección** \> **Centro de acción**.</span><span class="sxs-lookup"><span data-stu-id="68edb-118">In the EAC, navigate to **protection** \> **action center**.</span></span>
    
    ![Vaya al Centro de actividades del Centro de administración de Exchange.](media/9bbf0844-7b34-4a86-a2b7-8c7e9c8519a3.png)
  
2. <span data-ttu-id="68edb-120">Seleccione el icono de **búsqueda** y, a continuación, escriba la dirección SMTP del usuario bloqueado.</span><span class="sxs-lookup"><span data-stu-id="68edb-120">Select the **Search** icon, and then enter the SMTP address of the blocked user.</span></span> 
    
    ![Buscar a un usuario bloqueado en el Centro de actividades](media/f931b5a0-7115-4d95-9f6f-b403436031ba.png)
  
3. <span data-ttu-id="68edb-122">Haga clic en **Desbloquear la cuenta** en el panel Descripción.</span><span class="sxs-lookup"><span data-stu-id="68edb-122">Click **Unblock Account** in the description pane.</span></span> 
    
    ![Desbloquear a un usuario en el Centro de actividades](media/c5d5b1b9-8416-45aa-9631-881e94d1d056.png)
  
4. <span data-ttu-id="68edb-124">Haga clic en **Sí** para confirmar el cambio.</span><span class="sxs-lookup"><span data-stu-id="68edb-124">Click **Yes** to confirm the change.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="68edb-p104">Hay un límite para el número de veces que una cuenta puede ser desbloqueada por el Administrador de inquilinos. Si se ha superado el límite de un usuario, aparece un mensaje de error. Póngase en contacto con soporte técnico para desbloquear el usuario.</span><span class="sxs-lookup"><span data-stu-id="68edb-p104">There's a limit to the number of times that an account can be unblocked by the tenant admin. If the limit for a user has been exceeded, an error message appears. Contact Support to unblock the user.</span></span> 
  
## <a name="third-party-block-lists"></a><span data-ttu-id="68edb-127">Listas de bloqueados de terceros</span><span class="sxs-lookup"><span data-stu-id="68edb-127">Third-party block lists</span></span>

|<span data-ttu-id="68edb-128">**Nombre de la lista**</span><span class="sxs-lookup"><span data-stu-id="68edb-128">**List Name**</span></span>|<span data-ttu-id="68edb-129">**Portal de eliminación de la lista**</span><span class="sxs-lookup"><span data-stu-id="68edb-129">**Delisting Portal**</span></span>|<span data-ttu-id="68edb-130">**Más información**</span><span class="sxs-lookup"><span data-stu-id="68edb-130">**For more information**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="68edb-131">URIBL</span><span class="sxs-lookup"><span data-stu-id="68edb-131">URIBL</span></span>  <br/> |[https://admin.uribl.com/?section=lookup](https://admin.uribl.com/?section=lookup) <br/> |[<span data-ttu-id="68edb-132">Sitio Web URIBL</span><span class="sxs-lookup"><span data-stu-id="68edb-132">URIBL website </span></span>](https://uribl.com/) <br/> |
|<span data-ttu-id="68edb-133">SURBL</span><span class="sxs-lookup"><span data-stu-id="68edb-133">SURBL</span></span>  <br/> |[http://www.surbl.org/surbl-analysis](http://www.surbl.org/surbl-analysis) <br/> |[<span data-ttu-id="68edb-134">Presentación de datos de reputación de URI SURBL</span><span class="sxs-lookup"><span data-stu-id="68edb-134">Introducing SURBL URI reputation data</span></span>](http://www.surbl.org/) <br/> |
|<span data-ttu-id="68edb-135">Spamhaus </span><span class="sxs-lookup"><span data-stu-id="68edb-135">Spamhaus</span></span>  <br/> |[https://www.spamhaus.org/lookup/](https://www.spamhaus.org/lookup/) <br/> |[<span data-ttu-id="68edb-136">Descripción de filtrado de DNSBL</span><span class="sxs-lookup"><span data-stu-id="68edb-136">Understanding DNSBL Filtering</span></span>](https://www.spamhaus.org/whitepapers/dnsbl_function/) <br/> |
|<span data-ttu-id="68edb-137">invaluement</span><span class="sxs-lookup"><span data-stu-id="68edb-137">invaluement</span></span>  <br/> |[http://dnsbl.invaluement.com/lookup/](http://dnsbl.invaluement.com/lookup/) <br/> |[<span data-ttu-id="68edb-138">lista de lista contra correo no deseado</span><span class="sxs-lookup"><span data-stu-id="68edb-138">invaluement anti-spam list</span></span>](http://dnsbl.invaluement.com/) <br/> |
|<span data-ttu-id="68edb-139">Phishtank</span><span class="sxs-lookup"><span data-stu-id="68edb-139">Phishtank</span></span>  <br/> |[https://www.phishtank.com/](https://www.phishtank.com/) <br/> |[<span data-ttu-id="68edb-140">PhishTank preguntas más frecuentes</span><span class="sxs-lookup"><span data-stu-id="68edb-140">PhishTank FAQ</span></span>](https://www.phishtank.com/faq.php) <br/> |
   
> [!NOTE]
> <span data-ttu-id="68edb-141">Exchange Online Protection también utiliza las listas de bloqueados de terceros para el filtrado de spam.</span><span class="sxs-lookup"><span data-stu-id="68edb-141">Exchange Online Protection also uses third-party block lists for spam filtering.</span></span> 
   
## <a name="for-more-information"></a><span data-ttu-id="68edb-142">Más información</span><span class="sxs-lookup"><span data-stu-id="68edb-142">For more information</span></span>

[<span data-ttu-id="68edb-143">Configurar la directiva de correo no deseado saliente</span><span class="sxs-lookup"><span data-stu-id="68edb-143">Configure the outbound spam policy</span></span>](configure-the-outbound-spam-policy.md)
  
[<span data-ttu-id="68edb-144">Grupo de entrega de alto riesgo para mensajes salientes</span><span class="sxs-lookup"><span data-stu-id="68edb-144">High-risk delivery pool for outbound messages</span></span>](high-risk-delivery-pool-for-outbound-messages.md)

[<span data-ttu-id="68edb-145">Usar el portal de eliminación de la lista para quitarse de la lista de remitentes bloqueados de Office 365</span><span class="sxs-lookup"><span data-stu-id="68edb-145">Use the delist portal to remove yourself from the Office 365 blocked senders list</span></span>](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md)
  

  

