---
title: Supervisar y notificar el estado de la aplicación en Microsoft 365 Security
description: Describe cómo puede obtener más información sobre el uso de aplicaciones en la nube en la organización.
keywords: seguridad, malware, Microsoft 365, M365, Security Center, monitor, Report, apps
ms.prod: w10
ms.mktglfcycl: deploy
ms.localizationpriority: medium
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 02cc511532f65172aba2c0f98cdf594776f586a5
ms.sourcegitcommit: ef27da3ea5340d6e7a2eaa1288e2e005ef8e4788
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2019
ms.locfileid: "30791928"
---
# <a name="monitor-and-report-app-status-in-microsoft-365-security"></a><span data-ttu-id="5cc5a-104">Supervisar y notificar el estado de la aplicación en Microsoft 365 Security</span><span class="sxs-lookup"><span data-stu-id="5cc5a-104">Monitor and report app status in Microsoft 365 security</span></span>

[!include[Prerelease�information](prerelease.md)]

<span data-ttu-id="5cc5a-105">Estos informes proporcionan más información sobre cómo se usan las aplicaciones en la nube en la organización, incluidos los tipos de aplicaciones, su nivel de riesgo y las alertas.</span><span class="sxs-lookup"><span data-stu-id="5cc5a-105">These reports provide more insight into how cloud apps are being used in your organization, including what kinds of apps, their level of risk, and alerts.</span></span>

## <a name="monitor-email-accounts-at-risk"></a><span data-ttu-id="5cc5a-106">Supervisar las cuentas de correo electrónico en riesgo</span><span class="sxs-lookup"><span data-stu-id="5cc5a-106">Monitor email accounts at risk</span></span>

<span data-ttu-id="5cc5a-107">La **protección de correo electrónico** muestra las cuentas de correo electrónico en riesgo.</span><span class="sxs-lookup"><span data-stu-id="5cc5a-107">**Email protection** shows email accounts at risk.</span></span> <span data-ttu-id="5cc5a-108">Puede hacer clic en una cuenta para investigar más en el centro de seguridad de Windows Defender.</span><span class="sxs-lookup"><span data-stu-id="5cc5a-108">You can click an account to investigate further in Windows Defender Security Center.</span></span>

![Tarjeta de protección de correo electrónico](./media/security-docs/email-protection.png)

## <a name="monitor-app-permissions-granted-by-users"></a><span data-ttu-id="5cc5a-110">Supervisar los permisos de aplicación concedidos por los usuarios</span><span class="sxs-lookup"><span data-stu-id="5cc5a-110">Monitor app permissions granted by users</span></span>

<span data-ttu-id="5cc5a-111">**Cloud App Security: aplicaciones de OAuth** enumera las aplicaciones descubiertas por Cloud App Security a las que los usuarios han concedido permisos.</span><span class="sxs-lookup"><span data-stu-id="5cc5a-111">**Cloud App Security - OAuth apps** lists apps discovered by Cloud App Security that have been granted permissions by users.</span></span> <span data-ttu-id="5cc5a-112">El catálogo de riesgos de Cloud App Security incluye más de 16.000 aplicaciones que se evalúan con más de 70 factores de riesgo.</span><span class="sxs-lookup"><span data-stu-id="5cc5a-112">Cloud App Security's risk catalog includes over 16,000 apps that are assessed using over 70 risk factors.</span></span>

<span data-ttu-id="5cc5a-113">Los factores de riesgo comienzan desde información general, como el editor de la aplicación, hasta medidas de seguridad y controles, por ejemplo, si la aplicación admite el cifrado en reposo o proporciona un registro de auditoría de la actividad de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="5cc5a-113">The risk factors start from general information, such as the app publisher, to security measures and controls, such as whether the app supports for encryption at rest or provides an audit log of user activity.</span></span>

![Tarjeta de aplicaciones de OAuth para Cloud App Security](./media/security-docs/cloud-app-security-oauth-apps.png)

## <a name="monitor-cloud-app-user-accounts"></a><span data-ttu-id="5cc5a-115">Supervisar las cuentas de usuario de aplicación de nube</span><span class="sxs-lookup"><span data-stu-id="5cc5a-115">Monitor cloud app user accounts</span></span>

<span data-ttu-id="5cc5a-116">**Cuentas de aplicación de nube para revisión** enumera las cuentas que pueden requerir atención.</span><span class="sxs-lookup"><span data-stu-id="5cc5a-116">**Cloud app accounts for review** lists accounts that may require attention.</span></span>

![Cuentas de aplicación de nube para la tarjeta de revisión](./media/security-docs/cloud-app-accounts-for-review.png)

## <a name="understand-which-cloud-apps-are-used"></a><span data-ttu-id="5cc5a-118">Comprender qué aplicaciones en la nube se usan</span><span class="sxs-lookup"><span data-stu-id="5cc5a-118">Understand which cloud apps are used</span></span>

<span data-ttu-id="5cc5a-119">Las **aplicaciones en la nube detectadas (categorías)** muestran qué tipos de aplicaciones se usan en la organización y vínculos al panel de detección en la nube en Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="5cc5a-119">**Discovered cloud apps (categories)** show what kinds of apps are being used in your organization and links to the Cloud Discovery dashboard in Cloud App Security.</span></span> <span data-ttu-id="5cc5a-120">Para obtener más información, consulte [Inicio rápido: trabajar con aplicaciones detectadas](https://docs.microsoft.com/cloud-app-security/discovered-apps).</span><span class="sxs-lookup"><span data-stu-id="5cc5a-120">For more information, see [Quickstart: Work with discovered apps](https://docs.microsoft.com/cloud-app-security/discovered-apps).</span></span>  

![Tarjeta de categorías de aplicaciones en la nube detectadas](./media/security-docs/discovered-cloud-apps-categories.png)

## <a name="monitor-where-users-access-cloud-apps"></a><span data-ttu-id="5cc5a-122">Supervisar dónde acceden los usuarios a las aplicaciones en la nube</span><span class="sxs-lookup"><span data-stu-id="5cc5a-122">Monitor where users access cloud apps</span></span>

<span data-ttu-id="5cc5a-123">Las **ubicaciones de actividad de aplicación de nube** muestran dónde los usuarios están accediendo a las aplicaciones en la nube.</span><span class="sxs-lookup"><span data-stu-id="5cc5a-123">**Cloud app activity locations** show where users are accessing cloud apps.</span></span>

![Tarjeta de ubicaciones de actividad de aplicación en la nube](./media/security-docs/cloud-app-activity-locations.png)

## <a name="monitor-health-for-infrastructure-workloads"></a><span data-ttu-id="5cc5a-125">Supervisión del estado de las cargas de trabajo de la infraestructura</span><span class="sxs-lookup"><span data-stu-id="5cc5a-125">Monitor health for infrastructure workloads</span></span>

<span data-ttu-id="5cc5a-126">**Estado** de la infraestructura muestra alertas de estado de mantenimiento para cargas de trabajo de infraestructura en el centro de seguridad de Azure.</span><span class="sxs-lookup"><span data-stu-id="5cc5a-126">**Infrastructure health** shows health status alerts for infrastructure workloads in Azure Security Center.</span></span>

<span data-ttu-id="5cc5a-127">El centro de seguridad de Azure proporciona administración de seguridad unificada y protección contra amenazas avanzada a través de cargas de trabajo locales y en la nube.</span><span class="sxs-lookup"><span data-stu-id="5cc5a-127">Azure Security Center provides unified security management and advanced threat protection across on-premises and cloud workloads.</span></span> <span data-ttu-id="5cc5a-128">Puede recopilar, buscar y analizar datos de seguridad de una gran variedad de orígenes, incluidos firewalls y otras soluciones de asociados.</span><span class="sxs-lookup"><span data-stu-id="5cc5a-128">You can collect, search, and analyze security data from a variety of sources, including firewalls and other partner solutions.</span></span>

<span data-ttu-id="5cc5a-129">Para obtener más información, vea la [documentación del centro de seguridad de Azure](https://docs.microsoft.com/azure/security-center/).</span><span class="sxs-lookup"><span data-stu-id="5cc5a-129">For more information, see [Azure Security Center Documentation](https://docs.microsoft.com/azure/security-center/).</span></span>

![Tarjeta de mantenimiento de la infraestructura](./media/security-docs/infrastructure-health.png)
