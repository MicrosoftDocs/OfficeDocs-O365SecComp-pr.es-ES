---
title: Revisar y realizar acciones sobre alertas en Office 365 Cloud App Security
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 97e9c3d9-df89-458e-924b-369becee5532
description: Use la página alertas de seguridad de la aplicación de nube de Office 365 para ver posibles problemas y tomar medidas. Puede descartar o resolver las alertas y, si es necesario, suspender una cuenta de usuario.
ms.openlocfilehash: ff20b913553414d796f9653108ac9b8a3d84cb74
ms.sourcegitcommit: 7e2a0185cadea7f3a6afc5ddc445eac2e1ce22eb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/11/2019
ms.locfileid: "29603681"
---
# <a name="review-and-take-action-on-alerts-in-office-365-cloud-app-security"></a><span data-ttu-id="74116-104">Revisar y realizar acciones sobre alertas en Office 365 Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="74116-104">Review and take action on alerts in Office 365 Cloud App Security</span></span>
  
|<span data-ttu-id="74116-105">Evaluación **\>**</span><span class="sxs-lookup"><span data-stu-id="74116-105">\*\*\*\*Evaluation\*\* \>\*\*</span></span>|<span data-ttu-id="74116-106">Planeación de **\>**</span><span class="sxs-lookup"><span data-stu-id="74116-106">\*\*\*\*Planning\*\* \>\*\*</span></span>|<span data-ttu-id="74116-107">Implementación **\>**</span><span class="sxs-lookup"><span data-stu-id="74116-107">\*\*\*\*Deployment\*\* \>\*\*</span></span>|<span data-ttu-id="74116-108">Utilización de \*\*\*</span><span class="sxs-lookup"><span data-stu-id="74116-108">\*\*\*\*Utilization\*\*\*\*</span></span>|
|:-----|:-----|:-----|:-----|
|[<span data-ttu-id="74116-109">Empezar a evaluar</span><span class="sxs-lookup"><span data-stu-id="74116-109">Start evaluating</span></span>](office-365-cas-overview.md) <br/> |[<span data-ttu-id="74116-110">Comenzar a planear</span><span class="sxs-lookup"><span data-stu-id="74116-110">Start planning</span></span>](get-ready-for-office-365-cas.md) <br/> |[<span data-ttu-id="74116-111">Iniciar la implementación</span><span class="sxs-lookup"><span data-stu-id="74116-111">Start deploying</span></span>](turn-on-office-365-cas.md) <br/> |<span data-ttu-id="74116-112">¡Están aquí!</span><span class="sxs-lookup"><span data-stu-id="74116-112">You are here!</span></span>  <br/> [<span data-ttu-id="74116-113">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="74116-113">Next steps</span></span>](#next-steps) <br/> |
   
<span data-ttu-id="74116-114">Puede usar la página alertas de seguridad de la aplicación de nube de Office 365 para ver posibles problemas y, si es necesario, tomar medidas.</span><span class="sxs-lookup"><span data-stu-id="74116-114">You can use the Alerts page in Office 365 Cloud App Security to view potential issues and, if needed, take action.</span></span>
  
> [!NOTE]
> <span data-ttu-id="74116-p102">Debe ser un administrador global o administrador de seguridad para llevar a cabo las tareas de este artículo. Vea [permisos en la seguridad de Office 365 &amp; centro de cumplimiento](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="74116-p102">You must be a global administrator or security administrator to perform the tasks in this article. See [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span> 
  
## <a name="how-to-get-to-the-alerts-page"></a><span data-ttu-id="74116-117">Cómo llegar a la página de alertas</span><span class="sxs-lookup"><span data-stu-id="74116-117">How to get to the Alerts page</span></span>

1. <span data-ttu-id="74116-118">Vaya al portal de seguridad de la aplicación en la nube ([https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)) e iniciar sesión.</span><span class="sxs-lookup"><span data-stu-id="74116-118">Go to the Cloud App Security portal ([https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)) and sign in.</span></span>
  
2. <span data-ttu-id="74116-119">En la barra de navegación a través de la parte superior de la pantalla, elija **alertas**.</span><span class="sxs-lookup"><span data-stu-id="74116-119">In the navigation bar across the top of the screen, choose **Alerts**.</span></span><br/><span data-ttu-id="74116-120">![En la página alertas, puede ver las alertas que se activaron y todas las acciones realizadas.](media/3b53d4c9-4b13-435d-8547-8c0f9ae6b914.png)</span><span class="sxs-lookup"><span data-stu-id="74116-120">![On the Alerts page, you can see alerts that were triggered and any actions taken.](media/3b53d4c9-4b13-435d-8547-8c0f9ae6b914.png)</span></span>
  
## <a name="review-and-handle-alerts"></a><span data-ttu-id="74116-121">Revisión y controlar las alertas</span><span class="sxs-lookup"><span data-stu-id="74116-121">Review and handle alerts</span></span>

<span data-ttu-id="74116-p103">Las alertas le ayudarán a identificar las actividades en el entorno de nube de Office 365 que es posible que desee investigar más. También es posible que decida crear nuevas directivas o edición de directivas existentes en función de las alertas que consulte. Por ejemplo, si ve un administrador de inicio de sesión desde una ubicación extraña, es posible que decida configurar una directiva que impide que los administradores de inicio de sesión en Office 365 de determinadas ubicaciones.</span><span class="sxs-lookup"><span data-stu-id="74116-p103">Alerts help you identify activities in your Office 365 cloud environment that you might want to investigate further. You might also decide to create new policies or edit existing policies based on the alerts you see. For example, if you see an administrator logging on from a strange location, you may decide to set up a policy that prevents administrators from signing in to Office 365 from certain locations.</span></span>
  
> [!TIP]
> <span data-ttu-id="74116-125">Puede filtrar las alertas por **categoría** o por **gravedad** para que pueda administrar los más importantes en primer lugar.</span><span class="sxs-lookup"><span data-stu-id="74116-125">You can filter the alerts by **Category** or by **Severity** so you can manage the most important ones first.</span></span> 
  
<span data-ttu-id="74116-p104">Para cada alerta, busque en la causa para que pueda decidir qué acción debe realizar. Para ver más detalles acerca de una alerta y tomar medidas, como la resolución de la alerta o suspender una cuenta de los usuarios, elija la alerta para abrir una página de detalles. En la página de detalles, puede revisar el registro de actividad, las cuentas y los usuarios que están relacionadas con la alerta y realizar acciones como las siguientes:</span><span class="sxs-lookup"><span data-stu-id="74116-p104">For each alert, look into what caused it so you can decide what action to take. To see more details about an alert and to take action, such as resolving the alert or suspending a users account, choose the alert to open a details page. On the details page, you can review the activity log, accounts, and users that are related to the alert, and take actions such as the following:</span></span>
  
- <span data-ttu-id="74116-p105">**Descartar** Si la alerta era un falso positivo, cerrarlo. Opcionalmente, puede agregar un comentario que explique por qué se descarta.</span><span class="sxs-lookup"><span data-stu-id="74116-p105">**Dismiss** If the alert was a false positive, dismiss it. You can optionally add a comment explaining why you dismissed it.</span></span> 
    
- <span data-ttu-id="74116-p106">**Resolver la alerta** Si la alerta se desencadenó por una actividad que sabe que no es una amenaza, resolverlo. Opcionalmente, puede agregar un comentario que explique por qué se ha resuelto.</span><span class="sxs-lookup"><span data-stu-id="74116-p106">**Resolve alert** If the alert was triggered by an activity that you know isn't a threat, resolve it. You can optionally add a comment explaining why you resolved it.</span></span> 
    
- <span data-ttu-id="74116-133">**Suspender** Si sospecha que el inicio de sesión no autorizado ins en una cuenta, por ejemplo, alguien que inicie sesión desde otro país cuando sabe que esa persona es físicamente en una oficina local, puede [suspender la cuenta](suspend-or-restore-an-account-in-ocas.md) mientras investigar lo que está ocurriendo.</span><span class="sxs-lookup"><span data-stu-id="74116-133">**Suspend** If you suspect unauthorized sign ins on an account, for example, someone signing in from another country when you know that person is physically at a local office, you can [suspend the account](suspend-or-restore-an-account-in-ocas.md) while you investigate what's going on.</span></span> 
    
## <a name="next-steps"></a><span data-ttu-id="74116-134">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="74116-134">Next steps</span></span>

- [<span data-ttu-id="74116-135">Investigar una actividad</span><span class="sxs-lookup"><span data-stu-id="74116-135">Investigate an activity</span></span>](investigate-an-activity-in-office-365-cas.md)
    
- [<span data-ttu-id="74116-136">Suspender o restauración de una cuenta de usuario</span><span class="sxs-lookup"><span data-stu-id="74116-136">Suspend or restore a user account</span></span>](suspend-or-restore-an-account-in-ocas.md)
    
- <span data-ttu-id="74116-137">Ver una lista de admitidos de [orígenes de datos y los registros de tráfico Web](web-traffic-logs-and-data-sources-for-ocas.md)</span><span class="sxs-lookup"><span data-stu-id="74116-137">View a list of supported [Web traffic logs and data sources](web-traffic-logs-and-data-sources-for-ocas.md)</span></span>
    
- <span data-ttu-id="74116-138">Revise las [actividades de uso para la seguridad de la aplicación de nube de Office 365](utilization-activities-for-ocas.md)</span><span class="sxs-lookup"><span data-stu-id="74116-138">Review your [utilization activities for Office 365 Cloud App Security](utilization-activities-for-ocas.md)</span></span>
    

