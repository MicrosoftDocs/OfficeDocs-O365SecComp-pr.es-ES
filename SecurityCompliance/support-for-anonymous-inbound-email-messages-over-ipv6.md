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
# <a name="support-for-anonymous-inbound-email-messages-over-ipv6"></a>Compatibilidad para mensajes de correo electrónico entrante anónimos a través de IPv6

Exchange Online Protection (EOP) y Exchange Online admiten recibir mensajes de correo electrónico entrante anónimos a través de IPv6 communications de remitentes que no envíen mensajes a través de seguridad de capa de transporte (TLS). Puede participar en para recibir los mensajes a través de IPv6 solicitando esta funcionalidad de UNRESOLVED_TOKEN_VAL(exMCSS) abriendo el centro de administración de Office 365 en [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home), haciendo clic en **soporte técnico**y, a continuación, haciendo clic en **nueva solicitud de servicio**). Si no participar en IPv6 se seguirá recibiendo los mensajes a través de IPv4.
  
Los remitentes que transmiten mensajes al servicio a través de IPv6 deben cumplir las dos condiciones siguientes:
  
1. La dirección IPv6 de envío debe tener un registro PTR válido ([registro DNS inverso](https://en.wikipedia.org/wiki/Reverse_DNS_lookup) de la dirección IPv6 de envío). 
    
2. El remitente debe pasar la verificación SPF (definida en la norma [RFC 7208](https://tools.ietf.org/html/rfc7208)) o la [verificación de DKIM](http://dkim.org/) (definida en la norma [RFC 6376](https://www.rfc-editor.org/rfc/rfc6376.txt)).
    
Estos requisitos de la reunión es obligatoria independientemente de la configuración antes de optar en IPv6. Si se cumplen los requisitos de ambos, el mensaje se realizarán a través de filtrado de mensajes de correo electrónico normal proporcionado por el servicio. Si no se cumple uno u otro, se rechazará el mensaje con una de las siguientes 450 respuestas:
  
-  `450 4.7.25 Service unavailable, sending IPv6 address [2a01:111:f200:2004::240] must have reverse DNS record.`
    
-  `450 4.7.26 Service unavailable, message sent over IPv6 [2a01:111:f200:2004::240] must pass either SPF or DKIM validation.`
    
Si no ha optado por recibir mensajes a través de IPv6 y el remitente intenta forzar un mensaje a través de IPv6 conectándose manualmente al servidor de correo, el mensaje será rechazado con una respuesta 550, que tiene un aspecto similar al siguiente:
  
 `550 5.2.1 Service unavailable, [contoso.com] does not accept email over IPv6.`
  
## <a name="for-more-information"></a>Más información

[Compatibilidad para la validación de mensajes firmados con DKIM](support-for-validation-of-dkim-signed-messages.md)
  

