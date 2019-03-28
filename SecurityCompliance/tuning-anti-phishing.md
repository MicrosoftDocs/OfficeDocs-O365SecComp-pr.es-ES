---
title: Ajuste de la protección contra la suplantación de identidad en Office 365
ms.author: chrisda
author: chrisda
manager: serdars
ms.date: ''
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
description: Los administradores pueden aprender a identificar los motivos por los que se obtienen los mensajes de suplantación de identidad (phishing) y cómo hacerlo para evitar más mensajes de suplantación de identidad en el futuro.
ms.openlocfilehash: efda9e16c23e4533b6951e43ac085b7640e84576
ms.sourcegitcommit: 8a65a29aa3bfe5dcad0ff152a7cd795e02877dd9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2019
ms.locfileid: "30937832"
---
# <a name="tune-anti-phishing-protection-in-office-365"></a>Ajuste de la protección contra la suplantación de identidad en Office 365

Aunque Office 365 incluye una variedad de características antiphishing que están habilitadas de forma predeterminada, es posible que algunos mensajes de suplantación de identidad sigan teniendo acceso a sus buzones. En este tema se describe qué se puede hacer para descubrir por qué se ha recibido un mensaje de suplantación de identidad (phishing) y qué se puede hacer para ajustar la configuración antiphishing en la organización de Exchange Online _sin que los elementos sean peores_.

## <a name="first-things-first-deal-with-any-compromised-accounts-and-make-sure-you-block-any-more-phishing-messages-from-getting-through"></a>Primero lo primero: tratar con todas las cuentas comprometidas y asegurarse de que se impide el acceso a otros mensajes de suplantación de identidad

Si la cuenta de un destinatario se viera comprometida como resultado del mensaje de suplantación de identidad (phishing), siga los pasos que se indican en [responder a una cuenta de correo electrónico comprometida en Office 365](responding-to-a-compromised-email-account.md).

Si su suscripción incluye la protección contra amenazas avanzada (ATP), puede usar la [inteligencia sobre amenazas de Office 365](office-365-ti.md) para identificar a otros usuarios que también recibieron el mensaje de suplantación de identidad (phishing). Tiene opciones adicionales para bloquear los mensajes de suplantación de identidad:

- [Vínculos seguros de ATP](set-up-atp-safe-links-policies.md)

- [Datos adjuntos seguros ATP](set-up-atp-safe-attachments-policies.md)

- [Directivas contra la suplantación de identidad ATP](set-up-anti-phishing-policies.md). Tenga en cuenta que puede aumentar temporalmente los umbrales de suplantación de **identidad (phishing) avanzada** de la Directiva de **estándar** a **agresivo**, **más agresivo**o **más agresivo**.

Compruebe que estas características de ATP están activadas.

## <a name="report-the-phishing-message-to-microsoft"></a>Informar del mensaje de suplantación de identidad a Microsoft

Informar de los mensajes de suplantación de identidad resulta útil para ajustar los filtros que se usan para proteger a todos los clientes de Office 365.

Envíe el mensaje de suplantación de identidad _como datos_ adjuntos en un mensaje nuevo, si no, vacío a **phish@office365.microsoft.com**. No reenvíe el mensaje original; de lo contrario, no podemos examinar los encabezados de mensaje originales. O bien, puede usar el complemento de [mensajes de informe](https://docs.microsoft.com/office365/securitycompliance/enable-the-report-message-add-in) en Outlook o en Outlook en la web (anteriormente conocido como Outlook Web App).

Para obtener más información, vea enviar correo electrónico no deseado, mensajes de correo [no deseado y mensajes de estafa de suplantación de identidad a Microsoft para su análisis](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md).

## <a name="inspect-the-message-headers"></a>Inspeccionar los encabezados del mensaje

Puede examinar los encabezados del mensaje de suplantación de identidad (phishing) para ver si hay algo que puede hacer usted mismo para evitar que lleguen más mensajes de suplantación de identidad. En otras palabras, el examen de los encabezados de los mensajes puede ayudarle a identificar cualquier configuración de su organización que sea responsable de permitir los mensajes de suplantación de identidad (phishing) en.

En concreto, debe comprobar el campo de encabezado **X-Forefront-antispam-Report** en los encabezados de mensaje para ver si hay indicios de correo no deseado o de filtrado de phish en el valor de veredicto de filtrado de correo no deseado (SFV). Los mensajes que omiten el filtrado tendrán una `SCL:-1`entrada de, lo que significa que una de las configuraciones ha permitido este mensaje mediante la anulación del correo no deseado o los veredictos que el servicio ha determinado. Para obtener más información sobre cómo obtener encabezados de mensajes y la lista completa de todos los encabezados de mensajes contra correo no deseado y antiphishing disponibles, consulte [anti-spam Message headers](https://docs.microsoft.com/office365/SecurityCompliance/anti-spam-message-headers).

## <a name="best-practices-to-stay-protected"></a>Procedimientos recomendados para mantener la protección

- De manera mensual, ejecute la [puntuación segura de office 365](office-365-secure-score.md) para evaluar la configuración de seguridad de la organización de Office 365.

- Revise periódicamente el [Informe de inteligencia simulada](learn-about-spoof-intelligence.md) y [habilite la protección contra la suplantación de identidad en la Directiva contra la suplantación de identidad (phishing)](learn-about-spoof-intelligence.md#configuring-the-anti-spoofing-policy) para **poner en cuarentena** los mensajes sospechosos en lugar de entregarlos en la carpeta de correo no deseado del usuario.

- Revise periódicamente el [Informe de estado de protección contra amenazas](view-reports-for-atp.md#threat-protection-status-report).

- Algunos clientes permiten accidentalmente los mensajes de suplantación de identidad mediante la colocación de sus propios dominios en la lista Permitir remitente o permitir dominio en las directivas contra correo no deseado. Si decide hacerlo, debe extremar las precauciones. Aunque esta configuración permitirá el acceso a algunos mensajes legítimos, también permitirá mensajes malintencionados que normalmente se bloquearían mediante los filtros de phish y correo no deseado de Office 365.

  La mejor forma de tratar con los mensajes legítimos que están bloqueados por Office 365 (falsos positivos) que implican a los remitentes de su dominio es configurar completamente y por completo los registros de DMARC, DKIM y DMARC en DNS para _todos_ los dominios de correo electrónico en Office 365:

  - Compruebe que el registro SPF identifica _todos los_ orígenes de correo electrónico de los remitentes de su dominio (no olvide los servicios de terceros).

  - Use error (\-) para asegurarse de que los sistemas de correo electrónico que están configurados para ello rechacen a los remitentes no autorizados. Puede usar inteligencia de suplantación de [identidad](https://docs.microsoft.com/office365/securitycompliance/learn-about-spoof-intelligence) para identificar a los remitentes que usan su dominio para que pueda incluir remitentes de terceros autorizados en su registro de SPF.

  Para obtener instrucciones de configuración, consulte:
  
  - [Configurar SPF en Office 365 para ayudar a evitar la suplantación de identidad](set-up-spf-in-office-365-to-help-prevent-spoofing.md)

  - [Usar DKIM para validar el correo electrónico saliente enviado desde su dominio personalizado en Office 365](use-dkim-to-validate-outbound-email.md)

  - [Usar DMARC para validar el correo electrónico en Office 365](use-dmarc-to-validate-email.md)

- Siempre que sea posible, se recomienda entregar el correo electrónico del dominio directamente a Office 365. En otras palabras, apunte el registro MX del dominio de Office 365 a Office 365. Exchange Online Protection (EOP) puede proporcionar la mejor protección para los usuarios de la nube cuando el correo se entrega directamente a Office 365. Si debe usar un sistema de protección de correo electrónico de terceros delante de EOP, asegúrese de que ha seguido las instrucciones [aquí](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-mail-flow-using-third-party-cloud).

- La autenticación multifactor (MFA) es una forma realmente eficaz de evitar cuentas comprometidas. Debe considerar seriamente habilitar MFA para todos los usuarios. Para un enfoque por fases, empiece por habilitar la MFA para los usuarios más confidenciales (administradores, ejecutivos, etc.) antes de habilitar MFA para todos los usuarios. Para obtener instrucciones, vea [set up multi-factor Authentication](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication).

- Los intrusos suelen usar las reglas de reEnvío a los destinatarios externos para extraer datos. Use la información sobre la **revisión de reglas** de reenvío de buzones en la [calificación segura de Office 365](office-365-secure-score.md) para buscar e incluso impedir el reenvío de reglas a destinatarios externos. Para obtener más información, consulte [mitigaTing Client external forwardIng rules with Secure score](https://blogs.technet.microsoft.com/office365security/mitigating-client-external-forwarding-rules-with-secure-score/).
