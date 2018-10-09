---
title: Conceder a los usuarios acceso a la seguridad de Office 365 &amp; centro de cumplimiento
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/18/2017
ms.audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.PermissionsHelp
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 2cfce2c8-20c5-47f9-afc4-24b059c1bd76
description: Los usuarios necesitan tener asignados los permisos en la seguridad de Office 365 &amp; centro de cumplimiento de normas antes de que puedan administrar cualquiera de sus características de cumplimiento de normas o de seguridad.
ms.openlocfilehash: e0c8b655b1b3300e4ffa9aba1d94e65a9ef26121
ms.sourcegitcommit: 2e41cc24ad92005084f2ba432e724bdcc4e295ff
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/09/2018
ms.locfileid: "25450745"
---
# <a name="give-users-access-to-the-office-365-security-amp-compliance-center"></a><span data-ttu-id="9e5fd-103">Conceder a los usuarios acceso a la seguridad de Office 365 &amp; centro de cumplimiento</span><span class="sxs-lookup"><span data-stu-id="9e5fd-103">Give users access to the Office 365 Security &amp; Compliance Center</span></span>

<span data-ttu-id="9e5fd-p101">Los usuarios necesitan tener asignados los permisos en la seguridad de Office 365 &amp; centro de cumplimiento de normas antes de que puedan administrar cualquiera de sus características de cumplimiento de normas o de seguridad. Como administrador global de Office 365 o miembro del grupo de roles en la seguridad OrganizationManagement &amp; centro de cumplimiento, puede dar estos permisos a los usuarios. Los usuarios sólo podrán administrar las características de cumplimiento de normas o de seguridad que conceda acceso a.</span><span class="sxs-lookup"><span data-stu-id="9e5fd-p101">Users need to be assigned permissions in the Office 365 Security &amp; Compliance Center before they can manage any of its security or compliance features. As an Office 365 global admin or member of the OrganizationManagement role group in the Security &amp; Compliance Center, you can give these permissions to users. Users will only be able to manage the security or compliance features that you give them access to.</span></span> 
  
<span data-ttu-id="9e5fd-107">Para obtener más información acerca de los diferentes permisos puede otorgar a los usuarios de la seguridad &amp; centro de cumplimiento, desprotección [permisos en la seguridad de Office 365 &amp; centro de cumplimiento](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="9e5fd-107">For more information about the different permissions you can give to users in the Security &amp; Compliance Center, check out [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
  
## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="9e5fd-108">¿Qué necesita saber antes de comenzar?</span><span class="sxs-lookup"><span data-stu-id="9e5fd-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="9e5fd-109">Debe ser un administrador global de Office 365, o un miembro del grupo de roles en la seguridad OrganizationManagement &amp; centro de cumplimiento, para llevar a cabo los pasos descritos en este artículo.</span><span class="sxs-lookup"><span data-stu-id="9e5fd-109">You need to be an Office 365 global admin, or a member of the OrganizationManagement role group in the Security &amp; Compliance Center, to complete the steps in this article.</span></span>
    
- <span data-ttu-id="9e5fd-110">Grupos de roles para la seguridad &amp; centro de cumplimiento pueden tener nombres similares a los grupos de funciones en Exchange Online, pero no son los mismos.</span><span class="sxs-lookup"><span data-stu-id="9e5fd-110">Role groups for the Security &amp; Compliance Center might have similar names to the role groups in Exchange Online, but they're not the same.</span></span> 
    
- <span data-ttu-id="9e5fd-111">Las pertenencias a grupo de funciones no se comparten entre Exchange Online y la seguridad &amp; centro de cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="9e5fd-111">Role group memberships aren't shared between Exchange Online and the Security &amp; Compliance Center.</span></span>
    
## <a name="use-the-office-365-admin-center-to-give-another-user-access-to-the-security-amp-compliance-center"></a><span data-ttu-id="9e5fd-112">Use el centro de administración de Office 365 para ceder el otro usuario tenga acceso a la seguridad &amp; centro de cumplimiento</span><span class="sxs-lookup"><span data-stu-id="9e5fd-112">Use the Office 365 admin center to give another user access to the Security &amp; Compliance Center</span></span>

1. <span data-ttu-id="9e5fd-113">[Iniciar sesión en Office 365 y vaya al centro de administración](https://go.microsoft.com/fwlink/p/?LinkId=525275).</span><span class="sxs-lookup"><span data-stu-id="9e5fd-113">[Sign in to Office 365 and go to the Admin center](https://go.microsoft.com/fwlink/p/?LinkId=525275).</span></span>
    
2. <span data-ttu-id="9e5fd-114">En el centro de administración de Office 365, abra **centros de administración** y, a continuación, haga clic en **seguridad &amp; cumplimiento**.</span><span class="sxs-lookup"><span data-stu-id="9e5fd-114">In the Office 365 admin center, open **Admin centers** and then click **Security &amp; Compliance**.</span></span> 
    
3. <span data-ttu-id="9e5fd-115">En la seguridad &amp; centro de cumplimiento, vaya a **permisos**.</span><span class="sxs-lookup"><span data-stu-id="9e5fd-115">In the Security &amp; Compliance Center, go to **Permissions**.</span></span>
    
4. <span data-ttu-id="9e5fd-116">En la lista, elija el grupo de roles que se desea agregar al usuario y haga clic en **Editar** ![icono Editar](media/O365_MDM_CreatePolicy_EditIcon.gif).</span><span class="sxs-lookup"><span data-stu-id="9e5fd-116">From the list, choose the role group that you want to add the user to and click **Edit** ![Edit icon](media/O365_MDM_CreatePolicy_EditIcon.gif).</span></span>
    
5. <span data-ttu-id="9e5fd-117">En la página de propiedades del grupo de roles en **miembros**, haga clic en **Agregar**![icono Agregar](media/ITPro-EAC-AddIcon.gif) y seleccione el nombre del usuario (o usuarios) que desee agregar.</span><span class="sxs-lookup"><span data-stu-id="9e5fd-117">In the role group's properties page under **Members**, click **Add**![Add Icon](media/ITPro-EAC-AddIcon.gif) and select the name of the user (or users) you want to add.</span></span> 
    
6. <span data-ttu-id="9e5fd-118">Cuando haya seleccionado todos los usuarios que desea agregar al grupo de funciones, haga clic en \*\*Agregar-\> \*\* y, a continuación, **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="9e5fd-118">When you've selected all of the users you want to add to the role group, click **add-\>** and then **OK**.</span></span>
    
7. <span data-ttu-id="9e5fd-119">Haga clic en **Guardar** para guardar los cambios realizados en el grupo de funciones.</span><span class="sxs-lookup"><span data-stu-id="9e5fd-119">Click **Save** to save the changes to the role group.</span></span> 
    
### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="9e5fd-120">¿Cómo saber si el proceso se ha completado correctamente?</span><span class="sxs-lookup"><span data-stu-id="9e5fd-120">How do you know this worked?</span></span>

1. <span data-ttu-id="9e5fd-121">En la seguridad &amp; centro de cumplimiento, vaya a **permisos**.</span><span class="sxs-lookup"><span data-stu-id="9e5fd-121">In the Security &amp; Compliance Center, go to **Permissions**.</span></span>
    
2. <span data-ttu-id="9e5fd-122">En la lista, seleccione el grupo de roles para ver a los miembros.</span><span class="sxs-lookup"><span data-stu-id="9e5fd-122">From the list, select the role group to view the members.</span></span>
    
3. <span data-ttu-id="9e5fd-123">En la derecha, en los detalles del grupo de roles, puede ver a los miembros del grupo de roles.</span><span class="sxs-lookup"><span data-stu-id="9e5fd-123">On the right, in the role group details, you can view the members of the role group.</span></span>
    
## <a name="use-powershell-to-give-another-user-access-to-the-security-amp-compliance-center"></a><span data-ttu-id="9e5fd-124">Uso de PowerShell para ceder el otro usuario tenga acceso a la seguridad &amp; centro de cumplimiento</span><span class="sxs-lookup"><span data-stu-id="9e5fd-124">Use PowerShell to give another user access to the Security &amp; Compliance Center</span></span>

1. <span data-ttu-id="9e5fd-125">[Conectar con la seguridad de Office 365 &amp; centro de cumplimiento de normas mediante PowerShell remoto](https://go.microsoft.com/fwlink/p/?LinkID=627084).</span><span class="sxs-lookup"><span data-stu-id="9e5fd-125">[Connect to the Office 365 Security &amp; Compliance Center using remote PowerShell](https://go.microsoft.com/fwlink/p/?LinkID=627084).</span></span>
    
2. <span data-ttu-id="9e5fd-126">Use el comando **Add-RoleGroupMember** para agregar un usuario al rol Administración de la organización, tal y como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="9e5fd-126">Use the **Add-RoleGroupMember** command to add a user to the Organization Management Role, as shown in the following example.</span></span> 
    
  ```
  Add-RoleGroupMember -Identity "OrganizationManagement" -Member MatildaS
  
  ```

 <span data-ttu-id="9e5fd-127">**Parámetros**</span><span class="sxs-lookup"><span data-stu-id="9e5fd-127">**Parameters**</span></span>
  
-  <span data-ttu-id="9e5fd-128">_-Identity_ es el grupo de roles al que se agregará un miembro.</span><span class="sxs-lookup"><span data-stu-id="9e5fd-128">_-Identity_ is the role group to add a member to.</span></span> 
    
- - <span data-ttu-id="9e5fd-p102">_Miembro_ es el buzón de correo, el grupo de seguridad universal (USG) o el equipo para agregar al grupo de funciones. Puede especificar a un solo miembro a la vez.</span><span class="sxs-lookup"><span data-stu-id="9e5fd-p102">_Member_ is the mailbox, universal security group (USG), or computer to add to the role group. You can specify only one member at a time.</span></span> 
    
<span data-ttu-id="9e5fd-131">Para obtener información detallada sobre la sintaxis y los parámetros, vea [Add-RoleGroupMember](https://go.microsoft.com/fwlink/p/?LinkId=510859).</span><span class="sxs-lookup"><span data-stu-id="9e5fd-131">For detailed information on syntax and parameters, see [Add-RoleGroupMember](https://go.microsoft.com/fwlink/p/?LinkId=510859).</span></span>
  
### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="9e5fd-132">¿Cómo saber si el proceso se ha completado correctamente?</span><span class="sxs-lookup"><span data-stu-id="9e5fd-132">How do you know this worked?</span></span>

<span data-ttu-id="9e5fd-133">Para comprobar que ha asignado a los usuarios a acceso a la seguridad &amp; centro de cumplimiento, use el cmdlet **Get-RoleGroupMember** para ver los miembros en el grupo de roles de administración de la organización, tal como se muestra en el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="9e5fd-133">To verify that you've given users access to the Security &amp; Compliance Center, use the **Get-RoleGroupMember** cmdlet to view the members in the Organization Management role group, as shown in the following example.</span></span> 
  
```
Get-RoleGroupMember -Identity "OrganizationManagement"

```

<span data-ttu-id="9e5fd-134">Para obtener información detallada sobre la sintaxis y los parámetros, vea [Get-RoleGroupMember](https://go.microsoft.com/fwlink/p/?LinkId=510860).</span><span class="sxs-lookup"><span data-stu-id="9e5fd-134">For detailed information on syntax and parameters, see [Get-RoleGroupMember](https://go.microsoft.com/fwlink/p/?LinkId=510860).</span></span>
  

