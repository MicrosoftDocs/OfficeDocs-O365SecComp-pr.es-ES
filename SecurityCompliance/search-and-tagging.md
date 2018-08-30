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
# <a name="search-and-tagging"></a><span data-ttu-id="edcee-104">Búsqueda y etiquetado</span><span class="sxs-lookup"><span data-stu-id="edcee-104">Search and Tagging</span></span>

<span data-ttu-id="edcee-p102">En la exhibición de documentos electrónicos avanzada, el módulo de búsqueda y etiquetado permite buscar, obtener una vista previa y organizar los documentos en su caso. Actualmente, en este módulo se encuentra en versión beta.</span><span class="sxs-lookup"><span data-stu-id="edcee-p102">In Advanced eDiscovery, the Search and Tagging module enables you to search, preview, and organize the documents in your case. Currently, this module is in beta.</span></span>

> [!NOTE]
> <span data-ttu-id="edcee-p103">Exhibición de documentos electrónicos avanzada requiere un E3 de Office 365 con el complemento de cumplimiento avanzadas o una suscripción E5 para su organización. Si no tiene ese plan y desea probar avanzada exhibición de documentos electrónicos, puede [registrarse y obtener una versión de prueba de Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span><span class="sxs-lookup"><span data-stu-id="edcee-p103">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
## <a name="search-the-documents-in-your-case"></a><span data-ttu-id="edcee-109">Buscar los documentos en su caso</span><span class="sxs-lookup"><span data-stu-id="edcee-109">Search the documents in your case</span></span>

<span data-ttu-id="edcee-p104">Una vez que haya procesado documentos de exhibición de documentos electrónicos avanzada y, opcionalmente, ejecutar el módulo de analizar o la relevancia, puede usar la búsqueda y etiquetado a organizar y buscar a través de los documentos en el caso de uso de etiquetas de específico de cada caso. Puede definir las consultas de uso de las tarjetas de condición proporcionada o a través de un lenguaje de consulta de palabras clave similares en las palabras clave condición tarjeta. Sintaxis de palabras clave comunes, como AND, OR, NOT y NEAR(n) son compatible, así como final comodín de varios caracteres (\*). Estas propiedades son compatibles con el nombre de propiedad de lenguaje de consulta:</span><span class="sxs-lookup"><span data-stu-id="edcee-p104">Once you have processed documents in Advanced eDiscovery and optionally run the Analyze module or the Relevance module, you can use Search and Tagging to search through the documents in the case and organize them using case-specific tags. You can define your queries using the provided condition cards, or through a KQL-like query language in the Keywords condition card. Common KQL syntax, such as AND, OR, NOT, and NEAR(n) are supported, as well as trailing multi-character wildcard (\*). These properties are supported in the query language property name:</span></span>

- <span data-ttu-id="edcee-114">caselabel: etiquetas creado o aplicar la búsqueda y etiquetado para este caso</span><span class="sxs-lookup"><span data-stu-id="edcee-114">caselabel: tags created/applied in Search and Tagging for this case</span></span> 
- <span data-ttu-id="edcee-115">custodia: asignado en el caso - sujetas a limitaciones de custodia</span><span class="sxs-lookup"><span data-stu-id="edcee-115">custodians: custodians assigned in the case - subject to limitations</span></span>
- <span data-ttu-id="edcee-116">fecha: envía la fecha para el correo electrónico, fecha para los documentos de la modificación</span><span class="sxs-lookup"><span data-stu-id="edcee-116">date: sent date for email, modified date for documents</span></span>
- <span data-ttu-id="edcee-117">FileID: identificador de archivos dentro de las mayúsculas y minúsculas</span><span class="sxs-lookup"><span data-stu-id="edcee-117">fileid: file ID within the case</span></span>
- <span data-ttu-id="edcee-118">FileType: extensión de archivo nativo</span><span class="sxs-lookup"><span data-stu-id="edcee-118">filetype: native file extension</span></span>
- <span data-ttu-id="edcee-119">fileclass: correo electrónico, documentos o datos adjuntos</span><span class="sxs-lookup"><span data-stu-id="edcee-119">fileclass: email, document, or attachment</span></span>
- <span data-ttu-id="edcee-120">senderauthor: remitente para los correos electrónicos, autor de documentos</span><span class="sxs-lookup"><span data-stu-id="edcee-120">senderauthor: sender for emails, author for documents</span></span>
- <span data-ttu-id="edcee-121">tamaño: tamaño del archivo en KB</span><span class="sxs-lookup"><span data-stu-id="edcee-121">size: size of the file in KB</span></span>
- <span data-ttu-id="edcee-122">Asunto: asunto para los correos electrónicos, título para documentos</span><span class="sxs-lookup"><span data-stu-id="edcee-122">subjecttitle: subject for emails, title for documents</span></span>
- <span data-ttu-id="edcee-123">cco</span><span class="sxs-lookup"><span data-stu-id="edcee-123">bcc</span></span>
- <span data-ttu-id="edcee-124">cc</span><span class="sxs-lookup"><span data-stu-id="edcee-124">cc</span></span>
- <span data-ttu-id="edcee-125">los participantes: direcciones de todos los participantes en un subproceso de correo electrónico, incluidos para faltan vínculos de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="edcee-125">participants: Email addresses of all participants in an email thread, including for missing links</span></span>
- <span data-ttu-id="edcee-126">recibido: fecha de recepción</span><span class="sxs-lookup"><span data-stu-id="edcee-126">received: received date</span></span>
- <span data-ttu-id="edcee-127">destinatarios: direcciones (para, cc, CCO) o nombres de los destinatarios de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="edcee-127">recipients: email recipient names or addresses (to, cc, bcc)</span></span>
- <span data-ttu-id="edcee-128">remitente</span><span class="sxs-lookup"><span data-stu-id="edcee-128">sender</span></span>
- <span data-ttu-id="edcee-129">LastModifiedDate: última fecha de un documento de modificación</span><span class="sxs-lookup"><span data-stu-id="edcee-129">lastmodifieddate: last modified date of a document</span></span>
- <span data-ttu-id="edcee-130">enviado: envía la fecha de un correo electrónico</span><span class="sxs-lookup"><span data-stu-id="edcee-130">sent: sent date of an email</span></span>
- <span data-ttu-id="edcee-131"> a </span><span class="sxs-lookup"><span data-stu-id="edcee-131">to</span></span>
- <span data-ttu-id="edcee-132">Autor: el autor de un correo electrónico</span><span class="sxs-lookup"><span data-stu-id="edcee-132">author: author of an email</span></span>
- <span data-ttu-id="edcee-133">título: título de un documento</span><span class="sxs-lookup"><span data-stu-id="edcee-133">title: title of a document</span></span>
- <span data-ttu-id="edcee-134">dominanttheme: tema dominante de un elemento\*</span><span class="sxs-lookup"><span data-stu-id="edcee-134">dominanttheme: dominant theme of an item\*</span></span>
- <span data-ttu-id="edcee-135">themeslist: los temas que se asocian con un elemento\*</span><span class="sxs-lookup"><span data-stu-id="edcee-135">themeslist: themes that are associated with an item\*</span></span>
- <span data-ttu-id="edcee-136">readpercentile_ [issuenum]: leer percentil de un elemento para problema [issuenum]\*\*</span><span class="sxs-lookup"><span data-stu-id="edcee-136">readpercentile_[issuenum]: read percentile of an item for issue [issuenum]\*\*</span></span>
- <span data-ttu-id="edcee-137">relevancescore_ [issuenum]: puntuación de relevancia de un elemento para problema [issuenum]\*\*</span><span class="sxs-lookup"><span data-stu-id="edcee-137">relevancescore_[issuenum]: relevance score of an item for issue [issuenum]\*\*</span></span>
- <span data-ttu-id="edcee-138">relevancetag_ [issuenum]: si se ha etiquetado manualmente un elemento de la relevancia, su etiqueta de [issuenum]\*\*</span><span class="sxs-lookup"><span data-stu-id="edcee-138">relevancetag_[issuenum]: if an item has been manually tagged for relevance, its tag for [issuenum]\*\*</span></span>

<span data-ttu-id="edcee-139">\*Sólo está disponible si se ha ejecutado el módulo temas \* \* sólo está disponible si se ha ejecutado el módulo de relevancia</span><span class="sxs-lookup"><span data-stu-id="edcee-139">\* Only available if the Themes module has been run \*\* Only available if the Relevance module has been run</span></span>
  
## <a name="see-also"></a><span data-ttu-id="edcee-140">Vea también</span><span class="sxs-lookup"><span data-stu-id="edcee-140">See also</span></span>

[<span data-ttu-id="edcee-141">eDiscovery avanzado de Office 365</span><span class="sxs-lookup"><span data-stu-id="edcee-141">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="edcee-142">Evaluación de descripción en la relevancia</span><span class="sxs-lookup"><span data-stu-id="edcee-142">Understanding Assessment in Relevance</span></span>](assessment-in-relevance-in-advanced-ediscovery.md)
  
[<span data-ttu-id="edcee-143">Etiquetas temáticas y evaluación</span><span class="sxs-lookup"><span data-stu-id="edcee-143">Tagging and Assessment</span></span>](tagging-and-assessment-in-advanced-ediscovery.md)
  
[<span data-ttu-id="edcee-144">Etiquetado y formación de relevancia</span><span class="sxs-lookup"><span data-stu-id="edcee-144">Tagging and Relevance training</span></span>](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[<span data-ttu-id="edcee-145">Análisis de la relevancia de seguimiento</span><span class="sxs-lookup"><span data-stu-id="edcee-145">Tracking Relevance analysis</span></span>](track-relevance-analysis-in-advanced-ediscovery.md)
  
[<span data-ttu-id="edcee-146">Decidir en función de los resultados</span><span class="sxs-lookup"><span data-stu-id="edcee-146">Deciding based on the results</span></span>](decision-based-on-the-results-in-advanced-ediscovery.md)
  
[<span data-ttu-id="edcee-147">Las pruebas de análisis de la relevancia</span><span class="sxs-lookup"><span data-stu-id="edcee-147">Testing Relevance analysis</span></span>](test-relevance-analysis-in-advanced-ediscovery.md)

