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
# <a name="clone-a-content-search-in-the-office-365-security-amp-compliance-center"></a><span data-ttu-id="9f368-105">Clonación de una búsqueda de contenido en la seguridad de Office 365 &amp; centro de cumplimiento</span><span class="sxs-lookup"><span data-stu-id="9f368-105">Clone a Content Search in the Office 365 Security &amp; Compliance Center</span></span>

<span data-ttu-id="9f368-p102">Creación de una búsqueda de contenido en Office 365 seguridad &amp; centro de cumplimiento que busca una gran cantidad de buzones de correo o de SharePoint y OneDrive para sitios de negocio pueden tardar unos minutos. Especificación de los sitios para buscar también puede ser propensa a errores si se escribe mal una dirección URL. Para evitar estos problemas, puede usar la secuencia de comandos de Windows PowerShell en este artículo para clonar rápidamente una búsqueda de contenido existente. Al clonar una búsqueda, se crea una nueva búsqueda (con un nombre diferente) que contiene las mismas propiedades (por ejemplo, las ubicaciones de contenido y la consulta de búsqueda) que la búsqueda original. A continuación, puede editar la nueva búsqueda (cambiando la consulta de palabra clave o el intervalo de fechas) y ejecútelo.</span><span class="sxs-lookup"><span data-stu-id="9f368-p102">Creating a Content Search in Office 365 Security &amp; Compliance Center that searches a lot of mailboxes or SharePoint and OneDrive for Business sites can take awhile. Specifying the sites to search can also be prone to errors if you mistype a URL. To avoid these issues, you can use the Windows PowerShell script in this article to quickly clone an existing Content Search. When a you clone a search, a new search (with a different name) is created that contains the same properties (such as the content locations and the search query) as the original search. Then you can edit the new search (by changing the keyword query or the date range) and run it.</span></span>
  
<span data-ttu-id="9f368-111">¿Por qué clonar búsquedas de contenido?</span><span class="sxs-lookup"><span data-stu-id="9f368-111">Why clone Content Searches?</span></span>
  
- <span data-ttu-id="9f368-112">Para comparar los resultados de la palabra clave diferente ejecutar consultas de búsqueda en las mismas ubicaciones de contenido.</span><span class="sxs-lookup"><span data-stu-id="9f368-112">To compare the results of different keyword search queries run on the same content locations.</span></span>
    
- <span data-ttu-id="9f368-113">Para que se evitará tener que volver a escribir un gran número de ubicaciones de contenido cuando se crea una nueva búsqueda.</span><span class="sxs-lookup"><span data-stu-id="9f368-113">To save you from having to re-enter a large number of content locations when you create a new search.</span></span>
    
- <span data-ttu-id="9f368-114">Para reducir el tamaño de los resultados de búsqueda; Por ejemplo, si dispone de una búsqueda que devuelve demasiados resultados para exportar, puede clonar la búsqueda y, a continuación, agregue una condición de búsqueda en función de un intervalo de fechas para reducir el número de resultados de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="9f368-114">To decrease the size of the search results; for example, if you have a search that returns too many results to export, you can clone the search and then add a search condition based on a date range to reduce the number of search results.</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="9f368-115">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="9f368-115">Before you begin</span></span>

- <span data-ttu-id="9f368-116">Tiene que ser un miembro del grupo de roles de administrador de exhibición de documentos electrónicos en la seguridad &amp; centro de cumplimiento para ejecutar la secuencia de comandos que se describen en este tema.</span><span class="sxs-lookup"><span data-stu-id="9f368-116">You have to be a member of the eDiscovery Manager role group in the Security &amp; Compliance Center to run the script described in this topic.</span></span>
    
- <span data-ttu-id="9f368-p103">La secuencia de comandos incluye el tratamiento de errores mínima. El propósito principal de la secuencia de comandos es clonar rápidamente una búsqueda de contenido.</span><span class="sxs-lookup"><span data-stu-id="9f368-p103">The script includes minimal error handling. The primary purpose of the script is to quickly clone a content search.</span></span>
    
- <span data-ttu-id="9f368-119">La secuencia de comandos crea una nueva búsqueda de contenido, pero no la inicia.</span><span class="sxs-lookup"><span data-stu-id="9f368-119">The script creates a new Content Search, but doesn't start it.</span></span>
    
- <span data-ttu-id="9f368-p104">Esta secuencia de comandos tiene en cuenta si la búsqueda de contenido que está clonando está asociada a un caso de exhibición de documentos electrónicos. Si la búsqueda está asociada con un caso, la nueva búsqueda también se asociarán con el mismo caso. Si la búsqueda existente no está asociada a un caso, la nueva búsqueda aparecerán en la página de **búsqueda de contenido** en la seguridad &amp; centro de cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="9f368-p104">This script takes into account whether the Content Search that you're cloning is associated with an eDiscovery case. If the search is associated with a case, the new search will also be associated with the same case. If the existing search isn't associated with a case, the new search will be listed on the **Content search** page in the Security &amp; Compliance Center.</span></span> 
    
- <span data-ttu-id="9f368-p105">El script de ejemplo proporcionado en este tema no es compatible con ningún servicio o programa de soporte estándar de Microsoft. El script de ejemplo se proporciona tal cual sin garantía de ningún tipo. Microsoft renuncia a todas las garantías implícitas incluidas, sin limitación, cualquier las garantías implícitas de comerciabilidad o de idoneidad para un fin determinado. Todo el riesgo que pueda surgir por el uso o el rendimiento de la secuencia de comandos de ejemplo y documentación permanece con usted. En ningún caso Microsoft, sus autores o cualquier otro implicado en la creación, producción o entrega de las secuencias de comandos serán responsables de los daños índole (incluidos, pero sin limitarse a, daños por pérdida de beneficios empresariales, interrupción del negocio, pérdida de información de la empresa, o en otras pérdidas de carácter económico) derivado del uso o la incapacidad de usar los scripts de ejemplo o documentación, aunque Microsoft haya sido notificado de la posibilidad de dichos daños.</span><span class="sxs-lookup"><span data-stu-id="9f368-p105">The sample script provided in this topic isn't supported under any Microsoft standard support program or service. The sample script is provided AS IS without warranty of any kind. Microsoft further disclaims all implied warranties including, without limitation, any implied warranties of merchantability or of fitness for a particular purpose. The entire risk arising out of the use or performance of the sample script and documentation remains with you. In no event shall Microsoft, its authors, or anyone else involved in the creation, production, or delivery of the scripts be liable for any damages whatsoever (including, without limitation, damages for loss of business profits, business interruption, loss of business information, or other pecuniary loss) arising out of the use of or inability to use the sample scripts or documentation, even if Microsoft has been advised of the possibility of such damages.</span></span>
  
## <a name="step-1-run-the-script-to-clone-a-search"></a><span data-ttu-id="9f368-128">Paso 1: Ejecute el script para clonar una búsqueda</span><span class="sxs-lookup"><span data-stu-id="9f368-128">Step 1: Run the script to clone a search</span></span>

<span data-ttu-id="9f368-p106">La secuencia de comandos en este paso creará una nueva búsqueda de contenido mediante la clonación de uno existente. Al ejecutar este script, se le pedirá la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="9f368-p106">The script in this step will create a new Content Search by cloning an existing one. When you run this script, you'll be prompted for the following information:</span></span>
  
- <span data-ttu-id="9f368-p107">**Sus credenciales de usuario** : la secuencia de comandos usará las credenciales para conectarse a la seguridad &amp; centro de cumplimiento de normas de la organización de Office 365 con Windows PowerShell. Como se mencionó anteriormente, tiene que ser un miembro del grupo de roles de administrador de exhibición de documentos electrónicos en la seguridad &amp; centro de cumplimiento para ejecutar el script.</span><span class="sxs-lookup"><span data-stu-id="9f368-p107">**Your user credentials** - The script will use your credentials to connect to the Security &amp; Compliance Center for your Office 365 organization with Windows PowerShell. As previously stated, you have to be a member of the eDiscovery Manager role group in the Security &amp; Compliance Center to run the script.</span></span> 
    
- <span data-ttu-id="9f368-133">**El nombre de la búsqueda existente** - se trata de la búsqueda de contenido que va a clonar.</span><span class="sxs-lookup"><span data-stu-id="9f368-133">**The name of the existing search** - This is the Content Search that you want to clone.</span></span> 
    
- <span data-ttu-id="9f368-134">**El nombre de la nueva búsqueda que se crearán** - si deja este valor en blanco, la secuencia de comandos creará un nombre para la búsqueda nuevo que se basa en el nombre de la búsqueda que está clonando.</span><span class="sxs-lookup"><span data-stu-id="9f368-134">**The name of the new search that will be created** - If you leave this value blank, the script will create a name for the new search that is based on the name of the search that you're cloning.</span></span> 
    
<span data-ttu-id="9f368-135">Para clonar una búsqueda:</span><span class="sxs-lookup"><span data-stu-id="9f368-135">To clone a search:</span></span>
  
1. <span data-ttu-id="9f368-136">Guarde el siguiente texto en un archivo de secuencia de comandos de Windows PowerShell mediante el uso de un sufijo de nombre de archivo de. ps1; Por ejemplo, `CloneSearch.ps1`.</span><span class="sxs-lookup"><span data-stu-id="9f368-136">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `CloneSearch.ps1`.</span></span>
    
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

2. <span data-ttu-id="9f368-137">Abra Windows PowerShell y vaya a la carpeta donde guardó la secuencia de comandos.</span><span class="sxs-lookup"><span data-stu-id="9f368-137">Open Windows PowerShell and go to the folder where you saved the script.</span></span>
    
3. <span data-ttu-id="9f368-138">Ejecute la secuencia de comandos; Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="9f368-138">Run the script; for example:</span></span>
    
    ```
    .\CloneSearch.ps1
    ```

4. <span data-ttu-id="9f368-139">Cuando se le pidan sus credenciales, escriba su dirección de correo electrónico y contraseña y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="9f368-139">When prompted for your credentials, enter your email address and password, and then click **OK**.</span></span>
    
5. <span data-ttu-id="9f368-p108">Escriba la siguiente información cuando se le solicite la secuencia de comandos. Escriba cada parte de la información y, a continuación, presione **ENTRAR**.</span><span class="sxs-lookup"><span data-stu-id="9f368-p108">Enter following information when prompted by the script. Type each piece of information and then press **Enter**.</span></span>
    
    - <span data-ttu-id="9f368-142">El nombre de la búsqueda existente.</span><span class="sxs-lookup"><span data-stu-id="9f368-142">The name of the existing search.</span></span>
    
    - <span data-ttu-id="9f368-143">El nombre de la búsqueda nuevo.</span><span class="sxs-lookup"><span data-stu-id="9f368-143">The name of the new search.</span></span>
    
    <span data-ttu-id="9f368-p109">La secuencia de comandos crea la búsqueda de contenido nuevo, pero no la inicia. Esto le ofrece una oportunidad para editar y ejecutar la búsqueda en el paso siguiente. Puede ver las propiedades de la nueva búsqueda ejecutando el cmdlet **Get-ComplianceSearch** o yendo a la página de **búsqueda de contenido** o de **exhibición de documentos electrónicos** en la seguridad &amp; centro de cumplimiento, dependiendo de si está o no la búsqueda nuevo asociarse a un caso.</span><span class="sxs-lookup"><span data-stu-id="9f368-p109">The script creates the new Content Search, but doesn't start it. This gives you a chance to edit and run the search in the next step. You can view the properties of the new search by running the **Get-ComplianceSearch** cmdlet or by going to the **Content search** or **eDiscovery** page in the Security &amp; Compliance Center, depending on whether or not the new search is associated with a case.</span></span> 
  
## <a name="step-2-edit-and-run-the-cloned-search-in-the-security-amp-compliance-center"></a><span data-ttu-id="9f368-147">Paso 2: Editar y ejecutar la búsqueda clonada en la seguridad &amp; centro de cumplimiento</span><span class="sxs-lookup"><span data-stu-id="9f368-147">Step 2: Edit and run the cloned search in the Security &amp; Compliance Center</span></span>

<span data-ttu-id="9f368-p110">Después de la que ha ejecutado la secuencia de comandos que se debe clonar una búsqueda de contenido existente, el siguiente paso es ir a la seguridad &amp; centro de cumplimiento para editar y ejecutar la búsqueda nuevo. Como se mencionó anteriormente, puede editar una búsqueda cambiando la consulta de búsqueda de palabra clave y agregar o quitar las condiciones de búsqueda. Para obtener más información, vea:</span><span class="sxs-lookup"><span data-stu-id="9f368-p110">After the you've run the script to clone an existing Content Search, the next step is to go to the Security &amp; Compliance Center to edit and run the new search. As previously stated, you can edit a search by changing the keyword search query and adding or removing search conditions. For more information, see:</span></span>
  
- [<span data-ttu-id="9f368-151">Búsqueda de contenido en Office 365</span><span class="sxs-lookup"><span data-stu-id="9f368-151">Content Search in Office 365</span></span>](content-search.md)
    
- <span data-ttu-id="9f368-152">[Consultas de palabras clave y condiciones de búsqueda para la búsqueda de contenido](keyword-queries-and-search-conditions.md).</span><span class="sxs-lookup"><span data-stu-id="9f368-152">[Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md)</span></span>
    
- [<span data-ttu-id="9f368-153">casos de exhibición de documentos electrónicos en la seguridad de Office 365 &amp; centro de cumplimiento</span><span class="sxs-lookup"><span data-stu-id="9f368-153">eDiscovery cases in the Office 365 Security &amp; Compliance Center</span></span>](ediscovery-cases.md)
