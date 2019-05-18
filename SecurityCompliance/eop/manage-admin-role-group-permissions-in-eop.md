---
title: Administrar permisos de grupos de roles de administración en EOP
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 12/9/2016
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 125834f4-1024-4325-ad5a-d2573cfb005e
description: En Microsoft Exchange Online Protection, puede usar el Centro de administración de Exchange (EAC) para convertir a un usuario en miembro de un o varios grupos de roles para asignarle permisos para hacer ciertas tareas administrativas. También puede quitar a un usuario de uno o varios grupos de roles usando el EAC.
ms.openlocfilehash: 35f248bce26d28c8ab7465ff983629eb01db407b
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/17/2019
ms.locfileid: "34150162"
---
# <a name="manage-admin-role-group-permissions-in-eop"></a>Administrar permisos de grupos de roles de administración en EOP
  
En Microsoft Exchange Online Protection, puede usar el Centro de administración de Exchange (EAC) para convertir a un usuario en miembro de un o varios grupos de roles para asignarle permisos para hacer ciertas tareas administrativas. También puede quitar a un usuario de uno o varios grupos de roles usando el EAC.
  
## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de comenzar?

- Tiempo estimado para finalizar: 5-10 minutos
    
- Deberá tener asignados permisos antes de poder llevar a cabo este procedimiento o procedimientos. Para ver qué permisos necesita, consulte el Entrada "Usuarios, contactos y grupos de roles" en el tema [Permisos de características en EOP](feature-permissions-in-eop.md). 
    
- Algunos permisos de Office 365 se asignan a permisos de grupos de roles de administración de EOP. Para más información, vea la columna "Rol en Exchange Online" de la sección "¿A qué servicios se extienden mis permisos de Office 365?" del artículo [Asignación de roles de administrador](https://go.microsoft.com/fwlink/p/?LinkId=286708).
    
- Para obtener información acerca de los métodos abreviados de teclado aplicables a los procedimientos de este tema, consulte **Keyboard shortcuts in Exchange 2013**.
    
> [!TIP]
> ¿Tiene algún problema? Solicite ayuda en los foros de Exchange. Visite los foros en [Exchange Server](https://go.microsoft.com/fwlink/p/?linkId=60612),[Exchange Online](https://go.microsoft.com/fwlink/p/?linkId=267542), o [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351). 
  
## <a name="what-do-you-want-to-do"></a>¿Qué quiere hacer?

### <a name="use-the-eac-to-assign-members-to-admin-role-groups"></a>Usar el EAC para agregar miembros a grupos de roles de administrador

1. En el EAC, vaya a **** \> **roles de administrador**de permisos, haga clic en el grupo de roles al que desea agregar el usuario o usuarios y, a continuación](../media/ITPro-EAC-EditIcon.gif), haga clic en **Editar** ![icono de edición.
    
2. En Miembros, haga clic en **Agregar**![Agregar icono](../media/ITPro-EAC-AddIcon.gif). Aparecerá la ventana Seleccionar miembros.
    
3. Busque el usuario o usuarios que quiere agregar, o selecciónelos en la lista.
    
4. Después de seleccionar a los usuarios, haga clic en **Agregar** y en **Aceptar**. Se cerrará la ventana Seleccionar miembros.
    
5. Verá que el usuario se agregó al panel **Miembros**. Haga clic en **Guardar**.
    
    > [!NOTE]
    > Puede que los usuarios tengan que cerrar la sesión e iniciarla de nuevo para ver los cambios en sus permisos administrativos después de agregar o quitar miembros de ese grupo de roles. 
  
### <a name="use-the-eac-to-remove-members-from-admin-role-groups"></a>Usar el EAC para quitar miembros de grupos de roles de administrador

1. En el EAC, vaya a **** \> **roles de administrador**de permisos, haga clic en el grupo de roles del que desea quitar un usuario o usuarios y, a continuación](../media/ITPro-EAC-EditIcon.gif), haga clic en **Editar** ![icono de edición.
    
2. En Miembros, seleccione el usuario o usuarios que quiere quitar y haga clic en **Quitar**![Icono de quitar](../media/ITPro-EAC-RemoveIcon.gif).
    
3. Haga clic en **Guardar** para guardar el cambio en el grupo de roles y volver a la página **Roles de administrador**. Para comprobar que quitó correctamente al usuario del grupo de roles de administrador, asegúrese de que el miembro ya no aparece en Miembros en el panel de detalles del grupo de roles seleccionado. 
    
    > [!NOTE]
    > Puede que los usuarios tengan que cerrar la sesión e iniciarla de nuevo para ver los cambios en sus permisos administrativos después de agregar o quitar miembros de ese grupo de roles. 
  
## <a name="for-more-information"></a>Más información

[Permisos de características en EOP](feature-permissions-in-eop.md)
  

