---
title: Novedades de la seguridad de la aplicación de nube de Office 365
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: Admin
ms.topic: reference
ms.date: 12/26/2018
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: d674763c-a4c9-4604-8623-68c1836d27f3
description: Vea las novedades de seguridad de la aplicación de nube de Office 365
ms.openlocfilehash: 9f0c93d0de6ae8be72456c874ef8f5e3d42264e2
ms.sourcegitcommit: 25f72d20e76463c2f0a075dfc0116f00c934bd77
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/27/2018
ms.locfileid: "27447068"
---
# <a name="what-is-new-in-office-365-cloud-app-security"></a>Novedades de la seguridad de la aplicación de nube de Office 365

**Resumen** Lea este artículo para obtener una introducción rápida a las actualizaciones y nuevas características en Office 365 en la nube seguridad de la aplicación (anteriormente conocido como la administración de seguridad avanzada de Office 365), que es con tecnología de [Seguridad de la aplicación de Microsoft en la nube](https://aka.ms/whatiscas).
  
> [!TIP]
> En este artículo se actualiza con frecuencia, como las características se agregan o se ha mejorado. Actualizaciones de seguridad de la aplicación en la nube de Office 365 se liberan aproximadamente dos semanas después de las actualizaciones de seguridad de la aplicación de Microsoft en la nube, y no todas las actualizaciones de seguridad de la aplicación de Microsoft en la nube se aplican a la seguridad de la aplicación de nube de Office 365. Además, las nuevas características pueden tardar una semana o más después de su fecha de lanzamiento aparezca en su entorno de seguridad de la aplicación de nube de Office 365.

## <a name="office-365-cloud-app-security-release-138"></a>Versión de seguridad de la aplicación en la nube de Office 365 138

*Publicada el 23 de diciembre de 2018*

**Después de la [versión de seguridad de la aplicación de Microsoft en la nube 138](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-138)**:

- **Inicio de sesión automático cargarlo utilizando Docker en Windows** Seguridad de la aplicación en la nube ahora admite la carga de inicio de sesión automático para Windows 10 ([Entran los creadores de actualización](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) y versiones más recientes) y Windows Server ([versión 1709](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1709) y versiones más recientes) mediante el uso de Docker en Windows. Vea [este artículo](https://docs.microsoft.com/cloud-app-security/discovery-docker-windows) para obtener más información y configurar Docker.  

- **Integración de flujo de Microsoft** Seguridad de la aplicación en la nube ahora se integra con el [Flujo de Microsoft](https://docs.microsoft.com/flow/getting-started) para proporcionar guías de orquestación y automatización de alerta personalizados. Vea [este artículo](https://docs.microsoft.com/cloud-app-security/flow-integration) para obtener más información y configurar la integración de Microsoft Flow. 


## <a name="office-365-cloud-app-security-release-137"></a>Versión de seguridad de la aplicación en la nube de Office 365 137

*Publicadas el 8 de diciembre de 2018*

**Después de la [versión de seguridad de la aplicación de Microsoft en la nube 137](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-137)**:

- **Se agregó compatibilidad para Dynamics** Seguridad de la aplicación en la nube ahora incluye compatibilidad con las actividades de Microsoft Dynamics que son compatibles con el registro de auditoría de Office 365. 

- **Dirige las – nueva terminología!** Se cambió el nombre de las capacidades de los permisos de aplicación para mayor claridad: ahora se denomina OAuth aplicaciones. 


## <a name="office-365-cloud-app-security-release-136"></a>Versión de seguridad de la aplicación en la nube de Office 365 136

*Publicada el 25 de noviembre de 2018*

**Después de la [versión de seguridad de la aplicación de Microsoft en la nube 136](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-136)**:

- **Actualizaciones de detección de la nube** El analizador de registro personalizado se ha mejorado para admitir adicionales y formatos de los registros de tráfico web más complejo. Como parte de estos usuarios mejoras ahora puede escribir encabezados personalizados para los archivos de registro de headerless CSV, utilice delimitadores especiales para los archivos de clave y valor, del proceso de formato de archivo de registro del sistema y mucho más.

- **Nueva directiva de detección de anomalías: reglas de manipulación de bandeja de entrada sospechosos** Esta directiva de perfiles de su entorno y desencadenadores alertas cuando se establecen las reglas sospechosas que eliminan o mover mensajes o carpetas en la Bandeja de entrada de un usuario. Esto puede indicar que la cuenta del usuario se ve comprometida, que los mensajes que se están ocultos intencionadamente, y que el buzón de correo se utiliza para distribuir el correo no deseado o malware en su organización.

- **Soporte técnico para los grupos en las directivas de permisos de aplicación** Seguridad de la aplicación en la nube ahora le ofrece la capacidad para definir las directivas de permisos de aplicación de forma más granular, en función de la pertenencia a grupos de los usuarios que las aplicaciones de autorizados. Por ejemplo, un administrador puede decidir establecer una directiva que revoca aplicaciones poco frecuentes si le pidan permisos alta, sólo si el usuario que los permisos de autorización es un miembro del grupo Administradores.


## <a name="office-365-cloud-app-security-releases-133-134-and-135"></a>Versiones de seguridad de la aplicación en la nube de Office 365 133, 134 y 135

*Publicada en octubre y noviembre, 2018*

**Después de la [versión de seguridad de la aplicación de Microsoft en la nube 133, 134 y 135](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-133-134-135)**:

- **Nuevas directivas de detección de anomalías** son implantar gradualmente:
    
    - La nueva directiva de **exfiltration de datos a las aplicaciones no sancionadas** automáticamente está habilitada para avisarle cuando un usuario o dirección IP usa una aplicación que no se sancionado para llevar a cabo una actividad que se parece a un intento para exfiltrate información de su organización.
    
    - La nueva directiva de **varias actividades de la máquina virtual de eliminación** de perfiles de su entorno y activa las alertas cuando los usuarios eliminan varias de las máquinas virtuales en una sola sesión, con respecto a la línea de base de la organización.

- **Admitir la detección en la nube para i-filtro** La característica de detección de la nube de seguridad de aplicación en la nube ahora ha mejorado la compatibilidad con el analizador de registro del sistema i-filtro.


## <a name="office-365-cloud-app-security-release-131"></a>Versión de seguridad de la aplicación en la nube de Office 365 131

*Publicada el 16 de septiembre de 2018*

**Después de la [versión de seguridad de la aplicación de Microsoft en la nube 131](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-131)**:

- **Automáticamente revocar permisos sobre las aplicaciones OAuth arriesgados** Ahora puede controlar qué aplicaciones de OAuth los usuarios tienen acceso a, por revocar permisos de aplicación para OAuth las aplicaciones de Office. Al crear una directiva de permisos de aplicación, ahora puede establecer la directiva para revocar el permiso de una aplicación.

- **Detección de nube analizador integrado adicional compatibles** Detección de nube ahora es compatible con el formato de registro de Forcepoint Web seguridad en la nube.

  
## <a name="office-365-cloud-app-security-release-130"></a>Versión de seguridad de la aplicación en la nube de Office 365 130

*Publicada el 5 de septiembre de 2018*

**Después de [130 de la versión de seguridad de la aplicación de Microsoft en la nube](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-130)**:

- **Nueva barra de menús** Para proporcionar una experiencia más coherente de administración a través de productos de Microsoft 365 y para que pueda dinámicas más fácilmente entre las soluciones de seguridad de Microsoft, la barra de menús del portal de seguridad de la aplicación en la nube ha movido hasta el lado izquierdo de la pantalla. Esta navegación coherente experiencia ayuda a orientar a usted al pasar de un portal de seguridad de Microsoft a otro.<br/>![Barra de menús en la seguridad de la aplicación de Office en la nube](media/OCAS-MenuBar.png)<br/>

- **Puntuación de la aplicación de OAuth de impacto** Ahora puede enviar los comentarios del equipo de seguridad de la aplicación en la nube para hacernos saber si hay una aplicación de OAuth detectada en la organización que parece malintencionada. Esta nueva característica permite formar parte de nuestra comunidad de seguridad y mejorar el análisis y la puntuación de riesgo de aplicación de OAuth. Para obtener más información, vea [OAuth de administración de aplicaciones](manage-app-permissions-in-ocas.md).

- **Analizadores de detección de nuevo en la nube** Los analizadores de detección en la nube ahora admiten iboss seguro puerta de enlace de la nube y XG Sophos.


## <a name="office-365-cloud-app-security-release-128"></a>Versión de seguridad de la aplicación en la nube de Office 365 128

*Publicada el 5 de agosto de 2018* 
  
**Después de [128 de la versión de seguridad de la aplicación de Microsoft en la nube](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-128)**: 
  
- **Aplicaciones de OAuth entre múltiples aplicaciones** Para las aplicaciones de OAuth, ahora puede prohibir o aprobar varias aplicaciones en una sola acción. Por ejemplo, puede revisar todas las aplicaciones que se hayan concedido permiso por los usuarios de su organización, seleccione todas las aplicaciones que desea prohibir y, a continuación, haga clic en aplicaciones de prohibición para revocar todos los consentimiento concedido y ya no se permitirá a los usuarios conceder permiso a esas aplicaciones. Para obtener más información, vea [aplicaciones de administración de OAuth con seguridad de la aplicación de nube de Office 365](manage-app-permissions-in-ocas.md). 
    
- **Nueva consulta sugerido: GDPR listo en la nube aplicaciones** Hay una nueva consulta sugerida para que pueda identificar aplicaciones detectadas que están GDPR listo. Como probablemente ya sabe, GDPR ha recientemente se han convertido en una prioridad superior para los administradores de seguridad. Esta consulta le ayudará a identificar las aplicaciones que están GDPR listo fácilmente y mitigar amenazas al evaluar los riesgos de las aplicaciones que no están. Para usar la nueva consulta, en el panel de **Detección de la nube** , en la ficha **Discovered aplicaciones** , elija **consultas** > **aplicaciones GDPR listo en la nube**.<br/>![Consulta de aplicaciones de GDPR listo en la nube](media/OCAS-FindGDPRQueries.png)<br/>
    
## <a name="office-365-cloud-app-security-release-126"></a>Versión de seguridad de la aplicación en la nube de Office 365 126

*Publicada el 7 de julio de 2018* 
  
**Después de la [versión de seguridad de la aplicación de Microsoft en la nube 126](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-126)**: 
  
- **Corrección automática para detectar actividades sospechosas** Ahora puede definir las acciones de corrección automática de sesión sospechoso desencadenada por las directivas de detección de anomalías. Esta mejora le permite recibir una alerta al instante cuando se produce una infracción de y se aplican automáticamente a las acciones de gobierno, suspender como usuario. Para obtener más información, vea [las directivas de detección de anomalías de seguridad de la aplicación de nube de Office 365](anomaly-detection-policies-in-ocas.md).
    
- **Detección automatizada de riesgo de OAuth de aplicaciones** Además de la investigar existente de aplicaciones de OAuth conectadas a su entorno, seguridad de la aplicación de Office 365 en la nube ahora permite establecer notificaciones automáticas para informarle cuando una aplicación de OAuth cumple determinados criterios. Por ejemplo, se puede automáticamente avisará cuando hay aplicaciones que requieren un nivel de permisos alta y se han autorizado por más de 50 usuarios. Para obtener más información, vea [aplicaciones de administración de OAuth con seguridad de la aplicación de nube de Office 365](manage-app-permissions-in-ocas.md).
    
- **Compatibilidad con la administración del proveedor de servicios de seguridad gestionados (MSSP)** Seguridad de la aplicación de Office 365 en la nube ahora proporciona una mejor experiencia de administración a MSSPs y le permite configurar a socios externos como los administradores con cualquiera de los roles que se encuentra disponibles actualmente en la seguridad de la aplicación de nube de Office 365. Además, los administradores con derechos de acceso a más de un inquilino ahora pueden dinámicas fácilmente entre los inquilinos. 
    
## <a name="office-365-cloud-app-security-release-124"></a>Versión de seguridad de la aplicación en la nube de Office 365 124

*Publicada el 10 de junio de 2018* 
  
**Después de la [versión de seguridad de la aplicación de Microsoft en la nube 124](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-124)**: 
  
- **Implementaciones de ámbito** Las organizaciones empresariales forma granular pueden determinar qué usuarios para supervisar y proteger basándose en la pertenencia a grupo. Esta característica permite seleccionar los usuarios cuyas actividades no mostrará para cualquiera de las aplicaciones protegidas. Supervisión de ámbito es especialmente útil para el cumplimiento de normas y licencias. Algunas reglamentaciones de cumplimiento de normas exigen que Absténgase de supervisión de los usuarios de determinados países debido a la normativa local. Y puede supervisar a los usuarios menos permanecer dentro de los límites de las licencias de seguridad de la aplicación de nube de Office 365. 
    
- **Nuevo servidor de correo electrónico** El servidor de correo electrónico para la seguridad de la aplicación de nube de Office 365 ha cambiado y utiliza intervalos de direcciones IP diferentes. Para asegurarse de que puede obtener las notificaciones, agregar las nuevas direcciones IP a su lista de blanca contra correo no deseado. Para las organizaciones que personalización sus notificaciones, seguridad de la aplicación en la nube permite esto para que puede utilizar MailChimp, un servicio de correo electrónico de otro fabricante. Para obtener la lista de direcciones IP de servidor de correo e instrucciones para habilitar el trabajo con MailChimp, vea [requisitos de red (seguridad de la aplicación Microsoft en la nube)](https://docs.microsoft.com/cloud-app-security/network-requirements) y [configuración de correo (seguridad de la aplicación Microsoft en la nube)](https://docs.microsoft.com/cloud-app-security/mail-settings).
    
## <a name="office-365-cloud-app-security-release-121"></a>Versión de seguridad de la aplicación en la nube de Office 365 121

*Publicada el 6 de mayo de 2018* 
  
**Después de la [versión de seguridad de la aplicación de Microsoft en la nube 121](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-121)**: 
  
- **Mejoras en la directiva de detección de anomalías**. Se han mejorado para incluir dos nuevos tipos de detección de amenazas que gradualmente implantar directivas de detección de anomalías de Office 365 en la nube seguridad de la aplicación: 
    
  - **Actividad Ransomware.** Capacidades de detección de ransomware se extienden con detección de anomalías para dar cobertura más completa frente a ataques sofisticados ransomware. 
    
  - **Terminada la actividad del usuario.** Terminada permite de actividad de usuario para supervisar las cuentas de los usuarios con los que puede haber sido canceló el aprovisionamiento de aplicaciones de la empresa, pero que es posible que todavía tiene acceso a determinados recursos corporativos. 
    
    Para ver las [directivas de detección de anomalías](anomaly-detection-policies-in-ocas.md), en el portal de seguridad de la aplicación de nube de Office 365, elija **Control** \> **directivas**.
    
## <a name="office-365-cloud-app-security-release-120"></a>Versión de seguridad de la aplicación en la nube de Office 365 120

*Publicada el 22 de abril de 2018* 
  
**Después de [120 de la versión de seguridad de la aplicación de Microsoft en la nube](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-120)**: 
  
- **Aplicaciones internas como las actividades del usuario**. Para Office 365 y Azure Active Directory (AD Azure), nos estamos ahora gradualmente implantar la capacidad para detectar las aplicaciones internas como las actividades de cuenta de usuario realizadas por las aplicaciones de Office 365 y Azure AD (internas y externas). Esto le permite crear políticas para avisarle si una aplicación realiza actividades inesperadas y no autorizadas. 
    
- **Exportación de varios campos en la lista de aplicaciones de OAuth**. Al exportar una lista de aplicaciones de OAuth a csv, los campos adicionales como publisher, uso de la Comunidad y de nivel de permisos se incluyen para ayudarle con el proceso de investigación y cumplimiento de normas. 
    
## <a name="office-365-cloud-app-security-release-119"></a>Versión de seguridad de la aplicación en la nube de Office 365 119

*Publicada el 1 de abril de 2018* 
  
**Después de la [versión de seguridad de la aplicación de Microsoft en la nube 119](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-119)**: 
  
- **Mejoras en la detección de nube**. La detección de la nube proporciona más información acerca los usuarios superiores y direcciones IP, haciendo que sea más fácil para ver los detalles de uso sobre Office 365 y otras aplicaciones. Para obtener más información, vea [conclusiones de detección de aplicación de revisión de seguridad de la aplicación de nube de Office 365](review-app-discovery-findings-in-ocas.md).
    
    ![Se ha actualizado el panel detección de nube](media/12712681-c0b3-4cb3-b7fd-2cf2ad4e825f.png)
  
## <a name="office-365-cloud-app-security-release-118"></a>Versión de seguridad de la aplicación en la nube de Office 365 118

*Publicada el 18 de marzo de 2018* 
  
**Después de la [versión de seguridad de la aplicación de Microsoft en la nube 118](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-118)**: 
  
- **Admite barracuda**. Detección de nube ahora admite los firewalls de serie F de Barracuda y Barracuda F-serie firewall web registro transmisión por secuencias. 
    
## <a name="office-365-cloud-app-security-release-117"></a>Versión de seguridad de la aplicación en la nube de Office 365 117

*Publicada el 6 de marzo de 2018* 
  
**Después de la [versión de seguridad de la aplicación de Microsoft en la nube 117](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-117)**: 
  
- **compatible con filtro de i**. Detección de nube ahora admite i-filtro. 
    
## <a name="office-365-cloud-app-security-release-116"></a>Versión de seguridad de la aplicación en la nube de Office 365 116

*Publicada el 18 de febrero de 2018* 
  
**Después de la [versión de seguridad de la aplicación de Microsoft en la nube 116](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-116)**: 
  
- **Mejoras en la directiva de detección de anomalías**. Detección de anomalías de directivas de seguridad de la aplicación de nube de Office 365 se han mejorado con nuevas detecciones basada en escenarios incluidos imposible viajes, actividad desde una dirección IP sospechosa y los intentos de inicio de sesión con errores de varios. Las nuevas directivas se habilitan automáticamente, que proporciona la detección de amenazas de cuadro en todo el entorno de nube. Además, las nuevas directivas exponen más datos desde el motor de detección de seguridad de la aplicación de nube de Office 365, que puede ayudar a acelerar el proceso de investigación y contienen las amenazas en curso. Para obtener más información, vea el artículo de seguridad de la aplicación de Microsoft en la nube, [Obtenga análisis el comportamiento instantáneo y detección de anomalías](https://docs.microsoft.com/cloud-app-security/anomaly-detection-policy).
    
- **Compatibilidad con el registro del analizador para formatos de punto de control**. Los analizadores de registro de detección en la nube ahora admiten dos formatos de punto de comprobación adicionales: XML y KPC. 
    
## <a name="office-365-cloud-app-security-release-114"></a>Versión de seguridad de la aplicación en la nube de Office 365 114

*Publicada el 21 de enero de 2018* 
  
**Después de la [versión de seguridad de la aplicación de Microsoft en la nube 114](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-114)**: 
  
- **Estado del servicio**. Ahora puede comprobar el estado actual del servicio de seguridad de la aplicación de nube de Office 365 yendo para **ayudar a** \> **estado del sistema**. 
    
    ![Haga clic en Ayuda \> estado del sistema para ver el estado de mantenimiento del sistema](media/2b496dac-ed9d-4480-83b6-85f9510d3aea.png)
  
- **Las consultas personalizadas para el registro de actividad**. A partir de la versión 114, la capacidad de crear y guardar consultas personalizadas en el registro de actividad se implantar gradualmente. Consultas personalizadas permiten crear plantillas de filtro que se pueden reutilizar para una investigación de análisis detallado. Además, sugiere las consultas han sido agregado para proporcionar plantillas de investigación de fábrica para filtrar las actividades y detecta aplicaciones. Consultas sugeridas incluyen filtros personalizados para identificar riesgos, como las actividades de suplantación, las actividades de administrador, arriesgado nube que no son compatibles con aplicaciones de almacenamiento, aplicaciones de empresa con cifrado débil y los riesgos de seguridad. Use las consultas sugeridas como punto de partida, modifíquelas según sea necesario y, a continuación, guardarlos como una nueva consulta. 
    
## <a name="office-365-cloud-app-security-release-113"></a>Versión de seguridad de la aplicación en la nube de Office 365 113

*Publicadas el 8 de enero de 2018* 
  
**Después de la [versión de seguridad de la aplicación de Microsoft en la nube 113](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-113)**: 
  
- **Compatibilidad con el registro del analizador para formatos genéricos**. Los analizadores de registro de detección en la nube ahora admiten los siguientes formatos genéricos: LEEF, CEF y W3C. 

## <a name="releases-prior-to-113"></a>Versiones anteriores a 113

[Consulte las actualizaciones de 2017 para seguridad de la aplicación de nube de Office 365](new-in-office-365-cas-2017.md)
    
