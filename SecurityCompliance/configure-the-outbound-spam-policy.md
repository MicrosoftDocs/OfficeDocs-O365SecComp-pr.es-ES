---
title: Configurar notificaciones de directivas de correo no deseado salientes en Office 365
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 11/10/2016
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a44764e9-a5d2-4c67-8888-e7fb871c17c7
ms.collection:
- M365-security-compliance
description: Los administradores pueden aprender a modificar la configuración de notificaciones para detecciones de correo no deseado de salida en Office 365.
ms.openlocfilehash: c48b6cd634417a00040fb5479313782b44f6aa8d
ms.sourcegitcommit: 81b3bff27bc60235a38004c5b0297ac454331b25
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2019
ms.locfileid: "36822520"
---
# <a name="configure-outbound-spam-policy-notifications-in-office-365"></a><span data-ttu-id="94b0a-103">Configurar notificaciones de directivas de correo no deseado salientes en Office 365</span><span class="sxs-lookup"><span data-stu-id="94b0a-103">Configure outbound spam policy notifications in Office 365</span></span>

<span data-ttu-id="94b0a-104">El filtrado de correo no deseado saliente siempre está habilitado si utiliza el servicio para enviar correo electrónico saliente, lo que protege a las organizaciones que utilizan el servicio y sus destinatarios.</span><span class="sxs-lookup"><span data-stu-id="94b0a-104">Outbound spam filtering is always enabled if you use the service for sending outbound email, thereby protecting organizations using the service and their intended recipients.</span></span> <span data-ttu-id="94b0a-105">De manera similar al filtrado entrante, el filtrado de correo no deseado saliente está compuesto por el filtro de conexión y el filtro de contenido; no obstante, no es posible configurar el filtrado saliente.</span><span class="sxs-lookup"><span data-stu-id="94b0a-105">Similar to inbound filtering, outbound spam filtering is comprised of connection filtering and content filtering, however the outbound filter settings are not configurable.</span></span> <span data-ttu-id="94b0a-106">Si se determina que un mensaje saliente es correo no deseado, este se enruta mediante el grupo de entrega de mayor riesgo, que reduce la probabilidad de que el grupo de IP saliente normal se agregue a una lista de bloqueo.</span><span class="sxs-lookup"><span data-stu-id="94b0a-106">If an outbound message is determined to be spam, it is routed through the higher risk delivery pool, which reduces the probability of the normal outbound-IP pool being added to a block list.</span></span> <span data-ttu-id="94b0a-107">Si un cliente continúa enviando correo no deseado saliente mediante el servicio, su envío de mensajes se bloqueará.</span><span class="sxs-lookup"><span data-stu-id="94b0a-107">If a customer continues to send outbound spam through the service, they will be blocked from sending messages.</span></span>

<span data-ttu-id="94b0a-108">Aunque no puede deshabilitar ni cambiar el filtrado de correo no deseado saliente, puede configurar las siguientes opciones de notificación de correo no deseado saliente:</span><span class="sxs-lookup"><span data-stu-id="94b0a-108">Although you can't disable or change outbound spam filtering, you can configure the following outbound spam notification settings:</span></span>

- <span data-ttu-id="94b0a-109">**Enviar copias de mensajes sospechosos**: estos mensajes se marcan como correo no deseado (independientemente de la clasificación de SCL) y el filtro no los rechaza, pero se redirigen a través del grupo de entrega de mayor riesgo.</span><span class="sxs-lookup"><span data-stu-id="94b0a-109">**Send copies of suspicious messages**: These messages are marked as spam (regardless of the SCL rating) and are not rejected by the filter, but are routed through the higher risk delivery pool.</span></span> <span data-ttu-id="94b0a-110">Puede usar el centro de administración de Exchange (EAC) o \*\* \*\*\* los cmdlets-HostedOutboundSpamFilterPolicy en Exchange Online PowerShell o Exchange Online Protection PowerShell para especificar destinatarios adicionales para estos mensajes detectados.</span><span class="sxs-lookup"><span data-stu-id="94b0a-110">You can use the Exchange admin center (EAC) or the **\*-HostedOutboundSpamFilterPolicy** cmdlets in Exchange Online PowerShell or Exchange Online Protection PowerShell to specify addition recipients for these detected messages.</span></span> <span data-ttu-id="94b0a-111">Tenga en cuenta que los destinatarios se agregan como destinatarios **CCO** (los campos **desde** y **para** son el remitente y el destinatario originales).</span><span class="sxs-lookup"><span data-stu-id="94b0a-111">Note that the recipients are added as **Bcc** recipients (the **From** and **To** fields are the original sender and recipient).</span></span>

- <span data-ttu-id="94b0a-112">**Enviar notificaciones cuando se bloquea un remitente**: cuando hay una cantidad significativa de correo no deseado procedente de un usuario en particular, el usuario está deshabilitado para enviar mensajes de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="94b0a-112">**Send notifications when a sender is blocked**: When a significant amount of spam is coming from a particular user, the user is disabled from sending email messages.</span></span> <span data-ttu-id="94b0a-113">Los administradores reciben una notificación de forma predeterminada, pero puede usar el **usuario restringido del envío de** la [Directiva de alerta](alert-policies.md) de correo electrónico en el centro de cumplimiento de & de seguridad de Office 365 para configurar destinatarios de notificaciones adicionales.</span><span class="sxs-lookup"><span data-stu-id="94b0a-113">Admins are notified by default, but you can use the **User restricted from sending email** [alert policy](alert-policies.md) in the Office 365 Security & Compliance Center to configure additional notification recipients.</span></span>

  <span data-ttu-id="94b0a-114">Para ver el aspecto que tiene esta notificación, véase [Notificación de muestra cuando se bloquea a un remitente para enviar correo no deseado de salida](sample-notification-when-a-sender-is-blocked-sending-outbound-spam.md).</span><span class="sxs-lookup"><span data-stu-id="94b0a-114">To see what this notification looks like, see [Sample notification when a sender is blocked sending outbound spam](sample-notification-when-a-sender-is-blocked-sending-outbound-spam.md).</span></span> <span data-ttu-id="94b0a-115">Para obtener información sobre cómo volver a habilitar a un usuario, consulte [Removing a user, domain, or IP address from a block list after sending spam email](http://technet.microsoft.com/library/712cfcc1-31e8-4e51-8561-b64258a8f1e5.aspx).</span><span class="sxs-lookup"><span data-stu-id="94b0a-115">For information about getting re-enabled, see [Removing a user, domain, or IP address from a block list after sending spam email](http://technet.microsoft.com/library/712cfcc1-31e8-4e51-8561-b64258a8f1e5.aspx).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="94b0a-116">¿Qué necesita saber antes de comenzar?</span><span class="sxs-lookup"><span data-stu-id="94b0a-116">What do you need to know before you begin?</span></span>

- <span data-ttu-id="94b0a-117">Tiempo estimado para finalizar: 5 minutos</span><span class="sxs-lookup"><span data-stu-id="94b0a-117">Estimated time to complete: 5 minutes</span></span>

- <span data-ttu-id="94b0a-118">Para abrir el Centro de seguridad y cumplimiento, vea [Ir al Centro de seguridad y cumplimiento de Office 365](go-to-the-securitycompliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="94b0a-118">To open the Security & Compliance Center, see [Go to the Office 365 Security & Compliance Center](go-to-the-securitycompliance-center.md).</span></span>

- <span data-ttu-id="94b0a-119">Para abrir el EAC, consulte [centro de administración de Exchange en Exchange Online](https://docs.microsoft.com/Exchange/exchange-admin-center) o [Exchange admin Center in Exchange Online Protection](exchange-admin-center-in-exchange-online-protection-eop.md).</span><span class="sxs-lookup"><span data-stu-id="94b0a-119">To open the EAC, see [Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/exchange-admin-center) or [Exchange admin center in Exchange Online Protection](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="94b0a-120">Para abrir PowerShell de Exchange Online, vea [conectarse a Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="94b0a-120">To open Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="94b0a-121">Para abrir PowerShell de Exchange Online Protection, vea [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="94b0a-121">To open Exchange Online Protection PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="94b0a-122">La cuenta debe tener permisos asignados para poder realizar este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="94b0a-122">Your account needs to be assigned permissions before you can perform this procedure.</span></span> <span data-ttu-id="94b0a-123">Para ver qué permisos necesita, consulte la entrada de la función "Administrar alertas" en [permisos en el centro de seguridad & cumplimiento de Office 365](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="94b0a-123">To see what permissions you need, see the "Manage Alerts" role entry in [Permissions in the Office 365 Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="use-the-eac-to-configure-additional-recipients-for-outbound-spam-messages"></a><span data-ttu-id="94b0a-124">Usar el EAC para configurar destinatarios adicionales para los mensajes de correo no deseado saliente</span><span class="sxs-lookup"><span data-stu-id="94b0a-124">Use the EAC to configure additional recipients for outbound spam messages</span></span>

1. <span data-ttu-id="94b0a-125">En el EAC, vaya a **protección** \> **contra correo no deseado**de protección.</span><span class="sxs-lookup"><span data-stu-id="94b0a-125">In the EAC, go to **Protection** \> **Outbound spam**.</span></span>

2. <span data-ttu-id="94b0a-126">Seleccione la Directiva denominada **predeterminada**y, a continuación, haga clic](media/ITPro-EAC-EditIcon.png)en **Editar** ![icono de edición.</span><span class="sxs-lookup"><span data-stu-id="94b0a-126">Select the policy named **Default**, and then click **Edit** ![Edit icon](media/ITPro-EAC-EditIcon.png).</span></span>

3. <span data-ttu-id="94b0a-127">En la página de propiedades que se abre, compruebe que la pestaña **preferencias de correo no deseado saliente** está seleccionada y, a continuación, configure las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="94b0a-127">In the properties page that opens, verify that the **Outbound spam preferences** tab is selected, and then configure the following setting:</span></span>

   <span data-ttu-id="94b0a-128">**Envíe una copia de todos los mensajes de correo electrónico saliente sospechosos a las siguientes direcciones o**direcciones de correo electrónico: Active la casilla y escriba las direcciones de correo electrónico de uno o más administradores que se deben agregar al campo **CCO** de los mensajes detectados.</span><span class="sxs-lookup"><span data-stu-id="94b0a-128">**Send a copy of all suspicious outbound email messages to the following email address or addresses**: Select the check box and enter the email addresses of one or more administrators who should be added to the **Bcc** field of detected messages.</span></span> <span data-ttu-id="94b0a-129">Separe varias direcciones de correo electrónico con un punto y coma (;).</span><span class="sxs-lookup"><span data-stu-id="94b0a-129">Separate multiple email addresses with a semicolon ( ; ).</span></span>

   <span data-ttu-id="94b0a-130">Cuando haya terminado, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="94b0a-130">When you're finished, click **Save**.</span></span>

### <a name="use-exchange-online-powershell-or-exchange-online-protection-powershell-to-configure-additional-recipients-for-outbound-spam-messages"></a><span data-ttu-id="94b0a-131">Usar Exchange Online PowerShell o Exchange Online Protection PowerShell para configurar destinatarios adicionales para los mensajes de correo no deseado salientes</span><span class="sxs-lookup"><span data-stu-id="94b0a-131">Use Exchange Online PowerShell or Exchange Online Protection PowerShell to configure additional recipients for outbound spam messages</span></span>

<span data-ttu-id="94b0a-132">Para habilitar y configurar destinatarios adicionales para los mensajes de correo no deseado salientes, use la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="94b0a-132">To enable and configure additional recipients for outbound spam messages, use the following syntax:</span></span>

```PowerShell
Set-HostedOutboundSpamFilterPolicy -Identity Default -BccSuspiciousOutboundMail $true -BccSuspiciousOutboundAdditionalRecipients <recipients>
```

- <span data-ttu-id="94b0a-133">Para especificar los destinatarios que sobrescriben todos los valores existentes, use `emailaddress1,emailaddress2,...emailaddressN`la sintaxis.</span><span class="sxs-lookup"><span data-stu-id="94b0a-133">To specify recipients that overwrite all existing values, use the syntax `emailaddress1,emailaddress2,...emailaddressN`.</span></span>

- <span data-ttu-id="94b0a-134">Para agregar o quitar selectivamente los destinatarios sin que ello afecte a las demás entradas `@{Add="\<emailaddress1\>","\<emailaddress2\>"...; Remove="\<emailaddress1\>","\<emailaddress2\>"...}`, use la sintaxis.</span><span class="sxs-lookup"><span data-stu-id="94b0a-134">To selectively add or remove recipients without affecting the other entries, use the syntax `@{Add="\<emailaddress1\>","\<emailaddress2\>"...; Remove="\<emailaddress1\>","\<emailaddress2\>"...}`.</span></span>

<span data-ttu-id="94b0a-135">En este ejemplo se habilitan y configuran chris@contoso.com, laura@contoso.com y julia@contoso.com como destinatarios CCO para los mensajes de correo no deseado saliente.</span><span class="sxs-lookup"><span data-stu-id="94b0a-135">This example enables and configures chris@contoso.com, laura@contoso.com and julia@contoso.com as Bcc recipients for outbound spam messages.</span></span>

```PowerShell
Set-HostedOutboundSpamFilterPolicy -Identity Default -BccSuspiciousOutboundMail $true -BccSuspiciousOutboundAdditionalRecipients chris@contoso.com,laura@contoso.com,julia@contoso.com
```

<span data-ttu-id="94b0a-136">En este ejemplo se agrega michelle@contoso.com como un destinatario de CCO adicional.</span><span class="sxs-lookup"><span data-stu-id="94b0a-136">This example adds michelle@contoso.com as an additional Bcc recipient.</span></span>

```PowerShell
Set-HostedOutboundSpamFilterPolicy -Identity Default -BccSuspiciousOutboundAdditionalRecipients @{Add=michelle@contoso.com}
```

<span data-ttu-id="94b0a-137">En este ejemplo se quitan chris@contoso.com y julia@contoso.com de la lista de destinatarios CCO.</span><span class="sxs-lookup"><span data-stu-id="94b0a-137">This example removes chris@contoso.com and julia@contoso.com from the list of Bcc recipients.</span></span>

```PowerShell
Set-HostedOutboundSpamFilterPolicy -Identity Default -BccSuspiciousOutboundAdditionalRecipients @{Remove='chris@contoso.com','julia@contoso.com'}
```

<span data-ttu-id="94b0a-138">Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [set-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedoutboundspamfilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="94b0a-138">For detailed syntax and parameter information, see [Set-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedoutboundspamfilterpolicy).</span></span>

<span data-ttu-id="94b0a-139">**Nota**: Ejecute el comando `Get-HostedOutboundSpamFilterPolicy | Format-List` para ver los valores actuales de las propiedades *BccSuspiciousOutboundMail* y *BccSuspiciousOutboundAdditionalRecipients* .</span><span class="sxs-lookup"><span data-stu-id="94b0a-139">**Note**: Run the command `Get-HostedOutboundSpamFilterPolicy | Format-List` to see the current values of the *BccSuspiciousOutboundMail* and *BccSuspiciousOutboundAdditionalRecipients* properties.</span></span>

## <a name="use-the-security--compliance-center-to-configure-notifications-when-a-sender-is-blocked"></a><span data-ttu-id="94b0a-140">Usar el centro de seguridad & cumplimiento para configurar las notificaciones cuando se bloquea un remitente</span><span class="sxs-lookup"><span data-stu-id="94b0a-140">Use the Security & Compliance Center to configure notifications when a sender is blocked</span></span>

1. <span data-ttu-id="94b0a-141">En el centro de seguridad & cumplimiento, vaya a **directivas de alerta**de **alertas** \> .</span><span class="sxs-lookup"><span data-stu-id="94b0a-141">In the Security & Compliance Center, go to **Alerts** \> **Alert Policies**.</span></span>

2. <span data-ttu-id="94b0a-142">Busque y seleccione la Directiva denominada **usuario con restricción de envío de correo electrónico**.</span><span class="sxs-lookup"><span data-stu-id="94b0a-142">Find and select the policy named **User restricted from sending email**.</span></span>

3. <span data-ttu-id="94b0a-143">En la volando que se abre, haga clic en **Editar Directiva**.</span><span class="sxs-lookup"><span data-stu-id="94b0a-143">In the fly out that opens, click **Edit policy**.</span></span>

4. <span data-ttu-id="94b0a-144">En la página **Editar destinatarios** que aparece, configure las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="94b0a-144">In the **Edit recipients** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="94b0a-145">**Enviar notificaciones por correo electrónico**: **Compruebe que está** seleccionada.</span><span class="sxs-lookup"><span data-stu-id="94b0a-145">**Send email notifications**: Verify that **On** is selected.</span></span>

   - <span data-ttu-id="94b0a-146">**Destinatarios de correo electrónico**: de forma predeterminada **TenantAdmins** es el único valor aquí.</span><span class="sxs-lookup"><span data-stu-id="94b0a-146">**Email recipients**: By default **TenantAdmins** is the only value here.</span></span> <span data-ttu-id="94b0a-147">Para agregar más destinatarios, haga clic en un punto vacío en este cuadro, empiece a escribir el destinatario y seleccione el destinatario cuando se resuelva el nombre.</span><span class="sxs-lookup"><span data-stu-id="94b0a-147">To add additional recipients, click in an empty spot in this box, start typing the recipient, and select the recipient when their name resolves.</span></span> <span data-ttu-id="94b0a-148">Para quitar destinatarios, haga clic en la **X** junto a sus nombres.</span><span class="sxs-lookup"><span data-stu-id="94b0a-148">To remove recipients, click on the **X** next to their names.</span></span>

   - <span data-ttu-id="94b0a-149">**Límite de notificación diario**: el valor predeterminado es **sin límite**, pero puede configurar varios límites entre 1 y 200.</span><span class="sxs-lookup"><span data-stu-id="94b0a-149">**Daily notification limit**: The default value is **No limit**, but you can configure various limits from 1 to 200.</span></span>

   <span data-ttu-id="94b0a-150">Cuando haya terminado, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="94b0a-150">When you're finished, click **Save**.</span></span>

## <a name="for-more-information"></a><span data-ttu-id="94b0a-151">Más información</span><span class="sxs-lookup"><span data-stu-id="94b0a-151">For more information</span></span>

[<span data-ttu-id="94b0a-152">Grupo de entrega de alto riesgo para mensajes salientes</span><span class="sxs-lookup"><span data-stu-id="94b0a-152">High-risk delivery pool for outbound messages</span></span>](high-risk-delivery-pool-for-outbound-messages.md)

[<span data-ttu-id="94b0a-153">Preguntas más frecuentes sobre protección contra correo no deseado</span><span class="sxs-lookup"><span data-stu-id="94b0a-153">Anti-spam protection FAQ</span></span>](anti-spam-protection-faq.md)
