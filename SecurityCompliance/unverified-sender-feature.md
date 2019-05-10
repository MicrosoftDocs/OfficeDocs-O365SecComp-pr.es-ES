---
title: Remitente no verificado
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
ms.openlocfilehash: 5d4315afb33964e7c466384366b7315287cf6298
ms.sourcegitcommit: d24f50347c671cf5d2d8afec2f80d37d18af8b5d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/10/2019
ms.locfileid: "33867853"
---
# <a name="unverified-sender"></a><span data-ttu-id="bfc7d-103">Remitente no verificado</span><span class="sxs-lookup"><span data-stu-id="bfc7d-103">Unverified Sender</span></span>

<span data-ttu-id="bfc7d-104">Para evitar que los mensajes de suplantación de identidad lleguen a su buzón, Outlook.com y Outlook en la web Compruebe que el remitente es quien dice ser y marcar los mensajes sospechosos como correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="bfc7d-104">To prevent phishing messages from reaching your mailbox, Outlook.com and Outlook on the web verify that the sender is who they say they are and mark suspicious messages as junk email.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bfc7d-105">Cuando un mensaje se marca como una estafa de suplantación de identidad (phishing), Outlook.com y Outlook en la web muestran una advertencia en la parte superior de la página, pero los vínculos del mensaje todavía se pueden abrir.</span><span class="sxs-lookup"><span data-stu-id="bfc7d-105">When a message is marked as a phishing scam, Outlook.com and Outlook on the web display a warning at the top of the page, but any links in the message can still be opened.</span></span>

## <a name="how-can-i-identify-a-suspicious-message-in-my-inbox"></a><span data-ttu-id="bfc7d-106">¿Cómo puedo identificar un mensaje sospechoso en mi bandeja de entrada?</span><span class="sxs-lookup"><span data-stu-id="bfc7d-106">How can I identify a suspicious message in my inbox?</span></span>

<span data-ttu-id="bfc7d-107">Outlook.com y Outlook en la web muestran indicadores cuando no se puede identificar el remitente de un mensaje o su identidad es diferente de la que se ve en la dirección de remitente.</span><span class="sxs-lookup"><span data-stu-id="bfc7d-107">Outlook.com and Outlook on the web show indicators when the sender of a message either can't be identified or their identity is different from what you see in the From address.</span></span>

## <a name="how-to-manage-which-messages-receive-the-unverified-sender-treatment"></a><span data-ttu-id="bfc7d-108">Cómo administrar qué mensajes reciben el tratamiento de remitentes no comprobados</span><span class="sxs-lookup"><span data-stu-id="bfc7d-108">How to manage which messages receive the unverified sender treatment</span></span> 

<span data-ttu-id="bfc7d-109">Si es un cliente de Office 365, puede administrar esta característica a través del centro de seguridad & cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="bfc7d-109">If you are an Office 365 customer you can manage this feature through the Security & Compliance Center.</span></span> 

- <span data-ttu-id="bfc7d-110">En el centro de seguridad & cumplimiento de Office 365, los administradores de espacios empresariales pueden activar o desactivar la característica a través de la protección contra la suplantación de identidad (phishing) en la Directiva ANTIPHISH.</span><span class="sxs-lookup"><span data-stu-id="bfc7d-110">In the Office 365 Security & Compliance Center, tenant admins can turn the feature on, or off, through the Anti-spoofing protection under the Anti-Phish policy.</span></span> <span data-ttu-id="bfc7d-111">Además, puede administrarse mediante el cmdlet "Set-AntiPhishPolicy".</span><span class="sxs-lookup"><span data-stu-id="bfc7d-111">Additionally, it can be managed through the ‘Set-AntiPhishPolicy’ cmdlet.</span></span> <span data-ttu-id="bfc7d-112">Para obtener más información, consulte protección contra la suplantación de identidad en Office 365 y set-AntiPhishPolicy.</span><span class="sxs-lookup"><span data-stu-id="bfc7d-112">For more details, see Anti-phishing protection in Office 365 and Set-AntiPhishPolicy.</span></span>

    ![Edición de remitentes no autenticados en la interfaz gráfica.](media/unverified-sender-article-editing-unauthenticated-senders.jpg)

- <span data-ttu-id="bfc7d-114">Si un administrador ha identificado un falso positivo y un remitente no debe recibir el tratamiento de remitente no verificado, puede realizar una de las siguientes acciones para agregar el remitente a la lista de permitidos de falsificación de inteligencia de identidad:</span><span class="sxs-lookup"><span data-stu-id="bfc7d-114">If an admin has identified a false positive, and a sender should not be receiving the unverified sender treatment they can take one of the following actions to add the sender to the Spoof Intelligence spoof allow list:</span></span>
        
    - <span data-ttu-id="bfc7d-115">Agregue el par de dominios mediante el conocimiento de inteligencia de ti falso.</span><span class="sxs-lookup"><span data-stu-id="bfc7d-115">Add the domain pair through the Spoof Intelligence Insight.</span></span> <span data-ttu-id="bfc7d-116">Para obtener más información, consulte Walkthrough: suplantar inteligencia Insight</span><span class="sxs-lookup"><span data-stu-id="bfc7d-116">For more details, see Walkthrough: spoof intelligence insight</span></span>
                
    - <span data-ttu-id="bfc7d-117">Agregue el par de dominios mediante el cmdlet PhishFilterPolicy.</span><span class="sxs-lookup"><span data-stu-id="bfc7d-117">Add the domain pair through the PhishFilterPolicy cmdlet.</span></span> <span data-ttu-id="bfc7d-118">Para obtener más información, vea Set-PhishFilterPolicy y protección contra la suplantación de identidad en Office 365</span><span class="sxs-lookup"><span data-stu-id="bfc7d-118">For more details, see Set-PhishFilterPolicy and Anti-spoofing protection in Office 365</span></span>

<span data-ttu-id="bfc7d-119">Además, no se aplica el tratamiento de remitente no verificado si se entregó en la bandeja de entrada a través de una lista de permitidos del administrador, incluidas las reglas de transporte de correo electrónico (ETR), la lista de dominios seguros (Directiva contra correo no deseado), la lista de remitentes seguros o un usuario ha establecido este usuario como un "remitente seguro" en su entrada.</span><span class="sxs-lookup"><span data-stu-id="bfc7d-119">Additionally, we do not apply the unverified sender treatment if it was delivered to the inbox via an admin allow list, including Email Transport Rules (ETRs), Safe Domain List (Anti-Spam Policy), Safe Sender List or a user has set this user as a “Safe Sender” in their inbox.</span></span>

### <a name="you-see-a--in-the-sender-image"></a><span data-ttu-id="bfc7d-120">Ve un '? ' en la imagen del remitente</span><span class="sxs-lookup"><span data-stu-id="bfc7d-120">You see a '?' in the sender image</span></span>

<span data-ttu-id="bfc7d-121">Cuando Outlook.com y Outlook en la web no pueden comprobar la identidad del remitente mediante técnicas de autenticación de correo electrónico, muestran un '? ' en la foto del remitente.</span><span class="sxs-lookup"><span data-stu-id="bfc7d-121">When Outlook.com and Outlook on the web can't verify the identity of the sender using email authentication techniques, they display a '?' in the sender photo.</span></span> 

![El mensaje no pasó la comprobación](media/message-did-not-pass-verification.jpg)

<span data-ttu-id="bfc7d-123">No todos los mensajes que no se autentican son malintencionados.</span><span class="sxs-lookup"><span data-stu-id="bfc7d-123">Not every message that fails to authenticate is malicious.</span></span> <span data-ttu-id="bfc7d-124">Sin embargo, debe tener cuidado al interactuar con los mensajes que no se autentican si no reconoce al remitente.</span><span class="sxs-lookup"><span data-stu-id="bfc7d-124">However, you should be careful about interacting with messages that don't authenticate if you don't recognize the sender.</span></span> <span data-ttu-id="bfc7d-125">O bien, si reconoce a un remitente que normalmente no tiene un '? ' en la imagen del remitente, pero, de repente, lo empieza a ver, es posible que se trate de una firma en la que se está suplantando el remitente.</span><span class="sxs-lookup"><span data-stu-id="bfc7d-125">Or, if you recognize a sender that normally doesn't have a '?' in the sender image, but you suddenly start seeing it, that could be a sign the sender is being spoofed.</span></span>

### <a name="the-senders-address-is-different-than-what-appears-in-the-from-address"></a><span data-ttu-id="bfc7d-126">La dirección del remitente es diferente de la que aparece en la dirección de</span><span class="sxs-lookup"><span data-stu-id="bfc7d-126">The sender's address is different than what appears in the From address</span></span>

<span data-ttu-id="bfc7d-127">Con frecuencia, la dirección de correo electrónico que ve en un mensaje es diferente de la que aparece en la dirección de.</span><span class="sxs-lookup"><span data-stu-id="bfc7d-127">Frequently, the email address you see in a message is different than what you see in the From address.</span></span> <span data-ttu-id="bfc7d-128">En ocasiones, los phish atacantes intentan engañarle para que el remitente sea una persona distinta de la real.</span><span class="sxs-lookup"><span data-stu-id="bfc7d-128">Sometimes phishers try to trick you into thinking that the sender is someone other than who they really are.</span></span>

<span data-ttu-id="bfc7d-129">Cuando Outlook.com y Outlook en la Web detectan una diferencia entre la dirección real del remitente y la dirección de la dirección de, muestran el remitente real mediante la etiqueta Via, que se subraya.</span><span class="sxs-lookup"><span data-stu-id="bfc7d-129">When Outlook.com and Outlook on the web detect a difference between the sender's actual address and the address on the From address, they show the actual sender using the via tag, which will be underlined.</span></span>

![texto alternativo de remitente no comprobado](media/unverified-sender-feature1.png)

<span data-ttu-id="bfc7d-131">En este ejemplo, el dominio `suspicious.com` de envío está autenticado, pero el remitente ha `unknown@contoso.com` puesto en la dirección de remitente.</span><span class="sxs-lookup"><span data-stu-id="bfc7d-131">In this example, the sending domain `suspicious.com` is authenticated, but the sender put `unknown@contoso.com` in the From address.</span></span>

<span data-ttu-id="bfc7d-132">No todos los mensajes con una etiqueta Via son sospechosos.</span><span class="sxs-lookup"><span data-stu-id="bfc7d-132">Not every message with a via tag is suspicious.</span></span> <span data-ttu-id="bfc7d-133">Sin embargo, si no reconoce un mensaje con una etiqueta Via, debe tener cuidado a la hora de interactuar con él.</span><span class="sxs-lookup"><span data-stu-id="bfc7d-133">However, if you don't recognize a message with a via tag, you should be cautious about interacting with it.</span></span>

<span data-ttu-id="bfc7d-134">En Outlook.com y el nuevo Outlook en la web, puede desplazar el cursor sobre el nombre o la dirección del remitente en la lista de mensajes para ver su dirección de correo electrónico, sin necesidad de abrir el mensaje.</span><span class="sxs-lookup"><span data-stu-id="bfc7d-134">In Outlook.com and the new Outlook on the web, you can hover your cursor over a sender's name or address in the message list to see their email address, without needing to open the message.</span></span>

![Introducción a OneDrive](media/get-started-with-onedrive-message.png)

<span data-ttu-id="bfc7d-136">¿Cómo saber si está usando el nuevo Outlook en la web?</span><span class="sxs-lookup"><span data-stu-id="bfc7d-136">How do you know if you're using the new Outlook on the web?</span></span> <span data-ttu-id="bfc7d-137">Vea los siguientes ejemplos:</span><span class="sxs-lookup"><span data-stu-id="bfc7d-137">See the following examples:</span></span>

![Outlook vs Office 365](media/outlook-vs-outlook365.png)

## <a name="frequently-asked-questions"></a><span data-ttu-id="bfc7d-139">Preguntas más frecuentes</span><span class="sxs-lookup"><span data-stu-id="bfc7d-139">Frequently asked questions</span></span>

### <a name="what-criteria-does-outlookcom-and-outlook-on-the-web-use-to-add-the--and-the-via-properties"></a><span data-ttu-id="bfc7d-140">¿Qué criterios usa Outlook.com y Outlook en la web para agregar las propiedades "?" y "Via"?</span><span class="sxs-lookup"><span data-stu-id="bfc7d-140">What criteria does Outlook.com and Outlook on the web use to add the '?' and the 'via' properties?</span></span>

<span data-ttu-id="bfc7d-141">Para el '? ' en la imagen del remitente: Outlook.com requiere que el mensaje pase la autenticación SPF o DKIM.</span><span class="sxs-lookup"><span data-stu-id="bfc7d-141">For the '?' in the sender image:  Outlook.com requires that the message pass either SPF or DKIM authentication.</span></span> <span data-ttu-id="bfc7d-142">Para obtener más información, consulte [configurar SPF en Office 365 para evitar](set-up-spf-in-office-365-to-help-prevent-spoofing.md) la suplantación de identidad (spoofing) y el [uso de DKIM para validar el correo electrónico saliente enviado desde su dominio personalizado en Office 365](use-dkim-to-validate-outbound-email.md).</span><span class="sxs-lookup"><span data-stu-id="bfc7d-142">For more details, see [Set up SPF in Office 365 to help prevent spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md) and [Use DKIM to validate outbound email sent from your custom domain in Office 365](use-dkim-to-validate-outbound-email.md).</span></span>

<span data-ttu-id="bfc7d-143">Para la etiqueta Via: Si el dominio de la dirección de es diferente del dominio de la firma DKIM o del correo SMTP de, Outlook.com muestra el dominio en uno de estos dos campos (prefiriendo la firma DKIM).</span><span class="sxs-lookup"><span data-stu-id="bfc7d-143">For the via tag: If the domain in the From address is different from the domain in the DKIM signature or the SMTP MAIL FROM, Outlook.com displays the domain in one of those two fields (preferring the DKIM signature).</span></span>

### <a name="can-i-override-these-properties-with-ip-allows-exchange-transport-rule-allows-or-safe-senders"></a><span data-ttu-id="bfc7d-144">¿Puedo invalidar estas propiedades con permitir IP, la regla de transporte de Exchange permite o los remitentes seguros?</span><span class="sxs-lookup"><span data-stu-id="bfc7d-144">Can I override these properties with IP Allows, Exchange Transport Rule Allows, or safe senders?</span></span>

<span data-ttu-id="bfc7d-145">No puede invalidar estas propiedades.</span><span class="sxs-lookup"><span data-stu-id="bfc7d-145">You can't override these properties.</span></span>

### <a name="how-do-i-remove-these-properties"></a><span data-ttu-id="bfc7d-146">¿Cómo Quito estas propiedades?</span><span class="sxs-lookup"><span data-stu-id="bfc7d-146">How do I remove these properties?</span></span>

<span data-ttu-id="bfc7d-147">Para el '? ' en la imagen del remitente: como remitente, debe autenticar el mensaje con SPF o DKIM.</span><span class="sxs-lookup"><span data-stu-id="bfc7d-147">For the '?' in the sender image: As a sender, you should authenticate your message with either SPF or DKIM.</span></span>

<span data-ttu-id="bfc7d-148">Para la etiqueta Via: como remitente, debe asegurarse de que el dominio de la firma DKIM o el correo SMTP de sea el mismo que o sea un subdominio de, el dominio de la dirección de remitente.</span><span class="sxs-lookup"><span data-stu-id="bfc7d-148">For the via tag: As a sender, you should ensure that either the domain in the DKIM signature or the SMTP MAIL FROM is the same as, or is a subdomain of, the domain in the From address.</span></span>

### <a name="does-outlookcom-and-outlook-on-the-web-show-this-for-every-message-that-doesnt-pass-authentication"></a><span data-ttu-id="bfc7d-149">¿Outlook.com y Outlook en la web muestran esto por cada mensaje que no supera la autenticación?</span><span class="sxs-lookup"><span data-stu-id="bfc7d-149">Does Outlook.com and Outlook on the web show this for every message that doesn’t pass authentication?</span></span>

<span data-ttu-id="bfc7d-150">No necesariamente.</span><span class="sxs-lookup"><span data-stu-id="bfc7d-150">Not necessarily.</span></span> <span data-ttu-id="bfc7d-151">Outlook.com y Outlook en la web pueden tener otras propiedades dentro del mensaje para autenticar al remitente.</span><span class="sxs-lookup"><span data-stu-id="bfc7d-151">Outlook.com and Outlook on the web may have other properties within the message to authenticate the sender.</span></span>

## <a name="related-topics"></a><span data-ttu-id="bfc7d-152">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="bfc7d-152">Related topics</span></span>

[<span data-ttu-id="bfc7d-153">Ayuda para proteger su cuenta de correo electrónico de Outlook.com</span><span class="sxs-lookup"><span data-stu-id="bfc7d-153">Help protect your Outlook.com email account</span></span>](https://support.office.com/article/a4f20fc5-4307-4ece-8231-6d4d4bd8a9ba)

[<span data-ttu-id="bfc7d-154">Tratar con el abuso, suplantación de identidad (phishing) o suplantación en Outlook.com</span><span class="sxs-lookup"><span data-stu-id="bfc7d-154">Deal with abuse, phishing, or spoofing in Outlook.com</span></span>](https://support.office.com/article/0d882ea5-eedc-4bed-aebc-079ffa1105a3)

[<span data-ttu-id="bfc7d-155">Filtrar correo no deseado y correo no deseado en Outlook en la web</span><span class="sxs-lookup"><span data-stu-id="bfc7d-155">Filter junk email and spam in Outlook on the web</span></span>](https://support.office.com/article/db786e79-54e2-40cc-904f-d89d57b7f41d)
