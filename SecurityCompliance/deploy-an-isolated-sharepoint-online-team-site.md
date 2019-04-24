---
title: Implementar un sitio de grupo de SharePoint Online aislado
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 05/14/2018
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: Ent_O365
ms.custom: Ent_Solutions
ms.assetid: 3033614b-e23b-4f68-9701-f62525eafaab
description: 'Resumen: implemente un nuevo sitio de grupo aislado de SharePoint Online con estas instrucciones paso a paso.'
ms.openlocfilehash: 4cb60cd55f526592cb469d80a061375a4f556afe
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32257028"
---
# <a name="deploy-an-isolated-sharepoint-online-team-site"></a><span data-ttu-id="6e476-103">Implementar un sitio de grupo de SharePoint Online aislado</span><span class="sxs-lookup"><span data-stu-id="6e476-103">Deploy an isolated SharePoint Online team site</span></span>

 <span data-ttu-id="6e476-104">**Resumen:** Implemente un nuevo sitio de grupo aislado de SharePoint Online con estas instrucciones paso a paso.</span><span class="sxs-lookup"><span data-stu-id="6e476-104">**Summary:** Deploy a new isolated SharePoint Online team site with these step-by-step instructions.</span></span>
  
<span data-ttu-id="6e476-105">Este artículo es una guía paso a paso para la implementación de la creación y configuración de un sitio de grupo aislado de SharePoint Online en Microsoft Office 365.</span><span class="sxs-lookup"><span data-stu-id="6e476-105">This article is a step-by-step deployment guide for creating and configuring an isolated SharePoint Online team site in Microsoft Office 365.</span></span> <span data-ttu-id="6e476-106">En estos pasos se presupone el uso de los tres grupos de SharePoint predeterminados y los niveles de permisos correspondientes, con un solo grupo de acceso basado en Azure Active Directory (AD) para cada nivel de acceso.</span><span class="sxs-lookup"><span data-stu-id="6e476-106">These steps assume the use of the three default SharePoint groups and corresponding permission levels, with a single Azure Active Directory (AD)-based access group for each level of access.</span></span>
  
## <a name="phase-1-create-and-populate-the-team-site-access-groups"></a><span data-ttu-id="6e476-107">Fase 1: crear y rellenar los grupos de acceso a sitios de grupo</span><span class="sxs-lookup"><span data-stu-id="6e476-107">Phase 1: Create and populate the team site access groups</span></span>

<span data-ttu-id="6e476-108">En esta fase, se crean los tres grupos de acceso basados en Azure AD para los tres grupos de SharePoint predeterminados y se rellenan con las cuentas de usuario adecuadas.</span><span class="sxs-lookup"><span data-stu-id="6e476-108">In this phase, you create the three Azure AD-based access groups for the three default SharePoint groups and populate them with the appropriate user accounts.</span></span>
  
> [!NOTE]
> <span data-ttu-id="6e476-109">En los pasos siguientes se supone que ya existen todas las cuentas de usuario necesarias y que se les asignan las licencias adecuadas.</span><span class="sxs-lookup"><span data-stu-id="6e476-109">The following steps assume that all necessary user accounts already exist and are assigned the appropriate licenses.</span></span> <span data-ttu-id="6e476-110">Si no es así, agréguelos y asigne licencias antes de continuar con el paso 1.</span><span class="sxs-lookup"><span data-stu-id="6e476-110">If not, please add them and assign licenses before proceeding to step 1.</span></span> 
  
### <a name="step-1-list-the-sharepoint-online-admins-for-the-site"></a><span data-ttu-id="6e476-111">Paso 1: enumerar los administradores de SharePoint Online para el sitio</span><span class="sxs-lookup"><span data-stu-id="6e476-111">Step 1: List the SharePoint Online admins for the site</span></span>

<span data-ttu-id="6e476-112">DeTermine el conjunto de cuentas de usuario correspondiente a los administradores de SharePoint Online para el sitio de grupo aislado.</span><span class="sxs-lookup"><span data-stu-id="6e476-112">Determine the set of user accounts corresponding to the SharePoint Online admins for the isolated team site.</span></span>
  
<span data-ttu-id="6e476-113">Si administra cuentas de usuario y grupos a través de Office 365 y desea usar Windows PowerShell, cree una lista de sus nombres principales de usuario (UPN) (por ejemplo, UPN: belindan@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="6e476-113">If you are managing user accounts and groups through Office 365 and want to use Windows PowerShell, make a list of their user principal names (UPNs) (example UPN: belindan@contoso.com).</span></span>
  
### <a name="step-2-list-the-members-for-the-site"></a><span data-ttu-id="6e476-114">Paso 2: enumerar los miembros del sitio</span><span class="sxs-lookup"><span data-stu-id="6e476-114">Step 2: List the members for the site</span></span>

<span data-ttu-id="6e476-115">DeTermine el conjunto de cuentas de usuario correspondiente a los miembros del sitio de grupo aislado, quienes colaboran en los recursos almacenados en el sitio.</span><span class="sxs-lookup"><span data-stu-id="6e476-115">Determine the set of user accounts corresponding to the members for the isolated team site, those who will be collaborating on resources stored within the site.</span></span>
  
<span data-ttu-id="6e476-116">Si administra cuentas de usuario y grupos a través de Office 365 y desea usar PowerShell, cree una lista de sus UPN.</span><span class="sxs-lookup"><span data-stu-id="6e476-116">If you are managing user accounts and groups through Office 365 and want to use PowerShell, make a list of their UPNs.</span></span> <span data-ttu-id="6e476-117">Si hay muchos miembros del sitio, puede almacenar la lista de UPN en un archivo de texto y agregarlos todos con un solo comando de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6e476-117">If there are a lot of site members, you can store the list of UPNs in a text file and add them all with a single PowerShell command.</span></span>
  
### <a name="step-3-list-the-viewers-for-the-site"></a><span data-ttu-id="6e476-118">Paso 3: enumerar los visores del sitio</span><span class="sxs-lookup"><span data-stu-id="6e476-118">Step 3: List the viewers for the site</span></span>

<span data-ttu-id="6e476-119">DeTermine el conjunto de cuentas de usuario correspondiente a los visores del sitio de grupo aislado, las personas que pueden ver los recursos almacenados en el sitio, pero no pueden modificarlos ni colaborar directamente en su contenido.</span><span class="sxs-lookup"><span data-stu-id="6e476-119">Determine the set of user accounts corresponding to the viewers of the isolated team site, those who can view the resources stored in the site but not modify them or directly collaborate on their contents.</span></span>
  
<span data-ttu-id="6e476-120">Si administra cuentas de usuario y grupos a través de Office 365 y desea usar PowerShell, cree una lista de sus UPN.</span><span class="sxs-lookup"><span data-stu-id="6e476-120">If you are managing user accounts and groups through Office 365 and want to use PowerShell, make a list of their UPNs.</span></span> <span data-ttu-id="6e476-121">Si hay muchos miembros del sitio, puede almacenar la lista de UPN en un archivo de texto y agregarlos todos con un solo comando de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6e476-121">If there are a lot of site members, you can store the list of UPNs in a text file and add them all with a single PowerShell command.</span></span>
  
<span data-ttu-id="6e476-122">Los visores del sitio pueden incluir la administración ejecutiva, los asesores legales o las partes interesadas entre departamentos.</span><span class="sxs-lookup"><span data-stu-id="6e476-122">Viewers for the site might include executive management, legal counsel, or inter-departmental stakeholders.</span></span>
  
### <a name="step-4-create-the-three-access-groups-for-the-site-in-azure-ad"></a><span data-ttu-id="6e476-123">Paso 4: crear los tres grupos de acceso para el sitio en Azure AD</span><span class="sxs-lookup"><span data-stu-id="6e476-123">Step 4: Create the three access groups for the site in Azure AD</span></span>

<span data-ttu-id="6e476-124">Debe crear los siguientes grupos de acceso en Azure AD:</span><span class="sxs-lookup"><span data-stu-id="6e476-124">You need to create the following access groups in Azure AD:</span></span>
  
- <span data-ttu-id="6e476-125">Administradores de sitios (que contendrán la lista del paso 1)</span><span class="sxs-lookup"><span data-stu-id="6e476-125">Site admins (which will contain the list from step 1)</span></span>
    
- <span data-ttu-id="6e476-126">Miembros del sitio (que contendrán la lista del paso 2)</span><span class="sxs-lookup"><span data-stu-id="6e476-126">Site members (which will contain the list from step 2)</span></span>
    
- <span data-ttu-id="6e476-127">Visores del sitio (que contendrán la lista del paso 3)</span><span class="sxs-lookup"><span data-stu-id="6e476-127">Site viewers (which will contain the list from step 3)</span></span>
    
1. <span data-ttu-id="6e476-128">En el explorador, vaya a Azure portal en [https://portal.azure.com](https://portal.azure.com) e inicie sesión con las credenciales de una cuenta que se haya asignado con el rol de administrador de administración de usuarios o administrador de la compañía.</span><span class="sxs-lookup"><span data-stu-id="6e476-128">In your browser, go to the Azure portal at [https://portal.azure.com](https://portal.azure.com) and sign in with the credentials of an account that has been assigned with User Management Admin or Company Administrator role.</span></span>
    
2. <span data-ttu-id="6e476-129">En Azure Portal, haga clic en **Azure Active Directory > Grupos**.</span><span class="sxs-lookup"><span data-stu-id="6e476-129">In the Azure portal, click **Azure Active Directory > Groups**.</span></span>
    
3. <span data-ttu-id="6e476-130">En la hoja **Todos los grupos**, haga clic en **+ Nuevo grupo**.</span><span class="sxs-lookup"><span data-stu-id="6e476-130">On the **Groups - All groups** blade, click **+ New group**.</span></span>
    
4. <span data-ttu-id="6e476-131">En la hoja **Grupo**:</span><span class="sxs-lookup"><span data-stu-id="6e476-131">On the **Group** blade:</span></span>
    
  - <span data-ttu-id="6e476-132">Seleccione **Office 365** en **Tipo de grupo**.</span><span class="sxs-lookup"><span data-stu-id="6e476-132">Select **Office 365** in **Group type**.</span></span>
    
  - <span data-ttu-id="6e476-133">Escriba el nombre del grupo en **nombre**.</span><span class="sxs-lookup"><span data-stu-id="6e476-133">Type the group name in **Name**.</span></span>
    
  - <span data-ttu-id="6e476-134">Escriba una descripción del grupo en **Descripción del grupo**.</span><span class="sxs-lookup"><span data-stu-id="6e476-134">Type a description of the group in **Group description**.</span></span>
    
  - <span data-ttu-id="6e476-135">Seleccione **Asignada** en **Tipo de pertenencia**.</span><span class="sxs-lookup"><span data-stu-id="6e476-135">Select **Assigned** in **Membership type**.</span></span>
    
5. <span data-ttu-id="6e476-136">Haga clic en **Crear** y, después, cierre la hoja **Grupo**.</span><span class="sxs-lookup"><span data-stu-id="6e476-136">Click **Create**, and then close the **Group** blade.</span></span>
    
6. <span data-ttu-id="6e476-137">Repita los pasos 3-5 para los grupos adicionales.</span><span class="sxs-lookup"><span data-stu-id="6e476-137">Repeat steps 3-5 for your additional groups.</span></span>
    
> [!NOTE]
> <span data-ttu-id="6e476-138">Debe usar el portal de Azure para crear los grupos para que tengan habilitadas las características de Office.</span><span class="sxs-lookup"><span data-stu-id="6e476-138">You need to use the Azure portal to create the groups so that they have Office features enabled.</span></span> <span data-ttu-id="6e476-139">Si un sitio aislado de SharePoint Online se configura más adelante como un sitio extremadamente confidencial con una etiqueta de Azure Information Protection para cifrar archivos y asignar permisos a grupos específicos, los grupos permitidos deben haberse creado con las características de Office habilitadas.</span><span class="sxs-lookup"><span data-stu-id="6e476-139">If a SharePoint Online isolated site is later configured as a Highly Confidential site with an Azure Information Protection label to encrypt files and assign permission to specific groups, the permitted groups must have been created with Office features enabled.</span></span> <span data-ttu-id="6e476-140">No puede cambiar la configuración de las características de Office de un grupo de Azure AD una vez creado.</span><span class="sxs-lookup"><span data-stu-id="6e476-140">You cannot change the Office features setting of an Azure AD group after it has been created.</span></span> 
  
<span data-ttu-id="6e476-141">Esta es la configuración resultante con los tres grupos de acceso al sitio.</span><span class="sxs-lookup"><span data-stu-id="6e476-141">Here is your resulting configuration with the three site access groups.</span></span>
  
![Los tres grupos de acceso para la implementación de un sitio de SharePoint Online aislado.](media/c2557f61-478b-4494-95e9-d79fe5909e8b.png)
  
### <a name="step-5-add-the-user-accounts-to-the-access-groups"></a><span data-ttu-id="6e476-143">Paso 5.</span><span class="sxs-lookup"><span data-stu-id="6e476-143">Step 5.</span></span> <span data-ttu-id="6e476-144">Agregar las cuentas de usuario a los grupos de acceso</span><span class="sxs-lookup"><span data-stu-id="6e476-144">Add the user accounts to the access groups</span></span>

<span data-ttu-id="6e476-145">En este paso, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="6e476-145">In this step, do the following:</span></span>
  
1. <span data-ttu-id="6e476-146">Agregar la lista de usuarios del paso 1 al grupo de acceso de administradores de sitios</span><span class="sxs-lookup"><span data-stu-id="6e476-146">Add the list of users from step 1 to the site admins access group</span></span>
    
2. <span data-ttu-id="6e476-147">Agregar la lista de usuarios del paso 2 al grupo de acceso de miembros del sitio</span><span class="sxs-lookup"><span data-stu-id="6e476-147">Add the list of users from step 2 to the site members access group</span></span>
    
3. <span data-ttu-id="6e476-148">Agregar la lista de usuarios del paso 3 al grupo de acceso de visores del sitio</span><span class="sxs-lookup"><span data-stu-id="6e476-148">Add the list of users from step 3 to the site viewers access group</span></span>
    
<span data-ttu-id="6e476-149">Si administra cuentas de usuario y grupos a través de Windows Server AD, agregue usuarios a los grupos de acceso adecuados mediante los procedimientos habituales de administración de usuarios y grupos de Windows Server AD y espere la sincronización con su suscripción de Office 365.</span><span class="sxs-lookup"><span data-stu-id="6e476-149">If you are managing user accounts and groups through Windows Server AD, add users to the appropriate access groups using your normal Windows Server AD user and group management procedures and wait for synchronization with your Office 365 subscription.</span></span>
  
<span data-ttu-id="6e476-150">Si administra cuentas de usuario y grupos a través de Office 365, puede usar el centro de administración de Office o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6e476-150">If you are managing user accounts and groups through Office 365, you can use the Office Admin center or PowerShell.</span></span> <span data-ttu-id="6e476-151">Si tiene nombres de grupo duplicados para cualquiera de los grupos de acceso, debe usar el centro de administración de Office.</span><span class="sxs-lookup"><span data-stu-id="6e476-151">If you have duplicate group names for any of the access groups, you should use the Office Admin center.</span></span>
  
<span data-ttu-id="6e476-152">En el centro de administración de Office, inicie sesión con una cuenta de usuario que tenga asignado el rol de administrador de la cuenta de usuario o de administrador de la compañía y use grupos para agregar las cuentas de usuario y los grupos adecuados a los grupos de acceso apropiados.</span><span class="sxs-lookup"><span data-stu-id="6e476-152">For the Office Admin center, sign in with a user account that has been assigned the User Account Administrator or Company Administrator role and use Groups to add the appropriate user accounts and groups to the appropriate access groups.</span></span>
  
<span data-ttu-id="6e476-153">Para PowerShell, primero [Conéctese con el módulo Azure Active Directory PowerShell para Graph](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span><span class="sxs-lookup"><span data-stu-id="6e476-153">For PowerShell, first [Connect with the Azure Active Directory PowerShell for Graph module](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
  
<span data-ttu-id="6e476-154">A continuación, use el siguiente bloque de comandos para agregar una cuenta de usuario individual a un grupo de acceso:</span><span class="sxs-lookup"><span data-stu-id="6e476-154">Next, use the following command block to add an individual user account to an access group:</span></span>
  
```
$userUPN="<UPN of the user account>"
$grpName="<display name of the access group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

> [!TIP]
> <span data-ttu-id="6e476-155">Para obtener un archivo de texto que contenga todos los comandos de PowerShell y una hoja de cálculo de configuración de Excel que genere comandos de PowerShell en función de los nombres de cuenta de grupo y de usuario, descargue el kit de implementación de sitios de grupo de [SharePoint Online aislado](https://gallery.technet.microsoft.com/Isolated-SharePoint-Online-0b364907).</span><span class="sxs-lookup"><span data-stu-id="6e476-155">For a text file that contains all the PowerShell commands and an Excel configuration worksheet that generates PowerShell commands based on your group and user account names, download the [Isolated SharePoint Online Team Site Deployment Kit](https://gallery.technet.microsoft.com/Isolated-SharePoint-Online-0b364907).</span></span> 
  
<span data-ttu-id="6e476-156">Si ha guardado los UPN de cuentas de usuario para cualquiera de los grupos de acceso de un archivo de texto, puede usar el siguiente bloque de comandos de PowerShell para agregarlos todos a la vez:</span><span class="sxs-lookup"><span data-stu-id="6e476-156">If you stored the UPNs of user accounts for any of the access groups in a text file, you can use the following PowerShell command block to add them all at one time:</span></span>
  
```
$grpName="<display name of the access group>"
$fileName="<path and name of the file containing the list of account UPNs>"
$grpID=(Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
Get-Content $fileName | ForEach { $userUPN=$_; Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectID $grpID }
```

<span data-ttu-id="6e476-157">Para PowerShell, use el siguiente bloque de comandos para agregar un grupo individual a un grupo de acceso:</span><span class="sxs-lookup"><span data-stu-id="6e476-157">For PowerShell, use the following command block to add an individual group to an access group:</span></span>
  
```
$nestedGrpName="<display name of the group to add to the access group>"
$grpName="<display name of the access group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $nestedGrpName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID

```

<span data-ttu-id="6e476-158">Los resultados deben ser los siguientes:</span><span class="sxs-lookup"><span data-stu-id="6e476-158">The results should be the following:</span></span>
  
- <span data-ttu-id="6e476-159">El grupo de administradores de sitios de Azure AD contiene los grupos o cuentas de usuario de administrador del sitio</span><span class="sxs-lookup"><span data-stu-id="6e476-159">The site admins Azure AD group contains the site admin user accounts or groups</span></span>
    
- <span data-ttu-id="6e476-160">El grupo de miembros del sitio de Azure AD contiene los grupos o cuentas de usuario de los miembros del sitio</span><span class="sxs-lookup"><span data-stu-id="6e476-160">The site members Azure AD group contains the site member user accounts or groups</span></span>
    
- <span data-ttu-id="6e476-161">El grupo visores de sitio de Azure AD contiene las cuentas de usuario o los grupos que solo pueden ver el contenido del sitio</span><span class="sxs-lookup"><span data-stu-id="6e476-161">The site viewers Azure AD group contains the user accounts or groups that can only view the site contents</span></span>
    
<span data-ttu-id="6e476-162">Validar la lista de miembros del grupo para cada grupo de acceso con el centro de administración de Office o con el siguiente bloque de comandos de PowerShell:</span><span class="sxs-lookup"><span data-stu-id="6e476-162">Validate the list of group members for each access group with the Office Admin center or with the following PowerShell command block:</span></span>
  
```
$grpName="<display name of the access group>"
Get-AzureADGroupMember -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID | Sort UserPrincipalName | Select UserPrincipalName,DisplayName,UserType
```

<span data-ttu-id="6e476-163">Esta es la configuración resultante con los tres grupos de acceso al sitio rellenados con cuentas de usuario o grupos.</span><span class="sxs-lookup"><span data-stu-id="6e476-163">Here is your resulting configuration with the three site access groups populated with user accounts or groups.</span></span>
  
![Los tres grupos de acceso completados con cuentas de usuario.](media/2320107c-dad6-4c8f-94e5-f6427c125e71.png)
  
## <a name="phase-2-create-and-configure-the-isolated-team-site"></a><span data-ttu-id="6e476-165">Fase 2: crear y configurar el sitio de grupo aislado</span><span class="sxs-lookup"><span data-stu-id="6e476-165">Phase 2: Create and configure the isolated team site</span></span>

<span data-ttu-id="6e476-166">En esta fase, se crea el sitio de SharePoint Online aislado y se configuran los permisos para los niveles de permisos predeterminados de SharePoint Online para usar los nuevos grupos de acceso basados en Azure AD.</span><span class="sxs-lookup"><span data-stu-id="6e476-166">In this phase, you create the isolated SharePoint Online site and configure the permissions for the default SharePoint Online permission levels to use your new Azure AD-based access groups.</span></span>
  
<span data-ttu-id="6e476-167">En primer lugar, cree el sitio de grupo de SharePoint Online con estos pasos.</span><span class="sxs-lookup"><span data-stu-id="6e476-167">First, create the SharePoint Online team site with these steps.</span></span>
  
1. <span data-ttu-id="6e476-168">Inicie sesión en el centro de administración con una cuenta que también se vaya a usar para administrar el sitio de grupo de SharePoint Online (un administrador de SharePoint Online).</span><span class="sxs-lookup"><span data-stu-id="6e476-168">Sign in to the admin center with an account that will also be used to administer the SharePoint Online team site (a SharePoint Online administrator).</span></span> <span data-ttu-id="6e476-169">Para obtener ayuda, vea [Dónde iniciar sesión en Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4).</span><span class="sxs-lookup"><span data-stu-id="6e476-169">For help, see [Where to sign in to Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>
    
2. <span data-ttu-id="6e476-170">En la lista de iconos, haga clic en **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="6e476-170">In the list of tiles, click **SharePoint**.</span></span>
    
3. <span data-ttu-id="6e476-171">En la nueva pestaña **SharePoint** del explorador, haga clic en **+ Crear sitio**.</span><span class="sxs-lookup"><span data-stu-id="6e476-171">In the new **SharePoint** tab of your browser, click **+ Create site**.</span></span>
    
4. <span data-ttu-id="6e476-172">En la página **Crear un sitio**, haga clic en **Sitio de grupo**.</span><span class="sxs-lookup"><span data-stu-id="6e476-172">On the **Create a site** page, click **Team site**.</span></span>
    
5. <span data-ttu-id="6e476-173">En **nombre del sitio**, escriba un nombre para el sitio de grupo.</span><span class="sxs-lookup"><span data-stu-id="6e476-173">In **Site name**, type a name for the team site.</span></span> 
    
6. <span data-ttu-id="6e476-174">En **Descripción del sitio de grupo,** escriba una descripción opcional del propósito del sitio.</span><span class="sxs-lookup"><span data-stu-id="6e476-174">In **Team site description,** type an optional description of the purpose of the site.</span></span>
    
7. <span data-ttu-id="6e476-175">En **Configuración de privacidad**, seleccione **Privado: solo los miembros pueden obtener acceso a este sitio** y, después, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="6e476-175">In **Privacy settings**, select **Private - only members can access this site**, and then click **Next**.</span></span>
    
8. <span data-ttu-id="6e476-176">En el panel **Usuarios que quiere agregar**, haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="6e476-176">On the **Who do you want to add?** pane, click **Finish**.</span></span>
    
<span data-ttu-id="6e476-177">Después, desde el nuevo sitio de grupo de SharePoint Online, configure los permisos.</span><span class="sxs-lookup"><span data-stu-id="6e476-177">Next, from the new SharePoint Online team site, configure permissions.</span></span>
  
1. <span data-ttu-id="6e476-178">En la barra de herramientas, haga clic en el icono de configuración y, luego, en **Permisos del sitio**.</span><span class="sxs-lookup"><span data-stu-id="6e476-178">In the tool bar, click the settings icon, and then click **Site permissions**.</span></span>
    
2. <span data-ttu-id="6e476-179">En el panel **Permisos del sitio**, haga clic en **Advanced permissions settings** (Configuración de permisos avanzada).</span><span class="sxs-lookup"><span data-stu-id="6e476-179">In the **Site permissions** pane, click **Advanced permissions settings**.</span></span>
    
3. <span data-ttu-id="6e476-180">En la nueva pestaña **Permisos** del explorador, haga clic en **Configuración de solicitud de acceso**.</span><span class="sxs-lookup"><span data-stu-id="6e476-180">On the new **Permissions** tab of your browser, click **Access Request Settings**.</span></span>
    
4. <span data-ttu-id="6e476-181">En el cuadro de diálogo **configuración de solicitudes de acceso** , desactive **permitir a un miembro compartir el sitio y archivos y carpetas individuales** y **permitir solicitudes de acceso** (de modo que las tres casillas estén desactivadas) y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="6e476-181">In the **Access Requests Settings** dialog box, clear **Allow member to share the site and individual files and folders** and **Allow access requests** (so that all three check boxes are cleared), and then click **OK**.</span></span>
    
5. <span data-ttu-id="6e476-182">En la pestaña **permisos** del explorador, haga clic \*\* \<en miembros del name> del sitio\*\* de la lista.</span><span class="sxs-lookup"><span data-stu-id="6e476-182">On the **Permissions** tab of your browser, click **\<site name> Members** in the list.</span></span>
    
6. <span data-ttu-id="6e476-183">En **Personas y grupos**, haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="6e476-183">In **People and Groups**, click **New**.</span></span>
    
7. <span data-ttu-id="6e476-184">En el cuadro de diálogo **compartir** , escriba el nombre del grupo de acceso de los miembros del sitio, selecciónelo y, a continuación, haga clic en **compartir**.</span><span class="sxs-lookup"><span data-stu-id="6e476-184">In the **Share** dialog box, type the name of the site members access group, select it, and then click **Share**.</span></span>
    
8. <span data-ttu-id="6e476-185">Haga clic en el botón Volver del explorador.</span><span class="sxs-lookup"><span data-stu-id="6e476-185">Click the back button on your browser.</span></span>
    
9. <span data-ttu-id="6e476-186">Haga \*\* \<\*\* clic en propietarios de name> de sitio en la lista.</span><span class="sxs-lookup"><span data-stu-id="6e476-186">Click **\<site name> Owners** in the list.</span></span>
    
10. <span data-ttu-id="6e476-187">En **Personas y grupos**, haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="6e476-187">In **People and Groups**, click **New**.</span></span>
    
11. <span data-ttu-id="6e476-188">En el cuadro de diálogo **compartir** , escriba el nombre del grupo de acceso de administradores del sitio, selecciónelo y, a continuación, haga clic en **compartir**.</span><span class="sxs-lookup"><span data-stu-id="6e476-188">In the **Share** dialog box, type the name of the site admins access group, select it, and then click **Share**.</span></span>
    
12. <span data-ttu-id="6e476-189">Haga clic en el botón Volver del explorador.</span><span class="sxs-lookup"><span data-stu-id="6e476-189">Click the back button on your browser.</span></span>
    
13. <span data-ttu-id="6e476-190">Haga clic \*\* \<en el sitio name> visitantes\*\* de la lista.</span><span class="sxs-lookup"><span data-stu-id="6e476-190">Click **\<site name> Visitors** in the list.</span></span>
    
14. <span data-ttu-id="6e476-191">En **Personas y grupos**, haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="6e476-191">In **People and Groups**, click **New**.</span></span>
    
15. <span data-ttu-id="6e476-192">En el cuadro de diálogo **compartir** , escriba el nombre del grupo de acceso de visores del sitio, selecciónelo y, a continuación, haga clic en **compartir**.</span><span class="sxs-lookup"><span data-stu-id="6e476-192">In the **Share** dialog box, type the name of the site viewers access group, select it, and then click **Share**.</span></span>
    
16. <span data-ttu-id="6e476-193">Cierre la pestaña **Permisos** del explorador.</span><span class="sxs-lookup"><span data-stu-id="6e476-193">Close the **Permissions** tab of your browser.</span></span>
    
<span data-ttu-id="6e476-194">Los resultados de esta configuración de permisos son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="6e476-194">The results of these permission settings are:</span></span>
  
- <span data-ttu-id="6e476-195">El \*\* \<\*\* grupo de SharePoint propietarios de name> de sitios contiene el grupo de acceso de administradores del sitio, en el que todos los miembros tienen el nivel de permisos **control total** .</span><span class="sxs-lookup"><span data-stu-id="6e476-195">The **\<site name> Owners** SharePoint group contains the site admins access group, in which all the members have the **Full control** permission level.</span></span>
    
- <span data-ttu-id="6e476-196">El \*\* \<grupo de name> miembros del sitio\*\* de SharePoint contiene el grupo de acceso de miembros del sitio, en el que todos los miembros tienen el nivel de permisos **Editar** .</span><span class="sxs-lookup"><span data-stu-id="6e476-196">The **\<site name> Members** SharePoint group contains the site members access group, in which all the members have the **Edit** permission level.</span></span>
    
- <span data-ttu-id="6e476-197">El \*\* \<\*\* grupo de SharePoint name> visitantes del sitio contiene el grupo de acceso de visores del sitio, en el que todos los miembros tienen el nivel de permisos de **lectura** .</span><span class="sxs-lookup"><span data-stu-id="6e476-197">The **\<site name> Visitors** SharePoint group contains the site viewers access group, in which all the members have the **Read** permission level.</span></span>
    
- <span data-ttu-id="6e476-198">La capacidad de los miembros para invitar a otros miembros o para que los usuarios no miembros soliciten el acceso está deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="6e476-198">The ability for members to invite other members or for non-members to request access is disabled.</span></span>
    
<span data-ttu-id="6e476-199">Esta es la configuración resultante con los tres grupos de SharePoint para el sitio configurado para usar los tres grupos de acceso, que se rellenan con cuentas de usuario o grupos de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="6e476-199">Here is your resulting configuration with the three SharePoint groups for the site configured to use the three access groups, which are populated with user accounts or Azure AD groups.</span></span>
  
![La configuración final del sitio de SharePoint Online aislado con grupos de acceso y cuentas de usuario.](media/e7618971-06ab-447b-90ff-d8be3790fe63.png)
  
<span data-ttu-id="6e476-201">Usted y los miembros del sitio, a través de la pertenencia a grupos en uno de los grupos de acceso, ahora pueden colaborar con los recursos del sitio.</span><span class="sxs-lookup"><span data-stu-id="6e476-201">You and the members of the site, through group membership in one of the access groups, can now collaborate using the resources of the site.</span></span>
  
## <a name="next-step"></a><span data-ttu-id="6e476-202">Siguiente paso</span><span class="sxs-lookup"><span data-stu-id="6e476-202">Next step</span></span>

<span data-ttu-id="6e476-203">Cuando necesite cambiar la pertenencia al grupo de acceso al sitio o crear una carpeta de documentos con permisos personalizados, vea [administrar un sitio de grupo de SharePoint Online aislado](manage-an-isolated-sharepoint-online-team-site.md).</span><span class="sxs-lookup"><span data-stu-id="6e476-203">When you need to change site access group membership or create a document folder with custom permissions, see [Manage an isolated SharePoint Online team site](manage-an-isolated-sharepoint-online-team-site.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="6e476-204">Vea también</span><span class="sxs-lookup"><span data-stu-id="6e476-204">See Also</span></span>

[<span data-ttu-id="6e476-205">Sitios de grupo de SharePoint Online aislados</span><span class="sxs-lookup"><span data-stu-id="6e476-205">Isolated SharePoint Online team sites</span></span>](isolated-sharepoint-online-team-sites.md)
  
[<span data-ttu-id="6e476-206">Diseñar un sitio de grupo de SharePoint Online aislado</span><span class="sxs-lookup"><span data-stu-id="6e476-206">Design an isolated SharePoint Online team site</span></span>](design-an-isolated-sharepoint-online-team-site.md)
  
[<span data-ttu-id="6e476-207">Administrar un sitio de grupo de SharePoint Online aislado</span><span class="sxs-lookup"><span data-stu-id="6e476-207">Manage an isolated SharePoint Online team site</span></span>](manage-an-isolated-sharepoint-online-team-site.md)
  



