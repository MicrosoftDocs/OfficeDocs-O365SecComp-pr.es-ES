---
title: Eliminar elementos de la carpeta elementos recuperables de buzones de correo basados en la nube en suspensión-ayuda de administración
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: a85e1c87-a48e-4715-bfa9-d5275cde67b0
description: 'Para los administradores: Elimine los elementos de la carpeta elementos recuperables de un usuario para un buzón de correo de Exchange Online, incluso si el buzón se encuentra en retención legal. Esta es una forma eficaz de eliminar datos que se han derramado accidentalmente en Office 365.'
ms.openlocfilehash: 9da469af900c2610762338029aa80d31c7f10363
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/17/2019
ms.locfileid: "34150412"
---
# <a name="delete-items-in-the-recoverable-items-folder-of-cloud-based-mailboxes-on-hold---admin-help"></a>Eliminar elementos de la carpeta elementos recuperables de buzones de correo basados en la nube en suspensión-ayuda de administración

La carpeta elementos recuperables de un buzón de Exchange Online existe para protegerse de eliminaciones accidentales o malintencionadas. También se usa para almacenar elementos que se conservan y a los que acceden las características de cumplimiento de Office 365, como las búsquedas de exhibición de documentos electrónicos y las suspensiones. Sin embargo, en algunos casos, las organizaciones pueden tener datos que se conservan de forma involuntaria en la carpeta elementos recuperables que deben eliminar. Por ejemplo, un usuario podría enviar o reenviar sin saberlo un mensaje de correo electrónico que contenga información confidencial o información que pueda tener consecuencias serias para la empresa. Incluso si el mensaje se elimina de forma permanente, es posible que se retenga indefinidamente, ya que se ha realizado una suspensión legal en el buzón. Este escenario se conoce como derrame de datos porque los datos se han derramado involuntariamente en Office 365. En estas situaciones, puede eliminar los elementos de la carpeta elementos recuperables de un usuario para un buzón de correo de Exchange Online, incluso si ese buzón se coloca en suspensión con una de las diferentes características de retención en Office 365. Estos tipos de retenciones incluyen retenciones por juicio, suspensiones locales, suspensiones de exhibición de documentos electrónicos y directivas de retención de Office 365 creadas en el centro de seguridad y cumplimiento en Office 365 o en Microsoft 365.
  
 En este artículo se explica cómo eliminar elementos de la carpeta elementos recuperables para los buzones de correo basados en la nube que están en suspensión. Este procedimiento implica deshabilitar el acceso al buzón y deshabilitar la recuperación de un único elemento, deshabilitar el Asistente para carpeta administrada para procesar el buzón, quitar temporalmente la retención, eliminar elementos de la carpeta elementos recuperables y, a continuación, revertir el buzón a su configuración anterior. Este es el proceso: 
  
[Paso 1: recopilar información sobre el buzón](#step-1-collect-information-about-the-mailbox)

[Paso 2: preparar el buzón de correo](#step-2-prepare-the-mailbox)

[Paso 3: quitar todas las suspensiones del buzón](#step-3-remove-all-holds-from-the-mailbox)

[Paso 4: quitar la retención por retraso del buzón](#step-4-remove-the-delay-hold-from-the-mailbox)

[Paso 5: eliminar elementos de la carpeta elementos recuperables](#step-5-delete-items-in-the-recoverable-items-folder)

[Paso 6: revertir el buzón a su estado anterior](#step-6-revert-the-mailbox-to-its-previous-state)
  
> [!CAUTION]
> Los procedimientos descritos en este artículo harán que los datos se eliminen de forma permanente (purga) de un buzón de correo de Exchange Online. Esto significa que los mensajes que elimine de la carpeta elementos recuperables no se pueden recuperar y no estarán disponibles para la detección legal o para otros fines de cumplimiento. Si desea eliminar mensajes de un buzón de correo que está en retención como parte de una retención por juicio, la retención local, la retención de eDiscovery o la Directiva de retención de Office 365 creada en el centro de seguridad y cumplimiento, consulte la administración de registros o los departamentos legales. antes de quitar la suspensión. Es posible que su organización tenga una directiva que defina si un buzón de correo en espera o un incidente de derrame de datos tiene prioridad. 
  
## <a name="before-you-begin"></a>Antes de empezar

- Debe tener asignados los siguientes roles de administración en Exchange Online para buscar y eliminar mensajes de la carpeta elementos recuperables en el paso 5.
    
  - **Búsqueda** en buzones: este rol permite buscar buzones de correo en la organización. De forma predeterminada, los administradores de Exchange no tienen asignado este rol. Para asignarse a sí mismo el rol, agréguelo como miembro del grupo de roles de administración de detección en Exchange Online. 
    
  - **Importación y exportación** de buzones: este rol permite eliminar mensajes del buzón de un usuario. De forma predeterminada, este rol no está asignado a ningún grupo de roles. Para eliminar mensajes de los buzones de los usuarios, puede Agregar el rol importación y exportación de buzones al grupo de roles administración de la organización en Exchange Online. 
    
- El procedimiento descrito en este artículo no es compatible con los buzones inactivos. Esto se debe a que no puede volver a aplicar una retención (o una directiva de retención de Office 365) a un buzón inactivo después de quitarlo. Cuando se quita una retención de un buzón inactivo, se cambia a un buzón de correo eliminado temporalmente y se elimina permanentemente de la organización una vez que lo procesa el Asistente para carpeta administrada.
    
- No puede realizar este procedimiento para un buzón que se ha asignado a una directiva de retención de Office 365 que se ha bloqueado con un bloqueo de conservación. Esto se debe a que un bloqueo de conservación impide quitar o excluir el buzón de la Directiva de retención de Office 365 y deshabilitar el Asistente para carpeta administrada en el buzón. Para obtener más información acerca de las directivas de retención de bloqueo, consulte [bloquear una directiva de retención](retention-policies.md#locking-a-retention-policy).
    
- Si un buzón no se coloca en suspensión (o no tiene habilitada la recuperación de un único elemento), simplemente puede eliminar los elementos de la carpeta elementos recuperables. Para obtener más información acerca de cómo hacerlo, vea [Buscar y eliminar mensajes ](https://go.microsoft.com/fwlink/?linkid=852453).
  
## <a name="step-1-collect-information-about-the-mailbox"></a>Paso 1: recopilar información sobre el buzón

El primer paso consiste en recopilar propiedades seleccionadas del buzón de destino que afectarán a este procedimiento. Asegúrese de anotar esta configuración o guardarla en un archivo de texto, ya que cambiará algunas de estas propiedades y, a continuación, revertirá a los valores originales en el paso 6 después de eliminar elementos de la carpeta elementos recuperables. Esta es una lista de las propiedades de buzón que debe recopilar.
  
-  *SingleItemRecoveryEnabled* y *RetainDeletedItemsFor* ; Si es necesario, deshabilitará la recuperación única y aumentará el período de retención de elementos eliminados en el paso 3. 
    
-  *LitigationHoldEnabled* y *InPlaceHolds* ; debe identificar todas las suspensiones colocadas en el buzón de modo que pueda quitarlas temporalmente en el paso 3. Consulte la sección [More Information](#more-information) para obtener sugerencias sobre cómo identificar la suspensión de tipo que se puede colocar en un buzón. 
    
Además, debe obtener la configuración de acceso de cliente de buzones de correo para que pueda deshabilitarla temporalmente de modo que el propietario (u otros usuarios) no pueda obtener acceso al buzón durante este procedimiento. Por último, puede obtener el tamaño actual y el número de elementos en la carpeta elementos recuperables. Después de eliminar los elementos de la carpeta elementos recuperables en el paso 5, usará esta información para comprobar que los elementos se quitaron realmente.
  
1. [Conexión al PowerShell de Exchange Online](https://go.microsoft.com/fwlink/?linkid=396554). Asegúrese de usar un nombre de usuario y una contraseña para una cuenta de administrador a la que se haya asignado el rol de administración adecuado en Exchange Online. 
    
2. Ejecute el siguiente comando para obtener información sobre la recuperación de elementos individuales y el período de retención de elementos eliminados.

    ```
    Get-Mailbox <username> | FL SingleItemRecoveryEnabled,RetainDeletedItemsFor
    ```

   Si la recuperación de un único elemento está habilitada, deberá deshabilitarla en el paso 2. Si el período de retención de elementos eliminados no está establecido en 30 días (el valor máximo en Exchange Online), puede aumentarlo en el paso 2. 
    
3. Ejecute el siguiente comando para obtener la configuración de acceso al buzón del buzón. 
    
    ```
    Get-CASMailbox <username> | FL EwsEnabled,ActiveSyncEnabled,MAPIEnabled,OWAEnabled,ImapEnabled,PopEnabled
    ```

   Deshabilitará todos estos métodos de acceso en el paso 2.
    
4. Ejecute el siguiente comando para obtener información sobre las suspensiones y las directivas de retención de Office 365 que se aplican al buzón.
    
    ```
    Get-Mailbox <username> | FL LitigationHoldEnabled,InPlaceHolds
    ```


   > [!TIP]
    > Si hay demasiados valores en la propiedad *InPlaceHolds* y no todos ellos se muestran, puede ejecutar el `Get-Mailbox <username> | Select-Object -ExpandProperty InPlaceHolds` comando para mostrar cada valor en una línea independiente. 
  
5. Ejecute el siguiente comando para obtener información sobre cualquier directiva de retención de Office 365 de toda la organización. 

    ```
    Get-OrganizationConfig | FL InPlaceHolds
    ```
   Si su organización tiene cualquier directiva de retención de Office 365 de toda la organización, tendrá que excluir el buzón de correo de estas directivas en el paso 3.

   > [!TIP]
    > Si hay demasiados valores en la propiedad *InPlaceHolds* y no todos ellos se muestran, puede ejecutar el `Get-OrganizationConfig | Select-Object -ExpandProperty InPlaceHolds` comando para mostrar cada valor en una línea independiente. 
  
6. Ejecute el siguiente comando para obtener el tamaño actual y el número total de elementos de carpetas y subcarpetas en la carpeta elementos recuperables del buzón de correo principal del usuario. 

    ```
    Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
    ```

   Si el buzón de archivo del usuario está habilitado, ejecute el siguiente comando para obtener el tamaño y el número total de elementos de las carpetas y subcarpetas de la carpeta elementos recuperables de su buzón de archivo. 

    ```s
    Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems -Archive | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
    ```

   Al eliminar elementos en el paso 5, puede optar por eliminar o no eliminar los elementos de la carpeta elementos recuperables en el buzón de archivo principal del usuario. Tenga en cuenta que si el archivado de expansión automática está habilitado para el buzón de correo, los elementos de un buzón de archivo auxiliar no se eliminarán.
  
## <a name="step-2-prepare-the-mailbox"></a>Paso 2: preparar el buzón de correo

Después de recopilar y guardar información sobre el buzón de correo, el siguiente paso consiste en preparar el buzón realizando las siguientes tareas: 
  
- **Deshabilite el acceso del cliente al buzón** de correo para que el propietario del buzón no pueda obtener acceso a su buzón y realice cambios en los datos del buzón durante este procedimiento. 
    
- **Aumente el período de retención** de elementos eliminados a 30 días (el valor máximo en Exchange Online) para que los elementos no se purguen de la carpeta elementos recuperables antes de que pueda eliminarlos en el paso 5. 
    
- **Deshabilite la recuperación** de elementos individuales para que los elementos no se conserven (durante el período de retención del elemento eliminado) después de eliminarlos de la carpeta elementos recuperables en el paso 5. 
    
- **Deshabilite el Asistente para carpeta administrada** para que no procese el buzón y conserve los elementos que eliminó en el paso 5. 
    
Realice los siguientes pasos en Exchange Online PowerShell.
  
1. Ejecute el siguiente comando para deshabilitar el acceso de cliente al buzón. La sintaxis del comando presupone que todos los métodos de acceso de cliente están habilitados en el buzón.

    ```   
    Set-CASMailbox <username> -EwsEnabled $false -ActiveSyncEnabled $false -MAPIEnabled $false -OWAEnabled $false -ImapEnabled $false -PopEnabled $false
    ```
   
   > [!NOTE]
    > La deshabilitación de todos los métodos de acceso de cliente al buzón puede tardar hasta 60 minutos. Tenga en cuenta que, al deshabilitar estos métodos de acceso, no se desconectará el propietario del buzón en el que está actualmente conectado. Si el propietario no ha iniciado sesión, no podrá tener acceso a su buzón una vez que estos métodos de acceso estén deshabilitados. 
  
2. Ejecute el siguiente comando para aumentar el período de retención de elementos eliminados durante 30 días como máximo. Se supone que la configuración actual es inferior a 30 días. 

    ```
    Set-Mailbox <username> -RetainDeletedItemsFor 30
    ```

3. Ejecute el siguiente comando para deshabilitar la recuperación de elementos individuales.
    
    ```
    Set-Mailbox <username> -SingleItemRecoveryEnabled $false
    ```

   > [!NOTE]
    > La deshabilitación de la recuperación de elementos individuales puede tardar hasta 60 minutos. No elimine elementos de la carpeta elementos recuperables hasta que haya transcurrido este período. 
  
4. Ejecute el siguiente comando para evitar que el Asistente para carpeta administrada procese el buzón de correo. Como se ha explicado anteriormente, puede deshabilitar el Asistente para carpeta administrada solo si una directiva de retención de Office 365 con un bloqueo de conservación no se aplica al buzón. 

    ```
    Set-Mailbox <username> -ElcProcessingDisabled $true
    ```

## <a name="step-3-remove-all-holds-from-the-mailbox"></a>Paso 3: quitar todas las suspensiones del buzón

El último paso para poder eliminar elementos de la carpeta elementos recuperables es quitar todas las suspensiones (identificado en el paso 1) colocados en el buzón. Todas las suspensiones deben quitarse para que los elementos no se conserven después de eliminarlos de la carpeta elementos recuperables. Las secciones siguientes contienen información sobre cómo quitar distintos tipos de retenciones en un buzón. Consulte la sección [More Information](#more-information) para obtener sugerencias sobre cómo identificar la suspensión de tipo que se puede colocar en un buzón. Para obtener más información, consulte [How to identify The Type of Hold in a Exchange Online Mailbox](identify-a-hold-on-an-exchange-online-mailbox.md).
  
> [!CAUTION]
> Como se indicó anteriormente, consulte con la administración de registros o los departamentos jurídicos antes de quitar una retención de un buzón de correo. 
  
 ### <a name="litigation-hold"></a>Retención por juicio
  
Ejecute el siguiente comando en Exchange Online PowerShell para quitar una retención por juicio del buzón.

```
Set-Mailbox <username> -LitigationHoldEnabled $false
```

   
> [!NOTE]
> De forma similar a la deshabilitación de los métodos de acceso de cliente y la recuperación de elementos individuales, puede tardar hasta 60 minutos en quitar la retención por juicio. No elimine elementos de la carpeta elementos recuperables hasta que haya transcurrido este período. 
  
 ### <a name="in-place-hold"></a>Retención en contexto
  
Ejecute el siguiente comando en Exchange Online PowerShell para identificar la conservación local que está colocada en el buzón. Use el GUID de la retención local que identificó en el paso 1. 

```
Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL Name
```
   
Después de identificar la conservación local, puede usar el centro de administración de Exchange (EAC) o Exchange Online PowerShell para quitar el buzón de la retención. Para obtener más información, vea [crear o quitar una conservación local](https://go.microsoft.com/fwlink/?linkid=852668).
  
 ### <a name="office-365-retention-policies-applied-to-specific-mailboxes"></a>Directivas de retención de Office 365 aplicadas a buzones específicos
  
Ejecute el siguiente comando en [Security _AMP_ Compliance Center PowerShell](https://go.microsoft.com/fwlink/?linkid=627084) para identificar la Directiva de retención de Office 365 que se aplica al buzón. Use el GUID (sin incluir el `mbx` prefijo o `skp` ) para la Directiva de retención que identificó en el paso 1. 

```
Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name
```
   
Después de identificar la Directiva de retención, vaya a la página **retención** de **gobierno** \> de fecha en el centro de seguridad & cumplimiento, edite la Directiva de retención que identificó en el paso anterior y quite el buzón de la lista de destinatarios que se incluyen en la Directiva de retención. 
  
 ### <a name="organization-wide-office-365-retention-policies"></a>Directivas de retención de Office 365 de toda la organización
  
Las directivas de retención de Office 365 de toda la organización y de Exchange se aplican a todos los buzones de la organización. Se aplican en el nivel de la organización (no en el de buzón de correo) y se devuelven al ejecutar el cmdlet **Get-OrganizationConfig** en el paso 1. Ejecute el siguiente comando en [Security _AMP_ Compliance Center PowerShell](https://go.microsoft.com/fwlink/?linkid=627084) para identificar las directivas de retención de Office 365 de toda la organización. Use el GUID (sin incluir el `mbx` prefijo) para las directivas de retención de toda la organización que identificó en el paso 1. 

```
Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name
```

Después de identificar las directivas de retención de Office 365 de toda la organización, vaya a la página de **retención** de **gobierno** \> de fecha en el centro de seguridad & cumplimiento, edite cada directiva de retención de toda la organización que identificó en el paso anterior y agregue el buzón a la lista de destinatarios excluidos. Al hacerlo, se quitará el buzón de correo del usuario de la Directiva de retención. 

### <a name="office-365-retention-labels"></a>Etiquetas de retención de Office 365

Cuando un usuario aplica una etiqueta configurada para conservar contenido o conservar y, a continuación, eliminar el contenido en cualquier carpeta o elemento de su buzón de correo, la propiedad de buzón *ComplianceTagHoldApplied* se establece en **true**. Cuando esto ocurre, se considera que el buzón está en espera, como si se hubiera puesto en retención por juicio o asignado a una directiva de retención de Office 365.

Para ver el valor de la propiedad *ComplianceTagHoldApplied* , ejecute el siguiente comando en Exchange Online PowerShell:

```
Get-Mailbox <username> |FL ComplianceTagHoldApplied
```

Una vez que haya identificado que un buzón está en suspensión debido a que se aplica una etiqueta de retención a una carpeta o a un elemento, puede usar la herramienta de búsqueda de contenido en el centro de seguridad y cumplimiento para buscar los elementos etiquetados mediante la condición de búsqueda ComplianceTag. Para obtener más información, vea la sección "condiciones de búsqueda" en [consultas de palabras clave y condiciones de búsqueda para la búsqueda de contenido](keyword-queries-and-search-conditions.md#conditions-for-common-properties).

Para obtener más información acerca de las etiquetas, vea [información general sobre las etiquetas de Office 365](labels.md).

 ### <a name="ediscovery-case-holds"></a>suspensiones de casos de eDiscovery
  
Ejecute los siguientes comandos en [Security _AMP_ Compliance Center PowerShell](https://go.microsoft.com/fwlink/?linkid=627084) para identificar la retención asociada con un caso de exhibición de documentos electrónicos que se aplica al buzón. Use el GUID (sin incluir el `UniH` prefijo) para la suspensión de exhibición de documentos electrónicos que identificó en el paso 1. Tenga en cuenta que el segundo comando muestra el nombre del caso de eDiscovery con el que está asociada la retención; el tercer comando muestra el nombre de la suspensión. 
  
```
$CaseHold = Get-CaseHoldPolicy <hold GUID without prefix>
```

```
Get-ComplianceCase $CaseHold.CaseId | FL Name
```

```
$CaseHold.Name
```

Una vez que haya identificado el nombre del caso de eDiscovery y la retención, vaya a **** \> la página eDiscovery **eDiscovery** en el centro de cumplimiento, abra el caso y quite el buzón de la retención. Para obtener más información, vea [casos de eDiscovery](ediscovery-cases.md).
  
## <a name="step-4-remove-the-delay-hold-from-the-mailbox"></a>Paso 4: quitar la retención por retraso del buzón

Una vez que se quita cualquier tipo de retención de un buzón, el valor de la propiedad de buzón *DelayHoldApplied* se establece en **true**. Esto ocurre la próxima vez que el Asistente para carpeta administrada procesa el buzón de correo y detecta que se ha quitado una suspensión. Esto se denomina retenciones en *espera* y significa que la eliminación real de la retención se retrasa durante 30 días para impedir que los datos se eliminen de forma permanente del buzón. (El propósito de una retención retrasada es proporcionar a los administradores una oportunidad para buscar o recuperar los elementos del buzón que se purgarán después de que se quite una retención).  Cuando se coloca una retención en el buzón, el buzón sigue considerándose en espera durante un período de tiempo ilimitado, como si el buzón estuviera en retención por juicio. Transcurrido el plazo de 30 días, la retención en espera expira y Office 365 intentará quitar la retención retrasada automáticamente (estableciendo la propiedad *DelayHoldApplied* en **false**) para que la retención se elimine realmente. 

Para poder eliminar elementos en el paso 5, debe quitar la retención por retraso del buzón. En primer lugar, determine si la retención de retraso se aplica al buzón ejecutando el siguiente comando en Exchange Online PowerShell:

```
Get-Mailbox <username> | FL DelayHoldApplied
```

Si el valor de la propiedad *DelayHoldApplied* se establece en **false**, no se ha colocado una suspensión de retraso en el buzón. Puede ir al paso 5 y eliminar los elementos de la carpeta elementos recuperables.

Si el valor de la propiedad *DelayHoldApplied* está establecido en **true**, ejecute el siguiente comando para quitar la retención por retraso:

```
Set-Mailbox <username> -RemoveDelayHoldApplied
```
Tenga en cuenta que debe tener asignado el rol retención legal en Exchange Online para usar el parámetro *RemoveDelayHoldApplied* .

## <a name="step-5-delete-items-in-the-recoverable-items-folder"></a>Paso 5: eliminar elementos de la carpeta elementos recuperables

Ahora está listo para eliminar realmente los elementos de la carpeta elementos recuperables con el cmdlet [Search-Mailbox](https://go.microsoft.com/fwlink/?linkid=852595) en Exchange Online PowerShell. Tiene tres opciones al ejecutar el cmdlet **Search-Mailbox** . 
  
- Copie los elementos en un buzón de destino antes de eliminarlos para poder revisar los elementos, si es necesario, antes de eliminarlos.
    
- Copiar elementos en un buzón de correo de destino y eliminarlos en el mismo comando.
    
- Eliminar elementos sin copiarlos en un buzón de correo de destino. 
    
Tenga en cuenta que los elementos de la carpeta elementos recuperables del buzón de archivo principal del usuario también se eliminarán cuando ejecute el cmdlet **Search-Mailbox** . Para evitarlo, puede incluir el cambio  *DoNotIncludeArchive*  . Y como se mencionó anteriormente, si el archivado de expansión automática está habilitado para el buzón de correo, el cmdlet * * Search-Mailbox * * no elimina los elementos de un buzón de archivo auxiliar. Para obtener más información acerca del archivo de expansión automática, vea [información general sobre el archivado ilimitado en Office 365](unlimited-archiving.md).
  
> [!NOTE]
> Si incluye una consulta de búsqueda (utilizando el parámetro  *SearchQuery*  ), el cmdlet **Search-Mailbox** devolverá un máximo de 10 000 elementos en los resultados de búsqueda. Por tanto, si incluye una consulta de búsqueda, es posible que deba ejecutar el comando **Search-Mailbox** varias veces para eliminar más de 10 000 elementos. 
  
En los ejemplos siguientes se muestra la sintaxis de comandos para cada una de estas opciones. En estos ejemplos se `-SearchQuery size>0` usa el valor de parámetro, que elimina todos los elementos de todas las subcarpetas de la carpeta elementos recuperables. Si necesita eliminar solo elementos que coinciden con condiciones específicas, también puede usar el parámetro *SearchQuery* para especificar otras condiciones, como el asunto de un mensaje o un intervalo de fechas. Vea los [otros ejemplos de cómo usar el parámetro SearchQuery](#other-examples-of-using-the-searchquery-parameter) a continuación. 
  
### <a name="example-1"></a>Ejemplo 1

En este ejemplo se copian todos los elementos de la carpeta elementos recuperables del usuario en una carpeta del buzón de búsqueda de detección de la organización. Esto le permite revisar los elementos antes de eliminarlos de forma permanente.

```
Search-Mailbox <username> -SearchQuery size>0 -SearchDumpsterOnly -TargetMailbox "Discovery Search Mailbox" -TargetFolder "<foldername>"
```

En el ejemplo anterior, no es necesario copiar elementos en el buzón de búsqueda de detección. Puede copiar mensajes en cualquier buzón de correo de destino. Sin embargo, para impedir el acceso a datos de buzones potencialmente confidenciales, se recomienda copiar los mensajes a un buzón de correo que tenga acceso restringido al personal autorizado. De forma predeterminada, el acceso al buzón de búsqueda de detección predeterminado está restringido a los miembros del grupo de roles de administración de detección en Exchange Online. 
  
### <a name="example-2"></a>Ejemplo 2

En este ejemplo se copian todos los elementos de la carpeta elementos recuperables del usuario en una carpeta del buzón de búsqueda de detección de la organización y, a continuación, se eliminan los elementos de la carpeta elementos recuperables del usuario.

```
Search-Mailbox <username> -SearchQuery size>0 -SearchDumpsterOnly -TargetMailbox "Discovery Search Mailbox" -TargetFolder "<foldername>" -DeleteContent
```
 
### <a name="example-3"></a>Ejemplo 3

En este ejemplo se eliminan todos los elementos de la carpeta elementos recuperables del usuario, sin copiarlos en un buzón de destino. 

```
Search-Mailbox <username> -SearchQuery size>0 -SearchDumpsterOnly -DeleteContent
```

### <a name="other-examples-of-using-the-searchquery-parameter"></a>Otros ejemplos de cómo usar el parámetro SearchQuery

A continuación se muestran algunos ejemplos de cómo usar el parámetro *SearchQuery* para buscar mensajes específicos. Si usa el parámetro *SearchQuery* para buscar elementos específicos, considere la posibilidad de copiar los resultados de la búsqueda en un buzón de correo de destino para poder revisar los resultados de la búsqueda y, a continuación, revisar la consulta si es necesario antes de eliminar los resultados de una búsqueda. 
  
En este ejemplo se devuelven los mensajes que contienen una frase específica en el campo Subject.
  
```
SearchQuery 'subject:"MAIL_BOX VALIDATION/UPGRADE!!!"' 
```

En este ejemplo se devuelven los mensajes enviados en el intervalo de fechas especificado.
  
```
SearchQuery 'sent>=06/01/2016 AND sent<=09/01/2016'
```
 
En este ejemplo se devuelven los mensajes que se enviaron a la persona especificada.

```
SearchQuery 'to:garthf@alpinehouse.com'
```
   
### <a name="verify-that-items-were-deleted"></a>Comprobar que los elementos se han eliminado

Para comprobar si eliminó correctamente los elementos de la carpeta elementos recuperables de un buzón, use el cmdlet **Get-MailboxFolderStatistics** de PowerShell de Exchange Online para comprobar el tamaño y el número de elementos en la carpeta elementos recuperables. Puede comparar estas estadísticas con las que recopiló en el paso 1. 
  
Ejecute el siguiente comando en para obtener el tamaño actual y el número total de elementos de carpetas y subcarpetas en la carpeta elementos recuperables del buzón de correo principal del usuario. 
  
```
Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
```
   
Ejecute el siguiente comando para obtener el tamaño y el número total de elementos de carpetas y subcarpetas en la carpeta elementos recuperables del buzón de archivo del usuario. 

```
Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems -Archive | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
```
  
## <a name="step-6-revert-the-mailbox-to-its-previous-state"></a>Paso 6: revertir el buzón a su estado anterior

El último paso consiste en revertir el buzón a la configuración anterior. Esto significa restablecer las propiedades que cambió en el paso 2 y volver a aplicar las suspensiones que quitó en el paso 3. Esto incluye:
  
- Cambiar el período de retención de elementos eliminados de nuevo a su valor anterior. Como alternativa, puede dejar este conjunto en 30 días, el valor máximo en Exchange Online.
    
- Volver a habilitar la recuperación de elementos individuales.
    
- Volver a habilitar los métodos de acceso de cliente para que el propietario pueda obtener acceso a sus buzones.
    
- Volver a aplicar las suspensiones y las directivas de retención de Office 365 que quitó.
    
- Volver a habilitar el Asistente para carpeta administrada para procesar el buzón de correo.
    
> [!IMPORTANT]
> Le recomendamos que espere 24 horas después de volver a aplicar una retención o una directiva de retención de Office 365 (y comprobar que se ha implementado) antes de volver a habilitar el Asistente para la carpeta administrada para procesar el buzón. 
  
Realice los siguientes pasos (en la secuencia especificada) en Exchange Online PowerShell.
  
1. Ejecute el siguiente comando para volver a cambiar el período de retención de elementos eliminados a su valor original. Se supone que el valor anterior es inferior a 30 días; por ejemplo, 14 días. 
    
    ```
    Set-Mailbox <username> -RetainDeletedItemsFor 14
    ```
   
2. Ejecute el siguiente comando para volver a habilitar la recuperación de un único elemento.
   
    ```
    Set-Mailbox <username> -SingleItemRecoveryEnabled $true
    ```

3. Ejecute el siguiente comando para volver a habilitar todos los métodos de acceso de cliente al buzón.
    
    ```
    Set-CASMailbox <username> -EwsEnabled $true -ActiveSyncEnabled $true -MAPIEnabled $true -OWAEnabled $true -ImapEnabled $true -PopEnabled $true
    ```
   
4. Vuelva a aplicar las suspensiones que quitó en el paso 3. Según el tipo de retención, use uno de los procedimientos siguientes.
    
    **Retención por juicio**
    
    Ejecute el siguiente comando para volver a habilitar una retención por juicio para el buzón.
    
    ```
    Set-Mailbox <username> -LitigationHoldEnabled $true
    ```

    **In-Place Hold**
    
    Use el EAC (o Exchange Online PowerShell) para volver a agregar el buzón a la conservación local. 
    
    **Directivas de retención de Office 365 aplicadas a buzones específicos**
    
    Use el centro de seguridad & cumplimiento para volver a agregar el buzón a la Directiva de retención. Vaya a la página **retención** de **gobierno** \> de fecha en el centro de seguridad & cumplimiento, edite la Directiva de retención y vuelva a agregar el buzón a la lista de destinatarios a los que se aplica la Directiva de retención. 
    
    **Directivas de retención de Office 365 de toda la organización**
    
    Si quitó una directiva de retención de toda la organización o de todo el mundo al excluirla de la Directiva, use el centro de seguridad & cumplimiento para quitar el buzón de la lista de usuarios excluidos. Vaya a la página **retención** de **gobierno** \> de fecha en el centro de seguridad & cumplimiento, edite la Directiva de retención de toda la organización y quite el buzón de la lista de destinatarios excluidos. Al hacerlo, se volverá a aplicar la Directiva de retención al buzón de correo del usuario. 
    
    **suspensiones de casos de eDiscovery**
    
    Use el centro de seguridad & cumplimiento para agregar el buzón de correo de la retención asociada a un caso de exhibición de documentos electrónicos. Vaya a la página **exhibición** de documentos electrónicos de **exhibición** \> de documentos electrónicos, abra el caso y vuelva a agregar el buzón a la retención. 
    
5. Ejecute el siguiente comando para permitir que el Asistente para carpeta administrada procese el buzón de nuevo. Como se mencionó anteriormente, se recomienda esperar 24 horas después de volver a aplicar una retención o una directiva de retención de Office 365 (y comprobar que está en su ubicación) antes de volver a habilitar el Asistente para carpeta administrada. 

    ```
    Set-Mailbox <username> -ElcProcessingDisabled $false
    ```
   
6. Para comprobar que el buzón se ha revertido a su configuración anterior, puede ejecutar los siguientes comandos y, a continuación, comparar la configuración con las que recopiló en el paso 1.

    ```
    Get-Mailbox <username> | FL ElcProcessingDisabled,InPlaceHolds,LitigationHoldEnabled,RetainDeletedItemsFor,SingleItemRecoveryEnabled
    ```

    ```
    Get-CASMailbox <username> | FL EwsEnabled,ActiveSyncEnabled,MAPIEnabled,OWAEnabled,ImapEnabled,PopEnabled
    ```
  
## <a name="more-information"></a>Más información

Esta es una tabla que describe cómo identificar distintos tipos de retenciones en función de los valores de la propiedad *InPlaceHolds* cuando se ejecutan los cmdlets **Get-Mailbox** o **Get-OrganizationConfig** . Para obtener información más detallada, consulte [How to identify The Type of Hold in an Exchange Online Mailbox](identify-a-hold-on-an-exchange-online-mailbox.md).

Como se ha explicado anteriormente, tiene que quitar todas las suspensiones y las directivas de retención de Office 365 de un buzón de correo antes de poder eliminar correctamente los elementos de la carpeta elementos recuperables. 
  
|**Tipo de retención**|**Valor de ejemplo**|**Cómo identificar la retención**|
|:-----|:-----|:-----|
|Retención por juicio  <br/> | `True` <br/> |La propiedad *LitigationHoldEnabled* se establece en `True`.  <br/> |
|Retención en contexto  <br/> | `c0ba3ce811b6432a8751430937152491` <br/> |La propiedad *InPlaceHolds* contiene el GUID de la retención local que está colocada en el buzón. Puede decir que se trata de una conservación local porque el GUID no comienza con un prefijo.  <br/> Puede usar el `Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL` comando en Exchange Online PowerShell para obtener información sobre la conservación local en el buzón.  <br/> |
| Las directivas de retención de Office 365 del centro de cumplimiento de & de seguridad que se aplican a buzones específicos  <br/> | `mbxcdbbb86ce60342489bff371876e7f224` <br/> o  <br/>  `skp127d7cf1076947929bf136b7a2a8c36f` <br/> |Cuando se ejecuta el cmdlet **Get-Mailbox** , la propiedad *InPlaceHolds* también contiene los GUID de las directivas de retención de Office 365 que se aplican al buzón. Puede identificar las directivas de retención porque el GUID comienza por `mbx` el prefijo. Tenga en cuenta que si el GUID de la Directiva de retención `skp` comienza con el prefijo, indica que la Directiva de retención se aplica a las conversaciones de Skype empresarial.  <br/> Para identificar la Directiva de retención de Office 365 que se aplica al buzón de correo, ejecute el siguiente comando en Security & Compliance Center PowerShell: <br/> <br/>`Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name`<br/><br/>Asegúrese de quitar el `mbx` prefijo `skp` o cuando ejecute este comando.  <br/> |
|Directivas de retención de Office 365 de toda la organización en el centro de seguridad & cumplimiento  <br/> |Ningún valor  <br/> o  <br/>  `-mbxe9b52bf7ab3b46a286308ecb29624696`(indica que el buzón está excluido de una directiva de toda la organización)  <br/> |Incluso si la propiedad *InPlaceHolds* está vacía cuando ejecuta el cmdlet **Get-Mailbox** , es posible que se hayan aplicado al buzón una o varias directivas de retención de Office 365 de toda la organización.  <br/> Para comprobarlo, puede ejecutar el `Get-OrganizationConfig | FL InPlaceHolds` comando en Exchange Online PowerShell para obtener una lista de los GUID de las directivas de retención de Office 365 de toda la organización. El GUID de las directivas de retención de toda la organización que se aplican a `mbx` los buzones de Exchange comienza con el prefijo; por ejemplo `mbxa3056bb15562480fadb46ce523ff7b02`.  <br/> Para identificar la Directiva de retención de Office 365 de toda la organización que se aplica al buzón de correo, ejecute el siguiente comando en Security & Compliance Center PowerShell: <br/><br/> `Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name`<br/><br/>Tenga en cuenta que si un buzón se excluye de una directiva de retención de Office 365 de toda la organización, el GUID de la Directiva de retención se muestra en la propiedad *InPlaceHolds* del buzón del usuario cuando se ejecuta el cmdlet **Get-Mailbox** ; se identifica por el prefijo `-mbx`; por ejemplo,`-mbxe9b52bf7ab3b46a286308ecb29624696` <br/> |
|suspensión de casos de exhibición de documentos electrónicos en el centro de seguridad & cumplimiento  <br/> | `UniH7d895d48-7e23-4a8d-8346-533c3beac15d` <br/> |La propiedad *InPlaceHolds* también contiene el GUID de cualquier suspensión asociado con un caso de exhibición de documentos electrónicos en el centro de seguridad & cumplimiento que se puede colocar en el buzón de correo. Puede decir que se trata de una suspensión de casos de exhibición de documentos electrónicos `UniH` porque el GUID comienza por el prefijo.  <br/> Puede usar el `Get-CaseHoldPolicy` cmdlet en Security _AMP_ Compliance Center PowerShell para obtener información sobre el caso de eDiscovery con el que está asociado la retención en el buzón de correo. Por ejemplo, puede ejecutar el comando `Get-CaseHoldPolicy <hold GUID without prefix> | FL Name` para mostrar el nombre de la suspensión de mayúsculas y minúsculas que se encuentra en el buzón. Asegúrese de quitar el `UniH` prefijo al ejecutar este comando.  <br/><br/> Para identificar el caso de exhibición de documentos electrónicos con el que está asociada la retención en el buzón de correo, ejecute los siguientes comandos:<br/><br/>`$CaseHold = Get-CaseHoldPolicy <hold GUID without prefix>`<br/><br/>`Get-ComplianceCase $CaseHold.CaseId | FL Name`


