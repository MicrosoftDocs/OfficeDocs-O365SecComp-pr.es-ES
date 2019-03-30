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
ms.openlocfilehash: 2f0954bf7822ca6c82165ad20b2c732ab0594257
ms.sourcegitcommit: e7a776a04ef6ed5e287a33cfdc36aa2d72862b55
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/29/2019
ms.locfileid: "31001283"
---
# <a name="use-content-search-to-search-the-mailbox-and-onedrive-for-business-site-for-a-list-of-users"></a>Usar búsqueda de contenido para buscar una lista de usuarios en el buzón y el sitio de OneDrive para la Empresa

El centro de seguridad & cumplimiento proporciona una cantidad de cmdlets de Windows PowerShell que permiten automatizar las tareas relacionadas con la exhibición de documentos electrónicos que consumen tiempo. Actualmente, la creación de una búsqueda de contenido en el centro de seguridad & cumplimiento para buscar en un gran número de ubicaciones de contenido de custodios lleva tiempo y preparación. Antes de crear una búsqueda, tiene que recopilar la dirección URL de cada sitio de OneDrive para la empresa y, a continuación, agregar a la búsqueda todos los buzones de correo y neDrive para el sitio de la empresa. En futuras versiones, será más fácil hacerlo en el centro de cumplimiento de & de seguridad. Hasta entonces, puede usar el script de este artículo para automatizar este proceso. Esta secuencia de comandos le pedirá el nombre del dominio de mi sitio de su organización (por ejemplo, **contoso** en https://contoso-my.sharepoint.com)la dirección URL, una lista de direcciones de correo electrónico de usuario, el nombre de la nueva búsqueda de contenido y la consulta de búsqueda que se va a usar. La secuencia de comandos obtiene la dirección URL de OneDrive para la empresa de cada usuario de la lista y, a continuación, crea e inicia una búsqueda de contenido que busca en el buzón y el sitio de OneDrive para la empresa para cada usuario de la lista, usando la consulta de búsqueda que proporcione. 
  
## <a name="before-you-begin"></a>Antes de empezar

- Debe ser miembro del grupo de roles eDiscovery Manager en el centro de seguridad & cumplimiento y un administrador global de SharePoint Online para ejecutar el script en el paso 3.
    
- Asegúrese de guardar la lista de usuarios que ha creado en el paso 2 y el script en el paso 3 en la misma carpeta. Esto hará que sea más fácil ejecutar el script.
    
- El script incluye un tratamiento de errores mínimo. Su objetivo principal es buscar de forma rápida y sencilla el sitio de buzón de correo y OneDrive para la empresa de cada usuario.
    
- Las secuencias de comandos de ejemplo que se proporcionan en este tema no se admiten en ningún servicio o programa de soporte técnico estándar de Microsoft. Los scripts de ejemplo aparecen "TAL CUAL", sin garantía de ningún tipo. Microsoft renuncia aún más a[https://go.microsoft.com/fwlink/p/?LinkId=517283](https://go.microsoft.com/fwlink/p/?LinkId=517283)todas las garantías de i mplied, incluidas, entre otras, todas las garantías implícitas de comerciabilidad o de idoneidad para un propósito en particular. Cualquier riesgo resultante del uso o resultado de los scripts y la documentación de ejemplo será únicamente responsabilidad suya. En ningún caso Microsoft, sus autores o cualquier persona involucrada en su creación, producción o entrega de los scripts será responsable de cualquier daño (incluidos, de manera enunciativa pero no limitativa, daños por pérdidas de beneficios de una empresa, interrupción de la actividad de una empresa, pérdidas de información de una empresa, o cualquier otro daño pecuniario), incluso si Microsoft supiera de la posibilidad de tales daños.
    
## <a name="step-1-install-the-sharepoint-online-management-shell"></a>Paso 1: Instalar el Shell de administración de SharePoint Online
<a name="step1"> </a>

El primer paso es instalar el shell de administración de SharePoint Online. No tiene que usar el shell de este procedimiento, pero tiene que instalarlo porque contiene los requisitos previos necesarios para el script que ejecutó en el paso 3. Estos requisitos previos permiten que el script se comunique con SharePoint Online para obtener las direcciones URL de los sitios de OneDrive para la empresa.
  
Vaya a [configurar el entorno de Windows PowerShell de Shell de administración de SharePoint Online](https://go.microsoft.com/fwlink/p/?LinkID=286318) y realice el paso 1 y el paso 2 para instalar el shell de administración de SharePoint Online.
  
## <a name="step-2-generate-a-list-of-users"></a>Paso 2: generar una lista de usuarios
<a name="step2"> </a>

El script del paso 3 creará una búsqueda de contenido para buscar en los buzones y las cuentas de OneDrive una lista de usuarios. Solo puede escribir las direcciones de correo electrónico en un archivo de texto o puede ejecutar un comando en Windows PowerShell para obtener una lista de direcciones de correo electrónico y guardarlas en un archivo (ubicado en la misma carpeta en la que guardará el script en el paso 3).
  
Este es un comando de [Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=517283) que puede runt para obtener una lista de direcciones de correo electrónico para todos los usuarios de la organización y guardarla en un `Users.txt`archivo de texto denominado. 
  
```
Get-Mailbox -ResultSize unlimited -Filter { RecipientTypeDetails -eq 'UserMailbox'} | Select-Object PrimarySmtpAddress > Users.txt
```

Después de ejecutar este comando, asegúrese de abrir el archivo y quitar el encabezado que contiene el nombre de la propiedad `PrimarySmtpAddress`. El archivo de texto solo debe contener una lista de direcciones de correo electrónico y nada más. Asegúrese de que no haya filas en blanco antes ni después de la lista de direcciones de correo electrónico.
  
## <a name="step-3-run-the-script-to-create-and-start-the-search"></a>Paso 3: ejecutar el script para crear e iniciar la búsqueda

Al ejecutar el script en este paso, se le pedirá la siguiente información. Asegúrese de que tiene esta información lista antes de ejecutar el script.
  
- **Sus credenciales de usuario** : el script usará sus credenciales para acceder a SharePoint Online y obtener las direcciones URL de OneDrive para la empresa y para conectarse al centro de seguridad & cumplimiento con PowerShell remoto. 
    
- **Nombre del dominio de mi sitio** : el dominio de mi sitio es el dominio que contiene todos los sitios de OneDrive para la empresa de su organización. Por ejemplo, si la dirección URL del dominio de mi sitio **https://contoso-my.sharepoint.com**es, debe especificar `contoso` cuando el script le pide el nombre de su dominio de mi sitio. 
    
- **Nombreruta del archivo de texto del paso 2** : el directorio del archivo de texto que creó en el paso 2. Si el archivo de texto y el script están ubicados en la misma carpeta, escriba el nombre del archivo de texto. De lo contrario, escriba el directorio completo del archivo de texto. 
    
- **Nombre de la búsqueda de contenido** : el nombre de la búsqueda de contenido que se creará mediante el script. 
    
- **Consulta de búsqueda** : se crea y ejecuta la consulta de búsqueda que se usará con la búsqueda de contenido. Para obtener más información acerca de las consultas de búsqueda, vea [consultas de palabras clave y condiciones de búsqueda para la búsqueda de contenido](keyword-queries-and-search-conditions.md).


**Para ejecutar el script:**
    
1. Guarde el siguiente texto en un archivo de script de Windows PowerShell mediante un sufijo de nombre de archivo de. ps1; por ejemplo, `SearchEXOOD4B.ps1`. Guarde el archivo en la misma carpeta en la que guardó la lista de usuarios en el paso 2.
    
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

2. Abra Windows PowerShell y vaya a la carpeta en la que guardó el script y la lista de usuarios del paso 2.
    
3. Inicie el script; por ejemplo:
    
    ```
    .\SearchEXOOD4B.ps1
    ```

4. Cuando se le pidan sus credenciales, escriba su dirección de correo electrónico y contraseña y, a continuación, haga clic en **Aceptar**. 
    
5. Escriba la información siguiente cuando se lo solicite el script. Escriba cada fragmento de información y, a continuación, presione **entrar**.
    
    - Nombre del dominio de mi sitio. 
    
    - Ruta de ruta del archivo de texto que contiene la lista de usuarios.
    
    - Un nombre para la búsqueda de contenido.
    
    - La consulta de búsqueda (déjelo en blanco para devolver todos los elementos de las ubicaciones de contenido).
    
    El script obtiene las direcciones URL de cada sitio de OneDrive para la empresa y, a continuación, crea e inicia la búsqueda. Puede ejecutar el cmdlet **Get-ComplianceSearch** en Security _AMP_ Compliance Center PowerShell para mostrar las estadísticas y los resultados de la búsqueda, o bien puede ir a la página de **búsqueda de contenido** en el centro de seguridad & cumplimiento para ver la información sobre la búsqueda. 
