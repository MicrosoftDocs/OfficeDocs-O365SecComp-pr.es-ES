---
title: Integración de SIEM con Office 365 Threat Intelligence y protección contra amenazas avanzada
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: ITPro
ms.topic: overview
ms.service: o365-administration
localization_priority: None
search.appverid:
- MET150
- MOE150
ms.assetid: eb56b69b-3170-4086-82cf-ba40a530fa1b
description: Integre el servidor SIEM de su organización con Office 365 Threat Intelligence y la protección contra amenazas avanzada con la API de administración de actividad de Office 365.
ms.openlocfilehash: 854f763b72dfac1a5dc1442b1d9d123ed5439257
ms.sourcegitcommit: 8679937354c1d8870ecd41519a59d2d7468c23c4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2019
ms.locfileid: "30087249"
---
# <a name="siem-integration-with-office-365-threat-intelligence-and-advanced-threat-protection"></a><span data-ttu-id="6f41d-103">Integración de SIEM con Office 365 Threat Intelligence y protección contra amenazas avanzada</span><span class="sxs-lookup"><span data-stu-id="6f41d-103">SIEM integration with Office 365 Threat Intelligence and Advanced Threat Protection</span></span>

<span data-ttu-id="6f41d-p101">Si su organización usa un servidor de incidentes de seguridad y de administración de eventos (SIEM), puede integrar la inteligencia sobre amenazas de Office 365 y la protección contra amenazas avanzada con el servidor de SIEM. La integración de SIEM permite ver información, como malware detectada por Office 365 Advanced Protection y Threat Intelligence, en los informes del servidor de SIEM. Para configurar la integración de SIEM, use la [API de administración de actividad de Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference).</span><span class="sxs-lookup"><span data-stu-id="6f41d-p101">If your organization is using a security incident and event management (SIEM) server, you can integrate Office 365 Threat Intelligence and Advanced Threat Protection with your SIEM server. SIEM integration enables you to view information, such as malware detected by Office 365 Advanced Protection and Threat Intelligence, in your SIEM server reports. To set up SIEM integration, you use the [Office 365 Activity Management API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference).</span></span> 

<span data-ttu-id="6f41d-p102">La API de administración de actividad de Office 365 recupera información sobre acciones y eventos de usuario, administrador, sistema y Directiva de los registros de actividad de Office 365 y Azure Active Directory de la organización. El [esquema de protección contra amenazas avanzada de Office 365 y de inteligencia](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-intelligence-schema) sobre amenazas funciona con inteligencia de amenazas o protección contra amenazas avanzada, por lo que si su organización tiene protección contra amenazas avanzada pero no ofrece inteligencia de amenazas (o viceversa), puede Siga usando esa misma API para la integración del servidor de SIEM.</span><span class="sxs-lookup"><span data-stu-id="6f41d-p102">The Office 365 Activity Management API retrieves information about user, admin, system, and policy actions and events from your organization's Office 365 and Azure Active Directory activity logs. The [Office 365 Advanced Threat Protection and Threat Intelligence schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-intelligence-schema) works with Threat Intelligence and/or Advanced Threat Protection, so if your organization has Advanced Threat Protection but not Threat Intelligence (or vice versa), you can still use that same API for your SIEM server integration.</span></span> 

<span data-ttu-id="6f41d-p103">El servidor de SIEM u otro sistema similar debe sondear la **auditoría. general** Workload para acceder a los eventos de detección. Para obtener más información, vea Introducción [a las API de administración de Office 365](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis).</span><span class="sxs-lookup"><span data-stu-id="6f41d-p103">The SIEM server or other similar system should poll the **audit.general** workload to access detection events. To learn more see [Get started with Office 365 Management APIs](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis).</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="6f41d-111">Debe ser un administrador global de Office 365 o tener asignado el rol de administrador de seguridad para el centro de seguridad & cumplimiento para configurar la integración de SIEM con Office 365 protección contra amenazas avanzada.</span><span class="sxs-lookup"><span data-stu-id="6f41d-111">You must be an Office 365 global administrator or have the security administrator role assigned for the Security & Compliance Center to set up SIEM integration with Office 365 Advanced Threat Protection.</span></span><br/><span data-ttu-id="6f41d-p104">El registro de auditoría debe estar activado para su entorno de Office 365. Para obtener ayuda, consulte [activar o desactivar la búsqueda de registros de auditoría de Office 365](turn-audit-log-search-on-or-off.md).</span><span class="sxs-lookup"><span data-stu-id="6f41d-p104">Audit logging must be turned on for your Office 365 environment. To get help with this, see [Turn Office 365 audit log search on or off](turn-audit-log-search-on-or-off.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="6f41d-114">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="6f41d-114">Related topics</span></span>

[<span data-ttu-id="6f41d-115">Inteligencia sobre amenazas de Office 365</span><span class="sxs-lookup"><span data-stu-id="6f41d-115">Office 365 Threat Intelligence</span></span>](office-365-ti.md)

[<span data-ttu-id="6f41d-116">Protección contra amenazas avanzada de Office 365</span><span class="sxs-lookup"><span data-stu-id="6f41d-116">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md)

[<span data-ttu-id="6f41d-117">Informes inteligentes y opiniones del centro de seguridad &amp; y cumplimiento de Office 365</span><span class="sxs-lookup"><span data-stu-id="6f41d-117">Smart reports and insights in the Office 365 Security &amp; Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)
  
[<span data-ttu-id="6f41d-118">Permisos en el centro de seguridad &amp; y cumplimiento de Office 365</span><span class="sxs-lookup"><span data-stu-id="6f41d-118">Permissions in the Office 365 Security &amp; Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)
  

