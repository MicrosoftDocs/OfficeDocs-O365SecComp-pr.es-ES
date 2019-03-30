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
ms.sourcegitcommit: e7a776a04ef6ed5e287a33cfdc36aa2d72862b55
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/29/2019
ms.locfileid: "30998613"
---
# <a name="queue-alerts-and-queues"></a><span data-ttu-id="12192-103">Colas y alertas de cola</span><span class="sxs-lookup"><span data-stu-id="12192-103">Queue alerts and Queues</span></span>

## <a name="queue-alerts"></a><span data-ttu-id="12192-104">Alertas de cola</span><span class="sxs-lookup"><span data-stu-id="12192-104">Queue alerts</span></span>

<span data-ttu-id="12192-105">Cuando los mensajes no se pueden enviar desde la organización de Office 365 a los servidores de correo electrónico locales o asociados mediante conectores, los mensajes se colocan en la cola en Office 365.</span><span class="sxs-lookup"><span data-stu-id="12192-105">When messages can't be sent from your Office 365 organization to your on-premises or partner email servers using connectors, the messages are queued in Office 365.</span></span> <span data-ttu-id="12192-106">Algunos ejemplos comunes que causan esta condición son:</span><span class="sxs-lookup"><span data-stu-id="12192-106">Common examples that cause this condition are:</span></span>

- <span data-ttu-id="12192-107">El conector está configurado incorrectamente.</span><span class="sxs-lookup"><span data-stu-id="12192-107">The connector is incorrectly configured.</span></span>

- <span data-ttu-id="12192-108">Ha habido cambios en la red o en el firewall en su entorno local.</span><span class="sxs-lookup"><span data-stu-id="12192-108">There have been networking or firewall changes in your on-premises environment.</span></span>

<span data-ttu-id="12192-109">Office 365 seguirá reintentando la entrega durante 48 horas.</span><span class="sxs-lookup"><span data-stu-id="12192-109">Office 365 will continue to retry to delivery for 48 hours.</span></span> <span data-ttu-id="12192-110">TransCurridos 48 horas, los mensajes expirarán y se devolverán a los remitentes en informes de no entrega (también conocidos como NDR o mensajes de devolución).</span><span class="sxs-lookup"><span data-stu-id="12192-110">After 48 hours, the messages will expire and will be returned to the senders in non-delivery reports (also known as a NDRs or bounce messages).</span></span>

<span data-ttu-id="12192-111">Si el volumen de correo electrónico en cola supera el umbral predefinido (el valor predeterminado es de 2000 mensajes), las alertas estarán disponibles en el panel de flujo de correo en las **alertas recientes**y los administradores recibirán una notificación por correo electrónico (a su dirección de correo electrónico alternativa) .</span><span class="sxs-lookup"><span data-stu-id="12192-111">If the queued email volume exceeds the pre-defined threshold (the default value is 2000 messages), the alerts will be available in the mail flow dashboard at **Recent alerts**, and admins will receive an email notification (to their alternative email address).</span></span> <span data-ttu-id="12192-112">Para configurar el umbral de alerta, el límite de notificaciones diarias y los destinatarios de la alerta, consulte la sección **personalizar colas de alertas** a continuación.</span><span class="sxs-lookup"><span data-stu-id="12192-112">To configure the alert threshold, daily notification limit, and/or recipients of the alert, see the **Customize queue alerts** section below.</span></span>

![Poner alertas en cola en el área de alertas recientes del panel flujo de correo en el centro de seguridad & cumplimiento](media/5fc4a51c-6118-4270-960b-c6b176ef94ae.png)

## <a name="customize-queue-alerts"></a><span data-ttu-id="12192-114">Personalizar alertas de cola</span><span class="sxs-lookup"><span data-stu-id="12192-114">Customize queue alerts</span></span>

<span data-ttu-id="12192-115">Información de flujo de correo cree una directiva de alerta **llamada los mensajes se** han retrasado (la casilla **enviar notificaciones de correo electrónico** en la captura de pantalla de ejemplo siguiente) que se encuentra en **directivas**de alertas de **alertas** \> .</span><span class="sxs-lookup"><span data-stu-id="12192-115">Mail flow insights create an alert policy named **Messages have been delayed** (the **Send email notifications** check box in the example screen shot below) found in **Alerts** \> **Alert Policies**.</span></span> <span data-ttu-id="12192-116">Puede modificar el umbral y los destinatarios de alertas haciendo clic en la Directiva.</span><span class="sxs-lookup"><span data-stu-id="12192-116">You can modify the threshold and alert recipients by clicking on the policy.</span></span>

![Navegación de alertas](media/efb95976-9e0b-484e-a2fd-093c5bc7a40f.png)

<span data-ttu-id="12192-118">Verá una nueva hoja de información de directivas, ahora puede hacer clic en **Editar Directiva**.</span><span class="sxs-lookup"><span data-stu-id="12192-118">You'll see a new policy information blade, you can now click **Edit Policy**.</span></span>

![Editar Directiva](media/ed2aceae-3ee2-4849-a17e-87915987a7dd.png)

<span data-ttu-id="12192-120">La hoja de información cambiará a la **Directiva de edición**.</span><span class="sxs-lookup"><span data-stu-id="12192-120">The information blade will change to the **Edit Policy**.</span></span> <span data-ttu-id="12192-121">Ahora puede cambiar los destinatarios del correo electrónico de alerta, el límite del número de notificaciones enviadas por día y el umbral mínimo para desencadenar la alerta (200 o más).</span><span class="sxs-lookup"><span data-stu-id="12192-121">You can now change the recipients for the alert email, the limit on the number of notifications sent per day, and the minimum threshold to trigger the alert (200 or more).</span></span>

![Editar hoja de directivas](media/c657cc74-7867-474c-b2c9-dc478449f990.png)

## <a name="queue-alert-details"></a><span data-ttu-id="12192-123">Detalles de alerta de cola</span><span class="sxs-lookup"><span data-stu-id="12192-123">Queue alert details</span></span>

<span data-ttu-id="12192-124">Al hacer clic en la alerta, los detalles de la alerta aparecen en un panel flotante.</span><span class="sxs-lookup"><span data-stu-id="12192-124">When you click the alert, the alert details appear in a flyout pane.</span></span>

![Seleccione una alerta de cola en el área de alertas recientes del panel flujo de correo en el centro de seguridad & cumplimiento](media/1f6b0e96-5b2c-41ef-9684-9d813b3fabe6.png)

![El control flotante de alerta de cola en el centro de seguridad & cumplimiento](media/105c8fff-912f-4763-8806-2740ebdecd4b.png)

<span data-ttu-id="12192-127">Puede hacer clic en **Ver cola** en los detalles de alerta para ver los detalles de la cola, los problemas y los vínculos a las correcciones disponibles en un nuevo panel flotante.</span><span class="sxs-lookup"><span data-stu-id="12192-127">You can click **View queue** in the alert details to see the queue details, problems, and links to the available fixes in a new flyout pane.</span></span>

![El control flotante de alerta de cola en el centro de seguridad & cumplimiento](media/8ff60955-55ef-4f32-a966-85e02cb608d1.png)

![Ver la cola en los detalles de alerta](media/4eb088fe-5dd9-4bf4-b959-c1bb2545c515.png)

## <a name="queues"></a><span data-ttu-id="12192-130">Colas</span><span class="sxs-lookup"><span data-stu-id="12192-130">Queues</span></span>

<span data-ttu-id="12192-131">Incluso si el volumen de mensajes en cola no ha superado el umbral, puede seguir usando el área **colas** del panel flujo de correo para ver los mensajes que se han puesto en cola durante más de una hora.</span><span class="sxs-lookup"><span data-stu-id="12192-131">Even if the queued message volume hasn't exceeded the threshold, you can still use the **Queues** area of the mail flow dashboard to see messages that have been queued for more than one hour.</span></span> <span data-ttu-id="12192-132">Puede usar el área **colas** para supervisar el número de mensajes en cola (el valor 0 indica que el flujo de correo es aceptable) y realizar una acción antes de que el número de mensajes en cola sea demasiado grande.</span><span class="sxs-lookup"><span data-stu-id="12192-132">You can use the **Queues** area to monitor the number of queued messages (the value 0 indicates mail flow is OK) and take action before the number of queued messages becomes too large.</span></span>

![Colas del panel de flujo de correo en el centro de seguridad & cumplimiento](media/0ef6e2ef-dd22-4363-9d4a-b20a00babc9f.png)

<span data-ttu-id="12192-134">Al hacer clic en el número de mensajes en cola en las **colas**, los detalles de la cola y la orientación sobre cómo corregir el problema aparecerán en un panel flotante (el mismo control flotante que aparece después de hacer clic en **Ver cola** en detalles de una alerta de cola).</span><span class="sxs-lookup"><span data-stu-id="12192-134">When you click the number of queued messages in **Queues**, the queue details and guidance for how to fix the issue will appear in a flyout pane (the same flyout that appears after you click **View queue** in the details of a queue alert).</span></span>

![Detalles de la cola](media/4eb088fe-5dd9-4bf4-b959-c1bb2545c515.png)

## <a name="see-also"></a><span data-ttu-id="12192-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="12192-136">See also</span></span>

<span data-ttu-id="12192-137">Para obtener más información acerca de otras indicaciones de flujo de correo en el panel de flujo de correo, consulte [mail Flow Insights en el centro de seguridad _AMP_ cumplimiento](mail-flow-insights.md).</span><span class="sxs-lookup"><span data-stu-id="12192-137">For more information about other mail flow insights in the mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights.md).</span></span>
