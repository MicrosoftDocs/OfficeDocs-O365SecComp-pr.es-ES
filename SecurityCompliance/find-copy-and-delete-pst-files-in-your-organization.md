---
title: Use la herramienta de recopilación de PST para buscar, copiar y eliminar los archivos PST en su organización
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 10/18/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid: MOE150
ms.assetid: 7a150c84-049c-4a9c-8c91-22355b35f2a7
description: Use la herramienta de recopilación de PST de Microsoft para buscar la red de su organización para obtener un inventario de los archivos PST que están dispersos por la organización. Después de encontrar los archivos PST, puede usar la herramienta de recopilación de PST para copiarlos en una ubicación central para que pueda importar a Office 365.
ms.openlocfilehash: 0537a65a32fa25704045bd587cb20f9eee13f628
ms.sourcegitcommit: 7956955cd919f6e00b64e4506605a743c5872549
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/26/2018
ms.locfileid: "25038133"
---
# <a name="use-the-pst-collection-tool-to-find-copy-and-delete-pst-files-in-your-organization"></a>Use la herramienta de recopilación de PST para buscar, copiar y eliminar los archivos PST en su organización

Puede usar la herramienta de recopilación de PST de Microsoft para buscar en la red de su organización para los archivos PST. La herramienta le ayudará a obtener un inventario de los archivos PST que están dispersos por la organización. Después de encontrar los archivos PST, puede usar la herramienta de recopilación de PST para copiarlos en una ubicación central. Necesidad de archivos pst en un uno lugar, a continuación, le permite importarlos a Exchange Online buzones (o un solo buzón de Exchange Online), donde, a continuación, puede aplicar el amplio conjunto de características de cumplimiento en Office 365. Esto incluye la importación de archivos PST al archivo que contiene los buzones de correo, busca mensajes específicos en los archivos PST que ha importado mediante el uso de las herramientas de búsqueda de exhibición de documentos electrónicos, retención de mensajes mediante el uso de exhibición de documentos electrónicos de los usuarios y las directivas de retención de Office 365 y administración de la vida ciclo de estos mensajes mediante la mensajería registra las características de administración de Exchange en línea. Una vez que esté seguro de que los archivos PST que recopilan se han importado correctamente a Office 365, puede usar la herramienta para eliminarlos de su ubicación original en la red. 
  
Otra cosa que puede hacer con la herramienta de recopilación de PST es impedir que los usuarios crear nuevos archivos PST y cambiar los archivos PST existentes que se encuentran en la red. Estas capacidades "bloque" le permiten buscar, recopilar y la importación de un conjunto conocido de los archivos PST a Office 365 y evitar la proliferación futura de los archivos PST en su organización. 
  
## <a name="how-the-pst-collection-tool-works"></a>Cómo funciona la herramienta de recopilación de PST

Este es un breve resumen del proceso de uso de la herramienta de recopilación de PST para encontrar, controlar, recopilar y eliminar los archivos PST en su organización.
  
![Información general sobre el proceso de la herramienta de recopilación de PST](media/67a29f27-f83c-4f0a-9df4-7ed92d3086fe.png)
  
1. **[Paso 1: busque los archivos PST en su red](#step-1-find-pst-files-on-your-network)** - cuando se ejecuta la herramienta para buscar los archivos PST, especificar una ubicación, como una unidad organizativa que contiene los objetos de Active Directory para los equipos cliente y servidor. También puede buscar equipos específicos o recursos compartidos de archivos de red. Al ejecutar la herramienta, un agente de colección "ligero" se instala en los equipos de destino. Este agente busca en el equipo de destino para los archivos PST y, a continuación, envía información a la herramienta de recopilación de PST sobre cualquier archivo PST que encuentre. La herramienta crea archivos de registro que contiene información acerca de los archivos PST que se han encontrado en las ubicaciones especificadas. Estos archivos se usan cuando se ejecuta la herramienta en pasos posteriores. 
    
2. **[(Opcional) paso 2: controlar el acceso a los archivos PST](#optional-step-2-control-access-to-pst-files)** -la herramienta crea un objeto de directiva de grupo (GPO) con una configuración que impide que los usuarios de creación o cambio de los archivos PST. Este GPO se aplica a todos los usuarios de su dominio. En este paso opcional le ayuda a "bloquear" los archivos PST que se han encontrado en el paso 1, por lo que puede recopilar, importación y eliminarlos sin necesidad de archivos PST nuevos creados o los archivos PST existentes que se ha cambiado. 
    
3. **[Paso 3: copie los archivos PST en una ubicación de la colección](#step-3-copy-the-pst-files-to-a-collection-location)** -permite recopilar los archivos PST en una ubicación para que se pueden importar a buzones de Exchange Online mediante el servicio Office 365 importar en el paso 4. Cuando se ejecuta la herramienta en el modo "recopilar", cada agente de colección copia los archivos PST desde el equipo de destino que se instala el agente de sesión en la ubicación de la colección. 
    
4. **[Paso 4: importar los archivos PST a Office 365](#step-4-import-the-pst-files-to-office-365)** -después de copiar los archivos PST en una ubicación, estará listo importarlos a buzones de Exchange Online. 
    
5. **[Paso 5: eliminar los archivos PST que se encuentran en la red](#step-5-delete-the-pst-files-found-on-your-network)** - después de que los archivos PST que se encuentra y recopilados se han importado a buzones de Exchange Online en Office 365, puede usar la herramienta de recopilación de PST para eliminar los archivos PST desde las ubicaciones originales donde se se han encontrado en el paso 1. 

## <a name="before-you-begin"></a>Antes de empezar

- Siga estos pasos para descargar la herramienta de recopilación de PST en el equipo local. 
    
    1. [Descargar la herramienta de recopilación de PST](https://aka.ms/pstcollectiontool).
    
    2. En la ventana emergente, haga clic en **Guardar** \> **Guardar como** para guardar el archivo PSTCollectionTool.zip en una carpeta en el equipo local. 
    
    3. Extraiga el archivo PSTCollectionTool.zip a una carpeta en el equipo local; el nombre de la carpeta predeterminada es PSTCollectionTool.
    
- Para ejecutar la herramienta de recopilación de PST en cualquier modo (Buscar, bloquear, copiar o eliminar), debe ser miembro del grupo Administradores de dominio en su dominio de Active Directory. 

## <a name="step-1-find-pst-files-on-your-network"></a>Paso 1: Busque los archivos PST en su red

Es el primer paso ejecutar la herramienta de recopilación de PST para buscar los archivos PST en su organización. Puede usar la herramienta para los siguientes tipos de ubicaciones de búsqueda. 
  
- Unidades organizativas (OU) en un dominio de Active Directory local. La herramienta busca todos los equipos que están contenidos en la unidad organizativa especificada. 
    
- Equipos cliente y servidor. La herramienta busca en los equipos especificados. 
    
- Recursos compartidos de archivos de red. La herramienta busca en los recursos compartidos de archivos de red especificado. 
    
Vea la descripción de la `Locations` parámetro de tabla en el procedimiento siguiente para obtener ejemplos de la sintaxis que se usará para cada uno de estos tipos de ubicación. 
  
> [!IMPORTANT]
> Tiene que la ejecución de la herramienta de recopilación de PST en el modo de buscar antes de poder realizar otras acciones como bloquear, recopilar o eliminación de archivos PST. 
  
1. Abra un símbolo del sistema (ejecutar como administrador) en el equipo local.
    
2. Vaya a la carpeta PSTCollectionTool (o la carpeta que el archivo PSTCollectionTool.zip a la que ha extraído).
    
3. Cambie al directorio DataCollectorMaster.
    
4. Ejecute el siguiente comando para buscar los archivos PST en una ubicación especificada.
    
    ```
    DataCollectorMaster.exe -DataSource Pst -Mode Find -JobName <Name> -Locations <Locations to search for PSTs> -LogLocation <Location to store log files> -ConfigurationLocation <Location to store configuration files>
    ```

    En la siguiente tabla se describe los parámetros y sus valores necesarios al ejecutar el comando DataCollectorMaster.exe para buscar los archivos PST. 
    
    |Parámetro ***|****Descripción****|Ejemplos ***|
    |:-----|:-----|:-----|
    | `DataSource` <br/> |Especifica el tipo de datos para buscar. Actualmente, puede usar la herramienta de recopilación de PST para buscar los archivos PST.  <br/> | `-DataSource Pst` <br/> |
    | `Mode` <br/> |Especifica el tipo de operación que realizará la herramienta. Use el valor `Find` para localizar los archivos PST en las ubicaciones especificadas. Tenga en cuenta que la herramienta puede buscar y obtener información acerca de los archivos PST que están abiertos en los archivos PST y de Outlook que están conectados a los perfiles de Outlook.<br/> | `-Mode Find` <br/> |
    | `JobName` <br/> |Especifica el nombre de la tarea de la colección de PST. Este mismo nombre de trabajo va a usar cuando se ejecuta la herramienta de recopilación de PST a bloquear, recopilar y elimine los archivos PST que se encuentran al ejecutar la herramienta para buscar los archivos PST. El nombre del trabajo también se agregará a los nombres de archivo de registro y configuración.  <br/> | `-JobName PstSearch1` <br/> |
    | `Locations` <br/> | Especifica una o varias ubicaciones para buscar los archivos PST. Si especifica más de una ubicación, utilice un punto y coma (;) para separar las ubicaciones individuales. No olvide rodear los valores individuales de este parámetro con comillas dobles ("").<br/><br/>   Este es el formato del valor de identidad necesarios para los tipos de ubicaciones que se pueden buscar.  <br/><br/>        **Unidades organizativas** - el nombre distintivo (DN) se usa para identificar las unidades organizativas; Por ejemplo:`"OU=NorthAmerica,OU=NWRegion,OU=ITServices,DC=contoso,DC=com"` <br/> > [!IMPORTANT]> No puede especificar el contenedor de equipos integrado (por ejemplo, CN = Computers, DC = contoso, DC = com ") porque no es una unidad organizativa.<br/> <br/> **Máquinas** - Use el nombre completo o el nombre de dominio completo (FQDN) para identificar los equipos cliente y servidor en la red; Por ejemplo:  <br/>  DN:`"CN=FILESERVER01,CN=Computers,DC=contoso,DC=com"` <br/>  O bien  <br/>  FQDN:`"FILESERVER01.contoso.com"` <br/><br/>  **Recursos compartidos de archivos de red** – uso un nombre UNC para identificar recursos compartidos de archivos de red; Por ejemplo,`"\\FILESERVER02\Users"` <br/> | `-Locations "CN=FILESERVER01,CN=Computers,DC=contoso,DC=com";"CN=FILESERVER02,CN=Computers,DC=contoso,DC=com"` <br/> |
    | `LogLocation` <br/> |Especifica la carpeta que se copiarán los archivos de registro a. Si la carpeta no existe, se creará al ejecutar la herramienta.  <br/> | `-LogLocation "c:\users\admin\desktop\PSTCollection"` <br/> |
    | `ConfigurationLocation` <br/> |Especifica la carpeta que el archivo de configuración .xml se copiarán a. Este archivo contiene información acerca de cada archivo PST que se encuentra cuando se ejecuta la herramienta. Este archivo se utilizará cuando se ejecuta la herramienta en el paso 3 para copiar los archivos PST que se encuentran.  <br/> | `-ConfigurationLocation "c:\users\admin\desktop\PSTCollection\Configuration"` <br/> |
    | `ExcludedLocations` <br/> |Este parámetro opcional especifica ubicaciones se debe omitir durante una operación de búsqueda. Puede excluir unidades organizativas específicas, equipos y recursos compartidos de archivos de red. Por ejemplo, podría excluir máquinas, como máquina configurado como un servidor SQL server (u otros tipos de servidores de aplicaciones), que los usuarios no tienen acceso a. Si especifica más de una ubicación para excluir, utilice un punto y coma (;) para separar las ubicaciones individuales. No olvide rodear los valores individuales de este parámetro con comillas dobles ("").  <br/> | `-ExcludedLocations "SQLSERVER01.contoso.com"` <br/> |
    | `ForceRestart` <br/> |Este modificador opcional le permite ejecutar la herramienta en el modo de búsqueda para un trabajo de la colección de PST existente. Al usar el `ForceRestart` pase, los resultados de la operación de búsqueda anterior para el trabajo se descartarán, y la herramienta volver a examinar las ubicaciones especificadas y crear nuevos archivos de registro y configuración.<br/> | `-ForceRestart` <br/> |
   
    Este es un ejemplo de la sintaxis para el comando DataCollectorMaster.exe con los valores reales para cada parámetro:
    
    ```
    DataCollectorMaster.exe -DataSource Pst -Mode Find -JobName PstSearch1 -Locations "CN=FILESERVER01,CN=Computers,DC=contoso,DC=com";"CN=FILESERVER02,CN=Computers,DC=contoso,DC=com" -LogLocation "c:\users\admin\desktop\PSTCollection" -ConfigurationLocation "c:\users\admin\desktop\PSTCollection\Configuration"
    ```

    Después de ejecutar el comando, se muestran los mensajes de estado detallados que muestran el progreso de la búsqueda de los archivos PST en las ubicaciones especificadas. Después de unos momentos, un mensaje de estado final muestra el número total de archivos PST que se han encontrado, si se ha completado el trabajo, y si se produjeron errores. Los mismos mensajes de estado se copian en el archivo. log.
    
### <a name="results-of-running-datacollectormasterexe-in-the-find-mode"></a>Resultados de la ejecución de DataCollectorMaster.exe en el modo de buscar

Después de ejecutar correctamente la herramienta de recopilación de PST el modo de buscar, los siguientes archivos se crean y almacenan en las carpetas especificadas por la `LogLocation` y `ConfigurationLocation` parámetros. 
  
- **\<NombreDeTrabajo\>_Buscar_\<DateTimeStamp\>.log** -el archivo de registro contiene los mensajes de estado que se han mostrado. Este archivo se crea en la carpeta especificada por el `LogLocation` parámetro. 
    
- **\<NombreDeTrabajo\>_Buscar_\<DateTimeStamp\>.csv** -archivo CSV el contiene una fila por cada archivo PST que se encontró. La información para cada PST incluye el equipo donde se encontró el archivo PST, la ubicación de la ruta de acceso completa al archivo del archivo PST, el propietario del archivo PST y el tamaño (en kilobytes, KB) del archivo PST. Este archivo se crea en la carpeta especificada por el `LogLocation` parámetro. 
    
    > [!TIP]
    > Use la herramienta Autosuma en Excel para calcular el tamaño total (en KB) de todos los archivos PST que aparecen en el archivo CSV. A continuación, puede utilizar una calculadora de conversión para convertir el tamaño total en megabytes (MB) o gigabytes (GB). 
  
- **\<NombreDeTrabajo\>_Buscar_\<DateTimeStamp\>.xml** -el archivo XML contiene información acerca de los valores de parámetro que dónde se usa cuando se ejecutó la herramienta en el modo de buscar. Este archivo también contiene información sobre todos los archivos PST que se encontraron. Los datos de este archivo se utilizan cuando se ejecuta, vuelva a ejecutar la herramienta para el mismo trabajo al bloque, recopilar o eliminar el archivo PST los archivos que se han encontrado. Este archivo se crea en la carpeta especificada por el `ConfigurationLocation` parámetro. 
    
    > [!IMPORTANT]
    > No cambie el nombre, cambiar o mover este archivo. Se usa mediante la herramienta de recopilación de PST cuando vuelva a ejecutar la herramienta en el bloque, copia, o eliminar el modo para la misma tarea. 

## <a name="optional-step-2-control-access-to-pst-files"></a>(Opcional) Paso 2: Controlar el acceso a los archivos PST

En este paso opcional le permite "proteger" los archivos PST que se han encontrado en el paso 1 para que pueda recopilar e importar un conjunto conocido de los archivos PST a Office 365. Cuando se ejecuta la herramienta de recopilación de PST en el modo de bloqueo, ocurrirá lo siguiente: 
  
- La herramienta crea un objeto de directiva de grupo (GPO) denominado *Controles del uso de PST* . Este GPO está vinculado a su dominio y se aplica a todos los usuarios autenticados en su organización. 
    
- El GPO de controles de uso de PST crea la configuración del registro en equipos de la organización. Dependiendo del parámetro que usa, puede crear una configuración del registro para evitar que los usuarios de la creación de nuevos archivos PST y una configuración del registro que impide que los usuarios cambien los archivos PST existentes.
    
> [!NOTE]
> Si el control de acceso a los archivos PST es demasiado perjudiciales para su organización, es posible que tenga en cuenta si se omite este paso y realizar el paso 3 para copiar los archivos PST en una ubicación central. A continuación, repita el paso 1 para el mismo trabajo (mediante el uso de la `ForceRestart` parámetro) para buscar archivos adicionales de archivos pst que se crearon una vez copiados los archivos pst a la ubicación de la colección. Si se encuentran los archivos PST nuevos, se puede copiar a la ubicación de la colección. Al usar el `ForceRestart` parámetro cuando vuelva a ejecutar la herramienta en el modo de buscar, los resultados de la operación de búsqueda anterior de un trabajo se descartarán y la herramienta vuelve a analizarlo en las ubicaciones especificadas. 

Para bloquear el acceso a los archivos PST:

1. Abra un símbolo del sistema (ejecutar como administrador) en el equipo local.
    
2. Vaya al directorio donde descargó la herramienta de recopilación de PST a.
    
3. Ejecute el siguiente comando para bloquear el acceso a los archivos PST que se encuentra en el paso 1.

    ```
    DataCollectorMaster.exe -DataSource Pst -Mode Block -JobName <Name of job from Step 1> -ConfigurationLocation <Location of configuration files from Step 1> -BlockChangesToFiles -BlockNewFiles
    ```

    En la siguiente tabla se describe los parámetros y sus valores necesarios al ejecutar el comando DataCollectorMaster.exe para bloquear la creación y modificación de los archivos PST. 
    
    |Parámetro ***|****Descripción****|Ejemplos ***|
    |:-----|:-----|:-----|
    | `DataSource` <br/> |Especifica el tipo de datos para buscar. Actualmente, puede usar la herramienta de recopilación de PST para buscar los archivos PST.  <br/> | `-DataSource Pst` <br/> |
    | `Mode` <br/> |Especifica el tipo de operación que realizará la herramienta. Use el valor `Block` para impedir que los usuarios crear nuevos archivos PST y realizar cambios en los archivos PST existentes.<br/> | `-Mode Block` <br/> |
    | `JobName` <br/> |Especifica el nombre de un trabajo de la colección de PST existente. Se debe usar este mismo nombre de trabajo que usó cuando ejecutó la herramienta en el modo de buscar en el paso 1. Este nombre de trabajo también se agrega en el nombre del archivo de registro que se crea al ejecutar la herramienta en el modo de bloqueo.  <br/> | `-JobName PstSearch1` <br/> |
    | `ConfigurationLocation` <br/> |Especifica que la carpeta contiene el archivo de configuración XML que se creó cuando ejecutó la herramienta en el modo de buscar. Use el mismo valor que usa para este parámetro en el paso 1.  <br/> | `-ConfigurationLocation "c:\users\admin\desktop\PSTCollection\Configuration"` <br/> |
    | `LogLocation` <br/> |Especifica la carpeta en la que deben copiarse en el archivo de registro para la operación de bloqueo. Éste es un parámetro opcional. Si no se incluye, se copia el archivo de registro a la carpeta donde descargó la herramienta de recopilación de PST a. Considere el uso de la misma ubicación del registro que usó cuando ejecutó la herramienta en el modo de buscar en el paso 1 para que todos los archivos de registro se guardan en la misma carpeta.  <br/> | `-LogLocation "c:\users\admin\desktop\PSTCollection"` <br/> |
    | `BlockChangesToFiles` <br/> |Use este modificador para impedir que los usuarios cambien un archivo PST. Cuando se usa este modificador, se crea la siguiente entrada del registro: `HKEY_CURRENT_USER\Software\Policies\Microsoft\Office\<version>\Outlook\PST\PstDisableGrow` y el valor de datos está establecido en 1. Esta configuración del registro se crea en los equipos de la organización por el GPO que se crea al ejecutar la herramienta de recopilación de PST en el modo de bloqueo.<br/> | `-BlockChangesToFiles` <br/> |
    | `BlockNewFiles` <br/> |Use este modificador para impedir que los usuarios crear nuevos archivos PST, apertura e importar archivos PST para Outlook y exportar archivos PST de Outlook. Cuando se usa este modificador, se crea la siguiente entrada del registro: `HKEY_CURRENT_USER\Software\Policies\Microsoft\Office\<version>\Outlook\DisablePst` y el valor de datos está establecido en 1. Esta configuración del registro se crea en los equipos de la organización por el GPO que se crea al ejecutar la herramienta de recopilación de PST en el modo de bloqueo.<br/> | `-BlockNewFiles` <br/> |
   
    Este es un ejemplo de la sintaxis para el comando DataCollectorMaster.exe con los valores reales para cada parámetro:

    ```
    DataCollectorMaster.exe -DataSource Pst -Mode Block -JobName PstSearch1 -ConfigurationLocation "c:\users\admin\desktop\PSTCollection\Configuration" -LogLocation "c:\users\admin\desktop\PSTCollection" -BlockChangesToFiles -BlockNewFiles
    ```
    
    Se le pide que confirme que desea bloquear nuevos archivos PST o los cambios realizados en los archivos PST existentes. Después de confirmar que desea continuar y el comando se ejecuta correctamente, se muestra un mensaje que indica que se ha creado un nuevo GPO, denominado "Controles de uso de PST,".
    
## <a name="step-3-copy-the-pst-files-to-a-collection-location"></a>Paso 3: Copiar los archivos PST en una ubicación de la colección

El siguiente paso es copiar el archivo PST que encuentra cuando se ejecutó la herramienta de recopilación de PST en el modo de buscar los archivos. Esto le permite recopilar los archivos PST en una ubicación para que más adelante puede importar a Office 365. Antes de copiar los archivos PST en la ubicación de la colección, considere la posibilidad de determinar la cantidad total de espacio de almacenamiento que se requiere. Puede hacerlo mediante el archivo CSV que se creó en el paso 1 para calcular el tamaño total de todos los archivos PST.
  
> [!NOTE]
> Una vez que haya importado los archivos PST a Office 365 y eliminarlos de su ubicación original, es posible que desee eliminarlos de la ubicación de la colección que ha copiado en este paso. 
  
1. Abra un símbolo del sistema (ejecutar como administrador) en el equipo local.
    
2. Vaya al directorio donde descargó la herramienta de recopilación de PST a.
    
3. Ejecute el siguiente comando para copiar los archivos PST en una ubicación especificada.
    
    ```
    DataCollectorMaster.exe -DataSource Pst -Mode Collect -JobName <Name of job from Step 1> -Locations <same locations from Step 1> -ConfigurationLocation <Location of configuration files from Step 1> -CopyLocation <Location to copy PST files to>
    ```

    En la siguiente tabla se describe los parámetros y sus valores necesarios al ejecutar el comando DataCollectorMaster.exe para copiar los archivos PST. 
    
    |Parámetro ***|****Descripción****|Ejemplos ***|
    |:-----|:-----|:-----|
    | `DataSource` <br/> |Especifica el tipo de datos para buscar. Actualmente, puede usar la herramienta de recopilación de PST para buscar los archivos PST.  <br/> | `-DataSource Pst` <br/> |
    | `Mode` <br/> |Especifica el tipo de operación que realizará la herramienta. Use el valor `Collect` copiar que archivos PST que se han encontrado cuando se ejecutó la herramienta en el modo de buscar. Tenga en cuenta que la herramienta es capaz de copiar los archivos de PST que están abiertos en Outlook y copian los archivos PST que están conectados a los perfiles de Outlook.<br/> | `-Mode Collect` <br/> |
    | `JobName` <br/> |Especifica el nombre de un trabajo de la colección de PST existente. Se debe usar este mismo nombre de trabajo que usó cuando ejecutó la herramienta en el modo de buscar en el paso 1. Este nombre de trabajo también se agrega en el nombre del archivo de registro que se crea al ejecutar la herramienta en el modo de recopilar.  <br/> | `-JobName PstSearch1` <br/> |
    | `Locations` <br/> |Use el mismo valor que usa para la `Locations` parámetro en el paso 1. Se incluye este parámetro al ejecutar la herramienta en el modo de recopilar si desea volver a ejecutar la herramienta para eliminar los archivos PST desde su ubicación de origen en el paso 5.<br/> | `-Locations "CN=FILESERVER01,CN=Computers,DC=contoso,DC=com"; "CN=FILESERVER02,CN=Computers,DC=contoso,DC=com"` <br/> |
    | `ConfigurationLocation` <br/> |Especifica la carpeta que contiene el archivo de configuración XML que se creó cuando ejecutó la herramienta en el modo de buscar. Use el mismo valor que usa para este parámetro en el paso 1.  <br/> | `-ConfigurationLocation "c:\users\admin\desktop \PSTCollection\Configuration"` <br/> |
    | `CopyLocation` <br/> |Especifica la ubicación de la colección donde desea copiar los archivos PST. Puede copiar los archivos en un servidor de archivos, un recurso compartido de red o una unidad de disco duro. La ubicación debe existir antes de ejecutar la herramienta en el modo de recopilar. La herramienta no crea la ubicación y devolverá un error que indica que no existe.  <br/> Además, tiene permisos de escritura a la ubicación de la colección especificada por este parámetro.  <br/> | `-CopyLocation "\\FILESERVER03\PSTs"` <br/> |
    | `LogLocation` <br/> |Especifica la carpeta en la que deben copiarse en el archivo de registro para el modo de recopilar. Éste es un parámetro opcional. Si no se incluye, se copia el archivo de registro a la carpeta donde descargó la herramienta de recopilación de PST a. Considere el uso de la misma ubicación del registro que usó cuando ejecutó la herramienta en el modo de buscar en el paso 1 para que todos los archivos de registro se guardan en la misma carpeta.  <br/> | `-LogLocation "c:\users\admin\desktop\PSTCollection"` <br/> |
    | `ForceRestart` <br/> |Este modificador opcional le permite volver a ejecutar la herramienta en el modo de recopilación de un proyecto existente de la colección de PST. Si anteriormente se ejecutó la herramienta en el modo de recopilar, pero a continuación, ejecutó la herramienta en el modo de buscar con el `ForceRestart` modificador para volver a examinar las ubicaciones para los archivos PST, puede utilizar este modificador para volver a ejecutar la herramienta en modo de recopilación y vuelva a copiar los archivos PST que había encontrado cuándo su volver a examinar las ubicaciones. Cuando se usa el `ForceRestart` modificador en el modo de la colección, la herramienta pasa por alto cualquier operación de colección anterior e intenta copiar los archivos PST desde el principio.<br/> | `-ForceRestart` <br/> |
   
    Este es un ejemplo de la sintaxis de la herramienta de DataCollectorMaster.exe con los valores reales para cada parámetro:
    
    ```
    DataCollectorMaster.exe -DataSource Pst -Mode Collect -JobName PstSearch1 -Locations "CN=FILESERVER01,CN=Computers,DC=contoso,DC=com";"CN=FILESERVER02,CN=Computers,DC=contoso,DC=com" -ConfigurationLocation "c:\users\admin\desktop\PSTCollection\Configuration" -CopyLocation "\\FILESERVER03\PSTs" -LogLocation "c:\users\admin\desktop\PSTCollection"
    ```

    Después de ejecutar el comando, se muestran los mensajes de estado detallados que muestran el progreso de la recopilación de los archivos PST que se han encontrado en el paso 1. Después de unos momentos, un mensaje de estado final se muestra si hubo algún error y la ubicación en la que se copia el registro en. Los mismos mensajes de estado se copian en el archivo. log.
    
### <a name="results-of-running-datacollectormasterexe-in-the-collect-mode"></a>Resultados de la ejecución de DataCollectorMaster.exe en el modo de recopilar

Después de ejecutar correctamente DataCollectorMaster.exe en el modo de recopilar, los siguientes archivos se crean y almacenan en las carpetas especificadas por la `LogLocation` y `ConfigurationLocation` parámetros. 
  
- **\<NombreDeTrabajo\>_recopilar_\<DateTimeStamp\>.log** -el archivo de registro contiene los mensajes de estado que se han mostrado. Este archivo se crea en la carpeta especificada por el `LogLocation` parámetro. 
    
- **\<NombreDeTrabajo\>_recopilar_\<DateTimeStamp\>.xml** -el archivo XML sólo contiene información acerca de los valores de parámetro que donde utilizado por la herramienta se ejecutó en el modo de recopilar. Los datos de este archivo se utilizan cuando se ejecuta vuelva a ejecutar la herramienta DataCollectorMaster.exe para eliminar los archivos PST; consulte el [paso 5](#step-5-delete-the-pst-files-found-on-your-network).
    

## <a name="step-4-import-the-pst-files-to-office-365"></a>Paso 4: Importar los archivos PST a Office 365

Una vez recopilada los archivos PST que se encuentra en el paso 1, el siguiente paso es importarlos a los buzones de correo en Office 365. Como parte o el proceso de importación, debe crear un archivo de asignación de CSV que contiene una fila de cada archivo PST que desea importar. Información de cada fila especifica el nombre del archivo PST, dirección de correo electrónico del usuario y si va a importar el archivo PST al usuario principal de o archivo de buzón de correo. Use la información en el **nombreDeTrabajo\>_Buscar_\<DateTimeStamp.csv** archivo (creado en el paso) 1 que le ayudarán a crear el archivo de asignación de CSV. 
  
Para que obtener instrucciones paso a paso importar archivos PST a Office 365, vea uno de los siguientes temas:
  
- [Usar la carga en la red para importar archivos PST en Office 365](use-network-upload-to-import-pst-files.md)
    
- [Usar el envío de unidades para importar los archivos PST a Office 365](use-drive-shipping-to-import-pst-files-to-office-365.md)
    

## <a name="step-5-delete-the-pst-files-found-on-your-network"></a>Paso 5: Eliminación de los archivos PST que se encuentra en la red

Una vez importados los archivos PST que se encuentra y recopilan a buzones de Exchange Online en Office 365, puede usar la herramienta de recopilación de PST para eliminar los archivos PST de las ubicaciones de origen original dónde se encontraron en el paso 1. 
  
1. Abra un símbolo del sistema (ejecutar como administrador) en el equipo local.
    
2. Vaya al directorio donde descargó la herramienta de recopilación de PST a.
    
3. Ejecute el siguiente comando para eliminar los archivos PST.

    ```
    DataCollectorMaster.exe -DataSource Pst -Mode Delete -JobName <Name of job from Step 1> -ConfigurationLocation <Location of configuration files from Step 1> -CopyLocation <Location to copy PST files to>
    ```

    En la siguiente tabla se describe los parámetros y sus valores necesarios al ejecutar el comando DataCollectorMaster.exe para eliminar los archivos PST. 
    
    |Parámetro ***|****Descripción****|Ejemplos ***|
    |:-----|:-----|:-----|
    | `DataSource` <br/> |Especifica el tipo de datos para buscar. Actualmente, puede usar la herramienta de recopilación de PST para buscar los archivos PST. ![separador](media/b078d05c-3aee-4b9f-8805-6a8a9d8970ee.png)           <br/> | `-DataSource Pst` <br/> |
    | `Mode` <br/> |Especifica el tipo de operación que realizará la herramienta. Use el valor `Delete` eliminar que archivos PST que se han encontrado cuando se ejecutó la herramienta en el modo de buscar.<br/> | `-Mode Delete` <br/> |
    | `JobName` <br/> |Especifica el nombre de un trabajo de la colección de PST existente. Se debe usar este mismo nombre de trabajo que usó cuando se ejecutó la herramienta en el modo de buscar y el modo recopilar en el paso 1 y el paso 3. Este nombre de trabajo también se agrega en el nombre del archivo de registro que se crea al ejecutar la herramienta en el modo de eliminar.  <br/> | `-JobName PstSearch1` <br/> |
    | `ConfigurationLocation` <br/> |Especifica la carpeta que contiene el archivo de configuración XML que se creó cuando ejecutó la herramienta en el modo de recopilar. Use el mismo valor que usa para este parámetro en el paso 3.  <br/> | `-ConfigurationLocation "c:\users\admin\ desktop\PSTCollection\Configuration"` <br/> |
    | `LogLocation` <br/> |Especifica la carpeta en la que deben copiarse en el archivo de registro para el modo de eliminar. Éste es un parámetro opcional. Si no se incluye, se copia el archivo de registro a la carpeta donde descargó la herramienta de recopilación de PST a. Considere el uso de la misma ubicación del registro que usa cuando se ejecutó la herramienta en la búsqueda y modos de recopilar en el paso 1 y paso 3 para que todos los archivos de registro se guardan en la misma carpeta.  <br/> | `-LogLocation "c:\users\admin\desktop\PSTCollection"` <br/> |
    | `ForceRestart` <br/> |Este modificador opcional le permite volver a ejecutar la herramienta en el modo de eliminación de un proyecto existente de la colección de PST. Si anteriormente se ejecutó la herramienta en el modo de eliminar, pero a continuación, ejecutó la herramienta en el modo de buscar con el `ForceRestart` modificador para volver a examinar las ubicaciones para los archivos PST, puede utilizar este modificador para volver a ejecutar la herramienta en el modo eliminar y elimine los archivos PST que había encontrado cuándo su re-sca nned las ubicaciones. Cuando se usa el `ForceRestart` modificador en el modo de eliminar, la herramienta pasa por alto cualquier operación Eliminar anterior e intenta eliminar los archivos PST de nuevo.<br/> | `-ForceRestart` <br/> 

    Este es un ejemplo de la sintaxis de la herramienta de DataCollectorMaster.exe con los valores reales para cada parámetro:
    
    ```
    DataCollectorMaster.exe -DataSource Pst -Mode Delete -JobName PstSearch1 -ConfigurationLocation "c:\users\admin\desktop\PSTCollection\Configuration" -LogLocation "c:\users\admin\desktop\PSTCollection"
    ```
   
    Después de ejecutar el comando, se muestran los mensajes de estado detallados que muestran el progreso de la eliminación de los archivos PST que se encontraron en el paso 1 y recopilados en el paso 3. Después de unos momentos, un mensaje de estado final se muestra si hubo algún error y la ubicación en la que se copia el registro en. Los mismos mensajes de estado se copian en el archivo. log.
    
### <a name="results-of-running-datacollectormasterexe-in-the-delete-mode"></a>Resultados de la ejecución de DataCollectorMaster.exe en el modo de eliminar

Después de ejecutar correctamente DataCollectorMaster.exe en el modo de eliminar, los siguientes archivos se crean y almacenan en la carpeta especificada por el `LogLocation` y `ConfigurationLocation` parámetros. 
  
- **\<NombreDeTrabajo\>_Eliminar_\<DateTimeStamp\>.log** -el archivo de registro contiene los mensajes de estado que se han mostrado. Este archivo se crea en la carpeta especificada por el `LogLocation` parámetro. 
    
- **\<NombreDeTrabajo\>_Eliminar_\<DateTimeStamp\>.xml** -el archivo XML sólo contiene información acerca de los valores de parámetro que donde utilizado por la herramienta se ejecutó en el modo de eliminar. También muestra la ruta de acceso de archivos y el nombre de cada archivo PST que se ha eliminado. Este archivo se crea en la carpeta especificada por el `ConfigurationLocation` parámetro. 
