---
title: Protección contra amenazas avanzada de Office 365
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: 03/28/2019
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
- MOE150
ms.assetid: e100fe7c-f2a1-4b7d-9e08-622330b83653
ms.collection:
- M365-security-compliance
description: La Protección contra amenazas avanzada de Office 365 incluye datos adjuntos seguros, vínculos seguros, herramientas avanzadas contra la suplantación de identidad, herramientas de creación de informes y funciones de inteligencia de amenazas.
ms.openlocfilehash: ca948fdd99ca04830ecb7685ed8930a71345299f
ms.sourcegitcommit: 7a0cb7e1da39fc485fc29e7325b843d16b9808af
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2019
ms.locfileid: "36231094"
---
# <a name="office-365-advanced-threat-protection"></a>Protección contra amenazas avanzada de Office 365

> [!IMPORTANT]
> Este artículo está destinado a los clientes empresariales que tienen la [Protección contra amenazas avanzada de Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description). Si usa Outlook.com, Office 365 Hogar u Office 365 personal, y está buscando información sobre vínculos seguros en Outlook, consulte [Seguridad avanzada de Outlook.com](https://support.office.com/article/advanced-outlook-com-security-for-office-365-subscribers-882d2243-eab9-4545-a58a-b36fee4a46e2).

## <a name="overview"></a>Información general

La Protección contra amenazas avanzada de Office 365 (ATP) protege su organización contra las amenazas malintencionadas ocultas en mensajes de correo electrónico, vínculos (URL) y herramientas de colaboración. ATP incluye:

- [Directivas de protección contra amenazas](#configure-atp-policies): defina directivas de protección contra amenazas para establecer el nivel de protección adecuado para su organización. 

- [Informes](#view-atp-reports): vea informes en tiempo real para supervisar el rendimiento de ATP en la organización. 

- [Investigación de amenazas y capacidades de respuesta](#use-threat-investigation-and-response-capabilities): use las herramientas más avanzadas para investigar, entender, simular y evitar las amenazas. 

- [Investigación y respuestas automáticas](#save-time-with-automated-investigation-and-response): ahorre tiempo y esfuerzo al investigar y mitigar amenazas.

## <a name="office-365-atp-plan-1-and-plan-2"></a>Office 365 ATP Plan 1 y Plan 2

ATP se incluye en Office 365 E5; sin embargo, el Plan 1 y el Plan 2 de ATP están disponibles como complementos para determinadas suscripciones. Para obtener más información, consulte [Disponibilidad de características en los planes de ATP](https://docs.microsoft.com/es-ES/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans).

## <a name="configure-atp-policies"></a>Configurar directivas ATP

Office 365 ATP proporciona numerosas herramientas para establecer un nivel de protección adecuado para su organización. 

El equipo de seguridad de su organización debe definir directivas para cada herramienta de ATP en el Centro de seguridad y cumplimiento de Office 365. Vaya a **Administración de amenazas** > **Directiva** para acceder a las opciones de directivas. (Para obtener ayuda, consulte [Guía de inicio rápido: Configurar la Protección contra amenazas avanzada de Office 365](checklist-atp-setup.md)).

Las directivas definidas por la organización determinan el comportamiento y el nivel de protección para las amenazas predefinidas. Las opciones de directivas son muy flexibles. Por ejemplo, el equipo de seguridad de su organización puede establecer protección contra amenazas específica para el nivel de usuario, organización, destinatario y dominio. Es importante revisar las directivas de forma periódica, ya que surgen a diario nuevas amenazas y desafíos.  

- [Datos adjuntos seguros de ATP](atp-safe-attachments.md): proporciona protección de día cero para salvaguardar su sistema de mensajería, al comprobar los datos adjuntos de correo electrónico en busca de contenido malintencionado. Dirige todos los mensajes y datos adjuntos que no tienen una firma de virus o malware a un entorno especial y, a continuación, utiliza técnicas de aprendizaje automático y análisis para detectar fines malintencionados. Si no se encuentra ninguna actividad sospechosa, el mensaje se reenvía al buzón. Para obtener más información, consulte [Configurar directivas de datos adjuntos seguros de ATP de Office 365](set-up-atp-safe-attachments-policies.md).

- [Vínculos seguros de ATP](atp-safe-links.md): proporciona la comprobación en el momento del clic de las direcciones URL, por ejemplo, en mensajes de correo electrónico y archivos de Office. La protección es continua y se aplica en todo su entorno de mensajería y Office. Los vínculos se analizan en cada clic: los vínculos seguros siguen siendo accesibles y los vínculos maliciosos se bloquean dinámicamente. Para obtener más información, consulte [Configurar directivas de vínculos seguros de ATP de Office 365](https://docs.microsoft.com/es-ES/office365/securitycompliance/set-up-atp-safe-links-policies). 

- [ATP para SharePoint, OneDrive y Microsoft Teams](atp-for-spo-odb-and-teams.md): protege la organización cuando los usuarios colaboran y comparten archivos, al identificar y bloquear archivos malintencionados en los sitios de grupo y las bibliotecas de documentos. Para obtener más información, consulte [Activar ATP de Office 365 para SharePoint, OneDrive y Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md). 

- [Protección contra la suplantación de identidad de ATP](atp-anti-phishing.md): detecta los intentos de suplantar a los usuarios y dominios personalizados. Aplica modelos de aprendizaje automático y algoritmos avanzados de detección de suplantación para evitar ataques de suplantación de identidad. Para obtener más información, consulte [Configurar directivas contra suplantación de identidad y directivas contra suplantación de identidad de ATP de Office 365](set-up-anti-phishing-policies.md).

## <a name="view-atp-reports"></a>Ver informes de ATP

Office 365 ATP incluye un [panel de informes](view-reports-for-atp.md) avanzado para supervisar el rendimiento de ATP. Puede acceder a él en **Informes > Panel** en el Centro de seguridad y cumplimiento. 

Los informes se actualizan en tiempo real y proporcionan los detalles más recientes. Estos informes también proporcionan recomendaciones y le avisan de amenazas inminentes. Los informes predefinidos incluyen: 

- [Explorador de amenazas (o detecciones en tiempo real)](threat-explorer.md)

- [Informe de estado de protección contra amenazas](view-reports-for-atp.md#threat-protection-status-report)

- [Informe de tipos de archivos de ATP](view-reports-for-atp.md#atp-file-types-report)

- [Informe de disposición de mensajes ATP](view-reports-for-atp.md#atp-message-disposition-report)

- ... ¡y mucho más! 

## <a name="use-threat-investigation-and-response-capabilities"></a>Usar las funciones de investigación y respuesta de amenazas

Office 365 ATP Plan 2 incluye las mejores [herramientas de investigación y respuesta de amenazas](office-365-ti.md) que permiten que el equipo de seguridad de su organización anticipe, entienda y evite ataques malintencionados. 

- [Los rastreadores de amenazas](threat-trackers.md) proporcionan la información más reciente sobre los problemas actuales de ciberseguridad. Por ejemplo, puede ver información sobre el malware más reciente y tomar medidas antes de que se convierta en una amenaza real para su organización. Entre los rastreadores disponibles se incluyen [Rastreadores destacados](threat-trackers.md#noteworthy-trackers), [Rastreadores en tendencia](threat-trackers.md#trending-trackers), [Consultas rastreadas](threat-trackers.md#tracked-queries) y [Consultas guardadas](threat-trackers.md#saved-queries).

- [Explorador de amenazas (o detecciones en tiempo real)](threat-explorer.md) (también conocido como Explorador) es un informe en tiempo real que le permite identificar y analizar amenazas recientes. Puede configurar el Explorador para mostrar datos de períodos personalizados.

- [Simulador de ataques](attack-simulator.md) le permite ejecutar escenarios de ataque realistas en la organización para identificar los puntos vulnerables. Hay disponibles simulaciones de los tipos actuales de ataques, incluido un [ataque "spear-phishing" de nombre para mostrar](attack-simulator.md#display-name-spear-phishing-attack), un [ataque de difusión de contraseña](attack-simulator.md#password-spray-attack) y un [ataque de contraseña por fuerza bruta](attack-simulator.md#brute-force-password-attack) entre otros.
    
## <a name="save-time-with-automated-investigation-and-response"></a>Ahorre tiempo gracias a las investigaciones y respuestas automáticas

(**NOVEDAD**) Al investigar un posible ataque cibernético, el tiempo es esencial. Cuanto más pronto pueda identificar y mitigar las amenazas, mejor será para su organización. Office 365 ATP Plan 2 ahora incluirá funciones de [investigación y respuesta automatizadas (AIR)](automated-investigation-response-office.md). (Si todavía no tiene estas funciones, las tendrá pronto con ATP Plan 2).

AIR incluye un conjunto de guías de seguridad que se pueden iniciar automáticamente, como cuando se activa una alerta, o manualmente, como desde una vista del Explorador. AIR pueden ahorrar tiempo y esfuerzo de su equipo de operaciones de seguridad en la reducción de amenazas de manera eficaz. Para obtener más información, consulte [Investigación y respuesta automatizadas (AIR) con Office 365](automated-investigation-response-office.md).

## <a name="permissions-required-to-use-atp-features"></a>Permisos necesarios para usar las características de ATP

Para acceder a las características de ATP en el Centro de seguridad y cumplimiento, debe tener asignado un rol adecuado. En la tabla siguiente se ofrecen algunos ejemplos:

|Rol o grupo de roles  |Recursos para obtener más información  |
|---------|---------|
|Administrador global de Office 365 |[Acerca de los roles de administrador de Office 365](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)|
|Administrador de seguridad |
  [Permisos de roles de administrador en Azure Active Directory](https://docs.microsoft.com/es-ES/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|Administración de la organización en Exchange Online |
  [Permisos de Exchange Online](https://docs.microsoft.com/es-ES/exchange/permissions-exo/permissions-exo) <br>y<br> [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)|

Para obtener más información, vea:

- [Permisos en el Centro de seguridad y cumplimiento](permissions-in-the-security-and-compliance-center.md) 

- [Proporcionar a los usuarios acceso al Centro de seguridad y cumplimiento](grant-access-to-the-security-and-compliance-center.md)

## <a name="get-office-365-atp"></a>Obtener Office 365 ATP

Office 365 ATP Plan 2 está incluido en Office 365 Enterprise E5, Office 365 Educación A5 y Microsoft 365 Empresa. Si su suscripción no incluye Office 365 ATP, puede comprar ATP Plan 1 o ATP Plan 2 como complemento en determinadas suscripciones. Para obtener más información, consulte los siguientes recursos:

- Vea [Disponibilidad de Protección contra amenazas avanzada de Office 365 (ATP)](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#office-365-advanced-threat-protection-atp-availability) para obtener una lista de suscripciones que incluyen planes de ATP.

- Vea [Disponibilidad de características en los planes de Protección contra amenazas avanzada (ATP)](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans) para obtener una lista de las características incluidas en Plan 1 y Plan 2.

- Vea [Obtener la Protección contra amenazas avanzada de Office 365 adecuada](https://products.office.com/exchange/advance-threat-protection#pmg-allup-content) para comparar los planes y comprar Office 365 ATP.

## <a name="new-features-in-office-365-atp"></a>Nuevas características en ATP de Office 365

Se agregan nuevas características a Office 365 ATP continuamente. Para obtener más información, consulte los siguientes recursos:

- La [hoja de ruta de Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=advanced%2Cthreat%2Cprotection) ofrece una lista de las nuevas características en proceso de desarrollo e implementación.

- La [Descripción del servicio de Protección contra amenazas avanzada de Office 365](https://docs.microsoft.com/es-ES/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#whats-new-in-office-365-advanced-threat-protection-atp) describe las características y la disponibilidad en todos los planes de ATP.
