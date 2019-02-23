---
title: Usar la herramienta de recopilación de PST para buscar, copiar y eliminar archivos PST en la organización
ms.author: markjjo
author: markjjo
manager: laurawi
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid: MOE150
ms.assetid: 7a150c84-049c-4a9c-8c91-22355b35f2a7
description: Use la herramienta de recopilación de Microsoft PST para buscar en la red de su organización para obtener un inventario de los archivos PST que están dispersos en toda la organización. Después de encontrar los archivos PST, puede usar la herramienta de recopilación de PST para copiarlos en una ubicación central para poder importarlos a Office 365.
ms.openlocfilehash: 42f192b1a69ee9893df7cc8353b48cd9baabeda7
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/23/2019
ms.locfileid: "30216650"
---
# <a name="use-the-pst-collection-tool-to-find-copy-and-delete-pst-files-in-your-organization"></a>Usar la herramienta de recopilación de PST para buscar, copiar y eliminar archivos PST en la organización

> [!IMPORTANT]
> La herramienta de recopilación de PST descrita en este artículo no es compatible con ningún servicio o programa de soporte estándar de Microsoft. La herramienta se proporciona tal cual sin garantías de ningún tipo. Microsoft renuncia a todas las garantías implícitas, incluidas, entre otras, todas las garantías implícitas de comerciabilidad o de idoneidad para un propósito en particular. Todo el riesgo derivado del uso o el rendimiento de la herramienta y la documentación permanece con usted. En ningún caso Microsoft, sus autores o cualquier otro implicado en la creación, la producción o la entrega de la herramienta son responsables de cualquier daño (incluidos, entre otros, los daños en la pérdida de beneficios de negocio, la interrupción del negocio, la pérdida de información de la empresa u otra pérdida pecuniaria que surja del uso o la incapacidad de usar la herramienta o la documentación, incluso si se ha notificado a Microsoft de la posibilidad de dichos daños.

Puede usar la herramienta de recopilación de Microsoft PST para buscar archivos PST en la red de su organización. La herramienta le ayuda a obtener un inventario de los archivos PST que están dispersos en toda la organización. Después de encontrar los archivos PST, puede usar la herramienta de recopilación de PST para copiarlos en una ubicación central. Al tener los archivos PST en un lugar, se pueden importar a buzones de correo de Exchange Online (o a un único buzón de Exchange Online), donde puede aplicar el amplio conjunto de características de cumplimiento en Office 365. Esto incluye la importación de archivos PST a los buzones de archivo de los usuarios, la búsqueda de mensajes específicos en los archivos PST que importó mediante herramientas de búsqueda de eDiscovery, la retención de mensajes mediante suspensiones de eDiscovery y las directivas de retención de Office 365, y la administración de la vida ciclo de estos mensajes mediante las características de administración de registros de mensajería de Exchange Online. Una vez que esté seguro de que los archivos PST que ha recopilado se han importado correctamente a Office 365, puede usar la herramienta para eliminarlos de su ubicación original en la red. 
  
Otra cosa que puede hacer con la herramienta de recopilación de PST es impedir que los usuarios creen nuevos archivos PST y cambien los archivos PST existentes que encuentre en la red. Estas capacidades de "bloqueo" le permiten buscar, recopilar e importar un conjunto conocido de archivos PST a Office 365 y evitar la proliferación futura de archivos PST en su organización. 
  
## <a name="how-the-pst-collection-tool-works"></a>Funcionamiento de la herramienta de recopilación de PST

A continuación, se presenta una introducción rápida al proceso de uso de la herramienta de recopilación de PST para buscar, controlar, recopilar y eliminar archivos PST en la organización.
  
![Información general sobre el proceso de la herramienta de recopilación de PST](media/67a29f27-f83c-4f0a-9df4-7ed92d3086fe.png)
  
1. **[Paso 1: buscar archivos PST en la red](#step-1-find-pst-files-on-your-network)** : cuando ejecuta la herramienta para buscar archivos PST, especifica una ubicación, como una unidad organizativa que contiene objetos de Active Directory para equipos cliente y servidor. También puede buscar equipos específicos o recursos compartidos de archivos de red. Al ejecutar la herramienta, se instala un agente de colección "ligero" en los equipos de destino. Este agente busca archivos PST en el equipo de destino y, a continuación, envía información a la herramienta de recopilación de PST sobre cualquier archivo PST que encuentre. La herramienta crea archivos de registro que contienen información sobre los archivos PST que se encontraron en las ubicaciones especificadas. Estos archivos se usan cuando se ejecuta la herramienta en pasos posteriores. 
    
2. **[Paso 2 (opcional): controlar el acceso a los archivos PST](#optional-step-2-control-access-to-pst-files)** : la herramienta crea un objeto de directiva de grupo (GPO) con una configuración que impide que los usuarios creen o cambien archivos PST. Este GPO se aplica a todos los usuarios de su dominio. Este paso opcional ayuda a "bloquear" los archivos PST que se encontraron en el paso 1, de modo que pueda recopilarlos, importarlos y eliminarlos sin tener nuevos archivos PST creados o los archivos PST existentes cambiados. 
    
3. **[Paso 3: copiar los archivos PST en una ubicación de recopilación](#step-3-copy-the-pst-files-to-a-collection-location)** : Esto le permite recopilar los archivos PST en una ubicación para poder importarlos a buzones de correo de Exchange Online con el servicio de importación de Office 365 en el paso 4. Cuando se ejecuta la herramienta en el modo "recopilación", cada agente de recopilación copia los archivos PST del equipo de destino en el que está instalado el agente en la ubicación de la colección. 
    
4. **[Paso 4: importar los archivos PST a Office 365](#step-4-import-the-pst-files-to-office-365)** : una vez que haya copiado los archivos PST en una ubicación, estará listo para importarlos a buzones de correo de Exchange Online. 
    
5. **[Paso 5: eliminar los archivos PST que se encuentran en la red](#step-5-delete-the-pst-files-found-on-your-network)** : después de que los archivos PST que ha encontrado y recopilado se hayan importado a los buzones de Exchange online en Office 365, puede usar la herramienta de recopilación de PST para eliminar los archivos PST de las ubicaciones originales en las que se encontraron en el paso 1. 

## <a name="before-you-begin"></a>Antes de empezar

- Siga estos pasos para descargar la herramienta de recopilación de PST en su equipo local. 
    
    1. [Descargue la herramienta de recopilación de PST](https://aka.ms/pstcollectiontool).
    
    2. En la ventana emergente, haga clic en **Guardar** \> y **Guardar como** para guardar el archivo PSTCollectionTool. zip en una carpeta del equipo local. 
    
    3. Extraiga el archivo PSTCollectionTool. zip en una carpeta del equipo local; el nombre de carpeta predeterminado es PSTCollectionTool.
    
- Para ejecutar la herramienta de recopilación de PST en cualquier modo (buscar, bloquear, copiar o eliminar), debe pertenecer al grupo de administradores de dominio en el dominio de Active Directory. 

## <a name="step-1-find-pst-files-on-your-network"></a>Paso 1: buscar archivos PST en la red

El primer paso consiste en ejecutar la herramienta de recopilación de PST para buscar los archivos PST de la organización. Puede usar la herramienta para buscar los siguientes tipos de ubicaciones. 
  
- Unidades organizativas (OU) en un dominio de Active Directory local. La herramienta busca en todos los equipos que se encuentran en la unidad organizativa especificada. 
    
- Equipos cliente y servidor. La herramienta busca los equipos especificados. 
    
- Recursos compartidos de archivos de red. La herramienta busca los recursos compartidos de archivos de red especificados. 
    
Consulte la descripción del `Locations` parámetro en la tabla del siguiente procedimiento para obtener ejemplos de la sintaxis que se debe usar para cada uno de estos tipos de ubicación. 
  
> [!IMPORTANT]
> Debe ejecutar la herramienta de recopilación de PST en el modo de búsqueda antes de realizar otras acciones, como bloquear, recopilar o eliminar archivos PST. 
  
1. Abra un símbolo del sistema (ejecute como administrador) en el equipo local.
    
2. Vaya a la carpeta PSTCollectionTool (o la carpeta en la que extrajo el archivo PSTCollectionTool. zip).
    
3. Cambie al directorio DataCollectorMaster.
    
4. Ejecute el siguiente comando para buscar los archivos PST en una ubicación especificada.
    
    ```
    DataCollectorMaster.exe -DataSource Pst -Mode Find -JobName <Name> -Locations <Locations to search for PSTs> -LogLocation <Location to store log files> -ConfigurationLocation <Location to store configuration files>
    ```

    En la tabla siguiente se describen los parámetros y los valores necesarios al ejecutar el comando DataCollectorMaster. exe para buscar archivos PST. 
    
    |Parámetro * * * *|****Descripción****|Ejemplos * * * *|
    |:-----|:-----|:-----|
    | `DataSource` <br/> |Especifica el tipo de datos que se va a buscar. Actualmente, puede usar la herramienta de recopilación de PST para buscar archivos PST.  <br/> | `-DataSource Pst` <br/> |
    | `Mode` <br/> |Especifica el tipo de operación que realizará la herramienta. Use el valor `Find` para ubicar los archivos PST en las ubicaciones especificadas. Tenga en cuenta que la herramienta puede buscar y obtener información sobre los archivos PST que están abiertos en los archivos de Outlook y PST que están conectados a los perfiles de Outlook.<br/> | `-Mode Find` <br/> |
    | `JobName` <br/> |Especifica el nombre del trabajo de recopilación de PST. Usará este mismo nombre de trabajo cuando ejecute la herramienta de recopilación de PST para bloquear, recopilar y eliminar los archivos PST que se encuentran al ejecutar la herramienta para buscar archivos PST. El nombre del trabajo también se agregará al registro y a los nombres de archivo de configuración.  <br/> | `-JobName PstSearch1` <br/> |
    | `Locations` <br/> | Especifica una o varias ubicaciones en las que se van a buscar los archivos PST. Si especifica más de una ubicación, use un punto y coma (;) para separar ubicaciones individuales. Asegúrese de envolver los valores individuales de este parámetro con comillas dobles ("").<br/><br/>   Este es el formato de valor de identidad necesario para los tipos de ubicaciones que puede buscar.  <br/><br/>        **Unidades organizativas** : Use el nombre distintivo (DN) para identificar las unidades organizativas; por ejemplo:`"OU=NorthAmerica,OU=NWRegion,OU=ITServices,DC=contoso,DC=com"` <br/> > [!IMPORTANT]> no puede especificar el contenedor equipos integrados (por ejemplo, CN = equipos, DC = Contoso, DC = com ") porque no es una unidad organizativa.<br/> <br/> **Equipos** : Use el DN o el nombre de dominio completo (FQDN) para identificar los equipos cliente y servidor de la red; por ejemplo:  <br/>  DN`"CN=FILESERVER01,CN=Computers,DC=contoso,DC=com"` <br/>  O bien  <br/>  CUALIFICA`"FILESERVER01.contoso.com"` <br/><br/>  **Recursos** compartidos de archivos de red: Use un nombre UNC para identificar recursos compartidos de archivos de red; por ejemplo,`"\\FILESERVER02\Users"` <br/> | `-Locations "CN=FILESERVER01,CN=Computers,DC=contoso,DC=com";"CN=FILESERVER02,CN=Computers,DC=contoso,DC=com"` <br/> |
    | `LogLocation` <br/> |Especifica la carpeta en la que se copiarán los archivos de registro. Si la carpeta no existe, se creará al ejecutar la herramienta.  <br/> | `-LogLocation "c:\users\admin\desktop\PSTCollection"` <br/> |
    | `ConfigurationLocation` <br/> |Especifica la carpeta en la que se copiará el archivo de configuración. Xml. Este archivo contiene información sobre cada archivo PST que se encuentra al ejecutar la herramienta. Este archivo se usará al ejecutar la herramienta en el paso 3 para copiar los archivos PST que se encuentran.  <br/> | `-ConfigurationLocation "c:\users\admin\desktop\PSTCollection\Configuration"` <br/> |
    | `ExcludedLocations` <br/> |Este parámetro opcional especifica las ubicaciones que se deben omitir durante una operación de búsqueda. Puede excluir unidades organizativas específicas, equipos y recursos compartidos de archivos de red. Por ejemplo, podría excluir equipos configurados como un equipo configurado como SQL Server (u otros tipos de servidores de aplicaciones), que los usuarios no tienen acceso a. Si especifica más de una ubicación para excluir, use un punto y coma (;) para separar ubicaciones individuales. Asegúrese de envolver los valores individuales de este parámetro con comillas dobles ("").  <br/> | `-ExcludedLocations "SQLSERVER01.contoso.com"` <br/> |
    | `ForceRestart` <br/> |Este modificador opcional permite ejecutar la herramienta en el modo Find para un trabajo de colección de PST existente. Cuando use el `ForceRestart` modificador, se descartarán los resultados de la operación buscar anterior para el trabajo, y la herramienta volverá a examinar las ubicaciones especificadas y creará nuevos archivos de registro y de configuración.<br/> | `-ForceRestart` <br/> |
   
    A continuación, se muestra un ejemplo de la sintaxis del comando DataCollectorMaster. exe con valores reales para cada parámetro:
    
    ```
    DataCollectorMaster.exe -DataSource Pst -Mode Find -JobName PstSearch1 -Locations "CN=FILESERVER01,CN=Computers,DC=contoso,DC=com";"CN=FILESERVER02,CN=Computers,DC=contoso,DC=com" -LogLocation "c:\users\admin\desktop\PSTCollection" -ConfigurationLocation "c:\users\admin\desktop\PSTCollection\Configuration"
    ```

    Después de ejecutar el comando, se muestran los mensajes de estado detallados que muestran el progreso de la búsqueda de archivos PST en las ubicaciones especificadas. Después de un rato, un mensaje de estado final muestra el número total de archivos PST encontrados, si el trabajo se ha completado y si se ha producido algún error. Los mismos mensajes de estado se copian en el archivo. log.
    
### <a name="results-of-running-datacollectormasterexe-in-the-find-mode"></a>Resultados de ejecutar DataCollectorMaster. exe en el modo de búsqueda

Después de ejecutar correctamente la herramienta de recopilación de PST en el modo de búsqueda, se crean y almacenan los siguientes archivos en `LogLocation` las `ConfigurationLocation` carpetas especificadas por los parámetros y. 
  
- **\<JobName\>__ buscar\<DateTimeStamp\>. log** : el archivo de registro contiene los mensajes de estado mostrados. Este archivo se crea en la carpeta especificada por el `LogLocation` parámetro. 
    
- **\<JobName\>__ encontrar\<DateTimeStamp\>. csv** : el archivo CSV contiene una fila por cada archivo pst encontrado. La información de cada PST incluye el equipo en el que se encontró el archivo PST, la ubicación completa de la ruta de acceso al archivo PST, el propietario del archivo PST y el tamaño (en kilobytes, KB) del archivo PST. Este archivo se crea en la carpeta especificada por el `LogLocation` parámetro. 
    
    > [!TIP]
    > Use la herramienta autoSuma en Excel para calcular el tamaño total (en KB) de todos los archivos PST que aparecen en el archivo CSV. A continuación, puede usar una calculadora de conversión para convertir el tamaño total en megabytes (MB) o en gigabytes (GB). 
  
- **\<JobName\>__ Find\<DateTimeStamp\>. XML** : el archivo XML contiene información sobre los valores de parámetro que se usan cuando se ejecutó la herramienta en el modo de búsqueda. Este archivo también contiene información sobre cada archivo PST encontrado. Los datos de este archivo se usan al ejecutar volver a ejecutar la herramienta para que el mismo trabajo bloquee, recopile o elimine los archivos PST que se encontraron. Este archivo se crea en la carpeta especificada por el `ConfigurationLocation` parámetro. 
    
    > [!IMPORTANT]
    > No cambie el nombre de este archivo, cámbielo ni muévalo. Se usa en la herramienta de recopilación de PST al volver a ejecutar la herramienta en el modo bloquear, copiar o eliminar para el mismo trabajo. 

## <a name="optional-step-2-control-access-to-pst-files"></a>Opcional Paso 2: controlar el acceso a los archivos PST

Este paso opcional permite "bloquear" los archivos PST encontrados en el paso 1 para poder recopilar e importar un conjunto conocido de archivos PST a Office 365. Cuando ejecuta la herramienta de recopilación de PST en el modo de bloqueo, ocurrirán las siguientes situaciones: 
  
- La herramienta crea un objeto de directiva de grupo (GPO) denominado *controles de uso de PST* . Este GPO está vinculado a su dominio y se aplica a todos los usuarios autenticados de la organización. 
    
- El GPO de controles de uso de PST crea configuraciones del registro en los equipos de la organización. Según el parámetro que use, puede crear una configuración del registro para evitar que los usuarios creen nuevos archivos PST y una configuración del registro que evite que los usuarios cambien los archivos PST existentes.
    
> [!NOTE]
> Si el control de acceso a los archivos PST es demasiado disruptivo para su organización, puede considerar omitir este paso y realizar el paso 3 para copiar los archivos PST en una ubicación central. A continuación, puede repetir el paso 1 para el mismo trabajo (mediante `ForceRestart` el parámetro) para buscar archivos PST adicionales que se crearon después de copiar los archivos PST en la ubicación de la colección. Si se encuentran nuevos archivos PST, puede copiarlos en la ubicación de la colección. Cuando se usa el `ForceRestart` parámetro al volver a ejecutar la herramienta en el modo de búsqueda, se descartan los resultados de la operación buscar anterior de un trabajo, y la herramienta volverá a examinar las ubicaciones especificadas. 

Para bloquear el acceso a los archivos PST:

1. Abra un símbolo del sistema (ejecute como administrador) en el equipo local.
    
2. Vaya al directorio donde descargó la herramienta de recopilación de PST.
    
3. Ejecute el siguiente comando para bloquear el acceso a los archivos PST encontrados en el paso 1.

    ```
    DataCollectorMaster.exe -DataSource Pst -Mode Block -JobName <Name of job from Step 1> -ConfigurationLocation <Location of configuration files from Step 1> -BlockChangesToFiles -BlockNewFiles
    ```

    En la tabla siguiente se describen los parámetros y los valores necesarios al ejecutar el comando DataCollectorMaster. exe para bloquear la creación y modificación de los archivos PST. 
    
    |Parámetro * * * *|****Descripción****|Ejemplos * * * *|
    |:-----|:-----|:-----|
    | `DataSource` <br/> |Especifica el tipo de datos que se va a buscar. Actualmente, puede usar la herramienta de recopilación de PST para buscar archivos PST.  <br/> | `-DataSource Pst` <br/> |
    | `Mode` <br/> |Especifica el tipo de operación que realizará la herramienta. Use el valor `Block` para evitar que los usuarios creen nuevos archivos PST y realicen cambios en los archivos PST existentes.<br/> | `-Mode Block` <br/> |
    | `JobName` <br/> |Especifica el nombre de un trabajo de colección de archivos PST existente. Debe usar el mismo nombre de trabajo que usó al ejecutar la herramienta en el modo buscar en el paso 1. Este nombre de trabajo también se agrega al nombre del archivo de registro que se crea al ejecutar la herramienta en el modo de bloqueo.  <br/> | `-JobName PstSearch1` <br/> |
    | `ConfigurationLocation` <br/> |Especifica que la carpeta contiene el archivo de configuración. XML que se creó al ejecutar la herramienta en el modo de búsqueda. Use el mismo valor que usó para este parámetro en el paso 1.  <br/> | `-ConfigurationLocation "c:\users\admin\desktop\PSTCollection\Configuration"` <br/> |
    | `LogLocation` <br/> |Especifica la carpeta en la que se copiará el archivo de registro para la operación de bloqueo. Se trata de un parámetro opcional. Si no lo incluye, el archivo de registro se copiará en la carpeta donde haya descargado la herramienta de recopilación de PST. Considere la posibilidad de usar la misma ubicación de registro que usó cuando ejecutó la herramienta en el modo de búsqueda en el paso 1 para que todos los archivos de registro se guarden en la misma carpeta.  <br/> | `-LogLocation "c:\users\admin\desktop\PSTCollection"` <br/> |
    | `BlockChangesToFiles` <br/> |Use este modificador para evitar que los usuarios cambien un archivo PST. Cuando se usa este modificador, se crea la siguiente entrada del `HKEY_CURRENT_USER\Software\Policies\Microsoft\Office\<version>\Outlook\PST\PstDisableGrow` registro: y el valor de los datos se establece en 1. Esta configuración del registro se crea en los equipos de la organización por el GPO que se crea al ejecutar la herramienta de recopilación de PST en el modo de bloqueo.<br/> | `-BlockChangesToFiles` <br/> |
    | `BlockNewFiles` <br/> |Use este modificador para evitar que los usuarios creen nuevos archivos PST, abran e importen archivos PST en Outlook y exporten archivos PST desde Outlook. Cuando se usa este modificador, se crea la siguiente entrada del `HKEY_CURRENT_USER\Software\Policies\Microsoft\Office\<version>\Outlook\DisablePst` registro: y el valor de los datos se establece en 1. Esta configuración del registro se crea en los equipos de la organización por el GPO que se crea al ejecutar la herramienta de recopilación de PST en el modo de bloqueo.<br/> | `-BlockNewFiles` <br/> |
   
    A continuación, se muestra un ejemplo de la sintaxis del comando DataCollectorMaster. exe con valores reales para cada parámetro:

    ```
    DataCollectorMaster.exe -DataSource Pst -Mode Block -JobName PstSearch1 -ConfigurationLocation "c:\users\admin\desktop\PSTCollection\Configuration" -LogLocation "c:\users\admin\desktop\PSTCollection" -BlockChangesToFiles -BlockNewFiles
    ```
    
    Se le pedirá que confirme que desea bloquear los nuevos archivos PST o los cambios en los archivos PST existentes. Después de confirmar que desea continuar y que el comando se ejecuta correctamente, se muestra un mensaje que indica que se ha creado un nuevo GPO denominado "controles de uso de PST".
    
## <a name="step-3-copy-the-pst-files-to-a-collection-location"></a>Paso 3: copiar los archivos PST en una ubicación de colección

El paso siguiente es copiar los archivos PST que se encuentran cuando se ejecutó la herramienta de recopilación de PST en el modo de búsqueda. Esto le permite recopilar los archivos PST en una ubicación para poder importarlos más adelante a Office 365. Antes de copiar los archivos PST en la ubicación de recopilación, considere la posibilidad de determinar la cantidad total de espacio de almacenamiento que se requiere. Puede hacerlo con el archivo CSV que se creó en el paso 1 para calcular el tamaño total de todos los archivos PST.
  
> [!NOTE]
> Una vez que haya importado los archivos PST a Office 365 y los haya eliminado de su ubicación original, es posible que desee eliminarlos de la ubicación de recopilación en la que los copió en este paso. 
  
1. Abra un símbolo del sistema (ejecute como administrador) en el equipo local.
    
2. Vaya al directorio donde descargó la herramienta de recopilación de PST.
    
3. Ejecute el siguiente comando para copiar los archivos PST en una ubicación especificada.
    
    ```
    DataCollectorMaster.exe -DataSource Pst -Mode Collect -JobName <Name of job from Step 1> -Locations <same locations from Step 1> -ConfigurationLocation <Location of configuration files from Step 1> -CopyLocation <Location to copy PST files to>
    ```

    En la tabla siguiente se describen los parámetros y los valores necesarios al ejecutar el comando DataCollectorMaster. exe para copiar los archivos PST. 
    
    |Parámetro * * * *|****Descripción****|Ejemplos * * * *|
    |:-----|:-----|:-----|
    | `DataSource` <br/> |Especifica el tipo de datos que se va a buscar. Actualmente, puede usar la herramienta de recopilación de PST para buscar archivos PST.  <br/> | `-DataSource Pst` <br/> |
    | `Mode` <br/> |Especifica el tipo de operación que realizará la herramienta. Use el valor `Collect` para copiar los archivos PST que se encontraron al ejecutar la herramienta en el modo de búsqueda. Tenga en cuenta que la herramienta puede copiar los archivos PST que están abiertos en Outlook y copiar los archivos PST que están conectados a los perfiles de Outlook.<br/> | `-Mode Collect` <br/> |
    | `JobName` <br/> |Especifica el nombre de un trabajo de colección de archivos PST existente. Debe usar el mismo nombre de trabajo que usó al ejecutar la herramienta en el modo buscar en el paso 1. Este nombre de trabajo también se agrega al nombre del archivo de registro que se crea al ejecutar la herramienta en el modo de recopilación.  <br/> | `-JobName PstSearch1` <br/> |
    | `Locations` <br/> |Use el mismo valor que usó para el parámetro `Locations` en el paso 1. Tiene que incluir este parámetro cuando ejecuta la herramienta en el modo de recopilación si desea volver a ejecutar la herramienta para eliminar los archivos PST de la ubicación de origen en el paso 5.<br/> | `-Locations "CN=FILESERVER01,CN=Computers,DC=contoso,DC=com"; "CN=FILESERVER02,CN=Computers,DC=contoso,DC=com"` <br/> |
    | `ConfigurationLocation` <br/> |Especifica la carpeta que contiene el archivo de configuración. XML que se creó al ejecutar la herramienta en el modo de búsqueda. Use el mismo valor que usó para este parámetro en el paso 1.  <br/> | `-ConfigurationLocation "c:\users\admin\desktop \PSTCollection\Configuration"` <br/> |
    | `CopyLocation` <br/> |Especifica la ubicación de la colección donde desea copiar los archivos PST. Puede copiar archivos en un servidor de archivos, un recurso compartido de archivos de red o una unidad de disco duro. La ubicación debe existir antes de ejecutar la herramienta en el modo de recopilación. La herramienta no crea la ubicación y devolverá un error en el que se indica que no existe.  <br/> Además, tiene que escribir permisos en la ubicación de la colección especificada por este parámetro.  <br/> | `-CopyLocation "\\FILESERVER03\PSTs"` <br/> |
    | `LogLocation` <br/> |Especifica la carpeta en la que se copiará el archivo de registro del modo de recopilación. Se trata de un parámetro opcional. Si no lo incluye, el archivo de registro se copiará en la carpeta donde haya descargado la herramienta de recopilación de PST. Considere la posibilidad de usar la misma ubicación de registro que usó cuando ejecutó la herramienta en el modo de búsqueda en el paso 1 para que todos los archivos de registro se guarden en la misma carpeta.  <br/> | `-LogLocation "c:\users\admin\desktop\PSTCollection"` <br/> |
    | `ForceRestart` <br/> |Este modificador opcional permite volver a ejecutar la herramienta en modo de colección para un trabajo de colección de archivos PST existente. Si anteriormente ejecutó la herramienta en el modo de recopilación, pero luego ejecutó la herramienta de nuevo en el modo `ForceRestart` de búsqueda con el conmutador para volver a examinar ubicaciones de archivos PST, puede usar este modificador para volver a ejecutar la herramienta en el modo de recopilación y volver a copiar los archivos PST allí donde se encontraban cuando el volver a examinar las ubicaciones. Cuando se usa `ForceRestart` el modo de alternancia en la colección, la herramienta pasa por alto las operaciones de recopilación anteriores e intenta copiar los archivos PST desde cero.<br/> | `-ForceRestart` <br/> |
   
    A continuación, se muestra un ejemplo de la sintaxis de la herramienta DataCollectorMaster. exe con valores reales para cada parámetro:
    
    ```
    DataCollectorMaster.exe -DataSource Pst -Mode Collect -JobName PstSearch1 -Locations "CN=FILESERVER01,CN=Computers,DC=contoso,DC=com";"CN=FILESERVER02,CN=Computers,DC=contoso,DC=com" -ConfigurationLocation "c:\users\admin\desktop\PSTCollection\Configuration" -CopyLocation "\\FILESERVER03\PSTs" -LogLocation "c:\users\admin\desktop\PSTCollection"
    ```

    Después de ejecutar el comando, se muestran los mensajes de estado detallados que muestran el progreso de la recopilación de los archivos PST encontrados en el paso 1. Después de un rato, un mensaje de estado final muestra si hubo errores y la ubicación en la que se ha copiado el registro. Los mismos mensajes de estado se copian en el archivo. log.
    
### <a name="results-of-running-datacollectormasterexe-in-the-collect-mode"></a>Resultados de ejecutar DataCollectorMaster. exe en el modo de recopilación

Una vez que se haya ejecutado correctamente DataCollectorMaster. exe en el modo Collect, se crearán y almacenarán los siguientes archivos en `LogLocation` las `ConfigurationLocation` carpetas especificadas por los parámetros y. 
  
- **\<JobName\>__ Collect\<DateTimeStamp\>. log** : el archivo de registro contiene los mensajes de estado mostrados. Este archivo se crea en la carpeta especificada por el `LogLocation` parámetro. 
    
- **\<JobName\>__\<recopilar\>DateTimeStamp. XML** : el archivo XML solo contiene información sobre los valores de parámetro que usa la herramienta se ejecutó en el modo de recopilación. Los datos de este archivo se usan cuando ejecuta volver a ejecutar la herramienta DataCollectorMaster. exe para eliminar archivos PST; Vea el [paso 5](#step-5-delete-the-pst-files-found-on-your-network).
    

## <a name="step-4-import-the-pst-files-to-office-365"></a>Paso 4: importar los archivos PST a Office 365

Una vez que haya recopilado los archivos PST que se encuentran en el paso 1, el siguiente paso consiste en importarlos a los buzones en Office 365. Como parte o el proceso de importación, tendrá que crear un archivo de asignación CSV que contenga una fila de cada archivo PST que desee importar. La información de cada fila especifica el nombre del archivo PST, la dirección de correo del usuario y si desea importar el archivo PST en el buzón principal o de archivo del usuario. Use la información del **JobName\>_Find_\<DateTimeStamp. csv** File (que se creó en el paso) 1 para ayudarle a crear el archivo de asignación CSV. 
  
Para obtener instrucciones paso a paso para importar archivos PST a Office 365, consulte uno de los siguientes temas:
  
- [Usar la carga en la red para importar archivos PST en Office 365](use-network-upload-to-import-pst-files.md)
    
- [Usar el envío de unidades para importar los archivos PST a Office 365](use-drive-shipping-to-import-pst-files-to-office-365.md)
    

## <a name="step-5-delete-the-pst-files-found-on-your-network"></a>Paso 5: eliminar los archivos PST encontrados en la red

Una vez que los archivos PST que ha encontrado y recopilado se han importado a los buzones de Exchange online en Office 365, puede usar la herramienta de recopilación de PST para eliminar los archivos PST de las ubicaciones originales de origen donde se encontraron en el paso 1. 
  
1. Abra un símbolo del sistema (ejecute como administrador) en el equipo local.
    
2. Vaya al directorio donde descargó la herramienta de recopilación de PST.
    
3. Ejecute el siguiente comando para eliminar los archivos PST.

    ```
    DataCollectorMaster.exe -DataSource Pst -Mode Delete -JobName <Name of job from Step 1> -ConfigurationLocation <Location of configuration files from Step 1> -CopyLocation <Location to copy PST files to>
    ```

    En la tabla siguiente se describen los parámetros y los valores necesarios al ejecutar el comando DataCollectorMaster. exe para eliminar archivos PST. 
    
    |Parámetro * * * *|****Descripción****|Ejemplos * * * *|
    |:-----|:-----|:-----|
    | `DataSource` <br/> |Especifica el tipo de datos que se va a buscar. Actualmente, puede usar la herramienta de recopilación de PST para buscar archivos PST. ![separador](media/b078d05c-3aee-4b9f-8805-6a8a9d8970ee.png)           <br/> | `-DataSource Pst` <br/> |
    | `Mode` <br/> |Especifica el tipo de operación que realizará la herramienta. Use el valor `Delete` para eliminar los archivos PST que se encontraron al ejecutar la herramienta en el modo de búsqueda.<br/> | `-Mode Delete` <br/> |
    | `JobName` <br/> |Especifica el nombre de un trabajo de colección de archivos PST existente. Debe usar el mismo nombre de trabajo que usó al ejecutar la herramienta en el modo de búsqueda y el modo de recopilación en el paso 1 y el paso 3. Este nombre de trabajo también se agrega al nombre del archivo de registro que se crea al ejecutar la herramienta en el modo de eliminación.  <br/> | `-JobName PstSearch1` <br/> |
    | `ConfigurationLocation` <br/> |Especifica la carpeta que contiene el archivo de configuración. XML que se creó al ejecutar la herramienta en el modo de recopilación. Use el mismo valor que usó para este parámetro en el paso 3.  <br/> | `-ConfigurationLocation "c:\users\admin\ desktop\PSTCollection\Configuration"` <br/> |
    | `LogLocation` <br/> |Especifica la carpeta en la que se copiará el archivo de registro del modo de eliminación. Se trata de un parámetro opcional. Si no lo incluye, el archivo de registro se copiará en la carpeta donde haya descargado la herramienta de recopilación de PST. Considere la posibilidad de usar la misma ubicación de registro que usó cuando ejecutó la herramienta en los modos buscar y recopilar en el paso 1 y el paso 3 para que todos los archivos de registro se guarden en la misma carpeta.  <br/> | `-LogLocation "c:\users\admin\desktop\PSTCollection"` <br/> |
    | `ForceRestart` <br/> |Este modificador opcional permite volver a ejecutar la herramienta en el modo de eliminación para un trabajo de colección de PST existente. Si anteriormente ejecutó la herramienta en el modo de eliminación, pero después ejecutó la herramienta de nuevo en el modo `ForceRestart` de búsqueda con el conmutador para volver a examinar ubicaciones de archivos PST, puede usar este modificador para volver a ejecutar la herramienta en modo de eliminación y eliminar los archivos PST que se encontraron cuando su reactivación nned las ubicaciones. Cuando se usa `ForceRestart` el modificador en el modo de eliminación, la herramienta pasa por alto las operaciones de eliminación anteriores y vuelve a intentar eliminar los archivos PST.<br/> | `-ForceRestart` <br/> 

    A continuación, se muestra un ejemplo de la sintaxis de la herramienta DataCollectorMaster. exe con valores reales para cada parámetro:
    
    ```
    DataCollectorMaster.exe -DataSource Pst -Mode Delete -JobName PstSearch1 -ConfigurationLocation "c:\users\admin\desktop\PSTCollection\Configuration" -LogLocation "c:\users\admin\desktop\PSTCollection"
    ```
   
    Después de ejecutar el comando, se muestran los mensajes de estado detallados que muestran el progreso de la eliminación de los archivos PST encontrados en el paso 1 y recopilados en el paso 3. Después de un rato, un mensaje de estado final muestra si hubo errores y la ubicación en la que se ha copiado el registro. Los mismos mensajes de estado se copian en el archivo. log.
    
### <a name="results-of-running-datacollectormasterexe-in-the-delete-mode"></a>Resultados de ejecutar DataCollectorMaster. exe en el modo de eliminación

Después de ejecutar correctamente DataCollectorMaster. exe en el modo de eliminación, se crean y almacenan los siguientes archivos en la carpeta especificada `LogLocation` por `ConfigurationLocation` los parámetros y. 
  
- **\<JobName\>__ Delete\<DateTimeStamp\>. log** : el archivo de registro contiene los mensajes de estado mostrados. Este archivo se crea en la carpeta especificada por el `LogLocation` parámetro. 
    
- **\<JobName\>__ Delete\<DateTimeStamp\>. XML** : el archivo XML solo contiene información sobre los valores de parámetro que usa la herramienta se ejecutó en el modo de eliminación. También muestra el nombre y la ruta de acceso del archivo de cada archivo PST que se eliminó. Este archivo se crea en la carpeta especificada por el `ConfigurationLocation` parámetro. 
