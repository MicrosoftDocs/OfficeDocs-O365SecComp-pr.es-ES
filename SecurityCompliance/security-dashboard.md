---
title: Introducción al panel de seguridad
ms.author: deniseb
author: denisebmsft
manager: laurawi
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: fe0b9b8f-faa9-44ff-8095-4d1b2f507b74
ms.collection:
- M365-security-compliance
description: Use el nuevo panel de seguridad para revisar el estado de la protección contra amenazas de Office 365 y vea y actúe en alertas de seguridad.
ms.openlocfilehash: 78e6a67ace757cca9d25086c601ab4b4437c7bf8
ms.sourcegitcommit: 5a93c2f3df35d06a59a7fbaff5c91f7afde11781
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/11/2019
ms.locfileid: "34857670"
---
# <a name="security-dashboard"></a>Panel de seguridad

## <a name="overview"></a>Información general

El [Centro &amp; de seguridad y cumplimiento](go-to-the-securitycompliance-center.md) permite que su organización administre el cumplimiento y la protección de datos. Suponiendo que tiene los permisos necesarios, el panel de seguridad le permite revisar el estado de la protección contra amenazas, así como ver y actuar en alertas de seguridad. 
  
Vea el vídeo para obtener información general y lea este artículo para obtener más información.
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1VV3o]
  
Dependiendo de lo que incluya la suscripción de Office 365 de la organización, el panel de seguridad incluye varios widgets, como Resumen de administración de amenazas, estado de la protección contra amenazas, detecciones de amenazas semanales globales, malware y más, tal y como se describe en la siguientes secciones.
  
Para ver el panel de seguridad, en [el centro de &amp; seguridad y cumplimiento de Office 365](go-to-the-securitycompliance-center.md), vaya a **Panel**de **Administración** \> de amenazas.
  
> [!NOTE]
> Debe ser un administrador global de Office 365, un administrador de seguridad o un lector de seguridad para ver el panel de seguridad. Algunos widgets requieren permisos adicionales para ver. Para obtener más información, consulte Permissions [in the &amp; Office 365 Security Compliance Center](permissions-in-the-security-and-compliance-center.md). 
  
## <a name="threat-management-summary"></a>Resumen de administración de amenazas

El widget de Resumen de administración de amenazas le indica de un vistazo cómo su organización estuvo protegida contra amenazas durante los últimos siete (7) días.

![Panel de seguridad: widget de Resumen de administración de amenazas](media/SecDash-ThreatMgmtSummary.png)

La información que verá en el Resumen de administración de amenazas depende de lo que incluya la suscripción. En la tabla siguiente se describe la información que se incluye para Office 365 E3 y Office 365 E5.


|Office 365 E3  |Office 365 E5  |
|---------|---------|
|Mensajes de malware bloqueados<br/>Mensajes de suplantación bloqueados<br>Mensajes notificados por los usuarios<br><br><br><br> |Mensajes de malware bloqueados<br>Mensajes de suplantación bloqueados<br>Mensajes notificados por los usuarios<br>Malware de cero días bloqueado<br>Mensajes de suplantación de identidad avanzada detectados<br>URL malintencionadas bloqueadas |

Para ver o acceder al widget de Resumen de administración de amenazas, debe tener permisos para ver los informes de protección contra amenazas avanzada. Para obtener más información, consulte [¿Qué permisos se necesitan para ver los informes de ATP?](view-reports-for-atp.md#what-permissions-are-needed-to-view-the-atp-reports). 

## <a name="threat-protection-status"></a>Estado de la protección contra amenazas

El widget de estado de protección contra amenazas muestra la efectividad de la protección contra amenazas con una vista de tendencias y detalles de phish y malware. 

![Widget de estado de protección contra amenazas](media/tpswidget.png)

Los detalles dependen de si la suscripción a Office 365 incluye [Exchange Online Protection](eop/exchange-online-protection-eop.md) (EOP) con o sin [Office 365 protección contra amenazas avanzada](office-365-atp.md) (ATP).


|Si su suscripción incluye... |Verá estos detalles |
|---------|---------|
|EOP pero no Office 365 ATP     |Correo electrónico malintencionado detectado y bloqueado por EOP<br> Consulte [Informe de estado de protección contra amenazas (EOP)](view-email-security-reports.md#threat-protection-status-report).| |
|Office 365 ATP |Contenido malintencionado y correo electrónico malintencionado detectados y bloqueados por EOP y a ATP de Office 365<br>Recuento agregado de mensajes de correo electrónico únicos con contenido malintencionado bloqueado por el motor antimalware, la depuración [automática de cero horas](zero-hour-auto-purge.md)y las características de ATP (incluidos [vínculos seguros](atp-safe-links.md), [datos adjuntos seguros](atp-safe-attachments.md)y [protección contra phishing ATP](atp-anti-phishing.md)).<br>Consulte [Informe de estado de protección contra amenazas (ATP)](view-reports-for-atp.md#threat-protection-status-report). | 

Para ver o acceder al widget de estado de protección contra amenazas, debe tener permisos para ver los informes de protección contra amenazas avanzada. Para obtener más información, consulte [¿Qué permisos se necesitan para ver los informes de ATP?](view-reports-for-atp.md#what-permissions-are-needed-to-view-the-atp-reports). 

## <a name="global-weekly-threat-detections"></a>Detecciones de amenazas semanales globales
 
El widget global Week Threat DETECTIONS muestra el número de amenazas que se detectaron en los mensajes de correo electrónico en los últimos siete (7) días.

![Widget de detección de amenazas semanal global](media/globalweeklythreatdetections.png)

Las métricas se calculan como se describe en la siguiente tabla:

|Biometría  |Cómo se calcula  |
|---------|---------|
|Mensajes examinados |Número de mensajes de correo electrónico examinados multiplicado por el número de destinatarios |
|Amenazas detenidas  |Número de mensajes de correo electrónico identificados como que contienen malware multiplicado por el número de destinatarios |
|Bloqueado por [ATP](office-365-atp.md) |Número de mensajes de correo electrónico bloqueados por ATP multiplicado por el número de destinatarios |
|Eliminado tras la entrega |Número de mensajes eliminados por [purga automática de cero horas](zero-hour-auto-purge.md) multiplicado por el número de destinatarios |

## <a name="malware"></a>Malware

Los widgets de malware muestran detalles sobre las tendencias de malware y los tipos de familia de malware en los últimos siete (7) días.

![Tendencias de malware y tipos de familia](media/malwarewidgetatpe5.png)
 
## <a name="insights"></a>Información

Información no solo aspectos clave de la superficie que debe revisar también incluyen recomendaciones y acciones a tener en cuenta. 

![Información inteligente](media/smartinsights.png)

Por ejemplo, es posible que vea que se están entregando mensajes de correo electrónico de suplantación de identidad porque algunos usuarios han deshabilitado las opciones de correo no deseado. Para obtener más información acerca de cómo funcionan las ideas, consulte Reports [and Insights in the Office &amp; 365 Security Compliance Center](reports-and-insights-in-security-and-compliance.md).
  
## <a name="threat-investigation-and-response"></a>Investigación y respuesta de amenazas

Si la suscripción de su organización incluye [Office 365 Advanced Threat Protection Plan 2](office-365-ti.md), el panel de seguridad tiene una sección que incluye herramientas avanzadas de investigación y respuesta de amenazas. El equipo de seguridad de su organización puede usar la información de esta sección para comprender las campañas emergentes, investigar las amenazas y administrar los incidentes. 
  
![La inteligencia sobre amenazas ayuda a comprender los ataques dirigidos a la organización](media/threatintelwidget.png)
  
  
## <a name="trends"></a>Tendencias

Cerca de la parte inferior del panel de seguridad hay una sección **tendencias** que resume las tendencias del flujo de correo electrónico para su organización. Los informes proporcionan información sobre el correo electrónico clasificado como correo no deseado, malware, intentos de phishing y buen correo electrónico. Haga clic en un icono para ver información más detallada en el informe. 
  
![La sección tendencias resume las tendencias del flujo de correo electrónico para la organización](media/trends.png)
  
Y, si la suscripción a Office 365 de su organización incluye [office 365 plan de protección contra amenazas avanzada 2](office-365-ti.md), también tendrá un informe de **alertas de administración de amenazas reciente** en esta sección que permite al equipo de seguridad ver y realizar acciones en alertas de seguridad de alta prioridad. 

Para ver o acceder al widget de correo electrónico enviado y recibido, debe tener permisos para ver los informes de protección contra amenazas avanzada. Para obtener más información, consulte [¿Qué permisos se necesitan para ver los informes de ATP?](view-reports-for-atp.md#what-permissions-are-needed-to-view-the-atp-reports). 

Para ver o acceder al widget de alertas de administración de amenazas reciente, debe tener permisos para ver las alertas. Para obtener más información, consulte [permisos de RBAC necesarios para ver las alertas](alert-policies.md#rbac-permissions-required-to-view-alerts).
  
## <a name="related-topics"></a>Temas relacionados

[Ver informes de seguridad de correo electrónico &amp; en el centro de seguridad y cumplimiento](view-email-security-reports.md)
  
[Ver informes para la protección contra amenazas avanzada de Office 365](view-reports-for-atp.md)
  
[Protección contra amenazas avanzada de Office 365](office-365-atp.md)
  
[Respuesta y investigación de amenazas de Office 365](office-365-ti.md)
  

