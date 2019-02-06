---
title: Colocar una conservación local en un buzón eliminado temporalmente en Exchange Online
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid: ''
ms.assetid: 421f72bd-dd43-4be1-82f5-0ae9ac43bd00
description: Obtenga información sobre cómo crear una conservación local en un buzón eliminado temporalmente para que se convierta en inactivo y se conserve su contenido. Después, puede usar las herramientas de Microsoft eDiscovery para buscar el buzón inactivo.
ms.openlocfilehash: e666ac608ec224bf97caa947be2cb42b742c6fa9
ms.sourcegitcommit: ca97beff215d154b6ab006ce1222056434fde1a9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/05/2019
ms.locfileid: "29740802"
---
# <a name="put-an-in-place-hold-on-a-soft-deleted-mailbox-in-exchange-online"></a>Colocar una conservación local en un buzón eliminado temporalmente en Exchange Online

Obtenga información sobre cómo crear una conservación local en un buzón eliminado temporalmente para que se convierta en inactivo y se conserve su contenido. Después, puede usar las herramientas de Microsoft eDiscovery para buscar el buzón inactivo.
  
> [!NOTE]
> Nos hemos pospuso la fecha límite para la creación de nuevos suspensiones en contexto en Exchange Online (en los planes independientes de Office 365 y Exchange Online). Pero más adelante este año o el principio del próximo año, no podrá crear nuevos suspensiones en contexto en Exchange Online. Como alternativa al uso de suspensiones en contexto, puede usar [las directivas de retención](https://go.microsoft.com/fwlink/?linkid=827811) o [casos de exhibición de documentos electrónicos](https://go.microsoft.com/fwlink/?linkid=780738) en la seguridad de Office 365 &amp; centro de cumplimiento. Después de que se dé de baja nuevo suspensiones en contexto, aún podrá modificar existente retenciones locales y creando un nuevo suspensiones en contexto en Exchange Server 2013 y las implementaciones híbridas de Exchange todavía se admitirán. Y, aún podrá colocar buzones en suspensión por litigio. 
  
Es posible que tenga una situación donde una persona ha abandonado la organización y su correspondiente cuenta de usuario y su buzón se eliminaron. Posteriormente, se da cuenta hay información en el buzón de correo que debe conservarse. ¿Qué puede hacer? Si no ha caducado el período de retención de buzones eliminados, puede poner una retención local en el buzón eliminado (denominado un buzón eliminado temporalmente) y hacer que un buzón de correo inactivo. Un *buzón de correo inactivo* se usa para conservar el correo electrónico de un empleado anterior después de que abandona la organización. El contenido de un buzón inactivo se conserva para la duración de la conservación local que estaba se coloca en el buzón eliminado temporalmente cuando se realizó inactivos. Después de que el buzón de correo se realiza como inactiva, puede buscar el buzón de correo mediante el uso de exhibición de documentos electrónicos en contexto en Exchange Online, búsqueda de contenido en la seguridad de Office 365 &amp; centro de cumplimiento o el centro de exhibición de documentos electrónicos en SharePoint Online. 
  
> [!NOTE]
> En Exchange Online, un buzón eliminado temporalmente es un buzón que se ha eliminado, pero se puede recuperar en un período de retención específico. El período de retención de buzón eliminado temporalmente en Exchange Online es de 30 días. Esto significa que el buzón se puede recuperar (o convertirse en un buzón inactivo) en un plazo de 30 días después de eliminarse. Transcurrido este período, un buzón eliminado temporalmente se marca para su eliminación permanente y no puede recuperarse ni convertirse en inactivo. 
  
## <a name="before-you-begin"></a>Antes de empezar

- Tiene que usar el cmdlet **New-MailboxSearch** en Windows PowerShell para colocar una conservación local en un buzón eliminado temporalmente. No puede usar el Centro de administración de Exchange (EAC) ni el Centro de eDiscovery en SharePoint Online. 
    
- Para obtener información sobre cómo usar Windows PowerShell para conectarse a Exchange Online, vea [Conexión a Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).
    
- Ejecute el siguiente comando para obtener información de identidad sobre los buzones eliminados temporalmente en la organización. 
    
  ```
  Get-Mailbox -SoftDeletedMailbox | FL Name,WhenSoftDeleted,DistinguishedName,ExchangeGuid,PrimarySmtpAddress
  ```

- Para obtener más información acerca de los buzones de correo inactivos, vea [información general de buzones inactivos en Office 365](inactive-mailboxes-in-office-365.md).
    
## <a name="put-an-in-place-hold-on-a-soft-deleted-mailbox-to-make-it-an-inactive-mailbox"></a>Colocar una conservación local en un buzón eliminado temporalmente para convertirlo en un buzón inactivo

Use el cmdlet **New-MailboxSearch** para convertir un buzón eliminado temporalmente en un buzón inactivo. Para obtener más información, vea [New-MailboxSearch](http://technet.microsoft.com/library/74303b47-bb49-407c-a43b-590356eae35c.aspx).
  
1. Cree una variable que contenga las propiedades del buzón eliminado temporalmente. 
    
   ```
   $SoftDeletedMailbox = Get-Mailbox -SoftDeletedMailbox -Identity <identity of soft-deleted mailbox>
   ```

    > [!IMPORTANT]
    > En el comando anterior, use el valor de la propiedad **DistinguishedName** o **ExchangeGuid** para identificar el buzón eliminado temporalmente. Estas propiedades son únicas para cada buzón en su organización, mientras que es posible que un buzón activo y un buzón eliminado temporalmente tengan la misma dirección SMTP principal. 
  
2. Cree una conservación local y colóquela en el buzón eliminado temporalmente. En este ejemplo, no se especifica ninguna duración de la conservación. Esto significa que los elementos se conservarán de manera indefinida o hasta que la conservación se quite del buzón inactivo.
    
   ```
   New-MailboxSearch -Name "InactiveMailboxHold" -SourceMailboxes $SoftDeletedMailbox.DistinguishedName -InPlaceHoldEnabled $true
    ```
   También puede especificar una duración de la conservación cuando cree la conservación local. En este ejemplo se conservan elementos en el buzón inactivo durante aproximadamente 7 años.
    
   ```
   New-MailboxSearch -Name "InactiveMailboxHold" -SourceMailboxes $SoftDeletedMailbox.DistinguishedName -InPlaceHoldEnabled $true -ItemHoldPeriod 2777
   ```

3. Después de unos minutos, ejecute uno de los siguientes comandos para comprobar que el buzón eliminado temporalmente es un buzón inactivo.
    
   ```
   Get-Mailbox -InactiveMailboxOnly
   ```

    O bien
    
   ```
   Get-Mailbox -InactiveMailboxOnly -Identity $SoftDeletedMailbox.DistinguishedName  | FL IsInactiveMailbox
   ```

## <a name="more-information"></a>Más información

Después de que convierta un buzón eliminado temporalmente en un buzón inactivo, existen varias maneras en las que puede administrar el buzón. Para obtener más información, vea:
  
- [Cambiar la duración de retención para un buzón inactivo](change-the-hold-duration-for-an-inactive-mailbox.md)
    
- [Recuperar un buzón inactivo](recover-an-inactive-mailbox.md)
    
- [Restaurar un buzón inactivo](restore-an-inactive-mailbox.md)
    
- [Eliminar un buzón inactivo](delete-an-inactive-mailbox.md) (quitando la suspensión)
