---
title: Elementos parcialmente indizados en la búsqueda de contenido en Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 5/11/2018
ms.audience: Admin
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.UnindexedItemsLearnMore
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- SPO160
- MOE150
- MET150
ms.assetid: d1691de4-ca0d-446f-a0d0-373a4fc8487b
description: 'Obtenga información sobre los elementos sin indexar en Exchange y SharePoint que puede incluir en una búsqueda de contenido ejecutada a través del centro de seguridad & cumplimiento. '
ms.openlocfilehash: da51788b3f017811756c3c07294bf6e2712e2e2c
ms.sourcegitcommit: e7a776a04ef6ed5e287a33cfdc36aa2d72862b55
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/29/2019
ms.locfileid: "30999223"
---
# <a name="partially-indexed-items-in-content-search-in-office-365"></a>Elementos parcialmente indizados en la búsqueda de contenido en Office 365

Una búsqueda de contenido que se ejecuta desde el centro de seguridad & cumplimiento en Office 365 automáticamente incluye elementos parcialmente indizados en los resultados de búsqueda estimados al ejecutar una búsqueda. Los elementos indexados parcialmente son elementos de buzones de Exchange y documentos de sitios de SharePoint y OneDrive para la empresa que, por algún motivo, no se han indizado completamente para la búsqueda. En Exchange, un elemento parcialmente indizado normalmente contiene un archivo, de un tipo de archivo que no se puede indizar, que está adjunto a un mensaje de correo electrónico. A continuación se muestran algunos otros motivos por los que los elementos no se pueden indizar para la búsqueda y se devuelven como elementos parcialmente indizados cuando se ejecuta una búsqueda: 
  
- El tipo de archivo no se reconoce o no se admite para la indización.
    
-  Los mensajes tienen un archivo adjunto sin un controlador válido, como archivos de imagen; Esta es la causa más común de los elementos de correo electrónico parcialmente indizados. 
    
- El tipo de archivo se admite para indización pero se produjo un error de indización en un archivo específico.
    
- Se han adjuntado demasiados archivos a un mensaje de correo electrónico.
    
- Un archivo adjuntado a un mensaje de correo electrónico es demasiado grande.
    
- Un archivo se ha cifrado con tecnologías que no son de Microsoft.
    
- Un archivo está protegido por contraseña.
    
> [!NOTE]
> La mayoría de las organizaciones de Office 365 tienen menos del 1% de contenido en volumen y menos del 12% en el tamaño que se indexa parcialmente. El motivo de la diferencia entre el volumen y el tamaño es que los archivos más grandes tienen una probabilidad mayor de contenido que no se puede indizar completamente. 
  
Para las investigaciones legales, es posible que sea necesario que su organización Revise los elementos indizados parcialmente. También puede especificar si desea incluir elementos parcialmente indizados al exportar los resultados de búsqueda a un equipo local o al preparar los resultados para el análisis con Office 365 Advanced eDiscovery. Para obtener más información, vea el artículo sobre cómo [investigar elementos indizados parcialmente en Office 365 eDiscovery](investigating-partially-indexed-items-in-ediscovery.md).
  
## <a name="file-types-not-indexed-for-search"></a>Tipos de archivo no indexados para búsquedas

Determinados tipos de archivos, como mapas de bits o MP3, no incluyen contenido que se pueda indexar. Como resultado, los servidores de indización de búsqueda de Exchange y SharePoint no realizan una indización de texto completo en estos tipos de archivos. Estos tipos de archivo se consideran como no admitidos. También hay tipos de archivos para los que se ha deshabilitado la indexación de texto completo, ya sea de manera predeterminada o por un administrador. Los tipos de archivo no admitidos y deshabilitados se etiquetan como elementos sin indexar en las búsquedas de contenido. Como se indicó anteriormente, los elementos parcialmente indizados se pueden incluir en el conjunto de resultados de la búsqueda cuando se ejecuta una búsqueda, se exportan los resultados de la búsqueda a un equipo local o se preparan los resultados de la búsqueda para eDiscovery avanzado. 
  
Para obtener una lista de formatos de archivo compatibles y deshabilitados, vea los temas siguientes:
  
- **** - [Formatos de archivo de Exchange indizados por la búsqueda de Exchange](https://go.microsoft.com/fwlink/p/?LinkID=386618)
    
- **Exchange** - [Get-SearchDocumentFormat](https://go.microsoft.com/fwlink/p/?LinkID=724037)
    
- **** - [Extensiones de nombre de archivo de rastreo y tipos de archivo analizados predeterminados de SharePoint en SharePoint](https://go.microsoft.com/fwlink/p/?LinkID=404033)
    

  
## <a name="messages-and-documents-with-partially-indexed-file-types-can-be-returned-in-search-results"></a>Los mensajes y documentos con tipos de archivo indexados parcialmente pueden devolverse en los resultados de la búsqueda

No todos los mensajes de correo electrónico con datos adjuntos de archivo parcialmente indizados o todos los documentos de SharePoint parcialmente indizados se devuelven automáticamente como un elemento parcialmente indizado. Esto se debe a que otras propiedades de los mensajes o documentos **** , como la propiedad Subject de los mensajes de correo electrónico y las propiedades **title** o **Author** de los documentos, se indizan y están disponibles para su búsqueda. Por ejemplo, una búsqueda de palabra clave "Financial" devolverá elementos con un archivo adjunto parcialmente indizado si esa palabra clave aparece en el asunto de un mensaje de correo electrónico o en el nombre de archivo o el título de un documento. Sin embargo, si la palabra clave aparece sólo en el cuerpo del archivo, el mensaje o el documento se devolverá como un elemento parcialmente indizado. 
  
De forma similar, los mensajes con datos adjuntos de archivo parcialmente indizados y documentos de un tipo de archivo parcialmente indizado se incluyen en los resultados de la búsqueda cuando otras propiedades de mensaje o documento, que se indizan y permiten buscar, cumplen con los criterios de búsqueda. Las propiedades de los mensajes que se indexan para la búsqueda son las fechas de envío y recepción, el remitente y el destinatario, el nombre de archivo de un adjunto, y el texto del cuerpo del mensaje. Las propiedades de los documentos que se indexan para la búsqueda son las fechas de creación y modificación. Por lo tanto, aunque los datos adjuntos de un mensaje puedan ser un elemento parcialmente indizado, el mensaje se incluirá en los resultados de la búsqueda normales si el valor de otras propiedades de mensaje o documento coincide con los criterios de búsqueda.
  
Para obtener una lista de las propiedades de correo electrónico y documentos que puede buscar mediante la característica de búsqueda en el centro de seguridad & cumplimiento, vea [consultas de palabras clave y condiciones de búsqueda para la búsqueda de contenido](keyword-queries-and-search-conditions.md).
  

  
## <a name="partially-indexed-items-included-in-the-search-results"></a>Elementos parcialmente indizados incluidos en los resultados de la búsqueda
<a name="unindexeditemsresults"> </a>

Es posible que su organización tenga que identificar y realizar análisis adicionales en elementos parcialmente indizados para determinar qué son, qué contienen y si son relevantes para una investigación específica. Como se ha explicado anteriormente, los elementos parcialmente indizados en las ubicaciones de contenido que se buscan se incluyen automáticamente con los resultados de búsqueda estimados. Tiene la opción de incluir estos elementos parcialmente indizados al exportar los resultados de la búsqueda o preparar los resultados de la búsqueda para la exhibición avanzada de documentos electrónicos. Para incluir elementos parcialmente indizados cuando exporte resultados de búsqueda o los prepara para la exhibición avanzada de documentos electrónicos, seleccione una de las opciones para incluir elementos que tienen un formato no reconocido, están cifrados o no se indizaron por otros motivos.
  
Tenga en cuenta lo siguiente sobre los elementos parcialmente indizados:
  
- Cuando se ejecuta una búsqueda de contenido, el número total y el tamaño de los elementos parcialmente indizados (devuelto por la consulta de búsqueda) se muestran en las estadísticas de búsqueda en el panel de detalles, con la etiqueta "elementos sin indexar".
    
- Cuando se exportan los resultados de la búsqueda y se incluyen los elementos parcialmente indizados, los elementos de Exchange indizados parcialmente se exportan a un archivo PST independiente para cada buzón en el que se encuentran, o como mensajes individuales si se selecciona la opción para descargar elementos de Exchange como mensaje. los elementos de SharePoint parcialmente indizados se exportan a una carpeta denominada no **rastreable**.
    
- Si la búsqueda desde la que está exportando resultados es una búsqueda de ubicaciones de contenido específicas o de todas las ubicaciones de contenido de su organización, solo se exportarán los elementos sin indexar de las ubicaciones de contenido que contienen elementos que coinciden con los criterios de búsqueda. In other words, if no search results are found in a mailbox or site, then any unindexed items in that mailbox or site won't be exported. El motivo es que exportar los elementos parcialmente indizados de muchos lugares de la organización puede aumentar la probabilidad de errores de exportación y aumentar el tiempo que se tarda en exportar y descargar los resultados de la búsqueda.
    
    Para exportar elementos parcialmente indizados de todas las ubicaciones de contenido de una búsqueda, configure la búsqueda para devolver todos los elementos (quitando las palabras clave de la consulta de búsqueda) y, a continuación, exporte solo los elementos parcialmente indizados al exportar los resultados de la búsqueda (haciendo clic **solo en los elementos que tienen un formato no reconocido, están cifrados o no se indizaron por otros motivos** en **las opciones de salida**).
    
- Si elige incluir todos los elementos del buzón de correo en los resultados de la búsqueda o si una consulta de búsqueda no especifica ninguna palabra clave o solo especifica un intervalo de fechas, es posible que no se copien los elementos parcialmente indizados en el archivo PST que contiene los elementos parcialmente indizados. Esto se debe a que todos los elementos, incluidos los elementos parcialmente indizados, se incluirán automáticamente en los resultados de la búsqueda normales.
    
- Los elementos indexados parcialmente no están disponibles para la vista previa. Tiene que exportar los resultados de la búsqueda para ver los elementos parcialmente indizados devueltos por la búsqueda.

## <a name="partially-indexed-items-excluded-from-the-search-results"></a>Elementos parcialmente indizados excluidos de los resultados de la búsqueda

Si un elemento está indizado parcialmente pero no cumple los criterios de la consulta de búsqueda, no se incluirá como elemento parcialmente indizado en los resultados de la búsqueda. En otras palabras, el elemento se excluye de los resultados de la búsqueda. Por ejemplo, supongamos que ejecuta una búsqueda y no incluye ninguna palabra clave o propiedad porque desea incluir todo el contenido. Sin embargo, incluye una condición de intervalo de fechas para la consulta. Si un elemento parcialmente indizado está fuera de ese intervalo de fechas, no se incluirá como elemento parcialmente indizado. Los intervalos de fechas son una manera eficaz de excluir los elementos parcialmente indizados de los resultados de la búsqueda.
  
De forma similar, si elige incluir elementos parcialmente indizados al exportar los resultados de una búsqueda, no se exportarán los elementos indexados parcialmente que se excluyeron de los resultados de la búsqueda.
  
Una excepción a esta regla es cuando se crea una retención basada en consulta asociada a un caso de exhibición de documentos electrónicos. Si crea una suspensión basada en consulta, todos los elementos parcialmente indizados se colocan en suspensión. Esto incluye los elementos parcialmente indizados que no coinciden con los criterios de la consulta de búsqueda y los elementos parcialmente indizados que podrían estar fuera de una condición de intervalo de fechas. Para obtener más información acerca de la creación de retenciones basadas en consultas, vea el paso 4 en [casos de eDiscovery](ediscovery-cases.md#step-4-place-content-locations-on-hold).
  
## <a name="indexing-limits-for-messages-in-content-search"></a>Límites de indización de mensajes en la búsqueda de contenido

En la tabla siguiente se describen los límites de indización que podrían dar como resultado la devolución de un mensaje de correo electrónico como elemento parcialmente indizado en una búsqueda de contenido en Office 365.
  
Para obtener una lista de los límites de indización de documentos de SharePoint, vea [límites de búsqueda para SharePoint Online](https://support.office.com/article/7c06e9ed-98b6-4304-a900-14773a8fa32f).
  
|**Límite de indización**|**Notas**|**Descripción**|
|:-----|:-----|:-----|
|Tamaño máximo de datos adjuntos (excepto los archivos de Excel)  <br/> |150 MB  <br/> |El tamaño máximo de datos adjuntos de correo electrónico que se analizarán para la indización. Los datos adjuntos que superen este límite no se analizarán para la indización y el mensaje con los datos adjuntos se marcará como parcialmente indizado.  <br/><br/> **Nota:** El análisis es el proceso en el que el servicio de indización extrae el texto de los datos adjuntos, quita los caracteres innecesarios, como la puntuación y los espacios, y divide el texto en palabras (en un proceso denominado "tokenización"), que se almacenan en el índice.           |
|Tamaño máximo de los archivos de Excel  <br/> |4 MB  <br/> |El tamaño máximo de un archivo de Excel ubicado en un sitio o adjunto a un mensaje de correo electrónico que se analizará para la indización. Los archivos de Excel que superen este límite no se analizarán y el archivo o el correo electrónico con los datos adjuntos del archivo se marcarán como no indizados.  <br/> |
|Número máximo de datos adjuntos  <br/> |250  <br/> |El número máximo de archivos adjuntos a un mensaje de correo electrónico que se analizará para la indización. Si un mensaje tiene más de 250 datos adjuntos, se analizan e indizan los primeros 250, y el mensaje se marca como parcialmente indizado porque tenía datos adjuntos adicionales que no se analizaron.  <br/> |
|Profundidad máxima de datos adjuntos  <br/> |semestre  <br/> |El número máximo de datos adjuntos anidados que se analizan. Por ejemplo, si un mensaje de correo electrónico tiene otro mensaje adjunto y el mensaje adjunto tiene un documento de Word adjunto, se indizará el documento de Word y el mensaje adjunto. Este comportamiento seguirá hasta 30 archivos adjuntos anidados.  <br/> |
|Número máximo de imágenes adjuntas  <br/> |comprendi  <br/> |El analizador omite una imagen que se adjunta a un mensaje de correo electrónico y no se indiza.  <br/> |
|Tiempo máximo empleado en el análisis de un elemento  <br/> |30 segundos  <br/> |Se dedica un máximo de 30 segundos a analizar un elemento para la indización. Si el tiempo de análisis supera los 30 segundos, el elemento se marca como parcialmente indizado.  <br/> |
|Salida máxima del analizador  <br/> |2 millones de caracteres  <br/> |La cantidad máxima de salida de texto del analizador que se indiza. Por ejemplo, si el analizador extrajo 8 millones caracteres de un documento, solo se indizarán los primeros 2 millones de caracteres.  <br/> |
|Tokens de anotación máximos  <br/> |2 millones  <br/> |Cuando se indiza un mensaje de correo electrónico, se anota cada palabra con diferentes instrucciones de procesamiento que especifican cómo debe indizarse esa palabra. Cada conjunto de instrucciones de procesamiento se denomina token de anotación. Para mantener la calidad de servicio en Office 365, hay un límite de 2 millones de tokens de anotación para un mensaje de correo electrónico.  <br/> |
|Tamaño máximo del cuerpo en el índice  <br/> |67 millones caracteres  <br/> |El número total de caracteres en el cuerpo de un mensaje de correo electrónico y todos sus datos adjuntos. Cuando se indiza un mensaje de correo electrónico, todo el texto del cuerpo del mensaje y en todos los datos adjuntos se concatena en una sola cadena. El tamaño máximo de esta cadena indizada es de 67 millones caracteres.  <br/> |
|Número máximo de tokens únicos en el cuerpo  <br/> |1 millón  <br/> |Como se ha explicado anteriormente, los tokens son el resultado de extraer texto del contenido, quitar los signos de puntuación y espacios y, a continuación, dividirlo en palabras (llamadas tokens) que se almacenan en el índice. Por ejemplo, la frase `"cat, mouse, bird, dog, dog"` contiene 5 tokens. Pero solo 4 son tokens únicos. Hay un límite de 1 millón tokens únicos por mensaje de correo electrónico, lo que ayuda a evitar que el índice sea demasiado grande con tokens aleatorios.  <br/> |
   

  
## <a name="more-information-about-partially-indexed-items"></a>Más información acerca de los elementos parcialmente indizados
<a name="moreinfo"> </a>

- Como se mencionó anteriormente, debido a que las propiedades Message y Document y sus metadatos se indizan, una búsqueda de palabra clave puede devolver resultados si la palabra clave aparece en los metadatos indizados. En cambio, la misma búsqueda de palabra clave podría no devolver el mismo elemento si la palabra clave solo aparece en el contenido de un elemento con un tipo de archivo no admitido. En este caso, el elemento se devolvería como un elemento parcialmente indizado.
    
- Si se incluye un elemento parcialmente indizado en los resultados de la búsqueda porque cumplía los criterios de la consulta de búsqueda (y no se concluyó), no se incluirá como elemento parcialmente indizado en las estadísticas de búsqueda estimadas. Además, no se incluirá con elementos parcialmente indizados cuando se exportan los resultados de la búsqueda.
    
- Aunque un tipo de archivo es compatible con la indización y se indiza, puede haber errores de búsqueda o indización que harán que un archivo se devuelva como un elemento parcialmente indizado. Por ejemplo, la búsqueda en un archivo de Excel de gran tamaño podría ser parcialmente correcta (porque los 4 primeros MB están indizados), pero se produce un error porque se superó el límite de tamaño del archivo. En este caso, es posible que se devuelva el mismo archivo con los resultados de la búsqueda y como elemento parcialmente indizado.
    
- Los archivos adjuntos cifrados con tecnologías de Microsoft se indexan y se pueden buscar. Los archivos cifrados con tecnologías que no son de Microsoft se indizan parcialmente.
    
- Los mensajes de correo electrónico cifrados con S/MIME están indizados parcialmente. Esto incluye los mensajes cifrados con o sin datos adjuntos.
    
- Los mensajes protegidos con Information Rights Management (IRM) se indexan y se incluyen en los resultados de la búsqueda si coinciden con la consulta de búsqueda.

## <a name="see-also"></a>Vea también

[Investigar elementos indizados parcialmente en eDiscovery de Office 365](investigating-partially-indexed-items-in-ediscovery.md)

