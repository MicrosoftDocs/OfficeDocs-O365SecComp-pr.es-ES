---
title: Exportar documentos desde un conjunto de revisión
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
ms.openlocfilehash: 7c1daccab799b3967c6b8c1d577060d062c05a70
ms.sourcegitcommit: e323610df2df71c84f536e8a38650d33d8069e41
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2019
ms.locfileid: "34703793"
---
# <a name="export-documents-from-a-review-set"></a><span data-ttu-id="44b40-102">Exportar documentos desde un conjunto de revisión</span><span class="sxs-lookup"><span data-stu-id="44b40-102">Export documents from a review set</span></span>

<span data-ttu-id="44b40-103">Puede exportar el contenido para la presentación o la revisión externa a partir de un conjunto de revisión por uno de los siguientes métodos:</span><span class="sxs-lookup"><span data-stu-id="44b40-103">You can export content for presentation or external review from a review set by one of the following methods:</span></span>

- [<span data-ttu-id="44b40-104">Descargar documentos</span><span class="sxs-lookup"><span data-stu-id="44b40-104">Download documents</span></span>](#download-documents-from-a-review-set)
 
- [<span data-ttu-id="44b40-105">Exportar documentos</span><span class="sxs-lookup"><span data-stu-id="44b40-105">Export documents</span></span>](#export-documents-from-a-review-set)

## <a name="download-documents-from-a-review-set"></a><span data-ttu-id="44b40-106">Descargar documentos de un conjunto de revisión</span><span class="sxs-lookup"><span data-stu-id="44b40-106">Download documents from a review set</span></span>

<span data-ttu-id="44b40-107">La descarga ofrece una forma sencilla de descargar contenido de un conjunto de revisión en formato nativo.</span><span class="sxs-lookup"><span data-stu-id="44b40-107">Download offers a simple way to download content from a review set in Native format.</span></span> <span data-ttu-id="44b40-108">Aprovecha las características de transferencia de datos del explorador para que aparezca un mensaje del explorador una vez que la descarga esté lista.</span><span class="sxs-lookup"><span data-stu-id="44b40-108">It leverages the browser’s data transfer features so a browser prompt will appear once a download is ready.</span></span> <span data-ttu-id="44b40-109">Los archivos descargados con este método se comprimen en un archivo contenedor y serán archivos de nivel de elemento.</span><span class="sxs-lookup"><span data-stu-id="44b40-109">Files downloaded using this method will be zipped into a container file and will be item level files.</span></span> <span data-ttu-id="44b40-110">Esto significa que, si selecciona un archivo adjunto, recibirá automáticamente el correo electrónico con los datos adjuntos incluidos.</span><span class="sxs-lookup"><span data-stu-id="44b40-110">This means that if you select an attachment, you will automatically receive the email with the attachment included.</span></span> <span data-ttu-id="44b40-111">De forma similar, si selecciona una hoja de cálculo de Excel que estaba incrustada en un documento de Word, recibirá el documento de Word con la hoja de cálculo de Excel incrustada.</span><span class="sxs-lookup"><span data-stu-id="44b40-111">Similarly, if you select an excel spreadsheet that was embedded in a word document, you will receive the word document with the excel spreadsheet embedded.</span></span> <span data-ttu-id="44b40-112">Los elementos descargados conservarán la fecha de la última modificación, que se puede ver como una propiedad de archivo.</span><span class="sxs-lookup"><span data-stu-id="44b40-112">Downloaded items will preserve the last modified date which can be viewed as a file property.</span></span>

<span data-ttu-id="44b40-113">Para descargar contenido de un conjunto de revisión, seleccione los archivos que desea descargar y, a continuación, seleccione "Descargar" en el menú acciones.</span><span class="sxs-lookup"><span data-stu-id="44b40-113">To download content from a review set, start by selecting the files you want to download then select “Download” under the Actions menu.</span></span>

![Una captura de pantalla de una descripción de equipo generada automáticamente](../media/eDiscoDownload.png)

## <a name="export-documents-from-a-review-set"></a><span data-ttu-id="44b40-115">Exportar documentos desde un conjunto de revisión</span><span class="sxs-lookup"><span data-stu-id="44b40-115">Export documents from a review set</span></span>

<span data-ttu-id="44b40-116">La exportación permite a los usuarios personalizar el contenido que se incluye en el paquete de descarga.</span><span class="sxs-lookup"><span data-stu-id="44b40-116">Export allows users to customize the content that is included in the download package.</span></span> <span data-ttu-id="44b40-117">Proporciona una página de configuración con la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="44b40-117">It provides a configuration page with the following settings:</span></span>

### <a name="metadata-file"></a><span data-ttu-id="44b40-118">Archivo de metadatos</span><span class="sxs-lookup"><span data-stu-id="44b40-118">Metadata file</span></span>

<span data-ttu-id="44b40-119">Esto puede considerarse el "Cargar archivo" que contiene metadatos asociados con los archivos exportados.</span><span class="sxs-lookup"><span data-stu-id="44b40-119">This can be considered your “load file” that contains metadata associated with the files you exported.</span></span> <span data-ttu-id="44b40-120">Para obtener una lista de los campos disponibles en el archivo de \[metadatos, vea Link\].</span><span class="sxs-lookup"><span data-stu-id="44b40-120">For a list of fields available in the metadata file, see \[link\].</span></span> <span data-ttu-id="44b40-121">Por lo general, este archivo puede ser incorporado por las herramientas de terceros de terceras partes.<sup></sup></span><span class="sxs-lookup"><span data-stu-id="44b40-121">This file can typically be ingested by 3<sup>rd</sup> party tools downstream.</span></span>

### <a name="tag-data"></a><span data-ttu-id="44b40-122">Datos de etiqueta</span><span class="sxs-lookup"><span data-stu-id="44b40-122">Tag data</span></span>

<span data-ttu-id="44b40-123">Este contenido se agregaría como campos en el archivo de metadatos.</span><span class="sxs-lookup"><span data-stu-id="44b40-123">This content would be added as fields in the metadata file.</span></span> <span data-ttu-id="44b40-124">Contiene toda la información de etiqueta aplicada en los conjuntos de revisión.</span><span class="sxs-lookup"><span data-stu-id="44b40-124">It contains all of the tag information applied in review sets.</span></span>

### <a name="text-files"></a><span data-ttu-id="44b40-125">Archivos de texto</span><span class="sxs-lookup"><span data-stu-id="44b40-125">Text files</span></span>

<span data-ttu-id="44b40-126">Los archivos de texto se pueden generar para cada archivo exportado de un conjunto de revisión.</span><span class="sxs-lookup"><span data-stu-id="44b40-126">Text files can be generated for each file exported from a review set.</span></span> <span data-ttu-id="44b40-127">A menudo, los asociados de servicio necesitan estos archivos como parte de la recopilación de datos<sup></sup> en herramientas de terceros de terceros.</span><span class="sxs-lookup"><span data-stu-id="44b40-127">Often times these files are required by service partners as part of ingesting data into 3<sup>rd</sup> party tools downstream.</span></span>

### <a name="redacted-files"></a><span data-ttu-id="44b40-128">Archivos censurados</span><span class="sxs-lookup"><span data-stu-id="44b40-128">Redacted files</span></span>

<span data-ttu-id="44b40-129">Si se generan documentos PDF censurados durante la revisión, estos archivos están disponibles durante la exportación.</span><span class="sxs-lookup"><span data-stu-id="44b40-129">If redacted PDFs are generated during review, these files are available during export.</span></span> <span data-ttu-id="44b40-130">Los usuarios pueden decidir si desea exportar solo los archivos nativos o reemplazar los nativos que tienen redacciones con el grabado en documentos PDF.</span><span class="sxs-lookup"><span data-stu-id="44b40-130">Users can decide whether to export native files only or to replace natives that have redactions with the burned in PDFs.</span></span>

### <a name="export-location"></a><span data-ttu-id="44b40-131">Ubicación de exportación</span><span class="sxs-lookup"><span data-stu-id="44b40-131">Export Location</span></span>

<span data-ttu-id="44b40-132">El contenido exportado se entrega en un BLOB de Azure o el BLOB de un cliente de Microsoft se puede usar si los detalles se proporcionan en la exportación.</span><span class="sxs-lookup"><span data-stu-id="44b40-132">Exported content is delivered to either a Microsoft provided Azure blob or a customer’s blob can be used if the details are provided at export.</span></span>

### <a name="export-structure"></a><span data-ttu-id="44b40-133">Exportar estructura</span><span class="sxs-lookup"><span data-stu-id="44b40-133">Export Structure</span></span>

<span data-ttu-id="44b40-134">Cuando se exporta contenido desde un conjunto de revisión, el contenido se organiza en la estructura siguiente.</span><span class="sxs-lookup"><span data-stu-id="44b40-134">When content is exported from a review set, the content is organized in the following structure.</span></span>

  - <span data-ttu-id="44b40-135">Carpeta raíz: identificador de descarga</span><span class="sxs-lookup"><span data-stu-id="44b40-135">Root folder – Download ID</span></span>
    
      - <span data-ttu-id="44b40-136">Exportar\_archivo\_de carga. csv = archivo de metadatos</span><span class="sxs-lookup"><span data-stu-id="44b40-136">Export\_load\_file.csv = metadata file</span></span>
    
      - <span data-ttu-id="44b40-137">Summary. txt = un archivo de resumen con las estadísticas de exportación</span><span class="sxs-lookup"><span data-stu-id="44b40-137">Summary.txt = a summary file with export statistics</span></span>
    
      - <span data-ttu-id="44b40-138">Archivos\_nativos\_o de entrada = contiene todos los archivos nativos</span><span class="sxs-lookup"><span data-stu-id="44b40-138">Input\_or native\_files = contains all native files</span></span>
    
      - <span data-ttu-id="44b40-139">Archivos\_de errores = contiene los archivos de error incluidos en la exportación</span><span class="sxs-lookup"><span data-stu-id="44b40-139">Error\_files = contains any error files included in the export</span></span>
        
          - <span data-ttu-id="44b40-140">ExtractionError: un CSV que contiene los metadatos disponibles de los archivos que no se han extraído correctamente de los archivos principales</span><span class="sxs-lookup"><span data-stu-id="44b40-140">ExtractionError – a csv that contains any available metadata of files that were not properly extracted from parent files</span></span>
        
          - <span data-ttu-id="44b40-141">ProcessingError: contenido con errores de procesamiento.</span><span class="sxs-lookup"><span data-stu-id="44b40-141">ProcessingError – content with processing errors.</span></span> <span data-ttu-id="44b40-142">Este contenido es el significado del nivel de elemento si los datos adjuntos experimentan un error de procesamiento, el correo electrónico que contiene los datos adjuntos se incluirá en esta carpeta.</span><span class="sxs-lookup"><span data-stu-id="44b40-142">This content is item level meaning if an attachment experienced a processing error, the email that contains the attachment will be included in this folder.</span></span>
    
      - <span data-ttu-id="44b40-143">Archivos\_de\_texto extraídos = contiene todos los archivos de texto extraídos generados en el procesamiento.</span><span class="sxs-lookup"><span data-stu-id="44b40-143">Extracted\_text\_files = contains all of the extracted text files generated at processing.</span></span>