---
title: Información general sobre el archivado ilimitado en Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 37cdbb02-a24a-4093-8bdb-2a7f0b3a19ee
description: Obtenga información sobre el archivado de expansión automática en Office 365, que proporciona almacenamiento ilimitado de archivos para buzones de Exchange Online.
ms.openlocfilehash: 4ed1260cdf348d0bd29d88952ab69d234f044c26
ms.sourcegitcommit: baf23be44f1ed5abbf84f140b5ffa64fce605478
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/26/2019
ms.locfileid: "30296653"
---
# <a name="overview-of-unlimited-archiving-in-office-365"></a><span data-ttu-id="34912-103">Información general sobre el archivado ilimitado en Office 365</span><span class="sxs-lookup"><span data-stu-id="34912-103">Overview of unlimited archiving in Office 365</span></span>

<span data-ttu-id="34912-p101">En Office 365, los buzones de archivo proporcionan a los usuarios espacio de almacenamiento adicional en el buzón de correo. Después de habilitar el buzón de archivo de un usuario, hay disponible hasta 100 GB de almacenamiento adicional. Cuando se alcanza la cuota de almacenamiento de 100 GB, las organizaciones tuvieron que ponerse en contacto con Microsoft para solicitar espacio de almacenamiento adicional para un buzón de archivo. Esto ya no es así. La nueva característica de archivado ilimitado en Office 365 (denominada *archivado de expansión automática*) proporciona una cantidad ilimitada de almacenamiento en los buzones de archivo. Ahora, cuando se alcanza la cuota de almacenamiento en el buzón de archivo, Office 365 aumenta automáticamente el tamaño del archivo, lo que significa que los usuarios no se quedarán sin espacio de almacenamiento en el buzón y los administradores no tendrán que solicitar almacenamiento adicional para los buzones de archivo. .</span><span class="sxs-lookup"><span data-stu-id="34912-p101">In Office 365, archive mailboxes provide users with additional mailbox storage space. After a user's archive mailbox is enabled, up to 100 GB of additional storage is available. When the 100 GB storage quota is reached, organizations had to contact Microsoft to request additional storage space for an archive mailbox. That's no longer the case. The new unlimited archiving feature in Office 365 (called *auto-expanding archiving*) provides an unlimited amount of storage in archive mailboxes. Now, when the storage quota in the archive mailbox is reached, Office 365 automatically increases the size of the archive, which means that users won't run out of mailbox storage space and administrators won't have to request additional storage for archive mailboxes.</span></span>
  
<span data-ttu-id="34912-110">Para obtener instrucciones paso a paso para activar el archivado de expansión automática, vea [Habilitar el archivado ilimitado en Office 365](enable-unlimited-archiving.md).</span><span class="sxs-lookup"><span data-stu-id="34912-110">For step-by-step instructions for turning on auto-expanding archiving, see [Enable unlimited archiving in Office 365](enable-unlimited-archiving.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="34912-p102">El archivado de expansión automática también admite buzones compartidos. Para habilitar el archivo para un buzón compartido, se necesita una licencia de Exchange Online (plan 2) o una licencia de Exchange Online (plan 1) con una licencia de archivado de Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="34912-p102">Auto-expanding archiving also supports shared mailboxes. To enable the archive for a shared mailbox, an Exchange Online Plan 2 license or an Exchange Online Plan 1 license with an Exchange Online Archiving license is required.</span></span> 
  
## <a name="how-auto-expanding-archiving-works"></a><span data-ttu-id="34912-113">Funcionamiento del archivado de expansión automática</span><span class="sxs-lookup"><span data-stu-id="34912-113">How auto-expanding archiving works</span></span>

<span data-ttu-id="34912-p103">Como se ha explicado anteriormente, el espacio de almacenamiento de buzones de correo adicional se crea cuando se habilita el buzón de archivo de un usuario. Cuando el archivado de expansión automática está habilitado, Office 365 comprueba periódicamente el tamaño del buzón de archivo. Cuando un buzón de archivo se acerca al límite de almacenamiento, Office 365 crea automáticamente espacio de almacenamiento adicional para el archivo. Si el usuario se queda sin este espacio de almacenamiento adicional, Office 365 agrega más espacio de almacenamiento al archivo del usuario. Este proceso se produce de forma automática, lo que significa que los administradores no tienen que solicitar el almacenamiento de archivos adicional o administrar el archivado de expansión automática.</span><span class="sxs-lookup"><span data-stu-id="34912-p103">As previously explained, additional mailbox storage space is created when a user's archive mailbox is enabled. When auto-expanding archiving is enabled, Office 365 periodically checks the size of the archive mailbox. When an archive mailbox gets close to its storage limit, Office 365 automatically creates additional storage space for the archive. If the user runs out of this additional storage space, Office 365 adds more storage space to the user's archive. This process happens automatically, which means administrators don't have to request additional archive storage or manage auto-expanding archiving.</span></span> 
  
<span data-ttu-id="34912-119">A continuación se muestra una introducción rápida del proceso.</span><span class="sxs-lookup"><span data-stu-id="34912-119">Here's a quick overview of the process.</span></span>
  
![Información general sobre el proceso de archivado de expansión automática](media/74355385-d990-44fe-8a87-6c3639d1f63f.png)
  
1. <span data-ttu-id="34912-p104">El archivado está habilitado para un buzón de usuario o un buzón compartido. Se crea un buzón de archivo con 100 GB de espacio de almacenamiento y la cuota de advertencia para el buzón de archivo se establece en 90 GB.</span><span class="sxs-lookup"><span data-stu-id="34912-p104">Archiving is enabled for a user mailbox or a shared mailbox. An archive mailbox with 100 GB of storage space is created, and the warning quota for the archive mailbox is set to 90 GB.</span></span>
    
2. <span data-ttu-id="34912-p105">Un administrador habilita el archivado de expansión automática para el buzón de correo. A continuación, cuando el buzón de archivo (incluida la carpeta elementos recuperables) alcanza los 90 GB, se convierte en un archivo de expansión automática y Office 365 agrega espacio de almacenamiento al archivo. Tenga en cuenta que puede tardar hasta 30 días en aprovisionarse el espacio de almacenamiento adicional.</span><span class="sxs-lookup"><span data-stu-id="34912-p105">An administrator enables auto-expanding archiving for the mailbox. Then, when the archive mailbox (including the Recoverable Items folder) reaches 90 GB, it's converted to an auto-expanding archive, and Office 365 adds storage space to the archive. Note that it can take up to 30 days for the additional storage space to be provisioned.</span></span>
    
3. <span data-ttu-id="34912-126">Office 365 agrega automáticamente más espacio de almacenamiento al archivo cuando es necesario.</span><span class="sxs-lookup"><span data-stu-id="34912-126">Office 365 automatically adds more storage space to the archive when necessary.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="34912-p106">Si un buzón se coloca en retención o se asigna a una directiva de retención de Office 365, la cuota de almacenamiento de la Maibox de archivo se aumenta a 110 GB cuando está habilitado el archivado de expansión automática. De forma similar, la cuota de advertencia de archivo aumenta a 100 GB.</span><span class="sxs-lookup"><span data-stu-id="34912-p106">If a mailbox is placed on hold or assigned to an Office 365 retention policy, the storage quota for the archive maibox is increased to 110 GB when auto-expanding archiving is enabled. Similarly, the archive warning quota is increased to 100 GB.</span></span>

## <a name="what-gets-moved-to-the-additional-archive-storage-space"></a><span data-ttu-id="34912-129">¿Qué se mueve al espacio de almacenamiento adicional del archivo?</span><span class="sxs-lookup"><span data-stu-id="34912-129">What gets moved to the additional archive storage space?</span></span>

<span data-ttu-id="34912-p107">Para hacer un uso eficaz del almacenamiento de archivos de expansión automática, las carpetas pueden moverse. Office 365 determina qué carpetas se mueven cuando se agrega almacenamiento adicional al archivo. Cuando se mueve una carpeta, se crea automáticamente una subcarpeta en la carpeta original en la parte de archivo de la lista de carpetas de Outlook. Esta nueva subcarpeta apunta a los elementos que se movieron. la convención de nomenclatura que Office 365 usa para asignar un nombre a esta carpeta es \*\* \<el nombre\>de carpeta _yyyy (creado en mmm dd, yyyy h_mm)\*\*, donde:</span><span class="sxs-lookup"><span data-stu-id="34912-p107">To make efficient use of auto-expanding archive storage, folders might get moved. Office 365 determines which folders get moved when additional storage is added to the archive. When a folder is moved, a subfolder is automatically created under the original folder in the archive portion of the folder list in Outlook. This new subfolder points to the items that were moved. The naming convention that Office 365 uses to name this folder is **\<folder name\>_yyyy (Created on mmm dd, yyyy h_mm)**, where:</span></span> 
  
- <span data-ttu-id="34912-135">**yyyy** es el año en que se recibieron los mensajes de la carpeta.</span><span class="sxs-lookup"><span data-stu-id="34912-135">**yyyy** is the year the messages in the folder were received.</span></span> 
    
- <span data-ttu-id="34912-136">**dd mmm h_m** es la fecha y hora en que se creó la subcarpeta mediante Office 365, en formato UTC, en función de la zona horaria del usuario y la configuración regional en Outlook.</span><span class="sxs-lookup"><span data-stu-id="34912-136">**mmm dd, yyyy h_m** is the date and time that the subfolder was created by Office 365, in UTC format, based on the user's time zone and regional settings in Outlook.</span></span> 
    
<span data-ttu-id="34912-137">En las siguientes capturas de pantalla se muestra una lista de carpetas antes y después de que los mensajes se muevan a un archivo de expansión automática.</span><span class="sxs-lookup"><span data-stu-id="34912-137">The following screen shots show a folder list before and after messages are moved in an auto-expanded archive.</span></span>
  
 <span data-ttu-id="34912-138">**Antes de agregar almacenamiento adicional**</span><span class="sxs-lookup"><span data-stu-id="34912-138">**Before additional storage is added**</span></span>
  
![Lista de carpetas de buzón de archivo antes de aprovisionar el archivo de expansión automática](media/5d6d6420-e562-4912-aaab-1c111762b3f6.png)
  
 <span data-ttu-id="34912-140">**Una vez agregado el almacenamiento adicional**</span><span class="sxs-lookup"><span data-stu-id="34912-140">**After additional storage is added**</span></span>
  
![Lista de carpetas del buzón de archivo después de aprovisionar el archivo de expansión automática](media/c03c5f51-23fa-4fc2-b887-7e7e5cce30da.png)
  
## <a name="outlook-requirements-for-accessing-items-in-an-auto-expanded-archive"></a><span data-ttu-id="34912-142">Requisitos de Outlook para obtener acceso a elementos en un archivo de expansión automática</span><span class="sxs-lookup"><span data-stu-id="34912-142">Outlook requirements for accessing items in an auto-expanded archive</span></span>

<span data-ttu-id="34912-143">Para obtener acceso a los mensajes que se almacenan en un archivo de expansión automática, los usuarios tienen que usar uno de los siguientes clientes de Outlook:</span><span class="sxs-lookup"><span data-stu-id="34912-143">To access messages that are stored in an auto-expanded archive, users have to use one of the following Outlook clients:</span></span>
  
- <span data-ttu-id="34912-144">Outlook 2016 o Outlook 2019 para Windows</span><span class="sxs-lookup"><span data-stu-id="34912-144">Outlook 2016 or Outlook 2019 for Windows</span></span>
    
- <span data-ttu-id="34912-145">Outlook en la Web</span><span class="sxs-lookup"><span data-stu-id="34912-145">Outlook on the web</span></span> 
    
- <span data-ttu-id="34912-146">Outlook 2016 o Outlook 2019 para Mac</span><span class="sxs-lookup"><span data-stu-id="34912-146">Outlook 2016 or Outlook 2019 for Mac</span></span> 
    
> [!NOTE]
> <span data-ttu-id="34912-p108">Los usuarios de Outlook 2013 solo pueden tener acceso a elementos que se almacenaron originalmente en su buzón de archivo. No podrán tener acceso a los elementos que se mueven a almacenamiento de archivos adicionales.</span><span class="sxs-lookup"><span data-stu-id="34912-p108">Outlook 2013 users can only access items that were originally stored in their archive mailbox. They won't be able to access items that are moved to additional archive storage.</span></span> 
  
<span data-ttu-id="34912-149">Estos son algunos aspectos que se deben tener en cuenta al usar Outlook o Outlook en la web para tener acceso a los mensajes almacenados en un archivo de expansión automática.</span><span class="sxs-lookup"><span data-stu-id="34912-149">Here are some things to consider when using Outlook or Outlook on the web to access messages stored in an auto-expanded archive.</span></span>
  
- <span data-ttu-id="34912-150">Puede tener acceso a cualquier carpeta del buzón de archivo, incluidas las que se han movido al área de almacenamiento expandido automáticamente.</span><span class="sxs-lookup"><span data-stu-id="34912-150">You can access any folder in your archive mailbox, including ones that were moved to the auto-expanded storage area.</span></span>
    
- <span data-ttu-id="34912-p109">Puede buscar elementos que se movieron a un área de almacenamiento adicional solo si busca en la propia carpeta. Esto significa que debe seleccionar la carpeta de archivo en la lista de carpetas para seleccionar la opción **carpeta actual** como ámbito de búsqueda. De forma similar, si una carpeta de un área de almacenamiento con expansión automática contiene subcarpetas, deberá buscar cada subcarpeta por separado.</span><span class="sxs-lookup"><span data-stu-id="34912-p109">You can search for items that were moved to an additional storage area only by searching the folder itself. This means you have to select the archive folder in the folder list to select the **Current Folder** option as the search scope. Similarly, if a folder in an auto-expanded storage area contains subfolders, you have to search each subfolder separately.</span></span> 
    
- <span data-ttu-id="34912-154">Los recuentos de elementos en Outlook y los recuentos de leídos o no leídos (en Outlook y Outlook en la web) en un archivo de expansión automática podrían no ser precisos.</span><span class="sxs-lookup"><span data-stu-id="34912-154">Item counts in Outlook and Read/Unread counts (in Outlook and Outlook on the web ) in an auto-expanded archive might not be accurate.</span></span>
    
- <span data-ttu-id="34912-155">Puede eliminar los elementos de una subcarpeta que señale a un área de almacenamiento expandida automáticamente, pero no se puede eliminar la carpeta en sí.</span><span class="sxs-lookup"><span data-stu-id="34912-155">You can delete items in a subfolder that points to an auto-expanded storage area, but the folder itself can't be deleted.</span></span>
    
- <span data-ttu-id="34912-156">No puede usar la característica recuperar elementos eliminados para recuperar un elemento que se eliminó de un área de almacenamiento expandida automáticamente.</span><span class="sxs-lookup"><span data-stu-id="34912-156">You can't use the Recover Deleted Items feature to recover an item that was deleted from an auto-expanded storage area.</span></span>
  
## <a name="auto-expanding-archiving-and-other-office-365-compliance-features"></a><span data-ttu-id="34912-157">Archivado de expansión automática y otras características de cumplimiento de Office 365</span><span class="sxs-lookup"><span data-stu-id="34912-157">Auto-expanding archiving and other Office 365 compliance features</span></span>

<span data-ttu-id="34912-158">En esta sección se explica la funcionalidad entre el archivado de expansión automática y otras características del gobierno de datos y cumplimiento de Office 365.</span><span class="sxs-lookup"><span data-stu-id="34912-158">This section explains the functionality between auto-expanding archiving and other Office 365 compliance and data governance features.</span></span>
  
- <span data-ttu-id="34912-159">**eDiscovery** : cuando usa una herramienta de exhibición de documentos electrónicos de Office 365, como búsqueda de contenido o exhibición de documentos electrónicos local, también se busca en las áreas de almacenamiento adicionales de un archivo de expansión automática.</span><span class="sxs-lookup"><span data-stu-id="34912-159">**eDiscovery** - When you use an Office 365 eDiscovery tool, such as Content Search or In-Place eDiscovery, the additional storage areas in an auto-expanded archive are also searched.</span></span>
    
- <span data-ttu-id="34912-160">**Retención** : cuando coloca un buzón de correo en retención mediante el uso de herramientas como retención por juicio en Exchange online o eDiscovery Case retenciones y directivas de retención en el centro de seguridad & cumplimiento de Office 365, el contenido ubicado en un archivo de expansión automática también es colocado en suspensión.</span><span class="sxs-lookup"><span data-stu-id="34912-160">**Retention** - When you put a mailbox on hold by using tools such as Litigation Hold in Exchange Online or eDiscovery case holds and retention policies in the Office 365 Security & Compliance Center, content located in an auto-expanded archive is also placed on hold.</span></span>
    
- <span data-ttu-id="34912-161">**Administración de registros de mensajes (MRM)** : Si usa directivas de eliminación de MRM en Exchange Online para eliminar permanentemente los elementos de buzón expirados, los elementos expirados que se encuentran en el archivo de expansión automática también se eliminarán.</span><span class="sxs-lookup"><span data-stu-id="34912-161">**Messaging records management (MRM)** - If you use MRM deletion policies in Exchange Online to permanently delete expired mailbox items, expired items located in the auto-expanded archive will also be deleted.</span></span>
    
- <span data-ttu-id="34912-p110">**Servicio de importación** : puede usar el servicio de importación de Office 365 para importar archivos PST al archivo de expansión automática de un usuario. Puede importar hasta 100 GB de datos de archivos PST en el buzón de archivo del usuario.</span><span class="sxs-lookup"><span data-stu-id="34912-p110">**Import service** - You can use the Office 365 Import service to import PST files to a user's auto-expanded archive. You can import up to 100 GB of data from PST files to the user's archive mailbox.</span></span> 

## <a name="more-information"></a><span data-ttu-id="34912-164">Más información</span><span class="sxs-lookup"><span data-stu-id="34912-164">More information</span></span>

<span data-ttu-id="34912-165">Para obtener más información técnica sobre el archivado de expansión automática, consulte [Office 365: archivos de expansión automática de archivos de preguntas más frecuentes](https://blogs.technet.microsoft.com/exchange/2018/04/09/office-365-auto-expanding-archives-faq/).</span><span class="sxs-lookup"><span data-stu-id="34912-165">For more technical details about auto-expanding archiving, see [Office 365: Auto-Expanding Archives FAQ](https://blogs.technet.microsoft.com/exchange/2018/04/09/office-365-auto-expanding-archives-faq/).</span></span>