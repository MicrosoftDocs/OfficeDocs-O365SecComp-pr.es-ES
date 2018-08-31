---
title: Directivas de actividad y alertas en Office 365 Cloud App Security
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
ms.assetid: 367f25d3-10a0-4a91-bdae-70ebb7a79c98
description: Definir directivas de actividad con Office 365 la seguridad de la aplicación de nube para configurar alertas para desencadenar cuando actividades específicas suceden o sucedería con demasiada frecuencia. Mediante la configuración de directivas para activar las alertas, puede recibir una notificación sobre y supervisar las actividades específicas.
ms.openlocfilehash: a239e2bf453a01bf852a702a66cb2f09c02b8c96
ms.sourcegitcommit: c31424cafbf1953f2864d7e2ceb95b329a694edb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/29/2018
ms.locfileid: "23272375"
---
# <a name="activity-policies-and-alerts-in-office-365-cloud-app-security"></a><span data-ttu-id="2879c-104">Directivas de actividad y alertas en Office 365 Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="2879c-104">Activity policies and alerts in Office 365 Cloud App Security</span></span>

<span data-ttu-id="2879c-105">Administración avanzada de seguridad de Office 365 es ahora de seguridad de la aplicación de nube de Office 365.</span><span class="sxs-lookup"><span data-stu-id="2879c-105">Office 365 Advanced Security Management is now Office 365 Cloud App Security.</span></span>
  
|<span data-ttu-id="2879c-106">Evaluación **\>**</span><span class="sxs-lookup"><span data-stu-id="2879c-106">****Evaluation** \>**</span></span>|<span data-ttu-id="2879c-107">Planeación de **\>**</span><span class="sxs-lookup"><span data-stu-id="2879c-107">****Planning** \>**</span></span>|<span data-ttu-id="2879c-108">Implementación **\>**</span><span class="sxs-lookup"><span data-stu-id="2879c-108">****Deployment** \>**</span></span>|<span data-ttu-id="2879c-109">Utilización de \*\*\*</span><span class="sxs-lookup"><span data-stu-id="2879c-109">****Utilization****</span></span>|
|:-----|:-----|:-----|:-----|
|[<span data-ttu-id="2879c-110">Empezar a evaluar</span><span class="sxs-lookup"><span data-stu-id="2879c-110">Start evaluating</span></span>](office-365-cas-overview.md) <br/> |[<span data-ttu-id="2879c-111">Comenzar a planear</span><span class="sxs-lookup"><span data-stu-id="2879c-111">Start planning</span></span>](get-ready-for-office-365-cas.md) <br/> |<span data-ttu-id="2879c-112">¡Están aquí!</span><span class="sxs-lookup"><span data-stu-id="2879c-112">You are here!</span></span>  <br/> [<span data-ttu-id="2879c-113">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="2879c-113">Next step</span></span>](anomaly-detection-policies-in-ocas.md) <br/> |[<span data-ttu-id="2879c-114">Iniciar utilizando</span><span class="sxs-lookup"><span data-stu-id="2879c-114">Start utilizing</span></span>](utilization-activities-for-ocas.md) <br/> |
   
<span data-ttu-id="2879c-p102">Con la seguridad de la aplicación de nube de Office 365, las directivas de administración de la nube avanzada activan las alertas para las actividades específicas que suceden o sucedería con demasiada frecuencia. Por ejemplo, supongamos que un usuario intenta iniciar sesión en Office 365 y se produce un error 70 veces en un minuto. Suponga que otro usuario descarga los archivos de 7.000 o parece que se conectan desde Canadá, cuando ese usuario debe para estar en otra ubicación. O bien, lo que es peor, suponga que se ha puesto en peligro la cuenta de otra persona, y un atacante usa esa cuenta para obtener acceso a aplicaciones de nube de su organización y los datos confidenciales.</span><span class="sxs-lookup"><span data-stu-id="2879c-p102">With Office 365 Cloud App Security, advanced cloud management policies trigger alerts for specific activities that happen or happen too frequently. For example, suppose a user tries to sign in to Office 365 and fails 70 times in one minute. Suppose that another user downloads 7,000 files, or appears to be signed in from Canada, when that user is supposed to be in another location. Or worse, suppose that someone's account has been compromised, and an attacker is using that account to access your organization's cloud apps and sensitive data.</span></span>
  
<span data-ttu-id="2879c-p103">Si es un [administrador global o administrador de seguridad](permissions-in-the-security-and-compliance-center.md), las alertas de actividad notificación cuando eventos como éstas se produce. A continuación, puede realizar acciones específicas, como la suspensión de una cuenta de usuario hasta que puede investigar qué ha ocurrido.</span><span class="sxs-lookup"><span data-stu-id="2879c-p103">If you are a [global administrator or security administrator](permissions-in-the-security-and-compliance-center.md), activity alerts notify you when events like these occur. You can then take specific actions, such as suspending a user account until you can investigate what happened.</span></span>
  
> [!NOTE]
> <span data-ttu-id="2879c-p104">Son diferentes de las directivas de seguridad de la aplicación en la nube de Office 365 [las directivas de la seguridad de Office 365 de la alerta &amp; centro de cumplimiento](alert-policies.md). La actividad de las directivas que se describen en este artículo se definen en el portal de seguridad de la aplicación de nube de Office 365 y pueden ayudarle a una mejor administración de entorno de nube de su organización.</span><span class="sxs-lookup"><span data-stu-id="2879c-p104">Office 365 Cloud App Security policies are different from [alert policies in the Office 365 Security &amp; Compliance Center](alert-policies.md). The activity policies described in this article are defined in the Office 365 Cloud App Security portal, and can help you better manage your organization's cloud environment.</span></span> 
  
## <a name="before-you-begin"></a><span data-ttu-id="2879c-123">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="2879c-123">Before you begin</span></span>

<span data-ttu-id="2879c-124">Asegúrese de que:</span><span class="sxs-lookup"><span data-stu-id="2879c-124">Make sure that:</span></span>
  
- <span data-ttu-id="2879c-125">Su organización tiene la [Seguridad de la aplicación de Office 365 en la nube](office-365-cas-overview.md)y el servicio está [activado](turn-on-office-365-cas.md).</span><span class="sxs-lookup"><span data-stu-id="2879c-125">Your organization has [Office 365 Cloud App Security](office-365-cas-overview.md), and the service is [turned on](turn-on-office-365-cas.md).</span></span>
    
- <span data-ttu-id="2879c-126">[Registro de auditoría](turn-audit-log-search-on-or-off.md) está activado para el entorno de Office 365.</span><span class="sxs-lookup"><span data-stu-id="2879c-126">[Audit logging](turn-audit-log-search-on-or-off.md) is turned on for your Office 365 environment.</span></span> 
    
- <span data-ttu-id="2879c-127">Es un administrador global o administrador de seguridad para Office 365.</span><span class="sxs-lookup"><span data-stu-id="2879c-127">You are a global administrator or security administrator for Office 365.</span></span>
    
## <a name="create-a-new-activity-policy"></a><span data-ttu-id="2879c-128">Crear una nueva directiva de actividad</span><span class="sxs-lookup"><span data-stu-id="2879c-128">Create a new activity policy</span></span>

1. <span data-ttu-id="2879c-129">Como administrador global o administrador de seguridad, vaya a [https://protection.office.com](https://protection.office.com) e iniciar sesión con su cuenta de trabajo o escuela.</span><span class="sxs-lookup"><span data-stu-id="2879c-129">As a global administrator or security administrator, go to [https://protection.office.com](https://protection.office.com) and sign in using your work or school account.</span></span> 
    
2. <span data-ttu-id="2879c-130">En la seguridad &amp; centro de cumplimiento, elija **alertas** \> **avanzada de administrar las alertas**.</span><span class="sxs-lookup"><span data-stu-id="2879c-130">In the Security &amp; Compliance Center, choose **Alerts** \> **Manage advanced alerts**.</span></span>
    
3. <span data-ttu-id="2879c-131">Elija **Ir a la seguridad de la aplicación de Office 365 en la nube**.</span><span class="sxs-lookup"><span data-stu-id="2879c-131">Choose **Go to Office 365 Cloud App Security**.</span></span>
    
    <span data-ttu-id="2879c-132">Esto le llevará a la página de directivas de seguridad de aplicaciones de Office 365 en la nube.</span><span class="sxs-lookup"><span data-stu-id="2879c-132">This takes you to the Office 365 Cloud App Security Policies page.</span></span>
    
    ![Cuando vaya al portal de seguridad de la aplicación de nube de Office 365, empezar con la página de directivas](media/5cb8833c-4e08-438c-bab3-91b5106f6f3f.png)
  
4. <span data-ttu-id="2879c-134">Haga clic en **Crear directiva**y, a continuación, seleccione **Directiva de actividad**.</span><span class="sxs-lookup"><span data-stu-id="2879c-134">Click **Create policy**, and then select **Activity policy**.</span></span>
    
    ![Cuando se crea una directiva en O365 CAS, puede elegir entre las directivas de la actividad y detección de anomalías.](media/79f34535-ddf9-4a5b-a0a3-8766bf9c174c.png)
  
5. <span data-ttu-id="2879c-p105">En la página **Crear directiva de actividad** , especifique el **nombre de la directiva** y la **Descripción**. Para basar la directiva en una plantilla predeterminada, elija uno en la lista **plantilla de directiva** o crear su propia directiva sin utilizar una plantilla.</span><span class="sxs-lookup"><span data-stu-id="2879c-p105">On the **Create activity policy** page, specify the **Policy name** and **Description**. To base your policy on a default template, choose one in the **Policy template** list, or create your own policy without using a template.</span></span> 
    
    ![Puede crear directivas de actividad con seguridad de la aplicación de nube de Office 365.](media/4083a76f-7074-4d6a-8200-6d76d49259d7.png)
  
6. <span data-ttu-id="2879c-p106">Elija una **gravedad de directiva** (bajo, medio o alto) que mide el grado de gravedad es para usted si esta directiva desencadena una alerta. Esto le ayudará a filtrar alertas cuando está revisarlos más adelante.</span><span class="sxs-lookup"><span data-stu-id="2879c-p106">Choose a **Policy severity** (Low, Medium, or High) that measures how serious it is to you if this policy triggers an alert. This will help you filter alerts when you're reviewing them later.</span></span> 
    
7. <span data-ttu-id="2879c-p107">Elija una **categoría** para esta directiva. Esto le ayudará a filtrar y ordenar las alertas que se han desencadenado, o a las directivas de grupo cuando está revisando ellos para realizar cambios.</span><span class="sxs-lookup"><span data-stu-id="2879c-p107">Choose a **Category** for this policy. This will help you filter and sort alerts that have been triggered, or to group policies when you're reviewing them to make changes.</span></span> 
    
8. <span data-ttu-id="2879c-143">Elija **filtros de actividad** para configurar otras acciones o métricas que se activarán una alerta en función de esta directiva.</span><span class="sxs-lookup"><span data-stu-id="2879c-143">Choose **Activity filters** to set up other actions or metrics that will trigger an alert based on this policy.</span></span> 
    
9. <span data-ttu-id="2879c-144">En la **actividad coinciden con los parámetros**, especifique si una infracción de la directiva se desencadenará cuando una sola actividad coincide con los filtros, o si es necesario un número especificado de actividades repetidas antes de la alertas desencadenadores.</span><span class="sxs-lookup"><span data-stu-id="2879c-144">Under **Activity match parameters**, specify whether a policy violation will be triggered when a single activity matches the filters, or if a specified number of repeated activities is required before the alert triggers.</span></span>
    
    <span data-ttu-id="2879c-145">Si selecciona **repetida actividad**, especifique el número de actividades, el plazo de tiempo, y si una infracción contarán para un usuario dentro de una aplicación específica o para el mismo usuario con cualquier aplicación.</span><span class="sxs-lookup"><span data-stu-id="2879c-145">If you select **Repeated activity**, specify the number of activities, the time frame, and whether a violation will count for a user within a specific app or for the same user with any app.</span></span>
    
10. <span data-ttu-id="2879c-146">De forma opcional, puede seleccionar **crear alerta** para crear alertas adicionales para que reciba notificaciones de esta directiva (a través de correo electrónico, mensaje de texto o ambos).</span><span class="sxs-lookup"><span data-stu-id="2879c-146">Optionally, you can select **Create alert** to create additional alerts to receive notifications from this policy (via email, text message, or both).</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="2879c-147">Asegúrese de que su proveedor de correo electrónico no bloquea los correos electrónicos enviados desde no-reply@cloudappsecurity.com.</span><span class="sxs-lookup"><span data-stu-id="2879c-147">Make sure that your email provider doesn't block emails sent from no-reply@cloudappsecurity.com.</span></span> 
  
11. <span data-ttu-id="2879c-148">Elija las **acciones** que deben tomarse cuando se desencadena una alerta para suspender el usuario o requieren que el usuario iniciar sesión de nuevo a las aplicaciones de Office 365.</span><span class="sxs-lookup"><span data-stu-id="2879c-148">Choose the **Actions** that should be taken when an alert is triggered to suspend the user or require the user to sign in again to Office 365 apps.</span></span> 
    
12. <span data-ttu-id="2879c-149">Elija **crear** para terminar de crear la directiva.</span><span class="sxs-lookup"><span data-stu-id="2879c-149">Choose **Create** to finish creating your policy.</span></span> 
    
## <a name="next-steps"></a><span data-ttu-id="2879c-150">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="2879c-150">Next steps</span></span>
<span data-ttu-id="2879c-151"><a name="nextsteps"> </a></span><span class="sxs-lookup"><span data-stu-id="2879c-151"></span></span>

- [<span data-ttu-id="2879c-152">Directivas de detección de anomalías</span><span class="sxs-lookup"><span data-stu-id="2879c-152">Anomaly detection policies</span></span>](anomaly-detection-policies-in-ocas.md)
    
- [<span data-ttu-id="2879c-153">Integrar su servidor SIEM</span><span class="sxs-lookup"><span data-stu-id="2879c-153">Integrate your SIEM server</span></span>](integrate-your-siem-server-with-office-365-cas.md)
    
- [<span data-ttu-id="2879c-154">Revisar y realizar acciones en las alertas</span><span class="sxs-lookup"><span data-stu-id="2879c-154">Review and take action on alerts</span></span>](review-office-365-cas-alerts.md)
    
- [<span data-ttu-id="2879c-155">Las direcciones IP para simplificar la administración de grupo</span><span class="sxs-lookup"><span data-stu-id="2879c-155">Group your IP addresses to simplify management</span></span>](group-your-ip-addresses-in-ocas.md)
    

