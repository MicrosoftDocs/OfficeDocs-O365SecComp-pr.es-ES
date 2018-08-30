---
title: Introducción a las características de búsqueda y de exhibición de documentos electrónicos de Office 365
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
description: Información general sobre la característica de exhibición de documentos electrónicos y otras características de búsqueda dentro de Office 365 para auditar el uso y la transparencia.
ms.openlocfilehash: 2d5cc2533c195b51f685aebd8da4462518116905
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22536228"
---
# <a name="ediscovery-and-search-features"></a>Características de búsqueda y eDiscovery 

## <a name="ediscovery"></a>eDiscovery
La característica de exhibición de documentos electrónicos proporciona un único lugar para los administradores, responsables del cumplimiento normativo, y otra autorización a los usuarios llevar a cabo una investigación exhaustiva de actividad de usuario de Office 365. Responsables de seguridad con los permisos apropiados pueden realizar búsquedas y realizar suspensiones en el contenido. Los resultados de búsqueda son los mismos resultados que obtener en una búsqueda de contenido, excepto en que se crea un caso de exhibición de documentos electrónicos para cualquier suspensiones que se aplican. Los resultados de las búsquedas de exhibición de documentos electrónicos de están cifrados para la seguridad y se pueden analizar los datos exportados con [Avanzadas exhibición de documentos electrónicos](https://support.office.com/article/office-365-advanced-ediscovery-fd53438a-a760-45f6-9df4-861b50161ae4).

## <a name="content-search"></a>Búsqueda de contenido
[Búsqueda de contenido](https://support.office.com/article/Run-a-Content-Search-in-the-Office-365-Security-Compliance-Center-61852fd9-fe8a-4880-a339-cb19ed3bff4a) es una nueva herramienta de búsqueda de exhibición de documentos electrónicos en la seguridad & Centro de cumplimiento de normas que proporciona una mejor escalabilidad y capacidades de rendimiento a través de las herramientas de búsqueda de exhibición de documentos electrónicos anterior. Puede usar la búsqueda de contenido para buscar los buzones de correo, carpetas públicas, sitios de SharePoint Online y OneDrive para las ubicaciones de negocio. Búsqueda de contenido está diseñada específicamente para las búsquedas muy grandes. No hay ningún límite en el número de buzones de correo y los sitios que se pueden buscar. No existen límites en el número de búsquedas que se pueden ejecutar al mismo tiempo. Después de ejecutar una búsqueda, el número de orígenes de contenido y un número estimado de búsqueda se muestran los resultados en el panel de detalles en la página de búsqueda, donde puede obtener una vista previa de los resultados o exportarlos a un equipo local. Si su organización tiene una suscripción a Office 365 Enterprise E5, también puede [preparar los resultados](https://support.office.com/article/Run-a-Content-Search-in-the-Office-365-Security-Compliance-Center-61852fd9-fe8a-4880-a339-cb19ed3bff4a#prepare) para el análisis mediante las características de análisis eficaces de [exhibición de documentos electrónicos avanzada de Office 365](http://go.microsoft.com/fwlink/p/?LinkID=620116).

## <a name="audit-log-search"></a>Búsqueda de registro de auditoría
Además de seguimiento de los cambios en su organización de Office 365, los clientes también pueden ver los informes de auditoría y exportar registros de auditoría. Una vez habilitada la auditoría para un inquilino de Office 365, usuario y actividad administrativa para ese inquilino es registrada en los registros de eventos y realizados que admite búsquedas. Por ejemplo, puede usar para realizar un seguimiento de acciones realizadas en un buzón de correo por los usuarios que no sean el propietario del buzón de registro de auditoría de buzón de correo. Además, responsables del cumplimiento normativo pueden usar las capacidades de búsqueda y filtro para ver si un usuario ha visto o descargar un documento específico, o si un administrador tiene realizar actividades de administración de usuario o realizar cambios en la configuración de inquilino en los últimos 90 días. Los resultados de búsqueda pueden contener información de análisis valiosa sobre las actividades específicas que se llevaron a cabo por un usuario o un administrador. Ver [las actividades de auditada en Office 365](https://support.office.com/article/Search-the-audit-log-in-the-Office-365-Security-Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c#auditlogevents) para obtener una descripción de las actividades administrativas que se registran en Office 365 y el usuario.

Eventos de SharePoint Online y OneDrive para la empresa se muestran en el registro de dentro de 30 minutos de su aparición. Eventos de Exchange Online aparecen en los registros de auditoría dentro de 24 horas de aparición. Eventos de inicio de sesión de Azure AD están disponibles en cuestión de minutos de aparición y otros eventos de Active directory de Azure AD están disponibles dentro de 24 horas de aparición. También se pueden exportar eventos en los resultados de búsqueda de registro de auditoría para realizar un análisis. (Se puede exportar un máximo de 50.000 entradas de una búsqueda de registro de auditoría único. Para exportar las entradas más que este límite, reduzca el intervalo de fechas, o realizar varias búsquedas de registro de auditoría.)

En la siguiente tabla se detalla algunas de la información que se muestra en los informes de actividad. Vea el [registro de auditoría de propiedades detalladas en Office 365](https://support.office.com/article/detailed-properties-in-the-office-365-audit-log-ce004100-9e7f-443e-942b-9b04098fcfc3
) para obtener más información acerca de qué propiedades se recopilan por cada carga de trabajo de Office 365.

| Propiedad | Descripción |
|----------------|----------------------------------------------------------------------------------------------------------------------|
| Fecha | Fecha y hora del evento |
| User | Usuario que realizó la acción |
| IPCliente | Dirección IPv4 o IPv6 del dispositivo que se usó cuando se registró la actividad. |
| CreationTime | Fecha y hora en hora Universal coordinada (UTC) cuando el usuario ha realizado la actividad. |
| Origen de eventos | Identifica que se ha producido un evento. Los valores posibles son SharePoint y ObjectModel. |
| ID | Identificador de la entrada del informe. El identificador identifica la entrada del informe. |
| Operation | Nombre del usuario o actividad, que se corresponde con el valor seleccionado en los resultados para mostrar para esta actividad de usuario. |
| OrganizationId | GUID de servicio de Office 365 de la organización donde se produjo el evento. |
| UserAgent | Información sobre el explorador del usuario como proporcionada por el explorador. |
| UserId | Usuario que realizó la acción (especificada en la propiedad Operation) que se esperó en el registro que se está registrando. |
| UserType | Tipo de usuario que realizó la operación. Los siguientes valores indican el tipo de usuario. |
|  | 0 indica que un usuario normal. |
|  | 2 indica un administrador de la organización de Office 365. |
|  | 3 indica una cuenta de sistema de administrador o centro de datos de centros de datos de Microsoft. |
| Carga de trabajo | Servicio de Office 365 en el que se produjo la actividad. Los valores posibles para esta propiedad son: |
|  | Exchange Online |
|  | SharePoint Online |
|  | OneDrive para la Empresa |
|  | Informes de Azure Active Directory |


Para obtener instrucciones detalladas buscar Office 365 registros de auditoría, consulte [los registros de auditoría de búsqueda en el centro de cumplimiento y seguridad de Office 365](https://support.office.com/article/Search-the-audit-log-in-the-Office-365-Security-Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c).

## <a name="search-unified-audit-log"></a>Búsqueda unificada registro de auditoría
La característica de búsqueda de registro de auditoría en el centro de cumplimiento y seguridad puede utilizarse para buscar el registro de auditoría unificadas. Office 365 también proporciona la capacidad de buscar este registro mediante PowerShell remoto. Específicamente, el [cmdlet de UnifiedAuditLog de búsqueda](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-audit/Search-UnifiedAuditLog?view=exchange-ps) en Exchange Online PowerShell puede utilizarse para buscar el registro de auditoría unificado de eventos relativos a las operaciones de usuario de Exchange Online, SharePoint Online, OneDrive para la empresa y Azure AD. Puede buscar todos los eventos en un intervalo de fechas especificado, o puede filtrar los resultados en función de criterios específicos, como una acción específica, el usuario que realizó la acción o el objeto de destino. Los administradores pueden usar hasta 3 ejecutan simultáneamente sesiones de Exchange Online PowerShell para dividir las búsquedas de intervalo de fechas grande.
