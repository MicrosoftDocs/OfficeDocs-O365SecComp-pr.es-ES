---
title: Crear un informe sobre suspensiones en casos de eDiscovery en Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 9/11/2017
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid: MOE150
ms.assetid: cca08d26-6fbf-4b2c-b102-b226e4cd7381
description: Use el script de este artículo para generar un informe que contenga información sobre todas las suspensiones asociadas con casos de eDiscovery en el centro de cumplimiento en Office 365 o en Microsoft 365.
ms.openlocfilehash: db5a462087dd20ed71f87efe2fd83b821654f1b9
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32258778"
---
# <a name="create-a-report-on-holds-in-ediscovery-cases-in-office-365"></a><span data-ttu-id="a5457-103">Crear un informe sobre suspensiones en casos de eDiscovery en Office 365</span><span class="sxs-lookup"><span data-stu-id="a5457-103">Create a report on holds in eDiscovery cases in Office 365</span></span>
  
<span data-ttu-id="a5457-104">La secuencia de comandos de este artículo permite que los administradores de eDiscovery y los administradores de eDiscovery generen un informe que contiene información acerca de todas las suspensiones asociadas con casos de eDiscovery en el centro de cumplimiento de Office 365 o Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a5457-104">The script in this article lets eDiscovery administrators and eDiscovery managers generate a report that contains information about all holds that are associated with eDiscovery cases in the the compliance center in Office 365 or Microsoft 365.</span></span> <span data-ttu-id="a5457-105">El informe contiene información como, por ejemplo, el nombre del caso de que está asociada una suspensión, las ubicaciones de contenido que se encuentran en espera y si la retención se basa en la consulta.</span><span class="sxs-lookup"><span data-stu-id="a5457-105">The report contains information such as the name of the case a hold is associated with, the content locations that are placed on hold, and whether the hold is query-based.</span></span> <span data-ttu-id="a5457-106">Si hay casos que no tienen ninguna suspensión, el script creará un informe adicional con una lista de casos sin suspensiones.</span><span class="sxs-lookup"><span data-stu-id="a5457-106">If there are cases that don't have any holds, the script will create an additional report with a list of cases without holds.</span></span>

<span data-ttu-id="a5457-107">Consulte la sección [More Information](#more-information) para obtener una descripción detallada de la información incluida en el informe.</span><span class="sxs-lookup"><span data-stu-id="a5457-107">See the [More information](#more-information) section for a detailed description of the information included in the report.</span></span> 
  
## <a name="before-you-begin"></a><span data-ttu-id="a5457-108">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="a5457-108">Before you begin</span></span>

- <span data-ttu-id="a5457-109">Para generar un informe en todos los casos de eDiscovery de su organización, debe ser administrador de exhibición de documentos electrónicos en su organización.</span><span class="sxs-lookup"><span data-stu-id="a5457-109">To generate a report on all eDiscovery cases in your organization, you have to be an eDiscovery Administrator in your organization.</span></span> <span data-ttu-id="a5457-110">Si es un administrador de exhibición de documentos electrónicos, el informe solo incluirá información sobre los casos a los que puede tener acceso.</span><span class="sxs-lookup"><span data-stu-id="a5457-110">If you are an eDiscovery Manager, the report will only include information about the cases that you can access.</span></span> <span data-ttu-id="a5457-111">Para obtener más información sobre los permisos de exhibición de documentos electrónicos, consulte [asignar permisos de exhibición](assign-ediscovery-permissions.md)de documentos electrónicos.</span><span class="sxs-lookup"><span data-stu-id="a5457-111">For more information about eDiscovery permissions, see [Assign eDiscovery permissions](assign-ediscovery-permissions.md).</span></span>
    
- <span data-ttu-id="a5457-112">La secuencia de comandos de este artículo tiene un tratamiento de errores mínimo.</span><span class="sxs-lookup"><span data-stu-id="a5457-112">The script in this article has minimal error handling.</span></span> <span data-ttu-id="a5457-113">El objetivo principal es crear rápidamente informes sobre las suspensiones asociadas a los casos de eDiscovery de su organización.</span><span class="sxs-lookup"><span data-stu-id="a5457-113">The primary purpose is to quickly create report about the holds that are associated with the eDiscovery cases in your organization.</span></span>
    
- <span data-ttu-id="a5457-p104">Los scripts de ejemplo que se proporcionan en este tema no son compatibles con ningún servicio o programa de soporte técnico estándar de Microsoft. Los scripts de ejemplo se proporcionan tal cual, sin garantía de ningún tipo. Además, Microsoft se exime de todas las garantías implícitas, incluidas (sin limitación) las garantías implícitas de comerciabilidad o idoneidad para un propósito específico. El usuario asume todos los riesgos derivados del uso o del rendimiento de los scripts de ejemplo y la documentación. Microsoft, sus autores o cualquier persona relacionada con la creación, producción o entrega de los scripts no serán en ningún caso responsables de cualesquiera daños (incluidos, sin limitación, los daños producidos por la pérdida de beneficios comerciales, interrupción de la actividad comercial, pérdida de información empresarial u otras pérdidas económicas) derivados del uso o de la imposibilidad de uso de los scripts de ejemplo o la documentación, incluso aunque Microsoft tenga constancia de la posibilidad de que dichos daños se produzcan.</span><span class="sxs-lookup"><span data-stu-id="a5457-p104">The sample scripts provided in this topic aren't supported under any Microsoft standard support program or service. The sample scripts are provided AS IS without warranty of any kind. Microsoft further disclaims all implied warranties including, without limitation, any implied warranties of merchantability or of fitness for a particular purpose. The entire risk arising out of the use or performance of the sample scripts and documentation remains with you. In no event shall Microsoft, its authors, or anyone else involved in the creation, production, or delivery of the scripts be liable for any damages whatsoever (including, without limitation, damages for loss of business profits, business interruption, loss of business information, or other pecuniary loss) arising out of the use of or inability to use the sample scripts or documentation, even if Microsoft has been advised of the possibility of such damages.</span></span>
    
## <a name="step-1-connect-to-the-security--compliance-center-powershell"></a><span data-ttu-id="a5457-119">Paso 1: conectarse al centro de seguridad & de cumplimiento de PowerShell</span><span class="sxs-lookup"><span data-stu-id="a5457-119">Step 1: Connect to the Security & Compliance Center PowerShell</span></span>

<span data-ttu-id="a5457-120">El primer paso es conectarse al centro de cumplimiento de & de seguridad de su organización.</span><span class="sxs-lookup"><span data-stu-id="a5457-120">The first step is to connect to the Security & Compliance Center for your organization.</span></span>
  
1. <span data-ttu-id="a5457-121">Guarde el siguiente texto en un archivo de script de Windows PowerShell mediante un sufijo de nombre de archivo de. ps1; por ejemplo, `ConnectSCC.ps1`.</span><span class="sxs-lookup"><span data-stu-id="a5457-121">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `ConnectSCC.ps1`.</span></span> 
    
      ```
      # Get login credentials 
      $UserCredential = Get-Credential 
      $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Credential $UserCredential -Authentication Basic -AllowRedirection 
      Import-PSSession $Session -AllowClobber -DisableNameChecking 
      $Host.UI.RawUI.WindowTitle = $UserCredential.UserName + " (Security & Compliance Center)" 
    ```

2. <span data-ttu-id="a5457-122">En el equipo local, abra Windows PowerShell y vaya a la carpeta donde guardó el script.</span><span class="sxs-lookup"><span data-stu-id="a5457-122">On your local computer, open Windows PowerShell and go to the folder where you saved the script.</span></span> 
    
3. <span data-ttu-id="a5457-123">Ejecutar el script; por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="a5457-123">Run the script; for example:</span></span>

    ```
    .\ConnectSCC.ps1
    ```
   
4. <span data-ttu-id="a5457-124">Cuando se le pidan sus credenciales, escriba su dirección de correo electrónico y contraseña y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a5457-124">When prompted for your credentials, enter your email address and password, and then click **OK**.</span></span> 
  
## <a name="step-2-run-the-script-to-report-on-holds-associated-with-ediscovery-cases"></a><span data-ttu-id="a5457-125">Paso 2: ejecutar el script para informar sobre suspensiones asociadas con casos de eDiscovery</span><span class="sxs-lookup"><span data-stu-id="a5457-125">Step 2: Run the script to report on holds associated with eDiscovery cases</span></span>

<span data-ttu-id="a5457-126">Una vez que se haya conectado al centro de seguridad & Compliance Center PowerShell, el siguiente paso consiste en crear y ejecutar el script que recopila la información sobre los casos de eDiscovery de la organización.</span><span class="sxs-lookup"><span data-stu-id="a5457-126">After you've connected to Security & Compliance Center PowerShell, the next step is to create and run the script that collects information about the eDiscovery cases in your organization.</span></span> 
  
1. <span data-ttu-id="a5457-127">Guarde el siguiente texto en un archivo de script de Windows PowerShell mediante un sufijo de nombre de archivo de. ps1; por ejemplo, CaseHoldsReport. ps1.</span><span class="sxs-lookup"><span data-stu-id="a5457-127">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, CaseHoldsReport.ps1.</span></span> 
    
  ```
#script begin
" " 
write-host "***********************************************"
write-host "   Security & Compliance Center   " -foregroundColor yellow -backgroundcolor darkgreen
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

2. <span data-ttu-id="a5457-128">En la sesión de Windows PowerShell que se abrió en el paso 1, vaya a la carpeta en la que guardó el script.</span><span class="sxs-lookup"><span data-stu-id="a5457-128">In the Windows PowerShell session that opened in Step 1, go to the folder where you saved the script.</span></span> 
    
3. <span data-ttu-id="a5457-129">Ejecutar el script; por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="a5457-129">Run the script; for example:</span></span>

    ```
    .\CaseHoldsReport.ps1
    ```

    <span data-ttu-id="a5457-130">La secuencia de comandos pedirá una carpeta de destino en la que guardar el informe.</span><span class="sxs-lookup"><span data-stu-id="a5457-130">The script will prompt for a target folder to save the report to.</span></span> 
    
4. <span data-ttu-id="a5457-131">Escriba el nombre de la ruta de acceso completa de la carpeta en la que desea guardar el informe y, a continuación, presione **entrar**.</span><span class="sxs-lookup"><span data-stu-id="a5457-131">Type the full path name of the folder to save the report to, and then press **Enter**.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="a5457-132">Para guardar el informe en la misma carpeta en la que se encuentra el script, escriba un punto (".") cuando se le solicite una carpeta de destino.</span><span class="sxs-lookup"><span data-stu-id="a5457-132">To save the report in the same folder that the script is located in, type a period (".") when prompted for a target folder.</span></span> <span data-ttu-id="a5457-133">Para guardar el informe en una subcarpeta de la carpeta en la que se encuentra el script, escriba el nombre de la subcarpeta.</span><span class="sxs-lookup"><span data-stu-id="a5457-133">To save the report in a subfolder in the folder where the script is located, just type the name of the subfolder.</span></span> 
  
    <span data-ttu-id="a5457-134">El script empieza a recopilar información sobre todos los casos de eDiscovery de la organización.</span><span class="sxs-lookup"><span data-stu-id="a5457-134">The script starts to collect information about all the eDiscovery cases in your organization.</span></span> <span data-ttu-id="a5457-135">No obtenga acceso al archivo de informe mientras se ejecuta el script.</span><span class="sxs-lookup"><span data-stu-id="a5457-135">Don't access the report file while the script is running.</span></span> <span data-ttu-id="a5457-136">Una vez completado el script, se muestra un mensaje de confirmación en la sesión de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a5457-136">After the script is complete, a confirmation message is displayed in the Windows PowerShell session.</span></span> <span data-ttu-id="a5457-137">Después de que se muestre este mensaje, puede tener acceso al informe en la carpeta que especificó en el paso 4.</span><span class="sxs-lookup"><span data-stu-id="a5457-137">After this message is displayed, you can access the report in the folder that you specified in Step 4.</span></span> <span data-ttu-id="a5457-138">El nombre de archivo del informe es `CaseHoldsReport<DateTimeStamp>.csv`.</span><span class="sxs-lookup"><span data-stu-id="a5457-138">The file name for the report is `CaseHoldsReport<DateTimeStamp>.csv`.</span></span>

    <span data-ttu-id="a5457-139">Además, el script también crea un informe con una lista de casos que no tienen ninguna suspensión.</span><span class="sxs-lookup"><span data-stu-id="a5457-139">Addtionally, the script also creates a report with a list of cases that don't have any holds.</span></span> <span data-ttu-id="a5457-140">El nombre de archivo de este informe `CaseswithNoHolds<DateTimeStamp>.csv`es.</span><span class="sxs-lookup"><span data-stu-id="a5457-140">The file name for this report is `CaseswithNoHolds<DateTimeStamp>.csv`.</span></span>
    
    <span data-ttu-id="a5457-141">Este es un ejemplo de cómo se ejecuta el script CaseHoldsReport. ps1.</span><span class="sxs-lookup"><span data-stu-id="a5457-141">Here's an example of running the CaseHoldsReport.ps1 script.</span></span> 
    
    ![El resultado después de ejecutar el script CaseHoldsReport. ps1](media/7d312ed5-505e-4ec5-8f06-3571e3524a1a.png)
  
## <a name="more-information"></a><span data-ttu-id="a5457-143">Más información</span><span class="sxs-lookup"><span data-stu-id="a5457-143">More information</span></span>

<span data-ttu-id="a5457-144">El informe de suspensiones de casos que se crea al ejecutar el script de este artículo contiene la siguiente información sobre cada suspensión.</span><span class="sxs-lookup"><span data-stu-id="a5457-144">The case holds report that's created when you run the script in this article contains the following information about each hold.</span></span> <span data-ttu-id="a5457-145">Como se ha explicado anteriormente, debe ser administrador de eDiscovery para devolver información de todas las suspensiones de la organización.</span><span class="sxs-lookup"><span data-stu-id="a5457-145">As previously explained, you have to be an eDiscovery Administrator to return information for all holds in your organization.</span></span> <span data-ttu-id="a5457-146">Para obtener más información acerca de las suspensiones de casos, consulte [casos de eDiscovery](ediscovery-cases.md).</span><span class="sxs-lookup"><span data-stu-id="a5457-146">For more information about case holds, see [eDiscovery cases](ediscovery-cases.md).</span></span>
  
  - <span data-ttu-id="a5457-147">El nombre de la retención y el nombre del caso de exhibición de documentos electrónicos con el que está asociada la retención.</span><span class="sxs-lookup"><span data-stu-id="a5457-147">The name of the hold and the name of the eDiscovery case that the hold is associated with.</span></span>
    
  - <span data-ttu-id="a5457-148">Si el caso de exhibición de documentos electrónicos está activo o cerrado.</span><span class="sxs-lookup"><span data-stu-id="a5457-148">Whether or not the eDiscovery case is active or closed.</span></span>
    
  - <span data-ttu-id="a5457-149">Indica si la retención está habilitada o deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="a5457-149">Whether or not the hold is enabled or disabled.</span></span>
    
  - <span data-ttu-id="a5457-150">Los miembros del caso de eDiscovery con los que está asociada la retención.</span><span class="sxs-lookup"><span data-stu-id="a5457-150">The members of the eDiscovery case that the hold is associated with.</span></span> <span data-ttu-id="a5457-151">Los miembros de caso pueden ver o administrar un caso, según los permisos de exhibición de documentos electrónicos que se les haya asignado.</span><span class="sxs-lookup"><span data-stu-id="a5457-151">Case members can view or manage a case, depending on the eDiscovery permissions they've been assigned.</span></span>
    
  - <span data-ttu-id="a5457-152">La hora y la fecha en que se creó el caso.</span><span class="sxs-lookup"><span data-stu-id="a5457-152">The time and date the case was created.</span></span>
    
  - <span data-ttu-id="a5457-153">Si se cierra un caso, la persona que lo cerró y la fecha y hora en que se cerró.</span><span class="sxs-lookup"><span data-stu-id="a5457-153">If a case is closed, the person who closed it and the time and date it was closed.</span></span>
    
  - <span data-ttu-id="a5457-154">Las ubicaciones de los buzones de Exchange y de los sitios de SharePoint que están en suspensión.</span><span class="sxs-lookup"><span data-stu-id="a5457-154">The Exchange mailboxes and SharePoint sites locations that are on hold.</span></span>
    
  - <span data-ttu-id="a5457-155">Si la retención está basada en consultas, la sintaxis de la consulta.</span><span class="sxs-lookup"><span data-stu-id="a5457-155">If the hold is query-based, the query syntax.</span></span>
    
  - <span data-ttu-id="a5457-156">La fecha y la hora en que se creó la retención y la persona que la creó.</span><span class="sxs-lookup"><span data-stu-id="a5457-156">The time and date the hold was created and the person who created it.</span></span>
    
  - <span data-ttu-id="a5457-157">La fecha y la hora en que se modificó por última vez la retención y la persona que la modificó.</span><span class="sxs-lookup"><span data-stu-id="a5457-157">The time and date the hold was last changed and the person who changed it.</span></span>
