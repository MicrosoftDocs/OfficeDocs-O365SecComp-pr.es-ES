---
title: Integración del servidor SIEM con Microsoft 365
ms.author: deniseb
author: denisebmsft
manager: laurawi
audience: ITPro
ms.topic: article
ms.date: 06/17/2019
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
ms.custom:
- Ent_Solutions
- SIEM
description: 'Resumen: Lea este artículo para obtener información general sobre la integración del servidor SIEM con Microsoft 365.'
ms.openlocfilehash: 9138cbc395b90f50fa60bf545066c17cf26d7edf
ms.sourcegitcommit: f2798d46acfbd56314e809cd3fe0350be807e420
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/17/2019
ms.locfileid: "35014769"
---
# <a name="siem-server-integration-with-microsoft-365-services-and-applications"></a><span data-ttu-id="4ba3c-103">Integración del servidor de SIEM con los servicios y aplicaciones de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="4ba3c-103">SIEM server integration with Microsoft 365 services and applications</span></span>

## <a name="overview"></a><span data-ttu-id="4ba3c-104">Información general</span><span class="sxs-lookup"><span data-stu-id="4ba3c-104">Overview</span></span>

<span data-ttu-id="4ba3c-105">Si su organización usa un servidor de administración de eventos e información de seguridad (SIEM) o si tiene previsto obtener un servidor de SIEM en breve, es posible que se pregunte cómo se integrará con Microsoft 365, incluido Office 365 E5.</span><span class="sxs-lookup"><span data-stu-id="4ba3c-105">If your organization is using a Security Information and Event Management (SIEM) server, or if you are planning to get a SIEM server soon, you might be wondering how that'll integrate with your Microsoft 365, including Office 365 E5.</span></span> <span data-ttu-id="4ba3c-106">Si necesita un servidor de SIEM depende de muchos factores, como los requisitos de seguridad de la organización.</span><span class="sxs-lookup"><span data-stu-id="4ba3c-106">Whether you need a SIEM server depends on many factors, such as your organization's security requirements.</span></span> <span data-ttu-id="4ba3c-107">Microsoft 365 ofrece una amplia variedad de características de seguridad; sin embargo, si su organización tiene contenido y aplicaciones locales y en la nube (como en el caso de una implementación de nube híbrida), puede considerar la posibilidad de agregar un servidor SIEM para una protección adicional.</span><span class="sxs-lookup"><span data-stu-id="4ba3c-107">Microsoft 365 offers a variety of security features; however, if your organization has content and applications on premises and in the cloud (as in the case of a hybrid cloud deployment), you might consider adding a SIEM server for extra protection.</span></span> <span data-ttu-id="4ba3c-108">O bien, si su organización tiene unos requisitos de seguridad especialmente estrictos que debe cumplir, puede considerar la posibilidad de agregar un servidor SIEM a su entorno.</span><span class="sxs-lookup"><span data-stu-id="4ba3c-108">Or, if your organization has particularly stringent security requirements you must meet, you might consider adding a SIEM server to your environment.</span></span>

## <a name="siem-server-integration-microsoft-365"></a><span data-ttu-id="4ba3c-109">Integración del servidor de SIEM Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="4ba3c-109">SIEM server integration Microsoft 365</span></span>

<span data-ttu-id="4ba3c-110">Un servidor de SIEM puede recibir datos de una amplia variedad de aplicaciones y servicios de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4ba3c-110">A SIEM server can receive data from a wide variety of Microsoft 365 services and applications.</span></span> <span data-ttu-id="4ba3c-111">En la siguiente tabla se enumeran varios servicios y aplicaciones de Microsoft 365 junto con entradas del servidor SIEM y dónde obtener más información sobre la integración del servidor de SIEM.</span><span class="sxs-lookup"><span data-stu-id="4ba3c-111">The following table lists several Microsoft 365 services and applications along with SIEM server inputs and where to go to learn more about SIEM server integration.</span></span> 

| <span data-ttu-id="4ba3c-112">Servicio o aplicación de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="4ba3c-112">Microsoft 365 Service or Application</span></span> | <span data-ttu-id="4ba3c-113">Entradas del servidor SIEM</span><span class="sxs-lookup"><span data-stu-id="4ba3c-113">SIEM server inputs</span></span> | <span data-ttu-id="4ba3c-114">Recursos para obtener más información</span><span class="sxs-lookup"><span data-stu-id="4ba3c-114">Resources to learn more</span></span> |
| --- | --- | --- |
| [<span data-ttu-id="4ba3c-115">Protección contra amenazas avanzada de Office 365</span><span class="sxs-lookup"><span data-stu-id="4ba3c-115">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md) <br/><span data-ttu-id="4ba3c-116">o</span><span class="sxs-lookup"><span data-stu-id="4ba3c-116">or</span></span><br/>[<span data-ttu-id="4ba3c-117">Inteligencia sobre amenazas de Office 365</span><span class="sxs-lookup"><span data-stu-id="4ba3c-117">Office 365 Threat Intelligence</span></span>](office-365-ti.md) | <span data-ttu-id="4ba3c-118">Registros de auditoría</span><span class="sxs-lookup"><span data-stu-id="4ba3c-118">Audit logs</span></span> | [<span data-ttu-id="4ba3c-119">Integración de SIEM con Office 365 protección contra amenazas avanzada</span><span class="sxs-lookup"><span data-stu-id="4ba3c-119">SIEM integration with Office 365 Advanced Threat Protection</span></span>](siem-integration-with-office-365-ti.md) |
| [<span data-ttu-id="4ba3c-120">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="4ba3c-120">Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security) | <span data-ttu-id="4ba3c-121">Integración de registros</span><span class="sxs-lookup"><span data-stu-id="4ba3c-121">Log integration</span></span> | [<span data-ttu-id="4ba3c-122">Integración de SIEM con Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="4ba3c-122">SIEM integration with Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security/siem) |
| [<span data-ttu-id="4ba3c-123">Protección contra amenazas de Microsoft</span><span class="sxs-lookup"><span data-stu-id="4ba3c-123">Microsoft Threat Protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/) | <span data-ttu-id="4ba3c-124">Integración de registros</span><span class="sxs-lookup"><span data-stu-id="4ba3c-124">Log integration</span></span> | [<span data-ttu-id="4ba3c-125">Extraer alertas a las herramientas de SIEM</span><span class="sxs-lookup"><span data-stu-id="4ba3c-125">Pull alerts to your SIEM tools</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-siem) |
| <span data-ttu-id="4ba3c-126">[Centro de seguridad de Azure](https://docs.microsoft.com/azure/security-center/security-center-intro) (Protección contra amenazas y detección de amenazas)</span><span class="sxs-lookup"><span data-stu-id="4ba3c-126">[Azure Security Center](https://docs.microsoft.com/azure/security-center/security-center-intro) (Threat Protection and Threat Detection)</span></span> | <span data-ttu-id="4ba3c-127">Alertas</span><span class="sxs-lookup"><span data-stu-id="4ba3c-127">Alerts</span></span> | [<span data-ttu-id="4ba3c-128">Exportación de datos de seguridad de Azure a SIEM-configuración de canalización-vista previa</span><span class="sxs-lookup"><span data-stu-id="4ba3c-128">Azure Security data export to SIEM - Pipeline Configuration - Preview</span></span>](https://docs.microsoft.com/azure/security-center/security-center-export-data-to-siem) |
|[<span data-ttu-id="4ba3c-129">Análisis de amenazas avanzadas de Azure</span><span class="sxs-lookup"><span data-stu-id="4ba3c-129">Azure Advanced Threat Analytics</span></span>](https://docs.microsoft.com/azure/security/azure-threat-detection) | <span data-ttu-id="4ba3c-130">Azure monitor</span><span class="sxs-lookup"><span data-stu-id="4ba3c-130">Azure Monitor</span></span> | [<span data-ttu-id="4ba3c-131">Blog Usar Azure monitor para integrar con las herramientas de SIEM</span><span class="sxs-lookup"><span data-stu-id="4ba3c-131">(Blog) Use Azure Monitor to integrate with SIEM tools</span></span>](https://azure.microsoft.com/blog/use-azure-monitor-to-integrate-with-siem-tools) |
|[<span data-ttu-id="4ba3c-132">Azure Active Directory Identity Protection</span><span class="sxs-lookup"><span data-stu-id="4ba3c-132">Azure Active Directory Identity Protection</span></span>](https://docs.microsoft.com/azure/active-directory/identity-protection/overview) |<span data-ttu-id="4ba3c-133">Integración de registros</span><span class="sxs-lookup"><span data-stu-id="4ba3c-133">Log integration</span></span> |[<span data-ttu-id="4ba3c-134">Integrar las alertas de la API de seguridad de Microsoft Graph con un SIEM</span><span class="sxs-lookup"><span data-stu-id="4ba3c-134">Integrate Microsoft Graph Security API alerts with a SIEM</span></span>](https://docs.microsoft.com/graph/security-siemintegration) |


## <a name="audit-logging-must-be-turned-on"></a><span data-ttu-id="4ba3c-135">El registro de auditoría debe estar activado</span><span class="sxs-lookup"><span data-stu-id="4ba3c-135">Audit logging must be turned on</span></span>

<span data-ttu-id="4ba3c-136">Asegúrese de que el registro de auditoría esté activado antes de configurar la integración del servidor SIEM.</span><span class="sxs-lookup"><span data-stu-id="4ba3c-136">Make sure audit logging is turned on before you configure SIEM server integration.</span></span> 

- <span data-ttu-id="4ba3c-137">En SharePoint Online, OneDrive para la empresa y Azure Active Directory, [el registro de auditoría está activado en el centro de seguridad & cumplimiento](https://docs.microsoft.com/office365/securitycompliance/turn-audit-log-search-on-or-off).</span><span class="sxs-lookup"><span data-stu-id="4ba3c-137">For SharePoint Online, OneDrive for Business, and Azure Active Directory, [audit logging is turned on in the Security & Compliance Center](https://docs.microsoft.com/office365/securitycompliance/turn-audit-log-search-on-or-off).</span></span>

- <span data-ttu-id="4ba3c-138">Para Exchange Online, el [registro de auditoría está activado con Windows PowerShell](https://docs.microsoft.com/office365/securitycompliance/enable-mailbox-auditing).</span><span class="sxs-lookup"><span data-stu-id="4ba3c-138">For Exchange Online, [audit logging is turned on with Windows PowerShell](https://docs.microsoft.com/office365/securitycompliance/enable-mailbox-auditing).</span></span>
 
## <a name="see-also"></a><span data-ttu-id="4ba3c-139">Vea también</span><span class="sxs-lookup"><span data-stu-id="4ba3c-139">See Also</span></span>

[<span data-ttu-id="4ba3c-140">Adopción de la nube y soluciones híbridas</span><span class="sxs-lookup"><span data-stu-id="4ba3c-140">Cloud adoption and hybrid solutions</span></span>](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)
  
[<span data-ttu-id="4ba3c-141">Guías del laboratorio de pruebas de adopción de la nube (TLG)</span><span class="sxs-lookup"><span data-stu-id="4ba3c-141">Cloud adoption Test Lab Guides (TLGs)</span></span>](https://docs.microsoft.com/office365/enterprise/cloud-adoption-test-lab-guides-tlgs)


