---
title: Protección de archivos de SharePoint Online con Azure Information Protection
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
ms.assetid: 5b9c8e41-25d2-436d-89bb-9aecb9ec2b80
description: 'Resumen: aplique Azure Information Protection para proteger los archivos en un sitio de grupo de SharePoint Online altamente confidencial.'
ms.openlocfilehash: 4be30059192bb954a1c2d07d34ece76bb339d7dc
ms.sourcegitcommit: e7a776a04ef6ed5e287a33cfdc36aa2d72862b55
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/29/2019
ms.locfileid: "30999123"
---
# <a name="protect-sharepoint-online-files-with-azure-information-protection"></a><span data-ttu-id="1bcdb-103">Protección de archivos de SharePoint Online con Azure Information Protection</span><span class="sxs-lookup"><span data-stu-id="1bcdb-103">Protect SharePoint Online files with Azure Information Protection</span></span>

 <span data-ttu-id="1bcdb-104">**Resumen:** Aplique Azure Information Protection para proteger los archivos en un sitio de grupo de SharePoint Online altamente confidencial.</span><span class="sxs-lookup"><span data-stu-id="1bcdb-104">**Summary:** Apply Azure Information Protection to protect files in a highly confidential SharePoint Online team site.</span></span>
  
<span data-ttu-id="1bcdb-p101">Siga los pasos de este artículo para configurar Azure Information Protection para proporcionar cifrado y permisos para archivos. Estos archivos pueden agregarse a una biblioteca de SharePoint configurada para protección altamente confidencial. O bien, puede abrir un archivo directamente desde el sitio y usar al cliente de Azure Information Protection para agregar el cifrado. La protección mediante cifrado y permisos viaja con un archivo, incluso cuando se descarga desde el sitio.</span><span class="sxs-lookup"><span data-stu-id="1bcdb-p101">Use the steps in this article to configure Azure Information Protection to provide encryption and permissions for files. These files can be added to a SharePoint library configured for highly confidential protection. Or, you can open a file directly from the site and use the Azure Information Protection client to add encryption. The encryption and permissions protection travels with a file even when it is downloaded from the site.</span></span> 

<span data-ttu-id="1bcdb-p102">Estos pasos son parte de una solución más grande para la configuración de protección confidencial para sitios de SharePoint y los archivos de estos sitios. Para obtener más información, consulte [Protección de archivos y sitios de SharePoint Online](secure-sharepoint-online-sites-and-files.md).</span><span class="sxs-lookup"><span data-stu-id="1bcdb-p102">These steps are part of a larger solution for configuring highly confidential protection for SharePoint sites and the files within these sites. For more information, see [Secure SharePoint Online sites and files](secure-sharepoint-online-sites-and-files.md).</span></span> 

<span data-ttu-id="1bcdb-111">Usar Azure Information Protection para los archivos de SharePoint Online no es recomendable para todos los clientes, pero es una opción para aquellos que necesitan este nivel de protección de un subconjunto de archivos.</span><span class="sxs-lookup"><span data-stu-id="1bcdb-111">Using Azure Information Protection for files in SharePoint Online is not recommended for all customers, but is an option for customers who need this level of protection for a subset of files.</span></span>

<span data-ttu-id="1bcdb-112">Algunas notas importantes sobre esta solución:</span><span class="sxs-lookup"><span data-stu-id="1bcdb-112">Some important notes about this solution:</span></span>
- <span data-ttu-id="1bcdb-p103">Cuando se aplica el cifrado de Azure Information Protection a los archivos almacenados en Office 365, el servicio no puede procesar el contenido de estos archivos. No funcionan algunas características de colaboración, como la coautoría, eDiscovery, la búsqueda y Delve. Las directivas de prevención de pérdida de datos (DLP) solo pueden trabajar con los metadatos (incluidas las etiquetas de Office 365), pero no con el contenido de estos archivos (por ejemplo, números de tarjeta de crédito incluidos en los archivos).</span><span class="sxs-lookup"><span data-stu-id="1bcdb-p103">When Azure Information Protection encryption is applied to files stored in Office 365, the service cannot process the contents of these files. Co-authoring, eDiscovery, search, Delve, and other collaborative features do not work. Data Loss Prevention (DLP) policies can only work with the metadata (including Office 365 labels) but not the contents of these files (such as credit card numbers within files).</span></span>

- <span data-ttu-id="1bcdb-p104">Esta solución requiere que un usuario seleccione la etiqueta que aplica la protección de Azure Information Protection. Si necesita cifrado automático y que SharePoint sea capaz de indexar y comprobar los archivos, puede usar Information Rights Management (IRM) en SharePoint Online. Al configurar una biblioteca de SharePoint para IRM, los archivos se cifrarán automáticamente cuando se descarguen para su edición. IRM de SharePoint incluye limitaciones que podrían influir en su decisión. Para obtener más información, consulte [Configurar Information Rights Management (IRM) en el Centro de administración de SharePoint](https://support.office.com/article/Set-up-Information-Rights-Management-IRM-in-SharePoint-admin-center-239CE6EB-4E81-42DB-BF86-A01362FED65C).</span><span class="sxs-lookup"><span data-stu-id="1bcdb-p104">This solution requires a user to select a label that applies the protection from Azure Information Protection. If you require automatic encryption and the ability for SharePoint to index and inspect the files, consider using Information Rights Management (IRM) in SharePoint Online. When you configure a SharePoint library for IRM, files are automatically encrypted when they are downloaded for editing.  SharePoint IRM includes limitations that might influence your decision. For more information, see [Set up Information Rights Management (IRM) in SharePoint admin center](https://support.office.com/article/Set-up-Information-Rights-Management-IRM-in-SharePoint-admin-center-239CE6EB-4E81-42DB-BF86-A01362FED65C).</span></span>

## <a name="admin-setup"></a><span data-ttu-id="1bcdb-121">Configuración de administración</span><span class="sxs-lookup"><span data-stu-id="1bcdb-121">Admin setup</span></span>
<span data-ttu-id="1bcdb-122">Primero, siga las instrucciones que se indican en [Activar Azure RMS desde el Centro de administración de Microsoft 365](https://docs.microsoft.com/information-protection/deploy-use/activate-office365) para su suscripción de Office 365.</span><span class="sxs-lookup"><span data-stu-id="1bcdb-122">First, use the instructions in [Activate Azure RMS with the Office 365 admin center](https://docs.microsoft.com/information-protection/deploy-use/activate-office365) for your Office 365 subscription.</span></span>
  
<span data-ttu-id="1bcdb-123">Después, siga estos pasos para configurar Azure Information Protection con una nueva directiva con ámbito y una subetiqueta para la protección y los permisos relacionados con el sitio de grupo de SharePoint Online altamente confidencial.</span><span class="sxs-lookup"><span data-stu-id="1bcdb-123">Next, configure Azure Information Protection with a new scoped policy and sub-label for protection and permissions of your highly confidential SharePoint Online team site.</span></span>
  
1. <span data-ttu-id="1bcdb-124">Inicie sesión en el centro de administración con una cuenta que tenga el rol de Administrador de seguridad o Administrador de la compañía.</span><span class="sxs-lookup"><span data-stu-id="1bcdb-124">Sign in to the Office 365 portal with an account that has the Security Administrator or Company Administrator role.</span></span> <span data-ttu-id="1bcdb-125">Para obtener ayuda, vea [Where to sign in to Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4) (Dónde iniciar sesión en Office 365).</span><span class="sxs-lookup"><span data-stu-id="1bcdb-125">For help, see [Where to sign in to Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>
    
2. <span data-ttu-id="1bcdb-126">En una pestaña independiente del explorador, vaya a Azure Portal ([https://portal.azure.com](https://portal.azure.com)).</span><span class="sxs-lookup"><span data-stu-id="1bcdb-126">In a separate tab of your browser, go to the Azure portal ([https://portal.azure.com](https://portal.azure.com)).</span></span>
    
3. <span data-ttu-id="1bcdb-127">Si es la primera vez que configura Azure Information Protection, vea [estas instrucciones](https://docs.microsoft.com/information-protection/deploy-use/configure-policy#to-access-the-azure-information-protection-blade-for-the-first-time).</span><span class="sxs-lookup"><span data-stu-id="1bcdb-127">If this is the first time you are configuring Azure Information Protection, see these [instructions](https://docs.microsoft.com/information-protection/deploy-use/configure-policy#to-access-the-azure-information-protection-blade-for-the-first-time).</span></span>

4. <span data-ttu-id="1bcdb-128">En el panel de lista, haga clic en **Más servicios**, escriba **information** y haga clic en **Azure Information Protection**.</span><span class="sxs-lookup"><span data-stu-id="1bcdb-128">In the list pane, click **All services**, type **information**, and then click **Azure Information Protection**.</span></span>

5. <span data-ttu-id="1bcdb-129">Haga clic en **Etiquetas**.</span><span class="sxs-lookup"><span data-stu-id="1bcdb-129">Click **Labels**.</span></span>
    
6. <span data-ttu-id="1bcdb-130">Haga clic con el botón derecho en la etiqueta **Extremadamente confidencial** y después seleccione **Agregar una subetiqueta**.</span><span class="sxs-lookup"><span data-stu-id="1bcdb-130">Right-click the **Highly Confidential** label, and then click **Add a sub-label**.</span></span>
    
7. <span data-ttu-id="1bcdb-131">Escriba un nombre para la subetiqueta en **Nombre** y una descripción de la subetiqueta en **Descripción**.</span><span class="sxs-lookup"><span data-stu-id="1bcdb-131">Type a name for the sub-label in **Name** and a description of the sub-label in **Description**.</span></span>
    
8. <span data-ttu-id="1bcdb-132">En **Establecer permisos para documentos y correos electrónicos que contengan esta etiqueta**, haga clic en **Proteger**.</span><span class="sxs-lookup"><span data-stu-id="1bcdb-132">In **Set permissions for documents and emails containing this label**, click **Protect**.</span></span>
    
9. <span data-ttu-id="1bcdb-133">En la sección **Protección**, haga clic en **Azure (clave de nube)**.</span><span class="sxs-lookup"><span data-stu-id="1bcdb-133">In the **Protection** section, click **Azure (cloud key)**.</span></span>
    
10. <span data-ttu-id="1bcdb-134">En la hoja **Protección**, en **Configuración de protección**, haga clic en **Agregar permisos**.</span><span class="sxs-lookup"><span data-stu-id="1bcdb-134">On the **Protection** blade, under **Protection settings**, click **Add permissions**.</span></span>
    
11. <span data-ttu-id="1bcdb-135">En la hoja **Agregar permisos**, en **Especificar usuarios y grupos**, haga clic en **Examinar directorio**.</span><span class="sxs-lookup"><span data-stu-id="1bcdb-135">On the **Add permissions** blade, under **Specify users and groups**, click **Browse directory**.</span></span>
    
12. <span data-ttu-id="1bcdb-136">En el panel **Usuarios y grupos de AAD**, seleccione el grupo de acceso de miembros del sitio para el sitio de grupo de SharePoint Online extremadamente confidencial y haga clic en **Seleccionar**.</span><span class="sxs-lookup"><span data-stu-id="1bcdb-136">On the **AAD Users and Groups** pane, select the site members access group for your highly sensitive SharePoint Online team site, and then click **Select**.</span></span>
    
13. <span data-ttu-id="1bcdb-137">En **Seleccionar permisos del conjunto predefinido o personalizado**, haga clic en **Personalizar** y después active las casillas **Ver derechos**, **Editar contenido**, **Guardar**, **Responder** y **Responder a todos**.</span><span class="sxs-lookup"><span data-stu-id="1bcdb-137">Under **Choose permissions from the preset or set custom**, click **Custom**, and then click the **View Rights**, **Edit Content**, **Save**, **Reply**, and **Reply all** check boxes.</span></span>
    
14. <span data-ttu-id="1bcdb-138">Haga clic en **Aceptar** dos veces.</span><span class="sxs-lookup"><span data-stu-id="1bcdb-138">Click **OK** twice.</span></span>
    
15. <span data-ttu-id="1bcdb-139">En la hoja **Subetiqueta**, haga clic en **Guardar** y, después, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="1bcdb-139">On the **Sub-label** blade, click **Save**, and then click **OK**.</span></span>

16. <span data-ttu-id="1bcdb-140">En la hoja **Azure Information Protection**, haga clic en **Directivas > + Agregar una directiva**.</span><span class="sxs-lookup"><span data-stu-id="1bcdb-140">On the **Azure Information protection** blade, click **Policies > + Add a new policy**.</span></span>
    
17. <span data-ttu-id="1bcdb-141">Escriba un nombre de la nueva directiva en **Nombre de la directiva** y una descripción en **Descripción**.</span><span class="sxs-lookup"><span data-stu-id="1bcdb-141">Type a name for the new policy in **Policy name** and a description in **Description**.</span></span>
    
18. <span data-ttu-id="1bcdb-142">Haga clic en **Seleccionar a qué usuarios o grupos se aplica esta directiva > Usuarios o grupos** y, luego, seleccione el grupo de acceso de los miembros del sitio para su sitio de grupo de SharePoint Online extremadamente confidencial.</span><span class="sxs-lookup"><span data-stu-id="1bcdb-142">Click **Select which users or groups get this policy > User/Groups**, and then select the site members access group for your highly sensitive SharePoint Online team site.</span></span>
    
19. <span data-ttu-id="1bcdb-143">Haga clic en **Seleccionar > Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="1bcdb-143">Click **Select > OK**.</span></span>

20. <span data-ttu-id="1bcdb-p106">Haga clic en **Agregar o quitar etiquetas**. En el panel **Directiva: Agregar o quitar etiquetas**, haga clic en el nombre de la nueva subetiqueta y, después, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="1bcdb-p106">Click **Add or remove labels**. In the **Policy: Add or remove labels** pane, click the name of your new sub-label, and then click **OK**.</span></span>   

21. <span data-ttu-id="1bcdb-146">Haga clic en **Guardar**y después en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="1bcdb-146">Click **Save**, and then click **OK**.</span></span>
 
## <a name="client-setup"></a><span data-ttu-id="1bcdb-147">Instalación del cliente</span><span class="sxs-lookup"><span data-stu-id="1bcdb-147">Client setup</span></span>
<span data-ttu-id="1bcdb-148">Ya está listo para empezar a crear documentos y protegerlos con Azure Information Protection y su nueva etiqueta.</span><span class="sxs-lookup"><span data-stu-id="1bcdb-148">You are now ready to begin creating documents and protecting them with Azure Information Protection and your new label.</span></span>
  
<span data-ttu-id="1bcdb-p107">Necesita [instalar el cliente de Azure Information Protection](https://docs.microsoft.com/information-protection/rms-client/install-client-app) en el dispositivo o equipo basado en Windows. Puede generar scripts y automatizar la instalación, o bien los usuarios pueden instalar el cliente de forma manual. Vea los recursos siguientes:</span><span class="sxs-lookup"><span data-stu-id="1bcdb-p107">You must [install the Azure Information Protection client](https://docs.microsoft.com/information-protection/rms-client/install-client-app) on your device or Windows-based computer. You can script and automate the installation, or users can install the client manually. See the following resources:</span></span>
  
- [<span data-ttu-id="1bcdb-152">El lado cliente de Azure Information Protection</span><span class="sxs-lookup"><span data-stu-id="1bcdb-152">The client side of Azure Information Protection</span></span>](https://docs.microsoft.com/information-protection/rms-client/use-client)
    
- [<span data-ttu-id="1bcdb-153">Instalación del cliente de Azure Information Protection</span><span class="sxs-lookup"><span data-stu-id="1bcdb-153">Installing the Azure Information Protection client</span></span>](https://docs.microsoft.com/information-protection/rms-client/client-admin-guide)
    
- [<span data-ttu-id="1bcdb-154">Página de descarga para la instalación manual</span><span class="sxs-lookup"><span data-stu-id="1bcdb-154">Download page for manual installation</span></span>](https://www.microsoft.com/download/details.aspx?id=53018)
    
<span data-ttu-id="1bcdb-p108">Cuando se complete la instalación, los usuarios ejecutarán y, después, iniciarán sesión desde una aplicación de Office (como Microsoft Word) con su cuenta de Office 365. Una nueva barra de **Information Protection** permite a los usuarios seleccionar la nueva etiqueta. Asegúrese de que los usuarios conozcan el sitio de grupo de SharePoint Online y la etiqueta que necesitan usar para proteger sus archivos altamente confidenciales.</span><span class="sxs-lookup"><span data-stu-id="1bcdb-p108">Once installed, your users run and then sign-in from an Office application (such as Microsoft Word) with their Office 365 account. A new **Information Protection** bar allows users to select the new label. Make sure that your users know the SharePoint Online team site and which label to use, to protect their highly confidential files.</span></span>
  
> [!NOTE]
> <span data-ttu-id="1bcdb-158">Si tiene varios sitios de grupo de SharePoint Online extremadamente confidenciales, deberá crear varias directivas con ámbito de Azure Information Protection que contengan subetiquetas con la configuración anterior, con los permisos de cada subetiqueta establecidos en el grupo de acceso de miembros de sitio de un equipo de grupo concreto de SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="1bcdb-158">If you have multiple highly sensitive SharePoint Online team sites, you should create multiple Azure Information Protection scoped policies with sub-labels with the above settings, with the permissions for each sub-label set to the site members access group of a specific SharePoint Online team site.</span></span> 
  
## <a name="adding-permissions-for-external-users"></a><span data-ttu-id="1bcdb-159">Agregar permisos para usuarios externos</span><span class="sxs-lookup"><span data-stu-id="1bcdb-159">Adding permissions for external users</span></span>
<span data-ttu-id="1bcdb-p109">Hay dos maneras de conceder a los usuarios externos el acceso a archivos protegidos con Azure Information Protection. En ambos casos, los usuarios externos necesitan tener una cuenta de Azure AD. Si los usuarios externos no son miembros de una organización que usa Azure AD, pueden obtener una cuenta de Azure AD como usuario individual a través de esta página de suscripción: [https://aka.ms/aip-signup](https://aka.ms/aip-signup).</span><span class="sxs-lookup"><span data-stu-id="1bcdb-p109">There are two ways you can grant external users access to files protected with Azure Information Protection. In both cases, external users must have an Azure AD account. If external users aren't members of an organization that uses Azure AD, they can obtain an Azure AD account as an individual by using this signup page: [https://aka.ms/aip-signup](https://aka.ms/aip-signup).</span></span>

 - <span data-ttu-id="1bcdb-163">Agregar usuarios externos a un grupo de Azure AD que se usa para configurar la protección de una etiqueta.</span><span class="sxs-lookup"><span data-stu-id="1bcdb-163">Add external users to an Azure AD group that is used to configure protection for a label</span></span> <span data-ttu-id="1bcdb-164">Primero debe agregar la cuenta como un usuario B2B en el directorio.</span><span class="sxs-lookup"><span data-stu-id="1bcdb-164">You’ll need to first add the account as a B2B user in your directory.</span></span> <span data-ttu-id="1bcdb-165">Puede que el [almacenamiento en caché de pertenencia al grupo de Azure Rights Management](https://docs.microsoft.com/azure/information-protection/plan-design/prepare#group-membership-caching-by-azure-information-protection) tarde un par de horas.</span><span class="sxs-lookup"><span data-stu-id="1bcdb-165">It can take a couple of hours for [group membership caching by Azure Rights Management](https://docs.microsoft.com/azure/information-protection/plan-design/prepare#group-membership-caching-by-azure-information-protection).</span></span>  
 - <span data-ttu-id="1bcdb-p111">Agregar usuarios externos directamente a la protección de etiqueta. Puede agregar todos los usuarios de una organización (por ejemplo, Fabrikam.com), un usuario o un grupo de Azure AD (como un grupo de finanzas dentro de una organización). Puede agregar, por ejemplo, un grupo de reguladores externo para la protección de una etiqueta.</span><span class="sxs-lookup"><span data-stu-id="1bcdb-p111">Add external users directly to the label protection. You can add all users from an organization (e.g. Fabrikam.com), an Azure AD group (such as a finance group within an organization), or user. For example, you can add an external team of regulators to the protection for a label.</span></span>

## <a name="see-also"></a><span data-ttu-id="1bcdb-169">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1bcdb-169">See Also</span></span>

[<span data-ttu-id="1bcdb-170">Protección de archivos y sitios de SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="1bcdb-170">Secure SharePoint Online sites and files</span></span>](secure-sharepoint-online-sites-and-files.md)
  
[<span data-ttu-id="1bcdb-171">Instrucciones de seguridad de Microsoft para campañas políticas, organizaciones sin ánimo de lucro y otras organizaciones ágiles</span><span class="sxs-lookup"><span data-stu-id="1bcdb-171">Microsoft Security Guidance for Political Campaigns, Nonprofits, and Other Agile Organizations</span></span>](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md)
  
[<span data-ttu-id="1bcdb-172">Adopción de la nube y soluciones híbridas</span><span class="sxs-lookup"><span data-stu-id="1bcdb-172">Cloud adoption and hybrid solutions</span></span>](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)
