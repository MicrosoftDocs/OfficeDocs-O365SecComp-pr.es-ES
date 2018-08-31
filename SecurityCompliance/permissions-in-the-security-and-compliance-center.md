---
title: Los permisos de la seguridad de Office 365 &amp; centro de cumplimiento
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 6/29/2018
ms.audience: Admin
ms.topic: overview
f1_keywords:
- ms.o365.cc.AdminRoleGroups
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: d10608af-7934-490a-818e-e68f17d0e9c1
description: La seguridad de Office 365 &amp; centro de cumplimiento le permite conceder permisos a las personas que realicen tareas de cumplimiento de normas como la administración de dispositivos, prevención de pérdida de datos, exhibición de documentos electrónicos, retención y así sucesivamente. Estas personas pueden realizar sólo las tareas que se explícitamente les concede acceso a. Para obtener acceso a la seguridad &amp; centro de cumplimiento, los usuarios deben ser un administrador global de Office 365 o un miembro de uno o más seguridad &amp; grupos de roles de centro de cumplimiento.
ms.openlocfilehash: e393bad7c3a57b0734835e56fcd781cc31327c18
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "23013434"
---
# <a name="permissions-in-the-office-365-security-amp-compliance-center"></a>Los permisos de la seguridad de Office 365 &amp; centro de cumplimiento

La seguridad de Office 365 &amp; centro de cumplimiento le permite conceder permisos a las personas que realicen tareas de cumplimiento de normas como la administración de dispositivos, prevención de pérdida de datos, exhibición de documentos electrónicos, retención y así sucesivamente. Estas personas pueden realizar sólo las tareas que se explícitamente les concede acceso a. Para obtener acceso a la seguridad &amp; centro de cumplimiento, los usuarios deben ser un administrador global de Office 365 o un miembro de uno o más seguridad &amp; grupos de roles de centro de cumplimiento.
  
Los permisos de la seguridad &amp; centro de cumplimiento se basan en el modelo de permisos de Control de acceso en función de roles (RBAC). Éste es el mismo modelo de permisos que se usa en Exchange, por lo que si está familiarizado con Exchange, concesión de permisos en la seguridad &amp; centro de cumplimiento será muy similar. Es importante recordar, sin embargo, esa función de Exchange grupos y seguridad &amp; grupos de roles de centro de cumplimiento no compartan pertenencia o los permisos. Mientras tanto disponer de un grupo de funciones de administración de la organización, no son el mismo. Los permisos que se concedan y los miembros de los grupos de funciones, son diferentes. Hay una lista de seguridad &amp; grupos de roles de centro de cumplimiento que aparece a continuación.
  
![Permisos de página en la seguridad de Office 365 &amp; centro de cumplimiento](media/992c20ca-e82e-497c-9c8d-6fab212deb80.png)
  
## <a name="relationship-of-members-roles-and-role-groups"></a>Relación de los miembros, los roles y los grupos de roles

Un **rol** concede permisos para realizar un conjunto de tareas; por ejemplo, el rol de administración de casos permite trabajar con casos de exhibición de documentos electrónicos. 
  
Un **grupo de roles** es un conjunto de funciones que permite a los usuarios realizar su trabajo a través de la seguridad &amp; centro de cumplimiento de normas; Por ejemplo, el grupo de roles de administrador de cumplimiento de normas incluye las funciones de administración de casos, la búsqueda de contenido y configuración de la organización (además de otras personas) debido a que una persona que es un administrador de cumplimiento de normas tendrá los permisos para las tareas realizar su trabajo. 
  
La seguridad &amp; centro de cumplimiento incluye grupos de roles de forma predeterminada para las tareas y las funciones que necesita asignar personas a más comunes. Se recomienda agregar simplemente usuarios individuales como **miembros** a los grupos de roles de forma predeterminada. 
  
![Diagrama que muestra la relación de los grupos de roles con los roles y los miembros](media/2a16d200-968c-4755-98ec-f1862d58cb8b.png)
  
Puede editar o eliminar los grupos de roles existentes, pero no se recomienda esto. En lugar de modificar un grupo de roles de forma predeterminada, puede copiarlo, modificarlo y, a continuación, guárdelo con un nombre diferente.
  
## <a name="permissions-needed-to-use-features-in-the-security-amp-compliance-center"></a>Permisos necesarios para usar las características de la seguridad &amp; centro de cumplimiento

En la siguiente tabla se enumera los grupos de roles predeterminados que están disponibles en la seguridad &amp; centro de cumplimiento. Para conceder permisos a un usuario para realizar una tarea de cumplimiento, agregarlos a la seguridad adecuada &amp; grupo de roles de centro de cumplimiento.
  
Administración de permisos en la seguridad &amp; centro de cumplimiento sólo proporciona a los usuarios acceso a las características de cumplimiento que están disponibles dentro de la seguridad &amp; centro de cumplimiento propio. Si desea conceder permisos para otras características de cumplimiento que no están disponibles en la seguridad &amp; centro de cumplimiento, como las reglas de transporte de Exchange, tiene que usar el centro de administración de Exchange.
  
Para ver cómo conceder acceso a la seguridad &amp; centro de cumplimiento, desprotección [conceder a los usuarios acceso al centro de administración de cumplimiento de normas de Office 365](grant-access-to-the-security-and-compliance-center.md).
  
|**Grupo de funciones**|**Descripción**|
|:-----|:-----|
|**Administrador de cumplimiento de normas** <sup>1</sup> <br/> |Los miembros pueden administrar la configuración de administración de dispositivos, prevención de pérdida de datos, informes y conservación.  <br/> |
|**Administrador de exhibición de documentos electrónicos** <br/> | Los miembros pueden realizar búsquedas y aplicar retenciones en buzones de correo, sitios de SharePoint Online y ubicaciones de OneDrive para la Empresa. Los miembros pueden también crear y administrar casos de exhibición de documentos electrónicos, agregar y quitar a miembros de un caso, crear y modificar búsquedas de contenido de normas asociadas con un caso.<br/>  Un administrador de exhibición de documentos electrónicos es un miembro del grupo de roles de administrador de exhibición de documentos electrónicos al que se ha asignado permisos adicionales. Un administrador de exhibición de documentos electrónicos puede hacer lo siguiente:<br/>  Ver todos los casos de exhibición de documentos electrónicos de la organización.  <br/>  Administrar cualquier caso de exhibición de documentos electrónicos después de haberse agregado como miembro del caso.  <br/>  Acceso a Office 365 avanzada exhibición de documentos electrónicos. Esto es debido a que los administradores de la exhibición de documentos electrónicos se agregan automáticamente como administradores de exhibición de documentos electrónicos avanzada. Tenga en cuenta que tiene que ser un administrador en la seguridad de exhibición de documentos electrónicos &amp; centro de cumplimiento para tener acceso a la exhibición de documentos electrónicos avanzada. Para obtener más información acerca de cómo realizar un administrador de exhibición de documentos electrónicos de un usuario, vea [casos de exhibición de documentos electrónicos en la seguridad de Office 365 &amp; centro de cumplimiento](https://go.microsoft.com/fwlink/p/?LinkId=780738).<br/> Si desea ofrecer a un usuario privilegios administrativos en la exhibición de documentos electrónicos avanzada pero no desea realizar un administrador de exhibición de documentos electrónicos en la seguridad &amp; centro de cumplimiento, puede agregarlos al grupo de roles de administrador de exhibición de documentos electrónicos y, a continuación, agregarlas como un administrador en Opciones avanzada de exhibición de documentos electrónicos. Para obtener instrucciones, consulte [configuración de los usuarios y los casos de exhibición de documentos electrónicos avanzada de Office 365](https://go.microsoft.com/fwlink/p/?LinkId=780696).           |
|**Administración de la organización** <sup>1</sup> <br/> |Los miembros pueden controlar los permisos para obtener acceso a las características de la seguridad &amp; centro de cumplimiento y también administrar la configuración de administración de dispositivos, prevención de pérdida de datos, informes y conservación.  <br/> Tenga en cuenta en orden para un usuario que no sea un administrador global para ver la lista de los dispositivos administrados por MDM para Office 365 y realizar acciones en estos dispositivos, como la retirada de un dispositivo de MDM para Office 365, el usuario debe ser un administrador de Exchange.  <br/> Los administradores globales de Office 365 se agregan automáticamente como miembros de este grupo de funciones.           |
|**Administración de registros** <br/> |Los miembros pueden administrar y eliminar contenido de registro.  <br/> |
|**Reviewer** <br/> |Los miembros sólo pueden ver la lista de los casos en la página de casos de exhibición de documentos electrónicos en la seguridad &amp; centro de cumplimiento. No se puede crear, abrir o administrar un caso de exhibición de documentos electrónicos. Es el propósito principal de este grupo de funciones permitir que los miembros de la vista y acceso a datos en la exhibición de documentos electrónicos avanzada de casos.  <br/> Este grupo de roles tiene los permisos más restrictivos relacionados con la exhibición de documentos electrónicos.  <br/> |
|**Administrador de seguridad** <br/> |Pertenencia a este grupo de funciones se sincronizan entre los servicios y administran de forma centralizada. Este grupo de funciones no es fácil de administrar a través de los portales de administrador. Los miembros de este grupo de funciones pueden incluir los administradores entre-service, así como grupos de socios externos y Microsoft Support. De forma predeterminada, este grupo no se puede asignar cualquier funciones. Sin embargo, será un miembro de los grupos de funciones de los administradores de seguridad y heredará las capacidades de ese grupo de roles.  <br/> Todos los permisos de sólo lectura de la función de lector de seguridad, además de un número de permisos administrativos adicionales para los servicios del mismos: protección de la información de Azure, centro de protección de identidad, con privilegios de administración de identidades, servicio de Monitor de Office 365 Salud y seguridad de Office 365 &amp; centro de cumplimiento.  <br/> |
|**Lector de seguridad** <br/> |Los miembros tienen acceso de sólo lectura en un número de características de seguridad del centro de protección de identidad, con privilegios de administración de identidades, estado del servicio Monitor de Office 365 y Office 365 seguridad &amp; centro de cumplimiento.  <br/> Pertenencia a este grupo de funciones se sincronizan entre los servicios y administran de forma centralizada. Este grupo de funciones no es fácil de administrar a través de los portales de administrador. Los miembros de este grupo de funciones pueden incluir los administradores entre-service, así como grupos de socios externos y Microsoft Support. De forma predeterminada, este grupo no se puede asignar cualquier funciones. Sin embargo, será un miembro de los grupos de roles de seguridad lector y heredará las capacidades de ese grupo de roles.  <br/> |
|**Usuario de garantía de servicio** <br/> |Los miembros pueden tener acceso a la sección de garantía de servicio en la seguridad de Office 365 &amp; centro de cumplimiento. Garantía de servicio proporciona informes y documentos que se describen las prácticas de seguridad de Microsoft para los datos de cliente que se almacenan en Office 365. También proporciona informes de auditoría de otro fabricante independiente en Office 365. Para obtener más información, vea [Service assurance en la seguridad de Office 365 &amp; centro de cumplimiento](http://go.microsoft.com/fwlink/p/?LinkID=717765).<br/> |
|**Revisión de supervisión** <br/> |Los miembros pueden crear y administrar las directivas que definen que comunicaciones están sujetas a la revisión de una organización. Para obtener más información, vea [Configure supervisión revisar las directivas para la organización](configure-supervision-policies.md).<br/> |
   
> [!NOTE]
> <sup>1</sup> este grupo de funciones no asigne los permisos necesarios para buscar el registro de auditoría de Office 365 o para usar los informes que pueden incluir datos de Exchange, como los informes de DLP o ATP (miembros). Para buscar el registro de auditoría o para ver todos los informes, un usuario tiene que asignar permisos en Exchange Online. Esto es debido a que el cmdlet subyacente que sirven para buscar el registro de auditoría es un cmdlet de Exchange Online. Los administradores globales de Office 365 pueden buscar en el registro de auditoría y ver todos los informes de porque está agrega automáticamente como miembros del grupo de roles de administración de la organización de Exchange Online. Para obtener más información, vea [Buscar en el registro de auditoría de la seguridad de Office 365 &amp; centro de cumplimiento](https://go.microsoft.com/fwlink/p/?LinkID=708432). 
  

