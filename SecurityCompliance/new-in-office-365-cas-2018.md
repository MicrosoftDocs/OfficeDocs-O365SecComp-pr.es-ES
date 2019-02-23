---
title: Novedades de Office 365 Cloud App Security
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: Admin
ms.topic: reference
ms.date: 01/25/2019
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
description: Vea qué se ha lanzado durante 2018 para Office 365 Cloud App Security
ms.openlocfilehash: 986fb64eedf8184e7835d1fec41845fde13b294b
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/23/2019
ms.locfileid: "30214350"
---
# <a name="office-365-cloud-app-security-updates-during-2018"></a>Actualizaciones de seguridad de aplicaciones de nube de Office 365 durante 2018

## <a name="office-365-cloud-app-security-release-138"></a>Office 365 Cloud App Security Release 138

*Lanzado el 23 de diciembre de 2018*

** [Revisión de seguridad de aplicaciones en la nube de Microsoft 138](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-138)**:

- **Carga de registro automática con Docker en Windows** Cloud App Security ahora admite la carga de registro automática para Windows 10 ([actualización de creadores](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) y versiones posteriores) y Windows Server ([versión 1709](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1709) y posteriores) mediante Docker en Windows. Consulte [este artículo](https://docs.microsoft.com/cloud-app-security/discovery-docker-windows) para obtener más información y configurar Docker.  

- **Integración de Microsoft Flow** Cloud App Security ahora se integra con [Microsoft Flow](https://docs.microsoft.com/flow/getting-started) para proporcionar guías de automatización y orquestación personalizadas de alertas. Consulte [este artículo](https://docs.microsoft.com/cloud-app-security/flow-integration) para obtener más información y configurar la integración de Microsoft Flow. 

## <a name="office-365-cloud-app-security-release-137"></a>Office 365 Cloud App Security Release 137

*Lanzado el 8 de diciembre de 2018*

** [Revisión de seguridad de aplicaciones en la nube de Microsoft 137](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-137)**:

- Se **ha agregado compatibilidad para Dynamics** Cloud App Security ahora incluye compatibilidad para las actividades de Microsoft Dynamics que son compatibles con el registro de auditoría de Office 365. 

- ¡ **Cara arriba – nueva terminología!** El nombre de las funcionalidades de permisos de la aplicación se cambió para mayor claridad, ahora se denomina aplicaciones de OAuth. 

## <a name="office-365-cloud-app-security-release-136"></a>Office 365 Cloud App Security Release 136

*Lanzado el 25 de noviembre de 2018*

** [Revisión de seguridad de aplicaciones en la nube de Microsoft 136](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-136)**:

- **Actualizaciones de detección en la nube** El analizador de registros personalizado se ha mejorado para admitir formatos de registros de tráfico web adicionales y más complejos. Como parte de estas mejoras, los usuarios ahora pueden introducir encabezados personalizados para archivos de registro CSV sin encabezado, usar delimitadores especiales para los archivos de valor clave, el formato de archivo syslog del proceso, etc.

- **Nueva Directiva de detección de anomalías: reglas de manipulación de la bandeja de entrada sospechosa** Esta directiva perfila el entorno y desencadena alertas cuando se establecen reglas sospechosas que eliminan o mueven mensajes o carpetas en la bandeja de entrada de un usuario. Esto puede indicar que la cuenta del usuario está en peligro, que los mensajes se ocultan de forma intencionada y que el buzón se usa para distribuir correo no deseado o malware en su organización.

- **Compatibilidad con grupos en directivas de permisos de aplicaciones** Cloud App Security ahora le ofrece la posibilidad de definir directivas de permisos de aplicaciones de forma granular, en función de las pertenencias a grupos de los usuarios que autorizaron las aplicaciones. Por ejemplo, un administrador puede decidir establecer una directiva que revoca aplicaciones no comunes si solicitan permisos elevados, solo si el usuario que ha autorizado los permisos es miembro del grupo de administradores.

## <a name="office-365-cloud-app-security-releases-133-134-and-135"></a>Versiones de seguridad de aplicaciones de nube de Office 365 133, 134 y 135

*Lanzado en octubre a noviembre de 2018*

**Siguiente [versión de Microsoft Cloud App Security, 133, 134 y 135](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-133-134-135)**:

- **Las nuevas directivas de detección** de anomalías se implementan gradualmente:
    
    - La nueva Directiva de **exfiltración de datos a aplicaciones** no autorizadas se habilita automáticamente para que le avise cuando un usuario o una dirección IP use una aplicación que no esté sancionada para realizar una actividad similar a un intento de exfiltrar información de su organización.
    
    - La nueva Directiva de **actividades de VM de múltiples eliminaciones** perfila el entorno y desencadena alertas cuando los usuarios eliminan varias máquinas virtuales en una sola sesión, en relación con la línea base de la organización.

- **Compatibilidad de detección en la nube para i-Filter** La característica de detección en la nube de Cloud App Security ahora tiene compatibilidad mejorada con el analizador i-Filter syslog.

## <a name="office-365-cloud-app-security-release-131"></a>Office 365 Cloud App Security Release 131

*Lanzado el 16 de septiembre de 2018*

** [Revisión de seguridad de aplicaciones en la nube de Microsoft 131](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-131)**:

- **Revocar automáticamente los permisos de aplicaciones de OAuth arriesgadas** Ahora puede controlar a qué aplicaciones de OAuth tienen acceso los usuarios, al revocar el permiso de aplicación para aplicaciones de OAuth en Office. Al crear una directiva de permisos de aplicaciones, ahora puede establecer la Directiva para revocar el permiso de una aplicación.

- **Analizador integrado adicional compatible con detección en la nube** La detección en la nube ahora admite el formato de registro en la nube de seguridad Web de Forcepoint.
  
## <a name="office-365-cloud-app-security-release-130"></a>Office 365 Cloud App Security Release 130

*Lanzado el 5 de septiembre de 2018*

** [Revisión de seguridad de aplicaciones en la nube de Microsoft 130](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-130)**:

- **Nueva barra de menús** Para proporcionar una experiencia de administración más coherente en los productos de Microsoft 365 y para permitirle a las tablas dinámicas más fácilmente entre las soluciones de seguridad de Microsoft, la barra de menús del portal de Cloud App Security se ha movido al lado izquierdo de la pantalla. Esta experiencia de navegación coherente le ayuda a orientarse a sí mismo al pasar de un portal de seguridad de Microsoft a otro.<br/>![Barra de menús de seguridad de aplicaciones de la nube de Office](media/OCAS-MenuBar.png)<br/>

- Impacto en la puntuación de la **aplicación OAuth** Ahora puede enviar comentarios del equipo de Cloud App Security para informarnos si hay una aplicación de OAuth detectada en su organización que parece malintencionada. Esta nueva característica le permite formar parte de nuestra comunidad de seguridad y mejorar el análisis y la puntuación de riesgos de aplicaciones de OAuth. Para obtener más información, vea [Administrar aplicaciones de OAuth](manage-app-permissions-in-ocas.md).

- **Nuevos Analizadores de detección en la nube** Los analizadores de detección en la nube ahora admiten iboss Secure Cloud Gateway y Sophos XG.

## <a name="office-365-cloud-app-security-release-128"></a>Office 365 Cloud App Security Release 128

*Lanzado el 5 de agosto de 2018* 
  
** [Revisión de seguridad de aplicaciones en la nube de Microsoft 128](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-128)**: 
  
- **Aplicaciones de OAuth en varias aplicaciones** Para las aplicaciones de OAuth, ahora puede prohibir o aprobar varias aplicaciones en una sola acción. Por ejemplo, puede revisar todas las aplicaciones a las que los usuarios de su organización han concedido permisos, seleccionar todas las aplicaciones que quiere prohibir y, a continuación, hacer clic en prohibir aplicaciones para revocar todos los consentimiento concedidos y dejará de permitir que los usuarios concedan permiso a esas aplicaciones. Para obtener más información, consulte [Administrar aplicaciones de OAuth con Office 365 Cloud App Security](manage-app-permissions-in-ocas.md). 
    
- **Nueva consulta sugerida: RGPD-Ready Cloud apps** Hay una nueva consulta sugerida que le permitirá identificar las aplicaciones descubiertas que están listas para RGPD. Como probablemente ya sepa, RGPD se ha convertido recientemente en una prioridad principal para los administradores de seguridad. Esta consulta ayuda a identificar fácilmente las aplicaciones que están RGPDdas y a mitigar la amenaza mediante la evaluación del riesgo de las aplicaciones que no están disponibles. Para usar la nueva consulta, en el **Panel detección** en la nube, en la pestaña **aplicaciones detectadas** , elija **consultas** > **RGPD en la nube**preparadas.<br/>![Consulta RGPD-Ready Cloud apps](media/OCAS-FindGDPRQueries.png)<br/>
    
## <a name="office-365-cloud-app-security-release-126"></a>Office 365 Cloud App Security Release 126

*Lanzado el 7 de julio de 2018* 
  
** [Revisión de seguridad de aplicaciones en la nube de Microsoft 126](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-126)**: 
  
- **Corrección automatizada para actividades sospechosas** Ahora puede establecer acciones de corrección automáticas para sesiones sospechosas desencadenadas por las directivas de detección de anomalías. Esta mejora le permite recibir alertas instantáneamente cuando se produce una infracción y aplicar acciones de gobierno de forma automática, como suspender al usuario. Para obtener más información, vea [directivas de detección de anomalías en Office 365 Cloud App Security](anomaly-detection-policies-in-ocas.md).
    
- **Detección automatizada de aplicaciones de OAuth de riesgo** Además de la investigación existente de las aplicaciones de OAuth conectadas a su entorno, Office 365 Cloud App Security ahora le permite configurar notificaciones automatizadas que le permitan saber cuándo una aplicación de OAuth cumple con determinados criterios. Por ejemplo, puede recibir alertas automáticamente cuando hay aplicaciones que requieren un alto nivel de permisos y están autorizadas por más de 50 usuarios. Para obtener más información, vea [Administrar aplicaciones de OAuth con Office 365 Cloud App Security](manage-app-permissions-in-ocas.md).
    
- **Compatibilidad con la administración de proveedores de servicios de seguridad administrada (MSSP)** Office 365 Cloud App Security ahora proporciona una mejor experiencia de administración a MSSPs y le permite configurar socios externos como administradores con cualquiera de los roles actualmente disponibles en Office 365 Cloud App Security. Además, los administradores con derechos de acceso a más de un inquilino ahora pueden dinamizar fácilmente entre los inquilinos. 
    
## <a name="office-365-cloud-app-security-release-124"></a>Office 365 Cloud App Security Release 124

*Lanzado el 10 de junio de 2018* 
  
** [Revisión de seguridad de aplicaciones en la nube de Microsoft 124](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-124)**: 
  
- **Implementaciones con ámbito** Las organizaciones empresariales pueden determinar de una granularidad qué usuarios deben supervisar y proteger en función de la pertenencia a grupos. Esta característica le permite seleccionar los usuarios cuyas actividades no se mostrarán para ninguna de las aplicaciones protegidas. La supervisión con ámbito es especialmente útil para el cumplimiento normativo y las licencias. Algunas regulaciones de cumplimiento requieren que se abstendrá de supervisar a usuarios de determinados países debido a la normativa local. Además, puede supervisar el menor número de usuarios que deben mantenerse dentro de los límites de las licencias de seguridad de aplicación de Office 365 Cloud. 
    
- **Nuevo servidor de correo electrónico** El servidor de correo electrónico para Office 365 Cloud App Security ha cambiado y usa diferentes intervalos de direcciones IP. Para asegurarse de que puede obtener notificaciones, agregue las nuevas direcciones IP a su lista blanca contra correo electrónico no deseado. Para las organizaciones que personalizan sus notificaciones, Cloud App Security lo habilita para usted con MailChimp, un servicio de correo electrónico de terceros. Para obtener la lista de direcciones IP del servidor de correo e instrucciones para habilitar el trabajo con MailChimp, consulte [requisitos de red (Microsoft Cloud App Security)](https://docs.microsoft.com/cloud-app-security/network-requirements) y [configuración de correo (seguridad de Microsoft Cloud APP)](https://docs.microsoft.com/cloud-app-security/mail-settings).
    
## <a name="office-365-cloud-app-security-release-121"></a>Office 365 Cloud App Security Release 121

*Lanzado el 6 de mayo de 2018* 
  
** [Revisión de seguridad de aplicaciones en la nube de Microsoft 121](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-121)**: 
  
- **Mejoras**en la Directiva de detección de anomalías. Las directivas de detección de anomalías de Office 365 Cloud App Security se han mejorado para incluir dos tipos nuevos de detección de amenazas que se implementan gradualmente: 
    
  - **Actividad de ransomware.** Las capacidades de detección de ransomware se amplían con la detección de anomalías para proporcionarle una cobertura más completa contra ataques de ataque de ransomware sofisticados. 
    
  - **Finalizó la actividad del usuario.** La actividad de los usuarios finalizada permite supervisar las cuentas de los usuarios terminados que se hayan desaprovisionado de las aplicaciones corporativas, pero que aún puedan tener acceso a determinados recursos corporativos. 
    
    para ver las [directivas de detección](anomaly-detection-policies-in-ocas.md)de anomalías, en el portal de seguridad de aplicaciones de nube de Office 365, seleccione **directivas**de **Control** \> .
    
## <a name="office-365-cloud-app-security-release-120"></a>Office 365 Cloud App Security Release 120

*Lanzado el 22 de abril de 2018* 
  
** [Revisión de seguridad de aplicaciones en la nube de Microsoft 120](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-120)**: 
  
- **Aplicaciones internas como actividades de usuario**. Para Office 365 y Azure Active Directory (Azure AD), ahora estamos implementando gradualmente la capacidad de detectar aplicaciones internas como actividades de cuenta de usuario realizadas por las aplicaciones Office 365 y Azure AD (internas y externas). Esto le permite crear directivas para que le avisen si una aplicación realiza actividades inesperadas y no autorizadas. 
    
- **Más campos en la exportación de la lista de aplicaciones de OAuth**. Al exportar una lista de aplicaciones de OAuth a CSV, se incluyen campos adicionales, como publicador, nivel de permisos y uso de la comunidad para ayudar con el proceso de cumplimiento e investigación. 
    
## <a name="office-365-cloud-app-security-release-119"></a>Office 365 Cloud App Security Release 119

*Lanzado el 1 de abril de 2018* 
  
** [Revisión de seguridad de aplicaciones en la nube de Microsoft 119](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-119)**: 
  
- **Mejoras en la detección en la nube**. La detección en la nube proporciona más información sobre las direcciones IP y los usuarios principales, lo que facilita la visualización de los detalles de uso de Office 365 y otras aplicaciones. Para obtener más información, consulte [revisar las conclusiones de detección de aplicaciones en Office 365 Cloud App Security](review-app-discovery-findings-in-ocas.md).
    
    ![Se ha actualizado el panel de detección en la nube](media/12712681-c0b3-4cb3-b7fd-2cf2ad4e825f.png)
  
## <a name="office-365-cloud-app-security-release-118"></a>Office 365 Cloud App Security Release 118

*Lanzado el 18 de marzo de 2018* 
  
** [Revisión de seguridad de aplicaciones en la nube de Microsoft 118](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-118)**: 
  
- **Compatibilidad con Barracuda**. La detección en la nube ahora admite firewalls de la serie de Barracuda y un flujo de registros Web de Firewall de la serie Barracuda. 
    
## <a name="office-365-cloud-app-security-release-117"></a>Office 365 Cloud App Security Release 117

*Lanzado el 6 de marzo de 2018* 
  
** [Revisión de seguridad de aplicaciones en la nube de Microsoft 117](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-117)**: 
  
- **i-compatibilidad con filtros**. Detección en la nube admite ahora i-FILTER. 
    
## <a name="office-365-cloud-app-security-release-116"></a>Office 365 Cloud App Security Release 116

*Lanzado el 18 de febrero de 2018* 
  
** [Revisión de seguridad de aplicaciones en la nube de Microsoft 116](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-116)**: 
  
- **Mejoras**en la Directiva de detección de anomalías. Las directivas de detección de anomalías de Office 365 Cloud App Security se mejoraron con detecciones basadas en escenarios nuevas, incluidas las de viajes imposibles, la actividad de una dirección IP sospechosa y varios intentos erróneos de inicio de sesión. Las nuevas directivas se habilitan automáticamente, lo que proporciona una detección de amenazas prepara el equipo en todo el entorno de la nube. Además, las nuevas directivas exponen más datos del motor de detección de seguridad de aplicación de nube de Office 365, lo que puede ayudar a acelerar el proceso de investigación y contener amenazas continuas. Para obtener más información, consulte el artículo de Microsoft Cloud App Security [y obtenga una detección de anomalías y análisis de comportamiento instantáneos](https://docs.microsoft.com/cloud-app-security/anomaly-detection-policy).
    
- **Compatibilidad del analizador de registros para formatos de punto de comprobación**. Los analizadores de registro de detección en la nube ahora admiten dos formatos de punto de comprobación adicionales: XML y KPC. 
    
## <a name="office-365-cloud-app-security-release-114"></a>Office 365 Cloud App Security Release 114

*Lanzado el 21 de enero de 2018* 
  
** [Revisión de seguridad de aplicaciones en la nube de Microsoft 114](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-114)**: 
  
- **Estado del servicio**. ahora puede comprobar el estado del servicio de seguridad de aplicaciones en la nube de Office 365 actual si va a **ayuda** \> **del estado del sistema**. 
    
    ![Haga clic \> en ayuda estado del sistema para ver el estado del sistema](media/2b496dac-ed9d-4480-83b6-85f9510d3aea.png)
  
- **Consultas personalizadas para el registro de actividades**. A partir de la versión 114, la capacidad de crear y guardar consultas personalizadas en el registro de actividades se está implementando gradualmente. Las consultas personalizadas permiten crear plantillas de filtro que se pueden volver a usar para realizar una investigación de Deep profundización. Además, se han agregado consultas sugeridas para proporcionar plantillas de investigación de un solo cuadro para filtrar las actividades y las aplicaciones detectadas. Las consultas sugeridas incluyen filtros personalizados para identificar riesgos como actividades de suplantación, actividades de administrador, aplicaciones de almacenamiento en la nube arriesgadas no compatibles, aplicaciones empresariales con cifrado poco seguro y riesgos de seguridad. Use las consultas sugeridas como punto de partida, modifíquelas según sea necesario y, a continuación, guárdelas como una consulta nueva. 
    
## <a name="office-365-cloud-app-security-release-113"></a>Office 365 Cloud App Security Release 113

*Lanzado el 8 de enero de 2018* 
  
** [Revisión de seguridad de aplicaciones en la nube de Microsoft 113](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-113)**: 
  
- **Compatibilidad del analizador de registros para formatos genéricos**. Los analizadores de registro de detección en la nube ahora admiten los siguientes formatos genéricos: LEEF, CEF y W3C. 

## <a name="related-topics"></a>Temas relacionados

[Novedades de Office 365 Cloud App Security](new-in-office-365-cas.md)

[Consulte las actualizaciones de 2017 para Office 365 Cloud App Security](new-in-office-365-cas-2017.md)
    
[Actividades de uso después de implementar Office 365 Cloud App Security](utilization-activities-for-ocas.md)