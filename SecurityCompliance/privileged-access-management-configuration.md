---
title: Configuración de administración de acceso con privilegios en Office 365
ms.author: robmazz
author: robmazz
manager: laurawi
ms.audience: ITPro
ms.topic: overview
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Strat_O365_IP
ms.custom: Ent_Solutions
ms.assetid: ''
description: Utilice este tema para obtener más información acerca de la configuración de administración de acceso con privilegios en Office 365
ms.openlocfilehash: 13d278c8e8555aa069035c2f03b23db69a475b43
ms.sourcegitcommit: 448c5897e44448adfc82e3eaffb774c770c04815
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/12/2018
ms.locfileid: "25522262"
---
# <a name="configuring-privileged-access-management-in-office-365"></a><span data-ttu-id="7d749-103">Configuración de administración de acceso con privilegios en Office 365</span><span class="sxs-lookup"><span data-stu-id="7d749-103">Configuring privileged access management in Office 365</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7d749-104">En este tema se trata instrucciones de implementación y configuración para características sólo actualmente disponibles en Office 365 E5 y avanzada SKU de cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="7d749-104">This topic covers deployment and configuration guidance for features only currently available in Office 365 E5 and Advanced Compliance SKUs.</span></span>

<span data-ttu-id="7d749-p101">En este tema le guiará a través de habilitar y configurar la administración del acceso con privilegios en su organización de Office 365. Puede usar el centro de administración de Microsoft 365 o el PowerShell de administración de Exchange para administrar y usar con privilegios de acceso.</span><span class="sxs-lookup"><span data-stu-id="7d749-p101">This topic will guide you through enabling and configuring privileged access management in your Office 365 organization. You can use either the Microsoft 365 Admin Center or Exchange Management PowerShell to manage and use privileged access.</span></span> 

## <a name="enable-and-configure-privileged-access-management"></a><span data-ttu-id="7d749-107">Habilitar y configurar la administración con privilegios de acceso</span><span class="sxs-lookup"><span data-stu-id="7d749-107">Enable and configure privileged access management</span></span>

<span data-ttu-id="7d749-108">Siga estos pasos para configurar y utilizar con privilegios de acceso de la organización de Office 365:</span><span class="sxs-lookup"><span data-stu-id="7d749-108">Follow these steps to set up and use privileged access in your Office 365 organization:</span></span>

- [<span data-ttu-id="7d749-109">Paso 1: Crear el grupo del aprobador</span><span class="sxs-lookup"><span data-stu-id="7d749-109">Step 1: Create an approver's group</span></span>](privileged-access-management-configuration.md#step1)

    <span data-ttu-id="7d749-p102">Antes de empezar a usar acceso con privilegios, determinar quién tendrá la autoridad de aprobación para las solicitudes entrantes para el acceso a las tareas con privilegios elevados y con privilegios. Cualquier usuario que forma parte del grupo de los aprobadores podrán aprobar las solicitudes de acceso. Esto se habilita mediante la creación de un grupo de seguridad habilitados para correo en Office 365.</span><span class="sxs-lookup"><span data-stu-id="7d749-p102">Before you start using privilege access, determine who will have approval authority for incoming requests for access to elevated and privileged tasks. Any user who is part of the Approvers’ group will be able to approve access requests. This is enabled by creating a mail-enabled security group in Office 365.</span></span>

- [<span data-ttu-id="7d749-113">Paso 2: Habilitar el acceso con privilegios</span><span class="sxs-lookup"><span data-stu-id="7d749-113">Step 2: Enable privileged access</span></span>](privileged-access-management-configuration.md#step2)

    <span data-ttu-id="7d749-114">Acceso con privilegios debe habilitarse explícitamente en Office 365 con el grupo de aprobadores predeterminada y, incluido un conjunto de cuentas del sistema que desea que se deben excluir desde el control de acceso de administración con privilegios de acceso.</span><span class="sxs-lookup"><span data-stu-id="7d749-114">Privileged access needs to be explicitly turned on in Office 365 with the default approver group and including a set of system accounts that you’d want to be excluded from the privileged access management access control.</span></span>

- [<span data-ttu-id="7d749-115">Paso 3: Crear una directiva de acceso</span><span class="sxs-lookup"><span data-stu-id="7d749-115">Step 3: Create an access policy</span></span>](privileged-access-management-configuration.md#step3)

    <span data-ttu-id="7d749-p103">Creación de una directiva de aprobación le permite definir los requisitos de aprobación específico con ámbito en tareas individuales. Las opciones de tipo de aprobación son **automático** o **Manual**.</span><span class="sxs-lookup"><span data-stu-id="7d749-p103">Creating an approval policy allows you to define the specific approval requirements scoped at individual tasks. The approval type options are **Auto** or **Manual**.</span></span>

- [<span data-ttu-id="7d749-118">Paso 4: Enviar y aprobar las solicitudes de acceso con privilegios</span><span class="sxs-lookup"><span data-stu-id="7d749-118">Step 4: Submit/approve privileged access requests</span></span>](privileged-access-management-configuration.md#step4)

    <span data-ttu-id="7d749-p104">Una vez habilitado, con privilegios de acceso requiere aprobaciones para ejecutar cualquier tarea que tiene una directiva de aprobación asociada definida. Los usuarios que necesiten ejecutar tareas incluidas en la una directiva de aprobación debe solicitar y recibir aprobación de acceso con el fin de tener los permisos necesarios para ejecutar la tarea.</span><span class="sxs-lookup"><span data-stu-id="7d749-p104">Once enabled, privileged access requires approvals for executing any task that has an associated approval policy defined. Users needing to execute tasks included in the an approval policy must request and be granted access approval in order to have permissions necessary to execute the task.</span></span>

<span data-ttu-id="7d749-p105">Una vez se concede la aprobación, el usuario solicitante puede ejecutar la tarea prevista y va a autorizar y ejecutar la tarea en nombre de los usuarios con privilegios de acceso. La aprobación sigue siendo válida para el solicitado duración (duración predeterminada es de 4 horas), durante el cual el solicitante puede ejecutar la tarea prevista varias veces. Todas esas ejecuciones se registran y a disposición de cumplimiento de normas de auditoría y seguridad.</span><span class="sxs-lookup"><span data-stu-id="7d749-p105">After approval is granted, the requesting user can execute the intended task and privileged access will authorize and execute the task on users’ behalf. The approval remains valid for the requested duration (default duration is 4 hours), during which the requester can execute the intended task multiple times. All such executions are logged and made available for security and compliance auditing.</span></span> 

> [!NOTE]
> <span data-ttu-id="7d749-p106">Si desea usar PowerShell de administración de Exchange para habilitar y configurar el acceso con privilegios, siga los pasos de [conectarse a Exchange Online PowerShell mediante autenticación multifactor](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/mfa-connect-to-exchange-online-powershell?view=exchange-ps) para conectarse a Exchange Online PowerShell con Office 365 credenciales. No es necesario habilitar la autenticación multifactor para su organización de Office 365 usar los pasos para habilitar el acceso con privilegios mientras se conecta a Exchange Online PowerShell. Conectar con la autenticación multifactor crea un token de OAuth que se usa en el acceso con privilegios para las solicitudes de firma.</span><span class="sxs-lookup"><span data-stu-id="7d749-p106">If you want to use Exchange Management PowerShell to enable and configure privileged access, follow the steps in [Connect to Exchange Online PowerShell using Multi-Factor authentication](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/mfa-connect-to-exchange-online-powershell?view=exchange-ps) to connect to Exchange Online PowerShell with your Office 365 credentials. You do not need to enable multi-factor authentication for your Office 365 organization to use the steps to enable privileged access while connecting to Exchange Online PowerShell. Connecting with multi-factor authentication creates an OAuth token that is used by privileged access for signing your requests.</span></span>

<span data-ttu-id="7d749-127"><a name="step1"> </a></span><span class="sxs-lookup"><span data-stu-id="7d749-127"></span></span>

## <a name="step-1---create-an-approvers-group"></a><span data-ttu-id="7d749-128">Paso 1: crear el grupo del aprobador</span><span class="sxs-lookup"><span data-stu-id="7d749-128">Step 1 - Create an approver's group</span></span>

1. <span data-ttu-id="7d749-129">Inicie sesión en el [Centro de administración de Microsoft 365](https://portal.office.com) de uso de credenciales para una cuenta de administrador de la organización.</span><span class="sxs-lookup"><span data-stu-id="7d749-129">Sign into the [Microsoft 365 Admin Center](https://portal.office.com) using credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="7d749-130">En el centro de administración, vaya a **grupos** > **Agregar un grupo**.</span><span class="sxs-lookup"><span data-stu-id="7d749-130">In the Admin Center, go to **Groups** > **Add a group**.</span></span>

3. <span data-ttu-id="7d749-131">Seleccione el tipo de grupo de **grupo de seguridad habilitados para correo** y, a continuación, complete los campos **nombre**, **dirección de correo electrónico de grupo**y **Descripción** para el nuevo grupo.</span><span class="sxs-lookup"><span data-stu-id="7d749-131">Select the **mail-enabled security group** group type and then complete the **Name**, **Group email address**, and **Description** fields for the new group.</span></span>

4. <span data-ttu-id="7d749-p107">Guarde el grupo. Puede tardar unos minutos para el grupo configurarse completamente y aparezca en el centro de administración de Office 365.</span><span class="sxs-lookup"><span data-stu-id="7d749-p107">Save the group. It may take a few minutes for the group to be fully configured and to appear in the Office 365 Admin Center.</span></span>

5. <span data-ttu-id="7d749-134">Seleccione grupo de aprobadores nuevo y seleccione **Editar** para agregar usuarios al grupo.</span><span class="sxs-lookup"><span data-stu-id="7d749-134">Select the new approver's group and select **edit** to add users to the group.</span></span>

6. <span data-ttu-id="7d749-135">Guarde el grupo.</span><span class="sxs-lookup"><span data-stu-id="7d749-135">Save the group.</span></span>

<span data-ttu-id="7d749-136"><a name="step2"> </a></span><span class="sxs-lookup"><span data-stu-id="7d749-136"></span></span>

## <a name="step-2---enable-privileged-access"></a><span data-ttu-id="7d749-137">Paso 2: habilitar el acceso con privilegios</span><span class="sxs-lookup"><span data-stu-id="7d749-137">Step 2 - Enable privileged access</span></span>

### <a name="using-the-microsoft-365-admin-center"></a><span data-ttu-id="7d749-138">Desde el centro de administración de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="7d749-138">Using the Microsoft 365 Admin Center</span></span>

1. <span data-ttu-id="7d749-139">Inicie sesión en el [Centro de administración de Microsoft 365](https://portal.office.com) de uso de credenciales para una cuenta de administrador de la organización.</span><span class="sxs-lookup"><span data-stu-id="7d749-139">Sign into the [Microsoft 365 Admin Center](https://portal.office.com) using credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="7d749-140">En el centro de administración, vaya a **Configuración > seguridad y privacidad** > **con privilegios de acceso**.</span><span class="sxs-lookup"><span data-stu-id="7d749-140">In the Admin Center, go to **Settings > Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="7d749-141">Habilitar el control **requieren aprobaciones para el acceso con privilegios** .</span><span class="sxs-lookup"><span data-stu-id="7d749-141">Enable the **Require approvals for privileged access** control.</span></span>

4. <span data-ttu-id="7d749-142">Asignar a grupo del aprobador que creó en el paso 1 como el **grupo de aprobadores predeterminado**.</span><span class="sxs-lookup"><span data-stu-id="7d749-142">Assign the approver's group you created in Step 1 as the **Default approvers group**.</span></span>

5. <span data-ttu-id="7d749-143">**Guardar** y **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="7d749-143">**Save** and **Close**.</span></span>

### <a name="using-exchange-management-powershell"></a><span data-ttu-id="7d749-144">Uso de PowerShell de administración de Exchange</span><span class="sxs-lookup"><span data-stu-id="7d749-144">Using Exchange Management PowerShell</span></span>

<span data-ttu-id="7d749-145">En Exchange Online PowerShell para habilitar el acceso con privilegios y para asignar el grupo de aprobadores, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="7d749-145">Run the following command in Exchange Online PowerShell to enable privileged access and to assign the approver's group:</span></span>
```
Enable-ElevatedAccessControl -AdminGroup '<default approver group>' -SystemAccounts @('<systemAccountUPN1>','<systemAccountUPN2>')
```
<span data-ttu-id="7d749-146">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="7d749-146">Example:</span></span>
```
Enable-ElevatedAccessControl -AdminGroup 'pamapprovers@fabrikam.onmicrosoft.com' -SystemAccounts @('sys1@fabrikamorg.onmicrosoft.com', sys2@fabrikamorg.onmicrosoft.com')
```

> [!NOTE]
> <span data-ttu-id="7d749-147">Cuentas del sistema característica está disponible para asegurarse de determinados automations dentro de las organizaciones pueden trabajar sin dependencia en acceso con privilegios, sin embargo, se recomienda que estas exclusiones se excepcionales y los autorizados deben aprobados y auditar con regularidad.</span><span class="sxs-lookup"><span data-stu-id="7d749-147">System accounts feature is made available to ensure certain automations within your organizations can work without dependency on privileged access, however it is recommended that such exclusions be exceptional and those allowed should be approved and audited regularly.</span></span>

<span data-ttu-id="7d749-148"><a name="step3"> </a></span><span class="sxs-lookup"><span data-stu-id="7d749-148"></span></span>

## <a name="step-3---create-an-access-policy"></a><span data-ttu-id="7d749-149">Paso 3: crear una directiva de acceso</span><span class="sxs-lookup"><span data-stu-id="7d749-149">Step 3 - Create an access policy</span></span>

<span data-ttu-id="7d749-150">Puede crear y configurar directivas de acceso con privilegios de hasta 30 para su organización de Office 365.</span><span class="sxs-lookup"><span data-stu-id="7d749-150">You can create and configure up to 30 privileged access policies for your Office 365 organization.</span></span>

### <a name="using-the-microsoft-365-admin-center"></a><span data-ttu-id="7d749-151">Desde el centro de administración de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="7d749-151">Using the Microsoft 365 Admin Center</span></span>

1. <span data-ttu-id="7d749-152">Inicie sesión en el [Centro de administración de Microsoft 365](https://portal.office.com) de uso de credenciales para una cuenta de administrador de la organización.</span><span class="sxs-lookup"><span data-stu-id="7d749-152">Sign into the [Microsoft 365 Admin Center](https://portal.office.com) using credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="7d749-153">En el centro de administración, vaya a **configuración de** > **de seguridad y privacidad** > **con privilegios de acceso**.</span><span class="sxs-lookup"><span data-stu-id="7d749-153">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="7d749-154">Seleccione **las solicitudes y administrar las directivas de acceso**.</span><span class="sxs-lookup"><span data-stu-id="7d749-154">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="7d749-155">Seleccione **la configuración de directivas** y seleccione **Agregar una directiva**.</span><span class="sxs-lookup"><span data-stu-id="7d749-155">Select **Configure policies** and select **Add a policy**.</span></span>

5. <span data-ttu-id="7d749-156">En los campos de lista desplegable, seleccione los valores apropiados para su organización:</span><span class="sxs-lookup"><span data-stu-id="7d749-156">From the drop-down fields, select the appropriate values for your organization:</span></span>
    
    <span data-ttu-id="7d749-157">**Tipo de directiva**: tarea, rol o grupo de roles</span><span class="sxs-lookup"><span data-stu-id="7d749-157">**Policy type**: Task, Role, or Role Group</span></span>

    <span data-ttu-id="7d749-158">**Ámbito de directiva**: Exchange u Office 365</span><span class="sxs-lookup"><span data-stu-id="7d749-158">**Policy scope**: Exchange or Office 365</span></span>

    <span data-ttu-id="7d749-159">**Nombre de la directiva**: seleccione de las directivas disponibles</span><span class="sxs-lookup"><span data-stu-id="7d749-159">**Policy name**: Select from the available policies</span></span>

    <span data-ttu-id="7d749-160">**Tipo de aprobación**: Manual o automático</span><span class="sxs-lookup"><span data-stu-id="7d749-160">**Approval type**: Manual or Auto</span></span>

    <span data-ttu-id="7d749-161">**Grupo de aprobación**: seleccione el grupo de aprobadores que creó en el paso 1</span><span class="sxs-lookup"><span data-stu-id="7d749-161">**Approval group**: Select the approvers group created in Step 1</span></span>

6. <span data-ttu-id="7d749-p108">Seleccione **crear** y, a continuación, en **Cerrar**. Puede tardar unos minutos para la directiva ser totalmente configurado y habilitado.</span><span class="sxs-lookup"><span data-stu-id="7d749-p108">Select **Create** and then **Close**. It may take a few minutes for the policy to be fully configured and enabled.</span></span>

### <a name="using-exchange-management-powershell"></a><span data-ttu-id="7d749-164">Uso de PowerShell de administración de Exchange</span><span class="sxs-lookup"><span data-stu-id="7d749-164">Using Exchange Management PowerShell</span></span>

<span data-ttu-id="7d749-165">Ejecute el siguiente comando en Exchange Online PowerShell para crear y definir una directiva de aprobación:</span><span class="sxs-lookup"><span data-stu-id="7d749-165">Run the following command in Exchange Online PowerShell to create and define an approval policy:</span></span>

```
New-ElevatedAccessApprovalPolicy -Task 'Exchange\<exchange management cmdlet name>' -ApprovalType <Manual, Auto> -ApproverGroup '<default/custom approver group>'
```
<span data-ttu-id="7d749-166">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="7d749-166">Example:</span></span>
```
New-ElevatedAccessApprovalPolicy -Task 'Exchange\New-MoveRequest' -ApprovalType Manual -ApproverGroup 'mbmanagers@fabrikamorg.onmicrosoft.com'
```

<span data-ttu-id="7d749-167"><a name="step4"> </a></span><span class="sxs-lookup"><span data-stu-id="7d749-167"></span></span>

## <a name="step-4-submitapprove-privileged-access-requests"></a><span data-ttu-id="7d749-168">Paso 4: Enviar y aprobar las solicitudes de acceso con privilegios</span><span class="sxs-lookup"><span data-stu-id="7d749-168">Step 4: Submit/approve privileged access requests</span></span>

### <a name="requesting-elevation-authorization-to-execute-privileged-tasks"></a><span data-ttu-id="7d749-169">Solicitud de autorización de elevación para ejecutar tareas con privilegios</span><span class="sxs-lookup"><span data-stu-id="7d749-169">Requesting elevation authorization to execute privileged tasks</span></span>

<span data-ttu-id="7d749-p109">Las solicitudes de acceso con privilegios son válidas durante 24 horas después de que se envía la solicitud. Si no aprobadas o rechazadas, las solicitudes de punto de expirar y acceso no está aprobado.</span><span class="sxs-lookup"><span data-stu-id="7d749-p109">Requests for privileged access are valid for up to 24 hours after the request is submitted. If not approved or denied, the requests expire and access is not approved.</span></span>

#### <a name="using-the-microsoft-365-admin-center"></a><span data-ttu-id="7d749-172">Desde el centro de administración de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="7d749-172">Using the Microsoft 365 Admin Center</span></span>

1. <span data-ttu-id="7d749-173">Inicie sesión en el [Centro de administración de Microsoft 365](https://portal.office.com) con sus credenciales.</span><span class="sxs-lookup"><span data-stu-id="7d749-173">Sign into the [Microsoft 365 Admin Center](https://portal.office.com) using your credentials.</span></span>

2. <span data-ttu-id="7d749-174">En el centro de administración, vaya a **configuración de** > **de seguridad y privacidad** > **con privilegios de acceso**.</span><span class="sxs-lookup"><span data-stu-id="7d749-174">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="7d749-175">Seleccione **las solicitudes y administrar las directivas de acceso**.</span><span class="sxs-lookup"><span data-stu-id="7d749-175">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="7d749-p110">Seleccione **nueva solicitud**. En los campos de lista desplegable, seleccione los valores apropiados para su organización:</span><span class="sxs-lookup"><span data-stu-id="7d749-p110">Select **New request**. From the drop-down fields, select the appropriate values for your organization:</span></span>

    <span data-ttu-id="7d749-178">**Tipo de solicitud**: tarea, rol o grupo de roles</span><span class="sxs-lookup"><span data-stu-id="7d749-178">**Request type**: Task, Role, or Role Group</span></span>

    <span data-ttu-id="7d749-179">**Ámbito de solicitud**: Exchange</span><span class="sxs-lookup"><span data-stu-id="7d749-179">**Request scope**: Exchange</span></span>

    <span data-ttu-id="7d749-180">**Solicitud para**: seleccione de las directivas disponibles</span><span class="sxs-lookup"><span data-stu-id="7d749-180">**Request for**: Select from the available policies</span></span>

    <span data-ttu-id="7d749-p111">**Duración (horas)**: número de horas de acceso solicitados. No hay un límite en el número de horas que se puede solicitar.</span><span class="sxs-lookup"><span data-stu-id="7d749-p111">**Duration (hours)**: Number of hours of requested access. There isn't a limit on the number of hours that can be requested.</span></span>

    <span data-ttu-id="7d749-183">**Comentarios**: campo de texto de comentarios relacionados con la solicitud de acceso</span><span class="sxs-lookup"><span data-stu-id="7d749-183">**Comments**: Text field for comments related to your access request</span></span>

5. <span data-ttu-id="7d749-p112">Seleccione **Guardar** y, a continuación, en **Cerrar**. La solicitud se enviará al grupo del aprobador a través de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="7d749-p112">Select **Save** and then **Close**. Your request will be sent to the approver's group via email.</span></span>

#### <a name="using-exchange-management-powershell"></a><span data-ttu-id="7d749-186">Uso de PowerShell de administración de Exchange</span><span class="sxs-lookup"><span data-stu-id="7d749-186">Using Exchange Management PowerShell</span></span>

<span data-ttu-id="7d749-187">Ejecute el siguiente comando en Exchange Online PowerShell para crear y enviar una solicitud de aprobación al grupo del aprobador:</span><span class="sxs-lookup"><span data-stu-id="7d749-187">Run the following command in Exchange Online PowerShell to create and submit an approval request to the approver's group:</span></span>
```
New-ElevatedAccessRequest -Task 'Exchange\<exchange management cmdlet name>' -Reason '<appropriate reason>' -DurationHours <duration in hours>
```
<span data-ttu-id="7d749-188">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="7d749-188">Example:</span></span>
```
New-ElevatedAccessRequest -Task 'Exchange\New-MoveRequest' -Reason 'Attempting to fix the user mailbox error' -DurationHours 4
```
### <a name="view-status-of-elevation-requests"></a><span data-ttu-id="7d749-189">Ver el estado de las solicitudes de elevación</span><span class="sxs-lookup"><span data-stu-id="7d749-189">View status of elevation requests</span></span>
<span data-ttu-id="7d749-190">Una vez creada una solicitud de aprobación, puede revisar el estado de la solicitud de elevación en el centro de administración o en Exchange identificador de PowerShell de administración mediante el asociado con la solicitud.</span><span class="sxs-lookup"><span data-stu-id="7d749-190">After an approval request is created, elevation request status can be reviewed in the Admin Center or in Exchange Management PowerShell using the associated with request ID.</span></span>

#### <a name="using-the-microsoft-365-admin-center"></a><span data-ttu-id="7d749-191">Desde el centro de administración de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="7d749-191">Using the Microsoft 365 Admin Center</span></span>

1. <span data-ttu-id="7d749-192">Inicie sesión en el [Centro de administración de Microsoft 365](https://portal.office.com) con sus credenciales.</span><span class="sxs-lookup"><span data-stu-id="7d749-192">Sign into the [Microsoft 365 Admin Center](https://portal.office.com) using your credentials.</span></span>

2. <span data-ttu-id="7d749-193">En el centro de administración, vaya a **configuración de** > **de seguridad y privacidad** > **con privilegios de acceso**.</span><span class="sxs-lookup"><span data-stu-id="7d749-193">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="7d749-194">Seleccione **las solicitudes y administrar las directivas de acceso**.</span><span class="sxs-lookup"><span data-stu-id="7d749-194">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="7d749-195">Seleccione **la vista** para filtrar las solicitudes enviadas por estado **pendientes**, **aprobado**, **denegado**o **Caja de seguridad del cliente** .</span><span class="sxs-lookup"><span data-stu-id="7d749-195">Select **View** to filter submitted requests by **Pending**, **Approved**, **Denied**, or **Customer Lockbox** status.</span></span>

#### <a name="using-exchange-management-powershell"></a><span data-ttu-id="7d749-196">Uso de PowerShell de administración de Exchange</span><span class="sxs-lookup"><span data-stu-id="7d749-196">Using Exchange Management PowerShell</span></span>

<span data-ttu-id="7d749-197">Ejecute el siguiente comando en Exchange Online PowerShell para ver el estado de la solicitud de aprobación para un identificador de solicitud específico:</span><span class="sxs-lookup"><span data-stu-id="7d749-197">Run the following command in Exchange Online PowerShell to view a approval request status for a specific request ID:</span></span>
```
Get-ElevatedAccessRequest -Identity <request ID> | select RequestStatus
```
<span data-ttu-id="7d749-198">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="7d749-198">Example:</span></span>
```
Get-ElevatedAccessRequest -Identity 28560ed0-419d-4cc3-8f5b-603911cbd450 | select RequestStatus
```

### <a name="approving-an-elevation-authorization-request"></a><span data-ttu-id="7d749-199">Aprobación de una solicitud de autorización de elevación</span><span class="sxs-lookup"><span data-stu-id="7d749-199">Approving an elevation authorization request</span></span>
<span data-ttu-id="7d749-p113">Cuando se crea una solicitud de aprobación, los miembros del grupo de aprobadores relevantes recibirán una notificación de correo electrónico y pueden aprobar la solicitud asociada con el identificador de solicitud. El solicitante recibirá una notificación de la aprobación de la solicitud o la denegación a través del mensaje de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="7d749-p113">When an approval request is created, members of the relevant approver group will receive an email notification and can approve the request associated with the request ID. The requestor will be notified of the request approval or denial via email message.</span></span>

#### <a name="using-the-microsoft-365-admin-center"></a><span data-ttu-id="7d749-202">Desde el centro de administración de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="7d749-202">Using the Microsoft 365 Admin Center</span></span>

1. <span data-ttu-id="7d749-203">Inicie sesión en el [Centro de administración de Microsoft 365](https://portal.office.com) con sus credenciales.</span><span class="sxs-lookup"><span data-stu-id="7d749-203">Sign into the [Microsoft 365 Admin Center](https://portal.office.com) using your credentials.</span></span>

2. <span data-ttu-id="7d749-204">En el centro de administración, vaya a **configuración de** > **de seguridad y privacidad** > **con privilegios de acceso**.</span><span class="sxs-lookup"><span data-stu-id="7d749-204">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="7d749-205">Seleccione **las solicitudes y administrar las directivas de acceso**.</span><span class="sxs-lookup"><span data-stu-id="7d749-205">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="7d749-206">Seleccione una solicitud enumerada para ver los detalles y tomar medidas en la solicitud.</span><span class="sxs-lookup"><span data-stu-id="7d749-206">Select a listed request to view the details and to take action on the request.</span></span>

5. <span data-ttu-id="7d749-p114">Seleccione **Aprobar** para aprobar la solicitud o seleccione **Denegar** para denegar la solicitud. Anteriormente las solicitudes aprobadas pueden tener acceso revocado seleccionando **revocar**.</span><span class="sxs-lookup"><span data-stu-id="7d749-p114">Select **Approve** to approve the request or select **Deny** to deny the request. Previously approved requests can have access revoked by selecting **Revoke**.</span></span>

#### <a name="using-exchange-management-powershell"></a><span data-ttu-id="7d749-209">Uso de PowerShell de administración de Exchange</span><span class="sxs-lookup"><span data-stu-id="7d749-209">Using Exchange Management PowerShell</span></span>

<span data-ttu-id="7d749-210">Ejecute el siguiente comando en Exchange Online PowerShell para aprobar una solicitud de autorización de elevación:</span><span class="sxs-lookup"><span data-stu-id="7d749-210">Run the following command in Exchange Online PowerShell to approve an elevation authorization request:</span></span>

```
Approve-ElevatedAccessRequest -RequestId <request id> -Comment '<approval comment>'
```
<span data-ttu-id="7d749-211">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="7d749-211">Example:</span></span>
```
Approve-ElevatedAccessRequest -RequestId a4bc1bdf-00a1-42b4-be65-b6c63d6be279 -Comment '<approval comment>'
```

<span data-ttu-id="7d749-212">Ejecute el siguiente comando en Exchange Online PowerShell para denegar una solicitud de autorización de elevación:</span><span class="sxs-lookup"><span data-stu-id="7d749-212">Run the following command in Exchange Online PowerShell to deny an elevation authorization request:</span></span>

```
Deny-ElevatedAccessRequest -RequestId <request id> -Comment '<denial comment>'
```
<span data-ttu-id="7d749-213">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="7d749-213">Example:</span></span>
```
Deny-ElevatedAccessRequest -RequestId a4bc1bdf-00a1-42b4-be65-b6c63d6be279 -Comment '<denial comment>'
```

## <a name="delete-a-privileged-access-policy-in-office-365"></a><span data-ttu-id="7d749-214">Eliminar una directiva de acceso con privilegios en Office 365</span><span class="sxs-lookup"><span data-stu-id="7d749-214">Delete a privileged access policy in Office 365</span></span>
<span data-ttu-id="7d749-215">Puede eliminar una directiva de acceso con privilegios si ya no es necesario en la organización.</span><span class="sxs-lookup"><span data-stu-id="7d749-215">You can delete a privileged access policy if it is no longer needed in your organization.</span></span>

### <a name="using-the-microsoft-365-admin-center"></a><span data-ttu-id="7d749-216">Desde el centro de administración de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="7d749-216">Using the Microsoft 365 Admin Center</span></span>

1. <span data-ttu-id="7d749-217">Inicie sesión en el [Centro de administración de Microsoft 365](https://portal.office.com) de uso de credenciales para una cuenta de administrador de la organización.</span><span class="sxs-lookup"><span data-stu-id="7d749-217">Sign into the [Microsoft 365 Admin Center](https://portal.office.com) using credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="7d749-218">En el centro de administración, vaya a **configuración de** > **de seguridad y privacidad** > **con privilegios de acceso**.</span><span class="sxs-lookup"><span data-stu-id="7d749-218">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="7d749-219">Seleccione **las solicitudes y administrar las directivas de acceso**.</span><span class="sxs-lookup"><span data-stu-id="7d749-219">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="7d749-220">Seleccione **la configuración de directivas**.</span><span class="sxs-lookup"><span data-stu-id="7d749-220">Select **Configure policies**.</span></span>

5. <span data-ttu-id="7d749-221">Seleccione la directiva que desea eliminar y, a continuación, seleccione **Eliminar directiva**.</span><span class="sxs-lookup"><span data-stu-id="7d749-221">Select the policy you want to delete, then select **Remove Policy**.</span></span>

6. <span data-ttu-id="7d749-222">Seleccione **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="7d749-222">Select **Close**.</span></span>

### <a name="using-exchange-management-powershell"></a><span data-ttu-id="7d749-223">Uso de PowerShell de administración de Exchange</span><span class="sxs-lookup"><span data-stu-id="7d749-223">Using Exchange Management PowerShell</span></span>

<span data-ttu-id="7d749-224">Ejecute el siguiente comando en Exchange Online Powershell para eliminar una directiva de acceso con privilegios:</span><span class="sxs-lookup"><span data-stu-id="7d749-224">Run the following command in Exchange Online Powershell to delete a privileged access policy:</span></span>

```
Remove-ElevatedAccessApprovalPolicy -Identity <identity GUID of the policy you want to delete>
```

## <a name="disable-privileged-access-in-office-365"></a><span data-ttu-id="7d749-225">Deshabilitar el acceso con privilegios en Office 365</span><span class="sxs-lookup"><span data-stu-id="7d749-225">Disable privileged access in Office 365</span></span>

<span data-ttu-id="7d749-p115">Si es necesario, puede deshabilitar la administración con privilegios de acceso para la organización. Deshabilitar con privilegios de acceso no eliminar cualquier las directivas de aprobación asociada o grupos de aprobador.</span><span class="sxs-lookup"><span data-stu-id="7d749-p115">If needed, you can disable privileged access management for your organization. Disabling privileged access does not delete any associated approval policies or approver groups.</span></span>

### <a name="using-the-microsoft-365-admin-center"></a><span data-ttu-id="7d749-228">Desde el centro de administración de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="7d749-228">Using the Microsoft 365 Admin Center</span></span>

1. <span data-ttu-id="7d749-229">Inicie sesión en el [Centro de administración de Microsoft 365](https://portal.office.com) de uso de credenciales para una cuenta de administrador de la organización.</span><span class="sxs-lookup"><span data-stu-id="7d749-229">Sign into the [Microsoft 365 Admin Center](https://portal.office.com) using credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="7d749-230">En el centro de administración, vaya a **configuración de** > **de seguridad y privacidad** > **con privilegios de acceso**.</span><span class="sxs-lookup"><span data-stu-id="7d749-230">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="7d749-231">Habilitar el control **requieren aprobaciones para el acceso con privilegios** .</span><span class="sxs-lookup"><span data-stu-id="7d749-231">Enable the **Require approvals for privileged access** control.</span></span>

### <a name="using-exchange-management-powershell"></a><span data-ttu-id="7d749-232">Uso de PowerShell de administración de Exchange</span><span class="sxs-lookup"><span data-stu-id="7d749-232">Using Exchange Management PowerShell</span></span>

<span data-ttu-id="7d749-233">Ejecute el siguiente comando en Exchange Online Powershell para deshabilitar el acceso con privilegios:</span><span class="sxs-lookup"><span data-stu-id="7d749-233">Run the following command in Exchange Online Powershell to disable privileged access:</span></span>

```
Disable-ElevatedAccessControl
```