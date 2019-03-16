---
title: Quitar un usuario del portal de usuarios restringidos después de enviar correo no deseado
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 03/12/2019
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.exch.eac.ActionCenter.Restricted.Users.RestrictedUsers
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 712cfcc1-31e8-4e51-8561-b64258a8f1e5
ms.collection:
- M365-security-compliance
description: Si un usuario envía mensajes de correo electrónico de forma continua desde Office 365 que se clasifican como correo no deseado, se les restringirá el envío de mensajes adicionales.
ms.openlocfilehash: 61d52ad1f25dc3767ad51da5b3a217ace59303ce
ms.sourcegitcommit: 9918411c01e962d5c67d53dd30a8a9c28c547397
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2019
ms.locfileid: "30654557"
---
# <a name="removing-a-user-from-the-restricted-users-portal-after-sending-spam-email"></a><span data-ttu-id="b7cef-103">Quitar un usuario del portal de usuarios restringidos después de enviar correo no deseado</span><span class="sxs-lookup"><span data-stu-id="b7cef-103">Removing a user from the Restricted Users portal after sending spam email</span></span>

<span data-ttu-id="b7cef-104">Si un usuario envía mensajes de correo electrónico de forma continua desde Office 365 que se clasifican como correo no deseado, se les restringirá el envío de mensajes salientes más.</span><span class="sxs-lookup"><span data-stu-id="b7cef-104">If a user continuously sends emails from Office 365 that are classified as spam, they will be restricted from sending any more messages outbound.</span></span> <span data-ttu-id="b7cef-105">El usuario se mostrará en el servicio como un remitente de salida incorrecto y recibirá un informe de no entrega (NDR) que indica lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="b7cef-105">The user will be listed in the service as a bad outbound sender and will receive a Non-Delivery Report (NDR) that states:</span></span>

- <span data-ttu-id="b7cef-106">No se pudo entregar el mensaje porque no se reconoció como remitente válido.</span><span class="sxs-lookup"><span data-stu-id="b7cef-106">Your message couldn't be delivered because you weren't recognized as a valid sender.</span></span> <span data-ttu-id="b7cef-107">La razón más común es que se sospecha que su dirección de correo electrónico envía correo no deseado y ya no se le permite enviar mensajes fuera de la organización.</span><span class="sxs-lookup"><span data-stu-id="b7cef-107">The most common reason for this is that your email address is suspected of sending spam and it's no longer allowed to send messages outside of your organization.</span></span> <span data-ttu-id="b7cef-108">Póngase en contacto con su administrador de correo electrónico para obtener ayuda.</span><span class="sxs-lookup"><span data-stu-id="b7cef-108">Contact your email admin for assistance.</span></span> <span data-ttu-id="b7cef-109">El servidor remoto devolvió ' 550 5.1.8 acceso denegado, remitente de salida incorrecto '</span><span class="sxs-lookup"><span data-stu-id="b7cef-109">Remote Server returned '550 5.1.8 Access denied, bad outbound sender'</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="b7cef-110">¿Qué necesita saber antes de empezar?</span><span class="sxs-lookup"><span data-stu-id="b7cef-110">What do you need to know before you begin?</span></span>
<span data-ttu-id="b7cef-111"><a name="sectionSection0"> </a></span><span class="sxs-lookup"><span data-stu-id="b7cef-111"></span></span>

<span data-ttu-id="b7cef-112">Tiempo estimado para finalizar: 5 minutos</span><span class="sxs-lookup"><span data-stu-id="b7cef-112">Estimated time to complete: 5 minutes</span></span>
  
<span data-ttu-id="b7cef-113">Deberá tener asignados permisos antes de poder llevar a cabo este procedimiento o procedimientos.</span><span class="sxs-lookup"><span data-stu-id="b7cef-113">You need to be assigned permissions before you can perform this procedure or procedures.</span></span> <span data-ttu-id="b7cef-114">Para ver qué permisos necesita, consulte el tema "entrada contra correo electrónico no deseado" en el tema [permisos de características de Exchange Online](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx) .</span><span class="sxs-lookup"><span data-stu-id="b7cef-114">To see what permissions you need, see the "Anti-spam entry in the [Feature Permissions in Exchange Online](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx) topic.</span></span>

<span data-ttu-id="b7cef-115">El siguiente procedimiento también se puede llevar a cabo mediante PowerShell remoto.</span><span class="sxs-lookup"><span data-stu-id="b7cef-115">The following procedure can also be performed via remote PowerShell.</span></span> <span data-ttu-id="b7cef-116">Use el cmdlet Get-BlockedSenderAddress para obtener la lista de usuarios restringidos y Remove-BlockedSenderAddress para quitar la restricción.</span><span class="sxs-lookup"><span data-stu-id="b7cef-116">Use the Get-BlockedSenderAddress cmdlet to get the list of restricted users and Remove-BlockedSenderAddress to remove the restriction.</span></span> <span data-ttu-id="b7cef-117">Para obtener información sobre cómo usar Windows PowerShell para conectarse a Exchange Online, vea [Conexión a Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span><span class="sxs-lookup"><span data-stu-id="b7cef-117">To learn how to use Windows PowerShell to connect to Exchange Online, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span></span>

## <a name="remove-restrictions-for-a-blocked-office-365-email-account"></a><span data-ttu-id="b7cef-118">Quitar restricciones para una cuenta de correo electrónico de Office 365 no admitida</span><span class="sxs-lookup"><span data-stu-id="b7cef-118">Remove restrictions for a blocked Office 365 email account</span></span>

<span data-ttu-id="b7cef-119">Complete esta tarea en el centro de seguridad & cumplimiento (SCC) de Office 365.</span><span class="sxs-lookup"><span data-stu-id="b7cef-119">You complete this task in the Office 365 Security & Compliance Center (SCC).</span></span> <span data-ttu-id="b7cef-120">[Vaya al centro de cumplimiento de & de seguridad de Office 365](go-to-the-securitycompliance-center.md) para obtener más información sobre SCC.</span><span class="sxs-lookup"><span data-stu-id="b7cef-120">[Go to the Office 365 Security & Compliance Center](go-to-the-securitycompliance-center.md) for more details about SCC.</span></span> <span data-ttu-id="b7cef-121">Debe estar en el grupo de roles administración de la **organización** o **Administrador de seguridad** para poder realizar estas funciones.</span><span class="sxs-lookup"><span data-stu-id="b7cef-121">You need to be in the **Organization Management** or the **Security Administrator** role group in order to perform these functions.</span></span> <span data-ttu-id="b7cef-122">[Vaya a permisos en el centro de seguridad _AMP_ cumplimiento de Office 365](permissions-in-the-security-and-compliance-center.md) para obtener más información sobre los grupos de roles de SCC.</span><span class="sxs-lookup"><span data-stu-id="b7cef-122">[Go to Permissions in the Office 365 Security & Compliance Center](permissions-in-the-security-and-compliance-center.md) for more details about SCC role groups.</span></span>

1. <span data-ttu-id="b7cef-123">Con una cuenta profesional o educativa con privilegios de administrador global de Office 365, inicie sesión en el centro de seguridad y cumplimiento de Office 365 y, en la lista de la izquierda, expanda **Administración de amenazas**, elija **revisar**y, a continuación, seleccione **restringido Usuarios**de.</span><span class="sxs-lookup"><span data-stu-id="b7cef-123">Using a work or school account that has Office 365 global administrator privileges, sign into the Office 365 Security and Compliance Center and in the list on the left, expand **Threat Management**, choose **Review**, and then choose **Restricted Users**.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="b7cef-124">Para ir directamente a la página **usuarios restringidos** (anteriormente denominada centro de actividades) en el centro &amp; de seguridad y cumplimiento, use esta dirección URL: >[https://protection.office.com/#/restrictedusers](https://protection.office.com/?hash=/restrictedusers)</span><span class="sxs-lookup"><span data-stu-id="b7cef-124">To go directly to the **Restricted Users** page (formerly known as the Action Center) in the Security &amp; Compliance Center, use this URL: > [https://protection.office.com/#/restrictedusers](https://protection.office.com/?hash=/restrictedusers)</span></span>

2. <span data-ttu-id="b7cef-125">Esta página contendrá la lista de usuarios que han sido bloqueados para enviar correo a fuera de la organización.</span><span class="sxs-lookup"><span data-stu-id="b7cef-125">This page will contain the list of users that have been blocked from sending mail to outside of your organization.</span></span>  <span data-ttu-id="b7cef-126">Busque el usuario para el que desea quitar restricciones y, a continuación, haga clic en **desbloquear**.</span><span class="sxs-lookup"><span data-stu-id="b7cef-126">Find the user you wish to remove restrictions on and then click on **Unblock**.</span></span>

3. <span data-ttu-id="b7cef-127">Una reactivación irá a los detalles sobre la cuenta cuyo envío está restringido.</span><span class="sxs-lookup"><span data-stu-id="b7cef-127">A fly-out will go into the details about the account whose sending is restricted.</span></span> <span data-ttu-id="b7cef-128">Debe seguir las recomendaciones para asegurarse de que está llevando a cabo las acciones adecuadas en caso de que la cuenta se vea en realidad.</span><span class="sxs-lookup"><span data-stu-id="b7cef-128">You should go through the recommendations to ensure you're taking the proper actions in case the account is actually compromised.</span></span> <span data-ttu-id="b7cef-129">Haga clic en **siguiente** cuando haya terminado.</span><span class="sxs-lookup"><span data-stu-id="b7cef-129">Click **Next** when done.</span></span>

4. <span data-ttu-id="b7cef-130">La siguiente pantalla tiene recomendaciones para ayudar a evitar el futuro compromiso.</span><span class="sxs-lookup"><span data-stu-id="b7cef-130">The next screen has recommendations to help prevent future compromise.</span></span> <span data-ttu-id="b7cef-131">La habilitación de multi-factor Authentication (MFA) y el cambio de contraseñas son una buena defensa.</span><span class="sxs-lookup"><span data-stu-id="b7cef-131">Enabling multi-factor authentication (MFA) and changing the passwords are a good defense.</span></span> <span data-ttu-id="b7cef-132">Haga clic en **desbloquear el usuario** cuando haya terminado.</span><span class="sxs-lookup"><span data-stu-id="b7cef-132">Click **Unblock user** when done.</span></span>

5. <span data-ttu-id="b7cef-133">Haga clic en **sí** para confirmar el cambio.</span><span class="sxs-lookup"><span data-stu-id="b7cef-133">Click **Yes** to confirm the change.</span></span>

    > [!NOTE]
    > <span data-ttu-id="b7cef-134">Las restricciones pueden tardar hasta 30 minutos en quitarse.</span><span class="sxs-lookup"><span data-stu-id="b7cef-134">It may take up to 30 minutes before restrictions are removed.</span></span> 

## <a name="making-sure-admins-are-alerted-when-this-happens"></a><span data-ttu-id="b7cef-135">Asegurarse de que se advierte a los administradores cuando esto ocurre</span><span class="sxs-lookup"><span data-stu-id="b7cef-135">Making sure admins are alerted when this happens</span></span>

<span data-ttu-id="b7cef-136">Los administradores de espacios empresariales también recibirán una alerta que indica que se ha restringido el envío de más mensajes salientes al usuario.</span><span class="sxs-lookup"><span data-stu-id="b7cef-136">The tenant admins will also receive an alert stating that the user has been restricted from sending any more outbound messages.</span></span> <span data-ttu-id="b7cef-137">Se trata de una alerta predeterminada que se proporciona para todos los inquilinos y que aparece en la página directivas de alerta de SCC, titulada "el usuario restringió el envío de correo electrónico".</span><span class="sxs-lookup"><span data-stu-id="b7cef-137">It is a default alert that is provided for all tenants and is listed in the SCC Alert policies page, titled "User restricted from sending email".</span></span> <span data-ttu-id="b7cef-138">Vaya a [directivas de alerta en el centro de seguridad _AMP_ cumplimiento de Office 365](https://docs.microsoft.com/en-us/office365/securitycompliance/alert-policies) para obtener más información sobre la alerta.</span><span class="sxs-lookup"><span data-stu-id="b7cef-138">Go to [Alert policies in the Office 365 Security & Compliance Center](https://docs.microsoft.com/en-us/office365/securitycompliance/alert-policies) for more information on the alert.</span></span>

## <a name="for-more-information"></a><span data-ttu-id="b7cef-139">Para obtener más información</span><span class="sxs-lookup"><span data-stu-id="b7cef-139">For more information</span></span>

[<span data-ttu-id="b7cef-140">Responder a una cuenta de correo electrónico en peligro</span><span class="sxs-lookup"><span data-stu-id="b7cef-140">Responding to a compromised email account</span></span>](responding-to-a-compromised-email-account.md)

[<span data-ttu-id="b7cef-141">Descripción del usuario restringido del envío de alertas de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="b7cef-141">Understanding the User restricted from sending email alert</span></span>](https://docs.microsoft.com/en-us/office365/securitycompliance/alert-policies)

[<span data-ttu-id="b7cef-142">Grupo de entrega de alto riesgo para mensajes salientes</span><span class="sxs-lookup"><span data-stu-id="b7cef-142">High-risk delivery pool for outbound messages</span></span>](high-risk-delivery-pool-for-outbound-messages.md)

[<span data-ttu-id="b7cef-143">Permisos en el centro de seguridad & cumplimiento de Office 365</span><span class="sxs-lookup"><span data-stu-id="b7cef-143">Permissions in the Office 365 Security & Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)
