---
title: Notificación de muestra cuando se bloquea a un remitente para enviar correo no deseado de salida
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 11/2/2017
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c33fd406-a4c8-4ac8-ad85-123996c5cded
description: 'Cuando se bloquea a un remitente en el servicio debido al envío de correo no deseado de salida, el administrador de dominio especificado al Configurar la directiva de correo no deseado saliente recibirá un correo electrónico de notificación similar al siguiente:'
ms.openlocfilehash: b9fcdf9c2f44a4446a678ca4b22a0a12b24b6fd4
ms.sourcegitcommit: e9dca2d6a7838f98bb7eca127fdda2372cda402c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/21/2018
ms.locfileid: "23003249"
---
# <a name="sample-notification-when-a-sender-is-blocked-sending-outbound-spam"></a><span data-ttu-id="e2861-103">Notificación de muestra cuando se bloquea a un remitente para enviar correo no deseado de salida</span><span class="sxs-lookup"><span data-stu-id="e2861-103">Sample notification when a sender is blocked sending outbound spam</span></span>

<span data-ttu-id="e2861-104">Cuando se bloquea a un remitente en el servicio debido al envío de correo no deseado de salida, el administrador de dominio especificado al [Configurar la directiva de correo no deseado saliente](configure-the-outbound-spam-policy.md) recibirá un correo electrónico de notificación similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="e2861-104">When a sender is blocked from the service due to sending outbound spam, the domain admin specified when you [Configure the outbound spam policy](configure-the-outbound-spam-policy.md) will receive a notification email similar to the following:</span></span> 
  
 <span data-ttu-id="e2861-105">**Dirección del remitente:** spamalerts@microsoft.com</span><span class="sxs-lookup"><span data-stu-id="e2861-105">**Sender address:** spamalerts@microsoft.com</span></span> 
  
 <span data-ttu-id="e2861-106">**Asunto:** Notificación de correo no deseado de salida: \<  *nombre de cuenta*  \> bloqueada para enviar correo saliente</span><span class="sxs-lookup"><span data-stu-id="e2861-106">**Subject:** Outbound spam notification - \<  *account name*  \> blocked from sending outbound mail</span></span> 
  
 <span data-ttu-id="e2861-107">**Cuerpo:** Esto es una respuesta automática desde el sistema de análisis de Exchange Online Protection correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="e2861-107">**Body:** This is an automated reply from the Exchange Online Protection Spam Analysis System.</span></span> 
  
<span data-ttu-id="e2861-p101">Se pone en contacto debido a que hemos detectado volúmenes de correo electrónico que se marcó como correo no deseado o cualquier otro comportamiento sospechoso, que se originan desde la organización. Las siguientes cuentas de correo electrónico que se haya bloqueado de envío de correo electrónico (aún pueden recibir correo electrónico):</span><span class="sxs-lookup"><span data-stu-id="e2861-p101">You are being contacted because we have detected high volumes of email marked as spam, or other suspicious behavior, originating from your organization. The following email accounts have been blocked from sending email (they can still receive email):</span></span>
  
<span data-ttu-id="e2861-110">\< *nombre de cuenta*  \></span><span class="sxs-lookup"><span data-stu-id="e2861-110">\< *account name*  \></span></span> 
  
<span data-ttu-id="e2861-p102">Es probable que esta cuenta de correo electrónico se ha puesto en peligro. Por favor, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="e2861-p102">It is likely that this email account has been compromised. Please follow these steps:</span></span>
  
1. <span data-ttu-id="e2861-113">Resolver este problema en su parte por:</span><span class="sxs-lookup"><span data-stu-id="e2861-113">Resolve this issue on your side by:</span></span>
    
  - <span data-ttu-id="e2861-114">Cambiar la contraseña de la cuenta.</span><span class="sxs-lookup"><span data-stu-id="e2861-114">Changing the password of the account.</span></span>
    
  - <span data-ttu-id="e2861-115">Determinación de cómo se ha puesto en peligro la cuenta.</span><span class="sxs-lookup"><span data-stu-id="e2861-115">Determining how the account was compromised.</span></span>
    
  - <span data-ttu-id="e2861-116">Tomando precauciones para asegurarse de que esta vulnerabilidad no se aproveche nuevo.</span><span class="sxs-lookup"><span data-stu-id="e2861-116">Taking precautions to ensure that this vulnerability will not be exploited again.</span></span>
    
  - <span data-ttu-id="e2861-117">Para confirmar que se ha borrado la cola de correo saliente de todos los mensajes ofensivos.</span><span class="sxs-lookup"><span data-stu-id="e2861-117">Confirming that your outbound mail queue has been cleared of all offending messages.</span></span>
    
2. <span data-ttu-id="e2861-118">Póngase en contacto con el soporte técnico de Microsoft mediante el uso de su canal de contacto regular.</span><span class="sxs-lookup"><span data-stu-id="e2861-118">Contact Microsoft support by using your regular contact channel.</span></span>
    
3. <span data-ttu-id="e2861-119">Explique que dispone de un usuario que está bloqueado el envío de correo y que el problema se ha dedicado a.</span><span class="sxs-lookup"><span data-stu-id="e2861-119">Explain that you have a user that is blocked from sending mail and that the problem has been dealt with.</span></span>
    
4. <span data-ttu-id="e2861-120">El agente creará un vale de soporte técnico con la información que proporcionan y pasar para que tiene la dirección de correo electrónico o dominio desbloqueado.</span><span class="sxs-lookup"><span data-stu-id="e2861-120">The agent will create a support ticket with the information that you provide and escalate it to have the email address or domain unblocked.</span></span>
    
5. <span data-ttu-id="e2861-121">Después de que se ha desbloqueado la dirección y no hay otros asuntos pendientes, se ponen en contacto y una alerta para el desbloqueo.</span><span class="sxs-lookup"><span data-stu-id="e2861-121">After the address has been unblocked, and pending no other issues, you will be contacted and alerted to the unblocking.</span></span>
    
<span data-ttu-id="e2861-122">Gracias por asistir a nosotros en el control de correo electrónico no deseado.</span><span class="sxs-lookup"><span data-stu-id="e2861-122">Thank you for assisting us in controlling unwanted email.</span></span>
  
<span data-ttu-id="e2861-123">Exchange Online Protection.</span><span class="sxs-lookup"><span data-stu-id="e2861-123">Exchange Online Protection.</span></span>
  
<span data-ttu-id="e2861-124">\*\*NOTA: no responda a este correo electrónico ya que se envía desde una dirección sin supervisar\*\*</span><span class="sxs-lookup"><span data-stu-id="e2861-124">\*\*NOTE - Please do not respond to this email as it is sent from an unmonitored address\*\*</span></span>
  
> [!TIP]
> <span data-ttu-id="e2861-125">También puede ponerse en contacto con soporte técnico a través de las opciones que se documentan en la [Ayuda y soporte técnico para EOP](eop/help-and-support-for-eop.md).</span><span class="sxs-lookup"><span data-stu-id="e2861-125">You can also contact support via the options documented at [Help and support for EOP](eop/help-and-support-for-eop.md).</span></span> 
  

