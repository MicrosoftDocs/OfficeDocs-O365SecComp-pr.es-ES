---
title: Informe de mapa de flujo de correo
ms.author: chrisda
author: chrisda
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
description: Los administradores pueden obtener información sobre el informe de mapa de flujo de correo en el panel de flujo de correo en el centro de seguridad & cumplimiento.
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: bd05ff5cb78adb9dd89dbe3f69c2c3a78d2b1df9
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32252458"
---
# <a name="mail-flow-map-report"></a><span data-ttu-id="9425d-103">Informe de mapa de flujo de correo</span><span class="sxs-lookup"><span data-stu-id="9425d-103">Mail flow map report</span></span>

> [!NOTE]
> <span data-ttu-id="9425d-104">Las características descritas en este tema no se han implementado en todas las organizaciones de Office 365 y están sujetas a cambios.</span><span class="sxs-lookup"><span data-stu-id="9425d-104">The features described in this topic haven't been deployed to all Office 365 organizations, and are subject to change.</span></span>

<span data-ttu-id="9425d-105">Este informe proporciona información sobre cómo fluye el correo a través de la organización de Office 365.</span><span class="sxs-lookup"><span data-stu-id="9425d-105">This report gives insights as to how mail flows through your Office 365 organization.</span></span> <span data-ttu-id="9425d-106">Puede usar esta información para aprender patrones, identificar anomalías y corregir problemas a medida que se produzcan.</span><span class="sxs-lookup"><span data-stu-id="9425d-106">You can use this information to learn patterns, identify anomalies, and fix issues as they arise.</span></span>

![El informe de mapa de flujo de correo en el panel de flujo de correo en el centro de seguridad & cumplimiento](media/mail-flow-map-selected.png)

## <a name="mail-flow-map-widget"></a><span data-ttu-id="9425d-108">Widget de mapa de flujo de correo</span><span class="sxs-lookup"><span data-stu-id="9425d-108">Mail flow map widget</span></span>

<span data-ttu-id="9425d-109">De forma predeterminada, el mapa de flujo de correo muestra el patrón de flujo de correo de alto nivel del día anterior.</span><span class="sxs-lookup"><span data-stu-id="9425d-109">By default, the mail flow map shows the high level mail flow pattern from the previous day.</span></span> <span data-ttu-id="9425d-110">Puede usar las flechas izquierda y derecha para los distintos días.</span><span class="sxs-lookup"><span data-stu-id="9425d-110">You can use the left and right arrows for different days.</span></span> <span data-ttu-id="9425d-111">Al colocar el cursor del mouse sobre cada área del informe, se mostrará el volumen de correo desde y hacia la organización de Office 365, tal como se muestra en el siguiente diagrama:</span><span class="sxs-lookup"><span data-stu-id="9425d-111">Hovering your mouse cursor over each area in the report will show the volume of mail to and from your Office 365 organization as shown in the following diagram:</span></span>

![Flechas izquierda y derecha en el widget mapa de flujo de correo](media/mail-flow-map-widget.png)

## <a name="overview"></a><span data-ttu-id="9425d-113">Información general</span><span class="sxs-lookup"><span data-stu-id="9425d-113">Overview</span></span>

<span data-ttu-id="9425d-114">Al hacer clic en el widget **mapa de flujo de correo** , irá al informe de mapa de flujo de **correo** .</span><span class="sxs-lookup"><span data-stu-id="9425d-114">Clicking on the **Mail flow map** widget will take you to the **Mail flow map** report.</span></span> <span data-ttu-id="9425d-115">Aquí puede ver el nivel de informe más granular, puede hacer clic en ver tabla de detalles para ver los datos detallados.</span><span class="sxs-lookup"><span data-stu-id="9425d-115">Here you can see more granular level of report, you can click View details table to see detailed data.</span></span> <span data-ttu-id="9425d-116">También puede descargar el informe detallado haciendo clic en Request Report.</span><span class="sxs-lookup"><span data-stu-id="9425d-116">You can also download the detailed report by clicking Request report.</span></span>

![Vista general en el informe de mapa de flujo de correo](media/mail-flow-map-overview.png)

## <a name="details"></a><span data-ttu-id="9425d-118">Detalles</span><span class="sxs-lookup"><span data-stu-id="9425d-118">Details</span></span>

<span data-ttu-id="9425d-119">De forma predeterminada, **Mostrar datos para** se establece en el valor **información general**.</span><span class="sxs-lookup"><span data-stu-id="9425d-119">By default, **Show data for** is set to the value **Overview**.</span></span> <span data-ttu-id="9425d-120">Al hacer clic en la lista desplegable y seleccionar **detalles**, la vista cambia a los detalles del nivel de dominio.</span><span class="sxs-lookup"><span data-stu-id="9425d-120">When you click on the drop down and select **Detail**, the view switches to the domain level detail.</span></span>

![Seleccione detalle en Mostrar datos para en la vista de información general en el informe de mapa de flujo de correo](media/mail-flow-map-select-detail.png)

<span data-ttu-id="9425d-122">Se enumeran los dominios principales de remitente y destinatario, y el resto se colocará en **otros** como se muestra en los siguientes diagramas:</span><span class="sxs-lookup"><span data-stu-id="9425d-122">The top sender and recipient domains are listed, and the rest will be put in **Others** as shown in the following diagrams:</span></span>

![Vista de detalles en el informe de mapa de flujo de correo](media/mail-flow-map-detail.png)

## <a name="related-insights"></a><span data-ttu-id="9425d-124">Información relacionada</span><span class="sxs-lookup"><span data-stu-id="9425d-124">Related insights</span></span>

<span data-ttu-id="9425d-125">La información relacionada se muestra debajo del mapa de flujo de correo si está disponible (por ejemplo, el conocimiento del dominio del remitente o el conocimiento del bucle de correo).</span><span class="sxs-lookup"><span data-stu-id="9425d-125">Related insights are shown beneath the Mail flow map if they're available (for example, the Sender domain insight or the Mail loop insight).</span></span>

## <a name="see-also"></a><span data-ttu-id="9425d-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="9425d-126">See also</span></span>

<span data-ttu-id="9425d-127">Para obtener más información acerca de otras indicaciones de flujo de correo en el panel de flujo de correo, consulte [mail Flow Insights en el centro de seguridad _AMP_ cumplimiento](mail-flow-insights-v2.md).</span><span class="sxs-lookup"><span data-stu-id="9425d-127">For more information about other mail flow insights in the mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>