---
title: Vuelva a intentar una búsqueda de contenido para resolver un error de ubicación de contenido
ms.author: markjjo
author: markjjo
manager: laurawi
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: ''
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Use el botón Reintentar para resolver las búsquedas de contenido que tienen errores de ubicación de contenido.
ms.openlocfilehash: 0fdc11593fec42e1f9f9b76fbbb408d9c16fd183
ms.sourcegitcommit: d5f841744b716fcf368c670009b61441f5a5eed2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/08/2018
ms.locfileid: "27210201"
---
# <a name="retry-a-content-search-to-resolve-a-content-location-error"></a><span data-ttu-id="0155a-103">Vuelva a intentar una búsqueda de contenido para resolver un error de ubicación de contenido</span><span class="sxs-lookup"><span data-stu-id="0155a-103">Retry a Content Search to resolve a content location error</span></span>

<span data-ttu-id="0155a-104">Cuando se usa la búsqueda de contenido en el centro de cumplimiento y seguridad de Office 365 para buscar un gran número de buzones (por ejemplo, buscar 100.000 buzones o más en una sola búsqueda de contenido), obtendrá errores de búsqueda que son similares a lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="0155a-104">When you use Content Search in the Office 365 Security & Compliance Center to search a very large number of mailboxes (for example, searching 100,000 mailboxes or more in a single Content Search), you may get search errors that are similar to the following:</span></span>

```
Error

The search on the following locations failed:

User1@contoso.com: Problem in processing the request. Please try again later. If you keep getting this error, contact your admin. (CS008-009)

User2@contoso.com: Application error occurred. Please try again later. (CS012-002)
```

<span data-ttu-id="0155a-p101">Estos errores (con códigos de error de CS008-009 y CS012-002) indican que no se pudieron búsqueda de contenido buscar en ubicaciones específicas de contenido; en este ejemplo, no se han buscado dos buzones. Estos errores se muestran en la página de emergente de detalles de estado de la búsqueda de contenido.</span><span class="sxs-lookup"><span data-stu-id="0155a-p101">These errors (with error codes of CS008-009 and CS012-002) indicate that Content Search failed to search specific content locations; in this example, two mailboxes weren't searched. These errors are displayed on the status details flyout page of the Content Search.</span></span>

## <a name="cause-of-content-location-errors"></a><span data-ttu-id="0155a-107">Causa de errores de ubicación de contenido</span><span class="sxs-lookup"><span data-stu-id="0155a-107">Cause of content location errors</span></span>

<span data-ttu-id="0155a-p102">Al buscar en un gran número de buzones de correo, la búsqueda se distribuye a través de miles de servidores en un centro de datos de Microsoft. En un momento dado, servidores específicos podrían estar en estado de reinicio o en el proceso de conmutación por error para copias redundantes. En cualquiera de estos casos, la solicitud de búsqueda de contenido para recuperar datos será tiempo de espera. En el ejemplo anterior, los errores para los buzones de correo que no se pudo eran el resultado de la búsqueda alcanzar el tiempo límite.</span><span class="sxs-lookup"><span data-stu-id="0155a-p102">When searching a large number of mailboxes, the search is distributed across thousands of servers in a Microsoft datacenter. At any one time, specific servers could be in reboot state or in the process of failing over to redundant copies. In either of these cases, the Content Search's request to retrieve data will timeout. In the previous example, the errors for the mailboxes that failed were the result of the search timing out.</span></span>

## <a name="resolving-content-location-errors"></a><span data-ttu-id="0155a-112">Resolución de errores de ubicación de contenido</span><span class="sxs-lookup"><span data-stu-id="0155a-112">Resolving content location errors</span></span>

<span data-ttu-id="0155a-p103">Reiniciar la búsqueda a menudo provocarán errores similares en servidores diferentes. En lugar de reiniciar la búsqueda, haga clic en el botón **Reintentar** que se muestra en la parte superior de la página de resultados de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="0155a-p103">Restarting the search will often result in similar errors on different servers. Instead of restarting the search, click the **Retry** button that is displayed at the top of the search results page.</span></span>

![Haga clic en el botón Reintentar para resolver errores de ubicación de contenido](media/retrycontentsearch3.png)

<span data-ttu-id="0155a-p104">Esto dará como resultado de volver a intentar la búsqueda solo para los buzones de correo con errores. Cuando se vuelva a intentar la búsqueda, se conservan los otros resultados que se han devuelto correctamente.</span><span class="sxs-lookup"><span data-stu-id="0155a-p104">This will result in the retrying the search only for the mailboxes that failed. When you retry the search, the other results that were successfully returned are retained.</span></span>

## <a name="tips-to-avoid-content-location-errors"></a><span data-ttu-id="0155a-118">Sugerencias para evitar errores de ubicación de contenido</span><span class="sxs-lookup"><span data-stu-id="0155a-118">Tips to avoid content location errors</span></span>

<span data-ttu-id="0155a-119">A continuación presentamos algunas de las causas adición de errores de la ubicación del contenido y algunos consejos para ayudarle a evitarlos al buscar en un gran número de buzones de correo.</span><span class="sxs-lookup"><span data-stu-id="0155a-119">Here are some addition causes of content location errors and some tips to help you avoid them when searching large numbers of mailboxes.</span></span>

- <span data-ttu-id="0155a-p105">El buzón de correo que se buscan esté ocupado debido a la actividad de usuario. En este caso, el servicio de búsqueda puede limitar propio para evitar que el buzón de correo no está disponible. Para evitar este problema, intente ejecutar búsquedas durante el horario no.</span><span class="sxs-lookup"><span data-stu-id="0155a-p105">The mailbox being searched might be busy due to user activity. In this case, the search service might throttle itself to prevent the mailbox from becoming unavailable. To avoid this, try running searches during non-business hours.</span></span>

- <span data-ttu-id="0155a-p106">La consulta de búsqueda puede estar recuperando demasiado contenido desde el buzón de correo. Si es posible, intente reducir el ámbito de la búsqueda mediante el uso de palabras clave, los intervalos de fechas y las condiciones de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="0155a-p106">The search query might be retrieving too much content from the mailbox. If possible, try to narrow the scope of the search by using keywords, date ranges, and search conditions.</span></span>

- <span data-ttu-id="0155a-p107">Demasiadas palabras clave o frases de palabra clave cuando se crea una consulta de búsqueda con la [lista de palabras clave](view-keyword-statistics-for-content-search.md#get-keyword-statistics-for-content-searches). Cuando se ejecuta una consulta de búsqueda que usa la lista de palabras clave, básicamente ejecuta el servicio una búsqueda independiente para cada fila en la lista de palabras clave para que se pueden generar las estadísticas. Si utiliza la lista de palabras clave en las consultas de búsqueda, minimizar el número de filas de la lista de palabras clave o dividir las palabras clave números en listas más pequeñas y crear una búsqueda diferente para cada lista de palabras clave.</span><span class="sxs-lookup"><span data-stu-id="0155a-p107">Too many keywords or keyword phrases when you create a search query using the [keywords list](view-keyword-statistics-for-content-search.md#get-keyword-statistics-for-content-searches). When you run a search query that uses the keywords list, the service essentially runs a separate search for each row in the keyword list so that statistics can be generated. If you're using the keywords list in search queries, minimize the number of rows in the keyword list or divide the number keywords into smaller lists and create a different search for each keyword list.</span></span>

  > [!NOTE]
  > <span data-ttu-id="0155a-128">Para ayudar a reducir los problemas de listas de palabras clave de gran tamaño, ahora está limitado a un máximo de 20 filas de la lista de palabras clave de una consulta de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="0155a-128">To help reduce issues caused by large keyword lists, you're now limited to a maximum of 20 rows in the keyword list of a search query.</span></span>

- <span data-ttu-id="0155a-p108">Un número excesivo de búsquedas se están ejecutando en el mismo buzón al mismo tiempo. Si es posible, intente ejecutar una búsqueda a la vez en un buzón de prueba.</span><span class="sxs-lookup"><span data-stu-id="0155a-p108">Too many searches are being performed on the same mailbox at the same time. If possible, try to run one search at a time on any one mailbox.</span></span>

- <span data-ttu-id="0155a-p109">Búsqueda de un número excesivo de buzones de correo en una sola búsqueda. La probabilidad de errores de ubicación de contenido aumenta al buscar en un gran número de buzones de correo. Si es posible, intente ejecutar varias búsquedas de modo que cada búsqueda incluye un subconjunto de los buzones de correo en la organización.</span><span class="sxs-lookup"><span data-stu-id="0155a-p109">Searching too many mailboxes in a single search. The probability of content location errors increases when searching a very large number of mailboxes. If possible, try to run multiple searches so that each search includes a subset of  mailboxes in your organization.</span></span>

- <span data-ttu-id="0155a-p110">Mantenimiento necesario se lleva a cabo en el buzón de correo. Aunque esto causa probablemente se produce con poca frecuencia, esperar un poco mientras después de recibir el error de ubicación de contenido y, a continuación, vuelva a intentar la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="0155a-p110">Required maintenance is being performed on the mailbox. Though this cause probably occurs infrequently, wait a little while after receiving the content location error and then retry the search.</span></span>
