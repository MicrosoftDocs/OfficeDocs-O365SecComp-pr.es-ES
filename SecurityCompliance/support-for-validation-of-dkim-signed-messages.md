---
title: Compatibilidad para la validación de mensajes firmados con DKIM
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a4c95148-a00c-4d12-85ed-88520b547d97
ms.collection:
- M365-security-compliance
description: Obtenga información sobre la validación de mensajes firmados con DKIM en Exchange Online Protection y Exchange Online
ms.openlocfilehash: 75c104af4b3e6126bac37024de2c7f6ab337a028
ms.sourcegitcommit: 1947ad3c0dde9163ba9b6834d8b38bd04b4264a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2019
ms.locfileid: "36643272"
---
# <a name="support-for-validation-of-dkim-signed-messages"></a>Compatibilidad para la validación de mensajes firmados con DKIM

Exchange Online Protection (EOP) y Exchange Online admiten la validación de entrada de mensajes de Correo identificado con claves de dominio ([DKIM](https://www.rfc-editor.org/rfc/rfc6376.txt)). DKIM es un método para validar que un mensaje se envió desde el dominio donde dice que se originó, y que no ha sido suplantado por otra persona. Enlaza un mensaje de correo con la organización responsable de enviarlo. La comprobación de DKIM se usa automáticamente para todos los mensajes enviados a través de comunicaciones IPv6. Office 365 también admite DKIM cuando se envía correo a través de IPv4. (Para obtener más información acerca de la compatibilidad con IPv6, consulte [Compatibilidad para mensajes de correo electrónico entrante anónimos a través de IPv6](support-for-anonymous-inbound-email-messages-over-ipv6.md)).
  
DKIM valida un mensaje firmado digitalmente que aparece en el encabezado DKIM-Signature, en los encabezados de los mensajes. Los resultados de la validación de DKIM-Signature se estampan en el encabezado Authentication-Results que cumple la norma RFC 7001 ([Campo de encabezado de mensaje para indicar el estado de autenticación del mensaje](https://www.rfc-editor.org/rfc/rfc7001.txt)). El texto del encabezado del mensaje tiene un aspecto similar al siguiente (donde contoso.com es el remitente):
  
 `Authentication-Results: <contoso.com>; dkim=pass (signature was verified) header.d=example.com;`
  
Los administradores pueden crear [reglas de flujo de correo](http://technet.microsoft.com/library/743bd525-0ca2-426d-b76c-b4a052bc8886.aspx) de Exchange (también conocidas como reglas de transporte) en los resultados de una validación de DKIM para filtrar o enrutar los mensajes según sea necesario. 
  

