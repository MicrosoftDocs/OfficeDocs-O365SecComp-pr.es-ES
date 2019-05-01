---
title: Establecer una fecha de caducidad para el correo electrónico cifrado por Office 365 Advanced Message Encryption
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 4/30/2019
ms.audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: f87cb016-7876-4317-ae3c-9169b311ff8a
description: Con Office 365 avanzadas capacidades de cifrado de mensajes sobre el cifrado de mensajes de Office 365 (OME), puede ampliar su seguridad de correo electrónico estableciendo una fecha de expiración en los correos electrónicos a través de una plantilla personalizada de personalización de marca.
ms.openlocfilehash: c1fb876724bed970095e950906500ff551d93cee
ms.sourcegitcommit: 8eb3cb4ec45ae0bb75fde249e35c4bc3d263b84f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/30/2019
ms.locfileid: "33506738"
---
# <a name="set-an-expiration-date-for-email-encrypted-by-office-365-advanced-message-encryption"></a>Establecer una fecha de caducidad para el correo electrónico cifrado por Office 365 Advanced Message Encryption

Office 365 Advanced Message Encryption está disponible sobre el cifrado de mensajes de Office 365 en determinadas suscripciones. El cifrado de mensajes avanzado se incluye en [Microsoft 365 Enterprise E5](https://www.microsoft.com/microsoft-365/enterprise/home), Office 365 Enterprise E5 y Office 365 Education A5. Si su organización tiene una suscripción de Office 365 que no incluye el cifrado avanzado de mensajes de Office 365, puede comprar el cifrado de mensajes avanzado como complemento con la compatibilidad con E5 del SKU de compatibilidad avanzada.

Puede usar la expiración de mensajes en los correos electrónicos que los usuarios envían a los destinatarios externos que usan el portal OME para acceder a los correos electrónicos cifrados. Obliga a los destinatarios a usar el portal OME para ver y responder a los correos electrónicos cifrados enviados por la organización mediante una plantilla personalizada que especifica una fecha de expiración en Windows PowerShell.

Como administrador global de O365, cuando aplique la personalización de marca de la empresa para personalizar la apariencia de los mensajes de correo electrónico de su organización de Office 365, también puede especificar una expiración para estos mensajes de correo electrónico. Con Office 365 Advanced Message Encryption, puede crear varias plantillas para los mensajes de correo electrónico cifrados que se originan en su organización. Mediante el uso de una plantilla, puede controlar durante cuánto tiempo los destinatarios tienen acceso al correo enviado por los usuarios.

Cuando un usuario final recibe un correo con una fecha de expiración establecida, el usuario ve la fecha de expiración en el correo electrónico del contenedor. Si un usuario intenta abrir un correo expirado, aparece un error en el portal OME.

Solo los correos electrónicos a los destinatarios externos son caducados.

Con Office 365 Advanced Message Encryption, cada vez que se aplica la personalización de marca, la Office 365 aplica el contenedor al correo electrónico que se ajusta a la regla de flujo de correo a la que se aplica la plantilla. Además, la expiración solo puede usarse si se usa la personalización de marca personalizada.

## <a name="create-a-custom-branding-template-to-force-mail-expiration-by-using-powershell"></a>Crear una plantilla de personalización de marca personalizada para forzar la expiración del correo mediante PowerShell

1. [Conéctese a Exchange Online PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell) usando una cuenta con permisos de administrador global en su inquilino de Office 365.

2. Ejecute el cmdlet New-OMEConfiguration.

     ```powershell
     New-OMEConfiguration -Identity "Expire in 7 days" ExternalMailExpiryInDays 7
     ```

Donde:

- Identity es el nombre de la plantilla personalizada.

- ExternalMailExpiryInDays identifica el número de días que desea que los destinatarios puedan conservar el correo antes de que expire. Puede usar cualquier valor entre 1 y 730 días.

## <a name="more-information-about-office-365-advanced-message-encryption"></a>Más información sobre el cifrado de mensajes avanzado de Office 365

- [Office 365 Advanced Message Encryption](ome-advanced-message-encryption.md)

- [Revocar correo electrónico cifrado por el cifrado de mensajes avanzado de Office 365](revoke-ome-encrypted-mail.md)

- [Descripción de la Directiva de mensajes y el servicio de cumplimiento](https://docs.microsoft.com/en-us/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance)