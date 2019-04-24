---
title: Grupo de entrega de alto riesgo para mensajes salientes
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 8/24/2016
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ac11edd9-2da3-462d-8ea3-bbf9dbc6f948
ms.collection:
- M365-security-compliance
description: Cuando se ha comprometido el sistema de correo electrónico de un cliente por un ataque de malware o de correo no deseado y dicho sistema envía correo no deseado saliente por el servicio de filtrado hospedado, las direcciones IP de los servidores del centro de datos de Office 365 podrían incluirse en listas de bloqueados de terceros.
ms.openlocfilehash: b3c0aecd45dd01d407712af2e3945e1cff521710
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32253948"
---
# <a name="high-risk-delivery-pool-for-outbound-messages"></a>Grupo de entrega de alto riesgo para mensajes salientes

Cuando se ha comprometido el sistema de correo electrónico de un cliente por un ataque de malware o de correo no deseado y dicho sistema envía correo no deseado saliente por el servicio de filtrado hospedado, las direcciones IP de los servidores del centro de datos de Office 365 podrían incluirse en listas de bloqueados de terceros. Los servidores de destino que no usan el servicio de filtrado hospedado, pero que usan esas listas de bloqueados, rechazan todo el correo electrónico enviado desde cualquiera de las direcciones IP de filtrado hospedado que se hayan agregado a esas listas. Para evitarlo, todos los mensajes salientes que superen el umbral de correo no deseado se envían mediante un grupo de entrega de alto riesgo. Este grupo secundario de correo electrónico saliente solo se usa para enviar mensajes que pueden ser de baja calidad. Esto ayuda a proteger el resto de la red del envío de mensajes que podrían causar el bloqueo de la dirección IP de envío.
  
El uso de grupos de entrega de alto riesgo dedicados ayuda a garantizar que el grupo saliente normal solamente envíe mensajes que se sepa que son de alta calidad. El uso de este grupo secundario de direcciones IP ayuda a reducir la probabilidad de que el grupo normal de direcciones IP salientes se agregue a la lista de bloqueados. La posibilidad de que el grupo de entrega de alto riesgo se coloque en una lista de bloqueados aún sigue siendo un riesgo. Esto es así por diseño.
  
Los mensajes en los que el dominio de envío no tiene un registro de direcciones (registro A), el cual proporciona la dirección IP del dominio, ni tampoco un registro MX, el cual ayuda a dirigir el correo a los servidores que deben recibirlo en un dominio particular de DNS, siempre se enrutan por el grupo de entrega de alto riesgo independientemente de la disposición del correo no deseado.
  
## <a name="understanding-delivery-status-notification-dsn-messages"></a>Descripción de los mensajes de notificación de estado de entrega (DSN)

El grupo de entrega de alto riesgo saliente administra la entrega de todos los mensajes de DSN "devueltos" o "con error".
  
Las posibles causas de un aumento de mensajes de DSN son las siguientes:
  
- Una campaña de suplantación de identidad está afectando a uno de los clientes que utiliza el servicio
    
- Un ataque por recolección de directorios
    
- Un ataque de correo no deseado
    
- Un servidor SMTP de acceso no autorizado
    
Todos estos factores pueden causar el aumento repentino de la cantidad de mensajes de DSN que el servicio procesa. Muchas veces, los mensajes de DSN se perciben como correo no deseado en otros servidores y servicios de correo electrónico.
  
## <a name="for-more-information"></a>Más información

[Configurar la directiva de correo no deseado saliente](configure-the-outbound-spam-policy.md)
  
[Preguntas más frecuentes sobre protección contra correo no deseado](anti-spam-protection-faq.md)
  

