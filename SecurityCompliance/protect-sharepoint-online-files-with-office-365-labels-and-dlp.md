---
title: Proteger archivos de SharePoint Online con DLP y etiquetas de Office 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/15/2017
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom:
- Ent_Solutions
ms.assetid: c9f837af-8d71-4df1-a285-dedb1c5618b3
description: 'Resumen: Aplique directivas de etiquetas y prevención de pérdida de datos (DLP) de Office 365 a sitios de grupo de SharePoint Online con distintos niveles de protección de la información.'
ms.openlocfilehash: f8d835481c0eac00be11f7934c1d74b8a2d08d78
ms.sourcegitcommit: e0f016aca7befc8806233a492ee916cbe646094f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2018
ms.locfileid: "25345972"
---
# <a name="protect-sharepoint-online-files-with-office-365-labels-and-dlp"></a><span data-ttu-id="f927d-103">Proteger archivos de SharePoint Online con DLP y etiquetas de Office 365</span><span class="sxs-lookup"><span data-stu-id="f927d-103">Protect SharePoint Online files with Office 365 labels and DLP</span></span>

 <span data-ttu-id="f927d-104">**Resumen:** Aplique directivas de etiquetas y de prevención de pérdida de datos (DLP) de Office 365 a sitios de grupo de SharePoint Online con distintos niveles de protección de la información.</span><span class="sxs-lookup"><span data-stu-id="f927d-104">**Summary:** Apply Office 365 labels and data loss prevention (DLP) policies for SharePoint Online team sites with various levels of information protection.</span></span>
  
<span data-ttu-id="f927d-p101">Siga los pasos de este artículo para diseñar e implementar directivas de etiquetas y de prevención de pérdida de datos (DLP) de Office 365 para sitios de grupo de línea base, confidenciales y extremadamente confidenciales de SharePoint Online. Para más información sobre estos tres niveles de protección, vea [Proteger archivos y sitios de SharePoint Online](secure-sharepoint-online-sites-and-files.md).</span><span class="sxs-lookup"><span data-stu-id="f927d-p101">Use the steps in this article to design and deploy Office 365 labels and DLP policies for baseline, sensitive, and highly confidential SharePoint Online team sites. For more information about these three tiers of protection, see [Secure SharePoint Online sites and files](secure-sharepoint-online-sites-and-files.md).</span></span>
  
## <a name="how-this-works"></a><span data-ttu-id="f927d-107">Cómo funciona</span><span class="sxs-lookup"><span data-stu-id="f927d-107">How this works</span></span>
1. <span data-ttu-id="f927d-p102">Crear las etiquetas deseadas y publicarlas. Pueden tardar hasta 12 horas en publicarse.</span><span class="sxs-lookup"><span data-stu-id="f927d-p102">Create the desired labels and publish these. It can take up to 12 hours for these to be published.</span></span>
2. <span data-ttu-id="f927d-110">Para los sitios de SharePoint deseados, edite la configuración de la biblioteca de documentos para aplicar una etiqueta a los elementos de la biblioteca.</span><span class="sxs-lookup"><span data-stu-id="f927d-110">For the desired SharePoint sites, edit the document library settings to apply a label to items in the library.</span></span>
3. <span data-ttu-id="f927d-111">Crear directivas DLP que actúen en función de las etiquetas.</span><span class="sxs-lookup"><span data-stu-id="f927d-111">Create DLP policies to take action based on the labels.</span></span>

<span data-ttu-id="f927d-p103">Cuando los usuarios agregan un documento a la biblioteca, este recibirá la etiqueta asignada de forma predeterminada. Si es necesario, los usuarios pueden cambiar la etiqueta. Cuando un usuario comparte un documento fuera de la organización, DLP comprobará si tiene asignada una etiqueta y tomará medidas si una directiva DLP coincide con ella. DLP buscará otras coincidencias de directivas, como la protección de archivos con números de tarjeta de crédito si se configura este tipo de directiva.</span><span class="sxs-lookup"><span data-stu-id="f927d-p103">When users add a document to the library, the document will receive the assigned label by default. Users can change the label,if needed. When a user shares a document outside the organization, DLP will check to see if a label is assigned and take action if a DLP policy matches the label. DLP will look for other policy matches as well, such as protecting files with credit card numbers if this type of policy is configured.</span></span> 

## <a name="office-365-labels-for-your-sharepoint-online-sites"></a><span data-ttu-id="f927d-116">Etiquetas de Office 365 para los sitios de SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="f927d-116">Office 365 labels for your SharePoint Online sites</span></span>

<span data-ttu-id="f927d-117">Hay tres fases para crear y luego asignar etiquetas de Office 365 a sitios de grupo de SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="f927d-117">There are three phases to creating and then assigning Office 365 labels to SharePoint Online team sites.</span></span>
  
### <a name="phase-1-determine-the-office-365-label-names"></a><span data-ttu-id="f927d-118">Fase 1: Determinar los nombres de etiqueta de Office 365</span><span class="sxs-lookup"><span data-stu-id="f927d-118">Phase 1: Determine the Office 365 label names</span></span>

<span data-ttu-id="f927d-p104">En esta fase se determinan los nombres de las etiquetas de Office 365 para los cuatro niveles de protección de la información aplicados a los sitios de grupo de SharePoint Online. En la siguiente tabla se indican los nombres recomendados para cada nivel.</span><span class="sxs-lookup"><span data-stu-id="f927d-p104">In this phase, you determine the names of your Office 365 labels for the four levels of information protection applied to SharePoint Online team sites. The following table lists the recommended names for each level.</span></span>
  
|<span data-ttu-id="f927d-121">**Nivel de protección de sitio de grupo de SharePoint Online**</span><span class="sxs-lookup"><span data-stu-id="f927d-121">**SharePoint Online team site protection level**</span></span>|<span data-ttu-id="f927d-122">**Nombre de etiqueta**</span><span class="sxs-lookup"><span data-stu-id="f927d-122">**Label name**</span></span>|
|:-----|:-----|
|<span data-ttu-id="f927d-123">Base de referencia-Público</span><span class="sxs-lookup"><span data-stu-id="f927d-123">Baseline-Public</span></span>  <br/> |<span data-ttu-id="f927d-124">Interno público</span><span class="sxs-lookup"><span data-stu-id="f927d-124">Internal public</span></span>  <br/> |
|<span data-ttu-id="f927d-125">Base de referencia-Privado</span><span class="sxs-lookup"><span data-stu-id="f927d-125">Baseline-Private</span></span>  <br/> |<span data-ttu-id="f927d-126">Private</span><span class="sxs-lookup"><span data-stu-id="f927d-126">Private</span></span>  <br/> |
|<span data-ttu-id="f927d-127">Confidencial</span><span class="sxs-lookup"><span data-stu-id="f927d-127">Sensitive</span></span>  <br/> |<span data-ttu-id="f927d-128">Confidencial</span><span class="sxs-lookup"><span data-stu-id="f927d-128">Sensitive</span></span>  <br/> |
|<span data-ttu-id="f927d-129">Extremadamente confidencial</span><span class="sxs-lookup"><span data-stu-id="f927d-129">Highly Confidential</span></span>  <br/> |<span data-ttu-id="f927d-130">Extremadamente confidencial</span><span class="sxs-lookup"><span data-stu-id="f927d-130">Highly Confidential</span></span>  <br/> |
   
### <a name="phase-2-create-the-office-365-labels"></a><span data-ttu-id="f927d-131">Fase 2: Crear las etiquetas de Office 365</span><span class="sxs-lookup"><span data-stu-id="f927d-131">Phase 2: Create the Office 365 labels</span></span>

<span data-ttu-id="f927d-132">En esta fase se crean y luego se publican las etiquetas determinadas para los diferentes niveles de protección de la información.</span><span class="sxs-lookup"><span data-stu-id="f927d-132">In this phase, you create and then publish your determined labels for the different levels of information protection.</span></span>
  
<span data-ttu-id="f927d-133">Para crear las etiquetas, puede usar el Centro de administración de Office 365 o Microsoft PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f927d-133">To create the labels, you can use the Office 365 Admin center or Microsoft PowerShell.</span></span>
  
### <a name="create-office-365-labels-with-the-office-365-admin-center"></a><span data-ttu-id="f927d-134">Crear etiquetas de Office 365 con el Centro de administración de Office 365</span><span class="sxs-lookup"><span data-stu-id="f927d-134">Create Office 365 labels with the Office 365 Admin center</span></span>

1. <span data-ttu-id="f927d-p105">Inicie sesión en el portal de Office 365 con una cuenta que tenga el rol Administrador de seguridad o Administrador de la compañía. Para obtener ayuda, vea [Where to sign in to Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4) (Dónde iniciar sesión en Office 365).</span><span class="sxs-lookup"><span data-stu-id="f927d-p105">Sign in to the Office 365 portal with an account that has the Security Administrator or Company Administrator role. For help, see [Where to sign in to Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>
    
2. <span data-ttu-id="f927d-137">En la pestaña **Inicio de Microsoft Office**, haga clic en el icono **Administrador**.</span><span class="sxs-lookup"><span data-stu-id="f927d-137">From the **Microsoft Office Home** tab, click the **Admin** tile.</span></span>
    
3. <span data-ttu-id="f927d-138">En la nueva pestaña **Centro de administración de Office** del explorador, haga clic en **Centros de administración Seguridad &amp; Cumplimiento**.</span><span class="sxs-lookup"><span data-stu-id="f927d-138">From the new **Office Admin center** tab of your browser, click **Admin centers > Security &amp; Compliance**.</span></span>
    
4. <span data-ttu-id="f927d-139">En la nueva pestaña **Inicio - Seguridad y cumplimiento** del explorador, haga clic en **Clasificaciones > Etiquetas**.</span><span class="sxs-lookup"><span data-stu-id="f927d-139">From the new **Home - Security &amp; Compliance** tab of your browser, click **Classifications > Labels**.</span></span>
    
5. <span data-ttu-id="f927d-140">En el panel **Inicio > Etiquetas**, haga clic en **Crear una etiqueta**.</span><span class="sxs-lookup"><span data-stu-id="f927d-140">From the **Home > Labels** pane, click **Create a label**.</span></span>
    
6. <span data-ttu-id="f927d-141">En el panel **Asignar un nombre a la etiqueta**, escriba el nombre de la etiqueta y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="f927d-141">On the **Name your label** pane, type the name of the label, and then click **Next**.</span></span>
    
7. <span data-ttu-id="f927d-142">En el panel **Configuración de etiquetas**, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="f927d-142">On the **Label settings** pane, click **Next**.</span></span>
    
8. <span data-ttu-id="f927d-143">En el panel **Revise su configuración**, haga clic en **Crear esta etiqueta** y luego en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="f927d-143">On the **Review your settings** pane, click **Create this label**, and then click **Close**.</span></span>
    
9. <span data-ttu-id="f927d-144">Repita los pasos del 5 al 8 para las etiquetas adicionales.</span><span class="sxs-lookup"><span data-stu-id="f927d-144">Repeat steps 5-8 for your additional labels.</span></span>
    
### <a name="create-office-365-labels-with-powershell"></a><span data-ttu-id="f927d-145">Crear etiquetas de Office 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="f927d-145">Create Office 365 labels with PowerShell</span></span>

1. <span data-ttu-id="f927d-146">Conéctese al [Centro de seguridad y cumplimiento de Office 365&amp; mediante PowerShell remoto](http://go.microsoft.com/fwlink/?LinkID=799771&amp;clcid=0x409) y especifique las credenciales de una cuenta que tenga el rol Administrador de seguridad o Administrador de la compañía.</span><span class="sxs-lookup"><span data-stu-id="f927d-146">[Connect to the Office 365 Security &amp; Compliance Center using remote PowerShell](http://go.microsoft.com/fwlink/?LinkID=799771&amp;clcid=0x409) and specify the credentials of an account that has the Security Administrator or Company Administrator role.</span></span>
    
2. <span data-ttu-id="f927d-147">Rellene la lista de nombres de etiqueta y luego ejecute estos comandos en el símbolo del sistema de PowerShell:</span><span class="sxs-lookup"><span data-stu-id="f927d-147">Fill out the list of label names, and then run these commands at the PowerShell command prompt:</span></span>
    
  ```
  $labelNames=@(<list of label names, each enclosed in quotes and separated by commas>)
ForEach ($element in $labelNames){ New-ComplianceTag -Name $element }
  ```

<span data-ttu-id="f927d-148">Luego siga estos pasos para publicar las nuevas etiquetas de Office 365.</span><span class="sxs-lookup"><span data-stu-id="f927d-148">Next, use these steps to publish the new Office 365 labels.</span></span>
  
1. <span data-ttu-id="f927d-149">En el panel **Inicio > Etiquetas** del Centro de seguridad y cumplimiento, haga clic en **Publicar etiquetas**.</span><span class="sxs-lookup"><span data-stu-id="f927d-149">From the **Home > Labels** pane the Security &amp; Compliance Center, click **Publish labels**.</span></span>
    
2. <span data-ttu-id="f927d-150">En el panel **Elegir etiquetas para publicar**, haga clic en **Elegir etiquetas para publicar**.</span><span class="sxs-lookup"><span data-stu-id="f927d-150">On the **Choose labels to publish** pane, click **Choose labels to publish**.</span></span>
    
3. <span data-ttu-id="f927d-151">En el panel de **elección de etiquetas**, haga clic en **Agregar** y seleccione las cuatro etiquetas.</span><span class="sxs-lookup"><span data-stu-id="f927d-151">On the **Choose labels** pane, click **Add** and select all four labels.</span></span>
    
4. <span data-ttu-id="f927d-152">Haga clic en **Listo**.</span><span class="sxs-lookup"><span data-stu-id="f927d-152">Click **Done**.</span></span>
    
5. <span data-ttu-id="f927d-153">En el panel **Elegir etiquetas para publicar**, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="f927d-153">On the **Choose labels to publish** pane, click **Next**.</span></span>
    
6. <span data-ttu-id="f927d-154">En el panel **Elegir ubicaciones**, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="f927d-154">On the **Choose locations** pane, click **Next**.</span></span>
    
7. <span data-ttu-id="f927d-155">En el panel **Escriba un nombre para la directiva**, escriba un nombre para el conjunto de etiquetas en **Nombre** y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="f927d-155">On the **Name your policy** pane, type a name for your set of labels in **Name**, and then click **Next**.</span></span>
    
8. <span data-ttu-id="f927d-156">En el panel **Revise su configuración**, haga clic en **Publicar etiquetas** y luego en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="f927d-156">On the **Review your settings** pane, click **Publish labels**, and then click **Close**.</span></span>
    
### <a name="phase-3-apply-the-office-365-labels-to-your-sharepoint-online-sites"></a><span data-ttu-id="f927d-157">Fase 3: Aplicar las etiquetas de Office 365 a los sitios de SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="f927d-157">Phase 3: Apply the Office 365 labels to your SharePoint Online sites</span></span>

<span data-ttu-id="f927d-158">Siga estos pasos para aplicar las etiquetas de Office 365 a las carpetas de documentos de los sitios de grupo de SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="f927d-158">Use these steps to apply the Office 365 labels to the documents folders of your SharePoint Online team sites.</span></span>
  
1. <span data-ttu-id="f927d-159">En la pestaña **Inicio de Microsoft Office** del explorador, haga clic en el icono **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="f927d-159">From the **Microsoft Office Home** tab of your browser, click the **SharePoint** tile.</span></span>
    
2. <span data-ttu-id="f927d-160">En la nueva pestaña **SharePoint** del explorador, haga clic en un sitio al que haya que asignarle una etiqueta de Office 365.</span><span class="sxs-lookup"><span data-stu-id="f927d-160">On the new **SharePoint** tab in your browser, click a site that needs an Office 365 label assigned.</span></span>
    
3. <span data-ttu-id="f927d-161">En la nueva pestaña del sitio de SharePoint del explorador, haga clic en **Documentos**.</span><span class="sxs-lookup"><span data-stu-id="f927d-161">In the new SharePoint site tab of your browser, click **Documents**.</span></span>
    
4. <span data-ttu-id="f927d-162">Haga clic en el icono de configuración y luego en **Configuración de biblioteca**.</span><span class="sxs-lookup"><span data-stu-id="f927d-162">Click the settings icon, and then click **Library settings**.</span></span>
    
5. <span data-ttu-id="f927d-163">En **Permisos y administración**, haga clic en **Apply label to items in this library** (Aplicar la etiqueta a los elementos de esta biblioteca).</span><span class="sxs-lookup"><span data-stu-id="f927d-163">Under **Permissions and Management**, click **Apply label to items in this library**.</span></span>
    
6. <span data-ttu-id="f927d-164">En **Configuración-Aplicar etiqueta**, seleccione la etiqueta adecuada y haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="f927d-164">In **Settings-Apply Label**, select the appropriate label, and then click **Save**.</span></span>
    
7. <span data-ttu-id="f927d-165">Cierre la pestaña del sitio de SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="f927d-165">Close the tab for the SharePoint Online site.</span></span>
    
8. <span data-ttu-id="f927d-166">Repita los pasos del 3 al 8 para asignar etiquetas de Office 365 a otros sitios de SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="f927d-166">Repeat steps 3-8 to assign Office 365 labels to your additional SharePoint Online sites.</span></span>
    
<span data-ttu-id="f927d-167">Esta es la configuración resultante.</span><span class="sxs-lookup"><span data-stu-id="f927d-167">Here is your resulting configuration.</span></span>
  
![Etiquetas de Office 365 para los cuatro tipos de sitios de grupo de SharePoint Online.](media/e0a4fdd2-1c30-4d93-8af4-a6f0c6c29966.png)
  
## <a name="dlp-policies-for-your-sharepoint-online-sites"></a><span data-ttu-id="f927d-169">Directivas de DLP para los sitios de SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="f927d-169">DLP policies for your SharePoint Online sites</span></span>

<span data-ttu-id="f927d-170">Siga estos pasos para configurar una directiva de DLP que notifique a los usuarios cada vez que compartan un documento en un sitio de grupo confidencial de SharePoint Online de fuera de la organización.</span><span class="sxs-lookup"><span data-stu-id="f927d-170">Use these steps to configure a DLP policy that notifies users when they share a document on a SharePoint Online sensitive team site outside the organization.</span></span>
  
1. <span data-ttu-id="f927d-171">En la pestaña **Inicio de Microsoft Office** del explorador, haga clic en el icono **Seguridad y cumplimiento**.</span><span class="sxs-lookup"><span data-stu-id="f927d-171">From the **Microsoft Office Home** tab in your browser, click the **Security &amp; Compliance** tile.</span></span>
    
2. <span data-ttu-id="f927d-172">En la nueva pestaña **Seguridad y cumplimiento** del explorador, haga clic en **Prevención de pérdida de datos > Directiva**.</span><span class="sxs-lookup"><span data-stu-id="f927d-172">On the new **Security &amp; Compliance** tab in your browser, click **Data loss prevention > Policy**.</span></span>
    
3. <span data-ttu-id="f927d-173">En el panel **Prevención de pérdida de datos**, haga clic en **+ Crear una directiva**.</span><span class="sxs-lookup"><span data-stu-id="f927d-173">In the **Data loss prevention** pane, click **+ Create a policy**.</span></span>
    
4. <span data-ttu-id="f927d-174">En el panel **Start with a template or create a custom policy** (Empezar con una plantilla o crear una directiva personalizada), haga clic en **Personalizada** y luego en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="f927d-174">In the **Start with a template or create a custom policy** pane, click **Custom**, and then click **Next**.</span></span>
    
5. <span data-ttu-id="f927d-175">En el panel **Escriba un nombre para la directiva**, escriba el nombre de la directiva de DLP de nivel confidencial en **Nombre** y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="f927d-175">In the **Name your policy** pane, type the name for the sensitive level DLP policy in **Name**, and then click **Next**.</span></span>
    
6. <span data-ttu-id="f927d-176">En el panel **Elegir ubicaciones**, haga clic en **Let me choose specific locations** (Permitir elegir ubicaciones concretas) y luego en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="f927d-176">In the **Choose locations** pane, click **Let me choose specific locations**, and then click **Next**.</span></span>
    
7. <span data-ttu-id="f927d-177">En la lista de ubicaciones, deshabilite las ubicaciones **Correo electrónico de Exchange** y **Cuentas de OneDrive** y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="f927d-177">In the list of locations, disable the **Exchange email** and **OneDrive accounts** locations, and then click **Next**.</span></span>
    
8. <span data-ttu-id="f927d-178">En el panel **Customize the types of sensitive info you want to protect** (Personalizar los tipos de información confidencial que quiere proteger), haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="f927d-178">In the **Customize the types of sensitive info you want to protect** pane, click **Edit**.</span></span>
    
9. <span data-ttu-id="f927d-179">En el panel **Choose the types of content to protect** (Elegir los tipos de contenido que se va a proteger), haga clic en **Agregar** en el cuadro desplegable y luego en **Etiquetas**.</span><span class="sxs-lookup"><span data-stu-id="f927d-179">In the **Choose the types of content to protect** pane, click **Add** in the drop-down box, and then click **Labels**.</span></span>
    
10. <span data-ttu-id="f927d-180">En el panel **Etiquetas**, haga clic en **+ Agregar**, seleccione la etiqueta **Confidencial**, haga clic en **Agregar** y luego en **Listo**.</span><span class="sxs-lookup"><span data-stu-id="f927d-180">In the **Labels** pane, click **+ Add**, select the **Sensitive** label, click **Add**, and then click **Done**.</span></span>
    
11. <span data-ttu-id="f927d-181">En el panel **Choose the types of content to protect** (Elegir los tipos de contenido que se va a proteger), haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="f927d-181">In the **Choose the types of content to protect** pane, click **Save**.</span></span>
    
12. <span data-ttu-id="f927d-182">En el panel **Customize the types of sensitive info you want to protect** (Personalizar los tipos de información confidencial que quiere proteger), haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="f927d-182">In the **Customize the types of sensitive info you want to protect** pane, click **Next**.</span></span>
    
13. <span data-ttu-id="f927d-183">En el panel **What do you want to do if we detect sensitive info?** (¿Qué quiere hacer si se detecta información confidencial?), haga clic en **Customize the tip and email** (Personalizar la sugerencia y el correo electrónico).</span><span class="sxs-lookup"><span data-stu-id="f927d-183">In the **What do you want to do if we detect sensitive info?** pane, click **Customize the tip and email**.</span></span>
    
14. <span data-ttu-id="f927d-184">En el panel **Personalizar sugerencias de directiva y notificaciones de correo electrónico**, haga clic en **Personalizar el texto de la sugerencia de directiva**.</span><span class="sxs-lookup"><span data-stu-id="f927d-184">In the **Customize policy tips and email notifications** pane, click **Customize the policy tip text**.</span></span>
    
15. <span data-ttu-id="f927d-185">En el cuadro de texto, escriba o pegue una de las siguientes sugerencias, dependiendo de si ha implementado Azure Information Protection para proteger los archivos más confidenciales:</span><span class="sxs-lookup"><span data-stu-id="f927d-185">In the text box, type or paste in one of the following tips, depending on if you implemented Azure Information Protection to protect highly confidential files:</span></span>
    
  - <span data-ttu-id="f927d-p106">Para compartir con un usuario de fuera de la organización, descargue el archivo y luego ábralo. Haga clic en Archivo, Proteger documento y Cifrar con contraseña y, luego, especifique una contraseña segura. Envíe la contraseña en un correo electrónico diferente u otro medio de comunicación.</span><span class="sxs-lookup"><span data-stu-id="f927d-p106">To share with a user outside the organization, download the file and then open it. Click File, then Protect Document, and then Encrypt with Password, and then specify a strong password. Send the password in a separate email or other means of communication.</span></span>
  - <span data-ttu-id="f927d-p107">Los archivos extremadamente confidenciales están protegidos con cifrado. Solo pueden leerlos aquellos usuarios externos a los que su departamento de TI les ha concedido permiso para acceder a los archivos.</span><span class="sxs-lookup"><span data-stu-id="f927d-p107">Highly confidential files are protected with encryption. Only external users who are granted permissions to these files by your IT department can read them.</span></span>
    
    <span data-ttu-id="f927d-191">Otra opción es escribir o pegar una sugerencia de directiva propia que indique a los usuarios cómo compartir un archivo fuera de la organización.</span><span class="sxs-lookup"><span data-stu-id="f927d-191">Alternately, type or paste in your own policy tip that instructs users on how to share a file outside your organization.</span></span>
    
16. <span data-ttu-id="f927d-192">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="f927d-192">Click **OK**.</span></span>
    
17. <span data-ttu-id="f927d-193">En el panel **What do you want to do if we detect sensitive info?** (¿Qué quiere hacer si se detecta información confidencial?), desactive la casilla **Block people from sharing, and restrict access to shared content** (Evitar que los usuarios puedan compartir y restringir el acceso al contenido compartido) y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="f927d-193">In the **What do you want to do if we detect sensitive info?** pane, clear the **Block people from sharing, and restrict access to shared content** check box, and then click **Next**.</span></span>
    
18. <span data-ttu-id="f927d-194">En el panel **Do you want to turn on the policy or test things out first?** (¿Desea activar la directiva o probarla primero?), haga clic en **Yes, turn it on right away** (Sí, activarla inmediatamente) y luego en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="f927d-194">In the **Do you want to turn on the policy or test things out first?** pane, click **Yes, turn it on right away**, and then click **Next**.</span></span>
    
19. <span data-ttu-id="f927d-195">En el panel **Revise su configuración**, haga clic en **Crear** y luego en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="f927d-195">In the **Review your settings** pane, click **Create**, and then click **Close**.</span></span>
    
<span data-ttu-id="f927d-196">Esta es la configuración resultante para los sitios de grupo confidenciales de SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="f927d-196">Here is your resulting configuration for sensitive SharePoint Online team sites.</span></span>
  
![Directiva de DLP de un sitio de grupo aislado de SharePoint Online que utiliza la etiqueta Confidencial de Office 365.](media/2ff4cc53-87a8-43e3-b637-3068d88409f3.png)
  
<span data-ttu-id="f927d-198">Ahora siga estos pasos para configurar una directiva de DLP que impida a los usuarios compartir un documento en un sitio de grupo extremadamente confidencial de SharePoint Online de fuera de la organización.</span><span class="sxs-lookup"><span data-stu-id="f927d-198">Next, use these steps to configure a DLP policy that blocks users when they share a document on a SharePoint Online highly confidential team site outside the organization.</span></span>
  
1. <span data-ttu-id="f927d-199">En la pestaña **Inicio de Microsoft Office** del explorador, haga clic en el icono **Seguridad y cumplimiento**.</span><span class="sxs-lookup"><span data-stu-id="f927d-199">From the **Microsoft Office Home** tab in your browser, click the **Security &amp; Compliance** tile.</span></span>
    
2. <span data-ttu-id="f927d-200">En la nueva pestaña **Seguridad y cumplimiento** del explorador, haga clic en **Prevención de pérdida de datos > Directiva**.</span><span class="sxs-lookup"><span data-stu-id="f927d-200">On the new **Security &amp; Compliance** tab in your browser, click **Data loss prevention > Policy**.</span></span>
    
3. <span data-ttu-id="f927d-201">En el panel **Prevención de pérdida de datos**, haga clic en **+ Crear una directiva**.</span><span class="sxs-lookup"><span data-stu-id="f927d-201">In the **Data loss prevention** pane, click **+ Create a policy**.</span></span>
    
4. <span data-ttu-id="f927d-202">En el panel **Start with a template or create a custom policy** (Empezar con una plantilla o crear una directiva personalizada), haga clic en **Personalizada** y luego en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="f927d-202">In the **Start with a template or create a custom policy** pane, click **Custom**, and then click **Next**.</span></span>
    
5. <span data-ttu-id="f927d-203">En el panel **Escriba un nombre para la directiva**, escriba el nombre de la directiva de DLP de nivel extremadamente confidencial en **Nombre** y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="f927d-203">In the **Name your policy** pane, type the name for the highly sensitive level DLP policy in **Name**, and then click **Next**.</span></span>
    
6. <span data-ttu-id="f927d-204">En el panel **Elegir ubicaciones**, haga clic en **Let me choose specific locations** (Permitir elegir ubicaciones concretas) y luego en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="f927d-204">In the **Choose locations** pane, click **Let me choose specific locations**, and then click **Next**.</span></span>
    
7. <span data-ttu-id="f927d-205">En la lista de ubicaciones, deshabilite las ubicaciones **Correo electrónico de Exchange** y **Cuentas de OneDrive** y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="f927d-205">In the list of locations, disable the **Exchange email** and **OneDrive accounts** locations, and then click **Next**.</span></span>
    
8. <span data-ttu-id="f927d-206">En el panel **Customize the types of sensitive info you want to protect** (Personalizar los tipos de información confidencial que quiere proteger), haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="f927d-206">In the **Customize the types of sensitive info you want to protect** pane, click **Edit**.</span></span>
    
9. <span data-ttu-id="f927d-207">En el panel **Choose the types of content to protect** (Elegir los tipos de contenido que se va a proteger), haga clic en **Agregar** en el cuadro desplegable y luego en **Etiquetas**.</span><span class="sxs-lookup"><span data-stu-id="f927d-207">In the **Choose the types of content to protect** pane, click **Add** in the drop-down box, and then click **Labels**.</span></span>
    
10. <span data-ttu-id="f927d-208">En el panel **Etiquetas**, haga clic en **+ Agregar**, seleccione la etiqueta **Extremadamente confidencial**, haga clic en **Agregar** y luego en **Listo**.</span><span class="sxs-lookup"><span data-stu-id="f927d-208">In the **Labels** pane, click **+ Add**, select the **Highly Confidential** label, click **Add**, and then click **Done**.</span></span>
    
11. <span data-ttu-id="f927d-209">En el panel **Choose the types of content to protect** (Elegir los tipos de contenido que se va a proteger), haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="f927d-209">In the **Choose the types of content to protect** pane, click **Save**.</span></span>
    
12. <span data-ttu-id="f927d-210">En el panel **Customize the types of sensitive info you want to protect** (Personalizar los tipos de información confidencial que quiere proteger), haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="f927d-210">In the **Customize the types of sensitive info you want to protect** pane, click **Next**.</span></span>
    
13. <span data-ttu-id="f927d-211">En el panel **What do you want to do if we detect sensitive info?** (¿Qué quiere hacer si se detecta información confidencial?), haga clic en **Customize the tip and email** (Personalizar la sugerencia y el correo electrónico).</span><span class="sxs-lookup"><span data-stu-id="f927d-211">In the **What do you want to do if we detect sensitive info?** pane, click **Customize the tip and email**.</span></span>
    
14. <span data-ttu-id="f927d-212">En el panel **Customize policy tips and email notifications** (Personalizar sugerencias de directiva y notificaciones de correo electrónico), haga clic en **Customize the policy tip text** (Personalizar el texto de la sugerencia de directiva).</span><span class="sxs-lookup"><span data-stu-id="f927d-212">In the **Customize policy tips and email notifications** pane, click **Customize the policy tip text**.</span></span>
    
15. <span data-ttu-id="f927d-213">En el cuadro de texto, escriba o pegue lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f927d-213">In the text box, type or paste in the following:</span></span>
    
  - <span data-ttu-id="f927d-p108">Para compartir con un usuario de fuera de la organización, descargue el archivo y luego ábralo. Haga clic en Archivo, Proteger documento y Cifrar con contraseña y, luego, especifique una contraseña segura. Envíe la contraseña en un correo electrónico diferente u otro medio de comunicación.</span><span class="sxs-lookup"><span data-stu-id="f927d-p108">To share with a user outside the organization, download the file and then open it. Click File, then Protect Document, and then Encrypt with Password, and then specify a strong password. Send the password in a separate email or other means of communication.</span></span>
    
    <span data-ttu-id="f927d-217">O bien escriba o pegue una sugerencia de directiva propia que indique a los usuarios cómo compartir un archivo fuera de la organización.</span><span class="sxs-lookup"><span data-stu-id="f927d-217">Alternately, type or paste in your own policy tip that instructs users on how to share a file outside your organization.</span></span>
    
16. <span data-ttu-id="f927d-218">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="f927d-218">Click **OK**.</span></span>
    
17. <span data-ttu-id="f927d-219">En el panel **What do you want to do if we detect sensitive info?** (¿Qué desea hacer si se detecta información confidencial?), seleccione **Require a business justification to override** (Exigir una justificación de empresa para invalidar) y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="f927d-219">In the **What do you want to do if we detect sensitive info?** pane, select **Require a business justification to override**, and then click **Next**.</span></span>
    
18. <span data-ttu-id="f927d-220">En el panel **Do you want to turn on the policy or test things out first?** (¿Desea activar la directiva o probarla primero?), haga clic en **Yes, turn it on right away** (Sí, activarla inmediatamente) y luego en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="f927d-220">In the **Do you want to turn on the policy or test things out first?** pane, click **Yes, turn it on right away**, and then click **Next**.</span></span>
    
19. <span data-ttu-id="f927d-221">En el panel **Revise su configuración**, haga clic en **Crear** y luego en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="f927d-221">In the **Review your settings** pane, click **Create**, and then click **Close**.</span></span>
    
<span data-ttu-id="f927d-222">Esta es la configuración resultante para los sitios de grupo extremadamente confidenciales de SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="f927d-222">Here is your resulting configuration for high confidentiality SharePoint Online team sites.</span></span>
  
![Directiva de DLP de un sitio de grupo aislado de SharePoint Online que utiliza la etiqueta Extremadamente confidencial de Office 365.](media/f705d3d0-23c9-4333-8b70-ad3b91f835ea.png)
  
## <a name="next-step"></a><span data-ttu-id="f927d-224">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="f927d-224">Next step</span></span>

[<span data-ttu-id="f927d-225">Proteger archivos de SharePoint Online con Azure Information Protection</span><span class="sxs-lookup"><span data-stu-id="f927d-225">Protect SharePoint Online files with Azure Information Protection</span></span>](protect-sharepoint-online-files-with-azure-information-protection.md)
    
## <a name="see-also"></a><span data-ttu-id="f927d-226">Vea también</span><span class="sxs-lookup"><span data-stu-id="f927d-226">See Also</span></span>

[<span data-ttu-id="f927d-227">Protección de archivos y sitios de SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="f927d-227">Secure SharePoint Online sites and files</span></span>](secure-sharepoint-online-sites-and-files.md)
  
[<span data-ttu-id="f927d-228">Proteger sitios de SharePoint Online en un entorno de desarrollo y pruebas</span><span class="sxs-lookup"><span data-stu-id="f927d-228">Secure SharePoint Online sites in a dev/test environment</span></span>](secure-sharepoint-online-sites-in-a-dev-test-environment.md)
  
[<span data-ttu-id="f927d-229">Guía de seguridad de Microsoft para campañas políticas, ONG y otras organizaciones ágiles</span><span class="sxs-lookup"><span data-stu-id="f927d-229">Microsoft Security Guidance for Political Campaigns, Nonprofits, and Other Agile Organizations</span></span>](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md)
  
[<span data-ttu-id="f927d-230">Adopción de la nube y soluciones híbridas</span><span class="sxs-lookup"><span data-stu-id="f927d-230">Cloud adoption and hybrid solutions</span></span>](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)


