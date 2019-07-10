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
# <a name="how-office-365-validates-the-from-address-to-prevent-phishing"></a>Cómo Office 365 valida la dirección from para evitar la suplantación de identidad

Las cuentas de correo electrónico de Office 365 y Outlook.com reciben un número cada vez mayor de ataques de suplantación de identidad. Una técnica que usan los phishs es enviar mensajes que tienen valores para la dirección de: que no son compatibles con [RFC 5322](https://tools.ietf.org/html/rfc5322). La dirección de: también se llama la dirección 5322. from. Para ayudar a evitar este tipo de suplantación de identidad, Office 365 y Outlook.com requieren mensajes recibidos por el servicio para incluir una dirección compatible con RFC de: Address tal como se describe en este artículo.
  
> [!NOTE]
> La información de este artículo le obliga a tener un conocimiento básico del formato general de las direcciones de correo electrónico. Para obtener más información, vea [rfc 5322](https://tools.ietf.org/html/rfc5322) (en particular las secciones 3.2.3, 3,4 y 3.4.1), [RFC 5321](https://tools.ietf.org/html/rfc5321), así como [RFC 3696](https://tools.ietf.org/html/rfc3696). Este artículo trata sobre la aplicación de directivas para la dirección 5322. from. Este artículo no trata sobre la dirección 5321. MailFrom. 
  
Desafortunadamente, todavía hay algunos servidores de correo electrónico heredados en Internet que continúan enviando mensajes de correo electrónico "legítimos" que tienen una dirección de: que faltan o tienen un formato incorrecto. Si recibe regularmente correo electrónico de organizaciones que usan estos sistemas heredados, Anime a esas organizaciones a que actualicen sus servidores de correo para cumplir con los estándares de seguridad modernos.
  
Microsoft empezará a implementar la aplicación de las directivas descritas en este artículo el 9 de noviembre de 2017.
  
## <a name="how-office-365-enforces-the-use-of-a-valid-from-address-to-prevent-phishing-attacks"></a>Cómo Office 365 exige el uso de una dirección from: Address válida para evitar ataques de suplantación de identidad (phishing)

Office 365 está realizando cambios en la forma en que aplica el uso de la dirección de: en los mensajes que recibe para proteger mejor de los ataques de suplantación de identidad (phishing). En este artículo:
  
- [Todos los mensajes deben incluir una dirección from válida from:](how-office-365-validates-the-from-address.md#MustIncludeFromAddress)
    
- [Formato de la dirección de: Si no incluye un nombre para mostrar](how-office-365-validates-the-from-address.md#FormatNoDisplayName)
    
- [Formato de la dirección de: si incluye un nombre para mostrar](how-office-365-validates-the-from-address.md#FormatDisplayName)
    
- [Ejemplos adicionales de direcciones válidas y no válidas:](how-office-365-validates-the-from-address.md#Examples)
    
- [Suprimir las respuestas automáticas a su dominio personalizado sin romper la Directiva de:](how-office-365-validates-the-from-address.md#SuppressAutoReply)
    
- [Reemplazar el Office 365 de: Directiva de aplicación de direcciones](how-office-365-validates-the-from-address.md#Override)
    
- [Otras formas de evitar y proteger contra cybercrimes en Office 365](how-office-365-validates-the-from-address.md#OtherProtection)
    
El envío en nombre de otro usuario no se ve afectado por este cambio, para obtener más información, lea el blog de Tomás Zink "[¿Qué significa cuando hacemos referencia al" remitente "de un correo electrónico?](https://blogs.msdn.microsoft.com/tzink/2017/06/22/what-do-we-mean-when-we-refer-to-the-sender-of-an-email/)".
  
### <a name="all-messages-must-include-a-valid-from-address"></a>Todos los mensajes deben incluir una dirección from válida from:
<a name="MustIncludeFromAddress"> </a>

Algunos mensajes automatizados no incluyen una dirección de: cuando se envían. En el pasado, cuando Office 365 o Outlook.com recibía un mensaje sin una dirección de:, el servicio agregaba la siguiente dirección siguiente predeterminada desde: al mensaje para hacerla entregar:
  
```
From: <>
```

A partir del 9 de noviembre de 2017, Office 365 se implementarán cambios en sus centros de información y servidores de correo que aplicarán una nueva regla en la que Office 365 o Outlook.com no aceptarán mensajes sin una dirección de:. En su lugar, todos los mensajes que recibe Office 365 ya deben contener una dirección from: válida. De lo contrario, el mensaje se enviará a las carpetas correo no deseado o elementos eliminados de Outlook.com y Office 365. 
  
### <a name="syntax-overview-valid-format-for-the-from-address-for-office-365"></a>Información general sobre la sintaxis: formato válido para la dirección de: para Office 365
<a name="SyntaxOverviewFromAddress"> </a>

El formato del valor de la dirección de: se define en detalle en varias RFC. Hay muchas variaciones en el direccionamiento y lo que puede considerarse válido o no válido. Para mantenerlo sencillo, Microsoft recomienda usar el siguiente formato y las siguientes definiciones:
  
```
From: "displayname " <emailaddress >
```

Donde:
  
- Opcional  *displayName* es una frase que describe el propietario de la dirección de correo electrónico. Por ejemplo, podría tratarse de un nombre más descriptivo para describir al remitente que el nombre del buzón. El uso de un nombre para mostrar es opcional. Sin embargo, si decide usar un nombre para mostrar, Microsoft recomienda que siempre lo entre entre comillas como se muestra. 
    
- Necesarios  *EmailAddress* consta de: 
    
  ```
  local-part @domain
  ```

    Donde:
    
  - Necesarios  la *parte local* es una cadena que identifica el buzón asociado con la dirección. Esto es único dentro del dominio. A menudo, el GUID o el nombre de usuario del propietario del buzón se usa como el valor de la parte local. 
    
  - Necesarios  *Domain* es el nombre de dominio completo (FQDN) del servidor de correo que hospeda el buzón identificado por la parte local de la dirección de correo electrónico. 
    
### <a name="format-of-the-from-address-if-you-dont-include-a-display-name"></a>Formato de la dirección de: Si no incluye un nombre para mostrar
<a name="FormatNoDisplayName"> </a>

Un formato adecuado de: Address que no incluye un nombre para mostrar solo incluye una dirección de correo electrónico con o sin corchetes angulares. Microsoft recomienda que no separe los corchetes angulares con espacios. Además, no incluya nada después de la dirección de correo electrónico.
  
Los ejemplos siguientes son válidos:
  
```
From: sender@contoso.com
```

```
From: <sender@contoso.com>
```

El siguiente ejemplo es válido pero no se recomienda porque contiene espacios entre los corchetes angulares y la dirección de correo electrónico:
  
```
From: < sender@contoso.com >
```

El siguiente ejemplo no es válido porque contiene texto después de la dirección de correo electrónico:
  
```
From: "Office 365" <sender@contoso.com> (Sent by a process)
```

### <a name="format-of-the-from-address-if-you-include-a-display-name"></a>Formato de la dirección de: si incluye un nombre para mostrar
<a name="FormatDisplayName"> </a>

En el caso de las direcciones de: que incluyen un valor para el nombre para mostrar, se aplican las siguientes reglas:
  
- Si la dirección del remitente incluye un nombre para mostrar y el nombre para mostrar incluye una coma, el nombre para mostrar debe ir entre comillas. Por ejemplo:
    
    El siguiente ejemplo es válido:
    
  ```
  From: "Sender, Example" <sender.example@contoso.com>
  ```

    El siguiente ejemplo no es válido:
    
  ```
  From: Sender, Example <sender.example@contoso.com>
  ```

    El nombre para mostrar no se cierra entre comillas si el nombre para mostrar incluye una coma de acuerdo con RFC 5322.
    
    Como práctica recomendada, coloque las comillas alrededor del nombre para mostrar independientemente de si hay una coma dentro del nombre para mostrar.
    
- Si la dirección del remitente incluye un nombre para mostrar, la dirección de correo electrónico debe estar entre corchetes angulares.
    
    Como práctica recomendada, Microsoft recomienda encarecidamente que inserte un espacio entre el nombre para mostrar y la dirección de correo electrónico.
    
### <a name="additional-examples-of-valid-and-invalid-from-addresses"></a>Ejemplos adicionales de direcciones válidas y no válidas:
<a name="Examples"> </a>

- Validación
    
  ```
  From: "Office 365" <sender@contoso.com>
  ```

- No válido. La dirección de correo electrónico no se incluye entre corchetes angulares:
    
  ```
  From: Office 365 sender@contoso.com
  ```

- Válido, pero no se recomienda. El nombre para mostrar no está entre comillas. Como práctica recomendada, escriba siempre comillas alrededor del nombre para mostrar:
    
  ```
  From: Office 365 <sender@contoso.com>
  ```

- No válido. Todo se encierra entre comillas, no solo el nombre para mostrar:
    
  ```
  From: "Office 365 <sender@contoso.com>"
  ```

- No válido. No hay paréntesis angulares alrededor de la dirección de correo electrónico:
    
  ```
  From: "Office 365 <sender@contoso.com>" sender@contoso.com
  ```

- No válido. No hay ningún espacio entre el nombre para mostrar y el corchete angular izquierdo:
    
  ```
  From: Office 365<sender@contoso.com>
  ```

- No válido. No hay ningún espacio entre el comillas de cierre que rodea el nombre para mostrar y el corchete angular de apertura.
    
  ```
  From: "Office 365"<sender@contoso.com>
  ```

### <a name="suppress-auto-replies-to-your-custom-domain-without-breaking-the-from-policy"></a>Suprimir las respuestas automáticas a su dominio personalizado sin romper la Directiva de:
<a name="SuppressAutoReply"> </a>

Con el nuevo de: aplicación de Directiva, ya no podrá usar de: \< \> para suprimir las respuestas automáticas. En su lugar, debe configurar un registro MX nulo para el dominio personalizado.
  
El registro de intercambio de correo (MX) es un registro de recursos en DNS que identifica el servidor de correo que recibe el correo de su dominio. Las respuestas automáticas (y todas las respuestas) se suprimen naturalmente porque no hay ninguna dirección publicada a la que el servidor que responde puede enviar mensajes.
  
Cuando se configura un registro MX nulo para el dominio personalizado:
  
- Elija un dominio desde el que enviar mensajes que no acepten (reciban) correo electrónico. Por ejemplo, si su dominio principal es contoso.com, puede elegir noreply.contoso.com.
    
- Configurar el registro MX nulo para el dominio. Un registro MX nulo consta de un único punto, por ejemplo:
    
  ```
  noreply.contoso.com IN MX .
  ```

Para obtener más información acerca de la publicación de un MX nulo, consulte [RFC 7505](https://tools.ietf.org/html/rfc7505).
  
### <a name="overriding-the-office-365-from-address-enforcement-policy"></a>Reemplazar el Office 365 de: Directiva de aplicación de direcciones
<a name="Override"> </a>

Una vez completada la implementación de la nueva Directiva, solo puede omitir esta directiva para el correo entrante que reciba de Office 365 mediante uno de los siguientes métodos: 
  
- Listas de direcciones IP permitidas
    
- Reglas de flujo de correo de Exchange Online
    
Microsoft recomienda encarecidamente no invalidar la obligatoriedad de la Directiva de:. Invalidar esta Directiva puede aumentar el riesgo de exposición de la organización al correo no deseado, la suplantación de identidad (phishing) y otros cybercrimes.
  
No puede invalidar esta directiva para el correo saliente que envíe en Office 365. Además, Outlook.com no permitirá invalidaciones de ningún tipo, incluso a través del soporte técnico. 
  
### <a name="other-ways-to-prevent-and-protect-against-cybercrimes-in-office-365"></a>Otras formas de evitar y proteger contra cybercrimes en Office 365
<a name="OtherProtection"> </a>

Para obtener más información sobre cómo fortalecer la organización frente a cybercrimes como suplantación de identidad, correo no deseado, infracciones de datos y otras amenazas, vea [Security Best Practices for Office 365](https://support.office.com/article/9295e396-e53d-49b9-ae9b-0b5828cdedc3).
  
## <a name="related-topics"></a>Temas relacionados

[Mensajes de reenvío masivo de correo electrónico y EOP](https://technet.microsoft.com/en-us/library/dn499795%28v=exchg.150%29.aspx)
  

