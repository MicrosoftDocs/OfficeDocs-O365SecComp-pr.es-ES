---
title: Encabezados de mensajes de correo no deseado
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 2e3fcfc5-5604-4b88-ac0a-c5c45c03f1db
ms.collection:
- M365-security-compliance
description: Cuando Exchange Online Protection examina un mensaje de correo entrante, inserta el encabezado **X-Forefront-Antispam-Report** en cada mensaje.
ms.openlocfilehash: 973339a852bddb06fd7dfba4166e9e0917082725
ms.sourcegitcommit: 73f1db241c0686020167d43442e7b07a2199ea3a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/28/2019
ms.locfileid: "36658106"
---
# <a name="anti-spam-message-headers"></a>Encabezados de mensajes de correo no deseado

Cuando Exchange Online Protection examina un mensaje de correo entrante, inserta el encabezado **X-Forefront-Antispam-Report** en cada mensaje. Los campos de este encabezado pueden dar a los administradores información sobre el mensaje y la forma en que se procesó. Los campos del encabezado **X-Microsoft-Antispam** proporcionan información adicional sobre el correo masivo y la suplantación de identidad. Además de estos dos encabezados, Exchange Online Protection también inserta resultados de autenticación de correo electrónico para cada mensaje que procesa en el encabezado **Authentication-results**.

Para obtener información sobre cómo ver el encabezado del mensaje de un correo electrónico en distintos clientes de correo electrónico, vea [Analizador de encabezados de mensaje](https://go.microsoft.com/fwlink/p/?LinkId=306583) 
  
> [!TIP]
>  Puede copiar y pegar el contenido del encabezado de un mensaje en la herramienta [Analizador de mensaje](https://testconnectivity.microsoft.com/?tabid=mha). Esta herramienta le ayuda a analizar los encabezados y los convierte en un formato más legible.
  
## <a name="x-forefront-antispam-report-message-header-fields"></a>Campos del encabezado del mensaje X-Forefront-Antispam-Report

Al obtener acceso a la información del encabezado del mensaje, busque **X-Forefront-Antispam-Report** y, a continuación, busque los siguientes campos. El resto de los campos de este encabezado los usa exclusivamente el equipo de Microsoft contra el correo no deseado con fines de diagnóstico.

|**Campo de encabezado**|**Descripción**|
|:-----|:-----|
|CIP: [dirección IP]|La dirección IP de conexión. Quizás quiera especificar esta dirección IP cuando cree una lista de direcciones IP permitidas o una lista de direcciones IP bloqueadas en el filtro de conexión. Para obtener más información, vea [Configurar la directiva de filtro de conexión](configure-the-connection-filter-policy.md).  |
|CTRY|El país desde el que el mensaje se conectó al servicio. Está determinado por la dirección IP de conexión, que puede no ser la misma que la dirección IP de envío original.|
|LANG|El idioma en que se redactó el mensaje, que está definido por el código de país (por ejemplo, ru_RU indica ruso).|
|SCL|El valor del nivel de confianza contra correo no deseado (SCL) del mensaje. Para obtener más información sobre cómo interpretar estos valores, consulte [Niveles de confianza de correo no deseado](spam-confidence-levels.md).  |
|PCL|Valor de nivel de confianza de protección antiphishing (PCL) del mensaje.|
|SRV:BULK|El mensaje se identificó como mensaje de correo masivo. Si la opción avanzada de filtrado de correo no deseado **Bloquear todos los mensajes de correo masivo** está habilitada, se marcará como correo no deseado. Si no lo está, solo se marcará como correo no deseado en el caso de que el resto de las reglas de filtrado determinen que el mensaje es correo no deseado.|
|SFV:SFE|Se omitió el filtrado y se permitió el mensaje porque se envió desde una dirección de una lista de remitentes seguros del individuo.|
|SFV:BLK|Se omitió el filtrado y se bloqueó el mensaje porque se envió desde una dirección de una lista de remitentes bloqueados del individuo.  <br/> **Sugerencia:** Para obtener más información sobre cómo los usuarios finales pueden crear listas de remitentes seguros y bloqueados, vaya a [Bloquear o permitir (configuración del correo electrónico no deseado)](https://go.microsoft.com/fwlink/p/?LinkId=294862) (Outlook en la Web) e [Información sobre el filtro de correo electrónico no deseado](https://go.microsoft.com/fwlink/p/?LinkId=270065) (Outlook).|
|IPV:CAL|El mensaje se permitió a través de los filtros de correo no deseado porque la dirección IP estaba incluida en una lista de direcciones IP permitidas en el filtro de conexión.|
|IPV:NLI|La dirección IP no aparecía en ninguna lista de reputación de IP.|
|SFV:SPM|El filtro de contenido marcó el mensaje como correo no deseado.|
|SFV:SKS|El mensaje se marcó como correo no deseado antes de que el filtro de contenido lo procesara. Esto incluye los mensajes que coincidan con una regla de flujo de correo (también conocida como regla de transporte), la cual marca el mensaje automáticamente como correo no deseado y omite otros tipos de filtros.|
|SFV:SKA|El mensaje omitió el filtrado y se entregó a la bandeja de entrada porque coincidía con una lista de permitidos en la directiva de filtro de correo no deseado, como la lista de **remitentes permitidos**.|
|SFV:SKB|El mensaje se marcó como correo no deseado porque coincidía con una lista de bloqueados en la directiva de filtro de correo no deseado, como la lista de **remitentes bloqueados**.|
|SFV:SKN|El mensaje se marcó como correo seguro antes de que el filtro de contenido lo procesara. Esto incluye los mensajes que coincidan con una regla de flujo de correo, la cual marca el mensaje automáticamente como correo seguro y omite otros tipos de filtros.|
|SFV:SKI|Similar a SFV:SKN, el mensaje omitió el filtrado por otra razón, por ejemplo, ser un mensaje de correo electrónico dentro un inquilino de la organización.|
|SFV:SKQ|El mensaje fue publicado desde la cuarentena y se ha enviado a los destinatarios.|
|SFV:NSPM|El mensaje se marcó como correo seguro y se envió a los destinatarios correspondientes.|
|H: [helostring]|Cadena HELO o EHLO del servidor de correo que realiza la conexión.|
|PTR: [ReverseDNS]|Registro PTR, o registro de marcador, de la dirección IP de envío, también denominado dirección DNS inversa.|
|CAT:|La categoría de la directiva de protección que se aplica al mensaje: <br/>MALW: malware <br/>PHSH: phishing <br/>HSPM: correo no deseado de confianza elevada <br/>SPOOF: suplantación de identidad <br/>SPM: correo no deseado <br/>BULK: masivo <br/>DIMP: suplantación de dominio <br/>UIMP: suplantación de usuario <br/>Es posible que un mensaje entrante aparezca marcado por múltiples formas de protección y múltiples análisis de detección. Las directivas tienen diferentes prioridades y se aplica la que tenga la prioridad más alta. Consulte [Qué directiva se aplica cuando se ejecutan varios métodos de protección y exámenes de detección en el correo electrónico](https://docs.microsoft.com/office365/securitycompliance/how-policies-and-protections-are-combined).|
|SFTY|El mensaje se identificó como suplantación de identidad (phishing) y también se marcará con uno de los siguientes valores: <br/>9.1: valor predeterminado. El mensaje contiene una dirección URL de suplantación de identidad (phishing), puede tener otro contenido de suplantación de identidad (phishing) o se ha marcado como suplantación de identidad por otro filtro de correo, como una versión local de Exchange Server, antes de transmitir el mensaje a Office 365. <br/>9.11: el mensaje no ha superado las comprobaciones de suplantación de identidad donde el dominio de envío en el encabezado De: es el mismo, o se alinea con, o es parte de la misma organización que el dominio de recepción. Esto indica que se agregará una sugerencia de seguridad sobre la suplantación de la organización al mensaje. <br/>9.19: La suplantación del dominio del mensaje falló cuando el dominio remitente intentó hacerse pasar por un dominio que es propiedad del receptor o un dominio personalizado protegido por la directiva de protección contra la suplantación de identidad (anti-phishing). Esto indica que se agregará una sugerencia de seguridad de suplantación al mensaje si se habilitó a través de la directiva de protección contra la suplantación de identidad. <br/>9.20: El mensaje no superó las comprobaciones de suplantación del usuario cuando el usuario remitente intenta hacerse pasar por un usuario que pertenece a la organización del receptor o un usuario personalizado protegido por la directiva de protección contra la suplantación de identidad (anti-phishing). Esto indica que se agregará una sugerencia de seguridad de suplantación al mensaje si se habilitó a través de la directiva de protección contra la suplantación de identidad. <br/>9.21: El mensaje no superó las comprobaciones contra suplantaciones y el dominio remitente en el encabezado De: no se autentica y procede de un dominio externo. Se utiliza en combinación con un CompAuth (consulte Authentication-Results). <br/>9.22: Es lo mismo que el 9.21, pero el usuario tiene un remitente seguro que se reemplazó. <br/>9.23: Es lo mismo que el 9.22, pero la organización tiene un remitente o un dominio permitido que se reemplazó. <br/>9.24: Es lo mismo que el 9.23, pero el usuario tiene una regla de flujo de correo de Exchange que se reemplazó.|
|X-CustomSpam: [ASFOption]|El mensaje coincide con una opción avanzada de filtrado de correo no deseado (ASF). Por ejemplo, **X-CustomSpam: Vínculos de imagen a sitios remotos**indica que la opción ASF **Vínculos de imagen a sitios remotos ** tuvo una coincidencia. Para obtener más información sobre qué texto del encabezado X se agrega para cada opción específica del ASF, consulte [Opciones avanzadas de filtrado de correo no deseado](advanced-spam-filtering-asf-options.md).|
|

## <a name="x-microsoft-antispam-message-header-fields"></a>Campos de encabezado de mensaje de X-Microsoft-Antispam

En la tabla siguiente se describen los campos más útiles del encabezado de mensaje **X-Microsoft-Antispam**. El resto de los campos de este encabezado los usa exclusivamente el equipo de Microsoft contra el correo no deseado con fines de diagnóstico.
  
|**Campo de encabezado**|**Descripción**|
|:-----|:-----|
|BCL|El nivel de queja de correo masivo (BCL) del mensaje. Para más información, vea [Valores de nivel de queja de correo masivo](bulk-complaint-level-values.md).  |
|PCL|El nivel de confianza de protección antiphishing (PCL) del mensaje, que indica si se trata de un mensaje de suplantación de identidad. Este estado se puede devolver con uno de los siguientes valores numéricos: <br/>**0-3**: Es posible que el contenido del mensaje no represente una suplantación de identidad. <br/>**4-8**: Es posible que el contenido del mensaje represente una suplantación de identidad. <br/>**-9990**: (solo en Exchange Online Protection) Es posible que el contenido del mensaje represente una suplantación de identidad.  <br/>  Los valores se usan para determinar qué medidas toma el cliente de correo electrónico sobre los mensajes. Por ejemplo, Outlook usa la marca PCL para bloquear el contenido de los mensajes sospechosos. Para obtener más información sobre la suplantación de identidad (phishing) y cómo Outlook procesa los mensajes de suplantación de identidad, vea[Activar o desactivar vínculos en mensajes de correo electrónico](https://support.office.com/article/2D79B907-93B6-4774-82E6-1F0385CF20F8).|
|

## <a name="authentication-results-message-header"></a>Encabezado de mensaje Authentication-results

Office 365 graba los resultados de las comprobaciones de SPF, DKIM y DMARC en el encabezado de mensaje **Authentication-results** cuando nuestros servidores de correo reciben un mensaje de correo electrónico.
  
### <a name="check-stamp-syntax-and-examples"></a>Sintaxis y ejemplos de las marcas de verificación

En los siguientes ejemplos de sintaxis se muestra una parte del texto de la marca que Office 365 aplica al encabezado del mensaje por cada correo electrónico que se somete a una comprobación de autenticación de correo electrónico cuando lo recibimos en nuestros servidores de correo. Esta marca se agrega al encabezado **Authentication-Results**.
  
**Sintaxis: marca de verificación de SPF**
  
En cuanto a SPF, se aplica la siguiente sintaxis:
  
```text
spf=<pass (IP address)|fail (IP address)|softfail (reason)|neutral|none|temperror|permerror> smtp.mailfrom=<domain>
```

**Ejemplos: marca de verificación de SPF**
  
```text
spf=pass (sender IP is 192.168.0.1) smtp.mailfrom=contoso.com
spf=fail (sender IP is 127.0.0.1) smtp.mailfrom=contoso.com
```

**Sintaxis: marca de verificación de DKIM**
  
En cuanto a DKIM, se aplica la siguiente sintaxis:
  
```text
dkim=<pass|fail (reason)|none> header.d=<domain>
```

**Ejemplos: marca de verificación de DKIM**
  
```text
dkim=pass (signature was verified) header.d=contoso.com
dkim=fail (body hash did not verify) header.d=contoso.com
```

**Sintaxis: marca de verificación de DMARC**
  
En cuanto a DMARC, se aplica la siguiente sintaxis:
  
```text
dmarc=<pass|fail|bestguesspass|none> action=<permerror|temperror|oreject|pct.quarantine|pct.reject> header.from=<domain>
```

**Ejemplos: marca de verificación de DMARC**
  
```text
dmarc=pass action=none header.from=contoso.com
dmarc=bestguesspass action=none header.from=contoso.com
dmarc=fail action=none header.from=contoso.com
dmarc=fail action=oreject header.from=contoso.com
```

### <a name="authentication-results-message-header-fields-used-by-office-365-email-authentication"></a>Campos del encabezado de mensaje Authentication-results usados por la autenticación de correo electrónico de Office 365

En esta tabla se describen los campos y los valores posibles para todas las comprobaciones de autenticación de correo electrónico.
  
|**Campo de encabezado**|**Descripción**|
|:-----|:-----|
|spf|Describe los resultados de la comprobación de SPF del mensaje. Los valores posibles son: <br/>**pass (dirección IP)**: indica que se superó la verificación de SPF del mensaje e incluye la dirección IP del remitente. El cliente tiene autorización para enviar o retransmitir un correo electrónico en nombre del dominio del remitente. <br/>**fail (dirección IP)**: indica que no se superó la verificación de SPF del mensaje e incluye la dirección IP del remitente A veces, recibe la denominación _"error no recuperable"_. <br/>**softfail (motivo)**: indica que el registro SPF determinó que el servidor no puede efectuar envíos, pero se encuentra en transición. <br/>**neutral**: indica que el registro SPF declaró explícitamente que no afirma si la dirección IP tiene autorización o no. <br/>**none**: indica que el dominio no tiene ningún registro SPF o que el registro SPF no proporciona ningún resultado. <br/>**temperror**: indica que se produjo un error que puede ser de carácter temporal (por ejemplo, un error de DNS). Volverlo a intentar más tarde puede que lo resuelva sin la intervención de ningún administrador. <br/>**permerror**: indica que se produjo un error permanente. Sucede cuando, por ejemplo, el dominio tiene un registro SPF con un formato incorrecto.|
|smtp.mailfrom|Contiene el dominio de origen desde el que se envió el mensaje. Todos los errores relacionados con este mensaje de correo electrónico se enviarán al administrador de correo o a la entidad responsable del dominio. A veces, recibe la denominación dirección 5321.MailFrom o dirección de ruta de acceso inversa en el sobre del mensaje.|
|dkim|Describe los resultados de la comprobación de DKIM del mensaje. Los valores posibles son: <br/>**pass**: indica que se superó la validación por DKIM del mensaje. <br/>**fail (motivo)**: indica que no se superó la validación por DKIM del mensaje e incluye el motivo. Por ejemplo, si el mensaje no estaba firmado o no se verificó la firma. <br/>**none**: indica que el mensaje no estaba firmado. Esto podría indicar que el dominio tiene un registro DKIM o que el registro DKIM no proporciona ningún resultado, solo indica que el mensaje no estaba firmado.|
|header.d|Dominio identificado en la firma de DKIM, en caso de haber alguna. Se trata del dominio consultado para obtener la clave pública.|
|dmarc|Describe los resultados de la comprobación de DMARC del mensaje. Los valores posibles son: <br/>**pass**: indica que se superó la validación por DMARC del mensaje. <br/>**fail**: indica que no se superó la validación por DMARC del mensaje. <br/>**bestguesspass**: indica que no existe ningún registro TXT de DMARC para el dominio, pero si hubiera existido, el mensaje habría superado la validación por DMARC. Esto se debe a que el dominio de la dirección 5321.MailFrom coincide con el dominio de la dirección 5322.From. <br/>**none**: indica que no hay ningún registro TXT de DKIM para el dominio remitente en DNS.|
|acción|Indica la acción efectuada por el filtro de correo no deseado en función de los resultados de la comprobación de DMARC. Por ejemplo: <br/>**permerror**: se produjo un error permanente durante la evaluación por DMARC (por ejemplo, la detección de un registro TXT de DMARC con un formato incorrecto en DNS). Es probable que volver a enviar este mensaje no produzca un resultado diferente. Puede que deba ponerse en contacto con el propietario del dominio para intentar resolver el problema. <br/>**temperror**: se produjo un error temporal durante la evaluación por DMARC. Puede solicitar al remitente que reenvíe el mensaje más tarde para procesar correctamente el correo electrónico. <br/>**oreject** u **o.reject**: significa invalidar el rechazo. En este caso, Office 365 usa esta acción cuando recibe un mensaje que no supera la comprobación de DMARC desde un dominio cuyo registro TXT de DMARC tiene una directiva de p=reject. En lugar de eliminar o rechazar el mensaje, Office 365 marca el mensaje como correo no deseado. Para obtener más información sobre por qué Office 365 está configurado de esta forma, vea [Cómo controla Office 365 el correo electrónico entrante que no supera las comprobaciones de DMARC](use-dmarc-to-validate-email.md#inbounddmarcfail). <br/>**pct.quarantine**: indica que se entregará un porcentaje inferior al 100 % de los mensajes que no superen la validación por DMARC. Esto significa que el mensaje no superó la comprobación de DMARC y la directiva se estableció en cuarentena, pero el campo pct no se estableció en el 100 % y el sistema decidió, de forma aleatoria, no aplicar la acción de DMARC, de acuerdo con la directiva del dominio especificado. <br/>**pct.reject**: indica que se entregará un porcentaje inferior al 100 % de los mensajes que no superen la validación por DMARC. Esto significa que el mensaje no superó la comprobación de DMARC y se estableció el rechazo de la directiva, pero el campo pct no se estableció en el 100 % y el sistema decidió, de forma aleatoria, no aplicar la acción de DMARC, de acuerdo con la directiva del dominio especificado.|
|header.from|El dominio de la dirección De en el encabezado del mensaje de correo electrónico. A veces, recibe la denominación dirección _5322.From_.|
|compauth|Resultado de la autenticación compuesta. Office 365 la utiliza para combinar varios tipos de autenticación como SPF, DKIM, DMARC o cualquier otra parte del mensaje para determinar si el mensaje se autentica o no. Usa el dominio De: como base de la evaluación.|
|motivo|El motivo por el que se ha producido un error en la autenticación compuesta. El valor del motivo está formado por tres dígitos: <br/>**000**: el mensaje no se pudo autenticar explícitamente. Por ejemplo, el mensaje ha recibido un error de DMARC con una acción de cuarentena o rechazo. <br/>**001**: el mensaje no se pudo autenticar explícitamente, y el domino remitente no publicó las directivas de autenticación. Por ejemplo, una directiva DMARC de p=none. <br/>**1xx**: el mensaje superó la autenticación. Los dos últimos dígitos son códigos internos utilizados por Office 365. <br/>**2xx**: el mensaje superó la autenticación. Los dos últimos dígitos son códigos internos utilizados por Office 365. <br/>**3xx**: no se validó la autenticación compuesta del mensaje. <br/>**4xx**: el mensaje omitió la autenticación compuesta. Los dos últimos dígitos son códigos internos utilizados por Office 365.|
|
