---
title: Decisión según los resultados en eDiscovery avanzado de Office 365
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
ms.assetid: aed65bcd-0a4f-43e9-b5e5-b98cc376bdf8
description: 'Obtenga información sobre cómo la ficha Decide de exhibición de documentos electrónicos avanzada de Office 365 ofrece datos que le ayudarán a determinan el tamaño correcto del conjunto de revisión de los archivos de mayúsculas y minúsculas. '
ms.openlocfilehash: 58a181e00ad5843ccbbde4dcb47050eccf199225
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22535911"
---
# <a name="decision-based-on-the-results-in-office-365-advanced-ediscovery"></a>Decisión según los resultados en eDiscovery avanzado de Office 365

> [!NOTE]
> Exhibición de documentos electrónicos avanzada requiere un E3 de Office 365 con el complemento de cumplimiento avanzadas o una suscripción E5 para su organización. Si no tiene ese plan y desea probar avanzada exhibición de documentos electrónicos, puede [registrarse y obtener una versión de prueba de Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279). 
  
 En la exhibición de documentos electrónicos avanzada, la ficha Decide proporciona información adicional para ver y usar las estadísticas de la toma de decisiones para determinar el tamaño del conjunto de revisión de los archivos de mayúsculas y minúsculas. 
  
## <a name="using-the-decide-tab"></a>Mediante la ficha Decide

![Decisión de relevancia](media/f32fed89-f3b5-404a-90c7-ea25d2eb58a9.png)
  
Esta ficha incluye lo siguiente:
  
- **Problema**: desde aquí, puede seleccionar el problema de interés de la lista. 
    
- **Proporción de retirada de revisión**: comparación de avanzada de revisión de exhibición de documentos electrónicos según las puntuaciones de la relevancia. El punto límite del gráfico representa el porcentaje de archivos para revisar, asignados a una puntuación de relevancia. Esto se usa en la fase de prueba de la relevancia y como un umbral de exportación para la selección. Es el punto límite predeterminado, para el número de archivos para revisar en el punto en el que el equilibrio entre la recuperación y la precisión es óptimo. El punto límite real se debe determinar por el usuario según los objetivos y el equilibrio de costo (revisión %) y el riesgo (recuperación %). Con el control deslizante, puede ajustar el punto límite y ver el efecto en el gráfico y los parámetros, al ajustar el porcentaje de los archivos relevantes que se recuperarán y antes de validar una decisión.
    
- **Parámetros**: Revise, recuerde, parámetros relevantes y el coste Total de la siguiente son acumulativas estadísticas calculadas perteneciente a la revisión que se establece en relación a la colección para el caso de todo. Las definiciones de estos parámetros son los siguientes:
    
    **Revisión**: porcentaje de los archivos para revisar basándose en este límite. 
    
    **Recuerde**: porcentaje de los archivos relevantes en el conjunto de revisión. 
    
    **Siguiente relevantes**: costo para revisar e identificar un archivo relevante adicional que no está actualmente en la revisión establecido. 
    
    **Costo total**: costo para revisar este porcentaje de los archivos de mayúsculas y minúsculas. Configuración de los parámetros de costos se puede establecer por el Administrador de mayúsculas y minúsculas.
    
- **Distribución por puntuación de relevancia**: los archivos en la pantalla gris oscuro a la izquierda están por debajo de la puntuación de corte. Una información sobre herramientas muestra la puntuación de relevancia y el porcentaje de archivos relacionado en el archivo de revisión que se establece en relación con el total de archivos.
    
El panel de detalles expandido muestra detalles adicionales. Los archivos en las figuras de la colección no incluya archivos vacíos o imprecisas. Ilustraciones de archivos familia representan los archivos que no se cargados en la relevancia, sin embargo, aún se cuentan como parte de la familia.
  
## <a name="see-also"></a>Vea también

[eDiscovery avanzado de Office 365](office-365-advanced-ediscovery.md)
  
[Evaluación de descripción en la relevancia](assessment-in-relevance-in-advanced-ediscovery.md)
  
[Etiquetas temáticas y evaluación](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[Realización de aprendizaje de relevancia](tagging-and-assessment-in-advanced-ediscovery.md)
  
[Análisis de la relevancia de seguimiento](track-relevance-analysis-in-advanced-ediscovery.md)
  
[Las pruebas de análisis de la relevancia](test-relevance-analysis-in-advanced-ediscovery.md)

