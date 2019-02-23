---
title: Configurar grupos y usuarios en un entorno de desarrollo y prueba de campaña política
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/15/2017
ms.audience: ITPro
ms.topic: article
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 0e22bcf3-bad3-42a4-b44f-276e0cf4790f
description: 'Resumen: Cree suscripciones de evaluación de Office 365 y Enterprise Mobility + Security (EMS) que incluyan usuarios y grupos en un entorno de desarrollo y prueba para una campaña política.'
ms.openlocfilehash: 098ae2c3005e0c6ba7939c52260b1a2c49dc557e
ms.sourcegitcommit: a80bd8626720fabdf592b84e4424cd3a83d08280
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/23/2019
ms.locfileid: "30223709"
---
# <a name="configure-groups-and-users-for-a-political-campaign-devtest-environment"></a><span data-ttu-id="21b60-103">Configurar grupos y usuarios en un entorno de desarrollo y prueba de campaña política</span><span class="sxs-lookup"><span data-stu-id="21b60-103">Configure groups and users for a political campaign dev/test environment</span></span>

 <span data-ttu-id="21b60-104">**Resumen:** Cree suscripciones de evaluación de Office 365 y Enterprise Mobility + Security (EMS) que incluyan usuarios y grupos en un entorno de desarrollo y prueba para una campaña política.</span><span class="sxs-lookup"><span data-stu-id="21b60-104">**Summary:** Create Office 365 and Enterprise Mobility + Security (EMS) trial subscriptions with users and groups for a political campaign dev/test environment.</span></span>
  
<span data-ttu-id="21b60-105">Siga las instrucciones de este artículo para crear un entorno de desarrollo y prueba que incluya cuentas de usuario simplificadas y grupos para la solución de [Instrucciones de seguridad de Microsoft para campañas políticas, organizaciones sin ánimo de lucro y otras organizaciones ágiles](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md).</span><span class="sxs-lookup"><span data-stu-id="21b60-105">Use the instructions in this article to create a dev/test environment that includes simplified user accounts and groups for the [Microsoft Security Guidance for Political Campaigns, Nonprofits, and Other Agile Organizations](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md) solution.</span></span>
  
## <a name="phase-1-create-your-office-365-devtest-environment"></a><span data-ttu-id="21b60-106">Fase 1: Crear el entorno de desarrollo y prueba de Office 365</span><span class="sxs-lookup"><span data-stu-id="21b60-106">Phase 1: Create your Office 365 dev/test environment</span></span>

<span data-ttu-id="21b60-107">En esta fase se obtienen suscripciones de evaluación para Office 365 E5 y Enterprise Mobility + Security (EMS) E5 para una organización ficticia que representa una campaña política.</span><span class="sxs-lookup"><span data-stu-id="21b60-107">In this phase, you obtain trial subscriptions for Office 365 E5 and Enterprise Mobility + Security (EMS) E5 for a fictional organization that represents a political campaign.</span></span>
  
<span data-ttu-id="21b60-108">Siga primero las instrucciones de la **fase 2** del [entorno de desarrollo y prueba de Office 365](https://docs.microsoft.com/office365/enterprise/office-365-dev-test-environment).</span><span class="sxs-lookup"><span data-stu-id="21b60-108">First, follow the instructions in **Phase 2** of the [Office 365 dev/test environment](https://docs.microsoft.com/office365/enterprise/office-365-dev-test-environment).</span></span>
  
<span data-ttu-id="21b60-109">Después, inscríbase en la suscripción de evaluación de EMS E5 y la agregará a la misma organización de la suscripción de evaluación de Office 365.</span><span class="sxs-lookup"><span data-stu-id="21b60-109">Next, sign up for the EMS E5 trial subscription and add it to the same organization as your Office 365 trial subscription.</span></span>
  
1. <span data-ttu-id="21b60-p101">Si es necesario, inicie sesión en el portal de Office 365 con las credenciales de la cuenta de administrador global de la suscripción de evaluación. Para obtener ayuda, vea [Where to sign in to Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4) (Dónde iniciar sesión en Office 365).</span><span class="sxs-lookup"><span data-stu-id="21b60-p101">If needed, sign in to the Office 365 portal with the credentials of the global administrator account of your trial subscription. For help, see [Where to sign in to Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>
    
2. <span data-ttu-id="21b60-112">Haga clic en el icono **Administrador**.</span><span class="sxs-lookup"><span data-stu-id="21b60-112">Click the **Admin** tile.</span></span>
    
3. <span data-ttu-id="21b60-113">En la pestaña **Centro de administración de Office** del explorador, en el panel de navegación izquierdo, haga clic en **Facturación > Servicios de compra**.</span><span class="sxs-lookup"><span data-stu-id="21b60-113">On the **Office Admin center** tab in your browser, in the left navigation, click **Billing > Purchase services**.</span></span>
    
4. <span data-ttu-id="21b60-p102">En la página **Servicios de compra**, busque el elemento **Enterprise Mobility + Security E5**. Mantenga el puntero del mouse sobre ese elemento y haga clic en **Iniciar prueba gratuita**.</span><span class="sxs-lookup"><span data-stu-id="21b60-p102">On the **Purchase services** page, find the **Enterprise Mobility + Security E5** item. Hover your mouse pointer over it and click **Start free trial**.</span></span>
    
5. <span data-ttu-id="21b60-116">En la página **Confirmar pedido**, haga clic en **Probar ahora**.</span><span class="sxs-lookup"><span data-stu-id="21b60-116">On the **Confirm your order** page, click **Try now**.</span></span>
    
6. <span data-ttu-id="21b60-117">En la página **Recibo del pedido**, haga clic en **Continuar**.</span><span class="sxs-lookup"><span data-stu-id="21b60-117">On the **Order receipt** page, click **Continue**.</span></span>
    
<span data-ttu-id="21b60-118">Después, habilite la licencia de EMS E5 para la cuenta de administrador global.</span><span class="sxs-lookup"><span data-stu-id="21b60-118">Next, enable the EMS E5 license for your global administrator account.</span></span>
  
1. <span data-ttu-id="21b60-119">En el panel de navegación izquierdo de la pestaña **Centro de administración de Office 365** del explorador, haga clic en **Usuarios > Usuarios activos**.</span><span class="sxs-lookup"><span data-stu-id="21b60-119">On the **Office 365 Admin center** tab in your browser, in the left navigation, click **Users > Active users**.</span></span>
    
2. <span data-ttu-id="21b60-120">Haga clic en la cuenta de administrador global y, después, en **Editar** para **Licencias de productos**.</span><span class="sxs-lookup"><span data-stu-id="21b60-120">Click your global administrator account, and then click **Edit** for **Product licenses**.</span></span>
    
3. <span data-ttu-id="21b60-121">En el panel **Licencias de productos**, cambie la licencia del producto de **Enterprise Mobility + Security E5** a **Activada**, seleccione **Guardar** y, después, haga clic en **Cerrar** dos veces.</span><span class="sxs-lookup"><span data-stu-id="21b60-121">On the **Product licenses** pane, turn the product license for **Enterprise Mobility + Security E5** to **On**, click **Save,** and then click **Close** twice.</span></span>
    
## <a name="phase-2-create-and-configure-your-azure-active-directory-ad-groups"></a><span data-ttu-id="21b60-122">Fase 2: Crear y configurar los grupos de Azure Active Directory (AD)</span><span class="sxs-lookup"><span data-stu-id="21b60-122">Phase 2: Create and configure your Azure Active Directory (AD) groups</span></span>

<span data-ttu-id="21b60-123">En esta fase se crean y configuran los grupos de Azure AD para la campaña.</span><span class="sxs-lookup"><span data-stu-id="21b60-123">In this phase, you create and configure the Azure AD groups for your campaign.</span></span>
  
<span data-ttu-id="21b60-124">En primer lugar, cree un conjunto de grupos para una campaña política típica en Azure Portal.</span><span class="sxs-lookup"><span data-stu-id="21b60-124">First, create a set of groups for a typical political campaign with the Azure portal.</span></span>
  
1. <span data-ttu-id="21b60-p103">En una pestaña independiente en el explorador, vaya a Azure Portal en [https://portal.azure.com](https://portal.azure.com). Si es necesario, inicie sesión con las credenciales de la cuenta de administrador global de la suscripción de evaluación de Office 365 E5.</span><span class="sxs-lookup"><span data-stu-id="21b60-p103">On a separate tab in your browser, go to the Azure portal at [https://portal.azure.com](https://portal.azure.com). If needed, sign in with the credentials of the global administrator account for your Office 365 E5 trial subscription.</span></span>
    
2. <span data-ttu-id="21b60-127">En Azure Portal, haga clic en **Azure Active Directory > Usuarios y grupos > Todos los grupos**.</span><span class="sxs-lookup"><span data-stu-id="21b60-127">In the Azure portal, click **Azure Active Directory > Users and groups > All groups**.</span></span>
    
3. <span data-ttu-id="21b60-128">Siga estos pasos para cada nombre de grupo de la lista:</span><span class="sxs-lookup"><span data-stu-id="21b60-128">Do the following steps for each group name in this list:</span></span>
    
  - <span data-ttu-id="21b60-129">Personal directivo y estratégico</span><span class="sxs-lookup"><span data-stu-id="21b60-129">Senior and strategic staff</span></span>
    
  - <span data-ttu-id="21b60-130">Personal de TI</span><span class="sxs-lookup"><span data-stu-id="21b60-130">IT staff</span></span>
    
  - <span data-ttu-id="21b60-131">Personal de Análisis</span><span class="sxs-lookup"><span data-stu-id="21b60-131">Analytics staff</span></span>
    
  - <span data-ttu-id="21b60-132">Personal básico de plantilla</span><span class="sxs-lookup"><span data-stu-id="21b60-132">Regular core staff</span></span>
    
  - <span data-ttu-id="21b60-133">Personal de Operaciones</span><span class="sxs-lookup"><span data-stu-id="21b60-133">Operations staff</span></span>
    
  - <span data-ttu-id="21b60-134">Personal de campo</span><span class="sxs-lookup"><span data-stu-id="21b60-134">Field staff</span></span>
    
1. <span data-ttu-id="21b60-135">En la hoja **Todos los grupos**, haga clic en **+ Nuevo grupo**.</span><span class="sxs-lookup"><span data-stu-id="21b60-135">On the **All groups** blade, click **+ New group**.</span></span>
    
2. <span data-ttu-id="21b60-136">Escriba el nombre del grupo de la lista en **Nombre**.</span><span class="sxs-lookup"><span data-stu-id="21b60-136">Type the group name from the list in **Name**.</span></span>
    
3. <span data-ttu-id="21b60-137">Seleccione **Usuario dinámico** en **Pertenencia**.</span><span class="sxs-lookup"><span data-stu-id="21b60-137">Select **Dynamic user** in **Membership**.</span></span>
    
4. <span data-ttu-id="21b60-138">Haga clic en **Sí** en **¿Quiere habilitar las características de Office?**</span><span class="sxs-lookup"><span data-stu-id="21b60-138">Click **Yes** for **Enable Office features**.</span></span>
    
5. <span data-ttu-id="21b60-139">Haga clic en **Agregar una consulta dinámica**.</span><span class="sxs-lookup"><span data-stu-id="21b60-139">Click **Add dynamic query**.</span></span>
    
6. <span data-ttu-id="21b60-140">En **Add users where** (Agregar usuarios donde), seleccione **departamento**.</span><span class="sxs-lookup"><span data-stu-id="21b60-140">In **Add users where**, select **department**.</span></span>
    
7. <span data-ttu-id="21b60-141">En el siguiente campo, seleccione **Es igual a**.</span><span class="sxs-lookup"><span data-stu-id="21b60-141">In the next field, select **Equals**.</span></span>
    
8. <span data-ttu-id="21b60-142">En el siguiente campo, escriba el nombre del grupo de la lista.</span><span class="sxs-lookup"><span data-stu-id="21b60-142">In the next field, type the group name from the list.</span></span>
    
9. <span data-ttu-id="21b60-143">Haga clic en **Agregar consulta** luego en **Crear**.</span><span class="sxs-lookup"><span data-stu-id="21b60-143">Click **Add query**, and then click **Create**.</span></span>
    
10. <span data-ttu-id="21b60-144">Haga clic en **Users and groups - All groups** (Usuarios y grupos - Todos los grupos).</span><span class="sxs-lookup"><span data-stu-id="21b60-144">Click **Users and groups - All groups**.</span></span>
    
<span data-ttu-id="21b60-145">Después, configure los grupos para que a los miembros se les asignen automáticamente licencias de Office 365 E5 y EMS E5.</span><span class="sxs-lookup"><span data-stu-id="21b60-145">Next, you configure the groups so that members are automatically assigned Office 365 E5 and EMS E5 licenses.</span></span>
  
1. <span data-ttu-id="21b60-146">En Azure Portal, haga clic en **Azure Active Directory > Licencias > Todos los productos**.</span><span class="sxs-lookup"><span data-stu-id="21b60-146">In the Azure portal, click **Azure Active Directory > Licenses > All products**.</span></span>
    
2. <span data-ttu-id="21b60-147">En la lista, seleccione **Enterprise Mobility + Security E5** y **Office 365 Enterprise E5** y haga clic en **+ Asignar**.</span><span class="sxs-lookup"><span data-stu-id="21b60-147">In the list, select **Enterprise Mobility + Security E5** and **Office 365 Enterprise E5**, and then click **+ Assign**.</span></span>
    
3. <span data-ttu-id="21b60-148">En la hoja **Asignar licencia**, haga clic en **Usuarios y grupos**.</span><span class="sxs-lookup"><span data-stu-id="21b60-148">In the **Assign license** blade, click **Users and groups**.</span></span>
    
4. <span data-ttu-id="21b60-149">En la lista de grupos, seleccione los siguientes:</span><span class="sxs-lookup"><span data-stu-id="21b60-149">In the list of groups, select the following:</span></span>
    
  - <span data-ttu-id="21b60-150">Personal de Análisis</span><span class="sxs-lookup"><span data-stu-id="21b60-150">Analytics staff</span></span>
    
  - <span data-ttu-id="21b60-151">Personal de campo</span><span class="sxs-lookup"><span data-stu-id="21b60-151">Field staff</span></span>
    
  - <span data-ttu-id="21b60-152">Personal de TI</span><span class="sxs-lookup"><span data-stu-id="21b60-152">IT staff</span></span>
    
  - <span data-ttu-id="21b60-153">Personal de Operaciones</span><span class="sxs-lookup"><span data-stu-id="21b60-153">Operations staff</span></span>
    
  - <span data-ttu-id="21b60-154">Personal básico de plantilla</span><span class="sxs-lookup"><span data-stu-id="21b60-154">Regular core staff</span></span>
    
  - <span data-ttu-id="21b60-155">Personal directivo y estratégico</span><span class="sxs-lookup"><span data-stu-id="21b60-155">Senior and strategic staff</span></span>
    
5. <span data-ttu-id="21b60-156">Haga clic en **Seleccionar** y luego en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="21b60-156">Click **Select**, and then click **Assign**.</span></span>
    
6. <span data-ttu-id="21b60-157">Cierre la pestaña Azure Portal del explorador.</span><span class="sxs-lookup"><span data-stu-id="21b60-157">Close the Azure portal tab in your browser.</span></span>
    
## <a name="phase-3-add-your-user-accounts"></a><span data-ttu-id="21b60-158">Fase 3: Agregar las cuentas de usuario</span><span class="sxs-lookup"><span data-stu-id="21b60-158">Phase 3: Add your user accounts</span></span>

<span data-ttu-id="21b60-159">En esta fase se agregan las cuentas de usuario de ejemplo para la campaña política.</span><span class="sxs-lookup"><span data-stu-id="21b60-159">In this phase, you add the example user accounts for your political campaign.</span></span>
  
<span data-ttu-id="21b60-160">En primer lugar, debe [conectarse al módulo PowerShell de Azure Active Directory V2](https://go.microsoft.com/fwlink/?linkid=842218).</span><span class="sxs-lookup"><span data-stu-id="21b60-160">First, you [Connect with the Azure Active Directory V2 PowerShell module](https://go.microsoft.com/fwlink/?linkid=842218).</span></span>
  
<span data-ttu-id="21b60-161">Después, rellene el nombre de la organización, su ubicación y una contraseña común y, luego, ejecute estos comandos en el entorno de script integrado (ISE) o el símbolo del sistema de PowerShell:</span><span class="sxs-lookup"><span data-stu-id="21b60-161">Next, you fill in your organization name, your location, and a common password, and then run these commands from the PowerShell command prompt or Integrated Script Environment (ISE):</span></span>
  
```
$orgName="<organization name, such as contoso for the contoso.onmicrosoft.com trial subscription domain name>"
$location="<the ISO ALPHA2 country code, such as US for the United States>"
$commonPassword="<common password for all the new accounts>"

$PasswordProfile=New-Object -TypeName Microsoft.Open.AzureAD.Model.PasswordProfile
$PasswordProfile.Password=$commonPassword

$deptName="Senior and strategic staff"
$userNames=@("Candidate","ChiefOfStaff","Strategic1") 
foreach ($element in $userNames){ New-AzureADUser -DisplayName $element -PasswordProfile $PasswordProfile -UserPrincipalName ($element + "@" + $orgName + ".onmicrosoft.com") -AccountEnabled $true -MailNickName $element -Department $deptName -UsageLocation $location }
$deptName="IT staff"
$userNames=@("ITAdmin1","ITAdmin2") 
foreach ($element in $userNames){ New-AzureADUser -DisplayName $element -PasswordProfile $PasswordProfile -UserPrincipalName ($element + "@" + $orgName + ".onmicrosoft.com") -AccountEnabled $true -MailNickName $element -Department $deptName -UsageLocation $location }
$deptName="Analytics staff"
$userNames=@("DataScientist1") 
foreach ($element in $userNames){ New-AzureADUser -DisplayName $element -PasswordProfile $PasswordProfile -UserPrincipalName ($element + "@" + $orgName + ".onmicrosoft.com") -AccountEnabled $true -MailNickName $element -Department $deptName -UsageLocation $location }
$deptName="Regular core staff"
$userNames=@("Regular1","Regular2") 
foreach ($element in $userNames){ New-AzureADUser -DisplayName $element -PasswordProfile $PasswordProfile -UserPrincipalName ($element + "@" + $orgName + ".onmicrosoft.com") -AccountEnabled $true -MailNickName $element -Department $deptName -UsageLocation $location }
$deptName="Operations staff"
$userNames=@("Operations1") 
foreach ($element in $userNames){ New-AzureADUser -DisplayName $element -PasswordProfile $PasswordProfile -UserPrincipalName ($element + "@" + $orgName + ".onmicrosoft.com") -AccountEnabled $true -MailNickName $element -Department $deptName -UsageLocation $location }
$deptName="Field staff"
$userNames=@("FieldConsultant1") 
foreach ($element in $userNames){ New-AzureADUser -DisplayName $element -PasswordProfile $PasswordProfile -UserPrincipalName ($element + "@" + $orgName + ".onmicrosoft.com") -AccountEnabled $true -MailNickName $element -Department $deptName -UsageLocation $location }

```

> [!IMPORTANT]
> <span data-ttu-id="21b60-p104">Se usa una contraseña común para automatizar y facilitar la configuración de un entorno de desarrollo y prueba. Nos se recomienda hacerlo con suscripciones de producción. Cuando inicie sesión con cada una de estas nuevas cuentas de usuario, se le pedirá que cambie la contraseña.</span><span class="sxs-lookup"><span data-stu-id="21b60-p104">The use of a common password here is for automation and ease of configuration for a dev/test environment. This is not recommended for production subscriptions. As you sign in with each of these new user accounts, you will be prompted to change the password.</span></span> 
  
<span data-ttu-id="21b60-165">Siga estos pasos para comprobar que las licencias basadas en grupos y la pertenencia dinámica a grupos funcionan correctamente.</span><span class="sxs-lookup"><span data-stu-id="21b60-165">Use these steps to verify that dynamic group membership and group-based licensing are working correctly.</span></span>
  
1. <span data-ttu-id="21b60-166">En la pestaña **Inicio de Microsoft Office** del explorador, haga clic en el icono **Administrador**.</span><span class="sxs-lookup"><span data-stu-id="21b60-166">From the **Microsoft Office Home** tab of your browser, click the **Admin** tile.</span></span>
    
2. <span data-ttu-id="21b60-167">En la nueva pestaña **Centro de administración de Office** del explorador, haga clic en **Usuarios**.</span><span class="sxs-lookup"><span data-stu-id="21b60-167">From the new **Office Admin center** tab of your browser, click **Users**.</span></span>
    
3. <span data-ttu-id="21b60-168">En la lista de usuarios, haga clic en **Candidato**.</span><span class="sxs-lookup"><span data-stu-id="21b60-168">In the list of users, click **Candidate**.</span></span>
    
4. <span data-ttu-id="21b60-169">En el panel que muestra las propiedades de la cuenta de usuario **Candidato**, compruebe que:</span><span class="sxs-lookup"><span data-stu-id="21b60-169">In the pane that lists the properties of the **Candidate** user account, verify that:</span></span>
    
  - <span data-ttu-id="21b60-170">Es un miembro del grupo **Personal directivo y estratégico** (en **Pertenencia a grupos**).</span><span class="sxs-lookup"><span data-stu-id="21b60-170">It is a member of the **Senior and strategic staff** group (in **Group memberships**).</span></span>
    
  - <span data-ttu-id="21b60-171">Se le han asignado las licencias de **Enterprise Mobility + Security E5** y **Office 365 Enterprise E5** (en **Licencias de productos**).</span><span class="sxs-lookup"><span data-stu-id="21b60-171">It has been assigned the **Enterprise Mobility + Security E5** and **Office 365 Enterprise E5** licenses (in **Product licenses**).</span></span>
    
5. <span data-ttu-id="21b60-172">Cierre el panel de la cuenta de usuario **Candidato**.</span><span class="sxs-lookup"><span data-stu-id="21b60-172">Close the **Candidate** user account pane.</span></span>
    
## <a name="record-values-for-future-reference"></a><span data-ttu-id="21b60-173">Registrar valores para referencia futura</span><span class="sxs-lookup"><span data-stu-id="21b60-173">Record values for future reference</span></span>

<span data-ttu-id="21b60-174">Registre estos valores para trabajar con las suscripciones de prueba de Office 365 y EMS en este entorno de desarrollo y pruebas:</span><span class="sxs-lookup"><span data-stu-id="21b60-174">Record these values for working with the Office 365 and EMS trial subscriptions for this dev/test environment:</span></span>
  
- <span data-ttu-id="21b60-175">Nombre de la organización de la suscripción de prueba: ![](./media/Common-Images/TableLine.png)</span><span class="sxs-lookup"><span data-stu-id="21b60-175">Your trial subscription organization name: ![](./media/Common-Images/TableLine.png)</span></span> 
    
    <span data-ttu-id="21b60-176">Por ejemplo, en el nombre de dominio de la suscripción de prueba de contoso.onmicrosoft.com, el nombre de la organización es “contoso”.</span><span class="sxs-lookup"><span data-stu-id="21b60-176">For example, for the trial subscription domain name of contoso.onmicrosoft.com, the organization name is "contoso".</span></span>
    
- <span data-ttu-id="21b60-177">Nombre del administrador global de Office 365: ![](./media/Common-Images/TableLine.png).onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="21b60-177">The Office 365 global administrator name: ![](./media/Common-Images/TableLine.png).onmicrosoft.com</span></span>
    
    <span data-ttu-id="21b60-178">Registre la contraseña de esta cuenta y la contraseña inicial común de las demás cuentas de usuario en una ubicación segura.</span><span class="sxs-lookup"><span data-stu-id="21b60-178">Record the password for this account and the common initial password for the other user accounts in a secure location.</span></span>
    
## <a name="next-step"></a><span data-ttu-id="21b60-179">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="21b60-179">Next step</span></span>

<span data-ttu-id="21b60-180">Cree los cuatro tipos distintos de sitios de grupo de SharePoint Online en este entorno de desarrollo y pruebas con [Crear sitios de grupo en un entorno de desarrollo y prueba de campaña política](create-team-sites-in-a-political-campaign-dev-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="21b60-180">Build the four different types of SharePoint Online team sites in this dev/test environment with [Create team sites in a political campaign dev/test environment](create-team-sites-in-a-political-campaign-dev-test-environment.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="21b60-181">Vea también</span><span class="sxs-lookup"><span data-stu-id="21b60-181">See also</span></span>

[<span data-ttu-id="21b60-182">Guía de seguridad de Microsoft para campañas políticas, ONG y otras organizaciones ágiles</span><span class="sxs-lookup"><span data-stu-id="21b60-182">Microsoft Security Guidance for Political Campaigns, Nonprofits, and Other Agile Organizations</span></span>](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md)
  
[<span data-ttu-id="21b60-183">Crear sitios de grupo en un entorno de desarrollo y prueba de campaña política</span><span class="sxs-lookup"><span data-stu-id="21b60-183">Create team sites in a political campaign dev/test environment</span></span>](create-team-sites-in-a-political-campaign-dev-test-environment.md)
  
[<span data-ttu-id="21b60-184">Guías del entorno de pruebas de adopción de la nube (TLG)</span><span class="sxs-lookup"><span data-stu-id="21b60-184">Cloud adoption Test Lab Guides (TLGs)</span></span>](https://docs.microsoft.com/office365/enterprise/cloud-adoption-test-lab-guides-tlgs)
  
[<span data-ttu-id="21b60-185">Adopción de la nube y soluciones híbridas</span><span class="sxs-lookup"><span data-stu-id="21b60-185">Cloud adoption and hybrid solutions</span></span>](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)




