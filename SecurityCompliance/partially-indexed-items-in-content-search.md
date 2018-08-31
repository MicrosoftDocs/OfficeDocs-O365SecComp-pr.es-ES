---
title: Elementos parcialmente indizados en la búsqueda de contenido en Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 5/11/2018
ms.audience: Admin
ms.topic: overview
f1_keywords:
- ms.o365.cc.UnindexedItemsLearnMore
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- SPO160
- MOE150
- MET150
ms.assetid: d1691de4-ca0d-446f-a0d0-373a4fc8487b
description: 'Obtenga información sobre los elementos sin indizar de Exchange y SharePoint que puede incluir en una búsqueda de contenido que se ejecute a través de la seguridad de Office 365 &amp; centro de cumplimiento. '
ms.openlocfilehash: 4624985a9c80313d0222470e6cfb2c56495f2142
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22535724"
---
# <a name="partially-indexed-items-in-content-search-in-office-365"></a>Elementos parcialmente indizados en la búsqueda de contenido en Office 365

Una búsqueda de contenido que se ejecuta desde la seguridad de Office 365 &amp; centro de cumplimiento incluye automáticamente los elementos indizados parcialmente en los resultados de búsqueda estimado al ejecutar una búsqueda. Los elementos indizados parcialmente son los elementos del buzón de Exchange y documentos en SharePoint y OneDrive para los sitios de negocio que, por algún motivo, completamente no estaban indizados para la búsqueda. En Exchange, un elemento indizado parcialmente normalmente contiene un archivo, de un tipo de archivo que no se pueden indizar, que se adjunta a un mensaje de correo electrónico. Estas son algunas razones por qué elementos no se pueden indizar para la búsqueda y se devuelven como elementos indizados parcialmente al ejecutar una búsqueda: 
  
- El tipo de archivo es no reconocido o no compatibles para la indización.
    
-  Los mensajes tienen un archivo adjunto sin un controlador válido, como archivos de imagen; Ésta es la causa más común de elementos de correo electrónico parcialmente indizados. 
    
- El tipo de archivo se admite para indización pero se produjo un error de indización en un archivo específico.
    
- Se han adjuntado demasiados archivos a un mensaje de correo electrónico.
    
- Un archivo adjuntado a un mensaje de correo electrónico es demasiado grande.
    
- Un archivo se ha cifrado con tecnologías que no son de Microsoft.
    
- Un archivo está protegido por contraseña.
    
> [!NOTE]
> La mayoría de las organizaciones de Office 365 tienen menos del 1% de contenido por volumen e inferior al 12% el tamaño que se indiza parcialmente. El motivo de la diferencia entre el volumen y el tamaño es que los archivos más grandes tienen una mayor probabilidad de que contiene contenido que no se pueden indizar completamente. 
  
Para las investigaciones legales, su organización puede ser necesaria para revisar los elementos indizados parcialmente. También puede especificar si se incluyen los elementos indizados parcialmente al exportar los resultados de búsqueda a un equipo local o al preparar los resultados para el análisis con Office 365 avanzada exhibición de documentos electrónicos. Para obtener más información, vea [Investigating parcialmente indizar los elementos de exhibición de documentos electrónicos de Office 365](investigating-partially-indexed-items-in-ediscovery.md).
  
## <a name="file-types-not-indexed-for-search"></a>Tipos de archivo no indexados para búsquedas

Determinados tipos de archivos, como mapa de bits o archivos MP3, no contienen contenido que se puede indizar. Como resultado, la indización de los servidores de Exchange de búsqueda y SharePoint no realizan la indización de texto completo en estos tipos de archivos. Estos tipos de archivos se consideran tipos de archivo no compatibles. También existen tipos de archivo para que la indización de texto completo se ha deshabilitado, de forma predeterminada o por un administrador. Tipos de archivo no compatibles y deshabilitada se etiquetan como elementos sin indizar en búsquedas de contenido. Tal y como se ha indicado anteriormente, parcialmente indizados elementos pueden incluirse en el conjunto de resultados de búsqueda cuando se ejecuta una búsqueda, exportar los resultados de búsqueda a un equipo local, o preparar los resultados de búsqueda de exhibición de documentos electrónicos avanzada. 
  
Para obtener una lista de formatos de archivo compatibles y deshabilitados, vea los temas siguientes:
  
- **Exchange** - [formatos de archivo indizados por la búsqueda de Exchange](https://go.microsoft.com/fwlink/p/?LinkID=386618)
    
- **Exchange** - [Get-SearchDocumentFormat](https://go.microsoft.com/fwlink/p/?LinkID=724037)
    
- **SharePoint** - [extensiones de nombre de archivo y analizados predeterminados tipos de archivo en SharePoint](https://go.microsoft.com/fwlink/p/?LinkID=404033)
    

  
## <a name="messages-and-documents-with-partially-indexed-file-types-can-be-returned-in-search-results"></a>Los mensajes y documentos con parcialmente indizan tipos se pueden devolver en los resultados de búsqueda de archivo

No todos los mensajes de correo electrónico con datos adjuntos de archivos indexados parcialmente o todos los documentos de SharePoint parcialmente indizado automáticamente se devuelven como un elemento indizado parcialmente. Esto es debido a que otro mensaje o propiedades de documento, como la propiedad **Subject** en mensajes de correo electrónico y las propiedades de **título** o **autor** para los documentos están indizadas y disponibles que se desea buscar. Por ejemplo, una búsqueda de palabra clave para "financieros" devolverá elementos con datos adjuntos de archivos indexados parcialmente si esa palabra clave aparece en el asunto de un mensaje de correo electrónico o en el nombre de archivo o el título de un documento. Sin embargo, si la palabra clave sólo aparece en el cuerpo del archivo, el mensaje o documento se devolverá como un elemento indizado parcialmente. 
  
De forma similar, los mensajes con datos adjuntos de archivos indexados parcialmente y documentos de un tipo de archivo indizados parcialmente se incluyen en los resultados de búsqueda cuando otras propiedades de mensaje o un documento, que están indizados y se pueden buscar, cumplan los criterios de búsqueda. Las propiedades de mensaje que están indizadas para la búsqueda incluyen las fechas enviadas y recibidas, remitente y destinatario, el nombre de archivo de un archivo adjunto y el texto en el cuerpo del mensaje. Propiedades del documento indizadas para la búsqueda incluyen las fechas de creación y modificación. Por lo tanto, aunque un datos adjuntos del mensaje pueden ser un elemento indizado parcialmente, el mensaje se incluirá en los resultados de búsqueda normal si el valor de otras propiedades de mensaje o el documento coincide con los criterios de búsqueda.
  
Para obtener una lista de correo electrónico y propiedades de documentos que puede buscar mediante el uso de la característica de búsqueda en la seguridad &amp; centro de cumplimiento, consulte [consultas de palabra clave y las condiciones de búsqueda para la búsqueda de contenido](keyword-queries-and-search-conditions.md).
  

  
## <a name="partially-indexed-items-included-in-the-search-results"></a>Elementos indizados parcialmente incluidos en los resultados de búsqueda
<a name="unindexeditemsresults"> </a>

La organización es posible que sea necesaria para identificar y realizar un análisis adicional en los elementos parcialmente indizados para determinar qué son, lo que contienen y, si son relevantes para una investigación específica. Como se explica anteriormente, los elementos indizados parcialmente en las ubicaciones de contenido que se buscan se incluirán automáticamente con los resultados de búsqueda estimado. Tiene la opción de incluir estos elementos indizados parcialmente al exportar los resultados de búsqueda o preparar los resultados de búsqueda de exhibición de documentos electrónicos avanzada. Para incluir los elementos indizados parcialmente al exportar los resultados de búsqueda o preparación de exhibición de documentos electrónicos avanzada, seleccione una de las opciones para incluir los elementos que tienen un formato no reconocido, se cifran o no estaban indizados por otras razones.
  
Tenga en cuenta acerca de los elementos indizados parcialmente la siguiente:
  
- Cuando se ejecuta una búsqueda de contenido, el número total y el tamaño de los elementos indizados parcialmente (devuelto por la consulta de búsqueda) se muestran en las estadísticas de búsqueda en el panel de detalles, como una etiqueta como "sin indizar elementos".
    
- Al exportar los resultados de búsqueda e incluir elementos parcialmente indizados, elementos de Exchange parcialmente indizados se exportan a un archivo PST independiente para cada buzón de correo en los que se encuentran, o bien como los mensajes individuales si selecciona la opción de descargar los elementos de Exchange como mensajes. los elementos de SharePoint parcialmente indizados se exportan a una carpeta denominada **Uncrawlable**.
    
- Si la búsqueda que se va a exportar los resultados de era una búsqueda de ubicaciones de contenido específicas o todas las ubicaciones de contenido en su organización, se exportarán sólo los elementos sin indizar desde ubicaciones de contenido que contienen elementos que coinciden con los criterios de búsqueda. En otras palabras, si no hay resultados de búsqueda se encuentran en un buzón o un sitio, a continuación, los elementos sin indizar en ese buzón de correo o el sitio no se exportará. El motivo es que exportar elementos indizados parcialmente de una gran cantidad de ubicaciones en la organización puede aumentar la probabilidad de errores de exportación y aumentan el tiempo que se tarda en exportar y descargar los resultados de búsqueda.
    
    Para exportar elementos indizados parcialmente de todas las ubicaciones de contenido para una búsqueda, configurar la búsqueda para devolver todos los elementos (mediante la eliminación de todas las palabras clave de la consulta de búsqueda) y, a continuación, exportar sólo parcialmente elementos indizados al exportar los resultados de búsqueda (haciendo clic en sólo ** los elementos que tienen un formato no reconocido, se cifran o no estaban indizados por otras razones** en **Opciones de salida**).
    
- Si decide incluir todos los elementos de buzón de correo en los resultados de búsqueda, o si una consulta de búsqueda no especifica las palabras clave o sólo especifica un intervalo de fechas, es posible que los elementos indizados parcialmente no se copiar al archivo PST que contiene los elementos indizados parcialmente. Esto es debido a que todos los elementos, incluidos los elementos indizados parcialmente, se incluirá automáticamente en los resultados de búsqueda normal.
    
- Los elementos indizados parcialmente no están disponibles para la vista preliminar. Se debe exportar los resultados de búsqueda para ver los elementos indizados parcialmente devueltos por la búsqueda.

## <a name="partially-indexed-items-excluded-from-the-search-results"></a>Elementos indizados parcialmente excluidos de los resultados de búsqueda

Si un elemento se indiza parcialmente pero no satisface los criterios de consulta de búsqueda, no se incluye como un elemento indizado parcialmente en los resultados de búsqueda. En otras palabras, el elemento se excluye de los resultados de búsqueda. Por ejemplo, supongamos que ejecutar una búsqueda y no se incluye cualquier palabras clave o propiedades porque desea incluir todo el contenido. Pero incluye una condición de intervalo de fecha para la consulta. Si un elemento indizado parcialmente cae fuera de ese intervalo de fechas, no se incluye como un elemento indizado parcialmente. Intervalos de fechas son una forma eficaz para excluir los elementos indizados parcialmente de los resultados de búsqueda.
  
De forma similar, si decide incluir elementos indizados parcialmente al exportar los resultados de una búsqueda, no se exportará elementos indizados parcialmente que se han excluido de los resultados de búsqueda.
  
Una excepción a esta regla es cuando se crea una suspensión basada en consultas que está asociado con un caso de exhibición de documentos electrónicos. Si crea una suspensión basada en consultas, todos los elementos indizados parcialmente se pondrán en espera. Esto incluye elementos indizados parcialmente que no coincidan con los criterios de consulta de búsqueda y parcialmente indizada que pueden quedar fuera de una condición de intervalo de fecha. Para obtener más información acerca de la creación basada en consultas de suspensiones, consulte el paso 4 en [los casos de exhibición de documentos electrónicos en el centro de cumplimiento y seguridad de Office 365](ediscovery-cases.md#step-4-place-content-locations-on-hold).
  
## <a name="indexing-limits-for-messages-in-content-search"></a>Límites de indización para los mensajes en búsqueda de contenido

En la siguiente tabla se describe los límites de indización que podrían dar como resultado un mensaje de correo electrónico que se devuelven como un elemento indizado parcialmente en una búsqueda de contenido en Office 365.
  
Para obtener una lista de la indización de los límites de documentos de SharePoint, vea [los límites de búsqueda de SharePoint Online](https://support.office.com/article/7c06e9ed-98b6-4304-a900-14773a8fa32f).
  
|**Límite de indización**|**Notas**|**Descripción**|
|:-----|:-----|:-----|
|Tamaño máximo de datos adjuntos (excluyendo los archivos de Excel)  <br/> |150 MB  <br/> |El tamaño máximo de datos adjuntos de correo electrónico que se va a analizar para la indización. No se puede analizar los datos adjuntos que es mayor que este límite para la indización y el mensaje con los datos adjuntos se marcarán como parcialmente indizados.<br/><br/> **Nota:** Análisis es el proceso donde el servicio de Index Server extrae el texto de los datos adjuntos, quita los caracteres innecesarios como signos de puntuación y espacios y, a continuación, divide el texto en palabras (en un proceso denominado tokenización), que, a continuación, se almacenan en el índice.           |
|Tamaño máximo de archivos de Excel  <br/> |4 MB  <br/> |El tamaño máximo de un archivo de Excel ubicada en un sitio o adjunto a un mensaje de correo electrónico que se va a analizar para la indización. Cualquier archivo de Excel que es mayor que este límite no se puede analizar y el archivo o el correo electrónico que el mensaje con el archivo adjunto se marcarán como no indexados.  <br/> |
|Número máximo de datos adjuntos  <br/> |250  <br/> |El número máximo de archivos adjuntado a un mensaje de correo electrónico que se va a analizar para la indización. Si un mensaje tiene más de 250 datos adjuntos, se analizan y se indizan el primero 250 datos adjuntos, y el mensaje está marcado como parcialmente indizados porque tenía datos adjuntos adicionales que no se han analizado.  <br/> |
|Profundidad de máximo de datos adjuntos  <br/> |30  <br/> |El número máximo de datos adjuntos anidados que se analizan. Por ejemplo, si un mensaje de correo electrónico tiene otro mensaje adjunto y el mensaje adjunto tiene un documento de Word adjunto, el documento de Word y el mensaje adjunto se van a indizar. Este comportamiento se seguirá para datos adjuntos anidados hasta 30.  <br/> |
|Número máximo de las imágenes adjuntas  <br/> |0  <br/> |Una imagen que se adjunta a un mensaje de correo electrónico es omitida por el analizador y no está indizada.  <br/> |
|Tiempo máximo invertido en un elemento de análisis  <br/> |30 segundos  <br/> |Un máximo de 30 segundos se invierta en un elemento para la indización de análisis. Si el tiempo del análisis es superior a 30 segundos, el elemento se marca como parcialmente indizados.  <br/> |
|Salida de analizador máximo  <br/> |2 millones de caracteres  <br/> |La cantidad máxima de salida de texto desde el analizador que se indiza. Por ejemplo, si el analizador extrajo 8 millones de caracteres de un documento, se indizan sólo los caracteres del primero 2 millones.  <br/> |
|Tokens de anotación máximo  <br/> |2 millones  <br/> |Cuando un mensaje de correo electrónico está indizado, cada palabra se anota con las instrucciones de procesamiento diferentes que especifican cómo se debe indizar esa palabra. Cada conjunto de instrucciones de procesamiento se denomina un token de anotación. Para mantener la calidad del servicio en Office 365, hay un límite de 2 millones de tokens de anotación para un mensaje de correo electrónico.  <br/> |
|Tamaño máximo de cuerpo en el índice  <br/> |67 millones de caracteres  <br/> |El número total de caracteres en el cuerpo de un mensaje de correo electrónico y todos sus datos adjuntos. Cuando no se indiza un mensaje de correo electrónico, todo el texto en el cuerpo del mensaje y en todos los datos adjuntos se concatena en una sola cadena. El tamaño máximo de esta cadena que se indiza es 67 millones de caracteres.  <br/> |
|Tokens de únicos máximos en cuerpo  <br/> |1 millón  <br/> |Explica como anteriormente, los tokens son el resultado de la extracción de texto de contenido, la eliminación signos de puntuación y espacios y, a continuación, se divide en palabras (denominadas tokens) que se almacenan en el índice. Por ejemplo, la frase `"cat, mouse, bird, dog, dog"` contiene los tokens de 5. Pero sólo 4 de estos tokens únicos. Hay un límite de 1 millón de tokens único por mensaje de correo electrónico, lo que ayuda a evitar que el índice de introducción demasiado grande con tokens de aleatorios.<br/> |
   

  
## <a name="more-information-about-partially-indexed-items"></a>Para obtener más información acerca de los elementos indizados parcialmente
<a name="moreinfo"> </a>

- Como se ha indicado anteriormente, debido a que el mensaje y propiedades de documentos y sus metadatos se indizan, una búsqueda de palabra clave puede devolver resultados si esa palabra clave aparece en los metadatos indizados. Sin embargo, es posible que esa misma búsqueda de palabra clave no devolver el mismo elemento si la palabra clave sólo aparece en el contenido de un elemento con un tipo de archivo no compatibles. En este caso, se devolverá el elemento como un elemento indizado parcialmente.
    
- Si un elemento indizado parcialmente se incluye en los resultados de búsqueda debido a que cumplen los criterios de consulta de búsqueda (y no se ha excluido) no se incluirán como un elemento indizado parcialmente en las estadísticas de búsqueda estimado. Además, no se incluirán con los elementos indizados parcialmente al exportar los resultados de búsqueda.
    
- Aunque un tipo de archivo se admite para la indización y está indizado, puede haber errores de búsqueda o indización que harán que un archivo que se devuelve como un elemento indizado parcialmente. Por ejemplo, buscar un archivo muy grande de Excel puede deberse a parcialmente correcto (se indizan el primer 4 MB), pero, a continuación, se produce un error porque se supera el límite de tamaño de archivo. En este caso, es posible que el mismo archivo se devuelve con los resultados de búsqueda y como un elemento indizado parcialmente.
    
- Archivos adjuntos que se cifran con las tecnologías de Microsoft se indizan y se pueden buscar. Los archivos cifrados con tecnologías de Microsoft que no sean parcialmente se indizan.
    
- Mensajes de correo electrónico cifrados con S/MIME parcialmente se indizan. Esto incluye los mensajes cifrados con o sin datos adjuntos de archivo.
    
- Los mensajes protegidos con Information Rights Management (IRM) se indexan y se incluyen en los resultados de la búsqueda si coinciden con la consulta de búsqueda.

## <a name="see-also"></a>Vea también

[Investigar elementos indizados parcialmente en eDiscovery de Office 365](investigating-partially-indexed-items-in-ediscovery.md)

