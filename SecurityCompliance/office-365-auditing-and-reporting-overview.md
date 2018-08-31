---
title: Auditoría e informes en Office 365
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: 8/21/2018
audience: ITPro
ms.topic: article
ms.service: Office 365 Administration
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: Información general sobre auditoría y características dentro de Office 365, así como garantía de servicio de informes.
ms.openlocfilehash: 055a24523260bf14220d5436dcdd010f31f5d8cd
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22536474"
---
# <a name="auditing-and-reporting-in-office-365"></a>Auditoría e informes en Office 365

## <a name="introduction"></a>Introducción
Servicios de nube de Microsoft incluye varias auditoría y características que los clientes pueden usar para realizar un seguimiento de usuario y la actividad administrativa dentro de sus inquilinos, como los cambios realizados en sus opciones de configuración de SharePoint Online inquilino y Exchange Online de informes y los cambios realizados por los usuarios en los documentos y otros elementos. Los clientes pueden usar la información de auditoría y los informes disponibles en nuestros servicios de nube para administrar la experiencia del usuario, mitigar los riesgos y cumplir con las obligaciones de cumplimiento de normas de forma más eficaz.

## <a name="office-365-security--compliance-center"></a>Centro de seguridad y cumplimiento de Office 365
El [Centro de cumplimiento y seguridad de Office 365](https://support.office.com/article/Go-to-the-Office-365-Security-Compliance-Center-7e696a40-b86b-4a20-afcc-559218b7b1b8) es un portal única para la protección de los datos en Office 365 e incluye muchas auditoría y características de informes. Es una evolución del centro de cumplimiento de normas de Office 365. El centro de cumplimiento y seguridad está diseñada para las organizaciones que tienen datos protección o las necesidades de cumplimiento de normas o que desea auditar la actividad de usuario y administrador. Puede usar el centro de cumplimiento y seguridad para administrar el cumplimiento para todos los datos de Office 365 de su organización. Puede obtener acceso a la seguridad y el centro de cumplimiento en [http://protection.office.com](http://protection.office.com/) con su cuenta de administración de Office 365.

El centro de cumplimiento y seguridad incluye paneles de navegación que proporcionan acceso a varias características:
- **Alertas** - le permite administrar alertas, ver alertas relacionadas con la seguridad y administrar alertas avanzadas con la [Administración de seguridad avanzada](https://support.office.com/article/overview-of-office-365-cloud-app-security-81f0ee9a-9645-45ab-ba56-de9cbccab475). 
- **Permisos** - le permite [asignar permisos](https://support.office.com/article/Give-users-access-to-the-Office-365-Security-Compliance-Center-2cfce2c8-20c5-47f9-afc4-24b059c1bd76) , como administrador de cumplimiento de normas, eDiscovery Manager y otras a las personas de su organización para que pueden realizar tareas en el centro de cumplimiento y seguridad. Puede asignar permisos para la mayoría de las características en el centro de cumplimiento y seguridad, pero deben configurarse otros permisos de uso del centro de administración de Exchange y el centro de administración de SharePoint.
- **Administración de amenaza** - le permite crear y aplicar directivas de administración de dispositivo que usa la [Administración de dispositivos móviles de Office 365](https://support.office.com/article/Overview-of-Mobile-Device-Management-for-Office-365-faa7d8e5-645d-4d59-839c-c8d4c1869e4a), para configurar las directivas de [Prevención de pérdida de datos](https://support.office.com/article/Overview-of-data-loss-prevention-policies-1966b2a7-d1e2-4d92-ab61-42efbb137f5e) (DLP) de su organización, para configurar el filtrado, el correo electrónico anti-malware, correo identificado por claves de dominio (DKIM), los datos adjuntos seguros, vínculos seguros y permisos de aplicación.
- **Gobierno de datos** - le permite [Importar datos de SharePoint desde otros sistemas a Office 365 o de correo electrónico](https://support.office.com/article/Import-PST-files-or-SharePoint-data-to-Office-365-ba688e0a-0fcb-4bd7-8e57-2b669564ea84), [Configurar buzones de archivo](https://support.office.com/article/Enable-archive-mailboxes-in-the-Office-365-Security-Compliance-Center-268a109e-7843-405b-bb3d-b9393b2342ce)y establecer [las directivas de retención](https://support.office.com/article/Retention-in-the-Office-365-Security-Compliance-Center-2a0fc432-f18c-45aa-a539-30ab035c608c) de correo electrónico y otro contenido dentro de la organización.
- **Búsqueda & investigación** - proporciona herramientas de [búsqueda de contenido](https://support.office.com/article/Run-a-Content-Search-in-the-Office-365-Security-Compliance-Center-61852fd9-fe8a-4880-a339-cb19ed3bff4a), [registro de auditoría](https://support.office.com/article/Search-the-audit-log-in-the-Office-365-Security-Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c), cuarentena y [administración de casos de exhibición de documentos electrónicos](https://support.office.com/article/Manage-eDiscovery-cases-in-the-Office-365-Security-Compliance-Center-edea80d6-20a7-40fb-b8c4-5e8c8395f6da) rápidamente detalle de actividad a través de Exchange Online de los buzones de correo, grupos y carpetas públicas, SharePoint En línea y OneDrive para la empresa.
- **Informes** - le permite tener acceso rápidamente a [informes](https://support.office.com/article/Reports-in-the-Office-365-Security-Compliance-Center-7acd33ce-1ec8-49fb-b625-43bac7b58c5a) para SharePoint Online, OneDrive para la empresa, Exchange Online y Azure AD.
- **Garantía de servicio** - proporciona información acerca de cómo Microsoft mantiene la seguridad, privacidad y cumplimiento de normas global para Office 365, Azure, Microsoft Dynamics CRM Online, Microsoft Intune y otros servicios en la nube. También incluye acceso a terceros ISO, seguridad social y otros informes de auditoría, así como de los controles que se auditan, que proporciona información detallada acerca de los diversos controles que se han probado y verificado por auditores de terceros de Office 365.

## <a name="service-assurance"></a>Garantía de servicio
Muchos de nuestros clientes en sectores regulados están sujetos a los requisitos de cumplimiento extensa. Para realizar sus propios las evaluaciones de riesgos, los clientes necesitan a menudo información detallada acerca de cómo Office 365 mantiene la seguridad y la privacidad de sus datos. Microsoft se compromete a la seguridad y privacidad de los datos de cliente en sus servicios en la nube y a ganar la confianza de los clientes al proporcionar una vista transparente de sus operaciones y facilitar el acceso a los informes de cumplimiento independiente y evaluaciones.

Garantía de servicio proporciona transparencia de las operaciones y obtener información acerca de cómo Microsoft mantiene la seguridad, privacidad y cumplimiento de normas de datos de cliente de Office 365. Incluye informes de auditoría de terceros junto con una biblioteca de notas del producto, las preguntas más frecuentes y otros materiales en los temas de Office 365, como el cifrado de datos, la resistencia de datos, administración de incidentes de seguridad y mucho más. Los clientes pueden usar esta información para llevar a cabo sus propios evaluaciones de riesgos legales. Responsables del cumplimiento normativo pueden asignar el rol "Service Assurance User" para proporcionar a los usuarios acceso al servicio de seguro. El Administrador de inquilinos también puede proporcionar a los usuarios externos, como auditores independientes, con acceso a la información en el panel de garantía de servicio a través del [Portal de confianza de servicio de Microsoft en la nube](http://aka.ms/STP) (STP). Para obtener información detallada acerca de cómo tener acceso a la STP, visite [empezar a trabajar con el Portal de servicio de confianza para Office 365 para profesionales, Azure y Dynamics CRM Online suscripciones](http://aka.ms/STPHelp).

## <a name="onedrive-for-business-admin-center"></a>OneDrive para el centro de administración de negocio
El nuevo centro de administración de Microsoft OneDrive le ayuda a rápidamente y administrar fácilmente OneDrive su organización para la configuración de negocio en un solo lugar. Para usar el centro de administración de OneDrive, debe permitir el acceso a onedrive.com. También debe ser un administrador global para su organización o un administrador personalizado con la función de administrador de SharePoint. Obtener acceso a la OneDrive para la vista previa del centro de administración de empresarial en [https://admin.onedrive.com](https://admin.onedrive.com/).

Las características principales incluyen un área de cumplimiento de normas que proporciona a los administradores con vínculos para el centro de cumplimiento y seguridad de Office 365 para escenarios clave como buscar en el registro de auditoría, trabajar con DLP, retención, exhibición de documentos electrónicos y alertas.

## <a name="related-links"></a>Vínculos relacionados
- [Características de búsqueda y eDiscovery](office-365-ediscovery-and-search-features.md)
- [Características de presentación de informes de Office 365](office-365-reporting-features.md)
- [API de Actividad de administración de Office 365](office-365-management-activity-api.md)
- [Migraciones de buzones de Office 365](office-365-mailbox-migrations.md)
- [Registro interno para el equipo de ingeniería de Office 365](office-365-internal-logging.md)