---
title: Ejecutar análisis para investigar con mayor rapidez
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
ms.openlocfilehash: 9516035fb6c758fdff1852249fff2815f19af559
ms.sourcegitcommit: 2c5834235c32b2616e1813ce24eeb3419a09629f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "31030499"
---
# <a name="run-analytics-to-investigate-faster"></a><span data-ttu-id="0bcc8-102">Ejecutar análisis para investigar con mayor rapidez</span><span class="sxs-lookup"><span data-stu-id="0bcc8-102">Run analytics to investigate faster</span></span>

<span data-ttu-id="0bcc8-103">Cuando una colección de evidencias es grande, puede ser difícil revisarlas todas.</span><span class="sxs-lookup"><span data-stu-id="0bcc8-103">When an evidence collection is large, it can be difficult to review them all.</span></span> <span data-ttu-id="0bcc8-104">Un conjunto de evidencias suele incluir varias copias de los mismos mensajes de correo electrónico o de documentos similares.</span><span class="sxs-lookup"><span data-stu-id="0bcc8-104">A set of evidence often includes multiple copies of the same or similar email messages or documents.</span></span> <span data-ttu-id="0bcc8-105">Las investigaciones de datos (versión preliminar) proporcionan una serie de herramientas de análisis que pueden ayudarle a reducir el volumen de documentos que deben revisarse sin que se pierda información.</span><span class="sxs-lookup"><span data-stu-id="0bcc8-105">Data Investigations (Preview) provides a number of analytics tools that can help you reduce the volume of documents that need to be reviewed without any loss in information.</span></span> <span data-ttu-id="0bcc8-106">Para obtener más información acerca de estas funciones, consulte:</span><span class="sxs-lookup"><span data-stu-id="0bcc8-106">To learn more about these capabilities, see:</span></span>

- [<span data-ttu-id="0bcc8-107">Detección de semiduplicados</span><span class="sxs-lookup"><span data-stu-id="0bcc8-107">Near duplicate detection</span></span>](near-duplicates.md)

- [<span data-ttu-id="0bcc8-108">Subprocesos de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="0bcc8-108">Email threading</span></span>](email-threading.md)

- [<span data-ttu-id="0bcc8-109">Temas</span><span class="sxs-lookup"><span data-stu-id="0bcc8-109">Themes</span></span>](themes.md)

<span data-ttu-id="0bcc8-110">Para analizar los datos de un conjunto de evidencias:</span><span class="sxs-lookup"><span data-stu-id="0bcc8-110">To analyze data in an evidence set:</span></span>

1. <span data-ttu-id="0bcc8-111">Configure las opciones de Analytics para su investigación.</span><span class="sxs-lookup"><span data-stu-id="0bcc8-111">Configure the analytics settings for your investigation.</span></span> <span data-ttu-id="0bcc8-112">Para obtener más información, vea [Configure Search and Analytics Settings](configure-search-analytics-settings.md).</span><span class="sxs-lookup"><span data-stu-id="0bcc8-112">For more information, see [Configure search and analytics settings](configure-search-analytics-settings.md).</span></span>

2. <span data-ttu-id="0bcc8-113">Abra el conjunto de evidencias.</span><span class="sxs-lookup"><span data-stu-id="0bcc8-113">Open the evidence set.</span></span>

3. <span data-ttu-id="0bcc8-114">Haga clic en **administrar evidencias**.</span><span class="sxs-lookup"><span data-stu-id="0bcc8-114">Click **Manage evidence**.</span></span>

4. <span data-ttu-id="0bcc8-115">En **análisis**, haga clic en **analizar**.</span><span class="sxs-lookup"><span data-stu-id="0bcc8-115">Under **Analytics**, click **Analyze**.</span></span>

<span data-ttu-id="0bcc8-116">Puede comprobar el progreso del análisis en la ficha **trabajos** de la investigación.</span><span class="sxs-lookup"><span data-stu-id="0bcc8-116">You can check the progress of analysis on the **Jobs** tab in your investigation.</span></span> <span data-ttu-id="0bcc8-117">El tipo de trabajo que se desencadena se denomina **análisis en ejecución**.</span><span class="sxs-lookup"><span data-stu-id="0bcc8-117">The job type that's triggered is named **Running analytics**.</span></span>

 <span data-ttu-id="0bcc8-118">Una vez completado el análisis, puede ver una lista de duplicados exactos o casi duplicados del documento que está revisando ubicado en el panel de la derecha.</span><span class="sxs-lookup"><span data-stu-id="0bcc8-118">After analysis is completed, you can see a list of exact duplicates or near-duplicates of the document that you're reviewing located in the panel on the right.</span></span> <span data-ttu-id="0bcc8-119">Para seleccionar todos los duplicados del documento que está viendo, puede hacerlo fácilmente con este panel.</span><span class="sxs-lookup"><span data-stu-id="0bcc8-119">To select all duplicates of the document you're viewing, you can easily do so using this panel.</span></span> <span data-ttu-id="0bcc8-120">Para obtener más información sobre otras características de este panel, consulte [Review Data in Evidence](review-data-in-evidence.md).</span><span class="sxs-lookup"><span data-stu-id="0bcc8-120">To learn more about other features on this panel, see [Review data in evidence](review-data-in-evidence.md).</span></span> 

<span data-ttu-id="0bcc8-121">También puede ejecutar consultas adicionales en su evidencia usando los resultados del análisis, como los temas.</span><span class="sxs-lookup"><span data-stu-id="0bcc8-121">You can also run additional queries within your evidence using the outputs of the analysis such as themes.</span></span> <span data-ttu-id="0bcc8-122">Para obtener más información, vea [consultar los datos en evidencias](evidence-query.md).</span><span class="sxs-lookup"><span data-stu-id="0bcc8-122">For more information, see [Query the data in evidence](evidence-query.md).</span></span>

## <a name="analytics-report"></a><span data-ttu-id="0bcc8-123">Informe de análisis</span><span class="sxs-lookup"><span data-stu-id="0bcc8-123">Analytics report</span></span>

<span data-ttu-id="0bcc8-124">Para ver un informe de análisis para su evidencia:</span><span class="sxs-lookup"><span data-stu-id="0bcc8-124">To view an analytics report for your evidence:</span></span>

1. <span data-ttu-id="0bcc8-125">Abra el conjunto de evidencias.</span><span class="sxs-lookup"><span data-stu-id="0bcc8-125">Open the evidence set.</span></span>

2. <span data-ttu-id="0bcc8-126">Haga clic en **administrar evidencias**.</span><span class="sxs-lookup"><span data-stu-id="0bcc8-126">Click **Manage evidence**.</span></span>

3. <span data-ttu-id="0bcc8-127">En **análisis**, haga clic en **Ver informe**.</span><span class="sxs-lookup"><span data-stu-id="0bcc8-127">Under **Analytics**, click **View report**.</span></span>

<span data-ttu-id="0bcc8-128">El informe tiene cuatro componentes del análisis:</span><span class="sxs-lookup"><span data-stu-id="0bcc8-128">The report has four components from analysis:</span></span>

- <span data-ttu-id="0bcc8-129">**Desglose** : el número de correos electrónicos sin procesar, datos adjuntos y documentos que se encuentran en el conjunto de evidencias.</span><span class="sxs-lookup"><span data-stu-id="0bcc8-129">**Breakdown** - The number of raw emails, attachments, and documents found in the evidence set.</span></span>

- <span data-ttu-id="0bcc8-130">Mensajes de **correo electrónico** : el número de mensajes de eamil que son inclusivos, ambos inclusive, copias inclusivas o ninguna de las anteriores.</span><span class="sxs-lookup"><span data-stu-id="0bcc8-130">**Emails** - The number of eamil messages that are inclusives, inclusive minuses, inclusive copies, or none of the above.</span></span>
   - <span data-ttu-id="0bcc8-131">Inclusivos: el último mensaje del hilo de correo electrónico que contiene todo el historial anterior y requiere revisión.</span><span class="sxs-lookup"><span data-stu-id="0bcc8-131">Inclusives: The last message in the email thread that contains all previous history and requires review.</span></span>
   - <span data-ttu-id="0bcc8-132">Minus inclusive: el mensaje del hilo que contiene uno o varios datos adjuntos diferentes que requieren revisión.</span><span class="sxs-lookup"><span data-stu-id="0bcc8-132">Inclusive minuses: The message in the thread that contains one or more different attachments that requires review.</span></span>
   - <span data-ttu-id="0bcc8-133">Copias inclusivas: mensaje que es una copia de otro mensaje menos inclusivo o inclusivo (asunto y cuerpo).</span><span class="sxs-lookup"><span data-stu-id="0bcc8-133">Inclusive copies: The message that is a copy of another inclusive or inclusive minus message (subject and body).</span></span>

- <span data-ttu-id="0bcc8-134">**Datos** adjuntos: número de datos adjuntos de correo electrónico únicos o duplicados de un archivo adjunto de correo electrónico diferente dentro de la misma evidencia.</span><span class="sxs-lookup"><span data-stu-id="0bcc8-134">**Attachments** - The number of email attachments that are unique or duplicates of a different email attachment within the same evidence same.</span></span>

- <span data-ttu-id="0bcc8-135">**Documentos (excepto archivos adjuntos de correo electrónico)** : número de documentos únicos que requieren revisión, por ejemplo, el documento más representativo del conjunto casi duplicado o un duplicado exacto de otro documento).</span><span class="sxs-lookup"><span data-stu-id="0bcc8-135">**Documents (excluding email attachments)** - The number of unique documents that require review, for example, the most representative document of the near-duplicate set or an exact duplicate of another document).</span></span>