---
title: Auditar el uso compartido para buscar recursos compartidos con usuarios externos
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 2/13/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
- MOE150
- BCS160
- MET150
ms.assetid: 50bbf89f-7870-4c2a-ae14-42635e0cfc01
description: 'El uso compartido es una actividad clave en SharePoint Online y OneDrive para la empresa. Ahora, los administradores pueden usar la auditoría de uso compartido en el registro de auditoría de Office 365 para determinar cómo se usa el uso compartido en su organización. '
ms.openlocfilehash: a363ebe2e8b1697521ab5f84df0b3fc221a2abcd
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/17/2019
ms.locfileid: "34157902"
---
# <a name="use-sharing-auditing-in-the-office-365-audit-log"></a><span data-ttu-id="96fb6-104">Auditar el uso compartido para buscar recursos compartidos con usuarios externos</span><span class="sxs-lookup"><span data-stu-id="96fb6-104">Use sharing auditing in the Office 365 audit log</span></span>

<span data-ttu-id="96fb6-105">El uso compartido es una actividad clave en SharePoint Online y OneDrive para la empresa, y se usa ampliamente en organizaciones de Office 365.</span><span class="sxs-lookup"><span data-stu-id="96fb6-105">Sharing is a key activity in SharePoint Online and OneDrive for Business, and it's widely used in Office 365 organizations.</span></span> <span data-ttu-id="96fb6-106">Ahora, los administradores pueden usar la auditoría de uso compartido en el registro de auditoría de Office 365 para determinar cómo se usa el uso compartido en su organización.</span><span class="sxs-lookup"><span data-stu-id="96fb6-106">Administrators can now use sharing auditing in the Office 365 audit log to determine how sharing is being used in their organization.</span></span> 
  
## <a name="the-sharepoint-sharing-schema"></a><span data-ttu-id="96fb6-107">El esquema de uso compartido de SharePoint</span><span class="sxs-lookup"><span data-stu-id="96fb6-107">The SharePoint Sharing schema</span></span>

<span data-ttu-id="96fb6-108">Los eventos de uso compartido (excluir la Directiva de uso compartido y los eventos de vínculo de uso compartido) son distintos de los eventos relacionados con archivos y carpetas de una forma principal: un usuario está realizando una acción que tiene algún efecto en otro usuario.</span><span class="sxs-lookup"><span data-stu-id="96fb6-108">Sharing events (excluding sharing policy and sharing link events) are different from file- and folder-related events in one primary way: one user is taking an action that has some effect on another user.</span></span> <span data-ttu-id="96fb6-109">Por ejemplo, el usuario A concede el acceso de usuario B a un archivo.</span><span class="sxs-lookup"><span data-stu-id="96fb6-109">For example, User A gives User B access to a file.</span></span> <span data-ttu-id="96fb6-110">En este ejemplo, el usuario A es el usuario que *actúa* y el usuario B es el *usuario de destino*.</span><span class="sxs-lookup"><span data-stu-id="96fb6-110">In this example, User A is the  *acting user*  and User B is the  *target user*.</span></span> <span data-ttu-id="96fb6-111">En el esquema de archivos de SharePoint, la acción del usuario que actúa solo afecta al propio archivo.</span><span class="sxs-lookup"><span data-stu-id="96fb6-111">In the SharePoint File schema, the acting user's action only affects the file itself.</span></span> <span data-ttu-id="96fb6-112">Cuando el usuario A abre un archivo, la única información necesaria en el evento **FileAccessed** es el usuario que actúa.</span><span class="sxs-lookup"><span data-stu-id="96fb6-112">When User A opens a file, the only information needed in the **FileAccessed** event is the acting user.</span></span> <span data-ttu-id="96fb6-113">Para solucionar esta diferencia, hay un esquema independiente, denominado esquema de *uso compartido de SharePoint*, que recopila más información sobre los eventos de uso compartido.</span><span class="sxs-lookup"><span data-stu-id="96fb6-113">To address this difference, there is a separate schema, called the  *SharePoint Sharing schema*, that captures more information about sharing events.</span></span> <span data-ttu-id="96fb6-114">Esto garantiza que los administradores tengan más información sobre quién compartió un recurso y el usuario con el que se compartió el recurso.</span><span class="sxs-lookup"><span data-stu-id="96fb6-114">This ensures that administrators have more insight into who shared a resource and the user the resource was shared with.</span></span> 
  
<span data-ttu-id="96fb6-115">El esquema de uso compartido proporciona dos campos adicionales en el registro de auditoría relacionados con el uso compartido de eventos:</span><span class="sxs-lookup"><span data-stu-id="96fb6-115">The Sharing schema provides two additional fields in the audit log related to sharing events:</span></span> 
  
- <span data-ttu-id="96fb6-116">**TargetUserOrGroupName** : almacena el UPN o el nombre del usuario o grupo de destino con el que se compartió un recurso (usuario B en el ejemplo anterior).</span><span class="sxs-lookup"><span data-stu-id="96fb6-116">**TargetUserOrGroupName** - Stores the UPN or name of the target user or group that a resource was shared with (User B in the previous example).</span></span> 
    
- <span data-ttu-id="96fb6-117">**TargetUserOrGroupType** : identifica si el usuario o el grupo de destino es un miembro, un invitado, un grupo o un socio.</span><span class="sxs-lookup"><span data-stu-id="96fb6-117">**TargetUserOrGroupType** - Identifies whether the target user or group is a Member, Guest, Group, or Partner.</span></span> 
    
<span data-ttu-id="96fb6-118">Estos dos campos, además de otras propiedades del esquema del registro de auditoría de Office 365, como User, Operation y Date, pueden decir el artículo completo sobre el *que* el usuario compartió *qué* recurso con *quién* y *Cuándo*.</span><span class="sxs-lookup"><span data-stu-id="96fb6-118">These two fields, in addition to other properties from the Office 365 audit log schema such as User, Operation, and Date can tell the full story about  *which*  user shared  *what*  resource with  *whom*  and  *when*.</span></span> 
  
<span data-ttu-id="96fb6-119">Hay otra propiedad de esquema que es importante para la historia de uso compartido.</span><span class="sxs-lookup"><span data-stu-id="96fb6-119">There's another schema property that's important to the sharing story.</span></span> <span data-ttu-id="96fb6-120">La propiedad **EventData** almacena información adicional acerca de los eventos de uso compartido.</span><span class="sxs-lookup"><span data-stu-id="96fb6-120">The **EventData** property stores additional information about sharing events.</span></span> <span data-ttu-id="96fb6-121">Por ejemplo, cuando un usuario comparte un sitio con otro usuario, esto se consigue agregando el usuario de destino a un grupo de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="96fb6-121">For example, when a user shares a site with another user, this is accomplished by adding the target user to a SharePoint group.</span></span> <span data-ttu-id="96fb6-122">La propiedad **EventData** captura esta información adicional para proporcionar contexto a los administradores.</span><span class="sxs-lookup"><span data-stu-id="96fb6-122">The **EventData** property captures this additional information to provide context for administrators.</span></span> 

## <a name="the-sharepoint-sharing-model-and-sharing-events"></a><span data-ttu-id="96fb6-123">Modelo de uso compartido de SharePoint y eventos de uso compartido</span><span class="sxs-lookup"><span data-stu-id="96fb6-123">The SharePoint Sharing model and sharing events</span></span>

<span data-ttu-id="96fb6-124">El uso compartido se define realmente mediante tres eventos independientes: **SharingSet**, **SharingInvitationCreated**y **SharingInvitaitonAccepted**.</span><span class="sxs-lookup"><span data-stu-id="96fb6-124">Sharing is actually defined by three separate events: **SharingSet**, **SharingInvitationCreated**, and **SharingInvitaitonAccepted**.</span></span> <span data-ttu-id="96fb6-125">Este es el flujo de trabajo de cómo se registran los eventos de uso compartido en el registro de auditoría de Office 365.</span><span class="sxs-lookup"><span data-stu-id="96fb6-125">Here's the work flow for how sharing events are logged in the Office 365 audit log.</span></span> 
  
![Diagrama de flujo de cómo funciona la auditoría de uso compartido](media/d83dd40f-919b-484f-bfd6-5dc8de31bff6.png)
  
<span data-ttu-id="96fb6-127">Cuando un usuario (el que actúa como usuario) desea compartir un recurso con otro usuario (el usuario de destino), SharePoint (o OneDrive para la empresa) comprueba en primer lugar si la dirección de correo electrónico del usuario de destino ya está asociada a una cuenta de usuario en el directorio de la organización.</span><span class="sxs-lookup"><span data-stu-id="96fb6-127">When a user (the acting user) wants to share a resource with another user (the target user), SharePoint (or OneDrive for Business) first checks if the email address of the target user is already associated with a user account in the organization's directory.</span></span> <span data-ttu-id="96fb6-128">Si el usuario de destino está en el directorio de la organización, SharePoint hace lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="96fb6-128">If the target user is in the organization's directory, SharePoint does the following:</span></span>
  
-  <span data-ttu-id="96fb6-129">Asigna inmediatamente los permisos de usuario de destino para obtener acceso al recurso.</span><span class="sxs-lookup"><span data-stu-id="96fb6-129">Immediately assigns the target user permissions to access the resource.</span></span> 
    
- <span data-ttu-id="96fb6-130">Envía una notificación de uso compartido a la dirección de correo electrónico del usuario de destino.</span><span class="sxs-lookup"><span data-stu-id="96fb6-130">Sends a sharing notification to the email address of the target user.</span></span>
    
- <span data-ttu-id="96fb6-131">Registra un evento **SharingSet** .</span><span class="sxs-lookup"><span data-stu-id="96fb6-131">Logs a **SharingSet** event.</span></span> 
    
 <span data-ttu-id="96fb6-132">Si una cuenta de usuario para el usuario de destino no está en el directorio de la organización, SharePoint hace lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="96fb6-132">If a user account for the target user isn't in the organization's directory, SharePoint does the following:</span></span> 
  
- <span data-ttu-id="96fb6-133">Crea una invitación para uso compartido y la envía a la dirección de correo electrónico del usuario de destino.</span><span class="sxs-lookup"><span data-stu-id="96fb6-133">Creates a sharing invitation and sends it to the email address of the target user.</span></span>
    
- <span data-ttu-id="96fb6-134">Registra un evento **SharingInvitationCreated** .</span><span class="sxs-lookup"><span data-stu-id="96fb6-134">Logs a **SharingInvitationCreated** event.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="96fb6-135">El evento **SharingInvitationCreated** siempre está asociado con el uso compartido externo o invitado cuando el usuario de destino no tiene acceso al recurso que se ha compartido.</span><span class="sxs-lookup"><span data-stu-id="96fb6-135">The **SharingInvitationCreated** event is most always associated with external or guest sharing when the target user doesn't have access to the resource that was shared.</span></span> 
  
<span data-ttu-id="96fb6-136">Cuando el usuario de destino acepta la invitación para compartir que se le envía (haciendo clic en el vínculo de la invitación), SharePoint registra un evento **SharingInvitationAccepted** y le asigna los permisos de usuario de destino para obtener acceso al recurso.</span><span class="sxs-lookup"><span data-stu-id="96fb6-136">When the target user accepts the sharing invitation that's sent to them (by clicking the link in the invitation), SharePoint logs a **SharingInvitationAccepted** event and assigns the target user permissions to access the resource.</span></span> <span data-ttu-id="96fb6-137">También se registra información adicional sobre el usuario de destino, como la identidad del usuario a la que se envió la invitación y el usuario que realmente aceptó la invitación.</span><span class="sxs-lookup"><span data-stu-id="96fb6-137">Additional information about the target user is also logged, such as the identity of the user that the invitation was sent to and the user who actually accepted the invitation.</span></span> <span data-ttu-id="96fb6-138">En algunos casos, estos usuarios (o direcciones de correo electrónico) pueden ser diferentes.</span><span class="sxs-lookup"><span data-stu-id="96fb6-138">In some case, these users (or email addresses) might be different.</span></span> 
  

  
## <a name="how-to-identify-resources-shared-with-external-users"></a><span data-ttu-id="96fb6-139">Identificación de recursos compartidos con usuarios externos</span><span class="sxs-lookup"><span data-stu-id="96fb6-139">How to identify resources shared with external users</span></span>

<span data-ttu-id="96fb6-140">Un requisito común para los administradores es crear una lista de todos los recursos que se han compartido con usuarios fuera de la organización.</span><span class="sxs-lookup"><span data-stu-id="96fb6-140">A common requirement for administrators is creating a list of all resources that have been shared with users outside of the organization.</span></span> <span data-ttu-id="96fb6-141">Mediante el uso de la auditoría de uso compartido en Office 365, los administradores ahora pueden generar esta lista.</span><span class="sxs-lookup"><span data-stu-id="96fb6-141">By using sharing auditing in Office 365, administrators can now generate this list.</span></span> <span data-ttu-id="96fb6-142">Aquí se muestra cómo hacerlo.</span><span class="sxs-lookup"><span data-stu-id="96fb6-142">Here's how.</span></span>
  
### <a name="step-1-search-for-sharing-events-and-export-the-results-to-a-csv-file"></a><span data-ttu-id="96fb6-143">Paso 1: buscar eventos de uso compartido y exportar los resultados a un archivo CSV</span><span class="sxs-lookup"><span data-stu-id="96fb6-143">Step 1: Search for sharing events and export the results to a CSV file</span></span>

<span data-ttu-id="96fb6-144">El primer paso es buscar eventos de uso compartido en el registro de auditoría de Office 365.</span><span class="sxs-lookup"><span data-stu-id="96fb6-144">The first step is to search the Office 365 audit log for sharing events.</span></span> <span data-ttu-id="96fb6-145">Para obtener más información (incluidos los permisos necesarios) sobre cómo buscar en el registro de auditoría, vea [Buscar en el registro de auditoría del centro de seguridad _AMP_ cumplimiento](search-the-audit-log-in-security-and-compliance.md).</span><span class="sxs-lookup"><span data-stu-id="96fb6-145">For more details (including the required permissions) about searching the audit log, see [Search the audit log in the Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md).</span></span>
  
1. <span data-ttu-id="96fb6-146">Vaya a [https://protection.office.com](https://protection.office.com).</span><span class="sxs-lookup"><span data-stu-id="96fb6-146">Go to [https://protection.office.com](https://protection.office.com).</span></span>
    
2. <span data-ttu-id="96fb6-147">Inicie sesión en Office 365 con su cuenta profesional o educativa.</span><span class="sxs-lookup"><span data-stu-id="96fb6-147">Sign in to Office 365 using your work or school account.</span></span>
    
3. <span data-ttu-id="96fb6-148">En el panel izquierdo del centro de seguridad & cumplimiento, haga clic en búsqueda de**registros de auditoría**de **búsqueda**  > .</span><span class="sxs-lookup"><span data-stu-id="96fb6-148">In the left pane of the Security & Compliance Center, click **Search**  > **Audit log search**.</span></span>
    
    <span data-ttu-id="96fb6-149">Se muestra la página de **búsqueda de registros de auditoría** .</span><span class="sxs-lookup"><span data-stu-id="96fb6-149">The **Audit log search** page is displayed.</span></span> 
    
4. <span data-ttu-id="96fb6-150">En **actividades**, haga clic en **compartir actividades** para buscar solo eventos de uso compartido.</span><span class="sxs-lookup"><span data-stu-id="96fb6-150">Under **Activities**, click **Sharing activities** to search only for sharing events.</span></span> 
    
    ![En actividades, seleccione actividades de uso compartido.](media/46bb25b7-1eb2-4adf-903a-cc9ab58639f9.png)
  
5.  <span data-ttu-id="96fb6-152">Seleccione un intervalo de fecha y hora para buscar los eventos de uso compartido que se produjeron dentro de ese período.</span><span class="sxs-lookup"><span data-stu-id="96fb6-152">Select a date and time range to find the sharing events that occurred within that period.</span></span> 
    
6. <span data-ttu-id="96fb6-153">Haga clic en **Buscar** para ejecutar la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="96fb6-153">Click **Search** to run the search.</span></span> 
    
7. <span data-ttu-id="96fb6-154">Cuando la búsqueda termine de ejecutarse y se muestren los resultados, haga clic en **exportar resultados** \> **descargar todos los resultados**.</span><span class="sxs-lookup"><span data-stu-id="96fb6-154">When the search is finished running and the results are displayed , click **Export results** \> **Download all results**.</span></span>
    
    <span data-ttu-id="96fb6-155">Una vez seleccionada la opción exportar, se muestra un mensaje en la parte inferior de la ventana que le pregunta si desea abrir o guardar el archivo CSV.</span><span class="sxs-lookup"><span data-stu-id="96fb6-155">After you select the export option, a message is displayed at the bottom of the window that prompts you to open or save the CSV file.</span></span>
    
8. <span data-ttu-id="96fb6-156">Haga clic en **Guardar** \> y guardar **como** y guarde el archivo CSV en una carpeta del equipo local.</span><span class="sxs-lookup"><span data-stu-id="96fb6-156">Click **Save** \> **Save as** and save the CSV file to a folder on your local computer.</span></span> 
    

  
### <a name="step-2-filter-the-csv-file-for-resources-shared-with-external-users"></a><span data-ttu-id="96fb6-157">Paso 2: filtrar el archivo CSV para los recursos compartidos con usuarios externos</span><span class="sxs-lookup"><span data-stu-id="96fb6-157">Step 2: Filter the CSV file for resources shared with external users</span></span>

<span data-ttu-id="96fb6-158">El paso siguiente es filtrar el archivo CSV para los eventos **SharingSet** y **SharingInvitationCreated** , así como mostrar los eventos en los que la propiedad **TargetUserOrGroupType** es **Guest**.</span><span class="sxs-lookup"><span data-stu-id="96fb6-158">The next step is to filter the CSV for the **SharingSet** and **SharingInvitationCreated** events, and to display those events where the **TargetUserOrGroupType** property is **Guest**.</span></span> <span data-ttu-id="96fb6-159">Para ello, debe usar la característica Power Query de Excel.</span><span class="sxs-lookup"><span data-stu-id="96fb6-159">You'll use the Power Query feature in Excel to do this.</span></span> <span data-ttu-id="96fb6-160">El siguiente procedimiento se realiza en Excel 2016.</span><span class="sxs-lookup"><span data-stu-id="96fb6-160">The following procedure is performed in Excel 2016.</span></span> 
  
1. <span data-ttu-id="96fb6-161">En Excel 2016, abra un libro en blanco.</span><span class="sxs-lookup"><span data-stu-id="96fb6-161">In Excel 2016, open a blank workbook.</span></span>
    
2. <span data-ttu-id="96fb6-162">Haga clic en la pestaña **datos** .</span><span class="sxs-lookup"><span data-stu-id="96fb6-162">Click the **Data** tab.</span></span> 
    
3. <span data-ttu-id="96fb6-163">Haga clic en **nueva consulta** \> **desde archivo** \> **CSV**.</span><span class="sxs-lookup"><span data-stu-id="96fb6-163">Click **New Query** \> **From file** \> **From CSV**.</span></span>
    
    ![En la pestaña datos, seleccione Nueva consulta, seleccione desde archivo y, después, seleccione desde CSV](media/5170ab34-b449-40ea-bd3f-f1432c1c5973.png)
  
4. <span data-ttu-id="96fb6-165">Abra el archivo CSV que ha descargado en el paso 1.</span><span class="sxs-lookup"><span data-stu-id="96fb6-165">Open the CSV file that you downloaded in Step 1.</span></span>
    
    <span data-ttu-id="96fb6-166">El archivo CSV se abre en el editor de consultas.</span><span class="sxs-lookup"><span data-stu-id="96fb6-166">The CSV file is opened in the Query Editor.</span></span> <span data-ttu-id="96fb6-167">Tenga en cuenta que hay cuatro columnas: **tiempo**, **usuario**, **acción**y **detalle**.</span><span class="sxs-lookup"><span data-stu-id="96fb6-167">Note that there are four columns: **Time**, **User**, **Action**, and **Detail**.</span></span> <span data-ttu-id="96fb6-168">La columna de **detalle** es un campo de múltiples propiedades.</span><span class="sxs-lookup"><span data-stu-id="96fb6-168">The **Detail** column is a multi-property field.</span></span> <span data-ttu-id="96fb6-169">El paso siguiente es crear una nueva columna para cada una de las propiedades de la columna de **detalle** .</span><span class="sxs-lookup"><span data-stu-id="96fb6-169">The next step is to create a new column for each of the properties in the **Detail** column.</span></span> 
    
5. <span data-ttu-id="96fb6-170">Seleccione la columna **detalles** y, a continuación, en la pestaña **Inicio** , haga clic en **dividir columna** \> **por**delimitador.</span><span class="sxs-lookup"><span data-stu-id="96fb6-170">Select the **Detail** column, and then on the **Home** tab, click **Split Column** \> **By Delimiter**.</span></span>
    
    ![En la pestaña Inicio, haga clic en dividir columna y, a continuación, haga clic en por delimitador](media/aeb503e8-565b-42ea-91e2-9f127a74c00c.png)
  
6. <span data-ttu-id="96fb6-172">En la ventana **dividir columna por** delimitador, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="96fb6-172">In the **Split Column by Delimiter** window, do the following:</span></span> 
    
      - <span data-ttu-id="96fb6-173">En **seleccionar o escribir**delimitador, seleccione **coma**.</span><span class="sxs-lookup"><span data-stu-id="96fb6-173">Under **Select or enter delimiter**, select **Comma**.</span></span>
    
      - <span data-ttu-id="96fb6-174">En **dividir**, seleccione **en cada aparición del**delimitador.</span><span class="sxs-lookup"><span data-stu-id="96fb6-174">Under **Split**, select **At each occurrence of the delimiter**.</span></span>
    
7. <span data-ttu-id="96fb6-175">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="96fb6-175">Click **OK**.</span></span>
    
    <span data-ttu-id="96fb6-176">La columna de **detalle** se divide en varias columnas.</span><span class="sxs-lookup"><span data-stu-id="96fb6-176">The **Detail** column is split into multiple columns.</span></span> <span data-ttu-id="96fb6-177">Cada columna nueva tiene el nombre **detalle. 1**, **detalle. 2**, **detalle. 3**y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="96fb6-177">Each new column is named **Detail.1**, **Detail.2**, **Detail.3**, and so on.</span></span> <span data-ttu-id="96fb6-178">Observará que los valores de cada celda de las columnas **detail. n** van precedidos por el nombre de la propiedad; por ejemplo, **operación: SharingSet**, **Operation: SharingInvitationAccepted**y **Operation: SharingInvitationCreated**.</span><span class="sxs-lookup"><span data-stu-id="96fb6-178">You'll notice the values in each cell in the **Detail.n** columns are prefixed with the name of the property; for example, **Operation:SharingSet**, **Operation:SharingInvitationAccepted**, and **Operation:SharingInvitationCreated**.</span></span>
    
    ![La columna de detalle se divide en varias columnas, una para cada propiedad](media/4b104ead-0313-4bd4-b2a9-f143ccb378ac.png)
  
8. <span data-ttu-id="96fb6-180">En la pestaña **archivo** , haga clic en **cerrar &amp; carga** para cerrar el editor de consultas y abrir el archivo en un libro de Excel.</span><span class="sxs-lookup"><span data-stu-id="96fb6-180">On the **File** tab, click **Close &amp; Load** to close the Query Editor and open the file in an Excel workbook.</span></span> 
    
    <span data-ttu-id="96fb6-181">El paso siguiente es filtrar el archivo para que solo se muestren los eventos **SharingSet** y **SharingInvitationCreated** .</span><span class="sxs-lookup"><span data-stu-id="96fb6-181">The next step is to filter the file to only display the **SharingSet** and **SharingInvitationCreated** events.</span></span> 
    
9. <span data-ttu-id="96fb6-182">Vaya a la pestaña **Inicio** y, a continuación, seleccione la columna **acción** .</span><span class="sxs-lookup"><span data-stu-id="96fb6-182">Go to the **Home** tab, and then select the **Action** column.</span></span> 
    
10. <span data-ttu-id="96fb6-183">En la lista desplegable \*\*filtro &amp; \*\* de ordenación, desactive todas las selecciones, seleccione **SharingSet** y **SharingInvitationCreated**y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="96fb6-183">In the **Sort &amp; Filter** drop-down list, clear all selections, then select **SharingSet** and **SharingInvitationCreated**, and click **OK**.</span></span>
    
    <span data-ttu-id="96fb6-184">Excel muestra las filas de los eventos **SharingSet** y **SharingInvitationCreated** .</span><span class="sxs-lookup"><span data-stu-id="96fb6-184">Excel displays the rows for the **SharingSet** and **SharingInvitationCreated** events.</span></span> 
    
11. <span data-ttu-id="96fb6-185">Vaya a la columna llamada **detail. 17** (o a cualquier columna que contenga la propiedad **TargetUserOrGroupType** ) y selecciónela.</span><span class="sxs-lookup"><span data-stu-id="96fb6-185">Go to the column named **Detail.17** (or whichever column contains the **TargetUserOrGroupType** property) and select it.</span></span> 
    
12. <span data-ttu-id="96fb6-186">En la lista desplegable \*\*filtro &amp; \*\* de ordenación, desactive todas las selecciones, seleccione **TargetUserOrGroupType: invitado**y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="96fb6-186">In the **Sort &amp; Filter** drop-down list, clear all selections, then select **TargetUserOrGroupType:Guest**, and click **OK**.</span></span>
    
    <span data-ttu-id="96fb6-187">Ahora Excel muestra las filas de los eventos **SharingInvitationCreated** y **SharingSet** , y donde el usuario de destino está fuera de la organización, porque los usuarios externos se identifican mediante el valor **TargetUserOrGroupType: Guest**.</span><span class="sxs-lookup"><span data-stu-id="96fb6-187">Now Excel displays the rows for **SharingInvitationCreated** and **SharingSet** events AND where the target user is outside of your organization, because external users are identified by the value **TargetUserOrGroupType:Guest**.</span></span> 
    
<span data-ttu-id="96fb6-188">En la siguiente tabla se muestran todos los usuarios de la organización que compartía recursos con un usuario invitado dentro de un intervalo de fechas especificado.</span><span class="sxs-lookup"><span data-stu-id="96fb6-188">The following table shows all users in the organization who shared resources with a guest user within a specified date range.</span></span>
  
![Compartir eventos en el registro de auditoría de Office 365](media/0e0ecbe3-c794-4ca6-a2ca-63478fb3bb34.png)
  
<span data-ttu-id="96fb6-190">Aunque no se incluye en la tabla anterior, la columna **detail. 10** (o la columna que contiene la propiedad **objectId** ) identifica el recurso que se ha compartido con el usuario de destino; por ejemplo `ObjectId:https:\/\/contoso-my.sharepoint.com\/personal\/sarad_contoso_com\/Documents\/Southwater Proposal.docx`.</span><span class="sxs-lookup"><span data-stu-id="96fb6-190">Although it's not included in the previous table, the **Detail.10** column (or whichever column contains the **ObjectId** property) identifies the resource that was shared with the target user; for example  `ObjectId:https:\/\/contoso-my.sharepoint.com\/personal\/sarad_contoso_com\/Documents\/Southwater Proposal.docx`.</span></span>
  
> [!TIP]
> <span data-ttu-id="96fb6-191">Si desea identificar cuándo un usuario invitado ha recibido realmente permisos para obtener acceso a un recurso (en lugar de solo los recursos que compartiron con ellos), repita los pasos 10, 11 y 12, y filtre en la **SharingInvitationAccepted** y \*\*SharingSet \*\*eventos en el paso 10.</span><span class="sxs-lookup"><span data-stu-id="96fb6-191">If you want to identify when a guest user was actually assigned permissions to access a resource (as opposed to just the resources that where shared with them), repeat Steps 10, 11, and 12, and filter on the **SharingInvitationAccepted** and **SharingSet** events in Step 10.</span></span> 
