---
title: Preguntas más frecuentes sobre mensajes devueltos, aplazados y en cola de EOP
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 11/17/2014
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 9d015a0d-52a0-484d-9a08-121d04f973d3
description: En este tema se ofrecen respuestas a las preguntas más frecuentes sobre los mensajes que se ponen en cola, se aplazan o se devuelven durante el proceso de filtrado de Microsoft Exchange Online Protection (EOP).
ms.openlocfilehash: 7d584d8356cfca805427c5dd41dc3dee2ee57e85
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/17/2019
ms.locfileid: "34150272"
---
# <a name="eop-queued-deferred-and-bounced-messages-faq"></a>Preguntas más frecuentes sobre mensajes devueltos, aplazados y en cola de EOP

En este tema se ofrecen respuestas a las preguntas más frecuentes sobre los mensajes que se ponen en cola, se aplazan o se devuelven durante el proceso de filtrado de Microsoft Exchange Online Protection (EOP).
  
 **P. ¿Por qué se pone el correo en cola?**
  
R. Los mensajes se ponen en cola o se aplazan si el servicio no puede establecer una conexión con el servidor del destinatario para la entrega. Los mensajes no se aplazan si la red del destinatario devuelve un error de tipo 500.
  
 **P. ¿Cómo se aplaza un mensaje?**
  
R. Los mensajes se retienen cuando no se puede conectar con el servidor del destinatario y este devuelve un "error temporal" como que se agotó el tiempo de espera de la conexión, se rechazó la conexión o un error de tipo 400. Si se produce un error permanente, como un error de tipo 500, el mensaje se devuelve al remitente.
  
 **P. ¿Cuánto tiempo permanece aplazado un mensaje y cuál es el intervalo de reintento?**
  
R. Los mensajes aplazados permanecen en las colas durante 2 días. Los reintentos de envío de mensajes se basan en el error que se obtiene del sistema de correo del destinatario. Los primeros aplazamientos son de 15 minutos o menos, con reintentos posteriores (en las próximas mitades o más), lo que aumenta el intervalo en varios reintentos hasta un máximo de 60 minutos. La expansión de la duración del intervalo es dinámica, teniendo en cuenta varias variables como los tamaños de las colas y la prioridad de mensajes interna. En Basic, tiene 15 minutos (o menos) para comenzar y, a continuación, se expande a partir de las próximas horas a 60 min máx.
  
 **Q. Después de que se restaura el servidor de correo electrónico, ¿cómo se distribuyen los mensajes en cola?**
  
A. Después de que se restaura el servidor de correo electrónico, todos los mensajes en cola se procesan automáticamente en el orden en que se recibieron y se pusieron en cola cuando el servidor dejó de estar disponible. 
  

