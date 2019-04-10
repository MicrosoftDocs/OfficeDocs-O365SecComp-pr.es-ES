---
title: Administrar la auditoría de buzones de correo
ms.author: chrisda
author: chrisda
manager: serdars
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: aaca8987-5b62-458b-9882-c28476a66918
description: El registro de auditoría de buzones de correo está activado de forma predeterminada en Microsoft 365 (también denominado auditoría de buzones de correo predeterminada o auditoría de buzones de correo de forma predeterminada). Esto significa que determinadas acciones realizadas por los propietarios de buzones de correo, los delegados y los administradores se registran automáticamente en un registro de auditoría de buzones de correo, donde puede buscar actividades realizadas en el buzón.
ms.openlocfilehash: 38632798aedfa34ee7568a7038d5ff906888619c
ms.sourcegitcommit: 19d27ff836ee7fa1f8a4e761e04d928f13f4bfd8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2019
ms.locfileid: "31745322"
---
# <a name="manage-mailbox-auditing"></a>Administrar la auditoría de buzones de correo
  
A partir de enero 2019, Microsoft activa el registro de auditoría de buzones de correo de forma predeterminada para todas las organizaciones de Microsoft 365. Esto significa que se registran automáticamente determinadas acciones realizadas por los propietarios de buzones de correo, los delegados y los administradores, y los registros de auditoría de buzones correspondientes estarán disponibles cuando los busque en el registro de auditoría de buzones de correo. Antes de que se activara la auditoría de buzones de correo de forma predeterminada, tenía que habilitarla manualmente para cada buzón de usuario de la organización. 

Estas son algunas de las ventajas de la auditoría de buzones de correo de forma predeterminada:

- La auditoría se habilitará de forma predeterminada al crear un nuevo buzón. No tendrá que habilitarlo manualmente para los nuevos usuarios. 

- No tendrá administrar las acciones de buzón de correo que se auditan. Un conjunto definido de acciones de buzón se audita de forma predeterminada para cada tipo de inicio de sesión. Estos [tipos de inicio de sesión](#mailbox-actions-logged-by-default) son propietario, delegado y administrador.

- Las nuevas acciones de buzón de correo que Microsoft publica se auditarán de forma predeterminada. Cuando Microsoft lance una nueva acción de buzón (especialmente para ayudar a proteger su organización y ayudar con las investigaciones forenses), se agregará automáticamente a la lista de acciones de buzón auditada de forma predeterminada. Esto significa que no es necesario agregar nuevas acciones a la lista de acciones de buzón de correo realizadas por los propietarios, los delegados o los administradores. 

- Asegúrese de que está auditando las mismas acciones para todos los buzones de correo para que tenga una directiva de auditoría de buzones de correo coherente en toda la organización.

> [!TIP]
> Lo más importante que debe recordar es que, con la publicación de la auditoría de buzones de correo en de forma predeterminada, no tiene que hacer nada para administrar la auditoría de buzones de correo. Sin embargo, si desea obtener más información, cambiar el comportamiento de la configuración predeterminada o desactivarla a la vez, este artículo puede serle útil.

## <a name="verify-mailbox-auditing-on-by-default-is-turned-on"></a>Comprobar que la auditoría de buzones de correo está activada de forma predeterminada

Para comprobar que la auditoría de buzones de correo está activada de forma predeterminada para su organización, ejecute el siguiente comando en [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell):

```
Get-OrganizationConfig | FL AuditDisabled
``` 

Un valor de **false** indica que la auditoría de buzones de correo está habilitada de forma predeterminada para su organización. 

Cuando la auditoría de buzones de correo está activada de forma predeterminada (cuando la propiedad *AuditDisabled* está establecida en **false**), la configuración de la organización invalidará la configuración de auditoría de buzones de correo para un buzón específico. Por ejemplo, si la propiedad *AuditEnabled* de un buzón se establece en **false**, pero la auditoría de buzones de correo está habilitada de forma predeterminada para su organización, se auditarán las acciones del buzón predeterminadas para ese buzón. Si la auditoría de buzones de correo se deshabilitó explícitamente para un buzón específico y desea deshabilitarla, puede configurar el desvío de la auditoría de buzones para el propietario del buzón y otros usuarios a los que se les ha delegado acceso al buzón. Para obtener más información, vea la sección omitir el [registro de auditoría](#bypass-mailbox-audit-logging) de buzones en este artículo.

> [!NOTE]
> Cuando la auditoría de buzones de correo está activada de forma predeterminada, la propiedad *AuditEnabled* de un buzón no cambiará a **true** si se estableció actualmente en **false**. Es decir, la auditoría de buzones activada de forma predeterminada omite la propiedad *AuditEnabled* de un buzón de correo.

## <a name="supported-mailbox-types"></a>Tipos de buzones admitidos

En la siguiente tabla se muestran los tipos de buzones actualmente compatibles con la auditoría de buzones de correo de forma predeterminada:

|Tipo de buzón|Compatible|No admitido|
|:---------|:---------:|:---------:|
|Buzones de usuario    |![Marca de verificación](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)       |         |
|Buzones compartidos    |![Marca de verificación](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)        |       |
|Buzones de grupo de Office 365    |![Marca de verificación](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)         |         |
|Buzones de recursos    |      |![Marca de verificación](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)        |
|Buzones de carpetas públicas    |       |![Marca de verificación](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)  |
||||

## <a name="mailbox-actions-logged-by-default"></a>Acciones de buzón registradas de forma predeterminada

De forma predeterminada, se registra un conjunto de acciones de buzón para cada uno de los siguientes tipos de inicio de sesión:  

   - **Owner** -el propietario del buzón. 
   
   - **Delegado** : otro usuario al que se ha asignado el permiso sendas, SendOnBehalf o FullAccess al buzón de una persona. Tenga en cuenta que un administrador al que se haya asignado el permiso FullAccess en el buzón de un usuario también se considera un usuario delegado.
   
    - **Admin** : se considera que un tipo de inicio de sesión de administrador tiene acceso a los buzones de correo solo en los siguientes escenarios:
    
       - Cuando se busca un buzón de correo con una de las siguientes herramientas de eDiscovery de Microsoft: 

         - Búsqueda de contenido en el centro de cumplimiento.
       
         -  eDiscovery o exhibición avanzada de documentos electrónicos en el centro de cumplimiento.
       
         - Exhibición de documentos electrónicos local en Exchange Online.
       - Cuando se usa [Microsoft Exchange Server MAPI editor](https://go.microsoft.com/fwlink/p/?linkId=204086) para obtener acceso al buzón.     

En la siguiente tabla se enumeran las acciones de buzón que se registran de forma predeterminada para cada tipo de inicio de sesión.

|Acciones de administración|Acciones de delegado|Acciones del propietario|
|:---------|:---------|:---------|
|Crear    |Crear       | HardDelete        |
|HardDelete    |HardDelete        |MoveToDeletedItems       |
|MoveToDeletedItems    |MoveToDeletedItems         |SoftDelete         |
|SendAs    |SendAs      |    Update     |
|SendOnBehalf    |SendOnBehalf       |UpdateCalendarDelegation        |
|SoftDelete     |SoftDelete      | UpdateFolderPermissions        |
|Update    |Update       |UpdateInboxRules         |
|UpdateCalendarDelegation    | UpdateFolderPermissions        |         |
|UpdateFolderPermissions     | UpdateInboxRules        |         |
|UpdateInboxRules     |         |         |
||||

Estas son las descripciones de estas acciones de buzón. 

|Acción del buzón|Description|
|:---------|:---------|
|**Crear** <br/> |Se ha creado un elemento en la carpeta calendario, contactos, notas o tareas del buzón de correo; por ejemplo, se crea una nueva convocatoria de reunión. Tenga en cuenta que no se audita la creación, el envío o la recepción de un mensaje. Además, no se audita la creación de una carpeta de buzón de correo.  <br/> |
|**HardDelete** <br/> |Un mensaje se purgó de la carpeta Elementos recuperables.  <br/> |
|**MoveToDeletedItems** <br/> |Un mensaje se eliminó y se movió a la carpeta Elementos eliminados.  <br/> |
|**SendAs** <br/> |Un mensaje se envió mediante el permiso SendAs. Esto significa que otro usuario envió el mensaje como si procediera del propietario del buzón.  <br/> |
|**SendOnBehalf** <br/> |Un mensaje se envió mediante el permiso SendOnBehalf. Esto significa que otro usuario envió el mensaje en nombre del propietario del buzón. El mensaje indica el destinatario en nombre de quien se envió el mensaje y quién lo envió realmente.  <br/> |
|**SoftDelete** <br/> |Un mensaje se eliminó permanentemente o se eliminó de la carpeta Elementos eliminados. Los elementos eliminados de forma temporal se mueven a la carpeta Elementos recuperables.  <br/> |
|**Update** <br/> |Se cambió un mensaje o sus propiedades.  <br/> |
|**UpdateCalendarDelegation** <br/> |Se asignó una delegación de calendario a un buzón. La delegación de calendario da a otra persona en la misma organización permisos para administrar el calendario del propietario del buzón.  <br/> |
|**UpdateFolderPermissions** <br/> |Se ha cambiado un permiso de carpeta. Los permisos de carpeta controlan qué usuarios de la organización pueden tener acceso a las carpetas de un buzón de correo y los mensajes que se encuentran en dichas carpetas.  <br/> |
|**UpdateInboxRules** <br/> |Se ha agregado, quitado o cambiado una regla de bandeja de entrada. Las reglas de la bandeja de entrada se usan para procesar mensajes en la bandeja de entrada del usuario en función de las condiciones especificadas y emprender acciones cuando se cumplen las condiciones de una regla, como mover un mensaje a una carpeta especificada o eliminar un mensaje.  <br/> |
|||

Para obtener una lista completa de las acciones de buzón de correo, incluidas las que están disponibles pero que no se incluyen en el conjunto de acciones predeterminadas, vea la sección [acciones de auditoría](#mailbox-auditing-actions) de buzones de este artículo.

> [!IMPORTANT]
> Si ha configurado explícitamente las acciones de buzón de correo para auditar cualquier tipo de inicio de sesión antes de auditar el buzón de correo activado de forma predeterminada para la organización, la configuración existente del buzón de correo tendrá prioridad y no se sobrescribirá con el buzón predeterminado acciones descritas en esta sección. Si en cualquier momento desea volver a las acciones predeterminadas del buzón de correo, puede hacerlo ejecutando el comando **set-Mailbox-DefaultAuditSet** . Para obtener más información acerca de cómo hacerlo, consulte la sección [restaurar las acciones del buzón de correo](#restore-the-default-mailbox-actions) predeterminadas de este artículo.

### <a name="verify-that-default-mailbox-actions-are-being-logged-for-each-logon-type"></a>Compruebe que se registran las acciones predeterminadas del buzón para cada tipo de inicio de sesión

Con la publicación de la auditoría de buzones de correo activada de forma predeterminada, se ha agregado una nueva propiedad de buzón denominada *DefaultAuditSet* . Esta propiedad indica si las acciones predeterminadas del buzón (administradas por Microsoft) se están auditando para cada tipo de inicio de sesión de un buzón especificado. Puede ejecutar el siguiente comando para mostrar los valores de esta propiedad:

```
Get-Mailbox <username> | FL DefaultAuditSet
```

Un valor de `Admin, Delegate, Owner` indica que las acciones predeterminadas del buzón de los tres tipos de inicio de sesión se están auditando y que un administrador de la organización *no ha* cambiado las acciones de ningún tipo de inicio de sesión. Nota: este es el estado predeterminado después de que la auditoría de buzones de correo está activada de forma predeterminada en la organización. 

Si un administrador de su organización ha cambiado las acciones de buzón de correo que se auditan para un tipo de inicio de sesión (usando el cmdlet **set-Mailbox** con los parámetros *AuditAdmin*, *AuditDelegate*o *AuditOwner* ), el valor de la propiedad *DefaultAuditSet* será diferente del valor predeterminado. Por ejemplo, un valor de `Owner` indica que las acciones del buzón de correo predeterminadas para el propietario del buzón de correo se están auditando `Delegate` y `Admin` que las acciones y los cambios se han modificado. Si no se muestran valores para la propiedad *DefaultAuditSet* (también denominada valor *null* ), se han cambiado las acciones de buzón de los tres tipos de inicio de sesión.

Vea la sección [cambiar o restaurar acciones de buzón registradas de forma predeterminada](#change-or-restore-mailbox-actions-logged-by-default) en este artículo para obtener más información acerca de cómo cambiar las acciones de buzón de correo que se auditan.

### <a name="display-a-list-of-mailbox-actions-logged-by-default"></a>Mostrar una lista de acciones de buzón registradas de forma predeterminada

Puede ejecutar los siguientes comandos en Exchange Online PowerShell para mostrar la lista de acciones de buzón de correo que actualmente se usan para un buzón de correo para cada tipo de inicio de sesión:

**Acciones del propietario**

```
Get-Mailbox <username> | Select-Object -ExpandProperty AuditOwner
```

**Acciones de delegado**

```
Get-Mailbox <username> | Select-Object -ExpandProperty AuditDelegate
```

**Acciones de administración**

```
Get-Mailbox <username> | Select-Object -ExpandProperty AuditAdmin
```

## <a name="change-or-restore-mailbox-actions-logged-by-default"></a>Cambiar o restaurar acciones de buzón registradas de forma predeterminada

Como se ha explicado anteriormente, una de las ventajas clave de la auditoría de buzones de correo de forma predeterminada es que no es necesario administrar las acciones de buzones de correo que se auditan. Microsoft lo hace por usted y automáticamente agregará nuevas acciones de buzón de correo que se auditarán de forma predeterminada cuando se publiquen. Sin embargo, es posible que su organización tenga motivos para auditar un conjunto de acciones de buzón que sean distintas de las predeterminadas. En esta sección se muestra cómo cambiar las acciones de buzón de correo que se auditan para cada uno de los tipos de inicio de sesión y cómo volver a las acciones predeterminadas administradas por Microsoft.

> [!IMPORTANT]
> Si realiza algún cambio en las acciones de buzón de un usuario que se registra de forma predeterminada (tal como se describe en la siguiente sección), cualquier acción nueva de buzón de correo que Microsoft haya lanzado no será auditada para esos buzones. Tendrá que agregar explícitamente una nueva acción de buzón a la lista de acciones auditadas para un tipo de inicio de sesión.

### <a name="change-the-mailbox-actions-to-audit"></a>Cambiar las acciones de buzón de correo para auditar

Puede usar el cmdlet **set-Mailbox** con los parámetros *AuditAdmin*, *AuditDelegate*o *AuditOwner* para cambiar las acciones de buzón de correo que se auditan, según el tipo de inicio de sesión. Como estos parámetros relacionados con la auditoría son parámetros de varios valores (lo que significa que pueden tener más de un valor), hay dos maneras diferentes de cambiarlos.

- Puede especificar varias acciones de buzón de correo que sobrescriban las acciones existentes mediante la siguiente sintaxis `action1,action2,...actionN`:.

- Puede Agregar o quitar una o varias acciones de buzón de correo sin que ello afecte a los registros existentes mediante `@{Add="action1","value2"}` la `@{Remove="action1","action2"}`siguiente sintaxis: o.

Independientemente del método que use para cambiar las acciones de buzón de correo que se auditan, las acciones de buzón auditadas de forma predeterminada (para el tipo de inicio de sesión que ha modificado) dejarán de ser administradas por Microsoft. Además, el valor del tipo de inicio de sesión que ha modificado no se mostrará en el parámetro de buzón *DefaultAuditSet* [descrito anteriormente](#verify-that-default-mailbox-actions-are-being-logged-for-each-logon-type).

A continuación se muestran algunos ejemplos de cómo usar uno de estos métodos para cambiar las acciones de buzón de correo para auditar en cada uno de los diferentes tipos de inicio de sesión. 

En este ejemplo se cambian las acciones del buzón de administrador al sobrescribir las acciones predeterminadas con SoftDelete y HardDelete. 

```
Set-Mailbox <username> -AuditAdmin HardDelete,SoftDelete
```

En este ejemplo se agrega la acción de propietario MailboxLogin. 

```
Set-Mailbox <username> -AuditOwner @{Add="MailboxLogin"}
```

En este ejemplo se quita la acción de delegado MoveToDeletedItems.

```
Set-Mailbox <username> -AuditDelegate @{Remove="MoveToDeletedItems"}
```

#### <a name="checking-the-defaultauditset-property"></a>Comprobación de la propiedad DefaultAuditSet

Después de cambiar las acciones predeterminadas de buzón de correo para un tipo de inicio de sesión, la propiedad *DefaultAuditSet* del buzón se actualizará automáticamente para reflejar este cambio. Por ejemplo, si se ejecuta `Get-Mailbox <username> | FL DefaultAuditSet` después de la primera vez que se agrega o quita una acción del propietario del buzón, el comando solo devolverá un valor de `Admin, Delegate`. Esto indica que se han cambiado las acciones predeterminadas del buzón de correo, lo que significa que todas las nuevas acciones de propietario del buzón que Microsoft ha lanzado no se agregarán automáticamente a este buzón. Lo mismo se aplica para cambiar las acciones de buzón para el tipo de inicio de sesión de administrador o delegado.

### <a name="restore-the-default-mailbox-actions"></a>Restaurar las acciones del buzón predeterminadas

Si ha realizado cambios en las acciones de buzón de correo que se auditan para un tipo de inicio de sesión, puede restaurar las acciones predeterminadas del `Set-Mailbox -DefaultAuditSet` buzón de correo que se auditan al ejecutar el comando. Al hacerlo, se producirán las siguientes acciones:

- La lista actual de acciones de buzón se reemplazará por las acciones de buzón predeterminadas para el tipo de inicio de sesión adecuado.
 
- Las nuevas acciones de buzón de correo que Microsoft ha lanzado se agregarán automáticamente a la lista del tipo de inicio de sesión adecuado.

- La [propiedad de buzón DefaultAuditSet](#checking-the-defaultauditset-property) se actualizará para incluir el tipo de inicio de sesión adecuado.

Para restaurar las acciones del buzón de correo predeterminadas para todos los tipos de inicio de sesión, ejecute el siguiente comando:

```
Set-Mailbox <username> -DefaultAuditSet Admin,Delegate,Owner
```

Puede usar este comando para restaurar las acciones del buzón de correo predeterminadas para cualquiera de los tipos de inicio de sesión (mediante los valores de **Administrador**, **delegado**o **propietario** para el parámetro *DefaultAuditSet* ).

## <a name="turn-off-mailbox-auditing-on-by-default-for-your-organization"></a>Desactivar la auditoría de buzones de correo en la organización de forma predeterminada

Si por algún motivo su organización decide que no desea auditar las acciones de buzón de correo, puede desactivar la auditoría de buzones de correo de forma predeterminada para toda la organización ejecutando el siguiente comando en Exchange Online PowerShell:

```
Set-OrganizationConfig -AuditDisabled $true
```

Cuando la auditoría de buzones de correo está desactivada de forma predeterminada (la propiedad *AuditDisabled* se establece en **true**) para la organización, se producirán las siguientes acciones:

- La auditoría de buzones de correo está deshabilitada para su organización.

- No se auditarán las acciones del buzón (a partir del momento en que la auditoría está deshabilitada para la organización), incluso si la propiedad *AuditEnabled* de un buzón se establece en **true**.

- La auditoría de buzones de correo no se habilitará para nuevos buzones y se omitirá la configuración de la propiedad *AuditEnabled* en un buzón nuevo (o existente) en **true** .

- Se omitirá cualquier configuración de Asociación de omisión de auditoría de buzones (configurada con el cmdlet **set-MailboxAuditBypassAssociation** ).

- Los registros de auditoría de buzón de correo existentes se conservarán hasta que expire el límite de antigüedad del registro de auditoría para el registro.

### <a name="turn-on-mailbox-auditing-on-by-default"></a>Activar la auditoría de buzones de correo de forma predeterminada

Para volver a activar la auditoría de buzones de correo para su organización, simplemente ejecute el siguiente comando en Exchange Online PowerShell:

```
Set-OrganizationConfig -AuditDisabled $false
```

## <a name="bypass-mailbox-audit-logging"></a>Omisión del registro de auditoría de buzones

Actualmente, no puede deshabilitar la auditoría de buzones de correo específicos cuando la auditoría de buzones de correo está activada de forma predeterminada en la organización. Por ejemplo, se omite el establecimiento de la propiedad de buzón *AuditEnabled* en **false** .  Sin embargo, puede seguir usando el cmdlet **set-MailboxAuditBypassAssociation** de PowerShell de Exchange Online para evitar que se registren las acciones de buzón de correo realizadas por determinados usuarios. Al omitir la auditoría de buzones de correo, las acciones de buzón de correo realizadas por un usuario específico no se auditan, independientemente del buzón de correo en el que se realicen dichas acciones. Si omite la auditoría de buzones de correo para un usuario específico, no se registrarán las acciones del propietario del buzón realizadas por dicho usuario. Y si al mismo usuario se le asignan permisos para el buzón de otro usuario (o un buzón compartido), las acciones de delegado realizadas por el primer usuario tampoco se registrarán.

Para omitir el registro de auditoría de buzones de correo para un usuario específico, ejecute el siguiente comando:

```
Set-MailboxAuditBypassAssociation -Identity <username> -AuditByPassEnabled $true
```

Para comprobar que la auditoría se omite para el usuario especificado, ejecute el siguiente comando:

```
Get-MailboxAuditBypassAssociation -Identity <username> | FL AuditByPassEnabled
```

Un valor de **true** indica que se omite el registro de auditoría de buzones para ese usuario.

## <a name="mailbox-auditing-actions"></a>Acciones de auditoría de buzones
  
En la tabla siguiente se resumen las acciones que se auditan para cada tipo de inicio de sesión de usuario. En la tabla, un asterisco ( **\*** ) indica que la acción se registra de forma predeterminada. **No** indica que no se puede registrar una acción para ese tipo de inicio de sesión. Tenga en cuenta que un administrador al que se haya asignado el permiso Acceso total en el buzón de un usuario se considera usuario delegado. 
  
|**Acción**|**Descripción**|**Admin**|**Delegado**|**Owner**|
|:-----|:-----|:-----|:-----|:-----|
|**Copy** <br/> |Un mensaje se copió en otra carpeta.  <br/> |Sí  <br/> |No  <br/> |No  <br/> |
|**Crear** <br/> |Se crea un elemento en la carpeta calendario, contactos, notas o tareas del buzón de correo; por ejemplo, se crea una nueva convocatoria de reunión. Tenga en cuenta que no se audita la creación, el envío o la recepción de un mensaje. Además, no se audita la creación de una carpeta de buzón de correo.  <br/> |Sí\*  <br/> |Sí\*  <br/> |Sí  <br/> |
|**FolderBind**\** <br/> |Se tuvo acceso a una carpeta de buzón de correo. Esta acción también se registra cuando el administrador o un delegado abren el buzón de correo.  <br/> |Sí  <br/> |Sí  <br/> |No  <br/> |
|**HardDelete** <br/> |Un mensaje se purgó de la carpeta Elementos recuperables.  <br/> |Sí\*  <br/> |Sí\*  <br/> |Sí\*  <br/> |
|**MailboxLogin** <br/> |El usuario ha iniciado sesión en su buzón.  <br/> |No  <br/> |No  <br/> |Sí  <br/> |
|**MessageBind**\*** <br/> |Un mensaje se consultó en el panel de vista previa o se abrió.  <br/> |Sí  <br/> |No  <br/> |No  <br/> |
|**Mover** <br/> |Un mensaje se movió a otra carpeta.  <br/> |Sí  <br/> |Sí  <br/> |Sí  <br/> |
|**MoveToDeletedItems** <br/> |Un mensaje se eliminó y se movió a la carpeta Elementos eliminados.  <br/> |Sí\*  <br/> |Sí\*  <br/> |Sí\*  <br/> |
|**SendAs** <br/> |Un mensaje se envió mediante el permiso SendAs. Esto significa que otro usuario envió el mensaje como si procediera del propietario del buzón.  <br/> |Sí\*  <br/> |Sí\*  <br/> |No  <br/> |
|**SendOnBehalf** <br/> |Un mensaje se envió mediante el permiso SendOnBehalf. Esto significa que otro usuario envió el mensaje en nombre del propietario del buzón. El mensaje indica el destinatario en nombre de quien se envió el mensaje y quién lo envió realmente.  <br/> |Sí\*  <br/> |Sí\*  <br/> |No  <br/> |
|**SoftDelete** <br/> |Un mensaje se eliminó permanentemente o se eliminó de la carpeta Elementos eliminados. Los elementos eliminados de forma temporal se mueven a la carpeta Elementos recuperables.  <br/> |Sí\*  <br/> |Sí\*  <br/> |Sí\*  <br/> |
|**Update** <br/> |Se cambió un mensaje o sus propiedades.  <br/> |Sí\*  <br/> |Sí\*  <br/> |Sí\*  <br/> |
|**UpdateCalendarDelegation** <br/> |Se asignó una delegación de calendario a un buzón. La delegación de calendario da a otra persona de la organización permisos para administrar el calendario del propietario del buzón.  <br/> |Sí\*  <br/> |No  <br/> |Sí\*  <br/> |
|**UpdateFolderPermissions** <br/> |Se ha cambiado un permiso de carpeta. Los permisos de carpeta controlan qué usuarios de la organización pueden tener acceso a las carpetas de un buzón de correo y los mensajes que se encuentran en dichas carpetas.  <br/> |Sí\*  <br/> |Sí\*  <br/> |Sí\*  <br/> |
|**UpdateInboxRules** <br/> |Se ha agregado, quitado o cambiado una regla de bandeja de entrada. Las reglas de la bandeja de entrada se usan para procesar mensajes en la bandeja de entrada del usuario en función de las condiciones especificadas y emprender acciones cuando se cumplen las condiciones de una regla, como mover un mensaje a una carpeta especificada o eliminar un mensaje.  <br/> |Sí\*  <br/> |Sí\*  <br/> |Sí\*  <br/> |
   
> [!NOTE]
> <sup>\*</sup>Se audita de forma predeterminada cuando está habilitada la auditoría de buzones de correo predeterminada para el tipo de inicio de sesión. <br/><br/>  <sup>\*\*</sup>Se consolidan los registros de auditoría para las acciones de enlace de carpeta realizadas por los delegados. Se genera un registro de auditoría para el acceso a la carpeta individual en un período de 24 horas. <br/><br/> La acción MessageBind ha quedado en desuso en Exchange Online y ya no está disponible para agregarla a la lista de acciones de buzón para el tipo de inicio de sesión de administrador. <sup> \* \* \* </sup> 

## <a name="more-information"></a>Más información

- De forma predeterminada, las entradas del registro de auditoría de buzones se conservan durante 90 días y después se eliminan. Puede cambiar el límite de antigüedad de las entradas del registro de auditoría mediante el comando **set-Mailbox-AuditLogAgeLimit** en Exchange Online PowerShell. Tenga en cuenta que aumentar el límite de antigüedad predeterminado para los registros de auditoría de buzones de correo no afecta al límite de duración de 90 días para los registros de registro de auditoría de buzones en el registro de auditoría de Microsoft 365. Por ejemplo, si aumenta el límite de antigüedad para las entradas de registro de auditoría de buzones a 365 días, se podrá buscar en el registro de auditoría de Microsoft 365 solo durante 90 días después de que se haya producido el evento correspondiente. En este caso, tendría que buscar en el registro de auditoría del buzón del usuario los registros de más de 90 días. Para obtener más información acerca de la búsqueda de registros de auditoría de buzones, consulte [Search-MailboxAuditLog](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-audit/search-mailboxauditlog).

- Si ha cambiado la propiedad *AuditLogAgeLimit* de un buzón antes de auditar el buzón de correo activada de manera predeterminada para la organización, no se cambiará el límite de antigüedad del registro de auditoría existente para ese buzón; es decir, la auditoría de buzones de correo de forma predeterminada no afecta al límite de antigüedad actual para los registros de auditoría de buzón.

- Los registros de registro de auditoría de buzones de correo se ** almacenan en una subcarpeta (denominada Audits) en la carpeta elementos recuperables del buzón de correo de cada usuario. Tenga en cuenta lo siguiente en lo que se refiere a los registros de auditoría de buzón de correo y la carpeta elementos recuperables.
   
    - Los registros de auditoría de buzones de correo tienen en cuenta la cuota de almacenamiento de la carpeta elementos recuperables, que es 30 de manera predeterminada (la cuota de advertencia es de 20 GB). Tenga en cuenta que la cuota de almacenamiento de la carpeta elementos recuperables se ha incrementado automáticamente de 100 GB (cuota de advertencia de 90 MB) cuando se coloca una retención en un buzón o el buzón se asigna a una directiva de retención en el centro de cumplimiento.

    - Los registros de auditoría de buzones de correo también cuentan en el [límite de carpetas para la carpeta elementos recuperables](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#mailbox-folder-limits). El número máximo de elementos (que son registros de auditoría en este caso) que se pueden almacenar en la subcarpeta Audits es de 3 millones elementos. 

      > [!NOTE]
      > Es improbable que la auditoría de buzones de correo que se produzca de forma predeterminada afecte a la cuota de almacenamiento o el límite de la carpeta de elementos recuperables. 

    - Puede ejecutar el siguiente comando en Exchange Online PowerShell para mostrar el tamaño y el número de elementos en la subcarpeta Audits de la carpeta elementos recuperables: 
       ```
       Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems | Where-Object {$_.Name -eq 'Audits'} | FL FolderPath,FolderSize,ItemsInFolder
       ```

     - No se puede tener acceso directamente a un registro de auditoría en la carpeta elementos recuperables; en su lugar, use el cmdlet **Search-MailboxAuditLog** o busque en el registro de auditoría de Microsoft 365 para buscar y ver registros de auditoría de buzón de correo.

- Si un buzón se coloca en suspensión o se asigna a una directiva de retención en el centro de cumplimiento, las entradas del registro de auditoría se conservan durante la duración definida por la propiedad *AuditLogAgeLimit* del buzón (que se establece en 90 días de forma predeterminada). Para conservar los registros de auditoría más tiempo para los buzones en retención, debe aumentar el período de retención aumentando el valor de la propiedad *AuditLogAgeLimit* .