---
title: Cifrado avanzado de mensajes de Office 365
ms.author: krowley
author: kccross
manager: laurawi
ms.audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.date: 4/30/2019
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
description: El cifrado de mensajes avanzado en Office 365 ayuda a las organizaciones a cumplir sus obligaciones de cumplimiento permitiendo a los administradores expirar y revocar el acceso a través de un portal web de Office 365 a los correos electrónicos cifrados.
ms.openlocfilehash: 5559a2bca4cd804cfcfdf547146eeb416252ca5f
ms.sourcegitcommit: 865b3dc071150b20bf3967e1263fc54e75898284
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/09/2019
ms.locfileid: "33834909"
---
# <a name="office-365-advanced-message-encryption"></a>Cifrado avanzado de mensajes de Office 365

Office 365 Advanced Message Encryption está disponible sobre el cifrado de mensajes de Office 365 en determinadas suscripciones. El cifrado de mensajes avanzado se incluye en [Microsoft 365 Enterprise E5](https://www.microsoft.com/microsoft-365/enterprise/home), Office 365 Enterprise E5 y Office 365 Education A5. Si su organización tiene una suscripción de Office 365 que no incluye el cifrado avanzado de mensajes de Office 365, puede comprar el cifrado de mensajes avanzado como complemento con la compatibilidad con E5 del SKU de compatibilidad avanzada.

El cifrado de mensajes avanzado en Office 365 ayuda a los clientes a cumplir las obligaciones de cumplimiento que necesitan controles más flexibles sobre los destinatarios externos y su acceso a los correos electrónicos cifrados. Con el cifrado de mensajes avanzado en Office 365, puede controlar los mensajes de correo electrónico confidenciales que se comparten fuera de la organización con directivas automáticas. Estas directivas se configuran para identificar los tipos de información confidencial, como los identificadores de PII, financieros o de mantenimiento, o se pueden usar palabras clave para mejorar la protección. Una vez que haya configurado las directivas, empareja las directivas con plantillas de correo electrónico personalizadas y, a continuación, agrega una fecha de expiración para el control adicional de los correos electrónicos que se ajustan a la Directiva. Además, los administradores pueden controlar más los correos electrónicos cifrados a los que se accede externamente a través de un portal web seguro al revocar el acceso al correo en cualquier momento.

Solo puede revocar y establecer una fecha de caducidad para los correos electrónicos enviados a destinatarios externos.

Con Office 365 Advanced Message Encryption, siempre que aplique una plantilla de personalización de marca personalizada, Office 365 aplica un contenedor al correo electrónico que se ajusta a la regla de flujo de correo a la que se aplica la plantilla. Solo puede revocar mensajes y aplicar fechas de caducidad a los mensajes que reciben los usuarios a través del portal. Es decir, se aplica un correo electrónico con una plantilla de personalización de marca personalizada.

## <a name="get-started-with-office-365-advanced-message-encryption"></a>Introducción a Office 365 Advanced Message Encryption

En los siguientes temas se describe cómo configurar y usar el cifrado de mensajes avanzado.

La organización debe tener una suscripción que incluya el cifrado de mensajes avanzado de Office 365. Para obtener información detallada acerca de las suscripciones admitidas, consulte la [Descripción del servicio de cumplimiento y directivas de mensajes](https://docs.microsoft.com/en-us/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance).

Si no tiene ya configurado el cifrado de mensajes de Office 365, vea [configurar las nuevas capacidades de cifrado de mensajes de office 365](set-up-new-message-encryption-capabilities.md).

[Establezca una fecha de caducidad para el correo electrónico cifrado por el cifrado de mensajes avanzado de Office 365](ome-advanced-expiration.md). Controle los correos electrónicos confidenciales compartidos fuera de la organización con directivas automáticas que mejoran la protección al expirar el acceso a través de un portal web seguro a los correos electrónicos cifrados.

[Revocar correo electrónico cifrado por el cifrado de mensajes avanzado de Office 365](revoke-ome-encrypted-mail.md). Controle los correos electrónicos confidenciales compartidos fuera de la organización y mejore la protección al revocar el acceso a través de un portal web seguro a los correos electrónicos cifrados.  