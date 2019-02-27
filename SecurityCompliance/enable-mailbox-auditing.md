---
title: Habilitar la auditoría de buzones de correo en Office 365
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
- MET150
ms.assetid: aaca8987-5b62-458b-9882-c28476a66918
description: En Office 365, puede activar el registro de auditoría de buzones para registrar el acceso a buzones por parte de los propietarios, delegados y administradores de buzones de correo. De forma predeterminada, la auditoría de buzones de correo en Office 365 no está activada. Después de habilitar el registro de auditoría de buzones de correo para un buzón de correo, puede buscar en el registro de auditoría de Office 365 actividades realizadas en el buzón.
ms.openlocfilehash: a9bc84bad8532dd546d5ce3e2f149151967050d6
ms.sourcegitcommit: baf23be44f1ed5abbf84f140b5ffa64fce605478
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/26/2019
ms.locfileid: "30295923"
---
# <a name="enable-mailbox-auditing-in-office-365"></a>Habilitar la auditoría de buzones de correo en Office 365
  
En Office 365, puede activar el registro de auditoría de buzones para registrar el acceso a buzones por parte de los propietarios, delegados y administradores de buzones de correo. De forma predeterminada, la auditoría de buzones de correo en Office 365 no está activada. Esto significa que los eventos de auditoría de buzones de correo no aparecerán en los resultados al buscar en el registro de auditoría de Office 365 la actividad de buzón. Pero después de activar el registro de auditoría de buzón de correo de un usuario, puede buscar en el registro de auditoría la actividad de buzón. Además, cuando se activa el registro de auditoría de buzones de correo, algunas acciones que realizan los administradores, los delegados y los propietarios se registran de forma predeterminada. Para registrar (y, a continuación, buscar) acciones adicionales, consulte el paso 3.

## <a name="before-you-begin"></a>Antes de empezar
  
- Debe usar Exchange Online PowerShell para habilitar el registro de auditoría de buzones de correo. No puede usar el centro de seguridad &amp; y cumplimiento de Office 365 en el centro de administración de Exchange.
    
- No puede habilitar el registro de auditoría de buzones de correo para el buzón de correo que está asociado a un grupo de Office 365 o a un equipo en Microsoft Teams.
    
- Un administrador al que se haya asignado el permiso Acceso total en el buzón de un usuario se considera usuario delegado.
  
## <a name="step-1-connect-to-exchange-online-powershell"></a>Paso 1: conectarse a Exchange Online PowerShell

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

Después de conectarse a la organización de Exchange Online, use PowerShell para habilitar el registro de auditoría de buzones de correo para un buzón de correo. Como alternativa, puede habilitar la auditoría de buzones de correo para todos los buzones de la organización.
  
En este ejemplo se habilita el registro de auditoría de buzón de correo de Pilar Pinilla.
  
```
Set-Mailbox -Identity "Pilar Pinilla" -AuditEnabled $true
```

En este ejemplo se habilita el registro de auditoría de todos los buzones de correo de los usuarios de su organización.
  
```
Get-Mailbox -ResultSize Unlimited -Filter {RecipientTypeDetails -eq "UserMailbox"} | Set-Mailbox -AuditEnabled $true
```
  
## <a name="step-3-specify-owner-actions-to-audit"></a>Paso 3: Especificar las acciones de propietario que se auditarán

Cuando se habilita la auditoría para un buzón de correo, algunas acciones realizadas por el propietario del buzón se auditan de forma predeterminada. Tiene que especificar otras acciones de propietario que se van a auditar. Consulte la tabla de la sección [acciones de auditoría](#mailbox-auditing-actions) de buzones de correo para obtener una lista y una descripción de las acciones de propietario que se registran de forma predeterminada y las otras acciones que se pueden auditar. 
  
En este ejemplo se agregan las acciones de propietario **MailboxLogin** y **HardDelete** al buzón de correo de la auditoría del buzón de Pilar Pinilla. En este ejemplo se supone que ya se ha habilitado la auditoría de buzones para este buzón. 

```
Set-Mailbox "Pilar Pinilla" -AuditOwner @{Add="MailboxLogin","HardDelete"}
```

En este ejemplo se habilita el registro de auditoría de buzón de correo de Felipe García y se especifica que sólo se registrará la acción **MailboxLogin** realizada por el propietario del buzón. Tenga en cuenta que en este ejemplo se sobrescribe la acción UpdateFolderPermissions predeterminada. 
  
```
Set-Mailbox "Don Hall" -AuditEnabled $true -AuditOwner MailboxLogin
```
   
En este ejemplo se agregan las acciones de propietario **MailboxLogin**, **HardDelete**y **SoftDelete** a todos los buzones de correo de la organización. En este ejemplo se supone que ya se ha habilitado la auditoría de buzones para todos los buzones. 
  
```
Get-Mailbox -ResultSize Unlimited -Filter {RecipientTypeDetails -eq "UserMailbox"} | Set-Mailbox -AuditOwner @{Add="MailboxLogin","HardDelete","SoftDelete"}
```
  
## <a name="how-do-you-know-this-worked"></a>¿Cómo saber si el proceso se completó correctamente?

Para comprobar que se haya habilitado correctamente el registro de auditoría de buzones de correo, utilice el cmdlet **Get-Mailbox** para recuperar la configuración de auditoría de ese buzón. 
  
En este ejemplo se recupera la configuración de auditoría de Pilar Pinilla.

```
Get-Mailbox "Pilar Pinilla"| FL Audit*
```
   
En este ejemplo se recupera la configuración de auditoría de todos los buzones de correo de los usuarios de la organización.

```
Get-Mailbox -ResultSize Unlimited -Filter {RecipientTypeDetails -eq "UserMailbox"} | FL Name,Audit*
```
   
Un valor de **true** para la propiedad **AuditEnabled** comprueba que el registro de auditoría de buzones de correo está habilitado. 
    
## <a name="mailbox-auditing-actions"></a>Acciones de auditoría de buzones
  
En la siguiente tabla se enumeran las acciones que el registro de auditoría de buzones de correo puede registrar. La tabla incluye la acción que se puede registrar para los distintos tipos de inicio de sesión de usuario. En la tabla, un **no** indica que no se puede registrar una acción para ese tipo de inicio de sesión. Un asterisco ( **\*** ) indica que la acción se registra de forma predeterminada cuando el registro de auditoría del buzón de correo está habilitado para el buzón. 
  
|**Acción**|**Descripción**|**Administrador**|**Delegado\*\*\***|**Propietario**|
|:-----|:-----|:-----|:-----|:-----|
|**Copiar** <br/> |Un mensaje se copió en otra carpeta.  <br/> |Sí  <br/> |No  <br/> |No  <br/> |
|**Create** <br/> |Se crea un elemento en la carpeta calendario, contactos, notas o tareas del buzón de correo; por ejemplo, se crea una nueva convocatoria de reunión. Tenga en cuenta que no se audita la creación, el envío o la recepción de un mensaje. Además, no se audita la creación de una carpeta de buzón de correo.  <br/> |Sí\*  <br/> |Sí\*  <br/> |Sí  <br/> |
|**FolderBind** <br/> |Se tuvo acceso a una carpeta de buzón de correo. Esta acción también se registra cuando el administrador o un delegado abren el buzón de correo.  <br/> |Sí  <br/> |Sí\*\*  <br/> |No  <br/> |
|**HardDelete** <br/> |Un mensaje se purgó de la carpeta Elementos recuperables.  <br/> |Sí\*  <br/> |Sí\*  <br/> |Sí  <br/> |
|**MailboxLogin** <br/> |El usuario inició sesión en su buzón.  <br/> |No  <br/> |No  <br/> |Sí  <br/> |
|**MessageBind** <br/> |Un mensaje se consultó en el panel de vista previa o se abrió.  <br/> |Sí  <br/> |No  <br/> |No  <br/> |
|**Mover** <br/> |Un mensaje se movió a otra carpeta.  <br/> |Sí  <br/> |Sí   <br/> |Sí   <br/> |
|**MoveToDeletedItems** <br/> |Un mensaje se eliminó y se movió a la carpeta Elementos eliminados.  <br/> |Sí\*  <br/> |Sí\*  <br/> |Sí  <br/> |
|**SendAs** <br/> |Un mensaje se envió mediante el permiso SendAs. Esto significa que otro usuario envió el mensaje como si procediera del propietario del buzón.  <br/> |Sí\*  <br/> |Sí\*  <br/> |No  <br/> |
|**SendOnBehalf** <br/> |Un mensaje se envió mediante el permiso SendOnBehalf. Esto significa que otro usuario envió el mensaje en nombre del propietario del buzón. El mensaje indica el destinatario en nombre de quien se envió el mensaje y quién lo envió realmente.  <br/> |Sí\*  <br/> |Sí\*  <br/> |No  <br/> |
|**SoftDelete** <br/> |Un mensaje se eliminó permanentemente o se eliminó de la carpeta Elementos eliminados. Los elementos eliminados de forma temporal se mueven a la carpeta Elementos recuperables.  <br/> |Sí\*  <br/> |Sí\*  <br/> |Sí  <br/> |
|**Actualizar** <br/> |Se cambió un mensaje o sus propiedades.  <br/> |Sí\*  <br/> |Sí\*  <br/> |Sí  <br/> |
|**UpdateCalendarDelegation** <br/> |Se asignó una delegación de calendario a un buzón. La delegación de calendario da a otra persona en la misma organización permisos para administrar el calendario del propietario del buzón.  <br/> |Sí\*  <br/> |No  <br/> |Sí\*  <br/> |
|**UpdateFolderPermissions** <br/> |Se ha cambiado un permiso de carpeta. Los permisos de carpeta controlan qué usuarios de la organización pueden tener acceso a las carpetas de un buzón de correo y los mensajes que se encuentran en dichas carpetas.  <br/> |Sí\*  <br/> |Sí\*  <br/> |Sí\*  <br/> |
|**UpdateInboxRules** <br/> |Se ha agregado, quitado o cambiado una regla de bandeja de entrada. Las reglas de la bandeja de entrada se usan para procesar mensajes en la bandeja de entrada del usuario en función de las condiciones especificadas y emprender acciones cuando se cumplen las condiciones de una regla, como mover un mensaje a una carpeta especificada o eliminar un mensaje.  <br/> |Sí\*  <br/> |Sí\*  <br/> |Sí\*  <br/> |
   
> [!NOTE]
> <sup>\*</sup> Se audita de forma predeterminada si la auditoría está habilitada para un buzón.<br/><br/>  <sup>\*\*</sup>Las entradas para las acciones de enlace de carpeta realizadas por los delegados están consolidadas. Se genera una entrada de registro para el acceso a la carpeta individual en un período de 24 horas.<br/><br/><sup>\*\*\*</sup>Un administrador al que se haya asignado el permiso acceso total en el buzón de un usuario se considera un usuario delegado. 
  
Si ya no necesita que se auditen determinados tipos de acciones de buzón de correo, debe modificar la configuración del registro de auditoría del buzón para deshabilitar esas acciones. Las entradas de registro existentes no se purgan hasta que se alcanza el límite de antigüedad de retención para las entradas del registro de auditoría. Para obtener más información acerca de la antigüedad de retención de las entradas del registro de auditoría, consulte la sección "antes de empezar" en [Buscar el registro de auditoría en el centro de seguridad _AMP_ cumplimiento de Office 365](search-the-audit-log-in-security-and-compliance.md#before-you-begin).
  
## <a name="more-infotab"></a>[Más información](#tab/)
  
- Use el registro de auditoría de Office 365 para buscar la actividad del buzón que se ha registrado. Puede buscar actividad para un buzón de usuario específico. En la siguiente captura de pantalla se muestra una lista de las actividades de buzón de correo que puede buscar en el registro de auditoría de Office 365. Tenga en cuenta que estas actividades son las mismas acciones que se describen en la sección "acciones de auditoría de buzones de correo" de este tema.
    
    ![Puede buscar en el registro de auditoría de Office 365 las acciones de auditoría de buzones de correo seleccionando "actividades de buzón de Exchange" en la lista desplegable de actividades](media/fadc34f8-9de2-4688-8b1a-bc5540e69a23.png)
  
    En la tabla siguiente se describe cada actividad de buzón de correo que se puede buscar y se muestra la acción de auditoría de buzón correspondiente.
    
    |**Actividad en el registro de auditoría**|**Acción de auditoría de buzón**|
    |:-----|:-----|
    |Elemento de buzón creado  <br/> |Crear  <br/> |
    |Mensajes copiados a otra carpeta  <br/> |Copiar  <br/> |
    |Usuario que ha iniciado sesión en el buzón  <br/> |MailboxLogin  <br/> |
    |Mensaje enviado con los permisos enviar en nombre de  <br/> |SendOnBehalf  <br/> |
    |Mensajes purgados del buzón  <br/> |HardDelete  <br/> |
    |Mensajes movidos a la carpeta elementos eliminados  <br/> |MoveToDeletedItems  <br/> |
    |Mensajes movidos a otra carpeta  <br/> |Mover  <br/> |
    |Mensaje enviado con los permisos enviar como  <br/> |SendAs  <br/> |
    |Mensaje actualizado  <br/> |Update  <br/> |
    |Mensajes eliminados de la carpeta elementos eliminados  <br/> |SoftDelete  <br/> |
    |Permisos agregados a la carpeta  <br/> |UpdateFolderPermissions  <br/> |
    |Permisos modificados de la carpeta  <br/> |UpdateFolderPermissions  <br/> |
    |Permisos quitados de la carpeta  <br/> |UpdateFolderPermissions  <br/> |
    |Se agregó o quitó un usuario con acceso delegado a la carpeta calendario  <br/> |UpdateCalendarDelegation  <br/> |
   
    Tenga en cuenta que los **permisos de buzón de delegado agregados** y las actividades de permisos de buzón de correo de **delegado** que se muestran en la captura de pantalla anterior no están relacionados con acciones de auditoría de buzón. Indican si un administrador ha asignado o quitado el permiso de buzón de correo de FullAccess. 
    
    Para obtener información sobre el registro de auditoría de Office 365, consulte [Buscar el registro de auditoría en &amp; el centro de seguridad y cumplimiento de Office 365](search-the-audit-log-in-security-and-compliance.md).
    
- Solo se considera que un administrador ha tenido acceso a un buzón en los escenarios siguientes:
    
  - La exhibición de documentos electrónicos local en Exchange online o la búsqueda de contenido en Office 365 se usa para buscar en un buzón.
    
  - [Microsoft Exchange Server MAPI Editor](https://go.microsoft.com/fwlink/p/?linkId=204086) se usa para acceder al buzón de correo. 
    
- Al habilitar el registro de auditoría para un buzón de correo, también se pueden especificar las acciones de usuario (por ejemplo, acceso, traslado o eliminación de mensajes) que se registrarán para cada tipo de inicio de sesión (administrador, delegado o propietario). 
    
- Para deshabilitar el registro de auditoría de buzones de correo, ejecute el comando siguiente:

  ```
  Set-Mailbox -Identity <identity of mailbox> -AuditEnabled $false
   ```

- Las acciones que se auditan para cada tipo de usuario no se muestran cuando se ejecuta el cmdlet **Get-Mailbox** . Pero puede ejecutar los siguientes comandos para mostrar todas las acciones auditadas para un tipo de inicio de sesión de usuario específico. 

    ```
    Get-Mailbox <identity of mailbox> | Select-Object -ExpandProperty AuditAdmin
    ```

    ```
    Get-Mailbox <identity of mailbox> | Select-Object -ExpandProperty AuditDelegate
    ```

    ```
    Get-Mailbox <identity of mailbox> | Select-Object -ExpandProperty AuditOwner
    ```

- También puede exportar un registro de auditoría de buzones de correo y especificar las entradas que se incluirán en uno o más usuarios. Cada entrada del informe y del registro de auditoría incluye información sobre quién llevó a cabo la acción y cuándo, la acción que se ha realizado y si la acción se realizó correctamente. Para obtener más información, vea [exportar registros de auditoría](https://go.microsoft.com/fwlink/p/?LinkID=404104)de buzones de correo.
