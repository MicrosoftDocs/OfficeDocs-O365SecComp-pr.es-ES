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
ms.openlocfilehash: 057d8ac101b96f37846ac751645934279d45dc88
ms.sourcegitcommit: 17c7e18d7d00135b1af40cbea117c9a817a41117
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2018
ms.locfileid: "24972262"
---
# <a name="siem-integration-with-office-365-threat-intelligence-and-advanced-threat-protection"></a>Integración de SIEM con información sobre amenazas de Office 365 y avanzada de protección contra amenazas

Si su organización usa un servidor de administración (SIEM) de incidentes y eventos de seguridad, puede integrar información sobre amenazas de Office 365 y avanzada de protección contra amenazas con su servidor SIEM. Integración de SIEM permite ver la información, como malware detectado por protección avanzada de Office 365 e inteligencia de amenaza, en los informes de servidor SIEM. Para configurar la integración de SIEM, use la [API de administración de Office 365 actividad](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference). 

La API de administración de Office 365 actividad recupera información sobre el usuario, administración, sistema y las acciones de directiva y eventos de Office 365 y los registros de actividad de Azure Active Directory de su organización. [Esquema de información sobre amenazas y la protección de amenaza avanzada de Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-intelligence-schema) funciona con información sobre amenazas o protección contra amenazas avanzada, por lo que si su organización tiene avanzada protección contra amenazas, pero no la inteligencia sobre amenazas (o viceversa), puede aún puede usar esa misma API para la integración del servidor de SIEM. 

El servidor SIEM u otro sistema similar debería sondear la carga de trabajo **audit.general** a eventos de detección de acceso. Para obtener más información vea [empezar a trabajar con las API de administración de Office 365](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis). 

> [!IMPORTANT]
> Debe ser un administrador global de Office 365 o tener el rol de administrador de seguridad asignado en el centro de cumplimiento y seguridad para configurar la integración de SIEM con información sobre amenazas de Office 365 y avanzada de protección contra amenazas.<br/>Registro de auditoría debe activarlo para su entorno de Office 365. Para obtener ayuda con esto, vea [activar Office 365 de búsqueda de registros de auditoría activado o desactivado](turn-audit-log-search-on-or-off.md).

## <a name="related-topics"></a>Temas relacionados

[Inteligencia sobre amenazas de Office 365](office-365-ti.md)

[Protección contra amenazas avanzada de Office 365](office-365-atp.md)

[Informes y conocimientos en la seguridad de Office 365 de Smart &amp; centro de cumplimiento](reports-and-insights-in-security-and-compliance.md)
  
[Los permisos de la seguridad de Office 365 &amp; centro de cumplimiento](permissions-in-the-security-and-compliance-center.md)
  

