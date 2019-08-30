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
# <a name="manage-groups-in-eop"></a>Administrar grupos en EOP

 Puede usar Exchange Online Protection (EOP) para crear grupos habilitados para correo para una organización de Exchange. También puede usar EOP para definir o actualizar propiedades de grupo que especifiquen su pertenencia, las direcciones de correo electrónico y otros aspectos de los grupos. Puede crear grupos de distribución y grupos de seguridad, según sus necesidades. Se pueden crear estos grupos usando el Centro de administración de Exchange (EAC) o a través de Windows PowerShell remoto.
  
## <a name="types-of-mail-enabled-groups"></a>Tipos de grupos habilitados para correo

Puede crear dos tipos de grupos para su organización de Exchange:
  
- Los grupos de distribución son colecciones de usuarios de correo electrónico, como un equipo u otro grupo ad hoc, que necesitan recibir o enviar correo electrónico sobre un área común de interés. Los grupos de distribución son exclusivamente para distribuir mensajes de correo electrónico. En EOP, un grupo de distribución hace referencia a cualquier grupo habilitado para correo, tenga o no un contexto de seguridad.

- Los grupos de seguridad son colecciones de usuarios de correo electrónico que necesitan permisos de acceso para los roles de administrador. Por ejemplo, quizás quiera dar a un grupo de usuarios específico permisos de rol de administrador para que puedan configurar opciones de correo no deseado y antimalware.

    > [!NOTE]
    > De forma predeterminada, en todos los grupos de seguridad con correo habilitado es necesario que todos los remitentes estén autenticados. De este modo se evita que remitentes externos envíen mensajes a grupos de seguridad con correo habilitado.
  
## <a name="before-you-begin"></a>Antes de empezar

- Deberá tener asignados permisos antes de poder llevar a cabo este procedimiento o procedimientos. Para ver qué permisos necesita, consulte el entrada "Grupos de distribución y grupos de seguridad " en el tema [Permisos de características en EOP](feature-permissions-in-eop.md).

- Para abrir el centro de administración de Exchange, vea [centro de administración de Exchange en Exchange Online Protection](../exchange-admin-center-in-exchange-online-protection-eop.md).

- Tenga en cuenta que al crear y administrar grupos mediante los cmdlets de PowerShell de Exchange Online Protection, es posible que se encuentre con limitaciones.

- Los procedimientos de PowerShell de este tema usan un método de procesamiento por lotes que da como resultado un retraso en la propagación de unos minutos antes de que los resultados de los comandos estén visibles.

- Para obtener información sobre cómo usar Windows PowerShell para conectarse a Exchange Online Protection, vea [conectarse a PowerShell de Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell?view=exchange-ps).

- Para obtener información acerca de los métodos abreviados de teclado que se pueden aplicar a los procedimientos de este tema, consulte [métodos abreviados de teclado para el centro de administración de Exchange en Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).

> [!TIP]
> ¿Problemas? Solicite ayuda en el foro de [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) . 
  
## <a name="create-a-group-in-the-eac"></a>Crear un grupo en el EAC

1. En el EAC, vaya a **** \> **grupos**de destinatarios.

2. Haga **** ![clic en nuevo](../media/ITPro-EAC-AddIcon.gif)icono Agregar y, a continuación, haga clic en **grupo de distribución** o **grupo de seguridad**, según sus necesidades.

3. En la página **nuevo grupo de distribución** o **nuevo grupo de seguridad** , configure las siguientes opciones:

   - **Nombre para mostrar**: escriba un nombre para mostrar que sea único en su organización y tenga sentido para los usuarios de EOP. El nombre para mostrar es un campo obligatorio.

   - **Alias**: escriba un alias de grupo de hasta 64 caracteres que sea único para su organización. Los usuarios de EOP escriben el alias en la línea Para: de los mensajes de correo electrónico, y el alias se resuelve en el nombre para mostrar del grupo. Si cambia el alias, la dirección SMTP principal del grupo también cambiará y contendrá el nuevo alias. El alias es obligatorio. 

   - **Descripción**: escriba una descripción del grupo para que los usuarios sepan el propósito del grupo. 

   - **Propietarios**: de forma predeterminada, la persona que crea el grupo es el propietario. Puede Agregar un propietario seleccionando **Agregar** ![icono](../media/ITPro-EAC-AddIcon.gif)de agregar. Todos los grupos deben tener al menos un propietario.

     > [!NOTE]
     > Los propietarios no tienen que ser miembros del grupo.
  
   - **Miembros**: Use esta sección para agregar miembros de grupo y especificar si la aprobación es necesaria para que los usuarios se unan al grupo o lo abandonen. Para agregar miembros al grupo, haga clic en **Agregar** ![icono](../media/ITPro-EAC-AddIcon.gif)de agregar.

4. Haga clic en **Aceptar** para volver a la página original.

5. Cuando haya terminado, haga clic en **Guardar** para crear el grupo. El nuevo grupo debe aparecer en la lista de grupos.

## <a name="edit-or-remove-a-group-in-the-eac"></a>Editar o eliminar un grupo en el EAC

1. En el Centro de Administración de Exchange, vaya a **Destinatarios** \> **Grupos**.

2. Realice uno de los pasos siguientes:

   - Para editar un grupo: en la lista de grupos, haga clic en el grupo que desea ver o modificar y, a continuación **** ![, haga clic](../media/ITPro-EAC-EditIcon.gif)en Editar icono de edición. Puede actualizar la configuración general, agregar o quitar propietarios de grupo y agregar o quitar miembros del grupo según sea necesario.

   - Para quitar un grupo: seleccione el grupo y haga **** ![clic en quitar](../media/ITPro-EAC-RemoveIcon.gif)icono quitar.

3. Cuando termine los cambios, haga clic en **Guardar**.

## <a name="create-edit-or-remove-a-group-using-remote-windows-powershell"></a>Crear, modificar o quitar un grupo utilizando Windows PowerShell remoto

En esta sección se proporciona información acerca de la creación de grupos y el cambio de sus propiedades en PowerShell de Exchange Online Protection. También se muestra cómo quitar un grupo existente.
  
### <a name="create-a-group-using-remote-windows-powershell"></a>Crear un grupo con Windows PowerShell remoto
  
En este ejemplo se utiliza el cmdlet [New-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/New-EOPDistributionGroup) para crear un grupo de distribución con el alias itadmin y los administradores de TI de nombre. También agrega los usuarios como miembros del grupo.
  
```Powershell
New-EOPDistributionGroup -Type Distribution -Name "IT Administrators" -Alias itadmin -Members @("Member1","Member2","Member3") -ManagedBy Member1
```

**Nota**: para crear un grupo de seguridad en lugar de un grupo de distribución, use `Security` el valor del parámetro *Type* .
  
Para comprobar que el grupo de administradores de TI se creó correctamente, ejecute el siguiente comando para mostrar información sobre el nuevo Grupo:
  
```Powershell
Get-Recipient "IT Administrators" | Format-List
```

Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [Get-recipient](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/Get-Recipient).

Para obtener una lista de los miembros del grupo, ejecute el siguiente comando:
  
```Powershell
Get-DistributionGroupMember "IT Administrators"
```

Para obtener información más detallada acerca de la sintaxis y los parámetros, consulte [Get-DistributionGroupMember](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-distributiongroupmember).

Para obtener una lista completa de todos los grupos, ejecute el siguiente comando:
  
```Powershell
Get-Recipient -RecipientType "MailUniversalDistributionGroup" | Format-Table | more
```

### <a name="change-the-properties-of-a-group-using-remote-windows-powershell"></a>Cambiar las propiedades de un grupo mediante Windows PowerShell remoto
  
Una de las ventajas de usar PowerShell en lugar de la EAC es la capacidad de cambiar las propiedades de varios grupos.
  
A continuación, se muestran algunos ejemplos de cómo usar PowerShell de Exchange Online Protection para cambiar las propiedades del grupo.
  
En este ejemplo se usan los cambios en la dirección SMTP principal (también denominada dirección de respuesta) del grupo empleados de Seattle en sea.employees@contoso.com.
  
```Powershell
Set-EOPDistributionGroup "Seattle Employees" -PrimarysmptAddress "sea.employees@contoso.com"
```

Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [set-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/set-eopdistributiongroup).

Para comprobar que cambió correctamente las propiedades del grupo, ejecute el siguiente comando para comprobar el nuevo valor:
  
```Powershell
Get-Recipient "Seattle Employees" | Format-List "PrimarySmtpAddress"
```

En este ejemplo se actualizan todos los miembros del grupo empleados de Seattle. Use una coma para separar todos los miembros.
  
```Powershell
Update-EOPDistributionGroupMember -Identity "Seattle Employees" -Members @("Member1","Member2","Member3","Member4","Member5")
```

Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [Update-EOPDistributionGroupMember](https://docs.microsoft.com/en-us/powershell/module/exchange/users-and-groups/update-eopdistributiongroupmember).

Para obtener la lista de todos los miembros del grupo empleados de Seattle, ejecute el siguiente comando: 
  
```Powershell
Get-DistributionGroupMember "Seattle Employees"
```

### <a name="remove-a-group-using-remote-windows-powershell"></a>Quitar un grupo mediante Windows PowerShell remoto
  
En este ejemplo se quita el grupo de distribución denominado administradores de ti.
  
```Powershell
Remove-EOPDistributionGroup -Identity "IT Administrators"
```

Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [Remove-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/remove-eopdistributiongroup).

Para comprobar que se ha quitado el grupo, ejecute el siguiente comando y confirme que se eliminó el grupo (en este caso, "administradores de ti").
  
```Powershell
Get-Recipient -RecipientType "MailUniversalDistributionGroup"
```
