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
ms.openlocfilehash: 16d24ef7075a2db1dab86ee322b14f886c48b98b
ms.sourcegitcommit: 2cf7f5bb282c971d33e00f65d9982a3f14aec74e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/27/2018
ms.locfileid: "26706124"
---
# <a name="review-and-take-action-on-alerts-in-office-365-cloud-app-security"></a><span data-ttu-id="af644-104">Revisar y realizar acciones sobre alertas en Office 365 Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="af644-104">Review and take action on alerts in Office 365 Cloud App Security</span></span>
  
|<span data-ttu-id="af644-105">Evaluación **\>**</span><span class="sxs-lookup"><span data-stu-id="af644-105">\*\*\*\*Evaluation\*\* \>\*\*</span></span>|<span data-ttu-id="af644-106">Planeación de **\>**</span><span class="sxs-lookup"><span data-stu-id="af644-106">\*\*\*\*Planning\*\* \>\*\*</span></span>|<span data-ttu-id="af644-107">Implementación **\>**</span><span class="sxs-lookup"><span data-stu-id="af644-107">\*\*\*\*Deployment\*\* \>\*\*</span></span>|<span data-ttu-id="af644-108">Utilización de \*\*\*</span><span class="sxs-lookup"><span data-stu-id="af644-108">\*\*\*\*Utilization\*\*\*\*</span></span>|
|:-----|:-----|:-----|:-----|
|[<span data-ttu-id="af644-109">Empezar a evaluar</span><span class="sxs-lookup"><span data-stu-id="af644-109">Start evaluating</span></span>](office-365-cas-overview.md) <br/> |[<span data-ttu-id="af644-110">Comenzar a planear</span><span class="sxs-lookup"><span data-stu-id="af644-110">Start planning</span></span>](get-ready-for-office-365-cas.md) <br/> |[<span data-ttu-id="af644-111">Iniciar la implementación</span><span class="sxs-lookup"><span data-stu-id="af644-111">Start deploying</span></span>](turn-on-office-365-cas.md) <br/> |<span data-ttu-id="af644-112">¡Están aquí!</span><span class="sxs-lookup"><span data-stu-id="af644-112">You are here!</span></span>  <br/> [<span data-ttu-id="af644-113">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="af644-113">Next steps</span></span>](#next-steps) <br/> |
   
<span data-ttu-id="af644-114">Puede usar la página alertas de seguridad de la aplicación de nube de Office 365 para ver posibles problemas y, si es necesario, tomar medidas.</span><span class="sxs-lookup"><span data-stu-id="af644-114">You can use the Alerts page in Office 365 Cloud App Security to view potential issues and, if needed, take action.</span></span>
  
> [!NOTE]
> <span data-ttu-id="af644-p102">Debe ser un administrador global o administrador de seguridad para llevar a cabo las tareas de este artículo. Vea [permisos en la seguridad de Office 365 &amp; centro de cumplimiento](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="af644-p102">You must be a global administrator or security administrator to perform the tasks in this article. See [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span> 
  
## <a name="how-to-get-to-the-alerts-page"></a><span data-ttu-id="af644-117">Cómo llegar a la página de alertas</span><span class="sxs-lookup"><span data-stu-id="af644-117">How to get to the Alerts page</span></span>

1. <span data-ttu-id="af644-118">Como administrador global o administrador de seguridad, vaya a [https://security.microsoft.com](https://security.microsoft.com) e iniciar sesión con su cuenta de trabajo o escuela.</span><span class="sxs-lookup"><span data-stu-id="af644-118">As a global administrator or security administrator, go to [https://security.microsoft.com](https://security.microsoft.com) and sign in using your work or school account.</span></span> 
    
2. <span data-ttu-id="af644-119">En la seguridad &amp; centro de cumplimiento, elija **alertas** \> **avanzada de administrar las alertas**.</span><span class="sxs-lookup"><span data-stu-id="af644-119">In the Security &amp; Compliance Center, choose **Alerts** \> **Manage advanced alerts**.</span></span>
    
3. <span data-ttu-id="af644-120">Elija **Ir a la seguridad de la aplicación de Office 365 en la nube**.</span><span class="sxs-lookup"><span data-stu-id="af644-120">Choose **Go to Office 365 Cloud App Security**.</span></span><br/><span data-ttu-id="af644-121">![En la seguridad &amp; centro de cumplimiento, elija Administrar alertas avanzadas para ir a la seguridad de la aplicación de nube de Office 365](media/958632d4-03e3-4ade-8e22-d5509db6fca7.png)</span><span class="sxs-lookup"><span data-stu-id="af644-121">![In the Security &amp; Compliance Center, choose Manage Advanced Alerts to go to Office 365 Cloud App Security](media/958632d4-03e3-4ade-8e22-d5509db6fca7.png)</span></span>
  
4. <span data-ttu-id="af644-122">En la barra de navegación a través de la parte superior de la pantalla, elija **alertas**.</span><span class="sxs-lookup"><span data-stu-id="af644-122">In the navigation bar across the top of the screen, choose **Alerts**.</span></span><br/><span data-ttu-id="af644-123">![En la página alertas, puede ver las alertas que se activaron y todas las acciones realizadas.](media/3b53d4c9-4b13-435d-8547-8c0f9ae6b914.png)</span><span class="sxs-lookup"><span data-stu-id="af644-123">![On the Alerts page, you can see alerts that were triggered and any actions taken.](media/3b53d4c9-4b13-435d-8547-8c0f9ae6b914.png)</span></span>
  
## <a name="review-and-handle-alerts"></a><span data-ttu-id="af644-124">Revisión y controlar las alertas</span><span class="sxs-lookup"><span data-stu-id="af644-124">Review and handle alerts</span></span>

<span data-ttu-id="af644-p103">Las alertas le ayudarán a identificar las actividades en el entorno de nube de Office 365 que es posible que desee investigar más. También es posible que decida crear nuevas directivas o edición de directivas existentes en función de las alertas que consulte. Por ejemplo, si ve un administrador de inicio de sesión desde una ubicación extraña, es posible que decida configurar una directiva que impide que los administradores de inicio de sesión en Office 365 de determinadas ubicaciones.</span><span class="sxs-lookup"><span data-stu-id="af644-p103">Alerts help you identify activities in your Office 365 cloud environment that you might want to investigate further. You might also decide to create new policies or edit existing policies based on the alerts you see. For example, if you see an administrator logging on from a strange location, you may decide to set up a policy that prevents administrators from signing in to Office 365 from certain locations.</span></span>
  
> [!TIP]
> <span data-ttu-id="af644-128">Puede filtrar las alertas por **categoría** o por **gravedad** para que pueda administrar los más importantes en primer lugar.</span><span class="sxs-lookup"><span data-stu-id="af644-128">You can filter the alerts by **Category** or by **Severity** so you can manage the most important ones first.</span></span> 
  
<span data-ttu-id="af644-p104">Para cada alerta, busque en la causa para que pueda decidir qué acción debe realizar. Para ver más detalles acerca de una alerta y tomar medidas, como la resolución de la alerta o suspender una cuenta de los usuarios, elija la alerta para abrir una página de detalles. En la página de detalles, puede revisar el registro de actividad, las cuentas y los usuarios que están relacionadas con la alerta y realizar acciones como las siguientes:</span><span class="sxs-lookup"><span data-stu-id="af644-p104">For each alert, look into what caused it so you can decide what action to take. To see more details about an alert and to take action, such as resolving the alert or suspending a users account, choose the alert to open a details page. On the details page, you can review the activity log, accounts, and users that are related to the alert, and take actions such as the following:</span></span>
  
- <span data-ttu-id="af644-p105">**Descartar** Si la alerta era un falso positivo, cerrarlo. Opcionalmente, puede agregar un comentario que explique por qué se descarta.</span><span class="sxs-lookup"><span data-stu-id="af644-p105">**Dismiss** If the alert was a false positive, dismiss it. You can optionally add a comment explaining why you dismissed it.</span></span> 
    
- <span data-ttu-id="af644-p106">**Resolver la alerta** Si la alerta se desencadenó por una actividad que sabe que no es una amenaza, resolverlo. Opcionalmente, puede agregar un comentario que explique por qué se ha resuelto.</span><span class="sxs-lookup"><span data-stu-id="af644-p106">**Resolve alert** If the alert was triggered by an activity that you know isn't a threat, resolve it. You can optionally add a comment explaining why you resolved it.</span></span> 
    
- <span data-ttu-id="af644-136">**Suspender** Si sospecha que el inicio de sesión no autorizado ins en una cuenta, por ejemplo, alguien que inicie sesión desde otro país cuando sabe que esa persona es físicamente en una oficina local, puede [suspender la cuenta](suspend-or-restore-an-account-in-ocas.md) mientras investigar lo que está ocurriendo.</span><span class="sxs-lookup"><span data-stu-id="af644-136">**Suspend** If you suspect unauthorized sign ins on an account, for example, someone signing in from another country when you know that person is physically at a local office, you can [suspend the account](suspend-or-restore-an-account-in-ocas.md) while you investigate what's going on.</span></span> 
    
## <a name="next-steps"></a><span data-ttu-id="af644-137">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="af644-137">Next steps</span></span>

- [<span data-ttu-id="af644-138">Investigar una actividad</span><span class="sxs-lookup"><span data-stu-id="af644-138">Investigate an activity</span></span>](investigate-an-activity-in-office-365-cas.md)
    
- [<span data-ttu-id="af644-139">Suspender o restauración de una cuenta de usuario</span><span class="sxs-lookup"><span data-stu-id="af644-139">Suspend or restore a user account</span></span>](suspend-or-restore-an-account-in-ocas.md)
    
- <span data-ttu-id="af644-140">Ver una lista de admitidos de [orígenes de datos y los registros de tráfico Web](web-traffic-logs-and-data-sources-for-ocas.md)</span><span class="sxs-lookup"><span data-stu-id="af644-140">View a list of supported [Web traffic logs and data sources](web-traffic-logs-and-data-sources-for-ocas.md)</span></span>
    
- <span data-ttu-id="af644-141">Revise las [actividades de uso para la seguridad de la aplicación de nube de Office 365](utilization-activities-for-ocas.md)</span><span class="sxs-lookup"><span data-stu-id="af644-141">Review your [utilization activities for Office 365 Cloud App Security](utilization-activities-for-ocas.md)</span></span>
    

