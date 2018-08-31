---
title: Probar análisis de relevancia en eDiscovery avanzado de Office 365
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
ms.assetid: 1b092f7c-ea55-44f5-b419-63f3458fd7e0
description: 'Obtenga información sobre cómo usar la pestaña prueba después del cálculo de lote en Office 365 avanzada exhibición de documentos electrónicos para probar, comparar y validar la calidad total de procesamiento.  '
ms.openlocfilehash: 782859fe3b6bb3d00945c477928131cd1154446d
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22536215"
---
# <a name="test-relevance-analysis-in-office-365-advanced-ediscovery"></a>Probar análisis de relevancia en eDiscovery avanzado de Office 365

> [!NOTE]
> Exhibición de documentos electrónicos avanzada requiere un E3 de Office 365 con el complemento de cumplimiento avanzadas o una suscripción E5 para su organización. Si no tiene ese plan y desea probar avanzada exhibición de documentos electrónicos, puede [registrarse y obtener una versión de prueba de Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279). 
  
La ficha de prueba de exhibición de documentos electrónicos avanzada permite probar, comparar y validar la calidad total de procesamiento. Estas pruebas se llevan a cabo después del cálculo por lotes. Al etiquetar los archivos en la colección, con un experto hace que la sentencia firme sobre si es realmente relevante para el caso de cada archivo con etiqueta. 
  
En los escenarios único y de varios problemas, normalmente se realizan pruebas por el problema. Los resultados se pueden ver después de cada prueba, y pueden ser se han rediseñado los resultados de la prueba con los archivos de prueba de ejemplo especificado.
  
## <a name="testing-the-rest"></a>Probar el resto

La prueba de "Probar el resto" se usa para validar las decisiones de selección, por ejemplo, para revisar sólo archivos por encima de una puntuación del límite de la relevancia específico en función de los resultados de la exhibición de documentos electrónicos avanzada final. El experto revisa un ejemplo de los archivos en una puntuación de corte seleccionado para evaluar el número de archivos relevantes dentro de ese conjunto.
  
Esta prueba proporciona estadísticas y una comparación entre el conjunto de revisión y la prueba de la población de Rest. Los resultados del conjunto de revisión son aquellos calcula la relevancia durante la formación. Los resultados incluyen los cálculos, en función de configuración y los parámetros de entrada, tales como:
  
- Probar las estadísticas de ejemplo del número de archivos en una muestra e identificados archivos relevantes. 
    
- Comparación tabular de los parámetros de la población del conjunto de revisión y el resto, por ejemplo, el número de archivos, número estimado de archivos relevantes, estimado flexibilidad y el costo medio de buscar un archivo adicional relevante. Configuración de los parámetros de costos se puede establecer por el administrador.
    
1. Abrir la **la relevancia \> prueba** ficha. 
    
2. En la ficha **probar** , haga clic en **probar de nuevo**. Se muestra el cuadro de diálogo **crear pruebas** , tal como se muestra en el siguiente ejemplo. 
    
    ![Resultados de Probar el resto de relevancia](media/46e6898a-f929-4fd0-88d9-6f91d04b6ce2.png)
  
3. En **nombre de la prueba**y **Descripción**, escriba el nombre y la descripción.
    
4. En la lista **tipo de prueba** , seleccione **el resto de la prueba**
    
5. En la **problema / categoría** de lista, seleccione el nombre del problema. 
    
6. En la lista **de carga** , seleccione la carga. 
    
7. En **% lectura**, acepte el valor predeterminado o seleccione un valor para la puntuación de relevancia el límite. 
    
8. En **establecer tamaño**, o acepte el valor predeterminado. Tenga en cuenta que los iconos de restauración restaurará los valores predeterminados.
    
9. Haga clic en **Iniciar etiquetado**. Se genera una muestra de prueba.
    
10. Revisar y marcar cada uno de los archivos en el **la relevancia \> etiqueta** ficha y cuando haya terminado, haga clic en **calcular**.
    
11. En la ficha de prueba, puede hacer clic en **los resultados de la vista** para ver los resultados de pruebas. En la ilustración siguiente se muestra un ejemplo. 
    
    ![Resultados de Probar el resto](media/b95744a9-047d-4c29-992d-04fa7e58e58a.png)
  
En la figura anterior, la sección **parámetros de ejemplo** de la tabla contiene detalles sobre el número de archivos en el ejemplo de marcado por el experto y el número de archivos relevantes que se encuentran en ese ejemplo. 
  
La sección **parámetros de población** de la tabla contiene los resultados de pruebas, incluidos la población de conjunto de revisión de los archivos con una puntuación por debajo del límite seleccionado y población "El resto" de los archivos con una puntuación por encima del límite seleccionado. Para cada población, se muestran los resultados siguientes: 
  
- Incluye archivos con % lectura - corte indicado
    
- El número total de archivos 
    
- El número estimado de archivos relevantes 
    
- La flexibilidad estimada 
    
- El costo promedio de revisión de buscar el otro archivo relevante
    
## <a name="testing-the-slice"></a>Las pruebas del sector

"Probar el sector" prueba realiza pruebas similar a "Probar el resto" probar, pero a un segmento del archivo establecer tal como se especifica en % de lectura de la relevancia.
  
1. Abrir la **la relevancia \> prueba** ficha. 
    
2. En la ficha **probar** , haga clic en **probar de nuevo**. Se muestra el cuadro de diálogo **Crear prueba** . 
    
3. En **nombre de la prueba** y **Descripción**, escriba la información.
    
4. En la lista **tipo de prueba** , seleccione **prueba del sector**.
    
5. En la lista de **problemas** , seleccione el nombre del problema. 
    
6. En la lista **de carga** , seleccione la carga. 
    
7. En **% lectura entre**, acepte los valores de gama alta y baja de predeterminada o seleccione los valores para las puntuaciones el límite de la relevancia. 
    
8. En **establecer tamaño**, seleccione un valor o acepte el valor predeterminado.
    
    Los iconos de restauración restaurará el valor predeterminado.
    
9. Haga clic en **Iniciar etiquetado**. Se genera una muestra de prueba.
    
10. Revisar y marcar cada uno de los archivos en el **la relevancia \> etiqueta** ficha y cuando haya terminado, haga clic en **calcular**. 
    
11. En la ficha de prueba, puede hacer clic en **los resultados de la vista** para ver los resultados de pruebas. 
    
## <a name="see-also"></a>Vea también

[eDiscovery avanzado de Office 365](office-365-advanced-ediscovery.md)
  
[Evaluación de descripción en la relevancia](assessment-in-relevance-in-advanced-ediscovery.md)
  
[Etiquetas temáticas y evaluación](tagging-and-assessment-in-advanced-ediscovery.md)
  
[Etiquetado y formación de relevancia](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[Análisis de la relevancia de seguimiento](track-relevance-analysis-in-advanced-ediscovery.md)
  
[Decidir en función de los resultados](decision-based-on-the-results-in-advanced-ediscovery.md)

