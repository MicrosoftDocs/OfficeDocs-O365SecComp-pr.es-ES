---
title: Quitar un usuario, un dominio o una dirección IP de una lista de bloqueados después de enviar correo no deseado
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 09/05/2018
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
ms.openlocfilehash: 3f3130bec3cde4cdc1343a0140a9013deacfc519
ms.sourcegitcommit: d85fc77cba3a17d5ddf215e2f506f61b499e0cda
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2018
ms.locfileid: "23839114"
---
# <a name="removing-a-user-domain-or-ip-address-from-a-block-list-after-sending-spam-email"></a><span data-ttu-id="0e872-103">Quitar un usuario, un dominio o una dirección IP de una lista de bloqueados después de enviar correo no deseado</span><span class="sxs-lookup"><span data-stu-id="0e872-103">Removing a user, domain, or IP address from a block list after sending spam email</span></span>

<span data-ttu-id="0e872-104">Si un usuario envía continuamente mensajes de correo electrónico de Office 365 que se clasifica como correo no deseado, se bloqueará de enviar más mensajes.</span><span class="sxs-lookup"><span data-stu-id="0e872-104">If a user continuously sends email messages from Office 365 that is classified as spam, they will be blocked from sending any more messages.</span></span> 
  
<span data-ttu-id="0e872-105">Cuando un remitente está bloqueado de envío de mensajes de correos electrónicos, reciben un informe de no entrega (NDR o no se pudo enviar el mensaje de correo electrónico) que proporciona información específica acerca de los pasos que se tienen que tomar para desbloquear a sí mismos.</span><span class="sxs-lookup"><span data-stu-id="0e872-105">When a sender is blocked from sending emails messages, they receive a Non-Delivery Report (NDR or email failed to send message) that provides specific information about the steps that they have to take to unblock themselves.</span></span>
  
<span data-ttu-id="0e872-p101">No sólo a los usuarios individuales se pueden bloquear por los dominios de servicio, pero determinados sitios Web, y también se pueden bloquear las direcciones IP. En algunos casos, dominios o sitios Web pueden agregarse a una lista de bloqueados sólo porque aparecen en un mensaje de spam. Como la administración de Office 365, puede intentar obtener los usuarios, sitios, dominios y direcciones IP quitadas de listas de bloqueo de otro fabricante. Use los vínculos en la tabla en la parte inferior de este tema para ponerse en contacto con cada tercero y, a continuación, siga las instrucciones. Si alguien de fuera de Office 365 no puede enviar mensajes a su cuenta de Office 365, su cuenta puede haya terminado en la lista de remitentes bloqueados externo. Los usuarios externos a Office 365 pueden intentar se quiten de la lista de remitentes bloqueados a través del [portal de autoservicio de eliminación de la lista](https://technet.microsoft.com/library/mt661881%28v=exchg.150%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="0e872-p101">Not only can individual users be blocked by the service, but specific websites, domains, and IP addresses can also be blocked. In some cases, domains or websites can be added to a block list just because they appear in a spam message. As the Office 365 admin, you can try to get users, websites, domains, and IP addresses removed from third-party block lists. Use the links in the table at the bottom of this topic to contact each third party, and then follow the instructions. If someone outside Office 365 cannot send messages to your Office 365 account, their account may have ended up on the external blocked senders list. Users outside Office 365 can try to remove themselves from the blocked senders list by using the [self-service delisting portal](https://technet.microsoft.com/library/mt661881%28v=exchg.150%29.aspx).</span></span>
  
<span data-ttu-id="0e872-p102">Configuración de correo no deseado saliente puede configurar para que obtener anotification cuando un usuario de Office 365 está bloqueado de envío de correo electrónico que se clasifica como correo no deseado. Una vez resuelto el problema con el buzón del usuario, puede quitar el bloque de ese remitente.</span><span class="sxs-lookup"><span data-stu-id="0e872-p102">You can configure outbound spam settings so that you get anotification when an Office 365 user is blocked from sending email that's classified as spam. After the problem with the user's mailbox is resolved, you can remove the block on that sender.</span></span>
  
## <a name="unblock-a-blocked-office-365-email-account"></a><span data-ttu-id="0e872-114">Desbloquear una cuenta de correo electrónico de Office 365</span><span class="sxs-lookup"><span data-stu-id="0e872-114">Unblock a blocked Office 365 email account</span></span>

<span data-ttu-id="0e872-p103">Complete esta tarea en la seguridad de Office 365 & Centro de cumplimiento (SCC). Para obtener más información acerca de control de código fuente, [vaya a la seguridad de Office 365 & Centro de cumplimiento](go-to-the-securitycompliance-center.md) .</span><span class="sxs-lookup"><span data-stu-id="0e872-p103">You complete this task in the Office 365 Security & Compliance Center (SCC). [Go to the Office 365 Security & Compliance Center](go-to-the-securitycompliance-center.md) for more details about SCC.</span></span>

1. <span data-ttu-id="0e872-117">Utilizando una cuenta de trabajo o escuela que tiene privilegios de administrador global de Office 365, inicie sesión en el centro de cumplimiento y seguridad de Office 365 y en la lista de la izquierda, expanda **Administración de amenaza**, elija la **revisión**y, a continuación, elija **restringidos Los usuarios**.</span><span class="sxs-lookup"><span data-stu-id="0e872-117">Using a work or school account that has Office 365 global administrator privileges, sign into the Office 365 Security and Compliance Center and in the list on the left, expand **Threat Management**, choose **Review**, and then choose **Restricted Users**.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="0e872-118">Para ir directamente a la página **Usuarios restringidos** en la seguridad &amp; centro de cumplimiento, use esta dirección URL: >[https://protection.office.com/?hash=/restrictedusers](https://protection.office.com/?hash=/restrictedusers)</span><span class="sxs-lookup"><span data-stu-id="0e872-118">To go directly to the **Restricted Users** page in the Security &amp; Compliance Center, use this URL: > [https://protection.office.com/?hash=/restrictedusers](https://protection.office.com/?hash=/restrictedusers)</span></span>

2. <span data-ttu-id="0e872-p104">Esta página contendrá la lista de usuarios que se han bloqueado de envío de correo a fuera de la organización.  Busque el usuario o usuarios que desea quitar las restricciones y, a continuación, haga clic en **desbloquear**.</span><span class="sxs-lookup"><span data-stu-id="0e872-p104">This page will contain the list of users that have been blocked from sending mail to outside of your organization.  Find the user(s) you wish to remove restrictions and then click on **Unblock**.</span></span>

3. <span data-ttu-id="0e872-121">Haga clic en **Sí** para confirmar el cambio.</span><span class="sxs-lookup"><span data-stu-id="0e872-121">Click **Yes** to confirm the change.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="0e872-p105">Hay un límite para el número de veces que una cuenta puede ser desbloqueada por el Administrador de inquilinos. Si se ha superado el límite de un usuario, aparece un mensaje de error. A continuación, debe ponerse en contacto con soporte técnico para desbloquear el usuario.</span><span class="sxs-lookup"><span data-stu-id="0e872-p105">There's a limit to the number of times that an account can be unblocked by the tenant admin. If the limit for a user has been exceeded, an error message appears. You will then need to contact Support to unblock the user.</span></span> 
  
## <a name="third-party-block-lists"></a><span data-ttu-id="0e872-124">Listas de bloqueados de terceros</span><span class="sxs-lookup"><span data-stu-id="0e872-124">Third-party block lists</span></span>

|<span data-ttu-id="0e872-125">**Nombre de la lista**</span><span class="sxs-lookup"><span data-stu-id="0e872-125">**List Name**</span></span>|<span data-ttu-id="0e872-126">**Portal de eliminación de la lista**</span><span class="sxs-lookup"><span data-stu-id="0e872-126">**Delisting Portal**</span></span>|<span data-ttu-id="0e872-127">**Más información**</span><span class="sxs-lookup"><span data-stu-id="0e872-127">**For more information**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="0e872-128">URIBL</span><span class="sxs-lookup"><span data-stu-id="0e872-128">URIBL</span></span>  <br/> |[https://admin.uribl.com/?section=lookup](https://admin.uribl.com/?section=lookup) <br/> |[<span data-ttu-id="0e872-129">Sitio Web URIBL</span><span class="sxs-lookup"><span data-stu-id="0e872-129">URIBL website </span></span>](https://uribl.com/) <br/> |
|<span data-ttu-id="0e872-130">SURBL</span><span class="sxs-lookup"><span data-stu-id="0e872-130">SURBL</span></span>  <br/> |[http://www.surbl.org/surbl-analysis](http://www.surbl.org/surbl-analysis) <br/> |[<span data-ttu-id="0e872-131">Presentación de datos de reputación de URI SURBL</span><span class="sxs-lookup"><span data-stu-id="0e872-131">Introducing SURBL URI reputation data</span></span>](http://www.surbl.org/) <br/> |
|<span data-ttu-id="0e872-132">Spamhaus </span><span class="sxs-lookup"><span data-stu-id="0e872-132">Spamhaus</span></span>  <br/> |[https://www.spamhaus.org/lookup/](https://www.spamhaus.org/lookup/) <br/> |[<span data-ttu-id="0e872-133">Descripción de filtrado de DNSBL</span><span class="sxs-lookup"><span data-stu-id="0e872-133">Understanding DNSBL Filtering</span></span>](https://www.spamhaus.org/whitepapers/dnsbl_function/) <br/> |
|<span data-ttu-id="0e872-134">invaluement</span><span class="sxs-lookup"><span data-stu-id="0e872-134">invaluement</span></span>  <br/> |[http://dnsbl.invaluement.com/lookup/](http://dnsbl.invaluement.com/lookup/) <br/> |[<span data-ttu-id="0e872-135">lista de lista contra correo no deseado</span><span class="sxs-lookup"><span data-stu-id="0e872-135">invaluement anti-spam list</span></span>](http://dnsbl.invaluement.com/) <br/> |
|<span data-ttu-id="0e872-136">Phishtank</span><span class="sxs-lookup"><span data-stu-id="0e872-136">Phishtank</span></span>  <br/> |[https://www.phishtank.com/](https://www.phishtank.com/) <br/> |[<span data-ttu-id="0e872-137">PhishTank preguntas más frecuentes</span><span class="sxs-lookup"><span data-stu-id="0e872-137">PhishTank FAQ</span></span>](https://www.phishtank.com/faq.php) <br/> |
   
> [!NOTE]
> <span data-ttu-id="0e872-138">Exchange Online Protection también utiliza las listas de bloqueados de terceros para el filtrado de spam.</span><span class="sxs-lookup"><span data-stu-id="0e872-138">Exchange Online Protection also uses third-party block lists for spam filtering.</span></span> 
   
## <a name="for-more-information"></a><span data-ttu-id="0e872-139">Más información</span><span class="sxs-lookup"><span data-stu-id="0e872-139">For more information</span></span>

[<span data-ttu-id="0e872-140">Configurar la directiva de correo no deseado saliente</span><span class="sxs-lookup"><span data-stu-id="0e872-140">Configure the outbound spam policy</span></span>](configure-the-outbound-spam-policy.md)
  
[<span data-ttu-id="0e872-141">Grupo de entrega de alto riesgo para mensajes salientes</span><span class="sxs-lookup"><span data-stu-id="0e872-141">High-risk delivery pool for outbound messages</span></span>](high-risk-delivery-pool-for-outbound-messages.md)

[<span data-ttu-id="0e872-142">Usar el portal de eliminación de la lista para quitarse de la lista de remitentes bloqueados de Office 365</span><span class="sxs-lookup"><span data-stu-id="0e872-142">Use the delist portal to remove yourself from the Office 365 blocked senders list</span></span>](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md)
  

  

