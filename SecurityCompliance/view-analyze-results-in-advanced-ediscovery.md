---
title: Ver los resultados de análisis en eDiscovery avanzado de Office 365
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 9/14/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 5974f3c2-89fe-4c5f-ac7b-57f214437f7e
description: 'Entender dónde ver los resultados del proceso de analizar en Office 365 avanzada exhibición de documentos electrónicos, incluidas las definiciones de las opciones de la tarea que se muestra.  '
ms.openlocfilehash: 8f1de53e5548c8721f8fbfdb83374edb18379114
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22536582"
---
# <a name="view-analyze-results-in-office-365-advanced-ediscovery"></a><span data-ttu-id="c171e-103">Ver los resultados de análisis en eDiscovery avanzado de Office 365</span><span class="sxs-lookup"><span data-stu-id="c171e-103">View Analyze results in Office 365 Advanced eDiscovery</span></span>

> [!NOTE]
> <span data-ttu-id="c171e-p101">Exhibición de documentos electrónicos avanzada requiere un E3 de Office 365 con el complemento de cumplimiento avanzadas o una suscripción E5 para su organización. Si no tiene ese plan y desea probar avanzada exhibición de documentos electrónicos, puede [registrarse y obtener una versión de prueba de Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span><span class="sxs-lookup"><span data-stu-id="c171e-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="c171e-106">En la exhibición de documentos electrónicos avanzada, progreso y los resultados para el proceso de análisis pueden verse en una variedad de pantallas tal y como se describe a continuación.</span><span class="sxs-lookup"><span data-stu-id="c171e-106">In Advanced eDiscovery, progress and results for the Analyze process can be viewed in a variety of displays as described below.</span></span>
  
## <a name="view-analyze-task-status"></a><span data-ttu-id="c171e-107">Ver el estado de la tarea de análisis</span><span class="sxs-lookup"><span data-stu-id="c171e-107">View Analyze task status</span></span>

<span data-ttu-id="c171e-108">En **Prepare \> analizar \> los resultados \> estado de tareas**, se muestra el estado durante y después de la ejecución del proceso de análisis.</span><span class="sxs-lookup"><span data-stu-id="c171e-108">In **Prepare \> Analyze \> Results \> Task status**, the status is displayed during and after Analyze process execution.</span></span> 
  
![Analizar el estado de la tarea](media/d0372978-ce08-4f4e-a1fc-aa918ae44364.png)
  
<span data-ttu-id="c171e-110">Las tareas que se muestra pueden variar según las opciones seleccionadas.</span><span class="sxs-lookup"><span data-stu-id="c171e-110">The tasks displayed may vary depending on the options selected.</span></span> 
  
- <span data-ttu-id="c171e-111">**ND/ET: el programa de instalación**: prepara para la ejecución, por ejemplo, define los parámetros de ejecución y mayúsculas y minúsculas.</span><span class="sxs-lookup"><span data-stu-id="c171e-111">**ND/ET: setup**: Prepares for the run, for example, sets run and case parameters.</span></span>
    
- <span data-ttu-id="c171e-112">**ND/ET: cálculo ND**: análisis de procesos casi duplicados de archivos.</span><span class="sxs-lookup"><span data-stu-id="c171e-112">**ND/ET: ND calculation**: Processes Near-duplicate analysis of files.</span></span>
    
- <span data-ttu-id="c171e-113">**ND/ET: cálculo ET**: subprocesos de correo electrónico realiza análisis en el conjunto completo de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="c171e-113">**ND/ET: ET calculation**: Performs Email Thread analysis on the entire email set.</span></span>
    
- <span data-ttu-id="c171e-114">**ND/ET: tablas dinámicas y similitudes**: realiza la tabla dinámica y el procesamiento del archivo de similitud.</span><span class="sxs-lookup"><span data-stu-id="c171e-114">**ND/ET: pivots and similarities**: Performs pivot and file similarity processing.</span></span>
    
- <span data-ttu-id="c171e-115">**ND/ET: actualización de metadatos**: finaliza los nuevos datos recopilados en los archivos de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="c171e-115">**ND/ET: metadata update**: Finalizes the new data collected on the files in the database.</span></span>
    
- <span data-ttu-id="c171e-p102">**Temas: cálculo de los temas**: se ejecuta el análisis de los temas. (Muestra sólo si ha seleccionado).</span><span class="sxs-lookup"><span data-stu-id="c171e-p102">**Themes: themes calculation**: Runs themes analysis. (Displayed only if selected.)</span></span>
    
- <span data-ttu-id="c171e-p103">**Estado de la tarea**: esta línea se muestra después de la finalización de tareas. Mientras se ejecutan las tareas, se muestra la duración de ejecución.</span><span class="sxs-lookup"><span data-stu-id="c171e-p103">**Task status**: This line is displayed after task completion. While tasks are running, run duration is displayed.</span></span>
    
> [!NOTE]
> <span data-ttu-id="c171e-p104">Los resultados de análisis de cerca de duplicados y subprocesos de correo electrónico (ND y ED) se aplica al número de documentos que va a procesar. No incluye los archivos duplicados exactos.</span><span class="sxs-lookup"><span data-stu-id="c171e-p104">The Analyze results of Near-duplicates and Email Threads (ND and ED) applies to the number of documents to be processed. It does not include Exact duplicate files.</span></span> 
  
## <a name="view-near-duplicates-and-email-threads-status"></a><span data-ttu-id="c171e-122">Ver el estado de los subprocesos de correo electrónico y cerca de duplicados</span><span class="sxs-lookup"><span data-stu-id="c171e-122">View Near-duplicates and Email Threads status</span></span>

<span data-ttu-id="c171e-123">Los resultados de la población de **destino** mostrar el número de documentos, mensajes de correo electrónico, datos adjuntos y errores de la población de destino.</span><span class="sxs-lookup"><span data-stu-id="c171e-123">The **Target** population results display the number of documents, emails, attachments, and errors in the target population.</span></span> 
  
<span data-ttu-id="c171e-124">Los resultados de **documentos** mostrarán el número de tablas dinámicas, únicos cerca de duplicados y exacta de los archivos duplicada.</span><span class="sxs-lookup"><span data-stu-id="c171e-124">The **Documents** results display the number of pivots, unique near-duplicates, and exact duplicate files.</span></span> 
  
<span data-ttu-id="c171e-p105">Los resultados de **los correos electrónicos de** mostrarán el número de inclusive menos copias inclusivas únicas, ambos inclusive y el resto de los mensajes de correo electrónico. Los distintos tipos de resultados de correo electrónico son:</span><span class="sxs-lookup"><span data-stu-id="c171e-p105">The **Emails** results display the number of inclusive, inclusive minus, unique inclusive copies, and the rest of the email messages. The different types of email results are:</span></span> 
  
- <span data-ttu-id="c171e-p106">**Incluidos**: un correo electrónico inclusive es el nodo WriteError en un subproceso de correo electrónico y contiene todo el historial anterior de ese subproceso. Como resultado, el revisor con seguridad puede centrarse en el correo electrónico inclusive, sin necesidad de leer los mensajes anteriores en el subproceso.</span><span class="sxs-lookup"><span data-stu-id="c171e-p106">**Inclusive**: An inclusive email is the terminating node in an email thread and contains all the previous history of that thread. As a result, the reviewer can safely focus on the inclusive email, without the need to read the previous messages in the thread.</span></span> 
    
- <span data-ttu-id="c171e-p107">**Incluidos menos**: un correo electrónico inclusive se designa como menos inclusive, si hay uno o más diferentes los datos adjuntos asociados con los elementos primarios del mensaje inclusive. En este contexto, el término que primario se usa para los mensajes que se encuentra arriba en el subproceso de correo electrónico o las conversaciones se incluyen en ese correo electrónico inclusive específico. Un revisor puede usar inclusive menos indicación como una señal de que aunque es posible que no sea necesario revisar el contenido de los elementos primarios de correo electrónico inclusive, puede ser útil revisar los datos adjuntos asociados con los elementos primarios de la ruta de acceso en ambos inclusive.</span><span class="sxs-lookup"><span data-stu-id="c171e-p107">**Inclusive minus**: An inclusive email is designated as inclusive minus if there are one or more different attachments associated with the parents of the inclusive message. In this context, the term Parent is used for messages located upwards on the email thread or conversations included in that specific inclusive email. A reviewer can use the inclusive minus indication as a signal that although it might not be necessary to review the content of the inclusive email parents, it may be useful to review the attachments associated with the inclusive path parents.</span></span> 
    
- <span data-ttu-id="c171e-p108">**Copia inclusive**: un correo electrónico inclusive se designa como copia inclusive si se trata de la copia de otro mensaje marcado como inclusive o inclusive menos. En otras palabras, este mensaje tiene el mismo asunto y el cuerpo como otro mensaje inclusive y, como tal, co-autoría reside en el mismo nodo. Debido a que ambos inclusive copiar los mensajes contienen el mismo contenido, normalmente se omiten en el proceso de revisión.</span><span class="sxs-lookup"><span data-stu-id="c171e-p108">**Inclusive copy**: An inclusive email is designated as inclusive copy if it's the copy of another message marked as inclusive or inclusive minus. In other words, this message has the same subject and body as another inclusive message and, as such, co-resides in the same node. Because inclusive copy messages contain the same content, they can usually be skipped in the review process.</span></span> 
    
- <span data-ttu-id="c171e-p109">**El resto**: Esto indica correo electrónico que no contiene ningún contenido único y, por lo tanto, no se dividen en cualquiera de las tres categorías anteriores. Estos mensajes de correo electrónico no es necesario que se va a revisar. Si un mensaje contiene datos adjuntos que no se encuentra en un correo electrónico inclusive más adelante, a continuación, los datos adjuntos que necesite ser revisado. Esto se indica mediante la existencia de un inclusive menos correo electrónico dentro del subproceso.</span><span class="sxs-lookup"><span data-stu-id="c171e-p109">**The rest**: This indicates email that doesn't contain any unique content, and therefore doesn't fall into any of the previous three categories. These email messages don't need to be reviewed. If a message contains an attachment that isn't on a later inclusive email, then the attachment might need to be reviewed. This is indicated by the existence of an inclusive minus email within the thread.</span></span>
    
<span data-ttu-id="c171e-139">Los resultados de **los datos adjuntos de** mostrarán el número de datos adjuntos, según esas tipo como únicos y duplicados.</span><span class="sxs-lookup"><span data-stu-id="c171e-139">The **Attachments** results display the number of attachments, according to such type as unique and duplicates.</span></span> 
  
![Casi duplicados y subprocesos de correo electrónico](media/54491303-0ee3-4739-b42e-d1ee486842fd.png)
  
## <a name="see-also"></a><span data-ttu-id="c171e-141">Vea también</span><span class="sxs-lookup"><span data-stu-id="c171e-141">See also</span></span>

[<span data-ttu-id="c171e-142">eDiscovery avanzado de Office 365</span><span class="sxs-lookup"><span data-stu-id="c171e-142">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="c171e-143">Descripción de la similitud de documento</span><span class="sxs-lookup"><span data-stu-id="c171e-143">Understanding document similarity</span></span>](understand-document-similarity-in-advanced-ediscovery.md)
  
[<span data-ttu-id="c171e-144">Configurar las opciones de análisis</span><span class="sxs-lookup"><span data-stu-id="c171e-144">Setting Analyze options</span></span>](set-analyze-options-in-advanced-ediscovery.md)
  
[<span data-ttu-id="c171e-145">Configuración de omitir el texto</span><span class="sxs-lookup"><span data-stu-id="c171e-145">Setting ignore text</span></span>](set-ignore-text-in-advanced-ediscovery.md)
  
[<span data-ttu-id="c171e-146">Análisis de la opción Configuración avanzada</span><span class="sxs-lookup"><span data-stu-id="c171e-146">Setting Analyze advanced settings</span></span>](view-analyze-results-in-advanced-ediscovery.md)

