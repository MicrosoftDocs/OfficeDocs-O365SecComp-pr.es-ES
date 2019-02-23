---
title: Establecer la configuración de búsqueda y análisis
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: ''
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: 253650bb9916da8260491870d1a0bc899d6245c8
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/23/2019
ms.locfileid: "30217110"
---
# <a name="configure-search-and-analytics-settings"></a>Establecer la configuración de búsqueda y análisis


## <a name="near-duplicates-and-email-threading"></a>Duplicación cercana y subprocesamiento de correo electrónico

En esta sección, puede establecer parámetros para la detección de duplicados, la detección de mensajes casi duplicados y el hilo de correo electrónico.

- Habilitar/deshabilitar: incluir detección de duplicados, detección de duplicados y subproceso de correo electrónico como parte del flujo de análisis si está habilitado. Debido a que se basan en la otra parte, debe habilitarlas todas o deshabilitarlas todas.

- Umbral: Si el nivel de similitud de dos documentos está por encima del umbral, se colocarán en el mismo conjunto Near duplicado.

- Ocultar duplicados de manera predeterminada: Si esta configuración está activada, se aplicará un filtro para ocultar los documentos duplicados en el conjunto de trabajo de forma predeterminada. Si es necesario, el filtro se puede quitar manualmente en el conjunto de trabajo.

- Número mínimo o máximo de palabras: las próximas duplicaciones y el procesamiento de correo electrónico se ejecutarán solo en los documentos que tengan al menos el número mínimo de palabras y el número máximo de palabras como máximo. Para obtener más información, vea cerca de la [detección](near-duplicates.md) de duplicados y el [procesamiento de correo electrónico](email-threading.md).

## <a name="themes"></a>Temas

En esta sección, puede establecer parámetros para los temas.

- Habilitar/deshabilitar: incluir temas agrupados en clústeres como parte del flujo de análisis si está habilitado.
- Ajustar el número máximo de temas dinámicamente dinámicamente: en algunos casos, no hay documentos suficientes para generar el número deseado de temas. Si esta opción está activada, en lugar de intentar forzar el número máximo deseado de temas, el sistema ajusta dinámicamente el número máximo de temas.
- Número máximo de temas: número deseado de temas
- Incluir números en los temas: cuando está habilitado, incluirá los números en al generar los temas.  

## <a name="optical-character-recognition-ocr"></a>Reconocimiento óptico de caracteres (OCR)

Cuando esta opción está activada, OCR se ejecutará en las imágenes que se insertan en los conjuntos de trabajo para que se puedan buscar.

## <a name="ignore-text"></a>Omitir texto

Hay casos en los que determinados textos reducirán la calidad de los análisis, como las declinaciones de declinación de responsabilidad que se agregan a determinados mensajes de correo electrónico independientemente del contenido del correo electrónico. Si tiene constancia de estos casos, puede excluir este texto de análisis especificando el texto (se admite RegEx) y los módulos a los que se debe excluir el texto.