---
title: Actividades de uso después de implementar Office 365 Cloud App Security
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 01/28/2019
ms.audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 86f414ad-81de-4703-b40a-c6615bbe9108
description: Una vez que haya configurado e implementado la seguridad de aplicaciones de nube de Office 365, querrá realizar ciertas tareas para asegurarse de que la configuración es correcta y de que está preparado para realizar revisiones periódicas.
ms.openlocfilehash: 232de4df1d1eb4debdddcee2c1d8672d1aeb4b21
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32242548"
---
# <a name="utilization-activities-after-rolling-out-office-365-cloud-app-security"></a><span data-ttu-id="3ad48-103">Actividades de uso después de implementar Office 365 Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="3ad48-103">Utilization activities after rolling out Office 365 Cloud App Security</span></span>
  
|<span data-ttu-id="3ad48-104">Evaluación \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="3ad48-104">\*\*\*\*Evaluation\*\* \>\*\*</span></span>|<span data-ttu-id="3ad48-105">Planeación \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="3ad48-105">\*\*\*\*Planning\*\* \>\*\*</span></span>|<span data-ttu-id="3ad48-106">Implementación \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="3ad48-106">\*\*\*\*Deployment\*\* \>\*\*</span></span>|<span data-ttu-id="3ad48-107">Uso \* \* \* \*</span><span class="sxs-lookup"><span data-stu-id="3ad48-107">\*\*\*\*Utilization\*\*\*\*</span></span>|
|:-----|:-----|:-----|:-----|
|[<span data-ttu-id="3ad48-108">Empezar a evaluar</span><span class="sxs-lookup"><span data-stu-id="3ad48-108">Start evaluating</span></span>](office-365-cas-overview.md) <br/> |[<span data-ttu-id="3ad48-109">Empezar a planear</span><span class="sxs-lookup"><span data-stu-id="3ad48-109">Start planning</span></span>](get-ready-for-office-365-cas.md) <br/> |[<span data-ttu-id="3ad48-110">Iniciar la implementación</span><span class="sxs-lookup"><span data-stu-id="3ad48-110">Start deploying</span></span>](turn-on-office-365-cas.md) <br/> |<span data-ttu-id="3ad48-111">Ya está aquí.</span><span class="sxs-lookup"><span data-stu-id="3ad48-111">You are here!</span></span>  <br/> [<span data-ttu-id="3ad48-112">Siguiente paso</span><span class="sxs-lookup"><span data-stu-id="3ad48-112">Next step</span></span>](review-office-365-cas-alerts.md) <br/> |
   
> [!NOTE]
> <span data-ttu-id="3ad48-113">Office 365 Cloud App Security está disponible en Office 365 Enterprise E5.</span><span class="sxs-lookup"><span data-stu-id="3ad48-113">Office 365 Cloud App Security is available in Office 365 Enterprise E5.</span></span> <span data-ttu-id="3ad48-114">Si su organización usa otra suscripción de Office 365 Enterprise, Office 365 Cloud App Security puede adquirirse como un complemento.</span><span class="sxs-lookup"><span data-stu-id="3ad48-114">If your organization is using another Office 365 Enterprise subscription, Office 365 Cloud App Security can be purchased as an add-on.</span></span> <span data-ttu-id="3ad48-115">(como administrador global, en el centro de administración de Microsoft 365, elija **facturación** \> **Add**subscriptions). Para obtener más información, consulte [office 365 Platform Service Description: office &amp; 365 Security Compliance Center](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center) y [comprar o editar un complemento para Office 365 para empresas](https://support.office.com/article/4e7b57d6-b93b-457d-aecd-0ea58bff07a6).</span><span class="sxs-lookup"><span data-stu-id="3ad48-115">(As a global administrator, in the Microsoft 365 admin center, choose **Billing** \> **Add subscriptions**.) For more information, see [Office 365 Platform Service Description: Office 365 Security &amp; Compliance Center](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center) and [Buy or edit an add-on for Office 365 for business](https://support.office.com/article/4e7b57d6-b93b-457d-aecd-0ea58bff07a6).</span></span> 
  
<span data-ttu-id="3ad48-116">Una vez que haya configurado y configurado la seguridad de aplicaciones en la nube de Office 365, querrá realizar determinadas tareas de uso como administrador global de Office 365 o administrador de seguridad de su organización.</span><span class="sxs-lookup"><span data-stu-id="3ad48-116">After you have set up and configured Office 365 Cloud App Security, you'll want to perform certain utilization tasks as an Office 365 global administrator or security administrator for your organization.</span></span> 

<span data-ttu-id="3ad48-117">Al realizar estas tareas, le ayudará a asegurarse de que la seguridad de la aplicación de nube de Office 365 está configurada correctamente, a que las directivas están actualizadas y a su organización se obtienen valores de Office 365.</span><span class="sxs-lookup"><span data-stu-id="3ad48-117">By performing these tasks, you'll help ensure that Office 365 Cloud App Security is configured correctly, your policies are up to date, and your organization realizes value from Office 365.</span></span> <span data-ttu-id="3ad48-118">Use este artículo como guía para ayudarle a planear estas tareas.</span><span class="sxs-lookup"><span data-stu-id="3ad48-118">Use this article as a guide to help you plan for these tasks.</span></span>
  
> [!NOTE]
> <span data-ttu-id="3ad48-119">Debe ser administrador global o administrador de seguridad para realizar las tareas descritas en este artículo.</span><span class="sxs-lookup"><span data-stu-id="3ad48-119">You must be a global administrator or security administrator to perform the tasks described in this article.</span></span> <span data-ttu-id="3ad48-120">Para obtener más información, consulte perMissions [in the &amp; Office 365 Security Compliance Center](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="3ad48-120">To learn more, see [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span> 
    
## <a name="activities-after-the-initial-configuration-and-rollout-of-office-365-cloud-app-security"></a><span data-ttu-id="3ad48-121">Actividades después de la configuración inicial y la implementación de Office 365 Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="3ad48-121">Activities after the initial configuration and rollout of Office 365 Cloud App Security</span></span>

<span data-ttu-id="3ad48-122">Una vez que Office 365 Cloud App Security se configura y se implementa, como administrador global o como administradores de seguridad, tiene que tener en cuenta varios aspectos:</span><span class="sxs-lookup"><span data-stu-id="3ad48-122">After Office 365 Cloud App Security is configured and rolled out, as a global administrator or security administrators, you have several things to consider:</span></span>
  
- <span data-ttu-id="3ad48-123">¿Qué tareas deben agregarse al calendario del Departamento de ti?</span><span class="sxs-lookup"><span data-stu-id="3ad48-123">What tasks need to be added to the IT department calendar?</span></span>
    
- <span data-ttu-id="3ad48-124">¿Cómo puede asegurarse de que la seguridad de la aplicación de nube de Office 365 está configurada para usar el conjunto de directivas adecuado a lo largo del tiempo?</span><span class="sxs-lookup"><span data-stu-id="3ad48-124">How can you make sure Office 365 Cloud App Security is configured to use the right set of policies over time?</span></span>
    
- <span data-ttu-id="3ad48-125">¿Qué tipo de información de Resumen debería enviar a la cadena de administración de ti?</span><span class="sxs-lookup"><span data-stu-id="3ad48-125">What kinds of summary information should you send up the IT management chain?</span></span>
    
<span data-ttu-id="3ad48-126">En la tabla siguiente se resumen brevemente las tareas en curso que desea realizar y las tareas periódicas que debería considerar para agregar al calendario del Departamento de ti.</span><span class="sxs-lookup"><span data-stu-id="3ad48-126">The following table briefly summarizes the ongoing tasks you'll want to perform and periodic tasks you should consider adding to your IT department's calendar.</span></span>
  
|<span data-ttu-id="3ad48-127">**Tareas en curso**</span><span class="sxs-lookup"><span data-stu-id="3ad48-127">**Ongoing tasks**</span></span>|<span data-ttu-id="3ad48-128">**Tareas periódicas**</span><span class="sxs-lookup"><span data-stu-id="3ad48-128">**Periodic tasks**</span></span>|
|:-----|:-----|
| <span data-ttu-id="3ad48-129">Supervisión de las cuentas de correo electrónico a las que envía mensajes de alerta</span><span class="sxs-lookup"><span data-stu-id="3ad48-129">Monitor the email accounts to which you are sending alert messages</span></span>  <br/>  <span data-ttu-id="3ad48-130">Supervisar los suministros de noticias de Cybersecurity de la industria para obtener la información más reciente acerca de los nuevos ataques cibernéticos</span><span class="sxs-lookup"><span data-stu-id="3ad48-130">Monitor industry cybersecurity news feeds for the latest information about new cyber attacks</span></span>  <br/>  <span data-ttu-id="3ad48-131">Actuar sobre alertas de seguridad para identificar y solucionar incidentes y riesgos de seguridad</span><span class="sxs-lookup"><span data-stu-id="3ad48-131">Act on security alerts to identify and address security incidents and risks</span></span>  <br/>  <span data-ttu-id="3ad48-132">ReSumir cada incidente de seguridad y resolución en un registro central</span><span class="sxs-lookup"><span data-stu-id="3ad48-132">Summarize each security incident and resolution in a central log</span></span>  <br/> | <span data-ttu-id="3ad48-133">Realizar revisiones mensuales o trimestrales de alertas de seguridad de aplicaciones de nube de Office 365 para detectar anomalías y analizar tendencias</span><span class="sxs-lookup"><span data-stu-id="3ad48-133">Perform monthly or quarterly reviews of Office 365 Cloud App Security alerts to spot anomalies and analyze trends</span></span>  <br/>  <span data-ttu-id="3ad48-134">Realizar revisiones mensuales o trimestrales de las directivas de seguridad de aplicaciones de la nube de Office 365 para incluir mejoras en la seguridad de aplicaciones en la nube de Office 365 y dirigir nuevas cyberattacks y tendencias en Cybersecurity</span><span class="sxs-lookup"><span data-stu-id="3ad48-134">Perform monthly or quarterly reviews of your existing Office 365 Cloud App Security policies to include enhancements in Office 365 Cloud App Security and address new cyberattacks and trends in cybersecurity</span></span>  <br/> |
   
<span data-ttu-id="3ad48-135">Según el tamaño y el interés de su organización en la supervisión y el mantenimiento de un Stature de seguridad, puede compilar un resumen mensual para la cadena de administración de ti que incluya lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="3ad48-135">Depending on your organization's size and interest in monitoring and maintaining a security stature, you can compile a monthly summary for your IT management chain that includes:</span></span>
  
- <span data-ttu-id="3ad48-136">Los diferentes tipos de incidentes de seguridad identificados con Office 365 Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="3ad48-136">The different types of security incidents identified with Office 365 Cloud App Security</span></span>
    
- <span data-ttu-id="3ad48-137">Información de resumen del registro central de los incidentes de seguridad, como el número de incidentes detectados</span><span class="sxs-lookup"><span data-stu-id="3ad48-137">Summary information from your central log of the security incidents, such as number of incidents detected</span></span>
    
- <span data-ttu-id="3ad48-138">Tendencias de alertas y cómo se trataron</span><span class="sxs-lookup"><span data-stu-id="3ad48-138">Alert trends and how they were addressed</span></span>
    
- <span data-ttu-id="3ad48-139">Las últimas tendencias de Cybersecurity</span><span class="sxs-lookup"><span data-stu-id="3ad48-139">The latest cybersecurity trends</span></span>
    
- <span data-ttu-id="3ad48-140">Recomendaciones para los cambios en la Directiva de seguridad de aplicación de Office 365 Cloud y su impacto en los usuarios finales</span><span class="sxs-lookup"><span data-stu-id="3ad48-140">Recommendations for Office 365 Cloud App Security policy changes and their impact on end users</span></span>
    
## <a name="activities-after-time-has-passed-since-rolling-out-office-365-cloud-app-security"></a><span data-ttu-id="3ad48-141">Actividades después de que ha pasado el tiempo desde la implementación de la seguridad de aplicación de nube de Office 365</span><span class="sxs-lookup"><span data-stu-id="3ad48-141">Activities after time has passed since rolling out Office 365 Cloud App Security</span></span>

<span data-ttu-id="3ad48-142">Si ha transcurrido una cantidad de tiempo que ha transcurrido desde que ha configurado o mantenido inicialmente sus directivas de seguridad de aplicación de nube de Office 365, siga estos pasos para volver a una configuración que refleje los objetivos de seguridad de su organización y las capacidades actuales. de Office 365 Cloud App Security:</span><span class="sxs-lookup"><span data-stu-id="3ad48-142">If a protracted amount of time has passed since you initially configured or maintained your Office 365 Cloud App Security policies, take the following steps to get back to a configuration that reflects your organization's security goals and the current capabilities of Office 365 Cloud App Security:</span></span>
  
1. <span data-ttu-id="3ad48-143">DeTermine la fecha del último cambio de configuración de Office 365 Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="3ad48-143">Determine the date of the last configuration change for Office 365 Cloud App Security.</span></span>
    
2. <span data-ttu-id="3ad48-144">Comprenda su configuración actual de seguridad de aplicaciones de nube de Office 365 y ajuste las directivas según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="3ad48-144">Understand your current Office 365 Cloud App Security configuration and adjust those policies as needed.</span></span> <span data-ttu-id="3ad48-145">Por ejemplo, asegúrese de que sabe dónde se envían las alertas por correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="3ad48-145">For example, make sure you know where alerts are being sent via email.</span></span>
    
3. <span data-ttu-id="3ad48-146">Consulte [what's New in office 365 Cloud App Security](new-in-office-365-cas.md) para cambios de productos desde la última vez que configuró Office 365 Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="3ad48-146">See [what's new in Office 365 Cloud App Security](new-in-office-365-cas.md) for product changes since you last configured Office 365 Cloud App Security.</span></span> 
    
4. <span data-ttu-id="3ad48-147">Realice un análisis de alertas y registros de seguridad de aplicaciones de nube de Office 365 para detectar anomalías y analizar tendencias.</span><span class="sxs-lookup"><span data-stu-id="3ad48-147">Perform an analysis of Office 365 Cloud App Security alerts and logs to spot anomalies and analyze trends.</span></span>
    
5. <span data-ttu-id="3ad48-148">Compruebe las tendencias de Cybersecurity de la industria para conocer las amenazas de seguridad más recientes.</span><span class="sxs-lookup"><span data-stu-id="3ad48-148">Check industry cybersecurity trends to become aware of the latest security threats.</span></span>
    
6. <span data-ttu-id="3ad48-149">Realice un análisis de los cambios que deben realizarse en el conjunto actual de directivas de seguridad de aplicaciones de nube de Office 365.</span><span class="sxs-lookup"><span data-stu-id="3ad48-149">Perform an analysis of the changes that need to be made to the current set of Office 365 Cloud App Security policies.</span></span> <span data-ttu-id="3ad48-150">Incorpore cambios de características de seguridad de aplicaciones de nube de Office 365, anomalías actuales y tendencias de Cybersecurity.</span><span class="sxs-lookup"><span data-stu-id="3ad48-150">Incorporate Office 365 Cloud App Security feature changes, current anomalies, and cybersecurity trends.</span></span> <span data-ttu-id="3ad48-151">Recomendar cambios a las directivas existentes o la creación de nuevas directivas.</span><span class="sxs-lookup"><span data-stu-id="3ad48-151">Recommend changes to existing policies or the creation of new policies.</span></span>
    
7. <span data-ttu-id="3ad48-152">Cree un plan para implementar los cambios de la Directiva.</span><span class="sxs-lookup"><span data-stu-id="3ad48-152">Make a plan for implementing the policy changes.</span></span> <span data-ttu-id="3ad48-153">Comunique (socialmente) las consecuencias de los cambios propuestos con los usuarios finales según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="3ad48-153">Communicate (socialize) the consequences of the proposed changes with your end users as needed.</span></span>
    
8. <span data-ttu-id="3ad48-154">Implemente los cambios de la Directiva de seguridad de aplicación de Office 365 Cloud.</span><span class="sxs-lookup"><span data-stu-id="3ad48-154">Implement the Office 365 Cloud App Security policy changes.</span></span>
    
9. <span data-ttu-id="3ad48-155">Supervise los comentarios de los usuarios finales y alertas de seguridad de aplicaciones de nube de Office 365 y ajuste las directivas a lo largo del tiempo.</span><span class="sxs-lookup"><span data-stu-id="3ad48-155">Monitor end user feedback and Office 365 Cloud App Security alerts and adjust policies over time.</span></span>
    
## <a name="next-steps"></a><span data-ttu-id="3ad48-156">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="3ad48-156">Next steps</span></span>

- [<span data-ttu-id="3ad48-157">Investigar una actividad</span><span class="sxs-lookup"><span data-stu-id="3ad48-157">Investigate an activity</span></span>](investigate-an-activity-in-office-365-cas.md)
    
- [<span data-ttu-id="3ad48-158">Suspender o restaurar una cuenta de usuario</span><span class="sxs-lookup"><span data-stu-id="3ad48-158">Suspend or restore a user account</span></span>](suspend-or-restore-an-account-in-ocas.md)
    
- [<span data-ttu-id="3ad48-159">Administrar aplicaciones de OAuth</span><span class="sxs-lookup"><span data-stu-id="3ad48-159">Manage OAuth apps</span></span>](manage-app-permissions-in-ocas.md)
    
- [<span data-ttu-id="3ad48-160">Revisar los resultados de la detección de aplicaciones en Office 365 Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="3ad48-160">Review app discovery findings in Office 365 Cloud App Security</span></span>](review-app-discovery-findings-in-ocas.md)
    
- <span data-ttu-id="3ad48-161">Ver una lista de los [orígenes de datos y los registros de tráfico web](web-traffic-logs-and-data-sources-for-ocas.md) admitidos</span><span class="sxs-lookup"><span data-stu-id="3ad48-161">View a list of supported [Web traffic logs and data sources](web-traffic-logs-and-data-sources-for-ocas.md)</span></span>
    

