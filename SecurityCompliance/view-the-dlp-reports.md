---
title: Ver los informes de prevención de pérdida de datos
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 6/7/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 41eb4324-c513-4fa5-91c8-8fbd8aaba83b
description: Con los informes DLP en Office 365, puede ver rápidamente el número de coincidencias de directivas de DLP, invalidaciones o falsos positivos; vea si está tendencias de arriba o abajo en el tiempo; filtrar el informe de diferentes maneras; y ver detalles adicionales mediante la selección de un punto en una línea en el gráfico.
ms.openlocfilehash: 379e66fc3f2611cf338739d030c2b1d48e7416d8
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "23013914"
---
# <a name="view-the-reports-for-data-loss-prevention"></a>Ver los informes de prevención de pérdida de datos

Después de crear las directivas de prevención (DLP) la pérdida de datos, desea comprobar que trabaja como pensado y le ayuda a cumplir. Con la DLP informes en la seguridad de Office 365 &amp; centro de cumplimiento, puede ver rápidamente:
  
- **Coincidencias de directivas de DLP** Este informe muestra el recuento de coincidencias de directivas de DLP a través del tiempo. Puede filtrar el informe por fecha, la ubicación, la directiva o la acción. Puede usar este informe para: 
    
  - Ajustar o restringir sus directivas de DLP, tal y como se ejecuta en modo de prueba. Puede ver la regla específica que coincidieron con el contenido.
    
  - Centrarse en períodos de tiempo específicos y comprender las causas de los picos y las tendencias.
    
  - Descubra los procesos de negocio que infringen las directivas DLP de su organización.
    
  - Para comprender cualquier impacto en el negocio de las directivas de DLP, vean qué acciones se aplican al contenido.
    
  - Comprobar el cumplimiento de una directiva DLP específica mostrando las coincidencias de dicha directiva.
    
  - Ver una lista de los principales usuarios y repita los usuarios que contribuyen a los incidentes en la organización.
    
  - Ver una lista de los principales tipos de información confidencial de la organización.
    
- **Incidentes DLP** Este informe muestra también coincidencias de directivas con el tiempo, como el informe de coincide con la directiva. Sin embargo, la directiva coincide con informe muestra las coincidencias en un nivel de la regla; Por ejemplo, si un correo electrónico, coincidió con tres reglas diferentes, la directiva coincide con informe muestra tres diferentes elementos de línea. Por el contrario, el informe de incidentes muestra las coincidencias en un nivel de elemento; Por ejemplo, si un correo electrónico, coincidió con tres reglas diferentes, el informe de incidentes muestra un elemento de línea única para esa parte del contenido. 
    
  Debido a que los recuentos de informe se agregan de forma diferente, el informe de coincidencias de directiva es mejor para identificar las coincidencias con las reglas específicas y realizar ajustes en las directivas de DLP. El informe de incidentes es mejor para la identificación de partes específicas del contenido que son problemáticas para las directivas de DLP.
    
- **Invalidaciones y falsos positivos DLP** Si la directiva de DLP permite a los usuarios invalidarla o notificar un falso positivo, este informe muestra un recuento de esas instancias a través del tiempo. Puede filtrar el informe por fecha, la ubicación o la directiva. Puede usar este informe para: 
    
  - Ajustar o restringir sus directivas de DLP por vean qué directivas provocar una gran cantidad de falsos positivos.
    
  - Ver la justificación presentada por los usuarios cuando resuelvan una sugerencia de directiva mediante el reemplazo de la directiva.
    
  - Descubrir donde invalida el conflicto de directivas DLP con los procesos de negocio válido por incurrir en un gran número de usuarios.
    
Todos los informes DLP pueden mostrar los datos desde el período de tiempo de cuatro meses más reciente. Los datos más recientes pueden tardar hasta 24 horas que aparezca en los informes.
  
Puede encontrar estos informes en la seguridad &amp; centro de cumplimiento \> **informes** \> **panel**.
  
![Informe de coincidencias de directivas DLP](media/117d20c9-d379-403f-ad68-1f5cd6c4e5cf.png)
  
## <a name="view-the-justification-submitted-by-a-user-for-an-override"></a>Ver la justificación presentada por un usuario para un reemplazo

Si la directiva de DLP permite a los usuarios invalidarla, puede usar el falso positivo y reemplazar el informe para ver el texto enviado por los usuarios en la sugerencia de directiva.
  
![Campo de justificación de detalles del informe de reemplazo y falso positivo DLP](media/e11e3126-026d-4e77-a16d-74a0686d1fa3.png)
  
## <a name="take-action-on-insights-and-recommendations"></a>Tomar medidas en conocimientos y recomendaciones

Pueden mostrar informes de conocimientos y recomendaciones donde puede hacer clic en el icono de advertencia de color rojo para ver más detalles sobre posibles problemas y tomar medidas correctivas posibles.
  
![Al hacer clic en un icono de conocimientos para ver detalles y acciones que se realizarán](media/51782036-7299-4960-8175-75c2b1637159.png)
  
## <a name="find-the-cmdlets-for-the-dlp-reports"></a>Busque los cmdlets para los informes DLP

Para utilizar la mayoría de los cmdlets para la seguridad &amp; centro de cumplimiento, necesita:
  
1. [Conectarse a la seguridad de Office 365 &amp; centro de cumplimiento de normas mediante PowerShell remoto](http://go.microsoft.com/fwlink/?LinkID=799771&amp;clcid=0x409)
    
2. Use cualquiera de estas [Office 365 seguridad &amp; centro de cumplimiento cmdlets](http://go.microsoft.com/fwlink/?LinkID=799772&amp;clcid=0x409)
    
Sin embargo, los informes de DLP necesitan extraer datos de a través de Office 365, como Exchange Online. Por este motivo, los cmdlets de para los informes DLP están disponibles en Exchange Online Powershell, no en seguridad &amp; Powershell de centro de cumplimiento. Por lo tanto, para usar los cmdlets de para los informes DLP, necesitará:
  
1. [Connect to Exchange Online using remote PowerShell](http://go.microsoft.com/fwlink/?LinkID=799773&amp;clcid=0x409)
    
2. Use cualquiera de estos cmdlets para los informes DLP:
    
      - [Get-DlpDetectionsReport](http://go.microsoft.com/fwlink/?LinkID=799774&amp;clcid=0x409)
    
      - [Get-DlpDetailReport](http://go.microsoft.com/fwlink/?LinkID=799775&amp;clcid=0x409)
    

