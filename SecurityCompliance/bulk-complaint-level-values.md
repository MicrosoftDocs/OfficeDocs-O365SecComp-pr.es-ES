---
title: Valores de nivel de queja de correo masivo
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 3/5/2015
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a5b03b3c-37dd-429e-8e9b-2c1b25031794
ms.collection:
- M365-security-compliance
description: Los remitentes de correo masivo varían en su envío de tterns, creación de contenido y prácticas de adquisición de listas. Algunos son buenos correos masivos que envían mensajes deseados con contenido relevante a sus suscriptores. Estos mensajes generan algunas quejas por parte de los destinatarios. Otros correos masivos envían mensajes no solicitados que se asemejan al correo no deseado y generan muchas quejas a los destinatarios. Para distinguir estos tipos de correo masivo, los mensajes de correo masivo tienen asignada una clasificación de nivel de queja masiva (BCL). Las clasificaciones de BCL van de 1 a 9, en función de la probabilidad de que el correo masivo genere quejas. Es probable que un remitente que tenga una clasificación de la cuenta de que se proenvíen muchas quejas a los destinatarios, mientras que la clasificación 3 es poco probable que genere muchas quejas. Microsoft usa orígenes internos y de terceros para identificar el correo masivo y determinar la BCL adecuada. Esta clasificación se expone en el encabezado X-Microsoft-antispam de cada mensaje. Para obtener más información acerca de este encabezado de mensaje, consulte anti-spam Message headers.
ms.openlocfilehash: 9947c0f36681126748e8617d67116c6932209760
ms.sourcegitcommit: a80bd8626720fabdf592b84e4424cd3a83d08280
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/23/2019
ms.locfileid: "30222929"
---
# <a name="bulk-complaint-level-values"></a><span data-ttu-id="f78ed-112">Valores de nivel de queja de correo masivo</span><span class="sxs-lookup"><span data-stu-id="f78ed-112">Bulk Complaint Level values</span></span>

<span data-ttu-id="f78ed-p102">Los troyanos de envío masivo de correo electrónico varían en sus patrones de envío, la creación de contenido y las prácticas de adquisición de listas. Algunos son buenos troyanos de envío de correo electrónico que envían mensajes deseados con contenido relevante a sus suscriptores. Estos mensajes generan pocas quejas por parte de los destinatarios. Otros troyanos de envío masivo de correo electrónico envían mensajes no solicitados muy similares al correo no deseado y generan muchas quejas por parte de los destinatarios. Para distinguir estos tipos de troyanos de envío masivo de correo, se asigna una clasificación de nivel de queja de correo masivo (BCL) a los troyanos de envío masivo de correo electrónico. Las clasificaciones de BCL oscilan entre 1 y 9, según la probabilidad con la que el troyano de envío masivo de correo electrónico generará quejas. Es probable que un remitente que tiene una clasificación 9 de BCL genere muchas quejas por parte de los destinatarios, mientras que es poco probable que una clasificación 3 de BCL genere muchas quejas. Microsoft usa fuentes internas y de terceros para identificar el correo masivo y determinar el BCL adecuado. Esta clasificación se expone en el encabezado **X-Microsoft-Antispam** de cada mensaje. Para obtener más información sobre este encabezado de mensaje, vea [Encabezados de mensajes de correo no deseado](anti-spam-message-headers.md).</span><span class="sxs-lookup"><span data-stu-id="f78ed-p102">Bulk mailers vary in their sending patterns, content creation, and list acquisition practices. Some are good bulk mailers that send wanted messages with relevant content to their subscribers. These messages generate few complaints from recipients. Other bulk mailers send unsolicited messages that closely resemble spam and generate many complaints from recipients. To distinguish these types of bulk mailers, messages from bulk mailers are assigned a Bulk Complaint Level (BCL) rating. BCL ratings range from 1 to 9 depending on how likely the bulk mailer is to generate complaints. A sender that has a rating of BCL 9 is likely to generate many complaints from recipients, whereas a rating of BCL 3 is unlikely to generate many complaints. Microsoft uses both internal and third-party sources to identify bulk mail and determine the appropriate BCL. This rating is exposed in the **X-Microsoft-Antispam** header of every message. For more information about this message header, see [Anti-spam message headers](anti-spam-message-headers.md).</span></span> 
  
<span data-ttu-id="f78ed-123">Para usar los valores de BCL a fin de establecer el nivel deseado de filtrado de correo masivo que requiere su organización, siga estos pasos en [Configurar las directivas de filtro de correo no deseado](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="f78ed-123">You can use BCL values to set the desired level of bulk filtering your organization requires by following the steps in [Configure your spam filter policies](configure-your-spam-filter-policies.md).</span></span>
  
<span data-ttu-id="f78ed-p103">Se están agregando más valores de BCL y se incluirán aquí en el futuro. En la tabla siguiente se enumeran y describen los valores de BCL que están actualmente en uso.</span><span class="sxs-lookup"><span data-stu-id="f78ed-p103">More BCL values are being added and will be included here in the future. The following table lists and describes the BCL values that are currently in use.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="f78ed-126">**Valor de BCL**</span><span class="sxs-lookup"><span data-stu-id="f78ed-126">**BCL Value**</span></span> <br/> |<span data-ttu-id="f78ed-127">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="f78ed-127">**Description**</span></span> <br/> |
|<span data-ttu-id="f78ed-128">comprendi</span><span class="sxs-lookup"><span data-stu-id="f78ed-128">0</span></span>  <br/> |<span data-ttu-id="f78ed-129">El mensaje no es de un remitente de correo masivo.</span><span class="sxs-lookup"><span data-stu-id="f78ed-129">The message isn't from a bulk sender.</span></span>  <br/> |
|<span data-ttu-id="f78ed-130">1, 2, 3</span><span class="sxs-lookup"><span data-stu-id="f78ed-130">1, 2, 3</span></span>  <br/> |<span data-ttu-id="f78ed-131">El mensaje proviene de un remitente de correo masivo que genera pocas quejas.</span><span class="sxs-lookup"><span data-stu-id="f78ed-131">The message is from a bulk sender that generates few complaints.</span></span>  <br/> |
|<span data-ttu-id="f78ed-132">4, 5, 6, 7</span><span class="sxs-lookup"><span data-stu-id="f78ed-132">4, 5, 6, 7</span></span>  <br/> |<span data-ttu-id="f78ed-133">El mensaje proviene de un remitente de correo masivo que genera un número mixto de quejas.</span><span class="sxs-lookup"><span data-stu-id="f78ed-133">The message is from a bulk sender that generates a mixed number of complaints.</span></span>  <br/> |
|<span data-ttu-id="f78ed-134">8, 9</span><span class="sxs-lookup"><span data-stu-id="f78ed-134">8, 9</span></span>  <br/> |<span data-ttu-id="f78ed-135">El mensaje proviene de un remitente de correo masivo que genera un número elevado de quejas.</span><span class="sxs-lookup"><span data-stu-id="f78ed-135">The message is from a bulk sender that generates a high number of complaints</span></span>  <br/> |
   

