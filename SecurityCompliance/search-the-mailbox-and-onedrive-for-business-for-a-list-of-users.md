---
title: Usar búsqueda de contenido para buscar una lista de usuarios en el buzón y el sitio de OneDrive para la Empresa
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 1/3/2017
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
search.appverid: MOE150
ms.assetid: 5f4f8206-2d6a-4cb2-bbc6-7a0698703cc0
description: Use la búsqueda de contenido y el script de este artículo para buscar en los sitios buzones y OneDrive para la empresa un grupo de usuarios.
ms.openlocfilehash: 1d180d4b6deefd59a26b1e93f354c72810030718
ms.sourcegitcommit: baf23be44f1ed5abbf84f140b5ffa64fce605478
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/26/2019
ms.locfileid: "30295503"
---
# <a name="use-content-search-to-search-the-mailbox-and-onedrive-for-business-site-for-a-list-of-users"></a><span data-ttu-id="95798-103">Usar búsqueda de contenido para buscar una lista de usuarios en el buzón y el sitio de OneDrive para la Empresa</span><span class="sxs-lookup"><span data-stu-id="95798-103">Use Content Search to search the mailbox and OneDrive for Business site for a list of users</span></span>

<span data-ttu-id="95798-p101">El centro de seguridad &amp; y cumplimiento de Office 365 proporciona una serie de cmdlets de Windows PowerShell que permiten automatizar las tareas relacionadas con la exhibición de documentos electrónicos que consumen tiempo. Actualmente, la creación de una búsqueda de contenido &amp; en el centro de seguridad y cumplimiento para buscar en un gran número de ubicaciones de contenido de custodios lleva tiempo y preparación. Antes de crear una búsqueda, tiene que recopilar la dirección URL de cada sitio de OneDrive para la empresa y, a continuación, agregar a la búsqueda todos los buzones de correo y neDrive para el sitio de la empresa. En versiones futuras, será más fácil hacerlo en el centro de seguridad &amp; y cumplimiento. Hasta entonces, puede usar el script de este artículo para automatizar este proceso. Esta secuencia de comandos le pedirá el nombre del dominio de mi sitio de su organización (por ejemplo, **contoso** en https://contoso-my.sharepoint.com)la dirección URL, una lista de direcciones de correo electrónico de usuario, el nombre de la nueva búsqueda de contenido y la consulta de búsqueda que se va a usar. La secuencia de comandos obtiene la dirección URL de OneDrive para la empresa de cada usuario de la lista y, a continuación, crea e inicia una búsqueda de contenido que busca en el buzón y el sitio de OneDrive para la empresa para cada usuario de la lista, usando la consulta de búsqueda que proporcione.</span><span class="sxs-lookup"><span data-stu-id="95798-p101">The Office 365 Security &amp; Compliance Center provides a number of Windows PowerShell cmdlets that let you automate time-consuming eDiscovery-related tasks. Currently, creating a Content Search in the Security &amp; Compliance Center to search a large number of custodian content locations takes time and preparation. Before you create a search, you have to collect the URL for each OneDrive for Business site and then add each mailbox and O neDrive for Business site to the search. In future releases, this will be easier to do in the Security &amp; Compliance Center. Until then, you can use the script in this article to automate this process. This script prompts you for the name of your organization's MySite domain (for example, **contoso** in the URL https://contoso-my.sharepoint.com), a list of user email addresses, the name of the new Content Search, and the search query to use. The script gets the OneDrive for Business URL for each user in the list, and then it creates and starts a Content Search that searches the mailbox and OneDrive for Business site for each user in the list, using the search query that you provide.</span></span> 
  
## <a name="before-you-begin"></a><span data-ttu-id="95798-111">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="95798-111">Before you begin</span></span>

- <span data-ttu-id="95798-112">Debe ser miembro del grupo de roles eDiscovery Manager en el centro de seguridad &amp; y cumplimiento y un administrador global de SharePoint Online para ejecutar el script en el paso 3.</span><span class="sxs-lookup"><span data-stu-id="95798-112">You have to be a member of the eDiscovery Manager role group in the Security &amp; Compliance Center and a SharePoint Online global administrator to run the script in Step 3.</span></span>
    
- <span data-ttu-id="95798-p102">Asegúrese de guardar la lista de usuarios que ha creado en el paso 2 y el script en el paso 3 en la misma carpeta. Esto hará que sea más fácil ejecutar el script.</span><span class="sxs-lookup"><span data-stu-id="95798-p102">Be sure to save the list of users that you create in Step 2 and the script in Step 3 to the same folder. That will make it easier to run the script.</span></span>
    
- <span data-ttu-id="95798-p103">El script incluye un tratamiento de errores mínimo. Su objetivo principal es buscar de forma rápida y sencilla el sitio de buzón de correo y OneDrive para la empresa de cada usuario.</span><span class="sxs-lookup"><span data-stu-id="95798-p103">The script includes minimal error handling. It's primary purpose is to quickly and easily search the mailbox and OneDrive for Business site of each user.</span></span>
    
- <span data-ttu-id="95798-p104">Las secuencias de comandos de ejemplo que se proporcionan en este tema no se admiten en ningún servicio o programa de soporte técnico estándar de Microsoft. Los scripts de muestra se proporcionan tal cual sin ninguna garantía de ningún tipo. Microsoft renuncia aún más a[https://go.microsoft.com/fwlink/p/?LinkId=517283](https://go.microsoft.com/fwlink/p/?LinkId=517283)todas las garantías de i mplied, incluidas, entre otras, todas las garantías implícitas de comerciabilidad o de idoneidad para un propósito en particular. Todo el riesgo derivado del uso o el rendimiento de los scripts y la documentación de muestra permanece con usted. En ningún caso Microsoft, sus autores o cualquier otro implicado en la creación, la producción o la entrega de las secuencias de comandos serán responsables de cualquier daño (incluidos, entre otros, los daños causados por la pérdida de beneficios de negocio, la interrupción del negocio, la pérdida de información de la empresa u otra pérdida pecuniaria que surja del uso o la incapacidad para usar la documentación o los scripts de ejemplo, incluso si se ha notificado a Microsoft de la posibilidad de dichos daños.</span><span class="sxs-lookup"><span data-stu-id="95798-p104">The sample scripts provided in this topic aren't supported under any Microsoft standard support program or service. The sample scripts are provided AS IS without warranty of any kind. Microsoft further disclaims all i[https://go.microsoft.com/fwlink/p/?LinkId=517283](https://go.microsoft.com/fwlink/p/?LinkId=517283)mplied warranties including, without limitation, any implied warranties of merchantability or of fitness for a particular purpose. The entire risk arising out of the use or performance of the sample scripts and documentation remains with you. In no event shall Microsoft, its authors, or anyone else involved in the creation, production, or delivery of the scripts be liable for any damages whatsoever (including, without limitation, damages for loss of business profits, business interruption, loss of business information, or other pecuniary loss) arising out of the use of or inability to use the sample scripts or documentation, even if Microsoft has been advised of the possibility of such damages.</span></span>
    
## <a name="step-1-install-the-sharepoint-online-management-shell"></a><span data-ttu-id="95798-122">Paso 1: Instalar el Shell de administración de SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="95798-122">Step 1: Install the SharePoint Online Management Shell</span></span>
<span data-ttu-id="95798-123"><a name="step1"> </a></span><span class="sxs-lookup"><span data-stu-id="95798-123"></span></span>

<span data-ttu-id="95798-p105">El primer paso es instalar el shell de administración de SharePoint Online. No tiene que usar el shell de este procedimiento, pero tiene que instalarlo porque contiene los requisitos previos necesarios para el script que ejecutó en el paso 3. Estos requisitos previos permiten que el script se comunique con SharePoint Online para obtener las direcciones URL de los sitios de OneDrive para la empresa.</span><span class="sxs-lookup"><span data-stu-id="95798-p105">The first step is to install the SharePoint Online Management Shell. You don't have to use the shell in this procedure, but you have to install it because it contains pre-requisites required by the script that you run in Step 3. These prerequisites allow the script to communicate with SharePoint Online to get the URLs for the OneDrive for Business sites.</span></span>
  
<span data-ttu-id="95798-127">Vaya a [configurar el entorno de Windows PowerShell de Shell de administración de SharePoint Online](https://go.microsoft.com/fwlink/p/?LinkID=286318) y realice el paso 1 y el paso 2 para instalar el shell de administración de SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="95798-127">Go to [Set up the SharePoint Online Management Shell Windows PowerShell environment](https://go.microsoft.com/fwlink/p/?LinkID=286318) and perform Step 1 and Step 2 to install the SharePoint Online Management Shell.</span></span>
  
## <a name="step-2-generate-a-list-of-users"></a><span data-ttu-id="95798-128">Paso 2: generar una lista de usuarios</span><span class="sxs-lookup"><span data-stu-id="95798-128">Step 2: Generate a list of users</span></span>
<span data-ttu-id="95798-129"><a name="step2"> </a></span><span class="sxs-lookup"><span data-stu-id="95798-129"></span></span>

<span data-ttu-id="95798-p106">El script del paso 3 creará una búsqueda de contenido para buscar en los buzones y las cuentas de OneDrive una lista de usuarios. Solo puede escribir las direcciones de correo electrónico en un archivo de texto o puede ejecutar un comando en Windows PowerShell para obtener una lista de direcciones de correo electrónico y guardarlas en un archivo (ubicado en la misma carpeta en la que guardará el script en el paso 3).</span><span class="sxs-lookup"><span data-stu-id="95798-p106">The script in Step 3 will create a Content Search to search the mailboxes and OneDrive accounts for a list of users. You can just type the email addresses in a text file, or you can run a command in Windows PowerShell to get a list of email addresses and save them to a file (located in same folder that you'll save the script to in Step 3).</span></span>
  
<span data-ttu-id="95798-132">Este es un comando de [Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=517283) que puede runt para obtener una lista de direcciones de correo electrónico para todos los usuarios de la organización y guardarla en un `Users.txt`archivo de texto denominado.</span><span class="sxs-lookup"><span data-stu-id="95798-132">Here's an [Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=517283) command that you can runt to get a list of email addresses for all users in your organization and save it to a text file named `Users.txt`.</span></span> 
  
```
Get-Mailbox -ResultSize unlimited -Filter { RecipientTypeDetails -eq 'UserMailbox'} | Select-Object PrimarySmtpAddress > Users.txt
```

<span data-ttu-id="95798-p107">Después de ejecutar este comando, asegúrese de abrir el archivo y quitar el encabezado que contiene el nombre de la propiedad `PrimarySmtpAddress`. El archivo de texto solo debe contener una lista de direcciones de correo electrónico y nada más. Asegúrese de que no haya filas en blanco antes ni después de la lista de direcciones de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="95798-p107">After you run this command, be sure to open the file and remove the header that contains the property name,  `PrimarySmtpAddress`. The text file should just contain a list of email addresses, and nothing else. Make sure there are no blank rows before or after the list of email addresses.</span></span>
  
## <a name="step-3-run-the-script-to-create-and-start-the-search"></a><span data-ttu-id="95798-136">Paso 3: ejecutar el script para crear e iniciar la búsqueda</span><span class="sxs-lookup"><span data-stu-id="95798-136">Step 3: Run the script to create and start the search</span></span>

<span data-ttu-id="95798-p108">Al ejecutar el script en este paso, se le pedirá la siguiente información. Asegúrese de que tiene esta información lista antes de ejecutar el script.</span><span class="sxs-lookup"><span data-stu-id="95798-p108">When you run the script in this step, it will prompt you for the following information. Be sure to have this information ready before you run the script.</span></span>
  
- <span data-ttu-id="95798-139">**Sus credenciales de usuario** : el script usará sus credenciales para acceder a SharePoint Online y obtener las direcciones URL de OneDrive para la empresa &amp; y para conectarse al centro de seguridad y cumplimiento con PowerShell remoto.</span><span class="sxs-lookup"><span data-stu-id="95798-139">**Your user credentials** - The script will use your credentials to access SharePoint Online to get the OneDrive for Business URLs and to connect to the Security &amp; Compliance Center with remote PowerShell.</span></span> 
    
- <span data-ttu-id="95798-p109">**Nombre del dominio de mi sitio** : el dominio de mi sitio es el dominio que contiene todos los sitios de OneDrive para la empresa de su organización. Por ejemplo, si la dirección URL del dominio de mi sitio **https://contoso-my.sharepoint.com**es, debe especificar `contoso` cuando el script le pide el nombre de su dominio de mi sitio.</span><span class="sxs-lookup"><span data-stu-id="95798-p109">**Name of your MySite domain** - The MySite domain is the domain that contains all the OneDrive for Business sites in your organization. For example, if the URL for your MySite domain is **https://contoso-my.sharepoint.com**, then you would enter  `contoso` when the script prompts you for the name of your MySite domain.</span></span> 
    
- <span data-ttu-id="95798-p110">**Nombreruta del archivo de texto del paso 2** : el directorio del archivo de texto que creó en el paso 2. Si el archivo de texto y el script están ubicados en la misma carpeta, escriba el nombre del archivo de texto. De lo contrario, escriba el directorio completo del archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="95798-p110">**Pathname of the text file from Step 2** - The pathname of the text file that you created in Step 2. If the text file and the script are located in the same folder, then enter the name of the text file. Otherwise, enter the complete pathname for the text file.</span></span> 
    
- <span data-ttu-id="95798-145">**Nombre de la búsqueda de contenido** : el nombre de la búsqueda de contenido que se creará mediante el script.</span><span class="sxs-lookup"><span data-stu-id="95798-145">**Name of the Content Search** - The name of the Content Search that will be created by the script.</span></span> 
    
- <span data-ttu-id="95798-p111">**Consulta de búsqueda** : se crea y ejecuta la consulta de búsqueda que se usará con la búsqueda de contenido. Para obtener más información acerca de las consultas de búsqueda, vea [consultas de palabras clave y condiciones de búsqueda para la búsqueda de contenido](keyword-queries-and-search-conditions.md).</span><span class="sxs-lookup"><span data-stu-id="95798-p111">**Search query** - The search query that will be used with the Content Search is created and run. For more information about search queries, see [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md).</span></span>


<span data-ttu-id="95798-148">**Para ejecutar el script:**</span><span class="sxs-lookup"><span data-stu-id="95798-148">**To run the script:**</span></span>
    
1. <span data-ttu-id="95798-p112">Guarde el siguiente texto en un archivo de script de Windows PowerShell mediante un sufijo de nombre de archivo de. ps1; por ejemplo, `SearchEXOOD4B.ps1`. Guarde el archivo en la misma carpeta en la que guardó la lista de usuarios en el paso 2.</span><span class="sxs-lookup"><span data-stu-id="95798-p112">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `SearchEXOOD4B.ps1`. Save the file to the same folder where you saved the list of users in Step 2.</span></span>
    
  ```
  # This PowerShell script will prompt you for the following information:
  #    * Your user credentials 
  #    * The name of your organization's MySite domain                                              
  #    * The pathname for the text file that contains a list of user email addresses
  #    * The name of the Content Search that will be created
  #    * The search query string
  # The script will then:
  #    * Find the OneDrive for Business site for each user in the text file
  #    * Create and start a Content Search using the above information
  # Get user credentials
  if (!$credentials)
  {
      $credentials = Get-Credential
  }
  # Get the user's MySite domain name.  We use this to create the admin URL and root URL for OneDrive for Business
  $mySiteDomain = Read-Host "What is your organization's MySite domain?  For example,  'contoso' for 'https://contoso-my.sharepoint.com'"
  $AdminUrl = "https://$mySiteDomain-admin.sharepoint.com"
  $mySiteUrlRoot = "https://$mySiteDomain-my.sharepoint.com"
  # Get other required information
  $inputfile = read-host "Enter the file name of the text file that contains the email addresses for the users you want to search"
  $searchName = Read-Host "Enter the name for the new search"
  $searchQuery = Read-Host "Enter the search query you want to use"
  $emailAddresses = Get-Content $inputfile | where {$_ -ne ""}  | foreach{ $_.Trim() }
  # Connect to Office 365
  if (!$s -or !$a)
  {
      $s = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri "https://ps.compliance.protection.outlook.com/powershell-liveid" -Credential $credentials -Authentication Basic -AllowRedirection -SessionOption (New-PSSessionOption -SkipCACheck -SkipCNCheck -SkipRevocationCheck)
      $a = Import-PSSession $s -AllowClobber
      if (!$s)
      {
          Write-Error "Could not create PowerShell session."
          return;
      }
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
          Write-Error "SharePoint Online Management Shell isn't installed, please install from: http://go.microsoft.com/fwlink/p/?LinkId=255251 and then run this script again"
          return;
      }
  }
  if (!$spCreds)
  {
      $spCreds = New-Object Microsoft.SharePoint.Client.SharePointOnlineCredentials($credentials.UserName, $credentials.Password)
  }
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
  Write-Host "Getting each user's OneDrive for Business URL"
  $urls = @()
  foreach($emailAddress in $emailAddresses)
  {
      try
      {
          $prop = $UserProfileService.GetUserProfileByName("i:0#.f|membership|$emailAddress") | Where-Object { $_.Name -eq "PersonalSpace" } 
          $url = $prop.values[0].value
          $furl = $mySiteUrlRoot + $url
          $urls += $furl
          Write-Host "-$emailAddress => $furl"
      }
      catch
      {
          Write-Warning "Could not locate OneDrive for $emailAddress"
      }
  }
  Write-Host "Creating and starting the search"
  $search = New-ComplianceSearch -Name $searchName -ExchangeLocation $emailAddresses -SharePointLocation $urls -ContentMatchQuery $searchQuery
  # Finally, start the search and then display the status
  if($search)
  {
      Start-ComplianceSearch $search.Name
      Get-ComplianceSearch $search.Name
  }
  
  ```

2. <span data-ttu-id="95798-151">Abra Windows PowerShell y vaya a la carpeta en la que guardó el script y la lista de usuarios del paso 2.</span><span class="sxs-lookup"><span data-stu-id="95798-151">Open Windows PowerShell and go to the folder where you saved the script and the list of users from Step 2.</span></span>
    
3. <span data-ttu-id="95798-152">Inicie el script; por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="95798-152">Start the script; for example:</span></span>
    
    ```
    .\SearchEXOOD4B.ps1
    ```

4. <span data-ttu-id="95798-153">Cuando se le pidan sus credenciales, escriba su dirección de correo electrónico y contraseña y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="95798-153">When prompted for your credentials, enter your email address and password, and then click **OK**.</span></span> 
    
5. <span data-ttu-id="95798-p113">Escriba la información siguiente cuando se lo solicite el script. Escriba cada fragmento de información y, a continuación, presione **entrar**.</span><span class="sxs-lookup"><span data-stu-id="95798-p113">Enter following information when prompted by the script. Type each piece of information and then press **Enter**.</span></span>
    
    - <span data-ttu-id="95798-156">Nombre del dominio de mi sitio.</span><span class="sxs-lookup"><span data-stu-id="95798-156">The name of your MySite domain.</span></span> 
    
    - <span data-ttu-id="95798-157">Ruta de ruta del archivo de texto que contiene la lista de usuarios.</span><span class="sxs-lookup"><span data-stu-id="95798-157">The pathname of the text file that contains the list of users.</span></span>
    
    - <span data-ttu-id="95798-158">Un nombre para la búsqueda de contenido.</span><span class="sxs-lookup"><span data-stu-id="95798-158">A name for the Content Search.</span></span>
    
    - <span data-ttu-id="95798-159">La consulta de búsqueda (déjelo en blanco para devolver todos los elementos de las ubicaciones de contenido).</span><span class="sxs-lookup"><span data-stu-id="95798-159">The search query (leave this blank to return all items in the content locations).</span></span>
    
    <span data-ttu-id="95798-p114">El script obtiene las direcciones URL de cada sitio de OneDrive para la empresa y, a continuación, crea e inicia la búsqueda. Puede ejecutar el cmdlet **Get-ComplianceSearch** en Security _AMP_ Compliance Center PowerShell para mostrar las estadísticas y los resultados de la búsqueda, o puede ir a la página de **búsqueda de contenido** en &amp; el centro de seguridad y cumplimiento para ver información sobre la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="95798-p114">The script gets the URLs for each OneDrive for Business site and then creates and starts the search. You can either run the **Get-ComplianceSearch** cmdlet in Security & Compliance Center PowerShell to display the search statistics and results, or you can go to the **Content search** page in the Security &amp; Compliance Center to view information about the search.</span></span> 
