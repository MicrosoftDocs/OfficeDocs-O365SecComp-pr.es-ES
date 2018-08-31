---
title: Eliminar un buzón inactivo en Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 9/5/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: f5caf497-5e8d-4b7a-bfff-d02942f38150
description: Cuando ya no se necesita conservar el contenido de un buzón inactivo de Office 365, puede eliminar permanentemente el buzón de correo inactivo al quitar la suspensión. Después de quitar la suspensión, el buzón de correo inactivo se marca para su eliminación y se elimina permanentemente después de que se procesa.
ms.openlocfilehash: 91b73fff6ca319735289abe7ea9351b5fba931a0
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22535668"
---
# <a name="delete-an-inactive-mailbox-in-office-365"></a><span data-ttu-id="c9740-104">Eliminar un buzón inactivo en Office 365</span><span class="sxs-lookup"><span data-stu-id="c9740-104">Delete an inactive mailbox in Office 365</span></span>

<span data-ttu-id="c9740-p102">Un buzón inactivo se usa para conservar el correo electrónico de un empleado anterior después de que abandona la organización. Cuando ya no se necesita conservar el contenido de un buzón de correo inactivo, puede eliminar permanentemente el buzón de correo inactivo al quitar la suspensión. Además, es posible que se pueden incluir varias suspensiones en un buzón de correo inactivo. Por ejemplo, un buzón inactivo puede colocarse en suspensión por litigio y en una o varias suspensiones en contexto. Además, una directiva de retención de Office 365 (creado en la seguridad de Office 365 &amp; centro de cumplimiento) pueden aplicarse en el buzón de correo inactivo. Se debe quitar todas las directivas de retención de Office 365 y suspensiones de un buzón inactivo para eliminarlo. Después de quitar las suspensiones y las directivas de retención, el buzón de correo inactivo se marca para su eliminación y se elimina permanentemente después de que se procesa.</span><span class="sxs-lookup"><span data-stu-id="c9740-p102">An inactive mailbox is used to preserve a former employee's email after he or she leaves your organization. When you no longer need to preserve the contents of an inactive mailbox, you can permanently delete the inactive mailbox by removing the hold. Also, it's possible that multiple holds might be placed on an inactive mailbox. For example, an inactive mailbox might be placed on Litigation Hold and on one or more In-Place Holds. Additionally, an Office 365 retention policy (created in the Office 365 Security &amp; Compliance Center) might be applied to the inactive mailbox. You have to remove all holds and Office 365 retention policies from an inactive mailbox to delete it. After you remove the holds and retention policies, the inactive mailbox is marked for deletion and is permanently deleted after it's processed.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="c9740-p103">Hemos pospuesto la fecha límite del 1 de julio de 2017 para crear conservaciones locales con el fin de desactivar buzones, pero más adelante este año o a principios del año que viene ya no podrá crear conservaciones locales en Exchange Online. A partir de ese momento, solo podrán usarse retenciones por juicio y directivas de retención de Office 365 para crear buzones inactivos. Aun así, se seguirán admitiendo los buzones inactivos existentes que estén en conservación local y podrá seguir administrando las conservaciones locales de buzones inactivos. Esto incluye el cambio de la duración de las conservaciones locales y la eliminación de forma permanente de buzones inactivos al quitar la conservación local.</span><span class="sxs-lookup"><span data-stu-id="c9740-p103">We've postponed the July 1, 2017 deadline for creating new In-Place Holds to make a mailbox inactive. But later this year or early next year, you won't be able to create new In-Place Holds in Exchange Online. At that time, only Litigation Holds and Office 365 retention policies can be used to create an inactive mailbox. However, existing inactive mailboxes that are on In-Place Hold will still be supported, and you can continue to manage the In-Place Holds on inactive mailboxes. This includes changing the duration of an In-Place Hold and permanently deleting an inactive mailbox by removing the In-Place Hold.</span></span> 
  
<span data-ttu-id="c9740-117">Consulte la sección [Más información](delete-an-inactive-mailbox.md#moreinfo) para ver una descripción de lo que sucede una vez que se quitan las retenciones de un buzón inactivo.</span><span class="sxs-lookup"><span data-stu-id="c9740-117">See the [More information](delete-an-inactive-mailbox.md#moreinfo) section for a description of what happens after holds are removed from an inactive mailbox.</span></span> 
  
## <a name="before-you-begin"></a><span data-ttu-id="c9740-118">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="c9740-118">Before you begin</span></span>

- <span data-ttu-id="c9740-p104">Se debe usar Exchange Online PowerShell para quitar un juicio de un buzón de correo inactivo. No puede usar el centro de administración de Exchange (EAC). Para obtener instrucciones detalladas, vea [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/?linkid=396554). Puede usar Exchange Online PowerShell o el CEF para quitar una retención local de un buzón de correo inactivo.</span><span class="sxs-lookup"><span data-stu-id="c9740-p104">You have to use Exchange Online PowerShell to remove a Litigation Hold from an inactive mailbox. You can't use the Exchange admin center (EAC). For step-by-step instructions, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/?linkid=396554). You can use Exchange Online PowerShell or the EAC to remove an In-Place Hold from an inactive mailbox.</span></span> 
    
- <span data-ttu-id="c9740-p105">Puede copiar el contenido de un buzón inactivo a otro buzón antes de quitar la suspensión y eliminar un buzón de correo inactivo. Para obtener más información, vea [restaurar un buzón inactivo en Office 365](restore-an-inactive-mailbox.md).</span><span class="sxs-lookup"><span data-stu-id="c9740-p105">You can copy the contents of an inactive mailbox to another mailbox before you remove the hold and delete an inactive mailbox. For details, see [Restore an inactive mailbox in Office 365](restore-an-inactive-mailbox.md).</span></span>
    
- <span data-ttu-id="c9740-p106">Si quita la suspensión o la directiva de retención de Office 365 de un buzón inactivo y ha expirado el período de retención del buzón eliminado temporalmente para el buzón de correo, se eliminarán permanentemente el buzón de correo. Después de que se elimine, no se puede recuperar. Antes de quitar la suspensión, asegúrese de que ya no necesita el contenido del buzón de correo. Si desea volver a activar un buzón inactivo, puede recuperarlo. Para obtener información detallada, vea [recuperar un buzón inactivo en Office 365](recover-an-inactive-mailbox.md).</span><span class="sxs-lookup"><span data-stu-id="c9740-p106">If you remove the hold or Office 365 retention policy from an inactive mailbox and the soft-deleted mailbox retention period for the mailbox has expired, the mailbox will be permanently deleted. After it's deleted, it can't be recovered. Before you remove the hold, be sure that you no longer need the contents in the mailbox. If you want to re-activate an inactive mailbox, you can recover it. For details, see [Recover an inactive mailbox in Office 365](recover-an-inactive-mailbox.md).</span></span>
    
- <span data-ttu-id="c9740-130">Para obtener más información acerca de los buzones de correo inactivos, vea [buzones inactivos en Office 365](inactive-mailboxes-in-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="c9740-130">For more information about inactive mailboxes, see [Inactive mailboxes in Office 365](inactive-mailboxes-in-office-365.md).</span></span>
    
## <a name="step-1-identify-the-holds-on-an-inactive-mailbox"></a><span data-ttu-id="c9740-131">Paso 1: identificar las retenciones en un buzón inactivo</span><span class="sxs-lookup"><span data-stu-id="c9740-131">Step 1: Identify the holds on an inactive mailbox</span></span>

<span data-ttu-id="c9740-p107">Como se ha indicado anteriormente, se puede incluir una directiva de retención juicio, conservación local u Office 365 en un buzón de correo inactivo. El primer paso es identificar las suspensiones en un buzón de correo inactivo.</span><span class="sxs-lookup"><span data-stu-id="c9740-p107">As previously stated, a Litigation Hold, In-Place Hold, or Office 365 retention policy might be placed on an inactive mailbox. The first step is to identify the holds on an inactive mailbox.</span></span>
  
<span data-ttu-id="c9740-134">Ejecute el siguiente comando para mostrar la información de la retención de todos los buzones inactivos en su organización.</span><span class="sxs-lookup"><span data-stu-id="c9740-134">Run the following command to display the hold information for all inactive mailboxes in your organization.</span></span>
  
```
Get-Mailbox -InactiveMailboxOnly | FL DisplayName,Name,IsInactiveMailbox,LitigationHoldEnabled,InPlaceHolds
```

<span data-ttu-id="c9740-p108">El valor de **True** para la propiedad **LitigationHoldEnabled** indica que el buzón inactivo está en retención por juicio. Si una retención local se coloca en un buzón inactivo, el GUID de la retención se muestra como el valor de la propiedad **InPlaceHolds**. Por ejemplo, los siguientes resultados para dos buzones inactivos muestran que una retención por juicio se coloca en Ann Beebe y dos retenciones locales se colocan en Pilar Pinilla.</span><span class="sxs-lookup"><span data-stu-id="c9740-p108">The value of **True** for the **LitigationHoldEnabled** property indicates that the inactive mailbox is on Litigation Hold. If an In-Place Hold is placed on an inactive mailbox, the GUID for the hold is displayed as the value for the **InPlaceHolds** property. For example, the following results for two inactive mailboxes show that a Litigation Hold is placed on Ann Beebe and that two In-Place Holds are placed on Pilar Pinilla.</span></span> 
  
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
> <span data-ttu-id="c9740-p109">Si una gran cantidad de suspensiones en contexto se coloca en un buzón de correo inactivo, no todos los GUID de suspensión en contexto se mostrará. Puede ejecutar el siguiente comando para mostrar todos los In-Place mantenga GUID:`Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox> | Select-Object -ExpandProperty InPlaceHolds`</span><span class="sxs-lookup"><span data-stu-id="c9740-p109">If a lot of In-Place Holds are placed on an inactive mailbox, not all of the In-Place Hold GUIDs will be displayed. You can run the following command to display all the In-Place Hold GUIDs:  `Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox> | Select-Object -ExpandProperty InPlaceHolds`</span></span>
  
## <a name="step-2-remove-a-hold-from-an-inactive-mailbox"></a><span data-ttu-id="c9740-140">Paso 2: Quitar una retención de un buzón inactivo</span><span class="sxs-lookup"><span data-stu-id="c9740-140">Step 2: Remove a hold from an inactive mailbox</span></span>

<span data-ttu-id="c9740-p110">Tras identificar el tipo de retención que está colocada en el buzón inactivo (y si hay varias retenciones), el siguiente paso es quitar las retenciones del buzón. Como se mencionó anteriormente, tiene que quitar todas las retenciones para eliminar de forma permanente un buzón inactivo.</span><span class="sxs-lookup"><span data-stu-id="c9740-p110">After you identify what type of hold is placed on the inactive mailbox (and whether there are multiple holds), the next step is to remove the holds on the mailbox. As previously stated, you have to remove all holds to permanently delete an inactive mailbox.</span></span> 
  
### <a name="remove-a-litigation-hold"></a><span data-ttu-id="c9740-143">Quitar una retención por juicio</span><span class="sxs-lookup"><span data-stu-id="c9740-143">Remove a Litigation Hold</span></span>

<span data-ttu-id="c9740-p111">Como se mencionó anteriormente, tiene que usar Windows PowerShell para quitar una retención por juicio de un buzón inactivo. No puede usar el EAC. Ejecute el siguiente comando para quitar una retención por juicio.</span><span class="sxs-lookup"><span data-stu-id="c9740-p111">As previously stated, you have to use Windows PowerShell to remove a Litigation Hold from an inactive mailbox. You can't use the EAC. Run the following command to remove a Litigation Hold.</span></span>
  
```
Set-Mailbox -InactiveMailbox -Identity <identity of inactive mailbox> -LitigationHoldEnabled $false
```

> [!TIP]
> <span data-ttu-id="c9740-p112">La mejor manera de identificar un buzón inactivo es usando el valor Nombre distintivo o GUID de Exchange. El uso de uno de estos valores ayuda a impedir que se especifique accidentalmente el buzón equivocado.</span><span class="sxs-lookup"><span data-stu-id="c9740-p112">The best way to identify an inactive mailbox is by using its Distinguished Name or Exchange GUID value. Using one of these values helps prevent accidentally specifying the wrong mailbox.</span></span> 
  
### <a name="remove-in-place-holds"></a><span data-ttu-id="c9740-149">Quitar retenciones locales</span><span class="sxs-lookup"><span data-stu-id="c9740-149">Remove In-Place Holds</span></span>

 <span data-ttu-id="c9740-150">Hay dos maneras de quitar una retención local de un buzón inactivo:</span><span class="sxs-lookup"><span data-stu-id="c9740-150">There are two ways to remove an In-Place Hold from an inactive mailbox:</span></span> 
  
- <span data-ttu-id="c9740-151">**Eliminar el objeto de retención en contexto** Si el buzón de correo inactivo que desea eliminar de forma permanente es el buzón de origen único para una retención en contexto, sólo puede eliminar el objeto de retención en contexto.</span><span class="sxs-lookup"><span data-stu-id="c9740-151">**Delete the In-Place Hold object** If the inactive mailbox that you want to permanently delete is the only source mailbox for an In-Place Hold, you can just delete the In-Place Hold object.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="c9740-p113">Tiene que deshabilitar la retención antes de poder eliminar un objeto de retención local. Si intenta eliminar un objeto de retención local que tiene habilitada la retención, recibirá un mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="c9740-p113">You have to disable the hold before you can delete an In-Place Hold object. If you try to delete an In-Place Hold object that has the hold enabled, you'll receive an error message.</span></span> 
  
- <span data-ttu-id="c9740-154">**Quitar el buzón inactivo como buzón de origen de una retención local** Si quiere conservar otros buzones de origen para una retención local, puede quitar el buzón inactivo de la lista de buzones de origen y mantener el objeto de retención local.</span><span class="sxs-lookup"><span data-stu-id="c9740-154">**Remove the inactive mailbox as a source mailbox of an In-Place Hold** If you want to retain other source mailboxes for an In-Place Hold, you can remove the inactive mailbox from the list of source mailboxes and keep the In-Place Hold object.</span></span> 
    
#### <a name="use-the-eac-to-delete-an-in-place-hold"></a><span data-ttu-id="c9740-155">Usar el EAC para eliminar una retención local</span><span class="sxs-lookup"><span data-stu-id="c9740-155">Use the EAC to delete an In-Place Hold</span></span>

1. <span data-ttu-id="c9740-p114">Si conoce el nombre de la retención local que quiere eliminar, puede ir al siguiente paso. De lo contrario, ejecute el siguiente comando para obtener el nombre de la retención local que se coloca en el buzón inactivo que quiere eliminar de forma permanente. Use el GUID de retención local que obtuvo en [Paso 1: Identificar las retenciones en un buzón inactivo](delete-an-inactive-mailbox.md#step1).</span><span class="sxs-lookup"><span data-stu-id="c9740-p114">If you know the name of the In-Place Hold that you want to delete, you can go to the next step. Otherwise, run the following command to get the name of the In-Place Hold that is placed on the inactive mailbox that you want to permanently delete. Use the In-Place Hold GUID that you obtained in [Step 1: Identify the holds on an inactive mailbox](delete-an-inactive-mailbox.md#step1).</span></span>
    
```
  Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID> | FL Name
```

2. <span data-ttu-id="c9740-159">En el EAC, vaya a **administración de cumplimiento** \> **exhibición de documentos electrónicos en contexto &amp; suspensión**.</span><span class="sxs-lookup"><span data-stu-id="c9740-159">In the EAC, go to **Compliance management** \> **In-Place eDiscovery &amp; Hold**.</span></span>
    
<span data-ttu-id="c9740-160"><<<<<<< HEAD</span><span class="sxs-lookup"><span data-stu-id="c9740-160"><<<<<<< HEAD</span></span>
3. <span data-ttu-id="c9740-161">Seleccione la retención local que desea eliminar y, a continuación, haga clic en **Editar** ![icono Editar](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif).</span><span class="sxs-lookup"><span data-stu-id="c9740-161">Select the In-Place Hold you want to delete, and then click **Edit** ![Edit icon](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif).</span></span>
=======
3. <span data-ttu-id="c9740-p115">¡Seleccione la retención local que desea eliminar y, a continuación, haga clic en **Editar**! [Icono de edición](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif).</span><span class="sxs-lookup"><span data-stu-id="c9740-p115">Select the In-Place Hold you want to delete, and then click **Edit**! [Edit icon](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif).</span></span>
>>>>>>> <span data-ttu-id="c9740-164">conversión de markjjo</span><span class="sxs-lookup"><span data-stu-id="c9740-164">markjjo-conversion</span></span>
    
4. <span data-ttu-id="c9740-165">En la **exhibición de documentos electrónicos en contexto &amp; suspensión** propiedades de página, haga clic en **Conservación local**, desactive la casilla de **la retención de contenido de sitio que coinciden con la consulta de búsqueda en buzones seleccionados en** y, a continuación, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="c9740-165">On the **In-Place eDiscovery &amp; Hold** properties page, click **In-Place Hold**, uncheck the **Place content matching the search query in selected mailboxes on hold** box, and then click **Save**.</span></span>
    
5. <span data-ttu-id="c9740-166">En la **documentos electrónicos en &amp; suspensión** de página, vuelva a seleccionar la retención local y, a continuación, haga clic en **Eliminar**![icono de eliminación](media/87565fbb-5147-4f22-9ed7-1c18ce664392.png).</span><span class="sxs-lookup"><span data-stu-id="c9740-166">On the **In-Place eDiscovery &amp; Hold** page, select the In-Place Hold again, and then click **Delete**![Delete icon](media/87565fbb-5147-4f22-9ed7-1c18ce664392.png).</span></span>
    
6. <span data-ttu-id="c9740-167">En la advertencia, haga clic en **Sí** para eliminar la retención local.</span><span class="sxs-lookup"><span data-stu-id="c9740-167">On the warning, click **Yes** to delete the In-Place Hold.</span></span> 
    
#### <a name="use-exchange-online-powershell-to-delete-an-in-place-hold"></a><span data-ttu-id="c9740-168">Use Exchange Online PowerShell para eliminar una retención local</span><span class="sxs-lookup"><span data-stu-id="c9740-168">Use Exchange Online PowerShell to delete an In-Place Hold</span></span>

1. <span data-ttu-id="c9740-p116">Cree una variable que contenga las propiedades de la retención local que quiera eliminar. Use el GUID de retención local que obtuvo en [Paso 1: Identificar las retenciones en un buzón inactivo](delete-an-inactive-mailbox.md#step1).</span><span class="sxs-lookup"><span data-stu-id="c9740-p116">Create a variable that contains the properties of the In-Place Hold that you want to delete. Use the In-Place Hold GUID that you obtained in [Step 1: Identify the holds on an inactive mailbox](delete-an-inactive-mailbox.md#step1).</span></span>
    
```
  $InPlaceHold = Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID>
```

2. <span data-ttu-id="c9740-171">Deshabilite la retención en la retención local.</span><span class="sxs-lookup"><span data-stu-id="c9740-171">Disable the hold on the In-Place Hold.</span></span>
    
```
  Set-MailboxSearch $InPlaceHold.Name -InPlaceHoldEnabled $false
```

3. <span data-ttu-id="c9740-172">Elimine la retención local.</span><span class="sxs-lookup"><span data-stu-id="c9740-172">Delete the In-Place Hold.</span></span>
    
```
  Remove-MailboxSearch $InPlaceHold.Name
```

#### <a name="use-the-eac-to-remove-an-inactive-mailbox-from-an-in-place-hold"></a><span data-ttu-id="c9740-173">Usar el EAC para quitar un buzón inactivo de una retención local.</span><span class="sxs-lookup"><span data-stu-id="c9740-173">Use the EAC to remove an inactive mailbox from an In-Place Hold</span></span>

1. <span data-ttu-id="c9740-p117">Si conoce el nombre de la retención local que está colocada en el buzón inactivo, puede ir al siguiente paso. De lo contrario, ejecute el siguiente comando para obtener el nombre de la retención local colocada en el buzón. Use el GUID de retención local que obtuvo en [Paso 1: Identificar las retenciones en un buzón inactivo](delete-an-inactive-mailbox.md#step1).</span><span class="sxs-lookup"><span data-stu-id="c9740-p117">If you know the name of the In-Place Hold that's placed on the inactive mailbox, you can go to the next step. Otherwise, run the following command to get the name of the In-Place Hold placed on the mailbox. Use the In-Place Hold GUID that you obtained in [Step 1: Identify the holds on an inactive mailbox](delete-an-inactive-mailbox.md#step1).</span></span>
    
```
  Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID> | FL Name
```

2. <span data-ttu-id="c9740-177">En el EAC, vaya a **administración de cumplimiento** \> **exhibición de documentos electrónicos en contexto &amp; suspensión**.</span><span class="sxs-lookup"><span data-stu-id="c9740-177">In the EAC, go to **Compliance management** \> **In-Place eDiscovery &amp; Hold**.</span></span>
    
3. <span data-ttu-id="c9740-178">Seleccione la retención local que se coloca en el buzón de correo inactivo y, a continuación, haga clic en **Editar** ![icono Editar](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif).</span><span class="sxs-lookup"><span data-stu-id="c9740-178">Select the In-Place Hold that is placed on the inactive mailbox, and then click **Edit** ![Edit icon](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif).</span></span>
    
4. <span data-ttu-id="c9740-179">En la **exhibición de documentos electrónicos en contexto &amp; suspensión** propiedades de página, haga clic en **orígenes**.</span><span class="sxs-lookup"><span data-stu-id="c9740-179">On the **In-Place eDiscovery &amp; Hold** properties page, click **Sources**.</span></span>
    
5. <span data-ttu-id="c9740-180">En la lista de buzones de origen, haga clic en el nombre del buzón inactivo que quiere quitar y después haga clic en **Quitar**![Icono de quitar](media/adf01106-cc79-475c-8673-065371c1897b.gif).</span><span class="sxs-lookup"><span data-stu-id="c9740-180">In the list of source mailboxes, click the name of the inactive mailbox that you want to remove, and then click **Remove**![Remove icon](media/adf01106-cc79-475c-8673-065371c1897b.gif).</span></span>
    
6. <span data-ttu-id="c9740-p118">Haga clic en **Guardar** para guardar el cambio. Se muestra un mensaje que indica que la operación se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="c9740-p118">Click **Save** to save the change. A message is displayed saying the operation was successfully completed.</span></span> 
    
7. <span data-ttu-id="c9740-183">Repita los pasos 1 a 6 para quitar otras retenciones locales colocadas en el buzón inactivo.</span><span class="sxs-lookup"><span data-stu-id="c9740-183">Repeat steps 1 through 6 to remove other In-Place Holds placed on the inactive mailbox.</span></span>
    
#### <a name="use-exchange-online-powershell-to-remove-an-inactive-mailbox-from-an-in-place-hold"></a><span data-ttu-id="c9740-184">Use Exchange Online PowerShell para quitar un buzón inactivo de una retención local</span><span class="sxs-lookup"><span data-stu-id="c9740-184">Use Exchange Online PowerShell to remove an inactive mailbox from an In-Place Hold</span></span>

<span data-ttu-id="c9740-p119">Si la retención local contiene un gran número de buzones de origen, es posible que el buzón de correo inactivo no aparecerá en la página **orígenes** en el CEF. Hasta 3.000 buzones de correo se muestran en la página **orígenes** cuando se edita una retención local. Si un buzón inactivo no aparece en la página **orígenes** , puede usar Exchange Online PowerShell para quitarlo de la retención en contexto.</span><span class="sxs-lookup"><span data-stu-id="c9740-p119">If the In-Place Hold contains a large number of source mailboxes, it's possible the inactive mailbox won't be listed on the **Sources** page in the EAC. Up to 3,000 mailboxes are displayed on the **Sources** page when you edit an In-Place Hold. If an inactive mailbox isn't listed on the **Sources** page, you can use Exchange Online PowerShell to remove it from the In-Place Hold.</span></span> 
  
1. <span data-ttu-id="c9740-p120">Cree una variable que contenga las propiedades de la retención local colocada en el buzón inactivo. Use el GUID de retención local que obtuvo en [Paso 1: Identificar las retenciones en un buzón inactivo](delete-an-inactive-mailbox.md#step1).</span><span class="sxs-lookup"><span data-stu-id="c9740-p120">Create a variable that contains the properties of the In-Place Hold placed on the inactive mailbox. Use the In-Place Hold GUID that you obtained in [Step 1: Identify the holds on an inactive mailbox](delete-an-inactive-mailbox.md#step1).</span></span>
    
```
  $InPlaceHold = Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID>
```

2. <span data-ttu-id="c9740-190">Compruebe que el buzón inactivo aparezca como un buzón de origen para la retención local.</span><span class="sxs-lookup"><span data-stu-id="c9740-190">Verify that the inactive mailbox is listed as a source mailbox for the In-Place Hold.</span></span> 
    
```
  $InPlaceHold.Sources
```

   <span data-ttu-id="c9740-p121">**Nota:** La propiedad de *orígenes* de la retención local identifica los buzones de origen por sus propiedades *LegacyExchangeDN* . Debido a que esta propiedad identifica los buzones de correo inactivos, mediante la propiedad *orígenes* desde la retención local ayuda a evitar eliminar el buzón incorrecto. Esto también ayuda a evitar problemas si dos buzones tienen el mismo alias o la dirección de SMTP.</span><span class="sxs-lookup"><span data-stu-id="c9740-p121">**Note:** The *Sources* property of the In-Place Hold identifies the source mailboxes by their *LegacyExchangeDN* properties. Because this property uniquely identifies inactive mailboxes, using the *Sources* property from the In-Place Hold helps prevent removing the wrong mailbox. This also helps to avoid issues if two mailboxes have the same alias or SMTP address.</span></span> 
   
3. <span data-ttu-id="c9740-p122">Quite el buzón inactivo de la lista de buzones de origen en la variable. Asegúrese de usar la propiedad **LegacyExchangeDN** del buzón inactivo devuelto por el comando en el paso anterior.</span><span class="sxs-lookup"><span data-stu-id="c9740-p122">Remove the inactive mailbox from the list of source mailboxes in the variable. Be sure to use the **LegacyExchangeDN** of the inactive mailbox that's returned by the command in the previous step.</span></span> 
    
```
  $InPlaceHold.Sources.Remove("<LegacyExchangeDN of the inactive mailbox>")
```

    For example, the following command removes the inactive mailbox for Pilar Pinilla.
    
  ```
  $InPlaceHold.Sources.Remove("/o=contoso/ou=Exchange Administrative Group (FYDIBOHF23SPDLT)/cn=Recipients/cn=9c8dfff651ec4908950f5df60cbbda06-pilarp")
  ```

4. <span data-ttu-id="c9740-196">Compruebe que el buzón inactivo se quita de la lista de buzones de origen en la variable.</span><span class="sxs-lookup"><span data-stu-id="c9740-196">Verify that the inactive mailbox is removed from the list of source mailboxes in the variable.</span></span>
    
```
  $InPlaceHold.Sources
```

5. <span data-ttu-id="c9740-197">Modifique la retención local con la lista actualizada de buzones de origen, que no incluye el buzón inactivo.</span><span class="sxs-lookup"><span data-stu-id="c9740-197">Modify the In-Place Hold with the updated list of source mailboxes, which doesn't include the inactive mailbox.</span></span>
    
```
  Set-MailboxSearch $InPlaceHold.Name -SourceMailboxes $InPlaceHold.Sources
```

6. <span data-ttu-id="c9740-198">Compruebe que el buzón inactivo se quita de la lista de buzones de origen para la retención local.</span><span class="sxs-lookup"><span data-stu-id="c9740-198">Verify that the inactive mailbox is removed from the list of source mailboxes for the In-Place Hold.</span></span>
    
```
  Get-MailboxSearch $InPlaceHold.Name | FL Sources
```

## <a name="more-information"></a><span data-ttu-id="c9740-199">Más información</span><span class="sxs-lookup"><span data-stu-id="c9740-199">More information</span></span>

- <span data-ttu-id="c9740-p123">**Un buzón inactivo es un tipo de buzón eliminado temporalmente.** En Exchange Online, un buzón eliminado temporalmente es un buzón que se ha eliminado, pero se pueden recuperar en un período de retención específico. El período de retención del buzón eliminado temporalmente en Exchange Online es de 30 días. Esto significa que el buzón se puede recuperar en un plazo de 30 días después de eliminarse temporalmente. Después de 30 días, un buzón eliminado temporalmente se marca para su eliminación permanente y no puede recuperarse.</span><span class="sxs-lookup"><span data-stu-id="c9740-p123">**An inactive mailbox is a type of soft-deleted mailbox.** In Exchange Online, a soft-deleted mailbox is a mailbox that's been deleted but can be recovered within a specific retention period. The soft-deleted mailbox retention period in Exchange Online is 30 days. This means that the mailbox can be recovered within 30 days of being soft-deleted. After 30 days, a soft-deleted mailbox is marked for permanent deletion and can't be recovered.</span></span> 
    
- <span data-ttu-id="c9740-p124">**¿Qué ocurre después de quitar la retención en un buzón inactivo?** El buzón de correo se considera como otros buzones eliminados temporalmente y se marca para eliminación permanente una vez que expire el período de retención de 30 días del buzón eliminado temporalmente. Este período de retención empieza en la fecha en que el buzón se volvió inactivo por primera vez. Esta fecha se conoce como la fecha de eliminación temporal, que es la fecha cuando la cuenta de usuario de Office 365 correspondiente se eliminó o cuando el buzón de Exchange Online se eliminó con el cmdlet **Remove-Mailbox**. La fecha de eliminación temporal no es la fecha en que se quita la retención.</span><span class="sxs-lookup"><span data-stu-id="c9740-p124">**What happens after you remove the hold on an inactive mailbox?** The mailbox is treated like other soft-deleted mailboxes and is marked for permanent deletion after the 30-day soft-deleted mailbox retention period expires. This retention period starts on the date when the mailbox was first made inactive. This date is known as the soft-deleted date, which is the date the corresponding Office 365 user account was deleted or when the Exchange Online mailbox was deleted with the **Remove-Mailbox** cmdlet. The soft-deleted date isn't the date on which you remove the hold.</span></span> 
    
- <span data-ttu-id="c9740-p125">**¿Un buzón inactivo se elimina de forma permanente inmediatamente después de quitar la retención?** Si la fecha de eliminación temporal para un buzón inactivo supera 30 días, el buzón no se eliminará permanentemente en cuanto se quite la retención. El buzón se marcará para su eliminación permanente y se eliminará la próxima vez que se procese.</span><span class="sxs-lookup"><span data-stu-id="c9740-p125">**Is an inactive mailbox permanently deleted immediately after the hold is removed?** If the soft-deleted date for an inactive mailbox is older than 30 days, the mailbox won't be permanently deleted as soon as you remove the hold. The mailbox will be marked for permanent deletion and is deleted the next time it's processed.</span></span> 
    
- <span data-ttu-id="c9740-p126">**¿Cómo afecta el período de retención del buzón eliminado temporalmente los buzones de correo inactivos?** Si la fecha eliminado temporalmente para un buzón inactivo es más de 30 días antes de la fecha en que se ha quitado la suspensión, el buzón se marca para su eliminación permanente. Pero si un buzón inactivo tiene una fecha eliminado temporalmente dentro de los últimos 30 días y quitar la suspensión, puede recuperar el buzón de correo hasta que expire el período de retención del buzón eliminado temporalmente. Para obtener información detallada, vea [eliminar o restaurar los buzones de usuario en Exchange Online](https://go.microsoft.com/fwlink/?linkid=856835). Después de que expire el período de retención del buzón eliminado temporalmente, ha siga los procedimientos para recuperar un buzón de correo inactivo. Para obtener información detallada, vea [recuperar un buzón inactivo en Office 365](recover-an-inactive-mailbox.md).</span><span class="sxs-lookup"><span data-stu-id="c9740-p126">**How does the soft-deleted mailbox retention period affect inactive mailboxes?** If the soft-deleted date for an inactive mailbox is more than 30 days before the date the hold was removed, the mailbox is marked for permanent deletion. But if an inactive mailbox has a soft-deleted date within the last 30 days and you remove the hold, you can recover the mailbox up until the soft-deleted mailbox retention period expires. For details, see [Delete or restore user mailboxes in Exchange Online](https://go.microsoft.com/fwlink/?linkid=856835). After the soft-deleted mailbox retention period expires, you have follow the procedures for recovering an inactive mailbox. For details, see [Recover an inactive mailbox in Office 365](recover-an-inactive-mailbox.md).</span></span>
    
- <span data-ttu-id="c9740-p127">**¿Cómo se muestra información acerca de un buzón inactivo después de que se ha quitado la suspensión?** Una vez que se ha quitado una suspensión y el buzón de correo inactivo se ha vuelto a un buzón eliminado temporalmente, no se devuelven mediante el parámetro *InactiveMailboxOnly* con el cmdlet **Get-Mailbox** . Aunque se puede mostrar información sobre el buzón de correo mediante el comando **Get-Mailbox-SoftDeletedMailbox** . Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="c9740-p127">**How do you display information about an inactive mailbox after the hold is removed?** After a hold is removed and the inactive mailbox is reverted back to a soft-deleted mailbox, it won't be returned by using the  *InactiveMailboxOnly*  parameter with the **Get-Mailbox** cmdlet. But you can display information about the mailbox by using the **Get-Mailbox -SoftDeletedMailbox** command. For example:</span></span> 
    
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
  
<span data-ttu-id="c9740-p128">En el ejemplo anterior, la propiedad *WhenSoftDeleted* identifica la fecha eliminado temporalmente, que en este ejemplo es el 30 de octubre de 2014. Si este buzón eliminado temporalmente anteriormente era un buzón inactivo para que se ha quitado la suspensión, será eliminados permanentemente 30 días después del valor de la propiedad *WhenSoftDeleted* . En este caso, el buzón se elimina permanentemente después de 30 de noviembre de 2014.</span><span class="sxs-lookup"><span data-stu-id="c9740-p128">In the above example, the *WhenSoftDeleted* property identifies the soft-deleted date, which in this example is October 30, 2014. If this soft-deleted mailbox was previously an inactive mailbox for which the hold was removed, it will be permanently deleted 30 days after the value of the *WhenSoftDeleted* property. In this case, the mailbox is permanently deleted after November 30, 2014.</span></span>

