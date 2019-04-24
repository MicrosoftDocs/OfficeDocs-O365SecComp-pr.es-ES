---
title: Configuración de la administración del acceso con privilegios en Office 365
ms.author: robmazz
author: robmazz
manager: laurawi
ms.audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
ms.custom: Ent_Solutions
ms.assetid: ''
description: Use este tema para obtener más información sobre cómo configurar la administración del acceso con privilegios en Office 365
ms.openlocfilehash: e086e93c268fe4de627bef30d3ac7aed8e6b1f98
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32265242"
---
# <a name="configuring-privileged-access-management-in-office-365"></a><span data-ttu-id="67fc7-103">Configuración de la administración del acceso con privilegios en Office 365</span><span class="sxs-lookup"><span data-stu-id="67fc7-103">Configuring privileged access management in Office 365</span></span>

> [!IMPORTANT]
> <span data-ttu-id="67fc7-104">En este tema se tratan las instrucciones de implementación y configuración de las características disponibles actualmente en Office 365 E5 y las SKU de cumplimiento avanzado.</span><span class="sxs-lookup"><span data-stu-id="67fc7-104">This topic covers deployment and configuration guidance for features only currently available in Office 365 E5 and Advanced Compliance SKUs.</span></span>

<span data-ttu-id="67fc7-105">Este tema le guiará a través de la habilitación y configuración de la administración del acceso con privilegios en su organización de Office 365.</span><span class="sxs-lookup"><span data-stu-id="67fc7-105">This topic guides you through enabling and configuring privileged access management in your Office 365 organization.</span></span> <span data-ttu-id="67fc7-106">Puede usar tanto el centro de administración de Microsoft 365 como PowerShell de administración de Exchange para administrar y usar el acceso con privilegios.</span><span class="sxs-lookup"><span data-stu-id="67fc7-106">You can use either the Microsoft 365 Admin Center or Exchange Management PowerShell to manage and use privileged access.</span></span> 

## <a name="enable-and-configure-privileged-access-management"></a><span data-ttu-id="67fc7-107">Habilitación y configuración de la administración del acceso con privilegios</span><span class="sxs-lookup"><span data-stu-id="67fc7-107">Enable and configure privileged access management</span></span>

<span data-ttu-id="67fc7-108">Siga estos pasos para configurar y usar el acceso con privilegios en su organización de Office 365:</span><span class="sxs-lookup"><span data-stu-id="67fc7-108">Follow these steps to set up and use privileged access in your Office 365 organization:</span></span>

- [<span data-ttu-id="67fc7-109">Paso 1: crear un grupo de aprobadores</span><span class="sxs-lookup"><span data-stu-id="67fc7-109">Step 1: Create an approver's group</span></span>](privileged-access-management-configuration.md#step1)

    <span data-ttu-id="67fc7-110">Antes de empezar a usar el acceso de privilegios, determine quién necesita autoridad de aprobación para el acceso a las tareas elevadas y privilegiadas.</span><span class="sxs-lookup"><span data-stu-id="67fc7-110">Before you start using privilege access, determine who needs approval authority for incoming requests for access to elevated and privileged tasks.</span></span> <span data-ttu-id="67fc7-111">Cualquier usuario que forme parte del grupo de aprobadores puede aprobar solicitudes de acceso.</span><span class="sxs-lookup"><span data-stu-id="67fc7-111">Any user who is part of the Approvers’ group is able to approve access requests.</span></span> <span data-ttu-id="67fc7-112">Para habilitarlo, cree un grupo de seguridad habilitado para correo en Office 365.</span><span class="sxs-lookup"><span data-stu-id="67fc7-112">This is enabled by creating a mail-enabled security group in Office 365.</span></span>

- [<span data-ttu-id="67fc7-113">Paso 2: habilitar el acceso con privilegios</span><span class="sxs-lookup"><span data-stu-id="67fc7-113">Step 2: Enable privileged access</span></span>](privileged-access-management-configuration.md#step2)

    <span data-ttu-id="67fc7-114">El acceso con privilegios debe estar habilitado explícitamente en Office 365 con el grupo de aprobador predeterminado, incluido un conjunto de cuentas del sistema que desea excluir del control de acceso privilegiado de la administración de acceso.</span><span class="sxs-lookup"><span data-stu-id="67fc7-114">Privileged access must be explicitly enabled in Office 365 with the default approver group, including a set of system accounts that you want excluded from the privileged access management access control.</span></span>

- [<span data-ttu-id="67fc7-115">Paso 3: crear una directiva de acceso</span><span class="sxs-lookup"><span data-stu-id="67fc7-115">Step 3: Create an access policy</span></span>](privileged-access-management-configuration.md#step3)

    <span data-ttu-id="67fc7-116">La creación de una directiva de aprobación permite definir los requisitos de aprobación específicos en el ámbito de tareas individuales.</span><span class="sxs-lookup"><span data-stu-id="67fc7-116">Creating an approval policy allows you to define the specific approval requirements scoped at individual tasks.</span></span> <span data-ttu-id="67fc7-117">Las opciones de tipo de aprobación son **auto** o **manual**.</span><span class="sxs-lookup"><span data-stu-id="67fc7-117">The approval type options are **Auto** or **Manual**.</span></span>

- [<span data-ttu-id="67fc7-118">Paso 4: enviar o aprobar solicitudes de acceso privilegiadas</span><span class="sxs-lookup"><span data-stu-id="67fc7-118">Step 4: Submit/approve privileged access requests</span></span>](privileged-access-management-configuration.md#step4)

    <span data-ttu-id="67fc7-119">Una vez habilitado, el acceso con privilegios requiere aprobaciones para cualquier tarea que tenga definida una directiva de aprobación asociada.</span><span class="sxs-lookup"><span data-stu-id="67fc7-119">Once enabled, privileged access requires approvals for any task that has an associated approval policy defined.</span></span> <span data-ttu-id="67fc7-120">Para las tareas incluidas en una directiva de aprobación, los usuarios deben solicitar y recibir la aprobación de acceso para disponer de los permisos necesarios para ejecutar la tarea.</span><span class="sxs-lookup"><span data-stu-id="67fc7-120">For tasks included in an approval policy, users must request and be granted access approval to have permissions necessary to execute the task.</span></span>

<span data-ttu-id="67fc7-121">Una vez que se haya concedido la aprobación, el usuario que realiza la solicitud puede ejecutar la tarea deseada y el acceso privilegiado autorizará y ejecutará la tarea en nombre del usuario.</span><span class="sxs-lookup"><span data-stu-id="67fc7-121">After approval is granted, the requesting user can execute the intended task and privileged access will authorize and execute the task on behalf of the user.</span></span> <span data-ttu-id="67fc7-122">La aprobación sigue siendo válida durante la duración solicitada (la duración predeterminada es de 4 horas), durante el cual el solicitante puede ejecutar la tarea deseada varias veces.</span><span class="sxs-lookup"><span data-stu-id="67fc7-122">The approval remains valid for the requested duration (default duration is 4 hours), during which the requester can execute the intended task multiple times.</span></span> <span data-ttu-id="67fc7-123">Todas estas ejecuciones se registran y están disponibles para la auditoría de seguridad y cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="67fc7-123">All such executions are logged and made available for security and compliance auditing.</span></span> 

> [!NOTE]
> <span data-ttu-id="67fc7-124">Si desea usar el PowerShell de administración de Exchange para habilitar y configurar el acceso con privilegios, siga los pasos descritos en [Connect to Exchange Online PowerShell Using multi-factor Authentication](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/mfa-connect-to-exchange-online-powershell?view=exchange-ps) to Connect to Exchange Online PowerShell with your Office 365 necesarias.</span><span class="sxs-lookup"><span data-stu-id="67fc7-124">If you want to use Exchange Management PowerShell to enable and configure privileged access, follow the steps in [Connect to Exchange Online PowerShell using Multi-Factor authentication](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/mfa-connect-to-exchange-online-powershell?view=exchange-ps) to connect to Exchange Online PowerShell with your Office 365 credentials.</span></span> <span data-ttu-id="67fc7-125">No es necesario habilitar la autenticación multifactor para su organización de Office 365 para usar los pasos para habilitar el acceso privilegiado mientras se conecta a Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="67fc7-125">You do not need to enable multi-factor authentication for your Office 365 organization to use the steps to enable privileged access while connecting to Exchange Online PowerShell.</span></span> <span data-ttu-id="67fc7-126">La conexión con la autenticación multifactor crea un token de OAuth que se usa en el acceso con privilegios para firmar las solicitudes.</span><span class="sxs-lookup"><span data-stu-id="67fc7-126">Connecting with multi-factor authentication creates an OAuth token that is used by privileged access for signing your requests.</span></span>

<span data-ttu-id="67fc7-127"><a name="step1"> </a></span><span class="sxs-lookup"><span data-stu-id="67fc7-127"></span></span>

## <a name="step-1-create-an-approvers-group"></a><span data-ttu-id="67fc7-128">Paso 1: crear un grupo de aprobadores</span><span class="sxs-lookup"><span data-stu-id="67fc7-128">Step 1: Create an approver's group</span></span>

1. <span data-ttu-id="67fc7-129">Inicie sesión en el [centro de administración de Microsoft 365](https://admin.microsoft.com) con las credenciales de una cuenta de administrador en la organización.</span><span class="sxs-lookup"><span data-stu-id="67fc7-129">Sign into the [Microsoft 365 Admin Center](https://admin.microsoft.com) using credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="67fc7-130">En el centro de administración, vaya a **grupos** > **Agregar un grupo**.</span><span class="sxs-lookup"><span data-stu-id="67fc7-130">In the Admin Center, go to **Groups** > **Add a group**.</span></span>

3. <span data-ttu-id="67fc7-131">Seleccione **grupo de seguridad habilitado para correo** y, a continuación, complete los campos **nombre**, **dirección de correo electrónico de grupo**y **Descripción** para el nuevo grupo.</span><span class="sxs-lookup"><span data-stu-id="67fc7-131">Select **mail-enabled security group** and then complete the **Name**, **Group email address**, and **Description** fields for the new group.</span></span>

4. <span data-ttu-id="67fc7-132">Guarde el grupo.</span><span class="sxs-lookup"><span data-stu-id="67fc7-132">Save the group.</span></span> <span data-ttu-id="67fc7-133">Puede tardar unos minutos para que el grupo esté totalmente configurado y aparezca en el centro de administración de 365 de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="67fc7-133">It may take a few minutes for the group to be fully configured and to appear in the Microsoft 365 admin center.</span></span>

5. <span data-ttu-id="67fc7-134">Seleccione el grupo del nuevo aprobador y seleccione **Editar** para agregar usuarios al grupo.</span><span class="sxs-lookup"><span data-stu-id="67fc7-134">Select the new approver's group and select **edit** to add users to the group.</span></span>

6. <span data-ttu-id="67fc7-135">Guarde el grupo.</span><span class="sxs-lookup"><span data-stu-id="67fc7-135">Save the group.</span></span>

<span data-ttu-id="67fc7-136"><a name="step2"> </a></span><span class="sxs-lookup"><span data-stu-id="67fc7-136"></span></span>

## <a name="step-2-enable-privileged-access"></a><span data-ttu-id="67fc7-137">Paso 2: habilitar el acceso con privilegios</span><span class="sxs-lookup"><span data-stu-id="67fc7-137">Step 2: Enable privileged access</span></span>

### <a name="in-the-microsoft-365-admin-center"></a><span data-ttu-id="67fc7-138">En el centro de administración de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="67fc7-138">In the Microsoft 365 Admin Center</span></span>

1. <span data-ttu-id="67fc7-139">Inicie sesión en el [centro de administración de Microsoft 365](https://admin.microsoft.com) con las credenciales de una cuenta de administrador en la organización.</span><span class="sxs-lookup"><span data-stu-id="67fc7-139">Sign into the [Microsoft 365 Admin Center](https://admin.microsoft.com) using credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="67fc7-140">En el centro de administración, vaya a **configuración > seguridad** > de**privilegios**de privacidad &.</span><span class="sxs-lookup"><span data-stu-id="67fc7-140">In the Admin Center, go to **Settings > Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="67fc7-141">Habilite el control **de acceso requerir aprobaciones para privilegios** .</span><span class="sxs-lookup"><span data-stu-id="67fc7-141">Enable the **Require approvals for privileged access** control.</span></span>

4. <span data-ttu-id="67fc7-142">Asigne el grupo de aprobador que ha creado en el paso 1 como el **Grupo aprobadores**predeterminados.</span><span class="sxs-lookup"><span data-stu-id="67fc7-142">Assign the approver's group you created in Step 1 as the **Default approvers group**.</span></span>

5. <span data-ttu-id="67fc7-143">**Guarde** y **cierre**.</span><span class="sxs-lookup"><span data-stu-id="67fc7-143">**Save** and **Close**.</span></span>

### <a name="in-exchange-management-powershell"></a><span data-ttu-id="67fc7-144">En Exchange Management PowerShell</span><span class="sxs-lookup"><span data-stu-id="67fc7-144">In Exchange Management PowerShell</span></span>

<span data-ttu-id="67fc7-145">Para habilitar el acceso privilegiado y asignar el grupo del aprobador, ejecute el siguiente comando en Exchange Online PowerShell:</span><span class="sxs-lookup"><span data-stu-id="67fc7-145">To enable privileged access and to assign the approver's group, run the following command in Exchange Online PowerShell:</span></span>
```
Enable-ElevatedAccessControl -AdminGroup '<default approver group>' -SystemAccounts @('<systemAccountUPN1>','<systemAccountUPN2>')
```
<span data-ttu-id="67fc7-146">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="67fc7-146">Example:</span></span>
```
Enable-ElevatedAccessControl -AdminGroup 'pamapprovers@fabrikam.onmicrosoft.com' -SystemAccounts @('sys1@fabrikamorg.onmicrosoft.com', sys2@fabrikamorg.onmicrosoft.com')
```

> [!NOTE]
> <span data-ttu-id="67fc7-147">La característica cuentas del sistema está disponible para garantizar que determinadas automatización de las organizaciones puedan funcionar sin dependencia en el acceso con privilegios, pero se recomienda que esas exclusiones sean excepcionales y que se puedan aprobar y auditar. periódicamente.</span><span class="sxs-lookup"><span data-stu-id="67fc7-147">System accounts feature is made available to ensure certain automations within your organizations can work without dependency on privileged access, however it is recommended that such exclusions be exceptional and those allowed should be approved and audited regularly.</span></span>

<span data-ttu-id="67fc7-148"><a name="step3"> </a></span><span class="sxs-lookup"><span data-stu-id="67fc7-148"></span></span>

## <a name="step-3-create-an-access-policy"></a><span data-ttu-id="67fc7-149">Paso 3: crear una directiva de acceso</span><span class="sxs-lookup"><span data-stu-id="67fc7-149">Step 3: Create an access policy</span></span>

<span data-ttu-id="67fc7-150">Puede crear y configurar hasta 30 directivas de acceso privilegiadas para su organización de Office 365.</span><span class="sxs-lookup"><span data-stu-id="67fc7-150">You can create and configure up to 30 privileged access policies for your Office 365 organization.</span></span>

### <a name="in-the-microsoft-365-admin-center"></a><span data-ttu-id="67fc7-151">En el centro de administración de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="67fc7-151">In the Microsoft 365 Admin Center</span></span>

1. <span data-ttu-id="67fc7-152">Inicie sesión en el [centro de administración de Microsoft 365](https://admin.microsoft.com) con las credenciales de una cuenta de administrador en la organización.</span><span class="sxs-lookup"><span data-stu-id="67fc7-152">Sign into the [Microsoft 365 Admin Center](https://admin.microsoft.com) using credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="67fc7-153">En el centro de administración, vaya a **configuración** > **seguridad &** > **acceso privilegiado a**la privacidad.</span><span class="sxs-lookup"><span data-stu-id="67fc7-153">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="67fc7-154">Seleccione **Administrar directivas y solicitudes de acceso**.</span><span class="sxs-lookup"><span data-stu-id="67fc7-154">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="67fc7-155">Seleccione **configurar directivas** y seleccione **Agregar una directiva**.</span><span class="sxs-lookup"><span data-stu-id="67fc7-155">Select **Configure policies** and select **Add a policy**.</span></span>

5. <span data-ttu-id="67fc7-156">En los campos desplegables, seleccione los valores adecuados para su organización:</span><span class="sxs-lookup"><span data-stu-id="67fc7-156">From the drop-down fields, select the appropriate values for your organization:</span></span>
    
    <span data-ttu-id="67fc7-157">**Tipo de directiva**: tarea, rol o grupo de roles</span><span class="sxs-lookup"><span data-stu-id="67fc7-157">**Policy type**: Task, Role, or Role Group</span></span>

    <span data-ttu-id="67fc7-158">**Ámbito de directiva**: Exchange</span><span class="sxs-lookup"><span data-stu-id="67fc7-158">**Policy scope**: Exchange</span></span>

    <span data-ttu-id="67fc7-159">**Nombre de directiva**: Seleccione una de las directivas disponibles</span><span class="sxs-lookup"><span data-stu-id="67fc7-159">**Policy name**: Select from the available policies</span></span>

    <span data-ttu-id="67fc7-160">**Tipo de aprobación**: manual o automático</span><span class="sxs-lookup"><span data-stu-id="67fc7-160">**Approval type**: Manual or Auto</span></span>

    <span data-ttu-id="67fc7-161">**Grupo de aprobación**: seleccione el grupo aprobadores creado en el paso 1.</span><span class="sxs-lookup"><span data-stu-id="67fc7-161">**Approval group**: Select the approvers group created in Step 1</span></span>

6. <span data-ttu-id="67fc7-162">Seleccione **crear** y, a continuación, **cerrar**.</span><span class="sxs-lookup"><span data-stu-id="67fc7-162">Select **Create** and then **Close**.</span></span> <span data-ttu-id="67fc7-163">La Directiva puede tardar unos minutos en estar totalmente configurada y habilitada.</span><span class="sxs-lookup"><span data-stu-id="67fc7-163">It may take a few minutes for the policy to be fully configured and enabled.</span></span>

### <a name="in-exchange-management-powershell"></a><span data-ttu-id="67fc7-164">En Exchange Management PowerShell</span><span class="sxs-lookup"><span data-stu-id="67fc7-164">In Exchange Management PowerShell</span></span>

<span data-ttu-id="67fc7-165">Para crear y definir una directiva de aprobación, ejecute el siguiente comando en Exchange Online PowerShell:</span><span class="sxs-lookup"><span data-stu-id="67fc7-165">To create and define an approval policy, run the following command in Exchange Online PowerShell:</span></span>

```
New-ElevatedAccessApprovalPolicy -Task 'Exchange\<exchange management cmdlet name>' -ApprovalType <Manual, Auto> -ApproverGroup '<default/custom approver group>'
```
<span data-ttu-id="67fc7-166">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="67fc7-166">Example:</span></span>
```
New-ElevatedAccessApprovalPolicy -Task 'Exchange\New-MoveRequest' -ApprovalType Manual -ApproverGroup 'mbmanagers@fabrikamorg.onmicrosoft.com'
```

<span data-ttu-id="67fc7-167"><a name="step4"> </a></span><span class="sxs-lookup"><span data-stu-id="67fc7-167"></span></span>

## <a name="step-4-submitapprove-privileged-access-requests"></a><span data-ttu-id="67fc7-168">Paso 4: enviar o aprobar solicitudes de acceso privilegiadas</span><span class="sxs-lookup"><span data-stu-id="67fc7-168">Step 4: Submit/approve privileged access requests</span></span>

### <a name="requesting-elevation-authorization-to-execute-privileged-tasks"></a><span data-ttu-id="67fc7-169">Solicitar autorización de elevación para ejecutar tareas privilegiadas</span><span class="sxs-lookup"><span data-stu-id="67fc7-169">Requesting elevation authorization to execute privileged tasks</span></span>

<span data-ttu-id="67fc7-170">Las solicitudes de acceso con privilegios son válidas durante un máximo de 24 horas después de que se envíe la solicitud.</span><span class="sxs-lookup"><span data-stu-id="67fc7-170">Requests for privileged access are valid for up to 24 hours after the request is submitted.</span></span> <span data-ttu-id="67fc7-171">Si no se aprueba o se rechaza, las solicitudes expiran y el acceso no se aprueba.</span><span class="sxs-lookup"><span data-stu-id="67fc7-171">If not approved or denied, the requests expire and access is not approved.</span></span>

#### <a name="in-the-microsoft-365-admin-center"></a><span data-ttu-id="67fc7-172">En el centro de administración de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="67fc7-172">In the Microsoft 365 Admin Center</span></span>

1. <span data-ttu-id="67fc7-173">Inicie sesión en el [centro de administración de Microsoft 365](https://admin.microsoft.com) con sus credenciales.</span><span class="sxs-lookup"><span data-stu-id="67fc7-173">Sign into the [Microsoft 365 Admin Center](https://admin.microsoft.com) using your credentials.</span></span>

2. <span data-ttu-id="67fc7-174">En el centro de administración, vaya a **configuración** > **seguridad &** > **acceso privilegiado a**la privacidad.</span><span class="sxs-lookup"><span data-stu-id="67fc7-174">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="67fc7-175">Seleccione **Administrar directivas y solicitudes de acceso**.</span><span class="sxs-lookup"><span data-stu-id="67fc7-175">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="67fc7-176">Seleccione **nueva solicitud**.</span><span class="sxs-lookup"><span data-stu-id="67fc7-176">Select **New request**.</span></span> <span data-ttu-id="67fc7-177">En los campos desplegables, seleccione los valores adecuados para su organización:</span><span class="sxs-lookup"><span data-stu-id="67fc7-177">From the drop-down fields, select the appropriate values for your organization:</span></span>

    <span data-ttu-id="67fc7-178">**Tipo de solicitud**: tarea, rol o grupo de roles</span><span class="sxs-lookup"><span data-stu-id="67fc7-178">**Request type**: Task, Role, or Role Group</span></span>

    <span data-ttu-id="67fc7-179">**Ámbito de solicitud**: Exchange</span><span class="sxs-lookup"><span data-stu-id="67fc7-179">**Request scope**: Exchange</span></span>

    <span data-ttu-id="67fc7-180">**Solicitud de**: Seleccione una de las directivas disponibles</span><span class="sxs-lookup"><span data-stu-id="67fc7-180">**Request for**: Select from the available policies</span></span>

    <span data-ttu-id="67fc7-181">**Duración (horas)**: número de horas de acceso solicitado.</span><span class="sxs-lookup"><span data-stu-id="67fc7-181">**Duration (hours)**: Number of hours of requested access.</span></span> <span data-ttu-id="67fc7-182">No hay un límite en el número de horas que se puede solicitar.</span><span class="sxs-lookup"><span data-stu-id="67fc7-182">There isn't a limit on the number of hours that can be requested.</span></span>

    <span data-ttu-id="67fc7-183">**Comentarios**: campo de texto para comentarios relacionados con la solicitud de acceso</span><span class="sxs-lookup"><span data-stu-id="67fc7-183">**Comments**: Text field for comments related to your access request</span></span>

5. <span data-ttu-id="67fc7-184">Seleccione **Guardar** y, a continuación, **cerrar**.</span><span class="sxs-lookup"><span data-stu-id="67fc7-184">Select **Save** and then **Close**.</span></span> <span data-ttu-id="67fc7-185">La solicitud se enviará al grupo del aprobador a través del correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="67fc7-185">Your request will be sent to the approver's group via email.</span></span>

#### <a name="in-exchange-management-powershell"></a><span data-ttu-id="67fc7-186">En Exchange Management PowerShell</span><span class="sxs-lookup"><span data-stu-id="67fc7-186">In Exchange Management PowerShell</span></span>

<span data-ttu-id="67fc7-187">Ejecute el siguiente comando en Exchange Online PowerShell para crear y enviar una solicitud de aprobación al grupo del aprobador:</span><span class="sxs-lookup"><span data-stu-id="67fc7-187">Run the following command in Exchange Online PowerShell to create and submit an approval request to the approver's group:</span></span>
```
New-ElevatedAccessRequest -Task 'Exchange\<exchange management cmdlet name>' -Reason '<appropriate reason>' -DurationHours <duration in hours>
```
<span data-ttu-id="67fc7-188">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="67fc7-188">Example:</span></span>
```
New-ElevatedAccessRequest -Task 'Exchange\New-MoveRequest' -Reason 'Attempting to fix the user mailbox error' -DurationHours 4
```
### <a name="view-status-of-elevation-requests"></a><span data-ttu-id="67fc7-189">Ver el estado de las solicitudes de elevación</span><span class="sxs-lookup"><span data-stu-id="67fc7-189">View status of elevation requests</span></span>
<span data-ttu-id="67fc7-190">Después de crear una solicitud de aprobación, el estado de la solicitud de elevación se puede revisar en el centro de administración o en PowerShell de administración de Exchange con el identificador de solicitud asociado.</span><span class="sxs-lookup"><span data-stu-id="67fc7-190">After an approval request is created, elevation request status can be reviewed in the admin center or in Exchange Management PowerShell using the associated with request ID.</span></span>

#### <a name="in-the-microsoft-365-admin-center"></a><span data-ttu-id="67fc7-191">En el centro de administración de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="67fc7-191">In the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="67fc7-192">Inicie sesión en el [centro de administración de Microsoft 365](https://admin.microsoft.com) con sus credenciales.</span><span class="sxs-lookup"><span data-stu-id="67fc7-192">Sign into the [Microsoft 365 admin center](https://admin.microsoft.com) with your credentials.</span></span>

2. <span data-ttu-id="67fc7-193">En el centro de administración, vaya a **configuración** > **seguridad &** > **acceso privilegiado a**la privacidad.</span><span class="sxs-lookup"><span data-stu-id="67fc7-193">In the admin center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="67fc7-194">Seleccione **Administrar directivas y solicitudes de acceso**.</span><span class="sxs-lookup"><span data-stu-id="67fc7-194">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="67fc7-195">Seleccione **Ver** para filtrar las solicitudes enviadas por estado **pendiente**, **aprobado**, deNegado o de caja de **caja del cliente** . \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="67fc7-195">Select **View** to filter submitted requests by **Pending**, **Approved**, **Denied**, or **Customer Lockbox** status.</span></span>

#### <a name="in-exchange-management-powershell"></a><span data-ttu-id="67fc7-196">En Exchange Management PowerShell</span><span class="sxs-lookup"><span data-stu-id="67fc7-196">In Exchange Management PowerShell</span></span>

<span data-ttu-id="67fc7-197">Ejecute el siguiente comando en Exchange Online PowerShell para ver el estado de la solicitud de aprobación de un identificador de solicitud específico:</span><span class="sxs-lookup"><span data-stu-id="67fc7-197">Run the following command in Exchange Online PowerShell to view an approval request status for a specific request ID:</span></span>
```
Get-ElevatedAccessRequest -Identity <request ID> | select RequestStatus
```
<span data-ttu-id="67fc7-198">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="67fc7-198">Example:</span></span>
```
Get-ElevatedAccessRequest -Identity 28560ed0-419d-4cc3-8f5b-603911cbd450 | select RequestStatus
```

### <a name="approving-an-elevation-authorization-request"></a><span data-ttu-id="67fc7-199">Aprobación de una solicitud de autorización de elevación</span><span class="sxs-lookup"><span data-stu-id="67fc7-199">Approving an elevation authorization request</span></span>
<span data-ttu-id="67fc7-200">Cuando se crea una solicitud de aprobación, los miembros del grupo aprobador relevante reciben una notificación por correo electrónico y pueden aprobar la solicitud asociada con el identificador de solicitud.</span><span class="sxs-lookup"><span data-stu-id="67fc7-200">When an approval request is created, members of the relevant approver group receive an email notification and can approve the request associated with the request ID.</span></span> <span data-ttu-id="67fc7-201">El solicitante recibe la notificación de la aprobación o la denegación de la solicitud mediante un mensaje de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="67fc7-201">The requestor is notified of the request approval or denial via email message.</span></span>

#### <a name="in-the-microsoft-365-admin-center"></a><span data-ttu-id="67fc7-202">En el centro de administración de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="67fc7-202">In the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="67fc7-203">Inicie sesión en el [centro de administración de Microsoft 365](https://admin.microsoft.com) con sus credenciales.</span><span class="sxs-lookup"><span data-stu-id="67fc7-203">Sign into the [Microsoft 365 admin center](https://admin.microsoft.com) with your credentials.</span></span>

2. <span data-ttu-id="67fc7-204">En el centro de administración, vaya a **configuración** > **seguridad &** > **acceso privilegiado a**la privacidad.</span><span class="sxs-lookup"><span data-stu-id="67fc7-204">In the admin center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="67fc7-205">Seleccione **Administrar directivas y solicitudes de acceso**.</span><span class="sxs-lookup"><span data-stu-id="67fc7-205">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="67fc7-206">Seleccione una solicitud de la lista para ver los detalles y realizar la acción en la solicitud.</span><span class="sxs-lookup"><span data-stu-id="67fc7-206">Select a listed request to view the details and to take action on the request.</span></span>

5. <span data-ttu-id="67fc7-207">Seleccione **aprobar** para aprobar la solicitud o seleccione **denegar** para denegar la solicitud.</span><span class="sxs-lookup"><span data-stu-id="67fc7-207">Select **Approve** to approve the request or select **Deny** to deny the request.</span></span> <span data-ttu-id="67fc7-208">Las solicitudes aprobadas anteriormente pueden revocar el acceso mediante la selección de **REVOKE**.</span><span class="sxs-lookup"><span data-stu-id="67fc7-208">Previously approved requests can have access revoked by selecting **Revoke**.</span></span>

#### <a name="in-exchange-management-powershell"></a><span data-ttu-id="67fc7-209">En Exchange Management PowerShell</span><span class="sxs-lookup"><span data-stu-id="67fc7-209">In Exchange Management PowerShell</span></span>

<span data-ttu-id="67fc7-210">Para aprobar una solicitud de autorización de elevación, ejecute el siguiente comando en Exchange Online PowerShell:</span><span class="sxs-lookup"><span data-stu-id="67fc7-210">To approve an elevation authorization request, run the following command in Exchange Online PowerShell:</span></span>

```
Approve-ElevatedAccessRequest -RequestId <request id> -Comment '<approval comment>'
```
<span data-ttu-id="67fc7-211">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="67fc7-211">Example:</span></span>
```
Approve-ElevatedAccessRequest -RequestId a4bc1bdf-00a1-42b4-be65-b6c63d6be279 -Comment '<approval comment>'
```

<span data-ttu-id="67fc7-212">Para denegar una solicitud de autorización de elevación, ejecute el siguiente comando en Exchange Online PowerShell:</span><span class="sxs-lookup"><span data-stu-id="67fc7-212">To deny an elevation authorization request, run the following command in Exchange Online PowerShell:</span></span>

```
Deny-ElevatedAccessRequest -RequestId <request id> -Comment '<denial comment>'
```
<span data-ttu-id="67fc7-213">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="67fc7-213">Example:</span></span>
```
Deny-ElevatedAccessRequest -RequestId a4bc1bdf-00a1-42b4-be65-b6c63d6be279 -Comment '<denial comment>'
```

## <a name="delete-a-privileged-access-policy-in-office-365"></a><span data-ttu-id="67fc7-214">Eliminar una directiva de acceso privilegiada en Office 365</span><span class="sxs-lookup"><span data-stu-id="67fc7-214">Delete a privileged access policy in Office 365</span></span>
<span data-ttu-id="67fc7-215">Si ya no es necesario en su organización, puede eliminar una directiva de acceso privilegiado.</span><span class="sxs-lookup"><span data-stu-id="67fc7-215">If it is no longer needed in your organization, you can delete a privileged access policy.</span></span>

### <a name="in-the-microsoft-365-admin-center"></a><span data-ttu-id="67fc7-216">En el centro de administración de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="67fc7-216">In the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="67fc7-217">Inicie sesión en el [centro de administración de Microsoft 365](https://admin.microsoft.com) con las credenciales de una cuenta de administrador en la organización.</span><span class="sxs-lookup"><span data-stu-id="67fc7-217">Sign into the [Microsoft 365 admin center](https://admin.microsoft.com) using credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="67fc7-218">En el centro de administración, vaya a **configuración** > **seguridad &** > **acceso privilegiado a**la privacidad.</span><span class="sxs-lookup"><span data-stu-id="67fc7-218">In the admin center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="67fc7-219">Seleccione **Administrar directivas y solicitudes de acceso**.</span><span class="sxs-lookup"><span data-stu-id="67fc7-219">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="67fc7-220">Seleccione **configurar directivas**.</span><span class="sxs-lookup"><span data-stu-id="67fc7-220">Select **Configure policies**.</span></span>

5. <span data-ttu-id="67fc7-221">Seleccione la Directiva que desea eliminar y, a continuación, seleccione **quitar Directiva**.</span><span class="sxs-lookup"><span data-stu-id="67fc7-221">Select the policy you want to delete, then select **Remove Policy**.</span></span>

6. <span data-ttu-id="67fc7-222">Seleccione **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="67fc7-222">Select **Close**.</span></span>

### <a name="in-exchange-management-powershell"></a><span data-ttu-id="67fc7-223">En Exchange Management PowerShell</span><span class="sxs-lookup"><span data-stu-id="67fc7-223">In Exchange Management PowerShell</span></span>

<span data-ttu-id="67fc7-224">Para eliminar una directiva de acceso privilegiada, ejecute el siguiente comando en Exchange Online PowerShell:</span><span class="sxs-lookup"><span data-stu-id="67fc7-224">To delete a privileged access policy, run the following command in Exchange Online Powershell:</span></span>

```
Remove-ElevatedAccessApprovalPolicy -Identity <identity GUID of the policy you want to delete>
```

## <a name="disable-privileged-access-in-office-365"></a><span data-ttu-id="67fc7-225">DesHabilitar el acceso privilegiado en Office 365</span><span class="sxs-lookup"><span data-stu-id="67fc7-225">Disable privileged access in Office 365</span></span>

<span data-ttu-id="67fc7-226">Si es necesario, puede deshabilitar la administración del acceso con privilegios para su organización.</span><span class="sxs-lookup"><span data-stu-id="67fc7-226">If needed, you can disable privileged access management for your organization.</span></span> <span data-ttu-id="67fc7-227">La desHabilitación del acceso con privilegios no elimina ninguna directiva de aprobación o grupo de aprobador asociado.</span><span class="sxs-lookup"><span data-stu-id="67fc7-227">Disabling privileged access does not delete any associated approval policies or approver groups.</span></span>

### <a name="in-the-microsoft-365-admin-center"></a><span data-ttu-id="67fc7-228">En el centro de administración de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="67fc7-228">In the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="67fc7-229">Inicie sesión en el [centro de administración de Microsoft 365](https://admin.microsoft.com) con las credenciales de una cuenta de administrador en la organización.</span><span class="sxs-lookup"><span data-stu-id="67fc7-229">Sign into the [Microsoft 365 admin center](https://admin.microsoft.com) with credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="67fc7-230">En el centro de administración, vaya a **configuración** > **seguridad &** > **acceso privilegiado a**la privacidad.</span><span class="sxs-lookup"><span data-stu-id="67fc7-230">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="67fc7-231">Habilite el control **de acceso requerir aprobaciones para privilegios** .</span><span class="sxs-lookup"><span data-stu-id="67fc7-231">Enable the **Require approvals for privileged access** control.</span></span>

### <a name="in-exchange-management-powershell"></a><span data-ttu-id="67fc7-232">En Exchange Management PowerShell</span><span class="sxs-lookup"><span data-stu-id="67fc7-232">In Exchange Management PowerShell</span></span>

<span data-ttu-id="67fc7-233">Para deshabilitar el acceso privilegiado, ejecute el siguiente comando en Exchange Online PowerShell:</span><span class="sxs-lookup"><span data-stu-id="67fc7-233">To disable privileged access, run the following command in Exchange Online Powershell:</span></span>

```
Disable-ElevatedAccessControl
```