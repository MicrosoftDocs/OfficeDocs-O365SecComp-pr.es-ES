---
title: Características de presentación de informes de Office 365
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
description: Una explicación de características incluido en Office 365 de informes.
ms.openlocfilehash: 5a448089de5d517b81551269416c4a6f91599725
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22536783"
---
# <a name="office-365-reporting-features"></a>Características de presentación de informes de Office 365 

## <a name="introduction"></a>Introducción
La característica de informes en Office 365 proporciona una variedad de informes de auditoría para Azure Active Directory (AD), Exchange Online, administración de dispositivos, revisión de supervisión y prevención de pérdida de datos (DLP). Estos son diferentes e independientes de los informes de actividad de Office 365.

## <a name="office-365-reports-dashboard"></a>Panel de informes de Office 365
El panel de informes en la vista previa de centro de administración de Office 365 muestra la actividad de uso a través de Office 365. Los administradores globales de Office 365, o un Exchange Online, SharePoint Online o Skype para Administrador empresarial, puede obtener información pormenorizada sobre el uso de dicho servicio. Los informes pueden proporcionar conocimientos como el número de usuarios consumir un servicio concreto de Office 365, el número de usuarios que ha activado Office Professional Plus y cuánto correo fluye a través de la organización. Los informes están disponibles para los últimos 7, 30, 90 y 180 días.

Están disponibles los siguientes informes:
- [Informe de actividad de correo electrónico](https://support.office.com/article/Office-365-Reports-in-the-admin-center-preview--Email-activity-1cbe2c00-ca65-4fb9-9663-1bbfa58ebe44)
- [Informe de las activaciones de Microsoft Office](https://support.office.com/article/Office-365-Reports-in-the-admin-center-preview--Microsoft-Office-activations-87c24ae2-82e0-4d1e-be01-c3bcc3f18c60)
- [Informe de uso del sitio de SharePoint Online](https://support.office.com/article/Office-365-Reports-in-the-admin-center-preview--SharePoint-site-usage-4ecfb843-e5d5-464d-8bf6-7ed512a9b213)
- [OneDrive para el informe de uso del negocio](https://support.office.com/article/Office-365-Reports-in-the-Admin-Center-Preview--OneDrive-for-Business-usage-0de3b312-c4e8-4e4b-a02d-32b2f726a680)
- [Informe de actividad de yammer](https://support.office.com/article/View-the-Yammer-Activity-report-in-the-Office-365-admin-center-preview-c7c9f938-5b8e-4d52-b1a2-c7c32cb2312a)
- [Skype para informe de actividad de negocio](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-online-reporting/activity-report)
- [Skype para informe de actividad de negocio de punto a punto](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-online-reporting/peer-to-peer-activity-report)
- [Skype para informe del organizador de la Conferencia empresarial](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-online-reporting/conference-organizer-activity-report)
- [Skype para informe de actividad de participante en la Conferencia empresarial](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-online-reporting/conference-participant-activity-report)

Para obtener más información, consulte [Informes de actividad en el centro de administración de Office 365](https://support.office.com/article/activity-reports-in-the-office-365-admin-center-0d6dfb17-8582-4172-a9a9-aed798150263).


## <a name="azure-active-directory-reports"></a>Informes de Azure Active Directory
Office 365 usa Azure AD para la autenticación y administración de identidades. Los administradores de Office 365 pueden usar los informes generados por Azure para buscar una actividad inusual y acceso no autorizado a sus datos. Puede usar el acceso y uso de los informes en Azure AD para obtener visibilidad de la integridad y la seguridad de Active directory de su organización. Con esta información, un administrador puede determinar mejor donde puede ser posibles riesgos de seguridad para que puedan planear adecuadamente mitigar estos riesgos.

Informes de Azure AD se pueden exportar a Microsoft Excel y correlacionarse con otros datos de Office 365, como los resultados de una búsqueda de registro de auditoría, para proporcionar una perspectiva de acceso, la autenticación y las actividades del nivel de la aplicación. Informes de uso de recursos y anomalías avanzados están disponibles cuando se habilita Azure AD Premium. Estas avanzadas de informes ayuda a mejorar ayuda y posición de las organizaciones de seguridad la organización responde a las posibles amenazas mediante el aprovechamiento de análisis sobre el uso de access y la aplicación del dispositivo. Para obtener más información, vea [creación de informes de Azure Active Directory](https://docs.microsoft.com/azure/active-directory/reports-monitoring/overview-reports/).

## <a name="exchange-online-audit-reports"></a>Informes de auditoría en línea de Exchange
Informes de auditoría de Exchange Online incluyen detalles de acceso al buzón y los cambios realizados por los administradores en el inquilino de Exchange Online de una organización. Una vez habilitada la auditoría de buzón de correo, puede usar las tareas en la tabla siguiente para ejecutar informes y exportar registros de auditoría de Exchange Online.

>**Nota**: debe habilitar buzón registro de auditoría para cada buzón de correo para que los eventos auditados se guardan en el registro de auditoría para ese buzón. Si la auditoría de buzón de correo no está habilitado el registro para un buzón de correo, no se guardarán en el registro de auditoría y no aparecerán en los informes de auditoría de buzón de correo de eventos para ese buzón. Para obtener más información, vea [Habilitar la auditoría de buzón de correo](https://support.office.com/article/Enable-mailbox-auditing-in-Office-365-aaca8987-5b62-458b-9882-c28476a66918).

| Tarea | Descripción |
|----------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| [Ejecución de un informe de acceso al buzón de correo del que no se es propietario](https://docs.microsoft.com/exchange/security-and-compliance/exchange-auditing-reports/non-owner-mailbox-access-report) | Muestra la lista de buzones de correo que se ha tenido acceso por alguien que no sea el propietario del buzón. El informe contiene información acerca de quién tiene acceso a los buzones de correo, las acciones se tardaron en el buzón de correo, y si las acciones se realizaron correctamente. |
| [Exportar registros de auditoría de buzones](https://docs.microsoft.com/exchange/security-and-compliance/exchange-auditing-reports/export-mailbox-audit-logs) | Registros de auditoría de buzones de correo contienen información sobre el acceso y acciones en un buzón de correo realizada por un usuario que no sean el propietario del buzón. Los administradores pueden especificar los buzones de correo junto con un intervalo de fechas para generar informes. Los registros se exporta en XML, adjunta a un mensaje y enviados a usuarios específicos según lo determinado por el administrador. |
| [Ejecución de un informe de grupo de funciones de administrador](https://docs.microsoft.com/Office365/SecurityCompliance/eop/run-an-administrator-role-group-report-in-eop-eop) | El grupo de roles de administrador se usa para asignar privilegios administrativos a los usuarios. Estos privilegios permiten a los usuarios realizar tareas administrativas, como restablecer contraseñas, crear o modificar los buzones de correo y asignan privilegios de administrador a otros usuarios. El informe del grupo de roles de administración muestra los cambios a grupos de roles, incluida la adición o eliminación de miembros. |
| [Ver el registro de auditoría de administración](https://docs.microsoft.com/exchange/security-and-compliance/exchange-auditing-reports/view-administrator-audit-log) | Las listas de informe de registro de auditoría de administración todos creación, actualizar y eliminar las funciones realizadas por los administradores de Exchange Online. Las entradas del registro proporcionan información sobre qué cmdlet se ejecutó, ¿qué parámetros se usaron, que ejecutó el cmdlet y qué objetos afectados. |
| [Retención y búsqueda de contenido de buzones de correo](https://docs.microsoft.com/exchange/security-and-compliance/in-place-ediscovery/in-place-ediscovery) | Proporciona información detallada de los cambios a la exhibición de documentos electrónicos en contexto o la configuración de retención en contexto en los buzones de correo. |
| [Exportar el registro de auditoría de administración](https://docs.microsoft.com/exchange/security-and-compliance/exchange-auditing-reports/search-role-group-changes) | Los registros del registro de auditoría de administración acciones administrativas específicas, como creación, actualizar y eliminar en Exchange Online. Los resultados del registro de se exportan a XML y los administradores pueden optar por enviar este registro a un conjunto de usuarios. |
| [Ejecutar un informe de retención por litigio por buzón](https://docs.microsoft.com/exchange/security-and-compliance/exchange-auditing-reports/per-mailbox-litigation-hold-report) | Proporciona detalles de los cambios realizados a litigios mantienen parámetros de configuración en los buzones de correo. |
| [Ver y exportar el registro de auditoría del administrador externo](https://docs.microsoft.com/exchange/security-and-compliance/exchange-auditing-reports/view-external-admin-audit-log) | Contiene detalles de las acciones realizadas por los administradores externos. Las entradas de proporcionan información en qué cmdlet era ejecutar, ¿qué parámetros se usaron y todas las acciones que creación, modifican o eliminación los objetos de Exchange Online. |

## <a name="device-compliance-reports"></a>Informes de cumplimiento de normas de dispositivo
Puede administrar y proteger los dispositivos móviles cuando están conectados a la organización de Office 365 mediante el uso de Office 365 Mobile Device Management (MDM). Dispositivos móviles como smartphones y tabletas que se usan para tener acceso a correo electrónico del trabajo, calendario, contactos y documentos reproducción una parte importante en asegurándose de que los empleados están capacitados para trabajar en cualquier momento y desde cualquier lugar. Como resultado, es fundamental que proteger la información de su organización. Puede usar Office 365 MDM establece las reglas de acceso y directivas de seguridad del dispositivo y borrar dispositivos móviles si está perdidos o robados.

Informes de cumplimiento de normas de MDM proporcionan una introducción a las directivas que se han configurado por una organización para proteger los dispositivos móviles que tienen acceso a datos de Office 365. El informe permite el filtrado de dispositivos por estado de cumplimiento, las infracciones informadas, dispositivos bloqueados y cuántos dispositivos se han borrado como consecuencia de las directivas de seguridad. Para obtener más información, vea [Información general de administración de dispositivos móviles para Office 365](https://support.office.com/article/Overview-of-Mobile-Device-Management-for-Office-365-faa7d8e5-645d-4d59-839c-c8d4c1869e4a).

## <a name="data-loss-prevention"></a>Prevención de pérdida de datos
Las directivas DLP ayudan a administrar la seguridad y el flujo de información en una organización. Puede configurar directivas para bloquear el acceso a contenido, cifrar datos o notificar a los usuarios de la directiva y las infracciones de directivas con sugerencias de directivas de DLP en la aplicación. Informes de DLP proporcionan información sobre el número de coincidencias de directiva y la regla, invalidaciones y falsos positivos.

Puede usar el centro de administración de Office 365 para ver información sobre el número de mensajes detectados por las directivas DLP en formato de tabla o gráfico gráfica. En concreto, coincidencias de directivas de DLP para envían y reciben correo, y con reglas de DLP para correo enviado y recibido. También puede ver el número de coincidencias, invalidaciones y falsos positivos para cada directiva dentro de las últimas 24 horas desde el centro de administración de Exchange. Sin embargo, estos datos no están disponibles como un gráfico. Si se descarga un informe para su uso en Excel, puede ver incluso más detalles, como quién envió el mensaje, en qué día y coincidencias de qué directivas se activaron. Para obtener más información, vea [Ver informes acerca de las detecciones de directiva DLP](https://technet.microsoft.com/en-us/library/jj889415(v=exchg.150).aspx).

## <a name="auditing-in-yammer-enterprise"></a>Auditoría de empresa de Yammer
Yammer que Enterprise proporciona a los administradores con la capacidad de exportar los datos de actividad de usuario de sus redes de Yammer a través de la [API de exportación de datos de Yammer](https://support.office.com/article/export-data-from-yammer-enterprise-b303d8f3-007d-4ad4-81f8-54fb1ecfb3f2)o manualmente a través de la página de administración de red de Yammer. La capacidad de exportar registros está restringida a los administradores de red de Yammer. (Todos los administradores globales de Office 365 son los administradores de red de Yammer).

Se pueden exportar los datos siguientes:

| Filename | Descripción |
|----------------------------|-------------------------------------------------------------------------|
| Users.csv | Todos los usuarios nuevos, pendientes y suspendidos en la red |
| Messages.csv | Todos los mensajes en la red |
| .CsvcrearImprimir de texto (metadatos) | Archivo de metadatos como nombre de archivo, dirección URL de la API, identificador de la herramienta de envío, etcetera, que se cargan en. |
| .CsvcrearImprimir de texto (archivos originales) | Archivo zip de los archivos originales que se han cargado por los usuarios en Yammer |
| Topics.csv | Temas que se crea en la red |
| Pages.csv | Páginas creadas por los usuarios en la red (notas) |
| Admins.csv | Todos los comprobado que los administradores de la red |
| Networks.csv | Todas las redes externas de Yammer |

*Tabla 3 - Yammer red archivos de datos disponibles para la exportación por los clientes*

Datos de la empresa yammer también están disponibles a través de los informes de actividad de Office 365. Además, Yammer está trabajando activamente en exposición de registro adicional a través de la API de actividad de administración de Office 365 y en la capacidad de motivo a través de datos de uso de Power BI. Vea la [Guía básica de Office](https://fasttrack.microsoft.com/roadmap?filters=yammer) para obtener más información acerca de estas características.
