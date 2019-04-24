---
title: Investigar la actividad en Office 365 Cloud App Security
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 1/28/2019
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 15fa4545-28b4-4dd4-bf85-88e0926bd5fc
description: 'Con Office 365 Cloud App Security, puede ver lo que ocurre en su entorno de Office 365 buscando y investigando actividades y cuentas. '
ms.openlocfilehash: 0cc3860d953b40b0b0c247af6fb2b157d1abb235
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32254848"
---
# <a name="investigate-an-activity-in-office-365-cloud-app-security"></a><span data-ttu-id="229aa-103">Investigar la actividad en Office 365 Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="229aa-103">Investigate an activity in Office 365 Cloud App Security</span></span>
  
|<span data-ttu-id="229aa-104">Evaluación \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="229aa-104">\*\*\*\*Evaluation\*\* \>\*\*</span></span>|<span data-ttu-id="229aa-105">Planeación \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="229aa-105">\*\*\*\*Planning\*\* \>\*\*</span></span>|<span data-ttu-id="229aa-106">Implementación \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="229aa-106">\*\*\*\*Deployment\*\* \>\*\*</span></span>|<span data-ttu-id="229aa-107">Uso \* \* \* \*</span><span class="sxs-lookup"><span data-stu-id="229aa-107">\*\*\*\*Utilization\*\*\*\*</span></span>|
|:-----|:-----|:-----|:-----|
|[<span data-ttu-id="229aa-108">Empezar a evaluar</span><span class="sxs-lookup"><span data-stu-id="229aa-108">Start evaluating</span></span>](office-365-cas-overview.md) <br/> |[<span data-ttu-id="229aa-109">Empezar a planear</span><span class="sxs-lookup"><span data-stu-id="229aa-109">Start planning</span></span>](get-ready-for-office-365-cas.md) <br/> |[<span data-ttu-id="229aa-110">Iniciar la implementación</span><span class="sxs-lookup"><span data-stu-id="229aa-110">Start deploying</span></span>](turn-on-office-365-cas.md) <br/> |<span data-ttu-id="229aa-111">Ya está aquí.</span><span class="sxs-lookup"><span data-stu-id="229aa-111">You are here!</span></span>  <br/> [<span data-ttu-id="229aa-112">Siguientes pasos</span><span class="sxs-lookup"><span data-stu-id="229aa-112">Next steps</span></span>](#next-steps) <br/> |
   
<span data-ttu-id="229aa-113">Office 365 Cloud App Security funciona con su [registro de auditoría de office 365](detailed-properties-in-the-office-365-audit-log.md).</span><span class="sxs-lookup"><span data-stu-id="229aa-113">Office 365 Cloud App Security works with your [Office 365 audit log](detailed-properties-in-the-office-365-audit-log.md).</span></span> <span data-ttu-id="229aa-114">Con Office 365 Cloud App Security, como administrador global o administrador de seguridad, puede usar la página Registro de actividades para ver posibles problemas en el modo en que su organización usa Office 365.</span><span class="sxs-lookup"><span data-stu-id="229aa-114">With Office 365 Cloud App Security, as a global administrator or security administrator, you can use the Activity log page to see potential issues in how your organization is using Office 365.</span></span>
  
## <a name="how-to-get-to-the-activity-log-page"></a><span data-ttu-id="229aa-115">Cómo obtener acceso a la página Registro de actividades</span><span class="sxs-lookup"><span data-stu-id="229aa-115">How to get to the Activity log page</span></span>

1. <span data-ttu-id="229aa-116">Vaya al portal de Cloud App Security ([https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)) e inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="229aa-116">Go to the Cloud App Security portal ([https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)) and sign in.</span></span>
  
2. <span data-ttu-id="229aa-117">En la barra de navegación de la parte superior de la pantalla, elija **investigar** \> **registro de actividades**.</span><span class="sxs-lookup"><span data-stu-id="229aa-117">In the navigation bar across the top of the screen, choose **Investigate** \> **Activity log**.</span></span><br/><span data-ttu-id="229aa-118">![En el portal de CAS de O365, elija investigar.](media/8c7b87c9-71a6-4952-adb2-185e941ffe9a.png)</span><span class="sxs-lookup"><span data-stu-id="229aa-118">![In the O365 CAS portal, choose Investigate.](media/8c7b87c9-71a6-4952-adb2-185e941ffe9a.png)</span></span>
  
## <a name="review-and-investigate-activities"></a><span data-ttu-id="229aa-119">Revisión e investigación de actividades</span><span class="sxs-lookup"><span data-stu-id="229aa-119">Review and investigate activities</span></span>

<span data-ttu-id="229aa-120">En la página Registro de actividad, puede ver una lista de las diversas actividades que se están llevando a cabo dentro de la organización mediante Office 365.</span><span class="sxs-lookup"><span data-stu-id="229aa-120">On the Activity log page, you can see a list of various activities that are taking place within your organization using Office 365.</span></span> <span data-ttu-id="229aa-121">Puede usar filtros en la parte superior de la pantalla para centrarse en un tipo específico de actividad o en un usuario específico.</span><span class="sxs-lookup"><span data-stu-id="229aa-121">You can use filters across the top of the screen to focus on a specific type of activity or a specific user.</span></span> <span data-ttu-id="229aa-122">Por ejemplo, en la siguiente imagen se muestra información sobre el cambio de contraseña de la cuenta de administrador Office 365 de una organización:</span><span class="sxs-lookup"><span data-stu-id="229aa-122">For example, the following image shows information about an organization's Office 365 admin account's password change:</span></span>
  
![En Office 365 Cloud App Security, elija investigar \> registro de actividad.](media/5d54600c-59cd-4f33-b4f0-29b75c37baae.png)
  
<span data-ttu-id="229aa-124">Cuando vea cada elemento en el registro de actividades, puede hacer clic en los puntos suspensivos para buscar otras actividades relacionadas.</span><span class="sxs-lookup"><span data-stu-id="229aa-124">As you look at each item in the Activity log, you can click the ellipses to find other related activities.</span></span> <span data-ttu-id="229aa-125">Por ejemplo, puede ver otras actividades del mismo tipo, desde la misma dirección IP o desde el mismo país o región.</span><span class="sxs-lookup"><span data-stu-id="229aa-125">For example, you can view other activities of the same type, from the same IP address, or from the same country/region.</span></span>
  
<span data-ttu-id="229aa-126">También puede ver información sobre muchos otros tipos de actividades.</span><span class="sxs-lookup"><span data-stu-id="229aa-126">You can view information about many other kinds of activities, too.</span></span> <span data-ttu-id="229aa-127">Por ejemplo, estas son algunas de las actividades que puede ver en el registro de actividades:</span><span class="sxs-lookup"><span data-stu-id="229aa-127">For example, here are some of the activities you can view in the Activity log:</span></span>
  
- <span data-ttu-id="229aa-128">Miembros agregados o eliminados de grupos</span><span class="sxs-lookup"><span data-stu-id="229aa-128">Members added to or removed from groups</span></span>
    
- <span data-ttu-id="229aa-129">Cambios en las licencias de usuario</span><span class="sxs-lookup"><span data-stu-id="229aa-129">Changes in user licenses</span></span>
    
- <span data-ttu-id="229aa-130">Archivos o carpetas compartidos interna o externamente</span><span class="sxs-lookup"><span data-stu-id="229aa-130">Files or folders shared internally or externally</span></span>
    
- <span data-ttu-id="229aa-131">Sitios o colecciones de sitios creados o eliminados</span><span class="sxs-lookup"><span data-stu-id="229aa-131">Created or deleted sites or site collections</span></span>
    
- <span data-ttu-id="229aa-132">Reglas de reenvío de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="229aa-132">Email forwarding rules</span></span>
    
<span data-ttu-id="229aa-133">Use la página Registro de actividades para familiarizarse con la forma en que los usuarios de su organización usan Office 365 y los problemas que pueden tener a su alrededor.</span><span class="sxs-lookup"><span data-stu-id="229aa-133">Use the Activity log page to get acquainted with how people in your organization are using Office 365 and what issues they might be having along the way.</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="229aa-134">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="229aa-134">Next steps</span></span>

- [<span data-ttu-id="229aa-135">Revisar y realizar acciones sobre alertas en Office 365 Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="229aa-135">Review and take action on alerts in Office 365 Cloud App Security</span></span>](review-office-365-cas-alerts.md)
    
- <span data-ttu-id="229aa-136">Revisar las [actividades de uso de Office 365 Cloud App Security](utilization-activities-for-ocas.md)</span><span class="sxs-lookup"><span data-stu-id="229aa-136">Review your [utilization activities for Office 365 Cloud App Security](utilization-activities-for-ocas.md)</span></span>
    

