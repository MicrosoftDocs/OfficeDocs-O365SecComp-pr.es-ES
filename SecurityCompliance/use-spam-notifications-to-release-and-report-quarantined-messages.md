---
title: Usar notificaciones de correo no deseado para el usuario para liberar y notificar mensajes de correo en cuarentena en Office 365
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 03/14/2019
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 56de4ed5-b0aa-4195-9f46-033d7cc086bc
ms.collection:
- M365-security-compliance
description: Si el administrador habilita las notificaciones para los usuarios, recibirá un mensaje de notificación que enumera los mensajes enviados a su buzón que se identificaron como correo no deseado, en masa o de suplantación de identidad. Puede liberar o informar de los mensajes después de recibir la notificación.
ms.openlocfilehash: de67987b0028102bdf61889ce54ca4215182e279
ms.sourcegitcommit: 8657e003ab1ff49113f222d1ee8400eff174cb54
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/16/2019
ms.locfileid: "30638977"
---
# <a name="use-user-spam-notifications-to-release-and-report-quarantined-messages-in-office-365"></a><span data-ttu-id="4c3f6-104">Usar notificaciones de correo no deseado para el usuario para liberar y notificar mensajes de correo en cuarentena en Office 365</span><span class="sxs-lookup"><span data-stu-id="4c3f6-104">Use user spam notifications to release and report quarantined messages in Office 365</span></span>

<span data-ttu-id="4c3f6-105">Si su administrador habilita las notificaciones de correo no deseado para los usuarios, recibirá un mensaje de notificación que enumera los mensajes dirigidos a su buzón que se identificaron como correo no deseado y que se ponen en cuarentena en su lugar.</span><span class="sxs-lookup"><span data-stu-id="4c3f6-105">If your admin enables spam notifications for users, you'll receive a notification message that lists messages addressed to your mailbox that were identified as spam and quarantined instead.</span></span>
  
> [!TIP]
> <span data-ttu-id="4c3f6-106">Si es administrador y desea habilitar esta característica, puede elegir la opción cuando [modifique una directiva contra correo no deseado predeterminada](https://go.microsoft.com/fwlink/?LinkId=800313).</span><span class="sxs-lookup"><span data-stu-id="4c3f6-106">If you're an administrator and want to enable this feature, you can choose the option when you [modify a default anti-spam policy](https://go.microsoft.com/fwlink/?LinkId=800313).</span></span> 
  
<span data-ttu-id="4c3f6-107">El mensaje que recibe incluye el número de mensajes de correo no deseado en cuarentena que tiene, y la fecha y la hora (en UTC universal coordinada o UTC) del último mensaje de la lista.</span><span class="sxs-lookup"><span data-stu-id="4c3f6-107">The message you receive includes the number of spam-quarantined messages you have, and the date and time (in Universal Coordinated Time or UTC) of the last message in the list.</span></span> <span data-ttu-id="4c3f6-108">En la lista se incluyen los siguientes elementos para cada mensaje:</span><span class="sxs-lookup"><span data-stu-id="4c3f6-108">The list includes the following for each message:</span></span>
  
- <span data-ttu-id="4c3f6-109">**Remitente** El nombre de envío y la dirección de correo electrónico del mensaje en cuarentena.</span><span class="sxs-lookup"><span data-stu-id="4c3f6-109">**Sender** The send name and email address of the quarantined message.</span></span> 
    
- <span data-ttu-id="4c3f6-110">**Asunto** El texto de la línea de asunto del mensaje en cuarentena.</span><span class="sxs-lookup"><span data-stu-id="4c3f6-110">**Subject** The subject line text of the quarantined message.</span></span> 
    
- <span data-ttu-id="4c3f6-111">**Fecha** La fecha y hora (en UTC) en que el mensaje fue colocado en cuarentena.</span><span class="sxs-lookup"><span data-stu-id="4c3f6-111">**Date** The date and time (in UTC) that the message was quarantined.</span></span> 
    
- <span data-ttu-id="4c3f6-112">**Tamaño** El tamaño del mensaje, en kilobytes (KB).</span><span class="sxs-lookup"><span data-stu-id="4c3f6-112">**Size** The size of the message, in kilobytes (KBs).</span></span> 
    
<span data-ttu-id="4c3f6-113">Estas son las acciones que puede llevar a cabo con un mensaje en cuarentena:</span><span class="sxs-lookup"><span data-stu-id="4c3f6-113">These are the actions that you can take with a quarantined message:</span></span>

- <span data-ttu-id="4c3f6-114">**Obtenga una vista previa** del mensaje si desea obtener una vista previa del contenido o encabezado antes de llevar a cabo la acción.</span><span class="sxs-lookup"><span data-stu-id="4c3f6-114">**Preview** the message if you would like to preview the content or header prior to taking action.</span></span>

- <span data-ttu-id="4c3f6-115">**Descargue** el mensaje si desea revisar el mensaje y los datos adjuntos (si los hay) en el dispositivo antes de realizar la acción.</span><span class="sxs-lookup"><span data-stu-id="4c3f6-115">**Download** the message if you would like to review the message and attachments (if any) on your device prior to taking action.</span></span>

- <span data-ttu-id="4c3f6-116">**Release** si el mensaje no es correo no deseado y desea que Office 365 envíe el mensaje al buzón de correo.</span><span class="sxs-lookup"><span data-stu-id="4c3f6-116">**Release** if the message isn’t spam and you want Office 365 to send the message to your mailbox.</span></span>

- <span data-ttu-id="4c3f6-117">**Versión _AMP_ Permitir remitente** si el mensaje no es correo no deseado y desea que Office 365 agregue el remitente a la lista de remitentes seguros y destinatarios para futuros correos electrónicos.</span><span class="sxs-lookup"><span data-stu-id="4c3f6-117">**Release & Allow Sender** if the message isn’t spam and you want Office 365 to add the sender to your safe senders and recipients list for future emails.</span></span> <span data-ttu-id="4c3f6-118">Tenga en cuenta que el administrador puede tener otras configuraciones de permitir o bloquear de toda la organización que invaliden la lista de remitentes seguros.</span><span class="sxs-lookup"><span data-stu-id="4c3f6-118">Keep in mind that your admin may have other organization wide allow/block configurations that override your safe sender list.</span></span>

- <span data-ttu-id="4c3f6-119">**Publique el informe de &**, si el mensaje no es correo no deseado y desea enviar el mensaje al buzón e identificarlo en Microsoft para su análisis.</span><span class="sxs-lookup"><span data-stu-id="4c3f6-119">**Release & Report**, if the message isn’t spam and you want to send the message to your mailbox and report it to Microsoft for analysis.</span></span>

- <span data-ttu-id="4c3f6-120">**Bloquear** si desea que Office 365 agregue el remitente a la lista de remitentes bloqueados.</span><span class="sxs-lookup"><span data-stu-id="4c3f6-120">**Block** if you want Office 365 to add the sender to your blocked senders list.</span></span>

<span data-ttu-id="4c3f6-121">Tenga en cuenta lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="4c3f6-121">Be aware of the following:</span></span>
  
- <span data-ttu-id="4c3f6-122">Los mensajes que se ponen en cuarentena debido a que coinciden con una regla de flujo de correo no se incluyen en los mensajes de usuario en cuarentena.</span><span class="sxs-lookup"><span data-stu-id="4c3f6-122">Messages that are quarantined because they matched a mail flow rule are not included in user quarantined messages.</span></span> <span data-ttu-id="4c3f6-123">Solo se enumeran los mensajes en cuarentena de correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="4c3f6-123">Only spam-quarantined messages are listed.</span></span>
    
- <span data-ttu-id="4c3f6-124">Únicamente puede liberar un mensaje e identificarlo como un falso positivo (deseado) una vez.</span><span class="sxs-lookup"><span data-stu-id="4c3f6-124">You can only release a message and report it as a false positive (not junk) once.</span></span>
    

