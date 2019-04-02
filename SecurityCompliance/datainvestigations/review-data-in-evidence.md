---
title: Revisar datos en evidencia
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
ms.openlocfilehash: 279d2117a69e889f9e605e0ab211c03c5842a59d
ms.sourcegitcommit: 2c5834235c32b2616e1813ce24eeb3419a09629f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "31030528"
---
# <a name="review-data-in-evidence"></a><span data-ttu-id="e6687-102">Revisar datos en evidencia</span><span class="sxs-lookup"><span data-stu-id="e6687-102">Review data in evidence</span></span>

<span data-ttu-id="e6687-103">**Evidence** es una instantánea de los resultados de búsqueda que ha recopilado.</span><span class="sxs-lookup"><span data-stu-id="e6687-103">**Evidence** is a snapshot of search results that you collected.</span></span> <span data-ttu-id="e6687-104">Cuando se agregan resultados de búsqueda a Evidence, se desencadena un proceso para extraer archivos, metadatos y texto.</span><span class="sxs-lookup"><span data-stu-id="e6687-104">When you add search results to evidence, a process is triggered to extract files, metadata, and text.</span></span> <span data-ttu-id="e6687-105">A continuación, el sistema crea un nuevo índice de todos los datos y agrega a **prueba**.</span><span class="sxs-lookup"><span data-stu-id="e6687-105">Then, the system builds a new index of all the data and adds to **Evidence**.</span></span> 

<span data-ttu-id="e6687-106">Para cualquier incidente que tenga en cuenta el tiempo, esto le permite incluir rápidamente el entorno al eliminar datos en las ubicaciones originales mientras investiga la evidencia que se ha vuelto a crear en un entorno en cuarentena.</span><span class="sxs-lookup"><span data-stu-id="e6687-106">For any time-sensitive incidents, this allows you to quickly contain the environment by deleting data at original locations while investigating re-created evidence in a quarantined environment.</span></span> <span data-ttu-id="e6687-107">Una vez recopilada la evidencia, puede revisar documentos individuales en su formato nativo, formato de texto o un formato casi nativo.</span><span class="sxs-lookup"><span data-stu-id="e6687-107">Once evidence is collected, you can review individual documents in their native format, text format, or a near-native format.</span></span> <span data-ttu-id="e6687-108">Además, puede ejecutar consultas para restringir los datos por intervalo de tiempo, tipos de archivo, propietarios de datos y muchas otras tarjetas de condición.</span><span class="sxs-lookup"><span data-stu-id="e6687-108">Additionally, you can run queries to narrow the data by time range, file types, data owners, and many other condition cards.</span></span> <span data-ttu-id="e6687-109">Mediante el uso de las tarjetas de condición de autor/remitente/destinatario, puede examinar rápidamente quién está implicado en el derrame y si ha habido recursos compartidos externos.</span><span class="sxs-lookup"><span data-stu-id="e6687-109">Using Author/Sender/Recipient condition cards, you can quickly examine who are involved in the spill and if there have been any external shares.</span></span> <span data-ttu-id="e6687-110">Para más información, visite:</span><span class="sxs-lookup"><span data-stu-id="e6687-110">For more information, see:</span></span>

  - [<span data-ttu-id="e6687-111">Consultar los datos en evidencia</span><span class="sxs-lookup"><span data-stu-id="e6687-111">Query the data in evidence</span></span>](evidence-query.md)

<span data-ttu-id="e6687-112">Para agrupar documentos y obtener más ayuda para su revisión, haga clic en **administrar evidencias**.</span><span class="sxs-lookup"><span data-stu-id="e6687-112">To group documents and get more assistance for your review, click **Manage evidence**.</span></span> <span data-ttu-id="e6687-113">En el mosaico **Analytics** , haga clic en **analizar**.</span><span class="sxs-lookup"><span data-stu-id="e6687-113">In the **Analytics** tile, click **Analyze**.</span></span> <span data-ttu-id="e6687-114">De esta forma, se ejecutarán análisis avanzados, como la detección de duplicados, el procesamiento de correo electrónico y el análisis de temas.</span><span class="sxs-lookup"><span data-stu-id="e6687-114">This will run advanced analytics such as duplicate detection, email threading, and theme analysis.</span></span> <span data-ttu-id="e6687-115">Posteriormente, puede ver los temas generales de los datos y también organizar los documentos por conversaciones de correo electrónico, duplicados exactos y duplicados cercanos para facilitar su investigación.</span><span class="sxs-lookup"><span data-stu-id="e6687-115">Afterwards, you can see the general themes of the data and also organize documents by email threads, exact duplicates and near duplicates to facilitate your investigation.</span></span> <span data-ttu-id="e6687-116">Para más información, visite:</span><span class="sxs-lookup"><span data-stu-id="e6687-116">For more information, see:</span></span>

  - [<span data-ttu-id="e6687-117">Ejecutar análisis para investigar con mayor rapidez</span><span class="sxs-lookup"><span data-stu-id="e6687-117">Run analytics to investigate faster</span></span>](run-analytics-to-investigate-faster.md)

## <a name="view-documents-in-evidence"></a><span data-ttu-id="e6687-118">Ver documentos en prueba</span><span class="sxs-lookup"><span data-stu-id="e6687-118">View documents in evidence</span></span>

<span data-ttu-id="e6687-119">La investigación de datos (versión preliminar) muestra el contenido a través de varios visores cada uno con fines distintos.</span><span class="sxs-lookup"><span data-stu-id="e6687-119">Data investigation (Preview) displays content via several viewers each with different purposes.</span></span> <span data-ttu-id="e6687-120">Se pueden usar los distintos visores haciendo clic en cualquier documento en **evidencia**.</span><span class="sxs-lookup"><span data-stu-id="e6687-120">The various viewers can be used by clicking on any document in **Evidence**.</span></span> <span data-ttu-id="e6687-121">Los visores que se proporcionan actualmente son:</span><span class="sxs-lookup"><span data-stu-id="e6687-121">The viewers currently provided are:</span></span>

- <span data-ttu-id="e6687-122">Metadatos de archivo</span><span class="sxs-lookup"><span data-stu-id="e6687-122">File metadata</span></span>
- <span data-ttu-id="e6687-123">Vista nativa</span><span class="sxs-lookup"><span data-stu-id="e6687-123">Native view</span></span>
- <span data-ttu-id="e6687-124">Vista de texto</span><span class="sxs-lookup"><span data-stu-id="e6687-124">Text view</span></span>
- <span data-ttu-id="e6687-125">Vista de anotar</span><span class="sxs-lookup"><span data-stu-id="e6687-125">Annotate view</span></span>
- <span data-ttu-id="e6687-126">Vista convertida</span><span class="sxs-lookup"><span data-stu-id="e6687-126">Converted view</span></span>

## <a name="file-metadata"></a><span data-ttu-id="e6687-127">Metadatos de archivo</span><span class="sxs-lookup"><span data-stu-id="e6687-127">File metadata</span></span>

<span data-ttu-id="e6687-128">Este panel puede activarse o desactivarse para mostrar varios metadatos asociados con el documento.</span><span class="sxs-lookup"><span data-stu-id="e6687-128">This panel can be toggled on/off to display various metadata associated with the document.</span></span> <span data-ttu-id="e6687-129">Aunque la cuadrícula de resultados de búsqueda se puede personalizar para Mostrar metadatos específicos, hay casos en los que el desplazamiento horizontal puede resultar difícil mientras se revisan los datos.</span><span class="sxs-lookup"><span data-stu-id="e6687-129">Although the search results grid can be customized to display specific metadata, there are instances where scrolling horizontally can be difficult while reviewing data.</span></span> <span data-ttu-id="e6687-130">El panel metadatos de archivo permite al usuario alternar una vista dentro del visor.</span><span class="sxs-lookup"><span data-stu-id="e6687-130">The File metadata panel allows a user to toggle on a view within the viewer.</span></span>

![<span data-ttu-id="e6687-131">Panel metadatos de archivo</span><span class="sxs-lookup"><span data-stu-id="e6687-131">File metadata panel</span></span>
](../media/Reviewimage2.png)

## <a name="native-view"></a><span data-ttu-id="e6687-132">Vista nativa</span><span class="sxs-lookup"><span data-stu-id="e6687-132">Native view</span></span>

<span data-ttu-id="e6687-133">El visor nativo muestra la vista más completa de un documento.</span><span class="sxs-lookup"><span data-stu-id="e6687-133">The Native viewer displays the richest view of a document.</span></span> <span data-ttu-id="e6687-134">Admite cientos de tipos de archivo y está destinado a mostrar la experiencia más auténtica posible a la experiencia nativa.</span><span class="sxs-lookup"><span data-stu-id="e6687-134">It supports hundreds of file types and is meant to display the truest to native experience possible.</span></span> <span data-ttu-id="e6687-135">Para los archivos de Microsoft Office, por ejemplo, el visor aprovecha Office online para mostrar contenido como comentarios del documento, fórmulas de Excel, filas o columnas ocultas, notas de PowerPoint, etc. Para obtener más información acerca de los visores de Office Online, \[visite aquí necesita vínculo\]</span><span class="sxs-lookup"><span data-stu-id="e6687-135">For Microsoft Office files, for example, the viewer leverages Office Online in order to display content such as document comments, Excel formulas, hidden rows/columns, PowerPoint notes, etc. For more information regarding the Office Online viewers, visit here \[need link\]</span></span>

![<span data-ttu-id="e6687-136">Vista nativa</span><span class="sxs-lookup"><span data-stu-id="e6687-136">Native view</span></span>
](../media/Reviewimage3.png)

## <a name="text-view"></a><span data-ttu-id="e6687-137">Vista de texto</span><span class="sxs-lookup"><span data-stu-id="e6687-137">Text view</span></span>

<span data-ttu-id="e6687-138">El visor de texto proporciona una vista del texto extraído de un archivo.</span><span class="sxs-lookup"><span data-stu-id="e6687-138">The Text viewer provides a view of the extracted text of a file.</span></span> <span data-ttu-id="e6687-139">Ignora las imágenes incrustadas y el formato, pero será una vista eficaz si un usuario intenta comprender el contenido rápidamente.</span><span class="sxs-lookup"><span data-stu-id="e6687-139">It ignores any embedded images and formatting but will be a very performant view if a user is trying to understand the content quickly.</span></span> <span data-ttu-id="e6687-140">La vista de texto también incluye otras características:</span><span class="sxs-lookup"><span data-stu-id="e6687-140">Text view also includes other features:</span></span>

  - <span data-ttu-id="e6687-141">El contador de línea hace que sea más fácil hacer referencia a partes específicas de un documento</span><span class="sxs-lookup"><span data-stu-id="e6687-141">Line counter makes it easier to reference specific portions of a document</span></span>

  - <span data-ttu-id="e6687-142">Buscar el resaltado de referencias que resaltará los términos dentro del documento, así como la barra de desplazamiento</span><span class="sxs-lookup"><span data-stu-id="e6687-142">Search hit highlighting that will highlight terms within the document as well as the scrollbar</span></span>

  - <span data-ttu-id="e6687-143">La vista de diferencias proporciona una vista de comparación que resalta las diferencias textuales al ver documentos con duplicados Near</span><span class="sxs-lookup"><span data-stu-id="e6687-143">Diff view provides a comparison view that highlights textual differences when viewing Near Duplicate documents</span></span>

![<span data-ttu-id="e6687-144">Vista de texto</span><span class="sxs-lookup"><span data-stu-id="e6687-144">Text view</span></span>
](../media/Reviewimage4.png)

![<span data-ttu-id="e6687-145">Vista de diferencias</span><span class="sxs-lookup"><span data-stu-id="e6687-145">Diff view</span></span>
](../media/Reviewimage5.png)

## <a name="annotate-view"></a><span data-ttu-id="e6687-146">Vista de anotar</span><span class="sxs-lookup"><span data-stu-id="e6687-146">Annotate view</span></span>

<span data-ttu-id="e6687-147">La vista anotar proporciona características que permiten a los usuarios aplicar marcas en un documento durante la investigación, incluidos:</span><span class="sxs-lookup"><span data-stu-id="e6687-147">The Annotate view provides features that allow users to apply markup on a document during investigation including:</span></span>

  - <span data-ttu-id="e6687-148">Redacciones de área: los usuarios pueden dibujar un cuadro en el documento con el fin de ocultar contenido confidencial.</span><span class="sxs-lookup"><span data-stu-id="e6687-148">Area redactions – users can draw a box on the document in order to hide sensitive content</span></span>

  - <span data-ttu-id="e6687-149">Lápiz: los usuarios pueden dibujarse en un documento de forma gratuita para atraer la atención sobre determinadas partes de un documento.</span><span class="sxs-lookup"><span data-stu-id="e6687-149">Pencil – users can free-hand draw on a document in order to bring attention to certain portions of a document</span></span>

  - <span data-ttu-id="e6687-150">Seleccionar anotaciones: los usuarios pueden seleccionar anotaciones en un documento para poder eliminar</span><span class="sxs-lookup"><span data-stu-id="e6687-150">Select annotations - users can select annotations on a document in order to delete</span></span>

  - <span data-ttu-id="e6687-151">Alternar transparencia de anotación: hace que las anotaciones sean semitransparentes para poder ver el contenido detrás de la anotación</span><span class="sxs-lookup"><span data-stu-id="e6687-151">Toggle annotation transparency – makes annotations semi-transparent in order to view the content behind the annotation</span></span>

  - <span data-ttu-id="e6687-152">Página anterior: se desplaza a la página anterior</span><span class="sxs-lookup"><span data-stu-id="e6687-152">Previous page – navigates to previous page</span></span>

  - <span data-ttu-id="e6687-153">Página siguiente: se desplaza a la página siguiente.</span><span class="sxs-lookup"><span data-stu-id="e6687-153">Next page – navigates to the next page</span></span>

  - <span data-ttu-id="e6687-154">Ir a la página: el usuario puede escribir un número de página específico para navegar</span><span class="sxs-lookup"><span data-stu-id="e6687-154">Go to page – user can enter a specific page number to navigate to</span></span>

  - <span data-ttu-id="e6687-155">Zoom: establece el nivel de zoom para la vista anotar</span><span class="sxs-lookup"><span data-stu-id="e6687-155">Zoom – set zoom level for annotate view</span></span>

  - <span data-ttu-id="e6687-156">Girar: el usuario puede girar el documento en sentido horario</span><span class="sxs-lookup"><span data-stu-id="e6687-156">Rotate – user can rotate document clockwise</span></span>

  - <span data-ttu-id="e6687-157">Buscar: el usuario puede buscar en un documento y desplazarse a los distintos aciertos dentro del documento</span><span class="sxs-lookup"><span data-stu-id="e6687-157">Search – user can search within a document and navigate to the various hits within the document</span></span>
    
    ![<span data-ttu-id="e6687-158">Vista de anotar</span><span class="sxs-lookup"><span data-stu-id="e6687-158">Annotate view</span></span>
    ](../media/Reviewimage1.png)

<span data-ttu-id="e6687-159">Tenga en cuenta que estas anotaciones se encuentran en datos recopilados como evidencia, no en su ubicación original en el sistema activo.</span><span class="sxs-lookup"><span data-stu-id="e6687-159">Note that these annotations are on data collected as evidence, not at its original location in live system.</span></span> 

## <a name="more-information"></a><span data-ttu-id="e6687-160">Más información</span><span class="sxs-lookup"><span data-stu-id="e6687-160">More information</span></span>

<span data-ttu-id="e6687-161">En la siguiente tabla se enumeran los límites de evidencia en las investigaciones de datos (versión preliminar).</span><span class="sxs-lookup"><span data-stu-id="e6687-161">The following table lists the limits for evidence in Data Investigations (Preview).</span></span>  <span data-ttu-id="e6687-162">Los elementos que excedan los máximos de un solo archivo se mostrarán como errores de procesamiento.</span><span class="sxs-lookup"><span data-stu-id="e6687-162">Any items that exceed the single file maximums will show up as processing errors.</span></span>
    
  |<span data-ttu-id="e6687-163">**Descripción del límite**</span><span class="sxs-lookup"><span data-stu-id="e6687-163">**Description of limit**</span></span>|<span data-ttu-id="e6687-164">**Límite**</span><span class="sxs-lookup"><span data-stu-id="e6687-164">**Limit**</span></span>|
  |:-----|:-----|
  |<span data-ttu-id="e6687-165">Número máximo de colecciones de evidencias</span><span class="sxs-lookup"><span data-stu-id="e6687-165">Maximum number of evidence collections</span></span>  <br/> |<span data-ttu-id="e6687-166">50</span><span class="sxs-lookup"><span data-stu-id="e6687-166">50</span></span>  <br/> |
  |<span data-ttu-id="e6687-167">Número total de documentos que se pueden recopilar en un caso (para todas las colecciones de evidencias en la investigación)</span><span class="sxs-lookup"><span data-stu-id="e6687-167">Total number of documents that can be ingested into a case (for all evidence collections in the investigation)</span></span>  <br/> |<span data-ttu-id="e6687-168">1 millón</span><span class="sxs-lookup"><span data-stu-id="e6687-168">1 million</span></span>  <br/> |
  |<span data-ttu-id="e6687-169">Tamaño total de archivo por carga</span><span class="sxs-lookup"><span data-stu-id="e6687-169">Total file size per load</span></span>  <br/> |<span data-ttu-id="e6687-170">100 GB</span><span class="sxs-lookup"><span data-stu-id="e6687-170">100 GB</span></span>  <br/> |
  |<span data-ttu-id="e6687-171">Tamaño máximo de un solo archivo</span><span class="sxs-lookup"><span data-stu-id="e6687-171">Maximum size of single file</span></span>   <br/> |<span data-ttu-id="e6687-172">100 MB</span><span class="sxs-lookup"><span data-stu-id="e6687-172">100 MB</span></span>  <br/> |
  |<span data-ttu-id="e6687-173">Número máximo de caracteres extraídos de un único archivo</span><span class="sxs-lookup"><span data-stu-id="e6687-173">Maximum number of characters extracted from a single file</span></span>  <br/> |<span data-ttu-id="e6687-174">10 millones</span><span class="sxs-lookup"><span data-stu-id="e6687-174">10 million</span></span>  <br/> |
  |<span data-ttu-id="e6687-175">Profundidad de los elementos insertados en un documento</span><span class="sxs-lookup"><span data-stu-id="e6687-175">Depth of embedded items in a document</span></span>  <br/> |<span data-ttu-id="e6687-176">IVA</span><span class="sxs-lookup"><span data-stu-id="e6687-176">25</span></span>  <br/> |
  