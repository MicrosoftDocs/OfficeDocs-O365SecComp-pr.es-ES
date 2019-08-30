---
title: Administrar grupos en EOP
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 11/17/2014
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 212e68ac-6330-47e9-a169-6cf5e2f21e13
description: Puede usar Exchange Online Protection (EOP) para crear grupos habilitados para correo para una organización de Exchange. También puede usar EOP para definir o actualizar propiedades de grupo que especifiquen su pertenencia, las direcciones de correo electrónico y otros aspectos de los grupos.
ms.openlocfilehash: 9ce501c5d51561a7be86963ae98b62046995e46f
ms.sourcegitcommit: 361aab46b1bb295ed2dcc1a417ac81f699b8ff78
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/30/2019
ms.locfileid: "36676740"
---
# <a name="manage-groups-in-eop"></a><span data-ttu-id="13342-104">Administrar grupos en EOP</span><span class="sxs-lookup"><span data-stu-id="13342-104">Manage groups in EOP</span></span>

 <span data-ttu-id="13342-p102">Puede usar Exchange Online Protection (EOP) para crear grupos habilitados para correo para una organización de Exchange. También puede usar EOP para definir o actualizar propiedades de grupo que especifiquen su pertenencia, las direcciones de correo electrónico y otros aspectos de los grupos. Puede crear grupos de distribución y grupos de seguridad, según sus necesidades. Se pueden crear estos grupos usando el Centro de administración de Exchange (EAC) o a través de Windows PowerShell remoto.</span><span class="sxs-lookup"><span data-stu-id="13342-p102">You can use Exchange Online Protection (EOP) to create mail-enabled groups for an Exchange organization. You can also use EOP to define or update group properties that specify membership, email addresses, and other aspects of groups. You can create distribution groups and security groups, depending on your needs. These groups can be created by using the Exchange admin center (EAC) or via remote Windows PowerShell.</span></span>
  
## <a name="types-of-mail-enabled-groups"></a><span data-ttu-id="13342-109">Tipos de grupos habilitados para correo</span><span class="sxs-lookup"><span data-stu-id="13342-109">Types of mail-enabled groups</span></span>

<span data-ttu-id="13342-110">Puede crear dos tipos de grupos para su organización de Exchange:</span><span class="sxs-lookup"><span data-stu-id="13342-110">You can create two types of groups for your Exchange organization:</span></span>
  
- <span data-ttu-id="13342-111">Los grupos de distribución son colecciones de usuarios de correo electrónico, como un equipo u otro grupo ad hoc, que necesitan recibir o enviar correo electrónico sobre un área común de interés.</span><span class="sxs-lookup"><span data-stu-id="13342-111">Distribution groups are collections of email users, such as a team or other ad hoc group, who need to receive or send email regarding a common area of interest.</span></span> <span data-ttu-id="13342-112">Los grupos de distribución son exclusivamente para distribuir mensajes de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="13342-112">Distribution groups are exclusively for distributing email messages.</span></span> <span data-ttu-id="13342-113">En EOP, un grupo de distribución hace referencia a cualquier grupo habilitado para correo, tenga o no un contexto de seguridad.</span><span class="sxs-lookup"><span data-stu-id="13342-113">In EOP, a distribution group refers to any mail-enabled group, whether or not it has a security context.</span></span>

- <span data-ttu-id="13342-114">Los grupos de seguridad son colecciones de usuarios de correo electrónico que necesitan permisos de acceso para los roles de administrador.</span><span class="sxs-lookup"><span data-stu-id="13342-114">Security groups are collections of email users who need access permissions for Admin roles.</span></span> <span data-ttu-id="13342-115">Por ejemplo, quizás quiera dar a un grupo de usuarios específico permisos de rol de administrador para que puedan configurar opciones de correo no deseado y antimalware.</span><span class="sxs-lookup"><span data-stu-id="13342-115">For example, you might want to give specific group of users admin role permissions so they can configure anti-spam and anti-malware settings.</span></span>

    > [!NOTE]
    > <span data-ttu-id="13342-p105">De forma predeterminada, en todos los grupos de seguridad con correo habilitado es necesario que todos los remitentes estén autenticados. De este modo se evita que remitentes externos envíen mensajes a grupos de seguridad con correo habilitado.</span><span class="sxs-lookup"><span data-stu-id="13342-p105">By default, all new mail-enabled security groups require that all senders be authenticated. This prevents external senders from sending messages to mail-enabled security groups.</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="13342-118">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="13342-118">Before you begin</span></span>

- <span data-ttu-id="13342-p106">Deberá tener asignados permisos antes de poder llevar a cabo este procedimiento o procedimientos. Para ver qué permisos necesita, consulte el entrada "Grupos de distribución y grupos de seguridad " en el tema [Permisos de características en EOP](feature-permissions-in-eop.md).</span><span class="sxs-lookup"><span data-stu-id="13342-p106">You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Distribution Groups and Security Groups" entry in the [Feature permissions in EOP](feature-permissions-in-eop.md) topic.</span></span>

- <span data-ttu-id="13342-121">Para abrir el centro de administración de Exchange, vea [centro de administración de Exchange en Exchange Online Protection](../exchange-admin-center-in-exchange-online-protection-eop.md).</span><span class="sxs-lookup"><span data-stu-id="13342-121">To open the Exchange admin center, see [Exchange admin center in Exchange Online Protection](../exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="13342-122">Tenga en cuenta que al crear y administrar grupos mediante los cmdlets de PowerShell de Exchange Online Protection, es posible que se encuentre con limitaciones.</span><span class="sxs-lookup"><span data-stu-id="13342-122">Be aware that when creating and managing groups by using Exchange Online Protection PowerShell cmdlets, you may encounter throttling.</span></span>

- <span data-ttu-id="13342-123">Los procedimientos de PowerShell de este tema usan un método de procesamiento por lotes que da como resultado un retraso en la propagación de unos minutos antes de que los resultados de los comandos estén visibles.</span><span class="sxs-lookup"><span data-stu-id="13342-123">The PowerShell procedures in this topic use a batch processing method that results in a propagation delay of a few minutes before the results of the commands are visible.</span></span>

- <span data-ttu-id="13342-124">Para obtener información sobre cómo usar Windows PowerShell para conectarse a Exchange Online Protection, vea [conectarse a PowerShell de Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell?view=exchange-ps).</span><span class="sxs-lookup"><span data-stu-id="13342-124">To learn how to use Windows PowerShell to connect to Exchange Online Protection, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell?view=exchange-ps).</span></span>

- <span data-ttu-id="13342-125">Para obtener información acerca de los métodos abreviados de teclado que se pueden aplicar a los procedimientos de este tema, consulte [métodos abreviados de teclado para el centro de administración de Exchange en Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span><span class="sxs-lookup"><span data-stu-id="13342-125">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="13342-126">¿Problemas?</span><span class="sxs-lookup"><span data-stu-id="13342-126">Having problems?</span></span> <span data-ttu-id="13342-127">Solicite ayuda en el foro de [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) .</span><span class="sxs-lookup"><span data-stu-id="13342-127">Ask for help in the [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) forum.</span></span> 
  
## <a name="create-a-group-in-the-eac"></a><span data-ttu-id="13342-128">Crear un grupo en el EAC</span><span class="sxs-lookup"><span data-stu-id="13342-128">Create a group in the EAC</span></span>

1. <span data-ttu-id="13342-129">En el EAC, vaya a \*\*\*\* \> **grupos**de destinatarios.</span><span class="sxs-lookup"><span data-stu-id="13342-129">In the EAC, go to **Recipients** \> **Groups**.</span></span>

2. <span data-ttu-id="13342-130">Haga \*\*\*\* ![clic en nuevo](../media/ITPro-EAC-AddIcon.gif)icono Agregar y, a continuación, haga clic en **grupo de distribución** o **grupo de seguridad**, según sus necesidades.</span><span class="sxs-lookup"><span data-stu-id="13342-130">Click **New** ![Add Icon](../media/ITPro-EAC-AddIcon.gif), and then click **Distribution group** or **Security group**, depending on your needs.</span></span>

3. <span data-ttu-id="13342-131">En la página **nuevo grupo de distribución** o **nuevo grupo de seguridad** , configure las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="13342-131">On the **New distribution group** or **New security group** page, configure the following settings:</span></span>

   - <span data-ttu-id="13342-132">**Nombre para mostrar**: escriba un nombre para mostrar que sea único en su organización y tenga sentido para los usuarios de EOP.</span><span class="sxs-lookup"><span data-stu-id="13342-132">**Display name**: Type a display name that's unique to your organization and meaningful to EOP users.</span></span> <span data-ttu-id="13342-133">El nombre para mostrar es un campo obligatorio.</span><span class="sxs-lookup"><span data-stu-id="13342-133">The display name is required.</span></span>

   - <span data-ttu-id="13342-134">**Alias**: escriba un alias de grupo de hasta 64 caracteres que sea único para su organización.</span><span class="sxs-lookup"><span data-stu-id="13342-134">**Alias**: Type a group alias of up to 64 characters that's unique to your organization.</span></span> <span data-ttu-id="13342-135">Los usuarios de EOP escriben el alias en la línea Para: de los mensajes de correo electrónico, y el alias se resuelve en el nombre para mostrar del grupo.</span><span class="sxs-lookup"><span data-stu-id="13342-135">EOP users type the alias in the To: line of email messages and the alias resolves to the group's display name.</span></span> <span data-ttu-id="13342-136">Si cambia el alias, la dirección SMTP principal del grupo también cambiará y contendrá el nuevo alias.</span><span class="sxs-lookup"><span data-stu-id="13342-136">If you change the alias, the primary SMTP address for the group also changes and will contain the new alias.</span></span> <span data-ttu-id="13342-137">El alias es obligatorio.</span><span class="sxs-lookup"><span data-stu-id="13342-137">The alias is required.</span></span> 

   - <span data-ttu-id="13342-138">**Descripción**: escriba una descripción del grupo para que los usuarios sepan el propósito del grupo.</span><span class="sxs-lookup"><span data-stu-id="13342-138">**Description**: Type a description of the group so that people will know the purpose of the group.</span></span> 

   - <span data-ttu-id="13342-139">**Propietarios**: de forma predeterminada, la persona que crea el grupo es el propietario.</span><span class="sxs-lookup"><span data-stu-id="13342-139">**Owners**: By default, the person who creates the group is the owner.</span></span> <span data-ttu-id="13342-140">Puede Agregar un propietario seleccionando **Agregar** ![icono](../media/ITPro-EAC-AddIcon.gif)de agregar.</span><span class="sxs-lookup"><span data-stu-id="13342-140">You can add an owner by choosing **Add** ![Add Icon](../media/ITPro-EAC-AddIcon.gif).</span></span> <span data-ttu-id="13342-141">Todos los grupos deben tener al menos un propietario.</span><span class="sxs-lookup"><span data-stu-id="13342-141">All groups must have at least one owner.</span></span>

     > [!NOTE]
     > <span data-ttu-id="13342-142">Los propietarios no tienen que ser miembros del grupo.</span><span class="sxs-lookup"><span data-stu-id="13342-142">Owners don't have to be members of the group.</span></span>
  
   - <span data-ttu-id="13342-143">**Miembros**: Use esta sección para agregar miembros de grupo y especificar si la aprobación es necesaria para que los usuarios se unan al grupo o lo abandonen.</span><span class="sxs-lookup"><span data-stu-id="13342-143">**Members**: Use this section to add group members and to specify whether approval is required for people to join or leave the group.</span></span> <span data-ttu-id="13342-144">Para agregar miembros al grupo, haga clic en **Agregar** ![icono](../media/ITPro-EAC-AddIcon.gif)de agregar.</span><span class="sxs-lookup"><span data-stu-id="13342-144">To add members to the group, click **Add** ![Add Icon](../media/ITPro-EAC-AddIcon.gif).</span></span>

4. <span data-ttu-id="13342-145">Haga clic en **Aceptar** para volver a la página original.</span><span class="sxs-lookup"><span data-stu-id="13342-145">Click **OK** to return to the original page.</span></span>

5. <span data-ttu-id="13342-p112">Cuando haya terminado, haga clic en **Guardar** para crear el grupo. El nuevo grupo debe aparecer en la lista de grupos.</span><span class="sxs-lookup"><span data-stu-id="13342-p112">When you've finished, click **Save** to create the group. The new group should appear in the list of groups.</span></span>

## <a name="edit-or-remove-a-group-in-the-eac"></a><span data-ttu-id="13342-148">Editar o eliminar un grupo en el EAC</span><span class="sxs-lookup"><span data-stu-id="13342-148">Edit or remove a group in the EAC</span></span>

1. <span data-ttu-id="13342-149">En el Centro de Administración de Exchange, vaya a **Destinatarios** \> **Grupos**.</span><span class="sxs-lookup"><span data-stu-id="13342-149">In the EAC, navigate to **Recipients** \> **Groups**.</span></span>

2. <span data-ttu-id="13342-150">Realice uno de los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="13342-150">Do one of the following steps:</span></span>

   - <span data-ttu-id="13342-151">Para editar un grupo: en la lista de grupos, haga clic en el grupo que desea ver o modificar y, a continuación \*\*\*\* ![, haga clic](../media/ITPro-EAC-EditIcon.gif)en Editar icono de edición.</span><span class="sxs-lookup"><span data-stu-id="13342-151">To edit a group: In the list of groups, click the group that you want to view or change, and then click **Edit** ![Edit icon](../media/ITPro-EAC-EditIcon.gif).</span></span> <span data-ttu-id="13342-152">Puede actualizar la configuración general, agregar o quitar propietarios de grupo y agregar o quitar miembros del grupo según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="13342-152">You can update general settings, add or remove group owners, and add or remove group members as needed.</span></span>

   - <span data-ttu-id="13342-153">Para quitar un grupo: seleccione el grupo y haga \*\*\*\* ![clic en quitar](../media/ITPro-EAC-RemoveIcon.gif)icono quitar.</span><span class="sxs-lookup"><span data-stu-id="13342-153">To remove a group: Select the group and click **Remove** ![Remove icon](../media/ITPro-EAC-RemoveIcon.gif).</span></span>

3. <span data-ttu-id="13342-154">Cuando termine los cambios, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="13342-154">When you're finished making your changes, click **Save**.</span></span>

## <a name="create-edit-or-remove-a-group-using-remote-windows-powershell"></a><span data-ttu-id="13342-155">Crear, modificar o quitar un grupo utilizando Windows PowerShell remoto</span><span class="sxs-lookup"><span data-stu-id="13342-155">Create, edit, or remove a group using remote Windows PowerShell</span></span>

<span data-ttu-id="13342-156">En esta sección se proporciona información acerca de la creación de grupos y el cambio de sus propiedades en PowerShell de Exchange Online Protection.</span><span class="sxs-lookup"><span data-stu-id="13342-156">This section provides information about creating groups and changing their properties in Exchange Online Protection PowerShell.</span></span> <span data-ttu-id="13342-157">También se muestra cómo quitar un grupo existente.</span><span class="sxs-lookup"><span data-stu-id="13342-157">It also shows how to remove an existing group.</span></span>
  
### <a name="create-a-group-using-remote-windows-powershell"></a><span data-ttu-id="13342-158">Crear un grupo con Windows PowerShell remoto</span><span class="sxs-lookup"><span data-stu-id="13342-158">Create a group using remote Windows PowerShell</span></span>
  
<span data-ttu-id="13342-p115">En este ejemplo se utiliza el cmdlet [New-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/New-EOPDistributionGroup) para crear un grupo de distribución con el alias itadmin y los administradores de TI de nombre. También agrega los usuarios como miembros del grupo.</span><span class="sxs-lookup"><span data-stu-id="13342-p115">This example uses the [New-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/New-EOPDistributionGroup) cmdlet to create a distribution group with an alias of itadmin and the name IT Administrators. It also adds users as members of the group.</span></span>
  
```Powershell
New-EOPDistributionGroup -Type Distribution -Name "IT Administrators" -Alias itadmin -Members @("Member1","Member2","Member3") -ManagedBy Member1
```

<span data-ttu-id="13342-161">**Nota**: para crear un grupo de seguridad en lugar de un grupo de distribución, use `Security` el valor del parámetro *Type* .</span><span class="sxs-lookup"><span data-stu-id="13342-161">**Note**: To create a security group instead of a distribution group, use the value `Security` for the *Type* parameter.</span></span>
  
<span data-ttu-id="13342-162">Para comprobar que el grupo de administradores de TI se creó correctamente, ejecute el siguiente comando para mostrar información sobre el nuevo Grupo:</span><span class="sxs-lookup"><span data-stu-id="13342-162">To verify that you've successfully created the IT Administrators group, run the following command to display information about the new group:</span></span>
  
```Powershell
Get-Recipient "IT Administrators" | Format-List
```

<span data-ttu-id="13342-163">Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [Get-recipient](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/Get-Recipient).</span><span class="sxs-lookup"><span data-stu-id="13342-163">For detailed syntax and parameter information, see [Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/Get-Recipient).</span></span>

<span data-ttu-id="13342-164">Para obtener una lista de los miembros del grupo, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="13342-164">To get a list of members in the group, run the following command:</span></span>
  
```Powershell
Get-DistributionGroupMember "IT Administrators"
```

<span data-ttu-id="13342-165">Para obtener información más detallada acerca de la sintaxis y los parámetros, consulte [Get-DistributionGroupMember](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-distributiongroupmember).</span><span class="sxs-lookup"><span data-stu-id="13342-165">For detailed syntax and parameter information, see [Get-DistributionGroupMember](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-distributiongroupmember).</span></span>

<span data-ttu-id="13342-166">Para obtener una lista completa de todos los grupos, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="13342-166">To get a full list of all your groups, run the following command:</span></span>
  
```Powershell
Get-Recipient -RecipientType "MailUniversalDistributionGroup" | Format-Table | more
```

### <a name="change-the-properties-of-a-group-using-remote-windows-powershell"></a><span data-ttu-id="13342-167">Cambiar las propiedades de un grupo mediante Windows PowerShell remoto</span><span class="sxs-lookup"><span data-stu-id="13342-167">Change the properties of a group using remote Windows PowerShell</span></span>
  
<span data-ttu-id="13342-168">Una de las ventajas de usar PowerShell en lugar de la EAC es la capacidad de cambiar las propiedades de varios grupos.</span><span class="sxs-lookup"><span data-stu-id="13342-168">An advantage of using PowerShell instead of the EAC is the ability to change properties for multiple groups.</span></span>
  
<span data-ttu-id="13342-169">A continuación, se muestran algunos ejemplos de cómo usar PowerShell de Exchange Online Protection para cambiar las propiedades del grupo.</span><span class="sxs-lookup"><span data-stu-id="13342-169">Here are some examples of using Exchange Online Protection PowerShell to change group properties.</span></span>
  
<span data-ttu-id="13342-170">En este ejemplo se usan los cambios en la dirección SMTP principal (también denominada dirección de respuesta) del grupo empleados de Seattle en sea.employees@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="13342-170">This example uses changes the primary SMTP address (also called the reply address) for the Seattle Employees group to sea.employees@contoso.com.</span></span>
  
```Powershell
Set-EOPDistributionGroup "Seattle Employees" -PrimarysmptAddress "sea.employees@contoso.com"
```

<span data-ttu-id="13342-171">Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [set-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/set-eopdistributiongroup).</span><span class="sxs-lookup"><span data-stu-id="13342-171">For detailed syntax and parameter information, see [Set-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/set-eopdistributiongroup).</span></span>

<span data-ttu-id="13342-172">Para comprobar que cambió correctamente las propiedades del grupo, ejecute el siguiente comando para comprobar el nuevo valor:</span><span class="sxs-lookup"><span data-stu-id="13342-172">To verify that you've successfully changed the properties for the group, run the following command to verify the new value:</span></span>
  
```Powershell
Get-Recipient "Seattle Employees" | Format-List "PrimarySmtpAddress"
```

<span data-ttu-id="13342-173">En este ejemplo se actualizan todos los miembros del grupo empleados de Seattle.</span><span class="sxs-lookup"><span data-stu-id="13342-173">This example updates all the members of the Seattle Employees group.</span></span> <span data-ttu-id="13342-174">Use una coma para separar todos los miembros.</span><span class="sxs-lookup"><span data-stu-id="13342-174">Use a comma to separate all members.</span></span>
  
```Powershell
Update-EOPDistributionGroupMember -Identity "Seattle Employees" -Members @("Member1","Member2","Member3","Member4","Member5")
```

<span data-ttu-id="13342-175">Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [Update-EOPDistributionGroupMember](https://docs.microsoft.com/en-us/powershell/module/exchange/users-and-groups/update-eopdistributiongroupmember).</span><span class="sxs-lookup"><span data-stu-id="13342-175">For detailed syntax and parameter information, see [Update-EOPDistributionGroupMember](https://docs.microsoft.com/en-us/powershell/module/exchange/users-and-groups/update-eopdistributiongroupmember).</span></span>

<span data-ttu-id="13342-176">Para obtener la lista de todos los miembros del grupo empleados de Seattle, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="13342-176">To get the list of all the members in the group Seattle Employees, run the following command:</span></span> 
  
```Powershell
Get-DistributionGroupMember "Seattle Employees"
```

### <a name="remove-a-group-using-remote-windows-powershell"></a><span data-ttu-id="13342-177">Quitar un grupo mediante Windows PowerShell remoto</span><span class="sxs-lookup"><span data-stu-id="13342-177">Remove a group using remote Windows PowerShell</span></span>
  
<span data-ttu-id="13342-178">En este ejemplo se quita el grupo de distribución denominado administradores de ti.</span><span class="sxs-lookup"><span data-stu-id="13342-178">This example uses removes the distribution group named IT Administrators.</span></span>
  
```Powershell
Remove-EOPDistributionGroup -Identity "IT Administrators"
```

<span data-ttu-id="13342-179">Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [Remove-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/remove-eopdistributiongroup).</span><span class="sxs-lookup"><span data-stu-id="13342-179">For detailed syntax and parameter information, see [Remove-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/remove-eopdistributiongroup).</span></span>

<span data-ttu-id="13342-180">Para comprobar que se ha quitado el grupo, ejecute el siguiente comando y confirme que se eliminó el grupo (en este caso, "administradores de ti").</span><span class="sxs-lookup"><span data-stu-id="13342-180">To verify that the group was removed, run the following command, and confirm that the group (in this case "It Administrators") was deleted.</span></span>
  
```Powershell
Get-Recipient -RecipientType "MailUniversalDistributionGroup"
```
