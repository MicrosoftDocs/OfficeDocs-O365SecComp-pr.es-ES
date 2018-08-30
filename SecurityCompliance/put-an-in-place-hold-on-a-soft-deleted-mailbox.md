---
title: Colocar una conservación local en un buzón eliminado temporalmente en Exchange Online
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 1/18/2017
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 421f72bd-dd43-4be1-82f5-0ae9ac43bd00
description: Obtenga información sobre cómo crear una conservación local en un buzón eliminado temporalmente para que se convierta en inactivo y se conserve su contenido. Después, puede usar las herramientas de Microsoft eDiscovery para buscar el buzón inactivo.
ms.openlocfilehash: abc0aa625a5483141f25111dc1858a3d989f32d0
ms.sourcegitcommit: e9dca2d6a7838f98bb7eca127fdda2372cda402c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/21/2018
ms.locfileid: "23003119"
---
# <a name="put-an-in-place-hold-on-a-soft-deleted-mailbox-in-exchange-online"></a><span data-ttu-id="2ee8d-104">Colocar una conservación local en un buzón eliminado temporalmente en Exchange Online</span><span class="sxs-lookup"><span data-stu-id="2ee8d-104">Put an In-Place Hold on a soft-deleted mailbox in Exchange Online</span></span>

<span data-ttu-id="2ee8d-p102">Obtenga información sobre cómo crear una conservación local en un buzón eliminado temporalmente para que se convierta en inactivo y se conserve su contenido. Después, puede usar las herramientas de Microsoft eDiscovery para buscar el buzón inactivo.</span><span class="sxs-lookup"><span data-stu-id="2ee8d-p102">Learn how to create an In-Place Hold for a soft-deleted mailbox to make it inactive and preserve its contents. Then you can use Microsoft eDiscovery tools to search the inactive mailbox.</span></span>
  
> [!NOTE]
> <span data-ttu-id="2ee8d-p103">Nos hemos pospuso la fecha límite de 1 de julio de 2017 para la creación de nuevos suspensiones en contexto en Exchange Online (en los planes independientes de Office 365 y Exchange Online). Pero más adelante este año o el principio del próximo año, no podrá crear nuevos suspensiones en contexto en Exchange Online. Como alternativa al uso de suspensiones en contexto, puede usar [las directivas de retención](https://go.microsoft.com/fwlink/?linkid=827811) o [casos de exhibición de documentos electrónicos](https://go.microsoft.com/fwlink/?linkid=780738) en la seguridad de Office 365 &amp; centro de cumplimiento. Después de que se dé de baja nuevo suspensiones en contexto, aún podrá modificar existente retenciones locales y creando un nuevo suspensiones en contexto en Exchange Server 2013 y las implementaciones híbridas de Exchange todavía se admitirán. Y, aún podrá colocar buzones en suspensión por litigio.</span><span class="sxs-lookup"><span data-stu-id="2ee8d-p103">We've postponed the July 1, 2017 deadline for creating new In-Place Holds in Exchange Online (in Office 365 and Exchange Online standalone plans). But later this year or early next year, you won't be able to create new In-Place Holds in Exchange Online. As an alternative to using In-Place Holds, you can use [eDiscovery cases](https://go.microsoft.com/fwlink/?linkid=780738) or [retention policies](https://go.microsoft.com/fwlink/?linkid=827811) in the Office 365 Security &amp; Compliance Center. After we decommission new In-Place Holds, you'll still be able to modify existing In-Place Holds, and creating new In-Place Holds in Exchange Server 2013 and Exchange hybrid deployments will still be supported. And, you'll still be able to place mailboxes on Litigation Hold.</span></span> 
  
<span data-ttu-id="2ee8d-p104">Es posible que tenga una situación donde una persona ha abandonado la organización y su correspondiente cuenta de usuario y su buzón se eliminaron. Posteriormente, se da cuenta hay información en el buzón de correo que debe conservarse. ¿Qué puede hacer? Si no ha caducado el período de retención de buzones eliminados, puede poner una retención local en el buzón eliminado (denominado un buzón eliminado temporalmente) y hacer que un buzón de correo inactivo. Un *buzón de correo inactivo* se usa para conservar el correo electrónico de un empleado anterior después de que abandona la organización. El contenido de un buzón inactivo se conserva para la duración de la conservación local que estaba se coloca en el buzón eliminado temporalmente cuando se realizó inactivos. Después de que el buzón de correo se realiza como inactiva, puede buscar el buzón de correo mediante el uso de exhibición de documentos electrónicos en contexto en Exchange Online, búsqueda de contenido en la seguridad de Office 365 &amp; centro de cumplimiento o el centro de exhibición de documentos electrónicos en SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="2ee8d-p104">You might have a situation where a person has left your organization, and their corresponding user account and mailbox were deleted. Afterwards, you realize there's information in the mailbox that needs to be preserved. What can you do? If the deleted mailbox retention period hasn't expired, you can put an In-Place Hold on the deleted mailbox (called a  soft-deleted mailbox ) and make it an inactive mailbox. An  *inactive mailbox*  is used to preserve a former employee's email after he or she leaves your organization. The contents of an inactive mailbox are preserved for the duration of the In-Place Hold that was is placed on the soft-deleted mailbox when it was made inactive. After the mailbox is made inactive, you can search the mailbox by using In-Place eDiscovery in Exchange Online, Content Search in the Office 365 Security &amp; Compliance Center, or the eDiscovery Center in SharePoint Online.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="2ee8d-p105">En Exchange Online, un buzón eliminado temporalmente es un buzón que se ha eliminado, pero se puede recuperar en un período de retención específico. El período de retención de buzón eliminado temporalmente en Exchange Online es de 30 días. Esto significa que el buzón se puede recuperar (o convertirse en un buzón inactivo) en un plazo de 30 días después de eliminarse. Transcurrido este período, un buzón eliminado temporalmente se marca para su eliminación permanente y no puede recuperarse ni convertirse en inactivo.</span><span class="sxs-lookup"><span data-stu-id="2ee8d-p105">In Exchange Online, a soft-deleted mailbox is a mailbox that's been deleted but can be recovered within a specific retention period. The soft-deleted mailbox retention period in Exchange Online is 30 days. This means that the mailbox can be recovered (or made an inactive mailbox) within 30 days of being deleted. After 30 days, a soft-deleted mailbox is marked for permanent deletion and can't be recovered or made inactive.</span></span> 
  
## <a name="before-you-begin"></a><span data-ttu-id="2ee8d-123">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="2ee8d-123">Before you begin</span></span>
<span data-ttu-id="2ee8d-124"><a name="sectionSection0"> </a></span><span class="sxs-lookup"><span data-stu-id="2ee8d-124"></span></span>

- <span data-ttu-id="2ee8d-p106">Tiene que usar el cmdlet **New-MailboxSearch** en Windows PowerShell para colocar una conservación local en un buzón eliminado temporalmente. No puede usar el Centro de administración de Exchange (EAC) ni el Centro de eDiscovery en SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="2ee8d-p106">You have to use the **New-MailboxSearch** cmdlet in Windows PowerShell to put an In-Place Hold on a soft-deleted mailbox. You can't use the Exchange admin center (EAC) or the eDiscovery Center in SharePoint Online.</span></span> 
    
- <span data-ttu-id="2ee8d-127">Para obtener información sobre cómo usar Windows PowerShell para conectarse a Exchange Online, vea [Conexión a Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span><span class="sxs-lookup"><span data-stu-id="2ee8d-127">To learn how to use Windows PowerShell to connect to Exchange Online, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span></span>
    
- <span data-ttu-id="2ee8d-128">Ejecute el siguiente comando para obtener información de identidad sobre los buzones eliminados temporalmente en la organización.</span><span class="sxs-lookup"><span data-stu-id="2ee8d-128">Run the following command to get identity information about the soft-deleted mailboxes in your organization.</span></span> 
    
  ```
  Get-Mailbox -SoftDeletedMailbox | FL Name,WhenSoftDeleted,DistinguishedName,ExchangeGuid,PrimarySmtpAddress
  ```

- <span data-ttu-id="2ee8d-129">Para obtener más información sobre buzones inactivos, consulte [Buzones de correo inactivos en Exchange Online](http://technet.microsoft.com/library/2f2948c5-1c5a-4643-865c-b36e4ac1414b.aspx).</span><span class="sxs-lookup"><span data-stu-id="2ee8d-129">For more information about inactive mailboxes, see [Inactive mailboxes in Exchange Online](http://technet.microsoft.com/library/2f2948c5-1c5a-4643-865c-b36e4ac1414b.aspx).</span></span>
    
## <a name="put-an-in-place-hold-on-a-soft-deleted-mailbox-to-make-it-an-inactive-mailbox"></a><span data-ttu-id="2ee8d-130">Colocar una conservación local en un buzón eliminado temporalmente para convertirlo en un buzón inactivo</span><span class="sxs-lookup"><span data-stu-id="2ee8d-130">Put an In-Place Hold on a soft-deleted mailbox to make it an inactive mailbox</span></span>
<span data-ttu-id="2ee8d-131"><a name="sectionSection1"> </a></span><span class="sxs-lookup"><span data-stu-id="2ee8d-131"></span></span>

<span data-ttu-id="2ee8d-p107">Use el cmdlet **New-MailboxSearch** para convertir un buzón eliminado temporalmente en un buzón inactivo. Para obtener más información, vea [New-MailboxSearch](http://technet.microsoft.com/library/74303b47-bb49-407c-a43b-590356eae35c.aspx).</span><span class="sxs-lookup"><span data-stu-id="2ee8d-p107">Use the **New-MailboxSearch** cmdlet to make a soft-deleted mailbox an inactive mailbox. For more information, see [New-MailboxSearch](http://technet.microsoft.com/library/74303b47-bb49-407c-a43b-590356eae35c.aspx).</span></span>
  
1. <span data-ttu-id="2ee8d-134">Cree una variable que contenga las propiedades del buzón eliminado temporalmente.</span><span class="sxs-lookup"><span data-stu-id="2ee8d-134">Create a variable that contains the properties of the soft-deleted mailbox.</span></span> 
    
  ```
  $SoftDeletedMailbox = Get-Mailbox -SoftDeletedMailbox -Identity <identity of soft-deleted mailbox>
  ```

    > [!IMPORTANT]
    > <span data-ttu-id="2ee8d-p108">En el comando anterior, use el valor de la propiedad **DistinguishedName** o **ExchangeGuid** para identificar el buzón eliminado temporalmente. Estas propiedades son únicas para cada buzón en su organización, mientras que es posible que un buzón activo y un buzón eliminado temporalmente tengan la misma dirección SMTP principal.</span><span class="sxs-lookup"><span data-stu-id="2ee8d-p108">In the previous command, use the value of the **DistinguishedName** or **ExchangeGuid** property to identify the soft-deleted mailbox. These properties are unique for each mailbox in your organization, whereas it's possible that an active mailbox and a soft-deleted mailbox might have the same primary SMTP address.</span></span> 
  
2. <span data-ttu-id="2ee8d-p109">Cree una conservación local y colóquela en el buzón eliminado temporalmente. En este ejemplo, no se especifica ninguna duración de la conservación. Esto significa que los elementos se conservarán de manera indefinida o hasta que la conservación se quite del buzón inactivo.</span><span class="sxs-lookup"><span data-stu-id="2ee8d-p109">Create an In-Place Hold and place it on the soft-deleted mailbox. In this example, no hold duration is specified. This means items will be held indefinitely or until the hold is removed from the inactive mailbox.</span></span>
    
  ```
  New-MailboxSearch -Name "InactiveMailboxHold" -SourceMailboxes $SoftDeletedMailbox.DistinguishedName -InPlaceHoldEnabled $true
  
  ```

    <span data-ttu-id="2ee8d-p110">También puede especificar una duración de la conservación cuando cree la conservación local. En este ejemplo se conservan elementos en el buzón inactivo durante aproximadamente 7 años.</span><span class="sxs-lookup"><span data-stu-id="2ee8d-p110">You can also specify a hold duration when you create the In-Place Hold. This example holds items in the inactive mailbox for approximately 7 years.</span></span>
    
  ```
  New-MailboxSearch -Name "InactiveMailboxHold" -SourceMailboxes $SoftDeletedMailbox.DistinguishedName -InPlaceHoldEnabled $true -ItemHoldPeriod 2777
  ```

3. <span data-ttu-id="2ee8d-142">Después de unos minutos, ejecute uno de los siguientes comandos para comprobar que el buzón eliminado temporalmente es un buzón inactivo.</span><span class="sxs-lookup"><span data-stu-id="2ee8d-142">After a few moments, run one of the following commands to verify that the soft-deleted mailbox is an inactive mailbox.</span></span>
    
  ```
  Get-Mailbox -InactiveMailboxOnly
  ```

    <span data-ttu-id="2ee8d-143">O bien</span><span class="sxs-lookup"><span data-stu-id="2ee8d-143">Or</span></span>
    
  ```
  Get-Mailbox -InactiveMailboxOnly -Identity $SoftDeletedMailbox.DistinguishedName  | FL IsInactiveMailbox
  ```

## <a name="more-information"></a><span data-ttu-id="2ee8d-144">Más información</span><span class="sxs-lookup"><span data-stu-id="2ee8d-144">More information</span></span>
<span data-ttu-id="2ee8d-145"><a name="sectionSection2"> </a></span><span class="sxs-lookup"><span data-stu-id="2ee8d-145"></span></span>

<span data-ttu-id="2ee8d-p111">Después de que convierta un buzón eliminado temporalmente en un buzón inactivo, existen varias maneras en las que puede administrar el buzón. Para obtener más información, vea:</span><span class="sxs-lookup"><span data-stu-id="2ee8d-p111">After you make a soft-deleted mailbox an inactive mailbox, there are a number of ways you can manage the mailbox. For more information, see:</span></span>
  
- [<span data-ttu-id="2ee8d-148">Cambiar la duración de retención para un buzón inactivo en Exchange Online</span><span class="sxs-lookup"><span data-stu-id="2ee8d-148">Change the hold duration for an inactive mailbox in Exchange Online</span></span>](http://technet.microsoft.com/library/96eb634e-af2f-454e-8014-b698396811c4.aspx)
    
- [<span data-ttu-id="2ee8d-149">Recuperar un buzón inactivo en Exchange Online</span><span class="sxs-lookup"><span data-stu-id="2ee8d-149">Recover an inactive mailbox in Exchange Online</span></span>](http://technet.microsoft.com/library/283838b4-66ba-4c34-b221-e1a3875e1d29.aspx)
    
- [<span data-ttu-id="2ee8d-150">Restaurar un buzón inactivo en Exchange Online</span><span class="sxs-lookup"><span data-stu-id="2ee8d-150">Restore an inactive mailbox in Exchange Online</span></span>](http://technet.microsoft.com/library/1fb02feb-49e5-4485-aec5-9f1537b772b6.aspx)
    
- [<span data-ttu-id="2ee8d-151">Quitar una retención de un buzón inactivo en Exchange Online</span><span class="sxs-lookup"><span data-stu-id="2ee8d-151">Remove a hold from an inactive mailbox in Exchange Online</span></span>](http://technet.microsoft.com/library/930a98c3-cd81-4aaa-8e22-19714cb2b731.aspx)
    

