---
title: Compatibilidad para mensajes de correo electrónico entrante anónimos a través de IPv6
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: ''
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: b68df621-0a5f-4824-8abc-41e0c4fd1398
ms.collection:
- M365-security-compliance
description: Obtenga información sobre cómo configurar la compatibilidad con mensajes anónimos desde orígenes IPv6 para Exchange Online Protection y Exchange Online.
ms.openlocfilehash: 328cef29b7f8b9637ece7aca729ad1d706351667
ms.sourcegitcommit: b688d67935edb036658bb5aa1671328498d5ddd3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2019
ms.locfileid: "30670525"
---
# <a name="support-for-anonymous-inbound-email-messages-over-ipv6"></a><span data-ttu-id="28221-103">Compatibilidad para mensajes de correo electrónico entrante anónimos a través de IPv6</span><span class="sxs-lookup"><span data-stu-id="28221-103">Support for anonymous inbound email messages over IPv6</span></span>

<span data-ttu-id="28221-104">Exchange Online Protection (EOP) y Exchange Online permiten la recepción de mensajes de correo electrónico anónimos entrantes a través de comunicaciones IPv6 de remitentes que no envían mensajes a través de la Seguridad de capa de transporte (TLS).</span><span class="sxs-lookup"><span data-stu-id="28221-104">Exchange Online Protection (EOP) and Exchange Online support receiving anonymous inbound email messages over IPv6 communications from senders who don't send messages over Transport Layer Security (TLS).</span></span> <span data-ttu-id="28221-105">Puede optar por recibir mensajes a través de IPv6 si solicita esta funcionalidad del soporte técnico de Microsoft al abrir el centro de administración de [https://admin.microsoft.com/adminportal/home](https://admin.microsoft.com/adminportal/home)365 de Microsoft en, hacer clic en **soporte técnico**y, a continuación, hacer clic en **nueva solicitud de servicio**).</span><span class="sxs-lookup"><span data-stu-id="28221-105">You can opt-in to receive messages over IPv6 by requesting this functionality from Microsoft Support by opening the Microsoft 365 admin center at [https://admin.microsoft.com/adminportal/home](https://admin.microsoft.com/adminportal/home), clicking **Support**, and then clicking **New service request**).</span></span> <span data-ttu-id="28221-106">Si decide no elegir IPv6, continuará recibiendo mensajes a través de IPv4.</span><span class="sxs-lookup"><span data-stu-id="28221-106">If you don't opt-in to IPv6 you'll continue to receive messages over IPv4.</span></span>
  
<span data-ttu-id="28221-107">Los remitentes que transmiten mensajes al servicio a través de IPv6 deben cumplir las dos condiciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="28221-107">Senders who transmit messages to the service over IPv6 must comply with the following two requirements:</span></span>
  
1. <span data-ttu-id="28221-108">La dirección IPv6 de envío debe tener un registro PTR válido ([registro DNS inverso](https://en.wikipedia.org/wiki/Reverse_DNS_lookup) de la dirección IPv6 de envío).</span><span class="sxs-lookup"><span data-stu-id="28221-108">The sending IPv6 address must have a valid PTR record ([reverse DNS record](https://en.wikipedia.org/wiki/Reverse_DNS_lookup) of the sending IPv6 address).</span></span> 
    
2. <span data-ttu-id="28221-109">El remitente debe pasar la verificación SPF (definida en la norma [RFC 7208](https://tools.ietf.org/html/rfc7208)) o la [verificación de DKIM](http://dkim.org/) (definida en la norma [RFC 6376](https://www.rfc-editor.org/rfc/rfc6376.txt)).</span><span class="sxs-lookup"><span data-stu-id="28221-109">The sender must pass either SPF verification (defined in [RFC 7208](https://tools.ietf.org/html/rfc7208)) or [DKIM verification](http://dkim.org/) (defined in [RFC 6376](https://www.rfc-editor.org/rfc/rfc6376.txt)).</span></span>
    
<span data-ttu-id="28221-110">Cumplir con estos requisitos es obligatorio independientemente de la configuración que se tenía antes de optar por IPv6.</span><span class="sxs-lookup"><span data-stu-id="28221-110">Meeting these requirements is mandatory regardless of your configuration prior to opting-in to IPv6.</span></span> <span data-ttu-id="28221-111">Si se cumplen ambos requisitos, el mensaje pasará los filtros de mensajes de correo electrónico normales que proporciona el servicio.</span><span class="sxs-lookup"><span data-stu-id="28221-111">If both requirements are met, the message will go through normal email message filtering provided by the service.</span></span> <span data-ttu-id="28221-112">Si no se cumple uno de los dos, el mensaje se rechaza con una de las siguientes respuestas 450:</span><span class="sxs-lookup"><span data-stu-id="28221-112">If one or the other isn't met, the message will be rejected with one of the following 450 responses:</span></span>
  
-  `450 4.7.25 Service unavailable, sending IPv6 address [2a01:111:f200:2004::240] must have reverse DNS record.`
    
-  `450 4.7.26 Service unavailable, message sent over IPv6 [2a01:111:f200:2004::240] must pass either SPF or DKIM validation.`
    
<span data-ttu-id="28221-113">Si no ha optado por recibir mensajes a través de IPv6 y el remitente intenta forzar un mensaje a través de IPv6 conectándose manualmente al servidor de correo, el mensaje será rechazado con una respuesta 550, que tiene un aspecto similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="28221-113">If you aren't opted in to receive messages over IPv6 and the sender tries to force a message over IPv6 by manually connecting to the mail server, the message will be rejected with a 550 response that looks similar to the following:</span></span>
  
 `550 5.2.1 Service unavailable, [contoso.com] does not accept email over IPv6.`
  
## <a name="for-more-information"></a><span data-ttu-id="28221-114">Para obtener más información</span><span class="sxs-lookup"><span data-stu-id="28221-114">For more information</span></span>

[<span data-ttu-id="28221-115">Compatibilidad para la validación de mensajes firmados con DKIM</span><span class="sxs-lookup"><span data-stu-id="28221-115">Support for validation of DKIM signed messages</span></span>](support-for-validation-of-dkim-signed-messages.md)
  

