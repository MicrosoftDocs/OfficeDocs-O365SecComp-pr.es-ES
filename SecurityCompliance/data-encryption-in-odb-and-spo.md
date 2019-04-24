---
title: Cifrado de datos en OneDrive para la Empresa y SharePoint Online
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 7/2/2018
ms.audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
- MET150
ms.assetid: 6501b5ef-6bf7-43df-b60d-f65781847d6c
ms.collection:
- M365-security-compliance
description: Entienda los elementos básicos del cifrado de seguridad de datos en OneDrive para la Empresa y SharePoint Online.
ms.openlocfilehash: 84d44ceec96545388d0e4f77f0a84e95ff07db59
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32258158"
---
# <a name="data-encryption-in-onedrive-for-business-and-sharepoint-online"></a><span data-ttu-id="55284-103">Cifrado de datos en OneDrive para la Empresa y SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="55284-103">Data Encryption in OneDrive for Business and SharePoint Online</span></span>

<span data-ttu-id="55284-104">Entienda los elementos básicos del cifrado de seguridad de datos en OneDrive para la Empresa y SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="55284-104">Understand the basic elements of encryption for data security in OneDrive for Business and SharePoint Online.</span></span>
  
## <a name="overview"></a><span data-ttu-id="55284-105">Información general</span><span class="sxs-lookup"><span data-stu-id="55284-105">Overview</span></span>

<span data-ttu-id="55284-p101">Office 365 es un entorno altamente seguro que ofrece protección amplia en varias capas: seguridad de centro de datos físico, seguridad de red, seguridad de acceso, seguridad de aplicaciones y seguridad de datos. Este artículo se centra específicamente en el lado del cifrado en tránsito y en reposo de la seguridad de datos para OneDrive para la Empresa y SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="55284-p101">Office 365 is a highly secure environment that offers extensive protection in multiple layers: physical data center security, network security, access security, application security, and data security. This article specifically focuses on the in-transit and at-rest encryption side of data security for OneDrive for Business and SharePoint Online.</span></span>
  
<span data-ttu-id="55284-108">Para obtener una descripción de la seguridad de Office 365 como un todo, consulte las notas [del producto sobre seguridad en office 365](https://go.microsoft.com/fwlink/p/?LinkId=270895).</span><span class="sxs-lookup"><span data-stu-id="55284-108">For a description of Office 365 security as a whole, see [Security in Office 365 White Paper](https://go.microsoft.com/fwlink/p/?LinkId=270895).</span></span>
  
<span data-ttu-id="55284-109">Vea cómo funciona el cifrado de datos en el siguiente vídeo.</span><span class="sxs-lookup"><span data-stu-id="55284-109">Watch how data encryption works in the following video.</span></span>
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/dea0dec4-4077-4095-9a32-19b94ea2da4b?autoplay=false]
  
## <a name="encryption-of-data-in-transit"></a><span data-ttu-id="55284-110">Cifrado de datos en tránsito</span><span class="sxs-lookup"><span data-stu-id="55284-110">Encryption of data in transit</span></span>

<span data-ttu-id="55284-111">En OneDrive para la Empresa y SharePoint Online, hay dos escenarios en los que los datos entran y salen de los centros de datos.</span><span class="sxs-lookup"><span data-stu-id="55284-111">In OneDrive for Business and SharePoint Online, there are two scenarios in which data enters and exits the datacenters.</span></span>
  
- <span data-ttu-id="55284-p102">**Comunicación del cliente con el servidor** La comunicación con OneDrive para la Empresa a través de Internet usa conexiones SSL/TLS. Todas las conexiones SSL se establecen con claves de 2048 bits.</span><span class="sxs-lookup"><span data-stu-id="55284-p102">**Client communication with the server** Communication to OneDrive for Business across the Internet uses SSL/TLS connections. All SSL connections are established using 2048-bit keys.</span></span>

- <span data-ttu-id="55284-p103">**Movimiento de datos entre centros de datos** La razón principal para mover datos entre centros de datos es que la replicación geográfica habilite la recuperación ante desastres. Por ejemplo, los registros de transacciones y diferencias de almacenamiento de blobs de SQL Server recorren esta canalización. Mientras que estos datos ya se transmiten mediante una red privada, tendrán una mayor protección con el mejor cifrado de su clase.</span><span class="sxs-lookup"><span data-stu-id="55284-p103">**Data movement between datacenters** The primary reason to move data between datacenters is for geo-replication to enable disaster recovery. For instance, SQL Server transaction logs and blob storage deltas travel along this pipe. While this data is already transmitted by using a private network, it is further protected with best-in-class encryption.</span></span> 

## <a name="encryption-of-data-at-rest"></a><span data-ttu-id="55284-117">Cifrado de datos en reposo</span><span class="sxs-lookup"><span data-stu-id="55284-117">Encryption of data at rest</span></span>

<span data-ttu-id="55284-118">El cifrado en reposo incluye dos componentes: cifrado de nivel de disco de BitLocker y cifrado por archivo del contenido del cliente.</span><span class="sxs-lookup"><span data-stu-id="55284-118">Encryption at rest includes two components: BitLocker disk-level encryption and per-file encryption of customer content.</span></span>
  
<span data-ttu-id="55284-119">BitLocker se implementa para OneDrive para la Empresa y SharePoint Online en todo el servicio.</span><span class="sxs-lookup"><span data-stu-id="55284-119">BitLocker is deployed for OneDrive for Business and SharePoint Online across the service.</span></span> <span data-ttu-id="55284-120">El cifrado por archivo también se encuentra en OneDrive para la empresa y SharePoint Online en Office 365 multiinquilino y en entornos dedicados nuevos que se basan en tecnología multiempresa.</span><span class="sxs-lookup"><span data-stu-id="55284-120">Per-file encryption is also in OneDrive for Business and SharePoint Online in Office 365 multi-tenant and new dedicated environments that are built on multi-tenant technology.</span></span>
  
<span data-ttu-id="55284-p105">Mientras que BitLocker cifra todos los datos en un disco, el cifrado por archivo va más allá al incluir una clave de cifrado única para cada archivo. Además, la actualización de cada archivo se cifra mediante su propia clave de cifrado. Antes de almacenarse, las claves del contenido cifrado se almacenan en una ubicación físicamente independiente del contenido. Cada paso de este cifrado usa el Estándar de cifrado avanzado (AES) con claves de 256 bits y cumple el Estándar federal de procesamiento de información (FIPS) 140-2. El contenido cifrado se distribuye entre varios contenedores en el centro de datos y cada contenedor tiene credenciales exclusivas. Estas credenciales se almacenan en una ubicación física independiente del contenido o de las claves de contenido.</span><span class="sxs-lookup"><span data-stu-id="55284-p105">While BitLocker encrypts all data on a disk, per-file encryption goes even further by including a unique encryption key for each file. Further, every update to every file is encrypted using its own encryption key. Before they're stored, the keys to the encrypted content are stored in a physically separate location from the content. Every step of this encryption uses Advanced Encryption Standard (AES) with 256-bit keys and is Federal Information Processing Standard (FIPS) 140-2 compliant. The encrypted content is distributed across a number of containers throughout the datacenter, and each container has unique credentials. These credentials are stored in a separate physical location from either the content or the content keys.</span></span>
  
<span data-ttu-id="55284-127">Para obtener más información sobre el cumplimiento de FIPS 140-2, consulte [fips 140-2 Compliance](https://go.microsoft.com/fwlink/?LinkId=517625).</span><span class="sxs-lookup"><span data-stu-id="55284-127">For additional information about FIPS 140-2 compliance, see [FIPS 140-2 Compliance](https://go.microsoft.com/fwlink/?LinkId=517625).</span></span>
  
<span data-ttu-id="55284-p106">El cifrado de nivel de archivo en reposo saca provecho del almacenamiento de blobs para ofrecer aumento de almacenamiento prácticamente ilimitado y habilitar una protección sin precedentes. Todo el contenido de clientes en OneDrive para la Empresa y SharePoint Online se migrará al almacenamiento de blobs. A continuación, se muestra cómo se protegen los datos:</span><span class="sxs-lookup"><span data-stu-id="55284-p106">File-level encryption at rest takes advantage of blob storage to provide for virtually unlimited storage growth and to enable unprecedented protection. All customer content in OneDrive for Business and SharePoint Online will be migrated to blob storage. Here's how that data is secured:</span></span>
  
1. <span data-ttu-id="55284-p107">Todo el contenido se cifra, potencialmente con varias claves, y se distribuye por el centro de datos. Todos los archivos que se van a almacenar se dividen en uno o varios fragmentos, según su tamaño. A continuación, cada fragmento se cifra mediante su propia clave única. Las actualizaciones se administran de forma similar: el conjunto de cambios o diferencias, enviado por un usuario, se divide en fragmentos y cada uno se cifra con su propia clave.</span><span class="sxs-lookup"><span data-stu-id="55284-p107">All content is encrypted, potentially with multiple keys, and distributed across the datacenter. Each file to be stored is broken into one or more chunks, depending its size. Then, each chunk is encrypted using its own unique key. Updates are handled similarly: the set of changes, or deltas, submitted by a user is broken into chunks, and each is encrypted with its own key.</span></span>

2. <span data-ttu-id="55284-p108">Todos estos fragmentos (archivos, partes de archivos y diferencias de actualización) se almacenan como blobs en nuestro almacén de blobs. También se distribuyen aleatoriamente entre varios contenedores de blobs.</span><span class="sxs-lookup"><span data-stu-id="55284-p108">All of these chunks—files, pieces of files, and update deltas—are stored as blobs in our blob store. They also are randomly distributed across multiple blob containers.</span></span>

3. <span data-ttu-id="55284-137">El "mapa" que se usa para volver a ensamblar el archivo a partir de sus componentes se almacena en la base de datos de contenido.</span><span class="sxs-lookup"><span data-stu-id="55284-137">The "map" used to re-assemble the file from its components is stored in the Content Database.</span></span>

4. <span data-ttu-id="55284-p109">Cada contenedor de blobs tiene sus propias credenciales únicas por tipo de acceso (lectura, escritura, enumeración y eliminación). Cada conjunto de credenciales se encuentra en el almacén de claves seguras y se actualiza periódicamente.</span><span class="sxs-lookup"><span data-stu-id="55284-p109">Each blob container has its own unique credentials per access type (read, write, enumerate, and delete). Each set of credentials is held in the secure Key Store and is regularly refreshed.</span></span>

<span data-ttu-id="55284-140">En otras palabras, hay tres tipos diferentes de almacenes implicados en el cifrado por archivo en reposo, cada uno con una función distinta:</span><span class="sxs-lookup"><span data-stu-id="55284-140">In other words, there are three different types of stores involved in per-file encryption at rest, each with a distinct function:</span></span>
  
- <span data-ttu-id="55284-p110">El contenido se almacena como blobs cifrados en el almacén de blobs. La clave de cada fragmento de contenido se cifra y almacena por separado en la base de datos de contenido. El propio contenido no retiene ninguna pista sobre cómo se puede descifrar.</span><span class="sxs-lookup"><span data-stu-id="55284-p110">Content is stored as encrypted blobs in the blob store. The key to each chunk of content is encrypted and stored separately in the content database. The content itself holds no clue as to how it can be decrypted.</span></span>

- <span data-ttu-id="55284-p111">La base de datos de contenido es una base de datos de SQL Server. Contiene el mapa necesario para localizar y volver a ensamblar todos los blobs de contenido que se encuentran en el almacén de blobs, así como las claves necesarias para descifrar esos blobs.</span><span class="sxs-lookup"><span data-stu-id="55284-p111">The Content Database is a SQL Server database. It holds the map required to locate and reassemble all of the content blobs held in the blob store as well as the keys needed to decrypt those blobs.</span></span>

<span data-ttu-id="55284-p112">Cada uno de estos tres componentes de almacenamiento (el almacén de blobs, la base de datos de contenido y el almacén de claves) es físicamente independiente. La información contenida en cualquiera de los componentes es inutilizable por sí misma. Esto proporciona un nivel de seguridad sin precedentes. Sin acceso a los tres, es imposible recuperar las claves para los fragmentos, descifrar las claves para que puedan utilizarse, asociar las claves con sus fragmentos correspondientes, descifrar cualquier fragmento o reconstruir un documento a partir de sus fragmentos constituyentes.</span><span class="sxs-lookup"><span data-stu-id="55284-p112">Each of these three storage components—the blob store, the Content Database, and the Key Store—is physically separate. The information held in any one of the components is unusable on its own. This provides an unprecedented level of security. Without access to all three it is impossible to retrieve the keys to the chunks, decrypt the keys to make them usable, associate the keys with their corresponding chunks, decrypt any chunk, or reconstruct a document from its constituent chunks.</span></span>