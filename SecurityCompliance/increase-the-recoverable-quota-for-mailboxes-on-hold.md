---
title: Aumentar la cuota de elementos recuperables para los buzones de correo en retención
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 10/12/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: a8bdcbdd-9298-462f-b889-df26037a990c
description: 'Habilite el buzón de archivo y active el archivado de expansión automática para aumentar el tamaño de la carpeta elementos recuperables para un buzón de correo en Office 365. '
ms.openlocfilehash: 4c2e36dae3c8677579569d55a9c5b88efb5c54e5
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/17/2019
ms.locfileid: "34154242"
---
# <a name="increase-the-recoverable-items-quota-for-mailboxes-on-hold"></a><span data-ttu-id="07d61-103">Aumentar la cuota de elementos recuperables para los buzones de correo en retención</span><span class="sxs-lookup"><span data-stu-id="07d61-103">Increase the Recoverable Items quota for mailboxes on hold</span></span>

<span data-ttu-id="07d61-104">La Directiva de retención predeterminada, denominada Directiva de MRM predeterminada, que se aplica automáticamente a los nuevos buzones de correo de Exchange Online contiene una etiqueta de retención denominada elementos recuperables de 14 días para mover a archivo.</span><span class="sxs-lookup"><span data-stu-id="07d61-104">The default retention policy—named Default MRM Policy—that is automatically applied to new mailboxes in Exchange Online contains a retention tag named Recoverable Items 14 days move to archive.</span></span> <span data-ttu-id="07d61-105">Esta etiqueta de retención mueve los elementos de la carpeta elementos recuperables del buzón de correo principal del usuario a la carpeta elementos recuperables del buzón de archivo del usuario después de que expire el período de retención de 14 días de un elemento.</span><span class="sxs-lookup"><span data-stu-id="07d61-105">This retention tag moves items from the Recoverable Items folder in the user's primary mailbox to the Recoverable Items folder in the user's archive mailbox after the 14-day retention period expires for an item.</span></span> <span data-ttu-id="07d61-106">Para que esto suceda, debe estar habilitado el buzón de archivo del usuario.</span><span class="sxs-lookup"><span data-stu-id="07d61-106">For this to happen, the user's archive mailbox must be enabled.</span></span> <span data-ttu-id="07d61-107">Si el buzón de archivo no está habilitado, no se realiza ninguna acción, lo que significa que los elementos de la carpeta elementos recuperables de un buzón en retención no se mueven al buzón de archivo después de que expire el período de retención de 14 días.</span><span class="sxs-lookup"><span data-stu-id="07d61-107">If the archive mailbox isn't enabled, no action is taken, which means that items in the Recoverable Items folder for a mailbox on hold aren't moved to the archive mailbox after the 14-day retention period expires.</span></span> <span data-ttu-id="07d61-108">Como no se elimina nada de un buzón de correo en suspensión, es posible que se supere la cuota de almacenamiento de la carpeta elementos recuperables, especialmente si el buzón de archivo del usuario no está habilitado.</span><span class="sxs-lookup"><span data-stu-id="07d61-108">Because nothing is deleted from a mailbox on hold, it's possible that the storage quota for the Recoverable Items folder might be exceeded, especially if the user's archive mailbox isn't enabled.</span></span> 
  
<span data-ttu-id="07d61-109">Para ayudar a reducir la posibilidad de superar este límite, la cuota de almacenamiento de la carpeta elementos recuperables aumenta automáticamente de 30 GB a 100 GB cuando se coloca una retención en un buzón de correo en Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="07d61-109">To help reduce the chance of exceeding this limit, the storage quota for the Recoverable Items folder is automatically increased from 30 GB to 100 GB when a hold is placed on a mailbox in Exchange Online.</span></span> <span data-ttu-id="07d61-110">Si el buzón de archivo está habilitado, la cuota de almacenamiento de la carpeta Elementos recuperables del buzón de archivo también se incrementa de 30 GB a 100 GB.</span><span class="sxs-lookup"><span data-stu-id="07d61-110">If the archive mailbox is enabled, the storage quota for the Recoverable Items folder in the archive mailbox is also increased from 30 GB to 100 GB.</span></span> <span data-ttu-id="07d61-111">Si la característica de archivado de ampliación automática en Exchange Online está habilitada, la cuota de almacenamiento de la carpeta elementos recuperables del archivo del usuario será ilimitada.</span><span class="sxs-lookup"><span data-stu-id="07d61-111">If the auto-expanding archiving feature in Exchange Online is enabled, the storage quota for the Recoverable Items folder in the user's archive will be unlimited.</span></span>
  
 <span data-ttu-id="07d61-112"> En la tabla siguiente se resume la cuota de almacenamiento de la carpeta Elementos recuperables.</span><span class="sxs-lookup"><span data-stu-id="07d61-112">The following table summarizes the storage quota for the Recoverable Items folder.</span></span> 
  
|<span data-ttu-id="07d61-113">**Ubicación de la carpeta Elementos recuperables**</span><span class="sxs-lookup"><span data-stu-id="07d61-113">**Location of Recoverable Items folder**</span></span>|<span data-ttu-id="07d61-114">**Buzones que no están en suspensión**</span><span class="sxs-lookup"><span data-stu-id="07d61-114">**Mailboxes not on hold**</span></span>|<span data-ttu-id="07d61-115">**Buzones en suspensión**</span><span class="sxs-lookup"><span data-stu-id="07d61-115">**Mailboxes on hold**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="07d61-116">Buzón principal</span><span class="sxs-lookup"><span data-stu-id="07d61-116">Primary mailbox</span></span>  <br/> |<span data-ttu-id="07d61-117">30 GB</span><span class="sxs-lookup"><span data-stu-id="07d61-117">30 GB</span></span>  <br/> |<span data-ttu-id="07d61-118">100 GB</span><span class="sxs-lookup"><span data-stu-id="07d61-118">100 GB</span></span>  <br/> |
|<span data-ttu-id="07d61-119">Buzón de archivo<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="07d61-119">Archive mailbox<sup>\*</sup></span></span> <br/> |<span data-ttu-id="07d61-120">Ilimitado</span><span class="sxs-lookup"><span data-stu-id="07d61-120">Unlimited</span></span>  <br/> |<span data-ttu-id="07d61-121">Ilimitado</span><span class="sxs-lookup"><span data-stu-id="07d61-121">Unlimited</span></span>  <br/> |
|<span data-ttu-id="07d61-122">**Cuota de almacenamiento total de la carpeta Elementos recuperables**</span><span class="sxs-lookup"><span data-stu-id="07d61-122">**Total storage quota for the Recoverable Items folder**</span></span> <br/> |<span data-ttu-id="07d61-123">Ilimitado</span><span class="sxs-lookup"><span data-stu-id="07d61-123">Unlimited</span></span>  <br/> |<span data-ttu-id="07d61-124">Ilimitado</span><span class="sxs-lookup"><span data-stu-id="07d61-124">Unlimited</span></span>  <br/> |
   
> [!NOTE]
> <span data-ttu-id="07d61-125"><sup>\*</sup>La cuota de almacenamiento inicial para el buzón de archivo es de 100 GB para los usuarios con una licencia de Exchange Online (plan 2).</span><span class="sxs-lookup"><span data-stu-id="07d61-125"><sup>\*</sup> The initial storage quota for the archive mailbox is 100 GB for users with an Exchange Online (Plan 2) license.</span></span> <span data-ttu-id="07d61-126">Sin embargo, cuando el archivado de expansión automática está activado para buzones en retención, la cuota de almacenamiento para el buzón de archivo y la carpeta elementos recuperables aumenta a 110 GB.</span><span class="sxs-lookup"><span data-stu-id="07d61-126">However, when auto-expanding archiving is turned on for mailboxes on hold, the storage quota for both the archive mailbox and the Recoverable Items folder is increased to 110 GB.</span></span> <span data-ttu-id="07d61-127">El espacio de almacenamiento de archivo adicional se aprovisionará cuando sea necesario, lo que da como resultado una cantidad ilimitada de almacenamiento de archivo.</span><span class="sxs-lookup"><span data-stu-id="07d61-127">Additional archive storage space will be provisioned when necessary which results in an unlimited amount of archive storage.</span></span> <span data-ttu-id="07d61-128">Para obtener más información acerca del archivado de expansión automática, vea [información general sobre el archivado ilimitado en Office 365](unlimited-archiving.md).</span><span class="sxs-lookup"><span data-stu-id="07d61-128">For more information about auto-expanding archiving, see [Overview of unlimited archiving in Office 365](unlimited-archiving.md).</span></span> 
  
<span data-ttu-id="07d61-129">Cuando la cuota de almacenamiento de la carpeta Elementos recuperables en el buzón principal de un buzón en suspensión está a punto de alcanzar su límite, puede hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="07d61-129">When the storage quota for the Recoverable Items folder in the primary mailbox of a mailbox on hold is close to reaching its limit, you can do the following things:</span></span>
  
- <span data-ttu-id="07d61-130">**Habilitar el buzón de archivo y activar el archivado de expansión automática** : puede habilitar una capacidad de almacenamiento ilimitada para la carpeta elementos recuperables con tan solo habilitar el buzón de archivo y, a continuación, activar la característica de archivado de ampliación automática en Exchange. Online.</span><span class="sxs-lookup"><span data-stu-id="07d61-130">**Enable the archive mailbox and turn on auto-expanding archiving** - You can enable an unlimited storage capacity for the Recoverable Items folder simply by enabling the archive mailbox and then turning on the auto-expanding archiving feature in Exchange Online.</span></span> <span data-ttu-id="07d61-131">Esto da como resultado 110 GB para la carpeta elementos recuperables en el buzón principal y una cantidad ilimitada de capacidad de almacenamiento para la carpeta elementos recuperables del archivo del usuario.</span><span class="sxs-lookup"><span data-stu-id="07d61-131">This results in 110 GB for the Recoverable Items folder in the primary mailbox and an unlimited amount of storage capacity for the Recoverable Items folder in the user's archive.</span></span> <span data-ttu-id="07d61-132">Vea cómo: [Habilitar buzones de archivo en el centro de seguridad _AMP_ cumplimiento](enable-archive-mailboxes.md) y [Habilitar el archivado ilimitado en Office 365](enable-unlimited-archiving.md).</span><span class="sxs-lookup"><span data-stu-id="07d61-132">See how: [Enable archive mailboxes in the Security & Compliance Center](enable-archive-mailboxes.md) and [Enable unlimited archiving in Office 365](enable-unlimited-archiving.md).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="07d61-133">Después de habilitar el archivo para un buzón que esté a punto de superar la cuota de almacenamiento de la carpeta Elementos recuperables, podría interesarle ejecutar el Asistente para carpeta administrada a fin de activar manualmente el Asistente para procesar el buzón, de modo que los elementos expirados se muevan a la carpeta Elementos recuperables del buzón de archivo.</span><span class="sxs-lookup"><span data-stu-id="07d61-133">After you enable the archive for a mailbox that's close to exceeding the storage quota for the Recoverable Items folder, you might want to run the Managed Folder Assistant to manually trigger the assistant to process the mailbox so that expired items are moved the Recoverable Items folder in the archive mailbox.</span></span> <span data-ttu-id="07d61-134">Vea el [paso 4](#optional-step-4-run-the-managed-folder-assistant-to-apply-the-new-retention-settings) para obtener instrucciones.</span><span class="sxs-lookup"><span data-stu-id="07d61-134">See [Step 4](#optional-step-4-run-the-managed-folder-assistant-to-apply-the-new-retention-settings) for instructions.</span></span> <span data-ttu-id="07d61-135">Tenga en cuenta que podrían moverse otros elementos del buzón del usuario al nuevo buzón de archivo.</span><span class="sxs-lookup"><span data-stu-id="07d61-135">Note that other items in the user's mailbox might be moved to the new archive mailbox.</span></span> <span data-ttu-id="07d61-136">Considere la posibilidad de que se indique al usuario que esto puede ocurrir después de habilitar el buzón de archivo.</span><span class="sxs-lookup"><span data-stu-id="07d61-136">Consider telling the user that this may happen after you enable the archive mailbox.</span></span> 
  
- <span data-ttu-id="07d61-137">**Crear una directiva de retención personalizada para buzones de correo en** retención: además de habilitar el buzón de archivo y el archivado de expansión automática para buzones en retención por juicio o conservación local, es posible que también desee crear una directiva de retención personalizada para los buzones de correo en retención.</span><span class="sxs-lookup"><span data-stu-id="07d61-137">**Create a custom retention policy for mailboxes on hold** - In addition to enabling the archive mailbox and auto-expanding archiving for mailboxes on Litigation Hold or In-Place Hold, you might also want to create a custom retention policy for mailboxes on hold.</span></span> <span data-ttu-id="07d61-138">Esto le permite aplicar una directiva de retención a los buzones de correo en retención que es diferente de la Directiva de MRM predeterminada que se aplica a los buzones que no están en suspensión.</span><span class="sxs-lookup"><span data-stu-id="07d61-138">This let's you apply a retention policy to mailboxes on hold that's different from the Default MRM Policy that's applied to mailboxes that aren't on hold.</span></span> <span data-ttu-id="07d61-139">Esto le permite aplicar etiquetas de retención que se han diseñado específicamente para buzones de correo en retención.</span><span class="sxs-lookup"><span data-stu-id="07d61-139">This lets you to apply retention tags that are specifically designed for mailboxes on hold.</span></span> <span data-ttu-id="07d61-140">Esto incluye la creación de una nueva etiqueta de retención para la carpeta elementos recuperables.</span><span class="sxs-lookup"><span data-stu-id="07d61-140">This includes creating a new retention tag for the Recoverable Items folder.</span></span> 
    
<span data-ttu-id="07d61-141">En el resto de este tema se describen procedimientos paso a paso para crear una directiva de retención personalizada para los buzones en suspensión.</span><span class="sxs-lookup"><span data-stu-id="07d61-141">The remainder of this topic describes the step-by-step procedures to create a custom retention policy for mailboxes on hold.</span></span>
  
[<span data-ttu-id="07d61-142">Paso 1: Crear una etiqueta de retención personalizada para la carpeta Elementos recuperables</span><span class="sxs-lookup"><span data-stu-id="07d61-142">Step 1: Create a custom retention tag for the Recoverable Items folder</span></span>](#step-1-create-a-custom-retention-tag-for-the-recoverable-items-folder)

<span data-ttu-id="07d61-143">[[Paso 2: crear una nueva Directiva de retención para buzones en retención](#step-2-create-a-new-retention-policy-for-mailboxes-on-hold)</span><span class="sxs-lookup"><span data-stu-id="07d61-143">[[Step 2: Create a new retention policy for mailboxes on hold](#step-2-create-a-new-retention-policy-for-mailboxes-on-hold)</span></span>

[<span data-ttu-id="07d61-144">Paso 3: Aplicar la nueva directiva de retención a buzones de correo en suspensión</span><span class="sxs-lookup"><span data-stu-id="07d61-144">Step 3: Apply the new retention policy to mailboxes on hold</span></span>](#step-3-apply-the-new-retention-policy-to-mailboxes-on-hold)

[<span data-ttu-id="07d61-145">Paso 4 (opcional): Ejecutar el Asistente para carpeta administrada para aplicar la nueva configuración de retención</span><span class="sxs-lookup"><span data-stu-id="07d61-145">(Optional) Step 4: Run the Managed Folder Assistant to apply the new retention settings</span></span>](#optional-step-4-run-the-managed-folder-assistant-to-apply-the-new-retention-settings)
  
## <a name="step-1-create-a-custom-retention-tag-for-the-recoverable-items-folder"></a><span data-ttu-id="07d61-146">Paso 1: Crear una etiqueta de retención personalizada para la carpeta Elementos recuperables</span><span class="sxs-lookup"><span data-stu-id="07d61-146">Step 1: Create a custom retention tag for the Recoverable Items folder</span></span>

<span data-ttu-id="07d61-147">El primer paso consiste en crear una etiqueta de retención personalizada (denominada etiqueta de directiva de retención o RPT) para la carpeta Elementos recuperables.</span><span class="sxs-lookup"><span data-stu-id="07d61-147">The first step is to create a custom retention tag (called a retention policy tag or RPT) for the Recoverable Items folder.</span></span> <span data-ttu-id="07d61-148">Como se ha explicado anteriormente, esta RPT mueve elementos de la carpeta Elementos recuperables del buzón de correo principal del usuario a la carpeta Elementos recuperables del buzón de archivo del usuario.</span><span class="sxs-lookup"><span data-stu-id="07d61-148">As previously explained, this RPT moves items from the Recoverable Items folder in the user's primary mailbox to the Recoverable Items folder in the user's archive mailbox.</span></span> <span data-ttu-id="07d61-149">Debe usar PowerShell para crear una RPT para la carpeta elementos recuperables.</span><span class="sxs-lookup"><span data-stu-id="07d61-149">You have to use PowerShell to create an RPT for the Recoverable Items folder.</span></span> <span data-ttu-id="07d61-150">No puede usar el Centro de administración de Exchange (EAC).</span><span class="sxs-lookup"><span data-stu-id="07d61-150">You can't use the Exchange admin center (EAC).</span></span> 
  
1. [<span data-ttu-id="07d61-151">Conectarse a Exchange Online con el PowerShell remoto</span><span class="sxs-lookup"><span data-stu-id="07d61-151">Connect to Exchange Online using remote PowerShell</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=517283)
    
2. <span data-ttu-id="07d61-152">Ejecute el comando siguiente para crear una RPT para la carpeta Elementos recuperables: </span><span class="sxs-lookup"><span data-stu-id="07d61-152">Run the following command to create a new RPT for the Recoverable Items folder:</span></span> 
    
    ```
    New-RetentionPolicyTag -Name <Name of RPT> -Type RecoverableItems -AgeLimitForRetention <Number of days> -RetentionAction MoveToArchive
    ```

    <span data-ttu-id="07d61-p108">Por ejemplo, el comando siguiente crea una RPT para la carpeta Elementos recuperables denominada "30 días en Elementos recuperables para buzones en suspensión", con un período de retención de 30 días. Esto significa que, una vez que un elemento haya estado en la carpeta Elementos recuperables durante 30 días, se moverá a la carpeta Elementos recuperables del buzón de archivo del usuario.</span><span class="sxs-lookup"><span data-stu-id="07d61-p108">For example, the following command creates a RPT for the Recoverable Items folder named "Recoverable Items 30 days for mailboxes on hold", with a retention period of 30 days. This means that after an item has been in the Recoverable Items folder for 30 days, it will be moved to the Recoverable Items folder in the user's archive mailbox.</span></span>
    
    ```
    New-RetentionPolicyTag -Name "Recoverable Items 30 days for mailboxes on hold" -Type RecoverableItems -AgeLimitForRetention 30 -RetentionAction MoveToArchive
    ```

    > [!TIP]
    > <span data-ttu-id="07d61-155">Se recomienda que el período de retención (definido por el parámetro _AgeLimitForRetention_ ) para la RPT de elementos recuperables sea el mismo que el período de retención de elementos eliminados para los buzones de correo a los que se aplicará el RPT.</span><span class="sxs-lookup"><span data-stu-id="07d61-155">We recommend that the retention period (defined by the  _AgeLimitForRetention_ parameter) for the Recoverable Items RPT is the same as the deleted item retention period for the mailboxes that the RPT will be applied to.</span></span> <span data-ttu-id="07d61-156">Esto permite a un usuario todo el período de retención de elementos eliminados para recuperar los elementos eliminados antes de que se muevan al buzón de archivo.</span><span class="sxs-lookup"><span data-stu-id="07d61-156">This allows a user the entire deleted item retention period to recover deleted items before they are moved to the archive mailbox.</span></span> <span data-ttu-id="07d61-157">En el ejemplo anterior, el período de retención se estableció en 30 días en función de la hipótesis de que el período de retención de elementos eliminados para los buzones de correo es también de 30 días.</span><span class="sxs-lookup"><span data-stu-id="07d61-157">In the previous example, the retention period was set to 30 days based on the assumption that the deleted item retention period for mailboxes is also 30 days.</span></span> <span data-ttu-id="07d61-158">De forma predeterminada, se configura un buzón de correo de Exchange Online para conservar los elementos eliminados durante 14 días.</span><span class="sxs-lookup"><span data-stu-id="07d61-158">An Exchange Online mailbox is configured to retain deleted items for 14 days, by default.</span></span> <span data-ttu-id="07d61-159">Pero puede cambiar esta configuración a un máximo de 30 días.</span><span class="sxs-lookup"><span data-stu-id="07d61-159">But you can change this setting to a maximum of 30 days.</span></span> <span data-ttu-id="07d61-160">Para obtener más información, vea [cambiar el período de retención de elementos eliminados para un buzón de correo en Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=286940).</span><span class="sxs-lookup"><span data-stu-id="07d61-160">For more information, see [Change the deleted item retention period for a mailbox in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=286940).</span></span> 
  
## <a name="step-2-create-a-new-retention-policy-for-mailboxes-on-hold"></a><span data-ttu-id="07d61-161">Paso 2: Crear una directiva de retención para buzones de correo en suspensión</span><span class="sxs-lookup"><span data-stu-id="07d61-161">Step 2: Create a new retention policy for mailboxes on hold</span></span>

<span data-ttu-id="07d61-p110">El siguiente paso consiste en crear una directiva de retención y agregarle etiquetas de retención, incluida la RPT de Elementos recuperables que creó en el paso 1. Esta nueva directiva se aplicará a los buzones de correo en suspensión en el paso siguiente. </span><span class="sxs-lookup"><span data-stu-id="07d61-p110">The next step is to create a new retention policy and add retention tags to it, including the Recoverable Items RPT that you created in Step 1. This new policy will be applied to mailboxes on hold in the next step.</span></span> 
  
<span data-ttu-id="07d61-p111">Antes de crear la directiva de retención, determine las etiquetas de retención adicionales que quiere agregar. Para obtener una lista de las etiquetas de retención que se agregan a la directiva de MRM predeterminada y para obtener información sobre cómo crear etiquetas de retención, vea lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="07d61-p111">Before you create the new retention policy, determine the additional retention tags that you want to add. For a list of the retention tags that are added to the Default MRM Policy and for information about creating new retention tags, see the following:</span></span>
  
- [<span data-ttu-id="07d61-166">Directiva de retención predeterminada en Exchange Online</span><span class="sxs-lookup"><span data-stu-id="07d61-166">Default Retention Policy in Exchange Online </span></span>](https://go.microsoft.com/fwlink/p/?LinkId=746954)
    
- [<span data-ttu-id="07d61-167">Carpetas predeterminadas que admiten etiquetas de la directiva de retención</span><span class="sxs-lookup"><span data-stu-id="07d61-167">Default folders that support Retention Policy Tags</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=746957)
    
- <span data-ttu-id="07d61-168">La sección "crear una etiqueta de retención" en el tema [Create a Retention Policy](https://go.microsoft.com/fwlink/p/?LinkId=404422) .</span><span class="sxs-lookup"><span data-stu-id="07d61-168">The "Create a retention tag" section in the [Create a Retention Policy](https://go.microsoft.com/fwlink/p/?LinkId=404422) topic.</span></span>
    
<span data-ttu-id="07d61-169">Puede usar el EAC o Exchange Online PowerShell para crear una directiva de retención.</span><span class="sxs-lookup"><span data-stu-id="07d61-169">You can use the EAC or Exchange Online PowerShell to create a retention policy.</span></span>
  
### <a name="use-the-eac-to-create-a-retention-policy"></a><span data-ttu-id="07d61-170">Uso de EAC para crear una directiva de retención</span><span class="sxs-lookup"><span data-stu-id="07d61-170">Use the EAC to create a retention policy</span></span>
  
1. <span data-ttu-id="07d61-171">En el EAC, vaya a \*\*\*\* \> **directivas de retención**de administración de cumplimiento y, a continuación](media/ITPro-EAC-AddIcon.gif), haga clic en **Agregar** ![icono de agregar.</span><span class="sxs-lookup"><span data-stu-id="07d61-171">In the EAC, go to **Compliance management** \> **Retention policies**, and then click **Add** ![Add Icon](media/ITPro-EAC-AddIcon.gif).</span></span>
    
2. <span data-ttu-id="07d61-172">En la página **Nueva directiva de retención**, en **Nombre**, escriba un nombre que describa el propósito de la directiva, como **MRM Policy for Mailboxes on Hold** (Directiva de MRM para buzones de correo en suspensión). </span><span class="sxs-lookup"><span data-stu-id="07d61-172">On the **New retention policy** page, under **Name**, type a name that describes the purpose of the retention policy; for example, **MRM Policy for Mailboxes on Hold**.</span></span> 
    
3. <span data-ttu-id="07d61-173">En **etiquetas de retención**, haga clic en](media/ITPro-EAC-AddIcon.gif) **Agregar** ![icono de agregar.</span><span class="sxs-lookup"><span data-stu-id="07d61-173">Under **Retention tags**, click **Add** ![Add Icon](media/ITPro-EAC-AddIcon.gif).</span></span>
    
4. <span data-ttu-id="07d61-174">En la lista de etiquetas de retención, seleccione la RPT de Elementos recuperables que ha creado en el paso 1 y, después, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="07d61-174">In the list of retention tags, select the Recoverable Items RPT that you created in Step 1, and then click **Add**.</span></span>
    
    ![Seleccione la etiqueta de retención personalizada Elementos recuperables](media/eb49866b-bdef-4fcd-a6d9-01607c01249b.png)
  
5. <span data-ttu-id="07d61-p112">Seleccione las etiquetas de retención adicionales que quiera agregar a la directiva de retención. Por ejemplo, podría interesarle agregar las mismas etiquetas que se incluyen en la directiva de MRM predeterminada.</span><span class="sxs-lookup"><span data-stu-id="07d61-p112">Select additional retention tags to add to the retention policy. For example, you might want to add the same tags that are included in the Default MRM Policy.</span></span>
    
6. <span data-ttu-id="07d61-178">Cuando termine de agregar reglas de retención, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="07d61-178">When you're finished adding retention tags, click **OK**.</span></span>
    
7. <span data-ttu-id="07d61-179">Haga clic en **Guardar** para crear la directiva de retención.</span><span class="sxs-lookup"><span data-stu-id="07d61-179">Click **Save** to create the new retention policy.</span></span> 
    
    <span data-ttu-id="07d61-180">Observe que las etiquetas de retención vinculadas a la directiva de retención se muestran en el panel de detalles</span><span class="sxs-lookup"><span data-stu-id="07d61-180">Notice that the retention tags linked to the retention policy are displayed in the details pane.</span></span>
    
    ![Las etiquetas de retención vinculadas a la directiva de retención se muestran en el panel de detalles](media/dad1c8f4-9928-4d6d-991a-6f6c5194eceb.png)
  
### <a name="use-exchange-online-powershell-to-create-a-retention-policy"></a><span data-ttu-id="07d61-182">Usar Exchange Online PowerShell para crear una directiva de retención</span><span class="sxs-lookup"><span data-stu-id="07d61-182">Use Exchange Online PowerShell to create a retention policy</span></span>
  
<span data-ttu-id="07d61-183">Ejecute el comando siguiente para crear una directiva de retención para buzones en suspensión. </span><span class="sxs-lookup"><span data-stu-id="07d61-183">Run the following command to create new retention policy for mailboxes on hold.</span></span> 
  
```
New-RetentionPolicy <Name of retention policy>  -RetentionPolicyTagLinks <list of retention tags>

```

<span data-ttu-id="07d61-184">Por ejemplo, el comando siguiente crea la directiva de retención y las etiquetas de retención vinculadas que se muestran en la ilustración anterior.</span><span class="sxs-lookup"><span data-stu-id="07d61-184">For example, the following command creates the retention policy and linked retention tags that is displayed in the previous illustration.</span></span>
  
```
New-RetentionPolicy "MRM Policy for Mailboxes on Hold"  -RetentionPolicyTagLinks "Recoverable Items 30 days for mailboxes on hold","1 Month Delete","1 Week Delete","1 Year Delete","5 Year Delete","6 Month Delete","Default 2 year move to archive","Junk Email","Never Delete","Personal 1 year move to archive","Personal 5 year move to archive"
```
  
## <a name="step-3-apply-the-new-retention-policy-to-mailboxes-on-hold"></a><span data-ttu-id="07d61-185">Paso 3: Aplicar la nueva directiva de retención a buzones de correo en suspensión</span><span class="sxs-lookup"><span data-stu-id="07d61-185">Step 3: Apply the new retention policy to mailboxes on hold</span></span>

<span data-ttu-id="07d61-186">El último paso consiste en aplicar la nueva directiva de retención que ha creado en el paso 2 a buzones de correo en suspensión de su organización.</span><span class="sxs-lookup"><span data-stu-id="07d61-186">The last step is to apply the new retention policy that you created in Step 2 to mailboxes on hold in your organization.</span></span> <span data-ttu-id="07d61-187">Puede usar el EAC o Exchange Online PowerShell para aplicar la Directiva de retención a un único buzón o a varios buzones.</span><span class="sxs-lookup"><span data-stu-id="07d61-187">You can use the EAC or Exchange Online PowerShell to apply the retention policy to a single mailbox or to multiple mailboxes.</span></span> 
  
### <a name="use-the-eac-to-apply-the-new-retention-policy"></a><span data-ttu-id="07d61-188">Usar el EAC para aplicar la nueva directiva de retención</span><span class="sxs-lookup"><span data-stu-id="07d61-188">Use the EAC to apply the new retention policy</span></span>
  
1. <span data-ttu-id="07d61-189">Vaya a **Destinatarios** \> **Buzones de correo**.</span><span class="sxs-lookup"><span data-stu-id="07d61-189">Go to **Recipients** \> **Mailboxes**.</span></span>
    
2. <span data-ttu-id="07d61-190">En la vista de lista, seleccione el buzón al que desea aplicar la Directiva de retención y, a \*\*\*\* ![continuación, haga](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif)clic en Editar icono de edición.</span><span class="sxs-lookup"><span data-stu-id="07d61-190">In the list view, select the mailbox you want to apply the retention policy to, and then click **Edit** ![Edit icon](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif).</span></span>
    
3. <span data-ttu-id="07d61-191">En la página **Buzón de usuario**, haga clic en **Características de buzón de correo**.</span><span class="sxs-lookup"><span data-stu-id="07d61-191">On the **User Mailbox** page, click **Mailbox features**.</span></span>
    
4. <span data-ttu-id="07d61-192">En **Directiva de retención**, seleccione la directiva de retención que ha creado en el paso 2 y, después, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="07d61-192">Under **Retention policy**, select the retention policy that you created in Step 2, and then click **Save**.</span></span>
    
<span data-ttu-id="07d61-193">También puede usar el EAC para aplicar la directiva de retención a varios buzones.</span><span class="sxs-lookup"><span data-stu-id="07d61-193">You can also use the EAC to apply the retention policy to multiple mailboxes.</span></span>
  
1. <span data-ttu-id="07d61-194">Vaya a **Destinatarios** \> **Buzones de correo**.</span><span class="sxs-lookup"><span data-stu-id="07d61-194">Go to **Recipients** \> **Mailboxes**.</span></span>
    
2. <span data-ttu-id="07d61-195">En la vista de lista, use las teclas Mayús o Ctrl para seleccionar varios buzones.</span><span class="sxs-lookup"><span data-stu-id="07d61-195">In the list view, use the Shift or Ctrl keys to select multiple mailboxes.</span></span>
    
3. <span data-ttu-id="07d61-196">En el panel de detalles, haga clic en **Más opciones**.</span><span class="sxs-lookup"><span data-stu-id="07d61-196">In the details pane, click **More options**.</span></span>
    
4. <span data-ttu-id="07d61-197">En **Directiva de retención**, haga clic en **Actualizar**.</span><span class="sxs-lookup"><span data-stu-id="07d61-197">Under **Retention Policy**, click **Update**.</span></span>
    
5. <span data-ttu-id="07d61-198">En la página **Directiva de retención de asignación masiva**, seleccione la directiva de retención que ha creado en el paso 2 y, después, haga clic en **Guardar**. </span><span class="sxs-lookup"><span data-stu-id="07d61-198">On the **Bulk assign retention policy** page, select the retention policy that you created in Step 2, and then click **Save**.</span></span> 
    
### <a name="use-exchange-online-powershell-to-apply-the-new-retention-policy"></a><span data-ttu-id="07d61-199">Usar Exchange Online PowerShell para aplicar la nueva Directiva de retención</span><span class="sxs-lookup"><span data-stu-id="07d61-199">Use Exchange Online PowerShell to apply the new retention policy</span></span>
  
<span data-ttu-id="07d61-200">Puede usar Exchange Online PowerShell para aplicar una nueva Directiva de retención a un único buzón.</span><span class="sxs-lookup"><span data-stu-id="07d61-200">You can use Exchange Online PowerShell to apply a new retention policy to a single mailbox.</span></span> <span data-ttu-id="07d61-201">Pero el potencial real de PowerShell es que puede usarlo para identificar rápidamente todos los buzones de la organización que están en retención por juicio o conservación local y, a continuación, aplicar la nueva Directiva de retención a todos los buzones en retención en un solo comando.</span><span class="sxs-lookup"><span data-stu-id="07d61-201">But the real power of PowerShell is that you can use it to quickly identify all the mailboxes in your organization that are on either Litigation Hold or In-Place Hold, and then apply the new retention policy to all mailboxes on hold in a single command.</span></span> <span data-ttu-id="07d61-202">A continuación, se muestran algunos ejemplos de cómo usar Exchange PowerShell para aplicar una directiva de retención a uno o más buzones.</span><span class="sxs-lookup"><span data-stu-id="07d61-202">Here are some examples of using Exchange PowerShell to apply a retention policy to one or more mailboxes.</span></span> <span data-ttu-id="07d61-203">Todos los ejemplos aplican la directiva de retención que ha creado en el paso 2.</span><span class="sxs-lookup"><span data-stu-id="07d61-203">All of the examples apply the retention policy that was created in Step 2.</span></span>
  
<span data-ttu-id="07d61-204">En este ejemplo se aplica la nueva directiva de retención al buzón de Pilar Pinilla.</span><span class="sxs-lookup"><span data-stu-id="07d61-204">This example applies the new retention policy to Pilar Pinilla's mailbox.</span></span>
  
```
Set-Mailbox "Pilar Pinilla" -RetentionPolicy "MRM Policy for Mailboxes on Hold"
```

<span data-ttu-id="07d61-205">En este ejemplo se aplica la nueva directiva de retención a todos los buzones de correo de la organización que se encuentran en retención por juicio.</span><span class="sxs-lookup"><span data-stu-id="07d61-205">This example applies the new retention policy to all mailboxes in the organization that are on Litigation Hold.</span></span>
  
```
$LitigationHolds = Get-Mailbox -ResultSize unlimited | Where-Object {$_.LitigationHoldEnabled -eq 'True'}
```

```
$LitigationHolds.DistinguishedName | Set-Mailbox -RetentionPolicy "MRM Policy for Mailboxes on Hold"
```

<span data-ttu-id="07d61-206">En este ejemplo se aplica la nueva directiva de retención a todos los buzones de correo de la organización que se encuentran en Conservación local.</span><span class="sxs-lookup"><span data-stu-id="07d61-206">This example applies the new retention policy to all mailboxes in the organization that are on In-Place Hold.</span></span>
  
```
$InPlaceHolds = Get-Mailbox -ResultSize unlimited | Where-Object {$_.InPlaceHolds -ne $null}
```

```
$InPlaceHolds.DistinguishedName | Set-Mailbox -RetentionPolicy "MRM Policy for Mailboxes on Hold"
```

<span data-ttu-id="07d61-207">Puede usar el cmdlet **Get-Mailbox** para comprobar que se ha aplicado la nueva directiva de retención.</span><span class="sxs-lookup"><span data-stu-id="07d61-207">You can use the **Get-Mailbox** cmdlet to verify that the new retention policy was applied.</span></span> 
  
<span data-ttu-id="07d61-208">A continuación presentamos algunos ejemplos para comprobar que los comandos de los ejemplos anteriores han aplicado la directiva de retención Directiva de MRM para buzones de correo en suspensión a los buzones que se encuentran en retención por juicio y en Conservación local.</span><span class="sxs-lookup"><span data-stu-id="07d61-208">Here are some examples to verify that the commands in the previous examples applied the "MRM Policy for Mailboxes on Hold" retention policy to mailboxes on Litigation Hold and mailboxes on In-Place Hold.</span></span>
  
```
Get-Mailbox "Pilar Pinilla" | Select RetentionPolicy
```

```
Get-Mailbox -ResultSize unlimited | Where-Object {$_.LitigationHoldEnabled -eq 'True'} | FT DisplayName,RetentionPolicy -Auto
```

```
Get-Mailbox -ResultSize unlimited | Where-Object {$_.InPlaceHolds -ne $null} | FT DisplayName,RetentionPolicy -Auto
```
  
## <a name="optional-step-4-run-the-managed-folder-assistant-to-apply-the-new-retention-settings"></a><span data-ttu-id="07d61-209">Paso 4 (opcional): Ejecutar el Asistente para carpeta administrada para aplicar la nueva configuración de retención</span><span class="sxs-lookup"><span data-stu-id="07d61-209">(Optional) Step 4: Run the Managed Folder Assistant to apply the new retention settings</span></span>

<span data-ttu-id="07d61-210">Una vez aplicada la nueva Directiva de retención a los buzones, puede tardar hasta 7 días en Exchange Online para que el Asistente para carpeta administrada procese estos buzones mediante la configuración de la nueva Directiva de retención.</span><span class="sxs-lookup"><span data-stu-id="07d61-210">After you apply the new retention policy to mailboxes on hold, it can take up to 7 days in Exchange Online for the Managed Folder Assistant to process these mailboxes using the settings in the new retention policy.</span></span> <span data-ttu-id="07d61-211">En lugar de esperar a que se ejecute el Asistente para carpeta administrada, puede usar el cmdlet **Start-ManagedFolderAssistant** para activar manualmente el asistente, de modo que procese los buzones a los que les ha aplicado la nueva directiva de retención.</span><span class="sxs-lookup"><span data-stu-id="07d61-211">Instead of waiting for the Managed Folder Assistant to run, you can use the **Start-ManagedFolderAssistant** cmdlet to manually trigger the assistant to process the mailboxes that you applied the new retention policy to.</span></span> 
  
<span data-ttu-id="07d61-212">Ejecute el comando siguiente para iniciar el Asistente para carpeta administrada en el buzón del Pilar Pinilla.</span><span class="sxs-lookup"><span data-stu-id="07d61-212">Run the following command to start the Managed Folder Assistant for Pilar Pinilla's mailbox.</span></span>
  
```
Start-ManagedFolderAssistant "Pilar Pinilla"
```

<span data-ttu-id="07d61-213">Ejecute los comandos siguientes para iniciar el Asistente para carpeta administrada en todos los buzones en suspensión.</span><span class="sxs-lookup"><span data-stu-id="07d61-213">Run the following commands to start the Managed Folder Assistant for all mailboxes on hold.</span></span>
  
```
$MailboxesOnHold = Get-Mailbox -ResultSize unlimited | Where-Object {($_.InPlaceHolds -ne $null) -or ($_.LitigationHoldEnabled -eq "True")}
```

```
$MailboxesOnHold.DistinguishedName | Start-ManagedFolderAssistant
```

## <a name="more-information"></a><span data-ttu-id="07d61-214">Más información</span><span class="sxs-lookup"><span data-stu-id="07d61-214">More information</span></span>

- <span data-ttu-id="07d61-215">Después de habilitar el buzón de archivo de un usuario, considere la posibilidad de informar al usuario de que otros elementos del buzón (no solo los elementos de la carpeta Elementos recuperables) se podrían mover al buzón de archivo.</span><span class="sxs-lookup"><span data-stu-id="07d61-215">After you enable a user's archive mailbox, consider telling the user that other items in their mailbox (not just items in the Recoverable Items folder) might be moved to the archive mailbox.</span></span> <span data-ttu-id="07d61-216">Esto se debe a que la Directiva de MRM predeterminada que se asigna a los buzones de correo de Exchange Online contiene una etiqueta de retención (denominada 2 años como predeterminada, mover a archivo) que mueve los elementos al buzón de archivo dos años después de la fecha en que se entregó el elemento al buzón o se creó mediante el usuario.</span><span class="sxs-lookup"><span data-stu-id="07d61-216">This is because the Default MRM Policy that's assigned to Exchange Online mailboxes contains a retention tag (named Default 2 years move to archive) that moves items to the archive mailbox two years after the date the item was delivered to the mailbox or created by the user.</span></span> <span data-ttu-id="07d61-217">Para obtener más información, vea [Directiva de retención predeterminada en Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=746954) .</span><span class="sxs-lookup"><span data-stu-id="07d61-217">For more information, see [Default Retention Policy in Exchange Online ](https://go.microsoft.com/fwlink/p/?LinkId=746954)</span></span>
    
- <span data-ttu-id="07d61-218">Después de habilitar el buzón de archivo de un usuario, también puede decirle al usuario que puede recuperar los elementos eliminados de la carpeta elementos recuperables de su buzón de archivo.</span><span class="sxs-lookup"><span data-stu-id="07d61-218">After you enable a user's archive mailbox, you might also tell the user that they can recover deleted items in the Recoverable Items folder in their archive mailbox.</span></span> <span data-ttu-id="07d61-219">Puede hacerlo en Outlook seleccionando la carpeta **elementos eliminados** en el buzón de archivo y, a continuación, haciendo clic en **recuperar elementos eliminados del servidor** en la ficha **Inicio** . Para obtener más información acerca de la recuperación de elementos eliminados, vea [recuperar elementos eliminados en Outlook para Windows](https://go.microsoft.com/fwlink/p/?LinkId=624829).</span><span class="sxs-lookup"><span data-stu-id="07d61-219">They can do this in Outlook by selecting the **Deleted Items** folder in the archive mailbox, and then clicking **Recover Deleted Items from Server** on the **Home** tab. For more information about recovering deleted items, see [Recover deleted items in Outlook for Windows](https://go.microsoft.com/fwlink/p/?LinkId=624829).</span></span> 
