---
title: API de Actividad de administración de Office 365
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: 8/21/2018
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-analytics
description: Un breve resumen sobre la API de actividad de administración de Office 365.
ms.openlocfilehash: df90eba0d019a862d4699f3e2aa0a04e88b0c371
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/23/2019
ms.locfileid: "30214580"
---
# <a name="office-365-management-activity-api"></a>API de Actividad de administración de Office 365
Microsoft proporciona Reporting Services que permite a los administradores obtener información transaccional agregada sobre su inquilino de Office 365. La [API de actividad de administración 365 de Office](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview) usa un diseño RESTful estándar de la industria y OAuth v2 para la autenticación, lo que facilita empezar a experimentar con la recuperación de datos y su incorporación a herramientas y aplicaciones de visualización. La API proporciona una fuente de datos que incluye información sobre el usuario, el administrador, las operaciones y la actividad de seguridad en Office 365. Los datos se pueden conservar con fines regulatorios o combinarse con datos de registros que se retienen de una infraestructura local u otros orígenes para crear una solución de supervisión para operaciones, seguridad y cumplimiento en toda la empresa.

La API de actividad de administración de Office 365 proporciona información sobre diversas acciones y eventos de usuario, administrador, sistema y Directiva de los registros de actividad de Office 365 y Azure Active Directory. La API proporciona un esquema de auditoría coherente con más de 10 campos que son comunes a todos los servicios. Esto permite a las organizaciones establecer conexiones entre eventos de forma sencilla y permite nuevas formas de la razón sobre los datos. Docenas de proveedores de software independientes (ISV) se han asociado con Microsoft y han creado soluciones basadas en la API. Algunas soluciones se centran exclusivamente en los datos de Office 365, mientras que otras proporcionan la capacidad de recopilar datos de varios proveedores de nube y sistemas locales para crear una vista unificada de todas las operaciones, la seguridad y la actividad relacionada con el cumplimiento. Para obtener más información, vea la referencia de la [API de actividad de administración de Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference).
