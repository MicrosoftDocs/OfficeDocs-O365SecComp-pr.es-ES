---
title: Informes en el Centro de seguridad y cumplimiento
ms.author: markjjo
author: markjjo
manager: laurawi
ms.audience: Admin
ms.topic: overview
f1_keywords:
- ms.o365.cc.AuditingHelp
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 7acd33ce-1ec8-49fb-b625-43bac7b58c5a
description: 'Use el centro de seguridad & cumplimiento para obtener varios informes para su organización de SharePoint Online y Exchange Online, además de informes de Azure Active Directory.  '
ms.openlocfilehash: e336ddb500ced25fc17ebf4edfb680e410bae172
ms.sourcegitcommit: e7a776a04ef6ed5e287a33cfdc36aa2d72862b55
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/29/2019
ms.locfileid: "30999063"
---
# <a name="reports-in-the-security--compliance-center"></a>Informes en el Centro de seguridad y cumplimiento

Puede usar la página **ver informes** en el centro de seguridad & cumplimiento para obtener un acceso rápido a los informes de auditoría de sus organizaciones de SharePoint Online y Exchange Online. También puede obtener acceso a informes de inicio de sesión de usuario de Azure Active Directory (AD), informes de actividad de usuario y el registro de auditoría de Azure AD desde la página **ver informes** . Esto se debe a que la suscripción a Office 365 pagada incluye una suscripción gratuita a Microsoft Azure. La primera vez que intente obtener acceso a estos informes de Azure, tendrá que completar un proceso de registro de un solo tiempo. 
  
> [!TIP]
> Para ver informes adicionales sobre la actividad de su organización de Office 365, vea [informes de actividades en el centro de administración de Microsoft 365](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263). 
  
 **Antes de empezar**
  
Necesita los siguientes permisos para ver informes en el centro de seguridad & cumplimiento.
  
- Debe tener asignado el rol de lector de seguridad en el centro de administración de Exchange (EAC) para ver los informes en el centro de seguridad & cumplimiento. De forma predeterminada, este rol se asigna a los grupos de roles administración de la organización y lector de seguridad en el EAC.
    
- Debe tener asignado el rol de administración de cumplimiento de DLP de solo vista en el centro de seguridad & cumplimiento para ver los informes de DLP en el centro de seguridad & cumplimiento. De forma predeterminada, este rol se asigna a los grupos de roles administrador de cumplimiento, administración de la organización, administrador de seguridad y lector de seguridad en el centro de seguridad & cumplimiento.

- Además, debe tener asignado el rol de destinatarios con permiso de vista en el EAC para ver los informes de DLP en el EAC. De forma predeterminada, este rol se asigna a los grupos de roles administración de cumplimiento, administración de la organización y administración de la organización de solo vista en el EAC.
  
 **Para abrir la página ver informes en el centro de seguridad & cumplimiento:**
  
1. Vaya a [https://compliance.microsoft.com/#/viewreports](https://compliance.microsoft.com/#/viewreports).
    
2. Inicie sesión en Office 365 con las credenciales de una cuenta de usuario en su organización de Office 365.
    
En la página **ver informes** , puede ver los siguientes tipos de informes: 
  
- [Informes de auditoría](#auditing-reports)
- [Informe de revisión de supervisión](#supervisory-review-report)
- [Informes de prevención de pérdida de datos](#data-loss-prevention-reports)
    
## <a name="auditing-reports"></a>Informes de auditoría

En la tabla siguiente se describen los informes en la sección **Auditoría** de la página **ver informes** en el centro de seguridad & cumplimiento. 
  
|**Informe**|**Descripción**|
|:-----|:-----|
|**Informe de registro de auditoría de Office 365** <br/> |Puede buscar en el registro de auditoría de Office 365 la actividad de usuario y de administrador de su organización de Office 365. El informe contiene entradas actividad de usuario y administrador de Exchange Online, SharePoint Online, OneDrive para la empresa y Azure Active Directory, que es el servicio de directorio para Office 365. Para obtener más información, vea [Buscar en el registro de auditoría en el Office 365](search-the-audit-log-in-security-and-compliance.md).  <br/> |
|**Informes de Azure AD** <br/> |Para buscar actividad de inicio de sesión sospechoso o inusual en su organización de Office 365, puede usar los informes de actividad y de inicio de sesión en Microsoft Azure. También puede ver eventos en el registro de auditoría de Azure AD. Para ver los informes en Azure, solo tiene que hacer clic en **ver informes de Azure ad**. Para más información, visite: <br/><br/>[Use su suscripción gratuita de Azure Active Directory en Office 365](use-your-free-azure-ad-subscription-in-office-365.md). <br/> [Ver los informes de acceso y uso](http://go.microsoft.com/fwlink/p/?LinkId=506902).  <br/> |
|**Informes de auditoría de Exchange** <br/> | Puede usar la funcionalidad de auditoría de Office 365 para realizar un seguimiento de los cambios realizados en la configuración de Exchange Online por parte de los administradores de la organización. También se registran los cambios realizados en la organización de Exchange Online por un administrador del centro de datos de Microsoft o por un administrador delegado. Para Exchange Online, el registro de auditoría de administrador está habilitado de forma predeterminada, por lo que no tiene que hacer nada para activarlo. Exchange Online también proporciona un registro de auditoría de buzones de correo para permitirle realizar un seguimiento del acceso a los buzones por parte de alguien que no sea el propietario del buzón. Tiene que habilitar el registro de auditoría de buzones de correo para cada buzón en el que quiera realizar un seguimiento del acceso de no propietarios.  <br/>  Tanto para el proceso de registro de auditoría del administrador como de los buzones, puede ejecutar informes de auditoría para ver las entradas del registro de auditoría. También puede exportar los registros de auditoría del administrador y de los buzones que se le envían en un plazo de 24 horas en un archivo XML adjunto al mensaje de correo electrónico. <br/><br/>Para obtener más información acerca de la exportación de registros de auditoría, consulte:  <br/><br/> [Exportar registros de auditoría de buzones](http://go.microsoft.com/fwlink/p/?LinkID=404104) <br/> [Ver y exportar el registro de auditoría de administración del centro de administración de información](http://go.microsoft.com/fwlink/p/?LinkId=404109) <br/> [Buscar los informes de cambios del grupo de roles o auditorías de administrador](http://go.microsoft.com/fwlink/p/?LinkId=404105) <br/>   [Informes de auditoría de Exchange](http://go.microsoft.com/fwlink/p/?LinkID=395232).  <br/> |
   
## <a name="supervisory-review-report"></a>Informe de revisión de supervisión

Con el informe de revisión de supervisión, puede ver el estado de todas las directivas de revisión de supervisión de su organización. Para obtener más información, consulte [configurar las directivas de revisión de supervisión para su organización](configure-supervision-policies.md).
  
## <a name="data-loss-prevention-reports"></a>Informes de prevención de pérdida de datos

Los informes de prevención de pérdida de datos (DLP) contienen información sobre las directivas y reglas de DLP que se han aplicado al contenido que contienen datos confidenciales en la organización de Office 365. También puede configurar el informe para mostrar información acerca de las acciones de DLP que se basaban en las reglas y directivas DLP. Para obtener más información, vea [ver el informe de prevención de pérdida de datos](view-the-dlp-reports.md).
