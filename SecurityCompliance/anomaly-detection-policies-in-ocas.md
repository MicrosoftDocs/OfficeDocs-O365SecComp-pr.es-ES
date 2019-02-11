---
title: Directivas de detección de anomalías en Office 365 Cloud App Security
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 01/28/2019
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 88935b4e-dcb1-47f1-8aca-1bf8fb069db6
description: 'Las directivas de detección de anomalías de seguridad de la aplicación de nube de Office 365 usen algoritmos integrados para ayudar a descubrir posibles problemas. Debe tener la directiva de detección de anomalías de al menos un, que puede ajustar (al crearla) mediante el uso de filtros. '
ms.openlocfilehash: 5a6cf05b90b69045540bb7913124fe0d9e32f9a1
ms.sourcegitcommit: 7e2a0185cadea7f3a6afc5ddc445eac2e1ce22eb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/11/2019
ms.locfileid: "29612713"
---
# <a name="anomaly-detection-policies-in-office-365-cloud-app-security"></a>Directivas de detección de anomalías en Office 365 Cloud App Security

Administración avanzada de seguridad de Office 365 es ahora de seguridad de la aplicación de nube de Office 365.
  
|Evaluación **\>**|Planeación de **\>**|Implementación **\>**|Utilización de ***|
|:-----|:-----|:-----|:-----|
|[Empezar a evaluar](office-365-cas-overview.md) <br/> |[Comenzar a planear](get-ready-for-office-365-cas.md) <br/> |¡Están aquí!  <br/> [Paso siguiente](integrate-your-siem-server-with-office-365-cas.md) <br/> |[Iniciar utilizando](utilization-activities-for-ocas.md) <br/> |
   
A partir [de la seguridad de la aplicación de Microsoft en la nube versión 116](new-in-office-365-cas-2018.md#office-365-cloud-app-security-release-116), seguridad de la aplicación de nube de Office 365 incluye varias directivas de detección de anomalías predefinidos ("fuera de la caja") que incluyen usuario y análisis de comportamiento de entidad (UEBA) y una máquina de aprendizaje (ML).
  
![Para ver las directivas de detección de anomalías, elija Control \> directivas.](media/9663baa5-98bf-45e0-9458-6e572b43ec72.png)
  
Estas directivas de detección de anomalías proporcionan resultados inmediatos proporcionando detecciones de inmediatas, identificación de numerosas anomalías de comportamiento entre los usuarios y equipos y dispositivos conectados a la red. Además, las nuevas directivas exponen más datos desde el motor de detección de seguridad de la aplicación en la nube que le ayudarán a acelerar el proceso de investigación y contienen las amenazas en curso.
  
Como un administrador global de Office 365 o un administrador de seguridad, puede revisar y, si es necesario, revisar las directivas predeterminadas que están disponibles con seguridad de la aplicación de nube de Office 365.
  
 > [!IMPORTANT]
> Hay un período de aprendizaje inicial de siete (7) días durante el cual no se desencadenan alertas de comportamiento anómalo. El algoritmo de detección de anomalías está optimizado para reducir el número de alertas de falsos positivos. 
  
## <a name="before-you-begin"></a>Antes de empezar

Asegúrese de que:
  
- Su organización tiene la [Seguridad de la aplicación de Office 365 en la nube](office-365-cas-overview.md)y el servicio está [activado](turn-on-office-365-cas.md).
    
- [Registro de auditoría](turn-audit-log-search-on-or-off.md) está activado para el entorno de Office 365. 
    
- Es un administrador global o administrador de seguridad para Office 365.
    
## <a name="view-your-anomaly-detection-policies"></a>Ver las directivas de detección de anomalías

1. Como administrador global o administrador de seguridad, vaya al portal de seguridad de la aplicación en la nube ([https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)) e iniciar sesión.<br>Esto le llevará a la página de directivas de seguridad de aplicaciones de Office 365 en la nube.
    
2. En la lista **tipo** , seleccione **Directiva de detección de anomalías**.<br>La organización predeterminada (o los existentes) se muestran las directivas de detección de anomalías.<br>![Directivas de detección de anomalías en Office 365 Cloud App Security](media/2e0ee770-787a-4d4a-bea8-389dc765d4c6.png)
  
3. Seleccione una directiva para revisar o modificar su configuración.
    
4. Elija **Actualizar** para guardar los cambios. 
    
## <a name="learn-more-about-anomaly-detection-policies"></a>Encontrará más información acerca de las directivas de detección de anomalías

Directivas de detección de anomalías se habilitan automáticamente; Sin embargo, seguridad de la aplicación de nube de Office 365 tiene un período de aprendizaje inicial de siete días durante los que no todas las anomalías se generan alertas de detección. Después de que, en cada sesión se compara con la actividad, cuando los usuarios ya estaba activos, direcciones IP, dispositivos, etc. detectadas a través del mes pasado y la puntuación de riesgo de estas actividades. Estas detecciones forman parte del motor de detección de anomalías heurística que su entorno de perfiles y activa alertas con respecto a una línea de base que se ha aprendido en la actividad de su organización. Estas detecciones también aprovechan los algoritmos de aprendizaje de máquina diseñados para los usuarios y los patrones de inicio de sesión para reducir los falsos positivos de perfiles.
  
Anomalías se detectan mediante el examen de actividad del usuario. Se evalúa el riesgo mirando en más de 30 indicadores de riesgo diferentes, agrupados en varios factores de riesgo, como dirección IP arriesgado, errores de inicio de sesión, actividad de administración, cuentas inactivas, ubicación, imposible viajes, dispositivo y agente de usuario y tasa de actividad.
  
En función de los resultados de directivas, se desencadenan alertas de seguridad. Seguridad de la aplicación de Office 365 en la nube se busca en cada sesión de usuario en Office 365 y le avisa cada vez que ocurre algo que es diferente de la línea de base de la organización o de actividad regular de un usuario.
  
En la siguiente tabla se describe las directivas de detección de anomalías de forma predeterminada, lo que hacen y cómo funcionan.
  
|**Nombre de directiva de detección de anomalías**|**Funcionamiento**|
|:-----|:-----|
|Imposible viajes  <br/> |Identifica los dos actividades de usuario (es una sola o varias sesiones) que se originan desde ubicaciones geográficamente que sean dentro de un período de tiempo más corto que el tiempo habría tomado el usuario que viajar desde la ubicación de la primera a la segunda, que indica que un diferentes usuario está usando las mismas credenciales. Esta detección aprovecha una máquina algoritmo que omite evidentes "falsos positivos" que contribuyen a la condición de viajes imposible, como las redes privadas virtuales y ubicaciones que se usan con regularidad por otros usuarios en la organización de aprendizaje. La detección tiene un período de aprendizaje inicial de siete días durante el cual aprende patrón de actividad de un usuario nuevo.  <br/> |
|Actividad de país poco frecuentes  <br/> |Se considera más allá de las ubicaciones de actividad para determinar las ubicaciones de nuevo y poco frecuentes. El motor de detección de anomalías almacena información acerca de las ubicaciones anteriores utilizados por los usuarios de la organización. Se desencadena una alerta cuando se produce una actividad desde una ubicación que se no ha recientemente o nunca visitada por el usuario o por cualquier usuario de la organización.  <br/> |
|Actividad de direcciones IP anónimas  <br/> |Identifica que los usuarios ya estaba activos desde una dirección IP que se identificó como una dirección IP de proxy anónimo. Estos servidores proxy usados por las personas que desean ocultar la dirección IP de su dispositivo y se pueden usar para malintencionados. Esta detección aprovecha una máquina de aprendizaje algoritmo que reduce los "falsos positivos", como las direcciones IP mal con etiqueta que se usan con frecuencia por los usuarios de la organización.  <br/> |
|Actividad de direcciones IP sospechosas  <br/> |Identifica que los usuarios ya estaba activos desde una dirección IP que se ha identificado como arriesgado por Microsoft Threat inteligencia. Estas direcciones IP participan en las actividades malintencionadas, como Botnet C&amp;C y puede indicar la cuenta en peligro. Esta detección aprovecha una máquina de aprendizaje algoritmo que reduce los "falsos positivos", como las direcciones IP mal con etiqueta que se usan con frecuencia por los usuarios de la organización.  <br/> |
|Actividades poco habituales (por usuario)  <br/> | Identifica a los usuarios que realizan actividades poco habituales, tales como:  <br/>  --Varias descargas de archivos  <br/>  --Actividades de uso compartido de archivos  <br/>  --Actividades de eliminación de archivo  <br/>  --Actividades de suplantación  <br/>  --Las actividades administrativas  <br/>  Estas directivas buscar actividades dentro de una sola sesión con respecto a la línea de base aprendida, que podría indicar un intento de infracción. Estas detecciones sacar provecho de una máquina algoritmo que los perfiles de los usuarios inician sesión en el patrón de aprendizaje y reduce los falsos positivos. Estas detecciones forman parte del motor de detección de anomalías heurística que su entorno de perfiles y activa alertas con respecto a una línea de base que se ha aprendido en la actividad de su organización.  <br/> |
|Varios intentos de inicio de sesión con errores  <br/> |Identifica a los usuarios que no se pudo varios intentos de inicio de sesión en una única sesión con respecto a la línea de base aprendido, lo que podría indicar un intento de infracción.  <br/> |
   
## <a name="triage-anomaly-detection-alerts"></a>Alertas de detección de anomalías de evaluación de errores

Como las alertas se incluyen, puede procesar dichas alertas rápidamente y determinar cuáles para tratar en primer lugar. Necesidad de contexto para una alerta le permite ver la imagen más grande y determinar si realmente está ocurriendo algo malintencionado. Use el procedimiento siguiente para empezar a explorar una alerta:
  
1. Como administrador global o administrador de seguridad, vaya al portal de seguridad de la aplicación en la nube ([https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)) e iniciar sesión. 
    
2. Elija **alertas** para ver sus avisos. 
    
3. Para obtener el contexto de una alerta, siga estos pasos:
    
4. Elija **investigar** \> **registro de actividad**.
    
5. Seleccione un elemento, como un usuario o dirección IP. Se abrirá el alimentador de conocimientos relevantes.<br>![En el registro de actividad, puede investigar una dirección IP.](media/32a727c5-e406-4fe2-9443-c1a7fb6628fc.png)
  
6. En el alimentador de perspectivas pertinentes, haga clic en un comando disponible, como un icono en la sección **Mostrar SIMILAR** .<br> ![Haga clic en el icono de reloj para ver las actividades realizadas dentro de una actividad seleccionada 48 horas](media/c6c96aa0-98e5-4205-8873-45f8d6fd0843.png)
  
7. Obtenga información sobre el elemento seleccionado al continuar utilizando explorar detalles para ese elemento.
    
Una alerta en múltiples inicios de sesión con errores de hecho posible sospechosa y puede indicar un posible ataque de fuerza bruta. Sin embargo, como una alerta también puede ser un error de configuración de aplicación, lo que provoca que la alerta sea un favorable positivo es true. Si ve una alerta de varios-error-inicios de sesión con las actividades de sospechosas adicionales, a continuación, hay una mayor probabilidad de que una cuenta se ve comprometida. Por ejemplo, suponga que una alerta de varios-error de inicio de sesión es seguida por actividad desde una dirección IP TOR y actividad de viajes imposible, ambos indicadores seguros de compromiso. Incluso es posible que vea que el mismo usuario realiza una actividad masivo descarga, que a menudo es un indicador de que el atacante realizando exfiltration de datos. Lo de cosas que puede explorar en Office 365 la seguridad de la aplicación de nube para ver y procesar las alertas y tomar medidas donde sea necesario.
  
## <a name="next-steps"></a>Pasos siguientes

- [Integrar su servidor SIEM](integrate-your-siem-server-with-office-365-cas.md)
    
- [Revisar y realizar acciones en las alertas](review-office-365-cas-alerts.md)
    
- [Las direcciones IP para simplificar la administración de grupo](group-your-ip-addresses-in-ocas.md)
    

