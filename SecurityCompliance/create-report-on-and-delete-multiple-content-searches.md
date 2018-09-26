---
title: Crear, informar sobre y eliminar varias búsquedas de contenido
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/26/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- SPO160
- MOE150
ms.assetid: 1d463dda-a3b5-4675-95d4-83db19c9c4a3
description: Obtenga información sobre cómo automatizar las tareas de búsqueda de contenido como creación de búsquedas y ejecución de informes a través de secuencias de comandos de PowerShell en la seguridad de Office 365 &amp; centro de cumplimiento.
ms.openlocfilehash: a32c003dfd9a27ea8c38b29b31001b612368bc4a
ms.sourcegitcommit: 7956955cd919f6e00b64e4506605a743c5872549
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/26/2018
ms.locfileid: "25038143"
---
# <a name="create-report-on-and-delete-multiple-content-searches"></a>Crear, informar sobre y eliminar varias búsquedas de contenido

 Crear rápidamente y búsquedas de descubrimiento de informes a menudo es un paso importante en la exhibición de documentos electrónicos y las investigaciones cuando intenta obtener más información acerca de los datos subyacentes y la flexibilidad y la calidad de las búsquedas. Para ayudarle a hacer esto, la seguridad &amp; centro de cumplimiento ofrece un conjunto de cmdlets de Windows PowerShell para automatizar las tareas de búsqueda de contenido mucho tiempo. Estas secuencias de comandos proporcionan un modo rápido y fácil para crear un número de búsquedas y, a continuación, ejecutan informes de los resultados de búsqueda estimado que pueden ayudarle a determinar la cantidad de datos en cuestión. También puede usar las secuencias de comandos para crear diferentes versiones de búsquedas para comparar los resultados de que cada uno de ellos produce. Estos scripts pueden ayudarle a identificar y seleccionamos los datos rápidamente y eficaz. 
  
## <a name="before-you-begin"></a>Antes de empezar

- Tiene que ser un miembro del grupo de roles de administrador de exhibición de documentos electrónicos en la seguridad &amp; centro de cumplimiento para ejecutar las secuencias de comandos que se describen en este tema. 
    
- Para recopilar una lista de las direcciones URL para el OneDrive para sitios de profesionales de la organización que se puede agregar al archivo CSV en el paso 1, vea [crear una lista de todas las ubicaciones de OneDrive en la organización](https://support.office.com/article/Create-a-list-of-all-OneDrive-locations-in-your-organization-8e200cb2-c768-49cb-88ec-53493e8ad80a). 
    
- Asegúrese de guardar todos los archivos que cree en este tema para la misma carpeta. Que facilitan ejecutar las secuencias de comandos.
    
- Las secuencias de comandos incluyen el tratamiento de errores mínima. Su propósito principal es crear rápidamente, informar sobre y eliminar varias búsquedas de contenido.
    
- Los scripts de ejemplo que se proporcionan en este tema no son compatibles con ningún servicio o programa de soporte técnico estándar de Microsoft. Los scripts de ejemplo se proporcionan tal cual, sin garantía de ningún tipo. Además, Microsoft se exime de todas las garantías implícitas, incluidas (sin limitación) las garantías implícitas de comerciabilidad o idoneidad para un propósito específico. El usuario asume todos los riesgos derivados del uso o del rendimiento de los scripts de ejemplo y la documentación. Microsoft, sus autores o cualquier persona relacionada con la creación, producción o entrega de los scripts no serán en ningún caso responsables de cualesquiera daños (incluidos, sin limitación, los daños producidos por la pérdida de beneficios comerciales, interrupción de la actividad comercial, pérdida de información empresarial u otras pérdidas económicas) derivados del uso o de la imposibilidad de uso de los scripts de ejemplo o la documentación, incluso aunque Microsoft tenga constancia de la posibilidad de que dichos daños se produzcan.
    
## <a name="step-1-create-a-csv-file-that-contains-information-about-the-searches-you-want-to-run"></a>Paso 1: Crear un archivo CSV que contiene información acerca de las búsquedas que desea ejecutar

El archivo (CSV) de valores separados por comas que cree en este paso contiene una fila para cada usuario que desea buscar. Puede buscar en el buzón del usuario Exchange Online (que incluye el buzón de archivo, si está habilitado) y su OneDrive para el sitio de negocio. O bien, puede buscar en el buzón de correo o la OneDrive para el sitio de negocio. También puede buscar cualquier sitio en la organización de SharePoint Online. La secuencia de comandos que se ejecutan en el paso 3 va a crear una búsqueda independiente para cada fila en el archivo CSV. 
  
1. Copie y pegue el siguiente texto en un archivo .txt utilizando el Bloc de notas. Guarde este archivo en una carpeta en el equipo local. Ahorrará a las otras secuencias de comandos para esta carpeta también.
    
    ```
    ExchangeLocation,SharePointLocation,ContentMatchQuery,StartDate,EndDate
    sarad@contoso.onmicrosoft.com,https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft_com,(lawsuit OR legal),1/1/2000,12/31/2005
    sarad@contoso.onmicrosoft.com,https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft_com,(lawsuit OR legal),1/1/2006,12/31/2010
    sarad@contoso.onmicrosoft.com,https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft_com,(lawsuit OR legal),1/1/2011,3/21/2016
    ,https://contoso.sharepoint.com/sites/contoso,,,3/21/2016
    ,https://contoso-my.sharepoint.com/personal/davidl_contoso_onmicrosoft_com,,1/1/2015,
    ,https://contoso-my.sharepoint.com/personal/janets_contoso_onmicrosoft_com,,1/1/2015,
    ```

    La primera fila o la fila de encabezado, del archivo se enumera los parámetros que se usará para crear un nuevo búsquedas de contenido mediante el cmdlet **New-ComplianceSearch** (en la secuencia de comandos en el paso 3). Cada nombre de parámetro viene separada por una coma. Asegúrese de que no hay espacios en la fila de encabezado. Cada fila debajo de la fila de encabezado representa los valores de parámetro para cada búsqueda. Asegúrese de reemplazar los datos de marcador de posición en el archivo CSV con los datos reales. 
    
2. Abra el archivo .txt en Excel y, a continuación, use la información en la tabla siguiente para editar el archivo con información para cada búsqueda. 
    
    |**Parámetro**|**Descripción**|
    |:-----|:-----|
    | `ExchangeLocation` <br/> |La dirección SMTP del buzón del usuario.  <br/> |
    | `SharePointLocation` <br/> |La dirección URL para OneDrive del usuario para el sitio de negocio o la dirección URL de cualquier sitio de la organización. Para la dirección URL de OneDrive para sitios de negocio, use este formato: ` https://<your organization>-my.sharepoint.com/personal/<user alias>_<your organization>_onmicrosoft_com `. Por ejemplo, `https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft_com`.<br/> |
    | `ContentMatchQuery` <br/> |La consulta de búsqueda para la búsqueda. Para obtener más información acerca de cómo crear una consulta de búsqueda, vea [consultas de palabra clave y las condiciones de búsqueda para la búsqueda de contenido](keyword-queries-and-search-conditions.md).<br/> |
    | `StartDate` <br/> |Para el correo electrónico, la fecha en o después de un mensaje se ha recibido por un destinatario o enviado por el remitente. Para documentos de SharePoint o en OneDrive para sitios de negocio, la fecha en o después de un documento se modificó por última vez.  <br/> |
    | `EndDate` <br/> |Para el correo electrónico, la fecha en o antes de un mensaje se envió por enviado por el usuario. Para documentos de SharePoint o en OneDrive para sitios de negocio, la fecha en o antes de un documento se modificó por última vez.  <br/> |
   
3. Guarde el archivo de Excel como un archivo CSV a una carpeta en el equipo local. La secuencia de comandos que se crea en el paso 3 use la información de este archivo CSV para crear las búsquedas. 
  
## <a name="step-2-connect-to-security--compliance-center-powershell"></a>Paso 2: Conectarse a PowerShell de centro de cumplimiento y seguridad

El siguiente paso es conectar Windows PowerShell a la seguridad &amp; centro de cumplimiento de normas de la organización.
  
1. Guarde el siguiente texto en un archivo de secuencia de comandos de Windows PowerShell mediante el uso de un sufijo de nombre de archivo de. ps1; Por ejemplo, `ConnectSCC.ps1`. Guarde el archivo en la misma carpeta que haya guardado el archivo CSV para en el paso 1.
    
    ```
    # Get login credentials 
    $UserCredential = Get-Credential 
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Credential $UserCredential -Authentication Basic -AllowRedirection 
    Import-PSSession $Session -AllowClobber -DisableNameChecking 
    $Host.UI.RawUI.WindowTitle = $UserCredential.UserName + " (Office 365 Security &amp; Compliance Center)" 
    ```

2. En el equipo local, abra Windows PowerShell, vaya a la carpeta donde se encuentra la secuencia de comandos que creó en el paso anterior y, a continuación, ejecute el script; Por ejemplo:
    
    ```
    .\ConnectSCC.ps1
    ```
  
## <a name="step-3-run-the-script-to-create-and-start-the-searches"></a>Paso 3: Ejecutar el script para crear e iniciar las búsquedas

La secuencia de comandos en este paso va a crear una búsqueda de contenido independientes para cada fila en el archivo CSV que creó en el paso 1. Al ejecutar este script, se le pedirá para dos valores:
  
- **Identificador de grupo de búsqueda** - este nombre proporciona una manera sencilla de organizar las búsquedas que se crean desde el archivo CSV. Se denomina cada búsqueda que se crea con el identificador de grupo de búsqueda y, a continuación, se anexa un número en el nombre de la búsqueda. Por ejemplo, si especifica **ContosoCase** para el identificador de grupo de búsqueda, las búsquedas se denominan **ContosoCase_1**, **ContosoCase_2**, **ContosoCase_3**y así sucesivamente. Tenga en cuenta que el nombre que escriba distingue mayúsculas de minúsculas. Cuando se usa el identificador de grupo de búsqueda en el paso 4 y el paso 5, se debe usar el mismo caso tal como hizo al crearlo. 
    
- **Archivo CSV** : el nombre del archivo CSV que creó en el paso 1. No olvide incluir el uso del nombre de archivo completo, incluir la extensión de archivo .csv; Por ejemplo, `ContosoCase.csv`.
    
Para ejecutar el script:

1. Guarde el siguiente texto en un archivo de secuencia de comandos de Windows PowerShell mediante el uso de un sufijo de nombre de archivo de. ps1; Por ejemplo, `CreateSearches.ps1`. Guarde el archivo en la misma carpeta donde guardó los archivos de otros.
    
  ```
  # Get the Search Group ID and the location of the CSV input file
  $searchGroup = Read-Host 'Search Group ID'
  $csvFile = Read-Host 'Source CSV file'
    
  # Do a quick check to make sure our group name will not collide with other searches
  $searchCounter = 1
  import-csv $csvFile |
    ForEach-Object{
    
    $searchName = $searchGroup +'_' + $searchCounter
    $search = Get-ComplianceSearch $searchName -EA SilentlyContinue
    if ($search)
    {
        Write-Error "The Search Group ID conflicts with existing searches.  Please choose a search group name and restart the script."
        return
    }
    $searchCounter++
  }
    
  $searchCounter = 1
  import-csv $csvFile |
    ForEach-Object{
    
    # Create the query
    $query = $_.ContentMatchQuery
    if(($_.StartDate -or $_.EndDate))
    {
          # Add the appropriate date restrictions.  NOTE: Using the Date condition property here because it works across Exchange, SharePoint, and OneDrive for Business.
          # For Exchange, the Date condition property maps to the Sent and Received dates; for SharePoint and OneDrive for Business, it maps to Created and Modified dates.
          if($query)
          {
              $query += " AND"
          }
          $query += " ("
          if($_.StartDate)
          {
              $query += "Date >= " + $_.StartDate
          }
          if($_.EndDate)
          {
              if($_.StartDate)
              {
                  $query += " AND "
              }
              $query += "Date <= " + $_.EndDate
          }
          $query += ")"
    }
      
      # -ExchangeLocation can't be set to an empty string, set to null if there's no location.
      $exchangeLocation = $null
      if ( $_.ExchangeLocation)
      {
           $exchangeLocation = $_.ExchangeLocation
      }
    
    # Create and run the search        
    $searchName = $searchGroup +'_' + $searchCounter
    Write-Host "Creating and running search: " $searchName -NoNewline
    $search = New-ComplianceSearch -Name $searchName -ExchangeLocation $exchangeLocation -SharePointLocation $_.SharePointLocation -ContentMatchQuery $query
    
    # Start and wait for each search to complete
    Start-ComplianceSearch $search.Name
    while ((Get-ComplianceSearch $search.Name).Status -ne "Completed")
    {
        Write-Host " ." -NoNewline
        Start-Sleep -s 3
    }
    Write-Host ""
    
    $searchCounter++
  }
  ```

2. En Windows PowerShell, vaya a la carpeta donde guardó el script en el paso anterior y, a continuación, ejecute el script; Por ejemplo:
    
    ```
    .\CreateSearches.ps1
    ```

3. En el símbolo del sistema de **Identificador de grupo de búsqueda** , escriba un nombre de grupo de búsqueda y, a continuación, presione **ENTRAR**; Por ejemplo, `ContosoCase`. Recuerde que este nombre distingue entre mayúsculas y minúsculas, por lo que tendrá que escribir la misma manera en los pasos posteriores.
    
4. En el símbolo del sistema de **archivo CSV de origen** , escriba el nombre del archivo CSV, incluida la extensión de archivo .csv; Por ejemplo, `ContosoCase.csv`.
    
5. Presione **ENTRAR** para continuar la ejecución del script. 
    
    La secuencia de comandos muestra el progreso de la creación y ejecución de las búsquedas. Una vez finalizada la secuencia de comandos, devuelve en el símbolo del sistema. 
    
    ![Resultado de ejemplo de la ejecución de la secuencia de comandos para crear varias búsquedas de cumplimiento](media/37d59b0d-5f89-4dbc-9e2d-0e88e2ed7b4c.png)
  
## <a name="step-4-run-the-script-to-report-the-search-estimates"></a>Paso 4: Ejecute estimaciones de la secuencia de comandos para informar de la búsqueda

Después de crear las búsquedas, el siguiente paso es ejecutar un script que se muestra un informe simple del número de aciertos en la búsqueda para cada búsqueda que se creó en el paso 3. El informe también incluye el tamaño de los resultados para cada búsqueda y el número total de visitas y el tamaño total de todas las búsquedas. Al ejecutar el script de generación de informes, se le pedirá para el identificador de grupo de búsqueda y un nombre de archivo CSV si desea guardar el informe a un archivo CSV.
  
1. Guarde el siguiente texto en un archivo de secuencia de comandos de Windows PowerShell mediante el uso de un sufijo de nombre de archivo de. ps1; Por ejemplo, `SearchReport.ps1`. Guarde el archivo en la misma carpeta donde guardó los archivos de otros.
    
  ```
  $searchGroup = Read-Host 'Search Group ID'
  $outputFile = Read-Host 'Enter a file name or file path to save the report to a .csv file. Leave blank to only display the report'
  $searches = Get-ComplianceSearch | ?{$_.Name -clike $searchGroup + "_*"}
  $allSearchStats = @()
  foreach ($partialObj in $searches)
  {
      $search = Get-ComplianceSearch $partialObj.Name
      $sizeMB = [System.Math]::Round($search.Size / 1MB, 2)
      $searchStatus = $search.Status
      if($search.Errors)
      {
          $searchStatus = "Failed"
      }elseif($search.NumFailedSources -gt 0)
      {
          $searchStatus = "Failed Sources"
      }
      $searchStats = New-Object PSObject
      Add-Member -InputObject $searchStats -MemberType NoteProperty -Name Name -Value $search.Name
      Add-Member -InputObject $searchStats -MemberType NoteProperty -Name ContentMatchQuery -Value $search.ContentMatchQuery
      Add-Member -InputObject $searchStats -MemberType NoteProperty -Name Status -Value $searchStatus
      Add-Member -InputObject $searchStats -MemberType NoteProperty -Name Items -Value $search.Items
      Add-Member -InputObject $searchStats -MemberType NoteProperty -Name "Size" -Value $search.Size
      Add-Member -InputObject $searchStats -MemberType NoteProperty -Name "Size(MB)" -Value $sizeMB
      $allSearchStats += $searchStats
  }
  # Calculate the totals
  $allItems = ($allSearchStats | Measure-Object Items -Sum).Sum
  # Convert the total size to MB and round to the nearst 100th
  $allSize = ($allSearchStats | Measure-Object 'Size' -Sum).Sum
  $allSizeMB = [System.Math]::Round($allSize  / 1MB, 2)
  # Get the total successful searches and total of all searches
  $allSuccessCount = ($allSearchStats |?{$_.Status -eq "Completed"}).Count
  $allCount = $allSearchStats.Count
  $allStatus = [string]$allSuccessCount + " of " + [string]$allCount
  # Totals Row
  $totalSearchStats = New-Object PSObject
  Add-Member -InputObject $totalSearchStats -MemberType NoteProperty -Name Name -Value "Total"
  Add-Member -InputObject $totalSearchStats -MemberType NoteProperty -Name Status -Value $allStatus
  Add-Member -InputObject $totalSearchStats -MemberType NoteProperty -Name Items -Value $allItems
  Add-Member -InputObject $totalSearchStats -MemberType NoteProperty -Name "Size(MB)" -Value $allSizeMB
  $allSearchStats += $totalSearchStats
  # Just get the columns we're interested in showing
  $allSearchStatsPrime = $allSearchStats | Select-Object Name, Status, Items, "Size(MB)", ContentMatchQuery
  # Print the results to the screen
  $allSearchStatsPrime |ft -AutoSize -Wrap
  # Save the results to a CSV file
  if ($outputFile)
  {
      $allSearchStatsPrime | Export-Csv -Path $outputFile -NoTypeInformation
  }
  ```

2. En Windows PowerShell, vaya a la carpeta donde guardó el script en el paso anterior y, a continuación, ejecute el script; Por ejemplo:
    
    ```
    .\SearchReport.ps1
    ```

3. En el símbolo del sistema de **Identificador de grupo de búsqueda** , escriba un nombre de grupo de búsqueda y, a continuación, presione **ENTRAR**; Por ejemplo `ContosoCase`. Recuerde que este nombre distingue entre mayúsculas y minúsculas, por lo que tendrá que volver a la misma manera que hizo cuando ejecutó la secuencia de comandos en el paso 3.
    
4. En la **ruta de acceso para guardar el informe a un archivo CSV (dejar en blanco para mostrar el informe) del archivo** símbolo del sistema, escriba un nombre de archivo de la ruta de acceso de nombre de archivo completo (incluida la extensión de archivo .csv) si desea guardar el informe a un archivo CSV. nombre del archivo CSV, incluida la extensión de archivo .csv. Por ejemplo, podría escribir `ContosoCaseReport.csv` guardarlo en el directorio actual o se podría escribir `C:\Users\admin\OneDrive for Business\ContosoCase\ContosoCaseReport.csv` para guardarlo en una carpeta diferente. También puede dejar el símbolo del sistema en blanco para mostrar el informe, pero no se guarde en un archivo. 
    
5. Presione **ENTRAR**.
    
    La secuencia de comandos muestra el progreso de la creación y ejecución de las búsquedas. Una vez finalizada la secuencia de comandos, se muestra el informe. 
    
    ![Ejecutar el informe de búsqueda para mostrar las estimaciones para el grupo de búsqueda](media/3b5f2595-71d5-4a14-9214-fad156c981f8.png)
  
> [!NOTE]
> Si se especifica el mismo buzón de correo o sitio como una ubicación de contenido en más de una búsqueda en un grupo de búsqueda, la estimación total de resultados en el informe (para el número de elementos y el tamaño total) es posible que incluyan los resultados para los mismos elementos. Esto es debido a que el mismo mensaje de correo electrónico o el documento se contará más de una vez si coincide con la consulta para búsquedas diferentes en el grupo de búsqueda. 
  
## <a name="step-5-run-the-script-to-delete-the-searches"></a>Paso 5: Ejecutar la secuencia de comandos para eliminar las búsquedas

Debido a que puede estar creando una gran cantidad de búsquedas, este último script justo facilita eliminar rápidamente las búsquedas que creó en el paso 3. Al igual que las otras secuencias de comandos, éste también se le pedirá el identificador de grupo de búsqueda. Al ejecutar este script, se eliminarán todas las búsquedas con el identificador de grupo de búsqueda en el nombre de búsqueda. 
  
1. Guarde el siguiente texto en un archivo de secuencia de comandos de Windows PowerShell mediante el uso de un sufijo de nombre de archivo de. ps1; Por ejemplo, `DeleteSearches.ps1`. Guarde el archivo en la misma carpeta donde guardó los archivos de otros.
    
  ```
  # Delete all searches in a search group
  $searchGroup = Read-Host 'Search Group ID'
  Get-ComplianceSearch |
      ForEach-Object{
      # If the name matches the search group name pattern (case sensitive), delete the search
      if ($_.Name -cmatch $searchGroup + "_\d+")
      {
          Write-Host "Deleting search: " $_.Name
          Remove-ComplianceSearch $_.Name -Confirm:$false
      }
  }
  ```

2. En Windows PowerShell, vaya a la carpeta donde guardó el script en el paso anterior y, a continuación, ejecute el script; Por ejemplo:
    
    ```
    .\DeleteSearches.ps1
    ```

3. En el símbolo del sistema de **Identificador de grupo de búsqueda** , escriba un nombre de grupo de búsqueda para las búsquedas que desea eliminar y, a continuación, presione **ENTRAR**; Por ejemplo, `ContosoCase`. Recuerde que este nombre distingue entre mayúsculas y minúsculas, por lo que tendrá que volver a la misma manera que hizo cuando ejecutó la secuencia de comandos en el paso 3.
    
    La secuencia de comandos muestra el nombre de cada búsqueda que se elimina.
    
    ![Ejecutar la secuencia de comandos para eliminar las búsquedas en el grupo de búsqueda](media/9d97b9d6-a539-4d9b-a4e4-e99989144ec7.png)
