---
title: Usar DMARC para validar el correo electrónico en Office 365
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 4a05898c-b8e4-4eab-bd70-ee912e349737
ms.collection:
- M365-security-compliance
description: Obtenga información sobre cómo configurar la autenticación de mensajes basada en dominio, la creación de informes y la conformidad (DMARC) para validar los mensajes enviados desde su organización de Office 365.
ms.openlocfilehash: 9e3c2cd21e411d775f621c8b353bee9e6b0e235e
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/17/2019
ms.locfileid: "34156192"
---
# <a name="use-dmarc-to-validate-email-in-office-365"></a>Usar DMARC para validar el correo electrónico en Office 365

La autenticación de mensajes basada en el dominio, los informes y la conformidad ([DMARC](https://dmarc.org)) funcionan con el marco de directivas de remitente (SPF) y el correo identificado por DOMAINKEYS (DKIM) para autenticar a los remitentes de correo y garantizar que los sistemas de correo electrónico de destino confían en los mensajes enviados desde el dominio. Implementar DMARC con SPF y DKIM ofrece protección adicional contra el correo electrónico de suplantación de identidad. DMARC permite a los sistemas que reciben los correos determinar qué hacer con los mensajes enviados desde su dominio que no superan las comprobaciones SPF o DKIM.
  
## <a name="how-do-spf-and-dmarc-work-together-to-protect-email-in-office-365"></a>¿Cómo se coordinan SPF y DMARC para proteger el correo electrónico en Office 365?
<a name="SPFandDMARC"> </a>

 Un mensaje de correo electrónico puede contener varias direcciones de remitentes, que se usan para distintos propósitos. Por ejemplo, observe las siguientes direcciones: 
  
- **Dirección "mail from"**: identifica al remitente y especifica dónde enviar avisos de devolución si se producen problemas con la entrega del mensaje, como avisos de no entrega. Aparece en la zona del sobre de un mensaje de correo electrónico, aunque su aplicación de correo electrónico no suele mostrarla. A veces, recibe la denominación dirección 5321.MailFrom o dirección de ruta de acceso inversa.
    
- **Dirección "de"**: la dirección que muestra la dirección de de su aplicación de correo. Esta dirección identifica al autor del correo electrónico. Es decir, el buzón de la persona o el sistema responsable de escribir el mensaje. A veces, recibe la denominación dirección 5322.From.
    
SPF usa un registro TXT de DNS para proporcionar una lista de direcciones IP de envío autorizadas en un dominio dado. Normalmente, solo se realizan comprobaciones de SPF en la dirección 5321.MailFrom. Esto significa que la dirección de 5322.From no se autentica al usar solamente SPF. Esto habilita un escenario donde un usuario puede recibir un mensaje que pasa una comprobación de SPF, pero tiene una dirección de remitente 5322.From falsificada. Por ejemplo, veamos esta transcripción de SMTP:
  
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

En esta transcripción, las direcciones del remitente son las siguientes:
  
- Dirección MailFrom (5321.MailFrom): phish@phishing.contoso.com
    
- Dirección From (5322.From): security@woodgrovebank.com
    
Si configuró SPF, el servidor receptor realiza una comprobación en la dirección MailFrom phish@phishing.contoso.com. Si el mensaje procede de un origen válido para el dominio phishing.contoso.com, entonces pasa la comprobación de SPF. Como el cliente de correo electrónico muestra solo la dirección From, el usuario verá que este mensaje procede de security@woodgrovebank.com. Usando solo SPF, la validez de woodgrovebank.com nunca se autentica.
  
Cuando se usa DMARC, el servidor receptor también realiza una comprobación en la dirección From. En el ejemplo anterior, si no hay un registro TXT de DMARC para woodgrovebank.com, la comprobación de la dirección From da error.
  
## <a name="what-is-a-dmarc-txt-record"></a>¿Qué es un registro TXT de DMARC?
<a name="WhatisDMARC"> </a>

Al igual que los registros DNS para SPF, el registro para DMARC es un registro de texto (TXT) de DNS que ayuda a evitar la suplantación de identidad. Los registros TXT de DMARC se publican en DNS. Los registros TXT de DMARC validan el origen de los mensajes de correo electrónico contrastando la dirección IP del autor de un correo electrónico con el supuesto propietario del dominio de envío. El registro TXT de DMARC identifica los servidores de correo electrónico saliente autorizados. Así, los sistemas de correo electrónico de destino comprueban que los mensajes que reciben proceden de servidores de correo electrónico saliente autorizados.
  
El registro TXT de DMARC de Microsoft es algo así:
  
```
_dmarc.microsoft.com.   3600    IN      TXT     "v=DMARC1; p=none; pct=100; rua=mailto:d@rua.agari.com; ruf=mailto:d@ruf.agari.com; fo=1" 
```

Microsoft envía sus informes de DMARC a [Agari](https://agari.com), un agente externo. Agari recopila y analiza los informes de DMARC.
  
## <a name="implement-dmarc-for-inbound-mail"></a>Implementar DMARC para el correo entrante
<a name="implementDMARCinbound"> </a>

No hay que hacer nada para configurar DMARC para el correo que se recibe en Office 365. Nosotros nos hemos encargado de todo. Si quiere saber lo que ocurre con el correo que no pasa las comprobaciones de DMARC, vea [Cómo controla Office 365 el correo electrónico entrante que no supera las comprobaciones de DMARC](use-dmarc-to-validate-email.md#inbounddmarcfail).
  
## <a name="implement-dmarc-for-outbound-mail-from-office-365"></a>Implementar DMARC para el correo saliente de Office 365
<a name="implementDMARCoutbound"> </a>

Si usa Office 365, pero no está usando un dominio personalizado (sino el dominio onmicrosoft.com), solo tiene que configurar o implementar DMARC para la organización. SPF ya está configurado y Office 365 genera automáticamente una firma DKIM para el correo saliente. Para más información sobre esta firma, consulte [Comportamiento predeterminado para DKIM y Office 365](use-dkim-to-validate-outbound-email.md#DefaultDKIMbehavior).
  
 Si tiene un dominio personalizado o usa servidores de Exchange locales aparte de Office 365, implemente manualmente DMARC para el correo saliente. La implementación de DMARC para el dominio personalizado incluye estos pasos: 
  
- [Paso 1: Identificar orígenes válidos de correo para el dominio](use-dmarc-to-validate-email.md#IdentifyValidSources)
    
- [Paso 2: Configurar SPF para el dominio en Office 365](use-dmarc-to-validate-email.md#ConfigSPF)
    
- [Paso 3: Configurar DKIM para el dominio personalizado en Office 365](use-dmarc-to-validate-email.md#ConfigDKIM)
    
- [Paso 4: Formular el registro TXT de DMARC para el dominio en Office 365](use-dmarc-to-validate-email.md#CreateDMARCRecord)
    
### <a name="step-1-identify-valid-sources-of-mail-for-your-domain"></a>Paso 1: Identificar orígenes válidos de correo para el dominio
<a name="IdentifyValidSources"> </a>

Si tiene configurado SPF, quiere decir que ya ha hecho este paso. Sin embargo, para DMARC, hay que tener en cuenta otras cosas. Al identificar los orígenes de correo para el dominio, debemos responder a dos preguntas:
  
- ¿Qué direcciones IP envían mensajes desde mi dominio?
    
- En los correos electrónicos enviados por parte de terceros en mi nombre, ¿coincidirán los dominios 5321.MailFrom y 5322.From?
    
### <a name="step-2-set-up-spf-for-your-domain-in-office-365"></a>Paso 2: Configurar SPF para el dominio en Office 365
<a name="ConfigSPF"> </a>

Ahora que tiene una lista de todos los remitentes válidos, puede seguir los pasos para [Set up SPF in Office 365 to help prevent spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md).
  
Por ejemplo, suponiendo que contoso.com envía correos desde Exchange Online, un servidor Exchange local cuya dirección IP fuera 192.168.0.1 y una aplicación web cuya dirección IP fuera 192.168.100.100, el registro TXT de SPF tendría este aspecto:
  
```
contoso.com  IN  TXT  " v=spf1 ip4:192.168.0.1 ip4:192.168.100.100 include:spf.protection.outlook.com -all"
```

Como práctica recomendada, asegúrese de que el registro TXT de SPF tenga en cuenta a los remitentes externos.
  
### <a name="step-3-set-up-dkim-for-your-custom-domain-in-office-365"></a>Paso 3: Configurar DKIM para el dominio personalizado en Office 365
<a name="ConfigDKIM"> </a>

Cuando haya configurado SPF, deberá configurar DKIM. DKIM le permite agregar una firma digital en el encabezado de los mensajes de correo electrónico. Si no configura DKIM pero permite a Office 365 usar la configuración predeterminada de DKIM en el dominio, DMARC puede dar errores. Esto se debe a que la configuración predeterminada de DKIM usa el dominio onmicrosoft.com inicial como dirección de 5322.From, es decir, no usa el dominio personalizado. Esto provoca una discrepancia entre las direcciones 5321.MailFrom y 5322.From en todos los correos electrónicos enviados desde su dominio.
  
Si hay remitentes externos que envían correo en su nombre y el correo que envían tiene direcciones 5322.From y 5321.MailFrom que no coinciden, se producirá un error de DMARC en este correo electrónico. Para evitar esto, tendrá que configurar DKIM para el dominio, en concreto con ese remitente externo. Esto permite a Office 365 autenticar el correo electrónico desde el servicio de esta tercera parte. Sin embargo, también permite a otros usuarios, por ejemplo, Yahoo, Gmail y Comcast, comprobar la validez del correo electrónico que les envía la tercera parte como si lo hubiera enviado usted. Esto es beneficioso porque permite a los clientes generar relaciones de confianza con el dominio independientemente del sitio donde se encuentre su buzón y, al mismo tiempo, Office 365 no marca un mensaje como correo no deseado por suplantación de identidad, ya que pasa las comprobaciones de autenticación para el dominio.
  
Para ver las instrucciones sobre cómo configurar DKIM para el dominio, incluyendo cómo configurar DKIM para remitentes externos para que puedan suplantar la identidad de su dominio, consulte [Usar DKIM para validar el correo electrónico saliente enviado desde su dominio personalizado en Office 365](use-dkim-to-validate-outbound-email.md).
  
### <a name="step-4-form-the-dmarc-txt-record-for-your-domain-in-office-365"></a>Paso 4: Formular el registro TXT de DMARC para el dominio en Office 365
<a name="CreateDMARCRecord"> </a>

Aunque existen otras opciones de sintaxis que no se mencionan aquí, estas son las opciones de sintaxis más usadas en Office 365. Formule el registro TXT de DMARC para el dominio con el siguiente formato:
  
```
_dmarc.domain  TTL  IN  TXT  "v=DMARC1; pct=100; p=policy"
```

donde:
  
- *domain* es el dominio que quiere proteger. De forma predeterminada, el registro protege el correo del dominio y todos los subdominios. Por ejemplo, si especifica \_DMARC.contoso.com, dMarc protege el correo del dominio y todos los subdominios, como housewares.contoso.com o Plumbing.contoso.com. 
    
- *TTL* siempre debe ser el equivalente a una hora. La unidad usada para el TTL, ya sean las horas (1 hora), los minutos (60 minutos) o los segundos (3600 segundos), variará en función del registrador del dominio. 
    
- *PCT = 100* indica que esta regla debe usarse para el 100% del correo electrónico.
    
- *policy* especifica qué directiva quiere que el servidor de recepción siga si se produce un error en DMARC. Puede establecer la directiva en none, quarantine o reject. 
    
Para obtener información sobre las opciones que se usan, consulte los conceptos de las [Prácticas recomendadas para la implementación de DMARC en Office 365](use-dmarc-to-validate-email.md#DMARCbestpractices).
  
Ejemplos
  
- Directiva establecida en none
  
    ```
    _dmarc.contoso.com 3600 IN  TXT  "v=DMARC1; p=none"
    ```

- Directiva establecida en quarantine
  
    ```
    _dmarc.contoso.com 3600 IN  TXT  "v=DMARC1; p=quarantine"
    ```

- Directiva establecida en reject
  
    ```
    _dmarc.contoso.com  3600 IN  TXT  "v=DMARC1; p=reject"
    ```

Una vez que formule el registro, debe actualizarlo en el registrador del dominio. Para obtener instrucciones sobre cómo agregar el registro TXT de DMARC en los registros DNS para Office 365, consulte [Crear registros DNS para Office 365 al administrar los registros DNS](https://support.office.com/article/b0f3fdca-8a80-4e8e-9ef3-61e8a2a9ab23).
  
## <a name="best-practices-for-implementing-dmarc-in-office-365"></a>Prácticas recomendadas para la implementación de DMARC en Office 365
<a name="DMARCbestpractices"> </a>

DMARC se puede implementar gradualmente sin que esto afecte al resto del flujo de correo. Cree e implemente un plan de distribución con estos pasos de implementación. Realice cada uno de estos pasos primero con un subdominio, luego con otros subdominios y, finalmente, con el dominio de nivel superior de la organización antes de continuar con el paso siguiente.
  
1. Supervisar el impacto de implementar DMARC
    
    Comience con un registro en modo de supervisión simple para un subdominio o dominio que solicita que los receptores DMARC le envíen estadísticas sobre los mensajes que usan ese dominio. Un registro en modo de supervisión es un registro TXT de DMARC con la directiva establecida en none (p=none). Muchas empresas publican un registro TXT de DMARC con p=none porque no saben cuánto correo electrónico se pueden perder al publicar una directiva de DMARC más restrictiva. 
    
    Puede hacer esto incluso antes de implementar SPF o DKIM en la infraestructura de mensajería. Sin embargo, no podrá poner en cuarentena ni rechazar eficazmente el correo mediante DMARC hasta que no implemente también SPF y DKIM. Al introducir SPF y DKIM, los informes generados mediante DMARC indicarán los números y los orígenes de los mensajes que pasen estas comprobaciones y los que no. Se puede ver fácilmente qué cantidad del tráfico legítimo está cubierto o no por ellos, así como solucionar los problemas. También empezará a ver cuántos mensajes fraudulentos se envían y desde dónde.
    
2. Solicitar que los sistemas de correo externos pongan en cuarentena el correo que no supera las comprobaciones de DMARC
    
    Cuando cree que todo el tráfico legítimo o la mayor parte está protegido por SPF y DKIM, y sabe cuál es el impacto de implementar DMARC, puede implementar una directiva de cuarentena. Una directiva de cuarentena es un registro TXT de DMARC con una directiva establecida en quarantine (p=quarantine). Al hacer esto, pedimos a los receptores DMARC que pongan los mensajes de su dominio que no superen las pruebas de DMARC en el equivalente local a una carpeta de correo no deseado, en lugar de en las bandejas de entrada de los clientes.
    
3. Solicitar que los sistemas de correo externos no aceptan mensajes que no superen las pruebas de DMARC
    
    El último paso es implementar una directiva de rechazo. Una directiva de rechazo es un registro TXT de DMARC con una directiva establecida en reject (p=reject). Al hacerlo, pedimos a los receptores DMARC que no acepten los mensajes que no pasan las comprobaciones de DMARC. 
    
## <a name="how-office-365-handles-outbound-email-that-fails-dmarc"></a>Cómo controla Office 365 el correo electrónico saliente que no supera las comprobaciones de DMARC
<a name="outbounddmarcfail"> </a>

Si un mensaje es saliente de Office 365 y se produce un error de DMARC y ha establecido la Directiva en p = Quarantine o p = Reject, el mensaje se enruta a través del [grupo de entrega de alto riesgo para los mensajes salientes](high-risk-delivery-pool-for-outbound-messages.md). No hay ninguna invalidación para el correo saliente.
  
Si publica una directiva de rechazo de DMARC (p=reject), ningún otro cliente de Office 365 podrá suplantar la identidad de su dominio porque los mensajes no podrán pasar las comprobaciones de SPF o DKIM para el dominio al retransmitir un mensaje saliente a través del servicio. Sin embargo, si publica una directiva de rechazo de DMARC, pero no dispone de todo el correo electrónico autenticado a través de Office 365, una parte del correo entrante se puede marcar como correo no deseado (como se describe más arriba) o se rechazará si no publica SPF e intenta retransmitirlo para que salga a través del servicio. Esto sucede, por ejemplo, si se olvida de incluir algunas de las direcciones IP para servidores y aplicaciones que envían correo en nombre de su dominio al formular el registro TXT de DMARC.
  
## <a name="how-office-365-handles-inbound-email-that-fails-dmarc"></a>Cómo controla Office 365 el correo electrónico entrante que no supera las comprobaciones de DMARC
<a name="inbounddmarcfail"> </a>

Si la directiva DMARC del servidor de envío es p=reject, EOP marca el mensaje como correo no deseado en lugar de rechazarlo. En otras palabras, para el correo electrónico entrante, Office 365 considera que p=reject y p=quarantine es lo mismo.
  
Office 365 está configurado así porque hay mensajes de correo legítimos que pueden no superar las comprobaciones de DMARC. Por ejemplo, un mensaje podría no superar las pruebas DMARC si se envía a una lista de distribución que luego transmite el mensaje a todos los participantes de la lista. Si Office 365 rechaza estos mensajes, las personas podrían perder el correo electrónico legítimo y no habría forma de recuperarlo. Es decir, estos mensajes seguirían provocando un error en DMARC, pero se marcarían como correo no deseado y no se rechazarían. Los usuarios que quisieran podrían colocar estos mensajes en la bandeja de entrada a través de estos métodos:
  
- Los usuarios agregan remitentes seguros individualmente mediante el cliente de correo electrónico
    
- Los administradores crean una regla de flujo de correo de Exchange (también denominada regla de transporte) para todos los usuarios que permiten mensajes para esos remitentes en particular. 
    
## <a name="troubleshooting-your-dmarc-implementation"></a>Solución de problemas en la implementación de DMARC
<a name="dmarctroubleshoot"> </a>

Si configuró los registros MX de su dominio donde EOP no es la primera entrada, los errores de DMARC no se aplicarán en su dominio. 
  
Si usted es cliente de Office 365 y el registro MX principal de su dominio no apunta a EOP, no obtendrá las ventajas de DMARC. Por ejemplo, DMARC no funcionará si apunta el registro MX al servidor de correo local y luego enruta el correo electrónico a EOP usando un conector. En este escenario, el dominio receptor es uno de los dominios aceptados, pero EOP no es el MX principal. Por ejemplo, si contoso.com apunta su MX a sí mismo y usa EOP como registro MX secundario, el registro MX de contoso.com será así:
  
```
contoso.com     3600   IN  MX  0  mail.contoso.com
contoso.com     3600   IN  MX  10 contoso-com.mail.protection.outlook.com
```

Todo el correo electrónico o la mayor parte se enrutará primero a mail.contoso.com, ya que es el MX principal, y luego el correo se enrutará a EOP. En algunos casos, ni siquiera podría marcar EOP como registro MX y solo podría enlazar conectores para enrutar el correo electrónico. EOP no tiene que ser la primera entrada para que se realice la validación de DMARC. Solo garantiza la validación, ya que no se puede garantizar que todos los servidores locales o que no sean de O365 realizarán comprobaciones de DMARC.  DMARC se puede aplicar a un dominio de un cliente (no al del servidor) cuando se configura el registro TXT de DMARC, pero el servidor receptor no puede realmente realizar la obligatoriedad de hacerlo.  Si configura EOP como el servidor de recepción, EOP realiza la aplicación de DMARC.
  
## <a name="for-more-information"></a>Más información
<a name="sectionSection8"> </a>

¿Quiere más información sobre DMARC? Estos recursos lo pueden ayudar.
  
- Los [Encabezados de mensajes de correo no deseado](anti-spam-message-headers.md) incluyen la sintaxis y los campos de encabezado que usa Office 365 para efectuar comprobaciones de DMARC. 
    
- Siga la [Serie de aprendizaje de DMARC](https://www.m3aawg.org/activities/training/dmarc-training-series) from M <sup>3</sup>AAWG (Messaging, Malware, Mobile Anti-Abuse Working Group).
    
- Use la lista de comprobación que verá en [dmarcian](https://space.dmarcian.com/deployment/).
    
- Vaya directamente al origen en [DMARC.org](https://dmarc.org).
    
## <a name="see-also"></a>Vea también
<a name="sectionSection8"> </a>

[Cómo Office 365 usa el marco de directivas de remitente (SPF) para evitar la suplantación de identidad](how-office-365-uses-spf-to-prevent-spoofing.md)
  
[Configurar SPF en Office 365 para ayudar a evitar la suplantación de identidad](set-up-spf-in-office-365-to-help-prevent-spoofing.md)
  
[Usar DKIM para validar el correo electrónico saliente enviado desde su dominio personalizado en Office 365](use-dkim-to-validate-outbound-email.md)

