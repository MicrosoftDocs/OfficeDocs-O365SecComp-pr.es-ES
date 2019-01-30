---
title: Quitar un usuario, un dominio o una dirección IP de una lista de bloqueados después de enviar correo no deseado
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 11/01/2018
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
ms.openlocfilehash: 6f6f4504a9c79463aadc21f2eaeadcd769e8b151
ms.sourcegitcommit: 03b9221d9885bcde1cdb5df2c2dc5d835802d299
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2019
ms.locfileid: "29614404"
---
# <a name="removing-a-user-domain-or-ip-address-from-a-block-list-after-sending-spam-email"></a><span data-ttu-id="21d79-103">Quitar un usuario, un dominio o una dirección IP de una lista de bloqueados después de enviar correo no deseado</span><span class="sxs-lookup"><span data-stu-id="21d79-103">Removing a user, domain, or IP address from a block list after sending spam email</span></span>

<span data-ttu-id="21d79-p101">Si un usuario envía continuamente mensajes de correo electrónico de Office 365 que se clasifica como correo no deseado, se bloqueará de enviar más mensajes. El usuario se mostrarán en el servicio como un remitente de salida incorrecto y recibirá un informe de no entrega (NDR) que indica:</span><span class="sxs-lookup"><span data-stu-id="21d79-p101">If a user continuously sends email messages from Office 365 that is classified as spam, they will be blocked from sending any more messages. The user will be listed in the service as a bad outbound sender and will receive a Non-Delivery Report (NDR) that states:</span></span>

- <span data-ttu-id="21d79-p102">No se pudo entregar el mensaje porque no se han reconocido como remitente válido. La razón más común de esto es que su dirección de correo electrónico es sospechosos de enviar spam y que ya no se permite para enviar mensajes de fuera de la organización. Para obtener ayuda, póngase en contacto con el Administrador de correo electrónico.  Servidor remoto devolvió '550 5.1.8 acceso denegado, remitente saliente incorrecta'</span><span class="sxs-lookup"><span data-stu-id="21d79-p102">Your message couldn't be delivered because you weren't recognized as a valid sender. The most common reason for this is that your email address is suspected of sending spam and it's no longer allowed to send messages outside of your organization. Contact your email admin for assistance.  Remote Server returned '550 5.1.8 Access denied, bad outbound sender'</span></span>

<span data-ttu-id="21d79-110">Los administradores de inquilinos también recibirá una alerta que indica que el usuario ha restringido de envío de todos los mensajes salientes más.</span><span class="sxs-lookup"><span data-stu-id="21d79-110">The tenant admins will also receive an alert stating that the user has been restricted from sending any more outbound messages.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="21d79-111">¿Qué necesita saber antes de comenzar?</span><span class="sxs-lookup"><span data-stu-id="21d79-111">What do you need to know before you begin?</span></span>
<span data-ttu-id="21d79-112"><a name="sectionSection0"> </a></span><span class="sxs-lookup"><span data-stu-id="21d79-112"></span></span>

<span data-ttu-id="21d79-113">Tiempo estimado para finalizar: 5 minutos</span><span class="sxs-lookup"><span data-stu-id="21d79-113">Estimated time to complete: 5 minutes</span></span>
  
<span data-ttu-id="21d79-p103">Debe tener asignados los permisos puede llevar a cabo estos procedimientos. Para ver qué permisos necesita, vea la entrada"contra correo no deseado en el tema [Feature Permissions in Exchange Online](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx) .</span><span class="sxs-lookup"><span data-stu-id="21d79-p103">You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Anti-spam entry in the [Feature Permissions in Exchange Online](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx) topic.</span></span>

<span data-ttu-id="21d79-p104">El siguiente procedimiento también se puede realizar mediante PowerShell remoto. Use el cmdlet Get-BlockedSenderAddress para obtener la lista de usuarios restringidos y Remove-BlockedSenderAddress para quitar la restricción. Para obtener información sobre cómo usar Windows PowerShell para conectarse a Exchange Online, vea [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span><span class="sxs-lookup"><span data-stu-id="21d79-p104">The following procedure can also be performed via remote PowerShell. Use the Get-BlockedSenderAddress cmdlet to get the list of restricted users and Remove-BlockedSenderAddress to remove the restriction. To learn how to use Windows PowerShell to connect to Exchange Online, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span></span>

## <a name="remove-restrictions-for-a-blocked-office-365-email-account"></a><span data-ttu-id="21d79-119">Quitar restricciones para una cuenta de correo electrónico de Office 365 bloqueada</span><span class="sxs-lookup"><span data-stu-id="21d79-119">Remove restrictions for a blocked Office 365 email account</span></span>

<span data-ttu-id="21d79-p105">Complete esta tarea en el centro de cumplimiento (SCC) & de seguridad de Office 365. Para obtener más información acerca de control de código fuente, [vaya a la & centro de cumplimiento de seguridad de Office 365](go-to-the-securitycompliance-center.md) . Debe estar en la **Administración de la organización** o el grupo de roles de **Administrador de seguridad** con el fin de realizar estas funciones. Para obtener más información acerca de los grupos de funciones de control de código fuente, [vaya a permisos en el centro de cumplimiento de seguridad de Office 365 &](permissions-in-the-security-and-compliance-center.md) .</span><span class="sxs-lookup"><span data-stu-id="21d79-p105">You complete this task in the Office 365 Security & Compliance Center (SCC). [Go to the Office 365 Security & Compliance Center](go-to-the-securitycompliance-center.md) for more details about SCC. You need to be in the **Organization Management** or the **Security Administrator** role group in order to perform these functions. [Go to Permissions in the Office 365 Security & Compliance Center](permissions-in-the-security-and-compliance-center.md) for more details about SCC role groups.</span></span>

1. <span data-ttu-id="21d79-124">Utilizando una cuenta de trabajo o escuela que tiene privilegios de administrador global de Office 365, inicie sesión en el centro de cumplimiento y seguridad de Office 365 y en la lista de la izquierda, expanda **Administración de amenaza**, elija la **revisión**y, a continuación, elija **restringidos Los usuarios**.</span><span class="sxs-lookup"><span data-stu-id="21d79-124">Using a work or school account that has Office 365 global administrator privileges, sign into the Office 365 Security and Compliance Center and in the list on the left, expand **Threat Management**, choose **Review**, and then choose **Restricted Users**.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="21d79-125">Para ir directamente a la página **Usuarios restringidos** (anteriormente conocida como el centro de acción) en la seguridad &amp; centro de cumplimiento, use esta dirección URL: >[https://protection.office.com/?hash=/restrictedusers](https://protection.office.com/?hash=/restrictedusers)</span><span class="sxs-lookup"><span data-stu-id="21d79-125">To go directly to the **Restricted Users** page (formerly known as the Action Center) in the Security &amp; Compliance Center, use this URL: > [https://protection.office.com/?hash=/restrictedusers](https://protection.office.com/?hash=/restrictedusers)</span></span>

2. <span data-ttu-id="21d79-p106">Esta página contendrá la lista de usuarios que se han bloqueado de envío de correo a fuera de la organización.  Busque el usuario que desea quitar restricciones en y, a continuación, haga clic en **desbloquear**.</span><span class="sxs-lookup"><span data-stu-id="21d79-p106">This page will contain the list of users that have been blocked from sending mail to outside of your organization.  Find the user you wish to remove restrictions on and then click on **Unblock**.</span></span>

3. <span data-ttu-id="21d79-128">Haga clic en **Sí** para confirmar el cambio.</span><span class="sxs-lookup"><span data-stu-id="21d79-128">Click **Yes** to confirm the change.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="21d79-p107">Hay un límite para el número de veces que una cuenta puede ser desbloqueada por el Administrador de inquilinos. Si se ha superado el límite de un usuario, aparece un mensaje de error. A continuación, debe ponerse en contacto con soporte técnico para desbloquear el usuario.</span><span class="sxs-lookup"><span data-stu-id="21d79-p107">There's a limit to the number of times that an account can be unblocked by the tenant admin. If the limit for a user has been exceeded, an error message appears. You will then need to contact Support to unblock the user.</span></span></br></br> <span data-ttu-id="21d79-131">Puede tardar hasta 1 hora antes de que el usuario está desbloqueado.</span><span class="sxs-lookup"><span data-stu-id="21d79-131">It may take up to 1 hour before the user is unblocked.</span></span>
  
## <a name="third-party-block-lists"></a><span data-ttu-id="21d79-132">Listas de bloqueados de terceros</span><span class="sxs-lookup"><span data-stu-id="21d79-132">Third-party block lists</span></span>

<span data-ttu-id="21d79-p108">Exchange Online Protection también usa listas de bloqueo de otro fabricante para ayudar a tomar decisiones de filtrado de spam. Los usuarios, sitios, dominios y direcciones IP pueden agregarse a bloquear listas solo para que aparezca en un mensaje de spam. Como la administración de Office 365, debe intentar obtener estos objetos quitado de los proveedores de la lista de terceros si éstos pertenecen a usted.</span><span class="sxs-lookup"><span data-stu-id="21d79-p108">Exchange Online Protection also uses third-party block lists to help make decisions in spam filtering. Users, websites, domains, and IP addresses can be added to block lists just for appearing in a spam message. As the Office 365 admin, you should try to get these objects removed from the third-party list providers if they belong to you.</span></span>

> [!NOTE]
> <span data-ttu-id="21d79-p109">Si alguien de fuera de Office 365 no puede enviar mensajes a su cuenta de Office 365, puede ser su cuenta en la lista de remitentes bloqueados externo. Los usuarios externos a Office 365 pueden intentar quitar a sí mismos mediante el [portal de autoservicio de eliminación de la lista](https://docs.microsoft.com/en-us/office365/SecurityCompliance/use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis).</span><span class="sxs-lookup"><span data-stu-id="21d79-p109">If someone outside Office 365 cannot send messages to your Office 365 account, their account may be on the external blocked senders list. Users outside Office 365 can try to remove themselves by using the [self-service delisting portal](https://docs.microsoft.com/en-us/office365/SecurityCompliance/use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis).</span></span> 

## <a name="for-more-information"></a><span data-ttu-id="21d79-138">Más información</span><span class="sxs-lookup"><span data-stu-id="21d79-138">For more information</span></span>

[<span data-ttu-id="21d79-139">Responder a una cuenta de correo electrónico en peligro</span><span class="sxs-lookup"><span data-stu-id="21d79-139">Responding to a compromised email account</span></span>](responding-to-a-compromised-email-account.md)

[<span data-ttu-id="21d79-140">Configurar la directiva de correo no deseado saliente</span><span class="sxs-lookup"><span data-stu-id="21d79-140">Configure the outbound spam policy</span></span>](configure-the-outbound-spam-policy.md)
  
[<span data-ttu-id="21d79-141">Grupo de entrega de alto riesgo para mensajes salientes</span><span class="sxs-lookup"><span data-stu-id="21d79-141">High-risk delivery pool for outbound messages</span></span>](high-risk-delivery-pool-for-outbound-messages.md)

[<span data-ttu-id="21d79-142">Permisos en el centro de cumplimiento de normas de & de seguridad de Office 365</span><span class="sxs-lookup"><span data-stu-id="21d79-142">Permissions in the Office 365 Security & Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)

  

