---
title: Proporcionar a los usuarios acceso al Centro de seguridad y cumplimiento de Office 365
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.PermissionsHelp
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 2cfce2c8-20c5-47f9-afc4-24b059c1bd76
description: Los usuarios deben tener asignados permisos en el centro de seguridad & cumplimiento de Office 365 para poder administrar cualquiera de sus características de seguridad o cumplimiento.
ms.openlocfilehash: 7963a8c3db64e83566960abe9298b9a2d636ae53
ms.sourcegitcommit: 6302a43d947a908dd10a8e40550b806f491692fc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/13/2019
ms.locfileid: "35645125"
---
# <a name="give-users-access-to-the-office-365-security--compliance-center"></a><span data-ttu-id="78a41-103">Proporcionar a los usuarios acceso al Centro de seguridad y cumplimiento de Office 365</span><span class="sxs-lookup"><span data-stu-id="78a41-103">Give users access to the Office 365 Security & Compliance Center</span></span>

<span data-ttu-id="78a41-104">Los usuarios deben tener asignados permisos en el centro de seguridad & cumplimiento de Office 365 para poder administrar cualquiera de sus características de seguridad o cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="78a41-104">Users need to be assigned permissions in the Office 365 Security & Compliance Center before they can manage any of its security or compliance features.</span></span> <span data-ttu-id="78a41-105">Como administrador global de Office 365 o miembro del grupo de funciones OrganizationManagement en el centro de seguridad & cumplimiento, puede conceder estos permisos a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="78a41-105">As an Office 365 global admin or member of the OrganizationManagement role group in the Security & Compliance Center, you can give these permissions to users.</span></span> <span data-ttu-id="78a41-106">Los usuarios solo podrán administrar las características de seguridad o cumplimiento a las que les proporcione acceso.</span><span class="sxs-lookup"><span data-stu-id="78a41-106">Users will only be able to manage the security or compliance features that you give them access to.</span></span> 
  
<span data-ttu-id="78a41-107">Para obtener más información acerca de los distintos permisos que puede conceder a los usuarios en el centro de seguridad & cumplimiento, consulte Permissions [in the Office 365 security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="78a41-107">For more information about the different permissions you can give to users in the Security & Compliance Center, check out [Permissions in the Office 365 Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
  
## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="78a41-108">¿Qué necesita saber antes de comenzar?</span><span class="sxs-lookup"><span data-stu-id="78a41-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="78a41-109">Debe ser administrador global de Office 365 o miembro del grupo de funciones OrganizationManagement en el centro de seguridad & cumplimiento para completar los pasos descritos en este artículo.</span><span class="sxs-lookup"><span data-stu-id="78a41-109">You need to be an Office 365 global admin, or a member of the OrganizationManagement role group in the Security & Compliance Center, to complete the steps in this article.</span></span>

- <span data-ttu-id="78a41-110">Los grupos de roles para el centro de seguridad & cumplimiento pueden tener nombres similares a los grupos de roles en Exchange Online, pero no son los mismos.</span><span class="sxs-lookup"><span data-stu-id="78a41-110">Role groups for the Security & Compliance Center might have similar names to the role groups in Exchange Online, but they're not the same.</span></span>

- <span data-ttu-id="78a41-111">Las pertenencias a grupos de roles no se comparten entre Exchange Online y el centro de seguridad & cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="78a41-111">Role group memberships aren't shared between Exchange Online and the Security & Compliance Center.</span></span>

- <span data-ttu-id="78a41-112">Los permisos de acceso delegado (DAP) asociados con administrar en nombre de (AOBO) no pueden obtener acceso al centro de seguridad & cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="78a41-112">Delegated Access Permission (DAP) partners with Administer On Behalf Of (AOBO) permissions can't access the Security & Compliance Center.</span></span>

## <a name="use-the-office-365-admin-center-to-give-another-user-access-to-the-security--compliance-center"></a><span data-ttu-id="78a41-113">Usar el centro de administración de Office 365 para conceder a otro usuario acceso al centro de seguridad & cumplimiento</span><span class="sxs-lookup"><span data-stu-id="78a41-113">Use the Office 365 admin center to give another user access to the Security & Compliance Center</span></span>

1. <span data-ttu-id="78a41-114">[Inicie sesión en Office 365 y vaya al centro de administración](https://go.microsoft.com/fwlink/p/?LinkId=525275).</span><span class="sxs-lookup"><span data-stu-id="78a41-114">[Sign in to Office 365 and go to the Admin center](https://go.microsoft.com/fwlink/p/?LinkId=525275).</span></span>

2. <span data-ttu-id="78a41-115">En el centro de administración de Office 365, Abra **centros de administración** y, a continuación, haga clic en **seguridad & cumplimiento**.</span><span class="sxs-lookup"><span data-stu-id="78a41-115">In the Office 365 admin center, open **Admin centers** and then click **Security & Compliance**.</span></span>

3. <span data-ttu-id="78a41-116">En el centro de seguridad & cumplimiento, vaya a **permisos**.</span><span class="sxs-lookup"><span data-stu-id="78a41-116">In the Security & Compliance Center, go to **Permissions**.</span></span>

4. <span data-ttu-id="78a41-117">En la lista, elija el grupo de roles al que desea agregar el usuario y haga clic en **Editar** ![icono](media/O365-MDM-CreatePolicy-EditIcon.gif)editar.</span><span class="sxs-lookup"><span data-stu-id="78a41-117">From the list, choose the role group that you want to add the user to and click **Edit** ![Edit icon](media/O365-MDM-CreatePolicy-EditIcon.gif).</span></span>

5. <span data-ttu-id="78a41-118">En la página de propiedades del grupo de roles, en **miembros**, haga](media/ITPro-EAC-AddIcon.gif) clic en **Agregar**![icono de agregar y seleccione el nombre del usuario (o usuarios) que desea agregar.</span><span class="sxs-lookup"><span data-stu-id="78a41-118">In the role group's properties page under **Members**, click **Add**![Add Icon](media/ITPro-EAC-AddIcon.gif) and select the name of the user (or users) you want to add.</span></span>

6. <span data-ttu-id="78a41-119">Cuando haya seleccionado todos los usuarios que desee agregar al grupo de roles, haga clic en \*\*agregar\> \*\* y, a continuación, en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="78a41-119">When you've selected all of the users you want to add to the role group, click **add-\>** and then **OK**.</span></span>

7. <span data-ttu-id="78a41-120">Haga clic en **Guardar** para guardar los cambios realizados en el grupo de roles.</span><span class="sxs-lookup"><span data-stu-id="78a41-120">Click **Save** to save the changes to the role group.</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="78a41-121">¿Cómo saber si el proceso se ha completado correctamente?</span><span class="sxs-lookup"><span data-stu-id="78a41-121">How do you know this worked?</span></span>

1. <span data-ttu-id="78a41-122">En el centro de seguridad & cumplimiento, vaya a **permisos**.</span><span class="sxs-lookup"><span data-stu-id="78a41-122">In the Security & Compliance Center, go to **Permissions**.</span></span>

2. <span data-ttu-id="78a41-123">En la lista, seleccione el grupo de roles para ver los miembros.</span><span class="sxs-lookup"><span data-stu-id="78a41-123">From the list, select the role group to view the members.</span></span>

3. <span data-ttu-id="78a41-124">En la parte derecha, en los detalles del grupo de roles, puede ver los miembros del grupo de roles.</span><span class="sxs-lookup"><span data-stu-id="78a41-124">On the right, in the role group details, you can view the members of the role group.</span></span>

## <a name="use-powershell-to-give-another-user-access-to-the-security--compliance-center"></a><span data-ttu-id="78a41-125">Usar PowerShell para proporcionar a otro usuario acceso al centro de seguridad & cumplimiento</span><span class="sxs-lookup"><span data-stu-id="78a41-125">Use PowerShell to give another user access to the Security & Compliance Center</span></span>

1. <span data-ttu-id="78a41-126">[Conéctese a Office 365 Security & el centro de cumplimiento de PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).</span><span class="sxs-lookup"><span data-stu-id="78a41-126">[Connect to Office 365 Security & Compliance Center PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).</span></span>

2. <span data-ttu-id="78a41-127">Use el comando **Add-RoleGroupMember** para agregar un usuario al rol Administración de la organización, tal y como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="78a41-127">Use the **Add-RoleGroupMember** command to add a user to the Organization Management Role, as shown in the following example.</span></span>

   ```
   Add-RoleGroupMember -Identity "Organization Management" -Member MatildaS
   ```

   <span data-ttu-id="78a41-128">**Parámetros**:</span><span class="sxs-lookup"><span data-stu-id="78a41-128">**Parameters**:</span></span>
  
   - <span data-ttu-id="78a41-129">_Identity_ es el grupo de roles al que se agrega un miembro.</span><span class="sxs-lookup"><span data-stu-id="78a41-129">_Identity_ is the role group to add a member to.</span></span>

   - <span data-ttu-id="78a41-130">_Member_ es el buzón, el grupo de seguridad universal (USG) o el equipo que se va a agregar al grupo de roles.</span><span class="sxs-lookup"><span data-stu-id="78a41-130">_Member_ is the mailbox, universal security group (USG), or computer to add to the role group.</span></span> <span data-ttu-id="78a41-131">Solo se puede especificar un miembro cada vez.</span><span class="sxs-lookup"><span data-stu-id="78a41-131">You can specify only one member at a time.</span></span>

<span data-ttu-id="78a41-132">Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [Add-RoleGroupMember](https://go.microsoft.com/fwlink/p/?LinkId=510859).</span><span class="sxs-lookup"><span data-stu-id="78a41-132">For detailed information on syntax and parameters, see [Add-RoleGroupMember](https://go.microsoft.com/fwlink/p/?LinkId=510859).</span></span>
  
### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="78a41-133">¿Cómo saber si el proceso se ha completado correctamente?</span><span class="sxs-lookup"><span data-stu-id="78a41-133">How do you know this worked?</span></span>

<span data-ttu-id="78a41-134">Para comprobar que ha concedido a los usuarios acceso al centro de seguridad & cumplimiento, use el cmdlet **Get-RoleGroupMember** para ver los miembros del grupo de funciones de administración de la organización, tal como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="78a41-134">To verify that you've given users access to the Security & Compliance Center, use the **Get-RoleGroupMember** cmdlet to view the members in the Organization Management role group, as shown in the following example.</span></span>
  
```
Get-RoleGroupMember -Identity "Organization Management"
```

<span data-ttu-id="78a41-135">Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [Get-RoleGroupMember](https://go.microsoft.com/fwlink/p/?LinkId=510860).</span><span class="sxs-lookup"><span data-stu-id="78a41-135">For detailed information on syntax and parameters, see [Get-RoleGroupMember](https://go.microsoft.com/fwlink/p/?LinkId=510860).</span></span>
