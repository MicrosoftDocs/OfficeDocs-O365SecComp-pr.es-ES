---
title: Usar Búsqueda de contenido en el flujo de trabajo de eDiscovery
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 12/30/2016
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 55f31488-288a-473a-9b9e-831a11e3711a
description: 'Use un script de PowerShell para crear una búsqueda de exhibición de documentos electrónicos local en Exchange online en función de una búsqueda creada en el centro de seguridad & cumplimiento. '
ms.openlocfilehash: f3d5eb76dfa91334bccae42e0ddb66a71f739a6f
ms.sourcegitcommit: 044003455eb36071806c9f008ac631d54c64dde6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/24/2019
ms.locfileid: "35199827"
---
# <a name="use-content-search-in-your-ediscovery-workflow"></a>Usar Búsqueda de contenido en el flujo de trabajo de eDiscovery

La característica de búsqueda de contenido en el centro de seguridad & cumplimiento permite buscar en todos los buzones de la organización. A diferencia de la exhibición de documentos electrónicos local en Exchange Online (donde puede buscar hasta 10.000 buzones), no hay límites para el número de buzones de destino en una sola búsqueda. En los escenarios en los que necesite realizar búsquedas en toda la organización, puede usar Búsqueda de contenido para buscar en todos los buzones. A continuación, puede usar las características de flujo de trabajo de exhibición de documentos electrónicos local para realizar otras tareas relacionadas con la exhibición de documentos electrónicos, como colocar buzones en suspensión y exportar resultados de la búsqueda. Por ejemplo, supongamos que tiene que buscar en todos los buzones para identificar administradores específicos que responden a un caso jurídico. Puede usar la búsqueda de contenido en el centro de seguridad & cumplimiento para buscar en todos los buzones de la organización para identificar los que responden al caso. A continuación, puede usar esa lista de buzones de correo de custodios como buzones de origen para una búsqueda de exhibición de documentos electrónicos local en Exchange Online. El uso de la exhibición de documentos electrónicos local también permite poner en suspensión dichos buzones de origen, copiar los resultados de la búsqueda en un buzón de correo de detección y exportar los resultados de la búsqueda.
  
En este tema se incluye un script que puede ejecutar para crear una búsqueda de exhibición de documentos electrónicos local en Exchange Online usando la lista de buzones de origen y la consulta de búsqueda de una búsqueda creada en el centro de seguridad & cumplimiento. A continuación encontrará una descripción general del proceso:
  
[Paso 1: Crear una Búsqueda de contenido para todos los buzones de la organización](#step-1-create-a-content-search-to-search-all-mailboxes-in-your-organization)

[Paso 2: conectarse al centro de \& seguridad y cumplimiento y a Exchange online en una única sesión de PowerShell en remoto](#step-2-connect-to-the-security--compliance-center-and-exchange-online-in-a-single-remote-powershell-session)
  
[Paso 3: Ejecutar el script para crear una búsqueda de eDiscovery local a partir de la búsqueda de contenido](#step-3-run-the-script-to-create-an-in-place-ediscovery-search-from-the-content-search)

[Step 4: Start the In-Place eDiscovery search](#step-4-start-the-in-place-ediscovery-search)

## <a name="step-1-create-a-content-search-to-search-all-mailboxes-in-your-organization"></a>Paso 1: Crear una Búsqueda de contenido para todos los buzones de la organización

El primer paso consiste en usar el centro de seguridad & cumplimiento (o PowerShell del centro de seguridad & cumplimiento) para crear una búsqueda de contenido que busque en todos los buzones de la organización. No existe un límite para el número de buzones de una búsqueda de contenido. Especifique una consulta de palabras clave adecuada (o una consulta de los tipos de información confidencial) para que la búsqueda devuelva solo los buzones de origen relevantes para la investigación. Si es necesario, restrinja la consulta de búsqueda para limitar el ámbito de los resultados de la búsqueda y los buzones de origen devueltos.
  
> [!NOTE]
> Si la búsqueda de contenido de origen no devuelve ningún resultado, no se creará un eDiscovery local al ejecutar el script en el paso 3. Revise la consulta de búsqueda y, después, vuelva a ejecutar la búsqueda de contenido para mostrar los resultados de la búsqueda. 
  
### <a name="use-the-security--compliance-center-to-search-all-mailboxes"></a>Usar el Centro de seguridad y cumplimiento para buscar en todos los buzones

1. [Vaya al centro de seguridad & cumplimiento](go-to-the-securitycompliance-center.md). 
    
2.  > Haga **** clic en buscar**contenido**búsqueda y, a continuación, haga clic en **nuevo** ![icono](media/O365-MDM-CreatePolicy-AddIcon.gif)agregar nuevo.
    
3. En la página **Nueva búsqueda**, escriba un nombre para la búsqueda de contenido. 
    
4. En **¿Dónde desea buscar?**, haga clic en **Buscar en todos los buzones** y, a continuación, haga clic en **Siguiente**.
    
5. En **¿Qué desea buscar?**, escriba una consulta de búsqueda en el cuadro. Puede especificar palabras clave, propiedades del mensaje como la fecha de envío y de recepción, o propiedades del documento como nombres de archivo o la fecha de la última modificación de un documento. Puede usar consultas más complejas que usen un operador booleano, como AND, OR, NOT o NEAR, o también puede buscar información confidencial (por ejemplo, los números de la seguridad social) en los mensajes. Para obtener más información acerca de cómo crear consultas de búsqueda, consulte [Keyword queries for Content Search](keyword-queries-and-search-conditions.md).
    
6. Haga clic en **Búsqueda** para guardar la configuración de la búsqueda e iniciar la búsqueda. 
    
    Después de un rato, una estimación de los resultados de la búsqueda que se muestran en el panel de detalles. La estimación incluye el tamaño total y el número de elementos de los resultados de la búsqueda. Una vez finalizada la búsqueda, puede obtener una vista previa de los resultados de la búsqueda. Si es necesario, ****![haga clic en](media/O365-MDM-Policy-RefreshIcon.gif) actualizar icono de actualización para actualizar la información en el panel de detalles. 
    
7.  Si es necesario, refine la consulta de búsqueda para restringir el alcance de los resultados de la búsqueda y, a continuación, reinicie la búsqueda. 
    
### <a name="use-security--compliance-center-powershell-to-search-all-mailboxes"></a>Usar el PowerShell del centro de cumplimiento de & de seguridad para buscar en todos los buzones

También puede usar el cmdlet **New-ComplianceSearch** para buscar en todos los buzones de la organización. El primer paso consiste en [conectar con el PowerShell del centro de seguridad & cumplimiento](https://go.microsoft.com/fwlink/p/?LinkID=627084).
  
Este es un ejemplo del uso de PowerShell para buscar en todos los buzones de la organización. La consulta de búsqueda devuelve todos los mensajes enviados entre el 1 de enero de 2015 y el 30 de junio de 2015 y que contienen la frase "informe financiero" en la línea del asunto. El primer comando crea la búsqueda y el segundo comando la ejecuta. 
  
```
New-ComplianceSearch -Name "Search All-Financial Report" -ExchangeLocation all -ContentMatchQuery 'sent>=01/01/2015 AND sent<=06/30/2015 AND subject:"financial report"'
```

```
Start-ComplianceSearch -Identity "Search All-Financial Report"
```

Para obtener más información, consulte [New-ComplianceSearch](https://go.microsoft.com/fwlink/p/?LinkId=517935).
  
### <a name="verify-the-number-of-source-mailboxes-in-the-content-search"></a>Comprobar el número de buzones de origen en la búsqueda de contenido

Una búsqueda de contenido devuelve un máximo de 1.000 buzones de origen que contienen resultados de búsqueda. Si hay más de 1.000 buzones de correo que contienen contenido que coincide con la consulta de búsqueda, solo los primeros 1.000 buzones con mayor cantidad de resultados de búsqueda se incluyen en la búsqueda de contenido que creó en el paso anterior. Por lo tanto, si más de 1.000 buzones de correo contienen resultados de búsqueda, algunos de estos buzones no se incluirán en la lista de buzones de origen que se han copiado a la nueva búsqueda de exhibición de documentos electrónicos local creada en el paso 3. 
  
Para ayudarle a crear una búsqueda de contenido con un máximo de 1.000 buzones de correo de origen, siga estos pasos para ejecutar un script que muestre el número de buzones de origen (que contienen los resultados de la búsqueda) devueltos por la búsqueda de contenido que creó en el paso 1. 
  
1. Guarde el siguiente texto en un archivo de script de PowerShell con un sufijo de nombre de archivo de. ps1. Por ejemplo, puede guardarlo en un archivo denominado `SourceMailboxes.ps1`.
    
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

2. En Security & PowerShell del centro de cumplimiento, vaya a la carpeta donde se encuentre el script creado en el paso anterior y ejecute el script; por ejemplo:
    
    ```
    .\SourceMailboxes.ps1
    ```

3. Cuando el script se lo pida, escriba el nombre de la búsqueda de contenido que creó en el paso 1.
    
    El script muestra el número de buzones de origen que contienen los resultados de la búsqueda.
    
Si hay más de 1.000 buzones de origen, intente crear dos (o más) búsquedas de contenido. Por ejemplo, busque en la mitad de los buzones de la organización con una búsqueda de contenido y en la otra mitad con otra búsqueda de contenido. También puede cambiar los criterios de búsqueda para reducir el número de buzones que contengan los resultados de la búsqueda. Por ejemplo, puede incluir un intervalo de fechas o refinar la consulta de palabra clave.
  
## <a name="step-2-connect-to-the-security--compliance-center-and-exchange-online-in-a-single-remote-powershell-session"></a>Paso 2: conectarse al centro de \& seguridad y cumplimiento y a Exchange online en una única sesión de PowerShell en remoto

El paso siguiente es conectar Windows PowerShell al centro de seguridad & cumplimiento y a la organización de Exchange Online. Esto es necesario porque el script que ejecutó en el paso 3 requiere acceso a los cmdlets de búsqueda de contenido en el centro de seguridad & cumplimiento y los cmdlets de exhibición de documentos electrónicos local en Exchange Online.
  
1. Guarde el siguiente texto en un archivo de script de Windows PowerShell mediante un sufijo de nombre de archivo de .ps1. Por ejemplo, puede guardarlo en un archivo denominado `ConnectEXO-CC.ps1`.
    
    ```
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.outlook.com/powershell-liveid -Credential $UserCredential -Authentication Basic -AllowRedirection
    Import-PSSession $Session -DisableNameChecking
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Credential $UserCredential -Authentication Basic -AllowRedirection
    Import-PSSession $Session -AllowClobber -DisableNameChecking
    $Host.UI.RawUI.WindowTitle = $UserCredential.UserName + " (Exchange Online + Compliance Center)"
    ```

2. En el equipo local, abra Windows PowerShell, vaya a la carpeta en la que se encuentra el script creado en el paso anterior y, a continuación, ejecute el script. por ejemplo:
    
    ```
    .\ConnectEXO-CC.ps1
    ```

¿Cómo se sabe si se ha completado correctamente? Después de ejecutar el script, los cmdlets del centro de seguridad & cumplimiento y Exchange Online se importan a la sesión local de PowerShell. Si no se muestra ningún error, la conexión se habrá establecido correctamente. Una prueba rápida es ejecutar un cmdlet del centro de cumplimiento de & de seguridad (por ejemplo, **install-UnifiedCompliancePrerequisite** ) y un cmdlet de Exchange Online, como **Get-Mailbox**. 
  
## <a name="step-3-run-the-script-to-create-an-in-place-ediscovery-search-from-the-content-search"></a>Paso 3: Ejecutar el script para crear una búsqueda de eDiscovery local a partir de la búsqueda de contenido

Después de crear la sesión de PowerShell dual en el paso 2, el siguiente paso es ejecutar un script que convertirá una búsqueda de contenido existente en una búsqueda de exhibición de documentos electrónicos local. Esto es lo que hace el script:
  
- Le pide el nombre de la búsqueda de contenido que quiere convertir.
    
- Comprueba que se ha completado la búsqueda de contenido. Si la búsqueda de contenido no devuelve ningún resultado, no se creará el eDiscovery local.
    
- Guarda una lista de los buzones de origen de la búsqueda de contenido que contienen los resultados de la búsqueda en una variable.
    
- Crea una nueva búsqueda de exhibición de documentos electrónicos local con las propiedades siguientes. Tenga en cuenta que la búsqueda nueva no se inicia. Empezará en el paso 4.
    
  - **Nombre** : el nombre de la nueva búsqueda usa este formato: \<nombre de la búsqueda\>de contenido _MBSearch1. Si vuelve a ejecutar el script y usa la misma búsqueda de contenido de origen, la búsqueda se \<denominará nombre de\>búsqueda de contenido _MBSearch2.
    
  - **Buzones de origen** : todos los buzones de la búsqueda de contenido que contienen los resultados de la búsqueda. 
    
  - **Consulta de búsqueda** : la nueva búsqueda usa la consulta de búsqueda de la búsqueda de contenido. Si en la búsqueda de contenido se incluye todo el contenido (cuando la consulta de búsqueda está en blanco), la nueva búsqueda también tendrá una consulta de búsqueda en blanco donde se incluirá todo el contenido encontrado en los buzones de origen. 
    
  - **Estimar solo la búsqueda** : la nueva búsqueda se marca como una búsqueda de solo estimación. No se copiarán los resultados de búsqueda a un buzón de detección una vez que se haya iniciado. 
    
1. Guarde el siguiente texto en un archivo de script de Windows PowerShell mediante un sufijo de nombre de archivo de ps1. Por ejemplo, puede guardarlo en un archivo denominado `CreateMBSearchFromComplianceSearch.ps1`.
    
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

2. En la sesión de Windows PowerShell que creó en el paso 2, vaya a la carpeta en la que se encuentra el script creado en el paso anterior y, a continuación, ejecute el script. por ejemplo:
    
    ```
    .\CreateMBSearchFromComplianceSearch.ps1
    ```

3. Cuando se lo pida el script, escriba el nombre de la búsqueda de contenido que desea repartir en una búsqueda de exhibición de documentos electrónicos local (por ejemplo, la búsqueda que creó en el paso 1) y, a continuación, presione **entrar**.
    
    Si el script funciona, se crea una nueva búsqueda de exhibición de documentos electrónicos local con un estado **NotStarted**. Ejecute el comando  `Get-MailboxSearch <Name of Content Search>_MBSearch1 | FL` para mostrar las propiedades de la nueva búsqueda. 
  
## <a name="step-4-start-the-in-place-ediscovery-search"></a>Paso 4: Iniciar la búsqueda de exhibición de documentos electrónicos local

El script que se ejecuta en el paso 3 crea una nueva búsqueda de exhibición de documentos electrónicos local, pero no la inicia. El siguiente paso es iniciar la búsqueda para obtener una estimación de los resultados de búsqueda.
  
1. In the Exchange admin center (EAC), go to **Compliance management** \> **In-Place eDiscovery &amp; Hold**.
    
2. En la vista de lista, seleccione la búsqueda de exhibición de documentos electrónicos local que se creó en el paso 3.
    
3. Haga **** ![clic en el](media/5f6f9463-50e9-460b-8738-b67e759c2efc.gif) \> icono búsqueda de búsqueda **estimar resultados de búsqueda** para iniciar la búsqueda y devolver una estimación del tamaño total y el número de elementos devueltos por la búsqueda. 
    
    Las estimaciones se muestran en el panel de detalles. Haga **** ![clic en el](media/O365-MDM-Policy-RefreshIcon.gif) icono Actualizar actualización para actualizar la información que se muestra en el panel de detalles. 
    
4. Para obtener una vista previa de los resultados una vez completada la búsqueda, haga clic en **Vista previa de los resultados de búsqueda** en el panel de detalles.
  
## <a name="next-steps-after-creating-and-running-the-in-place-ediscovery-search"></a>Pasos siguientes después de crear y ejecutar la búsqueda de exhibición de documentos electrónicos local

Después de crear e iniciar la búsqueda de exhibición de documentos electrónicos local que el script ha creado en el paso 3, puede usar el flujo de trabajo normal de la exhibición de documentos electrónicos local para realizar distintas acciones de exhibición de documentos electrónicos en los resultados de la búsqueda.
  
### <a name="create-an-in-place-hold"></a>Crear una Conservación local

1. In the EAC, go to **Compliance management** \> **In-Place eDiscovery &amp; Hold**.
    
2. En la vista de lista, seleccione la búsqueda de exhibición de documentos electrónicos local que creó en el paso 3 y, a continuación](media/O365-MDM-CreatePolicy-EditIcon.gif), haga clic en **Editar** ![icono de edición.
    
3. En la página **Conservación local**, active la casilla **Pausar el contenido que coincida con la consulta de búsqueda en los buzones seleccionados** y después seleccione una de las siguientes opciones: 
    
  - **Retener** indefinidamente: elija esta opción para poner los elementos devueltos por la búsqueda en una retención indefinida. Los elementos en espera se conservarán hasta que quite el buzón de correo de la búsqueda o la búsqueda. 
    
  - **Especificar el número de días que se conservarán los elementos relacionados con la fecha de recepción** : elija esta opción para retener elementos durante un período específico. La duración se calcula desde la fecha en que un elemento de buzón se recibe o se crea. 
    
4. Haga clic en **Guardar** para crear la conservación local y reiniciar la búsqueda. 
    
[Return to top](use-content-search-in-ediscovery.md#top)
  
### <a name="copy-the-search-results"></a>Copiar los resultados de la búsqueda

1. In the EAC, go to **Compliance management** \> **In-Place eDiscovery &amp; Hold**.
    
2. En la vista de lista, seleccione la búsqueda de exhibición de documentos electrónicos local que ha creado en el paso 3.
    
3. Haga clic en el](media/5f6f9463-50e9-460b-8738-b67e759c2efc.gif)icono Buscar búsqueda y, a continuación, haga clic en **copiar resultados de búsqueda** en la lista desplegable. **** ![ 
    
4. En **Copiar resultados de búsqueda**, seleccione entre las siguientes opciones:
    
    - **Incluir elementos** que no se pueden buscar: Active esta casilla para incluir elementos de buzones que no se pudieron buscar (por ejemplo, mensajes con datos adjuntos de tipos de archivo que la búsqueda de Exchange no pudo indexar). 
    
    - **Habilitación de** la desduplicación: Seleccione esta casilla para excluir los mensajes duplicados. Solo una instancia del mensaje se copiará en el buzón de correo de detección. 
    
    - **Habilitar registro completo** : Seleccione esta casilla para incluir un registro completo en los resultados de la búsqueda. 
    
    - **Enviarme un correo cuando se haya completado la copia** : Seleccione esta casilla para recibir una notificación por correo electrónico cuando la búsqueda se haya completado. 
    
    - **Copiar los resultados en este buzón de detección** : haga clic en **examinar** para seleccionar el buzón de correo de detección en el que desea copiar los resultados de la búsqueda. 
    
5. Haga clic en **Copiar** para iniciar el proceso de copia de los resultados de la búsqueda en el buzón de correo de detección especificado. 
    
6. Haga **** ![clic en actualizar](media/O365-MDM-Policy-RefreshIcon.gif) icono para actualizar la información sobre el estado de copia que se muestra en el panel de detalles. 
    
7. Una vez que la copia esté completa, haga clic en **Abrir** para abrir el buzón de correo de detección y ver los resultados de la búsqueda. 
  
### <a name="export-the-search-results"></a>Exportar los resultados de la búsqueda

1. In the EAC, go to **Compliance management** \> **In-Place eDiscovery &amp; Hold**.
    
2. En la vista de lista, seleccione la búsqueda de exhibición de documentos electrónicos local que se creó en el paso 3 y luego haga clic en **Exportar a un archivo PST**.
    
3. En la ventana de la **herramienta de exportación de PST de exhibición de documentos electrónicos**: 
    
    - Haga clic en **Examinar** para especificar la ubicación donde quiere descargar el archivo PST. 
    
    - Haga clic en la casilla **Habilitar desduplicación** para excluir los mensajes duplicados. Solo se incluirá una instancia de cada mensaje en el archivo PST. 
    
    - Haga clic en la casilla **Incluir elementos no aptos para la búsqueda** si quiere incluir los elementos del buzón que no pudieron buscar (por ejemplo, los mensajes con datos adjuntos de tipos de archivo que la búsqueda de Exchange no pudo indexar). Los elementos no aptos para la búsqueda se exportan a un archivo PST independiente. 
    
4. Haga clic en **Inicio** para exportar los resultados de búsqueda a un archivo PST. 
    
    Se mostrará una ventana con información acerca del estado del proceso de exportación.
