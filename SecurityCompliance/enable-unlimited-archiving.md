---
title: 'Habilitar el archivado ilimitado en Office 365: ayuda de administración'
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/29/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: e2a789f2-9962-4960-9fd4-a00aa063559e
description: 'Para administradores: Obtenga información sobre cómo habilitar el archivado de expansión automática en Office 365, que proporciona a los usuarios un almacenamiento ilimitado para sus buzones de Exchange Online. Puede habilitar el archivado de expansión automática para toda la organización o solo para usuarios específicos.'
ms.openlocfilehash: a6f1e0e43854372b2c7b93c22c1160a7c555a95f
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/17/2019
ms.locfileid: "34154752"
---
# <a name="enable-unlimited-archiving-in-office-365---admin-help"></a>Habilitar el archivado ilimitado en Office 365: ayuda de administración

Puede usar la característica archivado de ampliación automática de Exchange online en Office 365 para habilitar el espacio de almacenamiento ilimitado para los buzones de archivo. Cuando el archivado de expansión automática está activado, el espacio de almacenamiento adicional se agrega automáticamente al buzón de archivo de un usuario cuando se acerca al límite de almacenamiento. El resultado es una capacidad de almacenamiento de buzones ilimitada. Puede activar el archivado de expansión automática para todos los usuarios de su organización o solo para usuarios específicos. Para obtener más información acerca del archivado de expansión automática, vea [información general sobre el archivado ilimitado en Office 365](unlimited-archiving.md).

## <a name="before-you-begin"></a>Antes de empezar

- Debe ser un administrador global de la organización de Office 365 o miembro del grupo de funciones de administración de la organización de su organización de Exchange Online para habilitar el archivado de expansión automática para toda la organización o para usuarios específicos. Como alternativa, debe ser miembro de un grupo de roles que tenga asignado el rol destinatarios de correo para habilitar el archivado de expansión automática para usuarios específicos.
    
- El buzón de archivo de un usuario debe estar habilitado para poder habilitar el archivado de expansión automática. A un usuario se le debe asignar una licencia de plan 2 de Exchange Online para habilitar el buzón de archivo. Si a un usuario se le asigna una licencia de Exchange Online plan 1, tendrá que asignarle una licencia de archivado de Exchange Online independiente para habilitar su buzón de archivo. Consulte [Habilitar buzones de archivo en el centro de seguridad _AMP_ cumplimiento](enable-archive-mailboxes.md).
    
- También puede usar PowerShell para habilitar los buzones de archivo. Consulte la sección [More Information](#more-information) para ver un ejemplo del comando de PowerShell que puede usar para habilitar buzones de archivo para todos los usuarios de la organización. 
    
- El archivado de expansión automática también es compatible con los buzones compartidos. Para habilitar el archivo para un buzón compartido, se necesita una licencia de Exchange Online (plan 2) o una licencia de Exchange Online (plan 1) con una licencia de archivado de Exchange Online.
    
- No puede usar el centro de administración de Exchange o el centro de seguridad & cumplimiento para habilitar el archivado de expansión automática. Debe usar Exchange Online PowerShell. Para conectarse a la organización de Exchange online mediante PowerShell remoto, vea [conectarse a Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).
    
  
## <a name="enable-auto-expanding-archiving-for-your-entire-organization"></a>Habilitación del archivado de expansión automática para toda la organización

Puede habilitar el archivado de expansión automática para toda la organización. Después de activarla, el archivado de expansión automática se habilitará para los buzones de usuario existentes y para los nuevos buzones de usuario que se creen. Al crear nuevos buzones de usuario, asegúrese de habilitar el buzón de archivo principal del usuario para que la característica de archivado de expansión automática funcione para el nuevo buzón de usuario.
  
1. [Conectarse a Exchange Online mediante PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554)
    
2. Ejecute el siguiente comando en Exchange Online PowerShell para habilitar el archivado de expansión automática para toda la organización.

    ```
    Set-OrganizationConfig -AutoExpandingArchive
    ```
  
## <a name="enable-auto-expanding-archiving-for-specific-users"></a>Habilitar el archivado de expansión automática para usuarios específicos

En lugar de habilitar el archivado de expansión automática para todos los usuarios de la organización, solo puede habilitarlo para usuarios específicos. Puede hacerlo porque solo algunos usuarios podrían necesitar un almacenamiento de archivo de gran tamaño.
  
Cuando habilita el archivado de expansión automática para un usuario específico y el buzón de correo del usuario en retención o se asigna a una directiva de retención de Office 365, se realizan los dos cambios de configuración siguientes:
  
- La cuota de almacenamiento del buzón de archivo principal del usuario aumenta en 10 GB (de 100 GB a 110 GB). La cuota de advertencia de archivo también aumenta en 10 GB (de 90 GB a 100 GB).
    
- La cuota de almacenamiento de la carpeta elementos recuperables del buzón de correo principal del usuario aumenta 10 GB (también de 100 GB a 110 GB). La cuota de advertencia de elementos recuperables también aumenta en 10 GB (de 90 GB a 100 GB). Estos cambios solo se aplican si el buzón de correo está en espera o se asigna a una directiva de retención de Office 365.
    
Este espacio adicional se agrega para evitar los problemas de almacenamiento que puedan surgir antes de que se aprovisione el archivo de expansión automática. Tenga en cuenta que *no se* agrega espacio de almacenamiento adicional cuando habilita el archivado de expansión automática para toda la organización, tal como se describe en la sección anterior. 
  
1. [Conectarse a Exchange Online mediante PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554)
    
2. Ejecute el siguiente comando en Exchange Online PowerShell para habilitar el archivado de expansión automática para un usuario específico. Como se ha explicado anteriormente, el buzón de archivo del usuario (archivo principal) debe estar habilitado para poder activar el archivado de expansión automática para ese usuario.
    
    ```
    Enable-Mailbox <user mailbox> -AutoExpandingArchive
    ```


> [!IMPORTANT]
> En una implementación híbrida de Exchange, no puede usar el comando **enable-Mailbox-AutoExpandingArchive** para habilitar el archivado de expansión automática para un usuario específico cuyo buzón de correo principal se encuentra local y su buzón de archivo está basado en la nube. Para habilitar el archivado de expansión automática para buzones de archivo basados en la nube en una implementación híbrida de Exchange, debe ejecutar el comando **set-OrganizationConfig-AutoExpandingArchive** en Exchange Online PowerShell para habilitar el archivado de expansión automática para toda la organización. Si los buzones de correo principales y de archivo de un usuario están basados en la nube, puede usar el comando **enable-Mailbox-AutoExpandingArchive** para habilitar el archivado de expansión automática para ese usuario específico. 
  
## <a name="verify-that-auto-expanding-archiving-is-enabled"></a>Comprobar que el archivado de expansión automática está habilitado

Para comprobar que el archivado de expansión automática está habilitado para su organización, ejecute el siguiente comando en Exchange Online PowerShell.

```
Get-OrganizationConfig | FL AutoExpandingArchiveEnabled
```

Un valor de `True` indica que el archivado de expansión automática está habilitado para la organización. 
  
Para comprobar que el archivado de expansión automática está habilitado para un usuario específico, ejecute el siguiente comando en Exchange Online PowerShell.
  
```
Get-Mailbox <user mailbox> | FL AutoExpandingArchiveEnabled
```
Un valor de `True` indica que el archivado de expansión automática está habilitado para el usuario. 
  
Tenga en cuenta lo siguiente después de habilitar el archivado de expansión automática:
  
- Si ejecuta el comando **set-OrganizationConfig-AutoExpandingArchive** para habilitar el archivado de expansión automática para su organización, no es necesario que ejecute **enable-Mailbox-AutoExpandingArchive** en buzones individuales. Tenga en cuenta que la ejecución del cmdlet **set-OrganizationConfig** para habilitar el archivado de expansión automática para su organización no cambia la propiedad *AutoExpandingArchiveEnabled* de `True`los buzones de usuario a.
    
- De forma similar, los valores de las propiedades del buzón *ArchiveQuota* y *ArchiveWarningQuota* no cambian cuando habilita el archivado de expansión automática. De hecho, cuando habilita el archivado de expansión automática para un buzón de usuario y la propiedad *AutoExpandingArchiveEnabled* se establece `True`en, se omiten las propiedades *ArchiveQuota* y *ArchiveWarningQuota* . Este es un ejemplo de estas propiedades de buzón de correo después de habilitar el archivado de expansión automática para el buzón de un usuario. 
    
    ![Las propiedades ArchiveQuota y ArchiveWarningQuota se ignoran después de habilitar el archivado de expansión automática](media/6a1c1b69-5c4c-4267-aac8-53577667f03e.png)

  
## <a name="more-information"></a>Más información

- También puede usar PowerShell para habilitar los buzones de archivo. Por ejemplo, puede ejecutar el siguiente comando en Exchange Online PowerShell para habilitar los buzones de archivo para todos los usuarios cuyo buzón de archivo no está habilitado.

    ```
    Get-Mailbox -Filter {ArchiveStatus -Eq "None" -AND RecipientTypeDetails -eq "UserMailbox"} | Enable-Mailbox -Archive
    ```

- Después de activar el archivado de expansión automática para su organización o para un usuario específico, un buzón de archivo se convierte en un archivo de expansión automática cuando el buzón de archivo (incluida la carpeta elementos recuperables) alcanza los 90 GB. El espacio de almacenamiento adicional puede tardar hasta 30 días en aprovisionarse.
    
- Después de activar el archivado de expansión automática, no puede desactivarse.
    
- El archivado de expansión automática se admite para los buzones de archivo basados en la nube de una implementación híbrida de Exchange para los usuarios que tienen un buzón principal local. Sin embargo, después de habilitar el archivado de expansión automática para un buzón de archivo basado en la nube, no puede desincorporarlo en el buzón de archivo de vuelta a la organización de Exchange local. Tenga en cuenta que el archivado de expansión automática no es compatible con los buzones locales en Exchange Server 2010.
    
- Para obtener una lista de los clientes de Outlook que los usuarios pueden usar para tener acceso a los elementos del área almacenamiento adicional en el buzón de archivo, consulte la sección "requisitos de Outlook para obtener acceso a los elementos de un archivo de expansión automática" en [información general sobre el archivado ilimitado en Office 365](unlimited-archiving.md#outlook-requirements-for-accessing-items-in-an-auto-expanded-archive) .
    
- Como se ha explicado anteriormente, se agrega 10 GB a la cuota de almacenamiento del buzón de correo de archivo principal del usuario (y a la carpeta elementos recuperables si el buzón está en retención) cuando se ejecuta el comando **enable-Mailbox-AutoExpandingArchive** . Esto proporciona almacenamiento adicional hasta que se aprovisiona el espacio de almacenamiento expandido (que puede tardar hasta 30 días). Este espacio de almacenamiento adicional no se agrega al ejecutar **set-OrganizationConfig-AutoExpandingArchive** para habilitar el archivado de expansión automática para todos los buzones de la organización. Si habilitó el archivado de expansión automática para toda la organización, pero necesita agregar 10 GB adicionales de espacio de almacenamiento para un usuario específico, puede ejecutar el comando **enable-Mailbox-AutoExpandingArchive** en ese buzón. Tenga en cuenta que recibirá un error que indica que el archivado de expansión automática ya está habilitado, pero el espacio de almacenamiento adicional se agregará al buzón. 

- Los administradores no pueden ajustar la cuota de almacenamiento.

> [!IMPORTANT]
> El archivado de expansión automática solo se admite para buzones de correo que se usan para usuarios individuales o buzones compartidos con una tasa de crecimiento que no supera 1 GB por día. El uso del registro en diario, las reglas de transporte o las reglas de reenvío automático para copiar mensajes en un buzón de archivo con el fin de archivar no está permitido. El buzón de archivo de un usuario está diseñado exclusivamente para dicho usuario. Microsoft se reserva el derecho de denegar el archivado ilimitado si el buzón de archivo de un usuario se usa para almacenar datos de archivo de otros usuarios.
