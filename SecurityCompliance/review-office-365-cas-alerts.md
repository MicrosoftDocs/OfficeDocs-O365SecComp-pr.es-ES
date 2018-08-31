---
title: Revisar y realizar acciones sobre alertas en Office 365 Cloud App Security
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 2/26/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 97e9c3d9-df89-458e-924b-369becee5532
description: Use la página alertas de seguridad de la aplicación de nube de Office 365 para ver posibles problemas y tomar medidas. Puede descartar o resolver las alertas y, si es necesario, suspender una cuenta de usuario.
ms.openlocfilehash: 62431adc73354e573978781f120a11746aef08d9
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22535584"
---
# <a name="review-and-take-action-on-alerts-in-office-365-cloud-app-security"></a>Revisar y realizar acciones sobre alertas en Office 365 Cloud App Security
  
|Evaluación **\>**|Planeación de **\>**|Implementación **\>**|Utilización de ***|
|:-----|:-----|:-----|:-----|
|[Empezar a evaluar](office-365-cas-overview.md) <br/> |[Comenzar a planear](get-ready-for-office-365-cas.md) <br/> |[Iniciar la implementación](turn-on-office-365-cas.md) <br/> |¡Están aquí!  <br/> [Pasos siguientes](#next-steps) <br/> |
   
Puede usar la página alertas de seguridad de la aplicación de nube de Office 365 para ver posibles problemas y, si es necesario, tomar medidas.
  
> [!NOTE]
> Debe ser un administrador global o administrador de seguridad para llevar a cabo las tareas de este artículo. Vea [permisos en la seguridad de Office 365 &amp; centro de cumplimiento](permissions-in-the-security-and-compliance-center.md). 
  
## <a name="how-to-get-to-the-alerts-page"></a>Cómo llegar a la página de alertas

1. Como administrador global o administrador de seguridad, vaya a [https://protection.office.com](https://protection.office.com) e iniciar sesión con su cuenta de trabajo o escuela. 
    
2. En la seguridad &amp; centro de cumplimiento, elija **alertas** \> **avanzada de administrar las alertas**.
    
3. Elija **Ir a la seguridad de la aplicación de Office 365 en la nube**.
    
    ![En la seguridad &amp; centro de cumplimiento, elija Administrar alertas avanzadas para ir a la seguridad de la aplicación de nube de Office 365](media/958632d4-03e3-4ade-8e22-d5509db6fca7.png)
  
4. En la barra de navegación a través de la parte superior de la pantalla, elija **alertas**.
    
    ![En la página alertas, puede ver las alertas que se activaron y todas las acciones realizadas.](media/3b53d4c9-4b13-435d-8547-8c0f9ae6b914.png)
  
## <a name="review-and-handle-alerts"></a>Revisión y controlar las alertas

Las alertas le ayudarán a identificar las actividades en el entorno de nube de Office 365 que es posible que desee investigar más. También es posible que decida crear nuevas directivas o edición de directivas existentes en función de las alertas que consulte. Por ejemplo, si ve un administrador de inicio de sesión desde una ubicación extraña, es posible que decida configurar una directiva que impide que los administradores de inicio de sesión en Office 365 de determinadas ubicaciones.
  
> [!TIP]
> Puede filtrar las alertas por **categoría** o por **gravedad** para que pueda administrar los más importantes en primer lugar. 
  
Para cada alerta, busque en la causa para que pueda decidir qué acción debe realizar. Para ver más detalles acerca de una alerta y tomar medidas, como la resolución de la alerta o suspender una cuenta de los usuarios, elija la alerta para abrir una página de detalles. En la página de detalles, puede revisar el registro de actividad, las cuentas y los usuarios que están relacionadas con la alerta y realizar acciones como las siguientes:
  
- **Descartar** Si la alerta era un falso positivo, cerrarlo. Opcionalmente, puede agregar un comentario que explique por qué se descarta. 
    
- **Resolver la alerta** Si la alerta se desencadenó por una actividad que sabe que no es una amenaza, resolverlo. Opcionalmente, puede agregar un comentario que explique por qué se ha resuelto. 
    
- **Suspender** Si sospecha que el inicio de sesión no autorizado ins en una cuenta, por ejemplo, alguien que inicie sesión desde otro país cuando sabe que esa persona es físicamente en una oficina local, puede [suspender la cuenta](suspend-or-restore-an-account-in-ocas.md) mientras investigar lo que está ocurriendo. 
    
## <a name="next-steps"></a>Pasos siguientes

- [Investigar una actividad](investigate-an-activity-in-office-365-cas.md)
    
- [Suspender o restauración de una cuenta de usuario](suspend-or-restore-an-account-in-ocas.md)
    
- Ver una lista de admitidos de [orígenes de datos y los registros de tráfico Web](web-traffic-logs-and-data-sources-for-ocas.md)
    
- Revise las [actividades de uso para la seguridad de la aplicación de nube de Office 365](utilization-activities-for-ocas.md)
    

