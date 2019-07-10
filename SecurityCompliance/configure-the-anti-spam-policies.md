---
title: Configurar las directivas contra correo electrónico no deseado
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 6/9/2015
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 31279431-828d-48bd-b979-20b6de15fa4a
ms.collection:
- M365-security-compliance
description: El filtrado de correo no deseado se habilita automáticamente en toda la compañía con las directivas de correo no deseado predeterminadas (filtro de conexión, filtro de correo no deseado y correo no deseado saliente). Como administrador, puede ver y editar, y no eliminar, las directivas contra correo no deseado predeterminadas para que se adapten mejor a las necesidades de la organización. Para mayor granularidad, también puede crear directivas de filtro de correo no deseado personalizadas y aplicarlas a determinados usuarios, grupos o dominios de la organización. De manera predeterminada, las directivas personalizadas tienen prioridad sobre las directivas predeterminadas, pero esta prioridad se puede cambiar.
ms.openlocfilehash: f6690ddf0f50762aaa7b9ff61385c279f66716c8
ms.sourcegitcommit: 32ecff689ae32c59a39b7633ca0f36a304e7516e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/09/2019
ms.locfileid: "35600116"
---
# <a name="configure-the-anti-spam-policies"></a><span data-ttu-id="7d2c6-106">Configurar las directivas contra correo electrónico no deseado</span><span class="sxs-lookup"><span data-stu-id="7d2c6-106">Configure the anti-spam policies</span></span>

<span data-ttu-id="7d2c6-p102">El filtrado de correo no deseado se habilita automáticamente en toda la compañía con las directivas de correo no deseado predeterminadas (filtro de conexión, filtro de correo no deseado y correo no deseado saliente). Como administrador, puede ver y editar, y no eliminar, las directivas contra correo no deseado predeterminadas para que se adapten mejor a las necesidades de la organización. Para mayor granularidad, también puede crear directivas de filtro de correo no deseado personalizadas y aplicarlas a determinados usuarios, grupos o dominios de la organización. De manera predeterminada, las directivas personalizadas tienen prioridad sobre las directivas predeterminadas, pero esta prioridad se puede cambiar.</span><span class="sxs-lookup"><span data-stu-id="7d2c6-p102">Spam filtering is automatically enabled company-wide through the default anti-spam policies (connection filter, spam filter, and outbound spam). As an administrator, you can view and edit, but not delete, the default anti-spam policies so that they are tailored to best meet the needs of your organization. For greater granularity, you can also create custom policies and apply them to specified users, groups, or domains in your organization. By default, custom policies take precedence over the default policy, but you can change the priority of your policies.</span></span> 
  
<span data-ttu-id="7d2c6-111">Para obtener más información acerca de la configuración de políticas contra correo no deseado, consulte los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="7d2c6-111">For more about configuring your anti-spam policies, see the following topics:</span></span>
  
[<span data-ttu-id="7d2c6-112">Configurar la directiva de filtro de conexión</span><span class="sxs-lookup"><span data-stu-id="7d2c6-112">Configure the connection filter policy</span></span>](configure-the-connection-filter-policy.md)
  
[<span data-ttu-id="7d2c6-113">Configurar las directivas de filtro de correo no deseado</span><span class="sxs-lookup"><span data-stu-id="7d2c6-113">Configure your spam filter policies</span></span>](configure-your-spam-filter-policies.md)
  
> [!IMPORTANT]
> <span data-ttu-id="7d2c6-114">Para clientes independientes de EOP: De manera predeterminada, los filtros de contenido de EOP envían mensajes detectados como correo no deseado a la carpeta Correo electrónico no deseado del destinatario.</span><span class="sxs-lookup"><span data-stu-id="7d2c6-114">For EOP standalone customers: By default, the EOP content filters send spam-detected messages to each recipients' Junk Email folder.</span></span> <span data-ttu-id="7d2c6-115">Sin embargo, para asegurarse de que la acción **mover el mensaje a la carpeta correo no deseado** funcionará con los buzones locales, debe configurar dos reglas de flujo de correo de Exchange (también conocidas como reglas de transporte) en los servidores locales para detectar los encabezados de correo no deseado agregados por EOP.</span><span class="sxs-lookup"><span data-stu-id="7d2c6-115">However, in order to ensure that the **Move message to Junk Email folder** action will work with on-premises mailboxes, you must configure two Exchange mail flow rules (also known as transport rules) on your on-premises servers to detect spam headers added by EOP.</span></span> <span data-ttu-id="7d2c6-116">Para más información, consulte [Asegurarse de que el correo no deseado se enruta a la carpeta de correo no deseado de cada usuario](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md).</span><span class="sxs-lookup"><span data-stu-id="7d2c6-116">For details, see [Ensure that spam is routed to each user's Junk Email folder](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md).</span></span> 
  
[<span data-ttu-id="7d2c6-117">Configurar la directiva de correo no deseado saliente</span><span class="sxs-lookup"><span data-stu-id="7d2c6-117">Configure the outbound spam policy</span></span>](configure-the-outbound-spam-policy.md)
  

