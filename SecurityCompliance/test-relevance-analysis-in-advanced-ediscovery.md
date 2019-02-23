---
title: Probar análisis de relevancia en eDiscovery avanzado de Office 365
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
ms.assetid: 1b092f7c-ea55-44f5-b419-63f3458fd7e0
description: 'Obtenga información sobre cómo usar la pestaña prueba tras el cálculo por lotes en Office 365 Advanced eDiscovery para probar, comparar y validar la calidad general de procesamiento.  '
ms.openlocfilehash: 735a6d8088b4696e2ebc348db435a11914bd0b10
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/23/2019
ms.locfileid: "30215840"
---
# <a name="test-relevance-analysis-in-office-365-advanced-ediscovery"></a>Probar análisis de relevancia en eDiscovery avanzado de Office 365

> [!NOTE]
> Para usar eDiscovery avanzado, su organización necesita una suscripción de Office 365 E3 con el complemento Cumplimiento avanzado, o bien una suscripción de E5. Si no tiene ese plan y quiere probar eDiscovery avanzado, puede [registrarse para una prueba de Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279). 
  
La pestaña prueba de eDiscovery avanzado permite probar, comparar y validar la calidad general de procesamiento. Estas pruebas se realizan después del cálculo por lotes. Al etiquetar los archivos de la colección, un experto realiza la última decisión sobre si cada archivo etiquetado es realmente relevante para el caso. 
  
En escenarios únicos o de varios problemas, las pruebas se realizan normalmente por problema. Los resultados se pueden ver después de cada prueba y los resultados de la prueba se pueden volver a usar con los archivos de prueba de ejemplo especificados.
  
## <a name="testing-the-rest"></a>Probar el resto

La prueba "probar el resto" se usa para validar las decisiones de selección, por ejemplo, para revisar solo los archivos por encima de una puntuación de límite de relevancia específica basada en los resultados avanzados de eDiscovery avanzado. El experto revisa un ejemplo de archivos con una puntuación de límite seleccionada para evaluar el número de archivos relevantes dentro de ese conjunto.
  
Esta prueba proporciona estadísticas y una comparación entre el conjunto de revisión y la prueba de la población de REST. Los resultados del conjunto de revisión son los que se calculan por relevancia durante la formación. Los resultados incluyen cálculos, basados en la configuración y los parámetros de entrada, como:
  
- Probar estadísticas de muestra del número de archivos de una muestra e identificado archivos relevantes. 
    
- Comparación tabular de los parámetros de población del conjunto de revisión y el resto, por ejemplo, el número de archivos, el número estimado de archivos relevantes, la riqueza estimada y el costo medio de buscar un archivo relevante adicional. El administrador puede establecer la configuración del parámetro cost.
    
1. Abra la **pestaña \> prueba de relevancia** . 
    
2. En la pestaña **prueba** , haga clic en **nueva prueba**. Se muestra el cuadro de diálogo **crear prueba** , tal como se muestra en el siguiente ejemplo. 
    
    ![Resultados de Probar el resto de relevancia](media/46e6898a-f929-4fd0-88d9-6f91d04b6ce2.png)
  
3. En **nombre**de la prueba y **Descripción**, escriba el nombre y la descripción.
    
4. En la lista **tipo de prueba** , seleccione **probar el resto**
    
5. En la lista **emisión/categoría** , seleccione el nombre del problema. 
    
6. En la lista **cargar** , seleccione la carga. 
    
7. En el **% lectura**, acepte el valor predeterminado o seleccione un valor para la puntuación de relevancia de corte. 
    
8. En **establecer tamaño**o aceptar el valor predeterminado. Tenga en cuenta que los iconos de restauración restaurarán los valores predeterminados.
    
9. Haga clic en **iniciar etiquetado**. Se genera una muestra de prueba.
    
10. Revise y etiquete cada uno de los archivos en la pestaña **etiqueta de relevancia \> ** y, cuando haya terminado, haga clic en **calcular**.
    
11. En la pestaña prueba, puede hacer clic en **ver resultados** para ver los resultados de la prueba. En la siguiente figura se muestra un ejemplo. 
    
    ![Resultados de Probar el resto](media/b95744a9-047d-4c29-992d-04fa7e58e58a.png)
  
En la figura anterior, la sección **parámetros de ejemplo** de la tabla contiene detalles sobre el número de archivos del ejemplo etiquetado por el experto y el número de archivos relevantes que se encuentran en ese ejemplo. 
  
La sección **parámetros** de rellenado de la tabla contiene los resultados de la prueba, incluido el rellenado de la revisión del conjunto de archivos con una puntuación inferior al límite seleccionado y el rellenado "el resto" de los archivos con una puntuación superior al límite seleccionado. Para cada población, se muestran los siguientes resultados: 
  
- Incluye archivos con el%-límite de lectura deClarados
    
- El número total de archivos 
    
- El número estimado de archivos relevantes 
    
- La riqueza estimada 
    
- El costo medio de revisión de buscar otro archivo relevante
    
## <a name="testing-the-slice"></a>Prueba del segmento

La prueba "probar el sector" realiza una prueba similar a la prueba "probar el resto", pero con un segmento del conjunto de archivos tal y como se especifica por% de lectura de relevancia.
  
1. Abra la **pestaña \> prueba de relevancia** . 
    
2. En la pestaña **prueba** , haga clic en **nueva prueba**. Se muestra el cuadro de diálogo **crear prueba** . 
    
3. En **nombre** de la prueba y **Descripción**, escriba la información.
    
4. En la lista **tipo de prueba** , seleccione **probar el sector**.
    
5. En la lista de **problemas** , seleccione el nombre del problema. 
    
6. En la lista **cargar** , seleccione la carga. 
    
7. En **leer% entre**, acepte los valores predeterminados de rango bajo y alto o seleccione valores para los resultados de relevancia de corte. 
    
8. En **establecer tamaño**, seleccione un valor o acepte el valor predeterminado.
    
    Los iconos de restauración restaurarán el valor predeterminado.
    
9. Haga clic en **iniciar etiquetado**. Se genera una muestra de prueba.
    
10. Revise y etiquete cada uno de los archivos en la pestaña **etiqueta de relevancia \> ** y, cuando haya terminado, haga clic en **calcular**. 
    
11. En la pestaña prueba, puede hacer clic en **ver resultados** para ver los resultados de la prueba. 
    
## <a name="see-also"></a>Vea también

[eDiscovery avanzado de Office 365](office-365-advanced-ediscovery.md)
  
[Descripción de la evaluación en relevancia](assessment-in-relevance-in-advanced-ediscovery.md)
  
[Etiquetado y evaluación](tagging-and-assessment-in-advanced-ediscovery.md)
  
[Aprendizaje de etiquetas y relevancia](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[Seguimiento del análisis de relevancia](track-relevance-analysis-in-advanced-ediscovery.md)
  
[Decisiones basadas en los resultados](decision-based-on-the-results-in-advanced-ediscovery.md)

