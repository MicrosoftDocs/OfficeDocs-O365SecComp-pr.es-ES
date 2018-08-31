---
title: Supervisión de Office 365 y la auditoría de acceso a controles
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: 8/21/2018
audience: ITPro
ms.topic: article
ms.service: Office 365 Administration
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: 'Resumen: Ofrece un resumen de los diversos supervisión y auditoría controles de acceso disponibles dentro de Office 365.'
ms.openlocfilehash: 7ef25d62ce3c4fa320dd0b164183c6f67be7d76d
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22536716"
---
# <a name="monitoring-and-auditing-access-controls-in-office-365"></a>Supervisión y auditoría de acceso a controles en Office 365

Microsoft lleva a cabo una amplia de supervisión y auditoría de todas las operaciones que se producen dentro de Office 365, el uso de privilegios y la delegación todos los. Control de Office 365 access es un proceso automatizado que se basa en el principio de privilegios mínimos y para incorporar acceso a controles de datos y las auditorías:
- Todos los acceso permitido es puede trazar a un único usuario, realizar los administradores responsables de su control de contenido de cliente.
- Las solicitudes de control de acceso, las aprobaciones y los registros de operaciones administrativas se capturan para el análisis de conocimientos de seguridad y eventos malintencionados.
- Los niveles de acceso se han revisado en cerca de pertenencia a grupos de seguridad en función de en tiempo real para asegurarse de que sólo los usuarios que hayan autorizado de justificación del negocio y cumplan los requisitos de idoneidad tienen acceso a los sistemas.
- Office 365, sus controles de acceso y servicios auxiliares, incluyendo Azure Active Directory y nuestros centros de datos físicos, se auditan con regularidad por terceros independientes para el cumplimiento de la [especificación ISO/IEC 27001](https://www.microsoft.com/en-us/TrustCenter/Compliance/iso-iec-27001), [ISO/IEC 27018](https://www.microsoft.com/en-us/TrustCenter/Compliance/iso-iec-27018), [seguridad social](https://www.microsoft.com/en-us/TrustCenter/Compliance/SOC), [FedRAMP](https://www.microsoft.com/en-us/TrustCenter/Compliance/FedRAMP)y otros [estándares](https://www.microsoft.com/en-us/TrustCenter/Compliance?service=Office#Icons).
- Los ingenieros de Office 365 son necesarias para comenzar anual formación de seguridad revisión de riesgos y procedimientos recomendados de acceso con privilegios elevados y reconoce, seguridad y las directivas de privacidad para continuar el mantenimiento de sus derechos para el servicio de Microsoft.

Alertas automatizadas se desencadenan cuando se detecta una actividad sospechosa, como múltiples inicios de sesión con errores en un breve período. El equipo de respuesta de seguridad de Office 365 usa el aprendizaje y análisis de datos grande para revisar y analizar la actividad de los patrones de acceso irregular y responde proactivamente a las actividades anómalas e ilegal. Microsoft también emplea un equipo dedicado de comprobadores de la penetración y activa en periódico rojo y equipo de azul ejercicios para buscar la seguridad y problemas de control en el servicio de acceso a. Los clientes también pueden comprobar la eficacia de los sistemas de control de acceso mediante el uso de informes de auditoría y la actividad de administración de API proporcionada por Office 365. 

Para obtener más información, vea la [referencia de la API de actividad de administración de Office 365](https://msdn.microsoft.com/en-us/library/office/mt227394.aspx) y [auditoría e informes en Office 365](office-365-auditing-and-reporting-overview.md).
