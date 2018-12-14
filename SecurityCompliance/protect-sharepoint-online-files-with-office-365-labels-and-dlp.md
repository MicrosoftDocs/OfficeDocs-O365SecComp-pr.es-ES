---
title: Proteger archivos de SharePoint Online con DLP y etiquetas de Office 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/12/2018
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
ms.openlocfilehash: 38ded352c91a4c7f0138a6b9932840842d730926
ms.sourcegitcommit: 031781d0eecf33baabcd03ea53546d41076062b4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/12/2018
ms.locfileid: "27240573"
---
# <a name="protect-sharepoint-online-files-with-office-365-labels-and-dlp"></a><span data-ttu-id="75f6b-103">Proteger archivos de SharePoint Online con DLP y etiquetas de Office 365</span><span class="sxs-lookup"><span data-stu-id="75f6b-103">Protect SharePoint Online files with Office 365 labels and DLP</span></span>

 <span data-ttu-id="75f6b-104">**Resumen:** Aplique directivas de etiquetas y de prevención de pérdida de datos (DLP) de Office 365 a sitios de grupo de SharePoint Online con distintos niveles de protección de la información.</span><span class="sxs-lookup"><span data-stu-id="75f6b-104">**Summary:** Apply Office 365 labels and data loss prevention (DLP) policies for SharePoint Online team sites with various levels of information protection.</span></span>
  
<span data-ttu-id="75f6b-p101">Siga los pasos de este artículo para diseñar e implementar directivas de etiquetas y de prevención de pérdida de datos (DLP) de Office 365 para sitios de grupo de línea base, confidenciales y extremadamente confidenciales de SharePoint Online. Para más información sobre estos tres niveles de protección, vea [Proteger archivos y sitios de SharePoint Online](secure-sharepoint-online-sites-and-files.md).</span><span class="sxs-lookup"><span data-stu-id="75f6b-p101">Use the steps in this article to design and deploy Office 365 labels and DLP policies for baseline, sensitive, and highly confidential SharePoint Online team sites. For more information about these three tiers of protection, see [Secure SharePoint Online sites and files](secure-sharepoint-online-sites-and-files.md).</span></span>
  
## <a name="how-this-works"></a><span data-ttu-id="75f6b-107">Cómo funciona</span><span class="sxs-lookup"><span data-stu-id="75f6b-107">How this works</span></span>
1. <span data-ttu-id="75f6b-p102">Crear las etiquetas deseadas y publicarlas. Pueden tardar hasta 12 horas en publicarse.</span><span class="sxs-lookup"><span data-stu-id="75f6b-p102">Create the desired labels and publish these. It can take up to 12 hours for these to be published.</span></span>
2. <span data-ttu-id="75f6b-110">Para los sitios de SharePoint deseados, edite la configuración de la biblioteca de documentos para aplicar una etiqueta a los elementos de la biblioteca.</span><span class="sxs-lookup"><span data-stu-id="75f6b-110">For the desired SharePoint sites, edit the document library settings to apply a label to items in the library.</span></span>
3. <span data-ttu-id="75f6b-111">Crear directivas DLP que actúen en función de las etiquetas.</span><span class="sxs-lookup"><span data-stu-id="75f6b-111">Create DLP policies to take action based on the labels.</span></span>

<span data-ttu-id="75f6b-p103">Cuando los usuarios agregan un documento a la biblioteca, este recibirá la etiqueta asignada de forma predeterminada. Si es necesario, los usuarios pueden cambiar la etiqueta. Cuando un usuario comparte un documento fuera de la organización, DLP comprobará si tiene asignada una etiqueta y tomará medidas si una directiva DLP coincide con ella. DLP buscará otras coincidencias de directivas, como la protección de archivos con números de tarjeta de crédito si se configura este tipo de directiva.</span><span class="sxs-lookup"><span data-stu-id="75f6b-p103">When users add a document to the library, the document will receive the assigned label by default. Users can change the label, if needed. When a user shares a document outside the organization, DLP will check to see if a label is assigned and take action if a DLP policy matches the label. DLP will look for other policy matches as well, such as protecting files with credit card numbers if this type of policy is configured.</span></span> 

## <a name="office-365-labels-for-your-sharepoint-online-sites"></a><span data-ttu-id="75f6b-116">Etiquetas de Office 365 para los sitios de SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="75f6b-116">Office 365 labels for your SharePoint Online sites</span></span>

<span data-ttu-id="75f6b-117">Hay tres fases para crear y luego asignar etiquetas de Office 365 a sitios de grupo de SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="75f6b-117">There are three phases to creating and then assigning Office 365 labels to SharePoint Online team sites.</span></span>
  
### <a name="phase-1-determine-the-office-365-label-names"></a><span data-ttu-id="75f6b-118">Fase 1: Determinar los nombres de etiqueta de Office 365</span><span class="sxs-lookup"><span data-stu-id="75f6b-118">Phase 1: Determine the Office 365 label names</span></span>

<span data-ttu-id="75f6b-p104">En esta fase se determinan los nombres de las etiquetas de Office 365 para los cuatro niveles de protección de la información aplicados a los sitios de grupo de SharePoint Online. En la siguiente tabla se indican los nombres recomendados para cada nivel.</span><span class="sxs-lookup"><span data-stu-id="75f6b-p104">In this phase, you determine the names of your Office 365 labels for the four levels of information protection applied to SharePoint Online team sites. The following table lists the recommended names for each level.</span></span>
  
|<span data-ttu-id="75f6b-121">**Nivel de protección de sitio de grupo de SharePoint Online**</span><span class="sxs-lookup"><span data-stu-id="75f6b-121">**SharePoint Online team site protection level**</span></span>|<span data-ttu-id="75f6b-122">**Nombre de etiqueta**</span><span class="sxs-lookup"><span data-stu-id="75f6b-122">**Label name**</span></span>|
|:-----|:-----|
|<span data-ttu-id="75f6b-123">Base de referencia-Público</span><span class="sxs-lookup"><span data-stu-id="75f6b-123">Baseline-Public</span></span>  <br/> |<span data-ttu-id="75f6b-124">Interno público</span><span class="sxs-lookup"><span data-stu-id="75f6b-124">Internal public</span></span>  <br/> |
|<span data-ttu-id="75f6b-125">Base de referencia-Privado</span><span class="sxs-lookup"><span data-stu-id="75f6b-125">Baseline-Private</span></span>  <br/> |<span data-ttu-id="75f6b-126">Private</span><span class="sxs-lookup"><span data-stu-id="75f6b-126">Private</span></span>  <br/> |
|<span data-ttu-id="75f6b-127">Confidencial</span><span class="sxs-lookup"><span data-stu-id="75f6b-127">Sensitive</span></span>  <br/> |<span data-ttu-id="75f6b-128">Confidencial</span><span class="sxs-lookup"><span data-stu-id="75f6b-128">Sensitive</span></span>  <br/> |
|<span data-ttu-id="75f6b-129">Extremadamente confidencial</span><span class="sxs-lookup"><span data-stu-id="75f6b-129">Highly Confidential</span></span>  <br/> |<span data-ttu-id="75f6b-130">Extremadamente confidencial</span><span class="sxs-lookup"><span data-stu-id="75f6b-130">Highly Confidential</span></span>  <br/> |
   
### <a name="phase-2-create-the-office-365-labels"></a><span data-ttu-id="75f6b-131">Fase 2: Crear las etiquetas de Office 365</span><span class="sxs-lookup"><span data-stu-id="75f6b-131">Phase 2: Create the Office 365 labels</span></span>

<span data-ttu-id="75f6b-132">En esta fase se crean y luego se publican las etiquetas determinadas para los diferentes niveles de protección de la información.</span><span class="sxs-lookup"><span data-stu-id="75f6b-132">In this phase, you create and then publish your determined labels for the different levels of information protection.</span></span>
  
<span data-ttu-id="75f6b-133">Para crear las etiquetas, puede usar el Centro de administración de Office 365 o Microsoft PowerShell.</span><span class="sxs-lookup"><span data-stu-id="75f6b-133">To create the labels, you can use the Office 365 Admin center or Microsoft PowerShell.</span></span>
  
### <a name="create-office-365-labels-with-the-office-365-admin-center"></a><span data-ttu-id="75f6b-134">Crear etiquetas de Office 365 con el Centro de administración de Office 365</span><span class="sxs-lookup"><span data-stu-id="75f6b-134">Create Office 365 labels with the Office 365 Admin center</span></span>

1. <span data-ttu-id="75f6b-p105">Inicie sesión en el portal de Office 365 con una cuenta que tenga el rol Administrador de seguridad o Administrador de la compañía. Para obtener ayuda, vea [Where to sign in to Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4) (Dónde iniciar sesión en Office 365).</span><span class="sxs-lookup"><span data-stu-id="75f6b-p105">Sign in to the Office 365 portal with an account that has the Security Administrator or Company Administrator role. For help, see [Where to sign in to Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>
    
2. <span data-ttu-id="75f6b-137">En la pestaña **Inicio de Microsoft Office**, haga clic en el icono **Administrador**.</span><span class="sxs-lookup"><span data-stu-id="75f6b-137">From the **Microsoft Office Home** tab, click the **Admin** tile.</span></span>
    
3. <span data-ttu-id="75f6b-138">En la nueva pestaña **Centro de administración de Office** del explorador, haga clic en **Centros de administración Seguridad &amp; Cumplimiento**.</span><span class="sxs-lookup"><span data-stu-id="75f6b-138">From the new **Office Admin center** tab of your browser, click **Admin centers > Security &amp; Compliance**.</span></span>
    
4. <span data-ttu-id="75f6b-139">En la nueva pestaña **Inicio - Seguridad y cumplimiento** del explorador, haga clic en **Clasificaciones > Etiquetas**.</span><span class="sxs-lookup"><span data-stu-id="75f6b-139">From the new **Home - Security &amp; Compliance** tab of your browser, click **Classifications > Labels**.</span></span>
    
5. <span data-ttu-id="75f6b-140">En el panel **Inicio > Etiquetas**, haga clic en la pestaña **Retención** y, después, haga clic en **Publicar etiquetas**.</span><span class="sxs-lookup"><span data-stu-id="75f6b-140">From the **Home > Labels** pane, click the **Retention** tab, and then click **Create a label**.</span></span>
    
6. <span data-ttu-id="75f6b-141">En el panel **Asignar un nombre a la etiqueta**, escriba el nombre de la etiqueta y una descripción para administradores y usuarios, después, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="75f6b-141">On the **Name your label** pane, type the name of the label, and then click **Next**.</span></span>

7. <span data-ttu-id="75f6b-142">En el panel **Configuración de etiquetas**, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="75f6b-142">On the **Label settings** pane, click **Next**.</span></span>
    
8. <span data-ttu-id="75f6b-143">En el panel **Revise su configuración**, haga clic en **Crear** y luego en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="75f6b-143">On the **Review your settings** pane, click **Create this label**, and then click **Close**.</span></span>
    
9. <span data-ttu-id="75f6b-144">Repita los pasos del 5 al 8 para las etiquetas adicionales.</span><span class="sxs-lookup"><span data-stu-id="75f6b-144">Repeat steps 5-8 for your additional labels.</span></span>
    
### <a name="create-office-365-labels-with-powershell"></a><span data-ttu-id="75f6b-145">Crear etiquetas de Office 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="75f6b-145">Create Office 365 labels with PowerShell</span></span>

1. <span data-ttu-id="75f6b-146">Conéctese al [Centro de seguridad y cumplimiento de Office 365&amp; mediante PowerShell remoto](http://go.microsoft.com/fwlink/?LinkID=799771&amp;clcid=0x409) y especifique las credenciales de una cuenta que tenga el rol Administrador de seguridad o Administrador de la compañía.</span><span class="sxs-lookup"><span data-stu-id="75f6b-146">[Connect to the Office 365 Security &amp; Compliance Center using remote PowerShell](http://go.microsoft.com/fwlink/?LinkID=799771&amp;clcid=0x409) and specify the credentials of an account that has the Security Administrator or Company Administrator role.</span></span>
    
2. <span data-ttu-id="75f6b-147">Rellene la lista de nombres de etiqueta y luego ejecute estos comandos en el símbolo del sistema de PowerShell:</span><span class="sxs-lookup"><span data-stu-id="75f6b-147">Fill out the list of label names, and then run these commands at the PowerShell command prompt:</span></span>
    
  ```
  $labelNames=@(<list of label names, each enclosed in quotes and separated by commas>)
ForEach ($element in $labelNames){ New-ComplianceTag -Name $element }
  ```

### <a name="publish-your-new-labels"></a><span data-ttu-id="75f6b-148">Publicar las nuevas etiquetas</span><span class="sxs-lookup"><span data-stu-id="75f6b-148">Publish your new labels</span></span>

<span data-ttu-id="75f6b-149">Luego siga estos pasos para publicar las nuevas etiquetas de Office 365.</span><span class="sxs-lookup"><span data-stu-id="75f6b-149">Next, use these steps to publish the new Office 365 labels.</span></span>
  
1. <span data-ttu-id="75f6b-150">En el panel **Inicio > Etiquetas** del Centro de seguridad y cumplimiento, haga clic en la pestaña **Retención** y, después, haga clic en **Publicar etiquetas**.</span><span class="sxs-lookup"><span data-stu-id="75f6b-150">From the **Home > Labels** pane of the Security &amp; Compliance Center, click the **Retention** tab, and then click **Publish labels**.</span></span>
    
2. <span data-ttu-id="75f6b-151">En el panel **Elegir etiquetas para publicar**, haga clic en **Elegir etiquetas para publicar**.</span><span class="sxs-lookup"><span data-stu-id="75f6b-151">On the **Choose labels to publish** pane, click **Choose labels to publish**.</span></span>
    
3. <span data-ttu-id="75f6b-152">En el panel de **elección de etiquetas**, haga clic en **Agregar** y seleccione las cuatro etiquetas.</span><span class="sxs-lookup"><span data-stu-id="75f6b-152">On the **Choose labels** pane, click **Add** and select all four labels.</span></span>
    
4. <span data-ttu-id="75f6b-153">Haga clic en **Listo**.</span><span class="sxs-lookup"><span data-stu-id="75f6b-153">Click **Done**.</span></span>
    
5. <span data-ttu-id="75f6b-154">En el panel **Elegir etiquetas para publicar**, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="75f6b-154">On the **Choose labels to publish** pane, click **Next**.</span></span>
    
6. <span data-ttu-id="75f6b-155">En el panel **Elegir ubicaciones**, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="75f6b-155">On the **Choose locations** pane, click **Next**.</span></span>
    
7. <span data-ttu-id="75f6b-156">En el panel **Escriba un nombre para la directiva**, escriba un nombre para el conjunto de etiquetas en **Nombre** y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="75f6b-156">On the **Name your policy** pane, type a name for your set of labels in **Name**, and then click **Next**.</span></span>
    
8. <span data-ttu-id="75f6b-157">En el panel **Revise su configuración**, haga clic en **Publicar etiquetas** y luego en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="75f6b-157">On the **Review your settings** pane, click **Publish labels**, and then click **Close**.</span></span>

    
### <a name="phase-3-apply-the-office-365-labels-to-your-sharepoint-online-sites"></a><span data-ttu-id="75f6b-158">Fase 3: Aplicar las etiquetas de Office 365 a los sitios de SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="75f6b-158">Phase 3: Apply the Office 365 labels to your SharePoint Online sites</span></span>

<span data-ttu-id="75f6b-159">Siga estos pasos para aplicar las etiquetas de Office 365 a las carpetas de documentos de los sitios de grupo de SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="75f6b-159">Use these steps to apply the Office 365 labels to the documents folders of your SharePoint Online team sites.</span></span>
  
1. <span data-ttu-id="75f6b-160">En la pestaña **Inicio de Microsoft Office** del explorador, haga clic en el icono **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="75f6b-160">From the **Microsoft Office Home** tab of your browser, click the **SharePoint** tile.</span></span>
    
2. <span data-ttu-id="75f6b-161">En la nueva pestaña **SharePoint** del explorador, haga clic en un sitio al que haya que asignarle una etiqueta de Office 365.</span><span class="sxs-lookup"><span data-stu-id="75f6b-161">On the new **SharePoint** tab in your browser, click a site that needs an Office 365 label assigned.</span></span>
    
3. <span data-ttu-id="75f6b-162">En la nueva pestaña del sitio de SharePoint del explorador, haga clic en **Documentos**.</span><span class="sxs-lookup"><span data-stu-id="75f6b-162">In the new SharePoint site tab of your browser, click **Documents**.</span></span>
    
4. <span data-ttu-id="75f6b-163">Haga clic en el icono de configuración y luego en **Configuración de biblioteca**.</span><span class="sxs-lookup"><span data-stu-id="75f6b-163">Click the settings icon, and then click **Library settings**.</span></span>
    
5. <span data-ttu-id="75f6b-164">En **Permisos y administración**, haga clic en **Apply label to items in this library** (Aplicar la etiqueta a los elementos de esta biblioteca).</span><span class="sxs-lookup"><span data-stu-id="75f6b-164">Under **Permissions and Management**, click **Apply label to items in this library**.</span></span>
    
6. <span data-ttu-id="75f6b-165">En **Configuración-Aplicar etiqueta**, seleccione la etiqueta adecuada y haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="75f6b-165">In **Settings-Apply Label**, select the appropriate label, and then click **Save**.</span></span>
    
7. <span data-ttu-id="75f6b-166">Cierre la pestaña del sitio de SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="75f6b-166">Close the tab for the SharePoint Online site.</span></span>
    
8. <span data-ttu-id="75f6b-167">Repita los pasos del 3 al 8 para asignar etiquetas de Office 365 a otros sitios de SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="75f6b-167">Repeat steps 3-8 to assign Office 365 labels to your additional SharePoint Online sites.</span></span>
    
<span data-ttu-id="75f6b-168">Esta es la configuración resultante.</span><span class="sxs-lookup"><span data-stu-id="75f6b-168">Here is your resulting configuration.</span></span>
  
![Etiquetas de Office 365 para los cuatro tipos de sitios de grupo de SharePoint Online.](media/e0a4fdd2-1c30-4d93-8af4-a6f0c6c29966.png)
  
## <a name="dlp-policies-for-your-sharepoint-online-sites"></a><span data-ttu-id="75f6b-170">Directivas de DLP para los sitios de SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="75f6b-170">DLP policies for your SharePoint Online sites</span></span>

<span data-ttu-id="75f6b-171">Siga estos pasos para configurar una directiva de DLP que notifique a los usuarios cada vez que compartan un documento en un sitio de grupo confidencial de SharePoint Online de fuera de la organización.</span><span class="sxs-lookup"><span data-stu-id="75f6b-171">Use these steps to configure a DLP policy that notifies users when they share a document on a SharePoint Online sensitive team site outside the organization.</span></span>

1. <span data-ttu-id="75f6b-172">En la pestaña **Inicio de Microsoft Office**, haga clic en el icono **Administrador**.</span><span class="sxs-lookup"><span data-stu-id="75f6b-172">From the **Microsoft Office Home** tab, click the **Admin** tile.</span></span>
    
2. <span data-ttu-id="75f6b-173">En la nueva pestaña **Centro de administración de Office** del explorador, haga clic en **Centros de administración > Seguridad &amp; Cumplimiento**.</span><span class="sxs-lookup"><span data-stu-id="75f6b-173">From the new **Office Admin center** tab of your browser, click **Admin centers > Security &amp; Compliance**.</span></span>
    
3. <span data-ttu-id="75f6b-174">En la nueva pestaña **Seguridad y cumplimiento** del explorador, haga clic en **Prevención de pérdida de datos > Directiva**.</span><span class="sxs-lookup"><span data-stu-id="75f6b-174">On the new **Security &amp; Compliance** tab in your browser, click **Data loss prevention > Policy**.</span></span>
    
4. <span data-ttu-id="75f6b-175">En el panel **Prevención de pérdida de datos**, haga clic en **+ Crear una directiva**.</span><span class="sxs-lookup"><span data-stu-id="75f6b-175">In the **Data loss prevention** pane, click **+ Create a policy**.</span></span>
    
5. <span data-ttu-id="75f6b-176">En el panel **Start with a template or create a custom policy** (Empezar con una plantilla o crear una directiva personalizada), haga clic en **Personalizada** y luego en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="75f6b-176">In the **Start with a template or create a custom policy** pane, click **Custom**, and then click **Next**.</span></span>
    
5. <span data-ttu-id="75f6b-177">En el panel **Escriba un nombre para la directiva**, escriba el nombre de la directiva de DLP de nivel confidencial en **Nombre** y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="75f6b-177">In the **Name your policy** pane, type the name for the sensitive level DLP policy in **Name**, and then click **Next**.</span></span>
    
6. <span data-ttu-id="75f6b-178">En el panel **Elegir ubicaciones**, haga clic en **Let me choose specific locations** (Permitir elegir ubicaciones concretas) y luego en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="75f6b-178">In the **Choose locations** pane, click **Let me choose specific locations**, and then click **Next**.</span></span>
    
7. <span data-ttu-id="75f6b-179">En la lista de ubicaciones, deshabilite las ubicaciones **Correo electrónico de Exchange** y **Cuentas de OneDrive** y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="75f6b-179">In the list of locations, disable the **Exchange email** and **OneDrive accounts** locations, and then click **Next**.</span></span>
    
8. <span data-ttu-id="75f6b-180">En el panel **Customize the types of sensitive info you want to protect** (Personalizar los tipos de información confidencial que quiere proteger), haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="75f6b-180">In the **Customize the types of sensitive info you want to protect** pane, click **Edit**.</span></span>
    
9. <span data-ttu-id="75f6b-181">En el panel **Choose the types of content to protect** (Elegir los tipos de contenido que se va a proteger), haga clic en **Agregar** en el cuadro desplegable y luego en **Etiquetas**.</span><span class="sxs-lookup"><span data-stu-id="75f6b-181">In the **Choose the types of content to protect** pane, click **Add** in the drop-down box, and then click **Labels**.</span></span>
    
10. <span data-ttu-id="75f6b-182">En el panel **Etiquetas**, haga clic en **+ Agregar**, seleccione la etiqueta **Confidencial**, haga clic en **Agregar** y luego en **Listo**.</span><span class="sxs-lookup"><span data-stu-id="75f6b-182">In the **Labels** pane, click **+ Add**, select the **Sensitive** label, click **Add**, and then click **Done**.</span></span>
    
11. <span data-ttu-id="75f6b-183">En el panel **Choose the types of content to protect** (Elegir los tipos de contenido que se va a proteger), haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="75f6b-183">In the **Choose the types of content to protect** pane, click **Save**.</span></span>
    
12. <span data-ttu-id="75f6b-184">En el panel **Customize the types of sensitive info you want to protect** (Personalizar los tipos de información confidencial que quiere proteger), haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="75f6b-184">In the **Customize the types of sensitive info you want to protect** pane, click **Next**.</span></span>

13. <span data-ttu-id="75f6b-185">En el panel **What do you want to do if we detect sensitive info?** (¿Qué quiere hacer si se detecta información confidencial?), haga clic en **Customize the tip and email** (Personalizar la sugerencia y el correo electrónico).</span><span class="sxs-lookup"><span data-stu-id="75f6b-185">In the **What do you want to do if we detect sensitive info?** pane, click **Customize the tip and email**.</span></span>
    
14. <span data-ttu-id="75f6b-186">En el panel **Personalizar sugerencias de directiva y notificaciones de correo electrónico**, haga clic en **Personalizar el texto de la sugerencia de directiva**.</span><span class="sxs-lookup"><span data-stu-id="75f6b-186">In the **Customize policy tips and email notifications** pane, click **Customize the policy tip text**.</span></span>
    
15. <span data-ttu-id="75f6b-187">En el cuadro de texto, escriba o pegue una de las siguientes sugerencias, dependiendo de si ha implementado Azure Information Protection para proteger los archivos más confidenciales:</span><span class="sxs-lookup"><span data-stu-id="75f6b-187">In the text box, type or paste in one of the following tips, depending on if you implemented Azure Information Protection to protect highly confidential files:</span></span>
    
  - <span data-ttu-id="75f6b-p106">Para compartir con un usuario de fuera de la organización, descargue el archivo y luego ábralo. Haga clic en Archivo, Proteger documento y Cifrar con contraseña y, luego, especifique una contraseña segura. Envíe la contraseña en un correo electrónico diferente u otro medio de comunicación.</span><span class="sxs-lookup"><span data-stu-id="75f6b-p106">To share with a user outside the organization, download the file and then open it. Click File, then Protect Document, and then Encrypt with Password, and then specify a strong password. Send the password in a separate email or other means of communication.</span></span>
  - <span data-ttu-id="75f6b-p107">Los archivos extremadamente confidenciales están protegidos con cifrado. Solo pueden leerlos aquellos usuarios externos a los que su departamento de TI les ha concedido permiso para acceder a los archivos.</span><span class="sxs-lookup"><span data-stu-id="75f6b-p107">Highly confidential files are protected with encryption. Only external users who are granted permissions to these files by your IT department can read them.</span></span>
    
    <span data-ttu-id="75f6b-193">Otra opción es escribir o pegar una sugerencia de directiva propia que indique a los usuarios cómo compartir un archivo fuera de la organización.</span><span class="sxs-lookup"><span data-stu-id="75f6b-193">Alternately, type or paste in your own policy tip that instructs users on how to share a file outside your organization.</span></span>
    
16. <span data-ttu-id="75f6b-194">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="75f6b-194">Click **OK**.</span></span>
    
17. <span data-ttu-id="75f6b-195">En el panel **¿Qué quiere hacer si se detecta información confidencial?**, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="75f6b-195">In the **What do you want to do if we detect sensitive info?** pane, click **Customize the tip and email**.</span></span>
    
18. <span data-ttu-id="75f6b-196">En el panel **Do you want to turn on the policy or test things out first?** (¿Desea activar la directiva o probarla primero?), haga clic en **Yes, turn it on right away** (Sí, activarla inmediatamente) y luego en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="75f6b-196">In the **Do you want to turn on the policy or test things out first?** pane, click **Yes, turn it on right away**, and then click **Next**.</span></span>
    
19. <span data-ttu-id="75f6b-197">En el panel **Revise su configuración**, haga clic en **Crear** y luego en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="75f6b-197">In the **Review your settings** pane, click **Create**, and then click **Close**.</span></span>
    
<span data-ttu-id="75f6b-198">Esta es la configuración resultante para los sitios de grupo confidenciales de SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="75f6b-198">Here is your resulting configuration for sensitive SharePoint Online team sites.</span></span>
  
![Directiva de DLP de un sitio de grupo aislado de SharePoint Online que utiliza la etiqueta Confidencial de Office 365.](media/2ff4cc53-87a8-43e3-b637-3068d88409f3.png)
  
<span data-ttu-id="75f6b-200">Ahora siga estos pasos para configurar una directiva de DLP que impida a los usuarios compartir un documento en un sitio de grupo extremadamente confidencial de SharePoint Online de fuera de la organización.</span><span class="sxs-lookup"><span data-stu-id="75f6b-200">Next, use these steps to configure a DLP policy that blocks users when they share a document on a SharePoint Online highly confidential team site outside the organization.</span></span>
  
1. <span data-ttu-id="75f6b-201">En la pestaña **Inicio de Microsoft Office** del explorador, haga clic en el icono **Seguridad y cumplimiento**.</span><span class="sxs-lookup"><span data-stu-id="75f6b-201">From the **Microsoft Office Home** tab in your browser, click the **Security &amp; Compliance** tile.</span></span>
    
2. <span data-ttu-id="75f6b-202">En la nueva pestaña **Seguridad y cumplimiento** del explorador, haga clic en **Prevención de pérdida de datos > Directiva**.</span><span class="sxs-lookup"><span data-stu-id="75f6b-202">On the new **Security &amp; Compliance** tab in your browser, click **Data loss prevention > Policy**.</span></span>
    
3. <span data-ttu-id="75f6b-203">En el panel **Prevención de pérdida de datos**, haga clic en **+ Crear una directiva**.</span><span class="sxs-lookup"><span data-stu-id="75f6b-203">In the **Data loss prevention** pane, click **+ Create a policy**.</span></span>
    
4. <span data-ttu-id="75f6b-204">En el panel **Start with a template or create a custom policy** (Empezar con una plantilla o crear una directiva personalizada), haga clic en **Personalizada** y luego en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="75f6b-204">In the **Start with a template or create a custom policy** pane, click **Custom**, and then click **Next**.</span></span>
    
5. <span data-ttu-id="75f6b-205">En el panel **Escriba un nombre para la directiva**, escriba el nombre de la directiva de DLP de nivel extremadamente confidencial en **Nombre** y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="75f6b-205">In the **Name your policy** pane, type the name for the highly sensitive level DLP policy in **Name**, and then click **Next**.</span></span>
    
6. <span data-ttu-id="75f6b-206">En el panel **Elegir ubicaciones**, haga clic en **Let me choose specific locations** (Permitir elegir ubicaciones concretas) y luego en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="75f6b-206">In the **Choose locations** pane, click **Let me choose specific locations**, and then click **Next**.</span></span>
    
7. <span data-ttu-id="75f6b-207">En la lista de ubicaciones, deshabilite las ubicaciones **Correo electrónico de Exchange** y **Cuentas de OneDrive** y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="75f6b-207">In the list of locations, disable the **Exchange email** and **OneDrive accounts** locations, and then click **Next**.</span></span>
    
8. <span data-ttu-id="75f6b-208">En el panel **Customize the types of sensitive info you want to protect** (Personalizar los tipos de información confidencial que quiere proteger), haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="75f6b-208">In the **Customize the types of sensitive info you want to protect** pane, click **Edit**.</span></span>
    
9. <span data-ttu-id="75f6b-209">En el panel **Choose the types of content to protect** (Elegir los tipos de contenido que se va a proteger), haga clic en **Agregar** en el cuadro desplegable y luego en **Etiquetas**.</span><span class="sxs-lookup"><span data-stu-id="75f6b-209">In the **Choose the types of content to protect** pane, click **Add** in the drop-down box, and then click **Labels**.</span></span>
    
10. <span data-ttu-id="75f6b-210">En el panel **Etiquetas**, haga clic en **+ Agregar**, seleccione la etiqueta **Extremadamente confidencial**, haga clic en **Agregar** y luego en **Listo**.</span><span class="sxs-lookup"><span data-stu-id="75f6b-210">In the **Labels** pane, click **+ Add**, select the **Highly Confidential** label, click **Add**, and then click **Done**.</span></span>
    
11. <span data-ttu-id="75f6b-211">En el panel **Choose the types of content to protect** (Elegir los tipos de contenido que se va a proteger), haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="75f6b-211">In the **Choose the types of content to protect** pane, click **Save**.</span></span>
    
12. <span data-ttu-id="75f6b-212">En el panel **Customize the types of sensitive info you want to protect** (Personalizar los tipos de información confidencial que quiere proteger), haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="75f6b-212">In the **Customize the types of sensitive info you want to protect** pane, click **Next**.</span></span>
    
13. <span data-ttu-id="75f6b-213">En el panel **What do you want to do if we detect sensitive info?** (¿Qué quiere hacer si se detecta información confidencial?), haga clic en **Customize the tip and email** (Personalizar la sugerencia y el correo electrónico).</span><span class="sxs-lookup"><span data-stu-id="75f6b-213">In the **What do you want to do if we detect sensitive info?** pane, click **Customize the tip and email**.</span></span>
    
14. <span data-ttu-id="75f6b-214">En el panel **Customize policy tips and email notifications** (Personalizar sugerencias de directiva y notificaciones de correo electrónico), haga clic en **Customize the policy tip text** (Personalizar el texto de la sugerencia de directiva).</span><span class="sxs-lookup"><span data-stu-id="75f6b-214">In the **Customize policy tips and email notifications** pane, click **Customize the policy tip text**.</span></span>
    
15. <span data-ttu-id="75f6b-215">En el cuadro de texto, escriba o pegue lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="75f6b-215">In the text box, type or paste in the following:</span></span>
    
  - <span data-ttu-id="75f6b-p108">Para compartir con un usuario de fuera de la organización, descargue el archivo y luego ábralo. Haga clic en Archivo, Proteger documento y Cifrar con contraseña y, luego, especifique una contraseña segura. Envíe la contraseña en un correo electrónico diferente u otro medio de comunicación.</span><span class="sxs-lookup"><span data-stu-id="75f6b-p108">To share with a user outside the organization, download the file and then open it. Click File, then Protect Document, and then Encrypt with Password, and then specify a strong password. Send the password in a separate email or other means of communication.</span></span>
    
    <span data-ttu-id="75f6b-219">O bien escriba o pegue una sugerencia de directiva propia que indique a los usuarios cómo compartir un archivo fuera de la organización.</span><span class="sxs-lookup"><span data-stu-id="75f6b-219">Alternately, type or paste in your own policy tip that instructs users on how to share a file outside your organization.</span></span>
    
16. <span data-ttu-id="75f6b-220">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="75f6b-220">Click **OK**.</span></span>
    
17. <span data-ttu-id="75f6b-221">En el panel **¿Qué quiere hacer si se detecta información confidencial?**, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="75f6b-221">In the **What do you want to do if we detect sensitive info?** pane, click **Customize the tip and email**.</span></span>
    
18. <span data-ttu-id="75f6b-222">En el panel **Do you want to turn on the policy or test things out first?** (¿Desea activar la directiva o probarla primero?), haga clic en **Yes, turn it on right away** (Sí, activarla inmediatamente) y luego en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="75f6b-222">In the **Do you want to turn on the policy or test things out first?** pane, click **Yes, turn it on right away**, and then click **Next**.</span></span>
    
19. <span data-ttu-id="75f6b-223">En el panel **Revise su configuración**, haga clic en **Crear** y luego en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="75f6b-223">In the **Review your settings** pane, click **Create**, and then click **Close**.</span></span>
    
<span data-ttu-id="75f6b-224">Esta es la configuración resultante para los sitios de grupo extremadamente confidenciales de SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="75f6b-224">Here is your resulting configuration for high confidentiality SharePoint Online team sites.</span></span>
  
![Directiva de DLP de un sitio de grupo aislado de SharePoint Online que utiliza la etiqueta Extremadamente confidencial de Office 365.](media/f705d3d0-23c9-4333-8b70-ad3b91f835ea.png)
  
## <a name="next-step"></a><span data-ttu-id="75f6b-226">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="75f6b-226">Next step</span></span>

[<span data-ttu-id="75f6b-227">Proteger archivos de SharePoint Online con Azure Information Protection</span><span class="sxs-lookup"><span data-stu-id="75f6b-227">Protect SharePoint Online files with Azure Information Protection</span></span>](protect-sharepoint-online-files-with-azure-information-protection.md)
    
## <a name="see-also"></a><span data-ttu-id="75f6b-228">Vea también</span><span class="sxs-lookup"><span data-stu-id="75f6b-228">See Also</span></span>

[<span data-ttu-id="75f6b-229">Protección de archivos y sitios de SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="75f6b-229">Secure SharePoint Online sites and files</span></span>](secure-sharepoint-online-sites-and-files.md)
  
[<span data-ttu-id="75f6b-230">Proteger sitios de SharePoint Online en un entorno de desarrollo y pruebas</span><span class="sxs-lookup"><span data-stu-id="75f6b-230">Secure SharePoint Online sites in a dev/test environment</span></span>](secure-sharepoint-online-sites-in-a-dev-test-environment.md)
  
[<span data-ttu-id="75f6b-231">Guía de seguridad de Microsoft para campañas políticas, ONG y otras organizaciones ágiles</span><span class="sxs-lookup"><span data-stu-id="75f6b-231">Microsoft Security Guidance for Political Campaigns, Nonprofits, and Other Agile Organizations</span></span>](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md)
  
[<span data-ttu-id="75f6b-232">Adopción de la nube y soluciones híbridas</span><span class="sxs-lookup"><span data-stu-id="75f6b-232">Cloud adoption and hybrid solutions</span></span>](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)


