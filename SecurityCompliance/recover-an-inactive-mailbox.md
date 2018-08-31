---
title: Recuperar un buzón inactivo en Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/21/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 35d0ecdb-7cb0-44be-ad5c-69df2f8f8b25
description: 'Si un empleado anterior devuelve a su organización, o si se contrata a un nuevo empleado a cabo en las responsabilidades de trabajo de un empleado abandonada, puede recuperar el contenido del buzón de correo inactivo en Office 365. Al recuperar un buzón inactivo, se convierte a un nuevo buzón de correo que contiene el contenido del buzón de correo inactivo. '
ms.openlocfilehash: dcc84e44454a75f8b4dac953599632d632f340b9
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22536754"
---
# <a name="recover-an-inactive-mailbox-in-office-365"></a>Recuperar un buzón inactivo en Office 365

Un buzón inactivo (que es un tipo de buzón eliminado temporalmente) se usa para conservar el correo electrónico de un empleado anterior después de que abandona la organización. Si ese empleado devuelve a su organización o si otro empleado tarda en las responsabilidades de cargo del empleado anterior, hay dos formas que puede realizar el contenido del buzón de correo inactivo disponibles para un usuario: 
  
- **Recuperar un buzón inactivo** Si devuelve el antiguo empleado para su organización, o si se contrata a un nuevo empleado a cabo en las responsabilidades de cargo del empleado anterior, puede recuperar el contenido del buzón de correo inactivo. Este método convierte el buzón de correo inactivo a un buzón nuevo, activo que contiene el contenido del buzón de correo inactivo. Una vez recuperado, ya no existe el buzón de correo inactivo. Los procedimientos descritos en este tema describen en este método. 
    
- **Restaurar un buzón inactivo** Si lleva a otro empleado en las responsabilidades de cargo del empleado anterior, o si otro usuario necesita obtener acceso al contenido del buzón de correo inactivo, puede restaurar (o combinación) el contenido del buzón de correo inactivo a un buzón existente. También puede restaurar el archivo desde un buzón de correo inactivo. Para los procedimientos de este método, vea [restaurar un buzón inactivo en Office 365](restore-an-inactive-mailbox.md).
    
Consulte la sección [Más información](recover-an-inactive-mailbox.md#moreinfo) para obtener más detalles sobre las diferencias entre la recuperación y restauración de un buzón inactivo, así como para obtener una descripción de lo que sucede cuando se recupera un buzón inactivo.
  
> [!NOTE]
> Nos hemos pospuso la fecha límite para la creación de nuevos suspensiones en contexto para definir un buzón de correo como inactiva. Pero en algún momento en el futuro, no podrá crear nuevos suspensiones en contexto en Exchange Online. En ese momento, sólo las directivas de retención por litigio contiene y Office 365 pueden usarse para crear un buzón de correo inactivo. Sin embargo, aún se admitirá buzones inactivos existentes que se encuentran en retención local, y puede continuar administrar el suspensiones en contexto en buzones de correo inactivos. Esto incluye el cambio de la duración de una retención local y eliminar permanentemente un buzón inactivo quitando la retención local. 
  
## <a name="before-you-begin"></a>Antes de empezar

- Se debe usar Exchange Online PowerShell para restaurar un buzón de correo inactivo. No puede usar el centro de administración de Exchange (EAC). Para obtener instrucciones detalladas, vea [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/?linkid=396554).
    
- Ejecute el siguiente comando para mostrar información de identidad para los buzones inactivos en la organización. 

    ```
    Get-Mailbox -InactiveMailboxOnly | FL Name,DistinguishedName,ExchangeGuid,PrimarySmtpAddress
    ```

    Use la información devuelta por este comando para recuperar un buzón inactivo específico.
    
- Para obtener más información acerca de los buzones de correo inactivos, vea [buzones inactivos en Office 365](inactive-mailboxes-in-office-365.md).
    
## <a name="recover-an-inactive-mailbox"></a>Recuperar un buzón inactivo

Utilice el cmdlet **New-Mailbox** con el parámetro *InactiveMailbox* para recuperar un buzón de correo inactivo. 
  
1. Cree una variable que contenga las propiedades del buzón inactivo. 
    
    ```
    $InactiveMailbox = Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox>
    ```
   
    > [!IMPORTANT]
    > En el comando anterior, use el valor de la propiedad **DistinguishedName** o **ExchangeGUID** para identificar el buzón inactivo. Estas propiedades son únicas para cada buzón en su organización, mientras que es posible que un buzón activo e inactivo puedan tener la misma dirección SMTP principal. 
  
2. En este ejemplo se utilizan las propiedades que se obtienen en el comando anterior y se recupera el buzón de correo inactivo a un buzón para el usuario Ann Beebe activo. Asegúrese de que los valores especificados para los parámetros de *nombre* y *MicrosoftOnlineServicesID* son únicos dentro de la organización. 

    ```
    New-Mailbox -InactiveMailbox $InactiveMailbox.DistinguishedName -Name annbeebe -FirstName Ann -LastName Beebe -DisplayName "Ann Beebe" -MicrosoftOnlineServicesID Ann.Beebe@contoso.com -Password (ConvertTo-SecureString -String 'P@ssw0rd' -AsPlainText -Force) -ResetPasswordOnNextLogon $true
    ```

    La dirección SMTP principal para el buzón de correo inactivo recuperada tendrá el mismo valor que el especificado por el parámetro *MicrosoftOnlineServicesID* . 
    
Después de recuperar un buzón inactivo, también se crea una nueva cuenta de usuario de Office 365. Para activar la cuenta de usuario, se tiene que asignar una licencia. Para asignar una licencia en el centro de administración de Office 365, consulte [Asignar o cancelar la asignación de licencias de Office 365 para empresas](https://go.microsoft.com/fwlink/p/?LinkId=276798).
  
## <a name="more-information"></a>Más información

- **¿Cuál es la diferencia principal entre recuperar y restaurar un buzón inactivo?** Al recuperar un buzón inactivo, el buzón se convierte básicamente en un buzón nuevo, el contenido y la estructura de carpetas del buzón inactivo se conservan y el buzón se vincula a una nueva cuenta de usuario. Una vez recuperado, el buzón inactivo deja de existir y los cambios realizados en el contenido en el nuevo buzón afectarán el contenido que se encontraba originalmente en retención en el buzón inactivo. Por el contrario, cuando se restaura un buzón inactivo, el contenido simplemente se copia a otro buzón de correo. El buzón inactivo se conserva y sigue siendo un buzón inactivo. Los cambios realizados en el contenido del buzón de destino no afectan el contenido original del buzón inactivo. El buzón inactivo se puede buscar todavía mediante el uso de la exhibición de documentos electrónicos local, su contenido se puede restaurar a otro buzón o se puede recuperar o eliminar en una fecha posterior. 
    
- **¿Qué sucede cuando se recupera un buzón inactivo?** Cuando se recupera un buzón inactivo, sucede lo siguiente: 
    
  - Se quita la retención por juicio (si estaba habilitada para el buzón inactivo).
    
  - Se quitan las retenciones locales. Esto significa que el buzón inactivo se quita como un buzón de origen de cualquier búsqueda de exhibición de documentos electrónicos locales o retenciones locales. 
    
  - Se ha quitado el buzón de correo inactivo de las directivas de retención de Office 365 ese where que se ha aplicado.
    
  - El período de recuperación de un solo elemento (definido por la propiedad de buzón **RetainDeletedItemsFor** ) se establece en 30 días. Normalmente, cuando se crea un nuevo buzón en Exchange Online, este período de retención se establece en 14 días. Si establece esto en el valor máximo de 30 días, tendrá más tiempo para recuperar los datos que se han eliminado (o depurado) de forma permanente del buzón inactivo. También puede deshabilitar la recuperación de un solo elemento o volver a establecer el período de recuperación de un solo elemento en el valor predeterminado de 14 días. Para obtener más información, consulte [Enable or disable single item recovery for a mailbox](https://go.microsoft.com/fwlink/?linkid=856769).
    
  - Está habilitada la suspensión de retención, y la duración de la suspensión de retención se establece en 30 días. Esto significa la directiva de retención de Exchange de forma predeterminada y cualquier Office 365 toda la Exchange o de toda la organización no se procesará las directivas de retención que se asignan al nuevo buzón durante 30 días. Esto da el empleado devolución o el nuevo propietario de la hora de buzón de correo inactivo recuperada para administrar los mensajes antiguos. De lo contrario, la directiva de retención Exchange u Office 365 podría eliminar elementos antiguos de buzón de correo (o mover elementos en el buzón de archivo, si está habilitada) que han caducado en función de las opciones configuradas para las directivas de retención Exchange u Office 365. Después de 30 días, expira la suspensión de retención, la propiedad del buzón de correo de **RetentionHoldEnabled** está establecida en **False**y el Asistente para carpeta administrada inicia el procesamiento de las directivas asignadas al buzón. Si no necesita este tiempo adicional, se puede quitar la suspensión de retención. Como alternativa, puede aumentar la duración de la suspensión de retención mediante el comando **Set-Mailbox-EndDateForRetentionHold** . Para obtener más información, vea [conservación un buzón de correo en retención](https://go.microsoft.com/fwlink/?linkid=856300).
    
- **Colocar una suspensión en el buzón de correo recuperado si necesita conservar el estado original del buzón de correo inactivo.** Para evitar que el nuevo propietario del buzón o la directiva de retención eliminar permanentemente todos los mensajes desde el buzón de correo inactivo recuperada, puede colocar el buzón de correo en suspensión por litigio para obtener más información, vea [colocar un buzón en suspensión por litigio](https://go.microsoft.com/fwlink/?linkid=856286).
    
- **Qué identificador de usuario puede usar al recuperar un buzón inactivo?** Al recuperar un buzón inactivo, el valor que especifique para el parámetro *MicrosoftOnlineServicesID* puede ser diferente de la original que estaba asociado con el buzón de correo inactivo. También puede usar el identificador de usuario original. Pero, como se ha indicado anteriormente, asegúrese de que los valores utilizados para *nombre* y *MicrosoftOnlineServicesID* son únicos dentro de la organización al recuperar el buzón de correo inactivo. 
    
- **¿Qué sucede si no ha expirado el período de retención de buzón para el buzón inactivo?** Si un buzón inactivo se eliminó temporalmente hace menos de 30 días, no se puede usar el comando **New-Mailbox -InactiveMailbox** para recuperarlo. Para recuperarlo es necesario restaurar la cuenta de usuario de Office 365 correspondiente. Para más información, vea [Suprimir o restaurar usuarios](https://go.microsoft.com/fwlink/p/?LinkId=279162).
    
- **¿Cómo saber si ha expirado el período de retención del buzón eliminado temporalmente para un buzón inactivo?** Ejecute el siguiente comando. 
    
    ```
    Get-Mailbox -InactiveMailboxOnly <identity of inactive mailbox> | FL ExternalDirectoryObjectId
  ```

    Si no hay un valor para la propiedad **ExternalDirectoryObjectId**, el período de retención del buzón ha expirado y puede recuperar el buzón inactivo ejecutando el comando **New-Mailbox -InactiveMailbox**. Si hay un valor para la propiedad **ExternalDirectoryObjectId**, no ha expirado el período de retención del buzón eliminado temporalmente y tiene que recuperar el buzón de correo restaurando la cuenta de usuario de Office 365. Consulte [Suprimir o restaurar usuarios](https://go.microsoft.com/fwlink/p/?LinkId=279162).
    
- **Considere la posibilidad de habilitar el buzón de archivo después de recuperar un buzón de correo inactivo.** Esto permite a la devolución de usuario o nuevo empleado mover mensajes antiguos para el buzón de archivo. Y cuando expire la suspensión de retención, la directiva de archivo que forma parte de la directiva de retención de Exchange predeterminado asignada a los buzones de correo moverán los elementos que son dos años Exchange Online o anterior para el buzón de archivo. Si no habilita el buzón de archivo, los elementos más de dos años permanecerá en el buzón del usuario principal. Para obtener más información, vea [Habilitar buzones de archivo en la seguridad de Office 365 &amp; centro de cumplimiento](enable-archive-mailboxes.md).
 