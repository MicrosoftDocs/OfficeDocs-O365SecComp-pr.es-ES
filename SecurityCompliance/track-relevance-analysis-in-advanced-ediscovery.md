---
title: Seguimiento del análisis de relevancia en eDiscovery avanzado de Office 365
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
ms.assetid: 3ab1e2c3-28cf-4bf5-b0a8-c0222f32bdf5
description: 'Obtenga información sobre cómo ver e interpretar los resultados para problemas de casos de exhibición de documentos electrónicos avanzada de Office 365 y estado de recursos de aprendizaje de la relevancia.  '
ms.openlocfilehash: a19f7eaabf5dc15eefaa7209ded8261020d0d557
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22536851"
---
# <a name="track-relevance-analysis-in-office-365-advanced-ediscovery"></a>Seguimiento del análisis de relevancia en eDiscovery avanzado de Office 365

> [!NOTE]
> Exhibición de documentos electrónicos avanzada requiere un E3 de Office 365 con el complemento de cumplimiento avanzadas o una suscripción E5 para su organización. Si no tiene ese plan y desea probar avanzada exhibición de documentos electrónicos, puede [registrarse y obtener una versión de prueba de Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279). 
  
En Avanzadas exhibición de documentos electrónicos, la ficha seguimiento de la relevancia muestra la validez de la formación de relevancia realizada en la ficha etiqueta calculada e indica el siguiente paso a tomar en el proceso de entrenamiento iterativo en la relevancia. 
  
## <a name="tracking-relevance-training-status"></a>Seguimiento del estado de recursos de aprendizaje de relevancia

1. Ver los detalles siguientes de la relevancia de seguimiento para los problemas de mayúsculas y minúsculas, tal como se muestra en el siguiente ejemplo de un cuadro de diálogo **nombre del problema** que aparece a continuación. 
    
  - **Evaluación**: este indicador de progreso muestra en qué medida la relevancia de recursos de aprendizaje a este punto se realizan ha logrado el destino de evaluación en términos de margen de error. También se muestra la flexibilidad de los resultados de aprendizaje de la relevancia. 
    
  - **Recursos de aprendizaje**: esta pantalla progreso codificada por colores de indicador y de información sobre herramientas indica el aprendizaje de la relevancia de resultados de estabilidad y una escala numérica que muestra el número de muestras de aprendizaje de la relevancia etiquetados para cada problema. El experto supervisa el progreso del proceso de aprendizaje de la relevancia iterativo. 
    
  - **Cálculo por lotes**: este indicador de progreso proporciona información acerca de la finalización de cálculo por lotes.
    
  - **Siguiente paso**: muestra la recomendación para el siguiente paso que se debe realizar. 
    
    En el ejemplo, se muestra una evaluación completada correctamente por un problema, indicada por el indicador de progreso de color completado y la marca de verificación. Etiquetado está en curso, pero el caso todavía se considera inestable (estado de estabilidad también se muestra en una información sobre herramientas). La recomendación de paso siguiente es "formación". 
    
    ![Formación del seguimiento de relevancia paso 1](media/a00fe607-680a-48eb-9d61-4565319f7ab6.png)
  
    La vista expandida muestra opciones e información adicional. El margen de error actual que se muestra es el margen de error de la recuperación en el estado actual de evaluación, dado los archivos existentes de evaluación (ya etiquetado).
    
    > [!NOTE]
    >  La fase de evaluación puede omitirse desactivando la casilla de verificación **evaluación** por el problema y, a continuación, para "todos los problemas". Sin embargo, como resultado, habrá ningún estadísticas para este problema. > Desactivando la casilla de verificación de **evaluación** sólo puede realizarse antes de realiza la evaluación. Cuando hay varios problemas en un caso, se omitirá el evaluación sólo si la casilla de verificación está desactivada por cada problema 
  
    Cuando no se completa la evaluación con el primer ejemplo de conjunto de archivos, evaluación podría ser el siguiente paso para etiquetar los archivos más. 
    
    En **la relevancia** \> **pista**, el indicador de progreso de aprendizaje y la información sobre herramientas indican el número estimado de ejemplos adicionales necesarios para llegar a la estabilidad. Esta estimación proporciona instrucciones para los recursos de aprendizaje adicionales necesitado.
    
    ![Formación del seguimiento de relevancia](media/98dbc3f5-5238-4d73-9f88-1aa4d77ea729.png)
  
2. Cuando esté listo etiquetado y si necesita continuar la formación, haga clic en **recursos de aprendizaje**. Otro conjunto de archivos de ejemplo se genera a partir del archivo cargado establecido para recursos de aprendizaje adicionales. A continuación, se devuelven a la ficha de etiqueta para etiquetar y formar a más archivos.
    
### <a name="reaching-stable-training-levels"></a>Alcanzar los niveles de formación estable

Después de que los archivos de evaluación han alcanzado un nivel estable de formación, exhibición de documentos electrónicos avanzada está preparada para cálculo por lotes.
  
> [!NOTE]
> Normalmente, después de tres estable ejemplos de aprendizaje, el siguiente paso es "Cálculo por lotes". Puede haber excepciones, por ejemplo, cuando se produjeron cambios para el etiquetado de los archivos de ejemplos anteriores o cuando se han agregado los archivos de inicialización. 
  
### <a name="performing-batch-calculation"></a>Realizar el cálculo por lotes

Cálculo por lotes se ejecuta como el siguiente paso después de que se haya completado correctamente aprendizaje (cuando un estado estable aprendizaje se muestra en la barra de progreso, una marca de verificación y un estado estable en la información sobre herramientas.) Cálculo del lote aplica el conocimiento adquirido durante el curso de la relevancia para la población de todo el archivo, para evaluar la relevancia de los archivos y para asignar las puntuaciones de la relevancia.
  
Cuando hay más de un problema, el cálculo de proceso por lotes se realiza por el problema. Durante el cálculo por lotes, se supervisa el progreso durante el procesamiento de todos los archivos. 
  
En este caso, el siguiente paso recomendado es "None", que indica que no hay recursos de aprendizaje de la relevancia iterativo adicionales es necesario en este momento. La siguiente fase es la **la relevancia de \> decidir** ficha. 
  
Si desea importar nuevos archivos después del cálculo por lotes, el administrador puede agregar los archivos importados a una carga de nuevo.
  
> [!NOTE]
> Si hace clic en **Cancelar** durante el cálculo por lotes, guarda el proceso de lo que ya se ha ejecutado. Si ejecuta el nuevo cálculo de proceso por lotes, el proceso continuará desde el último punto ejecutado. 
  
### <a name="assessing-tagging-consistency"></a>Evaluación de coherencia etiquetas temáticas

Si hay incoherencias en archivo etiquetado, puede afectar el análisis. La exhibición de documentos electrónicos avanzada etiquetado proceso de coherencia se puede usar cuando los resultados no son óptimos o coherencia está en duda. Se devuelve una lista de archivos de forma incoherente con etiqueta posibles, y pueda revisarse y volver a etiquetados, según sea necesario.
  
> [!NOTE]
> Después de siete o más redondea aprendizaje siguiente evaluación, etiquetado coherencia puede verse en **la relevancia** \> **pista** \> **problema** \> **resultados detallados** \> **curso de formación**. Esta revisión se realiza para un problema a la vez. 
  
1. En **relevancia \> pista**, expanda la fila de un problema.
    
2. A la derecha del **siguiente paso**, haga clic en **Modificar**.
    
3. Seleccione **las incoherencias de etiqueta** como la opción **siguiente paso** , después de siete ejemplos de aprendizaje y haga clic en **Aceptar**.
    
4. Seleccione **las incoherencias de etiqueta**. Mostrar una lista de las incoherencias para volver a marcar cuando sea necesario, abre la ficha de la **etiqueta** . 
    
5. Haga clic en **calcular** para enviar los cambios. El paso siguiente después de etiquetado incoherencias es "formación". 
    
## <a name="viewing-and-using-relevance-results"></a>Ver y usar los resultados de la relevancia

En el **la relevancia \> pista** ficha, expanda la fila de un problema y junto a los **resultados detallados**, haga clic en **Ver**. Los paneles de resultados detallados se muestran, como se muestra y se describe a continuación.
  
![Resultados detallados de la formación de relevancia](media/495c04a9-ed1e-4355-8cab-c14270ca2bbb.png)
  
### <a name="tagging-summary"></a>Resumen de las etiquetas temáticas

 En el ejemplo que se muestra a continuación, el **etiquetado de resumen** muestra los totales de cada uno de evaluación, formación y etiquetar los procesos de archivo puesta al día. 
  
![Resumen de etiquetado del seguimiento de relevancia](media/0ec906fc-bc84-4245-a964-fb3ca37891db.png)
  
### <a name="keywords"></a>Keywords

Una palabra clave es una cadena única, word, frase o secuencia de palabras en un archivo identificado por avanzada exhibición de documentos electrónicos como un indicador de si un archivo es relevante significativo. Lista de las columnas "Include" palabra clave y pesos en archivos etiquetados como pertinente y las columnas "Excluir" se enumeran las palabras clave y pesos en archivos etiquetados como no relevantes.
  
Exhibición de documentos electrónicos avanzada asigna palabras clave positivo o negativo los valores de weight. Cuanto mayor sea el peso, mayor será la probabilidad de que un archivo en el que aparece la palabra clave se asigna una puntuación más alta de la relevancia durante el cálculo de lote. 
  
La lista de exhibición de documentos electrónicos avanzada de palabras clave puede utilizarse para completar una lista creada por un experto o como una comprobación de validez indirecta en cualquier momento en el archivo de proceso de revisión.
  
### <a name="training-progress"></a>Curso de formación

El panel **Progreso del aprendizaje** incluye un aprendizaje progreso gráfico y la calidad de visualización de indicador, tal como se muestra en el ejemplo siguiente. 
  
![Progreso de formación del seguimiento de relevancia](media/8a5089f5-a162-4246-ae09-bc1921859860.png)
  
 **Indicador de calidad de recursos de aprendizaje**: muestra la clasificación de la coherencia de las etiquetas temáticas de la siguiente manera:
  
- **Buena**: los archivos se etiquetan de forma coherente. (Muestra de luz verde)
    
- **Medio**: algunos archivos se pueden etiquetar de forma incoherente. (Muestra amarillo claro)
    
- **Advertencia**: es posible que se etiquetados muchos archivos de forma incoherente. (Muestra de luz roja)
    
 **Gráfico de progreso de recursos de aprendizaje**: muestra el grado de estabilidad de aprendizaje de la relevancia después de un número de ciclos de aprendizaje de la relevancia en comparación con el valor de medida de F. Tal y como se mueva desde la izquierda a la derecha en el gráfico, se restringe el intervalo de confianza y se usa junto con la medida de F, mediante la exhibición de documentos electrónicos avanzada la relevancia para determinar la estabilidad cuando el aprendizaje de la relevancia de resultados están optimizados.
  
> [!NOTE]
> La relevancia usa F2, una métrica F medida donde recuperación recibe dos veces mucho peso como precisión. Para los casos con flexibilidad alta (más del 25%), usos de la relevancia F1 (proporción de 1:1). La proporción de F medida se puede configurar en **el programa de instalación de la relevancia** \> **Configuración avanzada**. 
  
### <a name="batch-calculation-results"></a>Resultados de los cálculos por lotes

El panel de **resultados de los cálculos por lotes** incluye el número de archivos que se han obtenido de la relevancia, como se indica a continuación: 
  
- **Success**
    
- **Vacío**: no contiene texto, por ejemplo, sólo espacios/fichas
    
- **Error**: debido a un tamaño excesivo o no se pudo leer
    
- **Omitido**: debido a un tamaño excesivo
    
- **Nebulous**: contiene texto sin sentido o no relevantes para el problema de características
    
> [!NOTE]
> Vacío, error, Ignored o Nebulous recibirá una puntuación de relevancia de -1. 
  
### <a name="training-statistics"></a>Estadísticas de recursos de aprendizaje

El panel de **estadísticas de recursos de aprendizaje** muestra estadísticas y gráficos basados en los resultados de aprendizaje de la relevancia de exhibición de documentos electrónicos avanzadas. 
  
![Estadísticas de formación del seguimiento de relevancia](media/9a07740e-20d3-49fb-b9b9-84265e0a1836.png)
  
Esta vista muestra lo siguiente:
  
- **Proporción de retirada de revisión**: comparación de resultados en función de la relevancia de puntuación en una revisión teoría lineal. Recuperación es estimada dado el conjunto de tamaño del conjunto de revisión.
    
- **Parámetros**: acumulativa calcula las estadísticas correspondientes a la revisión que se establece en relación con la población de archivo para el caso de todo.
    
- **Revisión**: porcentaje de los archivos para revisar basándose en este límite.
    
- **Recuerde**: porcentaje de pertinente archivos en el conjunto de revisión. 
    
- **Distribución por puntuación de relevancia**: los archivos en la pantalla gris oscuro a la izquierda están por debajo de la puntuación de corte. Una información sobre herramientas muestra la puntuación de relevancia y el porcentaje de archivos relacionado en el archivo de revisión que se establece en relación con el total de archivos.
    
## <a name="see-also"></a>Vea también

[eDiscovery avanzado de Office 365](office-365-advanced-ediscovery.md)
  
[Evaluación de descripción en la relevancia](assessment-in-relevance-in-advanced-ediscovery.md)
  
[Realizando y revisión de evaluación](tagging-and-assessment-in-advanced-ediscovery.md)
  
[Realización de aprendizaje de relevancia](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[En función de los resultados de la toma de decisiones](decision-based-on-the-results-in-advanced-ediscovery.md)
  
[Las pruebas de análisis de la relevancia](test-relevance-analysis-in-advanced-ediscovery.md)

