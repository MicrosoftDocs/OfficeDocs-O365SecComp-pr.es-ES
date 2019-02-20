---
title: Configuración de la administración del acceso con privilegios en Office 365
ms.author: robmazz
author: robmazz
manager: laurawi
ms.audience: ITPro
ms.topic: overview
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
ms.custom: Ent_Solutions
ms.assetid: ''
description: Use este tema para obtener más información sobre cómo configurar la administración del acceso con privilegios en Office 365
ms.openlocfilehash: 63780da59afb245b35916a1e7a5b2eb780d535a8
ms.sourcegitcommit: c94cb88a9ce5bcc2d3c558f0fcc648519cc264a2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/20/2019
ms.locfileid: "30090922"
---
# <a name="configuring-privileged-access-management-in-office-365"></a><span data-ttu-id="d90bf-103">Configuración de la administración del acceso con privilegios en Office 365</span><span class="sxs-lookup"><span data-stu-id="d90bf-103">Configuring privileged access management in Office 365</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d90bf-104">En este tema se tratan las instrucciones de implementación y configuración de las características disponibles actualmente en Office 365 E5 y las SKU de cumplimiento avanzado.</span><span class="sxs-lookup"><span data-stu-id="d90bf-104">This topic covers deployment and configuration guidance for features only currently available in Office 365 E5 and Advanced Compliance SKUs.</span></span>

<span data-ttu-id="d90bf-p101">Este tema le guiará a través de la habilitación y configuración de la administración del acceso con privilegios en su organización de Office 365. Puede usar tanto el centro de administración de Microsoft 365 como PowerShell de administración de Exchange para administrar y usar el acceso con privilegios.</span><span class="sxs-lookup"><span data-stu-id="d90bf-p101">This topic will guide you through enabling and configuring privileged access management in your Office 365 organization. You can use either the Microsoft 365 Admin Center or Exchange Management PowerShell to manage and use privileged access.</span></span> 

## <a name="enable-and-configure-privileged-access-management"></a><span data-ttu-id="d90bf-107">Habilitación y configuración de la administración del acceso con privilegios</span><span class="sxs-lookup"><span data-stu-id="d90bf-107">Enable and configure privileged access management</span></span>

<span data-ttu-id="d90bf-108">Siga estos pasos para configurar y usar el acceso con privilegios en su organización de Office 365:</span><span class="sxs-lookup"><span data-stu-id="d90bf-108">Follow these steps to set up and use privileged access in your Office 365 organization:</span></span>

- [<span data-ttu-id="d90bf-109">Paso 1: crear un grupo de aprobadores</span><span class="sxs-lookup"><span data-stu-id="d90bf-109">Step 1: Create an approver's group</span></span>](privileged-access-management-configuration.md#step1)

    <span data-ttu-id="d90bf-p102">Antes de empezar a usar el acceso de privilegios, determine quién tendrá autoridad de aprobación para el acceso a las tareas elevadas y privilegiadas. Cualquier usuario que forme parte del grupo de aprobadores podrá aprobar solicitudes de acceso. Para habilitarlo, cree un grupo de seguridad habilitado para correo en Office 365.</span><span class="sxs-lookup"><span data-stu-id="d90bf-p102">Before you start using privilege access, determine who will have approval authority for incoming requests for access to elevated and privileged tasks. Any user who is part of the Approvers’ group will be able to approve access requests. This is enabled by creating a mail-enabled security group in Office 365.</span></span>

- [<span data-ttu-id="d90bf-113">Paso 2: habilitar el acceso con privilegios</span><span class="sxs-lookup"><span data-stu-id="d90bf-113">Step 2: Enable privileged access</span></span>](privileged-access-management-configuration.md#step2)

    <span data-ttu-id="d90bf-114">El acceso privilegiado debe estar activado explícitamente en Office 365 con el grupo de aprobador predeterminado e incluir un conjunto de cuentas del sistema que se desea excluir del control de acceso privilegiado de la administración de acceso.</span><span class="sxs-lookup"><span data-stu-id="d90bf-114">Privileged access needs to be explicitly turned on in Office 365 with the default approver group and including a set of system accounts that you’d want to be excluded from the privileged access management access control.</span></span>

- [<span data-ttu-id="d90bf-115">Paso 3: crear una directiva de acceso</span><span class="sxs-lookup"><span data-stu-id="d90bf-115">Step 3: Create an access policy</span></span>](privileged-access-management-configuration.md#step3)

    <span data-ttu-id="d90bf-p103">La creación de una directiva de aprobación permite definir los requisitos de aprobación específicos en el ámbito de tareas individuales. Las opciones de tipo de aprobación son **auto** o **manual**.</span><span class="sxs-lookup"><span data-stu-id="d90bf-p103">Creating an approval policy allows you to define the specific approval requirements scoped at individual tasks. The approval type options are **Auto** or **Manual**.</span></span>

- [<span data-ttu-id="d90bf-118">Paso 4: enviar o aprobar solicitudes de acceso privilegiadas</span><span class="sxs-lookup"><span data-stu-id="d90bf-118">Step 4: Submit/approve privileged access requests</span></span>](privileged-access-management-configuration.md#step4)

    <span data-ttu-id="d90bf-p104">Una vez habilitado, el acceso con privilegios necesita aprobaciones para ejecutar cualquier tarea que tenga definida una directiva de aprobación asociada. Los usuarios que necesiten ejecutar tareas incluidas en la Directiva de aprobación deben solicitar y tener la aprobación de acceso para disponer de los permisos necesarios para ejecutar la tarea.</span><span class="sxs-lookup"><span data-stu-id="d90bf-p104">Once enabled, privileged access requires approvals for executing any task that has an associated approval policy defined. Users needing to execute tasks included in the an approval policy must request and be granted access approval in order to have permissions necessary to execute the task.</span></span>

<span data-ttu-id="d90bf-p105">Una vez concedida la aprobación, el usuario que realiza la solicitud puede ejecutar la tarea deseada y el acceso privilegiado autorizará y ejecutará la tarea en nombre de los usuarios. La aprobación sigue siendo válida durante la duración solicitada (la duración predeterminada es de 4 horas), durante el cual el solicitante puede ejecutar la tarea deseada varias veces. Todas estas ejecuciones se registran y están disponibles para la auditoría de seguridad y cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="d90bf-p105">After approval is granted, the requesting user can execute the intended task and privileged access will authorize and execute the task on users’ behalf. The approval remains valid for the requested duration (default duration is 4 hours), during which the requester can execute the intended task multiple times. All such executions are logged and made available for security and compliance auditing.</span></span> 

> [!NOTE]
> <span data-ttu-id="d90bf-p106">Si desea usar el PowerShell de administración de Exchange para habilitar y configurar el acceso con privilegios, siga los pasos descritos en [Connect to Exchange Online PowerShell Using multi-factor Authentication](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/mfa-connect-to-exchange-online-powershell?view=exchange-ps) to Connect to Exchange Online PowerShell with your Office 365 necesarias. No es necesario habilitar la autenticación multifactor para su organización de Office 365 para usar los pasos para habilitar el acceso privilegiado mientras se conecta a Exchange Online PowerShell. La conexión con la autenticación multifactor crea un token de OAuth que se usa en el acceso con privilegios para firmar las solicitudes.</span><span class="sxs-lookup"><span data-stu-id="d90bf-p106">If you want to use Exchange Management PowerShell to enable and configure privileged access, follow the steps in [Connect to Exchange Online PowerShell using Multi-Factor authentication](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/mfa-connect-to-exchange-online-powershell?view=exchange-ps) to connect to Exchange Online PowerShell with your Office 365 credentials. You do not need to enable multi-factor authentication for your Office 365 organization to use the steps to enable privileged access while connecting to Exchange Online PowerShell. Connecting with multi-factor authentication creates an OAuth token that is used by privileged access for signing your requests.</span></span>

<span data-ttu-id="d90bf-127"><a name="step1"> </a></span><span class="sxs-lookup"><span data-stu-id="d90bf-127"></span></span>

## <a name="step-1---create-an-approvers-group"></a><span data-ttu-id="d90bf-128">Paso 1: crear un grupo de aprobadores</span><span class="sxs-lookup"><span data-stu-id="d90bf-128">Step 1 - Create an approver's group</span></span>

1. <span data-ttu-id="d90bf-129">Inicie sesión en el [centro de administración de Microsoft 365](https://portal.office.com) con las credenciales de una cuenta de administrador en la organización.</span><span class="sxs-lookup"><span data-stu-id="d90bf-129">Sign into the [Microsoft 365 Admin Center](https://portal.office.com) using credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="d90bf-130">En el centro de administración, vaya a **grupos** > **Agregar un grupo**.</span><span class="sxs-lookup"><span data-stu-id="d90bf-130">In the Admin Center, go to **Groups** > **Add a group**.</span></span>

3. <span data-ttu-id="d90bf-131">Seleccione el tipo de grupo **grupo de seguridad habilitado para correo** y, a continuación, complete los campos **nombre**, **dirección de correo electrónico del grupo**y **Descripción** para el nuevo grupo.</span><span class="sxs-lookup"><span data-stu-id="d90bf-131">Select the **mail-enabled security group** group type and then complete the **Name**, **Group email address**, and **Description** fields for the new group.</span></span>

4. <span data-ttu-id="d90bf-p107">Guarde el grupo. El grupo puede tardar unos minutos en configurarse y aparecer completamente en el centro de administración de Office 365.</span><span class="sxs-lookup"><span data-stu-id="d90bf-p107">Save the group. It may take a few minutes for the group to be fully configured and to appear in the Office 365 Admin Center.</span></span>

5. <span data-ttu-id="d90bf-134">Seleccione el grupo del nuevo aprobador y seleccione **Editar** para agregar usuarios al grupo.</span><span class="sxs-lookup"><span data-stu-id="d90bf-134">Select the new approver's group and select **edit** to add users to the group.</span></span>

6. <span data-ttu-id="d90bf-135">Guarde el grupo.</span><span class="sxs-lookup"><span data-stu-id="d90bf-135">Save the group.</span></span>

<span data-ttu-id="d90bf-136"><a name="step2"> </a></span><span class="sxs-lookup"><span data-stu-id="d90bf-136"></span></span>

## <a name="step-2---enable-privileged-access"></a><span data-ttu-id="d90bf-137">Paso 2: habilitar el acceso con privilegios</span><span class="sxs-lookup"><span data-stu-id="d90bf-137">Step 2 - Enable privileged access</span></span>

### <a name="using-the-microsoft-365-admin-center"></a><span data-ttu-id="d90bf-138">Uso del centro de administración de 365 de Microsoft</span><span class="sxs-lookup"><span data-stu-id="d90bf-138">Using the Microsoft 365 Admin Center</span></span>

1. <span data-ttu-id="d90bf-139">Inicie sesión en el [centro de administración de Microsoft 365](https://portal.office.com) con las credenciales de una cuenta de administrador en la organización.</span><span class="sxs-lookup"><span data-stu-id="d90bf-139">Sign into the [Microsoft 365 Admin Center](https://portal.office.com) using credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="d90bf-140">En el centro de administración, vaya a **configuración > seguridad** > de**privilegios**de privacidad &.</span><span class="sxs-lookup"><span data-stu-id="d90bf-140">In the Admin Center, go to **Settings > Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="d90bf-141">Habilite el control **de acceso requerir aprobaciones para privilegios** .</span><span class="sxs-lookup"><span data-stu-id="d90bf-141">Enable the **Require approvals for privileged access** control.</span></span>

4. <span data-ttu-id="d90bf-142">Asigne el grupo de aprobador que ha creado en el paso 1 como el **Grupo aprobadores**predeterminados.</span><span class="sxs-lookup"><span data-stu-id="d90bf-142">Assign the approver's group you created in Step 1 as the **Default approvers group**.</span></span>

5. <span data-ttu-id="d90bf-143">**Guarde** y **cierre**.</span><span class="sxs-lookup"><span data-stu-id="d90bf-143">**Save** and **Close**.</span></span>

### <a name="using-exchange-management-powershell"></a><span data-ttu-id="d90bf-144">Uso de Exchange Management PowerShell</span><span class="sxs-lookup"><span data-stu-id="d90bf-144">Using Exchange Management PowerShell</span></span>

<span data-ttu-id="d90bf-145">Ejecute el siguiente comando en Exchange Online PowerShell para habilitar el acceso privilegiado y asignar el grupo del aprobador:</span><span class="sxs-lookup"><span data-stu-id="d90bf-145">Run the following command in Exchange Online PowerShell to enable privileged access and to assign the approver's group:</span></span>
```
Enable-ElevatedAccessControl -AdminGroup '<default approver group>' -SystemAccounts @('<systemAccountUPN1>','<systemAccountUPN2>')
```
<span data-ttu-id="d90bf-146">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="d90bf-146">Example:</span></span>
```
Enable-ElevatedAccessControl -AdminGroup 'pamapprovers@fabrikam.onmicrosoft.com' -SystemAccounts @('sys1@fabrikamorg.onmicrosoft.com', sys2@fabrikamorg.onmicrosoft.com')
```

> [!NOTE]
> <span data-ttu-id="d90bf-147">La característica cuentas del sistema está disponible para garantizar que determinadas automatización de las organizaciones puedan funcionar sin dependencia en el acceso con privilegios, pero se recomienda que esas exclusiones sean excepcionales y que se puedan aprobar y auditar. periódicamente.</span><span class="sxs-lookup"><span data-stu-id="d90bf-147">System accounts feature is made available to ensure certain automations within your organizations can work without dependency on privileged access, however it is recommended that such exclusions be exceptional and those allowed should be approved and audited regularly.</span></span>

<span data-ttu-id="d90bf-148"><a name="step3"> </a></span><span class="sxs-lookup"><span data-stu-id="d90bf-148"></span></span>

## <a name="step-3---create-an-access-policy"></a><span data-ttu-id="d90bf-149">Paso 3: crear una directiva de acceso</span><span class="sxs-lookup"><span data-stu-id="d90bf-149">Step 3 - Create an access policy</span></span>

<span data-ttu-id="d90bf-150">Puede crear y configurar hasta 30 directivas de acceso privilegiadas para su organización de Office 365.</span><span class="sxs-lookup"><span data-stu-id="d90bf-150">You can create and configure up to 30 privileged access policies for your Office 365 organization.</span></span>

### <a name="using-the-microsoft-365-admin-center"></a><span data-ttu-id="d90bf-151">Uso del centro de administración de 365 de Microsoft</span><span class="sxs-lookup"><span data-stu-id="d90bf-151">Using the Microsoft 365 Admin Center</span></span>

1. <span data-ttu-id="d90bf-152">Inicie sesión en el [centro de administración de Microsoft 365](https://portal.office.com) con las credenciales de una cuenta de administrador en la organización.</span><span class="sxs-lookup"><span data-stu-id="d90bf-152">Sign into the [Microsoft 365 Admin Center](https://portal.office.com) using credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="d90bf-153">En el centro de administración, vaya a **configuración** > **seguridad &** > **acceso privilegiado a**la privacidad.</span><span class="sxs-lookup"><span data-stu-id="d90bf-153">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="d90bf-154">Seleccione **Administrar directivas y solicitudes de acceso**.</span><span class="sxs-lookup"><span data-stu-id="d90bf-154">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="d90bf-155">Seleccione **configurar directivas** y seleccione **Agregar una directiva**.</span><span class="sxs-lookup"><span data-stu-id="d90bf-155">Select **Configure policies** and select **Add a policy**.</span></span>

5. <span data-ttu-id="d90bf-156">En los campos desplegables, seleccione los valores adecuados para su organización:</span><span class="sxs-lookup"><span data-stu-id="d90bf-156">From the drop-down fields, select the appropriate values for your organization:</span></span>
    
    <span data-ttu-id="d90bf-157">**Tipo de directiva**: tarea, rol o grupo de roles</span><span class="sxs-lookup"><span data-stu-id="d90bf-157">**Policy type**: Task, Role, or Role Group</span></span>

    <span data-ttu-id="d90bf-158">**Ámbito de directiva**: Exchange u Office 365</span><span class="sxs-lookup"><span data-stu-id="d90bf-158">**Policy scope**: Exchange or Office 365</span></span>

    <span data-ttu-id="d90bf-159">**Nombre de directiva**: Seleccione una de las directivas disponibles</span><span class="sxs-lookup"><span data-stu-id="d90bf-159">**Policy name**: Select from the available policies</span></span>

    <span data-ttu-id="d90bf-160">**Tipo de aprobación**: manual o automático</span><span class="sxs-lookup"><span data-stu-id="d90bf-160">**Approval type**: Manual or Auto</span></span>

    <span data-ttu-id="d90bf-161">**Grupo de aprobación**: seleccione el grupo aprobadores creado en el paso 1.</span><span class="sxs-lookup"><span data-stu-id="d90bf-161">**Approval group**: Select the approvers group created in Step 1</span></span>

6. <span data-ttu-id="d90bf-p108">Seleccione **crear** y, a continuación, **cerrar**. La Directiva puede tardar unos minutos en estar totalmente configurada y habilitada.</span><span class="sxs-lookup"><span data-stu-id="d90bf-p108">Select **Create** and then **Close**. It may take a few minutes for the policy to be fully configured and enabled.</span></span>

### <a name="using-exchange-management-powershell"></a><span data-ttu-id="d90bf-164">Uso de Exchange Management PowerShell</span><span class="sxs-lookup"><span data-stu-id="d90bf-164">Using Exchange Management PowerShell</span></span>

<span data-ttu-id="d90bf-165">Ejecute el siguiente comando en Exchange Online PowerShell para crear y definir una directiva de aprobación:</span><span class="sxs-lookup"><span data-stu-id="d90bf-165">Run the following command in Exchange Online PowerShell to create and define an approval policy:</span></span>

```
New-ElevatedAccessApprovalPolicy -Task 'Exchange\<exchange management cmdlet name>' -ApprovalType <Manual, Auto> -ApproverGroup '<default/custom approver group>'
```
<span data-ttu-id="d90bf-166">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="d90bf-166">Example:</span></span>
```
New-ElevatedAccessApprovalPolicy -Task 'Exchange\New-MoveRequest' -ApprovalType Manual -ApproverGroup 'mbmanagers@fabrikamorg.onmicrosoft.com'
```

<span data-ttu-id="d90bf-167"><a name="step4"> </a></span><span class="sxs-lookup"><span data-stu-id="d90bf-167"></span></span>

## <a name="step-4-submitapprove-privileged-access-requests"></a><span data-ttu-id="d90bf-168">Paso 4: enviar o aprobar solicitudes de acceso privilegiadas</span><span class="sxs-lookup"><span data-stu-id="d90bf-168">Step 4: Submit/approve privileged access requests</span></span>

### <a name="requesting-elevation-authorization-to-execute-privileged-tasks"></a><span data-ttu-id="d90bf-169">Solicitar autorización de elevación para ejecutar tareas privilegiadas</span><span class="sxs-lookup"><span data-stu-id="d90bf-169">Requesting elevation authorization to execute privileged tasks</span></span>

<span data-ttu-id="d90bf-p109">Las solicitudes de acceso con privilegios son válidas durante un máximo de 24 horas después de que se envíe la solicitud. Si no se aprueba o se rechaza, las solicitudes expiran y el acceso no se aprueba.</span><span class="sxs-lookup"><span data-stu-id="d90bf-p109">Requests for privileged access are valid for up to 24 hours after the request is submitted. If not approved or denied, the requests expire and access is not approved.</span></span>

#### <a name="using-the-microsoft-365-admin-center"></a><span data-ttu-id="d90bf-172">Uso del centro de administración de 365 de Microsoft</span><span class="sxs-lookup"><span data-stu-id="d90bf-172">Using the Microsoft 365 Admin Center</span></span>

1. <span data-ttu-id="d90bf-173">Inicie sesión en el [centro de administración de Microsoft 365](https://portal.office.com) con sus credenciales.</span><span class="sxs-lookup"><span data-stu-id="d90bf-173">Sign into the [Microsoft 365 Admin Center](https://portal.office.com) using your credentials.</span></span>

2. <span data-ttu-id="d90bf-174">En el centro de administración, vaya a **configuración** > **seguridad &** > **acceso privilegiado a**la privacidad.</span><span class="sxs-lookup"><span data-stu-id="d90bf-174">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="d90bf-175">Seleccione **Administrar directivas y solicitudes de acceso**.</span><span class="sxs-lookup"><span data-stu-id="d90bf-175">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="d90bf-p110">Seleccione **nueva solicitud**. En los campos desplegables, seleccione los valores adecuados para su organización:</span><span class="sxs-lookup"><span data-stu-id="d90bf-p110">Select **New request**. From the drop-down fields, select the appropriate values for your organization:</span></span>

    <span data-ttu-id="d90bf-178">**Tipo de solicitud**: tarea, rol o grupo de roles</span><span class="sxs-lookup"><span data-stu-id="d90bf-178">**Request type**: Task, Role, or Role Group</span></span>

    <span data-ttu-id="d90bf-179">**Ámbito de solicitud**: Exchange</span><span class="sxs-lookup"><span data-stu-id="d90bf-179">**Request scope**: Exchange</span></span>

    <span data-ttu-id="d90bf-180">**Solicitud de**: Seleccione una de las directivas disponibles</span><span class="sxs-lookup"><span data-stu-id="d90bf-180">**Request for**: Select from the available policies</span></span>

    <span data-ttu-id="d90bf-p111">**Duración (horas)**: número de horas de acceso solicitado. No hay un límite en el número de horas que se puede solicitar.</span><span class="sxs-lookup"><span data-stu-id="d90bf-p111">**Duration (hours)**: Number of hours of requested access. There isn't a limit on the number of hours that can be requested.</span></span>

    <span data-ttu-id="d90bf-183">**Comentarios**: campo de texto para comentarios relacionados con la solicitud de acceso</span><span class="sxs-lookup"><span data-stu-id="d90bf-183">**Comments**: Text field for comments related to your access request</span></span>

5. <span data-ttu-id="d90bf-p112">Seleccione **Guardar** y, a continuación, **cerrar**. La solicitud se enviará al grupo del aprobador a través del correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="d90bf-p112">Select **Save** and then **Close**. Your request will be sent to the approver's group via email.</span></span>

#### <a name="using-exchange-management-powershell"></a><span data-ttu-id="d90bf-186">Uso de Exchange Management PowerShell</span><span class="sxs-lookup"><span data-stu-id="d90bf-186">Using Exchange Management PowerShell</span></span>

<span data-ttu-id="d90bf-187">Ejecute el siguiente comando en Exchange Online PowerShell para crear y enviar una solicitud de aprobación al grupo del aprobador:</span><span class="sxs-lookup"><span data-stu-id="d90bf-187">Run the following command in Exchange Online PowerShell to create and submit an approval request to the approver's group:</span></span>
```
New-ElevatedAccessRequest -Task 'Exchange\<exchange management cmdlet name>' -Reason '<appropriate reason>' -DurationHours <duration in hours>
```
<span data-ttu-id="d90bf-188">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="d90bf-188">Example:</span></span>
```
New-ElevatedAccessRequest -Task 'Exchange\New-MoveRequest' -Reason 'Attempting to fix the user mailbox error' -DurationHours 4
```
### <a name="view-status-of-elevation-requests"></a><span data-ttu-id="d90bf-189">Ver el estado de las solicitudes de elevación</span><span class="sxs-lookup"><span data-stu-id="d90bf-189">View status of elevation requests</span></span>
<span data-ttu-id="d90bf-190">Después de crear una solicitud de aprobación, el estado de la solicitud de elevación se puede revisar en el centro de administración o en PowerShell de administración de Exchange con el identificador de solicitud asociado.</span><span class="sxs-lookup"><span data-stu-id="d90bf-190">After an approval request is created, elevation request status can be reviewed in the Admin Center or in Exchange Management PowerShell using the associated with request ID.</span></span>

#### <a name="using-the-microsoft-365-admin-center"></a><span data-ttu-id="d90bf-191">Uso del centro de administración de 365 de Microsoft</span><span class="sxs-lookup"><span data-stu-id="d90bf-191">Using the Microsoft 365 Admin Center</span></span>

1. <span data-ttu-id="d90bf-192">Inicie sesión en el [centro de administración de Microsoft 365](https://portal.office.com) con sus credenciales.</span><span class="sxs-lookup"><span data-stu-id="d90bf-192">Sign into the [Microsoft 365 Admin Center](https://portal.office.com) using your credentials.</span></span>

2. <span data-ttu-id="d90bf-193">En el centro de administración, vaya a **configuración** > **seguridad &** > **acceso privilegiado a**la privacidad.</span><span class="sxs-lookup"><span data-stu-id="d90bf-193">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="d90bf-194">Seleccione **Administrar directivas y solicitudes de acceso**.</span><span class="sxs-lookup"><span data-stu-id="d90bf-194">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="d90bf-195">Seleccione **Ver** para filtrar las solicitudes enviadas por estado **pendiente**, **aprobado**, deNegado o de caja de **caja del cliente** . \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="d90bf-195">Select **View** to filter submitted requests by **Pending**, **Approved**, **Denied**, or **Customer Lockbox** status.</span></span>

#### <a name="using-exchange-management-powershell"></a><span data-ttu-id="d90bf-196">Uso de Exchange Management PowerShell</span><span class="sxs-lookup"><span data-stu-id="d90bf-196">Using Exchange Management PowerShell</span></span>

<span data-ttu-id="d90bf-197">Ejecute el siguiente comando en Exchange Online PowerShell para ver el estado de la solicitud de aprobación de un identificador de solicitud específico:</span><span class="sxs-lookup"><span data-stu-id="d90bf-197">Run the following command in Exchange Online PowerShell to view a approval request status for a specific request ID:</span></span>
```
Get-ElevatedAccessRequest -Identity <request ID> | select RequestStatus
```
<span data-ttu-id="d90bf-198">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="d90bf-198">Example:</span></span>
```
Get-ElevatedAccessRequest -Identity 28560ed0-419d-4cc3-8f5b-603911cbd450 | select RequestStatus
```

### <a name="approving-an-elevation-authorization-request"></a><span data-ttu-id="d90bf-199">Aprobación de una solicitud de autorización de elevación</span><span class="sxs-lookup"><span data-stu-id="d90bf-199">Approving an elevation authorization request</span></span>
<span data-ttu-id="d90bf-p113">Cuando se crea una solicitud de aprobación, los miembros del grupo aprobador relevante recibirán una notificación por correo electrónico y podrán aprobar la solicitud asociada con el identificador de solicitud. El solicitante recibirá una notificación de la aprobación de la solicitud o de una denegación mediante un mensaje de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="d90bf-p113">When an approval request is created, members of the relevant approver group will receive an email notification and can approve the request associated with the request ID. The requestor will be notified of the request approval or denial via email message.</span></span>

#### <a name="using-the-microsoft-365-admin-center"></a><span data-ttu-id="d90bf-202">Uso del centro de administración de 365 de Microsoft</span><span class="sxs-lookup"><span data-stu-id="d90bf-202">Using the Microsoft 365 Admin Center</span></span>

1. <span data-ttu-id="d90bf-203">Inicie sesión en el [centro de administración de Microsoft 365](https://portal.office.com) con sus credenciales.</span><span class="sxs-lookup"><span data-stu-id="d90bf-203">Sign into the [Microsoft 365 Admin Center](https://portal.office.com) using your credentials.</span></span>

2. <span data-ttu-id="d90bf-204">En el centro de administración, vaya a **configuración** > **seguridad &** > **acceso privilegiado a**la privacidad.</span><span class="sxs-lookup"><span data-stu-id="d90bf-204">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="d90bf-205">Seleccione **Administrar directivas y solicitudes de acceso**.</span><span class="sxs-lookup"><span data-stu-id="d90bf-205">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="d90bf-206">Seleccione una solicitud de la lista para ver los detalles y realizar la acción en la solicitud.</span><span class="sxs-lookup"><span data-stu-id="d90bf-206">Select a listed request to view the details and to take action on the request.</span></span>

5. <span data-ttu-id="d90bf-p114">Seleccione **aprobar** para aprobar la solicitud o seleccione **denegar** para denegar la solicitud. Las solicitudes aprobadas anteriormente pueden revocar el acceso mediante la selección de **REVOKE**.</span><span class="sxs-lookup"><span data-stu-id="d90bf-p114">Select **Approve** to approve the request or select **Deny** to deny the request. Previously approved requests can have access revoked by selecting **Revoke**.</span></span>

#### <a name="using-exchange-management-powershell"></a><span data-ttu-id="d90bf-209">Uso de Exchange Management PowerShell</span><span class="sxs-lookup"><span data-stu-id="d90bf-209">Using Exchange Management PowerShell</span></span>

<span data-ttu-id="d90bf-210">Ejecute el siguiente comando en Exchange Online PowerShell para aprobar una solicitud de autorización de elevación:</span><span class="sxs-lookup"><span data-stu-id="d90bf-210">Run the following command in Exchange Online PowerShell to approve an elevation authorization request:</span></span>

```
Approve-ElevatedAccessRequest -RequestId <request id> -Comment '<approval comment>'
```
<span data-ttu-id="d90bf-211">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="d90bf-211">Example:</span></span>
```
Approve-ElevatedAccessRequest -RequestId a4bc1bdf-00a1-42b4-be65-b6c63d6be279 -Comment '<approval comment>'
```

<span data-ttu-id="d90bf-212">Ejecute el siguiente comando en Exchange Online PowerShell para denegar una solicitud de autorización de elevación:</span><span class="sxs-lookup"><span data-stu-id="d90bf-212">Run the following command in Exchange Online PowerShell to deny an elevation authorization request:</span></span>

```
Deny-ElevatedAccessRequest -RequestId <request id> -Comment '<denial comment>'
```
<span data-ttu-id="d90bf-213">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="d90bf-213">Example:</span></span>
```
Deny-ElevatedAccessRequest -RequestId a4bc1bdf-00a1-42b4-be65-b6c63d6be279 -Comment '<denial comment>'
```

## <a name="delete-a-privileged-access-policy-in-office-365"></a><span data-ttu-id="d90bf-214">Eliminar una directiva de acceso privilegiada en Office 365</span><span class="sxs-lookup"><span data-stu-id="d90bf-214">Delete a privileged access policy in Office 365</span></span>
<span data-ttu-id="d90bf-215">Puede eliminar una directiva de acceso privilegiado si ya no la necesita en su organización.</span><span class="sxs-lookup"><span data-stu-id="d90bf-215">You can delete a privileged access policy if it is no longer needed in your organization.</span></span>

### <a name="using-the-microsoft-365-admin-center"></a><span data-ttu-id="d90bf-216">Uso del centro de administración de 365 de Microsoft</span><span class="sxs-lookup"><span data-stu-id="d90bf-216">Using the Microsoft 365 Admin Center</span></span>

1. <span data-ttu-id="d90bf-217">Inicie sesión en el [centro de administración de Microsoft 365](https://portal.office.com) con las credenciales de una cuenta de administrador en la organización.</span><span class="sxs-lookup"><span data-stu-id="d90bf-217">Sign into the [Microsoft 365 Admin Center](https://portal.office.com) using credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="d90bf-218">En el centro de administración, vaya a **configuración** > **seguridad &** > **acceso privilegiado a**la privacidad.</span><span class="sxs-lookup"><span data-stu-id="d90bf-218">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="d90bf-219">Seleccione **Administrar directivas y solicitudes de acceso**.</span><span class="sxs-lookup"><span data-stu-id="d90bf-219">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="d90bf-220">Seleccione **configurar directivas**.</span><span class="sxs-lookup"><span data-stu-id="d90bf-220">Select **Configure policies**.</span></span>

5. <span data-ttu-id="d90bf-221">Seleccione la Directiva que desea eliminar y, a continuación, seleccione **quitar Directiva**.</span><span class="sxs-lookup"><span data-stu-id="d90bf-221">Select the policy you want to delete, then select **Remove Policy**.</span></span>

6. <span data-ttu-id="d90bf-222">Seleccione **cerrar**.</span><span class="sxs-lookup"><span data-stu-id="d90bf-222">Select **Close**.</span></span>

### <a name="using-exchange-management-powershell"></a><span data-ttu-id="d90bf-223">Uso de Exchange Management PowerShell</span><span class="sxs-lookup"><span data-stu-id="d90bf-223">Using Exchange Management PowerShell</span></span>

<span data-ttu-id="d90bf-224">Ejecute el siguiente comando en Exchange Online PowerShell para eliminar una directiva de acceso privilegiada:</span><span class="sxs-lookup"><span data-stu-id="d90bf-224">Run the following command in Exchange Online Powershell to delete a privileged access policy:</span></span>

```
Remove-ElevatedAccessApprovalPolicy -Identity <identity GUID of the policy you want to delete>
```

## <a name="disable-privileged-access-in-office-365"></a><span data-ttu-id="d90bf-225">DesHabilitar el acceso privilegiado en Office 365</span><span class="sxs-lookup"><span data-stu-id="d90bf-225">Disable privileged access in Office 365</span></span>

<span data-ttu-id="d90bf-p115">Si es necesario, puede deshabilitar la administración del acceso con privilegios para su organización. La desHabilitación del acceso con privilegios no elimina ninguna directiva de aprobación o grupo de aprobador asociado.</span><span class="sxs-lookup"><span data-stu-id="d90bf-p115">If needed, you can disable privileged access management for your organization. Disabling privileged access does not delete any associated approval policies or approver groups.</span></span>

### <a name="using-the-microsoft-365-admin-center"></a><span data-ttu-id="d90bf-228">Uso del centro de administración de 365 de Microsoft</span><span class="sxs-lookup"><span data-stu-id="d90bf-228">Using the Microsoft 365 Admin Center</span></span>

1. <span data-ttu-id="d90bf-229">Inicie sesión en el [centro de administración de Microsoft 365](https://portal.office.com) con las credenciales de una cuenta de administrador en la organización.</span><span class="sxs-lookup"><span data-stu-id="d90bf-229">Sign into the [Microsoft 365 Admin Center](https://portal.office.com) using credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="d90bf-230">En el centro de administración, vaya a **configuración** > **seguridad &** > **acceso privilegiado a**la privacidad.</span><span class="sxs-lookup"><span data-stu-id="d90bf-230">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="d90bf-231">Habilite el control **de acceso requerir aprobaciones para privilegios** .</span><span class="sxs-lookup"><span data-stu-id="d90bf-231">Enable the **Require approvals for privileged access** control.</span></span>

### <a name="using-exchange-management-powershell"></a><span data-ttu-id="d90bf-232">Uso de Exchange Management PowerShell</span><span class="sxs-lookup"><span data-stu-id="d90bf-232">Using Exchange Management PowerShell</span></span>

<span data-ttu-id="d90bf-233">Ejecute el siguiente comando en Exchange Online PowerShell para deshabilitar el acceso privilegiado:</span><span class="sxs-lookup"><span data-stu-id="d90bf-233">Run the following command in Exchange Online Powershell to disable privileged access:</span></span>

```
Disable-ElevatedAccessControl
```