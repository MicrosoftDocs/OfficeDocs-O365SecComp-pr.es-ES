---
title: Protección contra amenazas avanzada de Office 365
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 02/20/2019
ms.audience: Admin
ms.topic: hub-page
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: e100fe7c-f2a1-4b7d-9e08-622330b83653
ms.collection:
- M365-security-compliance
description: Office 365 Advanced Threat Protection incluye datos adjuntos seguros, vínculos seguros, herramientas avanzadas contra la suplantación de identidad, herramientas de informes y capacidades de inteligencia de amenazas.
ms.openlocfilehash: 5db4c5ff5ae7e536bba1f8730c724d151f367b54
ms.sourcegitcommit: 32cb896aef370764ec6e8f8278ebaf16f1c5ff37
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/20/2019
ms.locfileid: "30123931"
---
# <a name="office-365-advanced-threat-protection"></a>Protección contra amenazas avanzada de Office 365

> [!IMPORTANT]
> Este artículo está dirigido a los clientes de Office 365 Enterprise. Si usa Outlook.com, Office 365 Home o Office 365 personal, y está buscando información sobre vínculos seguros en Outlook, consulte [Advanced Outlook.com Security](https://support.office.com/article/advanced-outlook-com-security-for-office-365-subscribers-882d2243-eab9-4545-a58a-b36fee4a46e2).

## <a name="overview"></a>Información general

Office 365 Advanced Threat Protection (ATP) protege a su organización frente a amenazas malintencionadas que plantean mensajes de correo electrónico, vínculos (URL) y herramientas de colaboración. ATP incluye:

- [Directivas de protección contra amenazas](#configure-atp-policies): defina directivas de protección contra amenazas para establecer el nivel de protección adecuado para su organización. 

- [Informes](#view-atp-reports): ver informes en tiempo real para supervisar el rendimiento de ATP en su organización. 

- [Capacidades de inteligencia de amenazas](#utilize-threat-intelligence-capabilities): Use las herramientas de vanguardia para investigar, comprender, simular y evitar amenazas. 
 

## <a name="configure-atp-policies"></a>Configurar las directivas de ATP

Office 365 ATP proporciona numerosas herramientas para establecer un nivel de protección adecuado para su organización. 

El equipo de seguridad de la organización debe definir directivas para cada herramienta de ATP en el centro de seguridad & cumplimiento de Office 365. Vaya a **** > **Directiva** de administración de amenazas para acceder a las opciones de directiva. 

Las directivas definidas para su organización determinan el nivel de comportamiento y protección de las amenazas predefinidas. Las opciones de Directiva son extremadamente flexibles. Por ejemplo, el equipo de seguridad de su organización puede establecer una protección contra amenazas avanzada a nivel de usuario, organización, destinatario y dominio. Es importante revisar las directivas de forma regular, ya que las amenazas y los retos nuevos surgen a diario.  

- [Datos adjuntos seguros de ATP](atp-safe-attachments.md): proporciona protección de día cero para proteger el sistema de mensajería, comprobando los archivos adjuntos de correo electrónico en busca de contenido malintencionado. Dirige todos los mensajes y datos adjuntos que no tienen una firma de virus o malware a un entorno especial y, a continuación, usa técnicas de aprendizaje y análisis de máquina para detectar los intentos malintencionados. Si no se encuentra ninguna actividad sospechosa, el mensaje se reenvía al buzón. Para obtener más información, consulte [configurar las directivas de datos adjuntos seguros de Office 365 ATP](set-up-atp-safe-attachments-policies.md).

- [Vínculos seguros de ATP](atp-safe-links.md): proporciona la comprobación del tiempo de clic de las direcciones URL en mensajes de correo electrónico y archivos de Office. La protección está en curso y se aplica a todo el entorno de mensajería y de Office. Se examinan los vínculos para cada clic: los vínculos seguros permanecen accesibles y los vínculos malintencionados se bloquean dinámicamente. Para obtener más información, consulte [configurar las directivas de vínculos seguros de Office 365 ATP](https://docs.microsoft.com/en-us/office365/securitycompliance/set-up-atp-safe-links-policies). 

- [ATP para SharePoint, OneDrive y Microsoft Teams](atp-for-spo-odb-and-teams.md): protege a su organización cuando los usuarios colaboran y comparten archivos, identificando y bloqueando archivos malintencionados en los sitios de grupo y las bibliotecas de documentos. Para obtener más información, consulte [activar Office 365 ATP para SharePoint, OneDrive y Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md). 

- [Protección contra la suplantación de identidad ATP](atp-anti-phishing.md): detecta los intentos de suplantar a los usuarios y dominios personalizados. Aplica modelos de aprendizaje de la máquina y algoritmos de detección de suplantación avanzada a ataques de suplantación de identidad AVERT. Para obtener más información, consulte Configurar las directivas de protección contra suplantación de identidad [y antiphishing de Office 365 ATP](set-up-anti-phishing-policies.md).

## <a name="view-atp-reports"></a>Ver informes de ATP

Office 365 ATP incluye un [Panel de informes](view-reports-for-atp.md) avanzado para supervisar el rendimiento de ATP. Puede obtener acceso a ella en rePorts **_GT_ Dashboard** en el centro de seguridad & cumplimiento. 

Los informes se actualizan en tiempo real, lo que proporciona la información más reciente. Estos informes también proporcionan recomendaciones y le alertan de amenazas inminentes. Los informes predefinidos incluyen el informe de [Estado de protección contra amenazas](view-reports-for-atp.md#threat-protection-status-report), el informe de [tipos de archivo de ATP](view-reports-for-atp.md#atp-file-types-report), el informe de disposición de [mensajes ATP](view-reports-for-atp.md#atp-message-disposition-report) y más. 

## <a name="utilize-threat-intelligence-capabilities"></a>Usar capacidades de inteligencia de amenazas

Office 365 ATP incluye [las mejores herramientas de inteligencia sobre amenazas](office-365-ti.md) que permiten que el equipo de seguridad de su organización anticipe, comprenda y evite ataques malintencionados. 

- Los rastreadores de [amenazas](threat-trackers.md) proporcionan la última inteligencia sobre los problemas de Cybersecurity. Por ejemplo, puede ver información sobre el malware más reciente y tomar medidas preventivas antes de que se convierta en una amenaza real para su organización. Entre los rastreadores disponibles se incluyen los rastreadores dignos de [destacar](threat-trackers.md#noteworthy-trackers), los rastreadores de [tendencias](threat-trackers.md#trending-trackers), [las consultas con seguimiento](threat-trackers.md#tracked-queries)y [las consultas guardadas](threat-trackers.md#saved-queries).

- [Explorador](use-explorer-in-security-and-compliance.md) (también conocido como explorador de amenazas) es un informe en tiempo real que permite identificar y analizar amenazas recientes. Puede configurar el explorador para Mostrar datos de períodos personalizados.

- El simulador de [ataques](attack-simulator.md) le permite ejecutar escenarios de ataque realistas en su organización para identificar vulnerabilites. Hay disponibles simulaciones de los tipos de ataques actuales, incluido un ataque de suplantación de [identidad (Spear-phishing](attack-simulator.md#display-name-spear-phishing-attack)), un [ataque rociado por contraseña](attack-simulator.md#password-spray-attack), un ataque de contraseña de [fuerza bruta](attack-simulator.md#brute-force-password-attack)y mucho más.
    
## <a name="permissions-required-to-use-atp-features"></a>Permisos necesarios para usar las características de ATP

Para acceder a las características de ATP en el centro de seguridad & cumplimiento, debe tener asignado un rol adecuado. En la tabla siguiente se incluyen algunos ejemplos:

|Rol o grupo de roles  |Recursos para obtener más información  |
|---------|---------|
|Administrador global de Office 365 |[Acerca de los roles de administrador de Office 365](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)|
|Administrador de seguridad |[Permisos de rol de administrador en Azure Active Directory](https://docs.microsoft.com/en-us/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|Administración de la organización de Exchange Online |[Permisos de Exchange Online](https://docs.microsoft.com/en-us/exchange/permissions-exo/permissions-exo) <br>y<br> [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)|

Vea también:
- [Permisos en el centro de seguridad & cumplimiento de Office 365](permissions-in-the-security-and-compliance-center.md) 

- [Dar a los usuarios acceso al centro de cumplimiento de & de seguridad de Office 365](grant-access-to-the-security-and-compliance-center.md)

## <a name="get-office-365-atp"></a>Obtener Office 365 ATP

Office 365 ATP se incluye en Office 365 Enterprise E5, Office 365 Education A5 y Microsoft 365 Business. Si la suscripción no incluye ATP de Office 365, puede comprar ATP como complemento. Para obtener más información, vea los siguientes recursos:

- Consulte [Office 365 Advanced Threat Protection (ATP) Availability](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#office-365-advanced-threat-protection-atp-availability) para obtener una lista de las suscripciones que incluyen planes de ATP.

- Consulte la [disponibilidad de características en los planes de la protección contra amenazas avanzada (ATP)](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans) para obtener una lista de las características incluidas en el plan 1 y 2.

- Consulte [Get The Right office 365 Advanced Threat Protection](https://products.office.com/exchange/advance-threat-protection#pmg-allup-content) para comparar planes y comprar Office 365 ATP.

## <a name="new-features-in-office-365-atp"></a>Nuevas características de Office 365 ATP

Las nuevas características se agregan a Office 365 ATP continuamente. Para obtener más información, vea los siguientes recursos:

- La [Guía básica de 365 de Microsoft](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=advanced%2Cthreat%2Cprotection) proporciona una lista de las nuevas características en desarrollo e implementación.

- La [Descripción del servicio de protección contra amenazas avanzada de Office 365](https://docs.microsoft.com/en-us/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#whats-new-in-office-365-advanced-threat-protection-atp) describe las características y la disponibilidad en todos los planes de ATP.
