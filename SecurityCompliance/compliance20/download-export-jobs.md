---
title: Descargar trabajos de exportación
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: 56ed8eac259974b43ca0cd26b2bd0c339a5fc05b
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/17/2019
ms.locfileid: "34155152"
---
# <a name="download-export-jobs"></a><span data-ttu-id="483a5-102">Descargar trabajos de exportación</span><span class="sxs-lookup"><span data-stu-id="483a5-102">Download export jobs</span></span>

<span data-ttu-id="483a5-103">Todos los datos exportados se agregan a un BLOB de Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="483a5-103">All exported data is added to a Microsoft Azure blob.</span></span> <span data-ttu-id="483a5-104">Esto proporciona varias opciones para controlar los datos de forma descendente.</span><span class="sxs-lookup"><span data-stu-id="483a5-104">This provides multiple options to handle the data downstream.</span></span> <span data-ttu-id="483a5-105">Hay varias formas de tener acceso a un BLOB de Azure.</span><span class="sxs-lookup"><span data-stu-id="483a5-105">There are several ways to access an Azure blob.</span></span> <span data-ttu-id="483a5-106">Un método es usar el explorador de almacenamiento de Azure.</span><span class="sxs-lookup"><span data-stu-id="483a5-106">One method is to use Azure Storage Explorer.</span></span> <span data-ttu-id="483a5-107">Este método admite conexión simple, exploración y descarga.</span><span class="sxs-lookup"><span data-stu-id="483a5-107">This method supports simple connection, browsing and downloading.</span></span> <span data-ttu-id="483a5-108">Para obtener más información, visite<https://docs.microsoft.com/en-us/azure/storage/blobs/storage-quickstart-blobs-storage-explorer></span><span class="sxs-lookup"><span data-stu-id="483a5-108">For more information, visit <https://docs.microsoft.com/en-us/azure/storage/blobs/storage-quickstart-blobs-storage-explorer></span></span>

1.  <span data-ttu-id="483a5-109">Para descargar contenido después de completar un trabajo de exportación, vaya a la pestaña exportaciones y seleccione un trabajo de exportación.</span><span class="sxs-lookup"><span data-stu-id="483a5-109">To download content after an export job is complete, go to the Exports tab and select an export job.</span></span>

2.  <span data-ttu-id="483a5-110">Copie el texto en la sección "ubicaciones" del control flotante.</span><span class="sxs-lookup"><span data-stu-id="483a5-110">Copy the text in the “Locations” section of the flyout.</span></span>

![](../media/eDiscoExportJob.png)

3.  <span data-ttu-id="483a5-111">Abra el explorador de Azure Storage y haga clic en el botón "conectar"</span><span class="sxs-lookup"><span data-stu-id="483a5-111">Open Azure Storage Explorer and click the “Connect” button</span></span>

![](../media/AzureStorageConnect.png)

4.  <span data-ttu-id="483a5-112">Seleccione "usar un URI de firma de acceso compartido" y haga clic en siguiente.</span><span class="sxs-lookup"><span data-stu-id="483a5-112">Select “Use a shared access signature URI” and click next</span></span>

![](../media/AzureStorageConnect2.png)

5.  <span data-ttu-id="483a5-113">Pegue el texto de ubicación en el cuadro de texto URI y haga clic en siguiente.</span><span class="sxs-lookup"><span data-stu-id="483a5-113">Paste the Location text in the URI text box and click next</span></span>

![](../media/AzureStorageConnect3.png)

6.  <span data-ttu-id="483a5-114">Haga clic en conectar</span><span class="sxs-lookup"><span data-stu-id="483a5-114">Click Connect</span></span>

![](../media/AzureStorageConnect4.png)

<span data-ttu-id="483a5-115">Esto agregará la exportación como un objeto en las cuentas de almacenamiento, los servicios de datos adjuntos de SAS o los contenedores de blobs.</span><span class="sxs-lookup"><span data-stu-id="483a5-115">This will add the export as an object in Storage Accounts/SAS-Attached Services/Blob Containers.</span></span> <span data-ttu-id="483a5-116">Podrá explorar la exportación y descargar todas o parte de la exportación.</span><span class="sxs-lookup"><span data-stu-id="483a5-116">You will be able to explore the export and download all or portions of the export.</span></span>

![](../media/AzureStorageConnect5.png)