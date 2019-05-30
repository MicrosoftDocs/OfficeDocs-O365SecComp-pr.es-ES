---
title: Explorador de amenazas (y detecciones en tiempo real)
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 05/22/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 82ac9922-939c-41be-9c8a-7c75b0a4e27d
ms.collection:
- M365-security-compliance
description: Obtenga información sobre el explorador (y las detecciones en tiempo real) &amp; en el centro de seguridad y cumplimiento.
ms.openlocfilehash: 030f866c5e86daa3dc543bddae7152e19f377d3b
ms.sourcegitcommit: 6c0fcb82178a4ac26375545f328389a6852a81be
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/28/2019
ms.locfileid: "34490536"
---
# <a name="threat-explorer-and-real-time-detections"></a>Explorador de amenazas (y detecciones en tiempo real)

Si su organización tiene [office 365 Advanced Threat Protection](office-365-atp.md) (Office 365 ATP) y dispone de los [permisos necesarios](#required-licenses-and-permissions), tendrá un **Explorador** o detecciones en **tiempo real** (anteriormente informes en *tiempo real* , [consulte ](#new-features-in-real-time-detections)novedades). En el centro de seguridad & cumplimiento, vaya a **Administración de amenazas**y, a continuación, elija **Explorador** o **detecciones en tiempo real**. 

|Con el plan ATP 2, verá:  |Con el plan ATP 1, verá:  |
|---------|---------|
|![Explorador de amenazas](media/threatmgmt-explorer.png)      |![Detecciones en tiempo real](media/threatmgmt-realtimedetections.png)         |

Con el explorador (o detecciones en tiempo real), dispone de un informe eficaz que permite al equipo de operaciones de seguridad investigar y responder a las amenazas con eficacia y eficiencia, y es similar a la siguiente imagen: 

![Ir al explorador de \> administración de amenazas](media/cab32fa2-66f1-4ad5-bc1d-2bac4dbeb48c.png)

Con este informe, puede:
- [Ver malware detectado por las características de seguridad de Office 365](#see-malware-detected-in-email-by-technology)
- [Ver datos sobre direcciones URL de suplantación de identidad y hacer clic en veredicto](#view-data-about-phishing-urls-and-click-verdict)
- [Iniciar un proceso de investigación y respuesta automatizado desde una vista en el explorador](#start-automated-investigation-and-response) (Solo planeación ATP 2)
- ... [Investigue el correo electrónico malintencionado y mucho más](#more-ways-to-use-explorer-or-real-time-detections).

## <a name="new-features-in-real-time-detections"></a>Nuevas características en detecciones en tiempo real

Para los clientes de Office 365 ATP plan 1, el informe de detecciones en *tiempo real* se denominaba anteriormente *informes en tiempo real*. Además del cambio de nombre, se están implementando varias características y mejoras nuevas:

- En la vista phish, puede ver más detalles sobre las URL detectadas a través de los [vínculos seguros ATP](atp-safe-links.md). Los nuevos detalles y capacidades incluyen:
  - Direcciones URL en mensajes de correo electrónico
  - Filtrado basado en la información de dirección URL
  - Información de dirección URL que se muestra en los gráficos de datos
  - Tiempo de clic en datos sobre los clics en los mensajes

- Siempre que haya un cambio en una dirección URL haga clic en veredicto, verá una alerta. Hacer clic en los veredictos pueden cambiar cuando la reputación de la dirección URL cambia después de la detonación o cuando un usuario que está protegido por vínculos seguros de ATP invalida una [Advertencia de vínculos seguros de ATP](atp-safe-links-warning-pages.md).  
 
Estas mejoras permiten a los administradores de seguridad de su organización ver más detalles que antes. Los administradores de seguridad pueden ver información sobre los dominios de dirección URL, las direcciones URL perdidas, los veredictos y más y, a continuación, ajustar las directivas de ATP de Office 365 correctamente.

> [!NOTE]
> Aunque estas características se encuentran en versión preliminar, los datos de URL estarán disponibles durante un número limitado de días. 

## <a name="see-malware-detected-in-email-by-technology"></a>Ver malware detectado en correo electrónico por tecnología

Supongamos que desea ver el malware detectado en el correo electrónico con la tecnología de Office 365. Para ello, use la vista [email _GT_ malware](threat-explorer-views.md#email--malware) View of Explorer (o detección en tiempo real).

1. En el centro de seguridad & cumplimiento[https://protection.office.com](https://protection.office.com)(), elija **Threat Management** > **Explorer** (o **detecciones en tiempo real**). (En este ejemplo se usa el explorador).

2. En el **menú Ver** , elija**malware**de **correo electrónico** > .<br/>![Menú Ver para el explorador](media/ExplorerViewEmailMalwareMenu.png)<br/>

3. Haga clic en **remitente**y, a continuación, elija**tecnología de detección** **básica** > .<br/>Las tecnologías de detección están ahora disponibles como filtros para el informe.<br/>![Tecnologías de detección de malware](media/ExplorerEmailMalwareDetectionTech.png)<br/> 

4. Seleccione una opción y, a continuación, haga clic en el botón **Actualizar** para aplicar ese filtro.<br/>![Tecnología de detección seleccionada](media/ExplorerEmailMalwareDetectionTechATP.png)<br/> 

El informe se actualiza para mostrar el malware de resultados detectado en el correo electrónico, usando la opción de tecnología que seleccionó. Desde aquí, puede realizar análisis adicionales.

## <a name="view-data-about-phishing-urls-and-click-verdict"></a>Ver datos sobre direcciones URL de suplantación de identidad y hacer clic en veredicto

Supongamos que desea ver los intentos de suplantación de identidad mediante direcciones URL en el correo electrónico, incluida una lista de direcciones URL que se han permitido, bloqueado y reemplazado. La identificación de las direcciones URL en las que se hizo clic requiere que se configuren los [vínculos seguros de ATP](atp-safe-links.md) . Asegúrese de haber configurado [las directivas de vínculos seguros de ATP](set-up-atp-safe-links-policies.md) para la protección del tiempo de clic y el registro de los veredictos de clics por medio de vínculos seguros de ATP. 

Para revisar las direcciones URL de phish en mensajes y hacer clic en direcciones URL en mensajes de Phish, use el [correo electrónico _GT_ phish](threat-explorer-views.md#email--phish) View of Explorer (o detección en tiempo real).

1. En el centro de seguridad & cumplimiento[https://protection.office.com](https://protection.office.com)(), elija **Threat Management** > **Explorer** (o **detecciones en tiempo real**). (En este ejemplo se usa el explorador).

2. En el **menú Ver** , elija**phishing**de **correo electrónico** > .<br/>![Menú Ver para el explorador](media/ExplorerViewEmailPhishMenu.png)<br/>

3. Haga clic en **remitente**y, a continuación, elija **direcciones URL** > ,**haga clic en veredicto**.

4. Seleccione una o más opciones, como **bloqueada** y **bloque**invalidado y, a continuación, haga clic en el botón **Actualizar** que se encuentra en la misma línea que las opciones para aplicar ese filtro. (No actualice la ventana del explorador).<br/>![Direcciones URL y haga clic en veredictos](media/ThreatExplorerEmailPhishClickVerdictOptions.png)<br/>

    El informe se actualiza para mostrar dos tablas de direcciones URL diferentes en la ficha dirección URL del informe:

   1. Las **direcciones URL principales** son las que se encuentran en los mensajes que se han filtrado y la acción de entrega de correo electrónico se recuento para cada dirección URL. En la vista correo phish, esta lista normalmente contendrá direcciones URL legítimas. Los atacantes incluyen una mezcla de direcciones URL buenas y incorrectas en sus mensajes para intentar entregarlos, pero harán que los vínculos malintencionados sean más interesantes para el usuario hacer clic en. La tabla de direcciones URL se ordena por recuento de correo electrónico total (Nota: esta columna no se muestra para simplificar la vista).

   2. Los **clics principales** son las direcciones URL contenidas en vínculos seguros en las que se hizo clic, ordenadas por número total de clics (esta columna tampoco se muestra para simplificar la vista). Número total de recuentos por columna indique los vínculos seguros haga clic en recuento de veredictos para cada dirección URL con clic. En la vista de correo electrónico phish, estos son direcciones URL sospechosas o malintencionadas, pero pueden incluir direcciones URL limpias que estén en mensajes de suplantación. Los clics de dirección URL en vínculos desajustados no se mostrarán aquí.
   
   Las dos tablas URL muestran las direcciones URL principales en los correos electrónicos de suplantación de identidad por acción y ubicación de entrega, y muestran los clics en direcciones URL que se bloquearon (o visitaron a pesar de una advertencia) para que pueda comprender los posibles vínculos no válidos que los usuarios han recibido e interactúan con los usuarios. Desde aquí, puede realizar análisis adicionales. Por ejemplo, debajo del gráfico, puede ver las direcciones URL principales en los correos electrónicos que se bloquearon en el entorno de su organización.
   
   ![URL del explorador que se bloquearon](media/ExplorerPhishClickVerdictURLs.png)
   
   Seleccione una dirección URL para ver información más detallada. Tenga en cuenta que en el cuadro de diálogo de URL flotante, se quita el filtrado en los correos electrónicos para mostrar la vista completa de la exposición de la dirección URL en el entorno. Esto le permite filtrar los correos electrónicos en el explorador a los que le interesa, encontrar direcciones URL específicas que son posibles amenazas y, a continuación, ampliar la comprensión de la exposición de URL en su entorno (a través del cuadro de diálogo de detalles de URL) sin tener que agregar filtros de URL al Vista del explorador.

## <a name="review-email-messages-reported-by-users"></a>Revisar los mensajes de correo electrónico enviados por los usuarios

Supongamos que desea ver los mensajes de correo electrónico que los usuarios de la organización han notificado como correo no deseado, correo no deseado o suplantación de identidad mediante el [complemento de mensajes de informe para Outlook y Outlook en la web](enable-the-report-message-add-in.md). Para ello, use la vista de [correo electrónico >](threat-explorer-views.md#email--user-reported) del explorador (o detecciones en tiempo real) que ha notificado al usuario.

1. En el centro de seguridad & cumplimiento[https://protection.office.com](https://protection.office.com)(), elija **Threat Management** > **Explorer** (o **detecciones en tiempo real**). (En este ejemplo se usa el explorador).

2. En el menú **Ver** , elija **correo electrónico** > notificado por el**usuario**.<br/>![Menú Ver para el explorador](media/ExplorerViewMenuEmailUserReported.png)<br/>

3. Haga clic en **remitente**y, a continuación, elija**tipo de informe** **básico** > .

4. Seleccione una opción, como **phish**y, a continuación, haga clic en el botón **Actualizar** . <br/>![Phish notificados por el usuario](media/EmailUserReportedReportType.png)<br/> 

El informe se actualiza para Mostrar datos sobre los mensajes de correo electrónico que las personas de su organización han notificado como un intento de suplantación de identidad. Puede usar esta información para realizar análisis adicionales y, si es necesario, ajustar las [directivas antiphishing de ATP](set-up-anti-phishing-policies.md).

## <a name="start-automated-investigation-and-response"></a>Iniciar investigación y respuesta automatizadas

> [!NOTE]
> Las capacidades de investigación y respuesta automatizadas están disponibles en **office 365 ATP plan 2** y **Office 365 E5**.

(Nueva) La [investigación y la respuesta automatizadas](automated-investigation-response-office.md) pueden guardar el equipo de operaciones de seguridad con mucho tiempo y esfuerzo en la investigación y mitigación de ataques cibernéticos. Además de configurar alertas que pueden desencadenar una guía de seguridad, puede iniciar un proceso de investigación y respuesta automatizado desde una vista en el explorador. 

Para obtener más información sobre esto, consulte [ejemplo: un administrador de seguridad desencadena una investigación desde el explorador](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer).

## <a name="more-ways-to-use-explorer-or-real-time-detections"></a>Más formas de usar Explorer (o detecciones en tiempo real)

Además de los escenarios descritos en este artículo, tiene muchas más opciones de informes disponibles con el explorador (o detecciones en tiempo real). 
- [Buscar e investigar el correo electrónico malintencionado que se ha entregado](investigate-malicious-email-that-was-delivered.md)
- [Ver archivos malintencionados detectados en SharePoint Online, OneDrive y Microsoft Teams](malicious-files-detected-in-spo-odb-or-teams.md)
- [Obtener información general sobre las vistas en el explorador de amenazas (y detecciones en tiempo real)](threat-explorer-views.md)

## <a name="required-licenses-and-permissions"></a>Permisos y licencias necesarios

Debe tener [Office 365 ATP](office-365-atp.md) para obtener detecciones de Internet Explorer o en tiempo real.
- Explorer se incluye en el plan 2 de ATP de Office 365. 
- El informe de detecciones en tiempo real se incluye en el plan 1 de ATP de Office 365.

Para ver y usar el explorador o las detecciones en tiempo real, debe tener los permisos adecuados, como los que se han concedido a un administrador de seguridad o un lector de seguridad. 

- Para el centro &amp; de seguridad y cumplimiento, debe tener asignada una de las siguientes funciones:
    - Administración de la organización
    - Administrador de seguridad (puede asignarse en el centro de administración de Azure Active[https://aad.portal.azure.com](https://aad.portal.azure.com)Directory ())
    - Lector de seguridad

- Para Exchange Online, debe tener una de las siguientes funciones asignadas en el centro de administración de Exchange[https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)() o con cmdlets de PowerShell (vea [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)):
    - Administración de la organización
    - Administración de organización de solo lectura
    - Rol Destinatarios con permiso de vista
    - Administración de cumplimiento

Para obtener más información acerca de los roles y los permisos, vea los siguientes recursos:

- [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md)
- [Permisos de características de Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions)
  
