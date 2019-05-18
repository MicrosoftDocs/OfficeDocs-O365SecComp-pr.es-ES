---
title: Crear y publicar etiquetas de retención de forma masiva con PowerShell
ms.author: stephow
author: stephow-msft
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: Priority
search.appverid:
- MOE150
- MET150
description: En Office 365, puede usar etiquetas para implementar una programación de retención en su organización. Como administrador de registros o responsable de cumplimiento normativo, puede que tenga que crear y publicar cientos de etiquetas. Puede hacerlo mediante la interfaz de usuario del Centro de seguridad y cumplimiento, pero crear etiquetas de una en una es laborioso e ineficiente. Si usa el script y los archivos .csv que se proporcionan a continuación, puede crear y publicar de forma masiva etiquetas y directivas de etiquetas. Primero, creará una lista de las etiquetas y una lista de las directivas de etiquetas en Excel y, después, creará de forma masiva las etiquetas y las directivas de etiquetas en esas listas con PowerShell. Esto permite crear y publicar al mismo tiempo y con mayor facilidad todas las etiquetas que necesita la programación de retención.
ms.openlocfilehash: 09d1a1d2fa6faa333f9b53a7928abdc7409073b6
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/17/2019
ms.locfileid: "34152112"
---
# <a name="bulk-create-and-publish-retention-labels-by-using-powershell"></a><span data-ttu-id="743f6-108">Crear y publicar etiquetas de retención de forma masiva con PowerShell</span><span class="sxs-lookup"><span data-stu-id="743f6-108">Bulk create and publish retention labels by using PowerShell</span></span>

<span data-ttu-id="743f6-p102">En Office 365, puede usar etiquetas para implementar una programación de retención en su organización. Como administrador de registros o responsable de cumplimiento normativo, puede que tenga que crear y publicar cientos de etiquetas. Puede hacerlo mediante la interfaz de usuario del Centro de seguridad y cumplimiento, pero crear etiquetas de una en una es laborioso e ineficiente.</span><span class="sxs-lookup"><span data-stu-id="743f6-p102">In Office 365, you can use labels to implement a retention schedule for your organization. As a record manager or compliance officer, you might have hundreds of labels to create and publish. You can do this through the UI in the Security &amp; Compliance Center, but creating labels one at a time is time-consuming and inefficient.</span></span>
  
<span data-ttu-id="743f6-p103">Si usa el script y los archivos .csv que se proporcionan a continuación, puede crear y publicar de forma masiva etiquetas y directivas de etiquetas. Primero, creará una lista de las etiquetas y una lista de las directivas de etiquetas en Excel y, después, creará de forma masiva las etiquetas y las directivas de etiquetas en esas listas con PowerShell. Esto permite crear y publicar al mismo tiempo y con mayor facilidad todas las etiquetas que necesita la programación de retención.</span><span class="sxs-lookup"><span data-stu-id="743f6-p103">By using the script and .csv files provided below, you can bulk create and publish labels and label policies. First you create a list of the labels and a list of the label policies in Excel, and then you bulk create the labels and label policies in those lists by using PowerShell. This makes it easier to create and publish at one time all of the labels that your retention schedule requires.</span></span>
  
<span data-ttu-id="743f6-115">Para obtener más información sobre las etiquetas, vea [Información general sobre etiquetas](labels.md).</span><span class="sxs-lookup"><span data-stu-id="743f6-115">For more information about labels, see [Overview of labels](labels.md).</span></span>
  
## <a name="disclaimer"></a><span data-ttu-id="743f6-116">Aviso de declinación de responsabilidades</span><span class="sxs-lookup"><span data-stu-id="743f6-116">Disclaimer</span></span>

<span data-ttu-id="743f6-p104">Los scripts de ejemplo que se proporcionan en este tema no son compatibles con ningún servicio o programa de soporte técnico estándar de Microsoft. Los scripts de ejemplo se proporcionan tal cual, sin garantía de ningún tipo. Además, Microsoft se exime de todas las garantías implícitas, incluidas (sin limitación) las garantías implícitas de comerciabilidad o idoneidad para un propósito específico. El usuario asume todos los riesgos derivados del uso o del rendimiento de los scripts de ejemplo y la documentación. Microsoft, sus autores o cualquier persona relacionada con la creación, producción o entrega de los scripts no serán en ningún caso responsables de cualesquiera daños (incluidos, sin limitación, los daños producidos por la pérdida de beneficios comerciales, interrupción de la actividad comercial, pérdida de información empresarial u otras pérdidas económicas) derivados del uso o de la imposibilidad de uso de los scripts de ejemplo o la documentación, incluso aunque Microsoft tenga constancia de la posibilidad de que dichos daños se produzcan.</span><span class="sxs-lookup"><span data-stu-id="743f6-p104">The sample scripts provided in this topic aren't supported under any Microsoft standard support program or service. The sample scripts are provided AS IS without warranty of any kind. Microsoft further disclaims all implied warranties including, without limitation, any implied warranties of merchantability or of fitness for a particular purpose. The entire risk arising out of the use or performance of the sample scripts and documentation remains with you. In no event shall Microsoft, its authors, or anyone else involved in the creation, production, or delivery of the scripts be liable for any damages whatsoever (including, without limitation, damages for loss of business profits, business interruption, loss of business information, or other pecuniary loss) arising out of the use of or inability to use the sample scripts or documentation, even if Microsoft has been advised of the possibility of such damages.</span></span>
  
## <a name="step-1-create-a-csv-file-for-creating-the-labels"></a><span data-ttu-id="743f6-122">Paso 1: Crear un archivo .csv para crear las etiquetas</span><span class="sxs-lookup"><span data-stu-id="743f6-122">Step 1: Create a .csv file for creating the labels</span></span>

<span data-ttu-id="743f6-p105">Primero, cree un archivo .csv que contenga una lista de las etiquetas con su configuración de retención. Puede usar el ejemplo siguiente como una plantilla; para hacerlo, cópielo en Excel, convierta el texto en columnas (en Excel \> pestaña **Datos** \> **Texto en columnas** \> **Delimitado** \> **Coma** \> **General**) y, después, guarde la hoja de cálculo como un archivo .csv en una ubicación de fácil acceso.</span><span class="sxs-lookup"><span data-stu-id="743f6-p105">First you create a .csv file that contains a list of your labels with their retention settings. You can use the sample below as a template by copying it into Excel, converting the text to columns (in Excel \> **Data** tab \> **Text to Columns** \> **Delimited** \> **Comma** \> **General**), and then saving the worksheet as a .csv file in a location that's easy to find.</span></span>
  
<span data-ttu-id="743f6-125">Para obtener más información sobre los valores de parámetro para este cmdlet, vea [New-ComplianceTag](https://go.microsoft.com/fwlink/?linkid=866511).</span><span class="sxs-lookup"><span data-stu-id="743f6-125">For more information about the parameter values for this cmdlet, see [New-ComplianceTag](https://go.microsoft.com/fwlink/?linkid=866511).</span></span>
  
<span data-ttu-id="743f6-126">Notas:</span><span class="sxs-lookup"><span data-stu-id="743f6-126">Notes:</span></span>
  
- <span data-ttu-id="743f6-127">Si no especifica un archivo de origen para crear etiquetas, el script continuará y le pedirá el archivo de origen para publicar etiquetas (vea la sección siguiente), pero solo publicará las etiquetas existentes.</span><span class="sxs-lookup"><span data-stu-id="743f6-127">If you don't provide a source file for creating labels, the script moves on and prompts you for the source file for publishing labels (see the next section), and the script will publish only existing labels.</span></span>
    
- <span data-ttu-id="743f6-p106">Si el archivo .csv contiene una etiqueta con el mismo nombre que una ya existente, el script omitirá la creación de esa etiqueta. No se crean etiquetas duplicadas.</span><span class="sxs-lookup"><span data-stu-id="743f6-p106">If the .csv file contains a label with the same name as one that already exists, the script skips creating that label. No duplicate labels are created.</span></span>
    
- <span data-ttu-id="743f6-p107">Si cambia el nombre o modifica los encabezados de columna, el script producirá errores. El script necesita un archivo .csv con el formato especificado aquí.</span><span class="sxs-lookup"><span data-stu-id="743f6-p107">If you change or rename the column headers, the script will fail. The script requires a .csv file in the format provided here.</span></span>
    
### <a name="sample-csv-file"></a><span data-ttu-id="743f6-132">Archivo .csv de ejemplo</span><span class="sxs-lookup"><span data-stu-id="743f6-132">Sample .csv file</span></span>

```
Name (Required),Comment (Optional),IsRecordLabel (Required),RetentionAction (Optional),RetentionDuration (Optional),RetentionType (Optional),ReviewerEmail (Optional)
LabelName_t_1,Record - keep and delete - 2 years,$true,KeepAndDelete,730,CreationAgeInDays,
LabelName_t_2,Keep and delete tag - 7 years,$false,KeepAndDelete,2555,ModificationAgeInDays,
LabelName_t_3,5 year delete,$false,Delete,1825,TaggedAgeInDays,
LabelName_t_4,Record label tag - financial,$true,Keep,730,CreationAgeInDays,
```

## <a name="step-2-create-a-csv-file-for-publishing-the-labels"></a><span data-ttu-id="743f6-133">Paso 2: Crear un archivo .csv para publicar las etiquetas</span><span class="sxs-lookup"><span data-stu-id="743f6-133">Step 2: Create a .csv file for publishing the labels</span></span>

<span data-ttu-id="743f6-p108">Después, cree un archivo .csv que contenga una lista de directivas de etiquetas con sus ubicaciones y otras opciones de configuración. Puede usar el ejemplo siguiente como una plantilla; para hacerlo, cópielo en Excel, convierta el texto en columnas (en Excel \> pestaña **Datos** \> **Texto en columnas** \> **Delimitado** \> **Coma** \> **General**) y, después, guarde la hoja de cálculo como un archivo .csv en una ubicación de fácil acceso.</span><span class="sxs-lookup"><span data-stu-id="743f6-p108">Next you create a .csv file that contains a list of label policies with their locations and other settings. You can use the sample below as a template by copying it into Excel, converting the text to columns (in Excel \> **Data** tab \> **Text to Columns** \> **Delimited** \> **Comma** \> **General**), and then saving the worksheet as a .csv file in a location that's easy to find.</span></span>
  
<span data-ttu-id="743f6-136">Para obtener más información sobre los valores de parámetro para este cmdlet, vea [New-RetentionCompliancePolicy](https://go.microsoft.com/fwlink/?linkid=866512).</span><span class="sxs-lookup"><span data-stu-id="743f6-136">For more information about the parameter values for this cmdlet, see [New-RetentionCompliancePolicy](https://go.microsoft.com/fwlink/?linkid=866512).</span></span>
  
<span data-ttu-id="743f6-137">Notas:</span><span class="sxs-lookup"><span data-stu-id="743f6-137">Notes:</span></span>
  
- <span data-ttu-id="743f6-138">Si no especifica un archivo de origen para publicar etiquetas, el script creará etiquetas (vea la sección anterior), pero no las publicará.</span><span class="sxs-lookup"><span data-stu-id="743f6-138">If you don't provide a source file for publishing labels, the script creates labels (see the previous section) but does not publish them.</span></span>
    
- <span data-ttu-id="743f6-p109">Si el archivo .csv contiene una directiva de etiquetas con el mismo nombre de una que ya exista, el script omitirá la creación de esa directiva de etiquetas. No se crean directivas de etiquetas duplicadas.</span><span class="sxs-lookup"><span data-stu-id="743f6-p109">If the .csv file contains a label policy with the same name as one that already exists, the script skips creating that label policy. No duplicate label policies are created.</span></span>
    
- <span data-ttu-id="743f6-p110">El script solo publica las etiquetas que se aplican de forma manual en el contenido. Este script no admite las etiquetas que se aplican automáticamente en el contenido.</span><span class="sxs-lookup"><span data-stu-id="743f6-p110">The script publishes only labels that are applied manually to content. This script does not support labels that are auto-applied to content.</span></span>
    
- <span data-ttu-id="743f6-p111">Si cambia el nombre o modifica los encabezados de columna, el script producirá errores. El script necesita un archivo .csv con el formato especificado aquí.</span><span class="sxs-lookup"><span data-stu-id="743f6-p111">If you change or rename the column headers, the script will fail. The script requires a .csv file in the format provided here.</span></span>
    
### <a name="sample-csv-file"></a><span data-ttu-id="743f6-145">Archivo .csv de ejemplo</span><span class="sxs-lookup"><span data-stu-id="743f6-145">Sample .csv file</span></span>

```
Policy Name (Required),PublishComplianceTag (Required),Comment (Optional),Enabled (Required),ExchangeLocation (Optional),ExchangeLocationException (Optional),ModernGroupLocation (Optional),ModernGroupLocationException (Optional),OneDriveLocation (Optional),OneDriveLocationException (Optional),PublicFolderLocation (Optional),SharePointLocation (Optional),SharePointLocationException (Optional),SkypeLocation (Optional),SkypeLocationException (Optional)
Publishing Policy Red1,"LabelName_t_1, LabelName_t_2, LabelName_t_3, LabelName_t_4",N/A,$true,All,,All,,All,,,All,,,
Publishing Policy Orange1,"LabelName_t_1, LabelName_t_2",N/A,$true,All,,,,,,,,,,
Publishing Policy Yellow1,"LabelName_t_3, LabelName_t_4",N/A,$false,All,,,,,,,,,,
```

## <a name="step-3-create-the-powershell-script"></a><span data-ttu-id="743f6-146">Paso 3: Crear el script de PowerShell</span><span class="sxs-lookup"><span data-stu-id="743f6-146">Step 3: Create the PowerShell script</span></span>

<span data-ttu-id="743f6-p112">Copie y pegue el script de PowerShell siguiente en el Bloc de notas. Guarde el archivo con el sufijo de nombre de archivo .ps1 en una ubicación que le resulte fácil de encontrar (por ejemplo, \<ruta\>CrearProgramaciónDeRetención.ps1).</span><span class="sxs-lookup"><span data-stu-id="743f6-p112">Copy and paste the below PowerShell script into Notepad. Save the file by using a filename suffix of .ps1 in a location that's easy to find -- for example, \<path\>CreateRetentionSchedule.ps1.</span></span>
  
### <a name="powershell-script"></a><span data-ttu-id="743f6-149">Script de PowerShell</span><span class="sxs-lookup"><span data-stu-id="743f6-149">PowerShell script</span></span>

```
<#
. Steps: Import and Publish Compliance Tag
    ○ Load compliance tag csv file 
    ○ Validate csv file input
    ○ Create compliance tag
    ○ Create compliance policy
    ○ Publish compliance tag for the policy
    ○ Generate the log for tags creation
    ○ Generate the csv result for the tags created and published
. Syntax
    .\Publish-ComplianceTag.ps1 [-LabelListCSV <string>] [-PolicyListCSV <string>] 
. Detailed Description
    1) [-LabelListCSV <string>]
    -LabelListCSV ".\SampleInputFile_LabelList.csv"
    Load compliance tag for creation.
    2) [-PolicyListCSV <string>]
    -PolicyListCSV ".\SampleInputFile_PolicyList.csv"
    Load compliance tag for creation.
#>
param (
    [Parameter(Mandatory = $true)]
    [string]$LabelListCSV = "",
    [Parameter(Mandatory = $true)]
    [string]$PolicyListCSV = "",
    [Switch]$ResultCSV
)
# -------------------
# File operation
# -------------------
Function FileExist
{
    Param(
        # File path needed to check
        [Parameter(Mandatory = $true)]
        [String]$FilePath,
        [Switch]$Warning
    )
    $inputFileExist = Test-Path $FilePath
    if (!$inputFileExist)
    {
        if ($Warning -eq $false) 
        { 
            WriteToLog -Type "Failed" -Message "[File: $FilePath] The file doesn't exist"
            throw 
        }
        else 
        { 
            WriteToLog -Type "Warning" -Message "[File: $FilePath] The file doesn't exist"
        }
    }
    else
    {
        WriteToLog -Type "Succeed" -Message "[File: $FilePath] The file is found"
    }
}
# -------------------
# Log operation
# -------------------
Function WriteToLog
{
    Param(
        # Message want to write to log file
        [Parameter(Mandatory = $true)]
        [String]$Message,
        # "Succeed" or "Faild"
        [String]$Type = "Message"
    )
    $date = Get-Date -Format 'HH:mm:ss'
    $logInfo = $date + " - [$Type] " + $Message
    $logInfo | Out-File -FilePath $logfilePath -Append
    if ($Type -eq "Succeed") { Write-Host $logInfo -ForegroundColor Green }
    elseif ($Type -eq "Failed") { Write-Host $logInfo -ForegroundColor Red }
    elseif ($Type -eq "Warning") { Write-Host $logInfo -ForegroundColor Yellow }
    elseif ($Type -eq "Start") { Write-Host $logInfo -ForegroundColor Cyan }
    else { Write-Verbose $logInfo }
}
Function Create-Log
{
    Param(
        # Log folder Root
        [Parameter(Mandatory = $true)]
        [String]$LogFolderRoot,
        # The function Log file for
        [Parameter(Mandatory = $true)]
        [String]$LogFunction
    )
    $logFolderPath = "$LogFolderRoot\logfiles"
    $folderExist = Test-Path "$logFolderPath"
    if (!$folderExist)
    {
        $folder = New-Item "$logFolderPath" -type directory
    }
    $date = Get-Date -Format 'MMddyyyy_HHmmss'
    $logfilePath = "$logFolderPath\Log_{0}_{1}.txt" -f $LogFunction, $date
    Write-Verbose "Log file is writen to: $logfilePath"
    $logfile = New-Item $logfilePath  -type file
    return $logfilePath
}
Function Create-ResultCSV
{
    Param(
        # Result folder Root
        [Parameter(Mandatory = $true)]
        [String]$ResultFolderRoot,
        # The function Result file for
        [Parameter(Mandatory = $true)]
        [String]$ResultFunction
    )
    $retFolderPath = "$ResultFolderRoot\logfiles"
    $folderExist = Test-Path "$retFolderPath"
    if (!$folderExist)
    {
        $folder = New-Item "$retFolderPath" -type directory
    }
    $date = Get-Date -Format 'MMddyyyy_HHmmss'
    $retfilePath = "$retFolderPath\Result_{0}_{1}.csv" -f $ResultFunction, $date
    Write-Verbose "Result file is writen to: $retfilePath"
    $retfile = New-Item $retfilePath  -type file
    return $retfilePath
}
# -------------------
# Prepare Log File
# -------------------
$scriptPath = '.\'
$logfilePath = Create-Log -LogFolderRoot $scriptPath -LogFunction "Publish_Compliance_Tag"
if ($ResultCSV)
{
    $tagRetFile = Create-ResultCSV -ResultFolderRoot $scriptPath -ResultFunction "Tag_Creation"
    $tagPubRetFile = Create-ResultCSV -ResultFolderRoot $scriptPath -ResultFunction "Tag_Publish"
}
# -------------------
# Invoke Powershell cmdlet
# -------------------
Function InvokePowerShellCmdlet
{
    Param(
        [Parameter(Mandatory = $true)]
        [String]$CmdLet
    )
    try
    {
        WriteToLog -Type "Start" -Message "Execute Cmdlet : '$CmdLet'" 
        return Invoke-Expression $CmdLet -ErrorAction SilentlyContinue
    }
    catch
    {
        WriteToLog -Type "Failed" "Failed to execute cmdlet!"
        WriteToLog -Type "Failed" $error[0]
        return $null
    }
}
# -------------------
# Create Compliance Tag
# -------------------
Function CreateComplianceTag
{
    Param(
        # File path needed to check
        [Parameter(Mandatory = $true)]
        [String]$FilePath
    )
    
    WriteToLog -Type "Start" "Start to create Compliance Tag"
    FileExist $FilePath
    
    # TODO Validate CSV file for the Header
    try
    {
        # Import csv
        $labels = Import-Csv $FilePath
        # Retrieve existing compliance tags
        $tags = InvokePowerShellCmdlet "Get-ComplianceTag"
        foreach($lab in $labels)
        {
            # Cmdlet parameters
            $para = [String]::Empty;
            $name = [String]::Empty;
            $cmdlet = 'New-ComplianceTag'
            if ([String]::IsNullOrEmpty($lab.'Name (Required)'))
            {
                WriteToLog -Type "Failed" -Message "Could not acquire table for writing."
                throw;
            }
            else
            {
                $name = $lab.'Name (Required)'
                $cmdlet += " -Name '" + $name + "'"
            }
            if (![String]::IsNullOrEmpty($lab.'Comment (Optional)'))
            {
                $para = $lab.'Comment (Optional)'
                $cmdlet += " -Comment '" + $para + "'"
            }
            if (![String]::IsNullOrEmpty($lab.'IsRecordLabel (Required)'))
            {
                $para = $lab.'IsRecordLabel (Required)'
                $cmdlet += " -IsRecordLabel " + $para
            }
            if (![String]::IsNullOrEmpty($lab.'RetentionAction (Optional)'))
            {
                $para = $lab.'RetentionAction (Optional)'
                $cmdlet += " -RetentionAction " + $para 
            }
            if (![String]::IsNullOrEmpty($lab.'RetentionDuration (Optional)'))
            {
                $para = $lab.'RetentionDuration (Optional)'
                $cmdlet += " -RetentionDuration " + $para
            }
            if (![String]::IsNullOrEmpty($lab.'RetentionType (Optional)'))
            {
                $para = $lab.'RetentionType (Optional)'
                $cmdlet += " -RetentionType " + $para
            }
            if (![String]::IsNullOrEmpty($lab.'ReviewerEmail (Optional)'))
            {
                $emails = $lab.'ReviewerEmail (Optional)'.Split(",") | ForEach-Object { $_.Trim() }
                if (($emails -ne $null) -and ($emails.Count -ne 0))
                {
                    $eml = '@('
                    foreach($email in $emails)
                    {
                        $eml += "'{0}'," -f $email
                    }
                    $eml = $eml.Substring(0, $eml.Length - 1) + ')'
                    
                    $cmdlet += " -ReviewerEmail " + $eml
                }
            }
            # If the tag already exists, skip for creation
            if (($tags -eq $null) -or ($tags | ? { $_.Name.ToLower() -eq $name.ToLower() }) -eq $null)
            {
                # Create compliance tag
                $msg = "Execute Cmdlet : {0}" -f $cmdlet
                
                $ret = InvokePowerShellCmdlet $cmdlet
            
                if ($ret -eq $null)
                {
                    WriteToLog -Type "Failed" $error[0]
                    break;
                }
            }
            else
            {
                WriteToLog -Type "Warning" -Message "The tag '$name' already exists! Skip for creation!"
            }
        }
    }
    catch
    {
        WriteToLog -Type "Failed" "Error in input"
    }
}
# -------------------
# Create Retention Compliance Policy
# -------------------
Function CreateRetentionCompliancePolicy
{
    Param(
        # File path needed to check
        [Parameter(Mandatory = $true)]
        [String]$FilePath
    )
    
    WriteToLog -Type "Start" "Start to Create Retention Policy"
    FileExist $FilePath
    try
    {
        # Import csv
        $list = Import-Csv -Path $FilePath
        # Retrieve existing retention compliance policy
        $policies = InvokePowerShellCmdlet "Get-RetentionCompliancePolicy"
        foreach($rp in $list)
        {
            # Cmdlet parameters
            $para = [String]::Empty;
            $name = [String]::Empty;
            $rpid = [String]::Empty;
            $cmdlet = 'New-RetentionCompliancePolicy'
            if ([String]::IsNullOrEmpty($rp.'Policy Name (Required)'))
            {
                WriteToLog -Type "Failed" -Message "Could not acquire table for writing."
                throw;
            }
            else
            {
               $name = $rp.'Policy Name (Required)'
               $cmdlet += " -Name '" + $name + "'"
            }
            if ([String]::IsNullOrEmpty($rp.'Enabled (Required)'))
            {
                WriteToLog -Type "Failed" -Message "Could not acquire table for writing."
                throw;
            }
            else
            {
                $enabled = $rp.'Enabled (Required)'
                $cmdlet += " -Enabled " + $enabled
            }
            if (![String]::IsNullOrEmpty($rp.'ExchangeLocation (Optional)'))
            {
                $para = $rp.'ExchangeLocation (Optional)'
                $cmdlet += " -ExchangeLocation " + $para
            }
         
            if (![String]::IsNullOrEmpty($rp.'ExchangeLocationException (Optional)'))
            {
                $para = $rp.'ExchangeLocationException (Optional)'
                $cmdlet += " -ExchangeLocationException " + $para
            }
            if (![String]::IsNullOrEmpty($rp.'ModernGroupLocation (Optional)'))
            {
                $para = $rp.'ModernGroupLocation (Optional)'
                $cmdlet += " -ModernGroupLocation " + $para
            }
            if (![String]::IsNullOrEmpty($rp.'ModernGroupLocationException (Optional)'))
            {
                $para = $rp.'ModernGroupLocationException (Optional)'
                $cmdlet += " -ModernGroupLocationException " + $para
            }
            if (![String]::IsNullOrEmpty($rp.'OneDriveLocation (Optional)'))
            {
                $para = $rp.'OneDriveLocation (Optional)'
                $cmdlet += " -OneDriveLocation " + $para
            }
            if (![String]::IsNullOrEmpty($rp.'OneDriveLocationException (Optional)'))
            {
                $para = $rp.'OneDriveLocationException (Optional)'
                $cmdlet += " -OneDriveLocationException " + $para
            }
            if (![String]::IsNullOrEmpty($rp.'SharePointLocation (Optional)'))
            {
                $para = $rp.'SharePointLocation (Optional)'
                $cmdlet += " -SharePointLocation " + $para
            }
            if (![String]::IsNullOrEmpty($rp.'SharePointLocationException (Optional)'))
            {
                $para = $rp.'SharePointLocationException (Optional)'
                $cmdlet += " -SharePointLocationException " + $para
            }
            if (![String]::IsNullOrEmpty($rp.'PublicFolderLocation (Optional)'))
            {
                $para = $rp.'PublicFolderLocation (Optional)'
                $cmdlet += " -PublicFolderLocation " + $para
            }
            if (![String]::IsNullOrEmpty($rp.'SkypeLocation (Optional)'))
            {
                $para = $rp.'SkypeLocation (Optional)'
                $cmdlet += " -SkypeLocation " + $para
            }
            if (![String]::IsNullOrEmpty($rp.'SkypeLocationException (Optional)'))
            {
                $para = $rp.'SkypeLocationException (Optional)'
                $cmdlet += " -SkypeLocationException " + $para
            }
            # If the policy already exists, skip for creation
            if (($policies -eq $null) -or ($policies | ? { $_.Name.ToLower() -eq $name.ToLower() }) -eq $null)
            {
                # Create retention compliance policy
                $msg = "Execute Cmdlet : {0}" -f $cmdlet
            
                $ret = invokepowershellcmdlet $cmdlet
            
                if ($ret -eq $null)
                {
                    WriteToLog -Type "Failed" $error[0]
                    break;
                }
                $rpid = $ret.Guid
            }
            else
            {
                WriteToLog -Type "Warning" -Message "The policy '$name' already exists! Skip for creation!"
                $rpid = ($policies | ? { $_.Name.ToLower() -eq $name.ToLower() }).Guid
            }
                        
            # Retrieve tag name for publishing
            $ts = $rp.'PublishComplianceTag (Required)'
            $tagList = $ts.Split(",") | ForEach-Object { $_.Trim() }
            
            WriteToLog -Type "Message" -Message "Publish Tags : '$ts'" 
            
            PublishComplianceTag -PolicyGuid $rpid -TagName $tagList
        }
    }
    catch
    {
        WriteToLog -Type "Failed" "Error in input"
    }
}
# -------------------
# Publish Compliance Tag
# -------------------
Function PublishComplianceTag
{
    Param(
        [Parameter(Mandatory = $true)]
        [String]$PolicyGuid,
        [Parameter(Mandatory = $true)]
        [String[]]$TagNames
    )
    
    WriteToLog -Type "Start" "Start to Publish Compliance Tag"
    try
    {
        # Retrieve existing rule related to the given compliance policy
        $rule = InvokePowerShellCmdlet ("Get-RetentionComplianceRule -Policy {0}" -f $PolicyGuid)
        $tagGuids = New-Object System.Collections.ArrayList
        
        foreach ($tn in $TagNames)
        {
            $t = InvokePowerShellCmdlet ("Get-ComplianceTag {0}" -f $tn)
            $tagGuids.Add($t.Guid) | Out-Null
        }
        if ($rule -ne $null)
        {
            foreach ($r in $rule)
            {
                if ([String]::IsNullOrEmpty($r.PublishComplianceTag))
                {
                    continue;
                }
                else
                {
                    $tl = $r.PublishComplianceTag.Split(",")
                    if ($tagGuids.Contains([GUID]$tl[0]))
                    {
                        $tagGuids.Remove([GUID]$tl[0]);
                    }
                }
            }
        }
        
        foreach($t in $tagGuids)
        {
            # Publish compliance tag
            $cmdlet = "New-RetentionComplianceRule -Policy {0} -PublishComplianceTag {1}" -f $PolicyGuid, $t
            $ret = InvokePowerShellCmdlet $cmdlet
            
            if ($ret -eq $null)
            {
                WriteToLog -Type "Failed" $error[0]
                break;
            }
        }
    }
    catch
    {
        WriteToLog -Type "Failed" "Error in input"
    }
}
# -------------------
# Export All Labels Created in The Process
# -------------------
Function ExportCreatedComplianceTag
{
    Param(
        [Parameter(Mandatory = $true)]
        [String]$LabelFilePath
    )
    
    WriteToLog -Type "Start" "Start to Export Compliance Tag Created"
    try
    {
        # Import input csv
        $labels = Import-Csv $LabelFilePath
        # Create result table
        $tabName = "ResultTable"
        $table = New-Object system.Data.DataTable "$tabName"
        $col1 = New-Object system.Data.DataColumn Name,([string])
        $col2 = New-Object system.Data.DataColumn Comment,([string])
        $col3 = New-Object system.Data.DataColumn IsRecordLabel,([string])
        $col4 = New-Object system.Data.DataColumn RetentionAction,([string])
        $col5 = New-Object system.Data.DataColumn RetentionDuration,([string])
        $col6 = New-Object system.Data.DataColumn RetentionType,([string])
        $col7 = New-Object system.Data.DataColumn ReviewerEmail,([string])
        
        # Add the Columns
        $table.columns.add($col1)
        $table.columns.add($col2)
        $table.columns.add($col3)
        $table.columns.add($col4)
        $table.columns.add($col5)
        $table.columns.add($col6)
        $table.columns.add($col7)
        foreach($lab in $labels)
        {
            $t = InvokePowerShellCmdlet ("Get-ComplianceTag '{0}' " -f $lab.'Name (Required)')
            
            # Create a result row
            $row = $table.NewRow()
            $row['Name'] = $t.Name
            $row['Comment'] = $t.Comment
            $row['IsRecordLabel'] = $t.IsRecordLabel
            $row['RetentionAction'] = $t.RetentionAction
            $row['RetentionDuration'] = $t.RetentionDuration
            $row['RetentionType'] = $t.RetentionType
            $row['ReviewerEmail'] = $t.ReviewerEmail
            
            # Add the row to the table
            $table.Rows.Add($row)
        }
        $table | Export-Csv $tagRetFile -NoTypeInformation
    }
    catch
    {
        WriteToLog -Type "Failed" "Error in exporting results."
    }
}
# -------------------
# Export All Published Labels and Policies in The Process
# -------------------
Function ExportPublishedComplianceTagAndPolicy
{
    Param(
        [Parameter(Mandatory = $true)]
        [String[]]$PolicyFilePath
    )
    
    WriteToLog -Type "Start" "Start to Export Published Compliance Tag and Policy"
    try
    {
        # Import input csv
        $policies = Import-Csv $PolicyFilePath
        # Create result table
        $tabName = "ResultTable"
        $table = New-Object system.Data.DataTable "$tabName"
        $col1 = New-Object system.Data.DataColumn 'Policy Name',([string])
        $col2 = New-Object system.Data.DataColumn PublishComplianceTag,([string])
        $col3 = New-Object system.Data.DataColumn Comment,([string])
        $col4 = New-Object system.Data.DataColumn Enabled,([string])
        $col5 = New-Object system.Data.DataColumn ExchangeLocation,([string])
        $col6 = New-Object system.Data.DataColumn ExchangeLocationException,([string])
        $col7 = New-Object system.Data.DataColumn ModernGroupLocation,([string])
        $col8 = New-Object system.Data.DataColumn ModernGroupLocationException,([string])
        $col9 = New-Object system.Data.DataColumn OneDriveLocation,([string])
        $col10 = New-Object system.Data.DataColumn OneDriveLocationException,([string])
        $col11 = New-Object system.Data.DataColumn PublicFolderLocation,([string])
        $col12 = New-Object system.Data.DataColumn SharePointLocation,([string])
        $col13 = New-Object system.Data.DataColumn SharePointLocationException,([string])
        $col14 = New-Object system.Data.DataColumn SkypeLocation,([string])
        $col15 = New-Object system.Data.DataColumn SkypeLocationException,([string])
        
        # Add the Columns
        $table.columns.add($col1)
        $table.columns.add($col2)
        $table.columns.add($col3)
        $table.columns.add($col4)
        $table.columns.add($col5)
        $table.columns.add($col6)
        $table.columns.add($col7)
        $table.columns.add($col8)
        $table.columns.add($col9)
        $table.columns.add($col10)
        $table.columns.add($col11)
        $table.columns.add($col12)
        $table.columns.add($col13)
        $table.columns.add($col14)
        $table.columns.add($col15)
        foreach($policy in $policies)
        {
            $t = InvokePowerShellCmdlet ("Get-RetentionCompliancePolicy '{0}' -DistributionDetail" -f $policy.'Policy Name (Required)')
            
            # Create a result row
            $row = $table.NewRow()
            $row['Policy Name'] = $t.Name
            
            $rules = InvokePowerShellCmdlet ("Get-RetentionComplianceRule -Policy {0}" -f $t.Guid)
            $tagList = [String]::Empty
            foreach($rule in $rules)
            {
                if ([String]::IsNullOrEmpty($rule.PublishComplianceTag) -eq $False)
                {
                    $tName = $rule.PublishComplianceTag.Split(',')[1]
                    $tagList = [String]::Concat($tagList, $tName, ",")
                }
            }
            if (![String]::IsNullOrEmpty($tagList))
            {
                $tagList = $tagList.Substring(0, $tagList.LastIndexOf(','))
            }
            $row['PublishComplianceTag'] = $tagList
            $row['Comment'] = $t.Comment
            $row['Enabled'] = $t.Enabled
            $row['ExchangeLocation'] = $t.ExchangeLocation
            $row['ExchangeLocationException'] = $t.ExchangeLocationException
            $row['ModernGroupLocation'] = $t.ModernGroupLocation
            $row['ModernGroupLocationException'] = $t.ModernGroupLocationException
            $row['OneDriveLocation'] = $t.OneDriveLocation
            $row['OneDriveLocationException'] = $t.OneDriveLocationException
            $row['PublicFolderLocation'] = $t.PublicFolderLocation
            $row['SharePointLocation'] = $t.SharePointLocation
            $row['SharePointLocationException'] = $t.SharePointLocationException
            $row['SkypeLocation'] = $t.SkypeLocation
            $row['SkypeLocationException'] = $t.SkypeLocationException
            
            # Add the row to the table
            $table.Rows.Add($row)
        }
        $table | Export-Csv $tagPubRetFile -NoTypeInformation
    }
    catch
    {
        WriteToLog -Type "Failed" "Error in exporting results."
    }
}
# Create compliance tag
CreateComplianceTag -FilePath $LabelListCSV
# Create retention policy and publish compliance tag with the policy
CreateRetentionCompliancePolicy -FilePath $PolicyListCSV
# Export to result csv
if ($ResultCSV)
{
    ExportCreatedComplianceTag -LabelFilePath $LabelListCSV
    ExportPublishedComplianceTagAndPolicy -PolicyFilePath $PolicyListCSV 
}

```

## <a name="step-4-connect-to-security-amp-compliance-center-powershell"></a><span data-ttu-id="743f6-150">Paso 4: Conectarse a PowerShell del Centro de seguridad y cumplimiento</span><span class="sxs-lookup"><span data-stu-id="743f6-150">Step 4: Connect to Security &amp; Compliance Center PowerShell</span></span>

<span data-ttu-id="743f6-151">Siga los pasos descritos aquí:</span><span class="sxs-lookup"><span data-stu-id="743f6-151">Follow the steps here:</span></span>
  
- [<span data-ttu-id="743f6-152">Conectarse a PowerShell del Centro de seguridad y cumplimiento de Office 365</span><span class="sxs-lookup"><span data-stu-id="743f6-152">Connect to Office 365 Security &amp; Compliance Center PowerShell</span></span>](https://go.microsoft.com/fwlink/?linkid=799771)
    
## <a name="step-5-run-the-powershell-script-to-create-and-publish-the-labels"></a><span data-ttu-id="743f6-153">Paso 5: Ejecutar el script de PowerShell para crear y publicar las etiquetas</span><span class="sxs-lookup"><span data-stu-id="743f6-153">Step 5: Run the PowerShell script to create and publish the labels</span></span>

<span data-ttu-id="743f6-154">Después de conectarse a PowerShell del Centro de seguridad y cumplimiento, ejecute el script que crea y publica las etiquetas.</span><span class="sxs-lookup"><span data-stu-id="743f6-154">After you've connected to Security &amp; Compliance Center PowerShell, next you run the script that creates and publishes the labels.</span></span>
  
1. <span data-ttu-id="743f6-155">En la sesión de PowerShell del Centro de seguridad y cumplimiento, escriba la ruta de acceso, seguida de los caracteres .\ y el nombre de archivo del script y, después, presione ENTRAR para ejecutar el script, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="743f6-155">In the Security &amp; Compliance PowerShell session, enter the path, followed by the characters .\ and file name of the script, and then press ENTER to run the script - for example:</span></span>
    
  ```
  <path>.\CreateRetentionSchedule.ps1
  ```

    <span data-ttu-id="743f6-156">El script le pedirá las ubicaciones de los archivos .csv que creó anteriormente.</span><span class="sxs-lookup"><span data-stu-id="743f6-156">The script will prompt you for the locations of the .csv files that you created above.</span></span>
    
2. <span data-ttu-id="743f6-157">Escriba la ruta de acceso, seguida de los caracteres .\ y el nombre del archivo .csv y, después, presione ENTRAR; por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="743f6-157">Enter the path, followed by the characters .\ and file name of the .csv file, and then press ENTER - for example:</span></span>
    
  ```
  <path>.\LabelsToCreate.csv
  ```

## <a name="step-6-view-the-log-file-with-the-results"></a><span data-ttu-id="743f6-158">Paso 6: Ver el archivo de registro con los resultados</span><span class="sxs-lookup"><span data-stu-id="743f6-158">Step 6: View the log file with the results</span></span>

<span data-ttu-id="743f6-p113">Al ejecutar el script, este genera un archivo de registro de cada acción que realizó y si se ha completado correctamente o con errores. En el archivo de registro, se incluyen todos los metadatos sobre las etiquetas que se han creado y publicado. Encontrará el archivo de registro en esta ubicación (tenga en cuenta que los dígitos del nombre de archivo pueden variar).</span><span class="sxs-lookup"><span data-stu-id="743f6-p113">When you run the script, it generates a log file that records each action it took and whether the action succeeded or failed. The log file includes all metadata about what labels were created and what labels were published. You can find the log file at this location -- note that the digits in the file name vary.</span></span>
  
```
<path>.\Log_Publish_Compliance_Tag_01112018_151239.txt
```


