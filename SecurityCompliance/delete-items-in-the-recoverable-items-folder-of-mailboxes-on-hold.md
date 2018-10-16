---
title: Eliminar elementos de la carpeta elementos recuperables de los buzones de correo basados en la nube en espera - ayuda de administración
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: a85e1c87-a48e-4715-bfa9-d5275cde67b0
description: 'Para los administradores: eliminar elementos de carpeta de elementos recuperables de un usuario para un buzón de Exchange Online, incluso si ese buzón se coloca en retención legal. Esto es una forma eficaz para eliminar los datos que se ha derramado accidentalmente en Office 365.'
ms.openlocfilehash: 9174e953ebdd7f0032f411b99a814aeacd880a1e
ms.sourcegitcommit: dd58ed6fd424272e361bc3c109ecd6d63d673048
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/15/2018
ms.locfileid: "25566891"
---
# <a name="delete-items-in-the-recoverable-items-folder-of-cloud-based-mailboxes-on-hold---admin-help"></a><span data-ttu-id="899b8-104">Eliminar elementos de la carpeta elementos recuperables de los buzones de correo basados en la nube en espera - ayuda de administración</span><span class="sxs-lookup"><span data-stu-id="899b8-104">Delete items in the Recoverable Items folder of cloud-based mailboxes on hold - Admin Help</span></span>

<span data-ttu-id="899b8-p102">La carpeta elementos recuperables para un buzón de Exchange Online existe para proteger contra eliminaciones accidentales o intencionadas. También se usa para almacenar los elementos que se conservan y el acceso a características de cumplimiento de normas de Office 365, como las suspensiones y exhibición de documentos electrónicos las búsquedas. Sin embargo, en algunas situaciones en las organizaciones es posible que tienen datos que se ha conservado por equivocación en la carpeta elementos recuperables que debe eliminar. Por ejemplo, un usuario sin darse cuenta podría enviar o reenviar un mensaje de correo electrónico que contiene información confidencial o información que puede tener consecuencias serio del negocio. Incluso si el mensaje se elimina de manera permanente, es posible que se retenga indefinidamente porque se ha colocado una suspensión legal en el buzón de correo. En este escenario se conoce como pérdidas de datos porque derramas accidentalmente datos en Office 365. En estas situaciones, puede eliminar los elementos de carpeta de elementos recuperables de un usuario para un buzón de Exchange Online, incluso si ese buzón se pondrá en espera con una de las características de suspensión diferentes en Office 365. Estos tipos de suspensiones incluyen contiene litigios, suspensiones en contexto, suspensiones de exhibición de documentos electrónicos y las directivas de retención de Office 365 creadas en la seguridad de Office 365 &amp; centro de cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="899b8-p102">The Recoverable Items folder for an Exchange Online mailbox exists to protect from accidental or malicious deletions. It's also used to store items that are retained and accessed by Office 365 compliance features, such as holds and eDiscovery searches. However, in some situations organizations might have data that's been unintentionally retained in the Recoverable Items folder that they must delete. For example, a user might unknowingly send or forward an email message that contains sensitive information or information that may have serious business consequences. Even if the message is permanently deleted, it might be retained indefinitely because a legal hold has been placed on the mailbox. This scenario is known as data spillage because data has been unintentionally spilled into Office 365. In these situations, you can delete items in a user's Recoverable Items folder for an Exchange Online mailbox, even if that mailbox is placed on hold with one of the different hold features in Office 365. These types of holds include Litigation Holds, In-Place Holds, eDiscovery holds, and Office 365 retention policies created in the Office 365 Security &amp; Compliance Center.</span></span> 
  
 <span data-ttu-id="899b8-p103">En este artículo se explica cómo eliminar elementos de la carpeta elementos recuperables de buzones de correo basados en la nube que están en espera. Este procedimiento implica deshabilitar acceso al buzón y deshabilitar la recuperación de elemento único, deshabilitar el Asistente para carpeta administrada de procesar el buzón, quitar temporalmente la suspensión, eliminar elementos de la carpeta elementos recuperables y, a continuación, revertir el buzón de correo a su configuración anterior. Este es el proceso:</span><span class="sxs-lookup"><span data-stu-id="899b8-p103">This article explains how to delete items from the Recoverable Items folder for cloud-based mailboxes that are on hold. This procedure involves disabling access to the mailbox and disabling single item recovery, disabling the Managed Folder Assistant from processing the mailbox, temporarily removing the hold, deleting items from the Recoverable Items folder, and then reverting the mailbox to its previous configuration. Here's the process:</span></span> 
  
[<span data-ttu-id="899b8-116">Paso 1: Recopilar información acerca del buzón</span><span class="sxs-lookup"><span data-stu-id="899b8-116">Step 1: Collect information about the mailbox</span></span>](#step-1-collect-information-about-the-mailbox)

[<span data-ttu-id="899b8-117">Paso 2: Preparar el buzón de correo</span><span class="sxs-lookup"><span data-stu-id="899b8-117">Step 2: Prepare the mailbox</span></span>](#step-2-prepare-the-mailbox)

[<span data-ttu-id="899b8-118">Paso 3: Quitar todas las suspensiones desde el buzón de correo</span><span class="sxs-lookup"><span data-stu-id="899b8-118">Step 3: Remove all holds from the mailbox</span></span>](#step-3-remove-all-holds-from-the-mailbox)

[<span data-ttu-id="899b8-119">Paso 4: Quitar la suspensión de retraso desde el buzón de correo</span><span class="sxs-lookup"><span data-stu-id="899b8-119">Step 4: Remove the delay hold from the mailbox</span></span>](#step-4-remove-the-delay-hold-from-the-mailbox)

[<span data-ttu-id="899b8-120">Paso 5: Eliminar elementos de la carpeta elementos recuperables</span><span class="sxs-lookup"><span data-stu-id="899b8-120">Step 5: Delete items in the Recoverable Items folder</span></span>](#step-5-delete-items-in-the-recoverable-items-folder)

[<span data-ttu-id="899b8-121">Paso 6: Revertir el buzón de correo a su estado anterior</span><span class="sxs-lookup"><span data-stu-id="899b8-121">Step 6: Revert the mailbox to its previous state</span></span>](#step-6-revert-the-mailbox-to-its-previous-state)
  
> [!CAUTION]
> <span data-ttu-id="899b8-p104">Los procedimientos descritos en este artículo, se producirá datos que se va a eliminar de forma permanente (depuraron) de un buzón de Exchange Online. Es decir, los mensajes que se eliminan de la carpeta elementos recuperables no se pueden recuperar y no estarán disponibles para otros fines de cumplimiento de normas o de descubrimiento legal. Si desea eliminar los mensajes de un buzón que se pondrá en espera como parte de un juicio, conservación local, mantenga presionada la exhibición de documentos electrónicos o directiva de retención de Office 365 creado en la seguridad de Office 365 &amp; centro de cumplimiento, verificación con la administración de registros o con fines legales departamentos antes de quitar la suspensión. Su organización puede tener una directiva que define si un buzón de correo en espera o un incidente de pérdidas de datos tiene prioridad.</span><span class="sxs-lookup"><span data-stu-id="899b8-p104">The procedures outlined in this article will result in data being permanently deleted (purged) from an Exchange Online mailbox. That means messages that you delete from the Recoverable Items folder can't be recovered and won't be available for legal discovery or other compliance purposes. If you want to delete messages from a mailbox that's placed on hold as part of a Litigation Hold, In-Place Hold, eDiscovery hold, or Office 365 retention policy created in the Office 365 Security &amp; Compliance Center, check with your records management or legal departments before removing the hold. Your organization might have a policy that defines whether a mailbox on hold or a data spillage incident takes priority.</span></span> 
  
## <a name="before-you-begin"></a><span data-ttu-id="899b8-126">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="899b8-126">Before you begin</span></span>

- <span data-ttu-id="899b8-127">Se debe asignarse ambas de las siguientes funciones de administración de Exchange en línea para buscar y eliminar mensajes de la carpeta elementos recuperables en el paso 5.</span><span class="sxs-lookup"><span data-stu-id="899b8-127">You have to be assigned both of the following management roles in Exchange Online to search for and delete messages from the Recoverable Items folder in Step 5.</span></span>
    
  - <span data-ttu-id="899b8-p105">**Búsqueda de buzones** - esta función permite para buscar los buzones de correo en la organización. Los administradores de Exchange no están asignados a esta función de forma predeterminada. Para asignar manualmente este rol, agregar usted mismo como miembro del grupo de roles de administración de detección en Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="899b8-p105">**Mailbox Search** - This role lets you to search mailboxes in your organization. Exchange administrators aren't assigned this role by default. To assign yourself this role, add yourself as a member of the Discovery Management role group in Exchange Online.</span></span> 
    
  - <span data-ttu-id="899b8-p106">**Buzón de correo importar exportar** - este rol permite para eliminar mensajes del buzón de un usuario. De forma predeterminada, esta función no está asignada a ningún grupo de funciones. Para eliminar los mensajes de los buzones de los usuarios, puede agregar la función de exportación de importación de buzón de correo para el grupo de roles de administración de la organización de Exchange en línea.</span><span class="sxs-lookup"><span data-stu-id="899b8-p106">**Mailbox Import Export** - This role lets you to delete messages from a user's mailbox. By default, this role isn't assigned to any role group. To delete messages from users' mailboxes, you can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> 
    
- <span data-ttu-id="899b8-p107">El procedimiento descrito en este artículo no se admite para los buzones de correo inactivos. Debido a que no puede volver a aplicar una suspensión (o directiva de retención de Office 365) que consiste en un buzón inactivo después de quitarlo. Cuando se quita una suspensión de un buzón de correo inactivo, se cambia a un buzón eliminado temporalmente normal y se eliminarán permanentemente de la organización una vez que se procesa mediante el Asistente para carpeta administrada.</span><span class="sxs-lookup"><span data-stu-id="899b8-p107">The procedure described in this article isn't supported for inactive mailboxes. That's because you can't re-apply a hold (or Office 365 retention policy) to an inactive mailbox after you remove it. When you remove a hold from an inactive mailbox, it's changed to a normal soft-deleted mailbox and will be permanently deleted from your organization after it's processed by the Managed Folder Assistant.</span></span>
    
- <span data-ttu-id="899b8-p108">No se puede realizar este procedimiento para un buzón de correo que se ha asignado a una directiva de retención de Office 365 que se han sido bloqueada con un bloqueo de conservación. Eso es porque un bloqueo de conservación impide que se quiten o excluyendo el buzón de correo de la directiva de retención de Office 365 y de deshabilitar el Asistente de carpetas administradas en el buzón de correo. Para obtener más información acerca de las directivas de retención de bloqueo, vea [bloqueo de una directiva de retención](retention-policies.md#locking-a-retention-policy).</span><span class="sxs-lookup"><span data-stu-id="899b8-p108">You can't perform this procedure for a mailbox that has been assigned to an Office 365 retention policy that's been locked with a Preservation Lock. That's because a Preservation Lock prevents you from removing or excluding the mailbox from the Office 365 retention policy and from disabling the Managed Folder Assistant on the mailbox. For more information about locking retention policies, see [Locking a retention policy](retention-policies.md#locking-a-retention-policy).</span></span>
    
- <span data-ttu-id="899b8-p109">Si un buzón de correo no se pondrá en espera (o no tiene la recuperación de un solo elemento habilitada), simplemente puede eliminar los elementos de la carpeta elementos recuperables. Para obtener más información acerca de cómo hacer esto, vea [Buscar y eliminar mensajes ](https://go.microsoft.com/fwlink/?linkid=852453).</span><span class="sxs-lookup"><span data-stu-id="899b8-p109">If a mailbox isn't placed on hold (or doesn't have single item recovery enabled), you can simply delete the items from the Recoverable Items folder. For more information about how to do this, see [Search for and delete messages ](https://go.microsoft.com/fwlink/?linkid=852453).</span></span>
  
## <a name="step-1-collect-information-about-the-mailbox"></a><span data-ttu-id="899b8-142">Paso 1: Recopilar información acerca del buzón</span><span class="sxs-lookup"><span data-stu-id="899b8-142">Step 1: Collect information about the mailbox</span></span>

<span data-ttu-id="899b8-p110">En este primer paso es recopilar las propiedades seleccionadas del buzón de destino que afectará a este procedimiento. Asegúrese de anotar estas opciones de configuración o guardarlos en un archivo de texto, ya que podrá cambiar algunas de estas propiedades y, a continuación, volver a los valores originales en el paso 6, después de eliminar los elementos de la carpeta elementos recuperables. Aquí es una lista de las propiedades del buzón de correo que necesita recopilar.</span><span class="sxs-lookup"><span data-stu-id="899b8-p110">This first step is to collect selected properties from the target mailbox that will affect this procedure. Be sure to write down these settings or save them to a text file because you'll change some of these properties and then revert back to the original values in Step 6, after you delete items from the Recoverable Items folder. Here's a list of the mailbox properties you need to collect.</span></span>
  
-  <span data-ttu-id="899b8-146">*SingleItemRecoveryEnabled* y *RetainDeletedItemsFor* ; Si es necesario, podrá deshabilitar la recuperación único y aumentar el período de retención de elementos eliminados en el paso 3.</span><span class="sxs-lookup"><span data-stu-id="899b8-146">*SingleItemRecoveryEnabled*  and  *RetainDeletedItemsFor*  ; if necessary, you'll disable single recovery and increase the deleted items retention period in Step 3.</span></span> 
    
-  <span data-ttu-id="899b8-p111">*LitigationHoldEnabled* y *InPlaceHolds* ; deberá identificar todas las suspensiones colocadas en el buzón de correo para que se pueden quitar temporalmente en el paso 3. Vea la sección [obtener más información](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md#moreinfo) para obtener sugerencias sobre cómo identificar la suspensión de tipo que se puede incluir en un buzón de correo.</span><span class="sxs-lookup"><span data-stu-id="899b8-p111">*LitigationHoldEnabled*  and  *InPlaceHolds*  ; you need to identify all the holds placed on the mailbox so that you can temporarily remove them in Step 3. See the [More information](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md#moreinfo) section for tips about how to identify the type hold that might be placed on a mailbox.</span></span> 
    
<span data-ttu-id="899b8-p112">Además, debe obtener el buzón de correo en configuración de acceso de cliente, por lo que puede deshabilitarlas temporalmente por lo que el propietario (u otros usuarios) no se pueden obtener acceso al buzón durante este procedimiento. Por último, puede obtener el tamaño actual y el número de elementos en la carpeta elementos recuperables. Después de eliminar elementos de la carpeta elementos recuperables en el paso 5, debe usar esta información para comprobar que realmente se han eliminado los elementos.</span><span class="sxs-lookup"><span data-stu-id="899b8-p112">Additionally, you need to get the mailbox client access settings so you can temporarily disable them so the owner (or other users) can't access the mailbox during this procedure. Finally, you can get the current size and number of items in the Recoverable Items folder. After you delete items in the Recoverable Items folder in Step 5, you'll use this information to verify that items were actually removed.</span></span>
  
1. <span data-ttu-id="899b8-p113">[Conectarse a Exchange Online PowerShell](https://go.microsoft.com/fwlink/?linkid=396554). Asegúrese de usar un nombre de usuario y una contraseña para una cuenta de administrador que se ha asignado los roles de administración adecuada de Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="899b8-p113">[Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/?linkid=396554). Be sure to use a user name and password for an administrator account that's been assigned the appropriate management roles in Exchange Online.</span></span> 
    
2. <span data-ttu-id="899b8-154">Ejecute el siguiente comando para obtener información acerca de la recuperación de elemento único y el período de retención de elementos eliminados.</span><span class="sxs-lookup"><span data-stu-id="899b8-154">Run the following command to get information about single item recovery and the deleted item retention period.</span></span>

    ```
    Get-Mailbox <username> | FL SingleItemRecoveryEnabled,RetainDeletedItemsFor
    ```

   <span data-ttu-id="899b8-p114">Si está habilitada la recuperación de elemento único, debe deshabilitar en el paso 2. Si no se establece el período de retención de elementos eliminados durante 30 días (el valor máximo en Exchange Online), a continuación, puede aumentar en el paso 2.</span><span class="sxs-lookup"><span data-stu-id="899b8-p114">If single item recovery is enabled, you'll have to disable it in Step 2. If the deleted item retention period isn't set for 30 days (the maximum value in Exchange Online), then you can increase it in Step 2.</span></span> 
    
3. <span data-ttu-id="899b8-157">Ejecute el siguiente comando para obtener el buzón de configuración de acceso para el buzón de correo.</span><span class="sxs-lookup"><span data-stu-id="899b8-157">Run the following command to get the mailbox access settings for the mailbox.</span></span> 
    
    ```
    Get-CASMailbox <username> | FL EwsEnabled,ActiveSyncEnabled,MAPIEnabled,OWAEnabled,ImapEnabled,PopEnabled
    ```

   <span data-ttu-id="899b8-158">Podrá deshabilitar todos estos métodos de acceso en el paso 2.</span><span class="sxs-lookup"><span data-stu-id="899b8-158">You'll disable all of these access methods in Step 2.</span></span>
    
4. <span data-ttu-id="899b8-159">Ejecute el siguiente comando para obtener información sobre las suspensiones y las directivas de retención de Office 365 aplicadas al buzón de correo.</span><span class="sxs-lookup"><span data-stu-id="899b8-159">Run the following command to get information about the holds and Office 365 retention policies applied to the mailbox.</span></span>
    
    ```
    Get-Mailbox <username> | FL LitigationHoldEnabled,InPlaceHolds
    ```


   > [!TIP]
    > <span data-ttu-id="899b8-160">Si hay demasiados valores de la propiedad *InPlaceHolds* y no todos ellos se muestran, puede ejecutar el `Get-Mailbox <username> | Select-Object -ExpandProperty InPlaceHolds` comando para mostrar cada valor en una línea independiente.</span><span class="sxs-lookup"><span data-stu-id="899b8-160">If there are too many values in the  *InPlaceHolds*  property and not all of them are displayed, you can run the  `Get-Mailbox <username> | Select-Object -ExpandProperty InPlaceHolds` command to display each value on a separate line.</span></span> 
  
5. <span data-ttu-id="899b8-161">Ejecute el comando siguiente para obtener información acerca de las directivas de retención de Office 365 de toda la organización.</span><span class="sxs-lookup"><span data-stu-id="899b8-161">Run the following command to get information about any organization-wide Office 365 retention policies.</span></span> 

    ```
    Get-OrganizationConfig | FL InPlaceHolds
    ```
   <span data-ttu-id="899b8-162">Si su organización tiene las directivas de retención de Office 365 de toda la organización, debe excluir el buzón de correo de estas directivas en el paso 3.</span><span class="sxs-lookup"><span data-stu-id="899b8-162">If your organization has any organization-wide Office 365 retention policies, you'll have to exclude the mailbox from these policies in Step 3.</span></span>

   > [!TIP]
    > <span data-ttu-id="899b8-163">Si hay demasiados valores de la propiedad *InPlaceHolds* y no todos ellos se muestran, puede ejecutar el `Get-OrganizationConfig | Select-Object -ExpandProperty InPlaceHolds` comando para mostrar cada valor en una línea independiente.</span><span class="sxs-lookup"><span data-stu-id="899b8-163">If there are too many values in the  *InPlaceHolds*  property and not all of them are displayed, you can run the  `Get-OrganizationConfig | Select-Object -ExpandProperty InPlaceHolds` command to display each value on a separate line.</span></span> 
  
6. <span data-ttu-id="899b8-164">Ejecute el siguiente comando para obtener el tamaño actual y el número total de elementos en carpetas y subcarpetas en la carpeta elementos recuperables en el buzón del usuario principal.</span><span class="sxs-lookup"><span data-stu-id="899b8-164">Run the following command to get the current size and total number of items in folders and subfolders in the Recoverable Items folder in the user's primary mailbox.</span></span> 

    ```
    Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
    ```

   <span data-ttu-id="899b8-165">Si se habilita el buzón de archivo del usuario, ejecute el siguiente comando para obtener el tamaño y el número total de elementos en carpetas y subcarpetas en la carpeta elementos recuperables en su buzón de archivo.</span><span class="sxs-lookup"><span data-stu-id="899b8-165">If the user's archive mailbox is enabled, run the following command to get the size and total number of items in folders and subfolders in the Recoverable Items folder in their archive mailbox.</span></span> 

    ```s
    Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems -Archive | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
    ```

   <span data-ttu-id="899b8-p115">Cuando elimina los elementos en el paso 5, puede elegir eliminar o no eliminar elementos de la carpeta elementos recuperables en el buzón del usuario principal del archivo. Tenga en cuenta que si está habilitado la ampliación automática de archivado para el buzón de correo, los elementos de un buzón de archivo auxiliar no se eliminará.</span><span class="sxs-lookup"><span data-stu-id="899b8-p115">When you delete items in Step 5, you can choose to delete or not delete items in the Recoverable Items folder in the user's primary archive mailbox. Note that if auto-expanding archiving is enabled for the mailbox, items in an auxiliary archive mailbox won't be deleted.</span></span>
  
## <a name="step-2-prepare-the-mailbox"></a><span data-ttu-id="899b8-168">Paso 2: Preparar el buzón de correo</span><span class="sxs-lookup"><span data-stu-id="899b8-168">Step 2: Prepare the mailbox</span></span>

<span data-ttu-id="899b8-169">Después de recopilar y guardar información acerca del buzón, el siguiente paso es preparar el buzón de correo mediante la realización de las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="899b8-169">After collecting and saving information about the mailbox, the next step is to prepare the mailbox by performing the following tasks:</span></span> 
  
- <span data-ttu-id="899b8-170">**Deshabilitar el acceso de cliente al buzón de correo** para que el propietario del buzón no se puede obtener acceso a sus buzones de correo y realizar cambios en los datos de buzones durante este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="899b8-170">**Disable client access to mailbox** so that the mailbox owner can't access their mailbox and make any changes to the mailbox data during this procedure.</span></span> 
    
- <span data-ttu-id="899b8-171">**Aumentar el período de retención de elementos eliminados** en 30 días (el valor máximo en Exchange Online) para que no se purgan elementos desde la carpeta elementos recuperables antes de poder eliminar en el paso 5.</span><span class="sxs-lookup"><span data-stu-id="899b8-171">**Increase the deleted item retention period** to 30 days (the maximum value in Exchange Online) so that items aren't purged from the Recoverable Items folder before you can delete them in Step 5.</span></span> 
    
- <span data-ttu-id="899b8-172">**Deshabilitar la recuperación de elemento único** por lo los elementos no se conservan (para la duración del período de retención de elementos eliminados) después de eliminar de la carpeta elementos recuperables en el paso 5.</span><span class="sxs-lookup"><span data-stu-id="899b8-172">**Disable single Item recovery** so that items won't be retained (for the duration of the deleted item retention period) after you delete them from the Recoverable Items folder in Step 5.</span></span> 
    
- <span data-ttu-id="899b8-173">**Deshabilitar el Asistente para carpeta administrada** por lo que no procesar el buzón de correo y conservar los elementos que se eliminan en el paso 5.</span><span class="sxs-lookup"><span data-stu-id="899b8-173">**Disable the Managed Folder Assistant** so that it doesn't process the mailbox and retain the items that you delete in Step 5.</span></span> 
    
<span data-ttu-id="899b8-174">Realice los pasos siguientes en Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="899b8-174">Perform the following steps in Exchange Online PowerShell.</span></span>
  
1. <span data-ttu-id="899b8-p116">Ejecute el siguiente comando para deshabilitar todo el acceso de cliente para el buzón de correo. La sintaxis del comando, se da por supuesto que todos los métodos de acceso de cliente están habilitados en el buzón de correo.</span><span class="sxs-lookup"><span data-stu-id="899b8-p116">Run the following command to disable all client access to the mailbox. The command syntax assumes that all client access methods were enabled on the mailbox.</span></span>

    ```   
    Set-CASMailbox <username> -EwsEnabled $false -ActiveSyncEnabled $false -MAPIEnabled $false -OWAEnabled $false -ImapEnabled $false -PopEnabled $false
    ```
   
   > [!NOTE]
    > <span data-ttu-id="899b8-p117">Pueden tardar hasta 60 minutos para deshabilitar todos los métodos de acceso de cliente para el buzón de correo. Tenga en cuenta que al deshabilitar estos métodos de acceso no desconecta el propietario del buzón que haya iniciado la sesión. Si el propietario no se ha iniciado sesión, a continuación, no podrán tener acceso a su buzón después de que se deshabilitan estos métodos de acceso.</span><span class="sxs-lookup"><span data-stu-id="899b8-p117">It might take up to 60 minutes to disable all client access methods to the mailbox. Note that disabling these access methods won't disconnect the mailbox owner they're currently signed in. If the owner isn't signed in, then they won't be able to access their mailbox after these access methods are disabled.</span></span> 
  
2. <span data-ttu-id="899b8-p118">Ejecute el siguiente comando para aumentar el período de retención de elementos eliminados en el máximo de 30 días. Esto supone que la configuración actual es menor que 30 días.</span><span class="sxs-lookup"><span data-stu-id="899b8-p118">Run the following command to increase the deleted item retention period the maximum of 30 days. This assumes that the current setting is less than 30 days.</span></span> 

    ```
    Set-Mailbox <username> -RetainDeletedItemsFor 30
    ```

3. <span data-ttu-id="899b8-182">Ejecute el siguiente comando para deshabilitar la recuperación de elemento único.</span><span class="sxs-lookup"><span data-stu-id="899b8-182">Run the following command to disable single item recovery.</span></span>
    
    ```
    Set-Mailbox <username> -SingleItemRecoveryEnabled $false
    ```

   > [!NOTE]
    > <span data-ttu-id="899b8-p119">Pueden tardar hasta 60 minutos para deshabilitar la recuperación de elemento único. No eliminar los elementos en la carpeta elementos recuperables hasta que haya transcurrido este período.</span><span class="sxs-lookup"><span data-stu-id="899b8-p119">It might take up to 60 minutes to disable single item recovery. Don't delete items in the Recoverable Items folder until this period has elapsed.</span></span> 
  
4. <span data-ttu-id="899b8-p120">Ejecute el siguiente comando para evitar que el Asistente para carpeta administrada procesar el buzón. Como se explica anteriormente, puede deshabilitar el Asistente para carpeta administrada sólo si no se aplica una directiva de retención de Office 365 con un bloqueo de conservación para el buzón de correo.</span><span class="sxs-lookup"><span data-stu-id="899b8-p120">Run the following command to prevent the Managed Folder Assistant from processing the mailbox. As previously explained, you can disable the Managed Folder Assistant only if an Office 365 retention policy with a Preservation Lock is not applied to the mailbox.</span></span> 

    ```
    Set-Mailbox <username> -ElcProcessingDisabled $true
    ```

## <a name="step-3-remove-all-holds-from-the-mailbox"></a><span data-ttu-id="899b8-187">Paso 3: Quitar todas las suspensiones desde el buzón de correo</span><span class="sxs-lookup"><span data-stu-id="899b8-187">Step 3: Remove all holds from the mailbox</span></span>

<span data-ttu-id="899b8-p121">El último paso antes de eliminar los elementos de la carpeta elementos recuperables es quitar todas las suspensiones (que ha identificado en el paso 1) colocadas en el buzón de correo. Todas las suspensiones deben quitarse para que no se conservan los elementos después de eliminarlos de la carpeta elementos recuperables. Las secciones siguientes contienen información sobre cómo quitar distintos tipos de suspensiones en un buzón de correo. Vea la sección [obtener más información](#more-information) para obtener sugerencias sobre cómo identificar la suspensión de tipo que se puede incluir en un buzón de correo. Para obtener más información, vea [cómo se identifica el tipo de suspensión colocado en un buzón de Exchange Online](identify-a-hold-on-an-exchange-online-mailbox.md).</span><span class="sxs-lookup"><span data-stu-id="899b8-p121">The last step before you can delete items from the Recoverable Items folder is to remove all holds (that you identified in Step 1) placed on the mailbox. All holds must be removed so that items won't be retained after you delete them from the Recoverable Items folder. The following sections contain information about removing different types of holds on a mailbox. See the [More information](#more-information) section for tips about how to identify the type hold that might be placed on a mailbox. For additional information, see [How to identify the type of hold placed on an Exchange Online mailbox](identify-a-hold-on-an-exchange-online-mailbox.md).</span></span>
  
> [!CAUTION]
> <span data-ttu-id="899b8-193">Como se señaló anteriormente, compruebe con la administración de registros o departamentos legales antes de quitar una suspensión de un buzón de correo.</span><span class="sxs-lookup"><span data-stu-id="899b8-193">As previously stated, check with your records management or legal departments before removing a hold from a mailbox.</span></span> 
  
 ### <a name="litigation-hold"></a><span data-ttu-id="899b8-194">Retención por juicio</span><span class="sxs-lookup"><span data-stu-id="899b8-194">Litigation Hold</span></span>
  
<span data-ttu-id="899b8-195">Ejecute el siguiente comando en Exchange Online PowerShell para quitar un juicio desde el buzón de correo.</span><span class="sxs-lookup"><span data-stu-id="899b8-195">Run the following command in Exchange Online PowerShell to remove a Litigation Hold from the mailbox.</span></span>

```
Set-Mailbox <username> -LitigationHoldEnabled $false
```

   
> [!NOTE]
> <span data-ttu-id="899b8-p122">Al igual que la deshabilitación de los métodos de acceso de cliente y la recuperación de elemento único, puede tardar hasta 60 minutos para quitar la suspensión por litigio. No eliminar elementos de la carpeta elementos recuperables hasta que haya transcurrido este período.</span><span class="sxs-lookup"><span data-stu-id="899b8-p122">Similar to disabling the client access methods and single item recovery, it might take up to 60 minutes to remove the Litigation Hold. Don't delete items from the Recoverable Items folder until this period has elapsed.</span></span> 
  
 ### <a name="in-place-hold"></a><span data-ttu-id="899b8-198">Retención en contexto</span><span class="sxs-lookup"><span data-stu-id="899b8-198">In-Place Hold</span></span>
  
<span data-ttu-id="899b8-p123">Ejecute el siguiente comando en Exchange Online PowerShell para identificar la retención local que se coloca en el buzón de correo. Utilice el GUID para la retención local que ha identificado en el paso 1.</span><span class="sxs-lookup"><span data-stu-id="899b8-p123">Run the following command in Exchange Online PowerShell to identify the In-Place Hold that's placed on the mailbox. Use the GUID for the In-Place Hold that you identified in Step 1.</span></span> 

```
Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL Name
```
   
<span data-ttu-id="899b8-p124">Después de identificar la retención en contexto, puede usar el centro de administración de Exchange (EAC) o Exchange Online PowerShell para quitar el buzón de correo de la suspensión. Para obtener más información, consulte [Create or remove an In-Place Hold](https://go.microsoft.com/fwlink/?linkid=852668).</span><span class="sxs-lookup"><span data-stu-id="899b8-p124">After you identify the In-Place Hold, you can use the Exchange admin center (EAC) or Exchange Online PowerShell to remove the mailbox from the hold. For more information, see [Create or remove an In-Place Hold](https://go.microsoft.com/fwlink/?linkid=852668).</span></span>
  
 ### <a name="office-365-retention-policies-applied-to-specific-mailboxes"></a><span data-ttu-id="899b8-203">Directivas de retención 365 Office aplicadas a buzones específicos</span><span class="sxs-lookup"><span data-stu-id="899b8-203">Office 365 retention policies applied to specific mailboxes</span></span>
  
<span data-ttu-id="899b8-p125">Ejecute el siguiente comando [Office 365 seguridad &amp; PowerShell de centro de cumplimiento de normas](https://go.microsoft.com/fwlink/?linkid=627084) para identificar la directiva de retención de Office 365 que se aplica a los buzones de correo. Usar el GUID (sin incluir el `mbx` o `skp` prefijo) para la directiva de retención que ha identificado en el paso 1.</span><span class="sxs-lookup"><span data-stu-id="899b8-p125">Run the following command in [Office 365 Security &amp; Compliance Center PowerShell](https://go.microsoft.com/fwlink/?linkid=627084) to identify the Office 365 retention policy that is applied to the mailbox. Use the GUID (not including the  `mbx` or  `skp` prefix) for the retention policy that you identified in Step 1.</span></span> 

```
Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name
```
   
<span data-ttu-id="899b8-206">Después de identificar la directiva de retención, vaya a la **gobernanza de fecha** \> página de **retención** en la seguridad &amp; centro de cumplimiento, editar la directiva de retención que ha identificado en el paso anterior y quitar el buzón de correo de la lista de destinatarios que se incluyen en la directiva de retención.</span><span class="sxs-lookup"><span data-stu-id="899b8-206">After you identify the retention policy, go to the **Date governance** \> **Retention** page in the Security &amp; Compliance Center, edit the retention policy that you identified in the previous step, and remove the mailbox from the list of recipients that are included in the retention policy.</span></span> 
  
 ### <a name="organization-wide-office-365-retention-policies"></a><span data-ttu-id="899b8-207">Directivas de retención de Office 365 de toda la organización</span><span class="sxs-lookup"><span data-stu-id="899b8-207">Organization-wide Office 365 retention policies</span></span>
  
<span data-ttu-id="899b8-p126">Toda la organización y las directivas de retención de toda la Exchange Office 365 se aplican a todos los buzones de la organización. Que se aplican en el nivel de organización (no el nivel de buzón de correo) y se devuelven cuando se ejecuta el cmdlet **Get-OrganizationConfig** en el paso 1. Ejecute el siguiente comando [seguridad &amp; PowerShell de centro de cumplimiento de normas](https://go.microsoft.com/fwlink/?linkid=627084) para identificar las directivas de retención de Office 365 de toda la organización. Usar el GUID (sin incluir el `mbx` prefijo) de las directivas de retención de toda la organización que ha identificado en el paso 1.</span><span class="sxs-lookup"><span data-stu-id="899b8-p126">Organization-wide and Exchange-wide Office 365 retention policies are applied to every mailbox in the organization. They are applied at the organization level (not the mailbox level) and are returned when you run the **Get-OrganizationConfig** cmdlet in Step 1. Run the following command in [Security &amp; Compliance Center PowerShell](https://go.microsoft.com/fwlink/?linkid=627084) to identify the organization-wide Office 365 retention policies. Use the GUID (not including the  `mbx` prefix) for the organization-wide retention policies that you identified in Step 1.</span></span> 

```
Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name
```

<span data-ttu-id="899b8-p127">Después de identificar las directivas de retención de toda la organización Office 365, vaya a la **gobernanza de fecha** \> página de **retención** en la seguridad &amp; centro de cumplimiento, editar cada directiva de retención de toda la organización que ha identificado en el anterior paso y agregar el buzón de correo a la lista de destinatarios excluidos. De esta forma quitará el buzón del usuario de la directiva de retención.</span><span class="sxs-lookup"><span data-stu-id="899b8-p127">After you identify the organization-wide Office 365 retention policies, go to the **Date governance** \> **Retention** page in the Security &amp; Compliance Center, edit each organization-wide retention policy that you identified in the previous step, and add the mailbox to the list of excluded recipients. Doing this will remove the user's mailbox from the retention policy.</span></span> 

### <a name="office-365-retention-labels"></a><span data-ttu-id="899b8-214">Etiquetas de retención de Office 365</span><span class="sxs-lookup"><span data-stu-id="899b8-214">Office 365 retention labels</span></span>

<span data-ttu-id="899b8-p128">Cada vez que un usuario aplica una etiqueta que está configurada para conservar el contenido o retener y, a continuación, eliminar contenido a una carpeta o elemento en su buzón, la propiedad del buzón de correo de *ComplianceTagHoldApplied* se establece en **True**. Cuando esto sucede, se considera que el buzón se encuentra en suspensión, como si se colocan en suspensión por litigio o asignado a una directiva de retención de Office 365.</span><span class="sxs-lookup"><span data-stu-id="899b8-p128">Whenever a user applies a label that's configured to retain content or retain and then delete content to any folder or item in their mailbox, the *ComplianceTagHoldApplied* mailbox property is set to **True**. When this happens, the mailbox is considered to be on hold, just as if it was placed on Litigation Hold or assigned to an Office 365 retention policy.</span></span>

<span data-ttu-id="899b8-217">Para ver el valor de la propiedad *ComplianceTagHoldApplied* , ejecute el siguiente comando en Exchange Online PowerShell:</span><span class="sxs-lookup"><span data-stu-id="899b8-217">To view the value of the *ComplianceTagHoldApplied* property, run the following command in Exchange Online PowerShell:</span></span>

```
Get-Mailbox <username> |FL ComplianceTagHoldApplied
```

<span data-ttu-id="899b8-p129">Una vez que ha identificado que un buzón se encuentra en suspensión debido a que se aplica una etiqueta de retención a una carpeta o elemento, puede usar la herramienta de búsqueda de contenido en la seguridad & Centro de cumplimiento para buscar elementos etiquetados mediante el uso de la condición de búsqueda ComplianceTag. Para obtener más información, vea la sección "Las condiciones de búsqueda" en [las consultas de palabra clave y las condiciones de búsqueda para la búsqueda de contenido](keyword-queries-and-search-conditions.md#conditions-for-common-properties).</span><span class="sxs-lookup"><span data-stu-id="899b8-p129">After you've identified that a mailbox is on hold because a retention label is applied to a folder or item, you can use the Content Search tool in the Security & Compliance Center to search for labeled items by using the ComplianceTag search condition. For more information, see the "Search conditions" section in [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md#conditions-for-common-properties).</span></span>

<span data-ttu-id="899b8-220">Para obtener más información acerca de las etiquetas, vea [información general de Office 365 etiquetas](labels.md).</span><span class="sxs-lookup"><span data-stu-id="899b8-220">For more information about labels, see [Overview of Office 365 labels](labels.md).</span></span>

 ### <a name="ediscovery-case-holds"></a><span data-ttu-id="899b8-221">contiene el caso de exhibición de documentos electrónicos</span><span class="sxs-lookup"><span data-stu-id="899b8-221">eDiscovery case holds</span></span>
  
<span data-ttu-id="899b8-p130">Ejecute los siguientes comandos [seguridad &amp; PowerShell de centro de cumplimiento de normas](https://go.microsoft.com/fwlink/?linkid=627084) para identificar la suspensión asociada con un caso de exhibición de documentos electrónicos que se aplica a los buzones de correo. Usar el GUID (sin incluir el `UniH` prefijo) para la exhibición de documentos electrónicos espera que ha identificado en el paso 1. Tenga en cuenta que el segundo comando muestra el nombre de la suspensión está asociada; el caso de exhibición de documentos electrónicos el tercer comando muestra el nombre de la suspensión.</span><span class="sxs-lookup"><span data-stu-id="899b8-p130">Run the following commands in [Security &amp; Compliance Center PowerShell](https://go.microsoft.com/fwlink/?linkid=627084) to identify the hold associated with an eDiscovery case that's applied to the mailbox. Use the GUID (not including the  `UniH` prefix) for the eDiscovery hold that you identified in Step 1. Note that the second command displays the name of the eDiscovery case the hold is associated with; the third command displays the name of the hold.</span></span> 
  
```
$CaseHold = Get-CaseHoldPolicy <hold GUID without prefix>
```

```
Get-ComplianceCase $CaseHold.CaseId | FL Name
```

```
$CaseHold.Name
```

<span data-ttu-id="899b8-p131">Una vez que ha identificado el nombre del caso de exhibición de documentos electrónicos y la suspensión, vaya a la **búsqueda &amp; investigación** \> página de **exhibición de documentos electrónicos** en la seguridad &amp; centro de cumplimiento, abra el caso y quitar el buzón de correo de la suspensión. Para obtener más información, vea [administrar casos de exhibición de documentos electrónicos en la seguridad de Office 365 &amp; centro de cumplimiento](manage-ediscovery-cases.md).</span><span class="sxs-lookup"><span data-stu-id="899b8-p131">After you've identified the name of the eDiscovery case and the hold, go to the **Search &amp; investigation** \> **eDiscovery** page in the Security &amp; Compliance Center, open the case, and remove the mailbox from the hold. For more information, see [Manage eDiscovery cases in the Office 365 Security &amp; Compliance Center](manage-ediscovery-cases.md).</span></span>
  
## <a name="step-4-remove-the-delay-hold-from-the-mailbox"></a><span data-ttu-id="899b8-227">Paso 4: Quitar la suspensión de retraso desde el buzón de correo</span><span class="sxs-lookup"><span data-stu-id="899b8-227">Step 4: Remove the delay hold from the mailbox</span></span>

<span data-ttu-id="899b8-p132">Después de quita cualquier tipo de espera de un buzón de correo, el valor de la propiedad del buzón de correo de *DelayHoldApplied* se establece en **True**. Esto se denomina un *retraso suspensión* y significa que la eliminación real de la suspensión se retrasa durante 30 días impedir que los datos que se eliminan permanentemente (purga) desde el buzón de correo.   Cuando se coloca una suspensión de retraso en el buzón de correo, el buzón aún se considera que esté en espera para una duración ilimitada, como si el buzón estaba en suspensión por litigio. (El propósito de una suspensión de retraso es para dar a los administradores una oportunidad para buscar o recuperar los elementos del buzón de correo que se purgarán después de que se ha quitado una suspensión). Noe que después de 30 días, mantenga el retraso caduca y Office 365 automáticamente intenta quitar la suspensión de retraso (estableciendo la propiedad *DelayHoldApplied* en **False**) para que se quitarán realmente la suspensión.</span><span class="sxs-lookup"><span data-stu-id="899b8-p132">After any type of hold is removed from a mailbox, the value of the *DelayHoldApplied* mailbox property is set to **True**. This is called a *delay hold* and means that the actual removal of the hold is delayed for 30 days to prevent data from being permanently deleted (purged) from the mailbox.   When a delay hold is placed on the mailbox, the mailbox is still considered to be on hold for an unlimited duration, as if the mailbox was on Litigation Hold. (The purpose of a delay hold is to give admins an opportunity to search for or recover mailbox items that will be purged after a hold is removed.) Noe that after 30 days, the delay hold expires, and Office 365 will automatically attempt to remove the delay hold (by setting the *DelayHoldApplied* property to **False**) so that the hold will be actually removed.</span></span> 

<span data-ttu-id="899b8-p133">Antes de eliminar los elementos en el paso 5, se debe quitar la suspensión de retraso desde el buzón de correo. Ejecute el siguiente comando en Exchange Online PowerShell para quitar la suspensión de retraso:</span><span class="sxs-lookup"><span data-stu-id="899b8-p133">Before you can delete items in Step 5, you have to remove the delay hold from the mailbox. Run the following command in Exchange Online PowerShell to remove the delay hold:</span></span> 
 
```
Set-Mailbox <username> -RemoveDelayHoldApplied
```
<span data-ttu-id="899b8-234">Tenga en cuenta que debe ser asignado el rol de suspensión Legal en Exchange en línea para usar el parámetro *RemoveDelayHoldApplied* .</span><span class="sxs-lookup"><span data-stu-id="899b8-234">Note that you must be assigned the Legal Hold role in Exchange Online to use the *RemoveDelayHoldApplied* parameter.</span></span>

<span data-ttu-id="899b8-235">Para comprobar que se ha quitado la suspensión de retraso, ejecute el siguiente comando.</span><span class="sxs-lookup"><span data-stu-id="899b8-235">To verify that delay hold has been removed, run the following command.</span></span>

```
Get-Mailbox <username> | FL DelayHoldApplied
```

<span data-ttu-id="899b8-236">El valor **False** para la propiedad *DelayHoldApplied* indica que se ha quitado el retraso.</span><span class="sxs-lookup"><span data-stu-id="899b8-236">The value of **False** for the *DelayHoldApplied* property indicates the delay has been removed.</span></span>

## <a name="step-5-delete-items-in-the-recoverable-items-folder"></a><span data-ttu-id="899b8-237">Paso 5: Eliminar elementos de la carpeta elementos recuperables</span><span class="sxs-lookup"><span data-stu-id="899b8-237">Step 5: Delete items in the Recoverable Items folder</span></span>

<span data-ttu-id="899b8-p134">Ahora está listo para eliminar realmente los elementos en la carpeta elementos recuperables mediante el cmdlet [Search-Mailbox](https://go.microsoft.com/fwlink/?linkid=852595) en Exchange Online PowerShell. Dispone de tres opciones cuando se ejecuta el cmdlet **Search-Mailbox** .</span><span class="sxs-lookup"><span data-stu-id="899b8-p134">Now you're ready to actually delete items in the Recoverable Items folder by using the [Search-Mailbox](https://go.microsoft.com/fwlink/?linkid=852595) cmdlet in Exchange Online PowerShell. You have three options when running the **Search-Mailbox** cmdlet.</span></span> 
  
- <span data-ttu-id="899b8-240">Copie los elementos en un buzón de destino antes de eliminar para que puedan consultar los elementos, si es necesario, antes de eliminarlos.</span><span class="sxs-lookup"><span data-stu-id="899b8-240">Copy items to a target mailbox before you delete them so that you can review the items, if necessary, before you delete them.</span></span>
    
- <span data-ttu-id="899b8-241">Copie los elementos a un buzón de destino y eliminarlos en el mismo comando.</span><span class="sxs-lookup"><span data-stu-id="899b8-241">Copy items to a target mailbox and delete them in the same command.</span></span>
    
- <span data-ttu-id="899b8-242">Eliminar elementos sin copiarlos en un buzón de destino.</span><span class="sxs-lookup"><span data-stu-id="899b8-242">Delete items without copying them to a target mailbox.</span></span> 
    
<span data-ttu-id="899b8-p135">Tenga en cuenta que los elementos en la carpeta elementos recuperables en el buzón del usuario archivo principal también se eliminará cuando se ejecuta el \*\* Search-Mailbox \*\* cmdlet. Para evitar esto, puede incluir el modificador *DoNotIncludeArchive* . Y como se ha indicado anteriormente, si el archivado de ampliación automática está habilitada para el buzón de correo, la \*\* Search-Mailbox \*\* cmdlet no elimina los elementos de un buzón de archivo auxiliar. Para obtener más información acerca de la expansión automática archivar, vea [información general sobre el archivo ilimitado en Office 365](unlimited-archiving.md).</span><span class="sxs-lookup"><span data-stu-id="899b8-p135">Note that items in the Recoverable Items folder in the user's primary archive mailbox will also be deleted when you run the \*\* Search-Mailbox \*\* cmdlet. To prevent this, you can include the  *DoNotIncludeArchive*  switch. And as previously stated, if auto-expanding archiving is enabled for the mailbox, the \*\* Search-Mailbox \*\* cmdlet doesn't deleted items in an auxiliary archive mailbox. For more information about auto-expanding archive, see [Overview of unlimited archiving in Office 365](unlimited-archiving.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="899b8-p136">Si incluye una consulta de búsqueda (utilizando el parámetro  *SearchQuery*  ), el cmdlet **Search-Mailbox** devolverá un máximo de 10 000 elementos en los resultados de búsqueda. Por tanto, si incluye una consulta de búsqueda, es posible que deba ejecutar el comando **Search-Mailbox** varias veces para eliminar más de 10 000 elementos.</span><span class="sxs-lookup"><span data-stu-id="899b8-p136">If you include a search query (by using the  *SearchQuery*  parameter), the **Search-Mailbox** cmdlet will return a maximum of 10,000 items in the search results. Therefore if you include a search query, you might have to run the **Search-Mailbox** command multiple times to delete more than 10,000 items.</span></span> 
  
<span data-ttu-id="899b8-p137">Los siguientes ejemplos muestran la sintaxis de comando para cada una de estas opciones. Estos ejemplos se usa el `-SearchQuery size>0` valor del parámetro, que elimina todos los elementos de todas las subcarpetas de la carpeta elementos recuperables. Si necesita eliminar sólo los elementos que coinciden con las condiciones específicas, también puede usar el parámetro *SearchQuery* para especificar otras condiciones, como el asunto de un mensaje o un intervalo de fechas. Vea los [otros ejemplos de cómo utilizar el parámetro SearchQuery](#other-examples-of-using-the-searchquery-parameter) que aparece a continuación.</span><span class="sxs-lookup"><span data-stu-id="899b8-p137">The following examples show the command syntax for each of these options. These examples use the  `-SearchQuery size>0` parameter value, which deletes all items from all subfolders in the Recoverable Items folder. If you need to delete only items that match specific conditions, you can also use the  *SearchQuery*  parameter to specify other conditions, such as the subject of a message or a date range. See the [other examples of using the SearchQuery parameter](#other-examples-of-using-the-searchquery-parameter) below.</span></span> 
  
### <a name="example-1"></a><span data-ttu-id="899b8-253">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="899b8-253">Example 1</span></span>

<span data-ttu-id="899b8-p138">En este ejemplo se copian todos los elementos en la carpeta del usuario elementos recuperables en una carpeta de buzón de búsqueda de detección de la organización. Esto le permite revisar los elementos antes de eliminarlos permanentemente.</span><span class="sxs-lookup"><span data-stu-id="899b8-p138">This example copies all items in the user's Recoverable Items folder to a folder in your organization's Discovery Search Mailbox. This lets you review the items before you permanently delete them.</span></span>

```
Search-Mailbox <username> -SearchQuery size>0 -SearchDumpsterOnly -TargetMailbox "Discovery Search Mailbox" -TargetFolder "<foldername>"
```

<span data-ttu-id="899b8-p139">En el ejemplo anterior, no es necesario para copiar elementos en el buzón de búsqueda de detección. Puede copiar mensajes en cualquier buzón de destino. Sin embargo, para evitar el acceso a datos de buzones potencialmente confidencial, se recomienda copiar los mensajes a un buzón que tiene acceso restringido al personal autorizado. De forma predeterminada, acceso al buzón de búsqueda de detección predeterminado está restringido a los miembros del grupo de roles de administración de detección en Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="899b8-p139">In the previous example, it isn't required to copy items to the Discovery Search Mailbox. You can copy messages to any target mailbox. However, to prevent access to potentially sensitive mailbox data, we recommend copying messages to a mailbox that has access restricted to authorized personnel. By default, access to the default Discovery Search Mailbox is restricted to members of the Discovery Management role group in Exchange Online.</span></span> 
  
### <a name="example-2"></a><span data-ttu-id="899b8-260">Ejemplo 2</span><span class="sxs-lookup"><span data-stu-id="899b8-260">Example 2</span></span>

<span data-ttu-id="899b8-261">En este ejemplo se copian todos los elementos de la carpeta del usuario elementos recuperables en una carpeta de buzón de búsqueda de detección de la organización y, a continuación, eliminan los elementos de la carpeta del usuario elementos recuperables.</span><span class="sxs-lookup"><span data-stu-id="899b8-261">This example copies all items in the user's Recoverable Items folder to a folder in your organization's Discovery Search Mailbox and then deletes the items from the user's Recoverable Items folder.</span></span>

```
Search-Mailbox <username> -SearchQuery size>0 -SearchDumpsterOnly -TargetMailbox "Discovery Search Mailbox" -TargetFolder "<foldername>" -DeleteContent
```
 
### <a name="example-3"></a><span data-ttu-id="899b8-262">Ejemplo 3</span><span class="sxs-lookup"><span data-stu-id="899b8-262">Example 3</span></span>

<span data-ttu-id="899b8-263">En este ejemplo se eliminan todos los elementos de la carpeta del usuario elementos recuperables, sin copiarlos a un buzón de destino.</span><span class="sxs-lookup"><span data-stu-id="899b8-263">This example deletes all items in the user's Recoverable Items folder, without copying them to a target mailbox.</span></span> 

```
Search-Mailbox <username> -SearchQuery size>0 -SearchDumpsterOnly -DeleteContent
```

### <a name="other-examples-of-using-the-searchquery-parameter"></a><span data-ttu-id="899b8-264">Otros ejemplos de cómo utilizar el parámetro SearchQuery</span><span class="sxs-lookup"><span data-stu-id="899b8-264">Other examples of using the SearchQuery parameter</span></span>

<span data-ttu-id="899b8-p140">A continuación presentamos algunos ejemplos de usar el parámetro *SearchQuery* para buscar mensajes específicos. Si usa el parámetro *SearchQuery* para buscar elementos específicos, considere la posibilidad de copiar los resultados de búsqueda en un buzón de destino para que pueda revisar los resultados de búsqueda y, a continuación, revise la consulta si es necesario antes de eliminar los resultados de una búsqueda.</span><span class="sxs-lookup"><span data-stu-id="899b8-p140">Here are a few examples of using the  *SearchQuery*  parameter to find specific messages. If you use the  *SearchQuery*  parameter to search for specific items, consider copying the search results to a target mailbox so that you can review the search results and then revise the query if necessary before you delete the results of a search.</span></span> 
  
<span data-ttu-id="899b8-267">En este ejemplo se devuelve los mensajes que contienen una frase específica en el campo Asunto.</span><span class="sxs-lookup"><span data-stu-id="899b8-267">This example returns messages that contain a specific phrase in the Subject field.</span></span>
  
```
SearchQuery 'subject:"MAIL_BOX VALIDATION/UPGRADE!!!"' 
```

<span data-ttu-id="899b8-268">En este ejemplo se devuelve los mensajes que se enviaron dentro del intervalo de fechas especificado.</span><span class="sxs-lookup"><span data-stu-id="899b8-268">This example returns messages that were sent within the specified date range.</span></span>
  
```
SearchQuery 'sent>=06/01/2016 AND sent<=09/01/2016'
```
 
<span data-ttu-id="899b8-269">En este ejemplo se devuelve los mensajes que se han enviado a la persona especificada.</span><span class="sxs-lookup"><span data-stu-id="899b8-269">This example returns messages that were sent to the specified person.</span></span>

```
SearchQuery 'to:garthf@alpinehouse.com'
```
   
### <a name="verify-that-items-were-deleted"></a><span data-ttu-id="899b8-270">Compruebe que los elementos eliminados</span><span class="sxs-lookup"><span data-stu-id="899b8-270">Verify that items were deleted</span></span>

<span data-ttu-id="899b8-p141">Para comprobar que se han eliminado correctamente los elementos desde la carpeta elementos recuperables de un buzón de correo, usar el cmdlet de **Get-MailboxFolderStatistics** en Exchange Online PowerShell para comprobar el tamaño y el número de elementos en la carpeta elementos recuperables. Se pueden comparar estas estadísticas con los que se recopilan en el paso 1.</span><span class="sxs-lookup"><span data-stu-id="899b8-p141">To verify that you've successfully deleted items from the Recoverable Items folder of a mailbox, use **Get-MailboxFolderStatistics** cmdlet in Exchange Online PowerShell to check the size and number of items in Recoverable Items folder. You can compare these statistics with the ones you collected in Step 1.</span></span> 
  
<span data-ttu-id="899b8-273">Ejecute el siguiente comando para obtener el tamaño actual y el número total de elementos en carpetas y subcarpetas en la carpeta elementos recuperables en el buzón del usuario principal.</span><span class="sxs-lookup"><span data-stu-id="899b8-273">Run the following command in to get the current size and total number of items in folders and subfolders in the Recoverable Items folder in the user's primary mailbox.</span></span> 
  
```
Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
```
   
<span data-ttu-id="899b8-274">Ejecute el siguiente comando para obtener el tamaño y el número total de elementos en carpetas y subcarpetas en la carpeta elementos recuperables en el buzón de archivo del usuario.</span><span class="sxs-lookup"><span data-stu-id="899b8-274">Run the following command to get the size and total number of items in folders and subfolders in the Recoverable Items folder in the user's archive mailbox.</span></span> 

```
Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems -Archive | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
```
  
## <a name="step-6-revert-the-mailbox-to-its-previous-state"></a><span data-ttu-id="899b8-275">Paso 6: Revertir el buzón de correo a su estado anterior</span><span class="sxs-lookup"><span data-stu-id="899b8-275">Step 6: Revert the mailbox to its previous state</span></span>

<span data-ttu-id="899b8-p142">El paso final consiste en revertir el buzón de correo a su configuración anterior. Esto significa restablecer las propiedades que ha cambiado en el paso 2 y volver a aplicar las suspensiones que se quitan en el paso 3. Esto incluye:</span><span class="sxs-lookup"><span data-stu-id="899b8-p142">The final step is to revert the mailbox back to its previous configuration. This means resetting the properties that you changed in Step 2 and re-applying the holds that you removed in Step 3. This includes:</span></span>
  
- <span data-ttu-id="899b8-p143">Cambiar el período de retención de elementos eliminados copia a su valor anterior. Como alternativa, se puede deje esta opción establecida en 30 días, el valor máximo en Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="899b8-p143">Changing the deleted item retention period back to its previous value. Alternatively, you can just leave this set to 30 days, the maximum value in Exchange Online.</span></span>
    
- <span data-ttu-id="899b8-281">Volver a habilitar la recuperación de elemento único.</span><span class="sxs-lookup"><span data-stu-id="899b8-281">Re-enabling single Item recovery.</span></span>
    
- <span data-ttu-id="899b8-282">Volver a habilitar los métodos de acceso de cliente para que el propietario puede tener acceso a su buzón.</span><span class="sxs-lookup"><span data-stu-id="899b8-282">Re-enabling the client access methods so that the owner can access their mailbox.</span></span>
    
- <span data-ttu-id="899b8-283">Volver a aplicar las directivas de retención de Office 365 que se haya quitado y suspensiones.</span><span class="sxs-lookup"><span data-stu-id="899b8-283">Re-applying the holds and Office 365 retention policies that you removed.</span></span>
    
- <span data-ttu-id="899b8-284">Volver a habilitar el Asistente para carpeta administrada para procesar el buzón de correo.</span><span class="sxs-lookup"><span data-stu-id="899b8-284">Re-enabling the Managed Folder Assistant to process the mailbox.</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="899b8-285">Se recomienda que espere 24 horas después de volver a aplicar una suspensión u Office 365 retención directiva (y bien, comprobar que sea en contexto) antes de volver a habilitar el Asistente para carpeta administrada para procesar el buzón de correo.</span><span class="sxs-lookup"><span data-stu-id="899b8-285">We recommend that you wait 24 hours after re-applying a hold or Office 365 retention policy (and verifying that it's in place) before you re-enable the Managed Folder Assistant to process the mailbox.</span></span> 
  
<span data-ttu-id="899b8-286">Realice los pasos siguientes (en la secuencia especificada) en Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="899b8-286">Perform the following steps (in the specified sequence) in Exchange Online PowerShell.</span></span>
  
1. <span data-ttu-id="899b8-p144">Ejecutar el comando siguiente para cambiar el período de retención de elementos eliminados se copia a su valor original. Esto supone que la configuración anterior es inferior a 30 días; Por ejemplo, 14 días.</span><span class="sxs-lookup"><span data-stu-id="899b8-p144">Run the following command to change the deleted item retention period back to its original value. This assumes that the previous setting is less than 30 days; for example 14 days.</span></span> 
    
    ```
    Set-Mailbox <username> -RetainDeletedItemsFor 14
    ```
   
2. <span data-ttu-id="899b8-289">Ejecute el siguiente comando para volver a habilitar la recuperación de elemento único.</span><span class="sxs-lookup"><span data-stu-id="899b8-289">Run the following command to re-enable single item recovery.</span></span>
   
    ```
    Set-Mailbox <username> -SingleItemRecoveryEnabled $true
    ```

3. <span data-ttu-id="899b8-290">Ejecute el siguiente comando para volver a habilitar todos los métodos de acceso de cliente para el buzón de correo.</span><span class="sxs-lookup"><span data-stu-id="899b8-290">Run the following command to re-enable all client access methods to the mailbox.</span></span>
    
    ```
    Set-CASMailbox <username> -EwsEnabled $true -ActiveSyncEnabled $true -MAPIEnabled $true -OWAEnabled $true -ImapEnabled $true -PopEnabled $true
    ```
   
4. <span data-ttu-id="899b8-p145">Volver a aplicar las suspensiones que se quitan en el paso 3. Según el tipo de espera, use uno de los procedimientos siguientes.</span><span class="sxs-lookup"><span data-stu-id="899b8-p145">Re-apply the holds that you removed in Step 3. Depending on the type of hold, use one of the following procedures.</span></span>
    
    <span data-ttu-id="899b8-293">**Retención por juicio**</span><span class="sxs-lookup"><span data-stu-id="899b8-293">**Litigation Hold**</span></span>
    
    <span data-ttu-id="899b8-294">Ejecute el siguiente comando para volver a habilitar un juicio para el buzón de correo.</span><span class="sxs-lookup"><span data-stu-id="899b8-294">Run the following command to re-enable a Litigation Hold for the mailbox.</span></span>
    
    ```
    Set-Mailbox <username> -LitigationHoldEnabled $true
    ```

    <span data-ttu-id="899b8-295">**In-Place Hold**</span><span class="sxs-lookup"><span data-stu-id="899b8-295">**In-Place Hold**</span></span>
    
    <span data-ttu-id="899b8-296">Use el CEF (o Exchange Online PowerShell) para volver a agregar el buzón de correo a la retención local.</span><span class="sxs-lookup"><span data-stu-id="899b8-296">Use the EAC (or Exchange Online PowerShell) to add the mailbox back to the In-Place Hold.</span></span> 
    
    <span data-ttu-id="899b8-297">**Directivas de retención 365 Office aplicadas a buzones específicos**</span><span class="sxs-lookup"><span data-stu-id="899b8-297">**Office 365 retention policies applied to specific mailboxes**</span></span>
    
    <span data-ttu-id="899b8-p146">Usar la seguridad &amp; centro de cumplimiento volver a agregar el buzón de correo a la directiva de retención de Office 365. Vaya a la **gobernanza de fecha** \> página de **retención** en la seguridad &amp; centro de cumplimiento, editar la directiva de retención y agregar el buzón de correo a la lista de destinatarios que se aplica la directiva de retención.</span><span class="sxs-lookup"><span data-stu-id="899b8-p146">Use the Security &amp; Compliance Center to add the mailbox back to the Office 365 retention policy. Go to the **Date governance** \> **Retention** page in the Security &amp; Compliance Center, edit the retention policy, and add the mailbox back to the list of recipients that the retention policy is applied to.</span></span> 
    
    <span data-ttu-id="899b8-300">**Directivas de retención de Office 365 de toda la organización**</span><span class="sxs-lookup"><span data-stu-id="899b8-300">**Organization-wide Office 365 retention policies**</span></span>
    
    <span data-ttu-id="899b8-p147">Si elimina una directiva de retención de toda la Exchange o de toda la organización mediante la exclusión de la directiva, a continuación, usar la seguridad &amp; excluidos de centro de cumplimiento para quitar el buzón de correo de la lista de los usuarios. Vaya a la **gobernanza de fecha** \> página de **retención** en la seguridad &amp; centro de cumplimiento, editar la directiva de retención de toda la organización y quitar el buzón de correo de la lista de destinatarios excluidos. De esta forma volver a aplicar la directiva de retención para el buzón del usuario.</span><span class="sxs-lookup"><span data-stu-id="899b8-p147">If you removed an organization-wide or Exchange-wide retention policy by excluding it from the policy, then use the Security &amp; Compliance Center to remove the mailbox from the list of excluded users. Go to the **Date governance** \> **Retention** page in the Security &amp; Compliance Center, edit the organization-wide retention policy, and remove the mailbox from the list of excluded recipients. Doing this will re-apply the retention policy to the user's mailbox.</span></span> 
    
    <span data-ttu-id="899b8-304">**contiene el caso de exhibición de documentos electrónicos**</span><span class="sxs-lookup"><span data-stu-id="899b8-304">**eDiscovery case holds**</span></span>
    
    <span data-ttu-id="899b8-p148">Usar la seguridad &amp; centro de cumplimiento para agregar el buzón de hacer una copia de la suspensión a la que está asociado con un caso de exhibición de documentos electrónicos. Vaya a la **búsqueda &amp; investigación** \> página de **exhibición de documentos electrónicos** en la seguridad &amp; centro de cumplimiento, abra el caso y vuelva a agregar el buzón de correo a la suspensión.</span><span class="sxs-lookup"><span data-stu-id="899b8-p148">Use the Security &amp; Compliance Center to add the mailbox back the hold that's associated with an eDiscovery case. Go to the **Search &amp; investigation** \> **eDiscovery** page in the Security &amp; Compliance Center, open the case, and add the mailbox back to the hold.</span></span> 
    
5. <span data-ttu-id="899b8-p149">Ejecute el siguiente comando para permitir que el Asistente para carpeta administrada volver a procesar el buzón de correo. Como se mencionó anteriormente, se recomienda que espere 24 horas después de volver a aplicar una suspensión u Office 365 retención directiva (y bien, comprobar que sea en contexto) antes de volver a habilitar el Asistente para carpeta administrada.</span><span class="sxs-lookup"><span data-stu-id="899b8-p149">Run the following command to allow the Managed Folder Assistant to process the mailbox again. As previously stated, we recommend that you wait 24 hours after re-applying a hold or Office 365 retention policy (and verifying that it's in place) before you re-enable the Managed Folder Assistant.</span></span> 

    ```
    Set-Mailbox <username> -ElcProcessingDisabled $false
    ```
   
6. <span data-ttu-id="899b8-309">Para comprobar que el buzón de correo se ha revertido a su configuración anterior, puede ejecutar los siguientes comandos y, a continuación, compare la configuración a los que se recopilan en el paso 1.</span><span class="sxs-lookup"><span data-stu-id="899b8-309">To verify that the mailbox has been reverted back to its previous configuration, you can run the following commands and then compare the settings to the ones that you collected in Step 1.</span></span>

    ```
    Get-Mailbox <username> | FL ElcProcessingDisabled,InPlaceHolds,LitigationHoldEnabled,RetainDeletedItemsFor,SingleItemRecoveryEnabled
    ```

    ```
    Get-CASMailbox <username> | FL EwsEnabled,ActiveSyncEnabled,MAPIEnabled,OWAEnabled,ImapEnabled,PopEnabled
    ```
  
## <a name="more-information"></a><span data-ttu-id="899b8-310">Más información</span><span class="sxs-lookup"><span data-stu-id="899b8-310">More information</span></span>

<span data-ttu-id="899b8-p150">Aquí es una tabla que describe cómo identificar diferentes tipos de suspensiones según los valores de la propiedad *InPlaceHolds* al ejecutar los cmdlets **Get-Mailbox** o **Get-OrganizationConfig** . Para obtener información más detallada, vea [cómo se identifica el tipo de suspensión colocado en un buzón de Exchange Online](identify-a-hold-on-an-exchange-online-mailbox.md).</span><span class="sxs-lookup"><span data-stu-id="899b8-p150">Here's a table that describes how to identify different types of holds based on the values in the  *InPlaceHolds*  property when you run the **Get-Mailbox** or **Get-OrganizationConfig** cmdlets. For more detailed information, see [How to identify the type of hold placed on an Exchange Online mailbox](identify-a-hold-on-an-exchange-online-mailbox.md).</span></span>

<span data-ttu-id="899b8-313">Como ya se explica, tiene que quitar todas las suspensiones y las directivas de retención de Office 365 desde un buzón de correo antes de que pueden eliminar correctamente los elementos en la carpeta elementos recuperables.</span><span class="sxs-lookup"><span data-stu-id="899b8-313">As previously explained, you have to remove all holds and Office 365 retention policies from a mailbox before you can successfully delete items in the Recoverable Items folder.</span></span> 
  
|<span data-ttu-id="899b8-314">**Tipo de suspensión**</span><span class="sxs-lookup"><span data-stu-id="899b8-314">**Hold type**</span></span>|<span data-ttu-id="899b8-315">**Valor de ejemplo**</span><span class="sxs-lookup"><span data-stu-id="899b8-315">**Example value**</span></span>|<span data-ttu-id="899b8-316">**Cómo identificar la suspensión**</span><span class="sxs-lookup"><span data-stu-id="899b8-316">**How to identify the hold**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="899b8-317">Retención por juicio</span><span class="sxs-lookup"><span data-stu-id="899b8-317">Litigation Hold</span></span>  <br/> | `True` <br/> |<span data-ttu-id="899b8-318">La propiedad *LitigationHoldEnabled* está establecida en `True`.</span><span class="sxs-lookup"><span data-stu-id="899b8-318">The  *LitigationHoldEnabled*  property is set to  `True`.</span></span>  <br/> |
|<span data-ttu-id="899b8-319">Retención en contexto</span><span class="sxs-lookup"><span data-stu-id="899b8-319">In-Place Hold</span></span>  <br/> | `c0ba3ce811b6432a8751430937152491` <br/> |<span data-ttu-id="899b8-p151">La propiedad *InPlaceHolds* contiene el GUID de la retención local que se coloca en el buzón de correo. Puede saber que esto es una retención local debido a que el GUID no se inicia con un prefijo.</span><span class="sxs-lookup"><span data-stu-id="899b8-p151">The  *InPlaceHolds*  property contains the GUID of the In-Place Hold that's placed on the mailbox. You can tell this is an In-Place Hold because the GUID doesn't start with a prefix.  </span></span><br/> <span data-ttu-id="899b8-322">Puede usar la ' Get-MailboxSearch - InPlaceHoldIdentity<hold GUID></span><span class="sxs-lookup"><span data-stu-id="899b8-322">You can use the  \`Get-MailboxSearch -InPlaceHoldIdentity <hold GUID></span></span> | <span data-ttu-id="899b8-323">FL' command en Exchange Online PowerShell para obtener información acerca de la retención local en el buzón de correo.</span><span class="sxs-lookup"><span data-stu-id="899b8-323">FL\` command in Exchange Online PowerShell to get information about the In-Place Hold on the mailbox.</span></span>  <br/> |
| <span data-ttu-id="899b8-324">Las directivas de retención de Office 365 en la seguridad &amp; centro de cumplimiento que se aplican a buzones específicos</span><span class="sxs-lookup"><span data-stu-id="899b8-324">Office 365 retention policies in the Security &amp; Compliance Center applied to specific mailboxes</span></span>  <br/> | `mbxcdbbb86ce60342489bff371876e7f224` <br/> <span data-ttu-id="899b8-325">o</span><span class="sxs-lookup"><span data-stu-id="899b8-325">or</span></span>  <br/>  `skp127d7cf1076947929bf136b7a2a8c36f` <br/> |<span data-ttu-id="899b8-p152">Cuando se ejecuta el cmdlet **Get-Mailbox** , la propiedad *InPlaceHolds* contiene también las directivas de retención de los GUID de Office 365 aplicadas al buzón. Puede identificar las directivas de retención porque el GUID comienza por la `mbx` prefijo. Tenga en cuenta que si el GUID de la directiva de retención se inicia con el `skp` prefijo, que indica que se aplica la directiva de retención a Skype para conversaciones de negocios.</span><span class="sxs-lookup"><span data-stu-id="899b8-p152">When you run the **Get-Mailbox** cmdlet, the  *InPlaceHolds*  property also contains GUIDs of Office 365 retention policies applied to the mailbox. You can identify retention policies because the GUID starts with the  `mbx` prefix. Note that if the GUID of the retention policy starts with the  `skp` prefix, that indicates that the retention policy is applied to Skype for Business conversations.  </span></span><br/> <span data-ttu-id="899b8-329">En directiva de retención de Office 365 de identidad que se aplica a los buzones de correo, ejecute el siguiente comando en seguridad &amp; PowerShell de centro de cumplimiento:</span><span class="sxs-lookup"><span data-stu-id="899b8-329">To identity the Office 365 retention policy that's applied to the mailbox, run the following command in Security &amp; Compliance Center PowerShell:</span></span> <br/> <br/><span data-ttu-id="899b8-330">' Get-RetentionCompliancePolicy<retention policy GUID without prefix></span><span class="sxs-lookup"><span data-stu-id="899b8-330">\`Get-RetentionCompliancePolicy <retention policy GUID without prefix></span></span> | <span data-ttu-id="899b8-331">Nombre de FL`<br/><br/>Be sure to remove the  `los buzones` or  `skp' prefijo al ejecutar este comando.</span><span class="sxs-lookup"><span data-stu-id="899b8-331">FL Name`<br/><br/>Be sure to remove the  `mbx` or  `skp\` prefix when you run this command.</span></span>  <br/> |
|<span data-ttu-id="899b8-332">Las directivas de retención de Office 365 de toda la organización en la seguridad &amp; centro de cumplimiento</span><span class="sxs-lookup"><span data-stu-id="899b8-332">Organization-wide Office 365 retention policies in the Security &amp; Compliance Center</span></span>  <br/> |<span data-ttu-id="899b8-333">Ningún valor</span><span class="sxs-lookup"><span data-stu-id="899b8-333">No value</span></span>  <br/> <span data-ttu-id="899b8-334">o</span><span class="sxs-lookup"><span data-stu-id="899b8-334">or</span></span>  <br/>  <span data-ttu-id="899b8-335">`-mbxe9b52bf7ab3b46a286308ecb29624696`(indica que el buzón de correo está excluido de una directiva de toda la organización)</span><span class="sxs-lookup"><span data-stu-id="899b8-335">`-mbxe9b52bf7ab3b46a286308ecb29624696` (indicates that the mailbox is excluded from an organization-wide policy)</span></span>  <br/> |<span data-ttu-id="899b8-336">Incluso si la propiedad *InPlaceHolds* está vacía cuando se ejecuta el cmdlet **Get-Mailbox** , aún puede haber uno o más toda la organización Office 365 aplicadas políticas de retención para el buzón de correo.</span><span class="sxs-lookup"><span data-stu-id="899b8-336">Even if the  *InPlaceHolds*  property is empty when you run the **Get-Mailbox** cmdlet, there still might be one or more organization-wide Office 365 retention policies applied to the mailbox.</span></span>  <br/> <span data-ttu-id="899b8-337">Para comprobar esto, puede ejecutar el ' Get-OrganizationConfig</span><span class="sxs-lookup"><span data-stu-id="899b8-337">To verify this, you can run the  \`Get-OrganizationConfig</span></span> | <span data-ttu-id="899b8-338">FL InPlaceHolds` command in Exchange Online PowerShell to get a list of the GUIDs for organization-wide Office 365 retention policies. The GUID for organization-wide retention policies applied to Exchange mailboxes start with the  `los buzones` prefix; for example  `mbxa3056bb15562480fadb46ce523ff7b02`.  <br/> To identity the organization-wide Office 365 retention policy that's applied to the mailbox, run the following command in Security &amp; Compliance Center PowerShell: <br/><br/> `Get-RetentionCompliancePolicy<retention policy GUID without prefix></span><span class="sxs-lookup"><span data-stu-id="899b8-338">FL InPlaceHolds` command in Exchange Online PowerShell to get a list of the GUIDs for organization-wide Office 365 retention policies. The GUID for organization-wide retention policies applied to Exchange mailboxes start with the  `mbx` prefix; for example  `mbxa3056bb15562480fadb46ce523ff7b02`.  <br/> To identity the organization-wide Office 365 retention policy that's applied to the mailbox, run the following command in Security &amp; Compliance Center PowerShell: <br/><br/> `Get-RetentionCompliancePolicy <retention policy GUID without prefix></span></span> | <span data-ttu-id="899b8-339">Nombre de FL`<br/><br/>Note that if a mailbox is excluded from an organization-wide Office 365 retention policy, the GUID for the retention policy is displayed in the  *InPlaceHolds*  property of the user's mailbox when you run the **Get-Mailbox** cmdlet; it's identified by the prefix  `los buzones -`; for example,  `-mbxe9b52bf7ab3b46a286308ecb29624696'</span><span class="sxs-lookup"><span data-stu-id="899b8-339">FL Name`<br/><br/>Note that if a mailbox is excluded from an organization-wide Office 365 retention policy, the GUID for the retention policy is displayed in the  *InPlaceHolds*  property of the user's mailbox when you run the **Get-Mailbox** cmdlet; it's identified by the prefix  `-mbx`; for example,  `-mbxe9b52bf7ab3b46a286308ecb29624696\`</span></span> <br/> |
|<span data-ttu-id="899b8-340">conservación de caso de exhibición de documentos electrónicos en la seguridad &amp; centro de cumplimiento</span><span class="sxs-lookup"><span data-stu-id="899b8-340">eDiscovery case hold in the Security &amp; Compliance Center</span></span>  <br/> | `UniH7d895d48-7e23-4a8d-8346-533c3beac15d` <br/> |<span data-ttu-id="899b8-p153">La propiedad *InPlaceHolds* también contiene el GUID de cualquier suspensión asociado con un caso de exhibición de documentos electrónicos en la seguridad &amp; centro de cumplimiento que se puede colocar en el buzón de correo. Puede saber esto es una suspensión de casos de exhibición de documentos electrónicos porque el GUID comienza por la `UniH` prefijo.</span><span class="sxs-lookup"><span data-stu-id="899b8-p153">The  *InPlaceHolds*  property also contains the GUID of any hold associated with an eDiscovery case in the Security &amp; Compliance Center that might be placed on the mailbox. You can tell this is an eDiscovery case hold because the GUID starts with the  `UniH` prefix.  </span></span><br/> <span data-ttu-id="899b8-p154">Puede usar el `Get-CaseHoldPolicy` cmdlet en seguridad &amp; PowerShell de centro de cumplimiento para obtener información sobre el caso de exhibición de documentos electrónicos que está asociada la suspensión en el buzón de correo. Por ejemplo, puede ejecutar el comando ' Get-CaseHoldPolicy<hold GUID without prefix></span><span class="sxs-lookup"><span data-stu-id="899b8-p154">You can use the  `Get-CaseHoldPolicy` cmdlet in Security &amp; Compliance Center PowerShell to get information about the eDiscovery case that the hold on the mailbox is associated with. For example, you can run the command  \`Get-CaseHoldPolicy <hold GUID without prefix></span></span> | <span data-ttu-id="899b8-345">Nombre de FL` to display the name of the case hold that's on the mailbox. Be sure to remove the  `UniH` prefix when you run this command.  <br/><br/> To identity the eDiscovery case that the hold on the mailbox is associated with, run the following commands:<br/><br/>`$CaseHold = Get-CaseHoldPolicy <hold GUID without prefix> `<br/><br/>`$CaseHold.CaseId Get-ComplianceCase</span><span class="sxs-lookup"><span data-stu-id="899b8-345">FL Name` to display the name of the case hold that's on the mailbox. Be sure to remove the  `UniH` prefix when you run this command.  <br/><br/> To identity the eDiscovery case that the hold on the mailbox is associated with, run the following commands:<br/><br/>`$CaseHold = Get-CaseHoldPolicy <hold GUID without prefix>`<br/><br/>`Get-ComplianceCase $CaseHold.CaseId</span></span> | <span data-ttu-id="899b8-346">Nombre de FL'</span><span class="sxs-lookup"><span data-stu-id="899b8-346">FL Name\`</span></span>


