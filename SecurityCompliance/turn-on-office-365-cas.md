---
title: Activar Office 365 Cloud App Security
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: ba919c73-d021-404d-9850-eec57e78678c
description: Lea este artículo para obtener información sobre cómo activar Office 365 administración avanzada de seguridad, con tecnología de seguridad de la aplicación en la nube de Microsoft Azure.
ms.openlocfilehash: 8964a0b413b0350188c7f61638d04032534e5374
ms.sourcegitcommit: 9034809b6f308bedc3b8ddcca8242586b5c30f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2019
ms.locfileid: "28014792"
---
# <a name="turn-on-office-365-cloud-app-security"></a>Activar Office 365 Cloud App Security
  
|Evaluación **\>**|Planeación de **\>**|Implementación **\>**|Utilización de ***|
|:-----|:-----|:-----|:-----|
|[Empezar a evaluar](office-365-cas-overview.md) <br/> |[Comenzar a planear](get-ready-for-office-365-cas.md) <br/> |¡Están aquí!  <br/> [Paso siguiente](activity-policies-and-alerts.md) <br/> |[Iniciar utilizando](utilization-activities-for-ocas.md) <br/> |
  
## <a name="turn-on-office-365-cloud-app-security"></a>Activar Office 365 Cloud App Security

> [!IMPORTANT]
> Debe ser un administrador global o administrador de seguridad para llevar a cabo la siguiente tarea. Para obtener más información, vea [permisos en la seguridad de Office 365 &amp; centro de cumplimiento](permissions-in-the-security-and-compliance-center.md). En orden para Office 365 la seguridad de la aplicación de nube para que funcione la correcta, **debe estar activado el registro de auditoría** para su entorno de Office 365. Para obtener más información, vea [activar Office 365 de búsqueda de registros de auditoría activado o desactivado](turn-audit-log-search-on-or-off.md). 
  
1. Como administrador global o administrador de seguridad, vaya a [https://protection.office.com](https://security.microsoft.com) e iniciar sesión con su cuenta de trabajo o escuela para Office 365. (Esto le llevará a la seguridad &amp; centro de cumplimiento.) 
    
2. Vaya a **las alertas de** \> **avanzada de administrar las alertas**.
    
3. Seleccione **activar la seguridad de la aplicación de Office 365 en la nube**.
    
4. Elija **Ir a la seguridad de la aplicación de Office 365 en la nube**.<br/>![En la seguridad &amp; centro de cumplimiento, elija Administrar alertas avanzadas para ir a la seguridad de la aplicación de nube de Office 365](media/958632d4-03e3-4ade-8e22-d5509db6fca7.png)<br/>Esto le llevará al portal de seguridad de la aplicación de nube de Office 365, donde puede ver los informes y crear o editar las directivas.
    
> [!NOTE]
> Al activar la seguridad de la aplicación de nube de Office 365, información de auditoría sobre sus cuentas de usuario de Office 365 y las actividades del usuario se transfiere a la [Seguridad de la aplicación de Microsoft en la nube](https://aka.ms/whatiscas). Esto permite a Office 365 proporcionar alertas avanzadas, el filtrado y otras características para que pueda obtener información y tomar medidas sobre actividades sospechosas. 
  
## <a name="next-steps"></a>Pasos siguientes

- [Directivas de actividad](activity-policies-and-alerts.md)
    
- [Directivas de detección de anomalías](anomaly-detection-policies-in-ocas.md)
    
- [Integrar su servidor SIEM](integrate-your-siem-server-with-office-365-cas.md)
    
- [Las direcciones IP para simplificar la administración de grupo](group-your-ip-addresses-in-ocas.md)
    

