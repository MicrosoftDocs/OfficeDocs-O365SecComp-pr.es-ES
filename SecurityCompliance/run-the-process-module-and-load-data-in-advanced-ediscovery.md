---
title: Ejecutar el módulo de proceso y cargar datos en eDiscovery avanzado de Office 365
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
ms.assetid: c87bb0e5-301c-4d1d-958e-aabeb7990f44
description: 'Obtenga información sobre cómo usar la seguridad de Office 365 &amp; centro de cumplimiento para tener acceso a Office 365 avanzada exhibición de documentos electrónicos y ejecutar el módulo de proceso para un caso.  '
ms.openlocfilehash: 32052bccc37d20c8707a1efb0592f7c93daf3590
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22536207"
---
# <a name="run-the-process-module-and-load-data-in-office-365-advanced-ediscovery"></a>Ejecutar el módulo de proceso y cargar datos en eDiscovery avanzado de Office 365

> [!NOTE]
> Exhibición de documentos electrónicos avanzada requiere un E3 de Office 365 con el complemento de cumplimiento avanzadas o una suscripción E5 para su organización. Si no tiene ese plan y desea probar avanzada exhibición de documentos electrónicos, puede [registrarse y obtener una versión de prueba de Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279). 
  
En esta sección se describe la funcionalidad del módulo del proceso de exhibición de documentos electrónicos avanzadas. 
  
Además de los datos de archivo, se pueden cargar metadatos como tipo de archivo, extensión, ubicación o ruta de acceso, fecha de creación y tiempo, autor, custodia y asunto, en avanzada de exhibición de documentos electrónicos y guardan para cada caso. Algunos metadatos se calculan mediante avanzada exhibición de documentos electrónicos, por ejemplo, cuando se cargan archivos nativos. 
  
Exhibición de documentos electrónicos avanzada proporciona al sistema de valores de metadatos, como las agrupaciones de casi duplicados o las puntuaciones de la relevancia. Otros metadatos, como las anotaciones de archivo, se pueden agregar por el administrador. 
  
## <a name="running-process"></a>Proceso que se está ejecutando

> [!NOTE]
> Los números de lote se asignan a un archivo durante el proceso para permitir el seguimiento de los archivos. El número de lote también permite la identificación de los lotes de proceso para las opciones de reprocesamiento. Filtros adicionales están disponibles para filtrar por número de lote y sesiones. 
  
Realice los pasos siguientes para ejecutar el proceso.
  
1. [Abrir la seguridad de Office 365 &amp; centro de cumplimiento](go-to-the-securitycompliance-center.md) . 
    
2. Vaya a **búsqueda &amp; investigación** \> **exhibición de documentos electrónicos** y, a continuación, haga clic en **Ir a la exhibición de documentos electrónicos avanzada**.
    
3. En la exhibición de documentos electrónicos avanzada, seleccione el caso apropiado en la página de **casos** mostrada en y haga clic en **Ir a caso**.
    
4. En **Prepare** \> **proceso** \> **el programa de instalación**, seleccione un contenedor de la lista de contenedores disponibles.
    
    ![Haga clic en el proceso para agregar los resultados de búsqueda a las mayúsculas y minúsculas](media/50bdc55c-d378-4881-b302-31ef785fa359.png)
  
5. Haga clic en **configuración... avanzada** si desea agregar el contenedor como archivos de inicialización o como archivos con previa a la etiqueta. 
    
    Usar archivos de inicialización para acelerar el aprendizaje para problemas con flexibilidad baja (normalmente un 2% o menos). Para los archivos de inicialización, se recomienda que seleccione una gran variedad de archivos claramente relevantes y procesar sobre semillas 20-50 por problema (demasiados archivos de inicialización pueden contraer los resultados de la relevancia). Archivos de inicialización deben ser revisados por la misma persona que enseñará el problema.
    
    Usar archivos con previa a la etiqueta para automatizar la formación de relevancia. Debe marcar los archivos al menos 1.500 y mantener la misma que en la colección que se agrega a la relevancia de la proporción de relevantes para los archivos que no sean relevantes. Estos archivos se deben etiquetar manualmente, y debe estar seguro de la calidad de etiquetas temáticas.
    
    ![Captura de pantalla de avanzada de página de configuración para el procesamiento por lotes de archivos](media/3c25cb78-4484-41e5-bd34-3753c7ab6cf2.jpg)
  
  - En la sección **valor de inicialización** : 
    
    Seleccione **Marcar como archivos de inicialización** para marcar el contenedor como archivos de inicialización. También necesita elegir asignar por problema desde la **para el problema de** lista desplegable. Elija **pertinente** o **no relevantes** en la lista desplegable de **etiqueta** . 
    
    > [!NOTE]
    > Una vez que los archivos se establece como **valor de inicialización**, no se puede marcarlos como **previamente con etiqueta**. 
  
  - En la sección **archivos con previa a la etiqueta** : 
    
    Seleccione **Marcar como archivos con previa a la etiqueta** para marcar el contenedor como archivos con previa a la etiqueta. También debe asignar por problema desde la **para el problema de** lista desplegable. Elija **pertinente** o **no relevantes** en la lista desplegable de **etiqueta** . 
    
    > [!NOTE]
    > Una vez establecido archivos como **previamente con la etiqueta**, no se puede marcarlos como **valor de inicialización**. 
  
  - En la sección **correo electrónico etiquetado** . conjunto de qué parte de un correo electrónico procesado deben estar marcados como semillas o con previa a la etiqueta. 
    
6. Para empezar, haga clic en **proceso**. Cuando se complete, se muestran los resultados del proceso.
    
7. (Opcional) Si necesita asignar orígenes de datos a una custodia específica, puede agregar y editar los nombres de custodia en **custodia** \> **Administrar** y asignar custodia en **custodia** \> **asignar**. 
    
Si agrega a las mayúsculas y minúsculas, a continuación, puede procesar de nuevo.
  
## <a name="see-also"></a>Vea también

[eDiscovery avanzado de Office 365](office-365-advanced-ediscovery.md)
  
[Ver los resultados del módulo de proceso](view-process-module-results-in-advanced-ediscovery.md)

