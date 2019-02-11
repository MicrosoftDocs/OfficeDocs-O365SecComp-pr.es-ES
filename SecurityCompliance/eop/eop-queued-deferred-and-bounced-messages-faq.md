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
# <a name="eop-queued-deferred-and-bounced-messages-faq"></a>Preguntas más frecuentes sobre mensajes devueltos, aplazados y en cola de EOP

En este tema se ofrecen respuestas a las preguntas más frecuentes sobre los mensajes que se ponen en cola, se aplazan o se devuelven durante el proceso de filtrado de Microsoft Exchange Online Protection (EOP).
  
 **P. ¿Por qué se pone el correo en cola?**
  
R. Los mensajes se ponen en cola o se aplazan si el servicio no puede establecer una conexión con el servidor del destinatario para la entrega. Los mensajes no se aplazan si la red del destinatario devuelve un error de tipo 500.
  
 **P. ¿Cómo se aplaza un mensaje?**
  
R. Los mensajes se retienen cuando no se puede conectar con el servidor del destinatario y este devuelve un "error temporal" como que se agotó el tiempo de espera de la conexión, se rechazó la conexión o un error de tipo 400. Si se produce un error permanente, como un error de tipo 500, el mensaje se devuelve al remitente.
  
 **P. ¿Cuánto tiempo permanece aplazado un mensaje y cuál es el intervalo de reintento?**
  
R. mensajes en aplazamiento permanecerá en nuestras colas para 2 días. Mensaje de reintentos se basan en el error que recibimos desde el sistema de correo del destinatario. El primer aplazamientos pocas son 15 minutos o menor con reintentos subsiguientes (a través de la siguiente docenas de un byte o lo) al aumentar el intervalo a través de varios reintentos para un máximo de 60 minutos. La expansión de duración de intervalo es dinámica, teniendo en cuenta varios variables como los tamaños de la cola y la prioridad del mensaje interno. En basic, es de 15 minutos (o menos) para iniciar, a continuación, expandir desde allí a través de la siguiente pocas horas a 60 minutos max.
  
 **Q. Después de que se restaura el servidor de correo electrónico, ¿cómo se distribuyen los mensajes en cola?**
  
A. Después de que se restaura el servidor de correo electrónico, todos los mensajes en cola se procesan automáticamente en el orden en que se recibieron y se pusieron en cola cuando el servidor dejó de estar disponible. 
  

