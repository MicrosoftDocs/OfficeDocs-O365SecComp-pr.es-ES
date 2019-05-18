---
title: RGPD para Skype Empresarial Server
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
description: Obtenga información sobre cómo cumplir los requisitos de RGPD en Skype Empresarial Server local y Lync Server.
ms.openlocfilehash: 835876af133dfbce056ee765336c9e981732226d
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/17/2019
ms.locfileid: "34154392"
---
# <a name="gdpr-for-skype-for-business-server-and-lync-server"></a><span data-ttu-id="14862-103">RGPD para Skype Empresarial Server y Lync Server</span><span class="sxs-lookup"><span data-stu-id="14862-103">GDPR for Skype for Business Server and Lync Server</span></span>

<span data-ttu-id="14862-p101">La mayoría de los datos de Skype Empresarial Server y Lync Server se almacenan en Exchange Server. Esto incluye:</span><span class="sxs-lookup"><span data-stu-id="14862-p101">Most Skype for Business Server and Lync Server data is stored in Exchange Server. This includes:</span></span>

-   <span data-ttu-id="14862-106">El historial de conversaciones</span><span class="sxs-lookup"><span data-stu-id="14862-106">Conversation history</span></span>

-   <span data-ttu-id="14862-107">Las transcripciones y las notificaciones de correo de voz</span><span class="sxs-lookup"><span data-stu-id="14862-107">Voicemail notifications and transcriptions</span></span>

-   <span data-ttu-id="14862-108">Las invitaciones a reuniones</span><span class="sxs-lookup"><span data-stu-id="14862-108">Meeting invites</span></span>

<span data-ttu-id="14862-109">Use los procedimientos descritos para [RGPD para Exchange Server](gdpr-for-exchange-server.md) para buscar, exportar o eliminar estos tipos de datos para las solicitudes de RGPD.</span><span class="sxs-lookup"><span data-stu-id="14862-109">Use the procedures outlined for [GDPR for Exchange Server](gdpr-for-exchange-server.md) to find, export, or delete these types of data for GDPR requests.</span></span>

<span data-ttu-id="14862-p102">Las listas de contactos se almacenan en la base de datos de SQL Server. Se pueden exportar de las siguientes maneras:</span><span class="sxs-lookup"><span data-stu-id="14862-p102">Contact lists are stored in the SQL Server database. They can be exported in the following ways:</span></span>

-   <span data-ttu-id="14862-p103">Los propios usuarios finales pueden exportar los contactos haciendo clic con el botón derecho en el encabezado de grupo y seleccionando Copiar. Esto copiará todos los contactos de ese grupo en el portapapeles, que después pueden pegarse en cualquier aplicación.</span><span class="sxs-lookup"><span data-stu-id="14862-p103">End users themselves can export the contacts by right clicking the group header and selecting Copy. This will copy all the contacts in that group into the clipboard, which can then be pasted into any app.</span></span>

-   <span data-ttu-id="14862-114">Puede usar el cmdlet [Export-CsUserData](https://docs.microsoft.com/es-ES/powershell/module/skype/export-csuserdata) para exportar los datos.</span><span class="sxs-lookup"><span data-stu-id="14862-114">You can use the [Export-CsUserData](https://docs.microsoft.com/en-us/powershell/module/skype/export-csuserdata) cmdlet to export this data.</span></span>

<span data-ttu-id="14862-p104">El contenido cargado en reuniones (como documentos o archivos de PowerPoint) o el que se genera en una reunión (como la pizarra, los sondeos y las preguntas y respuestas) se almacena en el archivador. También puede exportarse si los usuarios finales inician sesión en una reunión que no ha caducado y descargan el contenido cargado o realizan capturas de pantalla en el caso del contenido generado.</span><span class="sxs-lookup"><span data-stu-id="14862-p104">Content uploaded into meetings (such as PowerPoint files or handouts) or content generated in a meeting (such as whiteboard, polls, or Q/A) is stored in the filer. This can also be exported if end users log back into any meeting that has not expired and download any uploaded content or take screenshots in the case of generated content.</span></span>

<span data-ttu-id="14862-p105">Las reuniones MeetNow que no están en el calendario de Exchange, la lista de contactos y los derechos de contactos (familia, compañeros de trabajo, etc.) están en la base de datos de usuario. En Lync Server 2013 y versiones posteriores, puede usar el cmdlet [Export-CsUserData](https://docs.microsoft.com/es-ES/powershell/module/skype/export-csuserdata) para exportar los datos.</span><span class="sxs-lookup"><span data-stu-id="14862-p105">MeetNow meetings that are not in the Exchange Calendar and Contact List and contact rights (family, co-worker, etc.) are in the User Database. In Lync Server 2013 and later, you can use the [Export-CsUserData](https://docs.microsoft.com/en-us/powershell/module/skype/export-csuserdata) cmdlet to export this data.</span></span>
