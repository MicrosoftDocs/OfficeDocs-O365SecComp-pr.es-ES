---
title: Usar una secuencia de comandos para agregar usuarios a una suspensión en un caso de exhibición de documentos electrónicos en la seguridad de Office 365 &amp; centro de cumplimiento
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 1/23/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.assetid: bad352ff-d5d2-45d8-ac2a-6cb832f10e73
description: Ejecutar un script para agregar rápidamente los buzones de correo y de sitios de OneDrive para la empresa a una nueva suspensión que está asociado con un caso de exhibición de documentos electrónicos en la seguridad de Office 365 &amp; centro de cumplimiento.
ms.openlocfilehash: eb53f01b4f1b7245e1411ac470db629115eb1ef5
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22536115"
---
# <a name="use-a-script-to-add-users-to-a-hold-in-an-ediscovery-case-in-the-office-365-security-amp-compliance-center"></a><span data-ttu-id="202b4-103">Usar una secuencia de comandos para agregar usuarios a una suspensión en un caso de exhibición de documentos electrónicos en la seguridad de Office 365 &amp; centro de cumplimiento</span><span class="sxs-lookup"><span data-stu-id="202b4-103">Use a script to add users to a hold in an eDiscovery case in the Office 365 Security &amp; Compliance Center</span></span>

<span data-ttu-id="202b4-p101">La seguridad de Office 365 &amp; centro de cumplimiento proporciona una gran cantidad de cmdlets de Windows PowerShell que permiten automatizar laboriosas tareas relacionadas con la creación y administración de casos de exhibición de documentos electrónicos. Actualmente, con la herramienta de casos de exhibición de documentos electrónicos en la seguridad &amp; centro de cumplimiento de normas para poner un gran número de ubicaciones de contenido de custodia en espera lleva tiempo y preparación. Por ejemplo, antes de crear una suspensión, se debe recopilar la dirección URL para cada OneDrive para el sitio de negocio que desee poner en espera. A continuación, para cada usuario que desee poner en espera, se debe agregar a su buzón y su OneDrive para el sitio de negocio a la suspensión. En futuras versiones de la seguridad &amp; centro de cumplimiento, esto se obtiene más fácil de hacer. Hasta entonces, puede utilizar la secuencia de comandos de este artículo para automatizar este proceso.</span><span class="sxs-lookup"><span data-stu-id="202b4-p101">The Office 365 Security &amp; Compliance Center provides lots of Windows PowerShell cmdlets that let you automate time-consuming tasks related to creating and managing eDiscovery cases. Currently, using the eDiscovery case tool in the Security &amp; Compliance Center to place a large number of custodian content locations on hold takes time and preparation. For example, before you create a hold, you have to collect the URL for each OneDrive for Business site that you want to place on hold. Then for each user you want to place on hold, you have to add their mailbox and their OneDrive for Business site to the hold. In future releases of the Security &amp; Compliance Center, this will get easier to do. Until then, you can use the script in this article to automate this process.</span></span>
  
<span data-ttu-id="202b4-p102">La secuencia de comandos le pide el nombre de dominio de Mi sitio de la organización (por ejemplo, **contoso** en la dirección URL https://contoso-my.sharepoint.com), el nombre de un caso de exhibición de documentos electrónicos existente, el nombre de la suspensión nuevo que asociado con el caso, una lista de direcciones de correo electrónico de los usuarios que desee. para poner en espera y una consulta de búsqueda que se utilizará si desea crear una suspensión basada en consultas. La secuencia de comandos, a continuación, obtiene la dirección URL para el OneDrive para sitio empresarial para cada usuario en la lista, crea la suspensión nuevo y, a continuación, agrega el buzón de correo y OneDrive para sitio empresarial para cada usuario en la lista a la suspensión. La secuencia de comandos también genera archivos de registro que contienen información acerca de la suspensión nuevo.</span><span class="sxs-lookup"><span data-stu-id="202b4-p102">The script prompts you for the name of your organization's MySite domain (for example, **contoso** in the URL https://contoso-my.sharepoint.com), the name of an existing eDiscovery case, the name of the new hold that associated with the case, a list of email addresses of the users you want to put on hold, and a search query to use if you want to create a query-based hold. The script then gets the URL for the OneDrive for Business site for each user in the list, creates the new hold, and then adds the mailbox and OneDrive for Business site for each user in the list to the hold. The script also generates log files that contain information about the new hold.</span></span> 
  
<span data-ttu-id="202b4-113">Estos son los pasos para que esto ocurra:</span><span class="sxs-lookup"><span data-stu-id="202b4-113">Here are the steps to make this happen:</span></span>
  
[<span data-ttu-id="202b4-114">Paso 1: Instalar el Shell de administración de SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="202b4-114">Step 1: Install the SharePoint Online Management Shell</span></span>](use-a-script-to-add-users-to-a-hold-in-ediscovery.md#step1)
  
[<span data-ttu-id="202b4-115">Paso 2: Generar una lista de usuarios</span><span class="sxs-lookup"><span data-stu-id="202b4-115">Step 2: Generate a list of users</span></span>](use-a-script-to-add-users-to-a-hold-in-ediscovery.md#step2)
  
[<span data-ttu-id="202b4-116">Paso 3: Ejecutar el script para crear una suspensión y agregar usuarios</span><span class="sxs-lookup"><span data-stu-id="202b4-116">Step 3: Run the script to create a hold and add users</span></span>](use-a-script-to-add-users-to-a-hold-in-ediscovery.md#step3)
  
## <a name="before-you-begin"></a><span data-ttu-id="202b4-117">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="202b4-117">Before you begin</span></span>

- <span data-ttu-id="202b4-p103">Tiene que ser un miembro del grupo de roles de administrador de exhibición de documentos electrónicos en la seguridad &amp; centro de cumplimiento y un administrador global de SharePoint Online para ejecutar el script en el paso 3. Para obtener más información, vea [asignar permisos de exhibición de documentos electrónicos en la seguridad de Office 365 &amp; centro de cumplimiento](assign-ediscovery-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="202b4-p103">You have to be a member of the eDiscovery Manager role group in the Security &amp; Compliance Center and a SharePoint Online global administrator to run the script in Step 3. For more information, see [Assign eDiscovery permissions in the Office‍ 365 Security &amp; Compliance Center](assign-ediscovery-permissions.md).</span></span>
    
- <span data-ttu-id="202b4-p104">Un máximo de 1.000 buzones de correo y 100 sitios puede agregarse a una suspensión a la que está asociado con un caso de exhibición de documentos electrónicos en la seguridad &amp; centro de cumplimiento. Suponiendo que todos los usuarios que desea poner en espera tienen un OneDrive para el sitio de negocio, puede agregar un máximo de 100 usuarios a una suspensión con la secuencia de comandos en este artículo.</span><span class="sxs-lookup"><span data-stu-id="202b4-p104">A maximum of 1,000 mailboxes and 100 sites can be added to a hold that's associated with an eDiscovery case in the Security &amp; Compliance Center. Assuming that every user that you want to place on hold has a OneDrive for Business site, you can add a maximum of 100 users to a hold using the script in this article.</span></span> 
    
- <span data-ttu-id="202b4-p105">Asegúrese de guardar la lista de usuarios que se crean en el paso 2 y la secuencia de comandos en el paso 3 en la misma carpeta. Que facilitan ejecutar el script.</span><span class="sxs-lookup"><span data-stu-id="202b4-p105">Be sure to save the list of users that you create in Step 2 and the script in Step 3 to the same folder. That will make it easier to run the script.</span></span>
    
- <span data-ttu-id="202b4-p106">La secuencia de comandos agrega la lista de usuarios a una suspensión nueva que está asociada con un caso existente. Asegúrese de que se crea el caso de que se va a asociar la suspensión con antes de ejecutar la secuencia de comandos.</span><span class="sxs-lookup"><span data-stu-id="202b4-p106">The script adds the list of users to a new hold that is associated with an existing case. Be sure the case that you want to associate the hold with is created before you run the script.</span></span>
    
- <span data-ttu-id="202b4-p107">La secuencia de comandos incluye el tratamiento de errores mínima. Su objetivo principal es rápida y fácilmente colocar el buzón de correo y OneDrive para el sitio de negocio de cada usuario en suspensión.</span><span class="sxs-lookup"><span data-stu-id="202b4-p107">The script includes minimal error handling. Its primary purpose is to quickly and easily place the mailbox and OneDrive for Business site of each user on hold.</span></span>
    
- <span data-ttu-id="202b4-p108">Las secuencias de comandos de ejemplo proporcionados en este tema no son compatibles con cualquier servicio o programa de soporte estándar de Microsoft. Las secuencias de comandos de ejemplo se proporcionan tal cual sin garantía de ningún tipo. Microsoft renuncia a todas las garantías implícitas incluidas, sin limitación, cualquier las garantías implícitas de comerciabilidad o de idoneidad para un fin determinado. Todo el riesgo que pueda surgir por el uso o el rendimiento de las secuencias de comandos de ejemplo y documentación permanece con usted. En ningún caso Microsoft, sus autores o cualquier otro implicado en la creación, producción o entrega de las secuencias de comandos serán responsables de los daños índole (incluidos, pero sin limitarse a, daños por pérdida de beneficios empresariales, interrupción del negocio, pérdida de información de la empresa, o en otras pérdidas de carácter económico) derivado del uso o la incapacidad de usar los scripts de ejemplo o documentación, aunque Microsoft haya sido notificado de la posibilidad de dichos daños.</span><span class="sxs-lookup"><span data-stu-id="202b4-p108">The sample scripts provided in this topic aren't supported under any Microsoft standard support program or service. The sample scripts are provided AS IS without warranty of any kind. Microsoft further disclaims all implied warranties including, without limitation, any implied warranties of merchantability or of fitness for a particular purpose. The entire risk arising out of the use or performance of the sample scripts and documentation remains with you. In no event shall Microsoft, its authors, or anyone else involved in the creation, production, or delivery of the scripts be liable for any damages whatsoever (including, without limitation, damages for loss of business profits, business interruption, loss of business information, or other pecuniary loss) arising out of the use of or inability to use the sample scripts or documentation, even if Microsoft has been advised of the possibility of such damages.</span></span>

## <a name="step-1-install-the-sharepoint-online-management-shell"></a><span data-ttu-id="202b4-133">Paso 1: Instalar el Shell de administración de SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="202b4-133">Step 1: Install the SharePoint Online Management Shell</span></span>

<span data-ttu-id="202b4-p109">El primer paso es instalar la consola de administración en línea de SharePoint si no está ya está instalado en el equipo local. No tiene que usar el shell en este procedimiento, pero debe instalarlo porque contiene los requisitos previos necesarios para la secuencia de comandos que se ejecutan en el paso 3. Estos requisitos previos de permiten la secuencia de comandos para comunicarse con SharePoint Online para obtener las direcciones URL para el OneDrive para sitios de negocio.</span><span class="sxs-lookup"><span data-stu-id="202b4-p109">The first step is to install the SharePoint Online Management Shell if it's not already installed on your local computer. You don't have to use the shell in this procedure, but you have to install it because it contains pre-requisites required by the script that you run in Step 3. These prerequisites allow the script to communicate with SharePoint Online to get the URLs for the OneDrive for Business sites.</span></span>
  
<span data-ttu-id="202b4-137">Vaya a [Configurar el entorno de SharePoint Online Management Shell de Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkID=286318) y realice el paso 1 y paso 2 para instalar la consola de administración de SharePoint Online en el equipo local.</span><span class="sxs-lookup"><span data-stu-id="202b4-137">Go to [Set up the SharePoint Online Management Shell Windows PowerShell environment](https://go.microsoft.com/fwlink/p/?LinkID=286318) and perform Step 1 and Step 2 to install the SharePoint Online Management Shell on your local computer.</span></span> 

## <a name="step-2-generate-a-list-of-users"></a><span data-ttu-id="202b4-138">Paso 2: Generar una lista de usuarios</span><span class="sxs-lookup"><span data-stu-id="202b4-138">Step 2: Generate a list of users</span></span>
<span data-ttu-id="202b4-139"><a name="step2"> </a></span><span class="sxs-lookup"><span data-stu-id="202b4-139"></span></span>

<span data-ttu-id="202b4-p110">La secuencia de comandos en el paso 3 creará una suspensión a la que está asociado con un caso de exhibición de documentos electrónicos y la adición de los buzones y OneDrive para sitios de profesionales de una lista de los usuarios a la suspensión. Sólo puede escribir las direcciones de correo electrónico en un archivo de texto, o puede ejecutar un comando de Windows PowerShell para obtener una lista de direcciones de correo electrónico y guardarlos en un archivo (que se encuentra en la misma carpeta que se va a guardar la secuencia de comandos en el paso 3).</span><span class="sxs-lookup"><span data-stu-id="202b4-p110">The script in Step 3 will create a hold that's associated with an eDiscovery case, and the add the mailboxes and OneDrive for Business sites of a list of users to the hold. You can just type the email addresses in a text file, or you can run a command in Windows PowerShell to get a list of email addresses and save them to a file (located in same folder that you'll save the script to in Step 3).</span></span>
  
<span data-ttu-id="202b4-142">Este es un comando de PowerShell (que se ejecuta mediante el uso de PowerShell remoto conectado a la organización de Exchange Online) obtener una lista de direcciones de correo electrónico para todos los usuarios de su organización y guárdelo en un archivo de texto denominado HoldUsers.txt.</span><span class="sxs-lookup"><span data-stu-id="202b4-142">Here's a PowerShell command (that you run by using remote PowerShell connected to your Exchange Online organization) to get a list of email addresses for all users in your organization and save it to a text file named HoldUsers.txt.</span></span>
  
```
Get-Mailbox -ResultSize unlimited -Filter { RecipientTypeDetails -eq 'UserMailbox'} | Select-Object PrimarySmtpAddress > HoldUsers.txt
```

<span data-ttu-id="202b4-p111">Después de ejecutar este comando, abra el archivo de texto y quitar el encabezado que contiene el nombre de la propiedad, `PrimarySmtpAddress`. A continuación, quite todas las direcciones de correo electrónico, excepto las de los usuarios que desea agregar a la suspensión que creará en el paso 3. Asegúrese de que no hay ninguna fila en blanco antes o después de la lista de direcciones de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="202b4-p111">After you run this command, open the text file and remove the header that contains the property name,  `PrimarySmtpAddress`. Then remove all email addresses except the ones for the users that you want to add to the hold that you'll create in Step 3. Make sure there are no blank rows before or after the list of email addresses.</span></span>
  

  
## <a name="step-3-run-the-script-to-create-a-hold-and-add-users"></a><span data-ttu-id="202b4-146">Paso 3: Ejecutar el script para crear una suspensión y agregar usuarios</span><span class="sxs-lookup"><span data-stu-id="202b4-146">Step 3: Run the script to create a hold and add users</span></span>
<span data-ttu-id="202b4-147"><a name="step3"> </a></span><span class="sxs-lookup"><span data-stu-id="202b4-147"></span></span>

<span data-ttu-id="202b4-p112">Cuando se ejecuta la secuencia de comandos en este paso, le pedirá la siguiente información. Asegúrese de que tiene esta información lista antes de ejecutar la secuencia de comandos.</span><span class="sxs-lookup"><span data-stu-id="202b4-p112">When you run the script in this step, it will prompt you for the following information. Be sure to have this information ready before you run the script.</span></span>
  
- <span data-ttu-id="202b4-p113">**Sus credenciales de usuario** : la secuencia de comandos usará las credenciales para conectarse a la seguridad &amp; centro de cumplimiento con PowerShell remoto. También utilizará estas credenciales para tener acceso a SharePoint Online para obtener el OneDrive para direcciones URL de negocio para la lista de usuarios.</span><span class="sxs-lookup"><span data-stu-id="202b4-p113">**Your user credentials** - The script will use your credentials to connect to the Security &amp; Compliance Center with remote PowerShell. It will also use these credentials to access SharePoint Online to get the OneDrive for Business URLs for the list of users.</span></span>
    
- <span data-ttu-id="202b4-p114">**Nombre de su dominio de Mi sitio** - misitio el dominio es el dominio que contiene la de OneDrive para sitios de profesionales de la organización. Por ejemplo, si la dirección URL para su dominio de Mi sitio es **https://contoso-my.sharepoint.com**, a continuación, deberá escribir `contoso` cuando la secuencia de comandos le pide el nombre de su dominio de Mi sitio.</span><span class="sxs-lookup"><span data-stu-id="202b4-p114">**Name of your MySite domain** - The MySite domain is the domain that contains all the OneDrive for Business sites in your organization. For example, if the URL for your MySite domain is **https://contoso-my.sharepoint.com**, then you would enter  `contoso` when the script prompts you for the name of your MySite domain.</span></span> 
    
- <span data-ttu-id="202b4-p115">**Nombre del caso** - el nombre de un caso existente. La secuencia de comandos creará una nueva suspensión que está asociada con este caso.</span><span class="sxs-lookup"><span data-stu-id="202b4-p115">**Name of the case** - The name of an existing case. The script will create a new hold that is associated with this case.</span></span>
    
- <span data-ttu-id="202b4-156">**Nombre de la suspensión** - el nombre de la suspensión de la secuencia de comandos creará y asociar con el caso especificado.</span><span class="sxs-lookup"><span data-stu-id="202b4-156">**Name of the hold** - The name of the hold the script will create and associate with the specified case.</span></span>
    
- <span data-ttu-id="202b4-p116">**Mantenga presionada la consulta de búsqueda para una consulta-based** - puede crear una suspensión basada en consultas para que sólo el contenido que cumpla los criterios de búsqueda especificado se pondrá en espera. Para poner todo el contenido en espera, simplemente, presione **ENTRAR** cuando se le solicite para una consulta de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="202b4-p116">**Search query for a query-based hold** - You can create a query-based hold so that only the content that meets the specified search criteria is placed on hold. To place all content on hold, just press **Enter** when you're prompted for a search query.</span></span> 
    
- <span data-ttu-id="202b4-p117">**Si desea activar la suspensión** - puede tener la secuencia de comandos activar la suspensión después de crearla o puede hacer que la secuencia de comandos cree la suspensión sin habilitarla. Si no dispone de la secuencia de comandos activar la suspensión, puede activarlo más adelante en la seguridad &amp; centro de cumplimiento o mediante la ejecución de los siguientes comandos de PowerShell:</span><span class="sxs-lookup"><span data-stu-id="202b4-p117">**Whether or not to turn the hold on** - You can have the script turn the hold on after it's created or you can have the script create the hold without enabling it. If you don't have the script turn on the hold, you can turn it on later in the Security &amp; Compliance Center or by running the following PowerShell commands:</span></span> 
    
  ```
  Set-CaseHoldPolicy -Identity <name of the hold> -Enabled $true
  ```

  ```
  Set-CaseHoldRule -Identity <name of the hold> -Disabled $false
  ```

- <span data-ttu-id="202b4-p118">**Nombre del archivo de texto con la lista de usuarios** : el nombre del archivo de texto del paso 2 que contiene la lista de usuarios para agregar a la suspensión. Si este archivo se encuentra en la misma carpeta que la secuencia de comandos, simplemente escriba el nombre del archivo (por ejemplo, HoldUsers.txt). Si el archivo de texto está en otra carpeta, escriba la ruta de acceso completa del archivo.</span><span class="sxs-lookup"><span data-stu-id="202b4-p118">**Name of the text file with the list of users** - The name of the text file from Step 2 that contains the list of users to add to the hold. If this file is located in the same folder as the script, just type the name of the file (for example, HoldUsers.txt). If the text file is in another folder, type the full pathname of the file.</span></span>
    
<span data-ttu-id="202b4-164">Una vez recopilada la información que la secuencia de comandos le pedirá, es el paso final ejecutar el script para crear la nueva suspensión y agregar usuarios a ella.</span><span class="sxs-lookup"><span data-stu-id="202b4-164">After you've collected the information that the script will prompt you for, the final step is to run the script to create the new hold and add users to it.</span></span>
  
1. <span data-ttu-id="202b4-165">Guarde el siguiente texto en un archivo de secuencia de comandos de Windows PowerShell mediante el uso de un sufijo de nombre de archivo de. ps1; Por ejemplo, `AddUsersToHold.ps1`.</span><span class="sxs-lookup"><span data-stu-id="202b4-165">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `AddUsersToHold.ps1`.</span></span>
    
  ```
  #script begin
  " " 
  write-host "***********************************************"
  write-host "   Office 365 Security &amp; Compliance Center   " -foregroundColor yellow -backgroundcolor darkgreen
  write-host "   eDiscovery cases - Add users to a hold   " -foregroundColor yellow -backgroundcolor darkgreen 
  write-host "***********************************************"
  " " 
  # Get user credentials &amp; Connect to Office 365 SCC, SPO
  $credentials = Get-Credential -Message "Specify your credentials to connect to the Office 365 Security &amp; Compliance Center and SharePoint Online"
  $s = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri "https://ps.compliance.protection.outlook.com/powershell-liveid" -Credential $credentials -Authentication Basic -AllowRedirection -SessionOption (New-PSSessionOption -SkipCACheck -SkipCNCheck -SkipRevocationCheck)
  $a = Import-PSSession $s -AllowClobber
      if (!$s)
      {
          Write-Error "Couldn't create PowerShell session."
          return;
      }
  # Load the SharePoint assemblies from the SharePoint Online Management Shell
  # To install, go to http://go.microsoft.com/fwlink/p/?LinkId=255251
  if (!$SharePointClient -or !$SPRuntime -or !$SPUserProfile)
  {
      $SharePointClient = [System.Reflection.Assembly]::LoadWithPartialName("Microsoft.SharePoint.Client")
      $SPRuntime = [System.Reflection.Assembly]::LoadWithPartialName("Microsoft.SharePoint.Client.Runtime")
      $SPUserProfile = [System.Reflection.Assembly]::LoadWithPartialName("Microsoft.SharePoint.Client.UserProfiles")
      if (!$SharePointClient)
      {
          Write-Error "The SharePoint Online Management Shell isn't installed. Please install it from: http://go.microsoft.com/fwlink/p/?LinkId=255251 and then re-run this script."
          return;
      }
  }
  if (!$spCreds)
  {
      $spCreds = New-Object Microsoft.SharePoint.Client.SharePointOnlineCredentials($credentials.UserName, $credentials.Password)
  }
  # Get the user's MySite domain name. We use this to create the admin URL and root URL for OneDrive for Business
  ""
  $mySiteDomain = Read-Host "Enter the name of your organization's MySite domain. For example, 'contoso' for 'https://contoso-my.sharepoint.com'"
  ""
  # Get other required information
  do{
  $casename = Read-Host "Enter the name of the case"
  $caseexists = (get-compliancecase -identity "$casename" -erroraction SilentlyContinue).isvalid
  if($caseexists -ne 'True')
  {""
  write-host "A case named '$casename' doesn't exist. Please specify the name of an existing case, or create a new case and then re-run the script." -foregroundColor Yellow
  ""}
  }While($caseexists -ne 'True')
  ""
  do{
  $holdName = Read-Host "Enter the name of the new hold"
  $holdexists=(get-caseholdpolicy -identity "$holdname" -case "$casename" -erroraction SilentlyContinue).isvalid
  if($holdexists -eq 'True')
  {""
  write-host "A hold named '$holdname' already exists. Please specify a new hold name." -foregroundColor Yellow
  ""}
  }While($holdexists -eq 'True')
  ""
  $holdQuery = Read-Host "Enter a search query to create a query-based hold, or press Enter to hold all content"
  ""
  $holdstatus = read-host "Do you want the hold enabled after it's created? (Yes/No)"
  do{
  ""
  $inputfile = read-host "Enter the name of the text file that contains the email addresses of the users to add to the hold"
  ""
  $fileexists = test-path -path $inputfile
  if($fileexists -ne 'True'){write-host "$inputfile doesn't exist. Please enter a valid file name." -foregroundcolor Yellow}
  }while($fileexists -ne 'True')
  #Import the list of addresses from the txt file.  Trim any excess spaces and make sure all addresses 
      #in the list are unique.
    [array]$emailAddresses = Get-Content $inputfile -ErrorAction SilentlyContinue | where {$_.trim() -ne ""}  | foreach{ $_.Trim() }
    [int]$dupl = $emailAddresses.count
    [array]$emailAddresses = $emailAddresses | select-object -unique
    $dupl -= $emailAddresses.count
  #Validate email addresses so the hold creation does not run in to an error.
  if($emailaddresses.count -gt 0){
  write-host ($emailAddresses).count "addresses were found in the text file. There were $dupl duplicate entries in the file." -foregroundColor Yellow
  ""
  Write-host "Validating the email addresses. Please wait..." -foregroundColor Yellow
  ""
  $finallist =@()
  foreach($emailAddress in $emailAddresses)
  {
  if((get-recipient $emailaddress -erroraction SilentlyContinue).isvalid -eq 'True')
  {$finallist += $emailaddress}
  else {"Unable to find the user $emailaddress"
  [array]$excludedlist += $emailaddress}
  }
  ""
  #find user's OneDrive Site URL using email address
  Write-Host "Getting the URL for each user's OneDrive for Business site." -foregroundColor Yellow
  ""
  $AdminUrl = "https://$mySiteDomain-admin.sharepoint.com"
  $mySiteUrlRoot = "https://$mySiteDomain-my.sharepoint.com"
  # Add the path of the User Profile Service to the SPO admin URL, then create a new webservice proxy to access it
  $proxyaddr = "$AdminUrl/_vti_bin/UserProfileService.asmx?wsdl"
  $UserProfileService= New-WebServiceProxy -Uri $proxyaddr -UseDefaultCredential False
  $UserProfileService.Credentials = $credentials
  # Take care of auth cookies
  $strAuthCookie = $spCreds.GetAuthenticationCookie($AdminUrl)
  $uri = New-Object System.Uri($AdminUrl)
  $container = New-Object System.Net.CookieContainer
  $container.SetCookies($uri, $strAuthCookie)
  $UserProfileService.CookieContainer = $container
  $urls = @()
  foreach($emailAddress in $emailAddresses)
  {
        try{
          $prop = $UserProfileService.GetUserProfileByName("i:0#.f|membership|$emailAddress") | Where-Object { $_.Name -eq "PersonalSpace" }
          $url = $prop.values[0].value
        if($url -ne $null){
          $furl = $mySiteUrlRoot + $url
          $urls += $furl
          Write-Host "- $emailAddress => $furl"
        [array]$ODadded += $furl}
    else{    
          Write-Warning "Couldn't locate OneDrive for $emailAddress"
        [array]$ODExluded += $emailAddress
      }}
    catch { 
    Write-Warning "Could not locate OneDrive for $emailAddress"
    [array]$ODExluded += $emailAddress
    Continue }
  }
  if(($finallist.count -gt 0) -or ($urls.count -gt 0)){
  ""
  Write-Host "Creating the hold named $holdname. Please wait..." -foregroundColor Yellow
  if(($holdstatus -eq "Y") -or ($holdstatus -eq  "y") -or ($holdstatus -eq "yes") -or ($holdstatus -eq "YES")){
  New-CaseHoldPolicy -Name "$holdName" -Case "$casename" -ExchangeLocation $finallist -SharePointLocation $urls -Enabled $True | out-null
  New-CaseHoldRule -Name "$holdName" -Policy "$holdname" -ContentMatchQuery $holdQuery | out-null
  }
  else{
  New-CaseHoldPolicy -Name "$holdName" -Case "$casename" -ExchangeLocation $finallist -SharePointLocation $urls -Enabled $false | out-null
  New-CaseHoldRule -Name "$holdName" -Policy "$holdname" -ContentMatchQuery $holdQuery -disabled $true | out-null
  }
  ""
  }
  else {"No valid locations were identified. Therefore, the hold wasn't created."}
  #write log files (if needed)
  $newhold=Get-CaseHoldPolicy -Identity "$holdname" -Case "$casename" -erroraction SilentlyContinue
  $newholdrule=Get-CaseHoldRule -Identity "$holdName" -erroraction SilentlyContinue
  if(($ODAdded.count -gt 0) -or ($ODExluded.count -gt 0) -or ($finallist.count -gt 0) -or ($excludedlist.count -gt 0) -or ($newhold.isvalid -eq 'True') -or ($newholdrule.isvalid -eq 'True'))
  {
  Write-Host "Generating output files..." -foregroundColor Yellow
  if($ODAdded.count -gt 0){
  "OneDrive Locations" | add-content .\LocationsOnHold.txt
  "==================" | add-content .\LocationsOnHold.txt 
  $newhold.SharePointLocation.name | add-content .\LocationsOnHold.txt}
  if($ODExluded.count -gt 0){ 
  "Users without OneDrive locations" | add-content .\LocationsNotOnHold.txt
  "================================" | add-content .\LocationsNotOnHold.txt
  $ODExluded | add-content .\LocationsNotOnHold.txt}
  if($finallist.count -gt 0){
  " " | add-content .\LocationsOnHold.txt
  "Exchange Locations" | add-content .\LocationsOnHold.txt
  "==================" | add-content .\LocationsOnHold.txt 
  $newhold.ExchangeLocation.name | add-content .\LocationsOnHold.txt}
  if($excludedlist.count -gt 0){
  " "| add-content .\LocationsNotOnHold.txt
  "Mailboxes not added to the hold" | add-content .\LocationsNotOnHold.txt
  "===============================" | add-content .\LocationsNotOnHold.txt
  $excludedlist | add-content .\LocationsNotOnHold.txt}
  $FormatEnumerationLimit=-1
  if($newhold.isvalid -eq 'True'){$newhold|fl >.\GetCaseHoldPolicy.txt}
  if($newholdrule.isvalid -eq 'True'){$newholdrule|Fl >.\GetCaseHoldRule.txt}
  }
  }
  else {"The hold wasn't created because no valid entries were found in the text file."}
  ""
  Write-host "Script complete!" -foregroundColor Yellow
  ""
  #script end
  ```

2. <span data-ttu-id="202b4-166">En el equipo local, abra Windows PowerShell y vaya a la carpeta donde guardó la secuencia de comandos.</span><span class="sxs-lookup"><span data-stu-id="202b4-166">On your local computer, open Windows PowerShell and go to the folder where you saved the script.</span></span>
    
3. <span data-ttu-id="202b4-167">Ejecute la secuencia de comandos; Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="202b4-167">Run the script; for example:</span></span>
    
      ```
    .\AddUsersToHold.ps1
      ```

4. <span data-ttu-id="202b4-168">Escriba la información que le pide la secuencia de comandos.</span><span class="sxs-lookup"><span data-stu-id="202b4-168">Enter the information that the script prompts you for.</span></span>
    
    <span data-ttu-id="202b4-p119">La secuencia de comandos se conecta a seguridad & PowerShell de centro de cumplimiento y, a continuación, crea la suspensión nuevo en el caso de exhibición de documentos electrónicos y agrega los buzones y OneDrive para la empresa para los usuarios de la lista. Puede ir a las mayúsculas y minúsculas en la página de **exhibición de documentos electrónicos** en la seguridad &amp; centro de cumplimiento para ver la suspensión nuevo.</span><span class="sxs-lookup"><span data-stu-id="202b4-p119">The script connects to Security & Compliance Center PowerShell, and then creates the new hold in the eDiscovery case and adds the mailboxes and OneDrive for Business for the users in the list. You can go to the case on the **eDiscovery** page in the Security &amp; Compliance Center to view the new hold.</span></span> 
    
<span data-ttu-id="202b4-171">Una vez finalizada la secuencia de comandos que se ejecuta, lo crea los siguientes archivos de registro y los guarda en la carpeta donde se encuentra la secuencia de comandos.</span><span class="sxs-lookup"><span data-stu-id="202b4-171">After the script is finished running, it creates the following log files, and saves them to the folder where the script is located.</span></span>
  
- <span data-ttu-id="202b4-172">**LocationsOnHold.txt** - contiene una lista de buzones de correo y OneDrive para los sitios de negocio que la secuencia de comandos correctamente colocado en suspensión.</span><span class="sxs-lookup"><span data-stu-id="202b4-172">**LocationsOnHold.txt** - Contains a list of mailboxes and OneDrive for Business sites that the script successfully placed on hold.</span></span>
    
- <span data-ttu-id="202b4-p120">**LocationsNotOnHold.txt** - contiene una lista de buzones de correo y OneDrive para los sitios de negocio que la secuencia de comandos no se convirtieron en espera. Si un usuario tiene un buzón de correo, pero no un OneDrive para el sitio de negocio, el usuario se incluirá en la lista de OneDrive para sitios de negocio que no se han colocado en suspensión.</span><span class="sxs-lookup"><span data-stu-id="202b4-p120">**LocationsNotOnHold.txt** - Contains a list of mailboxes and OneDrive for Business sites that the script did not place on hold. If a user has a mailbox, but not a OneDrive for Business site, the user would be included in the list of OneDrive for Business sites that weren't placed on hold.</span></span>
    
- <span data-ttu-id="202b4-p121">**GetCaseHoldPolicy.txt** - contiene el resultado del cmdlet **Get-CaseHoldPolicy** para la suspensión nuevo, que se ejecutó la secuencia de comandos después de crear la suspensión nuevo. La información devuelta por este cmdlet incluye una lista de los usuarios cuyos buzones de correo y OneDrive para sitios de negocio se colocaron en espera y si la suspensión está habilitada o deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="202b4-p121">**GetCaseHoldPolicy.txt** - Contains the output of the **Get-CaseHoldPolicy** cmdlet for the new hold, which the script ran after creating the new hold. The information returned by this cmdlet includes a list of users whose mailboxes and OneDrive for Business sites were placed on hold and whether the hold is enabled or disabled.</span></span> 
    
- <span data-ttu-id="202b4-p122">**GetCaseHoldRule.txt** - contiene el resultado del cmdlet **Get-CaseHoldRule** para la suspensión nuevo, que se ejecutó la secuencia de comandos después de crear la suspensión nuevo. La información devuelta por este cmdlet incluye la consulta de búsqueda si se usa la secuencia de comandos para crear una suspensión basada en consultas.</span><span class="sxs-lookup"><span data-stu-id="202b4-p122">**GetCaseHoldRule.txt** - Contains the output of the **Get-CaseHoldRule** cmdlet for the new hold, which the script ran after creating the new hold. The information returned by this cmdlet includes the search query if you used the script to create a query-based hold.</span></span> 
