---
title: Información general del panel de seguridad
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 02/07/2019
ms.audience: ITPro
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: fe0b9b8f-faa9-44ff-8095-4d1b2f507b74
ms.collection: M365-security-compliance
description: Usar el nuevo panel de seguridad para revisar el estado de protección de amenaza de Office 365 y ver y actuar en las alertas de seguridad.
ms.openlocfilehash: 403c47ed09e9652a66abeafb93be02589c9b1702
ms.sourcegitcommit: efccf5b4f22d34a9674bc55ebf3d88bc8bda2972
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2019
ms.locfileid: "29995131"
---
# <a name="security-dashboard"></a>Panel de seguridad

## <a name="overview"></a>Información general

La [seguridad &amp; centro de cumplimiento](go-to-the-securitycompliance-center.md) permite a su organización administrar la protección de datos y cumplimiento de normas. Suponiendo que tenga los permisos necesarios, el panel de seguridad permite revisar el estado de protección de amenaza, así como ver y actuar en las alertas de seguridad. 
  
Vea el vídeo para obtener una visión general y, a continuación, lea este artículo para obtener más información.
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/3540b1f8-62d2-47fa-a07d-d7ad76f55b0f?autoplay=false]
  
Dependiendo de lo que incluye la suscripción de Office 365 de su organización, el panel de seguridad incluye varias widgets, como resumen de la administración de amenaza, estado de protección de amenaza, Global las detecciones de amenazas semanal, Malware y obtener más información, tal como se describe en el en las secciones siguientes.
  
Para ver el panel de seguridad, en la [Office 365 seguridad &amp; centro de cumplimiento](go-to-the-securitycompliance-center.md), vaya a **administración de amenaza** \> **panel**.
  
> [!NOTE]
> Debe ser un administrador global de Office 365, un administrador de seguridad o un lector de seguridad para ver el panel de seguridad. Algunos widgets requieren permisos adicionales para ver. Para obtener más información, vea [permisos en la seguridad de Office 365 &amp; centro de cumplimiento](permissions-in-the-security-and-compliance-center.md). 
  
## <a name="threat-management-summary"></a>Resumen de la administración de amenaza

El widget de resumen de la administración de amenazas le indica de un vistazo cómo su organización se ha protegido contra las amenazas durante los últimos siete (7) días.

![Panel de seguridad - widget de resumen de administración de amenaza](media/SecDash-ThreatMgmtSummary.png)

La información que aparecerá en el resumen de la administración de amenaza depende de lo que incluye la suscripción. En la siguiente tabla se describe qué información se incluye para Office 365 Enterprise E3 y Office 365 Enterprise E5.


|Office 365 Enterprise E3  |Office 365 Enterprise E5  |
|---------|---------|
|Mensajes de malware bloqueados<br/>Bloqueada de mensajes de suplantación de identidad<br>Mensajes que notifica a los usuarios<br><br><br><br> |Mensajes de malware bloqueados<br>Bloqueada de mensajes de suplantación de identidad<br>Mensajes que notifica a los usuarios<br>Malware de día cero bloqueado<br>Mensajes de suplantación de identidad avanzada detectados<br>Direcciones URL malintencionadas bloqueadas |

Para ver o tener acceso el widget de resumen de administración de amenaza, debe tener permisos para ver los informes de protección contra amenazas de avanzada. Para obtener más información, vea [¿qué permisos son necesarios para ver los informes de ATP?](view-reports-for-atp.md#what-permissions-are-needed-to-view-the-atp-reports). 

## <a name="threat-protection-status"></a>Estado de protección de amenaza

El widget de estado de protección de amenaza muestra la eficacia de la protección de amenaza con una vista detallada y tendencia de phishing y malware. 

![Widget de estado de protección de amenaza](media/tpswidget.png)

Los detalles dependen de si la suscripción a Office 365 incluye [Exchange Online Protection](eop/exchange-online-protection-eop.md) (EOP) con o sin [La protección de amenaza avanzada de Office 365](office-365-atp.md) (ATP).


|Si la suscripción incluye... |Verá estos detalles |
|---------|---------|
|Elevación de privilegios pero no ATP de Office 365     |Correo electrónico malintencionado que se ha detectado y bloqueado por elevación de privilegios<br> Vea [el informe de estado de protección de amenaza (EOP)](view-email-security-reports.md#threat-protection-status-report).| |
|ATP de Office 365 |Correo electrónico malintencionado de contenido y malintencionado detectados y bloqueados por elevación de privilegios y Office 365 ATP<br>Recuento de agregados de mensajes de correo electrónico único con contenido malintencionado bloqueado por el motor de protección contra malware, [Purgar cero horas automático](zero-hour-auto-purge.md)y características de ATP (incluidos [Vínculos seguros](atp-safe-links.md), [Los datos adjuntos seguros](atp-safe-attachments.md)y [ATP anti-phishing](atp-anti-phishing.md)).<br>Vea [el informe de estado de protección de amenaza (ATP)](view-reports-for-atp.md#threat-protection-status-report). | 

Para ver o tener acceso el widget de estado de protección de amenaza, debe tener permisos para ver los informes de protección contra amenazas de avanzada. Para obtener más información, vea [¿qué permisos son necesarios para ver los informes de ATP?](view-reports-for-atp.md#what-permissions-are-needed-to-view-the-atp-reports). 

## <a name="global-weekly-threat-detections"></a>Detecciones de amenazas semanal global
 
El widget Global detecciones de amenazas semanal muestra cómo muchas de las amenazas que se detectaron en los mensajes de correo electrónico durante los últimos siete (7) días.

![Widget de las detecciones de amenazas semanal global](media/globalweeklythreatdetections.png)

Las métricas se calculan tal como se describe en la siguiente tabla:

|Métrica  |Cómo se calcula  |
|---------|---------|
|Mensajes examinados |Número de mensajes de correo electrónico examinados multiplicado por el número de destinatarios |
|Amenazas que se ha detenido  |Número de mensajes de correo electrónico identificado como que contiene el malware multiplicado por el número de destinatarios |
|Bloqueado por [ATP](office-365-atp.md) |Número de mensajes de correo electrónico bloqueados por ATP multiplicado por el número de destinatarios |
|Ha quitado después de la entrega |Número de mensajes que se quitan por [cero horas automático purgar](zero-hour-auto-purge.md) multiplicado por el número de destinatarios |

## <a name="malware"></a>Malware

Widgets de malware mostrarán detalles sobre las tendencias de malware y los tipos de malware familia durante los últimos siete (7) días.

![Tendencias de malware y tipos de familia](media/malwarewidgetatpe5.png)
 
## <a name="insights"></a>Enfoques

Entendimiento de superficie no sólo las cuestiones clave que debe revisar, también incluyen recomendaciones y las acciones que se deben considerar. 

![Entendimiento de inteligente](media/smartinsights.png)

Por ejemplo, es posible que vea que se van a entregar los mensajes de correo electrónico de suplantación de identidad debido a que algunos usuarios deshabilitó sus opciones de correo electrónico no deseado. Para obtener más información acerca de cómo funcionan los conocimientos, vea [informes y conocimientos en la seguridad de Office 365 &amp; centro de cumplimiento](reports-and-insights-in-security-and-compliance.md).
  
## <a name="threat-intelligence"></a>Información sobre amenazas

Si la suscripción de su organización incluye [las capacidades de inteligencia de amenaza](office-365-ti.md), el panel de seguridad tiene una sección de **Información sobre amenazas** que incluye herramientas avanzadas. Equipo de seguridad de su organización puede usar la información de esta sección para comprender las campañas emergentes, investigar las amenazas y administrar los incidentes. 
  
![Información sobre amenazas le ayudará a comprender los ataques dirigidos a su organización](media/threatintelwidget.png)
  
  
## <a name="trends"></a>Tendencias

Cerca de la parte inferior del panel de seguridad es una sección de **tendencias** , que se resume las tendencias de flujo de correo electrónico para su organización. Informes proporcionan información acerca del correo electrónico pueden clasificado como correo no deseado, malware, los intentos de suplantación de identidad y correo electrónico buena. Haga clic en un mosaico para ver información más detallada en el informe. 
  
![La sección tendencias resume las tendencias de flujo de correo electrónico para la organización](media/trends.png)
  
Y, si la suscripción a Office 365 de su organización incluye [las capacidades de inteligencia de amenaza](office-365-ti.md), también tendrá un informe de **avisos de administración de amenazas recientes** en esta sección que permite a su equipo de seguridad para ver y tomar medidas alertas de seguridad de alta prioridad. 

Para ver o tener acceso el widget enviado y recibido correo electrónico, debe tener permisos para ver los informes de protección contra amenazas de avanzada. Para obtener más información, vea [¿qué permisos son necesarios para ver los informes de ATP?](view-reports-for-atp.md#what-permissions-are-needed-to-view-the-atp-reports). 

Para ver o tener acceso el widget de alertas de administración de amenazas recientes, debe tener permisos para ver las alertas. Para obtener más información, vea [permisos RBAC necesitan para ver las alertas](alert-policies.md#rbac-permissions-required-to-view-alerts).
  
## <a name="related-topics"></a>Temas relacionados

[Ver los informes de seguridad de correo electrónico de la seguridad &amp; centro de cumplimiento](view-email-security-reports.md)
  
[Visualización de informes para la protección de amenaza avanzada de Office 365](view-reports-for-atp.md)
  
[Protección contra amenazas avanzada de Office 365](office-365-atp.md)
  
[Inteligencia sobre amenazas de Office 365](office-365-ti.md)
  

