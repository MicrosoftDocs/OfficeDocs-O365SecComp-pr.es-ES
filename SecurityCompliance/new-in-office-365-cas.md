---
title: Novedades de la seguridad de la aplicación de nube de Office 365
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: Admin
ms.topic: reference
ms.date: 10/31/2018
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: d674763c-a4c9-4604-8623-68c1836d27f3
description: Vea las novedades de seguridad de la aplicación de nube de Office 365
ms.openlocfilehash: f661d0d541e84db89b7abd99fd77ef9a767a4cd0
ms.sourcegitcommit: 49abeb8e57a5ee622d72a3782175a989b1a2e3c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/02/2018
ms.locfileid: "25935577"
---
# <a name="what-is-new-in-office-365-cloud-app-security"></a>Novedades de la seguridad de la aplicación de nube de Office 365

Lea este artículo para obtener una introducción rápida a las actualizaciones y nuevas características en Office 365 en la nube seguridad de la aplicación (anteriormente conocido como la administración de seguridad avanzada de Office 365), que es con tecnología de [Seguridad de la aplicación de Microsoft en la nube](https://aka.ms/whatiscas).
  
En este artículo se actualiza con frecuencia, como las características se agregan o se ha mejorado. Actualizaciones de seguridad de la aplicación en la nube de Office 365 se liberan aproximadamente dos semanas después de las actualizaciones de seguridad de la aplicación de Microsoft en la nube, y no todas las actualizaciones de seguridad de la aplicación de Microsoft en la nube se aplican a la seguridad de la aplicación de nube de Office 365. Además, las nuevas características pueden tardar una semana o más después de su fecha de lanzamiento aparezca en su entorno de seguridad de la aplicación de nube de Office 365.
  
## <a name="office-365-cloud-app-security-release-130"></a>Versión de seguridad de la aplicación en la nube de Office 365 130

*Publicada el 5 de septiembre de 2018*

**Lanzamiento con [130 de la versión de seguridad de la aplicación de Microsoft en la nube](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-130)**:

- **Nueva barra de menús** Para proporcionar una experiencia más coherente de administración a través de productos de Microsoft 365 y para que pueda dinámicas más fácilmente entre las soluciones de seguridad de Microsoft, la barra de menús del portal de seguridad de la aplicación en la nube ha movido hasta el lado izquierdo de la pantalla. Esta navegación coherente experiencia ayuda a orientar a usted al pasar de un portal de seguridad de Microsoft a otro.<br/>![Barra de menús en la seguridad de la aplicación de Office en la nube](media/OCAS-MenuBar.png)<br/>

- **Puntuación de la aplicación de OAuth de impacto** Ahora puede enviar los comentarios del equipo de seguridad de la aplicación en la nube para hacernos saber si hay una aplicación de OAuth detectada en la organización que parece malintencionada. Esta nueva característica permite formar parte de nuestra comunidad de seguridad y mejorar el análisis y la puntuación de riesgo de aplicación de OAuth. Para obtener más información, vea [Administrar permisos de aplicación](manage-app-permissions-in-ocas.md).

- **Analizadores de detección de nuevo en la nube** Los analizadores de detección en la nube ahora admiten iboss seguro puerta de enlace de la nube y XG Sophos.


## <a name="office-365-cloud-app-security-release-128"></a>Versión de seguridad de la aplicación en la nube de Office 365 128

*Publicada el 5 de agosto de 2018* 
  
**Lanzamiento con [128 de la versión de seguridad de la aplicación de Microsoft en la nube](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-128)**: 
  
- **Permisos de aplicación a través de varias aplicaciones** Para las aplicaciones que se hayan concedido permisos de aplicación, ahora puede prohibir o aprobar varias aplicaciones en una sola acción. Por ejemplo, puede revisar todas las aplicaciones que se hayan concedido permiso por los usuarios de su organización, seleccione todas las aplicaciones que desea prohibir y, a continuación, haga clic en aplicaciones de prohibición para revocar todos los consentimiento concedido y ya no se permitirá a los usuarios conceder permiso a esas aplicaciones. 
    
- **Nueva consulta sugerido: listo GDPR** Hay una nueva consulta sugerida para que pueda identificar aplicaciones detectadas que están GDPR listo. GDPR recientemente ha se han convertido en una prioridad superior para los administradores de seguridad. Esta consulta le ayudará a identificar las aplicaciones que están GDPR listo fácilmente y mitigar amenazas al evaluar los riesgos de las aplicaciones que no están. 
    
## <a name="office-365-cloud-app-security-release-126"></a>Versión de seguridad de la aplicación en la nube de Office 365 126

*Publicada el 7 de julio de 2018* 
  
**Publicada el con [126 de la versión de seguridad de la aplicación de Microsoft en la nube](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-126)**: 
  
- **Corrección automática para detectar actividades sospechosas** Ahora puede definir las acciones de corrección automática de sesión sospechoso desencadenada por las directivas de detección de anomalías. Esta mejora le permite recibir una alerta al instante cuando se produce una infracción de y se aplican automáticamente a las acciones de gobierno, suspender como usuario. Para obtener más información, vea [las directivas de detección de anomalías de seguridad de la aplicación de nube de Office 365](anomaly-detection-policies-in-ocas.md).
    
- **Detección automatizada de riesgo de OAuth de aplicaciones** Además de la investigar existente de aplicaciones de OAuth conectadas a su entorno, seguridad de la aplicación de Office 365 en la nube ahora permite establecer notificaciones automáticas para informarle cuando una aplicación de OAuth cumple determinados criterios. Por ejemplo, se puede automáticamente avisará cuando hay aplicaciones que requieren un nivel de permisos alta y se han autorizado por más de 50 usuarios. Para obtener más información, vea [administrar los permisos de aplicación con seguridad de la aplicación de nube de Office 365](manage-app-permissions-in-ocas.md).
    
- **Compatibilidad con la administración del proveedor de servicios de seguridad gestionados (MSSP)** Seguridad de la aplicación de Office 365 en la nube ahora proporciona una mejor experiencia de administración a MSSPs y le permite configurar a socios externos como los administradores con cualquiera de los roles que se encuentra disponibles actualmente en la seguridad de la aplicación de nube de Office 365. Además, los administradores con derechos de acceso a más de un inquilino ahora pueden dinámicas fácilmente entre los inquilinos. 
    
## <a name="office-365-cloud-app-security-release-124"></a>Versión de seguridad de la aplicación en la nube de Office 365 124

*Publicada el 10 de junio de 2018* 
  
**Publicada el con [124 de la versión de seguridad de la aplicación de Microsoft en la nube](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-124)**: 
  
- **Implementaciones de ámbito** Las organizaciones empresariales forma granular pueden determinar qué usuarios para supervisar y proteger basándose en la pertenencia a grupo. Esta característica permite seleccionar los usuarios cuyas actividades no mostrará para cualquiera de las aplicaciones protegidas. Supervisión de ámbito es especialmente útil para el cumplimiento de normas y licencias. Algunas reglamentaciones de cumplimiento de normas exigen que Absténgase de supervisión de los usuarios de determinados países debido a la normativa local. Y puede supervisar a los usuarios menos permanecer dentro de los límites de las licencias de seguridad de la aplicación de nube de Office 365. 
    
- **Nuevo servidor de correo electrónico** El servidor de correo electrónico para la seguridad de la aplicación de nube de Office 365 ha cambiado y utiliza intervalos de direcciones IP diferentes. Para asegurarse de que puede obtener las notificaciones, agregar las nuevas direcciones IP a su lista de blanca contra correo no deseado. Para las organizaciones que personalización sus notificaciones, seguridad de la aplicación en la nube permite esto para que puede utilizar MailChimp, un servicio de correo electrónico de otro fabricante. Para obtener la lista de direcciones IP de servidor de correo e instrucciones para habilitar el trabajo con MailChimp, vea [requisitos de red (seguridad de la aplicación Microsoft en la nube)](https://docs.microsoft.com/cloud-app-security/network-requirements) y [configuración de correo (seguridad de la aplicación Microsoft en la nube)](https://docs.microsoft.com/cloud-app-security/mail-settings).
    
## <a name="office-365-cloud-app-security-release-121"></a>Versión de seguridad de la aplicación en la nube de Office 365 121

*Publicada el 6 de mayo de 2018* 
  
**Publicada el con [121 de la versión de seguridad de la aplicación de Microsoft en la nube](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-121)**: 
  
- **Mejoras en la directiva de detección de anomalías**. Se han mejorado para incluir dos nuevos tipos de detección de amenazas que gradualmente implantar directivas de detección de anomalías de Office 365 en la nube seguridad de la aplicación: 
    
  - **Actividad Ransomware.** Capacidades de detección de ransomware se extienden con detección de anomalías para dar cobertura más completa frente a ataques sofisticados ransomware. 
    
  - **Terminada la actividad del usuario.** Terminada permite de actividad de usuario para supervisar las cuentas de los usuarios con los que puede haber sido canceló el aprovisionamiento de aplicaciones de la empresa, pero que es posible que todavía tiene acceso a determinados recursos corporativos. 
    
    Para ver las [directivas de detección de anomalías](anomaly-detection-policies-in-ocas.md), en el portal de seguridad de la aplicación de nube de Office 365, elija **Control** \> **directivas**.
    
## <a name="office-365-cloud-app-security-release-120"></a>Versión de seguridad de la aplicación en la nube de Office 365 120

*Publicada el 22 de abril de 2018* 
  
**Publicada el con [120 de la versión de seguridad de la aplicación de Microsoft en la nube](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-120)**: 
  
- **Aplicaciones internas como las actividades del usuario**. Para Office 365 y Azure Active Directory (AD Azure), nos estamos ahora gradualmente implantar la capacidad para detectar las aplicaciones internas como las actividades de cuenta de usuario realizadas por las aplicaciones de Office 365 y Azure AD (internas y externas). Esto le permite crear políticas para avisarle si una aplicación realiza actividades inesperadas y no autorizadas. 
    
- **Exportación de varios campos en la lista de permisos de aplicación**. Al exportar una lista de permisos de aplicación a csv, los campos adicionales como publisher, uso de la Comunidad y de nivel de permisos se incluyen para ayudarle con el proceso de investigación y cumplimiento de normas. 
    
## <a name="office-365-cloud-app-security-release-119"></a>Versión de seguridad de la aplicación en la nube de Office 365 119

*Publicada el 1 de abril de 2018* 
  
**Publicada el con [119 de la versión de seguridad de la aplicación de Microsoft en la nube](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-119)**: 
  
- **Mejoras en la detección de nube**. La detección de la nube proporciona más información acerca los usuarios superiores y direcciones IP, haciendo que sea más fácil para ver los detalles de uso sobre Office 365 y otras aplicaciones. Para obtener más información, vea [conclusiones de detección de aplicación de revisión de seguridad de la aplicación de nube de Office 365](review-app-discovery-findings-in-ocas.md).
    
    ![Se ha actualizado el panel detección de nube](media/12712681-c0b3-4cb3-b7fd-2cf2ad4e825f.png)
  
## <a name="office-365-cloud-app-security-release-118"></a>Versión de seguridad de la aplicación en la nube de Office 365 118

*Publicada el 18 de marzo de 2018* 
  
**Publicada el con [118 de la versión de seguridad de la aplicación de Microsoft en la nube](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-118)**: 
  
- **Admite barracuda**. Detección de nube ahora admite los firewalls de serie F de Barracuda y Barracuda F-serie firewall web registro transmisión por secuencias. 
    
## <a name="office-365-cloud-app-security-release-117"></a>Versión de seguridad de la aplicación en la nube de Office 365 117

*Publicada el 6 de marzo de 2018* 
  
**Publicada el con [117 de la versión de seguridad de la aplicación de Microsoft en la nube](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-117)**: 
  
- **compatible con filtro de i**. Detección de nube ahora admite i-filtro. 
    
## <a name="office-365-cloud-app-security-release-116"></a>Versión de seguridad de la aplicación en la nube de Office 365 116

*Publicada el 18 de febrero de 2018* 
  
**Publicada el con [116 de la versión de seguridad de la aplicación de Microsoft en la nube](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-116)**: 
  
- **Mejoras en la directiva de detección de anomalías**. Detección de anomalías de directivas de seguridad de la aplicación de nube de Office 365 se han mejorado con nuevas detecciones basada en escenarios incluidos imposible viajes, actividad desde una dirección IP sospechosa y los intentos de inicio de sesión con errores de varios. Las nuevas directivas se habilitan automáticamente, que proporciona la detección de amenazas de cuadro en todo el entorno de nube. Además, las nuevas directivas exponen más datos desde el motor de detección de seguridad de la aplicación de nube de Office 365, que puede ayudar a acelerar el proceso de investigación y contienen las amenazas en curso. Para obtener más información, vea el artículo de seguridad de la aplicación de Microsoft en la nube, [Obtenga análisis el comportamiento instantáneo y detección de anomalías](https://docs.microsoft.com/cloud-app-security/anomaly-detection-policy).
    
- **Compatibilidad con el registro del analizador para formatos de punto de control**. Los analizadores de registro de detección en la nube ahora admiten dos formatos de punto de comprobación adicionales: XML y KPC. 
    
## <a name="office-365-cloud-app-security-release-114"></a>Versión de seguridad de la aplicación en la nube de Office 365 114

*Publicada el 21 de enero de 2018* 
  
**Publicada el con la [versión de seguridad de la aplicación de Microsoft en la nube 114](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-114)**: 
  
- **Estado del servicio**. Ahora puede comprobar el estado actual del servicio de seguridad de la aplicación de nube de Office 365 yendo para **ayudar a** \> **estado del sistema**. 
    
    ![Haga clic en Ayuda \> estado del sistema para ver el estado de mantenimiento del sistema](media/2b496dac-ed9d-4480-83b6-85f9510d3aea.png)
  
- **Las consultas personalizadas para el registro de actividad**. A partir de la versión 114, la capacidad de crear y guardar consultas personalizadas en el registro de actividad se implantar gradualmente. Consultas personalizadas permiten crear plantillas de filtro que se pueden reutilizar para una investigación de análisis detallado. Además, sugiere las consultas han sido agregado para proporcionar plantillas de investigación de fábrica para filtrar las actividades y detecta aplicaciones. Consultas sugeridas incluyen filtros personalizados para identificar riesgos, como las actividades de suplantación, las actividades de administrador, arriesgado nube que no son compatibles con aplicaciones de almacenamiento, aplicaciones de empresa con cifrado débil y los riesgos de seguridad. Use las consultas sugeridas como punto de partida, modifíquelas según sea necesario y, a continuación, guardarlos como una nueva consulta. 
    
## <a name="office-365-cloud-app-security-release-113"></a>Versión de seguridad de la aplicación en la nube de Office 365 113

*Publicadas el 8 de enero de 2018* 
  
**Publicada el con [113 de la versión de seguridad de la aplicación de Microsoft en la nube](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-113)**: 
  
- **Compatibilidad con el registro del analizador para formatos genéricos**. Los analizadores de registro de detección en la nube ahora admiten los siguientes formatos genéricos: LEEF, CEF y W3C. 
    
## <a name="office-365-cloud-app-security-release-112"></a>Versión de seguridad de la aplicación en la nube de Office 365 112

*Publicada el 24 de diciembre de 2017* 
  
**Publicada el con [112 de la versión de seguridad de la aplicación de Microsoft en la nube](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-112)**: 
  
- **Alimentador de insight relevantes**. En el registro de actividad, ahora puede tener acceso el alimentador insight relevantes haciendo clic en un nombre de usuario o la dirección IP. 
    
    ![Haga clic en un nombre de usuario o la dirección IP del alimentador de insight relevantes en el registro de actividad.](media/8e32b3fa-8c0c-4c5e-b248-fe7d7e1b516d.png)
  
- **Capacidad de ver más actividades con un clic**. En la caja insight relevantes, hacer clic en el icono de reloj para ver todas las actividades realizadas dentro de 48 horas de una actividad seleccionada. 
    
    ![En el alimentador de perspectivas pertinentes, haga clic en el icono de reloj para ver las actividades realizadas dentro de una actividad seleccionada 48 horas](media/c6c96aa0-98e5-4205-8873-45f8d6fd0843.png)
  
- **Mejoras del analizador de registro para Juniper SRX**. Se realizaron mejoras en el analizador de registro de detección de la nube para Juniper SRX. 
    
## <a name="office-365-cloud-app-security-release-111"></a>Versión de seguridad de la aplicación en la nube de Office 365 111

*Publicada el 10 de diciembre de 2017* 
  
**Publicada el con [111 de la versión de seguridad de la aplicación de Microsoft en la nube](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-111)**: 
  
- **Mejoras de filtro de tiempo**. Filtros de tiempo ahora son más fáciles de usar. Para obtener acceso a un filtro de tiempo, en una vista, como el registro de actividad, las directivas, alertas, en la vista avanzada, elija la **fecha** en la lista de filtros. A continuación, elija una opción, como antes, después o en entre para aplicar el filtro de tiempo. 
    
    ![Use el filtro de fecha para ver información antes, después o entre las fechas.](media/9dbb2a10-f68f-413b-8b4e-88911152cb92.png)
  
## <a name="office-365-cloud-app-security-release-110"></a>Versión de seguridad de la aplicación en la nube de Office 365 110

*Publicada el 26 de noviembre de 2017* 
  
**Publicada el con la [versión de seguridad de la aplicación de Microsoft en la nube 110](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-110)**: 
  
- **Integración del servidor de SIEM ahora generalmente está disponible**. Conectar el servidor SIEM a la seguridad de la aplicación de nube de Office 365. Ahora puede enviar alertas y actividades automáticamente a su servidor SIEM de elección mediante la configuración de los agentes de SIEM. Vea [integrar su servidor SIEM con seguridad de la aplicación de nube de Office 365](integrate-your-siem-server-with-office-365-cas.md).
    
- **Facilitar el acceso a contenido de la Ayuda**. Usar el signo de interrogación nuevo en la esquina superior derecha, ahora puede tener acceso el contenido de Ayuda desde dentro de las páginas del portal de seguridad de la aplicación de nube de Office 365. Es contextual, desviar a la información que necesita, en función de la página en que está cada vínculo. 
    
- **Envíenos su opinión**. Uso de la cara sonriente en la esquina superior derecha, ahora puede enviar comentarios de cada página del portal de seguridad de la aplicación de nube de Office 365. Esto permite informar sobre errores, solicitar nuevas características y compartir su experiencia directamente con el equipo de seguridad de la aplicación de nube de Office 365. 
    
## <a name="office-365-cloud-app-security-release-102"></a>Versión de seguridad de la aplicación en la nube de Office 365 102

*Publicada el 13 de agosto de 2017* 
  
**Publicada el con [102 de la versión de seguridad de la aplicación de Microsoft en la nube](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-102)**: 
  
- **Nuevas acciones de investigación de usuario** habilitar un nivel de profundidad se ha agregado a las investigaciones de usuario. En una página de investigar, puede mantenga el mouse sobre una actividad, un usuario o una cuenta y aplicar como filtro y desde allí, puede ver actividades relacionadas o eventos. 
    
## <a name="office-365-cloud-app-security-release-100"></a>Versión de seguridad de la aplicación en la nube de Office 365 100

*Publicada el 17 de julio de 2017* 
  
**Publicada el con [100 de la versión de seguridad de la aplicación de Microsoft en la nube](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-100)**: 
  
- **Extensiones de seguridad** es un nuevo panel, donde puede administrar centralmente todas las extensiones de seguridad para Office 365 en la nube seguridad de la aplicación, incluidos los tokens de API y los agentes SIEM. Para ver el panel de extensiones de seguridad, siga estos pasos: 
    
1. Vaya a [https://protection.office.com](https://protection.office.com) e iniciar sesión con su cuenta de trabajo o escuela para Office 365. (Esto le llevará a la seguridad &amp; centro de cumplimiento.) 
    
2. Vaya a **las alertas de** \> **avanzada de administrar las alertas**.
    
3. Elija **Ir a la seguridad de la aplicación de Office 365 en la nube**.
    
    ![En la seguridad &amp; centro de cumplimiento, elija alertas \> administrar avanzada alertas \> vaya a administración de seguridad avanzada](media/9792b121-9cd4-4faa-a6e0-81cfab4bf2f2.png)
  
4. Elija **configuración** \> **extensiones de seguridad**.
    
    ![En el portal de ASM, elija configuración \> extensiones de seguridad](media/f03d47a1-91ff-41b9-9baf-b514cffe41a8.png)
  
- **Función mejorada de análisis**. Se han realizado mejoras en el registro de detección de la nube mecanismo de análisis. Errores internos son considerablemente menos probables que se produzca. 
    
- **Los formatos de registro esperado**. El formato esperado del registro para los registros de detección de la nube ahora proporciona ejemplos de formato de registro del sistema y el formato FTP. 
    
## <a name="related-topics"></a>Temas relacionados

[Contenido de Ayuda de seguridad de la aplicación en la nube de Office 365](office-365-cas-help.md)
  
[Actividades de uso después de implementar Office 365 Cloud App Security](utilization-activities-for-ocas.md)
  
[Los permisos de la seguridad de Office 365 &amp; centro de cumplimiento](permissions-in-the-security-and-compliance-center.md)
  

