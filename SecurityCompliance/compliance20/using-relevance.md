---
title: Utilice el módulo de la relevancia para analizar los datos de exhibición de documentos electrónicos avanzada (vista previa)
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: ''
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: 56e83a1f8a951fd6e14172122a5e86447c6f2ccf
ms.sourcegitcommit: 7e2a0185cadea7f3a6afc5ddc445eac2e1ce22eb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/11/2019
ms.locfileid: "29695176"
---
# <a name="use-the-relevance-module-to-analyze-data-in-advanced-ediscovery-preview"></a>Utilice el módulo de la relevancia para analizar los datos de exhibición de documentos electrónicos avanzada (vista previa)

En Avanzadas exhibición de documentos electrónicos (vista previa), el módulo de la relevancia incluye la formación de la relevancia y la revisión de los archivos relacionados con un caso. El flujo de trabajo de la relevancia se muestran y se describen a continuación:
  
![Flujo de trabajo de relevancia](../media/44c67dd2-7a20-40a9-b0ed-784364845c77.gif)
  
- **Ciclos de evaluación y seguimiento de**:
    
  - **Evaluación**: habilita la evaluación temprana basándose en una muestra aleatoria de archivos y usa esta evaluación para aplicar las decisiones para determinar el rendimiento del proceso de codificación predictivo. 
    
  - **Pista**: calcular y mostrar los resultados provisionales de la evaluación mientras supervisaba validez estadística del proceso. 
    
- **Ciclos de formación y seguimiento**
    
  - **Etiqueta**: exhibición de documentos electrónicos avanzada (vista previa) aprende criterios de relevancia específicos de cada problema según revisión iterativa del experto y etiquetas temáticas de archivos individuales.
    
  - **Pista**: calcular y mostrar los resultados provisionales de la formación de relevancia durante la validez estadística del proceso de supervisión. 
    
- **Cálculo por lotes**: los criterios de relevancia acumulados y aprendidos se aplica a la colección de todo el archivo y se genera una puntuación de relevancia para cada archivo.
    
- **Decide**: los resultados del análisis aplicado a las mayúsculas y minúsculas toda se muestra después del cálculo por lotes, y se muestran los datos que se usa para tomar decisiones de revisión del documento.
    
- **Prueba**: los resultados se pueden probar para comprobar la validez y la eficacia del procesamiento de exhibición de documentos electrónicos avanzada (vista previa).

- **Búsqueda**: una vez que se completa el flujo de trabajo de la relevancia, puede usar el resultado como percentil de lectura de un documento para su problema cuando se ejecuta una consulta dentro de su conjunto de trabajo.
    
## <a name="guidelines-for-relevance-training-and-review"></a>Directrices para la formación de la relevancia y revisión

Es una visión general de las directrices de aprendizaje de la relevancia y revisión:
  
- **Errores e incoherencias**: si se realizan las etiquetas temáticas errores durante la formación, volver a los ejemplos de archivo anteriores a corregirlos. Si hay demasiados errores para corregir o no hay una nueva perspectiva de la caja o un problema, deben volver a definir los criterios de la relevancia por el administrador y reinicia el aprendizaje de la relevancia.
    
- **Etiquetado y formación**: 
    
  - Los archivos se deben etiquetar basado en el contenido únicamente. No se considere la posibilidad de metadatos, como custodia, la fecha o la ruta de acceso de archivo. 
    
  - No considere la posibilidad de fecha indicaciones de rango en el texto al etiquetar los archivos.
    
  - No considere la posibilidad de imágenes gráficas incrustadas al etiquetar los archivos.
     
  - Omitir texto aplicadas a la relevancia se quitarán en el contenido del archivo que se muestra en la vista de texto en la relevancia. Si se han definido los valores para omitir el texto después de la relevancia de formación ya ha iniciado, el nuevo texto omitido se aplicarán a los archivos de ejemplo creados desde el punto en el que se definió. La característica de omitir texto debe utilizarse con cautela, como su uso puede reducir el rendimiento de análisis de archivo
    
  - Use la opción **Omitir etiquetado** sólo cuando sea necesario. Exhibición de documentos electrónicos avanzada (vista previa) no entrenamiento basándose en los archivos omitidos. En la evaluación, si es difícil saber si un archivo es relevante, es mejor etiqueta como Relevant (R) o no relevante (n) siempre que sea posible en lugar de seleccionar **Omitir**. Cuando la exhibición de documentos electrónicos avanzada (vista previa) se evalúa como recursos de aprendizaje, se puede, a continuación, ver grado estos tipos de archivos se han procesado.
    
  - Incluso los archivos con una cantidad muy pequeña de texto extraído se deben etiquetar en recursos de aprendizaje como R/NR, en lugar de "Omitir", cuando sea posible. 
    
  - Etiquetas temáticas pueden afectar el clasificador siempre y cuando el archivo se puede leer y se puede etiquetar como R/NR.
    
  - El número de secuencia de archivo en la lista de archivos de ejemplo que se muestra en la ficha **etiqueta** permite al usuario devolver en el orden mostrado original de los archivos. 
    
  - Puede volver a cualquier ejemplo y cambiar el etiquetado de la evaluación y establecer los archivos de recursos de aprendizaje. Al crear el ejemplo siguiente, se aplicarán los cambios.
    
  - Excel detectado archivos en formato PDF que deben trata de la misma como archivos de Excel nativos al etiquetar los archivos.
    
  - En caso de duda sobre el etiquetado de la relevancia de un archivo, consulte a un experto. Etiquetado incorrecto durante el aprendizaje de la relevancia puede dar lugar a pérdida de tiempo más adelante en el proceso y también puede tener un impacto negativo sobre la calidad de los resultados.
    
  - Palabras clave que se han definido en la palabra clave se mostrará listas en los colores para ayudar al usuario a identificar archivos relevantes al etiquetado.
    
- **Cálculo por lotes**: los archivos que se han etiquetado como R/NR por el experto recibirá una puntuación de 0 o 100. Esto se aplica a etiquetar realizados antes de cálculo por lotes. Si el experto había conmutada el problema a inactivo después de cálculo por lotes y había continuado etiquetado este problema, las puntuaciones recién con etiqueta no será 0 y 100, pero en su lugar la puntuación original.
    
- **Problemas y el modo de muestreo**: problemas normalmente están desactivados cuando se complete el trabajo en ellos (formación de relevancia es estable y cálculo por lotes se llevó a cabo), cuando se cancelan los problemas o cuando otro usuario está trabajando en los problemas.
    
## <a name="steps-in-relevance-training"></a>Pasos de aprendizaje de relevancia

En el **la relevancia \> pista** ficha, exhibición de documentos electrónicos avanzada proporciona recomendaciones sobre cómo proceder en el procesamiento, con los pasos siguientes. A continuación se describen las implicaciones cuando cada uno de los siguientes pasos se recomienda en el proceso de aprendizaje de la relevancia. 
  
- Etiquetas temáticas / Continue etiquetado: revisión de archivo y relevancia etiquetado realizado por un experto para cada archivo y emitir dentro de una muestra.
    
  - Implicación: Debe etiquetar un ejemplo existente.
    
- Evaluación / Continue evaluación: permite la validación anticipada de la relevancia de mayúsculas y minúsculas del problema y una vista preliminar de la relevancia de la población de archivo importada para el caso de actual.
    
  - Implicación: Evaluación más es necesario o recomendado.
    
- Recursos de aprendizaje / Continue aprendizaje: proceso durante qué avanzadas aprende exhibición de documentos electrónicos desde el experto que es etiquetar el archivo de ejemplos y adquiere la capacidad para identificar los criterios de relevancia pertinentes a cada problema dentro del contexto de cada caso.
    
  - Implicación: El problema necesita más recursos de formación; el ejemplo siguiente se debe crearse y etiquetado. 
    
- Cálculo de lotes: proceso de relevancia en qué opciones avanzadas exhibición de documentos electrónicos toma la información obtenida durante la fase de aprendizaje y aplica a la población de todo el archivo. Todos los archivos en el grupo de archivos pertinente se evalúan para la relevancia y asigna una puntuación de relevancia.
    
  - Implicación: El problema se estable y se puede realizar el cálculo por lotes.
    
- Ponerse al día: La relevancia indica cuándo con un experto revisa y un ejemplo de los archivos seleccionados desde un archivo adicional de carga durante un escenario de carga sucesivas de etiquetas.
    
  - Implicación: Se ha agregado una nueva carga y ponerse al día es necesario para continuar trabajando.
    
- Marcar incoherencias: proceso identifica a través de un algoritmo de exhibición de documentos electrónicos avanzadas, incoherencias en el archivo etiquetado proceso que puede afectar negativamente el análisis.
    
  - Implicación: En el ejemplo siguiente se incluye los archivos que se han etiquetado en los ejemplos anteriores, y se pueden repetir su etiquetado.
    
- Actualizar clasificador: permite al usuario aplicar cambios de inicialización o etiquetado.
    
  - Implicación: Etiquetado e inicialización cambios pueden aplicarse sin necesidad de realizar otro ejemplo de la relevancia de forma manual.
    
- En espera: se complete el proceso de aprendizaje de la relevancia.
    
  - Implicación: No hay recursos de aprendizaje de la relevancia es necesaria en ese momento.
    
Aunque avanzada exhibición de documentos electrónicos le guiará por el proceso, con recomienda seguir estos pasos en distintas etapas, también permite desplazarse por las fichas y páginas, así como a tomar decisiones a situaciones de dirección que pueden ser adecuadas para su caso individual, problema, o proceso de revisión de documentos. 
  
Es posible aceptar o reemplazar el paso siguiente de exhibición de documentos electrónicos avanzadas opciones de procesamiento. Si desea realizar un paso que no sea el próximo paso recomendado, haga clic en el **siguiente paso** que aparecen en la pantalla de problema expandida en el cuadro de diálogo, haga clic en el botón **Modificar** junto al paso siguiente y seleccione otra opción de paso siguiente. 
  
> [!NOTE]
> Algunas de las opciones pueden permanecer deshabilitadas después de desbloquear como no son compatibles para su uso en ese momento en el proceso. 
  
## <a name="more-information"></a>Más información

[Evaluación de descripción en la relevancia](../assessment-in-relevance-in-advanced-ediscovery.md)
  
[Etiquetas temáticas y evaluación](../tagging-and-assessment-in-advanced-ediscovery.md)
  
[Etiquetado y formación de relevancia](../tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[Análisis de la relevancia de seguimiento](../track-relevance-analysis-in-advanced-ediscovery.md)
  
[Decidir en función de los resultados](../decision-based-on-the-results-in-advanced-ediscovery.md)
  
[Las pruebas de análisis de la relevancia](../test-relevance-analysis-in-advanced-ediscovery.md)

[Realizar consultas en el conjunto de trabajo](working-set-search.md)
