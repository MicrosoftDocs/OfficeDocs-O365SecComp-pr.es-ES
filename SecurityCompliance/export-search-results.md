---
title: Exportar resultados de la búsqueda de contenido
ms.author: markjjo
author: markjjo
manager: laurawi
ms.audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.CustomizeExport
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: ed48d448-3714-4c42-85f5-10f75f6a4278
description: 'ExPorte los resultados de búsqueda de una búsqueda de contenido en el centro de seguridad & cumplimiento a un equipo local. Los resultados de correo electrónico se exportan como archivos PST. El contenido de SharePoint y los sitios de OneDrive para la empresa se exportan como documentos de Office nativos. '
ms.openlocfilehash: f20ad17ba4573485199d72a260598e77bd224ece
ms.sourcegitcommit: e7a776a04ef6ed5e287a33cfdc36aa2d72862b55
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/29/2019
ms.locfileid: "31000473"
---
# <a name="export-content-search-results"></a>Exportar resultados de la búsqueda de contenido

Después de que una búsqueda de contenido se haya ejecutado correctamente, puede exportar los resultados de la búsqueda a un equipo local. Cuando exporta los resultados de correo electrónico, estos se descargan en su equipo como archivos PST. Al exportar contenido de sitios de SharePoint y OneDrive para la empresa, se exportan copias de documentos nativos de Office. Existen documentos e informes adicionales que se incluyen con los resultados de búsqueda exportados.
  
Además, los mensajes de correo electrónico cifrados con RMS que se incluyan en los resultados de una búsqueda de contenido se descifrarán cuando los exporte (como mensajes individuales). Esta capacidad de descifrado está habilitada de forma predeterminada para los miembros del grupo de roles eDiscovery Manager. Esto se debe a que el rol de administración desCifrar RMS se asigna a este grupo de roles. Consulte la sección [More Information](#more-information) para obtener información detallada sobre el descifrado de RMS al exportar resultados de búsqueda. 
  
Exportar los resultados de una búsqueda de contenido implica preparar los resultados y, a continuación, descargarlos en un equipo local.
  
## <a name="before-you-begin"></a>Antes de empezar

- Para exportar los resultados de la búsqueda, debe tener asignado el rol de administración exportar en el centro de seguridad & cumplimiento. Este rol se asigna al grupo de roles de administrador de exhibición de documentos electrónicos integrado. No se asigna de forma predeterminada al grupo de roles de administración de la organización. Para obtener más información, consulte [asignar permisos de exhibición](assign-ediscovery-permissions.md)de documentos electrónicos.
    
- El equipo que use para exportar los resultados de búsqueda debe cumplir los siguientes requisitos del sistema:
    
  - Versiones de 32 o 64 bits de Windows 7 y versiones posteriores
    
  - Microsoft .NET Framework 4,7
    
  - Un explorador compatible:
    
     - Microsoft Edge
    
        O
    
     - Microsoft Internet Explorer 10 y versiones posteriores
    
    **Nota:** Microsoft no fabrica extensiones de terceros o complementos para aplicaciones ClickOnce. No se admite la exportación de resultados de búsqueda con un explorador no compatible con extensiones de terceros o complementos. 
    
- Cuando descargue los resultados de la búsqueda (descritos en el paso 2), puede aumentar la velocidad de descarga configurando una configuración del registro de Windows en el equipo que use para exportar los resultados de la búsqueda. Para obtener más información, consulte [aumentar la velocidad de descarga al exportar resultados de la búsqueda de exhibición de documentos electrónicos de Office 365](increase-download-speeds-when-exporting-ediscovery-results.md).
    
- Cuando se exportan los resultados de búsqueda, los datos se almacenan temporalmente en una ubicación de almacenamiento de Microsoft Azure única en la nube de Microsoft antes de descargarlos en el equipo local. asegúrese de que su organización puede conectarse al extremo en Azure, que es ** \*. blob.core.windows.net** (el carácter comodín representa un identificador único para la exportación). Los datos de los resultados de la búsqueda se eliminan de la ubicación de almacenamiento de Azure dos semanas después de su creación. 
    
- Si su organización usa un servidor proxy para comunicarse con Internet, debe definir la configuración del servidor proxy en el equipo que use para exportar los resultados de la búsqueda (para que la herramienta de exportación pueda ser autenticada por el servidor proxy). Para ello, abra el archivo *Machine. config* en la ubicación que coincida con su versión de Windows. 
    
  - **32 bits** - `%windir%\Microsoft.NET\Framework\[version]\Config\machine.config`
    
  - **64 bits** - `%windir%\Microsoft.NET\Framework64\[version]\Config\machine.config`
    
    Agregue las líneas siguientes al archivo *Machine. config* en algún lugar entre `<configuration>` las `</configuration>` etiquetas y. Asegúrese de reemplazar `ProxyServer` y `Port` con los valores correctos para su organización; por ejemplo, `proxy01.contoso.com:80` . 
    
    ```
    <system.net>
       <defaultProxy enabled="true" useDefaultCredentials="true">
         <proxy proxyaddress="http://ProxyServer :Port " 
                usesystemdefault="False" 
                bypassonlocal="True" 
                autoDetect="False" />
       </defaultProxy>
    </system.net>
    ```
    
## <a name="step-1-prepare-search-results-for-export"></a>Paso 1: Preparar los resultados de búsqueda para la exportación

El primer paso es preparar los resultados de búsqueda para la exportación. Al preparar los resultados, se cargan en una ubicación de almacenamiento de Azure en la nube de Microsoft. Tenga en cuenta que el contenido de los buzones de correo y los sitios se carga a una tasa máxima de 2 GB por hora.
  
1. Vaya a [https://compliance.microsoft.com](https://compliance.microsoft.com).
    
2. Inicie sesión en Office 365 con su cuenta profesional o educativa.
    
3. En el panel izquierdo del centro de seguridad & cumplimiento, haga clic en buscar **contenido**de **búsqueda** \> .
    
4. En la página **búsqueda de contenido** , seleccione una búsqueda. 
    
5. En el panel de detalles, en **Exportar resultados a un equipo**, haga clic en **Iniciar la exportación**.
    
    > [!NOTE]
    > Si los resultados de una búsqueda son de hace más de 7 días, se le solicitará que actualice los resultados de búsqueda. Si esto ocurre, cancele la exportación, haga clic en **Actualizar los resultados de búsqueda** en el panel de detalles para la búsqueda seleccionada y, a continuación, inicie la exportación de nuevo después de que se actualicen los resultados.  
  
6. En la página **exportar los resultados de búsqueda** , en **Opciones de salida**, elija una de las siguientes opciones:
    
    - Todos los elementos, excluidos los que tienen un formato no reconocido, están cifrados o no se indizaron por otros motivos
    
    - Todos los elementos, incluidos los que tienen un formato no reconocido, están cifrados o no se indizaron por otros motivos.
    
    - Solo los elementos que tienen un formato no reconocido, están cifrados o no se indizaron por otros motivos
    
    Vea la sección [más información](#more-information) para obtener una descripción de cómo se exportan los elementos indizados parcialmente. Para obtener más información acerca de los elementos parcialmente indizados, vea [elementos parcialmente indizados en la búsqueda de contenido](partially-indexed-items-in-content-search.md).
    
7. En **exportar contenido de Exchange como**, elija una de las siguientes opciones:
    
    - **Un archivo pst para cada buzón** : exporta un archivo pst para cada buzón de usuario que contiene los resultados de la búsqueda. Los resultados del buzón de archivo del usuario se incluyen en el mismo archivo PST. Tenga en cuenta que esta opción reproduce la estructura de carpetas del buzón de correo de origen. 
    
    - **Un archivo pst que contiene todos los mensajes** : exporta un único archivo pst (denominado *Exchange. pst* ) que contiene los resultados de búsqueda de todos los buzones de origen incluidos en la búsqueda. Tenga en cuenta que esta opción reproduce la estructura de carpetas del buzón para cada mensaje. 
    
    - Un **archivo pst que contiene todos los mensajes en una sola carpeta** : exporta los resultados de la búsqueda a un único archivo pst donde todos los mensajes se encuentran en una sola carpeta de nivel superior. Esta opción permite a los revisores revisar los elementos en orden cronológico (los elementos se ordenan por fecha de envío) sin tener que navegar por la estructura de carpetas del buzón original para cada elemento. 
    
    - **Mensajes individuales** : exporta los resultados de búsqueda como mensajes de correo electrónico individuales, con el formato. msg. Si selecciona esta opción, los resultados de la búsqueda de correo electrónico se exportan a una carpeta en el sistema de archivos. La ruta de acceso de la carpeta para los mensajes individuales es la misma que se usa si se exportaron los resultados a archivos PST. 
    
      > [!IMPORTANT]
      > Para descifrar los mensajes cifrados con RMS cuando se exportan, debe exportar los resultados de la búsqueda de correo electrónico como mensajes individuales. Los mensajes cifrados seguirán cifrados Si exporta los resultados de la búsqueda como un archivo PST. 
  
8. Haga clic en la casilla **Habilitar** desduplicación para excluir los mensajes duplicados. Esta opción solo aparece si los orígenes de contenido de la búsqueda incluyen buzones de correo de Exchange o carpetas públicas. 
    
    Si selecciona esta opción, solo se exportará una copia de un mensaje incluso si se encuentran varias copias del mismo mensaje en los buzones en los que se realizó la búsqueda. El informe de resultados de la exportación (Results. csv) contendrá una fila por cada copia de un mensaje duplicado, de modo que pueda identificar los buzones (o carpetas públicas) que contienen una copia del mensaje duplicado. Para obtener más información acerca de la desduplicación y cómo se identifican los elementos duplicados, vea desduplicación [en resultados de la búsqueda de exhibición](de-duplication-in-ediscovery-search-results.md)de documentos electrónicos.
    
9. Haga clic en la casilla **incluir versiones de los documentos de SharePoint** para exportar todas las versiones de los documentos de SharePoint. Esta opción solo aparece si los orígenes de contenido de la búsqueda incluyen sitios de SharePoint o de OneDrive para la empresa. 
    
10. Haga clic en la casilla **exportar archivos en una carpeta comprimida (en zip)** para exportar los resultados de la búsqueda a carpetas comprimidas. Esta opción solo está disponible cuando elige exportar elementos de Exchange como mensajes individuales y cuando los resultados de la búsqueda incluyen documentos de SharePoint o de OneDrive. Esta opción se usa principalmente para evitar el límite de caracteres de 260 en los nombres de ruta de acceso de los archivos de Windows cuando se exportan elementos. Consulte los "nombres de archivo de los elementos exportados" en la sección [más información](#more-information) . 
    
11. Haga clic en **Iniciar la exportación**.
    
    Los resultados de la búsqueda se preparan para la descarga, lo que significa que se cargan en la ubicación de almacenamiento de Azure en la nube de Microsoft. Cuando los resultados de búsqueda están listos para la descarga, el vínculo **Descargar resultados exportados** se muestra en **Exportar resultados a un equipo** en el panel de detalles. 
  
## <a name="step-2-download-the-search-results"></a>Paso 2: Descargar los resultados de búsqueda

El siguiente paso es descargar los resultados de la búsqueda desde la ubicación de Azure Storage a su equipo local.
  
Como se ha explicado anteriormente, puede aumentar la velocidad de descarga configurando una configuración del registro de Windows en el equipo que use para exportar los resultados de la búsqueda. Para obtener más información, consulte [aumentar la velocidad de descarga al exportar resultados de la búsqueda de exhibición de documentos electrónicos de Office 365](increase-download-speeds-when-exporting-ediscovery-results.md).
  
1. En el panel de detalles de la búsqueda para la que inició la exportación, en **Exportar resultados a un equipo**, haga clic en **Descargar resultados exportados**.
    
    La ventana **Descargar resultados** exportados se muestra y contiene la siguiente información sobre los resultados de la búsqueda que se descargarán en el equipo. 
    
    - El número de elementos que se descargarán.
    
    - El tamaño total estimado de los elementos que se descargarán.
    
    - Si los elementos indexados o sin indexar se exportarán. Los elementos sin indexar son elementos que tienen un formato reconocido, están cifrados o no se indexaron por otros motivos. Para obtener más información, consulte [Unindexed items in Content Search](partially-indexed-items-in-content-search.md).
    
    - Si las versiones de los documentos de SharePoint se descargarán o no.
    
    - El estado del proceso de preparación de la exportación. Puede iniciar la descarga de los resultados de búsqueda incluso si la preparación de los datos no está completa.
    
2. En **Clave de exportación**, haga clic en **Copiar al Portapapeles**. Esta clave se usará para descargar los resultados de la búsqueda en el paso 5.
    
    > [!NOTE]
    > Dado que cualquier persona puede instalar e iniciar la herramienta de exportación de exhibición de documentos electrónicos y después usar esta clave para descargar los resultados de búsqueda, asegúrese de tomar precauciones para proteger esta clave como protegería las contraseñas u otra información relacionada con la seguridad.  
  
3. Haga clic en **Descargar resultados**.
    
4. Si se le pide que instale la **herramienta de exportación MicrosoftOffice 365 eDiscovery**, haga clic en **instalar**.
    
5. En la **Herramienta de exportación de exhibición de documentos electrónicos**, pegue la clave de exportación que ha copiado en el paso 2 en el cuadro correspondiente.
    
6. Haga clic en **Examinar** para especificar la ubicación en la que desea descargar los archivos de los resultados de la búsqueda. 
    
    > [!NOTE]
    > Debido a la gran cantidad de actividad de disco (lecturas y escrituras), debe descargar los resultados de la búsqueda en una unidad de disco local; no descárguelos en una unidad de red asignada ni en otra ubicación de red. 
  
1. Haga clic en **Iniciar** para descargar los resultados de la búsqueda en el equipo. 
    
    La **Herramienta de exportación de exhibición de documentos electrónicos** muestra información del estado acerca del proceso de exportación, incluida una estimación del número (y tamaño) de los elementos restantes que se van a descargar. Una vez finalizado el proceso de exportación, puede tener acceso a los archivos en la ubicación en la que se descargaron. 
    

  
## <a name="more-information"></a>Más información

Aquí encontrará más información sobre cómo exportar los resultados de la búsqueda.
  
[Límites de exportación](#export-limits)
  
[Exportar informes](#export-reports)
  
[Exportar elementos parcialmente indizados](#exporting-partially-indexed-items)

[Exportar mensajes individuales o archivos PST](#exporting-individual-messages-or-pst-files)
  
[Descifrado de mensajes cifrados con RMS](#decrypting-rms-encrypted-messages)

[Nombres de archivo de los elementos exportados](#filenames-of-exported-items)  
  
[Varios](#miscellaneous)
  
 ### <a name="export-limits"></a>Límites de exportación
  
- La exportación de resultados de búsqueda desde el centro de seguridad & cumplimiento tiene los siguientes límites:
    
  - Puede exportar un máximo de 2 TB de datos a partir de una sola búsqueda de contenido. Si los resultados de la búsqueda tienen más de 2 TB, considere la posibilidad de usar intervalos de fechas u otros tipos de filtros para reducir el tamaño total de los resultados de la búsqueda.
    
  - Su organización puede exportar un máximo de 2 TB de datos durante un solo día.
    
  - Puede tener un máximo de 10 exportaciones ejecutándose a la vez dentro de su organización.
    
  - Un único usuario puede ejecutar un máximo de tres exportaciones al mismo tiempo.

  > [!NOTE]
  > Exportar solo los informes de una búsqueda de contenido también cuenta con el número de exportaciones que se ejecutan al mismo tiempo y el número de exportaciones que un solo usuario puede ejecutar.
    
- Como se indicó anteriormente, los resultados de la búsqueda de los buzones de correo y los sitios se cargan en la ubicación de almacenamiento de Azure (como se describe en [paso 1: preparar los resultados de la búsqueda para la exportación](#step-1-prepare-search-results-for-export)) a una velocidad máxima de 2 GB por hora.
    
- El tamaño máximo de un archivo PST que se puede exportar es de 10 GB de forma predeterminada. Esto significa que si los resultados de la búsqueda del buzón de un usuario son superiores a 10 GB, los resultados de la búsqueda para el buzón se exportarán en dos (o más) archivos PST independientes. Además, si decide exportar todos los resultados de búsqueda en un solo archivo PST, el archivo PST se Spilt en archivos PST adicionales si el tamaño total de los resultados de la búsqueda es superior a 10 GB. Si desea cambiar este tamaño predeterminado, puede editar el registro de Windows en el equipo que use para exportar los resultados de la búsqueda. Consulte [cambiar el tamaño de los archivos PST al exportar los resultados de la búsqueda de eDiscovery](change-the-size-of-pst-files-when-exporting-results.md).
    
    Además, los resultados de la búsqueda de un buzón de correo específico no se dividirán entre varios archivos PST a menos que el contenido de un buzón de correo sea superior a 10 GB. Si opta por exportar los resultados de la búsqueda de un archivo PST para que contenga todos los mensajes de una sola carpeta y los resultados de la búsqueda tienen un tamaño superior a 10 GB, los elementos siguen organizados en orden cronológico, por lo que se spiltrán en archivos PST adicionales basados en la d enviada izar.
     
 ### <a name="export-reports"></a>Exportar informes
  
- Al exportar los resultados de la búsqueda, se incluyen los siguientes informes además de los resultados de la búsqueda.
    
  - **Resumen de exportación** Un documento de Excel que contiene un resumen de la exportación. Esto incluye información como el número de orígenes de contenido que se han buscado, los tamaños Estimado y descargado de los resultados de la búsqueda y el número estimado y descargado de elementos que se exportaron. 
    
  - **Manifiesto** Un archivo de manifiesto (en formato XML) que contiene información sobre cada elemento incluido en los resultados de la búsqueda. 
    
  - **Resultados** Un documento de Excel que contiene información acerca de cada elemento que se descarga como resultado de la búsqueda. Para el correo electrónico, un registro de resultados contiene información acerca de cada mensaje, incluidos: 
    
      - La ubicación del mensaje en el buzón de origen (incluido si el mensaje se encuentra en el buzón de archivo o en el principal).
        
      - La fecha en que se envió o se recibió el mensaje.
        
      - La línea Asunto del mensaje.
        
      - El remitente y los destinatarios del mensaje.
        
      - Si el mensaje es un mensaje duplicado si ha habilitado la opción de desduplicación al exportar los resultados de la búsqueda. Los mensajes duplicados tendrán un valor en la columna **duplicar a elemento** que identifica el mensaje como duplicado. El valor de la columna **duplicar en elemento** contiene la identidad del elemento del mensaje que se ha exportado. Para obtener más información, vea desduplicación [en los resultados de la búsqueda de eDiscovery](de-duplication-in-ediscovery-search-results.md).
        
      Para los documentos de los sitios de SharePoint y OneDrive para la empresa, el registro de resultados contiene información sobre cada documento, incluidos:
        
      - La dirección URL del documento.
        
      - La dirección URL de la colección de sitio donde se ubica el documento.
        
      - La fecha en la que el documento se modificó por última vez.
        
      - El nombre del documento (que está ubicado en la columna Asunto del registro de resultados).
    
  - **Elementos** sin indexar Un documento de Excel que contiene información sobre cualquier elemento parcialmente indizado que se incluiría en los resultados de la búsqueda. Si no incluye elementos parcialmente indizados al generar el informe de resultados de búsqueda, este informe se descargará, pero estará vacío. 
    
  - **Errores y advertencias** Contiene errores y advertencias para los archivos encontrados durante la exportación. Consulte la columna detalles de los errores para obtener información específica de cada error o advertencia individual. 
    
  - **Elementos omitidos** Cuando se exportan resultados de búsqueda de sitios de SharePoint y OneDrive para la empresa, la exportación suele incluir un informe de elementos omitidos (SkippedItems. csv). Los elementos que se mencionan en este informe suelen ser elementos que no se pueden descargar, como una carpeta o un conjunto de documentos. No exportar este tipo de elementos es por diseño. Para otros elementos omitidos, el campo "tipo de error" y "detalles de error" del informe de elementos omitidos muestran la razón por la que se omitió el elemento y no se descargó con los demás resultados de la búsqueda. 
    
  - **Registro de seguimiento** Contiene información de registro detallada sobre el proceso de exportación y puede ayudarle a descubrir problemas durante la exportación. 
    
    > [!NOTE]
    > Solo puede exportar estos documentos sin tener que exportar los resultados de búsqueda reales. Consulte [exportar un informe de búsqueda de contenido](export-a-content-search-report.md). 
  
 ### <a name="exporting-partially-indexed-items"></a>Exportar elementos parcialmente indizados
  
- Si está exportando elementos de buzón de una búsqueda de contenido que devuelve todos los elementos del buzón de correo en los resultados de la búsqueda (porque no se incluyen palabras clave en la consulta de búsqueda), los elementos indexados parcialmente no se copiarán en el archivo PST que contiene los elementos sin indexar. Esto se debe a que todos los elementos, incluidos los elementos parcialmente indizados, se incluyen automáticamente en los resultados de la búsqueda normales. Esto significa que los elementos parcialmente indizados se incluirán en un archivo PST (o en mensajes individuales) que contengan los otros elementos indizados.
    
    Además, si exporta los elementos indizados y parcialmente indizados o si exporta sólo los elementos indizados de una búsqueda de contenido que devuelve todos los elementos, se descargará el mismo número de elementos. Esto ocurre aunque los resultados de búsqueda estimados para la búsqueda de contenido (que se muestran en las estadísticas de búsqueda en el centro de seguridad & cumplimiento) sigan incluyendo una estimación independiente del número de elementos parcialmente indizados. Por ejemplo, supongamos que la estimación de una búsqueda que incluye todos los elementos (sin palabras clave en la consulta de búsqueda) muestra que se han encontrado 1.000 elementos y que también se han encontrado 200 elementos indizados parcialmente. En este caso, los elementos 1.000 incluyen los elementos parcialmente indizados porque la búsqueda devuelve todos los elementos. Es decir, hay 1.000 total de elementos devueltos por la búsqueda y no 1.200 elementos (como cabría esperar). Si exporta los resultados de esta búsqueda y elige exportar los elementos indizados y parcialmente indizados (o solo los elementos indizados), se descargarán 1.000 elementos. Una vez más, esto se debe a que los elementos parcialmente indizados se incluyen con los resultados normales (indizados) cuando se usa una consulta de búsqueda en blanco para devolver todos los elementos. En este mismo ejemplo, si elige exportar sólo los elementos parcialmente indizados, solo se descargarán los elementos sin indexar 200.
    
    Tenga en cuenta también que en el ejemplo anterior (cuando exporte elementos indizados y indizados parcialmente o exporte sólo elementos indexados), el informe de **Resumen de exportación** incluido con los resultados de la búsqueda exportados mostraría 1.000 elementos estimados y 1.000 descargados elementos por los mismos motivos que se han descrito anteriormente. 
    
- Si la búsqueda desde la que está exportando resultados es una búsqueda de ubicaciones de contenido específicas o de todas las ubicaciones de contenido de su organización, solo se exportarán las ubicaciones de contenido de los elementos parciales que contienen elementos que coinciden con los criterios de búsqueda. Es decir, si no se encuentran resultados de búsqueda en un buzón de correo o en un sitio, no se exportarán los elementos parcialmente indizados de ese buzón o sitio. El motivo es que exportar los elementos parcialmente indizados de muchos lugares de la organización puede aumentar la probabilidad de errores de exportación y aumentar el tiempo que se tarda en exportar y descargar los resultados de la búsqueda.
    
    Para exportar elementos parcialmente indizados de todas las ubicaciones de contenido de una búsqueda, configure la búsqueda para devolver todos los elementos (quitando las palabras clave de la consulta de búsqueda) y, a continuación, exporte solo los elementos parcialmente indizados cuando exporte los resultados de la búsqueda.
    
    ![Usar la opción de exportación thrid para exportar solo los elementos sin indexar](media/5d7be338-a0e5-425f-8ba5-92769c24bf75.png)
  
- Al exportar resultados de búsqueda de sitios de SharePoint o de OneDrive para la empresa, la capacidad de exportar elementos sin indexar también depende de la opción de exportación que seleccione y de si un sitio en el que se realizó la búsqueda contiene un elemento indizado que coincida con los criterios de búsqueda. Por ejemplo, si busca sitios específicos de SharePoint o de OneDrive para la empresa y no se encuentra ningún resultado de búsqueda, no se exportarán elementos sin indexar de esos sitios si elige la segunda opción de exportación para exportar tanto los elementos indexados como los no indizados. Si un elemento indizado de un sitio coincide con los criterios de búsqueda, se exportarán todos los elementos no indexados de ese sitio cuando se exportan tanto elementos indizados como no indizados. En la siguiente ilustración se describen las opciones de exportación en función de si un sitio contiene o no un elemento indizado que coincida con los criterios de búsqueda.
    
    ![Elija la opción exportar en función de si un sitio contiene o no un elemento indizado que coincida con los criterios de búsqueda.](media/94f78786-c6bb-42fb-96b3-7ea3998bcd39.png)

    
    Solo se exportan los elementos indizados que coinciden con los criterios de búsqueda. No se exportan elementos parcialmente indizados.
    
    B: Si no hay elementos indizados de un sitio que coincidan con los criterios de búsqueda, no se exportarán los elementos indexados parcialmente de ese mismo sitio. Si los elementos indexados de un sitio se devuelven en los resultados de la búsqueda, se exportan los elementos parcialmente indizados de ese sitio. Es decir, solo se exportan los elementos parcialmente indizados de los sitios que contienen elementos que coinciden con los criterios de búsqueda.
    
    C: todos los elementos parcialmente indizados de todos los sitios de la búsqueda se exportan, independientemente de si un sitio contiene elementos que coinciden con los criterios de búsqueda.
    
    Si elige exportar elementos parcialmente indizados, los elementos del buzón indizados parcialmente se exportan a un archivo PST independiente independientemente de la opción que elija en **exportar contenido de Exchange como**.

- Si se devuelven elementos parcialmente indizados en los resultados de la búsqueda (debido a que otras propiedades de un elemento parcialmente indizado coinciden con los criterios de búsqueda), los índices parcialmente indizados se exportan con los resultados de la búsqueda normales. Por lo tanto, si decide exportar tanto los elementos indizados como los elementos parcialmente indizados (seleccionando **todos los elementos, incluidos los que tienen un formato no reconocido, que están cifrados o no se indizaron por otros motivos** , opción de exportación), se exportarán los elementos parcialmente indizados. con los resultados habituales se enumerarán en el informe Results. csv. No aparecerán en el informe items. csv sin indexar.
    
 ### <a name="exporting-individual-messages-or-pst-files"></a>Exportar mensajes individuales o archivos PST
  
- Si el nombre de la ruta de acceso del archivo de un mensaje supera el límite máximo de caracteres para Windows, el nombre de la ruta de acceso del archivo se trunca. Pero el nombre de la ruta de acceso del archivo original se enumerará en el manifiesto y ResultsLog.
    
- Como se explicó anteriormente, los resultados de la búsqueda de correo electrónico se exportan a una carpeta en el sistema de archivos. La ruta de acceso de la carpeta para los mensajes individuales replicaría la ruta de la carpeta en el buzón del usuario. Por ejemplo, para una búsqueda con el nombre "ContosoCase101" en la bandeja de entrada de un usuario estaría en la `~ContosoCase101\\<date of export\Exchange\user@contoso.com (Primary)\Top of Information Store\Inbox`ruta de la carpeta. 
    
- Si elige exportar los mensajes de correo electrónico de un archivo PST que contenga todos los mensajes de una sola carpeta, se incluirán en el nivel superior de la carpeta PST una carpeta de **elementos eliminados** y una carpeta de **carpetas de búsqueda** . Estas carpetas estarán vacías. 
  
 ### <a name="decrypting-rms-encrypted-messages"></a>Descifrado de mensajes cifrados con RMS
  
- Como se ha explicado anteriormente, para descifrar los mensajes cifrados con RMS cuando se exportan, se deben exportar los resultados de la búsqueda como mensajes individuales. Si exporta los resultados de la búsqueda a un archivo PST, los mensajes cifrados con RMS seguirán cifrados.
    
- La característica de descifrado de RMS de búsqueda de contenido no descifra los mensajes cifrados con el cifrado de mensajes de Office 365 (OME) cuando exporta resultados de búsqueda. Sin embargo, si un usuario de la organización envía un mensaje cifrado con OME, la copia del mensaje en la carpeta enviada del usuario no se cifra y será visible después de exportarlo. Sin embargo, si los usuarios de la organización reciben mensajes cifrados con OME, no se descifrarán una vez exportados. Para obtener más información acerca de OME, consulte [Office 365 Message Encryption](https://go.microsoft.com/fwlink/p/?linkid=844966).
    
- Los mensajes que se descifran se identifican en el informe **ResultsLog** . Este informe contiene una columna denominada **Estado**de descodificación y un valor descodificado en esta columna identifica los mensajes que se han descifrado. **** 
    
- Actualmente, esta capacidad de descifrado no incluye contenido cifrado de sitios de SharePoint y OneDrive para la empresa. Cuando se exportan, solo se descifrarán los mensajes de correo electrónico cifrados con RMS.
    
- Si un mensaje de correo electrónico cifrado con RMS tiene datos adjuntos (como un documento u otro mensaje de correo electrónico) que también están cifrados, solo se descifrará el mensaje de correo electrónico de nivel superior.
    
- No puede obtener una vista previa de un mensaje de correo electrónico cifrado con RMS. Para ver un mensaje cifrado, tiene que exportarlo.
    
- Si necesita impedir que alguien descifre mensajes cifrados con RMS, tendrá que crear un grupo de roles personalizado (copiando el grupo de roles integrado eDiscovery Manager) y, a continuación, quitar el rol de administración desCifrado de RMS del grupo de roles personalizado. A continuación, agregue la persona que no desea que descifre los mensajes como miembro del grupo de roles personalizado.
  
 ### <a name="filenames-of-exported-items"></a>Nombres de archivo de los elementos exportados
  
- Hay un límite de 260 caracteres (impuesto por el sistema operativo) para el nombre de la ruta de acceso completa de los mensajes de correo electrónico y los documentos del sitio exportados a su equipo local. El nombre de la ruta de acceso completa de los elementos exportados incluye la ubicación original del elemento y la ubicación de la carpeta en el equipo local en el que se descargan los resultados de la búsqueda. Por ejemplo, si especifica que los resultados de la búsqueda se `C:\Users\Admin\Desktop\SearchResults` descargan en la herramienta de exportación de exhibición de documentos electrónicos, el path completo `C:\Users\Admin\Desktop\SearchResults\ContentSearch1\03.15.2017-1242PM\Exchange\sarad@contoso.com (Primary)\Top of Information Store\Inbox\Insider trading investigation.msg`de un elemento de correo electrónico descargado sería.
    
    Si se supera el límite de 260 caracteres, se truncará el nombre de ruta completo de un elemento.
    
  - Si el nombre de la ruta de acceso completa tiene más de 260 caracteres, el nombre del archivo se acortará para que quede bajo el límite; Tenga en cuenta que el nombre de archivo truncado (sin incluir la extensión de archivo) no será inferior a 8 caracteres.
    
  - Si el nombre de la ruta de acceso completa sigue siendo demasiado largo después de acortar el nombre del archivo, el elemento se mueve de su ubicación actual a la carpeta principal. Si el nombre de la ruta de la ruta sigue siendo demasiado largo, el proceso se repite: Acorte el nombre de archivo y, si es necesario, desplácese de nuevo a la carpeta principal. Este proceso se repite hasta que el directorio completo tiene un límite de 260 caracteres.
    
  - Si ya existe un nombre de ruta de acceso completo truncado, se agregará un número de versión al final del nombre de archivo; por ejemplo, `statusmessage(2).msg`.
    
    Para ayudar a mitigar este problema, considere la posibilidad de descargar los resultados de la búsqueda en una ubicación con un nombre de ruta corto; por ejemplo, si se descargan los resultados `C:\Results` de la búsqueda en una carpeta denominada, se agregarán menos caracteres a los nombres de ruta `C:\Users\Admin\Desktop\Results`de los elementos exportados que al descargarlos en una carpeta denominada.
    
- Al exportar documentos de sitio, también es posible que se modifique el nombre de archivo original de un documento. Esto se produce específicamente para los documentos que se han eliminado de un sitio de SharePoint o de OneDrive para la empresa que se ha puesto en suspensión. Una vez que se elimina un documento ubicado en un sitio que está en suspensión, el documento eliminado se mueve automáticamente a la biblioteca de conservación de documentos para el sitio (que se creó cuando el sitio se puso en espera). Cuando el documento eliminado se mueve a la biblioteca de conservación de documentos, se anexa un identificador único e aleatorio al nombre del archivo original del documento. Por ejemplo, si el nombre de archivo de un `FY2017Budget.xlsx` documento es y el documento se elimina y se mueve a la biblioteca de conservación de documentos, el nombre de archivo del documento que se mueve a la biblioteca de conservación `FY2017Budget_DEAF727D-0478-4A7F-87DE-5487F033C81A2000-07-05T10-37-55.xlsx`de documentos se modifica de forma similar. Si un documento de la biblioteca de conservación de documentos coincide con la consulta de una búsqueda de contenido y se exportan los resultados de la búsqueda, el archivo exportado tendrá el nombre de archivo modificado; en este ejemplo, el nombre de archivo del documento exportado sería `FY2017Budget_DEAF727D-0478-4A7F-87DE-5487F033C81A2000-07-05T10-37-55.xlsx`.
    
    Además, cuando se modifica un documento ubicado en un sitio que está en suspensión (y se ha habilitado el control de versiones de la biblioteca de documentos en el sitio), se crea automáticamente una copia del archivo en la biblioteca de conservación de documentos. En este caso, también se anexa un identificador único e aleatorio al nombre del documento que se copia en la biblioteca de conservación de documentos.
    
    La razón por la que los nombres de archivo de los documentos que se mueven o se copian en la biblioteca de conservación de documentos es para evitar conflictos con los nombres de archivo. Para obtener más información sobre cómo colocar una retención en sitios y en la biblioteca de conservación de conservas, vea [información general sobre la conservación local en SharePoint Server 2016](https://support.office.com/article/5e400d68-cd51-444a-8fe6-e4df1d20aa95).
    
 ### <a name="miscellaneous"></a>Varios
  
- Todos los resultados de búsqueda y los informes de exportación se incluyen en una carpeta que tiene el mismo nombre que en la búsqueda de contenido. Los mensajes de correo electrónico que se exportaron se ubican en una carpeta denominada **Exchange**. Los documentos se ubican en una carpeta denominada **SharePoint**. 
    
- Los metadatos del sistema de archivos para los documentos de los sitios de SharePoint y OneDrive para la empresa se mantienen cuando los documentos se exportan a su equipo local. Eso significa que las propiedades del documento, como la fecha de creación y la fecha en la que se modificó por última vez, no cambian cuando se exportan los documentos.

- Si los resultados de la búsqueda incluyen un elemento de lista de SharePoint que coincide con la consulta de búsqueda, todas las filas de la lista se exportarán además del elemento que coincida con la consulta de búsqueda. Esto incluye todos los datos adjuntos de la lista. El motivo es proporcionar un contexto para los elementos de lista que se devuelven en los resultados de la búsqueda. Además, tenga en cuenta que los elementos de lista y datos adjuntos adicionales pueden hacer que el recuento de elementos exportados sea diferente de la estimación original de los resultados de búsqueda.
