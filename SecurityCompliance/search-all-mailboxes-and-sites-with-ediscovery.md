---
title: Buscar en todos los buzones y sitios con el Centro de exhibición de documentos electrónicos
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 12/30/2016
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 56e2978f-71b6-4141-b769-ad856d31bbec
description: En el centro de exhibición de documentos electrónicos en Office 365, puede buscar todos los buzones de Exchange Online, sitios de SharePoint Online y OneDrive para sitios de negocio en una búsqueda de exhibición de documentos electrónicos único. Para buscar todos los orígenes de contenido en la organización, un administrador de exhibición de documentos electrónicos debe tener asignado los permisos de exhibición de documentos electrónicos adecuados para cada origen de contenido.
ms.openlocfilehash: b3508d5929ca2b5b7a937eb2dccf677a2968cbbc
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22536037"
---
# <a name="search-all-mailboxes-and-sites-using-the-ediscovery-center"></a><span data-ttu-id="f44cb-104">Buscar en todos los buzones y sitios con el Centro de exhibición de documentos electrónicos</span><span class="sxs-lookup"><span data-stu-id="f44cb-104">Search all mailboxes and sites using the eDiscovery Center</span></span>

<span data-ttu-id="f44cb-p102">En el centro de exhibición de documentos electrónicos en Office 365, puede buscar todos los buzones de Exchange Online, sitios de SharePoint Online y OneDrive para sitios de negocio en una búsqueda de exhibición de documentos electrónicos único. Para buscar todos los orígenes de contenido en la organización, un administrador de exhibición de documentos electrónicos debe tener asignado los permisos de exhibición de documentos electrónicos adecuados para cada origen de contenido.</span><span class="sxs-lookup"><span data-stu-id="f44cb-p102">In the eDiscovery Center in Office 365, you can search all Exchange Online mailboxes, SharePoint Online sites, and OneDrive for Business sites in a single eDiscovery search. To search all content sources in the organization, an eDiscovery manager must be assigned the appropriate eDiscovery permissions for each content source.</span></span> 
  
## <a name="before-you-begin"></a><span data-ttu-id="f44cb-107">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="f44cb-107">Before you begin</span></span>

- <span data-ttu-id="f44cb-p103">Un administrador de exhibición de documentos electrónicos debe tener asignados los permisos adecuados para buscar en un origen de contenido. Para obtener más información sobre cómo asignar permisos de exhibición de documentos electrónicos a buzones y sitios, vea lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f44cb-p103">An eDiscovery manager must be assigned the appropriate permissions to search a content source. For more information about assigning eDiscovery permissions to mailboxes and sites, see the following:</span></span> 
    
  - [<span data-ttu-id="f44cb-110">Asignar permisos de exhibición de documentos electrónicos en Exchange</span><span class="sxs-lookup"><span data-stu-id="f44cb-110">Assign eDiscovery permissions in Exchange</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=526886)
    
  - [<span data-ttu-id="f44cb-111">Asignar permisos de exhibición de documentos electrónicos en SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="f44cb-111">Assign eDiscovery permissions in SharePoint Online</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=526885)
    
  - [<span data-ttu-id="f44cb-112">Asignar permisos de eDiscovery a sitios de OneDrive para la Empresa</span><span class="sxs-lookup"><span data-stu-id="f44cb-112">Assign eDiscovery permissions to OneDrive for Business sites</span></span>](assign-permissions-to-onedrive-for-business-sites.md)
    
- <span data-ttu-id="f44cb-p104">Puede buscar un máximo de 10.000 buzones de correo y un número ilimitado de SharePoint Online y OneDrive para sitios de profesionales en una consulta de búsqueda de exhibición de documentos electrónicos único. Sin embargo, si especifica los sitios específicos que se va a buscar, el límite es de 100 sitios.</span><span class="sxs-lookup"><span data-stu-id="f44cb-p104">You can search a maximum of 10,000 mailboxes and an unlimited number of SharePoint Online and OneDrive for Business sites in a single eDiscovery search query. However, if you specify the specific sites to search, the limit is 100 sites.</span></span>
    
- <span data-ttu-id="f44cb-115">Vea la sección [obtener más información](search-all-mailboxes-and-sites-with-ediscovery.md#moreinfo) para obtener una descripción de los límites al ver los resultados al buscar en todos los buzones de correo y sitios.</span><span class="sxs-lookup"><span data-stu-id="f44cb-115">See the [More information](search-all-mailboxes-and-sites-with-ediscovery.md#moreinfo) section for a description of the limits when viewing the results when searching all mailboxes and sites.</span></span> 
    
- <span data-ttu-id="f44cb-116">Para obtener más información acerca de cómo crear consultas de búsqueda en el centro de exhibición de documentos electrónicos, vea [crear y consultas de exhibición de documentos electrónicos ejecución](https://go.microsoft.com/fwlink/p/?LinkID=404032).</span><span class="sxs-lookup"><span data-stu-id="f44cb-116">For more information about creating search queries in the eDiscovery Center, see [Create and run eDiscovery queries](https://go.microsoft.com/fwlink/p/?LinkID=404032).</span></span>
    
## <a name="search-all-locations"></a><span data-ttu-id="f44cb-117">Buscar en todas las ubicaciones</span><span class="sxs-lookup"><span data-stu-id="f44cb-117">Search all locations</span></span>

1. <span data-ttu-id="f44cb-118">En el Centro de exhibición de documentos electrónicos, abra el caso de exhibición de documentos electrónicos para el que desea ejecutar la consulta de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="f44cb-118">In the eDiscovery Center, open the eDiscovery case that you want to run the search query for.</span></span>
    
2. <span data-ttu-id="f44cb-119">En la **búsqueda y exportación**, haga clic en una consulta existente o haga clic en **nuevo elemento** para crear una nueva consulta de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="f44cb-119">Under **Search and Export**, click an existing query or click **New item** to create a new search query.</span></span> 
    
3. <span data-ttu-id="f44cb-120">En la página de consulta de búsqueda, en la sección **Orígenes**, haga clic en **Modificar ámbito de consulta**.</span><span class="sxs-lookup"><span data-stu-id="f44cb-120">On the search query page, in the **Sources** section, click **Modify Query Scope**.</span></span>
    
4. <span data-ttu-id="f44cb-121">En la página **Modificar ámbito de consulta**, haga clic en **Buscar en todo** y seleccione las ubicaciones de contenido en las cuales buscar.</span><span class="sxs-lookup"><span data-stu-id="f44cb-121">On the **Modify Query Scope** page, click **Search everything**, and select the content locations to search.</span></span>
    
  - <span data-ttu-id="f44cb-122">Seleccione **Exchange** para buscar todos los buzones.</span><span class="sxs-lookup"><span data-stu-id="f44cb-122">Select **Exchange** to search all mailboxes.</span></span> 
    
  - <span data-ttu-id="f44cb-123">Seleccione **SharePoint** para buscar todos los SharePoint Online y OneDrive sitios profesionales.</span><span class="sxs-lookup"><span data-stu-id="f44cb-123">Select **SharePoint** to search all SharePoint Online and OneDrive for Business sites.</span></span> 
    
  - <span data-ttu-id="f44cb-124">Seleccione **Exchange** y **SharePoint** para buscar todas las ubicaciones de contenido en su organización.</span><span class="sxs-lookup"><span data-stu-id="f44cb-124">Select both **Exchange** and **SharePoint** to search all content locations in your organization.</span></span> 
    
![Buscar en todos los buzones de correo y sitios](media/e1f919ab-5596-43bb-a3c9-626cd41067b3.gif)
  
5. <span data-ttu-id="f44cb-126">Haga clic en **Aceptar** para guardar los cambios.</span><span class="sxs-lookup"><span data-stu-id="f44cb-126">Click **OK** to save the changes.</span></span> 
    
6. <span data-ttu-id="f44cb-p105">Complete o revise más información en la página de consulta de búsqueda, como la consulta de palabras clave, el intervalo de fechas o restringir los tipos específicos de contenido para buscar. Cuando esté listo para ejecutar la consulta, haga clic en **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="f44cb-p105">Complete or revise other information on the search query page, such as the keyword query, the date range, or narrowing the specific types of content to search for. When you're ready to run the query, click **Search**.</span></span> 
    
## <a name="more-information"></a><span data-ttu-id="f44cb-129">Más información</span><span class="sxs-lookup"><span data-stu-id="f44cb-129">More information</span></span>
<span data-ttu-id="f44cb-130"><a name="moreinfo"> </a></span><span class="sxs-lookup"><span data-stu-id="f44cb-130"></span></span>

- <span data-ttu-id="f44cb-131">Los 500 buzones principales y los 500 sitios principales con más resultados se muestran en **Orígenes** en la página **Consulta**.</span><span class="sxs-lookup"><span data-stu-id="f44cb-131">The top 500 mailboxes and the top 500 sites with the most results are listed under **Sources** on the **Query** page.</span></span> 
    
- <span data-ttu-id="f44cb-132">Se muestran el número total de elementos encontrados en todos los orígenes de contenido y su tamaño total combinado en **Orígenes** en la página **Consulta**. 
</span><span class="sxs-lookup"><span data-stu-id="f44cb-132">The total number of items found in all content sources and their combined total size are displayed under **Sources** on the **Query** page.</span></span> 
    
- <span data-ttu-id="f44cb-133">Puede obtener una vista previa de los 200 resultados de búsqueda más recientes ubicados en buzones de Exchange o sitios de SharePoint en la página **Consulta**.</span><span class="sxs-lookup"><span data-stu-id="f44cb-133">You can preview the 200 most recent search results located in Exchange mailboxes or SharePoint sites on the **Query** page.</span></span> 
    
    <span data-ttu-id="f44cb-134">La captura de pantalla siguiente muestra un ejemplo de los resultados de búsqueda que aparecen en la página **Consulta** cuando se busca en todos los sitios y buzones.</span><span class="sxs-lookup"><span data-stu-id="f44cb-134">The following screenshot shows an example of the search results displayed on the **Query** page when you search all mailboxes and sites.</span></span> 
    
    ![Captura de pantalla de resultados al buscar en todas las ubicaciones](media/4bf430f6-41ab-4bf6-afa9-33c3f6fd8b16.gif)
  

