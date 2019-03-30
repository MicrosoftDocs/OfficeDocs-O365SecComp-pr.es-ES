---
title: Usar un script para agregar usuarios a una suspensión en un caso de exhibición de documentos electrónicos en el centro de seguridad & cumplimiento
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 1/23/2017
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MBS150
ms.assetid: bad352ff-d5d2-45d8-ac2a-6cb832f10e73
description: Ejecute un script para agregar rápidamente sitios de buzones de correo y OneDrive para la empresa a una nueva retención asociada a un caso de exhibición de documentos electrónicos en el centro de seguridad & cumplimiento.
ms.openlocfilehash: 992fddad3bfbc9f08855bd85d87b0edf92b3cdbe
ms.sourcegitcommit: e7a776a04ef6ed5e287a33cfdc36aa2d72862b55
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/29/2019
ms.locfileid: "31001193"
---
# <a name="use-a-script-to-add-users-to-a-hold-in-an-ediscovery-case-in-the-security--compliance-center"></a><span data-ttu-id="04878-103">Usar un script para agregar usuarios a una suspensión en un caso de exhibición de documentos electrónicos en el centro de seguridad & cumplimiento</span><span class="sxs-lookup"><span data-stu-id="04878-103">Use a script to add users to a hold in an eDiscovery case in the Security & Compliance Center</span></span>

<span data-ttu-id="04878-104">El centro de seguridad & cumplimiento proporciona muchos cmdlets de Windows PowerShell que permiten automatizar tareas que llevan mucho tiempo relacionadas con la creación y la administración de casos de eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="04878-104">The Security & Compliance Center provides lots of Windows PowerShell cmdlets that let you automate time-consuming tasks related to creating and managing eDiscovery cases.</span></span> <span data-ttu-id="04878-105">Actualmente, el uso de la herramienta de casos de exhibición de documentos electrónicos en el centro de cumplimiento de seguridad & para poner un gran número de ubicaciones de contenido de custodios en retención lleva tiempo y preparación.</span><span class="sxs-lookup"><span data-stu-id="04878-105">Currently, using the eDiscovery case tool in the Security & Compliance Center to place a large number of custodian content locations on hold takes time and preparation.</span></span> <span data-ttu-id="04878-106">Por ejemplo, antes de crear una retención, tiene que recopilar la dirección URL de cada sitio de OneDrive para la empresa que quiera poner en retención.</span><span class="sxs-lookup"><span data-stu-id="04878-106">For example, before you create a hold, you have to collect the URL for each OneDrive for Business site that you want to place on hold.</span></span> <span data-ttu-id="04878-107">A continuación, para cada usuario que quiera poner en retención, tiene que agregar su buzón y su sitio de OneDrive para la empresa a la retención.</span><span class="sxs-lookup"><span data-stu-id="04878-107">Then for each user you want to place on hold, you have to add their mailbox and their OneDrive for Business site to the hold.</span></span> <span data-ttu-id="04878-108">En futuras versiones del centro de seguridad & cumplimiento, esto le resultará más sencillo.</span><span class="sxs-lookup"><span data-stu-id="04878-108">In future releases of the Security & Compliance Center, this will get easier to do.</span></span> <span data-ttu-id="04878-109">Hasta entonces, puede usar el script de este artículo para automatizar este proceso.</span><span class="sxs-lookup"><span data-stu-id="04878-109">Until then, you can use the script in this article to automate this process.</span></span>
  
<span data-ttu-id="04878-110">El script le pedirá el nombre del dominio de mi sitio de su organización (por ejemplo, **contoso** en la dirección https://contoso-my.sharepoint.com)URL, el nombre de un caso de eDiscovery existente, el nombre de la nueva retención asociada con el caso, una lista de direcciones de correo electrónico de los usuarios que desea poner en espera y una consulta de búsqueda para usar si desea crear una suspensión basada en consulta.</span><span class="sxs-lookup"><span data-stu-id="04878-110">The script prompts you for the name of your organization's MySite domain (for example, **contoso** in the URL https://contoso-my.sharepoint.com), the name of an existing eDiscovery case, the name of the new hold that associated with the case, a list of email addresses of the users you want to put on hold, and a search query to use if you want to create a query-based hold.</span></span> <span data-ttu-id="04878-111">A continuación, el script obtiene la dirección URL del sitio de OneDrive para la empresa para cada usuario de la lista, crea la nueva retención y, a continuación, agrega el buzón y el sitio de OneDrive para la empresa para cada usuario de la lista a la retención.</span><span class="sxs-lookup"><span data-stu-id="04878-111">The script then gets the URL for the OneDrive for Business site for each user in the list, creates the new hold, and then adds the mailbox and OneDrive for Business site for each user in the list to the hold.</span></span> <span data-ttu-id="04878-112">El script también genera archivos de registro que contienen información sobre la nueva suspensión.</span><span class="sxs-lookup"><span data-stu-id="04878-112">The script also generates log files that contain information about the new hold.</span></span> 
  
<span data-ttu-id="04878-113">Estos son los pasos para que esto suceda:</span><span class="sxs-lookup"><span data-stu-id="04878-113">Here are the steps to make this happen:</span></span>
  
[<span data-ttu-id="04878-114">Paso 1: Instalar el Shell de administración de SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="04878-114">Step 1: Install the SharePoint Online Management Shell</span></span>](#step-1-install-the-sharepoint-online-management-shell)
  
[<span data-ttu-id="04878-115">Paso 2: generar una lista de usuarios</span><span class="sxs-lookup"><span data-stu-id="04878-115">Step 2: Generate a list of users</span></span>](use-a-script-to-add-users-to-a-hold-in-ediscovery.md#step2)
  
[<span data-ttu-id="04878-116">Paso 3: ejecutar el script para crear una retención y agregar usuarios</span><span class="sxs-lookup"><span data-stu-id="04878-116">Step 3: Run the script to create a hold and add users</span></span>](use-a-script-to-add-users-to-a-hold-in-ediscovery.md#step3)
  
## <a name="before-you-begin"></a><span data-ttu-id="04878-117">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="04878-117">Before you begin</span></span>

- <span data-ttu-id="04878-118">Debe ser miembro del grupo de roles eDiscovery Manager en el centro de seguridad & cumplimiento y un administrador global de SharePoint Online para ejecutar el script en el paso 3.</span><span class="sxs-lookup"><span data-stu-id="04878-118">You have to be a member of the eDiscovery Manager role group in the Security & Compliance Center and a SharePoint Online global administrator to run the script in Step 3.</span></span> <span data-ttu-id="04878-119">Para obtener más información, vea [asignar permisos de exhibición de documentos electrónicos en el centro de seguridad _AMP_ cumplimiento de Office 365](assign-ediscovery-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="04878-119">For more information, see [Assign eDiscovery permissions in the Office‍ 365 Security & Compliance Center](assign-ediscovery-permissions.md).</span></span>
    
- <span data-ttu-id="04878-120">Se puede Agregar un máximo de 1.000 buzones y sitios de 100 a una suspensión asociada a un caso de exhibición de documentos electrónicos en el centro de seguridad & cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="04878-120">A maximum of 1,000 mailboxes and 100 sites can be added to a hold that's associated with an eDiscovery case in the Security & Compliance Center.</span></span> <span data-ttu-id="04878-121">SuPoniendo que todos los usuarios que quiera poner en retención dispongan de un sitio de OneDrive para la empresa, puede Agregar un máximo de 100 usuarios a una suspensión mediante el script de este artículo.</span><span class="sxs-lookup"><span data-stu-id="04878-121">Assuming that every user that you want to place on hold has a OneDrive for Business site, you can add a maximum of 100 users to a hold using the script in this article.</span></span> 
    
- <span data-ttu-id="04878-122">Asegúrese de guardar la lista de usuarios que ha creado en el paso 2 y el script en el paso 3 en la misma carpeta.</span><span class="sxs-lookup"><span data-stu-id="04878-122">Be sure to save the list of users that you create in Step 2 and the script in Step 3 to the same folder.</span></span> <span data-ttu-id="04878-123">Esto hará que sea más fácil ejecutar el script.</span><span class="sxs-lookup"><span data-stu-id="04878-123">That will make it easier to run the script.</span></span>
    
- <span data-ttu-id="04878-124">La secuencia de comandos agrega la lista de usuarios a una nueva retención asociada a un caso existente.</span><span class="sxs-lookup"><span data-stu-id="04878-124">The script adds the list of users to a new hold that is associated with an existing case.</span></span> <span data-ttu-id="04878-125">Asegúrese de que el caso con el que desea asociar la retención se ha creado antes de ejecutar el script.</span><span class="sxs-lookup"><span data-stu-id="04878-125">Be sure the case that you want to associate the hold with is created before you run the script.</span></span>
    
- <span data-ttu-id="04878-126">El script incluye un tratamiento de errores mínimo.</span><span class="sxs-lookup"><span data-stu-id="04878-126">The script includes minimal error handling.</span></span> <span data-ttu-id="04878-127">Su objetivo principal es ubicar de forma rápida y sencilla el buzón y el sitio de OneDrive para la empresa de cada usuario en espera.</span><span class="sxs-lookup"><span data-stu-id="04878-127">Its primary purpose is to quickly and easily place the mailbox and OneDrive for Business site of each user on hold.</span></span>
    
- <span data-ttu-id="04878-p108">Los scripts de ejemplo que se proporcionan en este tema no son compatibles con ningún servicio o programa de soporte técnico estándar de Microsoft. Los scripts de ejemplo se proporcionan tal cual, sin garantía de ningún tipo. Además, Microsoft se exime de todas las garantías implícitas, incluidas (sin limitación) las garantías implícitas de comerciabilidad o idoneidad para un propósito específico. El usuario asume todos los riesgos derivados del uso o del rendimiento de los scripts de ejemplo y la documentación. Microsoft, sus autores o cualquier persona relacionada con la creación, producción o entrega de los scripts no serán en ningún caso responsables de cualesquiera daños (incluidos, sin limitación, los daños producidos por la pérdida de beneficios comerciales, interrupción de la actividad comercial, pérdida de información empresarial u otras pérdidas económicas) derivados del uso o de la imposibilidad de uso de los scripts de ejemplo o la documentación, incluso aunque Microsoft tenga constancia de la posibilidad de que dichos daños se produzcan.</span><span class="sxs-lookup"><span data-stu-id="04878-p108">The sample scripts provided in this topic aren't supported under any Microsoft standard support program or service. The sample scripts are provided AS IS without warranty of any kind. Microsoft further disclaims all implied warranties including, without limitation, any implied warranties of merchantability or of fitness for a particular purpose. The entire risk arising out of the use or performance of the sample scripts and documentation remains with you. In no event shall Microsoft, its authors, or anyone else involved in the creation, production, or delivery of the scripts be liable for any damages whatsoever (including, without limitation, damages for loss of business profits, business interruption, loss of business information, or other pecuniary loss) arising out of the use of or inability to use the sample scripts or documentation, even if Microsoft has been advised of the possibility of such damages.</span></span>

## <a name="step-1-install-the-sharepoint-online-management-shell"></a><span data-ttu-id="04878-133">Paso 1: Instalar el Shell de administración de SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="04878-133">Step 1: Install the SharePoint Online Management Shell</span></span>

<span data-ttu-id="04878-134">El primer paso es instalar el shell de administración de SharePoint Online si todavía no está instalado en el equipo local.</span><span class="sxs-lookup"><span data-stu-id="04878-134">The first step is to install the SharePoint Online Management Shell if it's not already installed on your local computer.</span></span> <span data-ttu-id="04878-135">No tiene que usar el shell de este procedimiento, pero tiene que instalarlo porque contiene los requisitos previos necesarios para el script que ejecutó en el paso 3.</span><span class="sxs-lookup"><span data-stu-id="04878-135">You don't have to use the shell in this procedure, but you have to install it because it contains pre-requisites required by the script that you run in Step 3.</span></span> <span data-ttu-id="04878-136">Estos requisitos previos permiten que el script se comunique con SharePoint Online para obtener las direcciones URL de los sitios de OneDrive para la empresa.</span><span class="sxs-lookup"><span data-stu-id="04878-136">These prerequisites allow the script to communicate with SharePoint Online to get the URLs for the OneDrive for Business sites.</span></span>
  
<span data-ttu-id="04878-137">Vaya a [configurar el entorno de Windows PowerShell de Shell de administración de SharePoint Online](https://go.microsoft.com/fwlink/p/?LinkID=286318) y realice los pasos 1 y 2 para instalar el shell de administración de SharePoint Online en el equipo local.</span><span class="sxs-lookup"><span data-stu-id="04878-137">Go to [Set up the SharePoint Online Management Shell Windows PowerShell environment](https://go.microsoft.com/fwlink/p/?LinkID=286318) and perform Step 1 and Step 2 to install the SharePoint Online Management Shell on your local computer.</span></span> 

## <a name="step-2-generate-a-list-of-users"></a><span data-ttu-id="04878-138">Paso 2: generar una lista de usuarios</span><span class="sxs-lookup"><span data-stu-id="04878-138">Step 2: Generate a list of users</span></span>
<span data-ttu-id="04878-139"><a name="step2"> </a></span><span class="sxs-lookup"><span data-stu-id="04878-139"></span></span>

<span data-ttu-id="04878-140">El script del paso 3 creará una retención asociada con un caso de exhibición de documentos electrónicos, y los sitios y agregar los buzones y OneDrive para la empresa de una lista de usuarios a la retención.</span><span class="sxs-lookup"><span data-stu-id="04878-140">The script in Step 3 will create a hold that's associated with an eDiscovery case, and the add the mailboxes and OneDrive for Business sites of a list of users to the hold.</span></span> <span data-ttu-id="04878-141">Solo puede escribir las direcciones de correo electrónico en un archivo de texto o puede ejecutar un comando en Windows PowerShell para obtener una lista de direcciones de correo electrónico y guardarlas en un archivo (ubicado en la misma carpeta en la que guardará el script en el paso 3).</span><span class="sxs-lookup"><span data-stu-id="04878-141">You can just type the email addresses in a text file, or you can run a command in Windows PowerShell to get a list of email addresses and save them to a file (located in same folder that you'll save the script to in Step 3).</span></span>
  
<span data-ttu-id="04878-142">Este es un comando de PowerShell (que ejecuta con PowerShell remoto conectado a su organización de Exchange Online) para obtener una lista de direcciones de correo electrónico para todos los usuarios de la organización y guardarla en un archivo de texto denominado HoldUsers. txt.</span><span class="sxs-lookup"><span data-stu-id="04878-142">Here's a PowerShell command (that you run by using remote PowerShell connected to your Exchange Online organization) to get a list of email addresses for all users in your organization and save it to a text file named HoldUsers.txt.</span></span>
  
```
Get-Mailbox -ResultSize unlimited -Filter { RecipientTypeDetails -eq 'UserMailbox'} | Select-Object PrimarySmtpAddress > HoldUsers.txt
```

<span data-ttu-id="04878-143">Después de ejecutar este comando, abra el archivo de texto y quite el encabezado que contiene el nombre de `PrimarySmtpAddress`la propiedad.</span><span class="sxs-lookup"><span data-stu-id="04878-143">After you run this command, open the text file and remove the header that contains the property name,  `PrimarySmtpAddress`.</span></span> <span data-ttu-id="04878-144">A continuación, quite todas las direcciones de correo electrónico excepto las de los usuarios que desea agregar a la suspensión que creará en el paso 3.</span><span class="sxs-lookup"><span data-stu-id="04878-144">Then remove all email addresses except the ones for the users that you want to add to the hold that you'll create in Step 3.</span></span> <span data-ttu-id="04878-145">Asegúrese de que no haya filas en blanco antes ni después de la lista de direcciones de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="04878-145">Make sure there are no blank rows before or after the list of email addresses.</span></span>
  

  
## <a name="step-3-run-the-script-to-create-a-hold-and-add-users"></a><span data-ttu-id="04878-146">Paso 3: ejecutar el script para crear una retención y agregar usuarios</span><span class="sxs-lookup"><span data-stu-id="04878-146">Step 3: Run the script to create a hold and add users</span></span>
<span data-ttu-id="04878-147"><a name="step3"> </a></span><span class="sxs-lookup"><span data-stu-id="04878-147"></span></span>

<span data-ttu-id="04878-148">Al ejecutar el script en este paso, se le pedirá la siguiente información.</span><span class="sxs-lookup"><span data-stu-id="04878-148">When you run the script in this step, it will prompt you for the following information.</span></span> <span data-ttu-id="04878-149">Asegúrese de que tiene esta información lista antes de ejecutar el script.</span><span class="sxs-lookup"><span data-stu-id="04878-149">Be sure to have this information ready before you run the script.</span></span>
  
- <span data-ttu-id="04878-150">**Sus credenciales de usuario** : el script usará sus credenciales para conectarse al centro de cumplimiento de _AMP_ de seguridad con PowerShell remoto.</span><span class="sxs-lookup"><span data-stu-id="04878-150">**Your user credentials** - The script will use your credentials to connect to the Security & Compliance Center with remote PowerShell.</span></span> <span data-ttu-id="04878-151">También usará estas credenciales para acceder a SharePoint Online y obtener las direcciones URL de OneDrive para la empresa para la lista de usuarios.</span><span class="sxs-lookup"><span data-stu-id="04878-151">It will also use these credentials to access SharePoint Online to get the OneDrive for Business URLs for the list of users.</span></span>
    
- <span data-ttu-id="04878-152">**Nombre del dominio de mi sitio** : el dominio de mi sitio es el dominio que contiene todos los sitios de OneDrive para la empresa de su organización.</span><span class="sxs-lookup"><span data-stu-id="04878-152">**Name of your MySite domain** - The MySite domain is the domain that contains all the OneDrive for Business sites in your organization.</span></span> <span data-ttu-id="04878-153">Por ejemplo, si la dirección URL del dominio de mi sitio **https://contoso-my.sharepoint.com**es, debe especificar `contoso` cuando el script le pide el nombre de su dominio de mi sitio.</span><span class="sxs-lookup"><span data-stu-id="04878-153">For example, if the URL for your MySite domain is **https://contoso-my.sharepoint.com**, then you would enter  `contoso` when the script prompts you for the name of your MySite domain.</span></span> 
    
- <span data-ttu-id="04878-154">**Nombre del caso** : nombre de un caso existente.</span><span class="sxs-lookup"><span data-stu-id="04878-154">**Name of the case** - The name of an existing case.</span></span> <span data-ttu-id="04878-155">El script creará una nueva suspensión asociada a este caso.</span><span class="sxs-lookup"><span data-stu-id="04878-155">The script will create a new hold that is associated with this case.</span></span>
    
- <span data-ttu-id="04878-156">**Nombre de la suspensión** : el nombre de la retención que creará el script y se asociará con el caso especificado.</span><span class="sxs-lookup"><span data-stu-id="04878-156">**Name of the hold** - The name of the hold the script will create and associate with the specified case.</span></span>
    
- <span data-ttu-id="04878-157">**Consulta de búsqueda para una retención basada en consulta** : puede crear una suspensión basada en consulta para que solo se coloque en retención el contenido que cumpla los criterios de búsqueda especificados.</span><span class="sxs-lookup"><span data-stu-id="04878-157">**Search query for a query-based hold** - You can create a query-based hold so that only the content that meets the specified search criteria is placed on hold.</span></span> <span data-ttu-id="04878-158">Para poner todo el contenido en espera, simplemente presione **entrar** cuando se le pida una consulta de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="04878-158">To place all content on hold, just press **Enter** when you're prompted for a search query.</span></span> 
    
- <span data-ttu-id="04878-159">**Si quiere activar o no la retención** , puede hacer que la secuencia de comandos vuelva a pasar la retención una vez creada o puede hacer que el script cree la retención sin habilitarla.</span><span class="sxs-lookup"><span data-stu-id="04878-159">**Whether or not to turn the hold on** - You can have the script turn the hold on after it's created or you can have the script create the hold without enabling it.</span></span> <span data-ttu-id="04878-160">Si no tiene la secuencia de comandos activa, puede activarla más adelante en el centro de seguridad & cumplimiento o mediante la ejecución de los siguientes comandos de PowerShell:</span><span class="sxs-lookup"><span data-stu-id="04878-160">If you don't have the script turn on the hold, you can turn it on later in the Security & Compliance Center or by running the following PowerShell commands:</span></span> 
    
  ```
  Set-CaseHoldPolicy -Identity <name of the hold> -Enabled $true
  ```

  ```
  Set-CaseHoldRule -Identity <name of the hold> -Disabled $false
  ```

- <span data-ttu-id="04878-161">**Nombre del archivo de texto con la lista de usuarios** : el nombre del archivo de texto del paso 2 que contiene la lista de usuarios que se van a agregar a la suspensión.</span><span class="sxs-lookup"><span data-stu-id="04878-161">**Name of the text file with the list of users** - The name of the text file from Step 2 that contains the list of users to add to the hold.</span></span> <span data-ttu-id="04878-162">Si este archivo se encuentra en la misma carpeta que el script, escriba el nombre del archivo (por ejemplo, HoldUsers. txt).</span><span class="sxs-lookup"><span data-stu-id="04878-162">If this file is located in the same folder as the script, just type the name of the file (for example, HoldUsers.txt).</span></span> <span data-ttu-id="04878-163">Si el archivo de texto está en otra carpeta, escriba la ruta de directorio completa del archivo.</span><span class="sxs-lookup"><span data-stu-id="04878-163">If the text file is in another folder, type the full pathname of the file.</span></span>
    
<span data-ttu-id="04878-164">Una vez que haya recopilado la información que le pedirá el script, el paso final consiste en ejecutar el script para crear la nueva retención y agregar usuarios a la misma.</span><span class="sxs-lookup"><span data-stu-id="04878-164">After you've collected the information that the script will prompt you for, the final step is to run the script to create the new hold and add users to it.</span></span>
  
1. <span data-ttu-id="04878-165">Guarde el siguiente texto en un archivo de script de Windows PowerShell mediante un sufijo de nombre de archivo de. ps1; por ejemplo, `AddUsersToHold.ps1`.</span><span class="sxs-lookup"><span data-stu-id="04878-165">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `AddUsersToHold.ps1`.</span></span>
    
  ```
  #script begin
  " " 
  write-host "***********************************************"
  write-host "   Security & Compliance Center   " -foregroundColor yellow -backgroundcolor darkgreen
  write-host "   eDiscovery cases - Add users to a hold   " -foregroundColor yellow -backgroundcolor darkgreen 
  write-host "***********************************************"
  " " 
  # Get user credentials &amp; Connect to Office 365 SCC, SPO
  $credentials = Get-Credential -Message "Specify your credentials to connect to the Security & Compliance Center and SharePoint Online"
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

2. <span data-ttu-id="04878-166">En el equipo local, abra Windows PowerShell y vaya a la carpeta donde guardó el script.</span><span class="sxs-lookup"><span data-stu-id="04878-166">On your local computer, open Windows PowerShell and go to the folder where you saved the script.</span></span>
    
3. <span data-ttu-id="04878-167">Ejecutar el script; por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="04878-167">Run the script; for example:</span></span>
    
      ```
    .\AddUsersToHold.ps1
      ```

4. <span data-ttu-id="04878-168">Escriba la información que el script le pide.</span><span class="sxs-lookup"><span data-stu-id="04878-168">Enter the information that the script prompts you for.</span></span>
    
    <span data-ttu-id="04878-169">El script se conecta a Security & Compliance Center PowerShell y, a continuación, crea la nueva retención en el caso de eDiscovery y agrega los buzones y OneDrive para la empresa para los usuarios de la lista.</span><span class="sxs-lookup"><span data-stu-id="04878-169">The script connects to Security & Compliance Center PowerShell, and then creates the new hold in the eDiscovery case and adds the mailboxes and OneDrive for Business for the users in the list.</span></span> <span data-ttu-id="04878-170">Puede ir al caso en la página **exhibición** de documentos electrónicos en el centro de seguridad & cumplimiento para ver la nueva suspensión.</span><span class="sxs-lookup"><span data-stu-id="04878-170">You can go to the case on the **eDiscovery** page in the Security & Compliance Center to view the new hold.</span></span> 
    
<span data-ttu-id="04878-171">Una vez finalizada la ejecución del script, se crean los siguientes archivos de registro y se guardan en la carpeta en la que se encuentra el script.</span><span class="sxs-lookup"><span data-stu-id="04878-171">After the script is finished running, it creates the following log files, and saves them to the folder where the script is located.</span></span>
  
- <span data-ttu-id="04878-172">**LocationsOnHold. txt** : contiene una lista de buzones de correo y de sitios de OneDrive para la empresa en los que la secuencia de comandos se colocó correctamente en retención.</span><span class="sxs-lookup"><span data-stu-id="04878-172">**LocationsOnHold.txt** - Contains a list of mailboxes and OneDrive for Business sites that the script successfully placed on hold.</span></span>
    
- <span data-ttu-id="04878-173">**LocationsNotOnHold. txt** : contiene una lista de buzones de correo y de sitios de OneDrive para la empresa que el script no se ha puesto en espera.</span><span class="sxs-lookup"><span data-stu-id="04878-173">**LocationsNotOnHold.txt** - Contains a list of mailboxes and OneDrive for Business sites that the script did not place on hold.</span></span> <span data-ttu-id="04878-174">Si un usuario tiene un buzón de correo, pero no un sitio de OneDrive para la empresa, el usuario se incluiría en la lista de sitios de OneDrive para la empresa que no se pusieron en suspensión.</span><span class="sxs-lookup"><span data-stu-id="04878-174">If a user has a mailbox, but not a OneDrive for Business site, the user would be included in the list of OneDrive for Business sites that weren't placed on hold.</span></span>
    
- <span data-ttu-id="04878-175">**GetCaseHoldPolicy. txt** : contiene la salida del cmdlet **Get-CaseHoldPolicy** para la nueva suspensión, que se ejecutó el script después de crear la nueva suspensión.</span><span class="sxs-lookup"><span data-stu-id="04878-175">**GetCaseHoldPolicy.txt** - Contains the output of the **Get-CaseHoldPolicy** cmdlet for the new hold, which the script ran after creating the new hold.</span></span> <span data-ttu-id="04878-176">La información devuelta por este cmdlet incluye una lista de usuarios cuyos buzones y los sitios de OneDrive para la empresa se pusieron en retención y si la retención está habilitada o deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="04878-176">The information returned by this cmdlet includes a list of users whose mailboxes and OneDrive for Business sites were placed on hold and whether the hold is enabled or disabled.</span></span> 
    
- <span data-ttu-id="04878-177">**GetCaseHoldRule. txt** : contiene la salida del cmdlet **Get-CaseHoldRule** para la nueva suspensión, que se ejecutó el script después de crear la nueva suspensión.</span><span class="sxs-lookup"><span data-stu-id="04878-177">**GetCaseHoldRule.txt** - Contains the output of the **Get-CaseHoldRule** cmdlet for the new hold, which the script ran after creating the new hold.</span></span> <span data-ttu-id="04878-178">La información devuelta por este cmdlet incluye la consulta de búsqueda si usó el script para crear una suspensión basada en consulta.</span><span class="sxs-lookup"><span data-stu-id="04878-178">The information returned by this cmdlet includes the search query if you used the script to create a query-based hold.</span></span> 
