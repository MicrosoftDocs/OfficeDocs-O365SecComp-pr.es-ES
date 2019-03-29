---
title: Revisar y realizar acciones sobre alertas en Office 365 Cloud App Security
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
ms.assetid: 97e9c3d9-df89-458e-924b-369becee5532
description: Use la página Alertas de Office 365 Cloud App Security para ver posibles problemas y emprender acciones. Puede omitir o resolver las alertas y, si es necesario, suspender una cuenta de usuario.
ms.openlocfilehash: 701d80c3f890115c6c403fff21d2d0444d71c95a
ms.sourcegitcommit: 1658be51e2c21ed23bc4467a98af74300a45b975
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/26/2019
ms.locfileid: "30862472"
---
# <a name="review-and-take-action-on-alerts-in-office-365-cloud-app-security"></a>Revisar y realizar acciones sobre alertas en Office 365 Cloud App Security
  
|Evaluación * *\>**|Planeación * *\>**|Implementación * *\>**|Uso * * * *|
|:-----|:-----|:-----|:-----|
|[Empezar a evaluar](office-365-cas-overview.md) <br/> |[Empezar a planear](get-ready-for-office-365-cas.md) <br/> |[Iniciar la implementación](turn-on-office-365-cas.md) <br/> |Ya está aquí.  <br/> [Siguientes pasos](#next-steps) <br/> |
   
Puede usar la página de alertas de Office 365 Cloud App Security para ver posibles problemas y, si es necesario, realizar una acción.
  
> [!NOTE]
> Debe ser administrador global o administrador de seguridad para realizar las tareas de este artículo. Consulte [permisos en el centro de seguridad &amp; y cumplimiento de Office 365](permissions-in-the-security-and-compliance-center.md). 
  
## <a name="how-to-get-to-the-alerts-page"></a>Cómo obtener acceso a la página de alertas

1. Vaya al portal de Cloud App Security ([https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)) e inicie sesión.
  
2. En la barra de navegación en la parte superior de la pantalla, elija **alertas**.<br/>![En la página Alertas, puede ver las alertas que se han desencadenado y las acciones que se han llevado a cabo.](media/3b53d4c9-4b13-435d-8547-8c0f9ae6b914.png)
 
> [!NOTE]
> las alertas de Cloud App security también están visibles en el centro de cumplimiento de & de seguridad de Office 365 (vaya a **alertas** > **ver alertas**. Sin embargo, en este momento, debe resolver estas alertas en el portal de Cloud App Security y en el centro de cumplimiento de & de seguridad de Office 365. Para obtener más información, consulte [visualización de alertas de Cloud App Security](alert-policies.md#viewing-cloud-app-security-alerts)). 
 
## <a name="review-and-handle-alerts"></a>Revisar y controlar las alertas

Las alertas le ayudan a identificar actividades en su entorno de nube de Office 365 que quizá quiera investigar con más detalle. También puede optar por crear nuevas directivas o editar las existentes en función de las alertas que vea. Por ejemplo, si ve que un administrador inicia sesión desde una ubicación extraña, es posible que decida configurar una directiva que impida que los administradores inicien sesión en Office 365 desde determinadas ubicaciones.
  
> [!TIP]
> Puede filtrar las alertas por **categoría** o por **gravedad** para poder administrar las alertas más importantes en primer lugar. 
  
Para cada alerta, mire qué le causó para poder decidir qué acción llevar a cabo. Para ver más detalles sobre una alerta y emprender acciones como, por ejemplo, resolver la alerta o suspender una cuenta de usuario, elija la alerta para abrir una página de detalles. En la página detalles, puede revisar el registro de actividades, las cuentas y los usuarios que están relacionados con la alerta, y emprender acciones como las siguientes:
  
- **** Descartar Si la alerta era un falso positivo, se ha omitido. Opcionalmente, puede Agregar un comentario que explique por qué se ha desechado. 
    
- **Resolver alerta** Si la alerta se activó por una actividad que sabe que no es una amenaza, resuélvalo. Opcionalmente, puede Agregar un comentario que explique por qué lo resolvió. 
    
- **Suspender** Si sospecha que hay inicios de sesión no autorizados en una cuenta, por ejemplo, alguien que inicie sesión desde otro país cuando sepa que esa persona se encuentra físicamente en una oficina local, puede [suspender la cuenta](suspend-or-restore-an-account-in-ocas.md) mientras investiga el contenido que se está realizando. 
    
## <a name="next-steps"></a>Pasos siguientes

- [Investigar una actividad](investigate-an-activity-in-office-365-cas.md)
    
- [Suspender o restaurar una cuenta de usuario](suspend-or-restore-an-account-in-ocas.md)
    
- Ver una lista de los [orígenes de datos y los registros de tráfico web](web-traffic-logs-and-data-sources-for-ocas.md) admitidos
    
- Revisar las [actividades de uso de Office 365 Cloud App Security](utilization-activities-for-ocas.md)
    

