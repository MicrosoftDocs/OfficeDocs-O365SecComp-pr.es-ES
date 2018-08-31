---
title: Use la carga de red para importar los archivos PST de organización a Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/29/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 103f940c-0468-4e1a-b527-cc8ad13a5ea6
description: 'Para los administradores: Aprenda a usar la carga de red para la importación masiva de varios archivos PST a buzones de usuario en Office 365.'
ms.openlocfilehash: c5bcaed9075939d098ac4bf9fbf4d8a94007232c
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22535948"
---
# <a name="use-network-upload-to-import-your-organization-pst-files-to-office-365"></a>Use la carga de red para importar los archivos PST de organización a Office 365

> [!NOTE]
> En este artículo está dirigido a administradores. ¿Está intentando importar archivos PST en su propio buzón? Consulte el [correo electrónico de importación, contactos y calendario desde un archivo .pst de Outlook](https://go.microsoft.com/fwlink/p/?LinkID=785075)
  
Aquí están las instrucciones paso a paso necesarias para usar la carga de red para la importación masiva de varios archivos PST a buzones de correo de Office 365. Para las preguntas más frecuentes sobre el uso de carga de red para la importación masiva de archivos PST a buzones de correo de Office 365, vea [las preguntas más frecuentes para el uso de carga de red para importar los archivos PST](faqimporting-pst-files-to-office-365.md#using-network-upload-to-import-pst-files).
  
[Paso 1: Copie la dirección URL de SAS e instalar AzCopy de Azure](#step-1-copy-the-sas-url-and-install-azure-azcopy)

[Paso 2: Cargar los archivos PST a Office 365](#step-2-upload-your-pst-files-to-office-365)

[(Opcional) Paso 3: Ver una lista de los archivos PST cargado a Office 365](#optional-step-3-view-a-list-of-the-pst-files-uploaded-to-office-365)

[Paso 4: Crear el archivo de asignación de importación de PST](#step-4-create-the-pst-import-mapping-file)

[Paso 5: crear un trabajo de importación de PST en Office 365](#step-5-create-a-pst-import-job-in-office-365)

[Paso 6: Filtrar datos e iniciar el trabajo de importación de PST](#step-6-filter-data-and-start-the-pst-import-job)

Tenga en cuenta que tendrá que realizar el paso 1 sólo una vez para importar los archivos PST a buzones de correo de Office 365. Después de realizar estos pasos, siga el paso 2 a 6 cada vez que desee cargar e importar un lote de archivos PST.

## <a name="before-you-begin"></a>Antes de empezar
  
- Se debe asignar la función de importación de exportación de buzones de correo en Exchange en línea para importar archivos PST a buzones de Office 365. De forma predeterminada, este rol no está asignado a ningún grupo de funciones en Exchange Online. Puede agregar la función de exportación de importación de buzón de correo para el grupo de roles de administración de la organización. O bien, puede crear un nuevo grupo de roles, asignar el rol de buzón de correo importar exportar y, a continuación, agregue a usted como un miembro. Para obtener más información, vea el "Agregar un rol a un grupo de roles" o la "crear un grupo de roles" secciones en [Administrar grupos de roles](https://go.microsoft.com/fwlink/p/?LinkId=730688).
    
    Además crear la importación de trabajos en la seguridad de Office 365 &amp; debe ser verdadero centro de cumplimiento, uno de los siguientes:
    
  - Se debe tener asignado el rol de destinatarios de correo en Exchange Online. De forma predeterminada, este rol se asigna a los grupos de funciones de administración de la organización y administración de destinatarios.
    
    O bien
    
  - Debe ser un administrador global de la organización de Office 365.
    
  > [!TIP]
    > Considere la posibilidad de crear un nuevo grupo de funciones en Exchange Online diseñada específicamente para la importación de los archivos PST a Office 365. Para el nivel mínimo de privilegios necesarios para importar los archivos PST, asigne las funciones de importación de exportación de buzones de correo y destinatarios de correo para el nuevo grupo de roles y, a continuación, agregar a miembros. 
  
- El único método admitido para la importación de los archivos PST a Office 365 es usar la herramienta de AzCopy de Azure, tal como se describe en este tema. No puede usar el Explorador de almacenamiento de Azure para cargar los archivos PST directamente en el área de almacenamiento de Azure.
    
- Que se necesita para almacenar los archivos PST que desea importar a Office 365 en un servidor de archivos o la carpeta compartida en la organización. En el paso 2, ejecutará la herramienta de Azure AzCopy que se van a cargar los archivos PST que se almacenan en este servidor de archivo o carpeta a Office 365 comparten.
    
- Este procedimiento implica copiar y guardar una copia de una dirección URL que contiene una tecla de acceso. Esta información se utilizará en el paso 2 para cargar los archivos PST y, en el paso 3 si desea ver una lista de los archivos PST que se cargan en Office 365. Asegúrese de tomar precauciones para proteger esta dirección URL como haría proteger las contraseñas u otra información relacionada con la seguridad. Por ejemplo puede guardar en un documento de Microsoft Word protegidos con contraseña o en una unidad USB cifrada. Vea que la sección [obtener más información](#more-information) para obtener un ejemplo de esto combinado clave y la dirección URL. 
    
- Puede importar archivos PST a un buzón de correo inactivo en Office 365. Para ello, que especifica el GUID del buzón de correo inactivo en el `Mailbox` parámetro en el archivo de asignación de importación de PST. En la ficha **instrucciones** de este tema para obtener información, consulte el paso 4. 
    
- En una implementación híbrida de Exchange, puede importar archivos PST en un buzón de archivo basados en la nube para un usuario cuyo buzón de correo principal es local. Para ello, hacer lo siguiente en el archivo de asignación de importación de PST:
    
  - Especifique la dirección de correo electrónico para el buzón del usuario local en el `Mailbox` parámetro. 
    
  - Especificar el valor **TRUE** en el `IsArchive` parámetro. 
    
    Para obtener más información, consulte el [paso 4](#step-4-create-the-pst-import-mapping-file) . 
    
- Una vez que se importan los archivos PST en un buzón de Office 365, la suspensión de retención establecer para el buzón de correo está activada para una duración indefinida. Esto significa que no se procesará la directiva de retención asignada al buzón hasta que se desactiva la suspensión de retención o establecer una fecha para desactivar la suspensión. ¿Por qué hacemos esto? Si los mensajes que se importa a un buzón de correo son anteriores, se podría eliminar permanentemente (purga) debido a que ha caducado su período de retención en función de la configuración de retención configurada para el buzón de correo. Colocar el buzón de correo en suspensión de retención, le dará el tiempo de propietario del buzón de correo para administrar estos mensajes recién importadas o ceder mucho tiempo para cambiar la configuración de retención para el buzón de correo. Vea la ficha de **más información** en este tema para obtener sugerencias acerca de cómo administrar la suspensión de retención. 
    
- De forma predeterminada, el tamaño máximo de mensaje que se puede recibir un buzón de Office 365 es 35 MB. Eso es porque el valor predeterminado para la propiedad *MaxReceiveSize* para un buzón de correo se establece en 35 MB. Sin embargo, el límite de tamaño de recepción el máximo de mensaje en Office 365 es 150 MB. Por tanto, si importa un archivo PST que contiene un elemento más de 35 MB, el servicio Office 365 importar se cambiará automáticamente el valor de la propiedad *MaxReceiveSize* en el buzón de destino a 150 MB. Esto permite que los mensajes que se debe importar a buzones de usuario hasta 150 MB. 
    
    > [!TIP]
    > Para identificar el mensaje de tamaño de recepción para un buzón de correo, se puede ejecutar este comando en Exchange Online PowerShell: `Get-Mailbox <user mailbox> | FL MaxReceiveSize`. 

### <a name="step-1-copy-the-sas-url-and-install-azure-azcopy"></a>Paso 1: Copie la dirección URL de SAS e instalar AzCopy de Azure

El primer paso es descargar e instalar la herramienta de AzCopy de Azure, que es la herramienta que se ejecutará en el paso 2 para cargar archivos de PST a Office 365. También podrá copiar la dirección URL de SAS para su organización. Esta dirección URL es una combinación de la dirección URL de red para la ubicación de almacenamiento de Azure en la nube de Microsoft para su organización y una clave de firma de acceso compartidos (SAS). Esta clave proporciona los permisos necesarios para cargar los archivos PST en su ubicación de almacenamiento de Azure. Asegúrese de tomar precauciones para proteger la dirección URL de SAS. Es único para la organización y se utilizará en el paso 2.
  
 **Importante:** Se recomienda que use versión Azure AzCopy método de carga 7.1.0 para importar archivos PST mediante el uso de la red. Versión 7.1.0 se descarga en el paso 6b en el procedimiento siguiente. 
  
1. Vaya a [https://protection.office.com](https://protection.office.com) e iniciar sesión con las credenciales para una cuenta de administrador de la organización de Office 365. 
    
2. En el panel izquierdo de la seguridad &amp; centro de cumplimiento, haga clic en **el gobierno de datos** \> **importación**.
    
    **Nota:** Se debe tener asignados los permisos adecuados para tener acceso a la página de **importación** de la seguridad &amp; centro de cumplimiento. Vea la sección **antes de empezar** para obtener más información. 
    
3. En la página **Importar** , haga clic en ![icono Agregar](media/ITPro-EAC-AddIcon.gif) **nuevo trabajo de importación**.
    
    Se muestra el Asistente para importación de trabajo.
    
4. Escriba un nombre para el trabajo de importación de PST y, a continuación, haga clic en **siguiente**. Use las letras en minúscula, números, guiones y caracteres de subrayado. No se puede usar las letras en mayúsculas o incluir espacios en el nombre.
    
5. En el **¿desea volver a cargar o enviar datos?** de página, haga clic en **cargar los datos** y, a continuación, haga clic en **siguiente**.
    
    ![Haga clic en cargar los datos para crear una carga de red de trabajo de importación](media/e59f9dc3-ccde-44ff-ac38-c4e39d76ae85.png)
  
6. En la página **Importar datos** , realice las siguientes dos cosas: 
    
    ![Copie la dirección URL de SAS y descargar la herramienta de AzCopy de Azure en la página de datos de importación](media/74411014-ec4b-4e25-9065-404c934cce17.png)
  
    r. en el paso 2, haga clic en **Mostrar la dirección URL de SAS de carga de red**. Después de que se muestra la dirección URL de asociaciones de seguridad, haga clic en **Copiar al Portapapeles** y, a continuación, péguelo y guárdelo en un archivo, por lo que puede tener acceso a él más adelante.
    
    b. en el paso 3, haga clic en **Descargar AzCopy de Azure** para descargar e instalar la herramienta de AzCopy de Azure. Como se mencionó anteriormente, se descargará la versión 7.1.0. En la ventana emergente, haga clic en **Ejecutar** para instalar AzCopy. 
    
  **Nota:** Puede dejar que la página **Importar datos** abierto (en caso de que debe volver a copiar la dirección URL de SAS) o haga clic en **Cancelar** para cerrarlo. 
 
## <a name="step-2-upload-your-pst-files-to-office-365"></a>Paso 2: Cargar los archivos PST a Office 365

Ahora está listo para usar la herramienta de AzCopy.exe para cargar los archivos PST en Office 365. Esta herramienta se carga y almacena en una ubicación de almacenamiento de Azure en la nube de Microsoft. Como se explica anteriormente, la ubicación de almacenamiento de Azure que carga los archivos PST a reside en el mismo Microsoft centro de datos regional donde se encuentra su organización de Office 365. Para completar este paso, los archivos PST tienen que estar ubicada en un recurso compartido de archivos o un servidor de archivos en su organización. Esto se conoce como el directorio de origen en el procedimiento siguiente. Cada vez que se ejecuta la herramienta AzCopy, puede especificar un directorio de origen diferentes. 
  
1. Abra el símbolo del sistema del equipo local.
    
2. Vaya al directorio donde instaló la herramienta AzCopy.exe en el paso 1. Si ha instalado la herramienta en la ubicación predeterminada, vaya a `%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy`.
    
3. Ejecute el siguiente comando para cargar los archivos PST en Office 365.

    ```
    AzCopy.exe /Source:<Location of PST files> /Dest:<SAS URL> /V:<Log file location> /Y
  
    ```
 
    En la siguiente tabla se describe los parámetros y sus valores requeridos. Tenga en cuenta que la información obtenida en el paso anterior se usa en los valores para estos parámetros.
    
    |**Parámetro**|**Descripción**|**Ejemplo**|
    |:-----|:-----|:-----|
    | `/Source:` <br/> |Especifica el directorio de origen en la organización que contiene los archivos PST que se cargará a Office 365.  <br/> No olvide incluir el valor de este parámetro entre comillas dobles (" ").  <br/> | `/Source:"\\FILESERVER01\PSTs"` <br/> |
    | `/Dest:` <br/> |Especifica la dirección URL de SAS que obtuvo en el paso 1.  <br/> No olvide incluir el valor de este parámetro entre comillas dobles (" ").  <br/> **Sugerencia:** (Opcional) Puede especificar una subcarpeta en la ubicación de almacenamiento de Azure para cargar los archivos PST. Para ello, mediante la adición de una ubicación de la subcarpeta (después de "ingestiondata") en la dirección URL de SAS. El primer ejemplo no especifica una subcarpeta; Esto significa que los archivos PST se cargará en la raíz (denominada *ingestiondata* ) de la ubicación de almacenamiento de Azure. El segundo ejemplo carga los archivos PST en una subcarpeta (denominada *PSTFiles* ) en la raíz de la ubicación de almacenamiento de Azure.<br/> | `/Dest:"https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata?sv=2012-02-12&amp;se=9999-12-31T23%3A59%3A59Z&amp;sr=c&amp;si=IngestionSasForAzCopy201601121920498117&amp;sig=Vt5S4hVzlzMcBkuH8bH711atBffdrOS72TlV1mNdORg%3D"` <br/> O bien  <br/>  `/Dest:"https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata/PSTFiles?sv=2012-02-12&amp;se=9999-12-31T23%3A59%3A59Z&amp;sr=c&amp;si=IngestionSasForAzCopy201601121920498117&amp;sig=Vt5S4hVzlzMcBkuH8bH711atBffdrOS72TlV1mNdORg%3D"` <br/> |
    | `/V:` <br/> |Resulta en mensajes de estado detallados en un archivo de registro. De forma predeterminada, el archivo de registro detallado se denomina AzCopyVerbose.log en %LocalAppData%\Microsoft\Azure\AzCopy. Si especifica una ubicación de archivo existente para esta opción, el registro detallado se anexará a ese archivo.  <br/> No olvide incluir el valor de este parámetro entre comillas dobles (" ").  <br/> | `/V:"c:\Users\Admin\Desktop\Uploadlog.log"` <br/> |
    | `/S` <br/> |Este modificador opcional especifica el modo de recursiva para que la herramienta AzCopy copiará archivos pst que se encuentran en las subcarpetas en el directorio de origen que se especifica mediante el `/Source:` parámetro.  <br/> **Nota:** Si se incluye este modificador, los archivos PST en subcarpetas tendrán una ruta de acceso de archivo diferente en la ubicación de almacenamiento de Azure después de cargarlas. Debe especificar la ruta de acceso exacta del archivo en el archivo CSV que cree en el paso 4.<br/> | `/S` <br/> |
    | `/Y` <br/> |Este modificador requiere permite el uso de tokens SAS de sólo escritura cuando se carga los archivos PST en la ubicación de almacenamiento de Azure. La dirección URL de SAS obtenido en el paso 1 (y especificado en `/Dest:` parámetro) es un URL de SAS de sólo escritura, que es la razón por la que se debe incluir este modificador. Tenga en cuenta que una dirección URL de SAS de sólo escritura no impedirá que usen el Explorador de almacenamiento de Azure para ver una lista de los archivos PST que se cargan en la ubicación de almacenamiento de Azure.<br/> | `/Y` <br/> |
   
A continuación se muestra un ejemplo de la sintaxis de la herramienta AzCopy.exe, en el que se usan valores reales para cada parámetro:
    
```
  AzCopy.exe /Source:"\\FILESERVER1\PSTs" /Dest:"https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata?sv=2012-02-12&amp;se=9999-12-31T23%3A59%3A59Z&amp;sr=c&amp;si=IngestionSasForAzCopy201601121920498117&amp;sig=Vt5S4hVzlzMcBkuH8bH711atBffdrOS72TlV1mNdORg%3D" /V:"c:\Users\Admin\Desktop\AzCopy1.log" /Y
  
```

Después de ejecutar el comando, aparecen mensajes de estado en los que se muestra el progreso de la carga de los archivos PST. En un mensaje de estado final aparece el número total de archivos cargados correctamente. 
    
**Sugerencia:** Después de que se ejecute el comando AzCopy.exe correctamente y compruebe que todos los parámetros son correctos, guardar una copia de la sintaxis de línea de comandos para el mismo archivo (protegida) donde copió la información obtenida en el paso 1. A continuación, puede copiar y pegar este comando en un símbolo del sistema cada vez que se desea ejecutar la herramienta AzCopy.exe para cargar los archivos PST en Office 365. El único valor que es posible que deba cambiar son las que para la `/Source:` parámetro. Esto depende en el directorio de origen donde se encuentran los archivos PST. 

## <a name="optional-step-3-view-a-list-of-the-pst-files-uploaded-to-office-365"></a>(Opcional) Paso 3: Ver una lista de los archivos PST cargado a Office 365

Como un paso opcional, puede instalar y usar el Explorador de almacenamiento de información de Microsoft Azure (que es una herramienta gratuita y de código abierto) para ver la lista de los archivos PST que han cargado en el blob de Azure. Hay dos razones para ello:
  
- Compruebe que los archivos PST desde el servidor de archivos de la organización o la carpeta compartida se han cargado correctamente en el blob de Azure.
    
- Compruebe el nombre de archivo (y la ruta de acceso de la subcarpeta si ha incluido uno) para cada archivo PST cargado en el blob de Azure. Esto es realmente útil cuando se está creando el PST de archivo en el siguiente paso de asignación debido a que es necesario especificar la ruta de acceso de carpeta y el nombre de archivo para cada archivo PST. Comprobar estos nombres puede ayudar a reducir posibles errores en el archivo de asignación de PST.
    
El Explorador de almacenamiento de información de Microsoft Azure está en vista previa.
  
 **Importante:** No puede usar el Explorador de almacenamiento de Azure para cargar o modificar los archivos PST. El único método admitido para la importación de los archivos PST a Office 365 es utilizar AzCopy. Además, no se puede eliminar los archivos PST que han cargado en el blob de Azure. Si se intenta eliminar un archivo PST, recibirá un error acerca de no tener los permisos necesarios. Tenga en cuenta que todos los archivos PST se eliminan automáticamente desde el área de almacenamiento de Azure. Si no hay ningún trabajo de importación en curso y, a continuación, todos los archivos PST en el ** ingestiondata ** contenedor se eliminan 30 días después de que se creó el trabajo de importación más reciente. 
  
Para instalar el Explorador de almacenamiento de Azure y conectarse a su área de almacenamiento de Azure:
  
1. Descargue e instale la [herramienta de explorador de almacenamiento de Microsoft Azure](https://go.microsoft.com/fwlink/p/?LinkId=544842).
    
2. Inicie el Explorador de almacenamiento de información de Microsoft Azure, haga clic en **Cuentas de almacenamiento** en el panel izquierdo y, a continuación, haga clic en **Conectar con el almacenamiento de Azure**.
    
    ![Haga clic en cuentas de almacenamiento y, a continuación, haga clic en conectar para almacenamiento de Azure](media/75b80cc3-c336-4f96-ad32-54ac9b96a7af.png)
  
3. Haga clic en **utilizar una cadena de conexión o URI de firma (SAS) de acceso compartido** y haga clic en **siguiente**.
    
4. Haga clic en **usar un URI de SAS**, pegue la dirección URL de SAS que obtuvo en el paso 1 en el cuadro bajo **URI**y, a continuación, haga clic en **siguiente**.
    
5. En la página **Resumen de la conexión** , puede revisar la información de conexión y, a continuación, haga clic en **Conectar**.
    
    Se abre el contenedor de **ingestiondata** ; contiene los archivos PST que cargan en el paso 2. El contenedor de **ingestiondata** se encuentra en **Cuentas de almacenamiento** \> **(SAS-Attached Services)** \> **Contenedores de Blob**. 
    
    ![El explorador de almacenamiento de Azure muestra una lista de los archivos PST que ha cargado](media/12376fed-13a5-4a09-8fe6-e819e011b334.png)
  
6. Cuando haya terminado con el Explorador de almacenamiento de información de Microsoft Azure, haga clic con el botón **ingestiondata**y, a continuación, haga clic en **Desasociar** a desconectar de su área de almacenamiento de Azure. De lo contrario, recibirá un error la próxima vez que se intenta adjuntar. 
    
    ![Haga clic con el botón derecho en la ingesta y haga clic en Desasociar para desconectar de su área de almacenamiento de Azure](media/1e8e5e95-4215-4ce4-a13d-ab5f826a0510.png)
  
## <a name="step-4-create-the-pst-import-mapping-file"></a>Paso 4: Crear el archivo de asignación de importación de PST

Después de que se han cargado los archivos PST en la ubicación de almacenamiento de Azure para su organización de Office 365, el siguiente paso es crear una coma separados archivo valor (CSV) que especifica qué buzones de usuario se importará a los archivos PST. Podrá enviar este archivo CSV en el siguiente paso al crear un trabajo de importación de PST.
  
1. [Descargar una copia del archivo de asignación de importación de PST](https://go.microsoft.com/fwlink/p/?LinkId=544717).
    
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
    La primera fila o la fila de encabezado, del archivo CSV se enumera los parámetros que usará el servicio de PST Import para importar los archivos PST a buzones de usuario. Cada nombre de parámetro viene separada por una coma. Cada fila debajo de la fila de encabezado representa los valores de parámetro para la importación de un archivo PST a un buzón específico. Necesitará una fila para cada archivo PST que desea importar a un buzón de usuario. Asegúrese de reemplazar los datos de marcador de posición en el archivo de asignación con los datos reales.

   **Nota:** No cambiar nada en la fila de encabezado, incluidos los parámetros de SharePoint; se omitirán durante el proceso de importación de PST. 

 3. Use la información de la tabla siguiente para rellenar el archivo CSV con la información necesaria.


    |**Parámetro**|**Descripción**|**Ejemplo**|
    |:-----|:-----|:-----|
    | `Workload` <br/> |Especifica el servicio Office 365 que se va a importar datos. Para importar archivos PST a buzones de usuario, use `Exchange`.<br/> | `Exchange` <br/> |
    | `FilePath` <br/> |Especifica la ubicación de la carpeta en la ubicación de almacenamiento de Azure que cargan los archivos PST a en el paso 2.  <br/> Si no ha incluido un nombre de la subcarpeta opcional en la dirección URL de SAS en el `/Dest:` parámetro en el paso 2, deje este parámetro en blanco en el archivo CSV. Si ha incluido un nombre de la subcarpeta, especifique en este parámetro (vea el segundo ejemplo). El valor para este parámetro distingue mayúsculas de minúsculas.<br/> En cualquier caso, *no* incluya "ingestiondata" en el valor de la `FilePath` parámetro.  <br/><br/> **Importante:** El caso para el nombre de ruta de acceso del archivo debe ser el mismo que el caso que se usa si ha incluido un nombre de la subcarpeta opcional de la dirección URL de SAS en el `/Dest:` parámetro en el paso 2. Por ejemplo, si usó `PSTFiles` para la subcarpeta el nombre en el paso 2 y, a continuación, usar `pstfiles` en el `FilePath` parámetro en el archivo CSV, la importación para el archivo PST se producirá un error. Asegúrese de usar el mismo caso en ambas instancias.<br/> |(se deja en blanco)  <br/> O bien  <br/>  `PSTFiles` <br/> |
    | `Name` <br/> |Especifica el nombre del archivo PST que se va a importar al buzón del usuario. El valor para este parámetro distingue mayúsculas de minúsculas.<br/> <br/>**Importante:** El caso para el nombre del archivo PST en el archivo CSV debe ser el mismo que el archivo PST que se cargó en la ubicación de almacenamiento de Azure en el paso 2. Por ejemplo, si usa `annb.pst` en el `Name` parámetro en el archivo CSV, pero el nombre del archivo PST real es `AnnB.pst`, se producirá un error en la importación de ese archivo PST. Asegúrese de que el nombre de los archivos PST en el archivo CSV usa el mismo caso que el archivo PST real.<br/> | `annb.pst` <br/> |
    | `Mailbox` <br/> |Especifica la dirección de correo electrónico del buzón al que se va a importar el archivo PST. Tenga en cuenta que no se puede especificar una carpeta pública debido a que el servicio de importación de PST no admite la importación de los archivos PST a las carpetas públicas.<br/> Para importar un archivo PST a un buzón de correo inactivo, es necesario especificar el GUID del buzón de correo para este parámetro. Para obtener este GUID, ejecute el siguiente comando de PowerShell en Exchange Online: ' Get-Mailbox <identity of inactive mailbox> - InactiveMailboxOnly | Guid de FL` <br/> <br/>**Note:** In some cases, you might have multiple mailboxes with the same email address, where one mailbox is an active mailbox and the other mailbox is in a soft-deleted (or inactive) state. In these situations, you have to specify the mailbox GUID to uniquely identify the mailbox to import the PST file to. To obtain this GUID for active mailboxes, run the following PowerShell command:  `Get-Mailbox<identity of active mailbox> | Guid de FL`. To obtain the GUID for soft-deleted (or inactive) mailboxes, run this command  `Get-Mailbox <identity of soft-deleted or inactive mailbox> - SoftDeletedMailbox | Guid de FL'.  <br/> | `annb@contoso.onmicrosoft.com` <br/> O bien  <br/>  `2d7a87fe-d6a2-40cc-8aff-1ebea80d4ae7` <br/> |
    | `IsArchive` <br/> | Especifica si se va a importar o no el archivo PST en el buzón de archivo del usuario. Hay dos opciones:<br/><br/>**FALSE** - importa el archivo PST en el buzón del usuario principal.  <br/> **TRUE** - importa el archivo PST al buzón de archivo del usuario. Esto se da por supuesto que el [buzón de archivo del usuario está habilitado](enable-archive-mailboxes.md).<br/><br/>Si establece este parámetro en `TRUE` y buzón de archivo del usuario no está habilitado, se producirá un error en la importación de dicho usuario. Tenga en cuenta que si se produce un error en una importación de un usuario (debido a que su archivo no está habilitado y se establece esta propiedad en `TRUE`), los demás usuarios en el trabajo de importación no se verán afectados.<br/>  Si deja en blanco este parámetro, se importa el archivo PST en el buzón del usuario principal.  <br/> <br/>**Nota:** Para importar un archivo PST a un buzón de archivo basados en la nube para un usuario cuyo buzón de correo principal es local, sólo tiene que especificar `TRUE` para este parámetro y especificar la dirección de correo electrónico para el buzón del usuario local para el `Mailbox` parámetro.  <br/> | `FALSE` <br/> O bien  <br/>  `TRUE` <br/> |
    | `TargetRootFolder` <br/> | Especifica la carpeta de buzón de correo que se importa el archivo PST a.  <br/>  Si deja en blanco este parámetro, se va a importar el archivo PST en una carpeta nueva con nombre **importado** que se encuentra en el nivel raíz del buzón (el mismo nivel que la carpeta Bandeja de entrada y las otras carpetas de buzón de correo de forma predeterminada).  <br/>  Si especifica `/`, los elementos en el archivo PST se va a importar en directamente a la carpeta de bandeja de entrada del usuario.  <br/><br/>  Si especifica `/<foldername>`, los elementos en el archivo PST se importará a una carpeta denominada * \<foldername\> * . Por ejemplo, si usa `/ImportedPst`, los elementos se importará a una carpeta denominada **ImportedPst**. Esta carpeta se encuentran en el buzón del usuario en el mismo nivel que la carpeta Bandeja de entrada.<br/><br/> **Sugerencia:** Tenga en cuenta que ejecuta unos lotes de prueba para experimentar con este parámetro para que pueda determinar la mejor ubicación de carpeta para importar archivos de archivos pst a.  <br/> |(se deja en blanco)  <br/> O bien  <br/>  `/` <br/> O bien  <br/>  `/ImportedPst` <br/> |
    | `ContentCodePage` <br/> |Este parámetro opcional especifica un valor numérico para la página de códigos que se utilizará para importar los archivos PST en el formato de archivo ANSI. Este parámetro se usa para importar los archivos PST de organizaciones chino, japonés y coreano (CJK) debido a que estos lenguajes normalmente usan un juego de caracteres de doble byte (DBCS) para la codificación de caracteres. Si este parámetro no se usa para importar archivos PST para idiomas que usan DBCS para nombres de carpeta de buzón de correo, los nombres de carpeta a menudo aparecerán dañados después de su importación.<br/><br/> Para obtener una lista de valores admitidos que se usará para este parámetro, vea [Identificadores de la página de código](https://go.microsoft.com/fwlink/p/?LinkId=328514).  <br/> <br/>**Nota:** Como ya ha indicado, éste es un parámetro opcional y no tiene que incluir en el archivo CSV. O bien, puede incluirlo y deje el valor en blanco para una o varias filas.<br/> |(se deja en blanco)  <br/> O bien  <br/>  `932`(que es el identificador de la página de códigos para ANSI/OEM en japonés)  <br/> |
    | `SPFileContainer` <br/> |Para la importación de archivos PST, deje este parámetro en blanco.   <br/> |No aplicable  <br/> |
    | `SPManifestContainer` <br/> |Para la importación de archivos PST, deje este parámetro en blanco.   <br/> |No aplicable  <br/> |
    | `SPSiteUrl` <br/> |Para la importación de archivos PST, deje este parámetro en blanco.   <br/> |No aplicable  <br/> |

## <a name="step-5-create-a-pst-import-job-in-office-365"></a>Paso 5: crear un trabajo de importación de PST en Office 365

El siguiente paso es crear el trabajo de importación de PST en el servicio de importación en Office 365. Como se explica anteriormente, se enviará el archivo de asignación de importación de PST que creó en el paso 4. Después de crear el nuevo trabajo, Office 365 analiza los datos en los archivos PST y, a continuación, le proporciona una oportunidad para filtrar los datos que realmente obtienen importados a los buzones especificados en el archivo de asignación de importación de PST (consulte el [paso 6](#step-6-filter-data-and-start-the-pst-import-job)).
  
1. Vaya a [https://protection.office.com](https://protection.office.com) e iniciar sesión con las credenciales para una cuenta de administrador de la organización de Office 365. 
    
2. En el panel izquierdo de la seguridad &amp; centro de cumplimiento, haga clic en **el gobierno de datos** y, a continuación, haga clic en **Importar**.
    
3. En la página **Importar** , haga clic en ![icono Agregar](media/ITPro-EAC-AddIcon.gif) **nuevo trabajo de importación**.
    
    **Nota:** Se debe tener asignados los permisos adecuados para tener acceso a la página **Importar** en la seguridad &amp; centro de cumplimiento para crear un nuevo trabajo de importación. Vea la sección **antes de empezar** para obtener más información. 
    
4. Escriba un nombre para el trabajo de importación de PST y, a continuación, haga clic en **siguiente**. Use las letras en minúscula, números, guiones y caracteres de subrayado. No se puede usar las letras en mayúsculas o incluir espacios en el nombre.
    
5. En el **¿desea volver a cargar o enviar datos?** de página, haga clic en **cargar los datos** y, a continuación, haga clic en **siguiente**.
    
    ![Haga clic en cargar los datos para crear una carga de red de trabajo de importación](media/e59f9dc3-ccde-44ff-ac38-c4e39d76ae85.png)
  
6. En el paso 4 en la página **Importar datos** , haga clic en el **he terminado al cargar archivos de Mis** y **tengo acceso al archivo de asignación de las** casillas de verificación y, a continuación, haga clic en **siguiente**.
    
    ![Haga clic en las dos casillas de verificación en el paso 4](media/9f2427e8-3af2-4e27-95e6-a9f08430d3d8.png)
  
7. En la página **Seleccionar el archivo de asignación** , haga clic en **Seleccionar archivo de asignación** para enviar el archivo de asignación de importación de PST que creó en el paso 4. 
    
    ![Haga clic en el archivo de asignación Select para enviar el archivo CSV que creó para el trabajo de importación](media/d30b1d73-80bb-491e-a642-a21673d06889.png)
  
8. Después del nombre de la CSV archivo aparece bajo **la asignación de nombre de archivo**, haga clic en **Validar** para comprobar si el archivo CSV para errores. 
    
    ![Haga clic en validar para comprobar si el archivo CSV de errores](media/4680999d-5538-4059-b878-2736a5445037.png)
  
    El archivo CSV tiene que ser validado correctamente para crear un trabajo de importación de PST. Tenga en cuenta que el nombre de archivo se cambia a verde después de que se validan correctamente. Si se produce un error en la validación, haga clic en el vínculo **Ver registro** . Se abre un informe de errores de validación, con un mensaje de error para cada fila en el archivo que no se pudo. 
    
9. Después de valida correctamente el archivo de asignación de PST, leer el documento de términos y condiciones y, a continuación, haga clic en la casilla de verificación.
    
10. Haga clic en **Guardar** para enviar el trabajo y, a continuación, haga clic en **Cerrar** después de que el trabajo se ha creado correctamente. 
    
    Se muestra una página de estado emergente, con un estado de **análisis en curso** y el trabajo de importación nuevo se muestra en la lista en la página **Importar** . 
    
11. Haga clic en **Actualizar**![icono de actualización](media/O365-MDM-Policy-RefreshIcon.gif) para actualizar la información de estado que se muestra en la columna **estado** . Cuando se completa el análisis y están listos para importar los datos, se cambia el estado para **Análisis completado**.
    
    Puede hacer clic en el trabajo de importación para mostrar la página emergente de estado, que contiene información más detallada sobre el trabajo de importación, como el estado de cada archivo PST que aparecen en el archivo de asignación.
 
## <a name="step-6-filter-data-and-start-the-pst-import-job"></a>Paso 6: Filtrar datos e iniciar el trabajo de importación de PST

Después de crear el trabajo de importación en el paso 5, Office 365 analiza los datos en los archivos PST (de forma segura) mediante la identificación de la antigüedad de los elementos y los tipos de mensaje diferentes incluidos en los archivos PST. Cuando se completa el análisis y están listos para importar los datos, tiene la opción para importar todos los datos contenidos en los archivos PST o puede recortar los datos que se importan mediante la configuración de filtros que controlan qué datos obtiene importados.
  
1. En la página **Importar** en la seguridad &amp; centro de cumplimiento, haga clic en **listo para importar a Office 365** para el trabajo de importación que creó en el paso 5. 
    
    ![Haga clic en listo para importar a Office 365 junto a la que creó el trabajo de importación](media/5760aac3-300b-4e31-b894-253c42a4b82b.png)
  
    Se muestra un marcha página con información acerca de los archivos PST y otra información sobre el trabajo de importación.
    
2. En la página emergente, haga clic en **importar a Office 365**.
    
    Se abrirá la página **filtrar los datos** . Contiene toda la información de datos resultante del análisis realizado en los archivos PST por Office 365, incluida información acerca de la antigüedad de los datos de. En este momento, tiene la opción para filtrar los datos que se va a importar o importación todos los datos tal y como está. 
    
    ![Puede recortar los datos en los archivos PST o importar todos de la misma](media/287fc030-99e9-417b-ace7-f64617ea5d4e.png)
  
3. Realice una de las acciones siguientes:
    
    r. para recortar los datos que se importan, haga clic en **Sí, deseo filtrarla antes de importar**.
    
    Para obtener instrucciones detalladas paso a paso acerca del filtrado de los datos en los archivos PST y, a continuación, iniciar el trabajo de importación, vea [filtrar datos al importar archivos PST a Office 365](filter-data-when-importing-pst-files.md).
    
    O bien
    
    b. para importar todos los datos en los archivos PST, haga clic en **No, deseo importarlo todo** y haga clic en **siguiente**.
    
4. Si opta por importar todos los datos, haga clic en **Importar datos** para iniciar el trabajo de importación. 
    
    El estado del trabajo de importación es para mostrar en la página **Importar** . Haga clic en ![icono de actualización](media/O365-MDM-Policy-RefreshIcon.gif) **Actualizar** para actualizar la información de estado que se muestra en la columna **estado** . Haga clic en el trabajo de importación para mostrar la página emergente de estado, que muestra información de estado acerca de cada archivo PST que se están importando. 

## <a name="how-the-import-process-works"></a>Cómo funciona el proceso de importación
  
Puede usar la opción de carga de red y el servicio Office 365 importar para importación masiva de archivos PST a buzones de usuario. Carga de red significa cargar los archivos PST en un área de almacenamiento temporal en la nube de Microsoft. A continuación, el servicio Office 365 importación copia los archivos PST desde el área de almacenamiento para los buzones de usuario de destino.
  
Aquí es una ilustración y una descripción del proceso de carga de red para importar archivos PST a buzones de correo en Office 365.
  
![Flujo de trabajo de la red cargar el proceso para importar archivos PST a Office 365](media/9e05a19e-1e7a-4f1f-82df-9118f51588c4.png)
  
1. **Descarga el archivo PST importar herramienta y la ubicación de almacenamiento de Azure clave Private** - el primer paso es descargar la herramienta de línea de comandos de AzCopy de Azure y una clave de acceso que se usa para cargar los archivos PST en una ubicación de almacenamiento de Azure en la nube de Microsoft. Obtener estos desde la página de **importación** de la seguridad de Office 365 &amp; centro de cumplimiento. La clave (denominado una clave de firma (SAS) de acceso seguro, proporciona los permisos necesarios para cargar los archivos PST a privado y seguro de la ubicación de almacenamiento de Azure. Esta clave de acceso es única para la organización y ayuda a impedir el acceso no autorizado a los archivos PST después de que se cargan a la nube de Microsoft. Tenga en cuenta que la importación de los archivos PST a Office 365 no requiere a tiene una suscripción de Azure independiente a su organización. 
    
2. **Cargar los archivos PST a la ubicación de almacenamiento de Azure** - el siguiente paso consiste en usar la herramienta de AzCopy.exe (descargada en el paso 1) para cargar y almacenar los archivos PST en una ubicación de almacenamiento de Azure que reside en el mismo centro de datos regional Microsoft donde de Office 365 organización se encuentra. Para cargarlas, los archivos PST que desea importar a Office 365 tienen que estar ubicada en un recurso compartido de archivos o un servidor de archivos en su organización.
    
    Tenga en cuenta que hay un paso opcional que puede realizar para ver la lista de los archivos PST después de que se cargan a la ubicación de almacenamiento de Azure.
    
3. **Crear un archivo de asignación de importación de PST** - después de que se han cargado los archivos PST en la ubicación de almacenamiento de Azure, el siguiente paso es crear un archivo (CSV) de valores separados por comas que especifica qué buzones de usuario los archivos PST se importará a, tenga en cuenta que puede ser un archivo PST  importar a su buzón de archivo o buzón principal de un usuario. El servicio Office 365 importar usará la información en el archivo CSV para importar los archivos PST.
    
4. **Trabajo de importación de crear un archivo PST** - el siguiente paso es crear un trabajo de importación de PST en la página **Importar** en la seguridad &amp; centro de cumplimiento y enviar el archivo de asignación de importación de PST creado en el paso anterior. Después de crear el trabajo de importación, Office 365 analiza los datos en los archivos PST y, a continuación, le proporciona una oportunidad para definir filtros que controlan qué datos realmente obtiene importados a los buzones especificados en el archivo de asignación de importación de PST. 
    
5. **Filtrar los datos de PST que se va a importar a buzones de correo** - después de que se crea y se inicia el trabajo de importación, Office 365 analiza los datos en los archivos PST (segura y) mediante la identificación de la antigüedad de los elementos y los tipos de mensaje diferentes incluidos en los archivos PST . Cuando se completa el análisis y están listos para importar los datos, tiene la opción para importar todos los datos contenidos en los archivos PST o puede recortar los datos que se importan mediante la configuración de filtros que controlan qué datos obtiene importados.
    
6. **Iniciar el trabajo de importación de PST** - una vez iniciado el trabajo de importación, Office 365 utiliza la información en el archivo de asignación de importación de PST para importar los archivos PST desde la ubicación de almacenamiento de Azure a buzones de usuario. Información de estado sobre el trabajo de importación (incluida la información acerca de cada archivo PST que se están importando) se muestra en la página **Importar** en la seguridad &amp; centro de cumplimiento. Cuando finalice el trabajo de importación, el estado del trabajo se establece en **completa**.
  
## <a name="more-information"></a>Más información

- ¿Por qué importar archivos PST a Office 365?
    
  - Es una buena forma de importar datos de mensajería de su organización el archivado a Office 365.
    
  - Los datos están disponibles para el usuario en todos los dispositivos, ya que se almacenan en la nube.
    
  - Ayuda a las necesidades de cumplimiento de normas de dirección de la organización que le permite aplicar las características de cumplimiento de normas de Office 365 a los datos de los archivos PST que ha importado. Esto incluye:
    
  - Habilitación de [buzones de archivo](enable-archive-mailboxes.md) y la [ampliación automática de archivado](enable-unlimited-archiving.md) para ofrecer a los usuarios espacio de almacenamiento de buzones de correo adicionales para almacenar los datos que ha importado. 
    
  - Colocar buzones en [Suspensión por litigio](https://go.microsoft.com/fwlink/?linkid=856286) a conservar los datos que ha importado. 
    
  - Uso de [Herramientas de exhibición de documentos electrónicos](search-for-content.md) de Microsoft para buscar los datos que ha importado. 
    
  - Uso de [las directivas de retención de Office 365](retention-policies.md) para controlar cuánto tiempo se conservarán los datos que ha importado y qué acción debe realizar después de que expire el período de retención. 
    
  - Buscar en el [registro de auditoría de Office 365](search-the-audit-log-in-security-and-compliance.md) para los eventos relacionados con el buzón de correo que afectan a los datos que ha importado. 
    
  - Importación de datos de [buzones de correo inactivos](create-and-manage-inactive-mailboxes.md) para archivar datos con fines de cumplimiento. 
    
  - Uso de [directivas de prevención de pérdida de datos](data-loss-prevention-policies.md) para evitar que los datos confidenciales se pierdan fuera de su organización. 
  
- Este es un ejemplo de la dirección URL de firma de acceso compartidos (SAS) que se obtiene en el paso 1. En este ejemplo se también contiene la sintaxis para el comando que se ejecuta en la herramienta AzCopy.exe para cargar los archivos PST a Office 365. Asegúrese de tomar precauciones para proteger la dirección URL de SAS igual que protege a las contraseñas u otra información relacionada con la seguridad.

    ```
    SAS URL: https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata?sv=2012-02-12&amp;se=9999-12-31T23%3A59%3A59Z&amp;sr=c&amp;si=IngestionSasForAzCopy201601121920498117&amp;sig=Vt5S4hVzlzMcBkuH8bH711atBffdrOS72TlV1mNdORg%3D

    AzCopy.exe /Source:<Location of PST files> /Dest:<SAS URL> /V:<Log file location> /Y

    EXAMPLES

    This example uploads PST files to the root of the Azure storage location:

    AzCopy.exe /Source:"\\FILESERVER1\PSTs" /Dest:"https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata?sv=2012-02-12&amp;se=9999-12-31T23%3A59%3A59Z&amp;sr=c&amp;si=IngestionSasForAzCopy201601121920498117&amp;sig=Vt5S4hVzlzMcBkuH8bH711atBffdrOS72TlV1mNdORg%3D" /V:"c:\Users\Admin\Desktop\AzCopy1.log" /Y
    
    This example uploads PST files to a subfolder named PSTFiles  in the Azure storage location:

    AzCopy.exe /Source:"\\FILESERVER1\PSTs" /Dest:"https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata/PSTFiles?sv=2012-02-12&amp;se=9999-12-31T23%3A59%3A59Z&amp;sr=c&amp;si=IngestionSasForAzCopy201601121920498117&amp;sig=Vt5S4hVzlzMcBkuH8bH711atBffdrOS72TlV1mNdORg%3D" /V:"c:\Users\Admin\Desktop\AzCopy1.log" /Y
``

- As previously explained, the Office 365 Import service turns on the retention hold setting (for an indefinite duration) after PST files are imported to a mailbox. This means the  *RetentionHoldEnabled*  property is set to  `True` so that the retention policy assigned to the mailbox won't be processed. This gives the mailbox owner time to manage the newly-imported messages by preventing a deletion or archive policy from deleting or archiving older messages. Here are some steps you can take to manage this retention hold: 
    
    - After a certain period of time, you can turn off the retention hold by running the  `Set-Mailbox -RetentionHoldEnabled $false` command. For instructions, see [Place a mailbox on retention hold](https://go.microsoft.com/fwlink/p/?LinkId=544749).
    
   - You can configure the retention hold so that it's turned off on some date in the future. You do this by running the  `Set-Mailbox -EndDateForRetentionHold <date>` command. For example, assuming that today's date is July 1, 2016 and you want the retention hold turned off in 30 days, you would run the following command:  `Set-Mailbox -EndDateForRetentionHold 8/1/2016`. In this scenario, you would leave the  *RetentionHoldEnabled*  property set to  *True*  . For more information, see [Set-Mailbox](https://go.microsoft.com/fwlink/p/?LinkId=150317).
    
   - You can change the settings for the retention policy that's assigned to the mailbox so that older items that were imported won't be immediately deleted or moved to the user's archive mailbox. For example, you could lengthen the retention age for a deletion or archive policy that's assigned to the mailbox. In this scenario, you would turn off the retention hold on the mailbox after you changed the settings of the retention policy. For more information, see [Set up an archive and deletion policy for mailboxes in your Office 365 organization](set-up-an-archive-and-deletion-policy-for-mailboxes.md).
    
