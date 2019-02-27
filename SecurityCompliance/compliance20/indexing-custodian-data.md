---
title: Clasificación avanzada de los datos de administración
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: 1521aadca42c8119ae341065865b227fb16ffcf3
ms.sourcegitcommit: baf23be44f1ed5abbf84f140b5ffa64fce605478
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/26/2019
ms.locfileid: "30295033"
---
# <a name="advanced-indexing-of-custodian-data"></a><span data-ttu-id="9fc99-102">Clasificación avanzada de los datos de administración</span><span class="sxs-lookup"><span data-stu-id="9fc99-102">Advanced indexing of custodian data</span></span>

<span data-ttu-id="9fc99-p101">Cuando se agrega un custodio a un caso de exhibición avanzada de documentos electrónicos (versión preliminar), cualquier contenido de Office 365 que se considere indizado parcialmente se vuelve a procesar para que pueda ser buscado por completo.  Este proceso se denomina *indizaCión avanzada*. El contenido se puede indizar parcialmente por varios motivos, como la existencia de imágenes, tipos de archivo no admitidos o cuando se encuentran límites de tamaño de archivo de indización.</span><span class="sxs-lookup"><span data-stu-id="9fc99-p101">When a custodian is added to an Advanced eDiscovery (Preview) case, any content in Office 365 that was deemed as partially indexed is re-processed to make it fully searchable.  This process is called *Advanced indexing*. Content can be partially indexed for a number of reasons including the existence of images, unsupported file types or when indexing file size limits are encountered.</span></span>

<span data-ttu-id="9fc99-106">Para obtener más información acerca de la compatibilidad de procesamiento en Office 365 y elementos parcialmente indizados, vea:</span><span class="sxs-lookup"><span data-stu-id="9fc99-106">To learn more about processing support in Office 365 and partially indexed items, see:</span></span>

- [<span data-ttu-id="9fc99-107">Tipos de archivo admitidos en eDiscovery avanzado</span><span class="sxs-lookup"><span data-stu-id="9fc99-107">Supported file types in Advanced eDiscovery</span></span>](supported-filetypes-ediscovery20.md)
- [<span data-ttu-id="9fc99-108">Elementos parcialmente indizados en la búsqueda de contenido en Office 365</span><span class="sxs-lookup"><span data-stu-id="9fc99-108">Partially indexed items in Content Search in Office 365</span></span>](https://docs.microsoft.com/en-us/office365/securitycompliance/partially-indexed-items-in-content-search)
- [<span data-ttu-id="9fc99-109">Formatos de archivo indizados por la búsqueda de Exchange</span><span class="sxs-lookup"><span data-stu-id="9fc99-109">File formats indexed by Exchange Search</span></span>](https://docs.microsoft.com/en-us/exchange/file-formats-indexed-by-exchange-search-exchange-2013-help)
- [<span data-ttu-id="9fc99-110">Extensiones de nombres de archivo rastreados y tipos de archivo analizados de forma predeterminada en SharePoint Server</span><span class="sxs-lookup"><span data-stu-id="9fc99-110">Default crawled file name extensions and parsed file types in SharePoint Server</span></span>](https://docs.microsoft.com/en-us/SharePoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)

## <a name="viewing-advanced-indexing-results"></a><span data-ttu-id="9fc99-111">Ver resultados de indización avanzada</span><span class="sxs-lookup"><span data-stu-id="9fc99-111">Viewing Advanced indexing results</span></span>

<span data-ttu-id="9fc99-p102">Una vez completado el proceso de indización avanzado, puede comprender la efectividad del procesamiento.  En la vista de indización del custodio, el gráfico muestra todos los elementos agregados al *Índice híbrido*.  El índice híbrido es donde la exhibición avanzada de documentos electrónicos (vista previa) almacena el contenido que se ha vuelto a procesar.</span><span class="sxs-lookup"><span data-stu-id="9fc99-p102">After the Advanced indexing process is completed, you can get an understanding of the effectiveness of re-processing.  In the Custodian Indexing view, the graph lists all items added to the *hybrid index*.  The hybrid index is where Advanced eDiscovery (Preview) stores the re-processed content.</span></span>

<span data-ttu-id="9fc99-p103">El gráfico también incluye el número de elementos que requieren corrección y otro gráfico de errores por tipo de archivo. Para obtener más información, vea [corrección de errores al procesar datos](error-remediation.md).</span><span class="sxs-lookup"><span data-stu-id="9fc99-p103">The graph also includes the number of items that require remediation and another graph of errors by file type. For more information, see [Error remediation when processing data](error-remediation.md).</span></span>

## <a name="updating-advanced-indexes-for-custodians"></a><span data-ttu-id="9fc99-117">Actualización de índices avanzados para custodios</span><span class="sxs-lookup"><span data-stu-id="9fc99-117">Updating Advanced indexes for custodians</span></span>

<span data-ttu-id="9fc99-p104">Cuando se agrega un custodio a un caso de eDiscovery avanzado (vista previa), todos los elementos parcialmente indizados se vuelven a procesar. Sin embargo, a medida que pasa el tiempo, se pueden agregar más elementos indizados parcialmente al buzón de un usuario o a una cuenta de OneDrive.  Cuando sea necesario, puede actualizar los índices.</span><span class="sxs-lookup"><span data-stu-id="9fc99-p104">When a custodian is added to an Advanced eDiscovery (Preview) case, all partially indexed items are re-processed. However, as time passes, more partially indexed items may be added to a user's mailbox or OneDrive account.  When needed, you can update the indexes.</span></span>

> [!NOTE]
> <span data-ttu-id="9fc99-p105">La actualización de los índices de custodios es un proceso de ejecución prolongada. Se recomienda no actualizar índices más de una vez al día en un caso.</span><span class="sxs-lookup"><span data-stu-id="9fc99-p105">Updating custodian indexes is a long running process. It's recommended that you don't update indexes more than once per day in a case.</span></span>
