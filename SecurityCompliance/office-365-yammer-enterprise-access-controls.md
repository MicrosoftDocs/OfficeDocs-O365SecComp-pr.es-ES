---
title: Yammer Enterprise acceso a controles de Office 365
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
description: 'Resumen: Un breve resumen acerca de los controles de acceso de empresa de Yammer en el entorno de producción.'
ms.openlocfilehash: 3f51e63c16022353e743b57d8e977f2ea2e6a835
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22536717"
---
# <a name="yammer-enterprise-access-controls"></a><span data-ttu-id="6ef8e-103">Controles de acceso de Yammer Enterprise</span><span class="sxs-lookup"><span data-stu-id="6ef8e-103">Yammer Enterprise Access Controls</span></span> 

<span data-ttu-id="6ef8e-p101">Acceso físico y lógico para el entorno de producción Yammer está restringido a un conjunto muy pequeño de personas (infraestructura y operaciones). Al igual que con otros ingenieros de Office 365, los ingenieros de Yammer tienen cero acceso permanente a los datos de cliente. Debe solicitar acceso utilizando un sistema de control de acceso de just-in-time basado en aprobación similar a la caja de seguridad y hay un número limitado de aprobadores. Aprobadores comprobación la solicitud (por ejemplo, comprueban si la solicitud es legítima según necesidad, caso de negocio, hora, etc.) y, a continuación, aprobar o denegar la solicitud. Si se aprueba la solicitud, se concede acceso de manera oportuna durante un tiempo limitado y definido, después de que expire automáticamente.</span><span class="sxs-lookup"><span data-stu-id="6ef8e-p101">Both physical and logical access to the Yammer production environment is restricted to a very small set of people (infrastructure and operations). As with other Office 365 engineers, Yammer engineers have zero standing access to Customer Data. Access must be requested using an approval-based just-in-time access control system similar to Lockbox, and there is a limited number of approvers. Approvers verify the request (e.g., they verify whether the request is legitimate based on need, business case, time, etc.), and then approve or deny the request. If the request is approved, JIT access is granted for a defined and limited time, after which it automatically expires.</span></span> 

<span data-ttu-id="6ef8e-p102">Al igual que con otros servicios de Office 365, todo el acceso al entorno de producción Yammer aprovecha la autenticación multifactor. Todo el historial de acceso y el comando se atribuye a un usuario y registra y revisado periódicamente por el equipo de seguridad de Yammer.</span><span class="sxs-lookup"><span data-stu-id="6ef8e-p102">As with other Office 365 services, all access to the Yammer production environment leverages multi-factor authentication. All access and command history is attributed to a user, and logged and reviewed regularly by the Yammer security team.</span></span>

<span data-ttu-id="6ef8e-111">Para obtener más información acerca de la administración de Yammer y administración, consulte la [Ayuda de administración de Yammer](https://support.office.com/article/yammer-–-admin-help-e1464355-1f97-49ac-b2aa-dd320b179dbe?ui=en-US&rs=en-US&ad=US).</span><span class="sxs-lookup"><span data-stu-id="6ef8e-111">For more information about Yammer administration and management, see [Yammer Admin Help](https://support.office.com/article/yammer-–-admin-help-e1464355-1f97-49ac-b2aa-dd320b179dbe?ui=en-US&rs=en-US&ad=US).</span></span>