---
title: Usar el explorador de amenazas en &amp; el centro de seguridad y cumplimiento
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 03/21/2019
ms.audience: ITPro
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
ms.openlocfilehash: 202898873bb9611c747aed335d295c749c7cd0fa
ms.sourcegitcommit: a56128c7be5d59e976851c27301031e19fa1997d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/21/2019
ms.locfileid: "30732263"
---
# <a name="use-threat-explorer-in-the-security-amp-compliance-center"></a>Usar el explorador de amenazas en &amp; el centro de seguridad y cumplimiento

Si su organización tiene [Office 365 Advanced Threat Protection Plan 2](office-365-ti.md)y dispone de los permisos necesarios, puede usar el explorador de amenazas para identificar y analizar las amenazas. Por ejemplo, puede identificar y eliminar correo electrónico malintencionado que se entregó, o ver malware detectado por las características de seguridad de Office 365. El explorador de amenazas (también conocido como explorador) es una herramienta eficaz casi en tiempo real para ayudar a los equipos de operaciones de seguridad a investigar y &amp; responder a amenazas en el centro de seguridad y cumplimiento.
  
![Ir al explorador de \> administración de amenazas](media/cab32fa2-66f1-4ad5-bc1d-2bac4dbeb48c.png)
  
Para usar el explorador, en el &amp; centro de seguridad y cumplimiento, vaya a **Threat Management** \> **Explorer**.

> [!IMPORTANT]
> Office 365 Threat Intelligence es ahora Office 365 plan de protección contra amenazas avanzada 2, junto con otras capacidades de protección contra amenazas. Para obtener más información, consulte [planes y precios](https://products.office.com/exchange/advance-threat-protection) de la protección contra amenazas avanzada de Office 365 y la [Descripción del servicio de protección contra amenazas avanzada de Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).
      
## <a name="explorer-overview"></a>Información general del explorador

Si su organización tiene [capacidades de investigación y respuesta de amenazas de Office 365](office-365-ti.md) (esto se incluye en el plan de ATP 2) y tiene los permisos necesarios, puede usar el explorador de amenazas (también conocido como explorador) para identificar y analizar las amenazas. (En el centro &amp; de seguridad y cumplimiento, vaya a **Threat Management** \> **Explorer**).

![Ir al explorador de \> administración de amenazas](media/cab32fa2-66f1-4ad5-bc1d-2bac4dbeb48c.png)

En este artículo se describen algunas cosas que puede hacer con el explorador (hay muchas más posibilidades):

- [Consulte los tipos de malware detectados en el correo electrónico y la](#see-malware-detected-in-email-by-technology)tecnología de protección contra amenazas (protección antimalware, datos adJuntos seguros de ATP, etc.).

- [Ver datos sobre los vínculos de suplantación de identidad (URL)](#view-data-about-phishing-urls-and-click-verdict)y qué han sido los veredictos de clic (direcciones URL bloqueadas, permitidas o visitadas a pesar de las advertencias)

- [Revise los mensajes de correo electrónico que se notificaron como correo](#review-email-messages-reported-by-users)no deseado, correo no deseado o suplantaCión de identidad (phishing), e identifique cualquier tendencia (por ejemplo, un número de mensajes mayor que el habitual) que se notifica como phish. 

## <a name="see-malware-detected-in-email-by-technology"></a>Ver malware detectado en correo electrónico por tecnología

SuPongamos que desea ver el malware que se detectó en el correo electrónico y la tecnología de Office 365. Para ello, use la vista [email _GT_ malware](threat-explorer-views.md#email--malware) View of Explorer.

1. en el centro de seguridad & cumplimiento de Office[https://protection.office.com](https://protection.office.com)365 (), elija **Threat management** > **Explorer**.
2. En el **menú Ver** , elija**malware**de **correo electrónico** > .<br/>![Menú Ver para el explorador](media/ExplorerViewEmailMalwareMenu.png)<br/>
3. Haga clic en **remitente**y, a continuación, elija**tecnología de detección** **básica** > .<br/>Las tecnologías de detección están ahora disponibles como filtros para el informe.<br/>![Tecnologías de detección de malware](media/ExplorerEmailMalwareDetectionTech.png)<br/> 
4. Seleccione una opción y, a continuación, haga clic en el botón actualizar para aplicar ese filtro.<br/>![Tecnología de detección seleccionada](media/ExplorerEmailMalwareDetectionTechATP.png)<br/> 

El informe se actualiza para mostrar el malware de resultados detectado en el correo electrónico, usando la opción de tecnología que seleccionó. Desde aquí, puede realizar análisis adicionales.

## <a name="view-data-about-phishing-urls-and-click-verdict"></a>Ver datos sobre direcciones URL de suplantación de identidad y hacer clic en veredicto

SuPongamos que desea ver los intentos de suplantación de identidad mediante direcciones URL en el correo electrónico, incluida una lista de direcciones URL que se han permitido, bloqueado y reemplazado. Para ello, use la vista de [correo electrónico _GT_ phish](threat-explorer-views.md#email--phish) de Explorer.

1. en el centro de seguridad & cumplimiento de Office[https://protection.office.com](https://protection.office.com)365 (), elija **Threat management** > **Explorer**.
2. En el **menú Ver** , elija**phishing**de **correo electrónico** > .<br/>![Menú Ver para el explorador](media/ExplorerViewEmailPhishMenu.png)<br/>
3. Haga clic en **remitente**y, a continuación, elija **direcciones URL** > ,**haga clic en veredicto**.
4. Seleccione una o más opciones, como **bloqueada** y **bloque**invalidado y, a continuación, haga clic en el botón **Actualizar** para aplicar ese filtro.<br/>![Direcciones URL y haga clic en veredictos](media/ThreatExplorerEmailPhishClickVerdictOptions.png)<br/>

El informe se actualiza para mostrar las direcciones URL de suplantación de identidad (phishing) detectadas en correo electrónico que se bloquearon (o visitaron a pesar de una advertencia), junto con el estado de entrega del correo electrónico Desde aquí, puede realizar análisis adicionales. Por ejemplo, debajo del gráfico, puede ver las direcciones URL principales que se bloquearon en el correo electrónico de su organización. 

![URL del explorador que se bloquearon](media/ExplorerPhishClickVerdictURLs.png) 

Seleccione una dirección URL para ver información más detallada.

## <a name="review-email-messages-reported-by-users"></a>Revisar los mensajes de correo electrónico enviados por los usuarios

SuPongamos que desea ver los mensajes de correo electrónico que los usuarios de la organización han notificado como correo no deseado, correo no deseado o suPlantación de identidad mediante el [complemento de mensajes de informe para Outlook y Outlook en la web](enable-the-report-message-add-in.md). Para ello, use la vista de [correo electrónico >](threat-explorer-views.md#email--user-reported) del explorador notificado por el usuario.

1. en el centro de seguridad & cumplimiento de Office[https://protection.office.com](https://protection.office.com)365 (), elija **Threat management** > **Explorer**.
2. En el menú **Ver** , elija **correo electrónico** > notificado por el**usuario**.<br/>![Menú Ver para el explorador](media/ExplorerViewMenuEmailUserReported.png)<br/>
3. Haga clic en **remitente**y, a continuación, elija**tipo de informe** **básico** > .
4. Seleccione una opción, como **phish**y, a continuación, haga clic en el botón **Actualizar** . <br/>![Phish notificados por el usuario](media/EmailUserReportedReportType.png)<br/> 

El informe se actualiza para Mostrar datos sobre los mensajes de correo electrónico que las personas de su organización han notificado como un intento de suplantación de identidad. Puede usar esta información para realizar análisis adicionales y, si es necesario, ajustar las [directivas antiphishing de ATP](set-up-anti-phishing-policies.md).

## <a name="theres-more"></a>Hay más.

Además de los tres escenarios descritos en este artículo, tiene muchos escenarios de informes disponibles con el explorador. Estos son algunos ejemplos más:

- [Buscar e investigar el correo electrónico malintencionado que se ha entregado](investigate-malicious-email-that-was-delivered.md)

- [Ver archivos malintencionados detectados en SharePoint Online, OneDrive y Microsoft Teams](malicious-files-detected-in-spo-odb-or-teams.md)

- [Obtener información general sobre las vistas en el explorador de amenazas](threat-explorer-views.md)

## <a name="how-to-get-explorer"></a>Cómo obtener Explorer

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

Para obtener más información, vea los siguientes recursos:

- [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md)

- [Permisos de características de Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions)
  
## <a name="related-topics"></a>Temas relacionados

- [Investigación y respuesta automatizadas (AIR)](automated-investigation-response-office.md)

- [Vistas del explorador de amenazas](threat-explorer-views.md)

- [Ver informes para la protección contra amenazas avanzada de Office 365](view-reports-for-atp.md)
