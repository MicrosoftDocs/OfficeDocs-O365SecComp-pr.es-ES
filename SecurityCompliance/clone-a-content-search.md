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
# <a name="clone-a-content-search"></a><span data-ttu-id="8b1de-105">Clonar una búsqueda de contenido</span><span class="sxs-lookup"><span data-stu-id="8b1de-105">Clone a Content Search</span></span>

<span data-ttu-id="8b1de-106">La creación de una búsqueda de contenido en el centro de cumplimiento en Office 365 o Microsoft 365 que realiza búsquedas en muchos buzones o en sitios de SharePoint y OneDrive para la empresa puede tardar unos minutos.</span><span class="sxs-lookup"><span data-stu-id="8b1de-106">Creating a Content Search in the compliance center in Office 365 or Microsoft 365 that searches a lot of mailboxes or SharePoint and OneDrive for Business sites can take awhile.</span></span> <span data-ttu-id="8b1de-107">La especificación de los sitios que se van a buscar también puede provocar errores si se escribe Inde una dirección URL.</span><span class="sxs-lookup"><span data-stu-id="8b1de-107">Specifying the sites to search can also be prone to errors if you mistype a URL.</span></span> <span data-ttu-id="8b1de-108">Para evitar estos problemas, puede usar el script de Windows PowerShell de este artículo para clonar rápidamente una búsqueda de contenido existente.</span><span class="sxs-lookup"><span data-stu-id="8b1de-108">To avoid these issues, you can use the Windows PowerShell script in this article to quickly clone an existing Content Search.</span></span> <span data-ttu-id="8b1de-109">Cuando se clona una búsqueda, se crea una nueva búsqueda (con un nombre diferente) que contiene las mismas propiedades (como las ubicaciones de contenido y la consulta de búsqueda) como la búsqueda original.</span><span class="sxs-lookup"><span data-stu-id="8b1de-109">When a you clone a search, a new search (with a different name) is created that contains the same properties (such as the content locations and the search query) as the original search.</span></span> <span data-ttu-id="8b1de-110">A continuación, puede editar la nueva búsqueda (cambiando la palabra clave consulta o el intervalo de fechas) y ejecutarla.</span><span class="sxs-lookup"><span data-stu-id="8b1de-110">Then you can edit the new search (by changing the keyword query or the date range) and run it.</span></span>
  
<span data-ttu-id="8b1de-111">¿Por qué clonar búsquedas de contenido?</span><span class="sxs-lookup"><span data-stu-id="8b1de-111">Why clone Content Searches?</span></span>
  
- <span data-ttu-id="8b1de-112">Para comparar los resultados de las diferentes consultas de búsqueda de palabras clave que se ejecutan en las mismas ubicaciones de contenido.</span><span class="sxs-lookup"><span data-stu-id="8b1de-112">To compare the results of different keyword search queries run on the same content locations.</span></span>
    
- <span data-ttu-id="8b1de-113">Para evitar tener que volver a especificar un gran número de ubicaciones de contenido al crear una nueva búsqueda.</span><span class="sxs-lookup"><span data-stu-id="8b1de-113">To save you from having to re-enter a large number of content locations when you create a new search.</span></span>
    
- <span data-ttu-id="8b1de-114">Para reducir el tamaño de los resultados de la búsqueda; por ejemplo, si tiene una búsqueda que devuelve demasiados resultados para exportar, puede clonar la búsqueda y, a continuación, agregar una condición de búsqueda basada en un intervalo de fechas para reducir el número de resultados de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="8b1de-114">To decrease the size of the search results; for example, if you have a search that returns too many results to export, you can clone the search and then add a search condition based on a date range to reduce the number of search results.</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="8b1de-115">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="8b1de-115">Before you begin</span></span>

- <span data-ttu-id="8b1de-116">Debe ser miembro del grupo de roles eDiscovery Manager en el centro de seguridad & cumplimiento para ejecutar el script que se describe en este tema.</span><span class="sxs-lookup"><span data-stu-id="8b1de-116">You have to be a member of the eDiscovery Manager role group in the Security & Compliance Center to run the script described in this topic.</span></span>
    
- <span data-ttu-id="8b1de-117">El script incluye un tratamiento de errores mínimo.</span><span class="sxs-lookup"><span data-stu-id="8b1de-117">The script includes minimal error handling.</span></span> <span data-ttu-id="8b1de-118">El objetivo principal del script es clonar rápidamente una búsqueda de contenido.</span><span class="sxs-lookup"><span data-stu-id="8b1de-118">The primary purpose of the script is to quickly clone a content search.</span></span>
    
- <span data-ttu-id="8b1de-119">El script crea una nueva búsqueda de contenido, pero no la inicia.</span><span class="sxs-lookup"><span data-stu-id="8b1de-119">The script creates a new Content Search, but doesn't start it.</span></span>
    
- <span data-ttu-id="8b1de-120">Este script tiene en cuenta si la búsqueda de contenido que va a clonar está asociada a un caso de exhibición de documentos electrónicos.</span><span class="sxs-lookup"><span data-stu-id="8b1de-120">This script takes into account whether the Content Search that you're cloning is associated with an eDiscovery case.</span></span> <span data-ttu-id="8b1de-121">Si la búsqueda está asociada a un caso, la nueva búsqueda también se asociará con el mismo caso.</span><span class="sxs-lookup"><span data-stu-id="8b1de-121">If the search is associated with a case, the new search will also be associated with the same case.</span></span> <span data-ttu-id="8b1de-122">Si la búsqueda existente no está asociada a un caso, la nueva búsqueda se enumerará en la página **búsqueda de contenido** en el centro de cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="8b1de-122">If the existing search isn't associated with a case, the new search will be listed on the **Content search** page in the compliance center.</span></span> 
    
- <span data-ttu-id="8b1de-123">La secuencia de comandos de ejemplo proporcionada en este tema no es compatible con ningún servicio o programa de soporte estándar de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="8b1de-123">The sample script provided in this topic isn't supported under any Microsoft standard support program or service.</span></span> <span data-ttu-id="8b1de-124">El script de ejemplo se proporciona tal cual sin garantías de ningún tipo.</span><span class="sxs-lookup"><span data-stu-id="8b1de-124">The sample script is provided AS IS without warranty of any kind.</span></span> <span data-ttu-id="8b1de-125">Además, Microsoft no se hace responsable de cualquier garantía implícita, incluyendo, de manera enunciativa pero no limitativa, cualquier garantía implícita de comercialización o de calidad para cualquier propósito.</span><span class="sxs-lookup"><span data-stu-id="8b1de-125">Microsoft further disclaims all implied warranties including, without limitation, any implied warranties of merchantability or of fitness for a particular purpose.</span></span> <span data-ttu-id="8b1de-126">Todo el riesgo derivado del uso o el rendimiento de la secuencia de comandos de muestra y la documentación se conservan con usted.</span><span class="sxs-lookup"><span data-stu-id="8b1de-126">The entire risk arising out of the use or performance of the sample script and documentation remains with you.</span></span> <span data-ttu-id="8b1de-127">En ningún caso Microsoft, sus autores o cualquier persona involucrada en su creación, producción o entrega de los scripts será responsable de cualquier daño (incluidos, de manera enunciativa pero no limitativa, daños por pérdidas de beneficios de una empresa, interrupción de la actividad de una empresa, pérdidas de información de una empresa, o cualquier otro daño pecuniario), incluso si Microsoft supiera de la posibilidad de tales daños.</span><span class="sxs-lookup"><span data-stu-id="8b1de-127">In no event shall Microsoft, its authors, or anyone else involved in the creation, production, or delivery of the scripts be liable for any damages whatsoever (including, without limitation, damages for loss of business profits, business interruption, loss of business information, or other pecuniary loss) arising out of the use of or inability to use the sample scripts or documentation, even if Microsoft has been advised of the possibility of such damages.</span></span>
  
## <a name="step-1-run-the-script-to-clone-a-search"></a><span data-ttu-id="8b1de-128">Paso 1: ejecutar el script para clonar una búsqueda</span><span class="sxs-lookup"><span data-stu-id="8b1de-128">Step 1: Run the script to clone a search</span></span>

<span data-ttu-id="8b1de-129">El script de este paso creará una nueva búsqueda de contenido mediante la clonación de una existente.</span><span class="sxs-lookup"><span data-stu-id="8b1de-129">The script in this step will create a new Content Search by cloning an existing one.</span></span> <span data-ttu-id="8b1de-130">Al ejecutar este script, se le pedirá la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="8b1de-130">When you run this script, you'll be prompted for the following information:</span></span>
  
- <span data-ttu-id="8b1de-131">**Sus credenciales de usuario** : el script usará sus credenciales para conectarse al centro de seguridad & cumplimiento de la organización de Office 365 con Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8b1de-131">**Your user credentials** - The script will use your credentials to connect to the Security & Compliance Center for your Office 365 organization with Windows PowerShell.</span></span> <span data-ttu-id="8b1de-132">Como se mencionó anteriormente, tiene que ser miembro del grupo de roles eDiscovery Manager en el centro de seguridad & compCompliance para ejecutar el script.</span><span class="sxs-lookup"><span data-stu-id="8b1de-132">As previously stated, you have to be a member of the eDiscovery Manager role group in the Security & compCompliance Center to run the script.</span></span> 
    
- <span data-ttu-id="8b1de-133">**El nombre de la búsqueda existente** : es la búsqueda de contenido que desea clonar.</span><span class="sxs-lookup"><span data-stu-id="8b1de-133">**The name of the existing search** - This is the Content Search that you want to clone.</span></span> 
    
- <span data-ttu-id="8b1de-134">**El nombre de la nueva búsqueda que** se creará; si deja este valor en blanco, el script creará un nombre para la nueva búsqueda que se basa en el nombre de la búsqueda que va a clonar.</span><span class="sxs-lookup"><span data-stu-id="8b1de-134">**The name of the new search that will be created** - If you leave this value blank, the script will create a name for the new search that is based on the name of the search that you're cloning.</span></span> 
    
<span data-ttu-id="8b1de-135">Para clonar una búsqueda:</span><span class="sxs-lookup"><span data-stu-id="8b1de-135">To clone a search:</span></span>
  
1. <span data-ttu-id="8b1de-136">Guarde el siguiente texto en un archivo de script de Windows PowerShell mediante un sufijo de nombre de archivo de. ps1; por ejemplo, `CloneSearch.ps1`.</span><span class="sxs-lookup"><span data-stu-id="8b1de-136">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `CloneSearch.ps1`.</span></span>
    
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

2. <span data-ttu-id="8b1de-137">Abra Windows PowerShell y vaya a la carpeta en la que guardó el script.</span><span class="sxs-lookup"><span data-stu-id="8b1de-137">Open Windows PowerShell and go to the folder where you saved the script.</span></span>
    
3. <span data-ttu-id="8b1de-138">Ejecutar el script; por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="8b1de-138">Run the script; for example:</span></span>
    
    ```
    .\CloneSearch.ps1
    ```

4. <span data-ttu-id="8b1de-139">Cuando se le pidan sus credenciales, escriba su dirección de correo electrónico y contraseña y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="8b1de-139">When prompted for your credentials, enter your email address and password, and then click **OK**.</span></span>
    
5. <span data-ttu-id="8b1de-140">Escriba la información siguiente cuando se lo solicite el script.</span><span class="sxs-lookup"><span data-stu-id="8b1de-140">Enter following information when prompted by the script.</span></span> <span data-ttu-id="8b1de-141">Escriba cada fragmento de información y, a continuación, presione **entrar**.</span><span class="sxs-lookup"><span data-stu-id="8b1de-141">Type each piece of information and then press **Enter**.</span></span>
    
    - <span data-ttu-id="8b1de-142">El nombre de la búsqueda existente.</span><span class="sxs-lookup"><span data-stu-id="8b1de-142">The name of the existing search.</span></span>
    
    - <span data-ttu-id="8b1de-143">Nombre de la nueva búsqueda.</span><span class="sxs-lookup"><span data-stu-id="8b1de-143">The name of the new search.</span></span>
    
    <span data-ttu-id="8b1de-144">El script crea la nueva búsqueda de contenido, pero no la inicia.</span><span class="sxs-lookup"><span data-stu-id="8b1de-144">The script creates the new Content Search, but doesn't start it.</span></span> <span data-ttu-id="8b1de-145">Esto le da la oportunidad de editar y ejecutar la búsqueda en el paso siguiente.</span><span class="sxs-lookup"><span data-stu-id="8b1de-145">This gives you a chance to edit and run the search in the next step.</span></span> <span data-ttu-id="8b1de-146">Para ver las propiedades de la nueva búsqueda, ejecute el cmdlet **Get-ComplianceSearch** o vaya a la página de **búsqueda de contenido** o de **exhibición** de documentos electrónicos en el centro de cumplimiento, en función de si la nueva búsqueda está asociada a un caso o no.</span><span class="sxs-lookup"><span data-stu-id="8b1de-146">You can view the properties of the new search by running the **Get-ComplianceSearch** cmdlet or by going to the **Content search** or **eDiscovery** page in the compliance center, depending on whether or not the new search is associated with a case.</span></span> 
  
## <a name="step-2-edit-and-run-the-cloned-search-in-the-compliance-center"></a><span data-ttu-id="8b1de-147">Paso 2: editar y ejecutar la búsqueda clonada en el centro de cumplimiento</span><span class="sxs-lookup"><span data-stu-id="8b1de-147">Step 2: Edit and run the cloned search in the compliance center</span></span>

<span data-ttu-id="8b1de-148">Una vez que haya ejecutado el script para clonar una búsqueda de contenido existente, el siguiente paso consiste en ir al centro de cumplimiento para editar y ejecutar la nueva búsqueda.</span><span class="sxs-lookup"><span data-stu-id="8b1de-148">After the you've run the script to clone an existing Content Search, the next step is to go to the compliance center to edit and run the new search.</span></span> <span data-ttu-id="8b1de-149">Como se mencionó anteriormente, puede editar una búsqueda cambiando la consulta de búsqueda de palabras clave y agregando o quitando condiciones de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="8b1de-149">As previously stated, you can edit a search by changing the keyword search query and adding or removing search conditions.</span></span> <span data-ttu-id="8b1de-150">Para más información, visite:</span><span class="sxs-lookup"><span data-stu-id="8b1de-150">For more information, see:</span></span>
  
- [<span data-ttu-id="8b1de-151">Búsqueda de contenido en Office 365</span><span class="sxs-lookup"><span data-stu-id="8b1de-151">Content Search in Office 365</span></span>](content-search.md)
    
- <span data-ttu-id="8b1de-152">[Consultas de palabras clave y condiciones de búsqueda para la búsqueda de contenido](keyword-queries-and-search-conditions.md).</span><span class="sxs-lookup"><span data-stu-id="8b1de-152">[Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md)</span></span>
    
- [<span data-ttu-id="8b1de-153">casos de eDiscovery</span><span class="sxs-lookup"><span data-stu-id="8b1de-153">eDiscovery cases</span></span>](ediscovery-cases.md)
