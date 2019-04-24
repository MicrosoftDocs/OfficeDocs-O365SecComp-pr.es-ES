---
title: Controles de acceso empresarial de Office 365 Yammer
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
description: 'Resumen: un breve resumen sobre los controles de acceso empresarial de Yammer en el entorno de producción.'
ms.openlocfilehash: 61598235a010aaa1c578c449cb054073212a41f9
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32262352"
---
# <a name="yammer-enterprise-access-controls"></a><span data-ttu-id="2eaa1-103">Controles de acceso de Yammer Enterprise</span><span class="sxs-lookup"><span data-stu-id="2eaa1-103">Yammer Enterprise Access Controls</span></span> 

<span data-ttu-id="2eaa1-104">El acceso físico y lógico al entorno de producción de Yammer está restringido a un conjunto muy pequeño de personas (infraestructura y operaciones).</span><span class="sxs-lookup"><span data-stu-id="2eaa1-104">Both physical and logical access to the Yammer production environment is restricted to a very small set of people (infrastructure and operations).</span></span> <span data-ttu-id="2eaa1-105">Como con otros ingenieros de Office 365, los ingenieros de Yammer tienen un acceso sin igual a los datos de los clientes.</span><span class="sxs-lookup"><span data-stu-id="2eaa1-105">As with other Office 365 engineers, Yammer engineers have zero standing access to Customer Data.</span></span> <span data-ttu-id="2eaa1-106">El acceso debe solicitarse mediante un sistema de control de acceso Just-in-Time basado en aprobaciones similar a Lockbox y hay un número limitado de aprobadores.</span><span class="sxs-lookup"><span data-stu-id="2eaa1-106">Access must be requested using an approval-based just-in-time access control system similar to Lockbox, and there is a limited number of approvers.</span></span> <span data-ttu-id="2eaa1-107">Los aprobadores comprueban la solicitud (por ejemplo, comprueban si la solicitud es legítima según la necesidad, el caso de negocio, la hora, etc.) y, a continuación, aprueba o deniega la solicitud.</span><span class="sxs-lookup"><span data-stu-id="2eaa1-107">Approvers verify the request (e.g., they verify whether the request is legitimate based on need, business case, time, etc.), and then approve or deny the request.</span></span> <span data-ttu-id="2eaa1-108">Si se aprueba la solicitud, se concede el acceso JIT durante un tiempo limitado y definido, después de que expire automáticamente.</span><span class="sxs-lookup"><span data-stu-id="2eaa1-108">If the request is approved, JIT access is granted for a defined and limited time, after which it automatically expires.</span></span> 

<span data-ttu-id="2eaa1-109">Como con otros servicios de Office 365, todo acceso al entorno de producción de Yammer aprovecha la autenticación multifactor.</span><span class="sxs-lookup"><span data-stu-id="2eaa1-109">As with other Office 365 services, all access to the Yammer production environment leverages multi-factor authentication.</span></span> <span data-ttu-id="2eaa1-110">Todo el historial de acceso y comandos se atribuye a un usuario y ha sido registrado y revisado con regularidad por el equipo de seguridad de Yammer.</span><span class="sxs-lookup"><span data-stu-id="2eaa1-110">All access and command history is attributed to a user, and logged and reviewed regularly by the Yammer security team.</span></span>

<span data-ttu-id="2eaa1-111">Para obtener más información acerca de la administración y administración de Yammer, consulte [ayuda del administrador de Yammer](https://support.office.com/article/yammer-–-admin-help-e1464355-1f97-49ac-b2aa-dd320b179dbe?ui=en-US&rs=en-US&ad=US).</span><span class="sxs-lookup"><span data-stu-id="2eaa1-111">For more information about Yammer administration and management, see [Yammer Admin Help](https://support.office.com/article/yammer-–-admin-help-e1464355-1f97-49ac-b2aa-dd320b179dbe?ui=en-US&rs=en-US&ad=US).</span></span>