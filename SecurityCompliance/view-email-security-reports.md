---
title: Ver informes de seguridad de correo electrónico &amp; en el centro de seguridad y cumplimiento
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 03/19/2019
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 3a137e28-1174-42d5-99af-f18868b43e86
ms.collection:
- M365-security-compliance
description: Obtenga información sobre cómo buscar y usar informes de seguridad de correo electrónico para su organización con Office 365 Enterprise. Los informes de seguridad de correo electrónico están &amp; disponibles en el centro de seguridad y cumplimiento.
ms.openlocfilehash: 1a885661f5bf020c325ee2d9f084473ecb27c53a
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32268004"
---
# <a name="view-email-security-reports-in-the-security-amp-compliance-center"></a>Ver informes de seguridad de correo electrónico &amp; en el centro de seguridad y cumplimiento

Hay disponibles varios informes en el centro de [seguridad &amp; y cumplimiento](https://protection.office.com) para ayudarle a ver cómo las características de seguridad del correo electrónico, como las características contra correo electrónico no deseado, antimalware y de cifrado de Office 365 están protegiendo su organización. Si dispone de los [permisos necesarios](#what-permissions-are-needed-to-view-these-reports), puede ver estos informes en el centro de &amp; seguridad y cumplimiento desde el **** \> **Panel**de informes.
  
![Panel en el que se ve cómo está funcionando la protección contra amenazas avanzada](media/6b213d34-adbb-44af-8549-be9a7e2db087.png)
  
Los informes de seguridad de correo electrónico incluyen lo siguiente:
- [Informe](#encryption-report) de cifrado (Nueva)
- [Informe de estado de protección contra amenazas](#threat-protection-status-report) 
- [Informe de detecciones de malware](#malware-detections-report)    
- [Informe de malware principal](#top-malware-report)
- [Informe de remitentes y destinatarios principales](#top-senders-and-recipients-report)
- [Informe de detecciones de suPlantación de identidad](#spoof-detections-report)
- [Informe de detecciones de correo no deseado](#spam-detections-report)
- [Informe de correo electrónico enviado y recibido](#sent-and-received-email-report)
- [Informe de mensajes notificados por el usuario](#user-reported-messages-report)
    
## <a name="encryption-report"></a>Informe de cifrado

(**Nueva**) El **Informe** de cifrado muestra información sobre los mensajes de correo electrónico que se cifraron mediante directivas o los controles de usuario final. El equipo de seguridad de su organización puede usar esta información para identificar patrones y aplicar de forma proactiva o ajustar las directivas de los mensajes de correo electrónico confidenciales.

Para ver este informe, en el centro de seguridad & cumplimiento, vaya a **Informe**de cifrado de **Panel** \> de **informes** \> .

![Informe de cifrado](media/encryptionreport-defaultview.png) 

Cuando se abra el informe por primera vez, verá datos sobre los métodos de cifrado usados en los mensajes de correo electrónico de los últimos siete (7) días. Puede cambiar el intervalo de fechas y los detalles del informe haciendo clic en filtros en la esquina superior derecha de la pantalla.

![Filtros del informe de cifrado](media/encryptionreport-filters.png)   

También puede usar el menú desglosar por para ver los datos por plantilla de cifrado (o método).

![Método o plantilla de cifrado](media/encryptionreport-breakdownby.png)

Además, puede usar el menú Ver datos por para cambiar la vista para ver los recuentos de los mensajes cifrados a los cinco dominios destinatarios principales.

![Ver datos del informe de cifrado por menú](media/encryptionreport-viewdataby.png)

Con la flexibilidad del nuevo informe de cifrado, puede ver las tendencias y tomar las medidas adecuadas. Por ejemplo, si ve un gran número de mensajes de correo electrónico cifrados por los usuarios, es posible que desee agregar una directiva de cifrado para automatizar el cifrado para determinados casos de uso. (Para obtener ayuda con esto, vea [definir reglas de flujo de correo para cifrar mensajes de correo electrónico en Office 365](define-mail-flow-rules-to-encrypt-email.md)). Como otro ejemplo, si tiene varias plantillas de cifrado disponibles pero nadie las está usando, puede explorar si los usuarios necesitan formación para esa característica. 

Use este informe permite que el equipo de seguridad y cumplimiento de la organización supervise cómo se está usando el cifrado de mensajes y si se necesitan más acciones.

## <a name="threat-protection-status-report"></a>Informe de estado de protección contra amenazas

El informe de **Estado de protección contra amenazas** es un informe inteligente que muestra el correo electrónico malintencionado detectado y bloqueado por Exchange Online Protection. Este informe muestra información sobre el correo electrónico identificado como malware o como un intento de suplantación de identidad. 

> [!NOTE]
> Un informe de estado de protección contra amenazas está disponible para los clientes que tengan [Office 365 ATP](office-365-atp.md) o [Exchange Online Protection](eop/exchange-online-protection-eop.md) (EOP); sin embargo, la información que se muestra en el informe de estado de la protección contra amenazas para los clientes de ATP probablemente contendrá distintos datos de los que pueden ver los clientes de EOP. Por ejemplo, los clientes de EOP pueden ver información sobre malware detectado en el correo electrónico, pero no información sobre [los archivos malintencionados detectados en SharePoint Online, OneDrive o Microsoft Teams](atp-for-spo-odb-and-teams.md), una capacidad específica para ATP. ([Obtenga más información sobre los informes de ATP](view-reports-for-atp.md)).
  
Para ver este informe, en el [Centro &amp; de seguridad y cumplimiento](https://protection.office.com), vaya al **Panel** \> **informes** \> **Estado de protección contra amenazas**.
  
![Informe de estado de protección contra amenazas](media/0ff86e12-c2b2-4d89-92a5-cefb054dc070.png)
  
Al abrir por primera vez el informe de estado de protección contra amenazas, el informe muestra los datos de los últimos siete días de forma predeterminada; sin embargo, puede hacer clic en **filtros** y cambiar el intervalo de fechas de hasta 90 días de detalle. Este informe es útil para ver la eficacia y el impacto de las características de la protección de Exchange online de su organización, así como para las tendencias a largo plazo. 
  
![Filtros del informe de estado de protección contra amenazas](media/ab6b6b8d-e97a-4c3a-8fb1-c4940dcb7a07.png)
  
También puede elegir si desea ver los datos de correo electrónico identificado como malintencionado, correo electrónico identificado como intentos de suplantación de identidad (phishing) o correo electrónico identificado como malware que lo contiene.
  
![Opciones de vista del informe de estado de protección contra amenazas](media/d429ecd7-cb7a-4c99-8d27-79a2832cf467.png)
  
## <a name="malware-detections-report"></a>Informe de detecciones de malware

El informe de detecciones de **malware** muestra el número de mensajes entrantes y salientes que se detectaron que contenían malware para su organización. 
  
Para ver este informe, en el [Centro &amp; de seguridad y cumplimiento](https://protection.office.com), vaya a detecciones de **malware**del **Panel** \> de **informes** \> .
  
![Ejemplo de informe de detecciones de malware](media/a1ba61a3-565a-46d6-b0d5-6a6cff6b31d7.png)
  
De forma similar a otros informes, como el informe de estado de protección contra amenazas, el informe muestra los datos de los últimos siete días de manera predeterminada. Sin embargo, puede elegir **filtros** para cambiar el intervalo de fechas. 
  
## <a name="top-malware-report"></a>Informe de malware principal

El informe de **malware superior** muestra los distintos tipos de malware detectados por Exchange Online. 
  
Para ver este informe, en el [Centro &amp; de seguridad y cumplimiento](https://protection.office.com), vaya a **informes** \> de **malware superior**del **Panel** \> de informes.
  
![SCC-malware superior de EOP](media/763330b3-f56e-4ba4-b0bb-051500ae950a.png)
  
Cuando desplaza el puntero sobre una cuña del gráfico circular, puede ver el nombre de un tipo de malware y el número de mensajes que se detectaron como si tuvieran ese malware.
  
Haga clic (o puntee) en el informe para abrirlo en una nueva ventana del explorador, donde puede obtener una vista más detallada del informe.
  
![Este informe muestra el malware principal detectado para su organización](media/3fded224-fb31-4713-86f2-8afce5ce2991.png)
  
Debajo del gráfico, verá una lista de malware detectado y el número de mensajes que se detectaron como si tuvieran ese malware.
  
## <a name="top-senders-and-recipients-report"></a>Informe de remitentes y destinatarios principales

El informe de **remitentes y destinatarios principales** es un gráfico circular que muestra los remitentes de correo electrónico principales. 
  
Para ver este informe, en el [Centro &amp; de seguridad y cumplimiento](https://protection.office.com), vaya a los **destinatarios y remitentes principales**del **Panel** \> de **informes** \> .
  
![Para ver este informe, en el centro &amp; de seguridad y cumplimiento, vaya \> a \> informes de remitentes y destinatarios principales del panel de informes](media/b5506b5c-2420-4a5a-9ea3-d654294ac838.png)
  
Cuando desplaza el puntero sobre una cuña del gráfico circular, puede ver un recuento de los mensajes enviados o recibidos.
  
Haga clic (o puntee) en el informe para abrirlo en una nueva ventana del explorador, donde puede obtener una vista más detallada del informe.
  
Use la lista **Mostrar datos para** para elegir si desea ver los datos de los remitentes principales, los receptores, los destinatarios de correo no deseado y los destinatarios de malware. También puede ver quién recibió malware que se detectó con la protección contra amenazas avanzada. 
  
![Usar la lista Mostrar datos para para ver información específica](media/bd91449f-7d42-4749-8666-7b44044049b8.png)
  
Debajo del gráfico, verá quién eran los remitentes o destinatarios de correo electrónico principales, junto con un recuento de mensajes enviados o recibidos durante el período de tiempo especificado.
  
## <a name="spoof-detections-report"></a>Informe de detecciones de suPlantación de identidad

El informe de detecciones de suPlantación de **identidad** muestra el número de mensajes de correo falsificados que se han detectado y de aquellos que se consideran "buenos" (correo falsificado realizado por razones empresariales legítimas). 
  
Para ver este informe, en el [Centro &amp; de seguridad y cumplimiento](https://protection.office.com), vaya a **informes** \> de **correo falsificado**del **Panel** \> de informes.
  
![En el centro &amp; de seguridad y cumplimiento, vaya \> a \> informes de correo falsificado del panel de informes](media/0427e85c-9e40-4225-a0f0-e21a4e8b0e44.png)
  
Cuando se mantiene el puntero sobre un día del gráfico, puede ver cuántos mensajes de correo falsificado llegaron.
  
Haga clic (o puntee) en el informe para abrirlo en una nueva ventana del explorador, donde puede obtener una vista más detallada del informe.
  
## <a name="spam-detections-report"></a>Informe de detecciones de correo no deseado

El informe de detecciones de **correo no deseado** muestra todo el contenido de correo no deseado bloqueado por Exchange Online. 
  
Para ver este informe, en el [Centro &amp; de seguridad y cumplimiento](https://protection.office.com), vaya a detecciones de **correo no deseado**del **Panel** \> de **informes** \> .
  
![Para ver este informe, en el centro &amp; de seguridad y cumplimiento, vaya \> a \> informes de detección de correo no deseado de eop del panel informes](media/028cff3c-79ce-4ec0-8f0f-ec32ac28243a.png)
  
Al pasar el mouse sobre un día del gráfico, puede ver cuántos elementos se bloquearon ese día, así como la forma en que esos elementos se clasifican. Por ejemplo, puede ver cuántos mensajes de correo no deseado se filtraron y cuántos elementos procedían de una dirección de protocolo de Internet (IP) bloqueada.
  
Haga clic (o puntee) en el informe para abrirlo en una nueva ventana del explorador, donde puede obtener una vista más detallada del informe.
  
![El informe de detecciones de correo no deseado indica el número de mensajes de correo no deseado bloqueados o filtrados](media/370ec67d-eb30-4863-bfcf-68a41be02295.png)
  
Debajo del gráfico, verá una lista de elementos de correo no deseado que se detectaron. Seleccione un elemento para ver información adicional como, por ejemplo, si el elemento de correo no deseado era de entrada o de salida, su identificador de mensaje y su destinatario.
  
## <a name="sent-and-received-email-report"></a>Informe de correo electrónico enviado y recibido

El informe de **correo electrónico enviado y recibido** es un informe inteligente que muestra información sobre el correo electrónico entrante y saliente, incluidas las detecciones de correo no deseado, malware y el correo electrónico identificado como "bueno". 
  
Para ver este informe, en el [Centro &amp; de seguridad y cumplimiento](https://protection.office.com), vaya a **informes** \> **Panel** \> **enviados y recibidos**.
  
![Para ver este informe, en el centro &amp; de seguridad y cumplimiento, vaya \> a \> informes panel enviados y recibidos](media/0e710ed0-1b0e-4dac-8796-94a01a710f3a.png)
  
Al pasar el mouse sobre un día del gráfico, puede ver cuántos mensajes se han recibido y cómo se clasifican los mensajes. Por ejemplo, puede ver cuántos mensajes se han detectado como que contienen malware y cuántos se identificaron como correo no deseado.
  
Haga clic (o puntee) en el informe para abrirlo en una nueva ventana del explorador, donde puede obtener una vista más detallada del informe.
  
Puede usar la lista **desglosar por** para ver la información por tipo o por dirección (entrante y saliente). 
  
![Use la lista desglosar por para ver la información por tipo o por dirección.](media/a5b30c94-d75f-4bfc-851a-cb155685b177.png)
  
Debajo del gráfico, verá una lista de categorías de correo electrónico, como **GoodMail**, **SpamContentFiltered**, etc. Seleccione una categoría para ver información adicional, como las acciones que se tomaron para malware y si el correo electrónico se ha entrante o saliente.
  
![Este informe le indica sobre antimalware, contra correo no deseado y otras detecciones de mensajes](media/9ea4b606-f27a-46ee-97a7-be018e2b839c.png)
  
## <a name="user-reported-messages-report"></a>Informe de mensajes notificados por el usuario

El informe de **mensajes de** informes de usuario muestra información sobre los mensajes de correo electrónico que los usuarios han notificado como correo no deseado, intentos de suplantación de identidad (phishing) o correo correcto mediante el [complemento de mensajes de informe](enable-the-report-message-add-in.md).
  
Hay más detalles disponibles para cada mensaje, incluidos el motivo de la entrega, la excepción de la Directiva de correo no deseado o la regla de flujo de correo configurada para la organización. Para ver los detalles, seleccione un elemento de la lista de informes de usuarios y, a continuación, vea la información en las pestañas **Resumen** y **detalles** . 
  
![El informe de mensajes de informes de usuario muestra los usuarios etiquetados como correo no deseado, no deseado o intentos de suplantación de identidad.](media/ad5e9a3d-b833-419c-bcc9-3425d9604ead.png)
  
Para ver este informe, en el [Centro &amp; de seguridad y cumplimiento](https://protection.office.com), siga uno de estos procedimientos:
  
- Vaya a **mensajes de los que ha informado el usuario del** **Panel** \> de **Administración** \> de amenazas.
    
- Vaya a los mensajes de **revisión** \> de **Administración** \> de amenazas que ha **informado el usuario**.
    
![En el centro &amp; de seguridad y cumplimiento, elija \> mensajes \> de informe de usuario de revisión de administración de amenazas](media/e372c57c-1414-4616-957b-bc933b8c8711.png)
  
> [!IMPORTANT]
> Para que el informe de mensajes notificados por el usuario funcione correctamente, el **registro de auditoría debe estar activado** para su entorno de Office 365. Normalmente lo hace alguien que tiene el rol registros de auditoría asignado en Exchange Online. Para obtener más información, consulte [activar o desactivar la búsqueda de registros de auditoría de Office 365](turn-audit-log-search-on-or-off.md). 
  
## <a name="what-permissions-are-needed-to-view-these-reports"></a>¿Qué permisos se necesitan para ver estos informes?

Para poder ver y usar los informes descritos en este artículo, **debe tener asignada una función adecuada para el centro de &amp; seguridad y cumplimiento y el centro de administración de Exchange**.

- Para el centro &amp; de seguridad y cumplimiento, debe tener asignada una de las siguientes funciones:
    - Administración de la organización
    - Administrador de seguridad (puede asignarse en el centro de administración de Azure Active[https://aad.portal.azure.com](https://aad.portal.azure.com)Directory ()
    - Lector de seguridad

- Para Exchange Online, debe tener una de las siguientes funciones asignadas en el centro de administración de Exchange[https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)() o con cmdlets de PowerShell (vea [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)):
    - Administración de la organización
    - Administración de organización de solo lectura
    - Rol Destinatarios con permiso de vista
    - Administración de cumplimiento

Para obtener más información, vea los siguientes recursos:

- [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md)

- [Permisos de características de Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions)
   
   
## <a name="what-if-the-reports-arent-showing-data"></a>¿Qué ocurre si los informes no muestran datos?

Si no ve datos en los informes, compruebe que las directivas estén correctamente configuradas. Para obtener más información, consulte [protección contra correo electrónico no deseado y antimalware en Office 365](anti-spam-and-anti-malware-protection.md).
  
## <a name="related-topics"></a>Temas relacionados

[Protección contra correo no deseado de Office 365](anti-spam-protection.md)
  
[Informes y opiniones en el centro de seguridad &amp; y cumplimiento de Office 365](reports-and-insights-in-security-and-compliance.md)
  
[Crear una programación para un informe en el centro &amp; de seguridad y cumplimiento](create-a-schedule-for-a-report.md)
  
[Configurar y descargar un informe personalizado en el centro de &amp; seguridad y cumplimiento](set-up-and-download-a-custom-report.md)
  

