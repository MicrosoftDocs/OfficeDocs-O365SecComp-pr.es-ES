---
title: Colocar una conservación local en un buzón eliminado temporalmente en Exchange Online
ms.author: markjjo
author: markjjo
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid: ''
ms.assetid: 421f72bd-dd43-4be1-82f5-0ae9ac43bd00
description: Obtenga información sobre cómo crear una conservación local en un buzón eliminado temporalmente para que se convierta en inactivo y se conserve su contenido. Después, puede usar las herramientas de Microsoft eDiscovery para buscar el buzón inactivo.
ms.openlocfilehash: 70feb265e95741406dbf170c6be70bd83b2ec081
ms.sourcegitcommit: a80bd8626720fabdf592b84e4424cd3a83d08280
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/23/2019
ms.locfileid: "30223529"
---
# <a name="put-an-in-place-hold-on-a-soft-deleted-mailbox-in-exchange-online"></a><span data-ttu-id="456c2-104">Colocar una conservación local en un buzón eliminado temporalmente en Exchange Online</span><span class="sxs-lookup"><span data-stu-id="456c2-104">Put an In-Place Hold on a soft-deleted mailbox in Exchange Online</span></span>

<span data-ttu-id="456c2-p102">Obtenga información sobre cómo crear una conservación local en un buzón eliminado temporalmente para que se convierta en inactivo y se conserve su contenido. Después, puede usar las herramientas de Microsoft eDiscovery para buscar el buzón inactivo.</span><span class="sxs-lookup"><span data-stu-id="456c2-p102">Learn how to create an In-Place Hold for a soft-deleted mailbox to make it inactive and preserve its contents. Then you can use Microsoft eDiscovery tools to search the inactive mailbox.</span></span>
  
> [!NOTE]
> <span data-ttu-id="456c2-p103">Hemos pospuesto la fecha límite para crear nuevas reTenciones locales en Exchange Online (en los planes independientes de Office 365 y Exchange Online). Pero más adelante este año, no podrá crear nuevas reTenciones locales en Exchange Online. Como alternativa al uso de conservaciones locales, puede usar casos de [exhibición](https://go.microsoft.com/fwlink/?linkid=780738) de documentos electrónicos o [directivas de retención](https://go.microsoft.com/fwlink/?linkid=827811) en el &amp; centro de seguridad y cumplimiento de Office 365. Después de haber retirado nuevas retenciones locales, aún podrá modificar las suspensiones locales existentes y crear reTenciones locales en Exchange Server 2013 y las implementaciones híbridas de Exchange seguirán siendo compatibles. Además, podrá seguir colocando buzones de correo en retención por juicio.</span><span class="sxs-lookup"><span data-stu-id="456c2-p103">We've postponed the deadline for creating new In-Place Holds in Exchange Online (in Office 365 and Exchange Online standalone plans). But later this year or early next year, you won't be able to create new In-Place Holds in Exchange Online. As an alternative to using In-Place Holds, you can use [eDiscovery cases](https://go.microsoft.com/fwlink/?linkid=780738) or [retention policies](https://go.microsoft.com/fwlink/?linkid=827811) in the Office 365 Security &amp; Compliance Center. After we decommission new In-Place Holds, you'll still be able to modify existing In-Place Holds, and creating new In-Place Holds in Exchange Server 2013 and Exchange hybrid deployments will still be supported. And, you'll still be able to place mailboxes on Litigation Hold.</span></span> 
  
<span data-ttu-id="456c2-p104">Es posible que tenga una situación en la que una persona haya abandonado su organización y que se haya eliminado la cuenta de usuario y el buzón correspondientes. Después, se da cuenta de que hay información en el buzón que debe conservarse. ¿Qué puede hacer? Si el período de retención de buzón eliminado no ha expirado, puede colocar una conservación local en el buzón de correo eliminado (denominado buzón de correo eliminado temporalmente) y convertirlo en un buzón inactivo. Un *buzón inactivo* se usa para conservar el correo electrónico de un antiguo empleado después de que abandone la organización. El contenido de un buzón inactivo se conserva durante el período de tiempo de la retención local que se coloca en el buzón de correo eliminado temporalmente cuando se ha inactivo. Una vez que el buzón se convierte en inactivo, puede buscar en el buzón de correo mediante eDiscovery local en Exchange Online, en el centro de seguridad &amp; de Office 365 o en el centro de exhibición de documentos electrónicos de SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="456c2-p104">You might have a situation where a person has left your organization, and their corresponding user account and mailbox were deleted. Afterwards, you realize there's information in the mailbox that needs to be preserved. What can you do? If the deleted mailbox retention period hasn't expired, you can put an In-Place Hold on the deleted mailbox (called a  soft-deleted mailbox ) and make it an inactive mailbox. An  *inactive mailbox*  is used to preserve a former employee's email after he or she leaves your organization. The contents of an inactive mailbox are preserved for the duration of the In-Place Hold that was is placed on the soft-deleted mailbox when it was made inactive. After the mailbox is made inactive, you can search the mailbox by using In-Place eDiscovery in Exchange Online, Content Search in the Office 365 Security &amp; Compliance Center, or the eDiscovery Center in SharePoint Online.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="456c2-p105">En Exchange Online, un buzón eliminado temporalmente es un buzón que se ha eliminado, pero se puede recuperar en un período de retención específico. El período de retención de buzón eliminado temporalmente en Exchange Online es de 30 días. Esto significa que el buzón se puede recuperar (o convertirse en un buzón inactivo) en un plazo de 30 días después de eliminarse. Transcurrido este período, un buzón eliminado temporalmente se marca para su eliminación permanente y no puede recuperarse ni convertirse en inactivo.</span><span class="sxs-lookup"><span data-stu-id="456c2-p105">In Exchange Online, a soft-deleted mailbox is a mailbox that's been deleted but can be recovered within a specific retention period. The soft-deleted mailbox retention period in Exchange Online is 30 days. This means that the mailbox can be recovered (or made an inactive mailbox) within 30 days of being deleted. After 30 days, a soft-deleted mailbox is marked for permanent deletion and can't be recovered or made inactive.</span></span> 
  
## <a name="before-you-begin"></a><span data-ttu-id="456c2-123">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="456c2-123">Before you begin</span></span>

- <span data-ttu-id="456c2-p106">Tiene que usar el cmdlet **New-MailboxSearch** en Windows PowerShell para colocar una conservación local en un buzón eliminado temporalmente. No puede usar el Centro de administración de Exchange (EAC) ni el Centro de eDiscovery en SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="456c2-p106">You have to use the **New-MailboxSearch** cmdlet in Windows PowerShell to put an In-Place Hold on a soft-deleted mailbox. You can't use the Exchange admin center (EAC) or the eDiscovery Center in SharePoint Online.</span></span> 
    
- <span data-ttu-id="456c2-126">Para obtener información sobre cómo usar Windows PowerShell para conectarse a Exchange Online, vea [Conexión a Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span><span class="sxs-lookup"><span data-stu-id="456c2-126">To learn how to use Windows PowerShell to connect to Exchange Online, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span></span>
    
- <span data-ttu-id="456c2-127">Ejecute el siguiente comando para obtener información de identidad sobre los buzones eliminados temporalmente en la organización.</span><span class="sxs-lookup"><span data-stu-id="456c2-127">Run the following command to get identity information about the soft-deleted mailboxes in your organization.</span></span> 
    
  ```
  Get-Mailbox -SoftDeletedMailbox | FL Name,WhenSoftDeleted,DistinguishedName,ExchangeGuid,PrimarySmtpAddress
  ```

- <span data-ttu-id="456c2-128">Para obtener más información acerca de los buzones inactivos, vea [información general sobre buzones inactivos en Office 365](inactive-mailboxes-in-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="456c2-128">For more information about inactive mailboxes, see [Overview of inactive mailboxes in Office 365](inactive-mailboxes-in-office-365.md).</span></span>
    
## <a name="put-an-in-place-hold-on-a-soft-deleted-mailbox-to-make-it-an-inactive-mailbox"></a><span data-ttu-id="456c2-129">Colocar una conservación local en un buzón eliminado temporalmente para convertirlo en un buzón inactivo</span><span class="sxs-lookup"><span data-stu-id="456c2-129">Put an In-Place Hold on a soft-deleted mailbox to make it an inactive mailbox</span></span>

<span data-ttu-id="456c2-p107">Use el cmdlet **New-MailboxSearch** para convertir un buzón eliminado temporalmente en un buzón inactivo. Para obtener más información, vea [New-MailboxSearch](http://technet.microsoft.com/library/74303b47-bb49-407c-a43b-590356eae35c.aspx).</span><span class="sxs-lookup"><span data-stu-id="456c2-p107">Use the **New-MailboxSearch** cmdlet to make a soft-deleted mailbox an inactive mailbox. For more information, see [New-MailboxSearch](http://technet.microsoft.com/library/74303b47-bb49-407c-a43b-590356eae35c.aspx).</span></span>
  
1. <span data-ttu-id="456c2-132">Cree una variable que contenga las propiedades del buzón eliminado temporalmente.</span><span class="sxs-lookup"><span data-stu-id="456c2-132">Create a variable that contains the properties of the soft-deleted mailbox.</span></span> 
    
   ```
   $SoftDeletedMailbox = Get-Mailbox -SoftDeletedMailbox -Identity <identity of soft-deleted mailbox>
   ```

    > [!IMPORTANT]
    > <span data-ttu-id="456c2-p108">En el comando anterior, use el valor de la propiedad **DistinguishedName** o **ExchangeGuid** para identificar el buzón eliminado temporalmente. Estas propiedades son únicas para cada buzón en su organización, mientras que es posible que un buzón activo y un buzón eliminado temporalmente tengan la misma dirección SMTP principal.</span><span class="sxs-lookup"><span data-stu-id="456c2-p108">In the previous command, use the value of the **DistinguishedName** or **ExchangeGuid** property to identify the soft-deleted mailbox. These properties are unique for each mailbox in your organization, whereas it's possible that an active mailbox and a soft-deleted mailbox might have the same primary SMTP address.</span></span> 
  
2. <span data-ttu-id="456c2-p109">Cree una conservación local y colóquela en el buzón eliminado temporalmente. En este ejemplo, no se especifica ninguna duración de la conservación. Esto significa que los elementos se conservarán de manera indefinida o hasta que la conservación se quite del buzón inactivo.</span><span class="sxs-lookup"><span data-stu-id="456c2-p109">Create an In-Place Hold and place it on the soft-deleted mailbox. In this example, no hold duration is specified. This means items will be held indefinitely or until the hold is removed from the inactive mailbox.</span></span>
    
   ```
   New-MailboxSearch -Name "InactiveMailboxHold" -SourceMailboxes $SoftDeletedMailbox.DistinguishedName -InPlaceHoldEnabled $true
    ```
   <span data-ttu-id="456c2-p110">También puede especificar una duración de la conservación cuando cree la conservación local. En este ejemplo se conservan elementos en el buzón inactivo durante aproximadamente 7 años.</span><span class="sxs-lookup"><span data-stu-id="456c2-p110">You can also specify a hold duration when you create the In-Place Hold. This example holds items in the inactive mailbox for approximately 7 years.</span></span>
    
   ```
   New-MailboxSearch -Name "InactiveMailboxHold" -SourceMailboxes $SoftDeletedMailbox.DistinguishedName -InPlaceHoldEnabled $true -ItemHoldPeriod 2777
   ```

3. <span data-ttu-id="456c2-140">Después de unos minutos, ejecute uno de los siguientes comandos para comprobar que el buzón eliminado temporalmente es un buzón inactivo.</span><span class="sxs-lookup"><span data-stu-id="456c2-140">After a few moments, run one of the following commands to verify that the soft-deleted mailbox is an inactive mailbox.</span></span>
    
   ```
   Get-Mailbox -InactiveMailboxOnly
   ```

    <span data-ttu-id="456c2-141">O bien</span><span class="sxs-lookup"><span data-stu-id="456c2-141">Or</span></span>
    
   ```
   Get-Mailbox -InactiveMailboxOnly -Identity $SoftDeletedMailbox.DistinguishedName  | FL IsInactiveMailbox
   ```

## <a name="more-information"></a><span data-ttu-id="456c2-142">Más información</span><span class="sxs-lookup"><span data-stu-id="456c2-142">More information</span></span>

<span data-ttu-id="456c2-p111">Después de que convierta un buzón eliminado temporalmente en un buzón inactivo, existen varias maneras en las que puede administrar el buzón. Para obtener más información, vea:</span><span class="sxs-lookup"><span data-stu-id="456c2-p111">After you make a soft-deleted mailbox an inactive mailbox, there are a number of ways you can manage the mailbox. For more information, see:</span></span>
  
- [<span data-ttu-id="456c2-145">Cambiar la duración de retención para un buzón inactivo</span><span class="sxs-lookup"><span data-stu-id="456c2-145">Change the hold duration for an inactive mailbox</span></span>](change-the-hold-duration-for-an-inactive-mailbox.md)
    
- [<span data-ttu-id="456c2-146">Recuperar un buzón inactivo</span><span class="sxs-lookup"><span data-stu-id="456c2-146">Recover an inactive mailbox</span></span>](recover-an-inactive-mailbox.md)
    
- [<span data-ttu-id="456c2-147">Restaurar un buzón inactivo</span><span class="sxs-lookup"><span data-stu-id="456c2-147">Restore an inactive mailbox</span></span>](restore-an-inactive-mailbox.md)
    
- <span data-ttu-id="456c2-148">[Eliminar un buzón inactivo](delete-an-inactive-mailbox.md) (quitando la retención)</span><span class="sxs-lookup"><span data-stu-id="456c2-148">[Delete an inactive mailbox](delete-an-inactive-mailbox.md) (by removing the hold)</span></span>
