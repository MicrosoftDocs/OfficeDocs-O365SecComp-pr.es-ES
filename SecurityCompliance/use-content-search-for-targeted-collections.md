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
# <a name="use-content-search-in-office-365-for-targeted-collections"></a>Usar búsqueda de contenido en Office 365 para las colecciones de destinadas

La característica de búsqueda de contenido de la seguridad de Office 365 &amp; centro de cumplimiento no proporciona una forma directa en la interfaz de usuario para buscar carpetas específicas en los buzones de Exchange o SharePoint y OneDrive sitios profesionales. Sin embargo, es posible buscar carpetas específicas (denominadas una colección de destino) especificando el identificador de la carpeta o la ruta de acceso en la sintaxis de consulta de búsqueda reales. Uso de búsqueda de contenido para llevar a cabo una colección de destino es útil cuando esté seguro de que los elementos con capacidad de respuesta a un caso de o elementos con privilegios se encuentran en una carpeta de buzón de correo o de sitio específica. Puede usar la secuencia de comandos en este artículo para obtener el identificador de carpeta para carpetas del buzón o la ruta de acceso para las carpetas en un SharePoint y OneDrive para el sitio de negocio. A continuación, puede usar el identificador de la carpeta o la ruta de acceso en una consulta de búsqueda para devolver los elementos que se encuentran en la carpeta.
  
## <a name="before-you-begin"></a>Antes de empezar

- Tiene que ser un miembro del grupo de roles de administrador de exhibición de documentos electrónicos en la seguridad &amp; centro de cumplimiento para ejecutar el script en el paso 1. Para obtener más información, vea [asignar permisos de exhibición de documentos electrónicos en la seguridad de Office 365 &amp; centro de cumplimiento](assign-ediscovery-permissions.md).
    
    Además, debe tener asignado el rol de destinatarios de correo en la organización de Exchange Online. Este proceso es necesario para ejecutar el cmdlet **Get-MailboxFolderStatistics** , que se incluye en la secuencia de comandos en el paso 1. De forma predeterminada, el rol de destinatarios de correo se asigna a los grupos de funciones de administración de la organización y administración de destinatarios en Exchange Online. Para obtener más información acerca de cómo asignar permisos en Exchange Online, consulte [Manage role group members](https://go.microsoft.com/fwlink/p/?linkid=692102). Podría crear también un grupo de roles personalizados, asignar el rol de destinatarios de correo a ella y, a continuación, agregar a los miembros que necesitan para ejecutar el script en el paso 1. Para obtener más información, vea [Administrar grupos de roles](https://go.microsoft.com/fwlink/p/?linkid=730688).
    
- Cada vez que se ejecuta la secuencia de comandos en el paso 1, se crea una nueva sesión de PowerShell remota. Así se puede usar seguridad de todas las PowerShell sesiones remotas disponibles para usted. Para evitar que esto ocurra, puede ejecutar el siguiente comando para desconectar las sesiones de PowerShell remotas activas.
    
  ```
  Get-PSSession | Remove-PSSession
  ```

    Para obtener más información, vea [Conexión a Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).
    
- La secuencia de comandos incluye el tratamiento de errores mínima. El propósito principal de la secuencia de comandos es mostrar una lista de identificadores de carpeta de buzón o rutas de acceso que pueden usarse para llevar a cabo una colección de destino en la sintaxis de consulta de búsqueda de una búsqueda de contenido de sitio rápidamente.
    
- El script de ejemplo proporcionado en este tema no es compatible con ningún servicio o programa de soporte estándar de Microsoft. El script de ejemplo se proporciona tal cual sin garantía de ningún tipo. Microsoft renuncia a todas las garantías implícitas incluidas, sin limitación, cualquier las garantías implícitas de comerciabilidad o de idoneidad para un fin determinado. Todo el riesgo que pueda surgir por el uso o el rendimiento de la secuencia de comandos de ejemplo y documentación permanece con usted. En ningún caso Microsoft, sus autores o cualquier otro implicado en la creación, producción o entrega de las secuencias de comandos serán responsables de los daños índole (incluidos, pero sin limitarse a, daños por pérdida de beneficios empresariales, interrupción del negocio, pérdida de información de la empresa, o en otras pérdidas de carácter económico) derivado del uso o la incapacidad de usar los scripts de ejemplo o documentación, aunque Microsoft haya sido notificado de la posibilidad de dichos daños.
  
## <a name="step-1-run-the-script-to-get-a-list-of-folders-for-a-mailbox-or-site"></a>Paso 1: Ejecutar el script para obtener una lista de carpetas de un buzón de correo o sitio

La secuencia de comandos que se ejecuta en este primer paso devolverá una lista de carpetas del buzón o SharePoint o OneDrive para las carpetas de negocio y el identificador correspondiente de carpeta o ruta de acceso para cada carpeta. Al ejecutar este script, le pedirá la siguiente información.
  
- **Dirección URL de sitio o dirección de correo electrónico** Escriba una dirección de correo electrónico de la custodia para devolver una lista de carpetas de buzón de correo de Exchange y los identificadores de doblado. O bien, escriba la dirección URL de un sitio de SharePoint o un OneDrive para el sitio de negocio para devolver una lista de rutas de acceso para el sitio especificado. Estos son algunos ejemplos: 
    
  - **Exchange** - stacig@contoso.onmicrosoft.com 
    
  - **SharePoint** - https://contoso.sharepoint.com/sites/marketing 
    
  - **OneDrive para la empresa** - https://contoso-my.sharepoint.com/personal/stacig_contoso_onmicrosoft_com 
    
- **Sus credenciales de usuario** : la secuencia de comandos usará las credenciales para conectarse a Exchange Online y la seguridad &amp; centro de cumplimiento con PowerShell remoto. Como se explica anteriormente, se debe asignar los permisos adecuados para poder ejecutar correctamente esta secuencia de comandos.
    
Para mostrar una lista de carpetas del buzón o los nombres de ruta de acceso del sitio:
  
1. Guarde el siguiente texto en un archivo de secuencia de comandos de Windows PowerShell mediante el uso de un sufijo de nombre de archivo de. ps1; Por ejemplo, `GetFolderSearchParameters.ps1`.
    
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

2. En el equipo local, abra Windows PowerShell y vaya a la carpeta donde guardó la secuencia de comandos.
    
3. Ejecute la secuencia de comandos; Por ejemplo:
    
      ```
      .\GetFolderSearchParameters.ps1
      ```

4. Escriba la información que le pide la secuencia de comandos.
    
    La secuencia de comandos muestra una lista de carpetas del buzón o carpeta del sitio para el usuario especificado. Permitir que esta ventana Abrir para que pueda copiar un nombre de identificador o ruta de acceso de carpeta y péguelo en una consulta de búsqueda en el paso 2.
    
    > [!TIP]
    > En lugar de mostrar una lista de carpetas en la pantalla del equipo, puede volver a dirigir la salida de la secuencia de comandos en un archivo de texto. Este archivo se guardará en la carpeta donde se encuentra la secuencia de comandos. Por ejemplo, para redirigir la secuencia de comandos de salida a un archivo de texto, ejecute el siguiente comando en el paso 3: `.\GetFolderSearchParameters.ps1 > StacigFolderIds.txt` , a continuación, puede copiar un identificador de la carpeta o la ruta de acceso de archivo que se utilizará en una consulta de búsqueda.
  
### <a name="script-output-for-mailbox-folders"></a>Salida de secuencia de comandos para las carpetas de buzón de correo

Si va a recibir los identificadores de carpeta de buzón, la secuencia de comandos se conecta a Exchange Online mediante PowerShell remoto, ejecuta el cmdlet **Get-MailboxFolderStatisics** y, a continuación, muestra la lista de las carpetas del buzón de correo especificado. Para cada carpeta en el buzón de correo, la secuencia de comandos muestra el nombre de la carpeta en la columna **FolderPath** y el identificador de la carpeta en la columna **FolderQuery** . Además, la secuencia de comandos agrega el prefijo de **folderId** (que es el nombre de la propiedad del buzón de correo) para el identificador de la carpeta. Dado que la propiedad **folderid** es una propiedad que admite búsqueda, debe usar `folderid:<folderid>` en una consulta de búsqueda en el paso 2 a esa carpeta de búsqueda. 
  
Este es un ejemplo del resultado devuelto por la secuencia de comandos para las carpetas de buzón de correo.
  
![Ejemplo de la lista de carpetas del buzón y carpeta identificadores devueltos por la secuencia de comandos](media/cd739207-eb84-4ebf-a03d-703f3d3a797d.png)
  
El ejemplo en el paso 2 muestra la consulta utilizada para la subcarpeta de purga de búsqueda en la carpeta del usuario elementos recuperables.
  
### <a name="script-output-for-site-folders"></a>Salida de secuencia de comandos para las carpetas del sitio

Si va a recibir las rutas de acceso de SharePoint o OneDrive para los sitios de negocios, la secuencia de comandos se conecta a la seguridad &amp; centro de cumplimiento de normas mediante PowerShell remoto, se crea una nueva búsqueda de contenido que busca en el sitio para las carpetas y, a continuación, se muestra una lista de las carpetas que se encuentra en el sitio especificado. La secuencia de comandos muestra el nombre de cada carpeta y agrega el prefijo de la **ruta de acceso** (que es el nombre de la propiedad del sitio) a la dirección URL de la carpeta. Dado que la propiedad **ruta de acceso** es una propiedad que admite búsqueda, debe usar `path:<path>` en una consulta de búsqueda en el paso 2 a esa carpeta de búsqueda. 
  
Este es un ejemplo del resultado devuelto por la secuencia de comandos para las carpetas del sitio.
  
![Ejemplo de la lista de nombres de ruta de acceso para las carpetas de sitio devueltos por la secuencia de comandos](media/519e8347-7365-4067-af78-96c465dc3d15.png)
  
## <a name="step-2-use-a-folder-id-or-path-to-perform-a-targeted-collection"></a>Paso 2: Usar un identificador de la carpeta o la ruta de acceso para llevar a cabo una colección de destino

Una vez ejecutado el script para recopilar una lista de identificadores de las carpetas o rutas de acceso para un usuario específico, el siguiente paso para ir a la seguridad &amp; centro de cumplimiento y crear una nueva búsqueda de contenido para buscar una carpeta específica. Usará el `folderid:<folderid>` o `path:<path>` (propiedad) en la consulta de búsqueda que configura en el cuadro de palabra clave de búsqueda de contenido (o como el valor para el parámetro *ContentMatchQuery* si usa el cmdlet **New-ComplianceSearch** ). Puede combinar el `folderid` o `path` propiedad con otros parámetros de búsqueda o las condiciones de búsqueda. Si sólo se incluye el `folderid` o `path` en la consulta, la búsqueda devolverá todos los elementos que se encuentra en la carpeta especificada. 
  
> [!NOTE]
> Uso de la `path` propiedad a OneDrive ubicaciones de búsqueda no devolverá los archivos multimedia, como archivos .png, .tiff o .wav, en los resultados de búsqueda. 
  
1. Vaya a [https://protection.office.com](https://protection.office.com).
    
2. Inicie sesión en Office 365 con la cuenta y las credenciales que usan para ejecutar la secuencia de comandos en el paso 1.
    
3. En el panel izquierdo de la seguridad &amp; centro de cumplimiento, haga clic en **búsqueda &amp; investigación** \> de **búsqueda de contenido**y, a continuación, haga clic en **nuevo** ![icono Agregar](media/O365-MDM-CreatePolicy-AddIcon.gif).
    
4. En la página **Búsqueda nueva**, escriba un nombre para la búsqueda de contenido. Este nombre debe ser único en la organización. 
    
5. En **¿dónde desea que nos buscar**, siga uno de los siguientes valores, en función de si la búsqueda de una carpeta de buzón de correo o una carpeta del sitio:
    
    - Haga clic en **elegir buzones específicos para buscar** y, a continuación, agregue el mismo buzón que especificó cuando ejecutó la secuencia de comandos en el paso 1. 
    
      O bien
    
    - Haga clic en **Elegir sitios específicos para buscar** para buscar y, a continuación, agregar la misma dirección URL del sitio que especificó cuando ejecutó la secuencia de comandos en el paso 1. 
    
6. Haga clic en **Siguiente**.
    
7. En el cuadro de palabra clave en la página **¿Qué desea nos para buscar** , pegue la `folderid:<folderid>` o `path:<path>` valor devuelto por la secuencia de comandos en el paso 1. 
    
    Por ejemplo, se busca la consulta en la siguiente captura de pantalla de cualquier elemento en la subcarpeta de purga de la carpeta del usuario elementos recuperables (el valor de la `folderid` (propiedad) para la subcarpeta de purga se muestra en la captura de pantalla en el paso 1):
    
    ![Pegue el folderid o la ruta de acceso en el cuadro de palabra clave de la consulta de búsqueda](media/84057516-b663-48a4-a78f-8032a8f8da80.png)
  
8. Haga clic en **Buscar** para iniciar la búsqueda de la colección de destino. 
  
### <a name="examples-of-search-queries-for-targeted-collections"></a>Ejemplos de consultas de búsqueda para las colecciones de destinadas

Estos son algunos ejemplos del uso de la `folderid` y `path` las propiedades de una consulta de búsqueda para llevar a cabo una colección de destino. Tenga en cuenta que se usan los marcadores de posición para `folderid:<folderid>` y `path:<path>` para ahorrar espacio. 
  
- En este ejemplo se buscan en tres carpetas de buzón de correo diferente. Puede usar la sintaxis de consulta similar para buscar las carpetas ocultas en la carpeta elementos recuperables de un usuario.
    
  ```
  folderid:<folderid> OR folderid:<folderid> OR folderid:<folderid>
  ```

- En este ejemplo se busca una carpeta de buzón de correo para los elementos que contienen una frase exacta.
    
  ```
  folderid:<folderid> AND "Contoso financial results"
  ```

- En este ejemplo se buscan una carpeta del sitio (y todas las subcarpetas) para los documentos que contienen las letras "Acuerdo de confidencialidad" en el título.
    
  ```
  path:<path> AND filename:nda
  ```

- En este ejemplo se buscan una carpeta del sitio (y cualquier subcarpeta) para documentos que se han cambiado dentro de un intervalo de fechas.
    
  ```
  path:<path> AND (lastmodifiedtime>=01/01/2017 AND lastmodifiedtime<=01/21/2017)
  ```
  
## <a name="more-information"></a>Más información

Tenga en cuenta lo siguiente cuando se usa la secuencia de comandos en este artículo y realiza dirigido colecciones.
  
- La secuencia de comandos no quita todas las carpetas de los resultados. Por lo que algunas carpetas que aparecen en los resultados podrían ser buscar (o devolver elementos de cero), porque contienen contenido generado por el sistema.
    
- Esta secuencia de comandos sólo devuelve información de la carpeta de buzón principal del usuario. No devuelve información sobre las carpetas de buzón de archivo del usuario.
    
- Al buscar en las carpetas de buzón de correo, sólo la carpeta especificada (identificado por su `folderid` (propiedad)) se buscará. No se busca en las subcarpetas. Para buscar las subcarpetas, tiene que usar el `folderid` para la subcarpeta que desea buscar. 
    
- Al buscar en carpetas del sitio, la carpeta (identificado por su `path` (propiedad)) y se buscará en todas las subcarpetas. 
    
- Como se señaló anteriormente, no se puede usar `path` (propiedad) para buscar archivos multimedia, por ejemplo, .png, .tiff y los archivos .wav, que se encuentra en las ubicaciones de OneDrive. Use una [propiedad del sitio](keyword-queries-and-search-conditions.md#searchable-site-properties) de diferentes para buscar archivos multimedia en las carpetas de OneDrive. 
