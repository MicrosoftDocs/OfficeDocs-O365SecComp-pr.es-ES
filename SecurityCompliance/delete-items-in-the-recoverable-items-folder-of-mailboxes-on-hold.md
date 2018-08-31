---
title: Eliminar elementos de la carpeta elementos recuperables de los buzones de correo basados en la nube en espera - ayuda de administración
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 9/21/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: a85e1c87-a48e-4715-bfa9-d5275cde67b0
description: 'Para los administradores: eliminar elementos de carpeta de elementos recuperables de un usuario para un buzón de Exchange Online, incluso si ese buzón se coloca en retención legal. Esto es una forma eficaz para eliminar los datos que se ha derramado accidentalmente en Office 365.'
ms.openlocfilehash: 0519e389f05ed9952090fb9b163a05d18e3bd762
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "23014034"
---
# <a name="delete-items-in-the-recoverable-items-folder-of-cloud-based-mailboxes-on-hold---admin-help"></a>Eliminar elementos de la carpeta elementos recuperables de los buzones de correo basados en la nube en espera - ayuda de administración

La carpeta elementos recuperables para un buzón de Exchange Online existe para proteger contra eliminaciones accidentales o intencionadas. También se usa para almacenar los elementos que se conservan y el acceso a características de cumplimiento de normas de Office 365, como las suspensiones y exhibición de documentos electrónicos las búsquedas. Sin embargo, en algunas situaciones en las organizaciones es posible que tienen datos que se ha conservado por equivocación en la carpeta elementos recuperables que debe eliminar. Por ejemplo, un usuario sin darse cuenta podría enviar o reenviar un mensaje de correo electrónico que contiene información confidencial o información que puede tener consecuencias serio del negocio. Incluso si el mensaje se elimina de manera permanente, es posible que se retenga indefinidamente porque se ha colocado una suspensión legal en el buzón de correo. En este escenario se conoce como pérdidas de datos porque derramas accidentalmente datos en Office 365. En estas situaciones, puede eliminar los elementos de carpeta de elementos recuperables de un usuario para un buzón de Exchange Online, incluso si ese buzón se pondrá en espera con una de las características de suspensión diferentes en Office 365. Estos tipos de suspensiones incluyen contiene litigios, suspensiones en contexto, suspensiones de exhibición de documentos electrónicos y las directivas de retención de Office 365 creadas en la seguridad de Office 365 &amp; centro de cumplimiento. 
  
 En este artículo se explica cómo eliminar elementos de la carpeta elementos recuperables de buzones de correo basados en la nube que están en espera. Este procedimiento implica deshabilitar acceso al buzón y deshabilitar la recuperación de elemento único, deshabilitar el Asistente para carpeta administrada de procesar el buzón, quitar temporalmente la suspensión, eliminar elementos de la carpeta elementos recuperables y, a continuación, revertir el buzón de correo a su configuración anterior. Este es el proceso: 
  
[Paso 1: Recopilar información acerca del buzón](#step-1-collect-information-about-the-mailbox)

[Paso 2: Preparar el buzón de correo](#step-2-prepare-the-mailbox)

[Paso 3: Quitar todas las suspensiones desde el buzón de correo](#step-3-remove-all-holds-from-the-mailbox)

[Paso 4: Eliminar elementos de la carpeta elementos recuperables](#step-4-delete-items-in-the-recoverable-items-folder)

[Paso 5: Revertir el buzón de correo a su estado anterior](#step-5-revert-the-mailbox-to-its-previous-state)
  
> [!CAUTION]
> Los procedimientos descritos en este artículo, se producirá datos que se va a eliminar de forma permanente (depuraron) de un buzón de Exchange Online. Es decir, los mensajes que se eliminan de la carpeta elementos recuperables no se pueden recuperar y no estarán disponibles para otros fines de cumplimiento de normas o de descubrimiento legal. Si desea eliminar los mensajes de un buzón que se pondrá en espera como parte de un juicio, conservación local, mantenga presionada la exhibición de documentos electrónicos o directiva de retención de Office 365 creado en la seguridad de Office 365 &amp; centro de cumplimiento, verificación con la administración de registros o con fines legales departamentos antes de quitar la suspensión. Su organización puede tener una directiva que define si un buzón de correo en espera o un incidente de pérdidas de datos tiene prioridad. 
  
## <a name="before-you-begin"></a>Antes de empezar

- Se debe asignarse ambas de las siguientes funciones de administración de Exchange en línea para buscar y eliminar mensajes de la carpeta elementos recuperables en el paso 4.
    
  - **Búsqueda de buzones** - esta función permite para buscar los buzones de correo en la organización. Los administradores de Exchange no están asignados a esta función de forma predeterminada. Para asignar manualmente este rol, agregar usted mismo como miembro del grupo de roles de administración de detección en Exchange Online. 
    
  - **Buzón de correo importar exportar** - este rol permite para eliminar mensajes del buzón de un usuario. De forma predeterminada, esta función no está asignada a ningún grupo de funciones. Para eliminar los mensajes de los buzones de los usuarios, puede agregar la función de exportación de importación de buzón de correo para el grupo de roles de administración de la organización de Exchange en línea. 
    
- El procedimiento descrito en este artículo no se admite para los buzones de correo inactivos. Debido a que no puede volver a aplicar una suspensión (o directiva de retención de Office 365) que consiste en un buzón inactivo después de quitarlo. Cuando se quita una suspensión de un buzón de correo inactivo, se cambia a un buzón eliminado temporalmente normal y se eliminarán permanentemente de la organización una vez que se procesa mediante el Asistente para carpeta administrada.
    
- No se puede realizar este procedimiento para un buzón de correo que se ha asignado a una directiva de retención de Office 365 que se han sido bloqueada con un bloqueo de conservación. Eso es porque un bloqueo de conservación impide que se quiten o excluyendo el buzón de correo de la directiva de retención de Office 365 y de deshabilitar el Asistente de carpetas administradas en el buzón de correo. Para obtener más información acerca de las directivas de retención de bloqueo, vea [bloqueo de una directiva de retención](retention-policies.md#locking-a-retention-policy).
    
- Si un buzón de correo no se pondrá en espera (o no tiene la recuperación de un solo elemento habilitada), simplemente puede eliminar los elementos de la carpeta elementos recuperables. Para obtener más información acerca de cómo hacer esto, vea [Buscar y eliminar mensajes ](https://go.microsoft.com/fwlink/?linkid=852453).
  
## <a name="step-1-collect-information-about-the-mailbox"></a>Paso 1: Recopilar información acerca del buzón

En este primer paso es recopilar las propiedades seleccionadas del buzón de destino que afectará a este procedimiento. Asegúrese de anotar estas opciones de configuración o guardarlos en un archivo de texto, ya que podrá cambiar algunas de estas propiedades y, a continuación, volver a los valores originales en el paso 5, después de eliminar los elementos de la carpeta elementos recuperables. Aquí es una lista de las propiedades del buzón de correo que necesita recopilar.
  
-  *SingleItemRecoveryEnabled* y *RetainDeletedItemsFor* ; Si es necesario, podrá deshabilitar la recuperación único y aumentar el período de retención de elementos eliminados en el paso 3. 
    
-  *LitigationHoldEnabled* y *InPlaceHolds* ; deberá identificar todas las suspensiones colocadas en el buzón de correo para que se pueden quitar temporalmente en el paso 3. Vea la sección [obtener más información](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md#moreinfo) para obtener sugerencias sobre cómo identificar la suspensión de tipo que se puede incluir en un buzón de correo. 
    
Además, debe obtener el buzón de correo en configuración de acceso de cliente, por lo que puede deshabilitarlas temporalmente por lo que el propietario (u otros usuarios) no se pueden obtener acceso al buzón durante este procedimiento. Por último, puede obtener el tamaño actual y el número de elementos en la carpeta elementos recuperables. Después de eliminar elementos de la carpeta elementos recuperables en el paso 4, debe usar esta información para comprobar que realmente se han eliminado los elementos.
  
1. [Conectarse a Exchange Online PowerShell](https://go.microsoft.com/fwlink/?linkid=396554). Asegúrese de usar un nombre de usuario y una contraseña para una cuenta de administrador que se ha asignado los roles de administración adecuada de Exchange Online. 
    
2. Ejecute el siguiente comando para obtener información acerca de la recuperación de elemento único y el período de retención de elementos eliminados.

    ```
    Get-Mailbox <username> | FL SingleItemRecoveryEnabled,RetainDeletedItemsFor
    ```

   Si está habilitada la recuperación de elemento único, debe deshabilitar en el paso 2. Si no se establece el período de retención de elementos eliminados durante 30 días (el valor máximo en Exchange Online), a continuación, puede aumentar en el paso 2. 
    
3. Ejecute el siguiente comando para obtener el buzón de configuración de acceso para el buzón de correo. 
    
    ```
    Get-CASMailbox <username> | FL EwsEnabled,ActiveSyncEnabled,MAPIEnabled,OWAEnabled,ImapEnabled,PopEnabled
    ```

   Podrá deshabilitar todos estos métodos de acceso en el paso 2.
    
4. Ejecute el siguiente comando para obtener información sobre las suspensiones y las directivas de retención de Office 365 aplicadas al buzón de correo.
    
    ```
    Get-Mailbox <username> | FL LitigationHoldEnabled,InPlaceHolds
    ```


   > [!TIP]
    > Si hay demasiados valores de la propiedad *InPlaceHolds* y no todos ellos se muestran, puede ejecutar el `Get-Mailbox <username> | Select-Object -ExpandProperty InPlaceHolds` comando para mostrar cada valor en una línea independiente. 
  
5. Ejecute el comando siguiente para obtener información acerca de las directivas de retención de Office 365 de toda la organización. 

    ```
    Get-OrganizationConfig | FL InPlaceHolds
    ```
   Si su organización tiene las directivas de retención de Office 365 de toda la organización, debe excluir el buzón de correo de estas directivas en el paso 3.

   > [!TIP]
    > Si hay demasiados valores de la propiedad *InPlaceHolds* y no todos ellos se muestran, puede ejecutar el `Get-OrganizationConfig | Select-Object -ExpandProperty InPlaceHolds` comando para mostrar cada valor en una línea independiente. 
  
6. Ejecute el siguiente comando para obtener el tamaño actual y el número total de elementos en carpetas y subcarpetas en la carpeta elementos recuperables en el buzón del usuario principal. 

    ```
    Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
    ```

   Si se habilita el buzón de archivo del usuario, ejecute el siguiente comando para obtener el tamaño y el número total de elementos en carpetas y subcarpetas en la carpeta elementos recuperables en su buzón de archivo. 

    ```
    Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems -Archive | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
    ```

   Cuando elimina los elementos en el paso 4, puede elegir eliminar o no eliminar elementos de la carpeta elementos recuperables en el buzón del usuario principal del archivo. Tenga en cuenta que si está habilitado la ampliación automática de archivado para el buzón de correo, los elementos de un buzón de archivo auxiliar no se eliminará.
  
## <a name="step-2-prepare-the-mailbox"></a>Paso 2: Preparar el buzón de correo

Después de recopilar y guardar información acerca del buzón, el siguiente paso es preparar el buzón de correo mediante la realización de las siguientes tareas: 
  
- **Deshabilitar el acceso de cliente al buzón de correo** para que el propietario del buzón no se puede obtener acceso a sus buzones de correo y realizar cambios en los datos de buzones durante este procedimiento. 
    
- **Aumentar el período de retención de elementos eliminados** en 30 días (el valor máximo en Exchange Online) para que no se purgan elementos desde la carpeta elementos recuperables antes de poder eliminar en el paso 4. 
    
- **Deshabilitar la recuperación de elemento único** por lo los elementos no se conservan (para la duración del período de retención de elementos eliminados) después de eliminar de la carpeta elementos recuperables en el paso 4. 
    
- **Deshabilitar el Asistente para carpeta administrada** por lo que no procesar el buzón de correo y conservar los elementos que se eliminan en el paso 4. 
    
Realice los pasos siguientes en Exchange Online PowerShell.
  
1. Ejecute el siguiente comando para deshabilitar todo el acceso de cliente para el buzón de correo. La sintaxis del comando, se da por supuesto que todos los métodos de acceso de cliente están habilitados en el buzón de correo.

    ```   
    Set-CASMailbox <username> -EwsEnabled $false -ActiveSyncEnabled $false -MAPIEnabled $false -OWAEnabled $false -ImapEnabled $false -PopEnabled $false
    ```
   
   > [!NOTE]
    > Pueden tardar hasta 60 minutos para deshabilitar todos los métodos de acceso de cliente para el buzón de correo. Tenga en cuenta que al deshabilitar estos métodos de acceso no desconecta el propietario del buzón que haya iniciado la sesión. Si el propietario no se ha iniciado sesión, a continuación, no podrán tener acceso a su buzón después de que se deshabilitan estos métodos de acceso. 
  
2. Ejecute el siguiente comando para aumentar el período de retención de elementos eliminados en el máximo de 30 días. Esto supone que la configuración actual es menor que 30 días. 

    ```
    Set-Mailbox <username> -RetainDeletedItemsFor 30
    ```

3. Ejecute el siguiente comando para deshabilitar la recuperación de elemento único.
    
    ```
    Set-Mailbox <username> -SingleItemRecoveryEnabled $false
    ```

   > [!NOTE]
    > Pueden tardar hasta 60 minutos para deshabilitar la recuperación de elemento único. No eliminar los elementos en la carpeta elementos recuperables hasta que haya transcurrido este período. 
  
4. Ejecute el siguiente comando para evitar que el Asistente para carpeta administrada procesar el buzón. Como se explica anteriormente, puede deshabilitar el Asistente para carpeta administrada sólo si no se aplica una directiva de retención de Office 365 con un bloqueo de conservación para el buzón de correo. 

    ```
    Set-Mailbox <username> -ElcProcessingDisabled $true
    ```

## <a name="step-3-remove-all-holds-from-the-mailbox"></a>Paso 3: Quitar todas las suspensiones desde el buzón de correo

El último paso antes de eliminar los elementos de la carpeta elementos recuperables es quitar todas las suspensiones (que ha identificado en el paso 1) colocadas en el buzón de correo. Todas las suspensiones deben quitarse para que no se conservan los elementos después de eliminarlos de la carpeta elementos recuperables. Las secciones siguientes contienen información sobre cómo quitar distintos tipos de suspensiones en un buzón de correo. Vea la sección [obtener más información](#more-information) para obtener sugerencias sobre cómo identificar la suspensión de tipo que se puede incluir en un buzón de correo. 
  
> [!CAUTION]
> Como se señaló anteriormente, compruebe con la administración de registros o departamentos legales antes de quitar una suspensión de un buzón de correo. 
  
 ### <a name="litigation-hold"></a>Retención por juicio
  
Ejecute el siguiente comando en Exchange Online PowerShell para quitar un juicio desde el buzón de correo.

```
Set-Mailbox <username> -LitigationHoldEnabled $false
```

   
> [!NOTE]
> Al igual que la deshabilitación de los métodos de acceso de cliente y la recuperación de elemento único, puede tardar hasta 60 minutos para quitar la suspensión por litigio. No eliminar elementos de la carpeta elementos recuperables hasta que haya transcurrido este período. 
  
 ### <a name="in-place-hold"></a>Retención en contexto
  
Ejecute el siguiente comando en Exchange Online PowerShell para identificar la retención local que se coloca en el buzón de correo. Utilice el GUID para la retención local que ha identificado en el paso 1. 

```
Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL Name
```
   
Después de identificar la retención en contexto, puede usar el centro de administración de Exchange (EAC) o Exchange Online PowerShell para quitar el buzón de correo de la suspensión. Para obtener más información, consulte [Create or remove an In-Place Hold](https://go.microsoft.com/fwlink/?linkid=852668).
  
 ### <a name="office-365-retention-policies-applied-to-specific-mailboxes"></a>Directivas de retención 365 Office aplicadas a buzones específicos
  
Ejecute el siguiente comando [Office 365 seguridad &amp; PowerShell de centro de cumplimiento de normas](https://go.microsoft.com/fwlink/?linkid=627084) para identificar la directiva de retención de Office 365 que se aplica a los buzones de correo. Usar el GUID (sin incluir el `mbx` o `skp` prefijo) para la directiva de retención que ha identificado en el paso 1. 

```
Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name
```
   
Después de identificar la directiva de retención, vaya a la **gobernanza de fecha** \> página de **retención** en la seguridad &amp; centro de cumplimiento, editar la directiva de retención que ha identificado en el paso anterior y quitar el buzón de correo de la lista de destinatarios que se incluyen en la directiva de retención. 
  
 ### <a name="organization-wide-office-365-retention-policies"></a>Directivas de retención de Office 365 de toda la organización
  
Toda la organización y las directivas de retención de toda la Exchange Office 365 se aplican a todos los buzones de la organización. Que se aplican en el nivel de organización (no el nivel de buzón de correo) y se devuelven cuando se ejecuta el cmdlet **Get-OrganizationConfig** en el paso 1. Ejecute el siguiente comando [seguridad &amp; PowerShell de centro de cumplimiento de normas](https://go.microsoft.com/fwlink/?linkid=627084) para identificar las directivas de retención de Office 365 de toda la organización. Usar el GUID (sin incluir el `mbx` prefijo) de las directivas de retención de toda la organización que ha identificado en el paso 1. 

```
Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name
```

Después de identificar las directivas de retención de toda la organización Office 365, vaya a la **gobernanza de fecha** \> página de **retención** en la seguridad &amp; centro de cumplimiento, editar cada directiva de retención de toda la organización que ha identificado en el anterior paso y agregar el buzón de correo a la lista de destinatarios excluidos. De esta forma quitará el buzón del usuario de la directiva de retención. 
  
 ### <a name="ediscovery-case-holds"></a>contiene el caso de exhibición de documentos electrónicos
  
Ejecute los siguientes comandos [seguridad &amp; PowerShell de centro de cumplimiento de normas](https://go.microsoft.com/fwlink/?linkid=627084) para identificar la suspensión asociada con un caso de exhibición de documentos electrónicos que se aplica a los buzones de correo. Usar el GUID (sin incluir el `UniH` prefijo) para la exhibición de documentos electrónicos espera que ha identificado en el paso 1. Tenga en cuenta que el segundo comando muestra el nombre de la suspensión está asociada; el caso de exhibición de documentos electrónicos el tercer comando muestra el nombre de la suspensión. 
  
```
$CaseHold = Get-CaseHoldPolicy <hold GUID without prefix>
```

```
Get-ComplianceCase $CaseHold.CaseId | FL Name
```

```
$CaseHold.Name
```

Una vez que ha identificado el nombre del caso de exhibición de documentos electrónicos y la suspensión, vaya a la **búsqueda &amp; investigación** \> página de **exhibición de documentos electrónicos** en la seguridad &amp; centro de cumplimiento, abra el caso y quitar el buzón de correo de la suspensión. Para obtener más información, vea [administrar casos de exhibición de documentos electrónicos en la seguridad de Office 365 &amp; centro de cumplimiento](manage-ediscovery-cases.md).
  
## <a name="step-4-delete-items-in-the-recoverable-items-folder"></a>Paso 4: Eliminar elementos de la carpeta elementos recuperables

Ahora está listo para eliminar realmente los elementos en la carpeta elementos recuperables mediante el cmdlet [Search-Mailbox](https://go.microsoft.com/fwlink/?linkid=852595) en Exchange Online PowerShell. Dispone de tres opciones cuando se ejecuta el cmdlet **Search-Mailbox** . 
  
- Copie los elementos en un buzón de destino antes de eliminar para que puedan consultar los elementos, si es necesario, antes de eliminarlos.
    
- Copie los elementos a un buzón de destino y eliminarlos en el mismo comando.
    
- Eliminar elementos sin copiarlos en un buzón de destino. 
    
Tenga en cuenta que los elementos en la carpeta elementos recuperables en el buzón del usuario archivo principal también se eliminará cuando se ejecuta el ** Search-Mailbox ** cmdlet. Para evitar esto, puede incluir el modificador *DoNotIncludeArchive* . Y como se ha indicado anteriormente, si el archivado de ampliación automática está habilitada para el buzón de correo, la ** Search-Mailbox ** cmdlet no elimina los elementos de un buzón de archivo auxiliar. Para obtener más información acerca de la expansión automática archivar, vea [información general sobre el archivo ilimitado en Office 365](unlimited-archiving.md).
  
> [!NOTE]
> Si incluye una consulta de búsqueda (utilizando el parámetro  *SearchQuery*  ), el cmdlet **Search-Mailbox** devolverá un máximo de 10 000 elementos en los resultados de búsqueda. Por tanto, si incluye una consulta de búsqueda, es posible que deba ejecutar el comando **Search-Mailbox** varias veces para eliminar más de 10 000 elementos. 
  
Los siguientes ejemplos muestran la sintaxis de comando para cada una de estas opciones. Estos ejemplos se usa el `-SearchQuery size>0` valor del parámetro, que elimina todos los elementos de todas las subcarpetas de la carpeta elementos recuperables. Si necesita eliminar sólo los elementos que coinciden con las condiciones específicas, también puede usar el parámetro *SearchQuery* para especificar otras condiciones, como el asunto de un mensaje o un intervalo de fechas. Vea los [otros ejemplos de cómo utilizar el parámetro SearchQuery](#other-examples-of-using-the-searchquery-parameter) que aparece a continuación. 
  
### <a name="example-1"></a>Ejemplo 1

En este ejemplo se copian todos los elementos en la carpeta del usuario elementos recuperables en una carpeta de buzón de búsqueda de detección de la organización. Esto le permite revisar los elementos antes de eliminarlos permanentemente.

```
Search-Mailbox <username> -SearchQuery size>0 -SearchDumpsterOnly -TargetMailbox "Discovery Search Mailbox" -TargetFolder "<foldername>"
```

En el ejemplo anterior, no es necesario para copiar elementos en el buzón de búsqueda de detección. Puede copiar mensajes en cualquier buzón de destino. Sin embargo, para evitar el acceso a datos de buzones potencialmente confidencial, se recomienda copiar los mensajes a un buzón que tiene acceso restringido al personal autorizado. De forma predeterminada, acceso al buzón de búsqueda de detección predeterminado está restringido a los miembros del grupo de roles de administración de detección en Exchange Online. 
  
### <a name="example-2"></a>Ejemplo 2

En este ejemplo se copian todos los elementos de la carpeta del usuario elementos recuperables en una carpeta de buzón de búsqueda de detección de la organización y, a continuación, eliminan los elementos de la carpeta del usuario elementos recuperables.

```
Search-Mailbox <username> -SearchQuery size>0 -SearchDumpsterOnly -TargetMailbox "Discovery Search Mailbox" -TargetFolder "<foldername>" -DeleteContent
```
 
### <a name="example-3"></a>Ejemplo 3

En este ejemplo se eliminan todos los elementos de la carpeta del usuario elementos recuperables, sin copiarlos a un buzón de destino. 

```
Search-Mailbox <username> -SearchQuery size>0 -SearchDumpsterOnly -DeleteContent
```

### <a name="other-examples-of-using-the-searchquery-parameter"></a>Otros ejemplos de cómo utilizar el parámetro SearchQuery

A continuación presentamos algunos ejemplos de usar el parámetro *SearchQuery* para buscar mensajes específicos. Si usa el parámetro *SearchQuery* para buscar elementos específicos, considere la posibilidad de copiar los resultados de búsqueda en un buzón de destino para que pueda revisar los resultados de búsqueda y, a continuación, revise la consulta si es necesario antes de eliminar los resultados de una búsqueda. 
  
En este ejemplo se devuelve los mensajes que contienen una frase específica en el campo Asunto.
  
```
SearchQuery 'subject:"MAIL_BOX VALIDATION/UPGRADE!!!"' 
```

En este ejemplo se devuelve los mensajes que se enviaron dentro del intervalo de fechas especificado.
  
```
SearchQuery 'sent>=06/01/2016 AND sent<=09/01/2016'
```
 
En este ejemplo se devuelve los mensajes que se han enviado a la persona especificada.

```
SearchQuery 'to:garthf@alpinehouse.com'
```
   
### <a name="verify-that-items-were-deleted"></a>Compruebe que los elementos eliminados

Para comprobar que se han eliminado correctamente los elementos desde la carpeta elementos recuperables de un buzón de correo, usar el cmdlet de **Get-MailboxFolderStatistics** en Exchange Online PowerShell para comprobar el tamaño y el número de elementos en la carpeta elementos recuperables. Se pueden comparar estas estadísticas con los que se recopilan en el paso 1. 
  
Ejecute el siguiente comando para obtener el tamaño actual y el número total de elementos en carpetas y subcarpetas en la carpeta elementos recuperables en el buzón del usuario principal. 
  
```
Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
```
   
Ejecute el siguiente comando para obtener el tamaño y el número total de elementos en carpetas y subcarpetas en la carpeta elementos recuperables en el buzón de archivo del usuario. 

```
Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems -Archive | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
```
  
## <a name="step-5-revert-the-mailbox-to-its-previous-state"></a>Paso 5: Revertir el buzón de correo a su estado anterior

El paso final consiste en revertir el buzón de correo a su configuración anterior. Esto significa restablecer las propiedades que ha cambiado en el paso 2 y volver a aplicar las suspensiones que se quitan en el paso 3. Esto incluye:
  
- Cambiar el período de retención de elementos eliminados copia a su valor anterior. Como alternativa, se puede deje esta opción establecida en 30 días, el valor máximo en Exchange Online.
    
- Volver a habilitar la recuperación de elemento único.
    
- Volver a habilitar los métodos de acceso de cliente para que el propietario puede tener acceso a su buzón.
    
- Volver a aplicar las directivas de retención de Office 365 que se haya quitado y suspensiones.
    
- Volver a habilitar el Asistente para carpeta administrada para procesar el buzón de correo.
    
> [!IMPORTANT]
> Se recomienda que espere 24 horas después de volver a aplicar una suspensión u Office 365 retención directiva (y bien, comprobar que sea en contexto) antes de volver a habilitar el Asistente para carpeta administrada para procesar el buzón de correo. 
  
Realice los pasos siguientes (en la secuencia especificada) en Exchange Online PowerShell.
  
1. Ejecutar el comando siguiente para cambiar el período de retención de elementos eliminados se copia a su valor original. Esto supone que la configuración anterior es inferior a 30 días; Por ejemplo, 14 días. 
    
    ```
    Set-Mailbox <username> -RetainDeletedItemsFor 14
    ```
   
2. Ejecute el siguiente comando para volver a habilitar la recuperación de elemento único.
   
    ```
    Set-Mailbox <username> -SingleItemRecoveryEnabled $true
    ```

3. Ejecute el siguiente comando para volver a habilitar todos los métodos de acceso de cliente para el buzón de correo.
    
    ```
    Set-CASMailbox <username> -EwsEnabled $true -ActiveSyncEnabled $true -MAPIEnabled $true -OWAEnabled $true -ImapEnabled $true -PopEnabled $true
    ```
   
4. Volver a aplicar las suspensiones que se quitan en el paso 3. Según el tipo de espera, use uno de los procedimientos siguientes.
    
    **Retención por juicio**
    
    Ejecute el siguiente comando para volver a habilitar un juicio para el buzón de correo.
    
    ```
    Set-Mailbox <username> -LitigationHoldEnabled $true
    ```

    **In-Place Hold**
    
    Use el CEF (o Exchange Online PowerShell) para volver a agregar el buzón de correo a la retención local. 
    
    **Directivas de retención 365 Office aplicadas a buzones específicos**
    
    Usar la seguridad &amp; centro de cumplimiento volver a agregar el buzón de correo a la directiva de retención de Office 365. Vaya a la **gobernanza de fecha** \> página de **retención** en la seguridad &amp; centro de cumplimiento, editar la directiva de retención y agregar el buzón de correo a la lista de destinatarios que se aplica la directiva de retención. 
    
    **Directivas de retención de Office 365 de toda la organización**
    
    Si elimina una directiva de retención de toda la Exchange o de toda la organización mediante la exclusión de la directiva, a continuación, usar la seguridad &amp; excluidos de centro de cumplimiento para quitar el buzón de correo de la lista de los usuarios. Vaya a la **gobernanza de fecha** \> página de **retención** en la seguridad &amp; centro de cumplimiento, editar la directiva de retención de toda la organización y quitar el buzón de correo de la lista de destinatarios excluidos. De esta forma volver a aplicar la directiva de retención para el buzón del usuario. 
    
    **contiene el caso de exhibición de documentos electrónicos**
    
    Usar la seguridad &amp; centro de cumplimiento para agregar el buzón de hacer una copia de la suspensión a la que está asociado con un caso de exhibición de documentos electrónicos. Vaya a la **búsqueda &amp; investigación** \> página de **exhibición de documentos electrónicos** en la seguridad &amp; centro de cumplimiento, abra el caso y vuelva a agregar el buzón de correo a la suspensión. 
    
5. Ejecute el siguiente comando para permitir que el Asistente para carpeta administrada volver a procesar el buzón de correo. Como se mencionó anteriormente, se recomienda que espere 24 horas después de volver a aplicar una suspensión u Office 365 retención directiva (y bien, comprobar que sea en contexto) antes de volver a habilitar el Asistente para carpeta administrada. 

    ```
    Set-Mailbox <username> -ElcProcessingDisabled $false
    ```
   
6. Para comprobar que el buzón de correo se ha revertido a su configuración anterior, puede ejecutar los siguientes comandos y, a continuación, compare la configuración a los que se recopilan en el paso 1.

    ```
    Get-Mailbox <username> | FL ElcProcessingDisabled,InPlaceHolds,LitigationHoldEnabled,RetainDeletedItemsFor,SingleItemRecoveryEnabled
    ```

    ```
    Get-CASMailbox <username> | FL EwsEnabled,ActiveSyncEnabled,MAPIEnabled,OWAEnabled,ImapEnabled,PopEnabled
    ```
  
## <a name="more-information"></a>Más información

Aquí es una tabla que describe cómo identificar diferentes tipos de suspensiones según los valores de la propiedad *InPlaceHolds* al ejecutar los cmdlets **Get-Mailbox** o **Get-OrganizationConfig** . Como ya se explica, tiene que quitar todas las suspensiones y las directivas de retención de Office 365 desde un buzón de correo antes de que pueden eliminar correctamente los elementos en la carpeta elementos recuperables. 
  
|**Tipo de suspensión**|**Valor de ejemplo**|**Cómo identificar la suspensión**|
|:-----|:-----|:-----|
|Retención por juicio  <br/> | `True` <br/> |La propiedad *LitigationHoldEnabled* está establecida en `True`.  <br/> |
|Retención en contexto  <br/> | `c0ba3ce811b6432a8751430937152491` <br/> |La propiedad *InPlaceHolds* contiene el GUID de la retención local que se coloca en el buzón de correo. Puede saber que esto es una retención local debido a que el GUID no se inicia con un prefijo.<br/> Puede usar la ' Get-MailboxSearch - InPlaceHoldIdentity<hold GUID> | FL' command en Exchange Online PowerShell para obtener información acerca de la retención local en el buzón de correo.  <br/> |
| Las directivas de retención de Office 365 en la seguridad &amp; centro de cumplimiento que se aplican a buzones específicos  <br/> | `mbxcdbbb86ce60342489bff371876e7f224` <br/> o  <br/>  `skp127d7cf1076947929bf136b7a2a8c36f` <br/> |Cuando se ejecuta el cmdlet **Get-Mailbox** , la propiedad *InPlaceHolds* contiene también las directivas de retención de los GUID de Office 365 aplicadas al buzón. Puede identificar las directivas de retención porque el GUID comienza por la `mbx` prefijo. Tenga en cuenta que si el GUID de la directiva de retención se inicia con el `skp` prefijo, que indica que se aplica la directiva de retención a Skype para conversaciones de negocios.<br/> En directiva de retención de Office 365 de identidad que se aplica a los buzones de correo, ejecute el siguiente comando en seguridad &amp; PowerShell de centro de cumplimiento: <br/> <br/>' Get-RetentionCompliancePolicy<retention policy GUID without prefix> | Nombre de FL`<br/><br/>Be sure to remove the  `los buzones` or  `skp' prefijo al ejecutar este comando.  <br/> |
|Las directivas de retención de Office 365 de toda la organización en la seguridad &amp; centro de cumplimiento  <br/> |Ningún valor  <br/> o  <br/>  `-mbxe9b52bf7ab3b46a286308ecb29624696`(indica que el buzón de correo está excluido de una directiva de toda la organización)  <br/> |Incluso si la propiedad *InPlaceHolds* está vacía cuando se ejecuta el cmdlet **Get-Mailbox** , aún puede haber uno o más toda la organización Office 365 aplicadas políticas de retención para el buzón de correo.  <br/> Para comprobar esto, puede ejecutar el ' Get-OrganizationConfig | FL InPlaceHolds` command in Exchange Online PowerShell to get a list of the GUIDs for organization-wide Office 365 retention policies. The GUID for organization-wide retention policies applied to Exchange mailboxes start with the  `los buzones` prefix; for example  `mbxa3056bb15562480fadb46ce523ff7b02`.  <br/> To identity the organization-wide Office 365 retention policy that's applied to the mailbox, run the following command in Security &amp; Compliance Center PowerShell: <br/><br/> `Get-RetentionCompliancePolicy<retention policy GUID without prefix> | Nombre de FL`<br/><br/>Note that if a mailbox is excluded from an organization-wide Office 365 retention policy, the GUID for the retention policy is displayed in the  *InPlaceHolds*  property of the user's mailbox when you run the **Get-Mailbox** cmdlet; it's identified by the prefix  `los buzones -`; for example,  `-mbxe9b52bf7ab3b46a286308ecb29624696' <br/> |
|conservación de caso de exhibición de documentos electrónicos en la seguridad &amp; centro de cumplimiento  <br/> | `UniH7d895d48-7e23-4a8d-8346-533c3beac15d` <br/> |La propiedad *InPlaceHolds* también contiene el GUID de cualquier suspensión asociado con un caso de exhibición de documentos electrónicos en la seguridad &amp; centro de cumplimiento que se puede colocar en el buzón de correo. Puede saber esto es una suspensión de casos de exhibición de documentos electrónicos porque el GUID comienza por la `UniH` prefijo.<br/> Puede usar el `Get-CaseHoldPolicy` cmdlet en seguridad &amp; PowerShell de centro de cumplimiento para obtener información sobre el caso de exhibición de documentos electrónicos que está asociada la suspensión en el buzón de correo. Por ejemplo, puede ejecutar el comando ' Get-CaseHoldPolicy<hold GUID without prefix> | Nombre de FL` to display the name of the case hold that's on the mailbox. Be sure to remove the  `UniH` prefix when you run this command.  <br/><br/> To identity the eDiscovery case that the hold on the mailbox is associated with, run the following commands:<br/><br/>`$CaseHold = Get-CaseHoldPolicy <hold GUID without prefix> `<br/><br/>`$CaseHold.CaseId Get-ComplianceCase | Nombre de FL'


