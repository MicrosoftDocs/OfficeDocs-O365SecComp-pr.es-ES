---
title: Aprendizaje de la etiqueta y la relevancia en Office 365 Advanced eDiscovery
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 9/14/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 8576cc86-d51b-4285-b54b-67184714cc62
description: 'Obtenga información sobre los pasos para etiquetar y, a continuación, trabaje con una muestra de aprendizaje de 40 archivos durante la fase de formación de relevancia de Office 365 Advanced eDiscovery.  '
ms.openlocfilehash: 82380acc2ea90a600a3dd14f58c6d9bf0a06a1a6
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/17/2019
ms.locfileid: "34158352"
---
# <a name="tagging-and-relevance-training-in-office-365-advanced-ediscovery"></a>Aprendizaje de la etiqueta y la relevancia en Office 365 Advanced eDiscovery

> [!NOTE]
> Para usar eDiscovery avanzado, su organización necesita una suscripción de Office 365 E3 con el complemento Cumplimiento avanzado, o bien una suscripción de E5. Si no tiene ese plan y quiere probar eDiscovery avanzado, puede [registrarse para una prueba de Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279). 
  
En este tema se describe el procedimiento para trabajar con el módulo de aprendizaje de relevancia para la exhibición avanzada de documentos electrónicos. 
  
Una vez completada la evaluación en la exhibición avanzada de documentos electrónicos y especifica la fase de aprendizaje de relevancia, se incluye una muestra de formación de 40 archivos en la pestaña etiqueta para el etiquetado. 
  
## <a name="performing-relevance-training"></a>Realizar entrenamiento de relevancia

1. En la **pestaña \> etiqueta de relevancia** , el panel etiquetado se muestra de forma predeterminada en el panel izquierdo y se muestran los archivos de ejemplo, uno por vez, para el etiquetado. 
    
    ![Panel de etiquetas de relevancia](media/0cf19ab4-b427-4a7f-8749-0f4ed9afaf58.png)
  
    En la ficha **etiqueta** , se muestra el nombre para mostrar del archivo. Puede ser la ruta de acceso, el asunto del correo electrónico, el título o el nombre definido por el usuario. El identificador, la ruta de acceso de archivo o la ruta de acceso de texto se pueden copiar haciendo clic con el botón secundario en la ruta de acceso del archivo. 
    
    En las estadísticas de etiquetado de pestañas de **etiquetas** se muestra el número de ejemplo de archivo (en la parte superior del panel izquierdo), el número del archivo que se muestra actualmente de los archivos totales en el ejemplo (parte inferior del panel derecho) y el número total actual de archivos etiquetados en el ejemplo (parte inferior de t el panel izquierdo), que cambia a medida que se etiquetan los archivos. Esto se aplica a cualquier etiquetado de relevancia realizado, ya sea en evaluación, formación, puesta en marcha o prueba. 
    
    Los iconos que indican la existencia de comentarios, etiquetas y archivos de familia se muestran en la vista de archivo en una barra situada encima del archivo.
    
2. Determine la relevancia del archivo para el problema de caso y etiquete el archivo con los botones de iconos de opción de etiquetado o con los métodos abreviados de teclado, como se muestra en la siguiente tabla:
    
| |
|**Opción de etiquetado**|**Descripción**|**Método abreviado de teclado**|**Para varios problemas-método abreviado de teclado de etiqueta masiva**|
|:-----|:-----|:-----|:-----|
|R  <br/> |Metabolito  <br/> |Z  <br/> |Mayús + Z  <br/> |
|Nº  <br/> |No relevante  <br/> |X  <br/> |Mayús + X  <br/> |
|Skip  <br/> |Skip  <br/> |C  <br/> |Mayús + A  <br/> |
   
  - Cuando hay varios problemas para un archivo, después de marcar un problema, la selección se mueve al siguiente problema (si lo hay). 
    
  - Las palabras clave definidas por el administrador o el administrador de casos al resaltar palabras clave \> (palabras clave resaltadas de configuración de relevancia), se mostrarán (en los colores especificados) para ayudar a identificar los archivos relevantes al etiquetar. Si una palabra clave tiene un doble subrayado, se puede hacer clic para mostrar una sugerencia de herramienta con la descripción de la palabra clave. 
    
    De forma opcional, en la pestaña **etiqueta** , haga clic en **configuración de etiqueta** para establecer las siguientes opciones: 
    
    ![Configuración de etiquetas de relevancia](media/533e89fa-7eb4-409e-ab07-f5aab9296dd8.png)
  
  - **Etiqueta masiva**: Use esta opción para asignar varios problemas a un archivo; para ello, seleccione **todos** para establecer la etiqueta del archivo seleccionado para todos los problemas (invalida los problemas ya etiquetados) o seleccione **el resto** para aplicar la etiqueta a los demás problemas sin etiquetar. La opción seleccionada permanece en vigor para todos los casos de este usuario hasta que la modifica el usuario (la configuración es por usuario para todos los casos del usuario). 
    
  - **Etiqueta automática**: Active esta casilla para establecer otros problemas de un archivo como no relevante después de un único etiquetado relevante.
    
  - **Avance automático**: Active esta casilla de verificación para mover la selección de archivos que se muestra al siguiente archivo al etiquetar el último o único problema sin etiquetar. 
    
    Los archivos omitidos no se tendrán en cuenta para la formación de relevancia y la puntuación de relevancia.
    
3. Los comentarios de texto libre, asociados a un archivo, se pueden ver y editar a través de la opción **Comentario** en la lista desplegable panel izquierdo. (opcional) 
    
4. Las directrices para la etiquetación se pueden ver seleccionando la opción **pautas de etiquetado** en la lista desplegable del panel izquierdo. 
    
5. Cuando termine de etiquetar todos los archivos de la lista y esté listo para calcular los resultados, haga clic en **calcular**. Se muestra la pestaña **seguimiento** . 
    
## <a name="working-with-the-sample-files-list"></a>Trabajar con la lista de archivos de ejemplo

La lista de archivos de muestra le permite ver una lista de los archivos en un ejemplo de aprendizaje y realizar diversas acciones en uno o más archivos. En la ficha **etiqueta** de **relevancia** \> , el panel **archivos de ejemplo** izquierdo muestra una lista de archivos de ejemplo para el procesamiento con procesos de evaluación, formación, puesta en marcha e incoherencias. 
  
1. En la **ficha \> etiqueta de relevancia** , seleccione los archivos de ejemplo en la lista desplegable del panel izquierdo. Los archivos de ejemplo se muestran en el panel izquierdo. 
    
    ![Lista de archivos de ejemplo de etiqueta de relevancia](media/fd058bdd-645a-4af1-a1eb-bff08581cb18.png)
  
2. Seleccione un ejemplo o un número de archivo específico especificando o seleccionando su número en los cuadros **muestra** o **archivo** . 
    
  -   - Un número de secuencia de archivo aparece en la columna izquierda de la lista de archivos que se muestra en la ficha **etiqueta** . Al hacer clic en el encabezado, el orden original mostrado de los archivos vuelve a su orden original. 
    
  - Al hacer clic en una fila de archivo, se muestra su contenido en el panel derecho.
    
  - Desplácese entre los archivos del ejemplo actual mediante las opciones de la barra de menús inferior. Además, los métodos abreviados de teclado de navegación están disponibles:
    
    Para desplazarse al primer archivo del ejemplo: Mayús + Ctrl +\<
    
    Para ir al archivo anterior en el ejemplo: Mayús +\<
    
    Para ir al siguiente archivo del ejemplo: Mayús +\>
    
    Para navegar hasta el último archivo del ejemplo: Mayús + Ctrl +\>
    
## <a name="see-also"></a>Vea también

[eDiscovery avanzado de Office 365](office-365-advanced-ediscovery.md)
  
[Descripción de la evaluación en relevancia](assessment-in-relevance-in-advanced-ediscovery.md)
  
[Etiquetado y evaluación](tagging-and-assessment-in-advanced-ediscovery.md)
  
[Seguimiento del análisis de relevancia](track-relevance-analysis-in-advanced-ediscovery.md)
  
[Decisiones basadas en los resultados](decision-based-on-the-results-in-advanced-ediscovery.md)
  
[Prueba del análisis de relevancia](test-relevance-analysis-in-advanced-ediscovery.md)

