---
title: Compatibilidad para mensajes de correo electrónico entrante anónimos a través de IPv6
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 10/4/2017
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: b68df621-0a5f-4824-8abc-41e0c4fd1398
description: Exchange Online Protection (EOP) y Exchange Online admiten recibir mensajes de correo electrónico entrante anónimos a través de IPv6 communications de remitentes que no envíen mensajes a través de seguridad de capa de transporte (TLS). Puede participar en para recibir los mensajes a través de IPv6 solicitando esta funcionalidad de UNRESOLVED_TOKEN_VAL(exMCSS) abriendo el centro de administración de Office 365 en https://portal.office.com/adminportal/home, haciendo clic en soporte técnico y, a continuación, haciendo clic en nueva solicitud de servicio). Si no participar en IPv6 se seguirá recibiendo los mensajes a través de IPv4.
ms.openlocfilehash: 93575c57bb6eac5e0f92066dab3e6ed8b5f4b215
ms.sourcegitcommit: e9dca2d6a7838f98bb7eca127fdda2372cda402c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/21/2018
ms.locfileid: "23003019"
---
# <a name="support-for-anonymous-inbound-email-messages-over-ipv6"></a><span data-ttu-id="daa2c-105">Compatibilidad para mensajes de correo electrónico entrante anónimos a través de IPv6</span><span class="sxs-lookup"><span data-stu-id="daa2c-105">Support for anonymous inbound email messages over IPv6</span></span>

<span data-ttu-id="daa2c-p102">Exchange Online Protection (EOP) y Exchange Online admiten recibir mensajes de correo electrónico entrante anónimos a través de IPv6 communications de remitentes que no envíen mensajes a través de seguridad de capa de transporte (TLS). Puede participar en para recibir los mensajes a través de IPv6 solicitando esta funcionalidad de UNRESOLVED_TOKEN_VAL(exMCSS) abriendo el centro de administración de Office 365 en [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home), haciendo clic en **soporte técnico**y, a continuación, haciendo clic en **nueva solicitud de servicio**). Si no participar en IPv6 se seguirá recibiendo los mensajes a través de IPv4.</span><span class="sxs-lookup"><span data-stu-id="daa2c-p102">Exchange Online Protection (EOP) and Exchange Online support receiving anonymous inbound email messages over IPv6 communications from senders who don't send messages over Transport Layer Security (TLS). You can opt-in to receive messages over IPv6 by requesting this functionality from UNRESOLVED_TOKEN_VAL(exMCSS) by opening the Office 365 admin center at [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home), clicking **Support**, and then clicking **New service request**). If you don't opt-in to IPv6 you'll continue to receive messages over IPv4.</span></span>
  
<span data-ttu-id="daa2c-109">Los remitentes que transmiten mensajes al servicio a través de IPv6 deben cumplir las dos condiciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="daa2c-109">Senders who transmit messages to the service over IPv6 must comply with the following two requirements:</span></span>
  
1. <span data-ttu-id="daa2c-110">La dirección IPv6 de envío debe tener un registro PTR válido ([registro DNS inverso](https://en.wikipedia.org/wiki/Reverse_DNS_lookup) de la dirección IPv6 de envío).</span><span class="sxs-lookup"><span data-stu-id="daa2c-110">The sending IPv6 address must have a valid PTR record ([reverse DNS record](https://en.wikipedia.org/wiki/Reverse_DNS_lookup) of the sending IPv6 address).</span></span> 
    
2. <span data-ttu-id="daa2c-111">El remitente debe pasar la verificación SPF (definida en la norma [RFC 7208](https://tools.ietf.org/html/rfc7208)) o la [verificación de DKIM](http://dkim.org/) (definida en la norma [RFC 6376](https://www.rfc-editor.org/rfc/rfc6376.txt)).</span><span class="sxs-lookup"><span data-stu-id="daa2c-111">The sender must pass either SPF verification (defined in [RFC 7208](https://tools.ietf.org/html/rfc7208)) or [DKIM verification](http://dkim.org/) (defined in [RFC 6376](https://www.rfc-editor.org/rfc/rfc6376.txt)).</span></span>
    
<span data-ttu-id="daa2c-p103">Estos requisitos de la reunión es obligatoria independientemente de la configuración antes de optar en IPv6. Si se cumplen los requisitos de ambos, el mensaje se realizarán a través de filtrado de mensajes de correo electrónico normal proporcionado por el servicio. Si no se cumple uno u otro, se rechazará el mensaje con una de las siguientes 450 respuestas:</span><span class="sxs-lookup"><span data-stu-id="daa2c-p103">Meeting these requirements is mandatory regardless of your configuration prior to opting-in to IPv6. If both requirements are met, the message will go through normal email message filtering provided by the service. If one or the other isn't met, the message will be rejected with one of the following 450 responses:</span></span>
  
-  `450 4.7.25 Service unavailable, sending IPv6 address [2a01:111:f200:2004::240] must have reverse DNS record.`
    
-  `450 4.7.26 Service unavailable, message sent over IPv6 [2a01:111:f200:2004::240] must pass either SPF or DKIM validation.`
    
<span data-ttu-id="daa2c-115">Si no ha optado por recibir mensajes a través de IPv6 y el remitente intenta forzar un mensaje a través de IPv6 conectándose manualmente al servidor de correo, el mensaje será rechazado con una respuesta 550, que tiene un aspecto similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="daa2c-115">If you aren't opted in to receive messages over IPv6 and the sender tries to force a message over IPv6 by manually connecting to the mail server, the message will be rejected with a 550 response that looks similar to the following:</span></span>
  
 `550 5.2.1 Service unavailable, [contoso.com] does not accept email over IPv6.`
  
## <a name="for-more-information"></a><span data-ttu-id="daa2c-116">Más información</span><span class="sxs-lookup"><span data-stu-id="daa2c-116">For more information</span></span>

[<span data-ttu-id="daa2c-117">Compatibilidad para la validación de mensajes firmados con DKIM</span><span class="sxs-lookup"><span data-stu-id="daa2c-117">Support for validation of DKIM signed messages</span></span>](support-for-validation-of-dkim-signed-messages.md)
  

