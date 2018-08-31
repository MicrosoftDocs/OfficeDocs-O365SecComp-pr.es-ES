---
title: Etiquetado y evaluación en eDiscovery avanzado de Office 365
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
ms.assetid: b5c82de7-ed2f-4cc6-becd-db403faf4d18
description: 'Revise los pasos para realizar la formación de evaluación, incluidos archivos de etiquetado y revisar los resultados de la evaluación de exhibición de documentos electrónicos avanzada de Office 365. '
ms.openlocfilehash: 0f67dd4780a29536888231f556c18fe887f230ba
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22536065"
---
# <a name="tagging-and-assessment-in-office-365-advanced-ediscovery"></a>Etiquetado y evaluación en eDiscovery avanzado de Office 365

> [!NOTE]
> Exhibición de documentos electrónicos avanzada requiere un E3 de Office 365 con el complemento de cumplimiento avanzadas o una suscripción E5 para su organización. Si no tiene ese plan y desea probar avanzada exhibición de documentos electrónicos, puede [registrarse y obtener una versión de prueba de Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279). 
  
En esta sección se describe el procedimiento para el módulo de evaluación de la relevancia de exhibición de documentos electrónicos avanzadas. 
  
## <a name="performing-assessment-training-and-analysis"></a>Realización de análisis y formación de evaluación

1. En el **la relevancia \> pista** ficha, haga clic en **evaluación** para iniciar la evaluación del caso. 
    
    Por ejemplo, con fines de este procedimiento, se crea un conjunto de evaluación de ejemplo de 500 archivos y se muestra la ficha **etiqueta** , que contiene el panel etiquetado, el contenido del archivo que se muestra y otras opciones de etiquetas temáticas. 
    
    ![Pestaña de etiqueta de relevancia para la evaluación](media/c8acf891-b1cd-4344-816c-eabb8cbbe742.png)
  
2. Revise cada archivo en el ejemplo, determinar la relevancia de un archivo por cada problema de mayúsculas y minúsculas y marcar el archivo mediante el Relevance (R), no relevante (n) y omitir los botones en el panel de **etiquetado** . 
    
    > [!NOTE]
    >  Evaluación requiere 500 archivos con etiqueta. Si se "omiten archivos", recibirá más archivos a la etiqueta. 
  
3. Después de etiquetar todos los archivos en el ejemplo, haga clic en **calcular**. 
    
    El margen de error actual de evaluación y la flexibilidad se calculan y se muestran en la ficha **Seguimiento de relevancia** , con detalles expandidas por el problema, tal y como se muestra a continuación. Obtener más detalles acerca de este cuadro de diálogo se describen en la sección posterior "Los resultados de las evaluaciones de revisión". 
    
    ![Seguimiento de relevancia: evaluación](media/da911ba5-8678-40d6-9ad5-fd0b058355c1.png)
  
    > [!TIP]
    > De forma predeterminada, se recomienda que realice el paso siguiente de forma predeterminada cuando haya finalizado el indicador de progreso de evaluación para el problema, que indica que se ha revisado el ejemplo de evaluación y etiquetaron suficientes archivos relevantes. > En caso contrario, si desea ver los resultados de la pestaña **seguimiento** y control el margen de error y el siguiente paso, haga clic en **Modificar** junto al **Paso siguiente**, seleccione **evaluación continuar**y, a continuación, haga clic en **Aceptar**. 
  
1. Haga clic en **Modificar** a la derecha de la casilla de verificación de **evaluación** para ver y especificar los parámetros de evaluación por el problema. Se muestra un cuadro de diálogo de **nivel de evaluación** para cada problema, tal como se muestra en el ejemplo siguiente: 
    
    ![Problema de caso del nivel de evaluación](media/b7113fef-d125-4617-ae1b-c9eb0bf79aec.png)
  
    Los siguientes parámetros para el problema se calculan y se muestran en el cuadro de diálogo **nivel de evaluación** : 
    
    **Calcula el margen de error de destino para la recuperación**: en función de este valor, se calcula el número estimado de archivos adicionales necesarios para revisar. El margen que se usa para recuperación es mayor que el 75% y con un nivel de confianza del 95%. 
    
    **Los archivos de evaluación adicionales necesarios**: indica cuántos más archivos son necesarios si no se cumplen los requisitos del margen de error actual. 
    
2. Para ajustar el margen de error actual y ver el efecto de los márgenes de error diferentes (por problema):
    
1. En la lista **Seleccione el problema** , seleccione un problema. 
    
2. En el **margen de error de destino para recuperación estima**, escriba un nuevo valor.
    
3. Haga clic en **Actualizar valores** para ver el impacto de los ajustes. 
    
3. Haga clic en **Avanzadas** en el cuadro de diálogo de **nivel de evaluación** para ver los siguientes parámetros adicionales y detalles: 
    
    ![Vista avanzada del problema de caso del nivel de evaluación](media/577d7e0e-95df-48c2-9dec-bdeab5e801d8.png)
  
    **Flexibilidad estimado**: estimado flexibilidad según los resultados de la evaluación actual
    
    **Para recuperación supuesta**: de forma predeterminada, se aplica el margen de error de destino para recuperar por encima del 75%. Si desea cambiar este parámetro y controlar el margen de error en un intervalo de valores de recuperación diferente, haga clic en **Editar** . 
    
    **Nivel de confianza**: de forma predeterminada, el margen de error recomendada para confianza es 95%. Si desea cambiar este parámetro, haga clic en **Editar** . 
    
    **Margen de error de flexibilidad esperados**: dado los valores actualizados, este es el margen de error de la flexibilidad, esperado después de que se revisan todos los archivos de evaluación adicionales.
    
    **Los archivos de evaluación adicionales necesarios**: dado los valores actualizados, el número de evaluación adicional de los archivos que necesitan para ser revisado para llegar a la de destino.
    
    **Evaluación total archivos necesarios**: dado los valores actualizados, número total de archivos de evaluación necesarios para su revisión.
    
    **Número esperado de archivos relevantes de evaluación**: dados los valores actualizados, el número esperado de los archivos relevantes en toda la evaluación después de que se revisan todos los archivos de evaluación adicionales.
    
4. Haga clic en **volver a calcular valores**, si se modifican los parámetros. Cuando haya terminado, si hay un problema, haga clic en **Aceptar** para guardar los cambios (o **siguiente** cuando hay varios problemas para revisar o modificar y, a continuación, **Finalizar**). 
    
    Cuando hay varios problemas, después de todos los problemas se han revisado o ajustados, un **nivel de evaluación: resumen** se muestra el cuadro de diálogo, tal como se muestra en el siguiente ejemplo. 
    
    ![Resumen del nivel de evaluación](media/4997b46d-10a5-4abc-b3b2-7b75a370eb9e.png)
  
    Una vez finalizada la correcta de evaluación, continúe con la siguiente fase de aprendizaje de la relevancia.
    
## <a name="reviewing-assessment-results"></a>Revisar los resultados de la evaluación

Después de que se etiqueta un ejemplo de evaluación, se calculan los resultados de la evaluación y se muestran en la ficha seguimiento de la relevancia.
  
Los siguientes resultados se muestran en la visualización de pista expandida: 
  
- Margen de error actual de evaluación para las estimaciones de recuperación
    
- Flexibilidad estimado
    
- Archivos de evaluación adicionales necesarios (para revisión)
    
El margen de error actual de evaluación es el margen de error recomendado por avanzada exhibición de documentos electrónicos. El número que se muestra para "archivos de la evaluación adicionales necesarios" corresponde a esa recomendación.
  
El indicador de progreso de la evaluación muestra el nivel de finalización de la evaluación, dada el margen de error actual. Cuando la evaluación está en curso, el usuario va a marcar otro ejemplo de evaluación.
  
Cuando el indicador de progreso de la evaluación muestra evaluación como completada, que significa que se completó la revisión de ejemplo de evaluación y etiquetaron suficientes archivos relevantes. 
  
La visualización de pista expandida muestra el siguiente paso recomendado, las estadísticas de evaluación y acceso a resultados detallados.
  
Cuando flexibilidad es muy bajo, el número de archivos de evaluación adicionales necesarios para llegar a un número mínimo de archivos relevantes para producir estadísticas útiles es muy alto. Exhibición de documentos electrónicos avanzada, a continuación, recomienda pasar a recursos de aprendizaje. El indicador de progreso de la evaluación será sombreado y no hay estadísticas estará disponible. 
  
En ausencia de estabilización estadísticamente en función, habrá resultados con un nivel de precisión y confianza de nivel inferior. Sin embargo, estos resultados pueden utilizarse para buscar archivos relevantes cuando no es necesario saber el porcentaje de archivos relevantes que se encuentran. De forma similar, se puede usar este estado para enseñar a los problemas con la flexibilidad baja, donde las puntuaciones de la relevancia pueden acelerar el acceso a archivos relevantes para un problema específico.
  
> [!TIP]
> En el **la relevancia \> pista** ficha, mostrar problema expandida, están disponibles las siguientes opciones de visualización: > paso la próxima recomendada, tales como **siguiente paso: etiquetado** puede omitirse (por problema) haciendo clic en el botón **Modificar** para su derecha y, a continuación, seleccionar un paso diferente en el **paso siguiente**. Cuando no se ha completado el indicador de progreso de la evaluación, evaluación será la siguiente opción recomendada para etiquetar más archivos de evaluación y aumentar la precisión de las estadísticas. > Se puede cambiar el margen de error y evaluar su impacto, haciendo clic en **Modificar**y, en el **cuadro de diálogo nivel de evaluación**, cambiar el **margen de error de destino para recuperación estima**y haciendo clic en **Actualizar valores**. Además, en este cuadro de diálogo, puede ver las opciones avanzadas, haciendo clic en **Opciones avanzadas**. > Puede ver las estadísticas de nivel de evaluación adicionales y su impacto haciendo clic en **Ver**. En el diálogo de resultados de todos los detalles que se muestra, las estadísticas están disponibles por el problema, cuando hay al menos 500 archivos de evaluación con etiqueta y los archivos de al menos 18 se etiquetan como pertinente para el problema. 
  
## <a name="see-also"></a>Vea también

[eDiscovery avanzado de Office 365](office-365-advanced-ediscovery.md)
  
[Evaluación de descripción en la relevancia](assessment-in-relevance-in-advanced-ediscovery.md)
  
[Etiquetado y formación de relevancia](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[Análisis de la relevancia de seguimiento](track-relevance-analysis-in-advanced-ediscovery.md)
  
[Decidir en función de los resultados](decision-based-on-the-results-in-advanced-ediscovery.md)
  
[Las pruebas de análisis de la relevancia](test-relevance-analysis-in-advanced-ediscovery.md)

