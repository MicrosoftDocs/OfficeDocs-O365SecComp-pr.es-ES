---
title: Recuperar un buzón inactivo en Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/21/2018
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 35d0ecdb-7cb0-44be-ad5c-69df2f8f8b25
description: 'Si un antiguo empleado vuelve a su organización, o si se contrata a un nuevo empleado para que realice las responsabilidades laborales de un empleado que ya no está en parte, puede recuperar el contenido del buzón inactivo en Office 365. Al recuperar un buzón inactivo, se convierte en un nuevo buzón que contiene el contenido del buzón inactivo. '
ms.openlocfilehash: c7f942c518dcc74a4bdb37d67e27e8a63879ab46
ms.sourcegitcommit: e7a776a04ef6ed5e287a33cfdc36aa2d72862b55
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/29/2019
ms.locfileid: "30999823"
---
# <a name="recover-an-inactive-mailbox-in-office-365"></a>Recuperar un buzón inactivo en Office 365

Un buzón inactivo (que es un tipo de buzón eliminado temporalmente) se usa para conservar el correo electrónico de un empleado anterior después de que abandona la organización. Si el empleado vuelve a su organización o si otro empleado lleva a cabo las responsabilidades laborales del antiguo empleado, hay dos formas de poner el contenido del buzón inactivo a disposición de un usuario: 
  
- **Recuperar un buzón inactivo** Si el antiguo empleado vuelve a su organización, o si se contrata a un nuevo empleado para que realice las responsabilidades laborales del antiguo empleado, puede recuperar el contenido del buzón inactivo. Este método convierte el buzón inactivo en un nuevo buzón activo que incluye el contenido del buzón inactivo. Una vez recuperado, el buzón inactivo deja de existir. Los procedimientos de este tema describen este método. 
    
- **Restaurar un buzón inactivo** Si otro empleado asume las responsabilidades laborales del antiguo empleado o si otro usuario necesita tener acceso al contenido del buzón inactivo, puede restaurar (o combinar) el contenido del buzón inactivo en un buzón existente. También puede restaurar el archivo desde un buzón inactivo. Para conocer los procedimientos de este método, vea [restaurar un buzón inactivo en Office 365](restore-an-inactive-mailbox.md).
    
Consulte la sección [Más información](#more-information) para obtener más detalles sobre las diferencias entre la recuperación y restauración de un buzón inactivo, así como para obtener una descripción de lo que sucede cuando se recupera un buzón inactivo.
  
> [!NOTE]
> Hemos pospuesto la fecha límite para crear reTenciones locales nuevas para convertir un buzón en inactivo. Pero en algún momento en el futuro, no podrá crear nuevas reTenciones locales en Exchange Online. En ese momento, solo se pueden usar las suspensiones por juicio y las directivas de retención de Office 365 para crear un buzón inactivo. No obstante, se seguirán admitiendo los buzones inactivos existentes que estén en conservación local y podrá seguir administrando las conservaciones locales de buzones inactivos. Esto incluye el cambio de la duración de las conservaciones locales y la eliminación de forma permanentemente de buzones inactivos al quitar la conservación local. 
  
## <a name="before-you-begin"></a>Antes de empezar

- Debe usar Exchange Online PowerShell para restaurar un buzón inactivo. No puede usar el Centro de administración de Exchange (EAC). Para obtener instrucciones paso a paso, consulte [conectarse a Exchange Online PowerShell](https://go.microsoft.com/fwlink/?linkid=396554).
    
- Ejecute el siguiente comando para mostrar información de identidad para los buzones inactivos en la organización. 

    ```
    Get-Mailbox -InactiveMailboxOnly | FL Name,DistinguishedName,ExchangeGuid,PrimarySmtpAddress
    ```

    Use la información devuelta por este comando para recuperar un buzón inactivo específico.
    
- Para obtener más información acerca de los buzones inactivos, consulte buzones inactivos [en Office 365](inactive-mailboxes-in-office-365.md).
    
## <a name="recover-an-inactive-mailbox"></a>Recuperar un buzón inactivo

Use el cmdlet **New-Mailbox** con el parámetro *InactiveMailbox* para recuperar un buzón inactivo. 
  
1. Cree una variable que contenga las propiedades del buzón inactivo. 
    
    ```
    $InactiveMailbox = Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox>
    ```
   
    > [!IMPORTANT]
    > En el comando anterior, use el valor de la propiedad **DistinguishedName** o **ExchangeGUID** para identificar el buzón inactivo. Estas propiedades son únicas para cada buzón en su organización, mientras que es posible que un buzón activo e inactivo puedan tener la misma dirección SMTP principal. 
  
2. En este ejemplo se usan las propiedades que se obtuvieron en el comando anterior y se recupera el buzón inactivo en un buzón activo para el usuario Ann Beebe. Asegúrese de que los valores especificados para los parámetros *Name* y *MicrosoftOnlineServicesID* son únicos en la organización. 

    ```
    New-Mailbox -InactiveMailbox $InactiveMailbox.DistinguishedName -Name annbeebe -FirstName Ann -LastName Beebe -DisplayName "Ann Beebe" -MicrosoftOnlineServicesID Ann.Beebe@contoso.com -Password (ConvertTo-SecureString -String 'P@ssw0rd' -AsPlainText -Force) -ResetPasswordOnNextLogon $true
    ```

    La dirección SMTP principal para el buzón inactivo recuperado tendrá el mismo valor que el especificado por el parámetro *MicrosoftOnlineServicesID* . 
    
Después de recuperar un buzón inactivo, también se crea una nueva cuenta de usuario de Office 365. Para activar la cuenta de usuario, se tiene que asignar una licencia. Para asignar una licencia en Centro de administración de Microsoft 365, consulte [Asignar o cancelar la asignación de licencias de Office 365 para empresas](https://go.microsoft.com/fwlink/p/?LinkId=276798).
  
## <a name="more-information"></a>Más información

- **¿Cuál es la diferencia principal entre recuperar y restaurar un buzón inactivo?** Al recuperar un buzón inactivo, el buzón se convierte básicamente en un buzón nuevo, el contenido y la estructura de carpetas del buzón inactivo se conservan y el buzón se vincula a una nueva cuenta de usuario. Una vez recuperado, el buzón inactivo deja de existir y los cambios realizados en el contenido en el nuevo buzón afectarán el contenido que se encontraba originalmente en retención en el buzón inactivo. Por el contrario, cuando se restaura un buzón inactivo, el contenido simplemente se copia a otro buzón de correo. El buzón inactivo se conserva y sigue siendo un buzón inactivo. Los cambios realizados en el contenido del buzón de destino no afectan el contenido original del buzón inactivo. El buzón inactivo se puede buscar todavía mediante el uso de la exhibición de documentos electrónicos local, su contenido se puede restaurar a otro buzón o se puede recuperar o eliminar en una fecha posterior. 
    
- **¿Qué sucede cuando se recupera un buzón inactivo?** Cuando se recupera un buzón inactivo, sucede lo siguiente: 
    
  - Se quita la retención por juicio (si estaba habilitada para el buzón inactivo).
    
  - Se quitan las retenciones locales. Esto significa que el buzón inactivo se quita como un buzón de origen de cualquier búsqueda de exhibición de documentos electrónicos locales o retenciones locales. 
    
  - El buzón inactivo se quita de cualquier directiva de retención de Office 365 que se le haya aplicado.
    
  - El período de recuperación de un solo elemento (definido por la propiedad de buzón **RetainDeletedItemsFor** ) se establece en 30 días. Normalmente, cuando se crea un nuevo buzón en Exchange Online, este período de retención se establece en 14 días. Si establece esto en el valor máximo de 30 días, tendrá más tiempo para recuperar los datos que se han eliminado (o depurado) de forma permanente del buzón inactivo. También puede deshabilitar la recuperación de un solo elemento o volver a establecer el período de recuperación de un solo elemento en el valor predeterminado de 14 días. Para obtener más información, consulte [Enable or disable single item recovery for a mailbox](https://go.microsoft.com/fwlink/?linkid=856769).
    
  - La suspensión de retención está habilitada y la duración de la suspensión de retención se establece en 30 días. Esto significa que la Directiva de retención de Exchange predeterminada y todas las directivas de retención de Office 365 de toda la organización o de Exchange que se asignan al nuevo buzón no se procesarán durante 30 días. Esto proporciona al empleado que vuelve o al nuevo propietario del buzón inactivo recuperado el tiempo suficiente para administrar los mensajes antiguos. De lo contrario, la Directiva de retención de Exchange u Office 365 puede eliminar elementos de buzón antiguos (o mover elementos al buzón de archivo, si está habilitado) que han expirado según la configuración establecida para las directivas de retención de Exchange u Office 365. TransCurrido el plazo de 30 días, la suspensión de **** la retención se establece en **false**y el Asistente para carpeta administrada comienza a procesar las directivas asignadas al buzón de correo. Si no necesita este tiempo adicional, solo puede quitar la suspensión de retención. Como alternativa, puede aumentar la duración de la suspensión de retención mediante el comando **Set-Mailbox -EndDateForRetentionHold**. Para obtener más información, consulte [Place a mailbox on retention hold](https://go.microsoft.com/fwlink/?linkid=856300).
    
- **Si necesita conservar el estado original del buzón inactivo, coloque una retención en el buzón recuperado.** Para evitar que el nuevo propietario del buzón o la Directiva de retención eliminen permanentemente los mensajes del buzón inactivo recuperado, puede poner el buzón en retención por juicio para obtener más información, vea [poner un buzón de correo en](https://go.microsoft.com/fwlink/?linkid=856286)retención por juicio.
    
- **¿Qué identificador de usuario se puede usar cuando se recupera un buzón inactivo?** Al recuperar un buzón inactivo, el valor que especifique para el parámetro *MicrosoftOnlineServicesID* puede ser diferente del original que estaba asociado con el buzón inactivo. También se puede usar el identificador de usuario original. Pero, como se mencionó anteriormente, asegúrese de que los valores usados para *nombre* y *MicrosoftOnlineServicesID* son únicos dentro de la organización al recuperar el buzón inactivo. 
    
- **¿Qué sucede si no ha expirado el período de retención de buzón para el buzón inactivo?** Si un buzón inactivo se eliminó temporalmente hace menos de 30 días, no se puede usar el comando **New-Mailbox -InactiveMailbox** para recuperarlo. Para recuperarlo es necesario restaurar la cuenta de usuario de Office 365 correspondiente. Para más información, vea [Suprimir o restaurar usuarios](https://go.microsoft.com/fwlink/p/?LinkId=279162).
    
- **¿Cómo saber si ha expirado el período de retención del buzón eliminado temporalmente para un buzón inactivo?** Ejecute el siguiente comando. 
    
    ```
    Get-Mailbox -InactiveMailboxOnly <identity of inactive mailbox> | FL ExternalDirectoryObjectId
  ```

    Si no hay un valor para la propiedad **ExternalDirectoryObjectId**, el período de retención del buzón ha expirado y puede recuperar el buzón inactivo ejecutando el comando **New-Mailbox -InactiveMailbox**. Si hay un valor para la propiedad **ExternalDirectoryObjectId**, no ha expirado el período de retención del buzón eliminado temporalmente y tiene que recuperar el buzón de correo restaurando la cuenta de usuario de Office 365. Consulte [Suprimir o restaurar usuarios](https://go.microsoft.com/fwlink/p/?LinkId=279162).
    
- **Considere la posibilidad de habilitar el buzón de archivo después de recuperar un buzón inactivo.** Esto permite que el usuario que vuelve o el nuevo empleado muevan mensajes antiguos al buzón de archivo. Y cuando expire la suspensión de retención, la Directiva de archivo que forma parte de la Directiva de retención de Exchange predeterminada asignada a los buzones de correo de Exchange Online moverá los elementos que tengan dos años o más con el buzón de archivo. Si no habilita el buzón de archivo, los elementos de más de dos años permanecerán en el buzón principal del usuario. Para obtener más información, consulte [Habilitar buzones de archivo en el centro &amp; de seguridad y cumplimiento de Office 365](enable-archive-mailboxes.md).
 