---
title: 'Centro de administración de Exchange en Exchange Online Protection  '
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 12/09/2016
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 97921f0e-832f-40c7-b56d-414faede5191
ms.collection:
- M365-security-compliance
description: El Centro de administración de Exchange (EAC) es la consola de administración basada en web para Microsoft Exchange Online Protection (EOP).
ms.openlocfilehash: 9d32e6bfc9137a04d92c3916894e2070313607a8
ms.sourcegitcommit: 32ecff689ae32c59a39b7633ca0f36a304e7516e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/09/2019
ms.locfileid: "35599516"
---
# <a name="exchange-admin-center-in-exchange-online-protection"></a><span data-ttu-id="6c75c-103">Centro de administración de Exchange en Exchange Online Protection </span><span class="sxs-lookup"><span data-stu-id="6c75c-103">Exchange admin center in Exchange Online Protection</span></span> 

<span data-ttu-id="6c75c-104">El Centro de administración de Exchange (EAC) es la consola de administración basada en web para Microsoft Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="6c75c-104">The Exchange admin center (EAC) is the web-based management console for Microsoft Exchange Online Protection (EOP).</span></span> 
  
<span data-ttu-id="6c75c-p101">¿Está buscando la versión de Exchange 2013 de este tema? Vea [Exchange admin center in Exchange 2013](http://technet.microsoft.com/library/a9aea11a-6ba3-4f4a-a76e-79072e7cfc7d.aspx).</span><span class="sxs-lookup"><span data-stu-id="6c75c-p101">Looking for the Exchange 2013 version of this topic? See [Exchange admin center in Exchange 2013](http://technet.microsoft.com/library/a9aea11a-6ba3-4f4a-a76e-79072e7cfc7d.aspx).</span></span>
  
<span data-ttu-id="6c75c-p102">¿Está buscando la versión de Exchange Online de este tema? Vea [Exchange admin center in Exchange Online](https://docs.microsoft.com/exchange/exchange-admin-center).</span><span class="sxs-lookup"><span data-stu-id="6c75c-p102">Looking for the Exchange Online version of this topic? See [Exchange admin center in Exchange Online](https://docs.microsoft.com/exchange/exchange-admin-center).</span></span>
  
## <a name="accessing-the-eac"></a><span data-ttu-id="6c75c-109">Acceso a EAC</span><span class="sxs-lookup"><span data-stu-id="6c75c-109">Accessing the EAC</span></span>

<span data-ttu-id="6c75c-110">En la mayoría de los casos, los clientes de EOP obtendrán acceso al EAC a través del centro de administración 365 de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="6c75c-110">In most cases, EOP customers will access the EAC through the Microsoft 365 admin center.</span></span> <span data-ttu-id="6c75c-111">Encontrará un vínculo a EOP en el menú desplegable del icono **Administrador**, que está al lado del icono **Yo**.</span><span class="sxs-lookup"><span data-stu-id="6c75c-111">You can find a link to EOP in the drop-down menu in the **Admin** tile, which is next to the **Me** tile.</span></span> <span data-ttu-id="6c75c-112">Haga clic en el icono **Administrador** y seleccione **Protección en línea de Exchange** en el menú desplegable para ir al EAC.</span><span class="sxs-lookup"><span data-stu-id="6c75c-112">Click the **Admin** tile and select **Exchange Online Protection** from the drop down menu to be taken to the EAC.</span></span> 
  
<span data-ttu-id="6c75c-p104">You can also access the EAC sign in page directly via the following URL: https://admin.protection.outlook.com/ecp/\<companydomain\>. For example, https://admin.protection.outlook.com/ecp/contoso.onmicrosoft.com. After specifying your user credentials you will be taken directly into the EAC.</span><span class="sxs-lookup"><span data-stu-id="6c75c-p104">You can also access the EAC sign in page directly via the following URL: https://admin.protection.outlook.com/ecp/\<companydomain\>. For example, https://admin.protection.outlook.com/ecp/contoso.onmicrosoft.com. After specifying your user credentials you will be taken directly into the EAC.</span></span>
  
## <a name="common-user-interface-elements-in-the-eac"></a><span data-ttu-id="6c75c-116">Elementos comunes de la interfaz de usuario en EAC</span><span class="sxs-lookup"><span data-stu-id="6c75c-116">Common user interface elements in the EAC</span></span>

<span data-ttu-id="6c75c-117">En esta sección se describen los elementos de la interfaz de usuario del EAC.</span><span class="sxs-lookup"><span data-stu-id="6c75c-117">This section describes the user interface elements that are found in the EAC.</span></span>
  
![EOP: AdminCenter](media/EOP-AdminCenter.png)
  
### <a name="feature-pane"></a><span data-ttu-id="6c75c-119">Panel de características</span><span class="sxs-lookup"><span data-stu-id="6c75c-119">Feature Pane</span></span>

<span data-ttu-id="6c75c-p105">Este es el primer nivel de navegación para la mayoría de las tareas que realizará en el EAC. El panel de características se organiza por áreas.</span><span class="sxs-lookup"><span data-stu-id="6c75c-p105">This is the first level of navigation for most of the tasks you'll perform in the EAC. The feature pane is organized by feature areas.</span></span>
  
1. <span data-ttu-id="6c75c-122">**Destinatarios** Aquí es donde se muestran los usuarios internos y los contactos externos.</span><span class="sxs-lookup"><span data-stu-id="6c75c-122">**Recipients** This is where you'll view internal users and external contacts.</span></span> 
    
2. <span data-ttu-id="6c75c-123">**Permisos** Aquí es donde se administran los roles de administrador.</span><span class="sxs-lookup"><span data-stu-id="6c75c-123">**Permissions** This where you'll manage administrator roles.</span></span> 
    
3. <span data-ttu-id="6c75c-124">**Administración de cumplimiento** Aquí es donde se encuentran los registros de auditoría y los informes, como el informe de grupos de roles de administrador.</span><span class="sxs-lookup"><span data-stu-id="6c75c-124">**Compliance Management** This is where you'll find audit logs and reports, such as the administrator role group report.</span></span> 
    
4. <span data-ttu-id="6c75c-125">**Protección** En esta sección es donde se administra la protección antimalware y contra correo no deseado para la organización, así como los mensajes en cuarentena.</span><span class="sxs-lookup"><span data-stu-id="6c75c-125">**Protection** This is where you'll manage anti-malware and anti-spam protection for your organization, as well as manage messages in quarantine.</span></span> 
    
5. <span data-ttu-id="6c75c-126">**Flujo del correo** Aquí es donde se administran las reglas, los dominios aceptados y conectores, así como las ubicaciones en las que se realiza el seguimiento de mensajes.</span><span class="sxs-lookup"><span data-stu-id="6c75c-126">**Mail Flow** This is where you'll manage rules, accepted domains, and connectors, as well as where you'll go to perform message trace.</span></span> 
    
### <a name="tabs"></a><span data-ttu-id="6c75c-127">Pestañas</span><span class="sxs-lookup"><span data-stu-id="6c75c-127">Tabs</span></span>

<span data-ttu-id="6c75c-128">Las pestañas son el segundo nivel de navegación.</span><span class="sxs-lookup"><span data-stu-id="6c75c-128">The tabs are your second level of navigation.</span></span> <span data-ttu-id="6c75c-129">Las áreas de características contienen varias pestañas y cada área representa a una característica.</span><span class="sxs-lookup"><span data-stu-id="6c75c-129">Each of the feature areas contains various tabs, each representing a feature.</span></span>
  
### <a name="toolbar"></a><span data-ttu-id="6c75c-130">Barra de herramientas</span><span class="sxs-lookup"><span data-stu-id="6c75c-130">Toolbar</span></span>

<span data-ttu-id="6c75c-p107">Al hacer clic en la mayoría de las pestañas, verá una barra de herramientas. La barra de herramientas tiene iconos que realizan una acción específica. La siguiente tabla describe los iconos y sus acciones.</span><span class="sxs-lookup"><span data-stu-id="6c75c-p107">When you click most tabs, you'll see a toolbar. The toolbar has icons that perform a specific action. The following table describes the icons and their actions.</span></span>
  
|<span data-ttu-id="6c75c-134">**Icono**</span><span class="sxs-lookup"><span data-stu-id="6c75c-134">**Icon**</span></span>|<span data-ttu-id="6c75c-135">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="6c75c-135">**Name**</span></span>|<span data-ttu-id="6c75c-136">**Action**</span><span class="sxs-lookup"><span data-stu-id="6c75c-136">**Action**</span></span>|
|:-----|:-----|:-----|
|![Agregar icono](media/ITPro-EAC-AddIcon.gif)           <br/> |<span data-ttu-id="6c75c-138">Agregar, nuevo</span><span class="sxs-lookup"><span data-stu-id="6c75c-138">Add, New</span></span>  <br/> |<span data-ttu-id="6c75c-p108">Utilice este icono para crear un nuevo objeto. Algunos de estos iconos tienen una flecha hacia abajo asociada donde puede hacer clic para mostrar objetos adicionales que puede crear.</span><span class="sxs-lookup"><span data-stu-id="6c75c-p108">Use this icon to create a new object. Some of these icons have an associated down arrow you can click to show additional objects you can create.</span></span>  <br/> |
|![Icono Editar](media/ITPro-EAC-EditIcon.gif)           <br/> |<span data-ttu-id="6c75c-142">Editar</span><span class="sxs-lookup"><span data-stu-id="6c75c-142">Edit</span></span>  <br/> |<span data-ttu-id="6c75c-143">Utilice este icono para editar un objeto.</span><span class="sxs-lookup"><span data-stu-id="6c75c-143">Use this icon to edit an object.</span></span>  <br/> |
|![Eliminar icono](media/ITPro-EAC-DeleteIcon.gif)           <br/> |<span data-ttu-id="6c75c-145">Eliminar</span><span class="sxs-lookup"><span data-stu-id="6c75c-145">Delete</span></span>  <br/> |<span data-ttu-id="6c75c-p109">Utilice este icono para eliminar un objeto. Algunos iconos eliminados tienen una flecha hacia abajo donde puede hacer clic para mostrar opciones adicionales.</span><span class="sxs-lookup"><span data-stu-id="6c75c-p109">Use this icon to delete an object. Some delete icons have a down arrow you can click to show additional options.</span></span>  <br/> |
|![icono de Buscar](media/ITPro-EAC-.gif)           <br/> |<span data-ttu-id="6c75c-149">Búsqueda</span><span class="sxs-lookup"><span data-stu-id="6c75c-149">Search</span></span>  <br/> |<span data-ttu-id="6c75c-150">Usar este icono para abrir una casilla de búsqueda donde puede escribir una frase de búsqueda para el objeto que desee encontrar.</span><span class="sxs-lookup"><span data-stu-id="6c75c-150">Use this icon to open a search box in which you can type the search phrase for an object you want to find.</span></span>  <br/> |
|![Icono Actualizar](media/ITPro-EAC-RefreshIcon.gif)           <br/> |<span data-ttu-id="6c75c-152">Actualizar</span><span class="sxs-lookup"><span data-stu-id="6c75c-152">Refresh</span></span>  <br/> |<span data-ttu-id="6c75c-153">Utilice este icono para actualizar la vista de lista.</span><span class="sxs-lookup"><span data-stu-id="6c75c-153">Use this icon to refresh the list view.</span></span>  <br/> |
|![Icono Más opciones](media/ITPro-EAC-MoreOptionsIcon.gif)           <br/> |<span data-ttu-id="6c75c-155">Más opciones</span><span class="sxs-lookup"><span data-stu-id="6c75c-155">More options</span></span>  <br/> |<span data-ttu-id="6c75c-p110">Use este icono para ver más acciones que puede realizar para los objetos de la pestaña. Por ejemplo, al hacer clic en este icono en **Destinatarios \> Usuarios**, se muestra la opción para realizar una **Búsqueda avanzada**.  </span><span class="sxs-lookup"><span data-stu-id="6c75c-p110">Use this icon to view more actions you can perform for that tab's objects. For example, in **Recipients \> Users** clicking this icon shows the option to perform an **Advanced Search**.  </span></span><br/> |
|![Icono flecha arriba](media/ITPro-EAC-UpArrowIcon.gif)![Icono flecha abajo](media/ITPro-EAC-DownArrowIcon.gif)           <br/> |<span data-ttu-id="6c75c-160">Flecha hacia arriba y flecha hacia abajo</span><span class="sxs-lookup"><span data-stu-id="6c75c-160">Up arrow and down arrow</span></span>  <br/> |<span data-ttu-id="6c75c-161">Utilice estos iconos para mover la prioridad de un objeto hacia arriba o hacia abajo.</span><span class="sxs-lookup"><span data-stu-id="6c75c-161">Use these icons to move an object's priority up or down.</span></span>  <br/> |
|![Icono de quitar](media/ITPro-EAC-RemoveIcon.gif)           <br/> |<span data-ttu-id="6c75c-163">Quitar</span><span class="sxs-lookup"><span data-stu-id="6c75c-163">Remove</span></span>  <br/> |<span data-ttu-id="6c75c-164">Utilice este icono para quitar objetos de la lista.</span><span class="sxs-lookup"><span data-stu-id="6c75c-164">Use this icon to remove objects from a list.</span></span>  <br/> |
   
### <a name="list-view"></a><span data-ttu-id="6c75c-165">Vista de lista</span><span class="sxs-lookup"><span data-stu-id="6c75c-165">List View</span></span>

<span data-ttu-id="6c75c-p111">Cuando seleccione una pestaña, en la mayoría de los casos verá la vista de lista. El límite de visualización de la vista de lista del EAC es de 10.000 objetos aproximadamente. Además, la paginación se incluye para que pueda paginar los resultados.</span><span class="sxs-lookup"><span data-stu-id="6c75c-p111">When you select a tab, in most cases you'll see a list view. The viewable limit with the EAC list view is approximately 10,000 objects. In addition, paging is included so that you can page to results.</span></span>
  
### <a name="details-pane"></a><span data-ttu-id="6c75c-169">panel Detalles</span><span class="sxs-lookup"><span data-stu-id="6c75c-169">Details Pane</span></span>

<span data-ttu-id="6c75c-p112">Cuando seleccione un objeto de la vista de lista, la información acerca del objeto se muestra en el panel de detalles. En algunos casos, el panel de detalles incluye tareas de administración.</span><span class="sxs-lookup"><span data-stu-id="6c75c-p112">When you select an object from the list view, information about that object is displayed in the details pane. In some cases the details pane includes management tasks.</span></span>
  
### <a name="me-tile-and-help"></a><span data-ttu-id="6c75c-172">Mosaico Yo y Ayuda</span><span class="sxs-lookup"><span data-stu-id="6c75c-172">Me tile and Help</span></span>

<span data-ttu-id="6c75c-p113">El mosaico **Yo** permite cerrar sesión en el EAC e iniciar sesión como un usuario diferente. Desde el menú desplegable en **Ayuda**![Icono de ayuda](media/ITPro-EAC-HelpIcon.gif), puede realizar las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="6c75c-p113">The **Me** tile allows you to sign out the EAC and sign in as a different user. From the **Help**![Help Icon](media/ITPro-EAC-HelpIcon.gif) drop-down menu, you can perform the following actions:</span></span> 
  
1. <span data-ttu-id="6c75c-175">**Ayuda** Haga clic en ![Icono de ayuda](media/ITPro-EAC-HelpIcon.gif) para ver el contenido de la ayuda en línea.</span><span class="sxs-lookup"><span data-stu-id="6c75c-175">**Help** Click ![Help Icon](media/ITPro-EAC-HelpIcon.gif) to view the online help content.</span></span> 
    
2. <span data-ttu-id="6c75c-p114">**Deshabilitar el globo de Ayuda** El globo de Ayuda muestra la ayuda contextual de los campos cuando crea o edita un objeto. Puede desactivar el globo de Ayuda o activarlo si estaba deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="6c75c-p114">**Disable Help bubble** The Help bubble displays contextual help for fields when you create or edit an object. You can turn off the Help bubble or turn it on if it has been disabled.</span></span> 
    
3. <span data-ttu-id="6c75c-178">**Copyright** Haga clic en este vínculo para leer el aviso de derechos de autor de Exchange Online Protection.</span><span class="sxs-lookup"><span data-stu-id="6c75c-178">**Copyright** Click this link to read the copyright notice for Exchange Online Protection.</span></span> 
    
4. <span data-ttu-id="6c75c-179">**Privacidad** Haga clic para leer la directiva de privacidad de Exchange Online Protection.</span><span class="sxs-lookup"><span data-stu-id="6c75c-179">**Privacy** Click to read the privacy policy for Exchange Online Protection.</span></span> 
    
## <a name="supported-browsers"></a><span data-ttu-id="6c75c-180">Exploradores compatibles</span><span class="sxs-lookup"><span data-stu-id="6c75c-180">Supported Browsers</span></span>

<span data-ttu-id="6c75c-p115">Para conseguir la mejor experiencia con EAC, le recomendamos que use siempre la versión más actualizada de los exploradores, clientes de Office y aplicaciones. También le recomendamos que instale las actualizaciones de software cuando estén disponibles. Para obtener más información acerca de los navegadores compatibles y los requisitos del sistema para el servicio, vea [Requisitos del sistema de Office 365](https://go.microsoft.com/fwlink/p/?LinkID=402699).</span><span class="sxs-lookup"><span data-stu-id="6c75c-p115">For the best experience using the EAC, we recommend that you always use the latest browsers, Office clients, and apps. We also recommend that you install software updates when they become available. For more information about the supported browsers and system requirements for the service, see [Office 365 System Requirements](https://go.microsoft.com/fwlink/p/?LinkID=402699).</span></span> 
  
## <a name="supported-languages-in-eop"></a><span data-ttu-id="6c75c-184">Idiomas admitidos en EOP</span><span class="sxs-lookup"><span data-stu-id="6c75c-184">Supported languages in EOP</span></span>

<span data-ttu-id="6c75c-185">Los siguientes idiomas están disponibles y son compatibles con Exchange Online Protection.</span><span class="sxs-lookup"><span data-stu-id="6c75c-185">The following languages are supported and available for Exchange Online Protection.</span></span>
  
- <span data-ttu-id="6c75c-186">Amhárico</span><span class="sxs-lookup"><span data-stu-id="6c75c-186">Amharic</span></span>
    
- <span data-ttu-id="6c75c-187">Árabe</span><span class="sxs-lookup"><span data-stu-id="6c75c-187">Arabic</span></span>
    
- <span data-ttu-id="6c75c-188">Vasco (Euskera)</span><span class="sxs-lookup"><span data-stu-id="6c75c-188">Basque (Basque)</span></span>
    
- <span data-ttu-id="6c75c-189">Bengalí (India)</span><span class="sxs-lookup"><span data-stu-id="6c75c-189">Bengali (India)</span></span>
    
- <span data-ttu-id="6c75c-190">Búlgaro</span><span class="sxs-lookup"><span data-stu-id="6c75c-190">Bulgarian</span></span>
    
- <span data-ttu-id="6c75c-191">Catalán</span><span class="sxs-lookup"><span data-stu-id="6c75c-191">Catalan</span></span>
    
- <span data-ttu-id="6c75c-192">Chino (simplificado)</span><span class="sxs-lookup"><span data-stu-id="6c75c-192">Chinese (Simplified)</span></span>
    
- <span data-ttu-id="6c75c-193">Chino (tradicional)</span><span class="sxs-lookup"><span data-stu-id="6c75c-193">Chinese (Traditional)</span></span>
    
- <span data-ttu-id="6c75c-194">Croata</span><span class="sxs-lookup"><span data-stu-id="6c75c-194">Croatian</span></span>
    
- <span data-ttu-id="6c75c-195">Checo</span><span class="sxs-lookup"><span data-stu-id="6c75c-195">Czech</span></span>
    
- <span data-ttu-id="6c75c-196">Danés</span><span class="sxs-lookup"><span data-stu-id="6c75c-196">Danish</span></span>
    
- <span data-ttu-id="6c75c-197">Neerlandés</span><span class="sxs-lookup"><span data-stu-id="6c75c-197">Dutch</span></span>
    
- <span data-ttu-id="6c75c-198">Neerlandés</span><span class="sxs-lookup"><span data-stu-id="6c75c-198">Dutch</span></span>
    
- <span data-ttu-id="6c75c-199">Inglés</span><span class="sxs-lookup"><span data-stu-id="6c75c-199">English</span></span>
    
- <span data-ttu-id="6c75c-200">Estonio</span><span class="sxs-lookup"><span data-stu-id="6c75c-200">Estonian</span></span>
    
- <span data-ttu-id="6c75c-201">Filipino (Filipinas)</span><span class="sxs-lookup"><span data-stu-id="6c75c-201">Filipino (Philippines)</span></span>
    
- <span data-ttu-id="6c75c-202">Finés</span><span class="sxs-lookup"><span data-stu-id="6c75c-202">Finnish</span></span>
    
- <span data-ttu-id="6c75c-203">Francés</span><span class="sxs-lookup"><span data-stu-id="6c75c-203">French</span></span>
    
- <span data-ttu-id="6c75c-204">Gallego</span><span class="sxs-lookup"><span data-stu-id="6c75c-204">Galician</span></span>
    
- <span data-ttu-id="6c75c-205">Alemán</span><span class="sxs-lookup"><span data-stu-id="6c75c-205">German</span></span>
    
- <span data-ttu-id="6c75c-206">Griego</span><span class="sxs-lookup"><span data-stu-id="6c75c-206">Greek</span></span>
    
- <span data-ttu-id="6c75c-207">Gujarati</span><span class="sxs-lookup"><span data-stu-id="6c75c-207">Gujarati</span></span>
    
- <span data-ttu-id="6c75c-208">Hebreo</span><span class="sxs-lookup"><span data-stu-id="6c75c-208">Hebrew</span></span>
    
- <span data-ttu-id="6c75c-209">Hindi</span><span class="sxs-lookup"><span data-stu-id="6c75c-209">Hindi</span></span>
    
- <span data-ttu-id="6c75c-210">Húngaro</span><span class="sxs-lookup"><span data-stu-id="6c75c-210">Hungarian</span></span>
    
- <span data-ttu-id="6c75c-211">Islandés</span><span class="sxs-lookup"><span data-stu-id="6c75c-211">Icelandic</span></span>
    
- <span data-ttu-id="6c75c-212">Indonesio</span><span class="sxs-lookup"><span data-stu-id="6c75c-212">Indonesian</span></span>
    
- <span data-ttu-id="6c75c-213">Italiano</span><span class="sxs-lookup"><span data-stu-id="6c75c-213">Italian</span></span>
    
- <span data-ttu-id="6c75c-214">Japonés</span><span class="sxs-lookup"><span data-stu-id="6c75c-214">Japanese</span></span>
    
- <span data-ttu-id="6c75c-215">Kannada</span><span class="sxs-lookup"><span data-stu-id="6c75c-215">Kannada</span></span>
    
- <span data-ttu-id="6c75c-216">Kazajo</span><span class="sxs-lookup"><span data-stu-id="6c75c-216">Kazakh</span></span>
    
- <span data-ttu-id="6c75c-217">Kiswahili</span><span class="sxs-lookup"><span data-stu-id="6c75c-217">Kiswahili</span></span>
    
- <span data-ttu-id="6c75c-218">Coreano</span><span class="sxs-lookup"><span data-stu-id="6c75c-218">Korean</span></span>
    
- <span data-ttu-id="6c75c-219">Letón</span><span class="sxs-lookup"><span data-stu-id="6c75c-219">Latvian</span></span>
    
- <span data-ttu-id="6c75c-220">Lituano</span><span class="sxs-lookup"><span data-stu-id="6c75c-220">Lithuanian</span></span>
    
- <span data-ttu-id="6c75c-221">Malayo (Brunei Darussalam)</span><span class="sxs-lookup"><span data-stu-id="6c75c-221">Malay (Brunei Darussalam)</span></span>
    
- <span data-ttu-id="6c75c-222">Malayo (Malasia)</span><span class="sxs-lookup"><span data-stu-id="6c75c-222">Malay (Malaysia)</span></span>
    
- <span data-ttu-id="6c75c-223">Malayalam</span><span class="sxs-lookup"><span data-stu-id="6c75c-223">Malayalam</span></span>
    
- <span data-ttu-id="6c75c-224">Maratí</span><span class="sxs-lookup"><span data-stu-id="6c75c-224">Marathi</span></span>
    
- <span data-ttu-id="6c75c-225">Noruego (Bokmal)</span><span class="sxs-lookup"><span data-stu-id="6c75c-225">Norwegian (Bokmål)</span></span>
    
- <span data-ttu-id="6c75c-226">Noruego (Nynorsk)</span><span class="sxs-lookup"><span data-stu-id="6c75c-226">Norwegian (Nynorsk)</span></span>
    
- <span data-ttu-id="6c75c-227">Odia</span><span class="sxs-lookup"><span data-stu-id="6c75c-227">Oriya</span></span>
    
- <span data-ttu-id="6c75c-228">Persa</span><span class="sxs-lookup"><span data-stu-id="6c75c-228">Persian</span></span>
    
- <span data-ttu-id="6c75c-229">Polaco</span><span class="sxs-lookup"><span data-stu-id="6c75c-229">Polish</span></span>
    
- <span data-ttu-id="6c75c-230">Portugués (Brasil)</span><span class="sxs-lookup"><span data-stu-id="6c75c-230">Portuguese (Brazil)</span></span>
    
- <span data-ttu-id="6c75c-231">Portugués (Portugal)</span><span class="sxs-lookup"><span data-stu-id="6c75c-231">Portuguese (Portugal)</span></span>
    
- <span data-ttu-id="6c75c-232">Rumano</span><span class="sxs-lookup"><span data-stu-id="6c75c-232">Romanian</span></span>
    
- <span data-ttu-id="6c75c-233">Ruso</span><span class="sxs-lookup"><span data-stu-id="6c75c-233">Russian</span></span>
    
- <span data-ttu-id="6c75c-234">Serbio (cirílico, Serbia)</span><span class="sxs-lookup"><span data-stu-id="6c75c-234">Serbian (Cyrillic, Serbia)</span></span>
    
- <span data-ttu-id="6c75c-235">Serbio (latino)</span><span class="sxs-lookup"><span data-stu-id="6c75c-235">Serbian (Latin)</span></span>
    
- <span data-ttu-id="6c75c-236">Eslovaco</span><span class="sxs-lookup"><span data-stu-id="6c75c-236">Slovak</span></span>
    
- <span data-ttu-id="6c75c-237">Esloveno</span><span class="sxs-lookup"><span data-stu-id="6c75c-237">Slovenian</span></span>
    
- <span data-ttu-id="6c75c-238">Español</span><span class="sxs-lookup"><span data-stu-id="6c75c-238">Spanish</span></span>
    
- <span data-ttu-id="6c75c-239">Sueco</span><span class="sxs-lookup"><span data-stu-id="6c75c-239">Swedish</span></span>
    
- <span data-ttu-id="6c75c-240">Tamil</span><span class="sxs-lookup"><span data-stu-id="6c75c-240">Tamil</span></span>
    
- <span data-ttu-id="6c75c-241">Telugu</span><span class="sxs-lookup"><span data-stu-id="6c75c-241">Telugu</span></span>
    
- <span data-ttu-id="6c75c-242">Tailandés</span><span class="sxs-lookup"><span data-stu-id="6c75c-242">Thai</span></span>
    
- <span data-ttu-id="6c75c-243">Turco</span><span class="sxs-lookup"><span data-stu-id="6c75c-243">Turkish</span></span>
    
- <span data-ttu-id="6c75c-244">Ucraniano</span><span class="sxs-lookup"><span data-stu-id="6c75c-244">Ukrainian</span></span>
    
- <span data-ttu-id="6c75c-245">Urdu</span><span class="sxs-lookup"><span data-stu-id="6c75c-245">Urdu</span></span>
    
- <span data-ttu-id="6c75c-246">Vietnamita</span><span class="sxs-lookup"><span data-stu-id="6c75c-246">Vietnamese</span></span>
    
- <span data-ttu-id="6c75c-247">Galés</span><span class="sxs-lookup"><span data-stu-id="6c75c-247">Welsh</span></span>
    

