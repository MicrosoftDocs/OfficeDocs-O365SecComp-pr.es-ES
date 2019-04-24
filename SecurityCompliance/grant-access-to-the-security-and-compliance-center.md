---
title: Dar a los usuarios acceso al centro de &amp; seguridad y cumplimiento de Office 365
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: ''
ms.audience: Admin
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
description: Los usuarios deben tener asignados permisos en el centro de &amp; seguridad y cumplimiento de Office 365 para que puedan administrar cualquiera de sus características de seguridad o cumplimiento.
ms.openlocfilehash: 08b3781ceb48b9a8d5933a075106d7bd3b9ab17d
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32253978"
---
# <a name="give-users-access-to-the-office-365-security-amp-compliance-center"></a>Dar a los usuarios acceso al centro de &amp; seguridad y cumplimiento de Office 365

Los usuarios deben tener asignados permisos en el centro de &amp; seguridad y cumplimiento de Office 365 para que puedan administrar cualquiera de sus características de seguridad o cumplimiento. Como administrador global de Office 365 o miembro del grupo de funciones OrganizationManagement en el centro &amp; de seguridad y cumplimiento, puede conceder estos permisos a los usuarios. Los usuarios solo podrán administrar las características de seguridad o cumplimiento a las que les proporcione acceso. 
  
Para obtener más información acerca de los distintos permisos que puede conceder a los &amp; usuarios en el centro de seguridad y cumplimiento, consulte [permisos &amp; en el centro de seguridad y cumplimiento de Office 365](permissions-in-the-security-and-compliance-center.md).
  
## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de comenzar?

- Debe ser un administrador global de Office 365 o un miembro del grupo de funciones OrganizationManagement en el centro de seguridad &amp; y cumplimiento, para completar los pasos de este artículo.
    
- Los grupos de roles para &amp; el centro de seguridad y cumplimiento podrían tener nombres similares a los grupos de roles en Exchange Online, pero no son los mismos. 
    
- Las pertenencias a grupos de roles no se comparten &amp; entre Exchange Online y el centro de seguridad y cumplimiento.
    
## <a name="use-the-office-365-admin-center-to-give-another-user-access-to-the-security-amp-compliance-center"></a>Usar el centro de administración de Office 365 para conceder a otro usuario &amp; acceso al centro de seguridad y cumplimiento

1. [Inicie sesión en Office 365 y vaya al centro de administración](https://go.microsoft.com/fwlink/p/?LinkId=525275).
    
2. En el centro de administración de Office 365, Abra **centros de administración** y, a continuación, haga clic en **cumplimiento de seguridad &amp; **. 
    
3. En el centro &amp; de seguridad y cumplimiento, vaya a **permisos**.
    
4. En la lista, elija el grupo de roles al que desea agregar el usuario y haga clic en **Editar** ![icono](media/O365_MDM_CreatePolicy_EditIcon.gif)editar.
    
5. En la página de propiedades del grupo de roles, en **miembros**, haga](media/ITPro-EAC-AddIcon.gif) clic en **Agregar**![icono de agregar y seleccione el nombre del usuario (o usuarios) que desea agregar. 
    
6. Cuando haya seleccionado todos los usuarios que desee agregar al grupo de roles, haga clic en **agregar\> ** y, a continuación, en **Aceptar**.
    
7. Haga clic en **Guardar** para guardar los cambios realizados en el grupo de roles. 
    
### <a name="how-do-you-know-this-worked"></a>¿Cómo saber si el proceso se ha completado correctamente?

1. En el centro &amp; de seguridad y cumplimiento, vaya a **permisos**.
    
2. En la lista, seleccione el grupo de roles para ver los miembros.
    
3. En la parte derecha, en los detalles del grupo de roles, puede ver los miembros del grupo de roles.
    
## <a name="use-powershell-to-give-another-user-access-to-the-security-amp-compliance-center"></a>Usar PowerShell para proporcionar a otro usuario acceso al centro &amp; de seguridad y cumplimiento

1. [Conéctese a Office 365 Security _AMP_ Compliance Center PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).
    
2. Use el comando **Add-RoleGroupMember** para agregar un usuario al rol Administración de la organización, tal y como se muestra en el ejemplo siguiente. 
    
  ```
  Add-RoleGroupMember -Identity "OrganizationManagement" -Member MatildaS
  
  ```

 **Parámetros**
  
- _-Identity_ es el grupo de roles al que se agregará un miembro. 
    
- _Member_ es el buzón, el grupo de seguridad universal (USG) o el equipo que se va a agregar al grupo de roles. Solo se puede especificar un miembro cada vez. 
    
Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [Add-RoleGroupMember](https://go.microsoft.com/fwlink/p/?LinkId=510859).
  
### <a name="how-do-you-know-this-worked"></a>¿Cómo saber si el proceso se ha completado correctamente?

Para comprobar que ha concedido a los usuarios acceso al &amp; centro de seguridad y cumplimiento, use el cmdlet **Get-RoleGroupMember** para ver los miembros del grupo de roles de administración de la organización, tal como se muestra en el ejemplo siguiente. 
  
```
Get-RoleGroupMember -Identity "OrganizationManagement"

```

Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [Get-RoleGroupMember](https://go.microsoft.com/fwlink/p/?LinkId=510860).
  

