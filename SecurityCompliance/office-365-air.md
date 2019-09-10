---
title: Investigar y responder automáticamente a las amenazas en Office 365
keywords: AIR, autoIR, ATP, automatizado, investigación, respuesta, corrección, amenazas, avanzadas, amenazas, protección
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 09/09/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
description: Empiece a usar la investigación automatizada y las capacidades de respuesta en Office 365 Advanced Threat Protection Plan 2.
ms.openlocfilehash: 45fea46a591aac88a8d92c7a67d024d1446e9124
ms.sourcegitcommit: 81b3bff27bc60235a38004c5b0297ac454331b25
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2019
ms.locfileid: "36822500"
---
# <a name="automatically-investigate-and-respond-to-threats-in-office-365"></a><span data-ttu-id="54e8b-104">Investigar y responder automáticamente a las amenazas en Office 365</span><span class="sxs-lookup"><span data-stu-id="54e8b-104">Automatically investigate and respond to threats in Office 365</span></span>

## <a name="overview"></a><span data-ttu-id="54e8b-105">Información general</span><span class="sxs-lookup"><span data-stu-id="54e8b-105">Overview</span></span>

<span data-ttu-id="54e8b-106">[Protección contra amenazas avanzada de Office 365](office-365-atp.md) El plan 2 incluye capacidades de respuesta de incidente (AIR) automatizadas que pueden salvar el tiempo y el esfuerzo del equipo de operaciones de seguridad para tratar las alertas y amenazas.</span><span class="sxs-lookup"><span data-stu-id="54e8b-106">[Office 365 Advanced Threat Protection](office-365-atp.md) Plan 2 includes automated incident response (AIR) capabilities that can save your security operations team time and effort in dealing with alerts and threats.</span></span> <span data-ttu-id="54e8b-107">Lea este artículo para empezar a usar las funcionalidades de AIR en Office 365.</span><span class="sxs-lookup"><span data-stu-id="54e8b-107">Read this article to get started using AIR capabilities in Office 365.</span></span> <span data-ttu-id="54e8b-108">Para obtener más información acerca de cómo funciona AIR, vea [respuesta de incidente automatizada (Air) en Office 365](automated-investigation-response-office.md).</span><span class="sxs-lookup"><span data-stu-id="54e8b-108">To learn more about how AIR works, see [Automated incident response (AIR) in Office 365](automated-investigation-response-office.md).</span></span>

<span data-ttu-id="54e8b-109">Con AIR, cuando se desencadenan determinadas alertas, se inician una o más guías de seguridad y comienza la investigación automatizada.</span><span class="sxs-lookup"><span data-stu-id="54e8b-109">With AIR, when certain alerts are triggered, one or more security playbooks initiate, and automated investigation begins.</span></span> <span data-ttu-id="54e8b-110">Durante y después de un proceso de investigación automatizado, los administradores y el equipo de operaciones de seguridad pueden:</span><span class="sxs-lookup"><span data-stu-id="54e8b-110">During and after an automated investigation process, your administrators and security operations team can:</span></span>

- [<span data-ttu-id="54e8b-111">Ver los detalles de una investigación</span><span class="sxs-lookup"><span data-stu-id="54e8b-111">View the details of an investigation</span></span>](#view-details-of-an-investigation)

- [<span data-ttu-id="54e8b-112">Revisión y aprobación de acciones como resultado de una investigación</span><span class="sxs-lookup"><span data-stu-id="54e8b-112">Review and approve actions as a result of an investigation</span></span>](#review-and-approve-actions) 

- [<span data-ttu-id="54e8b-113">Ver los detalles de una alerta relacionada con una investigación</span><span class="sxs-lookup"><span data-stu-id="54e8b-113">View details about an alert related to an investigation</span></span>](#view-details-about-an-alert-related-to-an-investigation)

> [!NOTE]
> <span data-ttu-id="54e8b-114">Debe ser administrador global, administrador de seguridad, operador de seguridad o lector de seguridad para realizar las tareas descritas en este artículo.</span><span class="sxs-lookup"><span data-stu-id="54e8b-114">You must be a global administrator, security administrator, security operator, or security reader to perform the tasks described in this article.</span></span> <span data-ttu-id="54e8b-115">Para obtener más información, consulte [Microsoft 365 Security Center: roles y permisos](https://docs.microsoft.com/office365/securitycompliance/microsoft-security-and-compliance#required-licenses-and-permissions).</span><span class="sxs-lookup"><span data-stu-id="54e8b-115">To learn more, see [Microsoft 365 security center: roles and permissions](https://docs.microsoft.com/office365/securitycompliance/microsoft-security-and-compliance#required-licenses-and-permissions).</span></span>

## <a name="view-details-of-an-investigation"></a><span data-ttu-id="54e8b-116">Ver los detalles de una investigación</span><span class="sxs-lookup"><span data-stu-id="54e8b-116">View details of an investigation</span></span>

1. <span data-ttu-id="54e8b-117">Como administrador global de Office 365, administrador de seguridad o lector de seguridad, vaya [https://protection.office.com](https://protection.office.com) a e inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="54e8b-117">As an Office 365 global administrator, security administrator, or security reader, go to [https://protection.office.com](https://protection.office.com) and sign in.</span></span> <span data-ttu-id="54e8b-118">Esto le llevará al centro de seguridad & cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="54e8b-118">This takes you to the the Security & Compliance Center.</span></span>

2. <span data-ttu-id="54e8b-119">Realice una de las acciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="54e8b-119">Do one of the following:</span></span>

    - <span data-ttu-id="54e8b-120">Vaya al \*\*\*\* > **Panel**de administración de amenazas.</span><span class="sxs-lookup"><span data-stu-id="54e8b-120">Go to **Threat management** > **Dashboard**.</span></span> <span data-ttu-id="54e8b-121">Esto le llevará al [Panel de seguridad](security-dashboard.md).</span><span class="sxs-lookup"><span data-stu-id="54e8b-121">This takes you to the [Security Dashboard](security-dashboard.md).</span></span> <span data-ttu-id="54e8b-122">Los widgets de AIR aparecen en la parte superior del [Panel de seguridad](security-dashboard.md).</span><span class="sxs-lookup"><span data-stu-id="54e8b-122">Your AIR widgets appear across the top of the [Security Dashboard](security-dashboard.md).</span></span> <span data-ttu-id="54e8b-123">Seleccione un widget, como un **Resumen de investigaciones**.</span><span class="sxs-lookup"><span data-stu-id="54e8b-123">Select a widget, such as **Investigations summary**.</span></span>

    - <span data-ttu-id="54e8b-124">Vaya a \*\*\*\* > **investigaciones**de administración de amenazas.</span><span class="sxs-lookup"><span data-stu-id="54e8b-124">Go to **Threat management** > **Investigations**.</span></span> 

    <span data-ttu-id="54e8b-125">Cualquiera de estos métodos le lleva a una lista de investigaciones.</span><span class="sxs-lookup"><span data-stu-id="54e8b-125">Either method takes you to a list of investigations.</span></span>

    ![Página principal de investigación para AIR](media/air-maininvestigationpage.png) 

3. <span data-ttu-id="54e8b-127">En la lista de investigaciones, seleccione un elemento en la columna **ID** .</span><span class="sxs-lookup"><span data-stu-id="54e8b-127">In the list of investigations, select an item in the **ID** column.</span></span> <span data-ttu-id="54e8b-128">Se abrirá la página Detalles de la investigación, comenzando con el gráfico de investigación.</span><span class="sxs-lookup"><span data-stu-id="54e8b-128">This opens investigation details page, starting with the investigation graph.</span></span>

    ![Página de gráfico de investigación de aire](media/air-investigationgraphpage.png)

4. <span data-ttu-id="54e8b-130">Use las distintas pestañas para obtener más información sobre la investigación.</span><span class="sxs-lookup"><span data-stu-id="54e8b-130">Use the various tabs to learn more about the investigation.</span></span>

## <a name="review-and-approve-actions"></a><span data-ttu-id="54e8b-131">Revisión y aprobación de acciones</span><span class="sxs-lookup"><span data-stu-id="54e8b-131">Review and approve actions</span></span>

<span data-ttu-id="54e8b-132">En Office 365, las investigaciones automatizadas suelen dar como resultado una o varias acciones recomendadas.</span><span class="sxs-lookup"><span data-stu-id="54e8b-132">In Office 365, automated investigations typically result in one or more recommended actions.</span></span> <span data-ttu-id="54e8b-133">Sin embargo, no se lleva a cabo ninguna acción hasta que la aprueba el equipo de operaciones de seguridad.</span><span class="sxs-lookup"><span data-stu-id="54e8b-133">However, no actions are taken until they are approved by your security operations team.</span></span> <span data-ttu-id="54e8b-134">Use el siguiente procedimiento para revisar y aprobar acciones.</span><span class="sxs-lookup"><span data-stu-id="54e8b-134">Use the following procedure to review and approve actions.</span></span>

1. <span data-ttu-id="54e8b-135">Como administrador global de Office 365, administrador de seguridad o lector de seguridad, vaya [https://protection.office.com](https://protection.office.com) a e inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="54e8b-135">As an Office 365 global administrator, security administrator, or security reader, go to [https://protection.office.com](https://protection.office.com) and sign in.</span></span> 

2. <span data-ttu-id="54e8b-136">Vaya a \*\*\*\* > **investigaciones**de administración de amenazas.</span><span class="sxs-lookup"><span data-stu-id="54e8b-136">Go to **Threat management** > **Investigations**.</span></span>

3. <span data-ttu-id="54e8b-137">En la lista de investigaciones, seleccione un elemento en la columna **ID** .</span><span class="sxs-lookup"><span data-stu-id="54e8b-137">In the list of investigations, select an item in the **ID** column.</span></span> 

3. <span data-ttu-id="54e8b-138">En la vista detalles de la investigación, seleccione la ficha **acciones** . Aquí se enumeran las acciones pendientes de aprobación.</span><span class="sxs-lookup"><span data-stu-id="54e8b-138">On the investigation details view, select the **Actions** tab. Any actions that are pending approval are listed here.</span></span>

4. <span data-ttu-id="54e8b-139">Seleccione un elemento de la lista.</span><span class="sxs-lookup"><span data-stu-id="54e8b-139">Select an item in the list.</span></span>

5. <span data-ttu-id="54e8b-140">Seleccione **aprobar** para realizar la acción recomendada (o **rechazar** para cerrar la investigación sin emprender ninguna acción).</span><span class="sxs-lookup"><span data-stu-id="54e8b-140">Select **Approve** to take the recommended action (or **Reject** to close the investigation without taking action).</span></span>

## <a name="view-details-about-an-alert-related-to-an-investigation"></a><span data-ttu-id="54e8b-141">Ver los detalles de una alerta relacionada con una investigación</span><span class="sxs-lookup"><span data-stu-id="54e8b-141">View details about an alert related to an investigation</span></span>

<span data-ttu-id="54e8b-142">Ciertos tipos de alertas desencadenan la investigación automática en Office 365.</span><span class="sxs-lookup"><span data-stu-id="54e8b-142">Certain kinds of alerts trigger automated investigation in Office 365.</span></span> <span data-ttu-id="54e8b-143">Para obtener más información, vea [alertas](automated-investigation-response-office.md#alerts).</span><span class="sxs-lookup"><span data-stu-id="54e8b-143">To learn more, see [Alerts](automated-investigation-response-office.md#alerts).</span></span> <span data-ttu-id="54e8b-144">Use el siguiente procedimiento para ver los detalles de una alerta asociada a una investigación automatizada.</span><span class="sxs-lookup"><span data-stu-id="54e8b-144">Use the following procedure to view details about an alert that is associated with an automated investigation.</span></span>

1. <span data-ttu-id="54e8b-145">Como administrador global de Office 365, administrador de seguridad o lector de seguridad, vaya [https://protection.office.com](https://protection.office.com) a e inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="54e8b-145">As an Office 365 global administrator, security administrator, or security reader, go to [https://protection.office.com](https://protection.office.com) and sign in.</span></span> <span data-ttu-id="54e8b-146">Esto le llevará al centro de seguridad & cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="54e8b-146">This takes you to the the Security & Compliance Center.</span></span>

2. <span data-ttu-id="54e8b-147">Vaya a \*\*\*\* > **investigaciones**de administración de amenazas.</span><span class="sxs-lookup"><span data-stu-id="54e8b-147">Go to **Threat management** > **Investigations**.</span></span>

3. <span data-ttu-id="54e8b-148">En la lista de investigaciones, seleccione un elemento en la columna **ID** .</span><span class="sxs-lookup"><span data-stu-id="54e8b-148">In the list of investigations, select an item in the **ID** column.</span></span> 

4. <span data-ttu-id="54e8b-149">Con los detalles de una investigación abierta, seleccione la pestaña **alertas** . Aquí se enumeran las alertas que desencadenaron la investigación.</span><span class="sxs-lookup"><span data-stu-id="54e8b-149">With details of an investigation open, select the **Alerts** tab. Any alerts that triggered the investigation are listed here.</span></span>

5. <span data-ttu-id="54e8b-150">Seleccione un elemento de la lista.</span><span class="sxs-lookup"><span data-stu-id="54e8b-150">Select an item in the list.</span></span> <span data-ttu-id="54e8b-151">Se abre un control flotante, con detalles sobre la alerta y vínculos a acciones e información adicionales.</span><span class="sxs-lookup"><span data-stu-id="54e8b-151">A flyout opens, with details about the alert and links to additional information and actions.</span></span>

6. <span data-ttu-id="54e8b-152">Revise la información en el control flotante y, en función de la alerta en particular, realice una acción, como **resolver**, **suprimir**o **notificar a los usuarios**.</span><span class="sxs-lookup"><span data-stu-id="54e8b-152">Review the information on the flyout, and, depending on the particular alert, take an action, such as **Resolve**, **Suppress**, or **Notify users**.</span></span> 

    - <span data-ttu-id="54e8b-153">**Resolve** equivale a cerrar una alerta</span><span class="sxs-lookup"><span data-stu-id="54e8b-153">**Resolve** is equivalent to closing an alert</span></span>
    
    - <span data-ttu-id="54e8b-154">**Suprimir** hace que una directiva no desencadene alertas durante un período de tiempo especificado</span><span class="sxs-lookup"><span data-stu-id="54e8b-154">**Suppress** causes a policy to not trigger alerts for a specified period of time</span></span>
    
    - <span data-ttu-id="54e8b-155">**Notify users** inicia un correo electrónico con las direcciones de correo electrónico de los usuarios que ya se han especificado y permite que el equipo de operaciones de seguridad escriba un mensaje para esos usuarios.</span><span class="sxs-lookup"><span data-stu-id="54e8b-155">**Notify users** starts an email with users' email addresses already entered, and enables your security operations team to type a message to those users.</span></span> <span data-ttu-id="54e8b-156">(Es similar a enviar un mensaje a los destinatarios mediante el [Explorador de amenazas](threat-explorer.md)).</span><span class="sxs-lookup"><span data-stu-id="54e8b-156">(This is similar to sending a message to recipients using [Threat Explorer](threat-explorer.md).)</span></span>  

## <a name="use-the-office-365-management-activity-api-for-custom-or-third-party-reporting-solutions"></a><span data-ttu-id="54e8b-157">Usar la API de actividad de administración de Office 365 para soluciones de informes personalizadas o de terceros</span><span class="sxs-lookup"><span data-stu-id="54e8b-157">Use the Office 365 Management Activity API for custom or third-party reporting solutions</span></span>

<span data-ttu-id="54e8b-158">Si su organización usa una solución de informes personalizada o de terceros, puede ver información sobre las investigaciones automatizadas en esa solución mediante la API de actividad de administración 365 de Office.</span><span class="sxs-lookup"><span data-stu-id="54e8b-158">If your organization is using a custom or third-party reporting solution, you can view information about automated investigations in that solution by using the Office 365 Management Activity API.</span></span>

<span data-ttu-id="54e8b-159">Use los siguientes recursos para configurar esto:</span><span class="sxs-lookup"><span data-stu-id="54e8b-159">Use the following resources to set this up:</span></span>

|<span data-ttu-id="54e8b-160">Recurso</span><span class="sxs-lookup"><span data-stu-id="54e8b-160">Resource</span></span>  |<span data-ttu-id="54e8b-161">Descripción</span><span class="sxs-lookup"><span data-stu-id="54e8b-161">Description</span></span>  |
|---------|---------|
|[<span data-ttu-id="54e8b-162">Información general de las API de administración de Office 365</span><span class="sxs-lookup"><span data-stu-id="54e8b-162">Office 365 Management APIs overview</span></span>](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview)     |<span data-ttu-id="54e8b-163">La API de actividad de administración de Office 365 proporciona información sobre diversas acciones y eventos de usuario, administrador, sistema y directiva de los registros de actividad de Office 365 y Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="54e8b-163">The Office 365 Management Activity API provides information about various user, admin, system, and policy actions and events from Office 365 and Azure Active Directory activity logs.</span></span>         |
|[<span data-ttu-id="54e8b-164">Introducción a las API de administración de Office 365</span><span class="sxs-lookup"><span data-stu-id="54e8b-164">Get started with Office 365 Management APIs</span></span>](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis)     |<span data-ttu-id="54e8b-165">La API de administración 365 de Office usa Azure AD para proporcionar servicios de autenticación para que la aplicación tenga acceso a los datos de Office 365.</span><span class="sxs-lookup"><span data-stu-id="54e8b-165">The Office 365 Management API uses Azure AD to provide authentication services for your application to access Office 365 data.</span></span> <span data-ttu-id="54e8b-166">Siga los pasos de este artículo para configurarlo.</span><span class="sxs-lookup"><span data-stu-id="54e8b-166">Follow the steps in this article to set this up.</span></span>          |
|[<span data-ttu-id="54e8b-167">Referencia de las API de Actividad de administración de Office 365</span><span class="sxs-lookup"><span data-stu-id="54e8b-167">Office 365 Management Activity API reference</span></span>](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)     |<span data-ttu-id="54e8b-168">Puede usar la API de actividad de administración de Office 365 para recuperar información sobre las acciones y eventos de usuario, administrador, sistema y Directiva de los registros de actividad de Office 365 y Azure AD.</span><span class="sxs-lookup"><span data-stu-id="54e8b-168">You can use the Office 365 Management Activity API to retrieve information about user, admin, system, and policy actions and events from Office 365 and Azure AD activity logs.</span></span> <span data-ttu-id="54e8b-169">Lea este artículo para obtener más información sobre cómo funciona.</span><span class="sxs-lookup"><span data-stu-id="54e8b-169">Read this article to learn more about how this works.</span></span>        |
|[<span data-ttu-id="54e8b-170">Esquema de la API de Actividad de administración de Office 365</span><span class="sxs-lookup"><span data-stu-id="54e8b-170">Office 365 Management Activity API schema</span></span>](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema)     |<span data-ttu-id="54e8b-171">Obtenga información general sobre el [esquema común](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#common-schema) y el [esquema de investigación y respuesta de ATP y la investigación de amenazas de Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) para obtener información sobre los tipos de datos específicos disponibles a través de la API de actividad de administración de Office 365.</span><span class="sxs-lookup"><span data-stu-id="54e8b-171">Get an overview of the [Common schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#common-schema) and the [Office 365 ATP and threat investigation and response schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) to learn about specific kinds of data available through the Office 365 Management Activity API.</span></span>         |

## <a name="next-steps"></a><span data-ttu-id="54e8b-172">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="54e8b-172">Next steps</span></span>

[<span data-ttu-id="54e8b-173">Más información acerca de las alertas</span><span class="sxs-lookup"><span data-stu-id="54e8b-173">Learn more about alerts</span></span>](alert-policies.md)

[<span data-ttu-id="54e8b-174">Buscar y investigar manualmente el correo electrónico malintencionado que se entregó en Office 365</span><span class="sxs-lookup"><span data-stu-id="54e8b-174">Manually find and investigate malicious email that was delivered in Office 365</span></span>](investigate-malicious-email-that-was-delivered.md)

[<span data-ttu-id="54e8b-175">Obtener información sobre AIR en ATP de Microsoft defender</span><span class="sxs-lookup"><span data-stu-id="54e8b-175">Learn about AIR in Microsoft Defender ATP</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)

[<span data-ttu-id="54e8b-176">Visite el plan de desarrollo de Microsoft 365 para ver lo que estará próximamente y que se implementará</span><span class="sxs-lookup"><span data-stu-id="54e8b-176">Visit the Microsoft 365 Roadmap to see what's coming soon and rolling out</span></span>](https://www.microsoft.com/microsoft-365/roadmap?filters=)