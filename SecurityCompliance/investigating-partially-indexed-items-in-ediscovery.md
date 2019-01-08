---
title: Investigar elementos indizados parcialmente en eDiscovery de Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 1/26/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid: MOE150
ms.assetid: 4e8ff113-6361-41e2-915a-6338a7e2a1ed
description: Elementos indizados parcialmente (también llamada no indexado elementos) son los elementos del buzón de Exchange y documentos en SharePoint y sitios de OneDrive para la que, por algún motivo no estaba indizado completamente para la búsqueda de contenido. En este artículo, obtenga información sobre por qué elementos no se pueden indizar para la búsqueda y se devuelven como elementos indizados parcialmente, identificar errores de búsqueda para los elementos indizados parcialmente y usar un script de PowerShell para determinar la exposición de su organización a correo electrónico parcialmente indizado elementos.
ms.openlocfilehash: c1003f9907fffa37042ba62d01e4d938250cf570
ms.sourcegitcommit: 30faa3ba91cab4c36e3d8d8ed5858d5269ea8a56
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/08/2019
ms.locfileid: "27749344"
---
# <a name="investigating-partially-indexed-items-in-office-365-ediscovery"></a>Investigar elementos indizados parcialmente en eDiscovery de Office 365

Una búsqueda de contenido que se ejecuta desde la seguridad de Office 365 &amp; centro de cumplimiento incluye automáticamente los elementos indizados parcialmente en los resultados de búsqueda estimado al ejecutar una búsqueda. Los elementos indizados parcialmente son los elementos del buzón de Exchange y documentos en SharePoint y OneDrive para los sitios de negocio que, por algún motivo, completamente no estaban indizados para la búsqueda. La mayoría de los mensajes de correo electrónico y documentos del sitio se indizan correctamente debido a que se encuentren dentro de los [límites de indización para mensajes de correo electrónico](limits-for-content-search.md#indexing-limits-for-email-messages). Sin embargo, algunos elementos pueden superar estos límites de indización y se van a indizar parcialmente. Estas son otras razones por qué elementos no se pueden indizar para la búsqueda y se devuelven como elementos indizados parcialmente cuando se ejecuta una búsqueda de contenido:
  
- Mensajes de correo electrónico tienen un archivo adjunto de un tipo de archivo que no se pueden indizar; en la mayoría de los casos, es el tipo de archivo [no reconocido o no compatibles para la indización](partially-indexed-items-in-content-search.md#file-types-not-indexed-for-search)
    
- Mensajes de correo electrónico tienen un archivo adjunto sin un controlador válido, como archivos de imagen; Ésta es la causa más común de los elementos de correo electrónico parcialmente indizados
    
- Demasiados archivos adjuntados a un mensaje de correo electrónico
    
- Un archivo adjuntado a un mensaje de correo electrónico es demasiado grande
    
- Se admite el tipo de archivo para la indización, pero se produjo un error de indización para un archivo específico
    
Aunque varía, la mayoría de los clientes de las organizaciones de Office 365 tienen menos del 1% de contenido por volumen y menor que 12% del contenido por tamaño que se indiza parcialmente. El motivo de la diferencia entre el volumen frente a tamaño es que los archivos más grandes tienen una mayor probabilidad de que contiene contenido que no se pueden indizar completamente.
  
## <a name="why-does-the-partially-indexed-item-count-change-for-a-search"></a>¿Por qué se cambia el número de elementos indizados parcialmente para una búsqueda?

Después de ejecutar una búsqueda de contenido en la seguridad de Office 365 &amp; centro de cumplimiento, el número total y el tamaño de los elementos indizados parcialmente en las ubicaciones que se han buscado aparecen en las estadísticas de resultados de búsqueda que se muestran en las estadísticas detalladas para la búsqueda. Tenga en cuenta que estos se denominan *elementos sin indizar* en las estadísticas de búsqueda. A continuación presentamos algunas cosas que afectarán al número de elementos indizados parcialmente que se devuelven en los resultados de búsqueda: 
  
- Si un elemento se indiza parcialmente y coincide con la consulta de búsqueda, se incluye en el recuento (y tamaño) de los elementos de resultado de búsqueda y los elementos indizados parcialmente. Sin embargo, cuando se exportan los resultados de la misma que la búsqueda, el elemento se incluye únicamente con el conjunto de resultados de búsqueda; no se incluye como un elemento indizado parcialmente.
    
- Si especifica un intervalo de fechas para una consulta de búsqueda (incluidos en la consulta de palabras clave) o mediante una condición, cualquier elemento parcialmente indizado que no coincide con el intervalo de fechas no se incluye en el recuento de los elementos indizados parcialmente. Sólo los elementos indizados parcialmente que se encuentren dentro del intervalo de fechas se incluyen en el recuento de elementos indizados parcialmente.
    
 **Nota:** Parcialmente indizar los elementos ubicados en SharePoint y OneDrive sitios que *no están* incluidos en la estimación de los elementos indizados parcialmente que se muestra en las estadísticas detalladas para la búsqueda. Sin embargo, se pueden exportar los elementos indizados parcialmente al exportar los resultados de una búsqueda de contenido. Por ejemplo, si sólo busca sitios en una búsqueda de contenido, el número estimado parcialmente los elementos indizados será cero. 
  
## <a name="calculating-the-ratio-of-partially-indexed-items-in-your-organization"></a>Calcula la proporción de elementos indizados parcialmente en la organización

Para entender la exposición de la organización a los elementos indizados parcialmente, se puede ejecutar una búsqueda de todo el contenido en todos los buzones (mediante el uso de una consulta de palabra clave en blanco). En el siguiente ejemplo, hay 56,208 (4,830 MB) totalmente indizados elementos y 470 (316 MB) elementos indizados parcialmente.
  
![Ejemplo de que muestra estadísticas de búsqueda elementos indizados parcialmente](media/0f6a5cf7-4c98-44a0-a0dd-5aed67124641.png)
  
Puede determinar el porcentaje de los elementos indizados parcialmente mediante el uso de los siguientes cálculos.
  
 **Para calcular la proporción de elementos indizados parcialmente en su organización:**

`(Total number of partially indexed items/Total number of items) x 100`


`(470/56,208) x 100 = 0.84%`
 
Mediante el uso de los resultados de búsqueda del ejemplo anterior,. parcialmente se indizan 84% de todos los elementos de los buzones de correo.
  
 **Para calcular el porcentaje del tamaño de los elementos indizados parcialmente en su organización:**

`(Size of all partially indexed items/Size of all items) x 100`

`(316 MB/4830 MB) x 100 = 6.54%`

Por lo tanto en el ejemplo anterior, son 6.54% del tamaño total de los elementos del buzón de los elementos indizados parcialmente. Como se mencionó anteriormente, la mayoría de las organizaciones de Office 365 los clientes tienen menos del 1% de contenido por volumen y menor que 12% del contenido por tamaño que se indiza parcialmente.

## <a name="working-with-partially-indexed-items"></a>Trabajar con parcialmente elementos indizados

En los casos cuando se necesita examinar parcialmente los elementos para validar que no contienen información relevante, puede [exportar un informe de búsqueda de contenido](export-a-content-search-report.md) que contiene información acerca de los elementos indizados parcialmente. Al exportar un informe de búsqueda de contenido, asegúrese de elegir una de las opciones de exportación que incluye los elementos indizados parcialmente. 
  
![Elija la segunda o tercera opción para exportar los elementos indizados parcialmente](media/624a62b4-78f7-4329-ab5d-e62e3b369885.png)
  
Al exportar los resultados de la búsqueda de contenido o un informe de búsqueda de contenido mediante una de estas opciones, la exportación incluye un informe denominado Items.csv sin indizar. Este informe incluye la mayor parte de la misma información que el archivo ResultsLog.csv; Sin embargo, el archivo Items.csv no indizados también incluye dos campos relacionados con los elementos indizados parcialmente: **Error etiquetas** y **Propiedades de Error**. Estos campos contienen información sobre el error de indización para cada elemento indizado parcialmente. Uso de la información en estos dos campos puede ayudarle a determinar si el error de indización para un determinado repercute en la investigación. Si es así, puede realizar una búsqueda de contenido dirigida y recuperar y exportar mensajes de correo electrónico específicos y documentos de SharePoint o OneDrive para que se pueden examinar para determinar si son relevantes para la investigación. Para obtener instrucciones detalladas, consulte [Prepare un archivo CSV para una búsqueda de contenido dirigido en Office 365](csv-file-for-an-id-list-content-search.md).
  
 **Nota:** El archivo Items.csv no indizados también contiene campos con el nombre de **Tipo de Error** y el **Mensaje de Error**. Estos son heredados campos que contienen información que es similar a la información en los campos de **Etiquetas de Error** y **Las propiedades de Error** , pero con menos información detallada. Puede omitir estos campos heredados. 
  
## <a name="errors-related-to-partially-indexed-items"></a>Errores relacionados con los elementos indizados parcialmente

Etiquetas de error se componen de dos tipos de información, el error y el tipo de archivo. Por ejemplo, en este par error/filetype:

```
 parseroutputsize_xls
```

   
 `parseroutputsize`es el error y `xls` es el tipo de archivo del archivo que se produjo el error. En los casos eran no se reconoció el tipo de archivo o el tipo de archivo no es aplicable para el error, podrá ver el valor `noformat` en lugar del tipo de archivo. 
  
La siguiente es una lista de la indización de errores y una descripción de la causa posible del error.
  
|**Etiqueta de error**|**Descripción**|
|:-----|:-----|
| `attachmentcount` <br/> |Un mensaje de correo tenía demasiados datos adjuntos, y algunos de estos datos adjuntos no se han procesado.  <br/> |
| `attachmentdepth` <br/> |El analizador de almacenes de datos y documentos contenido encontró demasiados niveles de datos adjuntos que se pueden anidados dentro de otros datos adjuntos. Algunos de estos datos adjuntos no se procesaron.  <br/> |
| `attachmentrms` <br/> |Datos adjuntos no pudo descodificar debido a que era protegidos con RMS.  <br/> |
| `attachmentsize` <br/> |Un archivo adjuntado a un mensaje de correo electrónico es demasiado grande y no se pudo procesar.  <br/> |
| `indexingtruncated` <br/> |Al escribir el mensaje de correo electrónico procesados en el índice, una de las propiedades se pueden indizar era demasiado grande y se ha truncado. Se enumeran las propiedades truncadas en el campo de propiedades de Error.  <br/> |
| `invalidunicode` <br/> |Un mensaje de correo electrónico contiene texto que no se pudo procesar como Unicode válido. Indización de este elemento puede ser incompleta.  <br/> |
| `parserencrypted` <br/> |Se cifra el contenido de los datos adjuntos o un mensaje de correo electrónico y Office 365 no se pudo descodificar el contenido.  <br/> |
| `parsererror` <br/> |Se ha producido un error desconocido durante el análisis. Esto da como resultado normalmente desde un error de software o un bloqueo del servicio.  <br/> |
| `parserinputsize` <br/> |Era demasiado grande para el analizador para tratar un archivo adjunto, y el análisis de dichos datos adjuntos no hizo o no se completó.  <br/> |
| `parsermalformed` <br/> |Un archivo adjunto está mal formado y no se ha podido ser tratado por el analizador. Da formato a este resultado desde el archivo antiguo can, los archivos creados por el software incompatible o virus que pretende ser algo distinto de solicitado.  <br/> |
| `parseroutputsize` <br/> |El resultado del análisis de los datos adjuntos es demasiado grande y que tuvieron que se trunca.  <br/> |
| `parserunknowntype` <br/> |Datos adjuntos tenían un tipo de archivo que no se pudo detectar Office 365.  <br/> |
| `parserunsupportedtype` <br/> |Datos adjuntos tenían un tipo de archivo que se detectan 365could de Office, pero ese tipo de archivo de análisis no es compatible.  <br/> |
| `propertytoobig` <br/> |El valor de una propiedad de correo electrónico en Exchange era demasiado grande que se recuperarán almacén y no se pudo procesar el mensaje. Esto sólo ocurre normalmente a la propiedad de cuerpo de un mensaje de correo electrónico.  <br/> |
| `retrieverrms` <br/> |No se pudo descodificar un mensaje protegido mediante RMS los almacenes de datos de contenido.  <br/> |
| `wordbreakertruncated` <br/> |Demasiadas palabras se han identificado en el documento durante la indización. Detener el procesamiento de la propiedad al alcanzar el límite, y la propiedad se trunca.  <br/> |
   
Campos de error describen los campos que se ven afectados por el error de procesamiento que aparecen en el campo de etiquetas de Error. Si va a buscar, como una propiedad `subject` o `participants`, errores en el cuerpo del mensaje no afectan a los resultados de la búsqueda. Esto puede resultar útil al determinar exactamente qué elementos indizados parcialmente es posible que deba investigar.
  
## <a name="using-a-powershell-script-to-determine-your-organizations-exposure-to-partially-indexed-email-items"></a>Uso de un script de PowerShell para determinar la exposición de la organización a los elementos de correo electrónico parcialmente indizados

Los pasos siguientes muestran cómo ejecutar un script de PowerShell que busca todos los elementos de todos los buzones de Exchange y, a continuación, genera un informe sobre la relación de la organización de los elementos de correo electrónico parcialmente indizados (por el número y tamaño) y muestra el número de elementos (y el tipo de archivo) para cada error de indización que se produce. Use las descripciones de la etiqueta de error en la sección anterior para identificar el error de indización.
  
1. Guarde el siguiente texto en un archivo de secuencia de comandos de Windows PowerShell mediante el uso de un sufijo de nombre de archivo de. ps1; Por ejemplo, `PartiallyIndexedItems.ps1`.

```
  write-host "**************************************************"
  write-host "     Office 365 Security &amp; Compliance Center      " -foregroundColor yellow -backgroundcolor darkgreen
  write-host "   eDiscovery Partially Indexed Item Statistics   " -foregroundColor yellow -backgroundcolor darkgreen
  write-host "**************************************************"
  " " 
  # Create a search with Error Tags Refinders enabled
  Remove-ComplianceSearch "RefinerTest" -Confirm:$false -ErrorAction 'SilentlyContinue'
  New-ComplianceSearch -Name "RefinerTest" -ContentMatchQuery "size>0" -RefinerNames ErrorTags -ExchangeLocation ALL
  Start-ComplianceSearch "RefinerTest"
  # Loop while search is in progress
  do{
      Write-host "Waiting for search to complete..."
      Start-Sleep -s 5
      $complianceSearch = Get-ComplianceSearch "RefinerTest"
  }while ($complianceSearch.Status -ne 'Completed')
  $refiners = $complianceSearch.Refiners | ConvertFrom-Json
  $errorTagProperties = $refiners.Entries | Get-Member -MemberType NoteProperty
  $partiallyIndexedRatio = $complianceSearch.UnindexedItems / $complianceSearch.Items
  $partiallyIndexedSizeRatio = $complianceSearch.UnindexedSize / $complianceSearch.Size
  " "
  "===== Partially indexed items ====="
  "         Total          Ratio"
  "Count    {0:N0}{1:P2}" -f $complianceSearch.Items.ToString("N0").PadRight(15, " "), $partiallyIndexedRatio
  "Size(GB) {0:N2}{1:P2}" -f ($complianceSearch.Size / 1GB).ToString("N2").PadRight(15, " "), $partiallyIndexedSizeRatio
  " "
  Write-Host ===== Reasons for partially indexed items =====
  foreach($errorTagProperty in $errorTagProperties)
  {
      $name = $refiners.Entries.($errorTagProperty.Name).Name
      $count = $refiners.Entries.($errorTagProperty.Name).TotalCount
      $frag = $name.Split("{_}")
      $errorTag = $frag[0]
      $fileType = $frag[1]
      if ($errorTag -ne $lastErrorTag)
      {
          $errorTag
      }
      "    " + $fileType + " => " + $count
      $lastErrorTag = $errorTag
  }
  
```
   
2. [Conectarse a Office 365 seguridad &amp; centro de cumplimiento PowerShell](https://go.microsoft.com/fwlink/p/?linkid=627084).
    
3. En seguridad &amp; PowerShell de centro de cumplimiento, vaya a la carpeta donde guardó el script en el paso 1 y, a continuación, ejecute el script; Por ejemplo:

    ```
    .\PartiallyIndexedItems.ps1
    ```
   
Este es un ejemplo fo el resultado devuelto por la secuencia de comandos.
  
![Ejemplo de salida de secuencia de comandos que genera un informe sobre la exposición de la organización a los elementos de correo electrónico parcialmente indizados](media/aeab5943-c15d-431a-bdb2-82f135abc2f3.png)
  
Tenga en cuenta lo siguiente:
  
1. El número total y el tamaño de los elementos de correo electrónico y la relación entre la organización de los elementos de correo electrónico parcialmente indizada (por el número y tamaño)
    
2. Las etiquetas de un error de lista y los tipos de archivo para el que se produjo el error.
  
## <a name="see-also"></a>Vea también

[Elementos parcialmente indizados en la búsqueda de contenido en Office 365](partially-indexed-items-in-content-search.md)
