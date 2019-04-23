---
title: Habilitar buzones de archivo en el centro de seguridad & cumplimiento
ms.author: markjjo
author: markjjo
manager: laurawi
ms.audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.ArchivingHelp
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 268a109e-7843-405b-bb3d-b9393b2342ce
description: Use el centro de seguridad & cumplimiento en Office 365 para habilitar los buzones de archivo para que admitan los requisitos de retención, exhibición de documentos electrónicos y conservación de mensajes de la organización.
ms.openlocfilehash: d363943910d970576976d8386196b450dd5694f3
ms.sourcegitcommit: f0e3c9de0b545081a4d264f74559b941f6c71410
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/22/2019
ms.locfileid: "31958311"
---
# <a name="enable-archive-mailboxes-in-the-security--compliance-center"></a>Habilitar buzones de archivo en el centro de seguridad & cumplimiento
  
El archivado en Office 365 (también conocido como archivo local) proporciona a los usuarios un espacio de almacenamiento de buzones adicional. Después de activar los buzones de archivo, los usuarios pueden tener acceso a los mensajes y almacenarlos en sus buzones de archivo con Microsoft Outlook y Outlook en la web (anteriormente conocido como Outlook Web App). Los usuarios también pueden mover o copiar mensajes entre su buzón de correo principal y su buzón de archivo. También pueden recuperar elementos eliminados de la carpeta elementos recuperables de su buzón de archivo mediante la herramienta recuperar elementos eliminados. 
  
> [!TIP]
> Office 365 proporciona una cantidad ilimitada de almacenamiento de archivo con la característica de archivado de expansión automática. Cuando el archivado de expansión automática está activado y, a continuación, se alcanza la cuota de almacenamiento inicial en el buzón de archivo de un usuario, Office 365 agrega automáticamente espacio de almacenamiento adicional. Esto significa que los usuarios no se quedarán sin espacio de almacenamiento en el buzón de correo y no tendrá que administrar nada después de habilitar inicialmente el buzón de archivo y activar el archivado de expansión automática para su organización. Para obtener más información, vea [Información general sobre el archivado ilimitado en Office 365](unlimited-archiving.md). 
  
## <a name="before-you-begin"></a>Antes de empezar

Debe tener asignado el rol destinatarios de correo en Exchange Online para habilitar o deshabilitar buzones de archivo. De forma predeterminada, este rol se asigna a los grupos de roles administración de destinatarios y administración de la organización en la página **permisos** del centro de administración de Exchange. Si no ve la página **archivo** en el centro de seguridad & cumplimiento, pida al administrador que le asigne los permisos necesarios. 
  
## <a name="enable-an-archive-mailbox"></a>Habilitación de un buzón de archivo
  
1. Vaya a [https://protection.office.com](https://protection.office.com).
    
2. Inicie sesión en Office 365 con su cuenta profesional o educativa.
    
3. En el panel izquierdo del centro de seguridad & cumplimiento, haga clic en **archivo**de **gobierno** \> de datos.
    
    Aparece la página **Archivo**. La columna **Buzón de correo de archivo** indica si un buzón de archivo está habilitado o deshabilitado para cada usuario. 
    
4. En la lista de buzones de correo, seleccione el usuario para el que desea habilitar el buzón de correo.
    
    ![Haga clic en habilitar en el panel de detalles del usuario seleccionado para habilitar el buzón de archivo.](media/8b53cdec-d5c9-4c28-af11-611f95c37b34.png)
  
5. En el panel de detalles del usuario seleccionado, haga clic en **Habilitar**. 
    
    Se muestra una advertencia que indica que si habilita el buzón de archivo, los elementos del buzón del usuario que sean más antiguos que la Directiva de archivado asignada al buzón de correo se moverán al nuevo buzón de archivo. La Directiva de archivo predeterminada que forma parte de la Directiva de retención asignada a los buzones de Exchange Online mueve los elementos al buzón de archivo dos años después de la fecha en que el elemento se entregó al buzón o fue creado por el usuario. Para obtener más información, consulte la sección **más información** de este artículo. 
    
6. Haga clic en **Sí** para habilitar el buzón de archivo. 
    
    El buzón de archivo puede tardar un poco en crearse. Cuando se crea, el **buzón de archivo: habilitado** se muestra en el panel de detalles del usuario seleccionado. Puede que tenga que hacer **** ![clic en actualizar](media/O365-MDM-Policy-RefreshIcon.gif) icono para actualizar la información en el panel de detalles. 
    
> [!TIP]
> También puede habilitar buzones de archivo de forma masiva seleccionando varios usuarios con los buzones de archivo deshabilitados (use las teclas Mayús o Ctrl). Después de seleccionar varios buzones, haga clic en **Habilitar** en el panel de detalles. 
  
## <a name="disable-an-archive-mailbox"></a>Deshabilitar un buzón de archivo
  
También puede usar la página **archivo** del centro de seguridad & cumplimiento para deshabilitar el buzón de archivo de un usuario. Después de deshabilitar un buzón de archivo, puede volver a conectarlo al buzón de correo principal del usuario en un plazo de 30 días tras la deshabilitación. En este caso se restaura el contenido original del buzón de archivo. Transcurridos los 30 días, el contenido del buzón de archivo original se elimina definitivamente y no se puede recuperar. Así pues, si vuelve a habilitar el archivo después de los 30 días posteriores a la deshabilitación, se crea un buzón de archivo nuevo. 
  
Tenga en cuenta que la Directiva de archivo predeterminada asignada a los buzones de correo de los usuarios mueve los elementos al buzón de archivo dos años después de la fecha en que se entrega el artículo. Si deshabilita el buzón de archivo de un usuario, no se realizará ninguna acción en los elementos del buzón y permanecerán en el buzón de correo principal del usuario.
  
Para deshabilitar un buzón de archivo:
  
1. Vaya a [https://protection.office.com](https://protection.office.com).
    
2. Inicie sesión en Office 365 con su cuenta profesional o educativa.
    
3. En el panel izquierdo del centro de seguridad & cumplimiento, haga clic en **archivo**de **gobierno** \> de datos.
    
    Aparece la página **Archivo**. La columna **Buzón de correo de archivo** indica si un buzón de archivo está habilitado o deshabilitado para cada usuario. 
    
4. En la lista de buzones, seleccione el usuario para el que desea deshabilitar el buzón de archivo.
    
5. En el panel de detalles, haga clic en **Deshabilitar**. 
    
    Se muestra un mensaje de advertencia que indica que tendrá 30 días para volver a habilitar el buzón de archivo y que, después de 30 días, toda la información del archivo se eliminará de forma permanente. 
    
6. Haga clic en **Sí** para deshabilitar el buzón de archivo. 
    
    El buzón de archivo puede tardar un poco en deshabilitarse. Cuando está deshabilitado, el **buzón de archivo:** deshabilitado se muestra en el panel de detalles del usuario seleccionado. Puede que tenga que hacer **** ![clic en actualizar](media/O365-MDM-Policy-RefreshIcon.gif) icono para actualizar la información en el panel de detalles. 
    
> [!TIP]
> También puede deshabilitar buzones de archivo de forma masiva seleccionando varios usuarios con los buzones de archivo habilitados (use las teclas Mayús o Ctrl). Después de seleccionar varios buzones, haga clic en **Deshabilitar** en el panel de detalles. 
  
## <a name="use-exchange-online-powershell-to-enable-or-disable-archive-mailboxes"></a>Usar Exchange Online PowerShell para habilitar o deshabilitar buzones de archivo

También puede usar Exchange Online PowerShell para habilitar los buzones de archivo. La razón principal para usar PowerShell es que puede habilitar rápidamente el buzón de archivo para todos los usuarios de la organización.

El primer paso consiste en conectarse a Exchange Online PowerShell. Para obtener instrucciones, vea [conectarse a Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).

Una vez que esté conectado a Exchange Online, puede ejecutar los comandos de las siguientes secciones para habilitar o deshabilitar los buzones de archivo.

### <a name="enable-archive-mailboxes"></a>Habilitar buzones de archivo

Ejecute el siguiente comando para habilitar el buzón de archivo para un solo usuario.
    
  ```
  Enable-Mailbox -Identity <username> -Archive
  ```

Ejecute el siguiente comando para habilitar el buzón de archivo para todos los usuarios de la organización (cuyo buzón de archivo no está habilitado actualmente).
    
  ```
  Get-Mailbox -Filter {ArchiveStatus -Eq "None" -AND RecipientTypeDetails -eq "UserMailbox"} | Enable-Mailbox -Archive
  ```
  
### <a name="disable-archive-mailboxes"></a>DesHabilitar buzones de archivo

Ejecute el siguiente comando para deshabilitar el buzón de archivo para un solo usuario.
    
  ```
  Disable-Mailbox -Identity <username> -Archive
  ```

Ejecute el siguiente comando para deshabilitar el buzón de archivo para todos los usuarios de la organización (cuyo buzón de archivo está habilitado actualmente).
    
  ```
  Get-Mailbox -Filter {ArchiveStatus -Eq "Active" -AND RecipientTypeDetails -eq "UserMailbox"} | Disable-Mailbox -Archive
  ```

## <a name="more-information"></a>Más información
  
- Los buzones de archivo le ayudan a usted y a sus usuarios a cumplir los requisitos de retención, exhibición de documentos electrónicos y conservación de la organización. Por ejemplo, puede usar la Directiva de retención de Exchange de su organización para mover el contenido de los buzones de correo al buzón de archivo de los usuarios. Cuando use la herramienta de búsqueda de contenido en el centro de seguridad & cumplimiento para buscar contenido específico en el buzón de un usuario, también se buscará en el buzón de archivo del usuario. Y, al poner una retención por juicio o aplicar una directiva de retención de Office 365 en el buzón de un usuario, también se conservan los elementos del buzón de archivo.
  
- Cuando se habilita un buzón de archivo, los usuarios pueden almacenar mensajes en su buzón de archivo. Los usuarios pueden tener acceso a sus buzones de archivo mediante Microsoft Outlook y Outlook en la Web. Mediante cualquiera de estas aplicaciones cliente, los usuarios pueden visualizar mensajes en su buzón de archivo y mover o copiar mensajes entre su buzón de correo principal y el buzón de archivo. Los usuarios también pueden recuperar elementos eliminados de la carpeta de Elementos recuperables en su buzón de archivo mediante la herramienta Recuperar elementos eliminados. 
  
- Una vez habilitados los buzones de archivo, su organización puede aprovechar la Directiva de retención de Exchange predeterminada (también denominada Directiva de administración de registros de mensajes o de MRM) que se asigna automáticamente a todos los buzones. Cuando se habilita un buzón de archivo, la Directiva de retención de Exchange predeterminada hace lo siguiente automáticamente: 
  
    - Mueve los elementos que tienen dos años o más del buzón principal del usuario a su buzón de archivo. 
    
    - Mueve los elementos que tienen 14 días o más de la carpeta Elementos recuperables del buzón de correo principal del usuario a la carpeta Elementos recuperables del buzón de archivo.
    
- Para obtener más información acerca de los buzones de archivo y las directivas de retención de Exchange, consulte:
    
  - [Etiquetas de retención y directivas de retención](https://go.microsoft.com/fwlink/?LinkId=404424)
    
  - [Directiva de retención predeterminada en Exchange Online](https://go.microsoft.com/fwlink/?linkid=839418)
    
  - [Configurar una directiva de archivo y eliminación para los buzones de la organización de Office 365](set-up-an-archive-and-deletion-policy-for-mailboxes.md)
