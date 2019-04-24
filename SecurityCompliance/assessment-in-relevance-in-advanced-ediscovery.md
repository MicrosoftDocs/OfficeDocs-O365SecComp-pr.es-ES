---
title: Descripción de la evaluación en relevancia en Office 365 Advanced eDiscovery
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 9/14/2017
ms.audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 1d33d4fb-91ed-41c0-b72e-5a26eca3a2a7
description: Obtenga información general sobre la fase de evaluación y su rol a la hora de determinar la riqueza de los problemas durante la formación de relevancia en la exhibición avanzada de documentos electrónicos de Office 365.
ms.openlocfilehash: 1ddaa7ef37f762d7b63bb6c0c51193ff382b8d6b
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32250207"
---
# <a name="understand-assessment-in-relevance-in-office-365-advanced-ediscovery"></a>Descripción de la evaluación en relevancia en Office 365 Advanced eDiscovery

> [!NOTE]
> Para usar eDiscovery avanzado, su organización necesita una suscripción de Office 365 E3 con el complemento Cumplimiento avanzado, o bien una suscripción de E5. Si no tiene ese plan y quiere probar eDiscovery avanzado, puede [registrarse para una prueba de Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279). 
  
La exhibición avanzada de documentos electrónicos permite una evaluación temprana, por ejemplo, para los problemas definidos y los datos importados para un caso. La exhibición avanzada de documentos electrónicos permite al experto tomar decisiones relativas a un enfoque adoptado y aplicarlos al proyecto de revisión del documento.
  
## <a name="understanding-assessment"></a>Descripción de la evaluación

En la evaluación, el experto revisa un conjunto aleatorio de al menos 500 archivos, que se usan para determinar la riqueza de los problemas y para producir estadísticas que reflejen los resultados de la formación. La evaluación se realiza correctamente cuando se encuentran archivos relevantes para llegar a un nivel estadístico que ayude a la relevancia avanzada de eDiscovery a proporcionar estadísticas precisas y a determinar eficazmente el punto de estabilización en el proceso de formación. 
  
Cuanto mayor sea el número de archivos relevantes en el conjunto de evaluación, más precisos serán las estadísticas y la eficacia del algoritmo de estabilidad. El número de archivos relevantes dentro de los archivos de evaluación depende de la riqueza del problema. La riqueza es el porcentaje estimado de los archivos relevantes en el conjunto correspondiente a un problema. Los problemas con la riqueza más alta alcanzarán un número más alto de archivos relevantes más rápido que los problemas con la riqueza menor. Los problemas con la riqueza extremadamente baja (por ejemplo, un 2% o menos) requerirán un conjunto de evaluación muy grande para llegar a un número significativo de archivos relevantes.
  
Las estadísticas, que se presentan en las pestañas realizar seguimiento y decidir durante la formación y después del cálculo por lotes, incluyen los cálculos de la recuperación de los distintos conjuntos de revisión. En las estadísticas, las estimaciones basadas en un conjunto de muestra (en este caso, los archivos de evaluación) incluyen el margen de error y el nivel de confianza de ese margen de error. Por ejemplo, una recuperación de 80% estimada puede tener un margen de error de más o menos un 5% con un nivel de confianza de 95%. Esto significa que la recuperación estimada es en realidad del 75%-85% y esta estimación tiene un 95% de confianza. Cuanto mayor sea el conjunto de evaluación, el margen de error será más pequeño y las estadísticas serán más exactas. 
  
Una vez que el experto revisa un conjunto de evaluación inicial de 500 archivos, la relevancia puede determinar el margen actual de error de los valores de recuperación. Relevancia también establecerá un margen de error predeterminado que recomienda alcanzar para optimizar el conjunto de evaluación. A continuación se muestran algunos ejemplos:
  
- Si el conjunto de evaluación ya ha dado como resultado un margen de error de más o menos el 10%, la relevancia le recomendará pasar a la capacitación (no es necesaria ninguna revisión de evaluación adicional). 
    
- Si el conjunto de evaluación produjo un margen de error de más o menos el 13%, la relevancia puede recomendar la revisión de otro conjunto de archivos de evaluación para alcanzar un margen más pequeño. 
    
- Si la riqueza es extremadamente baja, la relevancia podría recomendar la detención de la evaluación, aunque el margen de error sea grande (lo que no resulta práctico), ya que el conjunto de evaluación necesario para alcanzar un margen de error útil es demasiado grande.
    
Cada problema tiene su propia riqueza, el margen actual de error y, como resultado, el número estimado de archivos de evaluación adicionales. El siguiente conjunto de evaluación se crea de acuerdo con el número máximo de archivos (hasta 1.000 en un único conjunto).
  
Puede aceptar las recomendaciones de relevancia o ajustar el margen de error actual de acuerdo con sus necesidades. El margen actual predeterminado del error se determina para la recuperación como igual o superior al 75%.
  
> [!NOTE]
> La fase de evaluación se puede omitir, en la pestaña **seguimiento de relevancia \> ** de la vista expandida para un problema, desactivando la casilla de verificación **evaluación** por problema y, a continuación, "todos los problemas". Sin embargo, como resultado, no habrá estadísticas para este problema. > desactivar la casilla de verificación **evaluación** solo puede realizarse antes de que se realice la evaluación. Cuando hay varios problemas en un caso, la evaluación se omite solo si la casilla de verificación está desactivada para cada problema 
  
## <a name="see-also"></a>Vea también

[eDiscovery avanzado de Office 365](office-365-advanced-ediscovery.md)
  
[Etiquetado y evaluación](tagging-and-assessment-in-advanced-ediscovery.md)
  
[Aprendizaje de etiquetas y relevancia](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[Seguimiento del análisis de relevancia](track-relevance-analysis-in-advanced-ediscovery.md)
  
[Decisiones basadas en los resultados](decision-based-on-the-results-in-advanced-ediscovery.md)
  
[Prueba del análisis de relevancia](test-relevance-analysis-in-advanced-ediscovery.md)

