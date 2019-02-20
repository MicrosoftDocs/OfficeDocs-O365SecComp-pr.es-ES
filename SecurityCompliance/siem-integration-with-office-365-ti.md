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
# <a name="siem-integration-with-office-365-threat-intelligence-and-advanced-threat-protection"></a>Integración de SIEM con Office 365 Threat Intelligence y protección contra amenazas avanzada

Si su organización usa un servidor de incidentes de seguridad y de administración de eventos (SIEM), puede integrar la inteligencia sobre amenazas de Office 365 y la protección contra amenazas avanzada con el servidor de SIEM. La integración de SIEM permite ver información, como malware detectada por Office 365 Advanced Protection y Threat Intelligence, en los informes del servidor de SIEM. Para configurar la integración de SIEM, use la [API de administración de actividad de Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference). 

La API de administración de actividad de Office 365 recupera información sobre acciones y eventos de usuario, administrador, sistema y Directiva de los registros de actividad de Office 365 y Azure Active Directory de la organización. El [esquema de protección contra amenazas avanzada de Office 365 y de inteligencia](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-intelligence-schema) sobre amenazas funciona con inteligencia de amenazas o protección contra amenazas avanzada, por lo que si su organización tiene protección contra amenazas avanzada pero no ofrece inteligencia de amenazas (o viceversa), puede Siga usando esa misma API para la integración del servidor de SIEM. 

El servidor de SIEM u otro sistema similar debe sondear la **auditoría. general** Workload para acceder a los eventos de detección. Para obtener más información, vea Introducción [a las API de administración de Office 365](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis). 

> [!IMPORTANT]
> Debe ser un administrador global de Office 365 o tener asignado el rol de administrador de seguridad para el centro de seguridad & cumplimiento para configurar la integración de SIEM con Office 365 protección contra amenazas avanzada.<br/>El registro de auditoría debe estar activado para su entorno de Office 365. Para obtener ayuda, consulte [activar o desactivar la búsqueda de registros de auditoría de Office 365](turn-audit-log-search-on-or-off.md).

## <a name="related-topics"></a>Temas relacionados

[Inteligencia sobre amenazas de Office 365](office-365-ti.md)

[Protección contra amenazas avanzada de Office 365](office-365-atp.md)

[Informes inteligentes y opiniones del centro de seguridad &amp; y cumplimiento de Office 365](reports-and-insights-in-security-and-compliance.md)
  
[Permisos en el centro de seguridad &amp; y cumplimiento de Office 365](permissions-in-the-security-and-compliance-center.md)
  

