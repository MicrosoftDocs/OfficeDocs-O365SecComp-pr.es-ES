---
title: Investigar la actividad en Office 365 Cloud App Security
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 2/26/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 15fa4545-28b4-4dd4-bf85-88e0926bd5fc
description: 'Con la seguridad de la aplicación de nube de Office 365, puede ver lo que sucede en el entorno de Office 365, ¿está buscando a través de instructora actividades y cuentas. '
ms.openlocfilehash: d988a86c5ceaa2ec46bc27f1aaff540fa3e0b3b4
ms.sourcegitcommit: 9034809b6f308bedc3b8ddcca8242586b5c30f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2019
ms.locfileid: "28014902"
---
# <a name="investigate-an-activity-in-office-365-cloud-app-security"></a><span data-ttu-id="adfcd-103">Investigar la actividad en Office 365 Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="adfcd-103">Investigate an activity in Office 365 Cloud App Security</span></span>
  
|<span data-ttu-id="adfcd-104">Evaluación **\>**</span><span class="sxs-lookup"><span data-stu-id="adfcd-104">\*\*\*\*Evaluation\*\* \>\*\*</span></span>|<span data-ttu-id="adfcd-105">Planeación de **\>**</span><span class="sxs-lookup"><span data-stu-id="adfcd-105">\*\*\*\*Planning\*\* \>\*\*</span></span>|<span data-ttu-id="adfcd-106">Implementación **\>**</span><span class="sxs-lookup"><span data-stu-id="adfcd-106">\*\*\*\*Deployment\*\* \>\*\*</span></span>|<span data-ttu-id="adfcd-107">Utilización de \*\*\*</span><span class="sxs-lookup"><span data-stu-id="adfcd-107">\*\*\*\*Utilization\*\*\*\*</span></span>|
|:-----|:-----|:-----|:-----|
|[<span data-ttu-id="adfcd-108">Empezar a evaluar</span><span class="sxs-lookup"><span data-stu-id="adfcd-108">Start evaluating</span></span>](office-365-cas-overview.md) <br/> |[<span data-ttu-id="adfcd-109">Comenzar a planear</span><span class="sxs-lookup"><span data-stu-id="adfcd-109">Start planning</span></span>](get-ready-for-office-365-cas.md) <br/> |[<span data-ttu-id="adfcd-110">Iniciar la implementación</span><span class="sxs-lookup"><span data-stu-id="adfcd-110">Start deploying</span></span>](turn-on-office-365-cas.md) <br/> |<span data-ttu-id="adfcd-111">¡Están aquí!</span><span class="sxs-lookup"><span data-stu-id="adfcd-111">You are here!</span></span>  <br/> [<span data-ttu-id="adfcd-112">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="adfcd-112">Next steps</span></span>](#next-steps) <br/> |
   
<span data-ttu-id="adfcd-p101">Office 365 funciona la seguridad de la aplicación en la nube con el [registro de auditoría de Office 365](detailed-properties-in-the-office-365-audit-log.md). Con la seguridad de la aplicación de nube de Office 365, como un administrador global o administrador de seguridad, puede usar la página de registro de actividad para ver posibles problemas en el modo en que su organización usa Office 365.</span><span class="sxs-lookup"><span data-stu-id="adfcd-p101">Office 365 Cloud App Security works with your [Office 365 audit log](detailed-properties-in-the-office-365-audit-log.md). With Office 365 Cloud App Security, as a global administrator or security administrator, you can use the Activity log page to see potential issues in how your organization is using Office 365.</span></span>
  
## <a name="how-to-get-to-the-activity-log-page"></a><span data-ttu-id="adfcd-115">Cómo llegar a la página de registro de actividad</span><span class="sxs-lookup"><span data-stu-id="adfcd-115">How to get to the Activity log page</span></span>

1. <span data-ttu-id="adfcd-p102">Como administrador global o administrador de seguridad, vaya a [https://protection.office.com](https://protection.office.com) e iniciar sesión con su cuenta de trabajo o escuela. (Vea [permisos en la seguridad de Office 365 &amp; centro de cumplimiento](permissions-in-the-security-and-compliance-center.md).)</span><span class="sxs-lookup"><span data-stu-id="adfcd-p102">As a global administrator or security administrator, go to [https://protection.office.com](https://protection.office.com) and sign in using your work or school account. (See [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).)</span></span>
    
2. <span data-ttu-id="adfcd-118">En la seguridad &amp; centro de cumplimiento, elija **alertas** \> **avanzada de administrar las alertas**.</span><span class="sxs-lookup"><span data-stu-id="adfcd-118">In the Security &amp; Compliance Center, choose **Alerts** \> **Manage advanced alerts**.</span></span>
    
3. <span data-ttu-id="adfcd-119">Elija **Ir a la seguridad de la aplicación de Office 365 en la nube**.</span><span class="sxs-lookup"><span data-stu-id="adfcd-119">Choose **Go to Office 365 Cloud App Security**.</span></span><br/><span data-ttu-id="adfcd-120">![En la seguridad &amp; centro de cumplimiento, elija Administrar alertas avanzadas para ir a la seguridad de la aplicación de nube de Office 365](media/958632d4-03e3-4ade-8e22-d5509db6fca7.png)</span><span class="sxs-lookup"><span data-stu-id="adfcd-120">![In the Security &amp; Compliance Center, choose Manage Advanced Alerts to go to Office 365 Cloud App Security](media/958632d4-03e3-4ade-8e22-d5509db6fca7.png)</span></span>
  
4. <span data-ttu-id="adfcd-121">En la barra de navegación a través de la parte superior de la pantalla, elija **investigar** \> **registro de actividad**.</span><span class="sxs-lookup"><span data-stu-id="adfcd-121">In the navigation bar across the top of the screen, choose **Investigate** \> **Activity log**.</span></span><br/><span data-ttu-id="adfcd-122">![En el portal de O365 CAS, elija investigar.](media/8c7b87c9-71a6-4952-adb2-185e941ffe9a.png)</span><span class="sxs-lookup"><span data-stu-id="adfcd-122">![In the O365 CAS portal, choose Investigate.](media/8c7b87c9-71a6-4952-adb2-185e941ffe9a.png)</span></span>
  
## <a name="review-and-investigate-activities"></a><span data-ttu-id="adfcd-123">Revise e investigar las actividades</span><span class="sxs-lookup"><span data-stu-id="adfcd-123">Review and investigate activities</span></span>

<span data-ttu-id="adfcd-p103">En la página de registro de actividad, puede ver una lista de diversas actividades que se están produciendo dentro de la organización con Office 365. Puede usar filtros en la parte superior de la pantalla para centrarse en un tipo específico de la actividad o un usuario específico. Por ejemplo, en la siguiente imagen se muestra información acerca del cambio de contraseña de la cuenta de administración de Office 365 de la organización:</span><span class="sxs-lookup"><span data-stu-id="adfcd-p103">On the Activity log page, you can see a list of various activities that are taking place within your organization using Office 365. You can use filters across the top of the screen to focus on a specific type of activity or a specific user. For example, the following image shows information about an organization's Office 365 admin account's password change:</span></span>
  
![En seguridad de la aplicación de nube de Office 365, elija investigar \> registro de actividad.](media/5d54600c-59cd-4f33-b4f0-29b75c37baae.png)
  
<span data-ttu-id="adfcd-p104">En lo que respecta a cada elemento en el registro de actividad, puede hacer clic en los puntos suspensivos para buscar otras actividades relacionadas. Por ejemplo, puede ver otras actividades del mismo tipo, desde la misma dirección IP, o desde el mismo país o región.</span><span class="sxs-lookup"><span data-stu-id="adfcd-p104">As you look at each item in the Activity log, you can click the ellipses to find other related activities. For example, you can view other activities of the same type, from the same IP address, or from the same country/region.</span></span>
  
<span data-ttu-id="adfcd-p105">Puede ver información acerca de muchos otros tipos de actividades, demasiado. Por ejemplo, aquí son algunas de las actividades que se puede ver en el registro de actividades:</span><span class="sxs-lookup"><span data-stu-id="adfcd-p105">You can view information about many other kinds of activities, too. For example, here are some of the activities you can view in the Activity log:</span></span>
  
- <span data-ttu-id="adfcd-132">Agregar o quitar de grupos de miembros</span><span class="sxs-lookup"><span data-stu-id="adfcd-132">Members added to or removed from groups</span></span>
    
- <span data-ttu-id="adfcd-133">Cambios en las licencias de usuario</span><span class="sxs-lookup"><span data-stu-id="adfcd-133">Changes in user licenses</span></span>
    
- <span data-ttu-id="adfcd-134">Los archivos o carpetas compartidas interna o externamente</span><span class="sxs-lookup"><span data-stu-id="adfcd-134">Files or folders shared internally or externally</span></span>
    
- <span data-ttu-id="adfcd-135">Creado o eliminados sitios o colecciones de sitios</span><span class="sxs-lookup"><span data-stu-id="adfcd-135">Created or deleted sites or site collections</span></span>
    
- <span data-ttu-id="adfcd-136">Las reglas de transferencia de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="adfcd-136">Email forwarding rules</span></span>
    
<span data-ttu-id="adfcd-137">Use la página de registro de actividad de familiarizarse con cómo las personas de su organización están usando Office 365 y qué problemas es posible que tenga a lo largo de la forma.</span><span class="sxs-lookup"><span data-stu-id="adfcd-137">Use the Activity log page to get acquainted with how people in your organization are using Office 365 and what issues they might be having along the way.</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="adfcd-138">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="adfcd-138">Next steps</span></span>

- [<span data-ttu-id="adfcd-139">Revisar y realizar acciones sobre alertas en Office 365 Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="adfcd-139">Review and take action on alerts in Office 365 Cloud App Security</span></span>](review-office-365-cas-alerts.md)
    
- <span data-ttu-id="adfcd-140">Revise las [actividades de uso para la seguridad de la aplicación de nube de Office 365](utilization-activities-for-ocas.md)</span><span class="sxs-lookup"><span data-stu-id="adfcd-140">Review your [utilization activities for Office 365 Cloud App Security](utilization-activities-for-ocas.md)</span></span>
    

