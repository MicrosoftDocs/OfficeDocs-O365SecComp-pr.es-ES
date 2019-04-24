---
title: Usar Búsqueda de contenido en el flujo de trabajo de eDiscovery
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 12/30/2016
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 55f31488-288a-473a-9b9e-831a11e3711a
description: 'Use un script de PowerShell para crear una búsqueda de exhibición de documentos electrónicos local en Exchange online en función de una búsqueda creada en el centro de seguridad & cumplimiento. '
ms.openlocfilehash: 2e4f1b3570ce2400472a0b2a9ddee886ffc4bab3
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32263802"
---
# <a name="use-content-search-in-your-ediscovery-workflow"></a><span data-ttu-id="f10fa-103">Usar Búsqueda de contenido en el flujo de trabajo de eDiscovery</span><span class="sxs-lookup"><span data-stu-id="f10fa-103">Use Content Search in your eDiscovery workflow</span></span>

<span data-ttu-id="f10fa-104">La característica de búsqueda de contenido en el centro de seguridad & cumplimiento permite buscar en todos los buzones de la organización.</span><span class="sxs-lookup"><span data-stu-id="f10fa-104">The Content Search feature in the Security & Compliance Center allows you to search all mailboxes in your organization.</span></span> <span data-ttu-id="f10fa-105">A diferencia de la exhibición de documentos electrónicos local en Exchange Online (donde puede buscar hasta 10.000 buzones), no hay límites para el número de buzones de destino en una sola búsqueda.</span><span class="sxs-lookup"><span data-stu-id="f10fa-105">Unlike In-Place eDiscovery in Exchange Online (where you can search up to 10,000 mailboxes), there are no limits for the number of target mailboxes in a single search.</span></span> <span data-ttu-id="f10fa-106">En los escenarios en los que necesite realizar búsquedas en toda la organización, puede usar Búsqueda de contenido para buscar en todos los buzones.</span><span class="sxs-lookup"><span data-stu-id="f10fa-106">For scenarios that require you to perform organization-wide searches, you can use Content Search to search all mailboxes.</span></span> <span data-ttu-id="f10fa-107">A continuación, puede usar las características de flujo de trabajo de exhibición de documentos electrónicos local para realizar otras tareas relacionadas con la exhibición de documentos electrónicos, como colocar buzones en suspensión y exportar resultados de la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="f10fa-107">Then you can use the workflow features of In-Place eDiscovery to perform other eDiscovery-related tasks, such as placing mailboxes on hold and exporting search results.</span></span> <span data-ttu-id="f10fa-108">Por ejemplo, supongamos que tiene que buscar en todos los buzones para identificar administradores específicos que responden a un caso jurídico.</span><span class="sxs-lookup"><span data-stu-id="f10fa-108">For example, let's say you have to search all mailboxes to identify specific custodians that are responsive to a legal case.</span></span> <span data-ttu-id="f10fa-109">Puede usar la búsqueda de contenido en el centro de seguridad & cumplimiento para buscar en todos los buzones de la organización para identificar los que responden al caso.</span><span class="sxs-lookup"><span data-stu-id="f10fa-109">You can use Content Search in the Security & Compliance Center to search all mailboxes in your organization to identify those that are responsive to the case.</span></span> <span data-ttu-id="f10fa-110">A continuación, puede usar esa lista de buzones de correo de custodios como buzones de origen para una búsqueda de exhibición de documentos electrónicos local en Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="f10fa-110">Then you can use that list of custodian mailboxes as the source mailboxes for an In-Place eDiscovery search in Exchange Online.</span></span> <span data-ttu-id="f10fa-111">El uso de la exhibición de documentos electrónicos local también permite poner en suspensión dichos buzones de origen, copiar los resultados de la búsqueda en un buzón de correo de detección y exportar los resultados de la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="f10fa-111">Using In-Place eDiscovery also allows you to put a hold on those source mailboxes, copy search results to a discovery mailbox, and export the search results.</span></span>
  
<span data-ttu-id="f10fa-112">En este tema se incluye un script que puede ejecutar para crear una búsqueda de exhibición de documentos electrónicos local en Exchange Online usando la lista de buzones de origen y la consulta de búsqueda de una búsqueda creada en el centro de seguridad & cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="f10fa-112">This topic includes a script that you can run to create an In-Place eDiscovery search in Exchange Online by using the list of source mailboxes and search query from a search created in the Security & Compliance Center.</span></span> <span data-ttu-id="f10fa-113">A continuación encontrará una descripción general del proceso:</span><span class="sxs-lookup"><span data-stu-id="f10fa-113">Here's an overview of the process:</span></span>
  
[<span data-ttu-id="f10fa-114">Paso 1: Crear una Búsqueda de contenido para todos los buzones de la organización</span><span class="sxs-lookup"><span data-stu-id="f10fa-114">Step 1: Create a Content Search to search all mailboxes in your organization</span></span>](#step-1-create-a-content-search-to-search-all-mailboxes-in-your-organization)

[<span data-ttu-id="f10fa-115">Paso 2: conectarse al centro de \& seguridad y cumplimiento y a Exchange online en una única sesión de PowerShell en remoto</span><span class="sxs-lookup"><span data-stu-id="f10fa-115">Step 2: Connect to the Security \& Compliance Center and Exchange Online in a single remote PowerShell session</span></span>](#step-2-connect-to-the-security--compliance-center-and-exchange-online-in-a-single-remote-powershell-session)
  
[<span data-ttu-id="f10fa-116">Paso 3: Ejecutar el script para crear una búsqueda de eDiscovery local a partir de la búsqueda de contenido</span><span class="sxs-lookup"><span data-stu-id="f10fa-116">Step 3: Run the script to create an In-Place eDiscovery search from the Content Search</span></span>](#step-3-run-the-script-to-create-an-in-place-ediscovery-search-from-the-content-search)

[<span data-ttu-id="f10fa-117">Step 4: Start the In-Place eDiscovery search</span><span class="sxs-lookup"><span data-stu-id="f10fa-117">Step 4: Start the In-Place eDiscovery search</span></span>](#step-4-start-the-in-place-ediscovery-search)

## <a name="step-1-create-a-content-search-to-search-all-mailboxes-in-your-organization"></a><span data-ttu-id="f10fa-118">Paso 1: Crear una Búsqueda de contenido para todos los buzones de la organización</span><span class="sxs-lookup"><span data-stu-id="f10fa-118">Step 1: Create a Content Search to search all mailboxes in your organization</span></span>

<span data-ttu-id="f10fa-119">El primer paso consiste en usar el centro de seguridad & cumplimiento (o PowerShell de & de seguridad del centro de cumplimiento) para crear una búsqueda de contenido que busque en todos los buzones de la organización.</span><span class="sxs-lookup"><span data-stu-id="f10fa-119">The first step is to use the Security & Compliance Center (or Security & Compliance Center PowerShell) to create a Content Search that searches all mailboxes in your organization.</span></span> <span data-ttu-id="f10fa-120">No existe un límite para el número de buzones de una búsqueda de contenido.</span><span class="sxs-lookup"><span data-stu-id="f10fa-120">There's no limit for the number of mailboxes for a single Content Search.</span></span> <span data-ttu-id="f10fa-121">Especifique una consulta de palabras clave adecuada (o una consulta de los tipos de información confidencial) para que la búsqueda devuelva solo los buzones de origen relevantes para la investigación.</span><span class="sxs-lookup"><span data-stu-id="f10fa-121">Specify an appropriate keyword query (or a query for sensitive information types) so that the search returns only those source mailboxes that are relevant to your investigation.</span></span> <span data-ttu-id="f10fa-122">Si es necesario, restrinja la consulta de búsqueda para limitar el ámbito de los resultados de la búsqueda y los buzones de origen devueltos.</span><span class="sxs-lookup"><span data-stu-id="f10fa-122">If necessary, refine the search query to narrow the scope of search results and source mailboxes that are returned.</span></span>
  
> [!NOTE]
> <span data-ttu-id="f10fa-p104">Si la búsqueda de contenido de origen no devuelve ningún resultado, no se creará un eDiscovery local al ejecutar el script en el paso 3. Revise la consulta de búsqueda y, después, vuelva a ejecutar la búsqueda de contenido para mostrar los resultados de la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="f10fa-p104">If the source Content Search doesn't return any results, an In-Place eDiscovery won't be created when you run the script in Step 3. You may have to revise the search query then rerun the Content Search to return search results.</span></span> 
  
### <a name="use-the-security--compliance-center-to-search-all-mailboxes"></a><span data-ttu-id="f10fa-125">Usar el Centro de seguridad y cumplimiento para buscar en todos los buzones</span><span class="sxs-lookup"><span data-stu-id="f10fa-125">Use the Security & Compliance Center to search all mailboxes</span></span>

1. <span data-ttu-id="f10fa-126">[Vaya al centro de seguridad _AMP_ cumplimiento](go-to-the-securitycompliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="f10fa-126">[Go to the Security & Compliance Center](go-to-the-securitycompliance-center.md).</span></span> 
    
2. <span data-ttu-id="f10fa-127"> > Haga \*\*\*\* clic en buscar*\*contenido*\*búsqueda y, a continuación, haga clic en *\*nuevo** ![icono](media/O365-MDM-CreatePolicy-AddIcon.gif)agregar nuevo.</span><span class="sxs-lookup"><span data-stu-id="f10fa-127">Click **Search** > **Content search**, and then click **New search** ![Add icon](media/O365-MDM-CreatePolicy-AddIcon.gif).</span></span>
    
3. <span data-ttu-id="f10fa-128">En la página **Nueva búsqueda**, escriba un nombre para la búsqueda de contenido.</span><span class="sxs-lookup"><span data-stu-id="f10fa-128">On the **New search** page, type a name for the Content Search.</span></span> 
    
4. <span data-ttu-id="f10fa-129">En **¿Dónde desea buscar?**, haga clic en **Buscar en todos los buzones** y, a continuación, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="f10fa-129">Under **Where do you want us to look?**, click **Search all mailboxes**, and then click **Next**.</span></span>
    
5. <span data-ttu-id="f10fa-130">En **¿Qué desea buscar?**, escriba una consulta de búsqueda en el cuadro.</span><span class="sxs-lookup"><span data-stu-id="f10fa-130">In the box under **What do you want us to look for?**, type a search query in the box.</span></span> <span data-ttu-id="f10fa-131">Puede especificar palabras clave, propiedades del mensaje como la fecha de envío y de recepción, o propiedades del documento como nombres de archivo o la fecha de la última modificación de un documento.</span><span class="sxs-lookup"><span data-stu-id="f10fa-131">You can specify keywords, message properties such as sent and received dates, or document properties such as file names or the date that a document was last changed.</span></span> <span data-ttu-id="f10fa-132">Puede usar consultas más complejas que usen un operador booleano, como AND, OR, NOT o NEAR, o también puede buscar información confidencial (por ejemplo, los números de la seguridad social) en los mensajes.</span><span class="sxs-lookup"><span data-stu-id="f10fa-132">You can use a more complex queries that use a Boolean operator, such as AND, OR, NOT or NEAR, or you can also search for sensitive information (such as social security numbers) in messages.</span></span> <span data-ttu-id="f10fa-133">Para obtener más información acerca de cómo crear consultas de búsqueda, consulte [Keyword queries for Content Search](keyword-queries-and-search-conditions.md).</span><span class="sxs-lookup"><span data-stu-id="f10fa-133">For more information about creating search queries, see [Keyword queries for Content Search](keyword-queries-and-search-conditions.md).</span></span>
    
6. <span data-ttu-id="f10fa-134">Haga clic en **Búsqueda** para guardar la configuración de la búsqueda e iniciar la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="f10fa-134">Click **Search** to save the search settings and start the search.</span></span> 
    
    <span data-ttu-id="f10fa-135">Después de un rato, una estimación de los resultados de la búsqueda que se muestran en el panel de detalles.</span><span class="sxs-lookup"><span data-stu-id="f10fa-135">After a while, an estimate of the search results displayed in the details pane.</span></span> <span data-ttu-id="f10fa-136">La estimación incluye el tamaño total y el número de elementos de los resultados de la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="f10fa-136">The estimate includes the total size and number of items for the search results.</span></span> <span data-ttu-id="f10fa-137">Una vez finalizada la búsqueda, puede obtener una vista previa de los resultados de la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="f10fa-137">After the search is completed, you can preview the search results.</span></span> <span data-ttu-id="f10fa-138">Si es necesario, \*\*\*\*![haga clic en](media/O365-MDM-Policy-RefreshIcon.gif) actualizar icono de actualización para actualizar la información en el panel de detalles.</span><span class="sxs-lookup"><span data-stu-id="f10fa-138">If necessary, click **Refresh**![Refresh icon](media/O365-MDM-Policy-RefreshIcon.gif) to update the information in the details pane.</span></span> 
    
7.  <span data-ttu-id="f10fa-139">Si es necesario, refine la consulta de búsqueda para restringir el alcance de los resultados de la búsqueda y, a continuación, reinicie la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="f10fa-139">If necessary, refine the search query to narrow the scope of search results and then restart the search.</span></span> 
    
### <a name="use-security--compliance-center-powershell-to-search-all-mailboxes"></a><span data-ttu-id="f10fa-140">Usar el centro de seguridad & PowerShell para buscar en todos los buzones</span><span class="sxs-lookup"><span data-stu-id="f10fa-140">Use Security & Compliance Center PowerShell to search all mailboxes</span></span>

<span data-ttu-id="f10fa-141">También puede usar el cmdlet **New-ComplianceSearch** para buscar en todos los buzones de la organización.</span><span class="sxs-lookup"><span data-stu-id="f10fa-141">You can also use the **New-ComplianceSearch** cmdlet to search all mailboxes in your organization.</span></span> <span data-ttu-id="f10fa-142">El primer paso consiste en [conectar con el PowerShell del centro de cumplimiento de & de seguridad](https://go.microsoft.com/fwlink/p/?LinkID=627084).</span><span class="sxs-lookup"><span data-stu-id="f10fa-142">The first step is to [Connect to Security & Compliance Center PowerShell](https://go.microsoft.com/fwlink/p/?LinkID=627084).</span></span>
  
<span data-ttu-id="f10fa-143">Este es un ejemplo del uso de PowerShell para buscar en todos los buzones de la organización.</span><span class="sxs-lookup"><span data-stu-id="f10fa-143">Here's an example of using PowerShell to search all mailboxes in your organization.</span></span> <span data-ttu-id="f10fa-144">La consulta de búsqueda devuelve todos los mensajes enviados entre el 1 de enero de 2015 y el 30 de junio de 2015 y que contienen la frase "informe financiero" en la línea del asunto.</span><span class="sxs-lookup"><span data-stu-id="f10fa-144">The search query returns all messages sent between January 1, 2015 and June 30, 2015 and that contain the phrase "financial report" in the subject line.</span></span> <span data-ttu-id="f10fa-145">El primer comando crea la búsqueda y el segundo comando la ejecuta.</span><span class="sxs-lookup"><span data-stu-id="f10fa-145">The first command creates the search, and the second command runs the search.</span></span> 
  
```
New-ComplianceSearch -Name "Search All-Financial Report" -ExchangeLocation all -ContentMatchQuery 'sent>=01/01/2015 AND sent<=06/30/2015 AND subject:"financial report"'
```

```
Start-ComplianceSearch -Identity "Search All-Financial Report"
```

<span data-ttu-id="f10fa-146">Para obtener más información, consulte [New-ComplianceSearch](https://go.microsoft.com/fwlink/p/?LinkId=517935).</span><span class="sxs-lookup"><span data-stu-id="f10fa-146">For more information, see [New-ComplianceSearch](https://go.microsoft.com/fwlink/p/?LinkId=517935).</span></span>
  
### <a name="verify-the-number-of-source-mailboxes-in-the-content-search"></a><span data-ttu-id="f10fa-147">Comprobar el número de buzones de origen en la búsqueda de contenido</span><span class="sxs-lookup"><span data-stu-id="f10fa-147">Verify the number of source mailboxes in the Content Search</span></span>

<span data-ttu-id="f10fa-148">Una búsqueda de contenido devuelve un máximo de 1.000 buzones de origen que contienen resultados de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="f10fa-148">A Content Search returns a maximum of 1,000 source mailboxes that contain search results.</span></span> <span data-ttu-id="f10fa-149">Si hay más de 1.000 buzones de correo que contienen contenido que coincide con la consulta de búsqueda, solo los primeros 1.000 buzones con mayor cantidad de resultados de búsqueda se incluyen en la búsqueda de contenido que creó en el paso anterior.</span><span class="sxs-lookup"><span data-stu-id="f10fa-149">If there are more than 1,000 mailboxes that contain content that matches the search query, only the top 1,000 mailboxes with the most search results are included in the Content Search that you created in the previous step.</span></span> <span data-ttu-id="f10fa-150">Por lo tanto, si más de 1.000 buzones de correo contienen resultados de búsqueda, algunos de estos buzones no se incluirán en la lista de buzones de origen que se han copiado a la nueva búsqueda de exhibición de documentos electrónicos local creada en el paso 3.</span><span class="sxs-lookup"><span data-stu-id="f10fa-150">So if more than 1,000 mailboxes contain search results, some of those mailboxes won't be included in the list of source mailboxes copied to the new In-Place eDiscovery search created in Step 3.</span></span> 
  
<span data-ttu-id="f10fa-151">Para ayudarle a crear una búsqueda de contenido con un máximo de 1.000 buzones de correo de origen, siga estos pasos para ejecutar un script que muestre el número de buzones de origen (que contienen los resultados de la búsqueda) devueltos por la búsqueda de contenido que creó en el paso 1.</span><span class="sxs-lookup"><span data-stu-id="f10fa-151">To help you create a Content Search with no more than 1,000 source mailboxes, follow these steps to run a script that displays the number of source mailboxes (that contain search results) returned by the Content Search you created in Step 1.</span></span> 
  
1. <span data-ttu-id="f10fa-152">Guarde el siguiente texto en un archivo de script de PowerShell con un sufijo de nombre de archivo de. ps1.</span><span class="sxs-lookup"><span data-stu-id="f10fa-152">Save the following text to a PowerShell script file by using a filename suffix of .ps1.</span></span> <span data-ttu-id="f10fa-153">Por ejemplo, puede guardarlo en un archivo denominado `SourceMailboxes.ps1`.</span><span class="sxs-lookup"><span data-stu-id="f10fa-153">For example, you could save it to a file named `SourceMailboxes.ps1`.</span></span>
    
  ```
  [CmdletBinding()]
  Param(
      [Parameter(Mandatory=$True,Position=1)]
      [string]$SearchName
  )
  $search = Get-ComplianceSearch $SearchName
  if ($search.Status -ne "Completed")
  {
                  "Please wait until the search finishes.";
                  break;
  }
  $results = $search.SuccessResults;
  if (($search.Items -le 0) -or ([string]::IsNullOrWhiteSpace($results)))
  {
                  "The Content Search " + $SearchName + " didn't return any useful results.";
                  break;
  }
  $mailboxes = @();
  $lines = $results -split '[\r\n]+';
  foreach ($line in $lines)
  {
      if ($line -match 'Location: (\S+),.+Item count: (\d+)' -and $matches[2] -gt 0)
      {
          $mailboxes += $matches[1];
      }
  }
  "Number of mailboxes that have search hits: " + $mailboxes.Count
  ```

2. <span data-ttu-id="f10fa-154">En Security & Compliance Center PowerShell, vaya a la carpeta donde se encuentre el script creado en el paso anterior y ejecute el script; por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="f10fa-154">In Security & Compliance Center PowerShell, go to the folder where the script you created in the previous step is located, and then run the script; for example:</span></span>
    
    ```
    .\SourceMailboxes.ps1
    ```

3. <span data-ttu-id="f10fa-155">Cuando el script se lo pida, escriba el nombre de la búsqueda de contenido que creó en el paso 1.</span><span class="sxs-lookup"><span data-stu-id="f10fa-155">When prompted by the script, type the name of the Content Search that you created in Step 1.</span></span>
    
    <span data-ttu-id="f10fa-156">El script muestra el número de buzones de origen que contienen los resultados de la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="f10fa-156">The script displays the number of source mailboxes that contain search results.</span></span>
    
<span data-ttu-id="f10fa-157">Si hay más de 1.000 buzones de origen, intente crear dos (o más) búsquedas de contenido.</span><span class="sxs-lookup"><span data-stu-id="f10fa-157">If there are more than 1,000 source mailboxes, try creating two (or more) Content Searches.</span></span> <span data-ttu-id="f10fa-158">Por ejemplo, busque en la mitad de los buzones de la organización con una búsqueda de contenido y en la otra mitad con otra búsqueda de contenido.</span><span class="sxs-lookup"><span data-stu-id="f10fa-158">For example, search half of your organization's mailboxes in one Content Search and the other half in another Content Search.</span></span> <span data-ttu-id="f10fa-159">También puede cambiar los criterios de búsqueda para reducir el número de buzones que contengan los resultados de la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="f10fa-159">You could also change the search criteria to reduce the number of mailboxes that contain search results.</span></span> <span data-ttu-id="f10fa-160">Por ejemplo, puede incluir un intervalo de fechas o refinar la consulta de palabra clave.</span><span class="sxs-lookup"><span data-stu-id="f10fa-160">For example, you could include a date range or refine the keyword query.</span></span>
  
## <a name="step-2-connect-to-the-security--compliance-center-and-exchange-online-in-a-single-remote-powershell-session"></a><span data-ttu-id="f10fa-161">Paso 2: conectarse al centro de \& seguridad y cumplimiento y a Exchange online en una única sesión de PowerShell en remoto</span><span class="sxs-lookup"><span data-stu-id="f10fa-161">Step 2: Connect to the Security \& Compliance Center and Exchange Online in a single remote PowerShell session</span></span>

<span data-ttu-id="f10fa-162">El paso siguiente es conectar Windows PowerShell al centro de seguridad & cumplimiento y a la organización de Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="f10fa-162">The next step is to connect Windows PowerShell to both the Security & Compliance Center and to your Exchange Online organization.</span></span> <span data-ttu-id="f10fa-163">Esto es necesario porque el script que ejecutó en el paso 3 requiere acceso a los cmdlets de búsqueda de contenido en el centro de seguridad & cumplimiento y los cmdlets de exhibición de documentos electrónicos local en Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="f10fa-163">This is necessary because the script that you run in Step 3 requires access to the Content Search cmdlets in the Security & Compliance Center and the In-Place eDiscovery cmdlets in Exchange Online.</span></span>
  
1. <span data-ttu-id="f10fa-164">Guarde el siguiente texto en un archivo de script de Windows PowerShell mediante un sufijo de nombre de archivo de .ps1.</span><span class="sxs-lookup"><span data-stu-id="f10fa-164">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1.</span></span> <span data-ttu-id="f10fa-165">Por ejemplo, puede guardarlo en un archivo denominado `ConnectEXO-CC.ps1`.</span><span class="sxs-lookup"><span data-stu-id="f10fa-165">For example, you could save it to a file named `ConnectEXO-CC.ps1`.</span></span>
    
    ```
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.outlook.com/powershell-liveid -Credential $UserCredential -Authentication Basic -AllowRedirection
    Import-PSSession $Session -DisableNameChecking
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Credential $UserCredential -Authentication Basic -AllowRedirection
    Import-PSSession $Session -AllowClobber -DisableNameChecking
    $Host.UI.RawUI.WindowTitle = $UserCredential.UserName + " (Exchange Online + Compliance Center)"
    ```

2. <span data-ttu-id="f10fa-166">En el equipo local, abra Windows PowerShell, vaya a la carpeta en la que se encuentra el script creado en el paso anterior y, a continuación, ejecute el script. por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="f10fa-166">On your local computer, open Windows PowerShell, go to the folder where the script that you created in the previous step is located, and then run the script; for example:</span></span>
    
    ```
    .\ConnectEXO-CC.ps1
    ```

<span data-ttu-id="f10fa-167">¿Cómo se sabe si se ha completado correctamente?</span><span class="sxs-lookup"><span data-stu-id="f10fa-167">How do you know if this worked?</span></span> <span data-ttu-id="f10fa-168">Después de ejecutar el script, los cmdlets del centro de seguridad de & cumplimiento y Exchange Online se importan a la sesión local de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f10fa-168">After you run the script, cmdlets from the Security & Compliance Center and Exchange Online are imported into your local PowerShell session.</span></span> <span data-ttu-id="f10fa-169">Si no se muestra ningún error, la conexión se habrá establecido correctamente.</span><span class="sxs-lookup"><span data-stu-id="f10fa-169">If you don't receive any errors, you connected successfully.</span></span> <span data-ttu-id="f10fa-170">Una prueba rápida es ejecutar un cmdlet del centro de cumplimiento de & de seguridad (por ejemplo, **install-UnifiedCompliancePrerequisite** ) y un cmdlet de Exchange Online, como **Get-Mailbox**.</span><span class="sxs-lookup"><span data-stu-id="f10fa-170">A quick test is to run a Security & Compliance Center cmdlet—for example, **Install-UnifiedCompliancePrerequisite** —and an Exchange Online cmdlet, such as **Get-Mailbox**.</span></span> 
  
## <a name="step-3-run-the-script-to-create-an-in-place-ediscovery-search-from-the-content-search"></a><span data-ttu-id="f10fa-171">Paso 3: Ejecutar el script para crear una búsqueda de eDiscovery local a partir de la búsqueda de contenido</span><span class="sxs-lookup"><span data-stu-id="f10fa-171">Step 3: Run the script to create an In-Place eDiscovery search from the Content Search</span></span>

<span data-ttu-id="f10fa-172">Después de crear la sesión de PowerShell dual en el paso 2, el siguiente paso es ejecutar un script que convertirá una búsqueda de contenido existente en una búsqueda de exhibición de documentos electrónicos local.</span><span class="sxs-lookup"><span data-stu-id="f10fa-172">After you create the dual PowerShell session in Step 2, the next step is to run a script that will convert an existing Content Search to an In-Place eDiscovery search.</span></span> <span data-ttu-id="f10fa-173">Esto es lo que hace el script:</span><span class="sxs-lookup"><span data-stu-id="f10fa-173">Here's what the script does:</span></span>
  
- <span data-ttu-id="f10fa-174">Le pide el nombre de la búsqueda de contenido que quiere convertir.</span><span class="sxs-lookup"><span data-stu-id="f10fa-174">Prompts you for the name of the Content Search to convert.</span></span>
    
- <span data-ttu-id="f10fa-p116">Comprueba que se ha completado la búsqueda de contenido. Si la búsqueda de contenido no devuelve ningún resultado, no se creará el eDiscovery local.</span><span class="sxs-lookup"><span data-stu-id="f10fa-p116">Verifies that the Content Search has completed running. If the Content Search doesn't return any results, and In-Place eDiscovery won't be created.</span></span>
    
- <span data-ttu-id="f10fa-177">Guarda una lista de los buzones de origen de la búsqueda de contenido que contienen los resultados de la búsqueda en una variable.</span><span class="sxs-lookup"><span data-stu-id="f10fa-177">Saves a list of the source mailboxes from the Content Search that contain search results to a variable.</span></span>
    
- <span data-ttu-id="f10fa-p117">Crea una nueva búsqueda de exhibición de documentos electrónicos local con las propiedades siguientes. Tenga en cuenta que la búsqueda nueva no se inicia. Empezará en el paso 4.</span><span class="sxs-lookup"><span data-stu-id="f10fa-p117">Creates a new In-Place eDiscovery search, with the following properties. Note that the new search isn't started. You'll start it in step 4.</span></span>
    
  - <span data-ttu-id="f10fa-181">**Nombre** : el nombre de la nueva búsqueda usa este formato: \<nombre de la búsqueda\>de contenido _MBSearch1.</span><span class="sxs-lookup"><span data-stu-id="f10fa-181">**Name** - The name of the new search uses this format: \<Name of Content Search\>_MBSearch1.</span></span> <span data-ttu-id="f10fa-182">Si vuelve a ejecutar el script y usa la misma búsqueda de contenido de origen, la búsqueda se \<denominará nombre de\>búsqueda de contenido _MBSearch2.</span><span class="sxs-lookup"><span data-stu-id="f10fa-182">If you run the script again and use the same source Content Search, the search will be named \<Name of Content Search\>_MBSearch2.</span></span>
    
  - <span data-ttu-id="f10fa-183">**Buzones de origen** : todos los buzones de la búsqueda de contenido que contienen los resultados de la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="f10fa-183">**Source mailboxes** - All mailboxes from the Content Search that contain search results.</span></span> 
    
  - <span data-ttu-id="f10fa-184">**Consulta de búsqueda** : la nueva búsqueda usa la consulta de búsqueda de la búsqueda de contenido.</span><span class="sxs-lookup"><span data-stu-id="f10fa-184">**Search query** - The new search uses the search query from the Content Search.</span></span> <span data-ttu-id="f10fa-185">Si en la búsqueda de contenido se incluye todo el contenido (cuando la consulta de búsqueda está en blanco), la nueva búsqueda también tendrá una consulta de búsqueda en blanco donde se incluirá todo el contenido encontrado en los buzones de origen.</span><span class="sxs-lookup"><span data-stu-id="f10fa-185">If the Content Search includes all content (where the search query is blank) the new search will also have a blank search query and will include all content found in the source mailboxes.</span></span> 
    
  - <span data-ttu-id="f10fa-186">**Estimar solo la búsqueda** : la nueva búsqueda se marca como una búsqueda de solo estimación.</span><span class="sxs-lookup"><span data-stu-id="f10fa-186">**Estimate only search** - The new search is marked as an estimate-only search.</span></span> <span data-ttu-id="f10fa-187">No se copiarán los resultados de búsqueda a un buzón de detección una vez que se haya iniciado.</span><span class="sxs-lookup"><span data-stu-id="f10fa-187">It won't copy search results to a discovery mailbox after you start it.</span></span> 
    
1. <span data-ttu-id="f10fa-188">Guarde el siguiente texto en un archivo de script de Windows PowerShell mediante un sufijo de nombre de archivo de ps1.</span><span class="sxs-lookup"><span data-stu-id="f10fa-188">Save the following text to a Windows PowerShell script file by using a filename suffix of ps1.</span></span> <span data-ttu-id="f10fa-189">Por ejemplo, puede guardarlo en un archivo denominado `CreateMBSearchFromComplianceSearch.ps1`.</span><span class="sxs-lookup"><span data-stu-id="f10fa-189">For example, you could save it to a file named `CreateMBSearchFromComplianceSearch.ps1`.</span></span>
    
  ```
  [CmdletBinding()]
  Param(
      [Parameter(Mandatory=$True,Position=1)]
      [string]$SearchName,
      [switch]$original,
      [switch]$restoreOriginal
  )
  $search = Get-ComplianceSearch $SearchName
  if ($search.Status -ne "Completed")
  {
    "Please wait until the search finishes";
    break;
  }
  $results = $search.SuccessResults;
  if (($search.Items -le 0) -or ([string]::IsNullOrWhiteSpace($results)))
  {
    "The Content Search " + $SearchName + " didn't return any useful results";
    "A mailbox search object wasn't created";
    break;
  }
  $mailboxes = @();
  $lines = $results -split '[\r\n]+';
  foreach ($line in $lines)
  {
      if ($line -match 'Location: (\S+),.+Item count: (\d+)' -and $matches[2] -gt 0)
      {
          $mailboxes += $matches[1];
      }
  }
  $msPrefix = $SearchName + "_MBSearch";
  $I = 1;
  $mbSearches = Get-MailboxSearch;
  while ($true)
  {
      $found = $false;
      $mbsName = "$msPrefix$I";
      foreach ($mbs in $mbSearches)
      {
          if ($mbs.Name -eq $mbsName)
          {
              $found = $true;
              break;
          }
      }
      if (!$found)
      {
          break;
      }
      $I++;
  }
  $query = $search.KeywordQuery;
  if ([string]::IsNullOrWhiteSpace($query))
  {
      $query = $search.ContentMatchQuery;
  }
  if ([string]::IsNullOrWhiteSpace($query))
  {
    New-MailboxSearch "$msPrefix$i" -SourceMailboxes $mailboxes -EstimateOnly;
  }
  else
  {
    New-MailboxSearch "$msPrefix$i" -SourceMailboxes $mailboxes -SearchQuery $query -EstimateOnly;
  }
  
  ```

2. <span data-ttu-id="f10fa-190">En la sesión de Windows PowerShell que creó en el paso 2, vaya a la carpeta en la que se encuentra el script creado en el paso anterior y, a continuación, ejecute el script. por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="f10fa-190">In the Windows PowerShell session that you created in Step 2, go to the folder where the script that you created in the previous step is located, and then run the script; for example:</span></span>
    
    ```
    .\CreateMBSearchFromComplianceSearch.ps1
    ```

3. <span data-ttu-id="f10fa-191">Cuando se lo pida el script, escriba el nombre de la búsqueda de contenido que desea repartir en una búsqueda de exhibición de documentos electrónicos local (por ejemplo, la búsqueda que creó en el paso 1) y, a continuación, presione **entrar**.</span><span class="sxs-lookup"><span data-stu-id="f10fa-191">When prompted by the script, type the name of the Content Search that you want to covert to an In-Place eDiscovery search (for example, the search that you created in Step 1), and then press **Enter**.</span></span>
    
    <span data-ttu-id="f10fa-p122">Si el script funciona, se crea una nueva búsqueda de exhibición de documentos electrónicos local con un estado **NotStarted**. Ejecute el comando  `Get-MailboxSearch <Name of Content Search>_MBSearch1 | FL` para mostrar las propiedades de la nueva búsqueda.</span><span class="sxs-lookup"><span data-stu-id="f10fa-p122">If the script is successful, a new In-Place eDiscovery search is created with a status of **NotStarted**. Run the command  `Get-MailboxSearch <Name of Content Search>_MBSearch1 | FL` to display the properties of the new search.</span></span> 
  
## <a name="step-4-start-the-in-place-ediscovery-search"></a><span data-ttu-id="f10fa-194">Paso 4: Iniciar la búsqueda de exhibición de documentos electrónicos local</span><span class="sxs-lookup"><span data-stu-id="f10fa-194">Step 4: Start the In-Place eDiscovery search</span></span>

<span data-ttu-id="f10fa-p123">El script que se ejecuta en el paso 3 crea una nueva búsqueda de exhibición de documentos electrónicos local, pero no la inicia. El siguiente paso es iniciar la búsqueda para obtener una estimación de los resultados de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="f10fa-p123">The script that you run in Step 3 creates a new In-Place eDiscovery search, but doesn't start it. The next step is to start the search so you can get an estimate of the search results.</span></span>
  
1. <span data-ttu-id="f10fa-197">In the Exchange admin center (EAC), go to **Compliance management** \> **In-Place eDiscovery &amp; Hold**.</span><span class="sxs-lookup"><span data-stu-id="f10fa-197">In the Exchange admin center (EAC), go to **Compliance management** \> **In-Place eDiscovery &amp; Hold**.</span></span>
    
2. <span data-ttu-id="f10fa-198">En la vista de lista, seleccione la búsqueda de exhibición de documentos electrónicos local que se creó en el paso 3.</span><span class="sxs-lookup"><span data-stu-id="f10fa-198">In the list view, select the In-Place eDiscovery search that you created in Step 3.</span></span>
    
3. <span data-ttu-id="f10fa-199">Haga \*\*\*\* ![clic en el](media/5f6f9463-50e9-460b-8738-b67e759c2efc.gif) \> icono búsqueda de búsqueda **estimar resultados de búsqueda** para iniciar la búsqueda y devolver una estimación del tamaño total y el número de elementos devueltos por la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="f10fa-199">Click **Search** ![Search icon](media/5f6f9463-50e9-460b-8738-b67e759c2efc.gif) \> **Estimate search results** to start the search and return an estimate of the total size and number of items returned by the search.</span></span> 
    
    <span data-ttu-id="f10fa-200">Las estimaciones se muestran en el panel de detalles.</span><span class="sxs-lookup"><span data-stu-id="f10fa-200">The estimates are displayed in the details pane.</span></span> <span data-ttu-id="f10fa-201">Haga \*\*\*\* ![clic en el](media/O365-MDM-Policy-RefreshIcon.gif) icono Actualizar actualización para actualizar la información que se muestra en el panel de detalles.</span><span class="sxs-lookup"><span data-stu-id="f10fa-201">Click **Refresh** ![Refresh icon](media/O365-MDM-Policy-RefreshIcon.gif) to update the information displayed in the details pane.</span></span> 
    
4. <span data-ttu-id="f10fa-202">Para obtener una vista previa de los resultados una vez completada la búsqueda, haga clic en **Vista previa de los resultados de búsqueda** en el panel de detalles.</span><span class="sxs-lookup"><span data-stu-id="f10fa-202">To preview the results after the search is completed, click **Preview search results** in the details pane.</span></span>
  
## <a name="next-steps-after-creating-and-running-the-in-place-ediscovery-search"></a><span data-ttu-id="f10fa-203">Pasos siguientes después de crear y ejecutar la búsqueda de exhibición de documentos electrónicos local</span><span class="sxs-lookup"><span data-stu-id="f10fa-203">Next steps after creating and running the In-Place eDiscovery search</span></span>

<span data-ttu-id="f10fa-204">Después de crear e iniciar la búsqueda de exhibición de documentos electrónicos local que el script ha creado en el paso 3, puede usar el flujo de trabajo normal de la exhibición de documentos electrónicos local para realizar distintas acciones de exhibición de documentos electrónicos en los resultados de la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="f10fa-204">After you create and start the In-Place eDiscovery search that was created by the script in Step 3, you can use the normal In-Place eDiscovery workflow to perform different eDiscovery actions on the search results.</span></span>
  
### <a name="create-an-in-place-hold"></a><span data-ttu-id="f10fa-205">Crear una Conservación local</span><span class="sxs-lookup"><span data-stu-id="f10fa-205">Create an In-Place Hold</span></span>

1. <span data-ttu-id="f10fa-206">In the EAC, go to **Compliance management** \> **In-Place eDiscovery &amp; Hold**.</span><span class="sxs-lookup"><span data-stu-id="f10fa-206">In the EAC, go to **Compliance management** \> **In-Place eDiscovery &amp; Hold**.</span></span>
    
2. <span data-ttu-id="f10fa-207">En la vista de lista, seleccione la búsqueda de exhibición de documentos electrónicos local que creó en el paso 3 y, a continuación](media/O365_MDM_CreatePolicy_EditIcon.gif), haga clic en **Editar** ![icono de edición.</span><span class="sxs-lookup"><span data-stu-id="f10fa-207">In the list view, select the In-Place eDiscovery search that you created in Step 3, and then click **Edit** ![Edit icon](media/O365_MDM_CreatePolicy_EditIcon.gif).</span></span>
    
3. <span data-ttu-id="f10fa-208">En la página **Conservación local**, active la casilla **Pausar el contenido que coincida con la consulta de búsqueda en los buzones seleccionados** y después seleccione una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="f10fa-208">On the **In-Place Hold** page, select the **Place content matching the search query in selected mailboxes on hold** check box and then select one of the following options:</span></span> 
    
  - <span data-ttu-id="f10fa-209">**Retener** indefinidamente: elija esta opción para poner los elementos devueltos por la búsqueda en una retención indefinida.</span><span class="sxs-lookup"><span data-stu-id="f10fa-209">**Hold indefinitely** - Choose this option to place items returned by the search on an indefinite hold.</span></span> <span data-ttu-id="f10fa-210">Los elementos en espera se conservarán hasta que quite el buzón de correo de la búsqueda o la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="f10fa-210">Items on hold will be preserved until you remove the mailbox from the search or remove the search.</span></span> 
    
  - <span data-ttu-id="f10fa-211">**Especificar el número de días que se conservarán los elementos relacionados con la fecha de recepción** : elija esta opción para retener elementos durante un período específico.</span><span class="sxs-lookup"><span data-stu-id="f10fa-211">**Specify number of days to hold items relative to their received date** - Choose this option to hold items for a specific period.</span></span> <span data-ttu-id="f10fa-212">La duración se calcula desde la fecha en que un elemento de buzón se recibe o se crea.</span><span class="sxs-lookup"><span data-stu-id="f10fa-212">The duration is calculated from the date a mailbox item is received or created.</span></span> 
    
4. <span data-ttu-id="f10fa-213">Haga clic en **Guardar** para crear la conservación local y reiniciar la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="f10fa-213">Click **Save** to create the In-Place Hold and restart the search.</span></span> 
    
[<span data-ttu-id="f10fa-214">Return to top</span><span class="sxs-lookup"><span data-stu-id="f10fa-214">Return to top</span></span>](use-content-search-in-ediscovery.md#top)
  
### <a name="copy-the-search-results"></a><span data-ttu-id="f10fa-215">Copiar los resultados de la búsqueda</span><span class="sxs-lookup"><span data-stu-id="f10fa-215">Copy the search results</span></span>

1. <span data-ttu-id="f10fa-216">In the EAC, go to **Compliance management** \> **In-Place eDiscovery &amp; Hold**.</span><span class="sxs-lookup"><span data-stu-id="f10fa-216">In the EAC, go to **Compliance management** \> **In-Place eDiscovery &amp; Hold**.</span></span>
    
2. <span data-ttu-id="f10fa-217">En la vista de lista, seleccione la búsqueda de exhibición de documentos electrónicos local que ha creado en el paso 3.</span><span class="sxs-lookup"><span data-stu-id="f10fa-217">In the list view, select the In-Place eDiscovery search that you created in Step 3.</span></span>
    
3. <span data-ttu-id="f10fa-218">Haga clic en el](media/5f6f9463-50e9-460b-8738-b67e759c2efc.gif)icono Buscar búsqueda y, a continuación, haga clic en **copiar resultados de búsqueda** en la lista desplegable. \*\*\*\* ![</span><span class="sxs-lookup"><span data-stu-id="f10fa-218">Click **Search** ![Search icon](media/5f6f9463-50e9-460b-8738-b67e759c2efc.gif), and then click **Copy search results** from the drop-down list.</span></span> 
    
4. <span data-ttu-id="f10fa-219">En **Copiar resultados de búsqueda**, seleccione entre las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="f10fa-219">In **Copy Search Results**, select from the following options:</span></span>
    
    - <span data-ttu-id="f10fa-220">**Incluir elementos** que no se pueden buscar: Active esta casilla para incluir elementos de buzones que no se pudieron buscar (por ejemplo, mensajes con datos adjuntos de tipos de archivo que la búsqueda de Exchange no pudo indexar).</span><span class="sxs-lookup"><span data-stu-id="f10fa-220">**Include unsearchable items** - Select this check box to include mailbox items that couldn't be searched (for example, messages with attachments of file types that couldn't be indexed by Exchange Search).</span></span> 
    
    - <span data-ttu-id="f10fa-221">**Habilitación de** la desduplicación: Seleccione esta casilla para excluir los mensajes duplicados.</span><span class="sxs-lookup"><span data-stu-id="f10fa-221">**Enable de-duplication** - Select this check box to exclude duplicate messages.</span></span> <span data-ttu-id="f10fa-222">Solo una instancia del mensaje se copiará en el buzón de correo de detección.</span><span class="sxs-lookup"><span data-stu-id="f10fa-222">Only a single instance of a message will be copied to the discovery mailbox.</span></span> 
    
    - <span data-ttu-id="f10fa-223">**Habilitar registro completo** : Seleccione esta casilla para incluir un registro completo en los resultados de la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="f10fa-223">**Enable full logging** - Select this check box to include a full log in search results.</span></span> 
    
    - <span data-ttu-id="f10fa-224">**Enviarme un correo cuando se haya completado la copia** : Seleccione esta casilla para recibir una notificación por correo electrónico cuando la búsqueda se haya completado.</span><span class="sxs-lookup"><span data-stu-id="f10fa-224">**Send me mail when the copy is completed** - Select this check box to get an email notification when the search is completed.</span></span> 
    
    - <span data-ttu-id="f10fa-225">**Copiar los resultados en este buzón de detección** : haga clic en **examinar** para seleccionar el buzón de correo de detección en el que desea copiar los resultados de la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="f10fa-225">**Copy results to this discovery mailbox** - Click **Browse** to select the discovery mailbox where you want the search results copied to.</span></span> 
    
5. <span data-ttu-id="f10fa-226">Haga clic en **Copiar** para iniciar el proceso de copia de los resultados de la búsqueda en el buzón de correo de detección especificado.</span><span class="sxs-lookup"><span data-stu-id="f10fa-226">Click **Copy** to start the process to copy the search results to the specified discovery mailbox.</span></span> 
    
6. <span data-ttu-id="f10fa-227">Haga \*\*\*\* ![clic en actualizar](media/O365-MDM-Policy-RefreshIcon.gif) icono para actualizar la información sobre el estado de copia que se muestra en el panel de detalles.</span><span class="sxs-lookup"><span data-stu-id="f10fa-227">Click **Refresh** ![Refresh icon](media/O365-MDM-Policy-RefreshIcon.gif) to update the information about the copying status that is displayed in the details pane.</span></span> 
    
7. <span data-ttu-id="f10fa-228">Una vez que la copia esté completa, haga clic en **Abrir** para abrir el buzón de correo de detección y ver los resultados de la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="f10fa-228">When copying is complete, click **Open** to open the discovery mailbox to view the search results.</span></span> 
  
### <a name="export-the-search-results"></a><span data-ttu-id="f10fa-229">Exportar los resultados de la búsqueda</span><span class="sxs-lookup"><span data-stu-id="f10fa-229">Export the search results</span></span>

1. <span data-ttu-id="f10fa-230">In the EAC, go to **Compliance management** \> **In-Place eDiscovery &amp; Hold**.</span><span class="sxs-lookup"><span data-stu-id="f10fa-230">In the EAC, go to **Compliance management** \> **In-Place eDiscovery &amp; Hold**.</span></span>
    
2. <span data-ttu-id="f10fa-231">En la vista de lista, seleccione la búsqueda de exhibición de documentos electrónicos local que se creó en el paso 3 y luego haga clic en **Exportar a un archivo PST**.</span><span class="sxs-lookup"><span data-stu-id="f10fa-231">In the list view, select the In-Place eDiscovery search that you created in Step 3, and then click **Export to a PST file**.</span></span>
    
3. <span data-ttu-id="f10fa-232">En la ventana de la **herramienta de exportación de PST de exhibición de documentos electrónicos**:</span><span class="sxs-lookup"><span data-stu-id="f10fa-232">In the **eDiscovery PST Export Tool** window, do the following:</span></span> 
    
    - <span data-ttu-id="f10fa-233">Haga clic en **Examinar** para especificar la ubicación donde quiere descargar el archivo PST.</span><span class="sxs-lookup"><span data-stu-id="f10fa-233">Click **Browse** to specify the location where you want to download the PST file.</span></span> 
    
    - <span data-ttu-id="f10fa-p128">Haga clic en la casilla **Habilitar desduplicación** para excluir los mensajes duplicados. Solo se incluirá una instancia de cada mensaje en el archivo PST.</span><span class="sxs-lookup"><span data-stu-id="f10fa-p128">Click the **Enable deduplication** checkbox to exclude duplicate messages. Only a single instance of a message will be included in the PST file.</span></span> 
    
    - <span data-ttu-id="f10fa-p129">Haga clic en la casilla **Incluir elementos no aptos para la búsqueda** si quiere incluir los elementos del buzón que no pudieron buscar (por ejemplo, los mensajes con datos adjuntos de tipos de archivo que la búsqueda de Exchange no pudo indexar). Los elementos no aptos para la búsqueda se exportan a un archivo PST independiente.</span><span class="sxs-lookup"><span data-stu-id="f10fa-p129">Click the **Include unsearchable items** checkbox to include mailbox items that couldn't be searched (for example, messages with attachments of file types that couldn't be indexed by Exchange Search). Unsearchable items are exported to a separate PST file.</span></span> 
    
4. <span data-ttu-id="f10fa-238">Haga clic en **Inicio** para exportar los resultados de búsqueda a un archivo PST.</span><span class="sxs-lookup"><span data-stu-id="f10fa-238">Click **Start** to export the search results to a PST file.</span></span> 
    
    <span data-ttu-id="f10fa-239">Se mostrará una ventana con información acerca del estado del proceso de exportación.</span><span class="sxs-lookup"><span data-stu-id="f10fa-239">A window is displayed that contains status information about the export process.</span></span>
