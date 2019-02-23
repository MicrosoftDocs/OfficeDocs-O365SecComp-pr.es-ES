---
title: Integrar el servidor SIEM con Office 365 Cloud App Security
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
ms.assetid: dd6d2417-49c4-4de6-9294-67fdabbf8532
description: Puede integrar su servidor de SIEM con Office 365 Cloud App Security. Lea este artículo para obtener información general sobre cómo funciona y cómo configurarlo.
ms.openlocfilehash: b4baeda3cb836c0b1aa528d29176bbf4321d1fe2
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/23/2019
ms.locfileid: "30215880"
---
# <a name="integrate-your-siem-server-with-office-365-cloud-app-security"></a>Integrar el servidor SIEM con Office 365 Cloud App Security
  
|Evaluación * *\>**|Planeación * *\>**|Implementación * *\>**|Uso * * * *|
|:-----|:-----|:-----|:-----|
|[Empezar a evaluar](office-365-cas-overview.md) <br/> |[Empezar a planear](get-ready-for-office-365-cas.md) <br/> |Ya está aquí.  <br/> [Siguiente paso](utilization-activities-for-ocas.md) <br/> |[Empezar a usar](utilization-activities-for-ocas.md) <br/> |
   
## <a name="overview-and-prerequisites"></a>Información general y requisitos previos

Puede integrar [Office 365 Cloud App Security](get-ready-for-office-365-cas.md) con su servidor de administración de eventos e información de seguridad (Siem) para habilitar el control centralizado de las alertas. Esto es especialmente ventajoso para las organizaciones que usan servicios en la nube y aplicaciones de servidor local. La integración con un servidor de SIEM permite que su equipo de seguridad Proteja mejor sus aplicaciones de Office 365 a la vez que mantiene un flujo de trabajo de seguridad usual mediante la automatización de determinados procedimientos de seguridad y la correlación entre eventos locales y basados en la nube.  
  
Cuando integre por primera vez su servidor de SIEM con Office 365 Cloud App Security, las alertas de los dos últimos días se reenvían al servidor de SIEM, así como todas las alertas desde entonces, según los filtros que seleccione. Además, si deshabilita esta característica durante un período prolongado, cuando vuelva a habilitarla, reenviará los últimos dos días de alertas y, a continuación, todas las alertas desde entonces.

### <a name="siem-integration-architecture"></a>Arquitectura de integración de SIEM

Un agente de SIEM se configura en la red de la organización. Cuando se implementa y configura, el agente de SIEM extrae los tipos de datos que se configuraron (alertas) con las API RESTful de seguridad de aplicación de nube de Office 365. A continuación, el tráfico se envía a través de un canal HTTPS cifrado en el puerto 443.
  
Cuando un agente de SIEM recupera datos de la seguridad de aplicación de nube de Office 365, envía los mensajes de syslog a su servidor de SIEM local mediante las configuraciones de red que se proporcionan durante la instalación (TCP o UDP con un puerto personalizado).

![Arquitectura de seguridad de aplicaciones de SIEM y nube](media/siem-architecture.png)

### <a name="supported-siem-servers"></a>Servidores SIEM admitidos

Office 365 Cloud App Security es compatible actualmente con los siguientes servidores SIEM:
- ArcSight de micro Focus
- CEF genérico

### <a name="prerequisites"></a>Requisitos previos

- Debe ser administrador global o administrador de seguridad para realizar las tareas descritas en este artículo. Consulte [permisos en el centro de seguridad &amp; y cumplimiento de Office 365](permissions-in-the-security-and-compliance-center.md)

- Debe tener habilitada la [seguridad de aplicación de nube de Office 365](turn-on-office-365-cas.md) para su organización.

- El [registro de auditoría](turn-audit-log-search-on-or-off.md) debe estar activado para Office 365

- Debe tener un servidor estándar que cumpla los siguientes requisitos para configurar la integración del servidor SIEM:
    - SO: Windows o Linux (puede ser una máquina virtual)
    - CPU: 2
    - Espacio en disco: 20 GB
    - RAM: 2 GB
    - [Java 8 de Oracle](http://www.oracle.com/technetwork/java/javase/downloads/index.html) instalado
    - Firewall configurado como se describe en [requisitos de red](https://docs.microsoft.com/cloud-app-security/network-requirements)

- Debe tener detalles sobre el **host syslog remoto** y el **número de Puerto Syslot**. Un administrador de red o un administrador de seguridad debe poder ayudarle a encontrar esa información. 

- Debe aceptar los términos de la [licencia de software](https://go.microsoft.com/fwlink/?linkid=862491) para descargar el [archivo jar](https://go.microsoft.com/fwlink/?linkid=838596) que necesitará para integrar su servidor de Siem.
 
## <a name="step-1-set-it-up-a-siem-agent-in-office-365-cloud-app-security"></a>Paso 1: configurar un agente de SIEM en Office 365 Cloud App Security

1. Vaya al portal de Cloud App Security ([https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)) e inicie sesión.
  
2. Haga clic en **configuración** \> de **extensiones de seguridad**y elija agentes de Siem.<br/>
![Elija Configuración > extensiones de seguridad](media/Settings-SecurityExtensions.png)

3. Elija **Agregar agente Siem**.<br/>![Elija Agregar agente SIEM.](media/SIEMAgents.png)
    
4. Elija **iniciar asistente**.<br/>![Obtener ayuda o iniciar el asistente](media/HelpOrWizard.png) 
    
5. En el paso **General** , especifique un nombre y **Seleccione el formato Siem** y establezca la **Configuración avanzada** que sea relevante para ese formato. A continuación, elija **siguiente**.<br/>![Especificar un nombre y un tipo](media/ChooseAgentTypeAndName.png)
    
6. En el paso **remoto de syslog** , especifique la dirección IP o el nombre de host del host de **syslog remoto** y el **número de Puerto syslog**. Seleccione TCP o UDP como protocolo syslog remoto. (Puede trabajar con el administrador de la red o con el administrador de seguridad para obtener estos detalles si no los tiene). A continuación, elija **siguiente**.<br/>![Especificar detalles de registro de registro remoto](media/ArcSightS1Syslog.png)
  
7. En el paso **tipos de datos** , realice una de las acciones siguientes y, a continuación, haga clic en **siguiente**:
    - Mantener la configuración predeterminada de **todas las alertas**<br/>O BIEN
    - Haga clic en **todas las alertas**y, a continuación, elija **filtros específicos**. Defina filtros para seleccionar los tipos de alertas que desea enviar a su servidor de SIEM.<br/>![Tipo de datos paso del asistente](media/ArcSightS1ExportOptions.png)
  
8. En la pantalla Enhorabuena, copie el token y guárdelo para más tarde.<br/>![Pantalla del agente de SIEM creada](media/SIEMAgentFinished.png) 

> [!IMPORTANT]
> En este punto, ha configurado un agente de SIEM en Office 365 Cloud App Security, pero la integración del servidor SIEM todavía no ha finalizado. Continúe con el paso siguiente para continuar con la integración del servidor de SIEM.

Después de hacer clic en cerrar y salir del asistente, en la pantalla extensiones de seguridad, puede ver el agente de SIEM que agregó en la tabla. Mostrará el estado **creado** hasta que se conecte más adelante.

![Agente de SIEM creado](media/SIEMAgentCreated.png)
    
## <a name="step-2-download-a-jar-file-and-run-it-on-your-siem-server"></a>Paso 2: descargar un archivo JAR y ejecutarlo en el servidor de SIEM

1. Descargue el [agente de Siem de Microsoft Cloud App Security](https://go.microsoft.com/fwlink/?linkid=838596) y descomprima la carpeta. (Debe aceptar los [términos de licencia del software](https://go.microsoft.com/fwlink/?linkid=862491) para poder continuar). 
    
2. Extraiga el archivo. jar de la carpeta ZIP y ejecútelo en el servidor de SIEM.
    
3. Después de ejecutar el archivo, ejecute el comando siguiente:<br/>
  ```
  java -jar mcas-siemagent-0.87.20-signed.jar [--logsDirectory DIRNAME] [--proxy ADDRESS[:PORT]] --token TOKEN
  ```
### <a name="important-notes"></a>Notas importantes

- El nombre de archivo puede variar en función de la versión del agente de SIEM. 

- Le recomendamos que ejecute el archivo JAR en el servidor de SIEM durante la configuración del servidor.

    - **Windows**: ejecutar como tarea programada, asegurándose de configurar la tarea para que **se ejecute tanto si el usuario inició sesión como si no** y borre la opción **detener la tarea si se ejecuta durante más de** .

    - **Linux**: agregue el comando ejecutar con un **&** al `rc.local` archivo. <br/>Ejemplo:<br/> 
    ```
    java -jar mcas-siemagent-0.87.20-signed.jar [--logsDirectory DIRNAME] [--proxy ADDRESS[:PORT]] --token TOKEN &
    ```

- Los parámetros entre corchetes [] son opcionales y solo deben usarse si proceden. Use las siguientes variables:

    - **DIRNAME** es la ruta de acceso al directorio que desea usar para los registros de depuración del agente local.

    - **Address [:P ORT]** es la dirección del servidor proxy y el puerto que usa el servidor para conectarse a Internet.

    - **Token** es el token del agente Siem que copió en el primer procedimiento.

    - Para obtener ayuda, escriba `-h`. 
  
## <a name="step-3-validate-that-the-siem-agent-is-working"></a>Paso 3: validar que el agente de SIEM funcione

1. Asegúrese de que el estado del agente de SIEM del portal de seguridad de aplicaciones de nube de Office 365 no se muestra como **error de conexión** o desconectado y de que no hay notificaciones de agente. ****<br/>Por ejemplo, aquí podemos ver que el servidor de SIEM está conectado:<br/>![Servidor de SIEM conectado](media/siem-connected.png)<br/>Y aquí podemos ver que el servidor de SIEM está desconectado:<br/>![Servidor de SIEM no conectado](media/siem-not-connected.png) 
  
2. En el servidor syslog/SIEM, asegúrese de que se ve que las alertas han llegado desde Office 365 Cloud App Security.
  
## <a name="what-the-logfiles-look-like"></a>Aspecto de los archivos de registro

Este es un ejemplo de archivo de registro de alertas que podría enviarse a un servidor de SIEM:

```
2017-07-15T20:42:30.531Z CEF:0|MCAS|SIEM_Agent|0.102.17|ALERT_CABINET_EVENT_MATCH_AUDIT|myPolicy|3|externalId=596a7e360c204203a335a3fb start=1500151350531 end=1500151350531 msg=Activity policy ''myPolicy'' was triggered by ''admin@box-contoso.com'' suser=admin@box-contoso.com destinationServiceName=Box cn1Label=riskScore cn1= cs1Label=portalURL cs1=https://cloud-app-security.com/#/alerts/596a7e360c204203a335a3fb cs2Label=uniqueServiceAppIds cs2=APPID_BOX cs3Label=relatedAudits cs3=1500151288183_acc891bf-33e1-424b-a021-0d4370789660 cs4Label=policyIDs cs4=59f0ab82f797fa0681e9b1c7

2017-07-16T09:36:26.550Z CEF:0|MCAS|SIEM_Agent|0.102.17|ALERT_CABINET_EVENT_MATCH_AUDIT|test-activity-policy|3|externalId=596b339b0c204203a33a51ae start=1500197786550 end=1500197786550 msg=Activity policy ''test-activity-policy'' was triggered by ''user@contoso.com'' suser=user@contoso.com destinationServiceName=Salesforce cn1Label=riskScore cn1= cs1Label=portalURL cs1=https://cloud-app-security.com/#/alerts/596b339b0c204203a33a51ae cs2Label=uniqueServiceAppIds cs2=APPID_SALESFORCE cs3Label=relatedAudits cs3=1500197720691_b7f6317c-b8de-476a-bc8f-dfa570e00349 cs4Label=policyIDs cs4=

2017-07-16T09:17:03.361Z CEF:0|MCAS|SIEM_Agent|0.102.17|ALERT_CABINET_EVENT_MATCH_AUDIT|test-activity-policy3|3|externalId=596b2fd70c204203a33a3eeb start=1500196623361 end=1500196623361 msg=Activity policy ''test-activity-policy3'' was triggered by ''admin@contoso.com'' suser=admin@contoso.com destinationServiceName=Office 365 cn1Label=riskScore cn1= cs1Label=portalURL cs1=https://cloud-app-security.com/#/alerts/596b2fd70c204203a33a3eeb cs2Label=uniqueServiceAppIds cs2=APPID_O365 cs3Label=relatedAudits cs3=1500196549157_a0e01f8a-e29a-43ae-8599-783c1c11597d cs4Label=policyIDs cs4=

2017-07-16T09:17:15.426Z CEF:0|MCAS|SIEM_Agent|0.102.17|ALERT_CABINET_EVENT_MATCH_AUDIT|test-activity-policy|3|externalId=596b2fd70c204203a33a3eec start=1500196635426 end=1500196635426 msg=Activity policy ''test-activity-policy'' was triggered by ''admin@contoso.com'' suser=admin@contoso.com destinationServiceName=Microsoft Office 365 admin center cn1Label=riskScore cn1= cs1Label=portalURL cs1=https://cloud-app-security.com/#/alerts/596b2fd70c204203a33a3eec cs2Label=uniqueServiceAppIds cs2=APPID_O365_PORTAL cs3Label=relatedAudits cs3=1500196557398_3e102b20-d9fa-4f66-b550-8c7a403bb4d8 cs4Label=policyIDs cs4=59f0ab35f797fa9811e9b1c7

2017-07-16T09:17:46.290Z CEF:0|MCAS|SIEM_Agent|0.102.17|ALERT_CABINET_EVENT_MATCH_AUDIT|test-activity-policy4|3|externalId=596b30200c204203a33a4765 start=1500196666290 end=1500196666290 msg=Activity policy ''test-activity-policy4'' was triggered by ''admin@contoso.com'' suser=admin@contoso.com destinationServiceName=Microsoft Exchange Online cn1Label=riskScore cn1= cs1Label=portalURL cs1=https://cloud-app-security.com/#/alerts/596b30200c204203a33a4765 cs2Label=uniqueServiceAppIds cs2=APPID_OUTLOOK cs3Label=relatedAudits cs3=1500196587034_a8673602-7e95-46d6-a1fe-c156c4709c5d cs4Label=policyIDs cs4=

2017-07-16T09:41:04.369Z CEF:0|MCAS|SIEM_Agent|0.102.17|ALERT_CABINET_EVENT_MATCH_AUDIT|test-activity-policy2|3|externalId=596b34b10c204203a33a5240 start=1500198064369 end=1500198064369 msg=Activity policy ''test-activity-policy2'' was triggered by ''user2@test15-adallom.com'' suser=user2@test15-adallom.com destinationServiceName=Google cn1Label=riskScore cn1= cs1Label=portalURL cs1=https://cloud-app-security.com/#/alerts/596b34b10c204203a33a5240 cs2Label=uniqueServiceAppIds cs2=APPID_33626 cs3Label=relatedAudits cs3=1500197996117_fd71f265-1e46-4f04-b372-2e32ec874cd3 cs4Label=policyIDs cs4=
```

Y este es otro ejemplo, esta vez en formato CEF:


|Nombre del campo CEF  | Descripción  |
|---------|---------|
|inícielo     | marca de hora de alerta        |
|centraliza     | marca de hora de alerta        |
|RT     | marca de hora de alerta        |
|msg     | Descripción de la alerta como se muestra en el portal de seguridad de aplicación de nube de Office 365        |
|suser     | usuario de asunto de alerta        |
|destinationServiceName     | la aplicación de origen de la alerta, como Office 365, SharePoint o OneDrive        |
|csLabel     | Varía (las etiquetas tienen distintos significados). Normalmente, las etiquetas se explican por sí mismas, como targetObjects.        |
|cs     | Información correspondiente a una etiqueta (como, por ejemplo, el usuario de destino de una alerta según el ejemplo de la etiqueta)        |

## <a name="additional-tasks-as-needed"></a>Tareas adicionales (según sea necesario)

Una vez que haya configurado el servidor de SIEM y lo haya integrado con Office 365 Cloud App Security, es posible que deba regenerar un token, editar un agente de SIEM o eliminar un agente de SIEM. En las secciones siguientes se describe cómo realizar estas tareas.

### <a name="regenerate-a-token"></a>Volver a generar un token

Si pierde el token, puede volver a generar uno. 

1. en Office 365 Cloud App Security[https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)portal (), elija **settings** > **security extensions**.

2. En la tabla, busque la fila del agente SIEM. 

3. Haga clic en los puntos suspensivos y, a continuación, elija **regenerar token**.<br/>![Regenere un token haciendo clic en los puntos suspensivos del agente de SIEM](media/04de368a-b88e-4a9c-a830-58025cb98db6.png)
  
### <a name="edit-a-siem-agent"></a>Edición de un agente de SIEM

1. en Office 365 Cloud App Security[https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)portal (), elija **settings** > **security extensions**.

2. Busque la fila del agente SIEM. 

3. Haga clic en los puntos suspensivos y, a continuación, elija **Editar**. (Si edita el agente SIEM, no es necesario volver a ejecutar el archivo. jar; se actualiza automáticamente).<br/>![Para editar el agente de SIEM, elija los puntos suspensivos y, a continuación, elija Editar.](media/96d0b362-3e0c-4dff-b2b4-d7af5b1bfb91.png)
  
### <a name="delete-a-siem-agent"></a>Eliminar un agente de SIEM

1. en Office 365 Cloud App Security[https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)portal (), elija **settings** > **security extensions**.

2. Busque la fila del agente SIEM. 

3. Haga clic en los puntos suspensivos y, a continuación, elija **eliminar**.<br/>![Para eliminar un agente de SIEM, elija los puntos suspensivos y, a continuación, elija Eliminar.](media/540b5bdf-5574-4ecc-a7b0-92a499a387d7.png)

  
## <a name="next-steps"></a>Pasos siguientes

- [Actividades de uso después de implementar Office 365 Cloud App Security](utilization-activities-for-ocas.md)
    
- [Revisar y realizar acciones en las alertas](review-office-365-cas-alerts.md)
    
- [Agrupar las direcciones IP para simplificar la administración](group-your-ip-addresses-in-ocas.md)
    

