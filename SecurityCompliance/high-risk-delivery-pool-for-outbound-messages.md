---
title: Grupo de entrega de alto riesgo para mensajes salientes
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 8/24/2016
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: ac11edd9-2da3-462d-8ea3-bbf9dbc6f948
description: Cuando se ha comprometido el sistema de correo electrónico de un cliente por un ataque de malware o de correo no deseado y dicho sistema envía correo no deseado saliente por el servicio de filtrado hospedado, las direcciones IP de los servidores del centro de datos de Office 365 podrían incluirse en listas de bloqueados de terceros.
ms.openlocfilehash: 856db53b105379ea3e606e39bf3c2612afa803c3
ms.sourcegitcommit: 22bca85c3c6d946083d3784f72e886c068d49f4a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/06/2018
ms.locfileid: "22026627"
---
# <a name="high-risk-delivery-pool-for-outbound-messages"></a><span data-ttu-id="32270-103">Grupo de entrega de alto riesgo para mensajes salientes</span><span class="sxs-lookup"><span data-stu-id="32270-103">High-risk delivery pool for outbound messages</span></span>

<span data-ttu-id="32270-p101">Cuando se ha comprometido el sistema de correo electrónico de un cliente por un ataque de malware o de correo no deseado y dicho sistema envía correo no deseado saliente por el servicio de filtrado hospedado, las direcciones IP de los servidores del centro de datos de Office 365 podrían incluirse en listas de bloqueados de terceros. Los servidores de destino que no usan el servicio de filtrado hospedado, pero que usan esas listas de bloqueados, rechazan todo el correo electrónico enviado desde cualquiera de las direcciones IP de filtrado hospedado que se hayan agregado a esas listas. Para evitarlo, todos los mensajes salientes que superen el umbral de correo no deseado se envían mediante un grupo de entrega de alto riesgo. Este grupo secundario de correo electrónico saliente solo se usa para enviar mensajes que pueden ser de baja calidad. Esto ayuda a proteger el resto de la red del envío de mensajes que podrían causar el bloqueo de la dirección IP de envío.</span><span class="sxs-lookup"><span data-stu-id="32270-p101">When a customer's email system has been compromised by malware or a malicious spam attack, and it's sending outbound spam through the hosted filtering service, this can result in the IP addresses of the Office 365 data center servers being listed on third-party block lists. Destination servers that do not use the hosted filtering service, but do use these block lists, reject all email sent from any of the hosted filtering IP addresses that have been added to those lists. To prevent this, all outbound messages that exceed the spam threshold are sent through a high-risk delivery pool. This secondary outbound email pool is only used to send messages that may be of low quality. This helps to protect the rest of the network from sending messages that are more likely to result in the sending IP address being blocked.</span></span>
  
<span data-ttu-id="32270-p102">El uso de grupos de entrega de alto riesgo dedicados ayuda a garantizar que el grupo saliente normal solamente envíe mensajes que se sepa que son de alta calidad. El uso de este grupo secundario de direcciones IP ayuda a reducir la probabilidad de que el grupo normal de direcciones IP salientes se agregue a la lista de bloqueados. La posibilidad de que el grupo de entrega de alto riesgo se coloque en una lista de bloqueados aún sigue siendo un riesgo. Esto es así por diseño.</span><span class="sxs-lookup"><span data-stu-id="32270-p102">The use of a dedicated high-risk delivery pool helps ensure that the normal outbound pool is only sending messages that are known to be of a high-quality. Using this secondary IP pool helps to reduce the probability of the normal outbound-IP pool being added to a blocked list. The possibility of the high-risk delivery pool being placed on a blocked list remains a risk. This is by design.</span></span>
  
<span data-ttu-id="32270-113">Los mensajes en los que el dominio de envío no tiene un registro de direcciones (registro A), el cual proporciona la dirección IP del dominio, ni tampoco un registro MX, el cual ayuda a dirigir el correo a los servidores que deben recibirlo en un dominio particular de DNS, siempre se enrutan por el grupo de entrega de alto riesgo independientemente de la disposición del correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="32270-113">Messages where the sending domain has no address record (A record), which gives you the IP address of the domain, and no MX record, which helps direct mail to the servers that should receive the mail for a particular domain in the DNS, are always routed through the high-risk delivery pool regardless of their spam disposition.</span></span>
  
## <a name="understanding-delivery-status-notification-dsn-messages"></a><span data-ttu-id="32270-114">Descripción de los mensajes de notificación de estado de entrega (DSN)</span><span class="sxs-lookup"><span data-stu-id="32270-114">Understanding Delivery Status Notification (DSN) messages</span></span>

<span data-ttu-id="32270-115">El grupo de entrega de alto riesgo saliente administra la entrega de todos los mensajes de DSN "devueltos" o "con error".</span><span class="sxs-lookup"><span data-stu-id="32270-115">The outbound high-risk delivery pool manages the delivery for all "bounced" or "failed" (DSN) messages.</span></span>
  
<span data-ttu-id="32270-116">Las posibles causas de un aumento de mensajes de DSN son las siguientes:</span><span class="sxs-lookup"><span data-stu-id="32270-116">Possible causes for a surge in DSN messages include the following:</span></span>
  
- <span data-ttu-id="32270-117">Una campaña de suplantación de identidad está afectando a uno de los clientes que utiliza el servicio</span><span class="sxs-lookup"><span data-stu-id="32270-117">A spoofing campaign affecting one of the customers using the service</span></span>
    
- <span data-ttu-id="32270-118">Un ataque por recolección de directorios</span><span class="sxs-lookup"><span data-stu-id="32270-118">A directory harvest attack</span></span>
    
- <span data-ttu-id="32270-119">Un ataque de correo no deseado</span><span class="sxs-lookup"><span data-stu-id="32270-119">A spam attack</span></span>
    
- <span data-ttu-id="32270-120">Un servidor SMTP de acceso no autorizado</span><span class="sxs-lookup"><span data-stu-id="32270-120">A rogue SMTP server</span></span>
    
<span data-ttu-id="32270-p103">Todos estos factores pueden causar el aumento repentino de la cantidad de mensajes de DSN que el servicio procesa. Muchas veces, los mensajes de DSN se perciben como correo no deseado en otros servidores y servicios de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="32270-p103">All of these issues can result in a sudden increase in the number of DSN messages being processed by the service. Many times, these DSN messages appear to be spam to other email servers and services.</span></span>
  
## <a name="for-more-information"></a><span data-ttu-id="32270-123">Más información</span><span class="sxs-lookup"><span data-stu-id="32270-123">For more information</span></span>

[<span data-ttu-id="32270-124">Configurar la directiva de correo no deseado saliente</span><span class="sxs-lookup"><span data-stu-id="32270-124">Configure the outbound spam policy</span></span>](configure-the-outbound-spam-policy.md)
  
[<span data-ttu-id="32270-125">Protección contra correo no deseado preguntas más frecuentes</span><span class="sxs-lookup"><span data-stu-id="32270-125">Anti-spam protection FAQ</span></span>](anti-spam-protection-faq.md)
  

