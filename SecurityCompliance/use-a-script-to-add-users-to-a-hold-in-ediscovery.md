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
# <a name="use-a-script-to-add-users-to-a-hold-in-an-ediscovery-case-in-the-office-365-security-amp-compliance-center"></a>Usar una secuencia de comandos para agregar usuarios a una suspensión en un caso de exhibición de documentos electrónicos en la seguridad de Office 365 &amp; centro de cumplimiento

La seguridad de Office 365 &amp; centro de cumplimiento proporciona una gran cantidad de cmdlets de Windows PowerShell que permiten automatizar laboriosas tareas relacionadas con la creación y administración de casos de exhibición de documentos electrónicos. Actualmente, con la herramienta de casos de exhibición de documentos electrónicos en la seguridad &amp; centro de cumplimiento de normas para poner un gran número de ubicaciones de contenido de custodia en espera lleva tiempo y preparación. Por ejemplo, antes de crear una suspensión, se debe recopilar la dirección URL para cada OneDrive para el sitio de negocio que desee poner en espera. A continuación, para cada usuario que desee poner en espera, se debe agregar a su buzón y su OneDrive para el sitio de negocio a la suspensión. En futuras versiones de la seguridad &amp; centro de cumplimiento, esto se obtiene más fácil de hacer. Hasta entonces, puede utilizar la secuencia de comandos de este artículo para automatizar este proceso.
  
La secuencia de comandos le pide el nombre de dominio de Mi sitio de la organización (por ejemplo, **contoso** en la dirección URL https://contoso-my.sharepoint.com), el nombre de un caso de exhibición de documentos electrónicos existente, el nombre de la suspensión nuevo que asociado con el caso, una lista de direcciones de correo electrónico de los usuarios que desee. para poner en espera y una consulta de búsqueda que se utilizará si desea crear una suspensión basada en consultas. La secuencia de comandos, a continuación, obtiene la dirección URL para el OneDrive para sitio empresarial para cada usuario en la lista, crea la suspensión nuevo y, a continuación, agrega el buzón de correo y OneDrive para sitio empresarial para cada usuario en la lista a la suspensión. La secuencia de comandos también genera archivos de registro que contienen información acerca de la suspensión nuevo. 
  
Estos son los pasos para que esto ocurra:
  
[Paso 1: Instalar el Shell de administración de SharePoint Online](use-a-script-to-add-users-to-a-hold-in-ediscovery.md#step1)
  
[Paso 2: Generar una lista de usuarios](use-a-script-to-add-users-to-a-hold-in-ediscovery.md#step2)
  
[Paso 3: Ejecutar el script para crear una suspensión y agregar usuarios](use-a-script-to-add-users-to-a-hold-in-ediscovery.md#step3)
  
## <a name="before-you-begin"></a>Antes de empezar

- Tiene que ser un miembro del grupo de roles de administrador de exhibición de documentos electrónicos en la seguridad &amp; centro de cumplimiento y un administrador global de SharePoint Online para ejecutar el script en el paso 3. Para obtener más información, vea [asignar permisos de exhibición de documentos electrónicos en la seguridad de Office 365 &amp; centro de cumplimiento](assign-ediscovery-permissions.md).
    
- Un máximo de 1.000 buzones de correo y 100 sitios puede agregarse a una suspensión a la que está asociado con un caso de exhibición de documentos electrónicos en la seguridad &amp; centro de cumplimiento. Suponiendo que todos los usuarios que desea poner en espera tienen un OneDrive para el sitio de negocio, puede agregar un máximo de 100 usuarios a una suspensión con la secuencia de comandos en este artículo. 
    
- Asegúrese de guardar la lista de usuarios que se crean en el paso 2 y la secuencia de comandos en el paso 3 en la misma carpeta. Que facilitan ejecutar el script.
    
- La secuencia de comandos agrega la lista de usuarios a una suspensión nueva que está asociada con un caso existente. Asegúrese de que se crea el caso de que se va a asociar la suspensión con antes de ejecutar la secuencia de comandos.
    
- La secuencia de comandos incluye el tratamiento de errores mínima. Su objetivo principal es rápida y fácilmente colocar el buzón de correo y OneDrive para el sitio de negocio de cada usuario en suspensión.
    
- Las secuencias de comandos de ejemplo proporcionados en este tema no son compatibles con cualquier servicio o programa de soporte estándar de Microsoft. Las secuencias de comandos de ejemplo se proporcionan tal cual sin garantía de ningún tipo. Microsoft renuncia a todas las garantías implícitas incluidas, sin limitación, cualquier las garantías implícitas de comerciabilidad o de idoneidad para un fin determinado. Todo el riesgo que pueda surgir por el uso o el rendimiento de las secuencias de comandos de ejemplo y documentación permanece con usted. En ningún caso Microsoft, sus autores o cualquier otro implicado en la creación, producción o entrega de las secuencias de comandos serán responsables de los daños índole (incluidos, pero sin limitarse a, daños por pérdida de beneficios empresariales, interrupción del negocio, pérdida de información de la empresa, o en otras pérdidas de carácter económico) derivado del uso o la incapacidad de usar los scripts de ejemplo o documentación, aunque Microsoft haya sido notificado de la posibilidad de dichos daños.

## <a name="step-1-install-the-sharepoint-online-management-shell"></a>Paso 1: Instalar el Shell de administración de SharePoint Online

El primer paso es instalar la consola de administración en línea de SharePoint si no está ya está instalado en el equipo local. No tiene que usar el shell en este procedimiento, pero debe instalarlo porque contiene los requisitos previos necesarios para la secuencia de comandos que se ejecutan en el paso 3. Estos requisitos previos de permiten la secuencia de comandos para comunicarse con SharePoint Online para obtener las direcciones URL para el OneDrive para sitios de negocio.
  
Vaya a [Configurar el entorno de SharePoint Online Management Shell de Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkID=286318) y realice el paso 1 y paso 2 para instalar la consola de administración de SharePoint Online en el equipo local. 

## <a name="step-2-generate-a-list-of-users"></a>Paso 2: Generar una lista de usuarios
<a name="step2"> </a>

La secuencia de comandos en el paso 3 creará una suspensión a la que está asociado con un caso de exhibición de documentos electrónicos y la adición de los buzones y OneDrive para sitios de profesionales de una lista de los usuarios a la suspensión. Sólo puede escribir las direcciones de correo electrónico en un archivo de texto, o puede ejecutar un comando de Windows PowerShell para obtener una lista de direcciones de correo electrónico y guardarlos en un archivo (que se encuentra en la misma carpeta que se va a guardar la secuencia de comandos en el paso 3).
  
Este es un comando de PowerShell (que se ejecuta mediante el uso de PowerShell remoto conectado a la organización de Exchange Online) obtener una lista de direcciones de correo electrónico para todos los usuarios de su organización y guárdelo en un archivo de texto denominado HoldUsers.txt.
  
```
Get-Mailbox -ResultSize unlimited -Filter { RecipientTypeDetails -eq 'UserMailbox'} | Select-Object PrimarySmtpAddress > HoldUsers.txt
```

Después de ejecutar este comando, abra el archivo de texto y quitar el encabezado que contiene el nombre de la propiedad, `PrimarySmtpAddress`. A continuación, quite todas las direcciones de correo electrónico, excepto las de los usuarios que desea agregar a la suspensión que creará en el paso 3. Asegúrese de que no hay ninguna fila en blanco antes o después de la lista de direcciones de correo electrónico.
  

  
## <a name="step-3-run-the-script-to-create-a-hold-and-add-users"></a>Paso 3: Ejecutar el script para crear una suspensión y agregar usuarios
<a name="step3"> </a>

Cuando se ejecuta la secuencia de comandos en este paso, le pedirá la siguiente información. Asegúrese de que tiene esta información lista antes de ejecutar la secuencia de comandos.
  
- **Sus credenciales de usuario** : la secuencia de comandos usará las credenciales para conectarse a la seguridad &amp; centro de cumplimiento con PowerShell remoto. También utilizará estas credenciales para tener acceso a SharePoint Online para obtener el OneDrive para direcciones URL de negocio para la lista de usuarios.
    
- **Nombre de su dominio de Mi sitio** - misitio el dominio es el dominio que contiene la de OneDrive para sitios de profesionales de la organización. Por ejemplo, si la dirección URL para su dominio de Mi sitio es **https://contoso-my.sharepoint.com**, a continuación, deberá escribir `contoso` cuando la secuencia de comandos le pide el nombre de su dominio de Mi sitio. 
    
- **Nombre del caso** - el nombre de un caso existente. La secuencia de comandos creará una nueva suspensión que está asociada con este caso.
    
- **Nombre de la suspensión** - el nombre de la suspensión de la secuencia de comandos creará y asociar con el caso especificado.
    
- **Mantenga presionada la consulta de búsqueda para una consulta-based** - puede crear una suspensión basada en consultas para que sólo el contenido que cumpla los criterios de búsqueda especificado se pondrá en espera. Para poner todo el contenido en espera, simplemente, presione **ENTRAR** cuando se le solicite para una consulta de búsqueda. 
    
- **Si desea activar la suspensión** - puede tener la secuencia de comandos activar la suspensión después de crearla o puede hacer que la secuencia de comandos cree la suspensión sin habilitarla. Si no dispone de la secuencia de comandos activar la suspensión, puede activarlo más adelante en la seguridad &amp; centro de cumplimiento o mediante la ejecución de los siguientes comandos de PowerShell: 
    
  ```
  Set-CaseHoldPolicy -Identity <name of the hold> -Enabled $true
  ```

  ```
  Set-CaseHoldRule -Identity <name of the hold> -Disabled $false
  ```

- **Nombre del archivo de texto con la lista de usuarios** : el nombre del archivo de texto del paso 2 que contiene la lista de usuarios para agregar a la suspensión. Si este archivo se encuentra en la misma carpeta que la secuencia de comandos, simplemente escriba el nombre del archivo (por ejemplo, HoldUsers.txt). Si el archivo de texto está en otra carpeta, escriba la ruta de acceso completa del archivo.
    
Una vez recopilada la información que la secuencia de comandos le pedirá, es el paso final ejecutar el script para crear la nueva suspensión y agregar usuarios a ella.
  
1. Guarde el siguiente texto en un archivo de secuencia de comandos de Windows PowerShell mediante el uso de un sufijo de nombre de archivo de. ps1; Por ejemplo, `AddUsersToHold.ps1`.
    
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

2. En el equipo local, abra Windows PowerShell y vaya a la carpeta donde guardó la secuencia de comandos.
    
3. Ejecute la secuencia de comandos; Por ejemplo:
    
      ```
    .\AddUsersToHold.ps1
      ```

4. Escriba la información que le pide la secuencia de comandos.
    
    La secuencia de comandos se conecta a seguridad & PowerShell de centro de cumplimiento y, a continuación, crea la suspensión nuevo en el caso de exhibición de documentos electrónicos y agrega los buzones y OneDrive para la empresa para los usuarios de la lista. Puede ir a las mayúsculas y minúsculas en la página de **exhibición de documentos electrónicos** en la seguridad &amp; centro de cumplimiento para ver la suspensión nuevo. 
    
Una vez finalizada la secuencia de comandos que se ejecuta, lo crea los siguientes archivos de registro y los guarda en la carpeta donde se encuentra la secuencia de comandos.
  
- **LocationsOnHold.txt** - contiene una lista de buzones de correo y OneDrive para los sitios de negocio que la secuencia de comandos correctamente colocado en suspensión.
    
- **LocationsNotOnHold.txt** - contiene una lista de buzones de correo y OneDrive para los sitios de negocio que la secuencia de comandos no se convirtieron en espera. Si un usuario tiene un buzón de correo, pero no un OneDrive para el sitio de negocio, el usuario se incluirá en la lista de OneDrive para sitios de negocio que no se han colocado en suspensión.
    
- **GetCaseHoldPolicy.txt** - contiene el resultado del cmdlet **Get-CaseHoldPolicy** para la suspensión nuevo, que se ejecutó la secuencia de comandos después de crear la suspensión nuevo. La información devuelta por este cmdlet incluye una lista de los usuarios cuyos buzones de correo y OneDrive para sitios de negocio se colocaron en espera y si la suspensión está habilitada o deshabilitada. 
    
- **GetCaseHoldRule.txt** - contiene el resultado del cmdlet **Get-CaseHoldRule** para la suspensión nuevo, que se ejecutó la secuencia de comandos después de crear la suspensión nuevo. La información devuelta por este cmdlet incluye la consulta de búsqueda si se usa la secuencia de comandos para crear una suspensión basada en consultas. 
