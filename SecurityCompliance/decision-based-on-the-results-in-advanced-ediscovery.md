---
title: Decisión según los resultados en eDiscovery avanzado de Office 365
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
ms.assetid: aed65bcd-0a4f-43e9-b5e5-b98cc376bdf8
description: 'Obtenga información sobre cómo la pestaña decidir en Office 365 Advanced eDiscovery proporciona datos que pueden ayudarle a determinar el tamaño correcto del conjunto de revisión de los archivos de casos. '
ms.openlocfilehash: c4767e703d03ef5dbdb808332e873d22094d7bca
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/23/2019
ms.locfileid: "30216110"
---
# <a name="decision-based-on-the-results-in-office-365-advanced-ediscovery"></a>Decisión según los resultados en eDiscovery avanzado de Office 365

> [!NOTE]
> Para usar eDiscovery avanzado, su organización necesita una suscripción de Office 365 E3 con el complemento Cumplimiento avanzado, o bien una suscripción de E5. Si no tiene ese plan y quiere probar eDiscovery avanzado, puede [registrarse para una prueba de Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279). 
  
 En la exhibición avanzada de documentos electrónicos, la pestaña decidir proporciona información adicional para ver y usar estadísticas de soporte de decisiones para determinar el tamaño del conjunto de revisión de los archivos de casos. 
  
## <a name="using-the-decide-tab"></a>Uso de la pestaña decidir

![Decisión de relevancia](media/f32fed89-f3b5-404a-90c7-ea25d2eb58a9.png)
  
Esta ficha incluye lo siguiente:
  
- **Problema**: desde aquí, puede seleccionar el asunto de interés de la lista. 
    
- **Tasa de revisión-RECALL**: comparación de la revisión avanzada de eDiscovery de acuerdo con los resultados de relevancia. El punto de corte en el gráfico representa el porcentaje de archivos que se van a revisar, asignado a una puntuación de relevancia. Se usa en la fase de prueba de relevancia y como un umbral de exportación para culling. El punto de corte predeterminado, para el número de archivos que se van a revisar, es el punto en el que el equilibrio entre la recuperación y la precisión es óptimo. El punto de corte real debe estar determinado por el usuario en función de los objetivos y del equilibrio de costes (% Review) y el riesgo (% recall). Con el control deslizante, puede ajustar el punto de corte y ver el efecto en el gráfico y los parámetros, al ajustar el porcentaje de archivos relevantes que se van a recuperar y antes de validar una decisión.
    
- **Parámetros**: los parámetros revisión, recuperación, siguiente relevante y costo total son estadísticas calculadas acumuladas relativas a la revisión establecida en relación con la colección para todo el caso. Las definiciones de estos parámetros son las siguientes:
    
    **Revisión**: porcentaje de archivos que se van a revisar en función de este límite. 
    
    **RECALL**: porcentaje de archivos relevantes en el conjunto de revisión. 
    
    **Siguiente relevante**: costo para revisar e identificar un archivo relevante adicional que no se encuentra actualmente en el conjunto de revisión. 
    
    **Costo total**: costo de revisión de este porcentaje de los archivos de casos. La configuración del parámetro costo puede definirla el administrador de casos.
    
- **Distribución por puntuación de relevancia**: los archivos en la pantalla gris oscuro a la izquierda están por debajo de la puntuación límite. Una información sobre herramientas muestra la puntuación de relevancia y el porcentaje relacionado de los archivos en el archivo de revisión establecido en relación con el total de archivos.
    
El panel de detalles expandido muestra detalles adicionales. Los archivos de las figuras de la colección no incluyen archivos vacíos o Nebulous. Las figuras de los archivos de familia representan los archivos que no se cargan en relevancia, aunque todavía se cuentan como parte de la familia.
  
## <a name="see-also"></a>Vea también

[eDiscovery avanzado de Office 365](office-365-advanced-ediscovery.md)
  
[Descripción de la evaluación en relevancia](assessment-in-relevance-in-advanced-ediscovery.md)
  
[Etiquetado y evaluación](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[Realizar entrenamiento de relevancia](tagging-and-assessment-in-advanced-ediscovery.md)
  
[Seguimiento del análisis de relevancia](track-relevance-analysis-in-advanced-ediscovery.md)
  
[Prueba del análisis de relevancia](test-relevance-analysis-in-advanced-ediscovery.md)

