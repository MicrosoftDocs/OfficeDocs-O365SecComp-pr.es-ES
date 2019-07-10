---
title: Etiquetado y evaluación en Office 365 Advanced eDiscovery
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 09/14/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: b5c82de7-ed2f-4cc6-becd-db403faf4d18
description: 'Revise los pasos para realizar la formación sobre la evaluación, incluidos los archivos de etiquetado y la revisión de los resultados de la evaluación en eDiscovery avanzado de Office 365. '
ms.openlocfilehash: 067f8933bd7fc1286e468d664bf4dbd754e64f00
ms.sourcegitcommit: 32ecff689ae32c59a39b7633ca0f36a304e7516e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/09/2019
ms.locfileid: "35600743"
---
# <a name="tagging-and-assessment-in-office-365-advanced-ediscovery"></a>Etiquetado y evaluación en Office 365 Advanced eDiscovery

> [!NOTE]
> Para usar eDiscovery avanzado, su organización necesita una suscripción de Office 365 E3 con el complemento Cumplimiento avanzado, o bien una suscripción de E5. Si no tiene ese plan y quiere probar eDiscovery avanzado, puede [registrarse para una prueba de Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279). 
  
En esta sección se describe el procedimiento para el módulo de evaluación de relevancia de eDiscovery avanzado. 
  
## <a name="performing-assessment-training-and-analysis"></a>Realización de análisis y aprendizaje de evaluación

1. En la **pestaña \> seguimiento de relevancia** , haga clic en **evaluación** para iniciar la evaluación de casos. 
    
    Por ejemplo, en este procedimiento, se crea un conjunto de evaluación de ejemplo de 500 archivos y se muestra la pestaña **etiqueta** , que contiene el panel etiquetado, el contenido del archivo mostrado y otras opciones de etiquetado. 
    
    ![Pestaña de etiqueta de relevancia para la evaluación](media/c8acf891-b1cd-4344-816c-eabb8cbbe742.png)
  
2. Revise cada archivo de la muestra, determine la relevancia del archivo para cada problema de caso y etiquete el archivo con los botones relevancia (R), no relevante (NR) y omitir en el panel de **etiquetado** . 
    
    > [!NOTE]
    >  La evaluación requiere 500 de archivos etiquetados. Si los archivos se "omiten", recibirás más archivos para etiquetar. 
  
3. Después de etiquetar todos los archivos en el ejemplo, haga clic en **calcular**. 
    
    El margen y la riqueza del error actual de la evaluación se calculan y muestran en la pestaña **seguimiento de relevancia** , con detalles expandidos por problema, tal como se muestra a continuación. Para obtener más información sobre este cuadro de diálogo, vea la sección posterior "revisión de los resultados de las evaluaciones". 
    
    ![Seguimiento de relevancia: evaluación](media/da911ba5-8678-40d6-9ad5-fd0b058355c1.png)
  
    > [!TIP]
    > De forma predeterminada, se recomienda continuar con el paso siguiente predeterminado cuando se haya completado el indicador de progreso de la evaluación para el problema, lo que indica que se ha revisado la muestra de evaluación y que se han etiquetado los archivos relevantes necesarios. De lo contrario, si desea ver los resultados de la ficha **seguimiento** y controlar el margen de error y el siguiente paso, haga clic en **modificar** junto al **siguiente paso**, seleccione **continuar evaluación**y, a continuación, haga clic en **Aceptar**. > 
  
1. Haga clic en **modificar** a la derecha de la casilla **evaluación** para ver y especificar los parámetros de evaluación por problema. Se muestra un cuadro de diálogo de **nivel de evaluación** para cada problema, tal como se muestra en el ejemplo siguiente: 
    
    ![Problema de caso del nivel de evaluación](media/b7113fef-d125-4617-ae1b-c9eb0bf79aec.png)
  
    Los siguientes parámetros para el problema se calculan y se muestran en el cuadro de diálogo **nivel de evaluación** : 
    
    **Margen de error de destino para estimaciones de recuperación**: según este valor, se calcula el número estimado de archivos adicionales necesarios para la revisión. El margen usado para la recuperación es superior al 75% y con un nivel de confianza de 95%. 
    
    Se **requieren archivos de evaluación adicionales**: indica el número de archivos necesarios si no se han cumplido los requisitos del margen de error actual. 
    
2. Para ajustar el margen de error actual y ver el efecto de los distintos márgenes de error (por problema):
    
1. En la lista **seleccionar problema** , seleccione un problema. 
    
2. En el **margen del error de destino para las estimaciones de recuperación**, escriba un nuevo valor.
    
3. Haga clic en **actualizar valores** para ver el impacto de los ajustes. 
    
3. Haga clic en **avanzadas** en el cuadro de diálogo **nivel de evaluación** para ver los siguientes parámetros y detalles adicionales: 
    
    ![Vista avanzada del problema de caso del nivel de evaluación](media/577d7e0e-95df-48c2-9dec-bdeab5e801d8.png)
  
    **Riqueza estimada**: riqueza estimada de acuerdo con los resultados de la evaluación actual
    
    **Para RECALL**recalld: de forma predeterminada, el margen de error de destino se aplica a RECALL por encima del 75%. Haga clic en **Editar** si desea cambiar este parámetro y controlar el margen de error en un intervalo diferente de valores de recuperación. 
    
    **Nivel de confianza**: de forma predeterminada, el margen de error recomendado para la confianza es del 95%. Haga clic en **Editar** si desea cambiar este parámetro. 
    
    **Margen de error de riqueza esperado**: dados los valores actualizados, este es el margen de error esperado de la riqueza, una vez que se han revisado todos los archivos de evaluación adicionales.
    
    Se **requieren archivos de evaluación adicionales**: dados los valores actualizados, el número de archivos de evaluación adicionales que deben revisarse para llegar al destino.
    
    **Total de archivos de evaluación necesarios**: dados los valores actualizados, los archivos de evaluación totales necesarios para la revisión.
    
    **Número previsto de archivos relevantes en la evaluación**: dados los valores actualizados, el número previsto de archivos relevantes en toda la evaluación después de revisar todos los archivos de evaluación adicionales.
    
4. Haga clic en **recalcular valores**, si se modifican los parámetros. Cuando haya terminado, si hay un problema, haga clic en **Aceptar** para guardar los cambios (o en **siguiente** cuando haya varios problemas para revisar o modificar y, a continuación, **Finalizar**). 
    
    Cuando hay varios problemas, una vez que se han revisado o ajustado todos los problemas, se muestra un cuadro de diálogo de **Resumen:** cuadro de diálogo de Resumen, tal como se muestra en el ejemplo siguiente. 
    
    ![Resumen del nivel de evaluación](media/4997b46d-10a5-4abc-b3b2-7b75a370eb9e.png)
  
    Una vez finalizada correctamente la evaluación, continúe con la siguiente fase del aprendizaje de relevancia.
    
## <a name="reviewing-assessment-results"></a>Revisión de los resultados de la evaluación

Después de etiquetar un ejemplo de evaluación, los resultados de la evaluación se calculan y se muestran en la pestaña seguimiento de relevancia.
  
Los siguientes resultados se muestran en la pantalla de la pista expandida: 
  
- Margen de error actual de la evaluación para estimaciones de recuperación
    
- Riqueza estimada
    
- Se requieren archivos de evaluación adicionales (para revisión)
    
El margen de error actual de la evaluación es el margen de error recomendado por eDiscovery avanzado. El número que se muestra para los "archivos de evaluación adicionales necesarios" corresponde a esa recomendación.
  
El indicador de progreso de la evaluación muestra el nivel de finalización de la evaluación, según el margen de error actual. Cuando se está realizando la evaluación, el usuario etiquetará otra muestra de evaluación.
  
Cuando el indicador de progreso de la evaluación muestra la evaluación como completada, significa que se ha completado la revisión de muestreo de la evaluación y que se han etiquetado los archivos relevantes. 
  
La pantalla expandida muestra el siguiente paso recomendado, las estadísticas de la evaluación y el acceso a los resultados detallados.
  
Cuando la riqueza es muy baja, el número de archivos de evaluación adicionales necesarios para alcanzar un número mínimo de archivos relevantes para producir estadísticas útiles es muy alto. La exhibición avanzada de documentos electrónicos le recomendará continuar con el aprendizaje. El indicador de progreso de la evaluación se verá sombreado y no habrá estadísticas disponibles. 
  
En ausencia de estabilización basada en estadísticas, habrá resultados con un nivel inferior de precisión y nivel de confianza. Sin embargo, estos resultados se pueden usar para buscar archivos relevantes cuando no es necesario conocer el porcentaje de archivos relevantes encontrados. De forma similar, este estado puede usarse para entrenar problemas con escasa riqueza, donde los resultados de relevancia pueden acelerar el acceso a los archivos relevantes para un problema específico.
  
> [!TIP]
> En la **pestaña \> seguimiento de relevancia** , la visualización de problemas expandida, están disponibles las siguientes opciones de visualización: > el paso siguiente recomendado, como **paso siguiente:** se puede omitir el etiquetado (por problema) haciendo clic en el botón **modificar** situado a la derecha. y, a continuación, seleccione un paso diferente en el **paso siguiente**. Cuando no se haya completado el indicador de progreso de la evaluación, la evaluación será la siguiente opción recomendada, para etiquetar más archivos de evaluación y aumentar la precisión de las estadísticas. > puede cambiar el margen de error y evaluar su impacto; para ello, haga clic en **modificar**y, en el **cuadro de diálogo nivel de evaluación**, cambie el **margen de error de destino para RECALL estimaciones**y haga clic en **actualizar valores**. Además, en este cuadro de diálogo, puede ver las opciones avanzadas haciendo clic en **avanzadas**. > puede ver estadísticas del nivel de evaluación adicional y su impacto haciendo clic en **Ver**. En el cuadro de diálogo resultados detallados mostrados, las estadísticas están disponibles por problema, cuando hay al menos 500 archivos de evaluación etiquetada y al menos 18 archivos se etiquetan como pertinentes para el problema. 
  
## <a name="see-also"></a>Vea también

[eDiscovery avanzado de Office 365](office-365-advanced-ediscovery.md)
  
[Descripción de la evaluación en relevancia](assessment-in-relevance-in-advanced-ediscovery.md)
  
[Aprendizaje de etiquetas y relevancia](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[Seguimiento del análisis de relevancia](track-relevance-analysis-in-advanced-ediscovery.md)
  
[Decisiones basadas en los resultados](decision-based-on-the-results-in-advanced-ediscovery.md)
  
[Prueba del análisis de relevancia](test-relevance-analysis-in-advanced-ediscovery.md)

