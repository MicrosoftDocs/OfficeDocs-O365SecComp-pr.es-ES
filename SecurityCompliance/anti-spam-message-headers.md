---
title: Encabezados de mensajes de correo no deseado
ms.author: krowley
author: kccross
manager: laurawi
ms.date: ''
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 2e3fcfc5-5604-4b88-ac0a-c5c45c03f1db
description: Cuando Exchange Online Protection examina un mensaje de correo entrante, inserta el encabezado **X-Forefront-Antispam-Report** en cada mensaje.
ms.openlocfilehash: d887fea94bac6177dde69fac9586d7d562ef50de
ms.sourcegitcommit: 03b9221d9885bcde1cdb5df2c2dc5d835802d299
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2019
ms.locfileid: "29614464"
---
# <a name="anti-spam-message-headers"></a>Encabezados de mensajes de correo no deseado

Cuando Exchange Online Protection examina un mensaje de correo entrante, inserta el encabezado **X-Forefront-Antispam-Report** en cada mensaje. Los campos de este encabezado pueden dar a los administradores información sobre el mensaje y la forma en que se procesó. Los campos del encabezado **X-Microsoft-Antispam** proporcionan información adicional sobre el correo masivo y la suplantación de identidad. Además de estos dos encabezados, Exchange Online Protection también inserta resultados de autenticación de correo electrónico para cada mensaje que procesa en el encabezado **Authentication-results**.
  
> [!TIP]
> Para obtener información sobre cómo ver un encabezado de mensaje de correo electrónico en distintos clientes de correo electrónico, consulte [Message Header Analyzer (Analizador de encabezados de mensaje)](https://go.microsoft.com/fwlink/p/?LinkId=306583). Puede copiar y pegar el contenido del encabezado del mensaje en la herramienta [Analizador de encabezados de mensaje](https://testconnectivity.microsoft.com/?tabid=mha). Si selecciona un mensaje que está en cuarentena en el centro de administración de Exchange, el vínculo **Ver encabezado de mensaje** también le permite copiar y pegar fácilmente el texto del encabezado del mensaje en la herramienta. Cuando esté en la herramienta Analizador de encabezados de mensaje, haga clic en **Analizar encabezados** para recuperar la información del encabezado.
  
## <a name="x-forefront-antispam-report-message-header-fields"></a>Campos de encabezado de mensaje X-Forefront-Antispam-Report
<a name="sectionSection0"> </a>

Al obtener acceso a la información del encabezado del mensaje, busque **X-Forefront-Antispam-Report** y, a continuación, busque los siguientes campos. El resto de los campos de este encabezado los usa exclusivamente el equipo de Microsoft contra el correo no deseado con fines de diagnóstico.

|**Campo de encabezado**|**Descripción**|
|:-----|:-----|
|CIP: [dirección IP]|La dirección IP de conexión. Quizás quiera especificar esta dirección IP cuando cree una lista de direcciones IP permitidas o una lista de direcciones IP bloqueadas en el filtro de conexión. Para obtener más información, vea [Configurar la directiva de filtro de conexión](configure-the-connection-filter-policy.md).  |
|CTRY|El país desde el que el mensaje se conectó al servicio. Está determinado por la dirección IP de conexión, que puede no ser la misma que la dirección IP de envío original.|
|LANG|El idioma en que se redactó el mensaje, que está definido por el código de país (por ejemplo, ru_RU indica ruso).|
|SCL|El valor del nivel de confianza contra correo no deseado (SCL) del mensaje. Para obtener más información sobre cómo interpretar estos valores, consulte [Niveles de confianza de correo no deseado](spam-confidence-levels.md).  |
|PCL|El valor del nivel de confianza de protección antiphishing (PCL) del mensaje. Consulte [PCL](anti-spam-message-headers.md#PCL) para obtener más información sobre los valores de PCL.  |
|SRV:BULK|El mensaje se identificó como mensaje de correo masivo. Si la opción avanzada de filtrado de correo no deseado **Bloquear todos los mensajes de correo masivo** está habilitada, se marcará como correo no deseado. Si no lo está, solo se marcará como correo no deseado en el caso de que el resto de las reglas de filtrado determinen que el mensaje es correo no deseado.  |
|SFV:SFE|Se omitió el filtrado y se permitió el mensaje porque se envió desde una dirección de una lista de remitentes seguros del individuo.|
|SFV:BLK|Se omitió el filtrado y se bloqueó el mensaje porque se envió desde una dirección de una lista de remitentes bloqueados del individuo.  <br/> **Sugerencia**: para obtener más información sobre cómo los usuarios finales pueden crear listas de remitentes seguros y bloqueados, vea [Bloquear o permitir (configuración de correo electrónico no deseado)](https://go.microsoft.com/fwlink/p/?LinkId=294862) (Outlook en la web) y la [información general sobre el filtro de correo electrónico no deseado](https://go.microsoft.com/fwlink/p/?LinkId=270065) (en Outlook).|
|IPV:CAL|El mensaje se permitió a través de los filtros de correo no deseado porque la dirección IP estaba incluida en una lista de direcciones IP permitidas en el filtro de conexión.|
|IPV:NLI|La dirección IP no aparecía en ninguna lista de reputación de IP.|
|SFV:SPM|El filtro de contenido marcó el mensaje como correo no deseado.|
|SFV:SKS|El mensaje se marcó como correo no deseado antes de que el filtro de contenido lo procesara. Esto incluye los mensajes que coinciden con una regla de transporte que marca el mensaje automáticamente como correo no deseado y omite otros tipos de filtrado.|
|SFV:SKA|El mensaje omitió el filtrado y se entregó a la bandeja de entrada porque coincidía con una lista de permitidos en la directiva de filtro de correo no deseado, como la lista de **remitentes permitidos**.|
|SFV:SKB|El mensaje se marcó como correo no deseado porque coincidía con una lista de bloqueados en la directiva de filtro de correo no deseado, como la lista de **remitentes bloqueados**.|
|SFV:SKN|El mensaje se marcó como correo seguro antes de que el filtro de contenido lo procesara. Esto incluye los mensajes que coinciden con una regla de transporte que marca el mensaje automáticamente como correo seguro y omite otros tipos de filtrado.|
|SFV:SKI|Similar a SFV:SKN, el mensaje omitió el filtrado por otra razón, por ejemplo, ser un mensaje de correo electrónico dentro un inquilino de la organización.|
|SFV:SKQ|El mensaje fue publicado desde la cuarentena y se ha enviado a los destinatarios.|
|SFV:NSPM|El mensaje se marcó como correo seguro y se envió a los destinatarios correspondientes.|
|H: [helostring]|Cadena HELO o EHLO del servidor de correo que realiza la conexión.|
|PTR: [ReverseDNS]|Registro PTR, o registro de marcador, de la dirección IP de envío, también denominado dirección DNS inversa.|
|SFTY|El mensaje se identificó como suplantación de identidad y también se marcan con uno de los siguientes valores: <br/>• 9.1: valor predeterminado. El mensaje contiene una dirección URL de la suplantación de identidad, puede contener otro contenido de suplantación de identidad o es posible que se han marcado como suplantación de identidad por otro filtro de correo como una versión local de Exchange Server antes de transmitir el mensaje a Office 365. <br/>• 9.11: mensaje de error contra la suplantación comprobaciones donde el dominio en el campo de envío: encabezado es el mismo que, o se alinea con o forma parte de la misma organización que el dominio receptor. Esto indica que una sugerencia de seguridad de suplantación de identidad dentro de la organización se agregarán al mensaje. <br/>• 9.19: mensaje de error de comprobaciones de suplantación de dominio donde el dominio envío está intentando suplantar a un dominio al que pertenece el receptor, o un dominio personalizado protegida por la directiva contra suplantación de identidad. Esto indica que una sugerencia de seguridad de suplantación se agregarán al mensaje, si se habilita a través de la directiva de Anti-Phishig. <br/>• 9,20: mensaje de error de comprobaciones de suplantación de usuario donde el usuario que envía está intentando suplantar a un usuario dentro de la organización de receptores o un usuario personalizado protegido por la directiva contra suplantación de identidad. Esto indica que una sugerencia de seguridad de suplantación se agregarán al mensaje, si se habilita a través de la directiva de Anti-Phishig. <br/>• 9.21: mensaje de error comprobaciones contra la suplantación y el dominio en el campo de envío: encabezado no autenticar y es de un dominio externo. Usados en combinación con CompAuth (vea resultados de autenticación). <br/>• 9.22: igual que 9.21, excepto que el usuario tiene un remitente seguro que se ha reemplazado. <br/>• 9.23: igual que 9.22, excepto que la organización tiene un remitente permitido o dominio que se ha reemplazado. <br/>• 9,24: igual que 9.23, excepto que el usuario tiene una regla de flujo de correo de Exchange que se ha reemplazado.|
|X-CustomSpam: [ASFOption]|El mensaje coincide con una opción de filtrado avanzadas correo no deseado. Por ejemplo, **X-CustomSpam: vínculos a sitios remotos de la imagen** indica que se ha asignado la opción ASF de **vínculos de imagen a sitios remotos** . Para averiguar qué texto de encabezado X se agrega para cada opción de ASF específico, vea [Opciones de filtrado avanzadas correo no deseado](advanced-spam-filtering-asf-options.md).|
   
## <a name="x-microsoft-antispam-message-header-fields"></a>Campos de encabezado de mensaje X-Microsoft-Antispam
<a name="sectionSection1"> </a>

En la tabla siguiente se describen los campos más útiles del encabezado de mensaje **X-Microsoft-Antispam**. El resto de los campos de este encabezado los usa exclusivamente el equipo de Microsoft contra el correo no deseado con fines de diagnóstico.
  
|**Campo de encabezado**|**Descripción**|
|:-----|:-----|
|BCL|El nivel de queja de correo masivo (BCL) del mensaje. Para más información, vea [Valores de nivel de queja de correo masivo](bulk-complaint-level-values.md).  |
|PCL|La suplantación de identidad Confidence nivel (PCL) del mensaje, que indica si se trata de un mensaje de suplantación de identidad. Este estado se puede devolver como uno de los siguientes valores numéricos:<br/>• **0-3**: el contenido del mensaje no es probable de suplantación de identidad. <br/>• **4-8**: el contenido del mensaje es probable de suplantación de identidad. <br/>• **-9990**: (sólo en la protección en línea de Exchange) el contenido del mensaje es probable de suplantación de identidad.  <br/>  Los valores se utilizan para determinar qué acción realiza el cliente de correo electrónico en los mensajes. Por ejemplo, Outlook usa la marca de PCL para bloquear el contenido de los mensajes sospechosos. Para obtener más información acerca de la suplantación de identidad y cómo Outlook procesa los mensajes de suplantación de identidad, vea [Activar o desactivar los vínculos en los mensajes de correo electrónico](https://support.office.com/article/2D79B907-93B6-4774-82E6-1F0385CF20F8).|
   
## <a name="authentication-results-message-header"></a>Encabezado de mensaje Authentication-results
<a name="sectionSection2"> </a>

Office 365 graba los resultados de las comprobaciones de SPF, DKIM y DMARC en el encabezado de mensaje **Authentication-results** cuando nuestros servidores de correo reciben un mensaje de correo electrónico.
  
### <a name="check-stamp-syntax-and-examples"></a>Sintaxis y ejemplos de las marcas de verificación
<a name="referenceSPFstamp"> </a>

En los siguientes ejemplos de sintaxis se muestra una parte del texto de la marca que Office 365 aplica al encabezado del mensaje por cada correo electrónico que se somete a una comprobación de autenticación de correo electrónico cuando lo recibimos en nuestros servidores de correo. Esta marca se agrega al encabezado **Authentication-Results**.
  
 **Sintaxis: marca de verificación de SPF**
  
En cuanto a SPF, se aplica la siguiente sintaxis:
  
```
spf=<pass (IP address)|fail (IP address)|softfail (reason)|neutral|none|temperror|permerror> smtp.mailfrom=<domain>
```

 **Ejemplos: marca de verificación de SPF**
  
```
spf=pass (sender IP is 192.168.0.1) smtp.mailfrom=contoso.com
spf=fail (sender IP is 127.0.0.1) smtp.mailfrom=contoso.com
```

 **Sintaxis: marca de verificación de DKIM**
  
En cuanto a DKIM, se aplica la siguiente sintaxis:
  
```
dkim=<pass|fail (reason)|none> header.d=<domain>
```

 **Ejemplos: marca de verificación de DKIM**
  
```
dkim=pass (signature was verified) header.d=contoso.com
dkim=fail (body hash did not verify) header.d=contoso.com
```

 **Sintaxis: marca de verificación de DMARC**
  
En cuanto a DMARC, se aplica la siguiente sintaxis:
  
```
dmarc=<pass|fail|bestguesspass|none> action=<permerror|temperror|oreject|pct.quarantine|pct.reject> header.from=<domain>
```

 **Ejemplos: marca de verificación de DMARC**
  
```
dmarc=pass action=none header.from=contoso.com
dmarc=bestguesspass action=none header.from=contoso.com
dmarc=fail action=none header.from=contoso.com
dmarc=fail action=oreject header.from=contoso.com
```

### <a name="authentication-results-message-header-fields-used-by-office-365-email-authentication"></a>Campos del encabezado de mensaje Authentication-results usados por la autenticación de correo electrónico de Office 365
<a name="referenceSPFstamp"> </a>

En esta tabla se describen los campos y los valores posibles para todas las comprobaciones de autenticación de correo electrónico.
  
|**Campo de encabezado**|**Descripción**|
|:-----|:-----|
|spf|Describe los resultados de la comprobación de SPF del mensaje. Los valores posibles son:  <br/>• **pasar (dirección IP)**: indica la comprobación de SPF para pasa el mensaje e incluye la dirección IP del remitente. El cliente está autorizado para enviar o retransmitir correo electrónico en nombre de dominio de la dirección del remitente.<br/>• **producirá un error (dirección IP)**: indica la comprobación de SPF para el mensaje de error e incluye la dirección IP del remitente. En ocasiones, esto se denomina _disco duro producirá un error_.<br/>• **error leve (razón)**: indica que el registro SPF ha designado el host como no se pueden enviar pero está en transición. <br/>• **neutro**: indica que el registro SPF ha declarado explícitamente que no es aserción si la dirección IP está autorizada. <br/>• **Ninguno**: indica que el dominio no tiene un registro SPF o el registro SPF no se evalúa como un resultado. <br/>• **temperror**: indica que produjo un error que puede ser temporal en la naturaleza, por ejemplo, un error DNS. Intentar más tarde es posible que se realizan con éxito sin intervención del administrador.<br/>• **permerror**: indica que se ha producido un error permanente. Esto sucede cuando, por ejemplo, el dominio tiene un registro SPF con formato incorrecto.|
|SMTP.MailFrom|Contiene el dominio de origen desde el que se envió el mensaje. Todos los errores relacionados con este mensaje de correo electrónico se enviarán al administrador de correo o a la entidad responsable del dominio. A veces, recibe la denominación dirección 5321.MailFrom o dirección de ruta de acceso inversa en el sobre del mensaje.|
|dkim|Describe los resultados de la comprobación de DKIM del mensaje. Los valores posibles son:  <br/>• **pasar**: indica la comprobación de DKIM para el mensaje que se pasa. <br/>• **producirá un error (razón)**: indica la comprobación de DKIM para el mensaje de error y por qué. Por ejemplo, si el mensaje no se firmó o no se ha comprobado la firma.<br/>• **Ninguno**: indica que el mensaje no se ha firmado. Esto puede o no puede indicar que el dominio tiene un registro DKIM o el registro DKIM no se evalúa como un resultado, solo que este mensaje no se ha firmado.|
|Header.d|Dominio identificado en la firma de DKIM, en caso de haber alguna. Se trata del dominio consultado para obtener la clave pública.|
|dmarc|Describe los resultados de la comprobación de DMARC del mensaje. Los valores posibles son:  <br/>• **pasar**: indica la comprobación DMARC pasada el mensaje. <br/>• **producirá un error**: indica la comprobación de DMARC para el mensaje de error. <br/>• **bestguesspass**: indica que no existe ningún registro TXT DMARC para el dominio, pero si uno tenía existía, habría pasado la comprobación de DMARC para el mensaje. Esto es debido a que el dominio en la dirección 5321.MailFrom coincide con el dominio en la dirección 5322.From.<br/>• **Ninguno**: indica que no hay ningún registro TXT DKIM existe para el dominio del remitente en DNS.|
|action|Indica la acción efectuada por el filtro de correo no deseado en función de los resultados de la comprobación de DMARC. Por ejemplo:  <br/>• **permerror**: se produjo un error permanente durante la evaluación de DMARC, como encontrar un incorrectamente creado TXT DMARC registrar en DNS. Si se intenta volver a enviar este mensaje no es probable que terminan con un resultado diferente. En su lugar, es posible que necesite ponerse en contacto con el propietario del dominio con el fin de resolver el problema.<br/>• **temperror**: se produjo un error temporal durante la evaluación de DMARC. Es posible que pueda solicitar que el remitente a enviar el mensaje más adelante con el fin de procesar correctamente el correo electrónico.<br/>• **oreject** o **o.reject**: significa reemplazar rechazar. En esta utiliza caso Office 365 comprobar esta acción cuando recibe un mensaje que se produce un error de la DMARC de un dominio cuyo registro TXT DMARC tiene una directiva de p = rechazar. En lugar de eliminar o rechazar el mensaje, Office 365 marca el mensaje como correo no deseado. Para obtener más información sobre por qué Office 365 está configurado de esta forma, vea [identificadores de cómo Office 365 que se produce un error DMARC el correo electrónico entrante](use-dmarc-to-validate-email.md#inbounddmarcfail).<br/>• **pct.quarantine**: indica que se entregarán un porcentaje inferior a 100% de los mensajes que no pasan la DMARC de todos modos. Esto significa que el mensaje no pudo DMARC y la directiva se estableció en cuarentena, pero no se estableció en el campo pct al 100% y el sistema de forma aleatoria determina que no se aplica la acción DMARC, según la directiva del dominio especificado.<br/>• **pct.reject**: indica que se entregarán un porcentaje inferior a 100% de los mensajes que no pasan la DMARC de todos modos. Esto significa que el mensaje no pudo DMARC y la directiva se estableció en Rechazar, pero no se estableció en el campo pct al 100% y el sistema de forma aleatoria determina que no se aplica la acción DMARC, según la directiva del dominio especificado.|
|Header.From|El dominio de dirección de origen en el encabezado del mensaje de correo electrónico. En ocasiones, esto se denomina la dirección _5322.From_ .|
|compauth|Resultado de la autenticación compuesto. Utilizado por Office 365 para combinar varios tipos de autenticación como SPF, DKIM, DMARC o cualquier otra parte del mensaje para determinar si el mensaje se autentica. Usa el From: dominio como base de evaluación.|
|motivo|La razón por la autenticación compuesta se pasa o errores. El valor de la razón por la se compone de tres dígitos:<br/>• **000**: explícitamente el mensaje de error de autenticación. Por ejemplo, recibe un error DMARC con una acción de cuarentena o rechazar el mensaje.<br/>• **001**: implícitamente el mensaje de error de autenticación y el dominio envío no publica las directivas de autenticación. Por ejemplo, una directiva de DMARC de p = none.<br/>• **1xx**: el mensaje pasa a la autenticación. El segundo de dos dígitos son códigos internos utilizados por Office 365.<br/>• **2xx**: la autenticación de mensajes se pasan temporalmente. El segundo de dos dígitos son códigos internos utilizados por Office 365.<br/>• **3xx**: el mensaje no se ha protegido para la autenticación compuesta. <br/>• **4xx**: el mensaje pasó autenticación compuesta. El segundo de dos dígitos son códigos internos utilizados por Office 365.|
