---
title: Compatibilidad para la validación de mensajes firmados con DKIM
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/9/2016
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: a4c95148-a00c-4d12-85ed-88520b547d97
description: Exchange Online Protection (EOP) y Exchange Online admiten la validación de entrada de mensajes de Correo identificado con claves de dominio (DKIM). DKIM es un método para validar que un mensaje se envió desde el dominio donde dice que se originó, y que no ha sido suplantado por otra persona. Enlaza un mensaje de correo con la organización responsable de enviarlo. La comprobación de DKIM se usa automáticamente para todos los mensajes enviados a través de comunicaciones IPv6. (Para obtener más información acerca de la compatibilidad con IPv6, consulte Compatibilidad para mensajes de correo electrónico entrante anónimos a través de IPv6).
ms.openlocfilehash: 0fafc5a4754309f8f467a712f934fea3067b660d
ms.sourcegitcommit: 22bca85c3c6d946083d3784f72e886c068d49f4a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/06/2018
ms.locfileid: "22026157"
---
# <a name="support-for-validation-of-dkim-signed-messages"></a>Compatibilidad para la validación de mensajes firmados con DKIM

Exchange Online Protection (EOP) y Exchange Online admiten la validación de entrada de mensajes de Correo identificado con claves de dominio ([DKIM](https://www.rfc-editor.org/rfc/rfc6376.txt)). DKIM es un método para validar que un mensaje se envió desde el dominio donde dice que se originó, y que no ha sido suplantado por otra persona. Enlaza un mensaje de correo con la organización responsable de enviarlo. La comprobación de DKIM se usa automáticamente para todos los mensajes enviados a través de comunicaciones IPv6. (Para obtener más información acerca de la compatibilidad con IPv6, consulte [Compatibilidad para mensajes de correo electrónico entrante anónimos a través de IPv6](support-for-anonymous-inbound-email-messages-over-ipv6.md)).
  
DKIM valida un mensaje firmado digitalmente que aparece en el encabezado DKIM-Signature, en los encabezados de los mensajes. Los resultados de la validación de DKIM-Signature se estampan en el encabezado Authentication-Results que cumple la norma RFC 7001 ([Campo de encabezado de mensaje para indicar el estado de autenticación del mensaje](https://www.rfc-editor.org/rfc/rfc7001.txt)). El texto del encabezado del mensaje tiene un aspecto similar al siguiente (donde contoso.com es el remitente):
  
 `Authentication-Results: <contoso.com>; dkim=pass (signature was verified) header.d=example.com;`
  
Los administradores pueden crear [Transport Rules](http://technet.microsoft.com/library/743bd525-0ca2-426d-b76c-b4a052bc8886.aspx) de Exchange en los resultados de una validación de DKIM para filtrar o enrutar los mensajes según sea necesario. 
  

