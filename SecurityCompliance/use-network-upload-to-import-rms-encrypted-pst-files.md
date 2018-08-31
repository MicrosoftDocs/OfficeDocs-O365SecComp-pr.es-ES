---
title: Usar la carga en la red para importar archivos PST con cifrado RMS en Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 5/29/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 84a595b8-cd77-4f66-ac52-57a33ddd4773
description: Obtenga información sobre cómo usar la carga de red para importar los archivos PST de cifrado de RMS a buzones de usuario en Office 365.
ms.openlocfilehash: 6460512e2d6085df684841248dc286d39dbd9d87
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22536812"
---
# <a name="use-network-upload-to-import-rms-encrypted-pst-files-to-office-365"></a>Usar la carga en la red para importar archivos PST con cifrado RMS en Office 365

**En este artículo está dirigido a administradores. ¿Está intentando importar archivos PST en su propio buzón? Consulte el [correo electrónico de importación, contactos y calendario desde un archivo .pst de Outlook](https://go.microsoft.com/fwlink/p/?LinkID=785075)**
   
Uso de la red cargar opción y el servicio Office 365 importar para importar archivos PST a buzones de usuario. Carga de red significa cargar los archivos PST en un área de almacenamiento temporal en la nube de Microsoft. A continuación, el servicio Office 365 importación copia los archivos PST desde el área de almacenamiento para los buzones de usuario de destino. Una nueva característica del servicio de importación permite cifrar los archivos PST antes de que se cargan y se almacenan en la nube de Microsoft. Estos archivos se podrán no cifrados importados a buzones de usuario. 
  
Estos son los pasos necesarios para cifrar e importar archivos PST a buzones de Office 365:
  
[Paso 1: configurar Azure Rights Management para la importación de PST ](#step-1-set-up-azure-rights-management-for-pst-import)

[Paso 2: generar una clave de cifrado para la importación de PST](#step-2-generate-an-encryption-key-for-pst-import)

[Paso 3: Obtener el identificador del inquilino de RMS y licencias de dirección URL](#step-3-obtain-rms-tenant-id-and-licensing-url)

[Paso 4: Descargar las herramientas de importación de PST y copie la dirección URL de SAS](#step-4-download-the-pst-import-tools-and-copy-the-sas-url)

[Paso 5: Cifrar y cargar los archivos PST en Office 365](#step-5-encrypt-and-upload-your-pst-files-to-office-365)

[(Opcional) Paso 6: Ver una lista de los archivos PST cargado a Office 365](#optional-step-6-view-a-list-of-the-pst-files-uploaded-to-office-365)

[Paso 7: Crear el archivo de asignación de importación de PST](#step-7-create-the-pst-import-mapping-file)

[Paso 8: crear un trabajo de importación de PST en Office 365](#step-8-create-a-pst-import-job-in-office-365)
  
> [!IMPORTANT]
> Se debe realizar el paso 1 a 4 de paso sólo una vez para instalar y configurar la organización para cifrar e importar archivos PST a buzones de correo de Office 365. Después de realizar estos pasos, siga el paso 5 al paso 8 cada vez que desee cifrar, cargar e importar un lote de archivos PST. 
  
Para obtener más información sobre cómo importar datos a Office 365, vea [información general de importación de los archivos PST de organización a Office 365](importing-pst-files-to-office-365.md).
  
## <a name="before-you-begin"></a>Antes de empezar

- Se debe asignar la función de importación de exportación de buzones de correo en Exchange en línea para importar archivos PST a buzones de Office 365. De forma predeterminada, este rol no está asignado a ningún grupo de funciones en Exchange Online. Puede agregar la función de exportación de importación de buzón de correo para el grupo de roles de administración de la organización. O bien, puede crear un nuevo grupo de roles, asignar el rol de buzón de correo importar exportar y, a continuación, agregue a usted como un miembro. Para obtener más información, vea el "Agregar un rol a un grupo de roles" o la "crear un grupo de roles" secciones en [Administrar grupos de roles](https://go.microsoft.com/fwlink/p/?LinkId=730688).
    
    Además crear la importación de trabajos en la seguridad de Office 365 &amp; debe ser verdadero centro de cumplimiento, uno de los siguientes:
    
  - Se debe tener asignado el rol de destinatarios de correo en Exchange Online. De forma predeterminada, este rol se asigna a los grupos de funciones de administración de la organización y administración de destinatarios.
    
    O bien
    
  - Debe ser un administrador global de la organización de Office 365.
    
  > [!TIP]
  > Considere la posibilidad de crear un nuevo grupo de funciones en Exchange Online diseñada específicamente para la importación de los archivos PST a Office 365. Para el nivel mínimo de privilegios necesarios para importar los archivos PST, asigne las funciones de importación de exportación de buzones de correo y destinatarios de correo para el nuevo grupo de roles y, a continuación, agregar a miembros. 
  
- Que se necesita para almacenar los archivos PST que desea importar a Office 365 en un servidor de archivos o la carpeta compartida en la organización. En el paso 5, lo ejecutará el ImportTool Office 365, que se va a cifrar y cargar los archivos PST que se almacenan en este servidor de archivo o carpeta a Office 365 comparten.
    
- Este procedimiento implica copiar y guardar una copia de una clave de cifrado, una clave de almacenamiento de información y un número de direcciones URL y las claves de identificación. Esta información se utilizará en el paso 5 para cifrar y cargar los archivos PST. Asegúrese de tomar precauciones para proteger estos simplemente como haría proteger las contraseñas u otra información relacionada con la seguridad. Por ejemplo puede guardarlos en un documento de Microsoft Word protegidos con contraseña o guardarlos en una unidad USB cifrada. Vea la sección [obtener más información](#more-information) para obtener un ejemplo de estas claves, identificadores y direcciones URL. 
    
- Puede importar archivos PST a un buzón de correo inactivo en Office 365. Para ello, que especifica el GUID del buzón de correo inactivo en el `Mailbox` parámetro en el archivo de asignación de importación de PST. Para obtener más información, vea el [paso 7](#step-7-create-the-pst-import-mapping-file) . 
    
- En una implementación híbrida de Exchange, puede importar archivos PST en un buzón de archivo basados en la nube para un usuario cuyo buzón de correo principal es local. Para ello, hacer lo siguiente en el archivo de asignación de importación de PST:
    
  - Especifique la dirección de correo electrónico para el buzón del usuario local en el `Mailbox` parámetro. 
    
  - Especificar el valor **TRUE** en el `IsArchive` parámetro. 
    
    Para obtener más información, vea el [paso 7](#step-7-create-the-pst-import-mapping-file) . 
    
- Una vez que se importan los archivos PST en un buzón de Office 365, la suspensión de retención establecer para el buzón de correo está activada para una duración indefinida. Esto significa que no se procesará la directiva de retención asignada al buzón hasta que se desactiva la suspensión de retención o establecer una fecha para desactivar la suspensión. ¿Por qué hacemos esto? Si los mensajes que se importa a un buzón de correo son anteriores, se podría eliminar permanentemente (purga) debido a que ha caducado su período de retención en función de la configuración de retención configurada para el buzón de correo. Colocar el buzón de correo en suspensión de retención, le dará el tiempo de propietario del buzón de correo para administrar estos mensajes recién importadas o ceder mucho tiempo para cambiar la configuración de retención para el buzón de correo. Vea la sección [obtener más información](#more-information) para obtener sugerencias acerca de cómo administrar la suspensión de retención. 
    
- Si no necesita cifrar los archivos PST antes de cargarlas en Office 365, vea [Use network cargar para importar archivos PST a Office 365](use-network-upload-to-import-pst-files.md).
    
- Para las preguntas más frecuentes sobre el uso de carga de red para importar archivos PST a Office 365, consulte [preguntas más frecuentes acerca de cómo importar archivos PST a Office 365](faqimporting-pst-files-to-office-365.md).
  
## <a name="step-1-set-up-azure-rights-management-for-pst-import"></a>Paso 1: configurar Azure Rights Management para la importación de PST 

Importación de PST usa la funcionalidad de cifrado proporcionada por el servicio de Azure Rights Management (RMS Azure) en Office 365. Esto le permite para cifrar los archivos PST antes de cargarlas a Office 365. 
  
Configuración de RMS de Azure para la importación de PST consta de tres pasos:
  
- [Activación de RMS de Azure](#activate-azure-rms)
    
- [Configuración de RMS en Exchange Online](#configure-rms-in-exchange-online)
    
- [Instalar al cliente de RMS de Active Directory](#install-the-active-directory-rms-client)
    
### <a name="activating-azure-rms"></a>Activación de RMS de Azure

RMS Azure está deshabilitada de forma predeterminada, pero usted u otro administrador de la organización puede activar. Siga las instrucciones que aparecen en la [Activación de Azure Rights Management](https://docs.microsoft.com/azure/information-protection/deploy-use/activate-service) para instalar y activar Azure DRM.
  
### <a name="configuring-rms-in-exchange-online"></a>Configuración de RMS en Exchange Online

Después de que ha activado el servicio de administración de derechos, el siguiente paso es configurar Information Rights Management (IRM) en Exchange Online para usar RMS de Azure. Para obtener más información, vea [Configurar IRM para usar Azure Rights Management](https://go.microsoft.com/fwlink/p/?LinkId=394816).
  
1. [Conectarse a Exchange Online mediante PowerShell remoto](https://go.microsoft.com/fwlink/p/?LinkId=396554 ).
    
2. Ejecute el comando siguiente para establecer la dirección URL de uso compartido de claves de RMS.
    
    ```
    Set-IRMConfiguration -RMSOnlineKeySharingLocation <RMS key sharing location>
    ```

    Use la siguiente tabla para determinar la ubicación correcta de uso compartido de claves de RMS para la ubicación de su organización.
    
    |**Ubicación**|**Ubicación de uso compartido de claves de RMS**|
    |:-----|:-----|
    |Norteamérica  <br/> | `https://sp-rms.na.aadrm.com/TenantManagement/ServicePartner.svc` <br/> |
    |Unión Europea  <br/> | `https://sp-rms.eu.aadrm.com/TenantManagement/ServicePartner.svc` <br/> |
    |Asia  <br/> | `https://sp-rms.ap.aadrm.com/TenantManagement/ServicePartner.svc` <br/> |
    |Sudamérica  <br/> | `https://sp-rms.sa.aadrm.com/TenantManagement/ServicePartner.svc` <br/> |
    |Office 365 Administración Pública (nube de la comunidad de administración pública)  <br/> | `https://sp-rms.govus.aadrm.com/TenantManagement/ServicePartner.svc`<sup>1</sup> <br/> |
   
    > [!NOTE]
    > <sup>1</sup> Solo deben utilizar esta ubicación de uso compartido de claves de RMS los clientes que han adquirido SKU de Office 365 Administración Pública (nube de la comunidad de administración pública). 
  
    Por ejemplo, este comando configura la clave de RMS Online ubicación de uso compartido en Exchange Online para un cliente que se encuentra en Norteamérica.
    
    ```
    Set-IRMConfiguration -RMSOnlineKeySharingLocation "https://sp-rms.na.aadrm.com/TenantManagement/ServicePartner.svc"
    ```

3. Ejecute el siguiente comando para importar un dominio de publicación de confianza (TPD) desde RMS Online a la organización de Office 365. 
    
    ```
    Import-RMSTrustedPublishingDomain -RMSOnline -Name "RMS Online"
    ```

    Un TPD contiene la configuración necesaria para usar las características de RMS en su organización, incluido el cifrado de archivos PST.  
    
4. Ejecute el siguiente comando para habilitar IRM para la organización de Office 365.
    
    ```
    Set-IRMConfiguration -InternalLicensingEnabled $true
    ```

### <a name="installing-the-active-directory-rms-client"></a>Instalar al cliente de RMS de Active Directory

El último paso de esta sección es para descargar al cliente de Rights Management Services (RMS) 2.1. Este software ayuda a proteger el acceso a Azure RMS y protege la información que fluye a través de las aplicaciones que usan Azure RMS instalar el cliente de RMS en el mismo equipo que se usará para cifrar y cargar los archivos PST en el paso 5. 
  
1. Descargar el [cliente de servicios de administración de derechos 2.1](https://www.microsoft.com/en-us/download/details.aspx?id=38396).
    
2. Ejecute el asistente del cliente de Rights Management Service de Active Directory 2.1 para instalar el cliente.

## <a name="step-2-generate-an-encryption-key-for-pst-import"></a>Paso 2: generar una clave de cifrado para la importación de PST

Después de configurar RMS de Azure, el siguiente paso es generar una clave de cifrado (denominada una clave simétrica) que se usará para cifrar los archivos PST que se cargan a Office 365. Que hará agregando el servicio de importación de PST como un servicio de entidad de seguridad en Active Directory de Azure. Adición de esta aplicación como una entidad de seguridad de servicio permite al servicio de PST Import autenticar directamente con Azure Active Directory cuando se carga, cifra los archivos PST a la ubicación de almacenamiento de Azure en el paso 5.
  
1. Inicie el módulo Azure Active Directory para Windows PowerShell.
    
2. Ejecute el comando siguiente para conectarse al servicio de Microsoft Online.
    
    ```
    Connect-MsolService
    ```

3. Escriba las credenciales para una cuenta de administrador de la organización de Office 365 y, a continuación, haga clic en **Aceptar**.
    
4. Ejecute el comando siguiente para generar una clave de cifrado (llamada clave simétrica). Debe hacerlo creando una nueva entidad de cifrado de archivos PST.
    
    ```
    New-MsolServicePrincipal -DisplayName PstEncryptionPrincipal
    ```

    El sistema muestra la clave simétrica y las propiedades de la nueva entidad de cifrado de archivos PST.
    
    ![Copiar y guardar la clave simétrica que se muestra](media/0003fdea-dace-41d2-b49d-f5c98c6230ca.png)
  
5. Copie la clave simétrica en un archivo de texto o de Word. Como se ha indicado anteriormente, asegúrese de tomar precauciones para proteger este archivo. Dado que es la única vez que se muestra la clave simétrica, tal vez debería tomar una captura de pantalla de esta ventana y guardarla en el mismo archivo.  
    
    > [!IMPORTANT]
    > Una vez creada la entidad de cifrado de archivos PST, no podrá recuperar la clave simétrica con el cmdlet **Get-MsolServicePrincipal**. Por eso es importante guardar la clave. 
  
Mantener Azure Active Directory módulo para Windows PowerShell abierta y conectada al servicio de Microsoft Online. Debe ejecutar un comando en esta ventana en el paso siguiente.

## <a name="step-3-obtain-rms-tenant-id-and-licensing-url"></a>Paso 3: Obtener el identificador del inquilino de RMS y licencias de dirección URL

El siguiente paso es obtener al inquilino identificador y licencias de dirección URL de ubicación para el servicio de RMS de Azure para su organización. Copie y guarde esta información en el mismo archivo que contiene la clave simétrica del paso 2. El identificador y la dirección URL se usará en el paso 5 para cifrar los archivos PST.
  
1. En el Azure módulo Active Directory para Windows PowerShell (que está conectado al servicio de Microsoft Online), ejecute el siguiente comando para conectar con el servicio de RMS de Azure en la organización de Office 365.
    
    ```
    Connect-AadrmService 
    ```

2. Escriba las credenciales para una cuenta de administrador de la organización de Office 365 y, a continuación, haga clic en **Aceptar**.
    
3. Ejecute el siguiente comando para mostrar el identificador de inquilino para el servicio de RMS de Azure en la organización de Office 365.
    
    ```
    Get-AadrmConfiguration | FL BPOSId
    ```

    Copie y guarde el valor para el `BPOSId` (propiedad). 
    
4. Ejecute el siguiente comando para mostrar la ubicación de licencias para el servicio de RMS de Azure.
    
    ```
    Get-AadrmConfiguration | FL LicensingIntranetDistributionPointUrl
    ```

    Copie y guarde el valor para el `LicensingIntranetDistributionPointUrl` (propiedad). 

## <a name="step-4-download-the-pst-import-tools-and-copy-the-sas-url"></a>Paso 4: Descargar las herramientas de importación de PST y copie la dirección URL de SAS

Ahora que ha configurado RMS de Azure y obtener los identificadores necesarios para cifrar los archivos PST, el siguiente paso es descargar e instalar las herramientas que se ejecutará en el paso 5 para cifrar y los archivos PST de carga para Office 365. Estas herramientas son la herramienta de AzCopy de Azure y la herramienta de cifrado de datos de Office 365. También podrá copiar la dirección URL de SAS para su organización. Esta dirección URL es una combinación de la dirección URL de red para la ubicación de almacenamiento de Azure en la nube de Microsoft para su organización y una clave de firma de acceso compartidos (SAS). Esta clave proporciona los permisos necesarios para cargar los archivos PST en su ubicación de almacenamiento de Azure. Guárdelo en el mismo archivo que ha copiado el resto de información para en el paso 2 y paso 3. Como se mencionó anteriormente, tome precauciones para proteger la dirección URL de SAS. 
  
> [!IMPORTANT]
> Se debe usar Azure AzCopy versión 5.0 para cargar correctamente los archivos PST en la ubicación de almacenamiento de Azure. Las versiones más recientes de la herramienta de AzCopy no son compatibles para la importación de los archivos PST a Office 365. Asegúrese de descargar la herramienta de AzCopy desde la página **cargar archivos a través de la red** siguiendo los procedimientos descritos en este paso. 
  
1. Vaya a [https://protection.office.com](https://protection.office.com).
    
2. Inicie sesión en Office 365 con las credenciales para una cuenta de administrador de la organización de Office 365.
    
3. En el panel izquierdo, haga clic en **el gobierno de datos** y, a continuación, haga clic en **Importar**.
    
4. En la página **Importar**, haga clic en **Ir al servicio de importación**.
    
5. En la página **Importar datos a Office 365** , haga clic en **nuevo trabajo** ![icono Agregar](media/ITPro-EAC-AddIcon.gif)y, a continuación, haga clic en **mensajes de correo electrónico de carga (archivos PST)**.
    
6. En la página **cargar archivos a través de la red** , en el paso 2, haga clic en **Mostrar la dirección URL de SAS de carga de red**.
    
7. Después de que se muestra la dirección URL, cópiela y vuelva a guardarla en el archivo donde guardó las otras claves. Asegúrese de copiar la dirección URL completa. 
    
8. En el paso 3, haga clic en **Descargar la herramienta de AzCopy de Azure** para descargar e instalar la herramienta de AzCopy de Azure. 
    
9. En la ventana emergente, haga clic en **Ejecutar** para instalar la herramienta AzCopy de Azure. 
    
    > [!IMPORTANT]
    > Asegúrese de instalar la herramienta de AzCopy de Azure en la ubicación predeterminada, que es `%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy` en un equipo que ejecuta Windows de 64 bits. Eso es porque cuando se ejecuta el O365ImportTool.exe en el paso 5, busca la herramienta AzCopy en esta ubicación. 
  
10. Después de instalar la herramienta de AzCopy de Azure, haga clic en **Descargar la herramienta de importación y el cifrado de datos de Office 365**.
    
11. En la ventana emergente, haga clic en **Guardar** \> **Guardar como** para guardar el archivo O365ImportTool.zip en una carpeta en el equipo local. 
    
12. Extraiga el archivo O365ImportTool.zip.
    
13. Haga clic en **Cancelar** para cerrar la página **cargar archivos a través de la red** . 
 
## <a name="step-5-encrypt-and-upload-your-pst-files-to-office-365"></a>Paso 5: Cifrar y cargar los archivos PST en Office 365

Después de haber completado el paso 1 a través del paso 4, estará listo usar la herramienta de O365ImportTool.exe para cifrar y cargar los archivos PST a Office 365. Esta herramienta cifra los archivos PST y, a continuación, carga y las almacena en una ubicación de almacenamiento de Azure en la nube de Microsoft. Para completar este paso, los archivos PST tienen que estar ubicada en un recurso compartido de archivos o un servidor de archivos en su organización. Esto se conoce como el directorio de origen en el procedimiento siguiente. Cada vez que se ejecuta la herramienta O365ImportTool.exe, aquí puede especificar un directorio de origen diferentes. 
  
1. Abra el símbolo del sistema del equipo local.
    
2. Vaya al directorio en el que instaló la herramienta O365ImportTool.exe en el paso 4.
    
3. Ejecute el comando siguiente para cifrar y cargar los archivos PST a Office 365.
    
    ```
    O365ImportTool.exe /srcdir:<Location of PST files> /protect-rmsserver:<RMS licensing location> /protect-tenantid:<BPOSId> /protect-key:<Symmetric key> /transfer:upload /upload-dest:<Network upload URL> /upload-destSAS:<SAS key>
    ```

    En la tabla siguiente se describen los parámetros y los valores requeridos. Tenga en cuenta que la información de los pasos anteriores se usa en los valores de estos parámetros.
    
    |**Parámetro**|**Descripción**|**Ejemplo**|
    |:-----|:-----|:-----|
    | `/srcdir:` <br/> |Especifica el directorio de origen en la organización que contiene los archivos PST que se cargará a Office 365.  <br/> | `/srcdir:\\FILESERVER01\PSTs` <br/> |
    | `/protect-rmsserver:` <br/> |Especifica la ubicación de licencias para el servicio de RMS de Azure. Use el valor de la `LicensingIntranetDistributionPointUrl` propiedad que obtuvo en el paso 3. Asegúrese de que rodee el valor de este parámetro con comillas dobles ("")<br/> | `/protect-rmsserver:"https://afcbd8ec-cb2b-4a1a-8246-0b4bc22d1978.rms.na.aadrm.com/_wmcs/licensing"` <br/> |
    | `/protect-tenantid:` <br/> |Especifica la identidad de la organización de RMS de Azure. Use el valor de la `BPOSId` propiedad que obtuvo en el paso 3.<br/> | `/protect-tenantid:42745b33-2a5c-4726-8a2a-ca43caa0f74b` <br/> |
    | `/protect-key:` <br/> |Especifica la clave simétrica que obtuvo en el paso 2. Asegúrese de que rodee el valor de este parámetro con comillas dobles ("").  <br/> | `/protect-key:"l+R+Umc5RGmSBh1oW+DoyMxm/h5h2JJXFcNOFiNp867="` <br/> |
    | `/transfer:` <br/> |Especifica si va a carga los archivos PST a través de la red o enviarlos en una unidad de disco duro. El valor `upload` indica que va a cargar los archivos a través de la red. El valor `drive` indica que vaya a distribuir los archivos pst en una unidad de disco duro.<br/> | `/transfer:upload` <br/> |
    | `/upload-dest:` <br/> |Especifica el destino en Office 365 donde se cargará los archivos PST en; Ésta es la ubicación de almacenamiento de Azure para su organización. El valor para este parámetro consta de la dirección URL de carga de red desde la dirección URL de asociaciones de seguridad que se copió en el paso 4. Asegúrese de que rodee el valor de este parámetro con comillas dobles ("").<br/><br/> **Sugerencia:** (Opcional) Puede especificar una subcarpeta en la ubicación de almacenamiento de Azure para cargar los archivos PST cifrados a. Para ello, mediante la adición de una ubicación de la subcarpeta (después de "ingestiondata") en la dirección URL de carga de red. El primer ejemplo no especifica una subcarpeta; Esto significa que los archivos PST se cargará en la raíz (denominada *ingestiondata* ) de la ubicación de almacenamiento de Azure. El segundo ejemplo carga los archivos PST en una subcarpeta (denominada *EncryptedPSTs* ) en la ubicación de almacenamiento de Azure.           | `/upload-dest:"https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata"` <br/> O bien  <br/>  `/upload-dest:"https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata/EncryptedPSTs"` <br/> |
    | `/upload-destSAS:` <br/> |Especifica la clave de asociaciones de seguridad de su organización. El valor para este parámetro se compone de la clave de asociaciones de seguridad de la dirección URL de asociaciones de seguridad que se copió en el paso 4. Tenga en cuenta que el primer carácter de la clave SAS es un signo de interrogación ("?"). Asegúrese de que rodee el valor de este parámetro con comillas dobles ("").  <br/> | `/upload-destSAS:"?sv=2012-02-12&amp;se=9999-12-31T23%3A59%3A59Z&amp;sr=c&amp;si=IngestionSasForAzCopy201601121920498117&amp;sig=Vt5S4hVzlzMcBkuH8bH711atBffdrOS72TlV1mNdORg%3D"` <br/> |
    | `/recurse` <br/> |Este modificador opcional especifica el modo de recursiva para que la herramienta O365ImportTool.exe copiará archivos pst que se encuentran en las subcarpetas en el directorio de origen que se especifica mediante el `/srcdir:` parámetro.  <br/><br/> **Nota:** Si se incluye este modificador, los archivos PST en subcarpetas tendrán una ruta de acceso de archivo diferente en la ubicación de almacenamiento de Azure después de cargarlas. Debe especificar la ruta de acceso exacta del archivo en el archivo CSV que cree en el paso 7.           | `/recurse` <br/> |
   
    A continuación se muestra un ejemplo de la sintaxis de la herramienta O365ImportTool.exe, en el que se usan valores reales para cada parámetro:
    
    ```
    O365ImportTool.exe /srcdir:\\FILESERVER01\PSTs /protect-rmsserver:"https://afcbd8ec-cb2b-4a1a-8246-0b4bc22d1978.rms.na.aadrm.com/_wmcs/licensing" /protect-tenantid:42745b33-2a5c-4726-8a2a-ca43caa0f74b  /protect-key:"l+R+Umc5RGmSBh1oW+DoyMxm/h5h2JJXFcNOFiNp867=" /transfer:upload /upload-dest:"https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata" /upload-destSAS:"?sv=2012-02-12&amp;se=9999-12-31T23%3A59%3A59Z&amp;sr=c&amp;si=IngestionSasForAzCopy201601121920498117&amp;sig=Vt5S4hVzlzMcBkuH8bH711atBffdrOS72TlV1mNdORg%3D"
    ```

    Después de ejecutar el comando, aparecen mensajes de estado en los que se muestra el progreso del cifrado y la carga de los archivos PST. En un mensaje de estado final aparece el número total de archivos cifrados y cargados correctamente.  
    
    > [!TIP]
    > Después de que se ejecute el comando O365ImportTool.exe correctamente y compruebe que todos los parámetros son correctos, guardar una copia de la sintaxis de línea de comandos para el mismo archivo (protegida) donde copió la información obtenida en los pasos anteriores. A continuación, puede copiar y pegar este comando en un símbolo del sistema cada vez que se desea ejecutar la herramienta O365ImportTool.exe para cifrar y cargar los archivos PST a Office 365. Los únicos valores es posible que deba cambiar son las que para la `/srcdir:` y `/upload-dest:` parámetros. 
  
## <a name="optional-step-6-view-a-list-of-the-pst-files-uploaded-to-office-365"></a>(Opcional) Paso 6: Ver una lista de los archivos PST cargado a Office 365

Como un paso opcional, puede instalar y usar el Explorador de almacenamiento de información de Microsoft Azure (que es una herramienta gratuita y de código abierto) para ver la lista de los archivos PST que han cargado en el blob de Azure. Hay tres buenas razones para hacerlo:
  
- Compruebe que los archivos PST desde el servidor de archivos de la organización o la carpeta compartida se han cargado correctamente en el blob de Azure.

- Compruebe que se cifran los archivos PST. Los archivos PST cifrados tienen un `.pfile` extensión que se anexa al nombre del archivo PST; Por ejemplo, `pilarp.pst.pfile`.
    
- Compruebe el nombre de archivo (y la ruta de acceso de la subcarpeta si ha incluido uno) para cada archivo PST cargado en el blob de Azure. Esto es realmente útil cuando se está creando el PST de archivo en el siguiente paso de asignación debido a que es necesario especificar la ruta de acceso de carpeta y el nombre de archivo para cada archivo PST. Comprobar estos nombres puede ayudar a reducir posibles errores en el archivo de asignación de PST.
    
El Explorador de almacenamiento de información de Microsoft Azure está en vista previa. 
  
 > [!IMPORTANT]
>  No puede usar el Explorador de almacenamiento de Azure para cargar o modificar los archivos PST. El único método admitido para la importación de los archivos PST a Office 365 es utilizar AzCopy. Además, no se puede eliminar los archivos PST que han cargado en el blob de Azure. Si se intenta eliminar un archivo PST, recibirá un error acerca de no tener los permisos necesarios. Tenga en cuenta que todos los archivos PST se eliminan automáticamente desde el área de almacenamiento de Azure. Si no hay ningún trabajo de importación en curso, a continuación, todos los archivos PST en el contenedor de **ingestiondata** se elimina 30 días después de que se creó el trabajo de importación más reciente. 
  
Para instalar el Explorador de almacenamiento de Azure y conectarse a su área de almacenamiento de Azure:
  
1. Descargue e instale la [herramienta de explorador de almacenamiento de Microsoft Azure](https://go.microsoft.com/fwlink/p/?LinkId=544842).
    
2. Inicie el Explorador de almacenamiento de información de Microsoft Azure, haga clic en **Cuentas de almacenamiento** en el panel izquierdo y, a continuación, haga clic en **Conectar con el almacenamiento de Azure**. 
    
    ![Haga clic en cuentas de almacenamiento y, a continuación, haga clic en conectar para almacenamiento de Azure](media/75b80cc3-c336-4f96-ad32-54ac9b96a7af.png)
  
3. En el cuadro de **Conectar con el almacenamiento de Azure**, pegue la dirección URL de SAS que obtuvo en el paso 4 y, a continuación, haga clic en **siguiente**. 
    
    ![Pegue la dirección URL de SAS en el cuadro en la página Conectar con el almacenamiento de Azure](media/5d034128-e087-48e1-9ebc-4c9fa262d5b7.png)
  
4. En la página **Resumen de la conexión** , puede revisar la información de conexión y, a continuación, haga clic en **Conectar**. 
    
5. En **Cuentas de almacenamiento**, expanda el nodo **(Servicio SAS)** y, a continuación, expanda el nodo de **Contenedores de Blob** . 
    
6. Haga clic en **ingestiondata**y, a continuación, haga clic en **Abrir Editor de contenedor de Blob**.
    
    ![Haga clic con el botón derecho en ingestiondata y, después, haga clic en Abrir editor de contenedores de blobs.](media/f50eee30-9202-4efc-904a-2895a0bc388d.png)
  
    Se muestra el área de almacenamiento de Azure, con una lista de los archivos PST que cargan en el paso 5.
    
    ![El explorador de almacenamiento de Azure muestra una lista de los archivos PST que ha cargado](media/a448ae43-e744-4153-8304-22b59e93883c.png)
  
7. Cuando haya terminado con el Explorador de almacenamiento de información de Microsoft Azure, haga clic con el botón **ingestiondata**y, a continuación, haga clic en **Desasociar** a desconectar de su área de almacenamiento de Azure. De lo contrario, recibirá un error la próxima vez que se intenta adjuntar. 
    
    ![Haga clic con el botón derecho en la ingesta y haga clic en Desasociar para desconectar de su área de almacenamiento de Azure](media/1e8e5e95-4215-4ce4-a13d-ab5f826a0510.png)
  
## <a name="step-7-create-the-pst-import-mapping-file"></a>Paso 7: Crear el archivo de asignación de importación de PST

Tras han cifran los archivos PST y cargados en la ubicación de almacenamiento de Azure para su organización de Office 365, el siguiente paso es crear una coma separados archivo valor (CSV) que especifica qué buzones de usuario se importará a los archivos PST. Va a enviar este archivo CSV en el siguiente paso al crear un trabajo de importación de PST.
  
1. [Descargar una copia del archivo de asignación de importación de PST](https://go.microsoft.com/fwlink/p/?LinkId=544717). 
    
2. Abra o guarde el archivo CSV en el equipo local. En el ejemplo siguiente se muestra un archivo de asignación de importaciones de archivos PST completado (que se abre en el Bloc de notas). Es mucho más fácil usar Microsoft Excel para editar el archivo CSV.
    
    ```
    Workload,FilePath,Name,Mailbox,IsArchive,TargetRootFolder,ContentCodePage,SPFileContainer,SPManifestContainer,SPSiteUrl
    Exchange,,annb.pst.pfile,annb@contoso.onmicrosoft.com,FALSE,/,,,,
    Exchange,,annb_archive.pst.pfile,annb@contoso.onmicrosoft.com,TRUE,/ImportedPst,,,,
    Exchange,,donh.pst.pfile,donh@contoso.onmicrosoft.com,FALSE,/,,,,
    Exchange,,donh_archive.pst.pfile,donh@contoso.onmicrosoft.com,TRUE,/ImportedPst,,,,
    Exchange,EncryptedPSTs,pilarp.pst.pfile,pilarp@contoso.onmicrosoft.com,FALSE,,,,,
    Exchange,EncryptedPSTs,pilarp_archive.pst.pfile,pilarp@contoso.onmicrosoft.com,TRUE,/ImportedPst,,,,
    Exchange,EncryptedPSTs,tonyk.pst.pfile,tonyk@contoso.onmicrosoft.com,FALSE,,,,,
    Exchange,EncryptedPSTs,tonyk_archive.pst.pfile,tonyk@contoso.onmicrosoft.com,TRUE,/ImportedPst,,,,
    Exchange,EncryptedPSTs,zrinkam.pst.pfile,zrinkam@contoso.onmicrosoft.com,FALSE,,,,,
    Exchange,EncryptedPSTs,zrinkam_archive.pst.pfile,zrinkam@contoso.onmicrosoft.com,TRUE,/ImportedPst,,,,
    ```

    La primera fila o la fila de encabezado, del archivo CSV se enumera los parámetros que usará el servicio de PST Import para importar los archivos PST a buzones de usuario. Cada nombre de parámetro viene separada por una coma. Cada fila debajo de la fila de encabezado representa los valores de parámetro para la importación de un archivo PST a un buzón específico. Necesitará una fila para cada archivo PST que desea importar a un buzón de usuario. Asegúrese de reemplazar los datos de marcador de posición en el archivo de asignación con los datos reales.
    
    > [!NOTE]
    > No cambie nada en la fila de encabezado, ni siquiera los parámetros SharePoint; se ignorarán durante el proceso de importación de PST. 
  
3. Use la información de la tabla siguiente para rellenar el archivo CSV con la información necesaria.
    
    |**Parámetro**|**Descripción**|**Ejemplo**|
    |:-----|:-----|:-----|
    | `Workload` <br/> |Especifica el servicio Office 365 que se va a importar datos. Para importar archivos PST a buzones de usuario, use `Exchange`.<br/> | `Exchange` <br/> |
    | `FilePath` <br/> |Especifica la ubicación de la carpeta en la ubicación de almacenamiento de Azure que cargan los archivos PST en el paso 5.  <br/>  Si no ha incluido un nombre de la subcarpeta opcional en la dirección URL de red en el `/upload-dest:` parámetro en el paso 5, deje este parámetro en blanco en el archivo CSV. Si ha incluido un nombre de la subcarpeta, especifique en este parámetro. El valor para este parámetro distingue mayúsculas de minúsculas. En cualquier caso, *no* incluya "ingestiondata" en el valor de la `FilePath` parámetro.<br/> <br/>**Importante:** El caso para el nombre de ruta de acceso del archivo debe ser el mismo caso que usa si ha incluido un nombre de la subcarpeta opcional de la dirección URL de SAS en el `/upload-dest:` parámetro en el paso 5. Por ejemplo, si usó `EncryptedPSTs` para la subcarpeta el nombre en el paso 5 y, a continuación, usar `encryptedpsts` en el `FilePath` parámetro en el archivo CSV, la importación para el archivo PST se producirá un error. Asegúrese de usar el mismo caso en ambas instancias.           |(se deja en blanco)  <br/> O bien  <br/>  `EncryptedPSTs` <br/> |
    | `Name` <br/> |Especifica el nombre del archivo PST que se va a importar al buzón del usuario. El valor para este parámetro distingue mayúsculas de minúsculas. Debido a que se cifran los archivos PST que se cargan en la ubicación de almacenamiento de Azure, un `.pfile` extensión se agrega al nombre del archivo PST. Debe agregar el `.pfile` los archivos de extensión en el nombre de los archivos PST en el archivo CSV.<br/><br/> **Importante:** El caso para el nombre del archivo PST en el archivo CSV debe ser el mismo que el archivo PST que se cargó en la ubicación de almacenamiento de Azure en el paso 5. Por ejemplo, si usa `annb.pst.pfile` en el `Name` parámetro en el archivo CSV, pero el nombre del archivo PST real es `AnnB.pst`, se producirá un error en la importación de ese archivo PST. Asegúrese de que el nombre de los archivos PST en el archivo CSV usa el mismo caso que el archivo PST real.           | `annb.pst.pfile` <br/> |
    | `Mailbox` <br/> |Especifica la dirección de correo electrónico del buzón en el que se importará el archivo PST.   <br/> Para importar un archivo PST a un buzón de correo inactivo, es necesario especificar el GUID del buzón de correo para este parámetro. Para obtener este GUID, ejecute el siguiente comando de PowerShell en Exchange Online: ' Get-Mailbox - InactiveMailboxOnly<identity of inactive mailbox> | Guid de FL` <br/><br/> **Note:** In some cases, you might have multiple mailboxes with the same email address, where one mailbox is an active mailbox and the other mailbox is in a soft-deleted (or inactive) state. In these situations, you have specify the mailbox GUID to uniquely identify the mailbox to import the PST file to. To obtain this GUID for active mailboxes, run the following PowerShell command:  `Get-Mailbox -<identity of active mailbox> | Guid de FL`. To obtain the GUID for soft-deleted (or inactive) mailboxes, run this command  `Get-Mailbox - <identity of soft-deleted or inactive mailbox> - SoftDeletedMailbox | FL Guid'           | `annb@contoso.onmicrosoft.com` <br/> O bien  <br/>  `2d7a87fe-d6a2-40cc-8aff-1ebea80d4ae7` <br/> |
    | `IsArchive` <br/> | Especifica si se va a importar o no el archivo PST en el buzón de archivo del usuario. Hay dos opciones:<br/> **FALSE** Importa el archivo PST en el buzón del usuario principal.  <br/> **Es TRUE** Importa el archivo PST al buzón de archivo del usuario.  <br/>  Si deja en blanco este parámetro, se importa el archivo PST en el buzón del usuario principal.  <br/><br/> **Nota:** Para importar un archivo PST a un buzón de archivo basados en la nube para un usuario cuyo buzón de correo principal es local, especifique **TRUE** para este parámetro y especificar la dirección de correo electrónico para el buzón del usuario local para el `Mailbox` parámetro.           | `FALSE` <br/> O bien  <br/>  `TRUE` <br/> |
    | `TargetRootFolder` <br/> | Especifica la carpeta de buzón de correo que se importa el archivo PST a.  <br/>  Si deja en blanco este parámetro, se va a importar el archivo PST en una carpeta nueva con nombre **importado** que se encuentra en el nivel raíz del buzón (el mismo nivel que la carpeta Bandeja de entrada y las otras carpetas de buzón de correo de forma predeterminada).  <br/>  Si especifica `/`, los elementos en el archivo PST se va a importar en directamente a la carpeta de bandeja de entrada del usuario.  <br/>  Si especifica `/<foldername>`, se va a importar elementos en el archivo PST en una subcarpeta denominada * \<foldername\> * . Por ejemplo, si usó `/ImportedPst`, se importará los elementos en una subcarpeta denominada **ImportedPst**. Esta subcarpeta se encuentran en la carpeta de bandeja de entrada del usuario.<br/><br/> **Sugerencia:** Tenga en cuenta que ejecuta unos lotes de prueba para experimentar con este parámetro para que pueda determinar la mejor ubicación de carpeta para importar archivos de archivos pst a.           |(se deja en blanco)  <br/> O bien  <br/>  `/` <br/> O bien  <br/>  `/ImportedPst` <br/> |
    | `ContentCodePage` <br/> |Este parámetro opcional especifica un valor numérico para la página de códigos que se utilizará para importar los archivos PST en el formato de archivo ANSI. Este parámetro se usa para importar los archivos PST de organizaciones chino, japonés y coreano (CJK) debido a que estos lenguajes normalmente usan un juego de caracteres de doble byte (DBCS) para la codificación de caracteres. Si este parámetro no se usa para importar archivos PST para idiomas que usan DBCS para nombres de carpeta de buzón de correo, los nombres de carpeta a menudo aparecerán dañados después de su importación. Para obtener una lista de valores admitidos que se usará para este parámetro, vea [Identificadores de la página de código](https://go.microsoft.com/fwlink/p/?LinkId=328514).<br/><br/> **Nota:** Como ya ha indicado, éste es un parámetro opcional y no tiene que incluir en el archivo CSV. O bien, puede incluirlo y deje el valor en blanco para una o varias filas.           |(se deja en blanco)  <br/> O bien  <br/>  `932`(que es el identificador de la página de códigos para ANSI/OEM en japonés)  <br/> |
    | `SPFileContainer` <br/> |Para la importación de archivos PST, deje este parámetro en blanco.   <br/> |No aplicable  <br/> |
    | `SPManifestContainer` <br/> |Para la importación de archivos PST, deje este parámetro en blanco.   <br/> |No aplicable  <br/> |
    | `SPSiteUrl` <br/> |Para la importación de archivos PST, deje este parámetro en blanco.   <br/> |No aplicable  <br/> |
  
## <a name="step-8-create-a-pst-import-job-in-office-365"></a>Paso 8: crear un trabajo de importación de PST en Office 365

El último paso es crear el trabajo de importación de PST en el servicio de importación en Office 365. Como se explica anteriormente, se enviará el archivo de asignación de importación de PST que creó en el paso 7. Después de crear el nuevo trabajo, el servicio de importación utilizará la información en el archivo de asignación para Naciones Unidas-cifrar e importar los archivos PST (que ha cargado en Office 365 en el paso 5) para el buzón del usuario especificado. 
  
1. Vaya a [https://protection.office.com](https://protection.office.com).
    
2. Inicie sesión en Office 365 con las credenciales para una cuenta de administrador de la organización de Office 365.
    
3. En el panel izquierdo, haga clic en **el gobierno de datos** y, a continuación, haga clic en **Importar**.
    
4. En la página **Importar**, haga clic en **Ir al servicio de importación**.
    
5. En la página **Importar datos a Office 365** , haga clic en **nuevo trabajo**![icono Agregar](media/ITPro-EAC-AddIcon.gif)y, a continuación, haga clic en **mensajes de correo electrónico de carga (archivos PST)**.
    
6. En la página **Cargar archivos a través de la red**, marque las casillas **Terminé de cargar mis archivos** y **Tengo acceso al archivo de asignación** y haga clic en **Siguiente**.  
    
7. Escriba un nombre para el trabajo de importación de PST y haga clic en **Siguiente**.
    
8. Haga clic en **Agregar** ![icono Agregar](media/ITPro-EAC-AddIcon.gif) para seleccionar el archivo de asignación de PST que creó en el paso 7. 
    
9. Cuando el nombre del archivo CSV aparezca en la lista, selecciónelo y haga clic en **Validar** para comprobar si hay errores en el archivo CSV.  
    
    > [!NOTE]
    > Explica como anterior, cuando se cifran los archivos PST, un `.pfile` extensión se anexa al nombre del archivo PST. Debe agregar el `.pfile` los archivos de extensión en el nombre de los archivos PST en el archivo CSV. Si no lo hace, se producirá un error en la validación del archivo CSV. 
  
    El archivo CSV debe estar validado correctamente para poder crear un trabajo de importación de PST. Si se produce un error en la validación, haga clic en el vínculo **No válido** de la columna **Estado**. Se abrirá una copia del archivo de asignación de importaciones de PST, con un mensaje de error para todas las filas del error en el que se produjo el error. 
    
10. Cuando el archivo de asignación de importaciones de PST se haya validado correctamente, lea el documento de términos y condiciones y marque la casilla.
    
11. Haga clic en **Finalizar** para enviar el trabajo. 
    
    El trabajo se muestra en la lista de trabajos de importación de PST en la página **Importar datos a Office 365** . 
    
12. Seleccione el trabajo y haga clic en **Actualizar**![icono de actualización](media/O365-MDM-Policy-RefreshIcon.gif) para actualizar la información de estado que se muestra en el panel de detalles. 
    
13. En el panel de detalles, haga clic en **Ver detalles** para obtener el último estado del trabajo seleccionado. 
 
## <a name="more-information"></a>Más información

- ¿Por qué importar archivos PST a Office 365?
    
  - Es una buena forma de migrar correo electrónico de su organización a Office 365.
    
  - Ayuda a satisfacer las necesidades de cumplimiento de la organización, ya que le permite:
    
  - Habilitar buzones de archivo para proporcionar a los usuarios espacio de almacenamiento adicional en el buzón.
    
  - Colocar los buzones en espera para conservar el contenido.
    
  - Usar las herramientas de exhibición de documentos electrónicos de Microsoft para buscar contenido en los buzones.
    
  - Usar directivas de retención para controlar el tiempo durante el que se conserva el contenido de los buzones.
    
  - Busque en el registro de auditoría de Office 365 para eventos relacionados con el buzón de correo.
    
  - Ayuda a proteger contra la pérdida de datos. Los archivos PST que se importan a buzones de correo de Office 365 heredan las características de alta disponibilidad de Exchange Online, en lugar de almacenar los datos en el equipo del usuario.
    
  - Los datos están disponibles para el usuario en todos los dispositivos, ya que se almacenan en la nube.
    
- Este es un ejemplo de las claves, los identificadores y las direcciones URL que se obtienen en los pasos 2, 3 y 4. En este ejemplo se también contiene la sintaxis para el comando que se ejecuta en la herramienta O365ImportTool.exe para cifrar y los archivos PST de carga para Office 365. Asegúrese de tomar precauciones para proteger estos simplemente como haría proteger las contraseñas u otra información relacionada con la seguridad.
    
  ```
  Symmetric key: l+R+Umc5RGmSBh1oW+DoyMxm/h5h2JJXFcNOFiNp867=

  BPOSId: 42745b33-2a5c-4726-8a2a-ca43caa0f74b

  LicensingIntranetDistributionPointUrl (RMS licensing location): https://afcbd8ec-cb2b-4a1a-8246-0b4bc22d1978.rms.na.aadrm.com/_wmcs/licensing
  
  SAS URL: https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata?sv=2012-02-12&amp;se=9999-12-31T23%3A59%3A59Z&amp;sr=c&amp;si=IngestionSasForAzCopy201601121920498117&amp;sig=Vt5S4hVzlzMcBkuH8bH711atBffdrOS72TlV1mNdORg%3D
  
  O365ImportTool.exe /srcdir:<Location of PST files> /protect-rmsserver:<RMS licensing location> /protect-tenantid:<BPOSId> /protect-key:<Symmetric key> /transfer:upload /upload-dest:<Network upload URL from the SAS URL> /upload-destSAS:<SAS key from the SAS URL>
  
  EXAMPLES
  
  This example uploads PST files to the root of the Azure storage location:

  O365ImportTool.exe /srcdir:\\FILESERVER01\PSTs /protect-rmsserver:"https://afcbd8ec-cb2b-4a1a-8246-0b4bc22d1978.rms.na.aadrm.com/_wmcs/licensing" /protect-tenantid:42745b33-2a5c-4726-8a2a-ca43caa0f74b /protect-ownerid:45beb445-4d06-47df-8e61-6ca1a88a080e /protect-key:"l+R+Umc5RGmSBh1oW+DoyMxm/h5h2JJXFcNOFiNp867=" /transfer:upload /upload-dest:"https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata" /upload-destSAS:"?sv=2012-02-12&amp;se=9999-12-31T23%3A59%3A59Z&amp;sr=c&amp;si=IngestionSasForAzCopy201601121920498117&amp;sig=Vt5S4hVzlzMcBkuH8bH711atBffdrOS72TlV1mNdORg%3D"
  
  This example uploads PST files to a subfolder named EncryptedPSTs  in the Azure storage location:
  
  O365ImportTool.exe /srcdir:\\FILESERVER01\PSTs /protect-rmsserver:"https://afcbd8ec-cb2b-4a1a-8246-0b4bc22d1978.rms.na.aadrm.com/_wmcs/licensing" /protect-tenantid:42745b33-2a5c-4726-8a2a-ca43caa0f74b /protect-ownerid:45beb445-4d06-47df-8e61-6ca1a88a080e /protect-key:"l+R+Umc5RGmSBh1oW+DoyMxm/h5h2JJXFcNOFiNp867=" /transfer:upload /upload-dest:"https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata/EncryptedPSTs" /upload-destSAS:"?sv=2012-02-12&amp;se=9999-12-31T23%3A59%3A59Z&amp;sr=c&amp;si=IngestionSasForAzCopy201601121920498117&amp;sig=Vt5S4hVzlzMcBkuH8bH711atBffdrOS72TlV1mNdORg%3D"
  ```

- Como se explica anteriormente, el servicio Office 365 importación activa la suspensión de retención establecer (durante un tiempo indefinido) después de que se importan los archivos PST en un buzón de correo. Esto significa que la propiedad *RentionHoldEnabled* está establecida en `True` para que no se procesará la directiva de retención asignada al buzón. Esto proporciona a la hora de propietario de buzón de correo para administrar los mensajes recién importadas al impedir que una eliminación o directiva de archivo eliminar o archivar los mensajes antiguos. Estos son algunos pasos que puede seguir para administrar la suspensión de retención: 
    
  - Después de un determinado período de tiempo, puede desactivar la suspensión de retención mediante la ejecución de la `Set-Mailbox -RetentionHoldEnabled $false` comando. Para obtener instrucciones, vea [conservación un buzón de correo en retención](https://go.microsoft.com/fwlink/p/?LinkId=544749).
    
  - Puede configurar la suspensión de retención para que está desactivado en una fecha en el futuro. Para ello, ejecuta el `Set-Mailbox -EndDateForRetentionHold <date>` comando. Por ejemplo, suponiendo que la fecha de hoy es 1 de julio de 2016 y desea que la suspensión de retención desactivada en 30 días, se ejecute el siguiente comando: `Set-Mailbox -EndDateForRetentionHold 8/1/2016`. En este escenario, dejaría la propiedad *RentionHoldEnabled* establecida en `True`. Para obtener más información, consulte [Set-Mailbox](https://go.microsoft.com/fwlink/p/?LinkId=150317).
    
  - Puede cambiar la configuración de la directiva de retención que se asigna al buzón para que no se elimina inmediatamente los elementos más antiguos que se han importado o movidos al buzón de archivo del usuario. Por ejemplo, podría aumentar la antigüedad de retención para una directiva de eliminación o un archivo que se asigna al buzón. En este escenario, debería desactivar la suspensión de retención en el buzón de correo después de cambiar la configuración de la directiva de retención. Para obtener más información, vea [Configurar una directiva de eliminación y de archivo para los buzones de correo en la organización de Office 365](set-up-an-archive-and-deletion-policy-for-mailboxes.md).
