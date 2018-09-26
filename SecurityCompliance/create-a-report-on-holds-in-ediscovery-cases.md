---
title: Crear un informe en las suspensiones en los casos de exhibición de documentos electrónicos en Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 9/11/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid: MOE150
ms.assetid: cca08d26-6fbf-4b2c-b102-b226e4cd7381
description: Use la secuencia de comandos de este artículo para generar un informe que contiene información acerca de todas las suspensiones a las que están asociadas con los casos de exhibición de documentos electrónicos en la seguridad de Office 365 &amp; centro de cumplimiento.
ms.openlocfilehash: b6cef2824002d7e45e4f500bc6c1e9bc880cbd41
ms.sourcegitcommit: 7956955cd919f6e00b64e4506605a743c5872549
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/26/2018
ms.locfileid: "25038213"
---
# <a name="create-a-report-on-holds-in-ediscovery-cases-in-office-365"></a><span data-ttu-id="68fd7-103">Crear un informe en las suspensiones en los casos de exhibición de documentos electrónicos en Office 365</span><span class="sxs-lookup"><span data-stu-id="68fd7-103">Create a report on holds in eDiscovery cases in Office 365</span></span>
  
<span data-ttu-id="68fd7-p101">La secuencia de comandos en este artículo permite a los administradores de la exhibición de documentos electrónicos y los administradores de exhibición de documentos electrónicos generan un informe que contiene información acerca de todas las suspensiones que se asocian con los casos de exhibición de documentos electrónicos en la seguridad de Office 365 &amp; centro de cumplimiento. El informe contiene información como el nombre del caso de una suspensión está asociado con las ubicaciones de contenido que se colocan en espera, y si la suspensión está basado en la consulta. Si hay casos en los que no tengan ninguna suspensión, la secuencia de comandos creará un informe adicional con una lista de los casos sin suspensiones.</span><span class="sxs-lookup"><span data-stu-id="68fd7-p101">The script in this article lets eDiscovery administrators and eDiscovery managers generate a report that contains information about all holds that are associated with eDiscovery cases in the Office 365 Security &amp; Compliance Center. The report contains information such as the name of the case a hold is associated with, the content locations that are placed on hold, and whether the hold is query-based. If there are cases that don't have any holds, the script will create an additional report with a list of cases without holds.</span></span>

<span data-ttu-id="68fd7-107">Vea la sección [obtener más información](#more-information) para obtener una descripción detallada de la información incluida en el informe.</span><span class="sxs-lookup"><span data-stu-id="68fd7-107">See the [More information](#more-information) section for a detailed description of the information included in the report.</span></span> 
  
## <a name="before-you-begin"></a><span data-ttu-id="68fd7-108">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="68fd7-108">Before you begin</span></span>

- <span data-ttu-id="68fd7-p102">Para generar un informe en todos los casos de exhibición de documentos electrónicos en su organización, debe ser un administrador de exhibición de documentos en su organización. Si es un administrador de exhibición de documentos electrónicos, el informe sólo incluirá información acerca de los casos que puede tener acceso. Para obtener más información acerca de los permisos de exhibición de documentos electrónicos, vea [asignar permisos de exhibición de documentos electrónicos en la seguridad de Office 365 &amp; centro de cumplimiento](assign-ediscovery-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="68fd7-p102">To generate a report on all eDiscovery cases in your organization, you have to be an eDiscovery Administrator in your organization. If you are an eDiscovery Manager, the report will only include information about the cases that you can access. For more information about eDiscovery permissions, see [Assign eDiscovery permissions in the Office‍ 365 Security &amp; Compliance Center](assign-ediscovery-permissions.md).</span></span>
    
- <span data-ttu-id="68fd7-p103">La secuencia de comandos en este artículo tiene el tratamiento de errores mínima. El propósito principal es crear rápidamente informe sobre las suspensiones que se asocian con los casos de exhibición de documentos electrónicos en su organización.</span><span class="sxs-lookup"><span data-stu-id="68fd7-p103">The script in this article has minimal error handling. The primary purpose is to quickly create report about the holds that are associated with the eDiscovery cases in your organization.</span></span>
    
- <span data-ttu-id="68fd7-p104">Los scripts de ejemplo que se proporcionan en este tema no son compatibles con ningún servicio o programa de soporte técnico estándar de Microsoft. Los scripts de ejemplo se proporcionan tal cual, sin garantía de ningún tipo. Además, Microsoft se exime de todas las garantías implícitas, incluidas (sin limitación) las garantías implícitas de comerciabilidad o idoneidad para un propósito específico. El usuario asume todos los riesgos derivados del uso o del rendimiento de los scripts de ejemplo y la documentación. Microsoft, sus autores o cualquier persona relacionada con la creación, producción o entrega de los scripts no serán en ningún caso responsables de cualesquiera daños (incluidos, sin limitación, los daños producidos por la pérdida de beneficios comerciales, interrupción de la actividad comercial, pérdida de información empresarial u otras pérdidas económicas) derivados del uso o de la imposibilidad de uso de los scripts de ejemplo o la documentación, incluso aunque Microsoft tenga constancia de la posibilidad de que dichos daños se produzcan.</span><span class="sxs-lookup"><span data-stu-id="68fd7-p104">The sample scripts provided in this topic aren't supported under any Microsoft standard support program or service. The sample scripts are provided AS IS without warranty of any kind. Microsoft further disclaims all implied warranties including, without limitation, any implied warranties of merchantability or of fitness for a particular purpose. The entire risk arising out of the use or performance of the sample scripts and documentation remains with you. In no event shall Microsoft, its authors, or anyone else involved in the creation, production, or delivery of the scripts be liable for any damages whatsoever (including, without limitation, damages for loss of business profits, business interruption, loss of business information, or other pecuniary loss) arising out of the use of or inability to use the sample scripts or documentation, even if Microsoft has been advised of the possibility of such damages.</span></span>
    
## <a name="step-1-connect-to-the-security-amp-compliance-center-using-remote-powershell"></a><span data-ttu-id="68fd7-119">Paso 1: Conectar a la seguridad &amp; centro de cumplimiento de normas mediante PowerShell remoto</span><span class="sxs-lookup"><span data-stu-id="68fd7-119">Step 1: Connect to the Security &amp; Compliance Center using Remote PowerShell</span></span>

<span data-ttu-id="68fd7-120">El primer paso es conectar Windows PowerShell a la seguridad &amp; centro de cumplimiento de normas de la organización.</span><span class="sxs-lookup"><span data-stu-id="68fd7-120">The first step is to connect Windows PowerShell to the Security &amp; Compliance Center for your organization.</span></span>
  
1. <span data-ttu-id="68fd7-121">Guarde el siguiente texto en un archivo de secuencia de comandos de Windows PowerShell mediante el uso de un sufijo de nombre de archivo de. ps1; Por ejemplo, `ConnectSCC.ps1`.</span><span class="sxs-lookup"><span data-stu-id="68fd7-121">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `ConnectSCC.ps1`.</span></span> 
    
      ```
      # Get login credentials 
      $UserCredential = Get-Credential 
      $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Credential $UserCredential -Authentication Basic -AllowRedirection 
      Import-PSSession $Session -AllowClobber -DisableNameChecking 
      $Host.UI.RawUI.WindowTitle = $UserCredential.UserName + " (Office 365 Security &amp; Compliance Center)" 
    ```

2. <span data-ttu-id="68fd7-122">En el equipo local, abra Windows PowerShell y vaya a la carpeta donde guardó la secuencia de comandos.</span><span class="sxs-lookup"><span data-stu-id="68fd7-122">On your local computer, open Windows PowerShell and go to the folder where you saved the script.</span></span> 
    
3. <span data-ttu-id="68fd7-123">Ejecute la secuencia de comandos; Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="68fd7-123">Run the script; for example:</span></span>

    ```
    .\ConnectSCC.ps1
    ```
   
4. <span data-ttu-id="68fd7-124">Cuando se le pidan sus credenciales, escriba su dirección de correo electrónico y contraseña y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="68fd7-124">When prompted for your credentials, enter your email address and password, and then click **OK**.</span></span> 
  
## <a name="step-2-run-the-script-to-report-on-holds-associated-with-ediscovery-cases"></a><span data-ttu-id="68fd7-125">Paso 2: Ejecutar el script para informar sobre las suspensiones asociado con los casos de exhibición de documentos electrónicos</span><span class="sxs-lookup"><span data-stu-id="68fd7-125">Step 2: Run the script to report on holds associated with eDiscovery cases</span></span>

<span data-ttu-id="68fd7-126">Una vez conectado a la seguridad &amp; centro de cumplimiento con PowerShell remoto, el siguiente paso es crear y ejecutar la secuencia de comandos que recopila información acerca de los casos de exhibición de documentos electrónicos en su organización.</span><span class="sxs-lookup"><span data-stu-id="68fd7-126">After you've connected to the Security &amp; Compliance Center with remote PowerShell, the next step is to create and run the script that collects information about the eDiscovery cases in your organization.</span></span> 
  
1. <span data-ttu-id="68fd7-127">Guarde el siguiente texto en un archivo de secuencia de comandos de Windows PowerShell mediante el uso de un sufijo de nombre de archivo de. ps1; Por ejemplo, CaseHoldsReport.ps1.</span><span class="sxs-lookup"><span data-stu-id="68fd7-127">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, CaseHoldsReport.ps1.</span></span> 
    
  ```
#script begin
" " 
write-host "***********************************************"
write-host "   Office 365 Security & Compliance Center   " -foregroundColor yellow -backgroundcolor darkgreen
write-host "        eDiscovery cases - Holds report         " -foregroundColor yellow -backgroundcolor darkgreen 
write-host "***********************************************"
" " 
#prompt users to specify a path to store the output files
$time=get-date
$Path = Read-Host 'Enter a file path to save the report to a .csv file'
$outputpath=$Path+'\'+'CaseHoldsReport'+' '+$time.day+'-'+$time.month+'-'+$time.year+' '+$time.hour+'.'+$time.minute+'.csv'
$noholdsfilepath=$Path+'\'+'CaseswithNoHolds'+' '+$time.day+'-'+$time.month+'-'+$time.year+' '+$time.hour+'.'+$time.minute+'.csv'
#add case details to the csv file
function add-tocasereport{
Param([string]$casename,
[String]$casestatus,
[datetime]$casecreatedtime,
[string]$casemembers,
[datetime]$caseClosedDateTime,
[string]$caseclosedby,
[string]$holdname,
[String]$Holdenabled,
[string]$holdcreatedby,
[string]$holdlastmodifiedby,
[string]$ExchangeLocation,
[string]$sharePointlocation,
[string]$ContentMatchQuery,
[datetime]$holdcreatedtime,
[datetime]$holdchangedtime
)
$addRow = New-Object PSObject 
Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Case name" -Value $casename
Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Case status" -Value $casestatus
Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Case members" -Value $casemembers
Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Case created time" -Value $casecreatedtime
Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Case closed time" -Value $caseClosedDateTime
Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Case closed by" -Value $caseclosedby
Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Hold name" -Value $holdname
Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Hold enabled" -Value $Holdenabled
Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Hold created by" -Value $holdcreatedby
Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Hold last changed by" -Value $holdlastmodifiedby
Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Exchange locations" -Value  $ExchangeLocation
Add-Member -InputObject $addRow -MemberType NoteProperty -Name "SharePoint locations" -Value $sharePointlocation
Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Hold query" -Value $ContentMatchQuery
Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Hold created time (UTC)" -Value $holdcreatedtime
Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Hold changed time (UTC)" -Value $holdchangedtime
$allholdreport = $addRow | Select-Object "Case name","Case status","Hold name","Hold enabled","Case members", "Case created time","Case closed time","Case closed by","Exchange locations","SharePoint locations","Hold query","Hold created by","Hold created time (UTC)","Hold last changed by","Hold changed time (UTC)"
$allholdreport | export-csv -path $outputPath -notypeinfo -append -Encoding ascii 
}
#get information on the cases and pass values to the case report function
" "
write-host "Gathering a list of cases and holds..."
" "
$edc =Get-ComplianceCase -ErrorAction SilentlyContinue
foreach($cc in $edc)
{
write-host "Working on case :" $cc.name
if($cc.status -eq 'Closed')
{
$cmembers = ((Get-ComplianceCaseMember -Case $cc.name).windowsLiveID)-join ';'
add-tocasereport -casename $cc.name -casestatus $cc.Status -caseclosedby $cc.closedby -caseClosedDateTime $cc.ClosedDateTime -casemembers $cmembers 
}
else{
$cmembers = ((Get-ComplianceCaseMember -Case $cc.name).windowsLiveID)-join ';'
$policies = Get-CaseHoldPolicy -Case $cc.Name | %{ Get-CaseHoldPolicy $_.Name -Case $_.CaseId -DistributionDetail}
if ($policies -ne $NULL)
{
foreach ($policy in $policies)
{
$rule=Get-CaseHoldRule -Policy $policy.name
add-tocasereport -casename $cc.name -casemembers $cmembers -casestatus $cc.Status -casecreatedtime $cc.CreatedDateTime -holdname $policy.name -holdenabled $policy.enabled -holdcreatedby $policy.CreatedBy -holdlastmodifiedby $policy.LastModifiedBy -ExchangeLocation (($policy.exchangelocation.name)-join ';') -SharePointLocation (($policy.sharePointlocation.name)-join ';') -ContentMatchQuery $rule.ContentMatchQuery -holdcreatedtime $policy.WhenCreatedUTC -holdchangedtime $policy.WhenChangedUTC
}
}
else{
write-host "No hold policies found in case:" $cc.name -foregroundColor 'Yellow'
" "
[string]$cc.name | out-file -filepath $noholdsfilepath -append 
}
}
}

" "
Write-host "Script complete! Report files saved to this folder: '$Path'"
" "
#script end
  ```

2. <span data-ttu-id="68fd7-128">En la sesión de Windows PowerShell que abrió en el paso 1, vaya a la carpeta donde guardó la secuencia de comandos.</span><span class="sxs-lookup"><span data-stu-id="68fd7-128">In the Windows PowerShell session that opened in Step 1, go to the folder where you saved the script.</span></span> 
    
3. <span data-ttu-id="68fd7-129">Ejecute la secuencia de comandos; Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="68fd7-129">Run the script; for example:</span></span>

    ```
    .\CaseHoldsReport.ps1
    ```

    <span data-ttu-id="68fd7-130">La secuencia de comandos realizará mostrará el mensaje guardar el informe para que una carpeta de destino.</span><span class="sxs-lookup"><span data-stu-id="68fd7-130">The script will prompt for a target folder to save the report to.</span></span> 
    
4. <span data-ttu-id="68fd7-131">Escriba el nombre de ruta de acceso completa de la carpeta que se va a guardar el informe y, a continuación, presione **ENTRAR**.</span><span class="sxs-lookup"><span data-stu-id="68fd7-131">Type the full path name of the folder to save the report to, and then press **Enter**.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="68fd7-p105">Para guardar el informe en la misma carpeta que la secuencia de comandos se encuentra en, escriba un punto (".") cuando se le solicite una carpeta de destino. Para guardar el informe en una subcarpeta en la carpeta donde se encuentra la secuencia de comandos, simplemente escriba el nombre de la subcarpeta.</span><span class="sxs-lookup"><span data-stu-id="68fd7-p105">To save the report in the same folder that the script is located in, type a period (".") when prompted for a target folder. To save the report in a subfolder in the folder where the script is located, just type the name of the subfolder.</span></span> 
  
    <span data-ttu-id="68fd7-p106">La secuencia de comandos empieza a recopilar información acerca de todos los casos de exhibición de documentos electrónicos en su organización. No tener acceso al archivo de informe mientras se está ejecutando la secuencia de comandos. Una vez finalizada la secuencia de comandos, se muestra un mensaje de confirmación en la sesión de Windows PowerShell. Después de que aparezca este mensaje, se puede obtener acceso al informe en la carpeta que especificó en el paso 4. Es el nombre de archivo para el informe de `CaseHoldsReport<DateTimeStamp>.csv`.</span><span class="sxs-lookup"><span data-stu-id="68fd7-p106">The script starts to collect information about all the eDiscovery cases in your organization. Don't access the report file while the script is running. After the script is complete, a confirmation message is displayed in the Windows PowerShell session. After this message is displayed, you can access the report in the folder that you specified in Step 4. The file name for the report is `CaseHoldsReport<DateTimeStamp>.csv`.</span></span>

    <span data-ttu-id="68fd7-p107">Addtionally, la secuencia de comandos también crea un informe con una lista de los casos que no tengan ninguna suspensión. El nombre de archivo para este informe es `CaseswithNoHolds<DateTimeStamp>.csv`.</span><span class="sxs-lookup"><span data-stu-id="68fd7-p107">Addtionally, the script also creates a report with a list of cases that don't have any holds. The file name for this report is `CaseswithNoHolds<DateTimeStamp>.csv`.</span></span>
    
    <span data-ttu-id="68fd7-141">Este es un ejemplo de ejecución del script CaseHoldsReport.ps1.</span><span class="sxs-lookup"><span data-stu-id="68fd7-141">Here's an example of running the CaseHoldsReport.ps1 script.</span></span> 
    
    ![El resultado después de ejecutar la secuencia de comandos CaseHoldsReport.ps1](media/7d312ed5-505e-4ec5-8f06-3571e3524a1a.png)
  
## <a name="more-information"></a><span data-ttu-id="68fd7-143">Más información</span><span class="sxs-lookup"><span data-stu-id="68fd7-143">More information</span></span>

<span data-ttu-id="68fd7-p108">El caso contiene el informe que se crea al ejecutar el script en este artículo contiene la siguiente información sobre cada suspensión. Como se explica anteriormente, debe ser un administrador para devolver información para todas las suspensiones en la organización de exhibición de documentos electrónicos. Para obtener más información acerca de caso de suspensiones, consulte [casos de exhibición de documentos electrónicos en la seguridad de Office 365 &amp; centro de cumplimiento](ediscovery-cases.md).</span><span class="sxs-lookup"><span data-stu-id="68fd7-p108">The case holds report that's created when you run the script in this article contains the following information about each hold. As previously explained, you have to be an eDiscovery Administrator to return information for all holds in your organization. For more information about case holds, see [eDiscovery cases in the Office 365 Security &amp; Compliance Center](ediscovery-cases.md).</span></span>
  
  - <span data-ttu-id="68fd7-147">El nombre de la suspensión y el nombre del caso de exhibición de documentos electrónicos que está asociada la suspensión.</span><span class="sxs-lookup"><span data-stu-id="68fd7-147">The name of the hold and the name of the eDiscovery case that the hold is associated with.</span></span>
    
  - <span data-ttu-id="68fd7-148">Si está o no el caso de exhibición de documentos electrónicos activo o cerrado.</span><span class="sxs-lookup"><span data-stu-id="68fd7-148">Whether or not the eDiscovery case is active or closed.</span></span>
    
  - <span data-ttu-id="68fd7-149">Si la suspensión está habilitada o deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="68fd7-149">Whether or not the hold is enabled or disabled.</span></span>
    
  - <span data-ttu-id="68fd7-p109">Los miembros de los casos de exhibición de documentos electrónicos que está asociada la suspensión. Case (miembros) puede ver o administrar un caso, dependiendo de los permisos de exhibición de documentos electrónicos que se han asignado.</span><span class="sxs-lookup"><span data-stu-id="68fd7-p109">The members of the eDiscovery case that the hold is associated with. Case members can view or manage a case, depending on the eDiscovery permissions they've been assigned.</span></span>
    
  - <span data-ttu-id="68fd7-152">La hora y fecha de que creación de las mayúsculas y minúsculas.</span><span class="sxs-lookup"><span data-stu-id="68fd7-152">The time and date the case was created.</span></span>
    
  - <span data-ttu-id="68fd7-153">Si se cierra un caso, la persona que se cierra y la hora y fecha se ha cerrado.</span><span class="sxs-lookup"><span data-stu-id="68fd7-153">If a case is closed, the person who closed it and the time and date it was closed.</span></span>
    
  - <span data-ttu-id="68fd7-154">Ubicaciones que están en espera de sitios de los buzones de Exchange y SharePoint.</span><span class="sxs-lookup"><span data-stu-id="68fd7-154">The Exchange mailboxes and SharePoint sites locations that are on hold.</span></span>
    
  - <span data-ttu-id="68fd7-155">Si la suspensión está basada en consultas, la sintaxis de consulta.</span><span class="sxs-lookup"><span data-stu-id="68fd7-155">If the hold is query-based, the query syntax.</span></span>
    
  - <span data-ttu-id="68fd7-156">La hora y fecha de que creación de la suspensión y la persona que lo creó.</span><span class="sxs-lookup"><span data-stu-id="68fd7-156">The time and date the hold was created and the person who created it.</span></span>
    
  - <span data-ttu-id="68fd7-157">La hora y fecha de que la suspensión se modificó por última vez y la persona que haya cambiado.</span><span class="sxs-lookup"><span data-stu-id="68fd7-157">The time and date the hold was last changed and the person who changed it.</span></span>
