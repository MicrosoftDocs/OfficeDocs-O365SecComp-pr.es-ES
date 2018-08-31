---
title: Ver los resultados de análisis en eDiscovery avanzado de Office 365
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
ms.assetid: 5974f3c2-89fe-4c5f-ac7b-57f214437f7e
description: 'Entender dónde ver los resultados del proceso de analizar en Office 365 avanzada exhibición de documentos electrónicos, incluidas las definiciones de las opciones de la tarea que se muestra.  '
ms.openlocfilehash: 8f1de53e5548c8721f8fbfdb83374edb18379114
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22536582"
---
# <a name="view-analyze-results-in-office-365-advanced-ediscovery"></a>Ver los resultados de análisis en eDiscovery avanzado de Office 365

> [!NOTE]
> Exhibición de documentos electrónicos avanzada requiere un E3 de Office 365 con el complemento de cumplimiento avanzadas o una suscripción E5 para su organización. Si no tiene ese plan y desea probar avanzada exhibición de documentos electrónicos, puede [registrarse y obtener una versión de prueba de Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279). 
  
En la exhibición de documentos electrónicos avanzada, progreso y los resultados para el proceso de análisis pueden verse en una variedad de pantallas tal y como se describe a continuación.
  
## <a name="view-analyze-task-status"></a>Ver el estado de la tarea de análisis

En **Prepare \> analizar \> los resultados \> estado de tareas**, se muestra el estado durante y después de la ejecución del proceso de análisis. 
  
![Analizar el estado de la tarea](media/d0372978-ce08-4f4e-a1fc-aa918ae44364.png)
  
Las tareas que se muestra pueden variar según las opciones seleccionadas. 
  
- **ND/ET: el programa de instalación**: prepara para la ejecución, por ejemplo, define los parámetros de ejecución y mayúsculas y minúsculas.
    
- **ND/ET: cálculo ND**: análisis de procesos casi duplicados de archivos.
    
- **ND/ET: cálculo ET**: subprocesos de correo electrónico realiza análisis en el conjunto completo de correo electrónico.
    
- **ND/ET: tablas dinámicas y similitudes**: realiza la tabla dinámica y el procesamiento del archivo de similitud.
    
- **ND/ET: actualización de metadatos**: finaliza los nuevos datos recopilados en los archivos de la base de datos.
    
- **Temas: cálculo de los temas**: se ejecuta el análisis de los temas. (Muestra sólo si ha seleccionado).
    
- **Estado de la tarea**: esta línea se muestra después de la finalización de tareas. Mientras se ejecutan las tareas, se muestra la duración de ejecución.
    
> [!NOTE]
> Los resultados de análisis de cerca de duplicados y subprocesos de correo electrónico (ND y ED) se aplica al número de documentos que va a procesar. No incluye los archivos duplicados exactos. 
  
## <a name="view-near-duplicates-and-email-threads-status"></a>Ver el estado de los subprocesos de correo electrónico y cerca de duplicados

Los resultados de la población de **destino** mostrar el número de documentos, mensajes de correo electrónico, datos adjuntos y errores de la población de destino. 
  
Los resultados de **documentos** mostrarán el número de tablas dinámicas, únicos cerca de duplicados y exacta de los archivos duplicada. 
  
Los resultados de **los correos electrónicos de** mostrarán el número de inclusive menos copias inclusivas únicas, ambos inclusive y el resto de los mensajes de correo electrónico. Los distintos tipos de resultados de correo electrónico son: 
  
- **Incluidos**: un correo electrónico inclusive es el nodo WriteError en un subproceso de correo electrónico y contiene todo el historial anterior de ese subproceso. Como resultado, el revisor con seguridad puede centrarse en el correo electrónico inclusive, sin necesidad de leer los mensajes anteriores en el subproceso. 
    
- **Incluidos menos**: un correo electrónico inclusive se designa como menos inclusive, si hay uno o más diferentes los datos adjuntos asociados con los elementos primarios del mensaje inclusive. En este contexto, el término que primario se usa para los mensajes que se encuentra arriba en el subproceso de correo electrónico o las conversaciones se incluyen en ese correo electrónico inclusive específico. Un revisor puede usar inclusive menos indicación como una señal de que aunque es posible que no sea necesario revisar el contenido de los elementos primarios de correo electrónico inclusive, puede ser útil revisar los datos adjuntos asociados con los elementos primarios de la ruta de acceso en ambos inclusive. 
    
- **Copia inclusive**: un correo electrónico inclusive se designa como copia inclusive si se trata de la copia de otro mensaje marcado como inclusive o inclusive menos. En otras palabras, este mensaje tiene el mismo asunto y el cuerpo como otro mensaje inclusive y, como tal, co-autoría reside en el mismo nodo. Debido a que ambos inclusive copiar los mensajes contienen el mismo contenido, normalmente se omiten en el proceso de revisión. 
    
- **El resto**: Esto indica correo electrónico que no contiene ningún contenido único y, por lo tanto, no se dividen en cualquiera de las tres categorías anteriores. Estos mensajes de correo electrónico no es necesario que se va a revisar. Si un mensaje contiene datos adjuntos que no se encuentra en un correo electrónico inclusive más adelante, a continuación, los datos adjuntos que necesite ser revisado. Esto se indica mediante la existencia de un inclusive menos correo electrónico dentro del subproceso.
    
Los resultados de **los datos adjuntos de** mostrarán el número de datos adjuntos, según esas tipo como únicos y duplicados. 
  
![Casi duplicados y subprocesos de correo electrónico](media/54491303-0ee3-4739-b42e-d1ee486842fd.png)
  
## <a name="see-also"></a>Vea también

[eDiscovery avanzado de Office 365](office-365-advanced-ediscovery.md)
  
[Descripción de la similitud de documento](understand-document-similarity-in-advanced-ediscovery.md)
  
[Configurar las opciones de análisis](set-analyze-options-in-advanced-ediscovery.md)
  
[Configuración de omitir el texto](set-ignore-text-in-advanced-ediscovery.md)
  
[Análisis de la opción Configuración avanzada](view-analyze-results-in-advanced-ediscovery.md)

