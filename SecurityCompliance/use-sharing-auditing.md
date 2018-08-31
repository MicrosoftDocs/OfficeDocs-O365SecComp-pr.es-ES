---
title: Uso compartido de auditoría en el registro de auditoría de Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 2/13/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- SPO160
- MOE150
- BCS160
- MET150
ms.assetid: 50bbf89f-7870-4c2a-ae14-42635e0cfc01
description: 'Uso compartido es una actividad clave en SharePoint Online y OneDrive para la empresa. Los administradores ahora pueden usar uso compartido de auditoría en el registro de auditoría de Office 365 para determinar cómo el uso compartido se está usando en su organización. '
ms.openlocfilehash: 511f8b0e61d450659d78177d5b87fac9ee636cd4
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22536306"
---
# <a name="use-sharing-auditing-in-the-office-365-audit-log"></a><span data-ttu-id="4390d-104">Uso compartido de auditoría en el registro de auditoría de Office 365</span><span class="sxs-lookup"><span data-stu-id="4390d-104">Use sharing auditing in the Office 365 audit log</span></span>

<span data-ttu-id="4390d-p102">El uso compartido una actividad clave en SharePoint Online y OneDrive para la empresa, y se utiliza ampliamente en las organizaciones de Office 365. Los administradores ahora pueden usar uso compartido de auditoría en el registro de auditoría de Office 365 para determinar cómo el uso compartido se está usando en su organización.</span><span class="sxs-lookup"><span data-stu-id="4390d-p102">Sharing is a key activity in SharePoint Online and OneDrive for Business, and it's widely used in Office 365 organizations. Administrators can now use sharing auditing in the Office 365 audit log to determine how sharing is being used in their organization.</span></span> 
  
## <a name="the-sharepoint-sharing-schema"></a><span data-ttu-id="4390d-107">El esquema de uso compartido de SharePoint</span><span class="sxs-lookup"><span data-stu-id="4390d-107">The SharePoint Sharing schema</span></span>

<span data-ttu-id="4390d-p103">Eventos de uso compartidos (excluido de directiva de uso compartido y uso compartido de vinculación eventos) son diferentes de los eventos relacionados con archivos y carpetas en una forma principal: un usuario está tomando una acción que tiene algunos efecto en otro usuario. Por ejemplo, un usuario proporciona acceso de usuario B a un archivo. En este ejemplo, el usuario A es el *que actúa el usuario* y usuario B es el *usuario de destino*. En el esquema de archivo de SharePoint, acción del usuario activo sólo afecta del propio archivo. Cuando el usuario A abre un archivo, la única información necesaria en el evento **FileAccessed** es el usuario activo. Para solucionar esta diferencia, hay un esquema independiente, denominado el *esquema de uso compartido de SharePoint*, que captura más información sobre el uso compartido de eventos. Esto garantiza que los administradores tienen más claro entendimiento en que un recurso compartido y el usuario, el recurso se ha compartido con.</span><span class="sxs-lookup"><span data-stu-id="4390d-p103">Sharing events (excluding sharing policy and sharing link events) are different from file- and folder-related events in one primary way: one user is taking an action that has some effect on another user. For example, User A gives User B access to a file. In this example, User A is the  *acting user*  and User B is the  *target user*. In the SharePoint File schema, the acting user's action only affects the file itself. When User A opens a file, the only information needed in the **FileAccessed** event is the acting user. To address this difference, there is a separate schema, called the  *SharePoint Sharing schema*, that captures more information about sharing events. This ensures that administrators have more insight into who shared a resource and the user the resource was shared with.</span></span> 
  
<span data-ttu-id="4390d-115">El esquema de uso compartido proporciona dos campos adicionales en el registro de auditoría relacionados con el uso compartido de eventos:</span><span class="sxs-lookup"><span data-stu-id="4390d-115">The Sharing schema provides two additional fields in the audit log related to sharing events:</span></span> 
  
- <span data-ttu-id="4390d-116">**TargetUserOrGroupName** - almacena el UPN o el nombre del usuario de destino o del grupo que se ha compartido un recurso con (usuario B en el ejemplo anterior).</span><span class="sxs-lookup"><span data-stu-id="4390d-116">**TargetUserOrGroupName** - Stores the UPN or name of the target user or group that a resource was shared with (User B in the previous example).</span></span> 
    
- <span data-ttu-id="4390d-117">**TargetUserOrGroupType** - identifica si el usuario de destino o el grupo es un miembro, invitado, grupo o socio.</span><span class="sxs-lookup"><span data-stu-id="4390d-117">**TargetUserOrGroupType** - Identifies whether the target user or group is a Member, Guest, Group, or Partner.</span></span> 
    
<span data-ttu-id="4390d-118">Esquema del registro de auditoría de estos dos campos, además de otras propiedades de Office 365, como usuario, operación y la fecha pueden indicar a la historia completa acerca de *qué* usuario shared *qué* recursos con *quién* y *cuándo*.</span><span class="sxs-lookup"><span data-stu-id="4390d-118">These two fields, in addition to other properties from the Office 365 audit log schema such as User, Operation, and Date can tell the full story about  *which*  user shared  *what*  resource with  *whom*  and  *when*.</span></span> 
  
<span data-ttu-id="4390d-p104">Hay otra propiedad de esquema que es importante para la historia de uso compartida. La propiedad **EventData** almacena información adicional sobre el uso compartido de eventos. Por ejemplo, cuando un usuario comparte un sitio con otro usuario, esto se logra agregando el usuario de destino a un grupo de SharePoint. La propiedad **EventData** captura esta información adicional para proporcionar contexto para los administradores.</span><span class="sxs-lookup"><span data-stu-id="4390d-p104">There's another schema property that's important to the sharing story. The **EventData** property stores additional information about sharing events. For example, when a user shares a site with another user, this is accomplished by adding the target user to a SharePoint group. The **EventData** property captures this additional information to provide context for administrators.</span></span> 

## <a name="the-sharepoint-sharing-model-and-sharing-events"></a><span data-ttu-id="4390d-123">El modelo de uso compartido y uso compartido de eventos de SharePoint</span><span class="sxs-lookup"><span data-stu-id="4390d-123">The SharePoint Sharing model and sharing events</span></span>

<span data-ttu-id="4390d-p105">Uso compartido está definido realmente por tres eventos independientes: **SharingSet**, **SharingInvitationCreated**y **SharingInvitaitonAccepted**. Aquí el flujo de trabajo para los eventos de uso compartidos de cómo se registran en el registro de auditoría de Office 365.</span><span class="sxs-lookup"><span data-stu-id="4390d-p105">Sharing is actually defined by three separate events: **SharingSet**, **SharingInvitationCreated**, and **SharingInvitaitonAccepted**. Here's the work flow for how sharing events are logged in the Office 365 audit log.</span></span> 
  
![Diagrama de flujo del funcionamiento de uso compartido de auditoría](media/d83dd40f-919b-484f-bfd6-5dc8de31bff6.png)
  
<span data-ttu-id="4390d-p106">Cuando un usuario (el usuario activo) desea compartir un recurso con otro usuario (el usuario de destino), SharePoint (o OneDrive para la empresa) comprueba primero si la dirección de correo electrónico del usuario de destino ya está asociada con una cuenta de usuario en el directorio de la organización. Si el usuario de destino se encuentra en el directorio de la organización, SharePoint hace lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="4390d-p106">When a user (the acting user) wants to share a resource with another user (the target user), SharePoint (or OneDrive for Business) first checks if the email address of the target user is already associated with a user account in the organization's directory. If the target user is in the organization's directory, SharePoint does the following:</span></span>
  
-  <span data-ttu-id="4390d-129">Asigna inmediatamente los permisos de usuario de destino para tener acceso al recurso.</span><span class="sxs-lookup"><span data-stu-id="4390d-129">Immediately assigns the target user permissions to access the resource.</span></span> 
    
- <span data-ttu-id="4390d-130">Envía una notificación de uso compartida en la dirección de correo electrónico del usuario de destino.</span><span class="sxs-lookup"><span data-stu-id="4390d-130">Sends a sharing notification to the email address of the target user.</span></span>
    
- <span data-ttu-id="4390d-131">Registra un evento **SharingSet** .</span><span class="sxs-lookup"><span data-stu-id="4390d-131">Logs a **SharingSet** event.</span></span> 
    
 <span data-ttu-id="4390d-132">Si una cuenta de usuario para el usuario de destino no está en el directorio de la organización, SharePoint hace lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="4390d-132">If a user account for the target user isn't in the organization's directory, SharePoint does the following:</span></span> 
  
- <span data-ttu-id="4390d-133">Crea una invitación para compartir y envía a la dirección de correo electrónico del usuario de destino.</span><span class="sxs-lookup"><span data-stu-id="4390d-133">Creates a sharing invitation and sends it to the email address of the target user.</span></span>
    
- <span data-ttu-id="4390d-134">Registra un evento **SharingInvitationCreated** .</span><span class="sxs-lookup"><span data-stu-id="4390d-134">Logs a **SharingInvitationCreated** event.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="4390d-135">El evento **SharingInvitationCreated** más siempre está asociado con el uso compartido externo o de invitado cuando el usuario de destino no tiene acceso al recurso que se ha compartido.</span><span class="sxs-lookup"><span data-stu-id="4390d-135">The **SharingInvitationCreated** event is most always associated with external or guest sharing when the target user doesn't have access to the resource that was shared.</span></span> 
  
<span data-ttu-id="4390d-p107">Cuando el usuario de destino acepta la invitación para compartir que se ha enviado a ellos (haciendo clic en el vínculo en la invitación), SharePoint registra un evento **SharingInvitationAccepted** y asigna los permisos de usuario de destino para tener acceso al recurso. También se registra información adicional sobre el usuario de destino, como la identidad del usuario que se envió la invitación y el usuario que realmente había aceptado la invitación. En algunos casos, estos usuarios (o direcciones de correo electrónico) pueden ser diferentes.</span><span class="sxs-lookup"><span data-stu-id="4390d-p107">When the target user accepts the sharing invitation that's sent to them (by clicking the link in the invitation), SharePoint logs a **SharingInvitationAccepted** event and assigns the target user permissions to access the resource. Additional information about the target user is also logged, such as the identity of the user that the invitation was sent to and the user who actually accepted the invitation. In some case, these users (or email addresses) might be different.</span></span> 
  

  
## <a name="how-to-identify-resources-shared-with-external-users"></a><span data-ttu-id="4390d-139">Cómo identificar los recursos compartidos con los usuarios externos</span><span class="sxs-lookup"><span data-stu-id="4390d-139">How to identify resources shared with external users</span></span>

<span data-ttu-id="4390d-p108">Un requisito común para los administradores es crear una lista de todos los recursos que se han compartido con los usuarios fuera de la organización. Mediante el uso de uso compartido de auditoría en Office 365, los administradores pueden generar ahora esta lista. Aquí es cómo.</span><span class="sxs-lookup"><span data-stu-id="4390d-p108">A common requirement for administrators is creating a list of all resources that have been shared with users outside of the organization. By using sharing auditing in Office 365, administrators can now generate this list. Here's how.</span></span>
  
### <a name="step-1-search-for-sharing-events-and-export-the-results-to-a-csv-file"></a><span data-ttu-id="4390d-143">Paso 1: Buscar eventos de uso compartido y exportar los resultados a un archivo CSV</span><span class="sxs-lookup"><span data-stu-id="4390d-143">Step 1: Search for sharing events and export the results to a CSV file</span></span>

<span data-ttu-id="4390d-p109">El primer paso es buscar el registro de auditoría de Office 365 para el uso compartido de eventos. Para obtener más detalles (incluidos los permisos necesarios) acerca de la búsqueda en el registro de auditoría, consulte [el registro de auditoría de búsqueda en la seguridad de Office 365 &amp; centro de cumplimiento](search-the-audit-log-in-security-and-compliance.md).</span><span class="sxs-lookup"><span data-stu-id="4390d-p109">The first step is to search the Office 365 audit log for sharing events. For more details (including the required permissions) about searching the audit log, see [Search the audit log in the Office 365 Security &amp; Compliance Center](search-the-audit-log-in-security-and-compliance.md).</span></span>
  
1. <span data-ttu-id="4390d-146">Vaya a [https://protection.office.com](https://protection.office.com).</span><span class="sxs-lookup"><span data-stu-id="4390d-146">Go to [https://protection.office.com](https://protection.office.com).</span></span>
    
2. <span data-ttu-id="4390d-147">Inicie sesión en Office 365 con su cuenta de trabajo o escuela.</span><span class="sxs-lookup"><span data-stu-id="4390d-147">Sign in to Office 365 using your work or school account.</span></span>
    
3. <span data-ttu-id="4390d-148">En el panel izquierdo de la seguridad &amp; centro de cumplimiento, haga clic en **búsqueda &amp; investigación**y, a continuación, haga clic en **búsqueda de registro de auditoría**.</span><span class="sxs-lookup"><span data-stu-id="4390d-148">In the left pane of the Security &amp; Compliance Center, click **Search &amp; investigation**, and then click **Audit log search**.</span></span>
    
    <span data-ttu-id="4390d-149">Se muestra la página de **búsqueda de registro de auditoría** .</span><span class="sxs-lookup"><span data-stu-id="4390d-149">The **Audit log search** page is displayed.</span></span> 
    
4. <span data-ttu-id="4390d-150">En **las actividades**, haga clic en **las actividades de uso compartido** para buscar sólo para uso compartido de eventos.</span><span class="sxs-lookup"><span data-stu-id="4390d-150">Under **Activities**, click **Sharing activities** to search only for sharing events.</span></span> 
    
    ![En actividades, seleccione las actividades de uso compartido](media/46bb25b7-1eb2-4adf-903a-cc9ab58639f9.png)
  
5.  <span data-ttu-id="4390d-152">Seleccione un intervalo de fechas y horas para encontrar los eventos de uso compartidos que se ha producido dentro de ese período.</span><span class="sxs-lookup"><span data-stu-id="4390d-152">Select a date and time range to find the sharing events that occurred within that period.</span></span> 
    
6. <span data-ttu-id="4390d-153">Haga clic en **Buscar** para ejecutar la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="4390d-153">Click **Search** to run the search.</span></span> 
    
7. <span data-ttu-id="4390d-154">Cuando finalice la búsqueda está ejecutando y los resultados se muestran, haga clic en **exportar los resultados de** \> **Descargar todos los resultados**.</span><span class="sxs-lookup"><span data-stu-id="4390d-154">When the search is finished running and the results are displayed , click **Export results** \> **Download all results**.</span></span>
    
    <span data-ttu-id="4390d-155">Después de seleccionar la opción de exportación, se muestra un mensaje en la parte inferior de la ventana que le pide que abra o guarde el archivo CSV.</span><span class="sxs-lookup"><span data-stu-id="4390d-155">After you select the export option, a message is displayed at the bottom of the window that prompts you to open or save the CSV file.</span></span>
    
8. <span data-ttu-id="4390d-156">Haga clic en **Guardar** \> **Guardar como** y guarde el archivo CSV en una carpeta en el equipo local.</span><span class="sxs-lookup"><span data-stu-id="4390d-156">Click **Save** \> **Save as** and save the CSV file to a folder on your local computer.</span></span> 
    

  
### <a name="step-2-filter-the-csv-file-for-resources-shared-with-external-users"></a><span data-ttu-id="4390d-157">Paso 2: Filtrar el archivo CSV para recursos compartidos con los usuarios externos</span><span class="sxs-lookup"><span data-stu-id="4390d-157">Step 2: Filter the CSV file for resources shared with external users</span></span>

<span data-ttu-id="4390d-p110">El siguiente paso para filtrar el CSV para los eventos **SharingSet** y **SharingInvitationCreated** y para mostrar los eventos donde es la propiedad **TargetUserOrGroupType** **invitado**. Para ello, debe usar la característica de consulta de alimentación en Excel. El siguiente procedimiento se realiza en Excel 2016.</span><span class="sxs-lookup"><span data-stu-id="4390d-p110">The next step is to filter the CSV for the **SharingSet** and **SharingInvitationCreated** events, and to display those events where the **TargetUserOrGroupType** property is **Guest**. You'll use the Power Query feature in Excel to do this. The following procedure is performed in Excel 2016.</span></span> 
  
1. <span data-ttu-id="4390d-161">En Excel 2016, abra un libro en blanco.</span><span class="sxs-lookup"><span data-stu-id="4390d-161">In Excel 2016, open a blank workbook.</span></span>
    
2. <span data-ttu-id="4390d-162">Haga clic en la pestaña **Datos**.</span><span class="sxs-lookup"><span data-stu-id="4390d-162">Click the **Data** tab.</span></span> 
    
3. <span data-ttu-id="4390d-163">Haga clic en **Nueva consulta** \> **de archivo** \> **De CSV**.</span><span class="sxs-lookup"><span data-stu-id="4390d-163">Click **New Query** \> **From file** \> **From CSV**.</span></span>
    
    ![En la ficha datos, seleccione nueva consulta, seleccione desde archivo y, a continuación, seleccione desde CSV](media/5170ab34-b449-40ea-bd3f-f1432c1c5973.png)
  
4. <span data-ttu-id="4390d-165">Abra el archivo CSV que ha descargado en el paso 1.</span><span class="sxs-lookup"><span data-stu-id="4390d-165">Open the CSV file that you downloaded in Step 1.</span></span>
    
    <span data-ttu-id="4390d-p111">El archivo CSV se abre en el Editor de consultas. Tenga en cuenta que no hay cuatro columnas: **tiempo**, **usuario**, **acción**y **Ver todos los detalles**. La columna **detalle** es un campo de propiedad múltiple. El siguiente paso es crear una nueva columna para cada una de las propiedades en la columna **todos los detalles** .</span><span class="sxs-lookup"><span data-stu-id="4390d-p111">The CSV file is opened in the Query Editor. Note that there are four columns: **Time**, **User**, **Action**, and **Detail**. The **Detail** column is a multi-property field. The next step is to create a new column for each of the properties in the **Detail** column.</span></span> 
    
5. <span data-ttu-id="4390d-170">Seleccione la columna **detalle** y, a continuación, en la ficha **Inicio** , haga clic en **División de columna** \> **Por delimitador**.</span><span class="sxs-lookup"><span data-stu-id="4390d-170">Select the **Detail** column, and then on the **Home** tab, click **Split Column** \> **By Delimiter**.</span></span>
    
    ![En la ficha Inicio, haga clic en división de columna y, a continuación, haga clic en por delimitador](media/aeb503e8-565b-42ea-91e2-9f127a74c00c.png)
  
6. <span data-ttu-id="4390d-172">En la ventana de **División de columna por delimitador** , haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="4390d-172">In the **Split Column by Delimiter** window, do the following:</span></span> 
    
      - <span data-ttu-id="4390d-173">En, **Seleccione o escriba el carácter delimitador**, seleccione **comas**.</span><span class="sxs-lookup"><span data-stu-id="4390d-173">Under **Select or enter delimiter**, select **Comma**.</span></span>
    
      - <span data-ttu-id="4390d-174">En **dos paneles**, seleccione **en cada aparición de delimitador**.</span><span class="sxs-lookup"><span data-stu-id="4390d-174">Under **Split**, select **At each occurrence of the delimiter**.</span></span>
    
7. <span data-ttu-id="4390d-175">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="4390d-175">Click **OK**.</span></span>
    
    <span data-ttu-id="4390d-p112">La columna de **detalle** se divide en varias columnas. Cada nueva columna se denomina **Detail.1**, **Detail.2**, **Detail.3**y así sucesivamente. Se puede observar que los valores de cada celda de las columnas **Detail.n** llevan el prefijo con el nombre de la propiedad; Por ejemplo, **Operación: SharingSet**, **SharingInvitationAccepted: operación**y **Operación: SharingInvitationCreated**.</span><span class="sxs-lookup"><span data-stu-id="4390d-p112">The **Detail** column is split into multiple columns. Each new column is named **Detail.1**, **Detail.2**, **Detail.3**, and so on. You'll notice the values in each cell in the **Detail.n** columns are prefixed with the name of the property; for example, **Operation:SharingSet**, **Operation:SharingInvitationAccepted**, and **Operation:SharingInvitationCreated**.</span></span>
    
    ![La columna de detalle se divide en varias columnas, uno para cada propiedad](media/4b104ead-0313-4bd4-b2a9-f143ccb378ac.png)
  
8. <span data-ttu-id="4390d-180">En la pestaña **archivo** , haga clic en **Cerrar &amp; carga** para cerrar el Editor de consultas y abra el archivo en un libro de Excel.</span><span class="sxs-lookup"><span data-stu-id="4390d-180">On the **File** tab, click **Close &amp; Load** to close the Query Editor and open the file in an Excel workbook.</span></span> 
    
    <span data-ttu-id="4390d-181">El siguiente paso es filtrar el archivo para mostrar únicamente los eventos **SharingSet** y **SharingInvitationCreated** .</span><span class="sxs-lookup"><span data-stu-id="4390d-181">The next step is to filter the file to only display the **SharingSet** and **SharingInvitationCreated** events.</span></span> 
    
9. <span data-ttu-id="4390d-182">Vaya a la ficha **Inicio** y, a continuación, seleccione la columna **acción** .</span><span class="sxs-lookup"><span data-stu-id="4390d-182">Go to the **Home** tab, and then select the **Action** column.</span></span> 
    
10. <span data-ttu-id="4390d-183">En la **ordenar &amp; filtro** lista desplegable, desactive todas las selecciones, a continuación, seleccione **SharingSet** y **SharingInvitationCreated**y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="4390d-183">In the **Sort &amp; Filter** drop-down list, clear all selections, then select **SharingSet** and **SharingInvitationCreated**, and click **OK**.</span></span>
    
    <span data-ttu-id="4390d-184">Excel muestra las filas para los eventos **SharingSet** y **SharingInvitationCreated** .</span><span class="sxs-lookup"><span data-stu-id="4390d-184">Excel displays the rows for the **SharingSet** and **SharingInvitationCreated** events.</span></span> 
    
11. <span data-ttu-id="4390d-185">Vaya a la columna con el nombre **Detail.17** (o la columna que contiene la propiedad **TargetUserOrGroupType** ) y selecciónelo.</span><span class="sxs-lookup"><span data-stu-id="4390d-185">Go to the column named **Detail.17** (or whichever column contains the **TargetUserOrGroupType** property) and select it.</span></span> 
    
12. <span data-ttu-id="4390d-186">En la **ordenar &amp; filtro** lista desplegable, desactive todas las selecciones, a continuación, seleccione **TargetUserOrGroupType:Guest**y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="4390d-186">In the **Sort &amp; Filter** drop-down list, clear all selections, then select **TargetUserOrGroupType:Guest**, and click **OK**.</span></span>
    
    <span data-ttu-id="4390d-187">Ahora Excel muestra las filas para los eventos de **SharingInvitationCreated** y **SharingSet** y donde el usuario de destino está fuera de la organización, debido a que los usuarios externos se identifican mediante el valor **TargetUserOrGroupType:Guest**.</span><span class="sxs-lookup"><span data-stu-id="4390d-187">Now Excel displays the rows for **SharingInvitationCreated** and **SharingSet** events AND where the target user is outside of your organization, because external users are identified by the value **TargetUserOrGroupType:Guest**.</span></span> 
    
<span data-ttu-id="4390d-188">La siguiente tabla muestran todos los usuarios de la organización que los recursos compartidos con un usuario invitado dentro de un intervalo de fechas especificado.</span><span class="sxs-lookup"><span data-stu-id="4390d-188">The following table shows all users in the organization who shared resources with a guest user within a specified date range.</span></span>
  
![Registro de auditoría de eventos de uso compartidos en Office 365](media/0e0ecbe3-c794-4ca6-a2ca-63478fb3bb34.png)
  
<span data-ttu-id="4390d-190">Aunque no se incluye en la tabla anterior, la columna **Detail.10** (o la columna que contiene la propiedad **ObjectId** ) identifica el recurso que se ha compartido con el usuario de destino; Por ejemplo `ObjectId:https:\/\/contoso-my.sharepoint.com\/personal\/sarad_contoso_com\/Documents\/Southwater Proposal.docx`.</span><span class="sxs-lookup"><span data-stu-id="4390d-190">Although it's not included in the previous table, the **Detail.10** column (or whichever column contains the **ObjectId** property) identifies the resource that was shared with the target user; for example  `ObjectId:https:\/\/contoso-my.sharepoint.com\/personal\/sarad_contoso_com\/Documents\/Southwater Proposal.docx`.</span></span>
  
> [!TIP]
> <span data-ttu-id="4390d-191">Si desea identificar cuando un usuario invitado se realmente asignó permisos para tener acceso a un recurso (en contraposición a sólo los recursos que where compartido con ellos), repita los pasos 10, 11 y 12 y filtrar la **SharingInvitationAccepted** y **SharingSet **eventos en el paso 10.</span><span class="sxs-lookup"><span data-stu-id="4390d-191">If you want to identify when a guest user was actually assigned permissions to access a resource (as opposed to just the resources that where shared with them), repeat Steps 10, 11, and 12, and filter on the **SharingInvitationAccepted** and **SharingSet** events in Step 10.</span></span> 
