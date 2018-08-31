---
title: Administrar permisos de grupos de roles de administración en EOP
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 12/9/2016
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: 125834f4-1024-4325-ad5a-d2573cfb005e
description: En Microsoft Exchange Online Protection, puede usar el Centro de administración de Exchange (EAC) para convertir a un usuario en miembro de un o varios grupos de roles para asignarle permisos para hacer ciertas tareas administrativas. También puede quitar a un usuario de uno o varios grupos de roles usando el EAC.
ms.openlocfilehash: b773b541b85288b4cb4deaa075cc0346d6bcc646
ms.sourcegitcommit: e9dca2d6a7838f98bb7eca127fdda2372cda402c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/21/2018
ms.locfileid: "23002979"
---
# <a name="manage-admin-role-group-permissions-in-eop"></a><span data-ttu-id="88b6f-104">Administrar permisos de grupos de roles de administración en EOP</span><span class="sxs-lookup"><span data-stu-id="88b6f-104">Manage admin role group permissions in EOP</span></span>
  
<span data-ttu-id="88b6f-p102">En Microsoft Exchange Online Protection, puede usar el Centro de administración de Exchange (EAC) para convertir a un usuario en miembro de un o varios grupos de roles para asignarle permisos para hacer ciertas tareas administrativas. También puede quitar a un usuario de uno o varios grupos de roles usando el EAC.</span><span class="sxs-lookup"><span data-stu-id="88b6f-p102">In Microsoft Exchange Online Protection (EOP), you can use the Exchange admin center (EAC) to make a user a member of a role group or groups in order to assign them permissions to perform specific administrative tasks. You can also remove a user from a role group or groups by using the EAC.</span></span>
  
## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="88b6f-107">¿Qué necesita saber antes de comenzar?</span><span class="sxs-lookup"><span data-stu-id="88b6f-107">What do you need to know before you begin?</span></span>

- <span data-ttu-id="88b6f-108">Tiempo estimado para finalizar: 5-10 minutos</span><span class="sxs-lookup"><span data-stu-id="88b6f-108">Estimated time to complete: 5-10 minutes</span></span>
    
- <span data-ttu-id="88b6f-p103">Deberá tener asignados permisos antes de poder llevar a cabo este procedimiento o procedimientos. Para ver qué permisos necesita, consulte el Entrada "Usuarios, contactos y grupos de roles" en el tema [Permisos de características en EOP](feature-permissions-in-eop.md).</span><span class="sxs-lookup"><span data-stu-id="88b6f-p103">You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Users, Contacts, and Role Groups" entry in the [Feature permissions in EOP](feature-permissions-in-eop.md) topic.</span></span> 
    
- <span data-ttu-id="88b6f-p104">Algunos permisos de Office 365 se asignan a permisos de grupos de roles de administración de EOP. Para más información, vea la columna "Rol en Exchange Online" de la sección "¿A qué servicios se extienden mis permisos de Office 365?" del artículo [Asignación de roles de administrador](https://go.microsoft.com/fwlink/p/?LinkId=286708).</span><span class="sxs-lookup"><span data-stu-id="88b6f-p104">Certain permissions in Office 365 map to EOP admin role group permissions. For more information, see the "Role in Exchange Online" column in the "Which services do my Office 365 permissions extend to?" section in [Assigning Admin Roles](https://go.microsoft.com/fwlink/p/?LinkId=286708).</span></span>
    
- <span data-ttu-id="88b6f-114">Para obtener información acerca de los métodos abreviados de teclado aplicables a los procedimientos de este tema, consulte **Métodos abreviados de teclado en el Centro de administración de Exchange**.</span><span class="sxs-lookup"><span data-stu-id="88b6f-114">For information about keyboard shortcuts that may apply to the procedures in this topic, see **Keyboard shortcuts in the Exchange admin center**.</span></span>
    
> [!TIP]
> <span data-ttu-id="88b6f-p105">¿Tiene algún problema? Solicite ayuda en los foros de Exchange. Visite los foros en [Exchange Server](https://go.microsoft.com/fwlink/p/?linkId=60612),[Exchange Online](https://go.microsoft.com/fwlink/p/?linkId=267542), o [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351).</span><span class="sxs-lookup"><span data-stu-id="88b6f-p105">Having problems? Ask for help in the Exchange forums. Visit the forums at [Exchange Server](https://go.microsoft.com/fwlink/p/?linkId=60612),[Exchange Online](https://go.microsoft.com/fwlink/p/?linkId=267542), or [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351).</span></span> 
  
## <a name="what-do-you-want-to-do"></a><span data-ttu-id="88b6f-118">¿Qué desea hacer?</span><span class="sxs-lookup"><span data-stu-id="88b6f-118">What do you want to do?</span></span>

### <a name="use-the-eac-to-assign-members-to-admin-role-groups"></a><span data-ttu-id="88b6f-119">Usar el EAC para agregar miembros a grupos de roles de administrador</span><span class="sxs-lookup"><span data-stu-id="88b6f-119">Use the EAC to assign members to admin role groups</span></span>

1. <span data-ttu-id="88b6f-120">En el EAC, vaya a **permisos** \> **Roles de administrador**, haga clic en el grupo de roles que desea agregar el usuario o a los usuarios y, a continuación, haga clic en **Editar** ![icono Editar](../media/ITPro-EAC-EditIcon.gif).</span><span class="sxs-lookup"><span data-stu-id="88b6f-120">In the EAC, navigate to **Permissions** \> **Admin Roles**, click the role group that you want to add the user or users to, and then click **Edit** ![Edit icon](../media/ITPro-EAC-EditIcon.gif).</span></span>
    
2. <span data-ttu-id="88b6f-p106">En Miembros, haga clic en **Agregar**![Agregar icono](../media/ITPro-EAC-AddIcon.gif). Aparecerá la ventana Seleccionar miembros.</span><span class="sxs-lookup"><span data-stu-id="88b6f-p106">Under Members, click **Add**![Add Icon](../media/ITPro-EAC-AddIcon.gif). The Select Members window will appear.</span></span>
    
3. <span data-ttu-id="88b6f-123">Busque el usuario o usuarios que quiere agregar, o selecciónelos en la lista.</span><span class="sxs-lookup"><span data-stu-id="88b6f-123">Search for the user or users that you wish to add, or select them from the list.</span></span>
    
4. <span data-ttu-id="88b6f-p107">Después de seleccionar a los usuarios, haga clic en **Agregar** y en **Aceptar**. Se cerrará la ventana Seleccionar miembros.</span><span class="sxs-lookup"><span data-stu-id="88b6f-p107">When you have selected the user or users that you want to add, click **Add**, and then click **OK**. The Select Members window will close.</span></span>
    
5. <span data-ttu-id="88b6f-p108">Verá que el usuario se agregó al panel **Miembros**. Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="88b6f-p108">You will see that the user has been added to the **Members** pane. Click **Save**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="88b6f-128">Puede que los usuarios tengan que cerrar la sesión e iniciarla de nuevo para ver los cambios en sus permisos administrativos después de agregar o quitar miembros de ese grupo de roles.</span><span class="sxs-lookup"><span data-stu-id="88b6f-128">Users may have to sign out and sign in again to see the change in their administrative rights after you add or remove members from the role group.</span></span> 
  
### <a name="use-the-eac-to-remove-members-from-admin-role-groups"></a><span data-ttu-id="88b6f-129">Usar el EAC para quitar miembros de grupos de roles de administrador</span><span class="sxs-lookup"><span data-stu-id="88b6f-129">Use the EAC to remove members from admin role groups</span></span>

1. <span data-ttu-id="88b6f-130">En el EAC, vaya a **permisos** \> **Roles de administrador**, haga clic en el grupo de roles que se desea quitar un usuario o usuarios de y, a continuación, haga clic en **Editar** ![icono Editar](../media/ITPro-EAC-EditIcon.gif).</span><span class="sxs-lookup"><span data-stu-id="88b6f-130">In the EAC, navigate to **Permissions** \> **Admin Roles**, click the role group that you want to remove a user or users from, and then click **Edit** ![Edit icon](../media/ITPro-EAC-EditIcon.gif).</span></span>
    
2. <span data-ttu-id="88b6f-131">En Miembros, seleccione el usuario o usuarios que quiere quitar y haga clic en **Quitar**![Icono de quitar](../media/ITPro-EAC-RemoveIcon.gif).</span><span class="sxs-lookup"><span data-stu-id="88b6f-131">Under Members, select the user or users that you want to remove and click **Remove**![Remove icon](../media/ITPro-EAC-RemoveIcon.gif).</span></span>
    
3. <span data-ttu-id="88b6f-p109">Haga clic en **Guardar** para guardar el cambio en el grupo de roles y volver a la página **Roles de administrador**. Para comprobar que quitó correctamente al usuario del grupo de roles de administrador, asegúrese de que el miembro ya no aparece en Miembros en el panel de detalles del grupo de roles seleccionado.</span><span class="sxs-lookup"><span data-stu-id="88b6f-p109">Click **Save** to save the change to the role group and return to the **Admin Roles** page. To verify that you've successfully removed the user from the administrator role group, make sure the member is no longer displayed under Members in the details pane for the selected role group.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="88b6f-134">Puede que los usuarios tengan que cerrar la sesión e iniciarla de nuevo para ver los cambios en sus permisos administrativos después de agregar o quitar miembros de ese grupo de roles.</span><span class="sxs-lookup"><span data-stu-id="88b6f-134">Users may have to sign out and sign in again to see the change in their administrative rights after you add or remove members from the role group.</span></span> 
  
## <a name="for-more-information"></a><span data-ttu-id="88b6f-135">Más información</span><span class="sxs-lookup"><span data-stu-id="88b6f-135">For more information</span></span>

[<span data-ttu-id="88b6f-136">Permisos de características en EOP</span><span class="sxs-lookup"><span data-stu-id="88b6f-136">Feature permissions in EOP</span></span>](feature-permissions-in-eop.md)
  

