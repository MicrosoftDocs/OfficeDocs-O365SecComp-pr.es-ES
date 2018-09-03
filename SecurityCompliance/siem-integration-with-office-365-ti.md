---
title: Integración de SIEM con información sobre amenazas de Office 365 y avanzada de protección contra amenazas
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
description: Integrar server de su organización SIEM con información sobre amenazas de Office 365 y avanzada protección contra amenazas con la API de administración de Office 365 actividad.
ms.openlocfilehash: 40c84b9d7b7ec4c9b15383e3ffbbabf839294def
ms.sourcegitcommit: e7b87fae103a858981bdbcdf7ec55afa4751ad05
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/31/2018
ms.locfileid: "23782147"
---
# <a name="siem-integration-with-office-365-threat-intelligence-and-advanced-threat-protection"></a><span data-ttu-id="2bf89-103">Integración de SIEM con información sobre amenazas de Office 365 y avanzada de protección contra amenazas</span><span class="sxs-lookup"><span data-stu-id="2bf89-103">SIEM integration with Office 365 Threat Intelligence and Advanced Threat Protection</span></span>

<span data-ttu-id="2bf89-p101">Si su organización usa un servidor de administración (SIEM) de incidentes y eventos de seguridad, puede integrar información sobre amenazas de Office 365 y avanzada de protección contra amenazas con su servidor SIEM. Integración de SIEM permite ver la información, como malware detectado por protección avanzada de Office 365 e inteligencia de amenaza, en los informes de servidor SIEM. Para configurar la integración de SIEM, use la [API de administración de Office 365 actividad](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference).</span><span class="sxs-lookup"><span data-stu-id="2bf89-p101">If your organization is using a security incident and event management (SIEM) server, you can integrate Office 365 Threat Intelligence and Advanced Threat Protection with your SIEM server. SIEM integration enables you to view information, such as malware detected by Office 365 Advanced Protection and Threat Intelligence, in your SIEM server reports. To set up SIEM integration, you use the [Office 365 Activity Management API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference).</span></span> 

<span data-ttu-id="2bf89-p102">La API de administración de Office 365 actividad recupera información sobre el usuario, administración, sistema y las acciones de directiva y eventos de Office 365 y los registros de actividad de Azure Active Directory de su organización. [Esquema de información sobre amenazas y la protección de amenaza avanzada de Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-intelligence-schema) funciona con información sobre amenazas o protección contra amenazas avanzada, por lo que si su organización tiene avanzada protección contra amenazas, pero no la inteligencia sobre amenazas (o viceversa), puede aún puede usar esa misma API para la integración del servidor de SIEM.</span><span class="sxs-lookup"><span data-stu-id="2bf89-p102">The Office 365 Activity Management API retrieves information about user, admin, system, and policy actions and events from your organization's Office 365 and Azure Active Directory activity logs. The [Office 365 Advanced Threat Protection and Threat Intelligence schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-intelligence-schema) works with Threat Intelligence and/or Advanced Threat Protection, so if your organization has Advanced Threat Protection but not Threat Intelligence (or vice versa), you can still use that same API for your SIEM server integration.</span></span> 

<span data-ttu-id="2bf89-p103">El servidor SIEM u otro sistema similar debería sondear la carga de trabajo **audit.general** a eventos de detección de acceso. Para obtener más información vea [empezar a trabajar con las API de administración de Office 365](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis).</span><span class="sxs-lookup"><span data-stu-id="2bf89-p103">The SIEM server or other similar system should poll the **audit.general** workload to access detection events. To learn more see [Get started with Office 365 Management APIs](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis).</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="2bf89-111">Debe ser un administrador global de Office 365 o tener el rol de administrador de seguridad asignado en el centro de cumplimiento y seguridad para configurar la integración de SIEM con información sobre amenazas de Office 365 y avanzada de protección contra amenazas.</span><span class="sxs-lookup"><span data-stu-id="2bf89-111">You must be an Office 365 global administrator or have the security administrator role assigned in the Security & Compliance Center to set up SIEM integration with Office 365 Threat Intelligence and Advanced Threat Protection.</span></span></br><span data-ttu-id="2bf89-p104">Registro de auditoría debe activarlo para su entorno de Office 365. Para obtener ayuda con esto, vea [activar Office 365 de búsqueda de registros de auditoría activado o desactivado](turn-audit-log-search-on-or-off.md).</span><span class="sxs-lookup"><span data-stu-id="2bf89-p104">Audit logging must be turned on for your Office 365 environment. To get help with this, see [Turn Office 365 audit log search on or off](turn-audit-log-search-on-or-off.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="2bf89-114">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="2bf89-114">Related topics</span></span>

[<span data-ttu-id="2bf89-115">Inteligencia sobre amenazas de Office 365</span><span class="sxs-lookup"><span data-stu-id="2bf89-115">Office 365 Threat Intelligence</span></span>](office-365-ti.md)

[<span data-ttu-id="2bf89-116">Protección contra amenazas avanzada de Office 365</span><span class="sxs-lookup"><span data-stu-id="2bf89-116">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md)

[<span data-ttu-id="2bf89-117">Informes y conocimientos en la seguridad de Office 365 de Smart &amp; centro de cumplimiento</span><span class="sxs-lookup"><span data-stu-id="2bf89-117">Smart reports and insights in the Office 365 Security &amp; Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)
  
[<span data-ttu-id="2bf89-118">Los permisos de la seguridad de Office 365 &amp; centro de cumplimiento</span><span class="sxs-lookup"><span data-stu-id="2bf89-118">Permissions in the Office 365 Security &amp; Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)
  

