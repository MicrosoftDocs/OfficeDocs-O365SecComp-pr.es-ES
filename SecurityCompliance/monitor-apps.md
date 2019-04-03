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
search.appverid: met150
ms.openlocfilehash: 33a10996ceaf3023d5aee58aaabf3fef54372c30
ms.sourcegitcommit: 8213c353954b92f5c3979bee4aa049da0fd28a18
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/03/2019
ms.locfileid: "31043301"
---
# <a name="monitor-and-report-app-status-in-microsoft-365-security"></a>Supervisar y notificar el estado de la aplicación en Microsoft 365 Security


Estos informes proporcionan más información sobre cómo se usan las aplicaciones en la nube en la organización, incluidos los tipos de aplicaciones, su nivel de riesgo y las alertas.

## <a name="monitor-email-accounts-at-risk"></a>Supervisar las cuentas de correo electrónico en riesgo

La **protección de correo electrónico** muestra las cuentas de correo electrónico en riesgo. Puede hacer clic en una cuenta para investigar más en el centro de seguridad de Windows Defender.

![Tarjeta de protección de correo electrónico](./media/security-docs/email-protection.png)

## <a name="monitor-app-permissions-granted-by-users"></a>Supervisar los permisos de aplicación concedidos por los usuarios

**Cloud App Security: aplicaciones de OAuth** enumera las aplicaciones descubiertas por Cloud App Security a las que los usuarios han concedido permisos. El catálogo de riesgos de Cloud App Security incluye más de 16.000 aplicaciones que se evalúan con más de 70 factores de riesgo.

Los factores de riesgo comienzan desde información general, como el editor de la aplicación, hasta medidas de seguridad y controles, por ejemplo, si la aplicación admite el cifrado en reposo o proporciona un registro de auditoría de la actividad de los usuarios.

![Tarjeta de aplicaciones de OAuth para Cloud App Security](./media/security-docs/cloud-app-security-oauth-apps.png)

## <a name="monitor-cloud-app-user-accounts"></a>Supervisar las cuentas de usuario de aplicación de nube

**Cuentas de aplicación de nube para revisión** enumera las cuentas que pueden requerir atención.

![Cuentas de aplicación de nube para la tarjeta de revisión](./media/security-docs/cloud-app-accounts-for-review.png)

## <a name="understand-which-cloud-apps-are-used"></a>Comprender qué aplicaciones en la nube se usan

Las **aplicaciones en la nube detectadas (categorías)** muestran qué tipos de aplicaciones se usan en la organización y vínculos al panel de detección en la nube en Cloud App Security. Para obtener más información, consulte [Inicio rápido: trabajar con aplicaciones detectadas](https://docs.microsoft.com/cloud-app-security/discovered-apps).  

![Tarjeta de categorías de aplicaciones en la nube detectadas](./media/security-docs/discovered-cloud-apps-categories.png)

## <a name="monitor-where-users-access-cloud-apps"></a>Supervisar dónde acceden los usuarios a las aplicaciones en la nube

Las **ubicaciones de actividad de aplicación de nube** muestran dónde los usuarios están accediendo a las aplicaciones en la nube.

![Tarjeta de ubicaciones de actividad de aplicación en la nube](./media/security-docs/cloud-app-activity-locations.png)

## <a name="monitor-health-for-infrastructure-workloads"></a>Supervisión del estado de las cargas de trabajo de la infraestructura

**Estado** de la infraestructura muestra alertas de estado de mantenimiento para cargas de trabajo de infraestructura en el centro de seguridad de Azure.

El centro de seguridad de Azure proporciona administración de seguridad unificada y protección contra amenazas avanzada a través de cargas de trabajo locales y en la nube. Puede recopilar, buscar y analizar datos de seguridad de una gran variedad de orígenes, incluidos firewalls y otras soluciones de asociados.

Para obtener más información, vea la [documentación del centro de seguridad de Azure](https://docs.microsoft.com/azure/security-center/).

![Tarjeta de mantenimiento de la infraestructura](./media/security-docs/infrastructure-health.png)
