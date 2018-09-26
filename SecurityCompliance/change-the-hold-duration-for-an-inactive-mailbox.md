---
title: Cambiar la duración de retención para un buzón inactivo en Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 8/29/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid: MOE150
ms.assetid: bdee24ed-b8cf-4dd0-92ae-b86ec4661e6b
description: Después de un buzón de Office 365 se realiza como inactivo, puede cambiar la duración de la suspensión o la directiva de retención de Office 365 asignada para el buzón de correo inactivo. La duración de retención define cuánto tiempo los elementos en la carpeta se conservan de elementos recuperables.
ms.openlocfilehash: e3d1d6c7ec0311813dfa1144cc960d2fed9e160d
ms.sourcegitcommit: 7956955cd919f6e00b64e4506605a743c5872549
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/26/2018
ms.locfileid: "25038063"
---
# <a name="change-the-hold-duration-for-an-inactive-mailbox-in-office-365"></a>Cambiar la duración de retención para un buzón inactivo en Office 365

Un buzón inactivo se utiliza para retener el correo electrónico de un empleado anterior después de que abandona la organización. Un buzón de correo, se convierte en inactivo cuando un juicio, una retención en contexto, una directiva de retención de Office 365, o una suspensión a la que está asociado con un caso de exhibición de documentos electrónicos se coloca en el buzón de correo y se elimina la cuenta de usuario de Office 365 correspondiente. El contenido de un buzón inactivo se conserva para la duración de la suspensión a la que se realizó en el buzón de correo antes de que se ha realizado como inactiva. La duración de retención define cuánto tiempo los elementos en la carpeta se conservan de elementos recuperables. Cuando expire la duración de retención de un elemento en la carpeta elementos recuperables, el elemento se elimina de manera permanente (Purgar) desde el buzón de correo inactivo. Después de un buzón de correo se realiza como inactiva, puede cambiar la duración de la suspensión o la directiva de retención de Office 365 asignada para el buzón de correo inactivo.
  
> [!IMPORTANT]
> Hemos pospuesto la fecha límite del 1 de julio de 2017 para crear conservaciones locales con el fin de desactivar buzones, pero más adelante este año o a principios del año que viene ya no podrá crear conservaciones locales en Exchange Online. A partir de ese momento, solo podrán usarse retenciones por juicio y directivas de retención de Office 365 para crear buzones inactivos. Aun así, se seguirán admitiendo los buzones inactivos existentes que estén en conservación local y podrá seguir administrando las conservaciones locales de buzones inactivos. Esto incluye el cambio de la duración de las conservaciones locales y la eliminación de forma permanente de buzones inactivos al quitar la conservación local. 
  
## <a name="before-you-begin"></a>Antes de empezar

- Se debe usar Exchange Online PowerShell para cambiar la duración de retención para un juicio en un buzón de correo inactivo. No puede usar el centro de administración de Exchange (EAC). Pero se puede usar Exchange Online PowerShell o el CEF para cambiar la duración de retención para una retención local. Puede usar la seguridad de Office 365 &amp; centro de cumplimiento o la seguridad &amp; PowerShell de centro de cumplimiento para cambiar la duración de retención para una directiva de retención de Office 365.
    
- Para conectarse a Exchange Online PowerShell o seguridad &amp; PowerShell de centro de cumplimiento, vea uno de los siguientes temas:
    
  - [Conectarse a Exchange Online mediante PowerShell remoto](https://go.microsoft.com/fwlink/p/?linkid=396554)
    
  - [Conectarse a PowerShell del Centro de seguridad y cumplimiento de Office 365](https://go.microsoft.com/fwlink/?linkid=799771)
    
- Tenga en cuenta que contiene asociado con los casos de exhibición de documentos electrónicos son suspensiones infinitas, lo que significa que no hay ninguna duración de retención que se puede cambiar. Se conservan los elementos indefinidamente o hasta que se elimina la suspensión y se elimina el buzón de correo inactivo.
    
- Para obtener más información acerca de los buzones de correo inactivos, vea [buzones inactivos en Office 365](inactive-mailboxes-in-office-365.md).
    
## <a name="step-1-identify-the-holds-on-an-inactive-mailbox"></a>Paso 1: identificar las retenciones en un buzón inactivo

Debido a que los distintos tipos de suspensiones o una o varias directivas de retención de Office 365 es posible que se coloca en un buzón de correo inactivo, es el primer paso identificar las suspensiones en un buzón de correo inactivo.
  
Ejecute el siguiente comando en Exchange Online PowerShell para mostrar la información de espera para todos los buzones inactivos en su organización.
  
```
Get-Mailbox -InactiveMailboxOnly | FL DisplayName,Name,IsInactiveMailbox,LitigationHoldEnabled,LitigationHoldDuration,InPlaceHolds
```
   
El valor **True** para la propiedad **LitigationHoldEnabled** indica que el buzón de correo inactivo está en suspensión por litigio. Si una retención en contexto, mantenga presionada la exhibición de documentos electrónicos o directiva de retención de Office 365 se coloca en un buzón de correo inactivo, un GUID de la directiva de retención o suspensión se muestra como el valor de la propiedad **InPlaceHolds** . Por ejemplo, el siguiente muestra los resultados para buzones inactivos 5. 
  
||
|:-----|
|
```
DisplayName           : Ann Beebe
Name                  : annb
IsInactiveMailbox     : True
LitigationHoldEnabled : True
LitigationHoldDuration: 365.00:00:00
InPlaceHolds          : {}
...
DisplayName           : Pilar Pinilla
Name                  : pilarp
IsInactiveMailbox     : True
LitigationHoldEnabled : False
LitigationHoldDuration: Unlimited
InPlaceHolds          : {c0ba3ce811b6432a8751430937152491}
...
DisplayName           : Mario Necaise
Name                  : marion
IsInactiveMailbox     : True
LitigationHoldEnabled : False
LitigationHoldDuration: Unlimited
InPlaceHolds          : {}
...
DisplayName           : Carol Olson
Name                  : carolo
IsInactiveMailbox     : True
LitigationHoldEnabled : False
LitigationHoldDuration: Unlimited
InPlaceHolds          : {mbxcdbbb86ce60342489bff371876e7f224}
...
DisplayName           : Abraham McMahon
Name                  : abrahamm
IsInactiveMailbox     : True
LitigationHoldEnabled : False
LitigationHoldDuration: Unlimited
InPlaceHolds          : {UniH7d895d48-7e23-4a8d-8346-533c3beac15d}
```
   
En la siguiente tabla identifica los cinco tipos de espera diferentes que se usaron para definir cada buzón de correo como inactiva.
  
|**Buzón de correo inactivo**|**Tipo de suspensión**|**Cómo identificar la suspensión en el buzón de correo inactivo**|
|:-----|:-----|:-----|
|Ana Díaz  <br/> |Retención por juicio  <br/> |La propiedad *LitigationHoldEnabled* está establecida en `True`.  <br/> |
|Pilar Pinilla  <br/> |Retención en contexto  <br/> |La propiedad *InPlaceHolds* contiene el GUID de la retención local que se coloca en el buzón de correo inactivo. Puede saber que esto es una retención local debido a que el identificador no se inicia con un prefijo.<br/> Puede usar la ' Get-MailboxSearch - InPlaceHoldIdentity<hold GUID> | FL' command en Exchange Online PowerShell para obtener información acerca de la retención local en el buzón de correo inactivo.  <br/> |
|Mario Necaise  <br/> |Directiva de retención de Office 365 de toda la organización en la seguridad &amp; centro de cumplimiento  <br/> |La propiedad *InPlaceHolds* está vacía. Esto indica que uno o varios (Exchange toda la) o de toda la organización Office 365 directiva de retención se aplica para el buzón de correo inactivo. En este caso, puede ejecutar el ' Get-OrganizationConfig | Select-Object - ExpandProperty InPlaceHolds` command in Exchange Online PowerShell to get a list of the GUIDs for organization-wide Office 365 retention policies. The GUID for organization-wide retention policies that are applied to Exchange mailboxes start with the  `los buzones` prefix; for example  `mbxa3056bb15562480fadb46ce523ff7b02`.  <br/> <br/>To identity the Office 365 retention policy that's applied to the inactive mailbox, run the following command in Security &amp; Compliance Center PowerShell.  <br/><br/> `Get-RetentionCompliancePolicy<retention policy GUID without prefix> | Nombre de FL'<br/><br/>
|Ana Olson  <br/> |Directiva de retención de Office 365 en la seguridad &amp; centro de cumplimiento que se aplican a buzones específicos  <br/> |La propiedad *InPlaceHolds* contiene el GUID de la directiva de retención de Office 365 que se aplica a los buzones de correo inactivo. Puede indicar que se trata de una directiva de retención que se aplica a buzones específicos debido a que el GUID comienza por la `mbx` prefijo. Tenga en cuenta que si el GUID de la directiva de retención aplicada para el buzón de correo inactivo iniciado con la `skp` prefijo, que podría indicar que la directiva de retención se aplica a Skype para conversaciones de negocios.<br/><br/> En directiva de retención de Office 365 de identidad que se aplica a los buzones de correo inactivo, ejecute el siguiente comando en seguridad &amp; PowerShell de centro de cumplimiento.<br/><br/> ' Get-RetentionCompliancePolicy<retention policy GUID without prefix> | Nombre de FL` <br/><br/>Be sure to remove the  `los buzones` or  `skp' prefijo al ejecutar este comando.  <br/> |
|Abraham McMahon  <br/> |conservación de caso de exhibición de documentos electrónicos en la seguridad &amp; centro de cumplimiento  <br/> |La propiedad *InPlaceHolds* contiene el GUID de la suspensión de casos de exhibición de documentos electrónicos que se coloca en el buzón de correo inactivo. Puede saber esto es una suspensión de casos de exhibición de documentos electrónicos porque el GUID comienza por la `UniH` prefijo.<br/> Puede usar el `Get-CaseHoldPolicy` cmdlet en seguridad &amp; PowerShell de centro de cumplimiento para obtener información sobre el caso de exhibición de documentos electrónicos que está asociada la suspensión en el buzón de correo inactivo. Por ejemplo, puede ejecutar el comando ' Get-CaseHoldPolicy<hold GUID without prefix> | Nombre de FL` to display the name of the case hold that's on the inactive mailbox. Be sure to remove the  `UniH` prefix when you run this command.  <br/><br/> To identity the eDiscovery case that the hold on the inactive mailbox is associated with, run the following commands.  <br/><br/> `$CaseHold = Get-CaseHoldPolicy <hold GUID without prefix> `<br/><br/> `$CaseHold.CaseId Get-ComplianceCase | Nombre de FL'<br/><br/><br/> **Nota:** No se recomienda el uso de exhibición de documentos electrónicos contiene de buzones inactivos. Eso es porque los casos de exhibición de documentos electrónicos están diseñados para casos específicos, el límite de tiempo relacionado con un problema legal. En algún momento, probablemente finalizará un caso legal y las suspensiones asociadas con el caso se quitará y será el caso de exhibición de documentos electrónicos cerrado (o eliminar). De hecho, si una suspensión que se coloca en un buzón inactivo está asociada a un caso de exhibición de documentos electrónicos y se libera la suspensión o el caso de exhibición de documentos electrónicos se cierra o se elimina, el buzón de correo inactivo se eliminarán permanentemente. 

Para obtener más información acerca de las directivas de retención de Office 365, vea [información general de las directivas de retención](retention-policies.md).
  
## <a name="step-2-change-the-hold-duration-for-an-inactive-mailbox"></a>Paso 2: cambiar la duración de retención para un buzón inactivo

Tras identificar el tipo de retención que está colocada en el buzón inactivo (y si hay varias retenciones), el siguiente paso es cambiar la duración para la retención. 
  
### <a name="change-the-duration-for-a-litigation-hold"></a>Cambiar la duración de una retención por juicio.

Aquí es cómo usar PowerShell en línea de Exchange para cambiar la duración de retención para un juicio que se coloca en un buzón de correo inactivo. No se puede usar el EAC. Ejecute el siguiente comando para cambiar la duración de la suspensión. En este ejemplo, se cambia la duración de retención a un período de tiempo ilimitado.
  
```
Set-Mailbox -InactiveMailbox -Identity <identity of inactive mailbox> -LitigationHoldDuration unlimited
```

El resultado es que se conservan los elementos en el buzón de correo inactivo indefinidamente o hasta que se elimina la suspensión o se cambia la duración de retención a un valor diferente.
  
> [!TIP]
> La mejor manera de identificar un buzón inactivo es usando el valor **Distinguished Name** o **Exchange GUID**. El uso de uno de estos valores ayuda a impedir que se especifique accidentalmente el buzón equivocado. 
  
### <a name="change-the-duration-for-an-in-place-hold"></a>Cambiar la duración de una conservación local

 Puede usar el CEF o Exchange Online PowerShell para cambiar la duración de retención para una retención local. 
  
#### <a name="use-the-eac-to-change-the-hold-duration"></a>Usar el EAC para cambiar la duración de retención

1. Si conoce el nombre de la retención local que desea cambiar, vaya al paso siguiente. De lo contrario, ejecute el siguiente comando para obtener el nombre de la retención local que se coloca en el buzón de correo inactivo. Utilice el GUID de suspensión en contexto que obtuvo en el [paso 1](#step-1-identify-the-holds-on-an-inactive-mailbox).

    ```
    Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID> | FL Name
    ```

2. En el EAC, vaya a **administración de cumplimiento** \> **exhibición de documentos electrónicos en contexto &amp; suspensión**.
    
3. Seleccione la retención local que desea cambiar y, a continuación, haga clic en **Editar** ![icono Editar](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif).
    
4. En la **exhibición de documentos electrónicos en contexto &amp; suspensión** propiedades de página, haga clic en **Retención en contexto**. 
    
5. Realice una de las siguientes acciones en función de la duración de retención actual:
    
1. Haga clic en **Retenido indefinidamente** para retener elementos durante un período de tiempo ilimitado. 
    
2. Haga clic en **Especificar número de días para retener elementos con respecto a su fecha de recepción** para retener elementos durante un período específico. Escriba el número de días que desea retener elementos para. 
    
    ![Captura de pantalla del cambio de duración para una conservación local](media/cfcfd92a-9d65-40c0-90ef-ab72697b0166.png)
  
6. Haga clic en **Guardar**.
    
#### <a name="use-exchange-online-powershell-to-change-the-hold-duration"></a>Use Exchange Online PowerShell para cambiar la duración de retención

1. Si conoce el nombre de la retención local que desea cambiar, vaya al paso siguiente. De lo contrario, ejecute el siguiente comando para obtener el nombre de la retención local que se coloca en el buzón de correo inactivo. Utilice el GUID de suspensión en contexto que obtuvo en el [paso 1](#step-1-identify-the-holds-on-an-inactive-mailbox).

    ```
    Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID> | FL Name
    ```

2. Ejecute el siguiente comando para cambiar la duración de retención. En este ejemplo, se cambia la duración de retención a 2.555 días (aproximadamente 7 años). 
    
    ```
    Set-MailboxSearch <identity of In-Place Hold> -ItemHoldPeriod 2555
    ```

     Para cambiar la duración de retención a un período de tiempo ilimitado, use  _-ItemHoldPeriod unlimited_.
  
## <a name="more-information"></a>Más información

- **¿Cómo se calcula la duración de retención para un elemento en un buzón inactivo?** La duración se calcula desde la fecha original en que un elemento de buzón se recibe o se crea. 
    
- **¿Qué sucede cuando expira la duración de retención?** Cuando expira la duración de retención de un elemento en la carpeta Elementos recuperables, el elemento se elimina permanentemente (se purga) del buzón inactivo. Si no hay ninguna duración especificada para la retención que se coloca en el buzón inactivo, nunca se purgan los elementos de la carpeta Elementos recuperables (a menos que se cambie la duración de retención del buzón inactivo). 
    
- **Es una directiva de retención de Exchange aún se procesan en buzones de correo inactivos?** Si se ha aplicado una directiva de retención de Exchange (los registros de mensajes de administración o MRM, característica en Exchange Online) a un buzón de correo cuando se realizó inactiva, va las directivas de eliminación (que están configuradas con una acción de retención **Eliminar** las etiquetas de retención) continuar que va a procesar en el buzón de correo inactivo. Esto significa que se mueven los elementos etiquetados con una directiva de eliminación a la carpeta elementos recuperables cuando expire el período de retención. Esos elementos, a continuación, se purgan desde el buzón de correo inactivo cuando expire la duración de retención para un elemento. 
    
    Por el contrario, se ignora cualquier directiva de archivo (que son etiquetas de retención configuradas con una acción de retención **MoveToArchive** ) que esté incluida en la directiva de retención asignada a un buzón inactivo. Eso significa que los elementos de un buzón inactivo etiquetados con una directiva de archivo permanecen en el buzón principal cuando expira el período de retención. No se mueven al buzón de archivo o a la carpeta Elementos recuperables en el buzón de archivo. Dado que un usuario no puede iniciar sesión en un buzón inactivo, no existen motivos para consumir los recursos del centro de datos para procesar las directivas de archivo. 
    
- **Para comprobar la nueva duración de retención, ejecute uno de los siguientes comandos.** El primer comando es para retención por juicio; el segundo es para conservación local. 

    ```
    Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox> | FL LitigationHoldDuration
    ```

    ```
    Get-MailboxSearch <identity of In-Place Hold> | FL ItemHoldPeriod
    ```

- **Al igual que los buzones habituales, el Asistente para carpeta administrada (MFA) también procesa buzones inactivos.** En Exchange Online, el MFA procesa buzones una vez cada siete días aproximadamente. Después de cambiar la duración de retención para un buzón inactivo, puede usar el cmdlet **Start-ManagedFolderAssistant** para empezar a procesar inmediatamente la nueva duración de retención para el buzón inactivo. Ejecute el comando siguiente. 

    ```
    Start-ManagedFolderAssistant -InactiveMailbox <identity of inactive mailbox>
    ```
   
- **Si se colocan una gran cantidad de suspensiones en un buzón inactivo, no todos de la suspensión se mostrará los GUID.** Puede ejecutar el siguiente comando para mostrar los GUID para todas las suspensiones (excepto las suspensiones litigios) que se colocan en un buzón de correo inactivo. 
    
    ```
    Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox> | Select-Object -ExpandProperty InPlaceHolds
    ```
