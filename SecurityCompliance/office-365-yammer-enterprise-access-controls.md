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
# <a name="yammer-enterprise-access-controls"></a>Controles de acceso de Yammer Enterprise 

Acceso físico y lógico para el entorno de producción Yammer está restringido a un conjunto muy pequeño de personas (infraestructura y operaciones). Al igual que con otros ingenieros de Office 365, los ingenieros de Yammer tienen cero acceso permanente a los datos de cliente. Debe solicitar acceso utilizando un sistema de control de acceso de just-in-time basado en aprobación similar a la caja de seguridad y hay un número limitado de aprobadores. Aprobadores comprobación la solicitud (por ejemplo, comprueban si la solicitud es legítima según necesidad, caso de negocio, hora, etc.) y, a continuación, aprobar o denegar la solicitud. Si se aprueba la solicitud, se concede acceso de manera oportuna durante un tiempo limitado y definido, después de que expire automáticamente. 

Al igual que con otros servicios de Office 365, todo el acceso al entorno de producción Yammer aprovecha la autenticación multifactor. Todo el historial de acceso y el comando se atribuye a un usuario y registra y revisado periódicamente por el equipo de seguridad de Yammer.

Para obtener más información acerca de la administración de Yammer y administración, consulte la [Ayuda de administración de Yammer](https://support.office.com/article/yammer-–-admin-help-e1464355-1f97-49ac-b2aa-dd320b179dbe?ui=en-US&rs=en-US&ad=US).