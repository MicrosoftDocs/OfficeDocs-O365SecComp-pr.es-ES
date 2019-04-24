---
title: Introducción a las características de exhibición de documentos electrónicos y búsqueda de Office 365
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
description: Información general sobre la característica de exhibición de documentos electrónicos y otras características de búsqueda en Office 365 para auditar el uso y la transparencia.
ms.openlocfilehash: a7a4412e116fe0cbb28ae1ac193178ac7e3097a3
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32262812"
---
# <a name="ediscovery-and-search-features"></a>Características de búsqueda y eDiscovery 

## <a name="ediscovery"></a>eDiscovery
La característica eDiscovery proporciona un único espacio para que los administradores, los responsables de cumplimiento normativo y otros usuarios autorizados realicen una investigación exhaustiva sobre la actividad de los usuarios de Office 365. Los directivos de seguridad con los permisos adecuados pueden realizar búsquedas y realizar retenciones en el contenido. Los resultados de la búsqueda son los mismos que se obtienen de una búsqueda de contenido, excepto que se crea un caso de exhibición de documentos electrónicos para las suspensiones que se aplican. Los resultados de las búsquedas de exhibición de documentos electrónicos se cifran por seguridad y los datos exportados se pueden analizar con la [exhibición avanzada](https://support.office.com/article/office-365-advanced-ediscovery-fd53438a-a760-45f6-9df4-861b50161ae4)de documentos electrónicos.

## <a name="content-search"></a>Búsqueda de contenido
La [búsqueda de contenido](https://support.office.com/article/Run-a-Content-Search-in-the-Office-365-Security-Compliance-Center-61852fd9-fe8a-4880-a339-cb19ed3bff4a) es una nueva herramienta de búsqueda de eDiscovery que proporciona funciones mejoradas de escalabilidad y rendimiento con respecto a las herramientas de búsqueda anteriores de eDiscovery. Puede usar la búsqueda de contenido para buscar en buzones de correo, carpetas públicas, sitios de SharePoint Online y ubicaciones de OneDrive para la empresa. La búsqueda de contenido está diseñada específicamente para búsquedas muy grandes. No hay ningún límite con respecto al número de buzones y sitios en los que se puede buscar. Tampoco existen límites con respecto al número de búsquedas que se pueden ejecutar al mismo tiempo. Después de ejecutar una búsqueda, el número de orígenes de contenido y el número estimado de resultados de la búsqueda se muestran en el panel de detalles de la página Buscar, donde puede obtener una vista previa de los resultados o exportarlos a un equipo local. Si su organización tiene una suscripción a Office 365 Enterprise E5, también puede [preparar los resultados para el](https://support.office.com/article/Run-a-Content-Search-in-the-Office-365-Security-Compliance-Center-61852fd9-fe8a-4880-a339-cb19ed3bff4a#prepare) análisis con las eficaces características de análisis de [Office 365 Advanced eDiscovery](http://go.microsoft.com/fwlink/p/?LinkID=620116).

## <a name="audit-log-search"></a>Búsqueda de registros de auditoría
Además de realizar un seguimiento de los cambios en su organización de Office 365, los clientes también pueden ver informes de auditoría y exportar registros de auditoría. Una vez que la auditoría está habilitada para un espacio empresarial de Office 365, la actividad administrativa y de usuario de ese inquilino se registra en los registros de eventos y se permite realizar búsquedas. Por ejemplo, puede usar el registro de auditoría de buzones de correo para realizar un seguimiento de las acciones realizadas en un buzón por otros usuarios que no sean el propietario del buzón. Además, los responsables de cumplimiento normativo pueden usar las funcionalidades de búsqueda y filtro para ver si un usuario ha visto o descargado un documento específico, o si un administrador ha realizado actividades de administración de usuarios o ha realizado cambios en la configuración de inquilinos en los últimos 90 días. Los resultados de la búsqueda pueden contener información forense valiosa sobre actividades específicas realizadas por un usuario o un administrador. Consulte [actividades auditadas en office 365](https://support.office.com/article/Search-the-audit-log-in-the-Office-365-Security-Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c#auditlogevents) para obtener una descripción de las actividades administrativas y de usuario que se han registrado en Office 365.

Los eventos de SharePoint Online y OneDrive para la empresa se muestran en el registro en un plazo de 30 minutos a partir de su ocurrencia. Los eventos de Exchange Online aparecen en los registros de auditoría en un plazo de 24 horas de repeticiones. Los eventos de inicio de sesión de Azure AD están disponibles en minutos de su ocurrencia y otros eventos de directorio de Azure AD están disponibles en un plazo de 24 horas de repeticiones. Los eventos de los resultados de la búsqueda de registros de auditoría también se pueden exportar para más análisis. (Se puede exportar un máximo de 50.000 entradas desde una sola búsqueda de registro de auditoría. Para exportar más entradas que este límite, reduzca el intervalo de fechas o ejecute varias búsquedas en el registro de auditoría.)

En la tabla siguiente se detalla parte de la información que se muestra en los informes de actividad. Consulte las [propiedades detalladas en el registro de auditoría de office 365](https://support.office.com/article/detailed-properties-in-the-office-365-audit-log-ce004100-9e7f-443e-942b-9b04098fcfc3
) para obtener más información sobre las propiedades que recopila cada una de las cargas de trabajo de Office 365.

| Propiedad | Descripción |
|----------------|----------------------------------------------------------------------------------------------------------------------|
| Fecha | Fecha y hora del evento |
| User | Usuario que realizó la acción |
| ClientIP | Dirección IPv4 o IPv6 del dispositivo que se usó cuando se registró la actividad. |
| CreationTime | Fecha y hora en la hora universal coordinada (UTC) cuando el usuario llevó a cabo la actividad. |
| EventSource | Identifica que se ha producido un evento. Los valores posibles son SharePoint y ObjectModel. |
| ID | IDENTIFICADOR de la entrada de informe. El identificador identifica de forma única la entrada del informe. |
| Operación | Nombre del usuario o actividad, que corresponde al valor seleccionado en la actividad mostrar resultados para este usuario. |
| OrganizationId | GUID para el servicio Office 365 de la organización en el que se produjo el evento. |
| UserAgent | Información sobre el explorador del usuario como lo proporciona el explorador. |
| UserId | Usuario que realizó la acción (especificado en la propiedad Operation) que resultó en el registro que se está registrando. |
| UserType | Tipo de usuario que realizó la operación. Los siguientes valores indican el tipo de usuario. |
|  | 0 indica un usuario normal. |
|  | 2 indica un administrador de la organización de Office 365. |
|  | 3 indica un administrador de centro de recursos de Microsoft o una cuenta de sistema de centro de recursos. |
| Carga de trabajo | Servicio de Office 365 en el que se produjo la actividad. Los valores posibles para esta propiedad son: |
|  | Exchange Online |
|  | SharePoint Online |
|  | OneDrive para la Empresa |
|  | Informes de Azure Active Directory |


Para obtener los pasos detallados para buscar registros de auditoría de Office 365, consulte [Searching Audit logs in the office 365](https://support.office.com/article/Search-the-audit-log-in-the-Office-365-Security-Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c).

## <a name="search-unified-audit-log"></a>Buscar registro de auditoría unificado
La característica de búsqueda de registros de auditoría se puede usar para buscar en el registro de auditoría unificado. Office 365 también ofrece la posibilidad de realizar búsquedas en este registro mediante PowerShell remoto. En concreto, el [cmdlet Search-UnifiedAuditLog](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-audit/Search-UnifiedAuditLog?view=exchange-ps) en Exchange Online PowerShell se puede usar para buscar en el registro de auditoría unificado de eventos relacionados con las operaciones de usuario de Exchange Online, SharePoint Online, OneDrive para la empresa y Azure ad. Puede buscar todos los eventos de un intervalo de fechas especificado o puede filtrar los resultados en función de criterios específicos, como una acción específica, el usuario que realizó la acción o el objeto de destino. Los administradores pueden usar hasta 3 sesiones de PowerShell de Exchange online que se ejecuten simultáneamente para dividir grandes búsquedas de intervalo de fechas.
