---
title: Poner un buzón en retención por juicio
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 10/18/2016
ms.audience: End User
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: adee4621-3626-4aec-aa53-00b35ff0d0b0
description: 'Coloque un buzón en retención por juicio para conservar todo el contenido del buzón, incluidos los elementos eliminados y las versiones originales de los elementos modificados. '
ms.openlocfilehash: 9c2d5c77a604e4dbe6e1f1db75142d3bf5790618
ms.sourcegitcommit: e9dca2d6a7838f98bb7eca127fdda2372cda402c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/21/2018
ms.locfileid: "23002849"
---
# <a name="place-a-mailbox-on-litigation-hold"></a><span data-ttu-id="89fe5-103">Poner un buzón en retención por juicio</span><span class="sxs-lookup"><span data-stu-id="89fe5-103">Place a mailbox on Litigation Hold</span></span>
 
<span data-ttu-id="89fe5-p101">Coloque un buzón en retención por juicio para conservar todo el contenido del buzón, incluidos los elementos eliminados y las versiones originales de los elementos modificados. Al colocar el buzón de correo de un usuario en retención por juicio, el contenido del buzón de archivo del usuario (si está habilitado) también se coloca en retención. Los elementos eliminados y modificados se conservan durante un período especificado o hasta que se elimina la retención por juicio del buzón. Todos los elementos del buzón de correo se devuelven en una búsqueda de [In-Place eDiscovery](http://technet.microsoft.com/library/6377cb7a-3416-4e15-8571-c45d2160fc6f.aspx).</span><span class="sxs-lookup"><span data-stu-id="89fe5-p101">Place a mailbox on Litigation Hold to preserve all mailbox content, including deleted items and original versions of modified items. When you place a user' mailbox on Litigation Hold, content in the user's archive mailbox (if it's enabled) is also placed on hold. Deleted and modified items are preserved for a specified period, or until you remove the mailbox from Litigation Hold. All such mailbox items are returned in an [In-Place eDiscovery](http://technet.microsoft.com/library/6377cb7a-3416-4e15-8571-c45d2160fc6f.aspx) search.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="89fe5-p102">La suspensión por litigio conserva los elementos en la carpeta elementos recuperables en el buzón del usuario. Según el número y tamaño de los elementos eliminados o se han modificado, el tamaño de la carpeta elementos recuperables del buzón puede aumentar rápidamente. De forma predeterminada, la carpeta elementos recuperables está configurada con una cuota alta. En Exchange Online, esta cuota se incrementa automáticamente cuando se realiza un buzón en suspensión por litigio. En Exchange Server 2013, se recomienda supervisar los buzones de correo que se colocan en suspensión por litigio semanalmente para asegurarse de que no alcancen los límites de las cuotas de elementos recuperables.</span><span class="sxs-lookup"><span data-stu-id="89fe5-p102">Litigation Hold preserves items in the Recoverable Items folder in the user's mailbox. Depending on number and size of items deleted or modified, the size of the Recoverable Items folder of the mailbox may increase quickly. The Recoverable Items folder is configured with a high quota by default. In Exchange Online, this quota is automatically increased when you place a mailbox on Litigation Hold. In Exchange Server 2013, we recommend that you monitor mailboxes that are placed on Litigation Hold on a weekly basis to ensure they don't reach the limits of the Recoverable Items quotas.</span></span> 
  
## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="89fe5-113">¿Qué necesita saber antes de empezar?</span><span class="sxs-lookup"><span data-stu-id="89fe5-113">What do you need to know before you begin?</span></span>
<span data-ttu-id="89fe5-114"><a name="sectionSection0"> </a></span><span class="sxs-lookup"><span data-stu-id="89fe5-114"></span></span>

- <span data-ttu-id="89fe5-115">Tiempo estimado para finalizar: 5 minutos</span><span class="sxs-lookup"><span data-stu-id="89fe5-115">Estimated time to complete: 5 minutes</span></span>
    
- <span data-ttu-id="89fe5-116">La configuración de la retención por juicio puede tardar hasta 60 minutos en surtir efecto.</span><span class="sxs-lookup"><span data-stu-id="89fe5-116">The Litigation Hold setting may take up to 60 minutes to take effect.</span></span>
    
- <span data-ttu-id="89fe5-p103">Deberá tener asignados permisos antes de poder llevar a cabo este procedimiento o procedimientos. Para ver qué permisos necesita, consulte el entrada "Conservación local" en el tema [Permisos de directivas de mensajería y conformidad](http://technet.microsoft.com/library/ec4d3b9f-b85a-4cb9-95f5-6fc149c3899b.aspx).</span><span class="sxs-lookup"><span data-stu-id="89fe5-p103">You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "In-Place Hold" entry in the [Messaging policy and compliance permissions](http://technet.microsoft.com/library/ec4d3b9f-b85a-4cb9-95f5-6fc149c3899b.aspx) topic.</span></span> 
    
- <span data-ttu-id="89fe5-p104">Para poner un buzón de Exchange Online en juicio, se debe asignar una licencia de Exchange Online (Plan 2). Si un buzón se asigna una licencia de Exchange Online (Plan 1), tendría asignarla a una licencia independiente de archivado de Exchange Online para poner en espera.</span><span class="sxs-lookup"><span data-stu-id="89fe5-p104">To place an Exchange Online mailbox on Litigation Hold, it must be assigned an Exchange Online (Plan 2) license. If a mailbox is assigned an Exchange Online (Plan 1) license, you would have to assign it a separate Exchange Online Archiving license to place it on hold.</span></span>
    
- <span data-ttu-id="89fe5-p105">Como se explica anteriormente, cuando se coloca un juicio en el buzón del usuario, contenido en el buzón del usuario archivo también se pondrá en espera. Si se coloca un juicio en un buzón principal local en una implementación híbrida de Exchange, el buzón de archivo basados en la nube (si está habilitada) también se pondrá en espera.</span><span class="sxs-lookup"><span data-stu-id="89fe5-p105">As previously explained, when you place a Litigation Hold on a user's mailbox, content in the user's archive mailbox is also placed on hold. If you place a Litigation Hold on an on-premises primary mailbox in an Exchange hybrid deployment, the cloud-based archive mailbox (if enabled) is also placed on hold.</span></span>
    
- <span data-ttu-id="89fe5-p106">En Exchange Online, la cuota de la carpeta elementos recuperables se incrementa automáticamente a 100 GB cuando se coloca un buzón en suspensión por litigio. El tamaño predeterminado de esta carpeta es de 30 GB.</span><span class="sxs-lookup"><span data-stu-id="89fe5-p106">In Exchange Online, the quota for the Recoverable Items folder is automatically increased to 100 GB when you place a mailbox on Litigation Hold. The default size of this folder is 30 GB.</span></span>
    
- <span data-ttu-id="89fe5-p107">Juicio conserva los elementos eliminados y conserva también versiones originales de elementos modificados hasta que se quite la suspensión. Opcionalmente, puede especificar una duración de retención, que conserva el nombre de un elemento de buzón de correo para el período de tiempo especificado. Si especifica un período de duración de retención, se calcula a partir de la fecha se recibe un mensaje o se crea un elemento de buzón de correo. Para conservar los elementos que cumplen los criterios especificados, utilice una retención local para crear una suspensión basada en consultas. Para obtener información detallada, vea [crear o quitar una retención local](http://technet.microsoft.com/library/9d5d8d37-a053-4830-9cb1-6e1ede25e963.aspx).</span><span class="sxs-lookup"><span data-stu-id="89fe5-p107">Litigation Hold preserves deleted items and also preserves original versions of modified items until the hold is removed. You can optionally specify a hold duration, which preserves a mailbox item for the specified duration period. If you specify a hold duration period, it's calculated from the date a message is received or a mailbox item is created. To preserve items that meet your specified criteria, use an In-Place Hold to create a query-based hold. For details, see [Create or Remove an In-Place Hold](http://technet.microsoft.com/library/9d5d8d37-a053-4830-9cb1-6e1ede25e963.aspx).</span></span>
    
- <span data-ttu-id="89fe5-p108">Para usar el Shell para colocar un buzón de Exchange Online en espera, se debe usar Exchange Online PowerShell. Para obtener más información, vea [Connect to Exchange Online Using Remote PowerShell](http://technet.microsoft.com/library/c8bea338-6c1a-4bdf-8de0-7895d427ee5b.aspx).</span><span class="sxs-lookup"><span data-stu-id="89fe5-p108">To use the Shell to place an Exchange Online mailbox on hold, you have to use Exchange Online PowerShell. For more information, see [Connect to Exchange Online Using Remote PowerShell](http://technet.microsoft.com/library/c8bea338-6c1a-4bdf-8de0-7895d427ee5b.aspx).</span></span>
    
- <span data-ttu-id="89fe5-p109">No se admite la creación de una retención por juicio en un buzón de carpeta pública. Tendrá que usar la conservación local para crear una retención en las carpetas públicas.</span><span class="sxs-lookup"><span data-stu-id="89fe5-p109">Placing a Litigation Hold on a public folder mailbox isn't supported. You have to use In-Place Hold to place a hold on public folders.</span></span>
    
## <a name="use-the-eac-to-place-a-mailbox-on-litigation-hold"></a><span data-ttu-id="89fe5-134">Usar el EMC para colocar un buzón en retención por juicio</span><span class="sxs-lookup"><span data-stu-id="89fe5-134">Use the EAC to place a mailbox on Litigation Hold</span></span>
<span data-ttu-id="89fe5-135"><a name="sectionSection1"> </a></span><span class="sxs-lookup"><span data-stu-id="89fe5-135"></span></span>

1. <span data-ttu-id="89fe5-136">Vaya a **Destinatarios** \> **Buzones de correo**.</span><span class="sxs-lookup"><span data-stu-id="89fe5-136">Go to **Recipients** \> **Mailboxes**.</span></span>
    
2. <span data-ttu-id="89fe5-137">En la lista de buzones de usuario, haga clic en el buzón de correo que desea colocar en suspensión por litigio y, a continuación, haga clic en **Editar** ![icono Editar](media/ITPro-EAC-EditIcon.gif).</span><span class="sxs-lookup"><span data-stu-id="89fe5-137">In the list of user mailboxes, click the mailbox that you want to place on Litigation Hold, and then click **Edit** ![Edit icon](media/ITPro-EAC-EditIcon.gif).</span></span>
    
3. <span data-ttu-id="89fe5-138">En la página de propiedades del buzón de correo, haga clic en **características de buzón.**</span><span class="sxs-lookup"><span data-stu-id="89fe5-138">On the mailbox properties page, click **Mailbox features.**</span></span>
    
4. <span data-ttu-id="89fe5-139">En **Retención por juicio: Deshabilitado**, haga clic en **Habilitar** para colocar el buzón en Retención por juicio.</span><span class="sxs-lookup"><span data-stu-id="89fe5-139">Under **Litigation hold: Disabled**, click **Enable** to place the mailbox on Litigation Hold.</span></span> 
    
5. <span data-ttu-id="89fe5-140">En la página **Retención por juicio**, especifique la siguiente información opcional:</span><span class="sxs-lookup"><span data-stu-id="89fe5-140">On the **Litigation Hold** page, enter the following optional information:</span></span> 
    
  - <span data-ttu-id="89fe5-p110">**Duración de retención por juicio (días):** Utilice este cuadro para especificar cuánto tiempo se conservarán los elementos del buzón cuando este se ponga en retención por juicio. La duración se calcula desde la fecha en que un elemento de buzón se recibe o se crea. Si deja este cuadro en blanco, los elementos se conservan indefinidamente o hasta que se elimine la retención. Use días para especificar la duración.</span><span class="sxs-lookup"><span data-stu-id="89fe5-p110">**Litigation hold duration (days)** Use this box to specify how long mailbox items are held when the mailbox is placed on Litigation Hold. The duration is calculated from the date a mailbox item is received or created. If you leave this box blank, items are held indefinitely or until the hold is removed. Use days to specify the duration.</span></span> 
    
  - <span data-ttu-id="89fe5-p111">**Nota** Utilice este cuadro para informar al usuario que su buzón se encuentra en suspensión por litigio. La nota aparecerá en el buzón del usuario si está utilizando Outlook 2010 o posterior.</span><span class="sxs-lookup"><span data-stu-id="89fe5-p111">**Note** Use this box to inform the user their mailbox is on Litigation Hold. The note will appear in the user's mailbox if they're using Outlook 2010 or later.</span></span> 
    
  - <span data-ttu-id="89fe5-p112">**Dirección URL** Utilice este cuadro para dirigir al usuario a un sitio Web para obtener más información acerca de la suspensión por litigio. Esta dirección URL aparece en el buzón del usuario si usan Outlook 2010 o posterior.</span><span class="sxs-lookup"><span data-stu-id="89fe5-p112">**URL** Use this box to direct the user to a website for more information about Litigation Hold. This URL appears in the user's mailbox if they are using Outlook 2010 or later.</span></span> 
    
6. <span data-ttu-id="89fe5-149">Haga clic en **Guardar** en la página **Retención por juicio** y, después, haga clic en **Guardar** en la página de propiedades del buzón.</span><span class="sxs-lookup"><span data-stu-id="89fe5-149">Click **Save** on the **Litigation Hold** page, and then click **Save** on the mailbox properties page.</span></span> 
  
## <a name="use-the-shell-to-place-a-mailbox-on-litigation-hold-indefinitely"></a><span data-ttu-id="89fe5-150">Usar el Shell para colocar un buzón en retención por juicio indefinidamente</span><span class="sxs-lookup"><span data-stu-id="89fe5-150">Use the Shell to place a mailbox on Litigation Hold indefinitely</span></span>
<span data-ttu-id="89fe5-151"><a name="sectionSection2"> </a></span><span class="sxs-lookup"><span data-stu-id="89fe5-151"></span></span>

<span data-ttu-id="89fe5-p113">En este ejemplo, se coloca el buzón bsuneja@contoso.com en retención por juicio. Los elementos del buzón se conservan indefinidamente o hasta que se elimine la retención.</span><span class="sxs-lookup"><span data-stu-id="89fe5-p113">This example places the mailbox bsuneja@contoso.com on Litigation Hold. Items in the mailbox are held indefinitely or until the hold is removed.</span></span>
  
```
Set-Mailbox bsuneja@contoso.com -LitigationHoldEnabled $true
```

> [!NOTE]
> <span data-ttu-id="89fe5-154">Al colocar un buzón en retención por juicio indefinidamente (sin especificar una duración), el valor de la propiedad  _LitigationHoldDuration_ del buzón se establece en  `Unlimited`.</span><span class="sxs-lookup"><span data-stu-id="89fe5-154">When you place a mailbox on Litigation Hold indefinitely (by not specifying a duration period), the value for the  _LitigationHoldDuration_ property mailbox is set to  `Unlimited`.</span></span> 
  
## <a name="use-the-shell-to-place-a-mailbox-on-litigation-hold-and-preserve-items-for-a-specified-duration"></a><span data-ttu-id="89fe5-155">Usar el Shell para colocar un buzón en retención por juicio y conservar los elementos durante un tiempo especificado</span><span class="sxs-lookup"><span data-stu-id="89fe5-155">Use the Shell to place a mailbox on Litigation Hold and preserve items for a specified duration</span></span>
<span data-ttu-id="89fe5-156"><a name="sectionSection3"> </a></span><span class="sxs-lookup"><span data-stu-id="89fe5-156"></span></span>

<span data-ttu-id="89fe5-157">Este ejemplo coloca el buzón bsuneja@contoso.com en retención por juicio y conserva los elementos durante 2555 días (aproximadamente 7 años).</span><span class="sxs-lookup"><span data-stu-id="89fe5-157">This example places the mailbox bsuneja@contoso.com on Litigation Hold and preserves items for 2555 days (approximately 7 years).</span></span> 
  
```
Set-Mailbox bsuneja@contoso.com -LitigationHoldEnabled $true -LitigationHoldDuration 2555
```

## <a name="use-the-shell-to-place-all-mailboxes-on-litigation-hold-for-a-specified-duration"></a><span data-ttu-id="89fe5-158">Usar el Shell para colocar todos los buzones en retención por juicio durante un tiempo especificado</span><span class="sxs-lookup"><span data-stu-id="89fe5-158">Use the Shell to place all mailboxes on Litigation Hold for a specified duration</span></span>
<span data-ttu-id="89fe5-159"><a name="sectionSection4"> </a></span><span class="sxs-lookup"><span data-stu-id="89fe5-159"></span></span>

<span data-ttu-id="89fe5-p114">Su organización puede necesitar que los datos de todos los buzones se conserven durante un período determinado. Antes de colocar todos los buzones de una organización en retención por juicio, tenga en cuenta lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="89fe5-p114">Your organization may require that all mailbox data be preserved for a specific period of time. Before you place all mailboxes in an organization on Litigation Hold, consider the following:</span></span>
  
<span data-ttu-id="89fe5-162">En este ejemplo todos los buzones de usuario de la organización se colocan en retención por juicio durante un año (365 días).</span><span class="sxs-lookup"><span data-stu-id="89fe5-162">This example places all user mailboxes in the organization on Litigation Hold for one year (365 days).</span></span>
  
```
Get-Mailbox -ResultSize Unlimited -Filter {RecipientTypeDetails -eq "UserMailbox"} | Set-Mailbox -LitigationHoldEnabled $true -LitigationHoldDuration 365
```

<span data-ttu-id="89fe5-163">El ejemplo usa el cmdlet [Get-Mailbox](http://technet.microsoft.com/library/8a5a6eb9-4a75-47f9-ae3b-a3ba251cf9a8.aspx) para recuperar todos los buzones de la organización, especifica un filtro de destinatarios para incluir todos los buzones de usuario y, después, canaliza la lista de buzones al cmdlet [Set-Mailbox](http://technet.microsoft.com/library/a0d413b9-d949-4df6-ba96-ac0906dedae2.aspx) para habilitar la retención por juicio y la duración de la retención.</span><span class="sxs-lookup"><span data-stu-id="89fe5-163">The example uses the [Get-Mailbox](http://technet.microsoft.com/library/8a5a6eb9-4a75-47f9-ae3b-a3ba251cf9a8.aspx) cmdlet to retrieve all mailboxes in the organization, specifies a recipient filter to include all user mailboxes, and then pipes the list of mailboxes to the [Set-Mailbox](http://technet.microsoft.com/library/a0d413b9-d949-4df6-ba96-ac0906dedae2.aspx) cmdlet to enable the Litigation Hold and hold duration.</span></span> 
  
<span data-ttu-id="89fe5-164">Para colocar todos los buzones de usuario en una retención indefinida, ejecute el comando anterior pero no incluya el parámetro  _LitigationHoldDuration_.</span><span class="sxs-lookup"><span data-stu-id="89fe5-164">To place all user mailboxes on an indefinite hold, run the previous command but don't include the  _LitigationHoldDuration_ parameter.</span></span> 
  
<span data-ttu-id="89fe5-165">Consulte la sección [Más información](#moreinfo.md) para ver ejemplos de cómo usar otras propiedades de destinatarios en un filtro para incluir o excluir uno o más buzones.</span><span class="sxs-lookup"><span data-stu-id="89fe5-165">See the [More information](#moreinfo.md) section for examples of using other recipient properties in a filter to include or exclude one or more mailboxes.</span></span> 
  
## <a name="use-the-shell-to-remove-a-mailbox-from-litigation-hold"></a><span data-ttu-id="89fe5-166">Usar el Shell para quitar un buzón de la retención por juicio</span><span class="sxs-lookup"><span data-stu-id="89fe5-166">Use the Shell to remove a mailbox from Litigation Hold</span></span>
<span data-ttu-id="89fe5-167"><a name="sectionSection5"> </a></span><span class="sxs-lookup"><span data-stu-id="89fe5-167"></span></span>

<span data-ttu-id="89fe5-168">En este ejemplo, se quita el buzón de correo bsuneja@contoso.com de la retención por juicio.</span><span class="sxs-lookup"><span data-stu-id="89fe5-168">This example removes the mailbox bsuneja@contoso.com from Litigation Hold.</span></span>
  
```
Set-Mailbox bsuneja@contoso.com -LitigationHoldEnabled $false
```

<span data-ttu-id="89fe5-169">P</span><span class="sxs-lookup"><span data-stu-id="89fe5-169">P</span></span>
## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="89fe5-170">¿Cómo saber si el proceso se ha completado correctamente?</span><span class="sxs-lookup"><span data-stu-id="89fe5-170">How do you know this worked?</span></span>
<span data-ttu-id="89fe5-171"><a name="sectionSection6"> </a></span><span class="sxs-lookup"><span data-stu-id="89fe5-171"></span></span>

<span data-ttu-id="89fe5-172">Para comprobar que un buzón se ha colocado correctamente en retención por juicio, realice unas de estas acciones:</span><span class="sxs-lookup"><span data-stu-id="89fe5-172">To verify that you have successfully placed a mailbox on Litigation Hold, do the one of the following:</span></span>
  
- <span data-ttu-id="89fe5-173">En el EAC:</span><span class="sxs-lookup"><span data-stu-id="89fe5-173">In the EAC:</span></span>
    
1. <span data-ttu-id="89fe5-174">Vaya a **Destinatarios** \> **Buzones de correo**.</span><span class="sxs-lookup"><span data-stu-id="89fe5-174">Go to **Recipients** \> **Mailboxes**.</span></span>
    
2. <span data-ttu-id="89fe5-175">En la lista de buzones de usuario, haga clic en el buzón de correo que se va a comprobar la configuración de la suspensión por litigio para y, a continuación, haga clic en **Editar** ![icono Editar](media/ITPro-EAC-EditIcon.gif).</span><span class="sxs-lookup"><span data-stu-id="89fe5-175">In the list of user mailboxes, click the mailbox that you want to verify Litigation Hold settings for, and then click **Edit** ![Edit icon](media/ITPro-EAC-EditIcon.gif).</span></span>
    
3. <span data-ttu-id="89fe5-176">En la página de propiedades del buzón de correo, haga clic en **características de buzón.**</span><span class="sxs-lookup"><span data-stu-id="89fe5-176">On the mailbox properties page, click **Mailbox features.**</span></span>
    
4. <span data-ttu-id="89fe5-177">En **Retención por juicio**, compruebe que la retención está habilitada.</span><span class="sxs-lookup"><span data-stu-id="89fe5-177">Under **Litigation hold**, verify that hold is enabled.</span></span>
    
5. <span data-ttu-id="89fe5-p115">Haga clic en **Ver detalles** para comprobar cuándo se colocó el buzón en retención por juicio y quién lo hizo. También puede comprobar o cambiar los valores de las casillas opcionales **Duración de retención por juicio (días)**, **Nota** y **Dirección URL**.</span><span class="sxs-lookup"><span data-stu-id="89fe5-p115">Click **View details** to verify when the mailbox was placed on Litigation Hold and by whom. You can also verify or change the values in the optional **Litigation hold duration (days)**, **Note**, and **URL** boxes.</span></span> 
    
- <span data-ttu-id="89fe5-180">En el Shell, ejecute uno de los siguientes comandos:</span><span class="sxs-lookup"><span data-stu-id="89fe5-180">In the Shell, run one of the following commands:</span></span>
    
  ```
  Get-Mailbox <name of mailbox> | FL LitigationHold*
  ```

    <span data-ttu-id="89fe5-181">o</span><span class="sxs-lookup"><span data-stu-id="89fe5-181">or</span></span>
    
  ```
  Get-Mailbox -ResultSize Unlimited -Filter {RecipientTypeDetails -eq "UserMailbox"} | FL Name,LitigationHold*
  ```

    <span data-ttu-id="89fe5-182">Si un buzón se coloca en retención por juicio indefinidamente, el valor de la propiedad del buzón  _LitigationHoldDuration_ se establece en  `Unlimited`.</span><span class="sxs-lookup"><span data-stu-id="89fe5-182">If a mailbox is placed on Litigation Hold indefinitely, the value for the  _LitigationHoldDuration_ property mailbox is set to  `Unlimited`.</span></span>
    
## <a name="more-information"></a><span data-ttu-id="89fe5-183">Más información</span><span class="sxs-lookup"><span data-stu-id="89fe5-183">More information</span></span>
<span data-ttu-id="89fe5-184"><a name="moreinfo"> </a></span><span class="sxs-lookup"><span data-stu-id="89fe5-184"></span></span>

- <span data-ttu-id="89fe5-185">Si su organización requiere que los datos de todos los buzones se conserven durante un período de tiempo específico, considere lo siguiente antes de poner todos los buzones de una organización en retención por juicio.</span><span class="sxs-lookup"><span data-stu-id="89fe5-185">If your organization requires that all mailbox data has to preserved for a specific period of time, consider the following before you place all mailboxes in an organization on Litigation Hold.</span></span>
    
  - <span data-ttu-id="89fe5-p116">Cuando se usa el comando anterior para aplicar una retención a todos los buzones de una organización (o a un subconjunto de buzones que coinciden con un filtro de destinatarios especificado), solo se retienen los buzones que existen en el momento en que se ejecuta el comando. Si crea nuevos buzones más adelante, tiene que ejecutar el comando de nuevo para poner los nuevos buzones en retención. Si crea nuevos buzones con frecuencia, puede ejecutar el comando como una tarea programada con la frecuencia que necesite.</span><span class="sxs-lookup"><span data-stu-id="89fe5-p116">When you use the previous command to place a hold on all mailboxes in an organization (or a subset of mailboxes matching a specified recipient filter) only mailboxes that exist at the time that you run the command are placed on hold. If you create new mailboxes later, you have to run the command again to place the new mailboxes on hold. If you create new mailboxes often, you can run the command as a scheduled task as frequently as required.</span></span>
    
  - <span data-ttu-id="89fe5-p117">Poner todos los buzones en suspensión por litigio puede afectar significativamente al tamaño de los buzones. En una organización de Exchange Server 2013, planeación de almacenamiento suficiente satisfacer los requisitos de conservación de la organización.</span><span class="sxs-lookup"><span data-stu-id="89fe5-p117">Placing all mailboxes on Litigation Hold can significantly impact mailbox sizes. In an Exchange Server 2013 organization, plan for adequate storage to meet your organization's preservation requirements.</span></span>
    
  - <span data-ttu-id="89fe5-p118">La carpeta elementos recuperables tiene su propio límite de almacenamiento, por lo que los elementos de la carpeta no se cuentan para el límite de almacenamiento de buzones de correo. Como se explica anteriormente, conservar los datos de buzón de correo durante un largo período de tiempo se de crecimiento de la carpeta elementos recuperables en el buzón del usuario y archivar. Para dar cabida a este aumento en Exchange Online, la cuota de la carpeta elementos recuperables se incrementa automáticamente de 30 GB a 100 GB cuando se coloca un buzón en suspensión por litigio.</span><span class="sxs-lookup"><span data-stu-id="89fe5-p118">The Recoverable Items folder has its own storage limit, so items in the folder don't count towards the mailbox storage limit. As previously explained, preserving mailbox data for a long period of time will result in growth of the Recoverable Items folder in a user's mailbox and archive. To accommodate for this increase in Exchange Online, the quota for the Recoverable Items folder is automatically increased from 30 GB to 100 GB when you place a mailbox on Litigation Hold.</span></span> 
    
    <span data-ttu-id="89fe5-p119">En Exchange Server 2013, el límite de almacenamiento predeterminada para la carpeta elementos recuperables también es de 30 GB. Se recomienda que supervisar periódicamente el tamaño de esta carpeta para asegurarse de que no llega al límite. Para obtener más información, vea [Carpeta elementos recuperables](http://technet.microsoft.com/library/efc48fb4-2ed8-4d05-93af-f3505fbc389d.aspx).</span><span class="sxs-lookup"><span data-stu-id="89fe5-p119">In Exchange Server 2013, the default storage limit for the Recoverable Items folder is also 30 GB. We recommend that you periodically monitor the size of this folder to ensure it doesn't reach the limit. For more information, see [Recoverable Items Folder](http://technet.microsoft.com/library/efc48fb4-2ed8-4d05-93af-f3505fbc389d.aspx).</span></span>
    
- <span data-ttu-id="89fe5-p120">El comando anterior para colocar una retención en todos los buzones utiliza un filtro de destinatarios que devuelve todos los buzones de usuario. Puede usar otras propiedades de destinatarios para devolver una lista de buzones específicos que puede canalizar después al cmdlet **Set-Mailbox** para poner esos buzones en retención por juicio.</span><span class="sxs-lookup"><span data-stu-id="89fe5-p120">The previous command to place a hold on all mailboxes uses a recipient filter that returns all user mailboxes. You can use other recipient properties to return a list of specific mailboxes that you can then pipe to the **Set-Mailbox** cmdlet to place a Litigation Hold on those mailboxes.</span></span> 
    
    <span data-ttu-id="89fe5-p121">Estos son algunos ejemplos de cómo usar los cmdlets **Get-Mailbox** y **Get-Recipient** para obtener un subconjunto de buzones en función de propiedades de usuarios o buzones. En estos ejemplos se da por hecho que las propiedades de buzón relevantes (como  _CustomAttributeN_ o  _Department_) se han rellenado.</span><span class="sxs-lookup"><span data-stu-id="89fe5-p121">Here are some examples of using the **Get-Mailbox** and **Get-Recipient** cmdlets to return a subset of mailboxes based on common user or mailbox properties. These examples assume that relevant mailbox properties (such as  _CustomAttributeN_ or  _Department_) have been populated.</span></span>
    
  ```
  Get-Mailbox -RecipientTypeDetails UserMailbox -ResultSize unlimited -Filter 'CustomAttribute15 -eq "OneYearLitigationHold"'
  ```

  ```
  Get-Recipient -RecipientTypeDetails UserMailbox -ResultSize unlimited -Filter 'Department -eq "HR"'
  ```

  ```
  Get-Recipient -RecipientTypeDetails UserMailbox -ResultSize unlimited -Filter 'PostalCode -eq "98052"'
  ```

  ```
  Get-Recipient -RecipientTypeDetails UserMailbox -ResultSize unlimited -Filter 'StateOrProvince -eq "WA"'
  ```

  ```
  Get-Mailbox -ResultSize Unlimited -Filter {RecipientTypeDetails -ne "DiscoveryMailbox"}
  ```

    <span data-ttu-id="89fe5-p122">Puede usar otras propiedades de buzón de usuario en un filtro para incluir o excluir buzones de correo. Para obtener información detallada, vea [Filterable Properties for the -Filter Parameter](http://technet.microsoft.com/library/b02b0005-2fb6-4bc2-8815-305259fa5432.aspx).</span><span class="sxs-lookup"><span data-stu-id="89fe5-p122">You can use other user mailbox properties in a filter to include or exclude mailboxes. For details, see [Filterable Properties for the -Filter Parameter](http://technet.microsoft.com/library/b02b0005-2fb6-4bc2-8815-305259fa5432.aspx).</span></span>
    

