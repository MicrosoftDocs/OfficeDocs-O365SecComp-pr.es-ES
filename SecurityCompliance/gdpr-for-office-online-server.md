---
title: RGPD para Office Online Server y Office Web Apps Server
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.custom: ''
localization_priority: Priority
description: Obtenga información sobre cómo cumplir los requisitos de RGPD en Exchange Server local.
ms.openlocfilehash: c5a0fe45ad0d36f0caf30e04f481a11ea58241a5
ms.sourcegitcommit: c31424cafbf1953f2864d7e2ceb95b329a694edb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/29/2018
ms.locfileid: "23272335"
---
# <a name="gdpr-for-office-web-apps-server-and-office-online-server"></a><span data-ttu-id="6c9ea-103">RGPD para Office Web Apps Server y Office Online Server</span><span class="sxs-lookup"><span data-stu-id="6c9ea-103">GDPR for Office Web Apps Server and Office Online Server</span></span>

<span data-ttu-id="6c9ea-p101">Los datos de telemetría de Office Online Server y Office Web Apps Server se almacenan en un formulario de registros ULS. Puede usar el [Visor de ULS](https://www.microsoft.com/en-us/download/details.aspx?id=44020) para ver los registros ULS de su inquilino local.</span><span class="sxs-lookup"><span data-stu-id="6c9ea-p101">Office Online Server and Office Web Apps Server telemetry data is stored in the form of ULS logs. You can use [ULS Viewer](https://www.microsoft.com/en-us/download/details.aspx?id=44020) to view ULS logs from your on-premises tenant.</span></span>

<span data-ttu-id="6c9ea-p102">Cada línea de registro contiene un CorrelationID. Las líneas de registros relacionadas comparten el mismo CorrelationID. Cada CorrelationID está vinculado a un SessionID único y un SessionID puede estar relacionado con muchos CorrelationID. Cada SessionID puede estar relacionado con un único UserID, aunque algunas sesiones pueden ser anónimas y, por tanto, no tiene un UserID asociado. Para determinar qué datos están asociados a un usuario determinado, es posible asignar desde un UserID único para los SessionID asociados a ese usuario, de los SessionID a los CorrelationID, y de esos CorrelationID a todos los registros en las correlaciones. Consulte el siguiente diagrama para obtener información sobre la relación entre los distintos identificadores.</span><span class="sxs-lookup"><span data-stu-id="6c9ea-p102">Every log line contains a CorrelationID. Related log lines share the same CorrelationID. Each CorrelationID is tied to a single SessionID, and one SessionID may be related to many CorrelationIDs. Each SessionID may be related to a single UserID, although some sessions can be anonymous and therefore not have an associated UserID. In order to determine what data is associated with a particular user, it is therefore possible to map from a single UserID to the SessionIDs associated with that user, from those SessionIDs to the associated CorrelationIDs, and from those CorrelationIDs to all the logs in those correlations. See the below diagram for the relationship between the different IDs.</span></span>

![](media/gdpr-for-office-online-server-image1.jpg)

## <a name="gathering-logs"></a><span data-ttu-id="6c9ea-112">Registros de recopilación</span><span class="sxs-lookup"><span data-stu-id="6c9ea-112">Gathering Logs</span></span>

<span data-ttu-id="6c9ea-p103">Para recopilar todos los registros asociados con el UserID 1, por ejemplo, el primer paso sería recopilar todas las sesiones asociadas con el UserID 1 (es decir, SessionID 1 y SessionID 2). El siguiente paso sería recopilar todas las correlaciones asociadas con SessionID 1 (es decir, CorrelationID 1, 2 y 3) y SessionID 2 (es decir, CorrelationID 4). Por último, recopile todos los registros asociados con cada una de las correlaciones en la lista.</span><span class="sxs-lookup"><span data-stu-id="6c9ea-p103">In order to gather all logs associated with UserID 1, for example, the first step would be to gather all sessions associated with UserID 1 (i.e. SessionID 1 and SessionID2). The next step would be to gather all correlations associated with SessionID 1 (i.e. CorrelationIDs 1, 2, and 3) and with SessionID 2 (i.e. CorrelationID 4). Finally, gather all logs associated with each of the correlations in the list.</span></span>

1.  <span data-ttu-id="6c9ea-116">Iniciar UlsViewer</span><span class="sxs-lookup"><span data-stu-id="6c9ea-116">Launch UlsViewer</span></span>

2.  <span data-ttu-id="6c9ea-117">Abra el registro de ULS correspondiente al periodo de tiempo previsto; los registros ULS se almacenan en %PROGRAMDATA%\\Microsoft\\OfficeWebApps\\Data\\Logs\\ULS</span><span class="sxs-lookup"><span data-stu-id="6c9ea-117">Open up the uls log corresponding to the intended timeframe; ULS logs are stored in %PROGRAMDATA%\\Microsoft\\OfficeWebApps\\Data\\Logs\\ULS</span></span>

3.  <span data-ttu-id="6c9ea-118">Editar o modificar filtros</span><span class="sxs-lookup"><span data-stu-id="6c9ea-118">Edit | Modify Filter</span></span>

4.  <span data-ttu-id="6c9ea-119">Aplique un filtro que sea:</span><span class="sxs-lookup"><span data-stu-id="6c9ea-119">Apply a filter that is:</span></span>

    -   <span data-ttu-id="6c9ea-120">EventID es igual a apr3y o</span><span class="sxs-lookup"><span data-stu-id="6c9ea-120">EventID equals apr3y Or</span></span>

    -   <span data-ttu-id="6c9ea-121">EventID es igual a bp2d6</span><span class="sxs-lookup"><span data-stu-id="6c9ea-121">EventID equals bp2d6</span></span>

5.  <span data-ttu-id="6c9ea-122">Los UserId con hash estarán en el mensaje de uno de estos dos eventos</span><span class="sxs-lookup"><span data-stu-id="6c9ea-122">Hashed UserIds will be in the Message of either one of these two events</span></span>

6.  <span data-ttu-id="6c9ea-123">Para apr3y, el mensaje contiene un valor de UserID y un valor PUID</span><span class="sxs-lookup"><span data-stu-id="6c9ea-123">For apr3y, the Message will contain a UserID value and a PUID value</span></span>

7.  <span data-ttu-id="6c9ea-p104">Para bp2d6, el mensaje contiene gran cantidad de información. El campo de valor LoggableUserId es el UserID con hash.</span><span class="sxs-lookup"><span data-stu-id="6c9ea-p104">For bp2d6, the Message will contain quite a bit of information. The LoggableUserId Value field is the hashed UserID.</span></span>

8.  <span data-ttu-id="6c9ea-126">Una vez que se obtiene el UserId con hash de cualquiera de estas dos etiquetas, el valor WacSessionId de dicha fila en ULSViewer contendrá el WacSessionId asociado a ese usuario</span><span class="sxs-lookup"><span data-stu-id="6c9ea-126">Once the hashed UserId is obtained from either of these two tags, the WacSessionId value of that row in ULSViewer will contain the WacSessionId associated with that user</span></span>

9.  <span data-ttu-id="6c9ea-127">Recopilar todos los valores de WacSessionId asociados al usuario en cuestión</span><span class="sxs-lookup"><span data-stu-id="6c9ea-127">Collect all of the WacSessionId values associated with the user in question</span></span>

10. <span data-ttu-id="6c9ea-128">Filtre todos los EventId iguales a "xmnv", el mensaje es igual a "UserSessionId=\<WacSessionId\>" para el primer WacSessionId en la lista (reemplace la parte \<WacSessionId\> del filtro con su WacSessionId)</span><span class="sxs-lookup"><span data-stu-id="6c9ea-128">Filter for all EventId equals "xmnv", Message equals "UserSessionId=\<WacSessionId\>" for the first WacSessionId in the list (replacing the \<WacSessionId\> part of the filter with your WacSessionId)</span></span>

11. <span data-ttu-id="6c9ea-129">Recopilar todos los valores de correlación que coinciden con ese WacSessionId</span><span class="sxs-lookup"><span data-stu-id="6c9ea-129">Collect all values of Correlation that match that WacSessionId</span></span>

12. <span data-ttu-id="6c9ea-130">Repita los pasos 10-11 para todos los valores de WacSessionId en la lista del usuario en cuestión</span><span class="sxs-lookup"><span data-stu-id="6c9ea-130">Repeat steps 10-11 for all values of WacSessionId in your list for the user in question</span></span>

13. <span data-ttu-id="6c9ea-131">Filtrar todas las correlaciones es igual a la primera correlación en la lista</span><span class="sxs-lookup"><span data-stu-id="6c9ea-131">Filter for all Correlation equals the first Correlation in your list</span></span>

14. <span data-ttu-id="6c9ea-132">Recopilar todos los registros coincidentes con esa correlación</span><span class="sxs-lookup"><span data-stu-id="6c9ea-132">Collect all logs matching that Correlation</span></span>

15. <span data-ttu-id="6c9ea-133">Repita los pasos 13-14 para todos los valores de correlación en la lista del usuario en cuestión</span><span class="sxs-lookup"><span data-stu-id="6c9ea-133">Repeat steps 13-14 for all values of Correlation in your list for the user in question</span></span>

## <a name="types-of-data"></a><span data-ttu-id="6c9ea-134">Tipos de datos</span><span class="sxs-lookup"><span data-stu-id="6c9ea-134">Types of Data</span></span>

<span data-ttu-id="6c9ea-p105">Los registros de Office Online contienen una gran variedad de diferentes tipos de datos. Estos son algunos ejemplos de los datos que pueden contener los registros ULS:</span><span class="sxs-lookup"><span data-stu-id="6c9ea-p105">Office Online logs contain a variety of different types of data. The following are examples of the data that ULS logs may contain:</span></span>

-   <span data-ttu-id="6c9ea-137">Códigos de error para problemas detectados durante el uso del producto</span><span class="sxs-lookup"><span data-stu-id="6c9ea-137">Error codes for issues encountered during use of the product</span></span>

-   <span data-ttu-id="6c9ea-138">Clics de botones y otros fragmentos de datos sobre el uso de la aplicación</span><span class="sxs-lookup"><span data-stu-id="6c9ea-138">Button clicks and other pieces of data about app usage</span></span>

-   <span data-ttu-id="6c9ea-139">Datos de rendimiento de la aplicación y determinadas características en ella</span><span class="sxs-lookup"><span data-stu-id="6c9ea-139">Performance data about the app and/or particular features within the app</span></span>

-   <span data-ttu-id="6c9ea-140">Información de ubicación general sobre dónde está el equipo del usuario (por ejemplo, país o región, provincia y ciudad, derivados de la dirección IP), pero no la geolocalización precisa</span><span class="sxs-lookup"><span data-stu-id="6c9ea-140">General location information about where the user’s computer is (e.g. country / region, state, and city, derived from the IP address), but not precise geolocation</span></span>

-   <span data-ttu-id="6c9ea-141">Metadatos básicos sobre el explorador, por ejemplo, el nombre del explorador y la versión, y el equipo, por ejemplo, el tipo de sistema operativo y la versión</span><span class="sxs-lookup"><span data-stu-id="6c9ea-141">Basic metadata about the browser, e.g. browser name and version, and the computer, e.g. OS type and version</span></span>

-   <span data-ttu-id="6c9ea-142">Mensajes de error del host del documento (por ejemplo, OneDrive, SharePoint, Exchange)</span><span class="sxs-lookup"><span data-stu-id="6c9ea-142">Error messages from the document host (e.g. OneDrive, SharePoint, Exchange)</span></span>

-   <span data-ttu-id="6c9ea-143">Información sobre los procesos internos de la aplicación, que no está relacionada con las medidas que ha realizado el usuario</span><span class="sxs-lookup"><span data-stu-id="6c9ea-143">Information about processes internal to the app, unrelated to any action the user has taken</span></span>
