---
title: Administrar un sitio de grupo de SharePoint Online aislado
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/15/2017
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: Ent_O365
ms.custom: Ent_Solutions
ms.assetid: 79a61003-4905-4ba8-9e8a-16def7add37c
description: 'Resumen: administre el sitio de grupo de SharePoint Online aislado con estos procedimientos.'
ms.openlocfilehash: 1670c806c799cdbd9ffa6d3c45568a3342b88815
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/17/2019
ms.locfileid: "34155822"
---
# <a name="manage-an-isolated-sharepoint-online-team-site"></a>Administrar un sitio de grupo de SharePoint Online aislado

 **Resumen:** Administre el sitio de grupo de SharePoint Online aislado con estos procedimientos.
  
En este artículo se describen las operaciones de administración comunes para un sitio de grupo de SharePoint Online aislado.
  
## <a name="add-a-new-user"></a>Agregar un nuevo usuario

Cuando alguien nuevo se une al sitio, debe decidir su nivel de participación en el sitio:
  
- Administración: agregar la nueva cuenta de usuario al grupo de acceso de administradores de sitios
    
- Colaboración activa: agregar la cuenta de usuario al grupo de acceso de miembros del sitio
    
- Ver: agregar la cuenta de usuario al grupo de acceso de visores del sitio
    
Si administra cuentas de usuario y grupos a través de Windows Server Active Directory (AD), agregue los usuarios adecuados a los grupos de acceso adecuados mediante los procedimientos habituales de administración de grupos y usuarios de Windows Server AD y espere la sincronización con el Suscripción de Office 365.
  
Si administra cuentas de usuario y grupos a través de Office 365, puede usar el centro de administración de Office o PowerShell de Microsoft:
  
- En el centro de administración de Office, inicie sesión con una cuenta de usuario que tenga asignado el rol de administrador de la cuenta de usuario o de administrador de la compañía y use grupos para agregar los usuarios adecuados a los grupos de acceso adecuados.
    
- Para PowerShell, primero [Conéctese con el módulo Azure Active Directory PowerShell para Graph](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module). Para agregar una cuenta de usuario a un grupo de acceso con su nombre principal de usuario (UPN), use el siguiente bloque de comandos de PowerShell:
    
```
$userUPN="<UPN of the user account>"
$grpName="<display name of the group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

> [!TIP]
> Para obtener un archivo de texto que contenga todos los comandos de PowerShell y una hoja de cálculo de configuración de Excel que genere comandos de PowerShell en función de los nombres de cuenta de grupo y de usuario, descargue el kit de implementación de sitios de grupo de [SharePoint Online aislado](https://gallery.technet.microsoft.com/Isolated-SharePoint-Online-0b364907). 

Para agregar una cuenta de usuario a un grupo de acceso con su nombre para mostrar, use el siguiente bloque de comandos de PowerShell:

```
$userDisplayName="<display name of the user account>"
$grpName="<display name of the group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $userDisplayName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

## <a name="add-a-new-group"></a>Agregar un nuevo grupo

Para agregar acceso a todo un grupo, debe decidir el nivel de participación de todos los miembros del grupo en el sitio:
  
- Administración: agregar el grupo al grupo de acceso de administradores de sitios
    
- Colaboración activa: agregar el grupo al grupo de acceso de los miembros del sitio
    
- Ver: agregar el grupo al grupo de acceso de visores del sitio
    
Si administra cuentas de usuario y grupos a través de Windows Server AD, agregue los grupos adecuados a los grupos adecuados mediante los procedimientos habituales de administración de usuarios y grupos de Windows Server AD y espere la sincronización con la suscripción a Office 365.
  
Si administra cuentas de usuario y grupos a través de Office 365, puede usar el centro de administración de Office o PowerShell:
  
- En el centro de administración de Office, inicie sesión con una cuenta de usuario que tenga asignado el rol de administrador de la cuenta de usuario o de administrador de la compañía y use grupos para agregar los grupos adecuados a los grupos de acceso adecuados.
    
- Para PowerShell, primero [Conéctese con el módulo Azure Active Directory PowerShell para Graph](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).
 A continuación, use los siguientes comandos de PowerShell:
 
```
$newGroupName="<display name of the new group to add>"
$siteGrpName="<display name of the access group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $newGroupName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $siteGrpName }).ObjectID
```

## <a name="remove-a-user"></a>Quitar un usuario

Cuando es necesario quitar el acceso de un usuario del sitio, se quitan del grupo de acceso para el que actualmente son miembros según su participación en el sitio:
  
- Administración: quitar la cuenta de usuario del grupo de acceso de administradores de sitios
    
- Colaboración activa: quitar la cuenta de usuario del grupo de acceso de los miembros del sitio
    
- Ver: quitar la cuenta de usuario del grupo de acceso de visores del sitio
    
Si administra cuentas de usuario y grupos a través de Windows Server AD, quite los usuarios correspondientes de los grupos de acceso adecuados mediante los procedimientos habituales de administración de grupos y usuarios de Windows Server AD y espere la sincronización con su Office 365 scription.
  
Si administra cuentas de usuario y grupos a través de Office 365, puede usar el centro de administración de Office o PowerShell:
  
- En el centro de administración de Office, inicie sesión con una cuenta de usuario que tenga asignado el rol de administrador de la cuenta de usuario o de administrador de la compañía y use grupos para quitar los usuarios correspondientes de los grupos de acceso adecuados.
    
- Para PowerShell, primero [Conéctese con el módulo Azure Active Directory PowerShell para Graph](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).
Para quitar una cuenta de usuario de un grupo de acceso con su UPN, use el siguiente bloque de comandos de PowerShell:
    
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

Para quitar el acceso de un grupo completo, se quita el grupo del grupo de acceso para el que se integra en ese momento en función de su participación en el sitio:
  
- Administración: quitar el grupo del grupo de acceso de administradores de sitios
    
- Colaboración activa: quitar el grupo del grupo de acceso de los miembros del sitio
    
- Ver: quitar el grupo del grupo de acceso de visores del sitio
    
Si administra cuentas de usuario y grupos a través de Windows Server Active Directory, quite los grupos adecuados de los grupos de acceso adecuados mediante los procedimientos habituales de administración de grupos y usuarios de Windows Server AD y espere la sincronización con el Suscripción de Office 365.
  
Si administra cuentas de usuario y grupos a través de Office 365, puede usar el centro de administración de Office o PowerShell:
  
- En el centro de administración de Office, inicie sesión con una cuenta de usuario que tenga asignado el rol de administrador de la cuenta de usuario o de administrador de la compañía y use grupos para quitar los grupos adecuados de los grupos de acceso adecuados.
    
- Para PowerShell, primero [Conéctese con el módulo Azure Active Directory PowerShell para Graph](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).    
Para quitar un grupo de un grupo de acceso mediante sus nombres para mostrar, use el siguiente bloque de comandos de PowerShell:
    
```
$groupMemberName="<display name of the group to remove>"
$grpName="<display name of the access group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

## <a name="create-a-documents-subfolder-with-custom-permissions"></a>Crear una subcarpeta de documentos con permisos personalizados

En algunos casos, un subconjunto de las personas que trabajan en el sitio aislado necesita un lugar más privado para colaborar. Para los sitios de SharePoint Online, puede crear una subcarpeta en la carpeta documentos del sitio y asignar permisos personalizados. Los usuarios sin permisos no verán la subcarpeta.
  
Para crear una subcarpeta de documentos con permisos personalizados, haga lo siguiente:
  
1. Inicie sesión en Office 365 con una cuenta que sea miembro del grupo de administradores de acceso para el sitio. Para obtener ayuda, vea [Where to sign in to Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4) (Dónde iniciar sesión en Office 365).
    
2. Vaya al sitio de grupo aislado y haga clic en **documentos**.
    
3. Vaya a la carpeta de la carpeta documentos que contendrá la subcarpeta con permisos personalizados, cree la carpeta y, a continuación, ábrala.
    
4. Haga clic en **Compartir**.
    
5. Haga clic en **compartido con _GT_ avanzadas**.
    
6. Haga clic en **dejar de heredar permisos**y, a continuación, haga clic en **Aceptar**.
    
7. Haga clic en **Compartir**.
    
8. Haga clic en **compartido con _GT_ avanzadas**.
    
9. Haga clic en **conceder permisos _GT_ Shared with _GT_ Advanced**.
    
10. En la página permisos, haga clic ** \<en miembros del name> del sitio de la lista**.
    
11. En la ** \<página miembros del sitio name>** , seleccione la marca de verificación junto al grupo acceso de miembros del sitio, haga clic en **acciones**, haga clic en **quitar usuarios del grupo**y, a continuación, haga clic en **Aceptar**.
    
12. Para agregar miembros específicos a esta subcarpeta, haga clic en **nuevo _GT_ agregar usuarios**.
    
13. En el cuadro de diálogo **compartir** , escriba los nombres de las cuentas de usuario que pueden colaborar en los archivos de la subcarpeta y, a continuación, haga clic en **compartir**.
    
14. Actualice la página web para ver los nuevos resultados.
    
15. En **grupos** en el panel de navegación izquierdo, haga clic en el ** \<grupo name> visitantes** y use los pasos 11-14 para especificar el conjunto de cuentas de usuario que pueden ver los archivos de la subcarpeta (según sea necesario).
    
16. En **grupos** en el panel de navegación izquierdo, ** \<** haga clic en el grupo propietarios de name> de sitios y use los pasos 11-14 para especificar el conjunto de cuentas de usuario que pueden administrar los permisos de la subcarpeta (según sea necesario).
    
17. Cierre la pestaña **personas y grupos** del explorador.
    
## <a name="see-also"></a>Vea también

[Sitios de grupo de SharePoint Online aislados](isolated-sharepoint-online-team-sites.md)
  
[Diseñar un sitio de grupo de SharePoint Online aislado](design-an-isolated-sharepoint-online-team-site.md)

[Implementar un sitio de grupo de SharePoint Online aislado](deploy-an-isolated-sharepoint-online-team-site.md)



