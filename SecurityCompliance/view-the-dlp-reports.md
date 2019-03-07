---
title: Ver los informes de prevención de pérdida de datos
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 6/7/2018
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MET150
description: Con los informes de DLP en Office 365, puede ver rápidamente el número de coincidencias de directivas de DLP, invalidaciones o falsos positivos; ver si las tendencias están arriba o abajo con el tiempo; filtrar el informe de diferentes formas; y ver detalles adicionales seleccionando un punto en una línea del gráfico.
ms.openlocfilehash: 6f97a29b5a80eeff60b13ba4467d44e3ef87b028
ms.sourcegitcommit: 6aa82374eef09d2c1921f93bda3eabeeb28aadeb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "30454852"
---
# <a name="view-the-reports-for-data-loss-prevention"></a>Ver los informes de prevención de pérdida de datos

Después de crear las directivas de prevención de pérdida de datos (DLP), querrá comprobar que funcionan según lo previsto y ayudarle a mantener la conformidad. Con los informes de DLP en el centro de &amp; seguridad y cumplimiento de Office 365, puede ver rápidamente:
  
- Coincidencias de **directivas DLP** Este informe muestra el número de coincidencias de directivas de DLP a lo largo del tiempo. Puede filtrar el informe por fecha, ubicación, Directiva o acción. Puede usar este informe para: 
    
  - Ajustar o refinar las directivas de DLP a medida que las ejecuta en modo de prueba. Puede ver la regla específica que coincide con el contenido.
    
  - Centrarse en períodos de tiempo específicos y comprender las causas de los picos y las tendencias.
    
  - Descubra los procesos de negocio que infringen las directivas DLP de su organización.
    
  - Comprenda cualquier impacto empresarial de las directivas DLP mediante la visualización de las acciones que se aplican al contenido.
    
  - Comprobar el cumplimiento de una directiva DLP específica mostrando las coincidencias de dicha directiva.
    
  - Ver una lista de los usuarios principales y repetir los usuarios que están contribuyendo a incidentes de la organización.
    
  - Ver una lista de los principales tipos de información confidencial de la organización.
    
- **Incidentes de DLP** Este informe también muestra las coincidencias de directivas a lo largo del tiempo, como la Directiva coincide con el informe. Sin embargo, el informe de coincidencias de directivas muestra coincidencias en un nivel de regla; por ejemplo, si un correo electrónico coincide con tres reglas distintas, la Directiva coincide con el informe muestra tres elementos de línea diferentes. Por el contrario, el informe de incidentes muestra coincidencias en un nivel de elemento; por ejemplo, si un correo electrónico coincide con tres reglas distintas, el informe de incidentes muestra un elemento de línea único para esa parte de contenido. 
    
  Dado que el número de informes se agrega de forma diferente, el informe de coincidencias de directiva es mejor para identificar coincidencias con reglas específicas y ajustar directivas DLP. El informe de incidentes es mejor para identificar fragmentos específicos de contenido que son problemáticos para sus directivas de DLP.
    
- **Falsos positivos y reemplazos de DLP** Si su Directiva DLP permite a los usuarios invalidarla o informar de un falso positivo, este informe muestra un recuento de esas instancias a lo largo del tiempo. Puede filtrar el informe por fecha, ubicación o Directiva. Puede usar este informe para: 
    
  - Para ajustar o refinar las directivas de DLP, vea las directivas que incurren en un gran número de falsos positivos.
    
  - Ver las justificaciones enviadas por los usuarios cuando resuelven una sugerencia de directiva reemplazando la Directiva.
    
  - Descubra dónde entran en conflicto las directivas de DLP con procesos de negocio válidos al incurrir en un gran número de invalidaciones de usuario.
    
Todos los informes de DLP pueden mostrar datos del período de tiempo de cuatro meses más reciente. Los datos más recientes pueden tardar hasta 24 horas en aparecer en los informes.
  
Puede encontrar estos informes en el **Panel**de &amp; \> **informes** \> del centro de cumplimiento de seguridad.
  
![Informe de coincidencias de directivas de DLP](media/117d20c9-d379-403f-ad68-1f5cd6c4e5cf.png)
  
## <a name="view-the-justification-submitted-by-a-user-for-an-override"></a>Ver la justificación enviada por un usuario para una invalidación

Si su Directiva DLP permite a los usuarios invalidarla, puede usar el informe de anulación y de falso positivo para ver el texto enviado por los usuarios en la sugerencia de directiva.
  
![Campo de justificación en detalles del informe de reemplazo y falso positivo de DLP](media/e11e3126-026d-4e77-a16d-74a0686d1fa3.png)
  
## <a name="take-action-on-insights-and-recommendations"></a>Realizar acciones en información y recomendaciones

Los informes pueden mostrar información y recomendaciones en las que puede hacer clic en el icono rojo de advertencia para ver los detalles de los posibles problemas y realizar posibles acciones correctivas.
  
![Hacer clic en un icono de información para ver los detalles y las acciones que se deben realizar](media/51782036-7299-4960-8175-75c2b1637159.png)
  
## <a name="find-the-cmdlets-for-the-dlp-reports"></a>Buscar los cmdlets para los informes de DLP

Para usar la mayoría de los cmdlets del centro &amp; de seguridad y cumplimiento, debe:
  
1. [Conectarse al Centro de seguridad y cumplimiento de Office 365 mediante PowerShell remoto](http://go.microsoft.com/fwlink/?LinkID=799771&amp;clcid=0x409)
    
2. Use cualquiera de estos [cmdlets del &amp; centro de seguridad y cumplimiento de Office 365](http://go.microsoft.com/fwlink/?LinkID=799772&amp;clcid=0x409)
    
Sin embargo, los informes DLP necesitan extraer datos de toda la oficina 365, incluido Exchange Online. Por este motivo, los cmdlets para los informes de DLP están disponibles en Exchange Online PowerShell, no en &amp; PowerShell del centro de seguridad y cumplimiento. Por lo tanto, para usar los cmdlets para los informes de DLP, debe:
  
1. [Conectarse a Exchange Online con el PowerShell remoto](http://go.microsoft.com/fwlink/?LinkID=799773&amp;clcid=0x409)
    
2. Use cualquiera de estos cmdlets para los informes de DLP:
    
      - [Get-DlpDetectionsReport](http://go.microsoft.com/fwlink/?LinkID=799774&amp;clcid=0x409)
    
      - [Get-DlpDetailReport](http://go.microsoft.com/fwlink/?LinkID=799775&amp;clcid=0x409)
    

