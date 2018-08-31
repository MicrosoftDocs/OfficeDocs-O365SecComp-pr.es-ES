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
# <a name="how-office-365-validates-the-from-address-to-prevent-phishing"></a>Forma en que Office 365 valida la dirección para evitar la suplantación de identidad

Office 365 y las cuentas de correo electrónico de Outlook.com reciben un número cada vez mayor de los ataques de suplantación de identidad. Es una técnica los suplantadores de identidad usar enviar los mensajes que tienen valores para el campo de: dirección que no son compatibles con [RFC 5322](https://tools.ietf.org/html/rfc5322). Desde: dirección también se denomina la dirección 5322.From. Para ayudar a evitar que este tipo de suplantación de identidad, Office 365 y Outlook.com requieren los mensajes recibidos por el servicio para incluir un compatible con RFC desde: dirección tal y como se describe en este artículo.
  
> [!NOTE]
> La información de este artículo, es necesario tener un conocimiento básico del formato general de direcciones de correo electrónico. Para obtener más información, consulte [RFC 5322](https://tools.ietf.org/html/rfc5322) (especialmente en las secciones 3.2.3, 3.4 y 3.4.1), [RFC 5321](https://tools.ietf.org/html/rfc5321), así como [RFC 3696](https://tools.ietf.org/html/rfc3696). Este artículo trata sobre la aplicación de directivas para la dirección de 5322.From. Este artículo no trata sobre la dirección de 5321.MailFrom. 
  
Desafortunadamente, aún hay algunos servidores de correo electrónico heredado en Internet que continuarán enviando "legítimos" mensajes de correo electrónico que tengan una falta o mal formados desde: dirección. Si recibe regularmente correo electrónico de las organizaciones que usan estos sistemas heredados, sugiera a esas organizaciones para actualizar sus servidores de correo para cumplir con los estándares de seguridad modernos.
  
Se iniciará Microsoft implantar la aplicación de las directivas que se describen en este artículo en el 9 de noviembre de 2017.
  
## <a name="how-office-365-enforces-the-use-of-a-valid-from-address-to-prevent-phishing-attacks"></a>Cómo Office 365 exige el uso de un valor válido desde: dirección para evitar los ataques de suplantación de identidad

Office 365 está realizando cambios en la forma en exige el uso de From: dirección en los mensajes que recibe mejor con el fin de proteger al equipo contra los ataques de suplantación de identidad. En este artículo:
  
- [Todos los mensajes deben incluir válido desde: dirección](how-office-365-validates-the-from-address.md#MustIncludeFromAddress)
    
- [Todos los mensajes deben incluir válido desde: dirección](how-office-365-validates-the-from-address.md#MustIncludeFromAddress)
    
- [Formato de From: si no incluye un nombre para mostrar de direcciones](how-office-365-validates-the-from-address.md#FormatNoDisplayName)
    
- [Formato de From: si se incluye un nombre para mostrar de direcciones](how-office-365-validates-the-from-address.md#FormatDisplayName)
    
- [Ejemplos adicionales de válidos y no válidos de: direcciones](how-office-365-validates-the-from-address.md#Examples)
    
- [Suprimir las respuestas automáticas para su dominio personalizado sin interrumpir la From: directiva](how-office-365-validates-the-from-address.md#SuppressAutoReply)
    
- [Reemplazar el Office 365 desde: directiva de aplicación de direcciones](how-office-365-validates-the-from-address.md#Override)
    
- [Otras maneras de prevenir y proteger contra cybercrimes en Office 365](how-office-365-validates-the-from-address.md#OtherProtection)
    
Enviar en nombre de otro usuario no se ve afectado por este cambio, para obtener más información, lea el blog de Terry Zink "[Qué queremos decir cuando nos referimos a 'remitente' de un correo electrónico?](https://blogs.msdn.microsoft.com/tzink/2017/06/22/what-do-we-mean-when-we-refer-to-the-sender-of-an-email/)".
  
### <a name="all-messages-must-include-a-valid-from-address"></a>Todos los mensajes deben incluir válido desde: dirección
<a name="MustIncludeFromAddress"> </a>

Algunos mensajes automatizadas no incluyen un desde: dirección cuando se envían. En el pasado, cuando Office 365 o Outlook.com recibe un mensaje sin un desde: dirección, el servicio agrega el siguiente valor predeterminado de: dirección al mensaje con el fin de facilitar la entrega:
  
```
From: <>
```

Iniciar el 9 de noviembre de 2017 Office 365 va a ser implantar los cambios a sus servidores de correo electrónico y centros de datos que va a aplicar una nueva regla de donde los mensajes sin un desde: dirección ya no se aceptará por Office 365 o Outlook.com. En su lugar, todos los mensajes recibidos por Office 365 ya deben contener un valor válido desde: dirección. De lo contrario, el mensaje se enviará a las carpetas el correo electrónico no deseado o elementos eliminados en Outlook.com y Office 365. 
  
### <a name="syntax-overview-valid-format-for-the-from-address-for-office-365"></a>Introducción a la sintaxis: formato válido para el campo de: dirección para Office 365
<a name="SyntaxOverviewFromAddress"> </a>

El formato para el valor de From: dirección se define en detalle a través de varias de las solicitudes de cambio. Existen muchas variaciones en la solución y qué puede considerarse válido o no es válido. Para mantenerlo simple, Microsoft recomienda que utilice las definiciones y el siguiente formato:
  
```
From: "displayname " <emailaddress >
```

Donde:
  
- (Opcional)  *DisplayName* es una frase que describa el propietario de la dirección de correo electrónico. Por ejemplo, esto podría ser un nombre más fácil de usar para describir el remitente que el nombre del buzón. Uso de un nombre para mostrar es opcional. Sin embargo, si decide utilizar un nombre para mostrar, Microsoft recomienda que se siempre encerrarlo entre comillas tal como se muestra. 
    
- (Obligatorio)  *EmailAddress* se compone de: 
    
  ```
  local-part @domain
  ```

    Donde:
    
  - (Obligatorio)  *parte a local* es una cadena que identifica el buzón asociado con la dirección. Esto es único dentro del dominio. A menudo, nombre de usuario o el GUID del propietario del buzón se usa como el valor para la parte local. 
    
  - (Obligatorio)  *dominio* es el nombre de dominio completo (FQDN) del servidor de correo que hospeda el buzón de correo identificado por la parte local de la dirección de correo electrónico. 
    
### <a name="format-of-the-from-address-if-you-dont-include-a-display-name"></a>Formato de From: si no incluye un nombre para mostrar de direcciones
<a name="FormatNoDisplayName"> </a>

Un formato adecuado de: dirección que no incluya un nombre para mostrar incluye sólo una dirección de correo electrónico única con o sin corchetes angulares. Microsoft recomienda no separe los corchetes angulares con espacios. Además, no incluyen nada después de la dirección de correo electrónico.
  
En los ejemplos siguientes son válidos:
  
```
From: sender@contoso.com
```

```
From: <sender@contoso.com>
```

El ejemplo siguiente es válido pero no se recomienda porque contiene espacios entre los corchetes angulares y la dirección de correo electrónico:
  
```
From: < sender@contoso.com >
```

En el siguiente ejemplo no es válido porque contiene texto después de la dirección de correo electrónico:
  
```
From: "Office 365" <sender@contoso.com> (Sent by a process)
```

### <a name="format-of-the-from-address-if-you-include-a-display-name"></a>Formato de From: si se incluye un nombre para mostrar de direcciones
<a name="FormatDisplayName"> </a>

Para desde: las direcciones que incluyen un valor para el nombre para mostrar, que se aplican las siguientes reglas:
  
- Si la dirección del remitente incluye un nombre para mostrar y el nombre para mostrar incluye una coma, a continuación, el nombre para mostrar debe estar incluido entre comillas. Por ejemplo:
    
    El ejemplo siguiente es válido:
    
  ```
  From: "Sender, Example" <sender.example@contoso.com>
  ```

    En el siguiente ejemplo no es válido:
    
  ```
  From: Sender, Example <sender.example@contoso.com>
  ```

    No incluir el nombre para mostrar entre comillas si ese nombre para mostrar incluye una coma es válido de acuerdo con RFC 5322.
    
    Como procedimiento recomendado, put comillas alrededor del nombre para mostrar, independientemente de si existe o no es una coma en el nombre para mostrar.
    
- Si la dirección del remitente incluye un nombre para mostrar, la dirección de correo electrónico debe ir entre corchetes angulares.
    
    Como práctica recomendada, Microsoft recomienda encarecidamente que insertar un espacio entre el nombre para mostrar y la dirección de correo electrónico.
    
### <a name="additional-examples-of-valid-and-invalid-from-addresses"></a>Ejemplos adicionales de válidos y no válidos de: direcciones
<a name="Examples"> </a>

- Válido:
    
  ```
  From: "Office 365" <sender@contoso.com>
  ```

- No válido. La dirección de correo electrónico no se incluye con corchetes angulares:
    
  ```
  From: Office 365 sender@contoso.com
  ```

- Válido, pero no se recomienda. El nombre para mostrar no está en comillas. Como procedimiento recomendado, ponga siempre comillas en el nombre para mostrar:
    
  ```
  From: Office 365 <sender@contoso.com>
  ```

- No válido. Todo lo que está incluido entre comillas, no sólo el nombre para mostrar:
    
  ```
  From: "Office 365 <sender@contoso.com>"
  ```

- No válido. No hay ningún corchetes angulares alrededor de la dirección de correo electrónico:
    
  ```
  From: "Office 365 <sender@contoso.com>" sender@contoso.com
  ```

- No válido. No hay ningún espacio entre el nombre para mostrar y el corchete angular de apertura:
    
  ```
  From: Office 365<sender@contoso.com>
  ```

- No válido. No hay ningún espacio entre el quotation mark cierre alrededor el nombre para mostrar y el corchete angular.
    
  ```
  From: "Office 365"<sender@contoso.com>
  ```

### <a name="suppress-auto-replies-to-your-custom-domain-without-breaking-the-from-policy"></a>Suprimir las respuestas automáticas para su dominio personalizado sin interrumpir la From: directiva
<a name="SuppressAutoReply"> </a>

Con el nuevo a partir de: aplicación de directivas, ya no se puede usar desde: \< \> para suprimir las respuestas automáticas. En su lugar, debe configurar un registro MX null para su dominio personalizado.
  
El registro de intercambio (MX) de correo es un registro de recursos de DNS que identifica el servidor de correo que recibe el correo para su dominio. Las respuestas automáticas (y todas las respuestas) con naturalidad se suprimen porque no hay ninguna dirección publicada a la que el servidor de respuesta puede enviar mensajes.
  
Al configurar un registro MX nulo para su dominio personalizado:
  
- Elija un dominio desde el que se va a enviar los mensajes que no acepta (recibir) correo electrónico. Por ejemplo, si su dominio principal es contoso.com, es posible que elija noreply.contoso.com.
    
- Configurar el registro MX null para su dominio. Un registro MX null consta de un único punto, por ejemplo:
    
  ```
  noreply.contoso.com IN MX .
  ```

Para obtener más información acerca de cómo publicar un null MX, consulte [RFC 7505](https://tools.ietf.org/html/rfc7505).
  
### <a name="overriding-the-office-365-from-address-enforcement-policy"></a>Reemplazar el Office 365 desde: directiva de aplicación de direcciones
<a name="Override"> </a>

Una vez finalizada la implementación de la nueva directiva, solo puede omitir esta directiva para el correo entrante que recibe de Office 365 mediante uno de los métodos siguientes: 
  
- Listas de direcciones IP permitidas
    
- Reglas de flujo de correo de Exchange Online
    
Microsoft recomienda encarecidamente reemplazar el cumplimiento de From: directiva. Reemplazar esta directiva puede aumentar el riesgo de la organización de exposición a correo no deseado, suplantación de identidad y otros cybercrimes.
  
No se puede invalidar esta directiva para el correo saliente que se envía en Office 365. Además, Outlook.com no le permitirá invalidaciones de ningún tipo, incluso a través de soporte técnico. 
  
### <a name="other-ways-to-prevent-and-protect-against-cybercrimes-in-office-365"></a>Otras maneras de prevenir y proteger contra cybercrimes en Office 365
<a name="OtherProtection"> </a>

Para obtener más información sobre cómo se puede reforzar su organización contra cybercrimes como suplantación de identidad, spam, violaciones de datos y otras amenazas, vea [procedimientos recomendados de seguridad para Office 365](https://support.office.com/article/9295e396-e53d-49b9-ae9b-0b5828cdedc3).
  
## <a name="related-topics"></a>Temas relacionados

[Mensajes de reenvío masivo de correo electrónico y EOP](https://technet.microsoft.com/en-us/library/dn499795%28v=exchg.150%29.aspx)
  

