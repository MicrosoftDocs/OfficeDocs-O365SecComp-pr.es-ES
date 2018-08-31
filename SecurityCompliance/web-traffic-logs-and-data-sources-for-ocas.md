---
title: Orígenes de datos y registros de tráfico Web para Office 365 Cloud App Security
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 2/26/2018
ms.audience: ITPro
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 290b02bf-a988-4fb9-88b2-34e408216ac8
description: Office 365 en la nube seguridad de la aplicación funciona con los registros del tráfico web desde una amplia gama de proveedores. Lea este artículo para obtener más información acerca de los registros de tráfico web y orígenes de datos admitidos para la seguridad de la aplicación de nube de Office 365.
ms.openlocfilehash: 09b0358e0d8b9a6ed59393d8771237f7eaf8bb98
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22536291"
---
# <a name="web-traffic-logs-and-data-sources-for-office-365-cloud-app-security"></a>Orígenes de datos y registros de tráfico Web para Office 365 Cloud App Security
  
|Evaluación **\>**|Planeación de **\>**|Implementación **\>**|Utilización de ***|
|:-----|:-----|:-----|:-----|
|[Empezar a evaluar](office-365-cas-overview.md) <br/> |[Comenzar a planear](get-ready-for-office-365-cas.md) <br/> |[Iniciar la implementación](turn-on-office-365-cas.md) <br/> |¡Están aquí!  <br/> [Pasos siguientes](#next-steps) <br/> |
  
Puede usar una amplia variedad de orígenes de datos y archivos de registro del tráfico web con seguridad de la aplicación de nube de Office 365. Sin embargo, los archivos de registro del tráfico web deben incluir información específica y ser un formato determinado para que funcionen con informes de detección de aplicación de seguridad de la aplicación de Office 365 en la nube y el panel de detección de la nube. Use este artículo como guía de referencia para los registros de tráfico de web y orígenes de datos que usará con la seguridad de la aplicación de nube de Office 365.
  
> [!NOTE]
> Debe ser un administrador global, Administrador de seguridad o lector de seguridad para tener acceso a la seguridad &amp; portal centro de cumplimiento y seguridad de la aplicación de nube de Office 365. Vea [permisos en la seguridad de Office 365 &amp; centro de cumplimiento](permissions-in-the-security-and-compliance-center.md). 
  
## <a name="web-traffic-log-requirements"></a>Requisitos de registro del tráfico de Web

Están usando Office 365 datos de usos de seguridad de la aplicación en la nube en sus registros de tráfico web que le ayudarán a comprender qué aplicaciones de personas en su organización. Cuantos más detalles que se incluyen en los archivos de registro, el mejor visibilidad tendrá actividad del usuario.
  
En la siguiente tabla se enumera los requisitos y los atributos que son necesarios para que los registros de tráfico web para que funcione correctamente con seguridad de la aplicación de Office 365 en la nube:
  
|**Atributos**|**Requisitos adicionales **|
|:-----|:-----|
| Fecha de la transacción  <br/>  IP de origen  <br/>  Usuario de origen (recomendado)  <br/>  Dirección IP de destino  <br/>  Dirección URL de destino (recomendado: direcciones URL proporcionan una mayor precisión para la detección de aplicaciones en la nube que las direcciones IP)  <br/>  Cantidad total de datos (recomendados)  <br/>  Cantidad de carga o descarga datos (recomendado: proporciona información acerca de la nube patrones de uso de la aplicación)  <br/>  Acción realizada (permitidos o bloqueados)  <br/> | El origen de datos para los archivos de registro debe ser compatibles.  <br/>  El formato de que usan los archivos de registro debe coincidir con el formato estándar. Cuando se carga el archivo, detección de aplicación comprobará si esto.  <br/>  Los eventos en el registro deben haber tenido lugar no más de 90 días.  <br/>  El archivo de registro debe incluir información sobre el tráfico saliente que se puede analizar para la actividad de red.  <br/> |
   
Si los atributos no se incluyen en los registros que se cargan, seguridad de la aplicación de nube de Office 365 no se puede mostrar o analizar la información para usted. Por ejemplo, formato de registro estándar de Cisco ASA del servidor de seguridad no incluye la cantidad de bytes que se cargan por transacción, el nombre de usuario o una dirección URL de destino (sólo una dirección IP de destino). Debido a que no se encuentra dicha información en los archivos de registro de Cisco, seguridad de la aplicación de nube de Office 365 no incluirá al analizar el tráfico de red de su organización.
  
> [!NOTE]
> Para algunos tipos de servidores de seguridad, debe establecer un nivel de información para los registros de tráfico web incluir los atributos requeridos. Por ejemplo, los servidores de seguridad Cisco ASA deben tener el nivel de información establece en 6. Asegúrese de que confirmar que los servidores de seguridad se establecen para ofrecer la información correcta en los registros de tráfico web. 
  
## <a name="data-attributes-for-different-vendors"></a>Atributos de datos para distintos proveedores
<a name="BKMK_LogAndData"> </a>

La tabla siguiente resume la información de los registros del tráfico web de varios proveedores. **No olvide comprobar con su proveedor para obtener la información más actualizada.**
  
|**Origen de datos**|**Dirección URL de la aplicación de destino**|**IP de la aplicación de destino**|**Username**|**Origen IP**|**Tráfico total**|**Bytes cargados**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Barracuda  <br/> |**Sí** <br/> |**Sí** <br/> |**Sí** <br/> |**Sí** <br/> |No  <br/> |No  <br/> |
|Capa azul  <br/> |**Sí** <br/> |No  <br/> |**Sí** <br/> |**Sí** <br/> |**Sí** <br/> |**Sí** <br/> |
|Punto de control  <br/> |No  <br/> |**Sí** <br/> |No  <br/> |**Sí** <br/> |No  <br/> |No  <br/> |
|Cisco ASA  <br/> |No  <br/> |**Sí** <br/> |No  <br/> |**Sí** <br/> |**Sí** <br/> |No  <br/> |
|Cisco FWSM  <br/> |No  <br/> |**Sí** <br/> |No  <br/> |**Sí** <br/> |**Sí** <br/> |No  <br/> |
|Cisco Ironport WSA  <br/> |**Sí** <br/> |**Sí** <br/> |**Sí** <br/> |**Sí** <br/> |**Sí** <br/> |**Sí** <br/> |
|Cisco Meraki  <br/> |**Sí** <br/> |**Sí** <br/> |No  <br/> |**Sí** <br/> |No  <br/> |No  <br/> |
|Clavister NGFW (registro del sistema)  <br/> |**Sí** <br/> |**Sí** <br/> |**Sí** <br/> |**Sí** <br/> |**Sí** <br/> |**Sí** <br/> |
|Dell SonicWall  <br/> |**Sí** <br/> |**Sí** <br/> |No  <br/> |**Sí** <br/> |**Sí** <br/> |**Sí** <br/> |
|FortiGate  <br/> |No  <br/> |**Sí** <br/> |No  <br/> |**Sí** <br/> |**Sí** <br/> |**Sí** <br/> |
|Juniper SRX  <br/> |No  <br/> |**Sí** <br/> |No  <br/> |**Sí** <br/> |**Sí** <br/> |**Sí** <br/> |
|Juniper SSG  <br/> |No  <br/> |**Sí** <br/> |No  <br/> |**Sí** <br/> |**Sí** <br/> |**Sí** <br/> |
|McAfee SWG  <br/> |**Sí** <br/> |No  <br/> |No  <br/> |**Sí** <br/> |**Sí** <br/> |**Sí** <br/> |
|Meraki (Cisco)  <br/> |**Sí** <br/> |**Sí** <br/> |No  <br/> |**Sí** <br/> |No  <br/> |No  <br/> |
|Microsoft Threat Management Gateway  <br/> |**Sí** <br/> |No  <br/> |**Sí** <br/> |**Sí** <br/> |**Sí** <br/> |**Sí** <br/> |
|Palo Alto Networks  <br/> |**Sí** <br/> |**Sí** <br/> |**Sí** <br/> |**Sí** <br/> |**Sí** <br/> |**Sí** <br/> |
|Sophos  <br/> |**Sí** <br/> |**Sí** <br/> |**Sí** <br/> |**Sí** <br/> |**Sí** <br/> |No  <br/> |
|Calamar (común)  <br/> |**Sí** <br/> |No  <br/> |**Sí** <br/> |**Sí** <br/> |No  <br/> |**Sí** <br/> |
|Calamar (nativo)  <br/> |**Sí** <br/> |No  <br/> |**Sí** <br/> |**Sí** <br/> |No  <br/> |**Sí** <br/> |
|Websense - informe de detalles de investigación (CSV)  <br/> |**Sí** <br/> |**Sí** <br/> |**Sí** <br/> |**Sí** <br/> |**Sí** <br/> |**Sí** <br/> |
|Websense - registro de actividad de Internet (CEF)  <br/> |**Sí** <br/> |**Sí** <br/> |**Sí** <br/> |**Sí** <br/> |**Sí** <br/> |**Sí** <br/> |
|Zscaler  <br/> |**Sí** <br/> |**Sí** <br/> |**Sí** <br/> |**Sí** <br/> |**Sí** <br/> |**Sí** <br/> |
   
## <a name="supported-vendor-firewalls-and-proxies"></a>Los firewalls de proveedor compatibles y los servidores proxy
<a name="BKMK_Supported"> </a>

Seguridad de la aplicación en la nube Office 365 admite los siguientes firewalls y servidores proxy.
  
- Barracuda - Firewall de aplicación Web (W3C)
    
- Azul a capa Proxy administrativos - registro de acceso (W3C)
    
- Punto de comprobación
    
- Cisco ASA Firewall (tenga en cuenta que debe establecer el nivel de información en 6)
    
- Cisco IronPort WSA
    
- Cisco ScanSafe
    
- Cisco Merkai - registro de direcciones URL
    
- Dell Sonicwall
    
- Fortinet Fortigate
    
- Juniper SRX
    
- Juniper SSG
    
- McAfee Secure Web Gateway
    
- Microsoft Forefront Threat Management Gateway (W3C)
    
- Serie de Palo Alto Firewall
    
- Sophos administrativos
    
- Sophos Cyberoam
    
- Calamar (común)
    
- Calamar (nativo)
    
- Informe de detalles de investigación de Websense - soluciones de seguridad Web - (CSV)
    
- Registro de actividad de Internet de Websense - soluciones de seguridad Web - (CEF)
    
- Zscaler
    
> [!NOTE]
> Si un origen de datos que desea usar no se incluye aquí, puede solicitar que agregarse a la detección de la aplicación. Para ello, si se está creando un informe, seleccione **otro** origen de **datos**. A continuación, escriba el nombre del origen de datos que está intentando cargar. Se podrá revisar el registro y le permiten conocer si se agrega compatibilidad para ese tipo de registro. 
  
## <a name="troubleshoot-errors-when-log-files-are-uploaded"></a>Solucionar problemas cuando se cargan los archivos de registro

Después de cargar los archivos de registro del tráfico de web, compruebe el registro de gobierno para ver si hubo algún error. Si hay errores, use la información en la tabla siguiente para resolver esos errores.
  
|**Error**|**Descripción**|**Solución**|
|:-----|:-----|:-----|
|Tipo de archivo no compatibles  <br/> |El archivo cargado no es un archivo de registro válido. Por ejemplo, un archivo de imagen.  <br/> |Cargar un archivo gzip que se han exportado directamente desde el firewall o el proxy, zip o texto.  <br/> |
|Error interno  <br/> |Se detectó un error de recursos interno.  <br/> |Haga clic en **Reintentar** para volver a ejecutar la tarea.  <br/> |
|No coincide con el formato de registro  <br/> |El formato de registro que ha cargado no coincide con el formato esperado del registro para este origen de datos.  <br/> |
Compruebe que el registro no está dañado. Comparar y hacer coincidir el formato de archivo de registro para el formato de ejemplo que se muestra en la página de carga. |
|Las transacciones son más de 90 días de antigüedad  <br/> |Todas las transacciones son más de 90 días de antigüedad y por lo tanto, se están ignorando.  <br/> |Exportar un registro nuevo con eventos recientes y volver a cargarla.  <br/> |
|No hay transacciones para el catálogo de aplicaciones de nube  <br/> |No hay ninguna aplicación de nube reconocida de transacciones se encuentran en el registro.  <br/> |Compruebe que el registro contiene información sobre el tráfico saliente.  <br/> |
|Tipo de registro no compatible  <br/> |Al seleccionar **origen de datos = otros (no admitido)**, no se analiza el registro. En su lugar, se envía para su revisión en el equipo de técnicos de [Seguridad de la aplicación de Microsoft en la nube](https://aka.ms/whatiscas) .<br/> |El equipo de técnicos de [Seguridad de la aplicación de Microsoft en la nube](https://aka.ms/whatiscas) basa un analizador dedicado para cada origen de datos. Ya se admiten los orígenes de datos más populares. Cuando se carga un origen de datos no admitido, está revisado y se agrega a la lista de posibles nuevos analizadores de origen de datos.<br/> Cuando se agrega un nuevo analizador de la característica, se incluye una notificación en las notas de la versión de seguridad de la aplicación de Microsoft en la nube.  <br/> |
   
## <a name="next-steps"></a>Pasos siguientes

- [Revisar y realizar acciones en las alertas](review-office-365-cas-alerts.md)
    
- [Crear informes de detección de aplicaciones](create-app-discovery-reports-in-ocas.md)
    
- [Revisar las conclusiones de detección de aplicaciones](review-app-discovery-findings-in-ocas.md)
    
- [Revise las actividades de uso de seguridad de la aplicación de nube de Office 365](utilization-activities-for-ocas.md)
    

