---
title: Mensajes de reenvío masivo de correo electrónico y EOP
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 12/9/2016
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 6f64f2de-d626-48ed-8084-03cc72301aa4
ms.collection:
- M365-security-compliance
description: Los mensajes de reenvío masivo de correo electrónico no deseado son mensajes de devolución automatizados que los servidores de correo envían, normalmente como resultado de correo no deseado entrante. La lista DNSBL de Backscatterer contiene las direcciones IP que envían mensajes de reenvío masivo de correo electrónico. No es una lista de remitentes de correo no deseado y no intentamos quitar nuestros servidores de la lista DNSBL de Backscatterer.
ms.openlocfilehash: 62dd86d91e89e4f3c966b2969d0d763595bb5dc3
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32243901"
---
# <a name="backscatter-messages-and-eop"></a><span data-ttu-id="893d2-105">Mensajes de reenvío masivo de correo electrónico y EOP</span><span class="sxs-lookup"><span data-stu-id="893d2-105">Backscatter messages and EOP</span></span>

<span data-ttu-id="893d2-p102">Los mensajes de reenvío masivo de correo electrónico no deseado son mensajes de devolución automatizados que los servidores de correo envían, normalmente como resultado de correo no deseado entrante. Como Exchange Online Protection (EOP) es un servicio de filtrado de correo no deseado, nuestro servicio rechaza los mensajes de correo electrónico enviados a destinatarios inexistentes y a otros destinos sospechosos. Cuando esto sucede, EOP genera un mensaje de informe de no entrega (NDR) y lo entrega al "remitente". Como los remitentes de correo electrónico no deseado suelen usar una dirección "De" falsa o no válida en sus mensajes, la dirección del remitente a la que se envía el NDR puede provocar un reenvío masivo de correo electrónico no deseado. Cuando esto sucede, los servidores de salida que están asociados con la red de EOP pueden aparecer en la lista de bloqueo de DNS (DNSBL) de Backscatterer. La lista DNSBL de Backscatterer contiene las direcciones IP que envían mensajes de reenvío masivo de correo electrónico. No es una lista de remitentes de correo no deseado y no intentamos quitar nuestros servidores de la lista DNSBL de Backscatterer.</span><span class="sxs-lookup"><span data-stu-id="893d2-p102">Backscatter messages are the automated bounce messages that are sent by mail servers, typically as a result of incoming spam. Because Exchange Online Protection (EOP) is a spam filtering service, email messages sent to nonexistent recipients and to other suspicious destinations are rejected by our service. When this happens, EOP generates a non-delivery report (NDR) message and delivers it back to the "sender." Because spammers frequently use a forged or invalid "From" address in their messages, the sender address to which the NDR is sent may result in a backscatter message. When this happens, outgoing servers that are associated with the EOP network may be listed on the Backscatterer DNS Block List (DNSBL). The Backscatterer DNSBL is a list of IP addresses that send backscatter messages. It isn't a spammer list, and we don't try to remove our servers from the Backscatterer DNSBL.</span></span> 
  
> [!TIP]
> <span data-ttu-id="893d2-p103">Según las instrucciones del sitio web de Backscatterer, el uso del modo de rechazo para todo el correo entrante no es la configuración recomendada ni el uso de dicho servicio. En su lugar, se debe usar en modo seguro. Para obtener más información acerca de cómo implementar la configuración correcta de reenvío masivo de correo electrónico no deseado, visite el [sitio web de Backscatterer.org](http://www.backscatterer.org/?target=usage).</span><span class="sxs-lookup"><span data-stu-id="893d2-p103">According to the instructions on the Backscatterer website, the use of reject mode for all incoming mail isn't a recommended configuration or use of that service. It should be used in safe mode instead. For more information about implementing the correct backscatter configuration, visit the [Backscatterer.org website](http://www.backscatterer.org/?target=usage).</span></span> 
  
## <a name="related-topics"></a><span data-ttu-id="893d2-116">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="893d2-116">Related topics</span></span>
  
[<span data-ttu-id="893d2-117">Opciones avanzadas de filtrado de correo no deseado</span><span class="sxs-lookup"><span data-stu-id="893d2-117">Advanced spam filtering  options</span></span>](advanced-spam-filtering-asf-options.md)
  

