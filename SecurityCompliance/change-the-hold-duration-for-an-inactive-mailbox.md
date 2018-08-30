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
search.appverid:
- MOE150
- MET150
ms.assetid: bdee24ed-b8cf-4dd0-92ae-b86ec4661e6b
description: Después de un buzón de Office 365 se realiza como inactivo, puede cambiar la duración de la suspensión o la directiva de retención de Office 365 asignada para el buzón de correo inactivo. La duración de retención define cuánto tiempo los elementos en la carpeta se conservan de elementos recuperables.
ms.openlocfilehash: 22bd9f9294b625a38d243f6235097d1aee437121
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22536232"
---
# <a name="change-the-hold-duration-for-an-inactive-mailbox-in-office-365"></a><span data-ttu-id="f736c-104">Cambiar la duración de retención para un buzón inactivo en Office 365</span><span class="sxs-lookup"><span data-stu-id="f736c-104">Change the hold duration for an inactive mailbox in Office 365</span></span>

<span data-ttu-id="f736c-p102">Un buzón inactivo se utiliza para retener el correo electrónico de un empleado anterior después de que abandona la organización. Un buzón de correo, se convierte en inactivo cuando un juicio, una retención en contexto, una directiva de retención de Office 365, o una suspensión a la que está asociado con un caso de exhibición de documentos electrónicos se coloca en el buzón de correo y se elimina la cuenta de usuario de Office 365 correspondiente. El contenido de un buzón inactivo se conserva para la duración de la suspensión a la que se realizó en el buzón de correo antes de que se ha realizado como inactiva. La duración de retención define cuánto tiempo los elementos en la carpeta se conservan de elementos recuperables. Cuando expire la duración de retención de un elemento en la carpeta elementos recuperables, el elemento se elimina de manera permanente (Purgar) desde el buzón de correo inactivo. Después de un buzón de correo se realiza como inactiva, puede cambiar la duración de la suspensión o la directiva de retención de Office 365 asignada para el buzón de correo inactivo.</span><span class="sxs-lookup"><span data-stu-id="f736c-p102">An inactive mailbox is used to retain a former employee's email after he or she leaves your organization. A mailbox becomes inactive when a Litigation Hold, an In-Place Hold, an Office 365 retention policy, or a hold that's associated with an eDiscovery case is placed on the mailbox, and the corresponding Office 365 user account is deleted. The contents of an inactive mailbox are retained for the duration of the hold that was placed on the mailbox before it was made inactive. The hold duration defines how long items in the Recoverable Items folder are held. When the hold duration expires for an item in the Recoverable Items folder, the item is permanently deleted (purged) from the inactive mailbox. After a mailbox is made inactive, you can change the duration of the hold or Office 365 retention policy assigned to the inactive mailbox.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="f736c-p103">Hemos pospuesto la fecha límite del 1 de julio de 2017 para crear conservaciones locales con el fin de desactivar buzones, pero más adelante este año o a principios del año que viene ya no podrá crear conservaciones locales en Exchange Online. A partir de ese momento, solo podrán usarse retenciones por juicio y directivas de retención de Office 365 para crear buzones inactivos. Aun así, se seguirán admitiendo los buzones inactivos existentes que estén en conservación local y podrá seguir administrando las conservaciones locales de buzones inactivos. Esto incluye el cambio de la duración de las conservaciones locales y la eliminación de forma permanente de buzones inactivos al quitar la conservación local.</span><span class="sxs-lookup"><span data-stu-id="f736c-p103">We've postponed the July 1, 2017 deadline for creating new In-Place Holds to make a mailbox inactive. But later this year or early next year, you won't be able to create new In-Place Holds in Exchange Online. At that time, only Litigation Holds and Office 365 retention policies can be used to create an inactive mailbox. However, existing inactive mailboxes that are on In-Place Hold will still be supported, and you can continue to manage the In-Place Holds on inactive mailboxes. This includes changing the duration of an In-Place Hold and permanently deleting an inactive mailbox by removing the In-Place Hold.</span></span> 
  
## <a name="before-you-begin"></a><span data-ttu-id="f736c-116">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="f736c-116">Before you begin</span></span>

- <span data-ttu-id="f736c-p104">Se debe usar Exchange Online PowerShell para cambiar la duración de retención para un juicio en un buzón de correo inactivo. No puede usar el centro de administración de Exchange (EAC). Pero se puede usar Exchange Online PowerShell o el CEF para cambiar la duración de retención para una retención local. Puede usar la seguridad de Office 365 &amp; centro de cumplimiento o la seguridad &amp; PowerShell de centro de cumplimiento para cambiar la duración de retención para una directiva de retención de Office 365.</span><span class="sxs-lookup"><span data-stu-id="f736c-p104">You have to use Exchange Online PowerShell to change the hold duration for a Litigation Hold on an inactive mailbox. You can't use the Exchange admin center (EAC). But you can use Exchange Online PowerShell or the EAC to change the hold duration for an In-Place Hold. You can use the Office 365 Security &amp; Compliance Center or the Security &amp; Compliance Center PowerShell to change the hold duration for an Office 365 retention policy.</span></span>
    
- <span data-ttu-id="f736c-121">Para conectarse a Exchange Online PowerShell o seguridad &amp; PowerShell de centro de cumplimiento, vea uno de los siguientes temas:</span><span class="sxs-lookup"><span data-stu-id="f736c-121">To connect to Exchange Online PowerShell or Security &amp; Compliance Center PowerShell, see one of the following topics:</span></span>
    
  - [<span data-ttu-id="f736c-122">Conectarse a Exchange Online mediante PowerShell remoto</span><span class="sxs-lookup"><span data-stu-id="f736c-122">Connect to Exchange Online PowerShell</span></span>](https://go.microsoft.com/fwlink/p/?linkid=396554)
    
  - [<span data-ttu-id="f736c-123">Conectarse a Office 365 seguridad &amp; PowerShell de centro de cumplimiento</span><span class="sxs-lookup"><span data-stu-id="f736c-123">Connect to Office 365 Security &amp; Compliance Center PowerShell</span></span>](https://go.microsoft.com/fwlink/?linkid=799771)
    
- <span data-ttu-id="f736c-p105">Tenga en cuenta que contiene asociado con los casos de exhibición de documentos electrónicos son suspensiones infinitas, lo que significa que no hay ninguna duración de retención que se puede cambiar. Se conservan los elementos indefinidamente o hasta que se elimina la suspensión y se elimina el buzón de correo inactivo.</span><span class="sxs-lookup"><span data-stu-id="f736c-p105">Note that holds associated with eDiscovery cases are infinite holds, which means there is no hold duration that can be changed. Items are held forever or until the hold is removed and the inactive mailbox is deleted.</span></span>
    
- <span data-ttu-id="f736c-126">Para obtener más información acerca de los buzones de correo inactivos, vea [buzones inactivos en Office 365](inactive-mailboxes-in-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="f736c-126">For more information about inactive mailboxes, see [Inactive mailboxes in Office 365](inactive-mailboxes-in-office-365.md).</span></span>
    
## <a name="step-1-identify-the-holds-on-an-inactive-mailbox"></a><span data-ttu-id="f736c-127">Paso 1: identificar las retenciones en un buzón inactivo</span><span class="sxs-lookup"><span data-stu-id="f736c-127">Step 1: Identify the holds on an inactive mailbox</span></span>

<span data-ttu-id="f736c-128">Debido a que los distintos tipos de suspensiones o una o varias directivas de retención de Office 365 es posible que se coloca en un buzón de correo inactivo, es el primer paso identificar las suspensiones en un buzón de correo inactivo.</span><span class="sxs-lookup"><span data-stu-id="f736c-128">Because different types of holds or one or more Office 365 retention policies might be placed on an inactive mailbox, the first step is to identify the holds on an inactive mailbox.</span></span>
  
<span data-ttu-id="f736c-129">Ejecute el siguiente comando en Exchange Online PowerShell para mostrar la información de espera para todos los buzones inactivos en su organización.</span><span class="sxs-lookup"><span data-stu-id="f736c-129">Run the following command in Exchange Online PowerShell to display the hold information for all inactive mailboxes in your organization.</span></span>
  
```
Get-Mailbox -InactiveMailboxOnly | FL DisplayName,Name,IsInactiveMailbox,LitigationHoldEnabled,LitigationHoldDuration,InPlaceHolds
```
   
<span data-ttu-id="f736c-p106">El valor **True** para la propiedad **LitigationHoldEnabled** indica que el buzón de correo inactivo está en suspensión por litigio. Si una retención en contexto, mantenga presionada la exhibición de documentos electrónicos o directiva de retención de Office 365 se coloca en un buzón de correo inactivo, un GUID de la directiva de retención o suspensión se muestra como el valor de la propiedad **InPlaceHolds** . Por ejemplo, el siguiente muestra los resultados para buzones inactivos 5.</span><span class="sxs-lookup"><span data-stu-id="f736c-p106">The value of **True** for the **LitigationHoldEnabled** property indicates that the inactive mailbox is on Litigation Hold. If an In-Place Hold, eDiscovery hold, or Office 365 retention policy is placed on an inactive mailbox, a GUID for the hold or retention policy is displayed as the value for the **InPlaceHolds** property. For example, the following shows results for 5 inactive mailboxes.</span></span> 
  
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
   
<span data-ttu-id="f736c-133">En la siguiente tabla identifica los cinco tipos de espera diferentes que se usaron para definir cada buzón de correo como inactiva.</span><span class="sxs-lookup"><span data-stu-id="f736c-133">The following table identifies the five different hold types that were used to make each mailbox inactive.</span></span>
  
|<span data-ttu-id="f736c-134">**Buzón de correo inactivo**</span><span class="sxs-lookup"><span data-stu-id="f736c-134">**Inactive mailbox**</span></span>|<span data-ttu-id="f736c-135">**Tipo de suspensión**</span><span class="sxs-lookup"><span data-stu-id="f736c-135">**Hold type**</span></span>|<span data-ttu-id="f736c-136">**Cómo identificar la suspensión en el buzón de correo inactivo**</span><span class="sxs-lookup"><span data-stu-id="f736c-136">**How to identify the hold on the inactive mailbox**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="f736c-137">Ana Díaz</span><span class="sxs-lookup"><span data-stu-id="f736c-137">Ann Beebe</span></span>  <br/> |<span data-ttu-id="f736c-138">Retención por juicio</span><span class="sxs-lookup"><span data-stu-id="f736c-138">Litigation Hold</span></span>  <br/> |<span data-ttu-id="f736c-139">La propiedad *LitigationHoldEnabled* está establecida en `True`.</span><span class="sxs-lookup"><span data-stu-id="f736c-139">The  *LitigationHoldEnabled*  property is set to  `True`.</span></span>  <br/> |
|<span data-ttu-id="f736c-140">Pilar Pinilla</span><span class="sxs-lookup"><span data-stu-id="f736c-140">Pilar Pinilla</span></span>  <br/> |<span data-ttu-id="f736c-141">Retención en contexto</span><span class="sxs-lookup"><span data-stu-id="f736c-141">In-Place Hold</span></span>  <br/> |<span data-ttu-id="f736c-p107">La propiedad *InPlaceHolds* contiene el GUID de la retención local que se coloca en el buzón de correo inactivo. Puede saber que esto es una retención local debido a que el identificador no se inicia con un prefijo.</span><span class="sxs-lookup"><span data-stu-id="f736c-p107">The  *InPlaceHolds*  property contains the GUID of the In-Place Hold that's placed on the inactive mailbox. You can tell this is an In-Place Hold because the ID doesn't start with a prefix.  </span></span><br/> <span data-ttu-id="f736c-144">Puede usar la ' Get-MailboxSearch - InPlaceHoldIdentity<hold GUID></span><span class="sxs-lookup"><span data-stu-id="f736c-144">You can use the  \`Get-MailboxSearch -InPlaceHoldIdentity <hold GUID></span></span> | <span data-ttu-id="f736c-145">FL' command en Exchange Online PowerShell para obtener información acerca de la retención local en el buzón de correo inactivo.</span><span class="sxs-lookup"><span data-stu-id="f736c-145">FL\` command in Exchange Online PowerShell to get information about the In-Place Hold on the inactive mailbox.</span></span>  <br/> |
|<span data-ttu-id="f736c-146">Mario Necaise</span><span class="sxs-lookup"><span data-stu-id="f736c-146">Mario Necaise</span></span>  <br/> |<span data-ttu-id="f736c-147">Directiva de retención de Office 365 de toda la organización en la seguridad &amp; centro de cumplimiento</span><span class="sxs-lookup"><span data-stu-id="f736c-147">Organization-wide Office 365 retention policy in the Security &amp; Compliance Center</span></span>  <br/> |<span data-ttu-id="f736c-p108">La propiedad *InPlaceHolds* está vacía. Esto indica que uno o varios (Exchange toda la) o de toda la organización Office 365 directiva de retención se aplica para el buzón de correo inactivo. En este caso, puede ejecutar el ' Get-OrganizationConfig</span><span class="sxs-lookup"><span data-stu-id="f736c-p108">The  *InPlaceHolds*  property is empty. This indicates that one or more organization-wide or (Exchange-wide) Office 365 retention policy is applied to the inactive mailbox. In this case, you can run the  \`Get-OrganizationConfig</span></span> | <span data-ttu-id="f736c-151">Select-Object - ExpandProperty InPlaceHolds` command in Exchange Online PowerShell to get a list of the GUIDs for organization-wide Office 365 retention policies. The GUID for organization-wide retention policies that are applied to Exchange mailboxes start with the  `los buzones` prefix; for example  `mbxa3056bb15562480fadb46ce523ff7b02`.  <br/> <br/>To identity the Office 365 retention policy that's applied to the inactive mailbox, run the following command in Security &amp; Compliance Center PowerShell.  <br/><br/> `Get-RetentionCompliancePolicy<retention policy GUID without prefix></span><span class="sxs-lookup"><span data-stu-id="f736c-151">Select-Object -ExpandProperty InPlaceHolds` command in Exchange Online PowerShell to get a list of the GUIDs for organization-wide Office 365 retention policies. The GUID for organization-wide retention policies that are applied to Exchange mailboxes start with the  `mbx` prefix; for example  `mbxa3056bb15562480fadb46ce523ff7b02`.  <br/> <br/>To identity the Office 365 retention policy that's applied to the inactive mailbox, run the following command in Security &amp; Compliance Center PowerShell.  <br/><br/> `Get-RetentionCompliancePolicy <retention policy GUID without prefix></span></span> | <span data-ttu-id="f736c-152">Nombre de FL'</span><span class="sxs-lookup"><span data-stu-id="f736c-152">FL Name\`</span></span><br/><br/>
|<span data-ttu-id="f736c-153">Ana Olson</span><span class="sxs-lookup"><span data-stu-id="f736c-153">Carol Olson</span></span>  <br/> |<span data-ttu-id="f736c-154">Directiva de retención de Office 365 en la seguridad &amp; centro de cumplimiento que se aplican a buzones específicos</span><span class="sxs-lookup"><span data-stu-id="f736c-154">Office 365 retention policy in the Security &amp; Compliance Center applied to specific mailboxes</span></span>  <br/> |<span data-ttu-id="f736c-p109">La propiedad *InPlaceHolds* contiene el GUID de la directiva de retención de Office 365 que se aplica a los buzones de correo inactivo. Puede indicar que se trata de una directiva de retención que se aplica a buzones específicos debido a que el GUID comienza por la `mbx` prefijo. Tenga en cuenta que si el GUID de la directiva de retención aplicada para el buzón de correo inactivo iniciado con la `skp` prefijo, que podría indicar que la directiva de retención se aplica a Skype para conversaciones de negocios.</span><span class="sxs-lookup"><span data-stu-id="f736c-p109">The  *InPlaceHolds*  property contains the GUID of the Office 365 retention policy that's applied to the inactive mailbox. You can tell this is a retention policy that applied to specific mailboxes because the GUID starts with the  `mbx` prefix. Note that if GUID of the retention policy applied to the inactive mailbox started with the  `skp` prefix, that would indicate that the retention policy is applied to Skype for Business conversations.  </span></span><br/><br/> <span data-ttu-id="f736c-158">En directiva de retención de Office 365 de identidad que se aplica a los buzones de correo inactivo, ejecute el siguiente comando en seguridad &amp; PowerShell de centro de cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="f736c-158">To identity the Office 365 retention policy that's applied to the inactive mailbox, run the following command in Security &amp; Compliance Center PowerShell.</span></span><br/><br/> <span data-ttu-id="f736c-159">' Get-RetentionCompliancePolicy<retention policy GUID without prefix></span><span class="sxs-lookup"><span data-stu-id="f736c-159">\`Get-RetentionCompliancePolicy <retention policy GUID without prefix></span></span> | <span data-ttu-id="f736c-160">Nombre de FL` <br/><br/>Be sure to remove the  `los buzones` or  `skp' prefijo al ejecutar este comando.</span><span class="sxs-lookup"><span data-stu-id="f736c-160">FL Name` <br/><br/>Be sure to remove the  `mbx` or  `skp\` prefix when you run this command.</span></span>  <br/> |
|<span data-ttu-id="f736c-161">Abraham McMahon</span><span class="sxs-lookup"><span data-stu-id="f736c-161">Abraham McMahon</span></span>  <br/> |<span data-ttu-id="f736c-162">conservación de caso de exhibición de documentos electrónicos en la seguridad &amp; centro de cumplimiento</span><span class="sxs-lookup"><span data-stu-id="f736c-162">eDiscovery case hold in the Security &amp; Compliance Center</span></span>  <br/> |<span data-ttu-id="f736c-p110">La propiedad *InPlaceHolds* contiene el GUID de la suspensión de casos de exhibición de documentos electrónicos que se coloca en el buzón de correo inactivo. Puede saber esto es una suspensión de casos de exhibición de documentos electrónicos porque el GUID comienza por la `UniH` prefijo.</span><span class="sxs-lookup"><span data-stu-id="f736c-p110">The  *InPlaceHolds*  property contains the GUID of the eDiscovery case hold that's placed on the inactive mailbox. You can tell this is an eDiscovery case hold because the GUID starts with the  `UniH` prefix.  </span></span><br/> <span data-ttu-id="f736c-p111">Puede usar el `Get-CaseHoldPolicy` cmdlet en seguridad &amp; PowerShell de centro de cumplimiento para obtener información sobre el caso de exhibición de documentos electrónicos que está asociada la suspensión en el buzón de correo inactivo. Por ejemplo, puede ejecutar el comando ' Get-CaseHoldPolicy<hold GUID without prefix></span><span class="sxs-lookup"><span data-stu-id="f736c-p111">You can use the  `Get-CaseHoldPolicy` cmdlet in Security &amp; Compliance Center PowerShell to get information about the eDiscovery case that the hold on the inactive mailbox is associated with. For example, you can run the command  \`Get-CaseHoldPolicy <hold GUID without prefix></span></span> | <span data-ttu-id="f736c-167">Nombre de FL` to display the name of the case hold that's on the inactive mailbox. Be sure to remove the  `UniH` prefix when you run this command.  <br/><br/> To identity the eDiscovery case that the hold on the inactive mailbox is associated with, run the following commands.  <br/><br/> `$CaseHold = Get-CaseHoldPolicy <hold GUID without prefix> `<br/><br/> `$CaseHold.CaseId Get-ComplianceCase</span><span class="sxs-lookup"><span data-stu-id="f736c-167">FL Name` to display the name of the case hold that's on the inactive mailbox. Be sure to remove the  `UniH` prefix when you run this command.  <br/><br/> To identity the eDiscovery case that the hold on the inactive mailbox is associated with, run the following commands.  <br/><br/> `$CaseHold = Get-CaseHoldPolicy <hold GUID without prefix>`<br/><br/> `Get-ComplianceCase $CaseHold.CaseId</span></span> | <span data-ttu-id="f736c-168">Nombre de FL'</span><span class="sxs-lookup"><span data-stu-id="f736c-168">FL Name\`</span></span><br/><br/><br/> <span data-ttu-id="f736c-p112">**Nota:** No se recomienda el uso de exhibición de documentos electrónicos contiene de buzones inactivos. Eso es porque los casos de exhibición de documentos electrónicos están diseñados para casos específicos, el límite de tiempo relacionado con un problema legal. En algún momento, probablemente finalizará un caso legal y las suspensiones asociadas con el caso se quitará y será el caso de exhibición de documentos electrónicos cerrado (o eliminar). De hecho, si una suspensión que se coloca en un buzón inactivo está asociada a un caso de exhibición de documentos electrónicos y se libera la suspensión o el caso de exhibición de documentos electrónicos se cierra o se elimina, el buzón de correo inactivo se eliminarán permanentemente.</span><span class="sxs-lookup"><span data-stu-id="f736c-p112">**Note:** We don't recommend using eDiscovery holds for inactive mailboxes. That's because eDiscovery cases are intended for specific, time-bound cases related to a legal issue. At some point, a legal case will probably end and the holds associated with the case will be removed and the eDiscovery case will be closed (or deleted). In fact, if a hold that's placed on an inactive mailbox is associated with an eDiscovery case, and the hold is released or the eDiscovery case is closed or deleted, the inactive mailbox will be permanently deleted.</span></span> 

<span data-ttu-id="f736c-173">Para obtener más información acerca de las directivas de retención de Office 365, vea [información general de las directivas de retención](retention-policies.md).</span><span class="sxs-lookup"><span data-stu-id="f736c-173">For more information about Office 365 retention policies, see [Overview of retention policies](retention-policies.md).</span></span>
  
## <a name="step-2-change-the-hold-duration-for-an-inactive-mailbox"></a><span data-ttu-id="f736c-174">Paso 2: cambiar la duración de retención para un buzón inactivo</span><span class="sxs-lookup"><span data-stu-id="f736c-174">Step 2: Change the hold duration for an inactive mailbox</span></span>

<span data-ttu-id="f736c-175">Tras identificar el tipo de retención que está colocada en el buzón inactivo (y si hay varias retenciones), el siguiente paso es cambiar la duración para la retención.</span><span class="sxs-lookup"><span data-stu-id="f736c-175">After you identify what type of hold is placed on the inactive mailbox (and whether there are multiple holds), the next step is to change the duration for the hold.</span></span> 
  
### <a name="change-the-duration-for-a-litigation-hold"></a><span data-ttu-id="f736c-176">Cambiar la duración de una retención por juicio.</span><span class="sxs-lookup"><span data-stu-id="f736c-176">Change the duration for a Litigation Hold</span></span>

<span data-ttu-id="f736c-p113">Aquí es cómo usar PowerShell en línea de Exchange para cambiar la duración de retención para un juicio que se coloca en un buzón de correo inactivo. No se puede usar el EAC. Ejecute el siguiente comando para cambiar la duración de la suspensión. En este ejemplo, se cambia la duración de retención a un período de tiempo ilimitado.</span><span class="sxs-lookup"><span data-stu-id="f736c-p113">Here's how to use Exchange Online PowerShell to change the hold duration for a Litigation Hold that is placed on an inactive mailbox. You can't use the EAC. Run the following command to change the hold duration. In this example, the hold duration is changed to an unlimited period of time.</span></span>
  
```
Set-Mailbox -InactiveMailbox -Identity <identity of inactive mailbox> -LitigationHoldDuration unlimited
```

<span data-ttu-id="f736c-181">El resultado es que se conservan los elementos en el buzón de correo inactivo indefinidamente o hasta que se elimina la suspensión o se cambia la duración de retención a un valor diferente.</span><span class="sxs-lookup"><span data-stu-id="f736c-181">The result is that items in the inactive mailbox are retained indefinitely or until the hold is removed or the hold duration is changed to a different value.</span></span>
  
> [!TIP]
> <span data-ttu-id="f736c-p114">La mejor manera de identificar un buzón inactivo es usando el valor **Distinguished Name** o **Exchange GUID**. El uso de uno de estos valores ayuda a impedir que se especifique accidentalmente el buzón equivocado.</span><span class="sxs-lookup"><span data-stu-id="f736c-p114">The best way to identify an inactive mailbox is by using its **Distinguished Name** or **Exchange GUID** value. Using one of these values helps prevent accidentally specifying the wrong mailbox.</span></span> 
  
### <a name="change-the-duration-for-an-in-place-hold"></a><span data-ttu-id="f736c-184">Cambiar la duración de una conservación local</span><span class="sxs-lookup"><span data-stu-id="f736c-184">Change the duration for an In-Place Hold</span></span>

 <span data-ttu-id="f736c-185">Puede usar el CEF o Exchange Online PowerShell para cambiar la duración de retención para una retención local.</span><span class="sxs-lookup"><span data-stu-id="f736c-185">You can use the EAC or Exchange Online PowerShell to change the hold duration for an In-Place Hold.</span></span> 
  
#### <a name="use-the-eac-to-change-the-hold-duration"></a><span data-ttu-id="f736c-186">Usar el EAC para cambiar la duración de retención</span><span class="sxs-lookup"><span data-stu-id="f736c-186">Use the EAC to change the hold duration</span></span>

1. <span data-ttu-id="f736c-p115">Si conoce el nombre de la retención local que desea cambiar, vaya al paso siguiente. De lo contrario, ejecute el siguiente comando para obtener el nombre de la retención local que se coloca en el buzón de correo inactivo. Utilice el GUID de suspensión en contexto que obtuvo en el [paso 1](#step-1-identify-the-holds-on-an-inactive-mailbox).</span><span class="sxs-lookup"><span data-stu-id="f736c-p115">If you know the name of the In-Place Hold that you want to change, go to the next step. Otherwise, run the following command to get the name of the In-Place Hold that is placed on the inactive mailbox. Use the In-Place Hold GUID that you obtained in [Step 1](#step-1-identify-the-holds-on-an-inactive-mailbox).</span></span>

    ```
    Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID> | FL Name
    ```

2. <span data-ttu-id="f736c-190">En el EAC, vaya a **administración de cumplimiento** \> **exhibición de documentos electrónicos en contexto &amp; suspensión**.</span><span class="sxs-lookup"><span data-stu-id="f736c-190">In the EAC, go to **Compliance management** \> **In-Place eDiscovery &amp; Hold**.</span></span>
    
3. <span data-ttu-id="f736c-191">Seleccione la retención local que desea cambiar y, a continuación, haga clic en **Editar** ![icono Editar](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif).</span><span class="sxs-lookup"><span data-stu-id="f736c-191">Select the In-Place Hold you want to change, and then click **Edit** ![Edit icon](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif).</span></span>
    
4. <span data-ttu-id="f736c-192">En la **exhibición de documentos electrónicos en contexto &amp; suspensión** propiedades de página, haga clic en **Retención en contexto**.</span><span class="sxs-lookup"><span data-stu-id="f736c-192">On the **In-Place eDiscovery &amp; Hold** properties page, click **In-Place Hold**.</span></span> 
    
5. <span data-ttu-id="f736c-193">Realice una de las siguientes acciones en función de la duración de retención actual:</span><span class="sxs-lookup"><span data-stu-id="f736c-193">Do one of the following based on the current hold duration:</span></span>
    
1. <span data-ttu-id="f736c-194">Haga clic en **Retenido indefinidamente** para retener elementos durante un período de tiempo ilimitado.</span><span class="sxs-lookup"><span data-stu-id="f736c-194">Click **Hold indefinitely** to hold items for an unlimited period of time.</span></span> 
    
2. <span data-ttu-id="f736c-p116">Haga clic en **Especificar número de días para retener elementos con respecto a su fecha de recepción** para retener elementos durante un período específico. Escriba el número de días que desea retener elementos para.</span><span class="sxs-lookup"><span data-stu-id="f736c-p116">Click **Specify number of days to hold items relative to their received date** to hold items for a specific period. Type the number of days that you want to hold items for.</span></span> 
    
    ![Captura de pantalla del cambio de duración para una conservación local](media/cfcfd92a-9d65-40c0-90ef-ab72697b0166.png)
  
6. <span data-ttu-id="f736c-198">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="f736c-198">Click **Save**.</span></span>
    
#### <a name="use-exchange-online-powershell-to-change-the-hold-duration"></a><span data-ttu-id="f736c-199">Use Exchange Online PowerShell para cambiar la duración de retención</span><span class="sxs-lookup"><span data-stu-id="f736c-199">Use Exchange Online PowerShell to change the hold duration</span></span>

1. <span data-ttu-id="f736c-p117">Si conoce el nombre de la retención local que desea cambiar, vaya al paso siguiente. De lo contrario, ejecute el siguiente comando para obtener el nombre de la retención local que se coloca en el buzón de correo inactivo. Utilice el GUID de suspensión en contexto que obtuvo en el [paso 1](#step-1-identify-the-holds-on-an-inactive-mailbox).</span><span class="sxs-lookup"><span data-stu-id="f736c-p117">If you know the name of the In-Place Hold that you want to change, go to the next step. Otherwise, run the following command to get the name of the In-Place Hold that is placed on the inactive mailbox. Use the In-Place Hold GUID that you obtained in [Step 1](#step-1-identify-the-holds-on-an-inactive-mailbox).</span></span>

    ```
    Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID> | FL Name
    ```

2. <span data-ttu-id="f736c-p118">Ejecute el siguiente comando para cambiar la duración de retención. En este ejemplo, se cambia la duración de retención a 2.555 días (aproximadamente 7 años).</span><span class="sxs-lookup"><span data-stu-id="f736c-p118">Run the following command to change the hold duration. In this example, the hold duration is changed to 2,555 days (approximately 7 years).</span></span> 
    
    ```
    Set-MailboxSearch <identity of In-Place Hold> -ItemHoldPeriod 2555
    ```

     <span data-ttu-id="f736c-205">Para cambiar la duración de retención a un período de tiempo ilimitado, use  _-ItemHoldPeriod unlimited_.</span><span class="sxs-lookup"><span data-stu-id="f736c-205">To change the hold duration to an unlimited period of time, use  _-ItemHoldPeriod unlimited_.</span></span>
  
## <a name="more-information"></a><span data-ttu-id="f736c-206">Más información</span><span class="sxs-lookup"><span data-stu-id="f736c-206">More information</span></span>

- <span data-ttu-id="f736c-p119">**¿Cómo se calcula la duración de retención para un elemento en un buzón inactivo?** La duración se calcula desde la fecha original en que un elemento de buzón se recibe o se crea.</span><span class="sxs-lookup"><span data-stu-id="f736c-p119">**How is the hold duration calculated for an item in an inactive mailbox?** The duration is calculated from the original date a mailbox item was received or created.</span></span> 
    
- <span data-ttu-id="f736c-p120">**¿Qué sucede cuando expira la duración de retención?** Cuando expira la duración de retención de un elemento en la carpeta Elementos recuperables, el elemento se elimina permanentemente (se purga) del buzón inactivo. Si no hay ninguna duración especificada para la retención que se coloca en el buzón inactivo, nunca se purgan los elementos de la carpeta Elementos recuperables (a menos que se cambie la duración de retención del buzón inactivo).</span><span class="sxs-lookup"><span data-stu-id="f736c-p120">**What happens when the hold duration expires?** When the hold duration expires for a mailbox item in the Recoverable Items folder, the item is permanently deleted (purged) from the inactive mailbox. If there is no duration specified for the hold placed on the inactive mailbox, items in the Recoverable Items folder are never purged (unless the hold duration for the inactive mailbox is changed).</span></span> 
    
- <span data-ttu-id="f736c-p121">**Es una directiva de retención de Exchange aún se procesan en buzones de correo inactivos?** Si se ha aplicado una directiva de retención de Exchange (los registros de mensajes de administración o MRM, característica en Exchange Online) a un buzón de correo cuando se realizó inactiva, va las directivas de eliminación (que están configuradas con una acción de retención **Eliminar** las etiquetas de retención) continuar que va a procesar en el buzón de correo inactivo. Esto significa que se mueven los elementos etiquetados con una directiva de eliminación a la carpeta elementos recuperables cuando expire el período de retención. Esos elementos, a continuación, se purgan desde el buzón de correo inactivo cuando expire la duración de retención para un elemento.</span><span class="sxs-lookup"><span data-stu-id="f736c-p121">**Is an Exchange retention policy still processed on inactive mailboxes?** If an Exchange retention policy (the messaging records management, or MRM, feature in Exchange Online) was applied to a mailbox when it was made inactive, the deletion policies (which are retention tags configured with a **Delete** retention action) will continue to be processed on the inactive mailbox. That means items that are tagged with a deletion policy are moved to the Recoverable Items folder when the retention period expires. Those items are then purged from the inactive mailbox when the hold duration for an item expires.</span></span> 
    
    <span data-ttu-id="f736c-p122">Por el contrario, se ignora cualquier directiva de archivo (que son etiquetas de retención configuradas con una acción de retención **MoveToArchive** ) que esté incluida en la directiva de retención asignada a un buzón inactivo. Eso significa que los elementos de un buzón inactivo etiquetados con una directiva de archivo permanecen en el buzón principal cuando expira el período de retención. No se mueven al buzón de archivo o a la carpeta Elementos recuperables en el buzón de archivo. Dado que un usuario no puede iniciar sesión en un buzón inactivo, no existen motivos para consumir los recursos del centro de datos para procesar las directivas de archivo.</span><span class="sxs-lookup"><span data-stu-id="f736c-p122">Conversely, any archive policies (which are retention tags configured with a **MoveToArchive** retention action) that are included in the retention policy assigned to an inactive mailbox are ignored. That means items in an inactive mailbox that are tagged with an archive policy remain in the primary mailbox when the retention period expires. They're not moved to the archive mailbox or to the Recoverable Items folder in the archive mailbox. Because a user can't sign in to an inactive mailbox, there's no reason to consume datacenter resources to process archive policies.</span></span> 
    
- <span data-ttu-id="f736c-p123">**Para comprobar la nueva duración de retención, ejecute uno de los siguientes comandos.** El primer comando es para retención por juicio; el segundo es para conservación local.</span><span class="sxs-lookup"><span data-stu-id="f736c-p123">**To check the new hold duration, run one of the following commands.** The first command is for Litigation Hold; the second is for In-Place Hold.</span></span> 

    ```
    Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox> | FL LitigationHoldDuration
    ```

    ```
    Get-MailboxSearch <identity of In-Place Hold> | FL ItemHoldPeriod
    ```

- <span data-ttu-id="f736c-p124">**Al igual que los buzones habituales, el Asistente para carpeta administrada (MFA) también procesa buzones inactivos.** En Exchange Online, el MFA procesa buzones una vez cada siete días aproximadamente. Después de cambiar la duración de retención para un buzón inactivo, puede usar el cmdlet **Start-ManagedFolderAssistant** para empezar a procesar inmediatamente la nueva duración de retención para el buzón inactivo. Ejecute el comando siguiente.</span><span class="sxs-lookup"><span data-stu-id="f736c-p124">**Like regular mailboxes, the Managed Folder Assistant (MFA) also processes inactive mailboxes.** In Exchange Online, the MFA processes mailboxes approximately once every 7 days. After you change the hold duration for an inactive mailbox, you can use the **Start-ManagedFolderAssistant** cmdlet to immediately start processing the new hold duration for the inactive mailbox. Run the following command.</span></span> 

    ```
    Start-ManagedFolderAssistant -InactiveMailbox <identity of inactive mailbox>
    ```
   
- <span data-ttu-id="f736c-p125">**Si se colocan una gran cantidad de suspensiones en un buzón inactivo, no todos de la suspensión se mostrará los GUID.** Puede ejecutar el siguiente comando para mostrar los GUID para todas las suspensiones (excepto las suspensiones litigios) que se colocan en un buzón de correo inactivo.</span><span class="sxs-lookup"><span data-stu-id="f736c-p125">**If a lot of holds are placed on an inactive mailbox, not all of the hold GUIDs will be displayed.** You can run the following command to display the GUIDs for all holds (except Litigation Holds) that are placed on an inactive mailbox.</span></span> 
    
    ```
    Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox> | Select-Object -ExpandProperty InPlaceHolds
    ```
