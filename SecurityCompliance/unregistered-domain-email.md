---
title: Correo electrónico de dominio no registradas
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 10/17/2018
ms.audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
description: Si envía un gran volumen de correo electrónico de dominio no registradas, corre el riesgo de su correo electrónico se bloquean. Lea este artículo para obtener más información.
ms.openlocfilehash: 30d7887be0429195380f2c4ae1a328904dffd69c
ms.sourcegitcommit: 6d72cdb882b93edf6dfddb5ff2e6d8a16e2fa0bc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2018
ms.locfileid: "25596733"
---
# <a name="unregistered-domain-email-what-you-need-to-know"></a><span data-ttu-id="2c4c6-104">Correo electrónico de dominio no registrada: ¿Qué necesita saber</span><span class="sxs-lookup"><span data-stu-id="2c4c6-104">Unregistered Domain Email: What you need to know</span></span>

<span data-ttu-id="2c4c6-p102">Office 365 permite los inquilinos para que transmita algunos mensajes a través de Exchange Online Protection (EOP). Un ejemplo compatible de esto sería cuando los usuarios tienen un buzón de Office 365 y alguien externo envía correo electrónico pero reenvío de correo electrónico está configurado para que vuelve para el buzón del usuario externo. Esto es más comunes en entornos de educación donde los alumnos desean sacar provecho de su interfaz de correo electrónico personal, aunque siguen teniendo correos electrónicos relacionados a la escuela. Otro ejemplo es cuando los clientes se encuentran en un escenario híbrido y tienen servidores locales que envían correo electrónico fuera de la elevación de privilegios.</span><span class="sxs-lookup"><span data-stu-id="2c4c6-p102">Office 365 allows for tenants to relay some messages through Exchange Online Protection (EOP). One supported example of this would be when users have an Office 365 mailbox and someone external sends them email but email forwarding is configured so that it goes back out to the user's external mailbox. This is most common in education environments where students want to leverage their personal email interface but still get emails related to school. Another example is when customers are in a hybrid scenario and have on-premise servers that send email out of EOP.</span></span>

## <a name="problems-with-unregistered-domains"></a><span data-ttu-id="2c4c6-109">Problemas con los dominios no registradas</span><span class="sxs-lookup"><span data-stu-id="2c4c6-109">Problems with unregistered domains</span></span>

<span data-ttu-id="2c4c6-p103">El problema es cuando los servidores locales obtengan en riesgo y terminen la retransmisión de un gran volumen de correo no deseado fuera de la elevación de privilegios. En casi todos los casos, se configuran los conectores derecho pero se está enviando correo electrónico de dominios no registradas, también conocido como no aprovisionadas. Office 365 permitir una cantidad razonable de correo a proceden de dominios no registradas, pero debe configurarse un dominio aceptado en el centro de administración para cada dominio que planea enviar fuera de.</span><span class="sxs-lookup"><span data-stu-id="2c4c6-p103">The problem is when on-premise servers get compromised and end up relaying a large volume of spam out of EOP. In almost all cases, the right connectors are set up but email is being sent from unregistered, also known as unprovisioned, domains. Office 365 does allow a reasonable amount of mail to come from unregistered domains, but an Accepted Domain should be configured in the Admin Center for each domain you plan on sending out of.</span></span>

<span data-ttu-id="2c4c6-p104">Una vez que se ve comprometida, los inquilinos no podrán enviar correo saliente para dominios no registradas. Los usuarios recibirán un informe de no entrega (NDR) que indica:</span><span class="sxs-lookup"><span data-stu-id="2c4c6-p104">Once compromised, tenants will be prevented from sending outbound mail for unregistered domains. Users will receive a Non-Delivery Report (NDR) that states:</span></span>

- <span data-ttu-id="2c4c6-p105">550 5.7.750 servicio no disponible. Cliente bloqueado el envío de dominios no registradas</span><span class="sxs-lookup"><span data-stu-id="2c4c6-p105">550 5.7.750 Service unavailable. Client blocked from sending from unregistered domains</span></span>

## <a name="unblocking-tenant-in-order-to-send-again"></a><span data-ttu-id="2c4c6-117">Desbloqueo inquilino con el fin de volver a enviar</span><span class="sxs-lookup"><span data-stu-id="2c4c6-117">Unblocking tenant in order to send again</span></span>

<span data-ttu-id="2c4c6-118">Hay varias cosas que debe hacer en el caso de que se obtenga bloqueado para el envío de dominios no registradas:</span><span class="sxs-lookup"><span data-stu-id="2c4c6-118">There are several things you need to do if you get blocked for sending from unregistered domains:</span></span>

1. <span data-ttu-id="2c4c6-p106">Asegúrese de registrar todos los dominios en el centro de administración de Office 365. Puede encontrar más información [aquí](https://docs.microsoft.com/en-us/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains).</span><span class="sxs-lookup"><span data-stu-id="2c4c6-p106">Make sure that you register all of your domains in Office 365 admin center. More information can be found [here](https://docs.microsoft.com/en-us/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains).</span></span>

2. <span data-ttu-id="2c4c6-p107">Busque los conectores poco habituales. Actores malintencionados a menudo va a crear los conectores de entrada nueva en el inquilino de Office 365 para que envíen correo no deseado. Puede encontrar más información sobre la comprobación de los conectores [aquí](https://docs.microsoft.com/en-us/powershell/module/exchange/mail-flow/get-inboundconnector?view=exchange-ps).</span><span class="sxs-lookup"><span data-stu-id="2c4c6-p107">Look for unusual connectors. Malicious actors will often create new inbound connectors in your Office 365 tenant to send spam. More information on checking your connectors can be found [here](https://docs.microsoft.com/en-us/powershell/module/exchange/mail-flow/get-inboundconnector?view=exchange-ps).</span></span> 

3. <span data-ttu-id="2c4c6-124">Bloquear los servidores locales y asegúrese de que no se comprometido.</span><span class="sxs-lookup"><span data-stu-id="2c4c6-124">Lock down your on-premise servers and ensure that they are not compromised.</span></span>

> [!TIP]
> <span data-ttu-id="2c4c6-p108">Hay muchos factores implicados aquí, especialmente si se trata de los servidores de aplicaciones de terceros. No obstante, debe ser capaz de confirmar que todo el correo dejando los servidores son legítimos.</span><span class="sxs-lookup"><span data-stu-id="2c4c6-p108">There are many factors involved here, especially if these are third-party servers. Regardless, you will need to be able confirm that  all mail leaving your servers are legitimate.</span></span>

4. <span data-ttu-id="2c4c6-p109">Una vez hecho, debe llamar a Microsoft Support y preguntar obtener al inquilino desbloqueado para enviar de nuevo de dominios no registradas.  Proporcionar el código de error es útil, pero necesita demostrar que el entorno está protegido y que spam no se enviarán nuevo. Puede encontrar más información acerca de cómo abrir un caso de soporte [aquí](https://support.office.com/en-us/article/Contact-support-for-business-products-Admin-Help-32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b#ID0EAADAAA=online).</span><span class="sxs-lookup"><span data-stu-id="2c4c6-p109">Once done, you will need to call Microsoft Support and ask to get your tenant unblocked to send from unregistered domains again.  Providing the error code is helpful, but you will need to prove that your environment is secured and that spam will not be sent again. More information on opening a support case can be found [here](https://support.office.com/en-us/article/Contact-support-for-business-products-Admin-Help-32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b#ID0EAADAAA=online).</span></span>
  
## <a name="for-more-information"></a><span data-ttu-id="2c4c6-130">Para obtener más información</span><span class="sxs-lookup"><span data-stu-id="2c4c6-130">For more information</span></span>

[<span data-ttu-id="2c4c6-131">Office 365 email anti-spam protection</span><span class="sxs-lookup"><span data-stu-id="2c4c6-131">Office 365 email anti-spam protection</span></span>](anti-spam-protection.md)

[<span data-ttu-id="2c4c6-132">Informes de no entrega de correo electrónico en Office 365</span><span class="sxs-lookup"><span data-stu-id="2c4c6-132">Email non-delivery reports in Office 365</span></span>](https://support.office.com/article/email-non-delivery-reports-in-office-365-51daa6b9-2e35-49c4-a0c9-df85bf8533c3)

[<span data-ttu-id="2c4c6-133">Configurar el reenvío de correo electrónico para un buzón de correo</span><span class="sxs-lookup"><span data-stu-id="2c4c6-133">Configure email forwarding for a mailbox</span></span>](https://docs.microsoft.com/en-us/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding)

[<span data-ttu-id="2c4c6-134">Cómo configurar un dispositivo o aplicación multifunción para enviar correo mediante Office 365</span><span class="sxs-lookup"><span data-stu-id="2c4c6-134">How to set up a multifunction device or application to send email using Office 365</span></span>](https://support.office.com/en-us/article/How-to-set-up-a-multifunction-device-or-application-to-send-email-using-Office-365-69f58e99-c550-4274-ad18-c805d654b4c4)

<span data-ttu-id="2c4c6-135">[Administrar dominios aceptados en Exchange Online](https://docs.microsoft.com/en-us/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains).</span><span class="sxs-lookup"><span data-stu-id="2c4c6-135">[Manage accepted domains in Exchange Online](https://docs.microsoft.com/en-us/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains).</span></span>
