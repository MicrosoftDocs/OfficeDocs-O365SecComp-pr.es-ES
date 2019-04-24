---
title: Revisar y realizar acciones sobre alertas en Office 365 Cloud App Security
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 97e9c3d9-df89-458e-924b-369becee5532
description: Use la página Alertas de Office 365 Cloud App Security para ver posibles problemas y emprender acciones. Puede omitir o resolver las alertas y, si es necesario, suspender una cuenta de usuario.
ms.openlocfilehash: ddef10293fca7b722a13babdca5c05bbe2398cb3
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32261488"
---
# <a name="review-and-take-action-on-alerts-in-office-365-cloud-app-security"></a><span data-ttu-id="7130c-104">Revisar y realizar acciones sobre alertas en Office 365 Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="7130c-104">Review and take action on alerts in Office 365 Cloud App Security</span></span>
  
|<span data-ttu-id="7130c-105">Evaluación \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="7130c-105">\*\*\*\*Evaluation\*\* \>\*\*</span></span>|<span data-ttu-id="7130c-106">Planeación \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="7130c-106">\*\*\*\*Planning\*\* \>\*\*</span></span>|<span data-ttu-id="7130c-107">Implementación \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="7130c-107">\*\*\*\*Deployment\*\* \>\*\*</span></span>|<span data-ttu-id="7130c-108">Uso \* \* \* \*</span><span class="sxs-lookup"><span data-stu-id="7130c-108">\*\*\*\*Utilization\*\*\*\*</span></span>|
|:-----|:-----|:-----|:-----|
|[<span data-ttu-id="7130c-109">Empezar a evaluar</span><span class="sxs-lookup"><span data-stu-id="7130c-109">Start evaluating</span></span>](office-365-cas-overview.md) <br/> |[<span data-ttu-id="7130c-110">Empezar a planear</span><span class="sxs-lookup"><span data-stu-id="7130c-110">Start planning</span></span>](get-ready-for-office-365-cas.md) <br/> |[<span data-ttu-id="7130c-111">Iniciar la implementación</span><span class="sxs-lookup"><span data-stu-id="7130c-111">Start deploying</span></span>](turn-on-office-365-cas.md) <br/> |<span data-ttu-id="7130c-112">Ya está aquí.</span><span class="sxs-lookup"><span data-stu-id="7130c-112">You are here!</span></span>  <br/> [<span data-ttu-id="7130c-113">Siguientes pasos</span><span class="sxs-lookup"><span data-stu-id="7130c-113">Next steps</span></span>](#next-steps) <br/> |
   
<span data-ttu-id="7130c-114">Puede usar la página de alertas de Office 365 Cloud App Security para ver posibles problemas y, si es necesario, realizar una acción.</span><span class="sxs-lookup"><span data-stu-id="7130c-114">You can use the Alerts page in Office 365 Cloud App Security to view potential issues and, if needed, take action.</span></span>
  
> [!NOTE]
> <span data-ttu-id="7130c-115">Debe ser administrador global o administrador de seguridad para realizar las tareas de este artículo.</span><span class="sxs-lookup"><span data-stu-id="7130c-115">You must be a global administrator or security administrator to perform the tasks in this article.</span></span> <span data-ttu-id="7130c-116">Consulte [permisos en el centro de seguridad &amp; y cumplimiento de Office 365](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="7130c-116">See [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span> 
  
## <a name="how-to-get-to-the-alerts-page"></a><span data-ttu-id="7130c-117">Cómo obtener acceso a la página de alertas</span><span class="sxs-lookup"><span data-stu-id="7130c-117">How to get to the Alerts page</span></span>

1. <span data-ttu-id="7130c-118">Vaya al portal de Cloud App Security ([https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)) e inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="7130c-118">Go to the Cloud App Security portal ([https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)) and sign in.</span></span>
  
2. <span data-ttu-id="7130c-119">En la barra de navegación en la parte superior de la pantalla, elija **alertas**.</span><span class="sxs-lookup"><span data-stu-id="7130c-119">In the navigation bar across the top of the screen, choose **Alerts**.</span></span><br/><span data-ttu-id="7130c-120">![En la página Alertas, puede ver las alertas que se han desencadenado y las acciones que se han llevado a cabo.](media/3b53d4c9-4b13-435d-8547-8c0f9ae6b914.png)</span><span class="sxs-lookup"><span data-stu-id="7130c-120">![On the Alerts page, you can see alerts that were triggered and any actions taken.](media/3b53d4c9-4b13-435d-8547-8c0f9ae6b914.png)</span></span>
 
> [!NOTE]
> <span data-ttu-id="7130c-121">Las alertas de Cloud App Security también están visibles en el centro de seguridad & cumplimiento (vaya a **alertas** > **Ver alertas**.</span><span class="sxs-lookup"><span data-stu-id="7130c-121">Cloud App Security alerts are also visible in the Security & Compliance Center (go to **Alerts** > **View alerts**.</span></span> <span data-ttu-id="7130c-122">Sin embargo, en este momento, debe resolver estas alertas en el portal de Cloud App Security y en el centro de seguridad & cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="7130c-122">Currently, however, you must resolve these alerts in both the Cloud App Security portal and the Security & Compliance Center.</span></span> <span data-ttu-id="7130c-123">Para obtener más información, consulte [visualización de alertas de Cloud App Security](alert-policies.md#viewing-cloud-app-security-alerts)).</span><span class="sxs-lookup"><span data-stu-id="7130c-123">To learn more, see [Viewing Cloud App Security alerts](alert-policies.md#viewing-cloud-app-security-alerts).)</span></span> 
 
## <a name="review-and-handle-alerts"></a><span data-ttu-id="7130c-124">Revisar y controlar las alertas</span><span class="sxs-lookup"><span data-stu-id="7130c-124">Review and handle alerts</span></span>

<span data-ttu-id="7130c-125">Las alertas le ayudan a identificar actividades en su entorno de nube de Office 365 que quizá quiera investigar con más detalle.</span><span class="sxs-lookup"><span data-stu-id="7130c-125">Alerts help you identify activities in your Office 365 cloud environment that you might want to investigate further.</span></span> <span data-ttu-id="7130c-126">También puede optar por crear nuevas directivas o editar las existentes en función de las alertas que vea.</span><span class="sxs-lookup"><span data-stu-id="7130c-126">You might also decide to create new policies or edit existing policies based on the alerts you see.</span></span> <span data-ttu-id="7130c-127">Por ejemplo, si ve que un administrador inicia sesión desde una ubicación extraña, es posible que decida configurar una directiva que impida que los administradores inicien sesión en Office 365 desde determinadas ubicaciones.</span><span class="sxs-lookup"><span data-stu-id="7130c-127">For example, if you see an administrator logging on from a strange location, you may decide to set up a policy that prevents administrators from signing in to Office 365 from certain locations.</span></span>
  
> [!TIP]
> <span data-ttu-id="7130c-128">Puede filtrar las alertas por **categoría** o por **gravedad** para poder administrar las alertas más importantes en primer lugar.</span><span class="sxs-lookup"><span data-stu-id="7130c-128">You can filter the alerts by **Category** or by **Severity** so you can manage the most important ones first.</span></span> 
  
<span data-ttu-id="7130c-129">Para cada alerta, mire qué le causó para poder decidir qué acción llevar a cabo.</span><span class="sxs-lookup"><span data-stu-id="7130c-129">For each alert, look into what caused it so you can decide what action to take.</span></span> <span data-ttu-id="7130c-130">Para ver más detalles sobre una alerta y emprender acciones como, por ejemplo, resolver la alerta o suspender una cuenta de usuario, elija la alerta para abrir una página de detalles.</span><span class="sxs-lookup"><span data-stu-id="7130c-130">To see more details about an alert and to take action, such as resolving the alert or suspending a users account, choose the alert to open a details page.</span></span> <span data-ttu-id="7130c-131">En la página detalles, puede revisar el registro de actividades, las cuentas y los usuarios que están relacionados con la alerta, y emprender acciones como las siguientes:</span><span class="sxs-lookup"><span data-stu-id="7130c-131">On the details page, you can review the activity log, accounts, and users that are related to the alert, and take actions such as the following:</span></span>
  
- <span data-ttu-id="7130c-132">\*\*\*\* Descartar Si la alerta era un falso positivo, se ha omitido.</span><span class="sxs-lookup"><span data-stu-id="7130c-132">**Dismiss** If the alert was a false positive, dismiss it.</span></span> <span data-ttu-id="7130c-133">Opcionalmente, puede Agregar un comentario que explique por qué se ha desechado.</span><span class="sxs-lookup"><span data-stu-id="7130c-133">You can optionally add a comment explaining why you dismissed it.</span></span> 
    
- <span data-ttu-id="7130c-134">**Resolver alerta** Si la alerta se activó por una actividad que sabe que no es una amenaza, resuélvalo.</span><span class="sxs-lookup"><span data-stu-id="7130c-134">**Resolve alert** If the alert was triggered by an activity that you know isn't a threat, resolve it.</span></span> <span data-ttu-id="7130c-135">Opcionalmente, puede Agregar un comentario que explique por qué lo resolvió.</span><span class="sxs-lookup"><span data-stu-id="7130c-135">You can optionally add a comment explaining why you resolved it.</span></span> 
    
- <span data-ttu-id="7130c-136">**Suspender** Si sospecha que hay inicios de sesión no autorizados en una cuenta, por ejemplo, alguien que inicie sesión desde otro país cuando sepa que esa persona se encuentra físicamente en una oficina local, puede [suspender la cuenta](suspend-or-restore-an-account-in-ocas.md) mientras investiga el contenido que se está realizando.</span><span class="sxs-lookup"><span data-stu-id="7130c-136">**Suspend** If you suspect unauthorized sign ins on an account, for example, someone signing in from another country when you know that person is physically at a local office, you can [suspend the account](suspend-or-restore-an-account-in-ocas.md) while you investigate what's going on.</span></span> 
    
## <a name="next-steps"></a><span data-ttu-id="7130c-137">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="7130c-137">Next steps</span></span>

- [<span data-ttu-id="7130c-138">Investigar una actividad</span><span class="sxs-lookup"><span data-stu-id="7130c-138">Investigate an activity</span></span>](investigate-an-activity-in-office-365-cas.md)
    
- [<span data-ttu-id="7130c-139">Suspender o restaurar una cuenta de usuario</span><span class="sxs-lookup"><span data-stu-id="7130c-139">Suspend or restore a user account</span></span>](suspend-or-restore-an-account-in-ocas.md)
    
- <span data-ttu-id="7130c-140">Ver una lista de los [orígenes de datos y los registros de tráfico web](web-traffic-logs-and-data-sources-for-ocas.md) admitidos</span><span class="sxs-lookup"><span data-stu-id="7130c-140">View a list of supported [Web traffic logs and data sources](web-traffic-logs-and-data-sources-for-ocas.md)</span></span>
    
- <span data-ttu-id="7130c-141">Revisar las [actividades de uso de Office 365 Cloud App Security](utilization-activities-for-ocas.md)</span><span class="sxs-lookup"><span data-stu-id="7130c-141">Review your [utilization activities for Office 365 Cloud App Security](utilization-activities-for-ocas.md)</span></span>
    

