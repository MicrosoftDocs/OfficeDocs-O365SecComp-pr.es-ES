---
title: Directivas de detección de anomalías en Office 365 Cloud App Security
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 02/15/2019
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 88935b4e-dcb1-47f1-8aca-1bf8fb069db6
description: 'Las directivas de detección de anomalías de Office 365 Cloud App Security usan algoritmos integrados para ayudar a detectar posibles problemas. Debe tener al menos una directiva de detección de anomalías, que puede ajustar (cuando la crea) mediante filtros. '
ms.openlocfilehash: 5308af139a46dad0793ed7eedacab0aee62dcc6c
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32242883"
---
# <a name="anomaly-detection-policies-in-office-365-cloud-app-security"></a>Directivas de detección de anomalías en Office 365 Cloud App Security

|Evaluación * *\>**|Planeación * *\>**|Implementación * *\>**|Uso * * * *|
|:-----|:-----|:-----|:-----|
|[Empezar a evaluar](office-365-cas-overview.md) <br/> |[Empezar a planear](get-ready-for-office-365-cas.md) <br/> |Ya está aquí.  <br/> [Siguiente paso](ocas-conditional-access-app-control.md) <br/> |[Empezar a usar](utilization-activities-for-ocas.md) <br/> |
   
A partir de [Microsoft Cloud App Security release 116](new-in-office-365-cas-2018.md#office-365-cloud-app-security-release-116), Office 365 Cloud App Security incluye varias directivas de detección de anomalías predefinidas ("de fuera de la caja") que incluyen análisis de comportamiento de usuarios y entidades (UEBA) y aprendizaje de máquina (ml).
  
![Para ver las directivas de detección de anomalías, \> elija directivas de control.](media/9663baa5-98bf-45e0-9458-6e572b43ec72.png)
  
Estas directivas de detección de anomalías proporcionan resultados inmediatos al proporcionar detecciones inmediatas, dirigidas a numerosas anomalías de comportamiento en los usuarios y los equipos y dispositivos conectados a la red. Además, las nuevas directivas exponen más datos del motor de detección de seguridad de aplicaciones en la nube para ayudarle a acelerar el proceso de investigación y a contener amenazas en curso.
  
Como administrador global de Office 365 o administrador de seguridad, puede revisar y, si es necesario, revisar las directivas predeterminadas que están disponibles con Office 365 Cloud App Security.
  
 > [!IMPORTANT]
> Hay un período inicial de aprendizaje de siete (7) días durante el cual no se desencadenan alertas de comportamiento anómalo. El algoritmo de detección de anomalías está optimizado para reducir el número de alertas de falsos positivos. 
  
## <a name="before-you-begin"></a>Antes de empezar

Asegúrese de que:
  
- Su organización tiene [Office 365 Cloud App Security](office-365-cas-overview.md)y el servicio está [activado](turn-on-office-365-cas.md).
    
- El [registro de auditoría](turn-audit-log-search-on-or-off.md) está activado para su entorno de Office 365. 
    
- Es administrador global o administrador de seguridad de Office 365.
    
## <a name="view-your-anomaly-detection-policies"></a>Ver las directivas de detección de anomalías

1. Como administrador global o administrador de seguridad, vaya al portal de Cloud App Security ([https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)) e inicie sesión.<br>Esto le llevará a la página de directivas de seguridad de aplicación de Office 365 Cloud.
    
2. En la lista **tipo** , elija **Directiva de detección**de anomalías.<br>Se muestran las directivas de detección de anomalías predeterminadas de la organización (o existentes).<br>![Directivas de detección de anomalías en Office 365 Cloud App Security](media/2e0ee770-787a-4d4a-bea8-389dc765d4c6.png)
  
3. Seleccione una directiva para revisar o editar su configuración.
    
4. Elija **Actualizar** para guardar los cambios. 
    
## <a name="learn-more-about-anomaly-detection-policies"></a>Más información acerca de las directivas de detección de anomalías

Las directivas de detección de anomalías se habilitan automáticamente; sin embargo, Office 365 Cloud App Security tiene un período inicial de aprendizaje de siete días durante el cual no se producen todas las alertas de detección de anomalías. Después de esto, se compara cada sesión con la actividad, cuando los usuarios estaban activos, las direcciones IP, los dispositivos, etc. que se detectaron durante el último mes y la puntuación de riesgo de estas actividades. Estas detecciones forman parte del motor de detección de anomalías heurísticos que perfila el entorno y desencadena alertas con respecto a una línea base que se aprendió en la actividad de la organización. Estas detecciones también aprovechan los algoritmos de aprendizaje de máquina diseñados para generar perfiles de los usuarios y patrones de inicio de sesión para reducir los falsos positivos.
  
Las anomalías se detectan al analizar la actividad del usuario. El riesgo se evalúa examinando más de 30 indicadores de riesgo diferentes, agrupados en varios factores de riesgo, como direcciones IP peligrosas, errores de inicio de sesión, actividad de administrador, cuentas inactivas, ubicación, viajes imposibles, agente de usuario y de dispositivo y tasa de actividades.
  
En función de los resultados de la Directiva, se desencadenan alertas de seguridad. Office 365 Cloud App Security examina todas las sesiones de usuario en Office 365 y le avisa cuando ocurre algo que es diferente de la línea base de la organización o de la actividad regular de un usuario.
  
En la tabla siguiente se describen las directivas de detección de anomalías predeterminadas, lo que hacen y cómo funcionan.
  
|**Nombre de la Directiva de detección de anomalías**|**Funcionamiento**|
|:-----|:-----|
|Recorrido imPosible  <br/> |Identifica dos actividades de usuario (es una o varias sesiones) que se originan desde ubicaciones geográficamente lejanas dentro de un período de tiempo inferior al que habría llevado al usuario para viajar desde la primera ubicación hasta la segunda, lo que indica que hay otra el usuario usa las mismas credenciales. Esta detección aprovecha un algoritmo de aprendizaje de máquina que ignora los "falsos positivos" obvios que contribuyen a la condición de viajes imposibles de viajes, como VPN y ubicaciones que usan de forma regular otros usuarios de la organización. La detección tiene un período inicial de aprendizaje de siete días durante el cual aprende el patrón de actividad de un nuevo usuario.  <br/> |
|Actividad de país poco frecuente  <br/> |Tiene en cuenta las ubicaciones de la actividad pasadas para determinar ubicaciones nuevas e infrecuentes. El motor de detección de anomalías almacena información sobre las ubicaciones anteriores usadas por los usuarios de la organización. Una alerta se desencadena cuando se produce una actividad de una ubicación que no visitó recientemente o nunca visitó el usuario o cualquier usuario de la organización.  <br/> |
|Actividad de direcciones IP anónimas  <br/> |Identifica que los usuarios estaban activos desde una dirección IP que se identificó como una dirección IP de proxy anónimo. Estos proxies los usan las personas que quieren ocultar la dirección IP de su dispositivo, y pueden usarse con intenciones malintencionadas. Esta detección aprovecha un algoritmo de aprendizaje de la máquina que reduce los "falsos positivos", como las direcciones IP etiquetadas de manera generalizada que los usuarios de la organización usan ampliamente.  <br/> |
|Actividad de direcciones IP sospechosas  <br/> |Identifica que los usuarios estaban activos desde una dirección IP que Microsoft Threat Intelligence identificó como arriesgado. Estas direcciones IP están implicadas en actividades malintencionadas, como&amp;zombi c c, y pueden indicar una cuenta en peligro. Esta detección aprovecha un algoritmo de aprendizaje de la máquina que reduce los "falsos positivos", como las direcciones IP etiquetadas de manera generalizada que los usuarios de la organización usan ampliamente.  <br/> |
|Actividades inusuales (por usuario)  <br/> | Identifica a los usuarios que realizan actividades inusuales, como:  <br/>  --Varias descargas de archivos  <br/>  --Actividades de uso compartido de archivos  <br/>  --Actividades de eliminación de archivos  <br/>  --Actividades de suplantación  <br/>  --Actividades administrativas  <br/>  Estas directivas buscan actividades en una sola sesión con respecto a la línea base aprendida, lo que podría indicar en un intento de infracción. Estas detecciones aprovechan un algoritmo de aprendizaje de máquina que perfila a los usuarios en el patrón de inicio de sesión y reduce los falsos positivos. Estas detecciones forman parte del motor de detección de anomalías heurísticos que perfila el entorno y desencadena alertas con respecto a una línea base que se aprendió en la actividad de la organización.  <br/> |
|Varios intentos erróneos de inicio de sesión  <br/> |Identifica a los usuarios que no superaron los intentos de inicio de sesión en una sola sesión con respecto a la línea base aprendida, lo que podría indicar en un intento de infracción.  <br/> |
   
## <a name="triage-anomaly-detection-alerts"></a>Clasificar alertas de detección de anomalías

A medida que se presentan alertas, puede clasificar las alertas rápidamente y determinar cuáles se deben controlar en primer lugar. El hecho de tener contexto para una alerta le permite ver la imagen más grande y determinar si algo malintencionado está ocurriendo realmente. Use el siguiente procedimiento para empezar a explorar una alerta:
  
1. Como administrador global o administrador de seguridad, vaya al portal de Cloud App Security ([https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)) e inicie sesión. 
    
2. Elija **alertas** para ver sus alertas. 
    
3. Para obtener el contexto de una alerta, siga estos pasos:
    
4. Elija **investigar** \> **registro de actividades**.
    
5. Seleccione un elemento, como un usuario o una dirección IP. Se abrirá el cajón de información relevante.<br>![En el registro de actividades, puede investigar una dirección IP.](media/32a727c5-e406-4fe2-9443-c1a7fb6628fc.png)
  
6. En el cajón de información relevante, haga clic en un comando disponible, como un icono en la sección **Mostrar similar** .<br> ![Haga clic en el icono del reloj para ver las actividades realizadas en un plazo de 48 horas de una actividad seleccionada.](media/c6c96aa0-98e5-4205-8873-45f8d6fd0843.png)
  
7. Obtenga información sobre el elemento seleccionado; para ello, continúe explorando los detalles de ese elemento.
    
Una alerta en varios inicios de sesión erróneos podría ser sospechosa, y puede indicar un posible ataque por la fuerza bruta. Sin embargo, dicha alerta también puede ser un error de configuración de la aplicación, lo que provoca que la alerta sea un verdadero positivo. Si ve una alerta de varios errores de inicio de sesión con actividades sospechosas adicionales, es más probable que una cuenta esté en peligro. Por ejemplo, supongamos que una alerta de inicio de sesión múltiple que ha producido un error es seguida de una actividad de una dirección IP de TOR y de una actividad de viajes imposibles, ambos indicadores de peligro. Puede incluso ver que el mismo usuario ha realizado una actividad de descarga masiva, que suele ser un indicador del atacante que realiza la exfiltración de datos. Se trata de algo como que puede explorar en Office 365 Cloud App Security para ver y clasificar las alertas y realizar una acción cuando sea necesario.
  
## <a name="next-steps"></a>Pasos siguientes

- [Implementar el Control de aplicaciones de acceso condicional para las aplicaciones de Office 365](ocas-deploy-conditional-access-app-control.md)

- [Agrupar las direcciones IP para simplificar la administración](group-your-ip-addresses-in-ocas.md)

- [Integración del servidor de SIEM](integrate-your-siem-server-with-office-365-cas.md)
    
- [Revisar y realizar acciones en las alertas](review-office-365-cas-alerts.md)
    
    

