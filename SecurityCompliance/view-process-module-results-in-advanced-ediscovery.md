---
title: Ver resultados del módulo de proceso en eDiscovery avanzado de Office 365
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
ms.assetid: c6f016cb-409f-4ae9-911c-1395cf0c86ea
description: 'Obtenga información sobre cómo encontrar los resultados de un módulo de un proceso que se ejecutan en Office 365 avanzada exhibición de documentos electrónicos, incluidos el estado de la tarea y el proceso de resumen.  '
ms.openlocfilehash: 01093b0230aaf78ab7ccf1235f0874a0b69aa1bd
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22535611"
---
# <a name="view-process-module-results-in-office-365-advanced-ediscovery"></a>Ver resultados del módulo de proceso en eDiscovery avanzado de Office 365

Después de **Preparar** \> se inicia el **proceso** , puede ver el progreso y los resultados. 
  
> [!NOTE]
> Exhibición de documentos electrónicos avanzada requiere un E3 de Office 365 con el complemento de cumplimiento avanzadas o una suscripción E5 para su organización. Si no tiene ese plan y desea probar avanzada exhibición de documentos electrónicos, puede [registrarse y obtener una versión de prueba de Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279). 
  
## <a name="process-task-status"></a>Estado de la tarea de proceso

En **Prepare** \> **proceso** \> **los resultados**, la página muestra el estado actual (si el proceso se está ejecutando actualmente) o el último estado de tarea de estado de proceso tal como se muestra en el siguiente ejemplo.
  
![Estado de la tarea del módulo de proceso](media/9430f9e7-a4dd-47c7-ac2e-2c6a60fc948b.png)
  
Las tareas que se muestra pueden variar según las opciones de proceso seleccionadas. 
  
- **Inventario**: exhibición de documentos electrónicos avanzada recorre en iteración todos los archivos seleccionados para el proceso y realiza la recolección de datos básica.
    
- **Las firmas de calcular**: calcula las firmas digitales de MD5.
    
- **Extracción de compuestos**: extractos internos o contiene los archivos de forma recursiva de archivos compuestos (por ejemplo, PST, ZIP, MSG). Los archivos extraídos se almacenan en la carpeta de mayúsculas y minúsculas de las mayúsculas y minúsculas.
    
- **Base de datos de sincronización**: proceso de base de datos interna.
    
- **Copia de archivos**: proceso de copias de archivos. Siempre se muestra esta tarea, incluso cuando se selecciona la opción avanzada de los archivos de copia.
    
- **Extracción de texto**: cuando hay archivos nativos, exhibición de documentos electrónicos avanzada extrae el texto de estos archivos mediante DTSearch. El texto extraído de estos archivos se almacena como archivos de texto en la carpeta de mayúsculas y minúsculas.
    
- **Actualizar los metadatos**: procesa los metadatos cargados. 
    
- **Finalizing**: procesamiento interno que finaliza los datos de carga archivos de casos (por ejemplo, identificar los archivos de error y éxito). 
    
Estado de la tarea: muestra una vez finalizada la tarea. Mientras se ejecutan las tareas, se muestra la duración de ejecución.
  
> [!NOTE]
> Las tareas completadas también pueden incluir los totales de los archivos que se completó el procesamiento o con errores. 
  
> [!TIP]
> "Cancelar" proporciona una opción de reversión para detener la ejecución del proceso y, a continuación, revertir a la población de datos anterior o guarda datos procesados. Reversión borra procesados todos los datos. Si no desea que los datos procesados se pierdan (por ejemplo, plan para volver a cargar estos archivos), seleccione la "Cancelar" opción en esta ventana Elegir no revertir. 
  
## <a name="process-summary"></a>Resumen del proceso

En Prepare \> proceso \> los resultados \> proceso de resumen, se muestra un desglose de los resultados del archivo cargado según los resultados de procesamiento y error correcta de los archivos.
  
Los paneles de presentan una representación gráfica de las estadísticas de archivo importado, como se indica a continuación:
  
- **Proceso de resumen se acumulan**d: en el caso de todos los archivos.
    
- **Resumen del proceso por última vez**: los archivos que se cargan desde la última sesión o acción. 
    
- **Familias por última vez**: información de la familia en el caso (si hay alguno).
    
- Si se han agregado los archivos de **inicialización** , aparece el número de archivos de inicialización por el problema que se ha definido para los archivos. 
    
    Si el marcado de los archivos de **inicialización** no se pudo, que también se ha indicado. 
    
- Si se agregaron archivos **previamente con etiqueta** , aparece el número de archivos con previa a la etiqueta por el problema que se ha definido para los archivos. 
    
    Si el marcado de los archivos **etiquetados previamente** no se pudo, que también se ha indicado. 
    
![Resumen del módulo de proceso](media/2086a691-9e3d-4117-beb2-a5c3a9a4cc94.png)
  
## <a name="process-summary-accumulated-and-last-charts"></a>Resumen del proceso de acumulado y por última vez los gráficos

La barra izquierda incluye origen + archivos extraídos: que es todos los archivos que se encuentra. 
  
El derecho de la barra, procesada, incluye:
  
- Archivos con errores de carga
    
- Archivos cargados correctamente, que pueden incluir: 
    
  - **Existente**: los archivos que se cargaron antes y ahora se cargan nuevo (incluidos los duplicados).
    
  - **Texto**: archivos únicos con texto.
    
  - **No texto**: vaciar archivos de texto, archivos de texto nativa vacía, los archivos que no son de texto nativos. 
    
  - **Duplicar**s: duplicado archivos con texto.
    
## <a name="last-process-errors"></a>Última errores de proceso

En Prepare \> proceso \> los resultados \> se muestran errores de proceso última, detalles de los errores en la última sesión o acción realizada.
  
![Errores del módulo de proceso](media/4771d0f4-4217-445a-9ba4-8b6541c5ad09.png)
  
## <a name="see-also"></a>Vea también

[eDiscovery avanzado de Office 365](office-365-advanced-ediscovery.md)
  
[Ejecute el módulo de proceso y carga de datos](run-the-process-module-and-load-data-in-advanced-ediscovery.md)

