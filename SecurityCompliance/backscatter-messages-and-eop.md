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
# <a name="backscatter-messages-and-eop"></a>Mensajes de reenvío masivo de correo electrónico y EOP

Los mensajes de reenvío masivo de correo electrónico no deseado son mensajes de devolución automatizados que los servidores de correo envían, normalmente como resultado de correo no deseado entrante. Como Exchange Online Protection (EOP) es un servicio de filtrado de correo no deseado, nuestro servicio rechaza los mensajes de correo electrónico enviados a destinatarios inexistentes y a otros destinos sospechosos. Cuando esto sucede, EOP genera un mensaje de informe de no entrega (NDR) y lo entrega al "remitente". Como los remitentes de correo electrónico no deseado suelen usar una dirección "De" falsa o no válida en sus mensajes, la dirección del remitente a la que se envía el NDR puede provocar un reenvío masivo de correo electrónico no deseado. Cuando esto sucede, los servidores de salida que están asociados con la red de EOP pueden aparecer en la lista de bloqueo de DNS (DNSBL) de Backscatterer. La lista DNSBL de Backscatterer contiene las direcciones IP que envían mensajes de reenvío masivo de correo electrónico. No es una lista de remitentes de correo no deseado y no intentamos quitar nuestros servidores de la lista DNSBL de Backscatterer. 
  
> [!TIP]
> Según las instrucciones del sitio web de Backscatterer, el uso del modo de rechazo para todo el correo entrante no es la configuración recomendada ni el uso de dicho servicio. En su lugar, se debe usar en modo seguro. Para obtener más información acerca de cómo implementar la configuración correcta de reenvío masivo de correo electrónico no deseado, visite el [sitio web de Backscatterer.org](http://www.backscatterer.org/?target=usage). 
  
## <a name="related-topics"></a>Temas relacionados
  
[Opciones avanzadas de filtrado de correo no deseado](advanced-spam-filtering-asf-options.md)
  

