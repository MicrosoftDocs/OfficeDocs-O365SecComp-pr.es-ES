---
title: Introducción a Office 365 Cloud App Security
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 01/22/2019
ms.audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MET150
- MOE150
ms.assetid: 81f0ee9a-9645-45ab-ba56-de9cbccab475
description: 'Office 365 Cloud App Security le ofrece información sobre actividades sospechosas en Office 365 para poder investigar situaciones potencialmente problemáticas y, si es necesario, emprender acciones para solucionar los problemas de seguridad. '
ms.openlocfilehash: 974858a547d9af2db600f9856efbce619a3b38e4
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/23/2019
ms.locfileid: "30220180"
---
# <a name="overview-of-office-365-cloud-app-security"></a>Introducción a Office 365 Cloud App Security
  
|Evaluación * *\>**|Planeación * *\>**|Implementación * *\>**|Uso * * * *|
|:-----|:-----|:-----|:-----|
|Ya está aquí.  <br/> [Siguiente paso](get-ready-for-office-365-cas.md) <br/> |[Empezar a planear](get-ready-for-office-365-cas.md) <br/> |[Iniciar la implementación](turn-on-office-365-cas.md) <br/> |[Empezar a usar](utilization-activities-for-ocas.md) <br/> |
   
> [!NOTE]
> Office 365 Cloud App Security está disponible en Office 365 Enterprise E5. Si su organización usa otra suscripción de Office 365 Enterprise, Office 365 Cloud App Security puede adquirirse como un complemento. (como administrador global, en el centro de administración de Office 365, elija **facturación** \> **Add**subscriptions). Para obtener más información, consulte [office 365 Platform Service Description: office &amp; 365 Security Compliance Center](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center) y [comprar o editar un complemento para Office 365 para empresas](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/buy-or-edit-an-add-on). 
  
Office 365 Cloud App Security le proporciona información sobre actividades sospechosas en Office 365 para poder investigar situaciones potencialmente problemáticas y, si es necesario, emprender acciones para solucionar los problemas de seguridad. Con Office 365 Cloud App Security, puede recibir notificaciones de alertas desencadenadas para actividades atípicas o sospechosas, vea cómo se obtiene acceso a los datos de la organización en Office 365 y cómo se usa, se suspenden las cuentas de usuario que muestran actividades sospechosas y se requiere los usuarios pueden volver a iniciar sesión en las aplicaciones de Office 365 después de que se desencadene una alerta. Lea este artículo para obtener información general sobre las características y capacidades de seguridad de aplicaciones de nube de Office 365.
  
    
## <a name="how-to-find-the-office-365-cloud-app-security-portal"></a>Cómo encontrar el portal de seguridad de aplicaciones de nube de Office 365

> [!NOTE]
> Para acceder al portal de seguridad de aplicaciones de nube de Office 365, debe ser un administrador global de Office 365, un administrador de seguridad o un lector de seguridad. Para obtener más información, consulte perMissions [in the &amp; Office 365 Security Compliance Center](permissions-in-the-security-and-compliance-center.md). 
  
Puede acceder al portal de seguridad de la aplicación de nube de Office 365 [https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com) visitando e iniciando sesión. 

También puede obtener acceso desde el centro de seguridad &amp; y cumplimiento de Office 365. Esta es una buena forma de hacerlo:
  
1. Vaya a [https://protection.office.com](https://protection.office.com) e inicie sesión con su cuenta profesional o educativa para Office 365. (Esto le llevará al centro de &amp; seguridad y cumplimiento).
    
2. En el centro &amp; de seguridad y cumplimiento, elija **alertas** \> **Administrar alertas avanzadas**. <br/>![Elija Administrar alertas avanzadas para ir a Office 365 Cloud App Security](media/958632d4-03e3-4ade-8e22-d5509db6fca7.png)<br/>(Si Office 365 Cloud App Security todavía no está habilitado y es un administrador global, [Active Office 365 Cloud App Security](turn-on-office-365-cas.md)).
    
3. Elija **ir a Office 365 Cloud App Security**. 
    
## <a name="policies"></a>Policies

Office 365 Cloud App Security funciona con las directivas definidas para su organización. Con Office 365 Cloud App Security, su organización obtiene muchas directivas de detección de anomalías predefinidas y varias plantillas para las directivas de actividad. Estas directivas están diseñadas para detectar anomalías generales, identificar a los usuarios que inician sesión desde una dirección IP arriesgada, detectar actividades de ransomware, detectar actividades de administrador desde direcciones IP no corporativas y mucho más.
  
![En el portal de CAS, elija \> plantillas de control para ver o crear plantillas de directiva.](media/88f615b4-aa8a-480c-b239-323dfcd628e1.png)
  
para ver o usar plantillas de directiva, en el portal de seguridad de aplicaciones de nube de Office 365, vaya a **plantillas**de **Control** \> . 
  
![En el portal de CAS de O365, seleccione control](media/287c2ea9-5172-4697-8e0e-b9ab654105bc.png)
  
Para obtener más información acerca de las directivas, vea los siguientes recursos:
  
- [Directivas de actividad y alertas en Office 365 Cloud App Security](activity-policies-and-alerts.md)
    
- [Directivas de detección de anomalías en Office 365 Cloud App Security](anomaly-detection-policies-in-ocas.md)
    
## <a name="alerts"></a>Alertas

Cuando se definen las directivas, las alertas notifican sobre actividades sospechosas o atípicas que se detectaron. Para ver las alertas de su organización, elija **alertas** en la barra de navegación en la parte superior de la pantalla. 
  
![En la página Alertas, puede ver las alertas que se han desencadenado y las acciones que se han llevado a cabo.](media/3b53d4c9-4b13-435d-8547-8c0f9ae6b914.png)
  
A medida que se desencadenen alertas, puede revisarlas para obtener más información sobre lo que está ocurriendo. A continuación, si la actividad sigue siendo sospechosa, puede realizar una acción. Por ejemplo, puede notificar a un usuario sobre un problema, suspender a un usuario de iniciar sesión en Office 365 o requerir que un usuario vuelva a iniciar sesión en las aplicaciones de Office 365.
  
Para obtener más información acerca de las alertas, vea los siguientes recursos:
  
- [Directivas de actividad y alertas en Office 365 Cloud App Security](activity-policies-and-alerts.md)
    
- [Directivas de detección de anomalías en Office 365 Cloud App Security](anomaly-detection-policies-in-ocas.md)
    
- [Revisar y realizar acciones en las alertas de seguridad de la aplicación de nube de Office 365](review-office-365-cas-alerts.md)
    
## <a name="activity-logs"></a>Registros de actividad

Vea información sobre las actividades de usuario en la página Registro de actividades de Office 365 Cloud App Security.
  
![En el portal de CAS de O365, \> elija investigar registro de actividades.](media/ec19e77d-4e11-49fc-ab7c-0e8b0c29c93c.png)
  
para obtener acceso a esta página, en el portal de seguridad de aplicaciones de nube de Office 365, vaya a **investigación** \> de **registro de actividades**. 
  
![En el portal de CAS de O365, elija investigar.](media/8c7b87c9-71a6-4952-adb2-185e941ffe9a.png)
  
También puede usar los registros de tráfico web con Office 365 Cloud App Security. Cuanto más detalles se incluyan en los archivos de registro, mejor será la visibilidad que tendrá en la actividad de los usuarios. Puede usar los archivos de registro de Barracuda, Blue, Check Point, Cisco, Clavister, Dell SonicWALL, Fortinet, Juniper, McAfee, Microsoft, palo alto, Sophos, Squid, Websence, Zscaler, etc.
  
[Obtener información sobre los orígenes de datos y los registros de tráfico web para Office 365 Cloud App Security](web-traffic-logs-and-data-sources-for-ocas.md)
  
## <a name="oauth-apps"></a>Aplicaciones de OAuth

Con Office 365 Cloud App Security, puede permitir o impedir que los usuarios de su organización usen aplicaciones de terceros que tengan acceso a datos en Office 365.
  
![En las entidades de certificación de O365, puede obtener acceso a la página Administrar aplicaciones de OAuth desde el menú investigar.](media/78272cda-986f-4b3b-bbbe-8c236c74f5d3.png)
  
Para acceder a esta p? gina, vaya a **Investigate** \> **OAuth apps**. 
  
![En el portal de CAS de O365, elija investigar.](media/8c7b87c9-71a6-4952-adb2-185e941ffe9a.png)
  
[Administrar aplicaciones de OAuth con Office 365 Cloud App Security](manage-app-permissions-in-ocas.md)
  
## <a name="cloud-discovery-dashboard"></a>Panel de detección en la nube

El **Panel de detección**en la nube, también conocido como **detección de aplicaciones de productividad**, muestra información sobre el uso de aplicaciones en la nube dentro de la organización. Puede ver información sobre las aplicaciones, los usuarios, el tráfico y las transacciones, entre otras cosas, con este panel. El panel de detección en la nube es similar a la siguiente imagen: 
  
![En el portal de Office 365 CAS, elija \> descubrir panel de detección en la nube](media/61269290-fd82-4d4b-8045-aea1ebc82287.png)
  
para acceder a este panel, en el portal de seguridad de aplicaciones de nube de Office 365, vaya al panel **descubra** \> detección en **la nube**. 
  
![En el portal de Office 365 CAS, elija descubrir](media/73b5299f-94b5-49dd-a00f-154d188eb2c5.png)
  
[Revisar los resultados de la detección de aplicaciones en Office 365 Cloud App Security](review-app-discovery-findings-in-ocas.md)
  
## <a name="next-steps"></a>Pasos siguientes

- Obtener los [casos de uso de seguridad y la guía de uso de Office 365 Cloud App](https://aka.ms/O365CASGuide)
    
- [Prepararse para Office 365 Cloud App Security](get-ready-for-office-365-cas.md)
    

