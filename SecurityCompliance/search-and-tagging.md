---
title: Búsqueda y etiquetado
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 6/13/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 22f5adad-1bc0-460d-94a9-8732929f5b99
description: En la exhibición de documentos electrónicos avanzada, el módulo de búsqueda y etiquetado permite buscar, obtener una vista previa y organizar los documentos en su caso. Actualmente, en este módulo se encuentra en versión beta.
ms.openlocfilehash: fde887e496e9a40aa88d841053a0c66e48f04200
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22536276"
---
# <a name="search-and-tagging"></a>Búsqueda y etiquetado

En la exhibición de documentos electrónicos avanzada, el módulo de búsqueda y etiquetado permite buscar, obtener una vista previa y organizar los documentos en su caso. Actualmente, en este módulo se encuentra en versión beta.

> [!NOTE]
> Exhibición de documentos electrónicos avanzada requiere un E3 de Office 365 con el complemento de cumplimiento avanzadas o una suscripción E5 para su organización. Si no tiene ese plan y desea probar avanzada exhibición de documentos electrónicos, puede [registrarse y obtener una versión de prueba de Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279). 
  
## <a name="search-the-documents-in-your-case"></a>Buscar los documentos en su caso

Una vez que haya procesado documentos de exhibición de documentos electrónicos avanzada y, opcionalmente, ejecutar el módulo de analizar o la relevancia, puede usar la búsqueda y etiquetado a organizar y buscar a través de los documentos en el caso de uso de etiquetas de específico de cada caso. Puede definir las consultas de uso de las tarjetas de condición proporcionada o a través de un lenguaje de consulta de palabras clave similares en las palabras clave condición tarjeta. Sintaxis de palabras clave comunes, como AND, OR, NOT y NEAR(n) son compatible, así como final comodín de varios caracteres (*). Estas propiedades son compatibles con el nombre de propiedad de lenguaje de consulta:

- caselabel: etiquetas creado o aplicar la búsqueda y etiquetado para este caso 
- custodia: asignado en el caso - sujetas a limitaciones de custodia
- fecha: envía la fecha para el correo electrónico, fecha para los documentos de la modificación
- FileID: identificador de archivos dentro de las mayúsculas y minúsculas
- FileType: extensión de archivo nativo
- fileclass: correo electrónico, documentos o datos adjuntos
- senderauthor: remitente para los correos electrónicos, autor de documentos
- tamaño: tamaño del archivo en KB
- Asunto: asunto para los correos electrónicos, título para documentos
- cco
- cc
- los participantes: direcciones de todos los participantes en un subproceso de correo electrónico, incluidos para faltan vínculos de correo electrónico
- recibido: fecha de recepción
- destinatarios: direcciones (para, cc, CCO) o nombres de los destinatarios de correo electrónico
- remitente
- LastModifiedDate: última fecha de un documento de modificación
- enviado: envía la fecha de un correo electrónico
-  a 
- Autor: el autor de un correo electrónico
- título: título de un documento
- dominanttheme: tema dominante de un elemento\*
- themeslist: los temas que se asocian con un elemento\*
- readpercentile_ [issuenum]: leer percentil de un elemento para problema [issuenum]\*\*
- relevancescore_ [issuenum]: puntuación de relevancia de un elemento para problema [issuenum]\*\*
- relevancetag_ [issuenum]: si se ha etiquetado manualmente un elemento de la relevancia, su etiqueta de [issuenum]\*\*

\*Sólo está disponible si se ha ejecutado el módulo temas \* \* sólo está disponible si se ha ejecutado el módulo de relevancia
  
## <a name="see-also"></a>Vea también

[eDiscovery avanzado de Office 365](office-365-advanced-ediscovery.md)
  
[Evaluación de descripción en la relevancia](assessment-in-relevance-in-advanced-ediscovery.md)
  
[Etiquetas temáticas y evaluación](tagging-and-assessment-in-advanced-ediscovery.md)
  
[Etiquetado y formación de relevancia](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[Análisis de la relevancia de seguimiento](track-relevance-analysis-in-advanced-ediscovery.md)
  
[Decidir en función de los resultados](decision-based-on-the-results-in-advanced-ediscovery.md)
  
[Las pruebas de análisis de la relevancia](test-relevance-analysis-in-advanced-ediscovery.md)

