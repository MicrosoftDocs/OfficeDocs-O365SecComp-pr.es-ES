---
title: Agrupar las direcciones IP para simplificar la administración en Office 365 Cloud App Security
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
ms.assetid: b5e1471c-1ad6-4bc5-9e75-ce791aee283c
description: Para identificar fácilmente los conjuntos de direcciones IP que usará en la seguridad de la aplicación de nube de Office 365, como las direcciones IP de oficina física, puede configurar grupos de intervalos de direcciones IP.
ms.openlocfilehash: 42a62d2dd9771fb7d3ac992f4e0f8b5f6826efe3
ms.sourcegitcommit: 7e2a0185cadea7f3a6afc5ddc445eac2e1ce22eb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/11/2019
ms.locfileid: "29603741"
---
# <a name="group-your-ip-addresses-to-simplify-management-in-office-365-cloud-app-security"></a>Agrupar las direcciones IP para simplificar la administración en Office 365 Cloud App Security
  
|Evaluación **\>**|Planeación de **\>**|Implementación **\>**|Utilización de ***|
|:-----|:-----|:-----|:-----|
|[Empezar a evaluar](office-365-cas-overview.md) <br/> |[Comenzar a planear](get-ready-for-office-365-cas.md) <br/> |¡Están aquí!  <br/> [Pasos siguientes](#next-steps) <br/> |[Iniciar utilizando](utilization-activities-for-ocas.md) <br/> |
   
Para identificar fácilmente los conjuntos de direcciones IP que usará en la seguridad de la aplicación de nube de Office 365, como las direcciones IP de oficina física, puede configurar grupos de intervalos de direcciones IP. Definición de estos intervalos permite etiquetar y clasificar y, a continuación, puede usar etiquetas y categorías para personalizar la forma en que la actividad de los registros y las alertas se muestren e investigarse.
  
Cada grupo de intervalos de IP se puede etiquetar con nombres de etiqueta que elija y, a continuación, las etiquetas se pueden clasificar en función de una lista predeterminada de categorías IP (por ejemplo, Corporate, administrativas, Risky y VPN). Se admiten las direcciones IPv4 e IPv6.
  
> [!NOTE]
> Debe ser un administrador global o administrador de seguridad para llevar a cabo los procedimientos descritos en este artículo. Para obtener más información, vea [permisos en la seguridad de Office 365 &amp; centro de cumplimiento](permissions-in-the-security-and-compliance-center.md). 
  
## <a name="to-set-up-an-ip-address-range-in-office-365-cloud-app-security"></a>Para configurar un intervalo de direcciones IP en la seguridad de la aplicación de nube de Office 365

1. Como administrador global o administrador de seguridad, vaya al portal de seguridad de la aplicación en la nube ([https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)) e iniciar sesión.
    
2. En la esquina superior derecha de la página, haga clic en **configuración de** \> **intervalos de direcciones IP**.<br>![En seguridad de la aplicación de nube de Office 365, elija Configuración para tener acceso a la configuración del sistema y de datos](media/f6c48ee3-39b4-4b5a-8252-b6493b7bcd3d.png)<br>
  
3. Haga clic en el botón nuevo, que se parece a un signo más ( **+**).
    
4. En la ventana de **intervalo de direcciones IP de nuevo** , especifique los valores siguientes: 
    
|**Campo o lista**|**Qué hacer**|
|:-----|:-----|
|**Nombre** <br/> |Use este campo para administrar la configuración y el intervalo de direcciones IP. (No verá este valor en los registros de actividades.)  <br/> |
|**Intervalos de direcciones IP** <br/> |Especifique un rango, con la notación de prefijo de red (también conocido como notación CIDR). Por ejemplo, 192.168.1.0/27 incluye el intervalo de valores 192.168.1.0 a través de 192.168.1.31 (ambos inclusive).  <br/> |
|**Ubicación** y **registrado ISP** <br/> |Especifique la ubicación y el proveedor de servicios de Internet (ISP) para el intervalo de direcciones IP. Esto invalida los campos públicos definidos para las direcciones, lo que resulta útil para los casos, como una dirección IP es la que se considera como públicamente en Irlanda, pero es realmente en los Estados Unidos  <br/> |
|**Tags** <br/> |Usar etiquetas para el nombre de los grupos de direcciones IP. (A diferencia del campo nombre, verá las etiquetas en los registros de actividad.) Escriba una palabra o frase que desea usar para una etiqueta. Puede agregar tantas etiquetas como desee para cada intervalo de direcciones IP. Y, si ya ha configurado una etiqueta y que desea agregar este intervalo de direcciones IP, elija de la lista de etiquetas actuales que aparecen como comience a escribir.  <br/> |
|**Categoría** <br/> | Asignar categorías a las etiquetas para que sea más fácil reconocer las actividades que provienen de determinadas direcciones IP. Elegir entre las siguientes opciones:<br/> **Administrativas** Todas las direcciones IP de los administradores.  <br/> **Proveedor de nube** La dirección IP de su servidor proxy en la nube.  <br/> **Corporativo** Todas las direcciones IP en la red interna, las sucursales y las direcciones móviles Wi-Fi.  <br/> **Arriesgar** Todas las direcciones IP que considere la posibilidad de ser arriesgado, tales como las direcciones IP sospechoso han visto en el pasado, las direcciones IP en las redes de sus competidores y así sucesivamente. De forma predeterminada, las categorías arriesgadas incluye dos etiquetas IP: **proxy anónimo** y los **términos de referencia** <br/> **VPN** Las direcciones IP que usan los trabajadores remotos.  <br/> |
   
7. Elija **Guardar**.
    
Después de configurar los intervalos de direcciones IP, tenga en cuenta que eventos futuros sólo se ven afectados por estos cambios.
  
## <a name="next-steps"></a>Pasos siguientes

- [Las alertas y las directivas de actividad](activity-policies-and-alerts.md)
    
- [Directivas de detección de anomalías](anomaly-detection-policies-in-ocas.md)
    
- [Integrar su servidor SIEM](integrate-your-siem-server-with-office-365-cas.md)
    
- [Revisar y realizar acciones sobre alertas en Office 365 Cloud App Security](review-office-365-cas-alerts.md)
    

