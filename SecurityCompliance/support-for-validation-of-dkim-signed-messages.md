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
search.appverid:
- MET150
ms.assetid: a4c95148-a00c-4d12-85ed-88520b547d97
description: Exchange Online Protection (EOP) y Exchange Online admiten la validación de entrada de mensajes de Correo identificado con claves de dominio (DKIM). DKIM es un método para validar que un mensaje se envió desde el dominio donde dice que se originó, y que no ha sido suplantado por otra persona. Enlaza un mensaje de correo con la organización responsable de enviarlo. La comprobación de DKIM se usa automáticamente para todos los mensajes enviados a través de comunicaciones IPv6. (Para obtener más información acerca de la compatibilidad con IPv6, consulte Compatibilidad para mensajes de correo electrónico entrante anónimos a través de IPv6).
ms.openlocfilehash: d2fab69847732bb7ed54f943d2c7845e06084936
ms.sourcegitcommit: e9dca2d6a7838f98bb7eca127fdda2372cda402c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/21/2018
ms.locfileid: "23002281"
---
# <a name="support-for-validation-of-dkim-signed-messages"></a><span data-ttu-id="6699d-107">Compatibilidad para la validación de mensajes firmados con DKIM</span><span class="sxs-lookup"><span data-stu-id="6699d-107">Support for validation of DKIM signed messages</span></span>

<span data-ttu-id="6699d-p102">Exchange Online Protection (EOP) y Exchange Online admiten la validación de entrada de mensajes de Correo identificado con claves de dominio ([DKIM](https://www.rfc-editor.org/rfc/rfc6376.txt)). DKIM es un método para validar que un mensaje se envió desde el dominio donde dice que se originó, y que no ha sido suplantado por otra persona. Enlaza un mensaje de correo con la organización responsable de enviarlo. La comprobación de DKIM se usa automáticamente para todos los mensajes enviados a través de comunicaciones IPv6. (Para obtener más información acerca de la compatibilidad con IPv6, consulte [Compatibilidad para mensajes de correo electrónico entrante anónimos a través de IPv6](support-for-anonymous-inbound-email-messages-over-ipv6.md)).</span><span class="sxs-lookup"><span data-stu-id="6699d-p102">Exchange Online Protection (EOP) and Exchange Online support inbound validation of Domain Keys Identified Mail ([DKIM](https://www.rfc-editor.org/rfc/rfc6376.txt)) messages. DKIM is a method for validating that a message was sent from the domain it says it originated from and that it was not spoofed by someone else. It ties an email message to the organization responsible for sending it. DKIM verification is automatically used for all messages sent over IPv6 communications. (For more information about IPv6 support, see [Support for anonymous inbound email messages over IPv6](support-for-anonymous-inbound-email-messages-over-ipv6.md).)</span></span>
  
<span data-ttu-id="6699d-p103">DKIM valida un mensaje firmado digitalmente que aparece en el encabezado DKIM-Signature, en los encabezados de los mensajes. Los resultados de la validación de DKIM-Signature se estampan en el encabezado Authentication-Results que cumple la norma RFC 7001 ([Campo de encabezado de mensaje para indicar el estado de autenticación del mensaje](https://www.rfc-editor.org/rfc/rfc7001.txt)). El texto del encabezado del mensaje tiene un aspecto similar al siguiente (donde contoso.com es el remitente):</span><span class="sxs-lookup"><span data-stu-id="6699d-p103">DKIM validates a digitally signed message that appears in the DKIM-Signature header in the message headers. The results of a DKIM-Signature validation is stamped in the Authentication-Results header which conforms with RFC 7001 ([Message Header Field for Indicating Message Authentication Status](https://www.rfc-editor.org/rfc/rfc7001.txt)). The message header text appears similar to the following (where contoso.com is the sender):</span></span>
  
 `Authentication-Results: <contoso.com>; dkim=pass (signature was verified) header.d=example.com;`
  
<span data-ttu-id="6699d-116">Los administradores pueden crear [Transport Rules](http://technet.microsoft.com/library/743bd525-0ca2-426d-b76c-b4a052bc8886.aspx) de Exchange en los resultados de una validación de DKIM para filtrar o enrutar los mensajes según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="6699d-116">Admins can create Exchange [Transport Rules](http://technet.microsoft.com/library/743bd525-0ca2-426d-b76c-b4a052bc8886.aspx) on the results of a DKIM validation to filter or route messages as needed.</span></span> 
  

