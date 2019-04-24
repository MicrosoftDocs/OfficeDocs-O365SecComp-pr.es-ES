---
title: Ver los resultados de ANALYZE en Office 365 Advanced eDiscovery
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 9/14/2017
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 5974f3c2-89fe-4c5f-ac7b-57f214437f7e
description: 'Comprenda dónde ver los resultados del proceso de análisis en la exhibición avanzada de documentos electrónicos de Office 365, incluidas las definiciones de las opciones de tarea mostradas.  '
ms.openlocfilehash: 990bcbb3c6626521d40f7ce057c764200d5047b5
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32267120"
---
# <a name="view-analyze-results-in-office-365-advanced-ediscovery"></a><span data-ttu-id="ba44c-103">Ver los resultados de ANALYZE en Office 365 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="ba44c-103">View Analyze results in Office 365 Advanced eDiscovery</span></span>

> [!NOTE]
> <span data-ttu-id="ba44c-p101">Para usar eDiscovery avanzado, su organización necesita una suscripción de Office 365 E3 con el complemento Cumplimiento avanzado, o bien una suscripción de E5. Si no tiene ese plan y quiere probar eDiscovery avanzado, puede [registrarse para una prueba de Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span><span class="sxs-lookup"><span data-stu-id="ba44c-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="ba44c-106">En la exhibición avanzada de documentos electrónicos, el progreso y los resultados del proceso de análisis se pueden ver en varias pantallas, como se describe a continuación.</span><span class="sxs-lookup"><span data-stu-id="ba44c-106">In Advanced eDiscovery, progress and results for the Analyze process can be viewed in a variety of displays as described below.</span></span>
  
## <a name="view-analyze-task-status"></a><span data-ttu-id="ba44c-107">Ver el estado de la tarea de análisis</span><span class="sxs-lookup"><span data-stu-id="ba44c-107">View Analyze task status</span></span>

<span data-ttu-id="ba44c-108">En \*\*preparar \> el \> estado \> \*\*de la tarea de resultados del análisis, el estado se muestra durante y después de analizar la ejecución del proceso.</span><span class="sxs-lookup"><span data-stu-id="ba44c-108">In **Prepare \> Analyze \> Results \> Task status**, the status is displayed during and after Analyze process execution.</span></span> 
  
![Analizar el estado de la tarea](media/d0372978-ce08-4f4e-a1fc-aa918ae44364.png)
  
<span data-ttu-id="ba44c-110">Las tareas mostradas pueden variar en función de las opciones seleccionadas.</span><span class="sxs-lookup"><span data-stu-id="ba44c-110">The tasks displayed may vary depending on the options selected.</span></span> 
  
- <span data-ttu-id="ba44c-111">**ND/et: Setup**: se prepara para la ejecución, por ejemplo, establece los parámetros Run y case.</span><span class="sxs-lookup"><span data-stu-id="ba44c-111">**ND/ET: setup**: Prepares for the run, for example, sets run and case parameters.</span></span>
    
- <span data-ttu-id="ba44c-112">**ND/et: ND Calculation**: procesa el análisis de archivos casi duplicados.</span><span class="sxs-lookup"><span data-stu-id="ba44c-112">**ND/ET: ND calculation**: Processes Near-duplicate analysis of files.</span></span>
    
- <span data-ttu-id="ba44c-113">**ND-et: et Calculation**: realiza análisis de subprocesos de correo electrónico en todo el conjunto de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="ba44c-113">**ND/ET: ET calculation**: Performs Email Thread analysis on the entire email set.</span></span>
    
- <span data-ttu-id="ba44c-114">**ND/et: tablas dinámicas y similitudes**: realiza el procesamiento de similitudes de archivos y tablas dinámicas.</span><span class="sxs-lookup"><span data-stu-id="ba44c-114">**ND/ET: pivots and similarities**: Performs pivot and file similarity processing.</span></span>
    
- <span data-ttu-id="ba44c-115">**ND/et: metadatos Update**: finaliza los nuevos datos recopilados en los archivos de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="ba44c-115">**ND/ET: metadata update**: Finalizes the new data collected on the files in the database.</span></span>
    
- <span data-ttu-id="ba44c-116">**Temas: cálculo de temas**: ejecuta el análisis de temas.</span><span class="sxs-lookup"><span data-stu-id="ba44c-116">**Themes: themes calculation**: Runs themes analysis.</span></span> <span data-ttu-id="ba44c-117">(Solo se muestra si está seleccionado).</span><span class="sxs-lookup"><span data-stu-id="ba44c-117">(Displayed only if selected.)</span></span>
    
- <span data-ttu-id="ba44c-118">**Estado**de la tarea: esta línea se muestra después de la finalización de la tarea.</span><span class="sxs-lookup"><span data-stu-id="ba44c-118">**Task status**: This line is displayed after task completion.</span></span> <span data-ttu-id="ba44c-119">Mientras se ejecutan las tareas, se muestra la duración de ejecución.</span><span class="sxs-lookup"><span data-stu-id="ba44c-119">While tasks are running, run duration is displayed.</span></span>
    
> [!NOTE]
> <span data-ttu-id="ba44c-120">Los resultados del análisis de casi duplicados y subProcesos de correo electrónico (ND y ED) se aplican al número de documentos que se van a procesar.</span><span class="sxs-lookup"><span data-stu-id="ba44c-120">The Analyze results of Near-duplicates and Email Threads (ND and ED) applies to the number of documents to be processed.</span></span> <span data-ttu-id="ba44c-121">No incluye los archivos duplicados exActos.</span><span class="sxs-lookup"><span data-stu-id="ba44c-121">It does not include Exact duplicate files.</span></span> 
  
## <a name="view-near-duplicates-and-email-threads-status"></a><span data-ttu-id="ba44c-122">Ver el estado de subProcesos Near-duplicados y correo electrónico</span><span class="sxs-lookup"><span data-stu-id="ba44c-122">View Near-duplicates and Email Threads status</span></span>

<span data-ttu-id="ba44c-123">Los resultados de la población de **destino** muestran el número de documentos, mensajes de correo electrónico, datos adjuntos y errores en el rellenado de destino.</span><span class="sxs-lookup"><span data-stu-id="ba44c-123">The **Target** population results display the number of documents, emails, attachments, and errors in the target population.</span></span> 
  
<span data-ttu-id="ba44c-124">Los resultados de los **documentos** muestran el número de elementos dinámicos, los únicos casi duplicados y los archivos duplicados exactos.</span><span class="sxs-lookup"><span data-stu-id="ba44c-124">The **Documents** results display the number of pivots, unique near-duplicates, and exact duplicate files.</span></span> 
  
<span data-ttu-id="ba44c-125">Los resultados de los **mensajes** de correo electrónico muestran el número de copias inclusivas inclusivas inclusive, únicas y exclusivas, así como el resto de los mensajes de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="ba44c-125">The **Emails** results display the number of inclusive, inclusive minus, unique inclusive copies, and the rest of the email messages.</span></span> <span data-ttu-id="ba44c-126">Los diferentes tipos de resultados de correo electrónico son:</span><span class="sxs-lookup"><span data-stu-id="ba44c-126">The different types of email results are:</span></span> 
  
- <span data-ttu-id="ba44c-127">**Inclusive**: un correo electrónico inclusivo es el nodo de terminación en un hilo de correo electrónico y contiene todo el historial anterior de ese hilo.</span><span class="sxs-lookup"><span data-stu-id="ba44c-127">**Inclusive**: An inclusive email is the terminating node in an email thread and contains all the previous history of that thread.</span></span> <span data-ttu-id="ba44c-128">Como resultado, el revisor puede centrarse de forma segura en el correo electrónico inclusivo, sin necesidad de leer los mensajes anteriores en el hilo.</span><span class="sxs-lookup"><span data-stu-id="ba44c-128">As a result, the reviewer can safely focus on the inclusive email, without the need to read the previous messages in the thread.</span></span> 
    
- <span data-ttu-id="ba44c-129">**Impuestos incluidos**: un correo electrónico inclusivo se designa como inclusivo menos si hay uno o varios datos adjuntos diferentes asociados con los elementos primarios del mensaje inclusivo.</span><span class="sxs-lookup"><span data-stu-id="ba44c-129">**Inclusive minus**: An inclusive email is designated as inclusive minus if there are one or more different attachments associated with the parents of the inclusive message.</span></span> <span data-ttu-id="ba44c-130">En este contexto, el término "primario" se usa para los mensajes ubicados hacia arriba en la conversación de correo electrónico o conversaciones incluidas en ese correo electrónico específico inclusivo.</span><span class="sxs-lookup"><span data-stu-id="ba44c-130">In this context, the term Parent is used for messages located upwards on the email thread or conversations included in that specific inclusive email.</span></span> <span data-ttu-id="ba44c-131">Un revisor puede usar la indicación de menos inclusivo como una señal que, aunque puede que no sea necesario revisar el contenido de los elementos primarios de correo electrónico inclusivos, puede resultar útil revisar los datos adjuntos asociados a los elementos principales de la ruta de acceso inclusiva.</span><span class="sxs-lookup"><span data-stu-id="ba44c-131">A reviewer can use the inclusive minus indication as a signal that although it might not be necessary to review the content of the inclusive email parents, it may be useful to review the attachments associated with the inclusive path parents.</span></span> 
    
- <span data-ttu-id="ba44c-132">**Copia inclusiva**: los correos electrónicos inclusivos se designan como copia inclusiva si es la copia de otro mensaje marcada como un signo menos inclusivo o inclusivo.</span><span class="sxs-lookup"><span data-stu-id="ba44c-132">**Inclusive copy**: An inclusive email is designated as inclusive copy if it's the copy of another message marked as inclusive or inclusive minus.</span></span> <span data-ttu-id="ba44c-133">Es decir, este mensaje tiene el mismo asunto y el mismo cuerpo que otro mensaje inclusivo y, como tal, coexiste en el mismo nodo.</span><span class="sxs-lookup"><span data-stu-id="ba44c-133">In other words, this message has the same subject and body as another inclusive message and, as such, co-resides in the same node.</span></span> <span data-ttu-id="ba44c-134">Como los mensajes de copia inclusivos contienen el mismo contenido, normalmente se pueden omitir en el proceso de revisión.</span><span class="sxs-lookup"><span data-stu-id="ba44c-134">Because inclusive copy messages contain the same content, they can usually be skipped in the review process.</span></span> 
    
- <span data-ttu-id="ba44c-135">**El resto**: indica el correo electrónico que no contiene ningún contenido único y, por lo tanto, no se incluye en ninguna de las tres categorías anteriores.</span><span class="sxs-lookup"><span data-stu-id="ba44c-135">**The rest**: This indicates email that doesn't contain any unique content, and therefore doesn't fall into any of the previous three categories.</span></span> <span data-ttu-id="ba44c-136">No es necesario revisar estos mensajes de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="ba44c-136">These email messages don't need to be reviewed.</span></span> <span data-ttu-id="ba44c-137">Si un mensaje contiene datos adjuntos que no están en un correo electrónico inclusivo posterior, es posible que sea necesario revisar los datos adjuntos.</span><span class="sxs-lookup"><span data-stu-id="ba44c-137">If a message contains an attachment that isn't on a later inclusive email, then the attachment might need to be reviewed.</span></span> <span data-ttu-id="ba44c-138">Esto se indica mediante la existencia de un correo electrónico menos inclusivo dentro del hilo.</span><span class="sxs-lookup"><span data-stu-id="ba44c-138">This is indicated by the existence of an inclusive minus email within the thread.</span></span>
    
<span data-ttu-id="ba44c-139">Los resultados de los **datos** adjuntos muestran el número de datos adjuntos, según el tipo único y duplicados.</span><span class="sxs-lookup"><span data-stu-id="ba44c-139">The **Attachments** results display the number of attachments, according to such type as unique and duplicates.</span></span> 
  
![Casi duplicados y subprocesos de correo electrónico](media/54491303-0ee3-4739-b42e-d1ee486842fd.png)
  
## <a name="see-also"></a><span data-ttu-id="ba44c-141">Vea también</span><span class="sxs-lookup"><span data-stu-id="ba44c-141">See also</span></span>

[<span data-ttu-id="ba44c-142">eDiscovery avanzado de Office 365</span><span class="sxs-lookup"><span data-stu-id="ba44c-142">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="ba44c-143">Descripción de la similitud de documentos</span><span class="sxs-lookup"><span data-stu-id="ba44c-143">Understanding document similarity</span></span>](understand-document-similarity-in-advanced-ediscovery.md)
  
[<span data-ttu-id="ba44c-144">Configuración de las opciones de análisis</span><span class="sxs-lookup"><span data-stu-id="ba44c-144">Setting Analyze options</span></span>](set-analyze-options-in-advanced-ediscovery.md)
  
[<span data-ttu-id="ba44c-145">Configuración de omitir texto</span><span class="sxs-lookup"><span data-stu-id="ba44c-145">Setting ignore text</span></span>](set-ignore-text-in-advanced-ediscovery.md)
  
[<span data-ttu-id="ba44c-146">Configuración de la configuración avanzada de análisis</span><span class="sxs-lookup"><span data-stu-id="ba44c-146">Setting Analyze advanced settings</span></span>](view-analyze-results-in-advanced-ediscovery.md)

