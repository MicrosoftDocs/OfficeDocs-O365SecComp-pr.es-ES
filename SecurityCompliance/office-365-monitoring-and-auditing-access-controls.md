---
title: Controles de acceso de supervisión y auditoría de Office 365
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: 'Resumen: Resumen de los diversos controles de acceso de supervisión y auditoría disponibles en Office 365.'
ms.openlocfilehash: 39ee2b535c89419e161558cba2122e325228ffb1
ms.sourcegitcommit: 7b5e4a7a51f3cdd741deb77a2d60a18e2316618d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/01/2019
ms.locfileid: "33520720"
---
# <a name="monitoring-and-auditing-access-controls-in-office-365"></a>Supervisión y auditoría de controles de acceso en Office 365

Microsoft realiza una supervisión y auditoría exhaustiva de toda la delegación, los privilegios y las operaciones que se producen en Office 365. El control de acceso de Office 365 es un proceso automatizado que se basa en el principio de privilegios mínimos e incorpora controles y auditorías de acceso a datos:

- Todo el acceso permitido se puede trazar a un usuario único. Los administradores son responsables de su control del contenido del cliente.
- Se capturan las solicitudes de control de acceso, las aprobaciones y los registros de operaciones administrativas para analizar la seguridad y los eventos malintencionados.
- Los niveles de acceso se revisan casi en tiempo real en función de la pertenencia a grupos de seguridad para garantizar que solo los usuarios que tengan justificaciones empresariales autorizadas y cumplan los requisitos de elegibilidad tienen acceso a los sistemas.
- Office 365, sus controles de acceso y los servicios de soporte, incluidos Azure Active Directory y centros de recursos físicos, son auditados regularmente por terceros independientes para el cumplimiento de las normas [ISO/iec 27001](https://www.microsoft.com/en-us/TrustCenter/Compliance/iso-iec-27001), [ISO/IEC 27018](https://www.microsoft.com/en-us/TrustCenter/Compliance/iso-iec-27018), [SOC](https://www.microsoft.com/en-us/TrustCenter/Compliance/SOC), [ FedRAMP](https://www.microsoft.com/en-us/TrustCenter/Compliance/FedRAMP)y otros [estándares](https://www.microsoft.com/en-us/TrustCenter/Compliance?service=Office#Icons).
- Los ingenieros de Office 365 deben realizar una formación de seguridad anual, revisar los procedimientos de acceso elevado y confirmar las directivas de seguridad y privacidad de Microsoft para mantener los derechos del servicio.

Las alertas automatizadas se desencadenan cuando se detecta actividad sospechosa, como varios inicios de sesión erróneos en un período corto. El equipo de respuesta de seguridad de Office 365 usa el aprendizaje automático y un análisis de datos extensos para revisar y analizar la actividad, buscar patrones de acceso irregulares y responder de forma proactiva a actividades anómalas y ilícitas. Microsoft también emplea un equipo dedicado de evaluadores de penetración y participa en el equipo en rojo periódico y en los ejercicios de equipo azul para encontrar los problemas de seguridad y control de acceso en el servicio. Los clientes pueden comprobar la eficacia de los sistemas de control de acceso mediante el uso de informes de auditoría y la API de actividad de administración proporcionada por Office 365.

Para obtener más información, consulte referencia de la [API de actividad de administración de office 365](https://msdn.microsoft.com/en-us/library/office/mt227394.aspx) y [Auditoría e informes en Office 365](office-365-auditing-and-reporting-overview.md).
