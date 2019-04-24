---
title: Revisar los datos de pruebas
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
ms.openlocfilehash: e84f05fa1a7356952b62f2f4adc3b7d0f1ddc94e
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32258048"
---
# <a name="review-the-data-in-evidence"></a><span data-ttu-id="4b684-102">Revisar los datos de pruebas</span><span class="sxs-lookup"><span data-stu-id="4b684-102">Review the data in evidence</span></span>

<span data-ttu-id="4b684-103">Los datos de un conjunto de evidencias en una investigación de datos son una instantánea de los resultados de búsqueda que se recopilaron y se agregaron al conjunto de evidencias.</span><span class="sxs-lookup"><span data-stu-id="4b684-103">The data in an evidence set in a data investigation is a snapshot of the search results that you collected and added to the evidence set.</span></span> <span data-ttu-id="4b684-104">Cuando se agregan resultados de búsqueda a la evidencia, se desencadena un proceso para extraer los archivos, los metadatos y el texto de los elementos devueltos por la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="4b684-104">When you add search results to evidence, a process is triggered to extract files, metadata, and text from the items returned by the search.</span></span> <span data-ttu-id="4b684-105">A continuación, la herramienta de investigación de datos (vista previa) crea un nuevo índice (por un proceso denominado " *indizaCión avanzada*") de todos los datos y agrega a un conjunto de evidencias en la pestaña **evidencia** .</span><span class="sxs-lookup"><span data-stu-id="4b684-105">Then the Data Investigations (Preview) tool then builds a new index (by a process called *Advanced indexing*) of all the data and adds to an evidence set on the **Evidence** tab.</span></span> 

<span data-ttu-id="4b684-106">Para las investigaciones sensibles al tiempo, esto permite incluir rápidamente el entorno al eliminar los datos reales derramados o malintencionados que se encuentran en el origen de datos original, a la vez que permite investigar la evidencia que se ha vuelto a crear en un entorno en cuarentena, que en este caso son los datos copiados al conjunto de evidencias.</span><span class="sxs-lookup"><span data-stu-id="4b684-106">For time-sensitive investigations, this allows you to quickly contain the environment by deleting the actual spilled or malicious data located in the at original data source, while at the same time allowing you to investigate the re-created evidence in a quarantined environment, which in this case is the data copied to the evidence set).</span></span> <span data-ttu-id="4b684-107">Una vez recopilada y agregada la evidencia al conjunto de evidencias, puede revisar documentos individuales en su formato nativo, formato de texto o un formato casi nativo que puede usar para anotar y censurar documentos.</span><span class="sxs-lookup"><span data-stu-id="4b684-107">After the evidence is collected and added to the evidence set, you can review individual documents in their native format, text format, or a near-native format that you can use to annotate and redact documents.</span></span> <span data-ttu-id="4b684-108">Además, puede ejecutar consultas para restringir el conjunto de datos por intervalo de tiempo, tipos de archivo, propietarios de datos y muchas otras propiedades y condiciones de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="4b684-108">Additionally, you can run queries to narrow the data set by time range, file types, data owners, and many other properties and search conditions.</span></span> <span data-ttu-id="4b684-109">Por ejemplo, mediante el uso de las condiciones de autor, remitente o destinatario, puede identificar rápidamente a las personas involucradas en el incidente y si los datos de la organización se han compartido con usuarios externos.</span><span class="sxs-lookup"><span data-stu-id="4b684-109">For example, by using the Author, Sender, or Recipient conditions, you can quickly identify the people are involved in the incident and if any data from your organization has been shared with external users.</span></span> <span data-ttu-id="4b684-110">Para obtener más información acerca de la búsqueda en datos en un conjunto de evidencias, vea [consultar los datos en evidencias](evidence-query.md).</span><span class="sxs-lookup"><span data-stu-id="4b684-110">For more information about searching through data in an evidence set, see [Query the data in evidence](evidence-query.md).</span></span>

<span data-ttu-id="4b684-111">Para agrupar documentos y obtener más ayuda para su revisión, seleccione un conjunto de evidencias en la pestaña **evidencia** y, a continuación, haga clic en **administrar evidencias**.</span><span class="sxs-lookup"><span data-stu-id="4b684-111">To group documents and get more assistance for your review, select an evidence set on the **Evidence** tab, and then click **Manage evidence**.</span></span> <span data-ttu-id="4b684-112">En el mosaico **Analytics** , haga clic en recompilar **análisis para todo el conjunto**.</span><span class="sxs-lookup"><span data-stu-id="4b684-112">In the **Analytics** tile, click **Rebuild analytics for the whole set**.</span></span> <span data-ttu-id="4b684-113">De esta forma, se ejecutarán análisis avanzados, como la detección de duplicados, el procesamiento de correo electrónico y el análisis de temas.</span><span class="sxs-lookup"><span data-stu-id="4b684-113">This will run advanced analytics such as duplicate detection, email threading, and theme analysis.</span></span> <span data-ttu-id="4b684-114">Posteriormente, puede ver los temas generales de los datos y también organizar los documentos por correo electrónico, casi duplicados y duplicados exactos para ayudarle en su investigación.</span><span class="sxs-lookup"><span data-stu-id="4b684-114">Afterwards, you can see the general themes of the data and also organize documents by email threads, near duplicates, and exact duplicates to help your investigation.</span></span> <span data-ttu-id="4b684-115">Para obtener más información, vea [ejecutar análisis para investigar con mayor rapidez](run-analytics-to-investigate-faster.md).</span><span class="sxs-lookup"><span data-stu-id="4b684-115">For more information, see [Run analytics to investigate faster](run-analytics-to-investigate-faster.md).</span></span>

## <a name="view-documents-in-evidence"></a><span data-ttu-id="4b684-116">Ver documentos en prueba</span><span class="sxs-lookup"><span data-stu-id="4b684-116">View documents in evidence</span></span>

<span data-ttu-id="4b684-117">Las investigaciones de datos (versión preliminar) le permiten mostrar contenido en varios visores distintos, con un propósito diferente para cada visor.</span><span class="sxs-lookup"><span data-stu-id="4b684-117">Data Investigations (Preview) allows you to display content in several different viewers, with each viewer having a different purpose.</span></span> <span data-ttu-id="4b684-118">Estos visores son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="4b684-118">These viewers are:</span></span>

- <span data-ttu-id="4b684-119">Metadatos de archivo</span><span class="sxs-lookup"><span data-stu-id="4b684-119">File metadata</span></span>
- <span data-ttu-id="4b684-120">Vista nativa</span><span class="sxs-lookup"><span data-stu-id="4b684-120">Native view</span></span>
- <span data-ttu-id="4b684-121">Vista de texto</span><span class="sxs-lookup"><span data-stu-id="4b684-121">Text view</span></span>
- <span data-ttu-id="4b684-122">Vista de anotar</span><span class="sxs-lookup"><span data-stu-id="4b684-122">Annotate view</span></span>

<span data-ttu-id="4b684-123">Para tener acceso a cualquiera de estos visores, seleccione un documento en un conjunto de evidencias.</span><span class="sxs-lookup"><span data-stu-id="4b684-123">To access any of these viewers, just select a document in an evidence set.</span></span>

## <a name="file-metadata"></a><span data-ttu-id="4b684-124">Metadatos de archivo</span><span class="sxs-lookup"><span data-stu-id="4b684-124">File metadata</span></span>

<span data-ttu-id="4b684-125">Esta vista muestra varias propiedades de metadatos asociadas con el documento seleccionado.</span><span class="sxs-lookup"><span data-stu-id="4b684-125">This view displays various metadata properties associated with the selected document.</span></span> <span data-ttu-id="4b684-126">Puede activar y desactivar esta vista haciendo clic en metadatos del **archivo**.</span><span class="sxs-lookup"><span data-stu-id="4b684-126">You can toggle this view on and off by clicking **File metadata**.</span></span> <span data-ttu-id="4b684-127">Al revisar un documento, puede ver los metadatos del archivo y seguir cambiando entre los distintos visores.</span><span class="sxs-lookup"><span data-stu-id="4b684-127">When reviewing a document, you can view the file metadata and still change between the different viewers.</span></span>

<span data-ttu-id="4b684-128">A continuación, se muestra un ejemplo de los metadatos de archivo para un documento.</span><span class="sxs-lookup"><span data-stu-id="4b684-128">Here's an example of the file metadata for a document.</span></span> <span data-ttu-id="4b684-129">Para obtener más información acerca de los campos de metadatos, vea [Document Metadata Fields in Data investigaciones (Preview)](document-metadata-fields.md).</span><span class="sxs-lookup"><span data-stu-id="4b684-129">For more information about the metadata fields, see [Document metadata fields in Data Investigations (Preview)](document-metadata-fields.md).</span></span>

![Panel metadatos de archivo](../media/Reviewimage2.png)

## <a name="native-view"></a><span data-ttu-id="4b684-131">Vista nativa</span><span class="sxs-lookup"><span data-stu-id="4b684-131">Native view</span></span>

<span data-ttu-id="4b684-132">El visor nativo muestra la vista más exacta de un documento en su formato nativo.</span><span class="sxs-lookup"><span data-stu-id="4b684-132">The Native viewer displays the most accurate view of a document in it's native format.</span></span> <span data-ttu-id="4b684-133">La vista nativa es compatible con cientos de tipos de archivo y está destinada a mostrar documentos en la experiencia nativa más real posible.</span><span class="sxs-lookup"><span data-stu-id="4b684-133">Native view is supported for hundreds of file types and is meant to display documents in the truest native experience possible.</span></span> <span data-ttu-id="4b684-134">Para los archivos de Microsoft Office, el visor nativo usa Office online.</span><span class="sxs-lookup"><span data-stu-id="4b684-134">For Microsoft Office files, the Native viewer uses Office Online.</span></span> <span data-ttu-id="4b684-135">Esto le permite ver contenido como comentarios en diferentes documentos de Office, fórmulas y filas o columnas ocultas en Excel y la vista de notas en PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="4b684-135">This allows you to view content such as comments in different Office documents, formulas and hidden rows/columns in Excel, and the Notes view in PowerPoint.</span></span>

![<span data-ttu-id="4b684-136">Vista nativa</span><span class="sxs-lookup"><span data-stu-id="4b684-136">Native view</span></span>
](../media/Reviewimage3.png)

## <a name="text-view"></a><span data-ttu-id="4b684-137">Vista de texto</span><span class="sxs-lookup"><span data-stu-id="4b684-137">Text view</span></span>

<span data-ttu-id="4b684-138">El visor de texto proporciona una vista del texto extraído de un archivo.</span><span class="sxs-lookup"><span data-stu-id="4b684-138">The Text viewer provides a view of the extracted text of a file.</span></span> <span data-ttu-id="4b684-139">Omite las imágenes incrustadas y el formato, pero esta vista es muy útil si está intentando revisar y comprender rápidamente el contenido de un documento.</span><span class="sxs-lookup"><span data-stu-id="4b684-139">It ignores any embedded images and formatting, but this view is very useful if you're trying to quickly review and understand the content in a document.</span></span> <span data-ttu-id="4b684-140">La vista de texto también incluye estas características:</span><span class="sxs-lookup"><span data-stu-id="4b684-140">Text view also includes these features:</span></span>

  - <span data-ttu-id="4b684-141">Un contador de línea que hace que sea más fácil hacer referencia a partes específicas de un documento.</span><span class="sxs-lookup"><span data-stu-id="4b684-141">A line counter, which makes it easier to reference specific portions of a document.</span></span>

  - <span data-ttu-id="4b684-142">Buscar el resaltado de referencias que resalta los términos en el documento y en la barra de desplazamiento</span><span class="sxs-lookup"><span data-stu-id="4b684-142">Search hit highlighting that highlight terms in the document as well as on the scrollbar</span></span>

  - <span data-ttu-id="4b684-143">Una vista de diferencias proporciona una vista de comparación que resalta las diferencias de texto al ver los documentos mediante el panel de **duplicaDos Near** .</span><span class="sxs-lookup"><span data-stu-id="4b684-143">A diff view provides a comparison view that highlights the text differences when viewing documents using the **Near duplicates** panel.</span></span>

<span data-ttu-id="4b684-144">**Ejemplo de contador de línea y resaltado de búsqueda en el texto y en la barra de desplazamiento**</span><span class="sxs-lookup"><span data-stu-id="4b684-144">**Example of line counter and search hit highlighting in text and scrollbar**</span></span>

![<span data-ttu-id="4b684-145">Vista de texto</span><span class="sxs-lookup"><span data-stu-id="4b684-145">Text view</span></span>
](../media/Reviewimage4.png)

<span data-ttu-id="4b684-146">**Ejemplo de la vista diff**</span><span class="sxs-lookup"><span data-stu-id="4b684-146">**Example of the diff view**</span></span>

![<span data-ttu-id="4b684-147">Vista de diferencias</span><span class="sxs-lookup"><span data-stu-id="4b684-147">Diff view</span></span>
](../media/Reviewimage5.png)

## <a name="annotate-view"></a><span data-ttu-id="4b684-148">Vista de anotar</span><span class="sxs-lookup"><span data-stu-id="4b684-148">Annotate view</span></span>

<span data-ttu-id="4b684-149">La vista anotar proporciona características que permiten aplicar marcado a un documento durante el proceso de revisión; Esto incluye estas herramientas:</span><span class="sxs-lookup"><span data-stu-id="4b684-149">The Annotate view provides features that allow you to apply markup on a document during the review process; this  includes these tools:</span></span>

  - <span data-ttu-id="4b684-150">**Redacciones de área** : puede dibujar un cuadro opaco en el documento que oculte el contenido confidencial.</span><span class="sxs-lookup"><span data-stu-id="4b684-150">**Area redactions** – You can draw an opaque box on the document that hides sensitive content.</span></span>

  - <span data-ttu-id="4b684-151">**Lápiz** : puede liberar a mano un documento para atraer la atención a determinadas partes del contenido</span><span class="sxs-lookup"><span data-stu-id="4b684-151">**Pencil** – You can free-hand draw on a document to bring attention to certain portions of the content</span></span>

  - <span data-ttu-id="4b684-152">**Seleccionar anotaciones** : puede seleccionar y eliminar anotaciones en un documento.</span><span class="sxs-lookup"><span data-stu-id="4b684-152">**Select annotations** - You can select and delete annotations in a document.</span></span>

  - <span data-ttu-id="4b684-153">**Alternar transparencia de anotación** : puede alternar la transparencia de las anotaciones (entre opaco y semitransparente) para poder ver el contenido detrás de la anotación.</span><span class="sxs-lookup"><span data-stu-id="4b684-153">**Toggle annotation transparency** – You can toggle the transparency of annotations (between opaque and semi-transparent)so you can view the content behind the annotation.</span></span> <span data-ttu-id="4b684-154">Esto incluye alternar la transparencia de las anotaciones de lápiz y las redacciones.</span><span class="sxs-lookup"><span data-stu-id="4b684-154">This includes toggling the transparency of pencil annotations and redactions.</span></span>

<span data-ttu-id="4b684-155">La vista anotar también proporciona las siguientes funciones de navegación:</span><span class="sxs-lookup"><span data-stu-id="4b684-155">The Annotate view also provides the following navigation functionality:</span></span>

  - <span data-ttu-id="4b684-156">**Página anterior**, **página siguiente**y **vaya a** los controles de navegación de páginas que se van a usar para documentos de varias páginas.</span><span class="sxs-lookup"><span data-stu-id="4b684-156">**Previous page**, **Next page**, and **Go to page** - Navigation controls to use for multi-page documents.</span></span>

  - <span data-ttu-id="4b684-157">**Zoom** : aumenta o disminuye el tamaño de los documentos en la vista anotar.</span><span class="sxs-lookup"><span data-stu-id="4b684-157">**Zoom** – Increases or decreases the size of documents in Annotate view.</span></span>

  - <span data-ttu-id="4b684-158">**Girar** : girar documentos en el sentido de las agujas del reloj.</span><span class="sxs-lookup"><span data-stu-id="4b684-158">**Rotate** – Rotate documents clockwise.</span></span>

  - <span data-ttu-id="4b684-159">**Buscar** : busca palabras clave en un documento y, a continuación, usa los controles anterior y siguiente para ver los aciertos (resaltados) en el documento.</span><span class="sxs-lookup"><span data-stu-id="4b684-159">**Search** – Search for keywords in a document, and then use Previous and Next controls to view the hits (which are highlighted) within the document.</span></span>

<span data-ttu-id="4b684-160">**Ejemplo de la vista anotar**</span><span class="sxs-lookup"><span data-stu-id="4b684-160">**Example of Annotate view**</span></span>

![Vista de anotar](../media/Reviewimage1.png)

> [!NOTE]
> <span data-ttu-id="4b684-162">Las anotaciones se aplican a una copia del documento que se agregó al conjunto de evidencias.</span><span class="sxs-lookup"><span data-stu-id="4b684-162">Annotations are applied to a copy of the document that was added to the evidence set.</span></span> <span data-ttu-id="4b684-163">No se han anotado los documentos originales en el servicio activo.</span><span class="sxs-lookup"><span data-stu-id="4b684-163">The original documents in the live service aren't annotated.</span></span>
