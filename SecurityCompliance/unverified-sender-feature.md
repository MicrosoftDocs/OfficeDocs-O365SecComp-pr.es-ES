---
title: Identificación de mensajes sospechosos en Outlook.com y Outlook en la web
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 04/25/2019
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: Para evitar que los mensajes de suplantación de identidad lleguen a su buzón, Outlook.com y Outlook en la web Compruebe que el remitente es quien dice ser y marcar los mensajes sospechosos como correo no deseado.
ms.openlocfilehash: edba30bb2ac0f9dc6ebc12db957a518de0c1b543
ms.sourcegitcommit: 9907bebc5f225032f681c4952de0b0be2df278ac
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/26/2019
ms.locfileid: "33345930"
---
# <a name="identify-suspicious-messages-in-outlookcom-and-outlook-on-the-web"></a><span data-ttu-id="ec2b8-103">Identificación de mensajes sospechosos en Outlook.com y Outlook en la web</span><span class="sxs-lookup"><span data-stu-id="ec2b8-103">Identify suspicious messages in Outlook.com and Outlook on the web</span></span>

<span data-ttu-id="ec2b8-104">Para evitar que los mensajes de suplantación de identidad lleguen a su buzón, Outlook.com y Outlook en la web Compruebe que el remitente es quien dice ser y marcar los mensajes sospechosos como correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="ec2b8-104">To prevent phishing messages from reaching your mailbox, Outlook.com and Outlook on the web verify that the sender is who they say they are and mark suspicious messages as junk email.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ec2b8-105">Cuando un mensaje se marca como una estafa de suplantación de identidad (phishing), Outlook.com y Outlook en la web muestran una advertencia en la parte superior de la página, pero los vínculos del mensaje todavía se pueden abrir.</span><span class="sxs-lookup"><span data-stu-id="ec2b8-105">When a message is marked as a phishing scam, Outlook.com and Outlook on the web display a warning at the top of the page, but any links in the message can still be opened.</span></span>

## <a name="how-can-i-identify-a-suspicious-message-in-my-inbox"></a><span data-ttu-id="ec2b8-106">¿Cómo puedo identificar un mensaje sospechoso en mi bandeja de entrada?</span><span class="sxs-lookup"><span data-stu-id="ec2b8-106">How can I identify a suspicious message in my inbox?</span></span>

<span data-ttu-id="ec2b8-107">Outlook.com y Outlook en la web muestran indicadores cuando no se puede identificar el remitente de un mensaje o su identidad es diferente de la que se ve en la dirección de remitente.</span><span class="sxs-lookup"><span data-stu-id="ec2b8-107">Outlook.com and Outlook on the web show indicators when the sender of a message either can't be identified or their identity is different from what you see in the From address.</span></span>

### <a name="you-see-a--in-the-sender-image"></a><span data-ttu-id="ec2b8-108">Ve un '? ' en la imagen del remitente</span><span class="sxs-lookup"><span data-stu-id="ec2b8-108">You see a '?' in the sender image</span></span>

<span data-ttu-id="ec2b8-109">Cuando Outlook.com y Outlook en la web no pueden comprobar la identidad del remitente mediante técnicas de autenticación de correo electrónico, muestran un '? ' en la foto del remitente.</span><span class="sxs-lookup"><span data-stu-id="ec2b8-109">When Outlook.com and Outlook on the web can't verify the identity of the sender using email authentication techniques, they display a '?' in the sender photo.</span></span>

![El mensaje no pasó la comprobación](media/message-did-not-pass-verification.jpg)

<span data-ttu-id="ec2b8-111">No todos los mensajes que no se autentican son malintencionados.</span><span class="sxs-lookup"><span data-stu-id="ec2b8-111">Not every message that fails to authenticate is malicious.</span></span> <span data-ttu-id="ec2b8-112">Sin embargo, debe tener cuidado al interactuar con los mensajes que no se autentican si no reconoce al remitente.</span><span class="sxs-lookup"><span data-stu-id="ec2b8-112">However, you should be careful about interacting with messages that don't authenticate if you don't recognize the sender.</span></span> <span data-ttu-id="ec2b8-113">O bien, si reconoce a un remitente que normalmente no tiene un '? ' en la imagen del remitente, pero, de repente, lo empieza a ver, es posible que se trate de una firma en la que se está suplantando el remitente.</span><span class="sxs-lookup"><span data-stu-id="ec2b8-113">Or, if you recognize a sender that normally doesn't have a '?' in the sender image, but you suddenly start seeing it, that could be a sign the sender is being spoofed.</span></span>

### <a name="the-senders-address-is-different-than-what-appears-in-the-from-address"></a><span data-ttu-id="ec2b8-114">La dirección del remitente es diferente de la que aparece en la dirección de</span><span class="sxs-lookup"><span data-stu-id="ec2b8-114">The sender's address is different than what appears in the From address</span></span>

<span data-ttu-id="ec2b8-115">Con frecuencia, la dirección de correo electrónico que ve en un mensaje es diferente de la que aparece en la dirección de.</span><span class="sxs-lookup"><span data-stu-id="ec2b8-115">Frequently, the email address you see in a message is different than what you see in the From address.</span></span> <span data-ttu-id="ec2b8-116">En ocasiones, los phish atacantes intentan engañarle para que el remitente sea una persona distinta de la real.</span><span class="sxs-lookup"><span data-stu-id="ec2b8-116">Sometimes phishers try to trick you into thinking that the sender is someone other than who they really are.</span></span>

<span data-ttu-id="ec2b8-117">Cuando Outlook.com y Outlook en la Web detectan una diferencia entre la dirección real del remitente y la dirección de la dirección de, muestran el remitente real mediante la etiqueta Via, que se subraya.</span><span class="sxs-lookup"><span data-stu-id="ec2b8-117">When Outlook.com and Outlook on the web detect a difference between the sender's actual address and the address on the From address, they show the actual sender using the via tag, which will be underlined.</span></span>

![texto alternativo de remitente no comprobado](media/unverified-sender-feature1.png)

<span data-ttu-id="ec2b8-119">En este ejemplo, el dominio `suspicious.com` de envío está autenticado, pero el remitente ha `unknown@contoso.com` puesto en la dirección de remitente.</span><span class="sxs-lookup"><span data-stu-id="ec2b8-119">In this example, the sending domain `suspicious.com` is authenticated, but the sender put `unknown@contoso.com` in the From address.</span></span>

<span data-ttu-id="ec2b8-120">No todos los mensajes con una etiqueta Via son sospechosos.</span><span class="sxs-lookup"><span data-stu-id="ec2b8-120">Not every message with a via tag is suspicious.</span></span> <span data-ttu-id="ec2b8-121">Sin embargo, si no reconoce un mensaje con una etiqueta Via, debe tener cuidado a la hora de interactuar con él.</span><span class="sxs-lookup"><span data-stu-id="ec2b8-121">However, if you don't recognize a message with a via tag, you should be cautious about interacting with it.</span></span>

<span data-ttu-id="ec2b8-122">En Outlook.com y el nuevo Outlook en la web, puede desplazar el cursor sobre el nombre o la dirección del remitente en la lista de mensajes para ver su dirección de correo electrónico, sin necesidad de abrir el mensaje.</span><span class="sxs-lookup"><span data-stu-id="ec2b8-122">In Outlook.com and the new Outlook on the web, you can hover your cursor over a sender's name or address in the message list to see their email address, without needing to open the message.</span></span>

![Introducción a OneDrive](media/get-started-with-onedrive-message.png)

<span data-ttu-id="ec2b8-124">¿Cómo saber si está usando el nuevo Outlook en la web?</span><span class="sxs-lookup"><span data-stu-id="ec2b8-124">How do you know if you're using the new Outlook on the web?</span></span> <span data-ttu-id="ec2b8-125">Vea los siguientes ejemplos:</span><span class="sxs-lookup"><span data-stu-id="ec2b8-125">See the following examples:</span></span>

![Outlook vs Office 365](media/outlook-vs-outlook365.png)

## <a name="frequently-asked-questions"></a><span data-ttu-id="ec2b8-127">Preguntas más frecuentes</span><span class="sxs-lookup"><span data-stu-id="ec2b8-127">Frequently asked questions</span></span>

### <a name="what-criteria-does-outlookcom-and-outlook-on-the-web-use-to-add-the--and-the-via-properties"></a><span data-ttu-id="ec2b8-128">¿Qué criterios usa Outlook.com y Outlook en la web para agregar las propiedades "?" y "Via"?</span><span class="sxs-lookup"><span data-stu-id="ec2b8-128">What criteria does Outlook.com and Outlook on the web use to add the '?' and the 'via' properties?</span></span>

<span data-ttu-id="ec2b8-129">Para el '? ' en la imagen del remitente: Outlook.com requiere que el mensaje pase la autenticación SPF o DKIM.</span><span class="sxs-lookup"><span data-stu-id="ec2b8-129">For the '?' in the sender image:  Outlook.com requires that the message pass either SPF or DKIM authentication.</span></span> <span data-ttu-id="ec2b8-130">Para obtener más información, consulte [configurar SPF en Office 365 para evitar](set-up-spf-in-office-365-to-help-prevent-spoofing.md) la suplantación de identidad (spoofing) y el [uso de DKIM para validar el correo electrónico saliente enviado desde su dominio personalizado en Office 365](use-dkim-to-validate-outbound-email.md).</span><span class="sxs-lookup"><span data-stu-id="ec2b8-130">For more details, see [Set up SPF in Office 365 to help prevent spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md) and [Use DKIM to validate outbound email sent from your custom domain in Office 365](use-dkim-to-validate-outbound-email.md).</span></span>

<span data-ttu-id="ec2b8-131">Para la etiqueta Via: Si el dominio de la dirección de es diferente del dominio de la firma DKIM o del correo SMTP de, Outlook.com muestra el dominio en uno de estos dos campos (prefiriendo la firma DKIM).</span><span class="sxs-lookup"><span data-stu-id="ec2b8-131">For the via tag: If the domain in the From address is different from the domain in the DKIM signature or the SMTP MAIL FROM, Outlook.com displays the domain in one of those two fields (preferring the DKIM signature).</span></span>

### <a name="can-i-override-these-properties-with-ip-allows-exchange-transport-rule-allows-or-safe-senders"></a><span data-ttu-id="ec2b8-132">¿Puedo invalidar estas propiedades con permitir IP, la regla de transporte de Exchange permite o los remitentes seguros?</span><span class="sxs-lookup"><span data-stu-id="ec2b8-132">Can I override these properties with IP Allows, Exchange Transport Rule Allows, or safe senders?</span></span>

<span data-ttu-id="ec2b8-133">No puede invalidar estas propiedades.</span><span class="sxs-lookup"><span data-stu-id="ec2b8-133">You can't override these properties.</span></span>

### <a name="how-do-i-remove-these-properties"></a><span data-ttu-id="ec2b8-134">¿Cómo Quito estas propiedades?</span><span class="sxs-lookup"><span data-stu-id="ec2b8-134">How do I remove these properties?</span></span>

<span data-ttu-id="ec2b8-135">Para el '? ' en la imagen del remitente: como remitente, debe autenticar el mensaje con SPF o DKIM.</span><span class="sxs-lookup"><span data-stu-id="ec2b8-135">For the '?' in the sender image: As a sender, you should authenticate your message with either SPF or DKIM.</span></span>

<span data-ttu-id="ec2b8-136">Para la etiqueta Via: como remitente, debe asegurarse de que el dominio de la firma DKIM o el correo SMTP de sea el mismo que o sea un subdominio de, el dominio de la dirección de remitente.</span><span class="sxs-lookup"><span data-stu-id="ec2b8-136">For the via tag: As a sender, you should ensure that either the domain in the DKIM signature or the SMTP MAIL FROM is the same as, or is a subdomain of, the domain in the From address.</span></span>

### <a name="does-outlookcom-and-outlook-on-the-web-show-this-for-every-message-that-doesnt-pass-authentication"></a><span data-ttu-id="ec2b8-137">¿Outlook.com y Outlook en la web muestran esto por cada mensaje que no supera la autenticación?</span><span class="sxs-lookup"><span data-stu-id="ec2b8-137">Does Outlook.com and Outlook on the web show this for every message that doesn’t pass authentication?</span></span>

<span data-ttu-id="ec2b8-138">No necesariamente.</span><span class="sxs-lookup"><span data-stu-id="ec2b8-138">Not necessarily.</span></span> <span data-ttu-id="ec2b8-139">Outlook.com y Outlook en la web pueden tener otras propiedades dentro del mensaje para autenticar al remitente.</span><span class="sxs-lookup"><span data-stu-id="ec2b8-139">Outlook.com and Outlook on the web may have other properties within the message to authenticate the sender.</span></span>

## <a name="related-topics"></a><span data-ttu-id="ec2b8-140">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="ec2b8-140">Related topics</span></span>

[<span data-ttu-id="ec2b8-141">Ayuda para proteger su cuenta de correo electrónico de Outlook.com</span><span class="sxs-lookup"><span data-stu-id="ec2b8-141">Help protect your Outlook.com email account</span></span>](https://support.office.com/article/a4f20fc5-4307-4ece-8231-6d4d4bd8a9ba)

[<span data-ttu-id="ec2b8-142">Tratar con el abuso, suplantación de identidad (phishing) o suplantación en Outlook.com</span><span class="sxs-lookup"><span data-stu-id="ec2b8-142">Deal with abuse, phishing, or spoofing in Outlook.com</span></span>](https://support.office.com/article/0d882ea5-eedc-4bed-aebc-079ffa1105a3)

[<span data-ttu-id="ec2b8-143">Filtrar correo no deseado y correo no deseado en Outlook en la web</span><span class="sxs-lookup"><span data-stu-id="ec2b8-143">Filter junk email and spam in Outlook on the web</span></span>](https://support.office.com/article/db786e79-54e2-40cc-904f-d89d57b7f41d)
