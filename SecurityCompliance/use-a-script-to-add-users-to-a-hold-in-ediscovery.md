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
# <a name="use-a-script-to-add-users-to-a-hold-in-an-ediscovery-case-in-the-security--compliance-center"></a>Usar un script para agregar usuarios a una suspensión en un caso de exhibición de documentos electrónicos en el centro de seguridad & cumplimiento

El centro de seguridad & cumplimiento proporciona muchos cmdlets de Windows PowerShell que permiten automatizar tareas que llevan mucho tiempo relacionadas con la creación y la administración de casos de eDiscovery. Actualmente, el uso de la herramienta de casos de exhibición de documentos electrónicos en el centro de cumplimiento de seguridad & para poner un gran número de ubicaciones de contenido de custodios en retención lleva tiempo y preparación. Por ejemplo, antes de crear una retención, tiene que recopilar la dirección URL de cada sitio de OneDrive para la empresa que quiera poner en retención. A continuación, para cada usuario que quiera poner en retención, tiene que agregar su buzón y su sitio de OneDrive para la empresa a la retención. En futuras versiones del centro de seguridad & cumplimiento, esto le resultará más sencillo. Hasta entonces, puede usar el script de este artículo para automatizar este proceso.
  
El script le pedirá el nombre del dominio de mi sitio de su organización (por ejemplo, **contoso** en la dirección https://contoso-my.sharepoint.com)URL, el nombre de un caso de eDiscovery existente, el nombre de la nueva retención asociada con el caso, una lista de direcciones de correo electrónico de los usuarios que desea poner en espera y una consulta de búsqueda para usar si desea crear una suspensión basada en consulta. A continuación, el script obtiene la dirección URL del sitio de OneDrive para la empresa para cada usuario de la lista, crea la nueva retención y, a continuación, agrega el buzón y el sitio de OneDrive para la empresa para cada usuario de la lista a la retención. El script también genera archivos de registro que contienen información sobre la nueva suspensión. 
  
Estos son los pasos para que esto suceda:
  
[Paso 1: Instalar el Shell de administración de SharePoint Online](#step-1-install-the-sharepoint-online-management-shell)
  
[Paso 2: generar una lista de usuarios](use-a-script-to-add-users-to-a-hold-in-ediscovery.md#step2)
  
[Paso 3: ejecutar el script para crear una retención y agregar usuarios](use-a-script-to-add-users-to-a-hold-in-ediscovery.md#step3)
  
## <a name="before-you-begin"></a>Antes de empezar

- Debe ser miembro del grupo de roles eDiscovery Manager en el centro de seguridad & cumplimiento y un administrador global de SharePoint Online para ejecutar el script en el paso 3. Para obtener más información, vea [asignar permisos de exhibición de documentos electrónicos en el centro de seguridad _AMP_ cumplimiento de Office 365](assign-ediscovery-permissions.md).
    
- Se puede Agregar un máximo de 1.000 buzones y sitios de 100 a una suspensión asociada a un caso de exhibición de documentos electrónicos en el centro de seguridad & cumplimiento. SuPoniendo que todos los usuarios que quiera poner en retención dispongan de un sitio de OneDrive para la empresa, puede Agregar un máximo de 100 usuarios a una suspensión mediante el script de este artículo. 
    
- Asegúrese de guardar la lista de usuarios que ha creado en el paso 2 y el script en el paso 3 en la misma carpeta. Esto hará que sea más fácil ejecutar el script.
    
- La secuencia de comandos agrega la lista de usuarios a una nueva retención asociada a un caso existente. Asegúrese de que el caso con el que desea asociar la retención se ha creado antes de ejecutar el script.
    
- El script incluye un tratamiento de errores mínimo. Su objetivo principal es ubicar de forma rápida y sencilla el buzón y el sitio de OneDrive para la empresa de cada usuario en espera.
    
- Los scripts de ejemplo que se proporcionan en este tema no son compatibles con ningún servicio o programa de soporte técnico estándar de Microsoft. Los scripts de ejemplo se proporcionan tal cual, sin garantía de ningún tipo. Además, Microsoft se exime de todas las garantías implícitas, incluidas (sin limitación) las garantías implícitas de comerciabilidad o idoneidad para un propósito específico. El usuario asume todos los riesgos derivados del uso o del rendimiento de los scripts de ejemplo y la documentación. Microsoft, sus autores o cualquier persona relacionada con la creación, producción o entrega de los scripts no serán en ningún caso responsables de cualesquiera daños (incluidos, sin limitación, los daños producidos por la pérdida de beneficios comerciales, interrupción de la actividad comercial, pérdida de información empresarial u otras pérdidas económicas) derivados del uso o de la imposibilidad de uso de los scripts de ejemplo o la documentación, incluso aunque Microsoft tenga constancia de la posibilidad de que dichos daños se produzcan.

## <a name="step-1-install-the-sharepoint-online-management-shell"></a>Paso 1: Instalar el Shell de administración de SharePoint Online

El primer paso es instalar el shell de administración de SharePoint Online si todavía no está instalado en el equipo local. No tiene que usar el shell de este procedimiento, pero tiene que instalarlo porque contiene los requisitos previos necesarios para el script que ejecutó en el paso 3. Estos requisitos previos permiten que el script se comunique con SharePoint Online para obtener las direcciones URL de los sitios de OneDrive para la empresa.
  
Vaya a [configurar el entorno de Windows PowerShell de Shell de administración de SharePoint Online](https://go.microsoft.com/fwlink/p/?LinkID=286318) y realice los pasos 1 y 2 para instalar el shell de administración de SharePoint Online en el equipo local. 

## <a name="step-2-generate-a-list-of-users"></a>Paso 2: generar una lista de usuarios
<a name="step2"> </a>

El script del paso 3 creará una retención asociada con un caso de exhibición de documentos electrónicos, y los sitios y agregar los buzones y OneDrive para la empresa de una lista de usuarios a la retención. Solo puede escribir las direcciones de correo electrónico en un archivo de texto o puede ejecutar un comando en Windows PowerShell para obtener una lista de direcciones de correo electrónico y guardarlas en un archivo (ubicado en la misma carpeta en la que guardará el script en el paso 3).
  
Este es un comando de PowerShell (que ejecuta con PowerShell remoto conectado a su organización de Exchange Online) para obtener una lista de direcciones de correo electrónico para todos los usuarios de la organización y guardarla en un archivo de texto denominado HoldUsers. txt.
  
```
Get-Mailbox -ResultSize unlimited -Filter { RecipientTypeDetails -eq 'UserMailbox'} | Select-Object PrimarySmtpAddress > HoldUsers.txt
```

Después de ejecutar este comando, abra el archivo de texto y quite el encabezado que contiene el nombre de `PrimarySmtpAddress`la propiedad. A continuación, quite todas las direcciones de correo electrónico excepto las de los usuarios que desea agregar a la suspensión que creará en el paso 3. Asegúrese de que no haya filas en blanco antes ni después de la lista de direcciones de correo electrónico.
  

  
## <a name="step-3-run-the-script-to-create-a-hold-and-add-users"></a>Paso 3: ejecutar el script para crear una retención y agregar usuarios
<a name="step3"> </a>

Al ejecutar el script en este paso, se le pedirá la siguiente información. Asegúrese de que tiene esta información lista antes de ejecutar el script.
  
- **Sus credenciales de usuario** : el script usará sus credenciales para conectarse al centro de cumplimiento de _AMP_ de seguridad con PowerShell remoto. También usará estas credenciales para acceder a SharePoint Online y obtener las direcciones URL de OneDrive para la empresa para la lista de usuarios.
    
- **Nombre del dominio de mi sitio** : el dominio de mi sitio es el dominio que contiene todos los sitios de OneDrive para la empresa de su organización. Por ejemplo, si la dirección URL del dominio de mi sitio **https://contoso-my.sharepoint.com**es, debe especificar `contoso` cuando el script le pide el nombre de su dominio de mi sitio. 
    
- **Nombre del caso** : nombre de un caso existente. El script creará una nueva suspensión asociada a este caso.
    
- **Nombre de la suspensión** : el nombre de la retención que creará el script y se asociará con el caso especificado.
    
- **Consulta de búsqueda para una retención basada en consulta** : puede crear una suspensión basada en consulta para que solo se coloque en retención el contenido que cumpla los criterios de búsqueda especificados. Para poner todo el contenido en espera, simplemente presione **entrar** cuando se le pida una consulta de búsqueda. 
    
- **Si quiere activar o no la retención** , puede hacer que la secuencia de comandos vuelva a pasar la retención una vez creada o puede hacer que el script cree la retención sin habilitarla. Si no tiene la secuencia de comandos activa, puede activarla más adelante en el centro de seguridad & cumplimiento o mediante la ejecución de los siguientes comandos de PowerShell: 
    
  ```
  Set-CaseHoldPolicy -Identity <name of the hold> -Enabled $true
  ```

  ```
  Set-CaseHoldRule -Identity <name of the hold> -Disabled $false
  ```

- **Nombre del archivo de texto con la lista de usuarios** : el nombre del archivo de texto del paso 2 que contiene la lista de usuarios que se van a agregar a la suspensión. Si este archivo se encuentra en la misma carpeta que el script, escriba el nombre del archivo (por ejemplo, HoldUsers. txt). Si el archivo de texto está en otra carpeta, escriba la ruta de directorio completa del archivo.
    
Una vez que haya recopilado la información que le pedirá el script, el paso final consiste en ejecutar el script para crear la nueva retención y agregar usuarios a la misma.
  
1. Guarde el siguiente texto en un archivo de script de Windows PowerShell mediante un sufijo de nombre de archivo de. ps1; por ejemplo, `AddUsersToHold.ps1`.
    
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

2. En el equipo local, abra Windows PowerShell y vaya a la carpeta donde guardó el script.
    
3. Ejecutar el script; por ejemplo:
    
      ```
    .\AddUsersToHold.ps1
      ```

4. Escriba la información que el script le pide.
    
    El script se conecta a Security & Compliance Center PowerShell y, a continuación, crea la nueva retención en el caso de eDiscovery y agrega los buzones y OneDrive para la empresa para los usuarios de la lista. Puede ir al caso en la página **exhibición** de documentos electrónicos en el centro de seguridad & cumplimiento para ver la nueva suspensión. 
    
Una vez finalizada la ejecución del script, se crean los siguientes archivos de registro y se guardan en la carpeta en la que se encuentra el script.
  
- **LocationsOnHold. txt** : contiene una lista de buzones de correo y de sitios de OneDrive para la empresa en los que la secuencia de comandos se colocó correctamente en retención.
    
- **LocationsNotOnHold. txt** : contiene una lista de buzones de correo y de sitios de OneDrive para la empresa que el script no se ha puesto en espera. Si un usuario tiene un buzón de correo, pero no un sitio de OneDrive para la empresa, el usuario se incluiría en la lista de sitios de OneDrive para la empresa que no se pusieron en suspensión.
    
- **GetCaseHoldPolicy. txt** : contiene la salida del cmdlet **Get-CaseHoldPolicy** para la nueva suspensión, que se ejecutó el script después de crear la nueva suspensión. La información devuelta por este cmdlet incluye una lista de usuarios cuyos buzones y los sitios de OneDrive para la empresa se pusieron en retención y si la retención está habilitada o deshabilitada. 
    
- **GetCaseHoldRule. txt** : contiene la salida del cmdlet **Get-CaseHoldRule** para la nueva suspensión, que se ejecutó el script después de crear la nueva suspensión. La información devuelta por este cmdlet incluye la consulta de búsqueda si usó el script para crear una suspensión basada en consulta. 
