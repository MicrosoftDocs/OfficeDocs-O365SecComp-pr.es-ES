---
title: Administrar un sitio de grupo de SharePoint Online aislado
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/15/2017
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: Ent_O365
ms.custom: Ent_Solutions
ms.assetid: 79a61003-4905-4ba8-9e8a-16def7add37c
description: 'Resumen: administre el sitio de grupo de SharePoint Online aislado con estos procedimientos.'
ms.openlocfilehash: 81a6fcd80bb3e4950eb7b783d1ad964b9bc67cc5
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/23/2019
ms.locfileid: "30214490"
---
# <a name="manage-an-isolated-sharepoint-online-team-site"></a><span data-ttu-id="6920d-103">Administrar un sitio de grupo de SharePoint Online aislado</span><span class="sxs-lookup"><span data-stu-id="6920d-103">Manage an isolated SharePoint Online team site</span></span>

 <span data-ttu-id="6920d-104">**Resumen:** Administre el sitio de grupo de SharePoint Online aislado con estos procedimientos.</span><span class="sxs-lookup"><span data-stu-id="6920d-104">**Summary:** Manage your isolated SharePoint Online team site with these procedures.</span></span>
  
<span data-ttu-id="6920d-105">En este artículo se describen las operaciones de administración comunes para un sitio de grupo de SharePoint Online aislado.</span><span class="sxs-lookup"><span data-stu-id="6920d-105">This article describes common management operations for an isolated SharePoint Online team site.</span></span>
  
## <a name="add-a-new-user"></a><span data-ttu-id="6920d-106">Agregar un nuevo usuario</span><span class="sxs-lookup"><span data-stu-id="6920d-106">Add a new user</span></span>

<span data-ttu-id="6920d-107">Cuando alguien nuevo se une al sitio, debe decidir su nivel de participación en el sitio:</span><span class="sxs-lookup"><span data-stu-id="6920d-107">When someone new joins the site, you must decide their level of participation in the site:</span></span>
  
- <span data-ttu-id="6920d-108">Administración: agregar la nueva cuenta de usuario al grupo de acceso de administradores de sitios</span><span class="sxs-lookup"><span data-stu-id="6920d-108">Administration: Add the new user account to the site admins access group</span></span>
    
- <span data-ttu-id="6920d-109">Colaboración activa: agregar la cuenta de usuario al grupo de acceso de miembros del sitio</span><span class="sxs-lookup"><span data-stu-id="6920d-109">Active collaboration: Add the user account to the site members access group</span></span>
    
- <span data-ttu-id="6920d-110">Ver: agregar la cuenta de usuario al grupo de acceso de visores del sitio</span><span class="sxs-lookup"><span data-stu-id="6920d-110">Viewing: Add the user account to the site viewers access group</span></span>
    
<span data-ttu-id="6920d-111">Si administra cuentas de usuario y grupos a través de Windows Server Active Directory (AD), agregue los usuarios adecuados a los grupos de acceso adecuados mediante los procedimientos habituales de administración de grupos y usuarios de Windows Server AD y espere la sincronización con el Suscripción de Office 365.</span><span class="sxs-lookup"><span data-stu-id="6920d-111">If you are managing user accounts and groups through Windows Server Active Directory (AD), add the appropriate users to the appropriate access groups using your normal Windows Server AD user and group management procedures and wait for synchronization with your Office 365 subscription.</span></span>
  
<span data-ttu-id="6920d-112">Si administra cuentas de usuario y grupos a través de Office 365, puede usar el centro de administración de Office o PowerShell de Microsoft:</span><span class="sxs-lookup"><span data-stu-id="6920d-112">If you are managing user accounts and groups through Office 365, you can use the Office Admin center or Microsoft PowerShell:</span></span>
  
- <span data-ttu-id="6920d-113">En el centro de administración de Office, inicie sesión con una cuenta de usuario que tenga asignado el rol de administrador de la cuenta de usuario o de administrador de la compañía y use grupos para agregar los usuarios adecuados a los grupos de acceso adecuados.</span><span class="sxs-lookup"><span data-stu-id="6920d-113">For the Office Admin center, sign in with a user account that has been assigned the User Account Administrator or Company Administrator role and use Groups to add the appropriate users to the appropriate access groups.</span></span>
    
- <span data-ttu-id="6920d-p101">Para PowerShell, primero [Conéctese con el módulo de PowerShell Azure Active Directory V2](https://go.microsoft.com/fwlink/?linkid=842218). Para agregar una cuenta de usuario a un grupo de acceso con su nombre principal de usuario (UPN), use el siguiente bloque de comandos de PowerShell:</span><span class="sxs-lookup"><span data-stu-id="6920d-p101">For PowerShell, first [Connect with the Azure Active Directory V2 PowerShell module](https://go.microsoft.com/fwlink/?linkid=842218). To add a user account to an access group with its user principal name (UPN), use the following PowerShell command block:</span></span>
    
```
$userUPN="<UPN of the user account>"
$grpName="<display name of the group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

> [!TIP]
> <span data-ttu-id="6920d-116">Para obtener un archivo de texto que contenga todos los comandos de PowerShell y una hoja de cálculo de configuración de Excel que genere comandos de PowerShell en función de los nombres de cuenta de grupo y de usuario, descargue el kit de implementación de sitios de grupo de [SharePoint Online aislado](https://gallery.technet.microsoft.com/Isolated-SharePoint-Online-0b364907).</span><span class="sxs-lookup"><span data-stu-id="6920d-116">For a text file that contains all the PowerShell commands and an Excel configuration worksheet that generates PowerShell commands based on your group and user account names, download the [Isolated SharePoint Online Team Site Deployment Kit](https://gallery.technet.microsoft.com/Isolated-SharePoint-Online-0b364907).</span></span> 

<span data-ttu-id="6920d-117">Para agregar una cuenta de usuario a un grupo de acceso con su nombre para mostrar, use el siguiente bloque de comandos de PowerShell:</span><span class="sxs-lookup"><span data-stu-id="6920d-117">To add a user account to an access group with its display name, use the following PowerShell command block:</span></span>

```
$userDisplayName="<display name of the user account>"
$grpName="<display name of the group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $userDisplayName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

## <a name="add-a-new-group"></a><span data-ttu-id="6920d-118">Agregar un nuevo grupo</span><span class="sxs-lookup"><span data-stu-id="6920d-118">Add a new group</span></span>

<span data-ttu-id="6920d-119">Para agregar acceso a todo un grupo, debe decidir el nivel de participación de todos los miembros del grupo en el sitio:</span><span class="sxs-lookup"><span data-stu-id="6920d-119">To add access to an entire group, you must decide the level of participation of all the members of the group in the site:</span></span>
  
- <span data-ttu-id="6920d-120">Administración: agregar el grupo al grupo de acceso de administradores de sitios</span><span class="sxs-lookup"><span data-stu-id="6920d-120">Administration: Add the group to the site admins access group</span></span>
    
- <span data-ttu-id="6920d-121">Colaboración activa: agregar el grupo al grupo de acceso de los miembros del sitio</span><span class="sxs-lookup"><span data-stu-id="6920d-121">Active collaboration: Add the group to the site members access group</span></span>
    
- <span data-ttu-id="6920d-122">Ver: agregar el grupo al grupo de acceso de visores del sitio</span><span class="sxs-lookup"><span data-stu-id="6920d-122">Viewing: Add the group to the site viewers access group</span></span>
    
<span data-ttu-id="6920d-123">Si administra cuentas de usuario y grupos a través de Windows Server AD, agregue los grupos adecuados a los grupos adecuados mediante los procedimientos habituales de administración de usuarios y grupos de Windows Server AD y espere la sincronización con la suscripción a Office 365.</span><span class="sxs-lookup"><span data-stu-id="6920d-123">If you are managing user accounts and groups through Windows Server AD, add the appropriate groups to the appropriate groups using your normal Windows Server AD user and group management procedures and wait for synchronization with your Office 365 subscription.</span></span>
  
<span data-ttu-id="6920d-124">Si administra cuentas de usuario y grupos a través de Office 365, puede usar el centro de administración de Office o PowerShell:</span><span class="sxs-lookup"><span data-stu-id="6920d-124">If you are managing user accounts and groups through Office 365, you can use the Office Admin center or PowerShell:</span></span>
  
- <span data-ttu-id="6920d-125">En el centro de administración de Office, inicie sesión con una cuenta de usuario que tenga asignado el rol de administrador de la cuenta de usuario o de administrador de la compañía y use grupos para agregar los grupos adecuados a los grupos de acceso adecuados.</span><span class="sxs-lookup"><span data-stu-id="6920d-125">For the Office Admin center, sign in with a user account that has been assigned the User Account Administrator or Company Administrator role and use Groups to add the appropriate groups to the appropriate access groups.</span></span>
    
- <span data-ttu-id="6920d-p102">Para PowerShell, primero [Conéctese con el módulo de PowerShell Azure Active Directory V2](https://go.microsoft.com/fwlink/?linkid=842218). A continuación, use los siguientes comandos de PowerShell:</span><span class="sxs-lookup"><span data-stu-id="6920d-p102">For PowerShell, first [Connect with the Azure Active Directory V2 PowerShell module](https://go.microsoft.com/fwlink/?linkid=842218). Then, use the following PowerShell commands:</span></span>
 
```
$newGroupName="<display name of the new group to add>"
$siteGrpName="<display name of the access group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $newGroupName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $siteGrpName }).ObjectID
```

## <a name="remove-a-user"></a><span data-ttu-id="6920d-128">Quitar un usuario</span><span class="sxs-lookup"><span data-stu-id="6920d-128">Remove a user</span></span>

<span data-ttu-id="6920d-129">Cuando es necesario quitar el acceso de un usuario del sitio, se quitan del grupo de acceso para el que actualmente son miembros según su participación en el sitio:</span><span class="sxs-lookup"><span data-stu-id="6920d-129">When someone's access must be removed from the site, you remove them from the access group for which they are currently a member based on their participation in the site:</span></span>
  
- <span data-ttu-id="6920d-130">Administración: quitar la cuenta de usuario del grupo de acceso de administradores de sitios</span><span class="sxs-lookup"><span data-stu-id="6920d-130">Administration: Remove the user account from the site admins access group</span></span>
    
- <span data-ttu-id="6920d-131">Colaboración activa: quitar la cuenta de usuario del grupo de acceso de los miembros del sitio</span><span class="sxs-lookup"><span data-stu-id="6920d-131">Active collaboration: Remove the user account from the site members access group</span></span>
    
- <span data-ttu-id="6920d-132">Ver: quitar la cuenta de usuario del grupo de acceso de visores del sitio</span><span class="sxs-lookup"><span data-stu-id="6920d-132">Viewing: Remove the user account from the site viewers access group</span></span>
    
<span data-ttu-id="6920d-133">Si administra cuentas de usuario y grupos a través de Windows Server AD, quite los usuarios correspondientes de los grupos de acceso adecuados mediante los procedimientos habituales de administración de grupos y usuarios de Windows Server AD y espere la sincronización con su Office 365 scription.</span><span class="sxs-lookup"><span data-stu-id="6920d-133">If you are managing user accounts and groups through Windows Server AD, remove the appropriate users from the appropriate access groups using your normal Windows Server AD user and group management procedures and wait for synchronization with your Office 365 subscription.</span></span>
  
<span data-ttu-id="6920d-134">Si administra cuentas de usuario y grupos a través de Office 365, puede usar el centro de administración de Office o PowerShell:</span><span class="sxs-lookup"><span data-stu-id="6920d-134">If you are managing user accounts and groups through Office 365, you can use the Office Admin center or PowerShell:</span></span>
  
- <span data-ttu-id="6920d-135">En el centro de administración de Office, inicie sesión con una cuenta de usuario que tenga asignado el rol de administrador de la cuenta de usuario o de administrador de la compañía y use grupos para quitar los usuarios correspondientes de los grupos de acceso adecuados.</span><span class="sxs-lookup"><span data-stu-id="6920d-135">For the Office Admin center, sign in with a user account that has been assigned the User Account Administrator or Company Administrator role and use Groups to remove the appropriate users from the appropriate access groups.</span></span>
    
- <span data-ttu-id="6920d-p103">Para PowerShell, primero [Conéctese con el módulo de PowerShell Azure Active Directory V2](https://go.microsoft.com/fwlink/?linkid=842218). Para quitar una cuenta de usuario de un grupo de acceso con su UPN, use el siguiente bloque de comandos de PowerShell:</span><span class="sxs-lookup"><span data-stu-id="6920d-p103">For PowerShell, first [Connect with the Azure Active Directory V2 PowerShell module](https://go.microsoft.com/fwlink/?linkid=842218). To remove a user account from an access group with its UPN, use the following PowerShell command block:</span></span>
    
```
$userUPN="<UPN of the user account>"
$grpName="<display name of the access group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

<span data-ttu-id="6920d-138">Para quitar una cuenta de usuario de un grupo de acceso con su nombre para mostrar, use el siguiente bloque de comandos de PowerShell:</span><span class="sxs-lookup"><span data-stu-id="6920d-138">To remove a user account from an access group with its display name, use the following PowerShell command block:</span></span>
    
```
$userDisplayName="<display name of the user account>"
$grpName="<display name of the access group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADUser | Where { $_.DisplayName -eq $userDisplayName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

## <a name="remove-a-group"></a><span data-ttu-id="6920d-139">Quitar un grupo</span><span class="sxs-lookup"><span data-stu-id="6920d-139">Remove a group</span></span>

<span data-ttu-id="6920d-140">Para quitar el acceso de un grupo completo, se quita el grupo del grupo de acceso para el que se integra en ese momento en función de su participación en el sitio:</span><span class="sxs-lookup"><span data-stu-id="6920d-140">To remove access for an entire group, you remove the group from the access group for which they are currently a member based on their participation in the site:</span></span>
  
- <span data-ttu-id="6920d-141">Administración: quitar el grupo del grupo de acceso de administradores de sitios</span><span class="sxs-lookup"><span data-stu-id="6920d-141">Administration: Remove the group from the site admins access group</span></span>
    
- <span data-ttu-id="6920d-142">Colaboración activa: quitar el grupo del grupo de acceso de los miembros del sitio</span><span class="sxs-lookup"><span data-stu-id="6920d-142">Active collaboration: Remove the group from the site members access group</span></span>
    
- <span data-ttu-id="6920d-143">Ver: quitar el grupo del grupo de acceso de visores del sitio</span><span class="sxs-lookup"><span data-stu-id="6920d-143">Viewing: Remove the group from the site viewers access group</span></span>
    
<span data-ttu-id="6920d-144">Si administra cuentas de usuario y grupos a través de Windows Server Active Directory, quite los grupos adecuados de los grupos de acceso adecuados mediante los procedimientos habituales de administración de grupos y usuarios de Windows Server AD y espere la sincronización con el Suscripción de Office 365.</span><span class="sxs-lookup"><span data-stu-id="6920d-144">If you are managing user accounts and groups through Windows Server Active Directory, remove the appropriate groups from the appropriate access groups using your normal Windows Server AD user and group management procedures and wait for synchronization with your Office 365 subscription.</span></span>
  
<span data-ttu-id="6920d-145">Si administra cuentas de usuario y grupos a través de Office 365, puede usar el centro de administración de Office o PowerShell:</span><span class="sxs-lookup"><span data-stu-id="6920d-145">If you are managing user accounts and groups through Office 365, you can use the Office Admin center or PowerShell:</span></span>
  
- <span data-ttu-id="6920d-146">En el centro de administración de Office, inicie sesión con una cuenta de usuario que tenga asignado el rol de administrador de la cuenta de usuario o de administrador de la compañía y use grupos para quitar los grupos adecuados de los grupos de acceso adecuados.</span><span class="sxs-lookup"><span data-stu-id="6920d-146">For the Office Admin center, sign in with a user account that has been assigned the User Account Administrator or Company Administrator role and use Groups to remove the appropriate groups from the appropriate access groups.</span></span>
    
- <span data-ttu-id="6920d-147">Para PowerShell, primero [Conéctese con el módulo de PowerShell Azure Active Directory V2](https://go.microsoft.com/fwlink/?linkid=842218).</span><span class="sxs-lookup"><span data-stu-id="6920d-147">For PowerShell, first [Connect with the Azure Active Directory V2 PowerShell module](https://go.microsoft.com/fwlink/?linkid=842218).</span></span>    
<span data-ttu-id="6920d-148">Para quitar un grupo de un grupo de acceso mediante sus nombres para mostrar, use el siguiente bloque de comandos de PowerShell:</span><span class="sxs-lookup"><span data-stu-id="6920d-148">To remove a group from an access group using their display names, use the following PowerShell command block:</span></span>
    
```
$groupMemberName="<display name of the group to remove>"
$grpName="<display name of the access group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

## <a name="create-a-documents-subfolder-with-custom-permissions"></a><span data-ttu-id="6920d-149">Crear una subcarpeta de documentos con permisos personalizados</span><span class="sxs-lookup"><span data-stu-id="6920d-149">Create a documents subfolder with custom permissions</span></span>

<span data-ttu-id="6920d-p104">En algunos casos, un subconjunto de las personas que trabajan en el sitio aislado necesita un lugar más privado para colaborar. Para los sitios de SharePoint Online, puede crear una subcarpeta en la carpeta documentos del sitio y asignar permisos personalizados. Los usuarios sin permisos no verán la subcarpeta.</span><span class="sxs-lookup"><span data-stu-id="6920d-p104">In some cases, a subset of the people working within the isolated site need a more private place to collaborate. For SharePoint Online sites, you can create a subfolder in the Documents folder of the site and assign custom permissions. Those without permissions will not see the subfolder.</span></span>
  
<span data-ttu-id="6920d-153">Para crear una subcarpeta de documentos con permisos personalizados, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="6920d-153">To create a documents subfolder with custom permissions, do the following:</span></span>
  
1. <span data-ttu-id="6920d-p105">Inicie sesión en Office 365 con una cuenta que sea miembro del grupo de administradores de acceso para el sitio. Para obtener ayuda, consulte [dónde iniciar sesión en Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4).</span><span class="sxs-lookup"><span data-stu-id="6920d-p105">Sign in to Office 365 with an account that is a member of the admins access group for the site. For help, see [Where to sign in to Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>
    
2. <span data-ttu-id="6920d-156">Vaya al sitio de grupo aislado y haga clic en **documentos**.</span><span class="sxs-lookup"><span data-stu-id="6920d-156">Go to the isolated team site and click **Documents**.</span></span>
    
3. <span data-ttu-id="6920d-157">Vaya a la carpeta de la carpeta documentos que contendrá la subcarpeta con permisos personalizados, cree la carpeta y, a continuación, ábrala.</span><span class="sxs-lookup"><span data-stu-id="6920d-157">Browse to the folder in the documents folder that will contain the subfolder with custom permissions, create the folder, and then open it.</span></span>
    
4. <span data-ttu-id="6920d-158">Haga clic en **Compartir**.</span><span class="sxs-lookup"><span data-stu-id="6920d-158">Click **Share**.</span></span>
    
5. <span data-ttu-id="6920d-159">Haga clic en **compartido con _GT_ avanzadas**.</span><span class="sxs-lookup"><span data-stu-id="6920d-159">Click **Shared with > Advanced**.</span></span>
    
6. <span data-ttu-id="6920d-160">Haga clic en **dejar de heredar permisos**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="6920d-160">Click **Stop inheriting permissions**, and then click **OK**.</span></span>
    
7. <span data-ttu-id="6920d-161">Haga clic en **Compartir**.</span><span class="sxs-lookup"><span data-stu-id="6920d-161">Click **Share**.</span></span>
    
8. <span data-ttu-id="6920d-162">Haga clic en **compartido con _GT_ avanzadas**.</span><span class="sxs-lookup"><span data-stu-id="6920d-162">Click **Shared with > Advanced**.</span></span>
    
9. <span data-ttu-id="6920d-163">Haga clic en **conceder permisos _GT_ Shared with _GT_ Advanced**.</span><span class="sxs-lookup"><span data-stu-id="6920d-163">Click **Grant Permissions > Shared with > Advanced**.</span></span>
    
10. <span data-ttu-id="6920d-164">En la página permisos, haga clic \*\* \<en miembros del name> del sitio de la lista\*\*.</span><span class="sxs-lookup"><span data-stu-id="6920d-164">On the permissions page, click **\<site name> Members in the list**.</span></span>
    
11. <span data-ttu-id="6920d-165">En la \*\* \<página miembros del sitio name>\*\* , seleccione la marca de verificación junto al grupo acceso de miembros del sitio, haga clic en **acciones**, haga clic en **quitar usuarios del grupo**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="6920d-165">On the **\<site name> Members** page, select the checkmark next to the site members access group, click **Actions**, click **Remove users from group**, and then click **OK**.</span></span>
    
12. <span data-ttu-id="6920d-166">Para agregar miembros específicos a esta subcarpeta, haga clic en **nuevo _GT_ agregar usuarios**.</span><span class="sxs-lookup"><span data-stu-id="6920d-166">To add specific members to this subfolder, click **New > Add users**.</span></span>
    
13. <span data-ttu-id="6920d-167">En el cuadro de diálogo **compartir** , escriba los nombres de las cuentas de usuario que pueden colaborar en los archivos de la subcarpeta y, a continuación, haga clic en **compartir**.</span><span class="sxs-lookup"><span data-stu-id="6920d-167">In the **Share** dialog box, type the names of the user accounts that can collaborate on files in the subfolder, and then click **Share**.</span></span>
    
14. <span data-ttu-id="6920d-168">Actualice la página web para ver los nuevos resultados.</span><span class="sxs-lookup"><span data-stu-id="6920d-168">Refresh the web page to see the new results.</span></span>
    
15. <span data-ttu-id="6920d-169">en **grupos** en el panel de navegación izquierdo, haga clic en el \*\* \<grupo name> visitantes\*\* y use los pasos 11-14 para especificar el conjunto de cuentas de usuario que pueden ver los archivos de la subcarpeta (según sea necesario).</span><span class="sxs-lookup"><span data-stu-id="6920d-169">Under **Groups** in the left navigation, click the **\<site name> Visitors** group and use steps 11-14 to specify the set of user accounts that can view the files in the subfolder (as needed).</span></span>
    
16. <span data-ttu-id="6920d-170">en **grupos** en el panel de navegación izquierdo, \*\* \<\*\* haga clic en el grupo propietarios de name> de sitios y use los pasos 11-14 para especificar el conjunto de cuentas de usuario que pueden administrar los permisos de la subcarpeta (según sea necesario).</span><span class="sxs-lookup"><span data-stu-id="6920d-170">Under **Groups** in the left navigation, click the **\<site name> Owners** group and use steps 11-14 to specify the set of user accounts that can administer the permissions in the subfolder (as needed).</span></span>
    
17. <span data-ttu-id="6920d-171">Cierre la pestaña **personas y grupos** del explorador.</span><span class="sxs-lookup"><span data-stu-id="6920d-171">Close the **People and Groups** tab in your browser.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="6920d-172">Vea también</span><span class="sxs-lookup"><span data-stu-id="6920d-172">See Also</span></span>

[<span data-ttu-id="6920d-173">Sitios de grupo de SharePoint Online aislados</span><span class="sxs-lookup"><span data-stu-id="6920d-173">Isolated SharePoint Online team sites</span></span>](isolated-sharepoint-online-team-sites.md)
  
[<span data-ttu-id="6920d-174">Diseñar un sitio de grupo de SharePoint Online aislado</span><span class="sxs-lookup"><span data-stu-id="6920d-174">Design an isolated SharePoint Online team site</span></span>](design-an-isolated-sharepoint-online-team-site.md)

[<span data-ttu-id="6920d-175">Implementar un sitio de grupo de SharePoint Online aislado</span><span class="sxs-lookup"><span data-stu-id="6920d-175">Deploy an isolated SharePoint Online team site</span></span>](deploy-an-isolated-sharepoint-online-team-site.md)



