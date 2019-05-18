---
title: Crear sitios de grupo en un entorno de desarrollo y prueba de campaña política
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 05/21/2018
audience: ITPro
ms.topic: article
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.custom: ''
ms.assetid: c2112ce8-1c4b-424f-b200-59e161db2d21
description: 'Resumen: Cree sitios de grupo de SharePoint Online públicos, privados, confidenciales o extremadamente confidenciales en el entorno de desarrollo y prueba de una campaña política.'
ms.openlocfilehash: 3e0a79a0e521ab193685511cef59bcfa3fa68896
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/17/2019
ms.locfileid: "34151162"
---
# <a name="create-team-sites-in-a-political-campaign-devtest-environment"></a><span data-ttu-id="5e7c8-103">Crear sitios de grupo en un entorno de desarrollo y prueba de campaña política</span><span class="sxs-lookup"><span data-stu-id="5e7c8-103">Create team sites in a political campaign dev/test environment</span></span>

 <span data-ttu-id="5e7c8-104">**Resumen:** Cree sitios de grupo de SharePoint Online públicos, privados, confidenciales o extremadamente confidenciales en un entorno de desarrollo y prueba para una campaña política.</span><span class="sxs-lookup"><span data-stu-id="5e7c8-104">**Summary:** Create public, private, sensitive, and highly confidential SharePoint Online team sites in your political campaign dev/test environment.</span></span> 
  
<span data-ttu-id="5e7c8-p101">Siga las instrucciones de este artículo para crear un entorno de desarrollo y prueba que incluya los cuatro tipos distintos de sitios de grupo de SharePoint Online para la solución de [Instrucciones de seguridad de Microsoft para campañas políticas, organizaciones sin ánimo de lucro y otras organizaciones ágiles](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md). Estos sitios se describen en detalle en el tema 10, titulado **SharePoint y OneDrive para la Empresa**.</span><span class="sxs-lookup"><span data-stu-id="5e7c8-p101">Use the instructions in this article to create a dev/test environment that includes the four different types of SharePoint Online team sites for the [Microsoft Security Guidance for Political Campaigns, Nonprofits, and Other Agile Organizations](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md) solution. These sites are described in detail on Topic 10, titled **SharePoint and OneDrive for Business**.</span></span>
  
## <a name="phase-1-create-your-political-campaign-devtest-environment"></a><span data-ttu-id="5e7c8-107">Fase 1: Crear un entorno de desarrollo y prueba de campaña política</span><span class="sxs-lookup"><span data-stu-id="5e7c8-107">Phase 1: Create your political campaign dev/test environment</span></span>

<span data-ttu-id="5e7c8-108">En primer lugar, siga las instrucciones de [Configurar grupos y usuarios en un entorno de desarrollo y prueba de campaña política](configure-groups-and-users-for-a-political-campaign-dev-test-environment.md) para crear las suscripciones, los usuarios y los grupos.</span><span class="sxs-lookup"><span data-stu-id="5e7c8-108">First, follow the instructions in [Configure groups and users for a political campaign dev/test environment](configure-groups-and-users-for-a-political-campaign-dev-test-environment.md) to create your subscriptions, users, and groups.</span></span>
  
## <a name="phase-2-create-office-365-labels"></a><span data-ttu-id="5e7c8-109">Fase 2: Crear etiquetas de Office 365</span><span class="sxs-lookup"><span data-stu-id="5e7c8-109">Phase 2: Create Office 365 labels</span></span>

<span data-ttu-id="5e7c8-110">En esta fase se crean las etiquetas para los diferentes niveles de seguridad de las carpetas de documentos de sitios de grupo de SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="5e7c8-110">In this phase, you create the labels for the different levels of security for SharePoint Online team site document folders.</span></span>
  
1. <span data-ttu-id="5e7c8-111">Si es necesario, inicie sesión en el centro de administración con las credenciales de la cuenta de administrador global de la suscripción de evaluación.</span><span class="sxs-lookup"><span data-stu-id="5e7c8-111">If needed, sign in to the admin center with the credentials of the global administrator account of your trial subscription.</span></span> <span data-ttu-id="5e7c8-112">Para obtener ayuda, vea [Dónde iniciar sesión en Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4).</span><span class="sxs-lookup"><span data-stu-id="5e7c8-112">For help, see [Where to sign in to Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>
    
2. <span data-ttu-id="5e7c8-113">En la pestaña **Inicio de Microsoft Office**, haga clic en el icono **Administrador**.</span><span class="sxs-lookup"><span data-stu-id="5e7c8-113">From the **Microsoft Office Home** tab, click the **Admin** tile.</span></span>
    
3. <span data-ttu-id="5e7c8-114">En la nueva pestaña **Centro de administración de Office** del explorador, haga clic en **Centros de administración Seguridad &amp; Cumplimiento**.</span><span class="sxs-lookup"><span data-stu-id="5e7c8-114">From the new **Office Admin center** tab of your browser, click **Admin centers > Security &amp; Compliance**.</span></span>
    
4. <span data-ttu-id="5e7c8-115">En la nueva pestaña **Inicio - Seguridad y cumplimiento** del explorador, haga clic en **Clasificaciones > Etiquetas**.</span><span class="sxs-lookup"><span data-stu-id="5e7c8-115">From the new **Home - Security &amp; Compliance** tab of your browser, click **Classifications > Labels**.</span></span>
    
5. <span data-ttu-id="5e7c8-116">En el panel **Inicio > Etiquetas**, haga clic en **Crear una etiqueta**.</span><span class="sxs-lookup"><span data-stu-id="5e7c8-116">From the **Home > Labels** pane, click **Create a label**.</span></span>
    
6. <span data-ttu-id="5e7c8-117">En el panel **Asignar un nombre a la etiqueta**, escriba **Interna** y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="5e7c8-117">On the **Name your label** pane, type **Internal**, and then click **Next**.</span></span>
    
7. <span data-ttu-id="5e7c8-118">En el panel **Configuración de etiquetas**, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="5e7c8-118">On the **Label settings** pane, click **Next**.</span></span>
    
8. <span data-ttu-id="5e7c8-119">En el panel **Revise su configuración**, haga clic en **Crear esta etiqueta** y luego en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="5e7c8-119">On the **Review your settings** pane, click **Create this label**, and then click **Close**.</span></span>
    
9. <span data-ttu-id="5e7c8-120">Repita los pasos del 5 al 8 para estas etiquetas adicionales:</span><span class="sxs-lookup"><span data-stu-id="5e7c8-120">Repeat steps 5-8 for these additional labels:</span></span>
    
  - <span data-ttu-id="5e7c8-121">Private</span><span class="sxs-lookup"><span data-stu-id="5e7c8-121">Private</span></span>
    
  - <span data-ttu-id="5e7c8-122">Confidencial</span><span class="sxs-lookup"><span data-stu-id="5e7c8-122">Sensitive</span></span>
    
  - <span data-ttu-id="5e7c8-123">Extremadamente confidencial</span><span class="sxs-lookup"><span data-stu-id="5e7c8-123">Highly Confidential</span></span>
    
10. <span data-ttu-id="5e7c8-124">En el panel **Inicio > Etiquetas**, haga clic para **Publish labels** (Publicar etiquetas).</span><span class="sxs-lookup"><span data-stu-id="5e7c8-124">From the **Home > Labels** pane, click **Publish labels**.</span></span>
    
11. <span data-ttu-id="5e7c8-125">En el panel **Elegir etiquetas para publicar**, haga clic en **Elegir etiquetas para publicar**.</span><span class="sxs-lookup"><span data-stu-id="5e7c8-125">On the **Choose labels to publish** pane, click **Choose labels to publish**.</span></span>
    
12. <span data-ttu-id="5e7c8-126">En el panel de **elección de etiquetas**, haga clic en **Agregar** y seleccione las cuatro etiquetas.</span><span class="sxs-lookup"><span data-stu-id="5e7c8-126">On the **Choose labels** pane, click **Add** and select all four labels.</span></span>
    
13. <span data-ttu-id="5e7c8-127">Haga clic en **Listo**.</span><span class="sxs-lookup"><span data-stu-id="5e7c8-127">Click **Done**.</span></span>
    
14. <span data-ttu-id="5e7c8-128">En el panel **Elegir etiquetas para publicar**, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="5e7c8-128">On the **Choose labels to publish** pane, click **Next**.</span></span>
    
15. <span data-ttu-id="5e7c8-129">En el panel **Elegir ubicaciones**, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="5e7c8-129">On the **Choose locations** pane, click **Next**.</span></span>
    
16. <span data-ttu-id="5e7c8-130">En el panel **Escriba un nombre para la directiva**, escriba **Campaña** en **Nombre** y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="5e7c8-130">On the **Name your policy** pane, type **Campaign** in **Name**, and then click **Next**.</span></span>
    
17. <span data-ttu-id="5e7c8-131">En el panel **Revise su configuración**, haga clic en **Publicar etiquetas** y luego en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="5e7c8-131">On the **Review your settings** pane, click **Publish labels**, and then click **Close**.</span></span>
    
## <a name="phase-3-create-your-sharepoint-online-team-sites"></a><span data-ttu-id="5e7c8-132">Fase 3: Crear los sitios de grupo de SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="5e7c8-132">Phase 3: Create your SharePoint Online team sites</span></span>

<span data-ttu-id="5e7c8-133">En esta fase se crean y configuran los sitios de grupo de SharePoint Online para la campaña política correspondientes a los cuatro tipos de sitios de grupo de SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="5e7c8-133">In this phase, you create and configure SharePoint Online team sites for your political campaign corresponding to the four types of SharePoint Online team sites.</span></span>
  
### <a name="campaign-wide-team-site"></a><span data-ttu-id="5e7c8-134">Sitio de grupo de toda la campaña</span><span class="sxs-lookup"><span data-stu-id="5e7c8-134">Campaign wide team site</span></span>

<span data-ttu-id="5e7c8-135">Para crear un sitio de grupo público de línea base de SharePoint Online, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="5e7c8-135">To create a baseline public SharePoint Online team site, do the following:</span></span>
  
1. <span data-ttu-id="5e7c8-136">Si es necesario, use un explorador en el equipo local e inicie sesión en el centro de administración ([https://admin.microsoft.com](https://admin.microsoft.com)) con la cuenta de administrador global.</span><span class="sxs-lookup"><span data-stu-id="5e7c8-136">If needed, use a browser on your local computer and sign in to the admin center ([https://admin.microsoft.com](https://admin.microsoft.com)) using your global administrator account.</span></span>
    
2. <span data-ttu-id="5e7c8-137">En la lista de iconos, haga clic en **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="5e7c8-137">In the list of tiles, click **SharePoint**.</span></span>
    
3. <span data-ttu-id="5e7c8-138">En la nueva pestaña **SharePoint** del explorador, haga clic en **+ Crear sitio**.</span><span class="sxs-lookup"><span data-stu-id="5e7c8-138">On the new **SharePoint** tab in your browser, click **+ Create site**.</span></span>
    
4. <span data-ttu-id="5e7c8-139">En la página **Crear un sitio**, haga clic en **Sitio de grupo**.</span><span class="sxs-lookup"><span data-stu-id="5e7c8-139">On the **Create a site** page, click **Team site**.</span></span>
    
5. <span data-ttu-id="5e7c8-140">En **Nombre del sitio**, escriba **Toda la campaña**.</span><span class="sxs-lookup"><span data-stu-id="5e7c8-140">In **Site name**, type **Campaign wide**.</span></span> 
    
6. <span data-ttu-id="5e7c8-141">En **Team site description** (Descripción del sitio de grupo), escriba **Sitio de SharePoint para toda la campaña**.</span><span class="sxs-lookup"><span data-stu-id="5e7c8-141">In **Team site description**, type **SharePoint site for the entire campaign**.</span></span>
    
7. <span data-ttu-id="5e7c8-142">En **Configuración de privacidad**, seleccione **Public – anyone in the organization can access this site** (Público: cualquier usuario de la organización tiene acceso a este sitio) y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="5e7c8-142">In **Privacy settings**, select **Public - anyone in the organization can access this site**, and then click **Next**.</span></span>
    
8. <span data-ttu-id="5e7c8-143">En el panel **Who do you want to add?** (Usuarios que quiere agregar), haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="5e7c8-143">On the **Who do you want to add?** pane, click **Finish**.</span></span>
    
<span data-ttu-id="5e7c8-144">Después, configure la carpeta de documentos del sitio de grupo Toda la campaña con la etiqueta Interna.</span><span class="sxs-lookup"><span data-stu-id="5e7c8-144">Next, configure the documents folder of the Campaign wide team site for the Internal label.</span></span>
  
1. <span data-ttu-id="5e7c8-145">En la pestaña **Toda la campaña-Inicio** del explorador, haga clic en **Documentos**.</span><span class="sxs-lookup"><span data-stu-id="5e7c8-145">In the **Campaign wide-Home** tab of your browser, click **Documents**.</span></span>
    
2. <span data-ttu-id="5e7c8-146">Haga clic en el icono de configuración y luego en **Configuración de biblioteca**.</span><span class="sxs-lookup"><span data-stu-id="5e7c8-146">Click the settings icon, and then click **Library settings**.</span></span>
    
3. <span data-ttu-id="5e7c8-147">En **Permisos y administración**, haga clic en **Apply label to items in this library** (Aplicar la etiqueta a los elementos de esta biblioteca).</span><span class="sxs-lookup"><span data-stu-id="5e7c8-147">Under **Permissions and Management**, click **Apply label to items in this library**.</span></span>
    
4. <span data-ttu-id="5e7c8-148">En **Configuración-Aplicar etiqueta**, seleccione **Interna** y haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="5e7c8-148">In **Settings-Apply Label**, select **Internal**, and then click **Save**.</span></span>
    
### <a name="campaign-project-1-team-site"></a><span data-ttu-id="5e7c8-149">Sitio de grupo del proyecto de campaña 1</span><span class="sxs-lookup"><span data-stu-id="5e7c8-149">Campaign project 1 team site</span></span>

<span data-ttu-id="5e7c8-150">Para crear un sitio de grupo privado de línea base de SharePoint Online para un proyecto dentro de la organización, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="5e7c8-150">To create a baseline private SharePoint Online team site for a project within the campaign, do the following:</span></span>
  
1. <span data-ttu-id="5e7c8-151">Si es necesario, use un explorador en el equipo local e inicie sesión en el centro de administración ([https://admin.microsoft.com](https://admin.microsoft.com)) con la cuenta de administrador global.</span><span class="sxs-lookup"><span data-stu-id="5e7c8-151">If needed, use a browser on your local computer and sign in to the admin center ([https://admin.microsoft.com](https://admin.microsoft.com)) using your global administrator account.</span></span>
    
2. <span data-ttu-id="5e7c8-152">En la lista de iconos, haga clic en **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="5e7c8-152">In the list of tiles, click **SharePoint**.</span></span>
    
3. <span data-ttu-id="5e7c8-153">En la nueva pestaña **SharePoint** del explorador, haga clic en **+ Crear sitio**.</span><span class="sxs-lookup"><span data-stu-id="5e7c8-153">On the new **SharePoint** tab in your browser, click **+ Create site**.</span></span>
    
4. <span data-ttu-id="5e7c8-154">En la página **Crear un sitio**, haga clic en **Sitio de grupo**.</span><span class="sxs-lookup"><span data-stu-id="5e7c8-154">On the **Create a site** page, click **Team site**.</span></span>
    
5. <span data-ttu-id="5e7c8-155">En **Nombre del sitio**, escriba **Proyecto de campaña 1**.</span><span class="sxs-lookup"><span data-stu-id="5e7c8-155">In **Site name**, type **Campaign project 1**.</span></span> 
    
6. <span data-ttu-id="5e7c8-156">En **Team site description** (Descripción del sitio de grupo), escriba **Sitio de SharePoint para el proyecto de campaña 1**.</span><span class="sxs-lookup"><span data-stu-id="5e7c8-156">In **Team site description,** type **SharePoint site for Campaign project 1**.</span></span>
    
7. <span data-ttu-id="5e7c8-157">En **Configuración de privacidad**, seleccione **Private - only members can access this site** (Privado: solo los miembros tienen acceso a este sitio) y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="5e7c8-157">In **Privacy settings**, select **Private - only members can access this site**, and then click **Next**.</span></span>
    
8. <span data-ttu-id="5e7c8-158">En el panel **Who do you want to add?** (Usuarios que quiere agregar), haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="5e7c8-158">On the **Who do you want to add?** pane, click **Finish**.</span></span>
    
<span data-ttu-id="5e7c8-159">Después, configure la carpeta de documentos del sitio de grupo Proyecto de campaña 1 con la etiqueta Privada.</span><span class="sxs-lookup"><span data-stu-id="5e7c8-159">Next, configure the documents folder of the Campaign project 1 team site for the Private label.</span></span>
  
1. <span data-ttu-id="5e7c8-160">En la pestaña **Proyecto de campaña 1-Inicio** del explorador, haga clic en **Documentos**.</span><span class="sxs-lookup"><span data-stu-id="5e7c8-160">In the **Campaign project 1-Home** tab of your browser, click **Documents**.</span></span>
    
2. <span data-ttu-id="5e7c8-161">Haga clic en el icono de configuración y luego en **Configuración de biblioteca**.</span><span class="sxs-lookup"><span data-stu-id="5e7c8-161">Click the settings icon, and then click **Library settings**.</span></span>
    
3. <span data-ttu-id="5e7c8-162">En **Permisos y administración**, haga clic en **Apply label to items in this library** (Aplicar la etiqueta a los elementos de esta biblioteca).</span><span class="sxs-lookup"><span data-stu-id="5e7c8-162">Under **Permissions and Management**, click **Apply label to items in this library**.</span></span>
    
4. <span data-ttu-id="5e7c8-163">En **Configuración-Aplicar etiqueta**, seleccione **Privado** y haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="5e7c8-163">In **Settings-Apply Label**, select **Private**, and then click **Save**.</span></span>
    
### <a name="campaign-marketing-team-site"></a><span data-ttu-id="5e7c8-164">Sitio de grupo Marketing de la campaña</span><span class="sxs-lookup"><span data-stu-id="5e7c8-164">Campaign marketing team site</span></span>

<span data-ttu-id="5e7c8-165">Para crear un sitio de grupo aislado de SharePoint Online de nivel confidencial para recursos de marketing de la campaña, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="5e7c8-165">To create a sensitive-level isolated SharePoint Online team site for campaign marketing resources, do the following:</span></span>
  
1. <span data-ttu-id="5e7c8-166">Abra un explorador en el equipo local e inicie sesión en el centro de administración ([https://admin.microsoft.com](https://admin.microsoft.com)) con la cuenta de administrador global.</span><span class="sxs-lookup"><span data-stu-id="5e7c8-166">Using a browser on your local computer, sign in to the admin center ([https://admin.microsoft.com](https://admin.microsoft.com)) using your global administrator account.</span></span>
    
2. <span data-ttu-id="5e7c8-167">En la lista de iconos, haga clic en **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="5e7c8-167">In the list of tiles, click **SharePoint**.</span></span>
    
3. <span data-ttu-id="5e7c8-168">En la nueva pestaña **SharePoint** del explorador, haga clic en **+ Crear sitio**.</span><span class="sxs-lookup"><span data-stu-id="5e7c8-168">On the new **SharePoint** tab in your browser, click **+ Create site**.</span></span>
    
4. <span data-ttu-id="5e7c8-169">En la página **Crear un sitio**, haga clic en **Sitio de grupo**.</span><span class="sxs-lookup"><span data-stu-id="5e7c8-169">On the **Create a site** page, click **Team site**.</span></span>
    
5. <span data-ttu-id="5e7c8-170">En **Team site name** (Nombre del sitio de grupo), escriba **Marketing de la campaña**.</span><span class="sxs-lookup"><span data-stu-id="5e7c8-170">In **Team site name**, type **Campaign marketing**.</span></span>
    
6. <span data-ttu-id="5e7c8-171">En **Team site description** (Descripción del sitio de grupo), escriba **Sitio de SharePoint para marketing de la campaña (confidencial)**.</span><span class="sxs-lookup"><span data-stu-id="5e7c8-171">In **Team site description**, type **SharePoint site for campaign marketing (sensitive)**.</span></span>
    
7.  <span data-ttu-id="5e7c8-172">En **Configuración de privacidad**, seleccione **Private - only members can access this site** (Privado: solo los miembros tienen acceso a este sitio) y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="5e7c8-172">In **Privacy settings**, select **Private - only members can access this site**, and then click **Next**.</span></span>
    
8. <span data-ttu-id="5e7c8-173">En el panel **Who do you want to add?** (Usuarios que quiere agregar), haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="5e7c8-173">On the **Who do you want to add?** pane, click **Finish**.</span></span>
    
9. <span data-ttu-id="5e7c8-174">En la barra de herramientas de la nueva pestaña **Campaign marketing** (Marketing de la campaña) del explorador, haga clic en el icono de configuración y luego en **Permisos del sitio**.</span><span class="sxs-lookup"><span data-stu-id="5e7c8-174">On the new **Campaign marketing** tab in your browser, in the tool bar, click the settings icon, and then click **Site permissions**.</span></span>
    
10. <span data-ttu-id="5e7c8-175">En el panel **Permisos del sitio**, haga clic en **Advanced permissions settings** (Configuración de permisos avanzada).</span><span class="sxs-lookup"><span data-stu-id="5e7c8-175">In the **Site permissions** pane, click **Advanced permissions settings**.</span></span>
    
11. <span data-ttu-id="5e7c8-176">En la nueva pestaña **Permisos** del explorador, haga clic en **Configuración de solicitud de acceso**.</span><span class="sxs-lookup"><span data-stu-id="5e7c8-176">In the new **Permissions** tab in your browser, click **Access Request Settings**.</span></span>
    
12. <span data-ttu-id="5e7c8-177">En el cuadro de diálogo **Configuración de solicitud de acceso**, desactive **Permitir que los miembros compartan el sitio y archivos y carpetas individuales** y **Permitir a los miembros invitar a otros al grupo de miembros del sitio**, escriba **ITAdmin1@**<your organization name> **.onmicrosoft.com** en **Enviar todas las solicitudes de acceso** y luego haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="5e7c8-177">In the **Access Request Settings** dialog box, clear the **Allow members to share the site and individual files and folders** and **Allow members to invite others to the site members group** check boxes, type **ITAdmin1@**<your organization name> **.onmicrosoft.com** in **Send all requests for access**, and then click **OK**.</span></span>
    
13. <span data-ttu-id="5e7c8-178">Haga clic en **Marketing de la campaña-Miembros** en la lista.</span><span class="sxs-lookup"><span data-stu-id="5e7c8-178">Click **Campaign marketing Members** in the list.</span></span>
    
14. <span data-ttu-id="5e7c8-179">En la página **Personas y grupos**, haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="5e7c8-179">On the **People and Groups** page, click **New**.</span></span>
    
15. <span data-ttu-id="5e7c8-180">En el cuadro de diálogo **Compartir**, escriba **Personal directivo y estratégico**, selecciónelo y haga clic en **Compartir**.</span><span class="sxs-lookup"><span data-stu-id="5e7c8-180">In the **Share** dialog box, type **Senior and strategic staff**, select it, and then click **Share**.</span></span>
    
16. <span data-ttu-id="5e7c8-181">Repita los pasos 14 y 15 para grupo **Personal de Análisis** y la cuenta de usuario **Regular1**.</span><span class="sxs-lookup"><span data-stu-id="5e7c8-181">Repeat steps 14 and 15 for the **Analytics staff** group and the **Regular1** user account.</span></span>
    
17. <span data-ttu-id="5e7c8-182">Haga clic en el botón Atrás del explorador.</span><span class="sxs-lookup"><span data-stu-id="5e7c8-182">Click the back button on your browser.</span></span>
    
18. <span data-ttu-id="5e7c8-183">Haga clic en **Marketing de la campaña-Propietarios** en la lista.</span><span class="sxs-lookup"><span data-stu-id="5e7c8-183">Click **Campaign marketing Owners** in the list.</span></span>
    
19. <span data-ttu-id="5e7c8-184">En la página **Personas y grupos**, haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="5e7c8-184">On the **People and Groups** page, click **New**.</span></span>
    
20. <span data-ttu-id="5e7c8-185">En el cuadro de diálogo **Compartir**, escriba **Personal de TI**, selecciónelo y haga clic en **Compartir**.</span><span class="sxs-lookup"><span data-stu-id="5e7c8-185">In the **Share** dialog box, type **IT staff**, select it, and then click **Share**.</span></span>
    
21. <span data-ttu-id="5e7c8-186">Haga clic en el botón Atrás del explorador.</span><span class="sxs-lookup"><span data-stu-id="5e7c8-186">Click the back button on your browser.</span></span>
    
22. <span data-ttu-id="5e7c8-187">Cierre la pestaña **Personas y grupos** del explorador, haga clic en la pestaña **Marketing de la campaña-Inicio** del explorador y cierre el panel **Permisos del sitio**.</span><span class="sxs-lookup"><span data-stu-id="5e7c8-187">Close the **People and Groups** tab in your browser, click the **Campaign marketing-Home** tab in your browser, and then close the **Site permissions** pane.</span></span>
    
<span data-ttu-id="5e7c8-188">Estos son los resultados de la configuración de los permisos:</span><span class="sxs-lookup"><span data-stu-id="5e7c8-188">Here are the results of configuring permissions:</span></span>
  
- <span data-ttu-id="5e7c8-189">El grupo **Marketing de la campaña-Miembros** de SharePoint solo contiene el grupo **Personal directivo y estratégico** (que contiene las cuentas de usuario Candidate, ChiefOfStaff y Strategic1), el grupo **Marketing de la campaña** (que contiene la cuenta de usuario de administrador global), el grupo **Personal de Análisis** (que contiene la cuenta de usuario DataScientist1) y la cuenta de usuario**Regular1**.</span><span class="sxs-lookup"><span data-stu-id="5e7c8-189">The **Campaign marketing-Members** SharePoint group contains only the **Senior and strategic staff** group (which contains the Candidate, ChiefOfStaff, and Strategic1 user accounts), the **Campaign marketing** group (which contains the global administrator user account), the **Analytics staff** group (which contains the DataScientist1 user account), and the **Regular1** user account.</span></span>
    
- <span data-ttu-id="5e7c8-190">El grupo **Marketing de la campaña-Propietarios** de SharePoint solo contiene el grupo **Personal de TI** (que solo contiene las cuentas de usuario ITAdmin1 y ITAdmin2).</span><span class="sxs-lookup"><span data-stu-id="5e7c8-190">The **Campaign marketing-Owners** SharePoint group contains only the **IT staff** group (which contains only the ITAdmin1 and ITAdmin2 user accounts).</span></span>
    
- <span data-ttu-id="5e7c8-191">El grupo **Marketing de la campaña-Visitantes** de SharePoint no contiene grupos ni cuentas de usuario.</span><span class="sxs-lookup"><span data-stu-id="5e7c8-191">The **Campaign marketing-Visitors** SharePoint group contains no groups or user accounts.</span></span>
    
- <span data-ttu-id="5e7c8-192">Los miembros no pueden modificar los permisos de nivel de sitio (esto solo pueden hacerlo los miembros del grupo **Marketing de la campaña-Propietarios**).</span><span class="sxs-lookup"><span data-stu-id="5e7c8-192">Members cannot modify site-level permissions (this can only be done by members of the **Campaign marketing-Owners** group).</span></span>
    
- <span data-ttu-id="5e7c8-193">Otras cuentas de usuario no pueden acceder al sitio ni a sus recursos, pero pueden pedir acceso al sitio, que enviará un correo electrónico al buzón de la cuenta de usuario ITAdmin1.</span><span class="sxs-lookup"><span data-stu-id="5e7c8-193">Other user accounts cannot access the site or its resources, but can request access to the site, which will send an email to the ITAdmin1 user account mailbox.</span></span>
    
<span data-ttu-id="5e7c8-194">Después, configure la carpeta de documentos del sitio de grupo Marketing de la campaña con la etiqueta Confidencial.</span><span class="sxs-lookup"><span data-stu-id="5e7c8-194">Next, configure the documents folder of the Campaign marketing team site for the Sensitive label.</span></span>
  
1. <span data-ttu-id="5e7c8-195">En la pestaña **Marketing de la campaña-Inicio** del explorador, haga clic en **Documentos**.</span><span class="sxs-lookup"><span data-stu-id="5e7c8-195">In the **Campaign marketing-Home** tab of your browser, click **Documents**.</span></span>
    
2. <span data-ttu-id="5e7c8-196">Haga clic en el icono de configuración y luego en **Configuración de biblioteca**.</span><span class="sxs-lookup"><span data-stu-id="5e7c8-196">Click the settings icon, and then click **Library settings**.</span></span>
    
3. <span data-ttu-id="5e7c8-197">En **Permisos y administración**, haga clic en **Apply label to items in this library** (Aplicar la etiqueta a los elementos de esta biblioteca).</span><span class="sxs-lookup"><span data-stu-id="5e7c8-197">Under **Permissions and Management**, click **Apply label to items in this library**.</span></span>
    
4. <span data-ttu-id="5e7c8-198">En **Configuración-Aplicar etiqueta**, seleccione **Confidencial** y haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="5e7c8-198">In **Settings-Apply Label**, select **Sensitive**, and then click **Save**.</span></span>
    
<span data-ttu-id="5e7c8-p103">Después, configure una directiva de prevención de pérdida de datos (DLP) que notifique a los usuarios cada vez que compartan un documento en un sitio de grupo de SharePoint Online con la etiqueta Confidencial fuera de la organización. Esta directiva DLP se aplicará a los recursos del sitio Marketing de la campaña.</span><span class="sxs-lookup"><span data-stu-id="5e7c8-p103">Next, configure a data loss prevention (DLP) policy that notifies users when they share a document on a SharePoint Online team site with the Sensitive label outside the organization. This DLP policy will apply to resources in the Campaign marketing site.</span></span>
  
1. <span data-ttu-id="5e7c8-201">En la pestaña **Inicio de Microsoft Office** del explorador, haga clic en el icono **Seguridad y cumplimiento**.</span><span class="sxs-lookup"><span data-stu-id="5e7c8-201">From the **Microsoft Office Home** tab in your browser, click the **Security &amp; Compliance** tile.</span></span>
    
2. <span data-ttu-id="5e7c8-202">En la nueva pestaña **Seguridad y cumplimiento** del explorador, haga clic en **Prevención de pérdida de datos > Directiva**.</span><span class="sxs-lookup"><span data-stu-id="5e7c8-202">On the new **Security &amp; Compliance** tab in your browser, click **Data loss prevention > Policy**.</span></span>
    
3. <span data-ttu-id="5e7c8-203">En el panel **Prevención de pérdida de datos**, haga clic en **+ Crear una directiva**.</span><span class="sxs-lookup"><span data-stu-id="5e7c8-203">In the **Data loss prevention** pane, click **+ Create a policy**.</span></span>
    
4. <span data-ttu-id="5e7c8-204">En el panel **Start with a template or create a custom policy** (Empezar con una plantilla o crear una directiva personalizada), haga clic en **Personalizada** y luego en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="5e7c8-204">In the **Start with a template or create a custom policy** pane, click **Custom**, and then click **Next**.</span></span>
    
5. <span data-ttu-id="5e7c8-205">En el panel **Escriba un nombre para la directiva**, escriba **Sitios de grupo de SharePoint Online de etiqueta Confidencial** en **Nombre** y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="5e7c8-205">In the **Name your policy** pane, type **Sensitive label SharePoint Online team sites** in **Name**, and then click **Next**.</span></span>
    
6. <span data-ttu-id="5e7c8-206">En el panel **Elegir ubicaciones**, haga clic en **Let me choose specific locations** (Permitir elegir ubicaciones concretas) y luego en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="5e7c8-206">In the **Choose locations** pane, click **Let me choose specific locations**, and then click **Next**.</span></span>
    
7. <span data-ttu-id="5e7c8-207">En la lista de ubicaciones, deshabilite las ubicaciones **Correo electrónico de Exchange** y **Cuentas de OneDrive** y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="5e7c8-207">In the list of locations, disable the **Exchange email** and **OneDrive accounts** locations, and then click **Next**.</span></span>
    
8. <span data-ttu-id="5e7c8-208">En el panel **Customize the types of sensitive info you want to protect** (Personalizar los tipos de información confidencial que quiere proteger), haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="5e7c8-208">In the **Customize the types of sensitive info you want to protect** pane, click **Edit**.</span></span>
    
9. <span data-ttu-id="5e7c8-209">En el panel **Choose the types of content to protect** (Elegir los tipos de contenido que se va a proteger), haga clic en **Agregar** en el cuadro desplegable y luego en **Etiquetas**.</span><span class="sxs-lookup"><span data-stu-id="5e7c8-209">In the **Choose the types of content to protect** pane, click **Add** in the drop-down box, and then click **Labels**.</span></span>
    
10. <span data-ttu-id="5e7c8-210">En el panel **Etiquetas**, haga clic en **+ Agregar**, seleccione la etiqueta **Confidencial**, haga clic en **Agregar** y luego en **Listo**.</span><span class="sxs-lookup"><span data-stu-id="5e7c8-210">In the **Labels** pane, click **+ Add**, select the **Sensitive** label, click **Add**, and then click **Done**.</span></span>
    
11. <span data-ttu-id="5e7c8-211">En el panel **Choose the types of content to protect** (Elegir los tipos de contenido que se va a proteger), haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="5e7c8-211">In the **Choose the types of content to protect** pane, click **Save**.</span></span>
    
12. <span data-ttu-id="5e7c8-212">En el panel **Customize the types of sensitive info you want to protect** (Personalizar los tipos de información confidencial que quiere proteger), haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="5e7c8-212">In the **Customize the types of sensitive info you want to protect** pane, click **Next**.</span></span>
    
13. <span data-ttu-id="5e7c8-213">En el panel **What do you want to do if we detect sensitive info?** (¿Qué quiere hacer si se detecta información confidencial?), haga clic en **Customize the tip and email** (Personalizar la sugerencia y el correo electrónico).</span><span class="sxs-lookup"><span data-stu-id="5e7c8-213">In the **What do you want to do if we detect sensitive info?** pane, click **Customize the tip and email**.</span></span>
    
14. <span data-ttu-id="5e7c8-214">En el panel **Customize policy tips and email notifications** (Personalizar sugerencias de directiva y notificaciones de correo electrónico), haga clic en **Customize the policy tip text** (Personalizar el texto de la sugerencia de directiva).</span><span class="sxs-lookup"><span data-stu-id="5e7c8-214">In the **Customize policy tips and email notifications** pane, click **Customize the policy tip text**.</span></span>
    
15. <span data-ttu-id="5e7c8-215">En el cuadro de texto, escriba o pegue lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="5e7c8-215">In the text box, type or paste in the following:</span></span>
    
  - <span data-ttu-id="5e7c8-p104">Para compartir con un usuario de fuera de la organización, descargue el archivo y luego ábralo. Haga clic en Archivo, Proteger documento y Cifrar con contraseña y, luego, especifique una contraseña segura. Envíe la contraseña en un correo electrónico diferente u otro medio de comunicación.</span><span class="sxs-lookup"><span data-stu-id="5e7c8-p104">To share with a user outside the organization, download the file and then open it. Click File, then Protect Document, and then Encrypt with Password, and then specify a strong password. Send the password in a separate email or other means of communication.</span></span>
    
16. <span data-ttu-id="5e7c8-219">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="5e7c8-219">Click **OK**.</span></span>
    
17. <span data-ttu-id="5e7c8-220">En el panel **What do you want to do if we detect sensitive info?** (¿Qué quiere hacer si se detecta información confidencial?), desactive la casilla **Block people from sharing, and restrict access to shared content** (Evitar que los usuarios puedan compartir y restringir el acceso al contenido compartido) y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="5e7c8-220">In the **What do you want to do if we detect sensitive info?** pane, clear the **Block people from sharing, and restrict access to shared content** check box, and then click **Next**.</span></span>
    
18. <span data-ttu-id="5e7c8-221">En el panel **Do you want to turn on the policy or test things out first?** (¿Desea activar la directiva o probarla primero?), haga clic en **Yes, turn it on right away** (Sí, activarla inmediatamente) y luego en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="5e7c8-221">In the **Do you want to turn on the policy or test things out first?** pane, click **Yes, turn it on right away**, and then click **Next**.</span></span>
    
19. <span data-ttu-id="5e7c8-222">En el panel **Revise su configuración**, haga clic en **Crear** y luego en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="5e7c8-222">In the **Review your settings** pane, click **Create**, and then click **Close**.</span></span>
    
### <a name="campaign-strategy-team-site"></a><span data-ttu-id="5e7c8-223">Sitio de grupo Estrategia de la campaña</span><span class="sxs-lookup"><span data-stu-id="5e7c8-223">Campaign strategy team site</span></span>

<span data-ttu-id="5e7c8-224">Para crear un sitio de grupo aislado de SharePoint Online de nivel extremadamente confidencial para recursos estratégicos de la campaña, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="5e7c8-224">To create an isolated SharePoint Online team site at the highly confidential level for campaign strategy resources, do the following:</span></span>
  
1. <span data-ttu-id="5e7c8-225">Si es necesario, use un explorador en el equipo local e inicie sesión en el centro de administración ([https://admin.microsoft.com](https://admin.microsoft.com)) con la cuenta de administrador global.</span><span class="sxs-lookup"><span data-stu-id="5e7c8-225">If needed, use a browser on your local computer and sign in to the admin center ([https://admin.microsoft.com](https://admin.microsoft.com)) using your global administrator account.</span></span>
    
2. <span data-ttu-id="5e7c8-226">En la lista de iconos, haga clic en **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="5e7c8-226">In the list of tiles, click **SharePoint**.</span></span>
    
3. <span data-ttu-id="5e7c8-227">En la nueva pestaña **SharePoint** del explorador, haga clic en **+ Crear sitio**.</span><span class="sxs-lookup"><span data-stu-id="5e7c8-227">On the new **SharePoint** tab in your browser, click **+ Create site**.</span></span>
    
4. <span data-ttu-id="5e7c8-228">En la página **Crear un sitio**, haga clic en **Sitio de grupo**.</span><span class="sxs-lookup"><span data-stu-id="5e7c8-228">On the **Create a site** page, click **Team site**.</span></span>
    
5. <span data-ttu-id="5e7c8-229">En **Team site name** (Nombre del sitio de grupo), escriba **Estrategia de la campaña**.</span><span class="sxs-lookup"><span data-stu-id="5e7c8-229">In **Team site name**, type **Campaign strategy**.</span></span>
    
6. <span data-ttu-id="5e7c8-230">En **Team site description** (Descripción de sitio de grupo), escriba **Sitio de SharePoint para la estrategia de la campaña (extremadamente confidencial)**.</span><span class="sxs-lookup"><span data-stu-id="5e7c8-230">In **Team site description**, type **SharePoint site for campaign strategy (highly confidential)**.</span></span>
    
7.  <span data-ttu-id="5e7c8-231">En **Configuración de privacidad**, seleccione **Private - only members can access this site** (Privado: solo los miembros tienen acceso a este sitio) y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="5e7c8-231">In **Privacy settings**, select **Private - only members can access this site**, and then click **Next**.</span></span>
    
8. <span data-ttu-id="5e7c8-232">En el panel **Who do you want to add?** (Usuarios que quiere agregar), haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="5e7c8-232">On the **Who do you want to add?** pane, click **Finish**.</span></span>
    
9. <span data-ttu-id="5e7c8-233">En la barra de herramientas de la nueva pestaña **Estrategia de la campaña** del explorador, haga clic en el icono de configuración y luego en **Permisos del sitio**.</span><span class="sxs-lookup"><span data-stu-id="5e7c8-233">On the new **Campaign strategy** tab in your browser, in the tool bar, click the settings icon, and then click **Site permissions**.</span></span>
    
10. <span data-ttu-id="5e7c8-234">En el panel **Permisos del sitio**, haga clic en **Advanced permissions settings** (Configuración de permisos avanzada).</span><span class="sxs-lookup"><span data-stu-id="5e7c8-234">In the **Site permissions** pane, click **Advanced permissions settings**.</span></span>
    
11. <span data-ttu-id="5e7c8-235">En la nueva pestaña **Permisos** del explorador, haga clic en **Configuración de solicitud de acceso**.</span><span class="sxs-lookup"><span data-stu-id="5e7c8-235">In the new **Permissions** tab in your browser, click **Access Request Settings**.</span></span>
    
12. <span data-ttu-id="5e7c8-236">En el cuadro de diálogo **Configuración de solicitud de acceso**, desactive **Permitir que los miembros compartan el sitio y archivos y carpetas individuales** y **Permitir a los miembros invitar a otros al grupo de miembros del sitio** (de forma que las tres casillas estén desactivadas) y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="5e7c8-236">In the **Access Request Settings** dialog box, clear **Allow members to share the site and individual files and folders** and **Allow members to invite others to the site members group** (so that all three check boxes are cleared), and then click **OK**.</span></span>
    
13. <span data-ttu-id="5e7c8-237">Haga clic en **Estrategia de la campaña-Miembros** en la lista.</span><span class="sxs-lookup"><span data-stu-id="5e7c8-237">Click **Campaign strategy Members** in the list.</span></span>
    
14. <span data-ttu-id="5e7c8-238">En la página **Personas y grupos**, haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="5e7c8-238">On the **People and Groups** page, click **New**.</span></span>
    
15. <span data-ttu-id="5e7c8-239">En el cuadro de diálogo **Compartir**, escriba **Personal directivo y estratégico**, selecciónelo y haga clic en **Compartir**.</span><span class="sxs-lookup"><span data-stu-id="5e7c8-239">In the **Share** dialog box, type **Senior and strategic staff**, select it, and then click **Share**.</span></span>
    
16. <span data-ttu-id="5e7c8-240">Haga clic en **Estrategia de la campaña-Propietarios** en la lista.</span><span class="sxs-lookup"><span data-stu-id="5e7c8-240">Click **Campaign strategy Owners** in the list.</span></span>
    
17. <span data-ttu-id="5e7c8-241">En la página **Personas y grupos**, haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="5e7c8-241">On the **People and Groups** page, click **New**.</span></span>
    
18. <span data-ttu-id="5e7c8-242">En el cuadro de diálogo **Compartir**, escriba **Personal de TI**, selecciónelo y haga clic en **Compartir**.</span><span class="sxs-lookup"><span data-stu-id="5e7c8-242">In the **Share** dialog box, type **IT staff**, select it, and then click **Share**.</span></span>
    
19. <span data-ttu-id="5e7c8-243">Haga clic en el botón Atrás del explorador.</span><span class="sxs-lookup"><span data-stu-id="5e7c8-243">Click the back button on your browser.</span></span>
    
20. <span data-ttu-id="5e7c8-244">Cierre la pestaña **Personas y grupos** del explorador, haga clic en la pestaña **-Inicio** del explorador y cierre el panel **Permisos del sitio**.</span><span class="sxs-lookup"><span data-stu-id="5e7c8-244">Close the **People and Groups** tab in your browser, click the **Campaign strategy-Home** tab in your browser, and then close the **Site permissions** pane.</span></span>
    
<span data-ttu-id="5e7c8-245">Estos son los resultados de la configuración de los permisos:</span><span class="sxs-lookup"><span data-stu-id="5e7c8-245">Here are the results of configuring permissions:</span></span>
  
- <span data-ttu-id="5e7c8-246">El grupo **Estrategia de la campaña-Miembros** de SharePoint solo contiene el grupo **Personal directivo y estratégico** [Directivos] \(que solo contiene las cuentas de usuario Candidate, ChiefOfStaff, and Strategic1) y el grupo **Estrategia de la campaña** (que solo contiene la cuenta de usuario de administrador global).</span><span class="sxs-lookup"><span data-stu-id="5e7c8-246">The **Campaign strategy-Members** SharePoint group contains only the **Senior and strategic staff** group (which contains only the Candidate, ChiefOfStaff, and Strategic1 user accounts) and the **Campaign strategy** group (which contains only the global administrator user account).</span></span>
    
- <span data-ttu-id="5e7c8-247">El grupo **Estrategia de la campaña-Propietarios** de SharePoint solo contiene el grupo **Personal de TI** (que solo contiene las cuentas de usuario ITAdmin1 y ITAdmin2).</span><span class="sxs-lookup"><span data-stu-id="5e7c8-247">The **Campaign strategy-Owners** SharePoint group contains only the **IT staff** group (which contains only the ITAdmin1 and ITAdmin2 user accounts).</span></span>
    
- <span data-ttu-id="5e7c8-248">El grupo **Estrategia de la campaña-Visitantes** de SharePoint no contiene grupos ni cuentas de usuario.</span><span class="sxs-lookup"><span data-stu-id="5e7c8-248">The **Campaign strategy-Visitors** SharePoint group contains no groups or user accounts.</span></span>
    
- <span data-ttu-id="5e7c8-249">Los miembros no pueden modificar los permisos de nivel de sitio (esto solo pueden hacerlo los miembros del grupo **Estrategia de la campaña-Propietarios**).</span><span class="sxs-lookup"><span data-stu-id="5e7c8-249">Members cannot modify site-level permissions (this can only be done by members of the **Campaign strategy-Owners** group).</span></span>
    
- <span data-ttu-id="5e7c8-p105">Otras cuentas de usuario no tienen acceso al sitio o a sus recursos ni pedir acceso al sitio. Los permisos adicionales para el sitio deben ser asignados por el administrador global o por un miembro del grupo **Estrategia de la campaña-Propietarios**.</span><span class="sxs-lookup"><span data-stu-id="5e7c8-p105">Other user accounts cannot access the site or its resources or request access to the site. Additional permissions to the site must be done by the global administrator or by a member of the **Campaign strategy-Owners** group.</span></span>
    
<span data-ttu-id="5e7c8-252">Después, configure la carpeta de documentos del sitio de grupo Estrategia de la campaña con la etiqueta Extremadamente confidencial.</span><span class="sxs-lookup"><span data-stu-id="5e7c8-252">Next, configure the documents folder of the Campaign strategy team site for the Highly Confidential label.</span></span>
  
1. <span data-ttu-id="5e7c8-253">En la pestaña **Estrategia de la campaña-Inicio** del explorador, haga clic en **Documentos**.</span><span class="sxs-lookup"><span data-stu-id="5e7c8-253">In the **Campaign strategy-Home** tab of your browser, click **Documents**.</span></span>
    
2. <span data-ttu-id="5e7c8-254">Haga clic en el icono de configuración y luego en **Configuración de biblioteca**.</span><span class="sxs-lookup"><span data-stu-id="5e7c8-254">Click the settings icon, and then click **Library settings**.</span></span>
    
3. <span data-ttu-id="5e7c8-255">En **Permisos y administración**, haga clic en **Apply label to items in this library** (Aplicar la etiqueta a los elementos de esta biblioteca).</span><span class="sxs-lookup"><span data-stu-id="5e7c8-255">Under **Permissions and Management**, click **Apply label to items in this library**.</span></span>
    
4. <span data-ttu-id="5e7c8-256">En **Configuración-Aplicar etiqueta**, seleccione **Extremadamente confidencial** y haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="5e7c8-256">In **Settings-Apply Label**, select **Highly Confidential**, and then click **Save**.</span></span>
    
<span data-ttu-id="5e7c8-p106">Después, configure una directiva DLP que bloquee a los usuarios cuando compartan un documento en un sitio de grupo de SharePoint Online con la etiqueta Extremadamente confidencial fuera de la organización. Esta directiva DLP se aplicará a los recursos del sitio Estrategia de la campaña.</span><span class="sxs-lookup"><span data-stu-id="5e7c8-p106">Next, configure a DLP policy that blocks users when they share a document on a SharePoint Online team site with the Highly Confidential label outside the organization. This DLP policy will apply to resources in the Campaign strategy site.</span></span>
  
1. <span data-ttu-id="5e7c8-259">Si fuera necesario, use un explorador en el equipo local e inicie sesión en el centro de administración ([https://admin.microsoft.com](https://admin.microsoft.com)) con una cuenta que tenga el rol Administrador de seguridad o Administrador de la compañía.</span><span class="sxs-lookup"><span data-stu-id="5e7c8-259">If needed, use a browser on your local computer and sign in to the admin center ([https://admin.microsoft.com](https://admin.microsoft.com)) with an account that has the Security Administrator or Company Administrator role.</span></span>
    
2. <span data-ttu-id="5e7c8-260">En la pestaña **Inicio de Microsoft Office** del explorador, haga clic en el icono de **Seguridad y cumplimiento**.</span><span class="sxs-lookup"><span data-stu-id="5e7c8-260">From the **Microsoft Office Home** tab in your browser, click the **Security &amp; Compliance** tile.</span></span>
    
3. <span data-ttu-id="5e7c8-261">En la nueva pestaña **Seguridad y cumplimiento** del explorador, haga clic en **Prevención de pérdida de datos > Directiva**.</span><span class="sxs-lookup"><span data-stu-id="5e7c8-261">On the new **Security &amp; Compliance** tab in your browser, click **Data loss prevention > Policy**.</span></span>
    
4. <span data-ttu-id="5e7c8-262">En el panel **Prevención de pérdida de datos**, haga clic en **+ Crear una directiva**.</span><span class="sxs-lookup"><span data-stu-id="5e7c8-262">In the **Data loss prevention** pane, click **+ Create a policy**.</span></span>
    
5. <span data-ttu-id="5e7c8-263">En el panel **Start with a template or create a custom policy** (Empezar con una plantilla o crear una directiva personalizada), haga clic en **Personalizada** y luego en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="5e7c8-263">In the **Start with a template or create a custom policy** pane, click **Custom**, and then click **Next**.</span></span>
    
6. <span data-ttu-id="5e7c8-264">En el panel **Escriba un nombre para la directiva**, escriba **Sitios de grupo de SharePoint Online de etiqueta Extremadamente confidencial** en **Nombre** y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="5e7c8-264">In the **Name your policy** pane, type **Highly Confidential label SharePoint Online team sites** in **Name**, and then click **Next**.</span></span>
    
7. <span data-ttu-id="5e7c8-265">En el panel **Elegir ubicaciones**, haga clic en **Let me choose specific locations** (Permitir elegir ubicaciones concretas) y luego en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="5e7c8-265">In the **Choose locations** pane, click **Let me choose specific locations**, and then click **Next**.</span></span>
    
8. <span data-ttu-id="5e7c8-266">En la lista de ubicaciones, deshabilite las ubicaciones **Correo electrónico de Exchange** y **Cuentas de OneDrive** y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="5e7c8-266">In the list of locations, disable the **Exchange email** and **OneDrive accounts** locations, and then click **Next**.</span></span>
    
9. <span data-ttu-id="5e7c8-267">En el panel **Customize the types of sensitive info you want to protect** (Personalizar los tipos de información confidencial que quiere proteger), haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="5e7c8-267">In the **Customize the types of sensitive info you want to protect** pane, click **Edit**.</span></span>
    
10. <span data-ttu-id="5e7c8-268">En el panel **Choose the types of content to protect** (Elegir los tipos de contenido que se va a proteger), haga clic en **Agregar** en el cuadro desplegable y luego en **Etiquetas**.</span><span class="sxs-lookup"><span data-stu-id="5e7c8-268">In the **Choose the types of content to protect** pane, click **Add** in the drop-down box, and then click **Labels**.</span></span>
    
11. <span data-ttu-id="5e7c8-269">En el panel **Etiquetas**, haga clic en **+ Agregar**, seleccione la etiqueta **Extremadamente confidencial**, haga clic en **Agregar** y luego en **Listo**.</span><span class="sxs-lookup"><span data-stu-id="5e7c8-269">In the **Labels** pane, click **+ Add**, select the **Highly Confidential** label, click **Add**, and then click **Done**.</span></span>
    
12. <span data-ttu-id="5e7c8-270">En el panel **Choose the types of content to protect** (Elegir los tipos de contenido que se va a proteger), haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="5e7c8-270">In the **Choose the types of content to protect** pane, click **Save**.</span></span>
    
13. <span data-ttu-id="5e7c8-271">En el panel **Customize the types of sensitive info you want to protect** (Personalizar los tipos de información confidencial que quiere proteger), haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="5e7c8-271">In the **Customize the types of sensitive info you want to protect** pane, click **Next**.</span></span>
    
14. <span data-ttu-id="5e7c8-272">En el panel **What do you want to do if we detect sensitive info?** (¿Qué quiere hacer si se detecta información confidencial?), haga clic en **Customize the tip and email** (Personalizar la sugerencia y el correo electrónico).</span><span class="sxs-lookup"><span data-stu-id="5e7c8-272">In the **What do you want to do if we detect sensitive info?** pane, click **Customize the tip and email**.</span></span>
    
15. <span data-ttu-id="5e7c8-273">En el panel **Customize policy tips and email notifications** (Personalizar sugerencias de directiva y notificaciones de correo electrónico), haga clic en **Customize the policy tip text** (Personalizar el texto de la sugerencia de directiva).</span><span class="sxs-lookup"><span data-stu-id="5e7c8-273">In the **Customize policy tips and email notifications** pane, click **Customize the policy tip text**.</span></span>
    
16. <span data-ttu-id="5e7c8-274">En el cuadro de texto, escriba o pegue lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="5e7c8-274">In the text box, type or paste in the following:</span></span>
    
  - <span data-ttu-id="5e7c8-p107">Para compartir con un usuario de fuera de la organización, descargue el archivo y luego ábralo. Haga clic en Archivo, Proteger documento y Cifrar con contraseña y, luego, especifique una contraseña segura. Envíe la contraseña en un correo electrónico diferente u otro medio de comunicación.</span><span class="sxs-lookup"><span data-stu-id="5e7c8-p107">To share with a user outside the organization, download the file and then open it. Click File, then Protect Document, and then Encrypt with Password, and then specify a strong password. Send the password in a separate email or other means of communication.</span></span>
    
17. <span data-ttu-id="5e7c8-278">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="5e7c8-278">Click **OK**.</span></span>
    
18. <span data-ttu-id="5e7c8-279">En el panel **What do you want to do if we detect sensitive info?** (¿Qué desea hacer si se detecta información confidencial?), seleccione **Require a business justification to override** (Exigir una justificación de empresa para invalidar) y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="5e7c8-279">In the **What do you want to do if we detect sensitive info?** pane, select **Require a business justification to override**, and then click **Next**.</span></span>
    
19. <span data-ttu-id="5e7c8-280">En el panel **Do you want to turn on the policy or test things out first?** (¿Desea activar la directiva o probarla primero?), haga clic en **Yes, turn it on right away** (Sí, activarla inmediatamente) y luego en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="5e7c8-280">In the **Do you want to turn on the policy or test things out first?** pane, click **Yes, turn it on right away**, and then click **Next**.</span></span>
    
20. <span data-ttu-id="5e7c8-281">En el panel **Revise su configuración**, haga clic en **Crear** y luego en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="5e7c8-281">In the **Review your settings** pane, click **Create**, and then click **Close**.</span></span>
    
<span data-ttu-id="5e7c8-282">Siga las instrucciones de [Activate Azure RMS with the Microsoft 365 admin center](https://docs.microsoft.com/information-protection/deploy-use/activate-office365) (Activación de Azure RMS con el Centro de administración de Microsoft 365).</span><span class="sxs-lookup"><span data-stu-id="5e7c8-282">Use the instructions in [Activate Azure RMS with the Microsoft 365 admin center](https://docs.microsoft.com/information-protection/deploy-use/activate-office365).</span></span>
  
<span data-ttu-id="5e7c8-283">Después, siga estos pasos para configurar Azure Information Protection con una nueva directiva con ámbito y la subetiqueta de protección y permisos:</span><span class="sxs-lookup"><span data-stu-id="5e7c8-283">Next, configure Azure Information Protection with a new scoped policy and sub-label for protection and permissions with the following steps:</span></span>
  
1. <span data-ttu-id="5e7c8-284">Inicie sesión en el centro de administración con una cuenta que tenga el rol de Administrador de seguridad o Administrador de la compañía.</span><span class="sxs-lookup"><span data-stu-id="5e7c8-284">Sign in to the admin center with an account that has the Security Administrator or Company Administrator role.</span></span> <span data-ttu-id="5e7c8-285">Para obtener ayuda, vea [Where to sign in to Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4) (Dónde iniciar sesión en Office 365).</span><span class="sxs-lookup"><span data-stu-id="5e7c8-285">For help, see [Where to sign in to Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>
    
2. <span data-ttu-id="5e7c8-286">En una pestaña independiente del explorador, vaya a Azure Portal ([https://portal.azure.com](https://portal.azure.com)).</span><span class="sxs-lookup"><span data-stu-id="5e7c8-286">In a separate tab of your browser, go to the Azure portal ([https://portal.azure.com](https://portal.azure.com)).</span></span>
    
3. <span data-ttu-id="5e7c8-287">Si es la primera vez que configura Azure Information Protection, vea [estas instrucciones](https://docs.microsoft.com/information-protection/deploy-use/configure-policy#to-access-the-azure-information-protection-blade-for-the-first-time).</span><span class="sxs-lookup"><span data-stu-id="5e7c8-287">If this is the first time you are configuring Azure Information Protection, see these [instructions](https://docs.microsoft.com/information-protection/deploy-use/configure-policy#to-access-the-azure-information-protection-blade-for-the-first-time).</span></span>
    
4. <span data-ttu-id="5e7c8-288">En el panel de lista, haga clic en **Más servicios**, escriba **information** y haga clic en **Azure Information Protection**.</span><span class="sxs-lookup"><span data-stu-id="5e7c8-288">In the list pane, click **All services**, type **information**, and then click **Azure Information Protection**.</span></span>

5. <span data-ttu-id="5e7c8-289">Haga clic en **Etiquetas**.</span><span class="sxs-lookup"><span data-stu-id="5e7c8-289">Click **Labels**.</span></span>
    
6. <span data-ttu-id="5e7c8-290">Haga clic con el botón derecho en la etiqueta **Extremadamente confidencial** y después seleccione **Agregar una subetiqueta**.</span><span class="sxs-lookup"><span data-stu-id="5e7c8-290">Right-click the **Highly Confidential** label, and then click **Add a sub-label**.</span></span>
    
7. <span data-ttu-id="5e7c8-291">Escriba **Estrategia de la campaña** en **Nombre** y **Etiqueta para los documentos del sitio de grupo de estrategia de la campaña** en **Descripción**.</span><span class="sxs-lookup"><span data-stu-id="5e7c8-291">Type **CampaignStrategy** in **Name** and **Label for documents in the Campaign strategy team site** in **Description**.</span></span>
    
8. <span data-ttu-id="5e7c8-292">En **Establecer permisos para documentos y correos electrónicos que contengan esta etiqueta**, haga clic en **Proteger**.</span><span class="sxs-lookup"><span data-stu-id="5e7c8-292">In **Set permissions for documents and emails containing this label**, click **Protect**.</span></span>
    
9. <span data-ttu-id="5e7c8-293">En la sección **Protección**, haga clic en **Azure (clave de nube)**.</span><span class="sxs-lookup"><span data-stu-id="5e7c8-293">In the **Protection** section, click **Azure (cloud key)**.</span></span>
    
10. <span data-ttu-id="5e7c8-294">En la hoja **Protección**, en **Configuración de protección**, haga clic en **+ Agregar permisos**.</span><span class="sxs-lookup"><span data-stu-id="5e7c8-294">On the **Protection** blade, under **Protection settings**, click **+ Add permissions**.</span></span>
    
11. <span data-ttu-id="5e7c8-295">En la hoja **Agregar permisos**, en **Especificar usuarios y grupos**, haga clic en **+ Examinar directorio**.</span><span class="sxs-lookup"><span data-stu-id="5e7c8-295">On the **Add permissions** blade, under **Specify users and groups**, click **+ Browse directory**.</span></span>
    
12. <span data-ttu-id="5e7c8-296">En el panel **Usuarios y grupos de AAD**, seleccione **Personal directivo y estratégico** y haga clic en **Seleccionar**.</span><span class="sxs-lookup"><span data-stu-id="5e7c8-296">On the **AAD Users and Groups** pane, select **Senior and strategic staff**, and then click **Select**.</span></span>
    
13. <span data-ttu-id="5e7c8-297">En **Seleccionar permisos del conjunto predefinido o personalizado**, haga clic en **Personalizar** y después active las casillas **Ver derechos**, **Editar contenido**, **Guardar**, **Responder** y **Responder a todos**.</span><span class="sxs-lookup"><span data-stu-id="5e7c8-297">Under **Choose permissions from the preset or set custom**, click **Custom**, and then click the **View Rights**, **Edit Content**, **Save**, **Reply**, and **Reply all** check boxes.</span></span>
    
14. <span data-ttu-id="5e7c8-298">Haga clic en **Aceptar** dos veces.</span><span class="sxs-lookup"><span data-stu-id="5e7c8-298">Click **OK** twice.</span></span>
    
15. <span data-ttu-id="5e7c8-299">En la hoja **Subetiqueta**, haga clic en **Guardar** y, después, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="5e7c8-299">On the **Sub-label** blade, click **Save**, and then click **OK**.</span></span>

16. <span data-ttu-id="5e7c8-300">En la hoja **Azure Information Protection**, haga clic en **Directivas > + Agregar una directiva**.</span><span class="sxs-lookup"><span data-stu-id="5e7c8-300">On the **Azure Information protection** blade, click **Policies > + Add a new policy**.</span></span>
    
17. <span data-ttu-id="5e7c8-301">Escriba **Estrategia de la campaña** en **Nombre** y **Documentos del sitio de grupo de estrategia de la campaña** en **Descripción**.</span><span class="sxs-lookup"><span data-stu-id="5e7c8-301">Type **CampaignStrategy** in **Name** and **Documents in the Campaign strategy team site** in **Description**.</span></span>
    
18. <span data-ttu-id="5e7c8-302">Haga clic en **Seleccionar a qué usuarios o grupos se aplica esta directiva > Usuarios o grupos** y seleccione **Personal directivo y estratégico**.</span><span class="sxs-lookup"><span data-stu-id="5e7c8-302">Click **Select which users or groups get this policy > User/Groups**, and then select **Senior and strategic staff**.</span></span>
    
19. <span data-ttu-id="5e7c8-303">Haga clic en **Seleccionar > Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="5e7c8-303">Click **Select > OK**.</span></span>

20. <span data-ttu-id="5e7c8-p109">Haga clic en **Agregar o quitar etiquetas**. En el panel **Directiva: Agregar o quitar etiquetas**, seleccione **Estrategia de la campaña** y después haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="5e7c8-p109">Click **Add or remove labels**. In the **Policy: Add or remove labels** pane, click **CampaignStrategy**, and then click **OK**.</span></span>   

21. <span data-ttu-id="5e7c8-306">Haga clic en **Guardar**y después en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="5e7c8-306">Click **Save**, and then click **OK**.</span></span>
  
<span data-ttu-id="5e7c8-307">Ahora ya puede crear documentos en estos cuatro sitios y probar el acceso a ellos con diferentes cuentas de usuario.</span><span class="sxs-lookup"><span data-stu-id="5e7c8-307">You are now ready to begin creating documents in these four sites and test access to them with various user accounts.</span></span> 
  
<span data-ttu-id="5e7c8-308">Para proteger un documento con Azure Information Protection y esta nueva etiqueta, debe [instalar el cliente de Azure Information Protection](https://docs.microsoft.com/information-protection/rms-client/install-client-app) en un equipo de prueba, instalar Office desde el Centro de administración y luego iniciar sesión desde Microsoft Word con una cuenta del grupo **Personal directivo y estratégico** de la suscripción de evaluación.</span><span class="sxs-lookup"><span data-stu-id="5e7c8-308">To protect a document with Azure Information Protection and this new label, you must [install the Azure Information Protection client](https://docs.microsoft.com/information-protection/rms-client/install-client-app) on a test machine, install Office from the admin center, and then sign in from Microsoft Word with an account in the **Senior and strategic staff** group of your trial subscription.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="5e7c8-309">Vea también</span><span class="sxs-lookup"><span data-stu-id="5e7c8-309">See Also</span></span>

[<span data-ttu-id="5e7c8-310">Instrucciones de seguridad de Microsoft para campañas políticas, organizaciones sin ánimo de lucro y otras organizaciones ágiles</span><span class="sxs-lookup"><span data-stu-id="5e7c8-310">Microsoft Security Guidance for Political Campaigns, Nonprofits, and Other Agile Organizations</span></span>](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md)
  
[<span data-ttu-id="5e7c8-311">Configurar grupos y usuarios en un entorno de desarrollo y prueba de campaña política</span><span class="sxs-lookup"><span data-stu-id="5e7c8-311">Configure groups and users for a political campaign dev/test environment</span></span>](configure-groups-and-users-for-a-political-campaign-dev-test-environment.md)
  
[<span data-ttu-id="5e7c8-312">Guías del entorno de pruebas de adopción de la nube (TLG)</span><span class="sxs-lookup"><span data-stu-id="5e7c8-312">Cloud adoption Test Lab Guides (TLGs)</span></span>](https://docs.microsoft.com/office365/enterprise/cloud-adoption-test-lab-guides-tlgs)
  
[<span data-ttu-id="5e7c8-313">Adopción de la nube y soluciones híbridas</span><span class="sxs-lookup"><span data-stu-id="5e7c8-313">Cloud adoption and hybrid solutions</span></span>](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)




