---
title: Cambiar la duración de retención para un buzón inactivo en Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 8/29/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid: MOE150
ms.assetid: bdee24ed-b8cf-4dd0-92ae-b86ec4661e6b
description: Una vez que un buzón de correo de Office 365 se convierte en inactivo, puede cambiar la duración de la Directiva de retención de Office 365 o de suspensión asignada al buzón inactivo. La duración de retención define cuánto tiempo se retienen los elementos en la carpeta Elementos recuperables.
ms.openlocfilehash: 7840131af3df32b8b8e5a0faa1b101f9ec8ef541
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/17/2019
ms.locfileid: "34155572"
---
# <a name="change-the-hold-duration-for-an-inactive-mailbox-in-office-365"></a>Cambiar la duración de retención para un buzón inactivo en Office 365

Un buzón inactivo se usa para conservar el correo electrónico de un antiguo empleado después de que abandone la organización. Un buzón se vuelve inactivo cuando se coloca en el buzón una retención por juicio, una directiva de retención de Office 365 o una retención asociada a un caso de exhibición de documentos electrónicos, y se elimina la cuenta de usuario de Office 365 correspondiente. The contents of an inactive mailbox are retained for the duration of the hold that was placed on the mailbox before it was made inactive. La duración de retención define cuánto tiempo se retienen los elementos en la carpeta Elementos recuperables. Cuando expira la duración de retención de un elemento en la carpeta Elementos recuperables, el elemento se elimina permanentemente (se purga) del buzón inactivo. Una vez que un buzón de correo se convierte en inactivo, puede cambiar la duración de la retención o la Directiva de retención de Office 365 asignada al buzón inactivo.
  
> [!IMPORTANT]
> Hemos pospuesto la fecha límite del 1 de julio de 2017 para crear conservaciones locales con el fin de desactivar buzones, pero más adelante este año o a principios del año que viene ya no podrá crear conservaciones locales en Exchange Online. A partir de ese momento, solo podrán usarse retenciones por juicio y directivas de retención de Office 365 para crear buzones inactivos. Aun así, se seguirán admitiendo los buzones inactivos existentes que estén en conservación local y podrá seguir administrando las conservaciones locales de buzones inactivos. Esto incluye el cambio de la duración de las conservaciones locales y la eliminación de forma permanente de buzones inactivos al quitar la conservación local. 
  
## <a name="before-you-begin"></a>Antes de empezar

- Debe usar Exchange Online PowerShell para cambiar la duración de retención para una retención por juicio en un buzón inactivo. No puede usar el Centro de administración de Exchange (EAC). Pero puede usar Exchange Online PowerShell o el EAC para cambiar la duración de retención para una conservación local. Puede usar el centro de seguridad y cumplimiento o el centro de seguridad & cumplimiento de PowerShell para cambiar la duración de retención de una directiva de retención de Office 365.
    
- Para conectarse a PowerShell de Exchange Online PowerShell o Security & Compliance Center, consulte uno de los siguientes temas:
    
  - [Conectarse a Exchange Online mediante PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554)
    
  - [Conectarse a Office 365 Security& Compliance Center PowerShell](https://go.microsoft.com/fwlink/?linkid=799771)
    
- Tenga en cuenta que las suspensiones asociadas con casos de eDiscovery son suspensiones infinitas, lo que significa que no se puede cambiar la duración de la retención. Los elementos se mantienen para siempre o hasta que se quita la retención y se elimina el buzón inactivo.
    
- Para obtener más información acerca de los buzones inactivos, consulte buzones inactivos [en Office 365](inactive-mailboxes-in-office-365.md).
    
## <a name="step-1-identify-the-holds-on-an-inactive-mailbox"></a>Paso 1: identificar las retenciones en un buzón inactivo

Debido a que los distintos tipos de retenciones o una o más directivas de retención de Office 365 pueden colocarse en un buzón inactivo, el primer paso es identificar las retenciones en un buzón inactivo.
  
Ejecute el siguiente comando en Exchange Online PowerShell para mostrar la información de retención de todos los buzones inactivos de la organización.
  
```
Get-Mailbox -InactiveMailboxOnly | FL DisplayName,Name,IsInactiveMailbox,LitigationHoldEnabled,LitigationHoldDuration,InPlaceHolds
```
   
El valor de **True** para la propiedad **LitigationHoldEnabled** indica que el buzón inactivo está en retención por juicio. Si una directiva de retención local, conservación de exhibición de documentos electrónicos u Office 365 se coloca en un buzón inactivo, se muestra un GUID para la Directiva de retención o retención como el valor de la propiedad **InPlaceHolds** . Por ejemplo, a continuación se muestran los resultados de 5 buzones inactivos. 
  
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
   
En la siguiente tabla se identifican los cinco tipos de retención que se usaron para convertir cada buzón en inactivo.
  
|**Buzón inactivo**|**Tipo de retención**|**Cómo identificar la retención en el buzón inactivo**|
|:-----|:-----|:-----|
|Ann Beebe  <br/> |Retención por juicio  <br/> |La propiedad *LitigationHoldEnabled* se establece en `True`.  <br/> |
|Pilar Pinilla  <br/> |Retención en contexto  <br/> |La propiedad *InPlaceHolds* contiene el GUID de la retención local que está colocada en el buzón inactivo. Puede decir que se trata de una conservación local porque el identificador no comienza con un prefijo.  <br/> Puede usar el `Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL` comando en Exchange Online PowerShell para obtener información sobre la conservación local en el buzón inactivo.  <br/> |
|Mario Necaise  <br/> |Directiva de retención de Office 365 de toda la organización en el centro de seguridad & cumplimiento  <br/> |La propiedad *InPlaceHolds* está vacía. Esto indica que una o varias directivas de retención de Office 365 de toda la organización o de todo el mundo se aplican al buzón inactivo. En este caso, puede ejecutar el `Get-OrganizationConfig | Select-Object -ExpandProperty InPlaceHolds` comando en Exchange Online PowerShell para obtener una lista de los GUID de las directivas de retención de Office 365 de toda la organización. El GUID de las directivas de retención de toda la organización que se aplican a los buzones de Exchange comienzan con el `mbx` prefijo; por ejemplo `mbxa3056bb15562480fadb46ce523ff7b02`.  <br/> <br/>Para identificar la Directiva de retención de Office 365 que se aplica al buzón inactivo, ejecute el siguiente comando en Security & Compliance Center PowerShell.  <br/><br/> `Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name`<br/><br/>
|Carol Olson  <br/> |Directiva de retención de Office 365 en el centro de cumplimiento de & de seguridad que se aplica a buzones específicos  <br/> |La propiedad *InPlaceHolds* contiene el GUID de la Directiva de retención de Office 365 que se aplica al buzón inactivo. Puede decir que se trata de una directiva de retención que se aplica a buzones específicos, ya que `mbx` el GUID comienza con el prefijo. Tenga en cuenta que si el GUID de la Directiva de retención aplicada al buzón inactivo `skp` empezó con el prefijo, esto indicaría que la Directiva de retención se aplica a las conversaciones de Skype empresarial.  <br/><br/> Para identificar la Directiva de retención de Office 365 que se aplica al buzón inactivo, ejecute el siguiente comando en Security & Compliance Center PowerShell.<br/><br/> `Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name` <br/><br/>Asegúrese de quitar el `mbx` prefijo `skp` o cuando ejecute este comando.  <br/> |
|Abraham McMahon  <br/> |suspensión de casos de exhibición de documentos electrónicos en el centro de seguridad & cumplimiento  <br/> |La propiedad *InPlaceHolds* contiene el GUID de la suspensión de casos de exhibición de documentos electrónicos que se coloca en el buzón inactivo. Puede decir que se trata de una suspensión de casos de exhibición de documentos electrónicos `UniH` porque el GUID comienza por el prefijo.  <br/> Puede usar el `Get-CaseHoldPolicy` cmdlet en Security _AMP_ Compliance Center PowerShell para obtener información sobre el caso de eDiscovery al que está asociado la retención en el buzón inactivo. Por ejemplo, puede ejecutar el comando `Get-CaseHoldPolicy <hold GUID without prefix> | FL Name` para mostrar el nombre de la suspensión de mayúsculas y minúsculas que se encuentra en el buzón inactivo. Asegúrese de quitar el `UniH` prefijo al ejecutar este comando.  <br/><br/> Para identificar el caso de eDiscovery al que está asociado la retención en el buzón inactivo, ejecute los siguientes comandos.  <br/><br/> `$CaseHold = Get-CaseHoldPolicy <hold GUID without prefix>`<br/><br/> `Get-ComplianceCase $CaseHold.CaseId | FL Name`<br/><br/><br/> **Nota:** No se recomienda usar la retención de exhibición de documentos electrónicos para los buzones inactivos. Esto se debe a que los casos de eDiscovery están pensados para casos específicos y de tiempo limitado relacionados con problemas legales. En algún momento, es probable que finalice un caso legal y se quitarán las suspensiones asociadas al caso y se cerrará (o eliminará) el caso de exhibición de documentos electrónicos. De hecho, si una retención que se coloca en un buzón inactivo está asociada a un caso de exhibición de documentos electrónicos y la retención se suelta o el caso de exhibición de documentos electrónicos se cierra o se elimina, el buzón inactivo se eliminará permanentemente. 

Para obtener más información acerca de las directivas de retención de Office 365, consulte [información general sobre las directivas de retención](retention-policies.md).
  
## <a name="step-2-change-the-hold-duration-for-an-inactive-mailbox"></a>Paso 2: cambiar la duración de retención para un buzón inactivo

Tras identificar el tipo de retención que está colocada en el buzón inactivo (y si hay varias retenciones), el siguiente paso es cambiar la duración para la retención. 
  
### <a name="change-the-duration-for-a-litigation-hold"></a>Cambiar la duración de una retención por juicio.

Esta es la manera de usar Exchange Online PowerShell para cambiar la duración de retención para una retención por juicio que se coloca en un buzón inactivo. No puede usar el EAC. Ejecute el siguiente comando para cambiar la duración de retención. En este ejemplo, se cambia la duración de retención a un período de tiempo ilimitado.
  
```
Set-Mailbox -InactiveMailbox -Identity <identity of inactive mailbox> -LitigationHoldDuration unlimited
```

El resultado es que los elementos del buzón inactivo se conservan indefinidamente o hasta que se quita la retención o hasta que la duración de retención se cambia a un valor diferente.
  
> [!TIP]
> La mejor manera de identificar un buzón inactivo es usando el valor **Distinguished Name** o **Exchange GUID**. El uso de uno de estos valores ayuda a impedir que se especifique accidentalmente el buzón equivocado. 
  
### <a name="change-the-duration-for-an-in-place-hold"></a>Cambiar la duración de una conservación local

 Puede usar el EAC o Exchange Online PowerShell para cambiar la duración de retención para una conservación local. 
  
#### <a name="use-the-eac-to-change-the-hold-duration"></a>Usar el EAC para cambiar la duración de retención

1. Si conoce el nombre de la conservación local que quiere cambiar, vaya al siguiente paso. De lo contrario, ejecute el siguiente comando para obtener el nombre de la conservación local colocada en el buzón inactivo. Use el GUID de conservación local que obtuvo en el [paso 1](#step-1-identify-the-holds-on-an-inactive-mailbox).

    ```
    Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID> | FL Name
    ```

2. In the EAC, go to **Compliance management** \> **In-Place eDiscovery &amp; Hold**.
    
3. Seleccione la conservación local que desea cambiar y, a continuación, haga clic en **Editar** ![icono](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif)editar.
    
4. On the **In-Place eDiscovery &amp; Hold** properties page, click **In-Place Hold**. 
    
5. Realice una de las siguientes acciones en función de la duración de retención actual:
    
1. Haga clic en **Retenido indefinidamente** para retener elementos durante un período de tiempo ilimitado. 
    
2. Haga clic en **especificar el número de días que se conservarán los elementos relacionados con la fecha de recepción** para contener los elementos de un período específico. Type the number of days that you want to hold items for. 
    
    ![Captura de pantalla del cambio de duración para una conservación local](media/cfcfd92a-9d65-40c0-90ef-ab72697b0166.png)
  
6. Haga clic en **Guardar**.
    
#### <a name="use-exchange-online-powershell-to-change-the-hold-duration"></a>Usar Exchange Online PowerShell para cambiar la duración de retención

1. Si conoce el nombre de la conservación local que quiere cambiar, vaya al siguiente paso. De lo contrario, ejecute el siguiente comando para obtener el nombre de la conservación local colocada en el buzón inactivo. Use el GUID de conservación local que obtuvo en el [paso 1](#step-1-identify-the-holds-on-an-inactive-mailbox).

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
    
- **¿Se sigue procesando una directiva de retención de Exchange en buzones inactivos?** Si una directiva de retención de Exchange (la característica de administración de registros de mensajería, o MRM, en Exchange Online) se aplicó a un buzón de correo cuando se inactivo, las directivas de eliminación (que son etiquetas de retención configuradas con una acción de retención de **eliminación** ) se seguir procesándose en el buzón inactivo. Esto significa que los elementos etiquetados con una directiva de eliminación se mueven a la carpeta Elementos recuperables cuando expira el período de retención. Esos elementos luego se purgan del buzón inactivo cuando expira la duración de retención de un elemento. 
    
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
   
- **Si se colocan muchas suspensiones en un buzón inactivo, no se mostrarán todos los GUID de retención.** Puede ejecutar el siguiente comando para mostrar los GUID de todas las suspensiones (excepto las suspensiones por juicio) que se colocan en un buzón inactivo. 
    
    ```
    Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox> | Select-Object -ExpandProperty InPlaceHolds
    ```
