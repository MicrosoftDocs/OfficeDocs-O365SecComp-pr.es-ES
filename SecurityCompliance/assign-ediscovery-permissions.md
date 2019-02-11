---
title: Asignar permisos de exhibición de documentos electrónicos en la seguridad de Office 365 &amp; centro de cumplimiento
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 5b9a067b-9d2e-4aa5-bb33-99d8c0d0b5d7
description: Asigne los permisos necesarios para realizar tareas relacionadas con la exhibición de documentos electrónicos con la seguridad &amp; centro de cumplimiento.
ms.openlocfilehash: 95f0ed171c37ec84ca8bb8f00e69ab0318cd31cd
ms.sourcegitcommit: 7e2a0185cadea7f3a6afc5ddc445eac2e1ce22eb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/11/2019
ms.locfileid: "29741163"
---
# <a name="assign-ediscovery-permissions-in-the-office-365-security-amp-compliance-center"></a>Asignar permisos de exhibición de documentos electrónicos en la seguridad de Office 365 &amp; centro de cumplimiento

Si desea que las personas a usar cualquiera de las herramientas relacionadas con la exhibición de documentos electrónicos en la seguridad de Office 365 &amp; centro de cumplimiento, debe asignarles los permisos adecuados. La forma más sencilla de hacerlo es agregar la persona, el grupo de roles adecuados en la página de **permisos** en la seguridad de Office 365 &amp; centro de cumplimiento. En este tema se describe los permisos necesarios para realizar tareas relacionadas con la exhibición de documentos electrónicos con la seguridad &amp; centro de cumplimiento. 
  
El grupo de rol principal relacionadas con la exhibición de documentos electrónicos en seguridad &amp; centro de cumplimiento se denomina **Administrador de exhibición de documentos**. Existen dos subgrupos dentro de este grupo de funciones. 
  
- **los administradores de exhibición de documentos electrónicos** - una exhibición de documentos electrónicos el administrador puede usar la herramienta de búsqueda de contenido en la seguridad &amp; centro de cumplimiento para buscar ubicaciones de contenido de la organización y realizar varias acciones relacionadas con la búsqueda como vista previa y exportación de búsqueda resultados. (Miembros) puede también crear y administrar casos de exhibición de documentos electrónicos, agregar y quitar a miembros a un caso, crear casos suspensiones y ejecutar búsquedas de contenido asociado a un caso y los datos de access casos de exhibición de documentos electrónicos avanzada de Office 365.  Sólo puede tener acceso una exhibición de documentos electrónicos los administradores y administrar los casos que se creen. Que no se pueden tener acceso o administrar casos creados por otro jefes de exhibición de documentos electrónicos. 
    
- **exhibición de documentos electrónicos los administradores** - una exhibición de documentos electrónicos administrador es un miembro del grupo de roles de administrador de exhibición de documentos electrónicos y puede realizar la misma búsqueda de contenido y casos tareas relacionadas con la administración que puede realizar un administrador de exhibición de documentos electrónicos. Además, un administrador de exhibición de documentos electrónicos puede: 
    
  - Obtener acceso a todos los casos que se enumeran en la página de **casos de exhibición de documentos electrónicos** en la seguridad &amp; centro de cumplimiento. 

  - Acceso a datos de mayúsculas y minúsculas en Avanzadas exhibición de documentos electrónicos para cualquier caso en la organización.
    
  - Administrar cualquier caso de exhibición de documentos electrónicos después de haberse agregado como miembro del caso.
  
  Por motivos de por qué es posible que desea que los administradores de la exhibición de documentos electrónicos en su organización, vea la sección [obtener más información](#more-information) . 

> [!NOTE]
> Para analizar los datos de un usuario mediante la exhibición de documentos electrónicos avanzada, el usuario (la custodia de los datos) debe estar asignado una licencia de Office 365 E5. Como alternativa, se pueden asignar una licencia independiente de exhibición de documentos electrónicos avanzada a los usuarios con una licencia de Office 365 E1 o E3. Los administradores y responsables del cumplimiento normativo que se asignan a los casos y utilizan eDiscovery avanzada para analizar datos no necesitan una licencia de E5.  
  
## <a name="before-you-begin"></a>Antes de empezar

- Tiene que ser un miembro del grupo de roles de administración de la organización (o tener asignado el rol de administración de funciones) para asignar permisos de exhibición de documentos electrónicos en la seguridad &amp; centro de cumplimiento.
    
- Puede usar el cmdlet [Add-RoleGroupMember](https://technet.microsoft.com/en-us/library/dd638207%28v=exchg.160%29.aspx) en seguridad &amp; PowerShell de centro de cumplimiento para agregar un grupo de seguridad habilitados para correo como un miembro de la subgrupo de jefes de exhibición de documentos electrónicos en el grupo de roles de administrador de exhibición de documentos electrónicos. Sin embargo, no se puede agregar un grupo de seguridad con correo habilitado para el subgrupo de los administradores de exhibición de documentos electrónicos. Vea la sección [obtener más información](#more-information) para obtener más detalles. 
    
## <a name="assign-ediscovery-permissions-in-the-security-amp-compliance-center"></a>Asignar permisos de exhibición de documentos electrónicos en la seguridad &amp; centro de cumplimiento

1. Vaya a [https://protection.office.com](https://protection.office.com).
    
2. Inicie sesión en Office 365 con su cuenta profesional o educativa.
    
3. En el panel izquierdo de la seguridad &amp; centro de cumplimiento, haga clic en **permisos**y, a continuación, haga clic en la casilla de verificación situada junto a la **exhibición de documentos electrónicos Manager**.
    
4. En la página emergente de **exhibición de documentos electrónicos Manager** , realice uno de los siguientes en función de la que desea asignar permisos de exhibición de documentos electrónicos. 
    
  - **Para que un usuario sea un administrador de exhibición de documentos electrónicos** Junto a la **exhibición de documentos electrónicos Manager**, haga clic en **Editar**. Bajo **Selected exhibición de documentos electrónicos los administradores**, haga clic en **Editar**y, a continuación, haga clic en ![icono Agregar](media/ITPro-EAC-AddIcon.gif) **Agregar**. Seleccione el usuario (o usuarios) que desea agregar como un administrador de exhibición de documentos electrónicos y, a continuación, haga clic en **Agregar**. Cuando haya terminado de agregar usuarios, haga clic en **Listo**. A continuación, en la página de **Edición elija eDiscovery Manager** emergente, haga clic en **Guardar** para guardar los cambios en la pertenencia a Administrador de exhibición de documentos electrónicos. 
    
  - **Para que un usuario sea un administrador de exhibición de documentos electrónicos** Junto a la **exhibición de documentos electrónicos administrador**, haga clic en **Editar**. Bajo **Selected exhibición de documentos electrónicos los administradores**, haga clic en **Editar**y, a continuación, haga clic en ![icono Agregar](media/ITPro-EAC-AddIcon.gif) **Agregar**. Seleccione el usuario (o usuarios) que desea agregar como un administrador de exhibición de documentos electrónicos y, a continuación, haga clic en **Agregar**. Cuando haya terminado de agregar usuarios, haga clic en **Listo**. A continuación, en la página de **Edición elija eDiscovery administrador** emergente, haga clic en **Guardar** para guardar los cambios en la pertenencia del Administrador de exhibición de documentos electrónicos. 
    
> [!NOTE]
> También puede usar el cmdlet **Add-eDiscoveryCaseAdmin** para que un usuario sea un administrador de exhibición de documentos electrónicos. Sin embargo, el usuario debe estar asignado el rol de administración de casos para poder usar este cmdlet para que sean un administrador de exhibición de documentos electrónicos. Para obtener más información, vea [Add-eDiscoveryCaseAdmin](https://go.microsoft.com/fwlink/p/?LinkID=798217). 
  
En la página de **permisos** en la seguridad &amp; centro de cumplimiento, también es posible asignar a los usuarios los permisos relacionados con la exhibición de documentos electrónicos, agregándolos a los grupos de roles de administrador de cumplimiento de normas, administración de la organización y revisor. Para obtener una descripción de las funciones RBAC relacionadas con la exhibición de documentos electrónicos asignadas a cada uno de estos grupos de roles, vea la sección [roles RBAC relacionadas con la exhibición de documentos electrónicos](#rbac-roles-related-to-ediscovery) . 

## <a name="rbac-roles-related-to-ediscovery"></a>Funciones de RBAC relacionadas con la exhibición de documentos electrónicos

En la siguiente tabla se enumera las funciones RBAC relacionadas con la exhibición de documentos electrónicos en el centro de cumplimiento de seguridad & e indica los grupos de funciones integradas que se asigna cada función a de forma predeterminada. 
    
|**Rol**|**Administrador de cumplimiento de normas**|**exhibición de documentos electrónicos administrador Manager &**|**Administración de organizaciones**|**Reviewer**|
|:-----|:-----:|:-----:|:-----:|:-----:|
|Administración de casos <br/> |![Marca de verificación](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> |![Marca de verificación](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> |![Marca de verificación](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> | <br/> |
|Búsqueda de cumplimiento <br/> |![Marca de verificación](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> |![Marca de verificación](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> |![Marca de verificación](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> | <br/> |
|Exportar <br/> | <br/> |![Marca de verificación](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> | <br/> | <br/> |
|Retención <br/>  |![Marca de verificación](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> |![Marca de verificación](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> |![Marca de verificación](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> | <br/> |
|Vista previa <br/>  | <br/> |![Marca de verificación](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> | <br/> | <br/> |
|Revisión <br/>  | <br/> |![Marca de verificación](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> | <br/> |![Marca de verificación](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> |
|Descifrar de RMS <br/>  ||![Marca de verificación](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> |||
|Búsqueda y depuración <br/> | <br/> | <br/> |![Marca de verificación](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/> | <br/> | 
||||
  
Las secciones siguientes describen cada uno de los roles RBAC relacionadas con la exhibición de documentos electrónicos enumerados en la tabla anterior.

### <a name="case-management"></a>Administración de casos

Esta función permite a los usuarios crear, editar, eliminar y controlar el acceso a los casos de exhibición de documentos electrónicos en el centro de cumplimiento de seguridad &. Para obtener más información, vea [administrar casos de exhibición de documentos electrónicos en la seguridad de Office 365 &amp; centro de cumplimiento](manage-ediscovery-cases.md). Como se explica anteriormente, un usuario debe tener asignado el rol de administración de casos para poder usar el cmdlet **Add-eDiscoveryCaseAdmin** para que sean un administrador de exhibición de documentos electrónicos. 

### <a name="compliance-search"></a>Búsqueda de cumplimiento

Esta función permite a los usuarios a ejecutar la herramienta de búsqueda de contenido en el centro de cumplimiento para buscar buzones de correo y las carpetas públicas, sitios de SharePoint Online, OneDrive para los sitios de negocio, Skype para las conversaciones de negocios, grupos de Office 365 y Microsoft Teams & de seguridad. Esta función permite que un usuario obtener una estimación de los resultados de búsqueda y crear informes de exportación, pero las funciones adicionales son necesarios para iniciar acciones de búsqueda de contenido como obtener una vista previa, exportar o eliminar los resultados de búsqueda.

Tenga en cuenta que los usuarios asignada la función de búsqueda de cumplimiento, pero no tienen el rol de la vista previa puede obtener la vista previa de los resultados de una búsqueda en la que se ha iniciado la acción de vista previa por un usuario que tiene asignado el rol de vista previa. El usuario sin la función de vista previa puede obtener una vista previa los resultados para hasta 2 semanas después de que se ha creado la acción de vista previa inicial.

De forma similar, los usuarios asignados a la función de búsqueda de cumplimiento, pero no tienen el rol puede descargar los resultados de una búsqueda en la que ha iniciado la acción de exportación por un usuario que ha asignado la función de exportación de exportación. El usuario sin la función de exportación puede descargar los resultados de una búsqueda de hasta 2 semanas después de que se ha creado la acción de exportación inicial. Después de que no podrá descargar los resultados a menos que alguien con la función de exportación reinicia la exportación.

Para obtener más información, consulte [Búsqueda de contenido en Office 365](content-search.md). 

### <a name="export"></a>Exportar

La función permite a los usuarios a exportar los resultados de una búsqueda de contenido a un equipo local. También les permite preparar los resultados de búsqueda para el análisis de exhibición de documentos electrónicos avanzada. 

Para obtener más información acerca de cómo exportar los resultados de búsqueda, consulte [Exportar resultados de búsqueda de la & centro de cumplimiento de seguridad de Office 365](export-search-results.md).

### <a name="hold"></a>Retención

Esta función permite a los usuarios a colocar el contenido en los buzones de correo, carpetas públicas, sitios, Skype para conversaciones de negocios, y los grupos de Office 365 en suspensión. Cuando el contenido se encuentra en suspensión, los propietarios de contenido aún podrá modificar o eliminar el contenido original, pero el contenido se conservarán hasta que se elimina la suspensión o hasta que expire la duración de la suspensión. 

Para obtener más información sobre suspensiones, consulte:

- [casos de exhibición de documentos electrónicos en el centro de cumplimiento de seguridad de Office 365 &](ediscovery-cases.md) 
- [Información general sobre las directivas de retención](retention-policies.md)

### <a name="preview"></a>Vista previa

Esta función permite a los usuarios ver una lista de los elementos que se han devuelto desde una búsqueda de contenido. También podrán abrir y ver cada elemento de la lista para ver su contenido.

### <a name="review"></a>Revisión

Esta función permite a los usuarios tener acceso a los datos de casos de exhibición de documentos electrónicos avanzada de Office 365. El propósito principal de este rol es proporcionar a los usuarios acceso a la exhibición de documentos electrónicos avanzada. Los usuarios que están asignados a esta función pueden ver y abrir la lista de los casos, en la página de exhibición de documentos electrónicos en el centro de cumplimiento que son miembros de & de seguridad. Después de que el usuario obtiene acceso a un caso en el centro de cumplimiento de seguridad &, pueden hacer clic en **conmutador de exhibición de documentos electrónicos avanzada** para tener acceso y analizar los datos de escenario de exhibición de documentos electrónicos avanzada. Esta función no permite al usuario obtener una vista previa de los resultados de una búsqueda de contenido que está asociado con el caso o llevar a cabo otros búsqueda de contenido o las tareas de administración de casos.

### <a name="rms-decrypt"></a>Descifrar de RMS

Esta función permite a los usuarios descifrar cifrado de RMS mensajes de correo electrónico cuando exportación de búsqueda los resultados o preparar los resultados de búsqueda para el análisis de exhibición de documentos electrónicos avanzada. Para obtener más información acerca de descifrar los resultados de búsqueda durante la exportación, consulte [Exportar resultados de búsqueda de la & centro de cumplimiento de seguridad de Office 365](export-search-results.md).

### <a name="search-and-purge"></a>Búsqueda y depuración

Esta función permite a los usuarios a realizar la desinstalación de forma masiva de datos que cumplan los criterios de una búsqueda de contenido. Para obtener más información, vea [Buscar y eliminar mensajes de correo electrónico en la organización de Office 365](search-for-and-delete-messages-in-your-organization.md). 


## <a name="more-information"></a>Más información

- **¿Por qué crear un administrador de exhibición de documentos electrónicos?** Como ya se explica, una exhibición de documentos electrónicos administrador es miembro del grupo de roles de administrador de exhibición de documentos electrónicos que puede ver y obtener acceso a todos los casos de exhibición de documentos electrónicos en su organización. Esta capacidad para tener acceso a todos los casos de exhibición de documentos electrónicos tiene dos propósitos importantes: 
    
  - Si una persona que es el único miembro de un caso de exhibición de documentos electrónicos abandona la organización, nadie (incluidos los miembros del grupo de roles de administración de la organización u otro miembro del grupo de roles de administrador de exhibición de documentos electrónicos) puede tener acceso a ese caso de exhibición de documentos electrónicos porque no son un miembro de un caso. En esta situación, no sería ninguna forma de obtener acceso a los datos en el caso. Pero debido a que un administrador de exhibición de documentos electrónicos puede obtener acceso a todos los casos de exhibición de documentos electrónicos en la organización, pueden ver el caso de la seguridad &amp; centro de cumplimiento y agregue a sí mismos u otro administrador de exhibición de documentos electrónicos como un miembro de las mayúsculas y minúsculas.
    
  - Debido a que un administrador de exhibición de documentos electrónicos puede ver y obtener acceso a todos los casos de exhibición de documentos electrónicos, pueden auditar y supervisar todos los casos y las búsquedas de cumplimiento de normas de asociados. Esto puede ayudar a impedir que cualquier uso incorrecto de las búsquedas de cumplimiento de normas o los casos de exhibición de documentos electrónicos. Y exhibición de documentos electrónicos los administradores puede tener acceso a información confidencial en los resultados de una búsqueda de cumplimiento, debe limitar el número de personas que son administradores de exhibición de documentos electrónicos.
    
    Además, exhibición de documentos electrónicos los administradores de la seguridad &amp; centro de cumplimiento se agregan automáticamente como administradores de exhibición de documentos electrónicos avanzada. Esto significa que una persona debe ser un administrador para realizar tareas administrativas en eDiscovery avanzada, como configuración de usuarios, creación de casos e importación de datos en un caso de exhibición de documentos electrónicos.
    
- **¿Puedo agregar un grupo como un miembro del grupo de roles de administrador de exhibición de documentos electrónicos en la seguridad &amp; centro de cumplimiento?** Como ya se explica, puede agregar un grupo de seguridad habilitados para correo como un miembro de la subgrupo de jefes de exhibición de documentos electrónicos en el grupo de roles de administrador de exhibición de documentos electrónicos mediante el cmdlet **Add-RoleGroupMember** en seguridad &amp; PowerShell de centro de cumplimiento. Por ejemplo, puede ejecutar el siguiente comando para agregar un grupo de seguridad habilitados para correo para el grupo de roles de administrador de exhibición de documentos electrónicos. 
    
  ```
  Add-RoleGroupMember "eDiscovery Manager" -Member <name of security group>
  ```

    Tenga en cuenta que no se admite un grupo de distribución de Exchange o un grupo de Office 365. Debe usar un grupo de seguridad habilitados para correo, que puede crear en Exchange Online PowerShell mediante el uso de la ` New-DistributionGroup -Type Security ` comando. También puede crear un grupo de seguridad habilitados para correo (y agregar miembros) en el centro de administración de Exchange o en el centro de administración de Office 365. Tenga en cuenta que puede tardar hasta 60 minutos después de que se crea para una nueva seguridad habilitados para correo para que estén disponibles para agregar al grupo de funciones de los administradores de exhibición de documentos electrónicos. 
    
    También como se mencionó anteriormente, no es posible hacer una seguridad habilitados para correo un administrador de exhibición de documentos electrónicos de grupo mediante el cmdlet **Add-eDiscoveryCaseAdmin** en seguridad &amp; PowerShell de centro de cumplimiento. Sólo se pueden agregar usuarios individuales como exhibición de documentos electrónicos los administradores. 
    
    Tenga en cuenta que también no se puede agregar un grupo de seguridad habilitados para correo como un miembro de un caso.
