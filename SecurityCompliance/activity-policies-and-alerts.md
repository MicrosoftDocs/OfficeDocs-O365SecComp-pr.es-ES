---
title: Directivas de actividad y alertas en Office 365 Cloud App Security
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 01/28/2019
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 367f25d3-10a0-4a91-bdae-70ebb7a79c98
description: Definir directivas de actividad con Office 365 Cloud App Security para configurar las alertas que se desencadenen cuando se produzcan actividades específicas o se produzcan con demasiada frecuencia. Mediante la configuración de directivas para desencadenar alertas, puede recibir notificaciones sobre actividades específicas y supervisarlas.
ms.openlocfilehash: cfa58182ea35551ca3a3807c23e09c9f87c7be82
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/23/2019
ms.locfileid: "30219770"
---
# <a name="activity-policies-and-alerts-in-office-365-cloud-app-security"></a>Directivas de actividad y alertas en Office 365 Cloud App Security

|Evaluación * *\>**|Planeación * *\>**|Implementación * *\>**|Uso * * * *|
|:-----|:-----|:-----|:-----|
|[Empezar a evaluar](office-365-cas-overview.md) <br/> |[Empezar a planear](get-ready-for-office-365-cas.md) <br/> |Ya está aquí.  <br/> [Siguiente paso](anomaly-detection-policies-in-ocas.md) <br/> |[Empezar a usar](utilization-activities-for-ocas.md) <br/> |
   
Con Office 365 Cloud App Security, las directivas de administración de nube avanzadas activan alertas para actividades específicas que ocurren o se producen con demasiada frecuencia. Por ejemplo, supongamos que un usuario intenta iniciar sesión en Office 365 y produce un error 70 veces en un minuto. SuPongamos que otro usuario descarga archivos de 7.000, o que parece que ha iniciado sesión en Canadá, cuando se supone que el usuario está en otra ubicación. O peor, supongamos que la cuenta de un usuario está en peligro y que un atacante está usando esa cuenta para acceder a las aplicaciones en la nube y a los datos confidenciales de la organización.
  
Si es [administrador global o administrador de seguridad](permissions-in-the-security-and-compliance-center.md), las alertas de actividad le notificarán cuando se produzcan eventos como estos. A continuación, puede realizar acciones específicas, como suspender una cuenta de usuario hasta que pueda investigar qué ha sucedido.
  
> [!NOTE]
> Las directivas de seguridad de aplicación de nube de Office 365 son distintas de [las directivas &amp; de alerta del centro de seguridad y cumplimiento de Office 365](alert-policies.md). Las directivas de actividad descritas en este artículo se definen en el portal de seguridad de aplicaciones en la nube de Office 365 y pueden ayudarle a administrar mejor el entorno de nube de su organización. 
  
## <a name="before-you-begin"></a>Antes de empezar

Asegúrese de que:
  
- Su organización tiene [Office 365 Cloud App Security](office-365-cas-overview.md)y el servicio está [activado](turn-on-office-365-cas.md).
    
- El [registro de auditoría](turn-audit-log-search-on-or-off.md) está activado para su entorno de Office 365. 
    
- Es administrador global o administrador de seguridad de Office 365.
    
## <a name="create-a-new-activity-policy"></a>Crear una nueva Directiva de actividad

1. Como administrador global o administrador de seguridad, vaya al portal de Cloud App Security ([https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)) e inicie sesión. <br>Esto le llevará a la página de directivas de seguridad de aplicación de Office 365 Cloud.<br>![Cuando vaya al portal de seguridad de la aplicación de nube de Office 365, empezará con la página de directivas.](media/5cb8833c-4e08-438c-bab3-91b5106f6f3f.png)
  
2. Haga clic en **crear Directiva**y, a continuación, seleccione **Directiva de actividad**.<br>![Al crear una directiva en las entidades de certificación de O365, puede elegir entre directivas de actividad y directivas de detección de anomalías.](media/79f34535-ddf9-4a5b-a0a3-8766bf9c174c.png)
  
3. En la página **crear Directiva de actividad** , especifique el nombre y la **Descripción**de la **Directiva** . Para basar la Directiva en una plantilla predeterminada, elija una en la lista **plantilla de directiva** o cree su propia Directiva sin usar una plantilla.<br>![Puede crear directivas de actividad con Office 365 Cloud App Security.](media/4083a76f-7074-4d6a-8200-6d76d49259d7.png)
  
4. Elija una **gravedad de directiva** (baja, media o alta) que mida lo seria que es si esta directiva desencadena una alerta. Esto le ayudará a filtrar las alertas cuando las esté revisando más adelante. 
    
5. Elija una **categoría** para esta Directiva. Esto le ayudará a filtrar y ordenar las alertas que se han desencadenado o a las directivas de grupo cuando las esté revisando para realizar cambios. 
    
6. Elija **filtros de actividad** para configurar otras acciones o métricas que desencadenarán una alerta basada en esta Directiva. 
    
7. En **parámetros de coincidencia de actividad**, especifique si una infracción de Directiva se desencadenará cuando una sola actividad coincida con los filtros o si se requiere un número determinado de actividades repetidas antes de la activación de la alerta.<br>Si selecciona la **actividad repetida**, especifique el número de actividades, el intervalo de tiempo y si la infracción se contará para un usuario dentro de una aplicación específica o para el mismo usuario con cualquier aplicación.
    
8. Opcionalmente, puede seleccionar **crear alerta** para crear alertas adicionales para recibir notificaciones de esta Directiva (por correo electrónico, mensaje de texto o ambos).<br>Asegúrate de **que tu proveedor de correo electrónico no bloquee `no-reply@cloudappsecurity.com`los correos electrónicos enviados desde **. 
  
9. Elija las **acciones** que se deben realizar cuando se desencadene una alerta para suspender al usuario o pedir al usuario que inicie sesión de nuevo en las aplicaciones de Office 365. 
    
10. Elija **crear** para finalizar la creación de la Directiva. 
    
## <a name="next-steps"></a>Pasos siguientes

- [Directivas de detección de anomalías](anomaly-detection-policies-in-ocas.md)
    
- [Integración del servidor de SIEM](integrate-your-siem-server-with-office-365-cas.md)
    
- [Revisar y realizar acciones en las alertas](review-office-365-cas-alerts.md)
    
- [Agrupar las direcciones IP para simplificar la administración](group-your-ip-addresses-in-ocas.md)
    

