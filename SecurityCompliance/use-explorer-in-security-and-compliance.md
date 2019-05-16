---
title: Usar el explorador de amenazas en &amp; el centro de seguridad y cumplimiento
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 03/31/2019
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
description: Obtenga información sobre el explorador (también denominado explorador de amenazas) &amp; en el centro de seguridad y cumplimiento.
ms.openlocfilehash: 30f3759b6eb35508a9de8c03abb72562417aa04f
ms.sourcegitcommit: 0d5a863f48914eeaaf29f7d2a2022618de186247
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "34077336"
---
# <a name="use-threat-explorer-in-the-security-amp-compliance-center"></a>Usar el explorador de amenazas en &amp; el centro de seguridad y cumplimiento

Si su organización tiene [Office 365 Advanced Threat Protection Plan 2](office-365-ti.md) (ATP) y tiene los permisos necesarios, puede usar el explorador de amenazas (también conocido como explorador) para identificar y analizar las amenazas. (Para usar el explorador, en el &amp; centro de seguridad y cumplimiento, vaya a **Threat Management** \> **Explorer**).

![Ir al explorador de \> administración de amenazas](media/cab32fa2-66f1-4ad5-bc1d-2bac4dbeb48c.png)

Explorer es una herramienta eficaz y en tiempo real cercana para ayudar a los equipos de operaciones de seguridad a investigar y responder &amp; a amenazas en el centro de seguridad y cumplimiento. Estas son algunas de las cosas que puede hacer:
- [Ver malware detectado por las características de seguridad de Office 365](#see-malware-detected-in-email-by-technology)
- [Ver datos sobre direcciones URL de suplantación de identidad y hacer clic en veredicto](#view-data-about-phishing-urls-and-click-verdict)
- [Iniciar un proceso de investigación y respuesta automatizado desde una vista en el explorador](#start-automated-investigation-and-response)
- ... [y mucho más](#more-ways-to-use-explorer).

## <a name="see-malware-detected-in-email-by-technology"></a>Ver malware detectado en correo electrónico por tecnología

Supongamos que desea ver el malware que se detectó en el correo electrónico y la tecnología de Office 365. Para ello, use la vista [email _GT_ malware](threat-explorer-views.md#email--malware) View of Explorer.

1. En el centro de seguridad & cumplimiento[https://protection.office.com](https://protection.office.com)(), elija **Threat Management** > **Explorer**.
2. En el **menú Ver** , elija**malware**de **correo electrónico** > .<br/>![Menú Ver para el explorador](media/ExplorerViewEmailMalwareMenu.png)<br/>
3. Haga clic en **remitente**y, a continuación, elija**tecnología de detección** **básica** > .<br/>Las tecnologías de detección están ahora disponibles como filtros para el informe.<br/>![Tecnologías de detección de malware](media/ExplorerEmailMalwareDetectionTech.png)<br/> 
4. Seleccione una opción y, a continuación, haga clic en el botón actualizar para aplicar ese filtro.<br/>![Tecnología de detección seleccionada](media/ExplorerEmailMalwareDetectionTechATP.png)<br/> 

El informe se actualiza para mostrar el malware de resultados detectado en el correo electrónico, usando la opción de tecnología que seleccionó. Desde aquí, puede realizar análisis adicionales.

## <a name="view-data-about-phishing-urls-and-click-verdict"></a>Ver datos sobre direcciones URL de suplantación de identidad y hacer clic en veredicto

Supongamos que desea ver los intentos de suplantación de identidad mediante direcciones URL en el correo electrónico, incluida una lista de direcciones URL que se han permitido, bloqueado y reemplazado.  La identificación de las direcciones URL en las que se hizo clic requiere [vínculos seguros de ATP](atp-safe-links.md). (Asegúrese de que ha configurado y aplicado [las directivas de vínculos seguros ATP](set-up-atp-safe-links-policies.md) a sus usuarios para la protección en tiempo de clic y el registro de los veredictos en vínculos seguros de ATP). Para revisar direcciones URL de phish en mensajes y hacer clic en direcciones URL en mensajes de Phish, use el [correo electrónico > de phish](threat-explorer-views.md#email--phish) vista de Explorer.

1. En el centro de seguridad & cumplimiento[https://protection.office.com](https://protection.office.com)(), elija **Threat Management** > **Explorer**.
2. En el **menú Ver** , elija**phishing**de **correo electrónico** > .<br/>![Menú Ver para el explorador](media/ExplorerViewEmailPhishMenu.png)<br/>
3. Haga clic en **remitente**y, a continuación, elija **direcciones URL** > ,**haga clic en veredicto**.
4. Seleccione una o más opciones, como **bloqueada** y **bloque**invalidado y, a continuación, haga clic en el botón **Actualizar** para aplicar ese filtro.<br/>![Direcciones URL y haga clic en veredictos](media/ThreatExplorerEmailPhishClickVerdictOptions.png)<br/>

El informe se actualiza para mostrar dos tablas de direcciones URL diferentes en la ficha dirección URL siguiente:
1. Las **direcciones URL principales** son las que se encuentran en los mensajes que se han filtrado y la acción de entrega de correo electrónico se recuento para cada dirección URL. En la vista correo phish, esta lista normalmente contendrá direcciones URL legítimas. Los atacantes incluyen una mezcla de direcciones URL buenas y incorrectas en sus mensajes para intentar entregarlos, pero hacen que los vínculos malintencionados sean más interesantes para el usuario hacer clic en. La tabla de direcciones URL se ordena por recuento de correo electrónico total (Nota: esta columna no se muestra para simplificar la vista).
2. Los **clics principales** son las direcciones URL contenidas en vínculos seguros en las que se hizo clic, ordenadas por número total de clics (esta columna tampoco se muestra para simplificar la vista). Número total de recuentos por columna indique los vínculos seguros haga clic en recuento de veredictos para cada dirección URL con clic. En la vista de correo electrónico phish, estos serán vínculos sospechosos o malintencionados, pero podrían incluir direcciones URL limpias que se encuentren en mensajes de suplantación dese. Los clics de dirección URL en vínculos desajustados no se mostrarán aquí.

Las dos tablas URL muestran las direcciones URL principales en los correos electrónicos de suplantación de identidad (phishing) por estado de entrega y muestran los clics de dirección URL que se bloquearon (o visitaron a pesar de una advertencia) para que pueda comprender los posibles vínculos no válidos que los usuarios han recibido e interactúan con los usuarios. Desde aquí, puede realizar análisis adicionales. Por ejemplo, debajo del gráfico, puede ver las direcciones URL principales en los correos electrónicos que se bloquearon en el entorno de su organización. 

![URL del explorador que se bloquearon](media/ExplorerPhishClickVerdictURLs.png) 

Seleccione una dirección URL para ver información más detallada. Tenga en cuenta que en el cuadro de diálogo de URL flotante, se quita el filtrado en los correos electrónicos para mostrarle la vista completa de la exposición de la URL en su entorno. Esto le permite filtrar los correos electrónicos en el explorador a los que le interesa, encontrar direcciones URL específicas que son posibles amenazas y, a continuación, ampliar la comprensión de la exposición de URL en su entorno (a través del cuadro de diálogo de detalles de URL) sin tener que agregar filtros de URL al Vista del explorador.

## <a name="review-email-messages-reported-by-users"></a>Revisar los mensajes de correo electrónico enviados por los usuarios

Supongamos que desea ver los mensajes de correo electrónico que los usuarios de la organización han notificado como correo no deseado, correo no deseado o suplantación de identidad mediante el [complemento de mensajes de informe para Outlook y Outlook en la web](enable-the-report-message-add-in.md). Para ello, use la vista de [correo electrónico >](threat-explorer-views.md#email--user-reported) del explorador notificado por el usuario.

1. En el centro de seguridad & cumplimiento[https://protection.office.com](https://protection.office.com)(), elija **Threat Management** > **Explorer**.
2. En el menú **Ver** , elija **correo electrónico** > notificado por el**usuario**.<br/>![Menú Ver para el explorador](media/ExplorerViewMenuEmailUserReported.png)<br/>
3. Haga clic en **remitente**y, a continuación, elija**tipo de informe** **básico** > .
4. Seleccione una opción, como **phish**y, a continuación, haga clic en el botón **Actualizar** . <br/>![Phish notificados por el usuario](media/EmailUserReportedReportType.png)<br/> 

El informe se actualiza para Mostrar datos sobre los mensajes de correo electrónico que las personas de su organización han notificado como un intento de suplantación de identidad. Puede usar esta información para realizar análisis adicionales y, si es necesario, ajustar las [directivas antiphishing de ATP](set-up-anti-phishing-policies.md).

## <a name="start-automated-investigation-and-response"></a>Iniciar investigación y respuesta automatizadas

(Nueva) La [investigación y la respuesta automatizadas](automated-investigation-response-office.md), agregadas recientemente a ATP plan 2, pueden guardar el equipo de operaciones de seguridad en un gran número de tiempo y esfuerzo para investigar y mitigar los ataques cibernéticos. Además de configurar alertas que pueden desencadenar una guía de seguridad, puede iniciar un proceso de investigación y respuesta automatizado desde una vista en el explorador. 

Para obtener más información sobre esto, consulte [ejemplo: un administrador de seguridad desencadena una investigación desde el explorador de amenazas](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer).

## <a name="more-ways-to-use-explorer"></a>Más formas de usar el explorador

Además de los escenarios descritos en este artículo, tiene muchas más opciones de informes disponibles con el explorador. 
- [Buscar e investigar el correo electrónico malintencionado que se ha entregado](investigate-malicious-email-that-was-delivered.md)
- [Ver archivos malintencionados detectados en SharePoint Online, OneDrive y Microsoft Teams](malicious-files-detected-in-spo-odb-or-teams.md)
- [Obtener información general sobre las vistas en el explorador de amenazas](threat-explorer-views.md)

## <a name="required-licenses-and-permissions"></a>Permisos y licencias necesarios

Explorer se incluye en el [plan 2 de la protección contra amenazas avanzada de Office 365](office-365-ti.md). 

Para ver y usar el explorador, debe tener los permisos adecuados, como los que se han concedido a un administrador de seguridad o un lector de seguridad. 

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
  
