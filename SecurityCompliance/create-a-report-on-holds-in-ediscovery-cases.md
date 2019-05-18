---
title: Crear un informe sobre suspensiones en casos de eDiscovery en Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 9/11/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid: MOE150
ms.assetid: cca08d26-6fbf-4b2c-b102-b226e4cd7381
description: Use el script de este artículo para generar un informe que contenga información sobre todas las suspensiones asociadas con casos de eDiscovery en el centro de cumplimiento en Office 365 o en Microsoft 365.
ms.openlocfilehash: 7118b62dcd42413309e33c45e80516c8822faeff
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/17/2019
ms.locfileid: "34151292"
---
# <a name="create-a-report-on-holds-in-ediscovery-cases-in-office-365"></a>Crear un informe sobre suspensiones en casos de eDiscovery en Office 365
  
La secuencia de comandos de este artículo permite que los administradores de eDiscovery y los administradores de eDiscovery generen un informe que contiene información acerca de todas las suspensiones asociadas con casos de eDiscovery en el centro de cumplimiento de Office 365 o Microsoft 365. El informe contiene información como, por ejemplo, el nombre del caso de que está asociada una suspensión, las ubicaciones de contenido que se encuentran en espera y si la retención se basa en la consulta. Si hay casos que no tienen ninguna suspensión, el script creará un informe adicional con una lista de casos sin suspensiones.

Consulte la sección [More Information](#more-information) para obtener una descripción detallada de la información incluida en el informe. 
  
## <a name="before-you-begin"></a>Antes de empezar

- Para generar un informe en todos los casos de eDiscovery de su organización, debe ser administrador de exhibición de documentos electrónicos en su organización. Si es un administrador de exhibición de documentos electrónicos, el informe solo incluirá información sobre los casos a los que puede tener acceso. Para obtener más información sobre los permisos de exhibición de documentos electrónicos, consulte [asignar permisos de exhibición](assign-ediscovery-permissions.md)de documentos electrónicos.
    
- La secuencia de comandos de este artículo tiene un tratamiento de errores mínimo. El objetivo principal es crear rápidamente informes sobre las suspensiones asociadas a los casos de eDiscovery de su organización.
    
- Los scripts de ejemplo que se proporcionan en este tema no son compatibles con ningún servicio o programa de soporte técnico estándar de Microsoft. Los scripts de ejemplo se proporcionan tal cual, sin garantía de ningún tipo. Además, Microsoft se exime de todas las garantías implícitas, incluidas (sin limitación) las garantías implícitas de comerciabilidad o idoneidad para un propósito específico. El usuario asume todos los riesgos derivados del uso o del rendimiento de los scripts de ejemplo y la documentación. Microsoft, sus autores o cualquier persona relacionada con la creación, producción o entrega de los scripts no serán en ningún caso responsables de cualesquiera daños (incluidos, sin limitación, los daños producidos por la pérdida de beneficios comerciales, interrupción de la actividad comercial, pérdida de información empresarial u otras pérdidas económicas) derivados del uso o de la imposibilidad de uso de los scripts de ejemplo o la documentación, incluso aunque Microsoft tenga constancia de la posibilidad de que dichos daños se produzcan.
    
## <a name="step-1-connect-to-the-security--compliance-center-powershell"></a>Paso 1: conectarse al centro de seguridad & de cumplimiento de PowerShell

El primer paso es conectarse al centro de cumplimiento de & de seguridad de su organización.
  
1. Guarde el siguiente texto en un archivo de script de Windows PowerShell mediante un sufijo de nombre de archivo de. ps1; por ejemplo, `ConnectSCC.ps1`. 
    
      ```
      # Get login credentials 
      $UserCredential = Get-Credential 
      $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Credential $UserCredential -Authentication Basic -AllowRedirection 
      Import-PSSession $Session -AllowClobber -DisableNameChecking 
      $Host.UI.RawUI.WindowTitle = $UserCredential.UserName + " (Security & Compliance Center)" 
    ```

2. En el equipo local, abra Windows PowerShell y vaya a la carpeta donde guardó el script. 
    
3. Ejecutar el script; por ejemplo:

    ```
    .\ConnectSCC.ps1
    ```
   
4. Cuando se le pidan sus credenciales, escriba su dirección de correo electrónico y contraseña y, a continuación, haga clic en **Aceptar**. 
  
## <a name="step-2-run-the-script-to-report-on-holds-associated-with-ediscovery-cases"></a>Paso 2: ejecutar el script para informar sobre suspensiones asociadas con casos de eDiscovery

Una vez que se haya conectado al centro de seguridad & Compliance Center PowerShell, el siguiente paso consiste en crear y ejecutar el script que recopila la información sobre los casos de eDiscovery de la organización. 
  
1. Guarde el siguiente texto en un archivo de script de Windows PowerShell mediante un sufijo de nombre de archivo de. ps1; por ejemplo, CaseHoldsReport. ps1. 
    
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

2. En la sesión de Windows PowerShell que se abrió en el paso 1, vaya a la carpeta en la que guardó el script. 
    
3. Ejecutar el script; por ejemplo:

    ```
    .\CaseHoldsReport.ps1
    ```

    La secuencia de comandos pedirá una carpeta de destino en la que guardar el informe. 
    
4. Escriba el nombre de la ruta de acceso completa de la carpeta en la que desea guardar el informe y, a continuación, presione **entrar**.
    
    > [!TIP]
    > Para guardar el informe en la misma carpeta en la que se encuentra el script, escriba un punto (".") cuando se le solicite una carpeta de destino. Para guardar el informe en una subcarpeta de la carpeta en la que se encuentra el script, escriba el nombre de la subcarpeta. 
  
    El script empieza a recopilar información sobre todos los casos de eDiscovery de la organización. No obtenga acceso al archivo de informe mientras se ejecuta el script. Una vez completado el script, se muestra un mensaje de confirmación en la sesión de Windows PowerShell. Después de que se muestre este mensaje, puede tener acceso al informe en la carpeta que especificó en el paso 4. El nombre de archivo del informe es `CaseHoldsReport<DateTimeStamp>.csv`.

    Además, el script también crea un informe con una lista de casos que no tienen ninguna suspensión. El nombre de archivo de este informe `CaseswithNoHolds<DateTimeStamp>.csv`es.
    
    Este es un ejemplo de cómo se ejecuta el script CaseHoldsReport. ps1. 
    
    ![El resultado después de ejecutar el script CaseHoldsReport. ps1](media/7d312ed5-505e-4ec5-8f06-3571e3524a1a.png)
  
## <a name="more-information"></a>Más información

El informe de suspensiones de casos que se crea al ejecutar el script de este artículo contiene la siguiente información sobre cada suspensión. Como se ha explicado anteriormente, debe ser administrador de eDiscovery para devolver información de todas las suspensiones de la organización. Para obtener más información acerca de las suspensiones de casos, consulte [casos de eDiscovery](ediscovery-cases.md).
  
  - El nombre de la retención y el nombre del caso de exhibición de documentos electrónicos con el que está asociada la retención.
    
  - Si el caso de exhibición de documentos electrónicos está activo o cerrado.
    
  - Indica si la retención está habilitada o deshabilitada.
    
  - Los miembros del caso de eDiscovery con los que está asociada la retención. Los miembros de caso pueden ver o administrar un caso, según los permisos de exhibición de documentos electrónicos que se les haya asignado.
    
  - La hora y la fecha en que se creó el caso.
    
  - Si se cierra un caso, la persona que lo cerró y la fecha y hora en que se cerró.
    
  - Las ubicaciones de los buzones de Exchange y de los sitios de SharePoint que están en suspensión.
    
  - Si la retención está basada en consultas, la sintaxis de la consulta.
    
  - La fecha y la hora en que se creó la retención y la persona que la creó.
    
  - La fecha y la hora en que se modificó por última vez la retención y la persona que la modificó.
