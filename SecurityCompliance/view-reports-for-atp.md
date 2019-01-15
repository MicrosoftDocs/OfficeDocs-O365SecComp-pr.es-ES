---
title: Visualización de informes para la protección de amenaza avanzada de Office 365
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 01/07/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: e47e838c-d99e-4c0b-b9aa-e66c4fae902f
description: Obtenga información sobre cómo buscar y usar informes para Office 365 avanzada protección contra amenazas en la seguridad &amp; centro de cumplimiento.
ms.openlocfilehash: a17f182f5c8d79e7863b26324a3c073ef18f14c9
ms.sourcegitcommit: 9034809b6f308bedc3b8ddcca8242586b5c30f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2019
ms.locfileid: "28014952"
---
# <a name="view-reports-for-office-365-advanced-threat-protection"></a>Visualización de informes para la protección de amenaza avanzada de Office 365

Si su organización tiene [La protección de amenaza avanzada de Office 365](office-365-atp.md) (ATP) y si tiene los [permisos necesarios](#what-permissions-are-needed-to-view-these-reports), puede usar varios informes de ATP en la seguridad &amp; centro de cumplimiento. (Vaya a **informes** \> **panel**.)
  
![La seguridad &amp; panel del centro de cumplimiento puede ayudarle a ver dónde está trabajando avanzada de protección contra amenazas](media/6b213d34-adbb-44af-8549-be9a7e2db087.png)
  
Informes de ATP incluyen el [informe de estado de protección de amenaza](#threat-protection-status-report), el [informe de tipos de archivo de ATP](#atp-file-types-report)y el [informe de eliminación de mensaje de ATP](#atp-message-disposition-report). En este artículo se describe los informes de ATP e incluye vínculos a [informes adicionales para ver](#additional-reports-to-view).
  
## <a name="threat-protection-status-report"></a>Informe de estado de protección de amenaza

El informe de **Estado de protección de amenaza** es una vista única que reúne información sobre malintencionado correo electrónico malintencionado y contenido detectados y bloqueados por [ATP de Office 365](office-365-atp.md)y [Exchange Online Protection](eop/exchange-online-protection-overview.md) (EOP). El informe proporciona un recuento agregado de mensajes de correo electrónico único con contenido malintencionado (archivos o direcciones de sitios Web (URL)) bloqueados por el motor de antimalware, [cero horas automático purgar (ZAP)](zero-hour-auto-purge.md)y las características de ATP, como [Vínculos seguros ATP](atp-safe-links.md), [ATP seguras Datos adjuntos](atp-safe-attachments.md)y [las funciones de ATP contra suplantación de identidad](atp-anti-phishing.md).

> [!NOTE]
> Un informe de estado de protección de amenaza está disponible para los clientes que tengan [Office 365 ATP](office-365-atp.md) o [Exchange Online Protection](eop/exchange-online-protection-eop.md) (EOP); Sin embargo, la información que se muestra en el informe de estado de protección de amenaza para los clientes de ATP probablemente contendrá datos distintos a lo que es posible que vea los clientes de EOP. Por ejemplo, el informe de estado de protección de amenaza para los clientes de ATP contendrá información sobre [archivos malintencionados detectan en SharePoint Online, OneDrive o los equipos de Microsoft](atp-for-spo-odb-and-teams.md). Dicha información es específica de ATP, por lo que los clientes que tienen EOP pero no ATP no verán los detalles de su informe de estado de protección de amenaza.
  
Para ver el informe de estado de protección de amenaza, en la [seguridad &amp; centro de cumplimiento](https://protection.office.com), vaya a **informes** \> **panel** \> **Estado de protección de amenaza**.
  
![Informe de estado de protección de amenaza ATP](media/6bdd41eb-62e0-423b-9fd4-d1d5baf0cbd5.png)
  
Para obtener el estado detallado de un día, mantenga el mouse sobre el gráfico.
  
![Datos de estado de protección de amenaza de ATP para un día](media/d5c2c6ad-c002-4985-a032-c866e46fdea8.png)
  
De forma predeterminada, el informe de estado de protección de amenaza muestra datos para los últimos siete días. Sin embargo, puede elegir **filtros** y cambiar el intervalo de fechas para ver los datos de hasta 90 días. 
  
![Filtros de estado de protección de amenaza ATP](media/4f703369-642b-402b-9758-b9c828283410.png)
  
También puede usar el menú **Ver datos por** para cambiar la información que se muestra en el informe. 
  
![Opciones de visualización para el informe de estado de protección de amenaza ATP](media/4959bf8c-d192-4542-b00b-184e101e7513.png)
  
## <a name="atp-file-types-report"></a>Informe de tipos de archivo de ATP

El informe de **Tipos de archivo de ATP** muestra el tipo de archivos detectados como malintencionado por [Los datos adjuntos seguros de ATP](atp-safe-attachments.md).
  
Para ver este informe, en la [seguridad &amp; centro de cumplimiento](https://protection.office.com), vaya a **informes** \> **panel** \> **ATP tipos de archivo**.
  
![Informe de tipos de archivo de ATP](media/6e3f5d33-79aa-4b2d-938c-6ef135d9e54c.png)
  
Cuando mantenga el mouse sobre un día determinado, puede ver el desglose de los tipos de archivos malintencionados que se detectaron por [Los datos adjuntos seguros de ATP](atp-safe-attachments.md) y [contra correo no deseado &amp; protección antimalware en Office 365](anti-spam-and-anti-malware-protection.md).
  
![Datos de informe de tipos de archivo de ATP para un día](media/10d18428-699a-41d2-a73e-be3a8214ada1.png)
  
## <a name="atp-message-disposition-report"></a>Informe de eliminación de mensaje ATP

El informe de **Eliminación de mensaje de ATP** muestra las acciones que se tomaron para mensajes de correo electrónico que se detectaron como tener contenido malintencionado. 
  
Para ver este informe, en la [seguridad &amp; centro de cumplimiento](https://protection.office.com), vaya a **informes** \> **panel** \> **ATP mensaje disposición**.
  
![Informe de eliminación de mensajes de ATP](media/b0ff65c4-53d3-496d-bafa-8937a5eb69e5.png)
  
Cuando mantenga el mouse sobre una barra en el gráfico, puede ver las acciones realizadas para el correo electrónico detectado para ese día.
  
![Datos de informe de eliminación de mensajes de ATP para un día](media/68d2beb8-4b30-48c4-8ba6-5e8ab88ae456.png)
  
## <a name="additional-reports-to-view"></a>Para ver los informes adicionales

Además de los informes de ATP que se describe en este artículo, varios otros informes están disponibles, tal como se describe en la siguiente tabla:


|Tipo de informe  |Más información  |
|---------|---------|
|**Informes de seguridad de correo electrónico**, como una parte superior remitentes y destinatarios informe, un informe de correo de suplantación de la y un informe de detecciones de correo electrónico no deseado. | [Ver los informes de seguridad de correo electrónico de la seguridad &amp; centro de cumplimiento](view-email-security-reports.md)        |
|**Explorador** (se conoce también como el Explorador de amenaza, esto se incluye en [Office 365 amenaza inteligencia](office-365-ti.md))     | [Use el explorador en la seguridad &amp; centro de cumplimiento](use-explorer-in-security-and-compliance.md)        |
|**Resultados de la elevación de privilegios y ATP** (Esto es un informe personalizado que generar mediante el uso de PowerShell). Este informe contiene información, como el dominio, fecha, tipo de evento, dirección, acción y recuento de mensajes.  | [Referencia del cmdlet Get-MailTrafficATPReport](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/get-mailtrafficatpreport?view=exchange-ps) |
|**Detecciones de elevación de privilegios y ATP** (Esto es un informe personalizado que generar mediante el uso de PowerShell). Este informe contiene detalles sobre archivos malintencionados o las direcciones URL, los intentos de suplantación de identidad, suplantación y otras posibles amenazas de correo electrónico o de archivos.   | [Referencia del cmdlet Get-MailDetailATPReport](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/get-maildetailatpreport?view=exchange-ps)        |

  
## <a name="what-permissions-are-needed-to-view-the-atp-reports"></a>¿Qué permisos son necesarios para ver los informes de ATP?

Para poder ver y usar los informes que se describen en este artículo, **debe tener una función adecuada asignada en ambos la seguridad &amp; centro de cumplimiento y el centro de administración de Exchange**.

- Para la seguridad &amp; centro de cumplimiento, debe tener uno de los siguientes roles asignados:
    - Administración de la organización
    - Administrador de seguridad
    - Lector de seguridad

- Para Exchange Online, debe tener uno de los siguientes roles asignados:
    - Administración de la organización
    - Administración de organización de solo lectura
    - Rol Destinatarios con permiso de vista
    - Administración de cumplimiento

Para obtener más información, vea los siguientes recursos:

- [Los permisos de la seguridad de Office 365 &amp; centro de cumplimiento](permissions-in-the-security-and-compliance-center.md)

- [Permisos de características de Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions)
   
## <a name="what-if-the-reports-arent-showing-data"></a>¿Qué ocurre si los informes no muestran los datos?

Si no está viendo datos en los informes de ATP, vuelva a comprobar que sus directivas están configuradas correctamente. Su organización debe tener [las directivas de ATP seguros vínculos](set-up-atp-safe-links-policies.md) y [datos adjuntos seguros de ATP directivas](set-up-atp-safe-attachments-policies.md) definidas en orden para la protección de ATP para estar en su lugar. Vea también la [protección contra correo no deseado y antimalware en Office 365](anti-spam-and-anti-malware-protection.md).
  
## <a name="related-topics"></a>Temas relacionados

[Informes y conocimientos en la seguridad de Office 365 &amp; centro de cumplimiento](reports-and-insights-in-security-and-compliance.md)
  
[Crear una programación para un informe en la seguridad &amp; centro de cumplimiento](create-a-schedule-for-a-report.md)
  
[Configurar y descargar un informe personalizado en la seguridad &amp; centro de cumplimiento](set-up-and-download-a-custom-report.md)
  

