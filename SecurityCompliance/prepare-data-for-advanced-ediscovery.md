---
title: Preparar datos para Office 365 Advanced eDiscovery
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
ms.assetid: 2fb94c23-1846-4a0e-994d-da6d02445f15
description: 'Obtenga información sobre cómo usar el centro de &amp; seguridad y cumplimiento de Microsoft 365 para preparar datos de Office 365 para el análisis con Office 365 Advanced eDiscovery. '
ms.openlocfilehash: d9d81c145a86075affd76761eb6dcff0f84a1eac
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32265512"
---
# <a name="prepare-data-for-office-365-advanced-ediscovery"></a>Preparar datos para Office 365 Advanced eDiscovery

En este tema se describe cómo cargar los resultados de una búsqueda de contenido en un caso en eDiscovery avanzado. 
  
> [!NOTE]
> Para usar eDiscovery avanzado, su organización necesita una suscripción de Office 365 E3 con el complemento Cumplimiento avanzado, o bien una suscripción de E5. Si no tiene ese plan y quiere probar eDiscovery avanzado, puede [registrarse para una prueba de Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279). 
  
## <a name="step-1-prepare-office-365-data-for-advanced-ediscovery"></a>Paso 1: preparar los datos de Office 365 para la exhibición avanzada de documentos electrónicos

Para analizar datos con la exhibición avanzada de documentos electrónicos, puede usar los resultados de una búsqueda de contenido que se ejecuta en &amp; el centro de seguridad y cumplimiento de Microsoft 365 (que aparece en la &amp; página búsqueda de **contenido** en el centro de seguridad y cumplimiento de Microsoft 365) o en un búsqueda asociada a un caso de exhibición de documentos electrónicos **** (que se muestra en &amp; la página eDiscovery del centro de seguridad y cumplimiento). 
  
Para obtener los pasos detallados sobre cómo preparar los resultados de búsqueda para analizarlos en la exhibición avanzada de documentos electrónicos, vea [preparar los resultados de la búsqueda para Office 365 Advanced eDiscovery](prepare-search-results-for-advanced-ediscovery.md).
  
> [!NOTE]
> Si tiene datos fuera de Office 365 y desea importarlos a Office 365 para poder prepararlos y analizarlos en la exhibición avanzada de documentos electrónicos, vea [información general sobre la importación de archivos PST a office 365](https://support.office.com/article/ba688e0a-0fcb-4bd7-8e57-2b669564ea84) y el archivado de [datos de terceros en Office 365](https://go.microsoft.com/fwlink/p/?linkid=716918). 
  
## <a name="step-2-load-search-result-data-in-to-a-case-in-advanced-ediscovery"></a>Paso 2: cargar datos de resultados de búsqueda en un caso en eDiscovery avanzado

Después de preparar los resultados de la búsqueda en &amp; el centro de seguridad y cumplimiento para el análisis, el siguiente paso consiste en cargar los resultados de la búsqueda en un caso en eDiscovery avanzado. Para obtener información más detallada, consulte [ejecutar el módulo de proceso](run-the-process-module-in-advanced-ediscovery.md).
  
1. Vaya a [https://protection.office.com](https://protection.office.com).
    
2. Inicie sesión en Office 365 con su cuenta profesional o educativa.
    
3. En el Centro de seguridad y cumplimiento, haga clic en **Búsqueda e investigación** \> **eDiscovery** para mostrar la lista de casos en su organización. 
    
4. Haga clic en **abrir** junto al caso en el que desea cargar datos en la exhibición avanzada de documentos electrónicos. 
    
5. En la **página principal** del caso, haga clic en **eDiscovery avanzado**. 
    
    ![Haga clic en cambiar a exhibición avanzada de documentos electrónicos para abrir el caso en eDiscovery avanzado.](media/8e34ba23-62e3-4e68-a530-b6ece39b54be.png)
  
    Se muestra la barra de progreso **conectarse a la exhibición avanzada de** documentos electrónicos. Cuando está conectado a la exhibición avanzada de documentos electrónicos, se muestra una lista de contenedores en la página de configuración del caso. 
    
    ![El caso se muestra en la exhibición avanzada de documentos electrónicos](media/8036e152-70dc-4bb7-9379-61c1ed8326b4.png)
  
     Estos contenedores representan los resultados de búsqueda que ha preparado para el análisis en la exhibición avanzada de documentos electrónicos en el paso 1. Tenga en cuenta que el nombre del contenedor tiene el mismo nombre que la búsqueda de contenido en el caso del &amp; centro de seguridad y cumplimiento. Los contenedores de la lista son los que ha preparado. Si un usuario diferente ha preparado los resultados de búsqueda para la exhibición avanzada de documentos electrónicos, los contenedores correspondientes no se incluirán en la lista. 
    
6. Para cargar los datos de resultados de búsqueda de un contenedor en el caso de eDiscovery avanzado, seleccione un contenedor y, a continuación, haga clic en **procesar**.
    
Una vez que se agregan los &amp; resultados de la búsqueda del centro de seguridad y cumplimiento al caso de la exhibición avanzada de documentos electrónicos, el siguiente paso consiste en usar las herramientas de la exhibición avanzada de documentos electrónicos para analizar y deselección de los datos relevantes para el caso. 
  
## <a name="see-also"></a>Vea también

[eDiscovery avanzado de Office 365](office-365-advanced-ediscovery.md)
  
[Configurar usuarios y casos](set-up-users-and-cases-in-advanced-ediscovery.md)
  
[Analizar datos de casos](analyze-case-data-with-advanced-ediscovery.md)
  
[Administración de la configuración de relevancia](manage-relevance-setup-in-advanced-ediscovery.md)
  
[Usar el módulo de relevancia](use-relevance-in-advanced-ediscovery.md)
  
[Exportar datos de casos](export-case-data-in-advanced-ediscovery.md)

