---
title: Habilitar el archivado ilimitado en Office 365 - ayuda de administración
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/29/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: e2a789f2-9962-4960-9fd4-a00aa063559e
description: 'Para los administradores: Obtenga información sobre cómo habilitar el archivado en Office 365, que proporciona a los usuarios con el almacenamiento ilimitado para sus buzones de Exchange Online de ampliación automática. Puede habilitar la ampliación automática de archivado para toda la organización o solo para usuarios específicos.'
ms.openlocfilehash: ede3e75a021d750160268ccf06ac4fe1637d219a
ms.sourcegitcommit: 81c2fd5cd940c51bc43ac7858c7bdfa207ce401a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/03/2018
ms.locfileid: "23809705"
---
# <a name="enable-unlimited-archiving-in-office-365---admin-help"></a>Habilitar el archivado ilimitado en Office 365 - ayuda de administración

Puede usar la característica de archivado ampliación automática Exchange Online en Office 365 para habilitar el espacio de almacenamiento ilimitado para buzones de archivo. Cuando está activado el crecimiento automático de archivado, espacio de almacenamiento adicional se agrega automáticamente al buzón de archivo de un usuario cuando acerca al límite de almacenamiento. El resultado es la capacidad de almacenamiento de buzones de correo ilimitados. Para activar el archivado para todas las personas de su organización o solo para usuarios específicos de ampliación automática. Para obtener más información acerca de la expansión automática de archivado, vea [información general sobre el archivo ilimitado en Office 365](unlimited-archiving.md).

## <a name="before-you-begin"></a>Antes de empezar

- Debe ser un administrador global en la organización de Office 365 o un miembro del grupo de roles administración de la organización en la organización de Exchange Online para habilitar el archivado de ampliación automática para toda la organización o para usuarios específicos. Como alternativa, se debe ser un miembro de un grupo de roles que ha asignado el rol de destinatarios de correo para habilitar la ampliación automática de archivado para usuarios específicos.
    
- Buzón de archivo de un usuario debe estar habilitada para poder habilitar el archivado de ampliación automática. Un usuario debe estar asignado a una licencia de Exchange Online Plan 2 para habilitar el buzón de archivo. Si un usuario se le asigna una licencia de Exchange Online Plan 1, tendría que los asigne una licencia independiente de archivado de Exchange Online para habilitar su buzón de archivo. Vea [Habilitar buzones de archivo en la seguridad de Office 365 &amp; centro de cumplimiento](enable-archive-mailboxes.md).
    
- También puede usar PowerShell para habilitar buzones de archivo. Vea la sección [obtener más información](#more-information) para obtener un ejemplo del comando de PowerShell que puede usar para habilitar buzones de archivo para todos los usuarios de su organización. 
    
- Ampliación automática de archivado también es compatible con los buzones compartidos. Para habilitar el archivo para un buzón compartido, se requiere una licencia de Exchange Online Plan 2 o una licencia de Exchange Online Plan 1 con una licencia de archivado de Exchange Online.
    
- No se puede usar el centro de administración de Exchange o la seguridad &amp; centro de cumplimiento para habilitar el archivado de ampliación automática. Se debe usar Exchange Online PowerShell. Para conectarse a su organización de Exchange Online mediante PowerShell remoto, vea [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).
    
  
## <a name="enable-auto-expanding-archiving-for-your-entire-organization"></a>Habilitar el archivado de ampliación automática para toda la organización

Puede habilitar la ampliación automática de archivado para toda la organización. Después de activar, ampliación automática va a habilitar el archivado de buzones de usuario existentes y para los nuevos buzones de usuario que se crean. Al crear nuevos buzones de usuario, asegúrese de habilitar el buzón del usuario principal del archivo, por lo que la característica de archivado ampliación automática funcionará para el nuevo buzón de usuario.
  
1. [Conectarse a Exchange Online mediante PowerShell remoto](https://go.microsoft.com/fwlink/p/?linkid=396554)
    
2. Ejecute el siguiente comando en Exchange Online PowerShell para habilitar el archivado de ampliación automática para toda la organización.

    ```
    Set-OrganizationConfig -AutoExpandingArchive
    ```
  
## <a name="enable-auto-expanding-archiving-for-specific-users"></a>Habilitar el archivado para usuarios específicos de ampliación automática

En lugar de habilitar la ampliación automática de archivado para todos los usuarios de su organización, sólo puede habilitarla para usuarios específicos. Puede hacerlo debido a que sólo algunos usuarios puedan tener una necesidad de un almacenamiento de archivos muy grandes.
  
Cuando se habilita el crecimiento automático archivado para un usuario específico y el buzón del usuario en espera o asignado a una directiva de retención de Office 365, se realizan los siguientes cambios de dos configuraciones:
  
- La cuota de almacenamiento para el buzón del usuario archivo principal se aumenta por 10 GB (de 100 GB a 110 GB). La cuota de advertencia de archivo también se aumenta por 10 GB (de 90 GB a 100 GB).
    
- La cuota de almacenamiento para la carpeta elementos recuperables en el buzón del usuario principal se aumenta por 10 GB (también de 100 GB a 110 GB). También se aumenta la cuota de advertencia de elementos recuperables por 10 GB (de 90 GB a 100 GB). Estos cambios son aplicables sólo si el buzón de correo en espera o asignado a una directiva de retención de Office 365.
    
Este espacio adicional se agrega a evitar problemas de almacenamiento de información que se pueden producir antes de que se ha aprovisionado el archivo de ampliación automática. Tenga en cuenta que almacenamiento adicional espacio *no está* agregado cuando se habilita la expansión automática de archivado para toda la organización, como se describe en la sección anterior. 
  
1. [Conectarse a Exchange Online mediante PowerShell remoto](https://go.microsoft.com/fwlink/p/?linkid=396554)
    
2. Ejecute el siguiente comando en Exchange Online PowerShell para habilitar la ampliación automática de archivado para un usuario específico. Como se explica anteriormente, se debe habilitar el buzón del usuario archive (archivo principal) antes de que puede activar el archivado para que el usuario de ampliación automática.
    
    ```
    Enable-Mailbox <user mailbox> -AutoExpandingArchive
    ```


> [!IMPORTANT]
> En una implementación híbrida de Exchange, no puede usar el comando **Enable-Mailbox-AutoExpandingArchive** para habilitar el archivado para específicos de un usuario cuyo buzón principal se encuentra en instalaciones de ampliación automática y su buzón de archivo está basada en la nube. Para habilitar el crecimiento automático archivado de buzones de archivo basados en la nube en una implementación híbrida de Exchange, tendrá que ejecutar el comando **Set-OrganizationConfig AutoExpandingArchive** en Exchange Online PowerShell para habilitar el archivado de ampliación automática para toda la organización. Si principal de un usuario y los buzones de archivo son ambos basados en la nube, a continuación, puede usar el comando **Enable-Mailbox-AutoExpandingArchive** para habilitar el archivado de ampliación automática para ese usuario específico. 
  
## <a name="verify-that-auto-expanding-archiving-is-enabled"></a>Compruebe que está habilitado el archivado de ampliación automática

Para comprobar que la ampliación automática de archivado está habilitado para la organización, ejecute el siguiente comando en Exchange Online PowerShell.

```
Get-OrganizationConfig | FL AutoExpandingArchiveEnabled
```

Un valor de `True` indica que la ampliación automática de archivado está habilitado para la organización. 
  
Para comprobar que la ampliación automática de archivado es habilitar para un usuario específico, ejecute el siguiente comando en Exchange Online PowerShell.
  
```
Get-Mailbox <user mailbox> | FL AutoExpandingArchiveEnabled
```
Un valor de `True` indica que la ampliación automática de archivado está habilitado para el usuario. 
  
Después de habilitar la ampliación automática de archivado, tenga en cuenta lo siguiente:
  
- Si ejecuta el comando **Set-OrganizationConfig AutoExpandingArchive** para habilitar el archivado de ampliación automática para su organización, no tiene que ejecutar el **AutoExpandingArchive de Enable-Mailbox** en buzones individuales. Tenga en cuenta que ejecuta el cmdlet **Set-OrganizationConfig** para habilitar el archivado de ampliación automática para la organización no cambia la propiedad *AutoExpandingArchiveEnabled* en buzones de usuario a `True`.
    
- De forma similar, no se cambian los valores de las propiedades de buzones de correo *ArchiveQuota* y *ArchiveWarningQuota* cuando se habilita el archivado de ampliación automática. De hecho, cuando se habilita el crecimiento automático archivado para un buzón de usuario y se establece la propiedad *AutoExpandingArchiveEnabled* en `True`, sólo se omiten las propiedades *ArchiveQuota* y *ArchiveWarningQuota* . Este es un ejemplo de estas propiedades de buzón de correo después de ampliación automática de archivado está habilitado para el buzón de un usuario. 
    
    ![Se omiten las propiedades ArchiveQuota y ArchiveWarningQuota después de habilitar el archivado de ampliación automática](media/6a1c1b69-5c4c-4267-aac8-53577667f03e.png)

  
## <a name="more-information"></a>Más información

- También puede usar PowerShell para habilitar buzones de archivo. Por ejemplo, puede ejecutar el siguiente comando en Exchange Online PowerShell para habilitar buzones de archivo para todos los usuarios cuyo buzón de archivo ya no está habilitado.

    ```
    Get-Mailbox -Filter {ArchiveStatus -Eq "None" -AND RecipientTypeDetails -eq "UserMailbox"} | Enable-Mailbox -Archive
    ```

- Después de activar el archivado para su organización o para un usuario específico de ampliación automática, un buzón de archivo se convierte a un archivo de ampliación automática cuando el buzón de archivo (incluida la carpeta elementos recuperables) alcanza 90 GB. Puede tardar hasta 30 días para aprovisionar el espacio de almacenamiento adicional.
    
- Después de activar el archivado de ampliación automática, no se puede desactivar.
    
- Se admite la ampliación automática de archivado para buzones de archivo basados en la nube en una implementación híbrida de Exchange para los usuarios que tienen un buzón principal local. Sin embargo, después de ampliación automática de archivado está habilitado para un buzón de archivo basados en la nube, se no se puede desactivar-board ese buzón de archivo a la organización de Exchange local.
    
- Para obtener una lista de clientes de Outlook que los usuarios pueden usar para tener acceso a los elementos en el área de almacenamiento de información adicional en su buzón de archivo, vea la sección "Requisitos de Outlook para obtener acceso a los elementos de un archivo expandido automático" en [Overview of ilimitado archivado en Office 365](unlimited-archiving.md#outlook-requirements-for-accessing-items-in-an-auto-expanded-archive) .
    
- Tal como se explicó anteriormente, 10 GB se agrega a la cuota de almacenamiento del buzón de archivo principal del usuario (y a la carpeta elementos recuperables si el buzón se encuentra en suspensión) al ejecutar el comando **Enable-Mailbox-AutoExpandingArchive** . Esto proporciona almacenamiento adicional hasta que se ha aprovisionado el espacio de almacenamiento expandido automático (que puede tardar hasta 30 días). Este espacio de almacenamiento adicional no se agrega al ejecutar el **Set-OrganizationConfig AutoExpandingArchive** para habilitar el archivado de ampliación automática para todos los buzones de la organización. Si habilita la ampliación automática de archivado para toda la organización, pero necesita agregar la adicional 10 GB de espacio de almacenamiento para un usuario específico, puede ejecutar el comando **Enable-Mailbox-AutoExpandingArchive** en ese buzón. Tenga en cuenta que recibirá un error que indica que la ampliación automática de archivado ya se ha habilitado, pero el espacio de almacenamiento adicionales se agregarán al buzón. 
