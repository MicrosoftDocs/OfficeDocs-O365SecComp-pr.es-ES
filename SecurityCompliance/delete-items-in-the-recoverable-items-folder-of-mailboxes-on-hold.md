---
title: Eliminar elementos de la carpeta elementos recuperables de buzones de correo basados en la nube en suspensión-ayuda de administración
ms.author: markjjo
author: markjjo
manager: laurawi
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: a85e1c87-a48e-4715-bfa9-d5275cde67b0
description: 'Para los administradores: Elimine los elementos de la carpeta elementos recuperables de un usuario para un buzón de correo de Exchange Online, incluso si el buzón se encuentra en retención legal. Esta es una forma eficaz de eliminar datos que se han derramado accidentalmente en Office 365.'
ms.openlocfilehash: 4b7b12b33a2364d76b5d7dab6c7e94dc8f00d151
ms.sourcegitcommit: baf23be44f1ed5abbf84f140b5ffa64fce605478
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/26/2019
ms.locfileid: "30296183"
---
# <a name="delete-items-in-the-recoverable-items-folder-of-cloud-based-mailboxes-on-hold---admin-help"></a><span data-ttu-id="cfcf2-104">Eliminar elementos de la carpeta elementos recuperables de buzones de correo basados en la nube en suspensión-ayuda de administración</span><span class="sxs-lookup"><span data-stu-id="cfcf2-104">Delete items in the Recoverable Items folder of cloud-based mailboxes on hold - Admin Help</span></span>

<span data-ttu-id="cfcf2-p102">La carpeta elementos recuperables de un buzón de Exchange Online existe para protegerse de eliminaciones accidentales o malintencionadas. También se usa para almacenar elementos que se conservan y a los que acceden las características de cumplimiento de Office 365, como las búsquedas de exhibición de documentos electrónicos y las suspensiones. Sin embargo, en algunos casos, las organizaciones pueden tener datos que se conservan de forma involuntaria en la carpeta elementos recuperables que deben eliminar. Por ejemplo, un usuario podría enviar o reenviar sin saberlo un mensaje de correo electrónico que contenga información confidencial o información que pueda tener consecuencias serias para la empresa. Incluso si el mensaje se elimina de forma permanente, es posible que se retenga indefinidamente, ya que se ha realizado una suspensión legal en el buzón. Este escenario se conoce como derrame de datos porque los datos se han derramado involuntariamente en Office 365. En estas situaciones, puede eliminar los elementos de la carpeta elementos recuperables de un usuario para un buzón de correo de Exchange Online, incluso si ese buzón se coloca en suspensión con una de las diferentes características de retención en Office 365. Estos tipos de retenciones incluyen reTenciones por juicio, suspensiones locales, suspensiones de exhibición de documentos electrónicos y directivas de retención &amp; de Office 365 creadas en el centro de seguridad y cumplimiento de Office 365.</span><span class="sxs-lookup"><span data-stu-id="cfcf2-p102">The Recoverable Items folder for an Exchange Online mailbox exists to protect from accidental or malicious deletions. It's also used to store items that are retained and accessed by Office 365 compliance features, such as holds and eDiscovery searches. However, in some situations organizations might have data that's been unintentionally retained in the Recoverable Items folder that they must delete. For example, a user might unknowingly send or forward an email message that contains sensitive information or information that may have serious business consequences. Even if the message is permanently deleted, it might be retained indefinitely because a legal hold has been placed on the mailbox. This scenario is known as data spillage because data has been unintentionally spilled into Office 365. In these situations, you can delete items in a user's Recoverable Items folder for an Exchange Online mailbox, even if that mailbox is placed on hold with one of the different hold features in Office 365. These types of holds include Litigation Holds, In-Place Holds, eDiscovery holds, and Office 365 retention policies created in the Office 365 Security &amp; Compliance Center.</span></span> 
  
 <span data-ttu-id="cfcf2-p103">En este artículo se explica cómo eliminar elementos de la carpeta elementos recuperables para los buzones de correo basados en la nube que están en suspensión. Este procedimiento implica deshabilitar el acceso al buzón y deshabilitar la recuperación de un único elemento, deshabilitar el Asistente para carpeta administrada para procesar el buzón, quitar temporalmente la retención, eliminar elementos de la carpeta elementos recuperables y, a continuación, revertir el buzón a su configuración anterior. Este es el proceso:</span><span class="sxs-lookup"><span data-stu-id="cfcf2-p103">This article explains how to delete items from the Recoverable Items folder for cloud-based mailboxes that are on hold. This procedure involves disabling access to the mailbox and disabling single item recovery, disabling the Managed Folder Assistant from processing the mailbox, temporarily removing the hold, deleting items from the Recoverable Items folder, and then reverting the mailbox to its previous configuration. Here's the process:</span></span> 
  
[<span data-ttu-id="cfcf2-116">Paso 1: recopilar información sobre el buzón</span><span class="sxs-lookup"><span data-stu-id="cfcf2-116">Step 1: Collect information about the mailbox</span></span>](#step-1-collect-information-about-the-mailbox)

[<span data-ttu-id="cfcf2-117">Paso 2: preparar el buzón de correo</span><span class="sxs-lookup"><span data-stu-id="cfcf2-117">Step 2: Prepare the mailbox</span></span>](#step-2-prepare-the-mailbox)

[<span data-ttu-id="cfcf2-118">Paso 3: quitar todas las suspensiones del buzón</span><span class="sxs-lookup"><span data-stu-id="cfcf2-118">Step 3: Remove all holds from the mailbox</span></span>](#step-3-remove-all-holds-from-the-mailbox)

[<span data-ttu-id="cfcf2-119">Paso 4: quitar la retención por retraso del buzón</span><span class="sxs-lookup"><span data-stu-id="cfcf2-119">Step 4: Remove the delay hold from the mailbox</span></span>](#step-4-remove-the-delay-hold-from-the-mailbox)

[<span data-ttu-id="cfcf2-120">Paso 5: eliminar elementos de la carpeta elementos recuperables</span><span class="sxs-lookup"><span data-stu-id="cfcf2-120">Step 5: Delete items in the Recoverable Items folder</span></span>](#step-5-delete-items-in-the-recoverable-items-folder)

[<span data-ttu-id="cfcf2-121">Paso 6: revertir el buzón a su estado anterior</span><span class="sxs-lookup"><span data-stu-id="cfcf2-121">Step 6: Revert the mailbox to its previous state</span></span>](#step-6-revert-the-mailbox-to-its-previous-state)
  
> [!CAUTION]
> <span data-ttu-id="cfcf2-p104">Los procedimientos descritos en este artículo harán que los datos se eliminen de forma permanente (purga) de un buzón de correo de Exchange Online. Esto significa que los mensajes que elimine de la carpeta elementos recuperables no se pueden recuperar y no estarán disponibles para la detección legal o para otros fines de cumplimiento. Si desea eliminar mensajes de un buzón de correo que está en retención como parte de una retención por juicio, la retención local, la retención de eDiscovery o la Directiva de retención de Office 365 creada en el centro &amp; de seguridad y cumplimiento de Office 365, consulte la administración de registros o legal. departamentos antes de quitar la suspensión. Es posible que su organización tenga una directiva que defina si un buzón de correo en espera o un incidente de derrame de datos tiene prioridad.</span><span class="sxs-lookup"><span data-stu-id="cfcf2-p104">The procedures outlined in this article will result in data being permanently deleted (purged) from an Exchange Online mailbox. That means messages that you delete from the Recoverable Items folder can't be recovered and won't be available for legal discovery or other compliance purposes. If you want to delete messages from a mailbox that's placed on hold as part of a Litigation Hold, In-Place Hold, eDiscovery hold, or Office 365 retention policy created in the Office 365 Security &amp; Compliance Center, check with your records management or legal departments before removing the hold. Your organization might have a policy that defines whether a mailbox on hold or a data spillage incident takes priority.</span></span> 
  
## <a name="before-you-begin"></a><span data-ttu-id="cfcf2-126">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="cfcf2-126">Before you begin</span></span>

- <span data-ttu-id="cfcf2-127">Debe tener asignados los siguientes roles de administración en Exchange Online para buscar y eliminar mensajes de la carpeta elementos recuperables en el paso 5.</span><span class="sxs-lookup"><span data-stu-id="cfcf2-127">You have to be assigned both of the following management roles in Exchange Online to search for and delete messages from the Recoverable Items folder in Step 5.</span></span>
    
  - <span data-ttu-id="cfcf2-p105">**Búsqueda** en buzones: este rol permite buscar buzones de correo en la organización. De forma predeterminada, los administradores de Exchange no tienen asignado este rol. Para asignarse a sí mismo el rol, agréguelo como miembro del grupo de roles de administración de detección en Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="cfcf2-p105">**Mailbox Search** - This role lets you to search mailboxes in your organization. Exchange administrators aren't assigned this role by default. To assign yourself this role, add yourself as a member of the Discovery Management role group in Exchange Online.</span></span> 
    
  - <span data-ttu-id="cfcf2-p106">**Importación y exportación** de buzones: este rol permite eliminar mensajes del buzón de un usuario. De forma predeterminada, este rol no está asignado a ningún grupo de roles. Para eliminar mensajes de los buzones de los usuarios, puede Agregar el rol importación y exportación de buzones al grupo de roles administración de la organización en Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="cfcf2-p106">**Mailbox Import Export** - This role lets you to delete messages from a user's mailbox. By default, this role isn't assigned to any role group. To delete messages from users' mailboxes, you can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> 
    
- <span data-ttu-id="cfcf2-p107">El procedimiento descrito en este artículo no es compatible con los buzones inactivos. Esto se debe a que no puede volver a aplicar una retención (o una directiva de retención de Office 365) a un buzón inactivo después de quitarlo. Cuando se quita una retención de un buzón inactivo, se cambia a un buzón de correo eliminado temporalmente y se elimina permanentemente de la organización una vez que lo procesa el Asistente para carpeta administrada.</span><span class="sxs-lookup"><span data-stu-id="cfcf2-p107">The procedure described in this article isn't supported for inactive mailboxes. That's because you can't re-apply a hold (or Office 365 retention policy) to an inactive mailbox after you remove it. When you remove a hold from an inactive mailbox, it's changed to a normal soft-deleted mailbox and will be permanently deleted from your organization after it's processed by the Managed Folder Assistant.</span></span>
    
- <span data-ttu-id="cfcf2-p108">No puede realizar este procedimiento para un buzón que se ha asignado a una directiva de retención de Office 365 que se ha bloqueado con un bloqueo de conservación. Esto se debe a que un bloqueo de conservación impide quitar o excluir el buzón de la Directiva de retención de Office 365 y deshabilitar el Asistente para carpeta administrada en el buzón. Para obtener más información acerca de las directivas de retención de bloqueo, consulte [bloquear una directiva de retención](retention-policies.md#locking-a-retention-policy).</span><span class="sxs-lookup"><span data-stu-id="cfcf2-p108">You can't perform this procedure for a mailbox that has been assigned to an Office 365 retention policy that's been locked with a Preservation Lock. That's because a Preservation Lock prevents you from removing or excluding the mailbox from the Office 365 retention policy and from disabling the Managed Folder Assistant on the mailbox. For more information about locking retention policies, see [Locking a retention policy](retention-policies.md#locking-a-retention-policy).</span></span>
    
- <span data-ttu-id="cfcf2-p109">Si un buzón no se coloca en suspensión (o no tiene habilitada la recuperación de un único elemento), simplemente puede eliminar los elementos de la carpeta elementos recuperables. Para obtener más información acerca de cómo hacerlo, vea [Buscar y eliminar mensajes ](https://go.microsoft.com/fwlink/?linkid=852453).</span><span class="sxs-lookup"><span data-stu-id="cfcf2-p109">If a mailbox isn't placed on hold (or doesn't have single item recovery enabled), you can simply delete the items from the Recoverable Items folder. For more information about how to do this, see [Search for and delete messages ](https://go.microsoft.com/fwlink/?linkid=852453).</span></span>
  
## <a name="step-1-collect-information-about-the-mailbox"></a><span data-ttu-id="cfcf2-142">Paso 1: recopilar información sobre el buzón</span><span class="sxs-lookup"><span data-stu-id="cfcf2-142">Step 1: Collect information about the mailbox</span></span>

<span data-ttu-id="cfcf2-p110">El primer paso consiste en recopilar propiedades seleccionadas del buzón de destino que afectarán a este procedimiento. Asegúrese de anotar esta configuración o guardarla en un archivo de texto, ya que cambiará algunas de estas propiedades y, a continuación, revertirá a los valores originales en el paso 6 después de eliminar elementos de la carpeta elementos recuperables. Esta es una lista de las propiedades de buzón que debe recopilar.</span><span class="sxs-lookup"><span data-stu-id="cfcf2-p110">This first step is to collect selected properties from the target mailbox that will affect this procedure. Be sure to write down these settings or save them to a text file because you'll change some of these properties and then revert back to the original values in Step 6, after you delete items from the Recoverable Items folder. Here's a list of the mailbox properties you need to collect.</span></span>
  
-  <span data-ttu-id="cfcf2-146">*SingleItemRecoveryEnabled* y *RetainDeletedItemsFor* ; Si es necesario, deshabilitará la recuperación única y aumentará el período de retención de elementos eliminados en el paso 3.</span><span class="sxs-lookup"><span data-stu-id="cfcf2-146">*SingleItemRecoveryEnabled*  and  *RetainDeletedItemsFor*  ; if necessary, you'll disable single recovery and increase the deleted items retention period in Step 3.</span></span> 
    
-  <span data-ttu-id="cfcf2-p111">*LitigationHoldEnabled* y *InPlaceHolds* ; debe identificar todas las suspensiones colocadas en el buzón de modo que pueda quitarlas temporalmente en el paso 3. Consulte la sección [More Information](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md#moreinfo) para obtener sugerencias sobre cómo identificar la suspensión de tipo que se puede colocar en un buzón.</span><span class="sxs-lookup"><span data-stu-id="cfcf2-p111">*LitigationHoldEnabled*  and  *InPlaceHolds*  ; you need to identify all the holds placed on the mailbox so that you can temporarily remove them in Step 3. See the [More information](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md#moreinfo) section for tips about how to identify the type hold that might be placed on a mailbox.</span></span> 
    
<span data-ttu-id="cfcf2-p112">Además, debe obtener la configuración de acceso de cliente de buzones de correo para que pueda deshabilitarla temporalmente de modo que el propietario (u otros usuarios) no pueda obtener acceso al buzón durante este procedimiento. Por último, puede obtener el tamaño actual y el número de elementos en la carpeta elementos recuperables. Después de eliminar los elementos de la carpeta elementos recuperables en el paso 5, usará esta información para comprobar que los elementos se quitaron realmente.</span><span class="sxs-lookup"><span data-stu-id="cfcf2-p112">Additionally, you need to get the mailbox client access settings so you can temporarily disable them so the owner (or other users) can't access the mailbox during this procedure. Finally, you can get the current size and number of items in the Recoverable Items folder. After you delete items in the Recoverable Items folder in Step 5, you'll use this information to verify that items were actually removed.</span></span>
  
1. <span data-ttu-id="cfcf2-p113">[Conéctese a Exchange Online PowerShell](https://go.microsoft.com/fwlink/?linkid=396554). Asegúrese de usar un nombre de usuario y una contraseña para una cuenta de administrador a la que se haya asignado el rol de administración adecuado en Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="cfcf2-p113">[Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/?linkid=396554). Be sure to use a user name and password for an administrator account that's been assigned the appropriate management roles in Exchange Online.</span></span> 
    
2. <span data-ttu-id="cfcf2-154">Ejecute el siguiente comando para obtener información sobre la recuperación de elementos individuales y el período de retención de elementos eliminados.</span><span class="sxs-lookup"><span data-stu-id="cfcf2-154">Run the following command to get information about single item recovery and the deleted item retention period.</span></span>

    ```
    Get-Mailbox <username> | FL SingleItemRecoveryEnabled,RetainDeletedItemsFor
    ```

   <span data-ttu-id="cfcf2-p114">Si la recuperación de un único elemento está habilitada, deberá deshabilitarla en el paso 2. Si el período de retención de elementos eliminados no está establecido en 30 días (el valor máximo en Exchange Online), puede aumentarlo en el paso 2.</span><span class="sxs-lookup"><span data-stu-id="cfcf2-p114">If single item recovery is enabled, you'll have to disable it in Step 2. If the deleted item retention period isn't set for 30 days (the maximum value in Exchange Online), then you can increase it in Step 2.</span></span> 
    
3. <span data-ttu-id="cfcf2-157">Ejecute el siguiente comando para obtener la configuración de acceso al buzón del buzón.</span><span class="sxs-lookup"><span data-stu-id="cfcf2-157">Run the following command to get the mailbox access settings for the mailbox.</span></span> 
    
    ```
    Get-CASMailbox <username> | FL EwsEnabled,ActiveSyncEnabled,MAPIEnabled,OWAEnabled,ImapEnabled,PopEnabled
    ```

   <span data-ttu-id="cfcf2-158">Deshabilitará todos estos métodos de acceso en el paso 2.</span><span class="sxs-lookup"><span data-stu-id="cfcf2-158">You'll disable all of these access methods in Step 2.</span></span>
    
4. <span data-ttu-id="cfcf2-159">Ejecute el siguiente comando para obtener información sobre las suspensiones y las directivas de retención de Office 365 que se aplican al buzón.</span><span class="sxs-lookup"><span data-stu-id="cfcf2-159">Run the following command to get information about the holds and Office 365 retention policies applied to the mailbox.</span></span>
    
    ```
    Get-Mailbox <username> | FL LitigationHoldEnabled,InPlaceHolds
    ```


   > [!TIP]
    > <span data-ttu-id="cfcf2-160">Si hay demasiados valores en la propiedad *InPlaceHolds* y no todos ellos se muestran, puede ejecutar el `Get-Mailbox <username> | Select-Object -ExpandProperty InPlaceHolds` comando para mostrar cada valor en una línea independiente.</span><span class="sxs-lookup"><span data-stu-id="cfcf2-160">If there are too many values in the  *InPlaceHolds*  property and not all of them are displayed, you can run the  `Get-Mailbox <username> | Select-Object -ExpandProperty InPlaceHolds` command to display each value on a separate line.</span></span> 
  
5. <span data-ttu-id="cfcf2-161">Ejecute el siguiente comando para obtener información sobre cualquier directiva de retención de Office 365 de toda la organización.</span><span class="sxs-lookup"><span data-stu-id="cfcf2-161">Run the following command to get information about any organization-wide Office 365 retention policies.</span></span> 

    ```
    Get-OrganizationConfig | FL InPlaceHolds
    ```
   <span data-ttu-id="cfcf2-162">Si su organización tiene cualquier directiva de retención de Office 365 de toda la organización, tendrá que excluir el buzón de correo de estas directivas en el paso 3.</span><span class="sxs-lookup"><span data-stu-id="cfcf2-162">If your organization has any organization-wide Office 365 retention policies, you'll have to exclude the mailbox from these policies in Step 3.</span></span>

   > [!TIP]
    > <span data-ttu-id="cfcf2-163">Si hay demasiados valores en la propiedad *InPlaceHolds* y no todos ellos se muestran, puede ejecutar el `Get-OrganizationConfig | Select-Object -ExpandProperty InPlaceHolds` comando para mostrar cada valor en una línea independiente.</span><span class="sxs-lookup"><span data-stu-id="cfcf2-163">If there are too many values in the  *InPlaceHolds*  property and not all of them are displayed, you can run the  `Get-OrganizationConfig | Select-Object -ExpandProperty InPlaceHolds` command to display each value on a separate line.</span></span> 
  
6. <span data-ttu-id="cfcf2-164">Ejecute el siguiente comando para obtener el tamaño actual y el número total de elementos de carpetas y subcarpetas en la carpeta elementos recuperables del buzón de correo principal del usuario.</span><span class="sxs-lookup"><span data-stu-id="cfcf2-164">Run the following command to get the current size and total number of items in folders and subfolders in the Recoverable Items folder in the user's primary mailbox.</span></span> 

    ```
    Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
    ```

   <span data-ttu-id="cfcf2-165">Si el buzón de archivo del usuario está habilitado, ejecute el siguiente comando para obtener el tamaño y el número total de elementos de las carpetas y subcarpetas de la carpeta elementos recuperables de su buzón de archivo.</span><span class="sxs-lookup"><span data-stu-id="cfcf2-165">If the user's archive mailbox is enabled, run the following command to get the size and total number of items in folders and subfolders in the Recoverable Items folder in their archive mailbox.</span></span> 

    ```s
    Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems -Archive | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
    ```

   <span data-ttu-id="cfcf2-p115">Al eliminar elementos en el paso 5, puede optar por eliminar o no eliminar los elementos de la carpeta elementos recuperables en el buzón de archivo principal del usuario. Tenga en cuenta que si el archivado de expansión automática está habilitado para el buzón de correo, los elementos de un buzón de archivo auxiliar no se eliminarán.</span><span class="sxs-lookup"><span data-stu-id="cfcf2-p115">When you delete items in Step 5, you can choose to delete or not delete items in the Recoverable Items folder in the user's primary archive mailbox. Note that if auto-expanding archiving is enabled for the mailbox, items in an auxiliary archive mailbox won't be deleted.</span></span>
  
## <a name="step-2-prepare-the-mailbox"></a><span data-ttu-id="cfcf2-168">Paso 2: preparar el buzón de correo</span><span class="sxs-lookup"><span data-stu-id="cfcf2-168">Step 2: Prepare the mailbox</span></span>

<span data-ttu-id="cfcf2-169">Después de recopilar y guardar información sobre el buzón de correo, el siguiente paso consiste en preparar el buzón realizando las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="cfcf2-169">After collecting and saving information about the mailbox, the next step is to prepare the mailbox by performing the following tasks:</span></span> 
  
- <span data-ttu-id="cfcf2-170">**Deshabilite el acceso del cliente al buzón** de correo para que el propietario del buzón no pueda obtener acceso a su buzón y realice cambios en los datos del buzón durante este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="cfcf2-170">**Disable client access to mailbox** so that the mailbox owner can't access their mailbox and make any changes to the mailbox data during this procedure.</span></span> 
    
- <span data-ttu-id="cfcf2-171">**Aumente el período de retención** de elementos eliminados a 30 días (el valor máximo en Exchange Online) para que los elementos no se purguen de la carpeta elementos recuperables antes de que pueda eliminarlos en el paso 5.</span><span class="sxs-lookup"><span data-stu-id="cfcf2-171">**Increase the deleted item retention period** to 30 days (the maximum value in Exchange Online) so that items aren't purged from the Recoverable Items folder before you can delete them in Step 5.</span></span> 
    
- <span data-ttu-id="cfcf2-172">**Deshabilite la recuperación** de elementos individuales para que los elementos no se conserven (durante el período de retención del elemento eliminado) después de eliminarlos de la carpeta elementos recuperables en el paso 5.</span><span class="sxs-lookup"><span data-stu-id="cfcf2-172">**Disable single Item recovery** so that items won't be retained (for the duration of the deleted item retention period) after you delete them from the Recoverable Items folder in Step 5.</span></span> 
    
- <span data-ttu-id="cfcf2-173">**Deshabilite el Asistente para carpeta administrada** para que no procese el buzón y conserve los elementos que eliminó en el paso 5.</span><span class="sxs-lookup"><span data-stu-id="cfcf2-173">**Disable the Managed Folder Assistant** so that it doesn't process the mailbox and retain the items that you delete in Step 5.</span></span> 
    
<span data-ttu-id="cfcf2-174">Realice los siguientes pasos en Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cfcf2-174">Perform the following steps in Exchange Online PowerShell.</span></span>
  
1. <span data-ttu-id="cfcf2-p116">Ejecute el siguiente comando para deshabilitar el acceso de cliente al buzón. La sintaxis del comando presupone que todos los métodos de acceso de cliente están habilitados en el buzón.</span><span class="sxs-lookup"><span data-stu-id="cfcf2-p116">Run the following command to disable all client access to the mailbox. The command syntax assumes that all client access methods were enabled on the mailbox.</span></span>

    ```   
    Set-CASMailbox <username> -EwsEnabled $false -ActiveSyncEnabled $false -MAPIEnabled $false -OWAEnabled $false -ImapEnabled $false -PopEnabled $false
    ```
   
   > [!NOTE]
    > <span data-ttu-id="cfcf2-p117">La deshabilitación de todos los métodos de acceso de cliente al buzón puede tardar hasta 60 minutos. Tenga en cuenta que, al deshabilitar estos métodos de acceso, no se desconectará el propietario del buzón en el que está actualmente conectado. Si el propietario no ha iniciado sesión, no podrá tener acceso a su buzón una vez que estos métodos de acceso estén deshabilitados.</span><span class="sxs-lookup"><span data-stu-id="cfcf2-p117">It might take up to 60 minutes to disable all client access methods to the mailbox. Note that disabling these access methods won't disconnect the mailbox owner they're currently signed in. If the owner isn't signed in, then they won't be able to access their mailbox after these access methods are disabled.</span></span> 
  
2. <span data-ttu-id="cfcf2-p118">Ejecute el siguiente comando para aumentar el período de retención de elementos eliminados durante 30 días como máximo. Se supone que la configuración actual es inferior a 30 días.</span><span class="sxs-lookup"><span data-stu-id="cfcf2-p118">Run the following command to increase the deleted item retention period the maximum of 30 days. This assumes that the current setting is less than 30 days.</span></span> 

    ```
    Set-Mailbox <username> -RetainDeletedItemsFor 30
    ```

3. <span data-ttu-id="cfcf2-182">Ejecute el siguiente comando para deshabilitar la recuperación de elementos individuales.</span><span class="sxs-lookup"><span data-stu-id="cfcf2-182">Run the following command to disable single item recovery.</span></span>
    
    ```
    Set-Mailbox <username> -SingleItemRecoveryEnabled $false
    ```

   > [!NOTE]
    > <span data-ttu-id="cfcf2-p119">La deshabilitación de la recuperación de elementos individuales puede tardar hasta 60 minutos. No elimine elementos de la carpeta elementos recuperables hasta que haya transcurrido este período.</span><span class="sxs-lookup"><span data-stu-id="cfcf2-p119">It might take up to 60 minutes to disable single item recovery. Don't delete items in the Recoverable Items folder until this period has elapsed.</span></span> 
  
4. <span data-ttu-id="cfcf2-p120">Ejecute el siguiente comando para evitar que el Asistente para carpeta administrada procese el buzón de correo. Como se ha explicado anteriormente, puede deshabilitar el Asistente para carpeta administrada solo si una directiva de retención de Office 365 con un bloqueo de conservación no se aplica al buzón.</span><span class="sxs-lookup"><span data-stu-id="cfcf2-p120">Run the following command to prevent the Managed Folder Assistant from processing the mailbox. As previously explained, you can disable the Managed Folder Assistant only if an Office 365 retention policy with a Preservation Lock is not applied to the mailbox.</span></span> 

    ```
    Set-Mailbox <username> -ElcProcessingDisabled $true
    ```

## <a name="step-3-remove-all-holds-from-the-mailbox"></a><span data-ttu-id="cfcf2-187">Paso 3: quitar todas las suspensiones del buzón</span><span class="sxs-lookup"><span data-stu-id="cfcf2-187">Step 3: Remove all holds from the mailbox</span></span>

<span data-ttu-id="cfcf2-p121">El último paso para poder eliminar elementos de la carpeta elementos recuperables es quitar todas las suspensiones (identificado en el paso 1) colocados en el buzón. Todas las suspensiones deben quitarse para que los elementos no se conserven después de eliminarlos de la carpeta elementos recuperables. Las secciones siguientes contienen información sobre cómo quitar distintos tipos de retenciones en un buzón. Consulte la sección [More Information](#more-information) para obtener sugerencias sobre cómo identificar la suspensión de tipo que se puede colocar en un buzón. Para obtener más información, consulte [How to identify The Type of Hold in a Exchange Online Mailbox](identify-a-hold-on-an-exchange-online-mailbox.md).</span><span class="sxs-lookup"><span data-stu-id="cfcf2-p121">The last step before you can delete items from the Recoverable Items folder is to remove all holds (that you identified in Step 1) placed on the mailbox. All holds must be removed so that items won't be retained after you delete them from the Recoverable Items folder. The following sections contain information about removing different types of holds on a mailbox. See the [More information](#more-information) section for tips about how to identify the type hold that might be placed on a mailbox. For additional information, see [How to identify the type of hold placed on an Exchange Online mailbox](identify-a-hold-on-an-exchange-online-mailbox.md).</span></span>
  
> [!CAUTION]
> <span data-ttu-id="cfcf2-193">Como se indicó anteriormente, consulte con la administración de registros o los departamentos jurídicos antes de quitar una retención de un buzón de correo.</span><span class="sxs-lookup"><span data-stu-id="cfcf2-193">As previously stated, check with your records management or legal departments before removing a hold from a mailbox.</span></span> 
  
 ### <a name="litigation-hold"></a><span data-ttu-id="cfcf2-194">Retención por juicio</span><span class="sxs-lookup"><span data-stu-id="cfcf2-194">Litigation Hold</span></span>
  
<span data-ttu-id="cfcf2-195">Ejecute el siguiente comando en Exchange Online PowerShell para quitar una retención por juicio del buzón.</span><span class="sxs-lookup"><span data-stu-id="cfcf2-195">Run the following command in Exchange Online PowerShell to remove a Litigation Hold from the mailbox.</span></span>

```
Set-Mailbox <username> -LitigationHoldEnabled $false
```

   
> [!NOTE]
> <span data-ttu-id="cfcf2-p122">De forma similar a la deshabilitación de los métodos de acceso de cliente y la recuperación de elementos individuales, puede tardar hasta 60 minutos en quitar la retención por juicio. No elimine elementos de la carpeta elementos recuperables hasta que haya transcurrido este período.</span><span class="sxs-lookup"><span data-stu-id="cfcf2-p122">Similar to disabling the client access methods and single item recovery, it might take up to 60 minutes to remove the Litigation Hold. Don't delete items from the Recoverable Items folder until this period has elapsed.</span></span> 
  
 ### <a name="in-place-hold"></a><span data-ttu-id="cfcf2-198">Retención en contexto</span><span class="sxs-lookup"><span data-stu-id="cfcf2-198">In-Place Hold</span></span>
  
<span data-ttu-id="cfcf2-p123">Ejecute el siguiente comando en Exchange Online PowerShell para identificar la conservación local que está colocada en el buzón. Use el GUID de la retención local que identificó en el paso 1.</span><span class="sxs-lookup"><span data-stu-id="cfcf2-p123">Run the following command in Exchange Online PowerShell to identify the In-Place Hold that's placed on the mailbox. Use the GUID for the In-Place Hold that you identified in Step 1.</span></span> 

```
Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL Name
```
   
<span data-ttu-id="cfcf2-p124">Después de identificar la conservación local, puede usar el centro de administración de Exchange (EAC) o Exchange Online PowerShell para quitar el buzón de la retención. Para obtener más información, vea [crear o quitar una conservación local](https://go.microsoft.com/fwlink/?linkid=852668).</span><span class="sxs-lookup"><span data-stu-id="cfcf2-p124">After you identify the In-Place Hold, you can use the Exchange admin center (EAC) or Exchange Online PowerShell to remove the mailbox from the hold. For more information, see [Create or remove an In-Place Hold](https://go.microsoft.com/fwlink/?linkid=852668).</span></span>
  
 ### <a name="office-365-retention-policies-applied-to-specific-mailboxes"></a><span data-ttu-id="cfcf2-203">Directivas de retención de Office 365 aplicadas a buzones específicos</span><span class="sxs-lookup"><span data-stu-id="cfcf2-203">Office 365 retention policies applied to specific mailboxes</span></span>
  
<span data-ttu-id="cfcf2-p125">Ejecute el siguiente comando en [office 365 Security &amp; Compliance Center PowerShell](https://go.microsoft.com/fwlink/?linkid=627084) para identificar la Directiva de retención de Office 365 que se aplica al buzón. Use el GUID (sin incluir el `mbx` prefijo o `skp` ) para la Directiva de retención que identificó en el paso 1.</span><span class="sxs-lookup"><span data-stu-id="cfcf2-p125">Run the following command in [Office 365 Security &amp; Compliance Center PowerShell](https://go.microsoft.com/fwlink/?linkid=627084) to identify the Office 365 retention policy that is applied to the mailbox. Use the GUID (not including the  `mbx` or  `skp` prefix) for the retention policy that you identified in Step 1.</span></span> 

```
Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name
```
   
<span data-ttu-id="cfcf2-206">Después de identificar la Directiva de retención, vaya a la página **retención** de **gobierno** \> de fecha &amp; en el centro de seguridad y cumplimiento, modifique la Directiva de retención que identificó en el paso anterior y quite el buzón de la lista de destinatarios que se incluyen en la Directiva de retención.</span><span class="sxs-lookup"><span data-stu-id="cfcf2-206">After you identify the retention policy, go to the **Date governance** \> **Retention** page in the Security &amp; Compliance Center, edit the retention policy that you identified in the previous step, and remove the mailbox from the list of recipients that are included in the retention policy.</span></span> 
  
 ### <a name="organization-wide-office-365-retention-policies"></a><span data-ttu-id="cfcf2-207">Directivas de retención de Office 365 de toda la organización</span><span class="sxs-lookup"><span data-stu-id="cfcf2-207">Organization-wide Office 365 retention policies</span></span>
  
<span data-ttu-id="cfcf2-p126">Las directivas de retención de Office 365 de toda la organización y de Exchange se aplican a todos los buzones de la organización. Se aplican en el nivel de la organización (no en el de buzón de correo) y se devuelven al ejecutar el cmdlet **Get-OrganizationConfig** en el paso 1. Ejecute el siguiente comando en [el &amp; centro de seguridad y cumplimiento de PowerShell](https://go.microsoft.com/fwlink/?linkid=627084) para identificar las directivas de retención de Office 365 de toda la organización. Use el GUID (sin incluir el `mbx` prefijo) para las directivas de retención de toda la organización que identificó en el paso 1.</span><span class="sxs-lookup"><span data-stu-id="cfcf2-p126">Organization-wide and Exchange-wide Office 365 retention policies are applied to every mailbox in the organization. They are applied at the organization level (not the mailbox level) and are returned when you run the **Get-OrganizationConfig** cmdlet in Step 1. Run the following command in [Security &amp; Compliance Center PowerShell](https://go.microsoft.com/fwlink/?linkid=627084) to identify the organization-wide Office 365 retention policies. Use the GUID (not including the  `mbx` prefix) for the organization-wide retention policies that you identified in Step 1.</span></span> 

```
Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name
```

<span data-ttu-id="cfcf2-p127">después de identificar las directivas de retención de Office 365 de toda la organización, vaya a la página de **retención** de &amp; **gobierno** \> de fecha en el centro de seguridad y cumplimiento, edite cada directiva de retención de toda la organización que identificó en el paso anterior y agregue el buzón a la lista de destinatarios excluidos. Al hacerlo, se quitará el buzón de correo del usuario de la Directiva de retención.</span><span class="sxs-lookup"><span data-stu-id="cfcf2-p127">After you identify the organization-wide Office 365 retention policies, go to the **Date governance** \> **Retention** page in the Security &amp; Compliance Center, edit each organization-wide retention policy that you identified in the previous step, and add the mailbox to the list of excluded recipients. Doing this will remove the user's mailbox from the retention policy.</span></span> 

### <a name="office-365-retention-labels"></a><span data-ttu-id="cfcf2-214">Etiquetas de retención de Office 365</span><span class="sxs-lookup"><span data-stu-id="cfcf2-214">Office 365 retention labels</span></span>

<span data-ttu-id="cfcf2-p128">Cuando un usuario aplica una etiqueta configurada para conservar contenido o conservar y, a continuación, eliminar el contenido en cualquier carpeta o elemento de su buzón de correo, la propiedad de buzón *ComplianceTagHoldApplied* se establece en **true**. Cuando esto ocurre, se considera que el buzón está en espera, como si se hubiera puesto en retención por juicio o asignado a una directiva de retención de Office 365.</span><span class="sxs-lookup"><span data-stu-id="cfcf2-p128">Whenever a user applies a label that's configured to retain content or retain and then delete content to any folder or item in their mailbox, the *ComplianceTagHoldApplied* mailbox property is set to **True**. When this happens, the mailbox is considered to be on hold, just as if it was placed on Litigation Hold or assigned to an Office 365 retention policy.</span></span>

<span data-ttu-id="cfcf2-217">Para ver el valor de la propiedad *ComplianceTagHoldApplied* , ejecute el siguiente comando en Exchange Online PowerShell:</span><span class="sxs-lookup"><span data-stu-id="cfcf2-217">To view the value of the *ComplianceTagHoldApplied* property, run the following command in Exchange Online PowerShell:</span></span>

```
Get-Mailbox <username> |FL ComplianceTagHoldApplied
```

<span data-ttu-id="cfcf2-p129">Una vez que haya identificado que un buzón está en suspensión debido a que se aplica una etiqueta de retención a una carpeta o a un elemento, puede usar la herramienta de búsqueda de contenido en el centro de seguridad & cumplimiento para buscar elementos etiquetados mediante la condición de búsqueda ComplianceTag. Para obtener más información, vea la sección "condiciones de búsqueda" en [consultas de palabras clave y condiciones de búsqueda para la búsqueda de contenido](keyword-queries-and-search-conditions.md#conditions-for-common-properties).</span><span class="sxs-lookup"><span data-stu-id="cfcf2-p129">After you've identified that a mailbox is on hold because a retention label is applied to a folder or item, you can use the Content Search tool in the Security & Compliance Center to search for labeled items by using the ComplianceTag search condition. For more information, see the "Search conditions" section in [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md#conditions-for-common-properties).</span></span>

<span data-ttu-id="cfcf2-220">Para obtener más información acerca de las etiquetas, vea [información general sobre las etiquetas de Office 365](labels.md).</span><span class="sxs-lookup"><span data-stu-id="cfcf2-220">For more information about labels, see [Overview of Office 365 labels](labels.md).</span></span>

 ### <a name="ediscovery-case-holds"></a><span data-ttu-id="cfcf2-221">suspensiones de casos de eDiscovery</span><span class="sxs-lookup"><span data-stu-id="cfcf2-221">eDiscovery case holds</span></span>
  
<span data-ttu-id="cfcf2-p130">Ejecute los siguientes comandos en [el &amp; centro de seguridad y cumplimiento de PowerShell](https://go.microsoft.com/fwlink/?linkid=627084) para identificar la retención asociada con un caso de exhibición de documentos electrónicos que se aplica al buzón. Use el GUID (sin incluir el `UniH` prefijo) para la suspensión de exhibición de documentos electrónicos que identificó en el paso 1. Tenga en cuenta que el segundo comando muestra el nombre del caso de eDiscovery con el que está asociada la retención; el tercer comando muestra el nombre de la suspensión.</span><span class="sxs-lookup"><span data-stu-id="cfcf2-p130">Run the following commands in [Security &amp; Compliance Center PowerShell](https://go.microsoft.com/fwlink/?linkid=627084) to identify the hold associated with an eDiscovery case that's applied to the mailbox. Use the GUID (not including the  `UniH` prefix) for the eDiscovery hold that you identified in Step 1. Note that the second command displays the name of the eDiscovery case the hold is associated with; the third command displays the name of the hold.</span></span> 
  
```
$CaseHold = Get-CaseHoldPolicy <hold GUID without prefix>
```

```
Get-ComplianceCase $CaseHold.CaseId | FL Name
```

```
$CaseHold.Name
```

<span data-ttu-id="cfcf2-p131">Después de identificar el nombre del caso de eDiscovery y la retención, vaya a la página de \> **exhibición** de documentos electrónicos de investigación &amp; de \*\*búsqueda &amp; \*\* en el centro de seguridad y cumplimiento, abra el caso y quite el buzón de la suspensión. Para obtener más información, vea [administrar casos de eDiscovery en el centro &amp; de seguridad y cumplimiento de Office 365](manage-ediscovery-cases.md).</span><span class="sxs-lookup"><span data-stu-id="cfcf2-p131">After you've identified the name of the eDiscovery case and the hold, go to the **Search &amp; investigation** \> **eDiscovery** page in the Security &amp; Compliance Center, open the case, and remove the mailbox from the hold. For more information, see [Manage eDiscovery cases in the Office 365 Security &amp; Compliance Center](manage-ediscovery-cases.md).</span></span>
  
## <a name="step-4-remove-the-delay-hold-from-the-mailbox"></a><span data-ttu-id="cfcf2-227">Paso 4: quitar la retención por retraso del buzón</span><span class="sxs-lookup"><span data-stu-id="cfcf2-227">Step 4: Remove the delay hold from the mailbox</span></span>

<span data-ttu-id="cfcf2-p132">Una vez que se quita cualquier tipo de retención de un buzón, el valor de la propiedad de buzón *DelayHoldApplied* se establece en **true**. Esto ocurre la próxima vez que el Asistente para carpeta administrada procesa el buzón de correo y detecta que se ha quitado una suspensión. Esto se denomina retenciones en *espera* y significa que la eliminación real de la retención se retrasa durante 30 días para impedir que los datos se eliminen de forma permanente del buzón. (El propósito de una retención retrasada es proporcionar a los administradores una oportunidad para buscar o recuperar los elementos del buzón que se purgarán después de que se quite una retención).  Cuando se coloca una retención en el buzón, el buzón sigue considerándose en espera durante un período de tiempo ilimitado, como si el buzón estuviera en retención por juicio. TransCurrido el plazo de 30 días, la retención en espera expira y Office 365 intentará quitar la retención retrasada automáticamente (estableciendo la propiedad *DelayHoldApplied* en **false**) para que la retención se elimine realmente.</span><span class="sxs-lookup"><span data-stu-id="cfcf2-p132">After any type of hold is removed from a mailbox, the value of the *DelayHoldApplied* mailbox property is set to **True**. This occurs the next time the Managed Folder Assistant processes the mailbox and detects that a hold has been removed. This is called a *delay hold* and means the actual removal of the hold is delayed for 30 days to prevent data from being permanently deleted from the mailbox. (The purpose of a delay hold is to give admins an opportunity to search for or recover mailbox items that will be purged after a hold is removed.)  When a delay hold is placed on the mailbox, the mailbox is still considered to be on hold for an unlimited duration, as if the mailbox was on Litigation Hold. After 30 days, the delay hold expires, and Office 365 will automatically attempt to remove the delay hold (by setting the *DelayHoldApplied* property to **False**) so that the hold is actually removed.</span></span> 

<span data-ttu-id="cfcf2-p133">Para poder eliminar elementos en el paso 5, debe quitar la retención por retraso del buzón. En primer lugar, determine si la retención de retraso se aplica al buzón ejecutando el siguiente comando en Exchange Online PowerShell:</span><span class="sxs-lookup"><span data-stu-id="cfcf2-p133">Before you can delete items in Step 5, you have to remove the delay hold from the mailbox. First, determine if the delay hold is applied to the mailbox by running the following command in Exchange Online PowerShell:</span></span>

```
Get-Mailbox <username> | FL DelayHoldApplied
```

<span data-ttu-id="cfcf2-p134">Si el valor de la propiedad *DelayHoldApplied* se establece en **false**, no se ha colocado una suspensión de retraso en el buzón. Puede ir al paso 5 y eliminar los elementos de la carpeta elementos recuperables.</span><span class="sxs-lookup"><span data-stu-id="cfcf2-p134">If the value of the *DelayHoldApplied* property is set to **False**, a delay hold has not been placed on the mailbox. You can go to Step 5 and delete items in the Recoverable Items folder.</span></span>

<span data-ttu-id="cfcf2-237">Si el valor de la propiedad *DelayHoldApplied* está establecido en **true**, ejecute el siguiente comando para quitar la retención por retraso:</span><span class="sxs-lookup"><span data-stu-id="cfcf2-237">If the value of the *DelayHoldApplied* property is set to **True**, run the following command to remove the delay hold:</span></span>

```
Set-Mailbox <username> -RemoveDelayHoldApplied
```
<span data-ttu-id="cfcf2-238">Tenga en cuenta que debe tener asignado el rol retención legal en Exchange Online para usar el parámetro *RemoveDelayHoldApplied* .</span><span class="sxs-lookup"><span data-stu-id="cfcf2-238">Note that you must be assigned the Legal Hold role in Exchange Online to use the *RemoveDelayHoldApplied* parameter.</span></span>

## <a name="step-5-delete-items-in-the-recoverable-items-folder"></a><span data-ttu-id="cfcf2-239">Paso 5: eliminar elementos de la carpeta elementos recuperables</span><span class="sxs-lookup"><span data-stu-id="cfcf2-239">Step 5: Delete items in the Recoverable Items folder</span></span>

<span data-ttu-id="cfcf2-p135">Ahora está listo para eliminar realmente los elementos de la carpeta elementos recuperables con el cmdlet [Search-Mailbox](https://go.microsoft.com/fwlink/?linkid=852595) en Exchange Online PowerShell. Tiene tres opciones al ejecutar el cmdlet **Search-Mailbox** .</span><span class="sxs-lookup"><span data-stu-id="cfcf2-p135">Now you're ready to actually delete items in the Recoverable Items folder by using the [Search-Mailbox](https://go.microsoft.com/fwlink/?linkid=852595) cmdlet in Exchange Online PowerShell. You have three options when running the **Search-Mailbox** cmdlet.</span></span> 
  
- <span data-ttu-id="cfcf2-242">Copie los elementos en un buzón de destino antes de eliminarlos para poder revisar los elementos, si es necesario, antes de eliminarlos.</span><span class="sxs-lookup"><span data-stu-id="cfcf2-242">Copy items to a target mailbox before you delete them so that you can review the items, if necessary, before you delete them.</span></span>
    
- <span data-ttu-id="cfcf2-243">Copiar elementos en un buzón de correo de destino y eliminarlos en el mismo comando.</span><span class="sxs-lookup"><span data-stu-id="cfcf2-243">Copy items to a target mailbox and delete them in the same command.</span></span>
    
- <span data-ttu-id="cfcf2-244">Eliminar elementos sin copiarlos en un buzón de correo de destino.</span><span class="sxs-lookup"><span data-stu-id="cfcf2-244">Delete items without copying them to a target mailbox.</span></span> 
    
<span data-ttu-id="cfcf2-p136">Tenga en cuenta que los elementos de la carpeta elementos recuperables del buzón de archivo principal del usuario también se eliminarán cuando ejecute el cmdlet **Search-Mailbox** . Para evitarlo, puede incluir el modificador *DoNotIncludeArchive* . Y como se mencionó anteriormente, si el archivado de expansión automática está habilitado para el buzón de correo, el cmdlet \* \* Search-Mailbox \* \* no elimina los elementos de un buzón de archivo auxiliar. Para obtener más información acerca del archivo de expansión automática, vea [información general sobre el archivado ilimitado en Office 365](unlimited-archiving.md).</span><span class="sxs-lookup"><span data-stu-id="cfcf2-p136">Note that items in the Recoverable Items folder in the user's primary archive mailbox will also be deleted when you run the **Search-Mailbox** cmdlet. To prevent this, you can include the  *DoNotIncludeArchive*  switch. And as previously stated, if auto-expanding archiving is enabled for the mailbox, the \*\* Search-Mailbox \*\* cmdlet doesn't deleted items in an auxiliary archive mailbox. For more information about auto-expanding archive, see [Overview of unlimited archiving in Office 365](unlimited-archiving.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="cfcf2-p137">Si incluye una consulta de búsqueda (utilizando el parámetro  *SearchQuery*  ), el cmdlet **Search-Mailbox** devolverá un máximo de 10 000 elementos en los resultados de búsqueda. Por tanto, si incluye una consulta de búsqueda, es posible que deba ejecutar el comando **Search-Mailbox** varias veces para eliminar más de 10 000 elementos.</span><span class="sxs-lookup"><span data-stu-id="cfcf2-p137">If you include a search query (by using the  *SearchQuery*  parameter), the **Search-Mailbox** cmdlet will return a maximum of 10,000 items in the search results. Therefore if you include a search query, you might have to run the **Search-Mailbox** command multiple times to delete more than 10,000 items.</span></span> 
  
<span data-ttu-id="cfcf2-p138">En los ejemplos siguientes se muestra la sintaxis de comandos para cada una de estas opciones. En estos ejemplos se `-SearchQuery size>0` usa el valor de parámetro, que elimina todos los elementos de todas las subcarpetas de la carpeta elementos recuperables. Si necesita eliminar solo elementos que coinciden con condiciones específicas, también puede usar el parámetro *SearchQuery* para especificar otras condiciones, como el asunto de un mensaje o un intervalo de fechas. Vea los [otros ejemplos de cómo usar el parámetro SearchQuery](#other-examples-of-using-the-searchquery-parameter) a continuación.</span><span class="sxs-lookup"><span data-stu-id="cfcf2-p138">The following examples show the command syntax for each of these options. These examples use the  `-SearchQuery size>0` parameter value, which deletes all items from all subfolders in the Recoverable Items folder. If you need to delete only items that match specific conditions, you can also use the  *SearchQuery*  parameter to specify other conditions, such as the subject of a message or a date range. See the [other examples of using the SearchQuery parameter](#other-examples-of-using-the-searchquery-parameter) below.</span></span> 
  
### <a name="example-1"></a><span data-ttu-id="cfcf2-255">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="cfcf2-255">Example 1</span></span>

<span data-ttu-id="cfcf2-p139">En este ejemplo se copian todos los elementos de la carpeta elementos recuperables del usuario en una carpeta del buzón de búsqueda de detección de la organización. Esto le permite revisar los elementos antes de eliminarlos de forma permanente.</span><span class="sxs-lookup"><span data-stu-id="cfcf2-p139">This example copies all items in the user's Recoverable Items folder to a folder in your organization's Discovery Search Mailbox. This lets you review the items before you permanently delete them.</span></span>

```
Search-Mailbox <username> -SearchQuery size>0 -SearchDumpsterOnly -TargetMailbox "Discovery Search Mailbox" -TargetFolder "<foldername>"
```

<span data-ttu-id="cfcf2-p140">En el ejemplo anterior, no es necesario copiar elementos en el buzón de búsqueda de detección. Puede copiar mensajes en cualquier buzón de correo de destino. Sin embargo, para impedir el acceso a datos de buzones potencialmente confidenciales, se recomienda copiar los mensajes a un buzón de correo que tenga acceso restringido al personal autorizado. De forma predeterminada, el acceso al buzón de búsqueda de detección predeterminado está restringido a los miembros del grupo de roles de administración de detección en Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="cfcf2-p140">In the previous example, it isn't required to copy items to the Discovery Search Mailbox. You can copy messages to any target mailbox. However, to prevent access to potentially sensitive mailbox data, we recommend copying messages to a mailbox that has access restricted to authorized personnel. By default, access to the default Discovery Search Mailbox is restricted to members of the Discovery Management role group in Exchange Online.</span></span> 
  
### <a name="example-2"></a><span data-ttu-id="cfcf2-262">Ejemplo 2</span><span class="sxs-lookup"><span data-stu-id="cfcf2-262">Example 2</span></span>

<span data-ttu-id="cfcf2-263">En este ejemplo se copian todos los elementos de la carpeta elementos recuperables del usuario en una carpeta del buzón de búsqueda de detección de la organización y, a continuación, se eliminan los elementos de la carpeta elementos recuperables del usuario.</span><span class="sxs-lookup"><span data-stu-id="cfcf2-263">This example copies all items in the user's Recoverable Items folder to a folder in your organization's Discovery Search Mailbox and then deletes the items from the user's Recoverable Items folder.</span></span>

```
Search-Mailbox <username> -SearchQuery size>0 -SearchDumpsterOnly -TargetMailbox "Discovery Search Mailbox" -TargetFolder "<foldername>" -DeleteContent
```
 
### <a name="example-3"></a><span data-ttu-id="cfcf2-264">Ejemplo 3</span><span class="sxs-lookup"><span data-stu-id="cfcf2-264">Example 3</span></span>

<span data-ttu-id="cfcf2-265">En este ejemplo se eliminan todos los elementos de la carpeta elementos recuperables del usuario, sin copiarlos en un buzón de destino.</span><span class="sxs-lookup"><span data-stu-id="cfcf2-265">This example deletes all items in the user's Recoverable Items folder, without copying them to a target mailbox.</span></span> 

```
Search-Mailbox <username> -SearchQuery size>0 -SearchDumpsterOnly -DeleteContent
```

### <a name="other-examples-of-using-the-searchquery-parameter"></a><span data-ttu-id="cfcf2-266">Otros ejemplos de cómo usar el parámetro SearchQuery</span><span class="sxs-lookup"><span data-stu-id="cfcf2-266">Other examples of using the SearchQuery parameter</span></span>

<span data-ttu-id="cfcf2-p141">A continuación se muestran algunos ejemplos de cómo usar el parámetro *SearchQuery* para buscar mensajes específicos. Si usa el parámetro *SearchQuery* para buscar elementos específicos, considere la posibilidad de copiar los resultados de la búsqueda en un buzón de correo de destino para poder revisar los resultados de la búsqueda y, a continuación, revisar la consulta si es necesario antes de eliminar los resultados de una búsqueda.</span><span class="sxs-lookup"><span data-stu-id="cfcf2-p141">Here are a few examples of using the  *SearchQuery*  parameter to find specific messages. If you use the  *SearchQuery*  parameter to search for specific items, consider copying the search results to a target mailbox so that you can review the search results and then revise the query if necessary before you delete the results of a search.</span></span> 
  
<span data-ttu-id="cfcf2-269">En este ejemplo se devuelven los mensajes que contienen una frase específica en el campo subJect.</span><span class="sxs-lookup"><span data-stu-id="cfcf2-269">This example returns messages that contain a specific phrase in the Subject field.</span></span>
  
```
SearchQuery 'subject:"MAIL_BOX VALIDATION/UPGRADE!!!"' 
```

<span data-ttu-id="cfcf2-270">En este ejemplo se devuelven los mensajes enviados en el intervalo de fechas especificado.</span><span class="sxs-lookup"><span data-stu-id="cfcf2-270">This example returns messages that were sent within the specified date range.</span></span>
  
```
SearchQuery 'sent>=06/01/2016 AND sent<=09/01/2016'
```
 
<span data-ttu-id="cfcf2-271">En este ejemplo se devuelven los mensajes que se enviaron a la persona especificada.</span><span class="sxs-lookup"><span data-stu-id="cfcf2-271">This example returns messages that were sent to the specified person.</span></span>

```
SearchQuery 'to:garthf@alpinehouse.com'
```
   
### <a name="verify-that-items-were-deleted"></a><span data-ttu-id="cfcf2-272">Comprobar que los elementos se han eliminado</span><span class="sxs-lookup"><span data-stu-id="cfcf2-272">Verify that items were deleted</span></span>

<span data-ttu-id="cfcf2-p142">Para comprobar si eliminó correctamente los elementos de la carpeta elementos recuperables de un buzón, use el cmdlet **Get-MailboxFolderStatistics** de PowerShell de Exchange Online para comprobar el tamaño y el número de elementos en la carpeta elementos recuperables. Puede comparar estas estadísticas con las que recopiló en el paso 1.</span><span class="sxs-lookup"><span data-stu-id="cfcf2-p142">To verify that you've successfully deleted items from the Recoverable Items folder of a mailbox, use **Get-MailboxFolderStatistics** cmdlet in Exchange Online PowerShell to check the size and number of items in Recoverable Items folder. You can compare these statistics with the ones you collected in Step 1.</span></span> 
  
<span data-ttu-id="cfcf2-275">Ejecute el siguiente comando en para obtener el tamaño actual y el número total de elementos de carpetas y subcarpetas en la carpeta elementos recuperables del buzón de correo principal del usuario.</span><span class="sxs-lookup"><span data-stu-id="cfcf2-275">Run the following command in to get the current size and total number of items in folders and subfolders in the Recoverable Items folder in the user's primary mailbox.</span></span> 
  
```
Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
```
   
<span data-ttu-id="cfcf2-276">Ejecute el siguiente comando para obtener el tamaño y el número total de elementos de carpetas y subcarpetas en la carpeta elementos recuperables del buzón de archivo del usuario.</span><span class="sxs-lookup"><span data-stu-id="cfcf2-276">Run the following command to get the size and total number of items in folders and subfolders in the Recoverable Items folder in the user's archive mailbox.</span></span> 

```
Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems -Archive | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
```
  
## <a name="step-6-revert-the-mailbox-to-its-previous-state"></a><span data-ttu-id="cfcf2-277">Paso 6: revertir el buzón a su estado anterior</span><span class="sxs-lookup"><span data-stu-id="cfcf2-277">Step 6: Revert the mailbox to its previous state</span></span>

<span data-ttu-id="cfcf2-p143">El último paso consiste en revertir el buzón a la configuración anterior. Esto significa restablecer las propiedades que cambió en el paso 2 y volver a aplicar las suspensiones que quitó en el paso 3. Esto incluye:</span><span class="sxs-lookup"><span data-stu-id="cfcf2-p143">The final step is to revert the mailbox back to its previous configuration. This means resetting the properties that you changed in Step 2 and re-applying the holds that you removed in Step 3. This includes:</span></span>
  
- <span data-ttu-id="cfcf2-p144">Cambiar el período de retención de elementos eliminados de nuevo a su valor anterior. Como alternativa, puede dejar este conjunto en 30 días, el valor máximo en Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="cfcf2-p144">Changing the deleted item retention period back to its previous value. Alternatively, you can just leave this set to 30 days, the maximum value in Exchange Online.</span></span>
    
- <span data-ttu-id="cfcf2-283">Volver a habilitar la recuperación de elementos individuales.</span><span class="sxs-lookup"><span data-stu-id="cfcf2-283">Re-enabling single Item recovery.</span></span>
    
- <span data-ttu-id="cfcf2-284">Volver a habilitar los métodos de acceso de cliente para que el propietario pueda obtener acceso a sus buzones.</span><span class="sxs-lookup"><span data-stu-id="cfcf2-284">Re-enabling the client access methods so that the owner can access their mailbox.</span></span>
    
- <span data-ttu-id="cfcf2-285">Volver a aplicar las suspensiones y las directivas de retención de Office 365 que quitó.</span><span class="sxs-lookup"><span data-stu-id="cfcf2-285">Re-applying the holds and Office 365 retention policies that you removed.</span></span>
    
- <span data-ttu-id="cfcf2-286">Volver a habilitar el Asistente para carpeta administrada para procesar el buzón de correo.</span><span class="sxs-lookup"><span data-stu-id="cfcf2-286">Re-enabling the Managed Folder Assistant to process the mailbox.</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="cfcf2-287">Le recomendamos que espere 24 horas después de volver a aplicar una retención o una directiva de retención de Office 365 (y comprobar que se ha implementado) antes de volver a habilitar el Asistente para la carpeta administrada para procesar el buzón.</span><span class="sxs-lookup"><span data-stu-id="cfcf2-287">We recommend that you wait 24 hours after re-applying a hold or Office 365 retention policy (and verifying that it's in place) before you re-enable the Managed Folder Assistant to process the mailbox.</span></span> 
  
<span data-ttu-id="cfcf2-288">Realice los siguientes pasos (en la secuencia especificada) en Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cfcf2-288">Perform the following steps (in the specified sequence) in Exchange Online PowerShell.</span></span>
  
1. <span data-ttu-id="cfcf2-p145">Ejecute el siguiente comando para volver a cambiar el período de retención de elementos eliminados a su valor original. Se supone que el valor anterior es inferior a 30 días; por ejemplo, 14 días.</span><span class="sxs-lookup"><span data-stu-id="cfcf2-p145">Run the following command to change the deleted item retention period back to its original value. This assumes that the previous setting is less than 30 days; for example 14 days.</span></span> 
    
    ```
    Set-Mailbox <username> -RetainDeletedItemsFor 14
    ```
   
2. <span data-ttu-id="cfcf2-291">Ejecute el siguiente comando para volver a habilitar la recuperación de un único elemento.</span><span class="sxs-lookup"><span data-stu-id="cfcf2-291">Run the following command to re-enable single item recovery.</span></span>
   
    ```
    Set-Mailbox <username> -SingleItemRecoveryEnabled $true
    ```

3. <span data-ttu-id="cfcf2-292">Ejecute el siguiente comando para volver a habilitar todos los métodos de acceso de cliente al buzón.</span><span class="sxs-lookup"><span data-stu-id="cfcf2-292">Run the following command to re-enable all client access methods to the mailbox.</span></span>
    
    ```
    Set-CASMailbox <username> -EwsEnabled $true -ActiveSyncEnabled $true -MAPIEnabled $true -OWAEnabled $true -ImapEnabled $true -PopEnabled $true
    ```
   
4. <span data-ttu-id="cfcf2-p146">Vuelva a aplicar las suspensiones que quitó en el paso 3. Según el tipo de retención, use uno de los procedimientos siguientes.</span><span class="sxs-lookup"><span data-stu-id="cfcf2-p146">Re-apply the holds that you removed in Step 3. Depending on the type of hold, use one of the following procedures.</span></span>
    
    <span data-ttu-id="cfcf2-295">**Retención por juicio**</span><span class="sxs-lookup"><span data-stu-id="cfcf2-295">**Litigation Hold**</span></span>
    
    <span data-ttu-id="cfcf2-296">Ejecute el siguiente comando para volver a habilitar una retención por juicio para el buzón.</span><span class="sxs-lookup"><span data-stu-id="cfcf2-296">Run the following command to re-enable a Litigation Hold for the mailbox.</span></span>
    
    ```
    Set-Mailbox <username> -LitigationHoldEnabled $true
    ```

    <span data-ttu-id="cfcf2-297">**In-Place Hold**</span><span class="sxs-lookup"><span data-stu-id="cfcf2-297">**In-Place Hold**</span></span>
    
    <span data-ttu-id="cfcf2-298">Use el EAC (o Exchange Online PowerShell) para volver a agregar el buzón a la conservación local.</span><span class="sxs-lookup"><span data-stu-id="cfcf2-298">Use the EAC (or Exchange Online PowerShell) to add the mailbox back to the In-Place Hold.</span></span> 
    
    <span data-ttu-id="cfcf2-299">**Directivas de retención de Office 365 aplicadas a buzones específicos**</span><span class="sxs-lookup"><span data-stu-id="cfcf2-299">**Office 365 retention policies applied to specific mailboxes**</span></span>
    
    <span data-ttu-id="cfcf2-p147">Use el centro &amp; de seguridad y cumplimiento para volver a agregar el buzón a la Directiva de retención de Office 365. Vaya a la página **retención** de **gobierno** \> de fecha en &amp; el centro de seguridad y cumplimiento, edite la Directiva de retención y vuelva a agregar el buzón a la lista de destinatarios a los que se aplica la Directiva de retención.</span><span class="sxs-lookup"><span data-stu-id="cfcf2-p147">Use the Security &amp; Compliance Center to add the mailbox back to the Office 365 retention policy. Go to the **Date governance** \> **Retention** page in the Security &amp; Compliance Center, edit the retention policy, and add the mailbox back to the list of recipients that the retention policy is applied to.</span></span> 
    
    <span data-ttu-id="cfcf2-302">**Directivas de retención de Office 365 de toda la organización**</span><span class="sxs-lookup"><span data-stu-id="cfcf2-302">**Organization-wide Office 365 retention policies**</span></span>
    
    <span data-ttu-id="cfcf2-p148">Si quitó una directiva de retención de toda la organización o de todo el mundo al excluirla de la Directiva, use &amp; el centro de seguridad y cumplimiento para quitar el buzón de la lista de usuarios excluidos. Vaya a la página **retención** de **gobierno** \> de fecha en &amp; el centro de seguridad y cumplimiento, edite la Directiva de retención de toda la organización y quite el buzón de la lista de destinatarios excluidos. Al hacerlo, se volverá a aplicar la Directiva de retención al buzón de correo del usuario.</span><span class="sxs-lookup"><span data-stu-id="cfcf2-p148">If you removed an organization-wide or Exchange-wide retention policy by excluding it from the policy, then use the Security &amp; Compliance Center to remove the mailbox from the list of excluded users. Go to the **Date governance** \> **Retention** page in the Security &amp; Compliance Center, edit the organization-wide retention policy, and remove the mailbox from the list of excluded recipients. Doing this will re-apply the retention policy to the user's mailbox.</span></span> 
    
    <span data-ttu-id="cfcf2-306">**suspensiones de casos de eDiscovery**</span><span class="sxs-lookup"><span data-stu-id="cfcf2-306">**eDiscovery case holds**</span></span>
    
    <span data-ttu-id="cfcf2-p149">Use el centro &amp; de seguridad y cumplimiento para agregar el buzón de correo de la retención asociada a un caso de exhibición de documentos electrónicos. Vaya a la página de **exhibición** de documentos electrónicos de &amp; \*\*investigación &amp; \*\* \> de búsqueda en el centro de seguridad y cumplimiento, abra el caso y agregue el buzón de correo a la suspensión.</span><span class="sxs-lookup"><span data-stu-id="cfcf2-p149">Use the Security &amp; Compliance Center to add the mailbox back the hold that's associated with an eDiscovery case. Go to the **Search &amp; investigation** \> **eDiscovery** page in the Security &amp; Compliance Center, open the case, and add the mailbox back to the hold.</span></span> 
    
5. <span data-ttu-id="cfcf2-p150">Ejecute el siguiente comando para permitir que el Asistente para carpeta administrada procese el buzón de nuevo. Como se mencionó anteriormente, se recomienda esperar 24 horas después de volver a aplicar una retención o una directiva de retención de Office 365 (y comprobar que está en su ubicación) antes de volver a habilitar el Asistente para carpeta administrada.</span><span class="sxs-lookup"><span data-stu-id="cfcf2-p150">Run the following command to allow the Managed Folder Assistant to process the mailbox again. As previously stated, we recommend that you wait 24 hours after re-applying a hold or Office 365 retention policy (and verifying that it's in place) before you re-enable the Managed Folder Assistant.</span></span> 

    ```
    Set-Mailbox <username> -ElcProcessingDisabled $false
    ```
   
6. <span data-ttu-id="cfcf2-311">Para comprobar que el buzón se ha revertido a su configuración anterior, puede ejecutar los siguientes comandos y, a continuación, comparar la configuración con las que recopiló en el paso 1.</span><span class="sxs-lookup"><span data-stu-id="cfcf2-311">To verify that the mailbox has been reverted back to its previous configuration, you can run the following commands and then compare the settings to the ones that you collected in Step 1.</span></span>

    ```
    Get-Mailbox <username> | FL ElcProcessingDisabled,InPlaceHolds,LitigationHoldEnabled,RetainDeletedItemsFor,SingleItemRecoveryEnabled
    ```

    ```
    Get-CASMailbox <username> | FL EwsEnabled,ActiveSyncEnabled,MAPIEnabled,OWAEnabled,ImapEnabled,PopEnabled
    ```
  
## <a name="more-information"></a><span data-ttu-id="cfcf2-312">Más información</span><span class="sxs-lookup"><span data-stu-id="cfcf2-312">More information</span></span>

<span data-ttu-id="cfcf2-p151">Esta es una tabla que describe cómo identificar distintos tipos de retenciones en función de los valores de la propiedad *InPlaceHolds* cuando se ejecutan los cmdlets **Get-Mailbox** o **Get-OrganizationConfig** . Para obtener información más detallada, consulte [How to identify The Type of Hold in an Exchange Online Mailbox](identify-a-hold-on-an-exchange-online-mailbox.md).</span><span class="sxs-lookup"><span data-stu-id="cfcf2-p151">Here's a table that describes how to identify different types of holds based on the values in the  *InPlaceHolds*  property when you run the **Get-Mailbox** or **Get-OrganizationConfig** cmdlets. For more detailed information, see [How to identify the type of hold placed on an Exchange Online mailbox](identify-a-hold-on-an-exchange-online-mailbox.md).</span></span>

<span data-ttu-id="cfcf2-315">Como se ha explicado anteriormente, tiene que quitar todas las suspensiones y las directivas de retención de Office 365 de un buzón de correo antes de poder eliminar correctamente los elementos de la carpeta elementos recuperables.</span><span class="sxs-lookup"><span data-stu-id="cfcf2-315">As previously explained, you have to remove all holds and Office 365 retention policies from a mailbox before you can successfully delete items in the Recoverable Items folder.</span></span> 
  
|<span data-ttu-id="cfcf2-316">**Tipo de retención**</span><span class="sxs-lookup"><span data-stu-id="cfcf2-316">**Hold type**</span></span>|<span data-ttu-id="cfcf2-317">**Valor de ejemplo**</span><span class="sxs-lookup"><span data-stu-id="cfcf2-317">**Example value**</span></span>|<span data-ttu-id="cfcf2-318">**Cómo identificar la retención**</span><span class="sxs-lookup"><span data-stu-id="cfcf2-318">**How to identify the hold**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="cfcf2-319">Retención por juicio</span><span class="sxs-lookup"><span data-stu-id="cfcf2-319">Litigation Hold</span></span>  <br/> | `True` <br/> |<span data-ttu-id="cfcf2-320">La propiedad *LitigationHoldEnabled* se establece en `True`.</span><span class="sxs-lookup"><span data-stu-id="cfcf2-320">The  *LitigationHoldEnabled*  property is set to  `True`.</span></span>  <br/> |
|<span data-ttu-id="cfcf2-321">Retención en contexto</span><span class="sxs-lookup"><span data-stu-id="cfcf2-321">In-Place Hold</span></span>  <br/> | `c0ba3ce811b6432a8751430937152491` <br/> |<span data-ttu-id="cfcf2-p152">La propiedad *InPlaceHolds* contiene el GUID de la retención local que está colocada en el buzón. Puede decir que se trata de una conservación local porque el GUID no comienza con un prefijo.</span><span class="sxs-lookup"><span data-stu-id="cfcf2-p152">The  *InPlaceHolds*  property contains the GUID of the In-Place Hold that's placed on the mailbox. You can tell this is an In-Place Hold because the GUID doesn't start with a prefix.  </span></span><br/> <span data-ttu-id="cfcf2-324">Puede usar el `Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL` comando en Exchange Online PowerShell para obtener información sobre la conservación local en el buzón.</span><span class="sxs-lookup"><span data-stu-id="cfcf2-324">You can use the  `Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL` command in Exchange Online PowerShell to get information about the In-Place Hold on the mailbox.</span></span>  <br/> |
| <span data-ttu-id="cfcf2-325">Directivas de retención de Office 365 en &amp; el centro de seguridad y cumplimiento aplicadas a buzones específicos</span><span class="sxs-lookup"><span data-stu-id="cfcf2-325">Office 365 retention policies in the Security &amp; Compliance Center applied to specific mailboxes</span></span>  <br/> | `mbxcdbbb86ce60342489bff371876e7f224` <br/> <span data-ttu-id="cfcf2-326">o</span><span class="sxs-lookup"><span data-stu-id="cfcf2-326">or</span></span>  <br/>  `skp127d7cf1076947929bf136b7a2a8c36f` <br/> |<span data-ttu-id="cfcf2-p153">Cuando se ejecuta el cmdlet **Get-Mailbox** , la propiedad *InPlaceHolds* también contiene los GUID de las directivas de retención de Office 365 que se aplican al buzón. Puede identificar las directivas de retención porque el GUID comienza por `mbx` el prefijo. Tenga en cuenta que si el GUID de la Directiva de retención `skp` comienza con el prefijo, indica que la Directiva de retención se aplica a las conversaciones de Skype empresarial.</span><span class="sxs-lookup"><span data-stu-id="cfcf2-p153">When you run the **Get-Mailbox** cmdlet, the  *InPlaceHolds*  property also contains GUIDs of Office 365 retention policies applied to the mailbox. You can identify retention policies because the GUID starts with the  `mbx` prefix. Note that if the GUID of the retention policy starts with the  `skp` prefix, that indicates that the retention policy is applied to Skype for Business conversations.  </span></span><br/> <span data-ttu-id="cfcf2-330">Para identificar la Directiva de retención de Office 365 que se aplica al buzón de correo, ejecute el siguiente &amp; comando en Security Compliance Center PowerShell:</span><span class="sxs-lookup"><span data-stu-id="cfcf2-330">To identity the Office 365 retention policy that's applied to the mailbox, run the following command in Security &amp; Compliance Center PowerShell:</span></span> <br/> <br/>`Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name`<br/><br/><span data-ttu-id="cfcf2-331">Asegúrese de quitar el `mbx` prefijo `skp` o cuando ejecute este comando.</span><span class="sxs-lookup"><span data-stu-id="cfcf2-331">Be sure to remove the  `mbx` or  `skp` prefix when you run this command.</span></span>  <br/> |
|<span data-ttu-id="cfcf2-332">Directivas de retención de Office 365 de toda la organización &amp; en el centro de seguridad y cumplimiento</span><span class="sxs-lookup"><span data-stu-id="cfcf2-332">Organization-wide Office 365 retention policies in the Security &amp; Compliance Center</span></span>  <br/> |<span data-ttu-id="cfcf2-333">Ningún valor</span><span class="sxs-lookup"><span data-stu-id="cfcf2-333">No value</span></span>  <br/> <span data-ttu-id="cfcf2-334">o</span><span class="sxs-lookup"><span data-stu-id="cfcf2-334">or</span></span>  <br/>  <span data-ttu-id="cfcf2-335">`-mbxe9b52bf7ab3b46a286308ecb29624696`(indica que el buzón está excluido de una directiva de toda la organización)</span><span class="sxs-lookup"><span data-stu-id="cfcf2-335">`-mbxe9b52bf7ab3b46a286308ecb29624696` (indicates that the mailbox is excluded from an organization-wide policy)</span></span>  <br/> |<span data-ttu-id="cfcf2-336">Incluso si la propiedad *InPlaceHolds* está vacía cuando ejecuta el cmdlet **Get-Mailbox** , es posible que se hayan aplicado al buzón una o varias directivas de retención de Office 365 de toda la organización.</span><span class="sxs-lookup"><span data-stu-id="cfcf2-336">Even if the  *InPlaceHolds*  property is empty when you run the **Get-Mailbox** cmdlet, there still might be one or more organization-wide Office 365 retention policies applied to the mailbox.</span></span>  <br/> <span data-ttu-id="cfcf2-p154">Para comprobarlo, puede ejecutar el `Get-OrganizationConfig | FL InPlaceHolds` comando en Exchange Online PowerShell para obtener una lista de los GUID de las directivas de retención de Office 365 de toda la organización. El GUID de las directivas de retención de toda la organización que se aplican a `mbx` los buzoNes de Exchange comienza con el prefijo; por ejemplo `mbxa3056bb15562480fadb46ce523ff7b02`.</span><span class="sxs-lookup"><span data-stu-id="cfcf2-p154">To verify this, you can run the  `Get-OrganizationConfig | FL InPlaceHolds` command in Exchange Online PowerShell to get a list of the GUIDs for organization-wide Office 365 retention policies. The GUID for organization-wide retention policies applied to Exchange mailboxes start with the  `mbx` prefix; for example  `mbxa3056bb15562480fadb46ce523ff7b02`.  </span></span><br/> <span data-ttu-id="cfcf2-339">Para identificar la Directiva de retención de Office 365 de toda la organización que se aplica al buzón de correo, ejecute el &amp; siguiente comando en Security Compliance Center PowerShell:</span><span class="sxs-lookup"><span data-stu-id="cfcf2-339">To identity the organization-wide Office 365 retention policy that's applied to the mailbox, run the following command in Security &amp; Compliance Center PowerShell:</span></span> <br/><br/> `Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name`<br/><br/><span data-ttu-id="cfcf2-340">Tenga en cuenta que si un buzón se excluye de una directiva de retención de Office 365 de toda la organización, el GUID de la Directiva de retención se muestra en la propiedad *InPlaceHolds* del buzón del usuario cuando se ejecuta el cmdlet **Get-Mailbox** ; se identifica por el prefijo `-mbx`; por ejemplo,`-mbxe9b52bf7ab3b46a286308ecb29624696`</span><span class="sxs-lookup"><span data-stu-id="cfcf2-340">Note that if a mailbox is excluded from an organization-wide Office 365 retention policy, the GUID for the retention policy is displayed in the  *InPlaceHolds*  property of the user's mailbox when you run the **Get-Mailbox** cmdlet; it's identified by the prefix  `-mbx`; for example,  `-mbxe9b52bf7ab3b46a286308ecb29624696`</span></span> <br/> |
|<span data-ttu-id="cfcf2-341">suspensión de casos de eDiscovery en &amp; el centro de seguridad y cumplimiento</span><span class="sxs-lookup"><span data-stu-id="cfcf2-341">eDiscovery case hold in the Security &amp; Compliance Center</span></span>  <br/> | `UniH7d895d48-7e23-4a8d-8346-533c3beac15d` <br/> |<span data-ttu-id="cfcf2-p155">La propiedad *InPlaceHolds* también contiene el GUID de cualquier suspensión asociado con un caso de exhibición de documentos &amp; electrónicos en el centro de seguridad y cumplimiento que se puede colocar en el buzón. Puede decir que se trata de una suspensión de casos de exhibición de documentos electrónicos `UniH` porque el GUID comienza por el prefijo.</span><span class="sxs-lookup"><span data-stu-id="cfcf2-p155">The  *InPlaceHolds*  property also contains the GUID of any hold associated with an eDiscovery case in the Security &amp; Compliance Center that might be placed on the mailbox. You can tell this is an eDiscovery case hold because the GUID starts with the  `UniH` prefix.  </span></span><br/> <span data-ttu-id="cfcf2-p156">Puede usar el `Get-CaseHoldPolicy` cmdlet en el centro &amp; de seguridad y cumplimiento de PowerShell para obtener información sobre el caso de eDiscovery con el que está asociado la retención en el buzón de correo. Por ejemplo, puede ejecutar el comando `Get-CaseHoldPolicy <hold GUID without prefix> | FL Name` para mostrar el nombre de la suspensión de mayúsculas y minúsculas que se encuentra en el buzón. Asegúrese de quitar el `UniH` prefijo al ejecutar este comando.</span><span class="sxs-lookup"><span data-stu-id="cfcf2-p156">You can use the  `Get-CaseHoldPolicy` cmdlet in Security &amp; Compliance Center PowerShell to get information about the eDiscovery case that the hold on the mailbox is associated with. For example, you can run the command  `Get-CaseHoldPolicy <hold GUID without prefix> | FL Name` to display the name of the case hold that's on the mailbox. Be sure to remove the  `UniH` prefix when you run this command.  </span></span><br/><br/> <span data-ttu-id="cfcf2-347">Para identificar el caso de exhibición de documentos electrónicos con el que está asociada la retención en el buzón de correo, ejecute los siguientes comandos:</span><span class="sxs-lookup"><span data-stu-id="cfcf2-347">To identity the eDiscovery case that the hold on the mailbox is associated with, run the following commands:</span></span><br/><br/>`$CaseHold = Get-CaseHoldPolicy <hold GUID without prefix>`<br/><br/>`Get-ComplianceCase $CaseHold.CaseId | FL Name`


