---
title: Crear informes de detección de aplicaciones con Office 365 Cloud App Security
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 1/28/2019
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 3e68e691-1fc4-4d3e-a2c0-d3134eb64055
description: Cree informes con Office 365 Cloud App Security que le permita conocer cómo los usuarios de su organización usan Office 365 y otras aplicaciones.
ms.openlocfilehash: 23165a52a09e5bcde46ee3ab2110dc17d0faf7f4
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32259648"
---
# <a name="create-app-discovery-reports-using-office-365-cloud-app-security"></a>Crear informes de detección de aplicaciones con Office 365 Cloud App Security

|Evaluación * *\>**|Planeación * *\>**|Implementación * *\>**|Uso * * * *|
|:-----|:-----|:-----|:-----|
|[Empezar a evaluar](office-365-cas-overview.md) <br/> |[Empezar a planear](get-ready-for-office-365-cas.md) <br/> |[Iniciar la implementación](turn-on-office-365-cas.md) <br/> |Ya está aquí.  <br/> [Siguientes pasos](#next-steps) <br/> |
   
Office 365 Cloud App Security ayuda a los administradores globales, a los administradores de seguridad y a los lectores de seguridad a obtener información sobre los servicios de nube que usan los usuarios de una organización. Por ejemplo, puede ver dónde los usuarios almacenan y colaboran en documentos y cuántos datos se cargan en aplicaciones o servicios que se encuentran fuera de Office 365.
  
Para generar un informe de detección de aplicaciones, cargue manualmente los archivos de registro de tráfico web desde sus firewalls y servidores proxy y, a continuación, Office 365 Cloud App Security analiza y analiza estos archivos para el informe.
  
> [!NOTE]
> Debe ser un administrador global, un administrador de seguridad o un lector de seguridad para realizar las tareas descritas en este artículo. Para obtener más información, consulte perMissions [in the &amp; Office 365 Security Compliance Center](permissions-in-the-security-and-compliance-center.md). 
  
## <a name="create-a-report-with-app-discovery"></a>Crear un informe con detección de aplicaciones

Para crear un informe de detección de aplicaciones, identifique el origen de datos del proveedor para los archivos de registro que desee analizar, seleccione los archivos de registro y, a continuación, solicite el informe.
  
> [!NOTE]
> Use los archivos de registro de tráfico web que incluyan períodos de tráfico máximos para obtener la mejor representación del uso en su organización. 
  
1. Recopilar los [registros de tráfico y los orígenes de datos Web para Office 365 Cloud App Security](web-traffic-logs-and-data-sources-for-ocas.md).
    
2. Vaya al portal de Cloud App Security ([https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)) e inicie sesión. 
       
3. Elija **descubrir** \> **crear nuevo informe**. <br>![En el portal de Office 365 CAS, elija descubrir](media/73b5299f-94b5-49dd-a00f-154d188eb2c5.png)<br>
  
4. Especifique un nombre y una descripción para el informe y, a continuación, seleccione el origen de datos para los registros de tráfico web en la lista **origen de datos** . <br>![En entidades de certificación de O365 \> , elija descubrir crear nuevo informe.](media/22e660f0-5eb2-49fa-9fea-f88a5809a07b.png)<br>Si no aparece un origen de datos que le gustaría usar, puede solicitar que se agregue. Seleccione **otro** para **origen de datos**y, a continuación, escriba el nombre del origen de datos que está intentando cargar. Revisaremos el registro y le indicaremos si se agrega compatibilidad para el origen de datos que lo generó. 
  
5. Vaya a la ubicación de los archivos de registro que recopiló y seleccione los archivos. Los archivos de registro deben haber sido generados por el origen de datos elegido para el informe.
    
6. Haga clic en **crear** para iniciar el proceso de creación de informes. 
    
7. Para ver el estado del informe, haga clic en **administrar informes**de instantáneas. Cuando un informe esté listo, verá la opción **Ver informe** . 
    
## <a name="next-steps"></a>Pasos siguientes

- [Revisar y realizar acciones en las alertas](review-office-365-cas-alerts.md)
    
- [Revisar los resultados de la detección de aplicaciones en Office 365 Cloud App Security](review-app-discovery-findings-in-ocas.md)
    
- Revisar las [actividades de uso de Office 365 Cloud App Security](utilization-activities-for-ocas.md)
    

