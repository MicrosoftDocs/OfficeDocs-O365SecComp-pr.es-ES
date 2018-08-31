---
title: Forma en que Office 365 valida la dirección para evitar la suplantación de identidad
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 10/11/2017
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- OWC150
- MET150
ms.assetid: eef8408b-54d3-4d7d-9cf7-ad2af10b2e0e
description: 'Para ayudar a evitar la suplantación de identidad, Office 365 y Outlook.com ahora requieren cumplimiento del RFC desde: direcciones.'
ms.openlocfilehash: 562e08aa54cb6544beccb6f0e8760735f67b834b
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22535636"
---
# <a name="how-office-365-validates-the-from-address-to-prevent-phishing"></a><span data-ttu-id="b53f0-103">Forma en que Office 365 valida la dirección para evitar la suplantación de identidad</span><span class="sxs-lookup"><span data-stu-id="b53f0-103">How Office 365 validates the From address to prevent phishing</span></span>

<span data-ttu-id="b53f0-p101">Office 365 y las cuentas de correo electrónico de Outlook.com reciben un número cada vez mayor de los ataques de suplantación de identidad. Es una técnica los suplantadores de identidad usar enviar los mensajes que tienen valores para el campo de: dirección que no son compatibles con [RFC 5322](https://tools.ietf.org/html/rfc5322). Desde: dirección también se denomina la dirección 5322.From. Para ayudar a evitar que este tipo de suplantación de identidad, Office 365 y Outlook.com requieren los mensajes recibidos por el servicio para incluir un compatible con RFC desde: dirección tal y como se describe en este artículo.</span><span class="sxs-lookup"><span data-stu-id="b53f0-p101">Office 365 and Outlook.com email accounts receive an increasingly large number of phishing attacks. One technique phishers use is to send messages that have values for the From: address that are not compliant with [RFC 5322](https://tools.ietf.org/html/rfc5322). The From: address is also called the 5322.From address. To help prevent this type of phishing, Office 365 and Outlook.com require messages received by the service to include an RFC-compliant From: address as described in this article.</span></span>
  
> [!NOTE]
> <span data-ttu-id="b53f0-p102">La información de este artículo, es necesario tener un conocimiento básico del formato general de direcciones de correo electrónico. Para obtener más información, consulte [RFC 5322](https://tools.ietf.org/html/rfc5322) (especialmente en las secciones 3.2.3, 3.4 y 3.4.1), [RFC 5321](https://tools.ietf.org/html/rfc5321), así como [RFC 3696](https://tools.ietf.org/html/rfc3696). Este artículo trata sobre la aplicación de directivas para la dirección de 5322.From. Este artículo no trata sobre la dirección de 5321.MailFrom.</span><span class="sxs-lookup"><span data-stu-id="b53f0-p102">The information in this article requires you to have a basic understanding of the general format of email addresses. For more information, see [RFC 5322](https://tools.ietf.org/html/rfc5322) (particularly sections 3.2.3, 3.4, and 3.4.1), [RFC 5321](https://tools.ietf.org/html/rfc5321), as well as [RFC 3696](https://tools.ietf.org/html/rfc3696). This article is about policy enforcement for the 5322.From address. This article is not about the 5321.MailFrom address.</span></span> 
  
<span data-ttu-id="b53f0-p103">Desafortunadamente, aún hay algunos servidores de correo electrónico heredado en Internet que continuarán enviando "legítimos" mensajes de correo electrónico que tengan una falta o mal formados desde: dirección. Si recibe regularmente correo electrónico de las organizaciones que usan estos sistemas heredados, sugiera a esas organizaciones para actualizar sus servidores de correo para cumplir con los estándares de seguridad modernos.</span><span class="sxs-lookup"><span data-stu-id="b53f0-p103">Unfortunately, there are still some legacy email servers on the Internet that continue to send "legitimate" email messages that have a missing or malformed From: address. If you regularly receive email from organizations that use these legacy systems, encourage those organizations to update their mail servers to comply with modern security standards.</span></span>
  
<span data-ttu-id="b53f0-114">Se iniciará Microsoft implantar la aplicación de las directivas que se describen en este artículo en el 9 de noviembre de 2017.</span><span class="sxs-lookup"><span data-stu-id="b53f0-114">Microsoft will start rolling out enforcement of the policies described in this article on November 9, 2017.</span></span>
  
## <a name="how-office-365-enforces-the-use-of-a-valid-from-address-to-prevent-phishing-attacks"></a><span data-ttu-id="b53f0-115">Cómo Office 365 exige el uso de un valor válido desde: dirección para evitar los ataques de suplantación de identidad</span><span class="sxs-lookup"><span data-stu-id="b53f0-115">How Office 365 enforces the use of a valid From: address to prevent phishing attacks</span></span>

<span data-ttu-id="b53f0-p104">Office 365 está realizando cambios en la forma en exige el uso de From: dirección en los mensajes que recibe mejor con el fin de proteger al equipo contra los ataques de suplantación de identidad. En este artículo:</span><span class="sxs-lookup"><span data-stu-id="b53f0-p104">Office 365 is making changes to the way it enforces the use of the From: address in messages it receives in order to better protect you from phishing attacks. In this article:</span></span>
  
- [<span data-ttu-id="b53f0-118">Todos los mensajes deben incluir válido desde: dirección</span><span class="sxs-lookup"><span data-stu-id="b53f0-118">All messages must include a valid From: address</span></span>](how-office-365-validates-the-from-address.md#MustIncludeFromAddress)
    
- [<span data-ttu-id="b53f0-119">Todos los mensajes deben incluir válido desde: dirección</span><span class="sxs-lookup"><span data-stu-id="b53f0-119">All messages must include a valid From: address</span></span>](how-office-365-validates-the-from-address.md#MustIncludeFromAddress)
    
- [<span data-ttu-id="b53f0-120">Formato de From: si no incluye un nombre para mostrar de direcciones</span><span class="sxs-lookup"><span data-stu-id="b53f0-120">Format of the From: address if you don't include a display name</span></span>](how-office-365-validates-the-from-address.md#FormatNoDisplayName)
    
- [<span data-ttu-id="b53f0-121">Formato de From: si se incluye un nombre para mostrar de direcciones</span><span class="sxs-lookup"><span data-stu-id="b53f0-121">Format of the From: address if you include a display name</span></span>](how-office-365-validates-the-from-address.md#FormatDisplayName)
    
- [<span data-ttu-id="b53f0-122">Ejemplos adicionales de válidos y no válidos de: direcciones</span><span class="sxs-lookup"><span data-stu-id="b53f0-122">Additional examples of valid and invalid From: addresses</span></span>](how-office-365-validates-the-from-address.md#Examples)
    
- [<span data-ttu-id="b53f0-123">Suprimir las respuestas automáticas para su dominio personalizado sin interrumpir la From: directiva</span><span class="sxs-lookup"><span data-stu-id="b53f0-123">Suppress auto-replies to your custom domain without breaking the From: policy</span></span>](how-office-365-validates-the-from-address.md#SuppressAutoReply)
    
- [<span data-ttu-id="b53f0-124">Reemplazar el Office 365 desde: directiva de aplicación de direcciones</span><span class="sxs-lookup"><span data-stu-id="b53f0-124">Overriding the Office 365 From: address enforcement policy</span></span>](how-office-365-validates-the-from-address.md#Override)
    
- [<span data-ttu-id="b53f0-125">Otras maneras de prevenir y proteger contra cybercrimes en Office 365</span><span class="sxs-lookup"><span data-stu-id="b53f0-125">Other ways to prevent and protect against cybercrimes in Office 365</span></span>](how-office-365-validates-the-from-address.md#OtherProtection)
    
<span data-ttu-id="b53f0-126">Enviar en nombre de otro usuario no se ve afectado por este cambio, para obtener más información, lea el blog de Terry Zink "[Qué queremos decir cuando nos referimos a 'remitente' de un correo electrónico?](https://blogs.msdn.microsoft.com/tzink/2017/06/22/what-do-we-mean-when-we-refer-to-the-sender-of-an-email/)".</span><span class="sxs-lookup"><span data-stu-id="b53f0-126">Sending on behalf of another user is not affected by this change, for more details, read Terry Zink's blog "[What do we mean when we refer to the 'sender' of an email?](https://blogs.msdn.microsoft.com/tzink/2017/06/22/what-do-we-mean-when-we-refer-to-the-sender-of-an-email/)".</span></span>
  
### <a name="all-messages-must-include-a-valid-from-address"></a><span data-ttu-id="b53f0-127">Todos los mensajes deben incluir válido desde: dirección</span><span class="sxs-lookup"><span data-stu-id="b53f0-127">All messages must include a valid From: address</span></span>
<span data-ttu-id="b53f0-128"><a name="MustIncludeFromAddress"> </a></span><span class="sxs-lookup"><span data-stu-id="b53f0-128"></span></span>

<span data-ttu-id="b53f0-p105">Algunos mensajes automatizadas no incluyen un desde: dirección cuando se envían. En el pasado, cuando Office 365 o Outlook.com recibe un mensaje sin un desde: dirección, el servicio agrega el siguiente valor predeterminado de: dirección al mensaje con el fin de facilitar la entrega:</span><span class="sxs-lookup"><span data-stu-id="b53f0-p105">Some automated messages don't include a From: address when they are sent. In the past, when Office 365 or Outlook.com received a message without a From: address, the service added the following default From: address to the message in order to make it deliverable:</span></span>
  
```
From: <>
```

<span data-ttu-id="b53f0-p106">Iniciar el 9 de noviembre de 2017 Office 365 va a ser implantar los cambios a sus servidores de correo electrónico y centros de datos que va a aplicar una nueva regla de donde los mensajes sin un desde: dirección ya no se aceptará por Office 365 o Outlook.com. En su lugar, todos los mensajes recibidos por Office 365 ya deben contener un valor válido desde: dirección. De lo contrario, el mensaje se enviará a las carpetas el correo electrónico no deseado o elementos eliminados en Outlook.com y Office 365.</span><span class="sxs-lookup"><span data-stu-id="b53f0-p106">Starting November 9, 2017, Office 365 will be rolling out changes to its datacenters and mail servers which will enforce a new rule where messages without a From: address will no longer be accepted by Office 365 or Outlook.com. Instead, all messages received by Office 365 must already contain a valid From: address. Otherwise, the message will be sent to either the Junk Email or Deleted Items folders in Outlook.com and Office 365.</span></span> 
  
### <a name="syntax-overview-valid-format-for-the-from-address-for-office-365"></a><span data-ttu-id="b53f0-134">Introducción a la sintaxis: formato válido para el campo de: dirección para Office 365</span><span class="sxs-lookup"><span data-stu-id="b53f0-134">Syntax overview: Valid format for the From: address for Office 365</span></span>
<span data-ttu-id="b53f0-135"><a name="SyntaxOverviewFromAddress"> </a></span><span class="sxs-lookup"><span data-stu-id="b53f0-135"></span></span>

<span data-ttu-id="b53f0-p107">El formato para el valor de From: dirección se define en detalle a través de varias de las solicitudes de cambio. Existen muchas variaciones en la solución y qué puede considerarse válido o no es válido. Para mantenerlo simple, Microsoft recomienda que utilice las definiciones y el siguiente formato:</span><span class="sxs-lookup"><span data-stu-id="b53f0-p107">The format for the value of the From: address is defined in detail across several RFCs. There are many variations on addressing and what may be considered valid or invalid. To keep it simple, Microsoft recommends that you use the following format and definitions:</span></span>
  
```
From: "displayname " <emailaddress >
```

<span data-ttu-id="b53f0-139">Donde:</span><span class="sxs-lookup"><span data-stu-id="b53f0-139">Where:</span></span>
  
- <span data-ttu-id="b53f0-p108">(Opcional)  *DisplayName* es una frase que describa el propietario de la dirección de correo electrónico. Por ejemplo, esto podría ser un nombre más fácil de usar para describir el remitente que el nombre del buzón. Uso de un nombre para mostrar es opcional. Sin embargo, si decide utilizar un nombre para mostrar, Microsoft recomienda que se siempre encerrarlo entre comillas tal como se muestra.</span><span class="sxs-lookup"><span data-stu-id="b53f0-p108">(Optional)  *displayname*  is a phrase that describes the owner of the email address. For example, this might be a more user-friendly name to describe the sender than the name of the mailbox. Using a display name is optional. However, if you choose to use a display name, Microsoft recommends that you always enclose it within quotation marks as shown.</span></span> 
    
- <span data-ttu-id="b53f0-144">(Obligatorio)  *EmailAddress* se compone de:</span><span class="sxs-lookup"><span data-stu-id="b53f0-144">(Required)  *emailaddress*  is made up of:</span></span> 
    
  ```
  local-part @domain
  ```

    <span data-ttu-id="b53f0-145">Donde:</span><span class="sxs-lookup"><span data-stu-id="b53f0-145">Where:</span></span>
    
  - <span data-ttu-id="b53f0-p109">(Obligatorio)  *parte a local* es una cadena que identifica el buzón asociado con la dirección. Esto es único dentro del dominio. A menudo, nombre de usuario o el GUID del propietario del buzón se usa como el valor para la parte local.</span><span class="sxs-lookup"><span data-stu-id="b53f0-p109">(Required)  *local-part*  is a string that identifies the mailbox associated with the address. This is unique within the domain. Often, the mailbox owner's username or GUID is used as the value for the local-part.</span></span> 
    
  - <span data-ttu-id="b53f0-149">(Obligatorio)  *dominio* es el nombre de dominio completo (FQDN) del servidor de correo que hospeda el buzón de correo identificado por la parte local de la dirección de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="b53f0-149">(Required)  *domain*  is the fully-qualified domain name (FQDN) of the mail server that hosts the mailbox identified by the local-part of the email address.</span></span> 
    
### <a name="format-of-the-from-address-if-you-dont-include-a-display-name"></a><span data-ttu-id="b53f0-150">Formato de From: si no incluye un nombre para mostrar de direcciones</span><span class="sxs-lookup"><span data-stu-id="b53f0-150">Format of the From: address if you don't include a display name</span></span>
<span data-ttu-id="b53f0-151"><a name="FormatNoDisplayName"> </a></span><span class="sxs-lookup"><span data-stu-id="b53f0-151"></span></span>

<span data-ttu-id="b53f0-p110">Un formato adecuado de: dirección que no incluya un nombre para mostrar incluye sólo una dirección de correo electrónico única con o sin corchetes angulares. Microsoft recomienda no separe los corchetes angulares con espacios. Además, no incluyen nada después de la dirección de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="b53f0-p110">A properly formatted From: address that does not include a display name includes only a single email address with or without angle brackets. Microsoft recommends that you do not separate the angle brackets with spaces. In addition, don't include anything after the email address.</span></span>
  
<span data-ttu-id="b53f0-155">En los ejemplos siguientes son válidos:</span><span class="sxs-lookup"><span data-stu-id="b53f0-155">The following examples are valid:</span></span>
  
```
From: sender@contoso.com
```

```
From: <sender@contoso.com>
```

<span data-ttu-id="b53f0-156">El ejemplo siguiente es válido pero no se recomienda porque contiene espacios entre los corchetes angulares y la dirección de correo electrónico:</span><span class="sxs-lookup"><span data-stu-id="b53f0-156">The following example is valid but not recommended because it contains spaces between the angle brackets and the email address:</span></span>
  
```
From: < sender@contoso.com >
```

<span data-ttu-id="b53f0-157">En el siguiente ejemplo no es válido porque contiene texto después de la dirección de correo electrónico:</span><span class="sxs-lookup"><span data-stu-id="b53f0-157">The following example is invalid because it contains text after the email address:</span></span>
  
```
From: "Office 365" <sender@contoso.com> (Sent by a process)
```

### <a name="format-of-the-from-address-if-you-include-a-display-name"></a><span data-ttu-id="b53f0-158">Formato de From: si se incluye un nombre para mostrar de direcciones</span><span class="sxs-lookup"><span data-stu-id="b53f0-158">Format of the From: address if you include a display name</span></span>
<span data-ttu-id="b53f0-159"><a name="FormatDisplayName"> </a></span><span class="sxs-lookup"><span data-stu-id="b53f0-159"></span></span>

<span data-ttu-id="b53f0-160">Para desde: las direcciones que incluyen un valor para el nombre para mostrar, que se aplican las siguientes reglas:</span><span class="sxs-lookup"><span data-stu-id="b53f0-160">For From: addresses that include a value for the display name, the following rules apply:</span></span>
  
- <span data-ttu-id="b53f0-p111">Si la dirección del remitente incluye un nombre para mostrar y el nombre para mostrar incluye una coma, a continuación, el nombre para mostrar debe estar incluido entre comillas. Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="b53f0-p111">If the sender address includes a display name, and the display name includes a comma, then the display name must be enclosed within quotation marks. For example:</span></span>
    
    <span data-ttu-id="b53f0-163">El ejemplo siguiente es válido:</span><span class="sxs-lookup"><span data-stu-id="b53f0-163">The following example is valid:</span></span>
    
  ```
  From: "Sender, Example" <sender.example@contoso.com>
  ```

    <span data-ttu-id="b53f0-164">En el siguiente ejemplo no es válido:</span><span class="sxs-lookup"><span data-stu-id="b53f0-164">The following example is not valid:</span></span>
    
  ```
  From: Sender, Example <sender.example@contoso.com>
  ```

    <span data-ttu-id="b53f0-165">No incluir el nombre para mostrar entre comillas si ese nombre para mostrar incluye una coma es válido de acuerdo con RFC 5322.</span><span class="sxs-lookup"><span data-stu-id="b53f0-165">Not enclosing the display name in quotation marks if that display name includes a comma is invalid according to RFC 5322.</span></span>
    
    <span data-ttu-id="b53f0-166">Como procedimiento recomendado, put comillas alrededor del nombre para mostrar, independientemente de si existe o no es una coma en el nombre para mostrar.</span><span class="sxs-lookup"><span data-stu-id="b53f0-166">As a best practice, put quote marks around the display name regardless of whether or not there is a comma within the display name.</span></span>
    
- <span data-ttu-id="b53f0-167">Si la dirección del remitente incluye un nombre para mostrar, la dirección de correo electrónico debe ir entre corchetes angulares.</span><span class="sxs-lookup"><span data-stu-id="b53f0-167">If the sender address includes a display name, then the email address must be enclosed within angle brackets.</span></span>
    
    <span data-ttu-id="b53f0-168">Como práctica recomendada, Microsoft recomienda encarecidamente que insertar un espacio entre el nombre para mostrar y la dirección de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="b53f0-168">As a best practice, Microsoft strongly recommends that you insert a space between the display name and the email address.</span></span>
    
### <a name="additional-examples-of-valid-and-invalid-from-addresses"></a><span data-ttu-id="b53f0-169">Ejemplos adicionales de válidos y no válidos de: direcciones</span><span class="sxs-lookup"><span data-stu-id="b53f0-169">Additional examples of valid and invalid From: addresses</span></span>
<span data-ttu-id="b53f0-170"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="b53f0-170"></span></span>

- <span data-ttu-id="b53f0-171">Válido:</span><span class="sxs-lookup"><span data-stu-id="b53f0-171">Valid:</span></span>
    
  ```
  From: "Office 365" <sender@contoso.com>
  ```

- <span data-ttu-id="b53f0-p112">No válido. La dirección de correo electrónico no se incluye con corchetes angulares:</span><span class="sxs-lookup"><span data-stu-id="b53f0-p112">Invalid. The email address is not enclosed with angle brackets:</span></span>
    
  ```
  From: Office 365 sender@contoso.com
  ```

- <span data-ttu-id="b53f0-p113">Válido, pero no se recomienda. El nombre para mostrar no está en comillas. Como procedimiento recomendado, ponga siempre comillas en el nombre para mostrar:</span><span class="sxs-lookup"><span data-stu-id="b53f0-p113">Valid, but not recommended. The display name is not in quotes. As a best practice, always put quotation marks around the display name:</span></span>
    
  ```
  From: Office 365 <sender@contoso.com>
  ```

- <span data-ttu-id="b53f0-p114">No válido. Todo lo que está incluido entre comillas, no sólo el nombre para mostrar:</span><span class="sxs-lookup"><span data-stu-id="b53f0-p114">Invalid. Everything is enclosed within quotation marks, not just the display name:</span></span>
    
  ```
  From: "Office 365 <sender@contoso.com>"
  ```

- <span data-ttu-id="b53f0-p115">No válido. No hay ningún corchetes angulares alrededor de la dirección de correo electrónico:</span><span class="sxs-lookup"><span data-stu-id="b53f0-p115">Invalid. There are no angle brackets around the email address:</span></span>
    
  ```
  From: "Office 365 <sender@contoso.com>" sender@contoso.com
  ```

- <span data-ttu-id="b53f0-p116">No válido. No hay ningún espacio entre el nombre para mostrar y el corchete angular de apertura:</span><span class="sxs-lookup"><span data-stu-id="b53f0-p116">Invalid. There is no space between the display name and left angle bracket:</span></span>
    
  ```
  From: Office 365<sender@contoso.com>
  ```

- <span data-ttu-id="b53f0-p117">No válido. No hay ningún espacio entre el quotation mark cierre alrededor el nombre para mostrar y el corchete angular.</span><span class="sxs-lookup"><span data-stu-id="b53f0-p117">Invalid. There is no space between the closing quotation mark around the display name and the left angle bracket.</span></span>
    
  ```
  From: "Office 365"<sender@contoso.com>
  ```

### <a name="suppress-auto-replies-to-your-custom-domain-without-breaking-the-from-policy"></a><span data-ttu-id="b53f0-185">Suprimir las respuestas automáticas para su dominio personalizado sin interrumpir la From: directiva</span><span class="sxs-lookup"><span data-stu-id="b53f0-185">Suppress auto-replies to your custom domain without breaking the From: policy</span></span>
<span data-ttu-id="b53f0-186"><a name="SuppressAutoReply"> </a></span><span class="sxs-lookup"><span data-stu-id="b53f0-186"></span></span>

<span data-ttu-id="b53f0-p118">Con el nuevo a partir de: aplicación de directivas, ya no se puede usar desde: \< \> para suprimir las respuestas automáticas. En su lugar, debe configurar un registro MX null para su dominio personalizado.</span><span class="sxs-lookup"><span data-stu-id="b53f0-p118">With the new From: policy enforcement, you can no longer use From: \<\> to suppress auto-replies. Instead, you need to set up a null MX record for your custom domain.</span></span>
  
<span data-ttu-id="b53f0-p119">El registro de intercambio (MX) de correo es un registro de recursos de DNS que identifica el servidor de correo que recibe el correo para su dominio. Las respuestas automáticas (y todas las respuestas) con naturalidad se suprimen porque no hay ninguna dirección publicada a la que el servidor de respuesta puede enviar mensajes.</span><span class="sxs-lookup"><span data-stu-id="b53f0-p119">The mail exchanger (MX) record is a resource record in DNS that identifies the mail server that receives mail for your domain. Auto-replies (and all replies) are naturally suppressed because there is no published address to which the responding server can send messages.</span></span>
  
<span data-ttu-id="b53f0-191">Al configurar un registro MX nulo para su dominio personalizado:</span><span class="sxs-lookup"><span data-stu-id="b53f0-191">When you set up a null MX record for your custom domain:</span></span>
  
- <span data-ttu-id="b53f0-p120">Elija un dominio desde el que se va a enviar los mensajes que no acepta (recibir) correo electrónico. Por ejemplo, si su dominio principal es contoso.com, es posible que elija noreply.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="b53f0-p120">Choose a domain from which to send messages that doesn't accept (receive) email. For example, if your primary domain is contoso.com, you might choose noreply.contoso.com.</span></span>
    
- <span data-ttu-id="b53f0-p121">Configurar el registro MX null para su dominio. Un registro MX null consta de un único punto, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="b53f0-p121">Set up the null MX record for your domain. A null MX record consists of a single dot, for example:</span></span>
    
  ```
  noreply.contoso.com IN MX .
  ```

<span data-ttu-id="b53f0-196">Para obtener más información acerca de cómo publicar un null MX, consulte [RFC 7505](https://tools.ietf.org/html/rfc7505).</span><span class="sxs-lookup"><span data-stu-id="b53f0-196">For more information about publishing a null MX, see [RFC 7505](https://tools.ietf.org/html/rfc7505).</span></span>
  
### <a name="overriding-the-office-365-from-address-enforcement-policy"></a><span data-ttu-id="b53f0-197">Reemplazar el Office 365 desde: directiva de aplicación de direcciones</span><span class="sxs-lookup"><span data-stu-id="b53f0-197">Overriding the Office 365 From: address enforcement policy</span></span>
<span data-ttu-id="b53f0-198"><a name="Override"> </a></span><span class="sxs-lookup"><span data-stu-id="b53f0-198"></span></span>

<span data-ttu-id="b53f0-199">Una vez finalizada la implementación de la nueva directiva, solo puede omitir esta directiva para el correo entrante que recibe de Office 365 mediante uno de los métodos siguientes:</span><span class="sxs-lookup"><span data-stu-id="b53f0-199">Once roll out of the new policy is complete, you can only bypass this policy for inbound mail you receive from Office 365 by using one of the following methods:</span></span> 
  
- <span data-ttu-id="b53f0-200">Listas de direcciones IP permitidas</span><span class="sxs-lookup"><span data-stu-id="b53f0-200">IP allow lists</span></span>
    
- <span data-ttu-id="b53f0-201">Reglas de flujo de correo de Exchange Online</span><span class="sxs-lookup"><span data-stu-id="b53f0-201">Exchange Online mail flow rules</span></span>
    
<span data-ttu-id="b53f0-p122">Microsoft recomienda encarecidamente reemplazar el cumplimiento de From: directiva. Reemplazar esta directiva puede aumentar el riesgo de la organización de exposición a correo no deseado, suplantación de identidad y otros cybercrimes.</span><span class="sxs-lookup"><span data-stu-id="b53f0-p122">Microsoft strongly recommends against overriding the enforcement of the From: policy. Overriding this policy can increase your organization's risk of exposure to spam, phishing, and other cybercrimes.</span></span>
  
<span data-ttu-id="b53f0-p123">No se puede invalidar esta directiva para el correo saliente que se envía en Office 365. Además, Outlook.com no le permitirá invalidaciones de ningún tipo, incluso a través de soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="b53f0-p123">You cannot override this policy for outbound mail you send in Office 365. In addition, Outlook.com will not allow overrides of any kind, even through support.</span></span> 
  
### <a name="other-ways-to-prevent-and-protect-against-cybercrimes-in-office-365"></a><span data-ttu-id="b53f0-206">Otras maneras de prevenir y proteger contra cybercrimes en Office 365</span><span class="sxs-lookup"><span data-stu-id="b53f0-206">Other ways to prevent and protect against cybercrimes in Office 365</span></span>
<span data-ttu-id="b53f0-207"><a name="OtherProtection"> </a></span><span class="sxs-lookup"><span data-stu-id="b53f0-207"></span></span>

<span data-ttu-id="b53f0-208">Para obtener más información sobre cómo se puede reforzar su organización contra cybercrimes como suplantación de identidad, spam, violaciones de datos y otras amenazas, vea [procedimientos recomendados de seguridad para Office 365](https://support.office.com/article/9295e396-e53d-49b9-ae9b-0b5828cdedc3).</span><span class="sxs-lookup"><span data-stu-id="b53f0-208">For more information on how you can strengthen your organization against cybercrimes like phishing, spamming, data breaches, and other threats, see [Security best practices for Office 365](https://support.office.com/article/9295e396-e53d-49b9-ae9b-0b5828cdedc3).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="b53f0-209">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="b53f0-209">Related Topics</span></span>

[<span data-ttu-id="b53f0-210">Mensajes de reenvío masivo de correo electrónico y EOP</span><span class="sxs-lookup"><span data-stu-id="b53f0-210">Backscatter messages and EOP</span></span>](https://technet.microsoft.com/en-us/library/dn499795%28v=exchg.150%29.aspx)
  

