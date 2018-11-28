---
title: Introducción a Office 365 Cloud App Security
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: ITPro
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MET150
- MOE150
ms.assetid: 81f0ee9a-9645-45ab-ba56-de9cbccab475
description: 'Seguridad de la aplicación en la nube Office 365 proporciona entendimiento actividad sospechosa en Office 365 por lo que puede investigar situaciones en las que son potencialmente problemáticas y, si es necesario, tomar medidas para resolver problemas de seguridad. '
ms.openlocfilehash: b146512c22cbe86ce3aef95c5916de6959341578
ms.sourcegitcommit: 2cf7f5bb282c971d33e00f65d9982a3f14aec74e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/27/2018
ms.locfileid: "26706404"
---
# <a name="overview-of-office-365-cloud-app-security"></a><span data-ttu-id="e2823-103">Introducción a Office 365 Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="e2823-103">Overview of Office 365 Cloud App Security</span></span>
  
|<span data-ttu-id="e2823-104">Evaluación **\>**</span><span class="sxs-lookup"><span data-stu-id="e2823-104">\*\*\*\*Evaluation\*\* \>\*\*</span></span>|<span data-ttu-id="e2823-105">Planeación de **\>**</span><span class="sxs-lookup"><span data-stu-id="e2823-105">\*\*\*\*Planning\*\* \>\*\*</span></span>|<span data-ttu-id="e2823-106">Implementación **\>**</span><span class="sxs-lookup"><span data-stu-id="e2823-106">\*\*\*\*Deployment\*\* \>\*\*</span></span>|<span data-ttu-id="e2823-107">Utilización de \*\*\*</span><span class="sxs-lookup"><span data-stu-id="e2823-107">\*\*\*\*Utilization\*\*\*\*</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="e2823-108">¡Están aquí!</span><span class="sxs-lookup"><span data-stu-id="e2823-108">You are here!</span></span>  <br/> [<span data-ttu-id="e2823-109">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="e2823-109">Next step</span></span>](get-ready-for-office-365-cas.md) <br/> |[<span data-ttu-id="e2823-110">Comenzar a planear</span><span class="sxs-lookup"><span data-stu-id="e2823-110">Start planning</span></span>](get-ready-for-office-365-cas.md) <br/> |[<span data-ttu-id="e2823-111">Iniciar la implementación</span><span class="sxs-lookup"><span data-stu-id="e2823-111">Start deploying</span></span>](turn-on-office-365-cas.md) <br/> |[<span data-ttu-id="e2823-112">Iniciar utilizando</span><span class="sxs-lookup"><span data-stu-id="e2823-112">Start utilizing</span></span>](utilization-activities-for-ocas.md) <br/> |
   
> [!NOTE]
> <span data-ttu-id="e2823-p101">Seguridad de la aplicación de Office 365 en la nube está disponible en Office 365 Enterprise E5. Si su organización usa otra suscripción de Office 365 Enterprise, seguridad de la aplicación de nube de Office 365 puede adquirirse como un complemento. (Como administrador global, en el centro de administración de Office 365, elija **facturación** \> **Agregar suscripciones**.) Para obtener más información, vea [Descripción del servicio Office 365 plataforma: seguridad de Office 365 &amp; centro de cumplimiento](https://technet.microsoft.com/en-us/library/dn933793.aspx) y [comprar o editar un complemento de Office 365 para profesionales](https://support.office.com/article/4e7b57d6-b93b-457d-aecd-0ea58bff07a6).</span><span class="sxs-lookup"><span data-stu-id="e2823-p101">Office 365 Cloud App Security is available in Office 365 Enterprise E5. If your organization is using another Office 365 Enterprise subscription, Office 365 Cloud App Security can be purchased as an add-on. (As a global administrator, in the Office 365 admin center, choose **Billing** \> **Add subscriptions**.) For more information, see [Office 365 Platform Service Description: Office 365 Security &amp; Compliance Center](https://technet.microsoft.com/en-us/library/dn933793.aspx) and [Buy or edit an add-on for Office 365 for business](https://support.office.com/article/4e7b57d6-b93b-457d-aecd-0ea58bff07a6).</span></span> 
  
<span data-ttu-id="e2823-p102">Seguridad de la aplicación en la nube Office 365 proporciona una perspectiva de una actividad sospechosa en Office 365 por lo que puede investigar situaciones en las que son potencialmente problemáticas y, si es necesario, tomar medidas para resolver problemas de seguridad. Con la seguridad de la aplicación de nube de Office 365, puede recibir notificaciones de alertas desencadenadas para actividades atípicos o sospechosas, vea cómo se tiene acceso y se usa, los datos de la organización en Office 365 suspender las cuentas de usuario presenta actividad sospechosa y requieren a los usuarios iniciar sesión para aplicaciones de Office 365 después de que se haya desencadenado una alerta. Lea este artículo para obtener una visión general de las capacidades y características de seguridad de la aplicación de nube de Office 365.</span><span class="sxs-lookup"><span data-stu-id="e2823-p102">Office 365 Cloud App Security gives you insight into suspicious activity in Office 365 so you can investigate situations that are potentially problematic and, if needed, take action to address security issues. With Office 365 Cloud App Security, you can receive notifications of triggered alerts for atypical or suspicious activities, see how your organization's data in Office 365 is accessed and used, suspend user accounts exhibiting suspicious activity, and require users to log back in to Office 365 apps after an alert has been triggered. Read this article to get an overview of Office 365 Cloud App Security features and capabilities.</span></span>
  
    
## <a name="how-to-find-the-office-365-cloud-app-security-portal"></a><span data-ttu-id="e2823-119">Cómo encontrar el portal de seguridad de la aplicación de nube de Office 365</span><span class="sxs-lookup"><span data-stu-id="e2823-119">How to find the Office 365 Cloud App Security portal</span></span>

> [!NOTE]
> <span data-ttu-id="e2823-p103">Para obtener acceso al portal de seguridad de la aplicación de nube de Office 365, debe ser un administrador global, Administrador de seguridad o lector de seguridad. Para obtener más información, vea [permisos en la seguridad de Office 365 &amp; centro de cumplimiento](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="e2823-p103">To access the Office 365 Cloud App Security portal, you must be a global administrator, security administrator, or security reader. To learn more, see [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span> 
  
<span data-ttu-id="e2823-p104">Puede obtener el portal de seguridad de la aplicación de nube de Office 365 a través de la seguridad de Office 365 &amp; centro de cumplimiento. Aquí es una buena forma de hacerlo:</span><span class="sxs-lookup"><span data-stu-id="e2823-p104">You can get to the Office 365 Cloud App Security portal through the Office 365 Security &amp; Compliance Center. Here's one good way to do it:</span></span>
  
1. <span data-ttu-id="e2823-p105">Vaya a [https://security.microsoft.com](https://security.microsoft.com) e iniciar sesión con su cuenta de trabajo o escuela para Office 365. (Esto le llevará a la seguridad &amp; centro de cumplimiento.)</span><span class="sxs-lookup"><span data-stu-id="e2823-p105">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in using your work or school account for Office 365. (This takes you to the Security &amp; Compliance Center.)</span></span> 
    
2. <span data-ttu-id="e2823-126">En la seguridad &amp; centro de cumplimiento, elija **alertas** \> **avanzada de administrar las alertas**.</span><span class="sxs-lookup"><span data-stu-id="e2823-126">In the Security &amp; Compliance Center, choose **Alerts** \> **Manage advanced alerts**.</span></span> <br/><span data-ttu-id="e2823-127">![En la seguridad &amp; centro de cumplimiento, elija Administrar alertas avanzadas para ir a la seguridad de la aplicación de nube de Office 365](media/958632d4-03e3-4ade-8e22-d5509db6fca7.png)</span><span class="sxs-lookup"><span data-stu-id="e2823-127">![In the Security &amp; Compliance Center, choose Manage Advanced Alerts to go to Office 365 Cloud App Security](media/958632d4-03e3-4ade-8e22-d5509db6fca7.png)</span></span><br/><span data-ttu-id="e2823-128">(Si no está habilitado aún seguridad de la aplicación de nube de Office 365, y debe ser un administrador global, [activar la seguridad de la aplicación de nube de Office 365](turn-on-office-365-cas.md).)</span><span class="sxs-lookup"><span data-stu-id="e2823-128">(If Office 365 Cloud App Security is not yet enabled, and you are a global administrator, [turn on Office 365 Cloud App Security](turn-on-office-365-cas.md).)</span></span>
    
3. <span data-ttu-id="e2823-129">Elija **Ir a la seguridad de la aplicación de Office 365 en la nube**.</span><span class="sxs-lookup"><span data-stu-id="e2823-129">Choose **Go to Office 365 Cloud App Security**.</span></span> 
    
## <a name="policies"></a><span data-ttu-id="e2823-130">Policies</span><span class="sxs-lookup"><span data-stu-id="e2823-130">Policies</span></span>

<span data-ttu-id="e2823-p106">Office 365 funciona la seguridad de la aplicación en la nube con las directivas que se definen para su organización. Con la seguridad de la aplicación de nube de Office 365, su organización obtiene 10 directivas de detección de anomalías predefinidos y varias plantillas de directivas de actividad. Estas directivas están diseñadas para detectar anomalías general, identificar a los usuarios el registro de una dirección IP arriesgada, detectar actividades ransomware, detectar actividades de administrador de direcciones IP de no corporativos y mucho más.</span><span class="sxs-lookup"><span data-stu-id="e2823-p106">Office 365 Cloud App Security works with the policies that are defined for your organization. With Office 365 Cloud App Security, your organization gets 10 predefined anomaly detection policies and several templates for activity policies. These policies are designed to detect general anomalies, identify users logging in from a risky IP address, detect ransomware activities, detect administrator activities from non-corporate IP addresses, and more.</span></span>
  
![En el portal de entidades de certificación, elija Control \> plantillas para ver o crear plantillas de directiva](media/88f615b4-aa8a-480c-b239-323dfcd628e1.png)
  
<span data-ttu-id="e2823-135">Para ver o usar las plantillas de directiva, en el portal de seguridad de la aplicación de nube de Office 365, vaya al **Control** \> **plantillas**.</span><span class="sxs-lookup"><span data-stu-id="e2823-135">To view/use policy templates, in the Office 365 Cloud App Security portal, go to **Control** \> **Templates**.</span></span> 
  
![En el portal de O365 CAS, elija Control](media/287c2ea9-5172-4697-8e0e-b9ab654105bc.png)
  
<span data-ttu-id="e2823-137">Para obtener más información acerca de las directivas, vea los siguientes recursos:</span><span class="sxs-lookup"><span data-stu-id="e2823-137">To learn more about policies, see the following resources:</span></span>
  
- [<span data-ttu-id="e2823-138">Directivas de actividad y alertas en Office 365 Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="e2823-138">Activity policies and alerts in Office 365 Cloud App Security</span></span>](activity-policies-and-alerts.md)
    
- [<span data-ttu-id="e2823-139">Directivas de detección de anomalías en Office 365 Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="e2823-139">Anomaly detection policies in Office 365 Cloud App Security</span></span>](anomaly-detection-policies-in-ocas.md)
    
## <a name="alerts"></a><span data-ttu-id="e2823-140">Alertas</span><span class="sxs-lookup"><span data-stu-id="e2823-140">Alerts</span></span>

<span data-ttu-id="e2823-p107">Cuando se definen las directivas, alertas informan acerca de actividades sospechosas o atípicos que se detectaron. Para ver las alertas para la organización, elija **alertas** en la barra de navegación a través de la parte superior de la pantalla.</span><span class="sxs-lookup"><span data-stu-id="e2823-p107">When policies are defined, alerts notify you about suspicious or atypical activities that were detected. To view alerts for your organization, choose **Alerts** in the navigation bar across the top of the screen.</span></span> 
  
![En la página alertas, puede ver las alertas que se activaron y todas las acciones realizadas.](media/3b53d4c9-4b13-435d-8547-8c0f9ae6b914.png)
  
<span data-ttu-id="e2823-p108">Tal y como se desencadenan alertas puede revisarlos para obtener más información acerca de lo que está ocurriendo. A continuación, si la actividad es aún sospechosa, puede tomar medidas. Por ejemplo, puede notificar a un usuario sobre un problema, suspender un usuario de inicio de sesión en Office 365 o requieren un usuario iniciar sesión en aplicaciones de Office 365.</span><span class="sxs-lookup"><span data-stu-id="e2823-p108">As alerts are triggered you can review them to learn more about what is going on. Then, if the activity is still suspicious, you can take action. For example, you can notify a user about an issue, suspend a user from signing in to Office 365, or require a user to sign back in to Office 365 apps.</span></span>
  
<span data-ttu-id="e2823-147">Para obtener más información acerca de las alertas, vea los siguientes recursos:</span><span class="sxs-lookup"><span data-stu-id="e2823-147">To learn more about alerts, see the following resources:</span></span>
  
- [<span data-ttu-id="e2823-148">Directivas de actividad y alertas en Office 365 Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="e2823-148">Activity policies and alerts in Office 365 Cloud App Security</span></span>](activity-policies-and-alerts.md)
    
- [<span data-ttu-id="e2823-149">Directivas de detección de anomalías en Office 365 Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="e2823-149">Anomaly detection policies in Office 365 Cloud App Security</span></span>](anomaly-detection-policies-in-ocas.md)
    
- [<span data-ttu-id="e2823-150">Revisar y realizar acciones en las alertas de seguridad de la aplicación de nube de Office 365</span><span class="sxs-lookup"><span data-stu-id="e2823-150">Review and take action on Office 365 Cloud App Security alerts</span></span>](review-office-365-cas-alerts.md)
    
## <a name="activity-logs"></a><span data-ttu-id="e2823-151">Registros de actividad</span><span class="sxs-lookup"><span data-stu-id="e2823-151">Activity logs</span></span>

<span data-ttu-id="e2823-152">Ver información acerca de las actividades del usuario en la página de registro de actividad de seguridad de la aplicación de nube de Office 365.</span><span class="sxs-lookup"><span data-stu-id="e2823-152">View information about user activities on your Activity log page in Office 365 Cloud App Security.</span></span>
  
![En el portal de O365 CAS, elija investigar \> registro de actividad](media/ec19e77d-4e11-49fc-ab7c-0e8b0c29c93c.png)
  
<span data-ttu-id="e2823-154">Para tener acceso a esta página, en el portal de seguridad de la aplicación de nube de Office 365, vaya a **investigar** \> **registro de actividad**.</span><span class="sxs-lookup"><span data-stu-id="e2823-154">To get to this page, in the Office 365 Cloud App Security portal, go to **Investigate** \> **Activity log**.</span></span> 
  
![En el portal de O365 CAS, elija investigar.](media/8c7b87c9-71a6-4952-adb2-185e941ffe9a.png)
  
<span data-ttu-id="e2823-p109">Puede usar los registros de tráfico web con seguridad de la aplicación de nube de Office 365, demasiado. Cuantos más detalles que se incluyen en los archivos de registro, la mejor visibilidad tendrá en la actividad del usuario. Puede usar los archivos de registro de Barracuda, capa azul, Check Point, Cisco, Clavister, Dell SonicWALL, Fortinet, Juniper, McAfee, Microsoft, Palo Alto, Sophos, Squid, Websence, Zscaler y mucho más.</span><span class="sxs-lookup"><span data-stu-id="e2823-p109">You can use your web traffic logs with Office 365 Cloud App Security, too. The more details that are included in those log files, the better visibility you'll have into user activity. You can use log files from Barracuda, Blue Coat, Check Point, Cisco, Clavister, Dell SonicWALL, Fortinet, Juniper, McAfee, Microsoft, Palo Alto, Sophos, Squid, Websence, Zscaler, and more.</span></span>
  
[<span data-ttu-id="e2823-159">Obtenga información acerca de los orígenes de datos y los registros de tráfico web para seguridad de la aplicación de nube de Office 365</span><span class="sxs-lookup"><span data-stu-id="e2823-159">Learn about web traffic logs and data sources for Office 365 Cloud App Security</span></span>](web-traffic-logs-and-data-sources-for-ocas.md)
  
## <a name="app-permissions"></a><span data-ttu-id="e2823-160">Permisos de aplicación</span><span class="sxs-lookup"><span data-stu-id="e2823-160">App permissions</span></span>

<span data-ttu-id="e2823-161">Con Office 365 en la nube seguridad de la aplicación, puede permitir o impedir que los usuarios de la organización para usar aplicaciones de terceros que tienen acceso a datos en Office 365.</span><span class="sxs-lookup"><span data-stu-id="e2823-161">With Office 365 Cloud App Security, you can allow or prevent people in your organization to use third-party apps that access data in Office 365.</span></span>
  
![En CAS de O365, puede tener acceso a la página Administrar permisos de aplicación en el menú investigar.](media/78272cda-986f-4b3b-bbbe-8c236c74f5d3.png)
  
<span data-ttu-id="e2823-163">Para llegar a esta página, vaya a **investigar** \> **permisos de aplicación**.</span><span class="sxs-lookup"><span data-stu-id="e2823-163">To get to this page, go to **Investigate** \> **App permissions**.</span></span> 
  
![En el portal de O365 CAS, elija investigar.](media/8c7b87c9-71a6-4952-adb2-185e941ffe9a.png)
  
[<span data-ttu-id="e2823-165">Administrar permisos de aplicación con Office 365 Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="e2823-165">Manage app permissions using Office 365 Cloud App Security</span></span>](manage-app-permissions-in-ocas.md)
  
## <a name="cloud-discovery-dashboard"></a><span data-ttu-id="e2823-166">Panel de detección de la nube</span><span class="sxs-lookup"><span data-stu-id="e2823-166">Cloud Discovery Dashboard</span></span>

<span data-ttu-id="e2823-p110">El **Panel de la detección de la nube**, también conocida como **Detección de aplicaciones de productividad**, muestra información sobre el uso de la aplicación en la nube dentro de la organización. Puede ver información acerca de aplicaciones, los usuarios, el tráfico, las transacciones y más mediante este panel. El panel de detección en la nube es similar a la siguiente imagen:</span><span class="sxs-lookup"><span data-stu-id="e2823-p110">The **Cloud Discovery Dashboard**, also referred to as **Productivity App Discovery**, shows information about cloud app usage within your organization. You can view information about apps, users, traffic, transactions, and more using this dashboard. The Cloud Discovery Dashboard resembles the following image:</span></span> 
  
![En el portal de Office 365 CAS, elija detectar \> panel de detección de la nube](media/61269290-fd82-4d4b-8045-aea1ebc82287.png)
  
<span data-ttu-id="e2823-171">Para llegar a este panel, en el portal de seguridad de la aplicación de nube de Office 365, vaya a **descubrir** \> **panel de detección de la nube**.</span><span class="sxs-lookup"><span data-stu-id="e2823-171">To get to this dashboard, in the Office 365 Cloud App Security portal, go to **Discover** \> **Cloud Discovery dashboard**.</span></span> 
  
![En el portal de Office 365 CAS, elija detectar](media/73b5299f-94b5-49dd-a00f-154d188eb2c5.png)
  
[<span data-ttu-id="e2823-173">Revisar los resultados de la detección de aplicaciones en Office 365 Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="e2823-173">Review app discovery findings in Office 365 Cloud App Security</span></span>](review-app-discovery-findings-in-ocas.md)
  
## <a name="next-steps"></a><span data-ttu-id="e2823-174">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="e2823-174">Next steps</span></span>

- <span data-ttu-id="e2823-175">Obtenga la [Guía de uso y casos de uso de seguridad de aplicación de nube de Office 365](https://aka.ms/O365CASGuide)</span><span class="sxs-lookup"><span data-stu-id="e2823-175">Get the [Office 365 Cloud App Security Use Cases and Usage Guide](https://aka.ms/O365CASGuide)</span></span>
    
- [<span data-ttu-id="e2823-176">Prepararse para Office 365 Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="e2823-176">Get ready for Office 365 Cloud App Security</span></span>](get-ready-for-office-365-cas.md)
    

