---
title: Proporcionar a los usuarios acceso al Centro de seguridad y cumplimiento de Office 365
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.PermissionsHelp
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 2cfce2c8-20c5-47f9-afc4-24b059c1bd76
description: Los usuarios deben tener asignados permisos en el centro de seguridad & cumplimiento de Office 365 para poder administrar cualquiera de sus características de seguridad o cumplimiento.
ms.openlocfilehash: f11114ede37269f9b89c4d2b34c69f2d6db8a3f7
ms.sourcegitcommit: 044003455eb36071806c9f008ac631d54c64dde6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/24/2019
ms.locfileid: "35199747"
---
# <a name="give-users-access-to-the-office-365-security--compliance-center"></a>Proporcionar a los usuarios acceso al Centro de seguridad y cumplimiento de Office 365

Los usuarios deben tener asignados permisos en el centro de seguridad & cumplimiento de Office 365 para poder administrar cualquiera de sus características de seguridad o cumplimiento. Como administrador global de Office 365 o miembro del grupo de funciones OrganizationManagement en el centro de seguridad & cumplimiento, puede conceder estos permisos a los usuarios. Los usuarios solo podrán administrar las características de seguridad o cumplimiento a las que les proporcione acceso. 
  
Para obtener más información acerca de los distintos permisos que puede conceder a los usuarios en el centro de seguridad & cumplimiento, consulte Permissions [in the Office 365 security & Compliance Center](permissions-in-the-security-and-compliance-center.md).
  
## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de comenzar?

- Debe ser administrador global de Office 365 o miembro del grupo de funciones OrganizationManagement en el centro de seguridad & cumplimiento para completar los pasos descritos en este artículo.

- Los grupos de roles para el centro de seguridad & cumplimiento pueden tener nombres similares a los grupos de roles en Exchange Online, pero no son los mismos.

- Las pertenencias a grupos de roles no se comparten entre Exchange Online y el centro de seguridad & cumplimiento.

- Los permisos de acceso delegado (DAP) asociados con administrar en nombre de (AOBO) no pueden obtener acceso al centro de seguridad & cumplimiento.

## <a name="use-the-office-365-admin-center-to-give-another-user-access-to-the-security--compliance-center"></a>Usar el centro de administración de Office 365 para conceder a otro usuario acceso al centro de seguridad & cumplimiento

1. [Inicie sesión en Office 365 y vaya al centro de administración](https://go.microsoft.com/fwlink/p/?LinkId=525275).

2. En el centro de administración de Office 365, Abra **centros de administración** y, a continuación, haga clic en **seguridad & cumplimiento**.

3. En el centro de seguridad & cumplimiento, vaya a **permisos**.

4. En la lista, elija el grupo de roles al que desea agregar el usuario y haga clic en **Editar** ![icono](media/O365-MDM-CreatePolicy-EditIcon.gif)editar.

5. En la página de propiedades del grupo de roles, en **miembros**, haga](media/ITPro-EAC-AddIcon.gif) clic en **Agregar**![icono de agregar y seleccione el nombre del usuario (o usuarios) que desea agregar.

6. Cuando haya seleccionado todos los usuarios que desee agregar al grupo de roles, haga clic en **agregar\> ** y, a continuación, en **Aceptar**.

7. Haga clic en **Guardar** para guardar los cambios realizados en el grupo de roles.

### <a name="how-do-you-know-this-worked"></a>¿Cómo saber si el proceso se ha completado correctamente?

1. En el centro de seguridad & cumplimiento, vaya a **permisos**.

2. En la lista, seleccione el grupo de roles para ver los miembros.

3. En la parte derecha, en los detalles del grupo de roles, puede ver los miembros del grupo de roles.

## <a name="use-powershell-to-give-another-user-access-to-the-security--compliance-center"></a>Usar PowerShell para proporcionar a otro usuario acceso al centro de seguridad & cumplimiento

1. [Conéctese a Office 365 Security & el centro de cumplimiento de PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).

2. Use el comando **Add-RoleGroupMember** para agregar un usuario al rol Administración de la organización, tal y como se muestra en el ejemplo siguiente.

   ```
   Add-RoleGroupMember -Identity "OrganizationManagement" -Member MatildaS
   ```

   **Parámetros**:
  
   - _Identity_ es el grupo de roles al que se agrega un miembro.

   - _Member_ es el buzón, el grupo de seguridad universal (USG) o el equipo que se va a agregar al grupo de roles. Solo se puede especificar un miembro cada vez.

Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [Add-RoleGroupMember](https://go.microsoft.com/fwlink/p/?LinkId=510859).
  
### <a name="how-do-you-know-this-worked"></a>¿Cómo saber si el proceso se ha completado correctamente?

Para comprobar que ha concedido a los usuarios acceso al centro de seguridad & cumplimiento, use el cmdlet **Get-RoleGroupMember** para ver los miembros del grupo de funciones de administración de la organización, tal como se muestra en el ejemplo siguiente.
  
```
Get-RoleGroupMember -Identity "OrganizationManagement"
```

Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [Get-RoleGroupMember](https://go.microsoft.com/fwlink/p/?LinkId=510860).
