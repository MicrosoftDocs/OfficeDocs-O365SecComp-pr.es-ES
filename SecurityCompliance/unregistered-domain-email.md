---
title: Correo electrónico de dominio no registrado
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 10/17/2018
ms.audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
description: Si envía un gran volumen de correo electrónico de dominio no registrado, corre el riesgo de que se bloquee el correo electrónico. Lea este artículo para obtener más información.
ms.openlocfilehash: 8120bd147da2a7aab41ae14c444d2fe57242199e
ms.sourcegitcommit: 686bc9a8f7a7b6810a096f07d36751d10d334409
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/26/2019
ms.locfileid: "30276230"
---
# <a name="unregistered-domain-email-what-you-need-to-know"></a><span data-ttu-id="a0957-104">Correo electrónico de dominio no registrado: lo que debe saber</span><span class="sxs-lookup"><span data-stu-id="a0957-104">Unregistered Domain Email: What you need to know</span></span>

<span data-ttu-id="a0957-p102">Office 365 permite que los inquilinos retransmitan algunos mensajes a través de Exchange Online Protection (EOP). Un ejemplo admitido sería cuando los usuarios tienen un buzón de correo de Office 365 y alguien externo les envía correos electrónicos pero el reenvío de correo electrónico se configura de modo que vuelva al buzón externo del usuario. Esto es lo más habitual en los entornos educativos en los que los alumnos quieren aprovechar su interfaz de correo electrónico personal, pero siguen teniendo correos electrónicos relacionados con la escuela. Otro ejemplo es cuando los clientes se encuentran en un escenario híbrido y tienen servidores locales que envían correo electrónico fuera de EOP.</span><span class="sxs-lookup"><span data-stu-id="a0957-p102">Office 365 allows for tenants to relay some messages through Exchange Online Protection (EOP). One supported example of this would be when users have an Office 365 mailbox and someone external sends them email but email forwarding is configured so that it goes back out to the user's external mailbox. This is most common in education environments where students want to leverage their personal email interface but still get emails related to school. Another example is when customers are in a hybrid scenario and have on-premises servers that send email out of EOP.</span></span>

## <a name="problems-with-unregistered-domains"></a><span data-ttu-id="a0957-109">Problemas con dominios no registrados</span><span class="sxs-lookup"><span data-stu-id="a0957-109">Problems with unregistered domains</span></span>

<span data-ttu-id="a0957-p103">El problema se encuentra cuando los servidores locales se ven comprometidos y retransmiten un gran volumen de correo no deseado de EOP. En casi todos los casos, los conectores correctos se configuran, pero el correo electrónico se envía desde dominios no registrados, también conocidos como no aprovisionados. Office 365 permite que una cantidad razonable de correo proceda de dominios no registrados, pero debe configurarse un dominio aceptado en el centro de administración para cada dominio en el que tenga previsto enviar un.</span><span class="sxs-lookup"><span data-stu-id="a0957-p103">The problem is when on-premises servers get compromised and end up relaying a large volume of spam out of EOP. In almost all cases, the right connectors are set up but email is being sent from unregistered, also known as unprovisioned, domains. Office 365 does allow a reasonable amount of mail to come from unregistered domains, but an Accepted Domain should be configured in the Admin Center for each domain you plan on sending out of.</span></span>

<span data-ttu-id="a0957-p104">Una vez comprometida, se impedirá que los inquilinos envíen correo saliente para los dominios no registrados. Los usuarios recibirán un informe de no entrega (NDR) que indica lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="a0957-p104">Once compromised, tenants will be prevented from sending outbound mail for unregistered domains. Users will receive a Non-Delivery Report (NDR) that states:</span></span>

- <span data-ttu-id="a0957-p105">550 5.7.750 servicio no disponible. El cliente bloqueó el envío de dominios no registrados</span><span class="sxs-lookup"><span data-stu-id="a0957-p105">550 5.7.750 Service unavailable. Client blocked from sending from unregistered domains</span></span>

## <a name="unblocking-tenant-in-order-to-send-again"></a><span data-ttu-id="a0957-117">Desbloqueo de inquilino para enviar de nuevo</span><span class="sxs-lookup"><span data-stu-id="a0957-117">Unblocking tenant in order to send again</span></span>

<span data-ttu-id="a0957-118">Hay varias cosas que debe hacer si se bloquea para enviar desde dominios no registrados:</span><span class="sxs-lookup"><span data-stu-id="a0957-118">There are several things you need to do if you get blocked for sending from unregistered domains:</span></span>

1. <span data-ttu-id="a0957-p106">Asegúrese de registrar todos los dominios en el centro de administración de Office 365. Puede encontrar más información [aquí](https://docs.microsoft.com/en-us/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains).</span><span class="sxs-lookup"><span data-stu-id="a0957-p106">Make sure that you register all of your domains in Office 365 admin center. More information can be found [here](https://docs.microsoft.com/en-us/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains).</span></span>

2. <span data-ttu-id="a0957-p107">Busque conectores inusuales. A menudo, los actores malintencionados crean conectores entrantes nuevos en el inquilino de Office 365 para enviar correo no deseado. Puede encontrar más información sobre cómo comprobar los conectores [](https://docs.microsoft.com/en-us/powershell/module/exchange/mail-flow/get-inboundconnector?view=exchange-ps).</span><span class="sxs-lookup"><span data-stu-id="a0957-p107">Look for unusual connectors. Malicious actors will often create new inbound connectors in your Office 365 tenant to send spam. More information on checking your connectors can be found [here](https://docs.microsoft.com/en-us/powershell/module/exchange/mail-flow/get-inboundconnector?view=exchange-ps).</span></span> 

3. <span data-ttu-id="a0957-124">Bloquee los servidores locales y asegúrese de que no están comprometidos.</span><span class="sxs-lookup"><span data-stu-id="a0957-124">Lock down your on-premises servers and ensure that they are not compromised.</span></span>

> [!TIP]
> <span data-ttu-id="a0957-p108">Hay muchos factores implicados aquí, especialmente si se trata de servidores de terceros. Por lo tanto, tendrá que confirmar que todo el correo que sale de los servidores es legítimo.</span><span class="sxs-lookup"><span data-stu-id="a0957-p108">There are many factors involved here, especially if these are third-party servers. Regardless, you will need to be able confirm that  all mail leaving your servers are legitimate.</span></span>

4. <span data-ttu-id="a0957-p109">Una vez hecho, deberá llamar al soporte técnico de Microsoft y pedirle que desbloquee el espacio empresarial para enviar de nuevo desde dominios no registrados.  Proporcionarle el código de error es útil, pero tendrá que probar que su entorno está protegido y que el correo no deseado no se enviará de nuevo. Puede encontrar más información sobre cómo abrir un caso de soporte [aquí](https://support.office.com/en-us/article/Contact-support-for-business-products-Admin-Help-32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b#ID0EAADAAA=online).</span><span class="sxs-lookup"><span data-stu-id="a0957-p109">Once done, you will need to call Microsoft Support and ask to get your tenant unblocked to send from unregistered domains again.  Providing the error code is helpful, but you will need to prove that your environment is secured and that spam will not be sent again. More information on opening a support case can be found [here](https://support.office.com/en-us/article/Contact-support-for-business-products-Admin-Help-32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b#ID0EAADAAA=online).</span></span>
  
## <a name="for-more-information"></a><span data-ttu-id="a0957-130">Más información</span><span class="sxs-lookup"><span data-stu-id="a0957-130">For more information</span></span>

[<span data-ttu-id="a0957-131">Protección contra correo no deseado de Office 365</span><span class="sxs-lookup"><span data-stu-id="a0957-131">Office 365 email anti-spam protection</span></span>](anti-spam-protection.md)

[<span data-ttu-id="a0957-132">Informes de no entrega de correo electrónico en Office 365</span><span class="sxs-lookup"><span data-stu-id="a0957-132">Email non-delivery reports in Office 365</span></span>](https://support.office.com/article/email-non-delivery-reports-in-office-365-51daa6b9-2e35-49c4-a0c9-df85bf8533c3)

[<span data-ttu-id="a0957-133">Configurar el reenvío de correo electrónico para un buzón de correo</span><span class="sxs-lookup"><span data-stu-id="a0957-133">Configure email forwarding for a mailbox</span></span>](https://docs.microsoft.com/en-us/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding)

[<span data-ttu-id="a0957-134">Cómo configurar una aplicación o dispositivo multifunción para enviar correos electrónicos mediante Office 365</span><span class="sxs-lookup"><span data-stu-id="a0957-134">How to set up a multifunction device or application to send email using Office 365</span></span>](https://support.office.com/en-us/article/How-to-set-up-a-multifunction-device-or-application-to-send-email-using-Office-365-69f58e99-c550-4274-ad18-c805d654b4c4)

<span data-ttu-id="a0957-135">[Administrar dominios aceptados en Exchange Online](https://docs.microsoft.com/en-us/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains).</span><span class="sxs-lookup"><span data-stu-id="a0957-135">[Manage accepted domains in Exchange Online](https://docs.microsoft.com/en-us/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains).</span></span>
