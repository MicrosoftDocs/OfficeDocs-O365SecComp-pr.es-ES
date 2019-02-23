---
title: Aumentar la cuota de elementos recuperables para los buzones de correo en retención
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 10/12/2018
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: a8bdcbdd-9298-462f-b889-df26037a990c
description: 'Habilite el buzón de archivo y active el archivado de expansión automática para aumentar el tamaño de la carpeta elementos recuperables para un buzón de correo en Office 365. '
ms.openlocfilehash: ebb052ba17ba8a84076e1e75a82713cc5cf437a1
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/23/2019
ms.locfileid: "30218480"
---
# <a name="increase-the-recoverable-items-quota-for-mailboxes-on-hold"></a>Aumentar la cuota de elementos recuperables para los buzones de correo en retención

La Directiva de retención predeterminada, denominada Directiva de MRM predeterminada, que se aplica automáticamente a los nuevos buzones de correo de Exchange Online contiene una etiqueta de retención denominada elementos recuperables de 14 días para mover a archivo. Esta etiqueta de retención mueve los elementos de la carpeta elementos recuperables del buzón de correo principal del usuario a la carpeta elementos recuperables del buzón de archivo del usuario después de que expire el período de retención de 14 días de un elemento. Para que esto suceda, debe estar habilitado el buzón de archivo del usuario. Si el buzón de archivo no está habilitado, no se realiza ninguna acción, lo que significa que los elementos de la carpeta elementos recuperables de un buzón en retención no se mueven al buzón de archivo después de que expire el período de retención de 14 días. Como no se elimina nada de un buzón de correo en suspensión, es posible que se supere la cuota de almacenamiento de la carpeta elementos recuperables, especialmente si el buzón de archivo del usuario no está habilitado. 
  
Para ayudar a reducir la posibilidad de superar este límite, la cuota de almacenamiento de la carpeta elementos recuperables aumenta automáticamente de 30 GB a 100 GB cuando se coloca una retención en un buzón de correo en Exchange Online. Si el buzón de archivo está habilitado, la cuota de almacenamiento de la carpeta elementos recuperables del buzón de archivo también aumenta de 30 GB a 100 GB. Si la característica de archivado de ampliación automática en Exchange Online está habilitada, la cuota de almacenamiento de la carpeta elementos recuperables del archivo del usuario será ilimitada.
  
  En la tabla siguiente se resume la cuota de almacenamiento de la carpeta Elementos recuperables. 
  
|**Ubicación de la carpeta Elementos recuperables**|**Buzones que no están en suspensión**|**Buzones en suspensión**|
|:-----|:-----|:-----|
|Buzón principal  <br/> |30 GB  <br/> |100 GB  <br/> |
|Buzón de archivo<sup>\*</sup> <br/> |Ilimitado  <br/> |Ilimitado  <br/> |
|**Cuota de almacenamiento total de la carpeta Elementos recuperables** <br/> |Ilimitado  <br/> |Ilimitado  <br/> |
   
> [!NOTE]
> <sup>\*</sup>La cuota de almacenamiento inicial para el buzón de archivo es de 100 GB para los usuarios con una licencia de Exchange Online (plan 2). Sin embargo, cuando el archivado de expansión automática está activado para buzones en retención, la cuota de almacenamiento para el buzón de archivo y la carpeta elementos recuperables aumenta a 110 GB. El espacio de almacenamiento de archivo adicional se aprovisionará cuando sea necesario, lo que da como resultado una cantidad ilimitada de almacenamiento de archivo. Para obtener más información acerca del archivado de expansión automática, vea [información general sobre el archivado ilimitado en Office 365](unlimited-archiving.md). 
  
Cuando la cuota de almacenamiento de la carpeta Elementos recuperables en el buzón principal de un buzón en suspensión está a punto de alcanzar su límite, puede hacer lo siguiente:
  
- **Habilitar el buzón de archivo y activar el archivado de expansión automática** : puede habilitar una capacidad de almacenamiento ilimitada para la carpeta elementos recuperables con tan solo habilitar el buzón de archivo y, a continuación, activar la característica de archivado de ampliación automática en Exchange. Online. Esto da como resultado 110 GB para la carpeta elementos recuperables en el buzón principal y una cantidad ilimitada de capacidad de almacenamiento para la carpeta elementos recuperables del archivo del usuario. Vea cómo: [Habilitar buzones de archivo en el centro de &amp; seguridad y cumplimiento de Office 365](enable-archive-mailboxes.md) y [Habilitar el archivado ilimitado en Office 365](enable-unlimited-archiving.md).
    
    > [!NOTE]
    > Después de habilitar el archivo para un buzón que está a punto de superar la cuota de almacenamiento de la carpeta elementos recuperables, es posible que desee ejecutar el Asistente para carpeta administrada para desencadenar manualmente el Asistente para procesar el buzón de modo que los elementos expirados se muevan Carpeta elementos recuperables en el buzón de archivo. Consulte el [paso 4](#optional-step-4-run-the-managed-folder-assistant-to-apply-the-new-retention-settings) para obtener instrucciones. Tenga en cuenta que es posible que se muevan otros elementos del buzón del usuario al nuevo buzón de archivo. Considere la posibilidad de que se indique al usuario que esto puede ocurrir después de habilitar el buzón de archivo. 
  
- **Crear una directiva de retención personalizada para buzones de correo en** retención: además de habilitar el buzón de archivo y el archivado de expansión automática para buzones en retención por juicio o conservación local, es posible que también desee crear una directiva de retención personalizada para los buzones de correo en retención. Esto le permite aplicar una directiva de retención a los buzones de correo en retención que es diferente de la Directiva de MRM predeterminada que se aplica a los buzones que no están en suspensión. Esto le permite aplicar etiquetas de retención que se han diseñado específicamente para buzones de correo en retención. Esto incluye la creación de una nueva etiqueta de retención para la carpeta elementos recuperables. 
    
En el resto de este tema se describen procedimientos paso a paso para crear una directiva de retención personalizada para los buzones en suspensión.
  
[Paso 1: Crear una etiqueta de retención personalizada para la carpeta Elementos recuperables](#step-1-create-a-custom-retention-tag-for-the-recoverable-items-folder)

[[Paso 2: crear una nueva Directiva de retención para buzones en retención](#step-2-create-a-new-retention-policy-for-mailboxes-on-hold)

[Paso 3: Aplicar la nueva directiva de retención a buzones de correo en suspensión](#step-3-apply-the-new-retention-policy-to-mailboxes-on-hold)

[Paso 4 (opcional): Ejecutar el Asistente para carpeta administrada para aplicar la nueva configuración de retención](#optional-step-4-run-the-managed-folder-assistant-to-apply-the-new-retention-settings)
  
## <a name="step-1-create-a-custom-retention-tag-for-the-recoverable-items-folder"></a>Paso 1: Crear una etiqueta de retención personalizada para la carpeta Elementos recuperables

El primer paso consiste en crear una etiqueta de retención personalizada (denominada "etiqueta de directiva de retención" o "RPT") para la carpeta elementos recuperables. Como se explicó anteriormente, esta RPT mueve los elementos de la carpeta elementos recuperables del buzón de correo principal del usuario a la carpeta elementos recuperables del buzón de archivo del usuario. Debe usar PowerShell para crear una RPT para la carpeta elementos recuperables. No puede usar el centro de administración de Exchange (EAC). 
  
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
    > Se recomienda que el período de retención (definido por el parámetro _AgeLimitForRetention_ ) para la RPT de elementos recuperables sea el mismo que el período de retención de elementos eliminados para los buzones de correo a los que se aplicará el RPT. Esto permite a un usuario todo el período de retención de elementos eliminados para recuperar los elementos eliminados antes de que se muevan al buzón de archivo. En el ejemplo anterior, el período de retención se estableció en 30 días en función de la hipótesis de que el período de retención de elementos eliminados para los buzones de correo es también de 30 días. De forma predeterminada, se configura un buzón de correo de Exchange Online para conservar los elementos eliminados durante 14 días. Pero puede cambiar esta configuración a un máximo de 30 días. Para obtener más información, vea [cambiar el período de retención de elementos eliminados para un buzón de correo en Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=286940). 
  
## <a name="step-2-create-a-new-retention-policy-for-mailboxes-on-hold"></a>Paso 2: Crear una directiva de retención para buzones de correo en suspensión

El siguiente paso consiste en crear una directiva de retención y agregarle etiquetas de retención, incluida la RPT de Elementos recuperables que creó en el paso 1. Esta nueva directiva se aplicará a los buzones de correo en suspensión en el paso siguiente.  
  
Antes de crear la directiva de retención, determine las etiquetas de retención adicionales que quiere agregar. Para obtener una lista de las etiquetas de retención que se agregan a la directiva de MRM predeterminada y para obtener información sobre cómo crear etiquetas de retención, vea lo siguiente:
  
- [Directiva de retención predeterminada en Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=746954)
    
- [Carpetas predeterminadas que admiten etiquetas de la directiva de retención](https://go.microsoft.com/fwlink/p/?LinkId=746957)
    
- La sección "crear una etiqueta de retención" en el tema [Create a Retention Policy](https://go.microsoft.com/fwlink/p/?LinkId=404422) .
    
Puede usar el EAC o Exchange Online PowerShell para crear una directiva de retención.
  
### <a name="use-the-eac-to-create-a-retention-policy"></a>Uso de EAC para crear una directiva de retención
  
1. En el EAC, vaya a **** \> **directivas de retención**de administración de cumplimiento y, a continuación](media/ITPro-EAC-AddIcon.gif), haga clic en **Agregar** ![icono de agregar.
    
2. En la página **Nueva directiva de retención**, en **Nombre**, escriba un nombre que describa el propósito de la directiva, como **MRM Policy for Mailboxes on Hold** (Directiva de MRM para buzones de correo en suspensión).  
    
3. En **etiquetas de retención**, haga clic en](media/ITPro-EAC-AddIcon.gif) **Agregar** ![icono de agregar.
    
4. En la lista de etiquetas de retención, seleccione la RPT de Elementos recuperables que ha creado en el paso 1 y, después, haga clic en **Agregar**.
    
    ![Seleccione la etiqueta de retención personalizada Elementos recuperables](media/eb49866b-bdef-4fcd-a6d9-01607c01249b.png)
  
5. Seleccione las etiquetas de retención adicionales que quiera agregar a la directiva de retención. Por ejemplo, podría interesarle agregar las mismas etiquetas que se incluyen en la directiva de MRM predeterminada.
    
6. Cuando termine de agregar reglas de retención, haga clic en **Aceptar**.
    
7. Haga clic en **Guardar** para crear la directiva de retención. 
    
    Observe que las etiquetas de retención vinculadas a la directiva de retención se muestran en el panel de detalles
    
    ![Las etiquetas de retención vinculadas a la directiva de retención se muestran en el panel de detalles](media/dad1c8f4-9928-4d6d-991a-6f6c5194eceb.png)
  
### <a name="use-exchange-online-powershell-to-create-a-retention-policy"></a>Usar Exchange Online PowerShell para crear una directiva de retención
  
Ejecute el comando siguiente para crear una directiva de retención para buzones en suspensión.  
  
```
New-RetentionPolicy <Name of retention policy>  -RetentionPolicyTagLinks <list of retention tags>

```

Por ejemplo, el comando siguiente crea la directiva de retención y las etiquetas de retención vinculadas que se muestran en la ilustración anterior.
  
```
New-RetentionPolicy "MRM Policy for Mailboxes on Hold"  -RetentionPolicyTagLinks "Recoverable Items 30 days for mailboxes on hold","1 Month Delete","1 Week Delete","1 Year Delete","5 Year Delete","6 Month Delete","Default 2 year move to archive","Junk Email","Never Delete","Personal 1 year move to archive","Personal 5 year move to archive"
```
  
## <a name="step-3-apply-the-new-retention-policy-to-mailboxes-on-hold"></a>Paso 3: Aplicar la nueva directiva de retención a buzones de correo en suspensión

El último paso consiste en aplicar la nueva Directiva de retención que ha creado en el paso 2 a los buzones en retención en la organización. Puede usar el EAC o Exchange Online PowerShell para aplicar la Directiva de retención a un único buzón o a varios buzones. 
  
### <a name="use-the-eac-to-apply-the-new-retention-policy"></a>Usar el EAC para aplicar la nueva directiva de retención
  
1. Vaya a **Destinatarios** \> **Buzones de correo**.
    
2. En la vista de lista, seleccione el buzón al que desea aplicar la Directiva de retención y, a **** ![continuación, haga](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif)clic en Editar icono de edición.
    
3. En la página **Buzón de usuario**, haga clic en **Características de buzón de correo**.
    
4. En **Directiva de retención**, seleccione la directiva de retención que ha creado en el paso 2 y, después, haga clic en **Guardar**.
    
También puede usar el EAC para aplicar la directiva de retención a varios buzones.
  
1. Vaya a **Destinatarios** \> **Buzones de correo**.
    
2. En la vista de lista, use las teclas Mayús o Ctrl para seleccionar varios buzones.
    
3. En el panel de detalles, haga clic en **Más opciones**.
    
4. En **Directiva de retención**, haga clic en **Actualizar**.
    
5. En la página **Directiva de retención de asignación masiva**, seleccione la directiva de retención que ha creado en el paso 2 y, después, haga clic en **Guardar**.  
    
### <a name="use-exchange-online-powershell-to-apply-the-new-retention-policy"></a>Usar Exchange Online PowerShell para aplicar la nueva Directiva de retención
  
Puede usar Exchange Online PowerShell para aplicar una nueva Directiva de retención a un único buzón. Pero el potencial real de PowerShell es que puede usarlo para identificar rápidamente todos los buzones de la organización que están en retención por juicio o conservación local y, a continuación, aplicar la nueva Directiva de retención a todos los buzones en retención en un solo comando. A continuación, se muestran algunos ejemplos de cómo usar Exchange PowerShell para aplicar una directiva de retención a uno o más buzones. En todos los ejemplos se aplica la Directiva de retención que se creó en el paso 2.
  
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

Una vez aplicada la nueva Directiva de retención a los buzones, puede tardar hasta 7 días en Exchange Online para que el Asistente para carpeta administrada procese estos buzones mediante la configuración de la nueva Directiva de retención. En lugar de esperar a que se ejecute el Asistente para carpeta administrada, puede usar el cmdlet **Start-ManagedFolderAssistant** para desencadenar manualmente el Asistente para que procese los buzones a los que aplicó la nueva Directiva de retención. 
  
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

- Después de habilitar el buzón de archivo de un usuario, considere la posibilidad de indicar al usuario que se pueden mover otros elementos del buzón (no solo los elementos de la carpeta elementos recuperables) al buzón de archivo. Esto se debe a que la Directiva de MRM predeterminada que se asigna a los buzones de correo de Exchange Online contiene una etiqueta de retención (denominada 2 años como predeterminada, mover a archivo) que mueve los elementos al buzón de archivo dos años después de la fecha en que se entregó el elemento al buzón o se creó mediante el usuario. Para obtener más información, vea [Directiva de retención predeterminada en Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=746954) .
    
- Después de habilitar el buzón de archivo de un usuario, también puede decirle al usuario que puede recuperar los elementos eliminados de la carpeta elementos recuperables de su buzón de archivo. Puede hacerlo en Outlook seleccionando la carpeta **elementos eliminados** en el buzón de archivo y, a continuación, haciendo clic en **recuperar elementos eliminados del servidor** en la ficha **Inicio** . Para obtener más información acerca de la recuperación de elementos eliminados, vea [recuperar elementos eliminados en Outlook para Windows](https://go.microsoft.com/fwlink/p/?LinkId=624829). 
