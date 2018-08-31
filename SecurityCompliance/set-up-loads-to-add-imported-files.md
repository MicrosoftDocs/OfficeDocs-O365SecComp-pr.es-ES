---
title: Configurar cargas para agregar archivos importados en eDiscovery avanzado de Office 365
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
ms.assetid: 0e0a9d04-294f-4f54-8bf1-b32d81345126
description: 'Revise los pasos para agregar los archivos importados a la última carga definido, o el lote, de los archivos antes de realizar la formación de relevancia de exhibición de documentos electrónicos avanzada de Office 365.  '
ms.openlocfilehash: 2c986578b969b671351930fd6939a90e3a821dc2
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22536719"
---
# <a name="set-up-loads-to-add-imported-files-in-office-365-advanced-ediscovery"></a>Configurar cargas para agregar archivos importados en eDiscovery avanzado de Office 365

> [!NOTE]
> Exhibición de documentos electrónicos avanzada requiere un E3 de Office 365 con el complemento de cumplimiento avanzadas o una suscripción E5 para su organización. Si no tiene ese plan y desea probar avanzada exhibición de documentos electrónicos, puede [registrarse y obtener una versión de prueba de Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279). 
  
En la exhibición de documentos electrónicos avanzada, una carga es un nuevo lote de archivos agregados a un caso. De forma predeterminada, se define una carga y todos los archivos importados se agregan a él. Antes de realizar la formación de relevancia, archivos importados deben agregarse a la carga. 
  
Tenga en cuenta los siguientes escenarios:
  
- Los archivos nuevos se conocen como similar a los archivos anteriores cargados en la base de datos de mayúsculas y minúsculas, o la carga de archivos anterior era un conjunto aleatorio de la colección de archivos. En este caso, agregue los archivos importados a la carga del archivo actual.
    
- Nuevos archivos son diferentes de los anteriores (por ejemplo, desde un origen diferente), o no tiene ningún conocimiento previo que son similares o diferentes a las cargas anteriores. En este escenario, agregar los archivos importados a una nueva carga de archivo. Exhibición de documentos electrónicos avanzada reconoce esto como un escenario de carga sucesivas, invoca un proceso de puesta al día, bloqueos de recursos de aprendizaje de la relevancia y cálculos de lote hasta que se complete ponerse al día, y la carga de nuevo es integrada y formación. 
    
## <a name="adding-imported-files-to-the-current-load"></a>Adición de archivos importados a la carga actual

Todos los archivos importados deben agregarse a una carga que va a procesar en la exhibición de documentos electrónicos avanzada. Los archivos importados se agregan a la última carga definida. Si importa archivos adicionales más adelante, también deben agregarse a la carga.
  
1. En el **la relevancia \> el programa de instalación de la relevancia** ficha, seleccione **las cargas**.
    
    ![Pestaña Cargas de configuración de relevancia](media/278aac7f-655f-462f-852a-6baa5d818768.png)
  
2. **Archivos de inclusión**: seleccione una opción para los archivos que se incluirán. De forma predeterminada, la adición de archivos a la carga actual se basa en la población de "Todos los archivos".
    
    > [!TIP]
    > Cargar todos los archivos sacrificados disponibles en la relevancia. Si tiene previsto cargar sólo un subconjunto de los archivos disponibles, póngase en primer lugar en contacto con soporte técnico, como subconjuntos de carga puede afectar negativamente al aprendizaje de la relevancia. 
  
3. En la **administración de cargas**, seleccione una carga.
    
4. Haga clic en **Agregar archivos**. Los archivos se agregan a la carga y se muestra un mensaje de confirmación. 
    
5. Haga clic en **Aceptar**.
    
Ahora se pueden procesar los archivos en la exhibición de documentos electrónicos avanzada la relevancia para los archivos de recursos de aprendizaje.
  
## <a name="editing-a-load-name-within-a-case"></a>Edición de un nombre de la carga dentro de un caso

Si se cambia el nombre de la carga, se recomienda usar un nombre que es importante para el caso.
  
1. En el **la relevancia \> el programa de instalación de la relevancia** ficha, seleccione **las cargas**.
    
2. En la lista de **administración de cargas** , seleccione una carga y haga clic en el icono **Editar** . Se muestra la ventana de carga de edición. 
    
3. Escriba los cambios y, a continuación, haga clic en **Aceptar**.
    
## <a name="adding-imported-files-to-a-new-load"></a>Adición de archivos importados a una nueva carga

Después de iniciar el aprendizaje de la relevancia o realizar cálculos de lote, es posible que desee importar y procesar un conjunto de archivos adicional. 
  
Durante la puesta al día, puede crear, etiquetar y analizar el conjunto de ponerse al día. Exhibición de documentos electrónicos avanzada compara su evaluación de archivos pertinente y no pertinente en la carga de nuevo a los de cargas anteriores. En función de los resultados, le pedirá que tomar decisiones de ponerse al día, si es necesario y avanzada de exhibición de documentos electrónicos proporciona recomendaciones basadas en la información de la relevancia devengada. 
  
Las sucesivas cargas y funcionalidad de puesta al día varían como sigue: 
  
- Cuando se importa un nuevo archivo de carga después de cálculo por lotes, exhibición de documentos electrónicos avanzada determina en qué medida se clasifican los archivos en las siguientes categorías:
    
  - Similar (homogéneo): no se requiere una ronda personalizada, nueva y de aprendizaje de la relevancia y el conocimiento acumulado de la carga anterior se puede aplicar "tal cual" a la carga de nuevo. 
    
  - DISTINCT (heterogéneo): se requiere una ronda personalizada, nueva y de aprendizaje de la relevancia y no se puede aplicar el conocimiento acumulado de la carga anterior. 
    
    Estos términos hacen referencia al nivel de similitud de archivos entre las cargas y no está dentro de las cargas. 
    
- Al importar un nuevo archivo de carga durante el curso de la relevancia (antes de cálculo por lotes), permite ponerse al día continuar formación de relevancia en el conjunto de archivos united. Exhibición de documentos electrónicos avanzada no estimar si la carga de nuevo es similar a o distinta de la carga anterior. Simplemente recopila información sobre la carga de nuevo y habilita la relevancia de recursos de aprendizaje continuar en los nuevos y anteriores conjuntos de archivos. 
    
- Cuando hay varios problemas en recursos de aprendizaje de la relevancia, así como problemas después de cálculo por lotes, el proceso de ponerse al día se lleva a cabo una vez para todos los problemas, y los resultados se calculan y se muestran para cada problema.
    
> [!NOTE]
> Puede variar el tamaño de la muestra de ponerse al día. Depende del tamaño de la carga de nuevo con respecto a las cargas anteriores y en el número de muestras completado antes de agregar la nueva carga. El ejemplo de ponerse al día normalmente es un conjunto de archivos de 200 a 2.000 desde la carga de nuevo. 
  
> [!TIP]
> Ponerse al día detiene cualquier otras tareas y requiere revisión y etiquetado de archivo individuales. Por lo tanto, puede reducir una sobrecarga cuando se agregan nuevos archivos por lotes de gran tamaño. 
  
## <a name="adding-a-new-file-load-using-catch-up-and-rolling-loads"></a>Adición de una nueva carga de archivo con puesta al día y sucesiva carga

1. En el **la relevancia \> el programa de instalación de la relevancia** ficha, seleccione **las cargas**.
    
2. En **administración de cargas**, haga clic en el **+** icono para agregar una carga. Se muestra un mensaje de confirmación. 
    
3. Haga clic en **Sí** para continuar. Se muestra el cuadro de diálogo **Agregar nueva carga** . 
    
    > [!NOTE]
    > Sólo se puede agregar una nueva carga si las acciones se realizaron a la carga anterior. 
  
4. En el cuadro de diálogo **Agregar nuevo de carga** , escriba información en **cargar el nombre** y **Descripción** y, a continuación, haga clic en **Aceptar**. Exhibición de documentos electrónicos avanzada agrega una nueva carga.
    
5. Para importar el nuevo archivo de carga, haga clic en **Agregar archivos**. Todos los archivos nuevos se agregan a esta carga. Después de exhibición de documentos electrónicos avanzada importa los archivos, reconoce el escenario de cargas sucesivas e indica ponerse al día como el siguiente paso.
    
6. Haga clic en **ponerse al día** en la parte inferior del cuadro de diálogo para ejecutar el escenario. 
    
    Un único conjunto de ponerse al día, que normalmente contiene los archivos de 200 a 2.000 de la carga de nuevo, se crea para que todos los problemas permitir que el etiquetado de archivo simultáneo.
    
    Se proporcionan detalles acerca de si las cargas son similares o distintos, si avanzada exhibición de documentos electrónicos a combinar o divide automáticamente las cargas e información con respecto al procesamiento en el paso siguiente.
    
    Puede, a continuación, los archivos de etiqueta y ejecutar una operación de calcular. El etiquetado permite la relevancia determinar si las cargas son similares o distintos y le permite continuar trabajando en el nuevo conjunto de archivos.
    
7. Una vez que se revisa el conjunto ponerse al día, ver **relevancia \> pista** para los resultados de ponerse al día. 
    
1. Si se ha agregado la nueva carga de archivo durante la formación de la relevancia (es decir, el problema no ha experimentado todavía cálculo por lotes), **aprendizaje continuar** es el siguiente paso, independientemente de los resultados de ponerse al día. 
    
    Se procesan las cargas anteriores y nueva como una carga y continúa la formación de la relevancia en el conjunto de united. Ahora ha terminado con este procedimiento y puede continuar la formación de relevancia. 
    
2. Si se ha agregado la nueva carga después del cálculo por lotes, continúe con los pasos siguientes.
    
8. Cargas nuevo agregadas después del cálculo por lotes, de exhibición de documentos electrónicos avanzada determina si la carga de nuevo es similar a o distintos de cargas anteriores, como se indica a continuación:
    
1. Si se han encontrado cargas de forma similar: no hay recursos de aprendizaje adicionales de relevancia es necesario. El panel muestra el siguiente paso recomendado es ejecutar ** por lotes cálculo ** nuevamente para calcular las puntuaciones de relevancia para la carga de nuevo. Se han encontrado cargas de forma similar, por lo que se puede ejecutar el análisis de clasificador anterior en los nuevos archivos. 
    
2. Si se han encontrado cargas distinto: formación más relevancia es necesario y el siguiente paso es decisión ponerse al día. Seleccione una decisión ponerse al día de la siguiente manera:
    
    Si selecciona **Combinar cargas**, exhibición de documentos electrónicos avanzada combina cargas anteriores y nueva para el conjunto de recursos de aprendizaje. Aunque la primera carga salió a través de cálculo por lotes, se necesitan más recursos de formación. Continuar la formación anterior y nueva carga juntos. Cálculo por lotes, a continuación, se ejecutará de nuevo y se deben omitir las puntuaciones de cálculo por lotes anteriores. Elija esta selección cuando las puntuaciones de la relevancia para cargas existentes pueden volver a calcularse, por ejemplo, cuando no ha iniciado la revisión de las cargas de archivos existente.
    
    Si selecciona **carga dividida**, continuar aprendizaje relevancia únicamente en la carga de nuevo. En esta instancia, las puntuaciones de cálculo de lote anteriores permanecerá tal y como está. Elija esta opción cuando las puntuaciones de la relevancia existentes para cargas existentes no se pueden volver a calcularse, por ejemplo, si ya ha iniciado la revisión de cargas existentes. Las puntuaciones de la relevancia se administran por separado desde este punto hacia adelante y no se pueden combinar.
    
3. Haga clic en **continuar formación**.
    
## <a name="see-also"></a>Vea también

[eDiscovery avanzado de Office 365](office-365-advanced-ediscovery.md)
  
[Definición de problemas y la asignación de usuarios](define-issues-and-assign-users.md)
  
[Definición de resaltado de las palabras clave y avanzadas opciones](define-highlighted-keywords-and-advanced-options.md)

