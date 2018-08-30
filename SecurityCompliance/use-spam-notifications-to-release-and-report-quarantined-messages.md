---
title: Usar notificaciones de correo no deseado para el usuario para liberar y notificar mensajes de correo en cuarentena en Office 365
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 5/12/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 56de4ed5-b0aa-4195-9f46-033d7cc086bc
description: Si su administrador habilita las notificaciones para los usuarios, recibirá un mensaje de notificación que se enumera los mensajes enviados a su buzón de correo que se han identificado como correo no deseado, masiva o los mensajes de suplantación de identidad. Puede liberar o notificar mensajes después de que se le notifique.
ms.openlocfilehash: e355a94af5ac295503a8e205b1a896afc1c54fb6
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22535942"
---
# <a name="use-user-spam-notifications-to-release-and-report-quarantined-messages-in-office-365"></a><span data-ttu-id="b92b6-104">Usar notificaciones de correo no deseado para el usuario para liberar y notificar mensajes de correo en cuarentena en Office 365</span><span class="sxs-lookup"><span data-stu-id="b92b6-104">Use user spam notifications to release and report quarantined messages in Office 365</span></span>

<span data-ttu-id="b92b6-105">Si su administrador habilita las notificaciones de spam para los usuarios, recibirá un mensaje de notificación que se enumera los mensajes dirigidos a su buzón de correo que se han identificado como correo no deseado y puesto en cuarentena en su lugar.</span><span class="sxs-lookup"><span data-stu-id="b92b6-105">If your admin enables spam notifications for users, you'll receive a notification message that lists messages addressed to your mailbox that were identified as spam and quarantined instead.</span></span>
  
> [!TIP]
> <span data-ttu-id="b92b6-106">Si es un administrador y desea habilitar esta característica, puede elegir la opción al [modificar una directiva contra correo no deseado de forma predeterminada](https://go.microsoft.com/fwlink/?LinkId=800313).</span><span class="sxs-lookup"><span data-stu-id="b92b6-106">If you're an administrator and want to enable this feature, you can choose the option when you [modify a default anti-spam policy](https://go.microsoft.com/fwlink/?LinkId=800313).</span></span> 
  
<span data-ttu-id="b92b6-p102">El mensaje que recibe incluye el número de mensajes en cuarentena de correo no deseado que tiene, y la fecha y hora (en hora Universal coordinada o UTC) del último mensaje en la lista. La lista incluye los siguientes elementos para cada mensaje:</span><span class="sxs-lookup"><span data-stu-id="b92b6-p102">The message you receive includes the number of spam-quarantined messages you have, and the date and time (in Universal Coordinated Time or UTC) of the last message in the list. The list includes the following for each message:</span></span>
  
- <span data-ttu-id="b92b6-109">**Remitente** El nombre y correo electrónico dirección de envío del mensaje en cuarentena.</span><span class="sxs-lookup"><span data-stu-id="b92b6-109">**Sender** The send name and email address of the quarantined message.</span></span> 
    
- <span data-ttu-id="b92b6-110">**Asunto** El texto de la línea de asunto del mensaje en cuarentena.</span><span class="sxs-lookup"><span data-stu-id="b92b6-110">**Subject** The subject line text of the quarantined message.</span></span> 
    
- <span data-ttu-id="b92b6-111">**Fecha** La fecha y hora (en UTC) en que el mensaje fue colocado en cuarentena.</span><span class="sxs-lookup"><span data-stu-id="b92b6-111">**Date** The date and time (in UTC) that the message was quarantined.</span></span> 
    
- <span data-ttu-id="b92b6-112">**Tamaño** El tamaño del mensaje, en kilobytes (KB).</span><span class="sxs-lookup"><span data-stu-id="b92b6-112">**Size** The size of the message, in kilobytes (KBs).</span></span> 
    
<span data-ttu-id="b92b6-113">Actualmente, hay dos acciones que puede realizar con un mensaje en cuarentena:</span><span class="sxs-lookup"><span data-stu-id="b92b6-113">Currently, there are two actions you can take with a quarantined message:</span></span>
  
- <span data-ttu-id="b92b6-114">**Versión en bandeja de entrada** Elija esta opción para enviar el mensaje a la Bandeja de entrada, donde puede verlo.</span><span class="sxs-lookup"><span data-stu-id="b92b6-114">**Release to Inbox** Choose this to send the message to your inbox, where you can view it.</span></span> 
    
- <span data-ttu-id="b92b6-p103">**Informe como no deseado** Elija esta opción para enviar una copia del mensaje a Microsoft para su análisis. El equipo de spam se evalúa y analiza el mensaje y, dependiendo de los resultados del análisis, ajusta las reglas de filtro contra correo no deseado para permitir que el mensaje a través de.</span><span class="sxs-lookup"><span data-stu-id="b92b6-p103">**Report as Not Junk** Choose this to send a copy of the message to Microsoft for analysis. The spam team evaluates and analyzes the message, and, depending on the results of the analysis, adjusts the anti-spam filter rules to allow the message through.</span></span> 
    
<span data-ttu-id="b92b6-117">Tenga en cuenta de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="b92b6-117">Be aware of the following:</span></span>
  
- <span data-ttu-id="b92b6-p104">Los mensajes que están en cuarentena debido a que coincide con una regla de flujo de correo no se incluyen en los mensajes en cuarentena de usuario. Se muestran sólo los mensajes en cuarentena de correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="b92b6-p104">Messages that are quarantined because they matched a mail flow rule are not included in user quarantined messages. Only spam-quarantined messages are listed.</span></span>
    
- <span data-ttu-id="b92b6-120">Únicamente puede liberar un mensaje e identificarlo como un falso positivo (deseado) una vez.</span><span class="sxs-lookup"><span data-stu-id="b92b6-120">You can only release a message and report it as a false positive (not junk) once.</span></span>
    

