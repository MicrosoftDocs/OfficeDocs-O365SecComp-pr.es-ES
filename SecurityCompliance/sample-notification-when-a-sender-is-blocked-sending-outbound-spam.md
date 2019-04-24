---
title: Notificación de muestra cuando se bloquea a un remitente para enviar correo no deseado de salida
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 11/2/2017
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c33fd406-a4c8-4ac8-ad85-123996c5cded
ms.collection:
- M365-security-compliance
description: 'Cuando se bloquea a un remitente en el servicio debido al envío de correo no deseado de salida, el administrador de dominio especificado al Configurar la directiva de correo no deseado saliente recibirá un correo electrónico de notificación similar al siguiente:'
ms.openlocfilehash: 04d8bde8e9cadd3525191a5bee7d368229e85056
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32260978"
---
# <a name="sample-notification-when-a-sender-is-blocked-sending-outbound-spam"></a>Notificación de muestra cuando se bloquea a un remitente para enviar correo no deseado de salida

Cuando se bloquea a un remitente en el servicio debido al envío de correo no deseado de salida, el administrador de dominio especificado al [Configurar la directiva de correo no deseado saliente](configure-the-outbound-spam-policy.md) recibirá un correo electrónico de notificación similar al siguiente: 
  
 **Dirección del remitente:** spamalerts@microsoft.com 
  
 **Asunto:** Notificación de correo no deseado de salida: \<  *nombre de cuenta*  \> bloqueada para enviar correo saliente 
  
 **Cuerpo:** Se trata de una respuesta automática desde el sistema de análisis de correo no deseado de Exchange Online Protection. 
  
Nos ponemos en contacto con usted porque hemos detectado volúmenes elevados de correo electrónico marcado como correo no deseado, u otros comportamientos sospechosos, procedentes de su organización. Las siguientes cuentas de correo electrónico han sido bloqueadas para enviar correo electrónico (pueden seguir recibiendo correo electrónico):
  
\< *nombre de cuenta*  \> 
  
Es probable que esta cuenta de correo electrónico se haya puesto en peligro. Siga estos pasos:
  
1. Resuelva este problema en su parte:
    
  - Cambio de la contraseña de la cuenta.
    
  - Determinación del modo en que la cuenta se ha puesto en peligro.
    
  - Tomar precauciones para asegurarse de que no se pueda aprovechar esta vulnerabilidad de nuevo.
    
  - Confirmar que la cola de correo saliente se ha borrado de todos los mensajes ofensivos.
    
2. Póngase en contacto con el soporte técnico de Microsoft con el canal de contacto habitual.
    
3. Explique que hay un usuario que está bloqueado y no puede enviar correo y que el problema se ha solucionado.
    
4. El agente creará un vale de soporte técnico con la información que proporcione y la escalará para que la dirección de correo electrónico o el dominio no se bloqueen.
    
5. Una vez que se haya desbloqueado la dirección y no se hayan producido otros problemas, se le pondrá en contacto y se le enviará una alerta al desbloqueo.
    
Gracias por ayudarnos a controlar el correo no deseado.
  
Exchange Online Protection.
  
\*\*NOTA: no responda a este correo electrónico ya que se envía desde una dirección sin supervisar\*\*
  
> [!TIP]
> También puede ponerse en contacto con el soporte técnico a través de las opciones documentadas en [Help and Support for EOP](eop/help-and-support-for-eop.md). 
  

