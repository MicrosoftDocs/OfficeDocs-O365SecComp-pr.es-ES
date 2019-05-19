---
title: Protección contra la suplantación de identidad en Office 365
ms.author: tracyp
author: MSFTtracyp
manager: laurawi
ms.date: 03/29/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
search.appverid:
- MET150
ms.assetid: d24bb387-c65d-486e-93e7-06a4f1a436c0
ms.collection:
- M365-security-compliance
- Strat_O365_IP
ms.custom: TopSMBIssues
localization_priority: Priority
description: Este artículo describe cómo Office 365 reduce los ataques de phishing que usan dominios de remitentes falsificados, es decir, dominios suplantados. Para ello, analiza los mensajes y bloquea los que no pueden autenticarse mediante métodos de autenticación de correo electrónico estándar ni otras técnicas de reputación del remitente. Este cambio se implementó para reducir el número de ataques de phishing a los que se exponen las organizaciones de Office 365.
ms.openlocfilehash: 455ce577e4ffb3dc4d943004dd3c299e7e6f1eae
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/17/2019
ms.locfileid: "34155782"
---
# <a name="anti-spoofing-protection-in-office-365"></a>Protección contra la suplantación de identidad en Office 365

Este artículo describe cómo Office 365 reduce los ataques de phishing que usan dominios de remitentes falsificados, es decir, dominios suplantados. Para ello, analiza los mensajes y bloquea los que no pueden autenticarse mediante métodos de autenticación de correo electrónico estándar ni otras técnicas de reputación del remitente. Este cambio se implementó para reducir el número de ataques de phishing a los que se exponen las organizaciones de Office 365.
  
Este artículo también describe por qué se ha realizado este cambio, cómo pueden prepararse los clientes, cómo ver los mensajes que se verán afectados, cómo enviar informes sobre mensajes, cómo reducir los falsos positivos y cómo deben prepararse los remitentes de Microsoft para el cambio.
  
La tecnología contra la suplantación de Microsoft se implementó inicialmente para las organizaciones que tenían una suscripción a Office 365 Enterprise E5 o que habían comprado el complemento de Protección contra amenazas avanzada de Office 365 (ATP) para su suscripción. A partir de octubre de 2018, la protección se ha ampliado también para las organizaciones con Exchange Online Protection (EOP). Además, debido a la forma en que todos nuestros filtros aprenden unos de los otros, los usuarios de Outlook.com pueden verse afectados.
  
## <a name="how-spoofing-is-used-in-phishing-attacks"></a>Usar la suplantación de identidad (spoofing) en ataques de phishing

Cuando se trata de proteger a sus usuarios, Microsoft se toma muy en serio las amenazas de suplantación de identidad. Una de las técnicas que suelen utilizar los spammer y suplantadores es el "spoofing", que ocurre cuando se falsifica el remitente y un mensaje parece proceder de una persona u origen que no es el real. Esta técnica se usa a menudo en campañas de "phishing", diseñadas para obtener credenciales de usuarios. La tecnología contra la suplantación de identidad de Microsoft examina específicamente la falsificación del "encabezado De:", que es el que se muestra en un cliente de correo electrónico, como Outlook. Cuando Microsoft tiene alta confianza que el encabezado De: está falsificado, identifica el mensaje como una suplantación de identidad.
  
Los mensajes de suplantación de identidad tienen dos implicaciones negativas para los usuarios en la vida real:
  
### <a name="1-spoofed-messages-deceive-users"></a>1. Los mensajes falsificados engañan a los usuarios
  
En primer lugar, un mensaje falsificado puede engañar a un usuario para que haga clic en un vínculo y proporcione sus credenciales, descargue malware o responda a un mensaje con contenido confidencial (esto último se conoce como Business Email Compromise: compromiso de correo electrónico empresarial). Por ejemplo, el siguiente es un mensaje de suplantación de identidad con un remitente falsificado de msoutlook94@service.outlook.com:
  
![Mensaje de suplantación de identidad que suplanta service.outlook.com](media/1a441f21-8ef7-41c7-90c0-847272dc5350.jpg)
  
El mensaje anterior no proviene realmente de service.outlook.com, pero el atacante lo ha falsificado para que así parezca. Intenta engañar a un usuario para que haga clic en el vínculo del mensaje.
  
En el ejemplo siguiente se está suplantando contoso.com:
  
![Mensaje de suplantación de identidad: compromiso de correo electrónico empresarial](media/da15adaa-708b-4e73-8165-482fc9182090.jpg)
  
El mensaje parece legítimo, pero en realidad es una suplantación de identidad. Este mensaje de suplantación de identidad es un tipo de compromiso de correo electrónico empresarial, que es una subcategoría de suplantación de identidad.

### <a name="2-users-confuse-real-messages-for-fake-ones"></a>2. Los usuarios confunden mensajes reales con mensajes falsificados
  
En segundo lugar, los mensajes falsificados crean incertidumbre para los usuarios que conocen los mensajes de suplantación de identidad, pero no pueden diferenciar un mensaje verdadero de uno falso. Por ejemplo, el siguiente es un ejemplo de un restablecimiento de contraseña real desde la dirección de correo electrónico de la cuenta de Microsoft Security:
  
![Restablecimiento de contraseña legítimo de Microsoft](media/58a3154f-e83d-4f86-bcfe-ae9e8c87bd37.jpg)
  
El mensaje anterior proviene de Microsoft, pero al mismo tiempo, los usuarios están acostumbrados a recibir mensajes de suplantación de identidad que pueden engañar a un usuario para que haga clic en un vínculo y proporcione sus credenciales, descargue malware o responda a un mensaje con contenido confidencial. Como es difícil notar la diferencia entre un restablecimiento de contraseña verdadero y uno falso, muchos usuarios ignoran estos mensajes, los marcan como correo no deseado o informan innecesariamente sobre ellos a Microsoft como intentos de suplantaciones de identidad.

Para detener la suplantación de identidad, el sector de filtrado de correo electrónico ha desarrollado protocolos de autenticación como [SPF](https://docs.microsoft.com/office365/SecurityCompliance/set-up-spf-in-office-365-to-help-prevent-spoofing), [DKIM](https://docs.microsoft.com/office365/SecurityCompliance/use-dkim-to-validate-outbound-email) y [DMARC](https://docs.microsoft.com/office365/SecurityCompliance/use-dmarc-to-validate-email). DMARC evita la suplantación examinando el remitente de un mensaje, el que el usuario ve en su cliente de correo electrónico (en los ejemplos anteriores, service.outlook.com, outlook.com y accountprotection.microsoft.com), con el dominio que no ha producido un error de SPF o DKIM. Es decir, el dominio que el usuario ve se ha autenticado y, por tanto, no está falsificado. Para obtener una explicación más completa, vea la sección "*Comprender por qué la autenticación de correo electrónico no siempre es suficiente para detener la suplantación de identidad"* más adelante en este artículo.
  
Pero, el problema es que los registros de autenticación de correo electrónico son opcionales, no necesarios. Por lo tanto, aunque los dominios con directivas de autenticación seguras como microsoft.com y skype.com están protegidos frente a la suplantación de identidad, los que utilizan directivas de autenticación más débiles o no usan ninguna directiva son objetivos para la suplantación. En marzo de 2018, sólo un 9% de los dominios de empresas en la Fortune 500 publicaron directivas de autenticación de correo electrónico seguras. El 91% restante podía ser falsificado por un atacante y, a menos que el filtro de correo electrónico lo detectara con otra directiva, podía llegar a un usuario final y engañarlo:
  
![Directivas DMARC de las empresas en Fortune 500](media/84e77d34-2073-4a8e-9f39-f109b32d06df.jpg)
  
La proporción de pequeñas y medianas empresas que no están en la lista Fortune 500 y que publican directivas de autenticación de correo electrónico seguras es menor y es incluso más pequeña para los dominios que están fuera de Norteamérica y Europa occidental.
  
Esto es un gran problema ya que, aunque las empresas pueden no ser conscientes de cómo funciona la autenticación de correo electrónico, los suplantadores sí que la comprenden y se aprovechan de la ausencia de la misma.
  
Para obtener información sobre cómo configurar SPF, DKIM y DMARC, vea la sección "*Clientes de Office 365"* más adelante en este documento. 
  
## <a name="stopping-spoofing-with-implicit-email-authentication"></a>Detener la suplantación de identidad con la autenticación de correo electrónico implícita

Puesto que el phishing y el "spear phishing" (ataques de suplantación dirigidos a un objetivo específico) son un problema tan importante y debido a una adopción de directivas de autenticación de correo electrónico seguras tan limitada, Microsoft continúa invirtiendo en funciones para proteger a sus clientes. Por lo tanto, Microsoft va a seguir adelante con la *autenticación de correo electrónico implícita*: si un dominio no se autentica, Microsoft lo trata como si hubiese publicado registros de autenticación de correo electrónico y lo trata en consecuencia si produce un error de autenticación. 
  
Para ello, Microsoft ha creado muchas extensiones para la autenticación de correo electrónico normal, como la reputación del remitente, el historial de remitentes y destinatarios, el análisis de comportamiento y otras técnicas avanzadas. Un mensaje enviado desde un dominio que no publica la autenticación de correo electrónico se marcará como suplantación de identidad a menos que contenga otras señales que indiquen que es legítimo.
  
Al hacer esto, los usuarios finales pueden confiar en que los correos que les han enviado no se han falsificado, los remitentes pueden estar seguros de que nadie está suplantando su dominio y los clientes de Office 365 pueden ofrecer una protección aún mejor, como la protección de suplantación.
  
Para ver el anuncio general de Microsoft, vea [Un mar de phishing, parte 2: Protección contra la suplantación de identidad mejorada en Office 365](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Schooling-A-Sea-of-Phish-Part-2-Enhanced-Anti-spoofing/ba-p/176209).
  
## <a name="identifying-that-a-message-is-classified-as-spoofed"></a>Identificar que un mensaje se clasifica como falsificado

### <a name="composite-authentication"></a>Autenticación compuesta

Aunque SPF, DKIM y DMARC son útiles por sí mismos, no comunican de forma suficiente el estado de autenticación en caso de que un mensaje no contenga ningún registro de autenticación explícito. Por lo tanto, Microsoft ha desarrollado un algoritmo que combina varias señales en un único valor denominado autenticación compuesta ("compauth" para abreviar). Los clientes de Office 365 tienen valores de autenticación compuesta marcados en el encabezado *Authentication-Results* en los encabezados de mensaje. 
  
```
Authentication-Results:
  compauth=<fail|pass|softpass|none> reason=<yyy>

```

|**Resultado CompAuth**|**Descripción**|
|:-----|:-----|
|fail|El mensaje ha producido un error de autenticación explícita (el dominio remitente publica los registros explícitamente en el DNS) o autenticación implícita (el dominio remitente no publica los registros en el DNS, por lo que Office 365 interpola el resultado como si hubiera publicado los registros).|
|pass|El mensaje no ha producido un error de autenticación explícita (el mensaje no ha producido un error de DMARC, o [Best Guess Passed DMARC](https://blogs.msdn.microsoft.com/tzink/2015/05/06/what-is-dmarc-bestguesspass-in-office-365)) o autenticación implícita de alta confianza (el dominio remitente no publica los registros de autenticación de correo electrónico, pero Office 365 tiene seguros señales back-end para indicar que el mensaje es probablemente legítimo).|
|softpass|El mensaje no ha producido un error de autenticación implícita de confianza baja o mediana (el dominio remitente no publica la autenticación de correo electrónico, pero Office 365 tiene señales back-end para indicar el mensaje es legítimo aunque la potencia de la señal es más débil).|
|none|El mensaje no se ha autenticado (o se ha autenticado pero no se ha alineado), pero no se aplica la autenticación compuesta debido a la reputación del remitente u otros factores.|
   
|||
|:-----|:-----|
|**Motivo**|**Descripción**|
|0xx|El mensaje ha producido un error de autenticación compuesta.<br/>**000** significa que el mensaje ha producido un error de DMARC con una acción de rechazo o cuarentena.  <br/>**001** significa que el mensaje ha producido un error de autenticación de correo electrónico implícita. Esto significa que el dominio remitente no ha publicado registros de autenticación de correo electrónico o, si los ha publicado, tenían una directiva de error más débil (errores recuperables de SPF o neutrales, directiva DMARC p=none).  <br/>**002** significa que la organización tiene una directiva para el par de remitente y dominio que prohíbe explícitamente el envío de correos electrónicos falsificados. Esta configuración la establece manualmente un administrador.  <br/>**010** significa que el mensaje ha producido un error de DMARC con una acción de rechazo o cuarentena y el dominio es uno de los dominios aceptados de su organización (esto es parte de la suplantación de identidad interna o dentro de la organización).  <br/>**011** significa que el mensaje ha producido un error de autenticación de correo electrónico implícita y el dominio es uno de los dominios aceptados de su organización (esto es parte de la suplantación de identidad interna o dentro de la organización).|
|Todos los demás códigos (1xx 2xx, 3xx, 4xx, 5xx)|Corresponde a varios códigos internos de por qué un mensaje no ha producido un error de autenticación implícita o no tenía ninguna autenticación, pero no se ha aplicado ninguna acción.|
   
Consultando los encabezados de un mensaje, un administrador o incluso un usuario final puede determinar cómo Office 365 llega a la conclusión de que el remitente puede estar falsificado.
  
### <a name="differentiating-between-different-types-of-spoofing"></a>Diferenciar entre los distintos tipos de suplantación de identidad

Microsoft distingue entre dos tipos de mensajes de suplantación de identidad:
  
 **Suplantación de identidad dentro de la organización**
  
También se denomina suplantación interna, esto ocurre cuando el dominio de la dirección en De: es igual o se alinea con el dominio del destinatario (cuando este es uno de los [dominios aceptados](https://technet.microsoft.com/es-ES/library/jj945194%28v=exchg.150%29.aspx) de su organización) o si el dominio de la dirección en De: es parte de la misma organización.
  
Por ejemplo, los siguientes tienen remitente y destinatario desde el mismo dominio (contoso.com). Se insertan espacios en la dirección de correo electrónico para evitar la recopilación de los spambot en esta página):
  
De: remitente @ contoso.com
  
Para: destinatario @ contoso.com
  
Los siguientes tienen los dominios de remitente y destinatario que se alinean con el dominio de la organización (fabrikam.com):
  
De: remitente @ foo.fabrikam.com
  
Para: destinatario @ bar.fabrikam.com
  
Los dominios de remitente y destinatario siguientes son diferentes (microsoft.com y bing.com), pero pertenecen a la misma organización (es decir, ambos son parte de los dominios aceptados de la organización):
  
De: remitente @ microsoft.com
  
Para: destinatario @ bing.com
  
Los mensajes que producen un error de suplantación de identidad dentro de la organización contienen los siguientes valores en los encabezados:
  
X-Forefront-Antispam-Report: ...CAT:SPM/HSPM/PHSH;...SFTY:9.11
  
CAT es la categoría del mensaje y normalmente se marca como SPM (spam), pero en ocasiones pueden ser HSPM (spam de alta confianza) o PHISH (phishing), dependiendo de qué otros tipos de patrones aparecen en el mensaje.
  
El SFTY es el nivel de seguridad del mensaje, el primer dígito (9) del mensaje significa que el mensaje es phishing y el segundo conjunto de dígitos después del punto (11) significa que es una suplantación de identidad dentro de la organización.
  
No hay ningún código de motivo de autenticación compuesta para la suplantación dentro de la organización que se marcará más adelante en 2018 (escala de tiempo aún por definir).
  
 **Suplantación de identidad entre dominios**
  
Esto ocurre cuando el dominio remitente de la dirección en De: es un dominio externo a la organización receptora. Los mensajes que producen un error de autenticación compuesta debido a la suplantación de identidad entre dominios contienen los valores siguientes en los encabezados:
  
Authentication-Results: ... compauth=fail reason=000/001
  
X-Forefront-Antispam-Report: ...CAT:SPOOF;...SFTY:9.22
  
En ambos casos, se marca la siguiente sugerencia de seguridad roja en el mensaje o un equivalente personalizado para el idioma del buzón del destinatario:
  
![Sugerencia de seguridad roja: detección de fraude](media/a366156a-14e8-4c14-bfe5-2031b21936f8.jpg)
  
Puede diferenciar entre suplantación de identidad dentro de la organización y entre dominios solo consultando la dirección en De: y sabiendo cuál es el correo electrónico del destinatario o examinando los encabezados de correo electrónico.
  
## <a name="how-customers-of-office-365-can-prepare-themselves-for-the-new-anti-spoofing-protection"></a>Cómo los clientes de Office 365 pueden prepararse para la nueva protección contra la suplantación 

### <a name="information-for-administrators"></a>Información para administradores

Como administrador de una organización en Office 365, hay varios detalles clave que debería considerar.
  
### <a name="understanding-why-email-authentication-is-not-always-enough-to-stop-spoofing"></a>Comprender por qué la autenticación de correo electrónico no siempre es suficiente para detener la suplantación de identidad

La nueva protección contra la suplantación se basa en la autenticación de correo electrónico (SPF, DKIM y DMARC) para que un mensaje no se marque como la suplantación de identidad. Un ejemplo común es cuando un dominio remitente nunca ha publicado registros SPF. Si no hay ningún registro SPF o no están configurados correctamente, se marcará un mensaje enviado como falsificado a menos que Microsoft tiene inteligencia back-end que indique que el mensaje es legítimo.
  
Por ejemplo, antes de la implementación de la protección contra la suplantación, un mensaje podía aparecer sin registros SPF, DKIM y DMARC como el siguiente: 
  
```
Authentication-Results: spf=none (sender IP is 1.2.3.4)
  smtp.mailfrom=example.com; contoso.com; dkim=none
  (message not signed) header.d=none; contoso.com; dmarc=none
  action=none header.from=example.com;
From: sender @ example.com
To: receiver @ contoso.com
```
Después de la implementación, si tiene Office 365 Enterprise E5, EOP o ATP, se marca el valor compauth:
  
```
Authentication-Results: spf=none (sender IP is 1.2.3.4)
  smtp.mailfrom=example.com; contoso.com; dkim=none
  (message not signed) header.d=none; contoso.com; dmarc=none
  action=none header.from=example.com; compauth=fail reason=001
From: sender @ example.com
To: receiver @ contoso.com

```

Si ejemplo.com lo corrigió al configurar un registro SPF, pero no un registro DKIM, esto no produciría un error de autenticación compuesta porque el dominio de la dirección en De: se alinea con el dominio que no ha producido un error de SPF: 
  
```
Authentication-Results: spf=pass (sender IP is 1.2.3.4)
  smtp.mailfrom=example.com; contoso.com; dkim=none
  (message not signed) header.d=none; contoso.com; dmarc=bestguesspass
  action=none header.from=example.com; compauth=pass reason=109
From: sender @ example.com
To: receiver @ contoso.com
```

O bien, si se configuró un registro DKIM, pero no un registro SPF, esto tampoco produciría un error de autenticación compuesta porque el dominio de la dirección en De: se alinea con el dominio de la firma de DKIM que no ha producido el error: 
  
```
Authentication-Results: spf=none (sender IP is 1.2.3.4)
  smtp.mailfrom=example.com; contoso.com; dkim=pass
  (signature was verified) header.d=outbound.example.com;
  contoso.com; dmarc=bestguesspass action=none
  header.from=example.com; compauth=pass reason=109
From: sender @ example.com
To: receiver @ contoso.com
```

Pero, un atacante también puede configurar SPF o DKIM y firmar el mensaje con su propio dominio y especificar un dominio de la dirección en De: diferente. SPF y DKIM no requieren que el dominio se alinee con el dominio de la dirección De:, por ello, a menos que ejemplo.com haya publicado registros DMARC, este no se marcará como una suplantación de identidad mediante DMARC: 
  
```
Authentication-Results: spf=pass (sender IP is 5.6.7.8)
  smtp.mailfrom=maliciousDomain.com; contoso.com; dkim=pass
  (signature was verified) header.d=maliciousDomain.com;
  contoso.com; dmarc=none action=none header.from=example.com;
From: sender @ example.com
To: receiver @ contoso.com
```

En el cliente de correo electrónico (Outlook, Outlook en la Web o cualquier otro cliente de correo electrónico), se muestra solo el dominio en De:, sin el dominio en SPF o DKIM. Esto puede confundir al usuario y hacerle pensar que el mensaje proviene de ejemplo.com, pero realmente procede de dominioMalintencionado.com.
  
![El mensaje autenticado pero el dominio en De: no se alinea con lo que no produce error de SPF o DKIM](media/a9b5ab2a-dfd3-47c6-8ee8-e3dab2fae528.jpg)
  
Por ello, Office 365 requiere que el dominio de la dirección en De: se alinee con el dominio en la firma SPF o DKIM y si no, que contenga otras señales internas que indican que el mensaje es legítimo. En caso contrario, el mensaje es un error compauth. 
  
```
Authentication-Results: spf=none (sender IP is 5.6.7.8)
  smtp.mailfrom=maliciousDomain.com; contoso.com; dkim=pass
  (signature was verified) header.d=maliciousDomain.com;
  contoso.com; dmarc=none action=none header.from=contoso.com;
  compauth=fail reason=001
From: sender@contoso.com
To: someone@example.com
```

Por ello, la directiva contra la suplantación de Office 365 protege de los dominios sin autenticación y de los que configuran la autenticación, pero que no coinciden con el dominio de la dirección en De:, ya que este es el que el usuario ve y cree que es el remitente del mensaje. Esto es cierto tanto para los dominios externos a su organización, como para los dominios dentro de su organización.
  
Por ello, si recibe un mensaje que produjo un error de autenticación compuesta y se marcó como falsificado, aunque el mensaje nunca ha producido un error SPF y DKIM, es porque el dominio de la dirección en De: no se alinea con el dominio que no ha producido el error SPF y DKIM.
  
### <a name="understanding-changes-in-how-spoofed-emails-are-treated"></a>Comprender los cambios de cómo se tratan los correos electrónicos falsificados

Actualmente, en todas las organizaciones de Office 365, se marcan como correo no deseado los mensajes ATP y sin ATP que producen un error DMARC con una directiva de rechazo o cuarentena y se suelen tomar medidas de correo no deseado de alta confianza y, a veces, medidas de correo no deseado normal (dependiendo de si otra regla de correo no deseado primero lo identifica como tal). Las detecciones de suplantación de identidad dentro de la organización toman medidas de spam normal. No debe habilitarse este comportamiento y tampoco puede deshabilitarse.
  
Pero, para los mensajes de suplantación entre dominios, antes de este cambio pasaban por comprobaciones normales de spam, phishing y malware y, si otras partes del filtro los identificaban como sospechosos, se marcaban como spam, phishing o malware respectivamente. Con la nueva protección contra la suplantación entre dominios, para los mensajes que no se pueden autenticar, de forma predeterminada, se tomarán las medidas definidas en Protección contra suplantación de identidad \> Directiva contra la suplantación. Si uno no se define, se moverá a una carpeta de correo no deseado de los usuarios. En algunos casos, a los mensajes sospechosos también se les agregará la sugerencia de seguridad roja.
  
Por ello, algunos mensajes marcados previamente como spam siguen marcados, pero ahora también tendrá una sugerencia de seguridad roja; en otros casos, los mensajes marcados previamente como correo deseado se marcarán como spam (CAT:SPOOF) y se les agregará una sugerencia de seguridad roja. En otros casos, los clientes que solían mover todos los spam y phishing a la cuarentena, ahora los encontrará en la carpeta de correo no deseado (para cambiar este comportamiento, vea [Cambiar la configuración contra la suplantación](#changing-your-anti-spoofing-settings)).
  
Hay varias maneras para suplantar un mensaje (vea [Diferenciar entre los distintos tipos de suplantación de identidad](#differentiating-between-different-types-of-spoofing) anteriormente en este artículo), pero hasta marzo de 2018, la forma en que Office 365 los trata aún no se ha unificado. En la tabla siguiente hay un resumen rápido en el que la protección de suplantación entre dominios muestra el comportamiento nuevo: 
  
|**Tipo de suplantación de identidad**|**Categoría**|**¿Se ha agregado la sugerencia de seguridad?**|**Se aplica a**|
|:-----|:-----|:-----|:-----|
|Error DMARC (cuarentena o rechazo)  <br/> |HSPM (predeterminado), también puede ser SPM o PHSH  <br/> |No (todavía no)  <br/> |Todos los clientes de Office 365, Outlook.com  <br/> |
|Interno  <br/> |SPM  <br/> |Sí  <br/> |Todas las organizaciones de Office 365, Outlook.com  <br/> |
|Entre dominios  <br/> |SPOOF  <br/> |Sí  <br/> |Clientes de la Protección contra amenazas avanzada de Office 365 y E5 de  <br/> |

### <a name="changing-your-anti-spoofing-settings"></a>Cambiar la configuración contra la suplantación

Para crear o actualizar la configuración de directiva de suplantación (entre dominios), vaya a Protección contra suplantación de identidad \> Configuración contra la suplantación en la pestaña Administración de amenazas \> Directiva en el Centro de seguridad &amp; cumplimiento. Si no ha creado ninguna configuración contra suplantación de identidad, debe crearla:
  
![Protección contra la suplantación de identidad: crear una nueva directiva](media/9337ec91-270e-4fa7-9dfa-a51a2d1eb95e.jpg)
  
Si ya la ha creado, puede seleccionarla para modificarla:
  
![Protección contra la suplantación de identidad: modificar una directiva existente](media/75457a7c-882e-4984-80d1-21a12b42c53a.jpg)
  
Seleccione la directiva que acaba de crear y siga los pasos, como se describe en [Obtener más información sobre la inteligencia de suplantación de identidad](learn-about-spoof-intelligence.md).
  
![Habilitar o deshabilitar la protección contra la suplantación de identidad](media/c49e2147-c954-443c-9144-1cbd139e1166.jpg)
  
![Habilitar o deshabilitar las sugerencias de seguridad contra la suplantación de identidad](media/eec7c407-31fc-4f73-8325-307d82d1fb53.jpg)
  
Para crear una nueva directiva con PowerShell: 
  
```powershell
$org = Get-OrganizationConfig
$name = "My first anti-phishing policy for " + $org.Name
# Note: The name should not exclude 64 characters, including spaces.
# If it does, you will need to pick a smaller name.
# Next, create a new anti-phishing policy with the default values
New-AntiphishPolicy -Name $Name
# Select the domains to scope it to
# Multiple domains are specified in a comma-separated list
$domains = "domain1.com, domain2.com, domain3.com"
# Next, create the anti-phishing rule, scope it to the anti-phishing rule
New-AntiphishRule -Name $name -AntiphishPolicy $name -RecipientDomainIs $domains
```

Puede modificar los parámetros de la directiva contra suplantación de identidad con PowerShell, según la documentación en [Set-AntiphishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Set-AntiPhishPolicy?view=exchange-ps). Puede especificar el $name como parámetro:
  
```powershell
Set-AntiphishPolicy -Identity $name <fill in rest of parameters>
```

Más adelante en 2018, en lugar de tener que crear una directiva de forma predeterminada, se creará una que tenga como ámbito todos los destinatarios de la organización para que no tenga que especificarlos manualmente (las capturas de pantalla siguientes están sujetas a cambios antes de la implementación final).
  
![Directiva predeterminada contra la suplantación de identidad](media/1f27a0bf-e202-4e12-bbac-24baf013c8f9.jpg)
  
A diferencia de una directiva que cree, no puede eliminar la directiva predeterminada, modificar su prioridad o elegir el ámbito de usuarios, dominios o grupos con los que usarla.
  
![Detalles de la directiva predeterminada contra la suplantación de identidad](media/30c21ceb-df52-4c93-aa65-f44a55dc1009.jpg)
  
Configurar la protección predeterminada mediante PowerShell:
  
```powershell
$defaultAntiphishPolicy = Get-AntiphishPolicy | ? {$_.IsDefault -eq $true}
Set-AntiphishPolicy -Identity $defaultAntiphishPolicy.Name -EnableAntispoofEnforcement <$true|$false>
```

Sólo debe deshabilitar la protección contra la suplantación si tiene otro servidor o servidores de correo frente a Office 365 (vea Escenarios legítimos para deshabilitar la protección contra la suplantación de identidad para obtener más información).
  
```powershell
$defaultAntiphishPolicy = Get-AntiphishiPolicy | ? {$_.IsDefault $true}
Set-AntiphishPolicy -Identity $defaultAntiphishPolicy.Name -EnableAntispoofEnforcement $false 

```
> [!IMPORTANT]
> Si el primer paso en la ruta de acceso al correo electrónico es Office 365 y obtiene demasiados mensajes de correo electrónico legítimos marcados como suplantación de identidad, primero debe configurar la lista de remitentes permitidos para enviar correo electrónico falsificado a su dominio (vea la sección *"Administrar a remitentes legítimos que envían correo electrónico sin autenticar"* ). Si todavía recibe demasiados falsos positivos (es decir, mensajes legítimos marcados como falsificados), NO se recomienda deshabilitar la protección contra la suplantación por completo. Se recomienda elegir una protección básica en lugar de alta. Es mejor trabajar con los falsos positivos que exponer su organización a correos electrónicos falsificados que podrían llevar a costes significativamente superiores a largo plazo.

### <a name="managing-legitimate-senders-who-are-sending-unauthenticated-email"></a>Administrar a remitentes legítimos que envían correo electrónico sin autenticar

Office 365 realiza un seguimiento de quién está enviando correo sin autenticar en su organización. Si el servicio considera que el remitente no es legítimo, lo marcará como un error *compauth*. Esto se clasifica como SPOOF aunque depende de la directiva contra la suplantación que se aplicó al mensaje.
  
Pero, como administrador, puede especificar qué remitentes tienen permiso para enviar correo electrónico falsificado, invalidando la decisión de Office 365.
  
**Método 1: si su organización es propietaria del dominio, configure la autenticación de correo electrónico**
  
Este método puede usarse para resolver la suplantación de identidad dentro de la organización y entre dominios en caso de que es propietario o interactúa con varios espacios empresariales. También le ayuda a resolver la suplantación entre dominios donde envía a otros clientes de Office 365 y servicios de terceros hospedados en otros proveedores.
  
Para obtener más información, vea [Clientes de Office 365](#customers-of-office-365).

**Método 2: use la inteligencia de suplantación de identidad para configurar los remitentes permitidos de correo electrónico sin autenticar**
  
También puede usar la [inteligencia de suplantación de identidad](https://support.office.com/article/Learn-more-about-spoof-intelligence-978c3173-3578-4286-aaf4-8a10951978bf) para que los remitentes puedan enviar correos electrónicos sin autenticar a su organización. 
  
Para dominios externos, el usuario falsificado es el dominio de la dirección en De, mientras la infraestructura remitente es la dirección IP remitente (dividida en intervalos de CIDR /24) o el dominio de la organización del registro PTR (en la siguiente captura de pantalla, la dirección IP remitente puede ser 131.107.18.4, cuyo registro PTR es outbound.mail.protection.outlook.com y que debería mostrarse como outlook.com para la infraestructura remitente).
  
Para permitir que este remitente envíe correos electrónicos sin autenticar, cambie de **No** a **Sí**.
  
![Configurar remitentes permitidos en la protección contra la suplantación ](media/d4334921-d820-4334-8217-788279701e94.jpg)
  
También puede usar PowerShell para permitir que un remitente específico suplante su dominio:
  
```powershell
$file = "C:\My Documents\Summary Spoofed Internal Domains and Senders.csv"
```

```powershell
Get-PhishFilterPolicy -Detailed -SpoofAllowBlockList -SpoofType External | Export-CSV $file
```

![Obtener remitentes falsificados de Powershell](media/0e27ffcf-a5db-4c43-a19b-fa62326d5118.jpg)
  
En la imagen anterior, se han agregado saltos de línea adicionales para ajustar esta captura de pantalla. Normalmente, todos los valores aparecerían en una sola línea.
  
Edite el archivo y busque la línea que corresponde a outlook.com y bing.com, cambie la entrada AllowedToSpoof de No a Sí:
  
![Configuración de permiso de suplantación de identidad como Sí en Powershell](media/62340452-62d3-4958-9ce9-afe5275a870d.jpg)
  
Guarde el archivo y, después, ciérrelo:
  
```powershell
$UpdateSpoofedSenders = Get-Content -Raw "C:\My Documents\Spoofed Senders.csv"
Set-PhishFilterPolicy -Identity Default -SpoofAllowBlockList $UpdateSpoofedSenders
```

Ahora, esto le permitirá a bing.com enviar correos sin autenticar desde \*.outlook.com.

**Método 3: cree una entrada de permiso para el par de remitente y destinatario**
  
También puede evitar todos los filtros de spam para un remitente específico. Para obtener más información, vea [Cómo agregar de forma segura un remitente a una lista de permiso en Office 365](https://blogs.msdn.microsoft.com/tzink/2017/11/29/how-to-securely-add-a-sender-to-an-allow-list-in-office-365/).
  
Si usa este método, omitirá el filtrado de spam y algunos phishing, pero no omitirá el filtrado de malware.
  
**Método 4: póngase en contacto con el remitente y pídale que configure la autenticación de correo electrónico**
  
Por el problema del correo no deseado y la suplantación de identidad, Microsoft recomienda configurar la autenticación de correo electrónico a todos los remitentes. Si conoce a un administrador del dominio remitente, póngase en contacto con él y pídale que configure los registros de autenticación de correo electrónico para que no tenga que agregar invalidaciones. Para obtener más información, vea [Administradores de dominios que no son clientes de Office 365](#administrators-of-domains-that-are-not-office-365-customers) más adelante en este artículo. 
  
Aunque puede ser difícil empezar a enviar dominios para la autenticación, con el tiempo, como más filtros de correo electrónico comienzan a eliminar o incluso rechazan su correo electrónico, deberán configurar los registros adecuados para garantizar una mejor entrega.
  
### <a name="viewing-reports-of-how-many-messages-were-marked-as-spoofed"></a>Ver los informes de cuántos mensajes se marcan como falsificados

Cuando está habilitada la directiva contra la suplantación, puede usar las funciones de investigación y respuesta de amenazas para hacerse una idea de cuántos mensajes se marcan como phishing. Para ello, vaya al Centro de seguridad &amp; cumplimiento (SCC) en Administración de amenazas \> Explorador, establezca la vista phishing y ordene por dominio remitente o estado de protección:
  
![Vista de cuántos mensajes se marcan como phishing](media/de25009a-44d4-4c5f-94ba-9c75cd9c64b3.jpg)
  
Puede interactuar con los diversos informes para ver cuántos se han marcado como phishing, incluidos los mensajes marcados como SPOOF. Para obtener más información, vea [Introducción a la investigación de amenazas y respuestas de Office 365](get-started-with-ti.md).
  
Todavía no puede dividir los mensajes que se marcaron debido a la suplantación de identidad y otros tipos de phishing (como phishing general, suplantación de dominio o de usuario). Pero, más adelante, podrá hacerlo a través del Centro de seguridad &amp; cumplimiento. Una vez hecho, puede usar este informe como punto de partida para identificar los dominios remitentes que pueden ser legítimos y que se han marcado como suplantación de identidad debido a errores de autenticación.
  
La captura de pantalla siguiente es un ejemplo de cómo se mostrarán estos datos, pero puede que cambie a la hora de la publicación:
  
![Vista de los informes de suplantación de identidad por tipo de detección](media/dd25d63f-152c-4c55-a07b-184ecda2de81.jpg)
  
Para los clientes de ATP y E5, estos informes estarán disponibles más adelante en los informes de estado de protección contra amenazas (TPS), pero se retrasarán al menos 24 horas. Esta página se actualizará cuando se integren en el Centro de seguridad &amp; cumplimiento.
  
### <a name="predicting-how-many-messages-will-be-marked-as-spoof"></a>Predecir cuántos mensajes se marcarán como suplantación de identidad

Una vez que Office 365 actualiza su configuración para que pueda desactivar el cumplimiento de la protección contra la suplantación o pueda activarla a nivel de cumplimiento básico o alto, podrá ver que la disposición de mensajes cambiará según las distintas opciones de configuración. Es decir, si la protección contra la suplantación está desactivada, podrá ver cuántos mensajes se detectarán como suplantación de identidad si el cumplimiento se establece como básico; o bien, si ya es básico, podrá ver cuántos mensajes se detectarán como suplantación de identidad si se establece como alto.
  
Esta característica está actualmente en desarrollo. A medida de que se vayan definiendo más detalles, esta página se actualizará con capturas de pantalla del Centro de seguridad y cumplimiento y con ejemplos de PowerShell.
  
![El informe "Qué ocurre si" para habilitar la protección contra la suplantación](media/fdd085ae-02c1-4327-a063-bfe9a32ff1eb.jpg)
  
![Posible experiencia de usuario al permitir a un remitente falsificado](media/53f9f73e-fb01-47f3-9a6d-850c1aef5efe.jpg)
  
### <a name="legitimate-scenarios-to-disable-anti-spoofing"></a>Escenarios legítimos para deshabilitar la protección contra la suplantación

La protección contra la suplantación protege mejor a los clientes de los ataques de phishing y, por tanto, no se recomienda deshabilitarla. Si la deshabilita, puede resolver algunos falsos positivos a corto plazo, pero a largo plazo estará expuesto a más riesgos. Configurar la autenticación del lado del remitente o hacer ajustes en las políticas de phishing, generalmente son eventos únicos o requieren un mantenimiento mínimo y periódico. Pero, recuperarse de ataques de phishing en los que se han expuesto datos o se han puesto en riesgo los activos es mucho más peligroso.
  
Por ello, es mejor trabajar con los falsos positivos de la protección contra la suplantación de identidad que deshabilitarla.
  
Pero, hay un escenario legítimo donde debe deshabilitarse, es decir cuando hay productos de filtrado de correo electrónico adicionales en el enrutamiento de mensajes y Office 365 no es el primer paso en la ruta de acceso al correo electrónico:
  
![El registro MX del cliente no apunta a Office 365](media/62127c16-cfb8-4880-9cad-3c12d827c67e.jpg)
  
El otro servidor puede ser el servidor de correo de Exchange local, un dispositivo de filtrado de correo electrónico, como Ironport, u otro servicio hospedado en la nube. 
  
Si el registro MX del dominio del destinatario no apunta a Office 365, no es necesario deshabilitar la protección contra la suplantación porque Office 365 busca el registro MX de su dominio receptor y suprime la protección contra la suplantación si apunta a otro servicio. Si no sabe si su dominio tiene delante otro servidor, puede usar un sitio web como MX Toolbox para buscar el registro MX. Puede aparecer como se muestra a continuación:
  
![El registro MX indica que el dominio no apunta a Office 365](media/d868bb9f-3462-49aa-baea-9447a3ce4877.jpg)
  
Este dominio tiene un registro MX que no apunta a Office 365, por lo que Office 365 no aplica el cumplimiento de la protección contra la suplantación.
  
Pero, si el registro MX del dominio del destinatario *sí* apunta a Office 365, aunque hay otro servicio frente a Office 365, debe deshabilitar la protección contra la suplantación. El ejemplo más común es mediante la reescritura del destinatario: 
  
![Diagrama de enrutamiento para reescritura del destinatario](media/070d90d1-50a0-42e4-9fd3-920bc99a7cad.jpg)
  
El registro MX del dominio contoso.com apunta al servidor local, mientras que el registro MX del dominio @office365.contoso.net apunta a Office 365, porque contiene \*.protection.outlook.com o \*.eo.outlook.com en el registro MX:
  
![El registro MX apunta a Office 365, por tanto, probable reescritura del destinatario](media/4101ad51-ef92-4907-b466-b41d14d344ca.jpg)
  
No olvide diferenciar cuando el registro MX del dominio del destinatario no apunta a Office 365 y cuando se ha realizado una reescritura del destinatario. Es importante saber la diferencia entre estos dos casos.
  
Si no está seguro de si se ha realizado una reescritura de destinatario para su dominio receptor, a veces se ve en los encabezados del mensaje.
  
a) en primer lugar, observe los encabezados del mensaje para el dominio del destinatario en el encabezado de Authentication-Results:
  
```
Authentication-Results: spf=fail (sender IP is 1.2.3.4)
  smtp.mailfrom=example.com; office365.contoso.net; dkim=fail
  (body hash did not verify) header.d=simple.example.com;
  office365.contoso.net; dmarc=none action=none
  header.from=example.com; compauth=fail reason=001
```

El dominio del destinatario se encuentra en el texto rojo en negrita de la parte superior, en este caso office365.contoso.net. El destinatario en el encabezado Para: puede ser diferente:
  
Para: Destinatario de ejemplo \<destinatario @ contoso.com\>
  
Realice una búsqueda en el registro MX del dominio del destinatario real. Si contiene \*.protection.outlook.com, mail.messaging.microsoft.com, \*.eo.outlook.com o mail.global.frontbridge.com significa que MX apunta a Office 365.
  
Si no contiene dichos valores significa que MX no apunta a Office 365. Una herramienta que puede usar para comprobarlo es MX Toolbox.
  
Para este ejemplo concreto, la captura de pantalla siguiente indica que para contoso.com, el dominio que parece el destinatario ya que era el encabezado Para:, el registro MX apunta a un servidor local:
  
![Registro MX que apunta al servidor local](media/2444144a-9a90-4319-96b2-d115041f669f.jpg)
  
Pero, el destinatario real es office365.contoso.net, cuyo registro MX apunta a Office 365:
  
![MX que apunta a Office 365, debe ser reescritura del destinatario](media/10cf3245-9b50-475a-b655-d8a51f99d812.jpg)
  
Por lo tanto, para este mensaje probablemente se ha realizado una reescritura del destinatario.
  
b) en segundo lugar, asegúrese de distinguir entre los casos de uso común de reescritura del destinatario. Si vuelve a escribir el dominio del destinatario para \*.onmicrosoft.com, vuelva a escribirlo como \*. mail.onmicrosoft.com.
  
Una vez que haya identificado el dominio del destinatario final que se enruta detrás de otro servidor y el registro MX del dominio del destinatario apunta a Office 365 (como se publica en sus registros DNS), puede deshabilitar la protección contra la suplantación.
  
Recuerde que no se recomienda deshabilitar la protección contra la suplantación si el primer paso en la ruta de enrutamiento del dominio es Office 365. Se recomienda solo cuando está detrás de uno o más servicios.
  
### <a name="how-to-disable-anti-spoofing"></a>Deshabilitar la protección contra la suplantación

Si ya creó una directiva contra la suplantación de identidad, establezca el parámetro EnableAntispoofEnforcement como $false:
  
```
$name = "<name of policy>"
Set-AntiphishPolicy -Identity $name -EnableAntiSpoofEnforcement $false

```

Si no conoce el nombre de la directiva (o directivas) para deshabilitar, puede mostrarlas:
  
```
Get-AntiphishPolicy | fl Name
```

Si no tiene ninguna directiva contra la suplantación de identidad existente, puede crearla y deshabilitarla (incluso si no tiene una directiva, se sigue aplicando la protección contra la suplantación; más adelante en 2018, se creará una directiva predeterminada que, después, puede deshabilitar en lugar de crear una nueva). Deberá seguir varios pasos:
  
```
$org = Get-OrganizationConfig
$name = "My first anti-phishing policy for " + $org.Name
# Note: If the name is more than 64 characters, you will need to choose a smaller one
```

```
# Next, create a new anti-phishing policy with the default values
New-AntiphishPolicy -Name $Name
# Select the domains to scope it to
# Multiple domains are specified in a comma-separated list
$domains = "domain1.com, domain2.com, domain3.com"
# Next, create the anti-phishing rule, scope it to the anti-phishing rule
New-AntiphishRule -Name $name -AntiphishPolicy -RecipientDomainIs $domains
# Finally, scope the anti-phishing policy to the domains
Set-AntiphishPolicy -Identity $name -EnableAntispoofEnforcement $false

```

Se puede deshabilitar la protección contra la suplantación solo mediante el cmdlet (más adelante estará disponible en el centro de seguridad &amp; cumplimiento). Si no tiene acceso a PowerShell, cree un vale de soporte.
  
Recuerde que debe aplicarse a los dominios que se someten a un enrutamiento indirecto cuando se envían a Office 365. Resista la tentación de deshabilitar la protección contra la suplantación debido a algunos falsos positivos, será mejor trabajar con ellos a largo plazo.
  
### <a name="information-for-individual-users"></a>Información para usuarios individuales

Los usuarios individuales tienen una interacción limitada con la sugerencia de seguridad contra la suplantación. Pero, hay varias cosas que puede realizar para solucionar escenarios comunes.
 
### <a name="common-scenario-1---discussion-lists"></a>Escenario común n.º 1: listas de discusión

Se sabe que las listas de discusión tienen problemas con la protección contra la suplantación debido a la forma en que reenvían el mensaje y modifican su contenido, pero conservan la dirección De: original.
  
Por ejemplo, supongamos que su dirección de correo electrónico es usuario @ contoso.com, le interesa la observación de aves y se une a la lista de discusión de observadoresdeaves @ ejemplo.com. Cuando envía un mensaje a la lista de discusión, puede enviarlo así:
  
**De:** Jorge Montoya \<usuario @ contoso.com\> 
  
**Para:** lista de discusión de observadores de aves \<observadoresdeaves @ ejemplo.com\> 
  
**Asunto:** Excelente vista de arrendajos azules en la cima del Monte Rainier esta semana 
  
¿Alguien quiere echar un vistazo a la vista de esta semana desde el Monte Rainier?
  
Cuando la lista de correo electrónico recibe el mensaje, le da formato, modifica su contenido y lo reproduce para el resto de los miembros de la lista de discusión, que consta de los participantes de muchos destinatarios de correos electrónicos diferentes.
  
**De:** Jorge Montoya \<usuario @ contoso.com\> 
  
**Para:** lista de discusión de observadores de aves \<observadoresdeaves @ ejemplo.com\> 
  
**Asunto:** [OBSERVADORESDEAVES] Excelente vista de arrendajos azules en la cima del Monte Rainier esta semana 
  
¿Alguien quiere echar un vistazo a la vista de esta semana desde el Monte Rainier?
  
---
  
Este mensaje se envió a la lista de discusión de observadores de aves. Puede cancelar la suscripción en cualquier momento.
  
En el ejemplo anterior, el mensaje reproducido tiene la misma dirección De: (usuario @ contoso.com), pero el mensaje original se ha modificado y se han agregado una etiqueta en la línea de asunto y un pie de página en la parte inferior del mensaje. Este tipo de modificación del mensaje es común en las listas de distribución de correo y puede producir falsos positivos.
  
Si usted o alguien de su organización es un administrador de la lista de distribución de correo, puede configurarlo para pasar las comprobaciones de protección contra la suplantación.
  
- Consulte las preguntas más frecuentes en DMARC.org: [Manejo una lista de distribución de correo y quiero interactúan con DMARC, ¿qué debo hacer?](https://dmarc.org/wiki/FAQ#I_operate_a_mailing_list_and_I_want_to_interoperate_with_DMARC.2C_what_should_I_do.3F)

- Lea las instrucciones en esta entrada de blog: [Una sugerencia para los operadores de la lista de distribución de correo para interactuar con DMARC sin errores](https://blogs.msdn.microsoft.com/tzink/2017/03/22/a-tip-for-mailing-list-operators-to-interoperate-with-dmarc-to-avoid-failures/)

- Considere instalar las actualizaciones en el servidor de la lista de distribución de correo para admitir ARC, vea [https://arc-spec.org](https://arc-spec.org/)

Si no tiene la propiedad de la lista de distribución de correo:
  
- Puede solicitar al encargado de la lista de distribución de correo que implemente una de las opciones anteriores (también deben tener configurada la autenticación de correo electrónico para el dominio desde el que se retransmite la lista de distribución de correo)

- Puede crear reglas de buzón en el cliente de correo para mover mensajes a la Bandeja de entrada. Además, puede solicitar los administradores de su organización que configuren reglas de permiso o invalidaciones, como se describe en la sección Administrar a remitentes legítimos que envían correo electrónico sin autenticar

- Puede crear un vale de soporte con Office 365 para crear una invalidación de la lista de distribución de correo y usarla como legítima

### <a name="other-scenarios"></a>Otros escenarios

1. Si ninguno de los escenarios comunes anteriores se aplica a su situación, informe del mensaje como un falso positivo a Microsoft. Para obtener más información, vea la sección [¿Cómo señalar mensajes de correo no deseado o correo deseado a Microsoft?](#how-can-i-report-spam-or-non-spam-messages-back-to-microsoft) más adelante en este artículo. 

2. También puede contactarse con el administrador de correo electrónico que puede crear una incidencia de soporte técnico para Microsoft. El equipo de ingeniería de Microsoft investigará por qué el mensaje se marcó como una suplantación de identidad.

3. Además, si sabe quién es el remitente y está seguro de que no es una suplantación malintencionada, puede responder al remitente indicándole que está enviando mensajes desde un servidor de correo que no se autentica. A veces, el resultado es que el remitente original se pone en contacto con su administrador de TI, que configurará los registros de autenticación de correo electrónico necesarios.
  
Cuando hay suficientes remitentes que responden a los propietarios de dominios pidiéndoles que configuren los registros de autenticación de correo electrónico, es más probable que tomen medidas. Aunque Microsoft también trabaja con los propietarios de dominios para publicar los registros necesarios, es aún más efectivo cuando los usuarios individuales lo solicitan.

4. Opcionalmente, puede agregar el remitente a la lista de remitentes seguros. Pero, tenga en cuenta que si un atacante suplanta esa cuenta, el mensaje se entregará a su buzón. Por lo tanto, esta opción debería usarse con moderación.

## <a name="how-senders-to-microsoft-should-prepare-for-anti-spoofing-protection"></a>Cómo los remitentes a Microsoft deberían prepararse para la protección contra la suplantación de identidad.

Si es un administrador que actualmente envía mensajes a Microsoft, Office 365 u Outlook.com, deberá asegurarse de que el correo electrónico se autentica correctamente. En caso contrario, es posible que se marque como spam o phishing.
  
### <a name="customers-of-office-365"></a>Clientes de Office 365

Si es cliente de Office 365 y usa Office 365 para enviar correo electrónico saliente:
  
- Para sus dominios, vea [Configurar SPF en Office 365 para evitar la suplantación de identidad](set-up-spf-in-office-365-to-help-prevent-spoofing.md)

- Para sus dominios principales, vea [Usar DKIM para validar el correo electrónico saliente enviado desde su dominio personalizado en Office 365](use-dkim-to-validate-outbound-email.md)

- Puede [configurar los registros DMARC](use-dmarc-to-validate-email.md) para su dominio para determinar la lista de remitentes legítimos

Microsoft no proporciona instrucciones detalladas de implementación para cada SPF, DKIM y DMARC. Pero, hay una gran cantidad de información publicada en línea. También hay compañías de terceros dedicadas a ayudar a su organización a configurar los registros de autenticación de correo electrónico.
  
### <a name="administrators-of-domains-that-are-not-office-365-customers"></a>Administradores de dominios que no son clientes de Office 365

Si es un administrador de dominio, pero no es un cliente de Office 365:
  
- Debe configurar SPF para publicar direcciones IP de envío de su dominio y configurar DKIM (si disponible) para firmar digitalmente los mensajes. También puede configurar los registros DMARC.

- Si tiene remitentes de forma masiva que transmiten correos electrónicos en su nombre, debe trabajar con ellos para enviar correos electrónicos de forma que del dominio remitente en la dirección De: (si le pertenece) se alinea con el dominio que no produce error SPF o DMARC.

- Si tiene servidores de correo locales o envía correos desde un proveedor de Software como servicio o desde un servicio de hospedaje de nube como Microsoft Azure, GoDaddy, Rackspace, Amazon Web Services o similares, debería asegurarse de que se agregan al registro SPF. 

- Si es un dominio pequeño hospedado por un ISP, debe configurar el registro SPF según las instrucciones que le proporcionó su ISP. La mayoría de ISP proporcionan estos tipos de instrucciones y pueden encontrarse en las páginas de soporte técnico de la compañía.

- Incluso si no ha tenido que publicar registros de autenticación de correo electrónico antes y le ha funcionado bien, debe publicar registros de autenticación de correo electrónico para enviarlos a Microsoft. Al hacerlo, estará ayudando en la lucha contra la suplantación de identidad y reduciendo la posibilidad de que usted o las organizaciones a las que envíe mensajes sean suplantados.

### <a name="what-if-you-dont-know-who-sends-email-as-your-domain"></a>¿Qué pasa si no sabe quién envía correos electrónicos con su dominio?

Muchos dominios no publican registros SPF ya que no conocen todos los remitentes. No pasa nada, no es necesario que los conozca todos. En su lugar, debe empezar publicando un registro SPF para los que conoce, especialmente donde se encuentra el tráfico corporativo y publicar una política de SPF neutra, ?all:
  
ejemplo.com IN TXT "v = spf1 include:spf.ejemplo.com ?all"
  
La directiva de SPF neutra significa que todos los correos electrónicos que se incluyen en su infraestructura corporativa no producirán un error de autenticación en todos los otros destinatarios de correo electrónico. Los correos electrónicos de los remitentes que no conozca volverán a pasar a neutral, que es prácticamente lo mismo que no publicar ningún registro SPF.
  
Al enviar a Office 365, los correos electrónicos de su tráfico corporativo se marcarán como autenticados, pero es posible que los correos electrónicos de orígenes que no conozca aún se marquen como suplantación de identidad (dependiendo de si Office 365 puede autenticarlo implícitamente o no). Pero, sigue siendo una mejora a que Office 365 marque todo el correo electrónico como suplantación de identidad.
  
Una vez que haya iniciado un registro SPF con una directiva de reserva de ?all, puede incluir gradualmente más infraestructura de envío y publicar después una directiva más estricta. 
  
### <a name="what-if-you-are-the-owner-of-a-mailing-list"></a>¿Qué ocurre si es el propietario de una lista de distribución de correo?

Vea la sección [Escenario común n.º 1: listas de discusión](#common-scenario-1---discussion-lists).
  
### <a name="what-if-you-are-an-infrastructure-provider-such-as-an-internet-service-provider-isp-email-service-provider-esp-or-cloud-hosting-service"></a>¿Qué ocurre si es un proveedor de infraestructura como un proveedor de servicios de Internet (ISP), un proveedor de servicio de correo electrónico (ESP) o servicio de hospedaje en la nube?

Si hospeda un correo electrónico de un dominio y este dominio envía correos electrónicos o si proporciona una infraestructura de hospedaje que puede enviar correo electrónico, haga lo siguiente:
  
- Asegúrese de que los clientes disponen de documentación en la que se detalla lo que se publicará en sus registros SPF

- Considere añadir firmas DKIM en el correo electrónico saliente, incluso si el cliente no lo configura explícitamente (firma con un dominio predeterminado). Puede incluso añadir dos firmas DKIM en el correo electrónico (una con el dominio del cliente, si lo ha configurado, y otra con la firma DKIM de su empresa)

No se garantiza la capacidad de entrega a Microsoft aunque se autentique el correo electrónico que proviene de su plataforma, pero al menos se garantiza que Microsoft no marque el correo electrónico como no deseado por no estar autenticado. Para obtener más información sobre cómo Outlook.com filtra el correo electrónico, vea la [página del Administrador de correo de Outlook.com](https://postmaster.live.com/pm/postmaster.aspx).
  
Para obtener más información sobre procedimientos recomendados de proveedores de servicio, vea [Procedimientos recomendados de mensajería móvil de M3AAWG para proveedores de servicios](https://www.m3aawg.org/sites/default/files/M3AAWG-Mobile-Messaging-Best-Practices-Service-Providers-2015-08.pdf).
  
## <a name="frequently-asked-questions"></a>Preguntas más frecuentes

### <a name="why-is-microsoft-making-this-change"></a>¿Por qué Microsoft realiza este cambio?

Debido al impacto de los ataques de phishing y como la autenticación de correo electrónico existe desde hace más de 15 años, Microsoft cree que el riesgo de seguir permitiendo correos electrónicos sin autenticar es mayor que el riesgo de perder correos electrónicos legítimos.
  
### <a name="will-this-change-cause-legitimate-email-to-be-marked-as-spam"></a>¿Debido a este cambio un correo electrónico legítimo puede que se marque como spam?

Al principio, habrá algunos mensajes marcados como spam. Sin embargo, con el tiempo, se ajustarán los remitentes y la cantidad de mensajes etiquetados como falsificados será mínima para la mayoría de las rutas de correo electrónico.
  
Inicialmente, Microsoft adoptó esta característica varias semanas antes de implementarla para el resto de sus clientes. Aunque hubo complicaciones al principio, se fueron reduciendo gradualmente.
  
### <a name="will-microsoft-bring-this-feature-to-outlookcom-and-non-advanced-threat-protection-customers-of-office-365"></a>¿Microsoft proporcionará esta característica para clientes de Outlook.com y clientes sin Protección contra amenazas avanzada de Office 365?

La tecnología contra la suplantación de Microsoft se implementó inicialmente para las organizaciones que tenían una suscripción a Office 365 Enterprise E5 o que habían comprado el complemento de Protección contra amenazas avanzada de Office 365 (ATP) para su suscripción. A partir de octubre de 2018, la protección se ha ampliado también para las organizaciones con Exchange Online Protection (EOP). En el futuro, es posible que se publique para Outlook.com. Pero, si esto ocurre, puede que no se apliquen algunas funciones, como invalidaciones personalizadas e informes.
  
### <a name="how-can-i-report-spam-or-non-spam-messages-back-to-microsoft"></a>¿Cómo señalar mensajes de correo no deseado o correo deseado a Microsoft?

Puede usar el [complemento de mensaje de informe para Outlook](https://support.office.com/article/use-the-report-message-add-in-b5caa9f1-cdf3-4443-af8c-ff724ea719d2) o, si no está instalado, vea [Enviar mensajes de análisis de spam, correo deseado y phishing a Microsoft](https://technet.microsoft.com/es-ES/library/jj200769%28v=exchg.150%29.aspx).
  
### <a name="im-a-domain-administrator-who-doesnt-know-who-all-my-senders-are"></a>Soy un administrador de dominios y no sé quiénes son mis remitentes.

Vea [Administradores de dominios que no son clientes de Office 365](#administrators-of-domains-that-are-not-office-365-customers).
  
### <a name="what-happens-if-i-disable-anti-spoofing-protection-for-my-organization-even-though-office-365-is-my-primary-filter"></a>¿Qué ocurre si deshabilito la protección contra la suplantación de mi organización, aunque Office 365 es el filtro principal?

Esto no se recomienda porque estará expuesto a más intentos de mensajes de phishing y spam. No todos los casos de phishing son spoofing y no todos los spoofing pasarán sin detectarse. Pero, el riesgo será mayor que para un cliente que habilita la protección contra la suplantación.
  
### <a name="does-enabling-anti-spoofing-protection-mean-i-will-be-protected-from-all-phishing"></a>¿Habilitar la protección contra la suplantación significa estar protegido de todo tipo de suplantación?

Desafortunadamente no, porque los suplantadores se adaptarán para usar otras técnicas como cuentas comprometidas y configuración de cuentas de servicios gratuitos. Pero, la protección contra suplantación de identidad funciona mejor para detectar estos otros tipos de métodos de phishing porque las capas de protección de Office 365 están diseñadas para trabajar juntas y se crean una encima de otra.
  
### <a name="do-other-large-email-receivers-block-unauthenticated-email"></a>¿Otros grandes receptores de correo bloquean correos electrónicos sin autenticar? 

Casi todos los grandes receptores de correo implementan SPF, DKIM y DMARC tradicional. Algunos receptores tienen otras comprobaciones más estrictas además de estos estándares, pero pocos van tan lejos como Office 365 para bloquear el correo electrónico no autenticado y tratarlo como suplantación de identidad. Pero, la mayor parte del sector está pasando a ser más estricta respecto a este tipo concreto de correo electrónico, especialmente debido al problema de phishing.
  
### <a name="do-i-still-need-the-advanced-spam-filtering-option-enabled-for-spf-hard-fail-if-i-enable-anti-spoofing"></a>¿Necesito todavía una opción avanzada de filtrado de correo no deseado habilitada para "SPF hard fail" (errores no recuperables) si habilito la protección contra la suplantación?

No, esta opción ya no es necesaria porque la función contra la suplantación considera un conjunto de criterios mucho más amplio, además de los errores no recuperables de SPF. Si habilita la protección contra la suplantación y la opción de errores no recuperables de SPF, es posible que reciba más falsos positivos. Se recomienda deshabilitar esta característica porque que no proporcionan casi ninguna mejora adicional para spam o phishing y genera principalmente falsos positivos.
  
### <a name="does-sender-rewriting-scheme-srs-help-fix-forwarded-email"></a>¿El Sender Rewriting Scheme (SRS) ayuda a solucionar el correo electrónico reenviado?

SRS solo soluciona parcialmente el problema del correo electrónico reenviado. Al volver a escribir el SMTP MAIL FROM, SRS puede asegurarse de que un mensaje reenviado no produce un error de SPF en el destino siguiente. Pero, como la protección contra la suplantación se basa en la combinación entre la dirección De: y los dominios con firma MAIL FROM o DKIM (u otras señales), no es suficiente evitar que el correo reenviado se marque como falsificado. 
