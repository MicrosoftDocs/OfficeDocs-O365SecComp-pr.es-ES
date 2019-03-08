---
title: Exportar documentos desde un conjunto de trabajo
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
ms.openlocfilehash: 815b92b13ed09d8aec64f5207f1c82d910e2dce0
ms.sourcegitcommit: 9f38ba72eba0b656e507860ca228726e4199f7ec
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/07/2019
ms.locfileid: "30475710"
---
# <a name="export-documents-from-a-working-set"></a><span data-ttu-id="78d54-102">Exportar documentos desde un conjunto de trabajo</span><span class="sxs-lookup"><span data-stu-id="78d54-102">Export documents from a working set</span></span>

<span data-ttu-id="78d54-103">La exportación de contenido de un conjunto de trabajo puede realizarse a través de tres métodos diferentes:</span><span class="sxs-lookup"><span data-stu-id="78d54-103">Exporting content from a working set can be accomplished via 3 different methods:</span></span>

## <a name="download"></a><span data-ttu-id="78d54-104">Descargar</span><span class="sxs-lookup"><span data-stu-id="78d54-104">Download</span></span>

<span data-ttu-id="78d54-105">La descarga ofrece una forma sencilla de descargar contenido de un conjunto de trabajo en formato nativo.</span><span class="sxs-lookup"><span data-stu-id="78d54-105">Download offers a simple way to download content from a working set in Native format.</span></span> <span data-ttu-id="78d54-106">Aprovecha las características de transferencia de datos del explorador para que aparezca un mensaje del explorador una vez que la descarga esté lista.</span><span class="sxs-lookup"><span data-stu-id="78d54-106">It leverages the browser’s data transfer features so a browser prompt will appear once a download is ready.</span></span> <span data-ttu-id="78d54-107">Los archivos descargados con este método se comprimen en un archivo contenedor y serán archivos de nivel de elemento.</span><span class="sxs-lookup"><span data-stu-id="78d54-107">Files downloaded using this method will be zipped into a container file and will be item level files.</span></span> <span data-ttu-id="78d54-108">Esto significa que, si selecciona un archivo adjunto, recibirá automáticamente el correo electrónico con los datos adjuntos incluidos.</span><span class="sxs-lookup"><span data-stu-id="78d54-108">This means that if you select an attachment, you will automatically receive the email with the attachment included.</span></span> <span data-ttu-id="78d54-109">De forma similar, si selecciona una hoja de cálculo de Excel que estaba incrustada en un documento de Word, recibirá el documento de Word con la hoja de cálculo de Excel incrustada.</span><span class="sxs-lookup"><span data-stu-id="78d54-109">Similarly, if you select an excel spreadsheet that was embedded in a word document, you will receive the word document with the excel spreadsheet embedded.</span></span> <span data-ttu-id="78d54-110">Los elementos desCargados conservarán la fecha de la última modificación, que se puede ver como una propiedad de archivo.</span><span class="sxs-lookup"><span data-stu-id="78d54-110">Downloaded items will preserve the last modified date which can be viewed as a file property.</span></span>

<span data-ttu-id="78d54-111">Para descargar contenido de un conjunto de trabajo, seleccione los archivos que desea descargar y, a continuación, seleccione "Descargar" en el menú acciones.</span><span class="sxs-lookup"><span data-stu-id="78d54-111">To download content from a working set, start by selecting the files you want to download then select “Download” under the Actions menu.</span></span>

![Una captura de pantalla de una descripción de equipo generada automáticamente](../media/eDiscoDownload.png)

## <a name="export"></a><span data-ttu-id="78d54-113">Exportar</span><span class="sxs-lookup"><span data-stu-id="78d54-113">Export</span></span>

<span data-ttu-id="78d54-114">La exportación permite a los usuarios personalizar el contenido que se incluye en el paquete de descarga.</span><span class="sxs-lookup"><span data-stu-id="78d54-114">Export allows users to customize the content that is included in the download package.</span></span> <span data-ttu-id="78d54-115">Proporciona una página de configuración con la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="78d54-115">It provides a configuration page with the following settings:</span></span>

### <a name="metadata-file"></a><span data-ttu-id="78d54-116">Archivo de metaDatos</span><span class="sxs-lookup"><span data-stu-id="78d54-116">Metadata file</span></span>

> <span data-ttu-id="78d54-117">Esto puede considerarse el "Cargar archivo" que contiene metadatos asociados con los archivos exportados.</span><span class="sxs-lookup"><span data-stu-id="78d54-117">This can be considered your “load file” that contains metadata associated with the files you exported.</span></span> <span data-ttu-id="78d54-118">Para obtener una lista de los campos disponibles en el archivo de \[metadatos, vea Link\].</span><span class="sxs-lookup"><span data-stu-id="78d54-118">For a list of fields available in the metadata file, see \[link\].</span></span> <span data-ttu-id="78d54-119">Por lo general, este archivo puede ser incorporado por las herramientas de terceros de terceras partes.<sup></sup></span><span class="sxs-lookup"><span data-stu-id="78d54-119">This file can typically be ingested by 3<sup>rd</sup> party tools downstream.</span></span>

### <a name="tag-data"></a><span data-ttu-id="78d54-120">Datos de etiqueta</span><span class="sxs-lookup"><span data-stu-id="78d54-120">Tag data</span></span>

> <span data-ttu-id="78d54-121">Este contenido se agregaría como campos en el archivo de metadatos.</span><span class="sxs-lookup"><span data-stu-id="78d54-121">This content would be added as fields in the metadata file.</span></span> <span data-ttu-id="78d54-122">Contiene toda la información de etiqueta aplicada en los conjuntos de trabajo.</span><span class="sxs-lookup"><span data-stu-id="78d54-122">It contains all of the tag information applied in working sets.</span></span>

### <a name="text-files"></a><span data-ttu-id="78d54-123">Archivos de texto</span><span class="sxs-lookup"><span data-stu-id="78d54-123">Text files</span></span>

> <span data-ttu-id="78d54-124">Los archivos de texto se pueden generar para cada archivo exportado de un conjunto de trabajo.</span><span class="sxs-lookup"><span data-stu-id="78d54-124">Text files can be generated for each file exported from a working set.</span></span> <span data-ttu-id="78d54-125">A menudo, los asociados de servicio necesitan estos archivos como parte de la recopilación de datos<sup></sup> en herramientas de terceros de terceros.</span><span class="sxs-lookup"><span data-stu-id="78d54-125">Often times these files are required by service partners as part of ingesting data into 3<sup>rd</sup> party tools downstream.</span></span>

### <a name="redacted-files"></a><span data-ttu-id="78d54-126">Archivos censurados</span><span class="sxs-lookup"><span data-stu-id="78d54-126">Redacted files</span></span>

> <span data-ttu-id="78d54-127">Si se generan documentos PDF censurados durante la revisión, estos archivos están disponibles durante la exportación.</span><span class="sxs-lookup"><span data-stu-id="78d54-127">If redacted PDFs are generated during review, these files are available during export.</span></span> <span data-ttu-id="78d54-128">Los usuarios pueden decidir si desea exportar solo los archivos nativos o reemplazar los nativos que tienen redacciones con el grabado en documentos PDF.</span><span class="sxs-lookup"><span data-stu-id="78d54-128">Users can decide whether to export native files only or to replace natives that have redactions with the burned in PDFs.</span></span>

### <a name="export-location"></a><span data-ttu-id="78d54-129">Ubicación de exportación</span><span class="sxs-lookup"><span data-stu-id="78d54-129">Export Location</span></span>

> <span data-ttu-id="78d54-130">El contenido exPortado se entrega en un BLOB de Azure o el BLOB de un cliente de Microsoft se puede usar si los detalles se proporcionan en la exportación.</span><span class="sxs-lookup"><span data-stu-id="78d54-130">Exported content is delivered to either a Microsoft provided Azure blob or a customer’s blob can be used if the details are provided at export.</span></span>

## <a name="export-structure"></a><span data-ttu-id="78d54-131">Exportar estructura</span><span class="sxs-lookup"><span data-stu-id="78d54-131">Export Structure</span></span>

<span data-ttu-id="78d54-132">Cuando se exporta contenido desde un conjunto de trabajo, el contenido se organiza en la siguiente estructura.</span><span class="sxs-lookup"><span data-stu-id="78d54-132">When content is exported from a working set, the content is organized in the following structure.</span></span>

  - <span data-ttu-id="78d54-133">Carpeta raíz: identificador de descarga</span><span class="sxs-lookup"><span data-stu-id="78d54-133">Root folder – Download ID</span></span>
    
      - <span data-ttu-id="78d54-134">Exportar\_archivo\_de carga. csv = archivo de metadatos</span><span class="sxs-lookup"><span data-stu-id="78d54-134">Export\_load\_file.csv = metadata file</span></span>
    
      - <span data-ttu-id="78d54-135">Summary. txt = un archivo de resumen con las estadísticas de exportación</span><span class="sxs-lookup"><span data-stu-id="78d54-135">Summary.txt = a summary file with export statistics</span></span>
    
      - <span data-ttu-id="78d54-136">Archivos\_nativos\_o de entrada = contiene todos los archivos nativos</span><span class="sxs-lookup"><span data-stu-id="78d54-136">Input\_or native\_files = contains all native files</span></span>
    
      - <span data-ttu-id="78d54-137">Archivos\_de errores = contiene los archivos de error incluidos en la exportación</span><span class="sxs-lookup"><span data-stu-id="78d54-137">Error\_files = contains any error files included in the export</span></span>
        
          - <span data-ttu-id="78d54-138">ExtractionError: un CSV que contiene los metadatos disponibles de los archivos que no se han extraído correctamente de los archivos principales</span><span class="sxs-lookup"><span data-stu-id="78d54-138">ExtractionError – a csv that contains any available metadata of files that were not properly extracted from parent files</span></span>
        
          - <span data-ttu-id="78d54-139">ProcessingError: contenido con errores de procesamiento.</span><span class="sxs-lookup"><span data-stu-id="78d54-139">ProcessingError – content with processing errors.</span></span> <span data-ttu-id="78d54-140">Este contenido es el significado del nivel de elemento si los datos adjuntos experimentan un error de procesamiento, el correo electrónico que contiene los datos adjuntos se incluirá en esta carpeta.</span><span class="sxs-lookup"><span data-stu-id="78d54-140">This content is item level meaning if an attachment experienced a processing error, the email that contains the attachment will be included in this folder.</span></span>
    
      - <span data-ttu-id="78d54-141">Archivos\_de\_texto extraídos = contiene todos los archivos de texto extraídos generados en el procesamiento.</span><span class="sxs-lookup"><span data-stu-id="78d54-141">Extracted\_text\_files = contains all of the extracted text files generated at processing.</span></span>

## <a name="working-set"></a><span data-ttu-id="78d54-142">Espacio de trabajo</span><span class="sxs-lookup"><span data-stu-id="78d54-142">Working Set</span></span>

<span data-ttu-id="78d54-143">El contenido se puede Agregar a otro conjunto de trabajo.</span><span class="sxs-lookup"><span data-stu-id="78d54-143">Content can be added to another working set.</span></span>