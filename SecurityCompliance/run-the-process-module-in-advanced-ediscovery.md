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
# <a name="run-the-process-module-in-office-365-advanced-ediscovery"></a>Ejecutar el módulo de proceso en eDiscovery avanzado de Office 365

Archivos de casos se cargan en la exhibición de documentos electrónicos avanzada durante la **preparación** \> **proceso**. 
  
> [!NOTE]
> Exhibición de documentos electrónicos avanzada requiere un E3 de Office 365 con el complemento de cumplimiento avanzadas o una suscripción E5 para su organización. Si no tiene ese plan y desea probar avanzada exhibición de documentos electrónicos, puede [registrarse y obtener una versión de prueba de Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279). 
  
## <a name="guidelines-preparing-data-for-advanced-ediscovery"></a>Instrucciones: Preparar datos para la exhibición de documentos electrónicos avanzada

- **Calidad**: identificar claramente la población de mayúsculas y minúsculas archivo pertinente para el caso.
    
- **Cargas**: cargar los archivos en una ubicación que sea accesible a avanzada exhibición de documentos electrónicos.
    
- **Identificador de archivo**: un identificador de archivo único en la exhibición de documentos electrónicos avanzada. Si no se importa ningún identificador de archivo, exhibición de documentos electrónicos avanzada genera automáticamente el identificador. Si asignar el identificador de una carga de proceso posterior y asignar una ruta diferente a en la carga del proceso inicial, exhibición de documentos electrónicos avanzada va a reemplazar la ruta de acceso (en lugar de agregar una nueva entrada de archivo). El identificador se puede usar como una referencia en el proceso de exportación. El valor del identificador no debe ser "-1".
    
- **MD5**: esta firma se usa para diferenciar entre archivos (dos archivos no se consideran duplicados exactos a menos que tengan el mismo MD5). De forma predeterminada, exhibición de documentos electrónicos avanzada calcula el MD5 de archivos. Cuando los archivos cargados son archivos de texto, se recomienda para cargar y asignar el valor original de MD5 en lugar de calcular en la exhibición de documentos electrónicos avanzada.
    
- **Nombre y tipo de archivo**:
    
  - Exhibición de documentos electrónicos avanzada puede procesar archivos de varios formatos y extraer archivos nativos cargados en un formato estándar, como \*. TXT, HTML, o. XML. procesamiento de archivos de texto es más rápido que los archivos nativos. Archivos de texto extraídos se almacenan en la carpeta de mayúsculas y minúsculas.
    
  - No se cargan los archivos que no se pueden extraer, como los archivos del sistema o imágenes gráficas. Estos archivos pueden retrasar el procesamiento.
    
  - Compruebe que los nombres de archivo se denominan significativamente y rutas de acceso son correctos.
    
- **Ruta de acceso de archivo**: exhibición de documentos electrónicos avanzada puede cargar archivos con longitudes de ruta de acceso hasta 400 caracteres.
    
- **Extracción de texto**: al extraer texto de archivos nativos, además de texto normal, también se extraen los siguientes: columnas de texto oculto (Excel y .doc), oculto (Excel), control de cambios (.doc), objetos de notes (.ppt), incrustados de altavoz (por ejemplo, Objetos de Excel en un .ppt). Estos se pueden ver en el editor de texto.
    
- **Omitir texto**: esta característica opcional se define una vez que se ejecuta el proceso y antes de analizar. Omitir texto debe usarse con precaución debido a que su uso puede reducir el rendimiento de análisis del archivo.
    
- **Texto multilingüe**: exhibición de documentos electrónicos avanzada no procesa actualmente multilingües nombres para las etiquetas, custodia y problemas.
    
- **Metadatos**: determinar si hay metadatos que desea guardar en la base de datos de caso para futuras referencias, como el intervalo de fechas, el tamaño de archivo, el tipo de archivo, custodia y asunto. Después de que los archivos ya se han cargado sin volver a ejecutar el inventario o agregar el reprocesamiento de sobrecarga, se pueden cargar metadatos. 
    
  - Si los archivos se han cargado originalmente por la ruta de acceso, asigne la columna de ruta de acceso al importar los metadatos más adelante. Es posible hacer referencia al archivo por identificador y para asignar una ruta de acceso diferente. Éste es un escenario útil cuando cambian las rutas de acceso de archivo.
    
  - Si los archivos se han cargado originalmente por identificador de archivo, asigne la columna de identificador al cargar metadatos. Hace referencia al archivo mediante la ruta de acceso (en lugar de identificador) hará que los archivos que se va a volver a cargar con un ID diferente. Exhibición de documentos electrónicos avanzada crea copias de los archivos en su lugar que carga los metadatos de los archivos existentes.
    
- **Familias**: no es posible cargar una familia sin su elemento primario (cabeza de familia). 
    
- **Tamaño de archivo**: no hay ninguna limitación en el tamaño de archivos cargados a avanzada exhibición de documentos electrónicos. Para el análisis (analizar, la relevancia, etc.), el límite es es de 5.242.880 caracteres de texto extraído. Se omiten los archivos de mayor tamaño (por ejemplo, en la relevancia, los archivos no participan en el proceso de aprendizaje de la relevancia y no reciben una puntuación de relevancia después del cálculo por lotes).
    
- **Cantidad de archivo**: no hay ningún límite en el número de archivos que se pueden controlar en un único caso recomendado. Rendimiento depende de los recursos del sistema. 
    
## <a name="filtering-files"></a>Filtrado de archivos

Una etiqueta definida por el usuario puede asociarse con un conjunto de archivos que se excluirán proceso u otras tareas. Cada sesión de proceso está asociado con un ID de lote. Aunque no es visible para el experto en la relevancia el ID de lote, esto puede realizarse mediante una utilidad de búsqueda, mediante la adición de un filtro para el lote actual y etiquetar todos los archivos adecuados con una etiqueta definida por el usuario. 
  
## <a name="see-also"></a>Vea también

[eDiscovery avanzado de Office 365](office-365-advanced-ediscovery.md)
  
[Ejecute el módulo de proceso y carga de datos](run-the-process-module-and-load-data-in-advanced-ediscovery.md)
  
[Ver los resultados del módulo de proceso](view-process-module-results-in-advanced-ediscovery.md)

