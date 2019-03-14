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
ms.openlocfilehash: 229ee045d03b3fa4ccb7b4d5e59e1b2b7df6a7d7
ms.sourcegitcommit: 686bc9a8f7a7b6810a096f07d36751d10d334409
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/26/2019
ms.locfileid: "30276360"
---
# <a name="support-for-anonymous-inbound-email-messages-over-ipv6"></a>Compatibilidad para mensajes de correo electrónico entrante anónimos a través de IPv6

Exchange Online Protection (EOP) y Exchange Online permiten la recepción de mensajes de correo electrónico anónimos entrantes a través de comunicaciones IPv6 de remitentes que no envían mensajes a través de la Seguridad de capa de transporte (TLS). Puede optar por recibir mensajes a través de IPv6 solicitando esta funcionalidad del soporte técnico de Microsoft abriendo el centro de administración de Office [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home)365 en, haciendo clic en **soporte técnico**y, a continuación, haciendo clic en **nueva solicitud de servicio**). Si decide no elegir IPv6, continuará recibiendo mensajes a través de IPv4.
  
Los remitentes que transmiten mensajes al servicio a través de IPv6 deben cumplir las dos condiciones siguientes:
  
1. La dirección IPv6 de envío debe tener un registro PTR válido ([registro DNS inverso](https://en.wikipedia.org/wiki/Reverse_DNS_lookup) de la dirección IPv6 de envío). 
    
2. El remitente debe pasar la verificación SPF (definida en la norma [RFC 7208](https://tools.ietf.org/html/rfc7208)) o la [verificación de DKIM](http://dkim.org/) (definida en la norma [RFC 6376](https://www.rfc-editor.org/rfc/rfc6376.txt)).
    
Cumplir con estos requisitos es obligatorio independientemente de la configuración que se tenía antes de optar por IPv6. Si se cumplen ambos requisitos, el mensaje pasará los filtros de mensajes de correo electrónico normales que proporciona el servicio. Si no se cumple uno de los dos, el mensaje se rechaza con una de las siguientes respuestas 450:
  
-  `450 4.7.25 Service unavailable, sending IPv6 address [2a01:111:f200:2004::240] must have reverse DNS record.`
    
-  `450 4.7.26 Service unavailable, message sent over IPv6 [2a01:111:f200:2004::240] must pass either SPF or DKIM validation.`
    
Si no ha optado por recibir mensajes a través de IPv6 y el remitente intenta forzar un mensaje a través de IPv6 conectándose manualmente al servidor de correo, el mensaje será rechazado con una respuesta 550, que tiene un aspecto similar al siguiente:
  
 `550 5.2.1 Service unavailable, [contoso.com] does not accept email over IPv6.`
  
## <a name="for-more-information"></a>Más información

[Compatibilidad para la validación de mensajes firmados con DKIM](support-for-validation-of-dkim-signed-messages.md)
  

