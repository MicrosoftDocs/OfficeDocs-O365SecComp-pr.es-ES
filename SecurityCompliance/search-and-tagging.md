---
title: Búsqueda y etiquetado
ms.author: chrfox
author: chrfox
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 22f5adad-1bc0-460d-94a9-8732929f5b99
description: En eDiscovery avanzado, el módulo de búsqueda y etiquetado le permite buscar, obtener una vista previa y organizar los documentos en su caso. Actualmente, este módulo está en versión beta.
ms.openlocfilehash: 58913a01f30b4169470592f5fc271e3ce785ac5d
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32261378"
---
# <a name="search-and-tagging"></a>Búsqueda y etiquetado

En eDiscovery avanzado, el módulo de búsqueda y etiquetado le permite buscar, obtener una vista previa y organizar los documentos en su caso. Actualmente, este módulo está en versión beta. Para obtener una breve demostración de la búsqueda y el etiquetado, vea el vídeo sobre cómo [administrar los datos con la exhibición avanzada](https://www.youtube.com/watch?v=VaPYL3DHP6I) de documentos electrónicos.

> [!NOTE]
> Para usar eDiscovery avanzado, su organización necesita una suscripción de Office 365 E3 con el complemento Cumplimiento avanzado, o bien una suscripción de E5. Si no tiene ese plan y quiere probar eDiscovery avanzado, puede [registrarse para una prueba de Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279). 
  
## <a name="search-the-documents-in-your-case"></a>Buscar en los documentos de su caso

Una vez que haya procesado los documentos en un caso de exhibición avanzada de documentos electrónicos (y, opcionalmente, pueda ejecutar el módulo Analyze o relevancia), puede usar la búsqueda y el etiquetado para buscar documentos y, a continuación, organizarlos mediante la aplicación de etiquetas específicas para casos (también denominadas etiquetas). Puede definir una consulta de búsqueda con las tarjetas de condición proporcionadas o con un lenguaje de consulta de tipo KQL en la tarjeta de condición de palabras clave. Se admite la sintaxis de KQL común, como AND, OR, NOT y NEAR (n), así como comodín de varios caracteres al final (*). 

En la siguiente tabla se enumeran las propiedades que se pueden buscar con una consulta de palabras clave KQL. Como alternativa, puede usar una tarjeta de condición de en la herramienta de búsqueda de eDiscovery avanzada para agregar una condición (para las propiedades seleccionadas) a una consulta de búsqueda.

|**Propiedad**|**Descripción**|
|:-----|:-----|
|**caselabel** <br/> | Nombre de la etiqueta creada o aplicada cuando se etiqueta un documento. <br/> |
|**custodio** <br/> | El custodio asociado a un documento; sujeta a limitaciones. <br/> |
|**date** <br/> | Fecha de envío del correo electrónico; fecha de modificación de los documentos del sitio. <br/> |
|**ID** <br/> | IDENTIFICADOR de archivo dentro del caso. <br/> |
|**filetype** <br/> | La extensión de archivo nativa. <br/> |
|**fileclass** <br/> | Correo electrónico, documento o datos adjuntos. <br/> |
|**senderauthor** <br/> | El remitente del correo electrónico; el autor de los documentos del sitio. <br/> |
|**size** <br/> | El tamaño del archivo en KB. <br/> |
|**subjecttitle** <br/> | El asunto del correo electrónico; el título de los documentos del sitio. <br/> |
|**bcc** <br/> | El campo CCO de un correo electrónico. <br/> |
|**cc** <br/> | El campo CC de un correo electrónico. <br/> |
|**participants** <br/> | La dirección de correo electrónico de todos los participantes en una conversación de correo electrónico, incluidos los vínculos que faltan. <br/> |
|**received** <br/> | La fecha en que se recibió un correo electrónico. <br/> |
|**recipients** <br/> | Destinatarios de un correo electrónico, incluidos en los campos para, CC o CCO. <br/> |
|**sender** <br/> | El remitente de un correo electrónico. <br/> |
|**LastModifiedDate** <br/> | Fecha de la última modificación de un documento del sitio. <br/> |
|**sent** <br/> | Fecha de envío de un correo electrónico. <br/> |
|**to** <br/> | El destinatario que aparece en el campo para de un correo electrónico. <br/> |
|**crea** <br/> | El autor de un documento de sitio. <br/> |
|**title** <br/> | El título de un documento de sitio. <br/> |
|**dominanttheme**\* <br/> | El tema dominante de un elemento. <br/> |
|**themeslist**\* <br/> | Temas asociados a un elemento. <br/> |
|**readpercentile_ [issuenum]**\*\* <br/> | El percentil de lectura de un elemento, para el problema definido por [issuenum]. <br/> |
|**relevancescore_ [issuenum]**\*\* <br/> | La puntuación de relevancia de un elemento para el problema definido por [issuenum]. <br/> |
|**relevancetag_ [tagName]**\*\* <br/> | Si un elemento se ha etiquetado manualmente para la relevancia, la etiqueta definida por [tagName]. <br/> |
|||

\*Solo está disponible si se ha ejecutado el módulo de temas.

\*\*Solo está disponible si se ha ejecutado el módulo de relevancia.

Como alternativa, puede usar una tarjeta de condición en la herramienta de búsqueda de eDiscovery avanzada para agregar una condición (para las propiedades seleccionadas) a una consulta de búsqueda. En la siguiente captura de pantalla se muestran las condiciones que se pueden agregar a una consulta. La columna **Grupo** indica si la propiedad se aplica al correo electrónico, a los documentos del sitio o a ambos (indicado por el valor *Common*). Esta columna también identifica las propiedades que se pueden buscar y que están disponibles después de ejecutar el módulo relevancia.

![Condiciones de búsqueda en la herramienta de búsqueda avanzada de eDiscovery](media/AeDSearchConditions.png)

Para obtener más información acerca de las propiedades que permiten búsquedas, consulte [Keyword queries and search conditions](keyword-queries-and-search-conditions.md).
  
## <a name="see-also"></a>Vea también

[eDiscovery avanzado de Office 365](office-365-advanced-ediscovery.md)
  
[Descripción de la evaluación en relevancia](assessment-in-relevance-in-advanced-ediscovery.md)
  
[Etiquetado y evaluación](tagging-and-assessment-in-advanced-ediscovery.md)
  
[Aprendizaje de etiquetas y relevancia](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[Seguimiento del análisis de relevancia](track-relevance-analysis-in-advanced-ediscovery.md)
  
[Decisiones basadas en los resultados](decision-based-on-the-results-in-advanced-ediscovery.md)
  
[Prueba del análisis de relevancia](test-relevance-analysis-in-advanced-ediscovery.md)

