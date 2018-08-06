---
title: Encabezados de mensajes de correo no deseado
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 2/9/2018
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: 2e3fcfc5-5604-4b88-ac0a-c5c45c03f1db
description: Cuando Exchange Online Protection examina un mensaje de correo entrante, inserta el encabezado **X-Forefront-Antispam-Report** en cada mensaje.
ms.openlocfilehash: 7baa15f4d687c809d45461a135f64f0d18f49a7f
ms.sourcegitcommit: 22bca85c3c6d946083d3784f72e886c068d49f4a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/06/2018
ms.locfileid: "22026507"
---
# <a name="anti-spam-message-headers"></a>Encabezados de mensajes de correo no deseado

Cuando Exchange Online Protection examina un mensaje de correo entrante, inserta el encabezado **X-Forefront-Antispam-Report** en cada mensaje. Los campos de este encabezado pueden dar a los administradores información sobre el mensaje y la forma en que se procesó. Los campos del encabezado **X-Microsoft-Antispam** proporcionan información adicional sobre el correo masivo y la suplantación de identidad. Además de estos dos encabezados, Exchange Online Protection también inserta resultados de autenticación de correo electrónico para cada mensaje que procesa en el encabezado **Authentication-results**. 
  
> [!TIP]
> Para obtener información sobre cómo ver un encabezado de mensaje de correo electrónico en distintos clientes de correo electrónico, consulte [Message Header Analyzer (Analizador de encabezados de mensaje)](https://go.microsoft.com/fwlink/p/?LinkId=306583). Puede copiar y pegar el contenido del encabezado del mensaje en la herramienta [Analizador de encabezados de mensaje](https://testconnectivity.microsoft.com/?tabid=mha). Si selecciona un mensaje que está en cuarentena en el centro de administración de Exchange, el vínculo **Ver encabezado de mensaje** también le permite copiar y pegar fácilmente el texto del encabezado del mensaje en la herramienta. Cuando esté en la herramienta Analizador de encabezados de mensaje, haga clic en **Analizar encabezados** para recuperar la información del encabezado. 
  
## <a name="x-forefront-antispam-report-message-header-fields"></a>Campos de encabezado de mensaje X-Forefront-Antispam-Report
<a name="sectionSection0"> </a>

Al obtener acceso a la información del encabezado del mensaje, busque **X-Forefront-Antispam-Report** y, a continuación, busque los siguientes campos. El resto de los campos de este encabezado los usa exclusivamente el equipo de Microsoft contra el correo no deseado con fines de diagnóstico. 
  
|||
|:-----|:-----|
|**Campo de encabezado** <br/> |**Descripción** <br/> |
|CIP: [dirección IP]  <br/> |La dirección IP de conexión. Quizás quiera especificar esta dirección IP cuando cree una lista de direcciones IP permitidas o una lista de direcciones IP bloqueadas en el filtro de conexión. Para obtener más información, vea [Configurar la directiva de filtro de conexión](configure-the-connection-filter-policy.md).  <br/> |
|CTRY  <br/> |El país desde el que el mensaje se conectó al servicio. Está determinado por la dirección IP de conexión, que puede no ser la misma que la dirección IP de envío original.  <br/> |
|LANG  <br/> |El idioma en que se redactó el mensaje, que está definido por el código de país (por ejemplo, ru_RU indica ruso).  <br/> |
|SCL  <br/> |El valor del nivel de confianza contra correo no deseado (SCL) del mensaje. Para obtener más información sobre cómo interpretar estos valores, consulte [Niveles de confianza de correo no deseado](spam-confidence-levels.md).  <br/> |
|PCL  <br/> |El valor del nivel de confianza de protección antiphishing (PCL) del mensaje. Consulte [PCL](anti-spam-message-headers.md#PCL) para obtener más información sobre los valores de PCL.  <br/> |
|SRV:BULK  <br/> |El mensaje se identificó como mensaje de correo masivo. Si la opción avanzada de filtrado de correo no deseado **Bloquear todos los mensajes de correo masivo** está habilitada, se marcará como correo no deseado. Si no lo está, solo se marcará como correo no deseado en el caso de que el resto de las reglas de filtrado determinen que el mensaje es correo no deseado.  <br/> |
|SFV:SFE  <br/> |Se omitió el filtrado y se permitió el mensaje porque se envió desde una dirección de una lista de remitentes seguros del individuo.  <br/> |
|SFV:BLK  <br/> |Se omitió el filtrado y se bloqueó el mensaje porque se envió desde una dirección de una lista de remitentes bloqueados del individuo.  <br/> **Sugerencia:** Para obtener más información sobre cómo los usuarios finales pueden crear listas de remitentes seguros y bloqueados, vea [Bloquear o permitir (configuración del correo electrónico no deseado)](https://go.microsoft.com/fwlink/p/?LinkId=294862) (OWA) y [Información general sobre el filtro de correo electrónico no deseado](https://go.microsoft.com/fwlink/p/?LinkId=270065) (Outlook).  <br/> |
|IPV:CAL  <br/> |El mensaje se permitió a través de los filtros de correo no deseado porque la dirección IP estaba incluida en una lista de direcciones IP permitidas en el filtro de conexión.  <br/> |
|IPV:NLI  <br/> |La dirección IP no aparecía en ninguna lista de reputación de IP.  <br/> |
|SFV:SPM  <br/> |El filtro de contenido marcó el mensaje como correo no deseado.  <br/> |
|SFV:SKS  <br/> |El mensaje se marcó como correo no deseado antes de que el filtro de contenido lo procesara. Esto incluye los mensajes que coinciden con una regla de transporte que marca el mensaje automáticamente como correo no deseado y omite otros tipos de filtrado.  <br/> |
|SFV:SKA  <br/> |El mensaje omitió el filtrado y se entregó a la bandeja de entrada porque coincidía con una lista de permitidos en la directiva de filtro de correo no deseado, como la lista de **remitentes permitidos**.  <br/> |
|SFV:SKB  <br/> |El mensaje se marcó como correo no deseado porque coincidía con una lista de bloqueados en la directiva de filtro de correo no deseado, como la lista de **remitentes bloqueados**.  <br/> |
|SFV:SKN  <br/> |El mensaje se marcó como correo seguro antes de que el filtro de contenido lo procesara. Esto incluye los mensajes que coinciden con una regla de transporte que marca el mensaje automáticamente como correo seguro y omite otros tipos de filtrado.  <br/> |
|SFV:SKI  <br/> |Similar a SFV:SKN, el mensaje omitió el filtrado por otra razón, por ejemplo, ser un mensaje de correo electrónico dentro un inquilino de la organización.  <br/> |
|SFV:SKQ  <br/> |El mensaje fue publicado desde la cuarentena y se ha enviado a los destinatarios.  <br/> |
|SFV:NSPM  <br/> |El mensaje se marcó como correo seguro y se envió a los destinatarios correspondientes.  <br/> |
|H: [helostring]  <br/> |Cadena HELO o EHLO del servidor de correo que realiza la conexión.  <br/> |
|PTR: [ReverseDNS]  <br/> |Registro PTR, o registro de marcador, de la dirección IP de envío, también denominado dirección DNS inversa.  <br/> |
|SFTY  <br/> | El mensaje se identificó como suplantación de identidad y también se marcan con uno de los siguientes valores:  <br/>  9.1 - valor predeterminado. El mensaje contiene una dirección URL de la suplantación de identidad, puede contener otro contenido de suplantación de identidad o es posible que se han marcado como suplantación de identidad por otro filtro de correo como una versión local de Exchange Server antes de transmitir el mensaje a Office 365.  <br/>  9.11 - mensaje de error contra la suplantación comprobaciones donde el dominio en el campo de envío: encabezado es el mismo que, o se alinea con o forma parte de la misma organización que el dominio receptor.  <br/>  No pudo del mensaje de 9.21 - comprobaciones contra la suplantación y el dominio en el campo de envío: encabezado no autenticar. Usados en combinación con CompAuth (vea resultados de autenticación).  <br/>  9.22 - igual que 9.21, excepto que el usuario tiene un remitente seguro que se ha reemplazado.  <br/>  9.23 - igual que 9.22, excepto que la organización tiene un remitente permitido o dominio que se ha reemplazado.  <br/>  9,24 - igual que 9.23, excepto en que el usuario tiene un flujo de correo de Exchange de la regla se ha reemplazado.  <br/> |
|X-CustomSpam: [ASFOption]  <br/> |El mensaje coincide con una opción de filtrado avanzadas correo no deseado. Por ejemplo, **X-CustomSpam: vínculos a sitios remotos de la imagen** indica que se ha asignado la opción ASF de **vínculos de imagen a sitios remotos** . Para averiguar qué texto de encabezado X se agrega para cada opción de ASF específico, vea [Opciones de filtrado avanzadas correo no deseado](advanced-spam-filtering-asf-options.md).<br/> |
   
## <a name="x-microsoft-antispam-message-header-fields"></a>Campos de encabezado de mensaje X-Microsoft-Antispam
<a name="sectionSection1"> </a>

En la tabla siguiente se describen los campos más útiles del encabezado de mensaje **X-Microsoft-Antispam**. El resto de los campos de este encabezado los usa exclusivamente el equipo de Microsoft contra el correo no deseado con fines de diagnóstico. 
  
|||
|:-----|:-----|
|**Campo de encabezado** <br/> |**Descripción** <br/> |
|BCL  <br/> |El nivel de queja de correo masivo (BCL) del mensaje. Para más información, vea [Valores de nivel de queja de correo masivo](bulk-complaint-level-values.md).  <br/> |
|PCL  <br/> | El nivel de confianza de protección antiphishing (PCL) del mensaje, que indica si se trata de un mensaje de suplantación de identidad.  <br/>  Este estado se puede devolver con uno de los siguientes valores numéricos:  <br/> **0-3** No es probable que el contenido del mensaje represente una suplantación de identidad.  <br/> **4-8** Es probable que el contenido del mensaje represente una suplantación de identidad.  <br/> **-9990** (solo en Exchange Online Protection) Es probable que el contenido del mensaje represente una suplantación de identidad.  <br/>  Los valores se usan para determinar qué medidas toma el cliente de correo electrónico en los mensajes. Por ejemplo, Microsoft Office Outlook usa la marca PCL para bloquear el contenido de los mensajes sospechosos. Para obtener más información sobre la suplantación de identidad y sobre cómo Outlook procesa los mensajes de suplantación de identidad, consulte [Activar o desactivar los vínculos en los mensajes de correo](https://support.office.com/article/2D79B907-93B6-4774-82E6-1F0385CF20F8).  <br/> |
   
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
|spf  <br/> | Describe los resultados de la comprobación de SPF del mensaje. Los valores posibles son:  <br/> **pass (dirección IP)** indica que se superó la verificación de SPF del mensaje e incluye la dirección IP del remitente. El cliente tiene autorización para enviar o retransmitir correo electrónico en nombre del dominio del remitente.  <br/> **fail (dirección IP)** indica que no se superó la verificación de SPF del mensaje e incluye la dirección IP del remitente (a veces, recibe la denominación "error").<br/> **softfail (motivo)** indica que el registro SPF determinó que el host no puede efectuar envíos, pero se encuentra en transición.  <br/> **neutral** indica que el registro SPF declaró explícitamente que no afirma si la dirección IP tiene autorización o no.  <br/> **none** indica que el dominio no tiene ningún registro SPF o que el registro SPF no proporciona ningún resultado.  <br/> **temperror** indica que se produjo un error que puede ser de carácter temporal (por ejemplo, un error de DNS). Es posible que repitiendo la acción más adelante se resuelva sin la intervención de ningún administrador.  <br/> **permerror** indica que se produjo un error permanente. Sucede cuando, por ejemplo, el dominio tiene un registro SPF con un formato incorrecto.  <br/> |
|SMTP.MailFrom  <br/> |Contiene el dominio de origen desde el que se envió el mensaje. Todos los errores relacionados con este mensaje de correo electrónico se enviarán al administrador de correo o a la entidad responsable del dominio. A veces, recibe la denominación dirección 5321.MailFrom o dirección de ruta de acceso inversa en el sobre del mensaje.  <br/> |
|dkim  <br/> | Describe los resultados de la comprobación de DKIM del mensaje. Los valores posibles son:  <br/> **pass** indica que se superó la comprobación de DKIM del mensaje.  <br/> **fail (motivo)** indica que no se superó la comprobación de DKIM del mensaje e incluye el motivo. Por ejemplo, si el mensaje no estaba firmado o no se había verificado la firma.  <br/> **none** indica que el mensaje no estaba firmado. Esto podría indicar que el dominio tiene un registro DKIM o que el registro DKIM no proporciona ningún resultado, solo indica que el mensaje no estaba firmado.  <br/> |
|Header.d  <br/> |Dominio identificado en la firma de DKIM, en caso de haber alguna. Se trata del dominio consultado para obtener la clave pública.  <br/> |
|dmarc  <br/> | Describe los resultados de la comprobación de DMARC del mensaje. Los valores posibles son:  <br/> **pass**: indica la comprobación de DMARC que el mensaje superó.  <br/> **fail**: indica la comprobación de DMARC que el mensaje no superó.  <br/> **bestguesspass**: indica que no existe ningún registro TXT de DMARC para el dominio, pero si hubiera existido, el mensaje habría superado la comprobación de DMARC. Esto se debe a que el dominio de la dirección 5321.MailFrom coincide con el dominio de la dirección 5322.From.  <br/> **none**: indica que no hay ningún registro TXT de DKIM para el dominio de envío en DNS.  <br/> |
|action  <br/> | Indica la acción efectuada por el filtro de correo no deseado en función de los resultados de la comprobación de DMARC. Por ejemplo:  <br/> **permerror** Se produjo un error permanente durante la evaluación de DMARC (por ejemplo, la detección de un registro TXT de DMARC con un formato incorrecto en DNS). Es probable que volver a enviar este mensaje no produzca un resultado diferente. Puede que deba ponerse en contacto con el propietario del dominio para intentar resolver el problema.  <br/> **temperror** Se produjo un error temporal durante la evaluación de DMARC. Puede solicitar al remitente que vuelva a enviar el mensaje un poco más tarde para procesar correctamente el correo electrónico.  <br/> **oreject** u **o.reject** Significa invalidar el rechazo. En este caso, Office 365 usa esta acción cuando recibe un mensaje que no supera la comprobación de DMARC desde un dominio cuyo registro TXT de DMARC tiene una directiva de p=reject. En lugar de eliminar o rechazar el mensaje, Office 365 marca el mensaje como correo no deseado. Para obtener más información sobre por qué Office 365 está configurado de esta forma, consulte [Cómo controla Office 365 el correo electrónico entrante que no supera las comprobaciones de DMARC](use-dmarc-to-validate-email.md#inbounddmarcfail).  <br/> **pct.quarantine** Indica que se entregará un porcentaje inferior al 100 % de los mensajes que no superen la comprobación de DMARC. Esto significa que el mensaje no superó la comprobación de DMARC y la directiva se estableció en cuarentena, pero el campo pct no se estableció en el 100 % y el sistema decidió, de forma aleatoria, no aplicar la acción de DMARC, de acuerdo con la directiva del dominio especificado.  <br/> **pct.reject** Indica que se entregará un porcentaje inferior al 100 % de los mensajes que no superen la comprobación de DMARC. Esto significa que el mensaje no superó la comprobación de DMARC y se estableció el rechazo de la directiva, pero el campo pct no se estableció en el 100 % y el sistema decidió, de forma aleatoria, no aplicar la acción de DMARC, de acuerdo con la directiva del dominio especificado.  <br/> |
|Header.From  <br/> |El dominio de la dirección De en el encabezado del mensaje de correo electrónico. A veces, recibe la denominación dirección 5322.From.  <br/> |
|compauth  <br/> |Resultado de la autenticación compuesto. Utilizado por Office 365 para combinar varios tipos de autenticación como SPF, DKIM, DMARC o cualquier otra parte del mensaje para determinar si el mensaje se autentica. Usa el From: dominio como base de evaluación.  <br/> |
|motivo  <br/> | La razón por la autenticación compuesta se pasa o errores. El valor de la razón por la se compone de tres dígitos:  <br/>  000 - el mensaje de error explícitamente la autenticación. Por ejemplo, recibe un error DMARC con una acción de cuarentena o rechazar el mensaje.  <br/>  001 - implícitamente el mensaje de error de autenticación y el dominio envío no publica las directivas de autenticación. Por ejemplo, una directiva de DMARC de p = none.  <br/>  1xx - autenticación pasa el mensaje. El segundo de dos dígitos son códigos internos utilizados por Office 365.  <br/>  2xx - la autenticación de mensajes se pasan temporalmente. El segundo de dos dígitos son códigos internos utilizados por Office 365.  <br/>  3xx - el mensaje no se ha protegido para la autenticación compuesta.  <br/>  4xx - el mensaje pasó autenticación compuesta. El segundo de dos dígitos son códigos internos utilizados por Office 365.  <br/> |
  