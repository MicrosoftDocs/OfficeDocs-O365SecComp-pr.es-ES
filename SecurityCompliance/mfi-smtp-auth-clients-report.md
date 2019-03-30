---
title: Informe de clientes de autenticación SMTP
ms.author: chrisda
author: chrisda
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
description: Los administradores pueden obtener información sobre el informe de clientes de autenticación SMTP en el panel de flujo de correo en el centro de seguridad & cumplimiento.
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: b6698345a89edf52e4ee14cea144cb88ff080583
ms.sourcegitcommit: e7a776a04ef6ed5e287a33cfdc36aa2d72862b55
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/29/2019
ms.locfileid: "30998713"
---
# <a name="smtp-auth-clients-report"></a>Informe de clientes de autenticación SMTP

> [!NOTE]
> Las características descritas en este tema no se han implementado en todas las organizaciones de Office 365 y están sujetas a cambios.

El informe de **clientes de autenticación SMTP** resalta el uso del Protocolo de envío de cliente de autenticación SMTP por parte de los usuarios o las cuentas de sistema de la organización. Este protocolo heredado (que usa el punto de conexión smtp.office365.com) solo ofrece autenticación básica y es vulnerable a su uso por parte de cuentas comprometidas para enviar correo electrónico.  Este informe le permite comprobar actividades inusuales. También muestra los datos de uso de TLS para clientes o dispositivos que usan SMTP AUTH.

El widget que se muestra en el panel de flujo de correo indica el número de usuarios o cuentas de servicio que han usado el protocolo de autenticación SMTP en los últimos 7 días.

![El informe de clientes de autenticación SMTP del panel de flujo de correo en el centro de seguridad & cumplimiento](media/smtp-auth-clients-report-selected.png)

Al hacer clic en el widget, se abre un control flotante que proporciona una vista agregada del uso y los volúmenes de TLS para la semana pasada.

![El control flotante en el informe de clientes de autenticación SMTP](media/smtp-auth-clients-flyout.png)

Al hacer clic en el vínculo de **Informe clientes de autenticación SMTP** , verá dos tablas dinámicas de datos principales y dos vistas de datos. Las tablas dinámicas de datos son el **volumen de envío** y el **uso de TLS**. Las vistas de datos son el gráfico y la tabla de detalles.

La vista **volumen de envío** muestra el número de mensajes que se enviaron con SMTP AUTH para el intervalo de tiempo especificado. Puede ajustar el rango haciendo clic en **filtros**. El gráfico está organizado por dominio de remitente. Puede ver datos independientes para cada dominio seleccionando el dominio en el menú **Mostrar datos para** .

![Envío de volumen en el informe de clientes de autenticación SMTP](media/smtp-auth-clients-report-sending-volume.png)

Puede ver información detallada sobre los remitentes y sus recuentos de mensajes haciendo clic en **ver tabla de detalles**. Para volver al gráfico, haga clic en **Ver informe**.

![Tabla de detalles para enviar el volumen en el informe de clientes de autenticación SMTP](media/smtp-auth-clients-report-details-sending-volume.png)

La tabla dinámica de **uso de TLS** es importante debido al próximo desuso de TLS 1.0 y TLS 1.1 en Office 365. Muchos dispositivos y aplicaciones heredados no podrán enviar correo electrónico si solo pueden usar TLS 1.0 con autenticación SMTP. Esta tabla dinámica le permite identificar y realizar acciones en usuarios y cuentas del sistema que todavía usan versiones anteriores de TLS.

![Uso de TLS en el informe de clientes de autenticación SMTP](media/smtp-auth-clients-report-tls-usage.png)

Puede ver información detallada sobre los remitentes, las versiones de TLS que están usando con la autenticación SMTP y sus recuentos de mensajes haciendo clic en **ver tabla de detalles**. Para volver al gráfico, haga clic en **Ver informe**.

También puede descargar una versión más detallada del informe haciendo clic en solicitar informe.

![Tabla de detalles del uso de TLS en el informe de clientes de autenticación SMTP](media/smtp-auth-clients-report-details-tls-usage.png)

## <a name="see-also"></a>Vea también

Para obtener más información acerca de otras indicaciones de flujo de correo en el panel de flujo de correo, consulte [mail Flow Insights en el centro de seguridad _AMP_ cumplimiento](mail-flow-insights-v2.md).
