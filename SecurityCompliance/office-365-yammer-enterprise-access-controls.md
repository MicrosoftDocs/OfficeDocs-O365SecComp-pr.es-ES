---
title: Controles de acceso empresarial de Office 365 Yammer
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
- M365-security-compliance
description: 'Resumen: un breve resumen sobre los controles de acceso empresarial de Yammer en el entorno de producción.'
ms.openlocfilehash: 76b62e7ea026a52d822e5a213461e930b1d595e3
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/23/2019
ms.locfileid: "30217890"
---
# <a name="yammer-enterprise-access-controls"></a>Controles de acceso de Yammer Enterprise 

El acceso físico y lógico al entorno de producción de Yammer está restringido a un conjunto muy pequeño de personas (infraestructura y operaciones). Como con otros ingenieros de Office 365, los ingenieros de Yammer tienen un acceso sin igual a los datos de los clientes. El acceso debe solicitarse mediante un sistema de control de acceso Just-in-Time basado en aprobaciones similar a Lockbox y hay un número limitado de aprobadores. Los aprobadores comprueban la solicitud (por ejemplo, comprueban si la solicitud es legítima según la necesidad, el caso de negocio, la hora, etc.) y, a continuación, aprueba o deniega la solicitud. Si se aprueba la solicitud, se concede el acceso JIT durante un tiempo limitado y definido, después de que expire automáticamente. 

Como con otros servicios de Office 365, todo acceso al entorno de producción de Yammer aprovecha la autenticación multifactor. Todo el historial de acceso y comandos se atribuye a un usuario y ha sido registrado y revisado con regularidad por el equipo de seguridad de Yammer.

Para obtener más información acerca de la administración y administración de Yammer, consulte [ayuda del administrador de Yammer](https://support.office.com/article/yammer-–-admin-help-e1464355-1f97-49ac-b2aa-dd320b179dbe?ui=en-US&rs=en-US&ad=US).