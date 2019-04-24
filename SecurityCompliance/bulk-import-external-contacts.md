---
title: Importación masiva de contactos externos a Exchange Online
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/29/2018
ms.audience: End User
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOP150
ms.assetid: bed936bc-0969-4a6d-a7a5-66305c14e958
description: Obtenga información sobre cómo los administradores pueden usar Exchange Online PowerShell y un archivo CSV para importar de forma masiva contactos externos a la lista global de direcciones.
ms.openlocfilehash: 2948332d7cdf2d1364b2b563f94efdb3e8d0672d
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32244513"
---
# <a name="bulk-import-external-contacts-to-exchange-online"></a><span data-ttu-id="adaf3-103">Importación masiva de contactos externos a Exchange Online</span><span class="sxs-lookup"><span data-stu-id="adaf3-103">Bulk import external contacts to Exchange Online</span></span>

<span data-ttu-id="adaf3-104">**Este artículo está destinado a los administradores. ¿Está intentando importar contactos a su propio buzón? Consulte [Importar contactos a Outlook](https://support.office.com/article/bb796340-b58a-46c1-90c7-b549b8f3c5f8)**</span><span class="sxs-lookup"><span data-stu-id="adaf3-104">**This article is for administrators. Are you trying to import contacts to your own mailbox? See [Import contacts to Outlook](https://support.office.com/article/bb796340-b58a-46c1-90c7-b549b8f3c5f8)**</span></span>
   
<span data-ttu-id="adaf3-105">¿Su empresa tiene muchos contactos profesionales existentes que desea incluir en la libreta de direcciones compartida (también denominada lista global de direcciones) en Exchange Online?</span><span class="sxs-lookup"><span data-stu-id="adaf3-105">Does your company have lots of existing business contacts that you want to include in the shared address book (also called the global address list) in Exchange Online?</span></span> <span data-ttu-id="adaf3-106">¿Desea agregar contactos externos como miembros de grupos de distribución, exactamente igual que con los usuarios de su compañía?</span><span class="sxs-lookup"><span data-stu-id="adaf3-106">Do you want to add external contacts as members of distribution groups, just like you can with users inside your company?</span></span> <span data-ttu-id="adaf3-107">Si es así, puede usar Exchange Online PowerShell y un archivo CSV (valores separados por comas) para importar de forma masiva contactos externos en Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="adaf3-107">If so, you can use Exchange Online PowerShell and a CSV (Comma Separated Value) file to bulk import external contacts into Exchange Online.</span></span> <span data-ttu-id="adaf3-108">Se trata de un proceso de tres pasos:</span><span class="sxs-lookup"><span data-stu-id="adaf3-108">It's a three-step process:</span></span>
  
[<span data-ttu-id="adaf3-109">Paso 1: crear un archivo CSV que contenga información sobre los contactos externos</span><span class="sxs-lookup"><span data-stu-id="adaf3-109">Step 1: Create a CSV file that contains information about the external contacts</span></span>](#step-1-create-a-csv-file-that-contains-information-about-the-external-contacts)

[<span data-ttu-id="adaf3-110">Paso 2: crear los contactos externos con PowerShell</span><span class="sxs-lookup"><span data-stu-id="adaf3-110">Step 2: Create the external contacts with PowerShell</span></span>](#step-2-create-the-external-contacts-with-powershell) 

[<span data-ttu-id="adaf3-111">Paso 3: agregar información a las propiedades de los contactos externos</span><span class="sxs-lookup"><span data-stu-id="adaf3-111">Step 3: Add information to the properties of the external contacts</span></span>](#step-3-add-information-to-the-properties-of-the-external-contacts)

<span data-ttu-id="adaf3-112">Después de completar estos pasos para importar contactos, puede realizar estas tareas adicionales:</span><span class="sxs-lookup"><span data-stu-id="adaf3-112">After you complete these steps to import contacts, you can perform these additional tasks:</span></span>
  
- [<span data-ttu-id="adaf3-113">Agregar más contactos externos</span><span class="sxs-lookup"><span data-stu-id="adaf3-113">Add more external contacts</span></span>](#add-more-external-contacts)
  
- [<span data-ttu-id="adaf3-114">Ocultar contactos externos de la libreta de direcciones compartida</span><span class="sxs-lookup"><span data-stu-id="adaf3-114">Hide external contacts from the shared address book</span></span>](#hide-external-contacts-from-the-shared-address-book)
  
## <a name="step-1-create-a-csv-file-that-contains-information-about-the-external-contacts"></a><span data-ttu-id="adaf3-115">Paso 1: crear un archivo CSV que contenga información sobre los contactos externos</span><span class="sxs-lookup"><span data-stu-id="adaf3-115">Step 1: Create a CSV file that contains information about the external contacts</span></span>

<span data-ttu-id="adaf3-116">El primer paso consiste en crear un archivo CSV que contenga información sobre cada contacto externo que desee importar a Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="adaf3-116">The first step is to create a CSV file that contains information about each external contact that you want to import to Exchange Online.</span></span> 
  
1. <span data-ttu-id="adaf3-117">Copie el siguiente texto en un archivo de texto en el Bloc de notas y guárdelo en el escritorio como un archivo CSV con un sufijo de nombre de archivo de. csv; por ejemplo, ExternalContacts. csv.</span><span class="sxs-lookup"><span data-stu-id="adaf3-117">Copy the following text to a text file in NotePad, and save it to your desktop as a CSV file by using a filename suffix of .csv; for example, ExternalContacts.csv.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="adaf3-118">Si el idioma contiene caracteres especiales (como **å**, **ä**y **ö** en sueco), guarde el archivo CSV con codificación UTF-8 u otra codificación Unicode al guardar el archivo en el Bloc de notas.</span><span class="sxs-lookup"><span data-stu-id="adaf3-118">If your language contains special characters (such as **å**, **ä**, and **ö** in Swedish) save the CSV file with UTF-8 or other Unicode encoding when you save the file in NotePad.</span></span> 
  
    ```
    ExternalEmailAddress,Name,FirstName,LastName,StreetAddress,City,StateorProvince,PostalCode,Phone,MobilePhone,Pager,HomePhone,Company,Title,OtherTelephone,Department,CountryOrRegion,Fax,Initials,Notes,Office,Manager
    danp@fabrikam.com,Dan Park,Dan,Park,1234 23rd Ave,Golden,CO,80215,206-111-1234,303-900-1234,555-1212,123-456-7890,Fabrikam,Shipping clerk,555-5555,Shipping,US,123-4567,R.,Good worker,31/1663,Dan Park
    pilar@contoso.com,Pilar Pinilla,Pilar,Pinilla,1234 Main St.,Seattle,WA,98017,206-555-0100,206-555-0101,206-555-0102,206-555-1234,Contoso,HR Manager,206-555-0104,Executive,US,206-555-0105,P.,Technical decision maker,31/1000,Dan Park 
    ```

    <span data-ttu-id="adaf3-119">En la primera fila, o fila de encabezado, del archivo CSV se enumeran las propiedades de los contactos que se pueden usar al importarlos a Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="adaf3-119">The first row, or header row, of the CSV file lists the properties of contacts that can be used when you import them to Exchange Online.</span></span> <span data-ttu-id="adaf3-120">Cada nombre de propiedad está separado por una coma.</span><span class="sxs-lookup"><span data-stu-id="adaf3-120">Each property name is separated by a comma.</span></span> <span data-ttu-id="adaf3-121">Cada fila situada debajo de la fila de encabezado representa los valores de propiedad para importar un solo contacto externo.</span><span class="sxs-lookup"><span data-stu-id="adaf3-121">Each row under the header row represents the property values for importing a single external contact.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="adaf3-122">Este texto incluye datos de ejemplo, que se pueden eliminar.</span><span class="sxs-lookup"><span data-stu-id="adaf3-122">This text includes sample data, which you can delete.</span></span> <span data-ttu-id="adaf3-123">Pero no elimine ni cambie la primera fila (de encabezado).</span><span class="sxs-lookup"><span data-stu-id="adaf3-123">But don't delete or change the first (header) row.</span></span> <span data-ttu-id="adaf3-124">Contiene todas las propiedades de los contactos externos.</span><span class="sxs-lookup"><span data-stu-id="adaf3-124">It contains all of the properties for the external contacts.</span></span> 
  
2. <span data-ttu-id="adaf3-125">Abra el archivo CSV en Microsoft Excel para editar el archivo CSV porque es mucho más fácil usar Excel para editar el archivo CSV.</span><span class="sxs-lookup"><span data-stu-id="adaf3-125">Open the CSV file in Microsoft Excel to edit the CSV file because it's much easier to use Excel to edit the CSV file.</span></span>
    
3. <span data-ttu-id="adaf3-126">Cree una fila para cada contacto que desee importar a Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="adaf3-126">Create a row for each contact that you want to import to Exchange Online.</span></span> <span data-ttu-id="adaf3-127">ReLlenar tantas celdas como sea posible.</span><span class="sxs-lookup"><span data-stu-id="adaf3-127">Populate as many of the cells as possible.</span></span> <span data-ttu-id="adaf3-128">Esta información se mostrará en la libreta de direcciones compartida para cada contacto.</span><span class="sxs-lookup"><span data-stu-id="adaf3-128">This information will be displayed in the shared address book for each contact.</span></span> 
    
    > [!IMPORTANT]
    >  <span data-ttu-id="adaf3-129">Las siguientes propiedades (que son los primeros cuatro elementos de la fila de encabezado) son necesarias para crear un contacto externo y deben rellenarse en el archivo CSV: **ExternalEmailAddress**, **Name**, **FirstName**, **LastName**.</span><span class="sxs-lookup"><span data-stu-id="adaf3-129">The following properties (which are the first four items in the header row) are required to create an external contact and must be populated in the CSV file: **ExternalEmailAddress**, **Name**, **FirstName**, **LastName**.</span></span> <span data-ttu-id="adaf3-130">El comando de PowerShell que ejecutó en el paso 2 usará los valores de estas propiedades para crear los contactos.</span><span class="sxs-lookup"><span data-stu-id="adaf3-130">The PowerShell command that you run in Step 2 will use the values for these properties to create the contacts.</span></span> 

## <a name="step-2-create-the-external-contacts-with-powershell"></a><span data-ttu-id="adaf3-131">Paso 2: crear los contactos externos con PowerShell</span><span class="sxs-lookup"><span data-stu-id="adaf3-131">Step 2: Create the external contacts with PowerShell</span></span>

<span data-ttu-id="adaf3-132">El siguiente paso es usar el archivo CSV que creó en el paso 1 y PowerShell para importar de forma masiva los contactos externos que aparecen en el archivo CSV a Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="adaf3-132">The next step is to use the CSV file that you created in Step 1 and PowerShell to bulk import the external contacts listed in the CSV file to Exchange Online.</span></span> 
  
1.  <span data-ttu-id="adaf3-133">Conecte PowerShell a la organización de Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="adaf3-133">Connect PowerShell to your Exchange Online organization.</span></span> <span data-ttu-id="adaf3-134">Para obtener instrucciones paso a paso, consulte [conectarse a Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).</span><span class="sxs-lookup"><span data-stu-id="adaf3-134">For step-by-step instructions, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).</span></span> <span data-ttu-id="adaf3-135">Asegúrese de usar el nombre de usuario y la contraseña de su cuenta de administrador global de Office 365 cuando se conecte a Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="adaf3-135">Be sure to use the user name and password for your Office 365 global administrator account when you connect to Exchange Online PowerShell.</span></span> 
    
2. <span data-ttu-id="adaf3-136">Después de conectar PowerShell a Exchange Online, vaya a la carpeta escritorio donde guardó el archivo CSV en el paso 1; por ejemplo `C:\Users\Administrator\desktop`.</span><span class="sxs-lookup"><span data-stu-id="adaf3-136">After you connect PowerShell to Exchange Online, go to the desktop folder where you saved the CSV file in Step 1; for example `C:\Users\Administrator\desktop`.</span></span>
    
3. <span data-ttu-id="adaf3-137">Ejecute el siguiente comando para crear los contactos externos:</span><span class="sxs-lookup"><span data-stu-id="adaf3-137">Run the following command to create the external contacts:</span></span>

    ```
    Import-Csv .\ExternalContacts.csv|%{New-MailContact -Name $_.Name -DisplayName $_.Name -ExternalEmailAddress $_.ExternalEmailAddress -FirstName $_.FirstName -LastName $_.LastName}
    ```

    <span data-ttu-id="adaf3-138">Puede tardar un rato en crear los nuevos contactos, en función del número de importaciones que va a importar.</span><span class="sxs-lookup"><span data-stu-id="adaf3-138">It might take a while to create the new contacts, depending on how many you're importing.</span></span> <span data-ttu-id="adaf3-139">Cuando el comando termina de ejecutarse, PowerShell muestra una lista de los nuevos contactos que se crearon.</span><span class="sxs-lookup"><span data-stu-id="adaf3-139">When the command is finished running, PowerShell displays a list of the new contacts that were created.</span></span> 
    
4. <span data-ttu-id="adaf3-140">Para ver los nuevos contactos externos, vaya al centro de administración de Exchange (EAC) y, a \*\*\*\* \> continuación, haga clic en destinatarios y **contactos**.</span><span class="sxs-lookup"><span data-stu-id="adaf3-140">To view the new external contacts, go to the Exchange admin center (EAC), and then click **Recipients** \> **Contacts**.</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="adaf3-141">Para obtener instrucciones sobre cómo conectar con el EAC, vea [centro de administración de Exchange en Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=328197).</span><span class="sxs-lookup"><span data-stu-id="adaf3-141">For instructions for connecting to the EAC, see [Exchange admin center in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=328197).</span></span> 
  
5. <span data-ttu-id="adaf3-142">Si es necesario, \*\*\*\* ![haga clic en](media/O365-MDM-Policy-RefreshIcon.gif) actualizar icono de actualización para actualizar la lista y ver los contactos externos que se importaron.</span><span class="sxs-lookup"><span data-stu-id="adaf3-142">If necessary, click **Refresh** ![Refresh icon](media/O365-MDM-Policy-RefreshIcon.gif) to update the list and see the external contacts that were imported.</span></span> 
    
    <span data-ttu-id="adaf3-143">Los contactos importados aparecerán en la libreta de direcciones compartida en Outlook y Outlook en la Web.</span><span class="sxs-lookup"><span data-stu-id="adaf3-143">The imported contacts will appear in the shared address book in Outlook and Outlook on the web.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="adaf3-144">también puede ver los contactos en el centro de administración de Microsoft 365 yendo a **los** \> **contactos**de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="adaf3-144">You can also view the contacts in the Microsoft 365 admin center by going to **Users** \> **Contacts**.</span></span> 

## <a name="step-3-add-information-to-the-properties-of-the-external-contacts"></a><span data-ttu-id="adaf3-145">Paso 3: agregar información a las propiedades de los contactos externos</span><span class="sxs-lookup"><span data-stu-id="adaf3-145">Step 3: Add information to the properties of the external contacts</span></span>

<span data-ttu-id="adaf3-146">Después de ejecutar el comando en el paso 2, se crean los contactos externos, pero no contienen ninguna información de contacto u organización, que es la información de la mayoría de las celdas en el archivo CSV.</span><span class="sxs-lookup"><span data-stu-id="adaf3-146">After you run the command in Step 2, the external contacts are created, but they don't contain any of the contact or organization information, which is the information from the most of the cells in the CSV file.</span></span> <span data-ttu-id="adaf3-147">Esto se debe a que, al crear nuevos contactos externos, solo se rellenan las propiedades necesarias.</span><span class="sxs-lookup"><span data-stu-id="adaf3-147">This is because when you create new external contacts, only the required properties are populated.</span></span> <span data-ttu-id="adaf3-148">No se preocupe si no tiene toda la información rellenada en el archivo CSV.</span><span class="sxs-lookup"><span data-stu-id="adaf3-148">Don't worry if you don't have all the information populated in the CSV file.</span></span> <span data-ttu-id="adaf3-149">Si no está allí, no se agregará.</span><span class="sxs-lookup"><span data-stu-id="adaf3-149">If it's not there, it won't be added.</span></span>
  
1.  <span data-ttu-id="adaf3-150">Conecte PowerShell a la organización de Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="adaf3-150">Connect PowerShell to your Exchange Online organization.</span></span> <span data-ttu-id="adaf3-151">Para obtener instrucciones paso a paso, consulte [conectarse a Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).</span><span class="sxs-lookup"><span data-stu-id="adaf3-151">For step-by-step instructions, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).</span></span>
    
2. <span data-ttu-id="adaf3-152">Vaya a la carpeta escritorio donde guardó el archivo CSV en el paso 1; por ejemplo `C:\Users\Administrator\desktop`.</span><span class="sxs-lookup"><span data-stu-id="adaf3-152">Go to the desktop folder where you saved the CSV file in Step 1; for example `C:\Users\Administrator\desktop`.</span></span>
    
3. <span data-ttu-id="adaf3-153">Ejecute los dos comandos siguientes para agregar otras propiedades desde el archivo CSV a los contactos externos que creó en el paso 2.</span><span class="sxs-lookup"><span data-stu-id="adaf3-153">Run the following two commands to add the other properties from the CSV file to the external contacts that you created in Step 2.</span></span>
    
    ```
    $Contacts = Import-CSV .\ExternalContacts.csv
  
    ```

    ```
    $contacts | ForEach {Set-Contact $_.Name -StreetAddress $_.StreetAddress -City $_.City -StateorProvince $_.StateorProvince -PostalCode $_.PostalCode -Phone $_.Phone -MobilePhone $_.MobilePhone -Pager $_.Pager -HomePhone $_.HomePhone -Company $_.Company -Title $_.Title -OtherTelephone $_.OtherTelephone -Department $_.Department -Fax $_.Fax -Initials $_.Initials -Notes  $_.Notes -Office $_.Office -Manager $_.Manager}
    ```

    > [!NOTE]
    > <span data-ttu-id="adaf3-154">El parámetro _Manager_ puede ser problemático.</span><span class="sxs-lookup"><span data-stu-id="adaf3-154">The  _Manager_ parameter might be problematic.</span></span> <span data-ttu-id="adaf3-155">Si la celda está en blanco en el archivo CSV, recibirá un error y no se agregará ninguna información de la propiedad al contacto.</span><span class="sxs-lookup"><span data-stu-id="adaf3-155">If the cell is blank in the CSV file, you will get an error and none of the property information will be added to the contact.</span></span> <span data-ttu-id="adaf3-156">Si no necesita especificar un administrador, simplemente elimine ` -Manager $_.Manager ` del comando de PowerShell anterior.</span><span class="sxs-lookup"><span data-stu-id="adaf3-156">If you don't need to specify a manager, then just delete  ` -Manager $_.Manager ` from the previous PowerShell command.</span></span> 
  
    <span data-ttu-id="adaf3-157">Una vez más, puede tardar un rato en actualizar los contactos, en función de cuánto se importó en el paso 1.</span><span class="sxs-lookup"><span data-stu-id="adaf3-157">Again, it might take a while to update the contacts, depending on how many you imported in Step 1.</span></span> 
    
4. <span data-ttu-id="adaf3-158">Para comprobar que las propiedades se agregaron a los contactos:</span><span class="sxs-lookup"><span data-stu-id="adaf3-158">To verify that the properties were added to the contacts:</span></span> 
    
1. <span data-ttu-id="adaf3-159">En el EAC, vaya a **Destinatarios** \> **Contactos**.</span><span class="sxs-lookup"><span data-stu-id="adaf3-159">In the EAC, go to **Recipients** \> **Contacts**.</span></span>
    
2. <span data-ttu-id="adaf3-160">Haga clic en un contacto y, a continuación](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) , haga clic en **Editar** ![icono Editar para mostrar las propiedades del contacto.</span><span class="sxs-lookup"><span data-stu-id="adaf3-160">Click a contact and then click **Edit** ![Edit icon](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) to display the contact's properties.</span></span> 
    
<span data-ttu-id="adaf3-161">Y eso es todo.</span><span class="sxs-lookup"><span data-stu-id="adaf3-161">That's it!</span></span> <span data-ttu-id="adaf3-162">Los usuarios pueden ver los contactos y la información adicional en la libreta de direcciones de Outlook y Outlook en la Web.</span><span class="sxs-lookup"><span data-stu-id="adaf3-162">Users can see the contacts and the additional information in the address book Outlook and Outlook on the web.</span></span>
  
## <a name="add-more-external-contacts"></a><span data-ttu-id="adaf3-163">Agregar más contactos externos</span><span class="sxs-lookup"><span data-stu-id="adaf3-163">Add more external contacts</span></span>

<span data-ttu-id="adaf3-164">Puede repetir los pasos del 1 al paso 3 para agregar nuevos contactos externos en Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="adaf3-164">You can repeat Steps 1 through Step 3 to add new external contacts in Exchange Online.</span></span> <span data-ttu-id="adaf3-165">Usted o los usuarios de su empresa solo pueden agregar una nueva fila en el archivo CSV para el nuevo contacto.</span><span class="sxs-lookup"><span data-stu-id="adaf3-165">You or users in your company can just add a new row in the CSV file for the new contact.</span></span> <span data-ttu-id="adaf3-166">A continuación, puede ejecutar los comandos de PowerShell desde el paso 2 y el paso 3 para crear y agregar información a los nuevos contactos.</span><span class="sxs-lookup"><span data-stu-id="adaf3-166">Then you can run the PowerShell commands from Step 2 and Step 3 to create and add information to the new contacts.</span></span>
  
> [!NOTE]
> <span data-ttu-id="adaf3-167">Al ejecutar el comando para crear nuevos contactos, es posible que reciba un error que indica que los contactos que se crearon anteriormente ya existen.</span><span class="sxs-lookup"><span data-stu-id="adaf3-167">When you run the command to create new contacts, you might get an error saying that the contacts that were created earlier already exist.</span></span> <span data-ttu-id="adaf3-168">Sin embargo, se creará un nuevo contacto agregado al archivo CSV.</span><span class="sxs-lookup"><span data-stu-id="adaf3-168">But any new contact added to the CSV file is created.</span></span> 
  
## <a name="hide-external-contacts-from-the-shared-address-book"></a><span data-ttu-id="adaf3-169">Ocultar contactos externos de la dirección compartida book></span><span class="sxs-lookup"><span data-stu-id="adaf3-169">Hide external contacts from the shared address book></span></span>

<span data-ttu-id="adaf3-170">Es posible que algunas empresas solo usen contactos externos para que puedan agregarse como miembros de los grupos de distribución.</span><span class="sxs-lookup"><span data-stu-id="adaf3-170">Some companies may use external contacts only so they can be added as members of distribution groups.</span></span> <span data-ttu-id="adaf3-171">En este escenario, es posible que quiera ocultar los contactos externos de la libreta de direcciones compartida.</span><span class="sxs-lookup"><span data-stu-id="adaf3-171">In this scenario, they may want to hide external contacts from the shared address book.</span></span> <span data-ttu-id="adaf3-172">A continuación se describe cómo:</span><span class="sxs-lookup"><span data-stu-id="adaf3-172">Here's how:</span></span>
  
1.  <span data-ttu-id="adaf3-173">Conecte PowerShell a la organización de Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="adaf3-173">Connect PowerShell to your Exchange Online organization.</span></span> <span data-ttu-id="adaf3-174">Para obtener instrucciones paso a paso, consulte [conectarse a Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).</span><span class="sxs-lookup"><span data-stu-id="adaf3-174">For step-by-step instructions, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).</span></span>
    
2. <span data-ttu-id="adaf3-175">Para ocultar un solo contacto externo, ejecute el siguiente comando.</span><span class="sxs-lookup"><span data-stu-id="adaf3-175">To hide a single external contact, run the following command.</span></span>
    
    ```
    Set-MailContact <external contact> -HiddenFromAddressListsEnabled $true 
    ```
 
    <span data-ttu-id="adaf3-176">Por ejemplo, para ocultar Pilar Pinilla de la libreta de direcciones compartida, ejecute este comando:</span><span class="sxs-lookup"><span data-stu-id="adaf3-176">For example, to hide Pilar Pinilla from the shared address book, run this command:</span></span>

    ```
    Set-MailContact "Pilar Pinilla" -HiddenFromAddressListsEnabled $true
    ```
   
3. <span data-ttu-id="adaf3-177">Para ocultar todos los contactos externos de la libreta de direcciones compartida, ejecute este comando:</span><span class="sxs-lookup"><span data-stu-id="adaf3-177">To hide all external contacts from the shared address book, run this command:</span></span>

    ```
    Get-Contact -ResultSize unlimited -Filter {(RecipientTypeDetails -eq 'MailContact')} | Set-MailContact -HiddenFromAddressListsEnabled $true  
    ```

<span data-ttu-id="adaf3-178">Después de ocultarlos, los contactos externos no se muestran en la libreta de direcciones compartida, pero puede agregarlos como miembros de un grupo de distribución.</span><span class="sxs-lookup"><span data-stu-id="adaf3-178">After you hide them, external contacts aren't displayed in the shared address book, but you can still add them as members of a distribution group.</span></span>
