---
title: Directivas de actividad y alertas en Office 365 Cloud App Security
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 01/28/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 367f25d3-10a0-4a91-bdae-70ebb7a79c98
description: Definir directivas de actividad con Office 365 la seguridad de la aplicación de nube para configurar alertas para desencadenar cuando actividades específicas suceden o sucedería con demasiada frecuencia. Mediante la configuración de directivas para activar las alertas, puede recibir una notificación sobre y supervisar las actividades específicas.
ms.openlocfilehash: af364e7ff96f6d18b60d3267c5992d4c5533ea8c
ms.sourcegitcommit: 7e2a0185cadea7f3a6afc5ddc445eac2e1ce22eb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/11/2019
ms.locfileid: "29604097"
---
# <a name="activity-policies-and-alerts-in-office-365-cloud-app-security"></a>Directivas de actividad y alertas en Office 365 Cloud App Security

Administración avanzada de seguridad de Office 365 es ahora de seguridad de la aplicación de nube de Office 365.
  
|Evaluación **\>**|Planeación de **\>**|Implementación **\>**|Utilización de ***|
|:-----|:-----|:-----|:-----|
|[Empezar a evaluar](office-365-cas-overview.md) <br/> |[Comenzar a planear](get-ready-for-office-365-cas.md) <br/> |¡Están aquí!  <br/> [Paso siguiente](anomaly-detection-policies-in-ocas.md) <br/> |[Iniciar utilizando](utilization-activities-for-ocas.md) <br/> |
   
Con la seguridad de la aplicación de nube de Office 365, las directivas de administración de la nube avanzada activan las alertas para las actividades específicas que suceden o sucedería con demasiada frecuencia. Por ejemplo, supongamos que un usuario intenta iniciar sesión en Office 365 y se produce un error 70 veces en un minuto. Suponga que otro usuario descarga los archivos de 7.000 o parece que se conectan desde Canadá, cuando ese usuario debe para estar en otra ubicación. O bien, lo que es peor, suponga que se ha puesto en peligro la cuenta de otra persona, y un atacante usa esa cuenta para obtener acceso a aplicaciones de nube de su organización y los datos confidenciales.
  
Si es un [administrador global o administrador de seguridad](permissions-in-the-security-and-compliance-center.md), las alertas de actividad notificación cuando eventos como éstas se produce. A continuación, puede realizar acciones específicas, como la suspensión de una cuenta de usuario hasta que puede investigar qué ha ocurrido.
  
> [!NOTE]
> Son diferentes de las directivas de seguridad de la aplicación en la nube de Office 365 [las directivas de la seguridad de Office 365 de la alerta &amp; centro de cumplimiento](alert-policies.md). La actividad de las directivas que se describen en este artículo se definen en el portal de seguridad de la aplicación de nube de Office 365 y pueden ayudarle a una mejor administración de entorno de nube de su organización. 
  
## <a name="before-you-begin"></a>Antes de empezar

Asegúrese de que:
  
- Su organización tiene la [Seguridad de la aplicación de Office 365 en la nube](office-365-cas-overview.md)y el servicio está [activado](turn-on-office-365-cas.md).
    
- [Registro de auditoría](turn-audit-log-search-on-or-off.md) está activado para el entorno de Office 365. 
    
- Es un administrador global o administrador de seguridad para Office 365.
    
## <a name="create-a-new-activity-policy"></a>Crear una nueva directiva de actividad

1. Como administrador global o administrador de seguridad, vaya al portal de seguridad de la aplicación en la nube ([https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)) e iniciar sesión. <br>Esto le llevará a la página de directivas de seguridad de aplicaciones de Office 365 en la nube.<br>![Cuando vaya al portal de seguridad de la aplicación de nube de Office 365, empezar con la página de directivas](media/5cb8833c-4e08-438c-bab3-91b5106f6f3f.png)
  
2. Haga clic en **Crear directiva**y, a continuación, seleccione **Directiva de actividad**.<br>![Cuando se crea una directiva en O365 CAS, puede elegir entre las directivas de la actividad y detección de anomalías.](media/79f34535-ddf9-4a5b-a0a3-8766bf9c174c.png)
  
3. En la página **Crear directiva de actividad** , especifique el **nombre de la directiva** y la **Descripción**. Para basar la directiva en una plantilla predeterminada, elija uno en la lista **plantilla de directiva** o crear su propia directiva sin utilizar una plantilla.<br>![Puede crear directivas de actividad con seguridad de la aplicación de nube de Office 365.](media/4083a76f-7074-4d6a-8200-6d76d49259d7.png)
  
4. Elija una **gravedad de directiva** (bajo, medio o alto) que mide el grado de gravedad es para usted si esta directiva desencadena una alerta. Esto le ayudará a filtrar alertas cuando está revisarlos más adelante. 
    
5. Elija una **categoría** para esta directiva. Esto le ayudará a filtrar y ordenar las alertas que se han desencadenado, o a las directivas de grupo cuando está revisando ellos para realizar cambios. 
    
6. Elija **filtros de actividad** para configurar otras acciones o métricas que se activarán una alerta en función de esta directiva. 
    
7. En la **actividad coinciden con los parámetros**, especifique si una infracción de la directiva se desencadenará cuando una sola actividad coincide con los filtros, o si es necesario un número especificado de actividades repetidas antes de la alertas desencadenadores.<br>Si selecciona **repetida actividad**, especifique el número de actividades, el plazo de tiempo, y si una infracción contarán para un usuario dentro de una aplicación específica o para el mismo usuario con cualquier aplicación.
    
8. De forma opcional, puede seleccionar **crear alerta** para crear alertas adicionales para que reciba notificaciones de esta directiva (a través de correo electrónico, mensaje de texto o ambos).<br>**Asegúrese de que su proveedor de correo electrónico no bloquea los correos electrónicos enviados desde `no-reply@cloudappsecurity.com` **. 
  
9. Elija las **acciones** que deben tomarse cuando se desencadena una alerta para suspender el usuario o requieren que el usuario iniciar sesión de nuevo a las aplicaciones de Office 365. 
    
10. Elija **crear** para terminar de crear la directiva. 
    
## <a name="next-steps"></a>Pasos siguientes

- [Directivas de detección de anomalías](anomaly-detection-policies-in-ocas.md)
    
- [Integrar su servidor SIEM](integrate-your-siem-server-with-office-365-cas.md)
    
- [Revisar y realizar acciones en las alertas](review-office-365-cas-alerts.md)
    
- [Las direcciones IP para simplificar la administración de grupo](group-your-ip-addresses-in-ocas.md)
    

