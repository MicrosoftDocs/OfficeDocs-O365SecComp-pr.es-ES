---
title: Revisión del conocimiento del dominio del remitente
ms.author: chrisda
author: chrisda
manager: serdars
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
description: Los administradores pueden obtener información sobre la información sobre cómo solucionar el dominio del remitente en el panel de flujo de correo en el centro de seguridad & cumplimiento.
ms.openlocfilehash: 181f224064b5f31fd17c348cc4547826fbcd29a9
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/17/2019
ms.locfileid: "34158712"
---
# <a name="fix-sender-domain-insight"></a>Revisión del conocimiento del dominio del remitente

Office 365 requiere mensajes que envían desde entornos de correo electrónico locales internos a Office 365 para cumplir ciertos criterios de seguridad:

- Ha creado un conector de entrada en Office 365 para autenticar las conexiones SMTP desde el servidor de correo electrónico local mediante el uso de la dirección IP de origen o un certificado.

- Ha configurado su servidor de correo electrónico local para retransmitir el correo electrónico a través de Office 365 a un mundo externo.

- En la configuración, se cumple una de las siguientes instrucciones:

  - El dominio de correo electrónico del remitente está registrado en su organización de Office 365. Para obtener más información, vea Agregar dominios en Office 365.

  - El servidor de correo electrónico local está configurado para usar un certificado para enviar correo electrónico a Office 365, el certificado contiene o coincide exactamente con un nombre de dominio que se ha registrado en Office 365 y ha creado un conector basado en certificado en Office 365 con ese Reserva. 

Los mensajes que no cumplen los criterios no se atribuirán a la organización y podrían rechazarse.

La introducción a la **solución de dominio del remitente** muestra el correo electrónico de su entorno local que no cumple los criterios, le ayuda a identificar las cuentas de usuario y equipos potencialmente comprometidos en su entorno de correo electrónico local y le ayuda a tomar acciones de corrección.

![La información del dominio de remitentes Fix del panel flujo de correo del centro de seguridad & cumplimiento](media/sender-domain-insight-selected.png)

Al hacer clic en **Ver detalles**, se le lleva a otro widget con más detalles como se muestra en el siguiente diagrama:

![Widget de detalles en el información sobre la solución de dominio del remitente](media/sender-domain-view-details.png)

Verá el conector de entrada que se usó para entregar los mensajes a Office 365. También puede hacer clic en **ver identificadores de mensaje de ejemplo** para ver los detalles de los mensajes que se enviaron desde su entorno de correo electrónico local. Debido a que estos mensajes fueron rechazados por Office 365, no puede usar el seguimiento de mensajes, pero puede usar los identificadores de mensaje de ejemplo para realizar un seguimiento de los mensajes en su entorno de correo electrónico local.

![Ver identificadores de mensaje de ejemplo en el información de dominio del remitente de corrección](media/sender-domain-view-sample-message-ids.png)

## <a name="see-also"></a>Vea también

Para obtener más información acerca de otras indicaciones de flujo de correo en el panel de flujo de correo, consulte [mail Flow Insights en el centro de seguridad _AMP_ cumplimiento](mail-flow-insights-v2.md).
