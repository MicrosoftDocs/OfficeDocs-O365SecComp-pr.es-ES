---
title: Ejecutar el módulo de proceso en eDiscovery avanzado de Office 365
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 9/14/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: dbc1e251-0596-443b-ac9b-f398ba955b73
description: 'Obtenga información sobre las directrices para preparar archivos casos de datos de Office 365 para el análisis con Office 365 avanzada exhibición de documentos electrónicos.  '
ms.openlocfilehash: 52b1dce9fb778c6628d90c39135f0c93f08134d7
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22536747"
---
# <a name="run-the-process-module-in-office-365-advanced-ediscovery"></a><span data-ttu-id="60f39-103">Ejecutar el módulo de proceso en eDiscovery avanzado de Office 365</span><span class="sxs-lookup"><span data-stu-id="60f39-103">Run the Process module in Office 365 Advanced eDiscovery</span></span>

<span data-ttu-id="60f39-104">Archivos de casos se cargan en la exhibición de documentos electrónicos avanzada durante la **preparación** \> **proceso**.</span><span class="sxs-lookup"><span data-stu-id="60f39-104">Case files are loaded into the Advanced eDiscovery during **Prepare** \> **Process**.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="60f39-p101">Exhibición de documentos electrónicos avanzada requiere un E3 de Office 365 con el complemento de cumplimiento avanzadas o una suscripción E5 para su organización. Si no tiene ese plan y desea probar avanzada exhibición de documentos electrónicos, puede [registrarse y obtener una versión de prueba de Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span><span class="sxs-lookup"><span data-stu-id="60f39-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
## <a name="guidelines-preparing-data-for-advanced-ediscovery"></a><span data-ttu-id="60f39-107">Instrucciones: Preparar datos para la exhibición de documentos electrónicos avanzada</span><span class="sxs-lookup"><span data-stu-id="60f39-107">Guidelines: Preparing data for Advanced eDiscovery</span></span>

- <span data-ttu-id="60f39-108">**Calidad**: identificar claramente la población de mayúsculas y minúsculas archivo pertinente para el caso.</span><span class="sxs-lookup"><span data-stu-id="60f39-108">**Quality**: Clearly identify the case file population pertinent to the case.</span></span>
    
- <span data-ttu-id="60f39-109">**Cargas**: cargar los archivos en una ubicación que sea accesible a avanzada exhibición de documentos electrónicos.</span><span class="sxs-lookup"><span data-stu-id="60f39-109">**Loads**: Load the files into a location that is accessible to Advanced eDiscovery.</span></span>
    
- <span data-ttu-id="60f39-p102">**Identificador de archivo**: un identificador de archivo único en la exhibición de documentos electrónicos avanzada. Si no se importa ningún identificador de archivo, exhibición de documentos electrónicos avanzada genera automáticamente el identificador. Si asignar el identificador de una carga de proceso posterior y asignar una ruta diferente a en la carga del proceso inicial, exhibición de documentos electrónicos avanzada va a reemplazar la ruta de acceso (en lugar de agregar una nueva entrada de archivo). El identificador se puede usar como una referencia en el proceso de exportación. El valor del identificador no debe ser "-1".</span><span class="sxs-lookup"><span data-stu-id="60f39-p102">**File ID**: A unique file identifier in Advanced eDiscovery. If no file identifier is imported, Advanced eDiscovery automatically generates the ID. If you map the ID in a subsequent Process load, and map a different path than in the initial Process load, Advanced eDiscovery will replace the path (rather than add a new file entry). The ID can be used as a reference in the Export process. The ID value should not be "-1".</span></span>
    
- <span data-ttu-id="60f39-p103">**MD5**: esta firma se usa para diferenciar entre archivos (dos archivos no se consideran duplicados exactos a menos que tengan el mismo MD5). De forma predeterminada, exhibición de documentos electrónicos avanzada calcula el MD5 de archivos. Cuando los archivos cargados son archivos de texto, se recomienda para cargar y asignar el valor original de MD5 en lugar de calcular en la exhibición de documentos electrónicos avanzada.</span><span class="sxs-lookup"><span data-stu-id="60f39-p103">**MD5**: This signature is used to differentiate between files (two files are not considered exact duplicates unless they have the same MD5). By default, Advanced eDiscovery calculates the MD5 of files. When the loaded files are text files, it is recommended to load and map the original MD5 value instead of calculating it in Advanced eDiscovery.</span></span>
    
- <span data-ttu-id="60f39-118">**Nombre y tipo de archivo**:</span><span class="sxs-lookup"><span data-stu-id="60f39-118">**File type and name**:</span></span>
    
  - <span data-ttu-id="60f39-p104">Exhibición de documentos electrónicos avanzada puede procesar archivos de varios formatos y extraer archivos nativos cargados en un formato estándar, como \*. TXT, HTML, o. XML. procesamiento de archivos de texto es más rápido que los archivos nativos. Archivos de texto extraídos se almacenan en la carpeta de mayúsculas y minúsculas.</span><span class="sxs-lookup"><span data-stu-id="60f39-p104">Advanced eDiscovery can process files of various formats and extract loaded native files into a standard format, such as \*.TXT, HTML, or .XML. Processing of text files is faster than native files. Extracted text files are stored in the case folder.</span></span>
    
  - <span data-ttu-id="60f39-p105">No se cargan los archivos que no se pueden extraer, como los archivos del sistema o imágenes gráficas. Estos archivos pueden retrasar el procesamiento.</span><span class="sxs-lookup"><span data-stu-id="60f39-p105">Do not load files that cannot be extracted, such as system files or graphic images. These files may delay processing.</span></span>
    
  - <span data-ttu-id="60f39-124">Compruebe que los nombres de archivo se denominan significativamente y rutas de acceso son correctos.</span><span class="sxs-lookup"><span data-stu-id="60f39-124">Verify that file names are significantly named and paths are correct.</span></span>
    
- <span data-ttu-id="60f39-125">**Ruta de acceso de archivo**: exhibición de documentos electrónicos avanzada puede cargar archivos con longitudes de ruta de acceso hasta 400 caracteres.</span><span class="sxs-lookup"><span data-stu-id="60f39-125">**File path**: Advanced eDiscovery can load files with path lengths up to 400 characters.</span></span>
    
- <span data-ttu-id="60f39-p106">**Extracción de texto**: al extraer texto de archivos nativos, además de texto normal, también se extraen los siguientes: columnas de texto oculto (Excel y .doc), oculto (Excel), control de cambios (.doc), objetos de notes (.ppt), incrustados de altavoz (por ejemplo, Objetos de Excel en un .ppt). Estos se pueden ver en el editor de texto.</span><span class="sxs-lookup"><span data-stu-id="60f39-p106">**Text extraction**: When extracting text from native files, in addition to normal text, the following are also extracted: hidden text (Excel and .doc), hidden columns (Excel), track changes (.doc), speaker notes (.ppt), embedded objects (for example, Excel objects in a .ppt). These can be viewed in the Text editor.</span></span>
    
- <span data-ttu-id="60f39-p107">**Omitir texto**: esta característica opcional se define una vez que se ejecuta el proceso y antes de analizar. Omitir texto debe usarse con precaución debido a que su uso puede reducir el rendimiento de análisis del archivo.</span><span class="sxs-lookup"><span data-stu-id="60f39-p107">**Ignore Text**: This optional feature is defined after Process is run and before Analyze. Ignore text should be used with caution because its use may reduce the performance of file analysis.</span></span>
    
- <span data-ttu-id="60f39-130">**Texto multilingüe**: exhibición de documentos electrónicos avanzada no procesa actualmente multilingües nombres para las etiquetas, custodia y problemas.</span><span class="sxs-lookup"><span data-stu-id="60f39-130">**Multilingual text**: Advanced eDiscovery does not currently handle multilingual names for tags, custodian, and issues.</span></span>
    
- <span data-ttu-id="60f39-p108">**Metadatos**: determinar si hay metadatos que desea guardar en la base de datos de caso para futuras referencias, como el intervalo de fechas, el tamaño de archivo, el tipo de archivo, custodia y asunto. Después de que los archivos ya se han cargado sin volver a ejecutar el inventario o agregar el reprocesamiento de sobrecarga, se pueden cargar metadatos.</span><span class="sxs-lookup"><span data-stu-id="60f39-p108">**Metadata**: Determine if there is metadata that you want to save in the case database for future reference, such as date range, file size, file type, custodian, and subject. Metadata can be loaded after files were already loaded without rerunning the inventory or adding reprocessing overhead.</span></span> 
    
  - <span data-ttu-id="60f39-p109">Si los archivos se han cargado originalmente por la ruta de acceso, asigne la columna de ruta de acceso al importar los metadatos más adelante. Es posible hacer referencia al archivo por identificador y para asignar una ruta de acceso diferente. Éste es un escenario útil cuando cambian las rutas de acceso de archivo.</span><span class="sxs-lookup"><span data-stu-id="60f39-p109">If the files were originally loaded by path, map the path column when later importing metadata. It is possible to refer to the file by ID and to map a different path. This is a useful scenario when the file paths change.</span></span>
    
  - <span data-ttu-id="60f39-p110">Si los archivos se han cargado originalmente por identificador de archivo, asigne la columna de identificador al cargar metadatos. Hace referencia al archivo mediante la ruta de acceso (en lugar de identificador) hará que los archivos que se va a volver a cargar con un ID diferente. Exhibición de documentos electrónicos avanzada crea copias de los archivos en su lugar que carga los metadatos de los archivos existentes.</span><span class="sxs-lookup"><span data-stu-id="60f39-p110">If the files were originally loaded by File ID, map the ID column when loading metadata. Referring to the file by path (instead of ID) will cause files to be re-loaded with a different ID. Advanced eDiscovery creates copies of the files rather that loading metadata of the existing files.</span></span>
    
- <span data-ttu-id="60f39-139">**Familias**: no es posible cargar una familia sin su elemento primario (cabeza de familia).</span><span class="sxs-lookup"><span data-stu-id="60f39-139">**Families**: It is not possible to load a family without its parent (head of family).</span></span> 
    
- <span data-ttu-id="60f39-p111">**Tamaño de archivo**: no hay ninguna limitación en el tamaño de archivos cargados a avanzada exhibición de documentos electrónicos. Para el análisis (analizar, la relevancia, etc.), el límite es es de 5.242.880 caracteres de texto extraído. Se omiten los archivos de mayor tamaño (por ejemplo, en la relevancia, los archivos no participan en el proceso de aprendizaje de la relevancia y no reciben una puntuación de relevancia después del cálculo por lotes).</span><span class="sxs-lookup"><span data-stu-id="60f39-p111">**File size**: There is no limitation on the size of files loaded to Advanced eDiscovery. For analysis (Analyze, Relevance, etc.), the limit is 5,242,880 characters of extracted text. Larger files are ignored (for example, in Relevance, files do not participate in the Relevance training process and do not receive a Relevance score after batch calculation).</span></span>
    
- <span data-ttu-id="60f39-p112">**Cantidad de archivo**: no hay ningún límite en el número de archivos que se pueden controlar en un único caso recomendado. Rendimiento depende de los recursos del sistema.</span><span class="sxs-lookup"><span data-stu-id="60f39-p112">**File quantity**: There is no recommended limit on the number of files that can be handled in a single case. Performance depends on the resources of your system.</span></span> 
    
## <a name="filtering-files"></a><span data-ttu-id="60f39-145">Filtrado de archivos</span><span class="sxs-lookup"><span data-stu-id="60f39-145">Filtering files</span></span>

<span data-ttu-id="60f39-p113">Una etiqueta definida por el usuario puede asociarse con un conjunto de archivos que se excluirán proceso u otras tareas. Cada sesión de proceso está asociado con un ID de lote. Aunque no es visible para el experto en la relevancia el ID de lote, esto puede realizarse mediante una utilidad de búsqueda, mediante la adición de un filtro para el lote actual y etiquetar todos los archivos adecuados con una etiqueta definida por el usuario.</span><span class="sxs-lookup"><span data-stu-id="60f39-p113">A user-defined label can be associated with a set of files to exclude them from Process or other tasks. Each Process session is associated with a batch ID. Although the batch ID is not visible to the expert in Relevance, this can be done using a search utility, by adding a filter for the current batch and tagging all appropriate files with a user-defined label.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="60f39-149">Vea también</span><span class="sxs-lookup"><span data-stu-id="60f39-149">See also</span></span>

[<span data-ttu-id="60f39-150">eDiscovery avanzado de Office 365</span><span class="sxs-lookup"><span data-stu-id="60f39-150">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="60f39-151">Ejecute el módulo de proceso y carga de datos</span><span class="sxs-lookup"><span data-stu-id="60f39-151">Running the Process module and loading data</span></span>](run-the-process-module-and-load-data-in-advanced-ediscovery.md)
  
[<span data-ttu-id="60f39-152">Ver los resultados del módulo de proceso</span><span class="sxs-lookup"><span data-stu-id="60f39-152">Viewing Process module results</span></span>](view-process-module-results-in-advanced-ediscovery.md)

