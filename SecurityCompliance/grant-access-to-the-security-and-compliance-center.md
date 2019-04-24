---
title: Dar a los usuarios acceso al centro de &amp; seguridad y cumplimiento de Office 365
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: ''
ms.audience: Admin
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
description: Los usuarios deben tener asignados permisos en el centro de &amp; seguridad y cumplimiento de Office 365 para que puedan administrar cualquiera de sus características de seguridad o cumplimiento.
ms.openlocfilehash: 08b3781ceb48b9a8d5933a075106d7bd3b9ab17d
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32253978"
---
# <a name="give-users-access-to-the-office-365-security-amp-compliance-center"></a><span data-ttu-id="9127a-103">Dar a los usuarios acceso al centro de &amp; seguridad y cumplimiento de Office 365</span><span class="sxs-lookup"><span data-stu-id="9127a-103">Give users access to the Office 365 Security &amp; Compliance Center</span></span>

<span data-ttu-id="9127a-104">Los usuarios deben tener asignados permisos en el centro de &amp; seguridad y cumplimiento de Office 365 para que puedan administrar cualquiera de sus características de seguridad o cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="9127a-104">Users need to be assigned permissions in the Office 365 Security &amp; Compliance Center before they can manage any of its security or compliance features.</span></span> <span data-ttu-id="9127a-105">Como administrador global de Office 365 o miembro del grupo de funciones OrganizationManagement en el centro &amp; de seguridad y cumplimiento, puede conceder estos permisos a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="9127a-105">As an Office 365 global admin or member of the OrganizationManagement role group in the Security &amp; Compliance Center, you can give these permissions to users.</span></span> <span data-ttu-id="9127a-106">Los usuarios solo podrán administrar las características de seguridad o cumplimiento a las que les proporcione acceso.</span><span class="sxs-lookup"><span data-stu-id="9127a-106">Users will only be able to manage the security or compliance features that you give them access to.</span></span> 
  
<span data-ttu-id="9127a-107">Para obtener más información acerca de los distintos permisos que puede conceder a los &amp; usuarios en el centro de seguridad y cumplimiento, consulte [permisos &amp; en el centro de seguridad y cumplimiento de Office 365](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="9127a-107">For more information about the different permissions you can give to users in the Security &amp; Compliance Center, check out [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
  
## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="9127a-108">¿Qué necesita saber antes de comenzar?</span><span class="sxs-lookup"><span data-stu-id="9127a-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="9127a-109">Debe ser un administrador global de Office 365 o un miembro del grupo de funciones OrganizationManagement en el centro de seguridad &amp; y cumplimiento, para completar los pasos de este artículo.</span><span class="sxs-lookup"><span data-stu-id="9127a-109">You need to be an Office 365 global admin, or a member of the OrganizationManagement role group in the Security &amp; Compliance Center, to complete the steps in this article.</span></span>
    
- <span data-ttu-id="9127a-110">Los grupos de roles para &amp; el centro de seguridad y cumplimiento podrían tener nombres similares a los grupos de roles en Exchange Online, pero no son los mismos.</span><span class="sxs-lookup"><span data-stu-id="9127a-110">Role groups for the Security &amp; Compliance Center might have similar names to the role groups in Exchange Online, but they're not the same.</span></span> 
    
- <span data-ttu-id="9127a-111">Las pertenencias a grupos de roles no se comparten &amp; entre Exchange Online y el centro de seguridad y cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="9127a-111">Role group memberships aren't shared between Exchange Online and the Security &amp; Compliance Center.</span></span>
    
## <a name="use-the-office-365-admin-center-to-give-another-user-access-to-the-security-amp-compliance-center"></a><span data-ttu-id="9127a-112">Usar el centro de administración de Office 365 para conceder a otro usuario &amp; acceso al centro de seguridad y cumplimiento</span><span class="sxs-lookup"><span data-stu-id="9127a-112">Use the Office 365 admin center to give another user access to the Security &amp; Compliance Center</span></span>

1. <span data-ttu-id="9127a-113">[Inicie sesión en Office 365 y vaya al centro de administración](https://go.microsoft.com/fwlink/p/?LinkId=525275).</span><span class="sxs-lookup"><span data-stu-id="9127a-113">[Sign in to Office 365 and go to the Admin center](https://go.microsoft.com/fwlink/p/?LinkId=525275).</span></span>
    
2. <span data-ttu-id="9127a-114">En el centro de administración de Office 365, Abra **centros de administración** y, a continuación, haga clic en \*\*cumplimiento de seguridad &amp; \*\*.</span><span class="sxs-lookup"><span data-stu-id="9127a-114">In the Office 365 admin center, open **Admin centers** and then click **Security &amp; Compliance**.</span></span> 
    
3. <span data-ttu-id="9127a-115">En el centro &amp; de seguridad y cumplimiento, vaya a **permisos**.</span><span class="sxs-lookup"><span data-stu-id="9127a-115">In the Security &amp; Compliance Center, go to **Permissions**.</span></span>
    
4. <span data-ttu-id="9127a-116">En la lista, elija el grupo de roles al que desea agregar el usuario y haga clic en **Editar** ![icono](media/O365_MDM_CreatePolicy_EditIcon.gif)editar.</span><span class="sxs-lookup"><span data-stu-id="9127a-116">From the list, choose the role group that you want to add the user to and click **Edit** ![Edit icon](media/O365_MDM_CreatePolicy_EditIcon.gif).</span></span>
    
5. <span data-ttu-id="9127a-117">En la página de propiedades del grupo de roles, en **miembros**, haga](media/ITPro-EAC-AddIcon.gif) clic en **Agregar**![icono de agregar y seleccione el nombre del usuario (o usuarios) que desea agregar.</span><span class="sxs-lookup"><span data-stu-id="9127a-117">In the role group's properties page under **Members**, click **Add**![Add Icon](media/ITPro-EAC-AddIcon.gif) and select the name of the user (or users) you want to add.</span></span> 
    
6. <span data-ttu-id="9127a-118">Cuando haya seleccionado todos los usuarios que desee agregar al grupo de roles, haga clic en \*\*agregar\> \*\* y, a continuación, en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="9127a-118">When you've selected all of the users you want to add to the role group, click **add-\>** and then **OK**.</span></span>
    
7. <span data-ttu-id="9127a-119">Haga clic en **Guardar** para guardar los cambios realizados en el grupo de roles.</span><span class="sxs-lookup"><span data-stu-id="9127a-119">Click **Save** to save the changes to the role group.</span></span> 
    
### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="9127a-120">¿Cómo saber si el proceso se ha completado correctamente?</span><span class="sxs-lookup"><span data-stu-id="9127a-120">How do you know this worked?</span></span>

1. <span data-ttu-id="9127a-121">En el centro &amp; de seguridad y cumplimiento, vaya a **permisos**.</span><span class="sxs-lookup"><span data-stu-id="9127a-121">In the Security &amp; Compliance Center, go to **Permissions**.</span></span>
    
2. <span data-ttu-id="9127a-122">En la lista, seleccione el grupo de roles para ver los miembros.</span><span class="sxs-lookup"><span data-stu-id="9127a-122">From the list, select the role group to view the members.</span></span>
    
3. <span data-ttu-id="9127a-123">En la parte derecha, en los detalles del grupo de roles, puede ver los miembros del grupo de roles.</span><span class="sxs-lookup"><span data-stu-id="9127a-123">On the right, in the role group details, you can view the members of the role group.</span></span>
    
## <a name="use-powershell-to-give-another-user-access-to-the-security-amp-compliance-center"></a><span data-ttu-id="9127a-124">Usar PowerShell para proporcionar a otro usuario acceso al centro &amp; de seguridad y cumplimiento</span><span class="sxs-lookup"><span data-stu-id="9127a-124">Use PowerShell to give another user access to the Security &amp; Compliance Center</span></span>

1. <span data-ttu-id="9127a-125">[Conéctese a Office 365 Security _AMP_ Compliance Center PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).</span><span class="sxs-lookup"><span data-stu-id="9127a-125">[Connect to Office 365 Security & Compliance Center PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).</span></span>
    
2. <span data-ttu-id="9127a-126">Use el comando **Add-RoleGroupMember** para agregar un usuario al rol Administración de la organización, tal y como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="9127a-126">Use the **Add-RoleGroupMember** command to add a user to the Organization Management Role, as shown in the following example.</span></span> 
    
  ```
  Add-RoleGroupMember -Identity "OrganizationManagement" -Member MatildaS
  
  ```

 <span data-ttu-id="9127a-127">**Parámetros**</span><span class="sxs-lookup"><span data-stu-id="9127a-127">**Parameters**</span></span>
  
- <span data-ttu-id="9127a-128">_-Identity_ es el grupo de roles al que se agregará un miembro.</span><span class="sxs-lookup"><span data-stu-id="9127a-128">_-Identity_ is the role group to add a member to.</span></span> 
    
- <span data-ttu-id="9127a-129">_Member_ es el buzón, el grupo de seguridad universal (USG) o el equipo que se va a agregar al grupo de roles.</span><span class="sxs-lookup"><span data-stu-id="9127a-129">_Member_ is the mailbox, universal security group (USG), or computer to add to the role group.</span></span> <span data-ttu-id="9127a-130">Solo se puede especificar un miembro cada vez.</span><span class="sxs-lookup"><span data-stu-id="9127a-130">You can specify only one member at a time.</span></span> 
    
<span data-ttu-id="9127a-131">Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [Add-RoleGroupMember](https://go.microsoft.com/fwlink/p/?LinkId=510859).</span><span class="sxs-lookup"><span data-stu-id="9127a-131">For detailed information on syntax and parameters, see [Add-RoleGroupMember](https://go.microsoft.com/fwlink/p/?LinkId=510859).</span></span>
  
### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="9127a-132">¿Cómo saber si el proceso se ha completado correctamente?</span><span class="sxs-lookup"><span data-stu-id="9127a-132">How do you know this worked?</span></span>

<span data-ttu-id="9127a-133">Para comprobar que ha concedido a los usuarios acceso al &amp; centro de seguridad y cumplimiento, use el cmdlet **Get-RoleGroupMember** para ver los miembros del grupo de roles de administración de la organización, tal como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="9127a-133">To verify that you've given users access to the Security &amp; Compliance Center, use the **Get-RoleGroupMember** cmdlet to view the members in the Organization Management role group, as shown in the following example.</span></span> 
  
```
Get-RoleGroupMember -Identity "OrganizationManagement"

```

<span data-ttu-id="9127a-134">Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [Get-RoleGroupMember](https://go.microsoft.com/fwlink/p/?LinkId=510860).</span><span class="sxs-lookup"><span data-stu-id="9127a-134">For detailed information on syntax and parameters, see [Get-RoleGroupMember](https://go.microsoft.com/fwlink/p/?LinkId=510860).</span></span>
  

