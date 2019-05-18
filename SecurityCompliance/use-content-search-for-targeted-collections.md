---
title: Usar la búsqueda de contenido en Office 365 para colecciones dirigidas
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
search.appverid: MOE150
ms.assetid: e3cbc79c-5e97-43d3-8371-9fbc398cd92e
description: Use la búsqueda de contenido en el centro de seguridad & cumplimiento para realizar colecciones de destino. Una colección de destino significa que tiene la certeza de que los elementos que responden a un caso o los elementos con privilegios están ubicados en un buzón o carpeta de sitio específicos. Use el script de este artículo para obtener el identificador de carpeta o la ruta de acceso de las carpetas de sitio o de buzón de correo específicas que desea buscar.
ms.openlocfilehash: 476478f3f4d5c2d1992989eac790068f28ba747f
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/17/2019
ms.locfileid: "34156312"
---
# <a name="use-content-search-in-office-365-for-targeted-collections"></a>Usar la búsqueda de contenido en Office 365 para colecciones dirigidas

La característica de búsqueda de contenido en el centro &amp; de seguridad y cumplimiento de Office 365 no ofrece una forma directa en la interfaz de usuario para buscar en carpetas específicas de los buzones de Exchange o de los sitios de SharePoint y OneDrive para la empresa. Sin embargo, es posible buscar carpetas específicas (denominadas *colección de destino*) especificando la propiedad ID de la carpeta para la propiedad email o path (DocumentLink) de los sitios de la sintaxis de la consulta de búsqueda real. Usar la búsqueda de contenido para realizar una colección de destino es útil cuando tiene la certeza de que los elementos que responden a un caso o los elementos con privilegios están ubicados en un buzón o carpeta de sitio específicos. Puede usar el script de este artículo para obtener el identificador de carpeta para las carpetas de buzón o la ruta de acceso (DocumentLink) para las carpetas de un sitio de SharePoint y OneDrive para la empresa. A continuación, puede usar el identificador de carpeta o la ruta de acceso en una consulta de búsqueda para devolver los elementos que se encuentran en la carpeta.

> [!NOTE]
> Para devolver contenido que se encuentra en una carpeta de un sitio de SharePoint o de OneDrive para la empresa, el script de este tema usa la propiedad administrada DocumentLink en lugar de la propiedad path. La propiedad DocumentLink es más robusta que la propiedad path porque devolverá todo el contenido de una carpeta, mientras que la propiedad path no devolverá algunos archivos multimedia.

## <a name="before-you-begin"></a>Antes de empezar

- Debe ser miembro del grupo de roles eDiscovery Manager en el centro de seguridad &amp; y cumplimiento para ejecutar el script en el paso 1. Para obtener más información, consulte [asignar permisos de exhibición](assign-ediscovery-permissions.md)de documentos electrónicos.
    
    Además, debe tener asignado el rol destinatarios de correo en su organización de Exchange Online. Esto es necesario para ejecutar el cmdlet **Get-MailboxFolderStatistics** , que se incluye en el script en el paso 1. De forma predeterminada, la función destinatarios de correo se asigna a los grupos de funciones administración de la organización y administración de destinatarios en Exchange Online. Para obtener más información acerca de la asignación de permisos en Exchange Online, consulte [Manage role Group Members](https://go.microsoft.com/fwlink/p/?linkid=692102). También puede crear un grupo de funciones personalizado, asignarle el rol destinatarios de correo y, a continuación, agregar los miembros que necesitan ejecutar el script en el paso 1. Para obtener más información, consulte [Administrar grupos de roles](https://go.microsoft.com/fwlink/p/?linkid=730688).
    
- Cada vez que ejecute el script en el paso 1, se creará una nueva sesión de PowerShell remoto. Por lo tanto, puede usar todas las sesiones de PowerShell remoto disponibles. Para evitar que esto suceda, puede ejecutar el siguiente comando para desconectar las sesiones remotas de PowerShell activas.
    
  ```
  Get-PSSession | Remove-PSSession
  ```

    Para obtener más información, vea [Conexión a Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).
    
- El script incluye un tratamiento de errores mínimo. El objetivo principal de la secuencia de comandos es mostrar rápidamente una lista de identificadores de carpetas de buzones o rutas de sitios que se pueden usar en la sintaxis de la consulta de búsqueda de una búsqueda de contenido para realizar una colección de destino.
    
- La secuencia de comandos de ejemplo proporcionada en este tema no es compatible con ningún servicio o programa de soporte estándar de Microsoft. El script de ejemplo se proporciona tal cual sin garantías de ningún tipo. Además, Microsoft no se hace responsable de cualquier garantía implícita, incluyendo, de manera enunciativa pero no limitativa, cualquier garantía implícita de comercialización o de calidad para cualquier propósito. Todo el riesgo derivado del uso o el rendimiento de la secuencia de comandos de muestra y la documentación se conservan con usted. En ningún caso Microsoft, sus autores o cualquier persona involucrada en su creación, producción o entrega de los scripts será responsable de cualquier daño (incluidos, de manera enunciativa pero no limitativa, daños por pérdidas de beneficios de una empresa, interrupción de la actividad de una empresa, pérdidas de información de una empresa, o cualquier otro daño pecuniario), incluso si Microsoft supiera de la posibilidad de tales daños.
  
## <a name="step-1-run-the-script-to-get-a-list-of-folders-for-a-mailbox-or-site"></a>Paso 1: ejecutar el script para obtener una lista de las carpetas de un buzón de correo o sitio

El script que se ejecuta en el primer paso devolverá una lista de carpetas de buzones o de carpetas de SharePoint y OneDrive para la empresa, así como el identificador de carpeta o la ruta de acceso correspondientes para cada carpeta. Al ejecutar este script, se le pedirá la siguiente información.
  
- **Dirección de correo electrónico o dirección URL del sitio** Escriba una dirección de correo electrónico del custodio para obtener una lista de los identificadores de carpetas y carpetas de buzones de Exchange. O bien, escriba la dirección URL de un sitio de SharePoint o un sitio de OneDrive para la empresa para devolver una lista de rutas de la ubicación del sitio especificado. Aquí le mostramos otros ejemplos: 
    
  - **Exchange** -stacig@contoso.onmicrosoft.com 
    
  - **SharePoint** - https://contoso.sharepoint.com/sites/marketing 
    
  - **OneDrive para la empresa** - https://contoso-my.sharepoint.com/personal/stacig_contoso_onmicrosoft_com 
    
- **Sus credenciales de usuario** : el script usará sus credenciales para conectarse a Exchange Online y el centro de seguridad & cumplimiento con PowerShell remoto. Como se ha explicado anteriormente, tiene que asignar los permisos adecuados para que este script se ejecute correctamente.
    
Para mostrar una lista de las carpetas del buzón o los nombres de documentlink (ruta de acceso) del sitio:
  
1. Guarde el siguiente texto en un archivo de script de Windows PowerShell mediante un sufijo de nombre de archivo de. ps1; por ejemplo, `GetFolderSearchParameters.ps1`.
    
  ```
  #########################################################################################################
  # This PowerShell script will prompt you for:                             #
  #    * Admin credentials for a user who can run the Get-MailboxFolderStatistics cmdlet in Exchange    #
  #      Online and who is an eDiscovery Manager in the Security & Compliance Center.           #
  # The script will then:                                           #
  #    * If an email address is supplied: list the folders for the target mailbox.          #
  #    * If a SharePoint or OneDrive for Business site is supplied: list the documentlinks (folder paths) #
  #    * for the site.                                                                                  #
  #    * In both cases, the script supplies the correct search properties (folderid: or documentlink:)  #
  #      appended to the folder ID or documentlink to use in a Content Search.              #
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
  # Authenticate with Exchange Online and the Security & Compliance Center (Exchange Online Protection - EOP)
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
      # Authenticate with the Security & Compliance Center
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
              Write-Host "DocumentLink:""$rawUrl"""
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

2. En el equipo local, abra Windows PowerShell y vaya a la carpeta donde guardó el script.
    
3. Ejecutar el script; por ejemplo:
    
      ```
      .\GetFolderSearchParameters.ps1
      ```

4. Escriba la información que el script le pide.
    
    El script muestra una lista de carpetas de buzón de correo o carpetas del sitio para el usuario especificado. Deje esta ventana abierta para que pueda copiar un identificador de carpeta o un nombre de documentlink y pegarlo en una consulta de búsqueda en el paso 2.
    
    > [!TIP]
    > En lugar de mostrar una lista de carpetas en la pantalla del equipo, puede redirigir el resultado del script a un archivo de texto. Este archivo se guardará en la carpeta en la que se encuentra el script. Por ejemplo, para redirigir la salida del script a un archivo de texto, ejecute el siguiente comando en el `.\GetFolderSearchParameters.ps1 > StacigFolderIds.txt` paso 3: a continuación, puede copiar un identificador de carpeta o documentlink del archivo para usarlo en una consulta de búsqueda.
  
### <a name="script-output-for-mailbox-folders"></a>Salida de script para carpetas de buzón

Si está obteniendo identificadores de carpeta de buzón de correo, el script se conecta a Exchange online mediante PowerShell remoto, ejecuta el cmdlet **Get-MailboxFolderStatisics** y, a continuación, muestra la lista de las carpetas del buzón especificado. Para cada carpeta del buzón, el script muestra el nombre de la carpeta en la columna **folderPath** y el identificador de la carpeta en la columna **FolderQuery** . Además, el script agrega el prefijo de **folderId** (que es el nombre de la propiedad Mailbox) al identificador de la carpeta. Dado que la propiedad **folderId** es una propiedad que se puede buscar, `folderid:<folderid>` usará en una consulta de búsqueda en el paso 2 para buscar en esa carpeta. 

> [!IMPORTANT]
> El script de este artículo incluye la lógica de codificación que convierte los valores de identificador de carpeta de 64 caracteres devueltos por **Get-MailboxFolderStatistics** en el mismo formato de 48 caracteres que se indexa para la búsqueda. Si solo ejecuta el cmdlet **Get-MailboxFolderStatistics** en PowerShell para obtener un identificador de carpeta (en lugar de ejecutar el script de este artículo), se producirá un error en una consulta de búsqueda que use ese valor de ID de carpeta. Tiene que ejecutar el script para obtener los identificadores de carpeta con formato correcto que se pueden usar en una búsqueda de contenido.
  
A continuación, se muestra un ejemplo del resultado devuelto por el script para las carpetas de buzón de correo.
  
![Ejemplo de la lista de carpetas de buzones y de identificadores de carpetas devueltos por el script](media/cd739207-eb84-4ebf-a03d-703f3d3a797d.png)
  
El ejemplo del paso 2 muestra la consulta utilizada para buscar en la subcarpeta Purges de la carpeta elementos recuperables del usuario.
  
### <a name="script-output-for-site-folders"></a>Salida de script para carpetas de sitio

Si va a obtener la ruta de acceso de la propiedad **documentlink** de los sitios de SharePoint o de OneDrive para la empresa, el script se conecta al centro de seguridad & cumplimiento con PowerShell remoto, crea una nueva búsqueda de contenido que busca carpetas en el sitio. y, a continuación, muestra una lista de las carpetas que se encuentran en el sitio especificado. El script muestra el nombre de cada carpeta y agrega el prefijo de **documentlink** a la dirección URL de la carpeta. Como la propiedad **documentlink** es una propiedad que se puede buscar, use `documentlink:<path>` el par Property: value en una consulta de búsqueda en el paso 2 para buscar en esa carpeta. 
  
A continuación, se muestra un ejemplo de los resultados devueltos por el script para las carpetas del sitio.
  
![Ejemplo de la lista de nombres de documentlink para las carpetas de sitio devueltas por el script](media/519e8347-7365-4067-af78-96c465dc3d15.png)
  
## <a name="step-2-use-a-folder-id-or-documentlink-to-perform-a-targeted-collection"></a>Paso 2: usar un identificador de carpeta o documentlink para realizar una colección de destino

Después de ejecutar el script para recopilar una lista de identificadores de carpeta o documentlinks para un usuario específico, siga el paso siguiente para ir al centro de cumplimiento de & de seguridad y crear una nueva búsqueda de contenido para buscar en una carpeta específica. Use el `folderid:<folderid>` par propiedad o `documentlink:<path>` : valor de la consulta de búsqueda que configure en el cuadro palabra clave de búsqueda de contenido (o como el valor para el parámetro *ContentMatchQuery* si usa el cmdlet **New-ComplianceSearch** ). Puede combinar la `folderid` propiedad o `documentlink` con otros parámetros de búsqueda o condiciones de búsqueda. Si solo incluye la `folderid` propiedad o `documentlink` en la consulta, la búsqueda devolverá todos los elementos que se encuentran en la carpeta especificada. 
  
1. Vaya a [https://protection.office.com](https://protection.office.com).
    
2. Inicie sesión en Office 365 con la cuenta y las credenciales que usó para ejecutar el script en el paso 1.
    
3. En el panel izquierdo del centro de seguridad & cumplimiento, haga clic en búsqueda de **contenido**de **búsqueda** \> y, a continuación, en **nuevo** ![icono](media/O365-MDM-CreatePolicy-AddIcon.gif)agregar.
    
4. En la página **Búsqueda nueva**, escriba un nombre para la búsqueda de contenido. Este nombre debe ser único en la organización. 
    
5. En **¿dónde desea**que se vean?, realice una de las siguientes acciones, en función de si está buscando en una carpeta de buzón de correo o en una carpeta de sitio:
    
    - Haga clic en **elegir buzones específicos para buscar** y, a continuación, agregue el mismo buzón que especificó cuando ejecutó el script en el paso 1. 
    
      O bien
    
    - Haga clic en **elegir sitios específicos para buscar** en buscar y, a continuación, agregue la dirección URL del sitio que especificó al ejecutar el script en el paso 1. 
    
6. Haga clic en **Siguiente**.
    
7. En el cuadro palabra clave de la página **¿qué desea que busquemos?** , pegue el `folderid:<folderid>` valor `documentlink:<path>` o devuelto por el script en el paso 1. 
    
    Por ejemplo, en la siguiente captura de pantalla se buscará cualquier elemento de la subcarpeta depuraciones en la carpeta elementos recuperables del usuario (el valor de la `folderid` propiedad de la subcarpeta purgas se muestra en la captura de pantalla del paso 1):
    
    ![Pegue el folderId o documentlink en el cuadro de palabras clave de la consulta de búsqueda](media/84057516-b663-48a4-a78f-8032a8f8da80.png)
  
8. Haga clic en **Buscar** para iniciar la búsqueda de colección de destino. 
  
### <a name="examples-of-search-queries-for-targeted-collections"></a>Ejemplos de consultas de búsqueda para colecciones dirigidas

A continuación se muestran algunos ejemplos de `folderid` cómo `documentlink` usar las propiedades y en una consulta de búsqueda para realizar una colección de destino. Tenga en cuenta que los marcadores de `folderid:<folderid>` posición `documentlink:<path>` se usan para y para ahorrar espacio. 
  
- En este ejemplo se buscan tres carpetas de buzón diferentes. Puede usar sintaxis de consulta similar para buscar en las carpetas ocultas de la carpeta elementos recuperables de un usuario.
    
  ```
  folderid:<folderid> OR folderid:<folderid> OR folderid:<folderid>
  ```

- En este ejemplo se busca en una carpeta de buzón los elementos que contienen una frase exacta.
    
  ```
  folderid:<folderid> AND "Contoso financial results"
  ```

- En este ejemplo se busca en una carpeta del sitio (y en cualquier subcarpeta) documentos que contengan las letras "NDA" en el título.
    
  ```
  documentlink:<path> AND filename:nda
  ```

- En este ejemplo se busca en una carpeta del sitio (y en cualquier subcarpeta) los documentos que se han modificado en un intervalo de fechas.
    
  ```
  documentlink:<path> AND (lastmodifiedtime>=01/01/2017 AND lastmodifiedtime<=01/21/2017)
  ```
  
## <a name="more-information"></a>Más información

Tenga en cuenta lo siguiente cuando use el script de este artículo para realizar colecciones de destino.
  
- El script no quita ninguna carpeta de los resultados. Por lo tanto, algunas carpetas que aparecen en los resultados podrían no ser buscadas (o devolver cero elementos) porque contienen contenido generado por el sistema.
    
- Este script solo devuelve información de la carpeta del buzón de correo principal del usuario. No devuelve información sobre las carpetas en el buzón de archivo del usuario.
    
- Al buscar carpetas de buzón de correo, solo se buscará en `folderid` la carpeta especificada (identificada por su propiedad); no se buscará en las subcarpetas. Para buscar en las subcarpetas, debe usar el identificador de carpeta de la subcarpeta que desea buscar. 
    
- Al realizar búsquedas en carpetas de sitio, se buscará `documentlink` en la carpeta (identificada por su propiedad) y en todas las subcarpetas. 
    
- Al exportar los resultados de una búsqueda en la que solo especificó `folderid` la propiedad en la consulta de búsqueda, puede elegir la primera opción de exportación: "todos los elementos, excluidos los que tienen un formato no reconocido, están cifrados o no se indizaron por otros motivos". Todos los elementos de la carpeta siempre se exportarán independientemente de su estado de indización, ya que el identificador de carpeta siempre está indizado.
