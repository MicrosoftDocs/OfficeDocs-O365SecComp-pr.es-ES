---
title: Entendimiento de las reglas de flujo de correo lento
ms.author: chrisda
author: chrisda
manager: serdars
ms.date: 5/3/2018
ms.audience: ITPro
ms.topic: article
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 37125cdb-715d-42d0-b669-1a8efa140813
description: Los administradores pueden obtener información sobre el entendimiento de reglas de flujo de correo lento en el panel de flujo de correo en el centro de cumplimiento de seguridad de Office 365 &.
ms.openlocfilehash: 930ea7c57d896c75c6af1333f2bf202b56270199
ms.sourcegitcommit: 25fb33a1f8b2844fde15f6c03db2936c610824e0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2019
ms.locfileid: "28685647"
---
# <a name="slow-mail-flow-rules-insight"></a><span data-ttu-id="b269b-103">Entendimiento de las reglas de flujo de correo lento</span><span class="sxs-lookup"><span data-stu-id="b269b-103">Slow mail flow rules insight</span></span>

<span data-ttu-id="b269b-p101">Reglas de flujo de correo ineficaz (también conocida como reglas de transporte) pueden provocar retrasos de flujo de correo para su organización. Este entendimiento informes de reglas de flujo de correo que tienen un impacto en el flujo de correo de su organización. Ejemplos de estos tipos de reglas son:</span><span class="sxs-lookup"><span data-stu-id="b269b-p101">Inefficient mail flow rules (also known as transport rules) can lead to mail flow delays for your organization. This insight reports mail flow rules that have an impact on your organization's mail flow. Examples of these types of rules are:</span></span>

- <span data-ttu-id="b269b-107">Condiciones que use **es miembro de** para grandes grupos.</span><span class="sxs-lookup"><span data-stu-id="b269b-107">Conditions that use **Is member of** for large groups.</span></span>

- <span data-ttu-id="b269b-108">Condiciones que utiliza la coincidencia de patrones de expresión regular compleja (regex).</span><span class="sxs-lookup"><span data-stu-id="b269b-108">Conditions that use complex regular expression (regex) pattern matching.</span></span>

- <span data-ttu-id="b269b-109">Condiciones que utilice la comprobación de contenido en los datos adjuntos.</span><span class="sxs-lookup"><span data-stu-id="b269b-109">Conditions that use content checking in attachments.</span></span>

<span data-ttu-id="b269b-110">El entendimiento le ayudará a identificar y ajustar las reglas de flujo de correo para ayudar a reducir los retrasos de flujo de correo.</span><span class="sxs-lookup"><span data-stu-id="b269b-110">The insight will help you to identify and fine-tune mail flow rules to help reduce mail flow delays.</span></span>

![Un flujo de correo lento reglas insight en el panel de flujo de correo en el centro de cumplimiento de seguridad de Office 365 &](media/1dd90faa-f065-4b10-8b47-d35dc127fc26.png)

<span data-ttu-id="b269b-p102">Al hacer clic en **Ver detalles**, aparece un panel de emergente donde puede revisar la regla. En el panel emergente, puede hacer clic en **Ver los mensajes de ejemplo** para ver qué tipo de mensajes se ven afectados por la regla.</span><span class="sxs-lookup"><span data-stu-id="b269b-p102">When you click **View details**, a flyout pane appears where you can review the rule. In the flyout pane, can also click **view sample messages** to see what kind of messages are impacted by the rule.</span></span>

![Panel emergente al hacer clic en Ver detalles en un entendimiento de las reglas de flujo de correo lento en el panel de flujo de correo](media/2cbd43b7-1f21-4338-a70c-7b50de5c69cd.png)
