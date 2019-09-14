---
title: Novedades en el centro de cumplimiento de Microsoft 365
ms.author: brendonb
author: brendonb
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
- MOE150
- MET150
ms.assetid: e3c6df61-8513-499d-ad8e-8a91770bff63
ms.collection:
- M365-security-compliance
description: Al igual que con las características del centro de cumplimiento de Microsoft 365, el contenido de ayuda está evolucionando siempre. Estamos creando artículos nuevos, actualizando los existentes y realizando cambios en función de sus comentarios. Descubra las novedades y las actualizaciones de este mes.
ms.openlocfilehash: e7600c2f84d0b591c6114c2a61c77d8e2c664056
ms.sourcegitcommit: 9fd606e8d912f4507fbcd9f1fcb9dfcfd20de08b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/13/2019
ms.locfileid: "36980806"
---
# <a name="recent-updates-to-microsoft-365-compliance-content"></a>Actualizaciones recientes del contenido de cumplimiento de Microsoft 365

Al igual que con las características del centro de cumplimiento de Microsoft 365, el contenido de ayuda está evolucionando siempre. Estamos creando artículos nuevos, actualizando los existentes y realizando cambios en función de sus comentarios. Eche un vistazo al siguiente para ver las novedades y las actualizaciones de este mes.

> [!TIP]
> Para estar al tanto de las últimas actualizaciones de características en el centro de cumplimiento de Microsoft 365, consulte [what's New in the microsoft 365 Compliance Center](whats-new.md).

## <a name="august-2019"></a>2019 de agosto

### <a name="auditing"></a>Auditoría

[Administrar la auditoría de buzones](enable-mailbox-auditing.md#more-information) actualizados<br>Se agregaron detalles sobre cómo los eventos de registro de auditoría de buzones de correo solo están disponibles para los usuarios con licencias de E5 o buzones en los que un administrador activó manualmente la auditoría de buzones de correo. También nuevas instrucciones sobre cómo usar el cmdlet **Search-MailboxAuditLog** en Exchange Online PowerShell para buscar en el registro de auditoría de buzones de correo los usuarios sin licencias de E5.

[Buscar en el registro de auditoría de 365 de Office para solucionar escenarios comunes](auditing-troubleshooting-scenarios.md#investigate-why-there-was-a-successful-login-by-a-user-outside-your-organization) actualizados<br>Nueva sección sobre el uso de la autenticación de paso a través para investigar los inicios de sesión correctos por parte de usuarios externos.

### <a name="content-search--ediscovery"></a>Búsqueda de contenido & eDiscovery

[Configurar el filtrado de permisos para la búsqueda de contenido](permissions-filtering-for-content-search.md#using-a-filters-list-to-combine-filter-types) actualizados<br>Se agregaron detalles sobre el uso de una lista de filtros, que permite agregar filtros de buzón de correo y sitio a un único filtro de permisos de búsqueda.

[Búsqueda de contenido en Office 365](content-search.md#searching-disconnected-or-de-licensed-mailboxes) actualizados<br>Se agregaron detalles sobre los buzones de búsqueda desconectados o deshabilitados.

[Búsqueda de contenido en Office 365](content-search.md#searching-for-content-in-a-sharepoint-multi-geo-environment) actualizados<br>
[Configurar límites de cumplimiento para investigaciones de eDiscovery en Office 365](set-up-compliance-boundaries.md#searching-and-exporting-content-in-multi-geo-environments) actualizados<br>Se agregaron detalles a ambos artículos sobre la búsqueda de contenido en entornos multigeográfico de SharePoint.

### <a name="data-governance"></a>Gobierno de datos

[Información general sobre el archivado ilimitado en Office 365](unlimited-archiving.md#how-auto-expanding-archiving-works) actualizados<br>Se agregaron detalles sobre cómo Office 365 agrega un máximo de 20 archivos auxiliares para un total de 1 TB de almacenamiento adicional.

### <a name="data-investigations"></a>Investigaciones de datos

[Eliminar elementos de su ubicación original](datainvestigations/delete-items-from-original-locations.md) nuevo<br>Ahora disponible en la versión preliminar, puede seleccionar elementos en un conjunto de evidencias y, a continuación, eliminarlos temporalmente de sus ubicaciones originales en Exchange, SharePoint y OneDrive.

[Administrar un incidente de derrame de datos en Microsoft 365](datainvestigations/manage-data-spillage-incidents.md#step-4-delete-the-spilled-data) actualizados<br>Se agregaron detalles sobre cómo usar la nueva característica "eliminar elementos de su ubicación original" para eliminar datos derramados.

### <a name="permissions"></a>Permisos

[Permisos en el centro de cumplimiento de microsoft 365 y el centro de seguridad de microsoft 365](permissions-microsoft-365-compliance-security.md) nuevo<br>Los nuevos grupos de roles de Azure Active Directory se publicaron en la versión preliminar pública.

### <a name="records-management"></a>Administración de registros

[Información general sobre el administrador del plan de archivos (actualizado)](file-plan-manager.md#export-all-existing-retention-labels-to-analyze-andor-perform-offline-reviews)<br>Se agregó una tabla que enumera los valores válidos que se van a usar en la plantilla de Excel.

### <a name="supervision"></a>Supervisión

[Directivas de supervisión en Office 365](supervision-policies.md) actualizados<br>Se ha aclarado la compatibilidad de grupos y listas de distribución de Office 365, se han agregado instrucciones para coincidencias de palabras clave en correos electrónicos y datos adjuntos, y se clarifica la compatibilidad con Outlook en los canales de Team

### <a name="windows-information-protection"></a>Windows Information Protection

[Lista de aplicaciones de Microsoft habilitadas para su uso con Windows Information Protection (WIP)](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/enlightened-microsoft-apps-and-wip) actualizados <br>Microsoft 3D Viewer ahora es una aplicación habilitada.
