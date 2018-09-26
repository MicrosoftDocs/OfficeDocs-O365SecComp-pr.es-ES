---
title: Usar Búsqueda de contenido en el flujo de trabajo de eDiscovery
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 12/30/2016
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.assetid: 55f31488-288a-473a-9b9e-831a11e3711a
description: 'Usar un script de PowerShell para crear una búsqueda de exhibición de documentos electrónicos en contexto en Exchange Online basándose en una búsqueda creada en la seguridad de Office 365 &amp; centro de cumplimiento. '
ms.openlocfilehash: 42af94ce850736dede52e619c240bb9e0a6f7031
ms.sourcegitcommit: 7956955cd919f6e00b64e4506605a743c5872549
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/26/2018
ms.locfileid: "25038073"
---
# <a name="use-content-search-in-your-ediscovery-workflow"></a><span data-ttu-id="6ebbf-103">Usar Búsqueda de contenido en el flujo de trabajo de eDiscovery</span><span class="sxs-lookup"><span data-stu-id="6ebbf-103">Use Content Search in your eDiscovery workflow</span></span>

<span data-ttu-id="6ebbf-p101">La característica de búsqueda de contenido de la seguridad de Office 365 &amp; centro de cumplimiento le permite buscar todos los buzones de la organización. A diferencia de exhibición de documentos electrónicos en contexto en Exchange Online (que se pueden buscar hasta 10.000 buzones de correo), no hay ningún límite para el número de buzones de correo de destino en una sola búsqueda. Para los escenarios que requieren que se va a realizar búsquedas de toda la organización, puede usar la búsqueda de contenido para buscar todos los buzones. A continuación, puede usar las características de flujo de trabajo de exhibición de documentos electrónicos en contexto para llevar a cabo otras tareas relacionadas con la exhibición de documentos electrónicos, como los buzones de correo puestas en espera y los resultados de búsqueda de exportación. Por ejemplo, supongamos que tiene que buscar todos los buzones de correo para identificar a Custodios específicos que responden a un caso legal. Puede usar la búsqueda de contenido en la seguridad &amp; centro de cumplimiento para buscar todos los buzones de la organización para identificarlos que responden a las mayúsculas y minúsculas. A continuación, puede usar esa lista de buzones de correo de custodia como los buzones de origen para una búsqueda de exhibición de documentos electrónicos en contexto en Exchange Online. Uso de exhibición de documentos electrónicos también permite colocar una suspensión en los buzones de origen, copiar los resultados de búsqueda en un buzón de detección y exportar los resultados de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="6ebbf-p101">The Content Search feature in the Office 365 Security &amp; Compliance Center allows you to search all mailboxes in your organization. Unlike In-Place eDiscovery in Exchange Online (where you can search up to 10,000 mailboxes), there are no limits for the number of target mailboxes in a single search. For scenarios that require you to perform organization-wide searches, you can use Content Search to search all mailboxes. Then you can use the workflow features of In-Place eDiscovery to perform other eDiscovery-related tasks, such as placing mailboxes on hold and exporting search results. For example, let's say you have to search all mailboxes to identify specific custodians that are responsive to a legal case. You can use Content Search in the Security &amp; Compliance Center to search all mailboxes in your organization to identify those that are responsive to the case. Then you can use that list of custodian mailboxes as the source mailboxes for an In-Place eDiscovery search in Exchange Online. Using In-Place eDiscovery also allows you to put a hold on those source mailboxes, copy search results to a discovery mailbox, and export the search results.</span></span>
  
<span data-ttu-id="6ebbf-p102">En este tema se incluye una secuencia de comandos que puede ejecutar para crear una búsqueda de exhibición de documentos electrónicos en contexto en Exchange Online mediante el uso de la lista de buzones de origen y la consulta de búsqueda de una búsqueda creada en la seguridad &amp; centro de cumplimiento. Aquí es una descripción general del proceso:</span><span class="sxs-lookup"><span data-stu-id="6ebbf-p102">This topic includes a script that you can run to create an In-Place eDiscovery search in Exchange Online by using the list of source mailboxes and search query from a search created in the Security &amp; Compliance Center. Here's an overview of the process:</span></span>
  
[<span data-ttu-id="6ebbf-114">Paso 1: Crear una Búsqueda de contenido para todos los buzones de la organización</span><span class="sxs-lookup"><span data-stu-id="6ebbf-114">Step 1: Create a Content Search to search all mailboxes in your organization</span></span>](#step-1-create-a-content-search-to-search-all-mailboxes-in-your-organization)

[<span data-ttu-id="6ebbf-115">Paso 2: Conectarse a la seguridad &amp; centro de cumplimiento y Exchange Online en una sola sesión de PowerShell remota</span><span class="sxs-lookup"><span data-stu-id="6ebbf-115">Step 2: Connect to the Security &amp; Compliance Center and Exchange Online in a single remote PowerShell session</span></span>](#step-2-connect-to-the-security-amp-compliance-center-and-exchange-online-in-a-single-remote-powershell-session)
  
[<span data-ttu-id="6ebbf-116">Paso 3: Ejecutar el script para crear una búsqueda de eDiscovery local a partir de la búsqueda de contenido</span><span class="sxs-lookup"><span data-stu-id="6ebbf-116">Step 3: Run the script to create an In-Place eDiscovery search from the Content Search</span></span>](#step-3-run-the-script-to-create-an-in-place-ediscovery-search-from-the-content-search)

[<span data-ttu-id="6ebbf-117">Paso 4: Iniciar la búsqueda de exhibición de documentos electrónicos local</span><span class="sxs-lookup"><span data-stu-id="6ebbf-117">Step 4: Start the In-Place eDiscovery search</span></span>](#step-4-start-the-in-place-ediscovery-search)

## <a name="step-1-create-a-content-search-to-search-all-mailboxes-in-your-organization"></a><span data-ttu-id="6ebbf-118">Paso 1: Crear una Búsqueda de contenido para todos los buzones de la organización</span><span class="sxs-lookup"><span data-stu-id="6ebbf-118">Step 1: Create a Content Search to search all mailboxes in your organization</span></span>

<span data-ttu-id="6ebbf-p103">El primer paso consiste en usar la seguridad &amp; centro de cumplimiento (o seguridad y cumplimiento centro de PowerShell) para crear una búsqueda de contenido que busca en todos los buzones de la organización. No hay ningún límite para el número de buzones de correo para una sola búsqueda de contenido. Especificar una consulta de palabra clave adecuada (o una consulta para los tipos de información confidencial) para que la búsqueda devuelve sólo los buzones de origen que son relevantes para la investigación. Si es necesario, refinar la consulta de búsqueda para restringir el ámbito de los resultados de búsqueda y los buzones de origen que se devuelven.</span><span class="sxs-lookup"><span data-stu-id="6ebbf-p103">The first step is to use the Security &amp; Compliance Center (or Security & Compliance Center PowerShell) to create a Content Search that searches all mailboxes in your organization. There's no limit for the number of mailboxes for a single Content Search. Specify an appropriate keyword query (or a query for sensitive information types) so that the search returns only those source mailboxes that are relevant to your investigation. If necessary, refine the search query to narrow the scope of search results and source mailboxes that are returned.</span></span>
  
> [!NOTE]
> <span data-ttu-id="6ebbf-p104">Si la búsqueda de contenido de origen no devuelve ningún resultado, no se creará un eDiscovery local al ejecutar el script en el paso 3. Revise la consulta de búsqueda y, después, vuelva a ejecutar la búsqueda de contenido para mostrar los resultados de la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="6ebbf-p104">If the source Content Search doesn't return any results, an In-Place eDiscovery won't be created when you run the script in Step 3. You may have to revise the search query then rerun the Content Search to return search results.</span></span> 
  
### <a name="use-the-security-amp-compliance-center-to-search-all-mailboxes"></a><span data-ttu-id="6ebbf-125">Usar la seguridad &amp; centro de cumplimiento para buscar todos los buzones</span><span class="sxs-lookup"><span data-stu-id="6ebbf-125">Use the Security &amp; Compliance Center to search all mailboxes</span></span>

1. <span data-ttu-id="6ebbf-126">[Vaya a la seguridad de Office 365 &amp; centro de cumplimiento](go-to-the-securitycompliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="6ebbf-126">[Go to the Office 365 Security &amp; Compliance Center](go-to-the-securitycompliance-center.md).</span></span> 
    
2. <span data-ttu-id="6ebbf-127">Haga clic en **búsqueda &amp; investigación**, haga clic en **búsqueda de contenido**y, a continuación, haga clic en **nuevo** ![icono Agregar](media/O365-MDM-CreatePolicy-AddIcon.gif).</span><span class="sxs-lookup"><span data-stu-id="6ebbf-127">Click **Search &amp; investigation**, click **Content search**, and then click **New** ![Add icon](media/O365-MDM-CreatePolicy-AddIcon.gif).</span></span>
    
3. <span data-ttu-id="6ebbf-128">En la página **Nueva búsqueda**, escriba un nombre para la búsqueda de contenido.</span><span class="sxs-lookup"><span data-stu-id="6ebbf-128">On the **New search** page, type a name for the Content Search.</span></span> 
    
4. <span data-ttu-id="6ebbf-129">En **¿Dónde desea buscar?**, haga clic en **Buscar en todos los buzones** y, a continuación, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="6ebbf-129">Under **Where do you want us to look?**, click **Search all mailboxes**, and then click **Next**.</span></span>
    
5. <span data-ttu-id="6ebbf-p105">En el cuadro en **¿Qué desea nos para buscar?**, escriba una consulta de búsqueda en el cuadro. Puede especificar las palabras clave, mensaje propiedades como envían y reciben fechas, o las propiedades de documento, como los nombres de archivo o la fecha en que se modificó por última vez un documento. Puede usar una de las consultas más complejas que utilizan un operador booleano, como AND y OR, no o NEAR o también puede buscar información confidencial (como números de la seguridad social) en los mensajes. Para obtener más información acerca de cómo crear consultas de búsqueda, vea [consultas de palabra clave para la búsqueda de contenido](keyword-queries-and-search-conditions.md).</span><span class="sxs-lookup"><span data-stu-id="6ebbf-p105">In the box under **What do you want us to look for?**, type a search query in the box. You can specify keywords, message properties such as sent and received dates, or document properties such as file names or the date that a document was last changed. You can use a more complex queries that use a Boolean operator, such as AND, OR, NOT or NEAR, or you can also search for sensitive information (such as social security numbers) in messages. For more information about creating search queries, see [Keyword queries for Content Search](keyword-queries-and-search-conditions.md).</span></span>
    
6. <span data-ttu-id="6ebbf-134">Haga clic en **Búsqueda** para guardar la configuración de la búsqueda e iniciar la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="6ebbf-134">Click **Search** to save the search settings and start the search.</span></span> 
    
    <span data-ttu-id="6ebbf-p106">Después de unos momentos, se muestra una estimación de los resultados de búsqueda en el panel de detalles. La estimación incluye el tamaño total y el número de elementos para los resultados de búsqueda. Una vez finalizada la búsqueda, puede obtener una vista previa de los resultados de búsqueda. Si es necesario, haga clic en **Actualizar**![icono de actualización](media/O365-MDM-Policy-RefreshIcon.gif) para actualizar la información en el panel de detalles.</span><span class="sxs-lookup"><span data-stu-id="6ebbf-p106">After a while, an estimate of the search results displayed in the details pane. The estimate includes the total size and number of items for the search results. After the search is completed, you can preview the search results. If necessary, click **Refresh**![Refresh icon](media/O365-MDM-Policy-RefreshIcon.gif) to update the information in the details pane.</span></span> 
    
7.  <span data-ttu-id="6ebbf-139">Si es necesario, refine la consulta de búsqueda para restringir el alcance de los resultados de la búsqueda y, a continuación, reinicie la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="6ebbf-139">If necessary, refine the search query to narrow the scope of search results and then restart the search.</span></span> 
    
### <a name="use-security--compliance-center-powershell-to-search-all-mailboxes"></a><span data-ttu-id="6ebbf-140">Usar PowerShell de centro de cumplimiento y seguridad para buscar en todos los buzones</span><span class="sxs-lookup"><span data-stu-id="6ebbf-140">Use Security & Compliance Center PowerShell to search all mailboxes</span></span>

<span data-ttu-id="6ebbf-p107">También puede usar el cmdlet **New-ComplianceSearch** para buscar todos los buzones de la organización. El primer paso es [Conectar a Office 365 seguridad &amp; PowerShell de centro de cumplimiento de normas](https://go.microsoft.com/fwlink/p/?LinkID=627084).</span><span class="sxs-lookup"><span data-stu-id="6ebbf-p107">You can also use the **New-ComplianceSearch** cmdlet to search all mailboxes in your organization. The first step is to [Connect to Office 365 Security &amp; Compliance Center PowerShell](https://go.microsoft.com/fwlink/p/?LinkID=627084).</span></span>
  
<span data-ttu-id="6ebbf-p108">Este es un ejemplo del uso de PowerShell para buscar todos los buzones de la organización. La consulta de búsqueda devuelve todos los mensajes enviados entre el 1 de enero de 2015 y el 30 de junio de 2015 y que contengan la frase "informe financiero" en la línea de asunto. El primer comando crea la búsqueda y el segundo comando ejecuta la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="6ebbf-p108">Here's an example of using PowerShell to search all mailboxes in your organization. The search query returns all messages sent between January 1, 2015 and June 30, 2015 and that contain the phrase "financial report" in the subject line. The first command creates the search, and the second command runs the search.</span></span> 
  
```
New-ComplianceSearch -Name "Search All-Financial Report" -ExchangeLocation all -ContentMatchQuery 'sent>=01/01/2015 AND sent<=06/30/2015 AND subject:"financial report"'
```

```
Start-ComplianceSearch -Identity "Search All-Financial Report"
```

<span data-ttu-id="6ebbf-146">Para obtener más información, consulte [New-ComplianceSearch](https://go.microsoft.com/fwlink/p/?LinkId=517935).</span><span class="sxs-lookup"><span data-stu-id="6ebbf-146">For more information, see [New-ComplianceSearch](https://go.microsoft.com/fwlink/p/?LinkId=517935).</span></span>
  
### <a name="verify-the-number-of-source-mailboxes-in-the-content-search"></a><span data-ttu-id="6ebbf-147">Comprobar el número de buzones de origen en la búsqueda de contenido</span><span class="sxs-lookup"><span data-stu-id="6ebbf-147">Verify the number of source mailboxes in the Content Search</span></span>

<span data-ttu-id="6ebbf-p109">Una búsqueda de contenido devuelve un máximo de 1.000 buzones de correo de origen que contienen los resultados de búsqueda. Si hay más de 1.000 buzones de correo que contienen contenido que coincide con la consulta de búsqueda, sólo los buzones de correo superior 1.000 con los resultados de búsqueda mayoría se incluyen en la búsqueda de contenido que creó en el paso anterior. Por lo que si más de 1.000 buzones de correo contienen los resultados de búsqueda, algunos de esos buzones no se incluirán en la lista de buzones de origen copiado a la búsqueda de exhibición de documentos electrónicos en contexto nuevo creada en el paso 3.</span><span class="sxs-lookup"><span data-stu-id="6ebbf-p109">A Content Search returns a maximum of 1,000 source mailboxes that contain search results. If there are more than 1,000 mailboxes that contain content that matches the search query, only the top 1,000 mailboxes with the most search results are included in the Content Search that you created in the previous step. So if more than 1,000 mailboxes contain search results, some of those mailboxes won't be included in the list of source mailboxes copied to the new In-Place eDiscovery search created in Step 3.</span></span> 
  
<span data-ttu-id="6ebbf-151">Para ayudarle a crear una búsqueda de contenido con no más de buzones de origen 1.000, siga estos pasos para ejecutar un script que muestra el número de buzones de origen (que contienen los resultados de búsqueda) devuelto por la búsqueda de contenido que creó en el paso 1.</span><span class="sxs-lookup"><span data-stu-id="6ebbf-151">To help you create a Content Search with no more than 1,000 source mailboxes, follow these steps to run a script that displays the number of source mailboxes (that contain search results) returned by the Content Search you created in Step 1.</span></span> 
  
1. <span data-ttu-id="6ebbf-p110">Guarde el siguiente texto en un archivo de secuencia de comandos de PowerShell mediante el uso de un sufijo de nombre de archivo de. ps1. Por ejemplo, se podría guardar en un archivo denominado `SourceMailboxes.ps1`.</span><span class="sxs-lookup"><span data-stu-id="6ebbf-p110">Save the following text to a PowerShell script file by using a filename suffix of .ps1. For example, you could save it to a file named `SourceMailboxes.ps1`.</span></span>
    
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

2. <span data-ttu-id="6ebbf-154">En seguridad y cumplimiento de centro de PowerShell, vaya a la carpeta donde se encuentra la secuencia de comandos que creó en el paso anterior y, a continuación, ejecute el script; Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="6ebbf-154">In Security & Compliance Center PowerShell, go to the folder where the script you created in the previous step is located, and then run the script; for example:</span></span>
    
    ```
    .\SourceMailboxes.ps1
    ```

3. <span data-ttu-id="6ebbf-155">Cuando el script se lo pida, escriba el nombre de la búsqueda de contenido que creó en el paso 1.</span><span class="sxs-lookup"><span data-stu-id="6ebbf-155">When prompted by the script, type the name of the Content Search that you created in Step 1.</span></span>
    
    <span data-ttu-id="6ebbf-156">El script muestra el número de buzones de origen que contienen los resultados de la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="6ebbf-156">The script displays the number of source mailboxes that contain search results.</span></span>
    
<span data-ttu-id="6ebbf-p111">Si hay más de 1.000 buzones de correo de origen, pruebe a crear las búsquedas de contenido de dos (o más). Por ejemplo, buscar la mitad de los buzones de correo de su organización en una búsqueda de contenido y la otra mitad en búsqueda de contenido de otra. También puede cambiar los criterios de búsqueda para reducir el número de buzones que contienen resultados de búsqueda. Por ejemplo, podría incluir un intervalo de fechas o perfeccionar la consulta de palabra clave.</span><span class="sxs-lookup"><span data-stu-id="6ebbf-p111">If there are more than 1,000 source mailboxes, try creating two (or more) Content Searches. For example, search half of your organization's mailboxes in one Content Search and the other half in another Content Search. You could also change the search criteria to reduce the number of mailboxes that contain search results. For example, you could include a date range or refine the keyword query.</span></span>
  
## <a name="step-2-connect-to-the-security-amp-compliance-center-and-exchange-online-in-a-single-remote-powershell-session"></a><span data-ttu-id="6ebbf-161">Paso 2: Conectarse a la seguridad &amp; centro de cumplimiento y Exchange Online en una sola sesión de PowerShell remota</span><span class="sxs-lookup"><span data-stu-id="6ebbf-161">Step 2: Connect to the Security &amp; Compliance Center and Exchange Online in a single remote PowerShell session</span></span>

<span data-ttu-id="6ebbf-p112">El siguiente paso es conectar Windows PowerShell para ambos la seguridad &amp; centro de cumplimiento y a la organización de Exchange Online. Esto es necesario porque la secuencia de comandos que se ejecutan en el paso 3 requiere acceso a los cmdlets de búsqueda de contenido en la seguridad &amp; centro de cumplimiento y los cmdlets de exhibición de documentos electrónicos en contexto en Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="6ebbf-p112">The next step is to connect Windows PowerShell to both the Security &amp; Compliance Center and to your Exchange Online organization. This is necessary because the script that you run in Step 3 requires access to the Content Search cmdlets in the Security &amp; Compliance Center and the In-Place eDiscovery cmdlets in Exchange Online.</span></span>
  
1. <span data-ttu-id="6ebbf-p113">Guarde el siguiente texto en un archivo de secuencia de comandos de Windows PowerShell mediante el uso de un sufijo de nombre de archivo de. ps1. Por ejemplo, se podría guardar en un archivo denominado `ConnectEXO-CC.ps1`.</span><span class="sxs-lookup"><span data-stu-id="6ebbf-p113">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1. For example, you could save it to a file named `ConnectEXO-CC.ps1`.</span></span>
    
    ```
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.outlook.com/powershell-liveid -Credential $UserCredential -Authentication Basic -AllowRedirection
    Import-PSSession $Session -DisableNameChecking
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Credential $UserCredential -Authentication Basic -AllowRedirection
    Import-PSSession $Session -AllowClobber -DisableNameChecking
    $Host.UI.RawUI.WindowTitle = $UserCredential.UserName + " (Exchange Online + Compliance Center)"
    ```

2. <span data-ttu-id="6ebbf-166">En el equipo local, abra Windows PowerShell, vaya a la carpeta donde se encuentra la secuencia de comandos que creó en el paso anterior y, a continuación, ejecute el script; Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="6ebbf-166">On your local computer, open Windows PowerShell, go to the folder where the script that you created in the previous step is located, and then run the script; for example:</span></span>
    
    ```
    .\ConnectEXO-CC.ps1
    ```

<span data-ttu-id="6ebbf-p114">¿Cómo sé si ha funcionado? Después de ejecutar el script, cmdlets de la seguridad &amp; centro de cumplimiento y Exchange Online se importan en la sesión de PowerShell local. Si no recibe algún error, conectado correctamente. Es una prueba rápida ejecutar una seguridad &amp; centro de cumplimiento cmdlet — por ejemplo, **Install-UnifiedCompliancePrerequisite** — y un cmdlet de Exchange Online, por ejemplo, **Get-Mailbox**.</span><span class="sxs-lookup"><span data-stu-id="6ebbf-p114">How do you know if this worked? After you run the script, cmdlets from the Security &amp; Compliance Center and Exchange Online are imported into your local PowerShell session. If you don't receive any errors, you connected successfully. A quick test is to run a Security &amp; Compliance Center cmdlet—for example, **Install-UnifiedCompliancePrerequisite** —and an Exchange Online cmdlet, such as **Get-Mailbox**.</span></span> 
  
## <a name="step-3-run-the-script-to-create-an-in-place-ediscovery-search-from-the-content-search"></a><span data-ttu-id="6ebbf-171">Paso 3: Ejecutar el script para crear una búsqueda de eDiscovery local a partir de la búsqueda de contenido</span><span class="sxs-lookup"><span data-stu-id="6ebbf-171">Step 3: Run the script to create an In-Place eDiscovery search from the Content Search</span></span>

<span data-ttu-id="6ebbf-p115">Después de crear la sesión de PowerShell dual en el paso 2, el siguiente paso es ejecutar un script que se va a convertir una búsqueda de contenido existente a una búsqueda de exhibición de documentos electrónicos en contexto. Aquí es lo que hace la secuencia de comandos:</span><span class="sxs-lookup"><span data-stu-id="6ebbf-p115">After you create the dual PowerShell session in Step 2, the next step is to run a script that will convert an existing Content Search to an In-Place eDiscovery search. Here's what the script does:</span></span>
  
- <span data-ttu-id="6ebbf-174">Le pide el nombre de la búsqueda de contenido que quiere convertir.</span><span class="sxs-lookup"><span data-stu-id="6ebbf-174">Prompts you for the name of the Content Search to convert.</span></span>
    
- <span data-ttu-id="6ebbf-p116">Comprueba que se ha completado la búsqueda de contenido. Si la búsqueda de contenido no devuelve ningún resultado, no se creará el eDiscovery local.</span><span class="sxs-lookup"><span data-stu-id="6ebbf-p116">Verifies that the Content Search has completed running. If the Content Search doesn't return any results, and In-Place eDiscovery won't be created.</span></span>
    
- <span data-ttu-id="6ebbf-177">Guarda una lista de los buzones de origen de la búsqueda de contenido que contienen los resultados de la búsqueda en una variable.</span><span class="sxs-lookup"><span data-stu-id="6ebbf-177">Saves a list of the source mailboxes from the Content Search that contain search results to a variable.</span></span>
    
- <span data-ttu-id="6ebbf-p117">Crea una nueva búsqueda de exhibición de documentos electrónicos local con las propiedades siguientes. Tenga en cuenta que la búsqueda nueva no se inicia. Empezará en el paso 4.</span><span class="sxs-lookup"><span data-stu-id="6ebbf-p117">Creates a new In-Place eDiscovery search, with the following properties. Note that the new search isn't started. You'll start it in step 4.</span></span>
    
  - <span data-ttu-id="6ebbf-p118">**Nombre** : el nombre de la nueva búsqueda usa este formato: \<nombre de búsqueda de contenido\>_MBSearch1. Si se vuelva a ejecuta la secuencia de comandos y utilizar el mismo origen de búsqueda de contenido, la búsqueda se denominará \<nombre de búsqueda de contenido\>_MBSearch2.</span><span class="sxs-lookup"><span data-stu-id="6ebbf-p118">**Name** - The name of the new search uses this format: \<Name of Content Search\>_MBSearch1. If you run the script again and use the same source Content Search, the search will be named \<Name of Content Search\>_MBSearch2.</span></span>
    
  - <span data-ttu-id="6ebbf-183">**Buzones de origen** - todos los buzones de la búsqueda de contenido que contienen resultados de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="6ebbf-183">**Source mailboxes** - All mailboxes from the Content Search that contain search results.</span></span> 
    
  - <span data-ttu-id="6ebbf-p119">**Consulta de búsqueda** - la nueva búsqueda usa la consulta de búsqueda de la búsqueda de contenido. Si la búsqueda de contenido incluye todo el contenido (donde la consulta de búsqueda está en blanco) la nueva búsqueda también tendrán una consulta de búsqueda en blanco e incluirá todo el contenido que se encuentra en los buzones de origen.</span><span class="sxs-lookup"><span data-stu-id="6ebbf-p119">**Search query** - The new search uses the search query from the Content Search. If the Content Search includes all content (where the search query is blank) the new search will also have a blank search query and will include all content found in the source mailboxes.</span></span> 
    
  - <span data-ttu-id="6ebbf-p120">**Estimación de búsqueda solo** - la nueva búsqueda está marcado como una búsqueda de estimación. No copia los resultados de búsqueda a un buzón de detección después de iniciarlo.</span><span class="sxs-lookup"><span data-stu-id="6ebbf-p120">**Estimate only search** - The new search is marked as an estimate-only search. It won't copy search results to a discovery mailbox after you start it.</span></span> 
    
1. <span data-ttu-id="6ebbf-p121">Guarde el siguiente texto en un archivo de secuencia de comandos de Windows PowerShell mediante el uso de un sufijo de nombre de archivo de ps1. Por ejemplo, se podría guardar en un archivo denominado `CreateMBSearchFromComplianceSearch.ps1`.</span><span class="sxs-lookup"><span data-stu-id="6ebbf-p121">Save the following text to a Windows PowerShell script file by using a filename suffix of ps1. For example, you could save it to a file named `CreateMBSearchFromComplianceSearch.ps1`.</span></span>
    
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

2. <span data-ttu-id="6ebbf-190">En la sesión de Windows PowerShell que creó en el paso 2, vaya a la carpeta donde se encuentra la secuencia de comandos que creó en el paso anterior y, a continuación, ejecute el script; Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="6ebbf-190">In the Windows PowerShell session that you created in Step 2, go to the folder where the script that you created in the previous step is located, and then run the script; for example:</span></span>
    
    ```
    .\CreateMBSearchFromComplianceSearch.ps1
    ```

3. <span data-ttu-id="6ebbf-191">Cuando se le solicite la secuencia de comandos, escriba el nombre de la búsqueda de contenido que va a convertir a una búsqueda de exhibición de documentos electrónicos local (por ejemplo, la búsqueda que creó en el paso 1) y, a continuación, presione **ENTRAR**.</span><span class="sxs-lookup"><span data-stu-id="6ebbf-191">When prompted by the script, type the name of the Content Search that you want to covert to an In-Place eDiscovery search (for example, the search that you created in Step 1), and then press **Enter**.</span></span>
    
    <span data-ttu-id="6ebbf-p122">Si el script funciona, se crea una nueva búsqueda de exhibición de documentos electrónicos local con un estado **NotStarted**. Ejecute el comando  `Get-MailboxSearch <Name of Content Search>_MBSearch1 | FL` para mostrar las propiedades de la nueva búsqueda.</span><span class="sxs-lookup"><span data-stu-id="6ebbf-p122">If the script is successful, a new In-Place eDiscovery search is created with a status of **NotStarted**. Run the command  `Get-MailboxSearch <Name of Content Search>_MBSearch1 | FL` to display the properties of the new search.</span></span> 
  
## <a name="step-4-start-the-in-place-ediscovery-search"></a><span data-ttu-id="6ebbf-194">Paso 4: Iniciar la búsqueda de exhibición de documentos electrónicos local</span><span class="sxs-lookup"><span data-stu-id="6ebbf-194">Step 4: Start the In-Place eDiscovery search</span></span>

<span data-ttu-id="6ebbf-p123">El script que se ejecuta en el paso 3 crea una nueva búsqueda de exhibición de documentos electrónicos local, pero no la inicia. El siguiente paso es iniciar la búsqueda para obtener una estimación de los resultados de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="6ebbf-p123">The script that you run in Step 3 creates a new In-Place eDiscovery search, but doesn't start it. The next step is to start the search so you can get an estimate of the search results.</span></span>
  
1. <span data-ttu-id="6ebbf-197">En el centro de administración de Exchange (EAC), vaya a **administración de cumplimiento** \> **exhibición de documentos electrónicos en contexto &amp; suspensión**.</span><span class="sxs-lookup"><span data-stu-id="6ebbf-197">In the Exchange admin center (EAC), go to **Compliance management** \> **In-Place eDiscovery &amp; Hold**.</span></span>
    
2. <span data-ttu-id="6ebbf-198">En la vista de lista, seleccione la búsqueda de exhibición de documentos electrónicos local que se creó en el paso 3.</span><span class="sxs-lookup"><span data-stu-id="6ebbf-198">In the list view, select the In-Place eDiscovery search that you created in Step 3.</span></span>
    
3. <span data-ttu-id="6ebbf-199">Haga clic en **búsqueda** ![icono de búsqueda](media/5f6f9463-50e9-460b-8738-b67e759c2efc.gif) \> **los resultados de búsqueda de estimación** para iniciar la búsqueda y devolver una estimación del tamaño total y el número de elementos devueltos por la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="6ebbf-199">Click **Search** ![Search icon](media/5f6f9463-50e9-460b-8738-b67e759c2efc.gif) \> **Estimate search results** to start the search and return an estimate of the total size and number of items returned by the search.</span></span> 
    
    <span data-ttu-id="6ebbf-p124">Las estimaciones se muestran en el panel de detalles. Haga clic en **Actualizar** ![icono de actualización](media/O365-MDM-Policy-RefreshIcon.gif) para actualizar la información que se muestra en el panel de detalles.</span><span class="sxs-lookup"><span data-stu-id="6ebbf-p124">The estimates are displayed in the details pane. Click **Refresh** ![Refresh icon](media/O365-MDM-Policy-RefreshIcon.gif) to update the information displayed in the details pane.</span></span> 
    
4. <span data-ttu-id="6ebbf-202">Para obtener una vista previa de los resultados una vez completada la búsqueda, haga clic en **Vista previa de los resultados de búsqueda** en el panel de detalles.</span><span class="sxs-lookup"><span data-stu-id="6ebbf-202">To preview the results after the search is completed, click **Preview search results** in the details pane.</span></span>
  
## <a name="next-steps-after-creating-and-running-the-in-place-ediscovery-search"></a><span data-ttu-id="6ebbf-203">Pasos siguientes después de crear y ejecutar la búsqueda de exhibición de documentos electrónicos local</span><span class="sxs-lookup"><span data-stu-id="6ebbf-203">Next steps after creating and running the In-Place eDiscovery search</span></span>

<span data-ttu-id="6ebbf-204">Después de crear e iniciar la búsqueda de exhibición de documentos electrónicos local que el script ha creado en el paso 3, puede usar el flujo de trabajo normal de la exhibición de documentos electrónicos local para realizar distintas acciones de exhibición de documentos electrónicos en los resultados de la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="6ebbf-204">After you create and start the In-Place eDiscovery search that was created by the script in Step 3, you can use the normal In-Place eDiscovery workflow to perform different eDiscovery actions on the search results.</span></span>
  
### <a name="create-an-in-place-hold"></a><span data-ttu-id="6ebbf-205">Crear una Conservación local</span><span class="sxs-lookup"><span data-stu-id="6ebbf-205">Create an In-Place Hold</span></span>

1. <span data-ttu-id="6ebbf-206">En el EAC, vaya a **administración de cumplimiento** \> **exhibición de documentos electrónicos en contexto &amp; suspensión**.</span><span class="sxs-lookup"><span data-stu-id="6ebbf-206">In the EAC, go to **Compliance management** \> **In-Place eDiscovery &amp; Hold**.</span></span>
    
2. <span data-ttu-id="6ebbf-207">En la vista de lista, seleccione la búsqueda de exhibición de documentos electrónicos local que creó en el paso 3 y, a continuación, haga clic en **Editar** ![icono Editar](media/O365_MDM_CreatePolicy_EditIcon.gif).</span><span class="sxs-lookup"><span data-stu-id="6ebbf-207">In the list view, select the In-Place eDiscovery search that you created in Step 3, and then click **Edit** ![Edit icon](media/O365_MDM_CreatePolicy_EditIcon.gif).</span></span>
    
3. <span data-ttu-id="6ebbf-208">En la página **Conservación local**, active la casilla **Pausar el contenido que coincida con la consulta de búsqueda en los buzones seleccionados** y después seleccione una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="6ebbf-208">On the **In-Place Hold** page, select the **Place content matching the search query in selected mailboxes on hold** check box and then select one of the following options:</span></span> 
    
  - <span data-ttu-id="6ebbf-p125">**Espera indefinidamente** - elija esta opción para colocar los elementos devueltos por la búsqueda en una espera indefinida. Se conservarán los elementos en espera hasta que se quite la búsqueda en el buzón de correo o quita la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="6ebbf-p125">**Hold indefinitely** - Choose this option to place items returned by the search on an indefinite hold. Items on hold will be preserved until you remove the mailbox from the search or remove the search.</span></span> 
    
  - <span data-ttu-id="6ebbf-p126">**Especificar número de días para retener elementos con respecto a su fecha de recepción** : elija esta opción para retener elementos durante un período específico. La duración se calcula a partir la fecha de un elemento de buzón de correo se ha recibido o creado.</span><span class="sxs-lookup"><span data-stu-id="6ebbf-p126">**Specify number of days to hold items relative to their received date** - Choose this option to hold items for a specific period. The duration is calculated from the date a mailbox item is received or created.</span></span> 
    
4. <span data-ttu-id="6ebbf-213">Haga clic en **Guardar** para crear la conservación local y reiniciar la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="6ebbf-213">Click **Save** to create the In-Place Hold and restart the search.</span></span> 
    
[<span data-ttu-id="6ebbf-214">Return to top</span><span class="sxs-lookup"><span data-stu-id="6ebbf-214">Return to top</span></span>](use-content-search-in-ediscovery.md#top)
  
### <a name="copy-the-search-results"></a><span data-ttu-id="6ebbf-215">Copiar los resultados de la búsqueda</span><span class="sxs-lookup"><span data-stu-id="6ebbf-215">Copy the search results</span></span>

1. <span data-ttu-id="6ebbf-216">En el EAC, vaya a **administración de cumplimiento** \> **exhibición de documentos electrónicos en contexto &amp; suspensión**.</span><span class="sxs-lookup"><span data-stu-id="6ebbf-216">In the EAC, go to **Compliance management** \> **In-Place eDiscovery &amp; Hold**.</span></span>
    
2. <span data-ttu-id="6ebbf-217">En la vista de lista, seleccione la búsqueda de exhibición de documentos electrónicos local que ha creado en el paso 3.</span><span class="sxs-lookup"><span data-stu-id="6ebbf-217">In the list view, select the In-Place eDiscovery search that you created in Step 3.</span></span>
    
3. <span data-ttu-id="6ebbf-218">Haga clic en **búsqueda** ![icono de búsqueda](media/5f6f9463-50e9-460b-8738-b67e759c2efc.gif)y, a continuación, haga clic en **copiar los resultados de búsqueda** de la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="6ebbf-218">Click **Search** ![Search icon](media/5f6f9463-50e9-460b-8738-b67e759c2efc.gif), and then click **Copy search results** from the drop-down list.</span></span> 
    
4. <span data-ttu-id="6ebbf-219">En **Copiar resultados de búsqueda**, seleccione entre las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="6ebbf-219">In **Copy Search Results**, select from the following options:</span></span>
    
    - <span data-ttu-id="6ebbf-220">**Incluir elementos buscar** - Active esta casilla de verificación para incluir los elementos de buzón de correo que no se ha podido buscar (por ejemplo, los mensajes con datos adjuntos de tipos de archivo que se han podido indizar mediante la búsqueda de Exchange).</span><span class="sxs-lookup"><span data-stu-id="6ebbf-220">**Include unsearchable items** - Select this check box to include mailbox items that couldn't be searched (for example, messages with attachments of file types that couldn't be indexed by Exchange Search).</span></span> 
    
    - <span data-ttu-id="6ebbf-p127">**Habilitar la desduplicación** - Active esta casilla de verificación para excluir los mensajes duplicados. Una sola instancia de un mensaje se copiará en el buzón de detección.</span><span class="sxs-lookup"><span data-stu-id="6ebbf-p127">**Enable de-duplication** - Select this check box to exclude duplicate messages. Only a single instance of a message will be copied to the discovery mailbox.</span></span> 
    
    - <span data-ttu-id="6ebbf-223">**Habilitar el registro completo** - Active esta casilla de verificación para incluir un registro completo en los resultados de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="6ebbf-223">**Enable full logging** - Select this check box to include a full log in search results.</span></span> 
    
    - <span data-ttu-id="6ebbf-224">**Envíeme un correo electrónico cuando se complete la copia** - Active esta casilla de verificación para recibir una notificación de correo electrónico cuando se complete la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="6ebbf-224">**Send me mail when the copy is completed** - Select this check box to get an email notification when the search is completed.</span></span> 
    
    - <span data-ttu-id="6ebbf-225">**Copiar los resultados a este buzón de correo de detección** - haga clic en **Examinar** para seleccionar el buzón de detección donde desea que los resultados de búsqueda copiado en.</span><span class="sxs-lookup"><span data-stu-id="6ebbf-225">**Copy results to this discovery mailbox** - Click **Browse** to select the discovery mailbox where you want the search results copied to.</span></span> 
    
5. <span data-ttu-id="6ebbf-226">Haga clic en **Copiar** para iniciar el proceso de copia de los resultados de la búsqueda en el buzón de correo de detección especificado.</span><span class="sxs-lookup"><span data-stu-id="6ebbf-226">Click **Copy** to start the process to copy the search results to the specified discovery mailbox.</span></span> 
    
6. <span data-ttu-id="6ebbf-227">Haga clic en **Actualizar** ![icono de actualización](media/O365-MDM-Policy-RefreshIcon.gif) para actualizar la información sobre el estado de copia que se muestra en el panel de detalles.</span><span class="sxs-lookup"><span data-stu-id="6ebbf-227">Click **Refresh** ![Refresh icon](media/O365-MDM-Policy-RefreshIcon.gif) to update the information about the copying status that is displayed in the details pane.</span></span> 
    
7. <span data-ttu-id="6ebbf-228">Una vez que la copia esté completa, haga clic en **Abrir** para abrir el buzón de correo de detección y ver los resultados de la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="6ebbf-228">When copying is complete, click **Open** to open the discovery mailbox to view the search results.</span></span> 
  
### <a name="export-the-search-results"></a><span data-ttu-id="6ebbf-229">Exportar los resultados de la búsqueda</span><span class="sxs-lookup"><span data-stu-id="6ebbf-229">Export the search results</span></span>

1. <span data-ttu-id="6ebbf-230">En el EAC, vaya a **administración de cumplimiento** \> **exhibición de documentos electrónicos en contexto &amp; suspensión**.</span><span class="sxs-lookup"><span data-stu-id="6ebbf-230">In the EAC, go to **Compliance management** \> **In-Place eDiscovery &amp; Hold**.</span></span>
    
2. <span data-ttu-id="6ebbf-231">En la vista de lista, seleccione la búsqueda de exhibición de documentos electrónicos local que se creó en el paso 3 y luego haga clic en **Exportar a un archivo PST**.</span><span class="sxs-lookup"><span data-stu-id="6ebbf-231">In the list view, select the In-Place eDiscovery search that you created in Step 3, and then click **Export to a PST file**.</span></span>
    
3. <span data-ttu-id="6ebbf-232">En la ventana de la **herramienta de exportación de PST de exhibición de documentos electrónicos**:</span><span class="sxs-lookup"><span data-stu-id="6ebbf-232">In the **eDiscovery PST Export Tool** window, do the following:</span></span> 
    
    - <span data-ttu-id="6ebbf-233">Haga clic en **Examinar** para especificar la ubicación donde quiere descargar el archivo PST.</span><span class="sxs-lookup"><span data-stu-id="6ebbf-233">Click **Browse** to specify the location where you want to download the PST file.</span></span> 
    
    - <span data-ttu-id="6ebbf-p128">Haga clic en la casilla **Habilitar desduplicación** para excluir los mensajes duplicados. Solo se incluirá una instancia de cada mensaje en el archivo PST.</span><span class="sxs-lookup"><span data-stu-id="6ebbf-p128">Click the **Enable deduplication** checkbox to exclude duplicate messages. Only a single instance of a message will be included in the PST file.</span></span> 
    
    - <span data-ttu-id="6ebbf-p129">Haga clic en la casilla **Incluir elementos no aptos para la búsqueda** si quiere incluir los elementos del buzón que no pudieron buscar (por ejemplo, los mensajes con datos adjuntos de tipos de archivo que Exchange Search no pudo indizar). Los elementos no aptos para la búsqueda se exportan a un archivo PST independiente.</span><span class="sxs-lookup"><span data-stu-id="6ebbf-p129">Click the **Include unsearchable items** checkbox to include mailbox items that couldn't be searched (for example, messages with attachments of file types that couldn't be indexed by Exchange Search). Unsearchable items are exported to a separate PST file.</span></span> 
    
4. <span data-ttu-id="6ebbf-238">Haga clic en **Inicio** para exportar los resultados de búsqueda a un archivo PST.</span><span class="sxs-lookup"><span data-stu-id="6ebbf-238">Click **Start** to export the search results to a PST file.</span></span> 
    
    <span data-ttu-id="6ebbf-239">Se mostrará una ventana con información de estado sobre el proceso de exportación.</span><span class="sxs-lookup"><span data-stu-id="6ebbf-239">A window is displayed that contains status information about the export process.</span></span>
