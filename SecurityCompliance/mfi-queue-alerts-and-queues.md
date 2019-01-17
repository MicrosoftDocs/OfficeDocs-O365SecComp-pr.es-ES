---
title: Alertas de cola y colas
ms.author: chrisda
author: chrisda
manager: serdars
ms.date: ''
ms.audience: ITPro
ms.topic: article
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 37640c80-ce6f-47e2-afd1-bc1d3c50e637
description: Los administradores pueden saber qué alertas de cola y colas en el panel de flujo de correo en el centro de cumplimiento de seguridad de Office 365 &.
ms.openlocfilehash: fe750e32136af095bb0ccff8544306db76a7a667
ms.sourcegitcommit: 25fb33a1f8b2844fde15f6c03db2936c610824e0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2019
ms.locfileid: "28685653"
---
# <a name="queue-alerts-and-queues"></a>Alertas de cola y colas

## <a name="queue-alerts"></a>Alertas de cola

Cuando no se puede enviar los mensajes de la organización de Office 365 a su local o los servidores de correo electrónico de asociados mediante conectores, los mensajes se ponen en cola en Office 365. Ejemplos comunes que provocar esta condición son:

- El conector está configurado correctamente.

- Ha habido cambios de red o firewall en su entorno local.

Office 365 seguirá intentando a la entrega durante 48 horas. Después de 48 horas, los mensajes caducará y se devolverá a los remitentes en informes de no entrega (también conocido como un NDR o rebote a mensajes).

Si el volumen de correo electrónico en cola supera el umbral predefinido (el valor predeterminado es 2000 mensajes), las alertas estará disponibles en el panel de flujo de correo en **las alertas recientes**y administradores recibirán una notificación de correo electrónico (a su dirección de correo electrónico alternativo) . Para configurar el umbral de alerta, límite diario de notificación, o los destinatarios de la alerta, vea la sección de **alertas de cola de personalizar** más adelante.

![Alertas de cola en el área de alertas recientes del panel de flujo de correo en el centro de cumplimiento de seguridad de Office 365 &](media/5fc4a51c-6118-4270-960b-c6b176ef94ae.png)

## <a name="customize-queue-alerts"></a>Personalizar las alertas de cola

Entendimiento del flujo de correo crea una directiva de alerta con nombre **los mensajes se han retrasado** (la casilla de verificación **Enviar notificaciones de correo electrónico** en el ejemplo, se captura de pantalla siguiente) que se encuentra en **las alertas de** \> **Las directivas de alerta**. Puede modificar a los destinatarios del umbral y alerta haciendo clic en la directiva.

![Exploración de las alertas](media/efb95976-9e0b-484e-a2fd-093c5bc7a40f.png)

Verá un nuevo blade de información de la directiva, ahora puede hacer clic en **Editar directiva**.

![Directiva de edición ](media/ed2aceae-3ee2-4849-a17e-87915987a7dd.png)

El servidor blade de información cambiará a la **Directiva de edición**. Ahora puede cambiar a los destinatarios de la alerta por correo electrónico, el límite en el número de notificaciones enviadas por día y el umbral mínimo para desencadenar la alerta (200 o más).

![Editar directiva Blade](media/c657cc74-7867-474c-b2c9-dc478449f990.png)

## <a name="queue-alert-details"></a>Detalles de la alerta cola

Al hacer clic en la alerta, los detalles de alerta aparecen en un panel flotante.

![Seleccione una alerta de cola en el área de alertas recientes del panel de flujo de correo en el centro de cumplimiento de seguridad de Office 365 &](media/1f6b0e96-5b2c-41ef-9684-9d813b3fabe6.png)

![El emergente de detalles de alerta de cola en el centro de cumplimiento de seguridad de Office 365 &](media/105c8fff-912f-4763-8806-2740ebdecd4b.png)

Puede hacer clic en **Ver cola** en los detalles de alerta para ver los detalles de la cola, problemas y vínculos a las revisiones disponibles en un nuevo panel emergente.

![El emergente de detalles de alerta de cola en el centro de cumplimiento de seguridad de Office 365 &](media/8ff60955-55ef-4f32-a966-85e02cb608d1.png)

![Ver la cola en los detalles de alerta](media/4eb088fe-5dd9-4bf4-b959-c1bb2545c515.png)

## <a name="queues"></a>Colas

Incluso si el volumen de mensaje en cola no ha superado el umbral, aún puede usar el área de **colas** del panel de flujo de correo para ver los mensajes que se ha puesto en cola durante más de una hora. Puede usar el área de **colas** para supervisar el número de mensajes en cola (el valor 0 indica el flujo de correo es Aceptar) y tomar medidas antes de que el número de mensajes en cola se convierte en un tamaño demasiado grande.

![Colas en el panel de flujo de correo en el centro de cumplimiento de seguridad de Office 365 &](media/0ef6e2ef-dd22-4363-9d4a-b20a00babc9f.png)

Cuando haga clic en el número de mensajes en cola en **las colas**, los detalles de la cola y aparecerán las instrucciones sobre cómo solucionar el problema en un panel flotante (el mismo emergente que aparece después de hacer clic en **Ver cola** en los detalles de una alerta de cola).

![Detalles de la cola](media/4eb088fe-5dd9-4bf4-b959-c1bb2545c515.png)
