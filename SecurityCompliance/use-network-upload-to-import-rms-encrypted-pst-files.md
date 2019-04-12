---
title: Usar la carga en la red para importar archivos PST con cifrado RMS en Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 5/29/2018
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 84a595b8-cd77-4f66-ac52-57a33ddd4773
description: Obtenga información sobre cómo usar la carga de red para importar archivos PST cifrados con RMS en buzones de usuario en Office 365.
ms.openlocfilehash: 46f77f3fe173da23e08284884bb85c69ab53f710
ms.sourcegitcommit: 6c9340e4eb221bf81472ff3f1ae25ae21aaf5297
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/11/2019
ms.locfileid: "31814161"
---
# <a name="use-network-upload-to-import-rms-encrypted-pst-files-to-office-365"></a>Usar la carga en la red para importar archivos PST con cifrado RMS en Office 365

**Este artículo está destinado a los administradores. ¿Está intentando importar archivos PST a su propio buzón? Consulte [importar el correo electrónico, los contactos y el calendario desde un archivo. pst de Outlook](https://go.microsoft.com/fwlink/p/?LinkID=785075)**
   
Use la opción carga de red y el servicio de importación de Office 365 para importar archivos PST a los buzones de usuario. Carga de red significa que se cargan los archivos PST en un área de almacenamiento temporal en la nube de Microsoft. A continuación, el servicio de importación de Office 365 copia los archivos PST del área de almacenamiento en los buzones de usuario de destino. Una nueva característica del servicio de importación le permite cifrar los archivos PST antes de cargarlos y almacenarlos en la nube de Microsoft. Estos archivos se descifrarán al importarlos a los buzones de usuario. 
  
Estos son los pasos necesarios para cifrar e importar los archivos PST a los buzones de correo de Office 365:
  
[Paso 1: configurar Azure Rights Management para la importación de PST](#step-1-set-up-azure-rights-management-for-pst-import)

[Paso 2: generar una clave de cifrado para la importación de PST](#step-2-generate-an-encryption-key-for-pst-import)

[Paso 3: obtener el identificador de inquilino de RMS y la dirección URL de licencias](#step-3-obtain-rms-tenant-id-and-licensing-url)

[Paso 4: descargar las herramientas de importación de PST y copiar la dirección URL de SAS](#step-4-download-the-pst-import-tools-and-copy-the-sas-url)

[Paso 5: cifrar y cargar los archivos PST a Office 365](#step-5-encrypt-and-upload-your-pst-files-to-office-365)

[Opcional Paso 6: ver una lista de los archivos PST cargados en Office 365](#optional-step-6-view-a-list-of-the-pst-files-uploaded-to-office-365)

[Paso 7: crear el archivo de asignación de importaciones de PST](#step-7-create-the-pst-import-mapping-file)

[Paso 8: crear un trabajo de importación de PST en Office 365](#step-8-create-a-pst-import-job-in-office-365)
  
> [!IMPORTANT]
> Debe realizar los pasos del 1 al 4 sólo una vez para configurar y configurar la organización para cifrar e importar archivos PST a los buzones de correo de Office 365. Después de realizar estos pasos, siga los pasos 5 a 8 cada vez que desee cifrar, cargar e importar un lote de archivos PST. 
  
Para obtener más información acerca de cómo importar datos a Office 365, vea [información general sobre la importación de archivos PST de la organización a office 365](importing-pst-files-to-office-365.md).
  
## <a name="before-you-begin"></a>Antes de empezar

- Debe tener asignado el rol importación y exportación de buzones de correo en Exchange Online para importar archivos PST a los buzones de correo de Office 365. De forma predeterminada, este rol no está asignado a ningún grupo de roles en Exchange Online. You can add the Mailbox Import Export role to the Organization Management role group. Or you can create a new role group, assign the Mailbox Import Export role, and then add yourself as a member. Para obtener más información, vea las secciones "agregar un rol a un grupo de roles" o "crear un grupo de roles" en [Manage role Groups](https://go.microsoft.com/fwlink/p/?LinkId=730688).
    
    Además, para crear trabajos de importación en el centro de seguridad & cumplimiento, debe cumplirse una de las siguientes condiciones:
    
  - Debe tener asignado el rol destinatarios de correo en Exchange Online. By default, this role is assigned to the Organization Management and Recipient Management roles groups.
    
    O bien
    
  - Debe ser administrador global de la organización de Office 365.
    
  > [!TIP]
  > Considere la posibilidad de crear un nuevo grupo de roles en Exchange online que esté destinado específicamente a importar archivos PST a Office 365. Para el nivel mínimo de privilegios necesarios para importar archivos PST, asigne los roles Mailbox Import Export y mail Recipients al nuevo grupo de roles y, a continuación, agregue members. 
  
- Debe almacenar los archivos PST que desea importar a Office 365 en un servidor de archivos o una carpeta compartida de la organización. En el paso 5, ejecutará el ImportTool de Office 365, que cifrará y cargará los archivos PST almacenados en este servidor de archivos o carpeta compartida en Office 365.
    
- Este procedimiento implica copiar y guardar una copia de una clave de cifrado, una clave de almacenamiento y un número de direcciones URL y de claves de identificación. Esta información se usará en el paso 5 para cifrar y cargar los archivos PST. Asegúrese de tomar precauciones para protegerlos de la misma manera que protegería las contraseñas u otra información relacionada con la seguridad. Por ejemplo, puede guardarlos en un documento de Microsoft Word protegido por contraseña o en una unidad USB cifrada. Consulte la sección [Más información](#more-information) para ver un ejemplo de las claves, los identificadores y las direcciones URL. 
    
- Puede importar archivos PST a un buzón inactivo en Office 365. Para ello, especifique el GUID del buzón inactivo en el `Mailbox` parámetro del archivo de asignación de importaCIONES de PST. Consulte el [paso 7](#step-7-create-the-pst-import-mapping-file) para obtener más información. 
    
- En una implementación híbrida de Exchange, puede importar archivos PST a un buzón de archivo basado en la nube para un usuario cuyo buzón principal es local. Para ello, realice lo siguiente en el archivo de asignación de importaciones de PST:
    
  - Especifique la dirección de correo electrónico del buzón local del usuario en el `Mailbox` parámetro. 
    
  - Especifique el valor **true** en el `IsArchive` parámetro. 
    
    Consulte el [paso 7](#step-7-create-the-pst-import-mapping-file) para obtener más información. 
    
- Una vez que los archivos PST se importan a un buzón de correo de Office 365, la configuración de espera de retención del buzón de correo se activa durante un período de tiempo indefinido. Esto significa que la Directiva de retención asignada al buzón no se procesará hasta que desactive la suspensión de la retención o establezca una fecha para desactivar la retención. ¿Por qué hacemos esto? Si los mensajes importados a un buzón de correo son viejos, podrían eliminarse de forma permanente (purgarse) porque el período de retención ha expirado según la configuración de retención configurada para el buzón. Al colocar el buzón en suspensión de retención, el propietario del buzón podrá administrar estos mensajes recién importados o le dará tiempo para cambiar la configuración de retención del buzón. Consulte la sección [más información](#more-information) para obtener sugerencias sobre cómo administrar la suspensión de la retención. 
    
- Si no necesita cifrar los archivos PST antes de cargarlos en Office 365, vea [usar la carga en la red para importar archivos PST a office 365](use-network-upload-to-import-pst-files.md).
    
- Para conocer las preguntas más frecuentes sobre el uso de la carga de red para importar archivos PST a Office 365, vea [preguntas más frecuentes sobre la importación de archivos PST a office 365](faqimporting-pst-files-to-office-365.md).
  
## <a name="step-1-set-up-azure-rights-management-for-pst-import"></a>Paso 1: configurar Azure Rights Management para la importación de PST 

La importación de PST usa la funcionalidad de cifrado proporcionada por el servicio Azure Rights Management (Azure RMS) en Office 365. Esto le permite cifrar los archivos PST antes de cargarlos a Office 365. 
  
La configuración de Azure RMS para la importación de PST consta de tres pasos:
  
- [Activación de Azure RMS](#activating-azure-rms)
    
- [Configuración de RMS en Exchange Online](#configuring-rms-in-exchange-online)
    
- [Instalación del cliente RMS de Active Directory](#installing-the-active-directory-rms-client)
    
### <a name="activating-azure-rms"></a>Activación de Azure RMS

Azure RMS está deshabilitado de forma predeterminada, pero es posible que usted u otro administrador de su organización lo haya activado. Siga las instrucciones para [Activar Azure Rights Management](https://docs.microsoft.com/azure/information-protection/deploy-use/activate-service) para instalar y activar DRM de Azure.
  
### <a name="configuring-rms-in-exchange-online"></a>Configuración de RMS en Exchange Online

Una vez que haya activado el servicio Rights Management, el siguiente paso consiste en configurar Information Rights Management (IRM) en Exchange Online para usar Azure RMS. Para obtener más información, vea [configurar IRM para usar Azure Rights Management](https://go.microsoft.com/fwlink/p/?LinkId=394816).
  
1. [Conéctese a Exchange online mediante PowerShell remoto](https://go.microsoft.com/fwlink/p/?LinkId=396554 ).
    
2. Ejecute el comando siguiente para establecer la dirección URL de uso compartido de claves de RMS.
    
    ```
    Set-IRMConfiguration -RMSOnlineKeySharingLocation <RMS key sharing location>
    ```

    Use la siguiente tabla para determinar la ubicación correcta de uso compartido de claves de RMS para la ubicación de su organización.
    
    |**Location**|**Ubicación de uso compartido de claves de RMS**|
    |:-----|:-----|
    |Norteamérica  <br/> | `https://sp-rms.na.aadrm.com/TenantManagement/ServicePartner.svc` <br/> |
    |Unión Europea  <br/> | `https://sp-rms.eu.aadrm.com/TenantManagement/ServicePartner.svc` <br/> |
    |Asia  <br/> | `https://sp-rms.ap.aadrm.com/TenantManagement/ServicePartner.svc` <br/> |
    |Sudamérica  <br/> | `https://sp-rms.sa.aadrm.com/TenantManagement/ServicePartner.svc` <br/> |
    |Office 365 Administración Pública (nube de la comunidad de administración pública)  <br/> | `https://sp-rms.govus.aadrm.com/TenantManagement/ServicePartner.svc`<sup>1</sup> <br/> |
   
    > [!NOTE]
    > <sup>1</sup> Solo deben utilizar esta ubicación de uso compartido de claves de RMS los clientes que han adquirido SKU de Office 365 Administración Pública (nube de la comunidad de administración pública). 
  
    Por ejemplo, este comando configura la ubicación de uso compartido de claves de RMS online en Exchange Online para un cliente ubicado en Norteamérica.
    
    ```
    Set-IRMConfiguration -RMSOnlineKeySharingLocation "https://sp-rms.na.aadrm.com/TenantManagement/ServicePartner.svc"
    ```

3. Ejecute el siguiente comando para importar un dominio de publicación de confianza (TPD) desde RMS online a su organización de Office 365. 
    
    ```
    Import-RMSTrustedPublishingDomain -RMSOnline -Name "RMS Online"
    ```

    Un TPD contiene la configuración necesaria para usar las características de RMS en su organización, incluido el cifrado de archivos PST.  
    
4. Ejecute el siguiente comando para habilitar IRM en su organización de Office 365.
    
    ```
    Set-IRMConfiguration -InternalLicensingEnabled $true
    ```

### <a name="installing-the-active-directory-rms-client"></a>Instalación del cliente RMS de Active Directory

El último paso de esta sección consiste en descargar el cliente de Rights Management Services (RMS), versión 2.1. Este software ayuda a proteger el acceso a Azure RMS y protege la información que fluye a través de aplicaciones que usan Azure RMS. Instale el cliente de RMS en el mismo equipo que usará para cifrar y cargar los archivos PST en el paso 5. 
  
1. Descargue el [cliente de Rights Management Service 2,1](https://www.microsoft.com/en-us/download/details.aspx?id=38396).
    
2. Ejecute el asistente del cliente de Rights Management Service de Active Directory 2.1 para instalar el cliente.

## <a name="step-2-generate-an-encryption-key-for-pst-import"></a>Paso 2: generar una clave de cifrado para la importación de PST

Una vez que haya configurado Azure RMS, el siguiente paso consiste en generar una clave de cifrado (denominada clave simétrica) que se usará para cifrar los archivos PST que se cargan en Office 365. Para hacerlo, deberá agregar el servicio de importación de PST como entidad de servicio en Azure Active Directory. Agregar esta aplicación como una entidad de servicio permitirá que el servicio de importación de PST se autentique directamente con Azure Active Directory cuando cargue los archivos PST cifrados en la ubicación de almacenamiento de Azure en el paso 5.
  
1. Inicie el módulo de Azure Active Directory para Windows PowerShell.
    
2. Ejecute el comando siguiente para conectarse al servicio de Microsoft Online.
    
    ```
    Connect-MsolService
    ```

3. Escriba las credenciales de una cuenta de administrador en la organización de Office 365 y, a continuación, haga clic en **Aceptar**.
    
4. Ejecute el comando siguiente para generar una clave de cifrado (llamada clave simétrica). Debe hacerlo creando una nueva entidad de cifrado de archivos PST.
    
    ```
    New-MsolServicePrincipal -DisplayName PstEncryptionPrincipal
    ```

    El sistema muestra la clave simétrica y las propiedades de la nueva entidad de cifrado de archivos PST.
    
    ![Copiar y guardar la clave simétrica que se muestra](media/0003fdea-dace-41d2-b49d-f5c98c6230ca.png)
  
5. Copie la clave simétrica en un archivo de texto o de Word. Como se ha indicado anteriormente, asegúrese de tomar precauciones para proteger este archivo. Dado que es la única vez que se muestra la clave simétrica, tal vez debería tomar una captura de pantalla de esta ventana y guardarla en el mismo archivo.  
    
    > [!IMPORTANT]
    > Una vez creada la entidad de cifrado de archivos PST, no podrá recuperar la clave simétrica con el cmdlet **Get-MsolServicePrincipal**. Por eso es importante guardar la clave. 
  
Mantenga el módulo de Azure Active Directory para Windows PowerShell abierto y conectado al servicio de Microsoft online. En el siguiente paso ejecutará un comando en esta ventana.

## <a name="step-3-obtain-rms-tenant-id-and-licensing-url"></a>Paso 3: obtener el identificador de inquilino de RMS y la dirección URL de licencias

El siguiente paso es obtener el identificador de inquilino y la dirección URL de la ubicación de licencias para el servicio de Azure RMS de su organización. Copie y guarde esta información en el mismo archivo que contiene la clave simétrica del paso 2. El identificador y la dirección URL se usarán en el paso 5 para cifrar los archivos PST.
  
1. En el módulo Azure Active Directory para Windows PowerShell (que está conectado al servicio Microsoft online), ejecute el siguiente comando para conectarse al servicio de Azure RMS en su organización de Office 365.
    
    ```
    Connect-AadrmService 
    ```

2. Escriba las credenciales de una cuenta de administrador de su organización de Office 365 y, a continuación, haga clic en **Aceptar**.
    
3. Ejecute el siguiente comando para mostrar el identificador de inquilino del servicio de Azure RMS en la organización de Office 365.
    
    ```
    Get-AadrmConfiguration | FL BPOSId
    ```

    Copie y guarde el valor de la `BPOSId` propiedad. 
    
4. Ejecute el siguiente comando para mostrar la ubicación de la licencia del servicio Azure RMS.
    
    ```
    Get-AadrmConfiguration | FL LicensingIntranetDistributionPointUrl
    ```

    Copie y guarde el valor de la `LicensingIntranetDistributionPointUrl` propiedad. 

## <a name="step-4-download-the-pst-import-tools-and-copy-the-sas-url"></a>Paso 4: descargar las herramientas de importación de PST y copiar la dirección URL de SAS

Ahora que ha configurado Azure RMS y ha obtenido los identificadores necesarios para cifrar los archivos PST, el siguiente paso consiste en descargar e instalar las herramientas que se ejecutarán en el paso 5 para cifrar y cargar los archivos PST a Office 365. Estas herramientas son la herramienta AzCopy de Azure y la herramienta de cifrado de datos de Office 365. También copiará la dirección URL de SAS de su organización. Esta dirección URL es una combinación de la dirección URL de red para la ubicación de almacenamiento de Azure en la nube de Microsoft para su organización y una clave de firma de acceso compartido (SAS). Esta clave le proporciona los permisos necesarios para cargar archivos PST en su ubicación de almacenamiento de Azure. Guárdelo en el mismo archivo en el que copió la otra información en el paso 2 y en el paso 3. Como se mencionó anteriormente, tome precauciones para proteger la URL de SAS. 
  
> [!IMPORTANT]
> Tiene que usar Azure AzCopy versión 5,0 para cargar los archivos PST correctamente en la ubicación de almacenamiento de Azure. Las versiones más recientes de la herramienta AzCopy no se admiten para importar archivos PST a Office 365. Asegúrese de descargar la herramienta AzCopy de la página **cargar archivos a través de la red** siguiendo los procedimientos de este paso. 
  
1. Vaya a [https://protection.office.com](https://protection.office.com).
    
2. Inicie sesión en Office 365 con las credenciales de una cuenta de administrador de su organización de Office 365.
    
3. En el panel izquierdo, haga clic en **gobierno de datos** y, a continuación, haga clic en **importar**.
    
4. En la página **Importar**, haga clic en **Ir al servicio de importación**.
    
5. en la página **importar datos a Office 365** , haga clic en **nuevo** ![icono](media/ITPro-EAC-AddIcon.gif)agregar trabajo y, a continuación, haga clic en **cargar mensajes de correo electrónico (archivos PST)**.
    
6. En la página **cargar archivos a través de la red** , en el paso 2, haga clic en **Mostrar la dirección URL de carga de red SAS**.
    
7. Una vez mostrada la dirección URL, cópiela y guárdela en el archivo donde guardó las demás claves. Asegúrese de copiar toda la dirección URL. 
    
8. En el paso 3, haga clic en **descargar la herramienta azcopy** de Azure para descargar e instalar la herramienta Azcopy de Azure. 
    
9. En la ventana emergente, haga clic en **Ejecutar** para instalar la herramienta AzCopy de Azure. 
    
    > [!IMPORTANT]
    > Asegúrese de instalar la herramienta AzCopy de Azure en la ubicación predeterminada, que se `%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy` encuentra en un equipo que ejecuta Windows de 64 bits. Esto se debe a que cuando ejecuta O365ImportTool. exe en el paso 5, busca la herramienta AzCopy en esta ubicación. 
  
10. Una vez instalada la herramienta AzCopy de Azure, haga clic en **descargar la herramienta de importación y cifrado de datos de Office 365**.
    
11. En la ventana emergente, haga clic en **Guardar** \> y **Guardar como** para guardar el archivo O365ImportTool. zip en una carpeta del equipo local. 
    
12. Extraiga el archivo O365ImportTool.zip.
    
13. Haga clic en **Cancelar** para cerrar la página **cargar archivos a través de la red** . 
 
## <a name="step-5-encrypt-and-upload-your-pst-files-to-office-365"></a>Paso 5: cifrar y cargar los archivos PST a Office 365

Una vez completado el paso 1 hasta el paso 4, está listo para usar la herramienta O365ImportTool. exe para cifrar y cargar los archivos PST a Office 365. Esta herramienta cifra los archivos PST y, a continuación, los carga y almacena en una ubicación de Azure Storage en la nube de Microsoft. Para completar este paso, los archivos PST deben encontrarse en un recurso compartido de archivos o en un servidor de archivos de la organización. Esto se conoce como el directorio de origen en el siguiente procedimiento. Cada vez que ejecuta la herramienta O365ImportTool. exe, puede especificar un directorio de origen diferente. 
  
1. Abra el símbolo del sistema del equipo local.
    
2. Vaya al directorio en el que instaló la herramienta O365ImportTool.exe en el paso 4.
    
3. Ejecute el siguiente comando para cifrar y cargar los archivos PST a Office 365.
    
    ```
    O365ImportTool.exe /srcdir:<Location of PST files> /protect-rmsserver:<RMS licensing location> /protect-tenantid:<BPOSId> /protect-key:<Symmetric key> /transfer:upload /upload-dest:<Network upload URL> /upload-destSAS:<SAS key>
    ```

    En la tabla siguiente se describen los parámetros y los valores requeridos. Tenga en cuenta que la información de los pasos anteriores se usa en los valores de estos parámetros.
    
    |**Parameter**|**Descripción**|**Ejemplo**|
    |:-----|:-----|:-----|
    | `/srcdir:` <br/> |Especifica el directorio de origen de la organización que contiene los archivos PST que se cargarán en Office 365.  <br/> | `/srcdir:\\FILESERVER01\PSTs` <br/> |
    | `/protect-rmsserver:` <br/> |Especifica la ubicación de licencias para el servicio de Azure RMS. Use el valor de la `LicensingIntranetDistributionPointUrl` propiedad que obtuvo en el paso 3. Asegúrese de rodear el valor de este parámetro con comillas dobles ("").  <br/> | `/protect-rmsserver:"https://afcbd8ec-cb2b-4a1a-8246-0b4bc22d1978.rms.na.aadrm.com/_wmcs/licensing"` <br/> |
    | `/protect-tenantid:` <br/> |Especifica la identidad de la organización de Azure RMS. Use el valor de la `BPOSId` propiedad que obtuvo en el paso 3.  <br/> | `/protect-tenantid:42745b33-2a5c-4726-8a2a-ca43caa0f74b` <br/> |
    | `/protect-key:` <br/> |Especifica la clave simétrica que obtuvo en el paso 2. No olvide incluir el valor de este parámetro entre comillas dobles (" ").  <br/> | `/protect-key:"l+R+Umc5RGmSBh1oW+DoyMxm/h5h2JJXFcNOFiNp867="` <br/> |
    | `/transfer:` <br/> |Especifica si los archivos PST se cargan a través de la red o si se envían en una unidad de disco duro. El valor `upload` indica que está cargando los archivos a través de la red. El valor `drive` indica que está enviando los archivos PST en una unidad de disco duro.  <br/> | `/transfer:upload` <br/> |
    | `/upload-dest:` <br/> |Especifica el destino en Office 365 donde se cargarán los archivos PST; Esta es la ubicación de almacenamiento de Azure de su organización. El valor de este parámetro se compone de la dirección URL de carga de red de la dirección URL de SAS que copió en el paso 4. No olvide incluir el valor de este parámetro entre comillas dobles (" ").  <br/><br/> **Sugerencia:** Opcional Puede especificar una subcarpeta en la ubicación de Azure Storage en la que se van a cargar los archivos PST cifrados. Para hacerlo, agregue una ubicación de subcarpeta (después de "ingestiondata") en la dirección URL de carga de red. El primer ejemplo no especifica una subcarpeta; Esto significa que los archivos PST se cargarán en la raíz (denominada *ingestiondata* ) de la ubicación de almacenamiento de Azure. En el segundo ejemplo se cargan los archivos PST en una subcarpeta (denominada *EncryptedPSTs* ) en la ubicación de almacenamiento de Azure.           | `/upload-dest:"https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata"` <br/> O bien  <br/>  `/upload-dest:"https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata/EncryptedPSTs"` <br/> |
    | `/upload-destSAS:` <br/> |Especifica la clave SAS para la organización. El valor de este parámetro se compone de la clave SAS de la dirección URL de SAS que copió en el paso 4. Tenga en cuenta que el primer carácter de la clave SAS es un signo de interrogación ("?"). No olvide incluir el valor de este parámetro entre comillas dobles (" ").  <br/> | `/upload-destSAS:"?sv=2012-02-12&amp;se=9999-12-31T23%3A59%3A59Z&amp;sr=c&amp;si=IngestionSasForAzCopy201601121920498117&amp;sig=Vt5S4hVzlzMcBkuH8bH711atBffdrOS72TlV1mNdORg%3D"` <br/> |
    | `/recurse` <br/> |Este modificador opcional especifica el modo recursivo para que la herramienta O365ImportTool. exe copie los archivos PST que se encuentran en las subcarpetas en el directorio de origen especificado por el `/srcdir:` parámetro.  <br/><br/> **Nota:** Si incluye este modificador, los archivos PST en las subcarpetas tendrán un directorio de ruta de archivo diferente en la ubicación de almacenamiento de Azure después de que se carguen. Tendrá que especificar el nombre exacto de la ruta de acceso de archivo en el archivo CSV que cree en el paso 7.           | `/recurse` <br/> |
   
    A continuación se muestra un ejemplo de la sintaxis de la herramienta O365ImportTool.exe, en el que se usan valores reales para cada parámetro:
    
    ```
    O365ImportTool.exe /srcdir:\\FILESERVER01\PSTs /protect-rmsserver:"https://afcbd8ec-cb2b-4a1a-8246-0b4bc22d1978.rms.na.aadrm.com/_wmcs/licensing" /protect-tenantid:42745b33-2a5c-4726-8a2a-ca43caa0f74b  /protect-key:"l+R+Umc5RGmSBh1oW+DoyMxm/h5h2JJXFcNOFiNp867=" /transfer:upload /upload-dest:"https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata" /upload-destSAS:"?sv=2012-02-12&amp;se=9999-12-31T23%3A59%3A59Z&amp;sr=c&amp;si=IngestionSasForAzCopy201601121920498117&amp;sig=Vt5S4hVzlzMcBkuH8bH711atBffdrOS72TlV1mNdORg%3D"
    ```

    Después de ejecutar el comando, aparecen mensajes de estado en los que se muestra el progreso del cifrado y la carga de los archivos PST. En un mensaje de estado final aparece el número total de archivos cifrados y cargados correctamente.  
    
    > [!TIP]
    > Después de ejecutar correctamente el comando O365ImportTool.exe y de comprobar que todos los parámetros son correctos, guarde una copia de la sintaxis de la línea de comandos en el mismo archivo (protegido) en el que copió la información obtenida en los pasos anteriores. A continuación, puede copiar y pegar este comando en un símbolo del sistema cada vez que desee ejecutar la herramienta O365ImportTool. exe para cifrar y cargar los archivos PST a Office 365. Los únicos valores que puede que deba cambiar son los de los `/srcdir:` parámetros y `/upload-dest:` . 
  
## <a name="optional-step-6-view-a-list-of-the-pst-files-uploaded-to-office-365"></a>Opcional Paso 6: ver una lista de los archivos PST cargados en Office 365

Como paso opcional, puede instalar y usar el explorador de almacenamiento de Microsoft Azure (que es una herramienta de código abierto gratuita) para ver la lista de los archivos PST que ha cargado en el BLOB de Azure. Hay tres buenas razones para hacer esto:
  
- Compruebe que los archivos PST de la carpeta compartida o el servidor de archivos de la organización se hayan cargado correctamente en el BLOB de Azure.

- Compruebe que los archivos PST están cifrados. Los archivos PST cifrados `.pfile` tienen una extensión anexada al nombre del archivo pst; por ejemplo, `pilarp.pst.pfile`.
    
- Compruebe el nombre de archivo (y la ruta de directorio de la subcarpeta si incluyó una) para cada archivo PST cargado en el BLOB de Azure. Esto es muy útil al crear el archivo de asignación de PST en el paso siguiente, ya que tendrá que especificar el nombre de ruta de la carpeta y el nombre de archivo de todos los archivos PST. Comprobar estos nombres puede ayudar a reducir posibles errores en el archivo de asignación de PST.
    
El explorador de almacenamiento de Microsoft Azure está en versión preliminar. 
  
 > [!IMPORTANT]
>  No puede usar el explorador de Azure Storage para cargar o modificar archivos PST. El único método admitido para importar archivos PST a Office 365 es usar AzCopy. Además, no puede eliminar los archivos PST que ha cargado en el BLOB de Azure. Si intenta eliminar un archivo PST, recibirá un error sobre no tener los permisos necesarios. Tenga en cuenta que todos los archivos PST se eliminan automáticamente del área de almacenamiento de Azure. If there are no import jobs in progress, then all PST files in the **ingestiondata** container are deleted 30 days after the most recent import job was created. 
  
Para instalar el explorador de almacenamiento de Azure y conectarse a su área de almacenamiento de Azure:
  
1. Descargue e instale la [herramienta Microsoft Azure Storage Explorer](https://go.microsoft.com/fwlink/p/?LinkId=544842).
    
2. Inicie el explorador de almacenamiento de Microsoft Azure, haga clic con el botón derecho en **cuentas de almacenamiento** en el panel izquierdo y, después, haga clic en **conectar a Azure Storage**. 
    
    ![Haga clic con el botón secundario en cuentas de almacenamiento y haga clic en conectar a Azure Storage](media/75b80cc3-c336-4f96-ad32-54ac9b96a7af.png)
  
3. En el cuadro en **conectarse a Azure Storage**, pegue la dirección URL de SAS que obtuvo en el paso 4 y, a continuación, haga clic en **siguiente**. 
    
    ![Pegue la dirección URL de SAS en el cuadro de la página conectar a Azure Storage](media/5d034128-e087-48e1-9ebc-4c9fa262d5b7.png)
  
4. En la página **Resumen de conexión** , puede revisar la información de conexión y, a continuación, hacer clic en **conectar**. 
    
5. En **cuentas de almacenamiento**, expanda el nodo **(SAS de servicio)** y, a continuación, expanda el nodo **contenedores** de blobs. 
    
6. Haga clic con el botón derecho en **ingestiondata** y, después, haga clic en **Abrir editor de contenedores de blobs**.
    
    ![Haga clic con el botón derecho en ingestiondata y, después, haga clic en Abrir editor de contenedores de blobs.](media/f50eee30-9202-4efc-904a-2895a0bc388d.png)
  
    Se muestra el área de almacenamiento de Azure, con una lista de los archivos PST que cargó en el paso 5.
    
    ![El explorador de almacenamiento de Azure muestra una lista de los archivos PST que ha cargado](media/a448ae43-e744-4153-8304-22b59e93883c.png)
  
7. Cuando haya terminado de usar el explorador de almacenamiento de Microsoft Azure, haga clic con el botón secundario en **ingestiondata**y, a continuación, haga clic en **desconectar** para desconectarse de su área de almacenamiento de Azure. En caso contrario, recibirá un error la próxima vez que intente conectarse. 
    
    ![Haga clic con el botón derecho en la ingesta y haga clic en Desasociar para desconectar de su área de almacenamiento de Azure](media/1e8e5e95-4215-4ce4-a13d-ab5f826a0510.png)
  
## <a name="step-7-create-the-pst-import-mapping-file"></a>Paso 7: crear el archivo de asignación de importaciones de PST

Una vez cifrados y cargados los archivos PST en la ubicación de almacenamiento de Azure para la organización de Office 365, el siguiente paso consiste en crear un archivo de valores separados por comas (CSV) que especifica a qué buzones de usuario se importarán los archivos PST. Este archivo CSV se enviará en el paso siguiente, cuando cree un trabajo de importación de archivos PST.
  
1. [Descargue una copia del archivo de asignación de importaciones de PST](https://go.microsoft.com/fwlink/p/?LinkId=544717). 
    
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

    En la primera fila (o la primera fila de encabezado) del archivo CSV aparecen los parámetros que usará el servicio de importación de PST para importar los archivos PST a los buzones de los usuarios. Los nombres de los parámetros están separados por comas. Cada fila situada debajo de la fila de encabezado representa los valores de parámetro para importar un archivo PST a un buzón específico. Necesitará una fila para cada archivo PST al que desee importar un buzón de usuario. No olvide reemplazar los datos de los marcadores de posición del archivo de asignación por los datos reales.
    
    > [!NOTE]
    > No cambie nada en la fila de encabezado, ni siquiera los parámetros SharePoint; se ignorarán durante el proceso de importación de PST. 
  
3. Use la información de la tabla siguiente para rellenar el archivo CSV con la información necesaria.
    
    |**Parameter**|**Descripción**|**Ejemplo**|
    |:-----|:-----|:-----|
    | `Workload` <br/> |Especifica el servicio de Office 365 al que se importarán los datos. Para importar archivos PST a los buzones de usuario `Exchange`, use.  <br/> | `Exchange` <br/> |
    | `FilePath` <br/> |Especifica la ubicación de la carpeta en la ubicación de almacenamiento de Azure en la que cargó los archivos PST en el paso 5.  <br/>  Si no incluyó un nombre de subcarpeta opcional en la dirección URL de red en `/upload-dest:` el parámetro en el paso 5, deje este parámetro en blanco en el archivo CSV. Si incluyó un nombre de subcarpeta, debe especificarlo en este parámetro. El valor de este parámetro distingue mayúsculas de minúsculas. En cualquier caso, *no* incluya "ingestiondata" en el valor del `FilePath` parámetro.  <br/> <br/>**Importante:** El caso del nombre de la ruta de acceso del archivo debe ser el mismo caso que usó si incluyó un nombre de subcarpeta opcional en la dirección URL `/upload-dest:` de SAS en el parámetro del paso 5. Por ejemplo, si ha usado `EncryptedPSTs` para el nombre de la subcarpeta en el paso 5 y `encryptedpsts` , a `FilePath` continuación, usa en el parámetro en el archivo CSV, se producirá un error en la importación del archivo pst. Asegúrese de usar el mismo caso en ambas instancias.           |(se deja en blanco)  <br/> O bien  <br/>  `EncryptedPSTs` <br/> |
    | `Name` <br/> |Especifica el nombre del archivo PST que se importará al buzón del usuario.  El valor de este parámetro distingue mayúsculas de minúsculas. Debido a que los archivos PST que se cargan en la ubicación de Azure Storage están cifrados, se agrega una `.pfile` extensión al nombre de archivo pst. Debe agregar la `.pfile` extensión al nombre de los archivos PST en el archivo CSV.  <br/><br/> **Importante:** El caso del nombre de archivo PST en el archivo CSV debe ser el mismo que el archivo PST que se cargó en la ubicación de almacenamiento de Azure en el paso 5. Por ejemplo, si usa `annb.pst.pfile` en el `Name` parámetro del archivo CSV, pero el nombre del archivo pst real `AnnB.pst`, se producirá un error en la importación de ese archivo pst. Asegúrese de que el nombre del archivo PST en el archivo CSV use el mismo caso que el archivo PST real.           | `annb.pst.pfile` <br/> |
    | `Mailbox` <br/> |Especifica la dirección de correo electrónico del buzón en el que se importará el archivo PST.   <br/> Para importar un archivo PST a un buzón inactivo, tiene que especificar el GUID de buzón para este parámetro. Para obtener este GUID, ejecute el siguiente comando de PowerShell en Exchange Online:  `Get-Mailbox -InactiveMailboxOnly <identity of inactive mailbox> | FL Guid` <br/><br/> **Nota:** En algunos casos, puede tener varios buzones con la misma dirección de correo electrónico, donde un buzón es un buzón activo y el otro buzón está en un estado eliminado temporalmente (o inactivo). En estas situaciones, ha especificado el GUID de buzón para identificar de forma exclusiva el buzón en el que se va a importar el archivo PST. Para obtener este GUID para buzones activos, ejecute el siguiente comando de PowerShell `Get-Mailbox - <identity of active mailbox> | FL Guid`:. Para obtener el GUID de los buzones eliminados temporalmente (o inactivos), ejecute este comando  `Get-Mailbox - <identity of soft-deleted or inactive mailbox> -SoftDeletedMailbox | FL Guid`           | `annb@contoso.onmicrosoft.com` <br/> O bien  <br/>  `2d7a87fe-d6a2-40cc-8aff-1ebea80d4ae7` <br/> |
    | `IsArchive` <br/> | Especifica si se va a importar o no el archivo PST en el buzón de archivo del usuario. Hay dos opciones:  <br/> **False** Importa el archivo PST en el buzón de correo principal del usuario.  <br/> **True** Importa el archivo PST en el buzón de archivo del usuario.  <br/>  If you leave this parameter blank, the PST file is imported to the user's primary mailbox.  <br/><br/> **Nota:** Para importar un archivo PST a un buzón de archivo basado en la nube para un usuario cuyo buzón de correo principal es local, solo especifique **true** para este parámetro y especifique la dirección de correo electrónico del buzón local del usuario para `Mailbox` el parámetro.           | `FALSE` <br/> O bien  <br/>  `TRUE` <br/> |
    | `TargetRootFolder` <br/> | Especifica la carpeta de buzón de correo a la que se importa el archivo PST.  <br/>  Si deja este parámetro en blanco, el archivo PST se importará a una nueva carpeta **** denominada importada que se encuentre en el nivel raíz del buzón de correo (el mismo nivel que la carpeta Bandeja de entrada y las otras carpetas de buzón de correo predeterminadas).  <br/>  Si especifica `/`, los elementos del archivo pst se importarán directamente en la carpeta Bandeja de entrada del usuario.  <br/>  Si especifica `/<foldername>`, los elementos del archivo pst se importarán a una subcarpeta denominada * \<nombreDeCarpeta\> * . Por ejemplo, si usa `/ImportedPst`, los elementos se importarán a una subcarpeta denominada **ImportedPst**. Esta subcarpeta se ubicará en la carpeta Bandeja de entrada del usuario.  <br/><br/> **Sugerencia:** Considere la posibilidad de ejecutar algunos lotes de prueba para experimentar con este parámetro, de modo que pueda determinar la mejor ubicación de la carpeta en la que se van a importar los archivos PST.           |(se deja en blanco)  <br/> O bien  <br/>  `/` <br/> O bien  <br/>  `/ImportedPst` <br/> |
    | `ContentCodePage` <br/> |Este parámetro opcional especifica un valor numérico para la página de códigos que se va a usar para importar archivos PST en el formato de archivo ANSI. Este parámetro se usa para importar archivos PST desde organizaciones de chino, Japonés y Coreano (CJK) porque estos idiomas suelen usar un juego de caracteres de doble byte (DBCS) para la codificación de caracteres. Si este parámetro no se usa para importar archivos PST para idiomas que usan DBCS para nombres de carpeta de buzón de correo, los nombres de carpeta suelen ser ilegibles una vez importados. Para obtener una lista de los valores admitidos que se deben usar para este parámetro, consulte identificadores de [Página de códigos](https://go.microsoft.com/fwlink/p/?LinkId=328514).  <br/><br/> **Nota:** Como se mencionó anteriormente, este es un parámetro opcional y no es necesario incluirlo en el archivo CSV. O puede incluirlo y dejar el valor en blanco para una o más filas.           |(se deja en blanco)  <br/> O bien  <br/>  `932` (que es el identificador de la página de códigos para ANSI/OEM japonés)  <br/> |
    | `SPFileContainer` <br/> |Para la importación de archivos PST, deje este parámetro en blanco.   <br/> |No aplicable  <br/> |
    | `SPManifestContainer` <br/> |Para la importación de archivos PST, deje este parámetro en blanco.   <br/> |No aplicable  <br/> |
    | `SPSiteUrl` <br/> |Para la importación de archivos PST, deje este parámetro en blanco.   <br/> |No aplicable  <br/> |
  
## <a name="step-8-create-a-pst-import-job-in-office-365"></a>Paso 8: crear un trabajo de importación de PST en Office 365

El último paso consiste en crear el trabajo de importación de PST en el servicio de importación en Office 365. Como se ha explicado anteriormente, enviará el archivo de asignación de importaciones de PST que creó en el paso 7. Después de crear el nuevo trabajo, el servicio de importación usará la información del archivo de asignación para descifrar e importar los archivos PST (que ha cargado en Office 365 en el paso 5) al buzón de usuario especificado. 
  
1. Vaya a [https://protection.office.com](https://protection.office.com).
    
2. Inicie sesión en Office 365 con las credenciales de una cuenta de administrador de su organización de Office 365.
    
3. En el panel izquierdo, haga clic en **gobierno de datos** y, a continuación, haga clic en **importar**.
    
4. En la página **Importar**, haga clic en **Ir al servicio de importación**.
    
5. en la página **importar datos a Office 365** , haga clic en **nuevo**![icono](media/ITPro-EAC-AddIcon.gif)agregar trabajo y, a continuación, haga clic en **cargar mensajes de correo electrónico (archivos PST)**.
    
6. En la página **Cargar archivos a través de la red**, marque las casillas **Terminé de cargar mis archivos** y **Tengo acceso al archivo de asignación** y haga clic en **Siguiente**.  
    
7. Escriba un nombre para el trabajo de importación de PST y haga clic en **Siguiente**.
    
8. Haga **** ![clic en agregar](media/ITPro-EAC-AddIcon.gif) icono para agregar para seleccionar el archivo de asignación de PST que creó en el paso 7. 
    
9. Cuando el nombre del archivo CSV aparezca en la lista, selecciónelo y haga clic en **Validar** para comprobar si hay errores en el archivo CSV.  
    
    > [!NOTE]
    > Como se explicó anteriormente, cuando se cifran los archivos PST `.pfile` , se anexa una extensión al nombre del archivo pst. Debe agregar la `.pfile` extensión al nombre de los archivos PST en el archivo CSV. Si no lo hace, se producirá un error en la validación del archivo CSV. 
  
    El archivo CSV debe estar validado correctamente para poder crear un trabajo de importación de PST. Si se produce un error en la validación, haga clic en el vínculo **No válido** de la columna **Estado**. Se abrirá una copia del archivo de asignación de importaciones de PST, con un mensaje de error para todas las filas del error en el que se produjo el error. 
    
10. Cuando el archivo de asignación de importaciones de PST se haya validado correctamente, lea el documento de términos y condiciones y marque la casilla.
    
11. Haga clic en **Finalizar** para enviar el trabajo. 
    
    El trabajo se muestra en la lista de trabajos de importación de PST en la página **importar datos a Office 365** . 
    
12. Seleccione el trabajo y haga ****![clic en actualizar](media/O365-MDM-Policy-RefreshIcon.gif) icono de actualización para actualizar la información de estado que se muestra en el panel de detalles. 
    
13. En el panel de detalles, haga clic en **Ver detalles** para obtener el último estado del trabajo seleccionado. 
 
## <a name="more-information"></a>Más información

- ¿Por qué importar archivos PST a Office 365?
    
  - Es una buena forma de migrar el correo electrónico de su organización a Office 365.
    
  - Ayuda a satisfacer las necesidades de cumplimiento de la organización, ya que le permite:
    
  - Habilitar buzones de archivo para proporcionar a los usuarios espacio de almacenamiento adicional en el buzón.
    
  - Colocar los buzones en espera para conservar el contenido.
    
  - Usar las herramientas de exhibición de documentos electrónicos de Microsoft para buscar contenido en los buzones.
    
  - Usar directivas de retención para controlar el tiempo durante el que se conserva el contenido de los buzones.
    
  - Busque en el registro de auditoría de Office 365 los eventos relacionados con el buzón.
    
  - Le protege frente a la pérdida de datos. Los archivos PST que se importan a los buzones de correo de Office 365 heredan las características de alta disponibilidad de Exchange Online, en lugar de almacenar los datos en el equipo de un usuario.
    
  - Los datos están disponibles para el usuario en todos los dispositivos, ya que se almacenan en la nube.
    
- A continuación, se muestra un ejemplo de las claves, los identificadores y las direcciones URL que se obtienen en los pasos 2, 3 y 4. Este ejemplo también contiene la sintaxis del comando que se ejecuta en la herramienta O365ImportTool. exe para cifrar y cargar los archivos PST a Office 365. Asegúrese de tomar precauciones para protegerlos de la misma manera que protegería las contraseñas u otra información relacionada con la seguridad.
    
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

- Como se explicó anteriormente, el servicio de importación de Office 365 activa la opción de espera de retención (por una duración indefinida) después de que los archivos PST se hayan importado a un buzón. Esto significa que la propiedad *RentionHoldEnabled* se establece `True` en para que no se procese la Directiva de retención asignada al buzón. Esto le da al propietario del buzón de correo el tiempo de administrar los mensajes recién importados al impedir que una directiva de eliminación o de archivo elimine o Archive mensajes más antiguos. Estos son algunos de los pasos que puede seguir para administrar esta suspensión de retención: 
    
  - Después de un período de tiempo determinado, puede desactivar la suspensión de la retención mediante la `Set-Mailbox -RetentionHoldEnabled $false` ejecución del comando. Para obtener instrucciones, vea [poner un buzón de correo en suspensión de retención](https://go.microsoft.com/fwlink/p/?LinkId=544749).
    
  - Puede configurar la suspensión de la retención para que esté desactivada en alguna fecha en el futuro. Para ello, ejecute el `Set-Mailbox -EndDateForRetentionHold <date>` comando. Por ejemplo, suponiendo que la fecha de hoy es el 1 de junio de 2016 y desea que la suspensión de la retención esté desactivada en 30 días, `Set-Mailbox -EndDateForRetentionHold 7/1/2016`ejecutaría el siguiente comando:. En este escenario, dejaría la propiedad *RentionHoldEnabled* establecida en `True`. Para obtener más información, vea [set-Mailbox](https://go.microsoft.com/fwlink/p/?LinkId=150317).
    
  - Puede cambiar la configuración de la Directiva de retención asignada al buzón para que los elementos más antiguos que se hayan importado no se eliminen inmediatamente ni se muevan al buzón de archivo del usuario. Por ejemplo, puede alargar la antigüedad de retención de una directiva de eliminación o archivo asignada al buzón. En este escenario, se desactiva la suspensión de la retención en el buzón de correo después de cambiar la configuración de la Directiva de retención. Para obtener más información, consulte [configurar una directiva de archivo y eliminación para buzones en la organización de Office 365](set-up-an-archive-and-deletion-policy-for-mailboxes.md).
