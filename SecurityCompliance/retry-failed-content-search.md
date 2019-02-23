---
title: Volver a intentar una búsqueda de contenido para resolver un error de ubicación de contenido
ms.author: markjjo
author: markjjo
manager: laurawi
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: ''
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Use el botón Reintentar para resolver búsquedas de contenido que tienen errores de ubicación de contenido.
ms.openlocfilehash: 032d93ef0990ed1dd7c1ea7bf2ba16653b3a862f
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/23/2019
ms.locfileid: "30218860"
---
# <a name="retry-a-content-search-to-resolve-a-content-location-error"></a><span data-ttu-id="b0fd7-103">Volver a intentar una búsqueda de contenido para resolver un error de ubicación de contenido</span><span class="sxs-lookup"><span data-stu-id="b0fd7-103">Retry a Content Search to resolve a content location error</span></span>

<span data-ttu-id="b0fd7-104">Cuando usa la búsqueda de contenido en el centro de seguridad & cumplimiento de Office 365 para buscar en un gran número de buzones (por ejemplo, buscar en 100.000 buzones o más en una sola búsqueda de contenido), es posible que obtenga errores de búsqueda similares a los siguientes:</span><span class="sxs-lookup"><span data-stu-id="b0fd7-104">When you use Content Search in the Office 365 Security & Compliance Center to search a very large number of mailboxes (for example, searching 100,000 mailboxes or more in a single Content Search), you may get search errors that are similar to the following:</span></span>

```
Error

The search on the following locations failed:

User1@contoso.com: Problem in processing the request. Please try again later. If you keep getting this error, contact your admin. (CS008-009)

User2@contoso.com: Application error occurred. Please try again later. (CS012-002)
```

<span data-ttu-id="b0fd7-p101">Estos errores (con códigos de error de CS008-009 y CS012-002) indican que la búsqueda de contenido no pudo buscar ubicaciones de contenido específicas; en este ejemplo, no se han buscado dos buzones. Estos errores se muestran en la página flotante de detalles de estado de la búsqueda de contenido.</span><span class="sxs-lookup"><span data-stu-id="b0fd7-p101">These errors (with error codes of CS008-009 and CS012-002) indicate that Content Search failed to search specific content locations; in this example, two mailboxes weren't searched. These errors are displayed on the status details flyout page of the Content Search.</span></span>

## <a name="cause-of-content-location-errors"></a><span data-ttu-id="b0fd7-107">Causa de errores de ubicación de contenido</span><span class="sxs-lookup"><span data-stu-id="b0fd7-107">Cause of content location errors</span></span>

<span data-ttu-id="b0fd7-p102">Al buscar en un gran número de buzones, la búsqueda se distribuye entre miles de servidores en un centro de recursos de Microsoft. En un momento dado, los servidores específicos podrían estar en estado de reinicio o en proceso de conmutación por error a copias redundantes. En cualquiera de estos casos, se agotará el tiempo de espera de la solicitud de búsqueda de contenido para recuperar datos. En el ejemplo anterior, los errores de los buzones de correo que no superaron el resultado de la búsqueda superan el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="b0fd7-p102">When searching a large number of mailboxes, the search is distributed across thousands of servers in a Microsoft datacenter. At any one time, specific servers could be in reboot state or in the process of failing over to redundant copies. In either of these cases, the Content Search's request to retrieve data will timeout. In the previous example, the errors for the mailboxes that failed were the result of the search timing out.</span></span>

## <a name="resolving-content-location-errors"></a><span data-ttu-id="b0fd7-112">Resolución de errores de ubicación de contenido</span><span class="sxs-lookup"><span data-stu-id="b0fd7-112">Resolving content location errors</span></span>

<span data-ttu-id="b0fd7-p103">El reinicio de la búsqueda con frecuencia provocará errores similares en servidores diferentes. En lugar de reiniciar la búsqueda, haga clic en el botón **Reintentar** que se muestra en la parte superior de la página de resultados de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="b0fd7-p103">Restarting the search will often result in similar errors on different servers. Instead of restarting the search, click the **Retry** button that is displayed at the top of the search results page.</span></span>

![Haga clic en el botón Reintentar para resolver los errores de ubicación de contenido](media/retrycontentsearch3.png)

<span data-ttu-id="b0fd7-p104">Esto hará que se vuelva a intentar la búsqueda de los buzones de correo que no se realizaron correctamente. Cuando se vuelve a intentar la búsqueda, se conservan los otros resultados que se devolvieron correctamente.</span><span class="sxs-lookup"><span data-stu-id="b0fd7-p104">This will result in the retrying the search only for the mailboxes that failed. When you retry the search, the other results that were successfully returned are retained.</span></span>

## <a name="tips-to-avoid-content-location-errors"></a><span data-ttu-id="b0fd7-118">Sugerencias para evitar errores de ubicación de contenido</span><span class="sxs-lookup"><span data-stu-id="b0fd7-118">Tips to avoid content location errors</span></span>

<span data-ttu-id="b0fd7-119">Estas son algunas de las causas de los errores de ubicación de contenido y algunas sugerencias para ayudarle a evitarlos cuando busque grandes cantidades de buzones.</span><span class="sxs-lookup"><span data-stu-id="b0fd7-119">Here are some addition causes of content location errors and some tips to help you avoid them when searching large numbers of mailboxes.</span></span>

- <span data-ttu-id="b0fd7-p105">El buzón en el que se realiza la búsqueda puede estar ocupado debido a la actividad del usuario. En este caso, el servicio de búsqueda se puede limitar para evitar que el buzón deje de estar disponible. Para evitarlo, intente ejecutar búsquedas durante el horario no comercial.</span><span class="sxs-lookup"><span data-stu-id="b0fd7-p105">The mailbox being searched might be busy due to user activity. In this case, the search service might throttle itself to prevent the mailbox from becoming unavailable. To avoid this, try running searches during non-business hours.</span></span>

- <span data-ttu-id="b0fd7-p106">La consulta de búsqueda podría estar recuperando demasiado contenido del buzón. Si es posible, intente restringir el ámbito de la búsqueda usando palabras clave, intervalos de fechas y condiciones de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="b0fd7-p106">The search query might be retrieving too much content from the mailbox. If possible, try to narrow the scope of the search by using keywords, date ranges, and search conditions.</span></span>

- <span data-ttu-id="b0fd7-p107">Demasiadas palabras clave o frases de palabras clave al crear una consulta de búsqueda con la [lista de palabras clave](view-keyword-statistics-for-content-search.md#get-keyword-statistics-for-content-searches). Cuando se ejecuta una consulta de búsqueda que usa la lista de palabras clave, el servicio básicamente ejecuta una búsqueda independiente para cada fila de la lista de palabras clave de modo que se puedan generar estadísticas. Si está usando la lista de palabras clave en las consultas de búsqueda, minimice el número de filas de la lista de palabras clave o divida las palabras clave de número en listas más pequeñas y cree una búsqueda diferente para cada lista de palabras clave.</span><span class="sxs-lookup"><span data-stu-id="b0fd7-p107">Too many keywords or keyword phrases when you create a search query using the [keywords list](view-keyword-statistics-for-content-search.md#get-keyword-statistics-for-content-searches). When you run a search query that uses the keywords list, the service essentially runs a separate search for each row in the keyword list so that statistics can be generated. If you're using the keywords list in search queries, minimize the number of rows in the keyword list or divide the number keywords into smaller lists and create a different search for each keyword list.</span></span>

  > [!NOTE]
  > <span data-ttu-id="b0fd7-128">Para ayudar a reducir los problemas causados por listas de palabras clave grandes, ahora está limitado a un máximo de 20 filas en la lista de palabras clave de una consulta de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="b0fd7-128">To help reduce issues caused by large keyword lists, you're now limited to a maximum of 20 rows in the keyword list of a search query.</span></span>

- <span data-ttu-id="b0fd7-p108">Se están realizando demasiadas búsquedas en el mismo buzón al mismo tiempo. Si es posible, intente ejecutar una búsqueda cada vez en un buzón.</span><span class="sxs-lookup"><span data-stu-id="b0fd7-p108">Too many searches are being performed on the same mailbox at the same time. If possible, try to run one search at a time on any one mailbox.</span></span>

- <span data-ttu-id="b0fd7-p109">Buscar en un gran número de buzones en una sola búsqueda. La probabilidad de errores de ubicación de contenido aumenta al buscar un gran número de buzones. Si es posible, intente ejecutar varias búsquedas para que cada búsqueda incluya un subconjunto de buzones de correo en la organización.</span><span class="sxs-lookup"><span data-stu-id="b0fd7-p109">Searching too many mailboxes in a single search. The probability of content location errors increases when searching a very large number of mailboxes. If possible, try to run multiple searches so that each search includes a subset of  mailboxes in your organization.</span></span>

- <span data-ttu-id="b0fd7-p110">Se está realizando el mantenimiento necesario en el buzón de correo. Aunque esta causa probablemente se produzca con frecuencia, espere un poco después de recibir el error de ubicación de contenido y, a continuación, vuelva a intentar la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="b0fd7-p110">Required maintenance is being performed on the mailbox. Though this cause probably occurs infrequently, wait a little while after receiving the content location error and then retry the search.</span></span>
