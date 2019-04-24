---
title: Prepararse para Office 365 Cloud App Security
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.date: 02/15/2019
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: d9ee4d67-f2b3-42b4-9c9e-c4529904990a
description: Introducción al uso de Office 365 Cloud App Security
ms.openlocfilehash: 89718adcbb7c77735db3009937d887e88d4a8bc3
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32254038"
---
# <a name="get-ready-for-office-365-cloud-app-security"></a>Prepararse para Office 365 Cloud App Security
  
|Evaluación * *\>**|Planeación * *\>**|Implementación * *\>**|Uso * * * *|
|:-----|:-----|:-----|:-----|
|[Empezar a evaluar](office-365-cas-overview.md) <br/> |Ya está aquí.  <br/> [Siguiente paso](turn-on-office-365-cas.md) <br/> |[Iniciar la implementación](turn-on-office-365-cas.md) <br/> |[Empezar a usar](utilization-activities-for-ocas.md) <br/> |
   
Cuando se prepara para activar e implementar Office 365 Cloud App Security para su organización, hay algunas cosas que debe tener en cuenta. Use este artículo como guía para planear Office 365 Cloud App Security.
    
## <a name="step-1-identify-and-protect-your-global-and-security-administrator-accounts"></a>Paso 1: identificar y proteger las cuentas de administrador global y de seguridad

Los administradores globales, los administradores de seguridad y los lectores de seguridad pueden acceder al portal de seguridad de aplicaciones de nube de Office 365 para ver las directivas, revisar las alertas y usar los informes. Los administradores globales y los administradores de seguridad pueden definir directivas y emprender otras acciones para proteger a su organización. (Para obtener más información, consulte perMissions [in the &amp; Office 365 Security Compliance Center](permissions-in-the-security-and-compliance-center.md)). Revise las cuentas de usuario de su organización que tienen permisos elevados como precaución. 
  
 **[Proteja sus cuentas de administrador global de Office 365](https://docs.microsoft.com/office365/enterprise/protect-your-global-administrator-accounts)**. 
  
## <a name="step-2-turn-on-audit-logging-for-your-organization"></a>Paso 2: activar el registro de auditoría de la organización

Para que Office 365 Cloud App Security funcione correctamente, el registro de auditoría debe estar activado. Esto lo suele hacer un administrador de Exchange online o un administrador global.
  
 **[Active o desactive la búsqueda de registros de auditoría de Office 365](turn-audit-log-search-on-or-off.md)**. 
  
## <a name="step-3-go-to-the-office-365-cloud-app-security-portal"></a>Paso 3: ir al portal de seguridad de aplicaciones de nube de Office 365

Puede acceder al portal de seguridad de la aplicación de nube de Office 365 [https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com) visitando e iniciando sesión. 

También puede obtener acceso desde el centro de seguridad &amp; y cumplimiento de Office 365. Esta es una buena forma de hacerlo:

1. Vaya a [https://protection.office.com](https://protection.office.com) e inicie sesión. (Esto le llevará al centro de &amp; seguridad y cumplimiento).
    
2. Vaya a **alertas** \> para **Administrar alertas avanzadas**.
    
3. Elija **ir a office 365 Cloud App Security** para ir al portal de seguridad de aplicaciones en la nube de Office 365.<br> ![Elija Administrar alertas avanzadas para ir a Office 365 Cloud App Security](media/958632d4-03e3-4ade-8e22-d5509db6fca7.png)<br>Cuando vaya al portal de seguridad de la aplicación de nube de Office 365, la primera página que ve es la página directivas, que se asemeja a la siguiente imagen:<br>![Cuando vaya al portal de seguridad de la aplicación de nube de Office 365, empezará con la página de directivas.](media/5cb8833c-4e08-438c-bab3-91b5106f6f3f.png)<br>
  
## <a name="step-4-define-policies-and-set-up-alerts-amp-actions"></a>Paso 4: definir directivas y configurar acciones de &amp; alertas

Los administradores globales y los administradores de seguridad definen directivas en Office 365 Cloud App Security. Durante el proceso de definición de directivas, también se establecen alertas y acciones. Una alerta es una notificación basada en criterios que aparece en una vista o se envía por correo electrónico. 
  
Hay dos tipos de alertas en Office 365 Cloud App Security: alertas de detección de anomalías que detectan actividades sospechosas y alertas de actividad, que se definen para actividades que podrían ser atípicos para su organización. Las alertas notifican a los administradores globales y a los administradores de seguridad cuando hay una actividad en su entorno de Office 365 que es inusual para su organización.
  
Vea los siguientes recursos para obtener más información:
  
- [Directivas de actividad y alertas en Office 365 Cloud App Security](activity-policies-and-alerts.md)
    
- [Directivas de detección de anomalías en Office 365 Cloud App Security](anomaly-detection-policies-in-ocas.md)
    
- [Revisar y realizar acciones en las alertas de seguridad de la aplicación de nube de Office 365](review-office-365-cas-alerts.md)
    

## <a name="step-5-set-up-conditional-access-app-control"></a>Paso 5: configurar el control de aplicaciones de acceso condicional

Configure y aplique controles en las aplicaciones de la organización, en función de determinadas condiciones, como qué usuarios pueden usar las aplicaciones y dónde. Definir las directivas de sesión y acceso a la aplicación de usuario para determinar si los documentos confidenciales se pueden descargar y cifrar, bloquear el acceso a determinadas aplicaciones, configurar el modo de solo lectura para determinadas aplicaciones y restringir las sesiones de usuario de las redes no corporativas.

Vea los siguientes recursos para obtener más información:

- [Proteger aplicaciones con el Control de aplicaciones de acceso condicional de Office 365 Cloud App Security](ocas-conditional-access-app-control.md)

- [Implementar el Control de aplicaciones de acceso condicional para las aplicaciones de Office 365](ocas-deploy-conditional-access-app-control.md)

## <a name="step-6-learn-about-your-organizations-cloud-usage"></a>Paso 6: información sobre el uso de la nube de la organización

Como administrador global, administrador de seguridad o lector de seguridad, puede obtener información sobre el uso de la nube de su organización mediante informes y un panel de detección en la nube (también denominado descubrimiento de aplicaciones de productividad). Este panel muestra información sobre los usuarios, las aplicaciones, el tráfico web y los niveles de riesgo.
  
![En el portal de Office 365 CAS, elija \> descubrir panel de detección en la nube](media/61269290-fd82-4d4b-8045-aea1ebc82287.png)
  
para ir al panel de detección de aplicaciones de productividad, en el portal de seguridad de aplicaciones de nube de Office 365, elija **descubrir** \> **panel de detección en la nube**.
  
![En el portal de Office 365 CAS, elija descubrir](media/73b5299f-94b5-49dd-a00f-154d188eb2c5.png)
  
Para rellenar los informes con la información que necesita, cargue los archivos de registro de los servidores proxy y los firewalls de su organización. Para obtener más información, vea los siguientes recursos:
  
- [Crear informes de detección de aplicaciones en Office 365 Cloud App Security](create-app-discovery-reports-in-ocas.md)
    
- [Revisar los resultados de la detección de aplicaciones en Office 365 Cloud App Security](review-app-discovery-findings-in-ocas.md)
    
## <a name="step-7-manage-apps-that-your-organization-is-using-to-access-office-365"></a>Paso 7: administrar las aplicaciones que su organización usa para obtener acceso a Office 365

Como administrador global o administrador de seguridad, puede administrar aplicaciones, como aplicaciones personalizadas o aplicaciones de terceros, que las personas de su organización usen en sus dispositivos con Office 365. Por ejemplo, supongamos que alguien ha descargado una aplicación personalizada que desea usar con Office 365. Puede revisar las aplicaciones que los usuarios usan, prohibir aplicaciones que no son de confianza o marcar aplicaciones como aprobadas para su seguimiento. [Administrar aplicaciones de OAuth con Office 365 Cloud App Security](manage-app-permissions-in-ocas.md).
  
## <a name="step-8-create-a-maintenance-plan"></a>Paso 8: crear un plan de mantenimiento

Una vez que haya configurado y configurado la seguridad de aplicaciones en la nube de Office 365, querrá realizar determinadas tareas de uso como administrador global de Office 365 o administrador de seguridad de su organización.
Al realizar estas tareas, le ayudará a asegurarse de que la seguridad de la aplicación de nube de Office 365 está configurada correctamente, a que las directivas están actualizadas y a su organización se obtienen valores de Office 365. Use este artículo como guía para ayudarle a planear estas tareas. Consulte [actividades de uso después de implementar Office 365 Cloud App Security](utilization-activities-for-ocas.md).

## <a name="optional-step-9-use-your-siem-server-with-office-365-cloud-app-security"></a>Opcional Paso 9: usar el servidor de SIEM con Office 365 Cloud App Security

¿Su organización usa un servidor de administración de eventos e información de seguridad (SIEM)? Office 365 Cloud App Security ahora puede integrarse con el servidor de SIEM para habilitar la supervisión centralizada de las alertas. La integración con un servicio de SIEM permite proteger mejor las aplicaciones de la nube y mantener el flujo de trabajo de seguridad habitual, automatizar los procedimientos de seguridad y correlacionar entre eventos locales y basados en la nube. El agente de SIEM se ejecuta en el servidor, extrae las alertas de la seguridad de la aplicación Cloud de Office 365 y las transmite a su servidor de SIEM. Consulte [integración de Siem con Office 365 Cloud App Security](integrate-your-siem-server-with-office-365-cas.md).
  
## <a name="next-steps"></a>Pasos siguientes

- [Activar la seguridad de aplicación de nube de Office 365](turn-on-office-365-cas.md)
    
- Pruebe nuestra [Guía del entorno de pruebas](https://docs.microsoft.com/office365/enterprise/cloud-app-security-for-your-office-365-dev-test-environment) para obtener una experiencia práctica en la que puede demostrar las características más eficaces de la seguridad de aplicaciones en la nube de Office 365 y crear una prueba de concepto. 
    

