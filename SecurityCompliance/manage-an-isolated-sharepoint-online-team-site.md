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
# <a name="manage-an-isolated-sharepoint-online-team-site"></a><span data-ttu-id="746db-103">Administrar un sitio de grupo de SharePoint Online aislado</span><span class="sxs-lookup"><span data-stu-id="746db-103">Manage an isolated SharePoint Online team site</span></span>

 <span data-ttu-id="746db-104">**Resumen:** Administrar el sitio de grupo de SharePoint Online aislado con estos procedimientos.</span><span class="sxs-lookup"><span data-stu-id="746db-104">**Summary:** Manage your isolated SharePoint Online team site with these procedures.</span></span>
  
<span data-ttu-id="746db-105">En este artículo se describe las operaciones habituales de administración para un sitio de grupo de SharePoint Online aislado.</span><span class="sxs-lookup"><span data-stu-id="746db-105">This article describes common management operations for an isolated SharePoint Online team site.</span></span>
  
## <a name="add-a-new-user"></a><span data-ttu-id="746db-106">Agregar un nuevo usuario</span><span class="sxs-lookup"><span data-stu-id="746db-106">Add a new user</span></span>

<span data-ttu-id="746db-107">Cuando alguien nuevo une al sitio, debe decidir su nivel de participación en el sitio:</span><span class="sxs-lookup"><span data-stu-id="746db-107">When someone new joins the site, you must decide their level of participation in the site:</span></span>
  
- <span data-ttu-id="746db-108">Administración: Agregar la cuenta de usuario nueva en el sitio de grupo de acceso a los administradores</span><span class="sxs-lookup"><span data-stu-id="746db-108">Administration: Add the new user account to the site admins access group</span></span>
    
- <span data-ttu-id="746db-109">Colaboración activo: agregar la cuenta de usuario en el sitio de grupo de acceso a los miembros</span><span class="sxs-lookup"><span data-stu-id="746db-109">Active collaboration: Add the user account to the site members access group</span></span>
    
- <span data-ttu-id="746db-110">Visualización: Agregar la cuenta de usuario en el sitio de los visores de tener acceso a grupo</span><span class="sxs-lookup"><span data-stu-id="746db-110">Viewing: Add the user account to the site viewers access group</span></span>
    
<span data-ttu-id="746db-111">Si va a administrar cuentas de usuario y grupos a través de Windows Server Active Directory (AD), agregue los usuarios adecuados a los grupos de acceso apropiado mediante sus normal Windows Server AD usuario y grupo de procedimientos de administración y espere a que la sincronización con su Suscripción de Office 365.</span><span class="sxs-lookup"><span data-stu-id="746db-111">If you are managing user accounts and groups through Windows Server Active Directory (AD), add the appropriate users to the appropriate access groups using your normal Windows Server AD user and group management procedures and wait for synchronization with your Office 365 subscription.</span></span>
  
<span data-ttu-id="746db-112">Si va a administrar cuentas de usuario y grupos a través de Office 365, puede usar el centro de administración de Office o Microsoft PowerShell:</span><span class="sxs-lookup"><span data-stu-id="746db-112">If you are managing user accounts and groups through Office 365, you can use the Office Admin center or Microsoft PowerShell:</span></span>
  
- <span data-ttu-id="746db-113">Para el centro de administración de Office, inicie sesión con una cuenta de usuario que se ha asignado el rol de administrador de la cuenta de usuario o administrador de la compañía y usar grupos para agregar los usuarios adecuados a los grupos de acceso apropiado.</span><span class="sxs-lookup"><span data-stu-id="746db-113">For the Office Admin center, sign in with a user account that has been assigned the User Account Administrator or Company Administrator role and use Groups to add the appropriate users to the appropriate access groups.</span></span>
    
- <span data-ttu-id="746db-p101">Para [Conectar con el módulo Azure Active Directory PowerShell V2](https://go.microsoft.com/fwlink/?linkid=842218)de primera de PowerShell. Para agregar una cuenta de usuario a un grupo de acceso con su nombre principal de usuario (UPN), use el siguiente bloque de comandos de PowerShell:</span><span class="sxs-lookup"><span data-stu-id="746db-p101">For PowerShell, first [Connect with the Azure Active Directory V2 PowerShell module](https://go.microsoft.com/fwlink/?linkid=842218). To add a user account to an access group with its user principal name (UPN), use the following PowerShell command block:</span></span>
    
```
$userUPN="<UPN of the user account>"
$grpName="<display name of the group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

> [!TIP]
> <span data-ttu-id="746db-116">Para un archivo de texto que contiene todos los comandos de PowerShell y un Excel hoja de trabajo de configuración que genera comandos de PowerShell en función de su grupo y usuario los nombres de cuenta, descargue el [Aislado SharePoint Online equipo sitio Kit de implementación](https://gallery.technet.microsoft.com/Isolated-SharePoint-Online-0b364907).</span><span class="sxs-lookup"><span data-stu-id="746db-116">For a text file that contains all the PowerShell commands and an Excel configuration worksheet that generates PowerShell commands based on your group and user account names, download the [Isolated SharePoint Online Team Site Deployment Kit](https://gallery.technet.microsoft.com/Isolated-SharePoint-Online-0b364907).</span></span> 

<span data-ttu-id="746db-117">Para agregar una cuenta de usuario a un grupo de acceso con su nombre para mostrar, use el siguiente bloque de comandos de PowerShell:</span><span class="sxs-lookup"><span data-stu-id="746db-117">To add a user account to an access group with its display name, use the following PowerShell command block:</span></span>

```
$userDisplayName="<display name of the user account>"
$grpName="<display name of the group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $userDisplayName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

## <a name="add-a-new-group"></a><span data-ttu-id="746db-118">Agregar un nuevo grupo</span><span class="sxs-lookup"><span data-stu-id="746db-118">Add a new group</span></span>

<span data-ttu-id="746db-119">Para obtener acceso a un grupo completo, debe decidir el nivel de la participación de todos los miembros del grupo en el sitio:</span><span class="sxs-lookup"><span data-stu-id="746db-119">To add access to an entire group, you must decide the level of participation of all the members of the group in the site:</span></span>
  
- <span data-ttu-id="746db-120">Administración: Agregar el grupo en el sitio de grupo de acceso a los administradores</span><span class="sxs-lookup"><span data-stu-id="746db-120">Administration: Add the group to the site admins access group</span></span>
    
- <span data-ttu-id="746db-121">Colaboración activo: agregar el grupo en el sitio de grupo de acceso a los miembros</span><span class="sxs-lookup"><span data-stu-id="746db-121">Active collaboration: Add the group to the site members access group</span></span>
    
- <span data-ttu-id="746db-122">Visualización: Agregar el grupo en el sitio de los visores de tener acceso a grupo</span><span class="sxs-lookup"><span data-stu-id="746db-122">Viewing: Add the group to the site viewers access group</span></span>
    
<span data-ttu-id="746db-123">Si va a administrar cuentas de usuario y grupos a través de Windows Server AD, agregue los grupos correspondientes a los grupos apropiados con su usuario normal de Windows Server AD y procedimientos de administración de grupo y espere para la sincronización con su suscripción de Office 365.</span><span class="sxs-lookup"><span data-stu-id="746db-123">If you are managing user accounts and groups through Windows Server AD, add the appropriate groups to the appropriate groups using your normal Windows Server AD user and group management procedures and wait for synchronization with your Office 365 subscription.</span></span>
  
<span data-ttu-id="746db-124">Si va a administrar cuentas de usuario y grupos a través de Office 365, puede usar el centro de administración de Office o PowerShell:</span><span class="sxs-lookup"><span data-stu-id="746db-124">If you are managing user accounts and groups through Office 365, you can use the Office Admin center or PowerShell:</span></span>
  
- <span data-ttu-id="746db-125">Para el centro de administración de Office, inicie sesión con una cuenta de usuario que se ha asignado el rol de administrador de la cuenta de usuario o administrador de la compañía y usar grupos para agregar los grupos correspondientes a los grupos de acceso apropiado.</span><span class="sxs-lookup"><span data-stu-id="746db-125">For the Office Admin center, sign in with a user account that has been assigned the User Account Administrator or Company Administrator role and use Groups to add the appropriate groups to the appropriate access groups.</span></span>
    
- <span data-ttu-id="746db-p102">Para [Conectar con el módulo Azure Active Directory PowerShell V2](https://go.microsoft.com/fwlink/?linkid=842218)de primera de PowerShell. A continuación, use los siguientes comandos de PowerShell:</span><span class="sxs-lookup"><span data-stu-id="746db-p102">For PowerShell, first [Connect with the Azure Active Directory V2 PowerShell module](https://go.microsoft.com/fwlink/?linkid=842218). Then, use the following PowerShell commands:</span></span>
 
```
$newGroupName="<display name of the new group to add>"
$siteGrpName="<display name of the access group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $newGroupName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $siteGrpName }).ObjectID
```

## <a name="remove-a-user"></a><span data-ttu-id="746db-128">Quitar un usuario</span><span class="sxs-lookup"><span data-stu-id="746db-128">Remove a user</span></span>

<span data-ttu-id="746db-129">Cuando una persona acceso debe quitarse del sitio, quita desde el grupo de acceso para la que actualmente son miembros en función de su participación en el sitio:</span><span class="sxs-lookup"><span data-stu-id="746db-129">When someone's access must be removed from the site, you remove them from the access group for which they are currently a member based on their participation in the site:</span></span>
  
- <span data-ttu-id="746db-130">Administración: Quitar la cuenta de usuario del grupo de acceso de los administradores de sitio</span><span class="sxs-lookup"><span data-stu-id="746db-130">Administration: Remove the user account from the site admins access group</span></span>
    
- <span data-ttu-id="746db-131">Colaboración activo: quitar la cuenta de usuario del grupo de acceso de sitio (miembros de)</span><span class="sxs-lookup"><span data-stu-id="746db-131">Active collaboration: Remove the user account from the site members access group</span></span>
    
- <span data-ttu-id="746db-132">Visualización: Quitar la cuenta de usuario del grupo de acceso de los visores de sitio</span><span class="sxs-lookup"><span data-stu-id="746db-132">Viewing: Remove the user account from the site viewers access group</span></span>
    
<span data-ttu-id="746db-133">Si va a administrar cuentas de usuario y grupos a través de Windows Server AD, quitar los usuarios adecuados de los grupos de acceso apropiado con su usuario normal de Windows Server AD y procedimientos de administración de grupo y espere a que la sincronización con Office 365 suscripción a.</span><span class="sxs-lookup"><span data-stu-id="746db-133">If you are managing user accounts and groups through Windows Server AD, remove the appropriate users from the appropriate access groups using your normal Windows Server AD user and group management procedures and wait for synchronization with your Office 365 subscription.</span></span>
  
<span data-ttu-id="746db-134">Si va a administrar cuentas de usuario y grupos a través de Office 365, puede usar el centro de administración de Office o PowerShell:</span><span class="sxs-lookup"><span data-stu-id="746db-134">If you are managing user accounts and groups through Office 365, you can use the Office Admin center or PowerShell:</span></span>
  
- <span data-ttu-id="746db-135">Para el centro de administración de Office, inicie sesión con una cuenta de usuario que se ha asignado el rol de administrador de la cuenta de usuario o administrador de la compañía y usar grupos para quitar los usuarios adecuados de los grupos de acceso apropiado.</span><span class="sxs-lookup"><span data-stu-id="746db-135">For the Office Admin center, sign in with a user account that has been assigned the User Account Administrator or Company Administrator role and use Groups to remove the appropriate users from the appropriate access groups.</span></span>
    
- <span data-ttu-id="746db-p103">Para [Conectar con el módulo Azure Active Directory PowerShell V2](https://go.microsoft.com/fwlink/?linkid=842218)de primera de PowerShell. Para quitar una cuenta de usuario de un grupo de acceso con su UPN, use el siguiente bloque de comandos de PowerShell:</span><span class="sxs-lookup"><span data-stu-id="746db-p103">For PowerShell, first [Connect with the Azure Active Directory V2 PowerShell module](https://go.microsoft.com/fwlink/?linkid=842218). To remove a user account from an access group with its UPN, use the following PowerShell command block:</span></span>
    
```
$userUPN="<UPN of the user account>"
$grpName="<display name of the access group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

<span data-ttu-id="746db-138">Para quitar una cuenta de usuario de un grupo de acceso con su nombre para mostrar, use el siguiente bloque de comandos de PowerShell:</span><span class="sxs-lookup"><span data-stu-id="746db-138">To remove a user account from an access group with its display name, use the following PowerShell command block:</span></span>
    
```
$userDisplayName="<display name of the user account>"
$grpName="<display name of the access group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADUser | Where { $_.DisplayName -eq $userDisplayName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

## <a name="remove-a-group"></a><span data-ttu-id="746db-139">Quitar un grupo</span><span class="sxs-lookup"><span data-stu-id="746db-139">Remove a group</span></span>

<span data-ttu-id="746db-140">Para quitar el acceso de un grupo entero, quitar el grupo desde el grupo de acceso para la que actualmente son miembros en función de su participación en el sitio:</span><span class="sxs-lookup"><span data-stu-id="746db-140">To remove access for an entire group, you remove the group from the access group for which they are currently a member based on their participation in the site:</span></span>
  
- <span data-ttu-id="746db-141">Administración: Quitar el grupo desde el grupo de acceso de los administradores de sitio</span><span class="sxs-lookup"><span data-stu-id="746db-141">Administration: Remove the group from the site admins access group</span></span>
    
- <span data-ttu-id="746db-142">Colaboración activo: quitar el grupo desde el grupo de acceso de los miembros de sitio</span><span class="sxs-lookup"><span data-stu-id="746db-142">Active collaboration: Remove the group from the site members access group</span></span>
    
- <span data-ttu-id="746db-143">Visualización: Quitar el grupo desde el grupo de acceso de los visores de sitio</span><span class="sxs-lookup"><span data-stu-id="746db-143">Viewing: Remove the group from the site viewers access group</span></span>
    
<span data-ttu-id="746db-144">Si va a administrar cuentas de usuario y grupos a través de Windows Server Active Directory, quitar los grupos apropiados de los grupos de acceso apropiado mediante sus normal Windows Server AD usuario y grupo de procedimientos de administración y espere a que la sincronización con su Suscripción de Office 365.</span><span class="sxs-lookup"><span data-stu-id="746db-144">If you are managing user accounts and groups through Windows Server Active Directory, remove the appropriate groups from the appropriate access groups using your normal Windows Server AD user and group management procedures and wait for synchronization with your Office 365 subscription.</span></span>
  
<span data-ttu-id="746db-145">Si va a administrar cuentas de usuario y grupos a través de Office 365, puede usar el centro de administración de Office o PowerShell:</span><span class="sxs-lookup"><span data-stu-id="746db-145">If you are managing user accounts and groups through Office 365, you can use the Office Admin center or PowerShell:</span></span>
  
- <span data-ttu-id="746db-146">Para el centro de administración de Office, inicie sesión con una cuenta de usuario que se ha asignado el rol de administrador de la cuenta de usuario o administrador de la compañía y usar grupos para quitar los grupos apropiados de los grupos de acceso apropiado.</span><span class="sxs-lookup"><span data-stu-id="746db-146">For the Office Admin center, sign in with a user account that has been assigned the User Account Administrator or Company Administrator role and use Groups to remove the appropriate groups from the appropriate access groups.</span></span>
    
- <span data-ttu-id="746db-147">Para [Conectar con el módulo Azure Active Directory PowerShell V2](https://go.microsoft.com/fwlink/?linkid=842218)de primera de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="746db-147">For PowerShell, first [Connect with the Azure Active Directory V2 PowerShell module](https://go.microsoft.com/fwlink/?linkid=842218).</span></span>    
<span data-ttu-id="746db-148">Para quitar un grupo de un grupo de acceso mediante sus nombres para mostrar, use el siguiente bloque de comandos de PowerShell:</span><span class="sxs-lookup"><span data-stu-id="746db-148">To remove a group from an access group using their display names, use the following PowerShell command block:</span></span>
    
```
$groupMemberName="<display name of the group to remove>"
$grpName="<display name of the access group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

## <a name="create-a-documents-subfolder-with-custom-permissions"></a><span data-ttu-id="746db-149">Cree una subcarpeta de documentos con permisos personalizados</span><span class="sxs-lookup"><span data-stu-id="746db-149">Create a documents subfolder with custom permissions</span></span>

<span data-ttu-id="746db-p104">En algunos casos, un subconjunto de las personas que trabajan en el sitio aislado necesita un lugar para colaborar más privado. Para sitios de SharePoint Online, puede crear una subcarpeta en la carpeta de documentos del sitio y asignar permisos personalizados. Los que no tienen permisos no verán la subcarpeta.</span><span class="sxs-lookup"><span data-stu-id="746db-p104">In some cases, a subset of the people working within the isolated site need a more private place to collaborate. For SharePoint Online sites, you can create a subfolder in the Documents folder of the site and assign custom permissions. Those without permissions will not see the subfolder.</span></span>
  
<span data-ttu-id="746db-153">Para crear una subcarpeta de documentos con permisos personalizados, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="746db-153">To create a documents subfolder with custom permissions, do the following:</span></span>
  
1. <span data-ttu-id="746db-p105">Inicie sesión en Office 365 con una cuenta que sea miembro del grupo Administradores de acceso para el sitio. Para obtener ayuda, consulte [Where iniciar sesión en Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4).</span><span class="sxs-lookup"><span data-stu-id="746db-p105">Sign in to Office 365 with an account that is a member of the admins access group for the site. For help, see [Where to sign in to Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>
    
2. <span data-ttu-id="746db-156">Vaya al sitio del equipo aislado y haga clic en **documentos**.</span><span class="sxs-lookup"><span data-stu-id="746db-156">Go to the isolated team site and click **Documents**.</span></span>
    
3. <span data-ttu-id="746db-157">Vaya a la carpeta en la carpeta de documentos que contendrá la subcarpeta con permisos personalizados, cree la carpeta y, a continuación, ábralo.</span><span class="sxs-lookup"><span data-stu-id="746db-157">Browse to the folder in the documents folder that will contain the subfolder with custom permissions, create the folder, and then open it.</span></span>
    
4. <span data-ttu-id="746db-158">Haga clic en **Compartir**.</span><span class="sxs-lookup"><span data-stu-id="746db-158">Click **Share**.</span></span>
    
5. <span data-ttu-id="746db-159">Haga clic en **Shared con > avanzada**.</span><span class="sxs-lookup"><span data-stu-id="746db-159">Click **Shared with > Advanced**.</span></span>
    
6. <span data-ttu-id="746db-160">Haga clic en **dejar de heredar permisos**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="746db-160">Click **Stop inheriting permissions**, and then click **OK**.</span></span>
    
7. <span data-ttu-id="746db-161">Haga clic en **Compartir**.</span><span class="sxs-lookup"><span data-stu-id="746db-161">Click **Share**.</span></span>
    
8. <span data-ttu-id="746db-162">Haga clic en **Shared con > avanzada**.</span><span class="sxs-lookup"><span data-stu-id="746db-162">Click **Shared with > Advanced**.</span></span>
    
9. <span data-ttu-id="746db-163">Haga clic en **conceder permisos > Shared con > avanzada**.</span><span class="sxs-lookup"><span data-stu-id="746db-163">Click **Grant Permissions > Shared with > Advanced**.</span></span>
    
10. <span data-ttu-id="746db-164">En la página permisos, haga clic en \*\* \<nombre del sitio > (miembros de) en la lista\*\*.</span><span class="sxs-lookup"><span data-stu-id="746db-164">On the permissions page, click **\<site name> Members in the list**.</span></span>
    
11. <span data-ttu-id="746db-165">En la \*\* \<nombre del sitio > miembros\*\* de página, seleccione la marca de verificación situada junto al grupo de acceso de los miembros de sitio, haga clic en **acciones**, haga clic en **quitar usuarios del grupo**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="746db-165">On the **\<site name> Members** page, select the checkmark next to the site members access group, click **Actions**, click **Remove users from group**, and then click **OK**.</span></span>
    
12. <span data-ttu-id="746db-166">Para agregar miembros específicos a esta subcarpeta, haga clic en **Nuevo > Agregar usuarios**.</span><span class="sxs-lookup"><span data-stu-id="746db-166">To add specific members to this subfolder, click **New > Add users**.</span></span>
    
13. <span data-ttu-id="746db-167">En el cuadro de diálogo **Compartir** , escriba los nombres de las cuentas de usuario que pueden colaborar en los archivos en la subcarpeta y, a continuación, haga clic en **Compartir**.</span><span class="sxs-lookup"><span data-stu-id="746db-167">In the **Share** dialog box, type the names of the user accounts that can collaborate on files in the subfolder, and then click **Share**.</span></span>
    
14. <span data-ttu-id="746db-168">Actualice la página web para ver los resultados de la nueva.</span><span class="sxs-lookup"><span data-stu-id="746db-168">Refresh the web page to see the new results.</span></span>
    
15. <span data-ttu-id="746db-169">En los **grupos** en el panel de navegación izquierdo, haga clic en el \*\* \<nombre del sitio > visitantes\*\* de grupo y siga los pasos del 11 al 14 para especificar el conjunto de cuentas de usuario que puede ver los archivos en la subcarpeta (según sea necesario).</span><span class="sxs-lookup"><span data-stu-id="746db-169">Under **Groups** in the left navigation, click the **\<site name> Visitors** group and use steps 11-14 to specify the set of user accounts that can view the files in the subfolder (as needed).</span></span>
    
16. <span data-ttu-id="746db-170">En los **grupos** en el panel de navegación izquierdo, haga clic en el \*\* \<nombre del sitio > propietarios\*\* de grupo y siga los pasos del 11 al 14 para especificar el conjunto de cuentas de usuario que puede administrar los permisos en la subcarpeta (según sea necesario).</span><span class="sxs-lookup"><span data-stu-id="746db-170">Under **Groups** in the left navigation, click the **\<site name> Owners** group and use steps 11-14 to specify the set of user accounts that can administer the permissions in the subfolder (as needed).</span></span>
    
17. <span data-ttu-id="746db-171">Cierre la ficha **personas y grupos** en el explorador.</span><span class="sxs-lookup"><span data-stu-id="746db-171">Close the **People and Groups** tab in your browser.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="746db-172">Consulte también</span><span class="sxs-lookup"><span data-stu-id="746db-172">See Also</span></span>

[<span data-ttu-id="746db-173">Sitios de grupo de SharePoint Online aislados</span><span class="sxs-lookup"><span data-stu-id="746db-173">Isolated SharePoint Online team sites</span></span>](isolated-sharepoint-online-team-sites.md)
  
[<span data-ttu-id="746db-174">Diseñar un sitio de grupo de SharePoint Online aislado</span><span class="sxs-lookup"><span data-stu-id="746db-174">Design an isolated SharePoint Online team site</span></span>](design-an-isolated-sharepoint-online-team-site.md)

[<span data-ttu-id="746db-175">Implementar un sitio de grupo de SharePoint Online aislado</span><span class="sxs-lookup"><span data-stu-id="746db-175">Deploy an isolated SharePoint Online team site</span></span>](deploy-an-isolated-sharepoint-online-team-site.md)



