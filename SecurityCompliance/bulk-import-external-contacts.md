---
title: Contactos externos de importación masiva a Exchange Online
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/29/2018
ms.audience: End User
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOP150
ms.assetid: bed936bc-0969-4a6d-a7a5-66305c14e958
description: Obtenga información sobre cómo los administradores pueden utilizar Exchange Online PowerShell y un archivo CSV a masa importar contactos externos a la lista global de direcciones.
ms.openlocfilehash: 4bde56d49ccf94dc91993df90e1ae693e25c961a
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22535684"
---
# <a name="bulk-import-external-contacts-to-exchange-online"></a><span data-ttu-id="b10bb-103">Contactos externos de importación masiva a Exchange Online</span><span class="sxs-lookup"><span data-stu-id="b10bb-103">Bulk import external contacts to Exchange Online</span></span>

<span data-ttu-id="b10bb-104">**En este artículo está dirigido a administradores. ¿Está intentando importar contactos a su propio buzón de correo? Consulte [Importar contactos en Outlook](https://support.office.com/article/bb796340-b58a-46c1-90c7-b549b8f3c5f8)**</span><span class="sxs-lookup"><span data-stu-id="b10bb-104">**This article is for administrators. Are you trying to import contacts to your own mailbox? See [Import contacts to Outlook](https://support.office.com/article/bb796340-b58a-46c1-90c7-b549b8f3c5f8)**</span></span>
   
<span data-ttu-id="b10bb-p101">¿Su empresa tiene una gran cantidad de contactos profesionales existentes que desee incluir en la libreta de direcciones compartida (también denominada la lista global de direcciones) en Exchange Online? ¿Desea agregar contactos externos como miembros de grupos de distribución, como ocurre con los usuarios dentro de su compañía? Si por lo tanto, puede usar Exchange Online PowerShell y un archivo CSV (valores separados por comas) para masiva importar contactos externos a Exchange Online. Es un proceso de tres pasos:</span><span class="sxs-lookup"><span data-stu-id="b10bb-p101">Does your company have lots of existing business contacts that you want to include in the shared address book (also called the global address list) in Exchange Online? Do you want to add external contacts as members of distribution groups, just like you can with users inside your company? If so, you can use Exchange Online PowerShell and a CSV (Comma Separated Value) file to bulk import external contacts into Exchange Online. It's a three-step process:</span></span>
  
[<span data-ttu-id="b10bb-109">Paso 1: Crear un archivo CSV que contiene información acerca de los contactos externos</span><span class="sxs-lookup"><span data-stu-id="b10bb-109">Step 1: Create a CSV file that contains information about the external contacts</span></span>](#step-1-create-a-csv-file-that-contains-information-about-the-external-contacts)

[<span data-ttu-id="b10bb-110">Paso 2: Crear los contactos externos con PowerShell</span><span class="sxs-lookup"><span data-stu-id="b10bb-110">Step 2: Create the external contacts with PowerShell</span></span>](#step-2-create-the-external-contacts-with-powershell) 

[<span data-ttu-id="b10bb-111">Paso 3: Agregar información a las propiedades de los contactos externos</span><span class="sxs-lookup"><span data-stu-id="b10bb-111">Step 3: Add information to the properties of the external contacts</span></span>](#step-3-add-information-to-the-properties-of-the-external-contacts)

<span data-ttu-id="b10bb-112">Después de completar estos pasos para importar los contactos, puede realizar estas tareas adicionales:</span><span class="sxs-lookup"><span data-stu-id="b10bb-112">After you complete these steps to import contacts, you can perform these additional tasks:</span></span>
  
- [<span data-ttu-id="b10bb-113">Agregar contactos externos más</span><span class="sxs-lookup"><span data-stu-id="b10bb-113">Add more external contacts</span></span>](bulk-import-external-contacts.md#AddMore)
  
- [<span data-ttu-id="b10bb-114">Ocultar los contactos externos de la libreta de direcciones compartida</span><span class="sxs-lookup"><span data-stu-id="b10bb-114">Hide external contacts from the shared address book</span></span>](bulk-import-external-contacts.md#Hide)
  
## <a name="step-1-create-a-csv-file-that-contains-information-about-the-external-contacts"></a><span data-ttu-id="b10bb-115">Paso 1: Crear un archivo CSV que contiene información acerca de los contactos externos</span><span class="sxs-lookup"><span data-stu-id="b10bb-115">Step 1: Create a CSV file that contains information about the external contacts</span></span>

<span data-ttu-id="b10bb-116">El primer paso es crear un archivo CSV que contiene información acerca de cada contacto externo que desea importar a Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="b10bb-116">The first step is to create a CSV file that contains information about each external contact that you want to import to Exchange Online.</span></span> 
  
1. <span data-ttu-id="b10bb-117">Copie el siguiente texto en un archivo de texto en el Bloc de notas y guárdelo en el escritorio como un archivo CSV mediante el uso de un sufijo de nombre de archivo de .csv; Por ejemplo, ExternalContacts.csv.</span><span class="sxs-lookup"><span data-stu-id="b10bb-117">Copy the following text to a text file in NotePad, and save it to your desktop as a CSV file by using a filename suffix of .csv; for example, ExternalContacts.csv.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="b10bb-118">Si su idioma contiene caracteres especiales (por ejemplo, **ö** en sueco, **ä**y **å**) guardar el archivo CSV con UTF-8 u otra codificación Unicode cuando guarde el archivo en el Bloc de notas.</span><span class="sxs-lookup"><span data-stu-id="b10bb-118">If your language contains special characters (such as **å**, **ä**, and **ö** in Swedish) save the CSV file with UTF-8 or other Unicode encoding when you save the file in NotePad.</span></span> 
  
    ```
    ExternalEmailAddress,Name,FirstName,LastName,StreetAddress,City,StateorProvince,PostalCode,Phone,MobilePhone,Pager,HomePhone,Company,Title,OtherTelephone,Department,CountryOrRegion,Fax,Initials,Notes,Office,Manager
    danp@fabrikam.com,Dan Park,Dan,Park,1234 23rd Ave,Golden,CO,80215,206-111-1234,303-900-1234,555-1212,123-456-7890,Fabrikam,Shipping clerk,555-5555,Shipping,US,123-4567,R.,Good worker,31/1663,Dan Park
    pilar@contoso.com,Pilar Pinilla,Pilar,Pinilla,1234 Main St.,Seattle,WA,98017,206-555-0100,206-555-0101,206-555-0102,206-555-1234,Contoso,HR Manager,206-555-0104,Executive,US,206-555-0105,P.,Technical decision maker,31/1000,Dan Park 
    ```

    <span data-ttu-id="b10bb-p102">La primera fila o la fila de encabezado, del archivo CSV se enumera las propiedades de los contactos que se pueden usar al importar a Exchange Online. Cada nombre de la propiedad viene separada por una coma. Cada fila debajo de la fila de encabezado representa los valores de propiedad para la importación de un solo contacto externo.</span><span class="sxs-lookup"><span data-stu-id="b10bb-p102">The first row, or header row, of the CSV file lists the properties of contacts that can be used when you import them to Exchange Online. Each property name is separated by a comma. Each row under the header row represents the property values for importing a single external contact.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="b10bb-p103">Este texto incluye datos de ejemplo, que se puede eliminar. Pero no elimine o cambie la primera fila (encabezado). Contiene todas las propiedades para los contactos externos.</span><span class="sxs-lookup"><span data-stu-id="b10bb-p103">This text includes sample data, which you can delete. But don't delete or change the first (header) row. It contains all of the properties for the external contacts.</span></span> 
  
2. <span data-ttu-id="b10bb-125">Abra el archivo CSV en Microsoft Excel para editar el archivo CSV porque es mucho más sencillo utilizar Excel para editar el archivo CSV.</span><span class="sxs-lookup"><span data-stu-id="b10bb-125">Open the CSV file in Microsoft Excel to edit the CSV file because it's much easier to use Excel to edit the CSV file.</span></span>
    
3. <span data-ttu-id="b10bb-p104">Crear una fila para cada contacto que desea importar a Exchange Online. Rellenar como muchas de las celdas como sea posible. Esta información se mostrará en la libreta de direcciones compartida para cada contacto.</span><span class="sxs-lookup"><span data-stu-id="b10bb-p104">Create a row for each contact that you want to import to Exchange Online. Populate as many of the cells as possible. This information will be displayed in the shared address book for each contact.</span></span> 
    
    > [!IMPORTANT]
    >  <span data-ttu-id="b10bb-p105">Las siguientes propiedades (que son los cuatro primeros elementos en la fila de encabezado) son necesarias para crear un contacto externo y se debe rellenar en el archivo CSV: **ExternalEmailAddress**, **nombre**, **FirstName**, **LastName (apellidos)**. El comando de PowerShell que se ejecutan en el paso 2 usará los valores de estas propiedades para crear los contactos.</span><span class="sxs-lookup"><span data-stu-id="b10bb-p105">The following properties (which are the first four items in the header row) are required to create an external contact and must be populated in the CSV file: **ExternalEmailAddress**, **Name**, **FirstName**, **LastName**. The PowerShell command that you run in Step 2 will use the values for these properties to create the contacts.</span></span> 

## <a name="step-2-create-the-external-contacts-with-powershell"></a><span data-ttu-id="b10bb-131">Paso 2: Crear los contactos externos con PowerShell</span><span class="sxs-lookup"><span data-stu-id="b10bb-131">Step 2: Create the external contacts with PowerShell</span></span>

<span data-ttu-id="b10bb-132">El siguiente paso consiste en usar el archivo CSV que creó en el paso 1 y PowerShell a masiva importar los contactos externos que aparecen en el archivo CSV a Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="b10bb-132">The next step is to use the CSV file that you created in Step 1 and PowerShell to bulk import the external contacts listed in the CSV file to Exchange Online.</span></span> 
  
1.  <span data-ttu-id="b10bb-p106">Conectarse PowerShell a la organización de Exchange Online. Para obtener instrucciones detalladas, vea [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554). Asegúrese de usar el nombre de usuario y la contraseña de la cuenta de administrador global de Office 365 al conectarse a Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b10bb-p106">Connect PowerShell to your Exchange Online organization. For step-by-step instructions, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554). Be sure to use the user name and password for your Office 365 global administrator account when you connect to Exchange Online PowerShell.</span></span> 
    
2. <span data-ttu-id="b10bb-136">Tras conectarse a Exchange Online PowerShell, vaya a la carpeta escritorio donde guardó el archivo CSV en el paso 1. Por ejemplo `C:\Users\Administrator\desktop`.</span><span class="sxs-lookup"><span data-stu-id="b10bb-136">After you connect PowerShell to Exchange Online, go to the desktop folder where you saved the CSV file in Step 1; for example `C:\Users\Administrator\desktop`.</span></span>
    
3. <span data-ttu-id="b10bb-137">Ejecute el siguiente comando para crear los contactos externos:</span><span class="sxs-lookup"><span data-stu-id="b10bb-137">Run the following command to create the external contacts:</span></span>

    ```
    Import-Csv .\ExternalContacts.csv|%{New-MailContact -Name $_.Name -DisplayName $_.Name -ExternalEmailAddress $_.ExternalEmailAddress -FirstName $_.FirstName -LastName $_.LastName}
    ```

    <span data-ttu-id="b10bb-p107">Puede tardar unos momentos para crear nuevos contactos, dependiendo de cuántos va a importar. Cuando finalice el comando Ejecutar, PowerShell, muestra una lista de los nuevos contactos que se crearon.</span><span class="sxs-lookup"><span data-stu-id="b10bb-p107">It might take a while to create the new contacts, depending on how many you're importing. When the command is finished running, PowerShell displays a list of the new contacts that were created.</span></span> 
    
4. <span data-ttu-id="b10bb-140">Para ver los nuevos contactos externos, vaya al centro de administración de Exchange (EAC) y, a continuación, haga clic en **destinatarios** \> **contactos**.</span><span class="sxs-lookup"><span data-stu-id="b10bb-140">To view the new external contacts, go to the Exchange admin center (EAC), and then click **Recipients** \> **Contacts**.</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="b10bb-141">Para obtener instrucciones para conectar con el CEF, vea el [Centro de administración de Exchange en Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=328197).</span><span class="sxs-lookup"><span data-stu-id="b10bb-141">For instructions for connecting to the EAC, see [Exchange admin center in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=328197).</span></span> 
  
5. <span data-ttu-id="b10bb-142">Si es necesario, haga clic en **Actualizar** ![icono de actualización](media/O365-MDM-Policy-RefreshIcon.gif) para actualizar la lista y ver los contactos externos a los que se han importado.</span><span class="sxs-lookup"><span data-stu-id="b10bb-142">If necessary, click **Refresh** ![Refresh icon](media/O365-MDM-Policy-RefreshIcon.gif) to update the list and see the external contacts that were imported.</span></span> 
    
    <span data-ttu-id="b10bb-143">Los contactos importados aparecerán en la libreta de direcciones compartida en Outlook y Outlook en el web.</span><span class="sxs-lookup"><span data-stu-id="b10bb-143">The imported contacts will appear in the shared address book in Outlook and Outlook on the web.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="b10bb-144">También puede ver los contactos en el centro de administración de Office 365 yendo a **los usuarios** \> **contactos**.</span><span class="sxs-lookup"><span data-stu-id="b10bb-144">You can also view the contacts in the Office 365 admin center by going to **Users** \> **Contacts**.</span></span> 

## <a name="step-3-add-information-to-the-properties-of-the-external-contacts"></a><span data-ttu-id="b10bb-145">Paso 3: Agregar información a las propiedades de los contactos externos</span><span class="sxs-lookup"><span data-stu-id="b10bb-145">Step 3: Add information to the properties of the external contacts</span></span>

<span data-ttu-id="b10bb-p108">Después de ejecutar el comando en el paso 2, se crean los contactos externos, pero que no contienen la información de contacto o la organización, que es la información de la mayoría de las celdas en el archivo CSV. Esto es debido a que al crear nuevos contactos externos, se rellenan sólo las propiedades necesarias. No se preocupe si no dispone de toda la información que se rellena en el archivo CSV. Si no es así, no se agregará.</span><span class="sxs-lookup"><span data-stu-id="b10bb-p108">After you run the command in Step 2, the external contacts are created, but they don't contain any of the contact or organization information, which is the information from the most of the cells in the CSV file. This is because when you create new external contacts, only the required properties are populated. Don't worry if you don't have all the information populated in the CSV file. If it's not there, it won't be added.</span></span>
  
1.  <span data-ttu-id="b10bb-p109">Conectarse PowerShell a la organización de Exchange Online. Para obtener instrucciones detalladas, vea [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).</span><span class="sxs-lookup"><span data-stu-id="b10bb-p109">Connect PowerShell to your Exchange Online organization. For step-by-step instructions, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).</span></span>
    
2. <span data-ttu-id="b10bb-152">Vaya a la carpeta escritorio donde guardó el archivo CSV en el paso 1. Por ejemplo `C:\Users\Administrator\desktop`.</span><span class="sxs-lookup"><span data-stu-id="b10bb-152">Go to the desktop folder where you saved the CSV file in Step 1; for example `C:\Users\Administrator\desktop`.</span></span>
    
3. <span data-ttu-id="b10bb-153">Ejecute los dos comandos siguientes para agregar las demás propiedades del archivo CSV a los contactos externos a los que ha creado en el paso 2.</span><span class="sxs-lookup"><span data-stu-id="b10bb-153">Run the following two commands to add the other properties from the CSV file to the external contacts that you created in Step 2.</span></span>
    
    ```
    $Contacts = Import-CSV .\ExternalContacts.csv
  
    ```

    ```
    $contacts | ForEach {Set-Contact $_.Name -StreetAddress $_.StreetAddress -City $_.City -StateorProvince $_.StateorProvince -PostalCode $_.PostalCode -Phone $_.Phone -MobilePhone $_.MobilePhone -Pager $_.Pager -HomePhone $_.HomePhone -Company $_.Company -Title $_.Title -OtherTelephone $_.OtherTelephone -Department $_.Department -Fax $_.Fax -Initials $_.Initials -Notes  $_.Notes -Office $_.Office -Manager $_.Manager}
    ```

    > [!NOTE]
    > <span data-ttu-id="b10bb-p110">El parámetro _Manager_ podría ser un inconveniente. Si la celda está en blanco en el archivo CSV, recibirá un error y ninguno de los datos de propiedad se agregarán al contacto. Si no es necesario especificar un administrador, a continuación, simplemente elimine ` -Manager $_.Manager ` desde el anterior comando de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b10bb-p110">The  _Manager_ parameter might be problematic. If the cell is blank in the CSV file, you will get an error and none of the property information will be added to the contact. If you don't need to specify a manager, then just delete  ` -Manager $_.Manager ` from the previous PowerShell command.</span></span> 
  
    <span data-ttu-id="b10bb-157">Una vez más, puede tardar unos momentos para actualizar los contactos, dependiendo de cuántos ha importado en el paso 1.</span><span class="sxs-lookup"><span data-stu-id="b10bb-157">Again, it might take a while to update the contacts, depending on how many you imported in Step 1.</span></span> 
    
4. <span data-ttu-id="b10bb-158">Para comprobar que se han agregado las propiedades a los contactos:</span><span class="sxs-lookup"><span data-stu-id="b10bb-158">To verify that the properties were added to the contacts:</span></span> 
    
1. <span data-ttu-id="b10bb-159">En el EAC, vaya a **Destinatarios** \> **Contactos**.</span><span class="sxs-lookup"><span data-stu-id="b10bb-159">In the EAC, go to **Recipients** \> **Contacts**.</span></span>
    
2. <span data-ttu-id="b10bb-160">Haga clic en un contacto y, a continuación, haga clic en **Editar** ![icono Editar](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) para mostrar las propiedades del contacto.</span><span class="sxs-lookup"><span data-stu-id="b10bb-160">Click a contact and then click **Edit** ![Edit icon](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) to display the contact's properties.</span></span> 
    
<span data-ttu-id="b10bb-p111">¡Eso es todo! Los usuarios pueden ver los contactos y la información adicional en la libreta de direcciones de Outlook y Outlook en el web.</span><span class="sxs-lookup"><span data-stu-id="b10bb-p111">That's it! Users can see the contacts and the additional information in the address book Outlook and Outlook on the web.</span></span>
  
## <a name="add-more-external-contacts"></a><span data-ttu-id="b10bb-163">Agregar contactos externos más</span><span class="sxs-lookup"><span data-stu-id="b10bb-163">Add more external contacts</span></span>

<span data-ttu-id="b10bb-p112">Repita los pasos del 1 al paso 3 para agregar contactos externos nuevos en Exchange Online. Usted o los usuarios de su compañía sólo pueden agregar una nueva fila en el archivo CSV para el nuevo contacto. A continuación, puede ejecutar los comandos de PowerShell de paso 2 y paso 3 para crear y agregar información a los nuevos contactos.</span><span class="sxs-lookup"><span data-stu-id="b10bb-p112">You can repeat Steps 1 through Step 3 to add new external contacts in Exchange Online. You or users in your company can just add a new row in the CSV file for the new contact. Then you can run the PowerShell commands from Step 2 and Step 3 to create and add information to the new contacts.</span></span>
  
> [!NOTE]
> <span data-ttu-id="b10bb-p113">Cuando se ejecuta el comando para crear nuevos contactos, es posible que obtenga un error que indica que los contactos a los que se crearon anteriormente ya existen. Pero se crea cualquier contacto nuevo que se agrega al archivo CSV.</span><span class="sxs-lookup"><span data-stu-id="b10bb-p113">When you run the command to create new contacts, you might get an error saying that the contacts that were created earlier already exist. But any new contact added to the CSV file is created.</span></span> 
  
## <a name="hide-external-contacts-from-the-shared-address-book"></a><span data-ttu-id="b10bb-169">Ocultar los contactos externos de la libreta de direcciones compartida ></span><span class="sxs-lookup"><span data-stu-id="b10bb-169">Hide external contacts from the shared address book></span></span>

<span data-ttu-id="b10bb-p114">Algunas compañías pueden utilizar los contactos externos solo por lo que se pueden agregar como miembros de grupos de distribución. En este escenario, desean ocultar a los contactos externos de la libreta de direcciones compartida. Aquí es cómo:</span><span class="sxs-lookup"><span data-stu-id="b10bb-p114">Some companies may use external contacts only so they can be added as members of distribution groups. In this scenario, they may want to hide external contacts from the shared address book. Here's how:</span></span>
  
1.  <span data-ttu-id="b10bb-p115">Conectarse PowerShell a la organización de Exchange Online. Para obtener instrucciones detalladas, vea [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).</span><span class="sxs-lookup"><span data-stu-id="b10bb-p115">Connect PowerShell to your Exchange Online organization. For step-by-step instructions, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).</span></span>
    
2. <span data-ttu-id="b10bb-175">Para ocultar un solo contacto externo, ejecute el siguiente comando.</span><span class="sxs-lookup"><span data-stu-id="b10bb-175">To hide a single external contact, run the following command.</span></span>
    
    ```
    Set-MailContact <external contact> -HiddenFromAddressListsEnabled $true 
    ```
 
    <span data-ttu-id="b10bb-176">Por ejemplo, para ocultar Pilar Pinilla desde la libreta de direcciones compartida, ejecute este comando:</span><span class="sxs-lookup"><span data-stu-id="b10bb-176">For example, to hide Pilar Pinilla from the shared address book, run this command:</span></span>

    ```
    Set-MailContact "Pilar Pinilla" -HiddenFromAddressListsEnabled $true
    ```
   
3. <span data-ttu-id="b10bb-177">Para ocultar todos los contactos externos de la libreta de direcciones compartida, ejecute este comando:</span><span class="sxs-lookup"><span data-stu-id="b10bb-177">To hide all external contacts from the shared address book, run this command:</span></span>

    ```
    Get-Contact -ResultSize unlimited -Filter {(RecipientTypeDetails -eq 'MailContact')} | Set-MailContact -HiddenFromAddressListsEnabled $true  
    ```

<span data-ttu-id="b10bb-178">Después de ocultar ellos, contactos externos no se muestran en la libreta de direcciones compartida, pero puede agregarla como miembros de un grupo de distribución.</span><span class="sxs-lookup"><span data-stu-id="b10bb-178">After you hide them, external contacts aren't displayed in the shared address book, but you can still add them as members of a distribution group.</span></span>
