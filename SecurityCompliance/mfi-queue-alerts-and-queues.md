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
# <a name="queue-alerts-and-queues"></a><span data-ttu-id="a45b9-103">Alertas de cola y colas</span><span class="sxs-lookup"><span data-stu-id="a45b9-103">Queue alerts and Queues</span></span>

## <a name="queue-alerts"></a><span data-ttu-id="a45b9-104">Alertas de cola</span><span class="sxs-lookup"><span data-stu-id="a45b9-104">Queue alerts</span></span>

<span data-ttu-id="a45b9-p101">Cuando no se puede enviar los mensajes de la organización de Office 365 a su local o los servidores de correo electrónico de asociados mediante conectores, los mensajes se ponen en cola en Office 365. Ejemplos comunes que provocar esta condición son:</span><span class="sxs-lookup"><span data-stu-id="a45b9-p101">When messages can't be sent from your Office 365 organization to your on-premises or partner email servers using connectors, the messages are queued in Office 365. Common examples that cause this condition are:</span></span>

- <span data-ttu-id="a45b9-107">El conector está configurado correctamente.</span><span class="sxs-lookup"><span data-stu-id="a45b9-107">The connector is incorrectly configured.</span></span>

- <span data-ttu-id="a45b9-108">Ha habido cambios de red o firewall en su entorno local.</span><span class="sxs-lookup"><span data-stu-id="a45b9-108">There have been networking or firewall changes in your on-premises environment.</span></span>

<span data-ttu-id="a45b9-p102">Office 365 seguirá intentando a la entrega durante 48 horas. Después de 48 horas, los mensajes caducará y se devolverá a los remitentes en informes de no entrega (también conocido como un NDR o rebote a mensajes).</span><span class="sxs-lookup"><span data-stu-id="a45b9-p102">Office 365 will continue to retry to delivery for 48 hours. After 48 hours, the messages will expire and will be returned to the senders in non-delivery reports (also known as a NDRs or bounce messages).</span></span>

<span data-ttu-id="a45b9-p103">Si el volumen de correo electrónico en cola supera el umbral predefinido (el valor predeterminado es 2000 mensajes), las alertas estará disponibles en el panel de flujo de correo en **las alertas recientes**y administradores recibirán una notificación de correo electrónico (a su dirección de correo electrónico alternativo) . Para configurar el umbral de alerta, límite diario de notificación, o los destinatarios de la alerta, vea la sección de **alertas de cola de personalizar** más adelante.</span><span class="sxs-lookup"><span data-stu-id="a45b9-p103">If the queued email volume exceeds the pre-defined threshold (the default value is 2000 messages), the alerts will be available in the mail flow dashboard at **Recent alerts**, and admins will receive an email notification (to their alternative email address). To configure the alert threshold, daily notification limit, and/or recipients of the alert, see the **Customize queue alerts** section below.</span></span>

![Alertas de cola en el área de alertas recientes del panel de flujo de correo en el centro de cumplimiento de seguridad de Office 365 &](media/5fc4a51c-6118-4270-960b-c6b176ef94ae.png)

## <a name="customize-queue-alerts"></a><span data-ttu-id="a45b9-114">Personalizar las alertas de cola</span><span class="sxs-lookup"><span data-stu-id="a45b9-114">Customize queue alerts</span></span>

<span data-ttu-id="a45b9-p104">Entendimiento del flujo de correo crea una directiva de alerta con nombre **los mensajes se han retrasado** (la casilla de verificación **Enviar notificaciones de correo electrónico** en el ejemplo, se captura de pantalla siguiente) que se encuentra en **las alertas de** \> **Las directivas de alerta**. Puede modificar a los destinatarios del umbral y alerta haciendo clic en la directiva.</span><span class="sxs-lookup"><span data-stu-id="a45b9-p104">Mail flow insights create an alert policy named **Messages have been delayed** (the **Send email notifications** check box in the example screen shot below) found in **Alerts** \> **Alert Policies**. You can modify the threshold and alert recipients by clicking on the policy.</span></span>

![Exploración de las alertas](media/efb95976-9e0b-484e-a2fd-093c5bc7a40f.png)

<span data-ttu-id="a45b9-118">Verá un nuevo blade de información de la directiva, ahora puede hacer clic en **Editar directiva**.</span><span class="sxs-lookup"><span data-stu-id="a45b9-118">You'll see a new policy information blade, you can now click **Edit Policy**.</span></span>

![Directiva de edición ](media/ed2aceae-3ee2-4849-a17e-87915987a7dd.png)

<span data-ttu-id="a45b9-p105">El servidor blade de información cambiará a la **Directiva de edición**. Ahora puede cambiar a los destinatarios de la alerta por correo electrónico, el límite en el número de notificaciones enviadas por día y el umbral mínimo para desencadenar la alerta (200 o más).</span><span class="sxs-lookup"><span data-stu-id="a45b9-p105">The information blade will change to the **Edit Policy**. You can now change the recipients for the alert email, the limit on the number of notifications sent per day, and the minimum threshold to trigger the alert (200 or more).</span></span>

![Editar directiva Blade](media/c657cc74-7867-474c-b2c9-dc478449f990.png)

## <a name="queue-alert-details"></a><span data-ttu-id="a45b9-123">Detalles de la alerta cola</span><span class="sxs-lookup"><span data-stu-id="a45b9-123">Queue alert details</span></span>

<span data-ttu-id="a45b9-124">Al hacer clic en la alerta, los detalles de alerta aparecen en un panel flotante.</span><span class="sxs-lookup"><span data-stu-id="a45b9-124">When you click the alert, the alert details appear in a flyout pane.</span></span>

![Seleccione una alerta de cola en el área de alertas recientes del panel de flujo de correo en el centro de cumplimiento de seguridad de Office 365 &](media/1f6b0e96-5b2c-41ef-9684-9d813b3fabe6.png)

![El emergente de detalles de alerta de cola en el centro de cumplimiento de seguridad de Office 365 &](media/105c8fff-912f-4763-8806-2740ebdecd4b.png)

<span data-ttu-id="a45b9-127">Puede hacer clic en **Ver cola** en los detalles de alerta para ver los detalles de la cola, problemas y vínculos a las revisiones disponibles en un nuevo panel emergente.</span><span class="sxs-lookup"><span data-stu-id="a45b9-127">You can click **View queue** in the alert details to see the queue details, problems, and links to the available fixes in a new flyout pane.</span></span>

![El emergente de detalles de alerta de cola en el centro de cumplimiento de seguridad de Office 365 &](media/8ff60955-55ef-4f32-a966-85e02cb608d1.png)

![Ver la cola en los detalles de alerta](media/4eb088fe-5dd9-4bf4-b959-c1bb2545c515.png)

## <a name="queues"></a><span data-ttu-id="a45b9-130">Colas</span><span class="sxs-lookup"><span data-stu-id="a45b9-130">Queues</span></span>

<span data-ttu-id="a45b9-p106">Incluso si el volumen de mensaje en cola no ha superado el umbral, aún puede usar el área de **colas** del panel de flujo de correo para ver los mensajes que se ha puesto en cola durante más de una hora. Puede usar el área de **colas** para supervisar el número de mensajes en cola (el valor 0 indica el flujo de correo es Aceptar) y tomar medidas antes de que el número de mensajes en cola se convierte en un tamaño demasiado grande.</span><span class="sxs-lookup"><span data-stu-id="a45b9-p106">Even if the queued message volume hasn't exceeded the threshold, you can still use the **Queues** area of the mail flow dashboard to see messages that have been queued for more than one hour. You can use the **Queues** area to monitor the number of queued messages (the value 0 indicates mail flow is OK) and take action before the number of queued messages becomes too large.</span></span>

![Colas en el panel de flujo de correo en el centro de cumplimiento de seguridad de Office 365 &](media/0ef6e2ef-dd22-4363-9d4a-b20a00babc9f.png)

<span data-ttu-id="a45b9-134">Cuando haga clic en el número de mensajes en cola en **las colas**, los detalles de la cola y aparecerán las instrucciones sobre cómo solucionar el problema en un panel flotante (el mismo emergente que aparece después de hacer clic en **Ver cola** en los detalles de una alerta de cola).</span><span class="sxs-lookup"><span data-stu-id="a45b9-134">When you click the number of queued messages in **Queues**, the queue details and guidance for how to fix the issue will appear in a flyout pane (the same flyout that appears after you click **View queue** in the details of a queue alert).</span></span>

![Detalles de la cola](media/4eb088fe-5dd9-4bf4-b959-c1bb2545c515.png)
