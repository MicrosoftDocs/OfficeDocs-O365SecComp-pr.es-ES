---
title: Usar notificaciones de correo no deseado para el usuario para liberar y notificar mensajes de correo en cuarentena en Office 365
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 5/12/2018
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 56de4ed5-b0aa-4195-9f46-033d7cc086bc
description: Si el administrador habilita las notificaciones para los usuarios, recibirá un mensaje de notificación que enumera los mensajes enviados a su buzón que se identificaron como correo no deseado, en masa o de suplantación de identidad. Puede liberar o informar de los mensajes después de recibir la notificación.
ms.openlocfilehash: eb51d8f73ff00781b74cfba4e580668710ce7a76
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/23/2019
ms.locfileid: "30216400"
---
# <a name="use-user-spam-notifications-to-release-and-report-quarantined-messages-in-office-365"></a><span data-ttu-id="5ca7c-104">Usar notificaciones de correo no deseado para el usuario para liberar y notificar mensajes de correo en cuarentena en Office 365</span><span class="sxs-lookup"><span data-stu-id="5ca7c-104">Use user spam notifications to release and report quarantined messages in Office 365</span></span>

<span data-ttu-id="5ca7c-105">Si su administrador habilita las notificaciones de correo no deseado para los usuarios, recibirá un mensaje de notificación que enumera los mensajes dirigidos a su buzón que se identificaron como correo no deseado y que se ponen en cuarentena en su lugar.</span><span class="sxs-lookup"><span data-stu-id="5ca7c-105">If your admin enables spam notifications for users, you'll receive a notification message that lists messages addressed to your mailbox that were identified as spam and quarantined instead.</span></span>
  
> [!TIP]
> <span data-ttu-id="5ca7c-106">Si es administrador y desea habilitar esta característica, puede elegir la opción cuando [modifique una directiva contra correo no deseado predeterminada](https://go.microsoft.com/fwlink/?LinkId=800313).</span><span class="sxs-lookup"><span data-stu-id="5ca7c-106">If you're an administrator and want to enable this feature, you can choose the option when you [modify a default anti-spam policy](https://go.microsoft.com/fwlink/?LinkId=800313).</span></span> 
  
<span data-ttu-id="5ca7c-p102">El mensaje que recibe incluye el número de mensajes de correo no deseado en cuarentena que tiene, y la fecha y la hora (en UTC universal coordinada o UTC) del último mensaje de la lista. En la lista se incluyen los siguientes elementos para cada mensaje:</span><span class="sxs-lookup"><span data-stu-id="5ca7c-p102">The message you receive includes the number of spam-quarantined messages you have, and the date and time (in Universal Coordinated Time or UTC) of the last message in the list. The list includes the following for each message:</span></span>
  
- <span data-ttu-id="5ca7c-109">**Remitente** El nombre de envío y la dirección de correo electrónico del mensaje en cuarentena.</span><span class="sxs-lookup"><span data-stu-id="5ca7c-109">**Sender** The send name and email address of the quarantined message.</span></span> 
    
- <span data-ttu-id="5ca7c-110">**Asunto** El texto de la línea de asunto del mensaje en cuarentena.</span><span class="sxs-lookup"><span data-stu-id="5ca7c-110">**Subject** The subject line text of the quarantined message.</span></span> 
    
- <span data-ttu-id="5ca7c-111">**Fecha** La fecha y hora (en UTC) en que el mensaje fue colocado en cuarentena.</span><span class="sxs-lookup"><span data-stu-id="5ca7c-111">**Date** The date and time (in UTC) that the message was quarantined.</span></span> 
    
- <span data-ttu-id="5ca7c-112">**Tamaño** El tamaño del mensaje, en kilobytes (KB).</span><span class="sxs-lookup"><span data-stu-id="5ca7c-112">**Size** The size of the message, in kilobytes (KBs).</span></span> 
    
<span data-ttu-id="5ca7c-113">Actualmente, hay dos acciones que puede llevar a cabo con un mensaje en cuarentena:</span><span class="sxs-lookup"><span data-stu-id="5ca7c-113">Currently, there are two actions you can take with a quarantined message:</span></span>
  
- <span data-ttu-id="5ca7c-114">**Liberar a bandeja de entrada** Elija esta opción para enviar el mensaje a su bandeja de entrada, donde puede verlo.</span><span class="sxs-lookup"><span data-stu-id="5ca7c-114">**Release to Inbox** Choose this to send the message to your inbox, where you can view it.</span></span> 
    
- <span data-ttu-id="5ca7c-p103">**Informar como correo deseado** Elija esta opción para enviar una copia del mensaje a Microsoft para su análisis. El equipo de correo no deseado evalúa y analiza el mensaje y, según los resultados del análisis, ajusta las reglas de filtro contra correo no deseado para permitir el paso del mensaje.</span><span class="sxs-lookup"><span data-stu-id="5ca7c-p103">**Report as Not Junk** Choose this to send a copy of the message to Microsoft for analysis. The spam team evaluates and analyzes the message, and, depending on the results of the analysis, adjusts the anti-spam filter rules to allow the message through.</span></span> 
    
<span data-ttu-id="5ca7c-117">Tenga en cuenta lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="5ca7c-117">Be aware of the following:</span></span>
  
- <span data-ttu-id="5ca7c-p104">Los mensajes que se ponen en cuarentena debido a que coinciden con una regla de flujo de correo no se incluyen en los mensajes de usuario en cuarentena. Solo se muestran los mensajes de correo no deseado en cuarentena.</span><span class="sxs-lookup"><span data-stu-id="5ca7c-p104">Messages that are quarantined because they matched a mail flow rule are not included in user quarantined messages. Only spam-quarantined messages are listed.</span></span>
    
- <span data-ttu-id="5ca7c-120">Únicamente puede liberar un mensaje e identificarlo como un falso positivo (deseado) una vez.</span><span class="sxs-lookup"><span data-stu-id="5ca7c-120">You can only release a message and report it as a false positive (not junk) once.</span></span>
    

