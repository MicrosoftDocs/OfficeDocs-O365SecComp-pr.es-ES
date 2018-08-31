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
# <a name="manage-groups-in-eop"></a>Administrar grupos en EOP

 Puede usar Exchange Online Protection (EOP) para crear grupos habilitados para correo para una organización de Exchange. También puede usar EOP para definir o actualizar propiedades de grupo que especifiquen su pertenencia, las direcciones de correo electrónico y otros aspectos de los grupos. Puede crear grupos de distribución y grupos de seguridad, según sus necesidades. Se pueden crear estos grupos usando el Centro de administración de Exchange (EAC) o a través de Windows PowerShell remoto. 
  
## <a name="types-of-mail-enabled-groups"></a>Tipos de grupos habilitados para correo

Puede crear dos tipos de grupos para su organización de Exchange:
  
- [Crear un grupo en el EAC](manage-groups-in-eop.md) (también conocidos como grupos de distribución) son colecciones de usuarios de correo electrónico, como un equipo u otro grupo ad hoc, que necesitan recibir o enviar correo electrónico relativo a un área de interés común. Los grupos de distribución son exclusivamente para distribuir mensajes de correo electrónico. En EOP, un grupo de distribución hace referencia a cualquier grupo habilitado para correo, tenga o no un contexto de seguridad.
    
- [Editar o eliminar un grupo en el EAC](manage-groups-in-eop.md) (también conocidos como grupos de seguridad) son colecciones de usuarios de correo electrónico que necesitan permisos de acceso para roles de administrador. Por ejemplo, quizás quiera dar a un grupo de usuarios específico permisos de rol de administrador para que puedan configurar opciones de correo no deseado y antimalware.
    
    > [!NOTE]
    > De forma predeterminada, en todos los grupos de seguridad con correo habilitado es necesario que todos los remitentes estén autenticados. De este modo se evita que remitentes externos envíen mensajes a grupos de seguridad con correo habilitado. 
  
## <a name="before-you-begin"></a>Antes de empezar

- Deberá tener asignados permisos antes de poder llevar a cabo este procedimiento o procedimientos. Para ver qué permisos necesita, consulte el entrada "Grupos de distribución y grupos de seguridad " en el tema [Permisos de características en EOP](feature-permissions-in-eop.md). 
    
- Tenga en cuenta que, al crear y gestionar grupos mediante los cmdlets de PowerShell remoto, podría encontrarse con límites.
    
- Este cmdlet usa un método de procesamiento por lotes que provoca un retraso en la propagación de unos minutos antes de que los resultados del cmdlet sean visibles.
    
- Para aprender cómo usar Windows PowerShell para conectarse a Exchange Online Protection, consulte [Conectarse a Exchange Online Protection mediante PowerShell remoto](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell?view=exchange-ps).
    
- Para obtener información acerca de los métodos abreviados de teclado aplicables a los procedimientos de este tema, consulte **Keyboard shortcuts in Exchange 2013**.
    
> [!TIP]
> ¿Tiene algún problema? Solicite ayuda en los foros de Exchange. Visite los foros en [Exchange Server](https://go.microsoft.com/fwlink/p/?linkId=60612),[Exchange Online](https://go.microsoft.com/fwlink/p/?linkId=267542), o [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351). 
  
## <a name="create-a-group-in-the-eac"></a>Crear un grupo en el EAC

1. En el Centro de administración de Exchange (EAC), vaya a **Destinatarios** \> **Grupos**.
    
2. Haga clic en **Nuevo**![Agregar icono](../media/ITPro-EAC-AddIcon.gif) y después, haga clic en **Grupo de distribución** o **Grupo de seguridad**, según sus necesidades. Consulte [Tipos de grupos habilitados para correo](manage-groups-in-eop.md) para ver la distinción. 
    
3. En la página **Nuevo grupo de distribución** o **Nuevo grupo de seguridad**, complete los campos siguientes: 
    
  - **Nombre para mostrar** Escriba un nombre para mostrar que sea único en su organización y significativo para los usuarios de EOP. El nombre para mostrar es un campo obligatorio. 
    
  - **Alias** Escriba un alias de grupo de hasta 64 caracteres que sea único para su organización. Los usuarios de EOP escriben el alias en la línea Para: de los mensajes de correo electrónico, y el alias se resuelve en el nombre para mostrar del grupo. Si cambia el alias, la dirección SMTP principal del grupo también cambiará y contendrá el nuevo alias. El alias es obligatorio. 
    
  - **Descripción** Escriba una descripción del grupo para que los usuarios conozcan su propósito. 
    
  - **Propietarios** De forma predeterminada, la persona que crea un grupo es el propietario. Para crear un propietario, seleccione **Agregar**![Agregar icono](../media/ITPro-EAC-AddIcon.gif). Todos los grupos deben tener al menos un propietario.
    
    > [!NOTE]
    > Los propietarios no tienen que ser miembros del grupo. 
  
  - **Miembros** Use esta sección para agregar miembros e indicar si se necesita aprobación para los usuarios que se unan al grupo o lo dejen. Para agregar miembros al grupo, haga clic en **Agregar**![Agregar icono](../media/ITPro-EAC-AddIcon.gif).
    
4. Haga clic en **Aceptar** para volver a la página original. 
    
5. Cuando haya terminado, haga clic en **Guardar** para crear el grupo. El nuevo grupo debe aparecer en la lista de grupos. 
    
## <a name="edit-or-remove-a-group-in-the-eac"></a>Editar o eliminar un grupo en el EAC

1. En el Centro de Administración de Exchange, vaya a **Destinatarios** \> **Grupos**.
    
2. Siga uno de estos pasos:
    
  - Para editar un grupo: en la lista de grupos, haga clic en la distribución o grupo de seguridad que desea ver o cambiar y, a continuación, haga clic en **Editar** ![icono Editar](../media/ITPro-EAC-EditIcon.gif). Puede actualizar la configuración general, agregar o quitar los propietarios del grupo y agregar o quitar a miembros del grupo, según sea necesario.
    
  - Para quitar un grupo: Seleccione el grupo y haga clic en **Quitar**![Icono de quitar](../media/ITPro-EAC-RemoveIcon.gif).
    
3. Cuando termine los cambios, haga clic en **Guardar**.
    
## <a name="create-edit-or-remove-a-group-using-remote-windows-powershell"></a>Crear, modificar o quitar un grupo utilizando Windows PowerShell remoto

En esta sección se proporciona información acerca de cómo crear grupos y cambiar sus propiedades mediante el uso de Windows PowerShell remoto. También se muestra cómo quitar un grupo existente. 
  
 **Para crear un grupo con Windows PowerShell remoto**
  
En este ejemplo se utiliza el cmdlet [New-EOPDistributionGroup](http://technet.microsoft.com/library/4610dfe5-fca8-4ba8-be3c-535d1753e0f4.aspx) para crear un grupo de distribución con el alias itadmin y los administradores de TI de nombre. También agrega los usuarios como miembros del grupo. 
  
```
New-EOPDistributionGroup -Type "Distribution" -Name "IT Administrators" -Alias itadmin -Members @("Member1","Member2","Member3") -ManagedBy "Member1"

```

Para crear un grupo de seguridad en lugar de un grupo de distribución, especifique  `-Type "Security"` en su lugar. 
  
Para comprobar que se ha creado correctamente el grupo de los administradores de TI, ejecute el cmdlet [Get-Recipient](http://technet.microsoft.com/library/2ce6250f-0ad3-4b29-870c-e1d6e1e154bc.aspx) para mostrar la información acerca del nuevo grupo: 
  
```
Get-Recipient "IT Administrators" | Format-List

```

Para obtener una lista de miembros del grupo, ejecute el cmdlet [Get-DistributionGroupMember](http://technet.microsoft.com/library/15c71bc5-4246-44ac-8b34-8ccd585294b5.aspx) como sigue: 
  
```
Get-DistributionGroupMember "IT Administrators"

```

Para obtener una lista completa de todos los grupos, ejecute el cmdlet [Get-Recipient](http://technet.microsoft.com/library/2ce6250f-0ad3-4b29-870c-e1d6e1e154bc.aspx) como sigue: 
  
```
Get-Recipient -RecipientType "MailUniversalDistributionGroup" | FT | more

```

 **Para cambiar las propiedades de un grupo mediante Windows PowerShell remoto**
  
Use los cmdlets [Get-Recipient](http://technet.microsoft.com/library/2ce6250f-0ad3-4b29-870c-e1d6e1e154bc.aspx) y [Set-EOPDistributionGroup](http://technet.microsoft.com/library/689a66c5-a524-4870-88f3-091fd6eae3b7.aspx) para ver y cambiar las propiedades de los grupos. Una de las ventajas de usar PowerShell remoto en lugar de EAC es la capacidad de cambiar las propiedades de varios grupos. 
  
A continuación presentamos algunos ejemplos del uso de Windows PowerShell remoto para cambiar las propiedades de grupo.
  
En este ejemplo se usa el cmdlet [Set-EOPDistributionGroup](http://technet.microsoft.com/library/689a66c5-a524-4870-88f3-091fd6eae3b7.aspx) para cambiar la dirección SMTP primaria (también denominada dirección de respuesta) del grupo Empleados de Seattle a sea.employees@contoso.com. 
  
```
Set-EOPDistributionGroup "Seattle Employees" -PrimarysmptAddress "sea.employees@contoso.com"

```

Para comprobar que se han cambiado correctamente las propiedades de un grupo, use el cmdlet [Get-Recipient](http://technet.microsoft.com/library/2ce6250f-0ad3-4b29-870c-e1d6e1e154bc.aspx) para comprobar los cambios. Una ventaja de usar el PowerShell remoto es que puede consultar varias propiedades de varios grupos. En el ejemplo anterior en el que se cambió el grupo de la dirección SMTP primaria, ejecute el siguiente comando para comprar el nuevo valor. 
  
```
Get-Recipient "Seattle Employees" | FL "PrimarySmtpAddress"

```

En este ejemplo se usa el cmdlet [Update-EOPDistributionGroupMember](http://technet.microsoft.com/library/a6d4f790-1b94-42f8-af6f-fa79c504d8ec.aspx) para actualizar todos los miembros del grupo Empleados de Seattle. Use una coma para separar todos los miembros. 
  
```
Update-EOPDistributionGroupMember -Identity "Seattle Employees" -Members @("Member1","Member2","Member3","Member4","Member5")

```

Para obtener la lista de todos los miembros del grupo Empleados de Seattle, use el cmdlet [Get-DistributionGroupMember](http://technet.microsoft.com/library/15c71bc5-4246-44ac-8b34-8ccd585294b5.aspx) como sigue: 
  
```
Get-DistributionGroupMember "Seattle Employees"

```

 **Para quitar un grupo con Windows PowerShell remoto**
  
En este ejemplo se usa el cmdlet [Remove-EOPDistributionGroup](http://technet.microsoft.com/library/a17b1307-3187-40b0-a438-c7b35a34c002.aspx) para quitar un grupo de distribución denominado Administradores de TI. 
  
```
Remove-EOPDistributionGroup -Identity "IT Administrators" 

```

Para comprobar que se ha quitado el grupo, ejecute el cmdlet [Get-Recipient](http://technet.microsoft.com/library/2ce6250f-0ad3-4b29-870c-e1d6e1e154bc.aspx) como sigue y confirme que el grupo (en este caso "Administradores de TI) se ha eliminado. 
  
```
Get-Recipient -RecipientType "MailUniversalDistributionGroup"

```


