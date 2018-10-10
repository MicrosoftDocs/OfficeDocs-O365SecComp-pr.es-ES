---
title: Visualización de informes para la protección de amenaza avanzada de Office 365
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: e47e838c-d99e-4c0b-b9aa-e66c4fae902f
description: Obtenga información sobre cómo buscar y usar informes para Office 365 avanzada protección contra amenazas en la seguridad &amp; centro de cumplimiento.
ms.openlocfilehash: 4a76c6a5b888142dc4c35af432fa61916145d648
ms.sourcegitcommit: 099bbfb1d16b251fd5cf18ec6515faaf9a989176
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/09/2018
ms.locfileid: "25454307"
---
# <a name="view-reports-for-office-365-advanced-threat-protection"></a>Visualización de informes para la protección de amenaza avanzada de Office 365

Si su organización tiene [La protección de amenaza avanzada de Office 365](office-365-atp.md) (ATP) y si tiene los [permisos necesarios](#what-permissions-are-needed-to-view-these-reports), puede usar varios informes de ATP en la seguridad &amp; centro de cumplimiento. (Vaya a **informes** \> **panel**.)
  
![La seguridad &amp; panel del centro de cumplimiento puede ayudarle a ver dónde está trabajando avanzada de protección contra amenazas](media/6b213d34-adbb-44af-8549-be9a7e2db087.png)
  
Informes de ATP incluyen el [informe de estado de protección de amenaza](#threat-protection-status-report), el [informe de tipos de archivo de ATP](#atp-file-types-report)y el [informe de eliminación de mensaje de ATP](#atp-message-disposition-report). En este artículo se describe los informes de ATP e incluye vínculos a [informes adicionales para ver](#additional-reports-to-view).
  
## <a name="threat-protection-status-report"></a>Informe de estado de protección de amenaza

El informe de **estado de protección de amenaza** es una vista única que reúne información sobre malintencionado correo electrónico malintencionado y contenido detectados y bloqueados por Exchange Online y avanzada de protección contra amenazas. El informe proporciona un recuento de mensajes de correo electrónico único con contenido malintencionado (archivos o direcciones URL) bloqueados por el motor de protección contra malware, [cero horas automático purgar (ZAP)](zero-hour-auto-purge.md)y las características de protección contra amenazas de avanzada, como [Vínculos seguros ATP](atp-safe-links.md), [ATP agregado Los datos adjuntos seguros](atp-safe-attachments.md)y [funciones de ATP contra suplantación de identidad en Office 365](atp-anti-phishing.md).
  
Para ver el informe de estado de protección de amenaza, en la seguridad &amp; centro de cumplimiento, vaya a **informes** \> **panel** \> **estado de protección de amenaza**.
  
![Informe de estado de protección de amenaza ATP](media/6bdd41eb-62e0-423b-9fd4-d1d5baf0cbd5.png)
  
Para obtener el estado detallado de un día, mantenga el mouse sobre el gráfico.
  
![Datos de estado de protección de amenaza de ATP para un día](media/d5c2c6ad-c002-4985-a032-c866e46fdea8.png)
  
De forma predeterminada, el informe de estado de protección de amenaza muestra datos para los últimos siete días. Sin embargo, puede elegir **filtros** y cambiar el intervalo de fechas para ver los datos de hasta 90 días. 
  
![Filtros de estado de protección de amenaza ATP](media/4f703369-642b-402b-9758-b9c828283410.png)
  
También puede usar el menú **Ver datos por** para cambiar la información que se muestra en el informe. 
  
![Opciones de visualización para el informe de estado de protección de amenaza ATP](media/4959bf8c-d192-4542-b00b-184e101e7513.png)
  
## <a name="atp-file-types-report"></a>Informe de tipos de archivo de ATP

El informe de **Tipos de archivo de ATP** muestra el tipo de archivos detectados como malintencionado por [Los datos adjuntos seguros de ATP](atp-safe-attachments.md).
  
Para ver este informe, en la seguridad &amp; centro de cumplimiento, vaya a **informes** \> **panel** \> **ATP tipos de archivo**.
  
![Informe de tipos de archivo de ATP](media/6e3f5d33-79aa-4b2d-938c-6ef135d9e54c.png)
  
Cuando mantenga el mouse sobre un día determinado, puede ver el desglose de los tipos de archivos malintencionados que se detectaron por [Los datos adjuntos seguros de ATP](atp-safe-attachments.md) y [contra correo no deseado &amp; protección antimalware en Office 365](anti-spam-and-anti-malware-protection.md).
  
![Datos de informe de tipos de archivo de ATP para un día](media/10d18428-699a-41d2-a73e-be3a8214ada1.png)
  
## <a name="atp-message-disposition-report"></a>Informe de eliminación de mensaje ATP

El informe de **Eliminación de mensaje de ATP** muestra las acciones que se tomaron para mensajes de correo electrónico que se detectaron como tener contenido malintencionado. 
  
Para ver este informe, en la seguridad &amp; centro de cumplimiento, vaya a **informes** \> **panel** \> **ATP mensaje disposición**.
  
![Informe de eliminación de mensajes de ATP](media/b0ff65c4-53d3-496d-bafa-8937a5eb69e5.png)
  
Cuando mantenga el mouse sobre una barra en el gráfico, puede ver las acciones realizadas para el correo electrónico detectado para ese día.
  
![Datos de informe de eliminación de mensajes de ATP para un día](media/68d2beb8-4b30-48c4-8ba6-5e8ab88ae456.png)
  
## <a name="additional-reports-to-view"></a>Para ver los informes adicionales

Además de los informes de ATP se describe en este artículo, [informes de seguridad de correo electrónico](view-email-security-reports.md) están disponibles en la seguridad &amp; centro de cumplimiento. Informes de seguridad de correo electrónico incluyen un [informe de los destinatarios y remitentes de la parte superior](view-email-security-reports.md#top-senders-and-recipients-report), un [informe de suplantación de correo](view-email-security-reports.md#spoof-mail-report), un [informe de detecciones de Spam](view-email-security-reports.md#spam-detections-report)y mucho más.
  
Y, si su organización tiene [Información sobre amenazas de Office 365](office-365-ti.md), también puede [Utilice el explorador en la seguridad &amp; centro de cumplimiento](use-explorer-in-security-and-compliance.md).
  
## <a name="what-permissions-are-needed-to-view-the-atp-reports"></a>¿Qué permisos son necesarios para ver los informes de ATP?

Para poder ver y usar los informes que se describen en este artículo, debe tener una función adecuada asignada en la seguridad &amp; centro de cumplimiento y en el centro de administración de Exchange.
  
|**Grupo de funciones**|**Punto de asignación**|**Obtener más información**|
|:-----|:-----|:-----|
| Uno de los siguientes:  <br/>  Administración de la organización  <br/>  Administrador de seguridad  <br/>  Lector de seguridad  <br/> |Seguridad &amp; centro de cumplimiento  <br/> |[Los permisos de la seguridad de Office 365 &amp; centro de cumplimiento](permissions-in-the-security-and-compliance-center.md) <br/> |
| Uno de los siguientes:  <br/>  Administración de la organización  <br/>  Administración de organización de solo lectura  <br/>  Rol Destinatarios con permiso de vista  <br/>  Administración de cumplimiento  <br/> |Centro de administración de Exchange  <br/> |[Permisos de características de Exchange Online](https://technet.microsoft.com/library/jj200673%28v=exchg.150%29.aspx) <br/> |
   
## <a name="what-if-the-reports-arent-showing-data"></a>¿Qué ocurre si los informes no muestran los datos?

Si no está viendo datos en los informes, vuelva a comprobar que sus directivas están configuradas correctamente. Su organización debe tener [las directivas de ATP seguros vínculos](set-up-atp-safe-links-policies.md) y [datos adjuntos seguros de ATP directivas](set-up-atp-safe-attachments-policies.md) definidas en orden para la protección de ATP para estar en su lugar. Vea también la [protección contra correo no deseado y antimalware en Office 365](anti-spam-and-anti-malware-protection.md).
  
## <a name="related-topics"></a>Temas relacionados

[Informes y conocimientos en la seguridad de Office 365 &amp; centro de cumplimiento](reports-and-insights-in-security-and-compliance.md)
  
[Crear una programación para un informe en la seguridad &amp; centro de cumplimiento](create-a-schedule-for-a-report.md)
  
[Configurar y descargar un informe personalizado en la seguridad &amp; centro de cumplimiento](set-up-and-download-a-custom-report.md)
  

