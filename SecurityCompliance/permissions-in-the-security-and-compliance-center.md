---
title: Permisos en el centro de seguridad &amp; y cumplimiento de Office 365
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 6/29/2018
ms.audience: Admin
ms.topic: overview
f1_keywords:
- ms.o365.cc.AdminRoleGroups
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: d10608af-7934-490a-818e-e68f17d0e9c1
description: El centro de seguridad &amp; y cumplimiento de Office 365 le permite conceder permisos a personas que realizan tareas de cumplimiento como la administración de dispositivos, prevención de pérdida de datos, eDiscovery, retención, etc. Estos usuarios solo pueden realizar las tareas a las que les conceda acceso de forma explícita. Para obtener acceso al &amp; centro de seguridad y cumplimiento, los usuarios deben ser un administrador global de Office 365 o miembro de uno &amp; o varios grupos de roles del centro de cumplimiento de seguridad.
ms.openlocfilehash: e935c71f9324dbce8e0b359bfe723b93ff500b0a
ms.sourcegitcommit: 48fa456981b5c52ab8aeace173c8366b9f36723b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2019
ms.locfileid: "30341361"
---
# <a name="permissions-in-the-office-365-security-amp-compliance-center"></a>Permisos en el centro de seguridad &amp; y cumplimiento de Office 365

El centro de seguridad &amp; y cumplimiento de Office 365 le permite conceder permisos a personas que realizan tareas de cumplimiento como la administración de dispositivos, prevención de pérdida de datos, eDiscovery, retención, etc. Estos usuarios solo pueden realizar las tareas a las que les conceda acceso de forma explícita. Para obtener acceso al &amp; centro de seguridad y cumplimiento, los usuarios deben ser un administrador global de Office 365 o miembro de uno &amp; o varios grupos de roles del centro de cumplimiento de seguridad.
  
Los permisos en el &amp; centro de seguridad y cumplimiento se basan en el modelo de permisos de control de acceso basado en roles (RBAC). Se trata del mismo modelo de permisos que usa Exchange, por lo que, si está familiarizado con Exchange, conceder permisos en &amp; el centro de seguridad y cumplimiento será muy similar. Sin embargo, es importante recordar que los grupos de roles de Exchange y &amp; los grupos de roles del centro de seguridad no comparten pertenencia o permisos. Aunque ambos tienen un grupo de roles de administración de la organización, no son iguales. Los permisos que conceden y los miembros de los grupos de roles son distintos. A continuación se incluye una lista &amp; de los grupos de roles del centro de cumplimiento de seguridad.
  
![Página de permisos en el centro de &amp; seguridad y cumplimiento de Office 365](media/992c20ca-e82e-497c-9c8d-6fab212deb80.png)
  
## <a name="relationship-of-members-roles-and-role-groups"></a>Relación de los miembros, los roles y los grupos de roles

Un **rol** concede permisos para realizar un conjunto de tareas; por ejemplo, el rol de administración de casos permite trabajar con casos de exhibición de documentos electrónicos. 
  
Un **grupo de roles** es un conjunto de roles que permite que los usuarios realicen su &amp; trabajo en el centro de seguridad y cumplimiento; por ejemplo, el grupo de roles de administrador de cumplimiento incluye los roles para la administración de casos, la búsqueda de contenido y la configuración de la organización (además de otros) porque alguien que es un administrador de cumplimiento necesitará los permisos para esas tareas para realizar su trabajo. 
  
El centro &amp; de seguridad y cumplimiento incluye grupos de roles predeterminados para las tareas y funciones más comunes que necesitará asignar a los usuarios. Le recomendamos que agregue simplemente usuarios individuales como **miembros** a los grupos de roles predeterminados. 
  
![Diagrama que muestra la relación de los grupos de roles con los roles y los miembros](media/2a16d200-968c-4755-98ec-f1862d58cb8b.png)
  
Puede editar o eliminar los grupos de roles existentes, pero no lo recomendamos. En lugar de editar un grupo de roles predeterminado, puede copiarlo, modificarlo y, a continuación, guardarlo con un nombre diferente.
  
## <a name="permissions-needed-to-use-features-in-the-security-amp-compliance-center"></a>Permisos necesarios para usar características en el centro &amp; de seguridad y cumplimiento

En la siguiente tabla se enumeran los grupos de funciones predeterminados &amp; que están disponibles en el centro de seguridad y cumplimiento. Para conceder permisos a un usuario para que realice una tarea de cumplimiento, agréguelos al grupo &amp; de funciones del centro de cumplimiento de seguridad adecuado.
  
La administración de permisos en &amp; el centro de seguridad y cumplimiento solo proporciona a los usuarios acceso a las características de &amp; cumplimiento que están disponibles en el propio centro de seguridad y cumplimiento. Si desea conceder permisos a otras características de cumplimiento que no se encuentren &amp; en el centro de seguridad y cumplimiento, como reglas de flujo de correo de Exchange (también conocidas como reglas de transporte), debe usar el centro de administración de Exchange.
  
Para ver cómo conceder acceso al centro de &amp; seguridad y cumplimiento, consulte [proporcionar a los usuarios acceso al centro de administración de cumplimiento de Office 365](grant-access-to-the-security-and-compliance-center.md).
  
|**Grupo de funciones**|**Descripción**|
|:-----|:-----|
|**Administrador de cumplimiento** <sup>1</sup> <br/> |Los miembros pueden administrar la configuración de la administración de dispositivos, la prevención de pérdida de datos, los informes y la conservación.  <br/> |
|**Administrador de exhibición de documentos electrónicos** <br/> | Los miembros pueden realizar búsquedas y realizar retenciones en buzones de correo, sitios de SharePoint Online y ubicaciones de OneDrive para la empresa. Los miembros también pueden crear y administrar casos de eDiscovery, agregar y quitar miembros de un caso, crear y editar búsquedas de contenido asociadas a un caso y obtener acceso a datos de caso en la exhibición avanzada de documentos electrónicos de Office 365.<br/><br/>Un administrador de eDiscovery es un miembro del grupo de roles eDiscovery Manager al que se le han asignado permisos adicionales. Además de las tareas que puede realizar un administrador de exhibición de documentos electrónicos, un administrador de eDiscovery puede:<br/><br/>  • Ver todos los casos de exhibición de documentos electrónicos de la organización.  <br/>  • Administrar cualquier caso de exhibición de documentos electrónicos después de que se agreguen como miembro del caso.  <br/><br/>La principal diferencia entre un administrador de eDiscovery y un administrador de exhibición de documentos electrónicos es que una exhibición de documentos electrónicos por puede tener acceso a todos los casos &amp; que aparecen en la página casos de **eDiscovery** del centro de seguridad y cumplimiento. Un administrador de exhibición de documentos electrónicos solo puede tener acceso a los casos que han creado o los casos de los que son miembros.  Para obtener más información acerca de cómo convertir un usuario en un administrador de exhibición de documentos electrónicos, consulte [asignar permisos de exhibición de documentos electrónicos en el centro de seguridad &amp; y cumplimiento de Office 365](assign-ediscovery-permissions.md).<br/>           |
|**Administración** de la organización <sup>1</sup> <br/> |Los miembros pueden controlar los permisos para obtener acceso a las &amp; características del centro de seguridad y cumplimiento, y también administrar la configuración de la administración de dispositivos, la prevención de pérdida de datos, los informes y la conservación.  <br/> Tenga en cuenta que, para que un usuario que no es un administrador global pueda ver la lista de dispositivos administrados por MDM para Office 365 y realizar acciones en estos dispositivos, como retirar un dispositivo de MDM para Office 365, el usuario debe ser un administrador de Exchange.  <br/> Los administradores globales de Office 365 se agregan automáticamente como miembros de este grupo de roles.           |
|**Administración de registros** <br/> |Los miembros pueden administrar y eliminar contenido de registros.  <br/> |
|**Reviewer** <br/> |Los miembros solo pueden ver la lista de casos en la página casos de eDiscovery en &amp; el centro de seguridad y cumplimiento. No pueden crear, abrir o administrar un caso de exhibición de documentos electrónicos. El objetivo principal de este grupo de roles es permitir a los miembros ver y obtener acceso a los datos de casos en eDiscovery avanzado.  <br/> Este grupo de roles tiene los permisos más restrictivos relacionados con la exhibición de documentos electrónicos.  <br/> |
|**Administrador de seguridad** <br/> |Los miembros de este grupo de roles pueden incluir administradores de varios servicios, así como grupos de socios externos y soporte técnico de Microsoft. De forma predeterminada, este grupo no puede tener asignado ningún rol. Sin embargo, será un miembro de la función administradores de seguridad de Azure Active Directory y heredará las capacidades de esa función. Para administrar los permisos de forma centralizada, realice cambios en este rol en el centro de administración de Azure Active Directory (para obtener más información, vea [permisos de roles de administrador en Azure Active Directory](https://docs.microsoft.com/en-us/azure/active-directory/users-groups-roles/directory-assign-admin-roles)). Si edita este grupo de roles en el centro de seguridad & cumplimiento, dichos cambios solo se aplican al centro de seguridad & cumplimiento y no a otros servicios, mientras que los cambios realizados en el centro de administración de Azure Active Directory afectan a todos los servicios.<br/> Todos los permisos de solo lectura de la función lector de seguridad, además de varios permisos administrativos adicionales para los mismos servicios: Azure Information Protection, centro de protección de identidad, administración de identidades privilegiada, supervisar el servicio Office 365 Health y Office 365 Security &amp; Compliance Center.  <br/> |
|**Lector de seguridad** <br/> |Los miembros tienen acceso de solo lectura a varias características de seguridad del centro de protección de identidad, la administración de identidad con privilegios, el estado del servicio Office &amp; 365 y el centro de seguridad de Office 365.  <br/> La perTenencia a este grupo de roles se sincroniza entre los servicios y se administra de forma centralizada. Los miembros de este grupo de roles pueden incluir administradores de varios servicios, así como grupos de socios externos y soporte técnico de Microsoft. De forma predeterminada, este grupo no puede tener asignado ningún rol. Sin embargo, será un miembro del rol lectores de seguridad en Azure Active Directory y heredará las capacidades de dicho rol. Para administrar los permisos de forma centralizada, realice cambios en este rol en el centro de administración de Azure Active Directory (para obtener más información, vea [permisos de roles de administrador en Azure Active Directory](https://docs.microsoft.com/en-us/azure/active-directory/users-groups-roles/directory-assign-admin-roles)). Si edita este grupo de roles en el centro de seguridad & cumplimiento, dichos cambios solo se aplican al centro de seguridad & cumplimiento y no a otros servicios, mientras que los cambios realizados en el centro de administración de Azure Active Directory afectan a todos los servicios.<br/> |
|**Usuario de garantía de servicio** <br/> |Los miembros pueden acceder a la sección de garantía del servicio en &amp; el centro de seguridad y cumplimiento de Office 365. Garantía del servicio proporciona informes y documentos que describen los procedimientos de seguridad de Microsoft para los datos de clientes almacenados en Office 365. También proporciona informes de auditoría de terceros independientes en Office 365. Para obtener más información, vea [garantía del servicio en el centro &amp; de seguridad y cumplimiento de Office 365](http://go.microsoft.com/fwlink/p/?LinkID=717765).<br/> |
|**Revisión de supervisión** <br/> |Los miembros pueden crear y administrar las directivas que definen qué comunicaciones están sujetas a revisión en una organización. Para obtener más información, consulte [configurar las directivas de revisión de supervisión para su organización](configure-supervision-policies.md).<br/> |
   
> [!NOTE]
> <sup>1</sup> este grupo de roles no asigna a los miembros los permisos necesarios para buscar en el registro de auditoría de Office 365 o usar los informes que puedan incluir datos de Exchange, como los informes DLP o ATP. Para buscar en el registro de auditoría o para ver todos los informes, se debe asignar a un usuario permisos en Exchange Online. Esto se debe a que el cmdlet subyacente usado para buscar en el registro de auditoría es un cmdlet de Exchange Online. Los administradores globales de Office 365 pueden buscar en el registro de auditoría y ver todos los informes porque se agregan automáticamente como miembros del grupo de roles de administración de la organización en Exchange Online. Para obtener más información, vea [Buscar en el registro de auditoría del centro &amp; de seguridad y cumplimiento de Office 365](https://go.microsoft.com/fwlink/p/?LinkID=708432). 
  

