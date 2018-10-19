---
title: Procedimientos recomendados de seguridad para Office 365
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 5/22/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MED150
- MBS150
- BCS160
- MET150
ms.assetid: 9295e396-e53d-49b9-ae9b-0b5828cdedc3
description: Minimizar el potencial de una infracción de datos o una cuenta en peligro siguiendo estos procedimientos recomendados.
ms.openlocfilehash: 0d3dc30a9975f2ed8fe6d524b4fc67918b34e51d
ms.sourcegitcommit: 49b565f6a57febe53f331b2605d6a06d11e2d0be
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2018
ms.locfileid: "25638004"
---
# <a name="security-best-practices-for-office-365"></a>Procedimientos recomendados de seguridad para Office 365

Minimizar el potencial de una infracción de datos o una cuenta en peligro siguiendo estos procedimientos recomendados.
  
Este artículo contiene una lista rápida de procedimientos recomendados. Para obtener información sobre la configuración de seguridad y análisis en profundidad más, vea [Guía de seguridad de Office 365: principales prioridades para los primeros 30 días, 90 días y más allá de](security-roadmap.md). En este artículo, puede encontrar información en función de investigaciones de ataques para el mundo real, donde nuestros expertos de la ciberseguridad principales de Microsoft Office 365 proporcionarán retroalimentación acerca de cómo evaluar el riesgo e implementar la seguridad, cumplimiento e información más críticos controles de protección para proteger al inquilino de Office 365. Aprenderá cómo dar prioridad a las amenazas, traducir las amenazas en estrategia técnica y, a continuación, adoptar un método sistemático a la implementación de las características y controles.
  
## <a name="use-office-365-secure-score"></a>Usar puntuación segura de Office 365

Puntuación seguro es una herramienta de análisis de seguridad que se recomienda lo que puede hacer para reducir el riesgo. Puntuación de seguro se busca en la configuración de Office 365 y las actividades y los compara con una línea de base establecida por Microsoft. Obtendrá una puntuación de cómo alineadas que se basan en con procedimientos recomendados de seguridad. Para obtener más información acerca de cómo obtener la puntuación de seguro y usarlo para aumentar la seguridad de la organización de Office 365, vea [Introducción a la puntuación de seguro de Office 365](office-365-secure-score.md).
  
¿Desea probar puntuación seguro?
  
Uso de una cuenta de trabajo o escuela que se ha asignado el rol de Office 365 [roles de administrador acerca de Office 365](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) , [iniciar sesión en Office 365](https://www.office.com/signin).
  
Acceso seguro puntuación en [https://SecureScore.office.com](https://SecureScore.office.com).
  
## <a name="use-multi-factor-authentication-mfa"></a>Usar la autenticación multifactor (MFA)

MFA agrega una capa adicional de protección a una estrategia de contraseña segura por requerir que los usuarios a una llamada de teléfono, mensaje de texto o una notificación de la aplicación en su teléfono inteligente después de escribir correctamente su contraseña. Con MFA en su lugar, las cuentas de usuario de Office 365 todavía están protegidas contra el acceso no autorizado, incluso si se ve comprometida una contraseña de usuario. Las cuentas están protegidas porque no se concede acceso a una cuenta hasta después de que se haya probado el desafío adicional. Una contraseña en peligro o robada no es suficiente.
  
- [Plan de Multi-Factor Authentication para implementaciones de Office 365](https://support.office.com/article/043807b2-21db-4d5c-b430-c8a6dee0e6ba)
    
- [Configurar autenticación multifactor para usuarios de Office 365](https://support.office.com/article/8f0454b2-f51a-4d9c-bcde-2c48e41621c6)
    
## <a name="use-office-365-cloud-app-security"></a>Usar la seguridad de la aplicación de Office 365 en la nube

Configurar las directivas en función de las necesidades de negocio para realizar un seguimiento de la actividad anómala y actuar en él. Configurar las alertas de seguridad de la aplicación de Office 365 en la nube para que los administradores puedan consultar la actividad de usuario inusual o arriesgado, como una descarga grandes cantidades de datos, varios error de intentos de inicio de sesión o inicios de sesión desde una dirección IP desconocida o peligrosa. Para las organizaciones con un plan de Office 365 Enterprise E5, puede empezar a usar seguridad de la aplicación de nube de Office 365 inmediatamente. Si dispone de un plan de empresa diferentes, puede comprar la seguridad de la aplicación de Office 365 en la nube como un complemento.
  
- [Información general de seguridad de la aplicación de Office 365 en la nube](office-365-cas-overview.md)
    
- [Activar Office 365 Cloud App Security](turn-on-office-365-cas.md)
    
## <a name="secure-mail-flow"></a>Flujo de correo seguro

Implementar el enriquecido conjunto en Exchange Online Protection de características y obtener mayor seguridad sobre la identidad del remitente de cada mensaje de correo electrónico y protección contra malware desconocido, virus y direcciones URL malintencionadas se transmite a través de mensajes de correo electrónico.
  
- Configurar las directivas de [Protección contra correo no deseado de Office 365 correo](anti-spam-protection.md) para su organización. 
    
- Obtenga información sobre y, a continuación, usar la [protección contra amenazas avanzadas para los datos adjuntos seguros y vínculos seguros](https://technet.microsoft.com/library/mt148491.aspx).
    
- [Protección contra malware de agregar a la organización](https://technet.microsoft.com/en-us/library/jj200669%28v=exchg.150%29.aspx).
    
- Obtenga información sobre y habilitar [sugerencias de seguridad en los mensajes de correo electrónico en Office 365](safety-tips-in-office-365.md) para los usuarios. 
    
- Si utiliza un dominio personalizado para su organización en Office 365, configurar SPF, DKIM y, a continuación, DMARC para validar el correo enviado por la organización y para ayudar a evitar la suplantación de identidad:
    
  - [Configurar SPF en Office 365 para ayudar a evitar la suplantación de identidad](https://docs.microsoft.com/office365/SecurityCompliance/set-up-spf-in-office-365-to-help-prevent-spoofing).
    
  - [Uso de DKIM para validar el correo electrónico saliente enviado desde su dominio personalizado en Office 365](https://docs.microsoft.com/office365/SecurityCompliance/set-up-spf-in-office-365-to-help-prevent-spoofing).
    
  - [Usar DMARC para validar el correo electrónico en Office 365](https://technet.microsoft.com/library/mt734386%28v=exchg.150%29.aspx).
    
## <a name="enable-mailbox-audit-logging"></a>Habilitación del registro de auditoría de buzones de correo

Algunos registro de auditoría se habilita automáticamente para usted en Office 365; Sin embargo, el registro de auditoría de buzón no está activado de forma predeterminada. Activar el registro de auditoría para todos los buzones de usuario en Office 365 con Exchange Online PowerShell. Para obtener información, vea [Habilitar la auditoría en Office 365 de buzón de correo](https://go.microsoft.com/fwlink/p/?LinkID=626109).
  
Una vez que haya habilitado puede el registro de auditoría [Buscar en el registro de auditoría de la seguridad de Office 365 &amp; centro de cumplimiento](search-the-audit-log-in-security-and-compliance.md) para saber quién ha iniciado sesión en los buzones de usuario, mensajes enviados y otras actividades realizadas por el propietario del buzón, un usuario delegado o un administrador. Para obtener una lista de las actividades de buzón de correo que se incluyen en Office 365 de registro de auditoría de forma predeterminada, vea [las actividades de buzón de correo de Exchange](search-the-audit-log-in-security-and-compliance.md#exchange-mailbox-activities).
  
Para obtener información acerca de otras acciones que puede realizar con el registro de auditoría, como cambiar la cantidad de tiempo para guardar las entradas en el registro de auditoría, vea [registro en Exchange 2016 de auditoría de buzón de correo](https://technet.microsoft.com/en-us/library/ff459237%28v=exchg.160%29.aspx).
  
## <a name="configure-data-loss-prevention-dlp"></a>Configuración de prevención de pérdida de datos (DLP)

DLP permite identificar datos confidenciales y crear directivas que ayudan a impedir que los usuarios los datos de uso compartido de forma accidental o intencionada. DLP funciona a través de Office 365 incluido Exchange Online, SharePoint Online y OneDrive para que sus usuarios puedan permanecer compatible con sin interrumpir su flujo de trabajo. Para obtener más información, vea [información general de las directivas de prevención de pérdida de datos](data-loss-prevention-policies.md).
  
## <a name="use-customer-lockbox"></a>Use la caja de seguridad del cliente

Como un administrador de Office 365, puede usar la caja de seguridad de cliente para controlar cómo un ingeniero de soporte técnico de Microsoft tiene acceso a los datos durante una sesión de ayuda. En los casos donde el ingeniero requiere acceso a los datos para solucionar problemas y corregir un problema, caja de seguridad de cliente permite aprobar o rechazar la solicitud de acceso. Si aprobarlo, el ingeniero puede tener acceso a los datos. Cada solicitud tiene un tiempo de expiración y una vez que se resuelve el problema, se cierra la solicitud y se revoca el acceso. Caja de seguridad del cliente se incluye en el plan de Office 365 Enterprise E5, o puede comprar una suscripción independiente con cualquier otro plan de enterprise de Office 365. Para obtener información, vea [Office 365 las solicitudes de caja de seguridad del cliente](https://support.office.com/article/36f9cdd1-e64c-421b-a7e4-4a54d16440a2).
  
## <a name="try-it-yourself"></a>Pruébelo
<a name="SecureScore"> </a>

Vea estas características de seguridad de trabajar en una suscripción de prueba de Office 365 antes de la adopción de en producción.
  
- [Crear una suscripción de prueba de Office 365](https://technet.microsoft.com/library/mt736406.aspx)
    
- [Configurar y probar MFA para una cuenta de usuario](https://technet.microsoft.com/library/mt492459.aspx)
    
- [Configurar y probar Office 365 la seguridad de la aplicación de nube para notificar de actividad de administrador global](https://technet.microsoft.com/library/mt757250.aspx)
    
- [Configurar y probar ATP para el correo electrónico sospechoso](https://technet.microsoft.com/library/mt490479.aspx)
    
- Compruebe la [Puntuación de Office 365 seguro](https://securescore.office.com/) para su suscripción de prueba para cada uno de los pasos anteriores 
    

