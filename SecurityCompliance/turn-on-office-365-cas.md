---
title: Activar la seguridad de aplicación de nube de Office 365
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: ba919c73-d021-404d-9850-eec57e78678c
description: Lea este artículo para obtener información sobre cómo activar la seguridad de aplicaciones en la nube de Office 365, con la tecnología Cloud App Security en Microsoft Azure.
ms.openlocfilehash: 1227545b1e4d1521dc1820342f09aabdf16ec2c6
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32264132"
---
# <a name="turn-on-office-365-cloud-app-security"></a>Activar la seguridad de aplicación de nube de Office 365
  
|Evaluación * *\>**|Planeación * *\>**|Implementación * *\>**|Uso * * * *|
|:-----|:-----|:-----|:-----|
|[Empezar a evaluar](office-365-cas-overview.md) <br/> |[Empezar a planear](get-ready-for-office-365-cas.md) <br/> |Ya está aquí.  <br/> [Siguiente paso](activity-policies-and-alerts.md) <br/> |[Empezar a usar](utilization-activities-for-ocas.md) <br/> |
  
## <a name="turn-on-office-365-cloud-app-security"></a>Activar la seguridad de aplicación de nube de Office 365

> [!IMPORTANT]
> Debe ser administrador global o administrador de seguridad para realizar la siguiente tarea. Para obtener más información, consulte perMissions [in the &amp; Office 365 Security Compliance Center](permissions-in-the-security-and-compliance-center.md). Para que Office 365 Cloud App Security funcione correctamente, el **registro de auditoría debe estar activado** para su entorno de Office 365. Para obtener más información, consulte [activar o desactivar la búsqueda de registros de auditoría de Office 365](turn-audit-log-search-on-or-off.md). 
  
1. Como administrador global o administrador de seguridad, vaya a [https://protection.office.com](https://security.microsoft.com) e inicie sesión con su cuenta profesional o educativa para Office 365. (Esto le llevará al centro de &amp; seguridad y cumplimiento). 
    
2. Vaya a **alertas** \> para **Administrar alertas avanzadas**.
    
3. Seleccione **activar Office 365 Cloud App Security**.
    
4. Elija **ir a Office 365 Cloud App Security**.<br/>![En el centro &amp; de seguridad y cumplimiento, elija Administrar alertas avanzadas para ir a Office 365 Cloud App Security.](media/958632d4-03e3-4ade-8e22-d5509db6fca7.png)<br/>Esto le llevará al portal de seguridad de la aplicación de nube de Office 365, donde podrá ver los informes y crear o editar directivas.

Una vez que haya activado Office 365 Cloud App Security, puede ir al portal de Cloud App Security visitando [https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com) e iniciando sesión.
    
> [!NOTE]
> Al activar la seguridad de aplicación de nube de Office 365, se transfiere la información de auditoría de las cuentas de usuario y las actividades de usuario de Office 365 a [Microsoft Cloud App Security](https://aka.ms/whatiscas). Esto permite a Office 365 proporcionar alertas avanzadas, filtrado y otras características para que pueda obtener información y tomar medidas sobre actividades sospechosas. 
  
## <a name="next-steps"></a>Pasos siguientes

- [Directivas de actividad](activity-policies-and-alerts.md)
    
- [Directivas de detección de anomalías](anomaly-detection-policies-in-ocas.md)
    
- [Integración del servidor de SIEM](integrate-your-siem-server-with-office-365-cas.md)
    
- [Agrupar las direcciones IP para simplificar la administración](group-your-ip-addresses-in-ocas.md)
    

