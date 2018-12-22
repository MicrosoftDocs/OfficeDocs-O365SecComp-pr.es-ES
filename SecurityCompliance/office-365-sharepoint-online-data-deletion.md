---
title: Eliminación de datos en línea de SharePoint de Office 365
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: Office 365 Administration
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: Una explicación de eliminación de datos en SharePoint Online.
ms.openlocfilehash: 8a84859ce170a4c3ca713c751aef2b6d5b911c55
ms.sourcegitcommit: 29ba4c36af8e90ddc8d885863ef25bac2cffbe94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2018
ms.locfileid: "27411166"
---
# <a name="sharepoint-online-data-deletion-in-office-365"></a><span data-ttu-id="907a3-103">Eliminación de datos en línea de SharePoint en Office 365</span><span class="sxs-lookup"><span data-stu-id="907a3-103">SharePoint Online Data Deletion in Office 365</span></span>

<span data-ttu-id="907a3-p101">SharePoint Online almacena objetos como abstracta código dentro de las bases de datos de aplicación. Cuando un usuario carga un archivo en SharePoint Online, ese archivo se desmontar y traducir a código de la aplicación y se almacena en varias tablas a través de varias bases de datos. En SharePoint Online, todo el contenido que un cliente carga se divide en fragmentos, cifrados (potencialmente con varias claves de AES de 256 bits) y distribuido en el centro de datos. Para obtener información específica acerca del proceso de fragmentación y el cifrado, vea [cifrado en la nube de Microsoft](office-365-encryption-in-the-microsoft-cloud-overview.md).</span><span class="sxs-lookup"><span data-stu-id="907a3-p101">SharePoint Online stores objects as abstracted code within application databases. When a user uploads a file to SharePoint Online, that file is disassembled and translated into application code and stored in multiple tables across multiple databases. In SharePoint Online, all content that a customer uploads is broken into chunks, encrypted (potentially with multiple AES 256-bit keys), and distributed across the datacenter. For specific details about the chunking and encryption process, see [Encryption in the Microsoft Cloud](office-365-encryption-in-the-microsoft-cloud-overview.md).</span></span> 

<span data-ttu-id="907a3-p102">En SharePoint Online, los elementos se conservan para 93 días desde el momento en que eliminarlos de su ubicación original. Permanecer en la Papelera de reciclaje del sitio todo el tiempo, a menos que alguien elimina ellos desde allí o vacía la Papelera de reciclaje. En ese caso, los elementos se vaya a la colección de sitios Papelera de reciclaje, donde permanecen para el resto de los días 93. Para obtener información acerca de cómo restaurar los elementos eliminados, vea [restaurar los elementos en la Papelera de reciclaje de un sitio de SharePoint](https://support.office.com/en-us/article/6df466b6-55f2-4898-8d6e-c0dff851a0be#ID0EAADAAA=Online
) y [Restaurar elementos eliminados de la Papelera de reciclaje de la colección de sitios](https://support.office.com/article/5fa924ee-16d7-487b-9a0a-021b9062d14b). El tiempo de retención de la Papelera de reciclaje no es configurable en SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="907a3-p102">In SharePoint Online, items are retained for 93 days from the time you delete them from their original location. They stay in the site Recycle Bin the entire time, unless someone deletes them from there or empties that Recycle Bin. In that case, the items go to the site collection Recycle Bin, where they stay for the remainder of the 93 days. For info about restoring deleted items, see [Restore items in the Recycle Bin of a SharePoint site](https://support.office.com/en-us/article/6df466b6-55f2-4898-8d6e-c0dff851a0be#ID0EAADAAA=Online
) and [Restore deleted items from the site collection recycle bin](https://support.office.com/article/5fa924ee-16d7-487b-9a0a-021b9062d14b). The Recycle Bin retention time is not configurable in SharePoint Online.</span></span>

<span data-ttu-id="907a3-113">Cuando se elimina una colección de sitios, también está eliminando la jerarquía de sitios en la colección y todo el contenido dentro de ellos:</span><span class="sxs-lookup"><span data-stu-id="907a3-113">When you delete a site collection, you're also deleting the hierarchy of sites in the collection, and all content within them:</span></span>
- <span data-ttu-id="907a3-114">Documentos y bibliotecas de documentos</span><span class="sxs-lookup"><span data-stu-id="907a3-114">Documents and document libraries</span></span>
- <span data-ttu-id="907a3-115">Listas y datos de lista</span><span class="sxs-lookup"><span data-stu-id="907a3-115">Lists and list data</span></span>
- <span data-ttu-id="907a3-116">Opciones de configuración de sitio</span><span class="sxs-lookup"><span data-stu-id="907a3-116">Site configuration settings</span></span>
- <span data-ttu-id="907a3-117">Información de roles y seguridad que está relacionada con el sitio o sus subsitios</span><span class="sxs-lookup"><span data-stu-id="907a3-117">Role and security information that is related to the site or its subsites</span></span>
- <span data-ttu-id="907a3-118">Subsitios de la información de sitio Web, su contenido y el usuario de nivel superior</span><span class="sxs-lookup"><span data-stu-id="907a3-118">Subsites of the top-level website, their contents, and user information</span></span>

<span data-ttu-id="907a3-119">Si accidentalmente elimina una colección de sitios, se puede restaurar de forma global o SharePoint admin con el centro de administración de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="907a3-119">If you accidentally delete a site collection, it can be restored by a global or SharePoint admin using the SharePoint admin center.</span></span> 

<span data-ttu-id="907a3-p103">Eliminación de disco duro se produce cuando un usuario purga los elementos eliminados de la Papelera de reciclaje de la colección de sitios cuando expiren los períodos de retención y copia de seguridad, o cuando un administrador elimina de forma permanente una colección de sitios mediante el [cmdlet Remove-SPODeletedSite](/powershell/module/sharepoint-online/Remove-SPODeletedSite?view=sharepoint-ps). Cuando se elimina un usuario de disco duro (elimina de forma permanente o depura) también se eliminan contenido de SharePoint Online, todas las claves de cifrado para los fragmentos eliminados. Los bloques en los discos que anteriormente se almacenan los fragmentos eliminados se marcan como no usado y están disponible para volver a usar.</span><span class="sxs-lookup"><span data-stu-id="907a3-p103">Hard deletion occurs when a user purges deleted items from the site collection Recycle Bin, when the retention and backup periods expire, or when an administrator permanently deletes a site collection using the [Remove-SPODeletedSite cmdlet](/powershell/module/sharepoint-online/Remove-SPODeletedSite?view=sharepoint-ps). When a user hard deletes (permanently deletes, or purges) content from SharePoint Online, all encryption keys for the deleted chunks are also deleted. The blocks on the disks that previously stored the deleted chunks are marked as unused and available for re-use.</span></span>
