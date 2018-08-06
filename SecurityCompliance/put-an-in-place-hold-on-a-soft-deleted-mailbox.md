---
title: Colocar una conservación local en un buzón eliminado temporalmente en Exchange Online
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 1/18/2017
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: 421f72bd-dd43-4be1-82f5-0ae9ac43bd00
description: Obtenga información sobre cómo crear una conservación local en un buzón eliminado temporalmente para que se convierta en inactivo y se conserve su contenido. Después, puede usar las herramientas de Microsoft eDiscovery para buscar el buzón inactivo.
ms.openlocfilehash: 226929764fe39b99f526301029d4a41e2fa486cc
ms.sourcegitcommit: 22bca85c3c6d946083d3784f72e886c068d49f4a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/06/2018
ms.locfileid: "22027617"
---
# <a name="put-an-in-place-hold-on-a-soft-deleted-mailbox-in-exchange-online"></a>Colocar una conservación local en un buzón eliminado temporalmente en Exchange Online

Obtenga información sobre cómo crear una conservación local en un buzón eliminado temporalmente para que se convierta en inactivo y se conserve su contenido. Después, puede usar las herramientas de Microsoft eDiscovery para buscar el buzón inactivo.
  
> [!NOTE]
> Nos hemos pospuso la fecha límite de 1 de julio de 2017 para la creación de nuevos suspensiones en contexto en Exchange Online (en los planes independientes de Office 365 y Exchange Online). Pero más adelante este año o el principio del próximo año, no podrá crear nuevos suspensiones en contexto en Exchange Online. Como alternativa al uso de suspensiones en contexto, puede usar [las directivas de retención](https://go.microsoft.com/fwlink/?linkid=827811) o [casos de exhibición de documentos electrónicos](https://go.microsoft.com/fwlink/?linkid=780738) en la seguridad de Office 365 &amp; centro de cumplimiento. Después de que se dé de baja nuevo suspensiones en contexto, aún podrá modificar existente retenciones locales y creando un nuevo suspensiones en contexto en Exchange Server 2013 y las implementaciones híbridas de Exchange todavía se admitirán. Y, aún podrá colocar buzones en suspensión por litigio. 
  
Es posible que tenga una situación donde una persona ha abandonado la organización y su correspondiente cuenta de usuario y su buzón se eliminaron. Posteriormente, se da cuenta hay información en el buzón de correo que debe conservarse. ¿Qué puede hacer? Si no ha caducado el período de retención de buzones eliminados, puede poner una retención local en el buzón eliminado (denominado un buzón eliminado temporalmente) y hacer que un buzón de correo inactivo. Un *buzón de correo inactivo* se usa para conservar el correo electrónico de un empleado anterior después de que abandona la organización. El contenido de un buzón inactivo se conserva para la duración de la conservación local que estaba se coloca en el buzón eliminado temporalmente cuando se realizó inactivos. Después de que el buzón de correo se realiza como inactiva, puede buscar el buzón de correo mediante el uso de exhibición de documentos electrónicos en contexto en Exchange Online, búsqueda de contenido en la seguridad de Office 365 &amp; centro de cumplimiento o el centro de exhibición de documentos electrónicos en SharePoint Online. 
  
> [!NOTE]
> En Exchange Online, un buzón eliminado temporalmente es un buzón que se ha eliminado, pero se puede recuperar en un período de retención específico. El período de retención de buzón eliminado temporalmente en Exchange Online es de 30 días. Esto significa que el buzón se puede recuperar (o convertirse en un buzón inactivo) en un plazo de 30 días después de eliminarse. Transcurrido este período, un buzón eliminado temporalmente se marca para su eliminación permanente y no puede recuperarse ni convertirse en inactivo. 
  
## <a name="before-you-begin"></a>Antes de empezar
<a name="sectionSection0"> </a>

- Tiene que usar el cmdlet **New-MailboxSearch** en Windows PowerShell para colocar una conservación local en un buzón eliminado temporalmente. No puede usar el Centro de administración de Exchange (EAC) ni el Centro de eDiscovery en SharePoint Online. 
    
- Para obtener información sobre cómo usar Windows PowerShell para conectarse a Exchange Online, vea [Conexión a Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).
    
- Ejecute el siguiente comando para obtener información de identidad sobre los buzones eliminados temporalmente en la organización. 
    
  ```
  Get-Mailbox -SoftDeletedMailbox | FL Name,WhenSoftDeleted,DistinguishedName,ExchangeGuid,PrimarySmtpAddress
  ```

- Para obtener más información sobre buzones inactivos, consulte [Buzones de correo inactivos en Exchange Online](http://technet.microsoft.com/library/2f2948c5-1c5a-4643-865c-b36e4ac1414b.aspx).
    
## <a name="put-an-in-place-hold-on-a-soft-deleted-mailbox-to-make-it-an-inactive-mailbox"></a>Colocar una conservación local en un buzón eliminado temporalmente para convertirlo en un buzón inactivo
<a name="sectionSection1"> </a>

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
<a name="sectionSection2"> </a>

Después de que convierta un buzón eliminado temporalmente en un buzón inactivo, existen varias maneras en las que puede administrar el buzón. Para obtener más información, vea:
  
- [Cambiar la duración de retención para un buzón inactivo en Exchange Online](http://technet.microsoft.com/library/96eb634e-af2f-454e-8014-b698396811c4.aspx)
    
- [Recuperar un buzón inactivo en Exchange Online](http://technet.microsoft.com/library/283838b4-66ba-4c34-b221-e1a3875e1d29.aspx)
    
- [Restaurar un buzón inactivo en Exchange Online](http://technet.microsoft.com/library/1fb02feb-49e5-4485-aec5-9f1537b772b6.aspx)
    
- [Quitar una retención de un buzón inactivo en Exchange Online](http://technet.microsoft.com/library/930a98c3-cd81-4aaa-8e22-19714cb2b731.aspx)
    

