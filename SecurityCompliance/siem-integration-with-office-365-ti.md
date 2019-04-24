---
title: Integración de SIEM con Office 365 protección contra amenazas avanzada
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
- MOE150
ms.assetid: eb56b69b-3170-4086-82cf-ba40a530fa1b
ms.date: 03/11/2019
ms.collection:
- M365-security-compliance
description: Integre el servidor de SIEM de su organización con la protección contra amenazas avanzada de Office 365 y eventos de amenazas relacionados en la API de administración de actividad de Office 365.
ms.openlocfilehash: fa9dcda0556684b748068cbe5ee848ba443d7667
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32260688"
---
# <a name="siem-integration-with-office-365-advanced-threat-protection"></a><span data-ttu-id="b8284-103">Integración de SIEM con Office 365 protección contra amenazas avanzada</span><span class="sxs-lookup"><span data-stu-id="b8284-103">SIEM integration with Office 365 Advanced Threat Protection</span></span>

<span data-ttu-id="b8284-104">Si su organización usa un servidor de incidentes de seguridad y de administración de eventos (SIEM), puede integrar la protección contra amenazas avanzada de Office 365 con el servidor de SIEM.</span><span class="sxs-lookup"><span data-stu-id="b8284-104">If your organization is using a security incident and event management (SIEM) server, you can integrate Office 365 Advanced Threat Protection with your SIEM server.</span></span> <span data-ttu-id="b8284-105">La integración de SIEM permite ver información, como malware o phish detectada por la protección avanzada de Office 365, en los informes del servidor de SIEM.</span><span class="sxs-lookup"><span data-stu-id="b8284-105">SIEM integration enables you to view information, such as malware or phish detected by Office 365 Advanced Protection, in your SIEM server reports.</span></span> <span data-ttu-id="b8284-106">Para configurar la integración de SIEM, use la [API de administración de actividad de Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference).</span><span class="sxs-lookup"><span data-stu-id="b8284-106">To set up SIEM integration, you use the [Office 365 Activity Management API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference).</span></span> 

<span data-ttu-id="b8284-107">La API de administración de actividad de Office 365 recupera información sobre acciones y eventos de usuario, administrador, sistema y Directiva de los registros de actividad de Office 365 y Azure Active Directory de la organización.</span><span class="sxs-lookup"><span data-stu-id="b8284-107">The Office 365 Activity Management API retrieves information about user, admin, system, and policy actions and events from your organization's Office 365 and Azure Active Directory activity logs.</span></span> <span data-ttu-id="b8284-108">El [esquema de protección contra amenazas avanzada de office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-intelligence-schema) funciona con la protección contra amenazas avanzada, de modo que si su organización tiene el plan 1 de la protección contra amenazas avanzada de Office 365 o bien el plan 2 u Office 365 E5, puede usar esa misma API para la integración del servidor de Siem.</span><span class="sxs-lookup"><span data-stu-id="b8284-108">The [Office 365 Advanced Threat Protection schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-intelligence-schema) works with Advanced Threat Protection, so if your organization has the Office 365 Advanced Threat Protection Plan 1 or Plan 2 or Office 365 E5, you can still use that same API for your SIEM server integration.</span></span> 

<span data-ttu-id="b8284-109">El servidor de SIEM u otro sistema similar debe sondear la **auditoría. general** Workload para acceder a los eventos de detección.</span><span class="sxs-lookup"><span data-stu-id="b8284-109">The SIEM server or other similar system should poll the **audit.general** workload to access detection events.</span></span> <span data-ttu-id="b8284-110">Para obtener más información, vea Introducción [a las API de administración de Office 365](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis).</span><span class="sxs-lookup"><span data-stu-id="b8284-110">To learn more see [Get started with Office 365 Management APIs](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis).</span></span> <span data-ttu-id="b8284-111">Además, los siguientes valores de **AuditLogRecordType** son relevantes para los eventos de ATP de Office 365:</span><span class="sxs-lookup"><span data-stu-id="b8284-111">In addition, the following values of **AuditLogRecordType** are relevant for Office 365 ATP events:</span></span>

### <a name="enum-auditlogrecordtype---type-edmint32"></a><span data-ttu-id="b8284-112">Enum: AuditLogRecordType - Tipo: Edm.Int32</span><span class="sxs-lookup"><span data-stu-id="b8284-112">Enum: AuditLogRecordType - Type: Edm.Int32</span></span>

#### <a name="auditlogrecordtype"></a><span data-ttu-id="b8284-113">AuditLogRecordType</span><span class="sxs-lookup"><span data-stu-id="b8284-113">AuditLogRecordType</span></span>

|<span data-ttu-id="b8284-114">Valor</span><span class="sxs-lookup"><span data-stu-id="b8284-114">Value</span></span>|<span data-ttu-id="b8284-115">Nombre del miembro</span><span class="sxs-lookup"><span data-stu-id="b8284-115">Member name</span></span>|<span data-ttu-id="b8284-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="b8284-116">Description</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="b8284-117">28</span><span class="sxs-lookup"><span data-stu-id="b8284-117">28</span></span>|<span data-ttu-id="b8284-118">ThreatIntelligence</span><span class="sxs-lookup"><span data-stu-id="b8284-118">ThreatIntelligence</span></span>|<span data-ttu-id="b8284-119">Eventos de suplantación de identidad y malware de Exchange Online Protection y Protección contra amenazas avanzada de Office 365.</span><span class="sxs-lookup"><span data-stu-id="b8284-119">Phishing and malware events from Exchange Online Protection and Office 365 Advanced Threat Protection.</span></span>|
|<span data-ttu-id="b8284-120">41</span><span class="sxs-lookup"><span data-stu-id="b8284-120">41</span></span>|<span data-ttu-id="b8284-121">ThreatIntelligenceUrl</span><span class="sxs-lookup"><span data-stu-id="b8284-121">ThreatIntelligenceUrl</span></span>|<span data-ttu-id="b8284-122">Vínculos seguros ATP tiempo de bloqueo y bloqueo de eventos de invalidación de la protección contra amenazas avanzada de Office 365.</span><span class="sxs-lookup"><span data-stu-id="b8284-122">ATP Safe Links time-of-block and block override events from Office 365 Advanced Threat Protection.</span></span>|
|<span data-ttu-id="b8284-123">47</span><span class="sxs-lookup"><span data-stu-id="b8284-123">47</span></span>|<span data-ttu-id="b8284-124">ThreatIntelligenceAtpContent</span><span class="sxs-lookup"><span data-stu-id="b8284-124">ThreatIntelligenceAtpContent</span></span>|<span data-ttu-id="b8284-125">Eventos de suPlantación de identidad y malware para archivos en SharePoint Online, OneDrive para la empresa y Microsoft Teams de la protección contra amenazas avanzada de Office 365.</span><span class="sxs-lookup"><span data-stu-id="b8284-125">Phishing and malware events for files in SharePoint Online, OneDrive for Business, and Microsoft Teams from Office 365 Advanced Threat Protection.</span></span>|

> [!IMPORTANT]
> <span data-ttu-id="b8284-126">Debe ser un administrador global de Office 365 o tener asignado el rol de administrador de seguridad para el centro de seguridad & cumplimiento para configurar la integración de SIEM con Office 365 protección contra amenazas avanzada.</span><span class="sxs-lookup"><span data-stu-id="b8284-126">You must be an Office 365 global administrator or have the security administrator role assigned for the Security & Compliance Center to set up SIEM integration with Office 365 Advanced Threat Protection.</span></span><br/><span data-ttu-id="b8284-127">El registro de auditoría debe estar activado para su entorno de Office 365.</span><span class="sxs-lookup"><span data-stu-id="b8284-127">Audit logging must be turned on for your Office 365 environment.</span></span> <span data-ttu-id="b8284-128">Para obtener ayuda, consulte [activar o desactivar la búsqueda de registros de auditoría de Office 365](turn-audit-log-search-on-or-off.md).</span><span class="sxs-lookup"><span data-stu-id="b8284-128">To get help with this, see [Turn Office 365 audit log search on or off](turn-audit-log-search-on-or-off.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="b8284-129">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="b8284-129">Related topics</span></span>

[<span data-ttu-id="b8284-130">Respuesta y investigación de amenazas de Office 365</span><span class="sxs-lookup"><span data-stu-id="b8284-130">Office 365 Threat Investigation and Response</span></span>](office-365-ti.md)

[<span data-ttu-id="b8284-131">Protección contra amenazas avanzada de Office 365</span><span class="sxs-lookup"><span data-stu-id="b8284-131">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md)

[<span data-ttu-id="b8284-132">Informes inteligentes y opiniones del centro de seguridad &amp; y cumplimiento de Office 365</span><span class="sxs-lookup"><span data-stu-id="b8284-132">Smart reports and insights in the Office 365 Security &amp; Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)
  
[<span data-ttu-id="b8284-133">Permissions in the Office 365 Security &amp; Compliance Center</span><span class="sxs-lookup"><span data-stu-id="b8284-133">Permissions in the Office 365 Security &amp; Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)
  
