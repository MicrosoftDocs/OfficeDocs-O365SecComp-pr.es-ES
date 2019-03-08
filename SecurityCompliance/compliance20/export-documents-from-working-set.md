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
# <a name="export-documents-from-a-working-set"></a>Exportar documentos desde un conjunto de trabajo

La exportación de contenido de un conjunto de trabajo puede realizarse a través de tres métodos diferentes:

## <a name="download"></a>Descargar

La descarga ofrece una forma sencilla de descargar contenido de un conjunto de trabajo en formato nativo. Aprovecha las características de transferencia de datos del explorador para que aparezca un mensaje del explorador una vez que la descarga esté lista. Los archivos descargados con este método se comprimen en un archivo contenedor y serán archivos de nivel de elemento. Esto significa que, si selecciona un archivo adjunto, recibirá automáticamente el correo electrónico con los datos adjuntos incluidos. De forma similar, si selecciona una hoja de cálculo de Excel que estaba incrustada en un documento de Word, recibirá el documento de Word con la hoja de cálculo de Excel incrustada. Los elementos desCargados conservarán la fecha de la última modificación, que se puede ver como una propiedad de archivo.

Para descargar contenido de un conjunto de trabajo, seleccione los archivos que desea descargar y, a continuación, seleccione "Descargar" en el menú acciones.

![Una captura de pantalla de una descripción de equipo generada automáticamente](../media/eDiscoDownload.png)

## <a name="export"></a>Exportar

La exportación permite a los usuarios personalizar el contenido que se incluye en el paquete de descarga. Proporciona una página de configuración con la siguiente configuración:

### <a name="metadata-file"></a>Archivo de metaDatos

> Esto puede considerarse el "Cargar archivo" que contiene metadatos asociados con los archivos exportados. Para obtener una lista de los campos disponibles en el archivo de \[metadatos, vea Link\]. Por lo general, este archivo puede ser incorporado por las herramientas de terceros de terceras partes.<sup></sup>

### <a name="tag-data"></a>Datos de etiqueta

> Este contenido se agregaría como campos en el archivo de metadatos. Contiene toda la información de etiqueta aplicada en los conjuntos de trabajo.

### <a name="text-files"></a>Archivos de texto

> Los archivos de texto se pueden generar para cada archivo exportado de un conjunto de trabajo. A menudo, los asociados de servicio necesitan estos archivos como parte de la recopilación de datos<sup></sup> en herramientas de terceros de terceros.

### <a name="redacted-files"></a>Archivos censurados

> Si se generan documentos PDF censurados durante la revisión, estos archivos están disponibles durante la exportación. Los usuarios pueden decidir si desea exportar solo los archivos nativos o reemplazar los nativos que tienen redacciones con el grabado en documentos PDF.

### <a name="export-location"></a>Ubicación de exportación

> El contenido exPortado se entrega en un BLOB de Azure o el BLOB de un cliente de Microsoft se puede usar si los detalles se proporcionan en la exportación.

## <a name="export-structure"></a>Exportar estructura

Cuando se exporta contenido desde un conjunto de trabajo, el contenido se organiza en la siguiente estructura.

  - Carpeta raíz: identificador de descarga
    
      - Exportar\_archivo\_de carga. csv = archivo de metadatos
    
      - Summary. txt = un archivo de resumen con las estadísticas de exportación
    
      - Archivos\_nativos\_o de entrada = contiene todos los archivos nativos
    
      - Archivos\_de errores = contiene los archivos de error incluidos en la exportación
        
          - ExtractionError: un CSV que contiene los metadatos disponibles de los archivos que no se han extraído correctamente de los archivos principales
        
          - ProcessingError: contenido con errores de procesamiento. Este contenido es el significado del nivel de elemento si los datos adjuntos experimentan un error de procesamiento, el correo electrónico que contiene los datos adjuntos se incluirá en esta carpeta.
    
      - Archivos\_de\_texto extraídos = contiene todos los archivos de texto extraídos generados en el procesamiento.

## <a name="working-set"></a>Espacio de trabajo

El contenido se puede Agregar a otro conjunto de trabajo.