---
title: Diferencias entre los resultados de búsqueda de exhibición de documentos electrónicos estimados y reales en Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 4/13/2017
ms.audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- SPO160
- MOE150
- MET150
ms.assetid: 8f20ca4f-a908-46ec-99e6-9890d269ecf2
description: 'Comprender por qué los resultados de búsqueda estimados y reales pueden variar en las búsquedas que ejecute las herramientas de exhibición de documentos electrónicos en Office 365. '
ms.openlocfilehash: 15fd34fc4b2f7edaa4020043d3dd7ffc21d643ad
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22535619"
---
# <a name="differences-between-estimated-and-actual-ediscovery-search-results-in-office-365"></a>Diferencias entre los resultados de búsqueda de exhibición de documentos electrónicos estimados y reales en Office 365

En este tema se aplica a las búsquedas que se pueden ejecutar mediante una de las siguientes herramientas de exhibición de documentos electrónicos de Microsoft:  <br/>  
- Contenido de búsqueda en la seguridad de Office 365 &amp; centro de cumplimiento  <br/>  
- Exhibición de documentos electrónicos en contexto en el centro de administración de Exchange (EAC)  <br/>  
- Centro de exhibición de documentos electrónicos en SharePoint Online  <br/> 
   
Cuando se ejecuta una búsqueda de exhibición de documentos electrónicos, la herramienta que usa devolverá una estimación del número de elementos (y su tamaño total) que cumplen los criterios de búsqueda. Por ejemplo, al ejecutar una búsqueda en la seguridad &amp; centro de cumplimiento, la búsqueda estimada se muestran los resultados en el panel de detalles para la búsqueda seleccionada.
  
![Cálculo de resultados que se muestra en el panel de detalles de la búsqueda seleccionada](media/74e4ce83-40be-41a9-b60f-5ad447e79fe4.png)
  
Esto es la misma estimación del tamaño total y el número de elementos que se muestra en la exhibición de documentos electrónicos herramienta para exportar al exportar los resultados a un equipo local y en el informe de resumen de exportación que se descarga con los resultados de búsqueda.
  
**Resultados de estimado en la herramienta de exportación de exhibición de documentos electrónicos**

![Resultados estimados en la herramienta de exportación de exhibición de documentos electrónicos](media/d34312a5-0ee6-49aa-9460-7ea0015a6e66.png)
  
**Estimado resultados en el informe de resumen de exportación**

![Los resultados de la búsqueda estimada se incluyen en el informe de resumen de exportación](media/44b579da-86c2-4f33-81b5-84d604003eda.png)
  
Sin embargo, como verá en la captura de pantalla anterior del informe de resumen de exportación, el tamaño y el número de resultados de búsqueda reales que realmente se descargan son diferentes del tamaño y el número de resultados de búsqueda estimado. 
  
![Diferencia entre los resultados de la búsqueda estimados y descargados](media/84aef318-230f-430d-9d9e-02f21342d364.png)
  
Estas son algunas de las razones para estas diferencias:
  
- **Los resultados de la forma se estimación** - una estimación de los resultados de búsqueda son sólo eso, una estimación (y no un recuento real) de los elementos que cumplen los criterios de consulta de búsqueda. Para compilar la estimación de elementos de Exchange, una lista de los identificadores que cumplen los criterios de búsqueda del mensaje se solicita desde la base de datos de Exchange mediante la herramienta de exhibición de documentos electrónicos que está utilizando. Pero al exportar los resultados de búsqueda, la búsqueda se vuelve a ejecutar y los mensajes reales se recuperan de la base de datos de Exchange. Por lo que pueden provocar que estas diferencias debido a cómo se determinan el número estimado de elementos y el número real de elementos. 
    
- **Los cambios que se producen entre el momento cuando la estimación y exportar los resultados de búsqueda** - al exportar los resultados de búsqueda, la búsqueda se reinicie para recopilar ese elementos más recientes en el índice de búsqueda que cumplen los criterios de búsqueda. Es posible que hay adicionales se crearon elementos, enviado o recibido que cumplen los criterios de búsqueda en el tiempo entre cuando se recopilaron los resultados de búsqueda estimado y cuando se exportaron los resultados de búsqueda. También es posible que los elementos que estaban en el índice de búsqueda cuando los resultados de búsqueda se han estimado son ya no existe debido a que se han purgado desde la ubicación del contenido antes de que se exportan los resultados de búsqueda. Una forma de mitigar este problema es especificar un intervalo de fechas para una búsqueda de exhibición de documentos electrónicos. Otra forma consiste en colocar una suspensión en ubicaciones de contenido para que los elementos se conservan y no se puede purgar. 
    
- **Elementos sin indizar** - los elementos que están indizadas para la búsqueda puede provocar diferencias entre los resultados de búsqueda estimado y real. Por ejemplo, en lugar de exhibición de documentos electrónicos en el centro de exhibición de documentos electrónicos en SharePoint y Exchange no incluir elementos sin indizar (que no cumplen con los criterios de búsqueda) al ejecutar una búsqueda para calcular los resultados de búsqueda. Pero puede incluir elementos sin indizar al exportar los resultados de búsqueda. Si incluye elementos sin indizar al exportar los resultados de búsqueda, puede haber más elementos que se exportan. Esto causará una diferencia entre los resultados de búsqueda estimado y exportado. 
    
    Cuando se usa la herramienta de búsqueda de contenido en la seguridad &amp; centro de cumplimiento, tiene la opción de incluir elementos sin indizar en la estimación de la búsqueda. El número de elementos sin indizar devueltos por la búsqueda aparece en el panel de detalles, junto con los otros resultados de búsqueda estimado. Todos los elementos sin indizar también se incluirán en el tamaño total de los resultados de búsqueda estimado. Al exportar los resultados de búsqueda, tiene la opción de incluir o no incluir elementos sin indizar. Cómo configurar estas opciones puede dar lugar a diferencias entre estimado y los resultados de búsqueda real que se descargan. 
    
- **Exportar los resultados de una búsqueda de contenido que incluye todas las ubicaciones de contenido** - si la búsqueda que se va a exportar los resultados de una búsqueda de todas las ubicaciones de contenido en su organización y, a continuación, sólo los elementos sin indizar desde ubicaciones de contenido que contienen no se ha se exportarán los elementos que coinciden con los criterios de búsqueda. En otras palabras, si no hay resultados de búsqueda se encuentran en un buzón o un sitio, a continuación, los elementos sin indizar en ese buzón de correo o el sitio no se exportará. Sin embargo, sin indizar los elementos de todas las ubicaciones de contenido (incluso los que no contienen elementos que coinciden con la consulta de búsqueda) se incluirán en los resultados de búsqueda estimado. 
    
    Como alternativa, si la búsqueda que se va a exportar los resultados de incluido ubicaciones de contenido específicas, se exportarán los elementos sin indizar (que no están excluidos por los criterios de búsqueda) de todas las ubicaciones de contenido especificados en la búsqueda. En este caso, el número estimado de elementos sin indizar y el número de elementos sin indizar realmente exportado deben ser el mismo.
    
    La razón para no exportar elementos sin indizar desde cada ubicación en la organización es porque es posible que aumente la probabilidad de errores de exportación y aumentar el tiempo que se tarda en exportar y descargar los resultados de búsqueda.
    
- **Formatos de archivo sin procesar frente a formatos de archivo exportado** - elementos para Exchange, el tamaño estimado de los resultados de búsqueda se calcula mediante el uso de los tamaños de mensaje de Exchange sin procesar. Sin embargo, se exportan los mensajes de correo electrónico en un archivo PST o que los mensajes individuales (que tienen el formato como archivos EML). Ambos estas opciones de exportación utilizan un archivo diferente formato ese sin procesar mensajes de Exchange, lo que da como resultado el tamaño total del archivo exportado que se va a diferentes que el tamaño estimado del archivo. 
    
- **Las versiones de documentos** - documentos de SharePoint, varias versiones de un documento no se incluyen en los resultados de búsqueda estimado. Pero tiene la opción de incluir todas las versiones del documento al exportar los resultados de búsqueda, lo que aumentarán el número real (y el tamaño total) de los documentos exportados. 
    
- **La desduplicación** - elementos para Exchange, la desduplicación reduce el número de elementos que se exportan. Tiene la opción para duplicar Desaprovisionamiento de los resultados de búsqueda al exportar a ellos. Para los mensajes de Exchange, esto significa que se exporta una sola instancia de un mensaje, incluso aunque ese mensaje podría encontrarse en varios buzones de correo. Los resultados de búsqueda estimado incluirán cada instancia de un mensaje. Por lo que si elige la opción de desduplicación al exportar los resultados de búsqueda, el número real de elementos que se exportan podría ser considerablemente menor que el número estimado de elementos. 
    
    Otra cosa a tener en cuenta si elige la opción de desduplicación es que se exportan todos los elementos de Exchange en un único archivo PST y no se conserva la estructura de carpetas de los buzones de origen. El archivo PST exportado contiene sólo los elementos de correo electrónico. Sin embargo, un informe de resultados de búsqueda contiene una entrada para cada mensaje exportado que identifica el buzón de origen donde se encuentra el mensaje. Esto ayuda a identificar todos los buzones que contienen un mensaje duplicado. Si no habilita la desduplicación, se exporta un archivo PST independiente para cada buzón que se incluyen en la búsqueda. 
    
## <a name="exporting-unindexed-items-from-the-ediscovery-center-in-sharepoint-online"></a>Exportar elementos sin indizar desde el centro de exhibición de documentos electrónicos en SharePoint Online

En el centro de exhibición de documentos electrónicos en SharePoint Online, tiene la opción de incluir el contenido sin indizar (de Exchange y SharePoint) al exportar los resultados de una búsqueda de exhibición de documentos electrónicos. Para ello, seleccione la opción de **incluir elementos que se cifran o tienen un formato no reconocido** . Elementos sin indizar (también denominados uncrawlable en SharePoint) son elementos en Exchange y SharePoint que, por algún motivo, no estaba indizado para la búsqueda. Sin indizar elementos de Exchange se enumeran en el informe de **Errores de Exchange de índice** que se ha incluido al exportar los resultados de búsqueda. De forma similar, sin indizar los elementos de SharePoint se enumeran en el informe de **Errores del índice de SharePoint** . Al exportar elementos sin indizar, descargados en una carpeta denominada **Uncrawlable**. Sin indizar elementos de Exchange se incluyen en un archivo PST; todos los documentos sin indizar de SharePoint se descargan demasiado. El número de elementos sin indizar (si hay alguno) se enumeran en cada informe de errores de índice. El número de elementos sin indizar en los informes debe coincidir con el número de elementos sin indizar que se descargan. 
  
 **¿Cuáles son algunas de las razones si el número de elementos sin indizar exportados no coincide con el número de elementos en el informe de errores de índice?** Como se explica anteriormente, es posible que los elementos se han purgado desde Office 365 entre el momento en que se ejecutó la estimación de la búsqueda y la hora en que se exportaron los resultados de búsqueda. Puede producirse una discrepancia similar para los elementos sin indizar. Por ejemplo, podría ser el índice de búsqueda a la fecha cuando se exportan los resultados de búsqueda. Esto significa que un elemento no indizado que se ha exportado con los resultados de búsqueda no es posible que aparezca en el informe de errores de índice debido a que el elemento no se indiza en el momento en que se exportaron los resultados de búsqueda. El resultado sería más sin indizar elementos que se va a exportar, que se enumeran en el informe de errores de índice. De forma similar, un elemento no indizado que aparecen en el informe de errores de índice podría se han purgado desde Office 365 antes de que se actualizó el índice de búsqueda. El resultado sería menos elementos sin indizar, que se va a exportar, que se enumeran en el informe de errores de índice. 
  
> [!NOTE]
> Si no selecciona la opción de **incluir elementos que se cifran o tienen un formato no reconocido** al exportar los resultados de búsqueda o descargar sólo los informes, se descargan los informes de error de índice pero no tienen todas las entradas. Esto no significa que no existe los errores de indización. Sólo significa que los elementos no indizados no se incluyeron en la exportación. 
  

