---
title: Habilitar la auditoría de buzones de correo en Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/19/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: aaca8987-5b62-458b-9882-c28476a66918
description: En Office 365, puede activar registro de auditoría de buzón de correo para registrar el acceso a buzones de correo por los propietarios de los buzones de correo, delegados y los administradores. De forma predeterminada, la auditoría de buzón de correo en Office 365 no está activada. Después de habilitar la auditoría de buzón de correo para un buzón de correo, puede buscar en el registro de auditoría de Office 365 para actividades que se realizan en el buzón de correo.
ms.openlocfilehash: a31a96c8c5c65965746a3a31bc924731289795f0
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22536022"
---
# <a name="enable-mailbox-auditing-in-office-365"></a>Habilitar la auditoría de buzones de correo en Office 365
  
En Office 365, puede activar registro de auditoría de buzón de correo para registrar el acceso a buzones de correo por los propietarios de los buzones de correo, delegados y los administradores. De forma predeterminada, la auditoría de buzón de correo en Office 365 no está activada. Esto significa que los eventos de auditoría de buzón de correo no aparecerá en los resultados al buscar en el registro de auditoría de Office 365 para la actividad de buzón de correo de. Pero después de activar el registro para un buzón de usuario de auditoría de buzón de correo, puede buscar el registro de auditoría para la actividad de buzón de correo. Además, cuando el buzón de correo de auditoría registro está activado, algunas acciones realizadas por los administradores, los delegados, y se registran los propietarios de forma predeterminada. Para registrar (y, a continuación, buscar) acciones adicionales, vea el paso 3.

## <a name="before-you-begin"></a>Antes de empezar
  
- Se debe usar Exchange Online PowerShell para habilitar el buzón de registro de auditoría. No se puede usar la seguridad de Office 365 &amp; centro de cumplimiento o el centro de administración de Exchange.
    
- Después de habilitar la auditoría de buzón de correo para un buzón de correo, acceso a las acciones de buzón de correo y determinados admin y delegado se registran de forma predeterminada. Para registrar las acciones realizadas por el propietario del buzón, debe especificar qué acciones de propietario para auditar. Vea la sección "Más información" para ver una lista de acciones que se registran después de registro de auditoría de buzón de correo está habilitada, y las acciones que están disponibles para cada tipo de inicio de sesión de usuario.
    
- No se puede habilitar el registro para el buzón de correo que está asociado con un grupo de Office 365 o a un equipo en Microsoft Teams de auditoría de buzón de correo.
    
- Un administrador al que se haya asignado el permiso Acceso total en el buzón de un usuario se considera usuario delegado.
  
## <a name="step-1-connect-to-exchange-online-powershell"></a>Paso 1: Conectar a Exchange Online PowerShell

1. En el equipo local, abra Windows PowerShell y ejecute el siguiente comando.
   
    ```
    $UserCredential = Get-Credential
    ```

2. En el cuadro de diálogo **Solicitud de credenciales de Windows PowerShell**, escriba el nombre de usuario y la contraseña de una cuenta de administrador global de Office 365 y, después, haga clic en **Aceptar**.
    
3. Ejecute el comando siguiente:
    
    ```
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
    ```

3. Ejecute el comando siguiente.

    ```
    Import-PSSession $Session
    ```
   
4. Para comprobar que se ha conectado a su organización de Exchange Online, ejecute el comando siguiente para obtener una lista de todos los buzones de correo de su organización.
    
    ```
    Get-Mailbox
    ```
  
Para obtener más información o si tiene problemas para conectarse a su organización de Exchange Online, consulte [Conectarse a Exchange Online mediante PowerShell remoto](https://go.microsoft.com/fwlink/p/?LinkId=517283).
  
## <a name="step-2-enable-mailbox-audit-logging"></a>Paso 2: Habilitar el registro de auditoría de buzones de correo

Tras conectarse a la organización de Exchange Online, use PowerShell para habilitar la auditoría de buzón de correo para un buzón de correo. Como alternativa, puede habilitar la auditoría de buzón de correo para todos los buzones de la organización.
  
En este ejemplo se habilita la auditoría de buzón para el buzón del Pilar Pinilla.
  
```
Set-Mailbox -Identity "Pilar Pinilla" -AuditEnabled $true
```

En este ejemplo se habilita el registro de auditoría de todos los buzones de correo de los usuarios de su organización.
  
```
Get-Mailbox -ResultSize Unlimited -Filter {RecipientTypeDetails -eq "UserMailbox"} | Set-Mailbox -AuditEnabled $true
```
  
## <a name="step-3-specify-owner-actions-to-audit"></a>Paso 3: Especificar las acciones de propietario que se auditarán

Al habilitar la auditoría para un buzón de correo, sólo una acción ( **UpdateFolderPermissions** ) realizada por el propietario del buzón se audita de forma predeterminada. Es necesario especificar otras acciones de propietario para auditar. Vea la tabla en la sección "Acciones de buzón de correo" para una lista y una descripción de las acciones de propietario que se pueden auditar. 
  
En este ejemplo se agregan las acciones de propietario **MailboxLogin** y **HardDelete** en buzón de auditoría de buzón de correo del Pilar Pinilla. En este ejemplo se da por supuesto que el auditoría de buzón de correo ya se ha habilitado para este buzón de correo. 

```
Set-Mailbox "Pilar Pinilla" -AuditOwner @{Add="MailboxLogin","HardDelete"}
```

En este ejemplo se habilita la auditoría de buzón para el buzón de Don Hall y especifica que se registrarán solo la acción de **MailboxLogin** realizada por el propietario del buzón. Tenga en cuenta que en este ejemplo se sobrescribe la acción de UpdateFolderPermissions de forma predeterminada. 
  
```
Set-Mailbox "Don Hall" -AuditEnabled $true -AuditOwner MailboxLogin
```
   
En este ejemplo se agregan a las acciones de propietario **SoftDelete** , **HardDelete**y **MailboxLogin**a todos los buzones de correo en la organización. En este ejemplo se da por supuesto que el auditoría de buzón de correo ya se ha habilitado para todos los buzones. 
  
```
Get-Mailbox -ResultSize Unlimited -Filter {RecipientTypeDetails -eq "UserMailbox"} | Set-Mailbox -AuditOwner @{Add="MailboxLogin","HardDelete","SoftDelete"}
```
  
## <a name="how-do-you-know-this-worked"></a>¿Cómo saber si el proceso se ha completado correctamente?

Para comprobar que se haya habilitado correctamente el registro de auditoría de buzones de correo, utilice el cmdlet **Get-Mailbox** para recuperar la configuración de auditoría de ese buzón. 
  
En este ejemplo se recupera la configuración de auditoría de Pilar Pinilla.

```
Get-Mailbox "Pilar Pinilla"| FL Audit*
```
   
En este ejemplo se recupera la configuración de auditoría de todos los buzones de correo de los usuarios de la organización.

```
Get-Mailbox -ResultSize Unlimited -Filter {RecipientTypeDetails -eq "UserMailbox"} | FL Name,Audit*
```
   
Un valor de **True** para la propiedad **AuditEnabled** comprueba que auditoría de buzón de correo está habilitado el registro. 
    
## <a name="mailbox-auditing-actions"></a>Acciones de auditoría de buzón de correo
  
En la siguiente tabla se enumera las acciones que se pueden registrar por buzón de registro de auditoría. La tabla incluye la acción que se puede registrar para los tipos de inicio de sesión de usuario diferente. En la tabla, un **No** indica que no se puede registrar una acción para ese tipo de inicio de sesión. Un asterisco ( **\*** ) indica que la acción se registra de forma predeterminada cuando el registro de auditoría de buzón de correo está habilitado para el buzón de correo. Como se ha indicado anteriormente, la acción de propietario sólo que se audita de manera predeterminada cuando se activa la auditoría de buzón de correo es UpdateFolderPermissions. Para iniciar otras acciones realizadas por el propietario del buzón, debe especificar acciones de propietario adicionales para auditar. Para ello, vea el [paso 3](#step-3-specify-owner-actions-to-audit) de este tema. 
  
|**Acción**|**Descripción**|**Administrador**|**Delegado\*\*\***|**Propietario**|
|:-----|:-----|:-----|:-----|:-----|
|**Copiar** <br/> |Un mensaje se copió en otra carpeta.  <br/> |Sí  <br/> |No  <br/> |No  <br/> |
|**Create** <br/> |Se crea un elemento en la carpeta Calendario, contactos, notas o tareas en el buzón de correo; Por ejemplo, se crea una nueva convocatoria de reunión. Tenga en cuenta que no se audita crear, enviar o recibir un mensaje. Además, no se audita la creación de una carpeta de buzón de correo.  <br/> |Sí\*  <br/> |Sí\*  <br/> |Sí  <br/> |
|**FolderBind** <br/> |Se tuvo acceso a una carpeta de buzón de correo. Esta acción también se registra cuando el administrador o un delegado abren el buzón de correo.  <br/> |Sí\*  <br/> |Sí\*\*  <br/> |No  <br/> |
|**HardDelete** <br/> |Un mensaje se purgó de la carpeta Elementos recuperables.  <br/> |Sí\*  <br/> |Sí\*  <br/> |Sí  <br/> |
|**MailboxLogin** <br/> |El usuario inició sesión en su buzón.  <br/> |No  <br/> |No  <br/> |Sí  <br/> |
|**MessageBind** <br/> |Un mensaje se consultó en el panel de vista previa o se abrió.  <br/> |Sí  <br/> |No  <br/> |No  <br/> |
|**Mover** <br/> |Un mensaje se movió a otra carpeta.  <br/> |Sí\*  <br/> |Sí  <br/> |Sí  <br/> |
|**MoveToDeletedItems** <br/> |Un mensaje se eliminó y se movió a la carpeta Elementos eliminados.  <br/> |Sí\*  <br/> |Sí  <br/> |Sí  <br/> |
|**SendAs** <br/> |Un mensaje se envió mediante el permiso SendAs. Esto significa que otro usuario envió el mensaje como si procediera del propietario del buzón.  <br/> |Sí\*  <br/> |Sí\*  <br/> |No  <br/> |
|**SendOnBehalf** <br/> |Un mensaje se envió mediante el permiso SendOnBehalf. Esto significa que otro usuario envió el mensaje en nombre del propietario del buzón. El mensaje indica el destinatario en nombre de quien se envió el mensaje y quién lo envió realmente.  <br/> |Sí\*  <br/> |Sí  <br/> |No  <br/> |
|**SoftDelete** <br/> |Un mensaje se eliminó permanentemente o se eliminó de la carpeta Elementos eliminados. Los elementos eliminados de forma temporal se mueven a la carpeta Elementos recuperables.  <br/> |Sí\*  <br/> |Sí\*  <br/> |Sí  <br/> |
|**Actualizar** <br/> |Se cambió un mensaje o sus propiedades.  <br/> |Sí\*  <br/> |Sí\*  <br/> |Sí  <br/> |
|**UpdateCalendarDelegation** <br/> |Una delegación de calendario se asignó a un buzón de correo. Delegación de calendario proporciona a otra persona en los mismos permisos de organización para administrar el calendario del propietario del buzón.  <br/> |Sí\*  <br/> |No  <br/> |Sí\*  <br/> |
|**UpdateFolderPermissions** <br/> |Se ha cambiado un permiso de la carpeta. Control de los permisos de carpeta qué usuarios de la organización pueden tener acceso a las carpetas de un buzón de correo y los mensajes que se encuentra en esas carpetas.  <br/> |Sí\*  <br/> |Sí\*  <br/> |Sí\*  <br/> |
|**UpdateInboxRules** <br/> |Se han agregado, eliminada o cambiado una regla de bandeja de entrada. Las reglas de bandeja de entrada se usan para procesar los mensajes en la Bandeja de entrada del usuario en función de las condiciones especificadas y realizar acciones cuando se cumplen las condiciones de una regla, como mover un mensaje a una carpeta especificada o la eliminación de un mensaje.  <br/> |Sí\*  <br/> |Sí\*  <br/> |Sí\*  <br/> |
   
> [!NOTE]
> <sup>\*</sup>Se audita de manera predeterminada si está habilitada la auditoría para un buzón de correo. > <sup> \* </sup> Se consolidan las entradas para acciones realizadas por los delegados de enlazar la carpeta. Se genera una entrada de registro para el acceso de carpeta individuales dentro de un intervalo de tiempo de 24 horas. > <sup> \* \* </sup> Un administrador que se ha asignado el permiso acceso total al buzón de un usuario se considera un usuario delegado. 
  
Si ya no necesita determinados tipos de acciones de buzón de correo que se va a auditar, debe modificar la configuración de registro de auditoría del buzón para deshabilitar esas acciones. Las entradas de registro existentes no se purgan hasta que se alcanza el límite de edad de 90 días para las entradas de registro de auditoría.
  
## <a name="more-infotab"></a>[Obtener más información](#tab/)
  
- Usar el registro de auditoría de Office 365 para buscar actividad de buzón de correo que se hayan registrado. Puede buscar de la actividad de un buzón de usuario específico. La siguiente captura de pantalla muestra una lista de actividades de buzón de correo que se pueden buscar en el registro de auditoría de Office 365. Tenga en cuenta que estas actividades son las mismas acciones que se describen en la sección "Acciones de auditoría de buzón" en este tema.
    
    ![Puede buscar el registro de auditoría de Office 365 para acciones de auditoría de buzón de correo mediante la selección de "Actividades de buzón de correo de Exchange" en la lista desplegable de actividades](media/fadc34f8-9de2-4688-8b1a-bc5540e69a23.png)
  
    En la siguiente tabla se describe cada actividad que puede buscar y muestra el buzón correspondiente acción de auditoría de buzón de correo.
    
    |**Actividad en el registro de auditoría**|**Acción de auditoría de buzón de correo**|
    |:-----|:-----|
    |Elemento de buzón de correo creada  <br/> |Crear  <br/> |
    |Mensajes copiados a otra carpeta  <br/> |Copiar  <br/> |
    |Usuario que ha iniciado sesión en el buzón de correo  <br/> |MailboxLogin  <br/> |
    |Envía el mensaje con los permisos Enviar en nombre  <br/> |SendOnBehalf  <br/> |
    |Mensajes purgados desde el buzón de correo  <br/> |HardDelete  <br/> |
    |Mover mensajes a la carpeta Elementos eliminados  <br/> |MoveToDeletedItems  <br/> |
    |Mover mensajes a otra carpeta  <br/> |Mover  <br/> |
    |Envía el mensaje con permisos Enviar como  <br/> |SendAs  <br/> |
    |Mensaje actualizado  <br/> |Update  <br/> |
    |Mensajes eliminados de la carpeta Elementos eliminados  <br/> |SoftDelete  <br/> |
    |Permisos se ha agregado a la carpeta  <br/> |UpdateFolderPermissions  <br/> |
    |Modificación de permisos de carpeta  <br/> |UpdateFolderPermissions  <br/> |
    |Se han quitado los permisos de carpeta  <br/> |UpdateFolderPermissions  <br/> |
    |Se ha quitado o se ha agregado un usuario con acceso de delegado a la carpeta Calendario  <br/> |UpdateCalendarDelegation  <br/> |
   
    Tenga en cuenta que las actividades **se agregó delegar permisos de buzón de correo** y **se quitan delegar permisos de buzón de correo** que se muestra en la captura de pantalla anterior no están relacionadas con acciones de auditoría de buzón de correo. Indican si un administrador asignado o había quitado contar con permiso de buzón de correo. 
    
    Para obtener información sobre el registro de auditoría de Office 365, vea [Buscar en el registro de auditoría de la seguridad de Office 365 &amp; centro de cumplimiento](search-the-audit-log-in-security-and-compliance.md).
    
- Solo se considera que un administrador ha tenido acceso a un buzón en los escenarios siguientes:
    
  - Exhibición de documentos electrónicos en contexto en Exchange Online o búsqueda de contenido en Office 365 se usa para buscar en un buzón.
    
  - [Microsoft Exchange Server MAPI Editor](https://go.microsoft.com/fwlink/p/?linkId=204086) se usa para acceder al buzón de correo. 
    
- Al habilitar el registro de auditoría para un buzón de correo, también se pueden especificar las acciones de usuario (por ejemplo, acceso, traslado o eliminación de mensajes) que se registrarán para cada tipo de inicio de sesión (administrador, delegado o propietario). 
    
- Para deshabilitar el registro de auditoría de buzones de correo, ejecute el comando siguiente:

  ```
  Set-Mailbox -Identity <identity of mailbox> -AuditEnabled $false
   ```

- No se muestran las acciones que se van a auditar para cada tipo de usuario cuando se ejecuta el cmdlet **Get-Mailbox** . Pero puede ejecutar los siguientes comandos para mostrar todas las acciones auditadas para un tipo de inicio de sesión de usuario específico. 

    ```
    Get-Mailbox <identity of mailbox> | Select-Object -ExpandProperty AuditAdmin
    ```

    ```
    Get-Mailbox <identity of mailbox> | Select-Object -ExpandProperty AuditDelegate
    ```

    ```
    Get-Mailbox <identity of mailbox> | Select-Object -ExpandProperty AuditOwner
    ```

- También puede exportar un registro de auditoría de buzones de correo y especificar las entradas que desea incluir para uno o varios usuarios. Cada entrada en el informe y el registro de auditoría incluye información acerca de quién realizó la acción y cuando realiza la acción, y si la acción se realizó correctamente. Para obtener más información, vea [exportar registros de auditoría de buzones de correo](https://go.microsoft.com/fwlink/p/?LinkID=404104).
