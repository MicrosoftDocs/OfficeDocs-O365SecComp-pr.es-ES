---
title: Directivas de actividad y alertas en Office 365 Cloud App Security
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 01/28/2019
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 367f25d3-10a0-4a91-bdae-70ebb7a79c98
description: Definir directivas de actividad con Office 365 Cloud App Security para configurar las alertas que se desencadenen cuando se produzcan actividades específicas o se produzcan con demasiada frecuencia. Mediante la configuración de directivas para desencadenar alertas, puede recibir notificaciones sobre actividades específicas y supervisarlas.
ms.openlocfilehash: cfa58182ea35551ca3a3807c23e09c9f87c7be82
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/23/2019
ms.locfileid: "30219770"
---
# <a name="activity-policies-and-alerts-in-office-365-cloud-app-security"></a><span data-ttu-id="4191a-104">Directivas de actividad y alertas en Office 365 Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="4191a-104">Activity policies and alerts in Office 365 Cloud App Security</span></span>

|<span data-ttu-id="4191a-105">Evaluación \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="4191a-105">\*\*\*\*Evaluation\*\* \>\*\*</span></span>|<span data-ttu-id="4191a-106">Planeación \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="4191a-106">\*\*\*\*Planning\*\* \>\*\*</span></span>|<span data-ttu-id="4191a-107">Implementación \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="4191a-107">\*\*\*\*Deployment\*\* \>\*\*</span></span>|<span data-ttu-id="4191a-108">Uso \* \* \* \*</span><span class="sxs-lookup"><span data-stu-id="4191a-108">\*\*\*\*Utilization\*\*\*\*</span></span>|
|:-----|:-----|:-----|:-----|
|[<span data-ttu-id="4191a-109">Empezar a evaluar</span><span class="sxs-lookup"><span data-stu-id="4191a-109">Start evaluating</span></span>](office-365-cas-overview.md) <br/> |[<span data-ttu-id="4191a-110">Empezar a planear</span><span class="sxs-lookup"><span data-stu-id="4191a-110">Start planning</span></span>](get-ready-for-office-365-cas.md) <br/> |<span data-ttu-id="4191a-111">Ya está aquí.</span><span class="sxs-lookup"><span data-stu-id="4191a-111">You are here!</span></span>  <br/> [<span data-ttu-id="4191a-112">Siguiente paso</span><span class="sxs-lookup"><span data-stu-id="4191a-112">Next step</span></span>](anomaly-detection-policies-in-ocas.md) <br/> |[<span data-ttu-id="4191a-113">Empezar a usar</span><span class="sxs-lookup"><span data-stu-id="4191a-113">Start utilizing</span></span>](utilization-activities-for-ocas.md) <br/> |
   
<span data-ttu-id="4191a-p102">Con Office 365 Cloud App Security, las directivas de administración de nube avanzadas activan alertas para actividades específicas que ocurren o se producen con demasiada frecuencia. Por ejemplo, supongamos que un usuario intenta iniciar sesión en Office 365 y produce un error 70 veces en un minuto. SuPongamos que otro usuario descarga archivos de 7.000, o que parece que ha iniciado sesión en Canadá, cuando se supone que el usuario está en otra ubicación. O peor, supongamos que la cuenta de un usuario está en peligro y que un atacante está usando esa cuenta para acceder a las aplicaciones en la nube y a los datos confidenciales de la organización.</span><span class="sxs-lookup"><span data-stu-id="4191a-p102">With Office 365 Cloud App Security, advanced cloud management policies trigger alerts for specific activities that happen or happen too frequently. For example, suppose a user tries to sign in to Office 365 and fails 70 times in one minute. Suppose that another user downloads 7,000 files, or appears to be signed in from Canada, when that user is supposed to be in another location. Or worse, suppose that someone's account has been compromised, and an attacker is using that account to access your organization's cloud apps and sensitive data.</span></span>
  
<span data-ttu-id="4191a-p103">Si es [administrador global o administrador de seguridad](permissions-in-the-security-and-compliance-center.md), las alertas de actividad le notificarán cuando se produzcan eventos como estos. A continuación, puede realizar acciones específicas, como suspender una cuenta de usuario hasta que pueda investigar qué ha sucedido.</span><span class="sxs-lookup"><span data-stu-id="4191a-p103">If you are a [global administrator or security administrator](permissions-in-the-security-and-compliance-center.md), activity alerts notify you when events like these occur. You can then take specific actions, such as suspending a user account until you can investigate what happened.</span></span>
  
> [!NOTE]
> <span data-ttu-id="4191a-p104">Las directivas de seguridad de aplicación de nube de Office 365 son distintas de [las directivas &amp; de alerta del centro de seguridad y cumplimiento de Office 365](alert-policies.md). Las directivas de actividad descritas en este artículo se definen en el portal de seguridad de aplicaciones en la nube de Office 365 y pueden ayudarle a administrar mejor el entorno de nube de su organización.</span><span class="sxs-lookup"><span data-stu-id="4191a-p104">Office 365 Cloud App Security policies are different from [alert policies in the Office 365 Security &amp; Compliance Center](alert-policies.md). The activity policies described in this article are defined in the Office 365 Cloud App Security portal, and can help you better manage your organization's cloud environment.</span></span> 
  
## <a name="before-you-begin"></a><span data-ttu-id="4191a-122">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="4191a-122">Before you begin</span></span>

<span data-ttu-id="4191a-123">Asegúrese de que:</span><span class="sxs-lookup"><span data-stu-id="4191a-123">Make sure that:</span></span>
  
- <span data-ttu-id="4191a-124">Su organización tiene [Office 365 Cloud App Security](office-365-cas-overview.md)y el servicio está [activado](turn-on-office-365-cas.md).</span><span class="sxs-lookup"><span data-stu-id="4191a-124">Your organization has [Office 365 Cloud App Security](office-365-cas-overview.md), and the service is [turned on](turn-on-office-365-cas.md).</span></span>
    
- <span data-ttu-id="4191a-125">El [registro de auditoría](turn-audit-log-search-on-or-off.md) está activado para su entorno de Office 365.</span><span class="sxs-lookup"><span data-stu-id="4191a-125">[Audit logging](turn-audit-log-search-on-or-off.md) is turned on for your Office 365 environment.</span></span> 
    
- <span data-ttu-id="4191a-126">Es administrador global o administrador de seguridad de Office 365.</span><span class="sxs-lookup"><span data-stu-id="4191a-126">You are a global administrator or security administrator for Office 365.</span></span>
    
## <a name="create-a-new-activity-policy"></a><span data-ttu-id="4191a-127">Crear una nueva Directiva de actividad</span><span class="sxs-lookup"><span data-stu-id="4191a-127">Create a new activity policy</span></span>

1. <span data-ttu-id="4191a-128">Como administrador global o administrador de seguridad, vaya al portal de Cloud App Security ([https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)) e inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="4191a-128">As a global administrator or security administrator, go to the Cloud App Security portal ([https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)) and sign in.</span></span> <br><span data-ttu-id="4191a-129">Esto le llevará a la página de directivas de seguridad de aplicación de Office 365 Cloud.</span><span class="sxs-lookup"><span data-stu-id="4191a-129">This takes you to the Office 365 Cloud App Security Policies page.</span></span><br><span data-ttu-id="4191a-130">![Cuando vaya al portal de seguridad de la aplicación de nube de Office 365, empezará con la página de directivas.](media/5cb8833c-4e08-438c-bab3-91b5106f6f3f.png)</span><span class="sxs-lookup"><span data-stu-id="4191a-130">![When you go to the Office 365 Cloud App Security portal, you start with the Policies page](media/5cb8833c-4e08-438c-bab3-91b5106f6f3f.png)</span></span>
  
2. <span data-ttu-id="4191a-131">Haga clic en **crear Directiva**y, a continuación, seleccione **Directiva de actividad**.</span><span class="sxs-lookup"><span data-stu-id="4191a-131">Click **Create policy**, and then select **Activity policy**.</span></span><br><span data-ttu-id="4191a-132">![Al crear una directiva en las entidades de certificación de O365, puede elegir entre directivas de actividad y directivas de detección de anomalías.](media/79f34535-ddf9-4a5b-a0a3-8766bf9c174c.png)</span><span class="sxs-lookup"><span data-stu-id="4191a-132">![When you create a policy in O365 CAS, you can choose between Activity policies and Anomaly Detection policies.](media/79f34535-ddf9-4a5b-a0a3-8766bf9c174c.png)</span></span>
  
3. <span data-ttu-id="4191a-p105">En la página **crear Directiva de actividad** , especifique el nombre y la **Descripción**de la **Directiva** . Para basar la Directiva en una plantilla predeterminada, elija una en la lista **plantilla de directiva** o cree su propia Directiva sin usar una plantilla.</span><span class="sxs-lookup"><span data-stu-id="4191a-p105">On the **Create activity policy** page, specify the **Policy name** and **Description**. To base your policy on a default template, choose one in the **Policy template** list, or create your own policy without using a template.</span></span><br><span data-ttu-id="4191a-135">![Puede crear directivas de actividad con Office 365 Cloud App Security.](media/4083a76f-7074-4d6a-8200-6d76d49259d7.png)</span><span class="sxs-lookup"><span data-stu-id="4191a-135">![You can create activity policies with Office 365 Cloud App Security.](media/4083a76f-7074-4d6a-8200-6d76d49259d7.png)</span></span>
  
4. <span data-ttu-id="4191a-p106">Elija una **gravedad de directiva** (baja, media o alta) que mida lo seria que es si esta directiva desencadena una alerta. Esto le ayudará a filtrar las alertas cuando las esté revisando más adelante.</span><span class="sxs-lookup"><span data-stu-id="4191a-p106">Choose a **Policy severity** (Low, Medium, or High) that measures how serious it is to you if this policy triggers an alert. This will help you filter alerts when you're reviewing them later.</span></span> 
    
5. <span data-ttu-id="4191a-p107">Elija una **categoría** para esta Directiva. Esto le ayudará a filtrar y ordenar las alertas que se han desencadenado o a las directivas de grupo cuando las esté revisando para realizar cambios.</span><span class="sxs-lookup"><span data-stu-id="4191a-p107">Choose a **Category** for this policy. This will help you filter and sort alerts that have been triggered, or to group policies when you're reviewing them to make changes.</span></span> 
    
6. <span data-ttu-id="4191a-140">Elija **filtros de actividad** para configurar otras acciones o métricas que desencadenarán una alerta basada en esta Directiva.</span><span class="sxs-lookup"><span data-stu-id="4191a-140">Choose **Activity filters** to set up other actions or metrics that will trigger an alert based on this policy.</span></span> 
    
7. <span data-ttu-id="4191a-141">En **parámetros de coincidencia de actividad**, especifique si una infracción de Directiva se desencadenará cuando una sola actividad coincida con los filtros o si se requiere un número determinado de actividades repetidas antes de la activación de la alerta.</span><span class="sxs-lookup"><span data-stu-id="4191a-141">Under **Activity match parameters**, specify whether a policy violation will be triggered when a single activity matches the filters, or if a specified number of repeated activities is required before the alert triggers.</span></span><br><span data-ttu-id="4191a-142">Si selecciona la **actividad repetida**, especifique el número de actividades, el intervalo de tiempo y si la infracción se contará para un usuario dentro de una aplicación específica o para el mismo usuario con cualquier aplicación.</span><span class="sxs-lookup"><span data-stu-id="4191a-142">If you select **Repeated activity**, specify the number of activities, the time frame, and whether a violation will count for a user within a specific app or for the same user with any app.</span></span>
    
8. <span data-ttu-id="4191a-143">Opcionalmente, puede seleccionar **crear alerta** para crear alertas adicionales para recibir notificaciones de esta Directiva (por correo electrónico, mensaje de texto o ambos).</span><span class="sxs-lookup"><span data-stu-id="4191a-143">Optionally, you can select **Create alert** to create additional alerts to receive notifications from this policy (via email, text message, or both).</span></span><br><span data-ttu-id="4191a-144">Asegúrate de \*\*que tu proveedor de correo electrónico no bloquee `no-reply@cloudappsecurity.com`los correos electrónicos enviados desde \*\*.</span><span class="sxs-lookup"><span data-stu-id="4191a-144">**Make sure that your email provider doesn't block emails sent from `no-reply@cloudappsecurity.com`**.</span></span> 
  
9. <span data-ttu-id="4191a-145">Elija las **acciones** que se deben realizar cuando se desencadene una alerta para suspender al usuario o pedir al usuario que inicie sesión de nuevo en las aplicaciones de Office 365.</span><span class="sxs-lookup"><span data-stu-id="4191a-145">Choose the **Actions** that should be taken when an alert is triggered to suspend the user or require the user to sign in again to Office 365 apps.</span></span> 
    
10. <span data-ttu-id="4191a-146">Elija **crear** para finalizar la creación de la Directiva.</span><span class="sxs-lookup"><span data-stu-id="4191a-146">Choose **Create** to finish creating your policy.</span></span> 
    
## <a name="next-steps"></a><span data-ttu-id="4191a-147">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="4191a-147">Next steps</span></span>

- [<span data-ttu-id="4191a-148">Directivas de detección de anomalías</span><span class="sxs-lookup"><span data-stu-id="4191a-148">Anomaly detection policies</span></span>](anomaly-detection-policies-in-ocas.md)
    
- [<span data-ttu-id="4191a-149">Integración del servidor de SIEM</span><span class="sxs-lookup"><span data-stu-id="4191a-149">Integrate your SIEM server</span></span>](integrate-your-siem-server-with-office-365-cas.md)
    
- [<span data-ttu-id="4191a-150">Revisar y realizar acciones en las alertas</span><span class="sxs-lookup"><span data-stu-id="4191a-150">Review and take action on alerts</span></span>](review-office-365-cas-alerts.md)
    
- [<span data-ttu-id="4191a-151">Agrupar las direcciones IP para simplificar la administración</span><span class="sxs-lookup"><span data-stu-id="4191a-151">Group your IP addresses to simplify management</span></span>](group-your-ip-addresses-in-ocas.md)
    

