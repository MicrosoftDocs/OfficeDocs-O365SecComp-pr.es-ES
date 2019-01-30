---
title: Clasificación de datos de custodia avanzada
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: ''
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: 158af8acf4acdb8ad6650c377a23b44ed28c6f54
ms.sourcegitcommit: ee28ee2b2bdfd049333c2f495d7f7780d13af4a6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2019
ms.locfileid: "29608332"
---
# <a name="advanced-indexing-of-custodian-data"></a><span data-ttu-id="c99a7-102">Clasificación de datos de custodia avanzada</span><span class="sxs-lookup"><span data-stu-id="c99a7-102">Advanced indexing of custodian data</span></span>

<span data-ttu-id="c99a7-p101">Cuando se agrega una custodia a un caso de exhibición de documentos electrónicos avanzada (vista previa), cualquier contenido en Office 365 que se consideró como parcialmente indizados se vuelve a procesar para hacer que permite realizar búsquedas.  Este proceso se denomina *indización avanzada*. Contenido se puede indizar parcialmente para una serie de razones, incluida la existencia de imágenes, tipos de archivo no compatibles o cuando se encuentran la indización de los límites de tamaño de archivo.  Para obtener más información acerca de los elementos indizados parcialmente, vea [parcialmente indizar los elementos de búsqueda de contenido en Office 365](https://docs.microsoft.com/en-us/office365/securitycompliance/partially-indexed-items-in-content-search).</span><span class="sxs-lookup"><span data-stu-id="c99a7-p101">When a custodian is added to an Advanced eDiscovery (Preview) case, any content in Office 365 that was deemed as partially indexed is re-processed to make it fully searchable.  This process is called *Advanced indexing*. Content can be partially indexed for a number of reasons including the existence of images, unsupported file types or when indexing file size limits are encountered.  To learn more about partially indexed items, see [Partially indexed items in Content Search in Office 365](https://docs.microsoft.com/en-us/office365/securitycompliance/partially-indexed-items-in-content-search).</span></span>

## <a name="viewing-advanced-indexing-results"></a><span data-ttu-id="c99a7-107">Ver los resultados de indización avanzados</span><span class="sxs-lookup"><span data-stu-id="c99a7-107">Viewing Advanced indexing results</span></span>

<span data-ttu-id="c99a7-p102">Después de que se complete el proceso de indización avanzado, puede obtener una descripción de la eficacia de volver a procesar.  En la vista de indización de custodia, el gráfico enumera todos los elementos que se agregan al *índice híbrida*.  El índice de híbrido es donde exhibición de documentos electrónicos avanzada (vista previa) almacena el contenido vuelve a procesar.</span><span class="sxs-lookup"><span data-stu-id="c99a7-p102">After the Advanced indexing process is completed, you can get an understanding of the effectiveness of re-processing.  In the Custodian Indexing view, the graph lists all items added to the *hybrid index*.  The hybrid index is where Advanced eDiscovery (Preview) stores the re-processed content.</span></span>

<span data-ttu-id="c99a7-p103">El gráfico también incluye el número de elementos que requieren corrección y otro gráfico de errores por tipo de archivo. Para obtener más información, vea [corrección de Error al procesar los datos](error-remediation.md).</span><span class="sxs-lookup"><span data-stu-id="c99a7-p103">The graph also includes the number of items that require remediation and another graph of errors by file type. For more information, see [Error remediation when processing data](error-remediation.md).</span></span>

## <a name="updating-advanced-indexes-for-custodians"></a><span data-ttu-id="c99a7-113">Actualización de índices avanzada de custodia</span><span class="sxs-lookup"><span data-stu-id="c99a7-113">Updating Advanced indexes for custodians</span></span>

<span data-ttu-id="c99a7-p104">Cuando se agrega una custodia a un caso de exhibición de documentos electrónicos avanzada (vista previa), se vuelve a procesar todos los elementos indizados parcialmente. Sin embargo, como el paso del tiempo, los elementos indizados más parcialmente pueden agregarse a un cuenta del usuario buzón de correo o OneDrive.  Cuando es necesario, puede actualizar los índices.</span><span class="sxs-lookup"><span data-stu-id="c99a7-p104">When a custodian is added to an Advanced eDiscovery (Preview) case, all partially indexed items are re-processed. However, as time passes, more partially indexed items may be added to a user's mailbox or OneDrive account.  When needed, you can update the indexes.</span></span>

> [!NOTE]
> <span data-ttu-id="c99a7-p105">Actualización de índices de custodia es un proceso de larga ejecución. Se recomienda que no se actualizan los índices más de una vez al día en un caso.</span><span class="sxs-lookup"><span data-stu-id="c99a7-p105">Updating custodian indexes is a long running process. It's recommended that you don't update indexes more than once per day in a case.</span></span>
