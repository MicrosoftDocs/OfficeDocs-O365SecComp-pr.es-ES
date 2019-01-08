---
title: Ver los informes de seguridad de correo electrónico de la seguridad &amp; centro de cumplimiento
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
ms.assetid: 3a137e28-1174-42d5-99af-f18868b43e86
description: Obtenga información sobre cómo buscar y usar informes de seguridad de correo electrónico para la organización con Office 365 Enterprise. Informes de seguridad de correo electrónico están disponibles en la seguridad &amp; centro de cumplimiento.
ms.openlocfilehash: 670317707c5695161f23615fb87fe93258e8d95b
ms.sourcegitcommit: 30faa3ba91cab4c36e3d8d8ed5858d5269ea8a56
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/08/2019
ms.locfileid: "27749334"
---
# <a name="view-email-security-reports-in-the-security-amp-compliance-center"></a>Ver los informes de seguridad de correo electrónico de la seguridad &amp; centro de cumplimiento

Una variedad de informes de seguridad de correo electrónico están disponibles en la [seguridad &amp; centro de cumplimiento](https://security.microsoft.com) que le ayudarán a ver cómo las características contra correo no deseado y antimalware en Office 365 protegen a la organización. Si tiene los [permisos necesarios](#what-permissions-are-needed-to-view-these-reports), puede ver estos informes en la seguridad &amp; centro de cumplimiento yendo a los **informes** \> **panel**.
  
![La seguridad &amp; panel del centro de cumplimiento puede ayudarle a ver dónde está trabajando avanzada de protección contra amenazas](media/6b213d34-adbb-44af-8549-be9a7e2db087.png)
  
Los informes de seguridad de correo electrónico son los siguientes:
  
- [Informe de estado de protección de amenaza](view-email-security-reports.md#tps) 
    
- [Informe de detecciones de malware](view-email-security-reports.md#maldet)
    
- [Informe de Malware superior](#top-malware-report)
    
- [Informe de remitentes y destinatarios principales](view-email-security-reports.md#topsenders)
    
- [Informe de correo de suplantación](#spoof-mail-report)
    
- [Informe de detecciones de correo electrónico no deseado](#spam-detections-report)
    
- [Informe de correo electrónico enviados y recibidos](view-email-security-reports.md#sentreceivedemail)
    
- [Informe de mensajes indicado por el usuario](view-email-security-reports.md#userreported) (nuevo)! 
    
## <a name="threat-protection-status-report"></a>Informe de estado de protección de amenaza

El nuevo informe de **Estado de protección de amenaza** es un informe inteligente que se muestra el correo electrónico malintencionado que se ha detectado y bloqueado por Exchange Online Protection. Este informe muestra información acerca del correo electrónico identificado como malware o un intento de suplantación de identidad. 

> [!NOTE]
> Un informe de estado de protección de amenaza está disponible para los clientes que tengan [Office 365 ATP](office-365-atp.md) o [Exchange Online Protection](eop/exchange-online-protection-eop.md) (EOP); Sin embargo, la información que se muestra en el informe de estado de protección de amenaza para los clientes de ATP probablemente contendrá datos distintos a lo que es posible que vea los clientes de EOP. Por ejemplo, los clientes de EOP pueden ver información sobre malware detectado en el correo electrónico, pero no información sobre [archivos malintencionados detectan en SharePoint Online, OneDrive o los equipos de Microsoft](atp-for-spo-odb-and-teams.md), una capacidad de ATP específicas. ([Más información acerca de los informes de ATP](view-reports-for-atp.md)).
  
Para ver este informe, en la [seguridad &amp; centro de cumplimiento](https://security.microsoft.com), vaya a **informes** \> **panel** \> **Estado de protección de amenaza**.
  
![Informe de estado de protección de amenaza](media/0ff86e12-c2b2-4d89-92a5-cefb054dc070.png)
  
La primera vez que se abre el informe de estado de protección de amenaza, el informe muestra datos de los últimos siete días de forma predeterminada; Sin embargo, puede haga clic en **filtros** y cambiar el intervalo de fechas de hasta 90 días de detalle. Este informe es útil para la visualización de la eficacia y el impacto de las características de protección en línea de Exchange de su organización y de tendencias a largo plazo. 
  
![Filtros del informe de estado de protección de amenaza](media/ab6b6b8d-e97a-4c3a-8fb1-c4940dcb7a07.png)
  
También puede elegir si de forma para ver los datos de correo electrónico que se identificó como malintencionado, correo electrónico o correo electrónico identificado como los intentos de suplantación de una identidad identifica como que contiene el malware.
  
![Opciones de vista de informe de estado de protección de amenaza](media/d429ecd7-cb7a-4c99-8d27-79a2832cf467.png)
  
## <a name="malware-detections-report"></a>Informe de detecciones de malware

El informe de **Detecciones de Malware** muestra el número de mensajes entrante y saliente se detectaron como que contiene el malware para su organización. 
  
Para ver este informe, en la [seguridad &amp; centro de cumplimiento](https://security.microsoft.com), vaya a **informes** \> **panel** \> **Detecciones de Malware**.
  
![Ejemplo de informe de detecciones de malware](media/a1ba61a3-565a-46d6-b0d5-6a6cff6b31d7.png)
  
Similar a otros informes, como el informe de estado de protección de amenaza, el informe muestra datos de los últimos siete días de forma predeterminada. Sin embargo, puede elegir **filtros** para cambiar el intervalo de fechas. 
  
## <a name="top-malware-report"></a>Informe de Malware superior

El informe de **Malware de la parte superior** muestra los distintos tipos de malware que se detectó por Exchange Online. 
  
Para ver este informe, en la [seguridad &amp; centro de cumplimiento](https://security.microsoft.com), vaya a **informes** \> **panel** \> **Malware de la parte superior**.
  
![SCC - principales de Malware de elevación de privilegios](media/763330b3-f56e-4ba4-b0bb-051500ae950a.png)
  
Cuando mantenga el mouse sobre una cuña en el gráfico circular, puede ver el nombre de un tipo de malware y el número de mensajes se detectaron como tener que el malware.
  
Haga clic en (o puntee) el informe para abrirlo en una nueva ventana del explorador, donde puede obtener una vista más detallada del informe.
  
![Este informe muestra las principales de malware detectado para su organización](media/3fded224-fb31-4713-86f2-8afce5ce2991.png)
  
Debajo del gráfico, verá una lista de malware detectado y cuántos mensajes se detectaron como tener que el malware.
  
## <a name="top-senders-and-recipients-report"></a>Informe de remitentes y destinatarios principales

El informe **principales remitentes y destinatarios** es un gráfico circular que muestra la lista de remitentes de correo electrónico superior. 
  
Para ver este informe, en la [seguridad &amp; centro de cumplimiento](https://security.microsoft.com), vaya a **informes** \> **panel** \> **principales remitentes y destinatarios**.
  
![Para ver este informe, en la seguridad &amp; centro de cumplimiento, vaya a informes \> panel \> principales remitentes y destinatarios](media/b5506b5c-2420-4a5a-9ea3-d654294ac838.png)
  
Cuando mantenga el mouse sobre una cuña en el gráfico circular, puede ver un recuento de los mensajes enviados o recibidos.
  
Haga clic en (o puntee) el informe para abrirlo en una nueva ventana del explorador, donde puede obtener una vista más detallada del informe.
  
Utilice la lista **Mostrar datos para** elegir si desea ver los datos para remitentes principales, receptores, de correo no deseado y los destinatarios de malware. También puede ver que recibió el malware que se detectó por avanzada de protección contra amenazas. 
  
![Use la lista Mostrar datos para ver información específica](media/bd91449f-7d42-4749-8666-7b44044049b8.png)
  
Debajo del gráfico, comprobará que los remitentes de correo electrónico superior o fueron de los destinatarios, junto con un recuento de los mensajes enviados o recibidos para el período de tiempo determinado.
  
## <a name="spoof-mail-report"></a>Informe de correo de suplantación

El informe de **Correo de suplantación de la** muestra se detectaron ¿cuántos mensajes de correo de suplantación de la y, de ellas, cuáles se consideran "bueno" (correo de suplantación hecho por razones de negocio legítimo). 
  
Para ver este informe, en la [seguridad &amp; centro de cumplimiento](https://security.microsoft.com), vaya a **informes** \> **panel** \> **Suplantación de correo**.
  
![Para ver este informe, en la seguridad &amp; centro de cumplimiento, vaya a informes \> panel \> suplantación de correo](media/0427e85c-9e40-4225-a0f0-e21a4e8b0e44.png)
  
Cuando mantenga el mouse sobre un día en el gráfico, puede ver cuántos mensajes de correo de suplantación de la suministrada a través de.
  
Haga clic en (o puntee) el informe para abrirlo en una nueva ventana del explorador, donde puede obtener una vista más detallada del informe.
  
## <a name="spam-detections-report"></a>Informe de detecciones de correo electrónico no deseado

El informe de **Detecciones de Spam** muestra todo el contenido de spam bloqueado por Exchange Online. 
  
Para ver este informe, en la [seguridad &amp; centro de cumplimiento](https://security.microsoft.com), vaya a **informes** \> **panel** \> **Detecciones de Spam**.
  
![Para ver este informe, en la seguridad &amp; centro de cumplimiento, vaya a informes \> panel \> detecciones de correo electrónico no deseado de elevación de privilegios](media/028cff3c-79ce-4ec0-8f0f-ec32ac28243a.png)
  
Cuando mantenga el mouse sobre un día en el gráfico, puede ver cuántos elementos se han bloqueado ese día, así como el modo en esos elementos se clasifican. Por ejemplo, puede ver cuántos mensajes de spam se han filtrado y cuántos elementos proceden de una dirección de protocolo de Internet (IP) bloqueados.
  
Haga clic en (o puntee) el informe para abrirlo en una nueva ventana del explorador, donde puede obtener una vista más detallada del informe.
  
![El informe de detecciones de correo electrónico no deseado le indica cuántos mensajes de spam se han bloqueado o filtran](media/370ec67d-eb30-4863-bfcf-68a41be02295.png)
  
Debajo del gráfico, verá una lista de elementos de spam que se detectaron. Seleccione un elemento para ver información adicional, por ejemplo, si el elemento de spam fue entrante o saliente, su identificador de mensaje y su destinatario.
  
## <a name="sent-and-received-email-report"></a>Informe de correo electrónico enviados y recibidos

El informe **enviado y recibido de correo electrónico** es un informe inteligente que muestra información sobre el correo electrónico entrante y saliente, incluidas las detecciones de spam, malware y correo electrónico identificado como "bueno". 
  
Para ver este informe, en la [seguridad &amp; centro de cumplimiento](https://security.microsoft.com), vaya a **informes** \> **panel** \> **enviado y recibido de correo electrónico**.
  
![Para ver este informe, en la seguridad &amp; centro de cumplimiento, vaya a informes \> panel \> enviados y correo electrónico recibido](media/0e710ed0-1b0e-4dac-8796-94a01a710f3a.png)
  
Cuando mantenga el mouse sobre un día en el gráfico, puede ver cuántos mensajes procede y cómo se clasifican los mensajes. Por ejemplo, puede ver cuántos mensajes se detectaron como que contiene el malware y cuántos se han identificado como correo no deseado.
  
Haga clic en (o puntee) el informe para abrirlo en una nueva ventana del explorador, donde puede obtener una vista más detallada del informe.
  
Puede usar la lista de **dividir por** para ver la información por tipo o por dirección (entrante y saliente). 
  
![Use la lista de interrupción hacia abajo por para ver la información de tipo o la dirección](media/a5b30c94-d75f-4bfc-851a-cb155685b177.png)
  
Debajo del gráfico, verá una lista de categorías de correo electrónico, como **GoodMail**, **SpamContentFiltered**y así sucesivamente. Seleccione una categoría para ver información adicional, como las acciones que se tomaron de malware y de correo electrónico si fue entrante o saliente.
  
![Este informe le informa sobre anti-malware, contra correo no deseado y detecciones de otros mensajes](media/9ea4b606-f27a-46ee-97a7-be018e2b839c.png)
  
## <a name="user-reported-messages-report-new"></a>Informe de mensajes indicado por el usuario (¡nuevo!)

El informe de **mensajes indicado por el usuario** muestra información sobre los mensajes de correo electrónico que los usuarios han informado como correo no deseado, los intentos de suplantación de identidad o correo correcto mediante el [complemento en el mensaje de informe](enable-the-report-message-add-in.md).
  
Detalles están disponibles para cada mensaje, incluidos el motivo de la entrega, como una excepción de la directiva de spam o regla de flujo de correo de su organización. Para ver los detalles, seleccione un elemento en la lista de informes de usuario y, a continuación, ver la información en las fichas **Resumen** y **Detalles** . 
  
![El informe de los mensajes de User-Reported muestra a los usuarios de los mensajes etiquetados como no deseado, no correo no deseado o suplantación de identidad intentos.](media/ad5e9a3d-b833-419c-bcc9-3425d9604ead.png)
  
Para ver este informe, en la [seguridad &amp; centro de cumplimiento](https://security.microsoft.com), siga uno de los siguientes procedimientos:
  
- Vaya a **administración de amenaza** \> **panel** \> **mensajes indicado por el usuario**.
    
- Vaya a **administración de amenaza** \> **revisión** \> **mensajes indicado por el usuario**.
    
![En la seguridad &amp; centro de cumplimiento, elija Administración de amenaza \> revisión \> mensajes indicado por usuario](media/e372c57c-1414-4616-957b-bc933b8c8711.png)
  
> [!IMPORTANT]
> En orden para que el informe de mensajes notificados por los usuarios para que funcione correctamente, **debe estar activado el registro de auditoría** para su entorno de Office 365. Normalmente, esto se realiza por una persona que tenga el rol de los registros de auditoría asignado en Exchange Online. Para obtener más información, vea [activar Office 365 de búsqueda de registros de auditoría activado o desactivado](turn-audit-log-search-on-or-off.md). 
  
## <a name="what-permissions-are-needed-to-view-these-reports"></a>¿Qué permisos son necesarios para ver estos informes?

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

Si no está viendo datos en los informes, vuelva a comprobar que sus directivas están configuradas correctamente. Para obtener más información, consulte [protección contra correo no deseado y antimalware en Office 365](anti-spam-and-anti-malware-protection.md).
  
## <a name="related-topics"></a>Temas relacionados

[Protección contra correo no deseado de Office 365](anti-spam-protection.md)
  
[Informes y conocimientos en la seguridad de Office 365 &amp; centro de cumplimiento](reports-and-insights-in-security-and-compliance.md)
  
[Crear una programación para un informe en la seguridad &amp; centro de cumplimiento](create-a-schedule-for-a-report.md)
  
[Configurar y descargar un informe personalizado en la seguridad &amp; centro de cumplimiento](set-up-and-download-a-custom-report.md)
  

