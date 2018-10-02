---
title: Límites de búsqueda de contenido en la seguridad de Office 365 &amp; centro de cumplimiento
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 4/30/2018
ms.audience: Admin
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 78fe3147-1979-4c41-83bb-aeccf244368d
description: 'Obtenga información acerca de los límites en vigor para la característica de búsqueda de contenido de la seguridad de Office 365 &amp; centro de cumplimiento, como el número máximo de búsquedas simultáneas. '
ms.openlocfilehash: 917351f380c81ebfabfd4b3ff05a534c65c8f318
ms.sourcegitcommit: b6473cd6ba3f9ac79dc6a2040fc148020dfbe464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/02/2018
ms.locfileid: "25358379"
---
# <a name="limits-for-content-search-in-the-office-365-security-amp-compliance-center"></a>Límites de búsqueda de contenido en la seguridad de Office 365 &amp; centro de cumplimiento

> [!NOTE]
> Los límites de este tema son diferentes de los límites actuales de exhibición de documentos electrónicos en contexto en Exchange Online y para el centro de exhibición de documentos electrónicos en SharePoint Online. 
  
Distintos límites se aplican a la característica de búsqueda de contenido de la seguridad de Office 365 &amp; centro de cumplimiento. Ejecutan este búsquedas de incluir en la página de **búsqueda de contenido** y las búsquedas que están asociadas con un caso de exhibición de documentos electrónicos. Estos límites ayudan a mantener la salud y la calidad de los servicios que proporciona a las organizaciones de Office 365. También hay algunos límites relacionados con la indización de mensajes de correo electrónico en Exchange Online para la búsqueda. No se puede modificar la búsqueda de contenido o los límites de la indización de correo electrónico, pero debe tener en cuenta de ellos para que estos límites se pueden tener en cuenta al planear, ejecución y solución de problemas de búsquedas de contenido. 
  
 **Contenido**
  
[Límites de búsqueda del contenido](limits-for-content-search.md#searchlimits)
  
[Límites de indización para mensajes de correo electrónico](limits-for-content-search.md#indexinglimits)
  
[Más información](limits-for-content-search.md#moreinfo)
  
## <a name="content-search-limits"></a>Límites de búsqueda del contenido
<a name="searchlimits"> </a>

En la siguiente tabla se enumera los límites de búsqueda en la seguridad &amp; centro de cumplimiento.
  
|**Descripción del límite**|**Límite**|
|:-----|:-----|
|El número máximo de buzones de correo o sitios que se pueden buscar en una sola búsqueda de contenido  <br/> |Sin límite  <br/> |
|El número máximo de búsquedas de contenido que se pueden ejecutar al mismo tiempo en su organización.  <br/> |Sin límite  <br/> |
|El número máximo de búsquedas de contenido que un único usuario puede iniciar al mismo tiempo. Tenga en cuenta que es muy probable que se alcanza este límite cuando el usuario intenta iniciar varias búsquedas mediante el uso de la **Get-ComplianceSearch \| ComplianceSearch de inicio** command en PowerShell de centro de cumplimiento y seguridad.<br/> |10    <br/> |
|El número máximo de elementos por buzón de usuario que se muestran en la página de vista previa durante la vista previa de los resultados de la búsqueda de contenido.  <br/> |100  <br/> |
|El número máximo de elementos que se encuentran en todos los buzones de usuario que se muestran en la página de vista previa durante la vista previa de los resultados de la búsqueda de contenido. Se muestran los elementos más recientes.  <br/> |1,000  <br/> |
|El número máximo de buzones de usuario que puede obtener una vista previa de los resultados de búsqueda. Si hay más de 1000 buzones de correo que contienen contenido que coincide con la consulta de búsqueda, sólo los principales 1000 buzones de correo con los resultados de búsqueda mayoría estará disponibles para la vista previa.  <br/> |1,000  <br/> |
|El número máximo de elementos que se encuentran en SharePoint y OneDrive para los sitios de negocio que se muestran en la página de vista previa durante la vista previa de los resultados de la búsqueda de contenido. Se muestran los elementos más recientes.  <br/> |200  <br/> |
|El número máximo de sitios (en SharePoint y OneDrive para la empresa) que se puede obtener una vista previa de los resultados de búsqueda. Si hay más de 200 sitios totales que incluyen contenido que coincide con la consulta de búsqueda, los sitios de 200 superiores con los resultados de búsqueda mayoría estará disponibles para la vista previa.  <br/> |200  <br/> |
|El número máximo de elementos por buzón de carpetas públicas que se muestran en la página de vista previa durante la vista previa de los resultados de la búsqueda de contenido.  <br/> |100  <br/> |
|El número máximo de elementos que se encuentran en todos los buzones de carpetas públicas que se muestran en la página de vista previa durante la vista previa de los resultados de la búsqueda de contenido.  <br/> |200  <br/> |
|El número máximo de buzones de correo públicas que puede obtener una vista previa de los resultados de búsqueda. Si hay más de 500 buzones de carpetas públicas que incluyen contenido que coincide con la consulta de búsqueda, sólo la superior 500 buzones de carpetas públicas con los resultados de búsqueda mayoría estará disponibles para la vista previa.  <br/> |500  <br/> |
|El número máximo de caracteres para la consulta de búsqueda (incluidos los operadores y condiciones) para una búsqueda de contenido.  <br/><br/> **Nota:** Este límite surte efecto después de que la consulta se expande, lo que significa que la consulta obtener expandirán frente a cada una de las palabras clave. Por ejemplo, si una consulta de búsqueda tiene 15 palabras clave y los parámetros adicionales y condiciones, la consulta se expande 15 veces, cada uno con los otros parámetros y condiciones de la consulta. Por lo tanto, aunque es posible que sea el número de caracteres en la consulta de búsqueda por debajo del límite, es la consulta expandida que puede contribuir a si se excede este límite.<br/> |**Buzones de correo:** 10.000  <br/> **Sitios:** 4.000 al buscar en todos los sitios o 2.000 al buscar en un máximo de 20 sitios <sup>1</sup> <br/> |
|Número máximo de variantes devuelto cuando se usa un carácter de prefijo comodín para buscar una frase exacta en una consulta de búsqueda o cuando se usa un carácter comodín de prefijo y el operador booleano **NEAR** u **ONEAR** .  <br/> |10.000 <sup>2</sup> <br/> |
|El número mínimo de caracteres alfabéticos para caracteres comodín de prefijo; Por ejemplo, `time*`, `one*`, o `set*`.  <br/> |3   <br/> |
|El número máximo de buzones de correo en una búsqueda de contenido que se pueden eliminar los elementos en realizando una acción de "búsqueda y purgar" (mediante el uso de la **New-ComplianceSearchAction-purgar** comando). Si la búsqueda de contenido que esté realizando una acción de purga para tiene más buzones de origen que este límite, se producirá un error en la acción de purga. Para obtener más información acerca de la búsqueda y purgar, vea [Buscar y eliminar mensajes de correo electrónico en la organización de Office 365](search-for-and-delete-messages-in-your-organization.md).<br/> |50.000  <br/> |
   
> [!NOTE]
> <sup>1</sup> al buscar en SharePoint y OneDrive para las ubicaciones de negocio, se cuentan los caracteres en las direcciones URL de los sitios que se buscan respecto a este límite.<br/> <sup>2</sup> para consultas que no sean frase (un valor de palabra clave que no utilice las comillas dobles) usaremos un índice de prefijo especial. Nos dice que se produce una palabra en un documento, pero no donde se produce en el documento. Para hacer una consulta de frases (un valor de palabra clave con comillas dobles), necesitamos comparar la posición dentro del documento para las palabras de la frase. Esto significa que no podemos utilizar el índice de prefijo para consultas de frases. En este caso, se expanda internamente la consulta con todas las palabras posibles que se expande el prefijo a; Por ejemplo, `"time*"` puede expandir a `"time OR timer OR times OR timex OR timeboxed OR …"`. 10.000 es el número máximo de variantes de que la palabra puede expandir a, no el número de documentos que coinciden con la consulta. No hay ningún límite superior para los términos que no sean frase. 
  
[Return to top](limits-for-content-search.md#top)
  
## <a name="indexing-limits-for-email-messages"></a>Límites de indización para mensajes de correo electrónico
<a name="indexinglimits"> </a>

En la siguiente tabla se describe los límites de indización que podrían dar como resultado un mensaje de correo electrónico que se devuelven como un elemento no indizado o un elemento indizado parcialmente en los resultados de una búsqueda de contenido.
  
|**Límite de indización**|**Notas**|**Descripción**|
|:-----|:-----|:-----|
|Tamaño máximo de datos adjuntos (excluyendo los archivos de Excel)  <br/> |150 MB  <br/> |El tamaño máximo de datos adjuntos de correo electrónico que se va a analizar para la indización. No se puede analizar los datos adjuntos que es mayor que este límite para la indización y el mensaje con los datos adjuntos se marcarán como parcialmente indizados.<br/> <br/>**Nota:** Análisis es el proceso donde el servicio de Index Server extrae el texto de los datos adjuntos, quita los caracteres innecesarios como signos de puntuación y espacios y, a continuación, divide el texto en palabras (en un proceso denominado tokenización), que, a continuación, se almacenan en el índice.           |
|Tamaño máximo de archivos de Excel  <br/> |4 MB  <br/> |El tamaño máximo de un archivo de Excel ubicada en un sitio o adjunto a un mensaje de correo electrónico que se va a analizar para la indización. Cualquier archivo de Excel que es mayor que este límite no se puede analizar y el archivo o el correo electrónico que el mensaje con el archivo adjunto se marcarán como no indexados.  <br/> |
|Número máximo de datos adjuntos  <br/> |250  <br/> |El número máximo de archivos adjuntado a un mensaje de correo electrónico que se va a analizar para la indización. Si un mensaje tiene más de 250 datos adjuntos, se analizan y se indizan el primero 250 datos adjuntos, y el mensaje está marcado como parcialmente indizados porque tenía datos adjuntos adicionales que no se han analizado.  <br/> |
|Profundidad de máximo de datos adjuntos  <br/> |30  <br/> |El número máximo de datos adjuntos anidados que se analizan. Por ejemplo, si un mensaje de correo electrónico tiene otro mensaje adjunto y el mensaje adjunto tiene un documento de Word adjunto, el documento de Word y el mensaje adjunto se van a indizar. Este comportamiento se seguirá para datos adjuntos anidados hasta 30.  <br/> |
|Número máximo de las imágenes adjuntas  <br/> |0  <br/> |Una imagen que se adjunta a un mensaje de correo electrónico es omitida por el analizador y no está indizada.  <br/> |
|Tiempo máximo invertido en un elemento de análisis  <br/> |30 segundos  <br/> |Un máximo de 30 segundos se invierta en un elemento para la indización de análisis. Si el tiempo del análisis es superior a 30 segundos, el elemento se marca como parcialmente indizados.  <br/> |
|Salida de analizador máximo  <br/> |2 millones de caracteres  <br/> |La cantidad máxima de salida de texto desde el analizador que se indiza. Por ejemplo, si el analizador extrajo 8 millones de caracteres de un documento, se indizan sólo los caracteres del primero 2 millones.  <br/> |
|Tokens de anotación máximo  <br/> |2 millones  <br/> |Cuando un mensaje de correo electrónico está indizado, cada palabra se anota con las instrucciones de procesamiento diferentes que especifican cómo se debe indizar esa palabra. Cada conjunto de instrucciones de procesamiento se denomina un token de anotación. Para mantener la calidad del servicio en Office 365, hay un límite de 2 millones de tokens de anotación para un mensaje de correo electrónico.  <br/> |
|Tamaño máximo de cuerpo en el índice  <br/> |67 millones de caracteres  <br/> |El número total de caracteres en el cuerpo de un mensaje de correo electrónico y todos sus datos adjuntos. Cuando no se indiza un mensaje de correo electrónico, todo el texto en el cuerpo del mensaje y en todos los datos adjuntos se concatena en una sola cadena. El tamaño máximo de esta cadena que se indiza es 67 millones de caracteres.  <br/> |
|Tokens de únicos máximos en cuerpo  <br/> |1 millón  <br/> |Explica como anteriormente, los tokens son el resultado de la extracción de texto de contenido, la eliminación signos de puntuación y espacios y, a continuación, se divide en palabras (denominadas tokens) que se almacenan en el índice. Por ejemplo, la frase `"cat, mouse, bird, dog, dog"` contiene los tokens de 5. Pero sólo 4 de estos tokens únicos. Hay un límite de 1 millón de tokens único por mensaje de correo electrónico, lo que ayuda a evitar que el índice de introducción demasiado grande con tokens de aleatorios.<br/> |
   
[Return to top](limits-for-content-search.md#top)
  
## <a name="more-information"></a>Más información
<a name="moreinfo"> </a>

Hay aspectos relacionados a diferentes de límites adicionales de la búsqueda de contenido, como exportar los resultados de búsqueda e indización de contenido. Para obtener una descripción de estos límites, vea los temas siguientes:
  
- 
    
- [Elementos parcialmente indizados en la búsqueda de contenido en Office 365](partially-indexed-items-in-content-search.md)
    
- [Investigar elementos indizados parcialmente en eDiscovery de Office 365](investigating-partially-indexed-items-in-ediscovery.md)
    
- [Límites de búsqueda de SharePoint Online](https://support.office.com/article/7c06e9ed-98b6-4304-a900-14773a8fa32f)
    
Para obtener información acerca de las búsquedas de contenido, vea:
  
- [Búsqueda de contenido en Office 365](content-search.md)
    
- [Consultas de palabras clave y condiciones de búsqueda para la búsqueda de contenido](keyword-queries-and-search-conditions.md).
    
[Return to top](limits-for-content-search.md#top)
  

