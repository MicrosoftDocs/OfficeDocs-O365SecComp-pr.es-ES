---
title: Usar el módulo relevancia para analizar datos en evidencias
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
ms.openlocfilehash: 3aa37a6778947934759eb652a9367559b9ef838b
ms.sourcegitcommit: 2c5834235c32b2616e1813ce24eeb3419a09629f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "31030536"
---
# <a name="use-the-relevance-module-to-analyze-data-in-evidence"></a>Usar el módulo relevancia para analizar datos en evidencias

En las investigaciones de datos (versión preliminar), el módulo de relevancia incluye el entrenamiento de relevancia y la revisión de los archivos relacionados con una investigación. El flujo de trabajo de relevancia se muestra y se describe de la siguiente manera:
  
![Flujo de trabajo de relevancia](../media/44c67dd2-7a20-40a9-b0ed-784364845c77.gif)
  
- **Ciclos de evaluación y seguimiento**:
    
  - **Evaluación**: permite realizar evaluaciones tempranas basándose en un ejemplo aleatorio de archivos y usa esta evaluación para aplicar decisiones para determinar el rendimiento del proceso de codificación predictivo. 
    
  - **Track**: calcule y muestre los resultados temporales de la evaluación mientras supervisa la validez estadística del proceso. 
    
- **Ciclos de formación y seguimiento**
    
  - **Tag**: Data investigaciones (versión preliminar) aprende los criterios de relevancia específicos de cada problema en función de la revisión iterativa del experto y el etiquetado de archivos individuales.
    
  - **Track**: calcule y muestre los resultados temporales de la formación de relevancia mientras supervisa la validez estadística del proceso. 
    
- **Cálculo del lote**: los criterios de relevancia acumulados y adquiridos se aplican a toda la colección de archivos y se genera una puntuación de relevancia para cada archivo.
    
- **Decida**: los resultados del análisis aplicado a todo el caso se muestran tras el cálculo del lote y se muestran los datos usados para realizar las decisiones de revisión del documento.
    
- **Prueba**: se pueden probar los resultados para comprobar la validez y la eficacia del procesamiento de las investigaciones de datos (vista previa).

- **Buscar**: una vez que se ha completado el flujo de trabajo de relevancia, puede usar el resultado como, por ejemplo, el percentil de lectura de un documento para su problema al ejecutar una consulta en el conjunto de trabajo.
    
## <a name="guidelines-for-relevance-training-and-review"></a>Directrices para la revisión y el aprendizaje de relevancia

A continuación, se encuentra una descripción general de las directrices para la revisión y aprendizaje de relevancia:
  
- **Errores e**incoherencias: si se producen errores de etiquetado durante el aprendizaje, vuelva a ejemplos de archivos anteriores para corregirlos. Si hay demasiados errores para corregir o hay una nueva perspectiva del caso o problema, el administrador debe volver a definir los criterios de relevancia y se reiniciará el entrenamiento de relevancia.
    
- **Etiquetado y aprendizaje**: 
    
  - Los archivos deben etiquetarse en función del contenido únicamente. No tenga en cuenta los metadatos, como custodios, Date o path de archivo. 
    
  - No se deben tener en cuenta las indicaciones de intervalo de fechas en el texto al etiquetar archivos.
    
  - No considere las imágenes gráficas incrustadas cuando etiquete archivos.
     
  - Omitir el texto aplicado a la relevancia se quitará en el contenido del archivo que se muestra en la vista de texto en relevancia. Si los valores de omitir texto se definieron después de que ya se haya iniciado el entrenamiento de relevancia, el nuevo texto omitido se aplicará a los archivos de ejemplo creados a partir del punto en que se definió. La característica omitir texto debe usarse con cuidado, ya que su uso puede reducir el rendimiento del análisis de archivos
    
  - Use la opción **omitir etiquetado** solo cuando sea necesario. Las investigaciones de datos (versión preliminar) no se basan en archivos omitidos. En la evaluación, si es difícil distinguir si un archivo es relevante, es mejor marcar como relevante (R) o no relevante (NR) siempre que sea posible, en lugar de seleccionar **SKIP**. Cuando las investigaciones de datos (versión preliminar) evalúan el aprendizaje, se puede ver cómo se procesaron estos tipos de archivos.
    
  - Incluso los archivos con una cantidad muy pequeña de texto extraído deben etiquetarse en el aprendizaje como R/NR, en lugar de "omitir", cuando sea posible. 
    
  - El etiquetado puede afectar al clasificador siempre que el archivo sea legible y pueda etiquetarse como R/NR.
    
  - El número de secuencia de archivo en la lista de archivos de ejemplo mostrados de la ficha **etiqueta** permite al usuario volver al orden original mostrado de los archivos. 
    
  - Puede volver a cualquier muestra y cambiar la etiquetación de los archivos de la evaluación y el conjunto de formación. Los cambios se aplicarán al crear el ejemplo siguiente.
    
  - Los archivos de Excel examinados en formato PDF deben tratarse igual que los archivos de Excel nativos al etiquetar archivos.
    
  - Si tiene dudas sobre el etiquetado de relevancia de un archivo, consulte a un experto. Un etiquetado incorrecto durante el aprendizaje de relevancia puede llevar a la pérdida de tiempo más adelante en el proceso y también puede tener un impacto negativo en la calidad de los resultados generales.
    
  - Las palabras clave que se definieron en las listas de palabras clave se mostrarán en colores para ayudar al usuario a identificar los archivos relevantes al etiquetar.
    
- **Cálculo del lote**: los archivos que el experto etiquetó como R/NR recibirán una puntuación de 0 o 100. Esto se aplica a las etiquetas realizadas antes del cálculo por lotes. Si el experto ha cambiado el problema a inActivo tras el cálculo del lote y ha seguido el etiquetado de este problema, los nuevos resultados etiquetados no serán 100/0, sino la puntuación original.
    
- **Problemas y modo de muestreo**: los problemas suelen estar desactivados cuando se completa el trabajo en ellos (el entrenamiento de relevancia está estabilizado y se ha realizado el cálculo del lote), cuando se cancelan los problemas o cuando otro usuario está trabajando en los problemas.
    
## <a name="steps-in-relevance-training"></a>Pasos de aprendizaje de relevancia

En la **pestaña \> seguimiento de relevancia** , investigaciones de datos proporciona recomendaciones sobre cómo continuar en el procesamiento, con los siguientes pasos. Las implicaciones se describen a continuación cuando se recomienda cada uno de los pasos siguientes en el proceso de entrenamiento de relevancia. 
  
- Etiquetado/continuar etiquetado: revisión de archivos y etiquetado de relevancia realizado por un experto para cada archivo y problema dentro de un ejemplo.
    
  - Implicación: debe etiquetarse una muestra existente.
    
- Evaluación/continuar evaluación: permite la validación temprana de la relevancia de los casos y una vista preliminar de la relevancia de la población de archivos importada para el caso actual.
    
  - Implicación: se requiere o se recomienda más evaluación.
    
- Aprendizaje/continuar formación: proceso durante el cual las investigaciones de datos aprenden del experto que etiqueta los ejemplos de archivos y adquiere la capacidad de identificar criterios de relevancia relacionados con cada problema en el contexto de cada caso.
    
  - Implicación: el problema necesita más formación; la siguiente muestra se debe crear y etiquetar. 
    
- Cálculo del lote: proceso de relevancia en el que las investigaciones de datos toman la información adquirida durante la fase de formación y la aplican a todo el llenado de archivos. Todos los archivos del grupo de archivos pertinentes se evalúan para su relevancia y se les asigna una puntuación de relevancia.
    
  - Implicación: el problema se ha estabilizado y se puede realizar el cálculo del lote.
    
- Puesta en marcha: la relevancia indica cuando un experto revisa y etiqueta una muestra de archivos seleccionados desde una carga de archivos adicional durante un escenario de cargas sucesivas.
    
  - Implicación: se ha agregado una nueva carga y se debe realizar la puesta en marcha para seguir trabajando.
    
- Incoherencias de etiquetas: el proceso identifica, a través de un algoritmo de investigación de datos, incoherencias en el proceso de etiquetado de archivos que pueden afectar negativamente al análisis.
    
  - Implicación: el ejemplo siguiente incluirá los archivos que se han etiquetado en ejemplos anteriores y se debe rehacer su etiquetado.
    
- Actualizar clasificador: permite al usuario aplicar cambios de etiquetado o de inicialización.
    
  - Implicación: se pueden aplicar los cambios de etiquetado y de inicialización sin necesidad de ejecutar manualmente otro ejemplo de relevancia.
    
- En espera: se ha completado el proceso de entrenamiento de relevancia.
    
  - Implicación: en este momento no se requiere ningún entrenamiento sobre la relevancia.
    
Aunque las investigaciones de datos le guían por el proceso, con los pasos siguientes recomendados en diferentes etapas, también le permite navegar entre pestañas y páginas, y elegir opciones para abordar las situaciones que puedan ser pertinentes para su caso individual, problema o proceso de revisión de documentos. 
  
Es posible aceptar o invalidar las investigaciones de datos opciones de procesamiento del próximo paso. Si desea realizar un paso que no sea el siguiente paso recomendado, haga clic en el **siguiente paso** que aparece en la pantalla problema expandido en el cuadro de diálogo, haga clic en el botón **modificar** junto al paso siguiente y seleccione otra opción de paso siguiente. 
  
> [!NOTE]
> Algunas opciones pueden permanecer deshabilitadas tras el desbloqueo porque no se pueden usar en ese punto del proceso. 
  
## <a name="more-information"></a>Más información

[Descripción de la evaluación en relevancia](../assessment-in-relevance-in-advanced-ediscovery.md)
  
[Etiquetado y evaluación](../tagging-and-assessment-in-advanced-ediscovery.md)
  
[Aprendizaje de etiquetas y relevancia](../tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[Seguimiento del análisis de relevancia](../track-relevance-analysis-in-advanced-ediscovery.md)
  
[Decisiones basadas en los resultados](../decision-based-on-the-results-in-advanced-ediscovery.md)
  
[Prueba del análisis de relevancia](../test-relevance-analysis-in-advanced-ediscovery.md)

[Consultar los datos en evidencia](evidence-query.md)