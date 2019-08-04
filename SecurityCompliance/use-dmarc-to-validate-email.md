---
title: Usar DMARC para validar el correo electrónico en Office 365
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 4a05898c-b8e4-4eab-bd70-ee912e349737
ms.collection:
- M365-security-compliance
description: Obtenga información sobre cómo configurar la autenticación de mensajes basada en dominio, la creación de informes y la conformidad (DMARC) para validar los mensajes enviados desde su organización de Office 365.
ms.openlocfilehash: 95d1220f065633d899d415800e7ad9c5e91e759f
ms.sourcegitcommit: 33c8e9c16143650ca443d73e91631f9180a9268e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/25/2019
ms.locfileid: "35854754"
---
# <a name="use-dmarc-to-validate-email-in-office-365"></a><span data-ttu-id="75e9b-103">Usar DMARC para validar el correo electrónico en Office 365</span><span class="sxs-lookup"><span data-stu-id="75e9b-103">Use DMARC to validate email in Office 365</span></span>

<span data-ttu-id="75e9b-104">La autenticación de mensajes basada en el dominio, los informes y la conformidad ([DMARC](https://dmarc.org)) funcionan con el marco de directivas de remitente (SPF) y el correo identificado por DOMAINKEYS (DKIM) para autenticar a los remitentes de correo y garantizar que los sistemas de correo electrónico de destino confían en los mensajes enviados desde el dominio.</span><span class="sxs-lookup"><span data-stu-id="75e9b-104">Domain-based Message Authentication, Reporting, and Conformance ([DMARC](https://dmarc.org)) works with Sender Policy Framework (SPF) and DomainKeys Identified Mail (DKIM) to authenticate mail senders and ensure that destination email systems trust messages sent from your domain.</span></span> <span data-ttu-id="75e9b-105">Implementar DMARC con SPF y DKIM ofrece protección adicional contra el correo electrónico de suplantación de identidad.</span><span class="sxs-lookup"><span data-stu-id="75e9b-105">Implementing DMARC with SPF and DKIM provides additional protection against spoofing and phishing email.</span></span> <span data-ttu-id="75e9b-106">DMARC permite a los sistemas que reciben los correos determinar qué hacer con los mensajes enviados desde su dominio que no superan las comprobaciones SPF o DKIM.</span><span class="sxs-lookup"><span data-stu-id="75e9b-106">DMARC helps receiving mail systems determine what to do with messages sent from your domain that fail SPF or DKIM checks.</span></span>
  
## <a name="how-do-spf-and-dmarc-work-together-to-protect-email-in-office-365"></a><span data-ttu-id="75e9b-107">¿Cómo se coordinan SPF y DMARC para proteger el correo electrónico en Office 365?</span><span class="sxs-lookup"><span data-stu-id="75e9b-107">How do SPF and DMARC work together to protect email in Office 365?</span></span>
<span data-ttu-id="75e9b-108"><a name="SPFandDMARC"> </a></span><span class="sxs-lookup"><span data-stu-id="75e9b-108"></span></span>

 <span data-ttu-id="75e9b-p102">Un mensaje de correo electrónico puede contener varias direcciones de remitentes, que se usan para distintos propósitos. Por ejemplo, observe las siguientes direcciones:</span><span class="sxs-lookup"><span data-stu-id="75e9b-p102">An email message may contain multiple originator, or sender, addresses. These addresses are used for different purposes. For example, consider these addresses:</span></span> 
  
- <span data-ttu-id="75e9b-112">**Dirección "mail from"**: identifica al remitente y especifica dónde enviar avisos de devolución si se producen problemas con la entrega del mensaje, como avisos de no entrega.</span><span class="sxs-lookup"><span data-stu-id="75e9b-112">**"Mail From" address**: Identifies the sender and specifies where to send return notices if any problems occur with the delivery of the message, such as non-delivery notices.</span></span> <span data-ttu-id="75e9b-113">Aparece en la zona del sobre de un mensaje de correo electrónico, aunque su aplicación de correo electrónico no suele mostrarla.</span><span class="sxs-lookup"><span data-stu-id="75e9b-113">This appears in the envelope portion of an email message and is not usually displayed by your email application.</span></span> <span data-ttu-id="75e9b-114">A veces, recibe la denominación dirección 5321.MailFrom o dirección de ruta de acceso inversa.</span><span class="sxs-lookup"><span data-stu-id="75e9b-114">This is sometimes called the 5321.MailFrom address or the reverse-path address.</span></span>
    
- <span data-ttu-id="75e9b-115">**Dirección "de"**: la dirección que muestra la dirección de de su aplicación de correo.</span><span class="sxs-lookup"><span data-stu-id="75e9b-115">**"From" address**: The address displayed as the From address by your mail application.</span></span> <span data-ttu-id="75e9b-116">Esta dirección identifica al autor del correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="75e9b-116">This address identifies the author of the email.</span></span> <span data-ttu-id="75e9b-117">Es decir, el buzón de la persona o el sistema responsable de escribir el mensaje.</span><span class="sxs-lookup"><span data-stu-id="75e9b-117">That is, the mailbox of the person or system responsible for writing the message.</span></span> <span data-ttu-id="75e9b-118">A veces, recibe la denominación dirección 5322.From.</span><span class="sxs-lookup"><span data-stu-id="75e9b-118">This is sometimes called the 5322.From address.</span></span>
    
<span data-ttu-id="75e9b-p105">SPF usa un registro TXT de DNS para proporcionar una lista de direcciones IP de envío autorizadas en un dominio dado. Normalmente, solo se realizan comprobaciones de SPF en la dirección 5321.MailFrom. Esto significa que la dirección de 5322.From no se autentica al usar solamente SPF. Esto habilita un escenario donde un usuario puede recibir un mensaje que pasa una comprobación de SPF, pero tiene una dirección de remitente 5322.From falsificada. Por ejemplo, veamos esta transcripción de SMTP:</span><span class="sxs-lookup"><span data-stu-id="75e9b-p105">SPF uses a DNS TXT record to provide a list of authorized sending IP addresses for a given domain. Normally, SPF checks are only performed against the 5321.MailFrom address. This means that the 5322.From address is not authenticated when you use SPF by itself. This allows for a scenario where a user can receive a message which passes an SPF check but has a spoofed 5322.From sender address. For example, consider this SMTP transcript:</span></span>
  
```
S: Helo woodgrovebank.com
S: Mail from: phish@phishing.contoso.com
S: Rcpt to: astobes@tailspintoys.com
S: data
S: To: "Andrew Stobes" <astobes@tailspintoys.com>
S: From: "Woodgrove Bank Security" <security@woodgrovebank.com>
S: Subject: Woodgrove Bank - Action required
S:
S: Greetings User,
S: 
S: We need to verify your banking details.
S: Please click the following link to verify that we have the right information for your account.
S: 
S: http://short.url/woodgrovebank/updateaccount/12-121.aspx
S:
S: Thank you,
S: Woodgrove Bank
S: .
```

<span data-ttu-id="75e9b-124">En esta transcripción, las direcciones del remitente son las siguientes:</span><span class="sxs-lookup"><span data-stu-id="75e9b-124">In this transcript, the sender addresses are as follows:</span></span>
  
- <span data-ttu-id="75e9b-125">Dirección MailFrom (5321.MailFrom): phish@phishing.contoso.com</span><span class="sxs-lookup"><span data-stu-id="75e9b-125">Mail from address (5321.MailFrom): phish@phishing.contoso.com</span></span>
    
- <span data-ttu-id="75e9b-126">Dirección From (5322.From): security@woodgrovebank.com</span><span class="sxs-lookup"><span data-stu-id="75e9b-126">From address (5322.From): security@woodgrovebank.com</span></span>
    
<span data-ttu-id="75e9b-p106">Si configuró SPF, el servidor receptor realiza una comprobación en la dirección MailFrom phish@phishing.contoso.com. Si el mensaje procede de un origen válido para el dominio phishing.contoso.com, entonces pasa la comprobación de SPF. Como el cliente de correo electrónico muestra solo la dirección From, el usuario verá que este mensaje procede de security@woodgrovebank.com. Usando solo SPF, la validez de woodgrovebank.com nunca se autentica.</span><span class="sxs-lookup"><span data-stu-id="75e9b-p106">If you configured SPF, then the receiving server performs a check against the Mail from address phish@phishing.contoso.com. If the message came from a valid source for the domain phishing.contoso.com then the SPF check passes. Since the email client only displays the From address, the user sees that this message came from security@woodgrovebank.com. With SPF alone, the validity of woodgrovebank.com was never authenticated.</span></span>
  
<span data-ttu-id="75e9b-p107">Cuando se usa DMARC, el servidor receptor también realiza una comprobación en la dirección From. En el ejemplo anterior, si no hay un registro TXT de DMARC para woodgrovebank.com, la comprobación de la dirección From da error.</span><span class="sxs-lookup"><span data-stu-id="75e9b-p107">When you use DMARC, the receiving server also performs a check against the From address. In the example above, if there is a DMARC TXT record in place for woodgrovebank.com, then the check against the From address fails.</span></span>
  
## <a name="what-is-a-dmarc-txt-record"></a><span data-ttu-id="75e9b-133">¿Qué es un registro TXT de DMARC?</span><span class="sxs-lookup"><span data-stu-id="75e9b-133">What is a DMARC TXT record?</span></span>
<span data-ttu-id="75e9b-134"><a name="WhatisDMARC"> </a></span><span class="sxs-lookup"><span data-stu-id="75e9b-134"></span></span>

<span data-ttu-id="75e9b-p108">Al igual que los registros DNS para SPF, el registro para DMARC es un registro de texto (TXT) de DNS que ayuda a evitar la suplantación de identidad. Los registros TXT de DMARC se publican en DNS. Los registros TXT de DMARC validan el origen de los mensajes de correo electrónico contrastando la dirección IP del autor de un correo electrónico con el supuesto propietario del dominio de envío. El registro TXT de DMARC identifica los servidores de correo electrónico saliente autorizados. Así, los sistemas de correo electrónico de destino comprueban que los mensajes que reciben proceden de servidores de correo electrónico saliente autorizados.</span><span class="sxs-lookup"><span data-stu-id="75e9b-p108">Like the DNS records for SPF, the record for DMARC is a DNS text (TXT) record that helps prevent spoofing and phishing. You publish DMARC TXT records in DNS. DMARC TXT records validate the origin of email messages by verifying the IP address of an email's author against the alleged owner of the sending domain. The DMARC TXT record identifies authorized outbound email servers. Destination email systems can then verify that messages they receive originate from authorized outbound email servers.</span></span>
  
<span data-ttu-id="75e9b-140">El registro TXT de DMARC de Microsoft es algo así:</span><span class="sxs-lookup"><span data-stu-id="75e9b-140">Microsoft's DMARC TXT record looks something like this:</span></span>
  
```
_dmarc.microsoft.com.   3600    IN      TXT     "v=DMARC1; p=none; pct=100; rua=mailto:d@rua.agari.com; ruf=mailto:d@ruf.agari.com; fo=1" 
```

<span data-ttu-id="75e9b-p109">Microsoft envía sus informes de DMARC a [Agari](https://agari.com), un agente externo. Agari recopila y analiza los informes de DMARC.</span><span class="sxs-lookup"><span data-stu-id="75e9b-p109">Microsoft sends its DMARC reports to [Agari](https://agari.com), a 3rd party. Agari collects and analyzes DMARC reports.</span></span>
  
## <a name="implement-dmarc-for-inbound-mail"></a><span data-ttu-id="75e9b-143">Implementar DMARC para el correo entrante</span><span class="sxs-lookup"><span data-stu-id="75e9b-143">Implement DMARC for inbound mail</span></span>
<span data-ttu-id="75e9b-144"><a name="implementDMARCinbound"> </a></span><span class="sxs-lookup"><span data-stu-id="75e9b-144"></span></span>

<span data-ttu-id="75e9b-p110">No hay que hacer nada para configurar DMARC para el correo que se recibe en Office 365. Nosotros nos hemos encargado de todo. Si quiere saber lo que ocurre con el correo que no pasa las comprobaciones de DMARC, vea [Cómo controla Office 365 el correo electrónico entrante que no supera las comprobaciones de DMARC](use-dmarc-to-validate-email.md#inbounddmarcfail).</span><span class="sxs-lookup"><span data-stu-id="75e9b-p110">You don't have to do a thing to set up DMARC for mail that you receive in Office 365. We've taken care of everything for you. If you want to learn what happens to mail that fails to pass our DMARC checks, see [How Office 365 handles inbound email that fails DMARC](use-dmarc-to-validate-email.md#inbounddmarcfail).</span></span>
  
## <a name="implement-dmarc-for-outbound-mail-from-office-365"></a><span data-ttu-id="75e9b-148">Implementar DMARC para el correo saliente de Office 365</span><span class="sxs-lookup"><span data-stu-id="75e9b-148">Implement DMARC for outbound mail from Office 365</span></span>
<span data-ttu-id="75e9b-149"><a name="implementDMARCoutbound"> </a></span><span class="sxs-lookup"><span data-stu-id="75e9b-149"></span></span>

<span data-ttu-id="75e9b-p111">Si usa Office 365, pero no está usando un dominio personalizado (sino el dominio onmicrosoft.com), solo tiene que configurar o implementar DMARC para la organización. SPF ya está configurado y Office 365 genera automáticamente una firma DKIM para el correo saliente. Para más información sobre esta firma, consulte [Comportamiento predeterminado para DKIM y Office 365](use-dkim-to-validate-outbound-email.md#DefaultDKIMbehavior).</span><span class="sxs-lookup"><span data-stu-id="75e9b-p111">If you use Office 365 but you aren't using a custom domain, that is, you use onmicrosoft.com, you don't need to do anything else to configure or implement DMARC for your organization. SPF is already set up for you and Office 365 automatically generates a DKIM signature for your outgoing mail. For more information about this signature, see [Default behavior for DKIM and Office 365](use-dkim-to-validate-outbound-email.md#DefaultDKIMbehavior).</span></span>
  
 <span data-ttu-id="75e9b-p112">Si tiene un dominio personalizado o usa servidores de Exchange locales aparte de Office 365, implemente manualmente DMARC para el correo saliente. La implementación de DMARC para el dominio personalizado incluye estos pasos:</span><span class="sxs-lookup"><span data-stu-id="75e9b-p112">If you have a custom domain or you are using on-premises Exchange servers in addition to Office 365, you need to manually implement DMARC for your outbound mail. Implementing DMARC for your custom domain includes these steps:</span></span> 
  
- [<span data-ttu-id="75e9b-155">Paso 1: Identificar orígenes válidos de correo para el dominio</span><span class="sxs-lookup"><span data-stu-id="75e9b-155">Step 1: Identify valid sources of mail for your domain</span></span>](use-dmarc-to-validate-email.md#IdentifyValidSources)
    
- [<span data-ttu-id="75e9b-156">Paso 2: Configurar SPF para el dominio en Office 365</span><span class="sxs-lookup"><span data-stu-id="75e9b-156">Step 2: Set up SPF for your domain in Office 365</span></span>](use-dmarc-to-validate-email.md#ConfigSPF)
    
- [<span data-ttu-id="75e9b-157">Paso 3: Configurar DKIM para el dominio personalizado en Office 365</span><span class="sxs-lookup"><span data-stu-id="75e9b-157">Step 3: Set up DKIM for your custom domain in Office 365</span></span>](use-dmarc-to-validate-email.md#ConfigDKIM)
    
- [<span data-ttu-id="75e9b-158">Paso 4: Formular el registro TXT de DMARC para el dominio en Office 365</span><span class="sxs-lookup"><span data-stu-id="75e9b-158">Step 4: Form the DMARC TXT record for your domain in Office 365</span></span>](use-dmarc-to-validate-email.md#CreateDMARCRecord)
    
### <a name="step-1-identify-valid-sources-of-mail-for-your-domain"></a><span data-ttu-id="75e9b-159">Paso 1: Identificar orígenes válidos de correo para el dominio</span><span class="sxs-lookup"><span data-stu-id="75e9b-159">Step 1: Identify valid sources of mail for your domain</span></span>
<span data-ttu-id="75e9b-160"><a name="IdentifyValidSources"> </a></span><span class="sxs-lookup"><span data-stu-id="75e9b-160"></span></span>

<span data-ttu-id="75e9b-p113">Si tiene configurado SPF, quiere decir que ya ha hecho este paso. Sin embargo, para DMARC, hay que tener en cuenta otras cosas. Al identificar los orígenes de correo para el dominio, debemos responder a dos preguntas:</span><span class="sxs-lookup"><span data-stu-id="75e9b-p113">If you have already set up SPF then you have already gone through this exercise. However, for DMARC, there are additional considerations. When identifying sources of mail for your domain there are two questions you need to answer:</span></span>
  
- <span data-ttu-id="75e9b-164">¿Qué direcciones IP envían mensajes desde mi dominio?</span><span class="sxs-lookup"><span data-stu-id="75e9b-164">What IP addresses send messages from my domain?</span></span>
    
- <span data-ttu-id="75e9b-165">En los correos electrónicos enviados por parte de terceros en mi nombre, ¿coincidirán los dominios 5321.MailFrom y 5322.From?</span><span class="sxs-lookup"><span data-stu-id="75e9b-165">For mail sent from third parties on my behalf, will the 5321.MailFrom and 5322.From domains match?</span></span>
    
### <a name="step-2-set-up-spf-for-your-domain-in-office-365"></a><span data-ttu-id="75e9b-166">Paso 2: Configurar SPF para el dominio en Office 365</span><span class="sxs-lookup"><span data-stu-id="75e9b-166">Step 2: Set up SPF for your domain in Office 365</span></span>
<span data-ttu-id="75e9b-167"><a name="ConfigSPF"> </a></span><span class="sxs-lookup"><span data-stu-id="75e9b-167"></span></span>

<span data-ttu-id="75e9b-168">Ahora que tiene una lista de todos los remitentes válidos, puede seguir los pasos para [Set up SPF in Office 365 to help prevent spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md).</span><span class="sxs-lookup"><span data-stu-id="75e9b-168">Now that you have a list of all your valid senders you can follow the steps to [Set up SPF in Office 365 to help prevent spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md).</span></span>
  
<span data-ttu-id="75e9b-169">Por ejemplo, suponiendo que contoso.com envía correos desde Exchange Online, un servidor Exchange local cuya dirección IP fuera 192.168.0.1 y una aplicación web cuya dirección IP fuera 192.168.100.100, el registro TXT de SPF tendría este aspecto:</span><span class="sxs-lookup"><span data-stu-id="75e9b-169">For example, assuming contoso.com sends mail from Exchange Online, an on-premises Exchange server whose IP address is 192.168.0.1, and a web application whose IP address is 192.168.100.100, the SPF TXT record would look like this:</span></span>
  
```
contoso.com  IN  TXT  " v=spf1 ip4:192.168.0.1 ip4:192.168.100.100 include:spf.protection.outlook.com -all"
```

<span data-ttu-id="75e9b-170">Como práctica recomendada, asegúrese de que el registro TXT de SPF tenga en cuenta a los remitentes externos.</span><span class="sxs-lookup"><span data-stu-id="75e9b-170">As a best practice, ensure that your SPF TXT record takes into account third-party senders.</span></span>
  
### <a name="step-3-set-up-dkim-for-your-custom-domain-in-office-365"></a><span data-ttu-id="75e9b-171">Paso 3: Configurar DKIM para el dominio personalizado en Office 365</span><span class="sxs-lookup"><span data-stu-id="75e9b-171">Step 3: Set up DKIM for your custom domain in Office 365</span></span>
<span data-ttu-id="75e9b-172"><a name="ConfigDKIM"> </a></span><span class="sxs-lookup"><span data-stu-id="75e9b-172"></span></span>

<span data-ttu-id="75e9b-p114">Cuando haya configurado SPF, deberá configurar DKIM. DKIM le permite agregar una firma digital en el encabezado de los mensajes de correo electrónico. Si no configura DKIM pero permite a Office 365 usar la configuración predeterminada de DKIM en el dominio, DMARC puede dar errores. Esto se debe a que la configuración predeterminada de DKIM usa el dominio onmicrosoft.com inicial como dirección de 5322.From, es decir, no usa el dominio personalizado. Esto provoca una discrepancia entre las direcciones 5321.MailFrom y 5322.From en todos los correos electrónicos enviados desde su dominio.</span><span class="sxs-lookup"><span data-stu-id="75e9b-p114">Once you have set up SPF, you need to set up DKIM. DKIM lets you add a digital signature to email messages in the message header. If you do not set up DKIM and instead allow Office 365 to use the default DKIM configuration for your domain, DMARC may fail. This is because the default DKIM configuration uses your initial onmicrosoft.com domain as the 5322.From address, not your custom domain. This forces a mismatch between the 5321.MailFrom and the 5322.From addresses in all email sent from your domain.</span></span>
  
<span data-ttu-id="75e9b-p115">Si hay remitentes externos que envían correo en su nombre y el correo que envían tiene direcciones 5322.From y 5321.MailFrom que no coinciden, se producirá un error de DMARC en este correo electrónico. Para evitar esto, tendrá que configurar DKIM para el dominio, en concreto con ese remitente externo. Esto permite a Office 365 autenticar el correo electrónico desde el servicio de esta tercera parte. Sin embargo, también permite a otros usuarios, por ejemplo, Yahoo, Gmail y Comcast, comprobar la validez del correo electrónico que les envía la tercera parte como si lo hubiera enviado usted. Esto es beneficioso porque permite a los clientes generar relaciones de confianza con el dominio independientemente del sitio donde se encuentre su buzón y, al mismo tiempo, Office 365 no marca un mensaje como correo no deseado por suplantación de identidad, ya que pasa las comprobaciones de autenticación para el dominio.</span><span class="sxs-lookup"><span data-stu-id="75e9b-p115">If you have third-party senders that send mail on your behalf and the mail they send has mismatched 5321.MailFrom and 5322.From addresses, DMARC will fail for that email. To avoid this, you need to set up DKIM for your domain specifically with that third-party sender. This allows Office 365 to authenticate email from this 3rd-party service. However, it also allows others, for example, Yahoo, Gmail, and Comcast, to verify email sent to them by the third-party as if it was email sent by you. This is beneficial because it allows your customers to build trust with your domain no matter where their mailbox is located, and at the same time Office 365 won't mark a message as spam due to spoofing because it passes authentication checks for your domain.</span></span>
  
<span data-ttu-id="75e9b-183">Para ver las instrucciones sobre cómo configurar DKIM para el dominio, incluyendo cómo configurar DKIM para remitentes externos para que puedan suplantar la identidad de su dominio, consulte [Usar DKIM para validar el correo electrónico saliente enviado desde su dominio personalizado en Office 365](use-dkim-to-validate-outbound-email.md).</span><span class="sxs-lookup"><span data-stu-id="75e9b-183">For instructions on setting up DKIM for your domain, including how to set up DKIM for third-party senders so they can spoof your domain, see [Use DKIM to validate outbound email sent from your custom domain in Office 365](use-dkim-to-validate-outbound-email.md).</span></span>
  
### <a name="step-4-form-the-dmarc-txt-record-for-your-domain-in-office-365"></a><span data-ttu-id="75e9b-184">Paso 4: Formular el registro TXT de DMARC para el dominio en Office 365</span><span class="sxs-lookup"><span data-stu-id="75e9b-184">Step 4: Form the DMARC TXT record for your domain in Office 365</span></span>
<span data-ttu-id="75e9b-185"><a name="CreateDMARCRecord"> </a></span><span class="sxs-lookup"><span data-stu-id="75e9b-185"></span></span>

<span data-ttu-id="75e9b-p116">Aunque existen otras opciones de sintaxis que no se mencionan aquí, estas son las opciones de sintaxis más usadas en Office 365. Formule el registro TXT de DMARC para el dominio con el siguiente formato:</span><span class="sxs-lookup"><span data-stu-id="75e9b-p116">Although there are other syntax options that are not mentioned here, these are the most commonly used options for Office 365. Form the DMARC TXT record for your domain in the format:</span></span>
  
```
_dmarc.domain  TTL  IN  TXT  "v=DMARC1; pct=100; p=policy"
```

<span data-ttu-id="75e9b-188">donde:</span><span class="sxs-lookup"><span data-stu-id="75e9b-188">where:</span></span>
  
- <span data-ttu-id="75e9b-189">*domain* es el dominio que quiere proteger.</span><span class="sxs-lookup"><span data-stu-id="75e9b-189">*domain* is the domain you want to protect.</span></span> <span data-ttu-id="75e9b-190">De forma predeterminada, el registro protege el correo del dominio y todos los subdominios.</span><span class="sxs-lookup"><span data-stu-id="75e9b-190">By default, the record protects mail from the domain and all subdomains.</span></span> <span data-ttu-id="75e9b-191">Por ejemplo, si especifica \_DMARC.contoso.com, dMarc protege el correo del dominio y todos los subdominios, como housewares.contoso.com o Plumbing.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="75e9b-191">For example, if you specify \_dmarc.contoso.com, then DMARC protects mail from the domain and all subdomains, such as housewares.contoso.com or plumbing.contoso.com.</span></span> 
    
- <span data-ttu-id="75e9b-p118">*TTL* siempre debe ser el equivalente a una hora. La unidad usada para el TTL, ya sean las horas (1 hora), los minutos (60 minutos) o los segundos (3600 segundos), variará en función del registrador del dominio.</span><span class="sxs-lookup"><span data-stu-id="75e9b-p118">*TTL* should always be the equivalent of one hour. The unit used for TTL, either hours (1 hour), minutes (60 minutes), or seconds (3600 seconds), will vary depending on the registrar for your domain.</span></span> 
    
- <span data-ttu-id="75e9b-194">*PCT = 100* indica que esta regla debe usarse para el 100% del correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="75e9b-194">*pct=100* indicates that this rule should be used for 100% of email.</span></span>
    
- <span data-ttu-id="75e9b-p119">*policy* especifica qué directiva quiere que el servidor de recepción siga si se produce un error en DMARC. Puede establecer la directiva en none, quarantine o reject.</span><span class="sxs-lookup"><span data-stu-id="75e9b-p119">*policy* specifies what policy you want the receiving server to follow if DMARC fails. You can set the policy to none, quarantine, or reject.</span></span> 
    
<span data-ttu-id="75e9b-197">Para obtener información sobre las opciones que se usan, consulte los conceptos de las [Prácticas recomendadas para la implementación de DMARC en Office 365](use-dmarc-to-validate-email.md#DMARCbestpractices).</span><span class="sxs-lookup"><span data-stu-id="75e9b-197">For information about which options to use, become familiar with the concepts in [Best practices for implementing DMARC in Office 365](use-dmarc-to-validate-email.md#DMARCbestpractices).</span></span>
  
<span data-ttu-id="75e9b-198">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="75e9b-198">Examples:</span></span>
  
- <span data-ttu-id="75e9b-199">Directiva establecida en none</span><span class="sxs-lookup"><span data-stu-id="75e9b-199">Policy set to none</span></span>
  
    ```
    _dmarc.contoso.com 3600 IN  TXT  "v=DMARC1; p=none"
    ```

- <span data-ttu-id="75e9b-200">Directiva establecida en quarantine</span><span class="sxs-lookup"><span data-stu-id="75e9b-200">Policy set to quarantine</span></span>
  
    ```
    _dmarc.contoso.com 3600 IN  TXT  "v=DMARC1; p=quarantine"
    ```

- <span data-ttu-id="75e9b-201">Directiva establecida en reject</span><span class="sxs-lookup"><span data-stu-id="75e9b-201">Policy set to reject</span></span>
  
    ```
    _dmarc.contoso.com  3600 IN  TXT  "v=DMARC1; p=reject"
    ```

<span data-ttu-id="75e9b-p120">Una vez que formule el registro, debe actualizarlo en el registrador del dominio. Para obtener instrucciones sobre cómo agregar el registro TXT de DMARC en los registros DNS para Office 365, consulte [Crear registros DNS para Office 365 al administrar los registros DNS](https://support.office.com/article/b0f3fdca-8a80-4e8e-9ef3-61e8a2a9ab23).</span><span class="sxs-lookup"><span data-stu-id="75e9b-p120">Once you have formed your record, you need to update the record at your domain registrar. For instructions on adding the DMARC TXT record to your DNS records for Office 365, see [Create DNS records for Office 365 when you manage your DNS records](https://support.office.com/article/b0f3fdca-8a80-4e8e-9ef3-61e8a2a9ab23).</span></span>
  
## <a name="best-practices-for-implementing-dmarc-in-office-365"></a><span data-ttu-id="75e9b-204">Prácticas recomendadas para la implementación de DMARC en Office 365</span><span class="sxs-lookup"><span data-stu-id="75e9b-204">Best practices for implementing DMARC in Office 365</span></span>
<span data-ttu-id="75e9b-205"><a name="DMARCbestpractices"> </a></span><span class="sxs-lookup"><span data-stu-id="75e9b-205"></span></span>

<span data-ttu-id="75e9b-p121">DMARC se puede implementar gradualmente sin que esto afecte al resto del flujo de correo. Cree e implemente un plan de distribución con estos pasos de implementación. Realice cada uno de estos pasos primero con un subdominio, luego con otros subdominios y, finalmente, con el dominio de nivel superior de la organización antes de continuar con el paso siguiente.</span><span class="sxs-lookup"><span data-stu-id="75e9b-p121">You can implement DMARC gradually without impacting the rest of your mail flow. Create and implement a roll out plan that follows these steps. Do each of these steps first with a sub-domain, then other sub-domains, and finally with the top-level domain in your organization before moving on to the next step.</span></span>
  
1. <span data-ttu-id="75e9b-209">Supervisar el impacto de implementar DMARC</span><span class="sxs-lookup"><span data-stu-id="75e9b-209">Monitor the impact of implementing DMARC</span></span>
    
    <span data-ttu-id="75e9b-p122">Comience con un registro en modo de supervisión simple para un subdominio o dominio que solicita que los receptores DMARC le envíen estadísticas sobre los mensajes que usan ese dominio. Un registro en modo de supervisión es un registro TXT de DMARC con la directiva establecida en none (p=none). Muchas empresas publican un registro TXT de DMARC con p=none porque no saben cuánto correo electrónico se pueden perder al publicar una directiva de DMARC más restrictiva.</span><span class="sxs-lookup"><span data-stu-id="75e9b-p122">Start with a simple monitoring-mode record for a sub-domain or domain that requests that DMARC receivers send you statistics about messages that they see using that domain. A monitoring-mode record is a DMARC TXT record that has its policy set to none (p=none). Many companies publish a DMARC TXT record with p=none because they are unsure about how much email they may lose by publishing a more restrictive DMARC policy.</span></span> 
    
    <span data-ttu-id="75e9b-p123">Puede hacer esto incluso antes de implementar SPF o DKIM en la infraestructura de mensajería. Sin embargo, no podrá poner en cuarentena ni rechazar eficazmente el correo mediante DMARC hasta que no implemente también SPF y DKIM. Al introducir SPF y DKIM, los informes generados mediante DMARC indicarán los números y los orígenes de los mensajes que pasen estas comprobaciones y los que no. Se puede ver fácilmente qué cantidad del tráfico legítimo está cubierto o no por ellos, así como solucionar los problemas. También empezará a ver cuántos mensajes fraudulentos se envían y desde dónde.</span><span class="sxs-lookup"><span data-stu-id="75e9b-p123">You can do this even before you've implemented SPF or DKIM in your messaging infrastructure. However, you won't be able to effectively quarantine or reject mail by using DMARC until you also implement SPF and DKIM. As you introduce SPF and DKIM, the reports generated through DMARC will provide the numbers and sources of messages that pass these checks, and those that don't. You can easily see how much of your legitimate traffic is or isn't covered by them, and troubleshoot any problems. You'll also begin to see how many fraudulent messages are being sent, and from where.</span></span>
    
2. <span data-ttu-id="75e9b-218">Solicitar que los sistemas de correo externos pongan en cuarentena el correo que no supera las comprobaciones de DMARC</span><span class="sxs-lookup"><span data-stu-id="75e9b-218">Request that external mail systems quarantine mail that fails DMARC</span></span>
    
    <span data-ttu-id="75e9b-p124">Cuando cree que todo el tráfico legítimo o la mayor parte está protegido por SPF y DKIM, y sabe cuál es el impacto de implementar DMARC, puede implementar una directiva de cuarentena. Una directiva de cuarentena es un registro TXT de DMARC con una directiva establecida en quarantine (p=quarantine). Al hacer esto, pedimos a los receptores DMARC que pongan los mensajes de su dominio que no superen las pruebas de DMARC en el equivalente local a una carpeta de correo no deseado, en lugar de en las bandejas de entrada de los clientes.</span><span class="sxs-lookup"><span data-stu-id="75e9b-p124">When you believe that all or most of your legitimate traffic is protected by SPF and DKIM, and you understand the impact of implementing DMARC, you can implement a quarantine policy. A quarantine policy is a DMARC TXT record that has its policy set to quarantine (p=quarantine). By doing this, you are asking DMARC receivers to put messages from your domain that fail DMARC into the local equivalent of a spam folder instead of your customers' inboxes.</span></span>
    
3. <span data-ttu-id="75e9b-222">Solicitar que los sistemas de correo externos no aceptan mensajes que no superen las pruebas de DMARC</span><span class="sxs-lookup"><span data-stu-id="75e9b-222">Request that external mail systems not accept messages that fail DMARC</span></span>
    
    <span data-ttu-id="75e9b-p125">El último paso es implementar una directiva de rechazo. Una directiva de rechazo es un registro TXT de DMARC con una directiva establecida en reject (p=reject). Al hacerlo, pedimos a los receptores DMARC que no acepten los mensajes que no pasan las comprobaciones de DMARC.</span><span class="sxs-lookup"><span data-stu-id="75e9b-p125">The final step is implementing a reject policy. A reject policy is a DMARC TXT record that has its policy set to reject (p=reject). When you do this, you're asking DMARC receivers not to accept messages that fail the DMARC checks.</span></span> 
    
## <a name="how-office-365-handles-outbound-email-that-fails-dmarc"></a><span data-ttu-id="75e9b-226">Cómo controla Office 365 el correo electrónico saliente que no supera las comprobaciones de DMARC</span><span class="sxs-lookup"><span data-stu-id="75e9b-226">How Office 365 handles outbound email that fails DMARC</span></span>
<span data-ttu-id="75e9b-227"><a name="outbounddmarcfail"> </a></span><span class="sxs-lookup"><span data-stu-id="75e9b-227"></span></span>

<span data-ttu-id="75e9b-228">Si un mensaje es saliente de Office 365 y se produce un error de DMARC y ha establecido la Directiva en p = Quarantine o p = Reject, el mensaje se enruta a través del [grupo de entrega de alto riesgo para los mensajes salientes](high-risk-delivery-pool-for-outbound-messages.md).</span><span class="sxs-lookup"><span data-stu-id="75e9b-228">If a message is outbound from Office 365 and fails DMARC, and you have set the policy to p=quarantine or p=reject, the message is routed through the [High-risk delivery pool for outbound messages](high-risk-delivery-pool-for-outbound-messages.md).</span></span> <span data-ttu-id="75e9b-229">No hay ninguna invalidación para el correo saliente.</span><span class="sxs-lookup"><span data-stu-id="75e9b-229">There is no override for outbound email.</span></span>
  
<span data-ttu-id="75e9b-p127">Si publica una directiva de rechazo de DMARC (p=reject), ningún otro cliente de Office 365 podrá suplantar la identidad de su dominio porque los mensajes no podrán pasar las comprobaciones de SPF o DKIM para el dominio al retransmitir un mensaje saliente a través del servicio. Sin embargo, si publica una directiva de rechazo de DMARC, pero no dispone de todo el correo electrónico autenticado a través de Office 365, una parte del correo entrante se puede marcar como correo no deseado (como se describe más arriba) o se rechazará si no publica SPF e intenta retransmitirlo para que salga a través del servicio. Esto sucede, por ejemplo, si se olvida de incluir algunas de las direcciones IP para servidores y aplicaciones que envían correo en nombre de su dominio al formular el registro TXT de DMARC.</span><span class="sxs-lookup"><span data-stu-id="75e9b-p127">If you publish a DMARC reject policy (p=reject), no other customer in Office 365 can spoof your domain because messages will not be able to pass SPF or DKIM for your domain when relaying a message outbound through the service. However, if you do publish a DMARC reject policy but don't have all of your email authenticated through Office 365, some of it may be marked as spam for inbound email (as described above), or it will be rejected if you do not publish SPF and try to relay it outbound through the service. This happens, for example, if you forget to include some of the IP addresses for servers and apps that send mail on behalf of your domain when you form your DMARC TXT record.</span></span>
  
## <a name="how-office-365-handles-inbound-email-that-fails-dmarc"></a><span data-ttu-id="75e9b-233">Cómo controla Office 365 el correo electrónico entrante que no supera las comprobaciones de DMARC</span><span class="sxs-lookup"><span data-stu-id="75e9b-233">How Office 365 handles inbound email that fails DMARC</span></span>
<span data-ttu-id="75e9b-234"><a name="inbounddmarcfail"> </a></span><span class="sxs-lookup"><span data-stu-id="75e9b-234"></span></span>

<span data-ttu-id="75e9b-p128">Si la directiva DMARC del servidor de envío es p=reject, EOP marca el mensaje como correo no deseado en lugar de rechazarlo. En otras palabras, para el correo electrónico entrante, Office 365 considera que p=reject y p=quarantine es lo mismo.</span><span class="sxs-lookup"><span data-stu-id="75e9b-p128">If the DMARC policy of the sending server is p=reject, EOP marks the message as spam instead of rejecting it. In other words, for inbound email, Office 365 treats p=reject and p=quarantine the same way.</span></span>
  
<span data-ttu-id="75e9b-p129">Office 365 está configurado así porque hay mensajes de correo legítimos que pueden no superar las comprobaciones de DMARC. Por ejemplo, un mensaje podría no superar las pruebas DMARC si se envía a una lista de distribución que luego transmite el mensaje a todos los participantes de la lista. Si Office 365 rechaza estos mensajes, las personas podrían perder el correo electrónico legítimo y no habría forma de recuperarlo. Es decir, estos mensajes seguirían provocando un error en DMARC, pero se marcarían como correo no deseado y no se rechazarían. Los usuarios que quisieran podrían colocar estos mensajes en la bandeja de entrada a través de estos métodos:</span><span class="sxs-lookup"><span data-stu-id="75e9b-p129">Office 365 is configured like this because some legitimate email may fail DMARC. For example, a message might fail DMARC if it is sent to a mailing list that then relays the message to all list participants. If Office 365 rejected these messages, people could lose legitimate email and have no way to retrieve it. Instead, these messages will still fail DMARC but they will be marked as spam and not rejected. If desired, users can still get these messages in their inbox through these methods:</span></span>
  
- <span data-ttu-id="75e9b-242">Los usuarios agregan remitentes seguros individualmente mediante el cliente de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="75e9b-242">Users add safe senders individually by using their email client</span></span>
    
- <span data-ttu-id="75e9b-243">Los administradores crean una regla de flujo de correo de Exchange (también denominada regla de transporte) para todos los usuarios que permiten mensajes para esos remitentes en particular.</span><span class="sxs-lookup"><span data-stu-id="75e9b-243">Administrators create an Exchange mail flow rule (also known as a transport rule) for all users that allows messages for those particular senders.</span></span> 
    
## <a name="troubleshooting-your-dmarc-implementation"></a><span data-ttu-id="75e9b-244">Solución de problemas en la implementación de DMARC</span><span class="sxs-lookup"><span data-stu-id="75e9b-244">Troubleshooting your DMARC implementation</span></span>
<span data-ttu-id="75e9b-245"><a name="dmarctroubleshoot"> </a></span><span class="sxs-lookup"><span data-stu-id="75e9b-245"></span></span>

<span data-ttu-id="75e9b-246">Si configuró los registros MX de su dominio donde EOP no es la primera entrada, los errores de DMARC no se aplicarán en su dominio.</span><span class="sxs-lookup"><span data-stu-id="75e9b-246">If you have configured your domain's MX records where EOP is not the first entry, DMARC failures will not be enforced for your domain.</span></span> 
  
<span data-ttu-id="75e9b-p130">Si usted es cliente de Office 365 y el registro MX principal de su dominio no apunta a EOP, no obtendrá las ventajas de DMARC. Por ejemplo, DMARC no funcionará si apunta el registro MX al servidor de correo local y luego enruta el correo electrónico a EOP usando un conector. En este escenario, el dominio receptor es uno de los dominios aceptados, pero EOP no es el MX principal. Por ejemplo, si contoso.com apunta su MX a sí mismo y usa EOP como registro MX secundario, el registro MX de contoso.com será así:</span><span class="sxs-lookup"><span data-stu-id="75e9b-p130">If you're an Office 365 customer, and your domain's primary MX record does not point to EOP, you will not get the benefits of DMARC. For example, DMARC won't work if you point the MX record to your on-premises mail server and then route email to EOP by using a connector. In this scenario, the receiving domain is one of your Accepted-Domains but EOP is not the primary MX. For example, suppose contoso.com points its MX at itself and uses EOP as a secondary MX record, contoso.com's MX record looks like the following:</span></span>
  
```
contoso.com     3600   IN  MX  0  mail.contoso.com
contoso.com     3600   IN  MX  10 contoso-com.mail.protection.outlook.com
```

<span data-ttu-id="75e9b-251">Todo el correo electrónico o la mayor parte se enrutará primero a mail.contoso.com, ya que es el MX principal, y luego el correo se enrutará a EOP.</span><span class="sxs-lookup"><span data-stu-id="75e9b-251">All, or most, email will first be routed to mail.contoso.com since it's the primary MX, and then mail will get routed to EOP.</span></span> <span data-ttu-id="75e9b-252">En algunos casos, ni siquiera podría marcar EOP como registro MX y solo podría enlazar conectores para enrutar el correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="75e9b-252">In some cases, you might not even list EOP as an MX record at all and simply hook up connectors to route your email.</span></span> <span data-ttu-id="75e9b-253">EOP no tiene que ser la primera entrada para que se realice la validación de DMARC.</span><span class="sxs-lookup"><span data-stu-id="75e9b-253">EOP does not have to be the first entry for DMARC validation to be done.</span></span> <span data-ttu-id="75e9b-254">Solo garantiza la validación, ya que no se puede garantizar que todos los servidores locales o que no sean de O365 realizarán comprobaciones de DMARC.</span><span class="sxs-lookup"><span data-stu-id="75e9b-254">It just ensures the validation, as we cannot be certain that all on-premise/non-O365 servers will do DMARC checks.</span></span>  <span data-ttu-id="75e9b-255">DMARC se puede aplicar a un dominio de un cliente (no al del servidor) cuando se configura el registro TXT de DMARC, pero el servidor receptor no puede realmente realizar la obligatoriedad de hacerlo.</span><span class="sxs-lookup"><span data-stu-id="75e9b-255">DMARC is eligible to be enforced for a customer’s domain (not server) when you set up the DMARC TXT record, but it is up to the receiving server to actually do the enforcement.</span></span>  <span data-ttu-id="75e9b-256">Si configura EOP como el servidor de recepción, EOP realiza la aplicación de DMARC.</span><span class="sxs-lookup"><span data-stu-id="75e9b-256">If you set up EOP as the receiving server, then EOP does the DMARC enforcement.</span></span>
  
## <a name="for-more-information"></a><span data-ttu-id="75e9b-257">Más información</span><span class="sxs-lookup"><span data-stu-id="75e9b-257">For more information</span></span>
<span data-ttu-id="75e9b-258"><a name="sectionSection8"> </a></span><span class="sxs-lookup"><span data-stu-id="75e9b-258"></span></span>

<span data-ttu-id="75e9b-p132">¿Quiere más información sobre DMARC? Estos recursos lo pueden ayudar.</span><span class="sxs-lookup"><span data-stu-id="75e9b-p132">Want more information about DMARC? These resources can help.</span></span>
  
- <span data-ttu-id="75e9b-261">Los [Encabezados de mensajes de correo no deseado](anti-spam-message-headers.md) incluyen la sintaxis y los campos de encabezado que usa Office 365 para efectuar comprobaciones de DMARC.</span><span class="sxs-lookup"><span data-stu-id="75e9b-261">[Anti-spam message headers](anti-spam-message-headers.md) includes the syntax and header fields used by Office 365 for DMARC checks.</span></span> 
    
- <span data-ttu-id="75e9b-262">Siga la [Serie de aprendizaje de DMARC](https://www.m3aawg.org/activities/training/dmarc-training-series) from M <sup>3</sup>AAWG (Messaging, Malware, Mobile Anti-Abuse Working Group).</span><span class="sxs-lookup"><span data-stu-id="75e9b-262">Take the [DMARC Training Series](https://www.m3aawg.org/activities/training/dmarc-training-series) from M <sup>3</sup>AAWG (Messaging, Malware, Mobile Anti-Abuse Working Group).</span></span>
    
- <span data-ttu-id="75e9b-263">Use la lista de comprobación que verá en [dmarcian](https://space.dmarcian.com/deployment/).</span><span class="sxs-lookup"><span data-stu-id="75e9b-263">Use the checklist at [dmarcian](https://space.dmarcian.com/deployment/).</span></span>
    
- <span data-ttu-id="75e9b-264">Vaya directamente al origen en [DMARC.org](https://dmarc.org).</span><span class="sxs-lookup"><span data-stu-id="75e9b-264">Go directly to the source at [DMARC.org](https://dmarc.org).</span></span>
    
## <a name="see-also"></a><span data-ttu-id="75e9b-265">Vea también</span><span class="sxs-lookup"><span data-stu-id="75e9b-265">See also</span></span>
<span data-ttu-id="75e9b-266"><a name="sectionSection8"> </a></span><span class="sxs-lookup"><span data-stu-id="75e9b-266"></span></span>

[<span data-ttu-id="75e9b-267">Cómo Office 365 usa el marco de directivas de remitente (SPF) para evitar la suplantación de identidad</span><span class="sxs-lookup"><span data-stu-id="75e9b-267">How Office 365 uses Sender Policy Framework (SPF) to prevent spoofing</span></span>](how-office-365-uses-spf-to-prevent-spoofing.md)
  
[<span data-ttu-id="75e9b-268">Configurar SPF en Office 365 para ayudar a evitar la suplantación de identidad</span><span class="sxs-lookup"><span data-stu-id="75e9b-268">Set up SPF in Office 365 to help prevent spoofing</span></span>](set-up-spf-in-office-365-to-help-prevent-spoofing.md)
  
[<span data-ttu-id="75e9b-269">Usar DKIM para validar el correo electrónico saliente enviado desde su dominio personalizado en Office 365</span><span class="sxs-lookup"><span data-stu-id="75e9b-269">Use DKIM to validate outbound email sent from your custom domain in Office 365</span></span>](use-dkim-to-validate-outbound-email.md)

