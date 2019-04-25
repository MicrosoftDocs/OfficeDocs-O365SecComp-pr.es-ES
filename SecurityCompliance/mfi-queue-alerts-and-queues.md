---
title: Colas y alertas de cola
ms.author: chrisda
author: chrisda
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 37640c80-ce6f-47e2-afd1-bc1d3c50e637
description: Los administradores pueden obtener información sobre las alertas de cola y las colas del panel del flujo de correo en el centro de seguridad & cumplimiento.
ms.openlocfilehash: 490665bb6b062c5a0b93c988adea9eeb9827cb86
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32267724"
---
# <a name="queue-alerts-and-queues"></a>Colas y alertas de cola

## <a name="queue-alerts"></a>Alertas de cola

Cuando los mensajes no se pueden enviar desde la organización de Office 365 a los servidores de correo electrónico locales o asociados mediante conectores, los mensajes se colocan en la cola en Office 365. Algunos ejemplos comunes que causan esta condición son:

- El conector está configurado incorrectamente.

- Ha habido cambios en la red o en el firewall en su entorno local.

Office 365 seguirá reintentando la entrega durante 48 horas. TransCurridos 48 horas, los mensajes expirarán y se devolverán a los remitentes en informes de no entrega (también conocidos como NDR o mensajes de devolución).

Si el volumen de correo electrónico en cola supera el umbral predefinido (el valor predeterminado es de 2000 mensajes), las alertas estarán disponibles en el panel de flujo de correo en las **alertas recientes**y los administradores recibirán una notificación por correo electrónico (a su dirección de correo electrónico alternativa) . Para configurar el umbral de alerta, el límite de notificaciones diarias y los destinatarios de la alerta, consulte la sección **personalizar colas de alertas** a continuación.

![Poner alertas en cola en el área de alertas recientes del panel flujo de correo en el centro de seguridad & cumplimiento](media/5fc4a51c-6118-4270-960b-c6b176ef94ae.png)

## <a name="customize-queue-alerts"></a>Personalizar alertas de cola

Información de flujo de correo cree una directiva de alerta **llamada los mensajes se** han retrasado (la casilla **enviar notificaciones de correo electrónico** en la captura de pantalla de ejemplo siguiente) que se encuentra en **directivas**de alertas de **alertas** \> . Puede modificar el umbral y los destinatarios de alertas haciendo clic en la Directiva.

![Navegación de alertas](media/efb95976-9e0b-484e-a2fd-093c5bc7a40f.png)

Verá una nueva hoja de información de directivas, ahora puede hacer clic en **Editar Directiva**.

![Editar Directiva](media/ed2aceae-3ee2-4849-a17e-87915987a7dd.png)

La hoja de información cambiará a la **Directiva de edición**. Ahora puede cambiar los destinatarios del correo electrónico de alerta, el límite del número de notificaciones enviadas por día y el umbral mínimo para desencadenar la alerta (200 o más).

![Editar hoja de directivas](media/c657cc74-7867-474c-b2c9-dc478449f990.png)

## <a name="queue-alert-details"></a>Detalles de alerta de cola

Al hacer clic en la alerta, los detalles de la alerta aparecen en un panel flotante.

![Seleccione una alerta de cola en el área de alertas recientes del panel flujo de correo en el centro de seguridad & cumplimiento](media/1f6b0e96-5b2c-41ef-9684-9d813b3fabe6.png)

![El control flotante de alerta de cola en el centro de seguridad & cumplimiento](media/105c8fff-912f-4763-8806-2740ebdecd4b.png)

Puede hacer clic en **Ver cola** en los detalles de alerta para ver los detalles de la cola, los problemas y los vínculos a las correcciones disponibles en un nuevo panel flotante.

![El control flotante de alerta de cola en el centro de seguridad & cumplimiento](media/8ff60955-55ef-4f32-a966-85e02cb608d1.png)

![Ver la cola en los detalles de alerta](media/4eb088fe-5dd9-4bf4-b959-c1bb2545c515.png)

## <a name="queues"></a>Colas

Incluso si el volumen de mensajes en cola no ha superado el umbral, puede seguir usando el área **colas** del panel flujo de correo para ver los mensajes que se han puesto en cola durante más de una hora. Puede usar el área **colas** para supervisar el número de mensajes en cola (el valor 0 indica que el flujo de correo es aceptable) y realizar una acción antes de que el número de mensajes en cola sea demasiado grande.

![Colas del panel de flujo de correo en el centro de seguridad & cumplimiento](media/0ef6e2ef-dd22-4363-9d4a-b20a00babc9f.png)

Al hacer clic en el número de mensajes en cola en las **colas**, los detalles de la cola y la orientación sobre cómo corregir el problema aparecerán en un panel flotante (el mismo control flotante que aparece después de hacer clic en **Ver cola** en detalles de una alerta de cola).

![Detalles de la cola](media/4eb088fe-5dd9-4bf4-b959-c1bb2545c515.png)

## <a name="see-also"></a>Recursos adicionales

Para obtener más información acerca de otras indicaciones de flujo de correo en el panel de flujo de correo, consulte [mail Flow Insights en el centro de seguridad _AMP_ cumplimiento](mail-flow-insights.md).
