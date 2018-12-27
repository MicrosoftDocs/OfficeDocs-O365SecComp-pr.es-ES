---
title: Orígenes de datos y registros de tráfico Web para Office 365 Cloud App Security
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 12/26/2018
ms.audience: ITPro
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 290b02bf-a988-4fb9-88b2-34e408216ac8
description: Office 365 en la nube seguridad de la aplicación funciona con los registros del tráfico web desde una amplia gama de proveedores. Lea este artículo para obtener más información acerca de los registros de tráfico web y orígenes de datos admitidos para la seguridad de la aplicación de nube de Office 365.
ms.openlocfilehash: ab962e4a030d06c133ad9fc4aa62a60755793bc3
ms.sourcegitcommit: 25f72d20e76463c2f0a075dfc0116f00c934bd77
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/27/2018
ms.locfileid: "27447058"
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
  
En las secciones siguientes se enumeran los atributos necesarios y los requisitos adicionales para los registros de tráfico web para que funcione correctamente con seguridad de la aplicación de nube de Office 365.

### <a name="attributes"></a>Atributos

Office 365 en la nube seguridad de la aplicación no se puede mostrar o analizar los atributos que no se incluyen en los registros de tráfico web. Por ejemplo, formato de registro estándar de Cisco ASA del servidor de seguridad no tiene el número de bytes cargados por transacción, el nombre de usuario o una dirección URL de destino (sólo una dirección IP de destino). Por lo tanto, no se muestran esos atributos en datos de detección de la nube y se limita la visibilidad de las aplicaciones en la nube. Para los servidores de seguridad Cisco ASA, se debe establecer el nivel de información a 6. 

Los registros de tráfico web deben incluir los siguientes atributos:

- Fecha de la transacción
- IP de origen
- Usuario de origen (muy recomendado)
- Dirección IP de destino
- Dirección URL de destino (recomendado; Las direcciones URL de proporcionan una mayor precisión para la detección de aplicaciones en la nube que las direcciones IP)
- Cantidad total de datos (recomendado; información de datos es muy valioso)
- Cantidad de carga o descarga datos (recomendado; proporciona conocimientos acerca de la nube patrones de uso de la aplicación)
- Acción realizada (permitidos o bloqueados)

### <a name="additional-requirements"></a>Requisitos adicionales 

Además de incluir los atributos enumerados anteriormente en este artículo, los registros de tráfico web deben cumplir los siguientes requisitos:

- El origen de datos para los archivos de registro debe ser compatibles.
- El formato de que usan los archivos de registro debe coincidir con el formato estándar. Cuando se carga el archivo, detección de aplicación comprobará si esto.
- Los eventos en el registro deben haber tenido lugar no más de 90 días.
- El archivo de registro debe incluir información sobre el tráfico saliente que se puede analizar para la actividad de red.
  
## <a name="data-attributes-for-different-vendors"></a>Atributos de datos para distintos proveedores

La tabla siguiente resume la información de los registros del tráfico web de varios proveedores. **No olvide comprobar con su proveedor para obtener la información más actualizada.**


|                 Origen de datos                  |    Dirección URL de la aplicación de destino    |    IP de la aplicación de destino     |       Nombre de usuario       |      Origen IP       |    Tráfico total     |    Bytes cargados    |
|----------------------------------------------|----------------------|----------------------|----------------------|----------------------|----------------------|----------------------|
|                  Barracuda                   | <strong>Sí</strong> | <strong>Sí</strong> | <strong>Sí</strong> | <strong>Sí</strong> |          No          |          No          |
|                  Capa azul                   | <strong>Sí</strong> |          No          | <strong>Sí</strong> | <strong>Sí</strong> | <strong>Sí</strong> | <strong>Sí</strong> |
|                  Punto de control                  |          No          | <strong>Sí</strong> |          No          | <strong>Sí</strong> |          No          |          No          |
|              Cisco ASA (registro del sistema)              |          No          | <strong>Sí</strong> |          No          | <strong>Sí</strong> | <strong>Sí</strong> |          No          |
|           Cisco ASA con parte de su eficacia           | <strong>Sí</strong> | <strong>Sí</strong> | <strong>Sí</strong> | <strong>Sí</strong> | <strong>Sí</strong> | <strong>Sí</strong> |
|                  Cisco FWSM                  |          No          | <strong>Sí</strong> |          No          | <strong>Sí</strong> | <strong>Sí</strong> |          No          |
|              Cisco Ironport WSA              | <strong>Sí</strong> | <strong>Sí</strong> | <strong>Sí</strong> | <strong>Sí</strong> | <strong>Sí</strong> | <strong>Sí</strong> |
|                 Cisco Meraki                 | <strong>Sí</strong> | <strong>Sí</strong> |          No          | <strong>Sí</strong> |          No          |          No          |
|           Clavister NGFW (registro del sistema)            | <strong>Sí</strong> | <strong>Sí</strong> | <strong>Sí</strong> | <strong>Sí</strong> | <strong>Sí</strong> | <strong>Sí</strong> |
|                SonicWall (anteriormente Dell)                | <strong>Sí</strong> | <strong>Sí</strong> |          No          | <strong>Sí</strong> | <strong>Sí</strong> | <strong>Sí</strong> |
|            Arte digital i-filtro             | <strong>Sí</strong> | <strong>Sí</strong> | <strong>Sí</strong> | <strong>Sí</strong> | <strong>Sí</strong> | <strong>Sí</strong> |
|                  FortiGate                   |          No          | <strong>Sí</strong> |          No          | <strong>Sí</strong> | <strong>Sí</strong> | <strong>Sí</strong> |
|                 Juniper SRX                  |          No          | <strong>Sí</strong> |          No          | <strong>Sí</strong> | <strong>Sí</strong> | <strong>Sí</strong> |
|                 Juniper SSG                  |          No          | <strong>Sí</strong> | <strong>Sí</strong> | <strong>Sí</strong> | <strong>Sí</strong> | <strong>Sí</strong> |
|                  McAfee SWG                  | <strong>Sí</strong> |          No          |          No          | <strong>Sí</strong> | <strong>Sí</strong> | <strong>Sí</strong> |
|                    TMG MS                    | <strong>Sí</strong> |          No          | <strong>Sí</strong> | <strong>Sí</strong> | <strong>Sí</strong> | <strong>Sí</strong> |
|              Palo Alto Networks              |          No          | <strong>Sí</strong> | <strong>Sí</strong> | <strong>Sí</strong> | <strong>Sí</strong> | <strong>Sí</strong> |
|                    Sophos                    | <strong>Sí</strong> | <strong>Sí</strong> | <strong>Sí</strong> | <strong>Sí</strong> | <strong>Sí</strong> |          No          |
|                Calamar (común)                | <strong>Sí</strong> |          No          | <strong>Sí</strong> | <strong>Sí</strong> |          No          | <strong>Sí</strong> |
|                Calamar (nativo)                | <strong>Sí</strong> |          No          | <strong>Sí</strong> | <strong>Sí</strong> |          No          | <strong>Sí</strong> |
| Websense - informe de detalles de investigación (CSV) | <strong>Sí</strong> | <strong>Sí</strong> | <strong>Sí</strong> | <strong>Sí</strong> | <strong>Sí</strong> | <strong>Sí</strong> |
|    Websense - registro de actividad de Internet (CEF)    | <strong>Sí</strong> | <strong>Sí</strong> | <strong>Sí</strong> | <strong>Sí</strong> | <strong>Sí</strong> | <strong>Sí</strong> |
|                   Zscaler                    | <strong>Sí</strong> | <strong>Sí</strong> | <strong>Sí</strong> | <strong>Sí</strong> | <strong>Sí</strong> | <strong>Sí</strong> |
   
## <a name="supported-vendor-firewalls-and-proxies"></a>Los firewalls de proveedor compatibles y los servidores proxy

Seguridad de la aplicación en la nube Office 365 admite los siguientes firewalls y servidores proxy.
  
- Barracuda - Firewall de aplicación Web (W3C)  
- Azul a capa Proxy administrativos - registro de acceso (W3C)
- Punto de comprobación
- Cisco ASA Firewall (asegúrese de que establecer el nivel de información a 6)
- Cisco ASA con parte de su eficacia   
- Cisco IronPort WSA
- Cisco ScanSafe
- Cisco Merkai - registro de direcciones URL
- Clavister NGFW (registro del sistema)
- Arte digital i-filtro
- Fortinet Fortigate
- iboss seguro puerta de enlace de la nube
- Juniper SRX
- Juniper SSG
- McAfee Secure Web Gateway
- Microsoft Forefront Threat Management Gateway (W3C)
- Serie de Palo Alto Firewall
- SonicWALL (anteriormente Dell)   
- Sophos administrativos
- Sophos XG
- Sophos Cyberoam
- Calamar (común)
- Calamar (nativo)
- Informe de detalles de investigación de Websense - soluciones de seguridad Web - (CSV)
- Registro de actividad de Internet de Websense - soluciones de seguridad Web - (CEF)
- Zscaler
    
> [!NOTE]
> Si un origen de datos que desea usar no se incluye aquí, puede solicitar que agregarse a la detección de la aplicación. Para ello, si se está creando un informe, seleccione **otro** origen de **datos**. A continuación, escriba el nombre del origen de datos que está intentando cargar. Se podrá revisar el registro y le permiten conocer si se agrega compatibilidad para ese tipo de registro. Como alternativa, puede [definir un analizador personalizado](https://docs.microsoft.com/cloud-app-security/custom-log-parser) que coincide con el formato. 
  
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
   
## <a name="next-steps"></a>Siguientes pasos

- [Revisar y realizar acciones en las alertas](review-office-365-cas-alerts.md)
    
- [Crear informes de detección de aplicaciones](create-app-discovery-reports-in-ocas.md)
    
- [Revisar las conclusiones de detección de aplicaciones](review-app-discovery-findings-in-ocas.md)
    
- [Revise las actividades de uso de seguridad de la aplicación de nube de Office 365](utilization-activities-for-ocas.md)
    

