---
title: Niveles de confianza de correo no deseado
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 10/2/2017
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 34681000-0022-4b92-b38a-e32b3ed96bf6
ms.collection:
- M365-security-compliance
description: A cada mensaje de correo electrónico que pasa por el filtrado de correo no deseado se le asigna una puntuación de correo no deseado. La puntuación se asigna a una clasificación de nivel de confianza contra correo no deseado (SCL) individual y se marca en un encabezado X. El servicio realiza acciones en los mensajes según la interpretación de la confianza contra correo no deseado de las clasificaciones de SCL. La tabla siguiente muestra cómo las distintas clasificaciones de SCL se interpretan en los filtros y la acción predeterminada que se realiza en los mensajes entrantes por cada clasificación.
ms.openlocfilehash: e7e8e29a7c3d4a3f09d674f72a400d27746e9081
ms.sourcegitcommit: 48fa456981b5c52ab8aeace173c8366b9f36723b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2019
ms.locfileid: "30341251"
---
# <a name="spam-confidence-levels"></a><span data-ttu-id="4cb7a-106">Niveles de confianza de correo no deseado</span><span class="sxs-lookup"><span data-stu-id="4cb7a-106">Spam confidence levels</span></span>

<span data-ttu-id="4cb7a-p102">A cada mensaje de correo electrónico que pasa por el filtrado de correo no deseado se le asigna una puntuación de correo no deseado. La puntuación se asigna a una clasificación de nivel de confianza contra correo no deseado (SCL) individual y se marca en un encabezado X. El servicio realiza acciones en los mensajes según la interpretación de la confianza contra correo no deseado de las clasificaciones de SCL. La tabla siguiente muestra cómo las distintas clasificaciones de SCL se interpretan en los filtros y la acción predeterminada que se realiza en los mensajes entrantes por cada clasificación.</span><span class="sxs-lookup"><span data-stu-id="4cb7a-p102">When an email message goes through spam filtering it is assigned a spam score. That score is mapped to an individual Spam Confidence Level (SCL) rating and stamped in an X-header. The service takes actions upon the messages depending upon the spam confidence interpretation of the SCL rating. The following table shows how the different SCL ratings are interpreted by the filters and the default action that is taken on inbound messages for each rating.</span></span>
  
|<span data-ttu-id="4cb7a-111">**Clasificación de SCL**</span><span class="sxs-lookup"><span data-stu-id="4cb7a-111">**SCL Rating**</span></span>|<span data-ttu-id="4cb7a-112">**Interpretación de confianza de correo no deseado**</span><span class="sxs-lookup"><span data-stu-id="4cb7a-112">**Spam Confidence Interpretation**</span></span>|<span data-ttu-id="4cb7a-113">**Acción predeterminada**</span><span class="sxs-lookup"><span data-stu-id="4cb7a-113">**Default Action**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="4cb7a-114">-1</span><span class="sxs-lookup"><span data-stu-id="4cb7a-114">-1</span></span>|<span data-ttu-id="4cb7a-115">Correo no deseado procedente de un remitente seguro, un destinatario seguro o una dirección IP de lista segura (asociado de confianza).</span><span class="sxs-lookup"><span data-stu-id="4cb7a-115">Non-spam coming from a safe sender, safe recipient, or safe listed IP address (trusted partner).</span></span>|<span data-ttu-id="4cb7a-116">Se entrega el mensaje a la bandeja de entrada de los destinatarios.</span><span class="sxs-lookup"><span data-stu-id="4cb7a-116">Deliver the message to the recipients' inbox.</span></span>|
|<span data-ttu-id="4cb7a-117">0, 1</span><span class="sxs-lookup"><span data-stu-id="4cb7a-117">0, 1</span></span>|<span data-ttu-id="4cb7a-118">Correo electrónico no deseado porque el mensaje se examinó y se determinó como limpio.</span><span class="sxs-lookup"><span data-stu-id="4cb7a-118">Non-spam because the message was scanned and determined to be clean.</span></span>|<span data-ttu-id="4cb7a-119">Se entrega el mensaje a la bandeja de entrada de los destinatarios.</span><span class="sxs-lookup"><span data-stu-id="4cb7a-119">Deliver the message to the recipients' inbox.</span></span>|
|<span data-ttu-id="4cb7a-120">5, 6</span><span class="sxs-lookup"><span data-stu-id="4cb7a-120">5, 6</span></span>|<span data-ttu-id="4cb7a-121">Correo no deseado</span><span class="sxs-lookup"><span data-stu-id="4cb7a-121">Spam</span></span>|<span data-ttu-id="4cb7a-122">El mensaje se entrega a la carpeta de Correo no deseado de los destinatarios.</span><span class="sxs-lookup"><span data-stu-id="4cb7a-122">Deliver the message to the recipients' Junk Email folder.</span></span>|
|<span data-ttu-id="4cb7a-123">7, 8, 9</span><span class="sxs-lookup"><span data-stu-id="4cb7a-123">7, 8, 9</span></span>|<span data-ttu-id="4cb7a-124">Correo no deseado de alta confianza</span><span class="sxs-lookup"><span data-stu-id="4cb7a-124">High confidence spam</span></span>|<span data-ttu-id="4cb7a-125">El mensaje se entrega a la carpeta de Correo no deseado de los destinatarios.</span><span class="sxs-lookup"><span data-stu-id="4cb7a-125">Deliver the message to the recipients' Junk Email folder.</span></span>|
   
> [!TIP]
> <span data-ttu-id="4cb7a-p103">El servicio no establece las clasificaciones de SCL de 2, 3, 4, 7 y 8. Una clasificación de SCL de 5 o 6 se considera correo no deseado sospechoso, que es menos seguro que el correo no deseado que una clasificación SCL de 9, que se considera cierto correo no deseado. Las diferentes acciones de correo no deseado y correo no deseado de alta confianza se pueden configurar a través de las directivas de filtro de contenido en el centro de administración de Exchange. Para obtener más información, consulte [configurar las directivas de filtro de correo no deseado](configure-your-spam-filter-policies.md). También puede establecer la clasificación SCL para los mensajes que coinciden con condiciones específicas usando reglas de flujo de correo (también conocidas como reglas de transporte), como se describe en [usar reglas de flujo de correo para establecer el nivel de confianza contra correo no deseado (SCL) en los mensajes](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md). Si usa una regla de flujo de correo para establecer SCL de 7, 8 o 9, el mensaje se considerará correo no deseado de confianza alta.</span><span class="sxs-lookup"><span data-stu-id="4cb7a-p103">SCL ratings of 2, 3, 4, 7, and 8 are not set by the service. An SCL rating of 5 or 6 is considered suspected spam, which is less certain to be spam than an SCL rating of 9, which is considered certain spam. Different actions for spam and high confidence spam can be configured via your content filter policies in the Exchange admin center. For more information, see [Configure your spam filter policies](configure-your-spam-filter-policies.md). You can also set the SCL rating for messages that match specific conditions by using mail flow rules (also known as transport rules), as described in [Use mail flow rules to set the spam confidence level (SCL) in messages](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md). If you use a mail flow rule to set SCL of 7, 8, or 9 the message will be treated as high confidence spam.</span></span> 
  
||
|:-----|
|<span data-ttu-id="4cb7a-p104">![El icono reducido de LinkedIn Learning](media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **¿Es la primera vez que usa Office 365?**         LinkedIn Learning pone a su disposición vídeos gratuitos de cursos de **Office 365 admins and IT pros**.</span><span class="sxs-lookup"><span data-stu-id="4cb7a-p104">![The short icon for LinkedIn Learning](media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **New to Office 365?**         Discover free video courses for **Office 365 admins and IT pros**, brought to you by LinkedIn Learning.</span></span>|
   

