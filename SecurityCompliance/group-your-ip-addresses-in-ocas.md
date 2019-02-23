---
title: Agrupar las direcciones IP para simplificar la administración en Office 365 Cloud App Security
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
ms.assetid: b5e1471c-1ad6-4bc5-9e75-ce791aee283c
description: Para identificar fácilmente los conjuntos de direcciones IP que va a usar en Office 365 Cloud App Security, como las direcciones IP de la oficina física, puede configurar grupos de intervalos de direcciones IP.
ms.openlocfilehash: b8f5c1dd46b2e3990d53a65881d12ca8f3961b16
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/23/2019
ms.locfileid: "30220450"
---
# <a name="group-your-ip-addresses-to-simplify-management-in-office-365-cloud-app-security"></a>Agrupar las direcciones IP para simplificar la administración en Office 365 Cloud App Security
  
|Evaluación * *\>**|Planeación * *\>**|Implementación * *\>**|Uso * * * *|
|:-----|:-----|:-----|:-----|
|[Empezar a evaluar](office-365-cas-overview.md) <br/> |[Empezar a planear](get-ready-for-office-365-cas.md) <br/> |Ya está aquí.  <br/> [Pasos siguientes](#next-steps) <br/> |[Empezar a usar](utilization-activities-for-ocas.md) <br/> |
   
Para identificar fácilmente los conjuntos de direcciones IP que va a usar en Office 365 Cloud App Security, como las direcciones IP de la oficina física, puede configurar grupos de intervalos de direcciones IP. La definición de estos intervalos le permite etiquetar y clasificarlos, y luego puede usar etiquetas y categorías para personalizar la forma en que se muestran y se investigan las alertas y los registros de actividad.
  
Cada grupo de intervalos IP se puede etiquetar con los nombres de etiqueta que elija y, a continuación, las etiquetas se pueden clasificar según una lista predeterminada de categorías IP (como corporativo, administrativo, arriesgado y VPN). Se admiten las direcciones IPv4 e IPv6.
  
> [!NOTE]
> Para llevar a cabo los procedimientos de este artículo, debe ser administrador global o administrador de seguridad. Para obtener más información, consulte perMissions [in the &amp; Office 365 Security Compliance Center](permissions-in-the-security-and-compliance-center.md). 
  
## <a name="to-set-up-an-ip-address-range-in-office-365-cloud-app-security"></a>Para configurar un intervalo de direcciones IP en Office 365 Cloud App Security

1. Como administrador global o administrador de seguridad, vaya al portal de Cloud App Security ([https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)) e inicie sesión.
    
2. En la parte superior derecha de la página, haga clic en **intervalo de direcciones IP**de **configuración** \> .<br>![En O365 Cloud App Security, elija Configuración para acceder a la configuración del sistema y de los datos](media/f6c48ee3-39b4-4b5a-8252-b6493b7bcd3d.png)<br>
  
3. Haga clic en el botón nuevo, que se asemeja al signo **+** más ().
    
4. En la ventana **nuevo intervalo de direcciones IP** , especifique los siguientes valores: 
    
|**Campo o lista**|**Qué hacer**|
|:-----|:-----|
|**Nombre** <br/> |Use este campo para administrar la configuración y el intervalo de direcciones IP. (No verá este valor en los registros de actividades).  <br/> |
|**Intervalos de direcciones IP** <br/> |Especifique un rango con la notación de prefijo de red (también conocida como notación CIDR). Por ejemplo, 192.168.1.0/27 incluye el intervalo de valores 192.168.1.0 a 192.168.1.31 (inclusive).  <br/> |
|**Ubicación** y **ISP registrados** <br/> |Especifique la ubicación y el proveedor de servicios de Internet (ISP) para el intervalo de direcciones IP. Esto reemplaza los campos públicos definidos para las direcciones, lo que resulta útil para casos como, por ejemplo, una dirección IP que se considera públicamente en Irlanda pero que, en realidad, se encuentra en Estados Unidos.  <br/> |
|**Tags** <br/> |Use etiquetas para asignar un nombre a los grupos de direcciones IP. (A diferencia del campo nombre, verá etiquetas en los registros de actividad). Escriba la palabra o frase que desea usar para una etiqueta. Puede Agregar tantas etiquetas como desee para cada intervalo de direcciones IP. Si ya ha configurado una etiqueta y desea agregar este intervalo de direcciones IP, selecciónela en la lista de etiquetas actuales que aparecen al empezar a escribir.  <br/> |
|**Categoría** <br/> | Asigne categorías a las etiquetas para que sea más fácil reconocer las actividades que provienen de determinadas direcciones IP. Elija una de las siguientes opciones:<br/> **Administrativo** Todas las direcciones IP de los administradores.  <br/> **Proveedor de nube** La dirección IP de su proxy en la nube.  <br/> **Empresa** Todas las direcciones IP de la red interna, las sucursales y las direcciones de itinerancia de Wi-Fi.  <br/> **Peligroso** Las direcciones IP que considere arriesgadas, como las direcciones IP sospechosas que ha visto anteriormente, direcciones IP en las redes de la competencia, etc. De forma predeterminada, las categorías de riesgo incluyen dos etiquetas IP: **proxy anónimo** y **Tor** <br/> **VPN** Cualquier dirección IP que usen los trabajadores remotos.  <br/> |
   
7. Elija **Guardar**.
    
Después de configurar los intervalos de direcciones IP, tenga en cuenta que estos cambios solo afectarán a los eventos futuros.
  
## <a name="next-steps"></a>Pasos siguientes

- [Directivas y alertas de actividad](activity-policies-and-alerts.md)
    
- [Directivas de detección de anomalías](anomaly-detection-policies-in-ocas.md)
    
- [Integración del servidor de SIEM](integrate-your-siem-server-with-office-365-cas.md)
    
- [Revisar y realizar acciones sobre alertas en Office 365 Cloud App Security](review-office-365-cas-alerts.md)
    

