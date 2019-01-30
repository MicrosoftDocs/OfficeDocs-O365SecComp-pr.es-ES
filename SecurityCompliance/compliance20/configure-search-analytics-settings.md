---
title: Configurar las opciones de búsqueda y análisis
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: ''
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: d9528a4bcfaa77f2e232b25d03eda46cce42ebb9
ms.sourcegitcommit: ee28ee2b2bdfd049333c2f495d7f7780d13af4a6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2019
ms.locfileid: "29608357"
---
# <a name="configure-search-and-analytics-settings"></a>Configurar las opciones de búsqueda y análisis


## <a name="near-duplicates-and-email-threading"></a>Cerca de duplicados y los subprocesos de correo electrónico

En esta sección, puede establecer parámetros para la detección de duplicados, cerca de detección de duplicados y subprocesos de correo electrónico.

- Habilitar o deshabilitar: incluyen la detección de duplicados, cerca de detección de duplicados y correo electrónico threading como parte del flujo de análisis si se habilita. Debido a que generan uno encima de otro, debe habilitar todos ellos o deshabilitar todos ellos.

- Umbral: si el nivel de similitud de dos documentos está por encima del umbral, se colocarán en el mismo cerca de conjunto duplicado.

- Ocultar duplicados de forma predeterminada: si esta opción está activada, se aplicará un filtro para ocultar documentos duplicados en el espacio de trabajo de forma predeterminada. El filtro se puede quitar de forma manual en el espacio de trabajo si es necesario.

- Número mínimo y máximo de palabras: cerca de duplicados y correo electrónico threading se ejecutará sólo en los documentos que tienen al menos el número mínimo de palabras y, como máximo, el número máximo de palabras. Para obtener más información, vea [cerca de detección de duplicados](near-duplicates.md) y los [subprocesos de correo electrónico](email-threading.md).

## <a name="themes"></a>Temas

En esta sección, puede establecer parámetros para los temas.

- Habilitar o deshabilitar: incluye temas de agrupación en clústeres como parte del flujo de análisis si se habilita.
- Ajustar el número máximo de temas dinámicamente dinámicamente: en algunos casos, no hay suficientes documentos para producir el número deseado de temas. Si esta opción está activada, a continuación, en lugar de intentar forzar que el número máximo que desee de los temas, el sistema ajusta el número máximo de los temas dinámicamente.
- Número máximo de temas: número deseado de temas
- Incluir los números en los temas: cuando está habilitada, se incluyen los números de cuando la generación de temas.  

## <a name="optical-character-recognition-ocr"></a>Reconocimiento óptico de caracteres (OCR)

Cuando esta opción está activada, se ejecutará el reconocimiento óptico de caracteres en las imágenes que se ingestión en conjuntos de trabajo para que se pueden buscar.

## <a name="ignore-text"></a>Omitir el texto

Hay instancias donde determinados textos disminuirá la calidad de análisis, como prolongada declinación de responsabilidades que se agrega a determinados mensajes de correo electrónico con independencia del contenido del correo electrónico. Si tiene constancia de tales casos, puede excluir este texto de análisis mediante la especificación del texto (se admite RegEx) y módulos que se debe excluir de texto.