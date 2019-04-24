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
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32252588"
---
# <a name="smtp-auth-clients-report"></a><span data-ttu-id="26ecb-103">Informe de clientes de autenticación SMTP</span><span class="sxs-lookup"><span data-stu-id="26ecb-103">SMTP Auth clients report</span></span>

> [!NOTE]
> <span data-ttu-id="26ecb-104">Las características descritas en este tema no se han implementado en todas las organizaciones de Office 365 y están sujetas a cambios.</span><span class="sxs-lookup"><span data-stu-id="26ecb-104">The features described in this topic haven't been deployed to all Office 365 organizations, and are subject to change.</span></span>

<span data-ttu-id="26ecb-105">El informe de **clientes de autenticación SMTP** resalta el uso del Protocolo de envío de cliente de autenticación SMTP por parte de los usuarios o las cuentas de sistema de la organización.</span><span class="sxs-lookup"><span data-stu-id="26ecb-105">The **SMTP Auth clients** report highlights the use of the SMTP Auth client submission protocol by users or system accounts in your organization.</span></span> <span data-ttu-id="26ecb-106">Este protocolo heredado (que usa el punto de conexión smtp.office365.com) solo ofrece autenticación básica y es vulnerable a su uso por parte de cuentas comprometidas para enviar correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="26ecb-106">This legacy protocol (which uses the endpoint smtp.office365.com) only offers Basic authentication, and is susceptible to being used by compromised accounts to send email.</span></span>  <span data-ttu-id="26ecb-107">Este informe le permite comprobar actividades inusuales.</span><span class="sxs-lookup"><span data-stu-id="26ecb-107">This report allows you to check for unusual activity.</span></span> <span data-ttu-id="26ecb-108">También muestra los datos de uso de TLS para clientes o dispositivos que usan SMTP AUTH.</span><span class="sxs-lookup"><span data-stu-id="26ecb-108">It also shows the TLS usage data for clients or devices using SMTP Auth.</span></span>

<span data-ttu-id="26ecb-109">El widget que se muestra en el panel de flujo de correo indica el número de usuarios o cuentas de servicio que han usado el protocolo de autenticación SMTP en los últimos 7 días.</span><span class="sxs-lookup"><span data-stu-id="26ecb-109">The widget that's shown in the Mail Flow dashboard indicates the number of users or service accounts that have used the SMTP Auth protocol in the last 7 days.</span></span>

![El informe de clientes de autenticación SMTP del panel de flujo de correo en el centro de seguridad & cumplimiento](media/smtp-auth-clients-report-selected.png)

<span data-ttu-id="26ecb-111">Al hacer clic en el widget, se abre un control flotante que proporciona una vista agregada del uso y los volúmenes de TLS para la semana pasada.</span><span class="sxs-lookup"><span data-stu-id="26ecb-111">Clicking on the widget opens a flyout that provides an aggregated view of the TLS usage and volumes for the last week.</span></span>

![El control flotante en el informe de clientes de autenticación SMTP](media/smtp-auth-clients-flyout.png)

<span data-ttu-id="26ecb-113">Al hacer clic en el vínculo de **Informe clientes de autenticación SMTP** , verá dos tablas dinámicas de datos principales y dos vistas de datos.</span><span class="sxs-lookup"><span data-stu-id="26ecb-113">When you click on the **SMTP Auth Clients Report** link, you'll see two main data pivots and two data views.</span></span> <span data-ttu-id="26ecb-114">Las tablas dinámicas de datos son el **volumen de envío** y el **uso de TLS**.</span><span class="sxs-lookup"><span data-stu-id="26ecb-114">The data pivots are the **Sending Volume** and **TLS Usage**.</span></span> <span data-ttu-id="26ecb-115">Las vistas de datos son el gráfico y la tabla de detalles.</span><span class="sxs-lookup"><span data-stu-id="26ecb-115">The data views are the chart and the details table.</span></span>

<span data-ttu-id="26ecb-116">La vista **volumen de envío** muestra el número de mensajes que se enviaron con SMTP AUTH para el intervalo de tiempo especificado.</span><span class="sxs-lookup"><span data-stu-id="26ecb-116">The **Sending Volume** view shows the number of messages that were sent using SMTP Auth for the specified time range.</span></span> <span data-ttu-id="26ecb-117">Puede ajustar el rango haciendo clic en **filtros**.</span><span class="sxs-lookup"><span data-stu-id="26ecb-117">You can adjust the range by clicking **Filters**.</span></span> <span data-ttu-id="26ecb-118">El gráfico está organizado por dominio de remitente.</span><span class="sxs-lookup"><span data-stu-id="26ecb-118">The chart is organized by sender domain.</span></span> <span data-ttu-id="26ecb-119">Puede ver datos independientes para cada dominio seleccionando el dominio en el menú **Mostrar datos para** .</span><span class="sxs-lookup"><span data-stu-id="26ecb-119">You can see separate data for each domain by selecting the domain in the **Show data for** drop down.</span></span>

![Envío de volumen en el informe de clientes de autenticación SMTP](media/smtp-auth-clients-report-sending-volume.png)

<span data-ttu-id="26ecb-121">Puede ver información detallada sobre los remitentes y sus recuentos de mensajes haciendo clic en **ver tabla de detalles**.</span><span class="sxs-lookup"><span data-stu-id="26ecb-121">You can view detailed information about the senders and their message counts by clicking **View details table**.</span></span> <span data-ttu-id="26ecb-122">Para volver al gráfico, haga clic en **Ver informe**.</span><span class="sxs-lookup"><span data-stu-id="26ecb-122">To return to the chart, click **View report**.</span></span>

![Tabla de detalles para enviar el volumen en el informe de clientes de autenticación SMTP](media/smtp-auth-clients-report-details-sending-volume.png)

<span data-ttu-id="26ecb-124">La tabla dinámica de **uso de TLS** es importante debido al próximo desuso de TLS 1.0 y TLS 1.1 en Office 365.</span><span class="sxs-lookup"><span data-stu-id="26ecb-124">The **TLS Usage** pivot is important due to the upcoming deprecation of TLS1.0 and TLS1.1 in Office 365.</span></span> <span data-ttu-id="26ecb-125">Muchos dispositivos y aplicaciones heredados no podrán enviar correo electrónico si solo pueden usar TLS 1.0 con autenticación SMTP. Esta tabla dinámica le permite identificar y realizar acciones en usuarios y cuentas del sistema que todavía usan versiones anteriores de TLS.</span><span class="sxs-lookup"><span data-stu-id="26ecb-125">Many legacy devices and applications will be unable to send email if they are only capable of using TLS1.0 with SMTP Auth. This pivot allows you to identify and take action on users and system accounts that are still using older versions of TLS.</span></span>

![Uso de TLS en el informe de clientes de autenticación SMTP](media/smtp-auth-clients-report-tls-usage.png)

<span data-ttu-id="26ecb-127">Puede ver información detallada sobre los remitentes, las versiones de TLS que están usando con la autenticación SMTP y sus recuentos de mensajes haciendo clic en **ver tabla de detalles**.</span><span class="sxs-lookup"><span data-stu-id="26ecb-127">You can view detailed information about the senders, the versions of TLS they are using with SMTP Auth, and their message counts by clicking **View details table**.</span></span> <span data-ttu-id="26ecb-128">Para volver al gráfico, haga clic en **Ver informe**.</span><span class="sxs-lookup"><span data-stu-id="26ecb-128">To return to the chart, click **View report**.</span></span>

<span data-ttu-id="26ecb-129">También puede descargar una versión más detallada del informe haciendo clic en solicitar informe.</span><span class="sxs-lookup"><span data-stu-id="26ecb-129">You can also download a more detailed version of the report by clicking Request report.</span></span>

![Tabla de detalles del uso de TLS en el informe de clientes de autenticación SMTP](media/smtp-auth-clients-report-details-tls-usage.png)

## <a name="see-also"></a><span data-ttu-id="26ecb-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="26ecb-131">See also</span></span>

<span data-ttu-id="26ecb-132">Para obtener más información acerca de otras indicaciones de flujo de correo en el panel de flujo de correo, consulte [mail Flow Insights en el centro de seguridad _AMP_ cumplimiento](mail-flow-insights-v2.md).</span><span class="sxs-lookup"><span data-stu-id="26ecb-132">For more information about other mail flow insights in the mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
