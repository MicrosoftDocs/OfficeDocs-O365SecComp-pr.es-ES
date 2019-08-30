---
title: Administrar permisos de grupos de roles de administración en EOP
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 125834f4-1024-4325-ad5a-d2573cfb005e
description: Los administradores pueden obtener información sobre cómo asignar o quitar permisos en el centro de administración de Exchange (EAC) en Exchange Online Protection.
ms.openlocfilehash: 7bd1a6959dd03a118608dfe45faa253fd56539d4
ms.sourcegitcommit: 361aab46b1bb295ed2dcc1a417ac81f699b8ff78
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/30/2019
ms.locfileid: "36676730"
---
# <a name="manage-admin-role-group-permissions-in-eop"></a>Administrar permisos de grupos de roles de administración en EOP
  
En Microsoft Exchange Online Protection, puede usar el Centro de administración de Exchange (EAC) para convertir a un usuario en miembro de un o varios grupos de roles para asignarle permisos para hacer ciertas tareas administrativas. También puede quitar a un usuario de uno o varios grupos de roles usando el EAC.
  
## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de comenzar?

- Tiempo estimado para finalizar: 5-10 minutos

- Para abrir el centro de administración de Exchange, vea [centro de administración de Exchange en Exchange Online Protection](../exchange-admin-center-in-exchange-online-protection-eop.md).

- Deberá tener asignados permisos antes de poder llevar a cabo este procedimiento o procedimientos. Para ver qué permisos necesita, consulte el Entrada "Usuarios, contactos y grupos de roles" en el tema [Permisos de características en EOP](feature-permissions-in-eop.md).

- Para obtener información acerca de los métodos abreviados de teclado que se pueden aplicar a los procedimientos de este tema, consulte [métodos abreviados de teclado para el centro de administración de Exchange en Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).

> [!TIP]
> ¿Problemas? Solicite ayuda en el foro de [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) .
  
## <a name="use-the-eac-to-assign-members-to-admin-role-groups"></a>Usar el EAC para agregar miembros a grupos de roles de administrador

1. En el EAC, vaya a **** \> **roles de administrador**de permisos, haga clic en el grupo de roles al que desea agregar el usuario o usuarios y, a continuación](../media/ITPro-EAC-EditIcon.gif), haga clic en **Editar** ![icono de edición.

2. En miembros, haga **** ![clic en agregar](../media/ITPro-EAC-AddIcon.gif)icono de agregar. Aparecerá la ventana Seleccionar miembros.

3. Busque el usuario o usuarios que quiere agregar, o selecciónelos en la lista.

4. Después de seleccionar a los usuarios, haga clic en **Agregar** y en **Aceptar**. Se cerrará la ventana Seleccionar miembros.

5. Verá que el usuario se agregó al panel **Miembros**. Haga clic en **Guardar**.

   > [!NOTE]
   > Puede que los usuarios tengan que cerrar la sesión e iniciarla de nuevo para ver los cambios en sus permisos administrativos después de agregar o quitar miembros de ese grupo de roles. 
  
## <a name="use-the-eac-to-remove-members-from-admin-role-groups"></a>Usar el EAC para quitar miembros de grupos de roles de administrador

1. En el EAC, vaya a **** \> **roles de administrador**de permisos, haga clic en el grupo de roles del que desea quitar un usuario o usuarios y, a continuación](../media/ITPro-EAC-EditIcon.gif), haga clic en **Editar** ![icono de edición.

2. En miembros, seleccione el usuario o usuarios que desea quitar y haga clic en **quitar** ![icono](../media/ITPro-EAC-RemoveIcon.gif)quitar.

3. Haga clic en **Guardar** para guardar el cambio en el grupo de roles y volver a la página **Roles de administrador**. Para comprobar que quitó correctamente al usuario del grupo de roles de administrador, asegúrese de que el miembro ya no aparece en Miembros en el panel de detalles del grupo de roles seleccionado.

   > [!NOTE]
   > Puede que los usuarios tengan que cerrar la sesión e iniciarla de nuevo para ver los cambios en sus permisos administrativos después de agregar o quitar miembros de ese grupo de roles.
  
## <a name="for-more-information"></a>Más información

[Permisos de características en EOP](feature-permissions-in-eop.md)
