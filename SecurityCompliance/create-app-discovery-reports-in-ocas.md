---
title: Crear informes de detección de aplicaciones con Office 365 Cloud App Security
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 1/28/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 3e68e691-1fc4-4d3e-a2c0-d3134eb64055
description: Crear informes con Office 365 en la nube seguridad de la aplicación que permiten a comprender cómo las personas de su organización están usando Office 365 y otras aplicaciones.
ms.openlocfilehash: 543a194ec9d441a4feea97b8ad49022094565d7a
ms.sourcegitcommit: 7e2a0185cadea7f3a6afc5ddc445eac2e1ce22eb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/11/2019
ms.locfileid: "29603721"
---
# <a name="create-app-discovery-reports-using-office-365-cloud-app-security"></a>Crear informes de detección de aplicaciones con Office 365 Cloud App Security

Administración avanzada de seguridad de Office 365 es ahora de seguridad de la aplicación de nube de Office 365.
  
|Evaluación **\>**|Planeación de **\>**|Implementación **\>**|Utilización de ***|
|:-----|:-----|:-----|:-----|
|[Empezar a evaluar](office-365-cas-overview.md) <br/> |[Comenzar a planear](get-ready-for-office-365-cas.md) <br/> |[Iniciar la implementación](turn-on-office-365-cas.md) <br/> |¡Están aquí!  <br/> [Pasos siguientes](#next-steps) <br/> |
   
Seguridad de la aplicación en la nube Office 365 ayuda a los administradores globales, los administradores de seguridad y obtenga información sobre los servicios de nube de personas en una organización de lectores de seguridad. Por ejemplo, puede ver donde los usuarios se almacenar y colaborar en los documentos y la cantidad de datos se está cargando en aplicaciones o servicios que están fuera de Office 365.
  
Para generar un informe de detección de aplicaciones, cargar manualmente los archivos de registro del tráfico web desde los servidores de seguridad y los servidores proxy y, a continuación, la seguridad de la aplicación de nube de Office 365 analiza y analiza los archivos para el informe.
  
> [!NOTE]
> Debe ser un administrador global, Administrador de seguridad o lector de seguridad para llevar a cabo las tareas descritas en este artículo. Para obtener más información, vea [permisos en la seguridad de Office 365 &amp; centro de cumplimiento](permissions-in-the-security-and-compliance-center.md). 
  
## <a name="create-a-report-with-app-discovery"></a>Crear un informe con la detección de aplicaciones

Para crear un informe de detección de aplicaciones, identifique el origen de datos del proveedor para los archivos de registro que se desean analizado, seleccione los archivos de registro y, a continuación, solicitar el informe.
  
> [!NOTE]
> Use los archivos de registro de tráfico web que incluyen los períodos de tráfico para obtener la mejor representación de uso en su organización. 
  
1. Recopilar los [registros de tráfico web y orígenes de datos de seguridad de la aplicación de nube de Office 365](web-traffic-logs-and-data-sources-for-ocas.md).
    
2. Vaya al portal de seguridad de la aplicación en la nube ([https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)) e iniciar sesión. 
       
3. Elija **detección** \> **crear un nuevo informe**. <br>![En el portal de Office 365 CAS, elija detectar](media/73b5299f-94b5-49dd-a00f-154d188eb2c5.png)<br>
  
4. Especifique un nombre y una descripción para el informe y, a continuación, seleccione el origen de datos de sus registros de tráfico web en la lista de **origen de datos** . <br>![En Office 365 CAS, elija detectar \> crear nuevo informe](media/22e660f0-5eb2-49fa-9fea-f88a5809a07b.png)<br>Si un origen de datos que desea usar no aparece, puede solicitar que se agrega. Seleccione **otro** origen de **datos**y, a continuación, escriba el nombre del origen de datos que está intentando cargar. Se podrá revisar el registro de y le permiten conocer si se agrega compatibilidad para el origen de datos que lo generó. 
  
5. Vaya a la ubicación de los archivos de registro que recopilan y seleccione los archivos. Los archivos de registro deben haberse generados por el origen de datos que haya elegido para el informe.
    
6. Haga clic en **crear** para iniciar el proceso de creación de informes. 
    
7. Para ver el estado del informe, haga clic en **administrar los informes de instantáneas**. Cuando el informe está listo, verá la opción de **Ver el informe** . 
    
## <a name="next-steps"></a>Pasos siguientes

- [Revisar y realizar acciones en las alertas](review-office-365-cas-alerts.md)
    
- [Revisar los resultados de la detección de aplicaciones en Office 365 Cloud App Security](review-app-discovery-findings-in-ocas.md)
    
- Revise las [actividades de uso para la seguridad de la aplicación de nube de Office 365](utilization-activities-for-ocas.md)
    

