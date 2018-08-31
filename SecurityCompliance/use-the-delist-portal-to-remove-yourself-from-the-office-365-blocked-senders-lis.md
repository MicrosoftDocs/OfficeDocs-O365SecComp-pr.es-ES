---
title: Usar el portal de eliminación de la lista para quitarse de la lista de remitentes bloqueados de Office 365
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 4/18/2016
ms.audience: ITPro
ms.topic: troubleshooting
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 0bcecdd4-3343-4cc0-9e58-e19d4de515e8
description: ¿Recibe un mensaje de error cuando intenta enviar un correo electrónico a un destinatario cuya dirección de correo electrónico está en Office 365? Si cree que no debería recibir este mensaje de error, use el portal de eliminación de la lista para quitarse de la lista de remitentes bloqueados de Office 365.
ms.openlocfilehash: 4964429f4d3aa1a585b1b543929f83c2cebfb9a4
ms.sourcegitcommit: e9dca2d6a7838f98bb7eca127fdda2372cda402c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/21/2018
ms.locfileid: "23003259"
---
# <a name="use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-list"></a><span data-ttu-id="f7518-104">Usar el portal de eliminación de la lista para quitarse de la lista de remitentes bloqueados de Office 365</span><span class="sxs-lookup"><span data-stu-id="f7518-104">Use the delist portal to remove yourself from the Office 365 blocked senders list</span></span>

<span data-ttu-id="f7518-p102">¿Recibe un mensaje de error cuando intenta enviar un correo electrónico a un destinatario cuya dirección de correo electrónico está en Office 365? Si cree que no debería recibir este mensaje de error, use el portal de eliminación de la lista para quitarse de la lista de remitentes bloqueados de Office 365.</span><span class="sxs-lookup"><span data-stu-id="f7518-p102">Are you getting an error message when you try to send an email to a recipient whose email address is in Office 365? If you think you should not be receiving the error message, you can use the delist portal to remove yourself from the Office 365 blocked senders list.</span></span>
  
## <a name="what-is-the-office-365-blocked-senders-list"></a><span data-ttu-id="f7518-107">¿Qué es la lista de remitentes bloqueados de Office 365?</span><span class="sxs-lookup"><span data-stu-id="f7518-107">What is the Office 365 blocked senders list?</span></span>

<span data-ttu-id="f7518-p103">Microsoft usa la lista de remitentes bloqueados para proteger a sus clientes contra el spam, la suplantación de identidad y los ataques de phishing. La dirección IP de su servidor de correo, es decir, la dirección que usa su servidor de correo para identificarse en Internet, se ha considerado como una amenaza potencial para Office 365 por uno de numerosos motivos. Cuando Office 365 agrega la dirección IP a la lista, evita todas las comunicaciones entre la dirección IP y cualquiera de nuestros clientes a través de nuestros centros de datos.</span><span class="sxs-lookup"><span data-stu-id="f7518-p103">Microsoft uses the blocked senders list to protect its customers from spam, spoofing, and phishing attacks. Your mail server's IP address, that is, the address your mail server uses to identify itself on the Internet, was tagged as a potential threat to Office 365 for one of a variety of reasons. When Office 365 adds the IP address to the list, it prevents all further communication between the IP address and any of our customers through our datacenters.</span></span>
  
<span data-ttu-id="f7518-111">Sabrá que lo hemos agregado a la lista cuando reciba una respuesta a un mensaje de correo que incluya un error similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="f7518-111">You will know you have been added to the list when you receive a response to a mail message that includes an error that looks something like this:</span></span>
  
<span data-ttu-id="f7518-p104">550 5.7.606-649 acceso denegado, prohibido enviar IP [_dirección IP_]; Para solicitar la eliminación de esta lista, visite https://sender.office.com/ y siga las instrucciones. Para obtener más información, consulte [informes de no entrega de correo electrónico en Office 365](http://go.microsoft.com/fwlink/?LinkID=526653).</span><span class="sxs-lookup"><span data-stu-id="f7518-p104">550 5.7.606-649 Access denied, banned sending IP [_IP address_]; To request removal from this list please visit https://sender.office.com/ and follow the directions. For more information please see [Email non-delivery reports in Office 365](http://go.microsoft.com/fwlink/?LinkID=526653).</span></span>
  
<span data-ttu-id="f7518-114">_IP address_ es la dirección IP del equipo en el que se ejecuta el servidor de correo.</span><span class="sxs-lookup"><span data-stu-id="f7518-114">where  _IP address_ is the IP address of the computer on which the mail server runs.</span></span> 
  
### <a name="to-use-the-office-365-delist-portal-to-remove-yourself-from-the-blocked-senders-list"></a><span data-ttu-id="f7518-115">Para usar el portal de eliminación de la lista de Office 365 para quitarse de la lista de remitentes bloqueados</span><span class="sxs-lookup"><span data-stu-id="f7518-115">To use the Office 365 delist portal to remove yourself from the blocked senders list</span></span>

1. <span data-ttu-id="f7518-116">En un explorador web, vaya a [https://sender.office.com](https://sender.office.com).</span><span class="sxs-lookup"><span data-stu-id="f7518-116">In a web browser, go to [https://sender.office.com](https://sender.office.com).</span></span>
    
2. <span data-ttu-id="f7518-p105">Siga las instrucciones que se indican en la página. Asegúrese de que usa la dirección de correo electrónico a la que se envió el mensaje de error, así como la dirección IP especificada en el mensaje de error. Solo se puede especificar una dirección de correo electrónico y una dirección IP por visita.</span><span class="sxs-lookup"><span data-stu-id="f7518-p105">Follow the instructions on the page. Ensure that you use the email address to which the error message was sent, and the IP address that is specified in the error message. You can only enter one email address and one IP address per visit.</span></span>
    
3. <span data-ttu-id="f7518-120">Haga clic en **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="f7518-120">Click **Submit**.</span></span>
    
    <span data-ttu-id="f7518-p106">El portal envía un correo electrónico a la dirección de correo electrónico que usted proporcione. El correo electrónico será similar a lo siguiente: ![captura de pantalla de correo electrónico recibido al enviar una solicitud a través del portal de delist](media/bf13e4f7-f68c-4e46-baa7-b6ab4cfc13f3.png)</span><span class="sxs-lookup"><span data-stu-id="f7518-p106">The portal sends an email to the email address that you supply. The email will look something like the following:  ![Screenshot of email received when you submit a request through the delist portal](media/bf13e4f7-f68c-4e46-baa7-b6ab4cfc13f3.png)</span></span>
  
4. <span data-ttu-id="f7518-123">Haga clic en el vínculo de confirmación que aparece en el correo electrónico que le ha enviado el portal de eliminación de la lista.</span><span class="sxs-lookup"><span data-stu-id="f7518-123">Click the confirmation link in the email sent to you by the delisting portal.</span></span>
    
    <span data-ttu-id="f7518-124">Regresará al portal de eliminación de la lista.</span><span class="sxs-lookup"><span data-stu-id="f7518-124">This brings you back to the delist portal.</span></span>
    
5. <span data-ttu-id="f7518-125">En el portal de eliminación de la lista, haga clic en **Quitar de la lista una IP**.</span><span class="sxs-lookup"><span data-stu-id="f7518-125">In the delist portal, click **Delist IP**.</span></span>
    
    <span data-ttu-id="f7518-p107">Después de quitar la dirección IP de la lista de remitentes bloqueados, los mensajes de correo electrónico que procedan de esa dirección IP se entregarán a los destinatarios que usen Office 365. Por lo tanto, asegúrese de que el correo electrónico enviado desde esa dirección IP no es ofensivo ni malintencionado; de lo contrario, es posible que se vuelva a bloquear la dirección IP.</span><span class="sxs-lookup"><span data-stu-id="f7518-p107">After the IP address is removed from the blocked senders list, email messages from that IP address will be delivered to recipients who use Office 365. So, make sure you're confident that email sent from that IP address won't be abusive or malicious; otherwise, the IP address might be blocked again.</span></span>
    

