---
title: Preguntas más frecuentes sobre mensajes devueltos, aplazados y en cola de EOP
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: 9d015a0d-52a0-484d-9a08-121d04f973d3
description: En este tema se ofrecen respuestas a las preguntas más frecuentes sobre los mensajes que se ponen en cola, se aplazan o se devuelven durante el proceso de filtrado de Microsoft Exchange Online Protection (EOP).
ms.openlocfilehash: 4b2c902adacd6e72e587aadaceecd22dd0084d85
ms.sourcegitcommit: 7e2a0185cadea7f3a6afc5ddc445eac2e1ce22eb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/11/2019
ms.locfileid: "29686430"
---
# <a name="eop-queued-deferred-and-bounced-messages-faq"></a><span data-ttu-id="d5fee-103">Preguntas más frecuentes sobre mensajes devueltos, aplazados y en cola de EOP</span><span class="sxs-lookup"><span data-stu-id="d5fee-103">EOP queued, deferred, and bounced messages FAQ</span></span>

<span data-ttu-id="d5fee-104">En este tema se ofrecen respuestas a las preguntas más frecuentes sobre los mensajes que se ponen en cola, se aplazan o se devuelven durante el proceso de filtrado de Microsoft Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="d5fee-104">This topic provides answers to frequently asked questions about messages that have been queued, deferred, or bounced during the Microsoft Exchange Online Protection (EOP) filtering process.</span></span>
  
 <span data-ttu-id="d5fee-105">**P. ¿Por qué se pone el correo en cola?**</span><span class="sxs-lookup"><span data-stu-id="d5fee-105">**Q. Why is mail queuing?**</span></span>
  
<span data-ttu-id="d5fee-p101">R. Los mensajes se ponen en cola o se aplazan si el servicio no puede establecer una conexión con el servidor del destinatario para la entrega. Los mensajes no se aplazan si la red del destinatario devuelve un error de tipo 500.</span><span class="sxs-lookup"><span data-stu-id="d5fee-p101">A. Messages are queued or deferred if the service is unable to make a connection to the recipient server for delivery. It will not defer messages if a 500-series error is returned from the recipient network.</span></span>
  
 <span data-ttu-id="d5fee-109">**P. ¿Cómo se aplaza un mensaje?**</span><span class="sxs-lookup"><span data-stu-id="d5fee-109">**Q. How does a message become deferred?**</span></span>
  
<span data-ttu-id="d5fee-p102">R. Los mensajes se retienen cuando no se puede conectar con el servidor del destinatario y este devuelve un "error temporal" como que se agotó el tiempo de espera de la conexión, se rechazó la conexión o un error de tipo 400. Si se produce un error permanente, como un error de tipo 500, el mensaje se devuelve al remitente.</span><span class="sxs-lookup"><span data-stu-id="d5fee-p102">A. Messages will be held when a connection to the recipient server cannot be made and the recipient's server is returning a "temporary failure" such as a connection time-out, connection refused, or a 400-series error. If there is a permanent failure, such as a 500-series error, then the message will be returned to the sender.</span></span>
  
 <span data-ttu-id="d5fee-113">**P. ¿Cuánto tiempo permanece aplazado un mensaje y cuál es el intervalo de reintento?**</span><span class="sxs-lookup"><span data-stu-id="d5fee-113">**Q. How long does a message remain in deferral and what is the retry interval?**</span></span>
  
<span data-ttu-id="d5fee-p103">R. mensajes en aplazamiento permanecerá en nuestras colas para 2 días. Mensaje de reintentos se basan en el error que recibimos desde el sistema de correo del destinatario. El primer aplazamientos pocas son 15 minutos o menor con reintentos subsiguientes (a través de la siguiente docenas de un byte o lo) al aumentar el intervalo a través de varios reintentos para un máximo de 60 minutos. La expansión de duración de intervalo es dinámica, teniendo en cuenta varios variables como los tamaños de la cola y la prioridad del mensaje interno. En basic, es de 15 minutos (o menos) para iniciar, a continuación, expandir desde allí a través de la siguiente pocas horas a 60 minutos max.</span><span class="sxs-lookup"><span data-stu-id="d5fee-p103">A. Messages in deferral will remain in our queues for 2 days. Message retry attempts are based on the error we get back from the recipient's mail system. The first few deferrals are 15 minutes or less, with subsequent retries (over the next half dozen or so) increasing the interval over multiple retries to a max of 60 minutes. The interval duration expansion is dynamic, taking into consideration multiple variables like queue sizes and internal message priority. In basic, it's 15 minutes (or less) to start, then expanding from there over the next few hours to 60 mins max.</span></span>
  
 <span data-ttu-id="d5fee-120">**Q. Después de que se restaura el servidor de correo electrónico, ¿cómo se distribuyen los mensajes en cola?**</span><span class="sxs-lookup"><span data-stu-id="d5fee-120">**Q. After your email server is restored, how are queued messages distributed?**</span></span>
  
<span data-ttu-id="d5fee-p104">A. Después de que se restaura el servidor de correo electrónico, todos los mensajes en cola se procesan automáticamente en el orden en que se recibieron y se pusieron en cola cuando el servidor dejó de estar disponible.</span><span class="sxs-lookup"><span data-stu-id="d5fee-p104">A. After your email server is restored, all queued messages are automatically processed in the order in which they were received and queued when the server became unavailable.</span></span> 
  

