---
title: Usar la búsqueda de contenido en Office 365 para colecciones dirigidas
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid: MOE150
ms.assetid: e3cbc79c-5e97-43d3-8371-9fbc398cd92e
description: Use la búsqueda de contenido en el centro &amp; de seguridad y cumplimiento de Office 365 para realizar colecciones de destino. Una colección de destino significa que tiene la certeza de que los elementos que responden a un caso o los elementos con privilegios están ubicados en un buzón o carpeta de sitio específicos. Use el script de este artículo para obtener el identificador de carpeta o la ruta de acceso de las carpetas de sitio o de buzón de correo específicas que desea buscar.
ms.openlocfilehash: 81628c670f80053479b3b7987e8c4ece884793c6
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/23/2019
ms.locfileid: "30215020"
---
# <a name="use-content-search-in-office-365-for-targeted-collections"></a><span data-ttu-id="c14c1-105">Usar la búsqueda de contenido en Office 365 para colecciones dirigidas</span><span class="sxs-lookup"><span data-stu-id="c14c1-105">Use Content Search in Office 365 for targeted collections</span></span>

<span data-ttu-id="c14c1-p102">La característica de búsqueda de contenido en el centro &amp; de seguridad y cumplimiento de Office 365 no ofrece una forma directa en la interfaz de usuario para buscar en carpetas específicas de los buzones de Exchange o de los sitios de SharePoint y OneDrive para la empresa. Sin embargo, es posible buscar carpetas específicas (denominadas *colección de destino*) especificando el identificador o la ruta de acceso de la carpeta en la sintaxis de la consulta de búsqueda real. Usar la búsqueda de contenido para realizar una colección de destino es útil cuando tiene la certeza de que los elementos que responden a un caso o los elementos con privilegios están ubicados en un buzón o carpeta de sitio específicos. Puede usar el script de este artículo para obtener el identificador de carpeta para las carpetas de buzón o la ruta de acceso de las carpetas en un sitio de SharePoint y OneDrive para la empresa. A continuación, puede usar el identificador de carpeta o la ruta de acceso en una consulta de búsqueda para devolver los elementos que se encuentran en la carpeta.</span><span class="sxs-lookup"><span data-stu-id="c14c1-p102">The Content Search feature in the Office 365 Security &amp; Compliance Center doesn't provide a direct way in the UI to search specific folders in Exchange mailboxes or SharePoint and OneDrive for Business sites. However, it's possible to search specific folders (called a *targeted collection*) by specifying the folder ID or path in the actual search query syntax. Using Content Search to perform a targeted collection is useful when you're confident that items responsive to a case or privileged items are located in a specific mailbox or site folder. You can use the script in this article to obtain the folder ID for mailbox folders or the path for folders on a SharePoint and OneDrive for Business site. Then you can use the folder ID or path in a search query to return items located in the folder.</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="c14c1-111">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="c14c1-111">Before you begin</span></span>

- <span data-ttu-id="c14c1-p103">Debe ser miembro del grupo de roles eDiscovery Manager en el centro de seguridad &amp; y cumplimiento para ejecutar el script en el paso 1. Para obtener más información, consulte [asignar permisos de exhibición de documentos electrónicos &amp; en el centro de seguridad y cumplimiento de Office 365](assign-ediscovery-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="c14c1-p103">You have to be a member of the eDiscovery Manager role group in the Security &amp; Compliance Center to run the script in Step 1. For more information, see [Assign eDiscovery permissions in the Office‍ 365 Security &amp; Compliance Center](assign-ediscovery-permissions.md).</span></span>
    
    <span data-ttu-id="c14c1-p104">Además, debe tener asignado el rol destinatarios de correo en su organización de Exchange Online. Esto es necesario para ejecutar el cmdlet **Get-MailboxFolderStatistics** , que se incluye en el script en el paso 1. De forma predeterminada, la función destinatarios de correo se asigna a los grupos de funciones administración de la organización y administración de destinatarios en Exchange Online. Para obtener más información acerca de la asignación de permisos en Exchange Online, consulte [Manage role Group Members](https://go.microsoft.com/fwlink/p/?linkid=692102). También puede crear un grupo de funciones personalizado, asignarle el rol destinatarios de correo y, a continuación, agregar los miembros que necesitan ejecutar el script en el paso 1. Para obtener más información, vea [Manage role Groups](https://go.microsoft.com/fwlink/p/?linkid=730688).</span><span class="sxs-lookup"><span data-stu-id="c14c1-p104">Additionally, you have to be assigned the Mail Recipients role in your Exchange Online organization. This is required to run the **Get-MailboxFolderStatistics** cmdlet, which is included in the script in Step 1. By default, the Mail Recipients role is assigned to the Organization Management and Recipient Management role groups in Exchange Online. For more information about assigning permissions in Exchange Online, see [Manage role group members](https://go.microsoft.com/fwlink/p/?linkid=692102). You could also create a custom role group, assign the Mail Recipients role to it, and then add the members who need to run the script in Step 1. For more information, see [Manage role groups](https://go.microsoft.com/fwlink/p/?linkid=730688).</span></span>
    
- <span data-ttu-id="c14c1-p105">Cada vez que ejecute el script en el paso 1, se creará una nueva sesión de PowerShell remoto. Por lo tanto, puede usar todas las sesiones de PowerShell remoto disponibles. Para evitar que esto suceda, puede ejecutar el siguiente comando para desconectar las sesiones remotas de PowerShell activas.</span><span class="sxs-lookup"><span data-stu-id="c14c1-p105">Each time you run the script in Step 1, a new remote PowerShell session is created. So you could use up all the remote PowerShell sessions available to you. To prevent this from happening, you can run the following command to disconnect your active remote PowerShell sessions.</span></span>
    
  ```
  Get-PSSession | Remove-PSSession
  ```

    <span data-ttu-id="c14c1-123">Para obtener más información, vea [Conexión a Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span><span class="sxs-lookup"><span data-stu-id="c14c1-123">For more information, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span></span>
    
- <span data-ttu-id="c14c1-p106">El script incluye un tratamiento de errores mínimo. El objetivo principal de la secuencia de comandos es mostrar rápidamente una lista de identificadores de carpetas de buzones o rutas de sitios que se pueden usar en la sintaxis de la consulta de búsqueda de una búsqueda de contenido para realizar una colección de destino.</span><span class="sxs-lookup"><span data-stu-id="c14c1-p106">The script includes minimal error handling. The primary purpose of the script is to quickly display a list of mailbox folder IDs or site paths that can be used in the search query syntax of a Content Search to perform a targeted collection.</span></span>
    
- <span data-ttu-id="c14c1-p107">La secuencia de comandos de ejemplo proporcionada en este tema no es compatible con ningún servicio o programa de soporte estándar de Microsoft. El script de ejemplo se proporciona tal cual sin garantías de ningún tipo. Microsoft renuncia a todas las garantías implícitas, incluidas, entre otras, todas las garantías implícitas de comerciabilidad o de idoneidad para un propósito en particular. Todo el riesgo derivado del uso o el rendimiento de la secuencia de comandos de muestra y la documentación se conservan con usted. En ningún caso Microsoft, sus autores o cualquier otro implicado en la creación, la producción o la entrega de las secuencias de comandos serán responsables de cualquier daño (incluidos, entre otros, los daños causados por la pérdida de beneficios de negocio, la interrupción del negocio, la pérdida de información de la empresa u otra pérdida pecuniaria que surja del uso o la incapacidad para usar la documentación o los scripts de ejemplo, incluso si se ha notificado a Microsoft de la posibilidad de dichos daños.</span><span class="sxs-lookup"><span data-stu-id="c14c1-p107">The sample script provided in this topic isn't supported under any Microsoft standard support program or service. The sample script is provided AS IS without warranty of any kind. Microsoft further disclaims all implied warranties including, without limitation, any implied warranties of merchantability or of fitness for a particular purpose. The entire risk arising out of the use or performance of the sample script and documentation remains with you. In no event shall Microsoft, its authors, or anyone else involved in the creation, production, or delivery of the scripts be liable for any damages whatsoever (including, without limitation, damages for loss of business profits, business interruption, loss of business information, or other pecuniary loss) arising out of the use of or inability to use the sample scripts or documentation, even if Microsoft has been advised of the possibility of such damages.</span></span>
  
## <a name="step-1-run-the-script-to-get-a-list-of-folders-for-a-mailbox-or-site"></a><span data-ttu-id="c14c1-131">Paso 1: ejecutar el script para obtener una lista de las carpetas de un buzón de correo o sitio</span><span class="sxs-lookup"><span data-stu-id="c14c1-131">Step 1: Run the script to get a list of folders for a mailbox or site</span></span>

<span data-ttu-id="c14c1-p108">El script que se ejecuta en el primer paso devolverá una lista de carpetas de buzón de correo o carpetas de SharePoint o de OneDrive para la empresa, así como el identificador de carpeta o la ruta de acceso correspondientes para cada carpeta. Al ejecutar este script, se le pedirá la siguiente información.</span><span class="sxs-lookup"><span data-stu-id="c14c1-p108">The script that you run in this first step will return a list of mailbox folders or SharePoint or OneDrive for Business folders, and the corresponding folder ID or path for each folder. When you run this script, it will prompt you for the following information.</span></span>
  
- <span data-ttu-id="c14c1-p109">**Dirección de correo electrónico o dirección URL del sitio** Escriba una dirección de correo electrónico del custodio para obtener una lista de los identificadores de carpetas y carpetas de buzones de Exchange. O bien, escriba la dirección URL de un sitio de SharePoint o un sitio de OneDrive para la empresa para devolver una lista de rutas de la ubicación del sitio especificado. A continuación se muestran algunos ejemplos:</span><span class="sxs-lookup"><span data-stu-id="c14c1-p109">**Email address or site URL** Type an email address of the custodian to return a list of Exchange mailbox folders and folder IDs. Or type the URL for a SharePoint site or a OneDrive for Business site to return a list of paths for the specified site. Here are some examples:</span></span> 
    
  - <span data-ttu-id="c14c1-137">**Exchange** -stacig@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="c14c1-137">**Exchange** - stacig@contoso.onmicrosoft.com</span></span> 
    
  - <span data-ttu-id="c14c1-138">**SharePoint** - https://contoso.sharepoint.com/sites/marketing</span><span class="sxs-lookup"><span data-stu-id="c14c1-138">**SharePoint** - https://contoso.sharepoint.com/sites/marketing</span></span> 
    
  - <span data-ttu-id="c14c1-139">**OneDrive para la empresa** - https://contoso-my.sharepoint.com/personal/stacig_contoso_onmicrosoft_com</span><span class="sxs-lookup"><span data-stu-id="c14c1-139">**OneDrive for Business** - https://contoso-my.sharepoint.com/personal/stacig_contoso_onmicrosoft_com</span></span> 
    
- <span data-ttu-id="c14c1-p110">**Sus credenciales de usuario** : el script usará sus credenciales para conectarse a Exchange Online y &amp; al centro de seguridad y cumplimiento con PowerShell remoto. Como se ha explicado anteriormente, tiene que asignar los permisos adecuados para que este script se ejecute correctamente.</span><span class="sxs-lookup"><span data-stu-id="c14c1-p110">**Your user credentials** - The script will use your credentials to connect to Exchange Online and the Security &amp; Compliance Center with remote PowerShell. As previously explained, you have to assigned the appropriate permissions to successfully run this script.</span></span>
    
<span data-ttu-id="c14c1-142">Para mostrar una lista de las carpetas del buzón o los nombres de las rutas de acceso a sitios:</span><span class="sxs-lookup"><span data-stu-id="c14c1-142">To display a list of mailbox folders or site path names:</span></span>
  
1. <span data-ttu-id="c14c1-143">Guarde el siguiente texto en un archivo de script de Windows PowerShell mediante un sufijo de nombre de archivo de. ps1; por ejemplo, `GetFolderSearchParameters.ps1`.</span><span class="sxs-lookup"><span data-stu-id="c14c1-143">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `GetFolderSearchParameters.ps1`.</span></span>
    
  ```
  #########################################################################################################
  # This PowerShell script will prompt you for:                             #
  #    * Admin credentials for a user who can run the Get-MailboxFolderStatistics cmdlet in Exchange    #
  #      Online and who is an eDiscovery Manager in the Security &amp; Compliance Center.           #
  # The script will then:                                           #
  #    * If an email address is supplied: list the folders for the target mailbox.          #
  #    * If a SharePoint or OneDrive for Business site is supplied: list the folder paths for the site. #
  #    * In both cases, the script supplies the correct search properties (folderid: or path:)      #
  #      appended to the folder ID or path ID to use in a Content Search.               #
  # Notes:                                              #
  #    * For SharePoint and OneDrive for Business, the paths are searched recursively; this means the   #
  #      the current folder and all sub-folders are searched.                       #
  #    * For Exchange, only the specified folder will be searched; this means sub-folders in the folder #
  #      will not be searched.  To search sub-folders, you need to use the specify the folder ID for    #
  #      each sub-folder that you want to search.                               #
  #    * For Exchange, only folders in the user's primary mailbox will be returned by the script.       #
  #########################################################################################################
  # Collect the target email address or SharePoint Url
  $addressOrSite = Read-Host "Enter an email address or a URL for a SharePoint or OneDrive for Business site"
  # Authenticate with Exchange Online and the Security &amp; Compliance Center (Exchange Online Protection - EOP)
  if (!$credentials)
  {
      $credentials = Get-Credential
  }
  if ($addressOrSite.IndexOf("@") -ige 0)
  {
      # List the folder Ids for the target mailbox
      $emailAddress = $addressOrSite
      # Authenticate with Exchange Online
      if (!$ExoSession)
      {
          $ExoSession = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.outlook.com/powershell-liveid/ -Credential $credentials -Authentication Basic -AllowRedirection
          Import-PSSession $ExoSession -AllowClobber -DisableNameChecking
      }
      $folderQueries = @()
      $folderStatistics = Get-MailboxFolderStatistics $emailAddress
      foreach ($folderStatistic in $folderStatistics)
      {
          $folderId = $folderStatistic.FolderId;
          $folderPath = $folderStatistic.FolderPath;
          $encoding= [System.Text.Encoding]::GetEncoding("us-ascii")
          $nibbler= $encoding.GetBytes("0123456789ABCDEF");
          $folderIdBytes = [Convert]::FromBase64String($folderId);
          $indexIdBytes = New-Object byte[] 48;
          $indexIdIdx=0;
          $folderIdBytes | select -skip 23 -First 24 | %{$indexIdBytes[$indexIdIdx++]=$nibbler[$_ -shr 4];$indexIdBytes[$indexIdIdx++]=$nibbler[$_ -band 0xF]}
          $folderQuery = "folderid:$($encoding.GetString($indexIdBytes))";
          $folderStat = New-Object PSObject
          Add-Member -InputObject $folderStat -MemberType NoteProperty -Name FolderPath -Value $folderPath
          Add-Member -InputObject $folderStat -MemberType NoteProperty -Name FolderQuery -Value $folderQuery
          $folderQueries += $folderStat
      }
      Write-Host "-----Exchange Folders-----"
      $folderQueries |ft
  }
  elseif ($addressOrSite.IndexOf("http") -ige 0)
  {
      $searchName = "SPFoldersSearch"
      $searchActionName = "SPFoldersSearch_Preview"
      # List the folders for the SharePoint or OneDrive for Business Site
      $siteUrl = $addressOrSite
      # Authenticate with the Security &amp; Compliance Center
      if (!$SccSession)
      {
          $SccSession = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Credential $credentials -Authentication Basic -AllowRedirection
          Import-PSSession $SccSession -AllowClobber -DisableNameChecking
      }
      # Clean-up, if the script was aborted, the search we created might not have been deleted.  Try to do so now.
      Remove-ComplianceSearch $searchName -Confirm:$false -ErrorAction 'SilentlyContinue'
      # Create a Content Search against the SharePoint Site or OneDrive for Business site and only search for folders; wait for the search to complete
      $complianceSearch = New-ComplianceSearch -Name $searchName -ContentMatchQuery "contenttype:folder" -SharePointLocation $siteUrl
      Start-ComplianceSearch $searchName
      do{
          Write-host "Waiting for search to complete..."
          Start-Sleep -s 5
          $complianceSearch = Get-ComplianceSearch $searchName
      }while ($complianceSearch.Status -ne 'Completed')
      if ($complianceSearch.Items -gt 0)
      {
          # Create a Compliance Search Action and wait for it to complete. The folders will be listed in the .Results parameter
          $complianceSearchAction = New-ComplianceSearchAction -SearchName $searchName -Preview
          do
          {
              Write-host "Waiting for search action to complete..."
              Start-Sleep -s 5
              $complianceSearchAction = Get-ComplianceSearchAction $searchActionName
          }while ($complianceSearchAction.Status -ne 'Completed')
          # Get the results and print out the folders
          $results = $complianceSearchAction.Results
          $matches = Select-String "Data Link:.+[,}]" -Input $results -AllMatches
          foreach ($match in $matches.Matches)
          {
              $rawUrl = $match.Value
              $rawUrl = $rawUrl -replace "Data Link: " -replace "," -replace "}"
              Write-Host "path:""$rawUrl"""
          }
      }
      else
      {
          Write-Host "No folders were found for $siteUrl"
      }
      Remove-ComplianceSearch $searchName -Confirm:$false -ErrorAction 'SilentlyContinue'
  }
  else
  {
      Write-Error "Couldn't recognize $addressOrSite as an email address or a site URL"
  }
  ```

2. <span data-ttu-id="c14c1-144">En el equipo local, abra Windows PowerShell y vaya a la carpeta donde guardó el script.</span><span class="sxs-lookup"><span data-stu-id="c14c1-144">On your local computer, open Windows PowerShell and go to the folder where you saved the script.</span></span>
    
3. <span data-ttu-id="c14c1-145">Ejecutar el script; por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="c14c1-145">Run the script; for example:</span></span>
    
      ```
      .\GetFolderSearchParameters.ps1
      ```

4. <span data-ttu-id="c14c1-146">Escriba la información que el script le pide.</span><span class="sxs-lookup"><span data-stu-id="c14c1-146">Enter the information that the script prompts you for.</span></span>
    
    <span data-ttu-id="c14c1-p111">La secuencia de comandos muestra una lista de las carpetas del buzón o la carpeta del sitio para el usuario especificado. Deje esta ventana abierta para que pueda copiar un identificador de carpeta o un nombre de ruta de acceso y pegarlo en una consulta de búsqueda en el paso 2.</span><span class="sxs-lookup"><span data-stu-id="c14c1-p111">The script displays a list of mailbox folders or site folder for the specified user. Let this window open so that you can copy a folder ID or path name and paste it in to a search query in Step 2.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="c14c1-p112">En lugar de mostrar una lista de carpetas en la pantalla del equipo, puede redirigir el resultado del script a un archivo de texto. Este archivo se guardará en la carpeta en la que se encuentra el script. Por ejemplo, para redirigir la salida del script a un archivo de texto, ejecute el siguiente comando en el `.\GetFolderSearchParameters.ps1 > StacigFolderIds.txt` paso 3: a continuación, puede copiar un identificador de carpeta o una ruta de acceso del archivo que se va a usar en una consulta de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="c14c1-p112">Instead of displaying a list of folders on the computer screen, you can re-direct the output of the script to a text file. This file will be saved to the folder where the script is located. For example, to redirect the script output to a text file, run the following command in Step 3:  `.\GetFolderSearchParameters.ps1 > StacigFolderIds.txt` Then you can copy a folder ID or path from the file to use in a search query.</span></span>
  
### <a name="script-output-for-mailbox-folders"></a><span data-ttu-id="c14c1-152">Salida de script para carpetas de buzón</span><span class="sxs-lookup"><span data-stu-id="c14c1-152">Script output for mailbox folders</span></span>

<span data-ttu-id="c14c1-p113">Si está obteniendo identificadores de carpeta de buzón de correo, el script se conecta a Exchange online mediante PowerShell remoto, ejecuta el cmdlet **Get-MailboxFolderStatisics** y, a continuación, muestra la lista de las carpetas del buzón especificado. Para cada carpeta del buzón, el script muestra el nombre de la carpeta en la columna **folderPath** y el identificador de la carpeta en la columna **FolderQuery** . Además, el script agrega el prefijo de **folderId** (que es el nombre de la propiedad Mailbox) al identificador de la carpeta. Dado que la propiedad **folderId** es una propiedad que se puede buscar, `folderid:<folderid>` usará en una consulta de búsqueda en el paso 2 para buscar en esa carpeta.</span><span class="sxs-lookup"><span data-stu-id="c14c1-p113">If you're getting mailbox folder IDs, the script connects to Exchange Online by using remote PowerShell, runs the **Get-MailboxFolderStatisics** cmdlet, and then displays the list of the folders from the specified mailbox. For every folder in the mailbox, the script displays the name of the folder in the **FolderPath** column and the folder ID in the **FolderQuery** column. Additionally, the script adds the prefix of **folderId** (which is the name of the mailbox property) to the folder ID. Because the **folderid** property is a searchable property, you'll use  `folderid:<folderid>` in a search query in Step 2 to search that folder.</span></span> 
  
<span data-ttu-id="c14c1-157">A continuación, se muestra un ejemplo del resultado devuelto por el script para las carpetas de buzón de correo.</span><span class="sxs-lookup"><span data-stu-id="c14c1-157">Here's an example of the output returned by the script for mailbox folders.</span></span>
  
![Ejemplo de la lista de carpetas de buzones y de identificadores de carpetas devueltos por el script](media/cd739207-eb84-4ebf-a03d-703f3d3a797d.png)
  
<span data-ttu-id="c14c1-159">El ejemplo del paso 2 muestra la consulta utilizada para buscar en la subcarpeta Purges de la carpeta elementos recuperables del usuario.</span><span class="sxs-lookup"><span data-stu-id="c14c1-159">The example in Step 2 shows the query used to search the Purges subfolder in the user's Recoverable Items folder.</span></span>
  
### <a name="script-output-for-site-folders"></a><span data-ttu-id="c14c1-160">Salida de script para carpetas de sitio</span><span class="sxs-lookup"><span data-stu-id="c14c1-160">Script output for site folders</span></span>

<span data-ttu-id="c14c1-p114">Si va a obtener rutas de sitios de SharePoint o de OneDrive para la empresa, el script se &amp; conecta al centro de seguridad y cumplimiento mediante PowerShell remoto, crea una nueva búsqueda de contenido que busca carpetas en el sitio y, a continuación, muestra una lista de las carpetas. ubicado en el sitio especificado. El script muestra el nombre de cada carpeta y agrega el prefijo de la **ruta de acceso** (que es el nombre de la propiedad del sitio) a la dirección URL de la carpeta. Dado que la propiedad **path** es una propiedad que se puede buscar, `path:<path>` usará en una consulta de búsqueda en el paso 2 para buscar en esa carpeta.</span><span class="sxs-lookup"><span data-stu-id="c14c1-p114">If you're getting paths from SharePoint or OneDrive for Business sites, the script connects to the Security &amp; Compliance Center using remote PowerShell, creates a new Content Search that searches the site for folders, and then displays a list of the folders located in the specified site. The script displays the name of each folder and adds the prefix of **path** (which is the name of the site property) to the folder URL. Because the **path** property is a searchable property, you'll use  `path:<path>` in a search query in Step 2 to search that folder.</span></span> 
  
<span data-ttu-id="c14c1-164">A continuación, se muestra un ejemplo de los resultados devueltos por el script para las carpetas del sitio.</span><span class="sxs-lookup"><span data-stu-id="c14c1-164">Here's an example of the output returned by the script for site folders.</span></span>
  
![Ejemplo de la lista de nombres de ruta de acceso para las carpetas de sitio devueltas por el script](media/519e8347-7365-4067-af78-96c465dc3d15.png)
  
## <a name="step-2-use-a-folder-id-or-path-to-perform-a-targeted-collection"></a><span data-ttu-id="c14c1-166">Paso 2: usar un identificador de carpeta o una ruta de acceso para realizar una colección de destino</span><span class="sxs-lookup"><span data-stu-id="c14c1-166">Step 2: Use a folder ID or path to perform a targeted collection</span></span>

<span data-ttu-id="c14c1-p115">Después de ejecutar el script para recopilar una lista de identificadores de carpeta o rutas de acceso para un usuario específico, el siguiente paso para &amp; ir al centro de cumplimiento y crear una nueva búsqueda de contenido para buscar en una carpeta específica. Use la `folderid:<folderid>` propiedad o `path:<path>` en la consulta de búsqueda que configure en el cuadro palabra clave de búsqueda de contenido (o como el valor para el parámetro *ContentMatchQuery* si usa el cmdlet **New-ComplianceSearch** ). Puede combinar la `folderid` propiedad o `path` con otros parámetros de búsqueda o condiciones de búsqueda. Si solo incluye la `folderid` propiedad o `path` en la consulta, la búsqueda devolverá todos los elementos que se encuentran en la carpeta especificada.</span><span class="sxs-lookup"><span data-stu-id="c14c1-p115">After you've run the script to collect a list of folder IDs or paths for a specific user, the next step to go to the Security &amp; Compliance Center and create a new Content Search to search a specific folder. You'll use the  `folderid:<folderid>` or  `path:<path>` property in the search query that you configure in the Content Search keyword box (or as the value for the  *ContentMatchQuery*  parameter if you use the **New-ComplianceSearch** cmdlet). You can combine the  `folderid` or  `path` property with other search parameters or search conditions. If you only include the  `folderid` or  `path` property in the query, the search will return all items located in the specified folder.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="c14c1-171">Usar la `path` propiedad para buscar en ubicaciones de OneDrive no devolverá archivos multimedia, como archivos. png,. TIFF o. wav, en los resultados de la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="c14c1-171">Using the  `path` property to search OneDrive locations won't return media files, such as .png, .tiff, or .wav files, in the search results.</span></span> 
  
1. <span data-ttu-id="c14c1-172">Vaya a [https://protection.office.com](https://protection.office.com).</span><span class="sxs-lookup"><span data-stu-id="c14c1-172">Go to [https://protection.office.com](https://protection.office.com).</span></span>
    
2. <span data-ttu-id="c14c1-173">Inicie sesión en Office 365 con la cuenta y las credenciales que usó para ejecutar el script en el paso 1.</span><span class="sxs-lookup"><span data-stu-id="c14c1-173">Sign in to Office 365 using the account and credentials that you used to run the script in Step 1.</span></span>
    
3. <span data-ttu-id="c14c1-174">En el panel izquierdo del centro de &amp; seguridad y cumplimiento, haga clic en búsqueda de \> **contenido**de \*\* &amp; investigación\*\* y en **nuevo** ![icono](media/O365-MDM-CreatePolicy-AddIcon.gif)agregar.</span><span class="sxs-lookup"><span data-stu-id="c14c1-174">In the left pane of the Security &amp; Compliance Center, click **Search &amp; investigation** \> **Content search**, and then click **New** ![Add icon](media/O365-MDM-CreatePolicy-AddIcon.gif).</span></span>
    
4. <span data-ttu-id="c14c1-p116">En la página **Búsqueda nueva**, escriba un nombre para la búsqueda de contenido. Este nombre debe ser único en la organización.</span><span class="sxs-lookup"><span data-stu-id="c14c1-p116">On the **New search** page, type a name for the Content Search. This name has to be unique in your organization.</span></span> 
    
5. <span data-ttu-id="c14c1-177">En **¿dónde desea**que se vean?, realice una de las siguientes acciones, en función de si está buscando en una carpeta de buzón de correo o en una carpeta de sitio:</span><span class="sxs-lookup"><span data-stu-id="c14c1-177">Under **Where do you want us to look**, do one of the following, based on whether you're searching a mailbox folder or a site folder:</span></span>
    
    - <span data-ttu-id="c14c1-178">Haga clic en **elegir buzones específicos para buscar** y, a continuación, agregue el mismo buzón que especificó cuando ejecutó el script en el paso 1.</span><span class="sxs-lookup"><span data-stu-id="c14c1-178">Click **Choose specific mailboxes to search** and then add the same mailbox that you specified when you ran the script in Step 1.</span></span> 
    
      <span data-ttu-id="c14c1-179">O bien</span><span class="sxs-lookup"><span data-stu-id="c14c1-179">Or</span></span>
    
    - <span data-ttu-id="c14c1-180">Haga clic en **elegir sitios específicos para buscar** en buscar y, a continuación, agregue la dirección URL del sitio que especificó al ejecutar el script en el paso 1.</span><span class="sxs-lookup"><span data-stu-id="c14c1-180">Click **Choose specific sites to search** to search and then add the same site URL that you specified when you ran the script in Step 1.</span></span> 
    
6. <span data-ttu-id="c14c1-181">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="c14c1-181">Click **Next**.</span></span>
    
7. <span data-ttu-id="c14c1-182">En el cuadro palabra clave de la página **¿qué desea que busquemos?** , pegue el `folderid:<folderid>` valor `path:<path>` o deVuelto por el script en el paso 1.</span><span class="sxs-lookup"><span data-stu-id="c14c1-182">In the keyword box on the **What do you want us to look for** page, paste the  `folderid:<folderid>` or  `path:<path>` value that was returned by the script in Step 1.</span></span> 
    
    <span data-ttu-id="c14c1-183">Por ejemplo, en la siguiente captura de pantalla se buscará cualquier elemento de la subcarpeta dePuraciones en la carpeta elementos recuperables del usuario (el valor de la `folderid` propiedad de la subcarpeta purgas se muestra en la captura de pantalla del paso 1):</span><span class="sxs-lookup"><span data-stu-id="c14c1-183">For example, the query in the following screenshot will search for any item in the Purges subfolder in the user's Recoverable Items folder (the value of the `folderid` property for the Purges subfolder is shown in the screenshot in Step 1):</span></span>
    
    ![Pegue la folderId o ruta de acceso en el cuadro de palabra clave de la consulta de búsqueda](media/84057516-b663-48a4-a78f-8032a8f8da80.png)
  
8. <span data-ttu-id="c14c1-185">Haga clic en **Buscar** para iniciar la búsqueda de colección de destino.</span><span class="sxs-lookup"><span data-stu-id="c14c1-185">Click **Search** to start the targeted collection search.</span></span> 
  
### <a name="examples-of-search-queries-for-targeted-collections"></a><span data-ttu-id="c14c1-186">Ejemplos de consultas de búsqueda para colecciones dirigidas</span><span class="sxs-lookup"><span data-stu-id="c14c1-186">Examples of search queries for targeted collections</span></span>

<span data-ttu-id="c14c1-p117">A continuación se muestran algunos ejemplos de `folderid` cómo `path` usar las propiedades y en una consulta de búsqueda para realizar una colección de destino. Tenga en cuenta que los marcadores de `folderid:<folderid>` posición `path:<path>` se usan para y para ahorrar espacio.</span><span class="sxs-lookup"><span data-stu-id="c14c1-p117">Here are some examples of using the  `folderid` and  `path` properties in a search query to perform a targeted collection. Note that placeholders are used for  `folderid:<folderid>` and  `path:<path>` to save space.</span></span> 
  
- <span data-ttu-id="c14c1-p118">En este ejemplo se buscan tres carpetas de buzón diferentes. Puede usar sintaxis de consulta similar para buscar en las carpetas ocultas de la carpeta elementos recuperables de un usuario.</span><span class="sxs-lookup"><span data-stu-id="c14c1-p118">This example searches three different mailbox folders. You could use similar query syntax to search the hidden folders in a user's Recoverable Items folder.</span></span>
    
  ```
  folderid:<folderid> OR folderid:<folderid> OR folderid:<folderid>
  ```

- <span data-ttu-id="c14c1-191">En este ejemplo se busca en una carpeta de buzón los elementos que contienen una frase exacta.</span><span class="sxs-lookup"><span data-stu-id="c14c1-191">This example searches a mailbox folder for items that contain an exact phrase.</span></span>
    
  ```
  folderid:<folderid> AND "Contoso financial results"
  ```

- <span data-ttu-id="c14c1-192">En este ejemplo se busca en una carpeta del sitio (y en cualquier subcarpeta) documentos que contengan las letras "NDA" en el título.</span><span class="sxs-lookup"><span data-stu-id="c14c1-192">This example searches a site folder (and any subfolders) for documents that contain the letters "NDA" in the title.</span></span>
    
  ```
  path:<path> AND filename:nda
  ```

- <span data-ttu-id="c14c1-193">En este ejemplo se busca en una carpeta del sitio (y en cualquier subcarpeta) los documentos que se han modificado en un intervalo de fechas.</span><span class="sxs-lookup"><span data-stu-id="c14c1-193">This example searches a site folder (and any subfolder) for documents there were changed within a date range.</span></span>
    
  ```
  path:<path> AND (lastmodifiedtime>=01/01/2017 AND lastmodifiedtime<=01/21/2017)
  ```
  
## <a name="more-information"></a><span data-ttu-id="c14c1-194">Más información</span><span class="sxs-lookup"><span data-stu-id="c14c1-194">More information</span></span>

<span data-ttu-id="c14c1-195">Tenga en cuenta lo siguiente cuando use el script de este artículo para realizar colecciones de destino.</span><span class="sxs-lookup"><span data-stu-id="c14c1-195">Keep the following things in mind when using the script in this article to perform targeted collections.</span></span>
  
- <span data-ttu-id="c14c1-p119">El script no quita ninguna carpeta de los resultados. Por lo tanto, algunas carpetas que aparecen en los resultados podrían no ser buscadas (o devolver cero elementos) porque contienen contenido generado por el sistema.</span><span class="sxs-lookup"><span data-stu-id="c14c1-p119">The script doesn't remove any folders from the results. So some folders listed in the results might be unsearchable (or return zero items) because they contain system-generated content.</span></span>
    
- <span data-ttu-id="c14c1-p120">Este script solo devuelve información de la carpeta del buzón de correo principal del usuario. No devuelve información sobre las carpetas en el buzón de archivo del usuario.</span><span class="sxs-lookup"><span data-stu-id="c14c1-p120">This script only returns folder information for the user's primary mailbox. It doesn't return information about folders in the user's archive mailbox.</span></span>
    
- <span data-ttu-id="c14c1-p121">Al buscar carpetas de buzón de correo, solo se buscará en `folderid` la carpeta especificada (identificada por su propiedad). No se buscará en las subcarpetas. Para buscar en las subcarpetas, debe usar el identificador de carpeta de la subcarpeta que desea buscar.</span><span class="sxs-lookup"><span data-stu-id="c14c1-p121">When searching mailbox folders, only the specified folder (identified by its  `folderid` property) will be searched. Subfolders won't be searched. To search sub-folders, you need to use the  folder ID for the sub-folder that you want to search.</span></span> 
    
- <span data-ttu-id="c14c1-203">Al realizar búsquedas en carpetas de sitio, se buscará `path` en la carpeta (identificada por su propiedad) y en todas las subcarpetas.</span><span class="sxs-lookup"><span data-stu-id="c14c1-203">When searching site folders, the folder (identified by its  `path` property) and all sub-folders will be searched.</span></span> 
    
- <span data-ttu-id="c14c1-p122">Como se mencionó anteriormente, no se `path` puede usar Property para buscar archivos multimedia, como archivos. png,. TIFF o. wav, ubicados en ubicaciones de OneDrive. Use una [propiedad de sitio](keyword-queries-and-search-conditions.md#searchable-site-properties) diferente para buscar archivos multimedia en las carpetas de OneDrive.</span><span class="sxs-lookup"><span data-stu-id="c14c1-p122">As previously stated, you can't use  `path` property to search for media files, such as .png, .tiff, or .wav files, located in OneDrive locations. Use a different [site property](keyword-queries-and-search-conditions.md#searchable-site-properties) to search for media files in OneDrive folders.</span></span> 

- <span data-ttu-id="c14c1-p123">Al exportar los resultados de una búsqueda en la que solo especificó `folderid` la propiedad en la consulta de búsqueda, puede elegir la primera opción de exportación: "todos los elementos, excluidos los que tienen un formato no reconocido, están cifrados o no se indizaron por otros motivos". Todos los elementos de la carpeta siempre se exportarán independientemente de su estado de indización, ya que el identificador de carpeta siempre está indizado.</span><span class="sxs-lookup"><span data-stu-id="c14c1-p123">When exporting the results of a search in which you only specified the `folderid` property in the search query, you can choose the first export option, "All items, excluding ones that have an unrecognized format, are encrypted, or weren't indexed for other reasons." All items in the folder will always be exported regardless of their indexing status because the folder ID is always indexed.</span></span>
