---
title: Proteger archivos de SharePoint Online con DLP y etiquetas de retención
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/29/2019
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom:
- Ent_Solutions
ms.assetid: c9f837af-8d71-4df1-a285-dedb1c5618b3
description: 'Resumen: Aplique directivas de etiquetas de retención y de prevención de pérdida de datos (DLP) a sitios de grupo de SharePoint Online con distintos niveles de protección de la información.'
ms.openlocfilehash: 81173e96ce6e67ee3b513abce4424686abe79e02
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32261678"
---
# <a name="protect-sharepoint-online-files-with-retention-labels-and-dlp"></a><span data-ttu-id="7f23c-103">Proteger archivos de SharePoint Online con DLP y etiquetas de retención</span><span class="sxs-lookup"><span data-stu-id="7f23c-103">Protect SharePoint Online files with retention labels and DLP</span></span>

 <span data-ttu-id="7f23c-104">**Resumen:** Aplique directivas de etiquetas de retención y de prevención de pérdida de datos (DLP) a sitios de grupo de SharePoint Online con distintos niveles de protección de la información.</span><span class="sxs-lookup"><span data-stu-id="7f23c-104">**Summary:** Apply retention labels and data loss prevention (DLP) policies for SharePoint Online team sites with various levels of information protection.</span></span>
  
<span data-ttu-id="7f23c-105">Siga los pasos de este artículo para diseñar e implementar directivas de etiquetas de retención y de prevención de pérdida de datos (DLP) para sitios de grupo de base de referencia, confidenciales y extremadamente confidenciales de SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="7f23c-105">Use the steps in this article to design and deploy retention labels and DLP policies for baseline, sensitive, and highly confidential SharePoint Online team sites.</span></span> <span data-ttu-id="7f23c-106">Para más información sobre estos tres niveles de protección, vea [Proteger sitios y archivos de SharePoint Online](secure-sharepoint-online-sites-and-files.md).</span><span class="sxs-lookup"><span data-stu-id="7f23c-106">For more information about these three tiers of protection, see [Secure SharePoint Online sites and files](secure-sharepoint-online-sites-and-files.md).</span></span>
  
## <a name="how-this-works"></a><span data-ttu-id="7f23c-107">Cómo funciona</span><span class="sxs-lookup"><span data-stu-id="7f23c-107">How this works</span></span>
1. <span data-ttu-id="7f23c-108">Crear las etiquetas de retención deseadas y publicarlas.</span><span class="sxs-lookup"><span data-stu-id="7f23c-108">Create the desired retention labels and publish these.</span></span> <span data-ttu-id="7f23c-109">Su publicación puede tardar hasta 12 horas.</span><span class="sxs-lookup"><span data-stu-id="7f23c-109">It can take up to 12 hours for these to be published.</span></span>
2. <span data-ttu-id="7f23c-110">Para los sitios de SharePoint deseados, edite la configuración de la biblioteca de documentos para aplicar las etiquetas de retención deseadas a los elementos de la biblioteca.</span><span class="sxs-lookup"><span data-stu-id="7f23c-110">For the desired SharePoint sites, edit the document library settings to apply the desired retention labels to items in the library.</span></span>
3. <span data-ttu-id="7f23c-111">Crear directivas DLP que actúen en función de las etiquetas de retención.</span><span class="sxs-lookup"><span data-stu-id="7f23c-111">Create DLP policies to take action based on the retention labels.</span></span>

<span data-ttu-id="7f23c-112">Cuando los usuarios agregan un documento a la biblioteca, el documento recibirá la etiqueta de retención asignada de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="7f23c-112">When users add a document to the library, the document will receive the assigned retention label by default.</span></span> <span data-ttu-id="7f23c-113">Los usuarios pueden cambiar la etiqueta, si fuera necesario.</span><span class="sxs-lookup"><span data-stu-id="7f23c-113">Users can change the label, if needed.</span></span> <span data-ttu-id="7f23c-114">Cuando un usuario comparte un documento fuera de la organización, DLP comprobará si se le ha asignado una etiqueta y tomará medidas si una directiva DLP coincide con la etiqueta.</span><span class="sxs-lookup"><span data-stu-id="7f23c-114">When a user shares a document outside the organization, DLP will check to see if a label is assigned and take action if a DLP policy matches the label.</span></span> <span data-ttu-id="7f23c-115">DLP buscará otras coincidencias de directivas, como la protección de archivos con números de tarjetas de crédito si se ha configurado este tipo de directiva.</span><span class="sxs-lookup"><span data-stu-id="7f23c-115">DLP will look for other policy matches as well, such as protecting files with credit card numbers if this type of policy is configured.</span></span> 

## <a name="retention-labels-for-your-sharepoint-online-sites"></a><span data-ttu-id="7f23c-116">Etiquetas de retención para los sitios de SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="7f23c-116">Retention labels for your SharePoint Online sites</span></span>

<span data-ttu-id="7f23c-117">Hay tres fases para crear y luego asignar etiquetas de retención a sitios de grupo de SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="7f23c-117">There are three phases to creating and then assigning retention labels to SharePoint Online team sites.</span></span>
  
### <a name="phase-1-determine-the-retention-label-names"></a><span data-ttu-id="7f23c-118">Fase 1: Determinar los nombres de etiqueta de retención</span><span class="sxs-lookup"><span data-stu-id="7f23c-118">Phase 1: Determine the retention label names</span></span>

<span data-ttu-id="7f23c-119">En esta fase se determinan los nombres de las etiquetas de retención para los cuatro niveles de protección de la información aplicados a los sitios de grupo de SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="7f23c-119">In this phase, you determine the names of your retention labels for the four levels of information protection applied to SharePoint Online team sites.</span></span> <span data-ttu-id="7f23c-120">En la siguiente tabla se indican los nombres recomendados para cada nivel.</span><span class="sxs-lookup"><span data-stu-id="7f23c-120">The following table lists the recommended names for each level.</span></span>
  
|<span data-ttu-id="7f23c-121">**Nivel de protección de sitio de grupo de SharePoint Online**</span><span class="sxs-lookup"><span data-stu-id="7f23c-121">**SharePoint Online team site protection level**</span></span>|<span data-ttu-id="7f23c-122">**Nombre de etiqueta**</span><span class="sxs-lookup"><span data-stu-id="7f23c-122">**Label name**</span></span>|
|:-----|:-----|
|<span data-ttu-id="7f23c-123">Base de referencia-Público</span><span class="sxs-lookup"><span data-stu-id="7f23c-123">Baseline-Public</span></span>  <br/> |<span data-ttu-id="7f23c-124">Interno público</span><span class="sxs-lookup"><span data-stu-id="7f23c-124">Internal public</span></span>  <br/> |
|<span data-ttu-id="7f23c-125">Base de referencia-Privado</span><span class="sxs-lookup"><span data-stu-id="7f23c-125">Baseline-Private</span></span>  <br/> |<span data-ttu-id="7f23c-126">Private</span><span class="sxs-lookup"><span data-stu-id="7f23c-126">Private</span></span>  <br/> |
|<span data-ttu-id="7f23c-127">Confidencial</span><span class="sxs-lookup"><span data-stu-id="7f23c-127">Sensitive</span></span>  <br/> |<span data-ttu-id="7f23c-128">Confidencial</span><span class="sxs-lookup"><span data-stu-id="7f23c-128">Sensitive</span></span>  <br/> |
|<span data-ttu-id="7f23c-129">Extremadamente confidencial</span><span class="sxs-lookup"><span data-stu-id="7f23c-129">Highly Confidential</span></span>  <br/> |<span data-ttu-id="7f23c-130">Extremadamente confidencial</span><span class="sxs-lookup"><span data-stu-id="7f23c-130">Highly Confidential</span></span>  <br/> |
   
### <a name="phase-2-create-the-retention-labels"></a><span data-ttu-id="7f23c-131">Fase 2: Crear las etiquetas de retención</span><span class="sxs-lookup"><span data-stu-id="7f23c-131">Phase 2: Create the retention labels</span></span>

<span data-ttu-id="7f23c-132">En esta fase se crean y luego se publican las etiquetas determinadas para los diferentes niveles de protección de la información.</span><span class="sxs-lookup"><span data-stu-id="7f23c-132">In this phase, you create and then publish your determined labels for the different levels of information protection.</span></span>
  
1. <span data-ttu-id="7f23c-133">Inicie sesión en el [portal de cumplimiento de Microsoft 365](https://compliance.microsoft.com) con una cuenta que tenga el rol de administrador de seguridad o administrador de la empresa.</span><span class="sxs-lookup"><span data-stu-id="7f23c-133">Sign in to the [Microsoft 365 compliance portal](https://compliance.microsoft.com) with an account that has the Security Administrator or Company Administrator role.</span></span>
    
2. <span data-ttu-id="7f23c-134">En la pestaña **Inicio: Cumplimiento de Microsoft 365** del explorador, haga clic en **Clasificaciones > Etiquetas**.</span><span class="sxs-lookup"><span data-stu-id="7f23c-134">From the **Home - Microsoft 365 compliance** tab of your browser, click **Classifications > Labels**.</span></span>
    
3. <span data-ttu-id="7f23c-135">Haga clic en **Etiquetas de retención > Crear una etiqueta**.</span><span class="sxs-lookup"><span data-stu-id="7f23c-135">Click **Retention labels > Create a label**.</span></span>
    
4. <span data-ttu-id="7f23c-136">En el panel **Asignar un nombre a la etiqueta**, escriba el nombre de la etiqueta y una descripción para administradores y usuarios, después, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="7f23c-136">On the **Name your label** pane, type the name of the label and a description for admins and users, and then click **Next**.</span></span>

5. <span data-ttu-id="7f23c-137">En el panel **Descriptores del plan de archivos**, rellene lo que sea necesario y, a continuación, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="7f23c-137">On the **File plan descriptors** pane, fill in as needed, and then click **Next**.</span></span>
    
6. <span data-ttu-id="7f23c-138">En el panel **Configuración de etiqueta**, si es necesario, marque **Retención** como **Activado** y establezca la configuración de retención.</span><span class="sxs-lookup"><span data-stu-id="7f23c-138">On the **Label settings** pane, if needed, set **Retention** to **On** and configure retention settings.</span></span> <span data-ttu-id="7f23c-139">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="7f23c-139">Click **Next**.</span></span>
    
7. <span data-ttu-id="7f23c-140">En el panel **Revise su configuración**, haga clic en **Crear la etiqueta**.</span><span class="sxs-lookup"><span data-stu-id="7f23c-140">On the **Review your settings** pane, click **Create the label**.</span></span>
    
8. <span data-ttu-id="7f23c-141">Para las otras etiquetas, haga clic en **Crear una etiqueta**, y, después, repita los pasos del 3 al 7 según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="7f23c-141">For your additional labels, click **Create a label**, and then repeat steps 3-7 as needed.</span></span>
    

### <a name="publish-your-new-labels"></a><span data-ttu-id="7f23c-142">Publicar las nuevas etiquetas</span><span class="sxs-lookup"><span data-stu-id="7f23c-142">Publish your new labels</span></span>

<span data-ttu-id="7f23c-143">Luego siga estos pasos para publicar las nuevas etiquetas de retención.</span><span class="sxs-lookup"><span data-stu-id="7f23c-143">Next, use these steps to publish the new retention labels.</span></span>
  
1. <span data-ttu-id="7f23c-144">En el panel **Etiquetas**, haga clic en la pestaña **Retención** y, después, haga clic en **Publicar etiquetas**.</span><span class="sxs-lookup"><span data-stu-id="7f23c-144">From the **Labels** pane, click the **Retention labels** tab, and then click **Publish labels**.</span></span>
    
2. <span data-ttu-id="7f23c-145">En el panel **Elegir etiquetas para publicar**, haga clic en **Elegir etiquetas para publicar**.</span><span class="sxs-lookup"><span data-stu-id="7f23c-145">On the **Choose labels to publish** pane, click **Choose labels to publish**.</span></span>
    
3. <span data-ttu-id="7f23c-146">En el panel **Elección de etiquetas**, haga clic en **Agregar**, seleccione las cuatro etiquetas y haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="7f23c-146">On the **Choose labels** pane, click **Add**, select all four labels, click **Add**.</span></span>
    
4. <span data-ttu-id="7f23c-147">Haga clic en **Listo**.</span><span class="sxs-lookup"><span data-stu-id="7f23c-147">Click **Done**.</span></span>
    
5. <span data-ttu-id="7f23c-148">En el panel **Elegir etiquetas para publicar**, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="7f23c-148">On the **Choose labels to publish** pane, click **Next**.</span></span>
    
6. <span data-ttu-id="7f23c-149">En el panel **Elegir ubicaciones**, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="7f23c-149">On the **Choose locations** pane, click **Next**.</span></span>
    
7. <span data-ttu-id="7f23c-150">En el panel **Escriba un nombre para la directiva**, escriba un nombre para el conjunto de etiquetas en **Nombre** y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="7f23c-150">On the **Name your policy** pane, type a name for your set of labels in **Name**, and then click **Next**.</span></span>
    
8. <span data-ttu-id="7f23c-151">En el panel **Revise la configuración**, haga clic en **Publicar etiquetas** y, después, en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="7f23c-151">On the **Review your settings** pane, click **Publish labels**, and then click **Close**.</span></span>

    
### <a name="phase-3-apply-the-retention-labels-to-your-sharepoint-online-sites"></a><span data-ttu-id="7f23c-152">Fase 3: Aplicar las etiquetas de retención a los sitios de SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="7f23c-152">Phase 3: Apply the retention labels to your SharePoint Online sites</span></span>

<span data-ttu-id="7f23c-153">Siga estos pasos para aplicar las etiquetas de retención a las carpetas de documentos de los sitios de grupo de SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="7f23c-153">Use these steps to apply the retention labels to the documents folders of your SharePoint Online team sites.</span></span>
  
1. <span data-ttu-id="7f23c-154">Inicie sesión en el [portal de Office 365](https://www.office.com), haga clic en la aplicación **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="7f23c-154">Sign in to the [Office 365 portal](https://www.office.com), click the **SharePoint** app.</span></span>
    
2. <span data-ttu-id="7f23c-155">En la nueva pestaña **SharePoint** del explorador, haga clic en un sitio al que haya que asignarle una etiqueta de retención.</span><span class="sxs-lookup"><span data-stu-id="7f23c-155">On the new **SharePoint** tab in your browser, click a site that needs a retention label assigned.</span></span>
    
3. <span data-ttu-id="7f23c-156">En la nueva pestaña del sitio de SharePoint del explorador, haga clic en **Documentos**.</span><span class="sxs-lookup"><span data-stu-id="7f23c-156">In the new SharePoint site tab of your browser, click **Documents**.</span></span>
    
4. <span data-ttu-id="7f23c-157">Haga clic en el icono de configuración y luego en **Configuración de biblioteca**.</span><span class="sxs-lookup"><span data-stu-id="7f23c-157">Click the settings icon, and then click **Library settings**.</span></span>
    
5. <span data-ttu-id="7f23c-158">En **Permisos y administración**, haga clic en **Apply label to items in this library** (Aplicar la etiqueta a los elementos de esta biblioteca).</span><span class="sxs-lookup"><span data-stu-id="7f23c-158">Under **Permissions and Management**, click **Apply label to items in this library**.</span></span>
    
6. <span data-ttu-id="7f23c-159">En **Configuración-Aplicar etiqueta**, seleccione la etiqueta de retención adecuada y haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="7f23c-159">In **Settings-Apply Label**, select the appropriate retention label, and then click **Save**.</span></span>
    
7. <span data-ttu-id="7f23c-160">Cierre la pestaña del sitio de SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="7f23c-160">Close the tab for the SharePoint Online site.</span></span>
    
8. <span data-ttu-id="7f23c-161">Repita los pasos del 2 al 8 para asignar etiquetas de retención a otros sitios de SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="7f23c-161">Repeat steps 2-8 to assign retention labels to your additional SharePoint Online sites.</span></span>
    
<span data-ttu-id="7f23c-162">Este es el resultado de la configuración.</span><span class="sxs-lookup"><span data-stu-id="7f23c-162">Here is your resulting configuration.</span></span>
  
![Etiquetas de retención para los cuatro tipos de sitios de grupo de SharePoint Online.](media/e0a4fdd2-1c30-4d93-8af4-a6f0c6c29966.png)
  
## <a name="dlp-policies-for-your-sharepoint-online-sites"></a><span data-ttu-id="7f23c-164">Directivas de DLP para los sitios de SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="7f23c-164">DLP policies for your SharePoint Online sites</span></span>

<span data-ttu-id="7f23c-165">Siga estos pasos para configurar una directiva de DLP que notifique a los usuarios cada vez que compartan un documento en un sitio de grupo confidencial de SharePoint Online de fuera de la organización.</span><span class="sxs-lookup"><span data-stu-id="7f23c-165">Use these steps to configure a DLP policy that notifies users when they share a document on a SharePoint Online sensitive team site outside the organization.</span></span>

1. <span data-ttu-id="7f23c-166">Inicie sesión en el [portal de cumplimiento de Microsoft 365](https://compliance.microsoft.com/) con una cuenta que tenga el rol Administrador de seguridad o Administrador de la compañía.</span><span class="sxs-lookup"><span data-stu-id="7f23c-166">Sign in to the [Microsoft 365 compliance portal](https://compliance.microsoft.com/) with an account that has the Security Administrator or Company Administrator role.</span></span>
    
2. <span data-ttu-id="7f23c-167">En la nueva pestaña **cumplimiento de Microsoft 365** del explorador, haga clic en **Directivas  > Prevención de pérdida de datos**.</span><span class="sxs-lookup"><span data-stu-id="7f23c-167">On the new **Microsoft 365 compliance** tab in your browser, click **Policies > Data loss prevention**.</span></span>
    
3. <span data-ttu-id="7f23c-168">En el panel **Inicio > Prevención de pérdida de datos**, haga clic en **Crear una directiva**.</span><span class="sxs-lookup"><span data-stu-id="7f23c-168">In the **Home > Data loss prevention** pane, click **Create a policy**.</span></span>
    
4. <span data-ttu-id="7f23c-169">En el panel **Start with a template or create a custom policy** (Empezar con una plantilla o crear una directiva personalizada), haga clic en **Personalizada** y luego en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="7f23c-169">In the **Start with a template or create a custom policy** pane, click **Custom**, and then click **Next**.</span></span>
    
5. <span data-ttu-id="7f23c-170">En el panel **Escriba un nombre para la directiva**, escriba el nombre de la directiva de DLP de nivel confidencial en **Nombre** y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="7f23c-170">In the **Name your policy** pane, type the name for the sensitive level DLP policy in **Name**, and then click **Next**.</span></span>
    
6. <span data-ttu-id="7f23c-171">En el panel **Elegir ubicaciones**, haga clic en **Let me choose specific locations** (Permitir elegir ubicaciones concretas) y luego en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="7f23c-171">In the **Choose locations** pane, click **Let me choose specific locations**, and then click **Next**.</span></span>
    
7. <span data-ttu-id="7f23c-172">En la lista de ubicaciones, deshabilite las ubicaciones **Correo electrónico de Exchange**, **Cuentas de OneDrive** y **mensajes de chat y de canal de Teams** y, después, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="7f23c-172">In the list of locations, disable the **Exchange email**, **OneDrive accounts**, and **Teams chat and channel messages** locations, and then click **Next**.</span></span>
    
8. <span data-ttu-id="7f23c-173">En el panel **Personalizar los tipos de información confidencial que quiere proteger**, haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="7f23c-173">In the **Customize the type of content you want to protect** pane, click **Edit**.</span></span>
    
9. <span data-ttu-id="7f23c-174">En el panel **Choose the types of content to protect** (Elegir los tipos de contenido que se va a proteger), haga clic en **Agregar** en el cuadro desplegable y luego en **Etiquetas de retención**.</span><span class="sxs-lookup"><span data-stu-id="7f23c-174">In the **Choose the types of content to protect** pane, click **Add** in the drop-down box, and then click **Retention labels**.</span></span>
    
10. <span data-ttu-id="7f23c-175">En el panel **Etiquetas de retención**, haga clic en **Agregar**, seleccione la etiqueta **Confidencial**, haga clic en **Agregar** y luego en **Listo**.</span><span class="sxs-lookup"><span data-stu-id="7f23c-175">In the **Retention labels** pane, click **Add**, select the **Sensitive** label, click **Add**, and then click **Done**.</span></span>
    
11. <span data-ttu-id="7f23c-176">En el panel **Choose the types of content to protect** (Elegir los tipos de contenido que se va a proteger), haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="7f23c-176">In the **Choose the types of content to protect** pane, click **Save**.</span></span>
    
12. <span data-ttu-id="7f23c-177">En el panel **Personalizar los tipos de información confidencial que quiere proteger**, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="7f23c-177">In the **Customize the type of content you want to protect** pane, click **Next**.</span></span>

13. <span data-ttu-id="7f23c-178">En el panel **What do you want to do if we detect sensitive info?** (¿Qué quiere hacer si se detecta información confidencial?), haga clic en **Customize the tip and email** (Personalizar la sugerencia y el correo electrónico).</span><span class="sxs-lookup"><span data-stu-id="7f23c-178">In the **What do you want to do if we detect sensitive info?** pane, click **Customize the tip and email**.</span></span>
    
14. <span data-ttu-id="7f23c-179">En el panel **Personalizar sugerencias de directiva y notificaciones de correo electrónico**, haga clic en **Personalizar el texto de la sugerencia de directiva**.</span><span class="sxs-lookup"><span data-stu-id="7f23c-179">In the **Customize policy tips and email notifications** pane, click **Customize the policy tip text**.</span></span>
    
15. <span data-ttu-id="7f23c-180">En el cuadro de texto, escriba o pegue una de las siguientes sugerencias, dependiendo de si ha implementado Azure Information Protection para proteger los archivos más confidenciales:</span><span class="sxs-lookup"><span data-stu-id="7f23c-180">In the text box, type or paste in one of the following tips, depending on if you implemented Azure Information Protection to protect highly confidential files:</span></span>
    
  - <span data-ttu-id="7f23c-p106">Para compartir con un usuario de fuera de la organización, descargue el archivo y luego ábralo. Haga clic en Archivo, Proteger documento y Cifrar con contraseña y, luego, especifique una contraseña segura. Envíe la contraseña en un correo electrónico diferente u otro medio de comunicación.</span><span class="sxs-lookup"><span data-stu-id="7f23c-p106">To share with a user outside the organization, download the file and then open it. Click File, then Protect Document, and then Encrypt with Password, and then specify a strong password. Send the password in a separate email or other means of communication.</span></span>
  - <span data-ttu-id="7f23c-p107">Los archivos extremadamente confidenciales están protegidos con cifrado. Solo pueden leerlos aquellos usuarios externos a los que su departamento de TI les ha concedido permiso para acceder a los archivos.</span><span class="sxs-lookup"><span data-stu-id="7f23c-p107">Highly confidential files are protected with encryption. Only external users who are granted permissions to these files by your IT department can read them.</span></span>
    
    <span data-ttu-id="7f23c-186">Otra opción es escribir o pegar una sugerencia de directiva propia que indique a los usuarios cómo compartir un archivo fuera de la organización.</span><span class="sxs-lookup"><span data-stu-id="7f23c-186">Alternately, type or paste in your own policy tip that instructs users on how to share a file outside your organization.</span></span>
    
16. <span data-ttu-id="7f23c-187">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="7f23c-187">Click **OK**.</span></span>
    
17. <span data-ttu-id="7f23c-188">En el panel **¿Qué quiere hacer si se detecta información confidencial?**, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="7f23c-188">In the **What do you want to do if we detect sensitive info?** pane, click **Next**.</span></span>
    
18. <span data-ttu-id="7f23c-189">En el panel **Do you want to turn on the policy or test things out first?** (¿Desea activar la directiva o probarla primero?), haga clic en **Yes, turn it on right away** (Sí, activarla inmediatamente) y luego en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="7f23c-189">In the **Do you want to turn on the policy or test things out first?** pane, click **Yes, turn it on right away**, and then click **Next**.</span></span>
    
19. <span data-ttu-id="7f23c-190">En el panel **Revise su configuración**, haga clic en **Crear** y luego en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="7f23c-190">In the **Review your settings** pane, click **Create**, and then click **Close**.</span></span>
    
<span data-ttu-id="7f23c-191">Esta es la configuración resultante para los sitios de grupo confidenciales de SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="7f23c-191">Here is your resulting configuration for sensitive SharePoint Online team sites.</span></span>
  
![Directiva de DLP de un sitio de grupo aislado de SharePoint Online que utiliza la etiqueta de retención Confidencial.](media/2ff4cc53-87a8-43e3-b637-3068d88409f3.png)
  
<span data-ttu-id="7f23c-193">Ahora siga estos pasos para configurar una directiva de DLP que impida a los usuarios compartir un documento en un sitio de grupo extremadamente confidencial de SharePoint Online de fuera de la organización.</span><span class="sxs-lookup"><span data-stu-id="7f23c-193">Next, use these steps to configure a DLP policy that blocks users when they share a document on a SharePoint Online highly confidential team site outside the organization.</span></span>
  
1. <span data-ttu-id="7f23c-194">En la nueva pestaña **cumplimiento de Microsoft 365** del explorador, haga clic en **Directivas  > Prevención de pérdida de datos**.</span><span class="sxs-lookup"><span data-stu-id="7f23c-194">On the new **Microsoft 365 compliance** tab in your browser, click **Policies > Data loss prevention**.</span></span>
    
2. <span data-ttu-id="7f23c-195">En el panel **Prevención de pérdida de datos**, haga clic en **Crear una directiva**.</span><span class="sxs-lookup"><span data-stu-id="7f23c-195">In the **Data loss prevention** pane, click **Create a policy**.</span></span>
    
3. <span data-ttu-id="7f23c-196">En el panel **Start with a template or create a custom policy** (Empezar con una plantilla o crear una directiva personalizada), haga clic en **Personalizada** y luego en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="7f23c-196">In the **Start with a template or create a custom policy** pane, click **Custom**, and then click **Next**.</span></span>
    
4. <span data-ttu-id="7f23c-197">En el panel **Escriba un nombre para la directiva**, escriba el nombre de la directiva de DLP de nivel extremadamente confidencial en **Nombre** y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="7f23c-197">In the **Name your policy** pane, type the name for the highly sensitive level DLP policy in **Name**, and then click **Next**.</span></span>
    
5. <span data-ttu-id="7f23c-198">En el panel **Elegir ubicaciones**, haga clic en **Let me choose specific locations** (Permitir elegir ubicaciones concretas) y luego en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="7f23c-198">In the **Choose locations** pane, click **Let me choose specific locations**, and then click **Next**.</span></span>
    
6. <span data-ttu-id="7f23c-199">En la lista de ubicaciones, deshabilite las ubicaciones **Correo electrónico de Exchange**, **Cuentas de OneDrive** y **mensajes de chat y de canal de Teams** y, después, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="7f23c-199">In the list of locations, disable the **Exchange email**, **OneDrive accounts**, and **Teams chat and channel messages** locations, and then click **Next**.</span></span>
    
7. <span data-ttu-id="7f23c-200">En el panel **Customize the types of sensitive info you want to protect** (Personalizar los tipos de información confidencial que quiere proteger), haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="7f23c-200">In the **Customize the types of sensitive info you want to protect** pane, click **Edit**.</span></span>
    
8. <span data-ttu-id="7f23c-201">En el panel **Choose the types of content to protect** (Elegir los tipos de contenido que se va a proteger), haga clic en **Agregar** en el cuadro desplegable y luego en **Etiquetas de retención**.</span><span class="sxs-lookup"><span data-stu-id="7f23c-201">In the **Choose the types of content to protect** pane, click **Add** in the drop-down box, and then click **Retention labels**.</span></span>
    
9. <span data-ttu-id="7f23c-202">En el panel **Etiquetas de retención**, haga clic en **Agregar**, seleccione la etiqueta **Extremadamente confidencial**, haga clic en **Agregar** y luego en **Listo**.</span><span class="sxs-lookup"><span data-stu-id="7f23c-202">In the **Retention labels** pane, click **Add**, select the **Highly Confidential** label, click **Add**, and then click **Done**.</span></span>
    
10. <span data-ttu-id="7f23c-203">En el panel **Choose the types of content to protect** (Elegir los tipos de contenido que se va a proteger), haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="7f23c-203">In the **Choose the types of content to protect** pane, click **Save**.</span></span>
    
12. <span data-ttu-id="7f23c-204">En el panel **Customize the types of sensitive info you want to protect** (Personalizar los tipos de información confidencial que quiere proteger), haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="7f23c-204">In the **Customize the types of sensitive info you want to protect** pane, click **Next**.</span></span>
    
13. <span data-ttu-id="7f23c-205">En el panel **What do you want to do if we detect sensitive info?** (¿Qué quiere hacer si se detecta información confidencial?), haga clic en **Customize the tip and email** (Personalizar la sugerencia y el correo electrónico).</span><span class="sxs-lookup"><span data-stu-id="7f23c-205">In the **What do you want to do if we detect sensitive info?** pane, click **Customize the tip and email**.</span></span>
    
14. <span data-ttu-id="7f23c-206">En el panel **Customize policy tips and email notifications** (Personalizar sugerencias de directiva y notificaciones de correo electrónico), haga clic en **Customize the policy tip text** (Personalizar el texto de la sugerencia de directiva).</span><span class="sxs-lookup"><span data-stu-id="7f23c-206">In the **Customize policy tips and email notifications** pane, click **Customize the policy tip text**.</span></span>
    
15. <span data-ttu-id="7f23c-207">En el cuadro de texto, escriba o pegue lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="7f23c-207">In the text box, type or paste in the following:</span></span>
    
  - <span data-ttu-id="7f23c-p108">Para compartir con un usuario de fuera de la organización, descargue el archivo y luego ábralo. Haga clic en Archivo, Proteger documento y Cifrar con contraseña y, luego, especifique una contraseña segura. Envíe la contraseña en un correo electrónico diferente u otro medio de comunicación.</span><span class="sxs-lookup"><span data-stu-id="7f23c-p108">To share with a user outside the organization, download the file and then open it. Click File, then Protect Document, and then Encrypt with Password, and then specify a strong password. Send the password in a separate email or other means of communication.</span></span>
    
    <span data-ttu-id="7f23c-211">O bien escriba o pegue una sugerencia de directiva propia que indique a los usuarios cómo compartir un archivo fuera de la organización.</span><span class="sxs-lookup"><span data-stu-id="7f23c-211">Alternately, type or paste in your own policy tip that instructs users on how to share a file outside your organization.</span></span>
    
16. <span data-ttu-id="7f23c-212">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="7f23c-212">Click **OK**.</span></span>
    
17. <span data-ttu-id="7f23c-213">En el panel **¿Qué quiere hacer si se detecta información confidencial?**, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="7f23c-213">In the **What do you want to do if we detect sensitive info?** pane, click **Next**.</span></span>
    
18. <span data-ttu-id="7f23c-214">En el panel **Do you want to turn on the policy or test things out first?** (¿Desea activar la directiva o probarla primero?), haga clic en **Yes, turn it on right away** (Sí, activarla inmediatamente) y luego en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="7f23c-214">In the **Do you want to turn on the policy or test things out first?** pane, click **Yes, turn it on right away**, and then click **Next**.</span></span>
    
19. <span data-ttu-id="7f23c-215">En el panel **Revise su configuración**, haga clic en **Crear** y luego en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="7f23c-215">In the **Review your settings** pane, click **Create**, and then click **Close**.</span></span>
    
<span data-ttu-id="7f23c-216">Esta es la configuración resultante para los sitios de grupo extremadamente confidenciales de SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="7f23c-216">Here is your resulting configuration for high confidentiality SharePoint Online team sites.</span></span>
  
![Directiva de DLP de un sitio de grupo aislado de SharePoint Online que utiliza la etiqueta de retención Extremadamente confidencial.](media/f705d3d0-23c9-4333-8b70-ad3b91f835ea.png)
  
## <a name="next-step"></a><span data-ttu-id="7f23c-218">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="7f23c-218">Next step</span></span>

[<span data-ttu-id="7f23c-219">Proteger archivos de SharePoint Online con Azure Information Protection</span><span class="sxs-lookup"><span data-stu-id="7f23c-219">Protect SharePoint Online files with Azure Information Protection</span></span>](protect-sharepoint-online-files-with-azure-information-protection.md)
    
## <a name="see-also"></a><span data-ttu-id="7f23c-220">Vea también</span><span class="sxs-lookup"><span data-stu-id="7f23c-220">See Also</span></span>

[<span data-ttu-id="7f23c-221">Protección de archivos y sitios de SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="7f23c-221">Secure SharePoint Online sites and files</span></span>](secure-sharepoint-online-sites-and-files.md)
  
[<span data-ttu-id="7f23c-222">Instrucciones de seguridad de Microsoft para campañas políticas, organizaciones sin ánimo de lucro y otras organizaciones ágiles</span><span class="sxs-lookup"><span data-stu-id="7f23c-222">Microsoft Security Guidance for Political Campaigns, Nonprofits, and Other Agile Organizations</span></span>](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md)
  
[<span data-ttu-id="7f23c-223">Adopción de la nube y soluciones híbridas</span><span class="sxs-lookup"><span data-stu-id="7f23c-223">Cloud adoption and hybrid solutions</span></span>](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)


