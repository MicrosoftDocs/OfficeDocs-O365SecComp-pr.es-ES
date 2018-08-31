---
title: Restaurar un buzón inactivo en Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 8/28/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 97e06a7a-ef9a-4ce8-baea-18b9e20449a3
description: Si un nuevo empleado u otro usuario necesita obtener acceso al contenido de un buzón inactivo en Office 365, puede restaurar (o combinación) el contenido del buzón de correo inactivo a un buzón existente.
ms.openlocfilehash: e0add2b63a48edc27795143324c83153b15dcf8c
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22535671"
---
# <a name="restore-an-inactive-mailbox-in-office-365"></a>Restaurar un buzón inactivo en Office 365

Un buzón inactivo (que es un tipo de buzón eliminado temporalmente) se utiliza para retener el correo electrónico de un empleado anterior después de que abandona la organización. Si lleva a otro empleado en las responsabilidades de cargo del empleado abandonada o si ese empleado devuelve a su organización, hay dos formas que puede realizar el contenido del buzón de correo inactivo disponibles para un usuario: 
  
- **Restaurar un buzón inactivo** Si otro empleado asume las responsabilidades del empleado que se marchó o si otro usuario necesita acceso al contenido del buzón inactivo, puede restaurar (o combinar) el contenido del buzón inactivo en un buzón existente. También puede restaurar el archivo desde un buzón inactivo. Una vez restaurado, el buzón inactivo se conserva y se mantiene como un buzón inactivo. En este tema se describen los procedimientos para restaurar un buzón inactivo. 
    
- **Recuperar un buzón inactivo** Si el empleado abandonado devuelve a su organización, o si se contrata a un nuevo empleado a cabo en las responsabilidades de cargo del empleado abandonada, puede recuperar el contenido del buzón de correo inactivo. Este método convierte el buzón de correo inactivo en un nuevo buzón de correo que contiene el contenido del buzón de correo inactivo. Una vez recuperado, ya no existe el buzón de correo inactivo. Para los procedimientos paso a paso, vea [recuperar un buzón inactivo en Office 365](recover-an-inactive-mailbox.md).
    
Vea la sección **obtener más información** en este artículo para obtener más información acerca de las diferencias entre la restauración y recuperación de un buzón de correo inactivo. 
  
## <a name="before-you-begin"></a>Antes de empezar

- Se debe usar Exchange Online PowerShell para restaurar un buzón de correo inactivo. No puede usar el centro de administración de Exchange (EAC). Para obtener instrucciones detalladas, vea [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/?linkid=396554).
    
- Ejecute el siguiente comando en Exchange Online PowerShell para obtener información de identidad para los buzones inactivos en su organización. 
    
    ```
    Get-Mailbox -InactiveMailboxOnly | FL Name,DistinguishedName,ExchangeGuid,PrimarySmtpAddress
    ```

     Use la información devuelta por este comando para restaurar un buzón inactivo específico.
    
- Para obtener más información acerca de los buzones de correo inactivos, vea [buzones inactivos en Office 365](inactive-mailboxes-in-office-365.md).
    
## <a name="restore-an-inactive-mailbox"></a>Restaurar un buzón inactivo

Use el cmdlet **New-MailboxRestoreRequest** con los parámetros  _SourceMailbox_ y  _TargetMailbox_ para restaurar el contenido de un buzón inactivo en un buzón existente. Para obtener más información sobre el uso de este cmdlet, vea [New-MailboxRestoreRequest](https://go.microsoft.com/fwlink/?linkid=856298).
  
1. Cree una variable que contenga las propiedades del buzón inactivo. 
    
    ```
    $InactiveMailbox = Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox>
    ```

    > [!IMPORTANT]
    > En el comando anterior, use el valor de la propiedad **DistinguishedName** o **ExchangeGUID** para identificar el buzón inactivo. Estas propiedades son únicas para cada buzón en su organización, mientras que es posible que un buzón activo e inactivo puedan tener la misma dirección SMTP principal. 
  
2. Restaurar el contenido del buzón inactivo en un buzón existente. El contenido del buzón inactivo (buzón de origen) se combinará en las carpetas correspondientes en el buzón existente (buzón de destino).
    
    ```
    New-MailboxRestoreRequest -SourceMailbox $InactiveMailbox.DistinguishedName -TargetMailbox newemployee@contoso.com -AllowLegacyDNMismatch
    ```
   
   Como alternativa, puede especificar una carpeta de nivel superior en el buzón de destino en el que se va a restaurar el contenido del buzón inactivo. Si la carpeta de destino especificada o la estructura de carpetas de destino no existe en el buzón de destino, se crea durante el proceso de restauración. 
    
    En este ejemplo se copian los elementos del buzón y las subcarpetas de un buzón inactivo a una carpeta denominada "Buzón inactivo" en la estructura de carpetas de nivel superior del buzón de destino.
    
   ```
   New-MailboxRestoreRequest -SourceMailbox $InactiveMailbox.DistinguishedName -TargetMailbox newemployee@contoso.com -TargetRootFolder "Inactive Mailbox" -AllowLegacyDNMismatch
   ```
  
## <a name="restore-the-archive-from-an-inactive-mailbox"></a>Restaurar el archivo a partir de un buzón inactivo

Si un buzón inactivo tiene un buzón de archivo, también puede restaurarlo en el buzón de archivo de un buzón existente. Para restaurar el archivo desde un buzón inactivo, tiene que agregar los modificadores  _SourceIsArchive_ y  _TargetIsAchive_ al comando utilizado para restaurar un buzón inactivo. 
  
1. Cree una variable que contenga las propiedades del buzón inactivo. 
    
    ```
    $InactiveMailbox = Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox>
    ```

    > [!IMPORTANT]
    > En el comando anterior, use el valor de la propiedad **DistinguishedName** o **ExchangeGUID** para identificar el buzón inactivo. Estas propiedades son únicas para cada buzón en su organización, mientras que es posible que un buzón activo e inactivo puedan tener la misma dirección SMTP principal. 
  
2. Restaure el contenido del archivo a partir del buzón inactivo (archivo de origen) en el archivo de un buzón existente (archivo de destino). En este ejemplo, el contenido del archivo de origen se copia a una carpeta denominada "Archivo de buzón inactivo" en el archivo del buzón de destino.

    ```
    New-MailboxRestoreRequest -SourceMailbox $InactiveMailbox.DistinguishedName -SourceIsArchive -TargetMailbox newemployee@contoso.com -TargetIsArchive -TargetRootFolder "Inactive Mailbox Archive" -AllowLegacyDNMismatch
    ```

  
## <a name="more-information"></a>Más información

- **¿Qué es la diferencia principal entre la recuperación y restauración de un buzón inactivo?** Al recuperar un buzón inactivo, básicamente, se convierte el buzón de correo a un buzón nuevo, se conservan el contenido y la estructura de carpetas de buzón de correo inactivo y el buzón de correo está vinculada a una nueva cuenta de usuario. Una vez que se recupere, ya no existe el buzón de correo inactivo y los cambios realizados en el contenido en el nuevo buzón afectará el contenido que se encontraba originalmente en espera en el buzón de correo inactivo. Por el contrario, cuando se restaura un buzón inactivo, el contenido simplemente se copia en otro buzón. El buzón de correo inactivo se mantiene y sigue siendo un buzón de correo inactivo. Los cambios realizados en el contenido en el buzón de destino no afectará al contenido original se conserva en el buzón de correo inactivo. Aún se puede buscar en el buzón de correo inactivo mediante la [herramienta de búsqueda de contenido](run-a-content-search-in-the-security-and-compliance-center.md) en la seguridad de Office 365 &amp; centro de cumplimiento, su contenido se puede restaurar en otro buzón, o puede ser recuperado o eliminado en una fecha posterior. 
    
- **¿Cómo se encuentran los buzones inactivos?** Para obtener una lista de los buzones inactivos en la organización y mostrar información útil para restaurar un buzón inactivo, puede ejecutar este comando. 

  ```
  Get-Mailbox -InactiveMailboxOnly | FL Name,PrimarySMTPAddress,DistinguishedName,ExchangeGUID,LegacyExchangeDN,ArchiveStatus
  ```

- **Utilizar una directiva de retención juicio u Office 365 para conservar el contenido del buzón de correo inactivo.** Si desea conservar el estado de un buzón inactivo tras la restauración, puede colocar el buzón de destino en [Juicio](https://go.microsoft.com/fwlink/?linkid=856286) o aplicar una [Directiva de retención de Office 365](retention-policies.md) antes de restaurar el buzón de correo inactivo. Esto evitará la eliminación permanente de todos los elementos desde el buzón de correo inactivo después de que se va a restaurar en el buzón de destino. 
    
- **La suspensión de retención habilitar en el buzón de destino antes de restaurar un buzón de correo inactivo.** Debido a que los elementos del buzón de un buzón inactivo podrían ser anteriores, considere la posibilidad de habilitar la suspensión de retención en el buzón de destino antes de restaurar un buzón de correo inactivo. Al colocar espera un buzón de correo en retención, no se procesará la directiva de retención que se asigna a él hasta que se elimina la suspensión de retención o hasta que la suspensión de la retención que expire. Esto da el propietario de la hora de buzón de correo de destino para administrar los mensajes antiguos desde el buzón de correo inactivo. De lo contrario, la directiva de retención puede eliminar elementos antiguos (o mover elementos en el buzón de archivo, si está habilitada) que han caducado en función de la configuración de retención configurada para el buzón de destino. Para obtener más información, vea [un buzón de correo en retención conservación en Exchange Online](https://go.microsoft.com/fwlink/?linkid=856300).
    
- **¿Qué hace el modificador AllowLegacyDNMismatch?** En los ejemplos anteriores para restaurar un buzón inactivo, se usa el modificador **AllowLegacyDNMismatch** para permitir la restauración de buzón de correo inactivo a un buzón de destino diferente. En un escenario típico de restauración, el objetivo es restaurar el contenido donde los buzones de origen y de destino son el mismo buzón. Por lo que de forma predeterminada, el cmdlet **New-MailboxRestoreRequest** comprueba para asegurarse de que el valor de la propiedad **LegacyExchangeDN** en los buzones de origen y de destino es la misma. Esto ayuda a impide que pueda restaurar accidentalmente un buzón de origen en el buzón de destino incorrecto. Si intenta restaurar un buzón inactivo sin usar el modificador **AllowLegacyDNMismatch** , puede producirse un error en el comando si los buzones de origen y de destino tienen diferentes valores para la propiedad **LegacyExchangeDN** . 
    
- **Puede usar otros parámetros con el cmdlet New-MailboxRestoreRequest para implementar escenarios de restauración diferentes para los buzones inactivos.**. Por ejemplo, puede ejecutar este comando para restaurar el archivo desde el buzón inactivo en el buzón principal del buzón de destino. 
    
  ```
  New-MailboxRestoreRequest -SourceMailbox <inactive mailbox> -SourceIsArchive -TargetMailbox <target mailbox> -TargetRootFolder "Inactive Mailbox Archive" -AllowLegacyDNMismatch
  ```

  Al ejecutar este comando también puede restaurar el buzón principal inactivo en el archivo del buzón de destino.

  ```
  New-MailboxRestoreRequest -SourceMailbox <inactive mailbox> -TargetMailbox <target mailbox> -TargetIsArchive -TargetRootFolder "Inactive Mailbox" -AllowLegacyDNMismatch
  ```

- **¿Qué hace el parámetro TargetRootFolder?** Como se explicó anteriormente, puede usar el parámetro **TargetRootFolder** para especificar una carpeta en la parte superior de la estructura de carpetas (también denominada la raíz) en el buzón de destino en el que se va a restaurar el contenido del buzón inactivo. Si no usa este parámetro, se combinan los elementos de buzón del buzón inactivo en las carpetas predeterminadas correspondientes del buzón de destino, y se vuelven a crear las carpetas personalizadas en la raíz del buzón de destino. Las siguientes ilustraciones resaltan las diferencias entre no usar y usar el parámetro **TargetRootFolder**. 
    
    **Jerarquía de carpetas en el buzón de destino cuando no se usa el parámetro TargetRootFolder**
    
    ![Captura de pantalla cuando no se utiliza el parámetro TargetRootFolder](media/76a759af-f483-4d1c-8cc7-243435b5562e.png)
  
    **Jerarquía de carpetas en el buzón de destino cuando se usa el parámetro TargetRootFolder**
    
    ![Captura de pantalla cuando se usa el parámetro TargetRootFolder](media/300da592-7323-48db-b8a4-07012259d113.png)

  

