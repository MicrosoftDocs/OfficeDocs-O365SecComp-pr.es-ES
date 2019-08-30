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
# <a name="manage-admin-role-group-permissions-in-eop"></a><span data-ttu-id="412b5-103">Administrar permisos de grupos de roles de administración en EOP</span><span class="sxs-lookup"><span data-stu-id="412b5-103">Manage admin role group permissions in EOP</span></span>
  
<span data-ttu-id="412b5-p101">En Microsoft Exchange Online Protection, puede usar el Centro de administración de Exchange (EAC) para convertir a un usuario en miembro de un o varios grupos de roles para asignarle permisos para hacer ciertas tareas administrativas. También puede quitar a un usuario de uno o varios grupos de roles usando el EAC.</span><span class="sxs-lookup"><span data-stu-id="412b5-p101">In Microsoft Exchange Online Protection (EOP), you can use the Exchange admin center (EAC) to make a user a member of a role group or groups in order to assign them permissions to perform specific administrative tasks. You can also remove a user from a role group or groups by using the EAC.</span></span>
  
## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="412b5-106">¿Qué necesita saber antes de comenzar?</span><span class="sxs-lookup"><span data-stu-id="412b5-106">What do you need to know before you begin?</span></span>

- <span data-ttu-id="412b5-107">Tiempo estimado para finalizar: 5-10 minutos</span><span class="sxs-lookup"><span data-stu-id="412b5-107">Estimated time to complete: 5-10 minutes</span></span>

- <span data-ttu-id="412b5-108">Para abrir el centro de administración de Exchange, vea [centro de administración de Exchange en Exchange Online Protection](../exchange-admin-center-in-exchange-online-protection-eop.md).</span><span class="sxs-lookup"><span data-stu-id="412b5-108">To open the Exchange admin center, see [Exchange admin center in Exchange Online Protection](../exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="412b5-p102">Deberá tener asignados permisos antes de poder llevar a cabo este procedimiento o procedimientos. Para ver qué permisos necesita, consulte el Entrada "Usuarios, contactos y grupos de roles" en el tema [Permisos de características en EOP](feature-permissions-in-eop.md).</span><span class="sxs-lookup"><span data-stu-id="412b5-p102">You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Users, Contacts, and Role Groups" entry in the [Feature permissions in EOP](feature-permissions-in-eop.md) topic.</span></span>

- <span data-ttu-id="412b5-111">Para obtener información acerca de los métodos abreviados de teclado que se pueden aplicar a los procedimientos de este tema, consulte [métodos abreviados de teclado para el centro de administración de Exchange en Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span><span class="sxs-lookup"><span data-stu-id="412b5-111">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="412b5-112">¿Problemas?</span><span class="sxs-lookup"><span data-stu-id="412b5-112">Having problems?</span></span> <span data-ttu-id="412b5-113">Solicite ayuda en el foro de [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) .</span><span class="sxs-lookup"><span data-stu-id="412b5-113">Ask for help in the [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) forum.</span></span>
  
## <a name="use-the-eac-to-assign-members-to-admin-role-groups"></a><span data-ttu-id="412b5-114">Usar el EAC para agregar miembros a grupos de roles de administrador</span><span class="sxs-lookup"><span data-stu-id="412b5-114">Use the EAC to assign members to admin role groups</span></span>

1. <span data-ttu-id="412b5-115">En el EAC, vaya a \*\*\*\* \> **roles de administrador**de permisos, haga clic en el grupo de roles al que desea agregar el usuario o usuarios y, a continuación](../media/ITPro-EAC-EditIcon.gif), haga clic en **Editar** ![icono de edición.</span><span class="sxs-lookup"><span data-stu-id="412b5-115">In the EAC, go to **Permissions** \> **Admin roles**, click the role group that you want to add the user or users to, and then click **Edit** ![Edit icon](../media/ITPro-EAC-EditIcon.gif).</span></span>

2. <span data-ttu-id="412b5-116">En miembros, haga \*\*\*\* ![clic en agregar](../media/ITPro-EAC-AddIcon.gif)icono de agregar.</span><span class="sxs-lookup"><span data-stu-id="412b5-116">Under Members, click **Add** ![Add Icon](../media/ITPro-EAC-AddIcon.gif).</span></span> <span data-ttu-id="412b5-117">Aparecerá la ventana Seleccionar miembros.</span><span class="sxs-lookup"><span data-stu-id="412b5-117">The Select Members window will appear.</span></span>

3. <span data-ttu-id="412b5-118">Busque el usuario o usuarios que quiere agregar, o selecciónelos en la lista.</span><span class="sxs-lookup"><span data-stu-id="412b5-118">Search for the user or users that you wish to add, or select them from the list.</span></span>

4. <span data-ttu-id="412b5-p105">Después de seleccionar a los usuarios, haga clic en **Agregar** y en **Aceptar**. Se cerrará la ventana Seleccionar miembros.</span><span class="sxs-lookup"><span data-stu-id="412b5-p105">When you have selected the user or users that you want to add, click **Add**, and then click **OK**. The Select Members window will close.</span></span>

5. <span data-ttu-id="412b5-p106">Verá que el usuario se agregó al panel **Miembros**. Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="412b5-p106">You will see that the user has been added to the **Members** pane. Click **Save**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="412b5-123">Puede que los usuarios tengan que cerrar la sesión e iniciarla de nuevo para ver los cambios en sus permisos administrativos después de agregar o quitar miembros de ese grupo de roles.</span><span class="sxs-lookup"><span data-stu-id="412b5-123">Users may have to sign out and sign in again to see the change in their administrative rights after you add or remove members from the role group.</span></span> 
  
## <a name="use-the-eac-to-remove-members-from-admin-role-groups"></a><span data-ttu-id="412b5-124">Usar el EAC para quitar miembros de grupos de roles de administrador</span><span class="sxs-lookup"><span data-stu-id="412b5-124">Use the EAC to remove members from admin role groups</span></span>

1. <span data-ttu-id="412b5-125">En el EAC, vaya a \*\*\*\* \> **roles de administrador**de permisos, haga clic en el grupo de roles del que desea quitar un usuario o usuarios y, a continuación](../media/ITPro-EAC-EditIcon.gif), haga clic en **Editar** ![icono de edición.</span><span class="sxs-lookup"><span data-stu-id="412b5-125">In the EAC, go to **Permissions** \> **Admin Roles**, click the role group that you want to remove a user or users from, and then click **Edit** ![Edit icon](../media/ITPro-EAC-EditIcon.gif).</span></span>

2. <span data-ttu-id="412b5-126">En miembros, seleccione el usuario o usuarios que desea quitar y haga clic en **quitar** ![icono](../media/ITPro-EAC-RemoveIcon.gif)quitar.</span><span class="sxs-lookup"><span data-stu-id="412b5-126">Under Members, select the user or users that you want to remove and click **Remove** ![Remove icon](../media/ITPro-EAC-RemoveIcon.gif).</span></span>

3. <span data-ttu-id="412b5-p107">Haga clic en **Guardar** para guardar el cambio en el grupo de roles y volver a la página **Roles de administrador**. Para comprobar que quitó correctamente al usuario del grupo de roles de administrador, asegúrese de que el miembro ya no aparece en Miembros en el panel de detalles del grupo de roles seleccionado.</span><span class="sxs-lookup"><span data-stu-id="412b5-p107">Click **Save** to save the change to the role group and return to the **Admin Roles** page. To verify that you've successfully removed the user from the administrator role group, make sure the member is no longer displayed under Members in the details pane for the selected role group.</span></span>

   > [!NOTE]
   > <span data-ttu-id="412b5-129">Puede que los usuarios tengan que cerrar la sesión e iniciarla de nuevo para ver los cambios en sus permisos administrativos después de agregar o quitar miembros de ese grupo de roles.</span><span class="sxs-lookup"><span data-stu-id="412b5-129">Users may have to sign out and sign in again to see the change in their administrative rights after you add or remove members from the role group.</span></span>
  
## <a name="for-more-information"></a><span data-ttu-id="412b5-130">Más información</span><span class="sxs-lookup"><span data-stu-id="412b5-130">For more information</span></span>

[<span data-ttu-id="412b5-131">Permisos de características en EOP</span><span class="sxs-lookup"><span data-stu-id="412b5-131">Feature permissions in EOP</span></span>](feature-permissions-in-eop.md)
