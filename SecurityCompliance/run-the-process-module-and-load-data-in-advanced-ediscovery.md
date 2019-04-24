---
title: Ejecutar el módulo de proceso y cargar datos en eDiscovery avanzado de Office 365
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
ms.assetid: c87bb0e5-301c-4d1d-958e-aabeb7990f44
description: 'Obtenga información sobre cómo usar el centro de &amp; seguridad y cumplimiento de Office 365 para obtener acceso a eDiscovery avanzado de Office 365 y ejecutar el módulo de proceso para un caso.  '
ms.openlocfilehash: 95c73c034ed2ffa1c45f9aacd8463c497a842859
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32261418"
---
# <a name="run-the-process-module-and-load-data-in-office-365-advanced-ediscovery"></a>Ejecutar el módulo de proceso y cargar datos en eDiscovery avanzado de Office 365

> [!NOTE]
> Para usar eDiscovery avanzado, su organización necesita una suscripción de Office 365 E3 con el complemento Cumplimiento avanzado, o bien una suscripción de E5. Si no tiene ese plan y quiere probar eDiscovery avanzado, puede [registrarse para una prueba de Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279). 
  
En esta sección se describe la funcionalidad del módulo de proceso avanzado de eDiscovery. 
  
Además de los datos de archivo, los metadatos como el tipo de archivo, la extensión, la ubicación o la ruta de acceso, la fecha y hora de creación, el autor, el custodio y el sujeto se pueden cargar en eDiscovery avanzado y guardarse para cada caso. Algunos metadatos los calcula la exhibición avanzada de documentos electrónicos, por ejemplo, cuando se cargan archivos nativos. 
  
EDiscovery avanzado proporciona valores de metadatos del sistema, como agrupaciones casi duplicadas o calificaciones de relevancia. El administrador puede agregar otros metadatos, como las anotaciones de archivo. 
  
## <a name="running-process"></a>Proceso en ejecución

> [!NOTE]
> Los números de lote se asignan a un archivo durante el proceso para permitir el seguimiento de archivos. El número de lote también permite la identificación de lotes de proceso para las opciones de reprocesamiento. Hay filtros adicionales disponibles para filtrar por número de lote y sesiones. 
  
Realice los siguientes pasos para ejecutar el proceso.
  
1. [Abra el centro de seguridad &amp; y cumplimiento de Office 365](go-to-the-securitycompliance-center.md) . 
    
2. Vaya a la **exhibición** de documentos electrónicos de ** &amp; investigación** \> y haga clic en **ir a exhibición avanzada**de documentos electrónicos.
    
3. En la exhibición avanzada de documentos electrónicos, seleccione el caso apropiado en la página **casos** mostrados y haga clic en **ir al caso**.
    
4. En **preparar** \> el **proceso** \> de **instalación**, seleccione un contenedor de la lista de contenedores disponibles.
    
    ![Haga clic en proceso para agregar los resultados de la búsqueda al caso](media/50bdc55c-d378-4881-b302-31ef785fa359.png)
  
5. Haga clic en **Configuración avanzada...** si desea agregar el contenedor como archivos semilla o como archivos etiquetados previamente. 
    
    Use los archivos de inicialización para acelerar el entrenamiento de problemas con escasa riqueza (normalmente 2% o menos). En el caso de los archivos de inicialización, se recomienda seleccionar una variedad de archivos y un proceso claramente relevantes alrededor de 20-50 de semillas por problema (demasiados archivos de inicialización pueden sesgar los resultados de relevancia). Los archivos de inicialización deben ser revisados por la misma persona que va a entrenar el problema.
    
    Use archivos etiquetados previamente para automatizar el entrenamiento de relevancia. Debe etiquetar al menos 1.500 archivos y mantener la proporción de archivos relevantes y no relevantes del mismo modo que en la colección agregada a relevancia. Estos archivos se deben etiquetar manualmente y debe estar seguro de la calidad de etiquetado.
    
    ![Captura de pantalla de la página Configuración avanzada para procesar archivos por lotes](media/3c25cb78-4484-41e5-bd34-3753c7ab6cf2.jpg)
  
  - En la sección **SEED** : 
    
    Elija **marcar como archivos semilla** para marcar el contenedor como archivos de inicialización. También tiene que elegir asignarlos por asunto en la lista desplegable **para problema** . Elija **relevante** o **no relevante** en la lista desplegable de **etiquetas** . 
    
    > [!NOTE]
    > Una vez que haya establecido **** los archivos como inicialización, no podrá marcarlos como **etiquetados previamente**. 
  
  - En la sección **archivos etiquetaDos previamente** : 
    
    Elija **marcar como archivos etiquetados previamente** para marcar el contenedor como archivos etiquetados previamente. También tiene que asignarlos por problema desde la lista desplegable **para problema** . Elija **relevante** o **no relevante** en la lista desplegable de **etiquetas** . 
    
    > [!NOTE]
    > Una vez que haya establecido los archivos como **etiquetaDos previamente**, no podrá marcarlos como **inicialización**. 
  
  - En la sección **etiquetado de correo electrónico** . establecer qué parte de un correo electrónico procesado se marcará como semilla o preetiquetada. 
    
6. Para empezar, haga clic en **procesar**. Una vez finalizado, se muestran los resultados del proceso.
    
7. Opcional Si necesita asignar orígenes de datos a un custodio específico, puede Agregar y editar nombres de custodios en los **custodios** \> **administre** y asigne custodios en **asignación**de **custodios** \> . 
    
Si agrega al caso, puede volver a procesar.
  
## <a name="see-also"></a>Vea también

[eDiscovery avanzado de Office 365](office-365-advanced-ediscovery.md)
  
[Visualización de los resultados del módulo de proceso](view-process-module-results-in-advanced-ediscovery.md)

