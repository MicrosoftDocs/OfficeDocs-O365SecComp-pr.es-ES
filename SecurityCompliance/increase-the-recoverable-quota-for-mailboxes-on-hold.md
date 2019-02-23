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
# <a name="increase-the-recoverable-items-quota-for-mailboxes-on-hold"></a><span data-ttu-id="5f8bf-103">Aumentar la cuota de elementos recuperables para los buzones de correo en retención</span><span class="sxs-lookup"><span data-stu-id="5f8bf-103">Increase the Recoverable Items quota for mailboxes on hold</span></span>

<span data-ttu-id="5f8bf-p101">La Directiva de retención predeterminada, denominada Directiva de MRM predeterminada, que se aplica automáticamente a los nuevos buzones de correo de Exchange Online contiene una etiqueta de retención denominada elementos recuperables de 14 días para mover a archivo. Esta etiqueta de retención mueve los elementos de la carpeta elementos recuperables del buzón de correo principal del usuario a la carpeta elementos recuperables del buzón de archivo del usuario después de que expire el período de retención de 14 días de un elemento. Para que esto suceda, debe estar habilitado el buzón de archivo del usuario. Si el buzón de archivo no está habilitado, no se realiza ninguna acción, lo que significa que los elementos de la carpeta elementos recuperables de un buzón en retención no se mueven al buzón de archivo después de que expire el período de retención de 14 días. Como no se elimina nada de un buzón de correo en suspensión, es posible que se supere la cuota de almacenamiento de la carpeta elementos recuperables, especialmente si el buzón de archivo del usuario no está habilitado.</span><span class="sxs-lookup"><span data-stu-id="5f8bf-p101">The default retention policy—named Default MRM Policy—that is automatically applied to new mailboxes in Exchange Online contains a retention tag named Recoverable Items 14 days move to archive. This retention tag moves items from the Recoverable Items folder in the user's primary mailbox to the Recoverable Items folder in the user's archive mailbox after the 14-day retention period expires for an item. For this to happen, the user's archive mailbox must be enabled. If the archive mailbox isn't enabled, no action is taken, which means that items in the Recoverable Items folder for a mailbox on hold aren't moved to the archive mailbox after the 14-day retention period expires. Because nothing is deleted from a mailbox on hold, it's possible that the storage quota for the Recoverable Items folder might be exceeded, especially if the user's archive mailbox isn't enabled.</span></span> 
  
<span data-ttu-id="5f8bf-p102">Para ayudar a reducir la posibilidad de superar este límite, la cuota de almacenamiento de la carpeta elementos recuperables aumenta automáticamente de 30 GB a 100 GB cuando se coloca una retención en un buzón de correo en Exchange Online. Si el buzón de archivo está habilitado, la cuota de almacenamiento de la carpeta elementos recuperables del buzón de archivo también aumenta de 30 GB a 100 GB. Si la característica de archivado de ampliación automática en Exchange Online está habilitada, la cuota de almacenamiento de la carpeta elementos recuperables del archivo del usuario será ilimitada.</span><span class="sxs-lookup"><span data-stu-id="5f8bf-p102">To help reduce the chance of exceeding this limit, the storage quota for the Recoverable Items folder is automatically increased from 30 GB to 100 GB when a hold is placed on a mailbox in Exchange Online. If the archive mailbox is enabled, the storage quota for the Recoverable Items folder in the archive mailbox is also increased from 30 GB to 100 GB. If the auto-expanding archiving feature in Exchange Online is enabled, the storage quota for the Recoverable Items folder in the user's archive will be unlimited.</span></span>
  
 <span data-ttu-id="5f8bf-112"> En la tabla siguiente se resume la cuota de almacenamiento de la carpeta Elementos recuperables.</span><span class="sxs-lookup"><span data-stu-id="5f8bf-112">The following table summarizes the storage quota for the Recoverable Items folder.</span></span> 
  
|<span data-ttu-id="5f8bf-113">**Ubicación de la carpeta Elementos recuperables**</span><span class="sxs-lookup"><span data-stu-id="5f8bf-113">**Location of Recoverable Items folder**</span></span>|<span data-ttu-id="5f8bf-114">**Buzones que no están en suspensión**</span><span class="sxs-lookup"><span data-stu-id="5f8bf-114">**Mailboxes not on hold**</span></span>|<span data-ttu-id="5f8bf-115">**Buzones en suspensión**</span><span class="sxs-lookup"><span data-stu-id="5f8bf-115">**Mailboxes on hold**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="5f8bf-116">Buzón principal</span><span class="sxs-lookup"><span data-stu-id="5f8bf-116">Primary mailbox</span></span>  <br/> |<span data-ttu-id="5f8bf-117">30 GB</span><span class="sxs-lookup"><span data-stu-id="5f8bf-117">30 GB</span></span>  <br/> |<span data-ttu-id="5f8bf-118">100 GB</span><span class="sxs-lookup"><span data-stu-id="5f8bf-118">100 GB</span></span>  <br/> |
|<span data-ttu-id="5f8bf-119">Buzón de archivo<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="5f8bf-119">Archive mailbox<sup>\*</sup></span></span> <br/> |<span data-ttu-id="5f8bf-120">Ilimitado</span><span class="sxs-lookup"><span data-stu-id="5f8bf-120">Unlimited</span></span>  <br/> |<span data-ttu-id="5f8bf-121">Ilimitado</span><span class="sxs-lookup"><span data-stu-id="5f8bf-121">Unlimited</span></span>  <br/> |
|<span data-ttu-id="5f8bf-122">**Cuota de almacenamiento total de la carpeta Elementos recuperables**</span><span class="sxs-lookup"><span data-stu-id="5f8bf-122">**Total storage quota for the Recoverable Items folder**</span></span> <br/> |<span data-ttu-id="5f8bf-123">Ilimitado</span><span class="sxs-lookup"><span data-stu-id="5f8bf-123">Unlimited</span></span>  <br/> |<span data-ttu-id="5f8bf-124">Ilimitado</span><span class="sxs-lookup"><span data-stu-id="5f8bf-124">Unlimited</span></span>  <br/> |
   
> [!NOTE]
> <span data-ttu-id="5f8bf-p103"><sup>\*</sup>La cuota de almacenamiento inicial para el buzón de archivo es de 100 GB para los usuarios con una licencia de Exchange Online (plan 2). Sin embargo, cuando el archivado de expansión automática está activado para buzones en retención, la cuota de almacenamiento para el buzón de archivo y la carpeta elementos recuperables aumenta a 110 GB. El espacio de almacenamiento de archivo adicional se aprovisionará cuando sea necesario, lo que da como resultado una cantidad ilimitada de almacenamiento de archivo. Para obtener más información acerca del archivado de expansión automática, vea [información general sobre el archivado ilimitado en Office 365](unlimited-archiving.md).</span><span class="sxs-lookup"><span data-stu-id="5f8bf-p103"><sup>\*</sup> The initial storage quota for the archive mailbox is 100 GB for users with an Exchange Online (Plan 2) license. However, when auto-expanding archiving is turned on for mailboxes on hold, the storage quota for both the archive mailbox and the Recoverable Items folder is increased to 110 GB. Additional archive storage space will be provisioned when necessary which results in an unlimited amount of archive storage. For more information about auto-expanding archiving, see [Overview of unlimited archiving in Office 365](unlimited-archiving.md).</span></span> 
  
<span data-ttu-id="5f8bf-129">Cuando la cuota de almacenamiento de la carpeta Elementos recuperables en el buzón principal de un buzón en suspensión está a punto de alcanzar su límite, puede hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="5f8bf-129">When the storage quota for the Recoverable Items folder in the primary mailbox of a mailbox on hold is close to reaching its limit, you can do the following things:</span></span>
  
- <span data-ttu-id="5f8bf-p104">**Habilitar el buzón de archivo y activar el archivado de expansión automática** : puede habilitar una capacidad de almacenamiento ilimitada para la carpeta elementos recuperables con tan solo habilitar el buzón de archivo y, a continuación, activar la característica de archivado de ampliación automática en Exchange. Online. Esto da como resultado 110 GB para la carpeta elementos recuperables en el buzón principal y una cantidad ilimitada de capacidad de almacenamiento para la carpeta elementos recuperables del archivo del usuario. Vea cómo: [Habilitar buzones de archivo en el centro de &amp; seguridad y cumplimiento de Office 365](enable-archive-mailboxes.md) y [Habilitar el archivado ilimitado en Office 365](enable-unlimited-archiving.md).</span><span class="sxs-lookup"><span data-stu-id="5f8bf-p104">**Enable the archive mailbox and turn on auto-expanding archiving** - You can enable an unlimited storage capacity for the Recoverable Items folder simply by enabling the archive mailbox and then turning on the auto-expanding archiving feature in Exchange Online. This results in 110 GB for the Recoverable Items folder in the primary mailbox and an unlimited amount of storage capacity for the Recoverable Items folder in the user's archive. See how: [Enable archive mailboxes in the Office 365 Security &amp; Compliance Center](enable-archive-mailboxes.md) and [Enable unlimited archiving in Office 365](enable-unlimited-archiving.md).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="5f8bf-p105">Después de habilitar el archivo para un buzón que está a punto de superar la cuota de almacenamiento de la carpeta elementos recuperables, es posible que desee ejecutar el Asistente para carpeta administrada para desencadenar manualmente el Asistente para procesar el buzón de modo que los elementos expirados se muevan Carpeta elementos recuperables en el buzón de archivo. Consulte el [paso 4](#optional-step-4-run-the-managed-folder-assistant-to-apply-the-new-retention-settings) para obtener instrucciones. Tenga en cuenta que es posible que se muevan otros elementos del buzón del usuario al nuevo buzón de archivo. Considere la posibilidad de que se indique al usuario que esto puede ocurrir después de habilitar el buzón de archivo.</span><span class="sxs-lookup"><span data-stu-id="5f8bf-p105">After you enable the archive for a mailbox that's close to exceeding the storage quota for the Recoverable Items folder, you might want to run the Managed Folder Assistant to manually trigger the assistant to process the mailbox so that expired items are moved the Recoverable Items folder in the archive mailbox. See [Step 4](#optional-step-4-run-the-managed-folder-assistant-to-apply-the-new-retention-settings) for instructions. Note that other items in the user's mailbox might be moved to the new archive mailbox. Consider telling the user that this may happen after you enable the archive mailbox.</span></span> 
  
- <span data-ttu-id="5f8bf-p106">**Crear una directiva de retención personalizada para buzones de correo en** retención: además de habilitar el buzón de archivo y el archivado de expansión automática para buzones en retención por juicio o conservación local, es posible que también desee crear una directiva de retención personalizada para los buzones de correo en retención. Esto le permite aplicar una directiva de retención a los buzones de correo en retención que es diferente de la Directiva de MRM predeterminada que se aplica a los buzones que no están en suspensión. Esto le permite aplicar etiquetas de retención que se han diseñado específicamente para buzones de correo en retención. Esto incluye la creación de una nueva etiqueta de retención para la carpeta elementos recuperables.</span><span class="sxs-lookup"><span data-stu-id="5f8bf-p106">**Create a custom retention policy for mailboxes on hold** - In addition to enabling the archive mailbox and auto-expanding archiving for mailboxes on Litigation Hold or In-Place Hold, you might also want to create a custom retention policy for mailboxes on hold. This let's you apply a retention policy to mailboxes on hold that's different from the Default MRM Policy that's applied to mailboxes that aren't on hold. This lets you to apply retention tags that are specifically designed for mailboxes on hold. This includes creating a new retention tag for the Recoverable Items folder.</span></span> 
    
<span data-ttu-id="5f8bf-141">En el resto de este tema se describen procedimientos paso a paso para crear una directiva de retención personalizada para los buzones en suspensión.</span><span class="sxs-lookup"><span data-stu-id="5f8bf-141">The remainder of this topic describes the step-by-step procedures to create a custom retention policy for mailboxes on hold.</span></span>
  
[<span data-ttu-id="5f8bf-142">Paso 1: Crear una etiqueta de retención personalizada para la carpeta Elementos recuperables</span><span class="sxs-lookup"><span data-stu-id="5f8bf-142">Step 1: Create a custom retention tag for the Recoverable Items folder</span></span>](#step-1-create-a-custom-retention-tag-for-the-recoverable-items-folder)

<span data-ttu-id="5f8bf-143">[[Paso 2: crear una nueva Directiva de retención para buzones en retención](#step-2-create-a-new-retention-policy-for-mailboxes-on-hold)</span><span class="sxs-lookup"><span data-stu-id="5f8bf-143">[[Step 2: Create a new retention policy for mailboxes on hold](#step-2-create-a-new-retention-policy-for-mailboxes-on-hold)</span></span>

[<span data-ttu-id="5f8bf-144">Paso 3: Aplicar la nueva directiva de retención a buzones de correo en suspensión</span><span class="sxs-lookup"><span data-stu-id="5f8bf-144">Step 3: Apply the new retention policy to mailboxes on hold</span></span>](#step-3-apply-the-new-retention-policy-to-mailboxes-on-hold)

[<span data-ttu-id="5f8bf-145">Paso 4 (opcional): Ejecutar el Asistente para carpeta administrada para aplicar la nueva configuración de retención</span><span class="sxs-lookup"><span data-stu-id="5f8bf-145">(Optional) Step 4: Run the Managed Folder Assistant to apply the new retention settings</span></span>](#optional-step-4-run-the-managed-folder-assistant-to-apply-the-new-retention-settings)
  
## <a name="step-1-create-a-custom-retention-tag-for-the-recoverable-items-folder"></a><span data-ttu-id="5f8bf-146">Paso 1: Crear una etiqueta de retención personalizada para la carpeta Elementos recuperables</span><span class="sxs-lookup"><span data-stu-id="5f8bf-146">Step 1: Create a custom retention tag for the Recoverable Items folder</span></span>

<span data-ttu-id="5f8bf-p107">El primer paso consiste en crear una etiqueta de retención personalizada (denominada "etiqueta de directiva de retención" o "RPT") para la carpeta elementos recuperables. Como se explicó anteriormente, esta RPT mueve los elementos de la carpeta elementos recuperables del buzón de correo principal del usuario a la carpeta elementos recuperables del buzón de archivo del usuario. Debe usar PowerShell para crear una RPT para la carpeta elementos recuperables. No puede usar el centro de administración de Exchange (EAC).</span><span class="sxs-lookup"><span data-stu-id="5f8bf-p107">The first step is to create a custom retention tag (called a retention policy tag or RPT) for the Recoverable Items folder. As previously explained, this RPT moves items from the Recoverable Items folder in the user's primary mailbox to the Recoverable Items folder in the user's archive mailbox. You have to use PowerShell to create an RPT for the Recoverable Items folder. You can't use the Exchange admin center (EAC).</span></span> 
  
1. [<span data-ttu-id="5f8bf-151">Conectarse a Exchange Online con el PowerShell remoto</span><span class="sxs-lookup"><span data-stu-id="5f8bf-151">Connect to Exchange Online using remote PowerShell</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=517283)
    
2. <span data-ttu-id="5f8bf-152">Ejecute el comando siguiente para crear una RPT para la carpeta Elementos recuperables: </span><span class="sxs-lookup"><span data-stu-id="5f8bf-152">Run the following command to create a new RPT for the Recoverable Items folder:</span></span> 
    
    ```
    New-RetentionPolicyTag -Name <Name of RPT> -Type RecoverableItems -AgeLimitForRetention <Number of days> -RetentionAction MoveToArchive
    ```

    <span data-ttu-id="5f8bf-p108">Por ejemplo, el comando siguiente crea una RPT para la carpeta Elementos recuperables denominada "30 días en Elementos recuperables para buzones en suspensión", con un período de retención de 30 días. Esto significa que, una vez que un elemento haya estado en la carpeta Elementos recuperables durante 30 días, se moverá a la carpeta Elementos recuperables del buzón de archivo del usuario.</span><span class="sxs-lookup"><span data-stu-id="5f8bf-p108">For example, the following command creates a RPT for the Recoverable Items folder named "Recoverable Items 30 days for mailboxes on hold", with a retention period of 30 days. This means that after an item has been in the Recoverable Items folder for 30 days, it will be moved to the Recoverable Items folder in the user's archive mailbox.</span></span>
    
    ```
    New-RetentionPolicyTag -Name "Recoverable Items 30 days for mailboxes on hold" -Type RecoverableItems -AgeLimitForRetention 30 -RetentionAction MoveToArchive
    ```

    > [!TIP]
    > <span data-ttu-id="5f8bf-p109">Se recomienda que el período de retención (definido por el parámetro _AgeLimitForRetention_ ) para la RPT de elementos recuperables sea el mismo que el período de retención de elementos eliminados para los buzones de correo a los que se aplicará el RPT. Esto permite a un usuario todo el período de retención de elementos eliminados para recuperar los elementos eliminados antes de que se muevan al buzón de archivo. En el ejemplo anterior, el período de retención se estableció en 30 días en función de la hipótesis de que el período de retención de elementos eliminados para los buzones de correo es también de 30 días. De forma predeterminada, se configura un buzón de correo de Exchange Online para conservar los elementos eliminados durante 14 días. Pero puede cambiar esta configuración a un máximo de 30 días. Para obtener más información, vea [cambiar el período de retención de elementos eliminados para un buzón de correo en Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=286940).</span><span class="sxs-lookup"><span data-stu-id="5f8bf-p109">We recommend that the retention period (defined by the  _AgeLimitForRetention_ parameter) for the Recoverable Items RPT is the same as the deleted item retention period for the mailboxes that the RPT will be applied to. This allows a user the entire deleted item retention period to recover deleted items before they are moved to the archive mailbox. In the previous example, the retention period was set to 30 days based on the assumption that the deleted item retention period for mailboxes is also 30 days. An Exchange Online mailbox is configured to retain deleted items for 14 days, by default. But you can change this setting to a maximum of 30 days. For more information, see [Change the deleted item retention period for a mailbox in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=286940).</span></span> 
  
## <a name="step-2-create-a-new-retention-policy-for-mailboxes-on-hold"></a><span data-ttu-id="5f8bf-161">Paso 2: Crear una directiva de retención para buzones de correo en suspensión</span><span class="sxs-lookup"><span data-stu-id="5f8bf-161">Step 2: Create a new retention policy for mailboxes on hold</span></span>

<span data-ttu-id="5f8bf-p110">El siguiente paso consiste en crear una directiva de retención y agregarle etiquetas de retención, incluida la RPT de Elementos recuperables que creó en el paso 1. Esta nueva directiva se aplicará a los buzones de correo en suspensión en el paso siguiente. </span><span class="sxs-lookup"><span data-stu-id="5f8bf-p110">The next step is to create a new retention policy and add retention tags to it, including the Recoverable Items RPT that you created in Step 1. This new policy will be applied to mailboxes on hold in the next step.</span></span> 
  
<span data-ttu-id="5f8bf-p111">Antes de crear la directiva de retención, determine las etiquetas de retención adicionales que quiere agregar. Para obtener una lista de las etiquetas de retención que se agregan a la directiva de MRM predeterminada y para obtener información sobre cómo crear etiquetas de retención, vea lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="5f8bf-p111">Before you create the new retention policy, determine the additional retention tags that you want to add. For a list of the retention tags that are added to the Default MRM Policy and for information about creating new retention tags, see the following:</span></span>
  
- [<span data-ttu-id="5f8bf-166">Directiva de retención predeterminada en Exchange Online</span><span class="sxs-lookup"><span data-stu-id="5f8bf-166">Default Retention Policy in Exchange Online </span></span>](https://go.microsoft.com/fwlink/p/?LinkId=746954)
    
- [<span data-ttu-id="5f8bf-167">Carpetas predeterminadas que admiten etiquetas de la directiva de retención</span><span class="sxs-lookup"><span data-stu-id="5f8bf-167">Default folders that support Retention Policy Tags</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=746957)
    
- <span data-ttu-id="5f8bf-168">La sección "crear una etiqueta de retención" en el tema [Create a Retention Policy](https://go.microsoft.com/fwlink/p/?LinkId=404422) .</span><span class="sxs-lookup"><span data-stu-id="5f8bf-168">The "Create a retention tag" section in the [Create a Retention Policy](https://go.microsoft.com/fwlink/p/?LinkId=404422) topic.</span></span>
    
<span data-ttu-id="5f8bf-169">Puede usar el EAC o Exchange Online PowerShell para crear una directiva de retención.</span><span class="sxs-lookup"><span data-stu-id="5f8bf-169">You can use the EAC or Exchange Online PowerShell to create a retention policy.</span></span>
  
### <a name="use-the-eac-to-create-a-retention-policy"></a><span data-ttu-id="5f8bf-170">Uso de EAC para crear una directiva de retención</span><span class="sxs-lookup"><span data-stu-id="5f8bf-170">Use the EAC to create a retention policy</span></span>
  
1. <span data-ttu-id="5f8bf-171">En el EAC, vaya a \*\*\*\* \> **directivas de retención**de administración de cumplimiento y, a continuación](media/ITPro-EAC-AddIcon.gif), haga clic en **Agregar** ![icono de agregar.</span><span class="sxs-lookup"><span data-stu-id="5f8bf-171">In the EAC, go to **Compliance management** \> **Retention policies**, and then click **Add** ![Add Icon](media/ITPro-EAC-AddIcon.gif).</span></span>
    
2. <span data-ttu-id="5f8bf-172">En la página **Nueva directiva de retención**, en **Nombre**, escriba un nombre que describa el propósito de la directiva, como **MRM Policy for Mailboxes on Hold** (Directiva de MRM para buzones de correo en suspensión). </span><span class="sxs-lookup"><span data-stu-id="5f8bf-172">On the **New retention policy** page, under **Name**, type a name that describes the purpose of the retention policy; for example, **MRM Policy for Mailboxes on Hold**.</span></span> 
    
3. <span data-ttu-id="5f8bf-173">En **etiquetas de retención**, haga clic en](media/ITPro-EAC-AddIcon.gif) **Agregar** ![icono de agregar.</span><span class="sxs-lookup"><span data-stu-id="5f8bf-173">Under **Retention tags**, click **Add** ![Add Icon](media/ITPro-EAC-AddIcon.gif).</span></span>
    
4. <span data-ttu-id="5f8bf-174">En la lista de etiquetas de retención, seleccione la RPT de Elementos recuperables que ha creado en el paso 1 y, después, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="5f8bf-174">In the list of retention tags, select the Recoverable Items RPT that you created in Step 1, and then click **Add**.</span></span>
    
    ![Seleccione la etiqueta de retención personalizada Elementos recuperables](media/eb49866b-bdef-4fcd-a6d9-01607c01249b.png)
  
5. <span data-ttu-id="5f8bf-p112">Seleccione las etiquetas de retención adicionales que quiera agregar a la directiva de retención. Por ejemplo, podría interesarle agregar las mismas etiquetas que se incluyen en la directiva de MRM predeterminada.</span><span class="sxs-lookup"><span data-stu-id="5f8bf-p112">Select additional retention tags to add to the retention policy. For example, you might want to add the same tags that are included in the Default MRM Policy.</span></span>
    
6. <span data-ttu-id="5f8bf-178">Cuando termine de agregar reglas de retención, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="5f8bf-178">When you're finished adding retention tags, click **OK**.</span></span>
    
7. <span data-ttu-id="5f8bf-179">Haga clic en **Guardar** para crear la directiva de retención.</span><span class="sxs-lookup"><span data-stu-id="5f8bf-179">Click **Save** to create the new retention policy.</span></span> 
    
    <span data-ttu-id="5f8bf-180">Observe que las etiquetas de retención vinculadas a la directiva de retención se muestran en el panel de detalles</span><span class="sxs-lookup"><span data-stu-id="5f8bf-180">Notice that the retention tags linked to the retention policy are displayed in the details pane.</span></span>
    
    ![Las etiquetas de retención vinculadas a la directiva de retención se muestran en el panel de detalles](media/dad1c8f4-9928-4d6d-991a-6f6c5194eceb.png)
  
### <a name="use-exchange-online-powershell-to-create-a-retention-policy"></a><span data-ttu-id="5f8bf-182">Usar Exchange Online PowerShell para crear una directiva de retención</span><span class="sxs-lookup"><span data-stu-id="5f8bf-182">Use Exchange Online PowerShell to create a retention policy</span></span>
  
<span data-ttu-id="5f8bf-183">Ejecute el comando siguiente para crear una directiva de retención para buzones en suspensión. </span><span class="sxs-lookup"><span data-stu-id="5f8bf-183">Run the following command to create new retention policy for mailboxes on hold.</span></span> 
  
```
New-RetentionPolicy <Name of retention policy>  -RetentionPolicyTagLinks <list of retention tags>

```

<span data-ttu-id="5f8bf-184">Por ejemplo, el comando siguiente crea la directiva de retención y las etiquetas de retención vinculadas que se muestran en la ilustración anterior.</span><span class="sxs-lookup"><span data-stu-id="5f8bf-184">For example, the following command creates the retention policy and linked retention tags that is displayed in the previous illustration.</span></span>
  
```
New-RetentionPolicy "MRM Policy for Mailboxes on Hold"  -RetentionPolicyTagLinks "Recoverable Items 30 days for mailboxes on hold","1 Month Delete","1 Week Delete","1 Year Delete","5 Year Delete","6 Month Delete","Default 2 year move to archive","Junk Email","Never Delete","Personal 1 year move to archive","Personal 5 year move to archive"
```
  
## <a name="step-3-apply-the-new-retention-policy-to-mailboxes-on-hold"></a><span data-ttu-id="5f8bf-185">Paso 3: Aplicar la nueva directiva de retención a buzones de correo en suspensión</span><span class="sxs-lookup"><span data-stu-id="5f8bf-185">Step 3: Apply the new retention policy to mailboxes on hold</span></span>

<span data-ttu-id="5f8bf-p113">El último paso consiste en aplicar la nueva Directiva de retención que ha creado en el paso 2 a los buzones en retención en la organización. Puede usar el EAC o Exchange Online PowerShell para aplicar la Directiva de retención a un único buzón o a varios buzones.</span><span class="sxs-lookup"><span data-stu-id="5f8bf-p113">The last step is to apply the new retention policy that you created in Step 2 to mailboxes on hold in your organization. You can use the EAC or Exchange Online PowerShell to apply the retention policy to a single mailbox or to multiple mailboxes.</span></span> 
  
### <a name="use-the-eac-to-apply-the-new-retention-policy"></a><span data-ttu-id="5f8bf-188">Usar el EAC para aplicar la nueva directiva de retención</span><span class="sxs-lookup"><span data-stu-id="5f8bf-188">Use the EAC to apply the new retention policy</span></span>
  
1. <span data-ttu-id="5f8bf-189">Vaya a **Destinatarios** \> **Buzones de correo**.</span><span class="sxs-lookup"><span data-stu-id="5f8bf-189">Go to **Recipients** \> **Mailboxes**.</span></span>
    
2. <span data-ttu-id="5f8bf-190">En la vista de lista, seleccione el buzón al que desea aplicar la Directiva de retención y, a \*\*\*\* ![continuación, haga](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif)clic en Editar icono de edición.</span><span class="sxs-lookup"><span data-stu-id="5f8bf-190">In the list view, select the mailbox you want to apply the retention policy to, and then click **Edit** ![Edit icon](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif).</span></span>
    
3. <span data-ttu-id="5f8bf-191">En la página **Buzón de usuario**, haga clic en **Características de buzón de correo**.</span><span class="sxs-lookup"><span data-stu-id="5f8bf-191">On the **User Mailbox** page, click **Mailbox features**.</span></span>
    
4. <span data-ttu-id="5f8bf-192">En **Directiva de retención**, seleccione la directiva de retención que ha creado en el paso 2 y, después, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="5f8bf-192">Under **Retention policy**, select the retention policy that you created in Step 2, and then click **Save**.</span></span>
    
<span data-ttu-id="5f8bf-193">También puede usar el EAC para aplicar la directiva de retención a varios buzones.</span><span class="sxs-lookup"><span data-stu-id="5f8bf-193">You can also use the EAC to apply the retention policy to multiple mailboxes.</span></span>
  
1. <span data-ttu-id="5f8bf-194">Vaya a **Destinatarios** \> **Buzones de correo**.</span><span class="sxs-lookup"><span data-stu-id="5f8bf-194">Go to **Recipients** \> **Mailboxes**.</span></span>
    
2. <span data-ttu-id="5f8bf-195">En la vista de lista, use las teclas Mayús o Ctrl para seleccionar varios buzones.</span><span class="sxs-lookup"><span data-stu-id="5f8bf-195">In the list view, use the Shift or Ctrl keys to select multiple mailboxes.</span></span>
    
3. <span data-ttu-id="5f8bf-196">En el panel de detalles, haga clic en **Más opciones**.</span><span class="sxs-lookup"><span data-stu-id="5f8bf-196">In the details pane, click **More options**.</span></span>
    
4. <span data-ttu-id="5f8bf-197">En **Directiva de retención**, haga clic en **Actualizar**.</span><span class="sxs-lookup"><span data-stu-id="5f8bf-197">Under **Retention Policy**, click **Update**.</span></span>
    
5. <span data-ttu-id="5f8bf-198">En la página **Directiva de retención de asignación masiva**, seleccione la directiva de retención que ha creado en el paso 2 y, después, haga clic en **Guardar**. </span><span class="sxs-lookup"><span data-stu-id="5f8bf-198">On the **Bulk assign retention policy** page, select the retention policy that you created in Step 2, and then click **Save**.</span></span> 
    
### <a name="use-exchange-online-powershell-to-apply-the-new-retention-policy"></a><span data-ttu-id="5f8bf-199">Usar Exchange Online PowerShell para aplicar la nueva Directiva de retención</span><span class="sxs-lookup"><span data-stu-id="5f8bf-199">Use Exchange Online PowerShell to apply the new retention policy</span></span>
  
<span data-ttu-id="5f8bf-p114">Puede usar Exchange Online PowerShell para aplicar una nueva Directiva de retención a un único buzón. Pero el potencial real de PowerShell es que puede usarlo para identificar rápidamente todos los buzones de la organización que están en retención por juicio o conservación local y, a continuación, aplicar la nueva Directiva de retención a todos los buzones en retención en un solo comando. A continuación, se muestran algunos ejemplos de cómo usar Exchange PowerShell para aplicar una directiva de retención a uno o más buzones. En todos los ejemplos se aplica la Directiva de retención que se creó en el paso 2.</span><span class="sxs-lookup"><span data-stu-id="5f8bf-p114">You can use Exchange Online PowerShell to apply a new retention policy to a single mailbox. But the real power of PowerShell is that you can use it to quickly identify all the mailboxes in your organization that are on either Litigation Hold or In-Place Hold, and then apply the new retention policy to all mailboxes on hold in a single command. Here are some examples of using Exchange PowerShell to apply a retention policy to one or more mailboxes. All of the examples apply the retention policy that was created in Step 2.</span></span>
  
<span data-ttu-id="5f8bf-204">En este ejemplo se aplica la nueva directiva de retención al buzón de Pilar Pinilla.</span><span class="sxs-lookup"><span data-stu-id="5f8bf-204">This example applies the new retention policy to Pilar Pinilla's mailbox.</span></span>
  
```
Set-Mailbox "Pilar Pinilla" -RetentionPolicy "MRM Policy for Mailboxes on Hold"
```

<span data-ttu-id="5f8bf-205">En este ejemplo se aplica la nueva directiva de retención a todos los buzones de correo de la organización que se encuentran en retención por juicio.</span><span class="sxs-lookup"><span data-stu-id="5f8bf-205">This example applies the new retention policy to all mailboxes in the organization that are on Litigation Hold.</span></span>
  
```
$LitigationHolds = Get-Mailbox -ResultSize unlimited | Where-Object {$_.LitigationHoldEnabled -eq 'True'}
```

```
$LitigationHolds.DistinguishedName | Set-Mailbox -RetentionPolicy "MRM Policy for Mailboxes on Hold"
```

<span data-ttu-id="5f8bf-206">En este ejemplo se aplica la nueva directiva de retención a todos los buzones de correo de la organización que se encuentran en Conservación local.</span><span class="sxs-lookup"><span data-stu-id="5f8bf-206">This example applies the new retention policy to all mailboxes in the organization that are on In-Place Hold.</span></span>
  
```
$InPlaceHolds = Get-Mailbox -ResultSize unlimited | Where-Object {$_.InPlaceHolds -ne $null}
```

```
$InPlaceHolds.DistinguishedName | Set-Mailbox -RetentionPolicy "MRM Policy for Mailboxes on Hold"
```

<span data-ttu-id="5f8bf-207">Puede usar el cmdlet **Get-Mailbox** para comprobar que se ha aplicado la nueva directiva de retención.</span><span class="sxs-lookup"><span data-stu-id="5f8bf-207">You can use the **Get-Mailbox** cmdlet to verify that the new retention policy was applied.</span></span> 
  
<span data-ttu-id="5f8bf-208">A continuación presentamos algunos ejemplos para comprobar que los comandos de los ejemplos anteriores han aplicado la directiva de retención Directiva de MRM para buzones de correo en suspensión a los buzones que se encuentran en retención por juicio y en Conservación local.</span><span class="sxs-lookup"><span data-stu-id="5f8bf-208">Here are some examples to verify that the commands in the previous examples applied the "MRM Policy for Mailboxes on Hold" retention policy to mailboxes on Litigation Hold and mailboxes on In-Place Hold.</span></span>
  
```
Get-Mailbox "Pilar Pinilla" | Select RetentionPolicy
```

```
Get-Mailbox -ResultSize unlimited | Where-Object {$_.LitigationHoldEnabled -eq 'True'} | FT DisplayName,RetentionPolicy -Auto
```

```
Get-Mailbox -ResultSize unlimited | Where-Object {$_.InPlaceHolds -ne $null} | FT DisplayName,RetentionPolicy -Auto
```
  
## <a name="optional-step-4-run-the-managed-folder-assistant-to-apply-the-new-retention-settings"></a><span data-ttu-id="5f8bf-209">Paso 4 (opcional): Ejecutar el Asistente para carpeta administrada para aplicar la nueva configuración de retención</span><span class="sxs-lookup"><span data-stu-id="5f8bf-209">(Optional) Step 4: Run the Managed Folder Assistant to apply the new retention settings</span></span>

<span data-ttu-id="5f8bf-p115">Una vez aplicada la nueva Directiva de retención a los buzones, puede tardar hasta 7 días en Exchange Online para que el Asistente para carpeta administrada procese estos buzones mediante la configuración de la nueva Directiva de retención. En lugar de esperar a que se ejecute el Asistente para carpeta administrada, puede usar el cmdlet **Start-ManagedFolderAssistant** para desencadenar manualmente el Asistente para que procese los buzones a los que aplicó la nueva Directiva de retención.</span><span class="sxs-lookup"><span data-stu-id="5f8bf-p115">After you apply the new retention policy to mailboxes on hold, it can take up to 7 days in Exchange Online for the Managed Folder Assistant to process these mailboxes using the settings in the new retention policy. Instead of waiting for the Managed Folder Assistant to run, you can use the **Start-ManagedFolderAssistant** cmdlet to manually trigger the assistant to process the mailboxes that you applied the new retention policy to.</span></span> 
  
<span data-ttu-id="5f8bf-212">Ejecute el comando siguiente para iniciar el Asistente para carpeta administrada en el buzón del Pilar Pinilla.</span><span class="sxs-lookup"><span data-stu-id="5f8bf-212">Run the following command to start the Managed Folder Assistant for Pilar Pinilla's mailbox.</span></span>
  
```
Start-ManagedFolderAssistant "Pilar Pinilla"
```

<span data-ttu-id="5f8bf-213">Ejecute los comandos siguientes para iniciar el Asistente para carpeta administrada en todos los buzones en suspensión.</span><span class="sxs-lookup"><span data-stu-id="5f8bf-213">Run the following commands to start the Managed Folder Assistant for all mailboxes on hold.</span></span>
  
```
$MailboxesOnHold = Get-Mailbox -ResultSize unlimited | Where-Object {($_.InPlaceHolds -ne $null) -or ($_.LitigationHoldEnabled -eq "True")}
```

```
$MailboxesOnHold.DistinguishedName | Start-ManagedFolderAssistant
```

## <a name="more-information"></a><span data-ttu-id="5f8bf-214">Más información</span><span class="sxs-lookup"><span data-stu-id="5f8bf-214">More information</span></span>

- <span data-ttu-id="5f8bf-p116">Después de habilitar el buzón de archivo de un usuario, considere la posibilidad de indicar al usuario que se pueden mover otros elementos del buzón (no solo los elementos de la carpeta elementos recuperables) al buzón de archivo. Esto se debe a que la Directiva de MRM predeterminada que se asigna a los buzones de correo de Exchange Online contiene una etiqueta de retención (denominada 2 años como predeterminada, mover a archivo) que mueve los elementos al buzón de archivo dos años después de la fecha en que se entregó el elemento al buzón o se creó mediante el usuario. Para obtener más información, vea [Directiva de retención predeterminada en Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=746954) .</span><span class="sxs-lookup"><span data-stu-id="5f8bf-p116">After you enable a user's archive mailbox, consider telling the user that other items in their mailbox (not just items in the Recoverable Items folder) might be moved to the archive mailbox. This is because the Default MRM Policy that's assigned to Exchange Online mailboxes contains a retention tag (named Default 2 years move to archive) that moves items to the archive mailbox two years after the date the item was delivered to the mailbox or created by the user. For more information, see [Default Retention Policy in Exchange Online ](https://go.microsoft.com/fwlink/p/?LinkId=746954)</span></span>
    
- <span data-ttu-id="5f8bf-p117">Después de habilitar el buzón de archivo de un usuario, también puede decirle al usuario que puede recuperar los elementos eliminados de la carpeta elementos recuperables de su buzón de archivo. Puede hacerlo en Outlook seleccionando la carpeta **elementos eliminados** en el buzón de archivo y, a continuación, haciendo clic en **recuperar elementos eliminados del servidor** en la ficha **Inicio** . Para obtener más información acerca de la recuperación de elementos eliminados, vea [recuperar elementos eliminados en Outlook para Windows](https://go.microsoft.com/fwlink/p/?LinkId=624829).</span><span class="sxs-lookup"><span data-stu-id="5f8bf-p117">After you enable a user's archive mailbox, you might also tell the user that they can recover deleted items in the Recoverable Items folder in their archive mailbox. They can do this in Outlook by selecting the **Deleted Items** folder in the archive mailbox, and then clicking **Recover Deleted Items from Server** on the **Home** tab. For more information about recovering deleted items, see [Recover deleted items in Outlook for Windows](https://go.microsoft.com/fwlink/p/?LinkId=624829).</span></span> 
