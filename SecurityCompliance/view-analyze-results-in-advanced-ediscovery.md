---
title: Ver los resultados de ANALYZE en Office 365 Advanced eDiscovery
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 9/14/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 5974f3c2-89fe-4c5f-ac7b-57f214437f7e
description: 'Comprenda dónde ver los resultados del proceso de análisis en la exhibición avanzada de documentos electrónicos de Office 365, incluidas las definiciones de las opciones de tarea mostradas.  '
ms.openlocfilehash: 092daa506316b5eb1ef1f5c466055b29e350dc18
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/17/2019
ms.locfileid: "34157862"
---
# <a name="view-analyze-results-in-office-365-advanced-ediscovery"></a>Ver los resultados de ANALYZE en Office 365 Advanced eDiscovery

> [!NOTE]
> Para usar eDiscovery avanzado, su organización necesita una suscripción de Office 365 E3 con el complemento Cumplimiento avanzado, o bien una suscripción de E5. Si no tiene ese plan y quiere probar eDiscovery avanzado, puede [registrarse para una prueba de Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279). 
  
En la exhibición avanzada de documentos electrónicos, el progreso y los resultados del proceso de análisis se pueden ver en varias pantallas, como se describe a continuación.
  
## <a name="view-analyze-task-status"></a>Ver el estado de la tarea de análisis

En **preparar \> el \> estado \> **de la tarea de resultados del análisis, el estado se muestra durante y después de analizar la ejecución del proceso. 
  
![Analizar el estado de la tarea](media/d0372978-ce08-4f4e-a1fc-aa918ae44364.png)
  
Las tareas mostradas pueden variar en función de las opciones seleccionadas. 
  
- **ND/et: Setup**: se prepara para la ejecución, por ejemplo, establece los parámetros Run y case.
    
- **ND/et: ND Calculation**: procesa el análisis de archivos casi duplicados.
    
- **ND-et: et Calculation**: realiza análisis de subprocesos de correo electrónico en todo el conjunto de correo electrónico.
    
- **ND/et: tablas dinámicas y similitudes**: realiza el procesamiento de similitudes de archivos y tablas dinámicas.
    
- **ND/et: metadatos Update**: finaliza los nuevos datos recopilados en los archivos de la base de datos.
    
- **Temas: cálculo de temas**: ejecuta el análisis de temas. (Solo se muestra si está seleccionado).
    
- **Estado**de la tarea: esta línea se muestra después de la finalización de la tarea. Mientras se ejecutan las tareas, se muestra la duración de ejecución.
    
> [!NOTE]
> Los resultados del análisis de casi duplicados y subprocesos de correo electrónico (ND y ED) se aplican al número de documentos que se van a procesar. No incluye los archivos duplicados exactos. 
  
## <a name="view-near-duplicates-and-email-threads-status"></a>Ver el estado de subprocesos Near-duplicados y correo electrónico

Los resultados de la población de **destino** muestran el número de documentos, mensajes de correo electrónico, datos adjuntos y errores en el rellenado de destino. 
  
Los resultados de los **documentos** muestran el número de elementos dinámicos, los únicos casi duplicados y los archivos duplicados exactos. 
  
Los resultados de los **mensajes** de correo electrónico muestran el número de copias inclusivas inclusivas inclusive, únicas y exclusivas, así como el resto de los mensajes de correo electrónico. Los diferentes tipos de resultados de correo electrónico son: 
  
- **Inclusive**: un correo electrónico inclusivo es el nodo de terminación en un hilo de correo electrónico y contiene todo el historial anterior de ese hilo. Como resultado, el revisor puede centrarse de forma segura en el correo electrónico inclusivo, sin necesidad de leer los mensajes anteriores en el hilo. 
    
- **Impuestos incluidos**: un correo electrónico inclusivo se designa como inclusivo menos si hay uno o varios datos adjuntos diferentes asociados con los elementos primarios del mensaje inclusivo. En este contexto, el término "primario" se usa para los mensajes ubicados hacia arriba en la conversación de correo electrónico o conversaciones incluidas en ese correo electrónico específico inclusivo. Un revisor puede usar la indicación de menos inclusivo como una señal que, aunque puede que no sea necesario revisar el contenido de los elementos primarios de correo electrónico inclusivos, puede resultar útil revisar los datos adjuntos asociados a los elementos principales de la ruta de acceso inclusiva. 
    
- **Copia inclusiva**: los correos electrónicos inclusivos se designan como copia inclusiva si es la copia de otro mensaje marcada como un signo menos inclusivo o inclusivo. Es decir, este mensaje tiene el mismo asunto y el mismo cuerpo que otro mensaje inclusivo y, como tal, coexiste en el mismo nodo. Como los mensajes de copia inclusivos contienen el mismo contenido, normalmente se pueden omitir en el proceso de revisión. 
    
- **El resto**: indica el correo electrónico que no contiene ningún contenido único y, por lo tanto, no se incluye en ninguna de las tres categorías anteriores. No es necesario revisar estos mensajes de correo electrónico. Si un mensaje contiene datos adjuntos que no están en un correo electrónico inclusivo posterior, es posible que sea necesario revisar los datos adjuntos. Esto se indica mediante la existencia de un correo electrónico menos inclusivo dentro del hilo.
    
Los resultados de los **datos** adjuntos muestran el número de datos adjuntos, según el tipo único y duplicados. 
  
![Casi duplicados y subprocesos de correo electrónico](media/54491303-0ee3-4739-b42e-d1ee486842fd.png)
  
## <a name="see-also"></a>Vea también

[eDiscovery avanzado de Office 365](office-365-advanced-ediscovery.md)
  
[Descripción de la similitud de documentos](understand-document-similarity-in-advanced-ediscovery.md)
  
[Configuración de las opciones de análisis](set-analyze-options-in-advanced-ediscovery.md)
  
[Configuración de omitir texto](set-ignore-text-in-advanced-ediscovery.md)
  
[Configuración de la configuración avanzada de análisis](view-analyze-results-in-advanced-ediscovery.md)

