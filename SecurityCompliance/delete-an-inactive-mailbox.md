---
title: Eliminar un buzón inactivo en Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 9/5/2017
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: f5caf497-5e8d-4b7a-bfff-d02942f38150
description: Si ya no necesita conservar el contenido de un buzón inactivo de Office 365, puede eliminar el buzón inactivo de forma permanente quitando la retención. Después de quitar la retención, el buzón inactivo se marca para su eliminación y se elimina de forma permanente después de su procesamiento.
ms.openlocfilehash: f1aa29b0e40d02e4b6450202c0b2a34ae3075677
ms.sourcegitcommit: e7a776a04ef6ed5e287a33cfdc36aa2d72862b55
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/29/2019
ms.locfileid: "31001073"
---
# <a name="delete-an-inactive-mailbox-in-office-365"></a>Eliminar un buzón inactivo en Office 365

Un buzón inactivo se usa para conservar el correo electrónico de un antiguo empleado después de que este se va de la organización. Cuando ya no necesita conservar el contenido de un buzón inactivo, puede quitar su retención para eliminarlo de forma permanente. Además, es posible que varias retenciones se coloquen en un buzón inactivo. Por ejemplo, un buzón inactivo puede colocarse en retención de litigios y en una o varias retenciones locales. Además, se puede aplicar una directiva de retención de Office 365 (creada en el centro de seguridad y cumplimiento en Office 365 o Microsoft 365) al buzón inactivo. Debe quitar todas las suspensiones y las directivas de retención de Office 365 de un buzón inactivo para eliminarlo. Después de quitar las directivas de retención y retención, el buzón inactivo se marca para su eliminación y se elimina de forma permanente después de su procesamiento.
  
> [!IMPORTANT]
> Hemos pospuesto la fecha límite del 1 de julio de 2017 para crear conservaciones locales con el fin de desactivar buzones, pero más adelante este año o a principios del año que viene ya no podrá crear conservaciones locales en Exchange Online. A partir de ese momento, solo podrán usarse retenciones por juicio y directivas de retención de Office 365 para crear buzones inactivos. Aun así, se seguirán admitiendo los buzones inactivos existentes que estén en conservación local y podrá seguir administrando las conservaciones locales de buzones inactivos. Esto incluye el cambio de la duración de las conservaciones locales y la eliminación de forma permanente de buzones inactivos al quitar la conservación local. 
  
Consulte la sección [More information](#more-information) para ver una descripción de lo que sucede una vez que se quitan las retenciones de un buzón inactivo. 
  
## <a name="before-you-begin"></a>Antes de empezar

- Debe usar Exchange Online PowerShell para quitar una retención por juicio de un buzón inactivo. No puede usar el Centro de administración de Exchange (EAC). Para obtener instrucciones paso a paso, consulte [conectarse a Exchange Online PowerShell](https://go.microsoft.com/fwlink/?linkid=396554). Puede usar Exchange Online PowerShell o el EAC para quitar una retención local de un buzón inactivo. 
    
- Puede copiar el contenido de un buzón inactivo a otro buzón antes de quitar la retención y eliminar un buzón inactivo. Para obtener más información, consulte [restaurar un buzón inactivo en Office 365](restore-an-inactive-mailbox.md).
    
- Si quita la Directiva de retención de Office 365 de un buzón inactivo y el período de retención de buzón eliminado temporalmente para el buzón ha expirado, el buzón se eliminará permanentemente. Una vez eliminado, no se puede recuperar. Antes de quitar la retención, asegúrese de que ya no necesita el contenido del buzón. Si desea volver a activar un buzón inactivo, puede recuperarlo. Para obtener más información, consulte [recuperar un buzón inactivo en Office 365](recover-an-inactive-mailbox.md).
    
- Para obtener más información acerca de los buzones inactivos, consulte buzones inactivos [en Office 365](inactive-mailboxes-in-office-365.md).
    
## <a name="step-1-identify-the-holds-on-an-inactive-mailbox"></a>Paso 1: identificar las retenciones en un buzón inactivo

Como se mencionó anteriormente, una retención por juicio, una retención local o la Directiva de retención de Office 365 se puede colocar en un buzón inactivo. El primer paso es identificar las retenciones de un buzón inactivo.
  
Ejecute el siguiente comando para mostrar la información de la retención de todos los buzones inactivos en su organización.
  
```
Get-Mailbox -InactiveMailboxOnly | FL DisplayName,Name,IsInactiveMailbox,LitigationHoldEnabled,InPlaceHolds
```

El valor de **True** para la propiedad **LitigationHoldEnabled** indica que el buzón inactivo está en retención por juicio. Si una retención local se coloca en un buzón inactivo, el GUID de la retención se muestra como el valor de la propiedad **InPlaceHolds**. Por ejemplo, los siguientes resultados para dos buzones inactivos muestran que una retención por juicio se coloca en Ann Beebe y dos retenciones locales se colocan en Pilar Pinilla. 
  
```
DisplayName           : Ann Beebe
Name                  : annb
IsInactiveMailbox     : True
LitigationHoldEnabled : True
InPlaceHolds          : {}
...
DisplayName           : Pilar Pinilla
Name                  : pilarp
IsInactiveMailbox     : True
LitigationHoldEnabled : False
InPlaceHolds          : {c0ba3ce811b6432a8751430937152491, ba6f4ba25b62490aaaa253eea27426ab}
```

> [!TIP]
> Si muchas retenciones locales se colocan en un buzón inactivo, no se mostrarán todos los GUID de retenciones locales. Puede ejecutar el siguiente comando para mostrar todos los GUID de conservación local:`Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox> | Select-Object -ExpandProperty InPlaceHolds`
  
## <a name="step-2-remove-a-hold-from-an-inactive-mailbox"></a>Paso 2: Quitar una retención de un buzón inactivo

Tras identificar el tipo de retención que está colocada en el buzón inactivo (y si hay varias retenciones), el siguiente paso es quitar las retenciones del buzón. Como se mencionó anteriormente, tiene que quitar todas las retenciones para eliminar de forma permanente un buzón inactivo. 
  
### <a name="remove-a-litigation-hold"></a>Quitar una retención de litigios

Como se mencionó anteriormente, tiene que usar Windows PowerShell para quitar una retención de litigios de un buzón inactivo. No puede usar el EAC. Ejecute el siguiente comando para quitar una retención de litigios.
  
```
Set-Mailbox -InactiveMailbox -Identity <identity of inactive mailbox> -LitigationHoldEnabled $false
```

> [!TIP]
> La mejor manera de identificar un buzón inactivo es usando el valor Nombre distintivo o GUID de Exchange. El uso de uno de estos valores ayuda a impedir que se especifique accidentalmente el buzón equivocado. 
  
### <a name="remove-in-place-holds"></a>Quitar retenciones locales

 Hay dos maneras de quitar una retención local de un buzón inactivo: 
  
- **Eliminar el objeto de retención local** Si el buzón inactivo que quiere eliminar de forma permanente es el único buzón de origen de una conservación local, simplemente puede eliminar el objeto de retención local. 
    
    > [!NOTE]
    > Tiene que deshabilitar la retención antes de poder eliminar un objeto de retención local. Si intenta eliminar un objeto de retención local que tiene habilitada la retención, recibirá un mensaje de error. 
  
- **Quitar el buzón inactivo como buzón de origen de una retención local** Si quiere conservar otros buzones de origen para una retención local, puede quitar el buzón inactivo de la lista de buzones de origen y mantener el objeto de retención local. 
    
#### <a name="use-the-eac-to-delete-an-in-place-hold"></a>Usar el EAC para eliminar una retención local

1. Si conoce el nombre de la retención local que quiere eliminar, puede ir al siguiente paso. De lo contrario, ejecute el siguiente comando para obtener el nombre de la retención local que se coloca en el buzón inactivo que quiere eliminar de forma permanente. Use el GUID de retención local que obtuvo en [Paso 1: Identificar las retenciones en un buzón inactivo](#step-1-identify-the-holds-on-an-inactive-mailbox).
    
```
  Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID> | FL Name
```

2. In the EAC, go to **Compliance management** \> **In-Place eDiscovery &amp; Hold**.
    
3. Seleccione la conservación local que desea eliminar y, a continuación, haga clic en **Editar** ![icono](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif)editar.
    
4. On the **In-Place eDiscovery &amp; Hold** properties page, click **In-Place Hold**, uncheck the **Place content matching the search query in selected mailboxes on hold** box, and then click **Save**.
    
5. On the **In-Place eDiscovery &amp; Hold** page, select the In-Place Hold again, and then click **Delete**![Delete icon](media/87565fbb-5147-4f22-9ed7-1c18ce664392.png).
    
6. En la advertencia, haga clic en **Sí** para eliminar la retención local. 
    
#### <a name="use-exchange-online-powershell-to-delete-an-in-place-hold"></a>Usar Exchange Online PowerShell para eliminar una conservación local

1. Cree una variable que contenga las propiedades de la retención local que quiera eliminar. Use el GUID de retención local que obtuvo en [Paso 1: Identificar las retenciones en un buzón inactivo](#step-1-identify-the-holds-on-an-inactive-mailbox).
    
```
  $InPlaceHold = Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID>
```

2. Deshabilite la retención en la retención local.
    
```
  Set-MailboxSearch $InPlaceHold.Name -InPlaceHoldEnabled $false
```

3. Elimine la retención local.
    
```
  Remove-MailboxSearch $InPlaceHold.Name
```

#### <a name="use-the-eac-to-remove-an-inactive-mailbox-from-an-in-place-hold"></a>Use el EAC para quitar un buzón inactivo de una retención local.

1. Si conoce el nombre de la retención local que está colocada en el buzón inactivo, puede ir al siguiente paso. De lo contrario, ejecute el siguiente comando para obtener el nombre de la retención local colocada en el buzón. Use el GUID de retención local que obtuvo en [Paso 1: Identificar las retenciones en un buzón inactivo](#step-1-identify-the-holds-on-an-inactive-mailbox).
    
```
  Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID> | FL Name
```

2. In the EAC, go to **Compliance management** \> **In-Place eDiscovery &amp; Hold**.
    
3. Seleccione la retención local que está colocada en el buzón inactivo y, a continuación **** ![, haga clic](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif)en Editar icono de edición.
    
4. On the **In-Place eDiscovery &amp; Hold** properties page, click **Sources**.
    
5. En la lista de buzones de origen, haga clic en el nombre del buzón inactivo que quiere quitar y después haga clic en **Quitar**![Icono de quitar](media/adf01106-cc79-475c-8673-065371c1897b.gif).
    
6. Haga clic en **Guardar** para guardar el cambio. Se muestra un mensaje que indica que la operación se completó correctamente. 
    
7. Repita los pasos 1 a 6 para quitar otras retenciones locales colocadas en el buzón inactivo.
    
#### <a name="use-exchange-online-powershell-to-remove-an-inactive-mailbox-from-an-in-place-hold"></a>Usar Exchange Online PowerShell para quitar un buzón inactivo de una conservación local

Si la retención local contiene un gran número de buzones de origen, es posible que el buzón local no aparezca en la página **Orígenes** en el EAC. Hasta 3.000 buzones se muestran en la página **Orígenes** cuando edita una retención local. Si un buzón inactivo no aparece en la lista de la página **orígenes** , puede usar Exchange Online PowerShell para quitarlo de la conservación local. 
  
1. Cree una variable que contenga las propiedades de la retención local colocada en el buzón inactivo. Use el GUID de retención local que obtuvo en [Paso 1: Identificar las retenciones en un buzón inactivo](#step-1-identify-the-holds-on-an-inactive-mailbox).
    
```
  $InPlaceHold = Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID>
```

2. Compruebe que el buzón inactivo aparezca como un buzón de origen para la retención local. 
    
```
  $InPlaceHold.Sources
```

   **Nota:** La ** propiedad Sources de la retención local identifica los buzones de origen por sus propiedades *legacyExchangeDN* . Como esta propiedad identifica exclusivamente los buzones inactivos, el uso de la propiedad *Sources* de la retención local ayuda a impedir que se elimine el buzón equivocado. También ayuda a evitar problemas si dos buzones tienen el mismo alias o dirección SMTP. 
   
3. Quite el buzón inactivo de la lista de buzones de origen en la variable. Asegúrese de usar la propiedad **LegacyExchangeDN** del buzón inactivo devuelto por el comando en el paso anterior. 
    
```
  $InPlaceHold.Sources.Remove("<LegacyExchangeDN of the inactive mailbox>")
```

    For example, the following command removes the inactive mailbox for Pilar Pinilla.
    
  ```
  $InPlaceHold.Sources.Remove("/o=contoso/ou=Exchange Administrative Group (FYDIBOHF23SPDLT)/cn=Recipients/cn=9c8dfff651ec4908950f5df60cbbda06-pilarp")
  ```

4. Compruebe que el buzón inactivo se quita de la lista de buzones de origen en la variable.
    
```
  $InPlaceHold.Sources
```

5. Modifique la retención local con la lista actualizada de buzones de origen, que no incluye el buzón inactivo.
    
```
  Set-MailboxSearch $InPlaceHold.Name -SourceMailboxes $InPlaceHold.Sources
```

6. Compruebe que el buzón inactivo se quita de la lista de buzones de origen para la retención local.
    
```
  Get-MailboxSearch $InPlaceHold.Name | FL Sources
```

## <a name="more-information"></a>Más información

- **Un buzón inactivo es un tipo de buzón eliminado temporalmente.** En Exchange Online, un buzón eliminado temporalmente es un buzón que se ha eliminado, pero se pueden recuperar en un período de retención específico. El período de retención del buzón eliminado temporalmente en Exchange Online es de 30 días. Esto significa que el buzón se puede recuperar en un plazo de 30 días después de eliminarse temporalmente. Después de 30 días, un buzón eliminado temporalmente se marca para su eliminación permanente y no puede recuperarse. 
    
- **¿Qué ocurre después de quitar la retención en un buzón inactivo?** El buzón de correo se considera como otros buzones eliminados temporalmente y se marca para eliminación permanente una vez que expire el período de retención de 30 días del buzón eliminado temporalmente. Este período de retención empieza en la fecha en que el buzón se volvió inactivo por primera vez. Esta fecha se conoce como la fecha de eliminación temporal, que es la fecha cuando la cuenta de usuario de Office 365 correspondiente se eliminó o cuando el buzón de Exchange Online se eliminó con el cmdlet **Remove-Mailbox**. La fecha de eliminación temporal no es la fecha en que se quita la retención. 
    
- **¿Un buzón inactivo se elimina de forma permanente inmediatamente después de quitar la retención?** Si la fecha de eliminación temporal para un buzón inactivo supera 30 días, el buzón no se eliminará permanentemente en cuanto se quite la retención. El buzón se marcará para su eliminación permanente y se eliminará la próxima vez que se procese. 
    
- **¿Cómo afecta a los buzones inactivos el período de retención de buzones eliminados temporalmente?** Si la fecha de eliminación temporal para un buzón inactivo es más de 30 días antes de la fecha en que se ha quitado la retención, el buzón se marca para su eliminación permanente. Pero si un buzón inactivo tiene una fecha de eliminación temporal en los últimos 30 días y se quita la retención, es posible recuperar el buzón hasta que expire el período de retención de buzones eliminados temporalmente. Para obtener más información, consulte [Delete or restore User mailboxes in Exchange Online](https://go.microsoft.com/fwlink/?linkid=856835). Una vez que expire el período de retención de buzones eliminados temporalmente, debe seguir los procedimientos para recuperar un buzón inactivo. Para obtener más información, consulte [recuperar un buzón inactivo en Office 365](recover-an-inactive-mailbox.md).
    
- **¿Cómo mostrar información sobre un buzón inactivo después de quitar la retención?** Una vez que se quita una retención y el buzón inactivo se revierte a un buzón eliminado temporalmente, no se devolverá mediante el parámetro *InactiveMailboxOnly* con el cmdlet **Get-Mailbox** . Pero puede mostrar información sobre el buzón mediante el comando **Get-Mailbox -SoftDeletedMailbox**. Por ejemplo: 
    
```
  Get-Mailbox -SoftDeletedMailbox -Identity pilarp | FL Name,Identity,LitigationHoldEnabled,In
  Placeholds,WhenSoftDeleted,IsInactiveMailbox
  Name                   : pilarp
  Identity               : Soft Deleted Objects\pilarp
  LitigationHoldEnabled  : False
  InPlaceHolds           : {}
  WhenSoftDeleted        : 10/30/2014 1:19:04 AM
  IsInactiveMailbox      : False
```
  
En el ejemplo anterior, la propiedad *WhenSoftDeleted* identifica la fecha de eliminación temporal, que en este ejemplo es el 30 de octubre de 2014. Si este buzón eliminado temporalmente era un buzón inactivo para el que se quitó la retención, se eliminará permanentemente 30 días después del valor de la propiedad *WhenSoftDeleted* . En este caso, el buzón se elimina permanentemente después del 30 de noviembre de 2014.

