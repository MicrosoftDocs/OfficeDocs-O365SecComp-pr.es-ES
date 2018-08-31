---
title: Notificación de muestra cuando se bloquea a un remitente para enviar correo no deseado de salida
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 11/2/2017
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c33fd406-a4c8-4ac8-ad85-123996c5cded
description: 'Cuando se bloquea a un remitente en el servicio debido al envío de correo no deseado de salida, el administrador de dominio especificado al Configurar la directiva de correo no deseado saliente recibirá un correo electrónico de notificación similar al siguiente:'
ms.openlocfilehash: b9fcdf9c2f44a4446a678ca4b22a0a12b24b6fd4
ms.sourcegitcommit: e9dca2d6a7838f98bb7eca127fdda2372cda402c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/21/2018
ms.locfileid: "23003249"
---
# <a name="sample-notification-when-a-sender-is-blocked-sending-outbound-spam"></a>Notificación de muestra cuando se bloquea a un remitente para enviar correo no deseado de salida

Cuando se bloquea a un remitente en el servicio debido al envío de correo no deseado de salida, el administrador de dominio especificado al [Configurar la directiva de correo no deseado saliente](configure-the-outbound-spam-policy.md) recibirá un correo electrónico de notificación similar al siguiente: 
  
 **Dirección del remitente:** spamalerts@microsoft.com 
  
 **Asunto:** Notificación de correo no deseado de salida: \<  *nombre de cuenta*  \> bloqueada para enviar correo saliente 
  
 **Cuerpo:** Esto es una respuesta automática desde el sistema de análisis de Exchange Online Protection correo no deseado. 
  
Se pone en contacto debido a que hemos detectado volúmenes de correo electrónico que se marcó como correo no deseado o cualquier otro comportamiento sospechoso, que se originan desde la organización. Las siguientes cuentas de correo electrónico que se haya bloqueado de envío de correo electrónico (aún pueden recibir correo electrónico):
  
\< *nombre de cuenta*  \> 
  
Es probable que esta cuenta de correo electrónico se ha puesto en peligro. Por favor, siga estos pasos:
  
1. Resolver este problema en su parte por:
    
  - Cambiar la contraseña de la cuenta.
    
  - Determinación de cómo se ha puesto en peligro la cuenta.
    
  - Tomando precauciones para asegurarse de que esta vulnerabilidad no se aproveche nuevo.
    
  - Para confirmar que se ha borrado la cola de correo saliente de todos los mensajes ofensivos.
    
2. Póngase en contacto con el soporte técnico de Microsoft mediante el uso de su canal de contacto regular.
    
3. Explique que dispone de un usuario que está bloqueado el envío de correo y que el problema se ha dedicado a.
    
4. El agente creará un vale de soporte técnico con la información que proporcionan y pasar para que tiene la dirección de correo electrónico o dominio desbloqueado.
    
5. Después de que se ha desbloqueado la dirección y no hay otros asuntos pendientes, se ponen en contacto y una alerta para el desbloqueo.
    
Gracias por asistir a nosotros en el control de correo electrónico no deseado.
  
Exchange Online Protection.
  
\*\*NOTA: no responda a este correo electrónico ya que se envía desde una dirección sin supervisar\*\*
  
> [!TIP]
> También puede ponerse en contacto con soporte técnico a través de las opciones que se documentan en la [Ayuda y soporte técnico para EOP](eop/help-and-support-for-eop.md). 
  

