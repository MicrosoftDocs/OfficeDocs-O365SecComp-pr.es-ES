---
title: Seguimiento del análisis de relevancia en Office 365 Advanced eDiscovery
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
ms.assetid: 3ab1e2c3-28cf-4bf5-b0a8-c0222f32bdf5
description: 'Obtenga información sobre cómo ver e interpretar el estado de aprendizaje de relevancia y los resultados de los problemas de caso en eDiscovery avanzado de Office 365.  '
ms.openlocfilehash: 8bdfd2ddb88215b7217d1cc4cdacf2e775a0d977
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32264442"
---
# <a name="track-relevance-analysis-in-office-365-advanced-ediscovery"></a>Seguimiento del análisis de relevancia en Office 365 Advanced eDiscovery

> [!NOTE]
> Para usar eDiscovery avanzado, su organización necesita una suscripción de Office 365 E3 con el complemento Cumplimiento avanzado, o bien una suscripción de E5. Si no tiene ese plan y quiere probar eDiscovery avanzado, puede [registrarse para una prueba de Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279). 
  
En la exhibición avanzada de documentos electrónicos, la pestaña seguimiento de relevancia muestra la validez calculada del entrenamiento de relevancia realizado en la pestaña etiqueta e indica el siguiente paso que debe realizar en el proceso de entrenamiento iterativo en relevancia. 
  
## <a name="tracking-relevance-training-status"></a>Seguimiento del estado del entrenamiento de relevancia

1. Vea los siguientes detalles en el seguimiento de relevancia para los problemas de casos, como se muestra en el siguiente ejemplo de un cuadro de diálogo de **nombre de problema** a continuación. 
    
  - **Evaluación**: este indicador de progreso muestra el grado en el que el entrenamiento de relevancia realizado hasta este punto ha logrado el objetivo de la evaluación en cuanto al margen de error. También se muestra la riqueza de los resultados de entrenamiento de relevancia. 
    
  - **Aprendizaje**: este indicador de progreso codificado por colores y muestra de la información sobre herramientas indica la estabilidad de los resultados del entrenamiento de relevancia y una escala numérica que muestra el número de muestras de aprendizaje de relevancia etiquetadas para cada problema. El experto supervisa el progreso del proceso de entrenamiento de relevancia iterativa. 
    
  - **Cálculo del lote**: este indicador de progreso proporciona información acerca de la finalización del cálculo por lotes.
    
  - **Siguiente paso**: muestra las recomendaciones para el siguiente paso que se debe realizar. 
    
    En el ejemplo, se muestra una evaluación completada correctamente de un problema, indicada por el indicador de progreso de color completado y la marca de verificación. Se está realizando un etiquetado, pero el caso se considera inestable (el estado de estabilidad también se muestra en un Consejo de herramientas). La recomendación de paso siguiente es "Training". 
    
    ![Formación del seguimiento de relevancia paso 1](media/a00fe607-680a-48eb-9d61-4565319f7ab6.png)
  
    La vista expandida muestra información adicional y opciones. El margen de error actual mostrado es el margen de error de la recuperación en el estado actual de la evaluación, dados los archivos de evaluación existentes (ya etiquetados).
    
    > [!NOTE]
    >  La fase de evaluación se puede omitir desactivando la casilla de verificación **evaluación** por problema y, a continuación, de "todos los problemas". Sin embargo, como resultado, no habrá estadísticas para este problema. > desactivar la casilla de verificación **evaluación** solo puede realizarse antes de que se realice la evaluación. Cuando hay varios problemas en un caso, la evaluación se omite solo si la casilla de verificación está desactivada para cada problema 
  
    Cuando la evaluación no se completa con el primer conjunto de ejemplos de archivos, la evaluación podría ser el paso siguiente para etiquetar más archivos. 
    
    En el **seguimiento**de **relevancia** \> , el indicador de progreso de formación y la información sobre herramientas indican el número estimado de muestras adicionales necesarias para alcanzar la estabilidad. Esta estimación proporciona una pauta para la formación adicional necesaria.
    
    ![Formación del seguimiento de relevancia](media/98dbc3f5-5238-4d73-9f88-1aa4d77ea729.png)
  
2. Cuando haya terminado de realizar el etiquetado y tenga que continuar con la formación, haga clic en **entrenamiento**. Se genera otro conjunto de archivos de ejemplo a partir del conjunto de archivos cargados para obtener más formación. A continuación, se vuelve a la pestaña etiqueta para etiquetar y entrenar a más archivos.
    
### <a name="reaching-stable-training-levels"></a>Alcanzar niveles de formación estables

Una vez que los archivos de evaluación alcanzan un nivel de formación estable, la exhibición avanzada de documentos electrónicos está lista para el cálculo por lotes.
  
> [!NOTE]
> Normalmente, después de tres ejemplos de formación estables, el siguiente paso es "cálculo por lotes". Puede haber excepciones, por ejemplo, cuando se han producido cambios en el etiquetado de archivos desde ejemplos anteriores o cuando se han agregado archivos de inicialización. 
  
### <a name="performing-batch-calculation"></a>Realizar el cálculo por lotes

El cálculo del lote se ejecuta como el paso siguiente una vez que el entrenamiento se completa correctamente (cuando la barra de progreso muestra un estado de entrenamiento estable, una marca de verificación y un estado estable en la información sobre herramientas). El cálculo del lote aplica los conocimientos adquiridos durante el entrenamiento de relevancia a toda la población de archivos, para evaluar la relevancia de los archivos y asignar los resultados de relevancia.
  
Cuando hay más de un problema, el cálculo del lote se realiza por problema. Durante el cálculo por lotes, el progreso se supervisa mientras se procesan todos los archivos. 
  
Aquí, el siguiente paso recomendado es "ninguno", que indica que no se requiere ningún aprendizaje de relevancia iterativo adicional en este punto. La siguiente fase es la **pestaña \> decisión de relevancia** . 
  
Si desea importar nuevos archivos tras el cálculo por lotes, el administrador puede Agregar los archivos importados a una nueva carga.
  
> [!NOTE]
> Si hace clic en **Cancelar** durante el cálculo por lotes, el proceso guarda lo que ya se ha ejecutado. Si vuelve a ejecutar el cálculo por lotes, el proceso continuará desde el último punto ejecutado. 
  
### <a name="assessing-tagging-consistency"></a>Evaluación de la coherencia de etiquetado

Si hay incoherencias en el etiquetado de archivos, puede afectar al análisis. El proceso de coherencia de etiquetado de exhibición de documentos electrónicos avanzado puede usarse cuando los resultados no son óptimos o la coherencia está en duda. Se devuelve una lista de los archivos etiquetados que pueden ser incoherentes y se pueden revisar y volver a etiquetar, según sea necesario.
  
> [!NOTE]
> Después de siete o más formación redondeos tras la evaluación, la coherencia de etiquetado se puede ver en el **seguimiento** \> **** \> de **relevancia** \> **progreso de aprendizaje**de **resultados** \> detallados. Esta revisión se realiza por un problema a la vez. 
  
1. En **el \> seguimiento de relevancia**, expanda la fila de un problema.
    
2. A la derecha del **paso siguiente**, haga clic en **modificar**.
    
3. Seleccione incoherencias de **etiquetas** como la opción de **paso siguiente** , después de siete ejemplos de aprendizaje y haga clic en **Aceptar**.
    
4. Seleccione incoherencias de **etiqueta**. La ficha **etiqueta** se abre y muestra una lista de las incoherencias que se deben volver a etiquetar según sea necesario. 
    
5. Haga clic en **calcular** para enviar los cambios. El paso siguiente tras las incoherencias de etiquetado es "Training". 
    
## <a name="viewing-and-using-relevance-results"></a>Visualización y uso de los resultados de relevancia

En la **pestaña \> seguimiento de relevancia** , expanda la fila de un problema y, junto a **resultados**detallados, haga clic en **Ver**. Se mostrarán los paneles de resultados deTallados, tal y como se describe a continuación.
  
![Resultados detallados de la formación de relevancia](media/495c04a9-ed1e-4355-8cab-c14270ca2bbb.png)
  
### <a name="tagging-summary"></a>Resumen de etiquetación

 En el ejemplo que se muestra a continuación, el **Resumen de etiquetado** muestra los totales de cada proceso de etiquetado de archivos de evaluación, formación y captura. 
  
![Resumen de etiquetado del seguimiento de relevancia](media/0ec906fc-bc84-4245-a964-fb3ca37891db.png)
  
### <a name="keywords"></a>Palabras clave

Una palabra clave es una cadena única, palabra, frase o secuencia de palabras en un archivo identificado por Advanced eDiscovery como un indicador significativo de si un archivo es relevante. La palabra clave "include" de la lista de columnas y los pesos en archivos etiquetados como relevantes, y las columnas "excluir" enumeran palabras clave y pesos en archivos etiquetados como no relevantes.
  
La exhibición avanzada de documentos electrónicos asigna valores de peso de palabras clave negativas o positiva. Cuanto mayor sea el peso, mayor será la probabilidad de que un archivo en el que aparezca la palabra clave tenga una puntuación de relevancia superior durante el cálculo del lote. 
  
La lista de palabras clave de eDiscovery avanzada se puede usar para complementar una lista creada por un experto o como comprobación indirecta de validez en cualquier punto del proceso de revisión de archivos.
  
### <a name="training-progress"></a>Progreso de formación

El panel **progreso del entrenamiento** incluye un gráfico de progreso de formación y una visualización del indicador de calidad, como se muestra en el ejemplo siguiente. 
  
![Progreso de formación del seguimiento de relevancia](media/8a5089f5-a162-4246-ae09-bc1921859860.png)
  
 **Indicador de calidad de formación**: muestra la clasificación de la coherencia de etiquetado de la siguiente manera:
  
- **Bueno**: los archivos se etiquetan de forma coherente. (Luz verde mostrada)
    
- **Media**: es posible que algunos archivos se etiqueten de manera incoherente. (Luz amarilla mostrada)
    
- **ADVERTENCIA**: es posible que muchos archivos se etiqueten de manera incoherente. (Luz roja mostrada)
    
 **Gráfico de progreso de formación**: muestra el grado de estabilidad del aprendizaje de relevancia después de varios ciclos de aprendizaje de relevancia en comparación con el valor de la medida de F. A medida que nos desplazamos de izquierda a derecha en el gráfico, el intervalo de confianza se reduce y se usa, junto con la medida F, por relevancia de eDiscovery avanzado para determinar la estabilidad cuando se optimizan los resultados de la formación de relevancia.
  
> [!NOTE]
> Relevancia usa F2, una métrica de F-Measure donde la recuperación recibe dos veces el peso de la precisión. Para los casos con alta riqueza (más de 25%), relevancia usa F1 (proporción de 1:1). La relación de medida F se puede configurar en la **Configuración avanzada**de la **configuración** \> de relevancia. 
  
### <a name="batch-calculation-results"></a>Resultados del cálculo por lotes

El panel de **resultados de cálculo por lotes** incluye el número de archivos que se han puntuado para la relevancia, de la siguiente manera: 
  
- **Success**
    
- **Empty**: no contiene texto, por ejemplo, solo espacios/tabulaciones
    
- **Error**: debido a un tamaño excesivo o no se pudo leer
    
- **Ignorado**: debido a un tamaño excesivo
    
- **Nebulous**: contiene texto sin significado o no tiene características relevantes para el problema
    
> [!NOTE]
> Empty, failed, Ignored o Nebulous recibirá una puntuación de relevancia de-1. 
  
### <a name="training-statistics"></a>Estadísticas de formación

El panel de **estadísticas de formación** muestra las estadísticas y los gráficos basados en los resultados de la formación avanzada de relevancia de eDiscovery. 
  
![Estadísticas de formación del seguimiento de relevancia](media/9a07740e-20d3-49fb-b9b9-84265e0a1836.png)
  
Esta vista muestra lo siguiente:
  
- **Tasa de revisión-RECALL**: comparación de los resultados de acuerdo con los resultados de relevancia en una revisión hipotéticamente lineal. La recuperación se calcula según el conjunto Review size set.
    
- **** Parameters: estadísticas calculadas acumuladas relativas a la revisión establecida en relación con el llenado de archivos para todo el caso.
    
- **Revisión**: porcentaje de archivos que se van a revisar en función de este límite.
    
- **RECALL**: porcentaje de archivos relevantes en el conjunto de revisión. 
    
- **Distribución por puntuación de relevancia**: los archivos en la pantalla gris oscuro a la izquierda están por debajo de la puntuación límite. Una información sobre herramientas muestra la puntuación de relevancia y el porcentaje relacionado de los archivos en el archivo de revisión establecido en relación con el total de archivos.
    
## <a name="see-also"></a>Vea también

[eDiscovery avanzado de Office 365](office-365-advanced-ediscovery.md)
  
[Descripción de la evaluación en relevancia](assessment-in-relevance-in-advanced-ediscovery.md)
  
[Realización y revisión de la evaluación](tagging-and-assessment-in-advanced-ediscovery.md)
  
[Realizar entrenamiento de relevancia](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[Toma de decisiones basándose en los resultados](decision-based-on-the-results-in-advanced-ediscovery.md)
  
[Prueba del análisis de relevancia](test-relevance-analysis-in-advanced-ediscovery.md)

