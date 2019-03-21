---
title: Reporte de reglas de flujo de correo lento
ms.author: chrisda
author: chrisda
manager: serdars
ms.date: 5/3/2018
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 37125cdb-715d-42d0-b669-1a8efa140813
description: Los administradores pueden obtener información sobre las reglas de flujo de correo lentas Insight en el panel del flujo de correo en el centro de seguridad & cumplimiento de Office 365.
ms.openlocfilehash: e1ce23c94cd5260d8a7a7ebd99521a4a6f5c7b0a
ms.sourcegitcommit: fec1010e405f14e792d650aee0312b78fced3343
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/21/2019
ms.locfileid: "30720260"
---
# <a name="slow-mail-flow-rules-insight"></a><span data-ttu-id="161b5-103">Reporte de reglas de flujo de correo lento</span><span class="sxs-lookup"><span data-stu-id="161b5-103">Slow mail flow rules insight</span></span>

<span data-ttu-id="161b5-104">Las reglas de flujo de correo ineficiente (también conocidas como reglas de transporte) pueden llevar a retrasos en el flujo de correo de la organización.</span><span class="sxs-lookup"><span data-stu-id="161b5-104">Inefficient mail flow rules (also known as transport rules) can lead to mail flow delays for your organization.</span></span> <span data-ttu-id="161b5-105">Esta visión informa de las reglas de flujo de correo que afectan al flujo de correo de su organización.</span><span class="sxs-lookup"><span data-stu-id="161b5-105">This insight reports mail flow rules that have an impact on your organization's mail flow.</span></span> <span data-ttu-id="161b5-106">Algunos ejemplos de estos tipos de reglas son:</span><span class="sxs-lookup"><span data-stu-id="161b5-106">Examples of these types of rules are:</span></span>

- <span data-ttu-id="161b5-107">Condiciones que usan **son miembros de** grupos grandes.</span><span class="sxs-lookup"><span data-stu-id="161b5-107">Conditions that use **Is member of** for large groups.</span></span>

- <span data-ttu-id="161b5-108">Condiciones que usan la coincidencia de patrón de expresiones regulares complejas (regex).</span><span class="sxs-lookup"><span data-stu-id="161b5-108">Conditions that use complex regular expression (regex) pattern matching.</span></span>

- <span data-ttu-id="161b5-109">Condiciones que usan la comprobación de contenido en datos adjuntos.</span><span class="sxs-lookup"><span data-stu-id="161b5-109">Conditions that use content checking in attachments.</span></span>

<span data-ttu-id="161b5-110">La información le ayudará a identificar y ajustar las reglas de flujo de correo para ayudar a reducir los retrasos del flujo de correo.</span><span class="sxs-lookup"><span data-stu-id="161b5-110">The insight will help you to identify and fine-tune mail flow rules to help reduce mail flow delays.</span></span>

![Una lenta Introducción A las reglas de flujo de correo en el panel de flujo de correo en el centro de seguridad & cumplimiento de Office 365](media/1dd90faa-f065-4b10-8b47-d35dc127fc26.png)

<span data-ttu-id="161b5-112">Al hacer clic en **Ver detalles**, aparece un panel flotante donde puede revisar la regla.</span><span class="sxs-lookup"><span data-stu-id="161b5-112">When you click **View details**, a flyout pane appears where you can review the rule.</span></span> <span data-ttu-id="161b5-113">En el panel de flotante, también puede hacer clic en **Ver mensajes de muestra** para ver el tipo de mensajes que se ven afectados por la regla.</span><span class="sxs-lookup"><span data-stu-id="161b5-113">In the flyout pane, can also click **view sample messages** to see what kind of messages are impacted by the rule.</span></span>

![Panel flotante después de hacer clic en ver detalles en una ventana de flujo de correo lenta información sobre las reglas del panel flujo de correo](media/2cbd43b7-1f21-4338-a70c-7b50de5c69cd.png)

## <a name="see-also"></a><span data-ttu-id="161b5-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="161b5-115">See also</span></span>

<span data-ttu-id="161b5-116">Para obtener más información acerca de otras indicaciones de flujo de correo en el panel de flujo de correo, consulte [mail Flow Insights en el centro de seguridad _AMP_ cumplimiento](mail-flow-insights.md).</span><span class="sxs-lookup"><span data-stu-id="161b5-116">For more information about other mail flow insights in the mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights.md).</span></span>
