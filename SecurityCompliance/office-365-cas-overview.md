---
title: Introducción a Office 365 Cloud App Security
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: ITPro
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MET150
- MOE150
ms.assetid: 81f0ee9a-9645-45ab-ba56-de9cbccab475
description: 'Seguridad de la aplicación en la nube Office 365 proporciona entendimiento actividad sospechosa en Office 365 por lo que puede investigar situaciones en las que son potencialmente problemáticas y, si es necesario, tomar medidas para resolver problemas de seguridad. '
ms.openlocfilehash: b146512c22cbe86ce3aef95c5916de6959341578
ms.sourcegitcommit: 2cf7f5bb282c971d33e00f65d9982a3f14aec74e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/27/2018
ms.locfileid: "26706404"
---
# <a name="overview-of-office-365-cloud-app-security"></a>Introducción a Office 365 Cloud App Security
  
|Evaluación **\>**|Planeación de **\>**|Implementación **\>**|Utilización de ***|
|:-----|:-----|:-----|:-----|
|¡Están aquí!  <br/> [Paso siguiente](get-ready-for-office-365-cas.md) <br/> |[Comenzar a planear](get-ready-for-office-365-cas.md) <br/> |[Iniciar la implementación](turn-on-office-365-cas.md) <br/> |[Iniciar utilizando](utilization-activities-for-ocas.md) <br/> |
   
> [!NOTE]
> Seguridad de la aplicación de Office 365 en la nube está disponible en Office 365 Enterprise E5. Si su organización usa otra suscripción de Office 365 Enterprise, seguridad de la aplicación de nube de Office 365 puede adquirirse como un complemento. (Como administrador global, en el centro de administración de Office 365, elija **facturación** \> **Agregar suscripciones**.) Para obtener más información, vea [Descripción del servicio Office 365 plataforma: seguridad de Office 365 &amp; centro de cumplimiento](https://technet.microsoft.com/en-us/library/dn933793.aspx) y [comprar o editar un complemento de Office 365 para profesionales](https://support.office.com/article/4e7b57d6-b93b-457d-aecd-0ea58bff07a6). 
  
Seguridad de la aplicación en la nube Office 365 proporciona una perspectiva de una actividad sospechosa en Office 365 por lo que puede investigar situaciones en las que son potencialmente problemáticas y, si es necesario, tomar medidas para resolver problemas de seguridad. Con la seguridad de la aplicación de nube de Office 365, puede recibir notificaciones de alertas desencadenadas para actividades atípicos o sospechosas, vea cómo se tiene acceso y se usa, los datos de la organización en Office 365 suspender las cuentas de usuario presenta actividad sospechosa y requieren a los usuarios iniciar sesión para aplicaciones de Office 365 después de que se haya desencadenado una alerta. Lea este artículo para obtener una visión general de las capacidades y características de seguridad de la aplicación de nube de Office 365.
  
    
## <a name="how-to-find-the-office-365-cloud-app-security-portal"></a>Cómo encontrar el portal de seguridad de la aplicación de nube de Office 365

> [!NOTE]
> Para obtener acceso al portal de seguridad de la aplicación de nube de Office 365, debe ser un administrador global, Administrador de seguridad o lector de seguridad. Para obtener más información, vea [permisos en la seguridad de Office 365 &amp; centro de cumplimiento](permissions-in-the-security-and-compliance-center.md). 
  
Puede obtener el portal de seguridad de la aplicación de nube de Office 365 a través de la seguridad de Office 365 &amp; centro de cumplimiento. Aquí es una buena forma de hacerlo:
  
1. Vaya a [https://security.microsoft.com](https://security.microsoft.com) e iniciar sesión con su cuenta de trabajo o escuela para Office 365. (Esto le llevará a la seguridad &amp; centro de cumplimiento.) 
    
2. En la seguridad &amp; centro de cumplimiento, elija **alertas** \> **avanzada de administrar las alertas**. <br/>![En la seguridad &amp; centro de cumplimiento, elija Administrar alertas avanzadas para ir a la seguridad de la aplicación de nube de Office 365](media/958632d4-03e3-4ade-8e22-d5509db6fca7.png)<br/>(Si no está habilitado aún seguridad de la aplicación de nube de Office 365, y debe ser un administrador global, [activar la seguridad de la aplicación de nube de Office 365](turn-on-office-365-cas.md).)
    
3. Elija **Ir a la seguridad de la aplicación de Office 365 en la nube**. 
    
## <a name="policies"></a>Policies

Office 365 funciona la seguridad de la aplicación en la nube con las directivas que se definen para su organización. Con la seguridad de la aplicación de nube de Office 365, su organización obtiene 10 directivas de detección de anomalías predefinidos y varias plantillas de directivas de actividad. Estas directivas están diseñadas para detectar anomalías general, identificar a los usuarios el registro de una dirección IP arriesgada, detectar actividades ransomware, detectar actividades de administrador de direcciones IP de no corporativos y mucho más.
  
![En el portal de entidades de certificación, elija Control \> plantillas para ver o crear plantillas de directiva](media/88f615b4-aa8a-480c-b239-323dfcd628e1.png)
  
Para ver o usar las plantillas de directiva, en el portal de seguridad de la aplicación de nube de Office 365, vaya al **Control** \> **plantillas**. 
  
![En el portal de O365 CAS, elija Control](media/287c2ea9-5172-4697-8e0e-b9ab654105bc.png)
  
Para obtener más información acerca de las directivas, vea los siguientes recursos:
  
- [Directivas de actividad y alertas en Office 365 Cloud App Security](activity-policies-and-alerts.md)
    
- [Directivas de detección de anomalías en Office 365 Cloud App Security](anomaly-detection-policies-in-ocas.md)
    
## <a name="alerts"></a>Alertas

Cuando se definen las directivas, alertas informan acerca de actividades sospechosas o atípicos que se detectaron. Para ver las alertas para la organización, elija **alertas** en la barra de navegación a través de la parte superior de la pantalla. 
  
![En la página alertas, puede ver las alertas que se activaron y todas las acciones realizadas.](media/3b53d4c9-4b13-435d-8547-8c0f9ae6b914.png)
  
Tal y como se desencadenan alertas puede revisarlos para obtener más información acerca de lo que está ocurriendo. A continuación, si la actividad es aún sospechosa, puede tomar medidas. Por ejemplo, puede notificar a un usuario sobre un problema, suspender un usuario de inicio de sesión en Office 365 o requieren un usuario iniciar sesión en aplicaciones de Office 365.
  
Para obtener más información acerca de las alertas, vea los siguientes recursos:
  
- [Directivas de actividad y alertas en Office 365 Cloud App Security](activity-policies-and-alerts.md)
    
- [Directivas de detección de anomalías en Office 365 Cloud App Security](anomaly-detection-policies-in-ocas.md)
    
- [Revisar y realizar acciones en las alertas de seguridad de la aplicación de nube de Office 365](review-office-365-cas-alerts.md)
    
## <a name="activity-logs"></a>Registros de actividad

Ver información acerca de las actividades del usuario en la página de registro de actividad de seguridad de la aplicación de nube de Office 365.
  
![En el portal de O365 CAS, elija investigar \> registro de actividad](media/ec19e77d-4e11-49fc-ab7c-0e8b0c29c93c.png)
  
Para tener acceso a esta página, en el portal de seguridad de la aplicación de nube de Office 365, vaya a **investigar** \> **registro de actividad**. 
  
![En el portal de O365 CAS, elija investigar.](media/8c7b87c9-71a6-4952-adb2-185e941ffe9a.png)
  
Puede usar los registros de tráfico web con seguridad de la aplicación de nube de Office 365, demasiado. Cuantos más detalles que se incluyen en los archivos de registro, la mejor visibilidad tendrá en la actividad del usuario. Puede usar los archivos de registro de Barracuda, capa azul, Check Point, Cisco, Clavister, Dell SonicWALL, Fortinet, Juniper, McAfee, Microsoft, Palo Alto, Sophos, Squid, Websence, Zscaler y mucho más.
  
[Obtenga información acerca de los orígenes de datos y los registros de tráfico web para seguridad de la aplicación de nube de Office 365](web-traffic-logs-and-data-sources-for-ocas.md)
  
## <a name="app-permissions"></a>Permisos de aplicación

Con Office 365 en la nube seguridad de la aplicación, puede permitir o impedir que los usuarios de la organización para usar aplicaciones de terceros que tienen acceso a datos en Office 365.
  
![En CAS de O365, puede tener acceso a la página Administrar permisos de aplicación en el menú investigar.](media/78272cda-986f-4b3b-bbbe-8c236c74f5d3.png)
  
Para llegar a esta página, vaya a **investigar** \> **permisos de aplicación**. 
  
![En el portal de O365 CAS, elija investigar.](media/8c7b87c9-71a6-4952-adb2-185e941ffe9a.png)
  
[Administrar permisos de aplicación con Office 365 Cloud App Security](manage-app-permissions-in-ocas.md)
  
## <a name="cloud-discovery-dashboard"></a>Panel de detección de la nube

El **Panel de la detección de la nube**, también conocida como **Detección de aplicaciones de productividad**, muestra información sobre el uso de la aplicación en la nube dentro de la organización. Puede ver información acerca de aplicaciones, los usuarios, el tráfico, las transacciones y más mediante este panel. El panel de detección en la nube es similar a la siguiente imagen: 
  
![En el portal de Office 365 CAS, elija detectar \> panel de detección de la nube](media/61269290-fd82-4d4b-8045-aea1ebc82287.png)
  
Para llegar a este panel, en el portal de seguridad de la aplicación de nube de Office 365, vaya a **descubrir** \> **panel de detección de la nube**. 
  
![En el portal de Office 365 CAS, elija detectar](media/73b5299f-94b5-49dd-a00f-154d188eb2c5.png)
  
[Revisar los resultados de la detección de aplicaciones en Office 365 Cloud App Security](review-app-discovery-findings-in-ocas.md)
  
## <a name="next-steps"></a>Pasos siguientes

- Obtenga la [Guía de uso y casos de uso de seguridad de aplicación de nube de Office 365](https://aka.ms/O365CASGuide)
    
- [Prepararse para Office 365 Cloud App Security](get-ready-for-office-365-cas.md)
    

