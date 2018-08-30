---
title: Aprendizaje de relevancia y etiquetas en eDiscovery avanzado de Office 365
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
ms.assetid: 8576cc86-d51b-4285-b54b-67184714cc62
description: 'Obtenga información sobre los pasos necesarios para la etiqueta y, a continuación, trabajar con un ejemplo de recursos de aprendizaje de 40 archivos durante la fase de aprendizaje de la relevancia de exhibición de documentos electrónicos avanzada de Office 365.  '
ms.openlocfilehash: 90272452c8c1317957e542eba07bc43722f9c0e9
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22536231"
---
# <a name="tagging-and-relevance-training-in-office-365-advanced-ediscovery"></a>Aprendizaje de relevancia y etiquetas en eDiscovery avanzado de Office 365

> [!NOTE]
> Exhibición de documentos electrónicos avanzada requiere un E3 de Office 365 con el complemento de cumplimiento avanzadas o una suscripción E5 para su organización. Si no tiene ese plan y desea probar avanzada exhibición de documentos electrónicos, puede [registrarse y obtener una versión de prueba de Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279). 
  
En este tema se describe el procedimiento para trabajar con el módulo de capacitación de la relevancia de exhibición de documentos electrónicos avanzadas. 
  
Después de evaluación se completa en la exhibición de documentos electrónicos avanzada y escriba la fase de aprendizaje de relevancia, se pone un ejemplo de recursos de aprendizaje de 40 archivos en la ficha de etiqueta para el etiquetado. 
  
## <a name="performing-relevance-training"></a>Realización de aprendizaje de relevancia

1. En el **la relevancia \> etiqueta** ficha, el panel etiquetado se muestra de forma predeterminada en el panel izquierdo y el ejemplo de los archivos se muestran, uno a la vez para el etiquetado. 
    
    ![Panel de etiquetas de relevancia](media/0cf19ab4-b427-4a7f-8749-0f4ed9afaf58.png)
  
    En la ficha **etiqueta** , se muestra el nombre del archivo para mostrar. Podría tratarse de la ruta de acceso, el asunto de correo electrónico, el título o el nombre definido por el usuario. El botón secundario en la ruta del archivo se puede copiar el identificador, la ruta de acceso de archivo o la ruta de acceso de texto. 
    
    La ficha **etiqueta** etiquetado estadísticas mostrar el número de ejemplo de archivo (en la parte superior del panel izquierdo), el número del archivo que se muestra actualmente fuera de los archivos de totales en el ejemplo de (desde la parte inferior del panel de la derecha) y el número total actual de los archivos con etiqueta en el ejemplo de (parte inferior de t panel izquierdo), que cambia al etiquetar los archivos. Esto se aplica a cualquier etiquetado de relevancia hecho, ya sea en prueba, aprendizaje, ponerse al día o evaluación. 
    
    Iconos que indican la existencia de comentarios, etiquetas y archivos de familia se muestran en la vista de archivo de una barra por encima del archivo.
    
2. Determinar la relevancia del archivo para el problema de mayúsculas y minúsculas y la etiqueta el archivo mediante los botones de icono de opción etiquetado o métodos abreviados de teclado, tal como se muestra en la siguiente tabla:
    
| |
|**Opción de etiquetas temáticas**|**Descripción**|**Método abreviado de teclado**|**Para varios problemas - masiva de método abreviado de teclado de etiqueta**|
|:-----|:-----|:-----|:-----|
|R  <br/> |Relevantes  <br/> |Z  <br/> |MAYÚS + Z  <br/> |
|N  <br/> |No relevantes  <br/> |X  <br/> |MAYÚS + X  <br/> |
|Omitir  <br/> |Omitir  <br/> |C  <br/> |MAYÚS + A  <br/> |
   
  - Si hay varios problemas de un archivo, después de marcar un problema, la selección se desplaza al siguiente problema (si hay alguno). 
    
  - Palabras clave que se han definido por el administrador o administrador de mayúsculas y minúsculas cuando el resaltado de las palabras clave (el programa de instalación de la relevancia \> resaltado de palabras clave), se mostrará (en colores especificados) para ayudar a identificar los archivos relevantes al etiquetado. Si una palabra clave tiene doble subrayado, puede hacer clic para mostrar una información sobre herramientas con descripción de la palabra clave. 
    
    De forma opcional, en la ficha **etiqueta** , haga clic en **configuración de etiqueta** para establecer las siguientes opciones: 
    
    ![Configuración de etiquetas de relevancia](media/533e89fa-7eb4-409e-ab07-f5aab9296dd8.png)
  
  - **Etiqueta de forma masiva**: Use esta opción para asignar varios problemas para un archivo mediante la selección de **todas las** para establecer la etiqueta para el archivo seleccionado para todos los problemas (reemplazos ya etiquetado problemas) o seleccionando **el resto** para aplicar la etiqueta a los problemas sin etiquetas restantes. La opción seleccionada permanece en vigor para todos los casos de este usuario hasta que se ha cambiado por ese usuario (el valor es por usuario para los casos de todos los del usuario). 
    
  - **Etiqueta automático**: Active esta casilla de verificación para establecer otros problemas de un archivo como no relevantes después de un único etiquetado relevante.
    
  - **Avance automático**: Active esta casilla de verificación para mover la selección de archivo que se muestra en el siguiente archivo al etiquetar el último o sólo problema sin etiquetas. 
    
    Los archivos omitidos no se considerarán para la formación de la relevancia y la relevancia de los resultados con fines.
    
3. Comentarios de texto libre, asociados con un archivo, pueden verse y modificarse a través de la opción de **comentario** en la lista desplegable de panel de la izquierda. (opcional) 
    
4. Instrucciones para el etiquetado se pueden ver seleccionando la opción **etiquetado instrucciones** en la lista desplegable de panel de la izquierda. 
    
5. Después de finalizar el etiquetado de todos los archivos en la lista y está listo para calcular los resultados, haga clic en **calcular**. Se muestra la ficha **seguimiento** . 
    
## <a name="working-with-the-sample-files-list"></a>Trabajar con la lista de los archivos de ejemplo

La lista de los archivos de ejemplo permite ver una lista de los archivos de ejemplo de entrenamiento y realizar diversas acción en uno o varios archivos. En la **relevancia** \> ficha de **etiqueta** , el panel izquierdo de **archivos de ejemplo** muestra una lista de archivos de ejemplo para los procesos de procesamiento con evaluación, aprendizaje, ponerse al día y las incoherencias. 
  
1. En el **la relevancia \> etiqueta** ficha, seleccione los archivos de ejemplo en la lista desplegable de panel de la izquierda. Los archivos de ejemplo se muestran en el panel izquierdo. 
    
    ![Lista de archivos de ejemplo de etiqueta de relevancia](media/fd058bdd-645a-4af1-a1eb-bff08581cb18.png)
  
2. Seleccione un número específico de ejemplo o de archivo, escriba o seleccione su número en los cuadros de **ejemplo** o **archivo** . 
    
  -   - Un número de secuencia de archivo se muestra en la columna izquierda de la lista de archivos que se muestra en la ficha **etiqueta** . Al hacer clic en el encabezado, el orden mostrado original de los archivos se devuelve a su orden original. 
    
  - Al hacer clic en una fila de archivo, su contenido muestra en el panel derecho.
    
  - Navegar entre archivos en el ejemplo actual mediante el uso de las opciones de barra de menú inferiores. Además, los métodos abreviados de teclado de navegación están disponibles:
    
    Para navegar hasta el primer archivo en el ejemplo: Mayús + Ctrl +\<
    
    Para navegar hasta el archivo en el ejemplo anterior: MAYÚS +\<
    
    Para navegar hasta el archivo en el ejemplo siguiente: MAYÚS +\>
    
    Para navegar hasta el último archivo en el ejemplo: Mayús + Ctrl +\>
    
## <a name="see-also"></a>Vea también

[eDiscovery avanzado de Office 365](office-365-advanced-ediscovery.md)
  
[Evaluación de descripción en la relevancia](assessment-in-relevance-in-advanced-ediscovery.md)
  
[Etiquetas temáticas y evaluación](tagging-and-assessment-in-advanced-ediscovery.md)
  
[Análisis de la relevancia de seguimiento](track-relevance-analysis-in-advanced-ediscovery.md)
  
[Decidir en función de los resultados](decision-based-on-the-results-in-advanced-ediscovery.md)
  
[Las pruebas de análisis de la relevancia](test-relevance-analysis-in-advanced-ediscovery.md)

