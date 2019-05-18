---
title: Límites de búsqueda de contenido en el centro de seguridad & cumplimiento
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 78fe3147-1979-4c41-83bb-aeccf244368d
description: 'Obtenga información sobre los límites en vigor para la característica de búsqueda de contenido en el centro de seguridad & cumplimiento en Office 365, como el número máximo de búsquedas simultáneas. '
ms.openlocfilehash: 6933fcb2a7b54c3617b2c01d54fa50fa4955ead2
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/17/2019
ms.locfileid: "34155912"
---
# <a name="limits-for-content-search-in-the-security--compliance-center"></a>Límites de búsqueda de contenido en el centro de seguridad & cumplimiento

> [!NOTE]
> Los límites de este tema son distintos de los límites actuales para la exhibición de documentos electrónicos local en Exchange Online y para el centro de exhibición de documentos electrónicos en SharePoint Online. 
  
Se aplican varios límites a la característica de búsqueda de contenido en el centro de seguridad & cumplimiento. Esto incluye búsquedas que se ejecutan en la página de **búsqueda de contenido** y búsquedas asociadas a un caso de exhibición de documentos electrónicos. Estos límites ayudan a conservar el mantenimiento y la calidad de los servicios proporcionados a organizaciones de Office 365. También hay límites relacionados con la indización de mensajes de correo electrónico en Exchange Online para la búsqueda. No puede modificar los límites de indexación de contenido o de correo electrónico, pero debe conocerlos para que pueda tener en cuenta estos límites al planear, ejecutar y solucionar los problemas de las búsquedas de contenido. 
  
## <a name="content-search-limits"></a>Límites de búsqueda de contenido

En la siguiente tabla se enumeran los límites de búsqueda en el centro de seguridad & cumplimiento.
  
|**Descripción del límite**|**Límite**|
|:-----|:-----|
|El número máximo de buzones o sitios en los que se puede buscar en una sola búsqueda de contenido  <br/> |Sin límite  <br/> |
|El número máximo de búsquedas de contenido que se pueden ejecutar al mismo tiempo en la organización.  <br/> |Sin límite  <br/> |
|El número máximo de búsquedas de contenido que un solo usuario puede iniciar al mismo tiempo. Tenga en cuenta que es muy probable que este límite se alcance cuando el usuario intenta iniciar varias búsquedas mediante el comando **Get-compliancesearch \| Start-Compliancesearch** en Security & Compliance Center PowerShell.  <br/> |10   <br/> |
|El número máximo de elementos por buzón de usuario que se muestran en la página de vista previa al previsualizar los resultados de la búsqueda de contenido.  <br/> |100  <br/> |
|El número máximo de elementos encontrados en todos los buzones de usuario que se muestran en la página de vista previa al previsualizar los resultados de la búsqueda de contenido. Se muestran los elementos más recientes.  <br/> |1,000  <br/> |
|El número máximo de buzones de usuario de los que se puede obtener una vista previa de los resultados de búsqueda. Si hay más de 1000 buzones que contienen contenido que coincide con la consulta de búsqueda, solo estarán disponibles los primeros 1000 buzones con la mayoría de resultados de búsqueda para la vista previa.  <br/> |1,000  <br/> |
|El número máximo de elementos encontrados en los sitios de SharePoint y OneDrive para la empresa que se muestran en la página de vista previa al previsualizar los resultados de la búsqueda de contenido. Se muestran los elementos más recientes.  <br/> |200  <br/> |
|El número máximo de sitios (en SharePoint y OneDrive para la empresa) en los que se puede obtener una vista previa de los resultados de búsqueda. Si hay más de 200 sitios en total que tienen contenido que coincide con la consulta de búsqueda, solo los principales sitios de 200 con mayor cantidad de resultados de búsqueda estarán disponibles para la vista previa.  <br/> |200  <br/> |
|El número máximo de elementos por buzón de carpetas públicas que se muestran en la página de vista previa al previsualizar los resultados de la búsqueda de contenido.  <br/> |100  <br/> |
|El número máximo de elementos encontrados en todos los buzones de carpetas públicas que se muestran en la página de vista previa al previsualizar los resultados de la búsqueda de contenido.  <br/> |200  <br/> |
|El número máximo de buzones públicos en los que se puede obtener una vista previa de los resultados de búsqueda. Si hay más de 500 buzones de carpetas públicas que contienen contenido que coincide con la consulta de búsqueda, solo los primeros 500 buzones de carpetas públicas con mayor cantidad de resultados de búsqueda estarán disponibles para la vista previa.  <br/> |500  <br/> |
|El número máximo de caracteres de la consulta de búsqueda (incluidos los operadores y las condiciones) de una búsqueda de contenido.  <br/><br/> **Nota:** Este límite surte efecto después de que se expande la consulta, lo que significa que la consulta se expandirá en cada una de las palabras clave. Por ejemplo, si una consulta de búsqueda tiene 15 palabras clave y otros parámetros y condiciones, la consulta se expande 15 veces, cada una con los demás parámetros y condiciones de la consulta. Por lo tanto, aunque el número de caracteres en la consulta de búsqueda puede estar por debajo del límite, es la consulta ampliada que puede contribuir a exceder este límite.  <br/> |**Buzones de correo:** 10.000  <br/> **Sitios:** 4.000 al buscar en todos los sitios o en 2.000 al buscar hasta 20 sitios <sup>1</sup> <br/> |
|Número máximo de variantes devueltas al usar un carácter comodín de prefijo para buscar una frase exacta en una consulta de búsqueda o cuando se usa un carácter comodín de prefijo y el operador booleano **Near** o **ONEAR** .  <br/> |10.000 <sup>2</sup> <br/> |
|El número mínimo de caracteres alfabéticos para los caracteres comodín de prefijo; por ejemplo, `time*` `one*`, o `set*`.  <br/> |3  <br/> |
|El número máximo de buzones en una búsqueda de contenido en la que se pueden eliminar elementos mediante una acción "buscar y purgar" (mediante el comando **New-ComplianceSearchAction-Purge** ). Si la búsqueda de contenido en la que está realizando una acción de purga tiene más buzones de origen que este límite, se producirá un error en la acción de purga. Para obtener más información acerca de las búsquedas y depuración, consulte [Buscar y eliminar mensajes de correo electrónico en su organización de Office 365](search-for-and-delete-messages-in-your-organization.md).  <br/> |50.000  <br/> |
   
> [!NOTE]
> <sup>1</sup> al buscar ubicaciones de SharePoint y OneDrive para la empresa, los caracteres de las direcciones URL de los sitios en los que se busca se cuentan en este límite. <br/> <sup>2</sup> para las consultas que no son de frases (un valor de palabra clave que no usa comillas dobles) usamos un índice de prefijo especial. Esto indica que se produce una palabra en un documento, pero no donde se produce en el documento. Para realizar una consulta de frases (un valor de palabra clave con comillas dobles), debemos comparar la posición del documento con las palabras de la frase. Esto significa que no podemos usar el índice de prefijos para las consultas de frases. En este caso, la consulta se expande internamente con todas las palabras posibles a las que se expande el prefijo; por ejemplo, `"time*"` se puede expandir `"time OR timer OR times OR timex OR timeboxed OR …"`a. 10.000 es el número máximo de variantes a las que se puede expandir la palabra, no el número de documentos que coinciden con la consulta. Para los términos que no son frases no hay ningún límite superior. 
  
## <a name="indexing-limits-for-email-messages"></a>Límites de indización de los mensajes de correo electrónico

En la tabla siguiente se describen los límites de indización que podrían dar como resultado la devolución de un mensaje de correo electrónico como un elemento no indizado o un elemento parcialmente indizado en los resultados de una búsqueda de contenido.
  
|**Límite de indización**|**Notas**|**Descripción**|
|:-----|:-----|:-----|
|Tamaño máximo de datos adjuntos (excepto los archivos de Excel)  <br/> |150 MB  <br/> |El tamaño máximo de datos adjuntos de correo electrónico que se analizarán para la indización. Los datos adjuntos que superen este límite no se analizarán para la indización y el mensaje con los datos adjuntos se marcará como parcialmente indizado.  <br/> <br/>**Nota:** El análisis es el proceso en el que el servicio de indización extrae el texto de los datos adjuntos, quita los caracteres innecesarios, como la puntuación y los espacios, y divide el texto en palabras (en un proceso denominado "tokenización"), que se almacenan en el índice.           |
|Tamaño máximo de los archivos de Excel  <br/> |4 MB  <br/> |El tamaño máximo de un archivo de Excel ubicado en un sitio o adjunto a un mensaje de correo electrónico que se analizará para la indización. Los archivos de Excel que superen este límite no se analizarán y el archivo o el correo electrónico con los datos adjuntos del archivo se marcarán como no indizados.  <br/> |
|Número máximo de datos adjuntos  <br/> |250  <br/> |El número máximo de archivos adjuntos a un mensaje de correo electrónico que se analizará para la indización. Si un mensaje tiene más de 250 datos adjuntos, se analizan e indizan los primeros 250, y el mensaje se marca como parcialmente indizado porque tenía datos adjuntos adicionales que no se analizaron.  <br/> |
|Profundidad máxima de datos adjuntos  <br/> |semestre  <br/> |El número máximo de datos adjuntos anidados que se analizan. Por ejemplo, si un mensaje de correo electrónico tiene otro mensaje adjunto y el mensaje adjunto tiene un documento de Word adjunto, se indizará el documento de Word y el mensaje adjunto. Este comportamiento seguirá hasta 30 archivos adjuntos anidados.  <br/> |
|Número máximo de imágenes adjuntas  <br/> |comprendi  <br/> |El analizador omite una imagen que se adjunta a un mensaje de correo electrónico y no se indiza.  <br/> |
|Tiempo máximo empleado en el análisis de un elemento  <br/> |30 segundos  <br/> |Se dedica un máximo de 30 segundos a analizar un elemento para la indización. Si el tiempo de análisis supera los 30 segundos, el elemento se marca como parcialmente indizado.  <br/> |
|Salida máxima del analizador  <br/> |2 millones de caracteres  <br/> |La cantidad máxima de salida de texto del analizador que se indiza. Por ejemplo, si el analizador extrajo 8 millones caracteres de un documento, solo se indizarán los primeros 2 millones de caracteres.  <br/> |
|Tokens de anotación máximos  <br/> |2 millones  <br/> |Cuando se indiza un mensaje de correo electrónico, se anota cada palabra con diferentes instrucciones de procesamiento que especifican cómo debe indizarse esa palabra. Cada conjunto de instrucciones de procesamiento se denomina token de anotación. Para mantener la calidad de servicio en Office 365, hay un límite de 2 millones de tokens de anotación para un mensaje de correo electrónico.  <br/> |
|Tamaño máximo del cuerpo en el índice  <br/> |67 millones caracteres  <br/> |El número total de caracteres en el cuerpo de un mensaje de correo electrónico y todos sus datos adjuntos. Cuando se indiza un mensaje de correo electrónico, todo el texto del cuerpo del mensaje y en todos los datos adjuntos se concatena en una sola cadena. El tamaño máximo de esta cadena indizada es de 67 millones caracteres.  <br/> |
|Número máximo de tokens únicos en el cuerpo  <br/> |1 millón  <br/> |Como se ha explicado anteriormente, los tokens son el resultado de extraer texto del contenido, quitar los signos de puntuación y espacios y, a continuación, dividirlo en palabras (llamadas tokens) que se almacenan en el índice. Por ejemplo, la frase `"cat, mouse, bird, dog, dog"` contiene 5 tokens. Pero solo 4 son tokens únicos. Hay un límite de 1 millón tokens únicos por mensaje de correo electrónico, lo que ayuda a evitar que el índice sea demasiado grande con tokens aleatorios.  <br/> |
  
## <a name="more-information"></a>Más información

Existen límites adicionales relacionados con los distintos aspectos de la búsqueda de contenido, como la exportación de resultados de búsqueda y la indización de contenido. Para obtener una descripción de estos límites, vea los siguientes temas:
  
- [Exportar resultados de la búsqueda de contenido](export-search-results.md#export-limits)
    
- [Elementos parcialmente indizados en la búsqueda de contenido en Office 365](partially-indexed-items-in-content-search.md)
    
- [Investigar elementos indizados parcialmente en eDiscovery de Office 365](investigating-partially-indexed-items-in-ediscovery.md)
    
- [Límites de búsqueda para SharePoint Online](https://support.office.com/article/7c06e9ed-98b6-4304-a900-14773a8fa32f)
    
Para obtener más información acerca de las búsquedas de contenido, consulte:
  
- [Búsqueda de contenido en Office 365](content-search.md)
    
- [Consultas de palabras clave y condiciones de búsqueda para la búsqueda de contenido](keyword-queries-and-search-conditions.md).
