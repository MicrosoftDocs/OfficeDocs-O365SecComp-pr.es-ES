---
title: Clonar una búsqueda de contenido
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 4/26/2017
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
ms.assetid: 7b40eeaa-544c-4534-b89b-9f79998e374c
description: Use el script de Windows PowerShell de este artículo para clonar rápidamente una búsqueda de contenido existente en el centro de cumplimiento de Office 365 o Microsoft 365. Cuando se clona una búsqueda, se crea una nueva búsqueda (con un nombre nuevo) que contiene las mismas propiedades que la búsqueda original. A continuación, puede editar la nueva búsqueda (cambiando la palabra clave consulta o el intervalo de fechas) y, a continuación, ejecutarla.
ms.openlocfilehash: b08ccb6fbaf2dc9d92e0814fe9f92ea77c731147
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32243351"
---
# <a name="clone-a-content-search"></a>Clonar una búsqueda de contenido

La creación de una búsqueda de contenido en el centro de cumplimiento en Office 365 o Microsoft 365 que realiza búsquedas en muchos buzones o en sitios de SharePoint y OneDrive para la empresa puede tardar unos minutos. La especificación de los sitios que se van a buscar también puede provocar errores si se escribe Inde una dirección URL. Para evitar estos problemas, puede usar el script de Windows PowerShell de este artículo para clonar rápidamente una búsqueda de contenido existente. Cuando se clona una búsqueda, se crea una nueva búsqueda (con un nombre diferente) que contiene las mismas propiedades (como las ubicaciones de contenido y la consulta de búsqueda) como la búsqueda original. A continuación, puede editar la nueva búsqueda (cambiando la palabra clave consulta o el intervalo de fechas) y ejecutarla.
  
¿Por qué clonar búsquedas de contenido?
  
- Para comparar los resultados de las diferentes consultas de búsqueda de palabras clave que se ejecutan en las mismas ubicaciones de contenido.
    
- Para evitar tener que volver a especificar un gran número de ubicaciones de contenido al crear una nueva búsqueda.
    
- Para reducir el tamaño de los resultados de la búsqueda; por ejemplo, si tiene una búsqueda que devuelve demasiados resultados para exportar, puede clonar la búsqueda y, a continuación, agregar una condición de búsqueda basada en un intervalo de fechas para reducir el número de resultados de búsqueda.
  
## <a name="before-you-begin"></a>Antes de empezar

- Debe ser miembro del grupo de roles eDiscovery Manager en el centro de seguridad & cumplimiento para ejecutar el script que se describe en este tema.
    
- El script incluye un tratamiento de errores mínimo. El objetivo principal del script es clonar rápidamente una búsqueda de contenido.
    
- El script crea una nueva búsqueda de contenido, pero no la inicia.
    
- Este script tiene en cuenta si la búsqueda de contenido que va a clonar está asociada a un caso de exhibición de documentos electrónicos. Si la búsqueda está asociada a un caso, la nueva búsqueda también se asociará con el mismo caso. Si la búsqueda existente no está asociada a un caso, la nueva búsqueda se enumerará en la página **búsqueda de contenido** en el centro de cumplimiento. 
    
- La secuencia de comandos de ejemplo proporcionada en este tema no es compatible con ningún servicio o programa de soporte estándar de Microsoft. El script de ejemplo se proporciona tal cual sin garantías de ningún tipo. Además, Microsoft no se hace responsable de cualquier garantía implícita, incluyendo, de manera enunciativa pero no limitativa, cualquier garantía implícita de comercialización o de calidad para cualquier propósito. Todo el riesgo derivado del uso o el rendimiento de la secuencia de comandos de muestra y la documentación se conservan con usted. En ningún caso Microsoft, sus autores o cualquier persona involucrada en su creación, producción o entrega de los scripts será responsable de cualquier daño (incluidos, de manera enunciativa pero no limitativa, daños por pérdidas de beneficios de una empresa, interrupción de la actividad de una empresa, pérdidas de información de una empresa, o cualquier otro daño pecuniario), incluso si Microsoft supiera de la posibilidad de tales daños.
  
## <a name="step-1-run-the-script-to-clone-a-search"></a>Paso 1: ejecutar el script para clonar una búsqueda

El script de este paso creará una nueva búsqueda de contenido mediante la clonación de una existente. Al ejecutar este script, se le pedirá la siguiente información:
  
- **Sus credenciales de usuario** : el script usará sus credenciales para conectarse al centro de seguridad & cumplimiento de la organización de Office 365 con Windows PowerShell. Como se mencionó anteriormente, tiene que ser miembro del grupo de roles eDiscovery Manager en el centro de seguridad & compCompliance para ejecutar el script. 
    
- **El nombre de la búsqueda existente** : es la búsqueda de contenido que desea clonar. 
    
- **El nombre de la nueva búsqueda que** se creará; si deja este valor en blanco, el script creará un nombre para la nueva búsqueda que se basa en el nombre de la búsqueda que va a clonar. 
    
Para clonar una búsqueda:
  
1. Guarde el siguiente texto en un archivo de script de Windows PowerShell mediante un sufijo de nombre de archivo de. ps1; por ejemplo, `CloneSearch.ps1`.
    
  ```
  # This PowerShell script clones an existing Content Search in the Office 365 security and compliance center.
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
      $Host.UI.RawUI.WindowTitle = $UserCredential.UserName + " (Security & Compliance Center)"
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

2. Abra Windows PowerShell y vaya a la carpeta en la que guardó el script.
    
3. Ejecutar el script; por ejemplo:
    
    ```
    .\CloneSearch.ps1
    ```

4. Cuando se le pidan sus credenciales, escriba su dirección de correo electrónico y contraseña y, a continuación, haga clic en **Aceptar**.
    
5. Escriba la información siguiente cuando se lo solicite el script. Escriba cada fragmento de información y, a continuación, presione **entrar**.
    
    - El nombre de la búsqueda existente.
    
    - Nombre de la nueva búsqueda.
    
    El script crea la nueva búsqueda de contenido, pero no la inicia. Esto le da la oportunidad de editar y ejecutar la búsqueda en el paso siguiente. Para ver las propiedades de la nueva búsqueda, ejecute el cmdlet **Get-ComplianceSearch** o vaya a la página de **búsqueda de contenido** o de **exhibición** de documentos electrónicos en el centro de cumplimiento, en función de si la nueva búsqueda está asociada a un caso o no. 
  
## <a name="step-2-edit-and-run-the-cloned-search-in-the-compliance-center"></a>Paso 2: editar y ejecutar la búsqueda clonada en el centro de cumplimiento

Una vez que haya ejecutado el script para clonar una búsqueda de contenido existente, el siguiente paso consiste en ir al centro de cumplimiento para editar y ejecutar la nueva búsqueda. Como se mencionó anteriormente, puede editar una búsqueda cambiando la consulta de búsqueda de palabras clave y agregando o quitando condiciones de búsqueda. Para más información, visite:
  
- [Búsqueda de contenido en Office 365](content-search.md)
    
- [Consultas de palabras clave y condiciones de búsqueda para la búsqueda de contenido](keyword-queries-and-search-conditions.md).
    
- [casos de eDiscovery](ediscovery-cases.md)
