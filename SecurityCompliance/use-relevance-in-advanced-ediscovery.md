---
title: Usar el módulo de relevancia en eDiscovery avanzado de Office 365
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
ms.assetid: 5d671821-d188-42da-a9ce-9cfe92beedfd
description: 'Obtenga información sobre el módulo de la relevancia en Office 365 avanzada exhibición de documentos electrónicos, incluidos un flujo de trabajo y los pasos para su revisión de aprendizaje y archivo e instrucciones.  '
ms.openlocfilehash: 2cf75ef95291c5393367ce01fb0cd660f9b99145
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22535957"
---
# <a name="use-the-relevance-module-in-office-365-advanced-ediscovery"></a>Usar el módulo de relevancia en eDiscovery avanzado de Office 365

> [!NOTE]
> Exhibición de documentos electrónicos avanzada requiere un E3 de Office 365 con el complemento de cumplimiento avanzadas o una suscripción E5 para su organización. Si no tiene ese plan y desea probar avanzada exhibición de documentos electrónicos, puede [registrarse y obtener una versión de prueba de Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279). 
  
En la exhibición de documentos electrónicos avanzada, el módulo de la relevancia incluye el aprendizaje de la relevancia y la revisión de los archivos relacionados con un caso. El flujo de trabajo de la relevancia se muestran y se describen a continuación:
  
![Flujo de trabajo de relevancia](media/44c67dd2-7a20-40a9-b0ed-784364845c77.gif)
  
- **Ciclos de evaluación y seguimiento de**:
    
  - **Evaluación**: exhibición de documentos electrónicos avanzada permite la evaluación temprana basándose en una muestra aleatoria de archivos y usa esta evaluación para aplicar las decisiones para determinar el rendimiento del proceso de codificación predictivo. 
    
  - **Pista**: exhibición de documentos electrónicos avanzada calcula y muestra resultados provisionales de la evaluación mientras supervisaba validez estadística del proceso. 
    
- **Ciclos de formación y seguimiento de**:
    
  - **Etiqueta**: exhibición de documentos electrónicos avanzada aprende criterios de relevancia específicos de cada problema según revisión iterativa del experto y etiquetas temáticas de archivos individuales.
    
  - **Pista**: exhibición de documentos electrónicos avanzada calcula y muestra resultados provisionales de la formación de relevancia mientras supervisaba validez estadística del proceso. 
    
- **Cálculo por lotes**: exhibición de documentos electrónicos avanzada toma los criterios de relevancia acumulados y aprendidos, se aplica a la colección de todo el archivo y genera las puntuaciones de la relevancia para cada archivo.
    
- **Decide**: exhibición de documentos electrónicos avanzada muestra los resultados del análisis que se aplica el caso completo después de cálculo por lotes y muestra los datos para tomar decisiones de revisión del documento.
    
- **Prueba**: los resultados de la exhibición de documentos electrónicos avanzada pueden probarse para comprobar la validez y la eficacia del procesamiento de exhibición de documentos electrónicos avanzadas.
    
## <a name="guidelines-for-relevance-training-and-review"></a>Directrices para la formación de la relevancia y revisión

Es una visión general de las directrices de aprendizaje de la relevancia y revisión:
  
- **Errores e incoherencias**: si se realizan las etiquetas temáticas errores durante la formación, volver a los ejemplos de archivo anteriores a corregirlos. Si hay demasiados errores para corregir o no hay una nueva perspectiva de la caja o un problema, deben volver a definir los criterios de la relevancia por el administrador y reinicia el aprendizaje de la relevancia.
    
- **Etiquetado y formación**: 
    
  - Los archivos se deben etiquetar basado en el contenido únicamente. No se considere la posibilidad de metadatos, como custodia, la fecha o la ruta de acceso de archivo. 
    
  - No considere la posibilidad de fecha indicaciones de rango en el texto al etiquetar los archivos.
    
  - No considere la posibilidad de imágenes gráficas incrustadas al etiquetar los archivos.
    
  - Si la visualización de un archivo mediante el icono **con el formato de vista de texto** mientras etiquetas temáticas, no tenga en cuenta el formato del texto. Por ejemplo, una palabra que se muestra con formato de tachado (una línea horizontal a través de su centro de eliminación) todavía se considera por relevancia como parte del texto analizado. 
    
  - Omitir el texto que se aplica a la relevancia (según lo definido por el Administrador de casos o el administrador) se quitará en el contenido del archivo que se muestra en la vista de texto en la relevancia. Si se han definido los valores para omitir el texto después de la relevancia de formación ya ha iniciado, el nuevo texto omitido se aplicarán a los archivos de ejemplo creados desde el punto en el que se definió. La característica de omitir texto debe utilizarse con cautela, como su uso puede reducir el rendimiento de análisis de archivo
    
  - Use la opción **Omitir etiquetado** sólo cuando sea necesario. Exhibición de documentos electrónicos avanzada no enseñar a basándose en los archivos omitidos. En la evaluación, si es difícil saber si un archivo es relevante, es mejor etiqueta como Relevant (R) o no relevante (n) siempre que sea posible en lugar de seleccionar **Omitir**. Cuando avanzada exhibición de documentos electrónicos se evalúa como recursos de aprendizaje, se puede, a continuación, ver grado estos tipos de archivos se han procesado.
    
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
  
## <a name="see-also"></a>Vea también

[eDiscovery avanzado de Office 365](office-365-advanced-ediscovery.md)
  
[Evaluación de descripción en la relevancia](assessment-in-relevance-in-advanced-ediscovery.md)
  
[Etiquetas temáticas y evaluación](tagging-and-assessment-in-advanced-ediscovery.md)
  
[Etiquetado y formación de relevancia](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[Análisis de la relevancia de seguimiento](track-relevance-analysis-in-advanced-ediscovery.md)
  
[Decidir en función de los resultados](decision-based-on-the-results-in-advanced-ediscovery.md)
  
[Las pruebas de análisis de la relevancia](test-relevance-analysis-in-advanced-ediscovery.md)

