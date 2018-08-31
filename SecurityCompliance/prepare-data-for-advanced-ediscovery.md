---
title: Preparar datos para eDiscovery avanzado de Office 365
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
ms.assetid: 2fb94c23-1846-4a0e-994d-da6d02445f15
description: 'Obtenga información sobre cómo usar la seguridad de Office 365 &amp; centro de cumplimiento para preparar los datos de Office 365 para el análisis con Office 365 avanzada exhibición de documentos electrónicos. '
ms.openlocfilehash: cf0c76b0c274121da435de7829c769abf5111cab
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22536590"
---
# <a name="prepare-data-for-office-365-advanced-ediscovery"></a>Preparar datos para eDiscovery avanzado de Office 365

En este tema se describe cómo cargar los resultados de una búsqueda de contenido en un caso de exhibición de documentos electrónicos avanzada. 
  
> [!NOTE]
> Exhibición de documentos electrónicos avanzada requiere un E3 de Office 365 con el complemento de cumplimiento avanzadas o una suscripción E5 para su organización. Si no tiene ese plan y desea probar avanzada exhibición de documentos electrónicos, puede [registrarse y obtener una versión de prueba de Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279). 
  
## <a name="step-1-prepare-office-365-data-for-advanced-ediscovery"></a>Paso 1: Preparar datos de Office 365 para exhibición de documentos electrónicos avanzada

Para analizar datos con avanzadas exhibición de documentos electrónicos, puede usar los resultados de una búsqueda de contenido que se ejecuta en la seguridad de Office 365 &amp; centro de cumplimiento (que aparecen en la página de **búsqueda de contenido** en la seguridad de Office 365 &amp; centro de cumplimiento) o una búsqueda asociado a un caso de exhibición de documentos electrónicos (que aparecen en la página de **exhibición de documentos electrónicos** en la seguridad &amp; centro de cumplimiento). 
  
Para obtener los pasos detallados sobre la preparación de los resultados de búsqueda para el análisis de exhibición de documentos electrónicos avanzada, vea [preparar los resultados de búsqueda de exhibición de documentos electrónicos avanzada de Office 365](prepare-search-results-for-advanced-ediscovery.md).
  
> [!NOTE]
> Si dispone de datos fuera de Office 365 y desea importarlo a Office 365 para que pueda preparar y analizar en Avanzadas exhibición de documentos electrónicos, una vea [información general de importación de los archivos PST a Office 365](https://support.office.com/article/ba688e0a-0fcb-4bd7-8e57-2b669564ea84) y [archivado de datos de terceros en Office 365](https://go.microsoft.com/fwlink/p/?linkid=716918). 
  
## <a name="step-2-load-search-result-data-in-to-a-case-in-advanced-ediscovery"></a>Paso 2: Carga resultado datos de búsqueda en un caso de exhibición de documentos electrónicos avanzada

Después de preparar los resultados de búsqueda en la seguridad &amp; centro de cumplimiento para el análisis, el siguiente paso es cargar los resultados de búsqueda en un caso de exhibición de documentos electrónicos avanzada. Para obtener información más detallada, vea [ejecutar el módulo de proceso](run-the-process-module-in-advanced-ediscovery.md).
  
1. Vaya a [https://protection.office.com](https://protection.office.com).
    
2. Inicie sesión en Office 365 con su cuenta de trabajo o escuela.
    
3. En la seguridad &amp; centro de cumplimiento, haga clic en **búsqueda &amp; investigación** \> **exhibición de documentos electrónicos** para mostrar la lista de casos de la organización. 
    
4. Junto al caso de que se desea cargar los datos en a en la exhibición de documentos electrónicos avanzada, haga clic en **Abrir** . 
    
5. En la página **principal** para el caso, haga clic en **Avanzadas exhibición de documentos electrónicos**. 
    
    ![Haga clic en cambiar para exhibición de documentos electrónicos avanzada para abrir el caso de exhibición de documentos electrónicos avanzada](media/8e34ba23-62e3-4e68-a530-b6ece39b54be.png)
  
    Se muestra la barra de progreso **que se conectan a la exhibición de documentos electrónicos avanzada** . Cuando está conectado a la exhibición de documentos electrónicos avanzada, se muestra una lista de contenedores en la página del programa de instalación para el caso. 
    
    ![Se muestra el caso de exhibición de documentos electrónicos avanzada](media/8036e152-70dc-4bb7-9379-61c1ed8326b4.png)
  
     Estos contenedores representan los resultados de búsqueda que ha preparado para el análisis de exhibición de documentos electrónicos avanzada en el paso 1. Tenga en cuenta que el nombre del contenedor tiene el mismo nombre que la búsqueda de contenido en el caso de la seguridad &amp; centro de cumplimiento. Los contenedores de la lista son los que ha preparado. Si un usuario diferente preparado los resultados de búsqueda de exhibición de documentos electrónicos avanzada, los contenedores correspondientes no se incluirán en la lista. 
    
6. Para cargar los datos de resultados de búsqueda de un contenedor en el caso de exhibición de documentos electrónicos avanzada, seleccione un contenedor y, a continuación, haga clic en **proceso**.
    
Después de los resultados de búsqueda de la seguridad &amp; centro de cumplimiento se agregan para el caso de exhibición de documentos electrónicos avanzada, el siguiente paso consiste en usar las herramientas de exhibición de documentos electrónicos avanzada para analizar y extraer los datos que es relevantes para el caso. 
  
## <a name="see-also"></a>Vea también

[eDiscovery avanzado de Office 365](office-365-advanced-ediscovery.md)
  
[Configurar los usuarios y de los casos](set-up-users-and-cases-in-advanced-ediscovery.md)
  
[Analizar los datos de casos](analyze-case-data-with-advanced-ediscovery.md)
  
[Administración del programa de instalación de la relevancia](manage-relevance-setup-in-advanced-ediscovery.md)
  
[Con el módulo de relevancia](use-relevance-in-advanced-ediscovery.md)
  
[Exportación de datos de casos](export-case-data-in-advanced-ediscovery.md)

