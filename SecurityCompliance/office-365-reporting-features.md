---
title: Características de presentación de informes de Office 365
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-analytics
description: Una explicación de las características de informes en Office 365.
ms.openlocfilehash: 5e765045982d6788ee93550fa8041a52efb306c0
ms.sourcegitcommit: e7a776a04ef6ed5e287a33cfdc36aa2d72862b55
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/29/2019
ms.locfileid: "31000253"
---
# <a name="office-365-reporting-features"></a>Características de presentación de informes de Office 365 

## <a name="introduction"></a>Introducción
La característica de informes de Office 365 proporciona una variedad de informes de auditoría para Azure Active Directory (AD), Exchange Online, la administración de dispositivos, la revisión de supervisión y la prevención de pérdida de datos (DLP). Estos son distintos y separados de los informes de actividad de Office 365.

## <a name="office-365-reports-dashboard"></a>Panel de informes de Office 365
El panel informes de la vista previa del centro de administración de Microsoft 365 muestra la actividad de uso en Office 365. Los administradores globales de Office 365 o los administradores de Exchange Online, SharePoint Online o Skype empresarial pueden obtener información detallada sobre el uso de ese servicio. Los informes pueden proporcionar información como el número de usuarios que consumen un servicio de Office 365 en particular, el número de usuarios que han activado Office Professional Plus y la cantidad de correo que fluye a través de la organización. Los informes están disponibles para los últimos 7, 30, 90 y 180 días.

Están disponibles los siguientes informes:
- [Informe de actividad de correo electrónico](https://support.office.com/article/Office-365-Reports-in-the-admin-center-preview--Email-activity-1cbe2c00-ca65-4fb9-9663-1bbfa58ebe44)
- [Informe de activaciones de Microsoft Office](https://support.office.com/article/Office-365-Reports-in-the-admin-center-preview--Microsoft-Office-activations-87c24ae2-82e0-4d1e-be01-c3bcc3f18c60)
- [Informe de uso del sitio de SharePoint Online](https://support.office.com/article/Office-365-Reports-in-the-admin-center-preview--SharePoint-site-usage-4ecfb843-e5d5-464d-8bf6-7ed512a9b213)
- [Informe de uso de OneDrive para la empresa](https://support.office.com/article/Office-365-Reports-in-the-Admin-Center-Preview--OneDrive-for-Business-usage-0de3b312-c4e8-4e4b-a02d-32b2f726a680)
- [Informe de actividad de Yammer](https://support.office.com/article/View-the-Yammer-Activity-report-in-the-Office-365-admin-center-preview-c7c9f938-5b8e-4d52-b1a2-c7c32cb2312a)
- [Informe de actividad de Skype empresarial](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-online-reporting/activity-report)
- [Informe de actividad punto a punto de Skype empresarial](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-online-reporting/peer-to-peer-activity-report)
- [Informe de organizador de conferencias de Skype empresarial](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-online-reporting/conference-organizer-activity-report)
- [Informe de actividad de participantes de conferencias de Skype empresarial](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-online-reporting/conference-participant-activity-report)

Para obtener más información, vea [informes de actividades en el centro de administración de Microsoft 365](https://support.office.com/article/activity-reports-in-the-office-365-admin-center-0d6dfb17-8582-4172-a9a9-aed798150263).


## <a name="azure-active-directory-reports"></a>Informes de Azure Active Directory
Office 365 usa Azure AD para la autenticación y la administración de identidades. Office 365 los administradores pueden usar los informes generados por Azure para buscar actividades inusuales y acceso no autorizado a sus datos. Puede usar los informes de acceso y uso de Azure AD para obtener visibilidad sobre la integridad y la seguridad del directorio de su organización. Con esta información, un administrador puede determinar mejor dónde puede haber posibles riesgos de seguridad, de modo que pueda planear de forma adecuada los riesgos para mitigarlos.

Los informes de Azure AD se pueden exportar a Microsoft Excel y correlacionarse con otros datos de Office 365, como los resultados de una búsqueda de registros de auditoría, para proporcionar información sobre el acceso, la autenticación y las actividades de nivel de aplicación. Los informes de anomalías y uso de recursos avanzados están disponibles cuando Azure AD Premium está habilitado. Estos informes avanzados ayudan a mejorar la postura de seguridad de una organización y ayudan a las organizaciones a responder a amenazas potenciales aprovechando análisis de acceso a dispositivos y uso de aplicaciones. Para obtener más información, vea [informes de Azure Active Directory](https://docs.microsoft.com/azure/active-directory/reports-monitoring/overview-reports/).

## <a name="exchange-online-audit-reports"></a>Informes de auditoría de Exchange Online
Los informes de auditoría de Exchange online incluyen detalles sobre el acceso a los buzones y los cambios realizados por los administradores en el inquilino de Exchange online de una organización. Una vez habilitada la auditoría de buzones, puede usar las tareas que se indican en la siguiente tabla para ejecutar informes y exportar los registros de auditoría de Exchange Online.

>**Nota**: debe habilitar el registro de auditoría de buzones de correo para cada buzón para que los eventos auditados se guarden en el registro de auditoría de ese buzón. Si el registro de auditoría de buzones de correo no está habilitado para un buzón, los eventos de ese buzón no se guardarán en el registro de auditoría y no aparecerán en los informes de auditoría de buzones de correo. Para obtener más información, consulte [Habilitar la auditoría](https://support.office.com/article/Enable-mailbox-auditing-in-Office-365-aaca8987-5b62-458b-9882-c28476a66918)de buzones de correo.

| Tarea | Descripción |
|----------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| [Ejecución de un informe de acceso al buzón de correo del que no se es propietario](https://docs.microsoft.com/exchange/security-and-compliance/exchange-auditing-reports/non-owner-mailbox-access-report) | Muestra la lista de buzones a los que ha tenido acceso una persona que no es el propietario del buzón. El informe contiene información sobre quién ha tenido acceso al buzón, las acciones que han realizado en el buzón y si las acciones se han realizado correctamente. |
| [Exportar registros de auditoría de buzones](https://docs.microsoft.com/exchange/security-and-compliance/exchange-auditing-reports/export-mailbox-audit-logs) | Los registros de auditoría de buzones de correo contienen información sobre acceso y acciones en un buzón de correo tomado por un usuario que no es el propietario del buzón. Los administradores pueden especificar los buzones junto con un intervalo de fechas para generar informes. Los registros se exportan en XML, se adjuntan a un mensaje y se envían a usuarios específicos según la determinación del administrador. |
| [Realización de un informe de grupo de roles de administrador](https://docs.microsoft.com/Office365/SecurityCompliance/eop/run-an-administrator-role-group-report-in-eop-eop) | El grupo de roles de administrador se usa para asignar privilegios administrativos a los usuarios. Estos privilegios permiten a los usuarios realizar tareas administrativas, como restablecer contraseñas, crear o modificar buzones de correo y asignar privilegios de administrador a otros usuarios. El informe de grupo de roles de administrador muestra los cambios en los grupos de roles, incluida la adición o eliminación de miembros. |
| [Ver el registro de auditoría de administración](https://docs.microsoft.com/exchange/security-and-compliance/exchange-auditing-reports/view-administrator-audit-log) | El informe de registro de auditoría de administrador enumera todas las funciones de creación, actualización y eliminación realizadas por los administradores de Exchange Online. Las entradas de registro proporcionan información sobre el cmdlet que se ejecutó, los parámetros que se usaron, quién ejecutó el cmdlet y qué objetos se vieron afectados. |
| [Búsqueda y retención de contenido de buzones](https://docs.microsoft.com/exchange/security-and-compliance/in-place-ediscovery/in-place-ediscovery) | Proporciona detalles de los cambios en la configuración de exhibición de documentos electrónicos local o de conservación local en los buzones. |
| [Exportación del registro de auditoría de administrador](https://docs.microsoft.com/exchange/security-and-compliance/exchange-auditing-reports/search-role-group-changes) | El registro de auditoría de administrador registra acciones administrativas específicas como crear, actualizar y eliminar en Exchange Online. Los resultados del registro se exportan a XML y los administradores pueden elegir enviar este registro a un conjunto de usuarios. |
| [Realización de un informe de retención por juicio por buzón](https://docs.microsoft.com/exchange/security-and-compliance/exchange-auditing-reports/per-mailbox-litigation-hold-report) | Proporciona detalles de los cambios en la configuración de retención por juicio en los buzones. |
| [Ver y exportar el registro de auditoría de administrador externo](https://docs.microsoft.com/exchange/security-and-compliance/exchange-auditing-reports/view-external-admin-audit-log) | Contiene los detalles de las acciones realizadas por los administradores externos. Las entradas proporcionan información sobre el cmdlet que se ejecutó, los parámetros que se usaron y las acciones que crean, modifican o eliminan objetos en Exchange Online. |

## <a name="device-compliance-reports"></a>Informes de cumplimiento de dispositivos
Puede administrar y proteger los dispositivos móviles cuando están conectados a su organización de Office 365 mediante la administración de dispositivos móviles (MDM) de Office 365. Los dispositivos móviles como smartphones y tabletas que se usan para tener acceso al correo electrónico, el calendario, los contactos y los documentos del trabajo juegan una gran parte para garantizar que los empleados puedan trabajar en cualquier momento y desde cualquier lugar. Como resultado, es fundamental proteger la información de la organización. Puede usar la MDM de Office 365 para establecer las directivas de seguridad de los dispositivos y las reglas de acceso, así como para borrar los dispositivos móviles en caso de pérdida o robo.

Los informes de cumplimiento de MDM proporcionan una visión general de las directivas configuradas por una organización para proteger los dispositivos móviles que tienen acceso a los datos de Office 365. El informe permite filtrar los dispositivos por estado de cumplimiento, violaciones notificados, dispositivos bloqueados y Cuántos dispositivos se borraron como resultado de las directivas de seguridad. Para obtener más información, vea [información general sobre la administración de dispositivos móviles para Office 365](https://support.office.com/article/Overview-of-Mobile-Device-Management-for-Office-365-faa7d8e5-645d-4d59-839c-c8d4c1869e4a).

## <a name="data-loss-prevention"></a>Prevención de pérdida de datos
Las directivas de DLP ayudan a administrar la seguridad y el flujo de la información en una organización. Puede configurar directivas para bloquear el acceso al contenido, cifrar los datos o notificar a los usuarios de las infracciones de directivas y directivas mediante sugerencias de directivas DLP en la aplicación. Los informes de DLP proporcionan información sobre el número de coincidencias de directivas y reglas, invalidaciones y falsos positivos.

Puede usar el centro de administración de Microsoft 365 para ver información sobre el número de mensajes detectados por las directivas de DLP en formato de tabla o gráfico gráfico. Concretamente, las coincidencias de directivas de DLP para el correo enviado y recibido y las coincidencias de reglas de DLP para correo enviado y recibido. También puede ver el número de coincidencias, invalidaciones y falsos positivos para cada directiva en las últimas 24 horas usando el centro de administración de Exchange. Sin embargo, estos datos no están disponibles en forma de gráfico. Si descarga un informe para usarlo en Excel, puede ver incluso más detalles, como quién envió el mensaje, en qué día y qué coincidencias de directivas se activaron. Para obtener más información, vea [ver informes sobre detecciones de directivas de DLP](https://technet.microsoft.com/en-us/library/jj889415(v=exchg.150).aspx).

## <a name="auditing-in-yammer-enterprise"></a>Auditoría en Yammer Enterprise
Yammer Enterprise proporciona a los administradores la capacidad de exportar datos de actividad de usuario desde sus redes de Yammer a través de la [API de exportación de datos de Yammer](https://support.office.com/article/export-data-from-yammer-enterprise-b303d8f3-007d-4ad4-81f8-54fb1ecfb3f2)o manualmente a través de la página de administración de red de Yammer. La capacidad de exportar registros está restringida a los administradores de red en Yammer. (Todos los administradores globales de Office 365 son administradores de red de Yammer).

Se pueden exportar los datos siguientes:

| Filename | Descripción |
|----------------------------|-------------------------------------------------------------------------|
| Users.csv | Todos los usuarios nuevos, pendientes y suspendidos de la red |
| Messages.csv | Todos los mensajes de la red |
| Files. csv (metadatos) | MetaDatos como nombre de archivo, dirección URL de la API de archivo, ID de cargador, cargados en, etc. |
| Files. csv (archivos originales) | Archivo zip de los archivos originales cargados por los usuarios en Yammer |
| Topics.csv | Temas creados en la red |
| Pages.csv | Páginas (notas) creadas por los usuarios en la red |
| Admins.csv | Todos los administradores verificados en la red |
| Networks.csv | Todas las redes externas de Yammer |

*Tabla 3: archivos de datos de red de Yammer disponibles para su exportación por los clientes*

Los datos de Yammer Enterprise también están disponibles a través de los informes de actividad de Office 365. Además, Yammer está trabajando activamente en la exposición de registro adicional a través de la API de actividad de administración de Office 365 y en la capacidad de motivar datos con Power BI. Consulte el [mapa de ruta de Office](https://fasttrack.microsoft.com/roadmap?filters=yammer) para obtener más información sobre estas características.
