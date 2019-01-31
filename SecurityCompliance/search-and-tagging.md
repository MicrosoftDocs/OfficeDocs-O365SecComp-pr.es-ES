---
title: Búsqueda y etiquetado
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 22f5adad-1bc0-460d-94a9-8732929f5b99
description: En la exhibición de documentos electrónicos avanzada, el módulo de búsqueda y etiquetado permite buscar, obtener una vista previa y organizar los documentos en su caso. Actualmente, en este módulo se encuentra en versión beta.
ms.openlocfilehash: 013e559ca55e9a877dfb2f8747c4696f81e1e095
ms.sourcegitcommit: 25f1028643d8a20d17306e8b09cafea46eaf7a58
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/31/2019
ms.locfileid: "29666150"
---
# <a name="search-and-tagging"></a>Búsqueda y etiquetado

En la exhibición de documentos electrónicos avanzada, el módulo de búsqueda y etiquetado permite buscar, obtener una vista previa y organizar los documentos en su caso. Actualmente, en este módulo se encuentra en versión beta. Para obtener una demostración breve de búsqueda y etiquetado, vea el vídeo de [administrar los datos con avanzadas exhibición de documentos electrónicos](https://www.youtube.com/watch?v=VaPYL3DHP6I) .

> [!NOTE]
> Para usar eDiscovery avanzado, su organización necesita una suscripción de Office 365 E3 con el complemento Cumplimiento avanzado, o bien una suscripción de E5. Si no tiene ese plan y quiere probar eDiscovery avanzado, puede [registrarse para una prueba de Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279). 
  
## <a name="search-the-documents-in-your-case"></a>Buscar los documentos en su caso

Después de haber procesa documentos en un caso de exhibición de documentos electrónicos avanzada (y, opcionalmente, ejecute el módulo analizar o relevancia), puede usar la búsqueda y etiquetado para buscar documentos y, a continuación, organizarlos mediante la aplicación de etiquetas de caso específico (también denominadas etiquetas). Puede definir una consulta de búsqueda con las tarjetas de condición proporcionada o mediante el uso de un lenguaje de consulta de palabras clave similares en las palabras clave condición tarjeta. Sintaxis de palabras clave comunes, como AND, OR, NOT y NEAR(n) son compatible, así como final comodín de varios caracteres (*). 

En la siguiente tabla se enumera las propiedades que se pueden buscar para el uso de una consulta de palabra clave palabras clave. Como alternativa, puede usar una tarjeta de condición para en la herramienta de búsqueda de exhibición de documentos avanzada para agregar una condición (para las propiedades seleccionadas) a una consulta de búsqueda.

|**Propiedad**|**Descripción**|
|:-----|:-----|
|**caselabel** <br/> | El nombre de la etiqueta que se creó o aplicar cuando un documento está etiquetado. <br/> |
|**custodia** <br/> | La custodia asociada a un documento. sujeto a las limitaciones. <br/> |
|**fecha** <br/> | Enviado fecha para el correo electrónico; la fecha de modificación de documentos del sitio. <br/> |
|**FileID** <br/> | El identificador de archivo dentro de las mayúsculas y minúsculas. <br/> |
|**FileType** <br/> | La extensión de archivo nativo. <br/> |
|**fileclass** <br/> | Correo electrónico, documentos o datos adjuntos. <br/> |
|**senderauthor** <br/> | El remitente de correo electrónico; el autor de documentos del sitio. <br/> |
|**tamaño** <br/> | El tamaño del archivo en KB. <br/> |
|**asunto** <br/> | El asunto del correo electrónico; el título de documentos del sitio. <br/> |
|**cco** <br/> | El campo CCO de un correo electrónico. <br/> |
|**cc** <br/> | El campo Cc de un correo electrónico. <br/> |
|**participantes** <br/> | La dirección de correo electrónico de todos los participantes en un subproceso de correo electrónico, incluidos para faltan vínculos. <br/> |
|**recibido** <br/> | La fecha en que se ha recibido un correo electrónico. <br/> |
|**destinatarios** <br/> | Destinatarios de un correo electrónico, incluidos en para, Cc o CCO campos. <br/> |
|**remitente** <br/> | El remitente de un correo electrónico. <br/> |
|**LastModifiedDate** <br/> | La última fecha de un documento del sitio de la modificación. <br/> |
|**enviado** <br/> | La fecha de envío de un correo electrónico. <br/> |
|**Para** <br/> | Los destinatarios que aparecen en el campo para de un correo electrónico. <br/> |
|**autor** <br/> | El autor de un documento del sitio. <br/> |
|**title** <br/> | El título de un documento del sitio. <br/> |
|**dominanttheme**\* <br/> | El tema dominante de un elemento. <br/> |
|**themeslist**\* <br/> | Temas que se asocian con un elemento. <br/> |
|**readpercentile_ [issuenum]**\*\* <br/> | El percentil de lectura de un elemento, para el problema definido por [issuenum]. <br/> |
|**relevancescore_ [issuenum]**\*\* <br/> | La puntuación de relevancia de un elemento, para el problema definido por [issuenum]. <br/> |
|**relevancetag_ [tagname]**\*\* <br/> | Si tiene un elemento se ha etiquetado manualmente para la relevancia, la etiqueta definida por [tagname]. <br/> |
|||

\*Sólo está disponible si se ha ejecutado el módulo de temas.

\*\*Sólo está disponible si se ha ejecutado el módulo de la relevancia.

Como alternativa, puede usar una tarjeta de condición en la herramienta de búsqueda de exhibición de documentos avanzada para agregar una condición (para las propiedades seleccionadas) a una consulta de búsqueda. La captura de pantalla siguiente muestra las condiciones que se pueden agregar a una consulta. La columna **grupo** indica si la propiedad se aplica al correo electrónico, documentos del sitio o ambos (indicada por el valor *común*). Esta columna identifica las propiedades que admite búsquedas que están disponibles después de ejecutar el módulo de la relevancia.

![Condiciones de búsqueda en la herramienta de búsqueda de exhibición de documentos electrónicos avanzadas](media/AeDSearchConditions.png)

Para obtener más información acerca de las propiedades que admite búsquedas, vea [consultas de palabra clave y las condiciones de búsqueda](keyword-queries-and-search-conditions.md).
  
## <a name="see-also"></a>Vea también

[eDiscovery avanzado de Office 365](office-365-advanced-ediscovery.md)
  
[Evaluación de descripción en la relevancia](assessment-in-relevance-in-advanced-ediscovery.md)
  
[Etiquetas temáticas y evaluación](tagging-and-assessment-in-advanced-ediscovery.md)
  
[Etiquetado y formación de relevancia](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[Análisis de la relevancia de seguimiento](track-relevance-analysis-in-advanced-ediscovery.md)
  
[Decidir en función de los resultados](decision-based-on-the-results-in-advanced-ediscovery.md)
  
[Las pruebas de análisis de la relevancia](test-relevance-analysis-in-advanced-ediscovery.md)

