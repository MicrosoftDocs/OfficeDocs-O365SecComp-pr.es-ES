---
title: Use la carga de red para importar los archivos PST de su organización a Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 103f940c-0468-4e1a-b527-cc8ad13a5ea6
description: 'Para los administradores: Obtenga información sobre cómo usar la carga de red para importar varios archivos PST a los buzones de usuario en Office 365.'
ms.openlocfilehash: 73123d5f36a01b31cfc38e6404bd400bb722fb36
ms.sourcegitcommit: f0e3c9de0b545081a4d264f74559b941f6c71410
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/22/2019
ms.locfileid: "31958581"
---
# <a name="use-network-upload-to-import-your-organization-pst-files-to-office-365"></a>Use la carga de red para importar los archivos PST de su organización a Office 365

> [!NOTE]
> Este artículo está destinado a los administradores. ¿Está intentando importar archivos PST a su propio buzón? Consulte [importar el correo electrónico, los contactos y el calendario desde un archivo. pst de Outlook](https://go.microsoft.com/fwlink/p/?LinkID=785075)
  
Estas son las instrucciones paso a paso necesarias para usar la carga de red para importar de forma masiva varios archivos PST a los buzones de correo de Office 365. Para conocer las preguntas más frecuentes sobre el uso de la carga de red para importar archivos PST en masa a los buzones de Office 365, consulte [FAQ para usar la carga de red para importar archivos PST](faqimporting-pst-files-to-office-365.md#using-network-upload-to-import-pst-files).
  
[Paso 1: copiar la URL de SAS e instalar Azure AzCopy](#step-1-copy-the-sas-url-and-install-azure-azcopy)

[Paso 2: cargar los archivos PST a Office 365](#step-2-upload-your-pst-files-to-office-365)

[Opcional Paso 3: ver una lista de los archivos PST cargados en Office 365](#optional-step-3-view-a-list-of-the-pst-files-uploaded-to-office-365)

[Paso 4: crear el archivo de asignación de importaciones de PST](#step-4-create-the-pst-import-mapping-file)

[Paso 5: crear un trabajo de importación de PST en Office 365](#step-5-create-a-pst-import-job-in-office-365)

[Paso 6: filtrar datos e iniciar el trabajo de importación de PST](#step-6-filter-data-and-start-the-pst-import-job)

Tenga en cuenta que solo tiene que realizar el paso 1 una vez para importar los archivos PST a los buzones de correo de Office 365. Después de realizar estos pasos, siga los pasos 2 a 6 cada vez que desee cargar e importar un lote de archivos PST.

## <a name="before-you-begin"></a>Antes de empezar
  
- Debe tener asignado el rol importación y exportación de buzones de correo en Exchange Online para importar archivos PST a los buzones de correo de Office 365. De forma predeterminada, este rol no está asignado a ningún grupo de roles en Exchange Online. You can add the Mailbox Import Export role to the Organization Management role group. Or you can create a new role group, assign the Mailbox Import Export role, and then add yourself as a member. Para obtener más información, vea las secciones "agregar un rol a un grupo de roles" o "crear un grupo de roles" en [Manage role Groups](https://go.microsoft.com/fwlink/p/?LinkId=730688).
    
    Además, para crear trabajos de importación en el centro de seguridad & cumplimiento, debe cumplirse una de las siguientes condiciones:
    
  - Debe tener asignado el rol destinatarios de correo en Exchange Online. By default, this role is assigned to the Organization Management and Recipient Management roles groups.
    
    O bien
    
  - Debe ser administrador global de la organización de Office 365.
    
  > [!TIP]
    > Considere la posibilidad de crear un nuevo grupo de roles en Exchange online que esté destinado específicamente a importar archivos PST a Office 365. Para el nivel mínimo de privilegios necesarios para importar archivos PST, asigne los roles Mailbox Import Export y mail Recipients al nuevo grupo de roles y, a continuación, agregue members. 
  
- El único método admitido para importar archivos PST a Office 365 es usar la herramienta AzCopy de Azure, tal y como se describe en este tema. No puede usar el explorador de Azure Storage para cargar archivos PST directamente en el área de almacenamiento de Azure.
    
- Debe almacenar los archivos PST que desea importar a Office 365 en un servidor de archivos o una carpeta compartida de la organización. En el paso 2, ejecutará la herramienta AzCopy de Azure para cargar los archivos PST que se almacenan en este servidor de archivos o carpeta compartida en Office 365.
    
- Este procedimiento implica copiar y guardar una copia de una dirección URL que contiene una clave de acceso. Esta información se usará en el paso 2 para cargar los archivos PST y, en el paso 3, si desea ver una lista de los archivos PST cargados en Office 365. Asegúrese de tomar precauciones para proteger esta dirección URL, como lo haría con las contraseñas u otra información relacionada con la seguridad. Por ejemplo, puede guardarla en un documento de Microsoft Word protegido con contraseña o en una unidad USB cifrada. Consulte la sección [More Information](#more-information) para ver un ejemplo de esta clave y URL combinadas. 
    
- Puede importar archivos PST a un buzón inactivo en Office 365. Para ello, especifique el GUID del buzón inactivo en el `Mailbox` parámetro del archivo de asignación de importaCIONES de PST. Consulte el paso 4 de la ficha **instrucciones** de este tema para obtener información. 
    
- En una implementación híbrida de Exchange, puede importar archivos PST a un buzón de archivo basado en la nube para un usuario cuyo buzón principal es local. Para ello, realice lo siguiente en el archivo de asignación de importaciones de PST:
    
  - Especifique la dirección de correo electrónico del buzón local del usuario en el `Mailbox` parámetro. 
    
  - Especifique el valor **true** en el `IsArchive` parámetro. 
    
    Consulte el [paso 4](#step-4-create-the-pst-import-mapping-file) para obtener más información. 
    
- Una vez que los archivos PST se importan a un buzón de correo de Office 365, la configuración de espera de retención del buzón de correo se activa durante un período de tiempo indefinido. Esto significa que la Directiva de retención asignada al buzón no se procesará hasta que desactive la suspensión de la retención o establezca una fecha para desactivar la retención. ¿Por qué hacemos esto? Si los mensajes importados a un buzón de correo son viejos, podrían eliminarse de forma permanente (purgarse) porque el período de retención ha expirado según la configuración de retención configurada para el buzón. Al colocar el buzón en suspensión de retención, el propietario del buzón podrá administrar estos mensajes recién importados o le dará tiempo para cambiar la configuración de retención del buzón. Consulte la ficha **más información** de este tema para obtener sugerencias sobre cómo administrar la suspensión de la retención. 
    
- De forma predeterminada, el tamaño máximo de mensaje que puede recibir un buzón de correo de Office 365 es de 35 MB. Esto se debe a que el valor predeterminado de la propiedad *MaxReceiveSize* para un buzón se establece en 35 MB. Sin embargo, el límite del tamaño máximo de recepción de mensajes en Office 365 es de 150 MB. Por lo tanto, si importa un archivo PST que contiene un elemento superior a 35 MB, el servicio de importación de Office 365 cambiará automáticamente el valor de la propiedad *MaxReceiveSize* en el buzón de destino a 150 MB. Esto permite que los mensajes de hasta 150 MB se importen a los buzones de usuario. 
    
    > [!TIP]
    > Para identificar el tamaño de recepción de un buzón de correo, puede ejecutar este comando en Exchange Online PowerShell `Get-Mailbox <user mailbox> | FL MaxReceiveSize`:. 

## <a name="step-1-copy-the-sas-url-and-install-azure-azcopy"></a>Paso 1: copiar la URL de SAS e instalar Azure AzCopy

El primer paso consiste en descargar e instalar la herramienta AzCopy de Azure, que es la herramienta que se ejecutará en el paso 2 para cargar los archivos PST a Office 365. También copiará la dirección URL de SAS de su organización. Esta dirección URL es una combinación de la dirección URL de red para la ubicación de almacenamiento de Azure en la nube de Microsoft para su organización y una clave de firma de acceso compartido (SAS). Esta clave le proporciona los permisos necesarios para cargar archivos PST en su ubicación de almacenamiento de Azure. Asegúrese de tomar precauciones para proteger la URL de SAS. Es único en su organización y se usará en el paso 2.

> [!IMPORTANT]
> Para importar archivos PST mediante el método de carga de red, se recomienda usar la versión de Azure AzCopy que se puede descargar en el paso 6B en el siguiente procedimiento.
  
1. Vaya a [https://protection.office.com](https://protection.office.com) e inicie sesión con las credenciales de una cuenta de administrador en la organización de Office 365. 
    
2. En el panel izquierdo del centro de seguridad & cumplimiento, haga clic en **importación**de **gobierno** \> de datos.
    
    > [!NOTE]
    > Debe tener asignados los permisos adecuados para acceder a la página **importar** en el centro de seguridad & cumplimiento. Vea la sección **antes de comenzar** para obtener más información. 
    
3. En la página **importar** , haga ![clic en](media/ITPro-EAC-AddIcon.gif) agregar icono **nuevo trabajo de importación**.
    
    Se mostrará el Asistente para importación de trabajos.
    
4. Escriba un nombre para el trabajo de importación de PST y, a continuación, haga clic en **siguiente**. Use letras minúsculas, números, guiones y caracteres de subrayado. No puede usar letras mayúsculas ni incluir espacios en el nombre.
    
5. En la página **¿desea cargar o enviar datos?** , haga clic en **cargar los datos** y, a continuación, haga clic en **siguiente**.
    
    ![Haga clic en cargar los datos para crear un trabajo de importación de carga de red](media/e59f9dc3-ccde-44ff-ac38-c4e39d76ae85.png)
  
6. En la página **importar datos** , siga estos dos pasos: 
    
    ![Copie la dirección URL de SAS y descargue la herramienta AzCopy de Azure en la página importar datos.](media/74411014-ec4b-4e25-9065-404c934cce17.png)
  
    a. En el paso 2, haga clic en **Mostrar dirección URL de carga de red SAS**. Una vez mostrada la dirección URL de SAS, haga clic en **copiar al** portapapeles y, a continuación, péguela y guárdela en un archivo para poder acceder a él más adelante.
    
    b. En el paso 3, haga clic en **Descargar Azure azcopy** para descargar e instalar la herramienta AzCopy de Azure. En la ventana emergente, haga clic en **Ejecutar** para instalar AzCopy. 
    
> [!NOTE]
> Puede dejar la página **importar datos** abierta (en caso de que necesite volver a copiar la dirección URL de SAS) o hacer clic en **Cancelar** para cerrarla. 
 
## <a name="step-2-upload-your-pst-files-to-office-365"></a>Paso 2: cargar los archivos PST a Office 365

Ahora está listo para usar la herramienta AzCopy. exe para cargar los archivos PST a Office 365. Esta herramienta las carga y almacena en una ubicación de almacenamiento de Azure en la nube de Microsoft. Como se ha explicado anteriormente, la ubicación de Azure Storage que se cargan los archivos PST reside en el mismo centro de información regional de Microsoft en el que se encuentra la organización 365 de Office. Para completar este paso, los archivos PST deben encontrarse en un recurso compartido de archivos o en un servidor de archivos de la organización. Esto se conoce como el directorio de origen en el siguiente procedimiento. Cada vez que ejecuta la herramienta AzCopy, puede especificar un directorio de origen diferente. 
  
1. Abra el símbolo del sistema del equipo local.
    
2. Vaya al directorio en el que instaló la herramienta AzCopy.exe en el paso 1. Si ha instalado la herramienta en la ubicación predeterminada, vaya a `%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy`.
    
3. Ejecute el siguiente comando para cargar los archivos PST a Office 365.

    ```
    AzCopy.exe /Source:<Location of PST files> /Dest:<SAS URL> /V:<Log file location> /Y
  
    ```
 
    > [!IMPORTANT] 
    > Debe especificar un directorio como la ubicación de origen en el comando anterior; no puede especificar un archivo PST individual. Se cargarán todos los archivos PST del directorio de origen.
 
    En la tabla siguiente se describen los parámetros de AzCopy. exe y sus valores necesarios. La información que ha obtenido en el paso anterior se usa en los valores de estos parámetros.
    
    |**Parámetro**|**Descripción**|**Ejemplo**|
    |:-----|:-----|:-----|
    | `/Source:` <br/> |Especifica el directorio de origen de la organización que contiene los archivos PST que se cargarán en Office 365.  <br/> No olvide incluir el valor de este parámetro entre comillas dobles (" ").  <br/> | `/Source:"\\FILESERVER01\PSTs"` <br/> |
    | `/Dest:` <br/> |Especifica la dirección URL de SAS que obtuvo en el paso 1.  <br/> No olvide incluir el valor de este parámetro entre comillas dobles (" ").  <br/> **Sugerencia:** Opcional Puede especificar una subcarpeta en la ubicación de Azure Storage para cargar los archivos PST. Para hacerlo, agregue una ubicación de subcarpeta (después de "ingestiondata") en la dirección URL de SAS. El primer ejemplo no especifica una subcarpeta; Esto significa que los archivos PST se cargarán en la raíz (denominada *ingestiondata* ) de la ubicación de almacenamiento de Azure. En el segundo ejemplo se cargan los archivos PST en una subcarpeta (denominada *PSTFiles* ) en la raíz de la ubicación de almacenamiento de Azure.  <br/> | `/Dest:"https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata?sv=2012-02-12&amp;se=9999-12-31T23%3A59%3A59Z&amp;sr=c&amp;si=IngestionSasForAzCopy201601121920498117&amp;sig=Vt5S4hVzlzMcBkuH8bH711atBffdrOS72TlV1mNdORg%3D"` <br/> O bien  <br/>  `/Dest:"https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata/PSTFiles?sv=2012-02-12&amp;se=9999-12-31T23%3A59%3A59Z&amp;sr=c&amp;si=IngestionSasForAzCopy201601121920498117&amp;sig=Vt5S4hVzlzMcBkuH8bH711atBffdrOS72TlV1mNdORg%3D"` <br/> |
    | `/V:` <br/> |Resulta en mensajes de estado detallados en un archivo de registro. De forma predeterminada, el archivo de registro detallado se denomina AzCopyVerbose.log en %LocalAppData%\Microsoft\Azure\AzCopy. Si especifica una ubicación de archivo existente para esta opción, el registro detallado se anexará a ese archivo.  <br/> No olvide incluir el valor de este parámetro entre comillas dobles (" ").  <br/> | `/V:"c:\Users\Admin\Desktop\Uploadlog.log"` <br/> |
    | `/S` <br/> |Este modificador opcional especifica el modo recursivo para que la herramienta AzCopy copie los archivos PST que se encuentran en las subcarpetas en el directorio de origen especificado por el `/Source:` parámetro.  <br/> **Nota:** Si incluye este modificador, los archivos PST en las subcarpetas tendrán un directorio de ruta de archivo diferente en la ubicación de almacenamiento de Azure después de que se carguen. Deberá especificar el directorio de ruta de archivo exacto en el archivo CSV que creará en el paso 4.  <br/> | `/S` <br/> |
    | `/Y` <br/> |Este modificador requiere el uso de tokens de SAS de solo escritura al cargar los archivos PST en la ubicación de almacenamiento de Azure. La dirección URL de SAS que obtuvo en el paso 1 ( `/Dest:` y que se especifica en el parámetro) es una dirección URL de SAS de solo escritura, que es la razón por la que debe incluir este modificador. Tenga en cuenta que una dirección URL de solo escritura de SAS no le impedirá usar el explorador de Azure Storage para ver una lista de los archivos PST cargados en la ubicación de almacenamiento de Azure.  <br/> | `/Y` <br/> |
   
A continuación se muestra un ejemplo de la sintaxis de la herramienta AzCopy.exe, en el que se usan valores reales para cada parámetro:
    
```
  AzCopy.exe /Source:"\\FILESERVER1\PSTs" /Dest:"https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata?sv=2012-02-12&amp;se=9999-12-31T23%3A59%3A59Z&amp;sr=c&amp;si=IngestionSasForAzCopy201601121920498117&amp;sig=Vt5S4hVzlzMcBkuH8bH711atBffdrOS72TlV1mNdORg%3D" /V:"c:\Users\Admin\Desktop\AzCopy1.log" /Y
  
```

Después de ejecutar el comando, aparecen mensajes de estado en los que se muestra el progreso de la carga de los archivos PST. En un mensaje de estado final aparece el número total de archivos cargados correctamente. 

> [!TIP]
> Una vez que haya ejecutado correctamente el comando AzCopy. exe y haya comprobado que todos los parámetros son correctos, guarde una copia de la sintaxis de la línea de comandos en el mismo archivo (seguro) donde copió la información que obtuvo en el paso 1. A continuación, puede copiar y pegar este comando en un símbolo del sistema cada vez que desee ejecutar la herramienta AzCopy. exe para cargar los archivos PST a Office 365. El único valor que puede que deba cambiar son los del `/Source:` parámetro. Esto depende del directorio de origen en el que están los archivos PST.

## <a name="optional-step-3-view-a-list-of-the-pst-files-uploaded-to-office-365"></a>Opcional Paso 3: ver una lista de los archivos PST cargados en Office 365

Como paso opcional, puede instalar y usar el explorador de almacenamiento de Microsoft Azure (que es una herramienta de código abierto gratuita) para ver la lista de los archivos PST que ha cargado en el BLOB de Azure. Hay dos motivos principales para esto:
  
- Compruebe que los archivos PST de la carpeta compartida o el servidor de archivos de la organización se hayan cargado correctamente en el BLOB de Azure.
    
- Compruebe el nombre de archivo (y la ruta de directorio de la subcarpeta si incluyó una) para cada archivo PST cargado en el BLOB de Azure. Esto es muy útil al crear el archivo de asignación de PST en el paso siguiente, ya que tendrá que especificar el nombre de ruta de la carpeta y el nombre de archivo de todos los archivos PST. Comprobar estos nombres puede ayudar a reducir posibles errores en el archivo de asignación de PST.
    
El explorador de almacenamiento de Microsoft Azure está en versión preliminar.
  
> [!IMPORTANT]
> No puede usar el explorador de Azure Storage para cargar o modificar archivos PST. El único método admitido para importar archivos PST a Office 365 es usar AzCopy. Además, no puede eliminar los archivos PST que ha cargado en el BLOB de Azure. Si intenta eliminar un archivo PST, recibirá un error sobre no tener los permisos necesarios. Tenga en cuenta que todos los archivos PST se eliminan automáticamente del área de almacenamiento de Azure. If there are no import jobs in progress, then all PST files in the **ingestiondata** container are deleted 30 days after the most recent import job was created.
  
Para instalar el explorador de almacenamiento de Azure y conectarse a su área de almacenamiento de Azure:
  
1. Descargue e instale la [herramienta Microsoft Azure Storage Explorer](https://go.microsoft.com/fwlink/p/?LinkId=544842).
    
2. Inicie el explorador de almacenamiento de Microsoft Azure, haga clic con el botón derecho en **cuentas de almacenamiento** en el panel izquierdo y, después, haga clic en **conectar a Azure Storage**.
    
    ![Haga clic con el botón secundario en cuentas de almacenamiento y haga clic en conectar a Azure Storage](media/75b80cc3-c336-4f96-ad32-54ac9b96a7af.png)
  
3. Haga clic en **usar un URI de firma de acceso compartido (SAS) o cadena de conexión** y haga clic en **siguiente**.
    
4. Haga clic en **usar un URI de SAS**, pegue la dirección URL de SAS que obtuvo en el paso 1 en el cuadro en **URI**y, a continuación, haga clic en **siguiente**.
    
5. En la página **Resumen de conexión** , puede revisar la información de conexión y, a continuación, hacer clic en **conectar**.
    
    El contenedor de **ingestiondata** se abre; contiene los archivos PST que cargó en el paso 2. El contenedor **ingestiondata** se encuentra en **contenedores de BLOB**de cuentas **** \> \> de **almacenamiento** (servicios adjuntos a SAS). 
    
    ![El explorador de almacenamiento de Azure muestra una lista de los archivos PST que ha cargado](media/12376fed-13a5-4a09-8fe6-e819e011b334.png)
  
6. Cuando haya terminado de usar el explorador de almacenamiento de Microsoft Azure, haga clic con el botón secundario en **ingestiondata**y, a continuación, haga clic en **desconectar** para desconectarse de su área de almacenamiento de Azure. En caso contrario, recibirá un error la próxima vez que intente conectarse. 
    
    ![Haga clic con el botón derecho en la ingesta y haga clic en Desasociar para desconectar de su área de almacenamiento de Azure](media/1e8e5e95-4215-4ce4-a13d-ab5f826a0510.png)
  
## <a name="step-4-create-the-pst-import-mapping-file"></a>Paso 4: crear el archivo de asignación de importaciones de PST

Una vez que los archivos PST se hayan cargado en la ubicación de almacenamiento de Azure para la organización de Office 365, el siguiente paso consiste en crear un archivo de valores separados por comas (CSV) que especifica a qué buzones de usuario se importarán los archivos PST. Enviará este archivo CSV en el paso siguiente al crear un trabajo de importación de PST.
  
1. [Descargue una copia del archivo de asignación de importaciones de PST](https://go.microsoft.com/fwlink/p/?LinkId=544717).
    
2. Abra o guarde el archivo CSV en el equipo local. En el ejemplo siguiente se muestra un archivo de asignación de importaciones de archivos PST completado (que se abre en el Bloc de notas). Es mucho más fácil usar Microsoft Excel para editar el archivo CSV.


    ```
    Workload,FilePath,Name,Mailbox,IsArchive,TargetRootFolder,ContentCodePage,SPFileContainer,SPManifestContainer,SPSiteUrl
    Exchange,,annb.pst,annb@contoso.onmicrosoft.com,FALSE,/,,,,
    Exchange,,annb_archive.pst,annb@contoso.onmicrosoft.com,TRUE,,,,,
    Exchange,,donh.pst,donh@contoso.onmicrosoft.com,FALSE,/,,,,
    Exchange,,donh_archive.pst,donh@contoso.onmicrosoft.com,TRUE,,,,,
    Exchange,PSTFiles,pilarp.pst,pilarp@contoso.onmicrosoft.com,FALSE,/,,,,
    Exchange,PSTFiles,pilarp_archive.pst,pilarp@contoso.onmicrosoft.com,TRUE,/ImportedPst,,,,
    Exchange,PSTFiles,tonyk.pst,tonyk@contoso.onmicrosoft.com,FALSE,,,,,
    Exchange,PSTFiles,tonyk_archive.pst,tonyk@contoso.onmicrosoft.com,TRUE,/ImportedPst,,,,
    Exchange,PSTFiles,zrinkam.pst,zrinkam@contoso.onmicrosoft.com,FALSE,,,,,
    Exchange,PSTFiles,zrinkam_archive.pst,zrinkam@contoso.onmicrosoft.com,TRUE,/ImportedPst,,,,
    ```
    En la primera fila (o la primera fila de encabezado) del archivo CSV aparecen los parámetros que usará el servicio de importación de PST para importar los archivos PST a los buzones de los usuarios. Los nombres de los parámetros están separados por comas. Cada fila situada debajo de la fila de encabezado representa los valores de parámetro para importar un archivo PST a un buzón específico. Necesitará una fila para cada archivo PST al que desee importar un buzón de usuario. No olvide reemplazar los datos de los marcadores de posición del archivo de asignación por los datos reales.

   **Nota:** No cambie nada en la fila de encabezado, incluidos los parámetros de SharePoint; se omitirán durante el proceso de importación de PST. 

 3. Use la información de la tabla siguiente para rellenar el archivo CSV con la información necesaria.


    |**Parámetro**|**Descripción**|**Ejemplo**|
    |:-----|:-----|:-----|
    | `Workload` <br/> |Especifica el servicio de Office 365 al que se importarán los datos. Para importar archivos PST a los buzones de usuario `Exchange`, use.  <br/> | `Exchange` <br/> |
    | `FilePath` <br/> |Especifica la ubicación de la carpeta en la ubicación de almacenamiento de Azure en la que cargó los archivos PST en el paso 2.  <br/> Si no incluyó un nombre de subcarpeta opcional en la dirección URL de SAS en `/Dest:` el parámetro en el paso 2, deje este parámetro en blanco en el archivo CSV. Si incluyó un nombre de subcarpeta, debe especificarlo en este parámetro (vea el segundo ejemplo). El valor de este parámetro distingue mayúsculas de minúsculas.  <br/> En cualquier caso, *no* incluya "ingestiondata" en el valor del `FilePath` parámetro.  <br/><br/> **Importante:** El caso del nombre de la ruta de acceso del archivo debe ser el mismo que usó si incluyó un nombre de subcarpeta opcional en la dirección URL de SAS `/Dest:` en el parámetro en el paso 2. Por ejemplo, si ha usado `PSTFiles` para el nombre de la subcarpeta en el paso 2 y `pstfiles` , a `FilePath` continuación, usa en el parámetro en el archivo CSV, se producirá un error en la importación del archivo pst. Asegúrese de usar el mismo caso en ambas instancias.  <br/> |(se deja en blanco)  <br/> O bien  <br/>  `PSTFiles` <br/> |
    | `Name` <br/> |Especifica el nombre del archivo PST que se importará al buzón del usuario.  El valor de este parámetro distingue mayúsculas de minúsculas.  <br/> <br/>**Importante:** El caso del nombre de archivo PST en el archivo CSV debe ser el mismo que el archivo PST que se cargó en la ubicación de almacenamiento de Azure en el paso 2. Por ejemplo, si usa `annb.pst` en el `Name` parámetro del archivo CSV, pero el nombre del archivo pst real `AnnB.pst`, se producirá un error en la importación de ese archivo pst. Asegúrese de que el nombre del archivo PST en el archivo CSV use el mismo caso que el archivo PST real.  <br/> | `annb.pst` <br/> |
    | `Mailbox` <br/> |Especifica la dirección de correo electrónico del buzón en el que se importará el archivo PST.  Tenga en cuenta que no puede especificar una carpeta pública porque el servicio de importación de PST no admite la importación de archivos PST a carpetas públicas.  <br/> Para importar un archivo PST a un buzón inactivo, tiene que especificar el GUID de buzón para este parámetro. Para obtener este GUID, ejecute el siguiente comando de PowerShell en Exchange Online:`Get-Mailbox <identity of inactive mailbox> -InactiveMailboxOnly | FL Guid` <br/> <br/>**Nota:** En algunos casos, puede tener varios buzones con la misma dirección de correo electrónico, donde un buzón es un buzón activo y el otro buzón está en un estado eliminado temporalmente (o inactivo). En estas situaciones, tiene que especificar el GUID del buzón para identificar de forma exclusiva el buzón en el que se va a importar el archivo PST. Para obtener este GUID para buzones activos, ejecute el siguiente comando de PowerShell `Get-Mailbox <identity of active mailbox> | FL Guid`:. Para obtener el GUID de los buzones eliminados temporalmente (o inactivos), ejecute `Get-Mailbox <identity of soft-deleted or inactive mailbox> -SoftDeletedMailbox | FL Guid`este comando.  <br/> | `annb@contoso.onmicrosoft.com` <br/> O bien  <br/>  `2d7a87fe-d6a2-40cc-8aff-1ebea80d4ae7` <br/> |
    | `IsArchive` <br/> | Especifica si se va a importar o no el archivo PST en el buzón de archivo del usuario. Hay dos opciones:  <br/><br/>**False** : importa el archivo pst en el buzón de correo principal del usuario.  <br/> **True** : importa el archivo pst en el buzón de archivo del usuario. This assumes that the [user's archive mailbox is enabled](enable-archive-mailboxes.md). <br/><br/>Si establece este parámetro en `TRUE` y el buzón de archivo del usuario no está habilitado, se producirá un error en la importación para ese usuario. Tenga en cuenta que si se produce un error en la importación de un usuario (porque el archivo no está `TRUE`habilitado y esta propiedad se establece en), los demás usuarios del trabajo de importación no se verán afectados.  <br/>  If you leave this parameter blank, the PST file is imported to the user's primary mailbox.  <br/> <br/>**Nota:** Para importar un archivo PST a un buzón de archivo basado en la nube para un usuario cuyo buzón de correo principal es local, `TRUE` solo tiene que especificar para este parámetro y especificar la dirección de correo electrónico del buzón local del `Mailbox` usuario para el parámetro.  <br/> | `FALSE` <br/> O bien  <br/>  `TRUE` <br/> |
    | `TargetRootFolder` <br/> | Especifica la carpeta de buzón de correo a la que se importa el archivo PST.  <br/>  Si deja este parámetro en blanco, el archivo PST se importará a una nueva carpeta **** denominada importada que se encuentre en el nivel raíz del buzón de correo (el mismo nivel que la carpeta Bandeja de entrada y las otras carpetas de buzón de correo predeterminadas).  <br/>  Si especifica `/`, los elementos del archivo pst se importarán directamente en la carpeta Bandeja de entrada del usuario.  <br/><br/>  Si especifica `/<foldername>`, los elementos del archivo pst se importarán a una carpeta llamada * \<NombreCarpeta\> * . Por ejemplo, si usa `/ImportedPst`, los elementos se importarán a una carpeta denominada **ImportedPst**. Esta carpeta se ubicará en el buzón del usuario en el mismo nivel que la carpeta Bandeja de entrada.  <br/><br/> **Sugerencia:** Considere la posibilidad de ejecutar algunos lotes de prueba para experimentar con este parámetro, de modo que pueda determinar la mejor ubicación de la carpeta en la que se van a importar los archivos PST.  <br/> |(se deja en blanco)  <br/> O bien  <br/>  `/` <br/> O bien  <br/>  `/ImportedPst` <br/> |
    | `ContentCodePage` <br/> |Este parámetro opcional especifica un valor numérico para la página de códigos que se va a usar para importar archivos PST en el formato de archivo ANSI. Este parámetro se usa para importar archivos PST desde organizaciones de chino, Japonés y Coreano (CJK) porque estos idiomas suelen usar un juego de caracteres de doble byte (DBCS) para la codificación de caracteres. Si este parámetro no se usa para importar archivos PST para idiomas que usan DBCS para nombres de carpeta de buzón de correo, los nombres de carpeta suelen ser ilegibles una vez importados.  <br/><br/> Para obtener una lista de los valores admitidos que se deben usar para este parámetro, consulte identificadores de [Página de códigos](https://go.microsoft.com/fwlink/p/?LinkId=328514).  <br/> <br/>**Nota:** Como se mencionó anteriormente, este es un parámetro opcional y no es necesario incluirlo en el archivo CSV. O puede incluirlo y dejar el valor en blanco para una o más filas.  <br/> |(se deja en blanco)  <br/> O bien  <br/>  `932`(que es el identificador de la página de códigos para ANSI/OEM japonés)  <br/> |
    | `SPFileContainer` <br/> |Para la importación de archivos PST, deje este parámetro en blanco.   <br/> |No aplicable  <br/> |
    | `SPManifestContainer` <br/> |Para la importación de archivos PST, deje este parámetro en blanco.   <br/> |No aplicable  <br/> |
    | `SPSiteUrl` <br/> |Para la importación de archivos PST, deje este parámetro en blanco.   <br/> |No aplicable  <br/> |

## <a name="step-5-create-a-pst-import-job-in-office-365"></a>Paso 5: crear un trabajo de importación de PST en Office 365

El siguiente paso es crear el trabajo de importación de PST en el servicio de importación en Office 365. Como se ha explicado anteriormente, enviará el archivo de asignación de importaciones de PST que creó en el paso 4. Después de crear el nuevo trabajo, Office 365 analiza los datos de los archivos PST y, a continuación, le ofrece la oportunidad de filtrar los datos que se importan realmente a los buzones especificados en el archivo de asignación de importaciones de PST (vea el [paso 6](#step-6-filter-data-and-start-the-pst-import-job)).
  
1. Vaya a [https://protection.office.com](https://protection.office.com) e inicie sesión con las credenciales de una cuenta de administrador en la organización de Office 365. 
    
2. En el panel izquierdo del centro de seguridad & cumplimiento, haga clic en **gobierno de datos** y, a continuación, en **importar**.
    
3. En la página **importar** , haga ![clic en](media/ITPro-EAC-AddIcon.gif) agregar icono **nuevo trabajo de importación**.
    
    **Nota:** Debe tener asignados los permisos adecuados para acceder a la página **importar** en el centro de seguridad & cumplimiento para crear un nuevo trabajo de importación. Vea la sección **antes de comenzar** para obtener más información. 
    
4. Escriba un nombre para el trabajo de importación de PST y, a continuación, haga clic en **siguiente**. Use letras minúsculas, números, guiones y caracteres de subrayado. No puede usar letras mayúsculas ni incluir espacios en el nombre.
    
5. En la página **¿desea cargar o enviar datos?** , haga clic en **cargar los datos** y, a continuación, haga clic en **siguiente**.
    
    ![Haga clic en cargar los datos para crear un trabajo de importación de carga de red](media/e59f9dc3-ccde-44ff-ac38-c4e39d76ae85.png)
  
6. En el paso 4 de la página **importar datos** , haga clic en las casillas de verificación estoy **listo para cargar mis archivos** y **tengo acceso al archivo de asignación** y, a continuación, haga clic en **siguiente**.
    
    ![Haga clic en las dos casillas de verificación del paso 4](media/9f2427e8-3af2-4e27-95e6-a9f08430d3d8.png)
  
7. En la página **seleccionar el archivo de asignación** , haga clic en **Seleccionar archivo de asignación** para enviar el archivo de asignación de importaciones de PST que creó en el paso 4. 
    
    ![Haga clic en seleccionar archivo de asignación para enviar el archivo CSV que ha creado para el trabajo de importación](media/d30b1d73-80bb-491e-a642-a21673d06889.png)
  
8. Una vez que el nombre del archivo CSV aparezca en **nombre del archivo de asignación**, haga clic en **validar** para comprobar si hay errores en el archivo CSV. 
    
    ![Haga clic en validar para comprobar si hay errores en el archivo CSV.](media/4680999d-5538-4059-b878-2736a5445037.png)
  
    El archivo CSV debe estar validado correctamente para poder crear un trabajo de importación de PST. Nota el nombre del archivo se cambia a verde una vez validado correctamente. Si se produce un error en la validación, haga clic en el vínculo **Ver registro** . Se abre un informe de errores de validación, con un mensaje de error para cada fila del archivo en la que se produjo un error. 
    
9. Una vez validado correctamente el archivo de asignación de PST, lea el documento de términos y condiciones y, a continuación, haga clic en la casilla.
    
10. Haga clic en **Guardar** para enviar el trabajo y, a continuación, haga clic en **cerrar** cuando el trabajo se haya creado correctamente. 
    
    Se muestra una página de control de estado, con un estado de **análisis en curso** y el nuevo trabajo de importación en la lista de la página **importar** . 
    
11. Haga **** ![clic en el](media/O365-MDM-Policy-RefreshIcon.gif) icono Actualizar actualización para actualizar la información de estado que se muestra en la columna **Estado** . Cuando se completa el análisis y los datos están listos para importarse, el estado cambia a **análisis completado**.
    
    Puede hacer clic en el trabajo de importación para mostrar la página de control flotante, que contiene información más detallada sobre el trabajo de importación, como el estado de cada archivo PST que aparece en el archivo de asignación.
 
## <a name="step-6-filter-data-and-start-the-pst-import-job"></a>Paso 6: filtrar datos e iniciar el trabajo de importación de PST

Después de crear el trabajo de importación en el paso 5, Office 365 analiza los datos de los archivos PST (de forma segura y segura) mediante la identificación de la antigüedad de los elementos y los distintos tipos de mensajes incluidos en los archivos PST. Cuando se completa el análisis y los datos están listos para importar, tiene la opción de importar todos los datos contenidos en los archivos PST o puede recortar los datos que se importan al establecer filtros que controlan qué datos se importan.
  
1. En la página **importar** del centro de seguridad & cumplimiento, haga clic en **listo para importar a Office 365** para el trabajo de importación que ha creado en el paso 5. 
    
    ![Haga clic en listo para importar a Office 365 junto al trabajo de importación que ha creado.](media/5760aac3-300b-4e31-b894-253c42a4b82b.png)
  
    Se muestra una página emergente con información sobre los archivos PST y otra información sobre el trabajo de importación.
    
2. En la página flotante, haga clic en **importar a Office 365**.
    
    Se mostrará la página **filtrar los datos** . Contiene los datos resultantes del análisis realizado en los archivos PST por Office 365, incluida la información sobre la antigüedad de los datos. En este punto, tiene la opción de filtrar los datos que se importarán o importar todos los datos tal y como están. 
    
    ![Puede recortar los datos de los archivos PST o importarlos todos](media/287fc030-99e9-417b-ace7-f64617ea5d4e.png)
  
3. Siga uno de los procedimientos siguientes:
    
    a. Para recortar los datos que se van a importar, haga clic en **sí, deseo filtrarlos antes**de importarlos.
    
    Para obtener instrucciones detalladas paso a paso sobre cómo filtrar los datos de los archivos PST y, a continuación, iniciar el trabajo de importación, vea [filtrar datos al importar archivos PST a Office 365](filter-data-when-importing-pst-files.md).
    
    O bien
    
    b. Para importar todos los datos de los archivos PST, haga clic en **no, deseo importar todo y,** a continuación, haga clic en **siguiente**.
    
4. Si decidió importar todos los datos, haga clic en **importar datos** para iniciar el trabajo de importación. 
    
    El estado del trabajo de importación se muestra en la página **importar** . Haga ![clic en](media/O365-MDM-Policy-RefreshIcon.gif) actualizar icono **Actualizar** para actualizar la información de estado que se muestra en la columna **Estado** . Haga clic en el trabajo de importación para mostrar la página de control flotante de estado, que muestra la información de estado de cada archivo PST que se está importando. 

## <a name="how-the-import-process-works"></a>Cómo funciona el proceso de importación
  
Puede usar la opción de carga en la red y el servicio de importación de Office 365 para importar archivos PST en masa a los buzones de usuario. Carga de red significa que se cargan los archivos PST en un área de almacenamiento temporal en la nube de Microsoft. A continuación, el servicio de importación de Office 365 copia los archivos PST del área de almacenamiento en los buzones de usuario de destino.
  
A continuación, se muestra una ilustración y una descripción del proceso de carga de red para importar archivos PST a los buzones en Office 365.
  
![Flujo de trabajo del proceso de carga de red para importar archivos PST a Office 365](media/9e05a19e-1e7a-4f1f-82df-9118f51588c4.png)
  
1. **Descargue la herramienta de importación de PST y la clave en una ubicación de almacenamiento de Azure privada** : el primer paso consiste en descargar la herramienta de línea de comandos de Azure AzCopy y una clave de acceso que se usa para cargar los archivos PST en una ubicación de almacenamiento de Azure en la nube de Microsoft. Puede obtenerlos en la página **importar** en el centro de seguridad & cumplimiento. La clave (denominada una clave de firma de acceso seguro (SAS) le proporciona los permisos necesarios para cargar archivos PST en una ubicación de almacenamiento seguro y privada de Azure. Esta clave de acceso es única para su organización y ayuda a impedir el acceso no autorizado a los archivos PST una vez que se cargan en la nube de Microsoft. Tenga en cuenta que la importación de archivos PST a Office 365 no requiere que la organización tenga una suscripción a Azure independiente. 
    
2. **Cargar los archivos PST en la ubicación de almacenamiento de Azure** : el siguiente paso consiste en usar la herramienta AzCopy. exe (descargada en el paso 1) para cargar y almacenar los archivos PST en una ubicación de almacenamiento de Azure que resida en el mismo centro de información regional de Microsoft donde se encuentra Office 365 se encuentra la organización. Para cargarlos, los archivos PST que desea importar a Office 365 deben encontrarse en un recurso compartido de archivos o en un servidor de archivos de la organización.
    
    Tenga en cuenta que hay un paso opcional que puede realizar para ver la lista de los archivos PST una vez cargados en la ubicación de almacenamiento de Azure.
    
3. **Crear un archivo de asignación** de importaciones de PST: una vez cargados los archivos PST en la ubicación de almacenamiento de Azure, el siguiente paso consiste en crear un archivo de valores separados por comas (CSV) que especifica a qué buzones de usuario se importarán los archivos PST, tenga en cuenta que un archivo pst se puede  se importa al buzón de correo principal de un usuario o a su buzón de archivo. El servicio de importación de Office 365 usará la información del archivo CSV para importar los archivos PST.
    
4. **Crear un trabajo de importación de PST** : el siguiente paso consiste en crear un trabajo de importación de PST en la página **importar** del centro de seguridad & cumplimiento y enviar el archivo de asignación de importaciones de PST creado en el paso anterior. Después de crear el trabajo de importación, Office 365 analiza los datos de los archivos PST y, a continuación, le ofrece la oportunidad de establecer filtros que controlan qué datos se importan realmente a los buzones especificados en el archivo de asignación de importaciones de PST. 
    
5. **Filtrar los datos PST que se importarán a** los buzones: una vez que se ha creado e iniciado el trabajo de importación, Office 365 analiza los datos de los archivos PST (con seguridad y de forma segura) mediante la identificación de la antigüedad de los elementos y los distintos tipos de mensajes incluidos en los archivos PST. . Cuando se completa el análisis y los datos están listos para importar, tiene la opción de importar todos los datos contenidos en los archivos PST o puede recortar los datos que se importan al establecer filtros que controlan qué datos se importan.
    
6. **Inicie el trabajo de importación de PST** : una vez iniciado el trabajo de importación, Office 365 usa la información del archivo de asignación de importaCIONES de PST para importar los archivos PST de la ubicación de Azure Storage a los buzones de usuario. La información de estado sobre el trabajo de importación (incluida la información sobre cada uno de los archivos PST que se está importando) se muestra en la página **importar** del centro de seguridad & cumplimiento. Una vez finalizado el trabajo de importación, el estado del trabajo se establece en **completado**.
  
## <a name="more-information"></a>Más información

- ¿Por qué importar archivos PST a Office 365?
    
  - Es una buena forma de importar los datos de mensajería de archivado de su organización a Office 365.
    
  - Los datos están disponibles para el usuario en todos los dispositivos, ya que se almacenan en la nube.
    
  - Ayuda a satisfacer las necesidades de cumplimiento de su organización al permitirle aplicar las características de cumplimiento de Office 365 a los datos de los archivos PST que importó. Esto incluye:
    
  - Habilitar los buzones de [archivo](enable-archive-mailboxes.md) y [el archivado de expansión automática](enable-unlimited-archiving.md) para dar a los usuarios espacio de almacenamiento adicional en el buzón de correo para almacenar los datos importados. 
    
  - Colocar buzones en retención por [juicio](https://go.microsoft.com/fwlink/?linkid=856286) para conservar los datos importados. 
    
  - Usar [las herramientas de eDiscovery](search-for-content.md) de Microsoft para buscar los datos que importó. 
    
  - Uso de [las directivas de retención de Office 365](retention-policies.md) para controlar el tiempo que se conservarán los datos importados y las acciones que se deben tomar una vez que expire el período de retención. 
    
  - Buscar en el [registro de auditoría de Office 365](search-the-audit-log-in-security-and-compliance.md) los eventos relacionados con buzones que afectan a los datos importados. 
    
  - Importar datos a [buzones](create-and-manage-inactive-mailboxes.md) inactivos para archivar datos con fines de cumplimiento. 
    
  - Uso de [directivas de prevención de pérdida de datos](data-loss-prevention-policies.md) para impedir la pérdida de datos confidenciales fuera de la organización. 
  
- A continuación, se muestra un ejemplo de la dirección URL de la firma de acceso compartido (SAS) que se obtiene en el paso 1. Este ejemplo también contiene la sintaxis del comando que se ejecuta en la herramienta AzCopy. exe para cargar los archivos PST a Office 365. Asegúrese de tomar precauciones para proteger la dirección URL de SAS al igual que lo haría para proteger contraseñas u otra información relacionada con la seguridad.

    ```
    SAS URL: https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata?sv=2012-02-12&amp;se=9999-12-31T23%3A59%3A59Z&amp;sr=c&amp;si=IngestionSasForAzCopy201601121920498117&amp;sig=Vt5S4hVzlzMcBkuH8bH711atBffdrOS72TlV1mNdORg%3D

    AzCopy.exe /Source:<Location of PST files> /Dest:<SAS URL> /V:<Log file location> /Y

    EXAMPLES

    This example uploads PST files to the root of the Azure storage location:

    AzCopy.exe /Source:"\\FILESERVER1\PSTs" /Dest:"https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata?sv=2012-02-12&amp;se=9999-12-31T23%3A59%3A59Z&amp;sr=c&amp;si=IngestionSasForAzCopy201601121920498117&amp;sig=Vt5S4hVzlzMcBkuH8bH711atBffdrOS72TlV1mNdORg%3D" /V:"c:\Users\Admin\Desktop\AzCopy1.log" /Y
    
    This example uploads PST files to a subfolder named PSTFiles  in the Azure storage location:

    AzCopy.exe /Source:"\\FILESERVER1\PSTs" /Dest:"https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata/PSTFiles?sv=2012-02-12&amp;se=9999-12-31T23%3A59%3A59Z&amp;sr=c&amp;si=IngestionSasForAzCopy201601121920498117&amp;sig=Vt5S4hVzlzMcBkuH8bH711atBffdrOS72TlV1mNdORg%3D" /V:"c:\Users\Admin\Desktop\AzCopy1.log" /Y
``

- As previously explained, the Office 365 Import service turns on the retention hold setting (for an indefinite duration) after PST files are imported to a mailbox. This means the  *RetentionHoldEnabled*  property is set to  **True** so that the retention policy assigned to the mailbox won't be processed. This gives the mailbox owner time to manage the newly-imported messages by preventing a deletion or archive policy from deleting or archiving older messages. Here are some steps you can take to manage this retention hold: 
    
    - After a certain period of time, you can turn off the retention hold by running the **Set-Mailbox -RetentionHoldEnabled $false** command. For instructions, see [Place a mailbox on retention hold](https://go.microsoft.com/fwlink/p/?LinkId=544749).
    
   - You can configure the retention hold so that it's turned off on some date in the future. You do this by running the **Set-Mailbox -EndDateForRetentionHold *date*** command. For example, assuming that today's date is June 1, 2016 and you want the retention hold turned off in 30 days, you would run the following command:  **Set-Mailbox -EndDateForRetentionHold 7/1/2016**. In this scenario, you would leave the  **RetentionHoldEnabled**  property set to  *True*. For more information, see [Set-Mailbox](https://go.microsoft.com/fwlink/p/?LinkId=150317).
    
   - You can change the settings for the retention policy that's assigned to the mailbox so that older items that were imported won't be immediately deleted or moved to the user's archive mailbox. For example, you could lengthen the retention age for a deletion or archive policy that's assigned to the mailbox. In this scenario, you would turn off the retention hold on the mailbox after you changed the settings of the retention policy. For more information, see [Set up an archive and deletion policy for mailboxes in your Office 365 organization](set-up-an-archive-and-deletion-policy-for-mailboxes.md).
    
