---
title: Procedimientos recomendados de seguridad para Office 365
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 5/22/2018
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MBS150
- BCS160
- MET150
ms.assetid: 9295e396-e53d-49b9-ae9b-0b5828cdedc3
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- Strat_O365_IP
description: Minimice la posibilidad de que se produzca una infracción de datos o una cuenta en peligro; para ello, siga estos procedimientos recomendados.
ms.openlocfilehash: 97dffe6e0cf4551c9addc1ba53c4f95c7d88b3f3
ms.sourcegitcommit: 7adfd8eda038cf25449bdf3df78b5e2fcc1999e7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/01/2019
ms.locfileid: "30357531"
---
# <a name="security-best-practices-for-office-365"></a>Procedimientos recomendados de seguridad para Office 365

Minimice la posibilidad de que se produzca una infracción de datos o una cuenta en peligro; para ello, siga estos procedimientos recomendados.
  
Este artículo contiene una lista rápida de procedimientos recomendados. Para obtener un análisis más exhaustivo e información sobre la configuración de la seguridad, consulte [Office 365 Security Roadmap: Top prioridades para los primeros 30 días, 90 días y posterior](security-roadmap.md). En ese artículo, encontrará información sobre la base de investigaciones de ataques en el mundo real, donde nuestros principales expertos en Microsoft Office 365 Cybersecurity proporcionan formación sobre cómo evaluar el riesgo e implementar la información, el cumplimiento y la seguridad más críticos controles de protección para proteger su inquilino de Office 365. Aprenderá a priorizar amenazas, traducir amenazas a la estrategia técnica y, a continuación, adoptar un enfoque sistemático para implementar características y controles.
  
## <a name="use-office-365-secure-score"></a>Usar la puntuación segura de Office 365

La calificación segura es una herramienta de análisis de seguridad que recomienda lo que se puede hacer para reducir aún más el riesgo. Puntuación segura busca la configuración y las actividades de Office 365 y las compara con una línea base establecida por Microsoft. Obtendrá una puntuación en función de la alineación que tenga con los procedimientos recomendados de seguridad. Para obtener más información acerca de cómo obtener una puntuación segura y usarla para aumentar la seguridad de su organización de Office 365, consulte [Introducing The office 365 Secure score](office-365-secure-score.md).
  
¿Desea probar la puntuación segura?
  
Con una cuenta profesional o educativa a la que se haya asignado el rol Office 365 [sobre roles de administrador de office 365](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) , [inicie sesión en Office 365](https://www.office.com/signin).
  
Acceso a la puntuación [https://SecureScore.office.com](https://SecureScore.office.com)segura en.
  
## <a name="use-multi-factor-authentication-mfa"></a>Usar multi-factor Authentication (MFA)

La MFA agrega una capa de protección adicional a una estrategia de contraseña segura, ya que obliga a los usuarios a confirmar una llamada telefónica, un mensaje de texto o una notificación de la aplicación en el smartphone después de escribir correctamente su contraseña. Con MFA en su ubicación, las cuentas de usuario de Office 365 siguen protegidas contra accesos no autorizados incluso si la contraseña de un usuario está en peligro. Las cuentas están protegidas porque no se ha concedido acceso a una cuenta hasta que se haya satisfecho el desafío adicional. Una contraseña comprometida o robada no es suficiente.
  
- [Plan de Multi-Factor Authentication para implementaciones de Office 365](https://support.office.com/article/043807b2-21db-4d5c-b430-c8a6dee0e6ba)

- [Configurar autenticación multifactor para usuarios de Office 365](https://support.office.com/article/8f0454b2-f51a-4d9c-bcde-2c48e41621c6)

## <a name="use-office-365-cloud-app-security"></a>Usar Office 365 Cloud App Security

Establezca directivas en función de las necesidades de su empresa para realizar un seguimiento de la actividad anómala y actuar sobre ella. Configurar alertas con Office 365 Cloud App Security para que los administradores puedan revisar la actividad de los usuarios inusual o arriesgada, como descargar grandes cantidades de datos, varios intentos de inicio de sesión incorrectos o inicios de sesión de una dirección IP desconocida o peligrosa. Para las organizaciones con un plan de Office 365 Enterprise E5, puede empezar a usar Office 365 Cloud App Security inmediatamente. Si tiene un plan de empresa diferente, puede comprar Office 365 Cloud App Security como un complemento.
  
- [Información general sobre la seguridad de aplicaciones en la nube de O365](office-365-cas-overview.md)

- [Activar Office 365 Cloud App Security](turn-on-office-365-cas.md)

## <a name="secure-mail-flow"></a>Flujo de correo seguro

Implemente el conjunto de características enriquecidas en la protección de Exchange Online y obtenga una mayor seguridad sobre la identidad del remitente de cada mensaje de correo electrónico y Protéjase contra el malware, los virus y los URL malintencionados desconocidos transmitidos a través de los correos electrónicos.
  
- Configurar las directivas de [protección contra correo no deseado de Office 365](anti-spam-protection.md) para su organización.

- Obtenga información acerca de y use [protección contra amenazas avanzada para datos adjuntos seguros y vínculos seguros](https://technet.microsoft.com/library/mt148491.aspx).

- [Agregue protección contra malware a su organización](https://technet.microsoft.com/en-us/library/jj200669%28v=exchg.150%29.aspx).

- Obtenga información sobre y habilite las [sugerencias de seguridad en los mensajes de correo electrónico en Office 365](safety-tips-in-office-365.md) para los usuarios.

- Si está usando un dominio personalizado para su organización en Office 365, configure SPF, DKIM y, a continuación, DMARC para validar el correo enviado por su organización y ayudar a evitar la suplantación de identidad:

  - [Configure SPF en Office 365 para ayudar a evitar la suplantación de identidad](https://docs.microsoft.com/office365/SecurityCompliance/set-up-spf-in-office-365-to-help-prevent-spoofing).

  - [Use DKIM para validar el correo electrónico saliente enviado desde su dominio personalizado en Office 365](https://docs.microsoft.com/office365/SecurityCompliance/set-up-spf-in-office-365-to-help-prevent-spoofing).

  - [Use DMARC para validar el correo electrónico en Office 365](https://technet.microsoft.com/library/mt734386%28v=exchg.150%29.aspx).

## <a name="enable-mailbox-audit-logging"></a>Habilitación del registro de auditoría de buzones de correo

Algunos registros de auditoría se habilitan automáticamente en Office 365; sin embargo, el registro de auditoría de buzones de correo no está activado de forma predeterminada. Active el registro de auditoría para todos los buzones de usuario en Office 365 mediante PowerShell de Exchange Online. Para obtener información, consulte [Habilitar la auditoría de buzones de correo en Office 365](https://go.microsoft.com/fwlink/p/?LinkID=626109).
  
Una vez que haya habilitado el registro de auditoría, puede [Buscar en el registro de &amp; auditoría del centro de seguridad y cumplimiento de Office 365](search-the-audit-log-in-security-and-compliance.md) para averiguar quién ha iniciado sesión en sus buzones de usuario, mensajes enviados y otras actividades realizadas por el propietario del buzón de correo, un usuario delegado, o un administrador. Para obtener una lista de las actividades de buzón que se incluyen en el registro de auditoría de Office 365 de forma predeterminada, consulte [Exchange Mailbox Activities](search-the-audit-log-in-security-and-compliance.md#exchange-mailbox-activities).
  
Para obtener información acerca de otras acciones que puede realizar con el registro de auditoría, como cambiar la cantidad de tiempo que se va a guardar entradas en el registro de auditoría, consulte [registro de auditoría de buzones de correo en Exchange 2016](https://technet.microsoft.com/en-us/library/ff459237%28v=exchg.160%29.aspx).
  
## <a name="configure-data-loss-prevention-dlp"></a>Configurar prevención de pérdida de datos (DLP)

DLP le permite identificar datos confidenciales y crear directivas que ayuden a impedir que los usuarios compartan los datos por accidente o de forma intencionada. DLP funciona en Office 365, incluidos Exchange Online, SharePoint Online y OneDrive para que los usuarios puedan cumplir sin interrumpir el flujo de trabajo. Para obtener más información, vea [información general sobre las directivas de prevención de pérdida de datos](data-loss-prevention-policies.md).
  
## <a name="use-customer-lockbox"></a>Usar caja de caja del cliente

Como administrador de Office 365, puede usar la caja de control del cliente para controlar cómo un ingeniero de soporte técnico de Microsoft obtiene acceso a los datos durante una sesión de ayuda. En los casos en los que el ingeniero requiere el acceso a los datos para solucionar un problema, el Lockbox del cliente le permite aprobar o rechazar la solicitud de acceso. Si lo aprueba, el ingeniero puede tener acceso a los datos. Cada solicitud tiene una fecha de expiración y, una vez resuelto el problema, se cierra la solicitud y se revoca el acceso. La caja de caja del cliente se incluye en el plan Office 365 Enterprise E5, o puede comprar una suscripción independiente con cualquier otro plan Enterprise 365 de Office. Para obtener más información, consulte [Office 365 Customer Lockbox](https://support.office.com/article/36f9cdd1-e64c-421b-a7e4-4a54d16440a2)requests.
  
## <a name="try-it-yourself"></a>Pruébelo usted mismo
<a name="SecureScore"> </a>

Consulte estas características de seguridad que funcionan en una suscripción de prueba de Office 365 antes de adoptarlas en producción.
  
- [Crear una suscripción de prueba de Office 365](https://technet.microsoft.com/library/mt736406.aspx)

- [Configurar y probar la MFA para una cuenta de usuario](https://technet.microsoft.com/library/mt492459.aspx)

- [Configurar y probar Office 365 Cloud App Security para notificar la actividad de administrador global](https://technet.microsoft.com/library/mt757250.aspx)

- [Configurar y probar ATP para correo electrónico sospechoso](https://technet.microsoft.com/library/mt490479.aspx)

- Compruebe la [puntuación segura de Office 365](https://securescore.office.com/) de su suscripción de prueba para cada uno de los pasos anteriores