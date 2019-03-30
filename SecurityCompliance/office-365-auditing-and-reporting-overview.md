---
title: Auditoría y creación de informes en los servicios en la nube de Microsoft
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- M365-analytics
description: Información general sobre las características de auditoría e informes de Office 365, Microsoft 365 y Service Assurance.
ms.openlocfilehash: a5df0dcb6f762723c6ec0102b2c39f1bc157720c
ms.sourcegitcommit: 1261a37c414111f869df5791548a768d853fda60
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/30/2019
ms.locfileid: "31004117"
---
# <a name="auditing-and-reporting-in-microsoft-cloud-services"></a>Auditoría y creación de informes en los servicios en la nube de Microsoft

## <a name="introduction"></a>Introducción
Servicios en la nube de Microsoft incluye varias características de informes y auditoría que los clientes pueden usar para realizar un seguimiento de la actividad administrativa y del usuario dentro de su inquilino, como los cambios realizados en las opciones de configuración de los inquilinos de Exchange Online y SharePoint Online. y los cambios realizados por los usuarios en documentos y otros elementos. Los clientes pueden usar la información de auditoría y los informes disponibles en nuestros servicios en la nube para administrar de forma más eficaz la experiencia del usuario, mitigar los riesgos y cumplir las obligaciones de cumplimiento.

## <a name="security--compliance-centers"></a>Centros de cumplimiento de & de seguridad
El centro de seguridad de [Office 365 Security &](https://protection.office.com), el centro de [seguridad de Microsoft 365](https://security.microsoft.com)y el [centro de cumplimiento de Microsoft 365](https://compliance.microsoft.com) son portales de un solo punto para la protección de datos en su organización, y incluyen muchas auditorías e informes ofrece. Estos centros están diseñados para organizaciones que tienen necesidades de cumplimiento o protección de datos, o que quieren auditar la actividad de los usuarios y administradores. Puede acceder a estos centros con su cuenta de administrador de suscripción.

Estos centros incluyen paneles de navegación que proporcionan acceso a varias características:
- **Alertas** : le permite administrar alertas, ver alertas relacionadas con la seguridad y administrar alertas avanzadas mediante [Office 365 Cloud App Security](https://docs.microsoft.com/en-us/Office365/SecurityCompliance/office-365-cas-overview). 
- **Permisos** : le permite [asignar permisos](https://support.office.com/article/Give-users-access-to-the-Office-365-Security-Compliance-Center-2cfce2c8-20c5-47f9-afc4-24b059c1bd76) como administrador de cumplimiento, administrador de exhibición de documentos electrónicos y otros usuarios a las personas de su organización para que puedan realizar tareas en estos centros. Puede asignar permisos para la mayoría de las características de cada centro, pero otros permisos deben configurarse con el centro de administración de Exchange y el centro de administración de SharePoint.
- **Threat Management** : permite crear y aplicar directivas de administración de dispositivos mediante la [Administración de dispositivos móviles de Office 365](https://support.office.com/article/Overview-of-Mobile-Device-Management-for-Office-365-faa7d8e5-645d-4d59-839c-c8d4c1869e4a), para configurar directivas de [prevención de pérdida de datos](https://support.office.com/article/Overview-of-data-loss-prevention-policies-1966b2a7-d1e2-4d92-ab61-42efbb137f5e) (DLP) para su organización, para configurar el filtrado de correo electrónico anti-malware, correo identificado por DomainKeys (DKIM), datos adjuntos seguros, vínculos seguros y aplicaciones de OAuth.
- **Gobierno de datos** : permite [importar correo electrónico o datos de SharePoint desde otros sistemas a Office 365](https://support.office.com/article/Import-PST-files-or-SharePoint-data-to-Office-365-ba688e0a-0fcb-4bd7-8e57-2b669564ea84), [configurar buzones de archivo](https://support.office.com/article/Enable-archive-mailboxes-in-the-Office-365-Security-Compliance-Center-268a109e-7843-405b-bb3d-b9393b2342ce)y establecer directivas de [retención](https://support.office.com/article/Retention-in-the-Office-365-Security-Compliance-Center-2a0fc432-f18c-45aa-a539-30ab035c608c) para el correo electrónico y otros contenidos dentro de la organización.
- **Search & Investigation** : proporciona la [búsqueda de contenido](https://support.office.com/article/Run-a-Content-Search-in-the-Office-365-Security-Compliance-Center-61852fd9-fe8a-4880-a339-cb19ed3bff4a), el [registro de auditoría](https://support.office.com/article/Search-the-audit-log-in-the-Office-365-Security-Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c), la cuarentena y las herramientas de administración de [casos de eDiscovery](https://support.office.com/article/Manage-eDiscovery-cases-in-the-Office-365-Security-Compliance-Center-edea80d6-20a7-40fb-b8c4-5e8c8395f6da) para profundizar rápidamente en la actividad entre buzones de correo, grupos y carpetas públicas de Exchange Online, SharePoint En línea y OneDrive para la empresa.
- **Informes** : le permite acceder rápidamente a los [informes](https://support.office.com/article/Reports-in-the-Office-365-Security-Compliance-Center-7acd33ce-1ec8-49fb-b625-43bac7b58c5a) de SharePoint Online, OneDrive para la empresa, Exchange Online y Azure ad.
- **Garantía del servicio** : proporciona información sobre cómo Microsoft mantiene la seguridad, la privacidad y el cumplimiento de los estándares globales de Office 365, Azure, Microsoft Dynamics CRM Online, Microsoft Intune y otros servicios en la nube. También incluye el acceso a los informes de auditoría ISO, SOC y otros de terceros, así como a los controles auditados, que proporciona información detallada acerca de los diversos controles que han sido probados y verificados por auditores de terceros de Office 365.

## <a name="service-assurance"></a>Garantía del servicio
Muchos de nuestros clientes en industrias reguladas están sujetos a amplios requisitos de cumplimiento. Para realizar sus propias evaluaciones de riesgos, los clientes a menudo necesitan información detallada sobre cómo Office 365 mantiene la seguridad y privacidad de sus datos. Microsoft se compromete a proteger la seguridad y privacidad de los datos de los clientes en sus servicios en la nube y a conseguir la confianza del cliente proporcionando una vista transparente de sus operaciones y un acceso sencillo a las evaluaciones y los informes de cumplimiento independientes.

Garantía del servicio proporciona transparencia de operaciones e información sobre cómo Microsoft mantiene la seguridad, la privacidad y el cumplimiento de los datos del cliente en Office 365. Incluye informes de auditoría de terceros junto con una biblioteca de notas del producto, preguntas más frecuentes y otros materiales sobre los temas de Office 365, como el cifrado de datos, la resistencia de datos, la administración de incidentes de seguridad y mucho más. Los clientes pueden usar esta información para realizar sus propias evaluaciones de riesgos reguladoras. Los responsables de cumplimiento normativo pueden asignar el rol "usuario de garantía de servicio" para dar a los usuarios acceso a la garantía del servicio. El administrador de inquilinos también puede proporcionar a los usuarios externos, como auditores independientes, acceso a la información del panel de garantía del servicio a través del [portal de confianza del servicio](http://aka.ms/STP) en la nube de Microsoft (STP). Para obtener más información sobre cómo acceder a STP, visite [Introducción al portal de confianza de servicios para las suscripciones de Office 365 para empresas, Azure y Dynamics CRM Online](http://aka.ms/STPHelp).

## <a name="onedrive-for-business-admin-center"></a>Centro de administración de OneDrive para la empresa
El nuevo centro de administración de Microsoft OneDrive le ayuda a administrar de forma rápida y sencilla la configuración de OneDrive para la empresa de su organización en un solo punto. Para usar el centro de administración de OneDrive, debe permitir el acceso a onedrive.com. También debe ser un administrador global de su organización o un administrador personalizado con el rol de administrador de SharePoint. Obtenga acceso a la vista previa del centro de [https://admin.onedrive.com](https://admin.onedrive.com/)administración de OneDrive para la empresa en.

Las características clave incluyen un área de cumplimiento que proporciona a los administradores vínculos al centro de administración adecuado para escenarios clave, como la búsqueda en el registro de auditoría, el trabajo con DLP, la retención, la exhibición de documentos electrónicos y las alertas.

## <a name="related-links"></a>Vínculos relacionados
- [Características de búsqueda y eDiscovery](office-365-ediscovery-and-search-features.md)
- [Características de presentación de informes de Office 365](office-365-reporting-features.md)
- [API de Actividad de administración de Office 365](office-365-management-activity-api.md)
- [Migraciones de buzones de Office 365](office-365-mailbox-migrations.md)
- [Registro interno para el equipo de ingeniería de Office 365](office-365-internal-logging.md)