---
title: Informes en la seguridad de Office 365 &amp; centro de cumplimiento
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 2/1/2018
ms.audience: Admin
ms.topic: overview
f1_keywords:
- ms.o365.cc.AuditingHelp
ms.service: o365-administration
localization_priority: Normal
ms.assetid: 7acd33ce-1ec8-49fb-b625-43bac7b58c5a
description: 'Usar la seguridad de Office 365 &amp; informes de centro de cumplimiento para obtener diversos informes para la organización de Exchange Online y SharePoint Online, además de Azure Active Directory.  '
ms.openlocfilehash: 019ccc49352db1aaf392287f62fa63f66913e293
ms.sourcegitcommit: 7956955cd919f6e00b64e4506605a743c5872549
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/26/2018
ms.locfileid: "25038343"
---
# <a name="reports-in-the-office-365-security-amp-compliance-center"></a>Informes en la seguridad de Office 365 &amp; centro de cumplimiento

Puede usar la página **Ver informes** en la seguridad de Office 365 &amp; centro de cumplimiento para agilizar el acceso a informes de auditoría para las organizaciones de Exchange Online y SharePoint Online. También se pueden acceder Azure Active Directory (AD) inicio de sesión de informes de usuario, informes de actividad del usuario, y la auditoría de Azure AD la sesión en la página **Ver informes** . Esto es debido a que su suscripción de pago Office 365 incluye una suscripción gratuita a Microsoft Azure. La primera vez que intenta obtener acceso a estos informes Azure, tendrá para llevar a cabo un proceso de registro único. 
  
> [!TIP]
> Para ver informes adicionales acerca de la actividad en la organización de Office 365, consulte [Informes de actividad en el centro de administración de Office 365](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263). 
  
 **Antes de empezar**
  
Necesita los siguientes permisos para ver los informes de la seguridad &amp; centro de cumplimiento.
  
- Tiene que tener asignado el rol de lector de seguridad en el centro de administración de Exchange (EAC) para ver los informes en la seguridad &amp; centro de cumplimiento. De forma predeterminada, este rol se asigna a los grupos de funciones de administración de la organización y lector de seguridad en el EAC.
    
- Tiene que tener asignado el rol de administración de cumplimiento de normas de DLP en la seguridad &amp; centro de cumplimiento para ver informes de DLP (y las directivas de DLP) en la seguridad &amp; centro de cumplimiento. De forma predeterminada, este rol se asigna a los grupos de roles de administrador de cumplimiento de normas, administración de la organización y Administrador de seguridad en la seguridad &amp; centro de cumplimiento.
    
Además, se tiene que tener asignado el rol de prevención de pérdida de datos en el EAC para ver informes de DLP (y las directivas de DLP) en el EAC. De forma predeterminada, este rol se asigna a los grupos de funciones de administración de cumplimiento y administración de la organización en el EAC.
  
 **Para abrir la página de informes de la vista de la seguridad &amp; centro de cumplimiento:**
  
1. Vaya a [https://protection.office.com/#/viewreports](https://protection.office.com/#/viewreports).
    
2. Inicie sesión en Office 365 con las credenciales para una cuenta de usuario de la organización de Office 365.
    
En la página **Ver informes** , puede ver los siguientes tipos de informes: 
  
- [Informes de auditoría en EOP](#auditing-reports)
- [Informe de revisión de supervisión](#supervisory-review-report)
- [Informes de prevención de pérdida de datos](#data-loss-prevention-reports)
    
## <a name="auditing-reports"></a>Informes de auditoría

En la siguiente tabla se describe los informes en la sección **auditoría** en la página **Ver informes** en la seguridad &amp; centro de cumplimiento. 
  
|**Informe**|**Descripción**|
|:-----|:-----|
|**Informe de registro de auditoría de Office 365** <br/> |Puede buscar el registro de auditoría de Office 365 para la actividad de usuario y administración de en la organización de Office 365. El informe contiene actividad de usuario y administración de las entradas en Exchange Online, SharePoint Online, OneDrive para la empresa y Azure Active Directory, que es el servicio de directorio para Office 365. Para obtener más información, vea [Buscar en el registro de auditoría de la seguridad de Office 365 &amp; centro de cumplimiento](search-the-audit-log-in-security-and-compliance.md).<br/> |
|**Informes de Azure AD** <br/> |Para buscar inusual o sospechosa inicio de sesión de actividad en la organización de Office 365, puede usar el inicio de sesión y la actividad de informes en Microsoft Azure. También puede ver eventos en el registro de auditoría de Azure AD. Para ver los informes en Azure, simplemente haga clic en **Ver Azure AD informes**. Para obtener más información, vea:<br/><br/>[Use su suscripción de Azure Active Directory gratuita en Office 365](use-your-free-azure-ad-subscription-in-office-365.md). <br/> [Ver los informes de uso y acceso](http://go.microsoft.com/fwlink/p/?LinkId=506902).  <br/> |
|**Informes de auditoría de Exchange** <br/> | Puede usar la funcionalidad de auditoría en Office 365 para realizar un seguimiento de los cambios realizados en la configuración de Exchange Online por los administradores de la organización. También se registran los cambios realizados en la organización de Exchange Online por un administrador de centro de datos de Microsoft o por un administrador delegado. Para Exchange Online, auditoría de administrador de registro está habilitado de forma predeterminada, por lo que no tiene que hacer nada para activarla. Exchange Online también proporciona un registro que permita controlar el acceso a los buzones de correo por alguien que no sea el propietario del buzón de auditoría de buzón de correo. Se debe habilitar la auditoría de buzón de correo para cada buzón de correo que se va a realizar un seguimiento de acceso no propietario.<br/>  Registro de auditoría para la administración y el buzón de correo, puede ejecutar informes de auditoría para ver las entradas de registro de auditoría. También puede exportar los registros de auditoría de buzón de correo y administración que se le envíen dentro de 24 horas en un archivo XML que se adjunta a mensaje de correo electrónico.<br/><br/>Para obtener más información acerca de cómo exportar los registros de auditoría, consulte:  <br/><br/> [Exportar registros de auditoría de buzones](http://go.microsoft.com/fwlink/p/?LinkID=404104) <br/> [Ver y exportar el registro de auditoría de administración de centros de datos](http://go.microsoft.com/fwlink/p/?LinkId=404109) <br/> [Los cambios del grupo de roles de búsqueda o los registros de auditoría del administrador](http://go.microsoft.com/fwlink/p/?LinkId=404105) <br/>   [Informes de auditoría de Exchange](http://go.microsoft.com/fwlink/p/?LinkID=395232).  <br/> |
   
## <a name="supervisory-review-report"></a>Informe de revisión de supervisión

Con el informe de revisión de supervisión, puede ver el estado de todas las directivas de la revisión de supervisión de la organización. Para obtener más información, vea [Configure supervisión revisar las directivas para la organización](configure-supervision-policies.md).
  
## <a name="data-loss-prevention-reports"></a>Informes de prevención de pérdida de datos

Informes de prevención de pérdida de datos (DLP) contienen información acerca de las directivas DLP y las reglas que se han aplicado al contenido contienen datos confidenciales en su organización de Office 365. También puede configurar el informe para mostrar información acerca de las acciones de DLP que se basaban en su directiva de DLP y reglas. Para obtener más información, vea [Ver el informe de prevención de pérdida de datos](view-the-dlp-reports.md).
