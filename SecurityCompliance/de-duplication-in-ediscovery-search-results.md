---
title: Desduplicación en los resultados de búsqueda de eDiscovery
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 12/21/2016
ms.audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 5af334b6-a15d-4f73-97f8-1423457d9f6b
description: Tiene la opción para duplicar Desaprovisionamiento de los resultados de búsqueda de exhibición de documentos electrónicos que se exportan para que se exporta sólo una copia de un mensaje de correo electrónico, aunque podrían haber encontrado varias instancias del mismo mensaje en buzones diferentes.
ms.openlocfilehash: 02a4f9f6db0fb8831d5e5cc13adaffbd0c4dcecc
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22536738"
---
# <a name="de-duplication-in-ediscovery-search-results"></a>Desduplicación en los resultados de búsqueda de eDiscovery

En este artículo se describe cómo la desduplicación de los resultados de búsqueda de exhibición de documentos electrónicos funciona y explica las limitaciones del algoritmo la desduplicación.
  
Cuando el uso de herramientas de exhibición de documentos electrónicos de Office 365 para exportar los resultados de una búsqueda de exhibición de documentos electrónicos, tiene la opción para duplicar Desaprovisionamiento de los resultados que se exportan. ¿Qué significa esto? Al habilitar la desduplicación (de forma predeterminada, la desduplicación no está habilitada), se exporta sólo una copia de un mensaje de correo electrónico, aunque podrían haber encontrado varias instancias del mismo mensaje en los buzones de correo que se desea buscar. La desduplicación le ayuda a ahorrar tiempo al reducir el número de elementos que se deben revisar y analizar después de que se exportan los resultados de búsqueda. Pero es importante comprender cómo funciona la desduplicación y tenga en cuenta que existen limitaciones en el algoritmo que pueden impedir que un único elemento que se marcará como un duplicado durante el proceso de exportación.
  
## <a name="how-duplicate-messages-are-identified"></a>Cómo se identifican los mensajes duplicados

Herramientas de Office 365 exhibición de documentos electrónicos use una combinación de las siguientes propiedades de correo electrónico para determinar si un mensaje es un duplicado:
  
- **InternetMessageId** - esta propiedad especifica el identificador de mensaje de Internet de un mensaje de correo electrónico, que es un identificador único global que hace referencia a una versión específica de un mensaje específico. Este identificador es generado por el programa de cliente de correo electrónico del remitente o del sistema de correo electrónico de host que envía el mensaje. Si una persona envía un mensaje a más de un destinatario, el identificador de mensaje de Internet será el mismo para cada instancia del mensaje. Las revisiones posteriores al mensaje original recibirá un identificador de mensaje diferentes. 
    
- **ConversationTopic** - su propiedad especifica al asunto de la secuencia de conversación de un mensaje. El valor de la propiedad **ConversationTopic** es la cadena que describe el tema general de la conversación. Una conservación consta de un mensaje inicial y todos los mensajes enviados en la respuesta al mensaje inicial. Los mensajes dentro de la misma conversación tienen el mismo valor para la propiedad **ConversationTopic** . El valor de esta propiedad normalmente es la línea de asunto del mensaje inicial que generan a la conversación. 
    
- **BodyTagInfo** - ésta es una propiedad de almacén de Exchange interno. El valor de esta propiedad se calcula mediante la comprobación de diversos atributos en el cuerpo del mensaje. Esta propiedad se usa para identificar las diferencias en el cuerpo de los mensajes. 
    
Durante el proceso de exportación de exhibición de documentos electrónicos, se comparan estas tres propiedades para cada mensaje que coincide con los criterios de búsqueda. Si estas propiedades son idénticas para los mensajes de dos (o más), los mensajes se determinan a ser duplicados y el resultado es que se exportará sólo una copia del mensaje si está habilitada la desduplicación. El mensaje que se ha exportado se conoce como el elemento de"origen". Se incluye información acerca de los mensajes duplicados en el **Results.csv** y **Manifest.xml** los informes que se incluyen con los resultados de búsqueda exportado. En el archivo **Results.csv** , un mensaje duplicado se identifica por tener un valor en la columna **duplicada para el elemento** . El valor de esta columna coincide con el valor de la columna de **Identidad del elemento** para el mensaje que se ha exportado. 
  
Los gráficos siguientes muestran cómo duplicados mensajes se muestran en los informes de **Results.csv** y **Manifest.xml** que se exportan con los resultados de búsqueda. Estos informes no incluyen las propiedades de correo electrónico se ha descrito anteriormente, que se usan en el algoritmo de la desduplicación. En su lugar, los informes incluyen la propiedad de **Identidad del elemento** que se asigna a los elementos por el almacén de Exchange. 
  
 ### <a name="resultscsv-report-viewed-in-excel"></a>Informe de Results.csv (que se ven en Excel)
  
![Visualización de información sobre los elementos duplicados en el informe de Results.csv](media/e3d64004-3b91-4cba-b6f3-934b46cbdcdb.png)
  
 ### <a name="manifestxml-report-viewed-in-excel"></a>Manifest.XML viendo el informe (en Excel)
  
![Visualización de información sobre los elementos duplicados en el informe de Manifest.xml](media/69aa4786-9883-46ff-bcae-b35e0daf4a6d.png)
  
Además, se incluyen otras propiedades de los mensajes duplicados en los informes de exportación. Esto incluye el buzón que se encuentra el mensaje duplicado, si el mensaje se envió a un grupo de distribución, y si el mensaje fue sería Cc o CCO d a otro usuario.
  
## <a name="limitations-of-the-de-duplication-algorithm"></a>Limitaciones del algoritmo de la desduplicación

Existen algunas limitaciones conocidas del algoritmo de desduplicación que pueden impedir que los elementos exclusivos obtener marcados como duplicados. Es importante comprender estas limitaciones para que pueda decidir si desea usar la característica de desduplicación opcional o no.
  
Hay una situación donde la característica de la desduplicación podría identificar erróneamente un mensaje como un duplicado y no exportarla (pero aún se citan como un duplicado en los informes de exportación). Estos son los mensajes que un usuario edita pero no se envíe. Por ejemplo, supongamos que un usuario selecciona un mensaje en Outlook, copia el contenido del mensaje y, a continuación, pega en un mensaje nuevo. A continuación, el usuario cambia una de las copias de quitar o agregar datos adjuntos o cambiando la línea de asunto o el cuerpo de la propia. Si estos dos mensajes coinciden con la consulta de una búsqueda de exhibición de documentos electrónicos, sólo uno de los mensajes se exportará si se habilita la desduplicación cuando se exportan los resultados de búsqueda. Por lo tanto, aunque se cambió el mensaje original o el mensaje copiado, ninguno de los mensajes revisados se enviaron y, por tanto, no se han actualizado los valores de las propiedades **InternetMessageId**, **ConversationTopic** y **BodyTagInfo** . Pero como se explica anteriormente, los mensajes se mostrarán en los informes de exportación 
  
Tenga en cuenta que los mensajes únicos también estén marcados como duplicados cuando está habilitada la característica de protección de la página de copia en escritura, como en el caso de un buzón de correo que se está en suspensión por litigio o suspensión en contexto. La característica de copia en escritura copia el mensaje original (y se guarda en la carpeta de versiones de la carpeta del usuario elementos recuperables) antes de guarda la revisión al elemento original. En este caso, la copia revisada y el mensaje original (en la carpeta elementos recuperables) podrían considerarse como mensajes duplicados y por lo tanto, se debería exportar sólo uno de ellos.
  
> [!IMPORTANT]
> Si las limitaciones del algoritmo la desduplicación pueden afectar a la calidad de los resultados de búsqueda, no debe habilitar la desduplicación al exportar elementos. Si las situaciones que se describen en esta sección están poco probable que sea un factor en los resultados de búsqueda, y desea reducir el número de elementos más probabilidades de ser duplicados, debería considerar habilitar la desduplicación. 
  
## <a name="more-information"></a>Más información

- La información de este artículo es aplicable al exportar los resultados de búsqueda mediante una de las siguientes herramientas de exhibición de documentos electrónicos:
    
  - Búsqueda de contenido en la seguridad de Office 365 &amp; centro de cumplimiento
    
  - Exhibición de documentos electrónicos local en Exchange Online
    
  - Centro de exhibición de documentos electrónicos en SharePoint Online
    
- Para obtener más información acerca de cómo exportar los resultados de búsqueda, vea:
    
  - [Exportar los resultados de búsqueda de la seguridad de Office 365 &amp; centro de cumplimiento](export-search-results.md)
    
  - [Exportar un informe de búsqueda de contenido de la seguridad de Office 365 &amp; centro de cumplimiento](export-a-content-search-report.md)
    
  - [Resultados de búsqueda de exhibición de documentos electrónicos en lugar de exportación a un archivo PST](https://go.microsoft.com/fwlink/p/?linkid=832671)
    
  - [Exportar contenido y crear informes en el Centro de eDiscovery](https://support.office.com/article/7b2ea190-5f9b-4876-86e5-4440354c381a)
