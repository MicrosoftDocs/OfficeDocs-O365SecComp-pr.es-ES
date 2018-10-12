---
title: Usar búsqueda de contenido en Office 365 para las colecciones de destinadas
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 10/12/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid: MOE150
ms.assetid: e3cbc79c-5e97-43d3-8371-9fbc398cd92e
description: Usar búsqueda de contenido en la seguridad de Office 365 &amp; centro de cumplimiento para llevar a cabo las colecciones de destinadas. Una colección de destino significa que el que esté seguro de que los elementos con capacidad de respuesta a un caso de o elementos con privilegios se encuentran en una carpeta de buzón de correo o de sitio específica. Use la secuencia de comandos de este artículo para obtener el identificador de la carpeta o la ruta de acceso para las carpetas de buzón de correo o sitio específicas que desea buscar.
ms.openlocfilehash: f4bb63a193a11e7467b3b296b2bdfa50657ae65a
ms.sourcegitcommit: 448c5897e44448adfc82e3eaffb774c770c04815
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/12/2018
ms.locfileid: "25522291"
---
# <a name="use-content-search-in-office-365-for-targeted-collections"></a><span data-ttu-id="a65e6-105">Usar búsqueda de contenido en Office 365 para las colecciones de destinadas</span><span class="sxs-lookup"><span data-stu-id="a65e6-105">Use Content Search in Office 365 for targeted collections</span></span>

<span data-ttu-id="a65e6-p102">La característica de búsqueda de contenido de la seguridad de Office 365 &amp; centro de cumplimiento no proporciona una forma directa en la interfaz de usuario para buscar carpetas específicas en los buzones de Exchange o SharePoint y OneDrive sitios profesionales. Sin embargo, es posible buscar carpetas específicas (denominadas una colección de destino) especificando el identificador de la carpeta o la ruta de acceso en la sintaxis de consulta de búsqueda reales. Uso de búsqueda de contenido para llevar a cabo una colección de destino es útil cuando esté seguro de que los elementos con capacidad de respuesta a un caso de o elementos con privilegios se encuentran en una carpeta de buzón de correo o de sitio específica. Puede usar la secuencia de comandos en este artículo para obtener el identificador de carpeta para carpetas del buzón o la ruta de acceso para las carpetas en un SharePoint y OneDrive para el sitio de negocio. A continuación, puede usar el identificador de la carpeta o la ruta de acceso en una consulta de búsqueda para devolver los elementos que se encuentran en la carpeta.</span><span class="sxs-lookup"><span data-stu-id="a65e6-p102">The Content Search feature in the Office 365 Security &amp; Compliance Center doesn't provide a direct way in the UI to search specific folders in Exchange mailboxes or SharePoint and OneDrive for Business sites. However, it is possible to search specific folders (called a targeted collection) by specifying the folder ID or path in the actual search query syntax. Using Content Search to perform a targeted collection is useful when you're confident that items responsive to a case or privileged items are located in a specific mailbox or site folder. You can use the script in this article to obtain the folder ID for mailbox folders or the path for folders on a SharePoint and OneDrive for Business site. Then you can use the folder ID or path in a search query to return items located in the folder.</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="a65e6-111">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="a65e6-111">Before you begin</span></span>

- <span data-ttu-id="a65e6-p103">Tiene que ser un miembro del grupo de roles de administrador de exhibición de documentos electrónicos en la seguridad &amp; centro de cumplimiento para ejecutar el script en el paso 1. Para obtener más información, vea [asignar permisos de exhibición de documentos electrónicos en la seguridad de Office 365 &amp; centro de cumplimiento](assign-ediscovery-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="a65e6-p103">You have to be a member of the eDiscovery Manager role group in the Security &amp; Compliance Center to run the script in Step 1. For more information, see [Assign eDiscovery permissions in the Office‍ 365 Security &amp; Compliance Center](assign-ediscovery-permissions.md).</span></span>
    
    <span data-ttu-id="a65e6-p104">Además, debe tener asignado el rol de destinatarios de correo en la organización de Exchange Online. Este proceso es necesario para ejecutar el cmdlet **Get-MailboxFolderStatistics** , que se incluye en la secuencia de comandos en el paso 1. De forma predeterminada, el rol de destinatarios de correo se asigna a los grupos de funciones de administración de la organización y administración de destinatarios en Exchange Online. Para obtener más información acerca de cómo asignar permisos en Exchange Online, consulte [Manage role group members](https://go.microsoft.com/fwlink/p/?linkid=692102). Podría crear también un grupo de roles personalizados, asignar el rol de destinatarios de correo a ella y, a continuación, agregar a los miembros que necesitan para ejecutar el script en el paso 1. Para obtener más información, vea [Administrar grupos de roles](https://go.microsoft.com/fwlink/p/?linkid=730688).</span><span class="sxs-lookup"><span data-stu-id="a65e6-p104">Additionally, you have to be assigned the Mail Recipients role in your Exchange Online organization. This is required to run the **Get-MailboxFolderStatistics** cmdlet, which is included in the script in Step 1. By default, the Mail Recipients role is assigned to the Organization Management and Recipient Management role groups in Exchange Online. For more information about assigning permissions in Exchange Online, see [Manage role group members](https://go.microsoft.com/fwlink/p/?linkid=692102). You could also create a custom role group, assign the Mail Recipients role to it, and then add the members who need to run the script in Step 1. For more information, see [Manage role groups](https://go.microsoft.com/fwlink/p/?linkid=730688).</span></span>
    
- <span data-ttu-id="a65e6-p105">Cada vez que se ejecuta la secuencia de comandos en el paso 1, se crea una nueva sesión de PowerShell remota. Así se puede usar seguridad de todas las PowerShell sesiones remotas disponibles para usted. Para evitar que esto ocurra, puede ejecutar el siguiente comando para desconectar las sesiones de PowerShell remotas activas.</span><span class="sxs-lookup"><span data-stu-id="a65e6-p105">Each time you run the script in Step 1, a new remote PowerShell session is created. So you could use up all the remote PowerShell sessions available to you. To prevent this from happening, you can run the following command to disconnect your active remote PowerShell sessions.</span></span>
    
  ```
  Get-PSSession | Remove-PSSession
  ```

    <span data-ttu-id="a65e6-123">Para obtener más información, vea [Conexión a Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span><span class="sxs-lookup"><span data-stu-id="a65e6-123">For more information, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span></span>
    
- <span data-ttu-id="a65e6-p106">La secuencia de comandos incluye el tratamiento de errores mínima. El propósito principal de la secuencia de comandos es mostrar una lista de identificadores de carpeta de buzón o rutas de acceso que pueden usarse para llevar a cabo una colección de destino en la sintaxis de consulta de búsqueda de una búsqueda de contenido de sitio rápidamente.</span><span class="sxs-lookup"><span data-stu-id="a65e6-p106">The script includes minimal error handling. The primary purpose of the script is to quickly display a list of mailbox folder IDs or site paths that can be used in the search query syntax of a Content Search to perform a targeted collection.</span></span>
    
- <span data-ttu-id="a65e6-p107">El script de ejemplo proporcionado en este tema no es compatible con ningún servicio o programa de soporte estándar de Microsoft. El script de ejemplo se proporciona tal cual sin garantía de ningún tipo. Microsoft renuncia a todas las garantías implícitas incluidas, sin limitación, cualquier las garantías implícitas de comerciabilidad o de idoneidad para un fin determinado. Todo el riesgo que pueda surgir por el uso o el rendimiento de la secuencia de comandos de ejemplo y documentación permanece con usted. En ningún caso Microsoft, sus autores o cualquier otro implicado en la creación, producción o entrega de las secuencias de comandos serán responsables de los daños índole (incluidos, pero sin limitarse a, daños por pérdida de beneficios empresariales, interrupción del negocio, pérdida de información de la empresa, o en otras pérdidas de carácter económico) derivado del uso o la incapacidad de usar los scripts de ejemplo o documentación, aunque Microsoft haya sido notificado de la posibilidad de dichos daños.</span><span class="sxs-lookup"><span data-stu-id="a65e6-p107">The sample script provided in this topic isn't supported under any Microsoft standard support program or service. The sample script is provided AS IS without warranty of any kind. Microsoft further disclaims all implied warranties including, without limitation, any implied warranties of merchantability or of fitness for a particular purpose. The entire risk arising out of the use or performance of the sample script and documentation remains with you. In no event shall Microsoft, its authors, or anyone else involved in the creation, production, or delivery of the scripts be liable for any damages whatsoever (including, without limitation, damages for loss of business profits, business interruption, loss of business information, or other pecuniary loss) arising out of the use of or inability to use the sample scripts or documentation, even if Microsoft has been advised of the possibility of such damages.</span></span>
  
## <a name="step-1-run-the-script-to-get-a-list-of-folders-for-a-mailbox-or-site"></a><span data-ttu-id="a65e6-131">Paso 1: Ejecutar el script para obtener una lista de carpetas de un buzón de correo o sitio</span><span class="sxs-lookup"><span data-stu-id="a65e6-131">Step 1: Run the script to get a list of folders for a mailbox or site</span></span>

<span data-ttu-id="a65e6-p108">La secuencia de comandos que se ejecuta en este primer paso devolverá una lista de carpetas del buzón o SharePoint o OneDrive para las carpetas de negocio y el identificador correspondiente de carpeta o ruta de acceso para cada carpeta. Al ejecutar este script, le pedirá la siguiente información.</span><span class="sxs-lookup"><span data-stu-id="a65e6-p108">The script that you run in this first step will return a list of mailbox folders or SharePoint or OneDrive for Business folders, and the corresponding folder ID or path for each folder. When you run this script, it will prompt you for the following information.</span></span>
  
- <span data-ttu-id="a65e6-p109">**Dirección URL de sitio o dirección de correo electrónico** Escriba una dirección de correo electrónico de la custodia para devolver una lista de carpetas de buzón de correo de Exchange y los identificadores de doblado. O bien, escriba la dirección URL de un sitio de SharePoint o un OneDrive para el sitio de negocio para devolver una lista de rutas de acceso para el sitio especificado. Estos son algunos ejemplos:</span><span class="sxs-lookup"><span data-stu-id="a65e6-p109">**Email address or site URL** Type an email address of the custodian to return a list of Exchange mailbox folders and fold IDs. Or type the URL for a SharePoint site or a OneDrive for Business site to return a list of paths for the specified site. Here are some examples:</span></span> 
    
  - <span data-ttu-id="a65e6-137">**Exchange** - stacig@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="a65e6-137">**Exchange** - stacig@contoso.onmicrosoft.com</span></span> 
    
  - <span data-ttu-id="a65e6-138">**SharePoint** - https://contoso.sharepoint.com/sites/marketing</span><span class="sxs-lookup"><span data-stu-id="a65e6-138">**SharePoint** - https://contoso.sharepoint.com/sites/marketing</span></span> 
    
  - <span data-ttu-id="a65e6-139">**OneDrive para la empresa** - https://contoso-my.sharepoint.com/personal/stacig_contoso_onmicrosoft_com</span><span class="sxs-lookup"><span data-stu-id="a65e6-139">**OneDrive for Business** - https://contoso-my.sharepoint.com/personal/stacig_contoso_onmicrosoft_com</span></span> 
    
- <span data-ttu-id="a65e6-p110">**Sus credenciales de usuario** : la secuencia de comandos usará las credenciales para conectarse a Exchange Online y la seguridad &amp; centro de cumplimiento con PowerShell remoto. Como se explica anteriormente, se debe asignar los permisos adecuados para poder ejecutar correctamente esta secuencia de comandos.</span><span class="sxs-lookup"><span data-stu-id="a65e6-p110">**Your user credentials** - The script will use your credentials to connect to Exchange Online and the Security &amp; Compliance Center with remote PowerShell. As previously explained, you have to assigned the appropriate permissions to successfully run this script.</span></span>
    
<span data-ttu-id="a65e6-142">Para mostrar una lista de carpetas del buzón o los nombres de ruta de acceso del sitio:</span><span class="sxs-lookup"><span data-stu-id="a65e6-142">To display a list of mailbox folders or site path names:</span></span>
  
1. <span data-ttu-id="a65e6-143">Guarde el siguiente texto en un archivo de secuencia de comandos de Windows PowerShell mediante el uso de un sufijo de nombre de archivo de. ps1; Por ejemplo, `GetFolderSearchParameters.ps1`.</span><span class="sxs-lookup"><span data-stu-id="a65e6-143">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `GetFolderSearchParameters.ps1`.</span></span>
    
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
          # Create a Complinace Search Action and wait for it to complete. The folders will be listed in the .Results parameter
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

2. <span data-ttu-id="a65e6-144">En el equipo local, abra Windows PowerShell y vaya a la carpeta donde guardó la secuencia de comandos.</span><span class="sxs-lookup"><span data-stu-id="a65e6-144">On your local computer, open Windows PowerShell and go to the folder where you saved the script.</span></span>
    
3. <span data-ttu-id="a65e6-145">Ejecute la secuencia de comandos; Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="a65e6-145">Run the script; for example:</span></span>
    
      ```
      .\GetFolderSearchParameters.ps1
      ```

4. <span data-ttu-id="a65e6-146">Escriba la información que le pide la secuencia de comandos.</span><span class="sxs-lookup"><span data-stu-id="a65e6-146">Enter the information that the script prompts you for.</span></span>
    
    <span data-ttu-id="a65e6-p111">La secuencia de comandos muestra una lista de carpetas del buzón o carpeta del sitio para el usuario especificado. Permitir que esta ventana Abrir para que pueda copiar un nombre de identificador o ruta de acceso de carpeta y péguelo en una consulta de búsqueda en el paso 2.</span><span class="sxs-lookup"><span data-stu-id="a65e6-p111">The script displays a list of mailbox folders or site folder for the specified user. Let this window open so that you can copy a folder ID or path name and paste it in to a search query in Step 2.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="a65e6-p112">En lugar de mostrar una lista de carpetas en la pantalla del equipo, puede volver a dirigir la salida de la secuencia de comandos en un archivo de texto. Este archivo se guardará en la carpeta donde se encuentra la secuencia de comandos. Por ejemplo, para redirigir la secuencia de comandos de salida a un archivo de texto, ejecute el siguiente comando en el paso 3: `.\GetFolderSearchParameters.ps1 > StacigFolderIds.txt` , a continuación, puede copiar un identificador de la carpeta o la ruta de acceso de archivo que se utilizará en una consulta de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="a65e6-p112">Instead of displaying a list of folders on the computer screen, you can re-direct the output of the script to a text file. This file will be saved to the folder where the script is located. For example, to redirect the script output to a text file, run the following command in Step 3:  `.\GetFolderSearchParameters.ps1 > StacigFolderIds.txt` Then you can copy a folder ID or path from the file to use in a search query.</span></span>
  
### <a name="script-output-for-mailbox-folders"></a><span data-ttu-id="a65e6-152">Salida de secuencia de comandos para las carpetas de buzón de correo</span><span class="sxs-lookup"><span data-stu-id="a65e6-152">Script output for mailbox folders</span></span>

<span data-ttu-id="a65e6-p113">Si va a recibir los identificadores de carpeta de buzón, la secuencia de comandos se conecta a Exchange Online mediante PowerShell remoto, ejecuta el cmdlet **Get-MailboxFolderStatisics** y, a continuación, muestra la lista de las carpetas del buzón de correo especificado. Para cada carpeta en el buzón de correo, la secuencia de comandos muestra el nombre de la carpeta en la columna **FolderPath** y el identificador de la carpeta en la columna **FolderQuery** . Además, la secuencia de comandos agrega el prefijo de **folderId** (que es el nombre de la propiedad del buzón de correo) para el identificador de la carpeta. Dado que la propiedad **folderid** es una propiedad que admite búsqueda, debe usar `folderid:<folderid>` en una consulta de búsqueda en el paso 2 a esa carpeta de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="a65e6-p113">If you're getting mailbox folder IDs, the script connects to Exchange Online by using remote PowerShell, runs the **Get-MailboxFolderStatisics** cmdlet, and then displays the list of the folders from the specified mailbox. For every folder in the mailbox, the script displays the name of the folder in the **FolderPath** column and the folder ID in the **FolderQuery** column. Additionally, the script adds the prefix of **folderId** (which is the name of the mailbox property) to the folder ID. Because the **folderid** property is a searchable property, you'll use  `folderid:<folderid>` in a search query in Step 2 to search that folder.</span></span> 
  
<span data-ttu-id="a65e6-157">Este es un ejemplo del resultado devuelto por la secuencia de comandos para las carpetas de buzón de correo.</span><span class="sxs-lookup"><span data-stu-id="a65e6-157">Here's an example of the output returned by the script for mailbox folders.</span></span>
  
![Ejemplo de la lista de carpetas del buzón y carpeta identificadores devueltos por la secuencia de comandos](media/cd739207-eb84-4ebf-a03d-703f3d3a797d.png)
  
<span data-ttu-id="a65e6-159">El ejemplo en el paso 2 muestra la consulta utilizada para la subcarpeta de purga de búsqueda en la carpeta del usuario elementos recuperables.</span><span class="sxs-lookup"><span data-stu-id="a65e6-159">The example in Step 2 shows the query used to search the Purges subfolder in the user's Recoverable Items folder.</span></span>
  
### <a name="script-output-for-site-folders"></a><span data-ttu-id="a65e6-160">Salida de secuencia de comandos para las carpetas del sitio</span><span class="sxs-lookup"><span data-stu-id="a65e6-160">Script output for site folders</span></span>

<span data-ttu-id="a65e6-p114">Si va a recibir las rutas de acceso de SharePoint o OneDrive para los sitios de negocios, la secuencia de comandos se conecta a la seguridad &amp; centro de cumplimiento de normas mediante PowerShell remoto, se crea una nueva búsqueda de contenido que busca en el sitio para las carpetas y, a continuación, se muestra una lista de las carpetas que se encuentra en el sitio especificado. La secuencia de comandos muestra el nombre de cada carpeta y agrega el prefijo de la **ruta de acceso** (que es el nombre de la propiedad del sitio) a la dirección URL de la carpeta. Dado que la propiedad **ruta de acceso** es una propiedad que admite búsqueda, debe usar `path:<path>` en una consulta de búsqueda en el paso 2 a esa carpeta de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="a65e6-p114">If you're getting paths from SharePoint or OneDrive for Business sites, the script connects to the Security &amp; Compliance Center using remote PowerShell, creates a new Content Search that searches the site for folders, and then displays a list of the folders located in the specified site. The script displays the name of each folder and adds the prefix of **path** (which is the name of the site property) to the folder URL. Because the **path** property is a searchable property, you'll use  `path:<path>` in a search query in Step 2 to search that folder.</span></span> 
  
<span data-ttu-id="a65e6-164">Este es un ejemplo del resultado devuelto por la secuencia de comandos para las carpetas del sitio.</span><span class="sxs-lookup"><span data-stu-id="a65e6-164">Here's an example of the output returned by the script for site folders.</span></span>
  
![Ejemplo de la lista de nombres de ruta de acceso para las carpetas de sitio devueltos por la secuencia de comandos](media/519e8347-7365-4067-af78-96c465dc3d15.png)
  
## <a name="step-2-use-a-folder-id-or-path-to-perform-a-targeted-collection"></a><span data-ttu-id="a65e6-166">Paso 2: Usar un identificador de la carpeta o la ruta de acceso para llevar a cabo una colección de destino</span><span class="sxs-lookup"><span data-stu-id="a65e6-166">Step 2: Use a folder ID or path to perform a targeted collection</span></span>

<span data-ttu-id="a65e6-p115">Una vez ejecutado el script para recopilar una lista de identificadores de las carpetas o rutas de acceso para un usuario específico, el siguiente paso para ir a la seguridad &amp; centro de cumplimiento y crear una nueva búsqueda de contenido para buscar una carpeta específica. Usará el `folderid:<folderid>` o `path:<path>` (propiedad) en la consulta de búsqueda que configura en el cuadro de palabra clave de búsqueda de contenido (o como el valor para el parámetro *ContentMatchQuery* si usa el cmdlet **New-ComplianceSearch** ). Puede combinar el `folderid` o `path` propiedad con otros parámetros de búsqueda o las condiciones de búsqueda. Si sólo se incluye el `folderid` o `path` en la consulta, la búsqueda devolverá todos los elementos que se encuentra en la carpeta especificada.</span><span class="sxs-lookup"><span data-stu-id="a65e6-p115">After you've run the script to collect a list of folder IDs or paths for a specific user, the next step to go to the Security &amp; Compliance Center and create a new Content Search to search a specific folder. You'll use the  `folderid:<folderid>` or  `path:<path>` property in the search query that you configure in the Content Search keyword box (or as the value for the  *ContentMatchQuery*  parameter if you use the **New-ComplianceSearch** cmdlet). You can combine the  `folderid` or  `path` property with other search parameters or search conditions. If you only include the  `folderid` or  `path` property in the query, the search will return all items located in the specified folder.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="a65e6-171">Uso de la `path` propiedad a OneDrive ubicaciones de búsqueda no devolverá los archivos multimedia, como archivos .png, .tiff o .wav, en los resultados de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="a65e6-171">Using the  `path` property to search OneDrive locations won't return media files, such as .png, .tiff, or .wav files, in the search results.</span></span> 
  
1. <span data-ttu-id="a65e6-172">Vaya a [https://protection.office.com](https://protection.office.com).</span><span class="sxs-lookup"><span data-stu-id="a65e6-172">Go to [https://protection.office.com](https://protection.office.com).</span></span>
    
2. <span data-ttu-id="a65e6-173">Inicie sesión en Office 365 con la cuenta y las credenciales que usan para ejecutar la secuencia de comandos en el paso 1.</span><span class="sxs-lookup"><span data-stu-id="a65e6-173">Sign in to Office 365 using the account and credentials that you used to run the script in Step 1.</span></span>
    
3. <span data-ttu-id="a65e6-174">En el panel izquierdo de la seguridad &amp; centro de cumplimiento, haga clic en **búsqueda &amp; investigación** \> de **búsqueda de contenido**y, a continuación, haga clic en **nuevo** ![icono Agregar](media/O365-MDM-CreatePolicy-AddIcon.gif).</span><span class="sxs-lookup"><span data-stu-id="a65e6-174">In the left pane of the Security &amp; Compliance Center, click **Search &amp; investigation** \> **Content search**, and then click **New** ![Add icon](media/O365-MDM-CreatePolicy-AddIcon.gif).</span></span>
    
4. <span data-ttu-id="a65e6-p116">En la página **Búsqueda nueva**, escriba un nombre para la búsqueda de contenido. Este nombre debe ser único en la organización.</span><span class="sxs-lookup"><span data-stu-id="a65e6-p116">On the **New search** page, type a name for the Content Search. This name has to be unique in your organization.</span></span> 
    
5. <span data-ttu-id="a65e6-177">En **¿dónde desea que nos buscar**, siga uno de los siguientes valores, en función de si la búsqueda de una carpeta de buzón de correo o una carpeta del sitio:</span><span class="sxs-lookup"><span data-stu-id="a65e6-177">Under **Where do you want us to look**, do one of the following, based on whether your searching a mailbox folder or a site folder:</span></span>
    
    - <span data-ttu-id="a65e6-178">Haga clic en **elegir buzones específicos para buscar** y, a continuación, agregue el mismo buzón que especificó cuando ejecutó la secuencia de comandos en el paso 1.</span><span class="sxs-lookup"><span data-stu-id="a65e6-178">Click **Choose specific mailboxes to search** and then add the same mailbox that you specified when you ran the script in Step 1.</span></span> 
    
      <span data-ttu-id="a65e6-179">O bien</span><span class="sxs-lookup"><span data-stu-id="a65e6-179">Or</span></span>
    
    - <span data-ttu-id="a65e6-180">Haga clic en **Elegir sitios específicos para buscar** para buscar y, a continuación, agregar la misma dirección URL del sitio que especificó cuando ejecutó la secuencia de comandos en el paso 1.</span><span class="sxs-lookup"><span data-stu-id="a65e6-180">Click **Choose specific sites to search** to search and then add the same site URL that you specified when you ran the script in Step 1.</span></span> 
    
6. <span data-ttu-id="a65e6-181">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="a65e6-181">Click **Next**.</span></span>
    
7. <span data-ttu-id="a65e6-182">En el cuadro de palabra clave en la página **¿Qué desea nos para buscar** , pegue la `folderid:<folderid>` o `path:<path>` valor devuelto por la secuencia de comandos en el paso 1.</span><span class="sxs-lookup"><span data-stu-id="a65e6-182">In the keyword box on the **What do you want us to look for** page, paste the  `folderid:<folderid>` or  `path:<path>` value that was returned by the script in Step 1.</span></span> 
    
    <span data-ttu-id="a65e6-183">Por ejemplo, se busca la consulta en la siguiente captura de pantalla de cualquier elemento en la subcarpeta de purga de la carpeta del usuario elementos recuperables (el valor de la `folderid` (propiedad) para la subcarpeta de purga se muestra en la captura de pantalla en el paso 1):</span><span class="sxs-lookup"><span data-stu-id="a65e6-183">For example, the query in the following screenshot will search for any item in the Purges subfolder in the user's Recoverable Items folder (the value of the `folderid` property for the Purges subfolder is shown in the screenshot in Step 1):</span></span>
    
    ![Pegue el folderid o la ruta de acceso en el cuadro de palabra clave de la consulta de búsqueda](media/84057516-b663-48a4-a78f-8032a8f8da80.png)
  
8. <span data-ttu-id="a65e6-185">Haga clic en **Buscar** para iniciar la búsqueda de la colección de destino.</span><span class="sxs-lookup"><span data-stu-id="a65e6-185">Click **Search** to start the targeted collection search.</span></span> 
  
### <a name="examples-of-search-queries-for-targeted-collections"></a><span data-ttu-id="a65e6-186">Ejemplos de consultas de búsqueda para las colecciones de destinadas</span><span class="sxs-lookup"><span data-stu-id="a65e6-186">Examples of search queries for targeted collections</span></span>

<span data-ttu-id="a65e6-p117">Estos son algunos ejemplos del uso de la `folderid` y `path` las propiedades de una consulta de búsqueda para llevar a cabo una colección de destino. Tenga en cuenta que se usan los marcadores de posición para `folderid:<folderid>` y `path:<path>` para ahorrar espacio.</span><span class="sxs-lookup"><span data-stu-id="a65e6-p117">Here are some examples of using the  `folderid` and  `path` properties in a search query to perform a targeted collection. Note that placeholders are used for  `folderid:<folderid>` and  `path:<path>` to save space.</span></span> 
  
- <span data-ttu-id="a65e6-p118">En este ejemplo se buscan en tres carpetas de buzón de correo diferente. Puede usar la sintaxis de consulta similar para buscar las carpetas ocultas en la carpeta elementos recuperables de un usuario.</span><span class="sxs-lookup"><span data-stu-id="a65e6-p118">This example searches three different mailbox folders. You could use similar query syntax to search the hidden folders in a user's Recoverable Items folder.</span></span>
    
  ```
  folderid:<folderid> OR folderid:<folderid> OR folderid:<folderid>
  ```

- <span data-ttu-id="a65e6-191">En este ejemplo se busca una carpeta de buzón de correo para los elementos que contienen una frase exacta.</span><span class="sxs-lookup"><span data-stu-id="a65e6-191">This example searches a mailbox folder for items that contain an exact phrase.</span></span>
    
  ```
  folderid:<folderid> AND "Contoso financial results"
  ```

- <span data-ttu-id="a65e6-192">En este ejemplo se buscan una carpeta del sitio (y todas las subcarpetas) para los documentos que contienen las letras "Acuerdo de confidencialidad" en el título.</span><span class="sxs-lookup"><span data-stu-id="a65e6-192">This example searches a site folder (and any subfolders) for documents that contain the letters "NDA" in the title.</span></span>
    
  ```
  path:<path> AND filename:nda
  ```

- <span data-ttu-id="a65e6-193">En este ejemplo se buscan una carpeta del sitio (y cualquier subcarpeta) para documentos que se han cambiado dentro de un intervalo de fechas.</span><span class="sxs-lookup"><span data-stu-id="a65e6-193">This example searches a site folder (and any subfolder) for documents there were changed within a date range.</span></span>
    
  ```
  path:<path> AND (lastmodifiedtime>=01/01/2017 AND lastmodifiedtime<=01/21/2017)
  ```
  
## <a name="more-information"></a><span data-ttu-id="a65e6-194">Más información</span><span class="sxs-lookup"><span data-stu-id="a65e6-194">More information</span></span>

<span data-ttu-id="a65e6-195">Tenga en cuenta lo siguiente cuando se usa la secuencia de comandos en este artículo y realiza dirigido colecciones.</span><span class="sxs-lookup"><span data-stu-id="a65e6-195">Keep the following things in mind when using the script in this article and performing targeted collections.</span></span>
  
- <span data-ttu-id="a65e6-p119">La secuencia de comandos no quita todas las carpetas de los resultados. Por lo que algunas carpetas que aparecen en los resultados podrían ser buscar (o devolver elementos de cero), porque contienen contenido generado por el sistema.</span><span class="sxs-lookup"><span data-stu-id="a65e6-p119">The script doesn't remove any folders from the results. So some folders listed in the results might be unsearchable (or return zero items) because they contain system-generated content.</span></span>
    
- <span data-ttu-id="a65e6-p120">Esta secuencia de comandos sólo devuelve información de la carpeta de buzón principal del usuario. No devuelve información sobre las carpetas de buzón de archivo del usuario.</span><span class="sxs-lookup"><span data-stu-id="a65e6-p120">This script only returns folder information for the user's primary mailbox. It doesn't return information about folders in the user's archive mailbox.</span></span>
    
- <span data-ttu-id="a65e6-p121">Al buscar en las carpetas de buzón de correo, sólo la carpeta especificada (identificado por su `folderid` (propiedad)) se buscará. No se busca en las subcarpetas. Para buscar las subcarpetas, tiene que usar el `folderid` para la subcarpeta que desea buscar.</span><span class="sxs-lookup"><span data-stu-id="a65e6-p121">When searching mailbox folders, only the specified folder (identified by its  `folderid` property) will be searched. Subfolders won't be searched. To search sub-folders, you need to use the  `folderid` for the sub-folder that you want to search.</span></span> 
    
- <span data-ttu-id="a65e6-203">Al buscar en carpetas del sitio, la carpeta (identificado por su `path` (propiedad)) y se buscará en todas las subcarpetas.</span><span class="sxs-lookup"><span data-stu-id="a65e6-203">When searching site folders, the folder (identified by its  `path` property) and all sub-folders will be searched.</span></span> 
    
- <span data-ttu-id="a65e6-p122">Como se señaló anteriormente, no se puede usar `path` (propiedad) para buscar archivos multimedia, por ejemplo, .png, .tiff y los archivos .wav, que se encuentra en las ubicaciones de OneDrive. Use una [propiedad del sitio](keyword-queries-and-search-conditions.md#searchable-site-properties) de diferentes para buscar archivos multimedia en las carpetas de OneDrive.</span><span class="sxs-lookup"><span data-stu-id="a65e6-p122">As previously stated, you can't use  `path` property to search for media files, such as .png, .tiff, or .wav files, located in OneDrive locations. Use a different [site property](keyword-queries-and-search-conditions.md#searchable-site-properties) to search for media files in OneDrive folders.</span></span> 
