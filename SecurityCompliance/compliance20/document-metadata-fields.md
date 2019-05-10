---
title: Campos de metadatos del documento en eDiscovery avanzado
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: 75550d48a474fc6429a780d0a03d28745e20e1f7
ms.sourcegitcommit: 865b3dc071150b20bf3967e1263fc54e75898284
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/09/2019
ms.locfileid: "33835060"
---
# <a name="document-metadata-fields-in-advanced-ediscovery"></a>Campos de metadatos del documento en eDiscovery avanzado

En la tabla de este artículo se enumeran los campos de metadatos de los documentos en un conjunto de revisión en un caso en eDiscovery avanzado. La tabla indica el nombre del campo de metadatos, si el campo se puede buscar al ejecutar una consulta en un conjunto de revisiones, si el campo está presente cuando se ven los metadatos de un documento seleccionado en un conjunto de revisiones y si el campo se incluye cuando documentos a re exportó. 

> [!NOTE]
> Los valores entre paréntesis en la columna **búsquedas en el conjunto de revisiones** es el nombre de la propiedad que se puede buscar. Los valores que aparecen entre paréntesis en la columna **de metadatos de archivo visibles** es el nombre de la propiedad que se muestra cuando está viendo los metadatos de archivo.

|**Nombre de campo** </br>|**Se pueden buscar en el conjunto de revisión** |**Visible en los metadatos de archivo** |**Exported** |
|:-------------------------- |:---------------------------------------- |:------------------------|:------------------|
|Etiquetas Case                  | Sí (etiquetas)                                      |                         | Sí         |
|Etiquetas de cumplimiento          |                                                 |                         | Sí         |
|Ruta de acceso compuesta              |                                                 |                         | Sí         |
|IDENTIFICADOR de contenedor               |                                                 |                         | Sí         |
|Índice de conversaciones         |                                                 |                         | Sí         |
|Custodian                  | Sí (custodio)                                 |   Sí (custodio)       | Sí         |
|Origen de datos                | Sí (origen)                                    |   Sí (carga de trabajo)          | Sí         |
|Fecha                       | Sí (fecha)                                      |   Sí (Fecha UTC)        | Sí         |
|Ruta de acceso compuesta con desduplicación      |                                                 |                         | Sí         |
|Custodios de desduplicación         |                                                 |                         | Sí         |
|Identificadores de archivo desduplicado           |                                                 |                         | Sí         |
|Autores de documentos                | Sí (autor) *                                   |    Sí (autor)         | Sí         |
|Comentarios de documento               | Sí (comentarios)                                  |                         | Sí         |
|Compañía doc                |                                                 |                         | Sí         |
|Fecha de documento creada           | Sí (createdTime) *                              |    Sí (hora de creación)   | Sí         |
|Fecha de documento modificada          | Sí (lastModifiedDate) *                         |                         | Sí         |
|Palabras clave de documento               |                                                 |                         | Sí         |
|Último documento guardado por          |                                                 |                         | Sí         |
|Documento modificado por            |                                                 |                         | Sí         |
|Asunto del documento                |                                                 |  Sí (asunto/título)    | Sí         |
|Plantilla de documento               |                                                 |                         | Sí         |
|Título del documento                  | Sí (título)                                     |  Sí (título)            | Sí         |
|Versión de documento                |                                                 |                         | Sí         |
|Tema dominante             | Sí (dominantTheme)                             |  Sí (tema dominante)   | Sí         |
|Subconjunto duplicado           |                                                 |                         | Sí         |
|Acción de correo electrónico               |                                                 |                         | Sí         |
|CCO de correo electrónico                  | Sí (CCO)                                       |                         | Sí         |
|CC de correo electrónico                   | Sí (CC)                                        |                         | Sí         |
|IDENTIFICADOR de conversación de correo electrónico      |                                                 |                         | Sí         |
|Fecha de recepción de correo electrónico        | Sí (recibido)                                  |   Sí (recibido)        | Sí         |
|Fecha de envío del correo electrónico            | Sí (enviado)                                      |   Sí (enviado)            | Sí         |
|El correo electrónico tiene datos adjuntos       |                                                 |                         | Sí         |
|Importancia del correo electrónico           |                                                 |                         | Sí         |
|Encabezados de correo electrónico de Internet     |                                                 |                         | Sí         |
|Nivel de correo electrónico                |                                                 |                         | Sí         |
|IDENTIFICADOR del mensaje de correo electrónico           |                                                 |                         | Sí         |
|Dominios de participantes de correo electrónico  | Sí (participantDomains)                        |                         | Sí         |
|Participantes de correo electrónico         | Sí (participantes)                              |                         | Sí         |
|Dominios de destinatarios de correo electrónico    | Sí (recipientDomains)                          |                         | Sí         |
|Destinatarios de correo electrónico           | Sí (destinatarios)                                |                         | Sí         |
|Seguridad del correo electrónico             |                                                 |                         | Sí         |
|Remitente de correo electrónico               | Sí (remitente)                                    |   Sí (remitente)          | Sí         |
|Dominio del remitente de correo electrónico        | Sí (senderDomain)                              |                         | Sí         |
|Confidencialidad del correo electrónico          |                                                 |                         | Sí         |
|Conjunto de correo electrónico                  | Sí (emailSetId)                                |   Sí (EmailSetID)      | Sí         |
|Asunto de correo electrónico              | Sí (asunto)                                   |   Sí (asunto/título)   | Sí         |
|Hilo de correo electrónico               |                                                 |                         | Sí         |
|Correo electrónico a                   | Sí (para)                                        |                         | Sí         |
|Código de error                 | Sí (processingStatus)                          |                         | Sí         |
|Exportar ruta de acceso nativa         |                                                 |                         | Sí         |
|Longitud de texto extraída      |                                                 |                         | Sí         |
|Ruta de acceso del texto extraído        |                                                 |                         | Sí         |
|IDENTIFICADOR de familia                  | Sí (familyId)                                  |   Sí (FamilyId)        | Sí         |
|Tamaño de la familia                |                                                 |                         | Sí         |
|Clase File                 | Sí (fileClass)                                 |   Sí (clase de archivo)      | Sí         |
|IDENTIFICADOR de archivo                    | Sí (fileId)                                    |   Sí (ID.)              | Sí         |
|Tiene texto                   |                                                 |                         | Sí         |
|Tipo inclusivo             | Sí (inclusiveType)                             |   Sí (tipo inclusivo)  | Sí         |
|Fecha de entrada modificada        |                                                 |                         | Sí         |
|IDENTIFICADOR de archivo de entrada              |                                                 |                         | Sí         |
|Ruta de acceso de entrada                 |                                                 |                         | Sí         |
|Id. de mensaje de Internet        |                                                 |                         | Sí         |
|Es representativo          | Sí (markAsRepresentative)                      |                         | Sí         |
|Clase Item                 |                                                 |                         | Sí         |
|IDENTIFICADOR de carga                    | Sí (loadId)                                    |                         | Sí         |
|Nombre de la ubicación              |                                                 |                         | Sí         |
|Marcado como Pivot            | Sí (markAsPivot)                               |   Sí (marcado como Pivot) | Sí         |
|Tipo de mensaje               | Sí (messageKind)                               |                         | Sí         |
|Extensión nativa           |                                                 |                         | Sí         |
|Nombre de archivo nativo           |                                                 |    Sí (nombre de archivo)      | Sí         |
|MD5 nativo                 |                                                 |                         | Sí         |
|SHA 256 nativo             |                                                 |                         | Sí         |
|Tamaño nativo                | Sí (tamaño)                                      |   Sí (NativeSize)     | Sí         |
|Tipo nativo                | Sí (fileType)                                  |   Sí (tipo de archivo)       | Sí         |
|Ordena ET no vinculado     |                                                 |                         | Sí         |
|Ordena ET ordenar incl.     |                                                 |                         | Sí         |
|ND establecido                     |                                                 |                         | Sí         |
|Autores de O365               | Sí (autor) *                                   |   Sí (remitente/autor)   | Sí         |
|O365 creado por            |                                                 |                         | Sí         |
|Fecha de creación de O365          | Sí (createdTime) *                              |                         | Sí         |
|Fecha de modificación de O365         | Sí (lastModifiedDate) *                         |   Sí (fecha de la última modificación) | Sí      |
|O365 modificada por           |                                                 |                         | Sí         |
|Nodo primario                |                                                 |                         | Sí         |
|IDENTIFICADOR dinámico                   | Sí (pivotId)                                   |  Sí (PivotID)          | Sí         |
|Número de destinatarios            |                                                 |                         | Sí         |
|Número de fila                 |                                                 |                         | Sí         |
|IDENTIFICADOR de conjunto                     |                                                 |                         | Sí         |
|Establecer primero los incluidos en el orden |                                                 |                         | Sí         |
|Porcentaje de similitud         |                                                 |                         | Sí         |
|Lista de temas                | Sí (themesList)                                | Sí (lista de temas)       | Sí         |
|Word count                 | Sí (wordCount)                                 |                         | Sí         |
|Puntuación de relevancia (problema)    | Sí (relevanceScore_issueNum)                   |                         | Sí           |
|Percentiles de lectura (problema)    | Sí (readPercentile_issueNum)                   |                         | Sí          |
|Etiqueta de relevancia (problema)      | Sí (relevanceTag_issueNum)                     |                         | Sí           |
|||||

  \*En estos campos, si hay valores incrustados en un documento, la búsqueda dará prioridad a esos valores; de lo contrario, intentará mostrar el valor de Office 365.