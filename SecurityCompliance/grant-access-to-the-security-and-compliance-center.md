---
title: Conceder a los usuarios acceso a la seguridad de Office 365 &amp; centro de cumplimiento
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/18/2017
ms.audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.PermissionsHelp
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 2cfce2c8-20c5-47f9-afc4-24b059c1bd76
description: Los usuarios necesitan tener asignados los permisos en la seguridad de Office 365 &amp; centro de cumplimiento de normas antes de que puedan administrar cualquiera de sus características de cumplimiento de normas o de seguridad.
ms.openlocfilehash: e0c8b655b1b3300e4ffa9aba1d94e65a9ef26121
ms.sourcegitcommit: 2e41cc24ad92005084f2ba432e724bdcc4e295ff
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/09/2018
ms.locfileid: "25450745"
---
# <a name="give-users-access-to-the-office-365-security-amp-compliance-center"></a>Conceder a los usuarios acceso a la seguridad de Office 365 &amp; centro de cumplimiento

Los usuarios necesitan tener asignados los permisos en la seguridad de Office 365 &amp; centro de cumplimiento de normas antes de que puedan administrar cualquiera de sus características de cumplimiento de normas o de seguridad. Como administrador global de Office 365 o miembro del grupo de roles en la seguridad OrganizationManagement &amp; centro de cumplimiento, puede dar estos permisos a los usuarios. Los usuarios sólo podrán administrar las características de cumplimiento de normas o de seguridad que conceda acceso a. 
  
Para obtener más información acerca de los diferentes permisos puede otorgar a los usuarios de la seguridad &amp; centro de cumplimiento, desprotección [permisos en la seguridad de Office 365 &amp; centro de cumplimiento](permissions-in-the-security-and-compliance-center.md).
  
## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de comenzar?

- Debe ser un administrador global de Office 365, o un miembro del grupo de roles en la seguridad OrganizationManagement &amp; centro de cumplimiento, para llevar a cabo los pasos descritos en este artículo.
    
- Grupos de roles para la seguridad &amp; centro de cumplimiento pueden tener nombres similares a los grupos de funciones en Exchange Online, pero no son los mismos. 
    
- Las pertenencias a grupo de funciones no se comparten entre Exchange Online y la seguridad &amp; centro de cumplimiento.
    
## <a name="use-the-office-365-admin-center-to-give-another-user-access-to-the-security-amp-compliance-center"></a>Use el centro de administración de Office 365 para ceder el otro usuario tenga acceso a la seguridad &amp; centro de cumplimiento

1. [Iniciar sesión en Office 365 y vaya al centro de administración](https://go.microsoft.com/fwlink/p/?LinkId=525275).
    
2. En el centro de administración de Office 365, abra **centros de administración** y, a continuación, haga clic en **seguridad &amp; cumplimiento**. 
    
3. En la seguridad &amp; centro de cumplimiento, vaya a **permisos**.
    
4. En la lista, elija el grupo de roles que se desea agregar al usuario y haga clic en **Editar** ![icono Editar](media/O365_MDM_CreatePolicy_EditIcon.gif).
    
5. En la página de propiedades del grupo de roles en **miembros**, haga clic en **Agregar**![icono Agregar](media/ITPro-EAC-AddIcon.gif) y seleccione el nombre del usuario (o usuarios) que desee agregar. 
    
6. Cuando haya seleccionado todos los usuarios que desea agregar al grupo de funciones, haga clic en **Agregar-\> ** y, a continuación, **Aceptar**.
    
7. Haga clic en **Guardar** para guardar los cambios realizados en el grupo de funciones. 
    
### <a name="how-do-you-know-this-worked"></a>¿Cómo saber si el proceso se ha completado correctamente?

1. En la seguridad &amp; centro de cumplimiento, vaya a **permisos**.
    
2. En la lista, seleccione el grupo de roles para ver a los miembros.
    
3. En la derecha, en los detalles del grupo de roles, puede ver a los miembros del grupo de roles.
    
## <a name="use-powershell-to-give-another-user-access-to-the-security-amp-compliance-center"></a>Uso de PowerShell para ceder el otro usuario tenga acceso a la seguridad &amp; centro de cumplimiento

1. [Conectar con la seguridad de Office 365 &amp; centro de cumplimiento de normas mediante PowerShell remoto](https://go.microsoft.com/fwlink/p/?LinkID=627084).
    
2. Use el comando **Add-RoleGroupMember** para agregar un usuario al rol Administración de la organización, tal y como se muestra en el ejemplo siguiente. 
    
  ```
  Add-RoleGroupMember -Identity "OrganizationManagement" -Member MatildaS
  
  ```

 **Parámetros**
  
-  _-Identity_ es el grupo de roles al que se agregará un miembro. 
    
- - _Miembro_ es el buzón de correo, el grupo de seguridad universal (USG) o el equipo para agregar al grupo de funciones. Puede especificar a un solo miembro a la vez. 
    
Para obtener información detallada sobre la sintaxis y los parámetros, vea [Add-RoleGroupMember](https://go.microsoft.com/fwlink/p/?LinkId=510859).
  
### <a name="how-do-you-know-this-worked"></a>¿Cómo saber si el proceso se ha completado correctamente?

Para comprobar que ha asignado a los usuarios a acceso a la seguridad &amp; centro de cumplimiento, use el cmdlet **Get-RoleGroupMember** para ver los miembros en el grupo de roles de administración de la organización, tal como se muestra en el siguiente ejemplo. 
  
```
Get-RoleGroupMember -Identity "OrganizationManagement"

```

Para obtener información detallada sobre la sintaxis y los parámetros, vea [Get-RoleGroupMember](https://go.microsoft.com/fwlink/p/?LinkId=510860).
  

