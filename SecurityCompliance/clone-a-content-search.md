---
title: Clonación de una búsqueda de contenido en la seguridad de Office 365 &amp; centro de cumplimiento
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 4/26/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MED150
ms.assetid: 7b40eeaa-544c-4534-b89b-9f79998e374c
description: Use el script de Windows PowerShell en este artículo para clonar rápidamente una búsqueda de contenido existente en la seguridad &amp; búsqueda Compliane centro. Al clonar una búsqueda, se crea una nueva búsqueda (con un nuevo nombre) que contiene las mismas propiedades que la búsqueda original. A continuación, puede editar la nueva búsqueda (cambiando la consulta de palabra clave o el intervalo de fechas) y, a continuación, ejecútelo.
ms.openlocfilehash: fd2ea0d8fa812d23e7479b664b13c786a62d5a38
ms.sourcegitcommit: 7956955cd919f6e00b64e4506605a743c5872549
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/26/2018
ms.locfileid: "25038053"
---
# <a name="clone-a-content-search-in-the-office-365-security-amp-compliance-center"></a>Clonación de una búsqueda de contenido en la seguridad de Office 365 &amp; centro de cumplimiento

Creación de una búsqueda de contenido en Office 365 seguridad &amp; centro de cumplimiento que busca una gran cantidad de buzones de correo o de SharePoint y OneDrive para sitios de negocio pueden tardar unos minutos. Especificación de los sitios para buscar también puede ser propensa a errores si se escribe mal una dirección URL. Para evitar estos problemas, puede usar la secuencia de comandos de Windows PowerShell en este artículo para clonar rápidamente una búsqueda de contenido existente. Al clonar una búsqueda, se crea una nueva búsqueda (con un nombre diferente) que contiene las mismas propiedades (por ejemplo, las ubicaciones de contenido y la consulta de búsqueda) que la búsqueda original. A continuación, puede editar la nueva búsqueda (cambiando la consulta de palabra clave o el intervalo de fechas) y ejecútelo.
  
¿Por qué clonar búsquedas de contenido?
  
- Para comparar los resultados de la palabra clave diferente ejecutar consultas de búsqueda en las mismas ubicaciones de contenido.
    
- Para que se evitará tener que volver a escribir un gran número de ubicaciones de contenido cuando se crea una nueva búsqueda.
    
- Para reducir el tamaño de los resultados de búsqueda; Por ejemplo, si dispone de una búsqueda que devuelve demasiados resultados para exportar, puede clonar la búsqueda y, a continuación, agregue una condición de búsqueda en función de un intervalo de fechas para reducir el número de resultados de búsqueda.
  
## <a name="before-you-begin"></a>Antes de empezar

- Tiene que ser un miembro del grupo de roles de administrador de exhibición de documentos electrónicos en la seguridad &amp; centro de cumplimiento para ejecutar la secuencia de comandos que se describen en este tema.
    
- La secuencia de comandos incluye el tratamiento de errores mínima. El propósito principal de la secuencia de comandos es clonar rápidamente una búsqueda de contenido.
    
- La secuencia de comandos crea una nueva búsqueda de contenido, pero no la inicia.
    
- Esta secuencia de comandos tiene en cuenta si la búsqueda de contenido que está clonando está asociada a un caso de exhibición de documentos electrónicos. Si la búsqueda está asociada con un caso, la nueva búsqueda también se asociarán con el mismo caso. Si la búsqueda existente no está asociada a un caso, la nueva búsqueda aparecerán en la página de **búsqueda de contenido** en la seguridad &amp; centro de cumplimiento. 
    
- El script de ejemplo proporcionado en este tema no es compatible con ningún servicio o programa de soporte estándar de Microsoft. El script de ejemplo se proporciona tal cual sin garantía de ningún tipo. Microsoft renuncia a todas las garantías implícitas incluidas, sin limitación, cualquier las garantías implícitas de comerciabilidad o de idoneidad para un fin determinado. Todo el riesgo que pueda surgir por el uso o el rendimiento de la secuencia de comandos de ejemplo y documentación permanece con usted. En ningún caso Microsoft, sus autores o cualquier otro implicado en la creación, producción o entrega de las secuencias de comandos serán responsables de los daños índole (incluidos, pero sin limitarse a, daños por pérdida de beneficios empresariales, interrupción del negocio, pérdida de información de la empresa, o en otras pérdidas de carácter económico) derivado del uso o la incapacidad de usar los scripts de ejemplo o documentación, aunque Microsoft haya sido notificado de la posibilidad de dichos daños.
  
## <a name="step-1-run-the-script-to-clone-a-search"></a>Paso 1: Ejecute el script para clonar una búsqueda

La secuencia de comandos en este paso creará una nueva búsqueda de contenido mediante la clonación de uno existente. Al ejecutar este script, se le pedirá la siguiente información:
  
- **Sus credenciales de usuario** : la secuencia de comandos usará las credenciales para conectarse a la seguridad &amp; centro de cumplimiento de normas de la organización de Office 365 con Windows PowerShell. Como se mencionó anteriormente, tiene que ser un miembro del grupo de roles de administrador de exhibición de documentos electrónicos en la seguridad &amp; centro de cumplimiento para ejecutar el script. 
    
- **El nombre de la búsqueda existente** - se trata de la búsqueda de contenido que va a clonar. 
    
- **El nombre de la nueva búsqueda que se crearán** - si deja este valor en blanco, la secuencia de comandos creará un nombre para la búsqueda nuevo que se basa en el nombre de la búsqueda que está clonando. 
    
Para clonar una búsqueda:
  
1. Guarde el siguiente texto en un archivo de secuencia de comandos de Windows PowerShell mediante el uso de un sufijo de nombre de archivo de. ps1; Por ejemplo, `CloneSearch.ps1`.
    
  ```
  # This PowerShell script clones an existing Content Search in the Office 365 Security &amp; Compliance Center
  # Get login credentials from the user
  if(!$UserCredential)
  {
      $UserCredential = Get-Credential
      $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Credential $UserCredential -Authentication Basic -AllowRedirection
      if (!$Session)
      {
          Write-Error "Couldn't create a remote PowerShell session."
          return
      }
      Import-PSSession $Session -AllowClobber -DisableNameChecking
      $Host.UI.RawUI.WindowTitle = $UserCredential.UserName + " (Office 365 Security &amp; Compliance Center)"
  }
  # Ask for the name of the search you want to clone
  $searchName = Read-Host 'Enter the name of the search that you want to clone'
  # Ask for the name of the new search
  $newSearchName = Read-Host 'Enter a name for the new search [leave blank to automatically generate a name]'
  $originalSearch = Get-ComplianceSearch $searchName -EA SilentlyContinue
  # Make sure we have a valid search before continuing
  if(!$originalSearch)
  {
      Write-Error "Couldn't find search: $searchName"
      return
  }
  $searchNameCounter = 1
  # Find a suitable name for the new search
  while(!$newSearchName)
  {
      $newSearchName = $originalSearch.Name + "_" + $searchNameCounter
      $tempSearch = Get-ComplianceSearch $newSearchName -EA SilentlyContinue
      if ($tempSearch)
      {
          $newSearchName = $null
          $searchNameCounter++
      }
  }
  $caseName
  # Determine if the search is part of a case; if so get the case name
  if ($originalSearch.CaseId)
  {
      $searchCase = Get-ComplianceCase $originalSearch.CaseId
      $caseName = $searchCase.Name
  }
  # Need to cast this value as a Boolean the old fashion way
  $allowNotFoundExchangeLocationsEnabled = $false
  if ($originalSearch.AllowNotFoundExchangeLocationsEnabled)
  {
      $allowNotFoundExchangeLocationsEnabled = $true
  }
  $newSearch = New-ComplianceSearch -Name $newSearchName -AllowNotFoundExchangeLocationsEnabled $allowNotFoundExchangeLocationsEnabled -Case $caseName -ContentMatchQuery $originalSearch.ContentMatchQuery -Description $originalSearch.Description -ExchangeLocation $originalSearch.ExchangeLocation -ExchangeLocationExclusion $originalSearch.ExchangeLocationExclusion -Language $originalSearch.Language -SharePointLocation $originalSearch.SharePointLocation -SharePointLocationExclusion $originalSearch.SharePointLocationExclusion -PublicFolderLocation $originalSearch.PublicFolderLocation
  if ($newSearch)
  {
      Write-Host $newSearch.Name "was successfully created" -ForegroundColor Yellow
  }
  ```

2. Abra Windows PowerShell y vaya a la carpeta donde guardó la secuencia de comandos.
    
3. Ejecute la secuencia de comandos; Por ejemplo:
    
    ```
    .\CloneSearch.ps1
    ```

4. Cuando se le pidan sus credenciales, escriba su dirección de correo electrónico y contraseña y, a continuación, haga clic en **Aceptar**.
    
5. Escriba la siguiente información cuando se le solicite la secuencia de comandos. Escriba cada parte de la información y, a continuación, presione **ENTRAR**.
    
    - El nombre de la búsqueda existente.
    
    - El nombre de la búsqueda nuevo.
    
    La secuencia de comandos crea la búsqueda de contenido nuevo, pero no la inicia. Esto le ofrece una oportunidad para editar y ejecutar la búsqueda en el paso siguiente. Puede ver las propiedades de la nueva búsqueda ejecutando el cmdlet **Get-ComplianceSearch** o yendo a la página de **búsqueda de contenido** o de **exhibición de documentos electrónicos** en la seguridad &amp; centro de cumplimiento, dependiendo de si está o no la búsqueda nuevo asociarse a un caso. 
  
## <a name="step-2-edit-and-run-the-cloned-search-in-the-security-amp-compliance-center"></a>Paso 2: Editar y ejecutar la búsqueda clonada en la seguridad &amp; centro de cumplimiento

Después de la que ha ejecutado la secuencia de comandos que se debe clonar una búsqueda de contenido existente, el siguiente paso es ir a la seguridad &amp; centro de cumplimiento para editar y ejecutar la búsqueda nuevo. Como se mencionó anteriormente, puede editar una búsqueda cambiando la consulta de búsqueda de palabra clave y agregar o quitar las condiciones de búsqueda. Para obtener más información, vea:
  
- [Búsqueda de contenido en Office 365](content-search.md)
    
- [Consultas de palabras clave y condiciones de búsqueda para la búsqueda de contenido](keyword-queries-and-search-conditions.md).
    
- [casos de exhibición de documentos electrónicos en la seguridad de Office 365 &amp; centro de cumplimiento](ediscovery-cases.md)
