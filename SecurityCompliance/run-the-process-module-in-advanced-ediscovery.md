---
title: Ejecutar el módulo de proceso en eDiscovery avanzado de Office 365
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 9/14/2017
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: dbc1e251-0596-443b-ac9b-f398ba955b73
description: 'Obtenga información sobre las directrices para preparar archivos de casos de Office 365 datos para analizar con Office 365 Advanced eDiscovery.  '
ms.openlocfilehash: 19d50bda21f752ec7c22fe52b6fa7272592de128
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/23/2019
ms.locfileid: "30216120"
---
# <a name="run-the-process-module-in-office-365-advanced-ediscovery"></a><span data-ttu-id="8b187-103">Ejecutar el módulo de proceso en eDiscovery avanzado de Office 365</span><span class="sxs-lookup"><span data-stu-id="8b187-103">Run the Process module in Office 365 Advanced eDiscovery</span></span>

<span data-ttu-id="8b187-104">Los archivos de casos se cargan en la exhibición avanzada de documentos electrónicos durante el **proceso**de **preparación** \> .</span><span class="sxs-lookup"><span data-stu-id="8b187-104">Case files are loaded into the Advanced eDiscovery during **Prepare** \> **Process**.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="8b187-p101">Para usar eDiscovery avanzado, su organización necesita una suscripción de Office 365 E3 con el complemento Cumplimiento avanzado, o bien una suscripción de E5. Si no tiene ese plan y quiere probar eDiscovery avanzado, puede [registrarse para una prueba de Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span><span class="sxs-lookup"><span data-stu-id="8b187-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
## <a name="guidelines-preparing-data-for-advanced-ediscovery"></a><span data-ttu-id="8b187-107">Instrucciones: preparación de datos para la exhibición avanzada de documentos electrónicos</span><span class="sxs-lookup"><span data-stu-id="8b187-107">Guidelines: Preparing data for Advanced eDiscovery</span></span>

- <span data-ttu-id="8b187-108">**Quality**: identifique claramente la población de archivos de caso pertinente para el caso.</span><span class="sxs-lookup"><span data-stu-id="8b187-108">**Quality**: Clearly identify the case file population pertinent to the case.</span></span>
    
- <span data-ttu-id="8b187-109">**Carga**: Cargue los archivos en una ubicación que sea accesible para la exhibición avanzada de documentos electrónicos.</span><span class="sxs-lookup"><span data-stu-id="8b187-109">**Loads**: Load the files into a location that is accessible to Advanced eDiscovery.</span></span>
    
- <span data-ttu-id="8b187-p102">**Identificador de archivo**: un identificador de archivo único en la exhibición avanzada de documentos electrónicos. Si no se importa ningún identificador de archivo, la exhibición de documentos electrónicos avanzada genera automáticamente el identificador. Si asigna el identificador en una carga de proceso posterior y asigna una ruta de acceso diferente a la carga de proceso inicial, la exhibición avanzada de documentos electrónicos reemplazará la ruta de acceso (en lugar de agregar una nueva entrada de archivo). El identificador puede usarse como referencia en el proceso de exportación. El valor del identificador no debe ser "-1".</span><span class="sxs-lookup"><span data-stu-id="8b187-p102">**File ID**: A unique file identifier in Advanced eDiscovery. If no file identifier is imported, Advanced eDiscovery automatically generates the ID. If you map the ID in a subsequent Process load, and map a different path than in the initial Process load, Advanced eDiscovery will replace the path (rather than add a new file entry). The ID can be used as a reference in the Export process. The ID value should not be "-1".</span></span>
    
- <span data-ttu-id="8b187-p103">**MD5**: esta firma se usa para diferenciar archivos (dos archivos no se consideran duplicados exactos a menos que tengan el mismo MD5). De forma predeterminada, eDiscovery avanzado calcula el MD5 de los archivos. Cuando los archivos cargados son archivos de texto, se recomienda cargar y asignar el valor MD5 original en lugar de calcularlo en la exhibición avanzada de documentos electrónicos.</span><span class="sxs-lookup"><span data-stu-id="8b187-p103">**MD5**: This signature is used to differentiate between files (two files are not considered exact duplicates unless they have the same MD5). By default, Advanced eDiscovery calculates the MD5 of files. When the loaded files are text files, it is recommended to load and map the original MD5 value instead of calculating it in Advanced eDiscovery.</span></span>
    
- <span data-ttu-id="8b187-118">**Tipo de archivo y nombre**:</span><span class="sxs-lookup"><span data-stu-id="8b187-118">**File type and name**:</span></span>
    
  - <span data-ttu-id="8b187-p104">EDiscovery avanzado puede procesar archivos de distintos formatos y extraer archivos nativos cargados en un formato estándar, como \*. TXT, HTML o. XML. el procesamiento de archivos de texto es más rápido que los archivos nativos. Los archivos de texto exTraídos se almacenan en la carpeta Case.</span><span class="sxs-lookup"><span data-stu-id="8b187-p104">Advanced eDiscovery can process files of various formats and extract loaded native files into a standard format, such as \*.TXT, HTML, or .XML. Processing of text files is faster than native files. Extracted text files are stored in the case folder.</span></span>
    
  - <span data-ttu-id="8b187-p105">No cargue archivos que no se puedan extraer, como archivos del sistema o imágenes gráficas. Estos archivos pueden retrasar el procesamiento.</span><span class="sxs-lookup"><span data-stu-id="8b187-p105">Do not load files that cannot be extracted, such as system files or graphic images. These files may delay processing.</span></span>
    
  - <span data-ttu-id="8b187-124">Compruebe que los nombres de archivo tengan un nombre significativo y que las rutas sean correctas.</span><span class="sxs-lookup"><span data-stu-id="8b187-124">Verify that file names are significantly named and paths are correct.</span></span>
    
- <span data-ttu-id="8b187-125">**Ruta**de acceso al archivo: eDiscovery avanzado puede cargar archivos con longitudes de ruta de hasta 400 caracteres.</span><span class="sxs-lookup"><span data-stu-id="8b187-125">**File path**: Advanced eDiscovery can load files with path lengths up to 400 characters.</span></span>
    
- <span data-ttu-id="8b187-p106">**Extracción de texto**: al extraer texto de archivos nativos, además del texto normal, también se extraen los siguientes elementos: texto oculto (Excel y. doc), columnas ocultas (Excel), control de cambios (. doc), notas del orador (. ppt), objetos incrustados (por ejemplo, Objetos de Excel en un. ppt). Se pueden ver en el editor de texto.</span><span class="sxs-lookup"><span data-stu-id="8b187-p106">**Text extraction**: When extracting text from native files, in addition to normal text, the following are also extracted: hidden text (Excel and .doc), hidden columns (Excel), track changes (.doc), speaker notes (.ppt), embedded objects (for example, Excel objects in a .ppt). These can be viewed in the Text editor.</span></span>
    
- <span data-ttu-id="8b187-p107">**Omitir texto**: esta característica opcional se define después de ejecutar el proceso y antes de analizar. Ignore Text debe usarse con cuidado porque su uso puede reducir el rendimiento del análisis de archivos.</span><span class="sxs-lookup"><span data-stu-id="8b187-p107">**Ignore Text**: This optional feature is defined after Process is run and before Analyze. Ignore text should be used with caution because its use may reduce the performance of file analysis.</span></span>
    
- <span data-ttu-id="8b187-130">**Texto multilingüe**: la exhibición avanzada de documentos electrónicos no controla actualmente los nombres multilingües de etiquetas, custodios y problemas.</span><span class="sxs-lookup"><span data-stu-id="8b187-130">**Multilingual text**: Advanced eDiscovery does not currently handle multilingual names for tags, custodian, and issues.</span></span>
    
- <span data-ttu-id="8b187-p108">**Metadata**: Determine si hay metadatos que desea guardar en la base de datos de casos para futuras referencias, como intervalo de fechas, tamaño de archivo, tipo de archivo, custodio y asunto. Los metaDatos se pueden cargar después de que los archivos se hayan cargado sin tener que volver a ejecutar el inventario o agregar la sobrecarga de reprocesamiento.</span><span class="sxs-lookup"><span data-stu-id="8b187-p108">**Metadata**: Determine if there is metadata that you want to save in the case database for future reference, such as date range, file size, file type, custodian, and subject. Metadata can be loaded after files were already loaded without rerunning the inventory or adding reprocessing overhead.</span></span> 
    
  - <span data-ttu-id="8b187-p109">Si los archivos se cargaron originalmente por ruta de acceso, asigne la columna Path cuando más adelante importando metadatos. Es posible hacer referencia al archivo por su identificador y asignar una ruta de acceso diferente. Este es un escenario útil cuando las rutas de archivo cambian.</span><span class="sxs-lookup"><span data-stu-id="8b187-p109">If the files were originally loaded by path, map the path column when later importing metadata. It is possible to refer to the file by ID and to map a different path. This is a useful scenario when the file paths change.</span></span>
    
  - <span data-ttu-id="8b187-p110">Si los archivos se cargaron originalmente por identificador de archivo, asigne la columna ID al cargar metadatos. Si se hace referencia al archivo por ruta de acceso (en lugar de ID.), los archivos se volverán a cargar con un identificador diferente. EDiscovery avanzado crea copias de los archivos en lugar de cargar los metadatos de los archivos existentes.</span><span class="sxs-lookup"><span data-stu-id="8b187-p110">If the files were originally loaded by File ID, map the ID column when loading metadata. Referring to the file by path (instead of ID) will cause files to be re-loaded with a different ID. Advanced eDiscovery creates copies of the files rather that loading metadata of the existing files.</span></span>
    
- <span data-ttu-id="8b187-139">**Familias**: no se puede cargar una familia sin su principal (encabezado de familia).</span><span class="sxs-lookup"><span data-stu-id="8b187-139">**Families**: It is not possible to load a family without its parent (head of family).</span></span> 
    
- <span data-ttu-id="8b187-p111">**Tamaño de archivo**: no hay ninguna limitación en el tamaño de los archivos cargados en la exhibición avanzada de documentos electrónicos. Para el análisis (analizar, relevancia, etc.), el límite es de 5.242.880 caracteres de texto extraído. Los archivos de mayor tamaño se ignoran (por ejemplo, en relevancia, los archivos no participan en el proceso de entrenamiento de relevancia y no reciben una puntuación de relevancia tras el cálculo del lote).</span><span class="sxs-lookup"><span data-stu-id="8b187-p111">**File size**: There is no limitation on the size of files loaded to Advanced eDiscovery. For analysis (Analyze, Relevance, etc.), the limit is 5,242,880 characters of extracted text. Larger files are ignored (for example, in Relevance, files do not participate in the Relevance training process and do not receive a Relevance score after batch calculation).</span></span>
    
- <span data-ttu-id="8b187-p112">**Cantidad de archivo**: no hay ningún límite recomendado en el número de archivos que se pueden administrar en un único caso. El rendimiento depende de los recursos del sistema.</span><span class="sxs-lookup"><span data-stu-id="8b187-p112">**File quantity**: There is no recommended limit on the number of files that can be handled in a single case. Performance depends on the resources of your system.</span></span> 
    
## <a name="filtering-files"></a><span data-ttu-id="8b187-145">Filtrado de archivos</span><span class="sxs-lookup"><span data-stu-id="8b187-145">Filtering files</span></span>

<span data-ttu-id="8b187-p113">Una etiqueta definida por el usuario puede asociarse a un conjunto de archivos para excluirlos del proceso u otras tareas. Cada sesión de proceso está asociada a un identificador de lote. Aunque el identificador del lote no es visible para el experto en relevancia, esto se puede hacer con una herramienta de búsqueda, agregando un filtro para el lote actual y etiquetando todos los archivos apropiados con una etiqueta definida por el usuario.</span><span class="sxs-lookup"><span data-stu-id="8b187-p113">A user-defined label can be associated with a set of files to exclude them from Process or other tasks. Each Process session is associated with a batch ID. Although the batch ID is not visible to the expert in Relevance, this can be done using a search utility, by adding a filter for the current batch and tagging all appropriate files with a user-defined label.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="8b187-149">Vea también</span><span class="sxs-lookup"><span data-stu-id="8b187-149">See also</span></span>

[<span data-ttu-id="8b187-150">eDiscovery avanzado de Office 365</span><span class="sxs-lookup"><span data-stu-id="8b187-150">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="8b187-151">Ejecutar el módulo de proceso y cargar datos</span><span class="sxs-lookup"><span data-stu-id="8b187-151">Running the Process module and loading data</span></span>](run-the-process-module-and-load-data-in-advanced-ediscovery.md)
  
[<span data-ttu-id="8b187-152">Visualización de los resultados del módulo de proceso</span><span class="sxs-lookup"><span data-stu-id="8b187-152">Viewing Process module results</span></span>](view-process-module-results-in-advanced-ediscovery.md)

