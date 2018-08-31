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
search.appverid:
- MOE150
- MET150
ms.assetid: cca08d26-6fbf-4b2c-b102-b226e4cd7381
description: Use la secuencia de comandos de este artículo para generar un informe que contiene información acerca de todas las suspensiones a las que están asociadas con los casos de exhibición de documentos electrónicos en la seguridad de Office 365 &amp; centro de cumplimiento.
ms.openlocfilehash: 8bc1285f776e2b1aa0c0330c06ccffff8ce4585c
ms.sourcegitcommit: c166964fe14eec69139a2d3d9c10d2c40ab33f91
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/28/2018
ms.locfileid: "23258648"
---
# <a name="create-a-report-on-holds-in-ediscovery-cases-in-office-365"></a>Crear un informe en las suspensiones en los casos de exhibición de documentos electrónicos en Office 365
  
La secuencia de comandos en este artículo permite a los administradores de la exhibición de documentos electrónicos y los administradores de exhibición de documentos electrónicos generan un informe que contiene información acerca de todas las suspensiones que se asocian con los casos de exhibición de documentos electrónicos en la seguridad de Office 365 &amp; centro de cumplimiento. El informe contiene información como el nombre del caso de una suspensión está asociado con las ubicaciones de contenido que se colocan en espera, y si la suspensión está basado en la consulta. Si hay casos en los que no tengan ninguna suspensión, la secuencia de comandos creará un informe adicional con una lista de los casos sin suspensiones.

Vea la sección [obtener más información](#more-information) para obtener una descripción detallada de la información incluida en el informe. 
  
## <a name="before-you-begin"></a>Antes de empezar

- Para generar un informe en todos los casos de exhibición de documentos electrónicos en su organización, debe ser un administrador de exhibición de documentos en su organización. Si es un administrador de exhibición de documentos electrónicos, el informe sólo incluirá información acerca de los casos que puede tener acceso. Para obtener más información acerca de los permisos de exhibición de documentos electrónicos, vea [asignar permisos de exhibición de documentos electrónicos en la seguridad de Office 365 &amp; centro de cumplimiento](assign-ediscovery-permissions.md).
    
- La secuencia de comandos en este artículo tiene el tratamiento de errores mínima. El propósito principal es crear rápidamente informe sobre las suspensiones que se asocian con los casos de exhibición de documentos electrónicos en su organización.
    
- Las secuencias de comandos de ejemplo proporcionados en este tema no son compatibles con cualquier servicio o programa de soporte estándar de Microsoft. Las secuencias de comandos de ejemplo se proporcionan tal cual sin garantía de ningún tipo. Microsoft renuncia a todas las garantías implícitas incluidas, sin limitación, cualquier las garantías implícitas de comerciabilidad o de idoneidad para un fin determinado. Todo el riesgo que pueda surgir por el uso o el rendimiento de las secuencias de comandos de ejemplo y documentación permanece con usted. En ningún caso Microsoft, sus autores o cualquier otro implicado en la creación, producción o entrega de las secuencias de comandos serán responsables de los daños índole (incluidos, pero sin limitarse a, daños por pérdida de beneficios empresariales, interrupción del negocio, pérdida de información de la empresa, o en otras pérdidas de carácter económico) derivado del uso o la incapacidad de usar los scripts de ejemplo o documentación, aunque Microsoft haya sido notificado de la posibilidad de dichos daños.
    
## <a name="step-1-connect-to-the-security-amp-compliance-center-using-remote-powershell"></a>Paso 1: Conectar a la seguridad &amp; centro de cumplimiento de normas mediante PowerShell remoto

El primer paso es conectar Windows PowerShell a la seguridad &amp; centro de cumplimiento de normas de la organización.
  
1. Guarde el siguiente texto en un archivo de secuencia de comandos de Windows PowerShell mediante el uso de un sufijo de nombre de archivo de. ps1; Por ejemplo, `ConnectSCC.ps1`. 
    
      ```
      # Get login credentials 
      $UserCredential = Get-Credential 
      $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Credential $UserCredential -Authentication Basic -AllowRedirection 
      Import-PSSession $Session -AllowClobber -DisableNameChecking 
      $Host.UI.RawUI.WindowTitle = $UserCredential.UserName + " (Office 365 Security &amp; Compliance Center)" 
    ```

2. En el equipo local, abra Windows PowerShell y vaya a la carpeta donde guardó la secuencia de comandos. 
    
3. Ejecute la secuencia de comandos; Por ejemplo:

    ```
    .\ConnectSCC.ps1
    ```
   
4. Cuando se le pidan sus credenciales, escriba su dirección de correo electrónico y contraseña y, a continuación, haga clic en **Aceptar**. 
  
## <a name="step-2-run-the-script-to-report-on-holds-associated-with-ediscovery-cases"></a>Paso 2: Ejecutar el script para informar sobre las suspensiones asociado con los casos de exhibición de documentos electrónicos

Una vez conectado a la seguridad &amp; centro de cumplimiento con PowerShell remoto, el siguiente paso es crear y ejecutar la secuencia de comandos que recopila información acerca de los casos de exhibición de documentos electrónicos en su organización. 
  
1. Guarde el siguiente texto en un archivo de secuencia de comandos de Windows PowerShell mediante el uso de un sufijo de nombre de archivo de. ps1; Por ejemplo, CaseHoldsReport.ps1. 
    
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

2. En la sesión de Windows PowerShell que abrió en el paso 1, vaya a la carpeta donde guardó la secuencia de comandos. 
    
3. Ejecute la secuencia de comandos; Por ejemplo:

    ```
    .\CaseHoldsReport.ps1
    ```

    La secuencia de comandos realizará mostrará el mensaje guardar el informe para que una carpeta de destino. 
    
4. Escriba el nombre de ruta de acceso completa de la carpeta que se va a guardar el informe y, a continuación, presione **ENTRAR**.
    
    > [!TIP]
    > Para guardar el informe en la misma carpeta que la secuencia de comandos se encuentra en, escriba un punto (".") cuando se le solicite una carpeta de destino. Para guardar el informe en una subcarpeta en la carpeta donde se encuentra la secuencia de comandos, simplemente escriba el nombre de la subcarpeta. 
  
    La secuencia de comandos empieza a recopilar información acerca de todos los casos de exhibición de documentos electrónicos en su organización. No tener acceso al archivo de informe mientras se está ejecutando la secuencia de comandos. Una vez finalizada la secuencia de comandos, se muestra un mensaje de confirmación en la sesión de Windows PowerShell. Después de que aparezca este mensaje, se puede obtener acceso al informe en la carpeta que especificó en el paso 4. Es el nombre de archivo para el informe de `CaseHoldsReport<DateTimeStamp>.csv`.

    Addtionally, la secuencia de comandos también crea un informe con una lista de los casos que no tengan ninguna suspensión. El nombre de archivo para este informe es `CaseswithNoHolds<DateTimeStamp>.csv`.
    
    Este es un ejemplo de ejecución del script CaseHoldsReport.ps1. 
    
    ![El resultado después de ejecutar la secuencia de comandos CaseHoldsReport.ps1](media/7d312ed5-505e-4ec5-8f06-3571e3524a1a.png)
  
## <a name="more-information"></a>Más información

El caso contiene el informe que se crea al ejecutar el script en este artículo contiene la siguiente información sobre cada suspensión. Como se explica anteriormente, debe ser un administrador para devolver información para todas las suspensiones en la organización de exhibición de documentos electrónicos. Para obtener más información acerca de caso de suspensiones, consulte [casos de exhibición de documentos electrónicos en la seguridad de Office 365 &amp; centro de cumplimiento](ediscovery-cases.md).
  
  - El nombre de la suspensión y el nombre del caso de exhibición de documentos electrónicos que está asociada la suspensión.
    
  - Si está o no el caso de exhibición de documentos electrónicos activo o cerrado.
    
  - Si la suspensión está habilitada o deshabilitada.
    
  - Los miembros de los casos de exhibición de documentos electrónicos que está asociada la suspensión. Case (miembros) puede ver o administrar un caso, dependiendo de los permisos de exhibición de documentos electrónicos que se han asignado.
    
  - La hora y fecha de que creación de las mayúsculas y minúsculas.
    
  - Si se cierra un caso, la persona que se cierra y la hora y fecha se ha cerrado.
    
  - Ubicaciones que están en espera de sitios de los buzones de Exchange y SharePoint.
    
  - Si la suspensión está basada en consultas, la sintaxis de consulta.
    
  - La hora y fecha de que creación de la suspensión y la persona que lo creó.
    
  - La hora y fecha de que la suspensión se modificó por última vez y la persona que haya cambiado.
