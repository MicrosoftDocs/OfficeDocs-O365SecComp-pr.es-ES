---
title: Configuración de la administración del acceso con privilegios en Office 365
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
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
ms.openlocfilehash: 46bfeaf0c73c4598fcdaa65d654201620396600c
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/17/2019
ms.locfileid: "34157422"
---
# <a name="configuring-privileged-access-management-in-office-365"></a>Configuración de la administración del acceso con privilegios en Office 365

> [!IMPORTANT]
> En este tema se tratan las instrucciones de implementación y configuración de las características disponibles actualmente en Office 365 E5 y las SKU de cumplimiento avanzado.

Este tema le guiará a través de la habilitación y configuración de la administración del acceso con privilegios en su organización de Office 365. Puede usar tanto el centro de administración de Microsoft 365 como PowerShell de administración de Exchange para administrar y usar el acceso con privilegios. 

## <a name="enable-and-configure-privileged-access-management"></a>Habilitación y configuración de la administración del acceso con privilegios

Siga estos pasos para configurar y usar el acceso con privilegios en su organización de Office 365:

- [Paso 1: crear un grupo de aprobadores](privileged-access-management-configuration.md#step1)

    Antes de empezar a usar el acceso de privilegios, determine quién necesita autoridad de aprobación para el acceso a las tareas elevadas y privilegiadas. Cualquier usuario que forme parte del grupo de aprobadores puede aprobar solicitudes de acceso. Para habilitarlo, cree un grupo de seguridad habilitado para correo en Office 365.

- [Paso 2: habilitar el acceso con privilegios](privileged-access-management-configuration.md#step2)

    El acceso con privilegios debe estar habilitado explícitamente en Office 365 con el grupo de aprobador predeterminado, incluido un conjunto de cuentas del sistema que desea excluir del control de acceso privilegiado de la administración de acceso.

- [Paso 3: crear una directiva de acceso](privileged-access-management-configuration.md#step3)

    La creación de una directiva de aprobación permite definir los requisitos de aprobación específicos en el ámbito de tareas individuales. Las opciones de tipo de aprobación son **auto** o **manual**.

- [Paso 4: enviar o aprobar solicitudes de acceso privilegiadas](privileged-access-management-configuration.md#step4)

    Una vez habilitado, el acceso con privilegios requiere aprobaciones para cualquier tarea que tenga definida una directiva de aprobación asociada. Para las tareas incluidas en una directiva de aprobación, los usuarios deben solicitar y recibir la aprobación de acceso para disponer de los permisos necesarios para ejecutar la tarea.

Una vez que se haya concedido la aprobación, el usuario que realiza la solicitud puede ejecutar la tarea deseada y el acceso privilegiado autorizará y ejecutará la tarea en nombre del usuario. La aprobación sigue siendo válida durante la duración solicitada (la duración predeterminada es de 4 horas), durante el cual el solicitante puede ejecutar la tarea deseada varias veces. Todas estas ejecuciones se registran y están disponibles para la auditoría de seguridad y cumplimiento. 

> [!NOTE]
> Si desea usar el PowerShell de administración de Exchange para habilitar y configurar el acceso con privilegios, siga los pasos descritos en [Connect to Exchange Online PowerShell Using multi-factor Authentication](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/mfa-connect-to-exchange-online-powershell?view=exchange-ps) to Connect to Exchange Online PowerShell with your Office 365 necesarias. No es necesario habilitar la autenticación multifactor para su organización de Office 365 para usar los pasos para habilitar el acceso privilegiado mientras se conecta a Exchange Online PowerShell. La conexión con la autenticación multifactor crea un token de OAuth que se usa en el acceso con privilegios para firmar las solicitudes.

<a name="step1"> </a>

## <a name="step-1-create-an-approvers-group"></a>Paso 1: crear un grupo de aprobadores

1. Inicie sesión en el [centro de administración de Microsoft 365](https://admin.microsoft.com) con las credenciales de una cuenta de administrador en la organización.

2. En el centro de administración, vaya a **grupos** > **Agregar un grupo**.

3. Seleccione **grupo de seguridad habilitado para correo** y, a continuación, complete los campos **nombre**, **dirección de correo electrónico de grupo**y **Descripción** para el nuevo grupo.

4. Guarde el grupo. Puede tardar unos minutos para que el grupo esté totalmente configurado y aparezca en el centro de administración de 365 de Microsoft.

5. Seleccione el grupo del nuevo aprobador y seleccione **Editar** para agregar usuarios al grupo.

6. Guarde el grupo.

<a name="step2"> </a>

## <a name="step-2-enable-privileged-access"></a>Paso 2: habilitar el acceso con privilegios

### <a name="in-the-microsoft-365-admin-center"></a>En el centro de administración de Microsoft 365

1. Inicie sesión en el [centro de administración de Microsoft 365](https://admin.microsoft.com) con las credenciales de una cuenta de administrador en la organización.

2. En el centro de administración, vaya a **configuración > seguridad** > de**privilegios**de privacidad &.

3. Habilite el control **de acceso requerir aprobaciones para privilegios** .

4. Asigne el grupo de aprobador que ha creado en el paso 1 como el **Grupo aprobadores**predeterminados.

5. **Guarde** y **cierre**.

### <a name="in-exchange-management-powershell"></a>En Exchange Management PowerShell

Para habilitar el acceso privilegiado y asignar el grupo del aprobador, ejecute el siguiente comando en Exchange Online PowerShell:
```
Enable-ElevatedAccessControl -AdminGroup '<default approver group>' -SystemAccounts @('<systemAccountUPN1>','<systemAccountUPN2>')
```
Ejemplo:
```
Enable-ElevatedAccessControl -AdminGroup 'pamapprovers@fabrikam.onmicrosoft.com' -SystemAccounts @('sys1@fabrikamorg.onmicrosoft.com', sys2@fabrikamorg.onmicrosoft.com')
```

> [!NOTE]
> La característica cuentas del sistema está disponible para garantizar que determinadas automatización de las organizaciones puedan funcionar sin dependencia en el acceso con privilegios, pero se recomienda que esas exclusiones sean excepcionales y que se puedan aprobar y auditar. periódicamente.

<a name="step3"> </a>

## <a name="step-3-create-an-access-policy"></a>Paso 3: crear una directiva de acceso

Puede crear y configurar hasta 30 directivas de acceso privilegiadas para su organización de Office 365.

### <a name="in-the-microsoft-365-admin-center"></a>En el centro de administración de Microsoft 365

1. Inicie sesión en el [centro de administración de Microsoft 365](https://admin.microsoft.com) con las credenciales de una cuenta de administrador en la organización.

2. En el centro de administración, vaya a **configuración** > **seguridad &** > **acceso privilegiado a**la privacidad.

3. Seleccione **Administrar directivas y solicitudes de acceso**.

4. Seleccione **configurar directivas** y seleccione **Agregar una directiva**.

5. En los campos desplegables, seleccione los valores adecuados para su organización:
    
    **Tipo de directiva**: tarea, rol o grupo de roles

    **Ámbito de directiva**: Exchange

    **Nombre de directiva**: Seleccione una de las directivas disponibles

    **Tipo de aprobación**: manual o automático

    **Grupo de aprobación**: seleccione el grupo aprobadores creado en el paso 1.

6. Seleccione **crear** y, a continuación, **cerrar**. La Directiva puede tardar unos minutos en estar totalmente configurada y habilitada.

### <a name="in-exchange-management-powershell"></a>En Exchange Management PowerShell

Para crear y definir una directiva de aprobación, ejecute el siguiente comando en Exchange Online PowerShell:

```
New-ElevatedAccessApprovalPolicy -Task 'Exchange\<exchange management cmdlet name>' -ApprovalType <Manual, Auto> -ApproverGroup '<default/custom approver group>'
```
Ejemplo:
```
New-ElevatedAccessApprovalPolicy -Task 'Exchange\New-MoveRequest' -ApprovalType Manual -ApproverGroup 'mbmanagers@fabrikamorg.onmicrosoft.com'
```

<a name="step4"> </a>

## <a name="step-4-submitapprove-privileged-access-requests"></a>Paso 4: enviar o aprobar solicitudes de acceso privilegiadas

### <a name="requesting-elevation-authorization-to-execute-privileged-tasks"></a>Solicitar autorización de elevación para ejecutar tareas privilegiadas

Las solicitudes de acceso con privilegios son válidas durante un máximo de 24 horas después de que se envíe la solicitud. Si no se aprueba o se rechaza, las solicitudes expiran y el acceso no se aprueba.

#### <a name="in-the-microsoft-365-admin-center"></a>En el centro de administración de Microsoft 365

1. Inicie sesión en el [centro de administración de Microsoft 365](https://admin.microsoft.com) con sus credenciales.

2. En el centro de administración, vaya a **configuración** > **seguridad &** > **acceso privilegiado a**la privacidad.

3. Seleccione **Administrar directivas y solicitudes de acceso**.

4. Seleccione **nueva solicitud**. En los campos desplegables, seleccione los valores adecuados para su organización:

    **Tipo de solicitud**: tarea, rol o grupo de roles

    **Ámbito de solicitud**: Exchange

    **Solicitud de**: Seleccione una de las directivas disponibles

    **Duración (horas)**: número de horas de acceso solicitado. No hay un límite en el número de horas que se puede solicitar.

    **Comentarios**: campo de texto para comentarios relacionados con la solicitud de acceso

5. Seleccione **Guardar** y, a continuación, **cerrar**. La solicitud se enviará al grupo del aprobador a través del correo electrónico.

#### <a name="in-exchange-management-powershell"></a>En Exchange Management PowerShell

Ejecute el siguiente comando en Exchange Online PowerShell para crear y enviar una solicitud de aprobación al grupo del aprobador:
```
New-ElevatedAccessRequest -Task 'Exchange\<exchange management cmdlet name>' -Reason '<appropriate reason>' -DurationHours <duration in hours>
```
Ejemplo:
```
New-ElevatedAccessRequest -Task 'Exchange\New-MoveRequest' -Reason 'Attempting to fix the user mailbox error' -DurationHours 4
```
### <a name="view-status-of-elevation-requests"></a>Ver el estado de las solicitudes de elevación
Después de crear una solicitud de aprobación, el estado de la solicitud de elevación se puede revisar en el centro de administración o en PowerShell de administración de Exchange con el identificador de solicitud asociado.

#### <a name="in-the-microsoft-365-admin-center"></a>En el centro de administración de Microsoft 365

1. Inicie sesión en el [centro de administración de Microsoft 365](https://admin.microsoft.com) con sus credenciales.

2. En el centro de administración, vaya a **configuración** > **seguridad &** > **acceso privilegiado a**la privacidad.

3. Seleccione **Administrar directivas y solicitudes de acceso**.

4. Seleccione **Ver** para filtrar las solicitudes enviadas por estado **pendiente**, **aprobado**, denegado o de caja de **caja del cliente** . ****

#### <a name="in-exchange-management-powershell"></a>En Exchange Management PowerShell

Ejecute el siguiente comando en Exchange Online PowerShell para ver el estado de la solicitud de aprobación de un identificador de solicitud específico:
```
Get-ElevatedAccessRequest -Identity <request ID> | select RequestStatus
```
Ejemplo:
```
Get-ElevatedAccessRequest -Identity 28560ed0-419d-4cc3-8f5b-603911cbd450 | select RequestStatus
```

### <a name="approving-an-elevation-authorization-request"></a>Aprobación de una solicitud de autorización de elevación
Cuando se crea una solicitud de aprobación, los miembros del grupo aprobador relevante reciben una notificación por correo electrónico y pueden aprobar la solicitud asociada con el identificador de solicitud. El solicitante recibe la notificación de la aprobación o la denegación de la solicitud mediante un mensaje de correo electrónico.

#### <a name="in-the-microsoft-365-admin-center"></a>En el centro de administración de Microsoft 365

1. Inicie sesión en el [centro de administración de Microsoft 365](https://admin.microsoft.com) con sus credenciales.

2. En el centro de administración, vaya a **configuración** > **seguridad &** > **acceso privilegiado a**la privacidad.

3. Seleccione **Administrar directivas y solicitudes de acceso**.

4. Seleccione una solicitud de la lista para ver los detalles y realizar la acción en la solicitud.

5. Seleccione **aprobar** para aprobar la solicitud o seleccione **denegar** para denegar la solicitud. Las solicitudes aprobadas anteriormente pueden revocar el acceso mediante la selección de **REVOKE**.

#### <a name="in-exchange-management-powershell"></a>En Exchange Management PowerShell

Para aprobar una solicitud de autorización de elevación, ejecute el siguiente comando en Exchange Online PowerShell:

```
Approve-ElevatedAccessRequest -RequestId <request id> -Comment '<approval comment>'
```
Ejemplo:
```
Approve-ElevatedAccessRequest -RequestId a4bc1bdf-00a1-42b4-be65-b6c63d6be279 -Comment '<approval comment>'
```

Para denegar una solicitud de autorización de elevación, ejecute el siguiente comando en Exchange Online PowerShell:

```
Deny-ElevatedAccessRequest -RequestId <request id> -Comment '<denial comment>'
```
Ejemplo:
```
Deny-ElevatedAccessRequest -RequestId a4bc1bdf-00a1-42b4-be65-b6c63d6be279 -Comment '<denial comment>'
```

## <a name="delete-a-privileged-access-policy-in-office-365"></a>Eliminar una directiva de acceso privilegiada en Office 365
Si ya no es necesario en su organización, puede eliminar una directiva de acceso privilegiado.

### <a name="in-the-microsoft-365-admin-center"></a>En el centro de administración de Microsoft 365

1. Inicie sesión en el [centro de administración de Microsoft 365](https://admin.microsoft.com) con las credenciales de una cuenta de administrador en la organización.

2. En el centro de administración, vaya a **configuración** > **seguridad &** > **acceso privilegiado a**la privacidad.

3. Seleccione **Administrar directivas y solicitudes de acceso**.

4. Seleccione **configurar directivas**.

5. Seleccione la Directiva que desea eliminar y, a continuación, seleccione **quitar Directiva**.

6. Seleccione **Cerrar**.

### <a name="in-exchange-management-powershell"></a>En Exchange Management PowerShell

Para eliminar una directiva de acceso privilegiada, ejecute el siguiente comando en Exchange Online PowerShell:

```
Remove-ElevatedAccessApprovalPolicy -Identity <identity GUID of the policy you want to delete>
```

## <a name="disable-privileged-access-in-office-365"></a>Deshabilitar el acceso privilegiado en Office 365

Si es necesario, puede deshabilitar la administración del acceso con privilegios para su organización. La deshabilitación del acceso con privilegios no elimina ninguna directiva de aprobación o grupo de aprobador asociado.

### <a name="in-the-microsoft-365-admin-center"></a>En el centro de administración de Microsoft 365

1. Inicie sesión en el [centro de administración de Microsoft 365](https://admin.microsoft.com) con las credenciales de una cuenta de administrador en la organización.

2. En el centro de administración, vaya a **configuración** > **seguridad &** > **acceso privilegiado a**la privacidad.

3. Habilite el control **de acceso requerir aprobaciones para privilegios** .

### <a name="in-exchange-management-powershell"></a>En Exchange Management PowerShell

Para deshabilitar el acceso privilegiado, ejecute el siguiente comando en Exchange Online PowerShell:

```
Disable-ElevatedAccessControl
```