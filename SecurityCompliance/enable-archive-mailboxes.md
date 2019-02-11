---
title: Habilitar buzones de archivo en la seguridad de Office 365 &amp; centro de cumplimiento
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.ArchivingHelp
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 268a109e-7843-405b-bb3d-b9393b2342ce
description: Usar la seguridad de Office 365 &amp; centro de cumplimiento para habilitar buzones de archivo admitir la retención de mensajes de su organización, exhibición de documentos electrónicos y los requisitos de retención.
ms.openlocfilehash: 1c290cf19b396221dac702efd1395911e8a51631
ms.sourcegitcommit: 7e2a0185cadea7f3a6afc5ddc445eac2e1ce22eb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/11/2019
ms.locfileid: "28327102"
---
# <a name="enable-archive-mailboxes-in-the-office-365-security-amp-compliance-center"></a>Habilitar buzones de archivo en la seguridad de Office 365 &amp; centro de cumplimiento
  
Archivado en Office 365 (también denominado archivado en contexto) proporciona a los usuarios con el espacio de almacenamiento de buzones de correo adicionales. Después de activar buzones de archivo, los usuarios pueden obtener acceso y almacenar los mensajes en sus buzones de archivo mediante el uso de Microsoft Outlook y Outlook Web App a los usuarios también pueden mover o copiar mensajes entre su buzón principal y su buzón de archivo. También pueden recuperar los elementos eliminados de la carpeta elementos recuperables en su buzón de archivo mediante la herramienta de recuperar elementos eliminados. 
  
> [!TIP]
> Office 365 proporciona una cantidad ilimitada de almacenamiento de archivos con la característica de archivado ampliación automática. Cuando está activado el crecimiento automático de archivado y, a continuación, se alcanza la cuota de almacenamiento inicial en el buzón de archivo de un usuario, Office 365 agrega automáticamente espacio de almacenamiento adicional. Esto significa que los usuarios no se ejecutan fuera del espacio de almacenamiento de buzones de correo y no tendrá que administrar inicialmente nada después de habilitar el buzón de archivo y activar la ampliación automática de archivado para su organización. Para obtener más información, vea [información general sobre el archivo ilimitado en Office 365](unlimited-archiving.md). 
  
## <a name="before-you-begin"></a>Antes de empezar

Se debe asignar el rol de destinatarios de correo en Exchange Online para habilitar o deshabilitar los buzones de archivo. De forma predeterminada, este rol se asigna a los grupos de funciones de administración de destinatarios y administración de la organización en la página de **permisos** en el centro de administración de Exchange. Si no ve la página de **archivo** en la seguridad &amp; del centro de cumplimiento, pida al administrador que asigne los permisos necesarios. 
  
## <a name="enable-an-archive-mailbox"></a>Habilitación de un buzón de archivo
  
1. Vaya a [https://protection.office.com](https://protection.office.com).
    
2. Inicie sesión en Office 365 con su cuenta profesional o educativa.
    
3. En el panel izquierdo de la seguridad &amp; centro de cumplimiento, haga clic en **el gobierno de datos** \> **archivo**.
    
    Aparece la página **Archivo**. La columna **Buzón de correo de archivo** indica si un buzón de archivo está habilitado o deshabilitado para cada usuario. 
    
4. En la lista de buzones de correo, seleccione el usuario para el que desea habilitar el buzón de correo.
    
    ![Haga clic en habilitar en el panel de detalles del usuario seleccionado para habilitar el buzón de archivo](media/8b53cdec-d5c9-4c28-af11-611f95c37b34.png)
  
5. En el panel de detalles para el usuario seleccionado, haga clic en **Habilitar**. 
    
    Se muestra una advertencia que indica que, si habilita el buzón de archivo, se moverán los elementos en el buzón del usuario que sean más antiguos que la directiva de archivado asignada al buzón para el nuevo buzón de archivo. La directiva de archivo predeterminada que forma parte de la directiva de retención asignada a buzones de Exchange Online mueve los elementos en el buzón de archivo dos años después de la fecha en que el elemento se ha entregado al buzón o creados por el usuario. Para obtener más información, vea la sección **más información** de este artículo. 
    
6. Haga clic en **Sí** para habilitar el buzón de archivo. 
    
    Puede tardar unos minutos para crear el buzón de archivo. Cuando se crea, **buzón de archivo: habilitado** se muestra en el panel de detalles del usuario seleccionado. Es posible que deba haga clic en **Actualizar** ![icono de actualización](media/O365-MDM-Policy-RefreshIcon.gif) para actualizar la información en el panel de detalles. 
    
> [!TIP]
> También puede habilitar buzones de archivo de forma masiva seleccionando varios usuarios con los buzones de archivo deshabilitados (use las teclas Mayús o Ctrl). Después de seleccionar varios buzones, haga clic en **Habilitar** en el panel de detalles. 
  
## <a name="disable-an-archive-mailbox"></a>Deshabilitar un buzón de archivo
  
También puede usar la página de **archivo** en la seguridad &amp; centro de cumplimiento para deshabilitar el buzón de archivo de un usuario. Después de deshabilitar un buzón de archivo, puede conectarse al buzón principal del usuario dentro de 30 días de deshabilitarla. En este caso, se restaura el contenido original del buzón de archivo. Después de 30 días, el contenido del buzón de archivo original se elimina permanentemente y no se puede recuperar. Por lo que si vuelve a habilitar el archivo de más de 30 días después de deshabilitarlo, se crea un nuevo buzón de archivo. 
  
Tenga en cuenta que la directiva de archivo predeterminado asignado a los buzones de los usuarios mueva los elementos en el buzón de archivo dos años después de la fecha del elemento se entrega. Si se deshabilita el buzón de archivo de un usuario, en los elementos del buzón no se llevará a cabo ninguna acción y permanecen en el buzón del usuario principal.
  
Para deshabilitar un buzón de archivo:
  
1. Vaya a [https://protection.office.com](https://protection.office.com).
    
2. Inicie sesión en Office 365 con su cuenta profesional o educativa.
    
3. En el panel izquierdo de la seguridad &amp; centro de cumplimiento, haga clic en **el gobierno de datos** \> **archivo**.
    
    Aparece la página **Archivo**. La columna **Buzón de correo de archivo** indica si un buzón de archivo está habilitado o deshabilitado para cada usuario. 
    
4. En la lista de buzones, seleccione el usuario para el que desea deshabilitar el buzón de archivo.
    
5. En el panel de detalles, haga clic en **Deshabilitar**. 
    
    Se muestra un mensaje de advertencia que indica que dispone de 30 días para volver a habilitar el buzón de archivo, y que después de 30 días, toda la información en el archivo se eliminarán permanentemente. 
    
6. Haga clic en **Sí** para deshabilitar el buzón de archivo. 
    
    Puede tardar unos minutos para deshabilitar el buzón de archivo. Cuando está deshabilitada, **buzón de archivo: deshabilitado** se muestra en el panel de detalles del usuario seleccionado. Es posible que deba haga clic en **Actualizar** ![icono de actualización](media/O365-MDM-Policy-RefreshIcon.gif) para actualizar la información en el panel de detalles. 
    
> [!TIP]
> También puede deshabilitar buzones de archivo de forma masiva seleccionando varios usuarios con los buzones de archivo habilitados (use las teclas Mayús o Ctrl). Después de seleccionar varios buzones, haga clic en **Deshabilitar** en el panel de detalles. 
  
## <a name="use-exchange-online-powershell-to-enable-or-disable-archive-mailboxes"></a>Use Exchange Online PowerShell para habilitar o deshabilitar los buzones de archivo

También puede usar Exchange Online PowerShell para habilitar buzones de archivo. La razón principal para usar PowerShell es que se puede habilitar rápidamente el buzón de archivo para todos los usuarios de la organización.

El primer paso es para conectarse a Exchange Online PowerShell. Para obtener instrucciones, vea [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).

Después de conectarse a Exchange Online, puede ejecutar los comandos en las secciones siguientes para habilitar o deshabilitar los buzones de archivo.

### <a name="enable-archive-mailboxes"></a>Habilitar buzones de archivo

Ejecute el siguiente comando para habilitar el buzón de archivo para un único usuario.
    
  ```
  Enable-Mailbox -Identity <username> -Archive
  ```

Ejecute el siguiente comando para habilitar el buzón de archivo para todos los usuarios de la organización (cuyo buzón de archivo actualmente no está habilitado).
    
  ```
  Get-Mailbox -Filter {ArchiveStatus -Eq "None" -AND RecipientTypeDetails -eq "UserMailbox"} | Enable-Mailbox -Archive
  ```
  
### <a name="disable-archive-mailboxes"></a>Deshabilitar los buzones de archivo

Ejecute el siguiente comando para deshabilitar el buzón de archivo para un único usuario.
    
  ```
  Disable-Mailbox -Identity <username> -Archive
  ```

Ejecute el siguiente comando para deshabilitar el buzón de archivo para todos los usuarios de su organización (cuyo buzón de archivo actualmente está habilitado).
    
  ```
  Get-Mailbox -Filter {ArchiveStatus -Eq "Active" -AND RecipientTypeDetails -eq "UserMailbox"} | Disable-Mailbox -Archive
  ```

## <a name="more-information"></a>Más información
  
- Buzones de archivo ayudan a usted y a sus usuarios para satisfacer la retención de la organización, exhibición de documentos electrónicos y los requisitos de retención. Por ejemplo, puede usar la directiva de retención de la organización Exchange para mover el contenido de buzón de correo al buzón de archivo de los usuarios. Al utilizar la herramienta de búsqueda de contenido en la seguridad &amp; también se buscará en el centro de cumplimiento para buscar el buzón de un usuario para contenido específico, buzón de archivo del usuario. Y, cuando se coloque un juicio o aplicar una directiva de retención de Office 365 para el buzón de un usuario, también se conservan los elementos en el buzón de archivo.
  
- Cuando se habilita un buzón de archivo, los usuarios pueden almacenar los mensajes en su buzón de archivo. Los usuarios pueden tener acceso a sus buzones de archivo mediante el uso de Microsoft Outlook y Outlook Web App mediante cualquiera de estas aplicaciones de cliente, los usuarios pueden ver los mensajes en su buzón de archivo y mover o copiar mensajes entre su buzón principal y su buzón de archivo. Los usuarios también pueden recuperar elementos eliminados desde la carpeta elementos recuperables en su buzón de archivo mediante la herramienta de recuperar elementos eliminados. 
  
- Después de archivo están habilitados los buzones de correo, su organización puede aprovechar la predeterminada Exchange directiva de retención (también denominada directiva de administración de registros de mensajería o MRM) que se asigna automáticamente a todos los buzones. Cuando se habilita un buzón de archivo, la directiva de retención predeterminada Exchange automáticamente hace lo siguiente: 
  
    - Mueve los elementos que tienen dos años o más del buzón principal del usuario a su buzón de archivo. 
    
    - Mueve los elementos que tienen 14 días o más de la carpeta Elementos recuperables del buzón de correo principal del usuario a la carpeta Elementos recuperables del buzón de archivo.
    
- Para obtener más información acerca de los buzones de archivo y las directivas de retención de Exchange, consulte:
  
    
  - [Etiquetas de retención y directivas de retención](https://go.microsoft.com/fwlink/?LinkId=404424)
    
  - [Directiva predeterminada de retención en Exchange Online](https://go.microsoft.com/fwlink/?linkid=839418)
    
  - [Configurar una directiva de eliminación y de archivo para los buzones de correo en la organización de Office 365](set-up-an-archive-and-deletion-policy-for-mailboxes.md)
