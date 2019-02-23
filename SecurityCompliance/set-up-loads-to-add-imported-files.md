---
title: Configurar cargas para agregar archivos importados en eDiscovery avanzado de Office 365
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
ms.assetid: 0e0a9d04-294f-4f54-8bf1-b32d81345126
description: 'Revise los pasos para agregar archivos importados a la última carga definida, o lote, de archivos antes de realizar el aprendizaje de relevancia en eDiscovery avanzado de Office 365.  '
ms.openlocfilehash: 8c5101628b468719f8aa4f81a4c73cbbb226105f
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/23/2019
ms.locfileid: "30215990"
---
# <a name="set-up-loads-to-add-imported-files-in-office-365-advanced-ediscovery"></a>Configurar cargas para agregar archivos importados en eDiscovery avanzado de Office 365

> [!NOTE]
> Para usar eDiscovery avanzado, su organización necesita una suscripción de Office 365 E3 con el complemento Cumplimiento avanzado, o bien una suscripción de E5. Si no tiene ese plan y quiere probar eDiscovery avanzado, puede [registrarse para una prueba de Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279). 
  
En eDiscovery avanzado, una carga es un nuevo lote de archivos que se agregan a un caso. De forma predeterminada, se define una carga y se agregan todos los archivos importados. Antes de realizar la formación de relevancia, los archivos importados deben agregarse a la carga. 
  
Tenga en cuenta los siguientes escenarios:
  
- Se sabe que los archivos nuevos son similares a los archivos anteriores cargados en la base de datos de casos o la carga anterior de archivos fue un conjunto aleatorio de la colección de archivos. En este caso, agregue los archivos importados a la carga de archivos actual.
    
- Los archivos nuevos son distintos de los anteriores (por ejemplo, de un origen distinto) o no hay conocimiento previo de que sean similares o distintos a las cargas anteriores. En este escenario, agregue los archivos importados a una nueva carga de archivos. EDiscovery avanzado reconoce esto como un escenario de cargas continuas, invoca un proceso de puesta en marcha, bloquea el entrenamiento de relevancia y los cálculos por lotes hasta que se completa la puesta en marcha y la nueva carga se integra y se entrena. 
    
## <a name="adding-imported-files-to-the-current-load"></a>Adición de archivos importados a la carga actual

Todos los archivos importados deben agregarse a una carga para ser procesados en eDiscovery avanzado. Los archivos importados se agregan a la última carga definida. Si importa archivos adicionales más adelante, también deben agregarse a la carga.
  
1. En la **pestaña \> configuración de relevancia** para la relevancia, seleccione **carga**.
    
    ![Pestaña Cargas de configuración de relevancia](media/278aac7f-655f-462f-852a-6baa5d818768.png)
  
2. **Archivos de inclusión**: Seleccione una opción para los archivos que se van a incluir. De forma predeterminada, la adición de archivos a la carga actual se basa en el llenado "todos los archivos".
    
    > [!TIP]
    > Cargar todos los archivos de selección disponibles en relevancia. Si tiene previsto cargar solo un subconjunto de los archivos disponibles, consulte primero la ayuda, ya que los subconjuntos de carga pueden afectar negativamente al entrenamiento de relevancia. 
  
3. En cargar **Administración**, seleccione una carga.
    
4. Haga clic en **Agregar archivos**. Los archivos se agregan a la carga y se muestra un mensaje de confirmación. 
    
5. Haga clic en **Aceptar**.
    
Ahora, los archivos se pueden procesar en la relevancia avanzada de eDiscovery para entrenar a los archivos.
  
## <a name="editing-a-load-name-within-a-case"></a>Edición de un nombre de carga en un caso

Si se cambia el nombre de carga, se recomienda usar un nombre significativo en el caso.
  
1. En la **pestaña \> configuración de relevancia** para la relevancia, seleccione **carga**.
    
2. En la lista **Administración de cargas** , seleccione una carga y haga clic en el icono **Editar** . Se muestra la ventana Editar carga. 
    
3. Escriba los cambios y, a continuación, haga clic en **Aceptar**.
    
## <a name="adding-imported-files-to-a-new-load"></a>Adición de archivos importados a una nueva carga

Después de iniciar el entrenamiento de relevancia o realizar el cálculo por lotes, es posible que desee importar y procesar un conjunto de archivos adicional. 
  
Durante la puesta en marcha, puede crear, etiquetar y analizar el conjunto de puesta en marcha. EDiscovery avanzado compara la evaluación de los archivos relevantes y no relevantes en la nueva carga con los de cargas anteriores. En función de los resultados, se le pedirá que tome decisiones de puesta en marcha, si es necesario, y la exhibición avanzada de documentos electrónicos le proporcionará recomendaciones basadas en la información de relevancia acumulada. 
  
Las cargas graduales y la funcionalidad de puesta en marcha varían de la siguiente manera: 
  
- Al importar una nueva carga de archivos después del cálculo por lotes, la exhibición avanzada de documentos electrónicos determina en qué medida los archivos se dividen en una de las siguientes categorías:
    
  - Similar (homogéneo): no se requiere una nueva ronda personalizada de formación de relevancia y el conocimiento acumulado de la carga anterior puede aplicarse "tal cual" a la nueva carga. 
    
  - DISTINCT (heterogéneo): se requiere un nuevo y personalizado de aprendizaje de relevancia, y no se puede aplicar el conocimiento acumulado de la carga anterior. 
    
    Estos términos se refieren al nivel de similitud de los archivos entre cargas y no dentro de las cargas. 
    
- Al importar una nueva carga de archivos durante el entrenamiento de relevancia (antes del cálculo por lotes), la puesta en marcha permite continuar la formación de relevancia en el conjunto de archivos. La exhibición avanzada de documentos electrónicos no calcula si la nueva carga es similar o es diferente de la carga anterior. Simplemente recopila información sobre la nueva carga y permite que el entrenamiento de relevancia continúe en los conjuntos de archivos nuevos y anteriores. 
    
- Cuando hay varios problemas en el entrenamiento de relevancia, así como problemas tras el cálculo del lote, el proceso de puesta en marcha se realiza una vez para todos los problemas y los resultados se calculan y se muestran para cada problema.
    
> [!NOTE]
> El tamaño de la muestra de puesta al día puede variar. Depende del tamaño de la nueva carga con respecto a las cargas anteriores y del número de muestras completadas antes de agregar la nueva carga. La muestra de puesta en marcha suele ser un conjunto de 200 a 2.000 archivos de la nueva carga. 
  
> [!TIP]
> La puesta en marcha detiene cualquier otra tarea y requiere un etiquetado y revisión del archivo individual. Por lo tanto, puede reducir la sobrecarga al agregar archivos nuevos en lotes grandes. 
  
## <a name="adding-a-new-file-load-using-catch-up-and-rolling-loads"></a>Adición de una nueva carga de archivos mediante la puesta en marcha y las cargas graduales

1. En la **pestaña \> configuración de relevancia** para la relevancia, seleccione **carga**.
    
2. En cargar **Administración**, haga clic **+** en el icono para agregar una carga. Se muestra un mensaje de confirmación. 
    
3. Haga clic en **sí** para continuar. Se muestra el cuadro de diálogo **Agregar nueva carga** . 
    
    > [!NOTE]
    > Solo se puede Agregar una nueva carga si se han realizado acciones con la carga anterior. 
  
4. En el cuadro de diálogo **Agregar nueva carga** , escriba la información en **nombre de carga** y **Descripción** y, a continuación, haga clic en **Aceptar**. La exhibición avanzada de documentos electrónicos agrega una nueva carga.
    
5. Para importar el nuevo archivo de carga, haga clic en **Agregar archivos**. Todos los archivos nuevos se agregan a esta carga. Una vez que la exhibición avanzada de documentos electrónicos importa los archivos, reconoce el escenario de cargas de rodadura e indica la puesta en marcha como paso siguiente.
    
6. Haga clic en **puesta en marcha** en la parte inferior del cuadro de diálogo para ejecutar el escenario. 
    
    Se crea un conjunto único de puesta en marcha, que suele contener de 200 a 2.000 archivos de la nueva carga, para todos los problemas que permitan el etiquetado simultáneo de archivos.
    
    Se proporcionan detalles sobre si las cargas son similares o distintas, si la exhibición de documentos electrónicos avanzada se combina o divide automáticamente las cargas, e información sobre el procesamiento en el paso siguiente.
    
    A continuación, puede etiquetar archivos y ejecutar una operación de cálculo. El etiquetado permite que la relevancia determine si las cargas son similares o distintas, y le permite seguir trabajando en el nuevo conjunto de archivos.
    
7. Una vez revisado el conjunto de la puesta en marcha, vea el seguimiento de la **relevancia \> ** de los resultados de la puesta al día. 
    
1. Si se agregó la nueva carga de archivos durante el entrenamiento de relevancia (es decir, el problema todavía no ha pasado por el cálculo del lote), **continúe con el aprendizaje** en el paso siguiente, independientemente de los resultados de la puesta en marcha. 
    
    Las cargas nuevas y anteriores se procesan como una carga y el entrenamiento de relevancia sigue en el conjunto de United. Ha terminado con este procedimiento y puede continuar con el aprendizaje de relevancia. 
    
2. Si la nueva carga se agregó después del cálculo por lotes, continúe con los pasos siguientes.
    
8. Para las nuevas cargas agregadas después del cálculo por lotes, la exhibición avanzada de documentos electrónicos determina si la nueva carga es similar o diferente de las cargas anteriores, como se indica a continuación:
    
1. Si se considera que las cargas son similares: no es necesaria ninguna formación adicional de relevancia. El panel muestra el siguiente paso recomendado es ejecutar * * cálculo por lotes * * de nuevo para calcular los resultados de relevancia para la nueva carga. Se encontraron cargas similares, por lo que el análisis de clasificado anterior puede ejecutarse en los nuevos archivos. 
    
2. Si se encontraron cargas distintas: es necesario más aprendizaje de relevancia y el siguiente paso es la decisión de puesta al día. Seleccione una decisión de puesta en marcha de la siguiente manera:
    
    Si selecciona **cargas de fusión**, la exhibición avanzada de documentos electrónicos combina cargas anteriores y nuevas para el conjunto de entrenamiento. Aunque la primera carga pasó a través del cálculo por lotes, se necesita más formación. Continuar la formación de cargas nuevas y anteriores juntas. El cálculo del lote se ejecutará de nuevo y se omitirán los resultados del cálculo del lote anterior. Elija esta selección cuando se pueden actualizar los resultados de relevancia para las cargas existentes, por ejemplo, cuando no se ha iniciado la revisión de las cargas de archivos existentes.
    
    Si selecciona **cargas divididas**, continúe el aprendizaje de relevancia solo en la nueva carga. En este caso, los resultados de cálculo del lote anteriores se conservarán tal cual. Elija esta opción si los resultados de relevancia existentes para cargas existentes no se pueden volver a calcular, por ejemplo, si ya se ha iniciado la revisión de las cargas existentes. Los resultados de relevancia se administran de forma independiente desde este punto hacia adelante y no se pueden combinar.
    
3. Haga clic en **continuar formación**.
    
## <a name="see-also"></a>Vea también

[eDiscovery avanzado de Office 365](office-365-advanced-ediscovery.md)
  
[Definir asuntos y asignar usuarios](define-issues-and-assign-users.md)
  
[Definir palabras clave resaltadas y opciones avanzadas](define-highlighted-keywords-and-advanced-options.md)

