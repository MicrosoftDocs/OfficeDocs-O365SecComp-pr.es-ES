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
ms.openlocfilehash: 47cae93a41b0fd60645021f6f299645777a9a2e1
ms.sourcegitcommit: c168410974bc90aaf55f1dcaa9e05c09b2b78d76
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/25/2018
ms.locfileid: "25011846"
---
# <a name="configuring-privileged-access-management-in-office-365"></a>Configuración de administración de acceso con privilegios en Office 365

> [!IMPORTANT]
> En este tema se trata instrucciones de implementación y configuración para características sólo actualmente disponibles en Office 365 E5 y avanzada SKU de cumplimiento.

En este tema le guiará a través de habilitar y configurar la administración del acceso con privilegios en su organización de Office 365. Puede usar cualquiera el el centro de administración de Microsoft 365 o Exchange Management PowerShell para administrar y usar privilegios de acceso. 

## <a name="enable-and-configure-privileged-access-management"></a>Habilitar y configurar la administración con privilegios de acceso

Siga estos pasos para configurar y utilizar con privilegios de acceso de la organización de Office 365:

- [Paso 1: Crear el grupo del aprobador](privileged-access-management-configuration.md#step1)

    Antes de empezar a usar acceso con privilegios, determinar quién tendrá la autoridad de aprobación para las solicitudes entrantes para el acceso a las tareas con privilegios elevados y con privilegios. Cualquier usuario que forma parte del grupo de los aprobadores podrán aprobar las solicitudes de acceso. Esto se habilita mediante la creación de un grupo de seguridad habilitados para correo en Office 365.

- [Paso 2: Habilitar el acceso con privilegios](privileged-access-management-configuration.md#step2)

    Acceso con privilegios debe habilitarse explícitamente en Office 365 con el grupo de aprobadores predeterminada y, incluido un conjunto de cuentas del sistema que desea que se deben excluir desde el control de acceso de administración con privilegios de acceso.

- [Paso 3: Crear una directiva de acceso](privileged-access-management-configuration.md#step3)

    Creación de una directiva de aprobación le permite definir los requisitos de aprobación específico con ámbito en tareas individuales. Las opciones de tipo de aprobación son **automático** o **Manual**.

- [Paso 4: Enviar y aprobar las solicitudes de acceso con privilegios](privileged-access-management-configuration.md#step4)

    Una vez habilitado, con privilegios de acceso requiere aprobaciones para ejecutar cualquier tarea que tiene una directiva de aprobación asociada definida. Los usuarios que necesiten ejecutar tareas incluidas en la una directiva de aprobación debe solicitar y recibir aprobación de acceso con el fin de tener los permisos necesarios para ejecutar la tarea.

Una vez se concede la aprobación, el usuario solicitante puede ejecutar la tarea prevista y va a autorizar y ejecutar la tarea en nombre de los usuarios con privilegios de acceso. La aprobación sigue siendo válida para el solicitado duración (duración predeterminada es de 4 horas), durante el cual el solicitante puede ejecutar la tarea prevista varias veces. Todas esas ejecuciones se registran y a disposición de cumplimiento de normas de auditoría y seguridad. 

> [!NOTE]
> Si desea usar PowerShell de administración de Exchange para habilitar y configurar el acceso con privilegios, siga los pasos de [conectarse a Exchange Online PowerShell mediante autenticación multifactor](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/mfa-connect-to-exchange-online-powershell?view=exchange-ps) para conectarse a Exchange Online PowerShell con Office 365 credenciales. No es necesario habilitar la autenticación multifactor para su organización de Office 365 usar los pasos para habilitar el acceso con privilegios mientras se conecta a Exchange Online PowerShell. Conectar con la autenticación multifactor crea un token de OAuth que se usa en el acceso con privilegios para las solicitudes de firma.

<a name="step1"> </a>

## <a name="step-1---create-an-approvers-group"></a>Paso 1: crear el grupo del aprobador

1. Inicie sesión en el [Centro de administración de Microsoft 365](https://portal.office.com) de uso de credenciales para una cuenta de administrador de la organización.

2. En el centro de administración, vaya a **grupos** > **Agregar un grupo**.

3. Seleccione el tipo de grupo de **grupo de seguridad habilitados para correo** y, a continuación, complete los campos **nombre**, **dirección de correo electrónico de grupo**y **Descripción** para el nuevo grupo.

4. Guarde el grupo. Puede tardar unos minutos para el grupo configurarse completamente y aparezca en el centro de administración de Office 365.

5. Seleccione grupo de aprobadores nuevo y seleccione **Editar** para agregar usuarios al grupo.

6. Guarde el grupo.

<a name="step2"> </a>

## <a name="step-2---enable-privileged-access"></a>Paso 2: habilitar el acceso con privilegios

### <a name="using-the-microsoft-365-admin-center"></a>Desde el centro de administración de Microsoft 365

1. Inicie sesión en el [Centro de administración de Microsoft 365](https://portal.office.com) de uso de credenciales para una cuenta de administrador de la organización.

2. En el centro de administración, vaya a **Configuración > seguridad y privacidad** > **con privilegios de acceso**.

3. Habilitar el control **requieren aprobaciones para el acceso con privilegios** .

4. Asignar a grupo del aprobador que creó en el paso 1 como el **grupo de aprobadores predeterminado**.

5. **Guardar** y **Cerrar**.

### <a name="using-exchange-management-powershell"></a>Uso de PowerShell de administración de Exchange

En Exchange Online PowerShell para habilitar el acceso con privilegios y para asignar el grupo de aprobadores, ejecute el siguiente comando:
```
Enable-ElevatedAccessControl -AdminGroup '<default approver group>' -SystemAccounts @('<systemAccountUPN1>','<systemAccountUPN2>')
```
Ejemplo:
```
Enable-ElevatedAccessControl -AdminGroup 'pamapprovers@fabrikam.onmicrosoft.com' -SystemAccounts @('sys1@fabrikamorg.onmicrosoft.com', sys2@fabrikamorg.onmicrosoft.com')
```

> [!NOTE]
> Cuentas del sistema característica está disponible para asegurarse de determinados automations dentro de las organizaciones pueden trabajar sin dependencia en acceso con privilegios, sin embargo, se recomienda que estas exclusiones se excepcionales y los autorizados deben aprobados y auditar con regularidad.

<a name="step3"> </a>

## <a name="step-3---create-an-access-policy"></a>Paso 3: crear una directiva de acceso

Puede crear y configurar directivas de acceso con privilegios de hasta 30 para su organización de Office 365.

### <a name="using-the-microsoft-365-admin-center"></a>Desde el centro de administración de Microsoft 365

1. Inicie sesión en el [Centro de administración de Microsoft 365](https://portal.office.com) de uso de credenciales para una cuenta de administrador de la organización.

2. En el centro de administración, vaya a **configuración de** > **de seguridad y privacidad** > **con privilegios de acceso**.

3. Seleccione **las solicitudes y administrar las directivas de acceso**.

4. Seleccione **la configuración de directivas** y seleccione **Agregar una directiva**.

5. En los campos de lista desplegable, seleccione los valores apropiados para su organización:
    
    **Tipo de directiva**: tarea, rol o grupo de roles

    **Ámbito de directiva**: Exchange u Office 365

    **Nombre de la directiva**: seleccione de las directivas disponibles

    **Tipo de aprobación**: Manual o automático

    **Grupo de aprobación**: seleccione el grupo de aprobadores que creó en el paso 1

6. Seleccione **crear** y, a continuación, en **Cerrar**. Puede tardar unos minutos para la directiva ser totalmente configurado y habilitado.

### <a name="using-exchange-management-powershell"></a>Uso de PowerShell de administración de Exchange

Ejecute el siguiente comando en Exchange Online PowerShell para crear y definir una directiva de aprobación:

```
New-ElevatedAccessApprovalPolicy -Task 'Exchange\<exchange management cmdlet name>' -ApprovalType <Manual, Auto> -ApproverGroup '<default/custom approver group>'
```
Ejemplo:
```
New-ElevatedAccessApprovalPolicy -Task 'Exchange\New-MoveRequest' -ApprovalType Manual -ApproverGroup 'mbmanagers@fabrikamorg.onmicrosoft.com'
```

<a name="step4"> </a>

## <a name="step-4-submitapprove-privileged-access-requests"></a>Paso 4: Enviar y aprobar las solicitudes de acceso con privilegios

### <a name="requesting-elevation-authorization-to-execute-privileged-tasks"></a>Solicitud de autorización de elevación para ejecutar tareas con privilegios

Las solicitudes de acceso con privilegios son válidas durante 24 horas después de que se envía la solicitud. Si no aprobadas o rechazadas, las solicitudes de punto de expirar y acceso no está aprobado.

#### <a name="using-the-microsoft-365-admin-center"></a>Desde el centro de administración de Microsoft 365

1. Inicie sesión en el [Centro de administración de Microsoft 365](https://portal.office.com) con sus credenciales.

2. En el centro de administración, vaya a **configuración de** > **de seguridad y privacidad** > **con privilegios de acceso**.

3. Seleccione **las solicitudes y administrar las directivas de acceso**.

4. Seleccione **nueva solicitud**. En los campos de lista desplegable, seleccione los valores apropiados para su organización:

    **Tipo de solicitud**: tarea, rol o grupo de roles

    **Ámbito de solicitud**: Exchange

    **Solicitud para**: seleccione de las directivas disponibles

    **Duración (horas)**: número de horas de acceso solicitados. No hay un límite en el número de horas que se puede solicitar.

    **Comentarios**: campo de texto de comentarios relacionados con la solicitud de acceso

5. Seleccione **Guardar** y, a continuación, en **Cerrar**. La solicitud se enviará al grupo del aprobador a través de correo electrónico.

#### <a name="using-exchange-management-powershell"></a>Uso de PowerShell de administración de Exchange

Ejecute el siguiente comando en Exchange Online PowerShell para crear y enviar una solicitud de aprobación al grupo del aprobador:
```
New-ElevatedAccessRequest -Task 'Exchange\<exchange management cmdlet name>' -Reason '<appropriate reason>' -DurationHours <duration in hours>
```
Ejemplo:
```
New-ElevatedAccessRequest -Task 'Exchange\New-MoveRequest' -Reason 'Attempting to fix the user mailbox error' -DurationHours 4
```
### <a name="view-status-of-elevation-requests"></a>Ver el estado de las solicitudes de elevación
Una vez creada una solicitud de aprobación, puede revisar el estado de la solicitud de elevación en el centro de administración o en Exchange identificador de PowerShell de administración mediante el asociado con la solicitud.

#### <a name="using-the-microsoft-365-admin-center"></a>Desde el centro de administración de Microsoft 365

1. Inicie sesión en el [Centro de administración de Microsoft 365](https://portal.office.com) con sus credenciales.

2. En el centro de administración, vaya a **configuración de** > **de seguridad y privacidad** > **con privilegios de acceso**.

3. Seleccione **las solicitudes y administrar las directivas de acceso**.

4. Seleccione **la vista** para filtrar las solicitudes enviadas por estado **pendientes**, **aprobado**, **denegado**o **Caja de seguridad del cliente** .

#### <a name="using-exchange-management-powershell"></a>Uso de PowerShell de administración de Exchange

Ejecute el siguiente comando en Exchange Online PowerShell para ver el estado de la solicitud de aprobación para un identificador de solicitud específico:
```
Get-ElevatedAccessRequest -Identity <request ID> | select RequestStatus
```
Ejemplo:
```
Get-ElevatedAccessRequest -Identity 28560ed0-419d-4cc3-8f5b-603911cbd450 | select RequestStatus
```

### <a name="approving-an-elevation-authorization-request"></a>Aprobación de una solicitud de autorización de elevación
Cuando se crea una solicitud de aprobación, los miembros del grupo de aprobadores relevantes recibirán una notificación de correo electrónico y pueden aprobar la solicitud asociada con el identificador de solicitud. El solicitante recibirá una notificación de la aprobación de la solicitud o la denegación a través del mensaje de correo electrónico.

#### <a name="using-the-microsoft-365-admin-center"></a>Desde el centro de administración de Microsoft 365

1. Inicie sesión en el [Centro de administración de Microsoft 365](https://portal.office.com) con sus credenciales.

2. En el centro de administración, vaya a **configuración de** > **de seguridad y privacidad** > **con privilegios de acceso**.

3. Seleccione **las solicitudes y administrar las directivas de acceso**.

4. Seleccione una solicitud enumerada para ver los detalles y tomar medidas en la solicitud.

5. Seleccione **Aprobar** para aprobar la solicitud o seleccione **Denegar** para denegar la solicitud. Anteriormente las solicitudes aprobadas pueden tener acceso revocado seleccionando **revocar**.

#### <a name="using-exchange-management-powershell"></a>Uso de PowerShell de administración de Exchange

Ejecute el siguiente comando en Exchange Online PowerShell para aprobar una solicitud de autorización de elevación:

```
Approve-ElevatedAccessRequest -RequestId <request id> -Comment '<approval comment>'
```
Ejemplo:
```
Approve-ElevatedAccessRequest -RequestId a4bc1bdf-00a1-42b4-be65-b6c63d6be279 -Comment '<approval comment>'
```

Ejecute el siguiente comando en Exchange Online PowerShell para denegar una solicitud de autorización de elevación:

```
Deny-ElevatedAccessRequest -RequestId <request id> -Comment '<denial comment>'
```
Ejemplo:
```
Deny-ElevatedAccessRequest -RequestId a4bc1bdf-00a1-42b4-be65-b6c63d6be279 -Comment '<denial comment>'
```

## <a name="delete-a-privileged-access-policy-in-office-365"></a>Eliminar una directiva de acceso con privilegios en Office 365
Puede eliminar una directiva de acceso con privilegios si ya no es necesario en la organización.

### <a name="using-the-microsoft-365-admin-center"></a>Desde el centro de administración de Microsoft 365

1. Inicie sesión en el [Centro de administración de Microsoft 365](https://portal.office.com) de uso de credenciales para una cuenta de administrador de la organización.

2. En el centro de administración, vaya a **configuración de** > **de seguridad y privacidad** > **con privilegios de acceso**.

3. Seleccione **las solicitudes y administrar las directivas de acceso**.

4. Seleccione **la configuración de directivas**.

5. Seleccione la directiva que desea eliminar y, a continuación, seleccione **Eliminar directiva**.

6. Seleccione **Cerrar**.

### <a name="using-exchange-management-powershell"></a>Uso de PowerShell de administración de Exchange

Ejecute el siguiente comando en Exchange Online Powershell para eliminar una directiva de acceso con privilegios:

```
Remove-ElevatedAccessApprovalPolicy -Identity <identity GUID of the policy you want to delete>
```

## <a name="disable-privileged-access-in-office-365"></a>Deshabilitar el acceso con privilegios en Office 365

Si es necesario, puede deshabilitar la administración con privilegios de acceso para la organización. Deshabilitar con privilegios de acceso no eliminar cualquier las directivas de aprobación asociada o grupos de aprobador.

### <a name="using-the-microsoft-365-admin-center"></a>Desde el centro de administración de Microsoft 365

1. Inicie sesión en el [Centro de administración de Microsoft 365](https://portal.office.com) de uso de credenciales para una cuenta de administrador de la organización.

2. En el centro de administración, vaya a **configuración de** > **de seguridad y privacidad** > **con privilegios de acceso**.

3. Habilitar el control **requieren aprobaciones para el acceso con privilegios** .

### <a name="using-exchange-management-powershell"></a>Uso de PowerShell de administración de Exchange

Ejecute el siguiente comando en Exchange Online Powershell para deshabilitar el acceso con privilegios:

```
Disable-ElevatedAccessControl
```