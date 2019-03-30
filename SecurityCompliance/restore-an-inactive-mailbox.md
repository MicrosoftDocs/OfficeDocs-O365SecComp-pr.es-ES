---
title: Restaurar un buzón inactivo en Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 8/28/2017
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 97e06a7a-ef9a-4ce8-baea-18b9e20449a3
description: Si un nuevo empleado u otro usuario necesita tener acceso al contenido de un buzón inactivo en Office 365, puede restaurar (o combinar) el contenido del buzón inactivo en un buzón existente.
ms.openlocfilehash: 1b80cf5bf9361959f1622b7b42f5c7598609539c
ms.sourcegitcommit: e7a776a04ef6ed5e287a33cfdc36aa2d72862b55
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/29/2019
ms.locfileid: "30999313"
---
# <a name="restore-an-inactive-mailbox-in-office-365"></a>Restaurar un buzón inactivo en Office 365

Un buzón inactivo (que es un tipo de buzón eliminado temporalmente) se usa para conservar el correo electrónico de un antiguo empleado después de que abandone la organización. Si otro empleado asume las responsabilidades del empleado que se marchó o si dicho empleado vuelve a la organización, hay dos maneras en que puede hacer que el contenido del buzón inactivo esté disponible para un usuario: 
  
- **Restaurar un buzón inactivo** Si otro empleado asume las responsabilidades del empleado que se marchó o si otro usuario necesita acceso al contenido del buzón inactivo, puede restaurar (o combinar) el contenido del buzón inactivo en un buzón existente. También puede restaurar el archivo desde un buzón inactivo. Una vez restaurado, el buzón inactivo se conserva y se mantiene como un buzón inactivo. En este tema se describen los procedimientos para restaurar un buzón inactivo. 
    
- **Recuperar un buzón inactivo** Si el empleado que se marchó vuelve a la organización o si se contrata a un nuevo empleado para que asuma las responsabilidades del empleado anterior, puede recuperar el contenido del buzón inactivo. Este método convierte el buzón inactivo en un buzón nuevo que contiene el contenido del buzón inactivo. Una vez recuperado, el buzón inactivo deja de existir. Para conocer los procedimientos paso a paso, vea [recuperar un buzón inactivo en Office 365](recover-an-inactive-mailbox.md).
    
Consulte la sección **más información** de este artículo para obtener más información sobre las diferencias entre restaurar y recuperar un buzón inactivo. 
  
## <a name="before-you-begin"></a>Antes de empezar

- Debe usar Exchange Online PowerShell para restaurar un buzón inactivo. No puede usar el Centro de administración de Exchange (EAC). Para obtener instrucciones paso a paso, consulte [conectarse a Exchange Online PowerShell](https://go.microsoft.com/fwlink/?linkid=396554).
    
- Ejecute el siguiente comando en Exchange Online PowerShell para obtener información de identidad para los buzones inactivos en la organización. 
    
    ```
    Get-Mailbox -InactiveMailboxOnly | FL Name,DistinguishedName,ExchangeGuid,PrimarySmtpAddress
    ```

     Use la información devuelta por este comando para restaurar un buzón inactivo específico.
    
- Para obtener más información acerca de los buzones inactivos, consulte buzones inactivos [en Office 365](inactive-mailboxes-in-office-365.md).
    
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

- **¿Cuál es la diferencia principal entre recuperar y restaurar un buzón inactivo?** Al recuperar un buzón inactivo, el buzón se convierte básicamente en un buzón nuevo, el contenido y la estructura de carpetas del buzón inactivo se conservan y el buzón se vincula a una nueva cuenta de usuario. Una vez recuperado, el buzón inactivo deja de existir y los cambios realizados en el contenido en el nuevo buzón afectarán el contenido que se encontraba originalmente en retención en el buzón inactivo. Por el contrario, cuando se restaura un buzón inactivo, el contenido simplemente se copia a otro buzón de correo. El buzón inactivo se conserva y sigue siendo un buzón inactivo. Los cambios realizados en el contenido del buzón de destino no afectan el contenido original del buzón inactivo. El buzón inactivo se puede seguir buscando mediante la herramienta de [búsqueda de contenido](run-a-content-search-in-the-security-and-compliance-center.md) en el centro de seguridad & cumplimiento, su contenido se puede restaurar a otro buzón o se puede recuperar o eliminar en una fecha posterior. 
    
- **¿Cómo se encuentran los buzones inactivos?** Para obtener una lista de los buzones inactivos en la organización y mostrar información útil para restaurar un buzón inactivo, puede ejecutar este comando. 

  ```
  Get-Mailbox -InactiveMailboxOnly | FL Name,PrimarySMTPAddress,DistinguishedName,ExchangeGUID,LegacyExchangeDN,ArchiveStatus
  ```

- **Use una retención por juicio o una directiva de retención de Office 365 para conservar el contenido de los buzones inactivos.** Si desea conservar el estado de un buzón inactivo después de que se restaure, puede poner el buzón de destino en retención por [juicio](https://go.microsoft.com/fwlink/?linkid=856286) o aplicar una [Directiva de retención de Office 365](retention-policies.md) antes de restaurar el buzón inactivo. Esto evitará la eliminación permanente de los elementos del buzón inactivo después de que se restauran en el buzón de destino. 
    
- **Habilitar la suspensión de retención en el buzón de destino antes de restaurar un buzón inactivo.** Como los elementos del buzón de un buzón inactivo podrían ser antiguos, considere la posibilidad de habilitar la suspensión de retención en el buzón de destino antes de restaurar un buzón inactivo. Al colocar un buzón en suspensión de retención, no se procesará la directiva de retención que se le asigna hasta que se elimine la suspensión de retención o hasta que expire el período de suspensión de retención. De este modo, el propietario del buzón de destino tiene tiempo para administrar los mensajes antiguos del buzón inactivo. De lo contrario, la directiva de retención puede eliminar los elementos antiguos (o mover elementos al buzón de archivo, si está habilitado) que han expirado en función de las opciones de retención configuradas para el buzón de destino. Para obtener más información, vea [poner un buzón de correo en suspensión de retención en Exchange Online](https://go.microsoft.com/fwlink/?linkid=856300).
    
- **¿Qué hace el modificador AllowLegacyDNMismatch?** En los ejemplos anteriores para restaurar un buzón inactivo, el modificador **AllowLegacyDNMismatch** se usa para permitir la restauración del buzón inactivo en un buzón de destino diferente. En un escenario típico de restauración, el objetivo es restaurar el contenido donde los buzones de origen y destino son el mismo buzón. Por lo tanto, de manera predeterminada, el cmdlet **New-MailboxRestoreRequest** se asegura de que el valor de la propiedad **legacyExchangeDN** en los buzones de origen y de destino sea el mismo. Esto ayuda a evitar que se restaure un buzón de origen en el buzón de destino incorrecto por accidente. Si intenta restaurar un buzón inactivo sin usar el modificador **AllowLegacyDNMismatch**, el comando puede dejar de funcionar si los buzones de origen y de destino tienen diferentes valores para la propiedad **LegacyExchangeDN**. 
    
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

  

