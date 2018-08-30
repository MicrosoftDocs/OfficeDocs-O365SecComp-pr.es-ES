---
title: Información general sobre el archivo ilimitado en Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/29/2018
ms.audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 37cdbb02-a24a-4093-8bdb-2a7f0b3a19ee
description: Obtenga información acerca de la expansión automática de archivado en Office 365, que proporciona almacenamiento de archivo ilimitado para buzones de Exchange Online.
ms.openlocfilehash: 4fc490871c1a0142ab0f68126cce6f2a51e0f7d0
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22535894"
---
# <a name="overview-of-unlimited-archiving-in-office-365"></a><span data-ttu-id="ec9a2-103">Información general sobre el archivo ilimitado en Office 365</span><span class="sxs-lookup"><span data-stu-id="ec9a2-103">Overview of unlimited archiving in Office 365</span></span>

<span data-ttu-id="ec9a2-p101">En Office 365, buzones de archivo proporcionan a los usuarios con el espacio de almacenamiento de buzones de correo adicionales. Después de habilita el buzón de archivo de un usuario, hasta 100 GB de almacenamiento de información adicional está disponible. Cuando se alcanza la cuota de almacenamiento de 100 GB, las organizaciones tenían ponerse en contacto con Microsoft para el espacio de almacenamiento adicional de la solicitud para un buzón de archivo. Ya no es el caso. La nueva característica de archivado ilimitada en Office 365 (llamado ampliación automática archivado) proporciona una cantidad ilimitada de almacenamiento en buzones de archivo. Ahora, cuando se alcanza la cuota de almacenamiento en el buzón de archivo, Office 365 automáticamente aumenta el tamaño de archivo, lo que significa que los usuarios no se ejecutan fuera del espacio de almacenamiento de buzones de correo y los administradores no deben solicitar almacenamiento adicional para buzones de archivo .</span><span class="sxs-lookup"><span data-stu-id="ec9a2-p101">In Office 365, archive mailboxes provide users with additional mailbox storage space. After a user's archive mailbox is enabled, up to 100 GB of additional storage is available. When the 100 GB storage quota is reached, organizations had to contact Microsoft to request additional storage space for an archive mailbox. That's no longer the case. The new unlimited archiving feature in Office 365 (called auto-expanding archiving) provides an unlimited amount of storage in archive mailboxes. Now, when the storage quota in the archive mailbox is reached, Office 365 automatically increases the size of the archive, which means that users won't run out of mailbox storage space and administrators won't have to request additional storage for archive mailboxes.</span></span>
  
<span data-ttu-id="ec9a2-110">Para obtener instrucciones paso a paso para activar la ampliación automática de archivado, vea [Habilitar el archivado ilimitado en Office 365](enable-unlimited-archiving.md).</span><span class="sxs-lookup"><span data-stu-id="ec9a2-110">For step-by-step instructions for turning on auto-expanding archiving, see [Enable unlimited archiving in Office 365](enable-unlimited-archiving.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="ec9a2-p102">Ampliación automática de archivado también es compatible con los buzones compartidos. Para habilitar el archivo para un buzón compartido, se requiere una licencia de Exchange Online Plan 2 o una licencia de Exchange Online Plan 1 con una licencia de archivado de Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="ec9a2-p102">Auto-expanding archiving also supports shared mailboxes. To enable the archive for a shared mailbox, an Exchange Online Plan 2 license or an Exchange Online Plan 1 license with an Exchange Online Archiving license is required.</span></span> 
  
## <a name="how-auto-expanding-archiving-works"></a><span data-ttu-id="ec9a2-113">¿Cómo ampliación automática funciona el archivado</span><span class="sxs-lookup"><span data-stu-id="ec9a2-113">How auto-expanding archiving works</span></span>

<span data-ttu-id="ec9a2-p103">Como buzón de correo adicional, explicado anteriormente espacio de almacenamiento se crea cuando está habilitado el buzón de archivo de un usuario. Cuando está habilitado la expansión automática de archivado, Office 365 comprueba periódicamente si el tamaño del buzón de archivo. Cuando se obtiene un buzón de archivo próximo a su límite de almacenamiento, Office 365 crea automáticamente espacio de almacenamiento adicionales para el archivo. Si el usuario se ejecuta fuera de este espacio de almacenamiento adicional, Office 365 agrega más espacio de almacenamiento para el archivo del usuario. Este proceso se realiza automáticamente, lo que significa que los administradores no deben solicitar el almacenamiento de archivos adicionales o administrar el archivado de ampliación automática.</span><span class="sxs-lookup"><span data-stu-id="ec9a2-p103">As previously explained, additional mailbox storage space is created when a user's archive mailbox is enabled. When auto-expanding archiving is enabled, Office 365 periodically checks the size of the archive mailbox. When an archive mailbox gets close to its storage limit, Office 365 automatically creates additional storage space for the archive. If the user runs out of this additional storage space, Office 365 adds more storage space to the user's archive. This process happens automatically, which means administrators don't have to request additional archive storage or manage auto-expanding archiving.</span></span> 
  
<span data-ttu-id="ec9a2-119">Este es un breve resumen del proceso.</span><span class="sxs-lookup"><span data-stu-id="ec9a2-119">Here's a quick overview of the process.</span></span>
  
![Información general del proceso de archiving ampliación automática](media/74355385-d990-44fe-8a87-6c3639d1f63f.png)
  
1. <span data-ttu-id="ec9a2-p104">El archivado está habilitado para un buzón de usuario o un buzón compartido. Se crea un buzón de archivo con 100 GB de espacio de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="ec9a2-p104">Archiving is enabled for a user mailbox or a shared mailbox. An archive mailbox with 100 GB of storage space is created.</span></span> 
    
2. <span data-ttu-id="ec9a2-p105">Un administrador habilita la ampliación automática de archivado para el buzón de correo. A continuación, cuando el buzón de archivo (incluida la carpeta elementos recuperables) alcanza 90 GB, se convierte en un archivo de ampliación automática y Office 365 agrega espacio de almacenamiento para el archivo. Tenga en cuenta que puede tardar hasta 30 días para aprovisionar el espacio de almacenamiento adicional.</span><span class="sxs-lookup"><span data-stu-id="ec9a2-p105">An administrator enables auto-expanding archiving for the mailbox. Then, when the archive mailbox (including the Recoverable Items folder) reaches 90 GB, it's converted to an auto-expanding archive, and Office 365 adds storage space to the archive. Note that it can take up to 30 days for the additional storage space to be provisioned.</span></span>
    
3. <span data-ttu-id="ec9a2-126">Office 365 agrega automáticamente más espacio de almacenamiento para el archivo cuando sea necesario.</span><span class="sxs-lookup"><span data-stu-id="ec9a2-126">Office 365 automatically adds more storage space to the archive when necessary.</span></span>
  
## <a name="what-gets-moved-to-the-additional-archive-storage-space"></a><span data-ttu-id="ec9a2-127">¿Qué Obtiene movido al espacio de almacenamiento adicionales de archiving?</span><span class="sxs-lookup"><span data-stu-id="ec9a2-127">What gets moved to the additional archive storage space?</span></span>

<span data-ttu-id="ec9a2-p106">Para hacer un uso eficiente de almacenamiento de archivo de crecimiento automático, es posible que se mueven las carpetas. Office 365 determina en qué carpetas se mueven cuando se agrega almacenamiento adicional al archivo. Cuando se mueve una carpeta, se crea automáticamente una subcarpeta bajo la carpeta original en la parte de archivo de la lista de carpetas de Outlook. Esta nueva subcarpeta apunta a los elementos que se han movido. Es la convención de nomenclatura que usa Office 365 para el nombre de la carpeta ** \<nombre de la carpeta\>_yyyy (creadas en mmm dd, aaaa h_mm)**, donde:</span><span class="sxs-lookup"><span data-stu-id="ec9a2-p106">To make efficient use of auto-expanding archive storage, folders might get moved. Office 365 determines which folders get moved when additional storage is added to the archive. When a folder is moved, a subfolder is automatically created under the original folder in the archive portion of the folder list in Outlook. This new subfolder points to the items that were moved. The naming convention that Office 365 uses to name this folder is **\<folder name\>_yyyy (Created on mmm dd, yyyy h_mm)**, where:</span></span> 
  
- <span data-ttu-id="ec9a2-133">**aaaa** es el año en que se recibieron los mensajes en la carpeta.</span><span class="sxs-lookup"><span data-stu-id="ec9a2-133">**yyyy** is the year the messages in the folder were received.</span></span> 
    
- <span data-ttu-id="ec9a2-134">**mmm dd, aaaa h_m** es la fecha y hora en que se creó la subcarpeta por Office 365, en formato UTC, en función de la zona horaria del usuario y la configuración regional en Outlook.</span><span class="sxs-lookup"><span data-stu-id="ec9a2-134">**mmm dd, yyyy h_m** is the date and time that the subfolder was created by Office 365, in UTC format, based on the user's time zone and regional settings in Outlook.</span></span> 
    
<span data-ttu-id="ec9a2-135">Las capturas de pantalla siguiente muestran una lista de carpetas antes y después de que los mensajes se mueven en un archivo expandido automático.</span><span class="sxs-lookup"><span data-stu-id="ec9a2-135">The following screen shots show a folder list before and after messages are moved in an auto-expanded archive.</span></span>
  
 <span data-ttu-id="ec9a2-136">**Antes de agrega almacenamiento adicional**</span><span class="sxs-lookup"><span data-stu-id="ec9a2-136">**Before additional storage is added**</span></span>
  
![Lista de carpetas de buzón de archivo antes de que se ha aprovisionado el archivo de ampliación automática](media/5d6d6420-e562-4912-aaab-1c111762b3f6.png)
  
 <span data-ttu-id="ec9a2-138">**Después de agrega almacenamiento adicional**</span><span class="sxs-lookup"><span data-stu-id="ec9a2-138">**After additional storage is added**</span></span>
  
![Lista de carpetas de buzón de archivo después de que se ha aprovisionado el archivo de ampliación automática](media/c03c5f51-23fa-4fc2-b887-7e7e5cce30da.png)
  
## <a name="outlook-requirements-for-accessing-items-in-an-auto-expanded-archive"></a><span data-ttu-id="ec9a2-140">Requisitos de Outlook para obtener acceso a los elementos de un archivo expandido automático</span><span class="sxs-lookup"><span data-stu-id="ec9a2-140">Outlook requirements for accessing items in an auto-expanded archive</span></span>

<span data-ttu-id="ec9a2-141">Para obtener acceso a los mensajes que se almacenan en un archivo expandido automático, los usuarios tienen que usar uno de los siguientes clientes de Outlook:</span><span class="sxs-lookup"><span data-stu-id="ec9a2-141">To access messages that are stored in an auto-expanded archive, users have to use one of the following Outlook clients:</span></span>
  
- <span data-ttu-id="ec9a2-142">Outlook 2016 para Windows</span><span class="sxs-lookup"><span data-stu-id="ec9a2-142">Outlook 2016 for Windows</span></span>
    
- <span data-ttu-id="ec9a2-143">Outlook en la web</span><span class="sxs-lookup"><span data-stu-id="ec9a2-143">Outlook on the web</span></span> 
    
- <span data-ttu-id="ec9a2-144">Outlook 2016 para Mac</span><span class="sxs-lookup"><span data-stu-id="ec9a2-144">Outlook 2016 for Mac</span></span> 
    
> [!NOTE]
> <span data-ttu-id="ec9a2-p107">Los usuarios de Outlook 2013 pueden sólo los elementos de acceso que se almacenaron originalmente en su buzón de archivo. No podrán para acceder a elementos que se mueven al almacenamiento de archivos adicionales.</span><span class="sxs-lookup"><span data-stu-id="ec9a2-p107">Outlook 2013 users can only access items that were originally stored in their archive mailbox. They won't be able to access items that are moved to additional archive storage.</span></span> 
  
<span data-ttu-id="ec9a2-147">A continuación presentamos algunas cosas que debe considerar cuando se utiliza Outlook o Outlook en el web para el acceso a los mensajes almacenados en un archivo expandido automático.</span><span class="sxs-lookup"><span data-stu-id="ec9a2-147">Here are some things to consider when using Outlook or Outlook on the web to access messages stored in an auto-expanded archive.</span></span>
  
- <span data-ttu-id="ec9a2-148">Puede tener acceso a cualquier carpeta en su buzón de archivo, los que se han movido al área de almacenamiento expandido automático incluidos.</span><span class="sxs-lookup"><span data-stu-id="ec9a2-148">You can access any folder in your archive mailbox, including ones that were moved to the auto-expanded storage area.</span></span>
    
- <span data-ttu-id="ec9a2-p108">Puede buscar los elementos que se han movido a un área de almacenamiento adicional buscando la propia carpeta. Esto significa que tiene que seleccionar la carpeta de archivos en la lista de carpetas para seleccionar la opción de la **Carpeta actual** como el ámbito de búsqueda. De forma similar, si una carpeta en un área de almacenamiento expandido automático contiene las subcarpetas, se debe buscar en cada subcarpeta por separado.</span><span class="sxs-lookup"><span data-stu-id="ec9a2-p108">You can search for items that were moved to an additional storage area only by searching the folder itself. This means you have to select the archive folder in the folder list to select the **Current Folder** option as the search scope. Similarly, if a folder in an auto-expanded storage area contains subfolders, you have to search each subfolder separately.</span></span> 
    
- <span data-ttu-id="ec9a2-152">Los recuentos de elemento en Outlook y recuentos de leído/no leído (en Outlook y Outlook en el web) en un archivo expandido automático es posible que no sean precisos.</span><span class="sxs-lookup"><span data-stu-id="ec9a2-152">Item counts in Outlook and Read/Unread counts (in Outlook and Outlook on the web ) in an auto-expanded archive might not be accurate.</span></span>
    
- <span data-ttu-id="ec9a2-153">Puede eliminar elementos en una subcarpeta que apunta a un área de almacenamiento expandido automático, pero no se puede eliminar la propia carpeta.</span><span class="sxs-lookup"><span data-stu-id="ec9a2-153">You can delete items in a subfolder that points to an auto-expanded storage area, but the folder itself can't be deleted.</span></span>
    
- <span data-ttu-id="ec9a2-154">No puede usar la característica recuperar elementos eliminados para recuperar un elemento que se ha eliminado de un área de almacenamiento expandido automático.</span><span class="sxs-lookup"><span data-stu-id="ec9a2-154">You can't use the Recover Deleted Items feature to recover an item that was deleted from an auto-expanded storage area.</span></span>
  
## <a name="auto-expanding-archiving-and-other-office-365-compliance-features"></a><span data-ttu-id="ec9a2-155">Ampliación automática de archivado y otras características de cumplimiento de normas de Office 365</span><span class="sxs-lookup"><span data-stu-id="ec9a2-155">Auto-expanding archiving and other Office 365 compliance features</span></span>

<span data-ttu-id="ec9a2-156">En esta sección se explica la funcionalidad entre la ampliación automática de archivado y otros cumplimiento de Office 365 y características de gobierno de datos.</span><span class="sxs-lookup"><span data-stu-id="ec9a2-156">This section explains the functionality between auto-expanding archiving and other Office 365 compliance and data governance features.</span></span>
  
- <span data-ttu-id="ec9a2-157">También se busca en la **exhibición de documentos electrónicos** - cuando use una herramienta de exhibición de documentos electrónicos de Office 365, como la búsqueda de contenido o en contexto exhibición de documentos electrónicos, las áreas de almacenamiento de información adicional en un archivo expandido automático.</span><span class="sxs-lookup"><span data-stu-id="ec9a2-157">**eDiscovery** - When you use an Office 365 eDiscovery tool, such as Content Search or In-Place eDiscovery, the additional storage areas in an auto-expanded archive are also searched.</span></span>
    
- <span data-ttu-id="ec9a2-158">**Retención** - al poner un buzón de correo en espera mediante herramientas como juicio en Exchange Online o contiene el caso de exhibición de documentos electrónicos y las directivas de retención de la seguridad de Office 365 &amp; centro de cumplimiento, contenido que se encuentra en un archivo expandido automático también es pondrá en espera.</span><span class="sxs-lookup"><span data-stu-id="ec9a2-158">**Retention** - When you put a mailbox on hold by using tools such as Litigation Hold in Exchange Online or eDiscovery case holds and retention policies in the Office 365 Security &amp; Compliance Center, content located in an auto-expanded archive is also placed on hold.</span></span>
    
- <span data-ttu-id="ec9a2-159">También se eliminará de **mensajería (MRM) de administración de registros** - si usa las directivas de eliminación de MRM en Exchange Online para eliminar permanentemente los elementos del buzón que han expirado, elementos caducados que se encuentra en el archivo expandido automático.</span><span class="sxs-lookup"><span data-stu-id="ec9a2-159">**Messaging records management (MRM)** - If you use MRM deletion policies in Exchange Online to permanently delete expired mailbox items, expired items located in the auto-expanded archive will also be deleted.</span></span>
    
- <span data-ttu-id="ec9a2-p109">**Importación de servicio** - puede usar el servicio Office 365 importar para importar archivos PST al archivo expandido automático de un usuario. Puede importar hasta 100 GB de datos de los archivos PST al buzón de archivo del usuario.</span><span class="sxs-lookup"><span data-stu-id="ec9a2-p109">**Import service** - You can use the Office 365 Import service to import PST files to a user's auto-expanded archive. You can import up to 100 GB of data from PST files to the user's archive mailbox.</span></span> 
