---
title: Comprender la evaluación de relevancia en eDiscovery avanzado de Office 365
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 9/14/2017
ms.audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 1d33d4fb-91ed-41c0-b72e-5a26eca3a2a7
description: 'Obtenga una visión general de la fase de evaluación y su función en la determinación de la flexibilidad de problemas durante la formación de la relevancia en la exhibición de documentos electrónicos avanzada de Office 365.  '
ms.openlocfilehash: a54a4134609b16568586f3cb6b60ebdeba860bac
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22536206"
---
# <a name="understand-assessment-in-relevance-in-office-365-advanced-ediscovery"></a>Comprender la evaluación de relevancia en eDiscovery avanzado de Office 365

> [!NOTE]
> Exhibición de documentos electrónicos avanzada requiere un E3 de Office 365 con el complemento de cumplimiento avanzadas o una suscripción E5 para su organización. Si no tiene ese plan y desea probar avanzada exhibición de documentos electrónicos, puede [registrarse y obtener una versión de prueba de Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279). 
  
Exhibición de documentos electrónicos avanzada permite evaluación temprana, por ejemplo, para los problemas definidos y los datos importados para un caso. Exhibición de documentos electrónicos avanzada permite el experto para tomar decisiones relativas a un enfoque adoptado y para aplicarlos al proyecto de revisión de documentos.
  
## <a name="understanding-assessment"></a>Evaluación de descripción

En la evaluación, el experto revisa un conjunto aleatorio de al menos 500 archivos, que se utilizan para determinar la flexibilidad de los problemas y para producir estadísticas que reflejan los resultados de aprendizaje. Evaluación es correcta cuando se encuentran suficientes archivos relevantes para alcanzar un nivel estadístico que le ayudarán a la exhibición de documentos electrónicos avanzada la relevancia para proporcionar estadísticas precisas y para determinar el punto de estabilización en el proceso de aprendizaje de forma eficaz. 
  
Cuanto mayor sea que el número de relevantes archivos en el conjunto de evaluación, más preciso las estadísticas y la eficacia del algoritmo de estabilidad. El número de archivos relevantes dentro de los archivos de evaluación depende de la flexibilidad del problema. Flexibilidad es el porcentaje estimado de los archivos relevantes en el conjunto de relevante para un problema. Problemas con mayor flexibilidad va a llegar a un número mayor de archivos relevantes más rápidamente que problemas con flexibilidad inferior. Problemas con flexibilidad extremadamente baja (por ejemplo, un 2% o menos) requerirá una evaluación muy grande establecida para alcanzar un gran número de archivos relevantes.
  
Las estadísticas, que se presentan en las fichas pista y Decide durante el entrenamiento y después del cálculo de lote, incluyen estimaciones de recuperación de conjuntos de revisión distinto. En estadísticas, establecen las estimaciones que se basan en una muestra (en este caso, los archivos de evaluación) incluyen el margen de error y el nivel de confianza de ese margen de error. Por ejemplo, la recuperación estimada de 80% puede tener un margen de error de más o menos el 5% con un nivel de confianza del 95%. Esto significa que la recuperación estimada es realmente 75-85% y esta estimación tiene confianza del 95%. Cuanto mayor sea el conjunto de evaluación, el margen de error pasa a ser más pequeño y las estadísticas son más precisas. 
  
Después de que el experto revisa un conjunto de evaluación inicial de los archivos de 500, la relevancia es capaz de determinar el margen de error de los valores de recuperación actual. La relevancia también establecerá un margen de error que recomienda para llegar a fin de optimizar el conjunto de evaluación predeterminado. Estos son algunos ejemplos:
  
- Si la evaluación ya establecida generaron un margen de error de más o menos un 10%, se recomienda la relevancia para pasar a recursos de aprendizaje (revisión de evaluación adicionales no es necesario). 
    
- Si el conjunto de evaluación produjo un margen de error de más o menos el 13%, la relevancia es posible que recomienda la revisión de otro conjunto de archivos de evaluación ponerse en contacto con un margen más pequeño. 
    
- Si flexibilidad es muy bajo, la relevancia es posible que recomienda detener evaluación, aunque el margen de error es grande (realizar estadísticas práctico), debido a que el conjunto de evaluación sea necesario ponerse en contacto con un margen de error útil es demasiado grande.
    
Cada problema tiene su propia flexibilidad, el actual margen de error y, como resultado, número estimado de archivos de evaluación adicionales. Se crea el siguiente conjunto de evaluación según el número máximo de archivos (hasta 1.000 en un conjunto único).
  
Puede aceptar las recomendaciones de la relevancia o ajustar el margen de error actual según sus necesidades. Se determina el margen de error actual de predeterminado para la recuperación a igual o superior al 75%.
  
> [!NOTE]
> Se puede omitir la fase de evaluación, en la **la relevancia \> pista** ficha en la vista expandida para un problema, desactivando la casilla de verificación **evaluación** por el problema y, a continuación, para "todos los problemas". Sin embargo, como resultado, habrá ningún estadísticas para este problema. > Desactivando la casilla de verificación de **evaluación** sólo puede realizarse antes de realiza la evaluación. Cuando hay varios problemas en un caso, se omitirá el evaluación sólo si la casilla de verificación está desactivada por cada problema 
  
## <a name="see-also"></a>Vea también

[eDiscovery avanzado de Office 365](office-365-advanced-ediscovery.md)
  
[Etiquetas temáticas y evaluación](tagging-and-assessment-in-advanced-ediscovery.md)
  
[Etiquetado y formación de relevancia](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[Análisis de la relevancia de seguimiento](track-relevance-analysis-in-advanced-ediscovery.md)
  
[Decidir en función de los resultados](decision-based-on-the-results-in-advanced-ediscovery.md)
  
[Las pruebas de análisis de la relevancia](test-relevance-analysis-in-advanced-ediscovery.md)

