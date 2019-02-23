---
title: Orígenes de datos y registros de tráfico Web para Office 365 Cloud App Security
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 12/26/2018
ms.audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 290b02bf-a988-4fb9-88b2-34e408216ac8
description: Office 365 Cloud App Security funciona con registros de tráfico web de una amplia gama de proveedores. Lea este artículo para obtener más información sobre los registros de tráfico web y los orígenes de datos compatibles para Office 365 Cloud App Security.
ms.openlocfilehash: 67246ded0e3d39c81b5b906f753b91298309d1d8
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/23/2019
ms.locfileid: "30218110"
---
# <a name="web-traffic-logs-and-data-sources-for-office-365-cloud-app-security"></a>Orígenes de datos y registros de tráfico Web para Office 365 Cloud App Security
  
|Evaluación * *\>**|Planeación * *\>**|Implementación * *\>**|Uso * * * *|
|:-----|:-----|:-----|:-----|
|[Empezar a evaluar](office-365-cas-overview.md) <br/> |[Empezar a planear](get-ready-for-office-365-cas.md) <br/> |[Iniciar la implementación](turn-on-office-365-cas.md) <br/> |Ya está aquí.  <br/> [Pasos siguientes](#next-steps) <br/> |
  
Puede usar una amplia variedad de archivos de registro de tráfico web y orígenes de datos con Office 365 Cloud App Security. Sin embargo, los archivos de registro de tráfico web deben incluir información específica y tener el formato de una determinada manera para que funcionen con los informes de detección de aplicaciones de Cloud App Security y el panel de detección en la nube. Use este artículo como guía de referencia para los registros de tráfico web y los orígenes de datos que va a usar con Office 365 Cloud App Security.
  
> [!NOTE]
> Debe ser administrador global, administrador de seguridad o lector de seguridad para obtener acceso al centro &amp; de seguridad y cumplimiento de Office 365 Cloud App Security portal. Consulte [permisos en el centro de seguridad &amp; y cumplimiento de Office 365](permissions-in-the-security-and-compliance-center.md). 
  
## <a name="web-traffic-log-requirements"></a>Requisitos del registro de tráfico web

Office 365 Cloud App Security usa datos en los registros de tráfico web para ayudarle a comprender qué aplicaciones usan las personas de su organización. Cuanto más detalles se incluyan en los archivos de registro, mejor será la visibilidad que tendrá en la actividad de los usuarios.
  
En las secciones siguientes se enumeran los atributos y los requisitos adicionales necesarios para que los registros de tráfico web funcionen correctamente con Office 365 Cloud App Security.

### <a name="attributes"></a>Atributos

Office 365 Cloud App Security no puede mostrar ni analizar atributos que no se incluyen en los registros de tráfico web. Por ejemplo, el formato de registro estándar de Firewall de Cisco ASA no tiene el número de bytes cargados por transacción, el nombre de usuario o una dirección URL de destino (solo una IP de destino). Por lo tanto, esos atributos no se muestran en los datos de detección en la nube y la visibilidad de las aplicaciones en la nube es limitada. Para los firewalls Cisco ASA, el nivel de información debe establecerse en 6. 

Los registros de tráfico web deben incluir los siguientes atributos:

- Fecha de la transacción
- IP de origen
- Usuario de origen (muy recomendado)
- Dirección IP de destino
- Dirección URL de destino (recomendada; Las direcciones URL proporcionan mayor precisión para la detección de aplicaciones en la nube que las direcciones IP)
- Cantidad total de datos (recomendado; la información de datos es muy valiosa)
- Cantidad de datos cargados o descargados (recomendado; proporciona información sobre los patrones de uso de aplicaciones en la nube)
- Acción emprendida (permitida o bloqueada)

### <a name="additional-requirements"></a>Requisitos adicionales 

Además de incluir los atributos enumerados anteriormente en este artículo, los registros de tráfico web deben cumplir los siguientes requisitos:

- El origen de datos para los archivos de registro debe ser compatible.
- El formato que usan los archivos de registro debe coincidir con el formato estándar. Cuando se cargue el archivo, la detección de la aplicación lo comprobará.
- Los eventos del registro deben haber tenido lugar más de 90 días.
- El archivo de registro debe incluir información de tráfico saliente que se pueda analizar para la actividad de red.
  
## <a name="data-attributes-for-different-vendors"></a>Atributos de datos para diferentes proveedores

En la tabla siguiente se resume la información de los registros de tráfico web de varios proveedores. **Asegúrese de consultar al proveedor para obtener la información más actualizada.**


|                 Origen de datos                  |    Dirección URL de la aplicación de destino    |    IP de la aplicación de destino     |       Nombre de usuario       |      IP de origen       |    Tráfico total     |    Bytes cargados    |
|----------------------------------------------|----------------------|----------------------|----------------------|----------------------|----------------------|----------------------|
|                  Barracuda Spam                   | <strong>Sí</strong> | <strong>Sí</strong> | <strong>Sí</strong> | <strong>Sí</strong> |          No          |          No          |
|                  Capa azul                   | <strong>Sí</strong> |          No          | <strong>Sí</strong> | <strong>Sí</strong> | <strong>Sí</strong> | <strong>Sí</strong> |
|                  Verifica                  |          No          | <strong>Sí</strong> |          No          | <strong>Sí</strong> |          No          |          No          |
|              Cisco ASA (syslog)              |          No          | <strong>Sí</strong> |          No          | <strong>Sí</strong> | <strong>Sí</strong> |          No          |
|           Cisco ASA con FirePOWER           | <strong>Sí</strong> | <strong>Sí</strong> | <strong>Sí</strong> | <strong>Sí</strong> | <strong>Sí</strong> | <strong>Sí</strong> |
|                  Cisco FWSM                  |          No          | <strong>Sí</strong> |          No          | <strong>Sí</strong> | <strong>Sí</strong> |          No          |
|              IronPort de Cisco para la WSA              | <strong>Sí</strong> | <strong>Sí</strong> | <strong>Sí</strong> | <strong>Sí</strong> | <strong>Sí</strong> | <strong>Sí</strong> |
|                 Cisco Meraki                 | <strong>Sí</strong> | <strong>Sí</strong> |          No          | <strong>Sí</strong> |          No          |          No          |
|           Clavister NGFW (syslog)            | <strong>Sí</strong> | <strong>Sí</strong> | <strong>Sí</strong> | <strong>Sí</strong> | <strong>Sí</strong> | <strong>Sí</strong> |
|                SonicWall (anteriormente Dell)                | <strong>Sí</strong> | <strong>Sí</strong> |          No          | <strong>Sí</strong> | <strong>Sí</strong> | <strong>Sí</strong> |
|            FILTRO i Digital Arts             | <strong>Sí</strong> | <strong>Sí</strong> | <strong>Sí</strong> | <strong>Sí</strong> | <strong>Sí</strong> | <strong>Sí</strong> |
|                  FortiGate                   |          No          | <strong>Sí</strong> |          No          | <strong>Sí</strong> | <strong>Sí</strong> | <strong>Sí</strong> |
|                 SRX de Juniper                  |          No          | <strong>Sí</strong> |          No          | <strong>Sí</strong> | <strong>Sí</strong> | <strong>Sí</strong> |
|                 Juniper de Juniper                  |          No          | <strong>Sí</strong> | <strong>Sí</strong> | <strong>Sí</strong> | <strong>Sí</strong> | <strong>Sí</strong> |
|                  McAfee SWG                  | <strong>Sí</strong> |          No          |          No          | <strong>Sí</strong> | <strong>Sí</strong> | <strong>Sí</strong> |
|                    MS TMG                    | <strong>Sí</strong> |          No          | <strong>Sí</strong> | <strong>Sí</strong> | <strong>Sí</strong> | <strong>Sí</strong> |
|              Redes palo alto              |          No          | <strong>Sí</strong> | <strong>Sí</strong> | <strong>Sí</strong> | <strong>Sí</strong> | <strong>Sí</strong> |
|                    Sophos                    | <strong>Sí</strong> | <strong>Sí</strong> | <strong>Sí</strong> | <strong>Sí</strong> | <strong>Sí</strong> |          No          |
|                Squid (común)                | <strong>Sí</strong> |          No          | <strong>Sí</strong> | <strong>Sí</strong> |          No          | <strong>Sí</strong> |
|                Squid (nativo)                | <strong>Sí</strong> |          No          | <strong>Sí</strong> | <strong>Sí</strong> |          No          | <strong>Sí</strong> |
| Websense-informe detallado de investigación (CSV) | <strong>Sí</strong> | <strong>Sí</strong> | <strong>Sí</strong> | <strong>Sí</strong> | <strong>Sí</strong> | <strong>Sí</strong> |
|    Websense-registro de actividad de Internet (CEF)    | <strong>Sí</strong> | <strong>Sí</strong> | <strong>Sí</strong> | <strong>Sí</strong> | <strong>Sí</strong> | <strong>Sí</strong> |
|                   Zscaler                    | <strong>Sí</strong> | <strong>Sí</strong> | <strong>Sí</strong> | <strong>Sí</strong> | <strong>Sí</strong> | <strong>Sí</strong> |
   
## <a name="supported-vendor-firewalls-and-proxies"></a>Servidores proxy y firewalls del proveedor admitidos

Office 365 Cloud App Security es compatible con los siguientes firewalls y servidores proxy.
  
- Barracuda-Firewall de la aplicación web (W3C)  
- Servidor proxy de acceso para azul estucado-registro de acceso (W3C)
- Punto de comprobación
- Servidor de seguridad Cisco ASA (Asegúrese de establecer el nivel de información en 6)
- Cisco ASA con FirePOWER   
- IronPort de Cisco para la WSA
- Cisco ScanSafe
- Cisco Merkai-URL log
- Clavister NGFW (syslog)
- FILTRO i Digital Arts
- Fortinet FortiGate
- Puerta de enlace de nube segura iboss
- SRX de Juniper
- Juniper de Juniper
- McAfee Secure Web Gateway
- Microsoft Forefront Threat Management Gateway (W3C)
- Firewall palo alto series
- SonicWALL (anteriormente Dell)   
- Sophos SG
- Sophos XG
- Sophos Cyberoam
- Squid (común)
- Squid (nativo)
- Websense-soluciones de seguridad Web-informe detallado de investigación (CSV)
- Websense-soluciones de seguridad Web-registro de actividad de Internet (CEF)
- Zscaler
    
> [!NOTE]
> Si no se incluye un origen de datos que le gustaría usar, puede solicitar que se agregue a la detección de aplicaciones. Para ello, cuando esté creando un informe, seleccione **otro** para origen de **datos**. A continuación, escriba el nombre del origen de datos que está intentando cargar. Revisaremos el registro y le indicaremos si agregamos soporte para ese tipo de registro. Como alternativa, puede [definir un analizador personalizado](https://docs.microsoft.com/cloud-app-security/custom-log-parser) que coincida con el formato. 
  
## <a name="troubleshoot-errors-when-log-files-are-uploaded"></a>Solucionar errores al cargar los archivos de registro

Después de cargar los archivos de registro de tráfico web, compruebe el registro de gobierno para ver si se ha producido algún error. Si hay errores, use la información de la siguiente tabla para resolver esos errores.
  
|**Error**|**Descripción**|**Solución**|
|:-----|:-----|:-----|
|Tipo de archivo no admitido  <br/> |El archivo cargado no es un archivo de registro válido. Por ejemplo, un archivo de imagen.  <br/> |Cargue un archivo de texto, ZIP o gzip que se exportó directamente desde el servidor de seguridad o el proxy.  <br/> |
|Error interno  <br/> |Se detectó un error interno en el recurso.  <br/> |Haga clic en **Reintentar** para volver a ejecutar la tarea.  <br/> |
|El formato del registro no coincide  <br/> |El formato de registro que cargó no coincide con el formato de registro esperado para este origen de datos.  <br/> |
Compruebe que el registro no esté dañado. Comparar y hacer coincidir el formato del archivo de registro con el formato de muestra que se muestra en la página de carga. |
|Las transacciones tienen más de 90 días de antigüedad  <br/> |Todas las transacciones tienen más de 90 días de antigüedad y, por lo tanto, se omiten.  <br/> |ExPorte un nuevo registro con eventos recientes y vuelva a cargarlo.  <br/> |
|No hay transacciones para catalogar aplicaciones en la nube  <br/> |En el registro no se encuentra ninguna transacción a ninguna aplicación en la nube reconocida.  <br/> |Compruebe que el registro contiene información de tráfico saliente.  <br/> |
|Tipo de registro no admitido  <br/> |Al seleccionar **origen de datos = otro (no admitido)**, no se analiza el registro. En su lugar, se envía para revisión al equipo técnico de [Microsoft Cloud App Security](https://aka.ms/whatiscas) .<br/> |El equipo técnico de [Microsoft Cloud App Security](https://aka.ms/whatiscas) crea un analizador dedicado para cada origen de datos. Los orígenes de datos más populares ya se admiten. Cuando se carga un origen de datos no admitido, se revisa y se agrega a la lista de posibles analizadores de orígenes de datos nuevos.<br/> Cuando se agrega un analizador nuevo a la característica, se incluye una notificación en las notas de la versión de seguridad de aplicaciones en la nube de Microsoft.  <br/> |
   
## <a name="next-steps"></a>Pasos siguientes

- [Revisar y realizar acciones en las alertas](review-office-365-cas-alerts.md)
    
- [Crear informes de detección de aplicaciones](create-app-discovery-reports-in-ocas.md)
    
- [Revisar las conclusiones de detección de aplicaciones](review-app-discovery-findings-in-ocas.md)
    
- [Revisar las actividades de uso de Office 365 Cloud App Security](utilization-activities-for-ocas.md)
    

