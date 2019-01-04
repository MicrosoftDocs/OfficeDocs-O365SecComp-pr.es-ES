---
title: Exportar los resultados de la búsqueda de contenido desde el centro de cumplimiento y seguridad de Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.CustomizeExport
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: ed48d448-3714-4c42-85f5-10f75f6a4278
description: 'Exportar los resultados de búsqueda de una búsqueda de contenido en el centro de cumplimiento y seguridad de Office 365 a un equipo local. Resultados de correo electrónico se exportan como archivos PST. Contenido de SharePoint y OneDrive para sitios de negocio se exportan como documentos de Office nativos. '
ms.openlocfilehash: d67b6aeedd3f01bd21de0e07f42870db7a18767b
ms.sourcegitcommit: ea625737c4be14927f69aa71d4fbd7d7d94d9334
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/04/2019
ms.locfileid: "27544121"
---
# <a name="export-content-search-results-from-the-office-365-security--compliance-center"></a>Exportar los resultados de la búsqueda de contenido desde el centro de cumplimiento y seguridad de Office 365

Después de ejecutar correctamente una búsqueda de contenido, puede exportar los resultados de búsqueda a un equipo local. Al exportar los resultados de correo electrónico, se descargan en el equipo como archivos PST. Al exportar contenido de SharePoint y OneDrive para sitios de negocio, se exportan copias de los documentos de Office nativos. Hay otros documentos e informes que se incluyen con los resultados de búsqueda exportado.
  
Además, todos los mensajes de correo electrónico cifrados de RMS que se incluyen en los resultados de una búsqueda de contenido se descifrarán al exportar (como los mensajes individuales). Esta capacidad de descifrado está habilitada de forma predeterminada para los miembros del grupo de roles de administrador de exhibición de documentos electrónicos. Esto es debido a que la función de administración de RMS descifrar se asigna a este grupo de funciones. Al exportar los resultados de búsqueda, vea la sección [más información](#more-information) para obtener información detallada acerca de descifrado de RMS. 
  
Exportar los resultados de una búsqueda de contenido implica la preparación de los resultados y, a continuación, los descarga en un equipo local.
  
## <a name="before-you-begin"></a>Antes de empezar

- Para exportar los resultados de búsqueda, tiene que tener asignado el rol de administración de exportación de la seguridad de Office 365 &amp; centro de cumplimiento. Esta función se asigna al grupo de roles de administrador de exhibición de documentos electrónicos integrados. No se asigna de forma predeterminada al grupo de funciones de administración de la organización. Para obtener más información, vea [asignar permisos de exhibición de documentos electrónicos en la seguridad de Office 365 &amp; centro de cumplimiento](assign-ediscovery-permissions.md).
    
- El equipo que use para exportar los resultados de búsqueda debe cumplir los siguientes requisitos del sistema:
    
  - Versiones de 32 o 64 bits de Windows 7 y versiones posteriores
    
  - Microsoft .NET Framework 4.7
    
  - Un explorador compatible:
    
     - Microsoft Edge
    
        O BIEN
    
     - Microsoft Internet Explorer 10 y versiones posteriores
    
    **Nota:** Microsoft no fabrica las extensiones de terceros o complementos para las aplicaciones ClickOnce. No se admite la exportación de resultados de búsqueda mediante un explorador no compatible con las extensiones de terceros o los complementos. 
    
- Al descargar los resultados de búsqueda (que se describe en el paso 2), puede aumentar la velocidad de descarga mediante la configuración de una configuración del registro de Windows en el equipo que utilice para exportar los resultados de búsqueda. Para obtener más información, vea [aumentar la velocidad de descarga al exportar los resultados de búsqueda de exhibición de documentos electrónicos de Office 365](increase-download-speeds-when-exporting-ediscovery-results.md).
    
- Al exportar los resultados de búsqueda, se almacenan temporalmente los datos en una ubicación de almacenamiento de Microsoft Azure única en la nube de Microsoft antes de se descarga en el equipo local. Asegúrese de que la organización puede conectarse al extremo en Azure, que es ** \*. blob.core.windows.net** (el carácter comodín representa un identificador único para la exportación). Los datos de los resultados de la búsqueda se eliminan de la ubicación de almacenamiento de Azure dos semanas después de crearla. 
    
- Si su organización usa un servidor proxy para comunicarse con Internet, debe definir la configuración del servidor proxy en el equipo que utilice para exportar los resultados de búsqueda (de manera que la herramienta de exportación se puede autenticar con el servidor proxy). Para ello, abra el archivo *machine.config* en la ubicación que coincida con su versión de Windows. 
    
  - **32-bit** - `%windir%\Microsoft.NET\Framework\[version]\Config\machine.config`
    
  - **64 bits** - `%windir%\Microsoft.NET\Framework64\[version]\Config\machine.config`
    
    Agregue las siguientes líneas al archivo *machine.config* en algún lugar entre la `<configuration>` y `</configuration>` etiquetas. Asegúrese de reemplazar `ProxyServer` y `Port` con los valores correctos para su organización; Por ejemplo, `proxy01.contoso.com:80` . 
    
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

El primer paso consiste en preparar los resultados de búsqueda para la exportación. Cuando se preparan los resultados, se cargan en una ubicación de almacenamiento de Azure en la nube de Microsoft. Tenga en cuenta que el contenido de los buzones de correo y los sitios se carga a una velocidad máxima de 2 GB por hora.
  
1. Vaya a [https://protection.office.com](https://protection.office.com).
    
2. Inicie sesión en Office 365 con su cuenta profesional o educativa.
    
3. En el panel izquierdo del Centro de seguridad y cumplimiento, haga clic en **Búsqueda e investigación** \> **Búsqueda de contenido**.
    
4. En la página de **búsqueda de contenido** , seleccione una búsqueda. 
    
5. En el panel de detalles, en **Exportar resultados a un equipo**, haga clic en **Iniciar la exportación**.
    
    > [!NOTE]
    > Si los resultados de una búsqueda son de hace más de 7 días, se le solicitará que actualice los resultados de búsqueda. Si esto ocurre, cancele la exportación, haga clic en **Actualizar los resultados de búsqueda** en el panel de detalles para la búsqueda seleccionada y, a continuación, inicie la exportación de nuevo después de que se actualicen los resultados.  
  
6. En la página **exportar los resultados de búsqueda** , en **Opciones de salida**, elija una de las siguientes opciones:
    
    - Todos los artículos, excepto que tienen un formato no reconocido, se cifran o no estaban indizados por otras razones
    
    - Todos los elementos, los que tienen formato no reconocido, incluidos se cifran o no estaban indizados por otras razones
    
    - Sólo los elementos que tienen un formato no reconocido, se cifran o no estaban indizados por otras razones
    
    Vea la sección [obtener más información](#more-information) para obtener una descripción acerca de los elementos indizados cómo parcialmente se exportan. Para obtener más información acerca de los elementos indizados parcialmente, vea [parcialmente indizar los elementos de búsqueda de contenido](partially-indexed-items-in-content-search.md).
    
7. En el **contenido de Exchange exportar como**, elija una de las siguientes opciones:
    
    - **Archivo PST uno para cada buzón** - exporta un archivo PST para cada buzón de usuario que contiene los resultados de búsqueda. Los resultados de buzón de archivo del usuario se incluyen en el mismo archivo PST. Tenga en cuenta que esta opción reproduce la estructura de carpetas de buzón de correo del buzón de origen. 
    
    - **Archivo PST uno que contiene todos los mensajes** - exporta un único archivo PST (denominado *Exchange.pst* ) que contiene los resultados de búsqueda de todos los buzones de origen que se incluyen en la búsqueda. Tenga en cuenta que esta opción reproduce la estructura de carpetas de buzón de correo para cada mensaje. 
    
    - **Todos los mensajes en una sola carpeta que contiene el archivo PST uno** - exporta los resultados de búsqueda a un archivo PST única donde todos los mensajes se encuentran en una carpeta de nivel superior, único. Esta opción permite a los revisores revise los elementos en orden cronológico (los elementos se ordenan por fecha de envío) sin tener que desplazarse por la estructura de carpeta de buzón de correo original para cada elemento. 
    
    - **Los mensajes individuales** : exporta los resultados de búsqueda como mensajes de correo electrónico individuales, con el formato .msg. Si selecciona esta opción, se exportan los resultados de búsqueda de correo electrónico a una carpeta en el sistema de archivos. La ruta de acceso de carpeta para los mensajes individuales es el mismo que el utilizado si exporta los resultados a los archivos PST. 
    
      > [!IMPORTANT]
      > Para descifrar mensajes cifrados mediante RMS cuando se va a exportar, debe exportar los resultados de búsqueda de correo electrónico como los mensajes individuales. Los mensajes cifrados permanecerán cifrados si exportar los resultados de búsqueda como un archivo PST. 
  
8. Haga clic en la casilla de verificación **Habilitar la desduplicación** para excluir los mensajes duplicados. Esta opción aparece únicamente si los orígenes de contenido de la búsqueda incluye los buzones de Exchange o carpetas públicas. 
    
    Si selecciona esta opción, se exportarán sólo una copia de un mensaje, incluso si se encuentran varias copias del mismo mensaje en los buzones de correo que se desea buscar. El informe de los resultados de la exportación (Results.csv) contendrá una fila por cada copia de un mensaje duplicado para que pueda identificar los buzones (o las carpetas públicas) que contienen una copia del mensaje duplicado. Para obtener más información acerca de la desduplicación y los elementos duplicados cómo se identifican, vea [la desduplicación en los resultados de búsqueda de exhibición de documentos electrónicos](de-duplication-in-ediscovery-search-results.md).
    
9. Haga clic en la casilla de verificación **incluir versiones de documentos de SharePoint** para exportar todas las versiones de documentos de SharePoint. Esta opción aparece únicamente si los orígenes de contenido de la búsqueda incluye SharePoint o OneDrive para los sitios de negocio. 
    
10. Haga clic en la casilla de verificación **exportar archivos en una carpeta comprimida (zip)** para exportar los resultados de búsqueda a las carpetas comprimidas. Esta opción está disponible sólo cuando se elige exportar elementos de Exchange como mensajes individuales y cuando los resultados de búsqueda incluyen documentos de SharePoint o OneDrive. Esta opción se usa principalmente para evitar el límite de 260 caracteres en los nombres de ruta de acceso de archivo de Windows cuando se exportan los elementos. Vea el "nombres de archivo de elementos exportados" en la sección [más información](#more-information) . 
    
11. Haga clic en **Iniciar la exportación**.
    
    Los resultados de búsqueda estén preparados para descargar el archivo, lo que significa que está que se cargan a la ubicación de almacenamiento de Azure en la nube de Microsoft. Cuando estén listos para la descarga de los resultados de búsqueda, se muestra el vínculo de **descarga de exporta los resultados** en **exportar los resultados a un equipo** en el panel de detalles. 
  
## <a name="step-2-download-the-search-results"></a>Paso 2: Descargar los resultados de búsqueda

El siguiente paso es descargar los resultados de búsqueda desde la ubicación de almacenamiento de Azure en su equipo local.
  
Como se explica anteriormente, puede aumentar la velocidad de descarga mediante la configuración de una configuración del registro de Windows en el equipo que utilice para exportar los resultados de búsqueda. Para obtener más información, vea [aumentar la velocidad de descarga al exportar los resultados de búsqueda de exhibición de documentos electrónicos de Office 365](increase-download-speeds-when-exporting-ediscovery-results.md).
  
1. En el panel de detalles de la búsqueda para la que inició la exportación, en **Exportar resultados a un equipo**, haga clic en **Descargar resultados exportados**.
    
    La **descarga exporta los resultados de la** ventana se muestra y contiene la siguiente información acerca de los resultados de búsqueda que se descargarán en su equipo. 
    
    - El número de elementos que se descargarán.
    
    - El tamaño total estimado de los elementos que se descargarán.
    
    - Si los elementos indexados o sin indexar se exportarán. Los elementos sin indexar son elementos que tienen un formato reconocido, están cifrados o no se indexaron por otros motivos. Para obtener más información, consulte [Unindexed items in Content Search](partially-indexed-items-in-content-search.md).
    
    - Si las versiones de los documentos de SharePoint se descargarán o no.
    
    - El estado del proceso de preparación de la exportación. Puede iniciar la descarga de los resultados de búsqueda incluso si la preparación de los datos no está completa.
    
2. En **Clave de exportación**, haga clic en **Copiar al Portapapeles**. Esta clave se usará para descargar los resultados de la búsqueda en el paso 5.
    
    > [!NOTE]
    > Dado que cualquier persona puede instalar e iniciar la herramienta de exportación de exhibición de documentos electrónicos y después usar esta clave para descargar los resultados de búsqueda, asegúrese de tomar precauciones para proteger esta clave como protegería las contraseñas u otra información relacionada con la seguridad.  
  
3. Haga clic en **Descargar resultados**.
    
4. Si le pide para instalar la **exhibición de documentos de Microsoft Office 365 herramienta para exportar**, haga clic en **instalar**.
    
5. En la **Herramienta de exportación de exhibición de documentos electrónicos**, pegue la clave de exportación que ha copiado en el paso 2 en el cuadro correspondiente.
    
6. Haga clic en **Examinar** para especificar la ubicación en la que desea descargar los archivos de los resultados de la búsqueda. 
    
    > [!NOTE]
    > Debido a la gran cantidad de actividad de disco (lecturas y escrituras), debe descargar los resultados de búsqueda a una unidad de disco local; No, se descargan en una unidad de red asignada u otra ubicación de red. 
  
1. Haga clic en **Iniciar** para descargar los resultados de la búsqueda en el equipo. 
    
    La **exhibición de documentos electrónicos herramienta para exportar** muestra información de estado sobre el proceso de exportación, así como una estimación del número (y tamaño) de los elementos restantes para ser descargado. Cuando se completa el proceso de exportación, puede tener acceso a los archivos en la ubicación donde se han descargado. 
    

  
## <a name="more-information"></a>Más información

Aquí es obtener más información acerca de cómo exportar los resultados de búsqueda.
  
[Límites de exportación](#export-limits)
  
[Exportación de informes](#export-reports)
  
[Exportación de los elementos indizados parcialmente](#exporting-partially-indexed-items)

[Exportación de los mensajes individuales o los archivos PST](#exporting-individual-messages-or-pst-files)
  
[Descifrar mensajes cifrados mediante RMS](#decrypting-rms-encrypted-messages)

[Nombres de archivo de los elementos exportados](#filenames-of-exported-items)  
  
[Varios](#miscellaneous)
  
 ### <a name="export-limits"></a>Límites de exportación
  
- Exportar los resultados de búsqueda de la seguridad &amp; centro de cumplimiento tiene los siguientes límites:
    
  - Puede exportar un máximo de 2 TB de datos desde una sola búsqueda de contenido. Si los resultados de búsqueda son mayores de 2 TB, considere el uso de intervalos de fecha u otros tipos de filtros para reducir el tamaño total de los resultados de búsqueda.
    
  - Su organización puede exportar un máximo de 2 TB de datos durante un solo día.
    
  - Puede tener un máximo de 10 exportaciones ejecutándose a la vez dentro de su organización.
    
  - Un único usuario puede ejecutar un máximo de tres exportaciones al mismo tiempo.

  > [!NOTE]
  > Exportar sólo los informes de una búsqueda de contenido también cuenta con respecto al número de exportaciones que se ejecuta en el mismo momento y el número de exportaciones que puede ejecutar un único usuario.
    
- Como se mencionó anteriormente, los resultados de búsqueda de buzones de correo y los sitios se cargan en la ubicación de almacenamiento de Azure (tal como se describe en [paso 1: preparación de los resultados para la exportación de búsqueda](#step-1-prepare-search-results-for-export)) a una velocidad máxima de 2 GB por hora.
    
- El tamaño máximo de un archivo PST que se puede exportar es 10 GB de forma predeterminada. Esto significa que si los resultados de búsqueda desde el buzón de un usuario son mayores de 10 GB, se exportará los resultados de búsqueda para el buzón de correo en los archivos PST independientes dos (o más). Además, si elige exportar todos los resultados de búsqueda en un único archivo PST, el archivo PST se se divide en archivos PST adicionales si el tamaño total de los resultados de búsqueda es mayor que 10 GB. Si desea cambiar este tamaño predeterminado, puede editar el registro de Windows en el equipo que utilice para exportar los resultados de búsqueda. Vea [cambiar el tamaño de los archivos PST al exportar los resultados de búsqueda de exhibición de documentos electrónicos](change-the-size-of-pst-files-when-exporting-results.md).
    
    Además, los resultados de búsqueda de un buzón específico no dividirse entre varios archivos PST a menos que el contenido de un solo buzón es más de 10 GB. Si opta por exportar los resultados de búsqueda en un PST archivo para contiene todos los mensajes en una sola carpeta y los resultados de búsqueda son mayores de 10 GB, los elementos aún están organizados en orden cronológico, por lo que se se divide en archivos PST adicionales en función de la d enviado ingerir.
     
 ### <a name="export-reports"></a>Exportación de informes
  
- Al exportar los resultados de búsqueda, los siguientes informes se incluyen además de los resultados de búsqueda.
    
  - **Resumen de exportación** Un documento de Excel que contiene un resumen de la exportación. Esto incluye información como el número de orígenes de contenido que se han buscado, el tamaño estimado y descargado de los resultados de búsqueda y el número estimado y descargado de elementos que se han exportado. 
    
  - **Manifiesto** Un archivo de manifiesto (en formato XML) que contiene información acerca de los artículos incluidos en los resultados de búsqueda. 
    
  - **Resultados** Un documento de Excel que contiene información acerca de cada elemento que se descarga como un resultado de búsqueda. Para el correo electrónico, el registro de resultados contiene información acerca de cada mensaje, incluidos: 
    
      - La ubicación del mensaje en el buzón de origen (incluido si el mensaje se encuentra en el buzón de archivo o en el principal).
        
      - La fecha en que se envió o se recibió el mensaje.
        
      - La línea Asunto del mensaje.
        
      - El remitente y los destinatarios del mensaje.
        
      - Si el mensaje es un mensaje duplicado si se habilita la opción de desduplicación al exportar los resultados de búsqueda. Mensajes duplicados tendrán un valor en la columna **duplicada para el elemento** que identifica el mensaje como un duplicado. El valor de la columna **duplicada para el elemento** contiene la identidad del elemento del mensaje que se ha exportado. Para obtener más información, vea [la desduplicación en los resultados de búsqueda de exhibición de documentos electrónicos](de-duplication-in-ediscovery-search-results.md).
        
      Para los documentos de SharePoint y OneDrive para sitios de profesionales, el registro de resultados contiene información acerca de cada documento, incluidos:
        
      - La dirección URL del documento.
        
      - La dirección URL de la colección de sitio donde se ubica el documento.
        
      - La fecha en la que el documento se modificó por última vez.
        
      - El nombre del documento (que está ubicado en la columna Asunto del registro de resultados).
    
  - **Elementos sin indizar** Un documento de Excel que contiene información acerca de los elementos indizados parcialmente que se incluirán en los resultados de búsqueda. Si no incluye los elementos indizados parcialmente al generar el informe de resultados de búsqueda, se descargará este informe, pero estará vacía. 
    
  - **Errores y advertencias** Contiene errores y advertencias para los archivos que se encontraron durante la exportación. Vea la columna de detalles del Error para obtener información específica de cada error individual o una advertencia. 
    
  - **Elementos omitidos** Al exportar los resultados de búsqueda de SharePoint y OneDrive para sitios de profesionales, la exportación incluirá normalmente un informe de elementos omitidos (SkippedItems.csv). Los elementos citados en este informe suelen ser los elementos que no se descargarán, como una carpeta o un documento establecer. No exportar este tipos de elementos es por diseño. Para otros elementos que se pasan por alto, el 'Error tipo' y el campo de detalles del Error en el informe de elementos omitidos mostrar el motivo por el elemento se omitió y no estaba descarga con los otros resultados de búsqueda. 
    
  - **El registro de seguimiento** Contiene información de registro detallada sobre el proceso de exportación y pueden ayudar a descubrir problemas durante la exportación. 
    
    > [!NOTE]
    > Sólo puede exportar estos documentos sin tener que volver a exportar los resultados de búsqueda reales. Consulte [exportar un informe de búsqueda de contenido](export-a-content-search-report.md). 
  
 ### <a name="exporting-partially-indexed-items"></a>Exportación de los elementos indizados parcialmente
  
- Si va a exportar los elementos del buzón desde una búsqueda de contenido que devuelve todos los elementos del buzón de correo en los resultados de búsqueda (debido a que no hay palabras clave donde se incluyen en la consulta de búsqueda), no se copiarán los elementos indizados parcialmente al archivo PST que contiene los elementos sin indizar. Esto es debido a que todos los elementos, incluidos los elementos indizados parcialmente, se incluyen automáticamente en los resultados de búsqueda normal. Esto significa que los elementos indizados parcialmente se incluirán en un archivo PST (o como los mensajes individuales) que contiene los elementos de otros, indizados.
    
    Además, si exporta los elementos indizados y parcialmente indizados o si exporta sólo los elementos indizados de una búsqueda de contenido que devuelve todos los elementos, se descargará el mismo número de elementos. Esto sucede aunque los resultados de búsqueda estimada para la búsqueda de contenido (que se muestra en las estadísticas de búsqueda en la seguridad &amp; centro de cumplimiento) aún incluirá una estimación independiente para el número de elementos indizados parcialmente. Por ejemplo, supongamos que se muestra la estimación para una búsqueda que incluye todos los elementos (no hay palabras clave en la consulta de búsqueda) que se han encontrado 1.000 elementos y que también se han encontrado elementos indizados parcialmente 200. En este caso, los elementos de 1.000 incluyen los elementos indizados parcialmente debido a que la búsqueda devuelve todos los elementos. En otras palabras, hay 1.000 elementos totales devueltos por la búsqueda y no 1.200 elementos (como es de esperar). Si exportar los resultados de esta búsqueda y elija Exportar indizados y parcialmente indiza elementos (o elementos indizados acaba), a continuación, se descargará 1.000 elementos. Una vez más, que es debido a que los elementos indizados parcialmente se incluyen con los resultados (indizados) regulares cuando se usa una consulta de búsqueda en blanco para devolver todos los elementos. En este mismo ejemplo, si se decide exportar sólo los elementos indizados parcialmente, a continuación, sólo los elementos sin indizar 200 podrían descargarse.
    
    Tenga en cuenta también que en el ejemplo anterior (al exportar elementos indizados y parcialmente indizados o exportar sólo los elementos indizados), el informe de **Resumen de exportación** incluido en los resultados de búsqueda exportado sería elementos de lista 1.000 elementos estimado y 1.000 descargado elementos por las mismas razones como se describió anteriormente. 
    
- Si la búsqueda que se va a exportar los resultados de era una búsqueda de ubicaciones de contenido específicas o todas las ubicaciones de contenido en su organización, se exportarán sólo los parcialmente elementos desde ubicaciones de contenido que contienen elementos que coinciden con los criterios de búsqueda. En otras palabras, si no hay resultados de búsqueda se encuentran en un buzón o un sitio, a continuación, cualquiera parcialmente elementos indizados en ese buzón o no se exportará el sitio. El motivo es que exportar elementos indizados parcialmente de una gran cantidad de ubicaciones en la organización puede aumentar la probabilidad de errores de exportación y aumentan el tiempo que se tarda en exportar y descargar los resultados de búsqueda.
    
    Para exportar elementos indizados parcialmente de todas las ubicaciones de contenido para una búsqueda, configurar la búsqueda para devolver todos los elementos (mediante la eliminación de todas las palabras clave de la consulta de búsqueda) y, a continuación, exportar sólo los elementos indizados parcialmente al exportar los resultados de búsqueda.
    
    ![Use la opción de exportación de la tercera para exportar sólo los elementos sin indizar](media/5d7be338-a0e5-425f-8ba5-92769c24bf75.png)
  
- Para exportar los resultados de búsqueda de SharePoint o OneDrive para sitios de negocio, la capacidad para exportar elementos sin indizar depende también de la opción de exportación que seleccione y de si un sitio que se realizó la búsqueda contiene un elemento indizado que coincide con los criterios de búsqueda. Por ejemplo, si busca específicas de SharePoint o OneDrive para los sitios de negocio y se encuentra ningún resultado de búsqueda, a continuación, no hay elementos sin indizar de dichos sitios se exportará si elige la segunda opción de exportación para exportar elementos indizados y no indizados. Si un elemento indizado de un sitio coincide con los criterios de búsqueda, a continuación, todos los elementos sin indizar desde ese sitio se exportará al exportar elementos indizados y no indizados. En la ilustración siguiente se describe las opciones de exportación en función de si un sitio contiene un elemento indizado que coincide con los criterios de búsqueda.
    
    ![Elija la opción de exportación en función de si un sitio contiene un elemento indizado que coincide con los criterios de búsqueda](media/94f78786-c6bb-42fb-96b3-7ea3998bcd39.png)

    
    A - se exportan sólo los elementos indizados que coincide con los criterios de búsqueda. No hay elementos indizados parcialmente se exportan.
    
    B - si no hay elementos indizados desde un sitio coincide con los criterios de búsqueda, no se exportan los elementos parcialmente indizados desde ese mismo sitio. Si se devuelven los elementos indizados desde un sitio en los resultados de búsqueda, se exportan los elementos indizados parcialmente de ese sitio. En otras palabras, se exportan sólo los elementos indizados parcialmente de los sitios que contienen los elementos que coinciden con los criterios de búsqueda.
    
    C - todos los elementos indizados parcialmente desde todos los sitios de la búsqueda se exportan, independientemente de si un sitio contiene elementos que coinciden con los criterios de búsqueda.
    
    Si decide exportar elementos indizados parcialmente, se exportan los elementos del buzón parcialmente indizados en un archivo PST independiente independientemente de la opción que elija en **Exchange exportar contenido como**.

- Si se devuelven los elementos indizados parcialmente en la búsqueda de resultados (debido a que otras propiedades de elementos indizados parcialmente coincide con los criterios de búsqueda), a continuación, se exporta esos parcialmente indizada con los resultados de búsqueda normal. Por lo tanto, si se decide exportar los elementos indizados y los elementos indizados parcialmente (seleccionando la opción de exportación de **todos los elementos, los que tienen formato no reconocido, incluidos se cifran, o no estaban indizados por otras razones** ), los elementos indizados parcialmente exportan con los resultados regulares se mostrarán en el informe de Results.csv. No se enumerarán en el informe de items.csv no indizados.
    
 ### <a name="exporting-individual-messages-or-pst-files"></a>Exportación de los mensajes individuales o los archivos PST
  
- Si el nombre de ruta de acceso de archivo de un mensaje supera el límite máximo de caracteres para Windows, el nombre de ruta de acceso de archivo se trunca. Pero el nombre de ruta de acceso del archivo original se mostrarán en el manifiesto y ResultsLog.
    
- Como se explica anteriormente, correo electrónico los resultados se exportan a una carpeta en el sistema de archivos de búsqueda. La ruta de acceso de carpeta para los mensajes individuales replica la ruta de acceso de carpeta en el buzón del usuario. Por ejemplo, para una búsqueda denominada "ContosoCase101" los mensajes en la Bandeja de entrada de un usuario debería encontrarse en la ruta de acceso de la carpeta `~ContosoCase101\\<date of export\Exchange\user@contoso.com (Primary)\Top of Information Store\Inbox`. 
    
- Si decide exportar mensajes de correo electrónico en un archivo PST que contiene todos los mensajes en una sola carpeta, una carpeta de **Elementos eliminados** y una carpeta de **Las carpetas de búsqueda** se incluyen en el nivel superior de la carpeta PST. Estas carpetas estarán vacías. 
  
 ### <a name="decrypting-rms-encrypted-messages"></a>Descifrar mensajes cifrados mediante RMS
  
- Como se explica anteriormente, para descifrar mensajes cifrados mediante RMS cuando exportarlos, debe exportar los resultados de búsqueda como los mensajes individuales. Si exporta los resultados de búsqueda a un archivo PST, mensajes cifrados mediante RMS permanecerá cifrados.
    
- La característica de descifrado de RMS en búsqueda de contenido no descifrar mensajes cifrados con Office 365 Message Encryption (OME) al exportar los resultados de búsqueda. Sin embargo, si se envía un mensaje cifrado con OME por un usuario en la organización, la copia del mensaje en la carpeta del usuario enviados no se cifra y se podrá ver después de que se exportó. Sin embargo, si se reciben mensajes cifrados con OME por los usuarios de la organización, no descifrar después de que se va a exportar. Para obtener más información sobre OME, consulte [Cifrado de mensajes de Office 365](https://go.microsoft.com/fwlink/p/?linkid=844966).
    
- Los mensajes que estén descifrados son identificados en el informe de **ResultsLog** . Este informe contiene una columna denominada **Estado descodificar**y un valor de **descodificación** en esta columna identifica los mensajes de la se han descifrar. 
    
- Actualmente, esta capacidad de descifrado no incluye contenido cifrado de SharePoint y OneDrive para sitios de negocio. Solo los mensajes de correo electrónico cifrados de RMS se descifrarán al exportar a ellos.
    
- Si un mensaje de correo electrónico cifrados RMS tiene datos adjuntos (como un documento o en otro mensaje de correo electrónico) también se cifran, se descifrarán sólo el mensaje de correo electrónico de nivel superior.
    
- No se puede obtener una vista previa de un mensaje de correo electrónico cifrados de RMS. Para ver un mensaje cifrado, debe exportarlo.
    
- Si necesita impedir que alguien descifrar mensajes cifrados mediante RMS, tendrá que crear un grupo de roles personalizados (copiando el grupo de roles de administrador de exhibición de documentos integrado) y, a continuación, quite el rol de administración de RMS descifrar el grupo de roles personalizados. A continuación, agregue a la persona que no desea descifrar mensajes como un miembro del grupo de roles personalizados.
  
 ### <a name="filenames-of-exported-items"></a>Nombres de archivo de los elementos exportados
  
- Hay un límite de 260 caracteres (impuesto por el sistema operativo) para el nombre de ruta de acceso completa de los mensajes de correo electrónico y documentos del sitio exportados al equipo local. El nombre de ruta de acceso completa para elementos exportados incluye la ubicación del elemento original y la ubicación de la carpeta en el equipo local donde se descargan los resultados de búsqueda en. Por ejemplo, si se especifica para descargar los resultados de búsqueda para `C:\Users\Admin\Desktop\SearchResults` en la herramienta de exportación de exhibición de documentos electrónicos, a continuación, en la ruta de acceso completa de un elemento de correo electrónico descargado sería `C:\Users\Admin\Desktop\SearchResults\ContentSearch1\03.15.2017-1242PM\Exchange\sarad@contoso.com (Primary)\Top of Information Store\Inbox\Insider trading investigation.msg`.
    
    Si se supera el límite de 260 caracteres, se truncarán el nombre de ruta de acceso completa para un elemento.
    
  - Si el nombre de ruta de acceso completa es más de 260 caracteres, el nombre de archivo se truncará para obtener por debajo del límite; Tenga en cuenta que el nombre de archivo truncado (excluyendo la extensión de archivo) no sea menor que 8 caracteres.
    
  - Si el nombre de ruta de acceso completa aún es demasiado largo después acortar el nombre de archivo, el elemento se mueve desde su ubicación actual a la carpeta principal. Si la ruta de acceso aún es demasiado largo, a continuación, el proceso se repite: acortar el nombre de archivo, y si es necesario volver a mover a la carpeta principal. Este proceso se repite hasta que la ruta de acceso completa está bajo el límite de 260 caracteres.
    
  - Si ya existe un nombre de ruta de acceso completa truncadas, un número de versión se agregará al final del nombre de archivo; Por ejemplo, `statusmessage(2).msg`.
    
    Para ayudar a mitigar este problema, considere la posibilidad de descargar los resultados de búsqueda a una ubicación con un nombre de ruta de acceso corta; Por ejemplo, descargar los resultados de búsqueda en una carpeta denominada `C:\Results` agregaría menos caracteres a los nombres de ruta de acceso de los elementos exportados que descargarlas a una carpeta denominada `C:\Users\Admin\Desktop\Results`.
    
- Al exportar documentos del sitio, también es posible que se van a modificar el nombre de archivo original de un documento. Esto sucede específicamente para los documentos que se han eliminado de un SharePoint o OneDrive para el sitio de negocio que se han colocado en suspensión. Después de que se elimina un documento que se encuentra en un sitio que se encuentra en suspensión, documento eliminado se mueve automáticamente a la biblioteca de conservación suspensión para el sitio (que se creó cuando el sitio se pondrá en espera). Cuando el documento eliminado se mueve a la biblioteca de conservación suspensión, un identificador único y genera de forma aleatoria se anexa al nombre del archivo original del documento. Por ejemplo, si el nombre de archivo para un documento es `FY2017Budget.xlsx` y ese documento más adelante se elimina y se mueve a la biblioteca mantenga presionada la conservación, se modifica el nombre de archivo del documento que se mueve a la biblioteca de conservación suspensión a algo parecido a `FY2017Budget_DEAF727D-0478-4A7F-87DE-5487F033C81A2000-07-05T10-37-55.xlsx`. Si un documento en la biblioteca de conservación mantenga coincide con la consulta de búsqueda de contenido y exportar los resultados de la búsqueda, el archivo exportado tendrá el nombre de archivo modificado; en este ejemplo, el nombre de archivo del documento exportado sería `FY2017Budget_DEAF727D-0478-4A7F-87DE-5487F033C81A2000-07-05T10-37-55.xlsx`.
    
    Además, cuando se modifica un documento ubicado en un sitio que se encuentra en suspensión (y se ha habilitado el control de versiones para la biblioteca de documentos en el sitio), automáticamente se crea una copia del archivo en la biblioteca de conservación suspensión. En este caso, un identificador único y genera de forma aleatoria también se anexa al nombre de archivo del documento que se copia a la biblioteca de conservación suspensión.
    
    La razón por qué nombres de archivo de documentos que se mueven o se copian a la biblioteca de conservación mantenga es para evitar que los nombres de archivo en conflicto. Para obtener más información acerca de la colocación de una suspensión en sitios y la biblioteca de conservación suspensión, consulte [Overview of en contexto se mantenga en SharePoint Server 2016](https://support.office.com/article/5e400d68-cd51-444a-8fe6-e4df1d20aa95).
    
 ### <a name="miscellaneous"></a>Varios
  
- Todos los resultados de la búsqueda y los informes de exportación se incluyen en una carpeta que tiene el mismo nombre que la búsqueda de contenido. Los mensajes de correo electrónico que se han exportado se encuentran en una carpeta denominada **Exchange**. Documentos se encuentran en una carpeta denominada **SharePoint**. 
    
- Los metadatos del sistema de archivos de documentos en SharePoint y OneDrive para sitios de profesionales se mantienen cuando se exportan documentos en el equipo local. Que significa que las propiedades de documento, como se creó y modificó por última vez las fechas, no se cambian cuando se exportan documentos.

- Si los resultados de búsqueda incluyen un elemento de lista de SharePoint que coincida con la consulta de búsqueda, se exportan todas las filas en la lista además el elemento que coincida con la consulta de búsqueda. Esto incluye los datos adjuntos en la lista. El motivo de esto consiste en proporcionar un contexto para elementos de lista que se devuelven en los resultados de búsqueda. Tenga en cuenta también que los elementos de lista adicionales y los datos adjuntos pueden causar el recuento de elementos exportados a ser diferente de la estimación original de los resultados de búsqueda.
