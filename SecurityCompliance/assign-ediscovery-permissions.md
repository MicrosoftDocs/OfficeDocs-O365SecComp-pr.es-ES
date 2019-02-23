---
title: Asignar permisos de exhibición de documentos electrónicos en &amp; el centro de seguridad y cumplimiento de Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 5b9a067b-9d2e-4aa5-bb33-99d8c0d0b5d7
description: Asigne los permisos necesarios para realizar tareas relacionadas con la exhibición de documentos &amp; electrónicos mediante el centro de seguridad y cumplimiento.
ms.openlocfilehash: c4dcbf51282aa2887fd7d5032eb8587b5e9d56d7
ms.sourcegitcommit: a80bd8626720fabdf592b84e4424cd3a83d08280
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/23/2019
ms.locfileid: "30223279"
---
# <a name="assign-ediscovery-permissions-in-the-office-365-security-amp-compliance-center"></a>Asignar permisos de exhibición de documentos electrónicos en &amp; el centro de seguridad y cumplimiento de Office 365

Si desea que los usuarios usen cualquiera de las herramientas relacionadas con la exhibición de documentos electrónicos en &amp; el centro de seguridad y cumplimiento de Office 365, tiene que asignarles los permisos adecuados. La forma más sencilla de hacerlo es agregar la persona el grupo de roles apropiado en la página de **permisos** del centro de seguridad &amp; y cumplimiento de Office 365. En este tema se describen los permisos necesarios para realizar tareas relacionadas con la exhibición &amp; de documentos electrónicos mediante el centro de seguridad y cumplimiento. 
  
El grupo de roles relacionado con eDiscovery principal del &amp; centro de seguridad y cumplimiento se llama **Administrador de exhibición**de documentos electrónicos. Hay dos subgrupos dentro de este grupo de roles. 
  
- **administradores de eDiscovery** : un administrador de exhibición de documentos electrónicos puede usar la herramienta &amp; de búsqueda de contenido en el centro de seguridad y cumplimiento para buscar ubicaciones de contenido en la organización y realizar diversas acciones relacionadas con la búsqueda, como la vista previa y la búsqueda de exportación. obtener. Los miembros también pueden crear y administrar casos de eDiscovery, agregar y quitar miembros de un caso, crear suspensiones de casos y ejecutar búsquedas de contenido asociadas a un caso, y obtener acceso a datos de caso en eDiscovery avanzado de Office 365.  Los administradores de eDiscovery solo pueden acceder y administrar los casos que crean. No pueden acceder ni administrar los casos creados por otros administradores de exhibición de documentos electrónicos. 
    
- **administradores de exhibición** de documentos electrónicos: un administrador de exhibición de documentos electrónicos es miembro del grupo de roles eDiscovery Manager y puede realizar las mismas tareas relacionadas con la búsqueda de contenido y la administración de casos que puede realizar un administrador de exhibición de documentos electrónicos. Además, un administrador de eDiscovery puede: 
    
  - Obtenga acceso a todos los casos que aparecen en la página **casos** de eDiscovery &amp; en el centro de seguridad y cumplimiento. 

  - Obtenga acceso a los datos de caso en eDiscovery avanzado para cualquier caso de la organización.
    
  - Administrar cualquier caso de exhibición de documentos electrónicos después de haberse agregado como miembro del caso.
  
  Consulte la sección [More Information](#more-information) para ver los motivos por los que puede desear que los administradores de eDiscovery de su organización. 

> [!NOTE]
> Para analizar los datos de un usuario con la exhibición avanzada de documentos electrónicos, el usuario (el custodio de los datos) debe tener asignada una licencia de Office 365 E5. Como alternativa, se puede asignar una licencia independiente de eDiscovery avanzado a los usuarios con una licencia de Office 365 E1 o E3. Los administradores y los responsables de cumplimiento que se asignan a los casos y usan la exhibición avanzada de documentos electrónicos para analizar los datos no necesitan una licencia E5.  
  
## <a name="before-you-begin"></a>Antes de empezar

- Debe ser miembro del grupo de roles de administración de la organización (o tener asignado el rol de administración de roles) para asignar permisos de exhibición &amp; de documentos electrónicos en el centro de seguridad y cumplimiento.
    
- Puede usar el cmdlet [Add-RoleGroupMember](https://technet.microsoft.com/en-us/library/dd638207%28v=exchg.160%29.aspx) del centro de &amp; seguridad y cumplimiento de PowerShell para agregar un grupo de seguridad habilitado para correo como miembro del subgrupo administradores de eDiscovery en el grupo de roles eDiscovery Manager. Sin embargo, no puede Agregar un grupo de seguridad habilitado para correo al subgrupo administradores de eDiscovery. Consulte la sección [More Information](#more-information) para obtener más información. 
    
## <a name="assign-ediscovery-permissions-in-the-security-amp-compliance-center"></a>Asignar permisos de exhibición de documentos &amp; electrónicos en el centro de seguridad y cumplimiento

1. Vaya a [https://protection.office.com](https://protection.office.com).
    
2. Inicie sesión en Office 365 con su cuenta profesional o educativa.
    
3. En el panel izquierdo del centro de &amp; seguridad y cumplimiento, haga clic en **permisos**y, a continuación, haga clic en la casilla situada junto a **Administrador de exhibición**de documentos electrónicos.
    
4. En la página flotante del **Administrador de exhibición** de documentos electrónicos, realice una de las siguientes acciones en función de los permisos de exhibición de documentos electrónicos que desee asignar. 
    
  - **Para convertir un usuario en Administrador de exhibición** de documentos electrónicos Junto a **Administrador de exhibición**de documentos electrónicos, haga clic en **Editar**. En **administradores de exhibición**de documentos electrónicos seleccionados, haga clic ![en **Editar**y en agregar icono](media/ITPro-EAC-AddIcon.gif) **Agregar**. Seleccione el usuario (o usuarios) que desea agregar como administrador de exhibición de documentos electrónicos y, a continuación, haga clic en **Agregar**. Cuando haya terminado de agregar usuarios, haga clic en **listo**. A continuación, en la página de edición seleccionar el control flotante de **eDiscovery Manager** , haga clic en **Guardar** para guardar los cambios en la perTenencia al administrador de eDiscovery. 
    
  - **Para convertir un usuario en Administrador de exhibición** de documentos electrónicos Junto a **Administrador de exhibición**de documentos electrónicos, haga clic en **Editar**. En **administradores de eDiscovery seleccionados**, haga clic en **Editar**y, ![a continuación](media/ITPro-EAC-AddIcon.gif) , haga clic en agregar icono **Agregar**. Seleccione el usuario (o usuarios) que desea agregar como administrador de exhibición de documentos electrónicos y, a continuación, haga clic en **Agregar**. Cuando haya terminado de agregar usuarios, haga clic en **listo**. A continuación, en la página de **edición de elegir administrador de exhibición** de documentos electrónicos, haga clic en **Guardar** para guardar los cambios en la perTenencia del administrador de exhibición de documentos electrónicos. 
    
> [!NOTE]
> También puede usar el cmdlet **Add-eDiscoveryCaseAdmin** para que un usuario sea administrador de exhibición de documentos electrónicos. Sin embargo, al usuario se le debe asignar el rol de administración de casos antes de que pueda usar este cmdlet para convertirlo en Administrador de exhibición de documentos electrónicos. Para obtener más información, vea [Add-eDiscoveryCaseAdmin](https://go.microsoft.com/fwlink/p/?LinkID=798217). 
  
En la página **permisos** del centro de &amp; seguridad y cumplimiento, también puede asignar permisos relacionados con la exhibición de documentos electrónicos, agregándolos a los grupos de roles administrador de cumplimiento, administración de la organización y revisor. Para obtener una descripción de los roles RBAC relacionados con la exhibición de documentos electrónicos asignados a cada uno de estos grupos de roles, consulte la sección [roles de RBAC relacionados con la exhibición](#rbac-roles-related-to-ediscovery) de documentos electrónicos. 

## <a name="rbac-roles-related-to-ediscovery"></a>Roles RBAC relacionados con la exhibición de documentos electrónicos

En la siguiente tabla se enumeran los roles RBAC relacionados con la exhibición de documentos electrónicos en el centro de cumplimiento de seguridad & y se indican los grupos de roles integrados a los que cada rol está asignado de forma predeterminada. 
    
|**Función**|**Administrador de cumplimiento**|**Administrador de eDiscovery & administrador**|**Administración de organizaciones**|**Reviewer**|
|:-----|:-----:|:-----:|:-----:|:-----:|
|Administración de casos <br/> |![Marca de verificación](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> |![Marca de verificación](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> |![Marca de verificación](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> | <br/> |
|Búsqueda de cumplimiento <br/> |![Marca de verificación](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> |![Marca de verificación](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> |![Marca de verificación](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> | <br/> |
|Exportar <br/> | <br/> |![Marca de verificación](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> | <br/> | <br/> |
|Retención <br/>  |![Marca de verificación](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> |![Marca de verificación](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> |![Marca de verificación](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> | <br/> |
|Vista previa <br/>  | <br/> |![Marca de verificación](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> | <br/> | <br/> |
|Revisión <br/>  | <br/> |![Marca de verificación](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> | <br/> |![Marca de verificación](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> |
|DesCifrado de RMS <br/>  ||![Marca de verificación](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> |||
|Búsqueda y dePuración <br/> | <br/> | <br/> |![Marca de verificación](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/> | <br/> | 
||||
  
En las secciones siguientes se describe cada uno de los roles RBAC relacionados con la exhibición de documentos electrónicos que aparecen en la tabla anterior.

### <a name="case-management"></a>Administración de casos

Este rol permite a los usuarios crear, editar, eliminar y controlar el acceso a casos de eDiscovery en el centro de seguridad & cumplimiento. Para obtener más información, vea [administrar casos de eDiscovery en el centro &amp; de seguridad y cumplimiento de Office 365](manage-ediscovery-cases.md). Como se ha explicado anteriormente, a un usuario se le debe asignar el rol de administración de casos antes de poder usar el cmdlet **Add-eDiscoveryCaseAdmin** para convertirlo en Administrador de exhibición de documentos electrónicos. 

### <a name="compliance-search"></a>Búsqueda de cumplimiento

Este rol permite a los usuarios ejecutar la herramienta de búsqueda de contenido en el centro de seguridad & cumplimiento para buscar en buzones de correo y carpetas públicas, sitios de SharePoint Online, sitios de OneDrive para la empresa, conversaciones de Skype empresarial, grupos de Office 365 y Microsoft Teams. Este rol permite al usuario obtener una estimación de los resultados de la búsqueda y crear informes de exportación, pero se necesitan roles adicionales para iniciar acciones de búsqueda de contenido, como la vista previa, la exportación o la eliminación de los resultados de la búsqueda.

Tenga en cuenta que los usuarios que tengan asignado el rol de búsqueda de cumplimiento pero que no tengan el rol de vista previa pueden obtener una vista previa de los resultados de una búsqueda en la que un usuario que tenga asignada la función de vista previa haya iniciado la acción de vista previa. El usuario sin el rol vista previa puede obtener una vista previa de los resultados durante 2 semanas después de que se haya creado la acción de vista previa inicial.

De forma similar, los usuarios que tienen asignado el rol de búsqueda de cumplimiento pero no tienen la función exportar pueden descargar los resultados de una búsqueda en la que la acción de exportación ha sido iniciada por un usuario que tiene asignada la función exportar. El usuario sin el rol exportar puede descargar los resultados de una búsqueda durante 2 semanas después de que se haya creado la acción de exportación inicial. Después de eso, no podrán descargar los resultados a menos que un usuario con el rol exportar reinicie la exportación.

Para obtener más información, consulte [búsqueda de contenido en Office 365](content-search.md). 

### <a name="export"></a>Exportar

El rol permite a los usuarios exportar los resultados de una búsqueda de contenido a un equipo local. También les permite preparar los resultados de búsqueda para el análisis en eDiscovery avanzado. 

Para obtener más información acerca de la exportación de resultados de búsqueda, vea [exportar resultados de búsqueda desde el centro de cumplimiento de Office 365 Security &](export-search-results.md).

### <a name="hold"></a>Retención

Este rol permite a los usuarios poner contenido en buzones de correo, carpetas públicas, sitios, conversaciones de Skype empresarial y grupos de Office 365 en suspensión. Cuando el contenido está en espera, los propietarios de contenido podrán modificar o eliminar el contenido original, pero el contenido se conservará hasta que se quite la retención o hasta que expire la duración de retención. 

Para obtener más información acerca de las suspensiones, consulte:

- [casos de eDiscovery en el centro de seguridad & cumplimiento de Office 365](ediscovery-cases.md) 
- [Información general sobre las directivas de retención](retention-policies.md)

### <a name="preview"></a>Vista previa

Este rol permite a los usuarios ver una lista de elementos devueltos de una búsqueda de contenido. También podrán abrir y ver cada elemento de la lista para ver su contenido.

### <a name="review"></a>Revisión

Esta función permite a los usuarios acceder a datos de casos en la exhibición avanzada de documentos electrónicos de Office 365. El objetivo principal de este rol es proporcionar a los usuarios acceso a la exhibición avanzada de documentos electrónicos. Los usuarios que tienen asignado este rol pueden ver y abrir la lista de casos en la página de exhibición de documentos electrónicos en el centro de seguridad & cumplimiento del que son miembros. Una vez que el usuario tiene acceso a un caso en el centro de seguridad & cumplimiento, puede hacer clic en **cambiar a eDiscovery avanzado** para acceder y analizar los datos del caso en la exhibición avanzada de documentos electrónicos. Este rol no permite al usuario obtener una vista previa de los resultados de una búsqueda de contenido asociada con el caso o para realizar otras tareas de búsqueda de contenido o de administración de casos.

### <a name="rms-decrypt"></a>DesCifrado de RMS

Este rol permite a los usuarios descifrar mensajes de correo electrónico cifrados con RMS al exportar resultados de búsqueda o preparar resultados de búsqueda para analizarlos en eDiscovery avanzado. Para obtener más información acerca del descifrado de los resultados de la búsqueda durante la exportación, consulte [exportar resultados de búsqueda desde el centro de seguridad _AMP_ cumplimiento de Office 365](export-search-results.md).

### <a name="search-and-purge"></a>Búsqueda y dePuración

Este rol permite a los usuarios realizar la eliminación masiva de datos que coinciden con los criterios de una búsqueda de contenido. Para obtener más información, vea [Buscar y eliminar mensajes de correo electrónico en la organización de Office 365](search-for-and-delete-messages-in-your-organization.md). 


## <a name="more-information"></a>Más información

- **¿Por qué crear un administrador de exhibición** de documentos electrónicos? Como se ha explicado anteriormente, un administrador de eDiscovery es miembro del grupo de roles eDiscovery Manager que puede ver y tener acceso a todos los casos de eDiscovery de su organización. Esta capacidad de tener acceso a todos los casos de eDiscovery tiene dos propósitos importantes: 
    
  - Si una persona que es el único miembro de un caso de exhibición de documentos electrónicos deja a su organización, nadie (incluidos los miembros del grupo de roles de administración de la organización u otro miembro del grupo de roles de eDiscovery Manager) puede tener acceso a ese caso de eDiscovery porque no son miembros. de un caso. En esta situación, no habría ninguna forma de obtener acceso a los datos en el caso. Pero como un administrador de eDiscovery puede tener acceso a todos los casos de eDiscovery de la organización, pueden ver el &amp; caso en el centro de seguridad y cumplimiento y agregarse a sí mismos o a otro administrador de eDiscovery como miembro del caso.
    
  - Dado que un administrador de eDiscovery puede ver y tener acceso a todos los casos de eDiscovery, puede auditar y supervisar todos los casos y las búsquedas de cumplimiento asociadas. Esto puede ayudar a evitar cualquier uso incorrecto de las búsquedas de cumplimiento o los casos de exhibición de documentos electrónicos. Y, dado que los administradores de eDiscovery pueden tener acceso a información potencialmente confidencial en los resultados de una búsqueda de cumplimiento, debe limitar el número de usuarios que son administradores de eDiscovery.
    
    Además, los administradores de eDiscovery del centro &amp; de seguridad y cumplimiento se agregan automáticamente como administradores en la exhibición avanzada de documentos electrónicos. Esto significa que una persona debe ser un administrador de eDiscovery para realizar tareas administrativas en la exhibición avanzada de documentos electrónicos, como la configuración de usuarios, la creación de casos y la importación de datos en un caso.
    
- **¿Puedo agregar un grupo como miembro del grupo de roles eDiscovery Manager en el centro de &amp; seguridad y cumplimiento?** Como se ha explicado anteriormente, puede Agregar un grupo de seguridad habilitado para correo como miembro del subgrupo administradores de eDiscovery en el grupo de roles administrador de eDiscovery mediante el cmdlet **Add-RoleGroupMember** del PowerShell del centro de cumplimiento de seguridad &amp; . Por ejemplo, puede ejecutar el siguiente comando para agregar un grupo de seguridad habilitado para correo al grupo de roles eDiscovery Manager. 
    
  ```
  Add-RoleGroupMember "eDiscovery Manager" -Member <name of security group>
  ```

    Tenga en cuenta que no se admite un grupo de distribución de Exchange o un grupo de Office 365. Debe usar un grupo de seguridad habilitado para correo, que puede crear en Exchange Online PowerShell con el ` New-DistributionGroup -Type Security ` comando. También puede crear un grupo de seguridad habilitado para correo (y agregar miembros) en el centro de administración de Exchange o en el centro de administración de Office 365. Tenga en cuenta que puede tardar hasta 60 minutos después de crear una nueva seguridad habilitada para correo que esté disponible para agregarla al grupo de roles eDiscovery Managers. 
    
    Además, como se mencionó anteriormente, no puede hacer que un grupo de seguridad habilitado para correo sea administrador de eDiscovery mediante el cmdlet &amp; **Add-EDiscoveryCaseAdmin** en el PowerShell del centro de cumplimiento de seguridad. Solo puede Agregar usuarios individuales como administradores de exhibición de documentos electrónicos. 
    
    Tenga en cuenta que tampoco puede Agregar un grupo de seguridad habilitado para correo como miembro de un caso.
