---
title: Prepararse para Office 365 Cloud App Security
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: ITPro
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: d9ee4d67-f2b3-42b4-9c9e-c4529904990a
description: Introducción al uso de la seguridad de la aplicación de nube de Office 365
ms.openlocfilehash: 1d1ae464278a5d9aafa5a176298f03174b6a37dc
ms.sourcegitcommit: 7e2a0185cadea7f3a6afc5ddc445eac2e1ce22eb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/11/2019
ms.locfileid: "29603701"
---
# <a name="get-ready-for-office-365-cloud-app-security"></a>Prepararse para Office 365 Cloud App Security
  
|Evaluación **\>**|Planeación de **\>**|Implementación **\>**|Utilización de ***|
|:-----|:-----|:-----|:-----|
|[Empezar a evaluar](office-365-cas-overview.md) <br/> |¡Están aquí!  <br/> [Paso siguiente](turn-on-office-365-cas.md) <br/> |[Iniciar la implementación](turn-on-office-365-cas.md) <br/> |[Iniciar utilizando](utilization-activities-for-ocas.md) <br/> |
   
Mientras se prepara para activar e implementar Office 365 en la nube seguridad de la aplicación (anteriormente conocido como administración avanzada de seguridad) para su organización, hay algunas cosas que debe tener en cuenta. Use este artículo como guía para planear la seguridad de la aplicación de nube de Office 365.
    
## <a name="step-1-identify-and-protect-your-global-and-security-administrator-accounts"></a>Paso 1: Identificar y proteger las cuentas de administrador global y seguridad

Los administradores globales, los administradores de seguridad y los lectores de seguridad pueden obtener acceso al portal de seguridad de la aplicación de nube de Office 365 para ver las directivas, revise las alertas y usar informes. Los administradores globales y los administradores de seguridad pueden definir directivas y realizar otras acciones para proteger su organización. (Para obtener más información, vea [permisos en la seguridad de Office 365 &amp; centro de cumplimiento](permissions-in-the-security-and-compliance-center.md).) Revise las cuentas de usuario de la organización que disponen de permisos elevados como medida de precaución. 
  
 **[Las cuentas de administrador global de proteger su Office 365](https://docs.microsoft.com/office365/enterprise/protect-your-global-administrator-accounts)**. 
  
## <a name="step-2-turn-on-audit-logging-for-your-organization"></a>Paso 2: Activar el registro de auditoría para la organización

En orden para Office 365 la seguridad de la aplicación de nube trabajar correcta, debe activarse el registro de auditoría. Normalmente, esto se realiza por un administrador de Exchange Online o un administrador global.
  
 **[Búsqueda de registro de auditoría de activar Office 365 activado o desactivado](turn-audit-log-search-on-or-off.md)**. 
  
## <a name="step-3-go-to-the-office-365-cloud-app-security-portal"></a>Paso 3: Vaya al portal de seguridad de la aplicación de nube de Office 365

Puede obtener el portal de seguridad de la aplicación de nube de Office 365, vaya a [https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com) e inicio de sesión. 

También puede obtener existe en la seguridad de Office 365 &amp; centro de cumplimiento. Aquí es una buena forma de hacerlo:

1. Vaya a [https://protection.office.com](https://protection.office.com) y el inicio de sesión. (Esto le llevará a la seguridad &amp; centro de cumplimiento.)
    
2. Vaya a **las alertas de** \> **avanzada de administrar las alertas**.
    
3. Elija **Ir a la seguridad de la aplicación de Office 365 en la nube** para ir al portal de seguridad de la aplicación de nube de Office 365.<br> ![Elija Administrar alertas avanzadas para ir a la seguridad de la aplicación de nube de Office 365](media/958632d4-03e3-4ade-8e22-d5509db6fca7.png)<br>Cuando vaya al portal de seguridad de la aplicación de nube de Office 365, la primera página que aparece es la página de directivas, que es similar a la siguiente imagen:<br>![Cuando vaya al portal de seguridad de la aplicación de nube de Office 365, empezar con la página de directivas](media/5cb8833c-4e08-438c-bab3-91b5106f6f3f.png)<br>
  
## <a name="step-4-define-policies-and-set-up-alerts-amp-actions"></a>Paso 4: Definir directivas y configurar las alertas de &amp; acciones

Los administradores globales y los administradores de seguridad definición directivas de seguridad de la aplicación de nube de Office 365. Durante el proceso de definición de las directivas, también se establecen las alertas y acciones. Una alerta es una notificación basada en los criterios que aparece en una vista o se envía a través de correo electrónico. 
  
Hay dos tipos de alertas de seguridad de la aplicación de Office 365 en la nube: alertas de detección de anomalías que detectan actividades sospechosas y alertas de actividad, que se definen para actividades que podrían ser atípicos para su organización. Las alertas de notificar a los administradores globales y los administradores de seguridad cuando hay una actividad en el entorno de Office 365 es poco habitual para su organización.
  
Vea los siguientes recursos para obtener más información:
  
- [Directivas de actividad y alertas en Office 365 Cloud App Security](activity-policies-and-alerts.md)
    
- [Directivas de detección de anomalías en Office 365 Cloud App Security](anomaly-detection-policies-in-ocas.md)
    
- [Revisar y realizar acciones en las alertas de seguridad de la aplicación de nube de Office 365](review-office-365-cas-alerts.md)
    
## <a name="step-5-learn-about-your-organizations-cloud-usage"></a>Paso 5: Información sobre el uso de la nube de su organización

Como administrador global, Administrador de seguridad o lector de seguridad, información sobre el uso de la nube de su organización a través de informes y un panel de detección de la nube (también denominado detección de aplicaciones de productividad). Este panel muestra información acerca de los usuarios, aplicaciones, el tráfico web y los niveles de riesgo.
  
![En el portal de Office 365 CAS, elija detectar \> panel de detección de la nube](media/61269290-fd82-4d4b-8045-aea1ebc82287.png)
  
Para ir al panel de detección de aplicaciones de productividad, en el portal de seguridad de la aplicación de nube de Office 365, elija **detectar** \> **panel de detección de la nube**.
  
![En el portal de Office 365 CAS, elija detectar](media/73b5299f-94b5-49dd-a00f-154d188eb2c5.png)
  
Para rellenar informes con la información que necesita, cargue los archivos de registro de los firewalls y servidores proxy de la organización. Para obtener más información, vea los siguientes recursos:
  
- [Crear informes de detección de aplicaciones en la seguridad de la aplicación de nube de Office 365](create-app-discovery-reports-in-ocas.md)
    
- [Revisar los resultados de la detección de aplicaciones en Office 365 Cloud App Security](review-app-discovery-findings-in-ocas.md)
    
## <a name="step-6-manage-apps-that-your-organization-is-using-to-access-office-365"></a>Paso 6: Administración de aplicaciones que su organización usa para el acceso a Office 365

Como administrador global o administrador de seguridad, puede administrar las aplicaciones, como aplicaciones personalizadas o las aplicaciones de terceros, que usan las personas de su organización en sus dispositivos con Office 365. Por ejemplo, suponga que alguien ha descargado una aplicación personalizada que deseen usar con Office 365. Puede revisar las aplicaciones que usan las personas, prohibir aplicaciones no confiables o marcar aplicaciones como aprobados para el seguimiento. [Aplicaciones de administración de OAuth con seguridad de la aplicación de nube de Office 365](manage-app-permissions-in-ocas.md).
  
## <a name="step-7-use-your-siem-server-with-office-365-cloud-app-security"></a>Paso 7: Utilizar el servidor SIEM con seguridad de la aplicación de nube de Office 365

¿La organización usa un servidor de administración (SIEM) de eventos e información de seguridad? Office 365 ahora puede integrar la seguridad de la aplicación en la nube con su servidor SIEM para habilitar la supervisión centralizada de alertas. Integración con un servicio SIEM permite proteger mejor sus aplicaciones de nube mientras se mantiene el flujo de trabajo de seguridad habituales, automatización de procedimientos de seguridad y correlacionar entre basados en la nube y locales eventos. El agente de SIEM se ejecuta en su servidor, extrae las alertas de seguridad de la aplicación de Office 365 en la nube y transmite las alertas en el servidor SIEM. Vea [integración de SIEM con seguridad de la aplicación de nube de Office 365](integrate-your-siem-server-with-office-365-cas.md).
  
## <a name="next-steps"></a>Pasos siguientes

- [Activar Office 365 Cloud App Security](turn-on-office-365-cas.md)
    
- Intente nuestra [Guía del laboratorio de pruebas](https://docs.microsoft.com/office365/enterprise/cloud-app-security-for-your-office-365-dev-test-environment) para una experiencia práctica donde puede demostrar las eficaces características de seguridad de la aplicación de Office 365 en la nube y crear una prueba de concepto. 
    

