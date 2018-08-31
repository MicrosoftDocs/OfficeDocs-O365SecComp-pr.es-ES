---
title: Administrar grupos en EOP
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: 212e68ac-6330-47e9-a169-6cf5e2f21e13
description: Puede usar Exchange Online Protection (EOP) para crear grupos habilitados para correo para una organización de Exchange. También puede usar EOP para definir o actualizar las propiedades del grupo que especifican la pertenencia, direcciones de correo electrónico y otros aspectos de grupos.
ms.openlocfilehash: 1af39e3a55864a9a87f90e0a00957ebf1631bb45
ms.sourcegitcommit: e9dca2d6a7838f98bb7eca127fdda2372cda402c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/21/2018
ms.locfileid: "23003179"
---
# <a name="manage-groups-in-eop"></a><span data-ttu-id="6b56a-104">Administrar grupos en EOP</span><span class="sxs-lookup"><span data-stu-id="6b56a-104">Manage groups in EOP</span></span>

 <span data-ttu-id="6b56a-p102">Puede usar Exchange Online Protection (EOP) para crear grupos habilitados para correo para una organización de Exchange. También puede usar EOP para definir o actualizar propiedades de grupo que especifiquen su pertenencia, las direcciones de correo electrónico y otros aspectos de los grupos. Puede crear grupos de distribución y grupos de seguridad, según sus necesidades. Se pueden crear estos grupos usando el Centro de administración de Exchange (EAC) o a través de Windows PowerShell remoto.</span><span class="sxs-lookup"><span data-stu-id="6b56a-p102">You can use Exchange Online Protection (EOP) to create mail-enabled groups for an Exchange organization. You can also use EOP to define or update group properties that specify membership, email addresses, and other aspects of groups. You can create distribution groups and security groups, depending on your needs. These groups can be created by using the Exchange admin center (EAC) or via remote Windows PowerShell.</span></span> 
  
## <a name="types-of-mail-enabled-groups"></a><span data-ttu-id="6b56a-109">Tipos de grupos habilitados para correo</span><span class="sxs-lookup"><span data-stu-id="6b56a-109">Types of mail-enabled groups</span></span>

<span data-ttu-id="6b56a-110">Puede crear dos tipos de grupos para su organización de Exchange:</span><span class="sxs-lookup"><span data-stu-id="6b56a-110">You can create two types of groups for your Exchange organization:</span></span>
  
- <span data-ttu-id="6b56a-p103">[Crear un grupo en el EAC](manage-groups-in-eop.md) (también conocidos como grupos de distribución) son colecciones de usuarios de correo electrónico, como un equipo u otro grupo ad hoc, que necesitan recibir o enviar correo electrónico relativo a un área de interés común. Los grupos de distribución son exclusivamente para distribuir mensajes de correo electrónico. En EOP, un grupo de distribución hace referencia a cualquier grupo habilitado para correo, tenga o no un contexto de seguridad.</span><span class="sxs-lookup"><span data-stu-id="6b56a-p103">[Create a group in the EAC](manage-groups-in-eop.md) (also known as distribution groups) are collections of email users, such as a team or other ad hoc group, who need to receive or send email regarding a common area of interest. Distribution groups are exclusively for distributing email messages. In EOP, a distribution group refers to any mail-enabled group, whether or not it has a security context.</span></span>
    
- <span data-ttu-id="6b56a-p104">[Editar o eliminar un grupo en el EAC](manage-groups-in-eop.md) (también conocidos como grupos de seguridad) son colecciones de usuarios de correo electrónico que necesitan permisos de acceso para roles de administrador. Por ejemplo, quizás quiera dar a un grupo de usuarios específico permisos de rol de administrador para que puedan configurar opciones de correo no deseado y antimalware.</span><span class="sxs-lookup"><span data-stu-id="6b56a-p104">[Edit or remove a group in the EAC](manage-groups-in-eop.md) (also known as security groups) are collections of email users who need access permissions for Admin roles. For example, you might want to give specific group of users admin role permissions so they can configure anti-spam and anti-malware settings.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="6b56a-p105">De forma predeterminada, en todos los grupos de seguridad con correo habilitado es necesario que todos los remitentes estén autenticados. De este modo se evita que remitentes externos envíen mensajes a grupos de seguridad con correo habilitado.</span><span class="sxs-lookup"><span data-stu-id="6b56a-p105">By default, all new mail-enabled security groups require that all senders be authenticated. This prevents external senders from sending messages to mail-enabled security groups.</span></span> 
  
## <a name="before-you-begin"></a><span data-ttu-id="6b56a-118">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="6b56a-118">Before you begin</span></span>

- <span data-ttu-id="6b56a-p106">Deberá tener asignados permisos antes de poder llevar a cabo este procedimiento o procedimientos. Para ver qué permisos necesita, consulte el entrada "Grupos de distribución y grupos de seguridad " en el tema [Permisos de características en EOP](feature-permissions-in-eop.md).</span><span class="sxs-lookup"><span data-stu-id="6b56a-p106">You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Distribution Groups and Security Groups" entry in the [Feature permissions in EOP](feature-permissions-in-eop.md) topic.</span></span> 
    
- <span data-ttu-id="6b56a-121">Tenga en cuenta que, al crear y gestionar grupos mediante los cmdlets de PowerShell remoto, podría encontrarse con límites.</span><span class="sxs-lookup"><span data-stu-id="6b56a-121">Be aware that when creating and managing groups by using remote PowerShell cmdlets, you may encounter throttling.</span></span>
    
- <span data-ttu-id="6b56a-122">Este cmdlet usa un método de procesamiento por lotes que provoca un retraso en la propagación de unos minutos antes de que los resultados del cmdlet sean visibles.</span><span class="sxs-lookup"><span data-stu-id="6b56a-122">This cmdlet uses a batch processing method that results in a propagation delay of a few minutes before the results of the cmdlet are visible.</span></span>
    
- <span data-ttu-id="6b56a-123">Para aprender cómo usar Windows PowerShell para conectarse a Exchange Online Protection, consulte [Conectarse a Exchange Online Protection mediante PowerShell remoto](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell?view=exchange-ps).</span><span class="sxs-lookup"><span data-stu-id="6b56a-123">To learn how to use Windows PowerShell to connect to Exchange Online Protection, see [Connect to Exchange Online Protection Using Remote PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell?view=exchange-ps).</span></span>
    
- <span data-ttu-id="6b56a-124">Para obtener información acerca de los métodos abreviados de teclado aplicables a los procedimientos de este tema, consulte **Keyboard shortcuts in Exchange 2013**.</span><span class="sxs-lookup"><span data-stu-id="6b56a-124">For information about keyboard shortcuts that may apply to the procedures in this topic, see **Keyboard shortcuts in the Exchange admin center**.</span></span>
    
> [!TIP]
> <span data-ttu-id="6b56a-p107">¿Tiene algún problema? Solicite ayuda en los foros de Exchange. Visite los foros en [Exchange Server](https://go.microsoft.com/fwlink/p/?linkId=60612),[Exchange Online](https://go.microsoft.com/fwlink/p/?linkId=267542), o [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351).</span><span class="sxs-lookup"><span data-stu-id="6b56a-p107">Having problems? Ask for help in the Exchange forums. Visit the forums at [Exchange Server](https://go.microsoft.com/fwlink/p/?linkId=60612),[Exchange Online](https://go.microsoft.com/fwlink/p/?linkId=267542), or [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351).</span></span> 
  
## <a name="create-a-group-in-the-eac"></a><span data-ttu-id="6b56a-128">Crear un grupo en el EAC</span><span class="sxs-lookup"><span data-stu-id="6b56a-128">Create a group in the EAC</span></span>

1. <span data-ttu-id="6b56a-129">En el Centro de administración de Exchange (EAC), vaya a **Destinatarios** \> **Grupos**.</span><span class="sxs-lookup"><span data-stu-id="6b56a-129">In the Exchange admin center (EAC), go to **Recipients** \> **Groups**.</span></span>
    
2. <span data-ttu-id="6b56a-p108">Haga clic en **Nuevo**![Agregar icono](../media/ITPro-EAC-AddIcon.gif) y después, haga clic en **Grupo de distribución** o **Grupo de seguridad**, según sus necesidades. Consulte [Tipos de grupos habilitados para correo](manage-groups-in-eop.md) para ver la distinción.</span><span class="sxs-lookup"><span data-stu-id="6b56a-p108">Click **New**![Add Icon](../media/ITPro-EAC-AddIcon.gif), and then click **Distribution group** or **Security group**, depending on your needs. See [Types of mail-enabled groups](manage-groups-in-eop.md) for the distinction.</span></span> 
    
3. <span data-ttu-id="6b56a-132">En la página **Nuevo grupo de distribución** o **Nuevo grupo de seguridad**, complete los campos siguientes:</span><span class="sxs-lookup"><span data-stu-id="6b56a-132">On the **New distribution group** or **New security group** page, complete the following fields:</span></span> 
    
  - <span data-ttu-id="6b56a-p109">**Nombre para mostrar** Escriba un nombre para mostrar que sea único en su organización y significativo para los usuarios de EOP. El nombre para mostrar es un campo obligatorio.</span><span class="sxs-lookup"><span data-stu-id="6b56a-p109">**Display name** Type a display name that's unique to your organization and meaningful to EOP users. The display name is required.</span></span> 
    
  - <span data-ttu-id="6b56a-p110">**Alias** Escriba un alias de grupo de hasta 64 caracteres que sea único para su organización. Los usuarios de EOP escriben el alias en la línea Para: de los mensajes de correo electrónico, y el alias se resuelve en el nombre para mostrar del grupo. Si cambia el alias, la dirección SMTP principal del grupo también cambiará y contendrá el nuevo alias. El alias es obligatorio.</span><span class="sxs-lookup"><span data-stu-id="6b56a-p110">**Alias** Type a group alias of up to 64 characters that's unique to your organization. EOP users type the alias in the To: line of email messages and the alias resolves to the group's display name. If you change the alias, the primary SMTP address for the group also changes and will contain the new alias. The alias is required.</span></span> 
    
  - <span data-ttu-id="6b56a-139">**Descripción** Escriba una descripción del grupo para que los usuarios conozcan su propósito.</span><span class="sxs-lookup"><span data-stu-id="6b56a-139">**Description** Type a description of the group so that people will know the purpose of the group.</span></span> 
    
  - <span data-ttu-id="6b56a-p111">**Propietarios** De forma predeterminada, la persona que crea un grupo es el propietario. Para crear un propietario, seleccione **Agregar**![Agregar icono](../media/ITPro-EAC-AddIcon.gif). Todos los grupos deben tener al menos un propietario.</span><span class="sxs-lookup"><span data-stu-id="6b56a-p111">**Owners** By default, the person who creates the group is the owner. You can add an owner by choosing **Add**![Add Icon](../media/ITPro-EAC-AddIcon.gif). All groups must have at least one owner.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="6b56a-143">Los propietarios no tienen que ser miembros del grupo.</span><span class="sxs-lookup"><span data-stu-id="6b56a-143">Owners don't have to be members of the group.</span></span> 
  
  - <span data-ttu-id="6b56a-p112">**Miembros** Use esta sección para agregar miembros e indicar si se necesita aprobación para los usuarios que se unan al grupo o lo dejen. Para agregar miembros al grupo, haga clic en **Agregar**![Agregar icono](../media/ITPro-EAC-AddIcon.gif).</span><span class="sxs-lookup"><span data-stu-id="6b56a-p112">**Members** Use this section to add group members and to specify whether approval is required for people to join or leave the group. To add members to the group, click **Add**![Add Icon](../media/ITPro-EAC-AddIcon.gif).</span></span>
    
4. <span data-ttu-id="6b56a-146">Haga clic en **Aceptar** para volver a la página original.</span><span class="sxs-lookup"><span data-stu-id="6b56a-146">Click **OK** to return to the original page.</span></span> 
    
5. <span data-ttu-id="6b56a-p113">Cuando haya terminado, haga clic en **Guardar** para crear el grupo. El nuevo grupo debe aparecer en la lista de grupos.</span><span class="sxs-lookup"><span data-stu-id="6b56a-p113">When you've finished, click **Save** to create the group. The new group should appear in the list of groups.</span></span> 
    
## <a name="edit-or-remove-a-group-in-the-eac"></a><span data-ttu-id="6b56a-149">Editar o eliminar un grupo en el EAC</span><span class="sxs-lookup"><span data-stu-id="6b56a-149">Edit or remove a group in the EAC</span></span>

1. <span data-ttu-id="6b56a-150">En el Centro de Administración de Exchange, vaya a **Destinatarios** \> **Grupos**.</span><span class="sxs-lookup"><span data-stu-id="6b56a-150">In the EAC, navigate to **Recipients** \> **Groups**.</span></span>
    
2. <span data-ttu-id="6b56a-151">Siga uno de estos pasos:</span><span class="sxs-lookup"><span data-stu-id="6b56a-151">Do one of the following:</span></span>
    
  - <span data-ttu-id="6b56a-p114">Para editar un grupo: en la lista de grupos, haga clic en la distribución o grupo de seguridad que desea ver o cambiar y, a continuación, haga clic en **Editar** ![icono Editar](../media/ITPro-EAC-EditIcon.gif). Puede actualizar la configuración general, agregar o quitar los propietarios del grupo y agregar o quitar a miembros del grupo, según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="6b56a-p114">To edit a group: In the list of groups, click the distribution or security group that you want to view or change, and then click **Edit** ![Edit icon](../media/ITPro-EAC-EditIcon.gif). You can update general settings, add or remove group owners, and add or remove group members, as needed.</span></span>
    
  - <span data-ttu-id="6b56a-154">Para quitar un grupo: Seleccione el grupo y haga clic en **Quitar**![Icono de quitar](../media/ITPro-EAC-RemoveIcon.gif).</span><span class="sxs-lookup"><span data-stu-id="6b56a-154">To remove a group: Select the group and click **Remove**![Remove icon](../media/ITPro-EAC-RemoveIcon.gif).</span></span>
    
3. <span data-ttu-id="6b56a-155">Cuando termine los cambios, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="6b56a-155">When you're finished making your changes, click **Save**.</span></span>
    
## <a name="create-edit-or-remove-a-group-using-remote-windows-powershell"></a><span data-ttu-id="6b56a-156">Crear, modificar o quitar un grupo utilizando Windows PowerShell remoto</span><span class="sxs-lookup"><span data-stu-id="6b56a-156">Create, edit, or remove a group using remote Windows PowerShell</span></span>

<span data-ttu-id="6b56a-p115">En esta sección se proporciona información acerca de cómo crear grupos y cambiar sus propiedades mediante el uso de Windows PowerShell remoto. También se muestra cómo quitar un grupo existente.</span><span class="sxs-lookup"><span data-stu-id="6b56a-p115">This section provides information about creating groups and changing their properties by using remote Windows PowerShell. It also shows how to remove an existing group.</span></span> 
  
 <span data-ttu-id="6b56a-159">**Para crear un grupo con Windows PowerShell remoto**</span><span class="sxs-lookup"><span data-stu-id="6b56a-159">**To create a group using remote Windows PowerShell**</span></span>
  
<span data-ttu-id="6b56a-p116">En este ejemplo se utiliza el cmdlet [New-EOPDistributionGroup](http://technet.microsoft.com/library/4610dfe5-fca8-4ba8-be3c-535d1753e0f4.aspx) para crear un grupo de distribución con el alias itadmin y los administradores de TI de nombre. También agrega los usuarios como miembros del grupo.</span><span class="sxs-lookup"><span data-stu-id="6b56a-p116">This example uses the [New-EOPDistributionGroup](http://technet.microsoft.com/library/4610dfe5-fca8-4ba8-be3c-535d1753e0f4.aspx) cmdlet to create a distribution group with an alias of itadmin and the name IT Administrators. It also adds users as members of the group.</span></span> 
  
```
New-EOPDistributionGroup -Type "Distribution" -Name "IT Administrators" -Alias itadmin -Members @("Member1","Member2","Member3") -ManagedBy "Member1"

```

<span data-ttu-id="6b56a-162">Para crear un grupo de seguridad en lugar de un grupo de distribución, especifique  `-Type "Security"` en su lugar.</span><span class="sxs-lookup"><span data-stu-id="6b56a-162">To create a security group instead of a distribution group, specify  `-Type "Security"` instead.</span></span> 
  
<span data-ttu-id="6b56a-163">Para comprobar que se ha creado correctamente el grupo de los administradores de TI, ejecute el cmdlet [Get-Recipient](http://technet.microsoft.com/library/2ce6250f-0ad3-4b29-870c-e1d6e1e154bc.aspx) para mostrar la información acerca del nuevo grupo:</span><span class="sxs-lookup"><span data-stu-id="6b56a-163">To verify that you've successfully created the IT Administrators group, run the [Get-Recipient](http://technet.microsoft.com/library/2ce6250f-0ad3-4b29-870c-e1d6e1e154bc.aspx) cmdlet to display information about the new group:</span></span> 
  
```
Get-Recipient "IT Administrators" | Format-List

```

<span data-ttu-id="6b56a-164">Para obtener una lista de miembros del grupo, ejecute el cmdlet [Get-DistributionGroupMember](http://technet.microsoft.com/library/15c71bc5-4246-44ac-8b34-8ccd585294b5.aspx) como sigue:</span><span class="sxs-lookup"><span data-stu-id="6b56a-164">To get a list of members in the group, run the [Get-DistributionGroupMember](http://technet.microsoft.com/library/15c71bc5-4246-44ac-8b34-8ccd585294b5.aspx) cmdlet as follows:</span></span> 
  
```
Get-DistributionGroupMember "IT Administrators"

```

<span data-ttu-id="6b56a-165">Para obtener una lista completa de todos los grupos, ejecute el cmdlet [Get-Recipient](http://technet.microsoft.com/library/2ce6250f-0ad3-4b29-870c-e1d6e1e154bc.aspx) como sigue:</span><span class="sxs-lookup"><span data-stu-id="6b56a-165">To get a full list of all your groups, run the [Get-Recipient](http://technet.microsoft.com/library/2ce6250f-0ad3-4b29-870c-e1d6e1e154bc.aspx) cmdlet as follows:</span></span> 
  
```
Get-Recipient -RecipientType "MailUniversalDistributionGroup" | FT | more

```

 <span data-ttu-id="6b56a-166">**Para cambiar las propiedades de un grupo mediante Windows PowerShell remoto**</span><span class="sxs-lookup"><span data-stu-id="6b56a-166">**To change the properties of a group using remote Windows PowerShell**</span></span>
  
<span data-ttu-id="6b56a-p117">Use los cmdlets [Get-Recipient](http://technet.microsoft.com/library/2ce6250f-0ad3-4b29-870c-e1d6e1e154bc.aspx) y [Set-EOPDistributionGroup](http://technet.microsoft.com/library/689a66c5-a524-4870-88f3-091fd6eae3b7.aspx) para ver y cambiar las propiedades de los grupos. Una de las ventajas de usar PowerShell remoto en lugar de EAC es la capacidad de cambiar las propiedades de varios grupos.</span><span class="sxs-lookup"><span data-stu-id="6b56a-p117">Use the [Get-Recipient](http://technet.microsoft.com/library/2ce6250f-0ad3-4b29-870c-e1d6e1e154bc.aspx) and [Set-EOPDistributionGroup](http://technet.microsoft.com/library/689a66c5-a524-4870-88f3-091fd6eae3b7.aspx) cmdlets to view and change properties for groups. An advantage of using remote PowerShell instead of the EAC is the ability to change properties for multiple groups.</span></span> 
  
<span data-ttu-id="6b56a-169">A continuación presentamos algunos ejemplos del uso de Windows PowerShell remoto para cambiar las propiedades de grupo.</span><span class="sxs-lookup"><span data-stu-id="6b56a-169">Here are some examples of using remote Windows PowerShell to change group properties.</span></span>
  
<span data-ttu-id="6b56a-170">En este ejemplo se usa el cmdlet [Set-EOPDistributionGroup](http://technet.microsoft.com/library/689a66c5-a524-4870-88f3-091fd6eae3b7.aspx) para cambiar la dirección SMTP primaria (también denominada dirección de respuesta) del grupo Empleados de Seattle a sea.employees@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="6b56a-170">This example uses the [Set-EOPDistributionGroup](http://technet.microsoft.com/library/689a66c5-a524-4870-88f3-091fd6eae3b7.aspx) cmdlet to change the primary SMTP address (also called the reply address) for the Seattle Employees group to sea.employees@contoso.com.</span></span> 
  
```
Set-EOPDistributionGroup "Seattle Employees" -PrimarysmptAddress "sea.employees@contoso.com"

```

<span data-ttu-id="6b56a-p118">Para comprobar que se han cambiado correctamente las propiedades de un grupo, use el cmdlet [Get-Recipient](http://technet.microsoft.com/library/2ce6250f-0ad3-4b29-870c-e1d6e1e154bc.aspx) para comprobar los cambios. Una ventaja de usar el PowerShell remoto es que puede consultar varias propiedades de varios grupos. En el ejemplo anterior en el que se cambió el grupo de la dirección SMTP primaria, ejecute el siguiente comando para comprar el nuevo valor.</span><span class="sxs-lookup"><span data-stu-id="6b56a-p118">To verify that you've successfully changed the properties for a group, use the [Get-Recipient](http://technet.microsoft.com/library/2ce6250f-0ad3-4b29-870c-e1d6e1e154bc.aspx) cmdlet to verify the changes. One advantage of using remote PowerShell is that you can view multiple properties for multiple groups. In the previous example where the primary SMTP address group was changed, run the following command to verify the new value:</span></span> 
  
```
Get-Recipient "Seattle Employees" | FL "PrimarySmtpAddress"

```

<span data-ttu-id="6b56a-p119">En este ejemplo se usa el cmdlet [Update-EOPDistributionGroupMember](http://technet.microsoft.com/library/a6d4f790-1b94-42f8-af6f-fa79c504d8ec.aspx) para actualizar todos los miembros del grupo Empleados de Seattle. Use una coma para separar todos los miembros.</span><span class="sxs-lookup"><span data-stu-id="6b56a-p119">This example uses the [Update-EOPDistributionGroupMember](http://technet.microsoft.com/library/a6d4f790-1b94-42f8-af6f-fa79c504d8ec.aspx) cmdlet to update all the members of the Seattle Employees group. Use a comma to separate all members.</span></span> 
  
```
Update-EOPDistributionGroupMember -Identity "Seattle Employees" -Members @("Member1","Member2","Member3","Member4","Member5")

```

<span data-ttu-id="6b56a-176">Para obtener la lista de todos los miembros del grupo Empleados de Seattle, use el cmdlet [Get-DistributionGroupMember](http://technet.microsoft.com/library/15c71bc5-4246-44ac-8b34-8ccd585294b5.aspx) como sigue:</span><span class="sxs-lookup"><span data-stu-id="6b56a-176">To get the list of all the members in the group Seattle Employees, use the [Get-DistributionGroupMember](http://technet.microsoft.com/library/15c71bc5-4246-44ac-8b34-8ccd585294b5.aspx) cmdlet as follows:</span></span> 
  
```
Get-DistributionGroupMember "Seattle Employees"

```

 <span data-ttu-id="6b56a-177">**Para quitar un grupo con Windows PowerShell remoto**</span><span class="sxs-lookup"><span data-stu-id="6b56a-177">**To remove a group using remote Windows PowerShell**</span></span>
  
<span data-ttu-id="6b56a-178">En este ejemplo se usa el cmdlet [Remove-EOPDistributionGroup](http://technet.microsoft.com/library/a17b1307-3187-40b0-a438-c7b35a34c002.aspx) para quitar un grupo de distribución denominado Administradores de TI.</span><span class="sxs-lookup"><span data-stu-id="6b56a-178">This example uses the [Remove-EOPDistributionGroup](http://technet.microsoft.com/library/a17b1307-3187-40b0-a438-c7b35a34c002.aspx) cmdlet to remove a distribution group named IT Administrators.</span></span> 
  
```
Remove-EOPDistributionGroup -Identity "IT Administrators" 

```

<span data-ttu-id="6b56a-179">Para comprobar que se ha quitado el grupo, ejecute el cmdlet [Get-Recipient](http://technet.microsoft.com/library/2ce6250f-0ad3-4b29-870c-e1d6e1e154bc.aspx) como sigue y confirme que el grupo (en este caso "Administradores de TI) se ha eliminado.</span><span class="sxs-lookup"><span data-stu-id="6b56a-179">To verify that the group was removed, run the [Get-Recipient](http://technet.microsoft.com/library/2ce6250f-0ad3-4b29-870c-e1d6e1e154bc.aspx) cmdlet as follows, and confirm that the group (in this case "It Administrators") was deleted.</span></span> 
  
```
Get-Recipient -RecipientType "MailUniversalDistributionGroup"

```


