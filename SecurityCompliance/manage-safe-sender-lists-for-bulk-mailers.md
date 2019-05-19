---
title: Administrar listas de remitentes seguros para troyanos de envío masivo de correo electrónico
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 11/17/2014
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: d48db4a3-9fbe-45e2-bbaa-1017ffdf96f8
ms.collection:
- M365-security-compliance
description: 'Si quiere usar listas de remitentes seguros, debe saber que Exchange Online Protection (EOP) y Outlook llevan a cabo el procesamiento de manera diferente. El servicio respeta los remitentes y los dominios seguros al inspeccionar la dirección RFC 5321.MailFrom y la dirección RFC 5322.From, mientras que Outlook agrega la dirección RFC 5322.From a la lista de remitentes seguros de un usuario. (Nota: El servicio inspecciona tanto la dirección 5321.MailFrom como la dirección 5322.From en busca de remitentes y dominios bloqueados).'
ms.openlocfilehash: 198697ad9ff4967ba55e138eb177095b355f97d2
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/17/2019
ms.locfileid: "34155662"
---
# <a name="manage-safe-sender-lists-for-bulk-mailers"></a><span data-ttu-id="54517-105">Administrar listas de remitentes seguros para troyanos de envío masivo de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="54517-105">Manage safe sender lists for bulk mailers</span></span>

<span data-ttu-id="54517-106">Si quiere usar listas de remitentes seguros, debe saber que Exchange Online Protection (EOP) y Outlook llevan a cabo el procesamiento de manera diferente.</span><span class="sxs-lookup"><span data-stu-id="54517-106">If you want to use safe sender lists, you should know that Exchange Online Protection (EOP) and Outlook handle processing differently.</span></span> <span data-ttu-id="54517-107">El servicio de Office 365 respeta a los remitentes y dominios seguros mediante la inspección de la dirección RFC 5321. MailFrom y la dirección RFC 5322. from, mientras que Outlook agrega la 5322 de RFC. from a la lista de remitentes seguros de un usuario.</span><span class="sxs-lookup"><span data-stu-id="54517-107">The Office 365 service respects safe senders and domains by inspecting the RFC 5321.MailFrom address and the RFC 5322.From address, while Outlook adds the RFC 5322.From address to a user's safe sender list.</span></span> <span data-ttu-id="54517-108">(Nota: El servicio inspecciona tanto la dirección 5321.MailFrom como la dirección 5322.From en busca de remitentes y dominios bloqueados).</span><span class="sxs-lookup"><span data-stu-id="54517-108">(Note: The service inspects both the 5321.MailFrom address and 5322.From address for blocked senders and domains.)</span></span>
  
<span data-ttu-id="54517-p103">La dirección CORREO SMTP DE, también conocida como dirección RFC 5321.MailFrom, es la dirección de correo electrónico que se usa para realizar comprobaciones de SPF, y si el correo no se puede entregar, se proporciona la ruta de acceso a la que se rechaza el mensaje. Se trata de la dirección de correo electrónico que se coloca en Return-Path en los encabezados de mensaje de forma predeterminada, aunque es posible que el remitente designe una dirección de Return-Path diferente.</span><span class="sxs-lookup"><span data-stu-id="54517-p103">The SMTP MAIL FROM address, otherwise known as the RFC 5321.MailFrom address, is the email address that's used to perform SPF checks, and if the mail can't be delivered, the path to which the bounced message is delivered. It's this email address that is placed into the Return-Path in the message headers by default, though it's possible for the sender to designate a different Return-Path address.</span></span>
  
<span data-ttu-id="54517-111">La dirección De: en los encabezados de los mensajes, también conocida como la dirección RFC 5322.From, es la dirección de correo electrónico que se muestra en el cliente de correo como Outlook.</span><span class="sxs-lookup"><span data-stu-id="54517-111">The From: address in the message headers, otherwise known as the RFC 5322.From address, is the email address that is displayed in the mail client such as Outlook.</span></span>
  
<span data-ttu-id="54517-p104">La mayoría de las veces las direcciones 5321.MailFrom y 5322.From son las mismas. Esto es típico para la comunicación de persona a persona. No obstante, cuando el correo electrónico se envía en nombre de otra persona, las direcciones son frecuentemente diferentes. Esto generalmente ocurre con mucha frecuencia en mensajes de correo masivos.</span><span class="sxs-lookup"><span data-stu-id="54517-p104">Much of the time, the 5321.MailFrom and 5322.From addresses are the same. This is typical for person-to-person communication. However, when email is sent on behalf of someone else, the addresses are frequently different. This usually happens most often for bulk email messages.</span></span>
  
<span data-ttu-id="54517-116">Por ejemplo, supongamos que la aerolínea Blue Yonder Airlines ha contratado a Margie's Travel para que distribuya su publicidad mediante correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="54517-116">For example, suppose that the airline Blue Yonder Airlines has contracted out Margie's Travel to send out its email advertising.</span></span> <span data-ttu-id="54517-117">Luego, obtiene un mensaje en su bandeja de entrada del remitente blueyonder@news.blueyonderairlines.com.</span><span class="sxs-lookup"><span data-stu-id="54517-117">You then get a message in your inbox from sender blueyonder@news.blueyonderairlines.com.</span></span> <span data-ttu-id="54517-118">En este caso, la dirección 5321. MailFrom es blueyonder.airlines@margiestravel.com y blueyonder@news.blueyonderairlines.com es la dirección 5322. from que es la que se ve en Outlook.</span><span class="sxs-lookup"><span data-stu-id="54517-118">In this case, 5321.MailFrom address is blueyonder.airlines@margiestravel.com, and blueyonder@news.blueyonderairlines.com is the 5322.From address which is the one, you see in Outlook.</span></span> <span data-ttu-id="54517-119">Debido a que el servicio respeta la dirección de RFC 5322. from, para evitar que se filtre este mensaje, puede Agregar la dirección RFC 5322. from como remitente seguro en Outlook (como un usuario) o, si es un administrador, configurar una regla de flujo de correo, tal como se muestra en el [anti-spam Sección protección](anti-spam-protection.md) .</span><span class="sxs-lookup"><span data-stu-id="54517-119">Because the service respects the RFC 5322.From address, to prevent this message from getting filtered, you can add the RFC 5322.From address as a safe sender in Outlook (as a user) or, if you're an administrator set up a mailflow rule as shown on the [Anti-spam Protection](anti-spam-protection.md) section.</span></span>
  

