---
title: Investigar y responder automáticamente a las amenazas en Office 365
keywords: AIR, autoIR, ATP, automatizado, investigación, respuesta, corrección, amenazas, avanzadas, amenazas, protección
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 09/04/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
description: Empiece a usar la investigación automatizada y las capacidades de respuesta en Office 365 Advanced Threat Protection Plan 2.
ms.openlocfilehash: 2c64ea936170524811839db7c593d67bfe11a928
ms.sourcegitcommit: 4a2bde56178609e75c1ad7ecad2db5e049fc0c45
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2019
ms.locfileid: "36762033"
---
# <a name="automatically-investigate-and-respond-to-threats-in-office-365"></a><span data-ttu-id="a0945-104">Investigar y responder automáticamente a las amenazas en Office 365</span><span class="sxs-lookup"><span data-stu-id="a0945-104">Automatically investigate and respond to threats in Office 365</span></span>

## <a name="overview"></a><span data-ttu-id="a0945-105">Información general</span><span class="sxs-lookup"><span data-stu-id="a0945-105">Overview</span></span>

<span data-ttu-id="a0945-106">[Protección contra amenazas avanzada de Office 365](office-365-atp.md) El plan 2 incluye capacidades de investigación y respuesta automatizadas (AIR) que pueden salvar el tiempo y el esfuerzo del equipo de operaciones de seguridad para tratar las alertas y las amenazas.</span><span class="sxs-lookup"><span data-stu-id="a0945-106">[Office 365 Advanced Threat Protection](office-365-atp.md) Plan 2 includes automated investigation and response (AIR) capabilities that can save your security operations team time and effort in dealing with alerts and threats.</span></span> <span data-ttu-id="a0945-107">Lea este artículo para empezar a usar las funcionalidades de AIR en Office 365.</span><span class="sxs-lookup"><span data-stu-id="a0945-107">Read this article to get started using AIR capabilities in Office 365.</span></span> <span data-ttu-id="a0945-108">Para obtener más información sobre cómo funciona AIR, consulte [Automated Investigation and Response (Air) con Office 365](automated-investigation-response-office.md).</span><span class="sxs-lookup"><span data-stu-id="a0945-108">To learn more about how AIR works, see [Automated Investigation and Response (AIR) with Office 365](automated-investigation-response-office.md).</span></span>

<span data-ttu-id="a0945-109">Con AIR, cuando se desencadenan determinadas alertas, se inician una o más guías de seguridad y comienza la investigación automatizada.</span><span class="sxs-lookup"><span data-stu-id="a0945-109">With AIR, when certain alerts are triggered, one or more security playbooks initiate, and automated investigation begins.</span></span> <span data-ttu-id="a0945-110">Durante y después de un proceso de investigación automatizado, los administradores y el equipo de operaciones de seguridad pueden:</span><span class="sxs-lookup"><span data-stu-id="a0945-110">During and after an automated investigation process, your administrators and security operations team can:</span></span>

- [<span data-ttu-id="a0945-111">Ver los detalles de una investigación</span><span class="sxs-lookup"><span data-stu-id="a0945-111">View the details of an investigation</span></span>](#view-details-of-an-investigation)

- [<span data-ttu-id="a0945-112">Revisión y aprobación de acciones como resultado de una investigación</span><span class="sxs-lookup"><span data-stu-id="a0945-112">Review and approve actions as a result of an investigation</span></span>](#review-and-approve-actions) 

- [<span data-ttu-id="a0945-113">Ver los detalles de una alerta relacionada con una investigación</span><span class="sxs-lookup"><span data-stu-id="a0945-113">View details about an alert related to an investigation</span></span>](#view-details-about-an-alert-related-to-an-investigation)

> [!NOTE]
> <span data-ttu-id="a0945-114">Debe ser administrador global, administrador de seguridad, operador de seguridad o lector de seguridad para realizar las tareas descritas en este artículo.</span><span class="sxs-lookup"><span data-stu-id="a0945-114">You must be a global administrator, security administrator, security operator, or security reader to perform the tasks described in this article.</span></span> <span data-ttu-id="a0945-115">Para obtener más información, consulte [Microsoft 365 Security Center: roles y permisos](https://docs.microsoft.com/office365/securitycompliance/microsoft-security-and-compliance#required-licenses-and-permissions).</span><span class="sxs-lookup"><span data-stu-id="a0945-115">To learn more, see [Microsoft 365 security center: roles and permissions](https://docs.microsoft.com/office365/securitycompliance/microsoft-security-and-compliance#required-licenses-and-permissions).</span></span>

## <a name="view-details-of-an-investigation"></a><span data-ttu-id="a0945-116">Ver los detalles de una investigación</span><span class="sxs-lookup"><span data-stu-id="a0945-116">View details of an investigation</span></span>

1. <span data-ttu-id="a0945-117">Como administrador global de Office 365, administrador de seguridad o lector de seguridad, vaya [https://protection.office.com](https://protection.office.com) a e inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="a0945-117">As an Office 365 global administrator, security administrator, or security reader, go to [https://protection.office.com](https://protection.office.com) and sign in.</span></span> <span data-ttu-id="a0945-118">Esto le llevará al centro de seguridad & cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="a0945-118">This takes you to the the Security & Compliance Center.</span></span>

2. <span data-ttu-id="a0945-119">Realice una de las acciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="a0945-119">Do one of the following:</span></span>

    - <span data-ttu-id="a0945-120">Vaya al \*\*\*\* > **Panel**de administración de amenazas.</span><span class="sxs-lookup"><span data-stu-id="a0945-120">Go to **Threat management** > **Dashboard**.</span></span> <span data-ttu-id="a0945-121">Esto le llevará al [Panel de seguridad](security-dashboard.md).</span><span class="sxs-lookup"><span data-stu-id="a0945-121">This takes you to the [Security Dashboard](security-dashboard.md).</span></span> <span data-ttu-id="a0945-122">Los widgets de AIR aparecen en la parte superior del [Panel de seguridad](security-dashboard.md).</span><span class="sxs-lookup"><span data-stu-id="a0945-122">Your AIR widgets appear across the top of the [Security Dashboard](security-dashboard.md).</span></span> <span data-ttu-id="a0945-123">Seleccione un widget, como un **Resumen de investigaciones**.</span><span class="sxs-lookup"><span data-stu-id="a0945-123">Select a widget, such as **Investigations summary**.</span></span>

    - <span data-ttu-id="a0945-124">Vaya a \*\*\*\* > **investigaciones**de administración de amenazas.</span><span class="sxs-lookup"><span data-stu-id="a0945-124">Go to **Threat management** > **Investigations**.</span></span> 

    <span data-ttu-id="a0945-125">Cualquiera de estos métodos le lleva a una lista de investigaciones.</span><span class="sxs-lookup"><span data-stu-id="a0945-125">Either method takes you to a list of investigations.</span></span>

    ![Página principal de investigación para AIR](media/air-maininvestigationpage.png) 

3. <span data-ttu-id="a0945-127">En la lista de investigaciones, seleccione un elemento en la columna **ID** .</span><span class="sxs-lookup"><span data-stu-id="a0945-127">In the list of investigations, select an item in the **ID** column.</span></span> <span data-ttu-id="a0945-128">Se abrirá la página Detalles de la investigación, comenzando con el gráfico de investigación.</span><span class="sxs-lookup"><span data-stu-id="a0945-128">This opens investigation details page, starting with the investigation graph.</span></span>

    ![Página de gráfico de investigación de aire](media/air-investigationgraphpage.png)

4. <span data-ttu-id="a0945-130">Use las distintas pestañas para obtener más información sobre la investigación.</span><span class="sxs-lookup"><span data-stu-id="a0945-130">Use the various tabs to learn more about the investigation.</span></span>

## <a name="review-and-approve-actions"></a><span data-ttu-id="a0945-131">Revisión y aprobación de acciones</span><span class="sxs-lookup"><span data-stu-id="a0945-131">Review and approve actions</span></span>

<span data-ttu-id="a0945-132">En Office 365, las investigaciones automatizadas suelen dar como resultado una o varias acciones recomendadas.</span><span class="sxs-lookup"><span data-stu-id="a0945-132">In Office 365, automated investigations typically result in one or more recommended actions.</span></span> <span data-ttu-id="a0945-133">Sin embargo, no se lleva a cabo ninguna acción hasta que la aprueba el equipo de operaciones de seguridad.</span><span class="sxs-lookup"><span data-stu-id="a0945-133">However, no actions are taken until they are approved by your security operations team.</span></span> <span data-ttu-id="a0945-134">Use el siguiente procedimiento para revisar y aprobar acciones.</span><span class="sxs-lookup"><span data-stu-id="a0945-134">Use the following procedure to review and approve actions.</span></span>

1. <span data-ttu-id="a0945-135">Como administrador global de Office 365, administrador de seguridad o lector de seguridad, vaya [https://protection.office.com](https://protection.office.com) a e inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="a0945-135">As an Office 365 global administrator, security administrator, or security reader, go to [https://protection.office.com](https://protection.office.com) and sign in.</span></span> 

2. <span data-ttu-id="a0945-136">Vaya a \*\*\*\* > **investigaciones**de administración de amenazas.</span><span class="sxs-lookup"><span data-stu-id="a0945-136">Go to **Threat management** > **Investigations**.</span></span>

3. <span data-ttu-id="a0945-137">En la lista de investigaciones, seleccione un elemento en la columna **ID** .</span><span class="sxs-lookup"><span data-stu-id="a0945-137">In the list of investigations, select an item in the **ID** column.</span></span> 

3. <span data-ttu-id="a0945-138">En la vista detalles de la investigación, seleccione la ficha **acciones** . Aquí se enumeran las acciones pendientes de aprobación.</span><span class="sxs-lookup"><span data-stu-id="a0945-138">On the investigation details view, select the **Actions** tab. Any actions that are pending approval are listed here.</span></span>

4. <span data-ttu-id="a0945-139">Seleccione un elemento de la lista.</span><span class="sxs-lookup"><span data-stu-id="a0945-139">Select an item in the list.</span></span>

5. <span data-ttu-id="a0945-140">Seleccione **aprobar** para realizar la acción recomendada (o **rechazar** para cerrar la investigación sin emprender ninguna acción).</span><span class="sxs-lookup"><span data-stu-id="a0945-140">Select **Approve** to take the recommended action (or **Reject** to close the investigation without taking action).</span></span>

## <a name="view-details-about-an-alert-related-to-an-investigation"></a><span data-ttu-id="a0945-141">Ver los detalles de una alerta relacionada con una investigación</span><span class="sxs-lookup"><span data-stu-id="a0945-141">View details about an alert related to an investigation</span></span>

<span data-ttu-id="a0945-142">Ciertos tipos de alertas desencadenan la investigación automática en Office 365.</span><span class="sxs-lookup"><span data-stu-id="a0945-142">Certain kinds of alerts trigger automated investigation in Office 365.</span></span> <span data-ttu-id="a0945-143">Para obtener más información, vea [alertas](automated-investigation-response-office.md#alerts).</span><span class="sxs-lookup"><span data-stu-id="a0945-143">To learn more, see [Alerts](automated-investigation-response-office.md#alerts).</span></span> <span data-ttu-id="a0945-144">Use el siguiente procedimiento para ver los detalles de una alerta asociada a una investigación automatizada.</span><span class="sxs-lookup"><span data-stu-id="a0945-144">Use the following procedure to view details about an alert that is associated with an automated investigation.</span></span>

1. <span data-ttu-id="a0945-145">Como administrador global de Office 365, administrador de seguridad o lector de seguridad, vaya [https://protection.office.com](https://protection.office.com) a e inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="a0945-145">As an Office 365 global administrator, security administrator, or security reader, go to [https://protection.office.com](https://protection.office.com) and sign in.</span></span> <span data-ttu-id="a0945-146">Esto le llevará al centro de seguridad & cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="a0945-146">This takes you to the the Security & Compliance Center.</span></span>

2. <span data-ttu-id="a0945-147">Vaya a \*\*\*\* > **investigaciones**de administración de amenazas.</span><span class="sxs-lookup"><span data-stu-id="a0945-147">Go to **Threat management** > **Investigations**.</span></span>

3. <span data-ttu-id="a0945-148">En la lista de investigaciones, seleccione un elemento en la columna **ID** .</span><span class="sxs-lookup"><span data-stu-id="a0945-148">In the list of investigations, select an item in the **ID** column.</span></span> 

4. <span data-ttu-id="a0945-149">Con los detalles de una investigación abierta, seleccione la pestaña **alertas** . Aquí se enumeran las alertas que desencadenaron la investigación.</span><span class="sxs-lookup"><span data-stu-id="a0945-149">With details of an investigation open, select the **Alerts** tab. Any alerts that triggered the investigation are listed here.</span></span>

5. <span data-ttu-id="a0945-150">Seleccione un elemento de la lista.</span><span class="sxs-lookup"><span data-stu-id="a0945-150">Select an item in the list.</span></span> <span data-ttu-id="a0945-151">Se abre un control flotante, con detalles sobre la alerta y vínculos a acciones e información adicionales.</span><span class="sxs-lookup"><span data-stu-id="a0945-151">A flyout opens, with details about the alert and links to additional information and actions.</span></span>

6. <span data-ttu-id="a0945-152">Revise la información en el control flotante y, en función de la alerta en particular, realice una acción, como **resolver**, **suprimir**o **notificar a los usuarios**.</span><span class="sxs-lookup"><span data-stu-id="a0945-152">Review the information on the flyout, and, depending on the particular alert, take an action, such as **Resolve**, **Suppress**, or **Notify users**.</span></span> 

## <a name="use-the-office-365-management-activity-api-for-custom-or-third-party-reporting-solutions"></a><span data-ttu-id="a0945-153">Usar la API de actividad de administración de Office 365 para soluciones de informes personalizadas o de terceros</span><span class="sxs-lookup"><span data-stu-id="a0945-153">Use the Office 365 Management Activity API for custom or third-party reporting solutions</span></span>

<span data-ttu-id="a0945-154">Si su organización usa una solución de informes personalizada o una solución de informes de terceros, puede ver información sobre las investigaciones automatizadas en esa solución mediante el uso de la API de actividad de administración 365 de Office.</span><span class="sxs-lookup"><span data-stu-id="a0945-154">If your organization is using a custom reporting solution, or a third-party reporting solution, you can view information about automated investigations in that solution by using the Office 365 Management Activity API.</span></span>

<span data-ttu-id="a0945-155">Use los siguientes recursos para configurar esto:</span><span class="sxs-lookup"><span data-stu-id="a0945-155">Use the following resources to set this up:</span></span>

|<span data-ttu-id="a0945-156">Recurso</span><span class="sxs-lookup"><span data-stu-id="a0945-156">Resource</span></span>  |<span data-ttu-id="a0945-157">Descripción</span><span class="sxs-lookup"><span data-stu-id="a0945-157">Description</span></span>  |
|---------|---------|
|[<span data-ttu-id="a0945-158">Información general de las API de administración de Office 365</span><span class="sxs-lookup"><span data-stu-id="a0945-158">Office 365 Management APIs overview</span></span>](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview)     |<span data-ttu-id="a0945-159">La API de actividad de administración de Office 365 proporciona información sobre diversas acciones y eventos de usuario, administrador, sistema y directiva de los registros de actividad de Office 365 y Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="a0945-159">The Office 365 Management Activity API provides information about various user, admin, system, and policy actions and events from Office 365 and Azure Active Directory activity logs.</span></span>         |
|[<span data-ttu-id="a0945-160">Introducción a las API de administración de Office 365</span><span class="sxs-lookup"><span data-stu-id="a0945-160">Get started with Office 365 Management APIs</span></span>](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis)     |<span data-ttu-id="a0945-161">La API de administración 365 de Office usa Azure AD para proporcionar servicios de autenticación para que la aplicación tenga acceso a los datos de Office 365.</span><span class="sxs-lookup"><span data-stu-id="a0945-161">The Office 365 Management API uses Azure AD to provide authentication services for your application to access Office 365 data.</span></span> <span data-ttu-id="a0945-162">Siga los pasos de este artículo para configurarlo.</span><span class="sxs-lookup"><span data-stu-id="a0945-162">Follow the steps in this article to set this up.</span></span>          |
|[<span data-ttu-id="a0945-163">Referencia de las API de Actividad de administración de Office 365</span><span class="sxs-lookup"><span data-stu-id="a0945-163">Office 365 Management Activity API reference</span></span>](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)     |<span data-ttu-id="a0945-164">Puede usar la API de actividad de administración de Office 365 para recuperar información sobre las acciones y eventos de usuario, administrador, sistema y Directiva de los registros de actividad de Office 365 y Azure AD.</span><span class="sxs-lookup"><span data-stu-id="a0945-164">You can use the Office 365 Management Activity API to retrieve information about user, admin, system, and policy actions and events from Office 365 and Azure AD activity logs.</span></span> <span data-ttu-id="a0945-165">Lea este artículo para obtener más información sobre cómo funciona.</span><span class="sxs-lookup"><span data-stu-id="a0945-165">Read this article to learn more about how this works.</span></span>        |
|[<span data-ttu-id="a0945-166">Esquema de la API de Actividad de administración de Office 365</span><span class="sxs-lookup"><span data-stu-id="a0945-166">Office 365 Management Activity API schema</span></span>](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema)     |<span data-ttu-id="a0945-167">Obtenga información general sobre el [esquema común](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#common-schema) y el [esquema de investigación y respuesta de ATP y la investigación de amenazas de Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) para obtener información sobre los tipos de datos específicos disponibles a través de la API de actividad de administración de Office 365.</span><span class="sxs-lookup"><span data-stu-id="a0945-167">Get an overview of the [Common schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#common-schema) and the [Office 365 ATP and threat investigation and response schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) to learn about specific kinds of data available through the Office 365 Management Activity API.</span></span>         |

## <a name="next-steps"></a><span data-ttu-id="a0945-168">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="a0945-168">Next steps</span></span>

[<span data-ttu-id="a0945-169">Más información acerca de las alertas</span><span class="sxs-lookup"><span data-stu-id="a0945-169">Learn more about alerts</span></span>](alert-policies.md)

[<span data-ttu-id="a0945-170">Buscar y investigar manualmente el correo electrónico malintencionado que se entregó en Office 365</span><span class="sxs-lookup"><span data-stu-id="a0945-170">Manually find and investigate malicious email that was delivered in Office 365</span></span>](investigate-malicious-email-that-was-delivered.md)

[<span data-ttu-id="a0945-171">Obtener información sobre AIR en ATP de Microsoft defender</span><span class="sxs-lookup"><span data-stu-id="a0945-171">Learn about AIR in Microsoft Defender ATP</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)

[<span data-ttu-id="a0945-172">Visite el plan de desarrollo de Microsoft 365 para ver lo que estará próximamente y que se implementará</span><span class="sxs-lookup"><span data-stu-id="a0945-172">Visit the Microsoft 365 Roadmap to see what's coming soon and rolling out</span></span>](https://www.microsoft.com/microsoft-365/roadmap?filters=)