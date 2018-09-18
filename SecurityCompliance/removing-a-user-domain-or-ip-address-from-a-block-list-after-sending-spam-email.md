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
ms.openlocfilehash: 6665c405c62f75b77e7898419ebcfbc1c8c20f4c
ms.sourcegitcommit: 7b85c22fc85ec19e4b44a07e91bfa9ade768185a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/18/2018
ms.locfileid: "23998614"
---
# <a name="removing-a-user-domain-or-ip-address-from-a-block-list-after-sending-spam-email"></a><span data-ttu-id="41bc8-103">Quitar un usuario, un dominio o una dirección IP de una lista de bloqueados después de enviar correo no deseado</span><span class="sxs-lookup"><span data-stu-id="41bc8-103">Removing a user, domain, or IP address from a block list after sending spam email</span></span>

<span data-ttu-id="41bc8-p101">Si un usuario envía continuamente mensajes de correo electrónico de Office 365 que se clasifica como correo no deseado, se bloqueará de enviar más mensajes. El usuario se mostrarán en el servicio como un remitente de salida incorrecto y recibirá un informe de no entrega (NDR) que indica:</span><span class="sxs-lookup"><span data-stu-id="41bc8-p101">If a user continuously sends email messages from Office 365 that is classified as spam, they will be blocked from sending any more messages. The user will be listed in the service as a bad outbound sender and will receive a Non-Delivery Report (NDR) that states:</span></span>

- <span data-ttu-id="41bc8-p102">No se pudo entregar el mensaje porque no se han reconocido como remitente válido. La razón más común de esto es que su dirección de correo electrónico es sospechosos de enviar spam y que ya no se permite para enviar mensajes de fuera de la organización. Para obtener ayuda, póngase en contacto con el Administrador de correo electrónico.  Servidor remoto devolvió '550 5.1.8 acceso denegado, remitente saliente incorrecta'</span><span class="sxs-lookup"><span data-stu-id="41bc8-p102">Your message couldn't be delivered because you weren't recognized as a valid sender. The most common reason for this is that your email address is suspected of sending spam and it's no longer allowed to send messages outside of your organization. Contact your email admin for assistance.  Remote Server returned '550 5.1.8 Access denied, bad outbound sender'</span></span>

<span data-ttu-id="41bc8-p103">Puede configurar la configuración de directiva de correo no deseado saliente por lo que se recibe una notificación cuando un usuario de Office 365 está bloqueado de envío de correo electrónico. Una vez resuelto el problema con el buzón del usuario, puede quitar el bloque de ese remitente.</span><span class="sxs-lookup"><span data-stu-id="41bc8-p103">You can configure your outbound spam policy settings so that you get a notification when an Office 365 user is blocked from sending email. After the problem with the user's mailbox is resolved, you can remove the block on that sender.</span></span>
  
## <a name="unblock-a-blocked-office-365-email-account"></a><span data-ttu-id="41bc8-112">Desbloquear una cuenta de correo electrónico de Office 365</span><span class="sxs-lookup"><span data-stu-id="41bc8-112">Unblock a blocked Office 365 email account</span></span>

<span data-ttu-id="41bc8-p104">Complete esta tarea en la seguridad de Office 365 & Centro de cumplimiento (SCC). Para obtener más información acerca de control de código fuente, [vaya a la seguridad de Office 365 & Centro de cumplimiento](go-to-the-securitycompliance-center.md) .</span><span class="sxs-lookup"><span data-stu-id="41bc8-p104">You complete this task in the Office 365 Security & Compliance Center (SCC). [Go to the Office 365 Security & Compliance Center](go-to-the-securitycompliance-center.md) for more details about SCC.</span></span>

1. <span data-ttu-id="41bc8-115">Utilizando una cuenta de trabajo o escuela que tiene privilegios de administrador global de Office 365, inicie sesión en el centro de cumplimiento y seguridad de Office 365 y en la lista de la izquierda, expanda **Administración de amenaza**, elija la **revisión**y, a continuación, elija **restringidos Los usuarios**.</span><span class="sxs-lookup"><span data-stu-id="41bc8-115">Using a work or school account that has Office 365 global administrator privileges, sign into the Office 365 Security and Compliance Center and in the list on the left, expand **Threat Management**, choose **Review**, and then choose **Restricted Users**.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="41bc8-116">Para ir directamente a la página **Usuarios restringidos** en la seguridad &amp; centro de cumplimiento, use esta dirección URL: >[https://protection.office.com/?hash=/restrictedusers](https://protection.office.com/?hash=/restrictedusers)</span><span class="sxs-lookup"><span data-stu-id="41bc8-116">To go directly to the **Restricted Users** page in the Security &amp; Compliance Center, use this URL: > [https://protection.office.com/?hash=/restrictedusers](https://protection.office.com/?hash=/restrictedusers)</span></span>

2. <span data-ttu-id="41bc8-p105">Esta página contendrá la lista de usuarios que se han bloqueado de envío de correo a fuera de la organización.  Busque el usuario que desea quitar restricciones en y, a continuación, haga clic en **desbloquear**.</span><span class="sxs-lookup"><span data-stu-id="41bc8-p105">This page will contain the list of users that have been blocked from sending mail to outside of your organization.  Find the user you wish to remove restrictions on and then click on **Unblock**.</span></span>

3. <span data-ttu-id="41bc8-119">Haga clic en **Sí** para confirmar el cambio.</span><span class="sxs-lookup"><span data-stu-id="41bc8-119">Click **Yes** to confirm the change.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="41bc8-p106">Hay un límite para el número de veces que una cuenta puede ser desbloqueada por el Administrador de inquilinos. Si se ha superado el límite de un usuario, aparece un mensaje de error. A continuación, debe ponerse en contacto con soporte técnico para desbloquear el usuario.</span><span class="sxs-lookup"><span data-stu-id="41bc8-p106">There's a limit to the number of times that an account can be unblocked by the tenant admin. If the limit for a user has been exceeded, an error message appears. You will then need to contact Support to unblock the user.</span></span>
  
## <a name="third-party-block-lists"></a><span data-ttu-id="41bc8-122">Listas de bloqueados de terceros</span><span class="sxs-lookup"><span data-stu-id="41bc8-122">Third-party block lists</span></span>

<span data-ttu-id="41bc8-p107">Exchange Online Protection también usa listas de bloqueo de otro fabricante para ayudar a tomar decisiones de filtrado de spam. Los usuarios, sitios, dominios y direcciones IP pueden agregarse a bloquear listas solo para que aparezca en un mensaje de spam. Como la administración de Office 365, debe intentar obtener estos objetos quitado de los proveedores de la lista de terceros si éstos pertenecen a usted. Use los vínculos en el debajo de la tabla para ponerse en contacto con cada tercero y, a continuación, siga las instrucciones.</span><span class="sxs-lookup"><span data-stu-id="41bc8-p107">Exchange Online Protection also uses third-party block lists to help make decisions in spam filtering. Users, websites, domains, and IP addresses can be added to block lists just for appearing in a spam message. As the Office 365 admin, you should try to get these objects removed from the third-party list providers if they belong to you. Use the links in the below table to contact each third party and then follow their instructions.</span></span>

|<span data-ttu-id="41bc8-127">**Nombre de la lista**</span><span class="sxs-lookup"><span data-stu-id="41bc8-127">**List Name**</span></span>|<span data-ttu-id="41bc8-128">**Portal de eliminación de la lista**</span><span class="sxs-lookup"><span data-stu-id="41bc8-128">**Delisting Portal**</span></span>|<span data-ttu-id="41bc8-129">**Más información**</span><span class="sxs-lookup"><span data-stu-id="41bc8-129">**For more information**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="41bc8-130">URIBL</span><span class="sxs-lookup"><span data-stu-id="41bc8-130">URIBL</span></span>  <br/> |[https://admin.uribl.com/?section=lookup](https://admin.uribl.com/?section=lookup) <br/> |[<span data-ttu-id="41bc8-131">Sitio Web URIBL</span><span class="sxs-lookup"><span data-stu-id="41bc8-131">URIBL website </span></span>](https://uribl.com/) <br/> |
|<span data-ttu-id="41bc8-132">SURBL</span><span class="sxs-lookup"><span data-stu-id="41bc8-132">SURBL</span></span>  <br/> |[http://www.surbl.org/surbl-analysis](http://www.surbl.org/surbl-analysis) <br/> |[<span data-ttu-id="41bc8-133">Presentación de datos de reputación de URI SURBL</span><span class="sxs-lookup"><span data-stu-id="41bc8-133">Introducing SURBL URI reputation data</span></span>](http://www.surbl.org/) <br/> |
|<span data-ttu-id="41bc8-134">Spamhaus </span><span class="sxs-lookup"><span data-stu-id="41bc8-134">Spamhaus</span></span>  <br/> |[https://www.spamhaus.org/lookup/](https://www.spamhaus.org/lookup/) <br/> |[<span data-ttu-id="41bc8-135">Descripción de filtrado de DNSBL</span><span class="sxs-lookup"><span data-stu-id="41bc8-135">Understanding DNSBL Filtering</span></span>](https://www.spamhaus.org/whitepapers/dnsbl_function/) <br/> |
|<span data-ttu-id="41bc8-136">invaluement</span><span class="sxs-lookup"><span data-stu-id="41bc8-136">invaluement</span></span>  <br/> |[http://dnsbl.invaluement.com/lookup/](http://dnsbl.invaluement.com/lookup/) <br/> |[<span data-ttu-id="41bc8-137">lista de lista contra correo no deseado</span><span class="sxs-lookup"><span data-stu-id="41bc8-137">invaluement anti-spam list</span></span>](http://dnsbl.invaluement.com/) <br/> |
|<span data-ttu-id="41bc8-138">Phishtank</span><span class="sxs-lookup"><span data-stu-id="41bc8-138">Phishtank</span></span>  <br/> |[https://www.phishtank.com/](https://www.phishtank.com/) <br/> |[<span data-ttu-id="41bc8-139">PhishTank preguntas más frecuentes</span><span class="sxs-lookup"><span data-stu-id="41bc8-139">PhishTank FAQ</span></span>](https://www.phishtank.com/faq.php) <br/> |

> [!NOTE]
> <span data-ttu-id="41bc8-p108">Si alguien de fuera de Office 365 no puede enviar mensajes a su cuenta de Office 365, puede ser su cuenta en la lista de remitentes bloqueados externo. Los usuarios externos a Office 365 pueden intentar quitar a sí mismos mediante el [portal de autoservicio de eliminación de la lista](https://docs.microsoft.com/en-us/office365/SecurityCompliance/use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis).</span><span class="sxs-lookup"><span data-stu-id="41bc8-p108">If someone outside Office 365 cannot send messages to your Office 365 account, their account may be on the external blocked senders list. Users outside Office 365 can try to remove themselves by using the [self-service delisting portal](https://docs.microsoft.com/en-us/office365/SecurityCompliance/use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis).</span></span> 

## <a name="for-more-information"></a><span data-ttu-id="41bc8-142">Más información</span><span class="sxs-lookup"><span data-stu-id="41bc8-142">For more information</span></span>

[<span data-ttu-id="41bc8-143">Responder a una cuenta de correo electrónico en peligro</span><span class="sxs-lookup"><span data-stu-id="41bc8-143">Responding to a compromised email account</span></span>](responding-to-a-compromised-email-account.md)

[<span data-ttu-id="41bc8-144">Configurar la directiva de correo no deseado saliente</span><span class="sxs-lookup"><span data-stu-id="41bc8-144">Configure the outbound spam policy</span></span>](configure-the-outbound-spam-policy.md)
  
[<span data-ttu-id="41bc8-145">Grupo de entrega de alto riesgo para mensajes salientes</span><span class="sxs-lookup"><span data-stu-id="41bc8-145">High-risk delivery pool for outbound messages</span></span>](high-risk-delivery-pool-for-outbound-messages.md)

  

  

