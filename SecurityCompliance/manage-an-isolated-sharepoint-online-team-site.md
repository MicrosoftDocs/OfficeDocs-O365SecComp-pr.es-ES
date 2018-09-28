---
title: Administrar un sitio de grupo de SharePoint Online aislado
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/15/2017
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
ms.custom: Ent_Solutions
ms.assetid: 79a61003-4905-4ba8-9e8a-16def7add37c
description: 'Resumen: Administre su sitio de grupo de SharePoint Online aislado con estos procedimientos.'
ms.openlocfilehash: 22b4cbbdd926635286d23570e1f61b64529d0e76
ms.sourcegitcommit: e0f016aca7befc8806233a492ee916cbe646094f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2018
ms.locfileid: "25345942"
---
# <a name="manage-an-isolated-sharepoint-online-team-site"></a>Administrar un sitio de grupo de SharePoint Online aislado

 **Resumen:** Administrar el sitio de grupo de SharePoint Online aislado con estos procedimientos.
  
En este artículo se describe las operaciones habituales de administración para un sitio de grupo de SharePoint Online aislado.
  
## <a name="add-a-new-user"></a>Agregar un nuevo usuario

Cuando alguien nuevo une al sitio, debe decidir su nivel de participación en el sitio:
  
- Administración: Agregar la cuenta de usuario nueva en el sitio de grupo de acceso a los administradores
    
- Colaboración activo: agregar la cuenta de usuario en el sitio de grupo de acceso a los miembros
    
- Visualización: Agregar la cuenta de usuario en el sitio de los visores de tener acceso a grupo
    
Si va a administrar cuentas de usuario y grupos a través de Windows Server Active Directory (AD), agregue los usuarios adecuados a los grupos de acceso apropiado mediante sus normal Windows Server AD usuario y grupo de procedimientos de administración y espere a que la sincronización con su Suscripción de Office 365.
  
Si va a administrar cuentas de usuario y grupos a través de Office 365, puede usar el centro de administración de Office o Microsoft PowerShell:
  
- Para el centro de administración de Office, inicie sesión con una cuenta de usuario que se ha asignado el rol de administrador de la cuenta de usuario o administrador de la compañía y usar grupos para agregar los usuarios adecuados a los grupos de acceso apropiado.
    
- Para [Conectar con el módulo Azure Active Directory PowerShell V2](https://go.microsoft.com/fwlink/?linkid=842218)de primera de PowerShell. Para agregar una cuenta de usuario a un grupo de acceso con su nombre principal de usuario (UPN), use el siguiente bloque de comandos de PowerShell:
    
```
$userUPN="<UPN of the user account>"
$grpName="<display name of the group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

> [!TIP]
> Para un archivo de texto que contiene todos los comandos de PowerShell y un Excel hoja de trabajo de configuración que genera comandos de PowerShell en función de su grupo y usuario los nombres de cuenta, descargue el [Aislado SharePoint Online equipo sitio Kit de implementación](https://gallery.technet.microsoft.com/Isolated-SharePoint-Online-0b364907). 

Para agregar una cuenta de usuario a un grupo de acceso con su nombre para mostrar, use el siguiente bloque de comandos de PowerShell:

```
$userDisplayName="<display name of the user account>"
$grpName="<display name of the group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $userDisplayName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

## <a name="add-a-new-group"></a>Agregar un nuevo grupo

Para obtener acceso a un grupo completo, debe decidir el nivel de la participación de todos los miembros del grupo en el sitio:
  
- Administración: Agregar el grupo en el sitio de grupo de acceso a los administradores
    
- Colaboración activo: agregar el grupo en el sitio de grupo de acceso a los miembros
    
- Visualización: Agregar el grupo en el sitio de los visores de tener acceso a grupo
    
Si va a administrar cuentas de usuario y grupos a través de Windows Server AD, agregue los grupos correspondientes a los grupos apropiados con su usuario normal de Windows Server AD y procedimientos de administración de grupo y espere para la sincronización con su suscripción de Office 365.
  
Si va a administrar cuentas de usuario y grupos a través de Office 365, puede usar el centro de administración de Office o PowerShell:
  
- Para el centro de administración de Office, inicie sesión con una cuenta de usuario que se ha asignado el rol de administrador de la cuenta de usuario o administrador de la compañía y usar grupos para agregar los grupos correspondientes a los grupos de acceso apropiado.
    
- Para [Conectar con el módulo Azure Active Directory PowerShell V2](https://go.microsoft.com/fwlink/?linkid=842218)de primera de PowerShell. A continuación, use los siguientes comandos de PowerShell:
 
```
$newGroupName="<display name of the new group to add>"
$siteGrpName="<display name of the access group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $newGroupName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $siteGrpName }).ObjectID
```

## <a name="remove-a-user"></a>Quitar un usuario

Cuando una persona acceso debe quitarse del sitio, quita desde el grupo de acceso para la que actualmente son miembros en función de su participación en el sitio:
  
- Administración: Quitar la cuenta de usuario del grupo de acceso de los administradores de sitio
    
- Colaboración activo: quitar la cuenta de usuario del grupo de acceso de sitio (miembros de)
    
- Visualización: Quitar la cuenta de usuario del grupo de acceso de los visores de sitio
    
Si va a administrar cuentas de usuario y grupos a través de Windows Server AD, quitar los usuarios adecuados de los grupos de acceso apropiado con su usuario normal de Windows Server AD y procedimientos de administración de grupo y espere a que la sincronización con Office 365 suscripción a.
  
Si va a administrar cuentas de usuario y grupos a través de Office 365, puede usar el centro de administración de Office o PowerShell:
  
- Para el centro de administración de Office, inicie sesión con una cuenta de usuario que se ha asignado el rol de administrador de la cuenta de usuario o administrador de la compañía y usar grupos para quitar los usuarios adecuados de los grupos de acceso apropiado.
    
- Para [Conectar con el módulo Azure Active Directory PowerShell V2](https://go.microsoft.com/fwlink/?linkid=842218)de primera de PowerShell. Para quitar una cuenta de usuario de un grupo de acceso con su UPN, use el siguiente bloque de comandos de PowerShell:
    
```
$userUPN="<UPN of the user account>"
$grpName="<display name of the access group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

Para quitar una cuenta de usuario de un grupo de acceso con su nombre para mostrar, use el siguiente bloque de comandos de PowerShell:
    
```
$userDisplayName="<display name of the user account>"
$grpName="<display name of the access group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADUser | Where { $_.DisplayName -eq $userDisplayName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

## <a name="remove-a-group"></a>Quitar un grupo

Para quitar el acceso de un grupo entero, quitar el grupo desde el grupo de acceso para la que actualmente son miembros en función de su participación en el sitio:
  
- Administración: Quitar el grupo desde el grupo de acceso de los administradores de sitio
    
- Colaboración activo: quitar el grupo desde el grupo de acceso de los miembros de sitio
    
- Visualización: Quitar el grupo desde el grupo de acceso de los visores de sitio
    
Si va a administrar cuentas de usuario y grupos a través de Windows Server Active Directory, quitar los grupos apropiados de los grupos de acceso apropiado mediante sus normal Windows Server AD usuario y grupo de procedimientos de administración y espere a que la sincronización con su Suscripción de Office 365.
  
Si va a administrar cuentas de usuario y grupos a través de Office 365, puede usar el centro de administración de Office o PowerShell:
  
- Para el centro de administración de Office, inicie sesión con una cuenta de usuario que se ha asignado el rol de administrador de la cuenta de usuario o administrador de la compañía y usar grupos para quitar los grupos apropiados de los grupos de acceso apropiado.
    
- Para [Conectar con el módulo Azure Active Directory PowerShell V2](https://go.microsoft.com/fwlink/?linkid=842218)de primera de PowerShell.    
Para quitar un grupo de un grupo de acceso mediante sus nombres para mostrar, use el siguiente bloque de comandos de PowerShell:
    
```
$groupMemberName="<display name of the group to remove>"
$grpName="<display name of the access group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

## <a name="create-a-documents-subfolder-with-custom-permissions"></a>Cree una subcarpeta de documentos con permisos personalizados

En algunos casos, un subconjunto de las personas que trabajan en el sitio aislado necesita un lugar para colaborar más privado. Para sitios de SharePoint Online, puede crear una subcarpeta en la carpeta de documentos del sitio y asignar permisos personalizados. Los que no tienen permisos no verán la subcarpeta.
  
Para crear una subcarpeta de documentos con permisos personalizados, haga lo siguiente:
  
1. Inicie sesión en Office 365 con una cuenta que sea miembro del grupo Administradores de acceso para el sitio. Para obtener ayuda, consulte [Where iniciar sesión en Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4).
    
2. Vaya al sitio del equipo aislado y haga clic en **documentos**.
    
3. Vaya a la carpeta en la carpeta de documentos que contendrá la subcarpeta con permisos personalizados, cree la carpeta y, a continuación, ábralo.
    
4. Haga clic en **Compartir**.
    
5. Haga clic en **Shared con > avanzada**.
    
6. Haga clic en **dejar de heredar permisos**y, a continuación, haga clic en **Aceptar**.
    
7. Haga clic en **Compartir**.
    
8. Haga clic en **Shared con > avanzada**.
    
9. Haga clic en **conceder permisos > Shared con > avanzada**.
    
10. En la página permisos, haga clic en ** \<nombre del sitio > (miembros de) en la lista**.
    
11. En la ** \<nombre del sitio > miembros** de página, seleccione la marca de verificación situada junto al grupo de acceso de los miembros de sitio, haga clic en **acciones**, haga clic en **quitar usuarios del grupo**y, a continuación, haga clic en **Aceptar**.
    
12. Para agregar miembros específicos a esta subcarpeta, haga clic en **Nuevo > Agregar usuarios**.
    
13. En el cuadro de diálogo **Compartir** , escriba los nombres de las cuentas de usuario que pueden colaborar en los archivos en la subcarpeta y, a continuación, haga clic en **Compartir**.
    
14. Actualice la página web para ver los resultados de la nueva.
    
15. En los **grupos** en el panel de navegación izquierdo, haga clic en el ** \<nombre del sitio > visitantes** de grupo y siga los pasos del 11 al 14 para especificar el conjunto de cuentas de usuario que puede ver los archivos en la subcarpeta (según sea necesario).
    
16. En los **grupos** en el panel de navegación izquierdo, haga clic en el ** \<nombre del sitio > propietarios** de grupo y siga los pasos del 11 al 14 para especificar el conjunto de cuentas de usuario que puede administrar los permisos en la subcarpeta (según sea necesario).
    
17. Cierre la ficha **personas y grupos** en el explorador.
    
## <a name="see-also"></a>Consulte también

[Sitios de grupo de SharePoint Online aislados](isolated-sharepoint-online-team-sites.md)
  
[Diseñar un sitio de grupo de SharePoint Online aislado](design-an-isolated-sharepoint-online-team-site.md)

[Implementar un sitio de grupo de SharePoint Online aislado](deploy-an-isolated-sharepoint-online-team-site.md)



