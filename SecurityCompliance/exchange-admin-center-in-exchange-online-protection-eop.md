---
title: 'Centro de administración de Exchange en Exchange Online Protection '
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/9/2016
ms.audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: 97921f0e-832f-40c7-b56d-414faede5191
description: El Centro de administración de Exchange (EAC) es la consola de administración basada en web para Microsoft Exchange Online Protection (EOP).
ms.openlocfilehash: 99640e561b41e47a74e7c22f0bbdcacd0dd80bd7
ms.sourcegitcommit: 22bca85c3c6d946083d3784f72e886c068d49f4a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/06/2018
ms.locfileid: "22026317"
---
# <a name="exchange-admin-center-in-exchange-online-protection"></a><span data-ttu-id="2eba6-103">Centro de administración de Exchange en Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="2eba6-103">Exchange admin center in Exchange Online Protection</span></span> 

<span data-ttu-id="2eba6-104">El Centro de administración de Exchange (EAC) es la consola de administración basada en web para Microsoft Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="2eba6-104">The Exchange admin center (EAC) is the web-based management console for Microsoft Exchange Online Protection (EOP).</span></span> 
  
<span data-ttu-id="2eba6-p101">¿Está buscando la versión de Exchange 2013 de este tema? Vea [Exchange admin center in Exchange 2013](http://technet.microsoft.com/library/a9aea11a-6ba3-4f4a-a76e-79072e7cfc7d.aspx).</span><span class="sxs-lookup"><span data-stu-id="2eba6-p101">Looking for the Exchange 2013 version of this topic? See [Exchange admin center in Exchange 2013](http://technet.microsoft.com/library/a9aea11a-6ba3-4f4a-a76e-79072e7cfc7d.aspx).</span></span>
  
<span data-ttu-id="2eba6-p102">¿Está buscando la versión de Exchange Online de este tema? Vea [Exchange admin center in Exchange Online](http://technet.microsoft.com/library/ace44f6b-4084-4f9c-89b3-e0317962472b.aspx).</span><span class="sxs-lookup"><span data-stu-id="2eba6-p102">Looking for the Exchange Online version of this topic? See [Exchange admin center in Exchange Online](http://technet.microsoft.com/library/ace44f6b-4084-4f9c-89b3-e0317962472b.aspx).</span></span>
  
## <a name="accessing-the-eac"></a><span data-ttu-id="2eba6-109">Acceso a EAC</span><span class="sxs-lookup"><span data-stu-id="2eba6-109">Accessing the EAC</span></span>

<span data-ttu-id="2eba6-p103">En la mayoría de los casos, los clientes de EOP obtienen acceso al EAC a través del Centro de administración de Office 365. Encontrará un vínculo a EOP en el menú desplegable del icono **Administrador**, que está al lado del icono **Yo**. Haga clic en el icono **Administrador** y seleccione **Protección en línea de Exchange** en el menú desplegable para ir al EAC.</span><span class="sxs-lookup"><span data-stu-id="2eba6-p103">In most cases, EOP customers will access the EAC through the Office 365 admin center. You can find a link to EOP in the drop-down menu in the **Admin** tile, which is next to the **Me** tile. Click the **Admin** tile and select **Exchange Online Protection** from the drop down menu to be taken to the EAC.</span></span> 
  
<span data-ttu-id="2eba6-p104">También puede obtener acceso a la página directamente a través de la siguiente dirección URL de inicio de sesión de CEF: https://admin.protection.outlook.com/ecp/\<companydomain\>. Por ejemplo, https://admin.protection.outlook.com/ecp/contoso.onmicrosoft.com. Después de especificar sus credenciales de usuario se le dirigirá directamente en el EAC.</span><span class="sxs-lookup"><span data-stu-id="2eba6-p104">You can also access the EAC sign in page directly via the following URL: https://admin.protection.outlook.com/ecp/\<companydomain\>. For example, https://admin.protection.outlook.com/ecp/contoso.onmicrosoft.com. After specifying your user credentials you will be taken directly into the EAC.</span></span>
  
## <a name="common-user-interface-elements-in-the-eac"></a><span data-ttu-id="2eba6-116">Elementos comunes de la interfaz de usuario en EAC</span><span class="sxs-lookup"><span data-stu-id="2eba6-116">Common user interface elements in the EAC</span></span>
<span data-ttu-id="2eba6-117"><a name="BKMK_CommonUserInterfaceElements"> </a></span><span class="sxs-lookup"><span data-stu-id="2eba6-117"></span></span>

<span data-ttu-id="2eba6-118">En esta sección se describen los elementos de la interfaz de usuario del EAC.</span><span class="sxs-lookup"><span data-stu-id="2eba6-118">This section describes the user interface elements that are found in the EAC.</span></span>
  
![AdminCenter de elevación de privilegios](media/EOP-AdminCenter.png)
  
### <a name="feature-pane"></a><span data-ttu-id="2eba6-120">Panel de características</span><span class="sxs-lookup"><span data-stu-id="2eba6-120">Feature Pane</span></span>

<span data-ttu-id="2eba6-p105">Este es el primer nivel de navegación para la mayoría de las tareas que realizará en el EAC. El panel de características se organiza por áreas.</span><span class="sxs-lookup"><span data-stu-id="2eba6-p105">This is the first level of navigation for most of the tasks you'll perform in the EAC. The feature pane is organized by feature areas.</span></span>
  
1. <span data-ttu-id="2eba6-123">**Destinatarios** Aquí es donde se muestran los usuarios internos y los contactos externos.</span><span class="sxs-lookup"><span data-stu-id="2eba6-123">**Recipients** This is where you'll view internal users and external contacts.</span></span> 
    
2. <span data-ttu-id="2eba6-124">**Permisos** Aquí es donde se administran los roles de administrador.</span><span class="sxs-lookup"><span data-stu-id="2eba6-124">**Permissions** This where you'll manage administrator roles.</span></span> 
    
3. <span data-ttu-id="2eba6-125">**Administración de cumplimiento** Aquí es donde se encuentran los registros de auditoría y los informes, como el informe de grupos de roles de administrador.</span><span class="sxs-lookup"><span data-stu-id="2eba6-125">**Compliance Management** This is where you'll find audit logs and reports, such as the administrator role group report.</span></span> 
    
4. <span data-ttu-id="2eba6-126">**Protección** En esta sección es donde se administra la protección antimalware y contra correo no deseado para la organización, así como los mensajes en cuarentena.</span><span class="sxs-lookup"><span data-stu-id="2eba6-126">**Protection** This is where you'll manage anti-malware and anti-spam protection for your organization, as well as manage messages in quarantine.</span></span> 
    
5. <span data-ttu-id="2eba6-127">**Flujo del correo** Aquí es donde se administran las reglas, los dominios aceptados y conectores, así como las ubicaciones en las que se realiza el seguimiento de mensajes.</span><span class="sxs-lookup"><span data-stu-id="2eba6-127">**Mail Flow** This is where you'll manage rules, accepted domains, and connectors, as well as where you'll go to perform message trace.</span></span> 
    
### <a name="tabs"></a><span data-ttu-id="2eba6-128">Fichas</span><span class="sxs-lookup"><span data-stu-id="2eba6-128">Tabs</span></span>

<span data-ttu-id="2eba6-p106">Las pestañas son el segundo nivel de navegación. Las áreas de características contienen varias pestañas y cada área representa a una característica.</span><span class="sxs-lookup"><span data-stu-id="2eba6-p106">The tabs are your second level of navigation. Each of the feature areas contains various tabs, each representing a feature.</span></span>
  
### <a name="toolbar"></a><span data-ttu-id="2eba6-131">Barra de herramientas</span><span class="sxs-lookup"><span data-stu-id="2eba6-131">Toolbar</span></span>

<span data-ttu-id="2eba6-p107">Al hacer clic en la mayoría de las pestañas, verá una barra de herramientas. La barra de herramientas tiene iconos que realizan una acción específica. La siguiente tabla describe los iconos y sus acciones.</span><span class="sxs-lookup"><span data-stu-id="2eba6-p107">When you click most tabs, you'll see a toolbar. The toolbar has icons that perform a specific action. The following table describes the icons and their actions.</span></span>
  
|<span data-ttu-id="2eba6-135">**Icono**</span><span class="sxs-lookup"><span data-stu-id="2eba6-135">**Icon**</span></span>|<span data-ttu-id="2eba6-136">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="2eba6-136">**Name**</span></span>|<span data-ttu-id="2eba6-137">**Action**</span><span class="sxs-lookup"><span data-stu-id="2eba6-137">**Action**</span></span>|
|:-----|:-----|:-----|
|![Agregar icono](media/ITPro-EAC-AddIcon.png)           <br/> |<span data-ttu-id="2eba6-139">Agregar, nuevo</span><span class="sxs-lookup"><span data-stu-id="2eba6-139">Add, New</span></span>  <br/> |<span data-ttu-id="2eba6-p108">Utilice este icono para crear un nuevo objeto. Algunos de estos iconos tienen una flecha hacia abajo asociada donde puede hacer clic para mostrar objetos adicionales que puede crear.</span><span class="sxs-lookup"><span data-stu-id="2eba6-p108">Use this icon to create a new object. Some of these icons have an associated down arrow you can click to show additional objects you can create.</span></span>  <br/> |
|![Icono Editar](media/ITPro-EAC-EditIcon.png)           <br/> |<span data-ttu-id="2eba6-143">Editar</span><span class="sxs-lookup"><span data-stu-id="2eba6-143">Edit</span></span>  <br/> |<span data-ttu-id="2eba6-144">Utilice este icono para editar un objeto.</span><span class="sxs-lookup"><span data-stu-id="2eba6-144">Use this icon to edit an object.</span></span>  <br/> |
|![Eliminar icono](media/ITPro-EAC-DeleteIcon.png)           <br/> |<span data-ttu-id="2eba6-146">Eliminar</span><span class="sxs-lookup"><span data-stu-id="2eba6-146">Delete</span></span>  <br/> |<span data-ttu-id="2eba6-p109">Utilice este icono para eliminar un objeto. Algunos iconos eliminados tienen una flecha hacia abajo donde puede hacer clic para mostrar opciones adicionales.</span><span class="sxs-lookup"><span data-stu-id="2eba6-p109">Use this icon to delete an object. Some delete icons have a down arrow you can click to show additional options.</span></span>  <br/> |
|![icono de Buscar](media/ITPro-EAC-.png)           <br/> |<span data-ttu-id="2eba6-150">Búsqueda</span><span class="sxs-lookup"><span data-stu-id="2eba6-150">Search</span></span>  <br/> |<span data-ttu-id="2eba6-151">Usar este icono para abrir una casilla de búsqueda donde puede escribir una frase de búsqueda para el objeto que desee encontrar.</span><span class="sxs-lookup"><span data-stu-id="2eba6-151">Use this icon to open a search box in which you can type the search phrase for an object you want to find.</span></span>  <br/> |
|![Icono Actualizar](media/ITPro-EAC-RefreshIcon.png)           <br/> |<span data-ttu-id="2eba6-153">Actualizar</span><span class="sxs-lookup"><span data-stu-id="2eba6-153">Refresh</span></span>  <br/> |<span data-ttu-id="2eba6-154">Utilice este icono para actualizar la vista de lista.</span><span class="sxs-lookup"><span data-stu-id="2eba6-154">Use this icon to refresh the list view.</span></span>  <br/> |
|![Icono Más opciones](media/ITPro-EAC-MoreOptionsIcon.png)           <br/> |<span data-ttu-id="2eba6-156">Más opciones</span><span class="sxs-lookup"><span data-stu-id="2eba6-156">More options</span></span>  <br/> |<span data-ttu-id="2eba6-p110">Use este icono para ver más acciones que puede realizar para los objetos de la pestaña. Por ejemplo, al hacer clic en este icono en **Destinatarios \> Usuarios**, se muestra la opción para realizar una **Búsqueda avanzada**.  </span><span class="sxs-lookup"><span data-stu-id="2eba6-p110">Use this icon to view more actions you can perform for that tab's objects. For example, in **Recipients \> Users** clicking this icon shows the option to perform an **Advanced Search**.  </span></span><br/> |
|![Icono flecha arriba](media/ITPro-EAC-UpArrowIcon.png)![Icono flecha abajo](media/ITPro-EAC-DownArrowIcon.png)           <br/> |<span data-ttu-id="2eba6-161">Flecha hacia arriba y flecha hacia abajo</span><span class="sxs-lookup"><span data-stu-id="2eba6-161">Up arrow and down arrow</span></span>  <br/> |<span data-ttu-id="2eba6-162">Utilice estos iconos para mover la prioridad de un objeto hacia arriba o hacia abajo.</span><span class="sxs-lookup"><span data-stu-id="2eba6-162">Use these icons to move an object's priority up or down.</span></span>  <br/> |
|![Icono de quitar](media/ITPro-EAC-RemoveIcon.png)           <br/> |<span data-ttu-id="2eba6-164">Quitar</span><span class="sxs-lookup"><span data-stu-id="2eba6-164">Remove</span></span>  <br/> |<span data-ttu-id="2eba6-165">Utilice este icono para quitar objetos de la lista.</span><span class="sxs-lookup"><span data-stu-id="2eba6-165">Use this icon to remove objects from a list.</span></span>  <br/> |
   
### <a name="list-view"></a><span data-ttu-id="2eba6-166">Vista de lista</span><span class="sxs-lookup"><span data-stu-id="2eba6-166">List View</span></span>

<span data-ttu-id="2eba6-p111">Cuando seleccione una pestaña, en la mayoría de los casos verá la vista de lista. El límite de visualización de la vista de lista del EAC es de 10.000 objetos aproximadamente. Además, la paginación se incluye para que pueda paginar los resultados.</span><span class="sxs-lookup"><span data-stu-id="2eba6-p111">When you select a tab, in most cases you'll see a list view. The viewable limit with the EAC list view is approximately 10,000 objects. In addition, paging is included so that you can page to results.</span></span>
  
### <a name="details-pane"></a><span data-ttu-id="2eba6-170">Panel de detalles</span><span class="sxs-lookup"><span data-stu-id="2eba6-170">Details Pane</span></span>

<span data-ttu-id="2eba6-p112">Cuando seleccione un objeto de la vista de lista, la información acerca del objeto se muestra en el panel de detalles. En algunos casos, el panel de detalles incluye tareas de administración.</span><span class="sxs-lookup"><span data-stu-id="2eba6-p112">When you select an object from the list view, information about that object is displayed in the details pane. In some cases the details pane includes management tasks.</span></span>
  
### <a name="me-tile-and-help"></a><span data-ttu-id="2eba6-173">Mosaico Yo y Ayuda</span><span class="sxs-lookup"><span data-stu-id="2eba6-173">Me tile and Help</span></span>

<span data-ttu-id="2eba6-p113">El mosaico **Yo** permite cerrar sesión en el EAC e iniciar sesión como un usuario diferente. Desde el menú desplegable en **Ayuda**![Icono de ayuda](media/ITPro-EAC-HelpIcon.png), puede realizar las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="2eba6-p113">The **Me** tile allows you to sign out the EAC and sign in as a different user. From the **Help**![Help Icon](media/ITPro-EAC-HelpIcon.png) drop-down menu, you can perform the following actions:</span></span> 
  
1. <span data-ttu-id="2eba6-176">**Ayuda** Haga clic en ![Icono de ayuda](media/ITPro-EAC-HelpIcon.png) para ver el contenido de la ayuda en línea.</span><span class="sxs-lookup"><span data-stu-id="2eba6-176">**Help** Click ![Help Icon](media/ITPro-EAC-HelpIcon.png) to view the online help content.</span></span> 
    
2. <span data-ttu-id="2eba6-p114">**Deshabilitar el globo de Ayuda** El globo de Ayuda muestra la ayuda contextual de los campos cuando crea o edita un objeto. Puede desactivar el globo de Ayuda o activarlo si estaba deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="2eba6-p114">**Disable Help bubble** The Help bubble displays contextual help for fields when you create or edit an object. You can turn off the Help bubble or turn it on if it has been disabled.</span></span> 
    
3. <span data-ttu-id="2eba6-179">**Copyright** Haga clic en este vínculo para leer el aviso de derechos de autor de Exchange Online Protection.</span><span class="sxs-lookup"><span data-stu-id="2eba6-179">**Copyright** Click this link to read the copyright notice for Exchange Online Protection.</span></span> 
    
4. <span data-ttu-id="2eba6-180">**Privacidad** Haga clic para leer la directiva de privacidad de Exchange Online Protection.</span><span class="sxs-lookup"><span data-stu-id="2eba6-180">**Privacy** Click to read the privacy policy for Exchange Online Protection.</span></span> 
    
## <a name="supported-browsers"></a><span data-ttu-id="2eba6-181">Exploradores compatibles</span><span class="sxs-lookup"><span data-stu-id="2eba6-181">Supported Browsers</span></span>
<span data-ttu-id="2eba6-182"><a name="BKMK_SupportedBrowsers"> </a></span><span class="sxs-lookup"><span data-stu-id="2eba6-182"></span></span>

<span data-ttu-id="2eba6-p115">Para conseguir la mejor experiencia con EAC, le recomendamos que use siempre la versión más actualizada de los exploradores, clientes de Office y aplicaciones. También le recomendamos que instale las actualizaciones de software cuando estén disponibles. Para obtener más información acerca de los navegadores compatibles y los requisitos del sistema para el servicio, vea [Requisitos del sistema de Office 365](https://go.microsoft.com/fwlink/p/?LinkID=402699).</span><span class="sxs-lookup"><span data-stu-id="2eba6-p115">For the best experience using the EAC, we recommend that you always use the latest browsers, Office clients, and apps. We also recommend that you install software updates when they become available. For more information about the supported browsers and system requirements for the service, see [Office 365 System Requirements](https://go.microsoft.com/fwlink/p/?LinkID=402699).</span></span> 
  
## <a name="supported-languages-in-eop"></a><span data-ttu-id="2eba6-186">Idiomas admitidos en EOP</span><span class="sxs-lookup"><span data-stu-id="2eba6-186">Supported languages in EOP</span></span>
<span data-ttu-id="2eba6-187"><a name="BKMK_SupportedLanguages"> </a></span><span class="sxs-lookup"><span data-stu-id="2eba6-187"></span></span>

<span data-ttu-id="2eba6-188">Los siguientes idiomas están disponibles y son compatibles con Exchange Online Protection.</span><span class="sxs-lookup"><span data-stu-id="2eba6-188">The following languages are supported and available for Exchange Online Protection.</span></span>
  
- <span data-ttu-id="2eba6-189">Amhárico</span><span class="sxs-lookup"><span data-stu-id="2eba6-189">Amharic</span></span>
    
- <span data-ttu-id="2eba6-190">Árabe</span><span class="sxs-lookup"><span data-stu-id="2eba6-190">Arabic</span></span>
    
- <span data-ttu-id="2eba6-191">Vasco (Euskera)</span><span class="sxs-lookup"><span data-stu-id="2eba6-191">Basque (Basque)</span></span>
    
- <span data-ttu-id="2eba6-192">Bengalí (India)</span><span class="sxs-lookup"><span data-stu-id="2eba6-192">Bengali (India)</span></span>
    
- <span data-ttu-id="2eba6-193">Búlgaro</span><span class="sxs-lookup"><span data-stu-id="2eba6-193">Bulgarian</span></span>
    
- <span data-ttu-id="2eba6-194">Catalán</span><span class="sxs-lookup"><span data-stu-id="2eba6-194">Catalan</span></span>
    
- <span data-ttu-id="2eba6-195">Chino (simplificado)</span><span class="sxs-lookup"><span data-stu-id="2eba6-195">Chinese (Simplified)</span></span>
    
- <span data-ttu-id="2eba6-196">Chino (tradicional)</span><span class="sxs-lookup"><span data-stu-id="2eba6-196">Chinese (Traditional)</span></span>
    
- <span data-ttu-id="2eba6-197">Croata</span><span class="sxs-lookup"><span data-stu-id="2eba6-197">Croatian</span></span>
    
- <span data-ttu-id="2eba6-198">Checo</span><span class="sxs-lookup"><span data-stu-id="2eba6-198">Czech</span></span>
    
- <span data-ttu-id="2eba6-199">Danés</span><span class="sxs-lookup"><span data-stu-id="2eba6-199">Danish</span></span>
    
- <span data-ttu-id="2eba6-200">Holandés</span><span class="sxs-lookup"><span data-stu-id="2eba6-200">Dutch</span></span>
    
- <span data-ttu-id="2eba6-201">Holandés</span><span class="sxs-lookup"><span data-stu-id="2eba6-201">Dutch</span></span>
    
- <span data-ttu-id="2eba6-202">Inglés</span><span class="sxs-lookup"><span data-stu-id="2eba6-202">English</span></span>
    
- <span data-ttu-id="2eba6-203">Estonio</span><span class="sxs-lookup"><span data-stu-id="2eba6-203">Estonian</span></span>
    
- <span data-ttu-id="2eba6-204">Filipino (Filipinas)</span><span class="sxs-lookup"><span data-stu-id="2eba6-204">Filipino (Philippines)</span></span>
    
- <span data-ttu-id="2eba6-205">Finlandés</span><span class="sxs-lookup"><span data-stu-id="2eba6-205">Finnish</span></span>
    
- <span data-ttu-id="2eba6-206">Francés</span><span class="sxs-lookup"><span data-stu-id="2eba6-206">French</span></span>
    
- <span data-ttu-id="2eba6-207">Gallego</span><span class="sxs-lookup"><span data-stu-id="2eba6-207">Galician</span></span>
    
- <span data-ttu-id="2eba6-208">Alemán</span><span class="sxs-lookup"><span data-stu-id="2eba6-208">German</span></span>
    
- <span data-ttu-id="2eba6-209">Griego</span><span class="sxs-lookup"><span data-stu-id="2eba6-209">Greek</span></span>
    
- <span data-ttu-id="2eba6-210">Gujarati</span><span class="sxs-lookup"><span data-stu-id="2eba6-210">Gujarati</span></span>
    
- <span data-ttu-id="2eba6-211">Hebreo</span><span class="sxs-lookup"><span data-stu-id="2eba6-211">Hebrew</span></span>
    
- <span data-ttu-id="2eba6-212">Hindi</span><span class="sxs-lookup"><span data-stu-id="2eba6-212">Hindi</span></span>
    
- <span data-ttu-id="2eba6-213">Húngaro</span><span class="sxs-lookup"><span data-stu-id="2eba6-213">Hungarian</span></span>
    
- <span data-ttu-id="2eba6-214">Islandés</span><span class="sxs-lookup"><span data-stu-id="2eba6-214">Icelandic</span></span>
    
- <span data-ttu-id="2eba6-215">Indonesio</span><span class="sxs-lookup"><span data-stu-id="2eba6-215">Indonesian</span></span>
    
- <span data-ttu-id="2eba6-216">Italiano</span><span class="sxs-lookup"><span data-stu-id="2eba6-216">Italian</span></span>
    
- <span data-ttu-id="2eba6-217">Japonés</span><span class="sxs-lookup"><span data-stu-id="2eba6-217">Japanese</span></span>
    
- <span data-ttu-id="2eba6-218">Kannada</span><span class="sxs-lookup"><span data-stu-id="2eba6-218">Kannada</span></span>
    
- <span data-ttu-id="2eba6-219">Kazajo</span><span class="sxs-lookup"><span data-stu-id="2eba6-219">Kazakh</span></span>
    
- <span data-ttu-id="2eba6-220">Kiswahili</span><span class="sxs-lookup"><span data-stu-id="2eba6-220">Kiswahili</span></span>
    
- <span data-ttu-id="2eba6-221">Coreano</span><span class="sxs-lookup"><span data-stu-id="2eba6-221">Korean</span></span>
    
- <span data-ttu-id="2eba6-222">Letón</span><span class="sxs-lookup"><span data-stu-id="2eba6-222">Latvian</span></span>
    
- <span data-ttu-id="2eba6-223">Lituano</span><span class="sxs-lookup"><span data-stu-id="2eba6-223">Lithuanian</span></span>
    
- <span data-ttu-id="2eba6-224">Malayo (Brunei Darussalam)</span><span class="sxs-lookup"><span data-stu-id="2eba6-224">Malay (Brunei Darussalam)</span></span>
    
- <span data-ttu-id="2eba6-225">Malayo (Malasia)</span><span class="sxs-lookup"><span data-stu-id="2eba6-225">Malay (Malaysia)</span></span>
    
- <span data-ttu-id="2eba6-226">Malayalam</span><span class="sxs-lookup"><span data-stu-id="2eba6-226">Malayalam</span></span>
    
- <span data-ttu-id="2eba6-227">Maratí</span><span class="sxs-lookup"><span data-stu-id="2eba6-227">Marathi</span></span>
    
- <span data-ttu-id="2eba6-228">Noruego (Bokmål)</span><span class="sxs-lookup"><span data-stu-id="2eba6-228">Norwegian (Bokmål)</span></span>
    
- <span data-ttu-id="2eba6-229">Noruego (Nynorsk)</span><span class="sxs-lookup"><span data-stu-id="2eba6-229">Norwegian (Nynorsk)</span></span>
    
- <span data-ttu-id="2eba6-230">Odia</span><span class="sxs-lookup"><span data-stu-id="2eba6-230">Oriya</span></span>
    
- <span data-ttu-id="2eba6-231">Persa</span><span class="sxs-lookup"><span data-stu-id="2eba6-231">Persian</span></span>
    
- <span data-ttu-id="2eba6-232">Polaco</span><span class="sxs-lookup"><span data-stu-id="2eba6-232">Polish</span></span>
    
- <span data-ttu-id="2eba6-233">Portugués (Brasil)</span><span class="sxs-lookup"><span data-stu-id="2eba6-233">Portuguese (Brazil)</span></span>
    
- <span data-ttu-id="2eba6-234">Portugués (Portugal)</span><span class="sxs-lookup"><span data-stu-id="2eba6-234">Portuguese (Portugal)</span></span>
    
- <span data-ttu-id="2eba6-235">Rumano</span><span class="sxs-lookup"><span data-stu-id="2eba6-235">Romanian</span></span>
    
- <span data-ttu-id="2eba6-236">Ruso</span><span class="sxs-lookup"><span data-stu-id="2eba6-236">Russian</span></span>
    
- <span data-ttu-id="2eba6-237">Serbio (cirílico, Serbia)</span><span class="sxs-lookup"><span data-stu-id="2eba6-237">Serbian (Cyrillic, Serbia)</span></span>
    
- <span data-ttu-id="2eba6-238">Serbio (Latín)</span><span class="sxs-lookup"><span data-stu-id="2eba6-238">Serbian (Latin)</span></span>
    
- <span data-ttu-id="2eba6-239">Eslovaco</span><span class="sxs-lookup"><span data-stu-id="2eba6-239">Slovak</span></span>
    
- <span data-ttu-id="2eba6-240">Esloveno</span><span class="sxs-lookup"><span data-stu-id="2eba6-240">Slovenian</span></span>
    
- <span data-ttu-id="2eba6-241">Español</span><span class="sxs-lookup"><span data-stu-id="2eba6-241">Spanish</span></span>
    
- <span data-ttu-id="2eba6-242">Sueco</span><span class="sxs-lookup"><span data-stu-id="2eba6-242">Swedish</span></span>
    
- <span data-ttu-id="2eba6-243">Tamil</span><span class="sxs-lookup"><span data-stu-id="2eba6-243">Tamil</span></span>
    
- <span data-ttu-id="2eba6-244">Telugu</span><span class="sxs-lookup"><span data-stu-id="2eba6-244">Telugu</span></span>
    
- <span data-ttu-id="2eba6-245">Tailandés</span><span class="sxs-lookup"><span data-stu-id="2eba6-245">Thai</span></span>
    
- <span data-ttu-id="2eba6-246">Turco</span><span class="sxs-lookup"><span data-stu-id="2eba6-246">Turkish</span></span>
    
- <span data-ttu-id="2eba6-247">Ucraniano</span><span class="sxs-lookup"><span data-stu-id="2eba6-247">Ukrainian</span></span>
    
- <span data-ttu-id="2eba6-248">Urdu</span><span class="sxs-lookup"><span data-stu-id="2eba6-248">Urdu</span></span>
    
- <span data-ttu-id="2eba6-249">Vietnamita</span><span class="sxs-lookup"><span data-stu-id="2eba6-249">Vietnamese</span></span>
    
- <span data-ttu-id="2eba6-250">Galés</span><span class="sxs-lookup"><span data-stu-id="2eba6-250">Welsh</span></span>
    

