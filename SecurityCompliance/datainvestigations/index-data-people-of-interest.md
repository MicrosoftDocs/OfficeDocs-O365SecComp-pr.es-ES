---
title: Indización avanzada de datos para una investigación
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
ms.openlocfilehash: 2e2077fa5ee5333a563470d5bcbb140364bc0ba2
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/17/2019
ms.locfileid: "34150782"
---
# <a name="advanced-indexing-of-data-for-an-investigation"></a><span data-ttu-id="8b394-102">Indización avanzada de datos para una investigación</span><span class="sxs-lookup"><span data-stu-id="8b394-102">Advanced indexing of data for an investigation</span></span>

<span data-ttu-id="8b394-103">El contenido del sistema activo se puede indizar parcialmente por una serie de motivos, como la existencia de imágenes, tipos de archivo no admitidos o cuando se encuentran límites de tamaño de archivo de indización.</span><span class="sxs-lookup"><span data-stu-id="8b394-103">Content in the live system can be partially indexed for a number of reasons including the existence of images, unsupported file types or when indexing file size limits are encountered.</span></span> <span data-ttu-id="8b394-104">Cuando se trata de un derrame de datos de riesgo alto, desea asegurarse de que la búsqueda capturó todos los datos que desea investigar.</span><span class="sxs-lookup"><span data-stu-id="8b394-104">When you are dealing with high risk data spill, you want to make sure that your search captured all data that you want to investigate.</span></span> <span data-ttu-id="8b394-105">Cuando se agrega una persona de interés a una investigación de datos, cualquier contenido de Office 365 que se consideró tal y como se consideraba parcialmente indizada se vuelve a procesar para que sea posible realizar búsquedas por completo.</span><span class="sxs-lookup"><span data-stu-id="8b394-105">When a person of interest is added to a Data investigation, any content in Office 365 that was deemed as partially indexed is re-processed to make it fully searchable.</span></span> <span data-ttu-id="8b394-106">Este proceso se denomina *indización avanzada*.</span><span class="sxs-lookup"><span data-stu-id="8b394-106">This process is called *Advanced indexing*.</span></span> 

<span data-ttu-id="8b394-107">Para obtener más información acerca de la compatibilidad de procesamiento en Office 365 y elementos parcialmente indizados, vea:</span><span class="sxs-lookup"><span data-stu-id="8b394-107">To learn more about processing support in Office 365 and partially indexed items, see:</span></span>

- [<span data-ttu-id="8b394-108">Tipos de archivo admitidos en investigaciones de datos</span><span class="sxs-lookup"><span data-stu-id="8b394-108">Supported file types in Data Investigations</span></span>](supported-filetypes-datainvestigations.md)

- [<span data-ttu-id="8b394-109">Elementos parcialmente indizados en la búsqueda de contenido en Office 365</span><span class="sxs-lookup"><span data-stu-id="8b394-109">Partially indexed items in Content Search in Office 365</span></span>](https://docs.microsoft.com/en-us/office365/securitycompliance/partially-indexed-items-in-content-search)

- [<span data-ttu-id="8b394-110">Formatos de archivo indizados por la búsqueda de Exchange</span><span class="sxs-lookup"><span data-stu-id="8b394-110">File formats indexed by Exchange Search</span></span>](https://docs.microsoft.com/en-us/exchange/file-formats-indexed-by-exchange-search-exchange-2013-help)

- [<span data-ttu-id="8b394-111">Extensiones de nombres de archivo rastreados y tipos de archivo analizados de forma predeterminada en SharePoint Server</span><span class="sxs-lookup"><span data-stu-id="8b394-111">Default crawled file name extensions and parsed file types in SharePoint Server</span></span>](https://docs.microsoft.com/en-us/SharePoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)

## <a name="viewing-advanced-indexing-results"></a><span data-ttu-id="8b394-112">Ver resultados de indización avanzada</span><span class="sxs-lookup"><span data-stu-id="8b394-112">Viewing Advanced indexing results</span></span>

<span data-ttu-id="8b394-113">Una vez completado el proceso de indización avanzado, puede comprender la efectividad del procesamiento.</span><span class="sxs-lookup"><span data-stu-id="8b394-113">After the Advanced indexing process is completed, you can get an understanding of the effectiveness of re-processing.</span></span>  <span data-ttu-id="8b394-114">En la vista de indización de personas de interés, el gráfico muestra todos los elementos agregados al *Índice híbrido*.</span><span class="sxs-lookup"><span data-stu-id="8b394-114">In the People of interest indexing view, the graph lists all items added to the *hybrid index*.</span></span>  <span data-ttu-id="8b394-115">El índice híbrido es donde las investigaciones de datos (vista previa) almacenan el contenido reprocesado.</span><span class="sxs-lookup"><span data-stu-id="8b394-115">The hybrid index is where Data Investigations (Preview) stores the re-processed content.</span></span>

<span data-ttu-id="8b394-116">El gráfico también incluye el número de elementos que requieren corrección y otro gráfico de errores por tipo de archivo.</span><span class="sxs-lookup"><span data-stu-id="8b394-116">The graph also includes the number of items that require remediation and another graph of errors by file type.</span></span> <span data-ttu-id="8b394-117">Para obtener más información, vea [corrección de errores al procesar datos](error-remediation.md).</span><span class="sxs-lookup"><span data-stu-id="8b394-117">For more information, see [Error remediation when processing data](error-remediation.md).</span></span>

## <a name="updating-advanced-indexes-for-people-of-interest"></a><span data-ttu-id="8b394-118">Actualización de índices avanzados para personas de interés</span><span class="sxs-lookup"><span data-stu-id="8b394-118">Updating Advanced indexes for people of interest</span></span>

<span data-ttu-id="8b394-119">Cuando se agrega una persona de interés a una investigación de datos, todos los elementos parcialmente indizados se vuelven a procesar.</span><span class="sxs-lookup"><span data-stu-id="8b394-119">When a person of interest is added to a data investigation, all partially indexed items are re-processed.</span></span> <span data-ttu-id="8b394-120">Sin embargo, a medida que pasa el tiempo, se pueden agregar más elementos indizados parcialmente al buzón de un usuario o a una cuenta de OneDrive.</span><span class="sxs-lookup"><span data-stu-id="8b394-120">However, as time passes, more partially indexed items may be added to a user's mailbox or OneDrive account.</span></span>  <span data-ttu-id="8b394-121">Cuando sea necesario, puede actualizar los índices.</span><span class="sxs-lookup"><span data-stu-id="8b394-121">When needed, you can update the indexes.</span></span>

> [!NOTE]
> <span data-ttu-id="8b394-122">La actualización de personas de índices de interés es un proceso de ejecución prolongada.</span><span class="sxs-lookup"><span data-stu-id="8b394-122">Updating people of interest indexes is a long running process.</span></span> <span data-ttu-id="8b394-123">Se recomienda no actualizar índices más de una vez al día en una investigación.</span><span class="sxs-lookup"><span data-stu-id="8b394-123">It's recommended that you don't update indexes more than once per day in an investigation.</span></span>
