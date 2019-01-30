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
# <a name="configure-search-and-analytics-settings"></a><span data-ttu-id="9b1fa-102">Configurar las opciones de búsqueda y análisis</span><span class="sxs-lookup"><span data-stu-id="9b1fa-102">Configure search and analytics settings</span></span>


## <a name="near-duplicates-and-email-threading"></a><span data-ttu-id="9b1fa-103">Cerca de duplicados y los subprocesos de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="9b1fa-103">Near duplicates and email threading</span></span>

<span data-ttu-id="9b1fa-104">En esta sección, puede establecer parámetros para la detección de duplicados, cerca de detección de duplicados y subprocesos de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="9b1fa-104">In this section, you can set parameters for duplicate detection, near duplicate detection, and email threading.</span></span>

- <span data-ttu-id="9b1fa-p101">Habilitar o deshabilitar: incluyen la detección de duplicados, cerca de detección de duplicados y correo electrónico threading como parte del flujo de análisis si se habilita. Debido a que generan uno encima de otro, debe habilitar todos ellos o deshabilitar todos ellos.</span><span class="sxs-lookup"><span data-stu-id="9b1fa-p101">Enable/disable: include duplicate detection, near duplicate detection, and email threading as part of analytics flow if enabled. Because they build on top of each other, you must enable all of them or disable all of them.</span></span>

- <span data-ttu-id="9b1fa-107">Umbral: si el nivel de similitud de dos documentos está por encima del umbral, se colocarán en el mismo cerca de conjunto duplicado.</span><span class="sxs-lookup"><span data-stu-id="9b1fa-107">Threshold: if the similarity level of two documents are above the threshold, they will be put in the same near duplicate set.</span></span>

- <span data-ttu-id="9b1fa-p102">Ocultar duplicados de forma predeterminada: si esta opción está activada, se aplicará un filtro para ocultar documentos duplicados en el espacio de trabajo de forma predeterminada. El filtro se puede quitar de forma manual en el espacio de trabajo si es necesario.</span><span class="sxs-lookup"><span data-stu-id="9b1fa-p102">Hide duplicates by default: if this setting is on, a filter to hide duplicate documents will be applied in the working set by default. The filter can be removed manually in the working set if necessary.</span></span>

- <span data-ttu-id="9b1fa-p103">Número mínimo y máximo de palabras: cerca de duplicados y correo electrónico threading se ejecutará sólo en los documentos que tienen al menos el número mínimo de palabras y, como máximo, el número máximo de palabras. Para obtener más información, vea [cerca de detección de duplicados](near-duplicates.md) y los [subprocesos de correo electrónico](email-threading.md).</span><span class="sxs-lookup"><span data-stu-id="9b1fa-p103">Minimum/maximum number of words: near duplicates and email threading will run only on documents that have at least the minimum number of words and at most the maximum number of words. For more information, see [Near duplicate detection](near-duplicates.md) and [Email threading](email-threading.md).</span></span>

## <a name="themes"></a><span data-ttu-id="9b1fa-112">Temas</span><span class="sxs-lookup"><span data-stu-id="9b1fa-112">Themes</span></span>

<span data-ttu-id="9b1fa-113">En esta sección, puede establecer parámetros para los temas.</span><span class="sxs-lookup"><span data-stu-id="9b1fa-113">In this section, you can set parameters for themes.</span></span>

- <span data-ttu-id="9b1fa-114">Habilitar o deshabilitar: incluye temas de agrupación en clústeres como parte del flujo de análisis si se habilita.</span><span class="sxs-lookup"><span data-stu-id="9b1fa-114">Enable/disable: include themes clustering as part of analytics flow if enabled.</span></span>
- <span data-ttu-id="9b1fa-p104">Ajustar el número máximo de temas dinámicamente dinámicamente: en algunos casos, no hay suficientes documentos para producir el número deseado de temas. Si esta opción está activada, a continuación, en lugar de intentar forzar que el número máximo que desee de los temas, el sistema ajusta el número máximo de los temas dinámicamente.</span><span class="sxs-lookup"><span data-stu-id="9b1fa-p104">Adjust maximum number of themes dynamically dynamically: in certain cases, there are not enough documents to produce the desired number of themes. If this setting is turned on, then rather than trying to force the desired maximum number of themes, the system adjusts maximum number of themes dynamically.</span></span>
- <span data-ttu-id="9b1fa-117">Número máximo de temas: número deseado de temas</span><span class="sxs-lookup"><span data-stu-id="9b1fa-117">Maximum number of themes: desired number of themes</span></span>
- <span data-ttu-id="9b1fa-118">Incluir los números en los temas: cuando está habilitada, se incluyen los números de cuando la generación de temas.</span><span class="sxs-lookup"><span data-stu-id="9b1fa-118">Include numbers in themes: When enabled, it will include numbers in when generating themes.</span></span>  

## <a name="optical-character-recognition-ocr"></a><span data-ttu-id="9b1fa-119">Reconocimiento óptico de caracteres (OCR)</span><span class="sxs-lookup"><span data-stu-id="9b1fa-119">Optical character recognition (OCR)</span></span>

<span data-ttu-id="9b1fa-120">Cuando esta opción está activada, se ejecutará el reconocimiento óptico de caracteres en las imágenes que se ingestión en conjuntos de trabajo para que se pueden buscar.</span><span class="sxs-lookup"><span data-stu-id="9b1fa-120">When this setting is turned on, OCR will be run on images that are ingested into working sets so that they can be searchable.</span></span>

## <a name="ignore-text"></a><span data-ttu-id="9b1fa-121">Omitir el texto</span><span class="sxs-lookup"><span data-stu-id="9b1fa-121">Ignore text</span></span>

<span data-ttu-id="9b1fa-p105">Hay instancias donde determinados textos disminuirá la calidad de análisis, como prolongada declinación de responsabilidades que se agrega a determinados mensajes de correo electrónico con independencia del contenido del correo electrónico. Si tiene constancia de tales casos, puede excluir este texto de análisis mediante la especificación del texto (se admite RegEx) y módulos que se debe excluir de texto.</span><span class="sxs-lookup"><span data-stu-id="9b1fa-p105">There are instances where certain texts will diminish the quality of analytics, such as lengthy disclaimers that get added to certain emails regardless of the content of the email. If you are aware of such cases, you can exclude this text from analytics by specifying the text (RegEx is supported) and which modules that text should be excluded for.</span></span>