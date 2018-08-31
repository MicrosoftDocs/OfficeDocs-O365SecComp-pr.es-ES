---
title: Usar el trasvase de registros de unidad para importar los archivos PST de organización a Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/14/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 40829b57-793c-4d41-b171-e9270129173d
description: 'Para los administradores: información sobre la importación masiva los archivos PST de su organización a buzones de correo de Office 365 copiando los archivos PST a una unidad de disco duro y, a continuación, enviarlo a Microsoft. '
ms.openlocfilehash: ebe88918b6c25e18562db7817d22fbf71f05e4c7
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22536111"
---
# <a name="use-drive-shipping-to-import-your-organization-pst-files-to-office-365"></a>Usar el trasvase de registros de unidad para importar los archivos PST de organización a Office 365

**En este artículo está dirigido a administradores. ¿Está intentando importar archivos PST en su propio buzón? Consulte el [correo electrónico de importación, contactos y calendario desde un archivo .pst de Outlook](https://go.microsoft.com/fwlink/p/?LinkID=785075)**
   
Usar el servicio Office 365 importar y la unidad de envío para la importación masiva de archivos PST a buzones de usuario. Envío de unidad significa que copie los archivos PST en una unidad de disco duro y, a continuación, enviar físicamente la unidad a Microsoft. Cuando Microsoft recibe la unidad de disco duro, personal del centro de datos va a copiar los datos de la unidad de disco duro a un área de almacenamiento en la nube de Microsoft. A continuación, tiene la oportunidad de recortar los datos de PST que realmente se importan a los buzones de correo de destino mediante la configuración de filtros que controlan qué datos obtiene importados. Después de iniciar el trabajo de importación, el servicio de importación importa los datos de PST desde el área de almacenamiento para los buzones de usuario. Uso de trasvase de registros de unidad para importar archivos PST a buzones de usuario es una forma de migrar correo electrónico de su organización a Office 365.
  
Estos son los pasos necesarios para usar la unidad de envío para importar archivos PST a buzones de Office 365:
  
[Paso 1: Descargue la herramienta de importación de PST y clave de almacenamiento seguro](#step-1-download-the-secure-storage-key-and-pst-import-tool)

[Paso 2: Copiar los archivos PST en la unidad de disco duro](#step-2-copy-the-pst-files-to-the-hard-drive)

[Paso 3: Crear el archivo de asignación de importación de PST](#step-3-create-the-pst-import-mapping-file)

[Paso 4: crear un trabajo de importación de PST en Office 365](#step-4-create-a-pst-import-job-in-office-365)

[Paso 5: enviar la unidad de disco duro a Microsoft](#step-5-ship-the-hard-drive-to-microsoft)

[Paso 6: Filtrar datos e iniciar el trabajo de importación de PST](#step-6-filter-data-and-start-the-pst-import-job)
  
> [!IMPORTANT]
> Se debe realizar el paso 1 una vez para hacia abajo de carga de la clave de almacenamiento seguro y la herramienta de importación. Después de realizar estos pasos, siga el paso 2 a 6 cada vez que desee enviar una unidad de disco duro a Microsoft. 
  
Para las preguntas más frecuentes acerca del uso de unidad de envío para importar archivos PST a Office 365, vea [las preguntas más frecuentes para el uso de unidad de envío para importar los archivos PST](faqimporting-pst-files-to-office-365.md#using-drive-shipping-to-import-pst-files). 
  
## <a name="before-you-begin"></a>Antes de empezar

- Se debe asignar la función de importación de exportación de buzones de correo en Exchange en línea para importar archivos PST a buzones de Office 365. De forma predeterminada, este rol no está asignado a ningún grupo de funciones en Exchange Online. Puede agregar la función de exportación de importación de buzón de correo para el grupo de roles de administración de la organización. O bien, puede crear un nuevo grupo de roles, asignar el rol de buzón de correo importar exportar y, a continuación, agregue a usted como un miembro. Para obtener más información, vea el "Agregar un rol a un grupo de roles" o la "crear un grupo de roles" secciones en [Administrar grupos de roles](https://go.microsoft.com/fwlink/p/?LinkId=730688).
    
    Además crear la importación de trabajos en la seguridad de Office 365 &amp; debe ser verdadero centro de cumplimiento, uno de los siguientes:
    
  - Se debe tener asignado el rol de destinatarios de correo en Exchange Online. De forma predeterminada, este rol se asigna a los grupos de funciones de administración de la organización y administración de destinatarios.
    
    O bien
    
  - Debe ser un administrador global de la organización de Office 365.
    
    > [!TIP]
    > Considere la posibilidad de crear un nuevo grupo de funciones en Exchange Online diseñada específicamente para la importación de los archivos PST a Office 365. Para el nivel mínimo de privilegios necesarios para importar los archivos PST, asigne las funciones de importación de exportación de buzones de correo y destinatarios de correo para el nuevo grupo de roles y, a continuación, agregar a miembros. 
  
- Que se necesita para almacenar los archivos PST que se desean copiar en una unidad de disco duro en un servidor de archivos o la carpeta compartida en la organización. En el paso 2, podrá ejecutar la herramienta de exportación de importación de Azure (WAImportExport.exe) que va a copiar los archivos PST que se almacenan en este servidor de archivo o carpeta a la unidad de disco duro comparten.
    
- Unidades de sólo 2,5 pulgadas de estado sólido (SSD) o 2,5 o 3,5 pulgadas SATA II/III interno unidades de disco duro compatibles para su uso con el servicio de importación de Office 365. Puede usar unidades de disco duro hasta 10 TB. Para los trabajos de importación, se procesarán solo el primer volumen de datos en la unidad de disco duro. El volumen de datos debe tener el formato NTFS. Cuando se copian datos a una unidad de disco duro, puede adjuntarlo directamente con un SSD de 2,5 pulgadas o 2,5 o 3,5 pulgadas conector SATA II/III o puede adjuntar externamente mediante un SSD de 2,5 pulgadas externo o adaptador de SATA II/III USB 2,5 o 3,5 pulgadas.
    
    > [!IMPORTANT]
    > Unidades de disco duro externas que vienen con un adaptador USB integrado no son compatibles con el servicio de importación de Office 365. Además, no se puede utilizar el disco dentro de mayúsculas y minúsculas de una unidad de disco duro externa. Por favor, no se suministran unidades de disco duro externas. 
  
- La unidad de disco duro que copie los archivos PST a debe estar cifrada con BitLocker. La herramienta WAImportExport.exe que se ejecutan en el paso 2 le ayudará a configurar BitLocker. También genera una clave de cifrado BitLocker que Microsoft personal del centro de datos va a utilizar para tener acceso a la unidad para cargar los archivos PST en el área de almacenamiento de Azure en la nube de Microsoft.
    
- Envío de la unidad está disponible a través de un contrato Enterprise de Microsoft (EA). Unidad de trasvase de registros no está disponible a través de un Microsoft Products y un contrato de servicios (MPSA).
    
- El costo para importar archivos PST a buzones de Office 365 con el trasvase de registros de unidad es 2 dólares por GB de datos. Por ejemplo, si incluye una unidad de disco duro que contiene 1.000 GB (1TB) de los archivos PST, el costo es $2.000 USD. Puede trabajar con un socio de pago de la cuota de importación. Para obtener información acerca de cómo buscar a un socio, vea [encontrar su socio de Office 365 o revendedor](https://go.microsoft.com/fwlink/p/?LinkId=785197).
    
- Usted o su organización debe tener una cuenta con FedEx o DHL. 
    
  - Las organizaciones de los Estados Unidos, Brasil, Europa y deben tener cuentas de FedEx.
    
  - Las organizaciones de Asia oriental, sureste de Asia, Japón, República de Corea y Australia deben tener cuentas DHL.
    
    Microsoft usará (y cargará) esta cuenta para devolverle la unidad de disco duro. 
    
- Es posible que la unidad de disco duro que envíe a Microsoft deba cruzar las fronteras internacionales. Si es el caso, usted es responsable de garantizar que la unidad de disco duro y los datos que contiene se importen o se exporten de acuerdo con la legislación vigente. Antes de enviar una unidad de disco duro, póngase en contacto con sus asesores para comprobar que la unidad y los datos se puedan enviar de forma legal al centro de datos de Microsoft identificado. De esta forma, se asegurará de que llega a Microsoft de forma puntual.
    
- Este procedimiento implica copiar y guardar una clave de almacenamiento seguro y una clave de cifrado BitLocker. Asegúrese de tomar precauciones para proteger estas claves como haría proteger las contraseñas u otra información relacionada con la seguridad. Por ejemplo, es posible que guardarlos en un documento de Microsoft Word protegidos con contraseña o guardarlos en una unidad USB cifrada. Vea la sección [obtener más información](use-drive-shipping-to-import-pst-files-to-office-365.md#moreinfo) para obtener un ejemplo de estas claves. 
    
- Una vez que se importan los archivos PST en un buzón de Office 365, la suspensión de retención establecer para el buzón de correo está activada para una duración indefinida. Esto significa que no se procesará la directiva de retención asignada al buzón hasta que se desactiva la suspensión de retención o establecer una fecha para desactivar la suspensión. ¿Por qué hacemos esto? Si los mensajes que se importa a un buzón de correo son anteriores, se podría eliminar permanentemente (purga) debido a que ha caducado su período de retención en función de la configuración de retención configurada para el buzón de correo. Colocar el buzón de correo en suspensión de retención, le dará el tiempo de propietario del buzón de correo para administrar estos mensajes recién importadas o ceder mucho tiempo para cambiar la configuración de retención para el buzón de correo. Vea la sección [obtener más información](use-drive-shipping-to-import-pst-files-to-office-365.md#moreinfo) para obtener sugerencias acerca de cómo administrar la suspensión de retención. 
    
- De forma predeterminada, el tamaño máximo de mensaje que se puede recibir un buzón de Office 365 es 35 MB. Eso es porque el valor predeterminado para la propiedad *MaxReceiveSize* para un buzón de correo se establece en 35 MB. Sin embargo, el límite de tamaño de recepción el máximo de mensaje en Office 365 es 150 MB. Por tanto, si importa un archivo PST que contiene un elemento más de 35 MB, el servicio Office 365 importar se cambiará automáticamente el valor de la propiedad *MaxReceiveSize* en el buzón de destino a 150 MB. Esto permite que los mensajes que se debe importar a buzones de usuario hasta 150 MB. 
    
    > [!TIP]
    > Para identificar el mensaje de tamaño de recepción para un buzón de correo, se puede ejecutar este comando en Exchange Online PowerShell: `Get-Mailbox <user mailbox> | FL MaxReceiveSize`. 
  
- Puede importar archivos PST a un buzón de correo inactivo en Office 365. Para ello, que especifica el GUID del buzón de correo inactivo en el `Mailbox` parámetro en el archivo de asignación de importación de PST. Vea [paso 3: crear el archivo de asignación de importación de PST](use-drive-shipping-to-import-pst-files-to-office-365.md#step3) para obtener más información. 
    
- En una implementación híbrida de Exchange, puede importar archivos PST en un buzón de archivo basados en la nube para un usuario cuyo buzón de correo principal es local. Para ello, hacer lo siguiente en el archivo de asignación de importación de PST:
    
  - Especifique la dirección de correo electrónico para el buzón del usuario local en el `Mailbox` parámetro. 
    
  - Especificar el valor **TRUE** en el `IsArchive` parámetro. 
    
    Vea [paso 3: crear el archivo de asignación de importación de PST](use-drive-shipping-to-import-pst-files-to-office-365.md#step3) para obtener más información. 

## <a name="step-1-download-the-secure-storage-key-and-pst-import-tool"></a>Paso 1: Descargue la herramienta de importación de PST y clave de almacenamiento seguro

El primer paso es descargar la clave de almacenamiento seguro y la herramienta y que se usará en el paso 2 para los archivos PST de copia a la unidad de disco duro.
  
> [!IMPORTANT]
> Se debe utilizar la versión de la herramienta de importación y exportación de Azure 1 (WAimportExportV1) para importar correctamente los archivos PST mediante el método de envío de la unidad. No se admite la versión 2 de la herramienta de importación y exportación de Azure y usarlo, se producirá en la preparación de forma incorrecta la unidad de disco duro para el trabajo de importación. Asegúrese de descargar la herramienta de importación y exportación de Azure de la seguridad &amp; centro de cumplimiento, siga los procedimientos descritos en este paso. 
  
1. Vaya a [https://protection.office.com/](https://protection.office.com/) e iniciar sesión con las credenciales para una cuenta de administrador de la organización de Office 365. 
    
2. En el panel izquierdo de la seguridad &amp; centro de cumplimiento, haga clic en **el gobierno de datos** \> **importación**.
    
    > [!NOTE]
    > Como se mencionó anteriormente, se debe tener asignados los permisos adecuados para tener acceso a la página de **importación** de la seguridad &amp; centro de cumplimiento. 
  
3. En la página **Importar** , haga clic en ![icono Agregar](media/ITPro-EAC-AddIcon.gif) **nuevo trabajo de importación**.
    
4. En el Asistente para importación de trabajo, escriba un nombre para el trabajo de importación de PST y, a continuación, haga clic en **siguiente**. Use las letras en minúscula, números, guiones y caracteres de subrayado. No se puede usar las letras en mayúsculas o incluir espacios en el nombre.
    
5. En la página **elija importar el tipo de trabajo** , haga clic en **unidades de disco duro de envío a uno de nuestras ubicaciones físicas** y, a continuación, haga clic en **siguiente**.
    
    ![Haga clic en unidades de disco duro de envío a uno de nuestras ubicaciones físicas para crear una unidad de trabajo de importación de envío](media/1584fdc5-cd4c-4e47-932e-db6c8e07f5f8.png)
  
6. En la página **Importar datos** , realice las siguientes dos cosas: 
    
    ![Copie la clave de almacenamiento seguro y descargar la herramienta de exportación de importación de Azure en la página de datos de importación](media/e22e0b48-e5ce-48e0-95bc-0490a2b3b983.png)
  
    r. en el paso 2, haga clic en **copiar la clave de almacenamiento seguro**. Después de que se muestra la clave de almacenamiento, haga clic en **Copiar al Portapapeles** y, a continuación, péguelo y guárdelo en un archivo, por lo que puede tener acceso a él más adelante.
    
    b. en el paso 3, **Descargue la herramienta de importación y exportación de Azure** para descargar e instalar la herramienta de importación y exportación de Azure (versión 1).
    
    - En la ventana emergente, haga clic en **Guardar** \> **Guardar como** para guardar el archivo WaImportExportV1.zip en una carpeta en el equipo local. 
    
    - Extraiga el archivo WaImportExportV1.zip.
    
7. Haga clic en **Cancelar** para cerrar al asistente. 
    
    Aquí volveremos a la página **Importar** en la seguridad &amp; centro de cumplimiento al crear el trabajo de importación en el paso 4. 

## <a name="step-2-copy-the-pst-files-to-the-hard-drive"></a>Paso 2: Copiar los archivos PST en la unidad de disco duro

El siguiente paso es usar la herramienta WAImportExport.exe para copiar los archivos PST en la unidad de disco duro. Esta herramienta cifra la unidad de disco duro con BitLocker, copia los archivos pst en la unidad de disco duro y crea un archivo de diario que almacena información sobre el proceso de copia. Para completar este paso, los archivos PST tienen que estar ubicada en un recurso compartido de archivos o un servidor de archivos en su organización. Esto se conoce como el directorio de origen en el procedimiento siguiente. 
  
> [!IMPORTANT]
> Después de ejecutar la herramienta WAImportExport.exe la primera vez para una unidad de disco duro, se debe usar una sintaxis diferente tiempo después de que. Esta sintaxis se explica en el paso 4 de este procedimiento para copiar los archivos PST en la unidad de disco duro. 
  
1. Abra el símbolo del sistema del equipo local.
    
    > [!TIP]
    > Si ejecuta el símbolo del sistema como administrador (seleccionando "Ejecutar como administrador" al abrirlo), en la ventana del símbolo del sistema aparecerán mensajes de error que le pueden ayudar a solucionar los problemas que aparecen al ejecutar la herramienta WAImportExport.exe. 
  
2. Vaya al directorio en el que instaló la herramienta WAImportExport.exe en el paso 1.
    
3. Ejecute el siguiente comando la primera vez que use la herramienta WAImportExport.exe para copiar archivos PST en una unidad de disco duro.

    ```
    WAImportExport.exe PrepImport /j:<Name of journal file> /t:<Drive letter> /id:<Name of session> /srcdir:<Location of PST files> /dstdir:<PST file path> /sk:<Storage account key> /encrypt /logdir:<Log file location>
    ```

    En la tabla siguiente se describen los parámetros y los valores requeridos.
    
    |**Parámetro**|**Descripción**|**Ejemplo**|
    |:-----|:-----|:-----|
    | `/j:` <br/> |Especifica el nombre del archivo de diario. Este archivo se guarda en la misma carpeta en la que se encuentra la herramienta WAImportExport.exe. Todas las unidades de disco duro que envíe a Microsoft deben tener un archivo de diario. Cada vez que ejecute la herramienta WAImportTool.exe para copiar archivos PST en una unidad de disco duro, la información se anexará al archivo de diario de esa unidad. 
  <br/> Personal del centro de datos de Microsoft usará la información en el archivo de diario para asociar la unidad de disco duro con el trabajo de importación que se crea en el paso 4 y para cargar los archivos PST en el área de almacenamiento de Azure en la nube de Microsoft.  <br/> | `/j:PSTHDD1.jrn` <br/> |
    | `/t:` <br/> |Especifica la letra de la unidad de disco duro cuando se conecta a su equipo local.  <br/> | `/t:h` <br/> |
    | `/id:` <br/> |Especifica el nombre de la sesión de copia. Cada vez que ejecuta la herramienta WAImportExport.exe para copiar los archivos en la unidad de disco duro, se define una sesión. Los archivos PST se copian en una carpeta cuyo nombre es el nombre de la sesión especificado por este parámetro.   <br/> | `/id:driveship1` <br/> |
    | `/srcdir:` <br/> |Especifica el directorio de origen en la organización que contiene los archivos PST que se copiarán durante la sesión. Asegúrese de que rodee el valor de este parámetro con comillas dobles ("").  <br/> | `/srcdir:"\\FILESERVER01\PSTs"` <br/> |
    | `/dstdir:` <br/> |Especifica el directorio de destino en el área de almacenamiento de Azure en la nube de Microsoft donde se cargará los archivos pst. Debe usar el valor `ingestiondata/`. Asegúrese de que rodee el valor de este parámetro con comillas dobles ("").<br/> De forma opcional, también puede agregar una ruta de acceso de archivo adicional en el valor de este parámetro. Por ejemplo, puede usar la ruta de acceso al directorio de origen en la unidad de disco duro (que se convierten a un formato de dirección URL), lo que se especifica en el `/srcdir:` parámetro. Por ejemplo, `\\FILESERVER01\PSTs` se ha cambiado a `FILESERVER01/PSTs`. En este caso, aún debe incluir `ingestiondata` en la ruta de acceso de archivo. En este ejemplo, el valor de la `/dstdir:` parámetro sería `"ingestiondata/FILESERVER01/PSTs"`.<br/> Una razón para agregar la ruta de acceso de archivo adicional es si hay archivos pst con el mismo nombre de archivo.  <br/> > [!NOTE]> Si se incluye el nombre de ruta opcional, el espacio de nombres para un archivo PST después de que se carga en el área de almacenamiento de Azure incluirá la ruta de acceso y el nombre del archivo PST; Por ejemplo, `FILESERVER01/PSTs/annb.pst`. Si no incluye una ruta de acceso, el espacio de nombres es sólo el nombre archivo PST; Por ejemplo `annb.pst`.           | `/dstdir:"ingestiondata/"` <br/> O bien  <br/>  `/dstdir:"ingestiondata/FILESERVER01/PSTs"` <br/> |
    | `/sk:` <br/> |Especifica la clave de la cuenta de almacenamiento que obtuvo en el paso 1. Asegúrese de que rodee el valor de este parámetro con comillas dobles ("").  <br/> | `"yaNIIs9Uy5g25Yoak+LlSHfqVBGOeNwjqtBEBGqRMoidq6/e5k/VPkjOXdDIXJHxHvNoNoFH5NcVUJXHwu9ZxQ=="` <br/> |
    | `/encrypt` <br/> |Este modificador activa BitLocker en la unidad de disco duro. Este parámetro es necesario la primera vez que ejecuta la herramienta WAImportExport.exe.  <br/> La clave de cifrado BitLocker se copia en el archivo de diario y el archivo de registro que se crea si usa el `/logfile:` parámetro. Como se explica anteriormente, se guarda el archivo de diario en la misma carpeta donde se encuentra la herramienta WAImportExport.exe.<br/> | `/encrypt` <br/> |
    | `/logdir:` <br/> |Este parámetro opcional especifica una carpeta para guardar los archivos de registro a. Si no se especifica, los archivos de registro son Guardar en la misma carpeta donde se encuentra la herramienta WAImportExport.exe. Asegúrese de que rodee el valor de este parámetro con comillas dobles ("").  <br/> | `/logdir:"c:\users\admin\desktop\PstImportLogs"` <br/> |
   
    A continuación se muestra un ejemplo de la sintaxis de la herramienta WAImportExport.exe, en el que se usan valores reales para cada parámetro:
    
    ```
    WAImportExport.exe PrepImport /j:PSTHDD1.jrn /t:f /id:driveship1 /srcdir:"\\FILESERVER01\PSTs" /dstdir:"ingestiondata/" /sk:"yaNIIs9Uy5g25Yoak+LlSHfqVBGOeNwjqtBEBGqRMoidq6/e5k/VPkjOXdDIXJHxHvNoNoFH5NcVUJXHwu9ZxQ==" /encrypt /logdir:"c:\users\admin\desktop\PstImportLogs"
    ```

    Después de ejecutar el comando, aparecen mensajes de estado en los que se muestra el progreso de la copia de los archivos PST en la unidad de disco duro. En un mensaje de estado final aparece el número total de archivos copiados correctamente. 
    
4. Ejecute este comando cada vez que ejecute la herramienta WAImportExport.ext para copiar los archivos PST en la misma unidad de disco duro.

    ```
    WAImportExport.exe PrepImport /j:<Name of journal file> /id:<Name of new session> /srcdir:<Location of PST files> /dstdir:<PST file path> 
    ```

    A continuación se muestra un ejemplo de la sintaxis para ejecutar sesiones posteriores y copiar los archivos PST en la misma unidad de disco duro.  

    ```
    WAImportExport.exe PrepImport /j:PSTHDD1.jrn /id:driveship2 /srcdir:"\\FILESERVER01\PSTs\SecondBatch" /dstdir:"ingestiondata/"
    ```

## <a name="step-3-create-the-pst-import-mapping-file"></a>Paso 3: Crear el archivo de asignación de importación de PST

Después de personal del centro de datos de Microsoft carga los archivos PST de la unidad de disco duro para el área de almacenamiento de Azure, el servicio de importación utilizará la información en el archivo de asignación de importación de archivos PST, que es un archivo de valores (CSV) separados por comas, que especifica qué buzones de usuario el PST los archivos se importará a. Va a enviar este archivo CSV en el siguiente paso al crear un trabajo de importación de PST.
  
1. [Descargar una copia del archivo de asignación de importación de PST](https://go.microsoft.com/fwlink/p/?LinkId=544717).
    
2. Abra o guarde el archivo CSV en el equipo local. En el ejemplo siguiente se muestra un archivo de asignación de importaciones de archivos PST completado (que se abre en el Bloc de notas). Es mucho más fácil usar Microsoft Excel para editar el archivo CSV.

    ```
    Workload,FilePath,Name,Mailbox,IsArchive,TargetRootFolder,ContentCodePage,SPFileContainer,SPManifestContainer,SPSiteUrl
    Exchange,FILESERVER01/PSTs,annb.pst,annb@contoso.onmicrosoft.com,FALSE,/,,,,
    Exchange,FILESERVER01/PSTs,annb_archive.pst,annb@contoso.onmicrosoft.com,TRUE,/ImportedPst,,,,
    Exchange,FILESERVER01/PSTs,donh.pst,donh@contoso.onmicrosoft.com,FALSE,/,,,,
    Exchange,FILESERVER01/PSTs,donh_archive.pst,donh@contoso.onmicrosoft.com,TRUE,/ImportedPst,,,,
    Exchange,FILESERVER01/PSTs,pilarp.pst,pilarp@contoso.onmicrosoft.com,FALSE,/,,,,
    Exchange,FILESERVER01/PSTs,pilarp_archive.pst,pilarp@contoso.onmicrosoft.com,TRUE,/ImportedPst,,,,
    Exchange,,tonyk.pst,tonyk@contoso.onmicrosoft.com,FALSE,/,,,,
    Exchange,,tonyk_archive.pst,tonyk@contoso.onmicrosoft.com,TRUE,,,,,
    Exchange,,zrinkam.pst,zrinkam@contoso.onmicrosoft.com,FALSE,/,,,,
    Exchange,,zrinkam_archive.pst,zrinkam@contoso.onmicrosoft.com,TRUE,,,,,
    ```

    La primera fila o la fila de encabezado, del archivo CSV se enumera los parámetros que usará el servicio de PST Import para importar los archivos PST a buzones de usuario. Cada nombre de parámetro viene separada por una coma. Cada fila debajo de la fila de encabezado representa los valores de parámetro para la importación de un archivo PST a un buzón específico. Necesitará una fila para cada archivo PST que se ha copiado a la unidad de disco duro. Asegúrese de reemplazar los datos de marcador de posición en el archivo de asignación con los datos reales.

    > [!NOTE]
    > No cambie nada en la fila de encabezado, ni siquiera los parámetros SharePoint; se ignorarán durante el proceso de importación de PST. 
  
3. Use la información de la tabla siguiente para rellenar el archivo CSV con la información necesaria.
    
    |**Parámetro**|**Descripción**|**Ejemplo**|
    |:-----|:-----|:-----|
    | `Workload` <br/> |Especifica el servicio Office 365 que se va a importar datos. Para importar archivos PST a buzones de usuario, use `Exchange`.<br/> | `Exchange` <br/> |
    | `FilePath` <br/> | Especifica la ubicación de la carpeta en el área de almacenamiento de Azure que archivos PST se copiarán en la unidad de disco duro se envía a Microsoft.  <br/>  Agregar en esta columna en el archivo CSV depende de lo que especificó en el para el `/dstdir:` parámetro en el paso anterior.  <br/>  Si usó `/dstdir:"ingestiondata/"`, a continuación, deje este parámetro en blanco en el archivo CSV.  <br/>  Si ha incluido un nombre de ruta opcional para el valor de la `/dstdir:` parámetro (por ejemplo, `/dstdir:"ingestiondata/FILESERVER01/PSTs"`, a continuación, utilice esa ruta de acceso (sin incluir "ingestiondata") para este parámetro en el archivo CSV. El valor para este parámetro distingue mayúsculas de minúsculas.<br/>  En cualquier caso, *no* incluya "ingestiondata" en el valor de la `FilePath` parámetro. Deje este parámetro en blanco o especificar sólo el nombre de ruta opcional.<br/> > [!IMPORTANT]> El caso para el nombre de ruta de acceso del archivo debe ser el mismo caso que especificó en el `/dstdir:` parámetro en el paso anterior. Por ejemplo, si usó `"ingestiondata/FILESERVER01/PSTs"` para el nombre de la subcarpeta en el paso anterior, pero a continuación, usar `fileserver01/psts` en el `FilePath` parámetro en el archivo CSV, la importación para el archivo PST se producirá un error. Asegúrese de usar el mismo caso en ambas instancias.           |(se deja en blanco)  <br/> O bien  <br/>  `FILESERVER01/PSTs` <br/> |
    | `Name` <br/> |Especifica el nombre del archivo PST que se va a importar al buzón del usuario. El valor para este parámetro distingue mayúsculas de minúsculas.<br/> > [!IMPORTANT]> El caso para el nombre del archivo PST en el archivo CSV debe ser el mismo que el archivo PST que se cargó en la ubicación de almacenamiento de Azure en el paso 2. Por ejemplo, si usa `annb.pst` en el `Name` parámetro en el archivo CSV, pero el nombre del archivo PST real es `AnnB.pst`, se producirá un error en la importación de ese archivo PST. Asegúrese de que el nombre de los archivos PST en el archivo CSV usa el mismo caso que el archivo PST real.           | `annb.pst` <br/> |
    | `Mailbox` <br/> |Especifica la dirección de correo electrónico del buzón al que se va a importar el archivo PST. Tenga en cuenta que no se puede especificar una carpeta pública debido a que el servicio de importación de PST no admite la importación de los archivos PST a las carpetas públicas.<br/> Para importar un archivo PST a un buzón de correo inactivo, es necesario especificar el GUID del buzón de correo para este parámetro. Para obtener este GUID, ejecute el siguiente comando de PowerShell en Exchange Online: ' Get-Mailbox <identity of inactive mailbox> - InactiveMailboxOnly | Guid de FL` <br/> > [!NOTE]> In some cases, you might have multiple mailboxes with the same email address, where one mailbox is an active mailbox and the other mailbox is in a soft-deleted (or inactive) state. In these situations, you have to specify the mailbox GUID to uniquely identify the mailbox to import the PST file to. To obtain this GUID for active mailboxes, run the following PowerShell command:  `Get-Mailbox<identity of active mailbox> | Guid de FL`. To obtain the GUID for soft-deleted (or inactive) mailboxes, run this command:  `Get-Mailbox <identity of soft-deleted or inactive mailbox> - SoftDeletedMailbox | Guid de FL'.           | `annb@contoso.onmicrosoft.com` <br/> O bien  <br/>  `2d7a87fe-d6a2-40cc-8aff-1ebea80d4ae7` <br/> |
    | `IsArchive` <br/> | Especifica si se va a importar o no el archivo PST en el buzón de archivo del usuario. Hay dos opciones:<br/> **FALSE** Importa el archivo PST en el buzón del usuario principal.  <br/> **Es TRUE** Importa el archivo PST al buzón de archivo del usuario. Esto se da por supuesto que el [buzón de archivo del usuario está habilitado](enable-archive-mailboxes.md). Si establece este parámetro en `TRUE` y buzón de archivo del usuario no está habilitado, se producirá un error en la importación de dicho usuario. Tenga en cuenta que si se produce un error en una importación de un usuario (debido a que su archivo no está habilitado y se establece esta propiedad en `TRUE`), los demás usuarios en el trabajo de importación no se verán afectados.<br/>  Si deja en blanco este parámetro, se importa el archivo PST en el buzón del usuario principal.  <br/> **Nota:** Para importar un archivo PST a un buzón de archivo basados en la nube para un usuario cuyo buzón de correo principal es local, sólo tiene que especificar `TRUE` para este parámetro y especificar la dirección de correo electrónico para el buzón del usuario local para el `Mailbox` parámetro.  <br/> | `FALSE` <br/> O bien  <br/>  `TRUE` <br/> |
    | `TargetRootFolder` <br/> | Especifica la carpeta de buzón de correo que se importa el archivo PST a.  <br/>  Si deja en blanco este parámetro, se va a importar el archivo PST en una carpeta nueva con nombre **importado** que se encuentra en el nivel raíz del buzón (el mismo nivel que la carpeta Bandeja de entrada y las otras carpetas de buzón de correo de forma predeterminada).  <br/>  Si especifica `/`, los elementos en el archivo PST se va a importar en directamente a la carpeta de bandeja de entrada del usuario.  <br/>  Si especifica `/<foldername>`, los elementos en el archivo PST se importará a una carpeta denominada * \<foldername\> * . Por ejemplo, si usa `/ImportedPst`, los elementos se importará a una carpeta denominada **ImportedPst**. Esta carpeta se encuentran en el buzón del usuario en el mismo nivel que la carpeta Bandeja de entrada.<br/> |(se deja en blanco)  <br/> O bien  <br/>  `/` <br/> O bien  <br/>  `/ImportedPst` <br/> |
    | `ContentCodePage` <br/> |Este parámetro opcional especifica un valor numérico para la página de códigos que se utilizará para importar los archivos PST en el formato de archivo ANSI. Este parámetro se usa para importar los archivos PST de organizaciones chino, japonés y coreano (CJK) debido a que estos lenguajes normalmente usan un juego de caracteres de doble byte (DBCS) para la codificación de caracteres. Si este parámetro no se usa para importar archivos PST para idiomas que usan DBCS para nombres de carpeta de buzón de correo, los nombres de carpeta a menudo aparecerán dañados después de su importación.<br/> Para obtener una lista de valores admitidos que se usará para este parámetro, vea [Identificadores de la página de código](https://go.microsoft.com/fwlink/p/?LinkId=328514).  <br/> > [!NOTE]> Como previamente indicó, esto es un parámetro opcional y no tiene que incluir en el archivo CSV. O bien, puede incluirlo y deje el valor en blanco para una o varias filas.           |(se deja en blanco)  <br/> O bien  <br/>  `932`(que es el identificador de la página de códigos para ANSI/OEM en japonés)  <br/> |
    | `SPFileContainer` <br/> |Para la importación de archivos PST, deje este parámetro en blanco.   <br/> |No aplicable  <br/> |
    | `SPManifestContainer` <br/> |Para la importación de archivos PST, deje este parámetro en blanco.   <br/> |No aplicable  <br/> |
    | `SPSiteUrl` <br/> |Para la importación de archivos PST, deje este parámetro en blanco.   <br/> |No aplicable  <br/> |

## <a name="step-4-create-a-pst-import-job-in-office-365"></a>Paso 4: crear un trabajo de importación de PST en Office 365

El siguiente paso es crear el trabajo de importación de PST en el servicio de importación en Office 365. Como se explica anteriormente, se enviará el archivo de asignación de importación de PST que creó en el paso 3. Después de crear el nuevo trabajo, el servicio de importación utilizará la información en el archivo de asignación para importar los archivos PST en el buzón de usuario especificado después de los archivos PST se copian de la unidad de disco duro en el área de almacenamiento de Azure y crear e iniciar el trabajo de importación.
  
1. Vaya a [https://protection.office.com](https://protection.office.com) e iniciar sesión con las credenciales para una cuenta de administrador de la organización de Office 365. 
    
2. En el panel izquierdo de la seguridad &amp; centro de cumplimiento, haga clic en **el gobierno de datos** y, a continuación, haga clic en **Importar**.
    
3. En la página **Importar** , haga clic en ![icono Agregar](media/ITPro-EAC-AddIcon.gif) **nuevo trabajo de importación**.
    
    > [!NOTE]
    > Como se mencionó anteriormente, se debe tener asignados los permisos adecuados para tener acceso a la página de **importación** de la seguridad &amp; centro de cumplimiento. 
  
4. Escriba un nombre para el trabajo de importación de PST y, a continuación, haga clic en **siguiente**. Use las letras en minúscula, números, guiones y caracteres de subrayado. No se puede usar las letras en mayúsculas o incluir espacios en el nombre.
    
5. En la página **elija importar el tipo de trabajo** , haga clic en **unidades de disco duro de envío a uno de nuestras ubicaciones físicas** y, a continuación, haga clic en **siguiente**.
    
    ![Haga clic en unidades de disco duro de envío a uno de nuestras ubicaciones físicas para crear una unidad de trabajo de importación de envío](media/1584fdc5-cd4c-4e47-932e-db6c8e07f5f8.png)
  
6. En el paso 6, haga clic en las casillas de verificación **han preparado mis unidades de disco duro y tener acceso a los archivos de diario de unidad es necesario** y **tiene acceso para el archivo de asignación** y, a continuación, haga clic en **siguiente**.
    
    ![Haga clic en las dos casillas de verificación en el paso 6](media/fad43078-ea68-4acd-b2ed-75a800183262.png)
  
7. En la página **Seleccione el archivo de la unidad** , haga clic en **Seleccionar archivo de la unidad**y, a continuación, vaya a la misma carpeta donde se encuentra la herramienta WAImportExport.exe. Se ha copiado el archivo de diario que se creó en el paso 2 para esta carpeta.
    
    ![Haga clic en Seleccionar unidad archivo para enviar el archivo de diario que se creó cuando ejecutó la herramienta de WAImportExport.exe](media/1ea35c04-bd88-4d7e-b7d9-dc390149d94f.png)
  
8. Seleccione el archivo de diario; Por ejemplo, `PSTHDD1.jrn`.
    
    > [!TIP]
    > Cuando se ejecutó la herramienta WAImportExport.exe en el paso 2, se especifica el nombre del archivo de diario de la `/j:` parámetro. 
  
9. Después de que el nombre del archivo unidad aparece bajo **nombre de archivo de unidad**, haga clic en **Validar** para comprobar si el archivo de la unidad para errores. 
    
    ![Haga clic en validar para validar el archivo de la unidad que ha seleccionado](media/4b707f5a-152a-4e74-b9f5-449c88d1fec4.png)
  
    El archivo de unidad tiene que ser validado correctamente para crear un trabajo de importación de PST. Tenga en cuenta que el nombre de archivo se cambia a verde después de que se validan correctamente. Si se produce un error en la validación, haga clic en el vínculo **Ver registro** . Se abre un informe de errores de validación, con un mensaje de error con información acerca de por qué no se pudo el archivo. 
    
    > [!NOTE]
    > Debe agregar y validar un archivo de diario para cada unidad de disco duro que se envían a Microsoft. 
  
10. Después de agregar y validar un archivo de diario para cada unidad de disco duro que se enviarán a Microsoft, haga clic en **siguiente**.
    
11. Haga clic en ![icono Agregar](media/ITPro-EAC-AddIcon.gif) **Seleccionar archivo de asignación** para enviar el archivo de asignación de importación de PST que creó en el paso 3. 
    
    ![Haga clic en el archivo de asignación Select para enviar el archivo CSV que creó para el trabajo de importación](media/d30b1d73-80bb-491e-a642-a21673d06889.png)
  
12. Después del nombre de la CSV archivo aparece bajo **la asignación de nombre de archivo**, haga clic en **Validar** para comprobar si el archivo CSV para errores. 
    
    ![Haga clic en validar para comprobar si el archivo CSV de errores](media/4680999d-5538-4059-b878-2736a5445037.png)
  
    El archivo CSV tiene que ser validado correctamente para crear un trabajo de importación de PST. Tenga en cuenta que el nombre de archivo se cambia a verde después de que se validan correctamente. Si se produce un error en la validación, haga clic en el vínculo **Ver registro** . Se abre un informe de errores de validación, con un mensaje de error para cada fila en el archivo que no se pudo. 
    
13. Después de valida correctamente el archivo de asignación de archivos PST, haga clic en **siguiente**.
    
14. En la página **proporcionar información de contacto** , escriba su información de contacto en los cuadros correspondientes. 
    
    Tenga en cuenta que se muestra la dirección de la ubicación de Microsoft que se va a distribuir las unidades de disco duros a. Esta dirección es generado automáticamente en función de su ubicación de centro de datos de Office 365. Copie esta dirección a un archivo o tomar una captura de pantalla.
    
15. Leer el documento de términos y condiciones, haga clic en la casilla de verificación y, a continuación, haga clic en **Guardar** para enviar el trabajo de importación. 
    
    Cuando el trabajo de importación se ha creado correctamente, se muestra una página de estado que se explica en los pasos de la unidad de proceso de envío.
    
16. En la página **Importar** , haga clic en ![icono de actualización](media/O365-MDM-Policy-RefreshIcon.gif) **Actualizar** para que se muestra la nueva unidad de trabajo de importación de envío en la lista de trabajos de importación. Tenga en cuenta que el estado se establece a la **espera de número de seguimiento**. También puede hacer clic en el trabajo de importación para mostrar la página emergente de estado, que contiene información más detallada sobre el trabajo de importación.
 
## <a name="step-5-ship-the-hard-drive-to-microsoft"></a>Paso 5: enviar la unidad de disco duro a Microsoft

El siguiente paso es enviar la unidad de disco duro a Microsoft y a continuación, proporcione el número de seguimiento para el envío y devolver información de envío para el trabajo de trasvase de registros de la unidad. Después de la unidad es recibida por Microsoft, tardará entre 7 y 10 días laborables para los datos personal del Centro para cargar los archivos PST en el área de almacenamiento de Azure para su organización.
  
> [!NOTE]
> Si no proporciona el número de seguimiento y la información de envío de devolución plazo de 14 días de crear el trabajo de importación, caducará el trabajo de importación. En este caso, tendrá que crear una nueva unidad de trabajo de importación de envío (vea [paso 4: crear un trabajo de importación de PST en Office 365](use-drive-shipping-to-import-pst-files-to-office-365.md#step4)) y volver a enviar el archivo de la unidad y el archivo de asignación de importación de PST. 
  
### <a name="ship-the-hard-drive"></a>Enviar la unidad de disco duro

Tenga en cuenta lo siguiente a la hora de enviar las unidades de disco duro a Microsoft:
  
- No se suministran el adaptador SATA-USB; solo tiene que enviar la unidad de disco duro.
    
- Empaquete la unidad de disco duro correctamente (por ejemplo, use un envoltorio de plástico con burbujas o una bolsa antiestática).
    
- Seleccione la empresa de transporte que desee para enviar la unidad de disco duro a Microsoft.
    
- Envío de la unidad de disco duro a la dirección de la ubicación de Microsoft que se muestra cuando el trabajo de importación que creó en el paso 4. No olvide incluir "Servicio de importación de Office 365" en la dirección de envío.
    
- Después de enviar la unidad de disco duro, asegúrese de anotar el nombre del transportista y el número de seguimiento, que deberá especificar en el siguiente paso.
    
### <a name="enter-the-tracking-number-and-other-shipping-information"></a>Indicar el número de seguimiento y otros datos de envío

Cuando haya enviado la unidad de disco duro a Microsoft, lleve a cabo el procedimiento siguiente en la página Servicio de importación.
  
1. Vaya a [https://protection.office.com](https://protection.office.com) e iniciar sesión con las credenciales para una cuenta de administrador de la organización de Office 365. 
    
2. En el panel izquierdo, haga clic en **el gobierno de datos** y, a continuación, haga clic en **Importar**.
    
3. En la página de **importación** , haga clic en el trabajo para el envío de unidad que se va a escribir el número de seguimiento. 
    
4. En la página de estado emergente, haga clic en **ENTRAR número de seguimiento**.
    
5. Proporcione la siguiente información de envío:
    
1. **Operador de entrega** Escriba el nombre de la compañía de entrega que usa para el envío de la unidad de disco duro a Microsoft. 
    
2. **Número de seguimiento** Escriba el número de seguimiento para el envío de la unidad de disco duro. 
    
3. **Número de cuenta de la compañía devuelto** Escriba el número de cuenta de su organización para el operador que enumeradas en **devolver portadora**. Microsoft utilizar (y cobrar) esta cuenta para enviar su disco duro. Tenga en cuenta que las organizaciones de los Estados Unidos y Europa, debe tener una cuenta con FedEx. Las organizaciones de Asia y el resto del mundo, debe tener una cuenta con DHL.
    
6. Haga clic en **Guardar** para guardar esta información del trabajo de importación. 
    
    En la página **Importar** , haga clic en ![icono de actualización](media/O365-MDM-Policy-RefreshIcon.gif) **Actualizar** para actualizar la información de la unidad de trabajo de importación de envío. Tenga en cuenta que el estado ahora está establecido en **unidades en tránsito**.

## <a name="step-6-filter-data-and-start-the-pst-import-job"></a>Paso 6: Filtrar datos e iniciar el trabajo de importación de PST

Después de la unidad de disco duro es recibida por Microsoft, el estado del trabajo de importación en la página **Importar** de cambiará a **unidades recibido**. Personal del centro de datos utilizará la información en el archivo de diario para cargar los archivos PST en el área de almacenamiento de Azure para su organización. En este momento, el estado cambiará a la **importación en curso**. Como se ha indicado anteriormente, se tardará entre 7 y 10 días de business después de recibir la unidad de disco duro para cargar los archivos PST.
  
Después de que se cargan los archivos PST en Azure, se cambia el estado para **un análisis en curso**. Esto indica que Office 365 es analizar los datos en los archivos PST (de forma segura) para identificar la antigüedad de los elementos y los tipos de mensaje diferentes incluidos en los archivos PST. Cuando se completa el análisis y están listos para importar los datos, se cambia el estado del trabajo de importación de **análisis**completado. En este momento, tiene la opción para importar todos los datos contenidos en los archivos PST o puede recortar los datos que se importan mediante la configuración de filtros que controlan qué datos obtiene importados.
  
1. Vaya a [https://protection.office.com](https://protection.office.com) e iniciar sesión con las credenciales para una cuenta de administrador de la organización de Office 365. 
    
2. En el panel izquierdo, haga clic en **el gobierno de datos** > **importación**.
    
3. En la página **Importar** , haga clic en **listo para importar a Office 365** para el trabajo de importación que creó en el paso 4. 
    
    ![Haga clic en listo para importar a Office 365 junto a la que creó el trabajo de importación](media/5760aac3-300b-4e31-b894-253c42a4b82b.png)
  
    Se muestra un marcha página con información acerca de los archivos PST y otra información sobre el trabajo de importación.
    
4. Haga clic en **importar a Office 365**.
    
5. Se abrirá la página **filtrar los datos** . Contiene toda la información de datos resultante del análisis realizado en los archivos PST por Office 365, incluida información acerca de la antigüedad de los datos de. En este momento, tiene la opción para filtrar los datos que se va a importar o importación todos los datos tal y como está. 
    
    ![Puede recortar los datos en los archivos PST o importar todos de la misma](media/287fc030-99e9-417b-ace7-f64617ea5d4e.png)
  
6. Realice una de las acciones siguientes:
    
    r. para recortar los datos que se importan, haga clic en **Sí, deseo filtrarla antes de importar**.
    
    Para obtener instrucciones detalladas paso a paso acerca del filtrado de los datos en los archivos PST y, a continuación, iniciar el trabajo de importación, vea [filtrar datos al importar archivos PST a Office 365](filter-data-when-importing-pst-files.md).
    
    O bien
    
    b. para importar todos los datos en los archivos PST, haga clic en **No, deseo importarlo todo** y haga clic en **siguiente**.
    
7. Si opta por importar todos los datos, haga clic en **Importar datos** para iniciar el trabajo de importación. 
    
    El estado del trabajo de importación se muestra en la página **Importar** . Haga clic en ![icono de actualización](media/O365-MDM-Policy-RefreshIcon.gif) **Actualizar** para actualizar la información de estado que se muestra en la columna **estado** . Haga clic en el trabajo de importación para mostrar la página emergente de estado, que muestra información de estado acerca de cada archivo PST que se están importando. Cuando se completa la importación y los archivos PST se han importado a buzones de usuario, el estado cambiará a **completado**.

## <a name="view-a-list-of-the-pst-files-uploaded-to-office-365"></a>Ver una lista de los archivos PST que se cargan en Office 365

Puede instalar y usar el Explorador de almacenamiento de información de Microsoft Azure (que es una herramienta gratuita y de código abierto) para ver la lista de los archivos PST que nos estamos cargados (por parte del personal del centro de datos de Microsoft) en el área de almacenamiento de Azure para su organización. Puede hacer esto para comprobar que los archivos PST de las unidades de disco duros que se envía a Microsoft se han cargado correctamente en el área de almacenamiento de Azure.
  
El Explorador de almacenamiento de información de Microsoft Azure está en vista previa.
  
 **Importante:** No puede usar el Explorador de almacenamiento de Azure para cargar o modificar los archivos PST. El único método admitido para la importación de los archivos PST a Office 365 es utilizar AzCopy. Además, no se puede eliminar los archivos PST que han cargado en el blob de Azure. Si se intenta eliminar un archivo PST, recibirá un error acerca de no tener los permisos necesarios. Tenga en cuenta que todos los archivos PST se eliminan automáticamente desde el área de almacenamiento de Azure. Si no hay ningún trabajo de importación en curso y, a continuación, todos los archivos PST en el ** ingestiondata ** contenedor se eliminan 30 días después de que se creó el trabajo de importación más reciente. 
  
Para instalar el Explorador de almacenamiento de Azure y conectarse a su área de almacenamiento de Azure:
  
1. Realice los pasos siguientes para obtener la dirección URL de la firma de acceso compartidos (SAS) para su organización. Esta dirección URL es una combinación de la dirección URL de red para la ubicación de almacenamiento de Azure en la nube de Microsoft para su organización y una clave de SAS. Esta clave proporciona los permisos necesarios para tener acceso a la ubicación de almacenamiento de Azure de su organización.
    
1. Vaya a [https://protection.office.com/](https://protection.office.com/) e iniciar sesión con las credenciales para una cuenta de administrador de la organización de Office 365. 
    
2. En el panel izquierdo de la seguridad &amp; centro de cumplimiento, haga clic en **el gobierno de datos** \> **importación**.
    
3. En la página **Importar** , haga clic en ![icono Agregar](media/ITPro-EAC-AddIcon.gif) **nuevo trabajo de importación**.
    
4. En el Asistente para importación de trabajo, escriba un nombre para el trabajo de importación de PST y, a continuación, haga clic en **siguiente**. Use las letras en minúscula, números, guiones y caracteres de subrayado. No se puede usar las letras en mayúsculas o incluir espacios en el nombre.
    
5. En la página **elija importar el tipo de trabajo** , haga clic en **cargar los datos** y, a continuación, haga clic en **siguiente**.
    
6. En el paso 2, haga clic en **Mostrar la dirección URL de SAS de carga de red**.
    
7. Después de que se muestra la dirección URL, cópiela y guárdelo en un archivo. Asegúrese de copiar la dirección URL completa.
    
    > [!IMPORTANT]
    > Asegúrese de tomar precauciones para proteger la dirección URL de SAS. Esto se puede usar cualquier persona para tener acceso al área de almacenamiento de Azure para su organización. 
  
8. Haga clic en **Cancelar** para cerrar al Asistente para importación de trabajo. 
    
2. Descargue e instale la [herramienta de explorador de almacenamiento de Microsoft Azure](https://go.microsoft.com/fwlink/p/?LinkId=544842).
    
3. Inicie el Explorador de almacenamiento de información de Microsoft Azure, haga clic en **Cuentas de almacenamiento** en el panel izquierdo y, a continuación, haga clic en **Conectar con el almacenamiento de Azure**.
    
    ![Haga clic en cuentas de almacenamiento y, a continuación, haga clic en conectar para almacenamiento de Azure](media/75b80cc3-c336-4f96-ad32-54ac9b96a7af.png)
  
4. Haga clic en **utilizar una cadena de conexión o URI de firma (SAS) de acceso compartido** y haga clic en **siguiente**.
    
5. Haga clic en **usar un URI de SAS**, pegue la dirección URL de SAS que obtuvo en el paso 1 en para en el cuadro bajo **URI**y, a continuación, haga clic en **siguiente**.
    
6. En la página **Resumen de la conexión** , puede revisar la información de conexión y, a continuación, haga clic en **Conectar**.
    
    Se abre el contenedor de **ingestiondata** ; contiene los archivos PST desde el disco duro. El contenedor de **ingestiondata** se encuentra en **Cuentas de almacenamiento** \> **(SAS-Attached Services)** \> **Contenedores de Blob**.
    
    ![El explorador de almacenamiento de Azure muestra una lista de los archivos PST que ha cargado](media/12376fed-13a5-4a09-8fe6-e819e011b334.png)
  
7. Cuando haya terminado con el Explorador de almacenamiento de información de Microsoft Azure, haga clic con el botón **ingestiondata**y, a continuación, haga clic en **Desasociar** a desconectar de su área de almacenamiento de Azure. De lo contrario, recibirá un error la próxima vez que se intenta adjuntar. 
    
    ![Haga clic con el botón derecho en la ingesta y haga clic en Desasociar para desconectar de su área de almacenamiento de Azure](media/1e8e5e95-4215-4ce4-a13d-ab5f826a0510.png)
  

  
## <a name="troubleshooting-tips"></a>Sugerencias para solucionar problemas
<a name="troubleshootingtips"> </a>

- **¿Qué sucede si se produce un error en el trabajo de importación debido a errores en el archivo de asignación de PST Importar CSV?** Si se produce un error en un trabajo de importación debido a errores en el archivo de asignación, no es necesario volver a enviar la unidad de disco duro a Microsoft para crear un nuevo trabajo de importación. Esto es debido a que los archivos PST de la unidad de disco duro que han enviado para el trabajo de importación de trasvase de registros de unidad ya se han cargado en el área de almacenamiento de Azure para su organización. En este caso, debe que corregir los errores en el archivo de asignación PST Importar CSV y, a continuación, crear un nuevo trabajo de importación de "carga de red" y enviar el archivo de asignación de CSV revisado. Para crear e iniciar un nuevo trabajo de importación de carga de red, vea [paso 5: crear un trabajo de importación de PST en Office 365](use-network-upload-to-import-pst-files.md#step-5-create-a-pst-import-job-in-office-365) y [paso 6: filtrar datos e iniciar el trabajo de importación de PST](use-network-upload-to-import-pst-files.md#step-6-filter-data-and-start-the-pst-import-job) en el tema "Carga de red de uso para importar archivos PST a Office 365". 
    
    > [!NOTE]
    > Para ayudar a solucionar problemas del archivo de asignación de CSV de importación de archivos PST, use la herramienta [Explorador de almacenamiento de Azure](#view-a-list-of-the-pst-files-uploaded-to-office-365) para ver la estructura de carpetas en el contenedor **ingestiondata** de los archivos PST desde su unidad de disco duro que se han cargado en el área de almacenamiento de Azure. Errores de asignación de archivo normalmente causados por un valor incorrecto en el parámetro FilePath. Este parámetro especifica la ubicación de un archivo PST en el área de almacenamiento de Azure. Vea la descripción del parámetro FilePath en la tabla en el [paso 3](#step-3-create-the-pst-import-mapping-file). Como se explica anteriormente, se ha especificado la ubicación de los archivos PST en el área de almacenamiento de Azure por la `/dstdir:` parámetro cuando se ejecutó la herramienta WAImportExport.exe en el [paso 2](#step-2-copy-the-pst-files-to-the-hard-drive). 
  

  
## <a name="more-information"></a>Más información

- Unidad de trasvase de registros es una forma eficaz para importar grandes cantidades de datos de mensajería archiving a Office 365 para aprovechar las características de cumplimiento que están disponibles para su organización. Después de importan los datos de archiving a buzones de usuario, se puede:
    
  - Habilitar [buzones de archivo](enable-archive-mailboxes.md) y la [ampliación automática de archivado](enable-unlimited-archiving.md) para ofrecer a los usuarios espacio de almacenamiento de buzones de correo adicionales para los datos. 
    
  - Colocar buzones en [Suspensión por litigio](https://go.microsoft.com/fwlink/?linkid=856286) a conservar los datos. 
    
  - Usar [Herramientas de exhibición de documentos electrónicos](search-for-content.md) de Microsoft para buscar los datos. 
    
  - Aplicar [las directivas de retención de Office 365](retention-policies.md) para controlar cuánto tiempo se retienen los datos y qué acción debe realizar después de que expire el período de retención. 
    
  - Búsqueda del [registro de auditoría de Office 365](search-the-audit-log-in-security-and-compliance.md) para eventos relacionados con estos datos. 
    
  - Importar datos a [buzones de correo inactivos](create-and-manage-inactive-mailboxes.md) para archivar datos con fines de cumplimiento. 
    
  - Proteger su organización contra la [pérdida de datos](data-loss-prevention-policies.md) de información confidencial. 
    
- A continuación se muestra un ejemplo de la clave de la cuenta de almacenamiento seguro y una clave de cifrado de BitLocker. Este ejemplo también contiene la sintaxis del comando WAImportExport.exe que ejecutó para copiar los archivos PST en una unidad de disco duro. Asegúrese de tomar precauciones para protegerlos de la misma manera que protegería las contraseñas u otra información relacionada con la seguridad.
    

    ```
    Secure storage account key: 

    yaNIIs9Uy5g25Yoak+LlSHfqVBGOeNwjqtBEBGqRMoidq6/e5k/VPkjOXdDIXJHxHvNoNoFH5NcVUJXHwu9ZxQ==

    BitLocker encryption key:

    397386-221353-718905-535249-156728-127017-683716-083391

  COMMAND SYNTAX

  First time:

  WAImportExport.exe PrepImport /j:<Name of journal file> /t:<Drive letter> /id:<Name of session> /srcdir:<Location of PST files> /dstdir:<PST file path> /sk:<Storage account key> /encrypt /logdir:<Log file location>

  Subsequent times:

  WAImportExport.exe PrepImport /j:<Name of journal file> /id:<Name of new session> /srcdir:<Location of PST files> /dstdir:<PST file path> 

  EXAMPLES

  First time:

  WAImportExport.exe PrepImport /j:PSTHDD1.jrn /t:f /id:driveship1 /srcdir:"\\FILESERVER1\PSTs" /dstdir:"ingestiondata/" /sk:"yaNIIs9Uy5g25Yoak+LlSHfqVBGOeNwjqtBEBGqRMoidq6/e5k/VPkjOXdDIXJHxHvNoNoFH5NcVUJXHwu9ZxQ==" /encrypt /logdir:"c:\users\admin\desktop\PstImportLogs"

  Subsequent times:

  WAImportExport.exe PrepImport /j:PSTHDD1.jrn /id:driveship2 /srcdir:"\\FILESERVER1\PSTs\SecondBatch" /dstdir:"ingestiondata/"
    ```
   
- Como se explica anteriormente, el servicio Office 365 importación activa la suspensión de retención establecer (durante un tiempo indefinido) después de que se importan los archivos PST en un buzón de correo. Esto significa que la propiedad *RentionHoldEnabled* está establecida en `True` para que no se procesará la directiva de retención asignada al buzón. Esto proporciona a la hora de propietario de buzón de correo para administrar los mensajes recién importadas al impedir que una eliminación o directiva de archivo eliminar o archivar los mensajes antiguos. Estos son algunos pasos que puede seguir para administrar la suspensión de retención: 
    
  - Después de un determinado período de tiempo, puede desactivar la suspensión de retención mediante la ejecución de la `Set-Mailbox -RetentionHoldEnabled $false` comando. Para obtener instrucciones, vea [conservación un buzón de correo en retención](https://go.microsoft.com/fwlink/p/?LinkId=544749).
    
  - Puede configurar la suspensión de retención para que está desactivado en una fecha en el futuro. Para ello, ejecuta el `Set-Mailbox -EndDateForRetentionHold <date>` comando. Por ejemplo, suponiendo que la fecha de hoy es 1 de julio de 2016 y desea que la suspensión de retención desactivada en 30 días, se ejecute el siguiente comando: `Set-Mailbox -EndDateForRetentionHold 8/1/2016`. En este escenario, dejaría la propiedad *RentionHoldEnabled* establecida en *True* . Para obtener más información, consulte [Set-Mailbox](https://go.microsoft.com/fwlink/p/?LinkId=150317).
    
  - Puede cambiar la configuración de la directiva de retención que se asigna al buzón para que no se elimina inmediatamente los elementos más antiguos que se han importado o movidos al buzón de archivo del usuario. Por ejemplo, podría aumentar la antigüedad de retención para una directiva de eliminación o un archivo que se asigna al buzón. En este escenario, debería desactivar la suspensión de retención en el buzón de correo después de cambiar la configuración de la directiva de retención. Para obtener más información, vea [Configurar una directiva de eliminación y de archivo para los buzones de correo en la organización de Office 365](set-up-an-archive-and-deletion-policy-for-mailboxes.md).
    

  

