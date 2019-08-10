---
title: Usar la carga en la red para importar los archivos PST de su organización a Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 103f940c-0468-4e1a-b527-cc8ad13a5ea6
description: 'Para administradores: obtenga información sobre cómo usar la carga en la red para importar en bloque varios archivos PST a buzones de usuario en Office 365.'
ms.openlocfilehash: bd15216df69e003a5aaddb2ec21ede4da5c5c312
ms.sourcegitcommit: 33c8e9c16143650ca443d73e91631f9180a9268e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/25/2019
ms.locfileid: "35854824"
---
# <a name="use-network-upload-to-import-your-organization-pst-files-to-office-365"></a>Usar la carga en la red para importar los archivos PST de su organización a Office 365

> [!NOTE]
> Este artículo está dirigido a administradores. ¿Está intentando importar archivos PST a su propio buzón? Vea [Importar el correo electrónico, los contactos y el calendario desde un archivo .pst de Outlook](https://go.microsoft.com/fwlink/p/?LinkID=785075)
  
Estas son las instrucciones paso a paso necesarias para usar la carga en la red para importar en bloque varios archivos PST a buzones de Office 365. Para leer las preguntas más frecuentes sobre el uso de la carga en la red para importar en bloque archivos PST a los buzones de Office 365, vea [Preguntas más frecuentes sobre el uso de carga en la red para importar archivos PST](faqimporting-pst-files-to-office-365.md#using-network-upload-to-import-pst-files).
  
[Paso 1: copiar la URL de SAS e instalar Azure AzCopy](#step-1-copy-the-sas-url-and-install-azure-azcopy)

[Paso 2: cargar los archivos PST en Office 365](#step-2-upload-your-pst-files-to-office-365)

[Paso 3 (opcional): ver una lista de los archivos PST cargados en Office 365](#optional-step-3-view-a-list-of-the-pst-files-uploaded-to-office-365)

[Paso 4: crear el archivo de asignación de importación de PST](#step-4-create-the-pst-import-mapping-file)

[Paso 5: crear un trabajo de importación de PST en Office 365](#step-5-create-a-pst-import-job-in-office-365)

[Paso 6: filtrar los datos e iniciar el trabajo de importación de PST](#step-6-filter-data-and-start-the-pst-import-job)

Tiene que llevar a cabo el paso 1 solo una vez para importar los archivos PST a los buzones de Office 365. Después de realizar estos pasos, siga los pasos comprendidos entre el 2 y el 6 cada vez que quiera cargar e importar un lote de archivos PST.

## <a name="before-you-begin"></a>Antes de empezar
  
- Debe tener asignado el rol importación o exportación de buzón de Exchange Online para importar archivos PST a los buzones de Office 365. Este rol no está asignado a ningún grupo de roles de Exchange Online de forma predeterminada. Puede agregar el rol Mailbox Import Export al grupo de roles Administración de la organización. También puede crear un grupo de roles, asignarle el rol Mailbox Import Export y agregarse a sí mismo como miembro. Para obtener más información, vea las secciones "Agregar un rol a un grupo de roles" o "Crear un grupo de roles" en [Administrar grupos de roles](https://go.microsoft.com/fwlink/p/?LinkId=730688).
    
    Además, para crear trabajos de importación en el Centro de seguridad y cumplimiento, debe cumplirse uno de estos requisitos:
    
  - Debe tener asignado el rol de los destinatarios de correo en Exchange Online. De forma predeterminada, este rol se asigna a los grupos de roles de administración de la organización y administración de destinatarios.
    
    O bien
    
  - Debe ser administrador global en su organización de Office 365. 
    
  > [!TIP]
    > Puede crear un nuevo grupo de roles en Exchange Online que está pensado específicamente para la importación de archivos PST a Office 365. Para obtener el nivel mínimo de privilegios necesarios para importar archivos PST, asigne los roles de importación o exportación de buzón y de destinatarios de correo al nuevo grupo de roles y, después, agregue a los miembros. 
  
- El único método admitido para importar archivos PST a Office 365 es usar la herramienta Azure AzCopy, tal y como se describe en este tema. No puede usar el Explorador de Azure Storage para cargar archivos PST directamente en el área de almacenamiento de Azure.
    
- Debe almacenar los archivos PST que quiere importar a Office 365 en un servidor de archivos o en una carpeta compartida de la organización. En el paso 2, ejecutará la herramienta Azure AzCopy, que cargará los archivos PST almacenados en este servidor de archivos o carpeta compartida en Office 365.
    
- Este procedimiento implica copiar y guardar una copia de una dirección URL que contiene una clave de acceso. Esta información se utilizará en el paso 2 para cargar los archivos PST y, en el paso 3, si quiere ver una lista de los archivos PST cargados en Office 365. Asegúrese de tomar precauciones para proteger esta dirección URL de la misma manera que protegería las contraseñas u otra información relacionada con la seguridad. Por ejemplo, puede guardarla en un documento de Microsoft Word protegido por contraseña o en una unidad USB cifrada. Vea la sección [Más información](#more-information) para ver un ejemplo de la clave y URL combinadas. 
    
- Puede importar archivos PST a un buzón inactivo de Office 365. Para ello, debe especificar el GUID del buzón inactivo en el parámetro `Mailbox` del archivo de asignación de importación de PST. Vea el paso 4 en la pestaña **Instrucciones** de este tema para obtener información. 
    
- En una implementación híbrida de Exchange, puede importar archivos PST a un buzón de archivo basado en la nube para un usuario cuyo buzón principal es local. Para ello, haga lo siguiente en el archivo de asignación de importación de PST:
    
  - Especifique la dirección de correo electrónico del buzón local del usuario en el parámetro `Mailbox`. 
    
  - Especifique el valor **TRUE** en el parámetro `IsArchive`. 
    
    Vea el [paso 4](#step-4-create-the-pst-import-mapping-file) para obtener más información. 
    
- Después de que los archivos PST se importan a un buzón de correo de Office 365, la configuración de espera de retención del buzón está activada durante un período de tiempo indefinido. Esto significa que la directiva de retención asignada al buzón no se procesará hasta que desactive la espera de retención o establezca una fecha para desactivar la retención. ¿Por qué lo hacemos? Si los mensajes importados a un buzón son antiguos, es posible que se eliminen de forma permanente, ya que su período de retención ha caducado en función de la configuración de retención establecida para el buzón. Al colocar el buzón en espera de retención, el propietario del buzón tendrá tiempo para administrar estos mensajes recién importados o le dará tiempo para cambiar la configuración de retención del buzón. Vea la pestaña **Más información** en este tema para obtener sugerencias sobre cómo administrar la espera de retención. 
    
- De forma predeterminada, el tamaño máximo de mensaje que puede recibir un buzón de Office 365 es de 35 MB. Esto se debe a que el valor predeterminado de la propiedad *MaxReceiveSize* de un buzón está establecido en 35 MB. Pero el límite de tamaño máximo de recepción de mensajes en Office 365 es de 150 MB. Por lo tanto, si importa un archivo PST que contiene un elemento superior a 35 MB, el servicio de importación de Office 365 cambiará automáticamente el valor de la propiedad *MaxReceiveSize* en el buzón de destino a 150 MB. Esto permite que se importen a buzones de usuario mensajes de hasta 150 MB. 
    
    > [!TIP]
    > Para identificar el tamaño de recepción de un buzón de correo, puede ejecutar este comando en PowerShell de Exchange Online: `Get-Mailbox <user mailbox> | FL MaxReceiveSize`. 

## <a name="step-1-copy-the-sas-url-and-install-azure-azcopy"></a>Paso 1: copiar la URL de SAS e instalar Azure AzCopy

El primer paso es descargar e instalar la herramienta Azure AzCopy, que es la herramienta que ejecutará en el paso 2 para cargar los archivos PST en Office 365. También deberá copiar la dirección URL de SAS de su organización. Esta dirección URL es una combinación de la dirección URL de red de la ubicación de almacenamiento de Azure en la nube de Microsoft de su organización y una clave de Firma de acceso compartido (SAS). Esta clave le proporciona los permisos necesarios para cargar los archivos PST a la ubicación de almacenamiento de Azure. Asegúrese de tomar precauciones para proteger la URL de SAS. Es exclusiva para su organización y se usará en el paso 2.

> [!IMPORTANT]
> Para importar archivos PST con el método de carga en la red, le recomendamos que use la versión de Azure AzCopy que puede descargarse en el paso 6B del procedimiento siguiente.
  
1. Ve a [https://protection.office.com](https://protection.office.com) e inicie sesión con las credenciales de una cuenta de administrador en su organización de Office 365. 
    
2. En el panel izquierdo del Centro de seguridad y cumplimiento, haga clic en **Gobierno de datos** \> **Importar**.
    
    > [!NOTE]
    > Es necesario que tenga asignados los permisos adecuados para tener acceso a la página **Importar** en el Centro de seguridad y cumplimiento. Vea la sección **Antes de empezar** para obtener más información. 
    
3. En la página **Importar**, haga clic en ![Agregar icono](media/ITPro-EAC-AddIcon.gif) **Nuevo trabajo de importación**.
    
    Se mostrará el asistente para la importación de trabajos.
    
4. Escriba un nombre para el trabajo de importación de PST y haga clic en **Siguiente**. Use letras minúsculas, números, guiones y caracteres de subrayado. Las letras en mayúscula no se pueden usar ni se pueden incluir espacios en el nombre.
    
5. En la página **¿Quiere cargar o enviar datos?**, haga clic en **Cargar los datos** y, después, en **Siguiente**.
    
    ![Hacer clic en Cargar los datos para crear un trabajo de importación de carga en la red](media/e59f9dc3-ccde-44ff-ac38-c4e39d76ae85.png)
  
6. En la página **Importar datos**, siga los dos pasos siguientes: 
    
    ![Copiar la dirección URL de SAS y descargar la herramienta Azure AzCopy en la página Importar datos](media/74411014-ec4b-4e25-9065-404c934cce17.png)
  
    A. En el paso 2, haga clic en **Mostrar dirección URL de carga en la red de SAS**. Después de que se muestre la URL de SAS, haga clic en **Copiar al Portapapeles**, péguela y guárdela en un archivo para que pueda acceder a ella más tarde.
    
    B. En el paso 3, haga clic en **Descargar Azure AzCopy** para descargar e instalar la herramienta. En la ventana emergente, haga clic en **Ejecutar** para instalar AzCopy. 
    
> [!NOTE]
> Puede dejar abierta la página **Importar datos** (en caso de que necesite volver a copiar la URL de SAS) o hacer clic en **Cancelar** para cerrarla. 
 
## <a name="step-2-upload-your-pst-files-to-office-365"></a>Paso 2: cargar los archivos PST en Office 365

Ahora ya puede usar la herramienta AzCopy.exe para cargar los archivos PST en Office 365. Esta herramienta los carga y los almacena en una ubicación de almacenamiento de Azure en la nube de Microsoft. Como mencionado anteriormente, la ubicación de almacenamiento de Azure que carga los archivos PST está en el mismo centro de datos regional de Microsoft que su organización de Office 365. Para llevar a cabo este paso, los archivos PST tienen que estar ubicados en un recurso compartido de archivos o en un servidor de archivos de su organización. Esto se conoce como el directorio de origen en el siguiente procedimiento. Cada vez que ejecute la herramienta AzCopy, puede especificar un directorio de origen diferente. 
  
1. Abra el símbolo del sistema del equipo local.
    
2. Vaya al directorio en el que instaló la herramienta AzCopy.exe en el paso 1. Si ha instalado la herramienta en la ubicación predeterminada, vaya a `%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy`.
    
3. Ejecute el comando siguiente para cargar los archivos PST en Office 365.

    ```
    AzCopy.exe /Source:<Location of PST files> /Dest:<SAS URL> /V:<Log file location> /Y
  
    ```
 
    > [!IMPORTANT] 
    > Debe especificar un directorio como la ubicación de origen en el comando anterior. No se puede especificar un archivo PST individual. Se cargarán todos los archivos PST en el directorio de origen.
 
    En la tabla siguiente se describen los parámetros y los valores requeridos de AzCopy.exe. La información de los pasos anteriores se usa en los valores de estos parámetros.
    
    |**Parámetro**|**Descripción**|**Ejemplo**|
    |:-----|:-----|:-----|
    | `/Source:` <br/> |Especifica el directorio de origen de la organización que contiene los archivos PST que se cargarán en Office 365.  <br/> No olvide incluir el valor de este parámetro entre comillas dobles (" ").  <br/> | `/Source:"\\FILESERVER01\PSTs"` <br/> |
    | `/Dest:` <br/> |Especifica la URL de SAS que ha obtenido en el paso 1.  <br/> No olvide incluir el valor de este parámetro entre comillas dobles (" ").  <br/> **Sugerencia:** (opcional) puede especificar una subcarpeta en la ubicación de almacenamiento de Azure en la que cargar los archivos PST. Para ello, agregue una ubicación de subcarpeta (después de "ingestiondata") en la dirección URL de SAS. En el primer ejemplo no se especifica una subcarpeta. Esto significa que los PST se cargarán en la raíz (denominada *ingestiondata*) de la ubicación de almacenamiento de Azure. El segundo ejemplo carga los archivos PST en una subcarpeta (denominada *PSTFiles*) en la raíz de la ubicación de almacenamiento de Azure.  <br/> | `/Dest:"https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata?sv=2012-02-12&amp;se=9999-12-31T23%3A59%3A59Z&amp;sr=c&amp;si=IngestionSasForAzCopy201601121920498117&amp;sig=Vt5S4hVzlzMcBkuH8bH711atBffdrOS72TlV1mNdORg%3D"` <br/> O bien  <br/>  `/Dest:"https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata/PSTFiles?sv=2012-02-12&amp;se=9999-12-31T23%3A59%3A59Z&amp;sr=c&amp;si=IngestionSasForAzCopy201601121920498117&amp;sig=Vt5S4hVzlzMcBkuH8bH711atBffdrOS72TlV1mNdORg%3D"` <br/> |
    | `/V:` <br/> |Resulta en mensajes de estado detallados en un archivo de registro. De forma predeterminada, el archivo de registro detallado se denomina AzCopyVerbose.log en %LocalAppData%\Microsoft\Azure\AzCopy. Si especifica una ubicación de archivo existente para esta opción, el registro detallado se anexará a ese archivo.  <br/> No olvide incluir el valor de este parámetro entre comillas dobles (" ").  <br/> | `/V:"c:\Users\Admin\Desktop\Uploadlog.log"` <br/> |
    | `/S` <br/> |Este modificador opcional especifica el modo recursivo para que la herramienta AzCopy copie los archivos PST que se encuentran en las subcarpetas del directorio de origen especificado por el parámetro `/Source:`.  <br/> **Nota:** si incluye este modificador, los archivos PST de las subcarpetas tendrán un nombre de ruta de archivo diferente en la ubicación de almacenamiento de Azure una vez cargados. Tendrá que especificar el nombre exacto de la ruta de acceso de archivo en el archivo CSV que cree en el paso 4.  <br/> | `/S` <br/> |
    | `/Y` <br/> |Este modificador necesario permite el uso de tokens de SAS de solo escritura al cargar los archivos PST en la ubicación de almacenamiento de Azure. La URL de SAS que ha obtenido en el paso 1 (y especificado en el parámetro `/Dest:`) es una dirección URL de solo escritura de SAS, por lo que debe incluir este modificador. Una dirección URL de SAS de solo escritura no le impedirá usar el Explorador de Azure Storage para ver una lista de los archivos PST cargados en la ubicación de almacenamiento de Azure.  <br/> | `/Y` <br/> |
   
A continuación se muestra un ejemplo de la sintaxis de la herramienta AzCopy.exe, en el que se usan valores reales para cada parámetro:
    
```
  AzCopy.exe /Source:"\\FILESERVER1\PSTs" /Dest:"https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata?sv=2012-02-12&amp;se=9999-12-31T23%3A59%3A59Z&amp;sr=c&amp;si=IngestionSasForAzCopy201601121920498117&amp;sig=Vt5S4hVzlzMcBkuH8bH711atBffdrOS72TlV1mNdORg%3D" /V:"c:\Users\Admin\Desktop\AzCopy1.log" /Y
  
```

Después de ejecutar el comando, aparecen mensajes de estado en los que se muestra el progreso de la carga de los archivos PST. En un mensaje de estado final aparece el número total de archivos cargados correctamente.

> [!TIP]
> Después de ejecutar correctamente el comando AzCopy.exe y de comprobar que todos los parámetros son correctos, guarde una copia de la sintaxis de la línea de comandos en el mismo archivo (protegido) en el que ha copiado la información obtenida en el paso 1. Luego, puede copiar y pegar este comando en un símbolo del sistema cada vez que quiera ejecutar la herramienta AzCopy.exe para cargar los archivos PST a Office 365. Los únicos valores que puede que deba cambiar son los del parámetro `/Source:`. Esto depende del directorio de origen en el que están los archivos PST.

## <a name="optional-step-3-view-a-list-of-the-pst-files-uploaded-to-office-365"></a>Paso 3 (opcional): ver una lista de los archivos PST cargados en Office 365

Como paso opcional, puede instalar y usar el Explorador de Microsoft Azure Storage (una herramienta gratuita de código abierto) para ver la lista de archivos PST que ha cargado en el blob de Azure. Hay dos motivos principales para hacerlo:
  
- Comprobar que los archivos PST de la carpeta compartida o el servidor de archivos de la organización se cargaron correctamente en el blob de Azure.
    
- Comprobar el nombre de archivo (y el nombre de ruta de subcarpeta, si se incluye) de cada archivo PST cargado en el blob de Azure. Esto es muy útil al crear el archivo de asignación de PST en el paso siguiente, ya que tendrá que especificar el nombre de ruta de la carpeta y el nombre de archivo de todos los archivos PST. Comprobar estos nombres puede ayudar a reducir posibles errores en el archivo de asignación de PST.
    
El Explorador de Microsoft Azure Storage está en versión preliminar.
  
> [!IMPORTANT]
> No puede usar el Explorador de Microsoft Azure Storage para cargar o modificar archivos PST. El único método admitido para importar archivos PST a Office 365 es usar AzCopy. Además, no puede eliminar archivos PST que haya cargado al blob de Azure. Si intenta eliminar un archivo PST, recibirá un error sobre no tener los permisos necesarios. Tenga en cuenta que todos los archivos PST se eliminan automáticamente de su área de almacenamiento de Azure. Si no hay ningún trabajo de importación en curso, los archivos PST del contenedor **ingestiondata** se eliminarán en un plazo de 30 días tras crear el último trabajo de importación.
  
Para instalar el Explorador de Azure Storage y conectarse al área de almacenamiento de Azure, haga lo siguiente:
  
1. Descargue e instale la [herramienta Explorador de Microsoft Azure Storage](https://go.microsoft.com/fwlink/p/?LinkId=544842).
    
2. Inicie el Explorador de Microsoft Azure Storage, haga clic derecho en **Cuentas de almacenamiento** en el panel izquierdo y, después, haga clic en **Conectar con almacenamiento de Azure**.
    
    ![Hacer clic derecho en Cuentas de almacenamiento y, después, hacer clic en Conectar a almacenamiento de Azure](media/75b80cc3-c336-4f96-ad32-54ac9b96a7af.png)
  
3. Haga clic en **Usar un URI de Firma de acceso compartido (SAS) o cadena de conexión** y haga clic en **Siguiente**.
    
4. Haga clic en **Usar un URI de SAS**, pegue la dirección URL de SAS que obtuvo en el paso 1 en el cuadro situado bajo **URI** y, después, haga clic en **Siguiente**.
    
5. En la página **Resumen de conexión**, puede revisar la información de conexión y, después, haga clic en **Conectar**.
    
    Se abre el contenedor **ingestiondata** que contiene los archivos PST que ha cargado en el paso 2. El contenedor **ingestiondata** se encuentra en **Cuentas de almacenamiento** \> **(servicios vinculados de SAS)** \> **Contenedores de blob**. 
    
    ![El Explorador de Azure Storage muestra una lista de los archivos PST que ha cargado](media/12376fed-13a5-4a09-8fe6-e819e011b334.png)
  
6. Cuando termine de usar el Explorador de Microsoft Azure Storage, haga clic derecho en **ingestiondata** y, después, haga clic en **Desasociar** para desconectarse del área de almacenamiento de Azure. En caso contrario, recibirá un error la próxima vez que intente vincularse. 
    
    ![Hacer clic derecho en la ingesta y hacer clic en Desasociar para desconectarse de su área de almacenamiento de Azure](media/1e8e5e95-4215-4ce4-a13d-ab5f826a0510.png)
  
## <a name="step-4-create-the-pst-import-mapping-file"></a>Paso 4: crear el archivo de asignación de importación de PST

Después de cargar los archivos PST en la ubicación de almacenamiento de Azure de su organización de Office 365, el siguiente paso consiste en crear un archivo de valores separados por comas (CSV) que especifique los buzones de usuario en los que se importarán los archivos PST. Este archivo CSV se enviará en el paso siguiente, cuando cree un trabajo de importación de archivos PST.
  
1. [Descargue una copia del archivo de asignación de importación de PST](https://go.microsoft.com/fwlink/p/?LinkId=544717).
    
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

   **Nota:** no cambie nada en la fila de encabezado, ni siquiera los parámetros SharePoint. Se ignorarán durante el proceso de importación de PST. 

 3. Use la información de la tabla siguiente para rellenar el archivo CSV con la información necesaria.


    |**Parámetro**|**Descripción**|**Ejemplo**|
    |:-----|:-----|:-----|
    | `Workload` <br/> |Especifica el servicio de Office 365 en el que se importarán los datos. Use `Exchange` para importar archivos PST a los buzones de los usuarios.  <br/> | `Exchange` <br/> |
    | `FilePath` <br/> |Especifica la ubicación de la carpeta en la ubicación de almacenamiento de Azure en la que ha cargado los archivos PST en el paso 2.  <br/> Si no ha incluido un nombre de subcarpeta opcional en la dirección URL de SAS en el parámetro `/Dest:` del paso 2, deje este parámetro en blanco en el archivo CSV. Si ha incluido un nombre de subcarpeta, especifíquelo en este parámetro (vea el segundo ejemplo). El valor de este parámetro distingue mayúsculas de minúsculas.  <br/> En cualquier caso, *no* incluya "ingestiondata" en el valor del parámetro `FilePath`.  <br/><br/> **Importante:** el uso de mayúsculas y minúsculas del nombre de la ruta de acceso del archivo debe ser el mismo que el usado si ha incluido un nombre de subcarpeta opcional en la dirección URL de SAS en el parámetro `/Dest:` del paso 2. Por ejemplo, si en el paso 2 ha usado `PSTFiles` para el nombre de subcarpeta y, después, `pstfiles` en el parámetro `FilePath` del archivo CSV, se producirá un error en la importación del archivo PST. Asegúrese de usar las mismas mayúsculas y minúsculas en ambas instancias.  <br/> |(se deja en blanco)  <br/> O bien  <br/>  `PSTFiles` <br/> |
    | `Name` <br/> |Especifica el nombre del archivo PST que se importará al buzón del usuario. El valor de este parámetro distingue mayúsculas de minúsculas.  <br/> <br/>**Importante:** el uso de mayúsculas y minúsculas del nombre de archivo PST en el archivo CSV debe ser el mismo que el archivo PST cargado en la ubicación de almacenamiento de Azure en el paso 2. Por ejemplo, si usa `annb.pst` en el parámetro `Name` del archivo CSV, pero el nombre del archivo PST real es `AnnB.pst`, se producirá un error en la importación de ese archivo PST. Asegúrese de que el nombre del PST en el archivo CSV use las mismas mayúsculas y minúsculas que el archivo PST real.  <br/> | `annb.pst` <br/> |
    | `Mailbox` <br/> |Especifica la dirección de correo electrónico del buzón en el que se importará el archivo PST. Tenga en cuenta que no puede especificar una carpeta pública porque el servicio de importación de PST no admite la importación de archivos PST a carpetas públicas.  <br/> Para importar un archivo PST a un buzón inactivo, tiene que especificar el GUID del buzón de correo de este parámetro. Para obtener este GUID, ejecute el siguiente comando de PowerShell en Exchange Online:  `Get-Mailbox <identity of inactive mailbox> -InactiveMailboxOnly | FL Guid` <br/> <br/>**Nota:** en algunos casos, es posible que tenga varios buzones con la misma dirección de correo electrónico, donde un buzón es un buzón activo y el otro buzón está en un estado de eliminación temporal (o inactivo). En estas situaciones, tiene que especificar el GUID del buzón de correo para identificar exclusivamente el buzón en el que se importa el archivo PST. Para obtener este GUID para los buzones activos, ejecute el siguiente comando de PowerShell: `Get-Mailbox <identity of active mailbox> | FL Guid`. Para obtener el GUID para los buzones eliminados temporalmente (o inactivos), ejecute este comando `Get-Mailbox <identity of soft-deleted or inactive mailbox> -SoftDeletedMailbox | FL Guid`.  <br/> | `annb@contoso.onmicrosoft.com` <br/> O bien  <br/>  `2d7a87fe-d6a2-40cc-8aff-1ebea80d4ae7` <br/> |
    | `IsArchive` <br/> | Especifica si se va a importar o no el archivo PST en el buzón de archivo del usuario. Hay dos opciones:  <br/><br/>**FALSE**: importa el archivo PST en el buzón principal del usuario.  <br/> **TRUE**: importa el archivo PST en el buzón de archivo del usuario. Esto supone que el [buzón de archivo del usuario está habilitado](enable-archive-mailboxes.md). <br/><br/>Si establece este parámetro en `TRUE` y el buzón de archivo del usuario no está habilitado, se producirá un error en la importación para ese usuario. Tenga en cuenta que si falla una importación para un usuario (porque su archivo no está habilitado y esta propiedad se establece en `TRUE`), los demás usuarios en el trabajo de importación no se verán afectados.  <br/>  Si deja este parámetro en blanco, el archivo PST se importa al buzón de correo principal del usuario.  <br/> <br/>**Nota**: para importar un archivo PST a un buzón de archivo basado en la nube para un usuario cuyo buzón de correo principal es local, solo tiene que especificar `TRUE` para este parámetro y especificar la dirección de correo electrónico del buzón local del usuario para el parámetro `Mailbox`.  <br/> | `FALSE` <br/> O bien  <br/>  `TRUE` <br/> |
    | `TargetRootFolder` <br/> | Especifica la carpeta en la que se importa el archivo PST.  <br/>  Si deja este parámetro en blanco, el archivo PST se importará a una carpeta nueva llamada **Importados**, ubicada en el nivel raíz del buzón (el mismo nivel que la Bandeja de entrada y el resto de las carpetas del buzón predeterminadas).  <br/>  Si especifica `/`, los elementos del archivo PST se importarán directamente en la carpeta Bandeja de entrada del usuario.  <br/><br/>  Si especifica `/<foldername>`, los elementos del archivo PST se importarán a una carpeta llamada \<*Nombre de carpeta\>*. Por ejemplo, si usa `/ImportedPst`, los elementos se importarán a una carpeta llamada **PST importados**. Esta carpeta estará ubicada en el buzón del usuario en el mismo nivel que la carpeta Bandeja de entrada.  <br/><br/> **Sugerencia:** considere la posibilidad de ejecutar algunos lotes de prueba para experimentar este parámetro y determinar la mejor ubicación de la carpeta en la que va a importar los archivos PST.  <br/> |(se deja en blanco)  <br/> O bien  <br/>  `/` <br/> O bien  <br/>  `/ImportedPst` <br/> |
    | `ContentCodePage` <br/> |Este parámetro opcional especifica un valor numérico de la página de códigos que se usa para importar archivos PST en el formato de archivo ANSI. Este parámetro se usa para importar archivos PST de las organizaciones de chino, japonés y coreano, porque estos idiomas suelen usar un juego de caracteres doble byte (DBCS) para la codificación de caracteres. Si no se usa este parámetro para importar archivos PST de los idiomas que usan DBCS para los nombres de las carpetas de buzón, dichos nombres suelen ser incomprensibles después de la importación.  <br/><br/> Para obtener una lista de los valores compatibles que se pueden usar para este parámetro, vea [Identificadores de página de códigos](https://go.microsoft.com/fwlink/p/?LinkId=328514).  <br/> <br/>**Nota:** como se ha mencionado anteriormente, se trata de un parámetro opcional y no es necesario incluirlo en el archivo CSV. También puede incluirlo y dejar el valor en blanco para una o varias filas.  <br/> |(se deja en blanco)  <br/> O bien  <br/>  `932` (que es el identificador de página de códigos para ANSI/OEM japonés)  <br/> |
    | `SPFileContainer` <br/> |Para la importación de archivos PST, deje este parámetro en blanco.  <br/> |No aplicable  <br/> |
    | `SPManifestContainer` <br/> |Para la importación de archivos PST, deje este parámetro en blanco.  <br/> |No aplicable  <br/> |
    | `SPSiteUrl` <br/> |Para la importación de archivos PST, deje este parámetro en blanco.  <br/> |No aplicable  <br/> |

## <a name="step-5-create-a-pst-import-job-in-office-365"></a>Paso 5: crear un trabajo de importación de PST en Office 365

El siguiente paso consiste en crear el trabajo de importación de PST en el servicio de importación de Office 365. Como se ha explicado anteriormente, enviará el archivo de asignación de importación de PST que ha creado en el paso 4. Después de crear el nuevo trabajo, Office 365 analiza los datos de los archivos PST y, después, le da la oportunidad de filtrar los datos que se importan realmente a los buzones especificados en el archivo de asignación de importación de PST (vea el [paso 6](#step-6-filter-data-and-start-the-pst-import-job)).
  
1. Ve a [https://protection.office.com](https://protection.office.com) e inicie sesión con las credenciales de una cuenta de administrador en su organización de Office 365. 
    
2. En el panel izquierdo del Centro de seguridad y cumplimiento, haga clic en **Gobierno de datos** y, después, en **Importar**.
    
3. En la página **Importar**, haga clic en ![Agregar icono](media/ITPro-EAC-AddIcon.gif) **Nuevo trabajo de importación**.
    
    **Nota:** debe tener asignados los permisos adecuados para tener acceso a la página **Importar** en el Centro de seguridad y cumplimiento para crear un nuevo trabajo de importación. Vea la sección **Antes de empezar** para obtener más información. 
    
4. Escriba un nombre para el trabajo de importación de PST y haga clic en **Siguiente**. Use letras minúsculas, números, guiones y caracteres de subrayado. Las letras en mayúscula no se pueden usar ni se pueden incluir espacios en el nombre.
    
5. En la página **¿Quiere cargar o enviar datos?**, haga clic en **Cargar los datos** y, después, en **Siguiente**.
    
    ![Hacer clic en Cargar los datos para crear un trabajo de importación de carga en la red](media/e59f9dc3-ccde-44ff-ac38-c4e39d76ae85.png)
  
6. En el paso 4, en la página **Importar datos**, marque las casillas **Terminé de cargar mis archivos** y **Tengo acceso al archivo de asignación**, y haga clic en **Siguiente**.
    
    ![Marcar las dos casillas del paso 4](media/9f2427e8-3af2-4e27-95e6-a9f08430d3d8.png)
  
7. En la página **Seleccionar el archivo de asignación**, haga clic en **Seleccionar el archivo de asignación** para enviar el archivo de asignación de importación de PST que ha creado en el paso 4. 
    
    ![Hacer clic en Seleccionar el archivo de asignación para enviar el archivo CSV que ha creado para el trabajo de importación](media/d30b1d73-80bb-491e-a642-a21673d06889.png)
  
8. Cuando el nombre del archivo CSV aparezca en **Asignación del nombre de archivo**, haga clic en **Validar** para comprobar si hay errores en el archivo CSV. 
    
    ![Hacer clic en Validar para comprobar si hay errores en el archivo CSV](media/4680999d-5538-4059-b878-2736a5445037.png)
  
    El archivo CSV debe estar validado correctamente para poder crear un trabajo de importación de PST. Tenga en cuenta que el nombre del archivo se cambia a verde una vez que se ha validado correctamente. Si se produce un error de validación, haga clic en el vínculo **Ver registro**. Se abre un informe de errores de validación, con un mensaje de error para cada fila del archivo que ha fallado. 
    
9. Cuando el archivo de asignación de importación de PST se haya validado correctamente, lea el documento de términos y condiciones y, después, marque la casilla.
    
10. Haga clic en **Guardar** para enviar el trabajo y, después de crear correctamente el trabajo, haga clic en **Cerrar**. 
    
    Se muestra una página de control flotante de estado, con un estado de **Análisis en curso** y el nuevo trabajo de importación en la lista de la página **Importar**. 
    
11. Haga clic en **Actualizar** ![Icono Actualizar](media/O365-MDM-Policy-RefreshIcon.gif) para actualizar la información de estado que se muestra en la columna **Estado**. Cuando el análisis se haya completado y los datos estén listos para su importación, el estado cambia a **Análisis finalizado**.
    
    Puede hacer clic en el trabajo de importación para mostrar la página de control flotante de estado, que contiene información más detallada sobre el trabajo de importación, como el estado de todos los archivos PST que aparecen en el archivo de asignación.
 
## <a name="step-6-filter-data-and-start-the-pst-import-job"></a>Paso 6: filtrar los datos e iniciar el trabajo de importación de PST

Después de crear e iniciar el trabajo de importación en el paso 5, Office 365 analiza de forma segura los datos de los archivos PST. Esto conlleva identificar la antigüedad de los elementos y los diferentes tipos de mensajes incluidos en los archivos PST. Una vez se haya completado el análisis y los datos estén listos para la importación, tiene la opción de importar todos los datos incluidos en los archivos PST o de recortar solo algunos de ellos, estableciendo filtros para controlar los datos para importar.
  
1. En la página **Importar** en el Centro de seguridad y cumplimiento, haga clic en **Preparado para importar a Office 365** para el trabajo de importación que ha creado en el paso 5. 
    
    ![Hacer clic en Preparado para importar a Office 365, junto al trabajo de importación que ha creado](media/5760aac3-300b-4e31-b894-253c42a4b82b.png)
  
    Se muestra una página de control flotante con información sobre los archivos PST y otra información sobre el trabajo de importación.
    
2. En la página de control flotante, haga clic en **Importar a Office 365**.
    
    Se mostrará la página **Filtrar los datos**. Contiene las información sobre datos resultante del análisis realizado en los archivos PST por Office 365, incluida la antigüedad de los datos. En este momento, tiene la opción de filtrar los datos que se importarán o importar todos los datos tal como estén. 
    
    ![Puede recortar los datos de los archivos PST o importarlos todos](media/287fc030-99e9-417b-ace7-f64617ea5d4e.png)
  
3. Realice una de las acciones siguientes:
    
    A. Para recortar los datos que importa, haga clic en **Sí, quiero filtrarlos antes de importarlos**.
    
    Para obtener instrucciones detalladas paso a paso sobre cómo filtrar los datos en los archivos PST y, después, iniciar el trabajo de importación, vea [Filtrar datos al importar archivos PST a Office 365](filter-data-when-importing-pst-files.md).
    
    O bien
    
    B. Para importar todos los datos de los archivos PST, haga clic en **No, quiero importarlos todos** y en **Siguiente**.
    
4. Si ha elegido importar todos los datos, haga clic en **Importar datos** para iniciar el trabajo de importación. 
    
    El estado del trabajo de importación se mostrará en la página **Importar**. Haga clic en el ![icono Actualizar](media/O365-MDM-Policy-RefreshIcon.gif) **Actualizar** para actualizar la información de estado que se muestra en la columna **Estado**. Haga clic en el trabajo de importación para mostrar la página de control flotante de estado, donde se muestra la información de estado de cada archivo PST que se importa. 

## <a name="how-the-import-process-works"></a>Cómo funciona el proceso de importación
  
Puede usar la opción carga en la red y el servicio de importación de Office 365 para importar archivos PST en bloque a los buzones de usuario. La carga en la red significa que carga los archivos PST en un área de almacenamiento temporal en la nube de Microsoft. Luego, el servicio de importación de Office 365 copia los archivos PST del área de almacenamiento en los buzones de usuario de destino.
  
Aquí se muestra una ilustración y una descripción del proceso de carga en la red para importar archivos PST a buzones de Office 365.
  
![Flujo de trabajo del proceso de carga en la red para importar archivos PST a Office 365](media/9e05a19e-1e7a-4f1f-82df-9118f51588c4.png)
  
1. **Descargar la herramienta de importación de PST y la clave en la ubicación de almacenamiento de Azure privada**: el primer paso es descargar la herramienta de línea de comandos de Azure AzCopy y una clave de acceso usada para cargar los archivos PST en una ubicación de almacenamiento de Azure en la nube de Microsoft. Puede obtenerlas en la página **Importar** en el Centro de seguridad y cumplimiento. La clave (denominada SAS, firma de acceso seguro) le proporciona los permisos necesarios para cargar los archivos PST en una ubicación de almacenamiento de Azure privada y segura. Esta clave de acceso es exclusiva para su organización y le ayuda a evitar el acceso no autorizado a archivos PST tras su carga en la nube de Microsoft. Tenga en cuenta que para importar archivos PST a Office 365 su organización no necesita una suscripción a Azure separada. 
    
2. **Cargar los archivos PST en la ubicación de almacenamiento de Azure**: el siguiente paso es usar la herramienta AzCopy.exe (descargada en el paso 1) para cargar y almacenar los archivos PST en una ubicación de almacenamiento de Azure que se encuentre en el mismo centro de datos regional de Microsoft que su organización de Office 365. Para poder cargar los archivos PST que quiere importar a Office 365, estos deben encontrarse en un recurso compartido de archivos o en un servidor de archivos de su organización.
    
    Tenga en cuenta que hay un paso opcional que puede realizar para ver la lista de los archivos PST una vez que se hayan cargado en la ubicación de almacenamiento de Azure.
    
3. **Crear un archivo de asignación de importación de PST**: una vez que los archivos PST se hayan cargado en la ubicación de almacenamiento de Azure, el siguiente paso es crear un archivo de valores separados por comas (CSV) que especifique los buzones de usuario en los que se importarán los archivos PST. Tenga en cuenta que un archivo PST se puede importar al buzón principal de un usuario o al buzón de archivo. El servicio de importación de Office 365 usará la información del archivo CVS para importar los archivos PST.
    
4. **Crear un trabajo de importación de PST**: el siguiente paso es crear un trabajo de importación de PST en la página **Importar** del Centro de cumplimiento y seguridad, y enviar el archivo de asignación de importación de PST creado en el paso anterior. Una vez creado el trabajo de importación, Office 365 analiza los datos de los archivos PST y, después, le permite establecer filtros para controlar los datos que se importan a los buzones especificados en el archivo de asignación de importación de PST. 
    
5. **Filtrar los datos PST que se importarán a los buzones**: después de crear e iniciar el trabajo de importación, Office 365 analiza de forma segura los datos de los archivos PST. Esto conlleva identificar la antigüedad de los elementos y los diferentes tipos de mensajes incluidos en los archivos PST. Una vez se haya completado el análisis y los datos estén listos para la importación, tiene la opción de importar todos los datos incluidos en los archivos PST o de recortar solo algunos de ellos, estableciendo filtros para controlar los datos para importar.
    
6. **Iniciar el trabajo de importación de PST**: una vez iniciado el trabajo de importación, Office 365 usará la información del archivo de asignación para importar los archivos PST desde la ubicación de almacenamiento de Azure a los buzones de usuario. En la página de **Importar** del Centro de cumplimiento y seguridad se mostrará información de estado sobre el trabajo de importación (incluida información individual de cada archivo PST importado). Cuando finalice el trabajo de importación, el estado del trabajo aparecerá como **Completado**.
  
## <a name="more-information"></a>Más información

- ¿Por qué importar archivos PST a Office 365?
    
  - Es una buena forma de importar los datos de mensajería de archivo de la organización a Office 365.
    
  - Los datos están disponibles para el usuario en todos los dispositivos, ya que se almacenan en la nube.
    
  - Permite satisfacer las necesidades de cumplimiento de su organización, ya que le permite aplicar las características de cumplimiento de Office 365 a los datos de los archivos PST que ha importado. Esto incluye:
    
  - Habilitar [buzones de archivo](enable-archive-mailboxes.md) y el [archivado de ampliación automática](enable-unlimited-archiving.md) para dar a los usuarios espacio de almacenamiento de buzón adicional para almacenar los datos importados. 
    
  - Colocar los buzones en [Suspensión por litigio](https://go.microsoft.com/fwlink/?linkid=856286) para conservar los datos importados. 
    
  - Usar las [herramientas eDiscovery](search-for-content.md) de Microsoft para buscar en los datos importados. 
    
  - Usar [las directivas de retención de Office 365](retention-policies.md) para controlar cuánto tiempo se conservan los datos importados y las acciones que deben realizarse cuando expire el período de retención. 
    
  - Buscar en el [registro de auditoría de Office 365](search-the-audit-log-in-security-and-compliance.md) eventos relacionados con el buzón que afectan a los datos importados. 
    
  - Importar datos a [buzones de correo inactivos](create-and-manage-inactive-mailboxes.md) para archivar datos por motivos de cumplimiento. 
    
  - Usar [directivas de prevención de pérdida de datos](data-loss-prevention-policies.md) para evitar la pérdida de datos confidenciales fuera de su organización. 
  
- Este es un ejemplo de la dirección URL de la Firma de acceso compartido (SAS) que se ha obtenido en el paso 1. Este ejemplo también contiene la sintaxis del comando que se ejecuta en la herramienta AzCopy.exe para cargar los archivos PST a Office 365. Asegúrese de tomar precauciones para proteger la URL de SAS de la misma manera que protegería las contraseñas u otra información relacionada con la seguridad.

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
    
