---
title: Cómo Office 365 valida la dirección from para evitar la suplantación de identidad
ms.author: tracyp
author: MSFTTracyp
manager: dansimp
ms.date: 10/11/2017
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- OWC150
- MET150
ms.assetid: eef8408b-54d3-4d7d-9cf7-ad2af10b2e0e
ms.collection:
- M365-security-compliance
description: 'Para ayudar a evitar la suplantación de identidad (phishing), Office 365 y Outlook.com requieren ahora el cumplimiento de RFC para de: addresses.'
ms.openlocfilehash: 39c9898a31c715487f3bc934ad0986e9a7b3679d
ms.sourcegitcommit: 32ecff689ae32c59a39b7633ca0f36a304e7516e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/09/2019
ms.locfileid: "35599136"
---
# <a name="how-office-365-validates-the-from-address-to-prevent-phishing"></a><span data-ttu-id="b6cb4-103">Cómo Office 365 valida la dirección from para evitar la suplantación de identidad</span><span class="sxs-lookup"><span data-stu-id="b6cb4-103">How Office 365 validates the From address to prevent phishing</span></span>

<span data-ttu-id="b6cb4-104">Las cuentas de correo electrónico de Office 365 y Outlook.com reciben un número cada vez mayor de ataques de suplantación de identidad.</span><span class="sxs-lookup"><span data-stu-id="b6cb4-104">Office 365 and Outlook.com email accounts receive an increasingly large number of phishing attacks.</span></span> <span data-ttu-id="b6cb4-105">Una técnica que usan los phishs es enviar mensajes que tienen valores para la dirección de: que no son compatibles con [RFC 5322](https://tools.ietf.org/html/rfc5322).</span><span class="sxs-lookup"><span data-stu-id="b6cb4-105">One technique phishers use is to send messages that have values for the From: address that are not compliant with [RFC 5322](https://tools.ietf.org/html/rfc5322).</span></span> <span data-ttu-id="b6cb4-106">La dirección de: también se llama la dirección 5322. from.</span><span class="sxs-lookup"><span data-stu-id="b6cb4-106">The From: address is also called the 5322.From address.</span></span> <span data-ttu-id="b6cb4-107">Para ayudar a evitar este tipo de suplantación de identidad, Office 365 y Outlook.com requieren mensajes recibidos por el servicio para incluir una dirección compatible con RFC de: Address tal como se describe en este artículo.</span><span class="sxs-lookup"><span data-stu-id="b6cb4-107">To help prevent this type of phishing, Office 365 and Outlook.com require messages received by the service to include an RFC-compliant From: address as described in this article.</span></span>
  
> [!NOTE]
> <span data-ttu-id="b6cb4-108">La información de este artículo le obliga a tener un conocimiento básico del formato general de las direcciones de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="b6cb4-108">The information in this article requires you to have a basic understanding of the general format of email addresses.</span></span> <span data-ttu-id="b6cb4-109">Para obtener más información, vea [rfc 5322](https://tools.ietf.org/html/rfc5322) (en particular las secciones 3.2.3, 3,4 y 3.4.1), [RFC 5321](https://tools.ietf.org/html/rfc5321), así como [RFC 3696](https://tools.ietf.org/html/rfc3696).</span><span class="sxs-lookup"><span data-stu-id="b6cb4-109">For more information, see [RFC 5322](https://tools.ietf.org/html/rfc5322) (particularly sections 3.2.3, 3.4, and 3.4.1), [RFC 5321](https://tools.ietf.org/html/rfc5321), as well as [RFC 3696](https://tools.ietf.org/html/rfc3696).</span></span> <span data-ttu-id="b6cb4-110">Este artículo trata sobre la aplicación de directivas para la dirección 5322. from.</span><span class="sxs-lookup"><span data-stu-id="b6cb4-110">This article is about policy enforcement for the 5322.From address.</span></span> <span data-ttu-id="b6cb4-111">Este artículo no trata sobre la dirección 5321. MailFrom.</span><span class="sxs-lookup"><span data-stu-id="b6cb4-111">This article is not about the 5321.MailFrom address.</span></span> 
  
<span data-ttu-id="b6cb4-112">Desafortunadamente, todavía hay algunos servidores de correo electrónico heredados en Internet que continúan enviando mensajes de correo electrónico "legítimos" que tienen una dirección de: que faltan o tienen un formato incorrecto.</span><span class="sxs-lookup"><span data-stu-id="b6cb4-112">Unfortunately, there are still some legacy email servers on the Internet that continue to send "legitimate" email messages that have a missing or malformed From: address.</span></span> <span data-ttu-id="b6cb4-113">Si recibe regularmente correo electrónico de organizaciones que usan estos sistemas heredados, Anime a esas organizaciones a que actualicen sus servidores de correo para cumplir con los estándares de seguridad modernos.</span><span class="sxs-lookup"><span data-stu-id="b6cb4-113">If you regularly receive email from organizations that use these legacy systems, encourage those organizations to update their mail servers to comply with modern security standards.</span></span>
  
<span data-ttu-id="b6cb4-114">Microsoft empezará a implementar la aplicación de las directivas descritas en este artículo el 9 de noviembre de 2017.</span><span class="sxs-lookup"><span data-stu-id="b6cb4-114">Microsoft will start rolling out enforcement of the policies described in this article on November 9, 2017.</span></span>
  
## <a name="how-office-365-enforces-the-use-of-a-valid-from-address-to-prevent-phishing-attacks"></a><span data-ttu-id="b6cb4-115">Cómo Office 365 exige el uso de una dirección from: Address válida para evitar ataques de suplantación de identidad (phishing)</span><span class="sxs-lookup"><span data-stu-id="b6cb4-115">How Office 365 enforces the use of a valid From: address to prevent phishing attacks</span></span>

<span data-ttu-id="b6cb4-116">Office 365 está realizando cambios en la forma en que aplica el uso de la dirección de: en los mensajes que recibe para proteger mejor de los ataques de suplantación de identidad (phishing).</span><span class="sxs-lookup"><span data-stu-id="b6cb4-116">Office 365 is making changes to the way it enforces the use of the From: address in messages it receives in order to better protect you from phishing attacks.</span></span> <span data-ttu-id="b6cb4-117">En este artículo:</span><span class="sxs-lookup"><span data-stu-id="b6cb4-117">In this article:</span></span>
  
- [<span data-ttu-id="b6cb4-118">Todos los mensajes deben incluir una dirección from válida from:</span><span class="sxs-lookup"><span data-stu-id="b6cb4-118">All messages must include a valid From: address</span></span>](how-office-365-validates-the-from-address.md#MustIncludeFromAddress)
    
- [<span data-ttu-id="b6cb4-119">Formato de la dirección de: Si no incluye un nombre para mostrar</span><span class="sxs-lookup"><span data-stu-id="b6cb4-119">Format of the From: address if you don't include a display name</span></span>](how-office-365-validates-the-from-address.md#FormatNoDisplayName)
    
- [<span data-ttu-id="b6cb4-120">Formato de la dirección de: si incluye un nombre para mostrar</span><span class="sxs-lookup"><span data-stu-id="b6cb4-120">Format of the From: address if you include a display name</span></span>](how-office-365-validates-the-from-address.md#FormatDisplayName)
    
- [<span data-ttu-id="b6cb4-121">Ejemplos adicionales de direcciones válidas y no válidas:</span><span class="sxs-lookup"><span data-stu-id="b6cb4-121">Additional examples of valid and invalid From: addresses</span></span>](how-office-365-validates-the-from-address.md#Examples)
    
- [<span data-ttu-id="b6cb4-122">Suprimir las respuestas automáticas a su dominio personalizado sin romper la Directiva de:</span><span class="sxs-lookup"><span data-stu-id="b6cb4-122">Suppress auto-replies to your custom domain without breaking the From: policy</span></span>](how-office-365-validates-the-from-address.md#SuppressAutoReply)
    
- [<span data-ttu-id="b6cb4-123">Reemplazar el Office 365 de: Directiva de aplicación de direcciones</span><span class="sxs-lookup"><span data-stu-id="b6cb4-123">Overriding the Office 365 From: address enforcement policy</span></span>](how-office-365-validates-the-from-address.md#Override)
    
- [<span data-ttu-id="b6cb4-124">Otras formas de evitar y proteger contra cybercrimes en Office 365</span><span class="sxs-lookup"><span data-stu-id="b6cb4-124">Other ways to prevent and protect against cybercrimes in Office 365</span></span>](how-office-365-validates-the-from-address.md#OtherProtection)
    
<span data-ttu-id="b6cb4-125">El envío en nombre de otro usuario no se ve afectado por este cambio, para obtener más información, lea el blog de Tomás Zink "[¿Qué significa cuando hacemos referencia al" remitente "de un correo electrónico?](https://blogs.msdn.microsoft.com/tzink/2017/06/22/what-do-we-mean-when-we-refer-to-the-sender-of-an-email/)".</span><span class="sxs-lookup"><span data-stu-id="b6cb4-125">Sending on behalf of another user is not affected by this change, for more details, read Terry Zink's blog "[What do we mean when we refer to the 'sender' of an email?](https://blogs.msdn.microsoft.com/tzink/2017/06/22/what-do-we-mean-when-we-refer-to-the-sender-of-an-email/)".</span></span>
  
### <a name="all-messages-must-include-a-valid-from-address"></a><span data-ttu-id="b6cb4-126">Todos los mensajes deben incluir una dirección from válida from:</span><span class="sxs-lookup"><span data-stu-id="b6cb4-126">All messages must include a valid From: address</span></span>
<span data-ttu-id="b6cb4-127"><a name="MustIncludeFromAddress"> </a></span><span class="sxs-lookup"><span data-stu-id="b6cb4-127"></span></span>

<span data-ttu-id="b6cb4-128">Algunos mensajes automatizados no incluyen una dirección de: cuando se envían.</span><span class="sxs-lookup"><span data-stu-id="b6cb4-128">Some automated messages don't include a From: address when they are sent.</span></span> <span data-ttu-id="b6cb4-129">En el pasado, cuando Office 365 o Outlook.com recibía un mensaje sin una dirección de:, el servicio agregaba la siguiente dirección siguiente predeterminada desde: al mensaje para hacerla entregar:</span><span class="sxs-lookup"><span data-stu-id="b6cb4-129">In the past, when Office 365 or Outlook.com received a message without a From: address, the service added the following default From: address to the message in order to make it deliverable:</span></span>
  
```
From: <>
```

<span data-ttu-id="b6cb4-130">A partir del 9 de noviembre de 2017, Office 365 se implementarán cambios en sus centros de información y servidores de correo que aplicarán una nueva regla en la que Office 365 o Outlook.com no aceptarán mensajes sin una dirección de:.</span><span class="sxs-lookup"><span data-stu-id="b6cb4-130">Starting November 9, 2017, Office 365 will be rolling out changes to its datacenters and mail servers which will enforce a new rule where messages without a From: address will no longer be accepted by Office 365 or Outlook.com.</span></span> <span data-ttu-id="b6cb4-131">En su lugar, todos los mensajes que recibe Office 365 ya deben contener una dirección from: válida.</span><span class="sxs-lookup"><span data-stu-id="b6cb4-131">Instead, all messages received by Office 365 must already contain a valid From: address.</span></span> <span data-ttu-id="b6cb4-132">De lo contrario, el mensaje se enviará a las carpetas correo no deseado o elementos eliminados de Outlook.com y Office 365.</span><span class="sxs-lookup"><span data-stu-id="b6cb4-132">Otherwise, the message will be sent to either the Junk Email or Deleted Items folders in Outlook.com and Office 365.</span></span> 
  
### <a name="syntax-overview-valid-format-for-the-from-address-for-office-365"></a><span data-ttu-id="b6cb4-133">Información general sobre la sintaxis: formato válido para la dirección de: para Office 365</span><span class="sxs-lookup"><span data-stu-id="b6cb4-133">Syntax overview: Valid format for the From: address for Office 365</span></span>
<span data-ttu-id="b6cb4-134"><a name="SyntaxOverviewFromAddress"> </a></span><span class="sxs-lookup"><span data-stu-id="b6cb4-134"></span></span>

<span data-ttu-id="b6cb4-135">El formato del valor de la dirección de: se define en detalle en varias RFC.</span><span class="sxs-lookup"><span data-stu-id="b6cb4-135">The format for the value of the From: address is defined in detail across several RFCs.</span></span> <span data-ttu-id="b6cb4-136">Hay muchas variaciones en el direccionamiento y lo que puede considerarse válido o no válido.</span><span class="sxs-lookup"><span data-stu-id="b6cb4-136">There are many variations on addressing and what may be considered valid or invalid.</span></span> <span data-ttu-id="b6cb4-137">Para mantenerlo sencillo, Microsoft recomienda usar el siguiente formato y las siguientes definiciones:</span><span class="sxs-lookup"><span data-stu-id="b6cb4-137">To keep it simple, Microsoft recommends that you use the following format and definitions:</span></span>
  
```
From: "displayname " <emailaddress >
```

<span data-ttu-id="b6cb4-138">Donde:</span><span class="sxs-lookup"><span data-stu-id="b6cb4-138">Where:</span></span>
  
- <span data-ttu-id="b6cb4-139">Opcional  *displayName* es una frase que describe el propietario de la dirección de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="b6cb4-139">(Optional)  *displayname*  is a phrase that describes the owner of the email address.</span></span> <span data-ttu-id="b6cb4-140">Por ejemplo, podría tratarse de un nombre más descriptivo para describir al remitente que el nombre del buzón.</span><span class="sxs-lookup"><span data-stu-id="b6cb4-140">For example, this might be a more user-friendly name to describe the sender than the name of the mailbox.</span></span> <span data-ttu-id="b6cb4-141">El uso de un nombre para mostrar es opcional.</span><span class="sxs-lookup"><span data-stu-id="b6cb4-141">Using a display name is optional.</span></span> <span data-ttu-id="b6cb4-142">Sin embargo, si decide usar un nombre para mostrar, Microsoft recomienda que siempre lo entre entre comillas como se muestra.</span><span class="sxs-lookup"><span data-stu-id="b6cb4-142">However, if you choose to use a display name, Microsoft recommends that you always enclose it within quotation marks as shown.</span></span> 
    
- <span data-ttu-id="b6cb4-143">Necesarios  *EmailAddress* consta de:</span><span class="sxs-lookup"><span data-stu-id="b6cb4-143">(Required)  *emailaddress*  is made up of:</span></span> 
    
  ```
  local-part @domain
  ```

    <span data-ttu-id="b6cb4-144">Donde:</span><span class="sxs-lookup"><span data-stu-id="b6cb4-144">Where:</span></span>
    
  - <span data-ttu-id="b6cb4-145">Necesarios  la *parte local* es una cadena que identifica el buzón asociado con la dirección.</span><span class="sxs-lookup"><span data-stu-id="b6cb4-145">(Required)  *local-part*  is a string that identifies the mailbox associated with the address.</span></span> <span data-ttu-id="b6cb4-146">Esto es único dentro del dominio.</span><span class="sxs-lookup"><span data-stu-id="b6cb4-146">This is unique within the domain.</span></span> <span data-ttu-id="b6cb4-147">A menudo, el GUID o el nombre de usuario del propietario del buzón se usa como el valor de la parte local.</span><span class="sxs-lookup"><span data-stu-id="b6cb4-147">Often, the mailbox owner's username or GUID is used as the value for the local-part.</span></span> 
    
  - <span data-ttu-id="b6cb4-148">Necesarios  *Domain* es el nombre de dominio completo (FQDN) del servidor de correo que hospeda el buzón identificado por la parte local de la dirección de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="b6cb4-148">(Required)  *domain*  is the fully-qualified domain name (FQDN) of the mail server that hosts the mailbox identified by the local-part of the email address.</span></span> 
    
### <a name="format-of-the-from-address-if-you-dont-include-a-display-name"></a><span data-ttu-id="b6cb4-149">Formato de la dirección de: Si no incluye un nombre para mostrar</span><span class="sxs-lookup"><span data-stu-id="b6cb4-149">Format of the From: address if you don't include a display name</span></span>
<span data-ttu-id="b6cb4-150"><a name="FormatNoDisplayName"> </a></span><span class="sxs-lookup"><span data-stu-id="b6cb4-150"></span></span>

<span data-ttu-id="b6cb4-151">Un formato adecuado de: Address que no incluye un nombre para mostrar solo incluye una dirección de correo electrónico con o sin corchetes angulares.</span><span class="sxs-lookup"><span data-stu-id="b6cb4-151">A properly formatted From: address that does not include a display name includes only a single email address with or without angle brackets.</span></span> <span data-ttu-id="b6cb4-152">Microsoft recomienda que no separe los corchetes angulares con espacios.</span><span class="sxs-lookup"><span data-stu-id="b6cb4-152">Microsoft recommends that you do not separate the angle brackets with spaces.</span></span> <span data-ttu-id="b6cb4-153">Además, no incluya nada después de la dirección de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="b6cb4-153">In addition, don't include anything after the email address.</span></span>
  
<span data-ttu-id="b6cb4-154">Los ejemplos siguientes son válidos:</span><span class="sxs-lookup"><span data-stu-id="b6cb4-154">The following examples are valid:</span></span>
  
```
From: sender@contoso.com
```

```
From: <sender@contoso.com>
```

<span data-ttu-id="b6cb4-155">El siguiente ejemplo es válido pero no se recomienda porque contiene espacios entre los corchetes angulares y la dirección de correo electrónico:</span><span class="sxs-lookup"><span data-stu-id="b6cb4-155">The following example is valid but not recommended because it contains spaces between the angle brackets and the email address:</span></span>
  
```
From: < sender@contoso.com >
```

<span data-ttu-id="b6cb4-156">El siguiente ejemplo no es válido porque contiene texto después de la dirección de correo electrónico:</span><span class="sxs-lookup"><span data-stu-id="b6cb4-156">The following example is invalid because it contains text after the email address:</span></span>
  
```
From: "Office 365" <sender@contoso.com> (Sent by a process)
```

### <a name="format-of-the-from-address-if-you-include-a-display-name"></a><span data-ttu-id="b6cb4-157">Formato de la dirección de: si incluye un nombre para mostrar</span><span class="sxs-lookup"><span data-stu-id="b6cb4-157">Format of the From: address if you include a display name</span></span>
<span data-ttu-id="b6cb4-158"><a name="FormatDisplayName"> </a></span><span class="sxs-lookup"><span data-stu-id="b6cb4-158"></span></span>

<span data-ttu-id="b6cb4-159">En el caso de las direcciones de: que incluyen un valor para el nombre para mostrar, se aplican las siguientes reglas:</span><span class="sxs-lookup"><span data-stu-id="b6cb4-159">For From: addresses that include a value for the display name, the following rules apply:</span></span>
  
- <span data-ttu-id="b6cb4-160">Si la dirección del remitente incluye un nombre para mostrar y el nombre para mostrar incluye una coma, el nombre para mostrar debe ir entre comillas.</span><span class="sxs-lookup"><span data-stu-id="b6cb4-160">If the sender address includes a display name, and the display name includes a comma, then the display name must be enclosed within quotation marks.</span></span> <span data-ttu-id="b6cb4-161">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="b6cb4-161">For example:</span></span>
    
    <span data-ttu-id="b6cb4-162">El siguiente ejemplo es válido:</span><span class="sxs-lookup"><span data-stu-id="b6cb4-162">The following example is valid:</span></span>
    
  ```
  From: "Sender, Example" <sender.example@contoso.com>
  ```

    <span data-ttu-id="b6cb4-163">El siguiente ejemplo no es válido:</span><span class="sxs-lookup"><span data-stu-id="b6cb4-163">The following example is not valid:</span></span>
    
  ```
  From: Sender, Example <sender.example@contoso.com>
  ```

    <span data-ttu-id="b6cb4-164">El nombre para mostrar no se cierra entre comillas si el nombre para mostrar incluye una coma de acuerdo con RFC 5322.</span><span class="sxs-lookup"><span data-stu-id="b6cb4-164">Not enclosing the display name in quotation marks if that display name includes a comma is invalid according to RFC 5322.</span></span>
    
    <span data-ttu-id="b6cb4-165">Como práctica recomendada, coloque las comillas alrededor del nombre para mostrar independientemente de si hay una coma dentro del nombre para mostrar.</span><span class="sxs-lookup"><span data-stu-id="b6cb4-165">As a best practice, put quote marks around the display name regardless of whether or not there is a comma within the display name.</span></span>
    
- <span data-ttu-id="b6cb4-166">Si la dirección del remitente incluye un nombre para mostrar, la dirección de correo electrónico debe estar entre corchetes angulares.</span><span class="sxs-lookup"><span data-stu-id="b6cb4-166">If the sender address includes a display name, then the email address must be enclosed within angle brackets.</span></span>
    
    <span data-ttu-id="b6cb4-167">Como práctica recomendada, Microsoft recomienda encarecidamente que inserte un espacio entre el nombre para mostrar y la dirección de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="b6cb4-167">As a best practice, Microsoft strongly recommends that you insert a space between the display name and the email address.</span></span>
    
### <a name="additional-examples-of-valid-and-invalid-from-addresses"></a><span data-ttu-id="b6cb4-168">Ejemplos adicionales de direcciones válidas y no válidas:</span><span class="sxs-lookup"><span data-stu-id="b6cb4-168">Additional examples of valid and invalid From: addresses</span></span>
<span data-ttu-id="b6cb4-169"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="b6cb4-169"></span></span>

- <span data-ttu-id="b6cb4-170">Validación</span><span class="sxs-lookup"><span data-stu-id="b6cb4-170">Valid:</span></span>
    
  ```
  From: "Office 365" <sender@contoso.com>
  ```

- <span data-ttu-id="b6cb4-171">No válido.</span><span class="sxs-lookup"><span data-stu-id="b6cb4-171">Invalid.</span></span> <span data-ttu-id="b6cb4-172">La dirección de correo electrónico no se incluye entre corchetes angulares:</span><span class="sxs-lookup"><span data-stu-id="b6cb4-172">The email address is not enclosed with angle brackets:</span></span>
    
  ```
  From: Office 365 sender@contoso.com
  ```

- <span data-ttu-id="b6cb4-173">Válido, pero no se recomienda.</span><span class="sxs-lookup"><span data-stu-id="b6cb4-173">Valid, but not recommended.</span></span> <span data-ttu-id="b6cb4-174">El nombre para mostrar no está entre comillas.</span><span class="sxs-lookup"><span data-stu-id="b6cb4-174">The display name is not in quotes.</span></span> <span data-ttu-id="b6cb4-175">Como práctica recomendada, escriba siempre comillas alrededor del nombre para mostrar:</span><span class="sxs-lookup"><span data-stu-id="b6cb4-175">As a best practice, always put quotation marks around the display name:</span></span>
    
  ```
  From: Office 365 <sender@contoso.com>
  ```

- <span data-ttu-id="b6cb4-176">No válido.</span><span class="sxs-lookup"><span data-stu-id="b6cb4-176">Invalid.</span></span> <span data-ttu-id="b6cb4-177">Todo se encierra entre comillas, no solo el nombre para mostrar:</span><span class="sxs-lookup"><span data-stu-id="b6cb4-177">Everything is enclosed within quotation marks, not just the display name:</span></span>
    
  ```
  From: "Office 365 <sender@contoso.com>"
  ```

- <span data-ttu-id="b6cb4-178">No válido.</span><span class="sxs-lookup"><span data-stu-id="b6cb4-178">Invalid.</span></span> <span data-ttu-id="b6cb4-179">No hay paréntesis angulares alrededor de la dirección de correo electrónico:</span><span class="sxs-lookup"><span data-stu-id="b6cb4-179">There are no angle brackets around the email address:</span></span>
    
  ```
  From: "Office 365 <sender@contoso.com>" sender@contoso.com
  ```

- <span data-ttu-id="b6cb4-180">No válido.</span><span class="sxs-lookup"><span data-stu-id="b6cb4-180">Invalid.</span></span> <span data-ttu-id="b6cb4-181">No hay ningún espacio entre el nombre para mostrar y el corchete angular izquierdo:</span><span class="sxs-lookup"><span data-stu-id="b6cb4-181">There is no space between the display name and left angle bracket:</span></span>
    
  ```
  From: Office 365<sender@contoso.com>
  ```

- <span data-ttu-id="b6cb4-182">No válido.</span><span class="sxs-lookup"><span data-stu-id="b6cb4-182">Invalid.</span></span> <span data-ttu-id="b6cb4-183">No hay ningún espacio entre el comillas de cierre que rodea el nombre para mostrar y el corchete angular de apertura.</span><span class="sxs-lookup"><span data-stu-id="b6cb4-183">There is no space between the closing quotation mark around the display name and the left angle bracket.</span></span>
    
  ```
  From: "Office 365"<sender@contoso.com>
  ```

### <a name="suppress-auto-replies-to-your-custom-domain-without-breaking-the-from-policy"></a><span data-ttu-id="b6cb4-184">Suprimir las respuestas automáticas a su dominio personalizado sin romper la Directiva de:</span><span class="sxs-lookup"><span data-stu-id="b6cb4-184">Suppress auto-replies to your custom domain without breaking the From: policy</span></span>
<span data-ttu-id="b6cb4-185"><a name="SuppressAutoReply"> </a></span><span class="sxs-lookup"><span data-stu-id="b6cb4-185"></span></span>

<span data-ttu-id="b6cb4-186">Con el nuevo de: aplicación de Directiva, ya no podrá usar de: \< \> para suprimir las respuestas automáticas.</span><span class="sxs-lookup"><span data-stu-id="b6cb4-186">With the new From: policy enforcement, you can no longer use From: \<\> to suppress auto-replies.</span></span> <span data-ttu-id="b6cb4-187">En su lugar, debe configurar un registro MX nulo para el dominio personalizado.</span><span class="sxs-lookup"><span data-stu-id="b6cb4-187">Instead, you need to set up a null MX record for your custom domain.</span></span>
  
<span data-ttu-id="b6cb4-188">El registro de intercambio de correo (MX) es un registro de recursos en DNS que identifica el servidor de correo que recibe el correo de su dominio.</span><span class="sxs-lookup"><span data-stu-id="b6cb4-188">The mail exchanger (MX) record is a resource record in DNS that identifies the mail server that receives mail for your domain.</span></span> <span data-ttu-id="b6cb4-189">Las respuestas automáticas (y todas las respuestas) se suprimen naturalmente porque no hay ninguna dirección publicada a la que el servidor que responde puede enviar mensajes.</span><span class="sxs-lookup"><span data-stu-id="b6cb4-189">Auto-replies (and all replies) are naturally suppressed because there is no published address to which the responding server can send messages.</span></span>
  
<span data-ttu-id="b6cb4-190">Cuando se configura un registro MX nulo para el dominio personalizado:</span><span class="sxs-lookup"><span data-stu-id="b6cb4-190">When you set up a null MX record for your custom domain:</span></span>
  
- <span data-ttu-id="b6cb4-191">Elija un dominio desde el que enviar mensajes que no acepten (reciban) correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="b6cb4-191">Choose a domain from which to send messages that doesn't accept (receive) email.</span></span> <span data-ttu-id="b6cb4-192">Por ejemplo, si su dominio principal es contoso.com, puede elegir noreply.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="b6cb4-192">For example, if your primary domain is contoso.com, you might choose noreply.contoso.com.</span></span>
    
- <span data-ttu-id="b6cb4-193">Configurar el registro MX nulo para el dominio.</span><span class="sxs-lookup"><span data-stu-id="b6cb4-193">Set up the null MX record for your domain.</span></span> <span data-ttu-id="b6cb4-194">Un registro MX nulo consta de un único punto, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="b6cb4-194">A null MX record consists of a single dot, for example:</span></span>
    
  ```
  noreply.contoso.com IN MX .
  ```

<span data-ttu-id="b6cb4-195">Para obtener más información acerca de la publicación de un MX nulo, consulte [RFC 7505](https://tools.ietf.org/html/rfc7505).</span><span class="sxs-lookup"><span data-stu-id="b6cb4-195">For more information about publishing a null MX, see [RFC 7505](https://tools.ietf.org/html/rfc7505).</span></span>
  
### <a name="overriding-the-office-365-from-address-enforcement-policy"></a><span data-ttu-id="b6cb4-196">Reemplazar el Office 365 de: Directiva de aplicación de direcciones</span><span class="sxs-lookup"><span data-stu-id="b6cb4-196">Overriding the Office 365 From: address enforcement policy</span></span>
<span data-ttu-id="b6cb4-197"><a name="Override"> </a></span><span class="sxs-lookup"><span data-stu-id="b6cb4-197"></span></span>

<span data-ttu-id="b6cb4-198">Una vez completada la implementación de la nueva Directiva, solo puede omitir esta directiva para el correo entrante que reciba de Office 365 mediante uno de los siguientes métodos:</span><span class="sxs-lookup"><span data-stu-id="b6cb4-198">Once roll out of the new policy is complete, you can only bypass this policy for inbound mail you receive from Office 365 by using one of the following methods:</span></span> 
  
- <span data-ttu-id="b6cb4-199">Listas de direcciones IP permitidas</span><span class="sxs-lookup"><span data-stu-id="b6cb4-199">IP allow lists</span></span>
    
- <span data-ttu-id="b6cb4-200">Reglas de flujo de correo de Exchange Online</span><span class="sxs-lookup"><span data-stu-id="b6cb4-200">Exchange Online mail flow rules</span></span>
    
<span data-ttu-id="b6cb4-201">Microsoft recomienda encarecidamente no invalidar la obligatoriedad de la Directiva de:.</span><span class="sxs-lookup"><span data-stu-id="b6cb4-201">Microsoft strongly recommends against overriding the enforcement of the From: policy.</span></span> <span data-ttu-id="b6cb4-202">Invalidar esta Directiva puede aumentar el riesgo de exposición de la organización al correo no deseado, la suplantación de identidad (phishing) y otros cybercrimes.</span><span class="sxs-lookup"><span data-stu-id="b6cb4-202">Overriding this policy can increase your organization's risk of exposure to spam, phishing, and other cybercrimes.</span></span>
  
<span data-ttu-id="b6cb4-203">No puede invalidar esta directiva para el correo saliente que envíe en Office 365.</span><span class="sxs-lookup"><span data-stu-id="b6cb4-203">You cannot override this policy for outbound mail you send in Office 365.</span></span> <span data-ttu-id="b6cb4-204">Además, Outlook.com no permitirá invalidaciones de ningún tipo, incluso a través del soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="b6cb4-204">In addition, Outlook.com will not allow overrides of any kind, even through support.</span></span> 
  
### <a name="other-ways-to-prevent-and-protect-against-cybercrimes-in-office-365"></a><span data-ttu-id="b6cb4-205">Otras formas de evitar y proteger contra cybercrimes en Office 365</span><span class="sxs-lookup"><span data-stu-id="b6cb4-205">Other ways to prevent and protect against cybercrimes in Office 365</span></span>
<span data-ttu-id="b6cb4-206"><a name="OtherProtection"> </a></span><span class="sxs-lookup"><span data-stu-id="b6cb4-206"></span></span>

<span data-ttu-id="b6cb4-207">Para obtener más información sobre cómo fortalecer la organización frente a cybercrimes como suplantación de identidad, correo no deseado, infracciones de datos y otras amenazas, vea [Security Best Practices for Office 365](https://support.office.com/article/9295e396-e53d-49b9-ae9b-0b5828cdedc3).</span><span class="sxs-lookup"><span data-stu-id="b6cb4-207">For more information on how you can strengthen your organization against cybercrimes like phishing, spamming, data breaches, and other threats, see [Security best practices for Office 365](https://support.office.com/article/9295e396-e53d-49b9-ae9b-0b5828cdedc3).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="b6cb4-208">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="b6cb4-208">Related Topics</span></span>

[<span data-ttu-id="b6cb4-209">Mensajes de reenvío masivo de correo electrónico y EOP</span><span class="sxs-lookup"><span data-stu-id="b6cb4-209">Backscatter messages and EOP</span></span>](https://technet.microsoft.com/en-us/library/dn499795%28v=exchg.150%29.aspx)
  

