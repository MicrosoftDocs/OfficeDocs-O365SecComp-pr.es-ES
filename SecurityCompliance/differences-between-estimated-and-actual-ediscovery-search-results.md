---
title: Diferencias entre los resultados de búsqueda de exhibición de documentos electrónicos Estimado y real en Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 4/13/2017
ms.audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- SPO160
- MOE150
ms.assetid: 8f20ca4f-a908-46ec-99e6-9890d269ecf2
description: 'Comprenda por qué los resultados de búsqueda reales y estimados pueden variar en las búsquedas ejecutadas con herramientas de eDiscovery en Office 365. '
ms.openlocfilehash: 35aa1163e33e6c8a07c765d620803e93a8e6290d
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/23/2019
ms.locfileid: "30217350"
---
# <a name="differences-between-estimated-and-actual-ediscovery-search-results-in-office-365"></a>Diferencias entre los resultados de búsqueda de exhibición de documentos electrónicos Estimado y real en Office 365

Este tema se aplica a las búsquedas que se pueden ejecutar con una de las siguientes herramientas de eDiscovery de Microsoft:  <br/>  
- Búsqueda de contenido en el centro de &amp; seguridad y cumplimiento de Office 365  <br/>  
- Exhibición de documentos electrónicos local en el centro de administración de Exchange (EAC)  <br/>  
- Centro de exhibición de documentos electrónicos en SharePoint Online  <br/> 
   
Cuando se ejecuta una búsqueda de exhibición de documentos electrónicos, la herramienta que se está usando devolverá una estimación del número de elementos (y su tamaño total) que cumplan los criterios de búsqueda. Por ejemplo, cuando se ejecuta una búsqueda en el centro &amp; de seguridad y cumplimiento, los resultados de la búsqueda estimados se muestran en el panel de detalles de la búsqueda seleccionada.
  
![Cálculo de resultados que se muestra en el panel de detalles de la búsqueda seleccionada](media/74e4ce83-40be-41a9-b60f-5ad447e79fe4.png)
  
Esta es la misma estimación de tamaño total y número de elementos que se muestra en la herramienta de exportación de exhibición de documentos electrónicos cuando se exportan resultados a un equipo local y en el informe de Resumen de exportación que se descarga con los resultados de la búsqueda.
  
**Resultados estimados en la herramienta de exportación de exhibición de documentos electrónicos**

![Resultados estimados en la herramienta de exportación de exhibición de documentos electrónicos](media/d34312a5-0ee6-49aa-9460-7ea0015a6e66.png)
  
**Resultados estimados en el informe de Resumen de exportación**

![Los resultados de la búsqueda estimada se incluyen en el informe de resumen de exportación](media/44b579da-86c2-4f33-81b5-84d604003eda.png)
  
Sin embargo, como verá en la captura de pantalla anterior del informe de Resumen de exportación, el tamaño y el número de resultados de búsqueda reales que se descargan son distintos del tamaño y el número de resultados de búsqueda estimados. 
  
![Diferencia entre los resultados de la búsqueda estimados y descargados](media/84aef318-230f-430d-9d9e-02f21342d364.png)
  
Estos son algunos de los motivos de estas diferencias:
  
- **La forma** en que se estiman los resultados-una estimación de los resultados de la búsqueda es sólo eso, una estimación (y no un recuento real) de los elementos que cumplen los criterios de la consulta de búsqueda. Para compilar la estimación de los elementos de Exchange, se solicita una lista de los identificadores de mensaje que cumplen los criterios de búsqueda en la base de datos de Exchange mediante la herramienta eDiscovery que está usando. Pero cuando se exportan los resultados de la búsqueda, la búsqueda se vuelve a ejecutar y los mensajes reales se recuperan de la base de datos de Exchange. Por lo tanto, es posible que se produzcan estas diferencias debido a cómo se determina el número estimado de elementos y el número real de elementos. 
    
- **Cambios que se producen entre el momento en que se calculan y se exportan los resultados** de la búsqueda: cuando se exportan los resultados de búsqueda, se reiniciará la búsqueda para recopilar los elementos más recientes del índice de búsqueda que cumplan los criterios de búsqueda. Es posible que se hayan creado, enviado o recibido elementos adicionales que cumplan los criterios de búsqueda en el tiempo entre el momento en que se recopilaron los resultados de búsqueda estimados y el momento en que se exportaron los resultados de la búsqueda. También es posible que los elementos que estaban en el índice de búsqueda cuando se calcularon los resultados de la búsqueda ya no existan porque se han purgado de la ubicación del contenido antes de que se exporten los resultados de la búsqueda. Una forma de mitigar este problema es especificar un intervalo de fechas para una búsqueda de exhibición de documentos electrónicos. Otra forma consiste en poner una retención en las ubicaciones de contenido para que los elementos se conserven y no puedan purgarse. 
    
- **Elementos** sin indexar: los elementos que no están indexados para la búsqueda pueden causar diferencias entre los resultados de búsqueda reales y estimados. Por ejemplo, la exhibición de documentos electrónicos local en Exchange y el centro de exhibición de documentos electrónicos de SharePoint no incluyen elementos sin indexar (que no cumplen los criterios de búsqueda) cuando se ejecuta una búsqueda para estimar los resultados de la búsqueda. Pero puede incluir elementos sin indexar al exportar los resultados de la búsqueda. Si incluye elementos sin indexar al exportar los resultados de la búsqueda, es posible que haya más elementos que se exportan. Esto hará que se produzca una diferencia entre los resultados de búsqueda estimados y exportados. 
    
    Al usar la herramienta de búsqueda de contenido en &amp; el centro de seguridad y cumplimiento, tiene la opción de incluir elementos sin indexar en la estimación de la búsqueda. El número de elementos sin indexar devueltos por la búsqueda se muestra en el panel de detalles junto con los demás resultados de búsqueda estimados. Los elementos sin indexar también se incluirán en el tamaño total de los resultados de búsqueda estimados. Al exportar los resultados de la búsqueda, tiene la opción de incluir o no los elementos no indexados. La forma en que se configuran estas opciones puede dar lugar a diferencias entre los resultados de búsqueda reales y estimados que se descargan. 
    
- **Exportar los resultados de una búsqueda de contenido que incluya todas las ubicaciones de contenido** : Si la búsqueda desde la que está exportando resultados es una búsqueda de todas las ubicaciones de contenido de la organización, solo los elementos sin indexar de las ubicaciones de contenido que contienen se exportarán los elementos que coinciden con los criterios de búsqueda. Es decir, si no se encuentran resultados de búsqueda en un buzón de correo o en un sitio, no se exportarán los elementos no indexados de ese buzón o sitio. Sin embargo, los elementos no indexados de todas las ubicaciones de contenido (incluso los que no contienen elementos que coinciden con la consulta de búsqueda) se incluirán en los resultados de búsqueda estimados. 
    
    Como alternativa, si la búsqueda que está exportando los resultados de ubicaciones de contenido específicas incluidas, los elementos sin indexar (que no se excluyen por los criterios de búsqueda) de todas las ubicaciones de contenido especificadas en la búsqueda se exportarán. En este caso, el número estimado de elementos sin indexar y el número de elementos no indexados que se han exportado realmente deben ser iguales.
    
    El motivo por el que no se exportan elementos sin indexar desde cada ubicación de la organización es que puede aumentar la probabilidad de errores de exportación y aumentar el tiempo necesario para exportar y descargar los resultados de la búsqueda.
    
- **Formatos de archivo sin procesar frente a formatos de archivo** exportados-para elementos de Exchange, el tamaño estimado de los resultados de la búsqueda se calcula mediante el tamaño de los mensajes de Exchange sin formato. Sin embargo, los mensajes de correo electrónico se exportan en un archivo PST o como mensajes individuales (que tienen el formato EML files). Ambas opciones de exportación usan un formato de archivo diferente que los mensajes de Exchange en bruto, lo que hace que el tamaño total del archivo exportado sea diferente al tamaño de archivo estimado. 
    
- **Versiones de documentos** : para documentos de SharePoint, no se incluyen varias versiones de un documento en los resultados de búsqueda estimados. Pero tiene la opción de incluir todas las versiones del documento al exportar los resultados de la búsqueda, lo que aumentará el número real (y el tamaño total) de los documentos exportados. 
    
- **** Desduplicación: para los elementos de Exchange, la desduplicación reduce el número de elementos que se exportan. Tiene la opción de desduplicar los resultados de la búsqueda al exportarlos. Para los mensajes de Exchange, esto significa que solo se exporta una instancia de un mensaje, aunque ese mensaje se pueda encontrar en varios buzones. Los resultados de búsqueda estimados incluyen todas las instancias de un mensaje. Por lo tanto, si elige la opción de desduplicación al exportar los resultados de la búsqueda, el número real de elementos que se exportan podría ser considerablemente menor que el número estimado de elementos. 
    
    Otra cosa que debe tener en cuenta si elige la opción de desduplicación es que todos los elementos de Exchange se exportan en un único archivo PST y la estructura de carpetas de los buzones de origen no se conserva. El archivo PST exportado solo contiene los elementos de correo electrónico. Sin embargo, un informe de resultados de búsqueda contiene una entrada para cada mensaje exportado que identifica el buzón de origen donde se encuentra el mensaje. Esto le ayuda a identificar todos los buzones que contienen un mensaje duplicado. Si no habilita la desduplicación, se exportará un archivo PST independiente para cada buzón incluido en la búsqueda. 
    
## <a name="exporting-unindexed-items-from-the-ediscovery-center-in-sharepoint-online"></a>Exportar elementos sin indexar desde el centro de exhibición de documentos electrónicos en SharePoint Online

En el centro de eDiscovery de SharePoint Online, tiene la opción de incluir contenido no indizado (de Exchange y SharePoint) al exportar los resultados de una búsqueda de exhibición de documentos electrónicos. Para ello, seleccione la opción **incluir elementos que están cifrados o que tienen una opción de formato no reconocida** . Los elementos sin indexar (también denominados no rastreables en SharePoint) son elementos de Exchange y SharePoint que, por algún motivo, no se indizaron para la búsqueda. Los elementos de Exchange no indizados aparecen en el informe de **errores de índice de Exchange** que se incluyen al exportar los resultados de búsqueda. De forma similar, los elementos de SharePoint no indizados se muestran en el informe de **errores de índice de SharePoint** . Cuando se exportan elementos sin indexar, se descargan en **** una carpeta denominada no rastreable. Los elementos de Exchange no indizados se incluyen en un archivo PST; se descarga también cada documento sin indexar de SharePoint. El número de elementos sin indexar (si hay alguno) se enumeran en cada informe de errores de índice. El número de elementos sin indexar en los informes debe coincidir con el número de elementos sin indexar que se descargan. 
  
 **¿Cuáles son los motivos por los que el número de elementos sin indexar exportados no coincide con el número de elementos en el informe de errores de índice?** Como se explicó anteriormente, es posible que los elementos se hayan purgado de Office 365 entre el momento en que se ejecutó la estimación de la búsqueda y el momento en que se exportaron los resultados de la búsqueda. Una discrepancia similar puede producirse para los elementos sin indexar. Por ejemplo, el índice de búsqueda podría ser fecha de salida cuando se exportan los resultados de la búsqueda. Esto significa que un elemento no indexado que se exportó con los resultados de la búsqueda podría no aparecer en el informe de errores de índice porque el elemento no se indizó en el momento en que se exportaron los resultados de la búsqueda. Esto daría como resultado que se exportan más elementos sin indexar que los enumerados en el informe de errores de índice. De forma similar, un elemento sin indexar que aparezca en el informe de errores de índice podría haberse purgado de Office 365 antes de que se actualizara el índice de búsqueda. Esto daría como resultado que se exportan menos elementos no indizados de los enumerados en el informe de errores de índice. 
  
> [!NOTE]
> Si no selecciona la opción **incluir elementos cifrados o con formato no reconocido** al exportar los resultados de la búsqueda o simplemente descargar los informes, se descargan los informes de errores de índice pero no tienen ninguna entrada. Esto no significa que no haya errores de indización. Solo significa que los elementos sin indexar no se incluyeron en la exportación. 
  

