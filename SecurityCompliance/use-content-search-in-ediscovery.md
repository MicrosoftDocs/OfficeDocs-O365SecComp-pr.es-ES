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
# <a name="use-content-search-in-your-ediscovery-workflow"></a>Usar Búsqueda de contenido en el flujo de trabajo de eDiscovery

La característica de búsqueda de contenido de la seguridad de Office 365 &amp; centro de cumplimiento le permite buscar todos los buzones de la organización. A diferencia de exhibición de documentos electrónicos en contexto en Exchange Online (que se pueden buscar hasta 10.000 buzones de correo), no hay ningún límite para el número de buzones de correo de destino en una sola búsqueda. Para los escenarios que requieren que se va a realizar búsquedas de toda la organización, puede usar la búsqueda de contenido para buscar todos los buzones. A continuación, puede usar las características de flujo de trabajo de exhibición de documentos electrónicos en contexto para llevar a cabo otras tareas relacionadas con la exhibición de documentos electrónicos, como los buzones de correo puestas en espera y los resultados de búsqueda de exportación. Por ejemplo, supongamos que tiene que buscar todos los buzones de correo para identificar a Custodios específicos que responden a un caso legal. Puede usar la búsqueda de contenido en la seguridad &amp; centro de cumplimiento para buscar todos los buzones de la organización para identificarlos que responden a las mayúsculas y minúsculas. A continuación, puede usar esa lista de buzones de correo de custodia como los buzones de origen para una búsqueda de exhibición de documentos electrónicos en contexto en Exchange Online. Uso de exhibición de documentos electrónicos también permite colocar una suspensión en los buzones de origen, copiar los resultados de búsqueda en un buzón de detección y exportar los resultados de búsqueda.
  
En este tema se incluye una secuencia de comandos que puede ejecutar para crear una búsqueda de exhibición de documentos electrónicos en contexto en Exchange Online mediante el uso de la lista de buzones de origen y la consulta de búsqueda de una búsqueda creada en la seguridad &amp; centro de cumplimiento. Aquí es una descripción general del proceso:
  
[Paso 1: Crear una Búsqueda de contenido para todos los buzones de la organización](#step-1-create-a-content-search-to-search-all-mailboxes-in-your-organization)

[Paso 2: Conectarse a la seguridad &amp; centro de cumplimiento y Exchange Online en una sola sesión de PowerShell remota](#step-2-connect-to-the-security-amp-compliance-center-and-exchange-online-in-a-single-remote-powershell-session)
  
[Paso 3: Ejecutar el script para crear una búsqueda de eDiscovery local a partir de la búsqueda de contenido](#step-3-run-the-script-to-create-an-in-place-ediscovery-search-from-the-content-search)

[Paso 4: Iniciar la búsqueda de exhibición de documentos electrónicos local](#step-4-start-the-in-place-ediscovery-search)

## <a name="step-1-create-a-content-search-to-search-all-mailboxes-in-your-organization"></a>Paso 1: Crear una Búsqueda de contenido para todos los buzones de la organización

El primer paso consiste en usar la seguridad &amp; centro de cumplimiento (o seguridad y cumplimiento centro de PowerShell) para crear una búsqueda de contenido que busca en todos los buzones de la organización. No hay ningún límite para el número de buzones de correo para una sola búsqueda de contenido. Especificar una consulta de palabra clave adecuada (o una consulta para los tipos de información confidencial) para que la búsqueda devuelve sólo los buzones de origen que son relevantes para la investigación. Si es necesario, refinar la consulta de búsqueda para restringir el ámbito de los resultados de búsqueda y los buzones de origen que se devuelven.
  
> [!NOTE]
> Si la búsqueda de contenido de origen no devuelve ningún resultado, no se creará un eDiscovery local al ejecutar el script en el paso 3. Revise la consulta de búsqueda y, después, vuelva a ejecutar la búsqueda de contenido para mostrar los resultados de la búsqueda. 
  
### <a name="use-the-security-amp-compliance-center-to-search-all-mailboxes"></a>Usar la seguridad &amp; centro de cumplimiento para buscar todos los buzones

1. [Vaya a la seguridad de Office 365 &amp; centro de cumplimiento](go-to-the-securitycompliance-center.md). 
    
2. Haga clic en **búsqueda &amp; investigación**, haga clic en **búsqueda de contenido**y, a continuación, haga clic en **nuevo** ![icono Agregar](media/O365-MDM-CreatePolicy-AddIcon.gif).
    
3. En la página **Nueva búsqueda**, escriba un nombre para la búsqueda de contenido. 
    
4. En **¿Dónde desea buscar?**, haga clic en **Buscar en todos los buzones** y, a continuación, haga clic en **Siguiente**.
    
5. En el cuadro en **¿Qué desea nos para buscar?**, escriba una consulta de búsqueda en el cuadro. Puede especificar las palabras clave, mensaje propiedades como envían y reciben fechas, o las propiedades de documento, como los nombres de archivo o la fecha en que se modificó por última vez un documento. Puede usar una de las consultas más complejas que utilizan un operador booleano, como AND y OR, no o NEAR o también puede buscar información confidencial (como números de la seguridad social) en los mensajes. Para obtener más información acerca de cómo crear consultas de búsqueda, vea [consultas de palabra clave para la búsqueda de contenido](keyword-queries-and-search-conditions.md).
    
6. Haga clic en **Búsqueda** para guardar la configuración de la búsqueda e iniciar la búsqueda. 
    
    Después de unos momentos, se muestra una estimación de los resultados de búsqueda en el panel de detalles. La estimación incluye el tamaño total y el número de elementos para los resultados de búsqueda. Una vez finalizada la búsqueda, puede obtener una vista previa de los resultados de búsqueda. Si es necesario, haga clic en **Actualizar**![icono de actualización](media/O365-MDM-Policy-RefreshIcon.gif) para actualizar la información en el panel de detalles. 
    
7.  Si es necesario, refine la consulta de búsqueda para restringir el alcance de los resultados de la búsqueda y, a continuación, reinicie la búsqueda. 
    
### <a name="use-security--compliance-center-powershell-to-search-all-mailboxes"></a>Usar PowerShell de centro de cumplimiento y seguridad para buscar en todos los buzones

También puede usar el cmdlet **New-ComplianceSearch** para buscar todos los buzones de la organización. El primer paso es [Conectar a Office 365 seguridad &amp; PowerShell de centro de cumplimiento de normas](https://go.microsoft.com/fwlink/p/?LinkID=627084).
  
Este es un ejemplo del uso de PowerShell para buscar todos los buzones de la organización. La consulta de búsqueda devuelve todos los mensajes enviados entre el 1 de enero de 2015 y el 30 de junio de 2015 y que contengan la frase "informe financiero" en la línea de asunto. El primer comando crea la búsqueda y el segundo comando ejecuta la búsqueda. 
  
```
New-ComplianceSearch -Name "Search All-Financial Report" -ExchangeLocation all -ContentMatchQuery 'sent>=01/01/2015 AND sent<=06/30/2015 AND subject:"financial report"'
```

```
Start-ComplianceSearch -Identity "Search All-Financial Report"
```

Para obtener más información, consulte [New-ComplianceSearch](https://go.microsoft.com/fwlink/p/?LinkId=517935).
  
### <a name="verify-the-number-of-source-mailboxes-in-the-content-search"></a>Comprobar el número de buzones de origen en la búsqueda de contenido

Una búsqueda de contenido devuelve un máximo de 1.000 buzones de correo de origen que contienen los resultados de búsqueda. Si hay más de 1.000 buzones de correo que contienen contenido que coincide con la consulta de búsqueda, sólo los buzones de correo superior 1.000 con los resultados de búsqueda mayoría se incluyen en la búsqueda de contenido que creó en el paso anterior. Por lo que si más de 1.000 buzones de correo contienen los resultados de búsqueda, algunos de esos buzones no se incluirán en la lista de buzones de origen copiado a la búsqueda de exhibición de documentos electrónicos en contexto nuevo creada en el paso 3. 
  
Para ayudarle a crear una búsqueda de contenido con no más de buzones de origen 1.000, siga estos pasos para ejecutar un script que muestra el número de buzones de origen (que contienen los resultados de búsqueda) devuelto por la búsqueda de contenido que creó en el paso 1. 
  
1. Guarde el siguiente texto en un archivo de secuencia de comandos de PowerShell mediante el uso de un sufijo de nombre de archivo de. ps1. Por ejemplo, se podría guardar en un archivo denominado `SourceMailboxes.ps1`.
    
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

2. En seguridad y cumplimiento de centro de PowerShell, vaya a la carpeta donde se encuentra la secuencia de comandos que creó en el paso anterior y, a continuación, ejecute el script; Por ejemplo:
    
    ```
    .\SourceMailboxes.ps1
    ```

3. Cuando el script se lo pida, escriba el nombre de la búsqueda de contenido que creó en el paso 1.
    
    El script muestra el número de buzones de origen que contienen los resultados de la búsqueda.
    
Si hay más de 1.000 buzones de correo de origen, pruebe a crear las búsquedas de contenido de dos (o más). Por ejemplo, buscar la mitad de los buzones de correo de su organización en una búsqueda de contenido y la otra mitad en búsqueda de contenido de otra. También puede cambiar los criterios de búsqueda para reducir el número de buzones que contienen resultados de búsqueda. Por ejemplo, podría incluir un intervalo de fechas o perfeccionar la consulta de palabra clave.
  
## <a name="step-2-connect-to-the-security-amp-compliance-center-and-exchange-online-in-a-single-remote-powershell-session"></a>Paso 2: Conectarse a la seguridad &amp; centro de cumplimiento y Exchange Online en una sola sesión de PowerShell remota

El siguiente paso es conectar Windows PowerShell para ambos la seguridad &amp; centro de cumplimiento y a la organización de Exchange Online. Esto es necesario porque la secuencia de comandos que se ejecutan en el paso 3 requiere acceso a los cmdlets de búsqueda de contenido en la seguridad &amp; centro de cumplimiento y los cmdlets de exhibición de documentos electrónicos en contexto en Exchange Online.
  
1. Guarde el siguiente texto en un archivo de secuencia de comandos de Windows PowerShell mediante el uso de un sufijo de nombre de archivo de. ps1. Por ejemplo, se podría guardar en un archivo denominado `ConnectEXO-CC.ps1`.
    
    ```
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.outlook.com/powershell-liveid -Credential $UserCredential -Authentication Basic -AllowRedirection
    Import-PSSession $Session -DisableNameChecking
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Credential $UserCredential -Authentication Basic -AllowRedirection
    Import-PSSession $Session -AllowClobber -DisableNameChecking
    $Host.UI.RawUI.WindowTitle = $UserCredential.UserName + " (Exchange Online + Compliance Center)"
    ```

2. En el equipo local, abra Windows PowerShell, vaya a la carpeta donde se encuentra la secuencia de comandos que creó en el paso anterior y, a continuación, ejecute el script; Por ejemplo:
    
    ```
    .\ConnectEXO-CC.ps1
    ```

¿Cómo sé si ha funcionado? Después de ejecutar el script, cmdlets de la seguridad &amp; centro de cumplimiento y Exchange Online se importan en la sesión de PowerShell local. Si no recibe algún error, conectado correctamente. Es una prueba rápida ejecutar una seguridad &amp; centro de cumplimiento cmdlet — por ejemplo, **Install-UnifiedCompliancePrerequisite** — y un cmdlet de Exchange Online, por ejemplo, **Get-Mailbox**. 
  
## <a name="step-3-run-the-script-to-create-an-in-place-ediscovery-search-from-the-content-search"></a>Paso 3: Ejecutar el script para crear una búsqueda de eDiscovery local a partir de la búsqueda de contenido

Después de crear la sesión de PowerShell dual en el paso 2, el siguiente paso es ejecutar un script que se va a convertir una búsqueda de contenido existente a una búsqueda de exhibición de documentos electrónicos en contexto. Aquí es lo que hace la secuencia de comandos:
  
- Le pide el nombre de la búsqueda de contenido que quiere convertir.
    
- Comprueba que se ha completado la búsqueda de contenido. Si la búsqueda de contenido no devuelve ningún resultado, no se creará el eDiscovery local.
    
- Guarda una lista de los buzones de origen de la búsqueda de contenido que contienen los resultados de la búsqueda en una variable.
    
- Crea una nueva búsqueda de exhibición de documentos electrónicos local con las propiedades siguientes. Tenga en cuenta que la búsqueda nueva no se inicia. Empezará en el paso 4.
    
  - **Nombre** : el nombre de la nueva búsqueda usa este formato: \<nombre de búsqueda de contenido\>_MBSearch1. Si se vuelva a ejecuta la secuencia de comandos y utilizar el mismo origen de búsqueda de contenido, la búsqueda se denominará \<nombre de búsqueda de contenido\>_MBSearch2.
    
  - **Buzones de origen** - todos los buzones de la búsqueda de contenido que contienen resultados de búsqueda. 
    
  - **Consulta de búsqueda** - la nueva búsqueda usa la consulta de búsqueda de la búsqueda de contenido. Si la búsqueda de contenido incluye todo el contenido (donde la consulta de búsqueda está en blanco) la nueva búsqueda también tendrán una consulta de búsqueda en blanco e incluirá todo el contenido que se encuentra en los buzones de origen. 
    
  - **Estimación de búsqueda solo** - la nueva búsqueda está marcado como una búsqueda de estimación. No copia los resultados de búsqueda a un buzón de detección después de iniciarlo. 
    
1. Guarde el siguiente texto en un archivo de secuencia de comandos de Windows PowerShell mediante el uso de un sufijo de nombre de archivo de ps1. Por ejemplo, se podría guardar en un archivo denominado `CreateMBSearchFromComplianceSearch.ps1`.
    
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

2. En la sesión de Windows PowerShell que creó en el paso 2, vaya a la carpeta donde se encuentra la secuencia de comandos que creó en el paso anterior y, a continuación, ejecute el script; Por ejemplo:
    
    ```
    .\CreateMBSearchFromComplianceSearch.ps1
    ```

3. Cuando se le solicite la secuencia de comandos, escriba el nombre de la búsqueda de contenido que va a convertir a una búsqueda de exhibición de documentos electrónicos local (por ejemplo, la búsqueda que creó en el paso 1) y, a continuación, presione **ENTRAR**.
    
    Si el script funciona, se crea una nueva búsqueda de exhibición de documentos electrónicos local con un estado **NotStarted**. Ejecute el comando  `Get-MailboxSearch <Name of Content Search>_MBSearch1 | FL` para mostrar las propiedades de la nueva búsqueda. 
  
## <a name="step-4-start-the-in-place-ediscovery-search"></a>Paso 4: Iniciar la búsqueda de exhibición de documentos electrónicos local

El script que se ejecuta en el paso 3 crea una nueva búsqueda de exhibición de documentos electrónicos local, pero no la inicia. El siguiente paso es iniciar la búsqueda para obtener una estimación de los resultados de búsqueda.
  
1. En el centro de administración de Exchange (EAC), vaya a **administración de cumplimiento** \> **exhibición de documentos electrónicos en contexto &amp; suspensión**.
    
2. En la vista de lista, seleccione la búsqueda de exhibición de documentos electrónicos local que se creó en el paso 3.
    
3. Haga clic en **búsqueda** ![icono de búsqueda](media/5f6f9463-50e9-460b-8738-b67e759c2efc.gif) \> **los resultados de búsqueda de estimación** para iniciar la búsqueda y devolver una estimación del tamaño total y el número de elementos devueltos por la búsqueda. 
    
    Las estimaciones se muestran en el panel de detalles. Haga clic en **Actualizar** ![icono de actualización](media/O365-MDM-Policy-RefreshIcon.gif) para actualizar la información que se muestra en el panel de detalles. 
    
4. Para obtener una vista previa de los resultados una vez completada la búsqueda, haga clic en **Vista previa de los resultados de búsqueda** en el panel de detalles.
  
## <a name="next-steps-after-creating-and-running-the-in-place-ediscovery-search"></a>Pasos siguientes después de crear y ejecutar la búsqueda de exhibición de documentos electrónicos local

Después de crear e iniciar la búsqueda de exhibición de documentos electrónicos local que el script ha creado en el paso 3, puede usar el flujo de trabajo normal de la exhibición de documentos electrónicos local para realizar distintas acciones de exhibición de documentos electrónicos en los resultados de la búsqueda.
  
### <a name="create-an-in-place-hold"></a>Crear una Conservación local

1. En el EAC, vaya a **administración de cumplimiento** \> **exhibición de documentos electrónicos en contexto &amp; suspensión**.
    
2. En la vista de lista, seleccione la búsqueda de exhibición de documentos electrónicos local que creó en el paso 3 y, a continuación, haga clic en **Editar** ![icono Editar](media/O365_MDM_CreatePolicy_EditIcon.gif).
    
3. En la página **Conservación local**, active la casilla **Pausar el contenido que coincida con la consulta de búsqueda en los buzones seleccionados** y después seleccione una de las siguientes opciones: 
    
  - **Espera indefinidamente** - elija esta opción para colocar los elementos devueltos por la búsqueda en una espera indefinida. Se conservarán los elementos en espera hasta que se quite la búsqueda en el buzón de correo o quita la búsqueda. 
    
  - **Especificar número de días para retener elementos con respecto a su fecha de recepción** : elija esta opción para retener elementos durante un período específico. La duración se calcula a partir la fecha de un elemento de buzón de correo se ha recibido o creado. 
    
4. Haga clic en **Guardar** para crear la conservación local y reiniciar la búsqueda. 
    
[Return to top](use-content-search-in-ediscovery.md#top)
  
### <a name="copy-the-search-results"></a>Copiar los resultados de la búsqueda

1. En el EAC, vaya a **administración de cumplimiento** \> **exhibición de documentos electrónicos en contexto &amp; suspensión**.
    
2. En la vista de lista, seleccione la búsqueda de exhibición de documentos electrónicos local que ha creado en el paso 3.
    
3. Haga clic en **búsqueda** ![icono de búsqueda](media/5f6f9463-50e9-460b-8738-b67e759c2efc.gif)y, a continuación, haga clic en **copiar los resultados de búsqueda** de la lista desplegable. 
    
4. En **Copiar resultados de búsqueda**, seleccione entre las siguientes opciones:
    
    - **Incluir elementos buscar** - Active esta casilla de verificación para incluir los elementos de buzón de correo que no se ha podido buscar (por ejemplo, los mensajes con datos adjuntos de tipos de archivo que se han podido indizar mediante la búsqueda de Exchange). 
    
    - **Habilitar la desduplicación** - Active esta casilla de verificación para excluir los mensajes duplicados. Una sola instancia de un mensaje se copiará en el buzón de detección. 
    
    - **Habilitar el registro completo** - Active esta casilla de verificación para incluir un registro completo en los resultados de búsqueda. 
    
    - **Envíeme un correo electrónico cuando se complete la copia** - Active esta casilla de verificación para recibir una notificación de correo electrónico cuando se complete la búsqueda. 
    
    - **Copiar los resultados a este buzón de correo de detección** - haga clic en **Examinar** para seleccionar el buzón de detección donde desea que los resultados de búsqueda copiado en. 
    
5. Haga clic en **Copiar** para iniciar el proceso de copia de los resultados de la búsqueda en el buzón de correo de detección especificado. 
    
6. Haga clic en **Actualizar** ![icono de actualización](media/O365-MDM-Policy-RefreshIcon.gif) para actualizar la información sobre el estado de copia que se muestra en el panel de detalles. 
    
7. Una vez que la copia esté completa, haga clic en **Abrir** para abrir el buzón de correo de detección y ver los resultados de la búsqueda. 
  
### <a name="export-the-search-results"></a>Exportar los resultados de la búsqueda

1. En el EAC, vaya a **administración de cumplimiento** \> **exhibición de documentos electrónicos en contexto &amp; suspensión**.
    
2. En la vista de lista, seleccione la búsqueda de exhibición de documentos electrónicos local que se creó en el paso 3 y luego haga clic en **Exportar a un archivo PST**.
    
3. En la ventana de la **herramienta de exportación de PST de exhibición de documentos electrónicos**: 
    
    - Haga clic en **Examinar** para especificar la ubicación donde quiere descargar el archivo PST. 
    
    - Haga clic en la casilla **Habilitar desduplicación** para excluir los mensajes duplicados. Solo se incluirá una instancia de cada mensaje en el archivo PST. 
    
    - Haga clic en la casilla **Incluir elementos no aptos para la búsqueda** si quiere incluir los elementos del buzón que no pudieron buscar (por ejemplo, los mensajes con datos adjuntos de tipos de archivo que Exchange Search no pudo indizar). Los elementos no aptos para la búsqueda se exportan a un archivo PST independiente. 
    
4. Haga clic en **Inicio** para exportar los resultados de búsqueda a un archivo PST. 
    
    Se mostrará una ventana con información de estado sobre el proceso de exportación.
