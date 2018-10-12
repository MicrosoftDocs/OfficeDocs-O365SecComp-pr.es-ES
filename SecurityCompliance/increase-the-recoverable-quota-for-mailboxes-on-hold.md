---
title: Aumentar la cuota de elementos recuperables para los buzones de correo en retención
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 10/12/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: a8bdcbdd-9298-462f-b889-df26037a990c
description: 'Habilitar el buzón de archivo y activar la ampliación automática de archivado para aumentar el tamaño de la carpeta elementos recuperables para un buzón de correo en Office 365. '
ms.openlocfilehash: a347155645d7c058080b1db7fd47f7ea16249724
ms.sourcegitcommit: 448c5897e44448adfc82e3eaffb774c770c04815
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/12/2018
ms.locfileid: "25522281"
---
# <a name="increase-the-recoverable-items-quota-for-mailboxes-on-hold"></a>Aumentar la cuota de elementos recuperables para los buzones de correo en retención

La directiva de retención de forma predeterminada, denominada directiva MRM predeterminada — es decir aplicados automáticamente a los nuevos buzones en Exchange Online contiene una etiqueta de retención mover a archivo con nombre días 14 de los elementos recuperables. Esta etiqueta de retención mueve elementos desde la carpeta elementos recuperables en el buzón del usuario principal a la carpeta elementos recuperables en el buzón del usuario archivo después de que expire el período de retención de 14 días para un elemento. Para que esto ocurra, debe habilitarse el buzón de archivo del usuario. Si el buzón de archivo no está habilitado, se realiza ninguna acción, lo que significa que no se mueven los elementos en la carpeta de un buzón en suspensión de elementos recuperables en el buzón de archivo, después de que expire el período de retención de 14 días. Debido a que no se elimina nada desde un buzón de correo en espera, es posible que es posible que se superó la cuota de almacenamiento de la carpeta elementos recuperables, especialmente si no está habilitado para el buzón de archivo del usuario. 
  
Para ayudar a reducir las posibilidades de si se excede este límite, la cuota de almacenamiento de la carpeta elementos recuperables se incrementa automáticamente de 30 GB a 100 GB cuando una suspensión se coloca en un buzón de correo en Exchange Online. Si se habilita el buzón de archivo, la cuota de almacenamiento para la carpeta elementos recuperables en el buzón de archivo también se incrementa de 30 GB a 100 GB. Si el archivado de ampliación automática de la característica en Exchange Online está habilitada, la cuota de almacenamiento para la carpeta elementos recuperables en el archivo del usuario será ilimitada.
  
  En la tabla siguiente se resume la cuota de almacenamiento de la carpeta Elementos recuperables. 
  
|**Ubicación de la carpeta Elementos recuperables**|**Buzones que no están en suspensión**|**Buzones en suspensión**|
|:-----|:-----|:-----|
|Buzón principal  <br/> |30 GB  <br/> |100 GB  <br/> |
|Buzón de archivo<sup>\*</sup> <br/> |Ilimitado  <br/> |Ilimitado  <br/> |
|**Cuota de almacenamiento total de la carpeta Elementos recuperables** <br/> |Ilimitado  <br/> |Ilimitado  <br/> |
   
> [!NOTE]
> <sup>\*</sup>La cuota de almacenamiento inicial para el buzón de archivo es de 100 GB para los usuarios con una licencia de Exchange Online (Plan 2). Sin embargo, cuando la ampliación automática de archivado está activado para los buzones de correo en espera, se aumenta la cuota de almacenamiento para el buzón de archivo y la carpeta elementos recuperables a 110 GB. Espacio de almacenamiento de archivo adicionales se aprovisionará cuando sea necesario que da como resultado una cantidad ilimitada de almacenamiento de archivos. Para obtener más información acerca de la expansión automática de archivado, vea [información general sobre el archivo ilimitado en Office 365](unlimited-archiving.md). 
  
Cuando la cuota de almacenamiento de la carpeta Elementos recuperables en el buzón principal de un buzón en suspensión está a punto de alcanzar su límite, puede hacer lo siguiente:
  
- **Habilitar el buzón de archivo y activar el archivado de ampliación automática** - puede habilitar una capacidad de almacenamiento de información ilimitado para la carpeta elementos recuperables, basta con habilitar el buzón de archivo y, a continuación, activar la característica de archivado ampliación automática de Exchange En línea. Esto da como resultado 110 GB para la carpeta elementos recuperables en el buzón principal y una cantidad ilimitada de capacidad de almacenamiento para la carpeta elementos recuperables en el archivo del usuario. Vea Cómo: [Habilitar buzones de archivo en la seguridad de Office 365 &amp; centro de cumplimiento](enable-archive-mailboxes.md) y [Habilitar el archivado ilimitado en Office 365](enable-unlimited-archiving.md).
    
    > [!NOTE]
    > Después de habilitar el archivo para un buzón de correo que está cerca de la superación del límite de la cuota de almacenamiento de la carpeta elementos recuperables, es posible que desee ejecutar el Asistente para carpeta administrada para desencadenar manualmente el Asistente para procesar el buzón de correo de modo que se mueven los elementos que han expirado el Carpeta elementos recuperables en el buzón de archivo. Para obtener instrucciones, consulte el [paso 4](#optional-step-4-run-the-managed-folder-assistant-to-apply-the-new-retention-settings) . Tenga en cuenta que es posible que puede moverse otros elementos en el buzón del usuario para el nuevo buzón de archivo. Tenga en cuenta que indica al usuario que esto puede ocurrir después de habilitar el buzón de archivo. 
  
- **Crear una directiva de retención personalizada para los buzones de correo en espera** - además de habilitar el buzón de archivo y ampliación automática archivado de buzones de correo en juicio o conservación local, es posible que también desee crear una directiva de retención personalizada para los buzones de correo en suspensión. Esto vamos a aplica una directiva de retención a los buzones de correo en espera que es diferente de la directiva MRM predeterminada que se aplica a los buzones de correo que no están en espera. Esto permite aplicar etiquetas de retención que están diseñadas específicamente para los buzones de correo en espera. Esto incluye la creación de una nueva etiqueta de retención para la carpeta elementos recuperables. 
    
En el resto de este tema se describen procedimientos paso a paso para crear una directiva de retención personalizada para los buzones en suspensión.
  
[Paso 1: Crear una etiqueta de retención personalizada para la carpeta Elementos recuperables](#step-1-create-a-custom-retention-tag-for-the-recoverable-items-folder)

[[Paso 2: crear una nueva directiva de retención para los buzones de correo en espera](#step-2-create-a-new-retention-policy-for-mailboxes-on-hold)

[Paso 3: Aplicar la nueva directiva de retención a buzones de correo en suspensión](#step-3-apply-the-new-retention-policy-to-mailboxes-on-hold)

[Paso 4 (opcional): Ejecutar el Asistente para carpeta administrada para aplicar la nueva configuración de retención](#optional-step-4-run-the-managed-folder-assistant-to-apply-the-new-retention-settings)
  
## <a name="step-1-create-a-custom-retention-tag-for-the-recoverable-items-folder"></a>Paso 1: Crear una etiqueta de retención personalizada para la carpeta Elementos recuperables

El primer paso es crear una etiqueta de retención personalizada (denominada una etiqueta de directiva de retención o RPT) de la carpeta elementos recuperables. Como se explica anteriormente, este RPT mueve los elementos de la carpeta elementos recuperables en el buzón del usuario principal a la carpeta elementos recuperables en el buzón de archivo del usuario. Se debe usar PowerShell para crear una RPT para la carpeta elementos recuperables. No puede usar el centro de administración de Exchange (EAC). 
  
1. [Conectarse a Exchange Online con el PowerShell remoto](https://go.microsoft.com/fwlink/p/?LinkId=517283)
    
2. Ejecute el comando siguiente para crear una RPT para la carpeta Elementos recuperables:  
    
    ```
    New-RetentionPolicyTag -Name <Name of RPT> -Type RecoverableItems -AgeLimitForRetention <Number of days> -RetentionAction MoveToArchive
    ```

    Por ejemplo, el comando siguiente crea una RPT para la carpeta Elementos recuperables denominada "30 días en Elementos recuperables para buzones en suspensión", con un período de retención de 30 días. Esto significa que, una vez que un elemento haya estado en la carpeta Elementos recuperables durante 30 días, se moverá a la carpeta Elementos recuperables del buzón de archivo del usuario.
    
    ```
    New-RetentionPolicyTag -Name "Recoverable Items 30 days for mailboxes on hold" -Type RecoverableItems -AgeLimitForRetention 30 -RetentionAction MoveToArchive
    ```

    > [!TIP]
    > Se recomienda que el período de retención (definido por el parámetro _AgeLimitForRetention_ ) para el RPT elementos recuperables es el mismo que el período de retención de elementos eliminados para los buzones de correo que se aplicará la RPT a. Esto permite a un usuario el período de retención de elementos eliminados todo para recuperar elementos eliminados antes de que se muevan al buzón de archivo. En el ejemplo anterior, el período de retención se estableció en 30 días que se basan en la suposición de que el período de retención de elementos eliminados para los buzones de correo también es de 30 días. Un buzón de Exchange Online está configurado para conservar los elementos eliminados durante 14 días, de forma predeterminada. Pero se puede cambiar esta configuración a un máximo de 30 días. Para obtener más información, vea [cambiar el período de retención de elementos eliminados de un buzón en Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=286940). 
  
## <a name="step-2-create-a-new-retention-policy-for-mailboxes-on-hold"></a>Paso 2: Crear una directiva de retención para buzones de correo en suspensión

El siguiente paso consiste en crear una directiva de retención y agregarle etiquetas de retención, incluida la RPT de Elementos recuperables que creó en el paso 1. Esta nueva directiva se aplicará a los buzones de correo en suspensión en el paso siguiente.  
  
Antes de crear la directiva de retención, determine las etiquetas de retención adicionales que quiere agregar. Para obtener una lista de las etiquetas de retención que se agregan a la directiva de MRM predeterminada y para obtener información sobre cómo crear etiquetas de retención, vea lo siguiente:
  
- [Directiva predeterminada de retención en Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=746954)
    
- [Carpetas predeterminadas que admiten etiquetas de la directiva de retención](https://go.microsoft.com/fwlink/p/?LinkId=746957)
    
- La sección "Creación de una etiqueta de retención" en el tema [crear una directiva de retención](https://go.microsoft.com/fwlink/p/?LinkId=404422) .
    
Puede usar el CEF o Exchange Online PowerShell para crear una directiva de retención.
  
### <a name="use-the-eac-to-create-a-retention-policy"></a>Uso de EAC para crear una directiva de retención
  
1. En el EAC, vaya a **administración de cumplimiento** \> **las directivas de retención**y, a continuación, haga clic en **Agregar** ![icono Agregar](media/ITPro-EAC-AddIcon.gif).
    
2. En la página **Nueva directiva de retención**, en **Nombre**, escriba un nombre que describa el propósito de la directiva, como **MRM Policy for Mailboxes on Hold** (Directiva de MRM para buzones de correo en suspensión).  
    
3. En **las etiquetas de retención**, haga clic en **Agregar** ![icono Agregar](media/ITPro-EAC-AddIcon.gif).
    
4. En la lista de etiquetas de retención, seleccione la RPT de Elementos recuperables que ha creado en el paso 1 y, después, haga clic en **Agregar**.
    
    ![Seleccione la etiqueta de retención personalizada Elementos recuperables](media/eb49866b-bdef-4fcd-a6d9-01607c01249b.png)
  
5. Seleccione las etiquetas de retención adicionales que quiera agregar a la directiva de retención. Por ejemplo, podría interesarle agregar las mismas etiquetas que se incluyen en la directiva de MRM predeterminada.
    
6. Cuando termine de agregar reglas de retención, haga clic en **Aceptar**.
    
7. Haga clic en **Guardar** para crear la directiva de retención. 
    
    Observe que las etiquetas de retención vinculadas a la directiva de retención se muestran en el panel de detalles
    
    ![Las etiquetas de retención vinculadas a la directiva de retención se muestran en el panel de detalles](media/dad1c8f4-9928-4d6d-991a-6f6c5194eceb.png)
  
### <a name="use-exchange-online-powershell-to-create-a-retention-policy"></a>Use Exchange Online PowerShell para crear una directiva de retención
  
Ejecute el comando siguiente para crear una directiva de retención para buzones en suspensión.  
  
```
New-RetentionPolicy <Name of retention policy>  -RetentionPolicyTagLinks <list of retention tags>

```

Por ejemplo, el comando siguiente crea la directiva de retención y las etiquetas de retención vinculadas que se muestran en la ilustración anterior.
  
```
New-RetentionPolicy "MRM Policy for Mailboxes on Hold"  -RetentionPolicyTagLinks "Recoverable Items 30 days for mailboxes on hold","1 Month Delete","1 Week Delete","1 Year Delete","5 Year Delete","6 Month Delete","Default 2 year move to archive","Junk Email","Never Delete","Personal 1 year move to archive","Personal 5 year move to archive"
```
  
## <a name="step-3-apply-the-new-retention-policy-to-mailboxes-on-hold"></a>Paso 3: Aplicar la nueva directiva de retención a buzones de correo en suspensión

El último paso consiste en aplicar la nueva directiva de retención que se ha creado en el paso 2 para los buzones de correo en espera en la organización. Puede usar el CEF o Exchange Online PowerShell para aplicar la directiva de retención a un buzón o a varios buzones. 
  
### <a name="use-the-eac-to-apply-the-new-retention-policy"></a>Usar el EAC para aplicar la nueva directiva de retención
  
1. Vaya a **Destinatarios** \> **Buzones de correo**.
    
2. En la vista de lista, seleccione el buzón que desea aplicar la directiva de retención a y, a continuación, haga clic en **Editar** ![icono Editar](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif).
    
3. En la página **Buzón de usuario**, haga clic en **Características de buzón de correo**.
    
4. En **Directiva de retención**, seleccione la directiva de retención que ha creado en el paso 2 y, después, haga clic en **Guardar**.
    
También puede usar el EAC para aplicar la directiva de retención a varios buzones.
  
1. Vaya a **Destinatarios** \> **Buzones de correo**.
    
2. En la vista de lista, use las teclas Mayús o Ctrl para seleccionar varios buzones.
    
3. En el panel de detalles, haga clic en **Más opciones**.
    
4. En **Directiva de retención**, haga clic en **Actualizar**.
    
5. En la página **Directiva de retención de asignación masiva**, seleccione la directiva de retención que ha creado en el paso 2 y, después, haga clic en **Guardar**.  
    
### <a name="use-exchange-online-powershell-to-apply-the-new-retention-policy"></a>Use Exchange Online PowerShell para aplicar la nueva directiva de retención
  
Puede usar Exchange Online PowerShell para aplicar una nueva directiva de retención a un solo buzón. Pero la eficacia real de PowerShell que puede usar para identificar rápidamente todos los buzones de correo en la organización que están en suspensión por litigio o conservación local y, a continuación, aplican la nueva directiva de retención a todos los buzones en suspensión en un solo comando. Estos son algunos ejemplos del uso de PowerShell de Exchange para aplicar una directiva de retención a uno o más buzones. Todos los ejemplos aplican la directiva de retención que se creó en el paso 2.
  
En este ejemplo se aplica la nueva directiva de retención al buzón de Pilar Pinilla.
  
```
Set-Mailbox "Pilar Pinilla" -RetentionPolicy "MRM Policy for Mailboxes on Hold"
```

En este ejemplo se aplica la nueva directiva de retención a todos los buzones de correo de la organización que se encuentran en retención por juicio.
  
```
$LitigationHolds = Get-Mailbox -ResultSize unlimited | Where-Object {$_.LitigationHoldEnabled -eq 'True'}
```

```
$LitigationHolds.DistinguishedName | Set-Mailbox -RetentionPolicy "MRM Policy for Mailboxes on Hold"
```

En este ejemplo se aplica la nueva directiva de retención a todos los buzones de correo de la organización que se encuentran en Conservación local.
  
```
$InPlaceHolds = Get-Mailbox -ResultSize unlimited | Where-Object {$_.InPlaceHolds -ne $null}
```

```
$InPlaceHolds.DistinguishedName | Set-Mailbox -RetentionPolicy "MRM Policy for Mailboxes on Hold"
```

Puede usar el cmdlet **Get-Mailbox** para comprobar que se ha aplicado la nueva directiva de retención. 
  
A continuación presentamos algunos ejemplos para comprobar que los comandos de los ejemplos anteriores han aplicado la directiva de retención Directiva de MRM para buzones de correo en suspensión a los buzones que se encuentran en retención por juicio y en Conservación local.
  
```
Get-Mailbox "Pilar Pinilla" | Select RetentionPolicy
```

```
Get-Mailbox -ResultSize unlimited | Where-Object {$_.LitigationHoldEnabled -eq 'True'} | FT DisplayName,RetentionPolicy -Auto
```

```
Get-Mailbox -ResultSize unlimited | Where-Object {$_.InPlaceHolds -ne $null} | FT DisplayName,RetentionPolicy -Auto
```
  
## <a name="optional-step-4-run-the-managed-folder-assistant-to-apply-the-new-retention-settings"></a>Paso 4 (opcional): Ejecutar el Asistente para carpeta administrada para aplicar la nueva configuración de retención

Después de aplicar la nueva directiva de retención a buzones de correo en espera, puede tardar hasta 7 días en Exchange Online para que el Asistente para carpeta administrada procesar estos buzones de correo con la configuración de la nueva directiva de retención. En lugar de esperar a ejecutar el Asistente para carpeta administrada, puede usar el cmdlet **Start-ManagedFolderAssistant** para activar manualmente el Asistente para procesar los buzones que se aplica la nueva directiva de retención a. 
  
Ejecute el comando siguiente para iniciar el Asistente para carpeta administrada en el buzón del Pilar Pinilla.
  
```
Start-ManagedFolderAssistant "Pilar Pinilla"
```

Ejecute los comandos siguientes para iniciar el Asistente para carpeta administrada en todos los buzones en suspensión.
  
```
$MailboxesOnHold = Get-Mailbox -ResultSize unlimited | Where-Object {($_.InPlaceHolds -ne $null) -or ($_.LitigationHoldEnabled -eq "True")}
```

```
$MailboxesOnHold.DistinguishedName | Start-ManagedFolderAssistant
```

## <a name="more-information"></a>Más información

- Después de habilitar el buzón de archivo de un usuario, tenga en cuenta que indica al usuario que es posible que puede moverse otros elementos en su buzón (no sólo los elementos en la carpeta elementos recuperables) para el buzón de archivo. Esto es debido a que la directiva MRM predeterminada que se asigna a los buzones de Exchange Online contiene una etiqueta de retención (años con nombre de valor predeterminado 2 mover a archivo) que mueve los elementos en el buzón de archivo dos años después de la fecha o el elemento se ha entregado al buzón creado por el usuario. Para obtener más información, vea [Directiva de retención predeterminada en Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=746954)
    
- Después de habilitar el buzón de archivo de un usuario, también podría indicar al usuario que se puede recuperar los elementos eliminados en la carpeta elementos recuperables en su buzón de archivo. Esto puede hacer en Outlook mediante la selección de la carpeta **Elementos eliminados** en el buzón de archivo y, a continuación, haciendo clic en **Recuperar elementos eliminados del servidor** en la ficha **Inicio** . Para obtener más información acerca de los elementos eliminados de recuperación, vea [que recuperar elementos eliminados en Outlook para Windows](https://go.microsoft.com/fwlink/p/?LinkId=624829). 
