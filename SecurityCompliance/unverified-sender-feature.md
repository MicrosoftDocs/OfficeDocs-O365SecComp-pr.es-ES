---
title: Remitente no verificado
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 07/11/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: Para evitar que los mensajes de suplantación de identidad lleguen a su buzón, Outlook.com y Outlook en la web Compruebe que el remitente es quien dice ser y marcar los mensajes sospechosos como correo no deseado.
ms.openlocfilehash: 233474dbfff430be8dd95d513adeb257bb26c5c7
ms.sourcegitcommit: 9e2df36b05a2c93ce2629a7a5eda8f44159d114d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/11/2019
ms.locfileid: "35628513"
---
# <a name="unverified-sender"></a><span data-ttu-id="a1b92-103">Remitente no verificado</span><span class="sxs-lookup"><span data-stu-id="a1b92-103">Unverified Sender</span></span>

> [!NOTE] 
> <span data-ttu-id="a1b92-104">Estas actualizaciones se están implementando ahora y es posible que no estén disponibles para todos los usuarios.</span><span class="sxs-lookup"><span data-stu-id="a1b92-104">These updates are rolling out now, and might not be available yet for all users.</span></span>

<span data-ttu-id="a1b92-105">Para evitar que los mensajes de suplantación de identidad lleguen a su buzón, Outlook.com y Outlook en la web Compruebe que el remitente es quien dice ser y marcar los mensajes sospechosos como correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="a1b92-105">To prevent phishing messages from reaching your mailbox, Outlook.com and Outlook on the web verify that the sender is who they say they are and mark suspicious messages as junk email.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a1b92-106">Cuando un mensaje se marca como una estafa de suplantación de identidad (phishing), Outlook.com y Outlook en la web muestran una advertencia en la parte superior de la página, pero los vínculos del mensaje todavía se pueden abrir.</span><span class="sxs-lookup"><span data-stu-id="a1b92-106">When a message is marked as a phishing scam, Outlook.com and Outlook on the web display a warning at the top of the page, but any links in the message can still be opened.</span></span>

## <a name="how-can-i-identify-a-suspicious-message-in-my-inbox"></a><span data-ttu-id="a1b92-107">¿Cómo puedo identificar un mensaje sospechoso en mi bandeja de entrada?</span><span class="sxs-lookup"><span data-stu-id="a1b92-107">How can I identify a suspicious message in my inbox?</span></span>

<span data-ttu-id="a1b92-108">Outlook.com y Outlook en la web muestran indicadores cuando no se puede identificar el remitente de un mensaje o su identidad es diferente de la que se ve en la dirección de remitente.</span><span class="sxs-lookup"><span data-stu-id="a1b92-108">Outlook.com and Outlook on the web show indicators when the sender of a message either can't be identified or their identity is different from what you see in the From address.</span></span>

## <a name="how-to-manage-which-messages-receive-the-unverified-sender-treatment"></a><span data-ttu-id="a1b92-109">Cómo administrar qué mensajes reciben el tratamiento de remitentes no comprobados</span><span class="sxs-lookup"><span data-stu-id="a1b92-109">How to manage which messages receive the unverified sender treatment</span></span> 

<span data-ttu-id="a1b92-110">Si es un cliente de Office 365, puede administrar esta característica a través del centro de seguridad & cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="a1b92-110">If you are an Office 365 customer you can manage this feature through the Security & Compliance Center.</span></span> 

- <span data-ttu-id="a1b92-111">En el centro de seguridad & cumplimiento de Office 365, los administradores globales o de seguridad pueden activar o desactivar la característica a través de la protección contra la suplantación de identidad (phishing) en la Directiva ANTIPHISH.</span><span class="sxs-lookup"><span data-stu-id="a1b92-111">In the Office 365 Security & Compliance Center, global or security administrators can turn the feature on or off, through anti-spoofing protection under the Anti-Phish policy.</span></span> <span data-ttu-id="a1b92-112">Además, puede administrarse mediante el cmdlet "Set-AntiPhishPolicy".</span><span class="sxs-lookup"><span data-stu-id="a1b92-112">Additionally, it can be managed through the ‘Set-AntiPhishPolicy’ cmdlet.</span></span> <span data-ttu-id="a1b92-113">Para obtener más información, consulte [protección contra la suplantación de identidad en Office 365](anti-phishing-protection.md) y [set-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/set-antiphishpolicy?view=exchange-ps).</span><span class="sxs-lookup"><span data-stu-id="a1b92-113">For more details, see [Anti-phishing protection in Office 365](anti-phishing-protection.md) and [Set-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/set-antiphishpolicy?view=exchange-ps).</span></span>

    ![Edición de remitentes no autenticados en la interfaz gráfica.](media/unverified-sender-article-editing-unauthenticated-senders.jpg)

- <span data-ttu-id="a1b92-115">Si un administrador ha identificado un falso positivo y un remitente no debe recibir el tratamiento de remitente no verificado, puede realizar una de las siguientes acciones para agregar el remitente a la lista de permitidos de falsificación de inteligencia de identidad:</span><span class="sxs-lookup"><span data-stu-id="a1b92-115">If an admin has identified a false positive, and a sender should not be receiving the unverified sender treatment they can take one of the following actions to add the sender to the Spoof Intelligence spoof allow list:</span></span>
        
    - <span data-ttu-id="a1b92-116">Agregue el par de dominios mediante el conocimiento de inteligencia de ti falso.</span><span class="sxs-lookup"><span data-stu-id="a1b92-116">Add the domain pair through the Spoof Intelligence Insight.</span></span> <span data-ttu-id="a1b92-117">Para obtener más información, consulte Walkthrough: suplantar inteligencia Insight</span><span class="sxs-lookup"><span data-stu-id="a1b92-117">For more details, see Walkthrough: spoof intelligence insight</span></span>
                
    - <span data-ttu-id="a1b92-118">Agregue el par de dominios mediante el cmdlet PhishFilterPolicy.</span><span class="sxs-lookup"><span data-stu-id="a1b92-118">Add the domain pair through the PhishFilterPolicy cmdlet.</span></span> <span data-ttu-id="a1b92-119">Para obtener más información, vea Set-PhishFilterPolicy y protección contra la suplantación de identidad en Office 365</span><span class="sxs-lookup"><span data-stu-id="a1b92-119">For more details, see Set-PhishFilterPolicy and Anti-spoofing protection in Office 365</span></span>

<span data-ttu-id="a1b92-120">Además, no se aplica el tratamiento de remitente no verificado si se entregó en la bandeja de entrada a través de una lista de permitidos del administrador, incluidas las reglas de transporte de correo electrónico (ETR), la lista de dominios seguros (Directiva contra correo no deseado), la lista de remitentes seguros o un usuario ha establecido este usuario como un "remitente seguro" en su entrada.</span><span class="sxs-lookup"><span data-stu-id="a1b92-120">Additionally, we do not apply the unverified sender treatment if it was delivered to the inbox via an admin allow list, including Email Transport Rules (ETRs), Safe Domain List (Anti-Spam Policy), Safe Sender List or a user has set this user as a “Safe Sender” in their inbox.</span></span>

### <a name="you-see-a--in-the-sender-image"></a><span data-ttu-id="a1b92-121">Ve un '? ' en la imagen del remitente</span><span class="sxs-lookup"><span data-stu-id="a1b92-121">You see a '?' in the sender image</span></span>

<span data-ttu-id="a1b92-122">Cuando Outlook.com y Outlook en la web no pueden comprobar la identidad del remitente mediante técnicas de autenticación de correo electrónico, muestran un '? ' en la foto del remitente.</span><span class="sxs-lookup"><span data-stu-id="a1b92-122">When Outlook.com and Outlook on the web can't verify the identity of the sender using email authentication techniques, they display a '?' in the sender photo.</span></span> 

![El mensaje no pasó la comprobación](media/message-did-not-pass-verification.jpg)

<span data-ttu-id="a1b92-124">No todos los mensajes que no se autentican son malintencionados.</span><span class="sxs-lookup"><span data-stu-id="a1b92-124">Not every message that fails to authenticate is malicious.</span></span> <span data-ttu-id="a1b92-125">Sin embargo, debe tener cuidado al interactuar con los mensajes que no se autentican si no reconoce al remitente.</span><span class="sxs-lookup"><span data-stu-id="a1b92-125">However, you should be careful about interacting with messages that don't authenticate if you don't recognize the sender.</span></span> <span data-ttu-id="a1b92-126">O bien, si reconoce a un remitente que normalmente no tiene un '? ' en la imagen del remitente, pero, de repente, lo empieza a ver, es posible que se trate de una firma en la que se está suplantando el remitente.</span><span class="sxs-lookup"><span data-stu-id="a1b92-126">Or, if you recognize a sender that normally doesn't have a '?' in the sender image, but you suddenly start seeing it, that could be a sign the sender is being spoofed.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="a1b92-127">Preguntas más frecuentes</span><span class="sxs-lookup"><span data-stu-id="a1b92-127">Frequently asked questions</span></span>

### <a name="what-criteria-does-outlookcom-and-outlook-on-the-web-use-to-add-the--and-the-via-properties"></a><span data-ttu-id="a1b92-128">¿Qué criterios usa Outlook.com y Outlook en la web para agregar las propiedades "?" y "Via"?</span><span class="sxs-lookup"><span data-stu-id="a1b92-128">What criteria does Outlook.com and Outlook on the web use to add the '?' and the 'via' properties?</span></span>

<span data-ttu-id="a1b92-129">Para el '? ' en la imagen del remitente: Outlook.com requiere que el mensaje pase la autenticación SPF o DKIM.</span><span class="sxs-lookup"><span data-stu-id="a1b92-129">For the '?' in the sender image:  Outlook.com requires that the message pass either SPF or DKIM authentication.</span></span> <span data-ttu-id="a1b92-130">Para obtener más información, consulte [configurar SPF en Office 365 para evitar](set-up-spf-in-office-365-to-help-prevent-spoofing.md) la suplantación de identidad (spoofing) y el [uso de DKIM para validar el correo electrónico saliente enviado desde su dominio personalizado en Office 365](use-dkim-to-validate-outbound-email.md).</span><span class="sxs-lookup"><span data-stu-id="a1b92-130">For more details, see [Set up SPF in Office 365 to help prevent spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md) and [Use DKIM to validate outbound email sent from your custom domain in Office 365](use-dkim-to-validate-outbound-email.md).</span></span>

<span data-ttu-id="a1b92-131">Para la etiqueta Via: Si el dominio de la dirección de es diferente del dominio de la firma DKIM o del correo SMTP de, Outlook.com muestra el dominio en uno de estos dos campos (prefiriendo la firma DKIM).</span><span class="sxs-lookup"><span data-stu-id="a1b92-131">For the via tag: If the domain in the From address is different from the domain in the DKIM signature or the SMTP MAIL FROM, Outlook.com displays the domain in one of those two fields (preferring the DKIM signature).</span></span>

### <a name="how-do-i-remove-the-"></a><span data-ttu-id="a1b92-132">¿Cómo quito el "?"</span><span class="sxs-lookup"><span data-stu-id="a1b92-132">How do I remove the '?'</span></span>

<span data-ttu-id="a1b92-133">Para el '? ' en la imagen del remitente: como remitente, debe autenticar el mensaje con SPF o DKIM.</span><span class="sxs-lookup"><span data-stu-id="a1b92-133">For the '?' in the sender image: As a sender, you should authenticate your message with either SPF or DKIM.</span></span>

<span data-ttu-id="a1b92-134">Para la etiqueta Via: como remitente, debe asegurarse de que el dominio de la firma DKIM o el correo SMTP de sea el mismo que o sea un subdominio de, el dominio de la dirección de remitente.</span><span class="sxs-lookup"><span data-stu-id="a1b92-134">For the via tag: As a sender, you should ensure that either the domain in the DKIM signature or the SMTP MAIL FROM is the same as, or is a subdomain of, the domain in the From address.</span></span>

### <a name="does-outlookcom-and-outlook-on-the-web-show-this-for-every-message-that-doesnt-pass-authentication"></a><span data-ttu-id="a1b92-135">¿Outlook.com y Outlook en la web muestran esto por cada mensaje que no supera la autenticación?</span><span class="sxs-lookup"><span data-stu-id="a1b92-135">Does Outlook.com and Outlook on the web show this for every message that doesn’t pass authentication?</span></span>

<span data-ttu-id="a1b92-136">No necesariamente.</span><span class="sxs-lookup"><span data-stu-id="a1b92-136">Not necessarily.</span></span> <span data-ttu-id="a1b92-137">Outlook.com y Outlook en la web pueden tener otras propiedades dentro del mensaje para autenticar al remitente.</span><span class="sxs-lookup"><span data-stu-id="a1b92-137">Outlook.com and Outlook on the web may have other properties within the message to authenticate the sender.</span></span>

## <a name="related-topics"></a><span data-ttu-id="a1b92-138">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="a1b92-138">Related topics</span></span>

[<span data-ttu-id="a1b92-139">Ayuda para proteger su cuenta de correo electrónico de Outlook.com</span><span class="sxs-lookup"><span data-stu-id="a1b92-139">Help protect your Outlook.com email account</span></span>](https://support.office.com/article/a4f20fc5-4307-4ece-8231-6d4d4bd8a9ba)

[<span data-ttu-id="a1b92-140">Tratar con el abuso, suplantación de identidad (phishing) o suplantación en Outlook.com</span><span class="sxs-lookup"><span data-stu-id="a1b92-140">Deal with abuse, phishing, or spoofing in Outlook.com</span></span>](https://support.office.com/article/0d882ea5-eedc-4bed-aebc-079ffa1105a3)

[<span data-ttu-id="a1b92-141">Filtrar correo no deseado y correo no deseado en Outlook en la web</span><span class="sxs-lookup"><span data-stu-id="a1b92-141">Filter junk email and spam in Outlook on the web</span></span>](https://support.office.com/article/db786e79-54e2-40cc-904f-d89d57b7f41d)
