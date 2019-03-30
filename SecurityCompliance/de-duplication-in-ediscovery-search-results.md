---
title: Desduplicación en los resultados de búsqueda de eDiscovery
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 12/21/2016
ms.audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid: MOE150
ms.assetid: 5af334b6-a15d-4f73-97f8-1423457d9f6b
description: Tiene la opción de desduplicar los resultados de la búsqueda de eDiscovery que se exportan para que solo se exporte una copia de un mensaje de correo electrónico, aunque se hayan encontrado varias instancias del mismo mensaje en diferentes buzones.
ms.openlocfilehash: b3810e3568bd2c7aa1628bcfcebbad5a87468ff8
ms.sourcegitcommit: e7a776a04ef6ed5e287a33cfdc36aa2d72862b55
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/29/2019
ms.locfileid: "30999303"
---
# <a name="de-duplication-in-ediscovery-search-results"></a>Desduplicación en los resultados de búsqueda de eDiscovery

En este artículo se describe cómo funciona la desduplicación de los resultados de la búsqueda de exhibición de documentos electrónicos y se explican las limitaciones del algoritmo de desduplicación.
  
Al usar las herramientas de eDiscovery de Office 365 para exportar los resultados de una búsqueda de exhibición de documentos electrónicos, tiene la opción de desduplicar los resultados que se exportan. Escenario Cuando se habilita la desduplicación (de forma predeterminada, la desduplicación no está habilitada), solo se exporta una copia de un mensaje de correo electrónico aunque se hayan encontrado varias instancias del mismo mensaje en los buzones en los que se realizó la búsqueda. La desduplicación le ayuda a ahorrar tiempo, ya que reduce el número de elementos que tiene que revisar y analizar una vez que se han exportado los resultados de la búsqueda. Pero es importante comprender cómo funciona la desduplicación y tener en cuenta que hay limitaciones en el algoritmo que pueden hacer que un elemento único se marque como duplicado durante el proceso de exportación.
  
## <a name="how-duplicate-messages-are-identified"></a>Identificación de los mensajes duplicados

Las herramientas de eDiscovery de Office 365 usan una combinación de las siguientes propiedades de correo electrónico para determinar si un mensaje es un duplicado:
  
- **InternetMessageId** : esta propiedad especifica el identificador de mensaje de Internet de un mensaje de correo electrónico, que es un identificador único global que hace referencia a una versión específica de un mensaje específico. Este identificador lo genera el programa cliente de correo electrónico del remitente o el sistema de correo electrónico de host que envía el mensaje. Si una persona envía un mensaje a más de un destinatario, el identificador del mensaje de Internet será el mismo para cada instancia del mensaje. Las revisiones posteriores del mensaje original recibirán un identificador de mensaje diferente. 
    
- **ConversationTopic** : esta propiedad especifica el asunto de la secuencia de conversación de un mensaje. El valor de la propiedad **ConversationTopic** es la cadena que describe el tema general de la conversación. Una conservación consta de un mensaje inicial y de todos los mensajes que se envían como respuesta al mensaje inicial. Los mensajes dentro de la misma conversación tienen el mismo valor para la propiedad **ConversationTopic** . El valor de esta propiedad suele ser la línea de asunto del mensaje inicial que generó la conversación. 
    
- **BodyTagInfo** : se trata de una propiedad interna del almacén de Exchange. El valor de esta propiedad se calcula comprobando varios atributos en el cuerpo del mensaje. Esta propiedad se usa para identificar las diferencias en el cuerpo de los mensajes. 
    
Durante el proceso de exportación de eDiscovery, se comparan estas tres propiedades para cada mensaje que coincida con los criterios de búsqueda. Si estas propiedades son idénticas para dos (o más) mensajes, esos mensajes se determinan como duplicados y el resultado es que solo se exportará una copia del mensaje si la desduplicación está habilitada. El mensaje que se exporta se conoce como el "elemento de origen". La información sobre los mensajes duplicados se incluye en los informes **Results. csv** y **manifest. XML** incluidos en los resultados de la búsqueda exportados. En el archivo **Results. csv** , se identifica un mensaje duplicado con un valor en la columna **duplicar a elemento** . El valor de esta columna coincide con el valor de la columna **identidad del elemento** del mensaje que se exportó. 
  
Los gráficos siguientes muestran cómo se muestran los mensajes duplicados en los informes **Results. csv** y **manifest. XML** que se exportan con los resultados de la búsqueda. Estos informes no incluyen las propiedades de correo electrónico descritas anteriormente, que se usan en el algoritmo de desduplicación. En su lugar, los informes incluyen la propiedad de **identidad de elemento** asignada a los elementos por el almacén de Exchange. 
  
 ### <a name="resultscsv-report-viewed-in-excel"></a>Informe Results. csv (visto en Excel)
  
![Ver información acerca de los elementos duplicados en el informe Results. csv](media/e3d64004-3b91-4cba-b6f3-934b46cbdcdb.png)
  
 ### <a name="manifestxml-report-viewed-in-excel"></a>Informe de manifest. XML (visto en Excel)
  
![Ver información acerca de los elementos duplicados en el informe manifest. XML](media/69aa4786-9883-46ff-bcae-b35e0daf4a6d.png)
  
Además, se incluyen otras propiedades de los mensajes duplicados en los informes de exportación. Esto incluye el buzón en el que se encuentra el mensaje duplicado, si el mensaje se envió a un grupo de distribución y si el mensaje fue CC o CCO a otro usuario.
  
## <a name="limitations-of-the-de-duplication-algorithm"></a>Limitaciones del algoritmo de desduplicación

Existen algunas limitaciones conocidas del algoritmo de desduplicación que pueden hacer que los elementos únicos se marquen como duplicados. Es importante comprender estas limitaciones para que pueda decidir si va a usar o no la característica de desduplicación opcional.
  
Hay una situación en la que la característica de desduplicación podría identificar erróneamente un mensaje como duplicado y no exportarlo (pero lo puede citar como un duplicado en los informes de exportación). Se trata de mensajes que un usuario edita pero no envía. Por ejemplo, supongamos que un usuario selecciona un mensaje en Outlook, copia el contenido del mensaje y lo pega en un mensaje nuevo. A continuación, el usuario cambia una de las copias quitando o agregando datos adjuntos, o cambiando la línea de asunto o el propio cuerpo. Si estos dos mensajes coinciden con la consulta de una búsqueda de exhibición de documentos electrónicos, solo se exportará uno de los mensajes si la desduplicación está habilitada cuando se exportan los resultados de la búsqueda. Por lo tanto, aunque se haya cambiado el mensaje original o el mensaje copiado, no se ha enviado ninguno de los mensajes modificados y, por lo tanto, no se actualizaron los valores de las propiedades **InternetMessageId**, **ConversationTopic** y **BodyTagInfo** . Pero, como se ha explicado anteriormente, ambos mensajes aparecerán en la lista de informes de exportación 
  
Tenga en cuenta que los mensajes únicos también se pueden marcar como duplicados cuando se habilita la característica de protección de página de copia en escritura, como en el caso de un buzón que se encuentra en retención por juicio o conservación local. La característica Copy-on-Write copia el mensaje original (y lo guarda en la carpeta versiones de la carpeta de elementos recuperables del usuario) antes de que se guarde la revisión del elemento original. En este caso, la copia revisada y el mensaje original (en la carpeta elementos recuperables) pueden considerarse mensajes duplicados y, por lo tanto, solo uno de ellos se exportará.
  
> [!IMPORTANT]
> Si las limitaciones del algoritmo de desduplicación pueden afectar a la calidad de los resultados de la búsqueda, no se debe habilitar la desduplicación al exportar los elementos. Si es improbable que las situaciones descritas en esta sección sean un factor de los resultados de la búsqueda y desea reducir el número de elementos que son más probables que estén duplicados, considere la posibilidad de habilitar la desduplicación. 
  
## <a name="more-information"></a>Más información

- La información de este artículo es aplicable al exportar resultados de búsqueda mediante una de las siguientes herramientas de eDiscovery:
    
  - Búsqueda de contenido en el centro de cumplimiento en Office 365
    
  - Exhibición de documentos electrónicos local en Exchange Online
    
  - Centro de exhibición de documentos electrónicos en SharePoint Online
    
- Para obtener más información sobre cómo exportar los resultados de la búsqueda, consulte:
    
  - [Exportar búsqueda de contenido](export-search-results.md)
    
  - [Exportar un informe de búsqueda de contenido](export-a-content-search-report.md)
    
  - [Exportar los resultados de la búsqueda de exhibición de documentos electrónicos local a un archivo PST](https://go.microsoft.com/fwlink/p/?linkid=832671)
    
  - [Exportar contenido y crear informes en el Centro de eDiscovery](https://support.office.com/article/7b2ea190-5f9b-4876-86e5-4440354c381a)
